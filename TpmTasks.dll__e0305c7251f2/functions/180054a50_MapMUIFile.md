# MapMUIFile

- ea: `0x180054a50`
- end: `0x180054b34`
- name: `MapMUIFile`
- size: `228`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x180054bf8`
- `0x180054cc8`

## callees

- `0x180054a50`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180054b1f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180054b1f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180054a93`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180054a93`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180054acf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180054afc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180054acf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180054afc`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180054af0`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180054af0`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180054ac3`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180054ac3`

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
0x180054a50  mov     [rsp+arg_0], rbx
0x180054a55  push    rdi
0x180054a56  sub     rsp, 40h
0x180054a5a  mov     eax, r8d
0x180054a5d  test    rcx, rcx
0x180054a60  jz      loc_180054B27
0x180054a66  test    edx, edx
0x180054a68  jz      loc_180054B14
0x180054a6e  xor     r9d, r9d; lpSecurityAttributes
0x180054a71  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x180054a7a  mov     [rsp+48h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x180054a82  mov     edx, 80000000h; dwDesiredAccess
0x180054a87  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x180054a8f  lea     r8d, [r9+5]; dwShareMode
0x180054a93  call    cs:__imp_CreateFileW
0x180054a99  mov     rbx, rax
0x180054a9c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180054aa0  jz      loc_180054B27
0x180054aa6  xor     r9d, r9d; dwMaximumSizeHigh
0x180054aa9  mov     qword ptr [rsp+48h+dwFlagsAndAttributes], 0; lpName
0x180054ab2  xor     edx, edx; lpFileMappingAttributes
0x180054ab4  mov     [rsp+48h+dwCreationDisposition], 0; dwMaximumSizeLow
0x180054abc  mov     rcx, rax; hFile
0x180054abf  lea     r8d, [r9+8]; flProtect
0x180054ac3  call    cs:__imp_CreateFileMappingW
0x180054ac9  mov     rcx, rbx; hObject
0x180054acc  mov     rdi, rax
0x180054acf  call    cs:__imp_CloseHandle
0x180054ad5  test    rdi, rdi
0x180054ad8  jz      short loc_180054B27
0x180054ada  xor     r9d, r9d; dwFileOffsetLow
0x180054add  mov     qword ptr [rsp+48h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x180054ae6  xor     r8d, r8d; dwFileOffsetHigh
0x180054ae9  mov     rcx, rdi; hFileMappingObject
0x180054aec  lea     edx, [r9+1]; dwDesiredAccess
0x180054af0  call    cs:__imp_MapViewOfFile
0x180054af6  mov     rcx, rdi; hObject
0x180054af9  mov     rbx, rax
0x180054afc  call    cs:__imp_CloseHandle
0x180054b02  mov     rcx, rbx
0x180054b05  or      rcx, 1; lpLibFileName
0x180054b09  neg     rbx
0x180054b0c  sbb     rax, rax
0x180054b0f  and     rax, rcx
0x180054b12  jmp     short loc_180054B29
0x180054b14  xor     r8d, r8d
0x180054b17  test    eax, eax
0x180054b19  setnz   r8b; dwFlags
0x180054b1d  xor     edx, edx; hFile
0x180054b1f  call    cs:__imp_LoadLibraryExW
0x180054b25  jmp     short loc_180054B29
0x180054b27  xor     eax, eax
0x180054b29  mov     rbx, [rsp+48h+arg_0]
0x180054b2e  add     rsp, 40h
0x180054b32  pop     rdi
0x180054b33  retn
```
