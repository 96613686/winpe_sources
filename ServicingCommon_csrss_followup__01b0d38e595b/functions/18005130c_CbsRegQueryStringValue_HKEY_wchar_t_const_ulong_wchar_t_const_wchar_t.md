# CbsRegQueryStringValue(HKEY__ *,wchar_t const *,ulong,wchar_t const *,wchar_t * *)

- ea: `0x18005130c`
- end: `0x1800517e2`
- name: `?CbsRegQueryStringValue@@YAJPEAUHKEY__@@PEB_WK1PEAPEA_W@Z`
- size: `1238`
- prototype: `int(HKEY, const wchar_t *, unsigned int, const wchar_t *, wchar_t **)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x180047da0`
- `0x180047e20`

## callees

- `0x180020440`
- `0x18002d2b0`
- `0x180046650`
- `0x180046bb4`
- `0x180046ca4`
- `0x1800473a8`
- `0x180047c5c`
- `0x18004c808`
- `0x18004f580`
- `0x180050adc`
- `0x18005126c`
- `0x18005130c`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x180051535`
- `ADVAPI32!RegQueryValueExW` at `0x180051646`
- `ADVAPI32!RegQueryValueExW` at `0x180051720`
- `ADVAPI32!RegQueryValueExW` at `0x180051535`
- `ADVAPI32!RegQueryValueExW` at `0x180051646`
- `ADVAPI32!RegQueryValueExW` at `0x180051720`

## string_xrefs

- `0x18005141d`: `Failed to open the registry root: n/a, key: {}.`
- `0x1800515d3`: `Failed initial query of value to get type, size, and value of registry value: {}`
- `0x18005167b`: `Failed to query value to get type and size of registry root: n/a, value: {}`
- `0x18005156d`: `Registry value is not a string type.`
- `0x180051742`: `Failed to query registry value: {}`

## pseudocode

```c
__int64 __fastcall CbsRegQueryStringValue(HKEY a1, const wchar_t *a2, __int64 a3, const wchar_t *a4, wchar_t **a5)
{
  const WCHAR *v5; // rax
  unsigned int v6; // ebx
  int v7; // edx
  HKEY v8; // r15
  LSTATUS v9; // eax
  int v10; // edx
  int v11; // r8d
  int v12; // ebx
  int v13; // edx
  unsigned int v14; // eax
  unsigned __int64 v15; // r9
  __int64 v16; // rdx
  LPBYTE v17; // rcx
  unsigned __int64 v18; // rbx
  int v19; // r12d
  int v20; // eax
  __int64 v21; // r9
  __int64 v22; // rdx
  int v23; // edi
  __int64 v24; // rdx
  int v25; // edx
  LSTATUS v26; // edi
  int v27; // r8d
  int v28; // edx
  int v29; // edx
  unsigned int v30; // eax
  int v31; // edx
  LSTATUS v32; // edi
  int v33; // r8d
  int v34; // edx
  unsigned int v35; // eax
  int v36; // edx
  LSTATUS v37; // edi
  int v38; // r8d
  int v39; // edx
  unsigned int v40; // eax
  unsigned int lpData; // [rsp+20h] [rbp-60h]
  unsigned int *v43; // [rsp+30h] [rbp-50h] BYREF
  unsigned int v44; // [rsp+38h] [rbp-48h] BYREF
  int *v45; // [rsp+40h] [rbp-40h] BYREF
  LPCWSTR lpValueName; // [rsp+48h] [rbp-38h] BYREF
  const wchar_t *v47; // [rsp+50h] [rbp-30h] BYREF
  DWORD cbData; // [rsp+58h] [rbp-28h] BYREF
  int v49; // [rsp+5Ch] [rbp-24h] BYREF
  unsigned int v50[2]; // [rsp+60h] [rbp-20h] BYREF
  DWORD Type; // [rsp+68h] [rbp-18h] BYREF
  HKEY v52; // [rsp+70h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  v5 = a4;
  v47 = a2;
  lpValueName = a4;
  if ( a5 )
  {
    v52 = 0;
    v8 = HKEY_LOCAL_MACHINE;
    if ( a2 )
    {
      v9 = CbsRegOpenKeyExW(a1, a2, a3, 0x20019u, &v52);
      v12 = v9;
      if ( v9 == 2 || v9 == 3 )
      {
        v6 = (unsigned __int16)v9 | 0x80070000;
LABEL_60:
        Windows::AutoGenericHandleBase<HKEY__ *,0,Windows::AutoGenericHandle<HKEY__ *,0,&void Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>>::Close(&v52);
        return v6;
      }
      if ( v9 )
      {
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            (_DWORD)LogAdapter::g_Logger,
            v10,
            v11,
            (unsigned int)"Failed to open the registry root: n/a, key: {}.",
            (__int64)&v47);
          if ( v12 > 0 )
            v14 = (unsigned __int16)v12 | 0x80070000;
          else
            v14 = v12;
          v49 = v14;
          *(_QWORD *)v50 = &v49;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v13,
            3,
            (unsigned int)": {0}",
            (__int64)v50);
        }
        v15 = (unsigned int)v12;
        v16 = 182;
LABEL_16:
        v6 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)v16,
               (unsigned int)"onecore\\base\\cbs\\util\\cbsreg.cpp",
               (const char *)v15,
               lpData);
        goto LABEL_60;
      }
      v8 = v52;
      v5 = lpValueName;
    }
    v17 = (LPBYTE)*a5;
    v18 = 0;
    v19 = 0;
    *(_QWORD *)v50 = 0;
    Type = 0;
    cbData = 0;
    if ( v17 )
    {
      v20 = SczSize(v17, v50);
      v6 = v20;
      if ( v20 < 0 )
      {
        v21 = (unsigned int)v20;
        v22 = 194;
LABEL_21:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v22,
          (unsigned int)"onecore\\base\\cbs\\util\\cbsreg.cpp",
          (const char *)v21,
          lpData);
        goto LABEL_60;
      }
      v18 = *(_QWORD *)v50;
      if ( *(_QWORD *)v50 >= 2u )
      {
        v23 = ULongLongToULong(2LL * *(_QWORD *)v50 - 4, &cbData);
        if ( v23 < 0 )
        {
          v24 = 199;
LABEL_25:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v24,
            (unsigned int)"onecore\\base\\cbs\\util\\cbsreg.cpp",
            (const char *)(unsigned int)v23,
            lpData);
          v6 = v23;
          goto LABEL_60;
        }
      }
      v26 = RegQueryValueExW(v8, lpValueName, 0, &Type, (LPBYTE)*a5, &cbData);
      if ( !v26 )
      {
        v19 = 1;
        goto LABEL_28;
      }
      if ( v26 != 234 )
      {
        if ( v26 != 2 )
        {
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<wchar_t const *>(
              (_DWORD)LogAdapter::g_Logger,
              v25,
              v27,
              (unsigned int)"Failed initial query of value to get type, size, and value of registry value: {}",
              (__int64)&lpValueName);
            if ( v26 > 0 )
              v30 = (unsigned __int16)v26 | 0x80070000;
            else
              v30 = v26;
            v49 = v30;
            v45 = &v49;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v29,
              3,
              (unsigned int)": {0}",
              (__int64)&v45);
          }
          v15 = (unsigned int)v26;
          v16 = 224;
          goto LABEL_16;
        }
LABEL_41:
        v6 = -2147024894;
        goto LABEL_60;
      }
    }
    else
    {
      v32 = RegQueryValueExW(v8, v5, 0, &Type, 0, &cbData);
      if ( v32 == 2 )
        goto LABEL_41;
      if ( v32 )
      {
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            (_DWORD)LogAdapter::g_Logger,
            v31,
            v33,
            (unsigned int)"Failed to query value to get type and size of registry root: n/a, value: {}",
            (__int64)&lpValueName);
          if ( v32 > 0 )
            v35 = (unsigned __int16)v32 | 0x80070000;
          else
            v35 = v32;
          v44 = v35;
          v43 = &v44;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v34,
            3,
            (unsigned int)": {0}",
            (__int64)&v43);
        }
        v15 = (unsigned int)v32;
        v16 = 240;
        goto LABEL_16;
      }
    }
LABEL_28:
    if ( Type - 1 > 1 )
    {
      v6 = -2147024883;
      v50[0] = -2147024883;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Registry value is not a string type.");
        v43 = v50;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v28,
          3,
          (unsigned int)": {}",
          (__int64)&v43);
      }
      v21 = 2147942413LL;
      v22 = 246;
      goto LABEL_21;
    }
    if ( !v19 )
    {
      v18 = ((unsigned __int64)cbData >> 1) + 2;
      v23 = SczAlloc(a5, v18);
      if ( v23 < 0 )
      {
        v24 = 255;
        goto LABEL_25;
      }
      v37 = RegQueryValueExW(v8, lpValueName, 0, &Type, (LPBYTE)*a5, &cbData);
      if ( v37 )
      {
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            (_DWORD)LogAdapter::g_Logger,
            v36,
            v38,
            (unsigned int)"Failed to query registry value: {}",
            (__int64)&lpValueName);
          if ( v37 > 0 )
            v40 = (unsigned __int16)v37 | 0x80070000;
          else
            v40 = v37;
          v50[0] = v40;
          v43 = v50;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v39,
            3,
            (unsigned int)": {0}",
            (__int64)&v43);
        }
        v15 = (unsigned int)v37;
        v16 = 266;
        goto LABEL_16;
      }
    }
    (*a5)[v18 - 2] = 0;
    (*a5)[v18 - 1] = 0;
    v6 = 0;
    goto LABEL_60;
  }
  v6 = -2147467261;
  v49 = -2147467261;
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No value result specified");
    *(_QWORD *)v50 = &v49;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (_DWORD)LogAdapter::g_Logger,
      v7,
      3,
      (unsigned int)": {}",
      (__int64)v50);
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xA7,
    (unsigned int)"onecore\\base\\cbs\\util\\cbsreg.cpp",
    (const char *)0x80004003LL,
    lpData);
  return v6;
}

```

## disassembly

```asm
0x18005130c  mov     [rsp-28h+arg_0], rbx
0x180051311  mov     [rsp-28h+arg_10], rsi
0x180051316  push    rbp
0x180051317  push    rdi
0x180051318  push    r12
0x18005131a  push    r14
0x18005131c  push    r15
0x18005131e  mov     rbp, rsp
0x180051321  sub     rsp, 80h
0x180051328  mov     rax, cs:__security_cookie
0x18005132f  xor     rax, rsp
0x180051332  mov     [rbp+var_8], rax
0x180051336  mov     r14, [rbp+arg_20]
0x18005133a  mov     rax, r9
0x18005133d  mov     [rbp+var_30], rdx
0x180051341  mov     [rbp+lpValueName], rax
0x180051345  test    r14, r14
0x180051348  jnz     short loc_1800513B7
0x18005134a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180051351  mov     ebx, 80004003h
0x180051356  mov     [rbp+var_24], ebx
0x180051359  test    rcx, rcx
0x18005135c  jz      short loc_18005139A
0x18005135e  lea     esi, [r14+3]
0x180051362  xor     edx, edx
0x180051364  mov     r8d, esi
0x180051367  lea     r9, aNoValueResultS; "No value result specified"
0x18005136e  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180051373  lea     rcx, [rbp+var_20]
0x180051377  mov     r8d, esi
0x18005137a  mov     [rsp+80h+lpData], rcx; int
0x18005137f  lea     rax, [rbp+var_24]
0x180051383  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18005138a  lea     r9, asc_1800AFAD8; ": {}"
0x180051391  mov     qword ptr [rbp+var_20], rax
0x180051395  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18005139a  mov     rcx, [rbp+28h]; this
0x18005139e  lea     r8, aOnecoreBaseCbs_2; "onecore\\base\\cbs\\util\\cbsreg.cpp"
0x1800513a5  mov     r9d, ebx; char *
0x1800513a8  mov     edx, 0A7h; void *
0x1800513ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800513b2  jmp     loc_1800517B7
0x1800513b7  mov     [rbp+var_10], 0
0x1800513bf  mov     esi, 3
0x1800513c4  mov     r15, 0FFFFFFFF80000002h
0x1800513cb  test    rdx, rdx
0x1800513ce  jz      loc_18005148F
0x1800513d4  lea     rax, [rbp+var_10]
0x1800513d8  mov     r9d, 20019h; unsigned int
0x1800513de  mov     [rsp+80h+lpData], rax; int
0x1800513e3  call    ?CbsRegOpenKeyExW@@YAKPEAUHKEY__@@PEB_WKKPEAPEAU1@@Z; CbsRegOpenKeyExW(HKEY__ *,wchar_t const *,ulong,ulong,HKEY__ * *)
0x1800513e8  mov     ebx, eax
0x1800513ea  cmp     eax, 2
0x1800513ed  jz      short loc_1800513FB
0x1800513ef  cmp     eax, esi
0x1800513f1  jnz     short loc_180051409
0x1800513f3  test    eax, eax
0x1800513f5  jle     loc_1800517AE
0x1800513fb  movzx   ebx, bx
0x1800513fe  or      ebx, 80070000h
0x180051404  jmp     loc_1800517AE
0x180051409  test    ebx, ebx
0x18005140b  jz      short loc_180051487
0x18005140d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180051414  test    rcx, rcx
0x180051417  jz      short loc_180051468
0x180051419  lea     rax, [rbp+var_30]
0x18005141d  lea     r9, aFailedToOpenTh; "Failed to open the registry root: n/a, "...
0x180051424  mov     [rsp+80h+lpData], rax
0x180051429  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x18005142e  test    ebx, ebx
0x180051430  jg      short loc_180051436
0x180051432  mov     eax, ebx
0x180051434  jmp     short loc_18005143E
0x180051436  movzx   eax, bx
0x180051439  or      eax, 80070000h
0x18005143e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180051445  lea     r9, a0; ": {0}"
0x18005144c  mov     [rbp+var_24], eax
0x18005144f  mov     r8d, esi
0x180051452  lea     rax, [rbp+var_24]
0x180051456  mov     qword ptr [rbp+var_20], rax
0x18005145a  lea     rax, [rbp+var_20]
0x18005145e  mov     [rsp+80h+lpData], rax; unsigned int
0x180051463  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180051468  mov     r9d, ebx; char *
0x18005146b  mov     edx, 0B6h; void *
0x180051470  mov     rcx, [rbp+28h]; this
0x180051474  lea     r8, aOnecoreBaseCbs_2; "onecore\\base\\cbs\\util\\cbsreg.cpp"
0x18005147b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180051480  mov     ebx, eax
0x180051482  jmp     loc_1800517AE
0x180051487  mov     r15, [rbp+var_10]
0x18005148b  mov     rax, [rbp+lpValueName]
0x18005148f  mov     rcx, [r14]
0x180051492  xor     ebx, ebx
0x180051494  xor     r12d, r12d
0x180051497  mov     qword ptr [rbp+var_20], rbx
0x18005149b  mov     [rbp+Type], ebx
0x18005149e  mov     [rbp+cbData], ebx
0x1800514a1  test    rcx, rcx
0x1800514a4  jz      loc_18005162B
0x1800514aa  lea     rdx, [rbp+var_20]
0x1800514ae  call    SczSize
0x1800514b3  mov     ebx, eax
0x1800514b5  test    eax, eax
0x1800514b7  jns     short loc_1800514D6
0x1800514b9  mov     r9d, eax; char *
0x1800514bc  mov     edx, 0C2h; void *
0x1800514c1  mov     rcx, [rbp+28h]; this
0x1800514c5  lea     r8, aOnecoreBaseCbs_2; "onecore\\base\\cbs\\util\\cbsreg.cpp"
0x1800514cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800514d1  jmp     loc_1800517AE
0x1800514d6  mov     rbx, qword ptr [rbp+var_20]
0x1800514da  cmp     rbx, 2
0x1800514de  jb      short loc_180051516
0x1800514e0  lea     rcx, ds:0FFFFFFFFFFFFFFFCh[rbx*2]; unsigned __int64
0x1800514e8  lea     rdx, [rbp+cbData]; unsigned int *
0x1800514ec  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1800514f1  mov     edi, eax
0x1800514f3  test    eax, eax
0x1800514f5  jns     short loc_180051516
0x1800514f7  mov     edx, 0C7h; void *
0x1800514fc  mov     rcx, [rbp+28h]; this
0x180051500  lea     r8, aOnecoreBaseCbs_2; "onecore\\base\\cbs\\util\\cbsreg.cpp"
0x180051507  mov     r9d, edi; char *
0x18005150a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005150f  mov     ebx, edi
0x180051511  jmp     loc_1800517AE
0x180051516  mov     rdx, [rbp+lpValueName]; lpValueName
0x18005151a  lea     rax, [rbp+cbData]
0x18005151e  mov     [rsp+80h+lpcbData], rax; lpcbData
0x180051523  lea     r9, [rbp+Type]; lpType
0x180051527  mov     rax, [r14]
0x18005152a  xor     r8d, r8d; lpReserved
0x18005152d  mov     rcx, r15; hKey
0x180051530  mov     [rsp+80h+lpData], rax; lpData
0x180051535  call    cs:__imp_RegQueryValueExW
0x18005153c  nop     dword ptr [rax+rax+00h]
0x180051541  mov     edi, eax
0x180051543  test    eax, eax
0x180051545  jnz     short loc_1800515B2
0x180051547  lea     r12d, [rax+1]
0x18005154b  mov     eax, [rbp+Type]
0x18005154e  dec     eax
0x180051550  cmp     eax, 1
0x180051553  jbe     loc_1800516D3
0x180051559  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180051560  mov     ebx, 8007000Dh
0x180051565  mov     [rbp+var_20], ebx
0x180051568  test    rcx, rcx
0x18005156b  jz      short loc_1800515A5
0x18005156d  lea     r9, aRegistryValueI; "Registry value is not a string type."
0x180051574  mov     r8d, esi
0x180051577  xor     edx, edx
0x180051579  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18005157e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180051585  lea     rax, [rbp+var_20]
0x180051589  mov     [rbp+var_50], rax
0x18005158d  lea     r9, asc_1800AFAD8; ": {}"
0x180051594  lea     rax, [rbp+var_50]
0x180051598  mov     r8d, esi
0x18005159b  mov     [rsp+80h+lpData], rax
0x1800515a0  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800515a5  mov     r9d, ebx
0x1800515a8  mov     edx, 0F6h
0x1800515ad  jmp     loc_1800514C1
0x1800515b2  cmp     edi, 0EAh
0x1800515b8  jz      short loc_18005154B
0x1800515ba  cmp     edi, 2
0x1800515bd  jz      loc_180051659
0x1800515c3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800515ca  test    rcx, rcx
0x1800515cd  jz      short loc_18005161E
0x1800515cf  lea     rax, [rbp+lpValueName]
0x1800515d3  lea     r9, aFailedInitialQ; "Failed initial query of value to get ty"...
0x1800515da  mov     [rsp+80h+lpData], rax
0x1800515df  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1800515e4  test    edi, edi
0x1800515e6  jg      short loc_1800515EC
0x1800515e8  mov     eax, edi
0x1800515ea  jmp     short loc_1800515F4
0x1800515ec  movzx   eax, di
0x1800515ef  or      eax, 80070000h
0x1800515f4  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800515fb  lea     r9, a0; ": {0}"
0x180051602  mov     [rbp+var_24], eax
0x180051605  mov     r8d, esi
0x180051608  lea     rax, [rbp+var_24]
0x18005160c  mov     [rbp+var_40], rax
0x180051610  lea     rax, [rbp+var_40]
0x180051614  mov     [rsp+80h+lpData], rax
0x180051619  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18005161e  mov     r9d, edi
0x180051621  mov     edx, 0E0h
0x180051626  jmp     loc_180051470
0x18005162b  lea     rcx, [rbp+cbData]
0x18005162f  xor     r8d, r8d; lpReserved
0x180051632  mov     [rsp+80h+lpcbData], rcx; lpcbData
0x180051637  lea     r9, [rbp+Type]; lpType
0x18005163b  mov     rcx, r15; hKey
0x18005163e  mov     [rsp+80h+lpData], rbx; lpData
0x180051643  mov     rdx, rax; lpValueName
0x180051646  call    cs:__imp_RegQueryValueExW
0x18005164d  nop     dword ptr [rax+rax+00h]
0x180051652  mov     edi, eax
0x180051654  cmp     eax, 2
0x180051657  jnz     short loc_180051663
0x180051659  mov     ebx, 80070002h
0x18005165e  jmp     loc_1800517AE
0x180051663  test    edi, edi
0x180051665  jz      loc_18005154B
0x18005166b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180051672  test    rcx, rcx
0x180051675  jz      short loc_1800516C6
0x180051677  lea     rax, [rbp+lpValueName]
0x18005167b  lea     r9, aFailedToQueryV; "Failed to query value to get type and s"...
0x180051682  mov     [rsp+80h+lpData], rax
0x180051687  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x18005168c  test    edi, edi
0x18005168e  jg      short loc_180051694
0x180051690  mov     eax, edi
0x180051692  jmp     short loc_18005169C
0x180051694  movzx   eax, di
0x180051697  or      eax, 80070000h
0x18005169c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800516a3  lea     r9, a0; ": {0}"
0x1800516aa  mov     [rbp+var_48], eax
0x1800516ad  mov     r8d, esi
0x1800516b0  lea     rax, [rbp+var_48]
0x1800516b4  mov     [rbp+var_50], rax
0x1800516b8  lea     rax, [rbp+var_50]
0x1800516bc  mov     [rsp+80h+lpData], rax
0x1800516c1  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800516c6  mov     r9d, edi
0x1800516c9  mov     edx, 0F0h
0x1800516ce  jmp     loc_180051470
0x1800516d3  test    r12d, r12d
0x1800516d6  jnz     loc_18005179A
0x1800516dc  mov     ebx, [rbp+cbData]
0x1800516df  mov     rcx, r14
0x1800516e2  shr     rbx, 1
0x1800516e5  add     rbx, 2
0x1800516e9  mov     rdx, rbx
0x1800516ec  call    SczAlloc
0x1800516f1  mov     edi, eax
0x1800516f3  test    eax, eax
0x1800516f5  jns     short loc_180051701
0x1800516f7  mov     edx, 0FFh
0x1800516fc  jmp     loc_1800514FC
0x180051701  mov     rdx, [rbp+lpValueName]; lpValueName
0x180051705  lea     rax, [rbp+cbData]
0x180051709  mov     [rsp+80h+lpcbData], rax; lpcbData
0x18005170e  lea     r9, [rbp+Type]; lpType
0x180051712  mov     rax, [r14]
0x180051715  xor     r8d, r8d; lpReserved
0x180051718  mov     rcx, r15; hKey
0x18005171b  mov     [rsp+80h+lpData], rax; lpData
0x180051720  call    cs:__imp_RegQueryValueExW
0x180051727  nop     dword ptr [rax+rax+00h]
0x18005172c  mov     edi, eax
0x18005172e  test    eax, eax
0x180051730  jz      short loc_18005179A
0x180051732  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180051739  test    rcx, rcx
0x18005173c  jz      short loc_18005178D
0x18005173e  lea     rax, [rbp+lpValueName]
0x180051742  lea     r9, aFailedToQueryR; "Failed to query registry value: {}"
0x180051749  mov     [rsp+80h+lpData], rax
0x18005174e  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x180051753  test    edi, edi
0x180051755  jg      short loc_18005175B
0x180051757  mov     eax, edi
0x180051759  jmp     short loc_180051763
0x18005175b  movzx   eax, di
0x18005175e  or      eax, 80070000h
0x180051763  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18005176a  lea     r9, a0; ": {0}"
0x180051771  mov     [rbp+var_20], eax
0x180051774  mov     r8d, esi
0x180051777  lea     rax, [rbp+var_20]
0x18005177b  mov     [rbp+var_50], rax
0x18005177f  lea     rax, [rbp+var_50]
0x180051783  mov     [rsp+80h+lpData], rax
0x180051788  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18005178d  mov     r9d, edi
0x180051790  mov     edx, 10Ah
0x180051795  jmp     loc_180051470
0x18005179a  mov     rcx, [r14]
0x18005179d  xor     eax, eax
0x18005179f  mov     [rcx+rbx*2-4], ax
0x1800517a4  mov     rcx, [r14]
0x1800517a7  mov     [rcx+rbx*2-2], ax
0x1800517ac  xor     ebx, ebx
0x1800517ae  lea     rcx, [rbp+var_10]
0x1800517b2  call    ?Close@?$AutoGenericHandleBase@PEAUHKEY__@@$0A@V?$AutoGenericHandle@PEAUHKEY__@@$0A@$1?CloseWithRegCloseKey@Detail@Windows@@YAXPEAU1@@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<HKEY__ *,0,Windows::AutoGenericHandle<HKEY__ *,0,&Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>>::Close(void)
0x1800517b7  mov     eax, ebx
0x1800517b9  mov     rcx, [rbp+var_8]
0x1800517bd  xor     rcx, rsp; StackCookie
0x1800517c0  call    __security_check_cookie
  ... truncated ...
```
