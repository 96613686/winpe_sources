# PrintCore::IppPrinterAttributesCache::_FileToBuffer(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::vector<uchar,std::allocator<uchar>> &)

- ea: `0x1800403b4`
- end: `0x18004054e`
- name: `?_FileToBuffer@IppPrinterAttributesCache@PrintCore@@AEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$vector@EV?$allocator@E@std@@@4@@Z`
- size: `410`
- prototype: `__int64 __fastcall(__int64, __int64, LPVOID *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callers

- `0x18003b640`

## callees

- `0x18000495c`
- `0x180010aec`
- `0x180012784`
- `0x1800127a4`
- `0x1800166a8`
- `0x180023664`
- `0x180037038`
- `0x1800403b4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040417`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040417`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800403fe`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800403fe`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800404e8`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800404e8`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180040457`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180040457`

## string_xrefs

- `0x18004042e`: `OneCoreUap\Internal\Printscan\inc\ippprinterattributescache.hxx`
- `0x180040469`: `OneCoreUap\Internal\Printscan\inc\ippprinterattributescache.hxx`
- `0x1800404f7`: `OneCoreUap\Internal\Printscan\inc\ippprinterattributescache.hxx`
- `0x18004051d`: `OneCoreUap\Internal\Printscan\inc\ippprinterattributescache.hxx`

## pseudocode

```c
__int64 __fastcall PrintCore::IppPrinterAttributesCache::_FileToBuffer(__int64 a1, __int64 a2, LPVOID *a3)
{
  const WCHAR *v4; // rax
  HANDLE FileW; // rbx
  const char *v6; // r9
  unsigned int LastError; // ebx
  DWORD FileSize; // eax
  const char *v10; // r9
  DWORD v11; // ebp
  char *v12; // rdx
  char *v13; // r14
  unsigned __int64 v14; // rcx
  char *v15; // rax
  size_t v16; // rdi
  const char *v17; // r9
  int dwCreationDisposition; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  __int64 NumberOfBytesRead; // [rsp+60h] [rbp+8h] BYREF
  HANDLE v21; // [rsp+68h] [rbp+10h] BYREF

  NumberOfBytesRead = a1;
  v4 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
  FileW = CreateFileW(v4, 0x80000000, 1u, 0, 3u, 0x100000u, 0);
  v21 = FileW;
  if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    if ( GetLastError() == 2 )
      LastError = -2147024894;
    else
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x3D,
                    (unsigned int)"OneCoreUap\\Internal\\Printscan\\inc\\ippprinterattributescache.hxx",
                    v6);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v21);
    return LastError;
  }
  FileSize = GetFileSize(FileW, 0);
  v11 = FileSize;
  if ( FileSize == -1 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x40,
      (unsigned int)"OneCoreUap\\Internal\\Printscan\\inc\\ippprinterattributescache.hxx",
      v10);
  v12 = (char *)*a3;
  v13 = (char *)a3[1];
  v14 = v13 - (_BYTE *)*a3;
  if ( FileSize < v14 )
  {
    v15 = &v12[FileSize];
LABEL_14:
    a3[1] = v15;
    goto LABEL_15;
  }
  if ( FileSize > v14 )
  {
    if ( FileSize <= (unsigned __int64)((_BYTE *)a3[2] - v12) )
    {
      v16 = FileSize - v14;
      memset_0(a3[1], 0, v16);
      v15 = &v13[v16];
      goto LABEL_14;
    }
    std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(a3, FileSize);
  }
LABEL_15:
  LODWORD(NumberOfBytesRead) = 0;
  if ( !ReadFile(FileW, *a3, v11, (LPDWORD)&NumberOfBytesRead, 0) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x43,
      (unsigned int)"OneCoreUap\\Internal\\Printscan\\inc\\ippprinterattributescache.hxx",
      v17);
  if ( (_DWORD)NumberOfBytesRead != v11 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x44,
      (unsigned int)"OneCoreUap\\Internal\\Printscan\\inc\\ippprinterattributescache.hxx",
      (const char *)0x8000FFFFLL,
      dwCreationDisposition);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v21);
  return 0;
}

```

## disassembly

```asm
0x1800403b4  mov     [rsp+arg_10], rbx
0x1800403b9  mov     [rsp+arg_18], rbp
0x1800403be  mov     [rsp+NumberOfBytesRead], rcx
0x1800403c3  push    rsi
0x1800403c4  push    rdi
0x1800403c5  push    r14
0x1800403c7  sub     rsp, 40h
0x1800403cb  mov     rsi, r8
0x1800403ce  mov     rcx, rdx
0x1800403d1  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800403d6  mov     [rsp+58h+hTemplateFile], 0; hTemplateFile
0x1800403df  mov     [rsp+58h+dwFlagsAndAttributes], 100000h; dwFlagsAndAttributes
0x1800403e7  mov     [rsp+58h+dwCreationDisposition], 3; dwCreationDisposition
0x1800403ef  xor     r9d, r9d; lpSecurityAttributes
0x1800403f2  mov     edx, 80000000h; dwDesiredAccess
0x1800403f7  lea     r8d, [r9+1]; dwShareMode
0x1800403fb  mov     rcx, rax; lpFileName
0x1800403fe  call    cs:__imp_CreateFileW
0x180040404  mov     rbx, rax
0x180040407  mov     [rsp+58h+arg_8], rax
0x18004040c  inc     rax
0x18004040f  test    rax, 0FFFFFFFFFFFFFFFEh
0x180040415  jnz     short loc_180040452
0x180040417  call    cs:__imp_GetLastError
0x18004041d  cmp     eax, 2
0x180040420  jnz     short loc_180040429
0x180040422  mov     ebx, 80070002h
0x180040427  jmp     short loc_180040441
0x180040429  mov     rcx, [rsp+58h]; this
0x18004042e  lea     r8, aOnecoreuapInte_0; "OneCoreUap\\Internal\\Printscan\\inc\\i"...
0x180040435  mov     edx, 3Dh ; '='; void *
0x18004043a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004043f  mov     ebx, eax
0x180040441  lea     rcx, [rsp+58h+arg_8]
0x180040446  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18004044b  mov     eax, ebx
0x18004044d  jmp     loc_18004053B
0x180040452  xor     edx, edx; lpFileSizeHigh
0x180040454  mov     rcx, rbx; hFile
0x180040457  call    cs:__imp_GetFileSize
0x18004045d  mov     ebp, eax
0x18004045f  mov     rcx, [rsp+58h]; this
0x180040464  cmp     eax, 0FFFFFFFFh
0x180040467  jnz     short loc_18004047B
0x180040469  lea     r8, aOnecoreuapInte_0; "OneCoreUap\\Internal\\Printscan\\inc\\i"...
0x180040470  mov     edx, 40h ; '@'; void *
0x180040475  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18004047b  mov     rdx, [rsi]
0x18004047e  mov     r14, [rsi+8]
0x180040482  mov     rcx, r14
0x180040485  sub     rcx, rdx
0x180040488  mov     rdi, rbp
0x18004048b  cmp     rbp, rcx
0x18004048e  jnb     short loc_180040496
0x180040490  lea     rax, [rdx+rbp]
0x180040494  jmp     short loc_1800404C5
0x180040496  jbe     short loc_1800404C9
0x180040498  mov     rax, [rsi+10h]
0x18004049c  sub     rax, rdx
0x18004049f  cmp     rdi, rax
0x1800404a2  jbe     short loc_1800404B1
0x1800404a4  mov     rdx, rdi
0x1800404a7  mov     rcx, rsi
0x1800404aa  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1800404af  jmp     short loc_1800404C9
0x1800404b1  sub     rdi, rcx
0x1800404b4  mov     r8, rdi; Size
0x1800404b7  xor     edx, edx; Val
0x1800404b9  mov     rcx, r14; void *
0x1800404bc  call    memset_0
0x1800404c1  lea     rax, [rdi+r14]
0x1800404c5  mov     [rsi+8], rax
0x1800404c9  mov     dword ptr [rsp+58h+NumberOfBytesRead], 0
0x1800404d1  mov     qword ptr [rsp+58h+dwCreationDisposition], 0; int
0x1800404da  lea     r9, [rsp+58h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800404df  mov     r8d, ebp; nNumberOfBytesToRead
0x1800404e2  mov     rdx, [rsi]; lpBuffer
0x1800404e5  mov     rcx, rbx; hFile
0x1800404e8  call    cs:__imp_ReadFile
0x1800404ee  mov     rcx, [rsp+58h]; this
0x1800404f3  test    eax, eax
0x1800404f5  jnz     short loc_180040507
0x1800404f7  lea     r8, aOnecoreuapInte_0; "OneCoreUap\\Internal\\Printscan\\inc\\i"...
0x1800404fe  lea     edx, [rax+43h]; void *
0x180040501  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180040507  cmp     dword ptr [rsp+58h+NumberOfBytesRead], ebp
0x18004050b  setnz   al
0x18004050e  mov     rcx, [rsp+58h]; this
0x180040513  test    al, al
0x180040515  jz      short loc_18004052F
0x180040517  mov     r9d, 8000FFFFh; char *
0x18004051d  lea     r8, aOnecoreuapInte_0; "OneCoreUap\\Internal\\Printscan\\inc\\i"...
0x180040524  mov     edx, 44h ; 'D'; void *
0x180040529  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004052f  lea     rcx, [rsp+58h+arg_8]
0x180040534  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180040539  xor     eax, eax
0x18004053b  mov     rbx, [rsp+58h+arg_10]
0x180040540  mov     rbp, [rsp+58h+arg_18]
0x180040545  add     rsp, 40h
0x180040549  pop     r14
0x18004054b  pop     rdi
0x18004054c  pop     rsi
0x18004054d  retn
```
