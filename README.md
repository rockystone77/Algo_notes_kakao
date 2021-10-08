# Algo_notes_kakao

## 신규 아이디 추천

![image](https://user-images.githubusercontent.com/88238335/136479738-505781fd-a220-45dc-94d2-c791c6e80ff9.png)

```Python

import re
def solution1(new_id):
    answer = ""
    #1
    answer = new_id.lower()
    #2
    answer = re.sub(r"[^a-zA-Z0-9-_.]",'', answer)
    #3
    answer = re.sub(r"\.+",".", answer)
    #4
    answer = re.sub(r"^[.]|[.]$", "", answer)
    #5
    answer = "a" if len(answer) == 0 else answer
    #6
    answer = answer[:15]
    answer = re.sub(r"^[.]|[.]$", "", answer)
    #7
    answer = answer + answer[-1] * (3-len(answer)) if len(answer) <= 2 else answer
    return answer


```
