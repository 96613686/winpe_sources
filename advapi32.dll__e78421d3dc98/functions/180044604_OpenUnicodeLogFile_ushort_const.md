# OpenUnicodeLogFile(ushort const *)

- ea: `0x180044604`
- end: `0x1800446c9`
- name: `?OpenUnicodeLogFile@@YAPEAXPEBG@Z`
- size: `197`
- prototype: `void *__fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180044814`

## callees

- `0x180044604`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18004464a`
- `KERNEL32!GetLastError` at `0x18004464a`
- `KERNEL32!CloseHandle` at `0x1800446b5`
- `KERNEL32!CloseHandle` at `0x1800446b5`
- `KERNEL32!WriteFile` at `0x1800446a8`
- `KERNEL32!WriteFile` at `0x1800446a8`
- `KERNEL32!CreateFileW` at `0x18004463b`
- `KERNEL32!CreateFileW` at `0x18004467b`
- `KERNEL32!CreateFileW` at `0x18004463b`
- `KERNEL32!CreateFileW` at `0x18004467b`

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
    if ( v3 != (HANDLE)-1LL && !WriteFile(v3, &qword_18007EF48, 8u, &NumberOfBytesWritten, 0) )
      CloseHandle(FileW);
  }
  return FileW;
}

```

## disassembly

```asm
0x180044604  mov     rax, rsp
0x180044607  mov     [rax+8], rbx
0x18004460b  push    rdi
0x18004460c  sub     rsp, 40h
0x180044610  xor     r9d, r9d; lpSecurityAttributes
0x180044613  mov     qword ptr [rax-18h], 0
0x18004461b  mov     dword ptr [rax-20h], 80h
0x180044622  mov     rdi, rcx
0x180044625  mov     dword ptr [rax+10h], 0
0x18004462c  mov     dword ptr [rax-28h], 3
0x180044633  lea     edx, [r9+6]; dwDesiredAccess
0x180044637  lea     r8d, [r9+1]; dwShareMode
0x18004463b  call    cs:__imp_CreateFileW
0x180044641  mov     rbx, rax
0x180044644  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180044648  jnz     short loc_1800446BB
0x18004464a  call    cs:__imp_GetLastError
0x180044650  cmp     eax, 2
0x180044653  jnz     short loc_1800446BB
0x180044655  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x18004465e  lea     edx, [rbx+7]; dwDesiredAccess
0x180044661  mov     [rsp+48h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180044669  lea     r8d, [rbx+2]; dwShareMode
0x18004466d  xor     r9d, r9d; lpSecurityAttributes
0x180044670  mov     [rsp+48h+dwCreationDisposition], 4; dwCreationDisposition
0x180044678  mov     rcx, rdi; lpFileName
0x18004467b  call    cs:__imp_CreateFileW
0x180044681  mov     rbx, rax
0x180044684  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180044688  jz      short loc_1800446BB
0x18004468a  lea     r9, [rsp+48h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18004468f  mov     qword ptr [rsp+48h+dwCreationDisposition], 0; lpOverlapped
0x180044698  mov     r8d, 8; nNumberOfBytesToWrite
0x18004469e  lea     rdx, qword_18007EF48; lpBuffer
0x1800446a5  mov     rcx, rax; hFile
0x1800446a8  call    cs:__imp_WriteFile
0x1800446ae  test    eax, eax
0x1800446b0  jnz     short loc_1800446BB
0x1800446b2  mov     rcx, rbx; hObject
0x1800446b5  call    cs:__imp_CloseHandle
0x1800446bb  mov     rax, rbx
0x1800446be  mov     rbx, [rsp+48h+arg_0]
0x1800446c3  add     rsp, 40h
0x1800446c7  pop     rdi
0x1800446c8  retn
```
