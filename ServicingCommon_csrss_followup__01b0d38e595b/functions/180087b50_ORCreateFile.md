# ORCreateFile

- ea: `0x180087b50`
- end: `0x180087ba3`
- name: `ORCreateFile`
- size: `83`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18008552c`
- `0x180087778`

## callees

- `0x180087b50`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180087b8c`
- `KERNEL32!GetLastError` at `0x180087b8c`
- `KERNEL32!CreateFileW` at `0x180087b6f`
- `KERNEL32!CreateFileW` at `0x180087b6f`

## pseudocode

```c
__int64 __fastcall ORCreateFile(const WCHAR *a1, DWORD a2, __int64 a3, DWORD a4, _QWORD *a5)
{
  unsigned int v5; // ebx
  HANDLE FileW; // rcx

  v5 = 0;
  FileW = CreateFileW(a1, a2, a4, 0, 3u, 0, 0);
  *a5 = FileW;
  if ( FileW == (HANDLE)-1LL )
    return GetLastError();
  return v5;
}

```

## disassembly

```asm
0x180087b50  push    rbx
0x180087b52  sub     rsp, 40h
0x180087b56  xor     ebx, ebx
0x180087b58  mov     r8d, r9d; dwShareMode
0x180087b5b  mov     [rsp+48h+hTemplateFile], rbx; hTemplateFile
0x180087b60  xor     r9d, r9d; lpSecurityAttributes
0x180087b63  mov     [rsp+48h+dwFlagsAndAttributes], ebx; dwFlagsAndAttributes
0x180087b67  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x180087b6f  call    cs:__imp_CreateFileW
0x180087b76  nop     dword ptr [rax+rax+00h]
0x180087b7b  mov     rcx, rax
0x180087b7e  mov     rax, [rsp+48h+arg_20]
0x180087b83  mov     [rax], rcx
0x180087b86  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180087b8a  jnz     short loc_180087B9A
0x180087b8c  call    cs:__imp_GetLastError
0x180087b93  nop     dword ptr [rax+rax+00h]
0x180087b98  mov     ebx, eax
0x180087b9a  mov     eax, ebx
0x180087b9c  add     rsp, 40h
0x180087ba0  pop     rbx
0x180087ba1  retn
```
