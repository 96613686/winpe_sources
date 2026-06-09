# CbsRegQueryQWORDValue(HKEY__ *,wchar_t const *,ulong,wchar_t const *,unsigned __int64 *)

- ea: `0x14001a4c0`
- end: `0x14001a7de`
- name: `?CbsRegQueryQWORDValue@@YAJPEAUHKEY__@@PEB_WK1PEA_K@Z`
- size: `798`
- prototype: `__int64 __fastcall(HKEY, const wchar_t *, __int64, const wchar_t *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x140020ffc`

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
- `0x14001a4c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14001a6e1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14001a6e1`

## string_xrefs

- `0x14001a640`: `Failed to open the registry root: n/a, key: {}.`
- `0x14001a70c`: `Failed to query registry value: {}`
- `0x14001a77b`: `Registry value is not a QWORD type.`
- `0x14001a4e3`: `SOFTWARE\Microsoft\Windows\CurrentVersion\SideBySide`

## pseudocode

```c
__int64 __fastcall CbsRegQueryQWORDValue(
        HKEY a1,
        const wchar_t *a2,
        __int64 a3,
        const wchar_t *a4,
        unsigned __int64 *a5)
{
  unsigned int v5; // ebx
  __int64 v6; // rdx
  __int64 v7; // rdx
  __int64 v8; // rdx
  HKEY *InitPointer; // rax
  __int64 v10; // r8
  LSTATUS v11; // eax
  __int64 v12; // rdx
  __int64 v13; // r8
  LSTATUS v14; // ebx
  __int64 v16; // rdx
  unsigned int v17; // eax
  __int64 v18; // rdx
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // rdx
  unsigned int v22; // eax
  __int64 v23; // rdx
  int lpData; // [rsp+20h] [rbp-41h]
  unsigned int lpDataa; // [rsp+20h] [rbp-41h]
  int v26[2]; // [rsp+30h] [rbp-31h] BYREF
  LPCWSTR lpSubKey[2]; // [rsp+40h] [rbp-21h] BYREF
  LPCWSTR lpValueName; // [rsp+50h] [rbp-11h] BYREF
  int v29; // [rsp+58h] [rbp-9h] BYREF
  unsigned int v30[2]; // [rsp+60h] [rbp-1h] BYREF
  DWORD Type; // [rsp+68h] [rbp+7h] BYREF
  DWORD cbData; // [rsp+6Ch] [rbp+Bh] BYREF
  HKEY hKey; // [rsp+70h] [rbp+Fh] BYREF
  BYTE Data[8]; // [rsp+78h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+57h]

  lpSubKey[0] = L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\SideBySide";
  lpValueName = a4;
  if ( a4 )
  {
    if ( !a5 )
    {
      v5 = -2147467261;
      v29 = -2147467261;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"No value result specified");
        *(_QWORD *)v30 = &v29;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          v8,
          3,
          (__int64)": {}",
          (__int64)v30);
      }
      v7 = 397;
      goto LABEL_5;
    }
    hKey = 0;
    InitPointer = (HKEY *)Windows::AutoComPtr<IClassFactory>::GetInitPointer(&hKey);
    v11 = CbsRegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey[0], v10, 0x20019u, InitPointer);
    v14 = v11;
    if ( v11 == 2 || v11 == 3 )
    {
      v5 = (unsigned __int16)v11 | 0x80070000;
    }
    else
    {
      if ( v11 )
      {
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            (__int64)LogAdapter::g_Logger,
            v12,
            v13,
            (__int64)"Failed to open the registry root: n/a, key: {}.",
            (__int64)lpSubKey);
          if ( v14 > 0 )
            v17 = (unsigned __int16)v14 | 0x80070000;
          else
            v17 = v14;
          v29 = v17;
          *(_QWORD *)v30 = &v29;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            v16,
            3,
            (__int64)": {0}",
            (__int64)v30);
        }
        v18 = 409;
      }
      else
      {
        Type = 0;
        *(_QWORD *)Data = 0;
        cbData = 8;
        v14 = RegQueryValueExW(hKey, lpValueName, 0, &Type, Data, &cbData);
        if ( v14 == 2 )
        {
          v5 = -2147024894;
          goto LABEL_13;
        }
        if ( !v14 )
        {
          if ( Type == 11 )
          {
            v5 = 0;
            *a5 = *(_QWORD *)Data;
          }
          else
          {
            v5 = -2147024883;
            v30[0] = -2147024883;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                (__int64)LogAdapter::g_Logger,
                0,
                3,
                (struct Windows::Rtl::IRtlFormattedOutputStream *)"Registry value is not a QWORD type.");
              *(_QWORD *)v26 = v30;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (__int64)LogAdapter::g_Logger,
                v23,
                3,
                (__int64)": {}",
                (__int64)v26);
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1A8,
              (unsigned int)"onecore\\base\\cbs\\util\\cbsreg.cpp",
              (const char *)0x8007000DLL,
              lpDataa);
          }
          goto LABEL_13;
        }
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            (__int64)LogAdapter::g_Logger,
            v19,
            v20,
            (__int64)"Failed to query registry value: {}",
            (__int64)&lpValueName);
          if ( v14 > 0 )
            v22 = (unsigned __int16)v14 | 0x80070000;
          else
            v22 = v14;
          v29 = v22;
          *(_QWORD *)v26 = &v29;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            v21,
            3,
            (__int64)": {0}",
            (__int64)v26);
        }
        v18 = 422;
      }
      v5 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v18,
             (unsigned int)"onecore\\base\\cbs\\util\\cbsreg.cpp",
             (const char *)(unsigned int)v14,
             lpDataa);
    }
LABEL_13:
    Windows::AutoGenericHandleBase<HKEY__ *,0,Windows::AutoGenericHandle<HKEY__ *,0,&void Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>>::Close(&hKey);
    return v5;
  }
  v5 = -2147024809;
  v29 = -2147024809;
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(
      (__int64)LogAdapter::g_Logger,
      0,
      3,
      (struct Windows::Rtl::IRtlFormattedOutputStream *)"No value name specified");
    *(_QWORD *)v30 = &v29;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (__int64)LogAdapter::g_Logger,
      v6,
      3,
      (__int64)": {}",
      (__int64)v30);
  }
  v7 = 396;
LABEL_5:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v7,
    (unsigned int)"onecore\\base\\cbs\\util\\cbsreg.cpp",
    (const char *)v5,
    lpData);
  return v5;
}

```

## disassembly

```asm
0x14001a4c0  push    rbp
0x14001a4c2  push    rbx
0x14001a4c3  push    rsi
0x14001a4c4  push    rdi
0x14001a4c5  lea     rbp, [rsp-37h]
0x14001a4ca  sub     rsp, 98h
0x14001a4d1  mov     rax, cs:__security_cookie
0x14001a4d8  xor     rax, rsp
0x14001a4db  mov     [rbp+4Fh+var_30], rax
0x14001a4df  mov     rsi, [rbp+4Fh+arg_20]
0x14001a4e3  lea     rax, aSoftwareMicros_8; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x14001a4ea  mov     [rbp+4Fh+lpSubKey], rax
0x14001a4ee  mov     [rbp+4Fh+lpValueName], r9
0x14001a4f2  test    r9, r9
0x14001a4f5  jnz     short loc_14001A565
0x14001a4f7  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001a4fe  mov     ebx, 80070057h
0x14001a503  mov     [rbp+4Fh+var_58], ebx
0x14001a506  test    rcx, rcx
0x14001a509  jz      short loc_14001A548
0x14001a50b  mov     edi, 3
0x14001a510  lea     r9, aNoValueNameSpe; "No value name specified"
0x14001a517  mov     r8d, edi
0x14001a51a  xor     edx, edx
0x14001a51c  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14001a521  lea     rcx, [rbp+4Fh+var_50]
0x14001a525  mov     r8d, edi
0x14001a528  mov     [rsp+0B0h+lpData], rcx; int
0x14001a52d  lea     rax, [rbp+4Fh+var_58]
0x14001a531  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001a538  lea     r9, asc_1400353E8; ": {}"
0x14001a53f  mov     qword ptr [rbp+4Fh+var_50], rax
0x14001a543  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001a548  mov     edx, 18Ch; void *
0x14001a54d  mov     rcx, [rbp+57h]; this
0x14001a551  lea     r8, aOnecoreBaseCbs_5; "onecore\\base\\cbs\\util\\cbsreg.cpp"
0x14001a558  mov     r9d, ebx; char *
0x14001a55b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001a560  jmp     loc_14001A612
0x14001a565  test    rsi, rsi
0x14001a568  jnz     short loc_14001A5C0
0x14001a56a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001a571  mov     ebx, 80004003h
0x14001a576  mov     [rbp+4Fh+var_58], ebx
0x14001a579  test    rcx, rcx
0x14001a57c  jz      short loc_14001A5B9
0x14001a57e  lea     edi, [rsi+3]
0x14001a581  xor     edx, edx
0x14001a583  mov     r8d, edi
0x14001a586  lea     r9, aNoValueResultS; "No value result specified"
0x14001a58d  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14001a592  lea     rcx, [rbp+4Fh+var_50]
0x14001a596  mov     r8d, edi
0x14001a599  mov     [rsp+0B0h+lpData], rcx
0x14001a59e  lea     rax, [rbp+4Fh+var_58]
0x14001a5a2  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001a5a9  lea     r9, asc_1400353E8; ": {}"
0x14001a5b0  mov     qword ptr [rbp+4Fh+var_50], rax
0x14001a5b4  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001a5b9  mov     edx, 18Dh
0x14001a5be  jmp     short loc_14001A54D
0x14001a5c0  lea     rcx, [rbp+4Fh+hKey]
0x14001a5c4  mov     [rbp+4Fh+hKey], 0
0x14001a5cc  call    ?GetInitPointer@?$AutoComPtr@UIClassFactory@@@Windows@@QEAAPEAPEAUIClassFactory@@XZ; Windows::AutoComPtr<IClassFactory>::GetInitPointer(void)
0x14001a5d1  mov     rdx, [rbp+4Fh+lpSubKey]; lpSubKey
0x14001a5d5  mov     r9d, 20019h; unsigned int
0x14001a5db  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14001a5e2  mov     [rsp+0B0h+lpData], rax; HKEY *
0x14001a5e7  call    ?CbsRegOpenKeyExW@@YAKPEAUHKEY__@@PEB_WKKPEAPEAU1@@Z; CbsRegOpenKeyExW(HKEY__ *,wchar_t const *,ulong,ulong,HKEY__ * *)
0x14001a5ec  mov     ebx, eax
0x14001a5ee  cmp     eax, 2
0x14001a5f1  jz      short loc_14001A600
0x14001a5f3  mov     edi, 3
0x14001a5f8  cmp     eax, edi
0x14001a5fa  jnz     short loc_14001A62C
0x14001a5fc  test    eax, eax
0x14001a5fe  jle     short loc_14001A609
0x14001a600  movzx   ebx, bx
0x14001a603  or      ebx, 80070000h
0x14001a609  lea     rcx, [rbp+4Fh+hKey]
0x14001a60d  call    ?Close@?$AutoGenericHandleBase@PEAUHKEY__@@$0A@V?$AutoGenericHandle@PEAUHKEY__@@$0A@$1?CloseWithRegCloseKey@Detail@Windows@@YAXPEAU1@@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<HKEY__ *,0,Windows::AutoGenericHandle<HKEY__ *,0,&Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>>::Close(void)
0x14001a612  mov     eax, ebx
0x14001a614  mov     rcx, [rbp+4Fh+var_30]
0x14001a618  xor     rcx, rsp; StackCookie
0x14001a61b  call    __security_check_cookie
0x14001a620  add     rsp, 98h
0x14001a627  pop     rdi
0x14001a628  pop     rsi
0x14001a629  pop     rbx
0x14001a62a  pop     rbp
0x14001a62b  retn
0x14001a62c  test    ebx, ebx
0x14001a62e  jz      short loc_14001A6AA
0x14001a630  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001a637  test    rcx, rcx
0x14001a63a  jz      short loc_14001A68B
0x14001a63c  lea     rax, [rbp+4Fh+lpSubKey]
0x14001a640  lea     r9, aFailedToOpenTh; "Failed to open the registry root: n/a, "...
0x14001a647  mov     [rsp+0B0h+lpData], rax
0x14001a64c  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x14001a651  test    ebx, ebx
0x14001a653  jg      short loc_14001A659
0x14001a655  mov     eax, ebx
0x14001a657  jmp     short loc_14001A661
0x14001a659  movzx   eax, bx
0x14001a65c  or      eax, 80070000h
0x14001a661  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001a668  lea     r9, a0; ": {0}"
0x14001a66f  mov     [rbp+4Fh+var_58], eax
0x14001a672  mov     r8d, edi
0x14001a675  lea     rax, [rbp+4Fh+var_58]
0x14001a679  mov     qword ptr [rbp+4Fh+var_50], rax
0x14001a67d  lea     rax, [rbp+4Fh+var_50]
0x14001a681  mov     [rsp+0B0h+lpData], rax; unsigned int
0x14001a686  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001a68b  mov     edx, 199h; void *
0x14001a690  mov     rcx, [rbp+57h]; this
0x14001a694  lea     r8, aOnecoreBaseCbs_5; "onecore\\base\\cbs\\util\\cbsreg.cpp"
0x14001a69b  mov     r9d, ebx; char *
0x14001a69e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x14001a6a3  mov     ebx, eax
0x14001a6a5  jmp     loc_14001A609
0x14001a6aa  mov     rdx, [rbp+4Fh+lpValueName]; lpValueName
0x14001a6ae  lea     rax, [rbp+4Fh+cbData]
0x14001a6b2  mov     rcx, [rbp+4Fh+hKey]; hKey
0x14001a6b6  lea     r9, [rbp+4Fh+Type]; lpType
0x14001a6ba  mov     [rsp+0B0h+lpcbData], rax; lpcbData
0x14001a6bf  xor     r8d, r8d; lpReserved
0x14001a6c2  lea     rax, [rbp+4Fh+Data]
0x14001a6c6  mov     [rbp+4Fh+Type], 0
0x14001a6cd  mov     [rsp+0B0h+lpData], rax; lpData
0x14001a6d2  mov     qword ptr [rbp+4Fh+Data], 0
0x14001a6da  mov     [rbp+4Fh+cbData], 8
0x14001a6e1  call    cs:__imp_RegQueryValueExW
0x14001a6e7  mov     ebx, eax
0x14001a6e9  cmp     eax, 2
0x14001a6ec  jnz     short loc_14001A6F8
0x14001a6ee  mov     ebx, 80070002h
0x14001a6f3  jmp     loc_14001A609
0x14001a6f8  test    ebx, ebx
0x14001a6fa  jz      short loc_14001A761
0x14001a6fc  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001a703  test    rcx, rcx
0x14001a706  jz      short loc_14001A757
0x14001a708  lea     rax, [rbp+4Fh+lpValueName]
0x14001a70c  lea     r9, aFailedToQueryR; "Failed to query registry value: {}"
0x14001a713  mov     [rsp+0B0h+lpData], rax
0x14001a718  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x14001a71d  test    ebx, ebx
0x14001a71f  jg      short loc_14001A725
0x14001a721  mov     eax, ebx
0x14001a723  jmp     short loc_14001A72D
0x14001a725  movzx   eax, bx
0x14001a728  or      eax, 80070000h
0x14001a72d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001a734  lea     r9, a0; ": {0}"
0x14001a73b  mov     [rbp+4Fh+var_58], eax
0x14001a73e  mov     r8d, edi
0x14001a741  lea     rax, [rbp+4Fh+var_58]
0x14001a745  mov     qword ptr [rbp+4Fh+var_80], rax
0x14001a749  lea     rax, [rbp+4Fh+var_80]
0x14001a74d  mov     [rsp+0B0h+lpData], rax
0x14001a752  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001a757  mov     edx, 1A6h
0x14001a75c  jmp     loc_14001A690
0x14001a761  cmp     [rbp+4Fh+Type], 0Bh
0x14001a765  jz      short loc_14001A7D0
0x14001a767  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001a76e  mov     ebx, 8007000Dh
0x14001a773  mov     [rbp+4Fh+var_50], ebx
0x14001a776  test    rcx, rcx
0x14001a779  jz      short loc_14001A7B3
0x14001a77b  lea     r9, aRegistryValueI; "Registry value is not a QWORD type."
0x14001a782  mov     r8d, edi
0x14001a785  xor     edx, edx
0x14001a787  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14001a78c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001a793  lea     rax, [rbp+4Fh+var_50]
0x14001a797  mov     qword ptr [rbp+4Fh+var_80], rax
0x14001a79b  lea     r9, asc_1400353E8; ": {}"
0x14001a7a2  lea     rax, [rbp+4Fh+var_80]
0x14001a7a6  mov     r8d, edi
0x14001a7a9  mov     [rsp+0B0h+lpData], rax; int
0x14001a7ae  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001a7b3  mov     rcx, [rbp+57h]; this
0x14001a7b7  lea     r8, aOnecoreBaseCbs_5; "onecore\\base\\cbs\\util\\cbsreg.cpp"
0x14001a7be  mov     r9d, ebx; char *
0x14001a7c1  mov     edx, 1A8h; void *
0x14001a7c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001a7cb  jmp     loc_14001A609
0x14001a7d0  mov     rax, qword ptr [rbp+4Fh+Data]
0x14001a7d4  xor     ebx, ebx
0x14001a7d6  mov     [rsi], rax
0x14001a7d9  jmp     loc_14001A609
```
