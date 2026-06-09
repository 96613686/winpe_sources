# D3DXCore::CFile::Open(void const *,int)

- ea: `0x1400aae30`
- end: `0x1400aaf10`
- name: `?Open@CFile@D3DXCore@@QEAAJPEBXH@Z`
- size: `224`
- prototype: `int(D3DXCore::CFile *__hidden this, const void *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140098694`

## callees

- `0x140001abc`
- `0x1400aae30`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400aaef3`
- `KERNEL32!GetLastError` at `0x1400aaef3`
- `KERNEL32!GetFileSize` at `0x1400aaebb`
- `KERNEL32!GetFileSize` at `0x1400aaebb`
- `KERNEL32!CreateFileMappingA` at `0x1400aaea6`
- `KERNEL32!CreateFileMappingA` at `0x1400aaea6`
- `KERNEL32!CreateFileA` at `0x1400aae73`
- `KERNEL32!CreateFileA` at `0x1400aae73`
- `KERNEL32!MapViewOfFile` at `0x1400aaee4`
- `KERNEL32!MapViewOfFile` at `0x1400aaee4`

## pseudocode

```c
__int64 __fastcall D3DXCore::CFile::Open(HANDLE *this, const CHAR *a2)
{
  HANDLE FileMappingA; // rax
  DWORD FileSize; // eax
  LPVOID v6; // rax

  if ( !a2 )
    return 2289436780LL;
  *this = CreateFileA(a2, 0x80000000, 1u, 0, 3u, 0x10000000u, 0);
  operator delete(0);
  if ( *this == (HANDLE)-1LL )
    goto LABEL_8;
  FileMappingA = CreateFileMappingA(*this, 0, 2u, 0, 0, 0);
  this[1] = FileMappingA;
  if ( FileMappingA == (HANDLE)-1LL )
    goto LABEL_8;
  FileSize = GetFileSize(*this, 0);
  *((_DWORD *)this + 6) = FileSize;
  if ( FileSize == -1 )
    goto LABEL_8;
  if ( FileSize )
  {
    v6 = MapViewOfFile(this[1], 4u, 0, 0, 0);
    this[2] = v6;
    if ( !v6 )
    {
LABEL_8:
      GetLastError();
      return 2289437529LL;
    }
  }
  else
  {
    this[2] = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x1400aae30  push    rbx
0x1400aae32  sub     rsp, 40h
0x1400aae36  mov     rax, rdx
0x1400aae39  mov     rbx, rcx
0x1400aae3c  test    rdx, rdx
0x1400aae3f  jnz     short loc_1400AAE4B
0x1400aae41  mov     eax, 8876086Ch
0x1400aae46  jmp     loc_1400AAEFE
0x1400aae4b  xor     r9d, r9d; lpSecurityAttributes
0x1400aae4e  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x1400aae57  mov     [rsp+48h+dwFlagsAndAttributes], 10000000h; dwFlagsAndAttributes
0x1400aae5f  mov     edx, 80000000h; dwDesiredAccess
0x1400aae64  mov     rcx, rax; lpFileName
0x1400aae67  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x1400aae6f  lea     r8d, [r9+1]; dwShareMode
0x1400aae73  call    cs:__imp_CreateFileA
0x1400aae79  xor     ecx, ecx; Block
0x1400aae7b  mov     [rbx], rax
0x1400aae7e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400aae83  cmp     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x1400aae87  jz      short loc_1400AAEF3
0x1400aae89  mov     rcx, [rbx]; hFile
0x1400aae8c  xor     r9d, r9d; dwMaximumSizeHigh
0x1400aae8f  mov     qword ptr [rsp+48h+dwFlagsAndAttributes], 0; lpName
0x1400aae98  xor     edx, edx; lpFileMappingAttributes
0x1400aae9a  mov     [rsp+48h+dwCreationDisposition], 0; dwMaximumSizeLow
0x1400aaea2  lea     r8d, [r9+2]; flProtect
0x1400aaea6  call    cs:__imp_CreateFileMappingA
0x1400aaeac  mov     [rbx+8], rax
0x1400aaeb0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400aaeb4  jz      short loc_1400AAEF3
0x1400aaeb6  mov     rcx, [rbx]; hFile
0x1400aaeb9  xor     edx, edx; lpFileSizeHigh
0x1400aaebb  call    cs:__imp_GetFileSize
0x1400aaec1  mov     [rbx+18h], eax
0x1400aaec4  cmp     eax, 0FFFFFFFFh
0x1400aaec7  jz      short loc_1400AAEF3
0x1400aaec9  test    eax, eax
0x1400aaecb  jz      short loc_1400AAF04
0x1400aaecd  mov     rcx, [rbx+8]; hFileMappingObject
0x1400aaed1  xor     r9d, r9d; dwFileOffsetLow
0x1400aaed4  xor     r8d, r8d; dwFileOffsetHigh
0x1400aaed7  mov     qword ptr [rsp+48h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x1400aaee0  lea     edx, [r9+4]; dwDesiredAccess
0x1400aaee4  call    cs:__imp_MapViewOfFile
0x1400aaeea  mov     [rbx+10h], rax
0x1400aaeee  test    rax, rax
0x1400aaef1  jnz     short loc_1400AAF0C
0x1400aaef3  call    cs:__imp_GetLastError
0x1400aaef9  mov     eax, 88760B59h
0x1400aaefe  add     rsp, 40h
0x1400aaf02  pop     rbx
0x1400aaf03  retn
0x1400aaf04  mov     qword ptr [rbx+10h], 0
0x1400aaf0c  xor     eax, eax
0x1400aaf0e  jmp     short loc_1400AAEFE
```
