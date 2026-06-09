# AiOpenWOWStubs(void * * const)

- ea: `0x18003f8e0`
- end: `0x18003f9f8`
- name: `?AiOpenWOWStubs@@YAXQEAPEAX@Z`
- size: `280`
- prototype: `void __fastcall(void **const)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, installer_update`

## callers

- `0x18000ed20`

## callees

- `0x180046e1a`
- `0x180046e50`

## import_xrefs

- `msvcrt!wcscat_s` at `0x18003f93f`
- `msvcrt!wcscat_s` at `0x18003f99c`
- `msvcrt!wcscat_s` at `0x18003f93f`
- `msvcrt!wcscat_s` at `0x18003f99c`
- `msvcrt!wcscpy_s` at `0x18003f92a`
- `msvcrt!wcscpy_s` at `0x18003f987`
- `msvcrt!wcscpy_s` at `0x18003f92a`
- `msvcrt!wcscpy_s` at `0x18003f987`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003f96f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003f9cc`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003f96f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003f9cc`

## string_xrefs

- `0x18003f98d`: `\InstallShield\setup.exe`

## pseudocode

```c
void __fastcall AiOpenWOWStubs(void **const a1)
{
  wchar_t Destination[264]; // [rsp+40h] [rbp-228h] BYREF

  memset_0(Destination, 0, 0x208u);
  wcscpy_s(Destination, 0x104u, &g_wszWow64Dir);
  wcscat_s(Destination, 0x104u, L"\\setup16.exe");
  *a1 = CreateFileW(Destination, 0xA0000000, 5u, 0, 3u, 0x80u, 0);
  wcscpy_s(Destination, 0x104u, &g_wszWow64Dir);
  wcscat_s(Destination, 0x104u, L"\\InstallShield\\setup.exe");
  a1[1] = CreateFileW(Destination, 0xA0000000, 5u, 0, 3u, 0x80u, 0);
}

```

## disassembly

```asm
0x18003f8e0  mov     [rsp+arg_8], rbx
0x18003f8e5  push    r15
0x18003f8e7  sub     rsp, 260h
0x18003f8ee  mov     rax, cs:__security_cookie
0x18003f8f5  xor     rax, rsp
0x18003f8f8  mov     [rsp+268h+var_18], rax
0x18003f900  mov     rbx, rcx
0x18003f903  xor     edx, edx; Val
0x18003f905  lea     rcx, [rsp+268h+Destination]; void *
0x18003f90a  mov     r8d, 208h; Size
0x18003f910  call    memset_0
0x18003f915  mov     r15d, 104h
0x18003f91b  lea     r8, ?g_wszWow64Dir@@3PAGA; Source
0x18003f922  mov     edx, r15d; SizeInWords
0x18003f925  lea     rcx, [rsp+268h+Destination]; Destination
0x18003f92a  call    cs:__imp_wcscpy_s
0x18003f930  lea     r8, aSetup16Exe; "\\setup16.exe"
0x18003f937  mov     edx, r15d; SizeInWords
0x18003f93a  lea     rcx, [rsp+268h+Destination]; Destination
0x18003f93f  call    cs:__imp_wcscat_s
0x18003f945  xor     r9d, r9d; lpSecurityAttributes
0x18003f948  mov     [rsp+268h+hTemplateFile], 0; hTemplateFile
0x18003f951  mov     [rsp+268h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18003f959  lea     rcx, [rsp+268h+Destination]; lpFileName
0x18003f95e  mov     edx, 0A0000000h; dwDesiredAccess
0x18003f963  mov     [rsp+268h+dwCreationDisposition], 3; dwCreationDisposition
0x18003f96b  lea     r8d, [r9+5]; dwShareMode
0x18003f96f  call    cs:__imp_CreateFileW
0x18003f975  lea     r8, ?g_wszWow64Dir@@3PAGA; Source
0x18003f97c  mov     edx, r15d; SizeInWords
0x18003f97f  lea     rcx, [rsp+268h+Destination]; Destination
0x18003f984  mov     [rbx], rax
0x18003f987  call    cs:__imp_wcscpy_s
0x18003f98d  lea     r8, aInstallshieldS; "\\InstallShield\\setup.exe"
0x18003f994  mov     edx, r15d; SizeInWords
0x18003f997  lea     rcx, [rsp+268h+Destination]; Destination
0x18003f99c  call    cs:__imp_wcscat_s
0x18003f9a2  xor     r9d, r9d; lpSecurityAttributes
0x18003f9a5  mov     [rsp+268h+hTemplateFile], 0; hTemplateFile
0x18003f9ae  mov     [rsp+268h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18003f9b6  lea     rcx, [rsp+268h+Destination]; lpFileName
0x18003f9bb  mov     edx, 0A0000000h; dwDesiredAccess
0x18003f9c0  mov     [rsp+268h+dwCreationDisposition], 3; dwCreationDisposition
0x18003f9c8  lea     r8d, [r9+5]; dwShareMode
0x18003f9cc  call    cs:__imp_CreateFileW
0x18003f9d2  mov     [rbx+8], rax
0x18003f9d6  mov     rcx, [rsp+268h+var_18]
0x18003f9de  xor     rcx, rsp; StackCookie
0x18003f9e1  call    __security_check_cookie
0x18003f9e6  mov     rbx, [rsp+268h+arg_8]
0x18003f9ee  add     rsp, 260h
0x18003f9f5  pop     r15
0x18003f9f7  retn
```
