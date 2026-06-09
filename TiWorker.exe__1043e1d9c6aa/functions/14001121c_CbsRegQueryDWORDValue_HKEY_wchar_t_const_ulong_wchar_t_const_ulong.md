# CbsRegQueryDWORDValue(HKEY__ *,wchar_t const *,ulong,wchar_t const *,ulong *)

- ea: `0x14001121c`
- end: `0x140011547`
- name: `?CbsRegQueryDWORDValue@@YAJPEAUHKEY__@@PEB_WK1PEAK@Z`
- size: `811`
- prototype: `__int64 __fastcall(HKEY, const wchar_t *, __int64, const wchar_t *, unsigned int *)`
- caller_count: `4`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callers

- `0x14000f5b0`
- `0x1400161e0`
- `0x140023db0`
- `0x140023e70`

## callees

- `0x140002310`
- `0x1400053c0`
- `0x140008d38`
- `0x140008ef4`
- `0x14000d910`
- `0x14000e610`
- `0x14000f36c`
- `0x14001118c`
- `0x14001121c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140011425`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140011425`

## string_xrefs

- `0x140011380`: `Failed to open the registry root: n/a, key: {}.`
- `0x140011453`: `Failed to query registry value: {}`
- `0x1400114c4`: `Registry value is not a DWORD type.`

## pseudocode

```c
__int64 __fastcall CbsRegQueryDWORDValue(HKEY a1, const wchar_t *a2, __int64 a3, const wchar_t *a4, unsigned int *a5)
{
  const WCHAR *v5; // rax
  unsigned int v6; // ebx
  __int64 v7; // rdx
  __int64 v8; // rdx
  __int64 v9; // rdx
  HKEY v10; // rcx
  LSTATUS v11; // eax
  LSTATUS v12; // ebx
  __int64 v13; // rdx
  unsigned int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // rdx
  unsigned int v17; // eax
  __int64 v18; // rdx
  int lpData; // [rsp+20h] [rbp-60h]
  unsigned int lpDataa; // [rsp+20h] [rbp-60h]
  int v22[2]; // [rsp+30h] [rbp-50h] BYREF
  const wchar_t *v23; // [rsp+38h] [rbp-48h] BYREF
  const wchar_t *v24; // [rsp+40h] [rbp-40h] BYREF
  int v25; // [rsp+48h] [rbp-38h] BYREF
  unsigned int v26[2]; // [rsp+50h] [rbp-30h] BYREF
  DWORD Type; // [rsp+58h] [rbp-28h] BYREF
  BYTE Data[4]; // [rsp+5Ch] [rbp-24h] BYREF
  DWORD cbData; // [rsp+60h] [rbp-20h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  v5 = a4;
  v23 = a4;
  v24 = a2;
  if ( a4 )
  {
    if ( !a5 )
    {
      v6 = -2147467261;
      v25 = -2147467261;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"No value result specified");
        *(_QWORD *)v26 = &v25;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          v9,
          3,
          (__int64)": {}",
          (__int64)v26);
      }
      v8 = 355;
      goto LABEL_5;
    }
    hKey = 0;
    v10 = HKEY_LOCAL_MACHINE;
    if ( a2 )
    {
      v11 = CbsRegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, a3, 0x20019u, &hKey);
      v12 = v11;
      if ( v11 == 2 || v11 == 3 )
      {
        v6 = (unsigned __int16)v11 | 0x80070000;
LABEL_37:
        Windows::AutoGenericHandleBase<HKEY__ *,0,Windows::AutoGenericHandle<HKEY__ *,0,&void Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>>::Close(&hKey);
        return v6;
      }
      if ( v11 )
      {
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (__int64)"Failed to open the registry root: n/a, key: {}.",
            (__int64)&v24);
          if ( v12 > 0 )
            v14 = (unsigned __int16)v12 | 0x80070000;
          else
            v14 = v12;
          v25 = v14;
          *(_QWORD *)v26 = &v25;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            v13,
            3,
            (__int64)": {0}",
            (__int64)v26);
        }
        v15 = 367;
LABEL_21:
        v6 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)v15,
               (unsigned int)"onecore\\base\\cbs\\util\\cbsreg.cpp",
               (const char *)(unsigned int)v12,
               lpDataa);
        goto LABEL_37;
      }
      v10 = hKey;
      v5 = v23;
    }
    Type = 0;
    *(_DWORD *)Data = 0;
    cbData = 4;
    v12 = RegQueryValueExW(v10, v5, 0, &Type, Data, &cbData);
    if ( v12 == 2 )
    {
      v6 = -2147024894;
      goto LABEL_37;
    }
    if ( !v12 )
    {
      if ( Type == 4 )
      {
        v6 = 0;
        *a5 = *(_DWORD *)Data;
      }
      else
      {
        v6 = -2147024883;
        v26[0] = -2147024883;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Registry value is not a DWORD type.");
          *(_QWORD *)v22 = v26;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            v18,
            3,
            (__int64)": {}",
            (__int64)v22);
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x17E,
          (unsigned int)"onecore\\base\\cbs\\util\\cbsreg.cpp",
          (const char *)0x8007000DLL,
          lpDataa);
      }
      goto LABEL_37;
    }
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (__int64)"Failed to query registry value: {}",
        (__int64)&v23);
      if ( v12 > 0 )
        v17 = (unsigned __int16)v12 | 0x80070000;
      else
        v17 = v12;
      v25 = v17;
      *(_QWORD *)v22 = &v25;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v16,
        3,
        (__int64)": {0}",
        (__int64)v22);
    }
    v15 = 380;
    goto LABEL_21;
  }
  v6 = -2147024809;
  v25 = -2147024809;
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(
      (__int64)LogAdapter::g_Logger,
      0,
      3,
      (struct Windows::Rtl::IRtlFormattedOutputStream *)"No value name specified");
    *(_QWORD *)v26 = &v25;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (__int64)LogAdapter::g_Logger,
      v7,
      3,
      (__int64)": {}",
      (__int64)v26);
  }
  v8 = 354;
LABEL_5:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"onecore\\base\\cbs\\util\\cbsreg.cpp",
    (const char *)v6,
    lpData);
  return v6;
}

```

## disassembly

```asm
0x14001121c  mov     [rsp-18h+arg_0], rbx
0x140011221  push    rbp
0x140011222  push    rsi
0x140011223  push    rdi
0x140011224  mov     rbp, rsp
0x140011227  sub     rsp, 80h
0x14001122e  mov     rax, cs:__security_cookie
0x140011235  xor     rax, rsp
0x140011238  mov     [rbp+var_10], rax
0x14001123c  mov     rsi, [rbp+arg_20]
0x140011240  mov     rax, r9
0x140011243  mov     [rbp+var_48], rax
0x140011247  mov     [rbp+var_40], rdx
0x14001124b  test    r9, r9
0x14001124e  jnz     short loc_1400112BC
0x140011250  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140011257  mov     ebx, 80070057h
0x14001125c  mov     [rbp+var_38], ebx
0x14001125f  test    rcx, rcx
0x140011262  jz      short loc_14001129F
0x140011264  lea     edi, [rax+3]
0x140011267  xor     edx, edx
0x140011269  mov     r8d, edi
0x14001126c  lea     r9, aNoValueNameSpe; "No value name specified"
0x140011273  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140011278  lea     rcx, [rbp+var_30]
0x14001127c  mov     r8d, edi
0x14001127f  mov     [rsp+80h+lpData], rcx; int
0x140011284  lea     rax, [rbp+var_38]
0x140011288  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001128f  lea     r9, asc_140030534; ": {}"
0x140011296  mov     qword ptr [rbp+var_30], rax
0x14001129a  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001129f  mov     edx, 162h; void *
0x1400112a4  mov     rcx, [rbp+18h]; this
0x1400112a8  lea     r8, aOnecoreBaseCbs_1; "onecore\\base\\cbs\\util\\cbsreg.cpp"
0x1400112af  mov     r9d, ebx; char *
0x1400112b2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400112b7  jmp     loc_140011526
0x1400112bc  test    rsi, rsi
0x1400112bf  jnz     short loc_140011317
0x1400112c1  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400112c8  mov     ebx, 80004003h
0x1400112cd  mov     [rbp+var_38], ebx
0x1400112d0  test    rcx, rcx
0x1400112d3  jz      short loc_140011310
0x1400112d5  lea     edi, [rsi+3]
0x1400112d8  xor     edx, edx
0x1400112da  mov     r8d, edi
0x1400112dd  lea     r9, aNoValueResultS; "No value result specified"
0x1400112e4  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1400112e9  lea     rcx, [rbp+var_30]
0x1400112ed  mov     r8d, edi
0x1400112f0  mov     [rsp+80h+lpData], rcx
0x1400112f5  lea     rax, [rbp+var_38]
0x1400112f9  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140011300  lea     r9, asc_140030534; ": {}"
0x140011307  mov     qword ptr [rbp+var_30], rax
0x14001130b  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140011310  mov     edx, 163h; wchar_t *
0x140011315  jmp     short loc_1400112A4
0x140011317  mov     [rbp+hKey], 0
0x14001131f  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x140011326  mov     edi, 3
0x14001132b  test    rdx, rdx
0x14001132e  jz      loc_1400113F4
0x140011334  lea     rax, [rbp+hKey]
0x140011338  mov     r9d, 20019h; unsigned int
0x14001133e  mov     [rsp+80h+lpData], rax; HKEY *
0x140011343  call    ?CbsRegOpenKeyExW@@YAKPEAUHKEY__@@PEB_WKKPEAPEAU1@@Z; CbsRegOpenKeyExW(HKEY__ *,wchar_t const *,ulong,ulong,HKEY__ * *)
0x140011348  mov     ebx, eax
0x14001134a  cmp     eax, 2
0x14001134d  jz      short loc_14001135B
0x14001134f  cmp     eax, edi
0x140011351  jnz     short loc_140011369
0x140011353  test    eax, eax
0x140011355  jle     loc_14001151D
0x14001135b  movzx   ebx, bx
0x14001135e  or      ebx, 80070000h
0x140011364  jmp     loc_14001151D
0x140011369  test    ebx, ebx
0x14001136b  jz      short loc_1400113EC
0x14001136d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140011374  test    rcx, rcx
0x140011377  jz      short loc_1400113CD
0x140011379  lea     rax, [rbp+var_40]
0x14001137d  mov     r8d, edi
0x140011380  lea     r9, aFailedToOpenTh; "Failed to open the registry root: n/a, "...
0x140011387  mov     [rsp+80h+lpData], rax
0x14001138c  xor     edx, edx
0x14001138e  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x140011393  test    ebx, ebx
0x140011395  jg      short loc_14001139B
0x140011397  mov     eax, ebx
0x140011399  jmp     short loc_1400113A3
0x14001139b  movzx   eax, bx
0x14001139e  or      eax, 80070000h
0x1400113a3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400113aa  lea     r9, a0; ": {0}"
0x1400113b1  mov     [rbp+var_38], eax
0x1400113b4  mov     r8d, edi
0x1400113b7  lea     rax, [rbp+var_38]
0x1400113bb  mov     qword ptr [rbp+var_30], rax
0x1400113bf  lea     rax, [rbp+var_30]
0x1400113c3  mov     [rsp+80h+lpData], rax; unsigned int
0x1400113c8  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1400113cd  mov     edx, 16Fh; void *
0x1400113d2  mov     rcx, [rbp+18h]; this
0x1400113d6  lea     r8, aOnecoreBaseCbs_1; "onecore\\base\\cbs\\util\\cbsreg.cpp"
0x1400113dd  mov     r9d, ebx; char *
0x1400113e0  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1400113e5  mov     ebx, eax
0x1400113e7  jmp     loc_14001151D
0x1400113ec  mov     rcx, [rbp+hKey]; hKey
0x1400113f0  mov     rax, [rbp+var_48]
0x1400113f4  lea     rdx, [rbp+cbData]
0x1400113f8  mov     [rbp+Type], 0
0x1400113ff  mov     [rsp+80h+lpcbData], rdx; lpcbData
0x140011404  lea     r9, [rbp+Type]; lpType
0x140011408  lea     rdx, [rbp+Data]
0x14001140c  mov     dword ptr [rbp+Data], 0
0x140011413  mov     [rsp+80h+lpData], rdx; lpData
0x140011418  xor     r8d, r8d; lpReserved
0x14001141b  mov     rdx, rax; lpValueName
0x14001141e  mov     [rbp+cbData], 4
0x140011425  call    cs:__imp_RegQueryValueExW
0x14001142b  mov     ebx, eax
0x14001142d  cmp     eax, 2
0x140011430  jnz     short loc_14001143C
0x140011432  mov     ebx, 80070002h
0x140011437  jmp     loc_14001151D
0x14001143c  test    ebx, ebx
0x14001143e  jz      short loc_1400114AA
0x140011440  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140011447  test    rcx, rcx
0x14001144a  jz      short loc_1400114A0
0x14001144c  lea     rax, [rbp+var_48]
0x140011450  mov     r8d, edi
0x140011453  lea     r9, aFailedToQueryR; "Failed to query registry value: {}"
0x14001145a  mov     [rsp+80h+lpData], rax
0x14001145f  xor     edx, edx
0x140011461  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x140011466  test    ebx, ebx
0x140011468  jg      short loc_14001146E
0x14001146a  mov     eax, ebx
0x14001146c  jmp     short loc_140011476
0x14001146e  movzx   eax, bx
0x140011471  or      eax, 80070000h
0x140011476  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001147d  lea     r9, a0; ": {0}"
0x140011484  mov     [rbp+var_38], eax
0x140011487  mov     r8d, edi
0x14001148a  lea     rax, [rbp+var_38]
0x14001148e  mov     qword ptr [rbp+var_50], rax
0x140011492  lea     rax, [rbp+var_50]
0x140011496  mov     [rsp+80h+lpData], rax
0x14001149b  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1400114a0  mov     edx, 17Ch
0x1400114a5  jmp     loc_1400113D2
0x1400114aa  cmp     [rbp+Type], 4
0x1400114ae  jz      short loc_140011516
0x1400114b0  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400114b7  mov     ebx, 8007000Dh
0x1400114bc  mov     [rbp+var_30], ebx
0x1400114bf  test    rcx, rcx
0x1400114c2  jz      short loc_1400114FC
0x1400114c4  lea     r9, aRegistryValueI_0; "Registry value is not a DWORD type."
0x1400114cb  mov     r8d, edi
0x1400114ce  xor     edx, edx
0x1400114d0  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1400114d5  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400114dc  lea     rax, [rbp+var_30]
0x1400114e0  mov     qword ptr [rbp+var_50], rax
0x1400114e4  lea     r9, asc_140030534; ": {}"
0x1400114eb  lea     rax, [rbp+var_50]
0x1400114ef  mov     r8d, edi
0x1400114f2  mov     [rsp+80h+lpData], rax; int
0x1400114f7  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1400114fc  mov     rcx, [rbp+18h]; this
0x140011500  lea     r8, aOnecoreBaseCbs_1; "onecore\\base\\cbs\\util\\cbsreg.cpp"
0x140011507  mov     r9d, ebx; char *
0x14001150a  mov     edx, 17Eh; void *
0x14001150f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140011514  jmp     short loc_14001151D
0x140011516  mov     eax, dword ptr [rbp+Data]
0x140011519  xor     ebx, ebx
0x14001151b  mov     [rsi], eax
0x14001151d  lea     rcx, [rbp+hKey]
0x140011521  call    ?Close@?$AutoGenericHandleBase@PEAUHKEY__@@$0A@V?$AutoGenericHandle@PEAUHKEY__@@$0A@$1?CloseWithRegCloseKey@Detail@Windows@@YAXPEAU1@@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<HKEY__ *,0,Windows::AutoGenericHandle<HKEY__ *,0,&Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>>::Close(void)
0x140011526  mov     eax, ebx
0x140011528  mov     rcx, [rbp+var_10]
0x14001152c  xor     rcx, rsp; StackCookie
0x14001152f  call    __security_check_cookie
0x140011534  mov     rbx, [rsp+80h+arg_0]
0x14001153c  add     rsp, 80h
0x140011543  pop     rdi
0x140011544  pop     rsi
0x140011545  pop     rbp
0x140011546  retn
```
