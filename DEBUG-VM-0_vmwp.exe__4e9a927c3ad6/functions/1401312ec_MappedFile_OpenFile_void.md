# MappedFile::OpenFile(void *)

- ea: `0x1401312ec`
- end: `0x140131413`
- name: `?OpenFile@MappedFile@@QEAAXPEAX@Z`
- size: `295`
- prototype: `void(MappedFile *__hidden this, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x140131238`

## callees

- `0x14005b628`
- `0x1400841e4`
- `0x1401312ec`
- `0x140132940`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x14013131c`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x14013131c`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1401313b7`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1401313b7`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x140131367`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x140131367`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1401313d0`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1401313d0`

## string_xrefs

- `0x140131331`: `onecore\vm\common\guestloader\inc\MappedFile.h`
- `0x140131392`: `onecore\vm\common\guestloader\inc\MappedFile.h`
- `0x1401313e8`: `onecore\vm\common\guestloader\inc\MappedFile.h`

## pseudocode

```c
void __fastcall MappedFile::OpenFile(union _LARGE_INTEGER *this, void *a2)
{
  const char *v4; // r9
  HANDLE FileMappingW; // rax
  const char *v6; // r9
  LPVOID v7; // rax
  const char *v8; // r9
  const void *QuadPart; // rcx
  union _LARGE_INTEGER FileSize; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  FileSize.QuadPart = 0;
  if ( !GetFileSizeEx(a2, &FileSize) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x35,
      (unsigned int)"onecore\\vm\\common\\guestloader\\inc\\MappedFile.h",
      v4);
  this[2] = FileSize;
  FileMappingW = CreateFileMappingW(a2, 0, 2u, 0, 0, 0);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    this,
    FileMappingW);
  if ( ((this->QuadPart + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x3F,
      (unsigned int)"onecore\\vm\\common\\guestloader\\inc\\MappedFile.h",
      v6);
  v7 = MapViewOfFile((HANDLE)this->QuadPart, 4u, 0, 0, 0);
  QuadPart = (const void *)this[1].QuadPart;
  this[1].QuadPart = (LONGLONG)v7;
  if ( QuadPart )
    UnmapViewOfFile(QuadPart);
  if ( !this[1].QuadPart )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x47,
      (unsigned int)"onecore\\vm\\common\\guestloader\\inc\\MappedFile.h",
      v8);
}

```

## disassembly

```asm
0x1401312ec  mov     [rsp+arg_10], rbx
0x1401312f1  push    rdi
0x1401312f2  sub     rsp, 40h
0x1401312f6  mov     rax, cs:__security_cookie
0x1401312fd  xor     rax, rsp
0x140131300  mov     [rsp+48h+var_10], rax
0x140131305  mov     rdi, rdx
0x140131308  mov     qword ptr [rsp+48h+FileSize], 0
0x140131311  mov     rbx, rcx
0x140131314  lea     rdx, [rsp+48h+FileSize]; lpFileSize
0x140131319  mov     rcx, rdi; hFile
0x14013131c  call    cs:__imp_GetFileSizeEx
0x140131323  nop     dword ptr [rax+rax+00h]
0x140131328  test    eax, eax
0x14013132a  jnz     short loc_140131341
0x14013132c  mov     rcx, [rsp+48h]; this
0x140131331  lea     r8, aOnecoreVmCommo_8; "onecore\\vm\\common\\guestloader\\inc\\"...
0x140131338  lea     edx, [rax+35h]; void *
0x14013133b  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140131341  mov     rax, qword ptr [rsp+48h+FileSize]
0x140131346  xor     r9d, r9d; dwMaximumSizeHigh
0x140131349  mov     [rsp+48h+lpName], 0; lpName
0x140131352  xor     edx, edx; lpFileMappingAttributes
0x140131354  mov     rcx, rdi; hFile
0x140131357  mov     [rbx+10h], rax
0x14013135b  mov     [rsp+48h+dwMaximumSizeLow], 0; dwMaximumSizeLow
0x140131363  lea     r8d, [r9+2]; flProtect
0x140131367  call    cs:__imp_CreateFileMappingW
0x14013136e  nop     dword ptr [rax+rax+00h]
0x140131373  mov     rdx, rax
0x140131376  mov     rcx, rbx
0x140131379  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x14013137e  mov     rcx, [rbx]; hFileMappingObject
0x140131381  lea     rax, [rcx+1]
0x140131385  test    rax, 0FFFFFFFFFFFFFFFEh
0x14013138b  jnz     short loc_1401313A4
0x14013138d  mov     rcx, [rsp+48h]; this
0x140131392  lea     r8, aOnecoreVmCommo_8; "onecore\\vm\\common\\guestloader\\inc\\"...
0x140131399  mov     edx, 3Fh ; '?'; void *
0x14013139e  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1401313a4  xor     r9d, r9d; dwFileOffsetLow
0x1401313a7  mov     qword ptr [rsp+48h+dwMaximumSizeLow], 0; dwNumberOfBytesToMap
0x1401313b0  xor     r8d, r8d; dwFileOffsetHigh
0x1401313b3  lea     edx, [r9+4]; dwDesiredAccess
0x1401313b7  call    cs:__imp_MapViewOfFile
0x1401313be  nop     dword ptr [rax+rax+00h]
0x1401313c3  mov     rcx, [rbx+8]; lpBaseAddress
0x1401313c7  mov     [rbx+8], rax
0x1401313cb  test    rcx, rcx
0x1401313ce  jz      short loc_1401313DC
0x1401313d0  call    cs:__imp_UnmapViewOfFile
0x1401313d7  nop     dword ptr [rax+rax+00h]
0x1401313dc  cmp     qword ptr [rbx+8], 0
0x1401313e1  jnz     short loc_1401313FA
0x1401313e3  mov     rcx, [rsp+48h]; this
0x1401313e8  lea     r8, aOnecoreVmCommo_8; "onecore\\vm\\common\\guestloader\\inc\\"...
0x1401313ef  mov     edx, 47h ; 'G'; void *
0x1401313f4  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1401313fa  mov     rcx, [rsp+48h+var_10]
0x1401313ff  xor     rcx, rsp; StackCookie
0x140131402  call    __security_check_cookie
0x140131407  mov     rbx, [rsp+48h+arg_10]
0x14013140c  add     rsp, 40h
0x140131410  pop     rdi
0x140131411  retn
```
