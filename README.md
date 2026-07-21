# AI PatternMaker

> 衣服の写真から、採寸・サイズ判定・実在するDXF型紙の参照・型紙生成へ。
>
> From a garment photo to measurement, size recommendation, real DXF pattern reference, and pattern generation.

[デモを見る / View Demo](https://wakai-m-jpg.github.io/AI-PatternMaker/) · [GitHub Repository](https://github.com/wakai-m-jpg/AI-PatternMaker)

---

## 日本語

### 概要

**AI PatternMaker** は、シャツなどの衣服写真から寸法を推定し、サイズ判定、本物のDXF型紙の参照、採寸値に合った型紙生成へ進む将来像を示すプロトタイプです。

現在のバージョンは、想定する一連のユーザー体験と型紙データの表示を検証するためのデモです。写真からの実際のAI採寸やDXFの動的な解析・変形はまだ行っていません。実装済みの範囲と今後の構想を明確に分け、衣服設計のワークフローをAIでどのように支援できるかを提示しています。

### 目指す体験

1. 衣服の前面・背面写真を用意する
2. AIが基準物と衣服の特徴点を検出し、寸法を推定する
3. 推定寸法から最も近いサイズを判定する
4. 条件に合う実在のDXF型紙を選択・参照する
5. 各パーツの縫い合わせ関係を保ちながら型紙を補正・生成する
6. CAD互換データや実寸PDFとして出力する

### 現在実装済みの機能

- 前面／背面のサンプル写真表示と切り替え
- 肩幅、身幅、着丈、袖丈、ヨーク丈、衿回りの採寸候補値表示
- 推奨サイズを提示するサイズ判定デモ
- DXF由来のシャツ型紙をSVGとして表示
- 写真から型紙生成までの5段階フローのデモ
- ブラウザ印刷／PDF保存
- デスクトップとモバイル幅に対応した基本的なレスポンシブUI

### 現在は未実装の機能

このプロトタイプでは、以下の機能はまだ実装されていません。

- 写真に対する実際のAI画像解析、セグメンテーション、特徴点検出
- 写真内の基準物を用いたピクセルから実寸への変換
- 撮影角度、遠近、レンズ歪みを考慮した採寸補正
- 入力寸法に基づく動的なサイズ判定
- 実DXFファイルのアップロード、読込、レイヤー解析
- 寸法差に応じた型紙パーツの変形・グレーディング
- 袖と袖ぐり、衿と衿ぐりなど、縫い合わせ線の整合性検証
- DXF形式での型紙出力
- 1:1実寸PDF、タイル印刷、CADソフトとの互換性保証

現在表示される採寸値、サイズ判定、DXF選択、型紙生成結果は、完成時の体験を説明するためのデモデータおよびデモ動作です。

### CodexとGPT-5.6の活用

本プロジェクトでは、**CodexとGPT-5.6**を共同開発・設計支援に活用しました。

- 5段階の操作フローとUI設計
- 既存コード全体のレビュー
- 実装上の問題点と不足機能の洗い出し
- 採寸値から型紙パーツを補正する生成ロジックの設計支援
- DXF参照、パーツ連動、出力機能に関する技術課題の整理
- OpenAI Build Week 2026応募用READMEの構成・文章改善

AIの提案をそのまま完成機能として扱うのではなく、プロトタイプの実装範囲を確認しながら、人間が目的、優先順位、将来設計を判断する形で使用しています。

### 今後の開発計画

1. **写真入力と前処理** — ユーザー写真のアップロード、前面・背面管理、衣服領域の抽出
2. **基準物検出** — 10×10cm基準物やマーカーを検出し、画像座標を実寸へ変換
3. **採寸精度向上** — 特徴点検出、遠近補正、信頼度表示、手動補正UI、正解データによる評価
4. **DXF解析** — 実DXFの読込、単位・レイヤー・線種・パーツ・ノッチ・地の目の識別
5. **実型紙生成** — 寸法差に基づくパラメトリック変形と、関連パーツの縫い合わせ長の連動補正
6. **CAD互換出力** — DXF、SVG、1:1 PDF、タイルPDFを出力し、主要CADソフトとの互換性を検証

### デモ・リポジトリ

- **デモURL:** https://wakai-m-jpg.github.io/AI-PatternMaker/
- **GitHub:** https://github.com/wakai-m-jpg/AI-PatternMaker

---

## English

### Overview

**AI PatternMaker** is a prototype that presents a future workflow for estimating garment measurements from shirt photos, recommending a size, referencing real DXF sewing patterns, and generating a pattern adapted to the estimated measurements.

The current version is a demonstration of the intended user journey and pattern visualization. It does not yet perform real AI-based photo measurement or dynamic DXF parsing and deformation. By clearly separating implemented features from planned capabilities, the project explores how AI could support the garment-pattern workflow from a photo to production-ready pattern data.

### Envisioned Experience

1. Provide front and back photos of a garment
2. Detect a scale reference and garment landmarks with AI to estimate measurements
3. Recommend the closest size from the estimated measurements
4. Select and reference a suitable real DXF pattern
5. Adjust or generate pattern pieces while preserving sewing-line relationships
6. Export CAD-compatible data or a full-scale PDF

### Currently Implemented

- Front and back sample-photo display and switching
- Candidate measurements for shoulder width, chest width, garment length, sleeve length, yoke length, and neck circumference
- Demonstration of a size recommendation
- SVG visualization of shirt patterns derived from DXF data
- Five-step demonstration flow from photo to pattern generation
- Browser printing and PDF saving
- Basic responsive UI for desktop and mobile widths

### Not Yet Implemented

The following capabilities are not implemented in the current prototype:

- Real AI image analysis, segmentation, or landmark detection
- Pixel-to-real-world conversion using a scale reference in the photo
- Measurement correction for perspective, camera angle, and lens distortion
- Dynamic size recommendation based on entered or detected measurements
- Uploading, parsing, and inspecting layers in real DXF files
- Measurement-driven pattern deformation or grading
- Validation of matching seam lengths, such as sleeve cap to armhole and collar to neckline
- DXF pattern export
- Guaranteed 1:1 PDF output, tiled printing, or compatibility with CAD software

The measurements, size result, DXF selection, and generated-pattern status currently shown are demonstration data and interactions designed to communicate the intended completed experience.

### How We Used Codex and GPT-5.6

We used **Codex and GPT-5.6** as collaborative development and design tools for:

- Designing the UI and five-step user flow
- Reviewing the complete existing codebase
- Identifying implementation issues and missing capabilities
- Supporting the design of measurement-driven pattern-generation logic
- Structuring technical challenges around DXF references, linked pattern pieces, and export
- Improving and restructuring this README for the OpenAI Build Week 2026 submission

AI suggestions were not treated as completed functionality. Human judgment remained responsible for the product goals, priorities, scope verification, and future architecture.

### Development Roadmap

1. **Photo analysis and preprocessing** — User uploads, front/back photo management, and garment-region extraction
2. **Scale-reference detection** — Detect a 10×10 cm reference object or markers and convert image coordinates into real measurements
3. **Measurement accuracy** — Landmark detection, perspective correction, confidence scores, manual adjustment tools, and evaluation against ground truth
4. **DXF parsing** — Read real DXF files and identify units, layers, line types, pattern pieces, notches, and grainlines
5. **Real pattern generation** — Apply parametric transformations based on measurement differences while synchronizing related seam lengths
6. **CAD-compatible export** — Export DXF, SVG, full-scale PDF, and tiled PDF, followed by compatibility testing with major CAD tools

### Demo and Repository

- **Demo:** https://wakai-m-jpg.github.io/AI-PatternMaker/
- **GitHub:** https://github.com/wakai-m-jpg/AI-PatternMaker

---

Built as a prototype for **OpenAI Build Week 2026**.
