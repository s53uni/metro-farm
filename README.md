<a name="top"></a>
  
# 부산 지하철 유휴공간 스마트팜 입지 분석
🏆 부산 빅데이터 분석 해커톤 대상 수상 🏆
- 구분: 팀 프로젝트
- 기간: 2024년 7월 1일 ~ 2024년 7월 10일

<details>
  <summary>Table of Contents</summary>
  
  1. [프로젝트 개요](#프로젝트-개요)
      + [주제 선정 배경](#주제-선정-배경)
      + [지하철 스마트팜 인지도](#지하철-스마트팜-인지도)
      + [타겟 선정 이유](#타겟-선정-이유)
  2. [데이터 정의](#데이터-정의)
  3. [프로젝트 과정](#프로젝트-과정)
      + [데이터 전처리](#데이터-전처리)
      + [탐색적 데이터 분석](#탐색적-데이터-분석)
      + [자치구 군집 분석](#자치구-군집-분석)
      + [지하철역 군집 분석](#지하철역-군집-분석)
  4. [결론](#결론)
     + [분석 결과](#분석-결과)
     + [서비스 제안](#서비스-제안)

</details>
<br>

## 프로젝트 개요
### 주제 선정 배경
부산시는 인구 감소, 산업 쇠퇴, 도심 내 유휴공간 증가 등 여러 문제에 직면해 있으며, 특히 지하철역 내 방치된 유휴공간이 경제적 비효율을 초래하고 있는 상황이다. 
이를 해결하고 부산교통공사의 재정 자립을 돕기 위해, 본 프로젝트에서는 지하철 유휴공간을 활용한 스마트팜 서비스 '키아라'의 도입을 제안한다.<br>

서울특별시의 '메트로팜' 사례를 보면, 기존 구조물을 재활용하여 설치 비용을 절감하고, 작물 판매 및 체험 방문을 통해 약 7,500만 원의 수익을 창출한 바 있다. 
광주광역시 역시 시민들이 농산물을 재배하고 휴식을 취할 수 있는 복합문화공간 형태의 스마트팜을 조성하였고, 역내 무인 판매기를 통해 작물을 판매하고 있다.<br>

부산광역시는 부산 사회적 경제 지원 기금(BEF)을 활용해 지하철 역사 내 스마트팜 '팜올치'를 거제해맞이역과 국제금융센터역 두 곳에 조성 중이다. 
그러나 팜올치는 소비자 접근이 어려운 위치에 있으며, 서비스에 대한 인지도도 낮은 편이다.<br>

본 프로젝트는 스마트팜 서비스의 타겟층을 건강과 식물 재배에 관심이 많은 청년층으로 설정하고, 이들이 주로 이용하는 지역과 접근성을 고려해 최적의 입지를 선정한다.
이를 통해 지하철 유휴공간 스마트팜 서비스의 인지도와 사용자 친밀감을 높여, '팜올치'를 비롯한 스마트팜 서비스의 지속 가능한 생태계 조성에 기여하고자 한다.

<br>

### 지하철 스마트팜 인지도
![지하철 스마트팜 인지도](https://github.com/user-attachments/assets/fb560b0e-f145-45b8-87ec-5a9aded6b613)
네이버 키워드 도구를 활용한 분석 결과, 스마트팜 및 서울시의 '메트로팜'과의 검색량을 비교했을 때, 부산시의 지하철 스마트팜에 대한 인지도가 상대적으로 낮은 것으로 나타났다. 

<br>

### 타겟 선정 이유
한국보건산업진흥원의 'MZ세대 건강관리 트렌드(2022)'에 따르면, 국내 건강관리 시장은 "건강을 중시하는 MZ세대"를 중심으로 빠르게 성장하고 있으며, 이들 사이에서는 "헬시플레저" 트렌드가 급부상하고 있다. 
MZ세대는 맛과 건강을 모두 챙기는 음식을 선호하며, 웨어러블 기기를 활용해 운동을 즐기는 등 적극적인 건강관리 활동을 실천하고 있다. 
이러한 이유로, 스마트팜 서비스의 주요 타겟층을 건강과 식물 재배에 관심이 많은 청년층으로 선정하게 되었다.

<p align="right"><a href="#top">⬆️TOP</a></p>

## 데이터 정의
#### 자치구 군집 분석 데이터
- 통계청 인구총조사(2022)
- 행정안전부 주민등록 인구 및 세대현황(2024.06)
- 부산광역시 부산시공공 주민등록인구 통계정보 서비스(2023.09)
- 부산광역시 주민등록 인구통계(2024.04)
- 부산광역시 사업체 조사(2022)
- 부산광역시 녹지 현황(2018)

#### 지하철역 군집 분석 데이터
- 부산교통공사 시간대별 승하차인원(2024.01)
- 부산교통공사 도시철도 임대시설물 현황(2023)
- 지역정보개발원 부산광역시 지방행정인허가공개데이터(2023.09)

<br>

## 프로젝트 과정
### 데이터 전처리
#### 자치구 군집 분석 데이터
1. 총 인구수를 인구 밀도로 나누어 자치구 면적 컬럼 생성
2. 자치구별 인구수를 총 인구수로 나누어 인구 비율 컬럼 생성
3. 군집 분석에 필요한 컬럼만 추출하여 병합

#### 지하철역 군집 분석 데이터
1. 부산광역시에 속하지 않는 지역의 지하철역 제거
2. 역명이 두 개씩 표기된 이상치 데이터 제거
3. 지하철역별 승하차 인원을 합산한 후, 일 평균 승차 인원과 하차 인원 컬럼 생성
4. 환승역 데이터가 중복된 것을 확인하여, 하나만 남기고 삭제
5. 지하철역별 유휴공간의 면적과 개수를 합산하여 컬럼을 생성
6. 군집 분석에 필요한 컬럼만 추출하여 병합

<p align="right"><a href="#top">⬆️TOP</a></p>

### 탐색적 데이터 분석
분석에 사용되는 변수가 매우 많아, 시각화를 통해 1차적으로 변수를 선정했다.

#### 자치구별 가구 수 시각화
![구별가구수히트맵](https://github.com/user-attachments/assets/16fab14c-e9ee-407c-9554-10d50243dcc1)
- 5인 세대 이상의 비중이 다른 세대에 비해 적음을 확인함
- 1인 세대부터 4인 세대까지의 분포만으로도 충분히 의미가 있다고 판단함

<br>

#### 자치구별 연령대 시각화
![구별나이대히트맵](https://github.com/user-attachments/assets/be552fb8-1864-4ac7-853d-8cc6455a6c89)
- 20대부터 60대까지의 비중이 높다는 점을 확인함

<br>

#### 자치구별 산업체수 시각화
![구별산업체수히트맵](https://github.com/user-attachments/assets/fc7ac820-8d69-4549-93d5-8f122403a4cd)
- 도매 및 소매업, 숙박 및 음식점업, 운수 및 창고업의 비중이 높다는 점을 확인하여 변수로 선정함
- 강서구와 사상구에서는 제조업의 비중이 높지만, 스마트팜과의 연관성이 낮다고 판단하여 변수로 사용하지 않음

<p align="right"><a href="#top">⬆️TOP</a></p>

### 자치구 군집 분석
자치구에 대한 군집 분석을 먼저 시행하는 이유는 자치구에 관한 데이터가 지하철역에 비해 많기 때문에 자치구별 특성을 하나의 가중치 변수로 축약하여 모델에 반영하기 위함이다. 
도출된 군집 중, 스마트팜 서비스를 적극적으로 이용할 가능성이 높은 군집에 더 높은 점수를 부여해 이를 가중치로 변환하였다.

#### 순차 특성 선택법
탐색적 데이터 분석으로 1차적으로 변수를 선정한 후, 순차 특성 선택법을 통해 중요한 변수를 한 번 더 선정했다.

|  | 전진 선택법 | 후진 제거법 |
| ----------------- | ----------------- | ----------------- |
| 선정된 변수       | 자치구 면적<br>3인세대<br>4인세대<br>숙박 및 음식점업<br>보건업 및 사회복지 서비스업<br>도매 및 소매업<br>50대<br>인구 비율<br>녹지개소 | 자치구 면적<br>1인세대<br>2인세대<br>숙박 및 음식점업<br>보건업 및 사회복지 서비스업<br>도매 및 소매업<br>20대<br>총인구수<br>인구 비율<br>녹지개소 |
| 실루엣 계수       | 0.45 | **0.54** |


- 후진 제거법의 실루엣 계수가 더 높게 나와 최종적으로 후진 제거법에서 선정된 변수를 자치구 군집 분석에 사용하기로 결정함
- 또한, 후진 제거법으로 선정된 변수들이 타겟층과 더 밀접하게 관련이 있다고 판단함

<br>

#### K-means 군집 분석
최적의 클러스터 수를 찾기 위해 엘보우 기법(Elbow Method)을 사용했다.
![자치구군집분석](https://github.com/user-attachments/assets/f0ce399f-0a6c-40d9-b790-b1f9d66976e3)
- 엘보우 기법 결과, 그래프의 기울기가 완만해지기 시작하는 지점인 K=3이 최적의 값임을 확인
- 군집의 수를 3으로 설정하여 분류한 결과, 중심점을 기준으로 유사한 특성을 가진 지역들이 잘 군집됨
- 이 군집 분석의 실루엣 계수는 0.57으로 나타남

<br>

군집별 자치구는 다음과 같다.
| 군집 | 자치구 |
| ------ | ------ |
| 0 | 사하구, 연제구, 금정구, 동래구, 사상구, 남구, 수영구, 북구 |
| 1 | 부산진구, 해운대구 |
| 2 | 중구, 서구, 동구, 강서구, 기장군 |

<br>

#### 자치구 가중치 부여

|  | 0 | 1 | 2 |
| ------ | ------ | ------ | ------ |
| 숙박 및 음식점 비율 낮은 순 | 2 | 1 | 3 |
| 보건업 및 복지 비율 높은 순 | 2 | 3 | 1 |
| 20대 인구 수 높은 순 | 2 | 3 | 1 |
| 녹지 개소 적은 순 | 2 | 3 | 1 |
| 인구 비율 높은 순 | 2 | 3 | 1 |
| 합계 | 10 | 13 | 7 |
| 자치구 가중치 | 0.5 | 1.0 | 0.0 |

- 스마트팜 서비스에 대한 수요가 예상되는 항목을 선정하여 군집의 중앙값을 기준으로 각 항목에 점수를 부여하고, Min-Max Scaling을 통해 가중치로 변환함

<p align="right"><a href="#top">⬆️TOP</a></p>

### 지하철역 군집 분석
지하철역 데이터에 자치구 가중치와 대학 수, 원예 관련 학과 수, 체력단련장 수 컬럼을 추가하여 군집 분석을 진행했다. 
대학 수를 추가한 이유는 서비스 타겟층인 청년층을 고려했기 때문이다. 원예 관련 학과가 있는 경우 스마트팜에 대한 관심과 이용 가능성이 높다고 판단하였다. 
체력단련장 수는 건강에 관심이 있는 사람들이 건강한 먹거리에 대한 관심이 높을 것으로 예상하여 포함했다. <br>

이 변수들은 행정동 단위로 세분화된 데이터여서 자치구 군집 분석에서 분리하여 지하철역 군집 분석에 활용했다.

#### K-means 군집 분석
마찬가지로 최적의 클러스터 수를 찾기 위해 엘보우 기법을 사용했다.
![지하철역군집분석](https://github.com/user-attachments/assets/b6843588-77eb-46f5-9e6d-d52a01882f04)
- 엘보우 기법 결과, 그래프의 기울기가 완만해지기 시작하는 지점인 K=9이 최적의 값임을 확인
- 군집의 수를 9로 설정하여 분석한 결과, 중심점을 기준으로 유사한 특성을 가진 지하철역들이 각 군집으로 분류됨
- 이 군집 분석의 실루엣 계수는 0.33으로 나타남

<br>

지하철역 군집 분석 결과와 해당 군집의 특성은 다음과 같다.
| 군집 | 역명 | 특징 |
| ------ | ------ | ------ |
| 0 | 괴정, 구남, 구서, 국제금융센터부산은행, 낫개, 당리, 덕포, 동대신, 동매, 동원, 명륜, 모라, 문현, 민락, 범어사, 부산진, 시청, 신장림, 장림, 초량, 토성, 화명 | 주거 밀집 지역 |
| 1 | 개금, 동의대, 반여농산물시장, 범내골, 벡스코, 부암, 부전, 석대, 센텀시티, 양정, 영산대, 장산, 중동, 해운대 | 상업 및 교육 지역 |
| 2 | 서면 | 주요 상업 중심지 |
| 3 | 강서구청, 구포, 금사, 낙민, 대저, 만덕, 명장, 배산, 사직, 서동, 수안, 안평, 충렬사 | 주거 및 농업 지역 |
| 4 | 부산대, 장전, 하단 | 대학가 및 학생 중심 지역 |
| 5 | 광안, 금련산, 남포, 범일, 부산, 사상, 신평, 온천장, 자갈치, 중앙 | 상업 및 관광 중심지 |
| 6 | 거제, 경성대부경대, 교대, 남산, 냉정, 대연, 못골, 종합운동장, 주례 | 주거 및 교육 지역 |
| 7 | 전포, 수영 | 상업 중심지 |
| 8 | 덕천, 동래, 미남, 연산 | 주거 및 상업 지역 |

<br>

#### 최종 입지 선정
마찬가지로 스마트팜 서비스에 대한 수요가 예상되는 항목을 선정하여 군집의 중앙값을 기준으로 각 항목에 점수를 부여했다. 

|                    | 0  | 1  | 2  | 3  | 4  | 5  | 6  | 7  | 8  |
|------------------------|----|----|----|----|----|----|----|----|----|
| 승하차 인원수 많은 순  | 2  | 4  | 9  | 1  | 7  | 6  | 3  | 5  | 8  |
| 체력단련장 수 많은 순  | 3  | 8  | 9  | 4  | 4  | 1  | 2  | 7  | 6  |
| 대학 수 많은 순        | 1  | 1  | 1  | 1  | 9  | 1  | 9  | 1  | 1  |
| 원예관련학과 수 많은 순 | 1  | 1  | 1  | 1  | 9  | 1  | 1  | 1  | 1  |
| 유휴공간 수 많은 순    | 3  | 4  | 6  | 1  | 5  | 8  | 1  | 9  | 7  |
| 유휴공간 면적 넓은 순  | 3  | 4  | 9  | 1  | 5  | 7  | 2  | 8  | 6  |
| 자치구 가중치 높은 순  | 1  | 9  | 9  | 1  | 1  | 1  | 1  | 5  | 1  |
| **합계**               | 14 | 31 | **44** | 10 | **40** | 25 | 19 | **36** | 30 |

합계 점수가 상위인 3개의 군집, 2, 4, 7을 최종 입지로 선정했다.

- 1위 군집인 군집 2는 **서면역**으로 부산의 대표적인 상업 중심지이다. 유동 인구가 많아 스마트팜에서 생산된 신선한 농산물을 바로 판매할 수 있으며, 스마트팜이 도시농업의 모범 사례로 상업 중심지에서 많은 사람들에게 노출되어 홍보 효과를 누릴 수 있다.
- 2위 군집인 군집 4는 **부산대, 장전, 하단역**으로 대학가 및 학생 중심 지역이다. 특히 부산대는 식물생명과학과, 원예생명공학과가 있고 동아대는 생명지원산업학과가 있어 관련 학과 재학생들의 이용이 기대된다.
- 3위 군집인 군집 7은 **전포, 수영역**으로 서면역과 같은 상업 중심지이다. 마찬가지로 유동 인구가 많아 스마트팜의 농산물 판매나 스마트팜 홍보에 유리한 위치이다.

<p align="right"><a href="#top">⬆️TOP</a></p>

## 결론
### 분석 결과
이 분석은 부산광역시의 자치구 및 지하철역 데이터를 활용하여 스마트팜 서비스의 최적 입지를 선정하는 과정으로, 
자치구와 지하철역의 군집 분석을 통해 각각의 특성을 파악한 후, 스마트팜 서비스에 대한 잠재적 수요를 평가하였다.<br>

분석 결과, 부산의 상업 중심지인 서면역이 최적의 입지로 선정되었으며, 대학가 및 학생 중심 지역인 부산대, 장전, 하단역, 그리고 또 다른 상업 중심지인 전포, 수영역이 뒤를 이었다. 
이 지하철역들은 높은 유동 인구, 청년층 밀집, 유휴공간 등의 요소를 고려할 때, 스마트팜 서비스가 성공적으로 정착하고 인지도를 높이기에 적합한 지역으로 판단된다.

<br>

### 서비스 제안
부산시의 기존 지하철 스마트팜은 주로 '판매'와 '어린이 체험'에 초점을 맞추고 있는 반면, 
본 프로젝트에서 제안하는 지하철 스마트팜 앱서비스 '키아라'는 청년층을 주요 대상으로 하여 '취미 생활과 건강'에 중점을 둔 차별화된 서비스를 제공하고자 한다.<br>

'키아라'를 통해 사용자는 원하는 지하철역을 선택하고, 재배하고 싶은 작물을 골라 원격으로 작물의 성장 과정을 모니터링할 수 있다. 
수확 시기가 되면 직접 수확 체험을 하거나, 수령 예약 후 지하철역에서 편리하게 작물을 받아볼 수 있다. 
이 서비스는 대학가나 상업 중심지 등 다양한 장소에 배치되어 사용자들에게 다채롭고 즐거운 작물 재배 경험을 제공한다.<br>

이와 같은 서비스는 지하철의 유휴 공간을 효율적으로 활용하는 동시에, 지하철 스마트팜 서비스의 인지도를 높이고 지역 경제 활성화와 도시농업 발전에 기여할 것으로 기대된다.<br>

#### 서비스 주요 기능
![키아라](https://github.com/user-attachments/assets/2f13f371-beee-4640-9d5e-02d0ec4a173b)

<p align="right"><a href="#top">⬆️TOP</a></p>
