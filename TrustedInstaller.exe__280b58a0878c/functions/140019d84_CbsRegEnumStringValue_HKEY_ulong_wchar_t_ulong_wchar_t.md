# CbsRegEnumStringValue(HKEY__ *,ulong,wchar_t *,ulong,wchar_t * *)

- ea: `0x140019d84`
- end: `0x14001a0d7`
- name: `?CbsRegEnumStringValue@@YAJPEAUHKEY__@@KPEA_WKPEAPEA_W@Z`
- size: `851`
- prototype: `__int64 __fastcall(HKEY hKey, DWORD dwIndex, wchar_t *, __int64, wchar_t **)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x14000c3e0`

## callees

- `0x1400023e0`
- `0x1400054b0`
- `0x14000ee94`
- `0x140016a40`
- `0x140016bfc`
- `0x140016fb4`
- `0x1400184fc`
- `0x140019d84`
- `0x14001c7a8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x140019eca`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x14001a01b`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x140019eca`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x14001a01b`

## string_xrefs

- `0x140019f68`: `Registry value for {} is not a string type.`
- `0x14001a038`: `Failed to enum value after it already existed once.`

## pseudocode

```c
__int64 __fastcall CbsRegEnumStringValue(HKEY hKey, DWORD dwIndex, wchar_t *a3, __int64 a4, wchar_t **a5)
{
  unsigned int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // rdx
  __int64 v10; // rdx
  LSTATUS v11; // eax
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // rdx
  __int64 v15; // rdx
  __int64 v16; // rdi
  int v17; // eax
  wchar_t *v18; // rsi
  LSTATUS v19; // ebx
  __int64 v20; // rdx
  unsigned int v21; // eax
  int lpReserved; // [rsp+20h] [rbp-51h]
  unsigned int lpReserveda; // [rsp+20h] [rbp-51h]
  unsigned int v25[2]; // [rsp+40h] [rbp-31h] BYREF
  LPWSTR lpValueName[2]; // [rsp+50h] [rbp-21h] BYREF
  LPBYTE lpData; // [rsp+60h] [rbp-11h] BYREF
  DWORD cbData; // [rsp+68h] [rbp-9h] BYREF
  DWORD Type; // [rsp+6Ch] [rbp-5h] BYREF
  int v30[2]; // [rsp+70h] [rbp-1h] BYREF
  DWORD v31; // [rsp+78h] [rbp+7h] BYREF
  DWORD cchValueName; // [rsp+80h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+57h]

  lpValueName[0] = a3;
  v31 = 260;
  if ( !a3 )
  {
    v7 = -2147467261;
    LODWORD(lpData) = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No value name result specified");
      *(_QWORD *)v30 = &lpData;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v8,
        3,
        (__int64)": {}",
        (__int64)v30);
    }
    v9 = 793;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\base\\cbs\\util\\cbsreg.cpp",
      (const char *)v7,
      lpReserved);
    return v7;
  }
  if ( !a5 )
  {
    v7 = -2147467261;
    LODWORD(lpData) = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No value result specified");
      *(_QWORD *)v30 = &lpData;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v10,
        3,
        (__int64)": {}",
        (__int64)v30);
    }
    v9 = 794;
    goto LABEL_5;
  }
  *a3 = 0;
  Type = 0;
  cbData = 0;
  cchValueName = v31;
  v11 = RegEnumValueW(hKey, dwIndex, lpValueName[0], &cchValueName, 0, &Type, 0, &cbData);
  if ( v11 > 0 )
    v7 = (unsigned __int16)v11 | 0x80070000;
  else
    v7 = v11;
  if ( v11 != 259 )
  {
    if ( (v7 & 0x80000000) != 0 )
    {
      LODWORD(lpData) = v7;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to RegEnumValue.");
        *(_QWORD *)v25 = &lpData;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          v14,
          3,
          (__int64)": {}",
          (__int64)v25);
      }
      v9 = 810;
      goto LABEL_5;
    }
    if ( Type - 1 > 1 )
    {
      v7 = -2147024883;
      v30[0] = -2147024883;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (__int64)LogAdapter::g_Logger,
          v12,
          v13,
          (__int64)"Registry value for {} is not a string type.",
          (__int64)lpValueName);
        *(_QWORD *)v25 = v30;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          v15,
          3,
          (__int64)": {}",
          (__int64)v25);
      }
      v9 = 814;
      goto LABEL_5;
    }
    v16 = cbData >> 1;
    lpData = 0;
    v17 = SczAlloc(&lpData, (unsigned int)(v16 + 1));
    v7 = v17;
    if ( v17 >= 0 )
    {
      v18 = (wchar_t *)lpData;
      v19 = RegEnumValueW(hKey, dwIndex, lpValueName[0], &v31, 0, &Type, lpData, &cbData);
      if ( v19 )
      {
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to enum value after it already existed once.");
          if ( v19 > 0 )
            v21 = (unsigned __int16)v19 | 0x80070000;
          else
            v21 = v19;
          v30[0] = v21;
          *(_QWORD *)v25 = v30;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            v20,
            3,
            (__int64)": {0}",
            (__int64)v25);
        }
        v7 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x339,
               (unsigned int)"onecore\\base\\cbs\\util\\cbsreg.cpp",
               (const char *)(unsigned int)v19,
               lpReserveda);
      }
      else
      {
        v18[v16] = 0;
        v7 = 0;
        *a5 = v18;
        lpData = 0;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x333,
        (unsigned int)"onecore\\base\\cbs\\util\\cbsreg.cpp",
        (const char *)(unsigned int)v17,
        lpReserved);
    }
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpData);
  }
  return v7;
}

```

## disassembly

```asm
0x140019d84  push    rbp
0x140019d86  push    rbx
0x140019d87  push    rsi
0x140019d88  push    rdi
0x140019d89  push    r12
0x140019d8b  push    r14
0x140019d8d  push    r15
0x140019d8f  lea     rbp, [rsp-1Fh]
0x140019d94  sub     rsp, 90h
0x140019d9b  mov     rax, cs:__security_cookie
0x140019da2  xor     rax, rsp
0x140019da5  mov     [rbp+4Fh+var_38], rax
0x140019da9  mov     r14, [rbp+4Fh+arg_20]
0x140019dad  mov     r12d, edx
0x140019db0  mov     [rbp+4Fh+lpValueName], r8
0x140019db4  mov     r15, rcx
0x140019db7  mov     [rbp+4Fh+var_48], 104h
0x140019dbe  test    r8, r8
0x140019dc1  jnz     short loc_140019E30
0x140019dc3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140019dca  mov     ebx, 80004003h
0x140019dcf  mov     dword ptr [rbp+4Fh+var_60], ebx
0x140019dd2  test    rcx, rcx
0x140019dd5  jz      short loc_140019E13
0x140019dd7  lea     edi, [r8+3]
0x140019ddb  xor     edx, edx
0x140019ddd  mov     r8d, edi
0x140019de0  lea     r9, aNoValueNameRes; "No value name result specified"
0x140019de7  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140019dec  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140019df3  lea     rax, [rbp+4Fh+var_60]
0x140019df7  mov     qword ptr [rbp+4Fh+var_50], rax
0x140019dfb  lea     r9, asc_1400353E8; ": {}"
0x140019e02  lea     rax, [rbp+4Fh+var_50]
0x140019e06  mov     r8d, edi
0x140019e09  mov     [rsp+0C0h+lpReserved], rax; int
0x140019e0e  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140019e13  mov     edx, 319h; void *
0x140019e18  mov     rcx, [rbp+57h]; this
0x140019e1c  lea     r8, aOnecoreBaseCbs_5; "onecore\\base\\cbs\\util\\cbsreg.cpp"
0x140019e23  mov     r9d, ebx; char *
0x140019e26  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140019e2b  jmp     loc_14001A0B7
0x140019e30  test    r14, r14
0x140019e33  jnz     short loc_140019E8C
0x140019e35  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140019e3c  mov     ebx, 80004003h
0x140019e41  mov     dword ptr [rbp+4Fh+var_60], ebx
0x140019e44  test    rcx, rcx
0x140019e47  jz      short loc_140019E85
0x140019e49  lea     edi, [r14+3]
0x140019e4d  xor     edx, edx
0x140019e4f  mov     r8d, edi
0x140019e52  lea     r9, aNoValueResultS; "No value result specified"
0x140019e59  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140019e5e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140019e65  lea     rax, [rbp+4Fh+var_60]
0x140019e69  mov     qword ptr [rbp+4Fh+var_50], rax
0x140019e6d  lea     r9, asc_1400353E8; ": {}"
0x140019e74  lea     rax, [rbp+4Fh+var_50]
0x140019e78  mov     r8d, edi
0x140019e7b  mov     [rsp+0C0h+lpReserved], rax
0x140019e80  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140019e85  mov     edx, 31Ah; dwIndex
0x140019e8a  jmp     short loc_140019E18
0x140019e8c  xor     eax, eax
0x140019e8e  lea     r9, [rbp+4Fh+cchValueName]; lpcchValueName
0x140019e92  mov     [r8], ax
0x140019e96  mov     r8, [rbp+4Fh+lpValueName]; lpValueName
0x140019e9a  mov     [rbp+4Fh+Type], eax
0x140019e9d  mov     [rbp+4Fh+cbData], eax
0x140019ea0  mov     eax, [rbp+4Fh+var_48]
0x140019ea3  mov     [rbp+4Fh+cchValueName], eax
0x140019ea6  lea     rax, [rbp+4Fh+cbData]
0x140019eaa  mov     [rsp+0C0h+lpcbData], rax; lpcbData
0x140019eaf  lea     rax, [rbp+4Fh+Type]
0x140019eb3  mov     [rsp+0C0h+lpData], 0; lpData
0x140019ebc  mov     [rsp+0C0h+lpType], rax; lpType
0x140019ec1  mov     [rsp+0C0h+lpReserved], 0; int
0x140019eca  call    cs:__imp_RegEnumValueW
0x140019ed0  test    eax, eax
0x140019ed2  jg      short loc_140019ED8
0x140019ed4  mov     ebx, eax
0x140019ed6  jmp     short loc_140019EE1
0x140019ed8  movzx   ebx, ax
0x140019edb  or      ebx, 80070000h
0x140019ee1  cmp     eax, 103h
0x140019ee6  jz      loc_14001A0B7
0x140019eec  test    ebx, ebx
0x140019eee  jns     short loc_140019F46
0x140019ef0  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140019ef7  mov     dword ptr [rbp+4Fh+var_60], ebx
0x140019efa  test    rcx, rcx
0x140019efd  jz      short loc_140019F3C
0x140019eff  mov     edi, 3
0x140019f04  lea     r9, aFailedToRegenu; "Failed to RegEnumValue."
0x140019f0b  mov     r8d, edi
0x140019f0e  xor     edx, edx
0x140019f10  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140019f15  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140019f1c  lea     rax, [rbp+4Fh+var_60]
0x140019f20  mov     qword ptr [rbp+4Fh+var_80], rax
0x140019f24  lea     r9, asc_1400353E8; ": {}"
0x140019f2b  lea     rax, [rbp+4Fh+var_80]
0x140019f2f  mov     r8d, edi
0x140019f32  mov     [rsp+0C0h+lpReserved], rax
0x140019f37  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140019f3c  mov     edx, 32Ah
0x140019f41  jmp     loc_140019E18
0x140019f46  mov     eax, [rbp+4Fh+Type]
0x140019f49  dec     eax
0x140019f4b  cmp     eax, 1
0x140019f4e  jbe     short loc_140019FAD
0x140019f50  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140019f57  mov     ebx, 8007000Dh
0x140019f5c  mov     [rbp+4Fh+var_50], ebx
0x140019f5f  test    rcx, rcx
0x140019f62  jz      short loc_140019FA3
0x140019f64  lea     rax, [rbp+4Fh+lpValueName]
0x140019f68  lea     r9, aRegistryValueF; "Registry value for {} is not a string t"...
0x140019f6f  mov     [rsp+0C0h+lpReserved], rax
0x140019f74  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x140019f79  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140019f80  lea     rax, [rbp+4Fh+var_50]
0x140019f84  mov     qword ptr [rbp+4Fh+var_80], rax
0x140019f88  lea     r9, asc_1400353E8; ": {}"
0x140019f8f  lea     rax, [rbp+4Fh+var_80]
0x140019f93  mov     r8d, 3
0x140019f99  mov     [rsp+0C0h+lpReserved], rax
0x140019f9e  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140019fa3  mov     edx, 32Eh
0x140019fa8  jmp     loc_140019E18
0x140019fad  mov     edi, [rbp+4Fh+cbData]
0x140019fb0  lea     rcx, [rbp+4Fh+var_60]
0x140019fb4  shr     edi, 1
0x140019fb6  mov     [rbp+4Fh+var_60], 0
0x140019fbe  lea     edx, [rdi+1]
0x140019fc1  call    SczAlloc
0x140019fc6  mov     ebx, eax
0x140019fc8  test    eax, eax
0x140019fca  jns     short loc_140019FE9
0x140019fcc  mov     rcx, [rbp+57h]; this
0x140019fd0  lea     r8, aOnecoreBaseCbs_5; "onecore\\base\\cbs\\util\\cbsreg.cpp"
0x140019fd7  mov     r9d, eax; char *
0x140019fda  mov     edx, 333h; void *
0x140019fdf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140019fe4  jmp     loc_14001A0AE
0x140019fe9  mov     rsi, [rbp+4Fh+var_60]
0x140019fed  lea     rax, [rbp+4Fh+cbData]
0x140019ff1  mov     r8, [rbp+4Fh+lpValueName]; lpValueName
0x140019ff5  lea     r9, [rbp+4Fh+var_48]; lpcchValueName
0x140019ff9  mov     [rsp+0C0h+lpcbData], rax; lpcbData
0x140019ffe  mov     edx, r12d; dwIndex
0x14001a001  lea     rax, [rbp+4Fh+Type]
0x14001a005  mov     [rsp+0C0h+lpData], rsi; lpData
0x14001a00a  mov     [rsp+0C0h+lpType], rax; lpType
0x14001a00f  mov     rcx, r15; hKey
0x14001a012  mov     [rsp+0C0h+lpReserved], 0; lpReserved
0x14001a01b  call    cs:__imp_RegEnumValueW
0x14001a021  mov     ebx, eax
0x14001a023  test    eax, eax
0x14001a025  jz      short loc_14001A09F
0x14001a027  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001a02e  test    rcx, rcx
0x14001a031  jz      short loc_14001A083
0x14001a033  mov     edi, 3
0x14001a038  lea     r9, aFailedToEnumVa; "Failed to enum value after it already e"...
0x14001a03f  mov     r8d, edi
0x14001a042  xor     edx, edx
0x14001a044  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14001a049  test    ebx, ebx
0x14001a04b  jg      short loc_14001A051
0x14001a04d  mov     eax, ebx
0x14001a04f  jmp     short loc_14001A059
0x14001a051  movzx   eax, bx
0x14001a054  or      eax, 80070000h
0x14001a059  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001a060  lea     r9, a0; ": {0}"
0x14001a067  mov     [rbp+4Fh+var_50], eax
0x14001a06a  mov     r8d, edi
0x14001a06d  lea     rax, [rbp+4Fh+var_50]
0x14001a071  mov     qword ptr [rbp+4Fh+var_80], rax
0x14001a075  lea     rax, [rbp+4Fh+var_80]
0x14001a079  mov     [rsp+0C0h+lpReserved], rax; unsigned int
0x14001a07e  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001a083  mov     rcx, [rbp+57h]; this
0x14001a087  lea     r8, aOnecoreBaseCbs_5; "onecore\\base\\cbs\\util\\cbsreg.cpp"
0x14001a08e  mov     r9d, ebx; char *
0x14001a091  mov     edx, 339h; void *
0x14001a096  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x14001a09b  mov     ebx, eax
0x14001a09d  jmp     short loc_14001A0AE
0x14001a09f  xor     eax, eax
0x14001a0a1  mov     [rsi+rdi*2], ax
0x14001a0a5  xor     ebx, ebx
0x14001a0a7  mov     [r14], rsi
0x14001a0aa  mov     [rbp+4Fh+var_60], rax
0x14001a0ae  lea     rcx, [rbp+4Fh+var_60]
0x14001a0b2  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x14001a0b7  mov     eax, ebx
0x14001a0b9  mov     rcx, [rbp+4Fh+var_38]
0x14001a0bd  xor     rcx, rsp; StackCookie
0x14001a0c0  call    __security_check_cookie
0x14001a0c5  add     rsp, 90h
0x14001a0cc  pop     r15
0x14001a0ce  pop     r14
0x14001a0d0  pop     r12
0x14001a0d2  pop     rdi
0x14001a0d3  pop     rsi
0x14001a0d4  pop     rbx
0x14001a0d5  pop     rbp
0x14001a0d6  retn
```
