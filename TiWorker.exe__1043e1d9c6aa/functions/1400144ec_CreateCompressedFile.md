# CreateCompressedFile

- ea: `0x1400144ec`
- end: `0x1400146eb`
- name: `CreateCompressedFile`
- size: `511`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14000f5b0`

## callees

- `0x140002310`
- `0x1400053c0`
- `0x140008d38`
- `0x140008ef4`
- `0x14000d910`
- `0x1400123a4`
- `0x1400144ec`
- `0x1400146f4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001469d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001469d`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x140014693`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x140014693`

## string_xrefs

- `0x140014543`: `No file path specified`
- `0x1400146c7`: `Failed NTFS compressing file {}`

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
  signed int LastError; // eax
  __int64 v16; // rcx
  int lpOutBuffer; // [rsp+20h] [rbp-58h]
  DWORD nOutBufferSize; // [rsp+28h] [rbp-50h]
  int lpBytesReturned; // [rsp+30h] [rbp-48h]
  int v20[2]; // [rsp+40h] [rbp-38h] BYREF
  const WCHAR *v21; // [rsp+48h] [rbp-30h] BYREF
  int v22; // [rsp+50h] [rbp-28h] BYREF
  __int16 InBuffer; // [rsp+54h] [rbp-24h] BYREF
  DWORD BytesReturned; // [rsp+58h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+20h]

  InBuffer = 2;
  v21 = a1;
  BytesReturned = 0;
  if ( !a1 )
  {
    v8 = -2147024809;
    v22 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No file path specified");
      *(_QWORD *)v20 = &v22;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v9,
        3,
        (__int64)": {}",
        (__int64)v20);
    }
    v10 = 1433;
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
    v22 = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No file handle result specified");
      *(_QWORD *)v20 = &v22;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v12,
        3,
        (__int64)": {}",
        (__int64)v20);
    }
    v10 = 1434;
    goto LABEL_5;
  }
  FileWithRetries = CreateFileWithRetries(a1, a2, a3, a4, lpOutBuffer, nOutBufferSize, lpBytesReturned, a8);
  v8 = FileWithRetries;
  if ( FileWithRetries < 0 )
  {
    v22 = FileWithRetries;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (__int64)"Failed creating file {}",
        (__int64)&v21);
      *(_QWORD *)v20 = &v22;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v14,
        3,
        (__int64)": {}",
        (__int64)v20);
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
      LogAdapter::TraceAtLevelHr<long,wchar_t const *>(
        v16,
        (unsigned int)LastError,
        "Failed NTFS compressing file {}",
        &v21);
  }
  return 0;
}

```

## disassembly

```asm
0x1400144ec  push    rbp
0x1400144ee  push    rbx
0x1400144ef  push    rdi
0x1400144f0  push    r14
0x1400144f2  mov     rbp, rsp
0x1400144f5  sub     rsp, 78h
0x1400144f9  mov     rax, cs:__security_cookie
0x140014500  xor     rax, rsp
0x140014503  mov     [rbp+var_18], rax
0x140014507  mov     rdi, [rbp+arg_38]
0x14001450b  mov     r14d, 2
0x140014511  mov     [rbp+InBuffer], r14w
0x140014516  mov     [rbp+var_30], rcx
0x14001451a  mov     [rbp+BytesReturned], 0
0x140014521  test    rcx, rcx
0x140014524  jnz     short loc_140014595
0x140014526  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001452d  mov     ebx, 80070057h
0x140014532  mov     [rbp+var_28], ebx
0x140014535  test    rcx, rcx
0x140014538  jz      short loc_140014576
0x14001453a  lea     edi, [r14+1]
0x14001453e  xor     edx, edx
0x140014540  mov     r8d, edi
0x140014543  lea     r9, aNoFilePathSpec; "No file path specified"
0x14001454a  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14001454f  lea     rcx, [rbp+var_38]
0x140014553  mov     r8d, edi
0x140014556  mov     [rsp+78h+lpOutBuffer], rcx; int
0x14001455b  lea     rax, [rbp+var_28]
0x14001455f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140014566  lea     r9, asc_140030534; ": {}"
0x14001456d  mov     qword ptr [rbp+var_38], rax
0x140014571  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140014576  mov     edx, 599h; void *
0x14001457b  mov     rcx, [rbp+20h]; this
0x14001457f  lea     r8, aOnecoreBaseCbs_4; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x140014586  mov     r9d, ebx; char *
0x140014589  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001458e  mov     eax, ebx
0x140014590  jmp     loc_1400146D5
0x140014595  test    rdi, rdi
0x140014598  jnz     short loc_1400145F2
0x14001459a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400145a1  mov     ebx, 80004003h
0x1400145a6  mov     [rbp+var_28], ebx
0x1400145a9  test    rcx, rcx
0x1400145ac  jz      short loc_1400145EB
0x1400145ae  mov     edi, 3
0x1400145b3  lea     r9, aNoFileHandleRe; "No file handle result specified"
0x1400145ba  mov     r8d, edi
0x1400145bd  xor     edx, edx
0x1400145bf  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1400145c4  lea     rcx, [rbp+var_38]
0x1400145c8  mov     r8d, edi
0x1400145cb  mov     [rsp+78h+lpOutBuffer], rcx
0x1400145d0  lea     rax, [rbp+var_28]
0x1400145d4  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400145db  lea     r9, asc_140030534; ": {}"
0x1400145e2  mov     qword ptr [rbp+var_38], rax
0x1400145e6  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1400145eb  mov     edx, 59Ah
0x1400145f0  jmp     short loc_14001457B
0x1400145f2  mov     [rsp+78h+lpOverlapped], rdi
0x1400145f7  call    CreateFileWithRetries
0x1400145fc  mov     ebx, eax
0x1400145fe  test    eax, eax
0x140014600  jns     short loc_140014661
0x140014602  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140014609  mov     [rbp+var_28], eax
0x14001460c  test    rcx, rcx
0x14001460f  jz      short loc_140014657
0x140014611  lea     rax, [rbp+var_30]
0x140014615  mov     edi, 3
0x14001461a  mov     r8d, edi
0x14001461d  mov     [rsp+78h+lpOutBuffer], rax
0x140014622  lea     r9, aFailedCreating; "Failed creating file {}"
0x140014629  xor     edx, edx
0x14001462b  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x140014630  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140014637  lea     rax, [rbp+var_28]
0x14001463b  mov     qword ptr [rbp+var_38], rax
0x14001463f  lea     r9, asc_140030534; ": {}"
0x140014646  lea     rax, [rbp+var_38]
0x14001464a  mov     r8d, edi
0x14001464d  mov     [rsp+78h+lpOutBuffer], rax
0x140014652  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140014657  mov     edx, 5A0h
0x14001465c  jmp     loc_14001457B
0x140014661  mov     rcx, [rdi]; hDevice
0x140014664  lea     rax, [rbp+BytesReturned]
0x140014668  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x140014671  lea     r8, [rbp+InBuffer]; lpInBuffer
0x140014675  mov     [rsp+78h+lpBytesReturned], rax; lpBytesReturned
0x14001467a  mov     r9d, r14d; nInBufferSize
0x14001467d  mov     [rsp+78h+nOutBufferSize], 0; nOutBufferSize
0x140014685  mov     edx, 9C040h; dwIoControlCode
0x14001468a  mov     [rsp+78h+lpOutBuffer], 0; lpOutBuffer
0x140014693  call    cs:__imp_DeviceIoControl
0x140014699  test    eax, eax
0x14001469b  jnz     short loc_1400146D3
0x14001469d  call    cs:__imp_GetLastError
0x1400146a3  test    eax, eax
0x1400146a5  jle     short loc_1400146AF
0x1400146a7  movzx   eax, ax
0x1400146aa  or      eax, 80070000h
0x1400146af  cmp     eax, 80070001h
0x1400146b4  jz      short loc_1400146D3
0x1400146b6  cmp     eax, 80070032h
0x1400146bb  jz      short loc_1400146D3
0x1400146bd  test    eax, eax
0x1400146bf  jns     short loc_1400146D3
0x1400146c1  lea     r9, [rbp+var_30]
0x1400146c5  mov     edx, eax
0x1400146c7  lea     r8, aFailedNtfsComp; "Failed NTFS compressing file {}"
0x1400146ce  call    ??$TraceAtLevelHr@JPEB_W@LogAdapter@@YAXW4LogLevel@0@JQEBDAEBQEB_W@Z; LogAdapter::TraceAtLevelHr<long,wchar_t const *>(LogAdapter::LogLevel,long,char const * const,wchar_t const * const &)
0x1400146d3  xor     eax, eax
0x1400146d5  mov     rcx, [rbp+var_18]
0x1400146d9  xor     rcx, rsp; StackCookie
0x1400146dc  call    __security_check_cookie
0x1400146e1  add     rsp, 78h
0x1400146e5  pop     r14
0x1400146e7  pop     rdi
0x1400146e8  pop     rbx
0x1400146e9  pop     rbp
0x1400146ea  retn
```
