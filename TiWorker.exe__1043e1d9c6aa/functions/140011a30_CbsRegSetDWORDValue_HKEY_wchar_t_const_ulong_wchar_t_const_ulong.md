# CbsRegSetDWORDValue(HKEY__ *,wchar_t const *,ulong,wchar_t const *,ulong)

- ea: `0x140011a30`
- end: `0x140011d06`
- name: `?CbsRegSetDWORDValue@@YAJPEAUHKEY__@@PEB_WK1K@Z`
- size: `726`
- prototype: `__int64 __fastcall(HKEY, const wchar_t *, __int64, wchar_t *, unsigned int Data)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000b2f8`
- `0x140023e70`

## callees

- `0x140002310`
- `0x1400053c0`
- `0x140008d38`
- `0x140008ef4`
- `0x14000d910`
- `0x14000e610`
- `0x14000f36c`
- `0x140010e7c`
- `0x14001118c`
- `0x140011a30`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140011c52`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140011c52`

## string_xrefs

- `0x140011b1f`: `Failed to create key: {}`
- `0x140011bc4`: `Failed to open key: {}`
- `0x140011c83`: `Failed to set registry value: {}`

## pseudocode

```c
__int64 __fastcall CbsRegSetDWORDValue(HKEY a1, const wchar_t *a2, __int64 a3, wchar_t *a4, unsigned int Data)
{
  const WCHAR *v5; // rax
  char v6; // si
  unsigned int v7; // ebx
  __int64 v8; // rdx
  HKEY v9; // rcx
  LSTATUS v10; // ebx
  __int64 v11; // rdx
  unsigned int v12; // eax
  __int64 v13; // rdx
  LSTATUS v14; // eax
  __int64 v15; // rdx
  unsigned int v16; // eax
  LSTATUS v17; // eax
  __int64 v18; // rdx
  unsigned int v19; // eax
  unsigned int lpData; // [rsp+20h] [rbp-31h]
  unsigned int lpDataa; // [rsp+20h] [rbp-31h]
  DWORD cbData; // [rsp+28h] [rbp-29h]
  struct _SECURITY_ATTRIBUTES *v24; // [rsp+30h] [rbp-21h]
  unsigned int v25[2]; // [rsp+50h] [rbp-1h] BYREF
  _QWORD v26[2]; // [rsp+60h] [rbp+Fh] BYREF
  wchar_t *v27; // [rsp+70h] [rbp+1Fh] BYREF
  int v28; // [rsp+78h] [rbp+27h] BYREF
  HKEY hKey; // [rsp+80h] [rbp+2Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+57h]

  v26[0] = a2;
  v5 = a4;
  v27 = a4;
  v6 = a3;
  if ( a4 )
  {
    hKey = 0;
    v9 = HKEY_LOCAL_MACHINE;
    if ( a2 )
    {
      if ( (a3 & 2) != 0 )
      {
        v10 = CbsRegCreateKeyExW(HKEY_LOCAL_MACHINE, a2, a3, a4, lpData, cbData, v24, &hKey);
        if ( v10 )
        {
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<wchar_t const *>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (__int64)"Failed to create key: {}",
              (__int64)v26);
            if ( v10 > 0 )
              v12 = (unsigned __int16)v10 | 0x80070000;
            else
              v12 = v10;
            v28 = v12;
            *(_QWORD *)v25 = &v28;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              v11,
              3,
              (__int64)": {0}",
              (__int64)v25);
          }
          v13 = 660;
LABEL_25:
          v7 = wil::details::in1diag3::Return_Win32(
                 retaddr,
                 (void *)v13,
                 (unsigned int)"onecore\\base\\cbs\\util\\cbsreg.cpp",
                 (const char *)(unsigned int)v10,
                 lpDataa);
          goto LABEL_38;
        }
      }
      else
      {
        v14 = CbsRegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, a3, 2u, &hKey);
        v10 = v14;
        if ( (v6 & 1) != 0 && (v14 == 2 || v14 == 3) )
        {
          v7 = (unsigned __int16)v14 | 0x80070000;
LABEL_38:
          Windows::AutoGenericHandleBase<HKEY__ *,0,Windows::AutoGenericHandle<HKEY__ *,0,&void Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>>::Close(&hKey);
          return v7;
        }
        if ( v14 )
        {
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<wchar_t const *>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (__int64)"Failed to open key: {}",
              (__int64)v26);
            if ( v10 > 0 )
              v16 = (unsigned __int16)v10 | 0x80070000;
            else
              v16 = v10;
            v28 = v16;
            *(_QWORD *)v25 = &v28;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              v15,
              3,
              (__int64)": {0}",
              (__int64)v25);
          }
          v13 = 669;
          goto LABEL_25;
        }
      }
      v9 = hKey;
      v5 = v27;
    }
    v17 = RegSetValueExW(v9, v5, 0, 4u, (const BYTE *)&Data, 4u);
    v10 = v17;
    if ( (v6 & 1) != 0 && v17 == 2 )
    {
      v7 = -2147024894;
      goto LABEL_38;
    }
    if ( !v17 )
    {
      v7 = 0;
      goto LABEL_38;
    }
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (__int64)"Failed to set registry value: {}",
        (__int64)&v27);
      if ( v10 > 0 )
        v19 = (unsigned __int16)v10 | 0x80070000;
      else
        v19 = v10;
      v28 = v19;
      *(_QWORD *)v25 = &v28;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v18,
        3,
        (__int64)": {0}",
        (__int64)v25);
    }
    v13 = 686;
    goto LABEL_25;
  }
  v7 = -2147024809;
  v28 = -2147024809;
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(
      (__int64)LogAdapter::g_Logger,
      0,
      3,
      (struct Windows::Rtl::IRtlFormattedOutputStream *)"No value name specified");
    *(_QWORD *)v25 = &v28;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (__int64)LogAdapter::g_Logger,
      v8,
      3,
      (__int64)": {}",
      (__int64)v25);
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x28A,
    (unsigned int)"onecore\\base\\cbs\\util\\cbsreg.cpp",
    (const char *)0x80070057LL,
    lpData);
  return v7;
}

```

## disassembly

```asm
0x140011a30  mov     [rsp-8+arg_0], rbx
0x140011a35  push    rbp
0x140011a36  push    rsi
0x140011a37  push    rdi
0x140011a38  lea     rbp, [rsp-3Fh]
0x140011a3d  sub     rsp, 90h
0x140011a44  mov     rax, cs:__security_cookie
0x140011a4b  xor     rax, rsp
0x140011a4e  mov     [rbp+4Fh+var_18], rax
0x140011a52  mov     [rbp+4Fh+var_40], rdx
0x140011a56  mov     rax, r9
0x140011a59  mov     [rbp+4Fh+var_30], rax
0x140011a5d  mov     esi, r8d
0x140011a60  test    r9, r9
0x140011a63  jnz     short loc_140011AD1
0x140011a65  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140011a6c  mov     ebx, 80070057h
0x140011a71  mov     [rbp+4Fh+var_28], ebx
0x140011a74  test    rcx, rcx
0x140011a77  jz      short loc_140011AB4
0x140011a79  lea     edi, [rax+3]
0x140011a7c  xor     edx, edx
0x140011a7e  mov     r8d, edi
0x140011a81  lea     r9, aNoValueNameSpe; "No value name specified"
0x140011a88  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140011a8d  lea     rcx, [rbp+4Fh+var_50]
0x140011a91  mov     r8d, edi
0x140011a94  mov     [rsp+0A0h+lpData], rcx; int
0x140011a99  lea     rax, [rbp+4Fh+var_28]
0x140011a9d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140011aa4  lea     r9, asc_140030534; ": {}"
0x140011aab  mov     qword ptr [rbp+4Fh+var_50], rax
0x140011aaf  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140011ab4  mov     rcx, [rbp+57h]; this
0x140011ab8  lea     r8, aOnecoreBaseCbs_1; "onecore\\base\\cbs\\util\\cbsreg.cpp"
0x140011abf  mov     r9d, ebx; char *
0x140011ac2  mov     edx, 28Ah; void *
0x140011ac7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140011acc  jmp     loc_140011CE5
0x140011ad1  mov     [rbp+4Fh+hKey], 0
0x140011ad9  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x140011ae0  mov     edi, 3
0x140011ae5  test    rdx, rdx
0x140011ae8  jz      loc_140011C38
0x140011aee  lea     rax, [rbp+4Fh+hKey]
0x140011af2  test    sil, 2
0x140011af6  jz      short loc_140011B76
0x140011af8  mov     [rsp+0A0h+var_68], rax; HKEY *
0x140011afd  call    ?CbsRegCreateKeyExW@@YAKPEAUHKEY__@@PEB_WKPEA_WKKQEAU_SECURITY_ATTRIBUTES@@PEAPEAU1@PEAK@Z; CbsRegCreateKeyExW(HKEY__ *,wchar_t const *,ulong,wchar_t *,ulong,ulong,_SECURITY_ATTRIBUTES * const,HKEY__ * *,ulong *)
0x140011b02  mov     ebx, eax
0x140011b04  test    eax, eax
0x140011b06  jz      loc_140011C30
0x140011b0c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140011b13  test    rcx, rcx
0x140011b16  jz      short loc_140011B6C
0x140011b18  lea     rax, [rbp+4Fh+var_40]
0x140011b1c  mov     r8d, edi
0x140011b1f  lea     r9, aFailedToCreate_10; "Failed to create key: {}"
0x140011b26  mov     [rsp+0A0h+lpData], rax
0x140011b2b  xor     edx, edx
0x140011b2d  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x140011b32  test    ebx, ebx
0x140011b34  jg      short loc_140011B3A
0x140011b36  mov     eax, ebx
0x140011b38  jmp     short loc_140011B42
0x140011b3a  movzx   eax, bx
0x140011b3d  or      eax, 80070000h
0x140011b42  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140011b49  lea     r9, a0; ": {0}"
0x140011b50  mov     [rbp+4Fh+var_28], eax
0x140011b53  mov     r8d, edi
0x140011b56  lea     rax, [rbp+4Fh+var_28]
0x140011b5a  mov     qword ptr [rbp+4Fh+var_50], rax
0x140011b5e  lea     rax, [rbp+4Fh+var_50]
0x140011b62  mov     [rsp+0A0h+lpData], rax
0x140011b67  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140011b6c  mov     edx, 294h; wchar_t *
0x140011b71  jmp     loc_140011C16
0x140011b76  mov     r9d, 2; unsigned int
0x140011b7c  mov     [rsp+0A0h+lpData], rax; HKEY *
0x140011b81  call    ?CbsRegOpenKeyExW@@YAKPEAUHKEY__@@PEB_WKKPEAPEAU1@@Z; CbsRegOpenKeyExW(HKEY__ *,wchar_t const *,ulong,ulong,HKEY__ * *)
0x140011b86  mov     ebx, eax
0x140011b88  test    sil, 1
0x140011b8c  jz      short loc_140011BAD
0x140011b8e  cmp     eax, 2
0x140011b91  jz      short loc_140011B9F
0x140011b93  cmp     eax, edi
0x140011b95  jnz     short loc_140011BAD
0x140011b97  test    eax, eax
0x140011b99  jle     loc_140011CDC
0x140011b9f  movzx   ebx, bx
0x140011ba2  or      ebx, 80070000h
0x140011ba8  jmp     loc_140011CDC
0x140011bad  test    ebx, ebx
0x140011baf  jz      short loc_140011C30
0x140011bb1  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140011bb8  test    rcx, rcx
0x140011bbb  jz      short loc_140011C11
0x140011bbd  lea     rax, [rbp+4Fh+var_40]
0x140011bc1  mov     r8d, edi
0x140011bc4  lea     r9, aFailedToOpenKe; "Failed to open key: {}"
0x140011bcb  mov     [rsp+0A0h+lpData], rax
0x140011bd0  xor     edx, edx
0x140011bd2  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x140011bd7  test    ebx, ebx
0x140011bd9  jg      short loc_140011BDF
0x140011bdb  mov     eax, ebx
0x140011bdd  jmp     short loc_140011BE7
0x140011bdf  movzx   eax, bx
0x140011be2  or      eax, 80070000h
0x140011be7  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140011bee  lea     r9, a0; ": {0}"
0x140011bf5  mov     [rbp+4Fh+var_28], eax
0x140011bf8  mov     r8d, edi
0x140011bfb  lea     rax, [rbp+4Fh+var_28]
0x140011bff  mov     qword ptr [rbp+4Fh+var_50], rax
0x140011c03  lea     rax, [rbp+4Fh+var_50]
0x140011c07  mov     [rsp+0A0h+lpData], rax; unsigned int
0x140011c0c  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140011c11  mov     edx, 29Dh; void *
0x140011c16  mov     rcx, [rbp+57h]; this
0x140011c1a  lea     r8, aOnecoreBaseCbs_1; "onecore\\base\\cbs\\util\\cbsreg.cpp"
0x140011c21  mov     r9d, ebx; char *
0x140011c24  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x140011c29  mov     ebx, eax
0x140011c2b  jmp     loc_140011CDC
0x140011c30  mov     rcx, [rbp+4Fh+hKey]; hKey
0x140011c34  mov     rax, [rbp+4Fh+var_30]
0x140011c38  mov     r9d, 4; dwType
0x140011c3e  lea     rdx, [rbp+4Fh+Data]
0x140011c42  mov     [rsp+0A0h+cbData], r9d; cbData
0x140011c47  xor     r8d, r8d; Reserved
0x140011c4a  mov     [rsp+0A0h+lpData], rdx; lpData
0x140011c4f  mov     rdx, rax; lpValueName
0x140011c52  call    cs:__imp_RegSetValueExW
0x140011c58  mov     ebx, eax
0x140011c5a  test    sil, 1
0x140011c5e  jz      short loc_140011C6C
0x140011c60  cmp     eax, 2
0x140011c63  jnz     short loc_140011C6C
0x140011c65  mov     ebx, 80070002h
0x140011c6a  jmp     short loc_140011CDC
0x140011c6c  test    ebx, ebx
0x140011c6e  jz      short loc_140011CDA
0x140011c70  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140011c77  test    rcx, rcx
0x140011c7a  jz      short loc_140011CD0
0x140011c7c  lea     rax, [rbp+4Fh+var_30]
0x140011c80  mov     r8d, edi
0x140011c83  lea     r9, aFailedToSetReg; "Failed to set registry value: {}"
0x140011c8a  mov     [rsp+0A0h+lpData], rax
0x140011c8f  xor     edx, edx
0x140011c91  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x140011c96  test    ebx, ebx
0x140011c98  jg      short loc_140011C9E
0x140011c9a  mov     eax, ebx
0x140011c9c  jmp     short loc_140011CA6
0x140011c9e  movzx   eax, bx
0x140011ca1  or      eax, 80070000h
0x140011ca6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140011cad  lea     r9, a0; ": {0}"
0x140011cb4  mov     [rbp+4Fh+var_28], eax
0x140011cb7  mov     r8d, edi
0x140011cba  lea     rax, [rbp+4Fh+var_28]
0x140011cbe  mov     qword ptr [rbp+4Fh+var_50], rax
0x140011cc2  lea     rax, [rbp+4Fh+var_50]
0x140011cc6  mov     [rsp+0A0h+lpData], rax
0x140011ccb  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140011cd0  mov     edx, 2AEh
0x140011cd5  jmp     loc_140011C16
0x140011cda  xor     ebx, ebx
0x140011cdc  lea     rcx, [rbp+4Fh+hKey]
0x140011ce0  call    ?Close@?$AutoGenericHandleBase@PEAUHKEY__@@$0A@V?$AutoGenericHandle@PEAUHKEY__@@$0A@$1?CloseWithRegCloseKey@Detail@Windows@@YAXPEAU1@@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<HKEY__ *,0,Windows::AutoGenericHandle<HKEY__ *,0,&Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>>::Close(void)
0x140011ce5  mov     eax, ebx
0x140011ce7  mov     rcx, [rbp+4Fh+var_18]
0x140011ceb  xor     rcx, rsp; StackCookie
0x140011cee  call    __security_check_cookie
0x140011cf3  mov     rbx, [rsp+0A0h+arg_0]
0x140011cfb  add     rsp, 90h
0x140011d02  pop     rdi
0x140011d03  pop     rsi
0x140011d04  pop     rbp
0x140011d05  retn
```
