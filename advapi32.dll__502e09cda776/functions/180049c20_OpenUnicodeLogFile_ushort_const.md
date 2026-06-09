# OpenUnicodeLogFile(ushort const *)

- ea: `0x180049c20`
- end: `0x180049d08`
- name: `?OpenUnicodeLogFile@@YAPEAXPEBG@Z`
- size: `232`
- prototype: `void *__fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180049e60`

## callees

- `0x180049c20`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180049c70`
- `KERNEL32!GetLastError` at `0x180049c70`
- `KERNEL32!CloseHandle` at `0x180049ced`
- `KERNEL32!CloseHandle` at `0x180049ced`
- `KERNEL32!WriteFile` at `0x180049cda`
- `KERNEL32!WriteFile` at `0x180049cda`
- `KERNEL32!CreateFileW` at `0x180049c57`
- `KERNEL32!CreateFileW` at `0x180049ca7`
- `KERNEL32!CreateFileW` at `0x180049c57`
- `KERNEL32!CreateFileW` at `0x180049ca7`

## pseudocode

```c
HANDLE __fastcall OpenUnicodeLogFile(LPCWSTR lpFileName)
{
  HANDLE FileW; // rbx
  HANDLE v3; // rax
  DWORD NumberOfBytesWritten; // [rsp+58h] [rbp+10h] BYREF

  NumberOfBytesWritten = 0;
  FileW = CreateFileW(lpFileName, 6u, 1u, 0, 3u, 0x80u, 0);
  if ( FileW == (HANDLE)-1LL && GetLastError() == 2 )
  {
    v3 = CreateFileW(lpFileName, 6u, 1u, 0, 4u, 0x80u, 0);
    FileW = v3;
    if ( v3 != (HANDLE)-1LL && !WriteFile(v3, &qword_18008CF88, 8u, &NumberOfBytesWritten, 0) )
      CloseHandle(FileW);
  }
  return FileW;
}

```

## disassembly

```asm
0x180049c20  mov     rax, rsp
0x180049c23  mov     [rax+8], rbx
0x180049c27  push    rdi
0x180049c28  sub     rsp, 40h
0x180049c2c  xor     r9d, r9d; lpSecurityAttributes
0x180049c2f  mov     qword ptr [rax-18h], 0
0x180049c37  mov     dword ptr [rax-20h], 80h
0x180049c3e  mov     rdi, rcx
0x180049c41  mov     dword ptr [rax+10h], 0
0x180049c48  mov     dword ptr [rax-28h], 3
0x180049c4f  lea     edx, [r9+6]; dwDesiredAccess
0x180049c53  lea     r8d, [r9+1]; dwShareMode
0x180049c57  call    cs:__imp_CreateFileW
0x180049c5e  nop     dword ptr [rax+rax+00h]
0x180049c63  mov     rbx, rax
0x180049c66  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180049c6a  jnz     loc_180049CF9
0x180049c70  call    cs:__imp_GetLastError
0x180049c77  nop     dword ptr [rax+rax+00h]
0x180049c7c  cmp     eax, 2
0x180049c7f  jnz     short loc_180049CF9
0x180049c81  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x180049c8a  lea     edx, [rbx+7]; dwDesiredAccess
0x180049c8d  mov     [rsp+48h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180049c95  lea     r8d, [rbx+2]; dwShareMode
0x180049c99  xor     r9d, r9d; lpSecurityAttributes
0x180049c9c  mov     [rsp+48h+dwCreationDisposition], 4; dwCreationDisposition
0x180049ca4  mov     rcx, rdi; lpFileName
0x180049ca7  call    cs:__imp_CreateFileW
0x180049cae  nop     dword ptr [rax+rax+00h]
0x180049cb3  mov     rbx, rax
0x180049cb6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180049cba  jz      short loc_180049CF9
0x180049cbc  lea     r9, [rsp+48h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180049cc1  mov     qword ptr [rsp+48h+dwCreationDisposition], 0; lpOverlapped
0x180049cca  mov     r8d, 8; nNumberOfBytesToWrite
0x180049cd0  lea     rdx, qword_18008CF88; lpBuffer
0x180049cd7  mov     rcx, rax; hFile
0x180049cda  call    cs:__imp_WriteFile
0x180049ce1  nop     dword ptr [rax+rax+00h]
0x180049ce6  test    eax, eax
0x180049ce8  jnz     short loc_180049CF9
0x180049cea  mov     rcx, rbx; hObject
0x180049ced  call    cs:__imp_CloseHandle
0x180049cf4  nop     dword ptr [rax+rax+00h]
0x180049cf9  mov     rax, rbx
0x180049cfc  mov     rbx, [rsp+48h+arg_0]
0x180049d01  add     rsp, 40h
0x180049d05  pop     rdi
0x180049d06  retn
```
