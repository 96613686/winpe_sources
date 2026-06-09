# AiOpenWOWStubs(void * * const)

- ea: `0x18003cb70`
- end: `0x18003cca7`
- name: `?AiOpenWOWStubs@@YAXQEAPEAX@Z`
- size: `311`
- prototype: `void __fastcall(void **const)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, installer_update`

## callers

- `0x18000edf0`

## callees

- `0x1800444ba`
- `0x1800444e0`

## import_xrefs

- `msvcrt!wcscat_s` at `0x18003cbd5`
- `msvcrt!wcscat_s` at `0x18003cc41`
- `msvcrt!wcscat_s` at `0x18003cbd5`
- `msvcrt!wcscat_s` at `0x18003cc41`
- `msvcrt!wcscpy_s` at `0x18003cbba`
- `msvcrt!wcscpy_s` at `0x18003cc26`
- `msvcrt!wcscpy_s` at `0x18003cbba`
- `msvcrt!wcscpy_s` at `0x18003cc26`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003cc08`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003cc74`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003cc08`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003cc74`

## string_xrefs

- `0x18003cc32`: `\InstallShield\setup.exe`

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
0x18003cb70  mov     [rsp+arg_8], rbx
0x18003cb75  push    r15
0x18003cb77  sub     rsp, 260h
0x18003cb7e  mov     rax, cs:__security_cookie
0x18003cb85  xor     rax, rsp
0x18003cb88  mov     [rsp+268h+var_18], rax
0x18003cb90  mov     rbx, rcx
0x18003cb93  xor     edx, edx; Val
0x18003cb95  lea     rcx, [rsp+268h+Destination]; void *
0x18003cb9a  mov     r8d, 208h; Size
0x18003cba0  call    memset_0
0x18003cba5  mov     r15d, 104h
0x18003cbab  lea     r8, ?g_wszWow64Dir@@3PAGA; Source
0x18003cbb2  mov     edx, r15d; SizeInWords
0x18003cbb5  lea     rcx, [rsp+268h+Destination]; Destination
0x18003cbba  call    cs:__imp_wcscpy_s
0x18003cbc1  nop     dword ptr [rax+rax+00h]
0x18003cbc6  lea     r8, aSetup16Exe; "\\setup16.exe"
0x18003cbcd  mov     edx, r15d; SizeInWords
0x18003cbd0  lea     rcx, [rsp+268h+Destination]; Destination
0x18003cbd5  call    cs:__imp_wcscat_s
0x18003cbdc  nop     dword ptr [rax+rax+00h]
0x18003cbe1  and     [rsp+268h+var_238], 0
0x18003cbe7  lea     rcx, [rsp+268h+Destination]; lpFileName
0x18003cbec  xor     r9d, r9d; lpSecurityAttributes
0x18003cbef  mov     [rsp+268h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18003cbf7  mov     edx, 0A0000000h; dwDesiredAccess
0x18003cbfc  mov     [rsp+268h+dwCreationDisposition], 3; dwCreationDisposition
0x18003cc04  lea     r8d, [r9+5]; dwShareMode
0x18003cc08  call    cs:__imp_CreateFileW
0x18003cc0f  nop     dword ptr [rax+rax+00h]
0x18003cc14  lea     r8, ?g_wszWow64Dir@@3PAGA; Source
0x18003cc1b  mov     edx, r15d; SizeInWords
0x18003cc1e  lea     rcx, [rsp+268h+Destination]; Destination
0x18003cc23  mov     [rbx], rax
0x18003cc26  call    cs:__imp_wcscpy_s
0x18003cc2d  nop     dword ptr [rax+rax+00h]
0x18003cc32  lea     r8, aInstallshieldS; "\\InstallShield\\setup.exe"
0x18003cc39  mov     edx, r15d; SizeInWords
0x18003cc3c  lea     rcx, [rsp+268h+Destination]; Destination
0x18003cc41  call    cs:__imp_wcscat_s
0x18003cc48  nop     dword ptr [rax+rax+00h]
0x18003cc4d  and     [rsp+268h+var_238], 0
0x18003cc53  lea     rcx, [rsp+268h+Destination]; lpFileName
0x18003cc58  xor     r9d, r9d; lpSecurityAttributes
0x18003cc5b  mov     [rsp+268h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18003cc63  mov     edx, 0A0000000h; dwDesiredAccess
0x18003cc68  mov     [rsp+268h+dwCreationDisposition], 3; dwCreationDisposition
0x18003cc70  lea     r8d, [r9+5]; dwShareMode
0x18003cc74  call    cs:__imp_CreateFileW
0x18003cc7b  nop     dword ptr [rax+rax+00h]
0x18003cc80  mov     [rbx+8], rax
0x18003cc84  mov     rcx, [rsp+268h+var_18]
0x18003cc8c  xor     rcx, rsp; StackCookie
0x18003cc8f  call    __security_check_cookie
0x18003cc94  mov     rbx, [rsp+268h+arg_8]
0x18003cc9c  add     rsp, 260h
0x18003cca3  pop     r15
0x18003cca5  retn
```
