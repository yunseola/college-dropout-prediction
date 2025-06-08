# 🎓 대학 중도탈락률 예측 프로젝트

## 🎯 프로젝트 개요
- 수도권, 지방, 전체 대학 데이터를 바탕으로, 중도 탈락률(자퇴·제적 비율)을 예측하는 머신러닝 모델을 개발했습니다.
- 팀원들과 역할을 나누어 수도권/지방/전체 대학 데이터를 분담해 분석했고, 본인은 **수도권 대학 데이터**를 담당하여 모델을 구축했습니다.
- 두 가지 비선형 모델인 **Random Forest**와 **Decision Tree**를 비교 분석하여, 성능이 더 우수한 Random Forest를 최종 채택했습니다.

## 🔧 사용 기술
- Python, pandas, scikit-learn, matplotlib, pdpbox, graphviz
- RandomForestRegressor + GridSearchCV 하이퍼파라미터 튜닝
- DecisionTreeRegressor로 해석 가능한 모델 보조
- Partial Dependence Plot(PDP)을 통한 주요 변수 영향 시각화

## 📈 주요 결과
- 최종 예측 모델: Random Forest (max_depth=9, n_estimators=30, criterion='mae')
- 성능: 평균 절대 오차(MAE) 기준 평가
- 모델별 주요 변수:
  - 수도권 대학: `1prof_std`
  - 지방 대학: `1work_std`
  - 전체 대학: `Fresh_Comp`

## 📁 폴더 구성
- notebooks/01_random_forest_dropout.ipynb : Random Forest 모델 구현
- notebooks/02_decision_tree_dropout.ipynb : 보조 분석용 Decision Tree 모델
- data/수도권.csv : 분석에 사용된 원본 데이터
- img/ : 모델 결과 시각화 (PDP, 변수 중요도 등)
- requirements.txt : 의존성 패키지 목록

## 📊 분석 방식 요약
- 중도탈락률 예측을 위한 회귀 기반 머신러닝 모델 개발
- Random Forest와 Decision Tree 모델을 모두 적용하여 성능 비교
- Validation Curve 및 GridSearchCV로 하이퍼파라미터 튜닝 수행
- 주요 변수에 대한 영향 분석을 위해 PDP 시각화 수행
- Decision Tree 시각화를 통해 해석력 보완

## 📌 참고 사항
- `pdpbox`는 최신 Python 환경에서 오류가 발생할 수 있어 GitHub 포크 버전으로 설치 필요:
  ```text
  pdpbox @ git+https://github.com/SauceCat/PDPbox.git
  ```
- 의사결정트리 시각화를 위해 Graphviz 설치가 필요함: https://graphviz.org/download/

## 📚 결론 요약
- 두 모델 모두 주요 변수들의 영향력을 잘 설명했으며, 예측 성능 측면에서 Random Forest가 더 우수하여 최종 채택
- 수도권 대학은 1prof_std, 지방 대학은 1work_std, 전체 대학은 Fresh_Comp가 가장 중요한 변수로 나타남
- 이러한 인사이트는 각 지역별로 맞춤형 교육 정책 수립에 활용 가능하며, 대학의 중도탈락률 감소를 위한 실질적 전략 수립에 기여할 수 있음

