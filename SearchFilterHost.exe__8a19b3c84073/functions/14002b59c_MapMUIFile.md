# MapMUIFile

- ea: `0x14002b59c`
- end: `0x14002b680`
- name: `MapMUIFile`
- size: `228`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x14002b6c8`
- `0x14002b7e0`

## callees

- `0x14002b59c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14002b66b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14002b66b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002b61b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002b648`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002b61b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002b648`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14002b5df`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14002b5df`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x14002b63c`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x14002b63c`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x14002b60f`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x14002b60f`

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
0x14002b59c  mov     [rsp+arg_0], rbx
0x14002b5a1  push    rdi
0x14002b5a2  sub     rsp, 40h
0x14002b5a6  mov     eax, r8d
0x14002b5a9  test    rcx, rcx
0x14002b5ac  jz      loc_14002B673
0x14002b5b2  test    edx, edx
0x14002b5b4  jz      loc_14002B660
0x14002b5ba  xor     r9d, r9d; lpSecurityAttributes
0x14002b5bd  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x14002b5c6  mov     [rsp+48h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x14002b5ce  mov     edx, 80000000h; dwDesiredAccess
0x14002b5d3  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x14002b5db  lea     r8d, [r9+5]; dwShareMode
0x14002b5df  call    cs:__imp_CreateFileW
0x14002b5e5  mov     rbx, rax
0x14002b5e8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14002b5ec  jz      loc_14002B673
0x14002b5f2  xor     r9d, r9d; dwMaximumSizeHigh
0x14002b5f5  mov     qword ptr [rsp+48h+dwFlagsAndAttributes], 0; lpName
0x14002b5fe  xor     edx, edx; lpFileMappingAttributes
0x14002b600  mov     [rsp+48h+dwCreationDisposition], 0; dwMaximumSizeLow
0x14002b608  mov     rcx, rax; hFile
0x14002b60b  lea     r8d, [r9+8]; flProtect
0x14002b60f  call    cs:__imp_CreateFileMappingW
0x14002b615  mov     rcx, rbx; hObject
0x14002b618  mov     rdi, rax
0x14002b61b  call    cs:__imp_CloseHandle
0x14002b621  test    rdi, rdi
0x14002b624  jz      short loc_14002B673
0x14002b626  xor     r9d, r9d; dwFileOffsetLow
0x14002b629  mov     qword ptr [rsp+48h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x14002b632  xor     r8d, r8d; dwFileOffsetHigh
0x14002b635  mov     rcx, rdi; hFileMappingObject
0x14002b638  lea     edx, [r9+1]; dwDesiredAccess
0x14002b63c  call    cs:__imp_MapViewOfFile
0x14002b642  mov     rcx, rdi; hObject
0x14002b645  mov     rbx, rax
0x14002b648  call    cs:__imp_CloseHandle
0x14002b64e  mov     rcx, rbx
0x14002b651  or      rcx, 1; lpLibFileName
0x14002b655  neg     rbx
0x14002b658  sbb     rax, rax
0x14002b65b  and     rax, rcx
0x14002b65e  jmp     short loc_14002B675
0x14002b660  xor     r8d, r8d
0x14002b663  test    eax, eax
0x14002b665  setnz   r8b; dwFlags
0x14002b669  xor     edx, edx; hFile
0x14002b66b  call    cs:__imp_LoadLibraryExW
0x14002b671  jmp     short loc_14002B675
0x14002b673  xor     eax, eax
0x14002b675  mov     rbx, [rsp+48h+arg_0]
0x14002b67a  add     rsp, 40h
0x14002b67e  pop     rdi
0x14002b67f  retn
```
