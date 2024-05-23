## 개발목적 및 목표


1. 언어 감수성이란?
    - 듣는 사람의 상황과 감정을 고려하여 언어를 사용하는 능력
    - 일상생활에서 의도치 않게 차별적 의미, 혹은 고정관념이 내포되어 있는 단어 표현 사용
        
        (ex. 경로를 알 수 없는 환자 = 깜깜이, 팔이 반인 티셔츠 = 반팔티)
        
2. 언어 감수성의 중요도
    - 언어 감수성이 연도별로 언급되는 양 분석한 결과, 매년 꾸준히 증가
    - 실제 기업에서도 이러한 사회적 분위기 반영
        
        (ex. 쿠팡맨 → 쿠팡친구, 야쿠르트 아줌마 → 프레시 매니저)
        
3. 개발 목적
    - 공공기관이나 기업, 공적인 자리에서 발표 시 누군가를 차별하는 내용이 포함된 표현을 사용하지는 않는 지 사전에 검토하여 사회적 호감도 상승 및 언어 사용에 대한 사람들의 인식 개선을 목표로 함
    - 또한, 여러 분야에서 사용되는 대화형 인공지능 서비스 ChatGPT의 언어 사용은 영향력에 비해 사회적 흐름 따라가지 못함 발견, ChatGPT의 답변을 언어 감수성 보완한 형태로 출력하여 서비스의 답변을 무비판적으로 사용하는 경우 대비
4. 개발 형태
    1. 언어 감수성 분석 모델
        
        맞춤법 교정기와 유사한 형태이나 언어 감수성 키워드 접목시킴
        
        흐름: 사용자가 문장 입력 → 언어 감수성 분석 → 권장 표현으로 수정하여 출력
        
    2. ChatGPT의 언어 감수성 교정 웹
        
        ChatGPT의 API와 (a)에서 개발한 언어 감수성 분석 모델을 연결함
        
        흐름: 사용자가 질문 입력 → ChatGPT가 답변 → 언어 감수성 분석 → 권장 표현으로 답변 수정하여 출력
        

## 최종 결과물


1. 언어 감수성 사전 구축
- 20여개의 논문 및 자료 조사를 통해 언어 감수성 낮은 단어 선별
- 논문에서 요청한 것을 바탕으로 대안어 채택
- 표준국어대사전 바탕으로 낮잡아 부르거나 속된 말인 경우, 대안어 임의로 제시하면 화자의 의도와 다르게 해석될 수 있으므로 대안어 제시 기준 설정
1. 언어 감수성 분석 모델
- 입력 문장의 감성 분석 통해 긍정, 부정 판단
- 언어 감수성의 낮음 여부 판단
- 언어 감수성이 낮음으로 판단될 경우, 사전의 카테고리 분류 및 대안어 검색하여 출력

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/b35b95c5-6342-462a-8b50-2349f1b244ea/8e1bdd46-46e7-4e1c-a144-f05ce0a81ad1/Untitled.png)

1. ChatGPT API 적용한 웹 구현
- ChatGPT API와 언어 감수성 분석 모델을 웹에 적용
