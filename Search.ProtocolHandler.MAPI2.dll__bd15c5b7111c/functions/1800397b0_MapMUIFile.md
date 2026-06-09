# MapMUIFile

- ea: `0x1800397b0`
- end: `0x180039894`
- name: `MapMUIFile`
- size: `228`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x1800398dc`
- `0x1800399f4`

## callees

- `0x1800397b0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003987f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003987f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003982f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003985c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003982f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003985c`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180039823`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180039823`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180039850`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180039850`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800397f3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800397f3`

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
0x1800397b0  mov     [rsp+arg_0], rbx
0x1800397b5  push    rdi
0x1800397b6  sub     rsp, 40h
0x1800397ba  mov     eax, r8d
0x1800397bd  test    rcx, rcx
0x1800397c0  jz      loc_180039887
0x1800397c6  test    edx, edx
0x1800397c8  jz      loc_180039874
0x1800397ce  xor     r9d, r9d; lpSecurityAttributes
0x1800397d1  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x1800397da  mov     [rsp+48h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x1800397e2  mov     edx, 80000000h; dwDesiredAccess
0x1800397e7  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x1800397ef  lea     r8d, [r9+5]; dwShareMode
0x1800397f3  call    cs:__imp_CreateFileW
0x1800397f9  mov     rbx, rax
0x1800397fc  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180039800  jz      loc_180039887
0x180039806  xor     r9d, r9d; dwMaximumSizeHigh
0x180039809  mov     qword ptr [rsp+48h+dwFlagsAndAttributes], 0; lpName
0x180039812  xor     edx, edx; lpFileMappingAttributes
0x180039814  mov     [rsp+48h+dwCreationDisposition], 0; dwMaximumSizeLow
0x18003981c  mov     rcx, rax; hFile
0x18003981f  lea     r8d, [r9+8]; flProtect
0x180039823  call    cs:__imp_CreateFileMappingW
0x180039829  mov     rcx, rbx; hObject
0x18003982c  mov     rdi, rax
0x18003982f  call    cs:__imp_CloseHandle
0x180039835  test    rdi, rdi
0x180039838  jz      short loc_180039887
0x18003983a  xor     r9d, r9d; dwFileOffsetLow
0x18003983d  mov     qword ptr [rsp+48h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x180039846  xor     r8d, r8d; dwFileOffsetHigh
0x180039849  mov     rcx, rdi; hFileMappingObject
0x18003984c  lea     edx, [r9+1]; dwDesiredAccess
0x180039850  call    cs:__imp_MapViewOfFile
0x180039856  mov     rcx, rdi; hObject
0x180039859  mov     rbx, rax
0x18003985c  call    cs:__imp_CloseHandle
0x180039862  mov     rcx, rbx
0x180039865  or      rcx, 1; lpLibFileName
0x180039869  neg     rbx
0x18003986c  sbb     rax, rax
0x18003986f  and     rax, rcx
0x180039872  jmp     short loc_180039889
0x180039874  xor     r8d, r8d
0x180039877  test    eax, eax
0x180039879  setnz   r8b; dwFlags
0x18003987d  xor     edx, edx; hFile
0x18003987f  call    cs:__imp_LoadLibraryExW
0x180039885  jmp     short loc_180039889
0x180039887  xor     eax, eax
0x180039889  mov     rbx, [rsp+48h+arg_0]
0x18003988e  add     rsp, 40h
0x180039892  pop     rdi
0x180039893  retn
```
