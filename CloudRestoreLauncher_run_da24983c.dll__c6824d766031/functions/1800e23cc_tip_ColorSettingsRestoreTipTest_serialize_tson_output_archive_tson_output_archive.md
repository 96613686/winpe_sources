# _tip_ColorSettingsRestoreTipTest::serialize<tson::output_archive>(tson::output_archive &)

- ea: `0x1800e23cc`
- end: `0x1800e250c`
- name: `??$serialize@Voutput_archive@tson@@@_tip_ColorSettingsRestoreTipTest@@QEAAXAEAVoutput_archive@tson@@@Z`
- size: `320`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800e4c60`

## callees

- `0x18002f134`

## string_xrefs

- `0x1800e23e5`: `lightModeRegSet`
- `0x1800e2407`: `systemModeRegSet`
- `0x1800e242a`: `transparencyRegSet`
- `0x1800e244d`: `colorPrevalenceRegSet`
- `0x1800e2470`: `autoColorizationRegSet`
- `0x1800e2493`: `dwmColorPrevalenceRegSet`

## pseudocode

```c
__int64 __fastcall _tip_ColorSettingsRestoreTipTest::serialize<tson::output_archive>(__int64 a1, __int64 a2)
{
  const char *v5; // [rsp+20h] [rbp-20h] BYREF
  char v6; // [rsp+28h] [rbp-18h]
  __int64 v7; // [rsp+30h] [rbp-10h]

  v6 = 15;
  v5 = "lightModeRegSet";
  v7 = a1 + 17;
  tson::output_archive::operator()<tson::nvp<bool &>>(a2, &v5);
  v6 = 16;
  v5 = "systemModeRegSet";
  v7 = a1 + 18;
  tson::output_archive::operator()<tson::nvp<bool &>>(a2, &v5);
  v6 = 18;
  v5 = "transparencyRegSet";
  v7 = a1 + 19;
  tson::output_archive::operator()<tson::nvp<bool &>>(a2, &v5);
  v6 = 21;
  v5 = "colorPrevalenceRegSet";
  v7 = a1 + 20;
  tson::output_archive::operator()<tson::nvp<bool &>>(a2, &v5);
  v6 = 22;
  v5 = "autoColorizationRegSet";
  v7 = a1 + 21;
  tson::output_archive::operator()<tson::nvp<bool &>>(a2, &v5);
  v6 = 24;
  v5 = "dwmColorPrevalenceRegSet";
  v7 = a1 + 22;
  tson::output_archive::operator()<tson::nvp<bool &>>(a2, &v5);
  v6 = 10;
  v5 = "bondLoaded";
  v7 = a1 + 16;
  tson::output_archive::operator()<tson::nvp<bool &>>(a2, &v5);
  v6 = 19;
  v5 = "setThemeAccentColor";
  v7 = a1 + 23;
  return tson::output_archive::operator()<tson::nvp<bool &>>(a2, &v5);
}

```

## disassembly

```asm
0x1800e23cc  mov     [rsp-8+arg_0], rbx
0x1800e23d1  mov     [rsp-8+arg_8], rdi
0x1800e23d6  push    rbp
0x1800e23d7  mov     rbp, rsp
0x1800e23da  sub     rsp, 40h
0x1800e23de  mov     rdi, rdx
0x1800e23e1  mov     [rbp+var_18], 0Fh
0x1800e23e5  lea     rax, aLightmoderegse; "lightModeRegSet"
0x1800e23ec  mov     rbx, rcx
0x1800e23ef  mov     [rbp+var_20], rax
0x1800e23f3  lea     rdx, [rbp+var_20]
0x1800e23f7  lea     rax, [rcx+11h]
0x1800e23fb  mov     rcx, rdi
0x1800e23fe  mov     [rbp+var_10], rax
0x1800e2402  call    ??$?RV?$nvp@AEA_N@tson@@@output_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@AEA_N@1@@Z; tson::output_archive::operator()<tson::nvp<bool &>>(tson::nvp<bool &> &&)
0x1800e2407  lea     rax, aSystemmoderegs; "systemModeRegSet"
0x1800e240e  mov     [rbp+var_18], 10h
0x1800e2412  mov     [rbp+var_20], rax
0x1800e2416  lea     rdx, [rbp+var_20]
0x1800e241a  lea     rax, [rbx+12h]
0x1800e241e  mov     rcx, rdi
0x1800e2421  mov     [rbp+var_10], rax
0x1800e2425  call    ??$?RV?$nvp@AEA_N@tson@@@output_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@AEA_N@1@@Z; tson::output_archive::operator()<tson::nvp<bool &>>(tson::nvp<bool &> &&)
0x1800e242a  lea     rax, aTransparencyre; "transparencyRegSet"
0x1800e2431  mov     [rbp+var_18], 12h
0x1800e2435  mov     [rbp+var_20], rax
0x1800e2439  lea     rdx, [rbp+var_20]
0x1800e243d  lea     rax, [rbx+13h]
0x1800e2441  mov     rcx, rdi
0x1800e2444  mov     [rbp+var_10], rax
0x1800e2448  call    ??$?RV?$nvp@AEA_N@tson@@@output_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@AEA_N@1@@Z; tson::output_archive::operator()<tson::nvp<bool &>>(tson::nvp<bool &> &&)
0x1800e244d  lea     rax, aColorprevalenc; "colorPrevalenceRegSet"
0x1800e2454  mov     [rbp+var_18], 15h
0x1800e2458  mov     [rbp+var_20], rax
0x1800e245c  lea     rdx, [rbp+var_20]
0x1800e2460  lea     rax, [rbx+14h]
0x1800e2464  mov     rcx, rdi
0x1800e2467  mov     [rbp+var_10], rax
0x1800e246b  call    ??$?RV?$nvp@AEA_N@tson@@@output_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@AEA_N@1@@Z; tson::output_archive::operator()<tson::nvp<bool &>>(tson::nvp<bool &> &&)
0x1800e2470  lea     rax, aAutocolorizati_0; "autoColorizationRegSet"
0x1800e2477  mov     [rbp+var_18], 16h
0x1800e247b  mov     [rbp+var_20], rax
0x1800e247f  lea     rdx, [rbp+var_20]
0x1800e2483  lea     rax, [rbx+15h]
0x1800e2487  mov     rcx, rdi
0x1800e248a  mov     [rbp+var_10], rax
0x1800e248e  call    ??$?RV?$nvp@AEA_N@tson@@@output_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@AEA_N@1@@Z; tson::output_archive::operator()<tson::nvp<bool &>>(tson::nvp<bool &> &&)
0x1800e2493  lea     rax, aDwmcolorpreval; "dwmColorPrevalenceRegSet"
0x1800e249a  mov     [rbp+var_18], 18h
0x1800e249e  mov     [rbp+var_20], rax
0x1800e24a2  lea     rdx, [rbp+var_20]
0x1800e24a6  lea     rax, [rbx+16h]
0x1800e24aa  mov     rcx, rdi
0x1800e24ad  mov     [rbp+var_10], rax
0x1800e24b1  call    ??$?RV?$nvp@AEA_N@tson@@@output_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@AEA_N@1@@Z; tson::output_archive::operator()<tson::nvp<bool &>>(tson::nvp<bool &> &&)
0x1800e24b6  lea     rax, aBondloaded; "bondLoaded"
0x1800e24bd  mov     [rbp+var_18], 0Ah
0x1800e24c1  mov     [rbp+var_20], rax
0x1800e24c5  lea     rdx, [rbp+var_20]
0x1800e24c9  lea     rax, [rbx+10h]
0x1800e24cd  mov     rcx, rdi
0x1800e24d0  mov     [rbp+var_10], rax
0x1800e24d4  call    ??$?RV?$nvp@AEA_N@tson@@@output_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@AEA_N@1@@Z; tson::output_archive::operator()<tson::nvp<bool &>>(tson::nvp<bool &> &&)
0x1800e24d9  lea     rax, aSetthemeaccent; "setThemeAccentColor"
0x1800e24e0  mov     [rbp+var_18], 13h
0x1800e24e4  mov     [rbp+var_20], rax
0x1800e24e8  lea     rdx, [rbp+var_20]
0x1800e24ec  lea     rax, [rbx+17h]
0x1800e24f0  mov     rcx, rdi
0x1800e24f3  mov     [rbp+var_10], rax
0x1800e24f7  call    ??$?RV?$nvp@AEA_N@tson@@@output_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@AEA_N@1@@Z; tson::output_archive::operator()<tson::nvp<bool &>>(tson::nvp<bool &> &&)
0x1800e24fc  mov     rbx, [rsp+40h+arg_0]
0x1800e2501  mov     rdi, [rsp+40h+arg_8]
0x1800e2506  add     rsp, 40h
0x1800e250a  pop     rbp
0x1800e250b  retn
```
