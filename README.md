
# Discourse Connective Marker Tool

This tool automatically generates the USR format from Hindi sentences. It can be used either through an internal API (requires IIIT-H VPN) or run locally on your machine.

---

## Requirements

- Python 3.x

---

## Setup and Usage (Local)

### 1. Clone the repository

Run the following command to clone the repository:

```bash
git clone https://github.com/riyatomar/USR_Builder.git
cd USR_Builder
```

---

### 2. Prepare Input

There will be 2 json input files with IO Directory:

(i) discourse_output.json: This json has Discourse Information with in segments.

```json
[
    {
        "dependent_sent_id": "None",
        "discourse_marker": "None",
        "discourse_relation": "समुच्चय",
        "head_sent_id": "None",
        "project_id": "1",
        "sent_1": "कौन तुम्हें यह काम करने को कह रहा है ?",
        "sent_1_id": "41",
        "sent_2": "क्या किसी ने यह किताब पढ़ी है ?",
        "sent_2_id": "42"
    }
]
```
(ii) updated_parser_output.json: This json includes Parser, NER, Morph, Simple and Complex Concept Information.

```json
{
    "response": [
        {
            "parser_output": [
                {
                    "dependency_relation": "k1",
                    "head_index": "7",
                    "index": 1,
                    "original_word": "कौन",
                    "pos_tag": "WQ",
                    "wx_word": "kOna",
                    "morph_info": {
                        "root": "kOna",
                        "cat": "p",
                        "case": "d",
                        "parsarg": "0",
                        "gen": "m",
                        "num": "s",
                        "per": "a"
                    }
                },
                {
                    "dependency_relation": "k2",
                    "head_index": "7",
                    "index": 2,
                    "original_word": "तुम्हें",
                    "pos_tag": "PRP",
                    "wx_word": "wumheM",
                    "morph_info": {
                        "root": "wU",
                        "cat": "p",
                        "case": "o",
                        "parsarg": "ko",
                        "gen": "f",
                        "num": "p",
                        "per": "m_h1"
                    }
                },
                {
                    "dependency_relation": "nmod__adj",
                    "head_index": "4",
                    "index": 3,
                    "original_word": "यह",
                    "pos_tag": "DEM",
                    "wx_word": "yaha",
                    "morph_info": {
                        "root": "yaha",
                        "cat": "p",
                        "case": "d",
                        "parsarg": "0",
                        "gen": "m",
                        "num": "s",
                        "per": "a"
                    }
                },
                {
                    "dependency_relation": "k2",
                    "head_index": "5",
                    "index": 4,
                    "original_word": "काम",
                    "pos_tag": "NN",
                    "wx_word": "kAma",
                    "morph_info": {
                        "root": "kAma",
                        "cat": "n",
                        "case": "d",
                        "gen": "m",
                        "num": "s"
                    }
                },
                {
                    "dependency_relation": "k2",
                    "head_index": "7",
                    "index": 5,
                    "original_word": "करने",
                    "pos_tag": "VM",
                    "wx_word": "karane",
                    "morph_info": {
                        "root": "kara",
                        "cat": "v",
                        "gen": "m",
                        "num": "p",
                        "per": "a",
                        "tam": "nA"
                    }
                },
                {
                    "dependency_relation": "lwg__psp",
                    "head_index": "5",
                    "index": 6,
                    "original_word": "को",
                    "pos_tag": "PSP",
                    "wx_word": "ko",
                    "morph_info": {
                        "root": "ko",
                        "cat": "prsg"
                    }
                },
                {
                    "dependency_relation": "main",
                    "head_index": "0",
                    "index": 7,
                    "original_word": "कह",
                    "pos_tag": "VM",
                    "wx_word": "kaha",
                    "morph_info": {
                        "root": "kaha",
                        "cat": "v",
                        "gen": "f",
                        "num": "s",
                        "per": "a",
                        "tam": "0"
                    }
                },
                {
                    "dependency_relation": "lwg__vaux",
                    "head_index": "7",
                    "index": 8,
                    "original_word": "रहा",
                    "pos_tag": "VAUX",
                    "wx_word": "rahA",
                    "morph_info": {
                        "root": "raha",
                        "cat": "v",
                        "gen": "m",
                        "num": "s",
                        "per": "a",
                        "tam": "yA"
                    }
                },
                {
                    "dependency_relation": "lwg__vaux_cont",
                    "head_index": "8",
                    "index": 9,
                    "original_word": "है",
                    "pos_tag": "VAUX",
                    "wx_word": "hE",
                    "morph_info": {
                        "root": "hE",
                        "cat": "v",
                        "gen": "m",
                        "num": "s",
                        "per": "a",
                        "tam": "hE"
                    }
                },
                {
                    "dependency_relation": "rsym",
                    "head_index": "7",
                    "index": 10,
                    "original_word": "?",
                    "pos_tag": "SYM",
                    "wx_word": "?"
                }
            ],
            "project_id": "1",
            "sentence": "कौन तुम्हें यह काम करने को कह रहा है ?",
            "sentence_id": "41"
        },
        {
            "parser_output": [
                {
                    "dependency_relation": "adv",
                    "head_index": "6",
                    "index": 1,
                    "original_word": "क्या",
                    "pos_tag": "WQ",
                    "wx_word": "kyA",
                    "morph_info": {
                        "root": "kyA",
                        "cat": "p",
                        "case": "d",
                        "parsarg": "0",
                        "gen": "m",
                        "num": "s",
                        "per": "a"
                    }
                },
                {
                    "dependency_relation": "k1",
                    "head_index": "6",
                    "index": 2,
                    "original_word": "किसी",
                    "pos_tag": "PRP",
                    "wx_word": "kisI",
                    "morph_info": {
                        "root": "kisI"
                    }
                },
                {
                    "dependency_relation": "lwg__psp",
                    "head_index": "2",
                    "index": 3,
                    "original_word": "ने",
                    "pos_tag": "PSP",
                    "wx_word": "ne",
                    "morph_info": {
                        "root": "ne",
                        "cat": "prsg"
                    }
                },
                {
                    "dependency_relation": "nmod__adj",
                    "head_index": "5",
                    "index": 4,
                    "original_word": "यह",
                    "pos_tag": "DEM",
                    "wx_word": "yaha",
                    "morph_info": {
                        "root": "yaha",
                        "cat": "p",
                        "case": "d",
                        "parsarg": "0",
                        "gen": "m",
                        "num": "s",
                        "per": "a"
                    }
                },
                {
                    "dependency_relation": "k2",
                    "head_index": "6",
                    "index": 5,
                    "original_word": "किताब",
                    "pos_tag": "NN",
                    "wx_word": "kiwAba",
                    "morph_info": {
                        "root": "kiwAba",
                        "cat": "n",
                        "case": "d",
                        "gen": "f",
                        "num": "s"
                    }
                },
                {
                    "dependency_relation": "main",
                    "head_index": "0",
                    "index": 6,
                    "original_word": "पढ़ी",
                    "pos_tag": "VM",
                    "wx_word": "paDZI",
                    "morph_info": {
                        "root": "paDZI"
                    }
                },
                {
                    "dependency_relation": "lwg__vaux",
                    "head_index": "6",
                    "index": 7,
                    "original_word": "है",
                    "pos_tag": "VAUX",
                    "wx_word": "hE",
                    "morph_info": {
                        "root": "hE",
                        "cat": "v",
                        "gen": "m",
                        "num": "s",
                        "per": "a",
                        "tam": "hE"
                    }
                },
                {
                    "dependency_relation": "rsym",
                    "head_index": "6",
                    "index": 8,
                    "original_word": "?",
                    "pos_tag": "SYM",
                    "wx_word": "?"
                }
            ],
            "project_id": "1",
            "sentence": "क्या किसी ने यह किताब पढ़ी है ?",
            "sentence_id": "42"
        }
    ]
}
```

> Make sure the JSON files has **only one JSON object**. Do not include multiple root-level JSON blocks.

---

### 3. Run the Tool

Use the following command to run the script:

```bash
python3 main.py
```

---

### 4. View the Output

The output will be saved in a file called `IO/usr_output.json` with a structure like this:

```
<sent_id=41>
#कौन तुम्हें यह काम करने को कह रहा है ?
$kim	1	-	-	7:k1	-	-	-	-
$addressee	2	-	pl	7:k2	-	-	-	-
$wyax	3	-	-	4:nmod__adj	-	proximal	-	-
kAma_1	4	-	-	5:k2	-	-	-	-
kara_1	5	-	pl	7:k2	-	-	-	-
kaha_1-0_raha_hE_1	7	-	-	0:main	-	-	-	-
%interrogative
</sent_id>

<sent_id=42>
#क्या किसी ने यह किताब पढ़ी है ?
$kim	1	-	-	6:adv	-	-	-	-
kisI	2	-	-	6:k1	-	-	-	-
$wyax	4	-	-	5:nmod__adj	-	proximal	-	-
kiwAba_1	5	-	-	6:k2	-	-	-	-
paDZI_1-wA_hE_1	6	-	-	0:main	-	-	-	-
%interrogative
</sent_id>
```

---

## API Usage (Optional)

This tool can also be used through an internal API provided by IIIT-Hyderabad.
API Endpoint: http://10.4.16.167:5008/usr_builder

- Input format (JSON POST):

```json
{
    "sentences": [
        {
            "project_id": "1",
            "sentence_id": "41",
            "sentence": "कौन तुम्हें यह काम करने को कह रहा है ?"
        },
        {
            "project_id": "1",
            "sentence_id": "42",
            "sentence": "क्या किसी ने यह किताब पढ़ी है ?"
        }
    ]
}
```

- Output format:

`````
<sent_id=41>
#कौन तुम्हें यह काम करने को कह रहा है ?
$kim	1	-	-	7:k1	-	-	-	-
$addressee	2	-	pl	7:k2	-	-	-	-
$wyax	3	-	-	4:nmod__adj	-	proximal	-	-
kAma_1	4	-	-	5:k2	-	-	-	-
kara_1	5	-	pl	7:k2	-	-	-	-
kaha_1-0_raha_hE_1	7	-	-	0:main	-	-	-	-
%interrogative
</sent_id>

<sent_id=42>
#क्या किसी ने यह किताब पढ़ी है ?
$kim	1	-	-	6:adv	-	-	-	-
kisI	2	-	-	6:k1	-	-	-	-
$wyax	4	-	-	5:nmod__adj	-	proximal	-	-
kiwAba_1	5	-	-	6:k2	-	-	-	-
paDZI_1-wA_hE_1	6	-	-	0:main	-	-	-	-
%interrogative
</sent_id>
```
> You must be connected to the **IIIT-Hyderabad VPN** to access the API.
