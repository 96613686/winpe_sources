# MapMUIFile

- ea: `0x14006918c`
- end: `0x140069270`
- name: `MapMUIFile`
- size: `228`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x1400692b8`
- `0x1400693d0`

## callees

- `0x14006918c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14006925b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14006925b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14006920b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140069238`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14006920b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140069238`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400691cf`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400691cf`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1400691ff`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1400691ff`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x14006922c`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x14006922c`

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
0x14006918c  mov     [rsp+arg_0], rbx
0x140069191  push    rdi
0x140069192  sub     rsp, 40h
0x140069196  mov     eax, r8d
0x140069199  test    rcx, rcx
0x14006919c  jz      loc_140069263
0x1400691a2  test    edx, edx
0x1400691a4  jz      loc_140069250
0x1400691aa  xor     r9d, r9d; lpSecurityAttributes
0x1400691ad  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x1400691b6  mov     [rsp+48h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x1400691be  mov     edx, 80000000h; dwDesiredAccess
0x1400691c3  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x1400691cb  lea     r8d, [r9+5]; dwShareMode
0x1400691cf  call    cs:__imp_CreateFileW
0x1400691d5  mov     rbx, rax
0x1400691d8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400691dc  jz      loc_140069263
0x1400691e2  xor     r9d, r9d; dwMaximumSizeHigh
0x1400691e5  mov     qword ptr [rsp+48h+dwFlagsAndAttributes], 0; lpName
0x1400691ee  xor     edx, edx; lpFileMappingAttributes
0x1400691f0  mov     [rsp+48h+dwCreationDisposition], 0; dwMaximumSizeLow
0x1400691f8  mov     rcx, rax; hFile
0x1400691fb  lea     r8d, [r9+8]; flProtect
0x1400691ff  call    cs:__imp_CreateFileMappingW
0x140069205  mov     rcx, rbx; hObject
0x140069208  mov     rdi, rax
0x14006920b  call    cs:__imp_CloseHandle
0x140069211  test    rdi, rdi
0x140069214  jz      short loc_140069263
0x140069216  xor     r9d, r9d; dwFileOffsetLow
0x140069219  mov     qword ptr [rsp+48h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x140069222  xor     r8d, r8d; dwFileOffsetHigh
0x140069225  mov     rcx, rdi; hFileMappingObject
0x140069228  lea     edx, [r9+1]; dwDesiredAccess
0x14006922c  call    cs:__imp_MapViewOfFile
0x140069232  mov     rcx, rdi; hObject
0x140069235  mov     rbx, rax
0x140069238  call    cs:__imp_CloseHandle
0x14006923e  mov     rcx, rbx
0x140069241  or      rcx, 1; lpLibFileName
0x140069245  neg     rbx
0x140069248  sbb     rax, rax
0x14006924b  and     rax, rcx
0x14006924e  jmp     short loc_140069265
0x140069250  xor     r8d, r8d
0x140069253  test    eax, eax
0x140069255  setnz   r8b; dwFlags
0x140069259  xor     edx, edx; hFile
0x14006925b  call    cs:__imp_LoadLibraryExW
0x140069261  jmp     short loc_140069265
0x140069263  xor     eax, eax
0x140069265  mov     rbx, [rsp+48h+arg_0]
0x14006926a  add     rsp, 40h
0x14006926e  pop     rdi
0x14006926f  retn
```
