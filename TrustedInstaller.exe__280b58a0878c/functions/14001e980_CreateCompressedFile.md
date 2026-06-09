# CreateCompressedFile

- ea: `0x14001e980`
- end: `0x14001eb6c`
- name: `CreateCompressedFile`
- size: `492`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140018630`

## callees

- `0x1400023e0`
- `0x1400054b0`
- `0x140016a40`
- `0x140016bfc`
- `0x140016fb4`
- `0x14001e898`
- `0x14001e980`
- `0x14001eb74`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001eb25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001eb25`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x14001eb1b`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x14001eb1b`

## string_xrefs

- `0x14001e9ce`: `No file path specified`

## pseudocode

```c
__int64 __fastcall CreateCompressedFile(
        const WCHAR *a1,
        bool *a2,
        __int64 a3,
        __int64 a4,
        int a5,
        int a6,
        int a7,
        HANDLE *a8)
{
  unsigned int v8; // ebx
  __int64 v9; // rdx
  __int64 v10; // rdx
  __int64 v12; // rdx
  int FileWithRetries; // eax
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // rdx
  signed int LastError; // eax
  __int64 v18; // rcx
  __int64 v19; // r8
  int lpOutBuffer; // [rsp+20h] [rbp-58h]
  DWORD nOutBufferSize; // [rsp+28h] [rbp-50h]
  int lpBytesReturned; // [rsp+30h] [rbp-48h]
  int v23[2]; // [rsp+40h] [rbp-38h] BYREF
  const WCHAR *v24; // [rsp+48h] [rbp-30h] BYREF
  int v25; // [rsp+50h] [rbp-28h] BYREF
  __int16 InBuffer; // [rsp+54h] [rbp-24h] BYREF
  DWORD BytesReturned; // [rsp+58h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+20h]

  InBuffer = 2;
  v24 = a1;
  BytesReturned = 0;
  if ( !a1 )
  {
    v8 = -2147024809;
    v25 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No file path specified");
      *(_QWORD *)v23 = &v25;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v9,
        3,
        (__int64)": {}",
        (__int64)v23);
    }
    v10 = 1433;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
      (const char *)v8,
      lpOutBuffer);
    return v8;
  }
  if ( !a8 )
  {
    v8 = -2147467261;
    v25 = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No file handle result specified");
      *(_QWORD *)v23 = &v25;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v12,
        3,
        (__int64)": {}",
        (__int64)v23);
    }
    v10 = 1434;
    goto LABEL_5;
  }
  FileWithRetries = CreateFileWithRetries(a1, a2, a3, a4, lpOutBuffer, nOutBufferSize, lpBytesReturned, a8);
  v8 = FileWithRetries;
  if ( FileWithRetries < 0 )
  {
    v25 = FileWithRetries;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (__int64)LogAdapter::g_Logger,
        v14,
        v15,
        (__int64)"Failed creating file {}",
        (__int64)&v24);
      *(_QWORD *)v23 = &v25;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v16,
        3,
        (__int64)": {}",
        (__int64)v23);
    }
    v10 = 1440;
    goto LABEL_5;
  }
  if ( !DeviceIoControl(*a8, 0x9C040u, &InBuffer, 2u, 0, 0, &BytesReturned, 0) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( LastError != -2147024895 && LastError != -2147024846 && LastError < 0 )
      LogAdapter::TraceAtLevelHr<long,wchar_t const *>(v18, (unsigned int)LastError, v19, (__int64)&v24);
  }
  return 0;
}

```

## disassembly

```asm
0x14001e980  push    rbp
0x14001e982  push    rbx
0x14001e983  push    rdi
0x14001e984  push    r14
0x14001e986  mov     rbp, rsp
0x14001e989  sub     rsp, 78h
0x14001e98d  mov     rax, cs:__security_cookie
0x14001e994  xor     rax, rsp
0x14001e997  mov     [rbp+var_18], rax
0x14001e99b  mov     rdi, [rbp+arg_38]
0x14001e99f  mov     r14d, 2
0x14001e9a5  mov     [rbp+InBuffer], r14w
0x14001e9aa  mov     [rbp+var_30], rcx
0x14001e9ae  mov     [rbp+BytesReturned], 0
0x14001e9b5  test    rcx, rcx
0x14001e9b8  jnz     short loc_14001EA27
0x14001e9ba  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001e9c1  mov     ebx, 80070057h
0x14001e9c6  mov     [rbp+var_28], ebx
0x14001e9c9  test    rcx, rcx
0x14001e9cc  jz      short loc_14001EA08
0x14001e9ce  lea     r9, aNoFilePathSpec; "No file path specified"
0x14001e9d5  xor     edx, edx
0x14001e9d7  lea     r8d, [r14+1]
0x14001e9db  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14001e9e0  lea     rcx, [rbp+var_38]
0x14001e9e4  mov     [rsp+78h+lpOutBuffer], rcx; int
0x14001e9e9  lea     rax, [rbp+var_28]
0x14001e9ed  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001e9f4  lea     r9, asc_1400353E8; ": {}"
0x14001e9fb  lea     r8d, [r14+1]
0x14001e9ff  mov     qword ptr [rbp+var_38], rax
0x14001ea03  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001ea08  mov     edx, 599h; void *
0x14001ea0d  mov     rcx, [rbp+20h]; this
0x14001ea11  lea     r8, aOnecoreBaseCbs_10; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x14001ea18  mov     r9d, ebx; char *
0x14001ea1b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001ea20  mov     eax, ebx
0x14001ea22  jmp     loc_14001EB56
0x14001ea27  test    rdi, rdi
0x14001ea2a  jnz     short loc_14001EA81
0x14001ea2c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001ea33  mov     ebx, 80004003h
0x14001ea38  mov     [rbp+var_28], ebx
0x14001ea3b  test    rcx, rcx
0x14001ea3e  jz      short loc_14001EA7A
0x14001ea40  lea     r9, aNoFileHandleRe; "No file handle result specified"
0x14001ea47  xor     edx, edx
0x14001ea49  lea     r8d, [rdi+3]
0x14001ea4d  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14001ea52  lea     rcx, [rbp+var_38]
0x14001ea56  mov     [rsp+78h+lpOutBuffer], rcx
0x14001ea5b  lea     rax, [rbp+var_28]
0x14001ea5f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001ea66  lea     r9, asc_1400353E8; ": {}"
0x14001ea6d  lea     r8d, [rdi+3]
0x14001ea71  mov     qword ptr [rbp+var_38], rax
0x14001ea75  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001ea7a  mov     edx, 59Ah
0x14001ea7f  jmp     short loc_14001EA0D
0x14001ea81  mov     [rsp+78h+lpOverlapped], rdi
0x14001ea86  call    CreateFileWithRetries
0x14001ea8b  mov     ebx, eax
0x14001ea8d  test    eax, eax
0x14001ea8f  jns     short loc_14001EAE9
0x14001ea91  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001ea98  mov     [rbp+var_28], eax
0x14001ea9b  test    rcx, rcx
0x14001ea9e  jz      short loc_14001EADF
0x14001eaa0  lea     rax, [rbp+var_30]
0x14001eaa4  lea     r9, aFailedCreating; "Failed creating file {}"
0x14001eaab  mov     [rsp+78h+lpOutBuffer], rax
0x14001eab0  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x14001eab5  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001eabc  lea     rax, [rbp+var_28]
0x14001eac0  mov     qword ptr [rbp+var_38], rax
0x14001eac4  lea     r9, asc_1400353E8; ": {}"
0x14001eacb  lea     rax, [rbp+var_38]
0x14001eacf  mov     r8d, 3
0x14001ead5  mov     [rsp+78h+lpOutBuffer], rax
0x14001eada  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001eadf  mov     edx, 5A0h
0x14001eae4  jmp     loc_14001EA0D
0x14001eae9  mov     rcx, [rdi]; hDevice
0x14001eaec  lea     rax, [rbp+BytesReturned]
0x14001eaf0  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x14001eaf9  lea     r8, [rbp+InBuffer]; lpInBuffer
0x14001eafd  mov     [rsp+78h+lpBytesReturned], rax; lpBytesReturned
0x14001eb02  mov     r9d, r14d; nInBufferSize
0x14001eb05  mov     [rsp+78h+nOutBufferSize], 0; nOutBufferSize
0x14001eb0d  mov     edx, 9C040h; dwIoControlCode
0x14001eb12  mov     [rsp+78h+lpOutBuffer], 0; lpOutBuffer
0x14001eb1b  call    cs:__imp_DeviceIoControl
0x14001eb21  test    eax, eax
0x14001eb23  jnz     short loc_14001EB54
0x14001eb25  call    cs:__imp_GetLastError
0x14001eb2b  test    eax, eax
0x14001eb2d  jle     short loc_14001EB37
0x14001eb2f  movzx   eax, ax
0x14001eb32  or      eax, 80070000h
0x14001eb37  cmp     eax, 80070001h
0x14001eb3c  jz      short loc_14001EB54
0x14001eb3e  cmp     eax, 80070032h
0x14001eb43  jz      short loc_14001EB54
0x14001eb45  test    eax, eax
0x14001eb47  jns     short loc_14001EB54
0x14001eb49  lea     r9, [rbp+var_30]
0x14001eb4d  mov     edx, eax
0x14001eb4f  call    ??$TraceAtLevelHr@JPEB_W@LogAdapter@@YAXW4LogLevel@0@JQEBDAEBQEB_W@Z; LogAdapter::TraceAtLevelHr<long,wchar_t const *>(LogAdapter::LogLevel,long,char const * const,wchar_t const * const &)
0x14001eb54  xor     eax, eax
0x14001eb56  mov     rcx, [rbp+var_18]
0x14001eb5a  xor     rcx, rsp; StackCookie
0x14001eb5d  call    __security_check_cookie
0x14001eb62  add     rsp, 78h
0x14001eb66  pop     r14
0x14001eb68  pop     rdi
0x14001eb69  pop     rbx
0x14001eb6a  pop     rbp
0x14001eb6b  retn
```
