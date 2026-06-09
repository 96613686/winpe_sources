# CbsRegQueryDWORDValue(HKEY__ *,wchar_t const *,ulong,wchar_t const *,ulong *)

- ea: `0x14001a16c`
- end: `0x14001a4ba`
- name: `?CbsRegQueryDWORDValue@@YAJPEAUHKEY__@@PEB_WK1PEAK@Z`
- size: `846`
- prototype: `__int64 __fastcall(HKEY, const wchar_t *, char, const wchar_t *, unsigned int *)`
- caller_count: `11`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140009b2c`
- `0x140012540`
- `0x140013414`
- `0x140016098`
- `0x140018630`
- `0x140019828`
- `0x140019878`
- `0x14001bd98`
- `0x140020f38`
- `0x140020ffc`
- `0x14002126c`

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
- `0x14001a16c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14001a393`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14001a393`

## string_xrefs

- `0x14001a2e7`: `Failed to open the registry root: n/a, key: {}.`
- `0x14001a3c2`: `Failed to query registry value: {}`
- `0x14001a431`: `Registry value is not a DWORD type.`

## pseudocode

```c
__int64 __fastcall CbsRegQueryDWORDValue(HKEY a1, const wchar_t *a2, char a3, const wchar_t *a4, unsigned int *a5)
{
  const WCHAR *v5; // rax
  unsigned int v6; // ebx
  int v7; // edx
  __int64 v8; // rdx
  int v9; // edx
  int v10; // esi
  HKEY *InitPointer; // rax
  unsigned int v12; // r8d
  unsigned int v13; // eax
  int v14; // edx
  int v15; // r8d
  int v16; // ebx
  int v17; // edx
  unsigned int v18; // eax
  __int64 v19; // rdx
  __int64 v20; // rcx
  LSTATUS v21; // eax
  int v22; // edx
  int v23; // r8d
  int v24; // edx
  unsigned int v25; // eax
  int v26; // edx
  int lpData; // [rsp+20h] [rbp-60h]
  unsigned int lpDataa; // [rsp+20h] [rbp-60h]
  int v30[2]; // [rsp+30h] [rbp-50h] BYREF
  LPCWSTR lpSubKey; // [rsp+38h] [rbp-48h] BYREF
  LPCWSTR lpValueName; // [rsp+40h] [rbp-40h] BYREF
  int v33; // [rsp+48h] [rbp-38h] BYREF
  unsigned int v34[2]; // [rsp+50h] [rbp-30h] BYREF
  DWORD Type; // [rsp+58h] [rbp-28h] BYREF
  BYTE Data[4]; // [rsp+5Ch] [rbp-24h] BYREF
  DWORD cbData; // [rsp+60h] [rbp-20h] BYREF
  __int64 v38; // [rsp+68h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  v5 = a4;
  lpValueName = a4;
  lpSubKey = a2;
  if ( a4 )
  {
    if ( !a5 )
    {
      v6 = -2147467261;
      v33 = -2147467261;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No value result specified");
        *(_QWORD *)v34 = &v33;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v9,
          3,
          (unsigned int)": {}",
          (__int64)v34);
      }
      v8 = 355;
      goto LABEL_5;
    }
    v10 = a3 & 1;
    v38 = 0;
    if ( a2 )
    {
      InitPointer = (HKEY *)Windows::AutoComPtr<IClassFactory>::GetInitPointer(&v38);
      v13 = CbsRegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, v12, 0x20019u, InitPointer);
      v16 = v13;
      if ( v10 && (v13 == 2 || v13 == 3) )
      {
        v6 = (unsigned __int16)v13 | 0x80070000;
LABEL_40:
        Windows::AutoGenericHandleBase<HKEY__ *,0,Windows::AutoGenericHandle<HKEY__ *,0,&void Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>>::Close(&v38);
        return v6;
      }
      if ( v13 )
      {
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            (_DWORD)LogAdapter::g_Logger,
            v14,
            v15,
            (unsigned int)"Failed to open the registry root: n/a, key: {}.",
            (__int64)&lpSubKey);
          if ( v16 > 0 )
            v18 = (unsigned __int16)v16 | 0x80070000;
          else
            v18 = v16;
          v33 = v18;
          *(_QWORD *)v34 = &v33;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v17,
            3,
            (unsigned int)": {0}",
            (__int64)v34);
        }
        v19 = 367;
LABEL_22:
        v6 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)v19,
               (unsigned int)"onecore\\base\\cbs\\util\\cbsreg.cpp",
               (const char *)(unsigned int)v16,
               lpDataa);
        goto LABEL_40;
      }
      v20 = v38;
      v5 = lpValueName;
    }
    else
    {
      v20 = -2147483646;
    }
    Type = 0;
    *(_DWORD *)Data = 0;
    cbData = 4;
    v21 = RegQueryValueExW((HKEY)v20, v5, 0, &Type, Data, &cbData);
    v16 = v21;
    if ( v10 && v21 == 2 )
    {
      v6 = -2147024894;
      goto LABEL_40;
    }
    if ( !v21 )
    {
      if ( Type == 4 )
      {
        v6 = 0;
        *a5 = *(_DWORD *)Data;
      }
      else
      {
        v6 = -2147024883;
        v34[0] = -2147024883;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Registry value is not a DWORD type.");
          *(_QWORD *)v30 = v34;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v26,
            3,
            (unsigned int)": {}",
            (__int64)v30);
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x17E,
          (unsigned int)"onecore\\base\\cbs\\util\\cbsreg.cpp",
          (const char *)0x8007000DLL,
          lpDataa);
      }
      goto LABEL_40;
    }
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (_DWORD)LogAdapter::g_Logger,
        v22,
        v23,
        (unsigned int)"Failed to query registry value: {}",
        (__int64)&lpValueName);
      if ( v16 > 0 )
        v25 = (unsigned __int16)v16 | 0x80070000;
      else
        v25 = v16;
      v33 = v25;
      *(_QWORD *)v30 = &v33;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v24,
        3,
        (unsigned int)": {0}",
        (__int64)v30);
    }
    v19 = 380;
    goto LABEL_22;
  }
  v6 = -2147024809;
  v33 = -2147024809;
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No value name specified");
    *(_QWORD *)v34 = &v33;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (_DWORD)LogAdapter::g_Logger,
      v7,
      3,
      (unsigned int)": {}",
      (__int64)v34);
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
0x14001a16c  mov     [rsp-18h+arg_0], rbx
0x14001a171  mov     [rsp-18h+arg_10], rsi
0x14001a176  push    rbp
0x14001a177  push    rdi
0x14001a178  push    r14
0x14001a17a  mov     rbp, rsp
0x14001a17d  sub     rsp, 80h
0x14001a184  mov     rax, cs:__security_cookie
0x14001a18b  xor     rax, rsp
0x14001a18e  mov     [rbp+var_10], rax
0x14001a192  mov     r14, [rbp+arg_20]
0x14001a196  mov     rax, r9
0x14001a199  mov     [rbp+lpValueName], rax
0x14001a19d  mov     esi, r8d
0x14001a1a0  mov     [rbp+lpSubKey], rdx
0x14001a1a4  test    r9, r9
0x14001a1a7  jnz     short loc_14001A215
0x14001a1a9  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001a1b0  mov     ebx, 80070057h
0x14001a1b5  mov     [rbp+var_38], ebx
0x14001a1b8  test    rcx, rcx
0x14001a1bb  jz      short loc_14001A1F8
0x14001a1bd  lea     edi, [rax+3]
0x14001a1c0  xor     edx, edx
0x14001a1c2  mov     r8d, edi
0x14001a1c5  lea     r9, aNoValueNameSpe; "No value name specified"
0x14001a1cc  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14001a1d1  lea     rcx, [rbp+var_30]
0x14001a1d5  mov     r8d, edi
0x14001a1d8  mov     [rsp+80h+lpData], rcx; int
0x14001a1dd  lea     rax, [rbp+var_38]
0x14001a1e1  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001a1e8  lea     r9, asc_1400353E8; ": {}"
0x14001a1ef  mov     qword ptr [rbp+var_30], rax
0x14001a1f3  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001a1f8  mov     edx, 162h; void *
0x14001a1fd  mov     rcx, [rbp+18h]; this
0x14001a201  lea     r8, aOnecoreBaseCbs_5; "onecore\\base\\cbs\\util\\cbsreg.cpp"
0x14001a208  mov     r9d, ebx; char *
0x14001a20b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001a210  jmp     loc_14001A494
0x14001a215  test    r14, r14
0x14001a218  jnz     short loc_14001A271
0x14001a21a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001a221  mov     ebx, 80004003h
0x14001a226  mov     [rbp+var_38], ebx
0x14001a229  test    rcx, rcx
0x14001a22c  jz      short loc_14001A26A
0x14001a22e  lea     edi, [r14+3]
0x14001a232  xor     edx, edx
0x14001a234  mov     r8d, edi
0x14001a237  lea     r9, aNoValueResultS; "No value result specified"
0x14001a23e  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14001a243  lea     rcx, [rbp+var_30]
0x14001a247  mov     r8d, edi
0x14001a24a  mov     [rsp+80h+lpData], rcx
0x14001a24f  lea     rax, [rbp+var_38]
0x14001a253  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001a25a  lea     r9, asc_1400353E8; ": {}"
0x14001a261  mov     qword ptr [rbp+var_30], rax
0x14001a265  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001a26a  mov     edx, 163h
0x14001a26f  jmp     short loc_14001A1FD
0x14001a271  and     esi, 1
0x14001a274  mov     [rbp+var_18], 0
0x14001a27c  mov     edi, 3
0x14001a281  test    rdx, rdx
0x14001a284  jz      loc_14001A35B
0x14001a28a  lea     rcx, [rbp+var_18]
0x14001a28e  call    ?GetInitPointer@?$AutoComPtr@UIClassFactory@@@Windows@@QEAAPEAPEAUIClassFactory@@XZ; Windows::AutoComPtr<IClassFactory>::GetInitPointer(void)
0x14001a293  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x14001a297  mov     r9d, 20019h; unsigned int
0x14001a29d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14001a2a4  mov     [rsp+80h+lpData], rax; HKEY *
0x14001a2a9  call    ?CbsRegOpenKeyExW@@YAKPEAUHKEY__@@PEB_WKKPEAPEAU1@@Z; CbsRegOpenKeyExW(HKEY__ *,wchar_t const *,ulong,ulong,HKEY__ * *)
0x14001a2ae  mov     ebx, eax
0x14001a2b0  test    esi, esi
0x14001a2b2  jz      short loc_14001A2D3
0x14001a2b4  cmp     eax, 2
0x14001a2b7  jz      short loc_14001A2C5
0x14001a2b9  cmp     eax, edi
0x14001a2bb  jnz     short loc_14001A2D3
0x14001a2bd  test    eax, eax
0x14001a2bf  jle     loc_14001A48B
0x14001a2c5  movzx   ebx, bx
0x14001a2c8  or      ebx, 80070000h
0x14001a2ce  jmp     loc_14001A48B
0x14001a2d3  test    ebx, ebx
0x14001a2d5  jz      short loc_14001A351
0x14001a2d7  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001a2de  test    rcx, rcx
0x14001a2e1  jz      short loc_14001A332
0x14001a2e3  lea     rax, [rbp+lpSubKey]
0x14001a2e7  lea     r9, aFailedToOpenTh; "Failed to open the registry root: n/a, "...
0x14001a2ee  mov     [rsp+80h+lpData], rax
0x14001a2f3  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x14001a2f8  test    ebx, ebx
0x14001a2fa  jg      short loc_14001A300
0x14001a2fc  mov     eax, ebx
0x14001a2fe  jmp     short loc_14001A308
0x14001a300  movzx   eax, bx
0x14001a303  or      eax, 80070000h
0x14001a308  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001a30f  lea     r9, a0; ": {0}"
0x14001a316  mov     [rbp+var_38], eax
0x14001a319  mov     r8d, edi
0x14001a31c  lea     rax, [rbp+var_38]
0x14001a320  mov     qword ptr [rbp+var_30], rax
0x14001a324  lea     rax, [rbp+var_30]
0x14001a328  mov     [rsp+80h+lpData], rax; unsigned int
0x14001a32d  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001a332  mov     edx, 16Fh; void *
0x14001a337  mov     rcx, [rbp+18h]; this
0x14001a33b  lea     r8, aOnecoreBaseCbs_5; "onecore\\base\\cbs\\util\\cbsreg.cpp"
0x14001a342  mov     r9d, ebx; char *
0x14001a345  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x14001a34a  mov     ebx, eax
0x14001a34c  jmp     loc_14001A48B
0x14001a351  mov     rcx, [rbp+var_18]
0x14001a355  mov     rax, [rbp+lpValueName]
0x14001a359  jmp     short loc_14001A362
0x14001a35b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14001a362  lea     rdx, [rbp+cbData]
0x14001a366  mov     [rbp+Type], 0
0x14001a36d  mov     [rsp+80h+lpcbData], rdx; lpcbData
0x14001a372  lea     r9, [rbp+Type]; lpType
0x14001a376  lea     rdx, [rbp+Data]
0x14001a37a  mov     dword ptr [rbp+Data], 0
0x14001a381  mov     [rsp+80h+lpData], rdx; lpData
0x14001a386  xor     r8d, r8d; lpReserved
0x14001a389  mov     rdx, rax; lpValueName
0x14001a38c  mov     [rbp+cbData], 4
0x14001a393  call    cs:__imp_RegQueryValueExW
0x14001a399  mov     ebx, eax
0x14001a39b  test    esi, esi
0x14001a39d  jz      short loc_14001A3AE
0x14001a39f  cmp     eax, 2
0x14001a3a2  jnz     short loc_14001A3AE
0x14001a3a4  mov     ebx, 80070002h
0x14001a3a9  jmp     loc_14001A48B
0x14001a3ae  test    ebx, ebx
0x14001a3b0  jz      short loc_14001A417
0x14001a3b2  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001a3b9  test    rcx, rcx
0x14001a3bc  jz      short loc_14001A40D
0x14001a3be  lea     rax, [rbp+lpValueName]
0x14001a3c2  lea     r9, aFailedToQueryR; "Failed to query registry value: {}"
0x14001a3c9  mov     [rsp+80h+lpData], rax
0x14001a3ce  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x14001a3d3  test    ebx, ebx
0x14001a3d5  jg      short loc_14001A3DB
0x14001a3d7  mov     eax, ebx
0x14001a3d9  jmp     short loc_14001A3E3
0x14001a3db  movzx   eax, bx
0x14001a3de  or      eax, 80070000h
0x14001a3e3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001a3ea  lea     r9, a0; ": {0}"
0x14001a3f1  mov     [rbp+var_38], eax
0x14001a3f4  mov     r8d, edi
0x14001a3f7  lea     rax, [rbp+var_38]
0x14001a3fb  mov     qword ptr [rbp+var_50], rax
0x14001a3ff  lea     rax, [rbp+var_50]
0x14001a403  mov     [rsp+80h+lpData], rax
0x14001a408  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001a40d  mov     edx, 17Ch
0x14001a412  jmp     loc_14001A337
0x14001a417  cmp     [rbp+Type], 4
0x14001a41b  jz      short loc_14001A483
0x14001a41d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001a424  mov     ebx, 8007000Dh
0x14001a429  mov     [rbp+var_30], ebx
0x14001a42c  test    rcx, rcx
0x14001a42f  jz      short loc_14001A469
0x14001a431  lea     r9, aRegistryValueI_1; "Registry value is not a DWORD type."
0x14001a438  mov     r8d, edi
0x14001a43b  xor     edx, edx
0x14001a43d  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14001a442  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001a449  lea     rax, [rbp+var_30]
0x14001a44d  mov     qword ptr [rbp+var_50], rax
0x14001a451  lea     r9, asc_1400353E8; ": {}"
0x14001a458  lea     rax, [rbp+var_50]
0x14001a45c  mov     r8d, edi
0x14001a45f  mov     [rsp+80h+lpData], rax; int
0x14001a464  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001a469  mov     rcx, [rbp+18h]; this
0x14001a46d  lea     r8, aOnecoreBaseCbs_5; "onecore\\base\\cbs\\util\\cbsreg.cpp"
0x14001a474  mov     r9d, ebx; char *
0x14001a477  mov     edx, 17Eh; void *
0x14001a47c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001a481  jmp     short loc_14001A48B
0x14001a483  mov     eax, dword ptr [rbp+Data]
0x14001a486  xor     ebx, ebx
0x14001a488  mov     [r14], eax
0x14001a48b  lea     rcx, [rbp+var_18]
0x14001a48f  call    ?Close@?$AutoGenericHandleBase@PEAUHKEY__@@$0A@V?$AutoGenericHandle@PEAUHKEY__@@$0A@$1?CloseWithRegCloseKey@Detail@Windows@@YAXPEAU1@@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<HKEY__ *,0,Windows::AutoGenericHandle<HKEY__ *,0,&Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>>::Close(void)
0x14001a494  mov     eax, ebx
0x14001a496  mov     rcx, [rbp+var_10]
0x14001a49a  xor     rcx, rsp; StackCookie
0x14001a49d  call    __security_check_cookie
0x14001a4a2  lea     r11, [rsp+80h+var_s0]
0x14001a4aa  mov     rbx, [r11+20h]
0x14001a4ae  mov     rsi, [r11+30h]
0x14001a4b2  mov     rsp, r11
0x14001a4b5  pop     r14
0x14001a4b7  pop     rdi
0x14001a4b8  pop     rbp
0x14001a4b9  retn
```
