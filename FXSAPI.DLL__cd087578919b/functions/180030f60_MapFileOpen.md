# MapFileOpen

- ea: `0x180030f60`
- end: `0x180031091`
- name: `MapFileOpen`
- size: `305`
- prototype: `__int64 __fastcall(const WCHAR *, int, int, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180035d78`
- `0x180036b20`

## callees

- `0x1800308e0`
- `0x180030f60`

## import_xrefs

- `KERNEL32!GetFileSize` at `0x180030fd0`
- `KERNEL32!GetFileSize` at `0x180030fd0`
- `KERNEL32!CreateFileMappingW` at `0x180031006`
- `KERNEL32!CreateFileMappingW` at `0x180031006`
- `KERNEL32!MapViewOfFileEx` at `0x180031051`
- `KERNEL32!MapViewOfFileEx` at `0x180031051`
- `KERNEL32!CloseHandle` at `0x18003101e`
- `KERNEL32!CloseHandle` at `0x180031069`
- `KERNEL32!CloseHandle` at `0x18003101e`
- `KERNEL32!CloseHandle` at `0x180031069`

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
0x180030f60  mov     [rsp+arg_0], rbx
0x180030f65  mov     [rsp+arg_8], rsi
0x180030f6a  push    rdi
0x180030f6b  sub     rsp, 40h
0x180030f6f  mov     eax, edx
0x180030f71  mov     dword ptr [rsp+48h+lpName], 0; int
0x180030f79  mov     edi, edx
0x180030f7b  mov     qword ptr [r9], 0
0x180030f82  mov     esi, r8d
0x180030f85  mov     qword ptr [r9+8], 0
0x180030f8d  xor     r8d, r8d
0x180030f90  mov     qword ptr [r9+10h], 0
0x180030f98  test    edx, edx
0x180030f9a  mov     [rsp+48h+dwMaximumSizeLow], 3; DWORD
0x180030fa2  mov     rbx, r9
0x180030fa5  setnz   r8b; dwShareMode
0x180030fa9  neg     eax
0x180030fab  mov     eax, 0C0000000h
0x180030fb0  sbb     edx, edx
0x180030fb2  and     edx, eax
0x180030fb4  add     edx, eax; dwDesiredAccess
0x180030fb6  call    InternalSafeCreateFile
0x180030fbb  mov     [rbx], rax
0x180030fbe  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180030fc2  jnz     short loc_180030FCB
0x180030fc4  xor     eax, eax
0x180030fc6  jmp     loc_180031080
0x180030fcb  xor     edx, edx; lpFileSizeHigh
0x180030fcd  mov     rcx, rax; hFile
0x180030fd0  call    cs:__imp_GetFileSize
0x180030fd7  nop     dword ptr [rax+rax+00h]
0x180030fdc  mov     [rbx+18h], eax
0x180030fdf  mov     [rsp+48h+lpName], 0; lpName
0x180030fe8  lea     ecx, [rax+rsi]
0x180030feb  mov     eax, edi
0x180030fed  neg     eax
0x180030fef  mov     [rsp+48h+dwMaximumSizeLow], ecx; dwMaximumSizeLow
0x180030ff3  mov     rcx, [rbx]; hFile
0x180030ff6  sbb     r8d, r8d
0x180030ff9  xor     r9d, r9d; dwMaximumSizeHigh
0x180030ffc  and     r8d, 0FFFFFFFEh
0x180031000  xor     edx, edx; lpFileMappingAttributes
0x180031002  add     r8d, 4; flProtect
0x180031006  call    cs:__imp_CreateFileMappingW
0x18003100d  nop     dword ptr [rax+rax+00h]
0x180031012  mov     [rbx+8], rax
0x180031016  test    rax, rax
0x180031019  jnz     short loc_18003102C
0x18003101b  mov     rcx, [rbx]; hObject
0x18003101e  call    cs:__imp_CloseHandle
0x180031025  nop     dword ptr [rax+rax+00h]
0x18003102a  jmp     short loc_180030FC4
0x18003102c  neg     edi
0x18003102e  mov     [rsp+48h+lpName], 0; lpBaseAddress
0x180031037  mov     rcx, rax; hFileMappingObject
0x18003103a  mov     qword ptr [rsp+48h+dwMaximumSizeLow], 0; dwNumberOfBytesToMap
0x180031043  sbb     edx, edx
0x180031045  xor     r9d, r9d; dwFileOffsetLow
0x180031048  and     edx, 2
0x18003104b  xor     r8d, r8d; dwFileOffsetHigh
0x18003104e  add     edx, 2; dwDesiredAccess
0x180031051  call    cs:__imp_MapViewOfFileEx
0x180031058  nop     dword ptr [rax+rax+00h]
0x18003105d  mov     [rbx+10h], rax
0x180031061  test    rax, rax
0x180031064  jnz     short loc_18003107B
0x180031066  mov     rcx, [rbx]; hObject
0x180031069  call    cs:__imp_CloseHandle
0x180031070  nop     dword ptr [rax+rax+00h]
0x180031075  mov     rcx, [rbx+8]
0x180031079  jmp     short loc_18003101E
0x18003107b  mov     eax, 1
0x180031080  mov     rbx, [rsp+48h+arg_0]
0x180031085  mov     rsi, [rsp+48h+arg_8]
0x18003108a  add     rsp, 40h
0x18003108e  pop     rdi
0x18003108f  retn
```
