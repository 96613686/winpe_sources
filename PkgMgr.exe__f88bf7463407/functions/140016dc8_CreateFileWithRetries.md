# CreateFileWithRetries

- ea: `0x140016dc8`
- end: `0x1400170b8`
- name: `CreateFileWithRetries`
- size: `752`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x140013288`
- `0x140016bc8`

## callees

- `0x140002360`
- `0x1400056ac`
- `0x1400067bc`
- `0x140006984`
- `0x140006c50`
- `0x14000952c`
- `0x140016870`
- `0x140016b84`
- `0x140016dc8`
- `0x14002750c`
- `0x140027858`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140017008`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140017008`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140016fe6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140016fe6`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140016ffb`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140016ffb`

## string_xrefs

- `0x140016e25`: `No file path specified`
- `0x140016f72`: `Failed calling GetSystemSecurity`
- `0x140017022`: `Failed to create file: {}`

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
  unsigned int v15; // r8d
  unsigned int v16; // edi
  int v17; // edx
  __int64 v18; // rdx
  int SystemSecurity; // eax
  int v20; // edx
  unsigned int i; // edi
  HANDLE v22; // rax
  signed int LastError; // edi
  int v24; // edx
  unsigned int v25; // eax
  int dwCreationDisposition; // [rsp+20h] [rbp-60h]
  unsigned int dwCreationDispositiona; // [rsp+20h] [rbp-60h]
  _BYTE v28[8]; // [rsp+40h] [rbp-40h] BYREF
  unsigned int v29[2]; // [rsp+48h] [rbp-38h] BYREF
  LPCWSTR lpFileName; // [rsp+50h] [rbp-30h] BYREF
  _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+58h] [rbp-28h] BYREF
  void *v32; // [rsp+70h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+8h]

  lpFileName = a1;
  v32 = 0;
  *(_QWORD *)&SecurityAttributes.nLength = 24;
  *(_OWORD *)&SecurityAttributes.lpSecurityDescriptor = 0;
  if ( !a1 )
  {
    v8 = -2147024809;
    LODWORD(v32) = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No file path specified");
      *(_QWORD *)v29 = &v32;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v9,
        3,
        (unsigned int)": {}",
        (__int64)v29);
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
    LODWORD(v32) = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No file handle result specified");
      *(_QWORD *)v29 = &v32;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v12,
        3,
        (unsigned int)": {}",
        (__int64)v29);
    }
    v10 = 1358;
    goto LABEL_5;
  }
  v28[0] = 0;
  CanSetSystemOwner = Windows::WCP::Implementation::Rtl::CanSetSystemOwner((Windows::WCP::Implementation::Rtl *)v28, a2);
  v16 = CanSetSystemOwner;
  if ( CanSetSystemOwner < 0 )
  {
    LODWORD(v32) = CanSetSystemOwner;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed calling CanSetSystemOwner");
      *(_QWORD *)v29 = &v32;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v17,
        3,
        (unsigned int)": {}",
        (__int64)v29);
    }
    v18 = 1374;
    return wil::details::in1diag3::Return_NtStatus(retaddr, (void *)v18, v15, (const char *)v16, dwCreationDisposition);
  }
  if ( v28[0] )
  {
    SystemSecurity = Windows::WCP::Implementation::Rtl::GetSystemSecurity(
                       (Windows::WCP::Implementation::Rtl *)&v32,
                       v14);
    v16 = SystemSecurity;
    if ( SystemSecurity < 0 )
    {
      LODWORD(v32) = SystemSecurity;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed calling GetSystemSecurity");
        *(_QWORD *)v29 = &v32;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v20,
          3,
          (unsigned int)": {}",
          (__int64)v29);
      }
      v18 = 1380;
      return wil::details::in1diag3::Return_NtStatus(
               retaddr,
               (void *)v18,
               v15,
               (const char *)v16,
               dwCreationDisposition);
    }
    SecurityAttributes.lpSecurityDescriptor = v32;
  }
  for ( i = 0; i < 3; ++i )
  {
    v22 = CreateFileW(lpFileName, 0x40000001u, 0, &SecurityAttributes, 2u, 0x2000080u, 0);
    if ( v22 != (HANDLE)-1LL )
    {
      *a8 = v22;
      return 0;
    }
    Sleep(0x3E8u);
  }
  LastError = GetLastError();
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<wchar_t const *>(
      (_DWORD)LogAdapter::g_Logger,
      0,
      3,
      (unsigned int)"Failed to create file: {}",
      (__int64)&lpFileName);
    if ( LastError > 0 )
      v25 = (unsigned __int16)LastError | 0x80070000;
    else
      v25 = LastError;
    LODWORD(v32) = v25;
    *(_QWORD *)v29 = &v32;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (_DWORD)LogAdapter::g_Logger,
      v24,
      3,
      (unsigned int)": {0}",
      (__int64)v29);
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
0x140016dc8  mov     [rsp-8+arg_8], rsi
0x140016dcd  mov     [rsp-8+arg_10], rdi
0x140016dd2  push    rbp
0x140016dd3  mov     rbp, rsp
0x140016dd6  sub     rsp, 80h
0x140016ddd  mov     rax, cs:__security_cookie
0x140016de4  xor     rax, rsp
0x140016de7  mov     [rbp+var_8], rax
0x140016deb  mov     rsi, [rbp+arg_38]
0x140016def  xorps   xmm0, xmm0
0x140016df2  mov     [rbp+lpFileName], rcx
0x140016df6  mov     [rbp+var_10], 0
0x140016dfe  mov     qword ptr [rbp+SecurityAttributes.nLength], 18h
0x140016e06  movups  xmmword ptr [rbp+SecurityAttributes.lpSecurityDescriptor], xmm0
0x140016e0a  test    rcx, rcx
0x140016e0d  jnz     short loc_140016E7E
0x140016e0f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140016e16  mov     edi, 80070057h
0x140016e1b  mov     dword ptr [rbp+var_10], edi
0x140016e1e  test    rcx, rcx
0x140016e21  jz      short loc_140016E5F
0x140016e23  xor     edx, edx
0x140016e25  lea     r9, aNoFilePathSpec; "No file path specified"
0x140016e2c  lea     r8d, [rdx+3]
0x140016e30  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140016e35  lea     rcx, [rbp+var_38]
0x140016e39  mov     r8d, 3
0x140016e3f  mov     qword ptr [rsp+80h+dwCreationDisposition], rcx; int
0x140016e44  lea     rax, [rbp+var_10]
0x140016e48  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140016e4f  lea     r9, asc_14002D4FC; ": {}"
0x140016e56  mov     qword ptr [rbp+var_38], rax
0x140016e5a  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140016e5f  mov     edx, 54Dh; void *
0x140016e64  mov     rcx, [rbp+8]; this
0x140016e68  lea     r8, aOnecoreBaseCbs_8; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x140016e6f  mov     r9d, edi; char *
0x140016e72  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140016e77  mov     eax, edi
0x140016e79  jmp     loc_140017097
0x140016e7e  test    rsi, rsi
0x140016e81  jnz     short loc_140016ED8
0x140016e83  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140016e8a  mov     edi, 80004003h
0x140016e8f  mov     dword ptr [rbp+var_10], edi
0x140016e92  test    rcx, rcx
0x140016e95  jz      short loc_140016ED1
0x140016e97  lea     r9, aNoFileHandleRe; "No file handle result specified"
0x140016e9e  xor     edx, edx
0x140016ea0  lea     r8d, [rsi+3]
0x140016ea4  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140016ea9  lea     rcx, [rbp+var_38]
0x140016ead  mov     qword ptr [rsp+80h+dwCreationDisposition], rcx
0x140016eb2  lea     rax, [rbp+var_10]
0x140016eb6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140016ebd  lea     r9, asc_14002D4FC; ": {}"
0x140016ec4  lea     r8d, [rsi+3]
0x140016ec8  mov     qword ptr [rbp+var_38], rax
0x140016ecc  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140016ed1  mov     edx, 54Eh; bool *
0x140016ed6  jmp     short loc_140016E64
0x140016ed8  lea     rcx, [rbp+var_40]; this
0x140016edc  mov     [rbp+var_40], 0
0x140016ee0  call    ?CanSetSystemOwner@Rtl@Implementation@WCP@Windows@@YAJPEA_N@Z; Windows::WCP::Implementation::Rtl::CanSetSystemOwner(bool *)
0x140016ee5  mov     edi, eax
0x140016ee7  test    eax, eax
0x140016ee9  jns     short loc_140016F4C
0x140016eeb  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140016ef2  mov     dword ptr [rbp+var_10], eax
0x140016ef5  test    rcx, rcx
0x140016ef8  jz      short loc_140016F36
0x140016efa  xor     edx, edx
0x140016efc  lea     r9, aFailedCallingC; "Failed calling CanSetSystemOwner"
0x140016f03  lea     r8d, [rdx+3]
0x140016f07  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140016f0c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140016f13  lea     rax, [rbp+var_10]
0x140016f17  mov     qword ptr [rbp+var_38], rax
0x140016f1b  lea     r9, asc_14002D4FC; ": {}"
0x140016f22  lea     rax, [rbp+var_38]
0x140016f26  mov     r8d, 3
0x140016f2c  mov     qword ptr [rsp+80h+dwCreationDisposition], rax; int
0x140016f31  call    ??$LogNumObjects@U?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatNtStatusWrapper<long> const &)
0x140016f36  mov     edx, 55Eh; void *
0x140016f3b  mov     rcx, [rbp+8]; this
0x140016f3f  mov     r9d, edi; char *
0x140016f42  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x140016f47  jmp     loc_140017097
0x140016f4c  cmp     [rbp+var_40], 0
0x140016f50  jz      short loc_140016FBB
0x140016f52  lea     rcx, [rbp+var_10]; this
0x140016f56  call    ?GetSystemSecurity@Rtl@Implementation@WCP@Windows@@YAJPEAPEAU_SECURITY_DESCRIPTOR@@@Z; Windows::WCP::Implementation::Rtl::GetSystemSecurity(_SECURITY_DESCRIPTOR * *)
0x140016f5b  mov     edi, eax
0x140016f5d  test    eax, eax
0x140016f5f  jns     short loc_140016FB3
0x140016f61  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140016f68  mov     dword ptr [rbp+var_10], eax
0x140016f6b  test    rcx, rcx
0x140016f6e  jz      short loc_140016FAC
0x140016f70  xor     edx, edx
0x140016f72  lea     r9, aFailedCallingG; "Failed calling GetSystemSecurity"
0x140016f79  lea     r8d, [rdx+3]
0x140016f7d  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140016f82  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140016f89  lea     rax, [rbp+var_10]
0x140016f8d  mov     qword ptr [rbp+var_38], rax
0x140016f91  lea     r9, asc_14002D4FC; ": {}"
0x140016f98  lea     rax, [rbp+var_38]
0x140016f9c  mov     r8d, 3
0x140016fa2  mov     qword ptr [rsp+80h+dwCreationDisposition], rax
0x140016fa7  call    ??$LogNumObjects@U?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatNtStatusWrapper<long> const &)
0x140016fac  mov     edx, 564h
0x140016fb1  jmp     short loc_140016F3B
0x140016fb3  mov     rax, [rbp+var_10]
0x140016fb7  mov     [rbp+SecurityAttributes.lpSecurityDescriptor], rax
0x140016fbb  xor     edi, edi
0x140016fbd  mov     rcx, [rbp+lpFileName]; lpFileName
0x140016fc1  lea     r9, [rbp+SecurityAttributes]; lpSecurityAttributes
0x140016fc5  mov     [rsp+80h+hTemplateFile], 0; hTemplateFile
0x140016fce  xor     r8d, r8d; dwShareMode
0x140016fd1  mov     [rsp+80h+dwFlagsAndAttributes], 2000080h; dwFlagsAndAttributes
0x140016fd9  mov     edx, 40000001h; dwDesiredAccess
0x140016fde  mov     [rsp+80h+dwCreationDisposition], 2; dwCreationDisposition
0x140016fe6  call    cs:__imp_CreateFileW
0x140016fec  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140016ff0  jnz     loc_140017092
0x140016ff6  mov     ecx, 3E8h; dwMilliseconds
0x140016ffb  call    cs:__imp_Sleep
0x140017001  inc     edi
0x140017003  cmp     edi, 3
0x140017006  jb      short loc_140016FBD
0x140017008  call    cs:__imp_GetLastError
0x14001700e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140017015  mov     edi, eax
0x140017017  test    rcx, rcx
0x14001701a  jz      short loc_140017074
0x14001701c  xor     edx, edx
0x14001701e  lea     rax, [rbp+lpFileName]
0x140017022  lea     r9, aFailedToCreate_0; "Failed to create file: {}"
0x140017029  mov     qword ptr [rsp+80h+dwCreationDisposition], rax
0x14001702e  lea     r8d, [rdx+3]
0x140017032  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x140017037  test    edi, edi
0x140017039  jg      short loc_14001703F
0x14001703b  mov     eax, edi
0x14001703d  jmp     short loc_140017047
0x14001703f  movzx   eax, di
0x140017042  or      eax, 80070000h
0x140017047  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001704e  lea     r9, a0; ": {0}"
0x140017055  mov     dword ptr [rbp+var_10], eax
0x140017058  mov     r8d, 3
0x14001705e  lea     rax, [rbp+var_10]
0x140017062  mov     qword ptr [rbp+var_38], rax
0x140017066  lea     rax, [rbp+var_38]
0x14001706a  mov     qword ptr [rsp+80h+dwCreationDisposition], rax; unsigned int
0x14001706f  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140017074  test    edi, edi
0x140017076  jz      short loc_140017095
0x140017078  mov     rcx, [rbp+8]; this
0x14001707c  lea     r8, aOnecoreBaseCbs_8; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x140017083  mov     r9d, edi; char *
0x140017086  mov     edx, 580h; void *
0x14001708b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x140017090  jmp     short loc_140017097
0x140017092  mov     [rsi], rax
0x140017095  xor     eax, eax
0x140017097  mov     rcx, [rbp+var_8]
0x14001709b  xor     rcx, rsp; StackCookie
0x14001709e  call    __security_check_cookie
0x1400170a3  lea     r11, [rsp+80h+var_s0]
0x1400170ab  mov     rsi, [r11+18h]
0x1400170af  mov     rdi, [r11+20h]
0x1400170b3  mov     rsp, r11
0x1400170b6  pop     rbp
0x1400170b7  retn
```
