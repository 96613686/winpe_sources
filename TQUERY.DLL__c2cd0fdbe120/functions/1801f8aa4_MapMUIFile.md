# MapMUIFile

- ea: `0x1801f8aa4`
- end: `0x1801f8b88`
- name: `MapMUIFile`
- size: `228`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x1801f8bd0`
- `0x1801f8d00`

## callees

- `0x1801f8aa4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1801f8b73`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1801f8b73`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801f8b23`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801f8b50`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801f8b23`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801f8b50`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1801f8b44`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1801f8b44`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1801f8b17`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1801f8b17`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801f8ae7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801f8ae7`

## pseudocode

```c
HMODULE __fastcall MapMUIFile(const WCHAR *a1, int a2, int a3)
{
  HANDLE FileW; // rax
  void *v4; // rbx
  HANDLE FileMappingW; // rdi
  unsigned __int64 v6; // rbx

  if ( a1 )
  {
    if ( !a2 )
      return LoadLibraryExW(a1, 0, a3 != 0);
    FileW = CreateFileW(a1, 0x80000000, 5u, 0, 3u, 0, 0);
    v4 = FileW;
    if ( FileW != (HANDLE)-1LL )
    {
      FileMappingW = CreateFileMappingW(FileW, 0, 8u, 0, 0, 0);
      CloseHandle(v4);
      if ( FileMappingW )
      {
        v6 = (unsigned __int64)MapViewOfFile(FileMappingW, 1u, 0, 0, 0);
        CloseHandle(FileMappingW);
        return (HMODULE)((v6 | 1) & -(__int64)(v6 != 0));
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1801f8aa4  mov     [rsp+arg_0], rbx
0x1801f8aa9  push    rdi
0x1801f8aaa  sub     rsp, 40h
0x1801f8aae  mov     eax, r8d
0x1801f8ab1  test    rcx, rcx
0x1801f8ab4  jz      loc_1801F8B7B
0x1801f8aba  test    edx, edx
0x1801f8abc  jz      loc_1801F8B68
0x1801f8ac2  xor     r9d, r9d; lpSecurityAttributes
0x1801f8ac5  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x1801f8ace  mov     [rsp+48h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x1801f8ad6  mov     edx, 80000000h; dwDesiredAccess
0x1801f8adb  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x1801f8ae3  lea     r8d, [r9+5]; dwShareMode
0x1801f8ae7  call    cs:__imp_CreateFileW
0x1801f8aed  mov     rbx, rax
0x1801f8af0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801f8af4  jz      loc_1801F8B7B
0x1801f8afa  xor     r9d, r9d; dwMaximumSizeHigh
0x1801f8afd  mov     qword ptr [rsp+48h+dwFlagsAndAttributes], 0; lpName
0x1801f8b06  xor     edx, edx; lpFileMappingAttributes
0x1801f8b08  mov     [rsp+48h+dwCreationDisposition], 0; dwMaximumSizeLow
0x1801f8b10  mov     rcx, rax; hFile
0x1801f8b13  lea     r8d, [r9+8]; flProtect
0x1801f8b17  call    cs:__imp_CreateFileMappingW
0x1801f8b1d  mov     rcx, rbx; hObject
0x1801f8b20  mov     rdi, rax
0x1801f8b23  call    cs:__imp_CloseHandle
0x1801f8b29  test    rdi, rdi
0x1801f8b2c  jz      short loc_1801F8B7B
0x1801f8b2e  xor     r9d, r9d; dwFileOffsetLow
0x1801f8b31  mov     qword ptr [rsp+48h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x1801f8b3a  xor     r8d, r8d; dwFileOffsetHigh
0x1801f8b3d  mov     rcx, rdi; hFileMappingObject
0x1801f8b40  lea     edx, [r9+1]; dwDesiredAccess
0x1801f8b44  call    cs:__imp_MapViewOfFile
0x1801f8b4a  mov     rcx, rdi; hObject
0x1801f8b4d  mov     rbx, rax
0x1801f8b50  call    cs:__imp_CloseHandle
0x1801f8b56  mov     rcx, rbx
0x1801f8b59  or      rcx, 1; lpLibFileName
0x1801f8b5d  neg     rbx
0x1801f8b60  sbb     rax, rax
0x1801f8b63  and     rax, rcx
0x1801f8b66  jmp     short loc_1801F8B7D
0x1801f8b68  xor     r8d, r8d
0x1801f8b6b  test    eax, eax
0x1801f8b6d  setnz   r8b; dwFlags
0x1801f8b71  xor     edx, edx; hFile
0x1801f8b73  call    cs:__imp_LoadLibraryExW
0x1801f8b79  jmp     short loc_1801F8B7D
0x1801f8b7b  xor     eax, eax
0x1801f8b7d  mov     rbx, [rsp+48h+arg_0]
0x1801f8b82  add     rsp, 40h
0x1801f8b86  pop     rdi
0x1801f8b87  retn
```
