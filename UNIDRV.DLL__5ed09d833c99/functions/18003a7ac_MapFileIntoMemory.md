# MapFileIntoMemory

- ea: `0x18003a7ac`
- end: `0x18003a8dc`
- name: `MapFileIntoMemory`
- size: `304`
- prototype: `__int64 __fastcall(const WCHAR *, __int64, DWORD *, HANDLE *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180022614`

## callees

- `0x18003a7ac`

## import_xrefs

- `KERNEL32!MapViewOfFile` at `0x18003a85e`
- `KERNEL32!MapViewOfFile` at `0x18003a85e`
- `KERNEL32!CloseHandle` at `0x18003a870`
- `KERNEL32!CloseHandle` at `0x18003a88b`
- `KERNEL32!CloseHandle` at `0x18003a870`
- `KERNEL32!CloseHandle` at `0x18003a88b`
- `KERNEL32!CreateFileW` at `0x18003a7f9`
- `KERNEL32!CreateFileW` at `0x18003a7f9`
- `KERNEL32!GetFileSize` at `0x18003a8c3`
- `KERNEL32!GetFileSize` at `0x18003a8c3`
- `KERNEL32!CreateFileMappingW` at `0x18003a834`
- `KERNEL32!CreateFileMappingW` at `0x18003a834`

## pseudocode

```c
__int64 __fastcall MapFileIntoMemory(const WCHAR *a1, __int64 a2, DWORD *a3, HANDLE *a4)
{
  HANDLE FileW; // rax
  HANDLE FileMappingW; // rax
  void *v9; // rsi
  DWORD FileSize; // eax

  if ( !a4 )
  {
LABEL_9:
    if ( a2 )
      *(_QWORD *)a2 = 0;
    return *(_QWORD *)a2;
  }
  if ( !a2 )
    goto LABEL_7;
  FileW = CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0x100080u, 0);
  *a4 = FileW;
  if ( FileW == (HANDLE)-1LL )
    goto LABEL_7;
  if ( a3 )
  {
    FileSize = GetFileSize(FileW, 0);
    *a3 = FileSize;
    if ( FileSize == -1 )
      goto LABEL_7;
  }
  FileMappingW = CreateFileMappingW(*a4, 0, 2u, 0, 0, 0);
  v9 = FileMappingW;
  if ( !FileMappingW || (*(_QWORD *)a2 = MapViewOfFile(FileMappingW, 4u, 0, 0, 0), CloseHandle(v9), !*(_QWORD *)a2) )
  {
LABEL_7:
    if ( *a4 != (HANDLE)-1LL )
    {
      CloseHandle(*a4);
      *a4 = (HANDLE)-1LL;
    }
    goto LABEL_9;
  }
  return *(_QWORD *)a2;
}

```

## disassembly

```asm
0x18003a7ac  mov     rax, rsp
0x18003a7af  mov     [rax+8], rbx
0x18003a7b3  mov     [rax+10h], rsi
0x18003a7b7  push    rdi
0x18003a7b8  sub     rsp, 40h
0x18003a7bc  mov     rdi, r9
0x18003a7bf  mov     rsi, r8
0x18003a7c2  mov     rbx, rdx
0x18003a7c5  test    r9, r9
0x18003a7c8  jz      loc_18003A89E
0x18003a7ce  test    rdx, rdx
0x18003a7d1  jz      loc_18003A882
0x18003a7d7  mov     qword ptr [rax-18h], 0
0x18003a7df  xor     r9d, r9d; lpSecurityAttributes
0x18003a7e2  mov     dword ptr [rax-20h], 100080h
0x18003a7e9  mov     edx, 80000000h; dwDesiredAccess
0x18003a7ee  mov     dword ptr [rax-28h], 3
0x18003a7f5  lea     r8d, [r9+1]; dwShareMode
0x18003a7f9  call    cs:__imp_CreateFileW
0x18003a800  nop     dword ptr [rax+rax+00h]
0x18003a805  mov     [rdi], rax
0x18003a808  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003a80c  jz      short loc_18003A882
0x18003a80e  test    rsi, rsi
0x18003a811  jnz     loc_18003A8BE
0x18003a817  mov     rcx, [rdi]; hFile
0x18003a81a  xor     r9d, r9d; dwMaximumSizeHigh
0x18003a81d  mov     [rsp+48h+lpName], 0; lpName
0x18003a826  xor     edx, edx; lpFileMappingAttributes
0x18003a828  mov     [rsp+48h+dwMaximumSizeLow], 0; dwMaximumSizeLow
0x18003a830  lea     r8d, [r9+2]; flProtect
0x18003a834  call    cs:__imp_CreateFileMappingW
0x18003a83b  nop     dword ptr [rax+rax+00h]
0x18003a840  mov     rsi, rax
0x18003a843  test    rax, rax
0x18003a846  jz      short loc_18003A882
0x18003a848  xor     r9d, r9d; dwFileOffsetLow
0x18003a84b  mov     qword ptr [rsp+48h+dwMaximumSizeLow], 0; dwNumberOfBytesToMap
0x18003a854  xor     r8d, r8d; dwFileOffsetHigh
0x18003a857  mov     rcx, rax; hFileMappingObject
0x18003a85a  lea     edx, [r9+4]; dwDesiredAccess
0x18003a85e  call    cs:__imp_MapViewOfFile
0x18003a865  nop     dword ptr [rax+rax+00h]
0x18003a86a  mov     rcx, rsi; hObject
0x18003a86d  mov     [rbx], rax
0x18003a870  call    cs:__imp_CloseHandle
0x18003a877  nop     dword ptr [rax+rax+00h]
0x18003a87c  cmp     qword ptr [rbx], 0
0x18003a880  jnz     short loc_18003A8AA
0x18003a882  cmp     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x18003a886  jz      short loc_18003A89E
0x18003a888  mov     rcx, [rdi]; hObject
0x18003a88b  call    cs:__imp_CloseHandle
0x18003a892  nop     dword ptr [rax+rax+00h]
0x18003a897  mov     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x18003a89e  test    rbx, rbx
0x18003a8a1  jz      short loc_18003A8AA
0x18003a8a3  mov     qword ptr [rbx], 0
0x18003a8aa  mov     rax, [rbx]
0x18003a8ad  mov     rbx, [rsp+48h+arg_0]
0x18003a8b2  mov     rsi, [rsp+48h+arg_8]
0x18003a8b7  add     rsp, 40h
0x18003a8bb  pop     rdi
0x18003a8bc  retn
0x18003a8be  xor     edx, edx; lpFileSizeHigh
0x18003a8c0  mov     rcx, rax; hFile
0x18003a8c3  call    cs:__imp_GetFileSize
0x18003a8ca  nop     dword ptr [rax+rax+00h]
0x18003a8cf  mov     [rsi], eax
0x18003a8d1  cmp     eax, 0FFFFFFFFh
0x18003a8d4  jnz     loc_18003A817
0x18003a8da  jmp     short loc_18003A882
```
