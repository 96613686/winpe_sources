# MapMUIFile

- ea: `0x180159744`
- end: `0x180159828`
- name: `MapMUIFile`
- size: `228`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x1800c0e38`
- `0x180159928`

## callees

- `0x180159744`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180159813`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180159813`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801597c3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801597f0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801597c3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801597f0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180159787`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180159787`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1801597b7`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1801597b7`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1801597e4`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1801597e4`

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
0x180159744  mov     [rsp+arg_0], rbx
0x180159749  push    rdi
0x18015974a  sub     rsp, 40h
0x18015974e  mov     eax, r8d
0x180159751  test    rcx, rcx
0x180159754  jz      loc_18015981B
0x18015975a  test    edx, edx
0x18015975c  jz      loc_180159808
0x180159762  xor     r9d, r9d; lpSecurityAttributes
0x180159765  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x18015976e  mov     [rsp+48h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x180159776  mov     edx, 80000000h; dwDesiredAccess
0x18015977b  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x180159783  lea     r8d, [r9+5]; dwShareMode
0x180159787  call    cs:__imp_CreateFileW
0x18015978d  mov     rbx, rax
0x180159790  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180159794  jz      loc_18015981B
0x18015979a  xor     r9d, r9d; dwMaximumSizeHigh
0x18015979d  mov     qword ptr [rsp+48h+dwFlagsAndAttributes], 0; lpName
0x1801597a6  xor     edx, edx; lpFileMappingAttributes
0x1801597a8  mov     [rsp+48h+dwCreationDisposition], 0; dwMaximumSizeLow
0x1801597b0  mov     rcx, rax; hFile
0x1801597b3  lea     r8d, [r9+8]; flProtect
0x1801597b7  call    cs:__imp_CreateFileMappingW
0x1801597bd  mov     rcx, rbx; hObject
0x1801597c0  mov     rdi, rax
0x1801597c3  call    cs:__imp_CloseHandle
0x1801597c9  test    rdi, rdi
0x1801597cc  jz      short loc_18015981B
0x1801597ce  xor     r9d, r9d; dwFileOffsetLow
0x1801597d1  mov     qword ptr [rsp+48h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x1801597da  xor     r8d, r8d; dwFileOffsetHigh
0x1801597dd  mov     rcx, rdi; hFileMappingObject
0x1801597e0  lea     edx, [r9+1]; dwDesiredAccess
0x1801597e4  call    cs:__imp_MapViewOfFile
0x1801597ea  mov     rcx, rdi; hObject
0x1801597ed  mov     rbx, rax
0x1801597f0  call    cs:__imp_CloseHandle
0x1801597f6  mov     rcx, rbx
0x1801597f9  or      rcx, 1; lpLibFileName
0x1801597fd  neg     rbx
0x180159800  sbb     rax, rax
0x180159803  and     rax, rcx
0x180159806  jmp     short loc_18015981D
0x180159808  xor     r8d, r8d
0x18015980b  test    eax, eax
0x18015980d  setnz   r8b; dwFlags
0x180159811  xor     edx, edx; hFile
0x180159813  call    cs:__imp_LoadLibraryExW
0x180159819  jmp     short loc_18015981D
0x18015981b  xor     eax, eax
0x18015981d  mov     rbx, [rsp+48h+arg_0]
0x180159822  add     rsp, 40h
0x180159826  pop     rdi
0x180159827  retn
```
