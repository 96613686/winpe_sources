# CbsRegQueryStringValue(HKEY__ *,wchar_t const *,ulong,wchar_t const *,wchar_t * *)

- ea: `0x140011550`
- end: `0x140011a29`
- name: `?CbsRegQueryStringValue@@YAJPEAUHKEY__@@PEB_WK1PEAPEA_W@Z`
- size: `1241`
- prototype: `__int64 __fastcall(HKEY, const wchar_t *, unsigned int, const wchar_t *, wchar_t **)`
- caller_count: `3`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x140007228`
- `0x14000f530`
- `0x14000f5b0`

## callees

- `0x140002310`
- `0x1400053c0`
- `0x140008d38`
- `0x140008ef4`
- `0x14000d910`
- `0x14000e610`
- `0x14000f36c`
- `0x14001118c`
- `0x140011550`
- `0x140012148`
- `0x14001726c`
- `0x14001887c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14001177e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140011890`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140011969`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14001177e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140011890`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140011969`

## string_xrefs

- `0x140011664`: `Failed to open the registry root: n/a, key: {}.`
- `0x14001181b`: `Failed initial query of value to get type, size, and value of registry value: {}`
- `0x1400118c2`: `Failed to query value to get type and size of registry root: n/a, value: {}`
- `0x1400117a8`: `Registry value is not a string type.`
- `0x140011988`: `Failed to query registry value: {}`

## pseudocode

```c
__int64 __fastcall CbsRegQueryStringValue(HKEY a1, const wchar_t *a2, unsigned int a3, const wchar_t *a4, wchar_t **a5)
{
  const WCHAR *v5; // rax
  unsigned int v6; // ebx
  int v7; // edx
  HKEY v8; // r15
  unsigned int v9; // eax
  int v10; // ebx
  int v11; // edx
  unsigned int v12; // eax
  __int64 v13; // r9
  __int64 v14; // rdx
  LPBYTE v15; // rcx
  unsigned __int64 v16; // rbx
  int v17; // r12d
  int v18; // eax
  int v19; // esi
  __int64 v20; // rdx
  LSTATUS v21; // esi
  int v22; // edx
  int v23; // edx
  unsigned int v24; // eax
  LSTATUS v25; // esi
  int v26; // edx
  unsigned int v27; // eax
  LSTATUS v28; // esi
  int v29; // edx
  unsigned int v30; // eax
  unsigned int lpData; // [rsp+20h] [rbp-60h]
  unsigned int v33[2]; // [rsp+30h] [rbp-50h] BYREF
  unsigned int *v34; // [rsp+38h] [rbp-48h] BYREF
  int *v35; // [rsp+40h] [rbp-40h] BYREF
  LPCWSTR lpValueName; // [rsp+48h] [rbp-38h] BYREF
  const wchar_t *v37; // [rsp+50h] [rbp-30h] BYREF
  DWORD cbData; // [rsp+58h] [rbp-28h] BYREF
  int v39; // [rsp+5Ch] [rbp-24h] BYREF
  DWORD Type; // [rsp+60h] [rbp-20h] BYREF
  HKEY v41; // [rsp+68h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  v5 = a4;
  v37 = a2;
  lpValueName = a4;
  if ( a5 )
  {
    v41 = 0;
    v8 = HKEY_LOCAL_MACHINE;
    if ( a2 )
    {
      v9 = CbsRegOpenKeyExW(a1, a2, a3, 0x20019u, &v41);
      v10 = v9;
      if ( v9 == 2 || v9 == 3 )
      {
        v6 = (unsigned __int16)v9 | 0x80070000;
LABEL_59:
        Windows::AutoGenericHandleBase<HKEY__ *,0,Windows::AutoGenericHandle<HKEY__ *,0,&void Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>>::Close(&v41);
        return v6;
      }
      if ( v9 )
      {
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            (_DWORD)LogAdapter::g_Logger,
            0,
            3,
            (unsigned int)"Failed to open the registry root: n/a, key: {}.",
            (__int64)&v37);
          if ( v10 > 0 )
            v12 = (unsigned __int16)v10 | 0x80070000;
          else
            v12 = v10;
          v39 = v12;
          *(_QWORD *)v33 = &v39;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v11,
            3,
            (unsigned int)": {0}",
            (__int64)v33);
        }
        v13 = (unsigned int)v10;
        v14 = 182;
LABEL_16:
        v6 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)v14,
               (unsigned int)"onecore\\base\\cbs\\util\\cbsreg.cpp",
               (const char *)v13,
               lpData);
        goto LABEL_59;
      }
      v8 = v41;
      v5 = lpValueName;
    }
    v15 = (LPBYTE)*a5;
    v16 = 0;
    v17 = 0;
    *(_QWORD *)v33 = 0;
    Type = 0;
    cbData = 0;
    if ( v15 )
    {
      v18 = SczSize(v15, v33);
      v6 = v18;
      if ( v18 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xC2,
          (unsigned int)"onecore\\base\\cbs\\util\\cbsreg.cpp",
          (const char *)(unsigned int)v18,
          lpData);
        goto LABEL_59;
      }
      v16 = *(_QWORD *)v33;
      if ( *(_QWORD *)v33 >= 2u )
      {
        v19 = ULongLongToULong(2LL * *(_QWORD *)v33 - 4, &cbData);
        if ( v19 < 0 )
        {
          v20 = 199;
LABEL_24:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v20,
            (unsigned int)"onecore\\base\\cbs\\util\\cbsreg.cpp",
            (const char *)(unsigned int)v19,
            lpData);
          v6 = v19;
          goto LABEL_59;
        }
      }
      v21 = RegQueryValueExW(v8, lpValueName, 0, &Type, (LPBYTE)*a5, &cbData);
      if ( !v21 )
      {
        v17 = 1;
        goto LABEL_27;
      }
      if ( v21 != 234 )
      {
        if ( v21 != 2 )
        {
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<wchar_t const *>(
              (_DWORD)LogAdapter::g_Logger,
              0,
              3,
              (unsigned int)"Failed initial query of value to get type, size, and value of registry value: {}",
              (__int64)&lpValueName);
            if ( v21 > 0 )
              v24 = (unsigned __int16)v21 | 0x80070000;
            else
              v24 = v21;
            v39 = v24;
            v35 = &v39;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v23,
              3,
              (unsigned int)": {0}",
              (__int64)&v35);
          }
          v13 = (unsigned int)v21;
          v14 = 224;
          goto LABEL_16;
        }
LABEL_40:
        v6 = -2147024894;
        goto LABEL_59;
      }
    }
    else
    {
      v25 = RegQueryValueExW(v8, v5, 0, &Type, 0, &cbData);
      if ( v25 == 2 )
        goto LABEL_40;
      if ( v25 )
      {
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            (_DWORD)LogAdapter::g_Logger,
            0,
            3,
            (unsigned int)"Failed to query value to get type and size of registry root: n/a, value: {}",
            (__int64)&lpValueName);
          if ( v25 > 0 )
            v27 = (unsigned __int16)v25 | 0x80070000;
          else
            v27 = v25;
          v33[0] = v27;
          v34 = v33;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v26,
            3,
            (unsigned int)": {0}",
            (__int64)&v34);
        }
        v13 = (unsigned int)v25;
        v14 = 240;
        goto LABEL_16;
      }
    }
LABEL_27:
    if ( Type - 1 > 1 )
    {
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Registry value is not a string type.");
        v34 = v33;
        v33[0] = -2147024883;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v22,
          3,
          (unsigned int)": {0}",
          (__int64)&v34);
      }
      v13 = 13;
      v14 = 246;
      goto LABEL_16;
    }
    if ( !v17 )
    {
      v16 = ((unsigned __int64)cbData >> 1) + 2;
      v19 = SczAlloc(a5, v16);
      if ( v19 < 0 )
      {
        v20 = 255;
        goto LABEL_24;
      }
      v28 = RegQueryValueExW(v8, lpValueName, 0, &Type, (LPBYTE)*a5, &cbData);
      if ( v28 )
      {
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            (_DWORD)LogAdapter::g_Logger,
            0,
            3,
            (unsigned int)"Failed to query registry value: {}",
            (__int64)&lpValueName);
          if ( v28 > 0 )
            v30 = (unsigned __int16)v28 | 0x80070000;
          else
            v30 = v28;
          v33[0] = v30;
          v34 = v33;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v29,
            3,
            (unsigned int)": {0}",
            (__int64)&v34);
        }
        v13 = (unsigned int)v28;
        v14 = 266;
        goto LABEL_16;
      }
    }
    (*a5)[v16 - 2] = 0;
    (*a5)[v16 - 1] = 0;
    v6 = 0;
    goto LABEL_59;
  }
  v6 = -2147467261;
  v39 = -2147467261;
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No value result specified");
    *(_QWORD *)v33 = &v39;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (_DWORD)LogAdapter::g_Logger,
      v7,
      3,
      (unsigned int)": {}",
      (__int64)v33);
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
0x140011550  mov     [rsp-28h+arg_0], rbx
0x140011555  mov     [rsp-28h+arg_10], rsi
0x14001155a  push    rbp
0x14001155b  push    rdi
0x14001155c  push    r12
0x14001155e  push    r14
0x140011560  push    r15
0x140011562  mov     rbp, rsp
0x140011565  sub     rsp, 80h
0x14001156c  mov     rax, cs:__security_cookie
0x140011573  xor     rax, rsp
0x140011576  mov     [rbp+var_10], rax
0x14001157a  mov     r14, [rbp+arg_20]
0x14001157e  mov     rax, r9
0x140011581  mov     [rbp+var_30], rdx
0x140011585  mov     [rbp+lpValueName], rax
0x140011589  test    r14, r14
0x14001158c  jnz     short loc_1400115FB
0x14001158e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140011595  mov     ebx, 80004003h
0x14001159a  mov     [rbp+var_24], ebx
0x14001159d  test    rcx, rcx
0x1400115a0  jz      short loc_1400115DE
0x1400115a2  lea     edi, [r14+3]
0x1400115a6  xor     edx, edx
0x1400115a8  mov     r8d, edi
0x1400115ab  lea     r9, aNoValueResultS; "No value result specified"
0x1400115b2  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1400115b7  lea     rcx, [rbp+var_50]
0x1400115bb  mov     r8d, edi
0x1400115be  mov     [rsp+80h+lpData], rcx; int
0x1400115c3  lea     rax, [rbp+var_24]
0x1400115c7  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400115ce  lea     r9, asc_140030534; ": {}"
0x1400115d5  mov     qword ptr [rbp+var_50], rax
0x1400115d9  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1400115de  mov     rcx, [rbp+28h]; this
0x1400115e2  lea     r8, aOnecoreBaseCbs_1; "onecore\\base\\cbs\\util\\cbsreg.cpp"
0x1400115e9  mov     r9d, ebx; char *
0x1400115ec  mov     edx, 0A7h; void *
0x1400115f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400115f6  jmp     loc_1400119FF
0x1400115fb  mov     [rbp+var_18], 0
0x140011603  mov     edi, 3
0x140011608  mov     r15, 0FFFFFFFF80000002h
0x14001160f  test    rdx, rdx
0x140011612  jz      loc_1400116D8
0x140011618  lea     rax, [rbp+var_18]
0x14001161c  mov     r9d, 20019h; unsigned int
0x140011622  mov     [rsp+80h+lpData], rax; int
0x140011627  call    ?CbsRegOpenKeyExW@@YAKPEAUHKEY__@@PEB_WKKPEAPEAU1@@Z; CbsRegOpenKeyExW(HKEY__ *,wchar_t const *,ulong,ulong,HKEY__ * *)
0x14001162c  mov     ebx, eax
0x14001162e  cmp     eax, 2
0x140011631  jz      short loc_14001163F
0x140011633  cmp     eax, edi
0x140011635  jnz     short loc_14001164D
0x140011637  test    eax, eax
0x140011639  jle     loc_1400119F6
0x14001163f  movzx   ebx, bx
0x140011642  or      ebx, 80070000h
0x140011648  jmp     loc_1400119F6
0x14001164d  test    ebx, ebx
0x14001164f  jz      short loc_1400116D0
0x140011651  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140011658  test    rcx, rcx
0x14001165b  jz      short loc_1400116B1
0x14001165d  lea     rax, [rbp+var_30]
0x140011661  mov     r8d, edi
0x140011664  lea     r9, aFailedToOpenTh; "Failed to open the registry root: n/a, "...
0x14001166b  mov     [rsp+80h+lpData], rax
0x140011670  xor     edx, edx
0x140011672  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x140011677  test    ebx, ebx
0x140011679  jg      short loc_14001167F
0x14001167b  mov     eax, ebx
0x14001167d  jmp     short loc_140011687
0x14001167f  movzx   eax, bx
0x140011682  or      eax, 80070000h
0x140011687  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001168e  lea     r9, a0; ": {0}"
0x140011695  mov     [rbp+var_24], eax
0x140011698  mov     r8d, edi
0x14001169b  lea     rax, [rbp+var_24]
0x14001169f  mov     qword ptr [rbp+var_50], rax
0x1400116a3  lea     rax, [rbp+var_50]
0x1400116a7  mov     [rsp+80h+lpData], rax; unsigned int
0x1400116ac  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1400116b1  mov     r9d, ebx; char *
0x1400116b4  mov     edx, 0B6h; void *
0x1400116b9  mov     rcx, [rbp+28h]; this
0x1400116bd  lea     r8, aOnecoreBaseCbs_1; "onecore\\base\\cbs\\util\\cbsreg.cpp"
0x1400116c4  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1400116c9  mov     ebx, eax
0x1400116cb  jmp     loc_1400119F6
0x1400116d0  mov     r15, [rbp+var_18]
0x1400116d4  mov     rax, [rbp+lpValueName]
0x1400116d8  mov     rcx, [r14]
0x1400116db  xor     ebx, ebx
0x1400116dd  xor     r12d, r12d
0x1400116e0  mov     qword ptr [rbp+var_50], rbx
0x1400116e4  mov     [rbp+Type], ebx
0x1400116e7  mov     [rbp+cbData], ebx
0x1400116ea  test    rcx, rcx
0x1400116ed  jz      loc_140011875
0x1400116f3  lea     rdx, [rbp+var_50]
0x1400116f7  call    SczSize
0x1400116fc  mov     ebx, eax
0x1400116fe  test    eax, eax
0x140011700  jns     short loc_14001171F
0x140011702  mov     rcx, [rbp+28h]; this
0x140011706  lea     r8, aOnecoreBaseCbs_1; "onecore\\base\\cbs\\util\\cbsreg.cpp"
0x14001170d  mov     r9d, eax; char *
0x140011710  mov     edx, 0C2h; void *
0x140011715  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001171a  jmp     loc_1400119F6
0x14001171f  mov     rbx, qword ptr [rbp+var_50]
0x140011723  cmp     rbx, 2
0x140011727  jb      short loc_14001175F
0x140011729  lea     rcx, ds:0FFFFFFFFFFFFFFFCh[rbx*2]; unsigned __int64
0x140011731  lea     rdx, [rbp+cbData]; unsigned int *
0x140011735  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x14001173a  mov     esi, eax
0x14001173c  test    eax, eax
0x14001173e  jns     short loc_14001175F
0x140011740  mov     edx, 0C7h; void *
0x140011745  mov     rcx, [rbp+28h]; this
0x140011749  lea     r8, aOnecoreBaseCbs_1; "onecore\\base\\cbs\\util\\cbsreg.cpp"
0x140011750  mov     r9d, esi; char *
0x140011753  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140011758  mov     ebx, esi
0x14001175a  jmp     loc_1400119F6
0x14001175f  mov     rdx, [rbp+lpValueName]; lpValueName
0x140011763  lea     rax, [rbp+cbData]
0x140011767  mov     [rsp+80h+lpcbData], rax; lpcbData
0x14001176c  lea     r9, [rbp+Type]; lpType
0x140011770  mov     rax, [r14]
0x140011773  xor     r8d, r8d; lpReserved
0x140011776  mov     rcx, r15; hKey
0x140011779  mov     [rsp+80h+lpData], rax; lpData
0x14001177e  call    cs:__imp_RegQueryValueExW
0x140011784  mov     esi, eax
0x140011786  test    eax, eax
0x140011788  jnz     short loc_1400117F7
0x14001178a  lea     r12d, [rax+1]
0x14001178e  mov     eax, [rbp+Type]
0x140011791  dec     eax
0x140011793  cmp     eax, 1
0x140011796  jbe     loc_14001191C
0x14001179c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400117a3  test    rcx, rcx
0x1400117a6  jz      short loc_1400117E7
0x1400117a8  lea     r9, aRegistryValueI; "Registry value is not a string type."
0x1400117af  mov     r8d, edi
0x1400117b2  xor     edx, edx
0x1400117b4  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1400117b9  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400117c0  lea     rax, [rbp+var_50]
0x1400117c4  mov     [rbp+var_48], rax
0x1400117c8  lea     r9, a0; ": {0}"
0x1400117cf  lea     rax, [rbp+var_48]
0x1400117d3  mov     [rbp+var_50], 8007000Dh
0x1400117da  mov     r8d, edi
0x1400117dd  mov     [rsp+80h+lpData], rax
0x1400117e2  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1400117e7  mov     r9d, 0Dh
0x1400117ed  mov     edx, 0F6h
0x1400117f2  jmp     loc_1400116B9
0x1400117f7  cmp     esi, 0EAh
0x1400117fd  jz      short loc_14001178E
0x1400117ff  cmp     esi, 2
0x140011802  jz      loc_14001189D
0x140011808  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001180f  test    rcx, rcx
0x140011812  jz      short loc_140011868
0x140011814  lea     rax, [rbp+lpValueName]
0x140011818  mov     r8d, edi
0x14001181b  lea     r9, aFailedInitialQ; "Failed initial query of value to get ty"...
0x140011822  mov     [rsp+80h+lpData], rax
0x140011827  xor     edx, edx
0x140011829  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x14001182e  test    esi, esi
0x140011830  jg      short loc_140011836
0x140011832  mov     eax, esi
0x140011834  jmp     short loc_14001183E
0x140011836  movzx   eax, si
0x140011839  or      eax, 80070000h
0x14001183e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140011845  lea     r9, a0; ": {0}"
0x14001184c  mov     [rbp+var_24], eax
0x14001184f  mov     r8d, edi
0x140011852  lea     rax, [rbp+var_24]
0x140011856  mov     [rbp+var_40], rax
0x14001185a  lea     rax, [rbp+var_40]
0x14001185e  mov     [rsp+80h+lpData], rax
0x140011863  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140011868  mov     r9d, esi
0x14001186b  mov     edx, 0E0h
0x140011870  jmp     loc_1400116B9
0x140011875  lea     rcx, [rbp+cbData]
0x140011879  xor     r8d, r8d; lpReserved
0x14001187c  mov     [rsp+80h+lpcbData], rcx; lpcbData
0x140011881  lea     r9, [rbp+Type]; lpType
0x140011885  mov     rcx, r15; hKey
0x140011888  mov     [rsp+80h+lpData], rbx; lpData
0x14001188d  mov     rdx, rax; lpValueName
0x140011890  call    cs:__imp_RegQueryValueExW
0x140011896  mov     esi, eax
0x140011898  cmp     eax, 2
0x14001189b  jnz     short loc_1400118A7
0x14001189d  mov     ebx, 80070002h
0x1400118a2  jmp     loc_1400119F6
0x1400118a7  test    esi, esi
0x1400118a9  jz      loc_14001178E
0x1400118af  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400118b6  test    rcx, rcx
0x1400118b9  jz      short loc_14001190F
0x1400118bb  lea     rax, [rbp+lpValueName]
0x1400118bf  mov     r8d, edi
0x1400118c2  lea     r9, aFailedToQueryV; "Failed to query value to get type and s"...
0x1400118c9  mov     [rsp+80h+lpData], rax
0x1400118ce  xor     edx, edx
0x1400118d0  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1400118d5  test    esi, esi
0x1400118d7  jg      short loc_1400118DD
0x1400118d9  mov     eax, esi
0x1400118db  jmp     short loc_1400118E5
0x1400118dd  movzx   eax, si
0x1400118e0  or      eax, 80070000h
0x1400118e5  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400118ec  lea     r9, a0; ": {0}"
0x1400118f3  mov     [rbp+var_50], eax
0x1400118f6  mov     r8d, edi
0x1400118f9  lea     rax, [rbp+var_50]
0x1400118fd  mov     [rbp+var_48], rax
0x140011901  lea     rax, [rbp+var_48]
0x140011905  mov     [rsp+80h+lpData], rax
0x14001190a  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001190f  mov     r9d, esi
0x140011912  mov     edx, 0F0h
0x140011917  jmp     loc_1400116B9
0x14001191c  test    r12d, r12d
0x14001191f  jnz     loc_1400119E2
0x140011925  mov     ebx, [rbp+cbData]
0x140011928  mov     rcx, r14
0x14001192b  shr     rbx, 1
0x14001192e  add     rbx, 2
0x140011932  mov     rdx, rbx
0x140011935  call    SczAlloc
0x14001193a  mov     esi, eax
0x14001193c  test    eax, eax
0x14001193e  jns     short loc_14001194A
0x140011940  mov     edx, 0FFh
0x140011945  jmp     loc_140011745
0x14001194a  mov     rdx, [rbp+lpValueName]; lpValueName
0x14001194e  lea     rax, [rbp+cbData]
0x140011952  mov     [rsp+80h+lpcbData], rax; lpcbData
0x140011957  lea     r9, [rbp+Type]; lpType
0x14001195b  mov     rax, [r14]
0x14001195e  xor     r8d, r8d; lpReserved
0x140011961  mov     rcx, r15; hKey
0x140011964  mov     [rsp+80h+lpData], rax; lpData
0x140011969  call    cs:__imp_RegQueryValueExW
0x14001196f  mov     esi, eax
0x140011971  test    eax, eax
0x140011973  jz      short loc_1400119E2
0x140011975  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001197c  test    rcx, rcx
0x14001197f  jz      short loc_1400119D5
0x140011981  lea     rax, [rbp+lpValueName]
0x140011985  mov     r8d, edi
0x140011988  lea     r9, aFailedToQueryR; "Failed to query registry value: {}"
0x14001198f  mov     [rsp+80h+lpData], rax
0x140011994  xor     edx, edx
0x140011996  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x14001199b  test    esi, esi
0x14001199d  jg      short loc_1400119A3
0x14001199f  mov     eax, esi
0x1400119a1  jmp     short loc_1400119AB
0x1400119a3  movzx   eax, si
0x1400119a6  or      eax, 80070000h
0x1400119ab  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400119b2  lea     r9, a0; ": {0}"
0x1400119b9  mov     [rbp+var_50], eax
0x1400119bc  mov     r8d, edi
0x1400119bf  lea     rax, [rbp+var_50]
0x1400119c3  mov     [rbp+var_48], rax
0x1400119c7  lea     rax, [rbp+var_48]
0x1400119cb  mov     [rsp+80h+lpData], rax
0x1400119d0  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1400119d5  mov     r9d, esi
0x1400119d8  mov     edx, 10Ah
0x1400119dd  jmp     loc_1400116B9
0x1400119e2  mov     rcx, [r14]
0x1400119e5  xor     eax, eax
0x1400119e7  mov     [rcx+rbx*2-4], ax
0x1400119ec  mov     rcx, [r14]
0x1400119ef  mov     [rcx+rbx*2-2], ax
0x1400119f4  xor     ebx, ebx
0x1400119f6  lea     rcx, [rbp+var_18]
0x1400119fa  call    ?Close@?$AutoGenericHandleBase@PEAUHKEY__@@$0A@V?$AutoGenericHandle@PEAUHKEY__@@$0A@$1?CloseWithRegCloseKey@Detail@Windows@@YAXPEAU1@@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<HKEY__ *,0,Windows::AutoGenericHandle<HKEY__ *,0,&Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>>::Close(void)
  ... truncated ...
```
