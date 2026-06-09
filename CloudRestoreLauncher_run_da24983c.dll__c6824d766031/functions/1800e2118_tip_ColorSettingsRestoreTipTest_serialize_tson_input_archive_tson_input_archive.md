# _tip_ColorSettingsRestoreTipTest::serialize<tson::input_archive>(tson::input_archive &)

- ea: `0x1800e2118`
- end: `0x1800e2258`
- name: `??$serialize@Vinput_archive@tson@@@_tip_ColorSettingsRestoreTipTest@@QEAAXAEAVinput_archive@tson@@@Z`
- size: `320`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800e4790`

## callees

- `0x1800342fc`

## string_xrefs

- `0x1800e2131`: `lightModeRegSet`
- `0x1800e2153`: `systemModeRegSet`
- `0x1800e2176`: `transparencyRegSet`
- `0x1800e2199`: `colorPrevalenceRegSet`
- `0x1800e21bc`: `autoColorizationRegSet`
- `0x1800e21df`: `dwmColorPrevalenceRegSet`

## pseudocode

```c
__int64 __fastcall _tip_ColorSettingsRestoreTipTest::serialize<tson::input_archive>(__int64 a1, __int64 a2)
{
  const char *v5; // [rsp+20h] [rbp-20h] BYREF
  char v6; // [rsp+28h] [rbp-18h]
  __int64 v7; // [rsp+30h] [rbp-10h]

  v6 = 15;
  v5 = "lightModeRegSet";
  v7 = a1 + 17;
  tson::input_archive::process<tson::nvp<bool &>>(a2, &v5);
  v6 = 16;
  v5 = "systemModeRegSet";
  v7 = a1 + 18;
  tson::input_archive::process<tson::nvp<bool &>>(a2, &v5);
  v6 = 18;
  v5 = "transparencyRegSet";
  v7 = a1 + 19;
  tson::input_archive::process<tson::nvp<bool &>>(a2, &v5);
  v6 = 21;
  v5 = "colorPrevalenceRegSet";
  v7 = a1 + 20;
  tson::input_archive::process<tson::nvp<bool &>>(a2, &v5);
  v6 = 22;
  v5 = "autoColorizationRegSet";
  v7 = a1 + 21;
  tson::input_archive::process<tson::nvp<bool &>>(a2, &v5);
  v6 = 24;
  v5 = "dwmColorPrevalenceRegSet";
  v7 = a1 + 22;
  tson::input_archive::process<tson::nvp<bool &>>(a2, &v5);
  v6 = 10;
  v5 = "bondLoaded";
  v7 = a1 + 16;
  tson::input_archive::process<tson::nvp<bool &>>(a2, &v5);
  v6 = 19;
  v5 = "setThemeAccentColor";
  v7 = a1 + 23;
  return tson::input_archive::process<tson::nvp<bool &>>(a2, &v5);
}

```

## disassembly

```asm
0x1800e2118  mov     [rsp-8+arg_0], rbx
0x1800e211d  mov     [rsp-8+arg_8], rdi
0x1800e2122  push    rbp
0x1800e2123  mov     rbp, rsp
0x1800e2126  sub     rsp, 40h
0x1800e212a  mov     rdi, rdx
0x1800e212d  mov     [rbp+var_18], 0Fh
0x1800e2131  lea     rax, aLightmoderegse; "lightModeRegSet"
0x1800e2138  mov     rbx, rcx
0x1800e213b  mov     [rbp+var_20], rax
0x1800e213f  lea     rdx, [rbp+var_20]
0x1800e2143  lea     rax, [rcx+11h]
0x1800e2147  mov     rcx, rdi
0x1800e214a  mov     [rbp+var_10], rax
0x1800e214e  call    ??$process@V?$nvp@AEA_N@tson@@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEA_N@1@@Z; tson::input_archive::process<tson::nvp<bool &>>(tson::nvp<bool &> &&)
0x1800e2153  lea     rax, aSystemmoderegs; "systemModeRegSet"
0x1800e215a  mov     [rbp+var_18], 10h
0x1800e215e  mov     [rbp+var_20], rax
0x1800e2162  lea     rdx, [rbp+var_20]
0x1800e2166  lea     rax, [rbx+12h]
0x1800e216a  mov     rcx, rdi
0x1800e216d  mov     [rbp+var_10], rax
0x1800e2171  call    ??$process@V?$nvp@AEA_N@tson@@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEA_N@1@@Z; tson::input_archive::process<tson::nvp<bool &>>(tson::nvp<bool &> &&)
0x1800e2176  lea     rax, aTransparencyre; "transparencyRegSet"
0x1800e217d  mov     [rbp+var_18], 12h
0x1800e2181  mov     [rbp+var_20], rax
0x1800e2185  lea     rdx, [rbp+var_20]
0x1800e2189  lea     rax, [rbx+13h]
0x1800e218d  mov     rcx, rdi
0x1800e2190  mov     [rbp+var_10], rax
0x1800e2194  call    ??$process@V?$nvp@AEA_N@tson@@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEA_N@1@@Z; tson::input_archive::process<tson::nvp<bool &>>(tson::nvp<bool &> &&)
0x1800e2199  lea     rax, aColorprevalenc; "colorPrevalenceRegSet"
0x1800e21a0  mov     [rbp+var_18], 15h
0x1800e21a4  mov     [rbp+var_20], rax
0x1800e21a8  lea     rdx, [rbp+var_20]
0x1800e21ac  lea     rax, [rbx+14h]
0x1800e21b0  mov     rcx, rdi
0x1800e21b3  mov     [rbp+var_10], rax
0x1800e21b7  call    ??$process@V?$nvp@AEA_N@tson@@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEA_N@1@@Z; tson::input_archive::process<tson::nvp<bool &>>(tson::nvp<bool &> &&)
0x1800e21bc  lea     rax, aAutocolorizati_0; "autoColorizationRegSet"
0x1800e21c3  mov     [rbp+var_18], 16h
0x1800e21c7  mov     [rbp+var_20], rax
0x1800e21cb  lea     rdx, [rbp+var_20]
0x1800e21cf  lea     rax, [rbx+15h]
0x1800e21d3  mov     rcx, rdi
0x1800e21d6  mov     [rbp+var_10], rax
0x1800e21da  call    ??$process@V?$nvp@AEA_N@tson@@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEA_N@1@@Z; tson::input_archive::process<tson::nvp<bool &>>(tson::nvp<bool &> &&)
0x1800e21df  lea     rax, aDwmcolorpreval; "dwmColorPrevalenceRegSet"
0x1800e21e6  mov     [rbp+var_18], 18h
0x1800e21ea  mov     [rbp+var_20], rax
0x1800e21ee  lea     rdx, [rbp+var_20]
0x1800e21f2  lea     rax, [rbx+16h]
0x1800e21f6  mov     rcx, rdi
0x1800e21f9  mov     [rbp+var_10], rax
0x1800e21fd  call    ??$process@V?$nvp@AEA_N@tson@@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEA_N@1@@Z; tson::input_archive::process<tson::nvp<bool &>>(tson::nvp<bool &> &&)
0x1800e2202  lea     rax, aBondloaded; "bondLoaded"
0x1800e2209  mov     [rbp+var_18], 0Ah
0x1800e220d  mov     [rbp+var_20], rax
0x1800e2211  lea     rdx, [rbp+var_20]
0x1800e2215  lea     rax, [rbx+10h]
0x1800e2219  mov     rcx, rdi
0x1800e221c  mov     [rbp+var_10], rax
0x1800e2220  call    ??$process@V?$nvp@AEA_N@tson@@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEA_N@1@@Z; tson::input_archive::process<tson::nvp<bool &>>(tson::nvp<bool &> &&)
0x1800e2225  lea     rax, aSetthemeaccent; "setThemeAccentColor"
0x1800e222c  mov     [rbp+var_18], 13h
0x1800e2230  mov     [rbp+var_20], rax
0x1800e2234  lea     rdx, [rbp+var_20]
0x1800e2238  lea     rax, [rbx+17h]
0x1800e223c  mov     rcx, rdi
0x1800e223f  mov     [rbp+var_10], rax
0x1800e2243  call    ??$process@V?$nvp@AEA_N@tson@@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEA_N@1@@Z; tson::input_archive::process<tson::nvp<bool &>>(tson::nvp<bool &> &&)
0x1800e2248  mov     rbx, [rsp+40h+arg_0]
0x1800e224d  mov     rdi, [rsp+40h+arg_8]
0x1800e2252  add     rsp, 40h
0x1800e2256  pop     rbp
0x1800e2257  retn
```
