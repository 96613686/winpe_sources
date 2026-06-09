# JobHelper::GetConfig(_JobConfig &)

- ea: `0x18000e0a8`
- end: `0x18000e51b`
- name: `?GetConfig@JobHelper@@AEAAJAEAU_JobConfig@@@Z`
- size: `1139`
- prototype: `__int64 __fastcall(JobHelper *__hidden this, struct _JobConfig *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000b388`

## callees

- `0x180002a50`
- `0x1800062ac`
- `0x180007110`
- `0x180007edc`
- `0x18000a3c0`
- `0x18000e0a8`
- `0x180013074`
- `0x18001f420`

## import_xrefs

- `msvcrt!wcstol` at `0x18000e49f`
- `msvcrt!wcstol` at `0x18000e49f`
- `msvcrt!wcstoul` at `0x18000e127`
- `msvcrt!wcstoul` at `0x18000e1cd`
- `msvcrt!wcstoul` at `0x18000e25e`
- `msvcrt!wcstoul` at `0x18000e2ef`
- `msvcrt!wcstoul` at `0x18000e40e`
- `msvcrt!wcstoul` at `0x18000e127`
- `msvcrt!wcstoul` at `0x18000e1cd`
- `msvcrt!wcstoul` at `0x18000e25e`
- `msvcrt!wcstoul` at `0x18000e2ef`
- `msvcrt!wcstoul` at `0x18000e40e`
- `msvcrt!_wtoi` at `0x18000e381`
- `msvcrt!_wtoi` at `0x18000e381`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall JobHelper::GetConfig(JobHelper *this, struct _JobConfig *a2)
{
  __int64 v3; // rdx
  const wchar_t *v4; // rcx
  unsigned int v5; // eax
  __int64 v6; // rdx
  const wchar_t *v7; // rcx
  unsigned int v8; // eax
  __int64 v9; // rdx
  const wchar_t *v10; // rcx
  unsigned int v11; // eax
  __int64 v12; // rdx
  const wchar_t *v13; // rcx
  unsigned int v14; // eax
  __int64 v15; // rdx
  const wchar_t *v16; // rcx
  __int64 v17; // rdx
  const wchar_t *v18; // rcx
  unsigned int v19; // eax
  __int64 v20; // rdx
  const wchar_t *v21; // rcx
  int v22; // eax
  __int64 v23; // rdx
  wchar_t *String[2]; // [rsp+30h] [rbp-29h] BYREF
  __int64 v26; // [rsp+40h] [rbp-19h]
  unsigned __int64 v27; // [rsp+48h] [rbp-11h]
  MI_Uint64 v28[4]; // [rsp+50h] [rbp-9h] BYREF

  std::wstring::wstring(String, &dword_180022F6C);
  std::wstring::wstring(v28, L"BitsNetworCostFlags");
  GetConfigItem(v28, (__int64)String);
  LOBYTE(v3) = 1;
  std::wstring::_Tidy(v28, v3, 0);
  v4 = (const wchar_t *)String;
  if ( v27 >= 8 )
    v4 = String[0];
  v5 = wcstoul(v4, 0, 10);
  *((_DWORD *)a2 + 1) = v5;
  if ( v5 == -1 || !v26 )
  {
    *((_DWORD *)a2 + 1) = 0;
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        127,
        (unsigned int)&WPP_9f155fbe94773387205a22e9edb85311_Traceguids,
        (unsigned int)L"BitsNetworCostFlags",
        0);
  }
  std::wstring::wstring(v28, L"BitsRetryDelay");
  GetConfigItem(v28, (__int64)String);
  LOBYTE(v6) = 1;
  std::wstring::_Tidy(v28, v6, 0);
  v7 = (const wchar_t *)String;
  if ( v27 >= 8 )
    v7 = String[0];
  v8 = wcstoul(v7, 0, 10);
  *((_DWORD *)a2 + 2) = v8;
  if ( v8 == -1 || !v26 )
  {
    *((_DWORD *)a2 + 2) = 600;
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        128,
        (unsigned int)&WPP_9f155fbe94773387205a22e9edb85311_Traceguids,
        (unsigned int)L"BitsRetryDelay",
        88);
  }
  std::wstring::wstring(v28, L"BitsNoProgressTimeout");
  GetConfigItem(v28, (__int64)String);
  LOBYTE(v9) = 1;
  std::wstring::_Tidy(v28, v9, 0);
  v10 = (const wchar_t *)String;
  if ( v27 >= 8 )
    v10 = String[0];
  v11 = wcstoul(v10, 0, 10);
  *((_DWORD *)a2 + 3) = v11;
  if ( v11 == -1 || !v26 )
  {
    *((_DWORD *)a2 + 3) = 3300;
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        129,
        (unsigned int)&WPP_9f155fbe94773387205a22e9edb85311_Traceguids,
        (unsigned int)L"BitsNoProgressTimeout",
        228);
  }
  std::wstring::wstring(v28, L"DeploymentRetries");
  GetConfigItem(v28, (__int64)String);
  LOBYTE(v12) = 1;
  std::wstring::_Tidy(v28, v12, 0);
  v13 = (const wchar_t *)String;
  if ( v27 >= 8 )
    v13 = String[0];
  v14 = wcstoul(v13, 0, 10);
  *((_DWORD *)a2 + 4) = v14;
  if ( v14 == -1 || !v26 )
  {
    *((_DWORD *)a2 + 4) = 5;
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        130,
        (unsigned int)&WPP_9f155fbe94773387205a22e9edb85311_Traceguids,
        (unsigned int)L"DeploymentRetries",
        5);
  }
  *((_DWORD *)a2 + 6) = CheckCRL();
  std::wstring::wstring(v28, L"BitsJobPriority");
  GetConfigItem(v28, (__int64)String);
  LOBYTE(v15) = 1;
  std::wstring::_Tidy(v28, v15, 0);
  v16 = (const wchar_t *)String;
  if ( v27 >= 8 )
    v16 = String[0];
  *(_DWORD *)a2 = _wtoi(v16);
  if ( !v26 )
  {
    *(_DWORD *)a2 = 0;
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        131,
        (unsigned int)&WPP_9f155fbe94773387205a22e9edb85311_Traceguids,
        (unsigned int)L"BitsJobPriority",
        0);
  }
  std::wstring::wstring(v28, L"DeployWaitTimeout");
  GetConfigItem(v28, (__int64)String);
  LOBYTE(v17) = 1;
  std::wstring::_Tidy(v28, v17, 0);
  v18 = (const wchar_t *)String;
  if ( v27 >= 8 )
    v18 = String[0];
  v19 = wcstoul(v18, 0, 10);
  *((_DWORD *)a2 + 5) = v19;
  if ( v19 == -1 || !v26 )
  {
    *((_DWORD *)a2 + 5) = 120000;
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        132,
        (unsigned int)&WPP_9f155fbe94773387205a22e9edb85311_Traceguids,
        (unsigned int)L"DeployWaitTimeout",
        192);
  }
  std::wstring::wstring(v28, L"JobPurgeIntervalInDays");
  GetConfigItem(v28, (__int64)String);
  LOBYTE(v20) = 1;
  std::wstring::_Tidy(v28, v20, 0);
  v21 = (const wchar_t *)String;
  if ( v27 >= 8 )
    v21 = String[0];
  v22 = wcstol(v21, 0, 10);
  *((_QWORD *)a2 + 4) = v22;
  if ( v22 == 0x7FFFFFFF || !v26 )
  {
    *((_QWORD *)a2 + 4) = 30;
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_Si(*((_QWORD *)WPP_GLOBAL_Control + 2));
  }
  LOBYTE(v23) = 1;
  std::wstring::_Tidy(String, v23, 0);
  return 0;
}

```

## disassembly

```asm
0x18000e0a8  push    rbp
0x18000e0aa  push    rbx
0x18000e0ab  push    r12
0x18000e0ad  push    r13
0x18000e0af  push    r14
0x18000e0b1  push    r15
0x18000e0b3  lea     rbp, [rsp-2Fh]
0x18000e0b8  sub     rsp, 88h
0x18000e0bf  mov     rax, cs:__security_cookie
0x18000e0c6  xor     rax, rsp
0x18000e0c9  mov     [rbp+57h+var_40], rax
0x18000e0cd  mov     rbx, rdx
0x18000e0d0  lea     rdx, dword_180022F6C
0x18000e0d7  lea     rcx, [rbp+57h+String]
0x18000e0db  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18000e0e0  nop
0x18000e0e1  lea     rdx, aBitsnetworcost; "BitsNetworCostFlags"
0x18000e0e8  lea     rcx, [rbp+57h+var_60]
0x18000e0ec  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18000e0f1  nop
0x18000e0f2  lea     rdx, [rbp+57h+String]
0x18000e0f6  lea     rcx, [rbp+57h+var_60]
0x18000e0fa  call    ?GetConfigItem@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV12@@Z; GetConfigItem(std::wstring const &,std::wstring &)
0x18000e0ff  nop
0x18000e100  xor     r8d, r8d
0x18000e103  mov     dl, 1
0x18000e105  lea     rcx, [rbp+57h+var_60]
0x18000e109  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000e10e  lea     rcx, [rbp+57h+String]
0x18000e112  cmp     [rbp+57h+var_68], 8
0x18000e117  cmovnb  rcx, [rbp+57h+String]; String
0x18000e11c  mov     r12d, 0Ah
0x18000e122  mov     r8d, r12d; Radix
0x18000e125  xor     edx, edx; EndPtr
0x18000e127  call    cs:__imp_wcstoul
0x18000e12e  nop     dword ptr [rax+rax+00h]
0x18000e133  mov     [rbx+4], eax
0x18000e136  lea     r15, WPP_9f155fbe94773387205a22e9edb85311_Traceguids
0x18000e13d  lea     r14, WPP_GLOBAL_Control
0x18000e144  or      r13d, 0FFFFFFFFh
0x18000e148  cmp     eax, r13d
0x18000e14b  jz      short loc_18000E154
0x18000e14d  cmp     [rbp+57h+var_70], 0
0x18000e152  jnz     short loc_18000E18D
0x18000e154  mov     dword ptr [rbx+4], 0
0x18000e15b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e162  cmp     rcx, r14
0x18000e165  jz      short loc_18000E18D
0x18000e167  test    byte ptr [rcx+1Ch], 1
0x18000e16b  jz      short loc_18000E18D
0x18000e16d  mov     edx, 7Fh
0x18000e172  mov     dword ptr [rsp+0B0h+var_90], 0
0x18000e17a  lea     r9, aBitsnetworcost; "BitsNetworCostFlags"
0x18000e181  mov     r8, r15
0x18000e184  mov     rcx, [rcx+10h]
0x18000e188  call    WPP_SF_Sd
0x18000e18d  lea     rdx, aBitsretrydelay; "BitsRetryDelay"
0x18000e194  lea     rcx, [rbp+57h+var_60]
0x18000e198  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18000e19d  nop
0x18000e19e  lea     rdx, [rbp+57h+String]
0x18000e1a2  lea     rcx, [rbp+57h+var_60]
0x18000e1a6  call    ?GetConfigItem@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV12@@Z; GetConfigItem(std::wstring const &,std::wstring &)
0x18000e1ab  nop
0x18000e1ac  xor     r8d, r8d
0x18000e1af  mov     dl, 1
0x18000e1b1  lea     rcx, [rbp+57h+var_60]
0x18000e1b5  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000e1ba  lea     rcx, [rbp+57h+String]
0x18000e1be  cmp     [rbp+57h+var_68], 8
0x18000e1c3  cmovnb  rcx, [rbp+57h+String]; String
0x18000e1c8  mov     r8d, r12d; Radix
0x18000e1cb  xor     edx, edx; EndPtr
0x18000e1cd  call    cs:__imp_wcstoul
0x18000e1d4  nop     dword ptr [rax+rax+00h]
0x18000e1d9  mov     [rbx+8], eax
0x18000e1dc  cmp     eax, r13d
0x18000e1df  jz      short loc_18000E1E8
0x18000e1e1  cmp     [rbp+57h+var_70], 0
0x18000e1e6  jnz     short loc_18000E21E
0x18000e1e8  mov     eax, 258h
0x18000e1ed  mov     [rbx+8], eax
0x18000e1f0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e1f7  cmp     rcx, r14
0x18000e1fa  jz      short loc_18000E21E
0x18000e1fc  test    byte ptr [rcx+1Ch], 1
0x18000e200  jz      short loc_18000E21E
0x18000e202  mov     edx, 80h
0x18000e207  mov     dword ptr [rsp+0B0h+var_90], eax
0x18000e20b  lea     r9, aBitsretrydelay; "BitsRetryDelay"
0x18000e212  mov     r8, r15
0x18000e215  mov     rcx, [rcx+10h]
0x18000e219  call    WPP_SF_Sd
0x18000e21e  lea     rdx, aBitsnoprogress; "BitsNoProgressTimeout"
0x18000e225  lea     rcx, [rbp+57h+var_60]
0x18000e229  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18000e22e  nop
0x18000e22f  lea     rdx, [rbp+57h+String]
0x18000e233  lea     rcx, [rbp+57h+var_60]
0x18000e237  call    ?GetConfigItem@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV12@@Z; GetConfigItem(std::wstring const &,std::wstring &)
0x18000e23c  nop
0x18000e23d  xor     r8d, r8d
0x18000e240  mov     dl, 1
0x18000e242  lea     rcx, [rbp+57h+var_60]
0x18000e246  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000e24b  lea     rcx, [rbp+57h+String]
0x18000e24f  cmp     [rbp+57h+var_68], 8
0x18000e254  cmovnb  rcx, [rbp+57h+String]; String
0x18000e259  mov     r8d, r12d; Radix
0x18000e25c  xor     edx, edx; EndPtr
0x18000e25e  call    cs:__imp_wcstoul
0x18000e265  nop     dword ptr [rax+rax+00h]
0x18000e26a  mov     [rbx+0Ch], eax
0x18000e26d  cmp     eax, r13d
0x18000e270  jz      short loc_18000E279
0x18000e272  cmp     [rbp+57h+var_70], 0
0x18000e277  jnz     short loc_18000E2AF
0x18000e279  mov     eax, 0CE4h
0x18000e27e  mov     [rbx+0Ch], eax
0x18000e281  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e288  cmp     rcx, r14
0x18000e28b  jz      short loc_18000E2AF
0x18000e28d  test    byte ptr [rcx+1Ch], 1
0x18000e291  jz      short loc_18000E2AF
0x18000e293  mov     edx, 81h
0x18000e298  mov     dword ptr [rsp+0B0h+var_90], eax
0x18000e29c  lea     r9, aBitsnoprogress; "BitsNoProgressTimeout"
0x18000e2a3  mov     r8, r15
0x18000e2a6  mov     rcx, [rcx+10h]
0x18000e2aa  call    WPP_SF_Sd
0x18000e2af  lea     rdx, aDeploymentretr; "DeploymentRetries"
0x18000e2b6  lea     rcx, [rbp+57h+var_60]
0x18000e2ba  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18000e2bf  nop
0x18000e2c0  lea     rdx, [rbp+57h+String]
0x18000e2c4  lea     rcx, [rbp+57h+var_60]
0x18000e2c8  call    ?GetConfigItem@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV12@@Z; GetConfigItem(std::wstring const &,std::wstring &)
0x18000e2cd  nop
0x18000e2ce  xor     r8d, r8d
0x18000e2d1  mov     dl, 1
0x18000e2d3  lea     rcx, [rbp+57h+var_60]
0x18000e2d7  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000e2dc  lea     rcx, [rbp+57h+String]
0x18000e2e0  cmp     [rbp+57h+var_68], 8
0x18000e2e5  cmovnb  rcx, [rbp+57h+String]; String
0x18000e2ea  mov     r8d, r12d; Radix
0x18000e2ed  xor     edx, edx; EndPtr
0x18000e2ef  call    cs:__imp_wcstoul
0x18000e2f6  nop     dword ptr [rax+rax+00h]
0x18000e2fb  mov     [rbx+10h], eax
0x18000e2fe  cmp     eax, r13d
0x18000e301  jz      short loc_18000E30A
0x18000e303  cmp     [rbp+57h+var_70], 0
0x18000e308  jnz     short loc_18000E33E
0x18000e30a  mov     eax, 5
0x18000e30f  mov     [rbx+10h], eax
0x18000e312  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e319  cmp     rcx, r14
0x18000e31c  jz      short loc_18000E33E
0x18000e31e  test    byte ptr [rcx+1Ch], 1
0x18000e322  jz      short loc_18000E33E
0x18000e324  lea     edx, [rax+7Dh]
0x18000e327  mov     dword ptr [rsp+0B0h+var_90], eax
0x18000e32b  lea     r9, aDeploymentretr; "DeploymentRetries"
0x18000e332  mov     r8, r15
0x18000e335  mov     rcx, [rcx+10h]
0x18000e339  call    WPP_SF_Sd
0x18000e33e  call    ?CheckCRL@@YAHXZ; CheckCRL(void)
0x18000e343  mov     [rbx+18h], eax
0x18000e346  lea     rdx, aBitsjobpriorit; "BitsJobPriority"
0x18000e34d  lea     rcx, [rbp+57h+var_60]
0x18000e351  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18000e356  nop
0x18000e357  lea     rdx, [rbp+57h+String]
0x18000e35b  lea     rcx, [rbp+57h+var_60]
0x18000e35f  call    ?GetConfigItem@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV12@@Z; GetConfigItem(std::wstring const &,std::wstring &)
0x18000e364  nop
0x18000e365  xor     r8d, r8d
0x18000e368  mov     dl, 1
0x18000e36a  lea     rcx, [rbp+57h+var_60]
0x18000e36e  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000e373  lea     rcx, [rbp+57h+String]
0x18000e377  cmp     [rbp+57h+var_68], 8
0x18000e37c  cmovnb  rcx, [rbp+57h+String]; String
0x18000e381  call    cs:__imp__wtoi
0x18000e388  nop     dword ptr [rax+rax+00h]
0x18000e38d  mov     [rbx], eax
0x18000e38f  cmp     [rbp+57h+var_70], 0
0x18000e394  jnz     short loc_18000E3CE
0x18000e396  mov     dword ptr [rbx], 0
0x18000e39c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e3a3  cmp     rcx, r14
0x18000e3a6  jz      short loc_18000E3CE
0x18000e3a8  test    byte ptr [rcx+1Ch], 1
0x18000e3ac  jz      short loc_18000E3CE
0x18000e3ae  mov     edx, 83h
0x18000e3b3  mov     dword ptr [rsp+0B0h+var_90], 0
0x18000e3bb  lea     r9, aBitsjobpriorit; "BitsJobPriority"
0x18000e3c2  mov     r8, r15
0x18000e3c5  mov     rcx, [rcx+10h]
0x18000e3c9  call    WPP_SF_Sd
0x18000e3ce  lea     rdx, aDeploywaittime; "DeployWaitTimeout"
0x18000e3d5  lea     rcx, [rbp+57h+var_60]
0x18000e3d9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18000e3de  nop
0x18000e3df  lea     rdx, [rbp+57h+String]
0x18000e3e3  lea     rcx, [rbp+57h+var_60]
0x18000e3e7  call    ?GetConfigItem@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV12@@Z; GetConfigItem(std::wstring const &,std::wstring &)
0x18000e3ec  nop
0x18000e3ed  xor     r8d, r8d
0x18000e3f0  mov     dl, 1
0x18000e3f2  lea     rcx, [rbp+57h+var_60]
0x18000e3f6  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000e3fb  lea     rcx, [rbp+57h+String]
0x18000e3ff  cmp     [rbp+57h+var_68], 8
0x18000e404  cmovnb  rcx, [rbp+57h+String]; String
0x18000e409  mov     r8d, r12d; Radix
0x18000e40c  xor     edx, edx; EndPtr
0x18000e40e  call    cs:__imp_wcstoul
0x18000e415  nop     dword ptr [rax+rax+00h]
0x18000e41a  mov     [rbx+14h], eax
0x18000e41d  cmp     eax, r13d
0x18000e420  jz      short loc_18000E429
0x18000e422  cmp     [rbp+57h+var_70], 0
0x18000e427  jnz     short loc_18000E45F
0x18000e429  mov     eax, 1D4C0h
0x18000e42e  mov     [rbx+14h], eax
0x18000e431  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e438  cmp     rcx, r14
0x18000e43b  jz      short loc_18000E45F
0x18000e43d  test    byte ptr [rcx+1Ch], 1
0x18000e441  jz      short loc_18000E45F
0x18000e443  mov     edx, 84h
0x18000e448  mov     dword ptr [rsp+0B0h+var_90], eax
0x18000e44c  lea     r9, aDeploywaittime; "DeployWaitTimeout"
0x18000e453  mov     r8, r15
0x18000e456  mov     rcx, [rcx+10h]
0x18000e45a  call    WPP_SF_Sd
0x18000e45f  lea     rdx, aJobpurgeinterv; "JobPurgeIntervalInDays"
0x18000e466  lea     rcx, [rbp+57h+var_60]
0x18000e46a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18000e46f  nop
0x18000e470  lea     rdx, [rbp+57h+String]
0x18000e474  lea     rcx, [rbp+57h+var_60]
0x18000e478  call    ?GetConfigItem@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV12@@Z; GetConfigItem(std::wstring const &,std::wstring &)
0x18000e47d  nop
0x18000e47e  xor     r8d, r8d
0x18000e481  mov     dl, 1
0x18000e483  lea     rcx, [rbp+57h+var_60]
0x18000e487  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000e48c  lea     rcx, [rbp+57h+String]
0x18000e490  cmp     [rbp+57h+var_68], 8
0x18000e495  cmovnb  rcx, [rbp+57h+String]; String
0x18000e49a  mov     r8d, r12d; Radix
0x18000e49d  xor     edx, edx; EndPtr
0x18000e49f  call    cs:__imp_wcstol
0x18000e4a6  nop     dword ptr [rax+rax+00h]
0x18000e4ab  movsxd  rcx, eax
0x18000e4ae  mov     [rbx+20h], rcx
0x18000e4b2  cmp     rcx, 7FFFFFFFh
0x18000e4b9  jz      short loc_18000E4C2
0x18000e4bb  cmp     [rbp+57h+var_70], 0
0x18000e4c0  jnz     short loc_18000E4EC
0x18000e4c2  mov     eax, 1Eh
0x18000e4c7  mov     [rbx+20h], rax
0x18000e4cb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e4d2  cmp     rcx, r14
0x18000e4d5  jz      short loc_18000E4EC
0x18000e4d7  test    byte ptr [rcx+1Ch], 1
0x18000e4db  jz      short loc_18000E4EC
0x18000e4dd  mov     [rsp+0B0h+var_90], rax
0x18000e4e2  mov     rcx, [rcx+10h]
0x18000e4e6  call    WPP_SF_Si
0x18000e4eb  nop
0x18000e4ec  xor     r8d, r8d
0x18000e4ef  mov     dl, 1
0x18000e4f1  lea     rcx, [rbp+57h+String]
0x18000e4f5  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000e4fa  xor     eax, eax
0x18000e4fc  mov     rcx, [rbp+57h+var_40]
0x18000e500  xor     rcx, rsp; StackCookie
0x18000e503  call    __security_check_cookie
0x18000e508  add     rsp, 88h
0x18000e50f  pop     r15
0x18000e511  pop     r14
0x18000e513  pop     r13
0x18000e515  pop     r12
0x18000e517  pop     rbx
0x18000e518  pop     rbp
0x18000e519  retn
```
