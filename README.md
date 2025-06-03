# IS6400 商业数据分析 | Business Data Analytics

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange.svg)](https://jupyter.org/)

[中文](#中文版本) | [English](#english-version)

---

## 中文版本

### 📋 项目概述

本项目是 IS6400 课程的小组项目，专注于**商业数据分析在金融风控领域的应用**。我们构建了一个综合的机器学习框架，主要解决**贷款违约预测**这一关键的金融风控问题。

**主要项目**：
- **贷款违约预测** - 通过多种机器学习模型识别潜在的违约客户（**最终成品**）

**前期探索**：
- 汽车价格预测 - 前期尝试的项目，后期已放弃，相关代码保留作为学习参考

### 🎯 核心目标

- **风险控制**：提高银行识别违约客户的能力，降低信贷损失
- **模型比较**：评估不同机器学习算法在金融风控场景中的表现
- **业务应用**：为银行信贷审批提供可靠的决策支持工具

### 📊 数据集

- **贷款数据集**：来自 [Kaggle Loan Approval Classification Data](https://www.kaggle.com/datasets/taweilo/loan-approval-classification-data)，包含客户基本信息、信贷历史、财务状况等特征（**主要数据集**）
- **汽车价格数据集**：来自 [Kaggle Car Price Prediction Challenge](https://www.kaggle.com/datasets/deepcontractor/car-price-prediction-challenge)（前期探索，已放弃）

### 🔧 技术栈

- **编程语言**：Python 3.8+
- **机器学习**：Scikit-learn, CatBoost, XGBoost
- **深度学习**：TensorFlow/Keras, BERT
- **数据处理**：Pandas, NumPy
- **可视化**：Matplotlib, Seaborn
- **开发环境**：Jupyter Notebook

### 🚀 实现的模型

#### 1. 传统机器学习模型
- **逻辑回归** (Logistic Regression)
- **K近邻算法** (KNN) 
- **决策树** (Decision Tree)
- **随机森林** (Random Forest)

#### 2. 集成学习模型
- **CatBoost** - 梯度提升算法
- **Stacking** - 多模型堆叠集成
- **Voting** - 投票集成

#### 3. 深度学习模型
- **多层感知机** (MLP/Neural Network)
- **BERT** - 基于Transformer的语言模型

#### 4. 高级分析技术
- **聚类分析** (Clustering Analysis)
- **特征选择** (向前选择/向后消除)

### 📁 项目结构

```
is6400-business-data-analytics/
│
├── data/                           # 数据文件
│   ├── loan_data.csv              # 原始贷款数据
│   ├── cleaned_loan_data.csv      # 清洗后的贷款数据
│   ├── further_cleaned_dataset.csv # 进一步清洗的数据
│   └── car_price_prediction.csv   # 汽车价格数据（前期探索）
│
├── data_cleaning/                  # 数据清洗
│   ├── loan_data_cleaning.ipynb   # 贷款数据清洗
│   └── further_data_cleaning.ipynb # 深度数据清洗
│
├── loan_data_analytics/           # 贷款违约预测模型（核心项目）
│   ├── logistic and cluster.ipynb # 逻辑回归与聚类
│   ├── knn.ipynb                  # K近邻算法
│   ├── decision_tree.ipynb        # 决策树
│   ├── random_forest.ipynb        # 随机森林
│   ├── catboost.ipynb            # CatBoost模型
│   ├── bert.ipynb                # BERT模型
│   ├── stacking.ipynb            # Stacking集成
│   ├── boost_voting.ipynb        # 提升投票算法
│   ├── stacking_results.md       # Stacking结果分析
│   ├── 向前选择和向后消除.md      # 特征选择方法
│   └── image/                    # 结果图像
│
├── data_analytics/                # 早期汽车价格预测探索（已放弃）
│   ├── multi_linear_reg.ipynb    # 多元线性回归
│   ├── mlp.ipynb                 # 多层感知机
│   ├── the_boss_mlp.ipynb        # 优化版MLP
│   ├── catboost.ipynb            # CatBoost回归
│   ├── best_model.h5             # 神经网络模型
│   └── best_catboost_model.cbm   # CatBoost模型
│
├── README.md                      # 项目说明文档
└── LICENSE                       # 开源许可证
```

### 📈 主要成果

#### 贷款违约预测模型性能对比

| 模型 | 准确率 | 召回率(违约) | 精确率(违约) | F1分数 | False Negatives |
|------|--------|-------------|-------------|--------|-----------------|
| **CatBoost** | **94%** | **80%** | **90%** | **0.85** | **394** |
| Random Forest | 93% | 76% | 90% | 0.83 | 477 |
| Decision Tree | 90% | 78% | 77% | 0.77 | 450 |
| KNN | 90% | 72% | 80% | 0.76 | 550 |
| BERT | 93% | 80% | 90% | 0.85 | 394 |

**CatBoost模型表现最佳**：
- ✅ 最高的整体准确率 (94%)
- ✅ 最好的违约客户识别能力 (80% 召回率)
- ✅ 最少的风险遗漏 (394个False Negatives)
- ✅ 高精确率 (90%) 减少误伤优质客户

#### 关键商业价值

1. **风险控制提升**：相比基准模型，CatBoost减少了156个潜在坏账 (550→394)
2. **机会成本优化**：高精确率减少了对优质客户的误判
3. **决策支持**：为银行信贷审批提供可靠的风险评估工具

### 🔬 研究亮点

1. **多模型比较**：系统性比较了从传统统计方法到深度学习的多种算法
2. **集成学习**：通过Stacking技术融合多个模型的优势
3. **特征工程**：实施了向前选择和向后消除等特征选择方法
4. **业务导向**：分析结果紧密结合实际业务场景和决策需求

### 👥 团队成员

本项目由IS6400课程小组协作完成，涵盖数据科学、机器学习和商业分析等多个领域。

### 📄 许可证

本项目采用 MIT 许可证 - 详见 [LICENSE](LICENSE) 文件

---

## English Version

### 📋 Project Overview

This project is a group assignment for the IS6400 course, focusing on **business data analytics applications in financial risk control**. We have built a comprehensive machine learning framework to address the critical business problem of **loan default prediction**.

**Main Project**:
- **Loan Default Prediction** - Identifying potential defaulting customers through various machine learning models (**Final Product**)

**Early Exploration**:
- Car Price Prediction - An early exploration project that was later abandoned, with related code retained for learning reference

### 🎯 Core Objectives

- **Risk Control**: Enhance banks' ability to identify defaulting customers and reduce credit losses
- **Model Comparison**: Evaluate the performance of different machine learning algorithms in financial risk control scenarios
- **Business Application**: Provide reliable decision support tools for bank credit approval

### 📊 Datasets

- **Loan Dataset**: From [Kaggle Loan Approval Classification Data](https://www.kaggle.com/datasets/taweilo/loan-approval-classification-data), contains customer demographics, credit history, financial status, and other features (**Primary Dataset**)
- **Car Price Dataset**: From [Kaggle Car Price Prediction Challenge](https://www.kaggle.com/datasets/deepcontractor/car-price-prediction-challenge) (Early exploration, abandoned)

### 🔧 Tech Stack

- **Programming Language**: Python 3.8+
- **Machine Learning**: Scikit-learn, CatBoost, XGBoost
- **Deep Learning**: TensorFlow/Keras, BERT
- **Data Processing**: Pandas, NumPy
- **Visualization**: Matplotlib, Seaborn
- **Development Environment**: Jupyter Notebook

### 🚀 Implemented Models

#### 1. Traditional Machine Learning Models
- **Logistic Regression**
- **K-Nearest Neighbors (KNN)**
- **Decision Tree**
- **Random Forest**

#### 2. Ensemble Learning Models
- **CatBoost** - Gradient Boosting Algorithm
- **Stacking** - Multi-model Stacking Ensemble
- **Voting** - Voting Ensemble

#### 3. Deep Learning Models
- **Multi-Layer Perceptron (MLP/Neural Network)**
- **BERT** - Transformer-based Language Model

#### 4. Advanced Analytics Techniques
- **Clustering Analysis**
- **Feature Selection** (Forward Selection/Backward Elimination)

### 📈 Key Results

#### Loan Default Prediction Model Performance Comparison

| Model | Accuracy | Recall (Default) | Precision (Default) | F1-Score | False Negatives |
|-------|----------|------------------|---------------------|----------|-----------------|
| **CatBoost** | **94%** | **80%** | **90%** | **0.85** | **394** |
| Random Forest | 93% | 76% | 90% | 0.83 | 477 |
| Decision Tree | 90% | 78% | 77% | 0.77 | 450 |
| KNN | 90% | 72% | 80% | 0.76 | 550 |
| BERT | 93% | 80% | 90% | 0.85 | 394 |

**CatBoost Model Performs Best**:
- ✅ Highest overall accuracy (94%)
- ✅ Best default customer identification capability (80% recall)
- ✅ Fewest risk omissions (394 False Negatives)
- ✅ High precision (90%) reduces misclassification of quality customers

#### Key Business Value

1. **Risk Control Improvement**: CatBoost reduced 156 potential bad loans compared to baseline (550→394)
2. **Opportunity Cost Optimization**: High precision reduces misclassification of quality customers
3. **Decision Support**: Provides reliable risk assessment tools for bank credit approval

### 🔬 Research Highlights

1. **Multi-model Comparison**: Systematic comparison of algorithms from traditional statistics to deep learning
2. **Ensemble Learning**: Leveraging advantages of multiple models through Stacking techniques
3. **Feature Engineering**: Implementation of forward selection and backward elimination methods
4. **Business-Oriented**: Analysis results closely integrated with actual business scenarios and decision needs

### 👥 Team Members

This project is collaboratively completed by the IS6400 course group, covering multiple fields including data science, machine learning, and business analytics.

### 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details

---

### 📞 联系方式 | Contact

如有问题或建议，欢迎提交Issue或Pull Request。
For questions or suggestions, feel free to submit an Issue or Pull Request.

---

**⭐ 如果这个项目对您有帮助，请给我们一个Star！**
**⭐ If this project helps you, please give us a Star!**