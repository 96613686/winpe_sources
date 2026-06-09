# CbsRegSetStringValue(HKEY__ *,wchar_t const *,ulong,wchar_t const *,wchar_t const * const)

- ea: `0x14001afa4`
- end: `0x14001b209`
- name: `?CbsRegSetStringValue@@YAJPEAUHKEY__@@PEB_WK1QEB_W@Z`
- size: `613`
- prototype: `__int64 __fastcall(HKEY hKey, const wchar_t *, __int64, const wchar_t *, BYTE *)`
- caller_count: `3`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140015b90`
- `0x140016210`
- `0x1400166f0`

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
- `0x14001afa4`
- `0x14001b23c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14001b154`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14001b154`

## string_xrefs

- `0x14001b093`: `Failed to open key: {}`
- `0x14001b170`: `Failed to set registry value: {}`

## pseudocode

```c
__int64 __fastcall CbsRegSetStringValue(HKEY hKey, const wchar_t *a2, __int64 a3, const wchar_t *a4, BYTE *a5)
{
  unsigned int v6; // ebx
  __int64 v7; // rdx
  HKEY *InitPointer; // rax
  __int64 v9; // r8
  __int64 v10; // rdx
  LSTATUS v11; // ebx
  __int64 v12; // r8
  __int64 v13; // rdx
  DWORD v14; // eax
  __int64 v15; // rdx
  __int64 v16; // rcx
  int v17; // eax
  const WCHAR *v18; // r10
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // rdx
  DWORD v22; // eax
  unsigned int lpData; // [rsp+20h] [rbp-50h]
  unsigned int v25[2]; // [rsp+30h] [rbp-40h] BYREF
  LPCWSTR lpSubKey[2]; // [rsp+40h] [rbp-30h] BYREF
  const wchar_t *v27; // [rsp+50h] [rbp-20h] BYREF
  DWORD cbData; // [rsp+58h] [rbp-18h] BYREF
  HKEY v29; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  lpSubKey[0] = a2;
  v27 = L"Events";
  if ( a5 )
  {
    v29 = 0;
    if ( a2 )
    {
      InitPointer = (HKEY *)Windows::AutoComPtr<IClassFactory>::GetInitPointer(&v29);
      v11 = CbsRegOpenKeyExW(hKey, lpSubKey[0], v9, 2u, InitPointer);
      if ( v11 )
      {
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            (__int64)LogAdapter::g_Logger,
            v10,
            v12,
            (__int64)"Failed to open key: {}",
            (__int64)lpSubKey);
          if ( v11 > 0 )
            v14 = (unsigned __int16)v11 | 0x80070000;
          else
            v14 = v11;
          cbData = v14;
          *(_QWORD *)v25 = &cbData;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            v13,
            3,
            (__int64)": {0}",
            (__int64)v25);
        }
        v15 = 521;
        goto LABEL_25;
      }
      hKey = v29;
    }
    cbData = 0;
    v16 = -1;
    do
      ++v16;
    while ( *(_WORD *)&a5[2 * v16] );
    v17 = ULongLongToULong(2 * v16 + 2, &cbData);
    v6 = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x20F,
        (unsigned int)"onecore\\base\\cbs\\util\\cbsreg.cpp",
        (const char *)(unsigned int)v17,
        lpData);
LABEL_27:
      Windows::AutoGenericHandleBase<HKEY__ *,0,Windows::AutoGenericHandle<HKEY__ *,0,&void Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>>::Close(&v29);
      return v6;
    }
    v11 = RegSetValueExW(hKey, v18, 0, 1u, a5, cbData);
    if ( !v11 )
    {
      v6 = 0;
      goto LABEL_27;
    }
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (__int64)LogAdapter::g_Logger,
        v19,
        v20,
        (__int64)"Failed to set registry value: {}",
        (__int64)&v27);
      if ( v11 > 0 )
        v22 = (unsigned __int16)v11 | 0x80070000;
      else
        v22 = v11;
      cbData = v22;
      *(_QWORD *)v25 = &cbData;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v21,
        3,
        (__int64)": {0}",
        (__int64)v25);
    }
    v15 = 534;
LABEL_25:
    v6 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v15,
           (unsigned int)"onecore\\base\\cbs\\util\\cbsreg.cpp",
           (const char *)(unsigned int)v11,
           lpData);
    goto LABEL_27;
  }
  v6 = -2147024809;
  cbData = -2147024809;
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(
      (__int64)LogAdapter::g_Logger,
      0,
      3,
      (struct Windows::Rtl::IRtlFormattedOutputStream *)"No value specified");
    *(_QWORD *)v25 = &cbData;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (__int64)LogAdapter::g_Logger,
      v7,
      3,
      (__int64)": {}",
      (__int64)v25);
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1F4,
    (unsigned int)"onecore\\base\\cbs\\util\\cbsreg.cpp",
    (const char *)0x80070057LL,
    lpData);
  return v6;
}

```

## disassembly

```asm
0x14001afa4  mov     [rsp-18h+arg_10], rbx
0x14001afa9  mov     [rsp-18h+arg_18], rsi
0x14001afae  push    rbp
0x14001afaf  push    rdi
0x14001afb0  push    r14
0x14001afb2  mov     rbp, rsp
0x14001afb5  sub     rsp, 70h
0x14001afb9  mov     rax, cs:__security_cookie
0x14001afc0  xor     rax, rsp
0x14001afc3  mov     [rbp+var_8], rax
0x14001afc7  mov     rsi, [rbp+arg_20]
0x14001afcb  lea     r10, aEvents; "Events"
0x14001afd2  xor     r14d, r14d
0x14001afd5  mov     [rbp+lpSubKey], rdx
0x14001afd9  mov     [rbp+var_20], r10
0x14001afdd  mov     rdi, rcx
0x14001afe0  test    rsi, rsi
0x14001afe3  jnz     short loc_14001B050
0x14001afe5  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001afec  mov     ebx, 80070057h
0x14001aff1  mov     [rbp+var_18], ebx
0x14001aff4  test    rcx, rcx
0x14001aff7  jz      short loc_14001B033
0x14001aff9  lea     r9, aNoValueSpecifi; "No value specified"
0x14001b000  xor     edx, edx
0x14001b002  lea     r8d, [rsi+3]
0x14001b006  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14001b00b  lea     rcx, [rbp+var_40]
0x14001b00f  mov     [rsp+70h+lpData], rcx; int
0x14001b014  lea     rax, [rbp+var_18]
0x14001b018  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001b01f  lea     r9, asc_1400353E8; ": {}"
0x14001b026  lea     r8d, [rsi+3]
0x14001b02a  mov     qword ptr [rbp+var_40], rax
0x14001b02e  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001b033  mov     rcx, [rbp+18h]; this
0x14001b037  lea     r8, aOnecoreBaseCbs_5; "onecore\\base\\cbs\\util\\cbsreg.cpp"
0x14001b03e  mov     r9d, ebx; char *
0x14001b041  mov     edx, 1F4h; void *
0x14001b046  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001b04b  jmp     loc_14001B1E6
0x14001b050  mov     [rbp+var_10], r14
0x14001b054  test    rdx, rdx
0x14001b057  jz      loc_14001B0F3
0x14001b05d  lea     rcx, [rbp+var_10]
0x14001b061  call    ?GetInitPointer@?$AutoComPtr@UIClassFactory@@@Windows@@QEAAPEAPEAUIClassFactory@@XZ; Windows::AutoComPtr<IClassFactory>::GetInitPointer(void)
0x14001b066  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x14001b06a  mov     r9d, 2; unsigned int
0x14001b070  mov     rcx, rdi; hKey
0x14001b073  mov     [rsp+70h+lpData], rax; int
0x14001b078  call    ?CbsRegOpenKeyExW@@YAKPEAUHKEY__@@PEB_WKKPEAPEAU1@@Z; CbsRegOpenKeyExW(HKEY__ *,wchar_t const *,ulong,ulong,HKEY__ * *)
0x14001b07d  mov     ebx, eax
0x14001b07f  test    eax, eax
0x14001b081  jz      short loc_14001B0EB
0x14001b083  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001b08a  test    rcx, rcx
0x14001b08d  jz      short loc_14001B0E1
0x14001b08f  lea     rax, [rbp+lpSubKey]
0x14001b093  lea     r9, aFailedToOpenKe; "Failed to open key: {}"
0x14001b09a  mov     [rsp+70h+lpData], rax
0x14001b09f  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x14001b0a4  test    ebx, ebx
0x14001b0a6  jg      short loc_14001B0AC
0x14001b0a8  mov     eax, ebx
0x14001b0aa  jmp     short loc_14001B0B4
0x14001b0ac  movzx   eax, bx
0x14001b0af  or      eax, 80070000h
0x14001b0b4  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001b0bb  lea     r9, a0; ": {0}"
0x14001b0c2  mov     [rbp+var_18], eax
0x14001b0c5  mov     r8d, 3
0x14001b0cb  lea     rax, [rbp+var_18]
0x14001b0cf  mov     qword ptr [rbp+var_40], rax
0x14001b0d3  lea     rax, [rbp+var_40]
0x14001b0d7  mov     [rsp+70h+lpData], rax
0x14001b0dc  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001b0e1  mov     edx, 209h
0x14001b0e6  jmp     loc_14001B1C3
0x14001b0eb  mov     rdi, [rbp+var_10]
0x14001b0ef  mov     r10, [rbp+var_20]
0x14001b0f3  mov     [rbp+var_18], r14d
0x14001b0f7  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14001b0fb  inc     rcx
0x14001b0fe  cmp     [rsi+rcx*2], r14w
0x14001b103  jnz     short loc_14001B0FB
0x14001b105  lea     rcx, ds:2[rcx*2]; unsigned __int64
0x14001b10d  lea     rdx, [rbp+var_18]; unsigned int *
0x14001b111  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x14001b116  mov     ebx, eax
0x14001b118  test    eax, eax
0x14001b11a  jns     short loc_14001B139
0x14001b11c  mov     rcx, [rbp+18h]; this
0x14001b120  lea     r8, aOnecoreBaseCbs_5; "onecore\\base\\cbs\\util\\cbsreg.cpp"
0x14001b127  mov     r9d, eax; char *
0x14001b12a  mov     edx, 20Fh; void *
0x14001b12f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001b134  jmp     loc_14001B1DD
0x14001b139  mov     eax, [rbp+var_18]
0x14001b13c  mov     r9d, 1; dwType
0x14001b142  mov     [rsp+70h+cbData], eax; cbData
0x14001b146  xor     r8d, r8d; Reserved
0x14001b149  mov     rdx, r10; lpValueName
0x14001b14c  mov     [rsp+70h+lpData], rsi; lpData
0x14001b151  mov     rcx, rdi; hKey
0x14001b154  call    cs:__imp_RegSetValueExW
0x14001b15a  mov     ebx, eax
0x14001b15c  test    eax, eax
0x14001b15e  jz      short loc_14001B1DA
0x14001b160  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001b167  test    rcx, rcx
0x14001b16a  jz      short loc_14001B1BE
0x14001b16c  lea     rax, [rbp+var_20]
0x14001b170  lea     r9, aFailedToSetReg; "Failed to set registry value: {}"
0x14001b177  mov     [rsp+70h+lpData], rax
0x14001b17c  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x14001b181  test    ebx, ebx
0x14001b183  jg      short loc_14001B189
0x14001b185  mov     eax, ebx
0x14001b187  jmp     short loc_14001B191
0x14001b189  movzx   eax, bx
0x14001b18c  or      eax, 80070000h
0x14001b191  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001b198  lea     r9, a0; ": {0}"
0x14001b19f  mov     [rbp+var_18], eax
0x14001b1a2  mov     r8d, 3
0x14001b1a8  lea     rax, [rbp+var_18]
0x14001b1ac  mov     qword ptr [rbp+var_40], rax
0x14001b1b0  lea     rax, [rbp+var_40]
0x14001b1b4  mov     [rsp+70h+lpData], rax; unsigned int
0x14001b1b9  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001b1be  mov     edx, 216h; void *
0x14001b1c3  mov     rcx, [rbp+18h]; this
0x14001b1c7  lea     r8, aOnecoreBaseCbs_5; "onecore\\base\\cbs\\util\\cbsreg.cpp"
0x14001b1ce  mov     r9d, ebx; char *
0x14001b1d1  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x14001b1d6  mov     ebx, eax
0x14001b1d8  jmp     short loc_14001B1DD
0x14001b1da  mov     ebx, r14d
0x14001b1dd  lea     rcx, [rbp+var_10]
0x14001b1e1  call    ?Close@?$AutoGenericHandleBase@PEAUHKEY__@@$0A@V?$AutoGenericHandle@PEAUHKEY__@@$0A@$1?CloseWithRegCloseKey@Detail@Windows@@YAXPEAU1@@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<HKEY__ *,0,Windows::AutoGenericHandle<HKEY__ *,0,&Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>>::Close(void)
0x14001b1e6  mov     eax, ebx
0x14001b1e8  mov     rcx, [rbp+var_8]
0x14001b1ec  xor     rcx, rsp; StackCookie
0x14001b1ef  call    __security_check_cookie
0x14001b1f4  lea     r11, [rsp+70h+var_s0]
0x14001b1f9  mov     rbx, [r11+30h]
0x14001b1fd  mov     rsi, [r11+38h]
0x14001b201  mov     rsp, r11
0x14001b204  pop     r14
0x14001b206  pop     rdi
0x14001b207  pop     rbp
0x14001b208  retn
```
