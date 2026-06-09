# MapFileOpen

- ea: `0x180016d50`
- end: `0x180016e81`
- name: `MapFileOpen`
- size: `305`
- prototype: `__int64 __fastcall(const WCHAR *, int, int, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180004540`
- `0x180005c30`

## callees

- `0x1800131b4`
- `0x180016d50`

## import_xrefs

- `KERNEL32!MapViewOfFileEx` at `0x180016e41`
- `KERNEL32!MapViewOfFileEx` at `0x180016e41`
- `KERNEL32!CreateFileMappingW` at `0x180016df6`
- `KERNEL32!CreateFileMappingW` at `0x180016df6`
- `KERNEL32!GetFileSize` at `0x180016dc0`
- `KERNEL32!GetFileSize` at `0x180016dc0`
- `KERNEL32!CloseHandle` at `0x180016e0e`
- `KERNEL32!CloseHandle` at `0x180016e59`
- `KERNEL32!CloseHandle` at `0x180016e0e`
- `KERNEL32!CloseHandle` at `0x180016e59`

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
0x180016d50  mov     [rsp+arg_0], rbx
0x180016d55  mov     [rsp+arg_8], rsi
0x180016d5a  push    rdi
0x180016d5b  sub     rsp, 40h
0x180016d5f  mov     eax, edx
0x180016d61  mov     dword ptr [rsp+48h+lpName], 0; int
0x180016d69  mov     edi, edx
0x180016d6b  mov     qword ptr [r9], 0
0x180016d72  mov     esi, r8d
0x180016d75  mov     qword ptr [r9+8], 0
0x180016d7d  xor     r8d, r8d
0x180016d80  mov     qword ptr [r9+10h], 0
0x180016d88  test    edx, edx
0x180016d8a  mov     [rsp+48h+dwMaximumSizeLow], 3; DWORD
0x180016d92  mov     rbx, r9
0x180016d95  setnz   r8b; dwShareMode
0x180016d99  neg     eax
0x180016d9b  mov     eax, 0C0000000h
0x180016da0  sbb     edx, edx
0x180016da2  and     edx, eax
0x180016da4  add     edx, eax; dwDesiredAccess
0x180016da6  call    InternalSafeCreateFile
0x180016dab  mov     [rbx], rax
0x180016dae  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180016db2  jnz     short loc_180016DBB
0x180016db4  xor     eax, eax
0x180016db6  jmp     loc_180016E70
0x180016dbb  xor     edx, edx; lpFileSizeHigh
0x180016dbd  mov     rcx, rax; hFile
0x180016dc0  call    cs:__imp_GetFileSize
0x180016dc7  nop     dword ptr [rax+rax+00h]
0x180016dcc  mov     [rbx+18h], eax
0x180016dcf  mov     [rsp+48h+lpName], 0; lpName
0x180016dd8  lea     ecx, [rax+rsi]
0x180016ddb  mov     eax, edi
0x180016ddd  neg     eax
0x180016ddf  mov     [rsp+48h+dwMaximumSizeLow], ecx; dwMaximumSizeLow
0x180016de3  mov     rcx, [rbx]; hFile
0x180016de6  sbb     r8d, r8d
0x180016de9  xor     r9d, r9d; dwMaximumSizeHigh
0x180016dec  and     r8d, 0FFFFFFFEh
0x180016df0  xor     edx, edx; lpFileMappingAttributes
0x180016df2  add     r8d, 4; flProtect
0x180016df6  call    cs:__imp_CreateFileMappingW
0x180016dfd  nop     dword ptr [rax+rax+00h]
0x180016e02  mov     [rbx+8], rax
0x180016e06  test    rax, rax
0x180016e09  jnz     short loc_180016E1C
0x180016e0b  mov     rcx, [rbx]; hObject
0x180016e0e  call    cs:__imp_CloseHandle
0x180016e15  nop     dword ptr [rax+rax+00h]
0x180016e1a  jmp     short loc_180016DB4
0x180016e1c  neg     edi
0x180016e1e  mov     [rsp+48h+lpName], 0; lpBaseAddress
0x180016e27  mov     rcx, rax; hFileMappingObject
0x180016e2a  mov     qword ptr [rsp+48h+dwMaximumSizeLow], 0; dwNumberOfBytesToMap
0x180016e33  sbb     edx, edx
0x180016e35  xor     r9d, r9d; dwFileOffsetLow
0x180016e38  and     edx, 2
0x180016e3b  xor     r8d, r8d; dwFileOffsetHigh
0x180016e3e  add     edx, 2; dwDesiredAccess
0x180016e41  call    cs:__imp_MapViewOfFileEx
0x180016e48  nop     dword ptr [rax+rax+00h]
0x180016e4d  mov     [rbx+10h], rax
0x180016e51  test    rax, rax
0x180016e54  jnz     short loc_180016E6B
0x180016e56  mov     rcx, [rbx]; hObject
0x180016e59  call    cs:__imp_CloseHandle
0x180016e60  nop     dword ptr [rax+rax+00h]
0x180016e65  mov     rcx, [rbx+8]
0x180016e69  jmp     short loc_180016E0E
0x180016e6b  mov     eax, 1
0x180016e70  mov     rbx, [rsp+48h+arg_0]
0x180016e75  mov     rsi, [rsp+48h+arg_8]
0x180016e7a  add     rsp, 40h
0x180016e7e  pop     rdi
0x180016e7f  retn
```
