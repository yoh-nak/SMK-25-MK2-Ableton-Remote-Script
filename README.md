# M-VAVE SMK-25 MK2 Ableton Live Blue Hand 16 Parameter Remote Script

[日本語](#日本語) | [English](#english)

---

# 日本語

M-VAVE **SMK-25 MK2** で、Ableton Live の **Blue Hand / Device Control を最大16パラメーター**操作するための User Remote Script です。

USB接続用とBluetooth接続用の2種類を用意しています。

## Download

- `SMK25_MK2_BlueHand_USB_16.zip` — USB接続用
- `SMK25_MK2_BlueHand_BT_16.zip` — Bluetooth接続用

使用する接続方式に合ったZIPをダウンロードしてください。

---

## 仕様

Blue Hand / Device Control 用として、以下の16個のCCを使用します。

| Parameter | CC | MIDI Ch. |
|---:|---:|---:|
| 1 | 20 | 1 |
| 2 | 21 | 1 |
| 3 | 22 | 1 |
| 4 | 23 | 1 |
| 5 | 24 | 1 |
| 6 | 25 | 1 |
| 7 | 26 | 1 |
| 8 | 27 | 1 |
| 9 | 28 | 1 |
| 10 | 29 | 1 |
| 11 | 30 | 1 |
| 12 | 31 | 1 |
| 13 | 32 | 1 |
| 14 | 33 | 1 |
| 15 | 34 | 1 |
| 16 | 35 | 1 |

- MIDI Channel: **1**
- Encoder Map Mode: **Absolute**
- Parameter 1〜8: **CC20〜27**
- Parameter 9〜16: **CC28〜35**
- Mixer / Transport / Pads: **無効**
- Bankボタン機能: **このスクリプトには含まれません**

8個の物理ノブを2バンクで使用する場合は、SMK-25 MK2側で次のように設定してください。

- 第1バンク: **CC20〜27**
- 第2バンク: **CC28〜35**

---

# Bluetooth版を使う前の準備

Bluetooth版では、Remote ScriptをAbleton Liveへ入れるだけでなく、**M-VAVE公式のソフトウェアを別途インストール**してください。

このプロジェクトでは、SMK-25 MK2のプリセット作成・編集に **`MidiSuite (new)` を推奨**します。今回のCC20〜35を使うプリセットも、新しい `MidiSuite (new)` を使って作成しています。

WindowsでBluetooth接続する場合は、あわせてM-VAVE公式の **`Sinco Connector`** を使用します。

## 必要なM-VAVE公式ソフト

| Software | 用途 | 推奨 |
|---|---|---|
| **MidiSuite (new)** | SMK-25 MK2のプリセット編集、ノブのCC設定、本体への保存 | **推奨 / 使用** |
| **Sinco Connector** | Windows 10 / 11でSMK-25 MK2をBluetooth MIDI接続 | **Bluetooth接続時に使用** |

## メーカー公式サイトからダウンロード

以下のソフトは、このGitHubリポジトリには含まれていません。**M-VAVEメーカー公式サイトからダウンロードしてください。**

**M-VAVE App Download**

https://www.m-vave.com/appdownload

**M-VAVE Download**

https://www.m-vave.com/download

**SMK25-II 製品ページ**

https://www.m-vave.com/product

メーカーサイトで次の名前を探してください。

```text
MidiSuite (new)
Sinco Connector
```

- `MidiSuite (new)` はSMK-25 MK2のプリセット編集に使用します。
- `Sinco Connector` はWindowsでBluetooth MIDI接続するために使用します。
- 旧 `MidiSuite V1.3.7` も掲載されていますが、このREADMEでは **MidiSuite (new) を推奨**します。

> **重要:** Remote Script、MidiSuite、Sinco Connectorは別のものです。このリポジトリから入手するのはAbleton Live用Remote Scriptです。SMK-25 MK2本体のプリセット編集には `MidiSuite (new)`、WindowsでのBluetooth MIDI接続には `Sinco Connector` をM-VAVE公式サイトから別途入手してください。

---

## WindowsでBluetooth接続する場合

1. M-VAVEメーカー公式サイトから **MidiSuite (new)** と **Sinco Connector** をダウンロード
2. `MidiSuite (new)` を使ってSMK-25 MK2のプリセット / CC設定を行い、本体へ保存
3. SMK-25 MK2のBluetoothを有効にする
4. **Sinco Connector** からSMK-25 MK2を接続
5. Windows上にSMK25IIのBluetooth MIDIポートが作成されていることを確認
6. Ableton Liveを起動
7. `Settings / Preferences → Link, Tempo & MIDI` を開く
8. Bluetooth版Remote Scriptと、通常MIDI / CC側のBluetoothポートを選択する

確認できた環境では、ポートは次のように分かれています。

```text
SMK25II-Bt-MIDI   ← Blue Hand / CC操作に使用
SMK25II-Bt-DAW    ← DAW / Mackie側
```

このRemote Scriptでは **`SMK25II-Bt-MIDI` 側**を使用します。

```text
Control Surface : SMK25_MK2_BlueHand_BT_16
Input           : SMK25II-Bt-MIDI
Output          : SMK25II-Bt-MIDI または None
```

ポート名は環境によって異なる場合があります。その場合は、SMK-25 MK2から送った **CC20〜35が届く通常MIDI / CC側ポート**を選択してください。

---

## SMK-25 MK2のプリセットを設定する

このRemote Scriptは、SMK-25 MK2から次のCCが送られる前提です。

```text
MIDI Channel 1

Bank / Set 1
CC20
CC21
CC22
CC23
CC24
CC25
CC26
CC27

Bank / Set 2
CC28
CC29
CC30
CC31
CC32
CC33
CC34
CC35
```

SMK-25 MK2の現在のプリセットがこのCC配置になっていない場合は、**M-VAVE公式の `MidiSuite (new)` でプリセットを編集**してください。このプロジェクトでは新しいMidiSuiteを推奨します。

### 推奨するノブ設定

| Physical control | Bank 1 | Bank 2 |
|---|---:|---:|
| Knob 1 | CC20 | CC28 |
| Knob 2 | CC21 | CC29 |
| Knob 3 | CC22 | CC30 |
| Knob 4 | CC23 | CC31 |
| Knob 5 | CC24 | CC32 |
| Knob 6 | CC25 | CC33 |
| Knob 7 | CC26 | CC34 |
| Knob 8 | CC27 | CC35 |

共通設定:

```text
MIDI Channel : 1
Encoder Mode : Absolute
```

設定後は、MidiSuite側で設定をSMK-25 MK2本体へ保存 / Writeしてください。

---

## Bluetooth版のセットアップ順序

```text
1. M-VAVE公式サイトからMidiSuite (new)とSinco Connectorを取得
        ↓
2. MidiSuite (new)でSMK-25 MK2のノブCCを設定
        ↓
3. 設定を本体プリセットへ保存
        ↓
4. WindowsならSinco ConnectorでBluetooth MIDI接続
        ↓
5. Bluetooth版Remote ScriptをUser Remote Scriptsへ配置
        ↓
6. Ableton Liveを起動
        ↓
7. Control SurfaceをSMK25_MK2_BlueHand_BT_16に設定
        ↓
8. InputをSMK25II-Bt-MIDI側に設定
        ↓
9. Ableton Liveでデバイスを選択
        ↓
10. Blue HandでParameter 1〜16を操作
```

---

# インストール

## 1. ZIPを展開する

### USB版

```text
SMK25_MK2_BlueHand_USB_16/
├─ README.md
└─ UserConfiguration.txt
```

### Bluetooth版

```text
SMK25_MK2_BlueHand_BT_16/
├─ README.md
└─ UserConfiguration.txt
```

## 2. Ableton Liveを終了する

Ableton Liveを完全に終了してから、展開したフォルダを配置してください。

## 3. User Remote Scripts フォルダへ配置する

確認できた構成では、次の場所へフォルダごと配置します。

```text
...\Live 12.3.2\Preferences\User Remote Scripts\
```

USB版:

```text
...\Live 12.3.2\Preferences\User Remote Scripts\
└─ SMK25_MK2_BlueHand_USB_16\
   ├─ README.md
   └─ UserConfiguration.txt
```

Bluetooth版:

```text
...\Live 12.3.2\Preferences\User Remote Scripts\
└─ SMK25_MK2_BlueHand_BT_16\
   ├─ README.md
   └─ UserConfiguration.txt
```

## 4. Ableton Liveを起動する

Liveを起動し、

**Preferences / Settings → Link, Tempo & MIDI**

を開きます。

---

# USB接続の設定

```text
Control Surface : SMK25_MK2_BlueHand_USB_16
Input           : USBの通常CCポート
Output          : 同じUSBポート、またはNone
```

元の動作版で使用していたUSBポート名:

```text
SMK25II MIDI 2
```

環境によって表示名が異なる場合は、**CC20〜35が届いているUSB MIDIポート**を選択してください。

---

# Bluetooth接続の設定

```text
Control Surface : SMK25_MK2_BlueHand_BT_16
Input           : Bluetoothの通常MIDI / CCポート
Output          : 同じBluetooth MIDIポート、またはNone
```

確認できた環境:

```text
SMK25II-Bt-MIDI   ← Blue Hand用
SMK25II-Bt-DAW    ← DAW / Mackie側
```

Blue Hand用には通常、

```text
SMK25II-Bt-MIDI
```

を使用します。

`SMK25II-Bt-DAW` はBlue Hand用には使用しません。

---

# Blue Hand の使い方

設定後、Ableton Liveでデバイスを選択すると、Blue Handの対象になっているパラメーターをSMK-25 MK2のCCで操作できます。

```text
CC20〜27 → Parameter 1〜8
CC28〜35 → Parameter 9〜16
```

8ノブを2バンクで使う場合は、SMK-25 MK2側のプリセット / バンク切り替えによって、送信CCを20〜27と28〜35に切り替えてください。

---

# CC番号を変更したい場合

`UserConfiguration.txt` 内の

```text
Encoder1
～
Encoder16
```

を、SMK-25 MK2から実際に送信するCC番号に合わせて変更できます。

---

# このスクリプトに含まれない機能

- BankボタンによるLive側の自動ページ切り替え
- Mixerコントロール
- Transportコントロール
- Padコントロール
- Mackie Control機能

この版は、**16個のDevice Control CCを直接Blue Handへ渡すシンプルな構成**です。

---

# Troubleshooting

## Control Surface に表示されない

- ZIPのまま配置せず、必ず展開してください。
- フォルダの中に `UserConfiguration.txt` があるか確認してください。
- `User Remote Scripts` の直下に対象フォルダを置いてください。
- Ableton Liveを完全終了してから再起動してください。

## ノブを回しても反応しない

SMK-25 MK2から以下が送信されているか確認してください。

```text
CC20〜35
MIDI Channel 1
```

Live側では、実際にCCが届いているMIDIポートをInputに選択してください。

## Bluetoothで反応しない

Bluetooth版では、DAW / Mackie側ではなく、通常のMIDI / CC側ポートを使用してください。

確認できた環境では:

```text
SMK25II-Bt-MIDI
```

をBlue Hand用に使用します。

---

# English

This repository provides an Ableton Live **User Remote Script** for the M-VAVE **SMK-25 MK2**, allowing up to **16 Blue Hand / Device Control parameters** to be controlled.

Two versions are included:

- USB version
- Bluetooth version

## Download

- `SMK25_MK2_BlueHand_USB_16.zip` — USB version
- `SMK25_MK2_BlueHand_BT_16.zip` — Bluetooth version

Download the ZIP file that matches your connection method.

---

## Specifications

The script uses the following CC assignments for Blue Hand / Device Control.

| Parameter | CC | MIDI Ch. |
|---:|---:|---:|
| 1 | 20 | 1 |
| 2 | 21 | 1 |
| 3 | 22 | 1 |
| 4 | 23 | 1 |
| 5 | 24 | 1 |
| 6 | 25 | 1 |
| 7 | 26 | 1 |
| 8 | 27 | 1 |
| 9 | 28 | 1 |
| 10 | 29 | 1 |
| 11 | 30 | 1 |
| 12 | 31 | 1 |
| 13 | 32 | 1 |
| 14 | 33 | 1 |
| 15 | 34 | 1 |
| 16 | 35 | 1 |

- MIDI Channel: **1**
- Encoder Map Mode: **Absolute**
- Parameters 1–8: **CC20–27**
- Parameters 9–16: **CC28–35**
- Mixer / Transport / Pads: **Disabled**
- Live-side automatic bank switching: **Not included**

If you use the 8 physical knobs in two banks, configure the SMK-25 MK2 as follows:

- Bank 1: **CC20–27**
- Bank 2: **CC28–35**

---

# Before using the Bluetooth version

The Bluetooth version requires more than just installing the Ableton Live Remote Script. You should also install the required **official M-VAVE software**.

For editing and creating SMK-25 MK2 presets, this project recommends **`MidiSuite (new)`**. The CC20–35 preset used for this project was created with the new `MidiSuite (new)`.

For Bluetooth MIDI on Windows, use M-VAVE's official **`Sinco Connector`**.

## Required official M-VAVE software

| Software | Purpose | Recommendation |
|---|---|---|
| **MidiSuite (new)** | Edit SMK-25 MK2 presets, assign knob CCs, write settings to the controller | **Recommended / Used for this project** |
| **Sinco Connector** | Bluetooth MIDI connection for SMK-25 MK2 on Windows 10 / 11 | **Required for the Windows Bluetooth setup used here** |

## Download from the official M-VAVE website

These applications are **not included in this GitHub repository**. Download them separately from the official M-VAVE website.

**M-VAVE App Download**

https://www.m-vave.com/appdownload

**M-VAVE Download**

https://www.m-vave.com/download

**SMK25-II product page**

https://www.m-vave.com/product

Look for:

```text
MidiSuite (new)
Sinco Connector
```

- Use `MidiSuite (new)` to edit the SMK-25 MK2 preset and CC assignments.
- Use `Sinco Connector` to create the Bluetooth MIDI connection on Windows.
- An older `MidiSuite V1.3.7` may also be listed, but this README recommends **MidiSuite (new)**.

> **Important:** The Remote Script, MidiSuite, and Sinco Connector are separate components. This repository provides the Ableton Live Remote Script only. Download `MidiSuite (new)` and `Sinco Connector` separately from the official M-VAVE website.

---

## Windows Bluetooth setup

1. Download **MidiSuite (new)** and **Sinco Connector** from the official M-VAVE website.
2. Use `MidiSuite (new)` to configure the SMK-25 MK2 preset and CC assignments, then save/write the preset to the controller.
3. Enable Bluetooth on the SMK-25 MK2.
4. Connect the SMK-25 MK2 using **Sinco Connector**.
5. Confirm that the SMK25II Bluetooth MIDI ports are available in Windows.
6. Launch Ableton Live.
7. Open `Settings / Preferences → Link, Tempo & MIDI`.
8. Select the Bluetooth Remote Script and the normal MIDI / CC Bluetooth port.

In the tested setup, the ports appear as:

```text
SMK25II-Bt-MIDI   ← Blue Hand / CC control
SMK25II-Bt-DAW    ← DAW / Mackie side
```

Use:

```text
Control Surface : SMK25_MK2_BlueHand_BT_16
Input           : SMK25II-Bt-MIDI
Output          : SMK25II-Bt-MIDI or None
```

Port names may differ depending on the system. If they do, select the normal MIDI / CC port that receives **CC20–35** from the SMK-25 MK2.

---

## Configure the SMK-25 MK2 preset

This Remote Script expects the following messages from the SMK-25 MK2.

```text
MIDI Channel 1

Bank / Set 1
CC20
CC21
CC22
CC23
CC24
CC25
CC26
CC27

Bank / Set 2
CC28
CC29
CC30
CC31
CC32
CC33
CC34
CC35
```

If your current SMK-25 MK2 preset does not use these CC assignments, edit it with the official **`MidiSuite (new)`**.

### Recommended knob assignments

| Physical control | Bank 1 | Bank 2 |
|---|---:|---:|
| Knob 1 | CC20 | CC28 |
| Knob 2 | CC21 | CC29 |
| Knob 3 | CC22 | CC30 |
| Knob 4 | CC23 | CC31 |
| Knob 5 | CC24 | CC32 |
| Knob 6 | CC25 | CC33 |
| Knob 7 | CC26 | CC34 |
| Knob 8 | CC27 | CC35 |

Common settings:

```text
MIDI Channel : 1
Encoder Mode : Absolute
```

After editing the preset, save/write the settings from MidiSuite to the SMK-25 MK2.

---

## Recommended Bluetooth setup order

```text
1. Download MidiSuite (new) and Sinco Connector from M-VAVE
        ↓
2. Configure the SMK-25 MK2 knob CCs in MidiSuite (new)
        ↓
3. Save/write the preset to the controller
        ↓
4. On Windows, connect via Sinco Connector
        ↓
5. Place the Bluetooth Remote Script in User Remote Scripts
        ↓
6. Start Ableton Live
        ↓
7. Select SMK25_MK2_BlueHand_BT_16 as the Control Surface
        ↓
8. Select SMK25II-Bt-MIDI as the Input
        ↓
9. Select a device in Ableton Live
        ↓
10. Control Parameters 1–16 with Blue Hand
```

---

# Installation

## 1. Extract the ZIP file

### USB version

```text
SMK25_MK2_BlueHand_USB_16/
├─ README.md
└─ UserConfiguration.txt
```

### Bluetooth version

```text
SMK25_MK2_BlueHand_BT_16/
├─ README.md
└─ UserConfiguration.txt
```

## 2. Quit Ableton Live

Completely close Ableton Live before copying the Remote Script folder.

## 3. Copy the folder into User Remote Scripts

In the tested setup:

```text
...\Live 12.3.2\Preferences\User Remote Scripts\
```

USB:

```text
...\Live 12.3.2\Preferences\User Remote Scripts\
└─ SMK25_MK2_BlueHand_USB_16\
   ├─ README.md
   └─ UserConfiguration.txt
```

Bluetooth:

```text
...\Live 12.3.2\Preferences\User Remote Scripts\
└─ SMK25_MK2_BlueHand_BT_16\
   ├─ README.md
   └─ UserConfiguration.txt
```

## 4. Start Ableton Live

Open:

**Preferences / Settings → Link, Tempo & MIDI**

---

# USB setup

```text
Control Surface : SMK25_MK2_BlueHand_USB_16
Input           : Normal USB CC/MIDI port
Output          : Same USB port, or None
```

The USB port name used in the tested setup was:

```text
SMK25II MIDI 2
```

If your port name is different, select the USB MIDI port that receives **CC20–35**.

---

# Bluetooth setup

```text
Control Surface : SMK25_MK2_BlueHand_BT_16
Input           : Normal Bluetooth MIDI / CC port
Output          : Same Bluetooth MIDI port, or None
```

Tested port names:

```text
SMK25II-Bt-MIDI   ← Blue Hand
SMK25II-Bt-DAW    ← DAW / Mackie side
```

For Blue Hand, use:

```text
SMK25II-Bt-MIDI
```

Do not use `SMK25II-Bt-DAW` as the Blue Hand input.

---

# Using Blue Hand

After setup, select a device in Ableton Live. The SMK-25 MK2 can then control the parameters assigned to the Blue Hand device control.

```text
CC20–27 → Parameters 1–8
CC28–35 → Parameters 9–16
```

If you use 8 knobs in two banks, switch the SMK-25 MK2 preset/bank so that the knobs send CC20–27 or CC28–35.

---

# Changing the CC assignments

You can edit the following entries in `UserConfiguration.txt`:

```text
Encoder1
～
Encoder16
```

Change them to match the CC numbers actually sent by your SMK-25 MK2.

---

# Features not included

- Automatic Live-side bank/page switching
- Mixer control
- Transport control
- Pad control
- Mackie Control functions

This script is intentionally simple: it sends **16 Device Control CC assignments directly to Blue Hand**.

---

# Troubleshooting

## The Control Surface does not appear

- Extract the ZIP file first.
- Make sure `UserConfiguration.txt` is inside the Remote Script folder.
- Place the folder directly inside `User Remote Scripts`.
- Completely quit and restart Ableton Live.

## The knobs do not respond

Confirm that the SMK-25 MK2 is sending:

```text
CC20–35
MIDI Channel 1
```

In Ableton Live, select the MIDI input port that is actually receiving those CC messages.

## Bluetooth does not respond

Use the normal MIDI / CC Bluetooth port, not the DAW / Mackie port.

In the tested setup:

```text
SMK25II-Bt-MIDI
```

is used for Blue Hand.

---

## Notes

The USB and Bluetooth scripts are based on working `UserConfiguration.txt` configurations and extend the Blue Hand / Device Control section to 16 parameters.

MIDI port names, Ableton Live settings, and the exact M-VAVE software UI may differ depending on OS, software version, and connection method.
