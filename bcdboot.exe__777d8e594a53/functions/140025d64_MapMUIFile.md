# MapMUIFile

- ea: `0x140025d64`
- end: `0x140025e48`
- name: `MapMUIFile`
- size: `228`
- prototype: `HMODULE __fastcall(const WCHAR *, int, int)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x140025f28`
- `0x140026010`

## callees

- `0x140025d64`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x140025da7`
- `KERNEL32!CreateFileW` at `0x140025da7`
- `KERNEL32!CloseHandle` at `0x140025de3`
- `KERNEL32!CloseHandle` at `0x140025e10`
- `KERNEL32!CloseHandle` at `0x140025de3`
- `KERNEL32!CloseHandle` at `0x140025e10`
- `KERNEL32!CreateFileMappingW` at `0x140025dd7`
- `KERNEL32!CreateFileMappingW` at `0x140025dd7`
- `KERNEL32!MapViewOfFile` at `0x140025e04`
- `KERNEL32!MapViewOfFile` at `0x140025e04`
- `KERNEL32!LoadLibraryExW` at `0x140025e33`
- `KERNEL32!LoadLibraryExW` at `0x140025e33`

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
0x140025d64  mov     [rsp+arg_0], rbx
0x140025d69  push    rdi
0x140025d6a  sub     rsp, 40h
0x140025d6e  mov     eax, r8d
0x140025d71  test    rcx, rcx
0x140025d74  jz      loc_140025E3B
0x140025d7a  test    edx, edx
0x140025d7c  jz      loc_140025E28
0x140025d82  xor     r9d, r9d; lpSecurityAttributes
0x140025d85  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x140025d8e  mov     [rsp+48h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x140025d96  mov     edx, 80000000h; dwDesiredAccess
0x140025d9b  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x140025da3  lea     r8d, [r9+5]; dwShareMode
0x140025da7  call    cs:__imp_CreateFileW
0x140025dad  mov     rbx, rax
0x140025db0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140025db4  jz      loc_140025E3B
0x140025dba  xor     r9d, r9d; dwMaximumSizeHigh
0x140025dbd  mov     qword ptr [rsp+48h+dwFlagsAndAttributes], 0; lpName
0x140025dc6  xor     edx, edx; lpFileMappingAttributes
0x140025dc8  mov     [rsp+48h+dwCreationDisposition], 0; dwMaximumSizeLow
0x140025dd0  mov     rcx, rax; hFile
0x140025dd3  lea     r8d, [r9+8]; flProtect
0x140025dd7  call    cs:__imp_CreateFileMappingW
0x140025ddd  mov     rcx, rbx; hObject
0x140025de0  mov     rdi, rax
0x140025de3  call    cs:__imp_CloseHandle
0x140025de9  test    rdi, rdi
0x140025dec  jz      short loc_140025E3B
0x140025dee  xor     r9d, r9d; dwFileOffsetLow
0x140025df1  mov     qword ptr [rsp+48h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x140025dfa  xor     r8d, r8d; dwFileOffsetHigh
0x140025dfd  mov     rcx, rdi; hFileMappingObject
0x140025e00  lea     edx, [r9+1]; dwDesiredAccess
0x140025e04  call    cs:__imp_MapViewOfFile
0x140025e0a  mov     rcx, rdi; hObject
0x140025e0d  mov     rbx, rax
0x140025e10  call    cs:__imp_CloseHandle
0x140025e16  mov     rcx, rbx
0x140025e19  or      rcx, 1; lpLibFileName
0x140025e1d  neg     rbx
0x140025e20  sbb     rax, rax
0x140025e23  and     rax, rcx
0x140025e26  jmp     short loc_140025E3D
0x140025e28  xor     r8d, r8d
0x140025e2b  test    eax, eax
0x140025e2d  setnz   r8b; dwFlags
0x140025e31  xor     edx, edx; hFile
0x140025e33  call    cs:__imp_LoadLibraryExW
0x140025e39  jmp     short loc_140025E3D
0x140025e3b  xor     eax, eax
0x140025e3d  mov     rbx, [rsp+48h+arg_0]
0x140025e42  add     rsp, 40h
0x140025e46  pop     rdi
0x140025e47  retn
```
