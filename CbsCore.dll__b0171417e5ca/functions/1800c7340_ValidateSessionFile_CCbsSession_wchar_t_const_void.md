# ValidateSessionFile(CCbsSession *,wchar_t const *,void * *)

- ea: `0x1800c7340`
- end: `0x1800c7655`
- name: `?ValidateSessionFile@@YAJPEAVCCbsSession@@PEB_WPEAPEAX@Z`
- size: `789`
- prototype: `int(struct CCbsSession *, const wchar_t *, void **)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x1800c6f6c`

## callees

- `0x180042448`
- `0x180095924`
- `0x180095e34`
- `0x180098538`
- `0x180099548`
- `0x18009cf78`
- `0x1800a02ec`
- `0x1800c7340`
- `0x1800eb920`
- `0x1802cf784`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c75c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c75c6`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800c7544`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800c7544`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800c7518`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800c7579`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800c7518`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800c7579`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800c749f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800c749f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800c74d0`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800c74d0`

## string_xrefs

- `0x1800c75e0`: `Failed to create session file`

## pseudocode

```c
__int64 __fastcall ValidateSessionFile(struct CCbsSession *a1, const wchar_t *a2, void **a3)
{
  unsigned int v5; // edi
  __int64 v6; // rdx
  unsigned int v8; // r14d
  HANDLE FileW; // rax
  HANDLE v10; // rdi
  BOOL v11; // ebx
  unsigned int v12; // ebx
  signed int LastError; // edi
  unsigned int v14; // eax
  int dwCreationDisposition; // [rsp+20h] [rbp-60h]
  unsigned int dwCreationDispositiona; // [rsp+20h] [rbp-60h]
  HANDLE hFile; // [rsp+40h] [rbp-40h] BYREF
  unsigned int v18[2]; // [rsp+48h] [rbp-38h] BYREF
  int v19; // [rsp+50h] [rbp-30h] BYREF
  DWORD NumberOfBytesRead; // [rsp+54h] [rbp-2Ch] BYREF
  _OWORD Buffer[2]; // [rsp+58h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  if ( !a2 )
  {
    v5 = -2147024809;
    v19 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No session file specified");
      hFile = &v19;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&hFile);
    }
    v6 = 7001;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\base\\cbs\\core\\packagestore.cpp",
      (const char *)v5,
      dwCreationDisposition);
    return v5;
  }
  if ( !a3 )
  {
    v5 = -2147467261;
    v19 = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No handle result specified");
      hFile = &v19;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&hFile);
    }
    v6 = 7002;
    goto LABEL_5;
  }
  NumberOfBytesRead = 0;
  v8 = 0;
  hFile = (HANDLE)-1LL;
  *a3 = 0;
  memset(Buffer, 0, sizeof(Buffer));
  if ( (unsigned int)DoesFileExist(a2, 0) )
  {
    do
    {
      FileW = CreateFileW(a2, 0xC0000000, 0, 0, 3u, 0x2000080u, 0);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &hFile,
        FileW);
      v10 = hFile;
      if ( hFile == (HANDLE)-1LL || !hFile )
      {
        Sleep(0x3E8u);
        ++v8;
        if ( v10 == (HANDLE)-1LL || !v10 )
          continue;
      }
      v11 = SetFilePointer(v10, -11, 0, 2u) == -1;
      if ( !ReadFile(v10, Buffer, 0xBu, &NumberOfBytesRead, 0) )
        v11 = 1;
      if ( !strcmp_0((const char *)Buffer, "</Sessions>") && !v11 )
      {
        SetFilePointer(v10, -11, 0, 2u);
        hFile = (HANDLE)-1LL;
        *a3 = v10;
      }
      goto LABEL_22;
    }
    while ( v8 < 3 );
    LastError = GetLastError();
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to create session file");
      if ( LastError > 0 )
        v14 = (unsigned __int16)LastError | 0x80070000;
      else
        v14 = LastError;
      v19 = v14;
      *(_QWORD *)v18 = &v19;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {0}",
        (__int64)v18);
    }
    if ( LastError )
    {
      v12 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x1B7D,
              (unsigned int)"onecore\\base\\cbs\\core\\packagestore.cpp",
              (const char *)(unsigned int)LastError,
              dwCreationDispositiona);
      goto LABEL_23;
    }
  }
LABEL_22:
  v12 = 0;
LABEL_23:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
  return v12;
}

```

## disassembly

```asm
0x1800c7340  mov     [rsp-28h+arg_0], rbx
0x1800c7345  mov     [rsp-28h+arg_18], rsi
0x1800c734a  push    rbp
0x1800c734b  push    rdi
0x1800c734c  push    r12
0x1800c734e  push    r14
0x1800c7350  push    r15
0x1800c7352  mov     rbp, rsp
0x1800c7355  sub     rsp, 80h
0x1800c735c  mov     rax, cs:__security_cookie
0x1800c7363  xor     rax, rsp
0x1800c7366  mov     [rbp+var_8], rax
0x1800c736a  mov     r15, r8
0x1800c736d  mov     r12, rdx
0x1800c7370  test    rdx, rdx
0x1800c7373  jnz     short loc_1800C73E4
0x1800c7375  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800c737c  mov     edi, 80070057h
0x1800c7381  mov     [rbp+var_30], edi
0x1800c7384  test    rcx, rcx
0x1800c7387  jz      short loc_1800C73C5
0x1800c7389  lea     ebx, [rdx+3]
0x1800c738c  mov     r8d, ebx
0x1800c738f  lea     r9, aNoSessionFileS; "No session file specified"
0x1800c7396  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800c739b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800c73a2  lea     rax, [rbp+var_30]
0x1800c73a6  mov     [rbp+hFile], rax
0x1800c73aa  lea     r9, asc_1802EE7AC; ": {}"
0x1800c73b1  lea     rax, [rbp+hFile]
0x1800c73b5  mov     r8d, ebx
0x1800c73b8  lea     edx, [rbx-2]
0x1800c73bb  mov     qword ptr [rsp+80h+dwCreationDisposition], rax; int
0x1800c73c0  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800c73c5  mov     edx, 1B59h; void *
0x1800c73ca  mov     rcx, [rbp+28h]; this
0x1800c73ce  lea     r8, aOnecoreBaseCbs_18; "onecore\\base\\cbs\\core\\packagestore."...
0x1800c73d5  mov     r9d, edi; char *
0x1800c73d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c73dd  mov     eax, edi
0x1800c73df  jmp     loc_1800C759D
0x1800c73e4  test    r15, r15
0x1800c73e7  jnz     short loc_1800C7443
0x1800c73e9  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800c73f0  mov     edi, 80004003h
0x1800c73f5  mov     [rbp+var_30], edi
0x1800c73f8  test    rcx, rcx
0x1800c73fb  jz      short loc_1800C743C
0x1800c73fd  lea     ebx, [r15+3]
0x1800c7401  xor     edx, edx
0x1800c7403  mov     r8d, ebx
0x1800c7406  lea     r9, aNoHandleResult; "No handle result specified"
0x1800c740d  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800c7412  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800c7419  lea     rax, [rbp+var_30]
0x1800c741d  mov     [rbp+hFile], rax
0x1800c7421  lea     r9, asc_1802EE7AC; ": {}"
0x1800c7428  lea     rax, [rbp+hFile]
0x1800c742c  mov     r8d, ebx
0x1800c742f  lea     edx, [rbx-2]
0x1800c7432  mov     qword ptr [rsp+80h+dwCreationDisposition], rax
0x1800c7437  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800c743c  mov     edx, 1B5Ah
0x1800c7441  jmp     short loc_1800C73CA
0x1800c7443  xorps   xmm0, xmm0
0x1800c7446  mov     [rbp+NumberOfBytesRead], 0
0x1800c744d  xor     r14d, r14d
0x1800c7450  mov     [rbp+hFile], 0FFFFFFFFFFFFFFFFh
0x1800c7458  xor     edx, edx
0x1800c745a  mov     [r8], r14
0x1800c745d  mov     rcx, r12
0x1800c7460  movups  [rbp+Buffer], xmm0
0x1800c7464  movups  [rbp+var_18], xmm0
0x1800c7468  call    DoesFileExist
0x1800c746d  test    eax, eax
0x1800c746f  jz      loc_1800C7590
0x1800c7475  lea     ebx, [r14+3]
0x1800c7479  lea     esi, [rbx-2]
0x1800c747c  mov     [rsp+80h+hTemplateFile], 0; hTemplateFile
0x1800c7485  xor     r9d, r9d; lpSecurityAttributes
0x1800c7488  mov     [rsp+80h+dwFlagsAndAttributes], 2000080h; dwFlagsAndAttributes
0x1800c7490  xor     r8d, r8d; dwShareMode
0x1800c7493  mov     edx, 0C0000000h; dwDesiredAccess
0x1800c7498  mov     [rsp+80h+dwCreationDisposition], ebx; dwCreationDisposition
0x1800c749c  mov     rcx, r12; lpFileName
0x1800c749f  call    cs:__imp_CreateFileW
0x1800c74a6  nop     dword ptr [rax+rax+00h]
0x1800c74ab  mov     rdx, rax
0x1800c74ae  lea     rcx, [rbp+hFile]
0x1800c74b2  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800c74b7  mov     rdi, [rbp+hFile]
0x1800c74bb  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800c74bf  jz      short loc_1800C74CB
0x1800c74c1  test    rdi, rdi
0x1800c74c4  jnz     short loc_1800C7502
0x1800c74c6  cmp     r14d, ebx
0x1800c74c9  jnb     short loc_1800C74EF
0x1800c74cb  mov     ecx, 3E8h; dwMilliseconds
0x1800c74d0  call    cs:__imp_Sleep
0x1800c74d7  nop     dword ptr [rax+rax+00h]
0x1800c74dc  add     r14d, esi
0x1800c74df  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800c74e3  jz      short loc_1800C74EA
0x1800c74e5  test    rdi, rdi
0x1800c74e8  jnz     short loc_1800C7502
0x1800c74ea  cmp     r14d, ebx
0x1800c74ed  jb      short loc_1800C747C
0x1800c74ef  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800c74f3  jz      loc_1800C75C6
0x1800c74f9  test    rdi, rdi
0x1800c74fc  jz      loc_1800C75C6
0x1800c7502  mov     r14d, 2
0x1800c7508  xor     r8d, r8d; lpDistanceToMoveHigh
0x1800c750b  mov     r9d, r14d; dwMoveMethod
0x1800c750e  mov     rcx, rdi; hFile
0x1800c7511  lea     r12d, [r14-0Dh]
0x1800c7515  mov     edx, r12d; lDistanceToMove
0x1800c7518  call    cs:__imp_SetFilePointer
0x1800c751f  nop     dword ptr [rax+rax+00h]
0x1800c7524  xor     ebx, ebx
0x1800c7526  mov     qword ptr [rsp+80h+dwCreationDisposition], 0; lpOverlapped
0x1800c752f  cmp     eax, 0FFFFFFFFh
0x1800c7532  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800c7536  lea     r8d, [r14+9]; nNumberOfBytesToRead
0x1800c753a  mov     rcx, rdi; hFile
0x1800c753d  lea     rdx, [rbp+Buffer]; lpBuffer
0x1800c7541  setz    bl
0x1800c7544  call    cs:__imp_ReadFile
0x1800c754b  nop     dword ptr [rax+rax+00h]
0x1800c7550  test    eax, eax
0x1800c7552  lea     rdx, aSessions_2; "</Sessions>"
0x1800c7559  lea     rcx, [rbp+Buffer]; Str1
0x1800c755d  cmovz   ebx, esi
0x1800c7560  call    strcmp_0
0x1800c7565  test    eax, eax
0x1800c7567  jnz     short loc_1800C7590
0x1800c7569  test    ebx, ebx
0x1800c756b  jnz     short loc_1800C7590
0x1800c756d  mov     r9d, r14d; dwMoveMethod
0x1800c7570  xor     r8d, r8d; lpDistanceToMoveHigh
0x1800c7573  mov     edx, r12d; lDistanceToMove
0x1800c7576  mov     rcx, rdi; hFile
0x1800c7579  call    cs:__imp_SetFilePointer
0x1800c7580  nop     dword ptr [rax+rax+00h]
0x1800c7585  mov     [rbp+hFile], 0FFFFFFFFFFFFFFFFh
0x1800c758d  mov     [r15], rdi
0x1800c7590  xor     ebx, ebx
0x1800c7592  lea     rcx, [rbp+hFile]
0x1800c7596  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800c759b  mov     eax, ebx
0x1800c759d  mov     rcx, [rbp+var_8]
0x1800c75a1  xor     rcx, rsp; StackCookie
0x1800c75a4  call    __security_check_cookie
0x1800c75a9  lea     r11, [rsp+80h+var_s0]
0x1800c75b1  mov     rbx, [r11+30h]
0x1800c75b5  mov     rsi, [r11+48h]
0x1800c75b9  mov     rsp, r11
0x1800c75bc  pop     r15
0x1800c75be  pop     r14
0x1800c75c0  pop     r12
0x1800c75c2  pop     rdi
0x1800c75c3  pop     rbp
0x1800c75c4  retn
0x1800c75c6  call    cs:__imp_GetLastError
0x1800c75cd  nop     dword ptr [rax+rax+00h]
0x1800c75d2  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800c75d9  mov     edi, eax
0x1800c75db  test    rcx, rcx
0x1800c75de  jz      short loc_1800C762E
0x1800c75e0  lea     r9, aFailedToCreate_26; "Failed to create session file"
0x1800c75e7  mov     r8d, ebx
0x1800c75ea  xor     edx, edx
0x1800c75ec  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800c75f1  test    edi, edi
0x1800c75f3  jg      short loc_1800C75F9
0x1800c75f5  mov     eax, edi
0x1800c75f7  jmp     short loc_1800C7601
0x1800c75f9  movzx   eax, di
0x1800c75fc  or      eax, 80070000h
0x1800c7601  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800c7608  lea     r9, a0; ": {0}"
0x1800c760f  mov     [rbp+var_30], eax
0x1800c7612  mov     r8d, ebx
0x1800c7615  lea     rax, [rbp+var_30]
0x1800c7619  mov     dl, sil
0x1800c761c  mov     qword ptr [rbp+var_38], rax
0x1800c7620  lea     rax, [rbp+var_38]
0x1800c7624  mov     qword ptr [rsp+80h+dwCreationDisposition], rax; unsigned int
0x1800c7629  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800c762e  test    edi, edi
0x1800c7630  jz      loc_1800C7590
0x1800c7636  mov     rcx, [rbp+28h]; this
0x1800c763a  lea     r8, aOnecoreBaseCbs_18; "onecore\\base\\cbs\\core\\packagestore."...
0x1800c7641  mov     r9d, edi; char *
0x1800c7644  mov     edx, 1B7Dh; void *
0x1800c7649  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800c764e  mov     ebx, eax
0x1800c7650  jmp     loc_1800C7592
```
