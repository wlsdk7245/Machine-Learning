# 머신 러닝

🔎 더 자세한 정보를 위해서는 [블로그 - 생리주기 예측](https://velog.io/@passengers/%EB%B3%B4%EB%A6%84%EB%8B%AC-2.1-%EB%A8%B8%EC%8B%A0%EB%9F%AC%EB%8B%9D-%EC%83%9D%EB%A6%AC-%EC%A3%BC%EA%B8%B0-%EC%98%88%EC%B8%A1) 또는 [블로그 - 진통제 추천](https://velog.io/@passengers/%EB%B3%B4%EB%A6%84%EB%8B%AC-2.2-%EB%A8%B8%EC%8B%A0%EB%9F%AC%EB%8B%9D-%EC%A7%84%ED%86%B5%EC%A0%9C-%EC%B6%94%EC%B2%9C) 을 확인해주세요!


## 생리주기 예측
### 📍 소개

&nbsp;&nbsp;&nbsp;&nbsp;생리 주기 파악은 여성 건강 관리에 가장 중요한 요소이기 때문에 생리 주기 예측은 보름달 서비스의 핵심이다. 

&nbsp;&nbsp;&nbsp;&nbsp;보름달 서비스는 사용자가 입력한 최근의 주기들을 활용하여 인공지능이 사용자의 생리 주기와 배란일 등의 정보를 예측한다. 사용자가 입력한 정보, 보름달의 예측들이 쌓여갈 수록 사용자는 더 정확한 주기와 배란일 등 자신에게 꼭 필요한 정보를 얻을 수 있게 될 것이다. 

### 📍 데이터셋


![](https://images.velog.io/images/passengers/post/4fb650b1-7244-47df-8c00-0e1cddde22da/image.png)

&nbsp;&nbsp;&nbsp;&nbsp;[공개 데이터 셋](https://epublications.marquette.edu/data_nfp/7/)을 찾았으나, 이 데이터 셋에는 규칙적인 주기를 가진 사람만이 존재해 불규칙한 주기에 대한 데이터를 위해 인위적인 [데이터 셋](https://docs.google.com/spreadsheets/d/1dgA92cMf24v6mVbfLOlIx4PBlI-sbjkncZ-7wOgB7Bk/edit#gid=0)을 만들어 함께 사용하였다. 
공개 데이터셋을 사용하였으나, 규칙적인 주기
&nbsp;&nbsp;&nbsp;&nbsp;Python Jupyter Notebook을 사용하여 ClientID, CycleNumber, LengthofCycle, MeanCycleLength, EstimatedDayofOvulation, LengthofMenses, MeanMensesLength, Age, NumberPregnancies, BMI - 만을 포함한 [cleaned dataset](https://github.com/Passengers-HY/Machine-Learning/blob/master/datasetcleaned.csv)을 만들었다.


### 📍 머신 러닝

![](https://images.velog.io/images/passengers/post/139129a3-de44-461f-88aa-cdb1bd4d0d41/image.png)

&nbsp;&nbsp;&nbsp;&nbsp;Cycle length가 길어질수록 estimated day of ovulation도 길어진다. 배란 예상일이 주기의 길이와 관련이 있다. 
![](https://images.velog.io/images/passengers/post/380c1dfa-82b2-45e5-b014-1c2bd28e62b5/cnn%20algorithm.PNG)

&nbsp;&nbsp;&nbsp;&nbsp;생리 주기는 일정 시간 간격으로 배치된 데이터들의 수열이기 때문에 1D CNN 알고리즘을 사용해 시계열 분석을 사용하였다. 

![](https://images.velog.io/images/passengers/post/0fb0641d-abc5-4b20-9034-0f4a8f033618/image.png)

&nbsp;&nbsp;&nbsp;&nbsp;1D CNN 알고리즘의 사용을 위해서 데이터를 이와 같이 바꾸었다. 

![](https://images.velog.io/images/passengers/post/b270a6e0-0155-4f7a-b3e0-bca379a57de4/lossvaluecycle.PNG)

&nbsp;&nbsp;&nbsp;&nbsp;주기 길이 예측 트레이닝 종료 후 loss 값은은 평균 0.0018이다. 값 예측에 있어 만족할 만한 수치이다.

### 📍
&nbsp;&nbsp;&nbsp;&nbsp;머신러닝을 통해서 우리가 목표했던 결과를 얻을 수 있었다. 보름달 서비스는 사용자가 입력한 정보를 이용하여 사용자의 다음 생리 주기, 배란일을 예측하여 알려준다. 이는 여성 건강 어플에서 가장 핵심이 되는 기능이고, 보름달 서비스에서도 주축이 될 것이다.


## 진통제 추천
### 📍 소개

&nbsp;&nbsp;&nbsp;&nbsp;여성이 월경 중에 겪게 되는 생리통을 가장 간편하게 해소할 수 있는 방법은 진통제 복용이다. 

&nbsp;&nbsp;&nbsp;&nbsp;사용자는 정보 부족 등으로 인해 예전부터 복용하던 약을 습관적으로 선택하지만, 개인별로 증상, 자신의 몸 상태에 따른 적절한 진통제의 복용은 생리통의 완화에 큰 도움이 될 것이다. 

&nbsp;&nbsp;&nbsp;&nbsp;보름달 서비스는 사용자가 모바일 어플리케이션 캘린더 디테일 페이지에 입력한 증상을 활용하여 알맞은 진통제를 추천하는 것을 목표로 한다.

### 📍 데이터셋

![](https://images.velog.io/images/passengers/post/40425e44-9982-4a6c-a922-453ac656ca6a/image.png) [[출처 : 「알고 먹는 약 모르고 먹는 약, 김정환」과 [민트병원 블로그](https://m.blog.naver.com/shamadeo/221358735509)]]

&nbsp;&nbsp;&nbsp;&nbsp;적절한 공개 데이터 셋을 찾을 수 없어 증상, 사용자의 건강 상태와 진통제에 관한 조사 후 1521가지 경우가 있는 인위적인 [데이터셋](https://github.com/Passengers-HY/Machine-Learning/blob/master/ds_pills.csv)을 만들었다.

&nbsp;&nbsp;&nbsp;&nbsp;추천 약의 경우, 인위적인 데이터 셋이기에 Feature Engineering 과정을 거치지 않고 다음의 Pill Number로 나타냈다.


| Pill Number | 추천 약 |
|---| --- |
| 1 | 스피드펜 나노, 자이날, 이지엔 |
| 2 | 이지엔6 이브 |
| 3 | 그날엔 |
| 4 | 이즈펜 |
| 5 | 우먼스 타이레놀 |
| 6 | 이지엔6 이브, 이브큐 레이디 |
| 7 | 싸이베린 |
| 8 | 게보린, 펜잘큐, 사리돈 에이 |
| 9 | 탁센 |
| 10 | 부스코판 플러스  |
| 11 | 그날엔 Q |
| 12 | 자이날 |


### 📍 머신 러닝

&nbsp;&nbsp;&nbsp;&nbsp;14개의 특성을 이용해 12개의 Pill Number를 예측하기 위하여 다중 클래스 알고리즘을 사용하였다. 

&nbsp;&nbsp;&nbsp;&nbsp;또한 1부터 12까지의 정수로 표현된 Pill Number를 0부터 11까지의 라벨을 이용하여 원 핫 인토딩을 수행하였다. 
![](https://images.velog.io/images/passengers/post/e134136c-d75e-4fc3-9808-534ebb0e1933/a.jpg)

&nbsp;&nbsp;&nbsp;&nbsp;위의 그래프는 tensorflow를 이용해 다중 클래스 분류 모델을 트레이닝 성능을 보여준다. 

&nbsp;&nbsp;&nbsp;&nbsp;400 epochs와 32의 batch size를 사용했을 때, 트레이닝과 테스트 모두에서 0.03의 loss value를 기록했다.

### 📍 

&nbsp;&nbsp;&nbsp;&nbsp;머신러닝을 통해 보름달은 사용자가 입력한 정보를 이용하여 사용자별 진통제를 추천해줄 수 있다. 사용자는 자신에게 맞는 약을 복용함으로써 더 빠르고 정확한 효과를 기대할 수 있다. 빠진 정보가 있다면 NUGU Speaker의 slot filling 기능을 통해 얻을 수 있다.


🔎 더 자세한 정보를 위해서는 [블로그 - 생리주기 예측](https://velog.io/@passengers/%EB%B3%B4%EB%A6%84%EB%8B%AC-2.1-%EB%A8%B8%EC%8B%A0%EB%9F%AC%EB%8B%9D-%EC%83%9D%EB%A6%AC-%EC%A3%BC%EA%B8%B0-%EC%98%88%EC%B8%A1) 또는 [블로그 - 진통제 추천](https://velog.io/@passengers/%EB%B3%B4%EB%A6%84%EB%8B%AC-2.2-%EB%A8%B8%EC%8B%A0%EB%9F%AC%EB%8B%9D-%EC%A7%84%ED%86%B5%EC%A0%9C-%EC%B6%94%EC%B2%9C) 을 확인해주세요!
