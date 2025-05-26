# Tese: Geração de Dados Sintéticos de Vibração para Aplicações em Agricultura de Precisão

Este repositório contém os arquivos utilizados no desenvolvimento da tese de mestrado, cujo objetivo foi analisar a viabilidade da geração de bases de dados sintéticas com características estatísticas semelhantes a sinais reais de vibração em ramos de cafeeiros, utilizados em processos de derriça mecânica.

## 📁 Estrutura do Repositório
```bash
├── dados/
│   ├── reais/
│   │   ├── medio_15Hz_1.xlsx
│   │   ├── ...
│   └── sinteticos/
│       ├── sint_medio_15Hz_1.csv
│       ├── ...
├── estatisticas/
│   └── estatisticas_reais_com_ar.xlsx
├── resultados_mecanicos/
│   └── resultados_mecanicos_dados_reais.xlsx
│   └── resultados_mecanicos_sinteticos.xlsx
├── laboratório/
│   └── Teste_de_ramos_em_laboratório.xlsx
├── scripts/
│   ├── extrair_estatisticas.py
│   ├── gerar_dados_sinteticos.py
│   ├── analisar_acf_rmse.py
├── graficos/
│   ├── comparacao_acf_real_sintetico.png
│   └── distribuicoes_estatisticas.png
├── tese/
│   └── tese_latex/
│       ├── main.tex
│       └── ...
├── README.md
```

## 📊 Dados

- Os arquivos da pasta `dados/reais/` são compostos por 45 arquivos `.xlsx`, cada um contendo três colunas:
  - `X_Value`: valores de tempo ou amostragem.
  - `Acceleration_0`: sinal de vibração captado na haste 0 (posição média do ramo).
  - `Acceleration_1`: sinal de vibração captado na haste 1 (posição superior do ramo).

- A pasta `dados/sinteticos/` contém 45 arquivos `.csv` gerados artificialmente com base nas estatísticas extraídas dos arquivos reais.

## 📈 Estatísticas

O arquivo `estatisticas/estatisticas_reais_com_ar.xlsx` contém 45 linhas (uma por arquivo real) e 40 colunas com estatísticas descritivas de cada canal (`Acceleration_0` e `Acceleration_1`), incluindo:
- Média, mediana, desvio padrão, variância, RMS, skewness, curtose, quartis, pico, fator de crista (FC), IQR.
- Coeficientes autoregressivos de ordem 1 a 5.

Essas estatísticas foram utilizadas para gerar os dados sintéticos e para comparar sua similaridade com os dados reais.

## 🧪 Scripts

Todos os scripts foram desenvolvidos em Python e estão localizados na pasta `scripts/`:
- `extrair_estatisticas.py`: extrai as estatísticas dos dados reais.
- `gerar_dados_sinteticos.py`: gera séries temporais sintéticas a partir das estatísticas.
- `analisar_acf_rmse.py`: calcula os gráficos de autocorrelação (ACF) e erro quadrático médio (RMSE) para comparação.

## 📄 Tese

A pasta `tese/tese_latex/` contém os arquivos em LaTeX da dissertação, organizados em capítulos. O documento final pode ser gerado compilando `main.tex`.

## 🔧 Requisitos

- Python 3.10+
- Bibliotecas: `pandas`, `numpy`, `matplotlib`, `statsmodels`, `scikit-learn`, `openpyxl`

Instalação rápida com:

```bash
pip install -r requirements.txt
```

## 📚 Objetivo da Pesquisa

A pesquisa investiga se é possível criar uma base de dados sintética de sinais de vibração apenas com base nas estatísticas extraídas dos sinais reais, visando reduzir a necessidade de coletas em campo para testes com sistemas vibratórios em colheitas mecanizadas.

---
