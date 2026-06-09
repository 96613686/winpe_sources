# MapMUIFile

- ea: `0x180083ec4`
- end: `0x180083fa8`
- name: `MapMUIFile`
- size: `228`
- prototype: `HMODULE __fastcall(const WCHAR *, int, int)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x180084054`
- `0x18008416c`

## callees

- `0x180083ec4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180083f93`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180083f93`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180083f43`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180083f70`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180083f43`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180083f70`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180083f07`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180083f07`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180083f37`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180083f37`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180083f64`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180083f64`

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
0x180083ec4  mov     [rsp+arg_0], rbx
0x180083ec9  push    rdi
0x180083eca  sub     rsp, 40h
0x180083ece  mov     eax, r8d
0x180083ed1  test    rcx, rcx
0x180083ed4  jz      loc_180083F9B
0x180083eda  test    edx, edx
0x180083edc  jz      loc_180083F88
0x180083ee2  xor     r9d, r9d; lpSecurityAttributes
0x180083ee5  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x180083eee  mov     [rsp+48h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x180083ef6  mov     edx, 80000000h; dwDesiredAccess
0x180083efb  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x180083f03  lea     r8d, [r9+5]; dwShareMode
0x180083f07  call    cs:__imp_CreateFileW
0x180083f0d  mov     rbx, rax
0x180083f10  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180083f14  jz      loc_180083F9B
0x180083f1a  xor     r9d, r9d; dwMaximumSizeHigh
0x180083f1d  mov     qword ptr [rsp+48h+dwFlagsAndAttributes], 0; lpName
0x180083f26  xor     edx, edx; lpFileMappingAttributes
0x180083f28  mov     [rsp+48h+dwCreationDisposition], 0; dwMaximumSizeLow
0x180083f30  mov     rcx, rax; hFile
0x180083f33  lea     r8d, [r9+8]; flProtect
0x180083f37  call    cs:__imp_CreateFileMappingW
0x180083f3d  mov     rcx, rbx; hObject
0x180083f40  mov     rdi, rax
0x180083f43  call    cs:__imp_CloseHandle
0x180083f49  test    rdi, rdi
0x180083f4c  jz      short loc_180083F9B
0x180083f4e  xor     r9d, r9d; dwFileOffsetLow
0x180083f51  mov     qword ptr [rsp+48h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x180083f5a  xor     r8d, r8d; dwFileOffsetHigh
0x180083f5d  mov     rcx, rdi; hFileMappingObject
0x180083f60  lea     edx, [r9+1]; dwDesiredAccess
0x180083f64  call    cs:__imp_MapViewOfFile
0x180083f6a  mov     rcx, rdi; hObject
0x180083f6d  mov     rbx, rax
0x180083f70  call    cs:__imp_CloseHandle
0x180083f76  mov     rcx, rbx
0x180083f79  or      rcx, 1; lpLibFileName
0x180083f7d  neg     rbx
0x180083f80  sbb     rax, rax
0x180083f83  and     rax, rcx
0x180083f86  jmp     short loc_180083F9D
0x180083f88  xor     r8d, r8d
0x180083f8b  test    eax, eax
0x180083f8d  setnz   r8b; dwFlags
0x180083f91  xor     edx, edx; hFile
0x180083f93  call    cs:__imp_LoadLibraryExW
0x180083f99  jmp     short loc_180083F9D
0x180083f9b  xor     eax, eax
0x180083f9d  mov     rbx, [rsp+48h+arg_0]
0x180083fa2  add     rsp, 40h
0x180083fa6  pop     rdi
0x180083fa7  retn
```
