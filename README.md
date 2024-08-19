# Ulysses-RFCorpus
Relevance Feedback corpus for Legal Information Retrieval.

Link: https://drive.google.com/file/d/1AstJwYZhiPUx-wKahwOxrTuJ7td5rLMi/view?usp=share_link

How to cite: 
Vitório, D., Souza, E., Martins, L. et al. Building a relevance feedback corpus for legal information retrieval in the real-case scenario of the Brazilian Chamber of Deputies. Lang Resources & Evaluation (2024). https://doi.org/10.1007/s10579-024-09767-3

Contact: damsv@cin.ufpe.br

-----------------------------------------------------------------

Contents:

1. bills_dataset.csv
   -
   Dataset containing legislative proposals from the Brazilian Chamber of Deputies, with the following attributes:
   - code - the bill's ID;
   - sig_tipo - the bill's type, from eight different ones: Recommendation (Indicação - INC); Legislative Decree Project (Projeto de Decreto Legislativo - PDL or PDC); Law Project (Projeto de Lei - PL); Inspection and Control Proposal (Proposta de Fiscalização e Controle - PFC); Complementary Law Project (Projeto de Lei Complementar - PLP or PLC); Resolution Project (Projeto de Resolução - PRC or PRN); Conversion Law Project (Projeto de Lei de Conversão - PLV); and Constitutional Amendment Proposal (Proposta de Emenda Constituicional - PEC);
   - name - the bill's name, informing its type, number, and year, e.g., "PL 5634/2019";
   - text_ementa - the bill's summary;
   - em_tramitacao - whether the bill is active or not;
   - situacao - the bill's status at the moment, e.g., "awaiting reply", "awaiting dispatch", "awaiting submission to the Senate";
   - text - the bill itself, in plain text;
   - text_preprocessed - the bill's text pre-processed with the same techniques presented in Souza et al. (2021).
  
3. relevance_feedback_dataset.csv
   -
   Dataset containing queries, a list of retrieved documents and their relevance judgements, with the following attributes:
   - id - the query's ID;
   - query - the query's plain text;
   - user_feedback - the record of the feedback given by the expert;
   - extra_results - the list of relevant documents not retrieved by the model and provided by the expert;
   - date_created - the timestamp of feedback;
   - num_doc_feedback - number of documents judged for each query;
   - extra_results_size - size of the list of extra_results.

   The user_feedback attribute contains a dictionary with the following keys:
   - id - the name of the document;
   - class - the relevance level for the document: "i" for irrelevant, "r" for very relevant, or "pr" for somewhat relevant (translated as "pouco relevante" in Portuguese);
   - score - the BM25L score for that document;
   - normalized_score - the score normalized between 0 and 1.
