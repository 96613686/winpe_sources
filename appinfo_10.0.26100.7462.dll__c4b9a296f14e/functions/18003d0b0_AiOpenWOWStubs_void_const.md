# AiOpenWOWStubs(void * * const)

- ea: `0x18003d0b0`
- end: `0x18003d1e7`
- name: `?AiOpenWOWStubs@@YAXQEAPEAX@Z`
- size: `311`
- prototype: `void __fastcall(void **const)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, installer_update`

## callers

- `0x18000edf0`

## callees

- `0x1800449fa`
- `0x180044a20`

## import_xrefs

- `msvcrt!wcscat_s` at `0x18003d115`
- `msvcrt!wcscat_s` at `0x18003d181`
- `msvcrt!wcscat_s` at `0x18003d115`
- `msvcrt!wcscat_s` at `0x18003d181`
- `msvcrt!wcscpy_s` at `0x18003d0fa`
- `msvcrt!wcscpy_s` at `0x18003d166`
- `msvcrt!wcscpy_s` at `0x18003d0fa`
- `msvcrt!wcscpy_s` at `0x18003d166`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003d148`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003d1b4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003d148`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003d1b4`

## string_xrefs

- `0x18003d172`: `\InstallShield\setup.exe`

## pseudocode

```c
void __fastcall AiOpenWOWStubs(void **const a1)
{
  wchar_t Destination[264]; // [rsp+40h] [rbp-228h] BYREF

  memset_0(Destination, 0, 0x208u);
  wcscpy_s(Destination, 0x104u, g_wszWow64Dir);
  wcscat_s(Destination, 0x104u, L"\\setup16.exe");
  *a1 = CreateFileW(Destination, 0xA0000000, 5u, 0, 3u, 0x80u, 0);
  wcscpy_s(Destination, 0x104u, g_wszWow64Dir);
  wcscat_s(Destination, 0x104u, L"\\InstallShield\\setup.exe");
  a1[1] = CreateFileW(Destination, 0xA0000000, 5u, 0, 3u, 0x80u, 0);
}

```

## disassembly

```asm
0x18003d0b0  mov     [rsp+arg_8], rbx
0x18003d0b5  push    r15
0x18003d0b7  sub     rsp, 260h
0x18003d0be  mov     rax, cs:__security_cookie
0x18003d0c5  xor     rax, rsp
0x18003d0c8  mov     [rsp+268h+var_18], rax
0x18003d0d0  mov     rbx, rcx
0x18003d0d3  xor     edx, edx; Val
0x18003d0d5  lea     rcx, [rsp+268h+Destination]; void *
0x18003d0da  mov     r8d, 208h; Size
0x18003d0e0  call    memset_0
0x18003d0e5  mov     r15d, 104h
0x18003d0eb  lea     r8, ?g_wszWow64Dir@@3PAGA; Source
0x18003d0f2  mov     edx, r15d; SizeInWords
0x18003d0f5  lea     rcx, [rsp+268h+Destination]; Destination
0x18003d0fa  call    cs:__imp_wcscpy_s
0x18003d101  nop     dword ptr [rax+rax+00h]
0x18003d106  lea     r8, aSetup16Exe; "\\setup16.exe"
0x18003d10d  mov     edx, r15d; SizeInWords
0x18003d110  lea     rcx, [rsp+268h+Destination]; Destination
0x18003d115  call    cs:__imp_wcscat_s
0x18003d11c  nop     dword ptr [rax+rax+00h]
0x18003d121  and     [rsp+268h+var_238], 0
0x18003d127  lea     rcx, [rsp+268h+Destination]; lpFileName
0x18003d12c  xor     r9d, r9d; lpSecurityAttributes
0x18003d12f  mov     [rsp+268h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18003d137  mov     edx, 0A0000000h; dwDesiredAccess
0x18003d13c  mov     [rsp+268h+dwCreationDisposition], 3; dwCreationDisposition
0x18003d144  lea     r8d, [r9+5]; dwShareMode
0x18003d148  call    cs:__imp_CreateFileW
0x18003d14f  nop     dword ptr [rax+rax+00h]
0x18003d154  lea     r8, ?g_wszWow64Dir@@3PAGA; Source
0x18003d15b  mov     edx, r15d; SizeInWords
0x18003d15e  lea     rcx, [rsp+268h+Destination]; Destination
0x18003d163  mov     [rbx], rax
0x18003d166  call    cs:__imp_wcscpy_s
0x18003d16d  nop     dword ptr [rax+rax+00h]
0x18003d172  lea     r8, aInstallshieldS; "\\InstallShield\\setup.exe"
0x18003d179  mov     edx, r15d; SizeInWords
0x18003d17c  lea     rcx, [rsp+268h+Destination]; Destination
0x18003d181  call    cs:__imp_wcscat_s
0x18003d188  nop     dword ptr [rax+rax+00h]
0x18003d18d  and     [rsp+268h+var_238], 0
0x18003d193  lea     rcx, [rsp+268h+Destination]; lpFileName
0x18003d198  xor     r9d, r9d; lpSecurityAttributes
0x18003d19b  mov     [rsp+268h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18003d1a3  mov     edx, 0A0000000h; dwDesiredAccess
0x18003d1a8  mov     [rsp+268h+dwCreationDisposition], 3; dwCreationDisposition
0x18003d1b0  lea     r8d, [r9+5]; dwShareMode
0x18003d1b4  call    cs:__imp_CreateFileW
0x18003d1bb  nop     dword ptr [rax+rax+00h]
0x18003d1c0  mov     [rbx+8], rax
0x18003d1c4  mov     rcx, [rsp+268h+var_18]
0x18003d1cc  xor     rcx, rsp; StackCookie
0x18003d1cf  call    __security_check_cookie
0x18003d1d4  mov     rbx, [rsp+268h+arg_8]
0x18003d1dc  add     rsp, 260h
0x18003d1e3  pop     r15
0x18003d1e5  retn
```
