# OpenUnicodeLogFile(ushort const *)

- ea: `0x18001b0d4`
- end: `0x18001b199`
- name: `?OpenUnicodeLogFile@@YAPEAXPEBG@Z`
- size: `197`
- prototype: `HANDLE __fastcall(LPCWSTR lpFileName)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18001af7c`
- `0x18001b1a0`

## callees

- `0x18001b0d4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b11a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b11a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b185`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b185`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001b10b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001b14b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001b10b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001b14b`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001b178`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001b178`

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
    if ( v3 != (HANDLE)-1LL && !WriteFile(v3, &qword_180030A38, 8u, &NumberOfBytesWritten, 0) )
      CloseHandle(FileW);
  }
  return FileW;
}

```

## disassembly

```asm
0x18001b0d4  mov     rax, rsp
0x18001b0d7  mov     [rax+8], rbx
0x18001b0db  push    rdi
0x18001b0dc  sub     rsp, 40h
0x18001b0e0  xor     r9d, r9d; lpSecurityAttributes
0x18001b0e3  mov     qword ptr [rax-18h], 0
0x18001b0eb  mov     dword ptr [rax-20h], 80h
0x18001b0f2  mov     rdi, rcx
0x18001b0f5  mov     dword ptr [rax+10h], 0
0x18001b0fc  mov     dword ptr [rax-28h], 3
0x18001b103  lea     edx, [r9+6]; dwDesiredAccess
0x18001b107  lea     r8d, [r9+1]; dwShareMode
0x18001b10b  call    cs:__imp_CreateFileW
0x18001b111  mov     rbx, rax
0x18001b114  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001b118  jnz     short loc_18001B18B
0x18001b11a  call    cs:__imp_GetLastError
0x18001b120  cmp     eax, 2
0x18001b123  jnz     short loc_18001B18B
0x18001b125  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x18001b12e  lea     edx, [rbx+7]; dwDesiredAccess
0x18001b131  mov     [rsp+48h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18001b139  lea     r8d, [rbx+2]; dwShareMode
0x18001b13d  xor     r9d, r9d; lpSecurityAttributes
0x18001b140  mov     [rsp+48h+dwCreationDisposition], 4; dwCreationDisposition
0x18001b148  mov     rcx, rdi; lpFileName
0x18001b14b  call    cs:__imp_CreateFileW
0x18001b151  mov     rbx, rax
0x18001b154  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001b158  jz      short loc_18001B18B
0x18001b15a  lea     r9, [rsp+48h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18001b15f  mov     qword ptr [rsp+48h+dwCreationDisposition], 0; lpOverlapped
0x18001b168  mov     r8d, 8; nNumberOfBytesToWrite
0x18001b16e  lea     rdx, qword_180030A38; lpBuffer
0x18001b175  mov     rcx, rax; hFile
0x18001b178  call    cs:__imp_WriteFile
0x18001b17e  test    eax, eax
0x18001b180  jnz     short loc_18001B18B
0x18001b182  mov     rcx, rbx; hObject
0x18001b185  call    cs:__imp_CloseHandle
0x18001b18b  mov     rax, rbx
0x18001b18e  mov     rbx, [rsp+48h+arg_0]
0x18001b193  add     rsp, 40h
0x18001b197  pop     rdi
0x18001b198  retn
```
