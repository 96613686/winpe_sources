# _tip_ColorSettingsBackupTipTest::serialize<tson::input_archive>(tson::input_archive &)

- ea: `0x1800e1fac`
- end: `0x1800e210f`
- name: `??$serialize@Vinput_archive@tson@@@_tip_ColorSettingsBackupTipTest@@QEAAXAEAVinput_archive@tson@@@Z`
- size: `355`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callers

- `0x1800e4730`

## callees

- `0x1800342fc`

## string_xrefs

- `0x1800e1fe7`: `isBondUpdated`
- `0x1800e200a`: `lightThemeRegRead`
- `0x1800e202d`: `systemThemeRegRead`
- `0x1800e2050`: `transparencyRegRead`
- `0x1800e2073`: `colorPrevalenceRegRead`
- `0x1800e2096`: `autoColorizatonRegRead`
- `0x1800e20b9`: `dwmColorPrevalenceRegRead`

## pseudocode

```c
__int64 __fastcall _tip_ColorSettingsBackupTipTest::serialize<tson::input_archive>(__int64 a1, __int64 a2)
{
  const char *v5; // [rsp+20h] [rbp-20h] BYREF
  char v6; // [rsp+28h] [rbp-18h]
  __int64 v7; // [rsp+30h] [rbp-10h]

  v6 = 10;
  v5 = "isBondLoad";
  v7 = a1 + 16;
  tson::input_archive::process<tson::nvp<bool &>>(a2, &v5);
  v6 = 13;
  v5 = "isBondUpdated";
  v7 = a1 + 17;
  tson::input_archive::process<tson::nvp<bool &>>(a2, &v5);
  v6 = 17;
  v5 = "lightThemeRegRead";
  v7 = a1 + 18;
  tson::input_archive::process<tson::nvp<bool &>>(a2, &v5);
  v6 = 18;
  v5 = "systemThemeRegRead";
  v7 = a1 + 19;
  tson::input_archive::process<tson::nvp<bool &>>(a2, &v5);
  v6 = 19;
  v5 = "transparencyRegRead";
  v7 = a1 + 20;
  tson::input_archive::process<tson::nvp<bool &>>(a2, &v5);
  v6 = 22;
  v5 = "colorPrevalenceRegRead";
  v7 = a1 + 21;
  tson::input_archive::process<tson::nvp<bool &>>(a2, &v5);
  v6 = 22;
  v5 = "autoColorizatonRegRead";
  v7 = a1 + 22;
  tson::input_archive::process<tson::nvp<bool &>>(a2, &v5);
  v6 = 25;
  v5 = "dwmColorPrevalenceRegRead";
  v7 = a1 + 23;
  tson::input_archive::process<tson::nvp<bool &>>(a2, &v5);
  v6 = 19;
  v5 = "getAccentThemeColor";
  v7 = a1 + 24;
  return tson::input_archive::process<tson::nvp<bool &>>(a2, &v5);
}

```

## disassembly

```asm
0x1800e1fac  mov     [rsp-8+arg_0], rbx
0x1800e1fb1  mov     [rsp-8+arg_8], rdi
0x1800e1fb6  push    rbp
0x1800e1fb7  mov     rbp, rsp
0x1800e1fba  sub     rsp, 40h
0x1800e1fbe  mov     rdi, rdx
0x1800e1fc1  mov     [rbp+var_18], 0Ah
0x1800e1fc5  lea     rax, aIsbondload; "isBondLoad"
0x1800e1fcc  mov     rbx, rcx
0x1800e1fcf  mov     [rbp+var_20], rax
0x1800e1fd3  lea     rdx, [rbp+var_20]
0x1800e1fd7  lea     rax, [rcx+10h]
0x1800e1fdb  mov     rcx, rdi
0x1800e1fde  mov     [rbp+var_10], rax
0x1800e1fe2  call    ??$process@V?$nvp@AEA_N@tson@@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEA_N@1@@Z; tson::input_archive::process<tson::nvp<bool &>>(tson::nvp<bool &> &&)
0x1800e1fe7  lea     rax, aIsbondupdated; "isBondUpdated"
0x1800e1fee  mov     [rbp+var_18], 0Dh
0x1800e1ff2  mov     [rbp+var_20], rax
0x1800e1ff6  lea     rdx, [rbp+var_20]
0x1800e1ffa  lea     rax, [rbx+11h]
0x1800e1ffe  mov     rcx, rdi
0x1800e2001  mov     [rbp+var_10], rax
0x1800e2005  call    ??$process@V?$nvp@AEA_N@tson@@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEA_N@1@@Z; tson::input_archive::process<tson::nvp<bool &>>(tson::nvp<bool &> &&)
0x1800e200a  lea     rax, aLightthemeregr; "lightThemeRegRead"
0x1800e2011  mov     [rbp+var_18], 11h
0x1800e2015  mov     [rbp+var_20], rax
0x1800e2019  lea     rdx, [rbp+var_20]
0x1800e201d  lea     rax, [rbx+12h]
0x1800e2021  mov     rcx, rdi
0x1800e2024  mov     [rbp+var_10], rax
0x1800e2028  call    ??$process@V?$nvp@AEA_N@tson@@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEA_N@1@@Z; tson::input_archive::process<tson::nvp<bool &>>(tson::nvp<bool &> &&)
0x1800e202d  lea     rax, aSystemthemereg; "systemThemeRegRead"
0x1800e2034  mov     [rbp+var_18], 12h
0x1800e2038  mov     [rbp+var_20], rax
0x1800e203c  lea     rdx, [rbp+var_20]
0x1800e2040  lea     rax, [rbx+13h]
0x1800e2044  mov     rcx, rdi
0x1800e2047  mov     [rbp+var_10], rax
0x1800e204b  call    ??$process@V?$nvp@AEA_N@tson@@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEA_N@1@@Z; tson::input_archive::process<tson::nvp<bool &>>(tson::nvp<bool &> &&)
0x1800e2050  lea     rax, aTransparencyre_0; "transparencyRegRead"
0x1800e2057  mov     [rbp+var_18], 13h
0x1800e205b  mov     [rbp+var_20], rax
0x1800e205f  lea     rdx, [rbp+var_20]
0x1800e2063  lea     rax, [rbx+14h]
0x1800e2067  mov     rcx, rdi
0x1800e206a  mov     [rbp+var_10], rax
0x1800e206e  call    ??$process@V?$nvp@AEA_N@tson@@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEA_N@1@@Z; tson::input_archive::process<tson::nvp<bool &>>(tson::nvp<bool &> &&)
0x1800e2073  lea     rax, aColorprevalenc_0; "colorPrevalenceRegRead"
0x1800e207a  mov     [rbp+var_18], 16h
0x1800e207e  mov     [rbp+var_20], rax
0x1800e2082  lea     rdx, [rbp+var_20]
0x1800e2086  lea     rax, [rbx+15h]
0x1800e208a  mov     rcx, rdi
0x1800e208d  mov     [rbp+var_10], rax
0x1800e2091  call    ??$process@V?$nvp@AEA_N@tson@@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEA_N@1@@Z; tson::input_archive::process<tson::nvp<bool &>>(tson::nvp<bool &> &&)
0x1800e2096  lea     rax, aAutocolorizato; "autoColorizatonRegRead"
0x1800e209d  mov     [rbp+var_18], 16h
0x1800e20a1  mov     [rbp+var_20], rax
0x1800e20a5  lea     rdx, [rbp+var_20]
0x1800e20a9  lea     rax, [rbx+16h]
0x1800e20ad  mov     rcx, rdi
0x1800e20b0  mov     [rbp+var_10], rax
0x1800e20b4  call    ??$process@V?$nvp@AEA_N@tson@@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEA_N@1@@Z; tson::input_archive::process<tson::nvp<bool &>>(tson::nvp<bool &> &&)
0x1800e20b9  lea     rax, aDwmcolorpreval_0; "dwmColorPrevalenceRegRead"
0x1800e20c0  mov     [rbp+var_18], 19h
0x1800e20c4  mov     [rbp+var_20], rax
0x1800e20c8  lea     rdx, [rbp+var_20]
0x1800e20cc  lea     rax, [rbx+17h]
0x1800e20d0  mov     rcx, rdi
0x1800e20d3  mov     [rbp+var_10], rax
0x1800e20d7  call    ??$process@V?$nvp@AEA_N@tson@@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEA_N@1@@Z; tson::input_archive::process<tson::nvp<bool &>>(tson::nvp<bool &> &&)
0x1800e20dc  lea     rax, aGetaccenttheme; "getAccentThemeColor"
0x1800e20e3  mov     [rbp+var_18], 13h
0x1800e20e7  mov     [rbp+var_20], rax
0x1800e20eb  lea     rdx, [rbp+var_20]
0x1800e20ef  lea     rax, [rbx+18h]
0x1800e20f3  mov     rcx, rdi
0x1800e20f6  mov     [rbp+var_10], rax
0x1800e20fa  call    ??$process@V?$nvp@AEA_N@tson@@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEA_N@1@@Z; tson::input_archive::process<tson::nvp<bool &>>(tson::nvp<bool &> &&)
0x1800e20ff  mov     rbx, [rsp+40h+arg_0]
0x1800e2104  mov     rdi, [rsp+40h+arg_8]
0x1800e2109  add     rsp, 40h
0x1800e210d  pop     rbp
0x1800e210e  retn
```
