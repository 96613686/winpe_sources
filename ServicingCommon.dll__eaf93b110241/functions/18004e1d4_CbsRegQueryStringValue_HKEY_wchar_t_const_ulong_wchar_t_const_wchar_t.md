# CbsRegQueryStringValue(HKEY__ *,wchar_t const *,ulong,wchar_t const *,wchar_t * *)

- ea: `0x18004e1d4`
- end: `0x18004e6ac`
- name: `?CbsRegQueryStringValue@@YAJPEAUHKEY__@@PEB_WK1PEAPEA_W@Z`
- size: `1240`
- prototype: `int(HKEY, const wchar_t *, unsigned int, const wchar_t *, wchar_t **)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x180044c10`
- `0x180044c90`

## callees

- `0x18001e51c`
- `0x1800293a0`
- `0x18003d7d4`
- `0x180041a74`
- `0x180041de8`
- `0x180043c00`
- `0x180044274`
- `0x1800496e8`
- `0x18004c460`
- `0x18004d9ac`
- `0x18004e134`
- `0x18004e1d4`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x18004e3fd`
- `ADVAPI32!RegQueryValueExW` at `0x18004e510`
- `ADVAPI32!RegQueryValueExW` at `0x18004e5ea`
- `ADVAPI32!RegQueryValueExW` at `0x18004e3fd`
- `ADVAPI32!RegQueryValueExW` at `0x18004e510`
- `ADVAPI32!RegQueryValueExW` at `0x18004e5ea`

## string_xrefs

- `0x18004e2e5`: `Failed to open the registry root: n/a, key: {}.`
- `0x18004e49d`: `Failed initial query of value to get type, size, and value of registry value: {}`
- `0x18004e545`: `Failed to query value to get type and size of registry root: n/a, value: {}`
- `0x18004e42d`: `Registry value is not a string type.`
- `0x18004e60c`: `Failed to query registry value: {}`

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
  __int64 v15; // r9
  __int64 v16; // rdx
  LPBYTE v17; // rcx
  unsigned __int64 v18; // rbx
  int v19; // r12d
  int v20; // eax
  int v21; // edi
  __int64 v22; // rdx
  int v23; // edx
  LSTATUS v24; // edi
  int v25; // r8d
  int v26; // edx
  int v27; // edx
  unsigned int v28; // eax
  int v29; // edx
  LSTATUS v30; // edi
  int v31; // r8d
  int v32; // edx
  unsigned int v33; // eax
  int v34; // edx
  LSTATUS v35; // edi
  int v36; // r8d
  int v37; // edx
  unsigned int v38; // eax
  unsigned int lpData; // [rsp+20h] [rbp-60h]
  unsigned int v41[2]; // [rsp+30h] [rbp-50h] BYREF
  unsigned int *v42; // [rsp+38h] [rbp-48h] BYREF
  int *v43; // [rsp+40h] [rbp-40h] BYREF
  LPCWSTR lpValueName; // [rsp+48h] [rbp-38h] BYREF
  const wchar_t *v45; // [rsp+50h] [rbp-30h] BYREF
  DWORD cbData; // [rsp+58h] [rbp-28h] BYREF
  int v47; // [rsp+5Ch] [rbp-24h] BYREF
  DWORD Type; // [rsp+60h] [rbp-20h] BYREF
  HKEY v49; // [rsp+68h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  v5 = a4;
  v45 = a2;
  lpValueName = a4;
  if ( a5 )
  {
    v49 = 0;
    v8 = HKEY_LOCAL_MACHINE;
    if ( a2 )
    {
      v9 = CbsRegOpenKeyExW(a1, a2, a3, 0x20019u, &v49);
      v12 = v9;
      if ( v9 == 2 || v9 == 3 )
      {
        v6 = (unsigned __int16)v9 | 0x80070000;
LABEL_59:
        Windows::AutoGenericHandleBase<HKEY__ *,0,Windows::AutoGenericHandle<HKEY__ *,0,&void Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>>::Close(&v49);
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
            (__int64)&v45);
          if ( v12 > 0 )
            v14 = (unsigned __int16)v12 | 0x80070000;
          else
            v14 = v12;
          v47 = v14;
          *(_QWORD *)v41 = &v47;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v13,
            3,
            (unsigned int)": {0}",
            (__int64)v41);
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
        goto LABEL_59;
      }
      v8 = v49;
      v5 = lpValueName;
    }
    v17 = (LPBYTE)*a5;
    v18 = 0;
    v19 = 0;
    *(_QWORD *)v41 = 0;
    Type = 0;
    cbData = 0;
    if ( v17 )
    {
      v20 = SczSize(v17, v41);
      v6 = v20;
      if ( v20 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xC2,
          (unsigned int)"onecore\\base\\cbs\\util\\cbsreg.cpp",
          (const char *)(unsigned int)v20,
          lpData);
        goto LABEL_59;
      }
      v18 = *(_QWORD *)v41;
      if ( *(_QWORD *)v41 >= 2u )
      {
        v21 = ULongLongToULong(2LL * *(_QWORD *)v41 - 4, &cbData);
        if ( v21 < 0 )
        {
          v22 = 199;
LABEL_24:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v22,
            (unsigned int)"onecore\\base\\cbs\\util\\cbsreg.cpp",
            (const char *)(unsigned int)v21,
            lpData);
          v6 = v21;
          goto LABEL_59;
        }
      }
      v24 = RegQueryValueExW(v8, lpValueName, 0, &Type, (LPBYTE)*a5, &cbData);
      if ( !v24 )
      {
        v19 = 1;
        goto LABEL_27;
      }
      if ( v24 != 234 )
      {
        if ( v24 != 2 )
        {
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<wchar_t const *>(
              (_DWORD)LogAdapter::g_Logger,
              v23,
              v25,
              (unsigned int)"Failed initial query of value to get type, size, and value of registry value: {}",
              (__int64)&lpValueName);
            if ( v24 > 0 )
              v28 = (unsigned __int16)v24 | 0x80070000;
            else
              v28 = v24;
            v47 = v28;
            v43 = &v47;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v27,
              3,
              (unsigned int)": {0}",
              (__int64)&v43);
          }
          v15 = (unsigned int)v24;
          v16 = 224;
          goto LABEL_16;
        }
LABEL_40:
        v6 = -2147024894;
        goto LABEL_59;
      }
    }
    else
    {
      v30 = RegQueryValueExW(v8, v5, 0, &Type, 0, &cbData);
      if ( v30 == 2 )
        goto LABEL_40;
      if ( v30 )
      {
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            (_DWORD)LogAdapter::g_Logger,
            v29,
            v31,
            (unsigned int)"Failed to query value to get type and size of registry root: n/a, value: {}",
            (__int64)&lpValueName);
          if ( v30 > 0 )
            v33 = (unsigned __int16)v30 | 0x80070000;
          else
            v33 = v30;
          v41[0] = v33;
          v42 = v41;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v32,
            3,
            (unsigned int)": {0}",
            (__int64)&v42);
        }
        v15 = (unsigned int)v30;
        v16 = 240;
        goto LABEL_16;
      }
    }
LABEL_27:
    if ( Type - 1 > 1 )
    {
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Registry value is not a string type.");
        v42 = v41;
        v41[0] = -2147024883;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v26,
          3,
          (unsigned int)": {0}",
          (__int64)&v42);
      }
      v15 = 13;
      v16 = 246;
      goto LABEL_16;
    }
    if ( !v19 )
    {
      v18 = ((unsigned __int64)cbData >> 1) + 2;
      v21 = SczAlloc(a5, v18);
      if ( v21 < 0 )
      {
        v22 = 255;
        goto LABEL_24;
      }
      v35 = RegQueryValueExW(v8, lpValueName, 0, &Type, (LPBYTE)*a5, &cbData);
      if ( v35 )
      {
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            (_DWORD)LogAdapter::g_Logger,
            v34,
            v36,
            (unsigned int)"Failed to query registry value: {}",
            (__int64)&lpValueName);
          if ( v35 > 0 )
            v38 = (unsigned __int16)v35 | 0x80070000;
          else
            v38 = v35;
          v41[0] = v38;
          v42 = v41;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v37,
            3,
            (unsigned int)": {0}",
            (__int64)&v42);
        }
        v15 = (unsigned int)v35;
        v16 = 266;
        goto LABEL_16;
      }
    }
    (*a5)[v18 - 2] = 0;
    (*a5)[v18 - 1] = 0;
    v6 = 0;
    goto LABEL_59;
  }
  v6 = -2147467261;
  v47 = -2147467261;
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No value result specified");
    *(_QWORD *)v41 = &v47;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (_DWORD)LogAdapter::g_Logger,
      v7,
      3,
      (unsigned int)": {}",
      (__int64)v41);
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
0x18004e1d4  mov     [rsp-28h+arg_0], rbx
0x18004e1d9  mov     [rsp-28h+arg_10], rsi
0x18004e1de  push    rbp
0x18004e1df  push    rdi
0x18004e1e0  push    r12
0x18004e1e2  push    r14
0x18004e1e4  push    r15
0x18004e1e6  mov     rbp, rsp
0x18004e1e9  sub     rsp, 80h
0x18004e1f0  mov     rax, cs:__security_cookie
0x18004e1f7  xor     rax, rsp
0x18004e1fa  mov     [rbp+var_10], rax
0x18004e1fe  mov     r14, [rbp+arg_20]
0x18004e202  mov     rax, r9
0x18004e205  mov     [rbp+var_30], rdx
0x18004e209  mov     [rbp+lpValueName], rax
0x18004e20d  test    r14, r14
0x18004e210  jnz     short loc_18004E27F
0x18004e212  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004e219  mov     ebx, 80004003h
0x18004e21e  mov     [rbp+var_24], ebx
0x18004e221  test    rcx, rcx
0x18004e224  jz      short loc_18004E262
0x18004e226  lea     esi, [r14+3]
0x18004e22a  xor     edx, edx
0x18004e22c  mov     r8d, esi
0x18004e22f  lea     r9, aNoValueResultS; "No value result specified"
0x18004e236  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18004e23b  lea     rcx, [rbp+var_50]
0x18004e23f  mov     r8d, esi
0x18004e242  mov     [rsp+80h+lpData], rcx; int
0x18004e247  lea     rax, [rbp+var_24]
0x18004e24b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004e252  lea     r9, asc_1800AFB70; ": {}"
0x18004e259  mov     qword ptr [rbp+var_50], rax
0x18004e25d  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18004e262  mov     rcx, [rbp+28h]; this
0x18004e266  lea     r8, aOnecoreBaseCbs_4; "onecore\\base\\cbs\\util\\cbsreg.cpp"
0x18004e26d  mov     r9d, ebx; char *
0x18004e270  mov     edx, 0A7h; void *
0x18004e275  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e27a  jmp     loc_18004E681
0x18004e27f  mov     [rbp+var_18], 0
0x18004e287  mov     esi, 3
0x18004e28c  mov     r15, 0FFFFFFFF80000002h
0x18004e293  test    rdx, rdx
0x18004e296  jz      loc_18004E357
0x18004e29c  lea     rax, [rbp+var_18]
0x18004e2a0  mov     r9d, 20019h; unsigned int
0x18004e2a6  mov     [rsp+80h+lpData], rax; int
0x18004e2ab  call    ?CbsRegOpenKeyExW@@YAKPEAUHKEY__@@PEB_WKKPEAPEAU1@@Z; CbsRegOpenKeyExW(HKEY__ *,wchar_t const *,ulong,ulong,HKEY__ * *)
0x18004e2b0  mov     ebx, eax
0x18004e2b2  cmp     eax, 2
0x18004e2b5  jz      short loc_18004E2C3
0x18004e2b7  cmp     eax, esi
0x18004e2b9  jnz     short loc_18004E2D1
0x18004e2bb  test    eax, eax
0x18004e2bd  jle     loc_18004E678
0x18004e2c3  movzx   ebx, bx
0x18004e2c6  or      ebx, 80070000h
0x18004e2cc  jmp     loc_18004E678
0x18004e2d1  test    ebx, ebx
0x18004e2d3  jz      short loc_18004E34F
0x18004e2d5  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004e2dc  test    rcx, rcx
0x18004e2df  jz      short loc_18004E330
0x18004e2e1  lea     rax, [rbp+var_30]
0x18004e2e5  lea     r9, aFailedToOpenTh; "Failed to open the registry root: n/a, "...
0x18004e2ec  mov     [rsp+80h+lpData], rax
0x18004e2f1  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x18004e2f6  test    ebx, ebx
0x18004e2f8  jg      short loc_18004E2FE
0x18004e2fa  mov     eax, ebx
0x18004e2fc  jmp     short loc_18004E306
0x18004e2fe  movzx   eax, bx
0x18004e301  or      eax, 80070000h
0x18004e306  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004e30d  lea     r9, a0; ": {0}"
0x18004e314  mov     [rbp+var_24], eax
0x18004e317  mov     r8d, esi
0x18004e31a  lea     rax, [rbp+var_24]
0x18004e31e  mov     qword ptr [rbp+var_50], rax
0x18004e322  lea     rax, [rbp+var_50]
0x18004e326  mov     [rsp+80h+lpData], rax; unsigned int
0x18004e32b  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18004e330  mov     r9d, ebx; char *
0x18004e333  mov     edx, 0B6h; void *
0x18004e338  mov     rcx, [rbp+28h]; this
0x18004e33c  lea     r8, aOnecoreBaseCbs_4; "onecore\\base\\cbs\\util\\cbsreg.cpp"
0x18004e343  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004e348  mov     ebx, eax
0x18004e34a  jmp     loc_18004E678
0x18004e34f  mov     r15, [rbp+var_18]
0x18004e353  mov     rax, [rbp+lpValueName]
0x18004e357  mov     rcx, [r14]
0x18004e35a  xor     ebx, ebx
0x18004e35c  xor     r12d, r12d
0x18004e35f  mov     qword ptr [rbp+var_50], rbx
0x18004e363  mov     [rbp+Type], ebx
0x18004e366  mov     [rbp+cbData], ebx
0x18004e369  test    rcx, rcx
0x18004e36c  jz      loc_18004E4F5
0x18004e372  lea     rdx, [rbp+var_50]
0x18004e376  call    SczSize
0x18004e37b  mov     ebx, eax
0x18004e37d  test    eax, eax
0x18004e37f  jns     short loc_18004E39E
0x18004e381  mov     rcx, [rbp+28h]; this
0x18004e385  lea     r8, aOnecoreBaseCbs_4; "onecore\\base\\cbs\\util\\cbsreg.cpp"
0x18004e38c  mov     r9d, eax; char *
0x18004e38f  mov     edx, 0C2h; void *
0x18004e394  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e399  jmp     loc_18004E678
0x18004e39e  mov     rbx, qword ptr [rbp+var_50]
0x18004e3a2  cmp     rbx, 2
0x18004e3a6  jb      short loc_18004E3DE
0x18004e3a8  lea     rcx, ds:0FFFFFFFFFFFFFFFCh[rbx*2]; unsigned __int64
0x18004e3b0  lea     rdx, [rbp+cbData]; unsigned int *
0x18004e3b4  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18004e3b9  mov     edi, eax
0x18004e3bb  test    eax, eax
0x18004e3bd  jns     short loc_18004E3DE
0x18004e3bf  mov     edx, 0C7h; void *
0x18004e3c4  mov     rcx, [rbp+28h]; this
0x18004e3c8  lea     r8, aOnecoreBaseCbs_4; "onecore\\base\\cbs\\util\\cbsreg.cpp"
0x18004e3cf  mov     r9d, edi; char *
0x18004e3d2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e3d7  mov     ebx, edi
0x18004e3d9  jmp     loc_18004E678
0x18004e3de  mov     rdx, [rbp+lpValueName]; lpValueName
0x18004e3e2  lea     rax, [rbp+cbData]
0x18004e3e6  mov     [rsp+80h+lpcbData], rax; lpcbData
0x18004e3eb  lea     r9, [rbp+Type]; lpType
0x18004e3ef  mov     rax, [r14]
0x18004e3f2  xor     r8d, r8d; lpReserved
0x18004e3f5  mov     rcx, r15; hKey
0x18004e3f8  mov     [rsp+80h+lpData], rax; lpData
0x18004e3fd  call    cs:__imp_RegQueryValueExW
0x18004e404  nop     dword ptr [rax+rax+00h]
0x18004e409  mov     edi, eax
0x18004e40b  test    eax, eax
0x18004e40d  jnz     short loc_18004E47C
0x18004e40f  lea     r12d, [rax+1]
0x18004e413  mov     eax, [rbp+Type]
0x18004e416  dec     eax
0x18004e418  cmp     eax, 1
0x18004e41b  jbe     loc_18004E59D
0x18004e421  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004e428  test    rcx, rcx
0x18004e42b  jz      short loc_18004E46C
0x18004e42d  lea     r9, aRegistryValueI; "Registry value is not a string type."
0x18004e434  mov     r8d, esi
0x18004e437  xor     edx, edx
0x18004e439  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18004e43e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004e445  lea     rax, [rbp+var_50]
0x18004e449  mov     [rbp+var_48], rax
0x18004e44d  lea     r9, a0; ": {0}"
0x18004e454  lea     rax, [rbp+var_48]
0x18004e458  mov     [rbp+var_50], 8007000Dh
0x18004e45f  mov     r8d, esi
0x18004e462  mov     [rsp+80h+lpData], rax
0x18004e467  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18004e46c  mov     r9d, 0Dh
0x18004e472  mov     edx, 0F6h
0x18004e477  jmp     loc_18004E338
0x18004e47c  cmp     edi, 0EAh
0x18004e482  jz      short loc_18004E413
0x18004e484  cmp     edi, 2
0x18004e487  jz      loc_18004E523
0x18004e48d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004e494  test    rcx, rcx
0x18004e497  jz      short loc_18004E4E8
0x18004e499  lea     rax, [rbp+lpValueName]
0x18004e49d  lea     r9, aFailedInitialQ; "Failed initial query of value to get ty"...
0x18004e4a4  mov     [rsp+80h+lpData], rax
0x18004e4a9  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x18004e4ae  test    edi, edi
0x18004e4b0  jg      short loc_18004E4B6
0x18004e4b2  mov     eax, edi
0x18004e4b4  jmp     short loc_18004E4BE
0x18004e4b6  movzx   eax, di
0x18004e4b9  or      eax, 80070000h
0x18004e4be  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004e4c5  lea     r9, a0; ": {0}"
0x18004e4cc  mov     [rbp+var_24], eax
0x18004e4cf  mov     r8d, esi
0x18004e4d2  lea     rax, [rbp+var_24]
0x18004e4d6  mov     [rbp+var_40], rax
0x18004e4da  lea     rax, [rbp+var_40]
0x18004e4de  mov     [rsp+80h+lpData], rax
0x18004e4e3  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18004e4e8  mov     r9d, edi
0x18004e4eb  mov     edx, 0E0h
0x18004e4f0  jmp     loc_18004E338
0x18004e4f5  lea     rcx, [rbp+cbData]
0x18004e4f9  xor     r8d, r8d; lpReserved
0x18004e4fc  mov     [rsp+80h+lpcbData], rcx; lpcbData
0x18004e501  lea     r9, [rbp+Type]; lpType
0x18004e505  mov     rcx, r15; hKey
0x18004e508  mov     [rsp+80h+lpData], rbx; lpData
0x18004e50d  mov     rdx, rax; lpValueName
0x18004e510  call    cs:__imp_RegQueryValueExW
0x18004e517  nop     dword ptr [rax+rax+00h]
0x18004e51c  mov     edi, eax
0x18004e51e  cmp     eax, 2
0x18004e521  jnz     short loc_18004E52D
0x18004e523  mov     ebx, 80070002h
0x18004e528  jmp     loc_18004E678
0x18004e52d  test    edi, edi
0x18004e52f  jz      loc_18004E413
0x18004e535  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004e53c  test    rcx, rcx
0x18004e53f  jz      short loc_18004E590
0x18004e541  lea     rax, [rbp+lpValueName]
0x18004e545  lea     r9, aFailedToQueryV; "Failed to query value to get type and s"...
0x18004e54c  mov     [rsp+80h+lpData], rax
0x18004e551  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x18004e556  test    edi, edi
0x18004e558  jg      short loc_18004E55E
0x18004e55a  mov     eax, edi
0x18004e55c  jmp     short loc_18004E566
0x18004e55e  movzx   eax, di
0x18004e561  or      eax, 80070000h
0x18004e566  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004e56d  lea     r9, a0; ": {0}"
0x18004e574  mov     [rbp+var_50], eax
0x18004e577  mov     r8d, esi
0x18004e57a  lea     rax, [rbp+var_50]
0x18004e57e  mov     [rbp+var_48], rax
0x18004e582  lea     rax, [rbp+var_48]
0x18004e586  mov     [rsp+80h+lpData], rax
0x18004e58b  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18004e590  mov     r9d, edi
0x18004e593  mov     edx, 0F0h
0x18004e598  jmp     loc_18004E338
0x18004e59d  test    r12d, r12d
0x18004e5a0  jnz     loc_18004E664
0x18004e5a6  mov     ebx, [rbp+cbData]
0x18004e5a9  mov     rcx, r14
0x18004e5ac  shr     rbx, 1
0x18004e5af  add     rbx, 2
0x18004e5b3  mov     rdx, rbx
0x18004e5b6  call    SczAlloc
0x18004e5bb  mov     edi, eax
0x18004e5bd  test    eax, eax
0x18004e5bf  jns     short loc_18004E5CB
0x18004e5c1  mov     edx, 0FFh
0x18004e5c6  jmp     loc_18004E3C4
0x18004e5cb  mov     rdx, [rbp+lpValueName]; lpValueName
0x18004e5cf  lea     rax, [rbp+cbData]
0x18004e5d3  mov     [rsp+80h+lpcbData], rax; lpcbData
0x18004e5d8  lea     r9, [rbp+Type]; lpType
0x18004e5dc  mov     rax, [r14]
0x18004e5df  xor     r8d, r8d; lpReserved
0x18004e5e2  mov     rcx, r15; hKey
0x18004e5e5  mov     [rsp+80h+lpData], rax; lpData
0x18004e5ea  call    cs:__imp_RegQueryValueExW
0x18004e5f1  nop     dword ptr [rax+rax+00h]
0x18004e5f6  mov     edi, eax
0x18004e5f8  test    eax, eax
0x18004e5fa  jz      short loc_18004E664
0x18004e5fc  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004e603  test    rcx, rcx
0x18004e606  jz      short loc_18004E657
0x18004e608  lea     rax, [rbp+lpValueName]
0x18004e60c  lea     r9, aFailedToQueryR; "Failed to query registry value: {}"
0x18004e613  mov     [rsp+80h+lpData], rax
0x18004e618  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x18004e61d  test    edi, edi
0x18004e61f  jg      short loc_18004E625
0x18004e621  mov     eax, edi
0x18004e623  jmp     short loc_18004E62D
0x18004e625  movzx   eax, di
0x18004e628  or      eax, 80070000h
0x18004e62d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004e634  lea     r9, a0; ": {0}"
0x18004e63b  mov     [rbp+var_50], eax
0x18004e63e  mov     r8d, esi
0x18004e641  lea     rax, [rbp+var_50]
0x18004e645  mov     [rbp+var_48], rax
0x18004e649  lea     rax, [rbp+var_48]
0x18004e64d  mov     [rsp+80h+lpData], rax
0x18004e652  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18004e657  mov     r9d, edi
0x18004e65a  mov     edx, 10Ah
0x18004e65f  jmp     loc_18004E338
0x18004e664  mov     rcx, [r14]
0x18004e667  xor     eax, eax
0x18004e669  mov     [rcx+rbx*2-4], ax
0x18004e66e  mov     rcx, [r14]
0x18004e671  mov     [rcx+rbx*2-2], ax
0x18004e676  xor     ebx, ebx
0x18004e678  lea     rcx, [rbp+var_18]
0x18004e67c  call    ?Close@?$AutoGenericHandleBase@PEAUHKEY__@@$0A@V?$AutoGenericHandle@PEAUHKEY__@@$0A@$1?CloseWithRegCloseKey@Detail@Windows@@YAXPEAU1@@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<HKEY__ *,0,Windows::AutoGenericHandle<HKEY__ *,0,&Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>>::Close(void)
0x18004e681  mov     eax, ebx
0x18004e683  mov     rcx, [rbp+var_10]
0x18004e687  xor     rcx, rsp; StackCookie
0x18004e68a  call    __security_check_cookie
0x18004e68f  lea     r11, [rsp+80h+var_s0]
  ... truncated ...
```
