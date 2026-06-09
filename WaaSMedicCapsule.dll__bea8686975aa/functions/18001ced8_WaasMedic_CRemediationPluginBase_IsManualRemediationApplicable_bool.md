# WaasMedic::CRemediationPluginBase::IsManualRemediationApplicable(bool &)

- ea: `0x18001ced8`
- end: `0x18001d418`
- name: `?IsManualRemediationApplicable@CRemediationPluginBase@WaasMedic@@IEAAJAEA_N@Z`
- size: `1344`
- prototype: `__int64 __fastcall(WaasMedic::CRemediationPluginBase *__hidden this, bool *)`
- caller_count: `17`
- callee_count: `11`
- tags: `loader_planting, installer_update`

## callers

- `0x18000c150`
- `0x18001cae0`
- `0x180038020`
- `0x18003a650`
- `0x18003e940`
- `0x180040f00`
- `0x180042e10`
- `0x180045370`
- `0x18004b2b0`
- `0x18004d7c0`
- `0x18004e660`
- `0x18004f1c0`
- `0x18004fa50`
- `0x180050b60`
- `0x1800514d0`
- `0x180053240`
- `0x180054fd0`

## callees

- `0x180003bb0`
- `0x1800070cc`
- `0x180007590`
- `0x180009a54`
- `0x18001ced8`
- `0x18001d47c`
- `0x18002543c`
- `0x180030890`
- `0x1800309a0`
- `0x180030f54`
- `0x180064010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001d108`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001d108`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001d358`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001d358`
- `OLEAUT32!__imp_VariantInit` at `0x18001d0b6`
- `OLEAUT32!__imp_VariantInit` at `0x18001d15a`
- `OLEAUT32!__imp_VariantInit` at `0x18001d206`
- `OLEAUT32!__imp_VariantInit` at `0x18001d0b6`
- `OLEAUT32!__imp_VariantInit` at `0x18001d15a`
- `OLEAUT32!__imp_VariantInit` at `0x18001d206`
- `OLEAUT32!__imp_VariantClear` at `0x18001d142`
- `OLEAUT32!__imp_VariantClear` at `0x18001d19e`
- `OLEAUT32!__imp_VariantClear` at `0x18001d1c6`
- `OLEAUT32!__imp_VariantClear` at `0x18001d254`
- `OLEAUT32!__imp_VariantClear` at `0x18001d39b`
- `OLEAUT32!__imp_VariantClear` at `0x18001d3a7`
- `OLEAUT32!__imp_VariantClear` at `0x18001d402`
- `OLEAUT32!__imp_VariantClear` at `0x18001d142`
- `OLEAUT32!__imp_VariantClear` at `0x18001d19e`
- `OLEAUT32!__imp_VariantClear` at `0x18001d1c6`
- `OLEAUT32!__imp_VariantClear` at `0x18001d254`
- `OLEAUT32!__imp_VariantClear` at `0x18001d39b`
- `OLEAUT32!__imp_VariantClear` at `0x18001d3a7`
- `OLEAUT32!__imp_VariantClear` at `0x18001d402`

## string_xrefs

- `0x18001d084`: `onecore\enduser\waasmedic\lib\plugins\remediationpluginbase.cpp`
- `0x18001d129`: `onecore\enduser\waasmedic\lib\plugins\remediationpluginbase.cpp`
- `0x18001d243`: `onecore\enduser\waasmedic\lib\plugins\remediationpluginbase.cpp`
- `0x18001d013`: `MaxManualRemediationAttempts`
- `0x18001d0c9`: `PluginManualCampaignId`
- `0x18001d3e4`: `PluginManualCampaignId`
- `0x18001d16c`: `PluginManualRunCount`
- `0x18001d1a9`: `PluginManualRunCount`
- `0x18001d385`: `Plugin %s manual remediation is not applicable because the last run time has not yet elapsed.`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall WaasMedic::CRemediationPluginBase::IsManualRemediationApplicable(
        WaasMedic::CRemediationPluginBase *this,
        bool *a2)
{
  __int64 v4; // rbx
  __int64 (__fastcall *v5)(__int64, _BYTE *, _BYTE *, __int128 *); // rdi
  __int64 v6; // rdx
  __int64 v7; // r15
  __int64 v8; // r8
  int v9; // edi
  __int64 v10; // rdx
  __int64 v11; // rbx
  __int64 (__fastcall *v12)(__int64, _BYTE *, _BYTE *, _DWORD *); // rdi
  __int64 v13; // rdx
  __int64 v14; // r8
  int v15; // eax
  __int128 *v16; // rdx
  int v17; // eax
  __int64 v18; // rdx
  int v19; // eax
  unsigned int v20; // eax
  int v21; // eax
  __int64 v22; // rdx
  unsigned __int64 v23; // r9
  __int64 v24; // rbx
  __int64 (__fastcall *v25)(__int64, _OWORD *, _OWORD *, _DWORD *); // rdi
  __int64 v26; // rdx
  int v28; // [rsp+20h] [rbp-E0h]
  bool v29; // [rsp+30h] [rbp-D0h] BYREF
  VARIANTARG pvarg; // [rsp+38h] [rbp-C8h] BYREF
  struct _FILETIME v31; // [rsp+50h] [rbp-B0h] BYREF
  _DWORD v32[2]; // [rsp+58h] [rbp-A8h] BYREF
  char v33; // [rsp+60h] [rbp-A0h]
  _DWORD v34[2]; // [rsp+68h] [rbp-98h] BYREF
  char v35; // [rsp+70h] [rbp-90h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v37[32]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v38[32]; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v39; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v40; // [rsp+D0h] [rbp-30h]
  unsigned __int64 v41; // [rsp+D8h] [rbp-28h]
  int v42; // [rsp+E0h] [rbp-20h]
  char v43; // [rsp+E4h] [rbp-1Ch]
  _OWORD v44[2]; // [rsp+E8h] [rbp-18h] BYREF
  _OWORD v45[2]; // [rsp+108h] [rbp+8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  *a2 = 0;
  v39 = 0;
  v40 = 0;
  v41 = 7;
  LOWORD(v39) = 0;
  v43 = 1;
  v42 = 1;
  v4 = *((_QWORD *)this + 13);
  v5 = *(__int64 (__fastcall **)(__int64, _BYTE *, _BYTE *, __int128 *))(*(_QWORD *)v4 + 16LL);
  memset(v37, 0, sizeof(v37));
  std::wstring::_Construct<1,unsigned short const *>(v37, L"ManualRemediationCampaignId", 27);
  v6 = *((_QWORD *)this + 14);
  memset(v38, 0, sizeof(v38));
  v7 = -1;
  v8 = -1;
  do
    ++v8;
  while ( *(_WORD *)(v6 + 2 * v8) );
  std::wstring::_Construct<1,unsigned short const *>(v38, v6, v8);
  v9 = v5(v4, v38, v37, &v39);
  std::wstring::~wstring(v38);
  std::wstring::~wstring(v37);
  if ( v9 >= 0 )
  {
    v33 = 0;
    v32[0] = 0;
    v32[1] = 2;
    v11 = *((_QWORD *)this + 13);
    v12 = *(__int64 (__fastcall **)(__int64, _BYTE *, _BYTE *, _DWORD *))(*(_QWORD *)v11 + 8LL);
    memset(v37, 0, sizeof(v37));
    std::wstring::_Construct<1,unsigned short const *>(v37, L"MaxManualRemediationAttempts", 28);
    v13 = *((_QWORD *)this + 14);
    memset(v38, 0, sizeof(v38));
    v14 = -1;
    do
      ++v14;
    while ( *(_WORD *)(v13 + 2 * v14) );
    std::wstring::_Construct<1,unsigned short const *>(v38, v13, v14);
    v9 = v12(v11, v38, v37, v32);
    std::wstring::~wstring(v38);
    std::wstring::~wstring(v37);
    if ( v9 < 0 )
    {
      v10 = 665;
      goto LABEL_10;
    }
    if ( !v40 || !v32[0] )
    {
LABEL_48:
      std::wstring::~wstring(&v39);
      return 0;
    }
    VariantInit(&pvarg);
    v15 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const wchar_t *, VARIANTARG *))(**((_QWORD **)this + 12) + 16LL))(
            *((_QWORD *)this + 12),
            *((_QWORD *)this + 14),
            L"PluginManualCampaignId",
            &pvarg);
    if ( v15 < 0 )
    {
      LogLevelW(
        2u,
        L"Failed to retrieve %s from state provider! hr = 0x%08x",
        L"PluginManualCampaignId",
        (unsigned int)v15);
    }
    else
    {
      if ( pvarg.vt != 8 )
      {
        if ( !pvarg.vt )
        {
          v17 = WaasMedic::CRemediationPluginBase::ResetManualPluginCampaign(this, &v39);
          v9 = v17;
          if ( v17 < 0 )
          {
            v18 = 713;
            goto LABEL_20;
          }
          *a2 = 1;
        }
LABEL_32:
        if ( !*a2 )
          goto LABEL_47;
        goto LABEL_33;
      }
      v16 = &v39;
      if ( v41 > 7 )
        v16 = (__int128 *)v39;
      if ( (unsigned int)_o__wcsicmp(pvarg.llVal, v16) )
      {
        v17 = WaasMedic::CRemediationPluginBase::ResetManualPluginCampaign(this, &v39);
        v9 = v17;
        if ( v17 < 0 )
        {
          v18 = 684;
LABEL_20:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v18,
            (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\remediationpluginbase.cpp",
            (const char *)(unsigned int)v17,
            v28);
LABEL_21:
          VariantClear(&pvarg);
          goto LABEL_51;
        }
        *a2 = 1;
LABEL_33:
        VariantInit((VARIANTARG *)v37);
        v31 = 0;
        v21 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const char *, _BYTE *))(**((_QWORD **)this + 12) + 16LL))(
                *((_QWORD *)this + 12),
                *((_QWORD *)this + 14),
                L"LastRemediationRunTime",
                v37);
        v9 = v21;
        if ( v21 < 0 )
        {
          v22 = 728;
LABEL_35:
          v23 = (unsigned int)v21;
LABEL_36:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v22,
            (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\remediationpluginbase.cpp",
            (const char *)v23,
            v28);
          VariantClear((VARIANTARG *)v37);
          goto LABEL_21;
        }
        if ( *(_WORD *)v37 == 8 )
        {
          v21 = WaasMedic::TimeHelper::StringToFileTime(*(const unsigned __int16 **)&v37[8], &v31);
          v9 = v21;
          if ( v21 < 0 )
          {
            v22 = 731;
            goto LABEL_35;
          }
          v35 = 0;
          v34[0] = 0;
          v34[1] = 2;
          v24 = *((_QWORD *)this + 13);
          v25 = *(__int64 (__fastcall **)(__int64, _OWORD *, _OWORD *, _DWORD *))(*(_QWORD *)v24 + 8LL);
          memset(v45, 0, sizeof(v45));
          std::wstring::_Construct<1,unsigned short const *>(v45, L"ManualRemediationIntervalInHours", 32);
          v26 = *((_QWORD *)this + 14);
          memset(v44, 0, sizeof(v44));
          do
            ++v7;
          while ( *(_WORD *)(v26 + 2 * v7) );
          std::wstring::_Construct<1,unsigned short const *>(v44, v26, v7);
          v9 = v25(v24, v44, v45, v34);
          std::wstring::~wstring(v44);
          std::wstring::~wstring(v45);
          if ( v9 < 0 )
          {
            v23 = (unsigned int)v9;
            v22 = 734;
            goto LABEL_36;
          }
          WaasMedic::TimeHelper::AddDelayToFileTime(&v31, 36000000000LL * v34[0], 1);
          SystemTimeAsFileTime = 0;
          GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
          v29 = 0;
          WaasMedic::TimeHelper::TimeDiff(&v31, &SystemTimeAsFileTime, &v29);
          if ( !v29 )
          {
            *a2 = 0;
            LogLevelW(
              4u,
              L"Plugin %s manual remediation is not applicable because the last run time has not yet elapsed.",
              *((_QWORD *)this + 14));
          }
        }
        VariantClear((VARIANTARG *)v37);
LABEL_47:
        VariantClear(&pvarg);
        goto LABEL_48;
      }
      VariantInit((VARIANTARG *)v38);
      v19 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const wchar_t *, _BYTE *))(**((_QWORD **)this + 12) + 16LL))(
              *((_QWORD *)this + 12),
              *((_QWORD *)this + 14),
              L"PluginManualRunCount",
              v38);
      if ( v19 >= 0 )
      {
        v20 = 0;
        if ( *(_WORD *)v38 == 19 )
          v20 = *(_DWORD *)&v38[8];
        *a2 = v20 < v32[0];
        VariantClear((VARIANTARG *)v38);
        goto LABEL_32;
      }
      LogLevelW(
        2u,
        L"Failed to retrieve %s from state provider! hr = 0x%08x",
        L"PluginManualRunCount",
        (unsigned int)v19);
      VariantClear((VARIANTARG *)v38);
    }
    VariantClear(&pvarg);
    v9 = 0;
    goto LABEL_51;
  }
  if ( v9 == -2089484279 )
    goto LABEL_48;
  v10 = 661;
LABEL_10:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v10,
    (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\remediationpluginbase.cpp",
    (const char *)(unsigned int)v9,
    v28);
LABEL_51:
  std::wstring::~wstring(&v39);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001ced8  mov     [rsp-8+arg_10], rbx
0x18001cedd  mov     [rsp-8+arg_18], rsi
0x18001cee2  push    rbp
0x18001cee3  push    rdi
0x18001cee4  push    r12
0x18001cee6  push    r14
0x18001cee8  push    r15
0x18001ceea  lea     rbp, [rsp-30h]
0x18001ceef  sub     rsp, 130h
0x18001cef6  mov     rax, cs:__security_cookie
0x18001cefd  xor     rax, rsp
0x18001cf00  mov     [rbp+50h+var_28], rax
0x18001cf04  mov     r14, rdx
0x18001cf07  mov     rsi, rcx
0x18001cf0a  xor     r12d, r12d
0x18001cf0d  mov     [rdx], r12b
0x18001cf10  xorps   xmm0, xmm0
0x18001cf13  movups  [rbp+50h+var_90], xmm0
0x18001cf17  mov     [rbp+50h+var_80], r12
0x18001cf1b  mov     [rbp+50h+var_78], 7
0x18001cf23  mov     word ptr [rbp+50h+var_90], r12w
0x18001cf28  mov     [rbp+50h+var_6C], 1
0x18001cf2c  mov     [rbp+50h+var_70], 1
0x18001cf33  mov     rbx, [rcx+68h]
0x18001cf37  mov     rax, [rbx]
0x18001cf3a  mov     rdi, [rax+10h]
0x18001cf3e  movups  xmmword ptr [rbp+50h+var_D0], xmm0
0x18001cf42  xorps   xmm1, xmm1
0x18001cf45  movdqu  xmmword ptr [rbp+50h+var_D0+10h], xmm1
0x18001cf4a  lea     r8d, [r12+1Bh]
0x18001cf4f  lea     rdx, aManualremediat; "ManualRemediationCampaignId"
0x18001cf56  lea     rcx, [rbp+50h+var_D0]
0x18001cf5a  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001cf5f  nop
0x18001cf60  mov     rdx, [rsi+70h]
0x18001cf64  xorps   xmm0, xmm0
0x18001cf67  movups  xmmword ptr [rbp+50h+var_B0], xmm0
0x18001cf6b  xorps   xmm1, xmm1
0x18001cf6e  movdqu  xmmword ptr [rbp+50h+var_B0+10h], xmm1
0x18001cf73  or      r15, 0FFFFFFFFFFFFFFFFh
0x18001cf77  mov     r8, r15
0x18001cf7a  inc     r8
0x18001cf7d  cmp     [rdx+r8*2], r12w
0x18001cf82  jnz     short loc_18001CF7A
0x18001cf84  lea     rcx, [rbp+50h+var_B0]
0x18001cf88  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001cf8d  nop
0x18001cf8e  lea     r9, [rbp+50h+var_90]
0x18001cf92  lea     r8, [rbp+50h+var_D0]
0x18001cf96  lea     rdx, [rbp+50h+var_B0]
0x18001cf9a  mov     rcx, rbx
0x18001cf9d  mov     rax, rdi
0x18001cfa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cfa5  mov     edi, eax
0x18001cfa7  mov     ebx, eax
0x18001cfa9  shr     ebx, 1Fh
0x18001cfac  lea     rcx, [rbp+50h+var_B0]; void *
0x18001cfb0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001cfb5  nop
0x18001cfb6  lea     rcx, [rbp+50h+var_D0]; void *
0x18001cfba  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001cfbf  test    bl, bl
0x18001cfc1  jz      short loc_18001CFE1
0x18001cfc3  cmp     edi, 83750009h
0x18001cfc9  jz      loc_18001D3AE
0x18001cfcf  test    edi, edi
0x18001cfd1  jns     loc_18001D40B
0x18001cfd7  mov     edx, 295h
0x18001cfdc  jmp     loc_18001D084
0x18001cfe1  mov     [rsp+150h+var_F0], r12b
0x18001cfe6  mov     [rsp+150h+var_F8], r12d
0x18001cfeb  mov     [rsp+150h+var_F4], 2
0x18001cff3  mov     rbx, [rsi+68h]
0x18001cff7  mov     rax, [rbx]
0x18001cffa  mov     rdi, [rax+8]
0x18001cffe  xorps   xmm0, xmm0
0x18001d001  movups  xmmword ptr [rbp+50h+var_D0], xmm0
0x18001d005  xorps   xmm1, xmm1
0x18001d008  movdqu  xmmword ptr [rbp+50h+var_D0+10h], xmm1
0x18001d00d  mov     r8d, 1Ch
0x18001d013  lea     rdx, aMaxmanualremed; "MaxManualRemediationAttempts"
0x18001d01a  lea     rcx, [rbp+50h+var_D0]
0x18001d01e  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001d023  nop
0x18001d024  mov     rdx, [rsi+70h]
0x18001d028  xorps   xmm0, xmm0
0x18001d02b  movups  xmmword ptr [rbp+50h+var_B0], xmm0
0x18001d02f  xorps   xmm1, xmm1
0x18001d032  movdqu  xmmword ptr [rbp+50h+var_B0+10h], xmm1
0x18001d037  mov     r8, r15
0x18001d03a  inc     r8
0x18001d03d  cmp     [rdx+r8*2], r12w
0x18001d042  jnz     short loc_18001D03A
0x18001d044  lea     rcx, [rbp+50h+var_B0]
0x18001d048  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001d04d  nop
0x18001d04e  lea     r9, [rsp+150h+var_F8]
0x18001d053  lea     r8, [rbp+50h+var_D0]
0x18001d057  lea     rdx, [rbp+50h+var_B0]
0x18001d05b  mov     rcx, rbx
0x18001d05e  mov     rax, rdi
0x18001d061  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d066  mov     edi, eax
0x18001d068  lea     rcx, [rbp+50h+var_B0]; void *
0x18001d06c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001d071  nop
0x18001d072  lea     rcx, [rbp+50h+var_D0]; void *
0x18001d076  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001d07b  test    edi, edi
0x18001d07d  jns     short loc_18001D09C
0x18001d07f  mov     edx, 299h; void *
0x18001d084  lea     r8, aOnecoreEnduser_9; "onecore\\enduser\\waasmedic\\lib\\plugi"...
0x18001d08b  mov     r9d, edi; char *
0x18001d08e  mov     rcx, [rbp+58h]; this
0x18001d092  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d097  jmp     loc_18001D40B
0x18001d09c  cmp     [rbp+50h+var_80], r12
0x18001d0a0  jz      loc_18001D3AE
0x18001d0a6  cmp     [rsp+150h+var_F8], r12d
0x18001d0ab  jz      loc_18001D3AE
0x18001d0b1  lea     rcx, [rsp+150h+pvarg]; pvarg
0x18001d0b6  call    cs:__imp_VariantInit
0x18001d0bc  nop
0x18001d0bd  mov     rcx, [rsi+60h]
0x18001d0c1  mov     rax, [rcx]
0x18001d0c4  lea     r9, [rsp+150h+pvarg]
0x18001d0c9  lea     r8, aPluginmanualca; "PluginManualCampaignId"
0x18001d0d0  mov     rdx, [rsi+70h]
0x18001d0d4  mov     rax, [rax+10h]
0x18001d0d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d0dd  test    eax, eax
0x18001d0df  js      loc_18001D3E1
0x18001d0e5  mov     ebx, 8
0x18001d0ea  cmp     bx, word ptr [rsp+150h+pvarg]
0x18001d0ef  jnz     loc_18001D1D1
0x18001d0f5  lea     rdx, [rbp+50h+var_90]
0x18001d0f9  cmp     [rbp+50h+var_78], 7
0x18001d0fe  cmova   rdx, qword ptr [rbp+50h+var_90]
0x18001d103  mov     rcx, qword ptr [rsp+150h+pvarg+8]
0x18001d108  call    cs:__imp__o__wcsicmp
0x18001d10e  test    eax, eax
0x18001d110  jz      short loc_18001D156
0x18001d112  lea     rdx, [rbp+50h+var_90]
0x18001d116  mov     rcx, rsi
0x18001d119  call    ?ResetManualPluginCampaign@CRemediationPluginBase@WaasMedic@@AEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; WaasMedic::CRemediationPluginBase::ResetManualPluginCampaign(std::wstring const &)
0x18001d11e  mov     edi, eax
0x18001d120  test    eax, eax
0x18001d122  jns     short loc_18001D14D
0x18001d124  mov     edx, 2ACh; void *
0x18001d129  lea     r8, aOnecoreEnduser_9; "onecore\\enduser\\waasmedic\\lib\\plugi"...
0x18001d130  mov     r9d, eax; char *
0x18001d133  mov     rcx, [rbp+58h]; this
0x18001d137  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d13c  nop
0x18001d13d  lea     rcx, [rsp+150h+pvarg]; pvarg
0x18001d142  call    cs:__imp_VariantClear
0x18001d148  jmp     loc_18001D40B
0x18001d14d  mov     byte ptr [r14], 1
0x18001d151  jmp     loc_18001D202
0x18001d156  lea     rcx, [rbp+50h+var_B0]; pvarg
0x18001d15a  call    cs:__imp_VariantInit
0x18001d160  nop
0x18001d161  mov     rcx, [rsi+60h]
0x18001d165  mov     rax, [rcx]
0x18001d168  lea     r9, [rbp+50h+var_B0]
0x18001d16c  lea     r8, aPluginmanualru; "PluginManualRunCount"
0x18001d173  mov     rdx, [rsi+70h]
0x18001d177  mov     rax, [rax+10h]
0x18001d17b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d180  test    eax, eax
0x18001d182  js      short loc_18001D1A6
0x18001d184  mov     eax, r12d
0x18001d187  cmp     word ptr [rbp+50h+var_B0], 13h
0x18001d18c  cmovz   eax, dword ptr [rbp+50h+var_B0+8]
0x18001d190  cmp     eax, [rsp+150h+var_F8]
0x18001d194  setb    al
0x18001d197  mov     [r14], al
0x18001d19a  lea     rcx, [rbp+50h+var_B0]; pvarg
0x18001d19e  call    cs:__imp_VariantClear
0x18001d1a4  jmp     short loc_18001D1F9
0x18001d1a6  mov     r9d, eax
0x18001d1a9  lea     r8, aPluginmanualru; "PluginManualRunCount"
0x18001d1b0  lea     rdx, aFailedToRetrie; "Failed to retrieve %s from state provid"...
0x18001d1b7  mov     ecx, 2; unsigned __int8
0x18001d1bc  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18001d1c1  nop
0x18001d1c2  lea     rcx, [rbp+50h+var_B0]; pvarg
0x18001d1c6  call    cs:__imp_VariantClear
0x18001d1cc  jmp     loc_18001D3FD
0x18001d1d1  cmp     r12w, word ptr [rsp+150h+pvarg]
0x18001d1d7  jnz     short loc_18001D1F9
0x18001d1d9  lea     rdx, [rbp+50h+var_90]
0x18001d1dd  mov     rcx, rsi
0x18001d1e0  call    ?ResetManualPluginCampaign@CRemediationPluginBase@WaasMedic@@AEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; WaasMedic::CRemediationPluginBase::ResetManualPluginCampaign(std::wstring const &)
0x18001d1e5  mov     edi, eax
0x18001d1e7  test    eax, eax
0x18001d1e9  jns     short loc_18001D1F5
0x18001d1eb  mov     edx, 2C9h
0x18001d1f0  jmp     loc_18001D129
0x18001d1f5  mov     byte ptr [r14], 1
0x18001d1f9  cmp     [r14], r12b
0x18001d1fc  jz      loc_18001D3A2
0x18001d202  lea     rcx, [rbp+50h+var_D0]; pvarg
0x18001d206  call    cs:__imp_VariantInit
0x18001d20c  nop
0x18001d20d  mov     qword ptr [rsp+150h+var_100.dwLowDateTime], r12
0x18001d212  mov     rcx, [rsi+60h]
0x18001d216  mov     rax, [rcx]
0x18001d219  lea     r9, [rbp+50h+var_D0]
0x18001d21d  lea     r8, aLastremediatio; "LastRemediationRunTime"
0x18001d224  mov     rdx, [rsi+70h]
0x18001d228  mov     rax, [rax+10h]
0x18001d22c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d231  mov     edi, eax
0x18001d233  test    eax, eax
0x18001d235  jns     short loc_18001D25F
0x18001d237  mov     edx, 2D8h; void *
0x18001d23c  mov     r9d, eax; char *
0x18001d23f  mov     rcx, [rbp+58h]; this
0x18001d243  lea     r8, aOnecoreEnduser_9; "onecore\\enduser\\waasmedic\\lib\\plugi"...
0x18001d24a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d24f  nop
0x18001d250  lea     rcx, [rbp+50h+var_D0]; pvarg
0x18001d254  call    cs:__imp_VariantClear
0x18001d25a  jmp     loc_18001D13D
0x18001d25f  cmp     word ptr [rbp+50h+var_D0], bx
0x18001d263  jnz     loc_18001D397
0x18001d269  lea     rdx, [rsp+150h+var_100]; struct _FILETIME *
0x18001d26e  mov     rcx, qword ptr [rbp+50h+var_D0+8]; unsigned __int16 *
0x18001d272  call    ?StringToFileTime@TimeHelper@WaasMedic@@SAJPEBGPEAU_FILETIME@@@Z; WaasMedic::TimeHelper::StringToFileTime(ushort const *,_FILETIME *)
0x18001d277  mov     edi, eax
0x18001d279  test    eax, eax
0x18001d27b  jns     short loc_18001D284
0x18001d27d  mov     edx, 2DBh
0x18001d282  jmp     short loc_18001D23C
0x18001d284  mov     [rsp+150h+var_E0], r12b
0x18001d289  mov     [rsp+150h+var_E8], r12d
0x18001d28e  mov     [rsp+150h+var_E4], 2
0x18001d296  mov     rbx, [rsi+68h]
0x18001d29a  mov     rax, [rbx]
0x18001d29d  mov     rdi, [rax+8]
0x18001d2a1  xorps   xmm0, xmm0
0x18001d2a4  movups  [rbp+50h+var_48], xmm0
0x18001d2a8  xorps   xmm1, xmm1
0x18001d2ab  movdqu  [rbp+50h+var_38], xmm1
0x18001d2b0  mov     r8d, 20h ; ' '
0x18001d2b6  lea     rdx, aManualremediat_0; "ManualRemediationIntervalInHours"
0x18001d2bd  lea     rcx, [rbp+50h+var_48]
0x18001d2c1  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001d2c6  nop
0x18001d2c7  mov     rdx, [rsi+70h]
0x18001d2cb  xorps   xmm0, xmm0
0x18001d2ce  movups  [rbp+50h+var_68], xmm0
0x18001d2d2  xorps   xmm1, xmm1
0x18001d2d5  movdqu  [rbp+50h+var_58], xmm1
0x18001d2da  inc     r15
0x18001d2dd  cmp     [rdx+r15*2], r12w
0x18001d2e2  jnz     short loc_18001D2DA
0x18001d2e4  mov     r8, r15
0x18001d2e7  lea     rcx, [rbp+50h+var_68]
0x18001d2eb  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001d2f0  nop
0x18001d2f1  lea     r9, [rsp+150h+var_E8]
0x18001d2f6  lea     r8, [rbp+50h+var_48]
0x18001d2fa  lea     rdx, [rbp+50h+var_68]
0x18001d2fe  mov     rcx, rbx
0x18001d301  mov     rax, rdi
0x18001d304  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d309  mov     edi, eax
0x18001d30b  lea     rcx, [rbp+50h+var_68]; void *
0x18001d30f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001d314  nop
0x18001d315  lea     rcx, [rbp+50h+var_48]; void *
0x18001d319  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001d31e  test    edi, edi
0x18001d320  jns     short loc_18001D32F
0x18001d322  mov     r9d, edi
0x18001d325  mov     edx, 2DEh
0x18001d32a  jmp     loc_18001D23F
0x18001d32f  mov     edx, [rsp+150h+var_E8]
0x18001d333  mov     rax, 861C46800h
0x18001d33d  imul    rdx, rax; unsigned __int64
0x18001d341  mov     r8b, 1; bool
0x18001d344  lea     rcx, [rsp+150h+var_100]; struct _FILETIME *
0x18001d349  call    ?AddDelayToFileTime@TimeHelper@WaasMedic@@SAXAEAU_FILETIME@@_K_N@Z; WaasMedic::TimeHelper::AddDelayToFileTime(_FILETIME &,unsigned __int64,bool)
0x18001d34e  mov     qword ptr [rsp+150h+SystemTimeAsFileTime.dwLowDateTime], r12
0x18001d353  lea     rcx, [rsp+150h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001d358  call    cs:__imp_GetSystemTimeAsFileTime
0x18001d35e  mov     [rsp+150h+var_120], r12b
0x18001d363  lea     r8, [rsp+150h+var_120]; bool *
0x18001d368  lea     rdx, [rsp+150h+SystemTimeAsFileTime]; struct _FILETIME *
0x18001d36d  lea     rcx, [rsp+150h+var_100]; struct _FILETIME *
0x18001d372  call    ?TimeDiff@TimeHelper@WaasMedic@@SA_KAEBU_FILETIME@@0AEA_N@Z; WaasMedic::TimeHelper::TimeDiff(_FILETIME const &,_FILETIME const &,bool &)
0x18001d377  cmp     [rsp+150h+var_120], r12b
0x18001d37c  jnz     short loc_18001D397
0x18001d37e  mov     [r14], r12b
0x18001d381  mov     r8, [rsi+70h]
0x18001d385  lea     rdx, aPluginSManualR; "Plugin %s manual remediation is not app"...
0x18001d38c  mov     ecx, 4; unsigned __int8
0x18001d391  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
  ... truncated ...
```
