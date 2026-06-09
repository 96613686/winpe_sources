# CbsRegQueryStringValue(HKEY__ *,wchar_t const *,ulong,wchar_t const *,wchar_t * *)

- ea: `0x14001a7e4`
- end: `0x14001acb5`
- name: `?CbsRegQueryStringValue@@YAJPEAUHKEY__@@PEB_WK1PEAPEA_W@Z`
- size: `1233`
- prototype: `__int64 __fastcall(HKEY, const wchar_t *, __int64, const wchar_t *, wchar_t **)`
- caller_count: `3`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140014334`
- `0x1400185b0`
- `0x140018630`

## callees

- `0x1400023e0`
- `0x1400054b0`
- `0x140006e98`
- `0x140007630`
- `0x140016a40`
- `0x140016bfc`
- `0x140016fb4`
- `0x1400184fc`
- `0x14001a0e0`
- `0x14001a7e4`
- `0x14001b23c`
- `0x14001c7a8`
- `0x14001e050`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14001aa19`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14001ab26`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14001abfa`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14001aa19`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14001ab26`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14001abfa`

## string_xrefs

- `0x14001a901`: `Failed to open the registry root: n/a, key: {}.`
- `0x14001aab3`: `Failed initial query of value to get type, size, and value of registry value: {}`
- `0x14001ab55`: `Failed to query value to get type and size of registry root: n/a, value: {}`
- `0x14001aa43`: `Registry value is not a string type.`
- `0x14001ac16`: `Failed to query registry value: {}`

## pseudocode

```c
__int64 __fastcall CbsRegQueryStringValue(HKEY a1, const wchar_t *a2, __int64 a3, const wchar_t *a4, wchar_t **a5)
{
  const WCHAR *v5; // rax
  unsigned int v6; // ebx
  int v7; // edx
  __int64 v8; // r15
  HKEY *InitPointer; // rax
  unsigned int v10; // r8d
  unsigned int v11; // eax
  int v12; // edx
  int v13; // r8d
  int v14; // ebx
  int v15; // edx
  unsigned int v16; // eax
  __int64 v17; // r9
  __int64 v18; // rdx
  LPBYTE v19; // rcx
  unsigned __int64 v20; // rbx
  int v21; // r12d
  int v22; // eax
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
  unsigned int v43[2]; // [rsp+30h] [rbp-50h] BYREF
  unsigned int *v44; // [rsp+38h] [rbp-48h] BYREF
  int *v45; // [rsp+40h] [rbp-40h] BYREF
  LPCWSTR lpValueName; // [rsp+48h] [rbp-38h] BYREF
  LPCWSTR lpSubKey; // [rsp+50h] [rbp-30h] BYREF
  DWORD cbData; // [rsp+58h] [rbp-28h] BYREF
  int v49; // [rsp+5Ch] [rbp-24h] BYREF
  DWORD Type; // [rsp+60h] [rbp-20h] BYREF
  __int64 v51; // [rsp+68h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  v5 = a4;
  lpSubKey = a2;
  lpValueName = a4;
  if ( a5 )
  {
    v51 = 0;
    v8 = -2147483646;
    if ( a2 )
    {
      InitPointer = (HKEY *)Windows::AutoComPtr<IClassFactory>::GetInitPointer(&v51);
      v11 = CbsRegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, v10, 0x20019u, InitPointer);
      v14 = v11;
      if ( v11 == 2 || v11 == 3 )
      {
        v6 = (unsigned __int16)v11 | 0x80070000;
LABEL_59:
        Windows::AutoGenericHandleBase<HKEY__ *,0,Windows::AutoGenericHandle<HKEY__ *,0,&void Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>>::Close(&v51);
        return v6;
      }
      if ( v11 )
      {
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            (_DWORD)LogAdapter::g_Logger,
            v12,
            v13,
            (unsigned int)"Failed to open the registry root: n/a, key: {}.",
            (__int64)&lpSubKey);
          if ( v14 > 0 )
            v16 = (unsigned __int16)v14 | 0x80070000;
          else
            v16 = v14;
          v49 = v16;
          *(_QWORD *)v43 = &v49;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v15,
            3,
            (unsigned int)": {0}",
            (__int64)v43);
        }
        v17 = (unsigned int)v14;
        v18 = 182;
LABEL_16:
        v6 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)v18,
               (unsigned int)"onecore\\base\\cbs\\util\\cbsreg.cpp",
               (const char *)v17,
               lpData);
        goto LABEL_59;
      }
      v8 = v51;
      v5 = lpValueName;
    }
    v19 = (LPBYTE)*a5;
    v20 = 0;
    v21 = 0;
    *(_QWORD *)v43 = 0;
    Type = 0;
    cbData = 0;
    if ( v19 )
    {
      v22 = SczSize(v19, v43);
      v6 = v22;
      if ( v22 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xC2,
          (unsigned int)"onecore\\base\\cbs\\util\\cbsreg.cpp",
          (const char *)(unsigned int)v22,
          lpData);
        goto LABEL_59;
      }
      v20 = *(_QWORD *)v43;
      if ( *(_QWORD *)v43 >= 2u )
      {
        v23 = ULongLongToULong(2LL * *(_QWORD *)v43 - 4, &cbData);
        if ( v23 < 0 )
        {
          v24 = 199;
LABEL_24:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v24,
            (unsigned int)"onecore\\base\\cbs\\util\\cbsreg.cpp",
            (const char *)(unsigned int)v23,
            lpData);
          v6 = v23;
          goto LABEL_59;
        }
      }
      v26 = RegQueryValueExW((HKEY)v8, lpValueName, 0, &Type, (LPBYTE)*a5, &cbData);
      if ( !v26 )
      {
        v21 = 1;
        goto LABEL_27;
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
          v17 = (unsigned int)v26;
          v18 = 224;
          goto LABEL_16;
        }
LABEL_40:
        v6 = -2147024894;
        goto LABEL_59;
      }
    }
    else
    {
      v32 = RegQueryValueExW((HKEY)v8, v5, 0, &Type, 0, &cbData);
      if ( v32 == 2 )
        goto LABEL_40;
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
          v43[0] = v35;
          v44 = v43;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v34,
            3,
            (unsigned int)": {0}",
            (__int64)&v44);
        }
        v17 = (unsigned int)v32;
        v18 = 240;
        goto LABEL_16;
      }
    }
LABEL_27:
    if ( Type - 1 > 1 )
    {
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Registry value is not a string type.");
        v44 = v43;
        v43[0] = -2147024883;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v28,
          3,
          (unsigned int)": {0}",
          (__int64)&v44);
      }
      v17 = 13;
      v18 = 246;
      goto LABEL_16;
    }
    if ( !v21 )
    {
      v20 = ((unsigned __int64)cbData >> 1) + 2;
      v23 = SczAlloc(a5, v20);
      if ( v23 < 0 )
      {
        v24 = 255;
        goto LABEL_24;
      }
      v37 = RegQueryValueExW((HKEY)v8, lpValueName, 0, &Type, (LPBYTE)*a5, &cbData);
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
          v43[0] = v40;
          v44 = v43;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v39,
            3,
            (unsigned int)": {0}",
            (__int64)&v44);
        }
        v17 = (unsigned int)v37;
        v18 = 266;
        goto LABEL_16;
      }
    }
    (*a5)[v20 - 2] = 0;
    (*a5)[v20 - 1] = 0;
    v6 = 0;
    goto LABEL_59;
  }
  v6 = -2147467261;
  v49 = -2147467261;
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No value result specified");
    *(_QWORD *)v43 = &v49;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (_DWORD)LogAdapter::g_Logger,
      v7,
      3,
      (unsigned int)": {}",
      (__int64)v43);
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
0x14001a7e4  mov     [rsp-28h+arg_0], rbx
0x14001a7e9  mov     [rsp-28h+arg_10], rsi
0x14001a7ee  push    rbp
0x14001a7ef  push    rdi
0x14001a7f0  push    r12
0x14001a7f2  push    r14
0x14001a7f4  push    r15
0x14001a7f6  mov     rbp, rsp
0x14001a7f9  sub     rsp, 80h
0x14001a800  mov     rax, cs:__security_cookie
0x14001a807  xor     rax, rsp
0x14001a80a  mov     [rbp+var_10], rax
0x14001a80e  mov     r14, [rbp+arg_20]
0x14001a812  mov     rax, r9
0x14001a815  mov     [rbp+lpSubKey], rdx
0x14001a819  mov     [rbp+lpValueName], rax
0x14001a81d  test    r14, r14
0x14001a820  jnz     short loc_14001A88F
0x14001a822  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001a829  mov     ebx, 80004003h
0x14001a82e  mov     [rbp+var_24], ebx
0x14001a831  test    rcx, rcx
0x14001a834  jz      short loc_14001A872
0x14001a836  lea     esi, [r14+3]
0x14001a83a  xor     edx, edx
0x14001a83c  mov     r8d, esi
0x14001a83f  lea     r9, aNoValueResultS; "No value result specified"
0x14001a846  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14001a84b  lea     rcx, [rbp+var_50]
0x14001a84f  mov     r8d, esi
0x14001a852  mov     [rsp+80h+lpData], rcx; int
0x14001a857  lea     rax, [rbp+var_24]
0x14001a85b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001a862  lea     r9, asc_1400353E8; ": {}"
0x14001a869  mov     qword ptr [rbp+var_50], rax
0x14001a86d  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001a872  mov     rcx, [rbp+28h]; this
0x14001a876  lea     r8, aOnecoreBaseCbs_5; "onecore\\base\\cbs\\util\\cbsreg.cpp"
0x14001a87d  mov     r9d, ebx; char *
0x14001a880  mov     edx, 0A7h; void *
0x14001a885  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001a88a  jmp     loc_14001AC8B
0x14001a88f  mov     [rbp+var_18], 0
0x14001a897  mov     esi, 3
0x14001a89c  mov     r15, 0FFFFFFFF80000002h
0x14001a8a3  test    rdx, rdx
0x14001a8a6  jz      loc_14001A973
0x14001a8ac  lea     rcx, [rbp+var_18]
0x14001a8b0  call    ?GetInitPointer@?$AutoComPtr@UIClassFactory@@@Windows@@QEAAPEAPEAUIClassFactory@@XZ; Windows::AutoComPtr<IClassFactory>::GetInitPointer(void)
0x14001a8b5  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x14001a8b9  mov     r9d, 20019h; unsigned int
0x14001a8bf  mov     rcx, r15; hKey
0x14001a8c2  mov     [rsp+80h+lpData], rax; int
0x14001a8c7  call    ?CbsRegOpenKeyExW@@YAKPEAUHKEY__@@PEB_WKKPEAPEAU1@@Z; CbsRegOpenKeyExW(HKEY__ *,wchar_t const *,ulong,ulong,HKEY__ * *)
0x14001a8cc  mov     ebx, eax
0x14001a8ce  cmp     eax, 2
0x14001a8d1  jz      short loc_14001A8DF
0x14001a8d3  cmp     eax, esi
0x14001a8d5  jnz     short loc_14001A8ED
0x14001a8d7  test    eax, eax
0x14001a8d9  jle     loc_14001AC82
0x14001a8df  movzx   ebx, bx
0x14001a8e2  or      ebx, 80070000h
0x14001a8e8  jmp     loc_14001AC82
0x14001a8ed  test    ebx, ebx
0x14001a8ef  jz      short loc_14001A96B
0x14001a8f1  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001a8f8  test    rcx, rcx
0x14001a8fb  jz      short loc_14001A94C
0x14001a8fd  lea     rax, [rbp+lpSubKey]
0x14001a901  lea     r9, aFailedToOpenTh; "Failed to open the registry root: n/a, "...
0x14001a908  mov     [rsp+80h+lpData], rax
0x14001a90d  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x14001a912  test    ebx, ebx
0x14001a914  jg      short loc_14001A91A
0x14001a916  mov     eax, ebx
0x14001a918  jmp     short loc_14001A922
0x14001a91a  movzx   eax, bx
0x14001a91d  or      eax, 80070000h
0x14001a922  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001a929  lea     r9, a0; ": {0}"
0x14001a930  mov     [rbp+var_24], eax
0x14001a933  mov     r8d, esi
0x14001a936  lea     rax, [rbp+var_24]
0x14001a93a  mov     qword ptr [rbp+var_50], rax
0x14001a93e  lea     rax, [rbp+var_50]
0x14001a942  mov     [rsp+80h+lpData], rax; unsigned int
0x14001a947  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001a94c  mov     r9d, ebx; char *
0x14001a94f  mov     edx, 0B6h; void *
0x14001a954  mov     rcx, [rbp+28h]; this
0x14001a958  lea     r8, aOnecoreBaseCbs_5; "onecore\\base\\cbs\\util\\cbsreg.cpp"
0x14001a95f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x14001a964  mov     ebx, eax
0x14001a966  jmp     loc_14001AC82
0x14001a96b  mov     r15, [rbp+var_18]
0x14001a96f  mov     rax, [rbp+lpValueName]
0x14001a973  mov     rcx, [r14]
0x14001a976  xor     ebx, ebx
0x14001a978  xor     r12d, r12d
0x14001a97b  mov     qword ptr [rbp+var_50], rbx
0x14001a97f  mov     [rbp+Type], ebx
0x14001a982  mov     [rbp+cbData], ebx
0x14001a985  test    rcx, rcx
0x14001a988  jz      loc_14001AB0B
0x14001a98e  lea     rdx, [rbp+var_50]
0x14001a992  call    SczSize
0x14001a997  mov     ebx, eax
0x14001a999  test    eax, eax
0x14001a99b  jns     short loc_14001A9BA
0x14001a99d  mov     rcx, [rbp+28h]; this
0x14001a9a1  lea     r8, aOnecoreBaseCbs_5; "onecore\\base\\cbs\\util\\cbsreg.cpp"
0x14001a9a8  mov     r9d, eax; char *
0x14001a9ab  mov     edx, 0C2h; void *
0x14001a9b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001a9b5  jmp     loc_14001AC82
0x14001a9ba  mov     rbx, qword ptr [rbp+var_50]
0x14001a9be  cmp     rbx, 2
0x14001a9c2  jb      short loc_14001A9FA
0x14001a9c4  lea     rcx, ds:0FFFFFFFFFFFFFFFCh[rbx*2]; unsigned __int64
0x14001a9cc  lea     rdx, [rbp+cbData]; unsigned int *
0x14001a9d0  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x14001a9d5  mov     edi, eax
0x14001a9d7  test    eax, eax
0x14001a9d9  jns     short loc_14001A9FA
0x14001a9db  mov     edx, 0C7h; void *
0x14001a9e0  mov     rcx, [rbp+28h]; this
0x14001a9e4  lea     r8, aOnecoreBaseCbs_5; "onecore\\base\\cbs\\util\\cbsreg.cpp"
0x14001a9eb  mov     r9d, edi; char *
0x14001a9ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001a9f3  mov     ebx, edi
0x14001a9f5  jmp     loc_14001AC82
0x14001a9fa  mov     rdx, [rbp+lpValueName]; lpValueName
0x14001a9fe  lea     rax, [rbp+cbData]
0x14001aa02  mov     [rsp+80h+lpcbData], rax; lpcbData
0x14001aa07  lea     r9, [rbp+Type]; lpType
0x14001aa0b  mov     rax, [r14]
0x14001aa0e  xor     r8d, r8d; lpReserved
0x14001aa11  mov     rcx, r15; hKey
0x14001aa14  mov     [rsp+80h+lpData], rax; lpData
0x14001aa19  call    cs:__imp_RegQueryValueExW
0x14001aa1f  mov     edi, eax
0x14001aa21  test    eax, eax
0x14001aa23  jnz     short loc_14001AA92
0x14001aa25  lea     r12d, [rax+1]
0x14001aa29  mov     eax, [rbp+Type]
0x14001aa2c  dec     eax
0x14001aa2e  cmp     eax, 1
0x14001aa31  jbe     loc_14001ABAD
0x14001aa37  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001aa3e  test    rcx, rcx
0x14001aa41  jz      short loc_14001AA82
0x14001aa43  lea     r9, aRegistryValueI_0; "Registry value is not a string type."
0x14001aa4a  mov     r8d, esi
0x14001aa4d  xor     edx, edx
0x14001aa4f  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14001aa54  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001aa5b  lea     rax, [rbp+var_50]
0x14001aa5f  mov     [rbp+var_48], rax
0x14001aa63  lea     r9, a0; ": {0}"
0x14001aa6a  lea     rax, [rbp+var_48]
0x14001aa6e  mov     [rbp+var_50], 8007000Dh
0x14001aa75  mov     r8d, esi
0x14001aa78  mov     [rsp+80h+lpData], rax
0x14001aa7d  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001aa82  mov     r9d, 0Dh
0x14001aa88  mov     edx, 0F6h
0x14001aa8d  jmp     loc_14001A954
0x14001aa92  cmp     edi, 0EAh
0x14001aa98  jz      short loc_14001AA29
0x14001aa9a  cmp     edi, 2
0x14001aa9d  jz      loc_14001AB33
0x14001aaa3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001aaaa  test    rcx, rcx
0x14001aaad  jz      short loc_14001AAFE
0x14001aaaf  lea     rax, [rbp+lpValueName]
0x14001aab3  lea     r9, aFailedInitialQ; "Failed initial query of value to get ty"...
0x14001aaba  mov     [rsp+80h+lpData], rax
0x14001aabf  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x14001aac4  test    edi, edi
0x14001aac6  jg      short loc_14001AACC
0x14001aac8  mov     eax, edi
0x14001aaca  jmp     short loc_14001AAD4
0x14001aacc  movzx   eax, di
0x14001aacf  or      eax, 80070000h
0x14001aad4  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001aadb  lea     r9, a0; ": {0}"
0x14001aae2  mov     [rbp+var_24], eax
0x14001aae5  mov     r8d, esi
0x14001aae8  lea     rax, [rbp+var_24]
0x14001aaec  mov     [rbp+var_40], rax
0x14001aaf0  lea     rax, [rbp+var_40]
0x14001aaf4  mov     [rsp+80h+lpData], rax
0x14001aaf9  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001aafe  mov     r9d, edi
0x14001ab01  mov     edx, 0E0h
0x14001ab06  jmp     loc_14001A954
0x14001ab0b  lea     rcx, [rbp+cbData]
0x14001ab0f  xor     r8d, r8d; lpReserved
0x14001ab12  mov     [rsp+80h+lpcbData], rcx; lpcbData
0x14001ab17  lea     r9, [rbp+Type]; lpType
0x14001ab1b  mov     rcx, r15; hKey
0x14001ab1e  mov     [rsp+80h+lpData], rbx; lpData
0x14001ab23  mov     rdx, rax; lpValueName
0x14001ab26  call    cs:__imp_RegQueryValueExW
0x14001ab2c  mov     edi, eax
0x14001ab2e  cmp     eax, 2
0x14001ab31  jnz     short loc_14001AB3D
0x14001ab33  mov     ebx, 80070002h
0x14001ab38  jmp     loc_14001AC82
0x14001ab3d  test    edi, edi
0x14001ab3f  jz      loc_14001AA29
0x14001ab45  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001ab4c  test    rcx, rcx
0x14001ab4f  jz      short loc_14001ABA0
0x14001ab51  lea     rax, [rbp+lpValueName]
0x14001ab55  lea     r9, aFailedToQueryV; "Failed to query value to get type and s"...
0x14001ab5c  mov     [rsp+80h+lpData], rax
0x14001ab61  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x14001ab66  test    edi, edi
0x14001ab68  jg      short loc_14001AB6E
0x14001ab6a  mov     eax, edi
0x14001ab6c  jmp     short loc_14001AB76
0x14001ab6e  movzx   eax, di
0x14001ab71  or      eax, 80070000h
0x14001ab76  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001ab7d  lea     r9, a0; ": {0}"
0x14001ab84  mov     [rbp+var_50], eax
0x14001ab87  mov     r8d, esi
0x14001ab8a  lea     rax, [rbp+var_50]
0x14001ab8e  mov     [rbp+var_48], rax
0x14001ab92  lea     rax, [rbp+var_48]
0x14001ab96  mov     [rsp+80h+lpData], rax
0x14001ab9b  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001aba0  mov     r9d, edi
0x14001aba3  mov     edx, 0F0h
0x14001aba8  jmp     loc_14001A954
0x14001abad  test    r12d, r12d
0x14001abb0  jnz     loc_14001AC6E
0x14001abb6  mov     ebx, [rbp+cbData]
0x14001abb9  mov     rcx, r14
0x14001abbc  shr     rbx, 1
0x14001abbf  add     rbx, 2
0x14001abc3  mov     rdx, rbx
0x14001abc6  call    SczAlloc
0x14001abcb  mov     edi, eax
0x14001abcd  test    eax, eax
0x14001abcf  jns     short loc_14001ABDB
0x14001abd1  mov     edx, 0FFh
0x14001abd6  jmp     loc_14001A9E0
0x14001abdb  mov     rdx, [rbp+lpValueName]; lpValueName
0x14001abdf  lea     rax, [rbp+cbData]
0x14001abe3  mov     [rsp+80h+lpcbData], rax; lpcbData
0x14001abe8  lea     r9, [rbp+Type]; lpType
0x14001abec  mov     rax, [r14]
0x14001abef  xor     r8d, r8d; lpReserved
0x14001abf2  mov     rcx, r15; hKey
0x14001abf5  mov     [rsp+80h+lpData], rax; lpData
0x14001abfa  call    cs:__imp_RegQueryValueExW
0x14001ac00  mov     edi, eax
0x14001ac02  test    eax, eax
0x14001ac04  jz      short loc_14001AC6E
0x14001ac06  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001ac0d  test    rcx, rcx
0x14001ac10  jz      short loc_14001AC61
0x14001ac12  lea     rax, [rbp+lpValueName]
0x14001ac16  lea     r9, aFailedToQueryR; "Failed to query registry value: {}"
0x14001ac1d  mov     [rsp+80h+lpData], rax
0x14001ac22  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x14001ac27  test    edi, edi
0x14001ac29  jg      short loc_14001AC2F
0x14001ac2b  mov     eax, edi
0x14001ac2d  jmp     short loc_14001AC37
0x14001ac2f  movzx   eax, di
0x14001ac32  or      eax, 80070000h
0x14001ac37  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001ac3e  lea     r9, a0; ": {0}"
0x14001ac45  mov     [rbp+var_50], eax
0x14001ac48  mov     r8d, esi
0x14001ac4b  lea     rax, [rbp+var_50]
0x14001ac4f  mov     [rbp+var_48], rax
0x14001ac53  lea     rax, [rbp+var_48]
0x14001ac57  mov     [rsp+80h+lpData], rax
0x14001ac5c  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001ac61  mov     r9d, edi
0x14001ac64  mov     edx, 10Ah
0x14001ac69  jmp     loc_14001A954
0x14001ac6e  mov     rcx, [r14]
0x14001ac71  xor     eax, eax
0x14001ac73  mov     [rcx+rbx*2-4], ax
0x14001ac78  mov     rcx, [r14]
0x14001ac7b  mov     [rcx+rbx*2-2], ax
0x14001ac80  xor     ebx, ebx
0x14001ac82  lea     rcx, [rbp+var_18]
0x14001ac86  call    ?Close@?$AutoGenericHandleBase@PEAUHKEY__@@$0A@V?$AutoGenericHandle@PEAUHKEY__@@$0A@$1?CloseWithRegCloseKey@Detail@Windows@@YAXPEAU1@@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<HKEY__ *,0,Windows::AutoGenericHandle<HKEY__ *,0,&Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>>::Close(void)
0x14001ac8b  mov     eax, ebx
0x14001ac8d  mov     rcx, [rbp+var_10]
0x14001ac91  xor     rcx, rsp; StackCookie
0x14001ac94  call    __security_check_cookie
0x14001ac99  lea     r11, [rsp+80h+var_s0]
  ... truncated ...
```
