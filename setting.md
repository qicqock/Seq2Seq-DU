- modify execute python file directory
- recommend the version of tensorflow-gpu < 2.0
- add current directory in sys. (train_and_predict.py 28 lines)
- download and insert in Seq2Seq-DU directory
    - https://github.com/google-research-datasets/dstc8-schema-guided-dialogue
    - https://github.com/google-research/bert/ (12-768 Bert-base)
- KeyError 'USE' and 'SYS' (user and system)
    - remove related code in data utils.py
    - but [USE] and [SYS] should be needed to distinguish user and sys turn.
    - solutions
        - add [USE] and [SYS] in bert-based vocab.txt
        <!-- - change vocab_size to 32524 in bert_config.json -->
        <!-- - tokenizer.add_special_tokens(["[USE] ... "])
        - extend the length of special_token_embedding -->

    related links
    - https://github.com/huggingface/tokenizers/issues/247
    - https://stackoverflow.com/questions/69191305/how-to-add-new-special-token-to-the-tokenizer 

- Multi GPU training issues
    - doesn't work with strategy that support in the tensorflow
    - Horovod
    