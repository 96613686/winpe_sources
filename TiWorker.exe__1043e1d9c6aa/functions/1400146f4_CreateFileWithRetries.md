# CreateFileWithRetries

- ea: `0x1400146f4`
- end: `0x1400149e4`
- name: `CreateFileWithRetries`
- size: `752`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x14000f5b0`
- `0x1400144ec`

## callees

- `0x140002310`
- `0x1400053c0`
- `0x140008d38`
- `0x140008ef4`
- `0x14000d910`
- `0x14000f36c`
- `0x14001093c`
- `0x140014104`
- `0x1400146f4`
- `0x1400266a4`
- `0x1400269f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140014934`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140014934`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140014912`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140014912`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140014927`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140014927`

## string_xrefs

- `0x140014751`: `No file path specified`
- `0x14001489e`: `Failed calling GetSystemSecurity`
- `0x14001494e`: `Failed to create file: {}`

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
  __int64 v9; // rdx
  __int64 v10; // rdx
  __int64 v12; // rdx
  int CanSetSystemOwner; // eax
  struct _SECURITY_DESCRIPTOR **v14; // rdx
  unsigned int v15; // r8d
  unsigned int v16; // edi
  __int64 v17; // rdx
  __int64 v18; // rdx
  int SystemSecurity; // eax
  __int64 v20; // rdx
  unsigned int i; // edi
  HANDLE v22; // rax
  signed int LastError; // edi
  __int64 v24; // rdx
  unsigned int v25; // eax
  int dwCreationDisposition; // [rsp+20h] [rbp-60h]
  _BYTE v27[8]; // [rsp+40h] [rbp-40h] BYREF
  unsigned int v28[2]; // [rsp+48h] [rbp-38h] BYREF
  LPCWSTR lpFileName; // [rsp+50h] [rbp-30h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+58h] [rbp-28h] BYREF
  void *v31; // [rsp+70h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+8h]

  lpFileName = a1;
  v31 = 0;
  *(_QWORD *)&SecurityAttributes.nLength = 24;
  *(_OWORD *)&SecurityAttributes.lpSecurityDescriptor = 0;
  if ( !a1 )
  {
    v8 = -2147024809;
    LODWORD(v31) = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No file path specified");
      *(_QWORD *)v28 = &v31;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v9,
        3,
        (__int64)": {}",
        (__int64)v28);
    }
    v10 = 1357;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
      (const char *)v8);
    return v8;
  }
  if ( !a8 )
  {
    v8 = -2147467261;
    LODWORD(v31) = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No file handle result specified");
      *(_QWORD *)v28 = &v31;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v12,
        3,
        (__int64)": {}",
        (__int64)v28);
    }
    v10 = 1358;
    goto LABEL_5;
  }
  v27[0] = 0;
  CanSetSystemOwner = Windows::WCP::Implementation::Rtl::CanSetSystemOwner((Windows::WCP::Implementation::Rtl *)v27, a2);
  v16 = CanSetSystemOwner;
  if ( CanSetSystemOwner < 0 )
  {
    LODWORD(v31) = CanSetSystemOwner;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed calling CanSetSystemOwner");
      *(_QWORD *)v28 = &v31;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v17,
        3,
        (__int64)": {}",
        (__int64)v28);
    }
    v18 = 1374;
    return wil::details::in1diag3::Return_NtStatus(retaddr, (void *)v18, v15, (const char *)v16, dwCreationDisposition);
  }
  if ( v27[0] )
  {
    SystemSecurity = Windows::WCP::Implementation::Rtl::GetSystemSecurity(
                       (Windows::WCP::Implementation::Rtl *)&v31,
                       v14);
    v16 = SystemSecurity;
    if ( SystemSecurity < 0 )
    {
      LODWORD(v31) = SystemSecurity;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed calling GetSystemSecurity");
        *(_QWORD *)v28 = &v31;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          v20,
          3,
          (__int64)": {}",
          (__int64)v28);
      }
      v18 = 1380;
      return wil::details::in1diag3::Return_NtStatus(
               retaddr,
               (void *)v18,
               v15,
               (const char *)v16,
               dwCreationDisposition);
    }
    SecurityAttributes.lpSecurityDescriptor = v31;
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
      (__int64)LogAdapter::g_Logger,
      0,
      3,
      (__int64)"Failed to create file: {}",
      (__int64)&lpFileName);
    if ( LastError > 0 )
      v25 = (unsigned __int16)LastError | 0x80070000;
    else
      v25 = LastError;
    LODWORD(v31) = v25;
    *(_QWORD *)v28 = &v31;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (__int64)LogAdapter::g_Logger,
      v24,
      3,
      (__int64)": {0}",
      (__int64)v28);
  }
  if ( LastError )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x580,
             (int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
             (const char *)(unsigned int)LastError);
  return 0;
}

```

## disassembly

```asm
0x1400146f4  mov     [rsp-8+arg_8], rsi
0x1400146f9  mov     [rsp-8+arg_10], rdi
0x1400146fe  push    rbp
0x1400146ff  mov     rbp, rsp
0x140014702  sub     rsp, 80h
0x140014709  mov     rax, cs:__security_cookie
0x140014710  xor     rax, rsp
0x140014713  mov     [rbp+var_8], rax
0x140014717  mov     rsi, [rbp+arg_38]
0x14001471b  xorps   xmm0, xmm0
0x14001471e  mov     [rbp+lpFileName], rcx
0x140014722  mov     [rbp+var_10], 0
0x14001472a  mov     qword ptr [rbp+SecurityAttributes.nLength], 18h
0x140014732  movups  xmmword ptr [rbp+SecurityAttributes.lpSecurityDescriptor], xmm0
0x140014736  test    rcx, rcx
0x140014739  jnz     short loc_1400147AA
0x14001473b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140014742  mov     edi, 80070057h
0x140014747  mov     dword ptr [rbp+var_10], edi
0x14001474a  test    rcx, rcx
0x14001474d  jz      short loc_14001478B
0x14001474f  xor     edx, edx
0x140014751  lea     r9, aNoFilePathSpec; "No file path specified"
0x140014758  lea     r8d, [rdx+3]
0x14001475c  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140014761  lea     rcx, [rbp+var_38]
0x140014765  mov     r8d, 3
0x14001476b  mov     qword ptr [rsp+80h+dwCreationDisposition], rcx; int
0x140014770  lea     rax, [rbp+var_10]
0x140014774  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001477b  lea     r9, asc_140030534; ": {}"
0x140014782  mov     qword ptr [rbp+var_38], rax
0x140014786  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001478b  mov     edx, 54Dh; void *
0x140014790  mov     rcx, [rbp+8]; this
0x140014794  lea     r8, aOnecoreBaseCbs_4; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x14001479b  mov     r9d, edi; char *
0x14001479e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400147a3  mov     eax, edi
0x1400147a5  jmp     loc_1400149C3
0x1400147aa  test    rsi, rsi
0x1400147ad  jnz     short loc_140014804
0x1400147af  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400147b6  mov     edi, 80004003h
0x1400147bb  mov     dword ptr [rbp+var_10], edi
0x1400147be  test    rcx, rcx
0x1400147c1  jz      short loc_1400147FD
0x1400147c3  lea     r9, aNoFileHandleRe; "No file handle result specified"
0x1400147ca  xor     edx, edx
0x1400147cc  lea     r8d, [rsi+3]
0x1400147d0  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1400147d5  lea     rcx, [rbp+var_38]
0x1400147d9  mov     qword ptr [rsp+80h+dwCreationDisposition], rcx
0x1400147de  lea     rax, [rbp+var_10]
0x1400147e2  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400147e9  lea     r9, asc_140030534; ": {}"
0x1400147f0  lea     r8d, [rsi+3]
0x1400147f4  mov     qword ptr [rbp+var_38], rax
0x1400147f8  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1400147fd  mov     edx, 54Eh; bool *
0x140014802  jmp     short loc_140014790
0x140014804  lea     rcx, [rbp+var_40]; this
0x140014808  mov     [rbp+var_40], 0
0x14001480c  call    ?CanSetSystemOwner@Rtl@Implementation@WCP@Windows@@YAJPEA_N@Z; Windows::WCP::Implementation::Rtl::CanSetSystemOwner(bool *)
0x140014811  mov     edi, eax
0x140014813  test    eax, eax
0x140014815  jns     short loc_140014878
0x140014817  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001481e  mov     dword ptr [rbp+var_10], eax
0x140014821  test    rcx, rcx
0x140014824  jz      short loc_140014862
0x140014826  xor     edx, edx
0x140014828  lea     r9, aFailedCallingC; "Failed calling CanSetSystemOwner"
0x14001482f  lea     r8d, [rdx+3]
0x140014833  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140014838  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001483f  lea     rax, [rbp+var_10]
0x140014843  mov     qword ptr [rbp+var_38], rax
0x140014847  lea     r9, asc_140030534; ": {}"
0x14001484e  lea     rax, [rbp+var_38]
0x140014852  mov     r8d, 3
0x140014858  mov     qword ptr [rsp+80h+dwCreationDisposition], rax; int
0x14001485d  call    ??$LogNumObjects@U?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatNtStatusWrapper<long> const &)
0x140014862  mov     edx, 55Eh; void *
0x140014867  mov     rcx, [rbp+8]; this
0x14001486b  mov     r9d, edi; char *
0x14001486e  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x140014873  jmp     loc_1400149C3
0x140014878  cmp     [rbp+var_40], 0
0x14001487c  jz      short loc_1400148E7
0x14001487e  lea     rcx, [rbp+var_10]; this
0x140014882  call    ?GetSystemSecurity@Rtl@Implementation@WCP@Windows@@YAJPEAPEAU_SECURITY_DESCRIPTOR@@@Z; Windows::WCP::Implementation::Rtl::GetSystemSecurity(_SECURITY_DESCRIPTOR * *)
0x140014887  mov     edi, eax
0x140014889  test    eax, eax
0x14001488b  jns     short loc_1400148DF
0x14001488d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140014894  mov     dword ptr [rbp+var_10], eax
0x140014897  test    rcx, rcx
0x14001489a  jz      short loc_1400148D8
0x14001489c  xor     edx, edx
0x14001489e  lea     r9, aFailedCallingG; "Failed calling GetSystemSecurity"
0x1400148a5  lea     r8d, [rdx+3]
0x1400148a9  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1400148ae  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400148b5  lea     rax, [rbp+var_10]
0x1400148b9  mov     qword ptr [rbp+var_38], rax
0x1400148bd  lea     r9, asc_140030534; ": {}"
0x1400148c4  lea     rax, [rbp+var_38]
0x1400148c8  mov     r8d, 3
0x1400148ce  mov     qword ptr [rsp+80h+dwCreationDisposition], rax
0x1400148d3  call    ??$LogNumObjects@U?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatNtStatusWrapper<long> const &)
0x1400148d8  mov     edx, 564h
0x1400148dd  jmp     short loc_140014867
0x1400148df  mov     rax, [rbp+var_10]
0x1400148e3  mov     [rbp+SecurityAttributes.lpSecurityDescriptor], rax
0x1400148e7  xor     edi, edi
0x1400148e9  mov     rcx, [rbp+lpFileName]; lpFileName
0x1400148ed  lea     r9, [rbp+SecurityAttributes]; lpSecurityAttributes
0x1400148f1  mov     [rsp+80h+hTemplateFile], 0; hTemplateFile
0x1400148fa  xor     r8d, r8d; dwShareMode
0x1400148fd  mov     [rsp+80h+dwFlagsAndAttributes], 2000080h; dwFlagsAndAttributes
0x140014905  mov     edx, 40000001h; dwDesiredAccess
0x14001490a  mov     [rsp+80h+dwCreationDisposition], 2; dwCreationDisposition
0x140014912  call    cs:__imp_CreateFileW
0x140014918  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14001491c  jnz     loc_1400149BE
0x140014922  mov     ecx, 3E8h; dwMilliseconds
0x140014927  call    cs:__imp_Sleep
0x14001492d  inc     edi
0x14001492f  cmp     edi, 3
0x140014932  jb      short loc_1400148E9
0x140014934  call    cs:__imp_GetLastError
0x14001493a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140014941  mov     edi, eax
0x140014943  test    rcx, rcx
0x140014946  jz      short loc_1400149A0
0x140014948  xor     edx, edx
0x14001494a  lea     rax, [rbp+lpFileName]
0x14001494e  lea     r9, aFailedToCreate_6; "Failed to create file: {}"
0x140014955  mov     qword ptr [rsp+80h+dwCreationDisposition], rax
0x14001495a  lea     r8d, [rdx+3]
0x14001495e  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x140014963  test    edi, edi
0x140014965  jg      short loc_14001496B
0x140014967  mov     eax, edi
0x140014969  jmp     short loc_140014973
0x14001496b  movzx   eax, di
0x14001496e  or      eax, 80070000h
0x140014973  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001497a  lea     r9, a0; ": {0}"
0x140014981  mov     dword ptr [rbp+var_10], eax
0x140014984  mov     r8d, 3
0x14001498a  lea     rax, [rbp+var_10]
0x14001498e  mov     qword ptr [rbp+var_38], rax
0x140014992  lea     rax, [rbp+var_38]
0x140014996  mov     qword ptr [rsp+80h+dwCreationDisposition], rax; unsigned int
0x14001499b  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1400149a0  test    edi, edi
0x1400149a2  jz      short loc_1400149C1
0x1400149a4  mov     rcx, [rbp+8]; this
0x1400149a8  lea     r8, aOnecoreBaseCbs_4; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x1400149af  mov     r9d, edi; char *
0x1400149b2  mov     edx, 580h; void *
0x1400149b7  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1400149bc  jmp     short loc_1400149C3
0x1400149be  mov     [rsi], rax
0x1400149c1  xor     eax, eax
0x1400149c3  mov     rcx, [rbp+var_8]
0x1400149c7  xor     rcx, rsp; StackCookie
0x1400149ca  call    __security_check_cookie
0x1400149cf  lea     r11, [rsp+80h+var_s0]
0x1400149d7  mov     rsi, [r11+18h]
0x1400149db  mov     rdi, [r11+20h]
0x1400149df  mov     rsp, r11
0x1400149e2  pop     rbp
0x1400149e3  retn
```
