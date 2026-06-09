# CreateFileWithRetries

- ea: `0x18004e0f8`
- end: `0x18004e3fc`
- name: `CreateFileWithRetries`
- size: `772`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180047e20`
- `0x18004def8`

## callees

- `0x180020440`
- `0x18002d2b0`
- `0x180045914`
- `0x180046650`
- `0x180046bb4`
- `0x180046ca4`
- `0x180047c5c`
- `0x1800499cc`
- `0x18004e0f8`
- `0x18006cacc`
- `0x18006cf90`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18004e34b`
- `KERNEL32!GetLastError` at `0x18004e34b`
- `KERNEL32!CreateFileW` at `0x18004e31d`
- `KERNEL32!CreateFileW` at `0x18004e31d`
- `KERNEL32!Sleep` at `0x18004e338`
- `KERNEL32!Sleep` at `0x18004e338`

## string_xrefs

- `0x18004e155`: `No file path specified`
- `0x18004e2a9`: `Failed calling GetSystemSecurity`
- `0x18004e369`: `Failed to create file: {}`

## pseudocode

```c
int __fastcall CreateFileWithRetries(
        const WCHAR *a1,
        bool *a2,
        __int64 a3,
        __int64 a4,
        int a5,
        int a6,
        int a7,
        _QWORD *a8)
{
  unsigned int v8; // edi
  int v9; // edx
  __int64 v10; // rdx
  int v12; // edx
  int CanSetSystemOwner; // eax
  struct _SECURITY_DESCRIPTOR **v14; // rdx
  unsigned int v15; // edi
  int v16; // edx
  __int64 v17; // rdx
  int SystemSecurity; // eax
  int v19; // edx
  unsigned int i; // edi
  HANDLE v21; // rax
  int v22; // edx
  signed int LastError; // edi
  int v24; // r8d
  int v25; // edx
  unsigned int v26; // eax
  int dwCreationDisposition; // [rsp+20h] [rbp-60h]
  unsigned int dwCreationDispositiona; // [rsp+20h] [rbp-60h]
  _BYTE v29[8]; // [rsp+40h] [rbp-40h] BYREF
  unsigned int v30[2]; // [rsp+48h] [rbp-38h] BYREF
  LPCWSTR lpFileName; // [rsp+50h] [rbp-30h] BYREF
  _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+58h] [rbp-28h] BYREF
  void *v33; // [rsp+70h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+8h]

  lpFileName = a1;
  v33 = 0;
  *(_QWORD *)&SecurityAttributes.nLength = 24;
  *(_OWORD *)&SecurityAttributes.lpSecurityDescriptor = 0;
  if ( !a1 )
  {
    v8 = -2147024809;
    LODWORD(v33) = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No file path specified");
      *(_QWORD *)v30 = &v33;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v9,
        3,
        (unsigned int)": {}",
        (__int64)v30);
    }
    v10 = 1357;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
      (const char *)v8,
      dwCreationDisposition);
    return v8;
  }
  if ( !a8 )
  {
    v8 = -2147467261;
    LODWORD(v33) = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No file handle result specified");
      *(_QWORD *)v30 = &v33;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v12,
        3,
        (unsigned int)": {}",
        (__int64)v30);
    }
    v10 = 1358;
    goto LABEL_5;
  }
  v29[0] = 0;
  CanSetSystemOwner = Windows::WCP::Implementation::Rtl::CanSetSystemOwner((Windows::WCP::Implementation::Rtl *)v29, a2);
  v15 = CanSetSystemOwner;
  if ( CanSetSystemOwner < 0 )
  {
    LODWORD(v33) = CanSetSystemOwner;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed calling CanSetSystemOwner");
      *(_QWORD *)v30 = &v33;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v16,
        3,
        (unsigned int)": {}",
        (__int64)v30);
    }
    v17 = 1374;
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)v17,
             (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
             (const char *)v15,
             dwCreationDisposition);
  }
  if ( v29[0] )
  {
    SystemSecurity = Windows::WCP::Implementation::Rtl::GetSystemSecurity(
                       (Windows::WCP::Implementation::Rtl *)&v33,
                       v14);
    v15 = SystemSecurity;
    if ( SystemSecurity < 0 )
    {
      LODWORD(v33) = SystemSecurity;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed calling GetSystemSecurity");
        *(_QWORD *)v30 = &v33;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v19,
          3,
          (unsigned int)": {}",
          (__int64)v30);
      }
      v17 = 1380;
      return wil::details::in1diag3::Return_NtStatus(
               retaddr,
               (void *)v17,
               (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
               (const char *)v15,
               dwCreationDisposition);
    }
    SecurityAttributes.lpSecurityDescriptor = v33;
  }
  for ( i = 0; i < 3; ++i )
  {
    v21 = CreateFileW(lpFileName, 0x40000001u, 0, &SecurityAttributes, 2u, 0x2000080u, 0);
    if ( v21 != (HANDLE)-1LL )
    {
      *a8 = v21;
      return 0;
    }
    Sleep(0x3E8u);
  }
  LastError = GetLastError();
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<wchar_t const *>(
      (_DWORD)LogAdapter::g_Logger,
      v22,
      v24,
      (unsigned int)"Failed to create file: {}",
      (__int64)&lpFileName);
    if ( LastError > 0 )
      v26 = (unsigned __int16)LastError | 0x80070000;
    else
      v26 = LastError;
    LODWORD(v33) = v26;
    *(_QWORD *)v30 = &v33;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (_DWORD)LogAdapter::g_Logger,
      v25,
      3,
      (unsigned int)": {0}",
      (__int64)v30);
  }
  if ( LastError )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x580,
             (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
             (const char *)(unsigned int)LastError,
             dwCreationDispositiona);
  return 0;
}

```

## disassembly

```asm
0x18004e0f8  mov     [rsp-8+arg_8], rsi
0x18004e0fd  mov     [rsp-8+arg_10], rdi
0x18004e102  push    rbp
0x18004e103  mov     rbp, rsp
0x18004e106  sub     rsp, 80h
0x18004e10d  mov     rax, cs:__security_cookie
0x18004e114  xor     rax, rsp
0x18004e117  mov     [rbp+var_8], rax
0x18004e11b  mov     rsi, [rbp+arg_38]
0x18004e11f  xorps   xmm0, xmm0
0x18004e122  mov     [rbp+lpFileName], rcx
0x18004e126  mov     [rbp+var_10], 0
0x18004e12e  mov     qword ptr [rbp+SecurityAttributes.nLength], 18h
0x18004e136  movups  xmmword ptr [rbp+SecurityAttributes.lpSecurityDescriptor], xmm0
0x18004e13a  test    rcx, rcx
0x18004e13d  jnz     short loc_18004E1AE
0x18004e13f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004e146  mov     edi, 80070057h
0x18004e14b  mov     dword ptr [rbp+var_10], edi
0x18004e14e  test    rcx, rcx
0x18004e151  jz      short loc_18004E18F
0x18004e153  xor     edx, edx
0x18004e155  lea     r9, aNoFilePathSpec; "No file path specified"
0x18004e15c  lea     r8d, [rdx+3]
0x18004e160  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18004e165  lea     rcx, [rbp+var_38]
0x18004e169  mov     r8d, 3
0x18004e16f  mov     qword ptr [rsp+80h+dwCreationDisposition], rcx; int
0x18004e174  lea     rax, [rbp+var_10]
0x18004e178  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004e17f  lea     r9, asc_1800AFAD8; ": {}"
0x18004e186  mov     qword ptr [rbp+var_38], rax
0x18004e18a  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18004e18f  mov     edx, 54Dh; void *
0x18004e194  mov     rcx, [rbp+8]; this
0x18004e198  lea     r8, aOnecoreBaseCbs_5; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x18004e19f  mov     r9d, edi; char *
0x18004e1a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e1a7  mov     eax, edi
0x18004e1a9  jmp     loc_18004E3DA
0x18004e1ae  test    rsi, rsi
0x18004e1b1  jnz     short loc_18004E208
0x18004e1b3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004e1ba  mov     edi, 80004003h
0x18004e1bf  mov     dword ptr [rbp+var_10], edi
0x18004e1c2  test    rcx, rcx
0x18004e1c5  jz      short loc_18004E201
0x18004e1c7  lea     r9, aNoFileHandleRe; "No file handle result specified"
0x18004e1ce  xor     edx, edx
0x18004e1d0  lea     r8d, [rsi+3]
0x18004e1d4  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18004e1d9  lea     rcx, [rbp+var_38]
0x18004e1dd  mov     qword ptr [rsp+80h+dwCreationDisposition], rcx
0x18004e1e2  lea     rax, [rbp+var_10]
0x18004e1e6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004e1ed  lea     r9, asc_1800AFAD8; ": {}"
0x18004e1f4  lea     r8d, [rsi+3]
0x18004e1f8  mov     qword ptr [rbp+var_38], rax
0x18004e1fc  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18004e201  mov     edx, 54Eh; bool *
0x18004e206  jmp     short loc_18004E194
0x18004e208  lea     rcx, [rbp+var_40]; this
0x18004e20c  mov     [rbp+var_40], 0
0x18004e210  call    ?CanSetSystemOwner@Rtl@Implementation@WCP@Windows@@YAJPEA_N@Z; Windows::WCP::Implementation::Rtl::CanSetSystemOwner(bool *)
0x18004e215  mov     edi, eax
0x18004e217  test    eax, eax
0x18004e219  jns     short loc_18004E283
0x18004e21b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004e222  mov     dword ptr [rbp+var_10], eax
0x18004e225  test    rcx, rcx
0x18004e228  jz      short loc_18004E266
0x18004e22a  xor     edx, edx
0x18004e22c  lea     r9, aFailedCallingC; "Failed calling CanSetSystemOwner"
0x18004e233  lea     r8d, [rdx+3]
0x18004e237  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18004e23c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004e243  lea     rax, [rbp+var_10]
0x18004e247  mov     qword ptr [rbp+var_38], rax
0x18004e24b  lea     r9, asc_1800AFAD8; ": {}"
0x18004e252  lea     rax, [rbp+var_38]
0x18004e256  mov     r8d, 3
0x18004e25c  mov     qword ptr [rsp+80h+dwCreationDisposition], rax; int
0x18004e261  call    ??$LogNumObjects@U?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatNtStatusWrapper<long> const &)
0x18004e266  mov     edx, 55Eh; void *
0x18004e26b  mov     rcx, [rbp+8]; this
0x18004e26f  lea     r8, aOnecoreBaseCbs_5; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x18004e276  mov     r9d, edi; char *
0x18004e279  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18004e27e  jmp     loc_18004E3DA
0x18004e283  cmp     [rbp+var_40], 0
0x18004e287  jz      short loc_18004E2F2
0x18004e289  lea     rcx, [rbp+var_10]; this
0x18004e28d  call    ?GetSystemSecurity@Rtl@Implementation@WCP@Windows@@YAJPEAPEAU_SECURITY_DESCRIPTOR@@@Z; Windows::WCP::Implementation::Rtl::GetSystemSecurity(_SECURITY_DESCRIPTOR * *)
0x18004e292  mov     edi, eax
0x18004e294  test    eax, eax
0x18004e296  jns     short loc_18004E2EA
0x18004e298  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004e29f  mov     dword ptr [rbp+var_10], eax
0x18004e2a2  test    rcx, rcx
0x18004e2a5  jz      short loc_18004E2E3
0x18004e2a7  xor     edx, edx
0x18004e2a9  lea     r9, aFailedCallingG; "Failed calling GetSystemSecurity"
0x18004e2b0  lea     r8d, [rdx+3]
0x18004e2b4  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18004e2b9  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004e2c0  lea     rax, [rbp+var_10]
0x18004e2c4  mov     qword ptr [rbp+var_38], rax
0x18004e2c8  lea     r9, asc_1800AFAD8; ": {}"
0x18004e2cf  lea     rax, [rbp+var_38]
0x18004e2d3  mov     r8d, 3
0x18004e2d9  mov     qword ptr [rsp+80h+dwCreationDisposition], rax
0x18004e2de  call    ??$LogNumObjects@U?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatNtStatusWrapper<long> const &)
0x18004e2e3  mov     edx, 564h
0x18004e2e8  jmp     short loc_18004E26B
0x18004e2ea  mov     rax, [rbp+var_10]
0x18004e2ee  mov     [rbp+SecurityAttributes.lpSecurityDescriptor], rax
0x18004e2f2  xor     edi, edi
0x18004e2f4  mov     rcx, [rbp+lpFileName]; lpFileName
0x18004e2f8  lea     r9, [rbp+SecurityAttributes]; lpSecurityAttributes
0x18004e2fc  mov     [rsp+80h+hTemplateFile], 0; hTemplateFile
0x18004e305  xor     r8d, r8d; dwShareMode
0x18004e308  mov     [rsp+80h+dwFlagsAndAttributes], 2000080h; dwFlagsAndAttributes
0x18004e310  mov     edx, 40000001h; dwDesiredAccess
0x18004e315  mov     [rsp+80h+dwCreationDisposition], 2; dwCreationDisposition
0x18004e31d  call    cs:__imp_CreateFileW
0x18004e324  nop     dword ptr [rax+rax+00h]
0x18004e329  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004e32d  jnz     loc_18004E3D5
0x18004e333  mov     ecx, 3E8h; dwMilliseconds
0x18004e338  call    cs:__imp_Sleep
0x18004e33f  nop     dword ptr [rax+rax+00h]
0x18004e344  inc     edi
0x18004e346  cmp     edi, 3
0x18004e349  jb      short loc_18004E2F4
0x18004e34b  call    cs:__imp_GetLastError
0x18004e352  nop     dword ptr [rax+rax+00h]
0x18004e357  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004e35e  mov     edi, eax
0x18004e360  test    rcx, rcx
0x18004e363  jz      short loc_18004E3B7
0x18004e365  lea     rax, [rbp+lpFileName]
0x18004e369  lea     r9, aFailedToCreate_3; "Failed to create file: {}"
0x18004e370  mov     qword ptr [rsp+80h+dwCreationDisposition], rax
0x18004e375  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x18004e37a  test    edi, edi
0x18004e37c  jg      short loc_18004E382
0x18004e37e  mov     eax, edi
0x18004e380  jmp     short loc_18004E38A
0x18004e382  movzx   eax, di
0x18004e385  or      eax, 80070000h
0x18004e38a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004e391  lea     r9, a0; ": {0}"
0x18004e398  mov     dword ptr [rbp+var_10], eax
0x18004e39b  mov     r8d, 3
0x18004e3a1  lea     rax, [rbp+var_10]
0x18004e3a5  mov     qword ptr [rbp+var_38], rax
0x18004e3a9  lea     rax, [rbp+var_38]
0x18004e3ad  mov     qword ptr [rsp+80h+dwCreationDisposition], rax; unsigned int
0x18004e3b2  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18004e3b7  test    edi, edi
0x18004e3b9  jz      short loc_18004E3D8
0x18004e3bb  mov     rcx, [rbp+8]; this
0x18004e3bf  lea     r8, aOnecoreBaseCbs_5; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x18004e3c6  mov     r9d, edi; char *
0x18004e3c9  mov     edx, 580h; void *
0x18004e3ce  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004e3d3  jmp     short loc_18004E3DA
0x18004e3d5  mov     [rsi], rax
0x18004e3d8  xor     eax, eax
0x18004e3da  mov     rcx, [rbp+var_8]
0x18004e3de  xor     rcx, rsp; StackCookie
0x18004e3e1  call    __security_check_cookie
0x18004e3e6  lea     r11, [rsp+80h+var_s0]
0x18004e3ee  mov     rsi, [r11+18h]
0x18004e3f2  mov     rdi, [r11+20h]
0x18004e3f6  mov     rsp, r11
0x18004e3f9  pop     rbp
0x18004e3fa  retn
```
