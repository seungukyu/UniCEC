# UniGEC
We introduce the **Unified-replacement GEC(Grammatical Error Correction) Dataset**, which combines results from multiple models to determine the likelihood of substituting synonyms for specific keywords. We collected a [research paper summary dataset](https://aihub.or.kr/aihubdata/data/view.do?currMenu=115&topMenu=100&aihubDataSe=realm&dataSetSn=90), covering eight domains. We used multiple LLMs (``EXAONE-3.0-7.8B-Instruct``, ``KULLM3``, ``Llama-3.1-8B-Instruct``) and PLMs (``bert-base``, ``xlm-roberta-base``) to extract keywords and their synonyms, based on token occurrence probabilities.

<img width="2181" alt="Image" src="https://github.com/user-attachments/assets/dc56f6e5-15aa-4135-b947-f5258842eda0" />

### Examples
We crawled synonyms in [Naver Korean Dictionary](https://ko.dict.naver.com).
|original_text|본 논문은 명나라 만력 연간에 매정조가 출간한 중국의 역대 기녀 전기집인 『청니연화기』에 관한 연구이다. 이 책은 한나라부터 명나라까지의 기녀에 관한 기록을 각종 문헌 속에서 골라 엮은 것인데, 당시에 기루가 발전하면서 명기에 대한 품조 현상이 유행한 것과 심학의 발전으로 인한 만명사조의 영향, 그리고 명기에 빗댄 사대부들을 향한 비판 의식 등이 출간 배경이라고 할 수 있다.|
|:---|:---|
|extracted keywords|'비판', '명나라'|
|synonyms of keywords|{'비판': ['논평', '비난', '비평', '판단', '평', '평가', '평론', '힐난']}, {'명나라': ['명']}|
|substituted_text|본 논문은 **명** 만력 연간에 매정조가 출간한 중국의 역대 기녀 전기집인 『청니연화기』에 관한 연구이다. 이 책은 한나라부터 **명**까지의 기녀에 관한 기록을 각종 문헌 속에서 골라 엮은 것인데, 당시에 기루가 발전하면서 명기에 대한 품조 현상이 유행한 것과 심학의 발전으로 인한 만명사조의 영향, 그리고 명기에 빗댄 사대부들을 향한 **비난** 의식 등이 출간 배경이라고 할 수 있다.|
