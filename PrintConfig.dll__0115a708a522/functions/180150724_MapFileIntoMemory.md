# MapFileIntoMemory

- ea: `0x180150724`
- end: `0x18015084e`
- name: `MapFileIntoMemory`
- size: `298`
- prototype: `__int64 __fastcall(const WCHAR *, __int64, DWORD *, HANDLE *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1801b4e88`

## callees

- `0x180150724`

## import_xrefs

- `KERNEL32!CreateFileMappingW` at `0x1801507c4`
- `KERNEL32!CreateFileMappingW` at `0x1801507c4`
- `KERNEL32!MapViewOfFile` at `0x1801507ee`
- `KERNEL32!MapViewOfFile` at `0x1801507ee`
- `KERNEL32!GetFileSize` at `0x180150794`
- `KERNEL32!GetFileSize` at `0x180150794`
- `KERNEL32!CreateFileW` at `0x180150771`
- `KERNEL32!CreateFileW` at `0x180150771`
- `KERNEL32!CloseHandle` at `0x180150800`
- `KERNEL32!CloseHandle` at `0x18015081b`
- `KERNEL32!CloseHandle` at `0x180150800`
- `KERNEL32!CloseHandle` at `0x18015081b`

## pseudocode

```c
__int64 __fastcall MapFileIntoMemory(const WCHAR *a1, __int64 a2, DWORD *a3, HANDLE *a4)
{
  HANDLE FileW; // rax
  DWORD FileSize; // eax
  HANDLE FileMappingW; // rax
  void *v10; // rsi

  if ( !a4 )
  {
LABEL_10:
    if ( a2 )
      *(_QWORD *)a2 = 0;
    return *(_QWORD *)a2;
  }
  if ( !a2 )
    goto LABEL_8;
  FileW = CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0x100080u, 0);
  *a4 = FileW;
  if ( FileW == (HANDLE)-1LL )
    goto LABEL_8;
  if ( a3 )
  {
    FileSize = GetFileSize(FileW, 0);
    *a3 = FileSize;
    if ( FileSize == -1 )
      goto LABEL_8;
  }
  FileMappingW = CreateFileMappingW(*a4, 0, 2u, 0, 0, 0);
  v10 = FileMappingW;
  if ( !FileMappingW || (*(_QWORD *)a2 = MapViewOfFile(FileMappingW, 4u, 0, 0, 0), CloseHandle(v10), !*(_QWORD *)a2) )
  {
LABEL_8:
    if ( *a4 != (HANDLE)-1LL )
    {
      CloseHandle(*a4);
      *a4 = (HANDLE)-1LL;
    }
    goto LABEL_10;
  }
  return *(_QWORD *)a2;
}

```

## disassembly

```asm
0x180150724  mov     rax, rsp
0x180150727  mov     [rax+8], rbx
0x18015072b  mov     [rax+10h], rsi
0x18015072f  push    rdi
0x180150730  sub     rsp, 40h
0x180150734  mov     rdi, r9
0x180150737  mov     rsi, r8
0x18015073a  mov     rbx, rdx
0x18015073d  test    r9, r9
0x180150740  jz      loc_18015082E
0x180150746  test    rdx, rdx
0x180150749  jz      loc_180150812
0x18015074f  mov     qword ptr [rax-18h], 0
0x180150757  xor     r9d, r9d; lpSecurityAttributes
0x18015075a  mov     dword ptr [rax-20h], 100080h
0x180150761  mov     edx, 80000000h; dwDesiredAccess
0x180150766  mov     dword ptr [rax-28h], 3
0x18015076d  lea     r8d, [r9+1]; dwShareMode
0x180150771  call    cs:__imp_CreateFileW
0x180150778  nop     dword ptr [rax+rax+00h]
0x18015077d  mov     [rdi], rax
0x180150780  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180150784  jz      loc_180150812
0x18015078a  test    rsi, rsi
0x18015078d  jz      short loc_1801507A7
0x18015078f  xor     edx, edx; lpFileSizeHigh
0x180150791  mov     rcx, rax; hFile
0x180150794  call    cs:__imp_GetFileSize
0x18015079b  nop     dword ptr [rax+rax+00h]
0x1801507a0  mov     [rsi], eax
0x1801507a2  cmp     eax, 0FFFFFFFFh
0x1801507a5  jz      short loc_180150812
0x1801507a7  mov     rcx, [rdi]; hFile
0x1801507aa  xor     r9d, r9d; dwMaximumSizeHigh
0x1801507ad  mov     [rsp+48h+lpName], 0; lpName
0x1801507b6  xor     edx, edx; lpFileMappingAttributes
0x1801507b8  mov     [rsp+48h+dwMaximumSizeLow], 0; dwMaximumSizeLow
0x1801507c0  lea     r8d, [r9+2]; flProtect
0x1801507c4  call    cs:__imp_CreateFileMappingW
0x1801507cb  nop     dword ptr [rax+rax+00h]
0x1801507d0  mov     rsi, rax
0x1801507d3  test    rax, rax
0x1801507d6  jz      short loc_180150812
0x1801507d8  xor     r9d, r9d; dwFileOffsetLow
0x1801507db  mov     qword ptr [rsp+48h+dwMaximumSizeLow], 0; dwNumberOfBytesToMap
0x1801507e4  xor     r8d, r8d; dwFileOffsetHigh
0x1801507e7  mov     rcx, rax; hFileMappingObject
0x1801507ea  lea     edx, [r9+4]; dwDesiredAccess
0x1801507ee  call    cs:__imp_MapViewOfFile
0x1801507f5  nop     dword ptr [rax+rax+00h]
0x1801507fa  mov     rcx, rsi; hObject
0x1801507fd  mov     [rbx], rax
0x180150800  call    cs:__imp_CloseHandle
0x180150807  nop     dword ptr [rax+rax+00h]
0x18015080c  cmp     qword ptr [rbx], 0
0x180150810  jnz     short loc_18015083A
0x180150812  cmp     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x180150816  jz      short loc_18015082E
0x180150818  mov     rcx, [rdi]; hObject
0x18015081b  call    cs:__imp_CloseHandle
0x180150822  nop     dword ptr [rax+rax+00h]
0x180150827  mov     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x18015082e  test    rbx, rbx
0x180150831  jz      short loc_18015083A
0x180150833  mov     qword ptr [rbx], 0
0x18015083a  mov     rax, [rbx]
0x18015083d  mov     rbx, [rsp+48h+arg_0]
0x180150842  mov     rsi, [rsp+48h+arg_8]
0x180150847  add     rsp, 40h
0x18015084b  pop     rdi
0x18015084c  retn
```
