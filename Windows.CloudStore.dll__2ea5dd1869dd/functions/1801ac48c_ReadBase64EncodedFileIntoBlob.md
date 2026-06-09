# ReadBase64EncodedFileIntoBlob

- ea: `0x1801ac48c`
- end: `0x1801ac68d`
- name: `ReadBase64EncodedFileIntoBlob`
- size: `513`
- prototype: `void *__fastcall(void *, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config`

## callers

- `0x1800d56f8`

## callees

- `0x180016cf4`
- `0x180019720`
- `0x1800219e0`
- `0x1800320d4`
- `0x180052730`
- `0x18009dd74`
- `0x1800febe4`
- `0x1801201a0`
- `0x180120c94`
- `0x180178038`
- `0x1801ac48c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801ac4ee`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801ac4ee`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1801ac534`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1801ac534`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1801ac5eb`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1801ac5eb`

## string_xrefs

- `0x1801ac50f`: `onecoreuap\shell\cloudstore\store\cache\src\cloudcacheearlydownloadinit.cpp`
- `0x1801ac53e`: `onecoreuap\shell\cloudstore\store\cache\src\cloudcacheearlydownloadinit.cpp`
- `0x1801ac570`: `onecoreuap\shell\cloudstore\store\cache\src\cloudcacheearlydownloadinit.cpp`
- `0x1801ac596`: `onecoreuap\shell\cloudstore\store\cache\src\cloudcacheearlydownloadinit.cpp`
- `0x1801ac5f5`: `onecoreuap\shell\cloudstore\store\cache\src\cloudcacheearlydownloadinit.cpp`
- `0x1801ac61e`: `onecoreuap\shell\cloudstore\store\cache\src\cloudcacheearlydownloadinit.cpp`

## pseudocode

```c
void *__fastcall ReadBase64EncodedFileIntoBlob(void *a1, __int64 a2)
{
  const WCHAR *v2; // rax
  HANDLE FileW; // rdi
  const char *v5; // r9
  const char *v6; // r9
  DWORD LowPart; // ebx
  DWORD v8; // esi
  size_t v9; // r8
  void *v10; // rsi
  const char *v11; // r9
  int dwCreationDisposition; // [rsp+20h] [rbp-39h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-39h]
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-19h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+48h] [rbp-11h] BYREF
  void *lpBuffer; // [rsp+50h] [rbp-9h] BYREF
  HANDLE v18[2]; // [rsp+58h] [rbp-1h] BYREF
  _BYTE v19[32]; // [rsp+68h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  v2 = (const WCHAR *)a2;
  v18[0] = a1;
  if ( *(_QWORD *)(a2 + 24) > 7u )
    v2 = *(const WCHAR **)a2;
  FileW = CreateFileW(v2, 0x80000000, 1u, 0, 3u, 0, 0);
  v18[0] = FileW;
  if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x8B,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\cloudcacheearlydownloadinit.cpp",
      v5);
  FileSize.QuadPart = 0;
  if ( !GetFileSizeEx(FileW, &FileSize) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x8E,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\cloudcacheearlydownloadinit.cpp",
      v6);
  LowPart = FileSize.LowPart;
  if ( FileSize.QuadPart > 0xFFFFFFFFLL )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x91,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\cloudcacheearlydownloadinit.cpp",
      (const char *)0x800700DFLL,
      dwCreationDisposition);
  if ( FileSize.QuadPart < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x92,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\cloudcacheearlydownloadinit.cpp",
      (const char *)0x80070570LL,
      dwCreationDisposition);
  v8 = FileSize.LowPart + 1;
  std::make_unique<char [0],0>(&lpBuffer, FileSize.LowPart + 1);
  v9 = v8;
  v10 = lpBuffer;
  memset_0(lpBuffer, 0, v9);
  NumberOfBytesRead = 0;
  if ( !ReadFile(FileW, v10, LowPart, &NumberOfBytesRead, 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x9D,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\cloudcacheearlydownloadinit.cpp",
      v11);
  if ( NumberOfBytesRead != LowPart )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x9F,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\cloudcacheearlydownloadinit.cpp",
      (const char *)0x8000FFFFLL,
      dwCreationDispositiona);
  std::string::string(v19, (const char *)v10);
  Base64Decode(a1, v19);
  std::string::_Tidy_deallocate(v19);
  std::unique_ptr<unsigned char [0]>::~unique_ptr<unsigned char [0]>(&lpBuffer);
  std::pair<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,bool>::~pair<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,bool>(v18);
  return a1;
}

```

## disassembly

```asm
0x1801ac48c  mov     [rsp-8+arg_10], rbx
0x1801ac491  push    rbp
0x1801ac492  push    rsi
0x1801ac493  push    rdi
0x1801ac494  push    r14
0x1801ac496  push    r15
0x1801ac498  lea     rbp, [rsp-37h]
0x1801ac49d  sub     rsp, 90h
0x1801ac4a4  mov     rax, cs:__security_cookie
0x1801ac4ab  xor     rax, rsp
0x1801ac4ae  mov     [rbp+57h+var_28], rax
0x1801ac4b2  mov     rax, rdx
0x1801ac4b5  mov     r14, rcx
0x1801ac4b8  mov     [rbp+57h+var_58], rcx
0x1801ac4bc  cmp     qword ptr [rdx+18h], 7
0x1801ac4c1  jbe     short loc_1801AC4C6
0x1801ac4c3  mov     rax, [rdx]
0x1801ac4c6  mov     [rsp+0B0h+hTemplateFile], 0; hTemplateFile
0x1801ac4cf  mov     [rsp+0B0h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x1801ac4d7  mov     [rsp+0B0h+dwCreationDisposition], 3; int
0x1801ac4df  xor     r9d, r9d; lpSecurityAttributes
0x1801ac4e2  mov     edx, 80000000h; dwDesiredAccess
0x1801ac4e7  lea     r8d, [r9+1]; dwShareMode
0x1801ac4eb  mov     rcx, rax; lpFileName
0x1801ac4ee  call    cs:__imp_CreateFileW
0x1801ac4f4  mov     rdi, rax
0x1801ac4f7  mov     [rbp+57h+var_58], rax
0x1801ac4fb  inc     rax
0x1801ac4fe  test    rax, 0FFFFFFFFFFFFFFFEh
0x1801ac504  setz    al
0x1801ac507  mov     rcx, [rbp+5Fh]; this
0x1801ac50b  test    al, al
0x1801ac50d  jz      short loc_1801AC521
0x1801ac50f  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x1801ac516  mov     edx, 8Bh; void *
0x1801ac51b  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1801ac521  mov     qword ptr [rbp+57h+FileSize], 0
0x1801ac529  mov     rbx, [rbp+5Fh]
0x1801ac52d  lea     rdx, [rbp+57h+FileSize]; lpFileSize
0x1801ac531  mov     rcx, rdi; hFile
0x1801ac534  call    cs:__imp_GetFileSizeEx
0x1801ac53a  test    eax, eax
0x1801ac53c  jnz     short loc_1801AC553
0x1801ac53e  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x1801ac545  mov     edx, 8Eh; void *
0x1801ac54a  mov     rcx, rbx; this
0x1801ac54d  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1801ac553  mov     eax, 0FFFFFFFFh
0x1801ac558  mov     rbx, qword ptr [rbp+57h+FileSize]
0x1801ac55c  cmp     rbx, rax
0x1801ac55f  setnle  al
0x1801ac562  mov     rcx, [rbp+5Fh]; this
0x1801ac566  test    al, al
0x1801ac568  jz      short loc_1801AC582
0x1801ac56a  mov     r9d, 800700DFh; char *
0x1801ac570  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x1801ac577  mov     edx, 91h; void *
0x1801ac57c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801ac582  test    rbx, rbx
0x1801ac585  sets    al
0x1801ac588  mov     rcx, [rbp+5Fh]; this
0x1801ac58c  test    al, al
0x1801ac58e  jz      short loc_1801AC5A8
0x1801ac590  mov     r9d, 80070570h; char *
0x1801ac596  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x1801ac59d  mov     edx, 92h; void *
0x1801ac5a2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801ac5a8  lea     eax, [rbx+1]
0x1801ac5ab  mov     esi, eax
0x1801ac5ad  mov     edx, eax
0x1801ac5af  lea     rcx, [rbp+57h+lpBuffer]
0x1801ac5b3  call    ??$make_unique@$$BY0A@D$0A@@std@@YA?AV?$unique_ptr@$$BY0A@DU?$default_delete@$$BY0A@D@std@@@0@_K@Z; std::make_unique<char [0],0>(unsigned __int64)
0x1801ac5b8  nop
0x1801ac5b9  mov     r8d, esi; Size
0x1801ac5bc  xor     edx, edx; Val
0x1801ac5be  mov     rsi, [rbp+57h+lpBuffer]
0x1801ac5c2  mov     rcx, rsi; void *
0x1801ac5c5  call    memset_0
0x1801ac5ca  mov     [rbp+57h+NumberOfBytesRead], 0
0x1801ac5d1  mov     r15, [rbp+5Fh]
0x1801ac5d5  mov     qword ptr [rsp+0B0h+dwCreationDisposition], 0; int
0x1801ac5de  lea     r9, [rbp+57h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1801ac5e2  mov     r8d, ebx; nNumberOfBytesToRead
0x1801ac5e5  mov     rdx, rsi; lpBuffer
0x1801ac5e8  mov     rcx, rdi; hFile
0x1801ac5eb  call    cs:__imp_ReadFile
0x1801ac5f1  test    eax, eax
0x1801ac5f3  jnz     short loc_1801AC60A
0x1801ac5f5  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x1801ac5fc  mov     edx, 9Dh; void *
0x1801ac601  mov     rcx, r15; this
0x1801ac604  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1801ac60a  cmp     [rbp+57h+NumberOfBytesRead], ebx
0x1801ac60d  setnz   al
0x1801ac610  mov     rcx, [rbp+5Fh]; this
0x1801ac614  test    al, al
0x1801ac616  jz      short loc_1801AC630
0x1801ac618  mov     r9d, 8000FFFFh; char *
0x1801ac61e  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x1801ac625  mov     edx, 9Fh; void *
0x1801ac62a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801ac630  mov     rdx, rsi
0x1801ac633  lea     rcx, [rbp+57h+var_48]
0x1801ac637  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1801ac63c  nop
0x1801ac63d  lea     rdx, [rbp+57h+var_48]
0x1801ac641  mov     rcx, r14
0x1801ac644  call    ?Base64Decode@@YA?AVblob@bond@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Base64Decode(std::string const &)
0x1801ac649  nop
0x1801ac64a  lea     rcx, [rbp+57h+var_48]; void *
0x1801ac64e  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1801ac653  nop
0x1801ac654  lea     rcx, [rbp+57h+lpBuffer]
0x1801ac658  call    ??1?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAA@XZ; std::unique_ptr<uchar [0]>::~unique_ptr<uchar [0]>(void)
0x1801ac65d  nop
0x1801ac65e  lea     rcx, [rbp+57h+var_58]
0x1801ac662  call    ??1?$pair@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@_N@std@@QEAA@XZ; std::pair<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,bool>::~pair<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,bool>(void)
0x1801ac667  mov     rax, r14
0x1801ac66a  mov     rcx, [rbp+57h+var_28]
0x1801ac66e  xor     rcx, rsp; StackCookie
0x1801ac671  call    __security_check_cookie
0x1801ac676  mov     rbx, [rsp+0B0h+arg_10]
0x1801ac67e  add     rsp, 90h
0x1801ac685  pop     r15
0x1801ac687  pop     r14
0x1801ac689  pop     rdi
0x1801ac68a  pop     rsi
0x1801ac68b  pop     rbp
0x1801ac68c  retn
```
