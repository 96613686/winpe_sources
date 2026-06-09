# MapFileOpen

- ea: `0x18001613c`
- end: `0x18001624e`
- name: `MapFileOpen`
- size: `274`
- prototype: `__int64 __fastcall(const WCHAR *, int, int, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800044f0`
- `0x180005b00`

## callees

- `0x180012ad4`
- `0x18001613c`

## import_xrefs

- `KERNEL32!MapViewOfFileEx` at `0x18001621b`
- `KERNEL32!MapViewOfFileEx` at `0x18001621b`
- `KERNEL32!CreateFileMappingW` at `0x1800161dc`
- `KERNEL32!CreateFileMappingW` at `0x1800161dc`
- `KERNEL32!GetFileSize` at `0x1800161ac`
- `KERNEL32!GetFileSize` at `0x1800161ac`
- `KERNEL32!CloseHandle` at `0x1800161ee`
- `KERNEL32!CloseHandle` at `0x18001622d`
- `KERNEL32!CloseHandle` at `0x1800161ee`
- `KERNEL32!CloseHandle` at `0x18001622d`

## pseudocode

```c
__int64 __fastcall MapFileOpen(const WCHAR *a1, int a2, int a3, __int64 a4)
{
  void *File; // rax
  DWORD FileSize; // eax
  HANDLE FileMappingW; // rax
  HANDLE v11; // rcx
  LPVOID v12; // rax

  *(_QWORD *)a4 = 0;
  *(_QWORD *)(a4 + 8) = 0;
  *(_QWORD *)(a4 + 16) = 0;
  File = (void *)InternalSafeCreateFile(a1, a2 != 0 ? 0x80000000 : -1073741824, a2 != 0, 3u, 0);
  *(_QWORD *)a4 = File;
  if ( File == (void *)-1LL )
    return 0;
  FileSize = GetFileSize(File, 0);
  *(_DWORD *)(a4 + 24) = FileSize;
  FileMappingW = CreateFileMappingW(*(HANDLE *)a4, 0, a2 != 0 ? 2 : 4, 0, FileSize + a3, 0);
  *(_QWORD *)(a4 + 8) = FileMappingW;
  if ( !FileMappingW )
  {
    v11 = *(HANDLE *)a4;
LABEL_5:
    CloseHandle(v11);
    return 0;
  }
  v12 = MapViewOfFileEx(FileMappingW, a2 != 0 ? 4 : 2, 0, 0, 0, 0);
  *(_QWORD *)(a4 + 16) = v12;
  if ( !v12 )
  {
    CloseHandle(*(HANDLE *)a4);
    v11 = *(HANDLE *)(a4 + 8);
    goto LABEL_5;
  }
  return 1;
}

```

## disassembly

```asm
0x18001613c  mov     [rsp+arg_0], rbx
0x180016141  mov     [rsp+arg_8], rsi
0x180016146  push    rdi
0x180016147  sub     rsp, 40h
0x18001614b  mov     eax, edx
0x18001614d  mov     dword ptr [rsp+48h+lpName], 0; int
0x180016155  mov     edi, edx
0x180016157  mov     qword ptr [r9], 0
0x18001615e  mov     esi, r8d
0x180016161  mov     qword ptr [r9+8], 0
0x180016169  xor     r8d, r8d
0x18001616c  mov     qword ptr [r9+10h], 0
0x180016174  test    edx, edx
0x180016176  mov     [rsp+48h+dwMaximumSizeLow], 3; DWORD
0x18001617e  mov     rbx, r9
0x180016181  setnz   r8b; dwShareMode
0x180016185  neg     eax
0x180016187  mov     eax, 0C0000000h
0x18001618c  sbb     edx, edx
0x18001618e  and     edx, eax
0x180016190  add     edx, eax; dwDesiredAccess
0x180016192  call    InternalSafeCreateFile
0x180016197  mov     [rbx], rax
0x18001619a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001619e  jnz     short loc_1800161A7
0x1800161a0  xor     eax, eax
0x1800161a2  jmp     loc_18001623E
0x1800161a7  xor     edx, edx; lpFileSizeHigh
0x1800161a9  mov     rcx, rax; hFile
0x1800161ac  call    cs:__imp_GetFileSize
0x1800161b2  mov     [rbx+18h], eax
0x1800161b5  mov     [rsp+48h+lpName], 0; lpName
0x1800161be  lea     ecx, [rax+rsi]
0x1800161c1  mov     eax, edi
0x1800161c3  neg     eax
0x1800161c5  mov     [rsp+48h+dwMaximumSizeLow], ecx; dwMaximumSizeLow
0x1800161c9  mov     rcx, [rbx]; hFile
0x1800161cc  sbb     r8d, r8d
0x1800161cf  xor     r9d, r9d; dwMaximumSizeHigh
0x1800161d2  and     r8d, 0FFFFFFFEh
0x1800161d6  xor     edx, edx; lpFileMappingAttributes
0x1800161d8  add     r8d, 4; flProtect
0x1800161dc  call    cs:__imp_CreateFileMappingW
0x1800161e2  mov     [rbx+8], rax
0x1800161e6  test    rax, rax
0x1800161e9  jnz     short loc_1800161F6
0x1800161eb  mov     rcx, [rbx]; hObject
0x1800161ee  call    cs:__imp_CloseHandle
0x1800161f4  jmp     short loc_1800161A0
0x1800161f6  neg     edi
0x1800161f8  mov     [rsp+48h+lpName], 0; lpBaseAddress
0x180016201  mov     rcx, rax; hFileMappingObject
0x180016204  mov     qword ptr [rsp+48h+dwMaximumSizeLow], 0; dwNumberOfBytesToMap
0x18001620d  sbb     edx, edx
0x18001620f  xor     r9d, r9d; dwFileOffsetLow
0x180016212  and     edx, 2
0x180016215  xor     r8d, r8d; dwFileOffsetHigh
0x180016218  add     edx, 2; dwDesiredAccess
0x18001621b  call    cs:__imp_MapViewOfFileEx
0x180016221  mov     [rbx+10h], rax
0x180016225  test    rax, rax
0x180016228  jnz     short loc_180016239
0x18001622a  mov     rcx, [rbx]; hObject
0x18001622d  call    cs:__imp_CloseHandle
0x180016233  mov     rcx, [rbx+8]
0x180016237  jmp     short loc_1800161EE
0x180016239  mov     eax, 1
0x18001623e  mov     rbx, [rsp+48h+arg_0]
0x180016243  mov     rsi, [rsp+48h+arg_8]
0x180016248  add     rsp, 40h
0x18001624c  pop     rdi
0x18001624d  retn
```
