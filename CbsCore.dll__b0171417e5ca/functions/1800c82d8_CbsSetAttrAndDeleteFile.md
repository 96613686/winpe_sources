# CbsSetAttrAndDeleteFile

- ea: `0x1800c82d8`
- end: `0x1800c8544`
- name: `CbsSetAttrAndDeleteFile`
- size: `620`
- prototype: `__int64 __fastcall(LPCWSTR lpExistingFileName)`
- caller_count: `5`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x1800c7b40`
- `0x1800c9494`
- `0x1800cbe5c`
- `0x1800fb864`
- `0x1801829cc`

## callees

- `0x180013250`
- `0x180016d40`
- `0x180095e34`
- `0x180098538`
- `0x180099548`
- `0x18009cf78`
- `0x1800c82d8`
- `0x1800eb920`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c83e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c84a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c83e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c84a0`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800c83b6`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800c8481`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800c83b6`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800c8481`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800c8490`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800c8490`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800c83d2`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800c83d2`

## pseudocode

```c
__int64 __fastcall CbsSetAttrAndDeleteFile(LPCWSTR lpExistingFileName)
{
  unsigned int v2; // ebx
  int v3; // eax
  const WCHAR *v4; // rbx
  signed int LastError; // ebx
  unsigned int v6; // eax
  __int64 v7; // rdx
  unsigned int v8; // eax
  unsigned int v10; // [rsp+20h] [rbp-30h]
  LPCWSTR lpNewFileName; // [rsp+30h] [rbp-20h] BYREF
  unsigned int v12[2]; // [rsp+38h] [rbp-18h] BYREF
  int v13; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]

  if ( lpExistingFileName )
  {
    lpNewFileName = 0;
    v3 = SczAllocConcat2Sz(&lpNewFileName, lpExistingFileName, L"_tmp");
    v2 = v3;
    if ( v3 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x184,
        (unsigned int)"onecore\\base\\cbs\\util\\cbsfile2.cpp",
        (const char *)(unsigned int)v3,
        v10);
LABEL_25:
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpNewFileName);
      return v2;
    }
    SetFileAttributesW(lpExistingFileName, 0x80u);
    v4 = lpNewFileName;
    if ( MoveFileExW(lpExistingFileName, lpNewFileName, 8u) )
    {
      SetFileAttributesW(v4, 0x80u);
      if ( !DeleteFileW(v4) )
      {
        LastError = GetLastError();
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed deleting file");
          if ( LastError > 0 )
            v8 = (unsigned __int16)LastError | 0x80070000;
          else
            v8 = LastError;
          v13 = v8;
          *(_QWORD *)v12 = &v13;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {0}",
            (__int64)v12);
        }
        if ( LastError )
        {
          v7 = 396;
          goto LABEL_15;
        }
      }
    }
    else
    {
      LastError = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed renaming file name");
        if ( LastError > 0 )
          v6 = (unsigned __int16)LastError | 0x80070000;
        else
          v6 = LastError;
        v13 = v6;
        *(_QWORD *)v12 = &v13;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {0}",
          (__int64)v12);
      }
      if ( LastError )
      {
        v7 = 392;
LABEL_15:
        v2 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)v7,
               (unsigned int)"onecore\\base\\cbs\\util\\cbsfile2.cpp",
               (const char *)(unsigned int)LastError,
               v10);
        goto LABEL_25;
      }
    }
    v2 = 0;
    goto LABEL_25;
  }
  v2 = -2147024809;
  v13 = -2147024809;
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(
      (__int64)LogAdapter::g_Logger,
      0,
      3,
      (struct Windows::Rtl::IRtlFormattedOutputStream *)"No filename specified");
    lpNewFileName = (LPCWSTR)&v13;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (__int64)LogAdapter::g_Logger,
      1,
      3,
      (__int64)": {}",
      (__int64)&lpNewFileName);
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x181,
    (unsigned int)"onecore\\base\\cbs\\util\\cbsfile2.cpp",
    (const char *)0x80070057LL,
    v10);
  return v2;
}

```

## disassembly

```asm
0x1800c82d8  mov     [rsp-8+arg_8], rbx
0x1800c82dd  mov     [rsp-8+arg_10], rdi
0x1800c82e2  push    rbp
0x1800c82e3  mov     rbp, rsp
0x1800c82e6  sub     rsp, 50h
0x1800c82ea  mov     rax, cs:__security_cookie
0x1800c82f1  xor     rax, rsp
0x1800c82f4  mov     [rbp+var_8], rax
0x1800c82f8  mov     rdi, rcx
0x1800c82fb  test    rcx, rcx
0x1800c82fe  jnz     short loc_1800C8370
0x1800c8300  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800c8307  mov     ebx, 80070057h
0x1800c830c  mov     [rbp+var_10], ebx
0x1800c830f  test    rcx, rcx
0x1800c8312  jz      short loc_1800C8353
0x1800c8314  mov     edi, 3
0x1800c8319  lea     r9, aNoFilenameSpec; "No filename specified"
0x1800c8320  mov     r8d, edi
0x1800c8323  xor     edx, edx
0x1800c8325  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800c832a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800c8331  lea     rax, [rbp+var_10]
0x1800c8335  mov     [rbp+lpNewFileName], rax
0x1800c8339  lea     r9, asc_1802EE7AC; ": {}"
0x1800c8340  lea     rax, [rbp+lpNewFileName]
0x1800c8344  mov     r8d, edi
0x1800c8347  mov     dl, 1
0x1800c8349  mov     qword ptr [rsp+50h+var_30], rax; int
0x1800c834e  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800c8353  mov     rcx, [rbp+8]; this
0x1800c8357  lea     r8, aOnecoreBaseCbs_48; "onecore\\base\\cbs\\util\\cbsfile2.cpp"
0x1800c835e  mov     r9d, ebx; char *
0x1800c8361  mov     edx, 181h; void *
0x1800c8366  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c836b  jmp     loc_1800C8525
0x1800c8370  lea     r8, aTmp; "_tmp"
0x1800c8377  mov     [rbp+lpNewFileName], 0
0x1800c837f  mov     rdx, rdi
0x1800c8382  lea     rcx, [rbp+lpNewFileName]
0x1800c8386  call    SczAllocConcat2Sz
0x1800c838b  mov     ebx, eax
0x1800c838d  test    eax, eax
0x1800c838f  jns     short loc_1800C83AE
0x1800c8391  mov     rcx, [rbp+8]; this
0x1800c8395  lea     r8, aOnecoreBaseCbs_48; "onecore\\base\\cbs\\util\\cbsfile2.cpp"
0x1800c839c  mov     r9d, eax; char *
0x1800c839f  mov     edx, 184h; void *
0x1800c83a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c83a9  jmp     loc_1800C851C
0x1800c83ae  mov     edx, 80h; dwFileAttributes
0x1800c83b3  mov     rcx, rdi; lpFileName
0x1800c83b6  call    cs:__imp_SetFileAttributesW
0x1800c83bd  nop     dword ptr [rax+rax+00h]
0x1800c83c2  mov     rbx, [rbp+lpNewFileName]
0x1800c83c6  mov     r8d, 8; dwFlags
0x1800c83cc  mov     rdx, rbx; lpNewFileName
0x1800c83cf  mov     rcx, rdi; lpExistingFileName
0x1800c83d2  call    cs:__imp_MoveFileExW
0x1800c83d9  nop     dword ptr [rax+rax+00h]
0x1800c83de  test    eax, eax
0x1800c83e0  jnz     loc_1800C8479
0x1800c83e6  call    cs:__imp_GetLastError
0x1800c83ed  nop     dword ptr [rax+rax+00h]
0x1800c83f2  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800c83f9  mov     ebx, eax
0x1800c83fb  test    rcx, rcx
0x1800c83fe  jz      short loc_1800C8452
0x1800c8400  mov     edi, 3
0x1800c8405  lea     r9, aFailedRenaming; "Failed renaming file name"
0x1800c840c  mov     r8d, edi
0x1800c840f  xor     edx, edx
0x1800c8411  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800c8416  test    ebx, ebx
0x1800c8418  jg      short loc_1800C841E
0x1800c841a  mov     eax, ebx
0x1800c841c  jmp     short loc_1800C8426
0x1800c841e  movzx   eax, bx
0x1800c8421  or      eax, 80070000h
0x1800c8426  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800c842d  lea     r9, a0; ": {0}"
0x1800c8434  mov     [rbp+var_10], eax
0x1800c8437  mov     r8d, edi
0x1800c843a  lea     rax, [rbp+var_10]
0x1800c843e  mov     dl, 1
0x1800c8440  mov     qword ptr [rbp+var_18], rax
0x1800c8444  lea     rax, [rbp+var_18]
0x1800c8448  mov     qword ptr [rsp+50h+var_30], rax; unsigned int
0x1800c844d  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800c8452  test    ebx, ebx
0x1800c8454  jz      loc_1800C851A
0x1800c845a  mov     edx, 188h; void *
0x1800c845f  mov     rcx, [rbp+8]; this
0x1800c8463  lea     r8, aOnecoreBaseCbs_48; "onecore\\base\\cbs\\util\\cbsfile2.cpp"
0x1800c846a  mov     r9d, ebx; char *
0x1800c846d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800c8472  mov     ebx, eax
0x1800c8474  jmp     loc_1800C851C
0x1800c8479  mov     edx, 80h; dwFileAttributes
0x1800c847e  mov     rcx, rbx; lpFileName
0x1800c8481  call    cs:__imp_SetFileAttributesW
0x1800c8488  nop     dword ptr [rax+rax+00h]
0x1800c848d  mov     rcx, rbx; lpFileName
0x1800c8490  call    cs:__imp_DeleteFileW
0x1800c8497  nop     dword ptr [rax+rax+00h]
0x1800c849c  test    eax, eax
0x1800c849e  jnz     short loc_1800C851A
0x1800c84a0  call    cs:__imp_GetLastError
0x1800c84a7  nop     dword ptr [rax+rax+00h]
0x1800c84ac  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800c84b3  mov     ebx, eax
0x1800c84b5  test    rcx, rcx
0x1800c84b8  jz      short loc_1800C850C
0x1800c84ba  mov     edi, 3
0x1800c84bf  lea     r9, aFailedDeleting_6; "Failed deleting file"
0x1800c84c6  mov     r8d, edi
0x1800c84c9  xor     edx, edx
0x1800c84cb  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800c84d0  test    ebx, ebx
0x1800c84d2  jg      short loc_1800C84D8
0x1800c84d4  mov     eax, ebx
0x1800c84d6  jmp     short loc_1800C84E0
0x1800c84d8  movzx   eax, bx
0x1800c84db  or      eax, 80070000h
0x1800c84e0  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800c84e7  lea     r9, a0; ": {0}"
0x1800c84ee  mov     [rbp+var_10], eax
0x1800c84f1  mov     r8d, edi
0x1800c84f4  lea     rax, [rbp+var_10]
0x1800c84f8  mov     dl, 1
0x1800c84fa  mov     qword ptr [rbp+var_18], rax
0x1800c84fe  lea     rax, [rbp+var_18]
0x1800c8502  mov     qword ptr [rsp+50h+var_30], rax
0x1800c8507  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800c850c  test    ebx, ebx
0x1800c850e  jz      short loc_1800C851A
0x1800c8510  mov     edx, 18Ch
0x1800c8515  jmp     loc_1800C845F
0x1800c851a  xor     ebx, ebx
0x1800c851c  lea     rcx, [rbp+lpNewFileName]
0x1800c8520  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1800c8525  mov     eax, ebx
0x1800c8527  mov     rcx, [rbp+var_8]
0x1800c852b  xor     rcx, rsp; StackCookie
0x1800c852e  call    __security_check_cookie
0x1800c8533  mov     rbx, [rsp+50h+arg_8]
0x1800c8538  mov     rdi, [rsp+50h+arg_10]
0x1800c853d  add     rsp, 50h
0x1800c8541  pop     rbp
0x1800c8542  retn
```
