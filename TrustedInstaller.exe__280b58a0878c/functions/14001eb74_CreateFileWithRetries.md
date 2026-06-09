# CreateFileWithRetries

- ea: `0x14001eb74`
- end: `0x14001ee4b`
- name: `CreateFileWithRetries`
- size: `727`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x140018630`
- `0x14001e980`

## callees

- `0x1400023e0`
- `0x1400054b0`
- `0x140016a40`
- `0x140016bfc`
- `0x140016fb4`
- `0x1400184fc`
- `0x140019a00`
- `0x14001e95c`
- `0x14001eb74`
- `0x140026498`
- `0x1400267e4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001eda1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001eda1`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14001ed94`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14001ed94`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14001ed7f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14001ed7f`

## string_xrefs

- `0x14001ebd1`: `No file path specified`
- `0x14001ed18`: `Failed calling GetSystemSecurity`
- `0x14001edb9`: `Failed to create file: {}`

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
  unsigned int v8; // ebx
  __int64 v9; // rdx
  __int64 v10; // rdx
  __int64 v12; // rdx
  int CanSetSystemOwner; // eax
  struct _SECURITY_DESCRIPTOR **v14; // rdx
  unsigned int v15; // ebx
  int v16; // edx
  int v17; // r8d
  int v18; // r9d
  __int64 v19; // rdx
  int SystemSecurity; // eax
  int v21; // edx
  int v22; // r8d
  int v23; // r9d
  unsigned int i; // ebx
  HANDLE v25; // rax
  __int64 v26; // rdx
  signed int LastError; // ebx
  __int64 v28; // r8
  __int64 v29; // rdx
  unsigned int v30; // eax
  int dwCreationDisposition; // [rsp+20h] [rbp-60h]
  unsigned int dwCreationDispositiona; // [rsp+20h] [rbp-60h]
  _BYTE v33[8]; // [rsp+40h] [rbp-40h] BYREF
  unsigned int v34[2]; // [rsp+48h] [rbp-38h] BYREF
  LPCWSTR lpFileName; // [rsp+50h] [rbp-30h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+58h] [rbp-28h] BYREF
  void *v37; // [rsp+70h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+8h]

  lpFileName = a1;
  v37 = 0;
  *(_QWORD *)&SecurityAttributes.nLength = 24;
  *(_OWORD *)&SecurityAttributes.lpSecurityDescriptor = 0;
  if ( !a1 )
  {
    v8 = -2147024809;
    LODWORD(v37) = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No file path specified");
      *(_QWORD *)v34 = &v37;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v9,
        3,
        (__int64)": {}",
        (__int64)v34);
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
    LODWORD(v37) = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No file handle result specified");
      *(_QWORD *)v34 = &v37;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v12,
        3,
        (__int64)": {}",
        (__int64)v34);
    }
    v10 = 1358;
    goto LABEL_5;
  }
  v33[0] = 0;
  CanSetSystemOwner = Windows::WCP::Implementation::Rtl::CanSetSystemOwner((Windows::WCP::Implementation::Rtl *)v33, a2);
  v15 = CanSetSystemOwner;
  if ( CanSetSystemOwner < 0 )
  {
    LODWORD(v37) = CanSetSystemOwner;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed calling CanSetSystemOwner");
      *(_QWORD *)v34 = &v37;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v16,
        v17,
        v18,
        (__int64)v34);
    }
    v19 = 1374;
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)v19,
             (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
             (const char *)v15,
             dwCreationDisposition);
  }
  if ( v33[0] )
  {
    SystemSecurity = Windows::WCP::Implementation::Rtl::GetSystemSecurity(
                       (Windows::WCP::Implementation::Rtl *)&v37,
                       v14);
    v15 = SystemSecurity;
    if ( SystemSecurity < 0 )
    {
      LODWORD(v37) = SystemSecurity;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed calling GetSystemSecurity");
        *(_QWORD *)v34 = &v37;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v21,
          v22,
          v23,
          (__int64)v34);
      }
      v19 = 1380;
      return wil::details::in1diag3::Return_NtStatus(
               retaddr,
               (void *)v19,
               (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
               (const char *)v15,
               dwCreationDisposition);
    }
    SecurityAttributes.lpSecurityDescriptor = v37;
  }
  for ( i = 0; i < 3; ++i )
  {
    v25 = CreateFileW(lpFileName, 0x40000001u, 0, &SecurityAttributes, 2u, 0x2000080u, 0);
    if ( v25 != (HANDLE)-1LL )
    {
      *a8 = v25;
      return 0;
    }
    Sleep(0x3E8u);
  }
  LastError = GetLastError();
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<wchar_t const *>(
      (__int64)LogAdapter::g_Logger,
      v26,
      v28,
      (__int64)"Failed to create file: {}",
      (__int64)&lpFileName);
    if ( LastError > 0 )
      v30 = (unsigned __int16)LastError | 0x80070000;
    else
      v30 = LastError;
    LODWORD(v37) = v30;
    *(_QWORD *)v34 = &v37;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (__int64)LogAdapter::g_Logger,
      v29,
      3,
      (__int64)": {0}",
      (__int64)v34);
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
0x14001eb74  mov     [rsp-8+arg_8], rbx
0x14001eb79  mov     [rsp-8+arg_10], rdi
0x14001eb7e  push    rbp
0x14001eb7f  mov     rbp, rsp
0x14001eb82  sub     rsp, 80h
0x14001eb89  mov     rax, cs:__security_cookie
0x14001eb90  xor     rax, rsp
0x14001eb93  mov     [rbp+var_8], rax
0x14001eb97  mov     rdi, [rbp+arg_38]
0x14001eb9b  xorps   xmm0, xmm0
0x14001eb9e  mov     [rbp+lpFileName], rcx
0x14001eba2  mov     [rbp+var_10], 0
0x14001ebaa  mov     qword ptr [rbp+SecurityAttributes.nLength], 18h
0x14001ebb2  movups  xmmword ptr [rbp+SecurityAttributes.lpSecurityDescriptor], xmm0
0x14001ebb6  test    rcx, rcx
0x14001ebb9  jnz     short loc_14001EC2A
0x14001ebbb  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001ebc2  mov     ebx, 80070057h
0x14001ebc7  mov     dword ptr [rbp+var_10], ebx
0x14001ebca  test    rcx, rcx
0x14001ebcd  jz      short loc_14001EC0B
0x14001ebcf  xor     edx, edx
0x14001ebd1  lea     r9, aNoFilePathSpec; "No file path specified"
0x14001ebd8  lea     r8d, [rdx+3]
0x14001ebdc  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14001ebe1  lea     rcx, [rbp+var_38]
0x14001ebe5  mov     r8d, 3
0x14001ebeb  mov     qword ptr [rsp+80h+dwCreationDisposition], rcx; int
0x14001ebf0  lea     rax, [rbp+var_10]
0x14001ebf4  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001ebfb  lea     r9, asc_1400353E8; ": {}"
0x14001ec02  mov     qword ptr [rbp+var_38], rax
0x14001ec06  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001ec0b  mov     edx, 54Dh; void *
0x14001ec10  mov     rcx, [rbp+8]; this
0x14001ec14  lea     r8, aOnecoreBaseCbs_10; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x14001ec1b  mov     r9d, ebx; char *
0x14001ec1e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001ec23  mov     eax, ebx
0x14001ec25  jmp     loc_14001EE2A
0x14001ec2a  test    rdi, rdi
0x14001ec2d  jnz     short loc_14001EC84
0x14001ec2f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001ec36  mov     ebx, 80004003h
0x14001ec3b  mov     dword ptr [rbp+var_10], ebx
0x14001ec3e  test    rcx, rcx
0x14001ec41  jz      short loc_14001EC7D
0x14001ec43  lea     r9, aNoFileHandleRe; "No file handle result specified"
0x14001ec4a  xor     edx, edx
0x14001ec4c  lea     r8d, [rdi+3]
0x14001ec50  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14001ec55  lea     rcx, [rbp+var_38]
0x14001ec59  mov     qword ptr [rsp+80h+dwCreationDisposition], rcx
0x14001ec5e  lea     rax, [rbp+var_10]
0x14001ec62  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001ec69  lea     r9, asc_1400353E8; ": {}"
0x14001ec70  lea     r8d, [rdi+3]
0x14001ec74  mov     qword ptr [rbp+var_38], rax
0x14001ec78  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001ec7d  mov     edx, 54Eh; bool *
0x14001ec82  jmp     short loc_14001EC10
0x14001ec84  lea     rcx, [rbp+var_40]; this
0x14001ec88  mov     [rbp+var_40], 0
0x14001ec8c  call    ?CanSetSystemOwner@Rtl@Implementation@WCP@Windows@@YAJPEA_N@Z; Windows::WCP::Implementation::Rtl::CanSetSystemOwner(bool *)
0x14001ec91  mov     ebx, eax
0x14001ec93  test    eax, eax
0x14001ec95  jns     short loc_14001ECF2
0x14001ec97  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001ec9e  mov     dword ptr [rbp+var_10], eax
0x14001eca1  test    rcx, rcx
0x14001eca4  jz      short loc_14001ECD5
0x14001eca6  xor     edx, edx
0x14001eca8  lea     r9, aFailedCallingC; "Failed calling CanSetSystemOwner"
0x14001ecaf  lea     r8d, [rdx+3]
0x14001ecb3  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14001ecb8  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001ecbf  lea     rax, [rbp+var_10]
0x14001ecc3  mov     qword ptr [rbp+var_38], rax
0x14001ecc7  lea     rax, [rbp+var_38]
0x14001eccb  mov     qword ptr [rsp+80h+dwCreationDisposition], rax; int
0x14001ecd0  call    ??$LogNumObjects@U?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatNtStatusWrapper<long> const &)
0x14001ecd5  mov     edx, 55Eh; void *
0x14001ecda  mov     rcx, [rbp+8]; this
0x14001ecde  lea     r8, aOnecoreBaseCbs_10; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x14001ece5  mov     r9d, ebx; char *
0x14001ece8  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x14001eced  jmp     loc_14001EE2A
0x14001ecf2  cmp     [rbp+var_40], 0
0x14001ecf6  jz      short loc_14001ED54
0x14001ecf8  lea     rcx, [rbp+var_10]; this
0x14001ecfc  call    ?GetSystemSecurity@Rtl@Implementation@WCP@Windows@@YAJPEAPEAU_SECURITY_DESCRIPTOR@@@Z; Windows::WCP::Implementation::Rtl::GetSystemSecurity(_SECURITY_DESCRIPTOR * *)
0x14001ed01  mov     ebx, eax
0x14001ed03  test    eax, eax
0x14001ed05  jns     short loc_14001ED4C
0x14001ed07  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001ed0e  mov     dword ptr [rbp+var_10], eax
0x14001ed11  test    rcx, rcx
0x14001ed14  jz      short loc_14001ED45
0x14001ed16  xor     edx, edx
0x14001ed18  lea     r9, aFailedCallingG; "Failed calling GetSystemSecurity"
0x14001ed1f  lea     r8d, [rdx+3]
0x14001ed23  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14001ed28  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001ed2f  lea     rax, [rbp+var_10]
0x14001ed33  mov     qword ptr [rbp+var_38], rax
0x14001ed37  lea     rax, [rbp+var_38]
0x14001ed3b  mov     qword ptr [rsp+80h+dwCreationDisposition], rax
0x14001ed40  call    ??$LogNumObjects@U?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatNtStatusWrapper<long> const &)
0x14001ed45  mov     edx, 564h
0x14001ed4a  jmp     short loc_14001ECDA
0x14001ed4c  mov     rax, [rbp+var_10]
0x14001ed50  mov     [rbp+SecurityAttributes.lpSecurityDescriptor], rax
0x14001ed54  xor     ebx, ebx
0x14001ed56  mov     rcx, [rbp+lpFileName]; lpFileName
0x14001ed5a  lea     r9, [rbp+SecurityAttributes]; lpSecurityAttributes
0x14001ed5e  mov     [rsp+80h+hTemplateFile], 0; hTemplateFile
0x14001ed67  xor     r8d, r8d; dwShareMode
0x14001ed6a  mov     [rsp+80h+dwFlagsAndAttributes], 2000080h; dwFlagsAndAttributes
0x14001ed72  mov     edx, 40000001h; dwDesiredAccess
0x14001ed77  mov     [rsp+80h+dwCreationDisposition], 2; dwCreationDisposition
0x14001ed7f  call    cs:__imp_CreateFileW
0x14001ed85  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14001ed89  jnz     loc_14001EE25
0x14001ed8f  mov     ecx, 3E8h; dwMilliseconds
0x14001ed94  call    cs:__imp_Sleep
0x14001ed9a  inc     ebx
0x14001ed9c  cmp     ebx, 3
0x14001ed9f  jb      short loc_14001ED56
0x14001eda1  call    cs:__imp_GetLastError
0x14001eda7  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001edae  mov     ebx, eax
0x14001edb0  test    rcx, rcx
0x14001edb3  jz      short loc_14001EE07
0x14001edb5  lea     rax, [rbp+lpFileName]
0x14001edb9  lea     r9, aFailedToCreate_14; "Failed to create file: {}"
0x14001edc0  mov     qword ptr [rsp+80h+dwCreationDisposition], rax
0x14001edc5  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x14001edca  test    ebx, ebx
0x14001edcc  jg      short loc_14001EDD2
0x14001edce  mov     eax, ebx
0x14001edd0  jmp     short loc_14001EDDA
0x14001edd2  movzx   eax, bx
0x14001edd5  or      eax, 80070000h
0x14001edda  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001ede1  lea     r9, a0; ": {0}"
0x14001ede8  mov     dword ptr [rbp+var_10], eax
0x14001edeb  mov     r8d, 3
0x14001edf1  lea     rax, [rbp+var_10]
0x14001edf5  mov     qword ptr [rbp+var_38], rax
0x14001edf9  lea     rax, [rbp+var_38]
0x14001edfd  mov     qword ptr [rsp+80h+dwCreationDisposition], rax; unsigned int
0x14001ee02  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001ee07  test    ebx, ebx
0x14001ee09  jz      short loc_14001EE28
0x14001ee0b  mov     rcx, [rbp+8]; this
0x14001ee0f  lea     r8, aOnecoreBaseCbs_10; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x14001ee16  mov     r9d, ebx; char *
0x14001ee19  mov     edx, 580h; void *
0x14001ee1e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x14001ee23  jmp     short loc_14001EE2A
0x14001ee25  mov     [rdi], rax
0x14001ee28  xor     eax, eax
0x14001ee2a  mov     rcx, [rbp+var_8]
0x14001ee2e  xor     rcx, rsp; StackCookie
0x14001ee31  call    __security_check_cookie
0x14001ee36  lea     r11, [rsp+80h+var_s0]
0x14001ee3e  mov     rbx, [r11+18h]
0x14001ee42  mov     rdi, [r11+20h]
0x14001ee46  mov     rsp, r11
0x14001ee49  pop     rbp
0x14001ee4a  retn
```
