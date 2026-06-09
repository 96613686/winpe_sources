# _tip_ColorSettingsBackupTipTest::serialize<tson::output_archive>(tson::output_archive &)

- ea: `0x1800e2260`
- end: `0x1800e23c3`
- name: `??$serialize@Voutput_archive@tson@@@_tip_ColorSettingsBackupTipTest@@QEAAXAEAVoutput_archive@tson@@@Z`
- size: `355`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callers

- `0x1800e4bd0`

## callees

- `0x18002f134`

## string_xrefs

- `0x1800e229b`: `isBondUpdated`
- `0x1800e22be`: `lightThemeRegRead`
- `0x1800e22e1`: `systemThemeRegRead`
- `0x1800e2304`: `transparencyRegRead`
- `0x1800e2327`: `colorPrevalenceRegRead`
- `0x1800e234a`: `autoColorizatonRegRead`
- `0x1800e236d`: `dwmColorPrevalenceRegRead`

## pseudocode

```c
__int64 __fastcall _tip_ColorSettingsBackupTipTest::serialize<tson::output_archive>(__int64 a1, __int64 a2)
{
  const char *v5; // [rsp+20h] [rbp-20h] BYREF
  char v6; // [rsp+28h] [rbp-18h]
  __int64 v7; // [rsp+30h] [rbp-10h]

  v6 = 10;
  v5 = "isBondLoad";
  v7 = a1 + 16;
  tson::output_archive::operator()<tson::nvp<bool &>>(a2, &v5);
  v6 = 13;
  v5 = "isBondUpdated";
  v7 = a1 + 17;
  tson::output_archive::operator()<tson::nvp<bool &>>(a2, &v5);
  v6 = 17;
  v5 = "lightThemeRegRead";
  v7 = a1 + 18;
  tson::output_archive::operator()<tson::nvp<bool &>>(a2, &v5);
  v6 = 18;
  v5 = "systemThemeRegRead";
  v7 = a1 + 19;
  tson::output_archive::operator()<tson::nvp<bool &>>(a2, &v5);
  v6 = 19;
  v5 = "transparencyRegRead";
  v7 = a1 + 20;
  tson::output_archive::operator()<tson::nvp<bool &>>(a2, &v5);
  v6 = 22;
  v5 = "colorPrevalenceRegRead";
  v7 = a1 + 21;
  tson::output_archive::operator()<tson::nvp<bool &>>(a2, &v5);
  v6 = 22;
  v5 = "autoColorizatonRegRead";
  v7 = a1 + 22;
  tson::output_archive::operator()<tson::nvp<bool &>>(a2, &v5);
  v6 = 25;
  v5 = "dwmColorPrevalenceRegRead";
  v7 = a1 + 23;
  tson::output_archive::operator()<tson::nvp<bool &>>(a2, &v5);
  v6 = 19;
  v5 = "getAccentThemeColor";
  v7 = a1 + 24;
  return tson::output_archive::operator()<tson::nvp<bool &>>(a2, &v5);
}

```

## disassembly

```asm
0x1800e2260  mov     [rsp-8+arg_0], rbx
0x1800e2265  mov     [rsp-8+arg_8], rdi
0x1800e226a  push    rbp
0x1800e226b  mov     rbp, rsp
0x1800e226e  sub     rsp, 40h
0x1800e2272  mov     rdi, rdx
0x1800e2275  mov     [rbp+var_18], 0Ah
0x1800e2279  lea     rax, aIsbondload; "isBondLoad"
0x1800e2280  mov     rbx, rcx
0x1800e2283  mov     [rbp+var_20], rax
0x1800e2287  lea     rdx, [rbp+var_20]
0x1800e228b  lea     rax, [rcx+10h]
0x1800e228f  mov     rcx, rdi
0x1800e2292  mov     [rbp+var_10], rax
0x1800e2296  call    ??$?RV?$nvp@AEA_N@tson@@@output_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@AEA_N@1@@Z; tson::output_archive::operator()<tson::nvp<bool &>>(tson::nvp<bool &> &&)
0x1800e229b  lea     rax, aIsbondupdated; "isBondUpdated"
0x1800e22a2  mov     [rbp+var_18], 0Dh
0x1800e22a6  mov     [rbp+var_20], rax
0x1800e22aa  lea     rdx, [rbp+var_20]
0x1800e22ae  lea     rax, [rbx+11h]
0x1800e22b2  mov     rcx, rdi
0x1800e22b5  mov     [rbp+var_10], rax
0x1800e22b9  call    ??$?RV?$nvp@AEA_N@tson@@@output_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@AEA_N@1@@Z; tson::output_archive::operator()<tson::nvp<bool &>>(tson::nvp<bool &> &&)
0x1800e22be  lea     rax, aLightthemeregr; "lightThemeRegRead"
0x1800e22c5  mov     [rbp+var_18], 11h
0x1800e22c9  mov     [rbp+var_20], rax
0x1800e22cd  lea     rdx, [rbp+var_20]
0x1800e22d1  lea     rax, [rbx+12h]
0x1800e22d5  mov     rcx, rdi
0x1800e22d8  mov     [rbp+var_10], rax
0x1800e22dc  call    ??$?RV?$nvp@AEA_N@tson@@@output_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@AEA_N@1@@Z; tson::output_archive::operator()<tson::nvp<bool &>>(tson::nvp<bool &> &&)
0x1800e22e1  lea     rax, aSystemthemereg; "systemThemeRegRead"
0x1800e22e8  mov     [rbp+var_18], 12h
0x1800e22ec  mov     [rbp+var_20], rax
0x1800e22f0  lea     rdx, [rbp+var_20]
0x1800e22f4  lea     rax, [rbx+13h]
0x1800e22f8  mov     rcx, rdi
0x1800e22fb  mov     [rbp+var_10], rax
0x1800e22ff  call    ??$?RV?$nvp@AEA_N@tson@@@output_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@AEA_N@1@@Z; tson::output_archive::operator()<tson::nvp<bool &>>(tson::nvp<bool &> &&)
0x1800e2304  lea     rax, aTransparencyre_0; "transparencyRegRead"
0x1800e230b  mov     [rbp+var_18], 13h
0x1800e230f  mov     [rbp+var_20], rax
0x1800e2313  lea     rdx, [rbp+var_20]
0x1800e2317  lea     rax, [rbx+14h]
0x1800e231b  mov     rcx, rdi
0x1800e231e  mov     [rbp+var_10], rax
0x1800e2322  call    ??$?RV?$nvp@AEA_N@tson@@@output_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@AEA_N@1@@Z; tson::output_archive::operator()<tson::nvp<bool &>>(tson::nvp<bool &> &&)
0x1800e2327  lea     rax, aColorprevalenc_0; "colorPrevalenceRegRead"
0x1800e232e  mov     [rbp+var_18], 16h
0x1800e2332  mov     [rbp+var_20], rax
0x1800e2336  lea     rdx, [rbp+var_20]
0x1800e233a  lea     rax, [rbx+15h]
0x1800e233e  mov     rcx, rdi
0x1800e2341  mov     [rbp+var_10], rax
0x1800e2345  call    ??$?RV?$nvp@AEA_N@tson@@@output_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@AEA_N@1@@Z; tson::output_archive::operator()<tson::nvp<bool &>>(tson::nvp<bool &> &&)
0x1800e234a  lea     rax, aAutocolorizato; "autoColorizatonRegRead"
0x1800e2351  mov     [rbp+var_18], 16h
0x1800e2355  mov     [rbp+var_20], rax
0x1800e2359  lea     rdx, [rbp+var_20]
0x1800e235d  lea     rax, [rbx+16h]
0x1800e2361  mov     rcx, rdi
0x1800e2364  mov     [rbp+var_10], rax
0x1800e2368  call    ??$?RV?$nvp@AEA_N@tson@@@output_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@AEA_N@1@@Z; tson::output_archive::operator()<tson::nvp<bool &>>(tson::nvp<bool &> &&)
0x1800e236d  lea     rax, aDwmcolorpreval_0; "dwmColorPrevalenceRegRead"
0x1800e2374  mov     [rbp+var_18], 19h
0x1800e2378  mov     [rbp+var_20], rax
0x1800e237c  lea     rdx, [rbp+var_20]
0x1800e2380  lea     rax, [rbx+17h]
0x1800e2384  mov     rcx, rdi
0x1800e2387  mov     [rbp+var_10], rax
0x1800e238b  call    ??$?RV?$nvp@AEA_N@tson@@@output_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@AEA_N@1@@Z; tson::output_archive::operator()<tson::nvp<bool &>>(tson::nvp<bool &> &&)
0x1800e2390  lea     rax, aGetaccenttheme; "getAccentThemeColor"
0x1800e2397  mov     [rbp+var_18], 13h
0x1800e239b  mov     [rbp+var_20], rax
0x1800e239f  lea     rdx, [rbp+var_20]
0x1800e23a3  lea     rax, [rbx+18h]
0x1800e23a7  mov     rcx, rdi
0x1800e23aa  mov     [rbp+var_10], rax
0x1800e23ae  call    ??$?RV?$nvp@AEA_N@tson@@@output_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@AEA_N@1@@Z; tson::output_archive::operator()<tson::nvp<bool &>>(tson::nvp<bool &> &&)
0x1800e23b3  mov     rbx, [rsp+40h+arg_0]
0x1800e23b8  mov     rdi, [rsp+40h+arg_8]
0x1800e23bd  add     rsp, 40h
0x1800e23c1  pop     rbp
0x1800e23c2  retn
```
