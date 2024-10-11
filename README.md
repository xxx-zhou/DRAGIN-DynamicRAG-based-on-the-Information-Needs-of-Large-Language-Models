# Dynamic Retrieval Augmented Generation based on the Information Needs of Large Language Models


## Research Background

1. **Research Issue**: 
   A major challenge in the application of large language models (LLMs) is the limited ability to dynamically acquire relevant and timely information during interaction with external sources. The existing retrieval augmentation techniques, like Retrieval-Augmented Generation (RAG), lack the ability to dynamically partition the information space and provide targeted knowledge for LLMs.
   
2. **Objective**: 
   The core research objective is to find methods for improving LLMs' access to necessary external information during generation, and to devise ways to enhance dynamic retrieval based on the model's information needs.

3. **Related Work**: 
   While prior work has explored static and dynamic augmentation for LLMs, including single retrieval systems like FLARE, token-based augmentation, and multi-level retrieval strategies, they lack flexibility. The paper aims to extend this by using dynamic partition strategies such as DRAGIN, combining aspects of previous RAG approaches, with the potential to achieve higher retrieval and generation efficiency.

---

## Methodology

This paper introduces the **DRAGIN** framework, designed to address dynamic information augmentation needs during text generation with LLMs. The key methodologies are described as follows:

1. **Real-time Information Distribution (RIND)**: 
   RIND enhances LLM performance by estimating the distribution of information across tokens and incorporating this estimation into dynamic decision-making during generation. The mathematical model to represent token information is:

  $$\
   H_i = - \sum_{v \in V} p_i(v) \log p_i(v)
   $$
   
   Where \( p_i(v) \) represents the probability distribution of token \( v \).

2. **Query-based Feedback System (QFS)**: 
   QFS refines LLMs by utilizing feedback from dynamic information retrieval systems, enabling faster retrieval and generation efficiency. This is modeled using a Transformer-based architecture, represented as:

  $$\
   A = \text{softmax} \left( \frac{Q K^T}{\sqrt{d_k}} \right) V
   $$  
   
   Where:
   - \( A \) denotes attention weights,
   - \( Q \) represents query tokens,
   - \( K \) represents key tokens, and
   - \( V \) represents value tokens.

3. **Inspection and Validation**: 
   The combination of RIND and QFS provides real-time feedback and inspection during LLM text generation. This helps to validate the knowledge retrieved dynamically and boosts performance across various tasks.

---

## Experiment Design

1. **Datasets**: 
   The model was evaluated on three widely used datasets:
   - WikiMultiHopQA
   - HotpotQA
   - StrategyQA-IR

2. **Metrics**: 
   Various evaluation metrics were used, including:
   - **EM (Exact Match)**
   - **F1 Score**

---

## Results and Analysis

1. **General Performance**: 
   DRAGIN outperforms traditional methods on all datasets. For instance, on WikiMultiHopQA, DRAGIN achieved an EM score of 0.304 and an F1 score of 0.3931, which is a significant improvement over other models.

2. **Efficiency Analysis**: 
   While FLARE demonstrated the best retrieval efficiency, DRAGIN was a close second, followed by FS-RAG and FL-RAG.

3. **Generalization Capabilities**: 
   DRAGIN exhibited robust performance across datasets, especially in generalization to unseen tasks, further validating the dynamic retrieval approach.

4. **Ablation Study**: 
   When compared to traditional retrieval methods (FS-RAG and FL-RAG), DRAGIN shows better inspection and query accuracy, particularly when querying specific tokens.

5. **GPT-based Comparison**: 
   DRAGIN's performance surpassed GPT models in several areas, though RAG models showed some advantages in specific cases.

---

## Conclusion

This paper presents **DRAGIN**, a dynamic retrieval framework utilizing RIND and QFS to significantly improve the dynamic retrieval capabilities of LLMs. DRAGIN demonstrated superior performance across multiple datasets, outperforming static and semi-dynamic retrieval methods. Future work will explore further optimization and generalization of this framework for broader applications.

---

## References
- WikiMultiHopQA, HotpotQA, StrategyQA-IR datasets used for evaluation.
- LLMs tested include: LLaMA-2-Chat-7B, LLaMA-2-Chat-13B, Vicuna-13B-v1.5.

