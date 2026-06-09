# CFile::Open(ushort const *,bool)

- ea: `0x180002d40`
- end: `0x180002d9a`
- name: `?Open@CFile@@QEAA_NPEBG_N@Z`
- size: `90`
- prototype: `bool __fastcall(CFile *this, const unsigned __int16 *, unsigned __int8)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002150`
- `0x180002cf0`

## callees

- `0x180002d40`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x180002d7f`
- `KERNEL32!CreateFileW` at `0x180002d7f`

## pseudocode

```c
bool __fastcall CFile::Open(CFile *this, const unsigned __int16 *a2, unsigned __int8 a3)
{
  char *FileW; // rax

  if ( *((_QWORD *)this + 1) != -1 )
    return 1;
  FileW = (char *)CreateFileW(a2, ((unsigned int)a3 + 2) << 30, 3u, 0, 3u, 0x10000000u, 0);
  *((_QWORD *)this + 1) = FileW;
  return FileW + 1 != 0;
}

```

## disassembly

```asm
0x180002d40  push    rbx
0x180002d42  sub     rsp, 40h
0x180002d46  cmp     qword ptr [rcx+8], 0FFFFFFFFFFFFFFFFh
0x180002d4b  mov     rax, rdx
0x180002d4e  mov     rbx, rcx
0x180002d51  jnz     short loc_180002D92
0x180002d53  movzx   edx, r8b
0x180002d57  xor     r9d, r9d; lpSecurityAttributes
0x180002d5a  add     edx, 2
0x180002d5d  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x180002d66  mov     r8d, 3; dwShareMode
0x180002d6c  shl     edx, 1Eh; dwDesiredAccess
0x180002d6f  mov     [rsp+48h+dwFlagsAndAttributes], 10000000h; dwFlagsAndAttributes
0x180002d77  mov     rcx, rax; lpFileName
0x180002d7a  mov     [rsp+48h+dwCreationDisposition], r8d; dwCreationDisposition
0x180002d7f  call    cs:__imp_CreateFileW
0x180002d85  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180002d89  mov     [rbx+8], rax
0x180002d8d  setnz   al
0x180002d90  jmp     short loc_180002D94
0x180002d92  mov     al, 1
0x180002d94  add     rsp, 40h
0x180002d98  pop     rbx
0x180002d99  retn
```
