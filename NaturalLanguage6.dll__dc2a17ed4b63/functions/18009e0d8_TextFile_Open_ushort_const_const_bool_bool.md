# TextFile::Open(ushort const * const,bool,bool)

- ea: `0x18009e0d8`
- end: `0x18009e140`
- name: `?Open@TextFile@@QEAA_NQEBG_N1@Z`
- size: `104`
- prototype: `bool __fastcall(TextFile *__hidden this, LPCWSTR lpFileName, bool, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180072a4c`

## callees

- `0x18009dfcc`
- `0x18009e0d8`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18009e113`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18009e113`

## pseudocode

```c
char __fastcall TextFile::Open(TextFile *this, LPCWSTR lpFileName, char a3)
{
  char *FileW; // rax

  FileW = (char *)CreateFileW(lpFileName, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    return 0;
  else
    return TextFile::Open(this, FileW, a3);
}

```

## disassembly

```asm
0x18009e0d8  mov     [rsp+arg_0], rbx
0x18009e0dd  push    rdi
0x18009e0de  sub     rsp, 40h
0x18009e0e2  mov     rax, rdx
0x18009e0e5  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x18009e0ee  xor     r9d, r9d; lpSecurityAttributes
0x18009e0f1  mov     [rsp+48h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18009e0f9  mov     bl, r8b
0x18009e0fc  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x18009e104  mov     rdi, rcx
0x18009e107  mov     edx, 80000000h; dwDesiredAccess
0x18009e10c  mov     rcx, rax; lpFileName
0x18009e10f  lea     r8d, [r9+1]; dwShareMode
0x18009e113  call    cs:__imp_CreateFileW
0x18009e119  lea     rdx, [rax-1]
0x18009e11d  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18009e121  ja      short loc_18009E133
0x18009e123  mov     r8b, bl; bool
0x18009e126  mov     rdx, rax; hFile
0x18009e129  mov     rcx, rdi; this
0x18009e12c  call    ?Open@TextFile@@QEAA_NPEAX_N@Z; TextFile::Open(void *,bool)
0x18009e131  jmp     short loc_18009E135
0x18009e133  xor     al, al
0x18009e135  mov     rbx, [rsp+48h+arg_0]
0x18009e13a  add     rsp, 40h
0x18009e13e  pop     rdi
0x18009e13f  retn
```
