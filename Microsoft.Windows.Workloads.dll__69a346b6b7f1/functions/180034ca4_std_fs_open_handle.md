# __std_fs_open_handle

- ea: `0x180034ca4`
- end: `0x180034cfb`
- name: `__std_fs_open_handle`
- size: `87`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180034974`

## callees

- `0x180034ca4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180034ce6`
- `KERNEL32!GetLastError` at `0x180034ce6`
- `KERNEL32!CreateFileW` at `0x180034cd7`
- `KERNEL32!CreateFileW` at `0x180034cd7`

## pseudocode

```c
__int64 __fastcall _std_fs_open_handle(_QWORD *a1, const WCHAR *a2, DWORD a3, DWORD dwFlagsAndAttributes)
{
  unsigned int v4; // edi
  HANDLE FileW; // rax

  v4 = 0;
  FileW = CreateFileW(a2, a3, 7u, 0, 3u, dwFlagsAndAttributes, 0);
  *a1 = FileW;
  if ( FileW == (HANDLE)-1LL )
    return GetLastError();
  return v4;
}

```

## disassembly

```asm
0x180034ca4  mov     [rsp+arg_0], rbx
0x180034ca9  push    rdi
0x180034caa  sub     rsp, 40h
0x180034cae  mov     eax, r8d
0x180034cb1  mov     r10, rdx
0x180034cb4  xor     edi, edi
0x180034cb6  mov     rbx, rcx
0x180034cb9  mov     [rsp+48h+hTemplateFile], rdi; hTemplateFile
0x180034cbe  mov     edx, eax; dwDesiredAccess
0x180034cc0  mov     [rsp+48h+dwFlagsAndAttributes], r9d; dwFlagsAndAttributes
0x180034cc5  mov     rcx, r10; lpFileName
0x180034cc8  xor     r9d, r9d; lpSecurityAttributes
0x180034ccb  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x180034cd3  lea     r8d, [rdi+7]; dwShareMode
0x180034cd7  call    cs:__imp_CreateFileW
0x180034cdd  mov     [rbx], rax
0x180034ce0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180034ce4  jnz     short loc_180034CEE
0x180034ce6  call    cs:__imp_GetLastError
0x180034cec  mov     edi, eax
0x180034cee  mov     rbx, [rsp+48h+arg_0]
0x180034cf3  mov     eax, edi
0x180034cf5  add     rsp, 40h
0x180034cf9  pop     rdi
0x180034cfa  retn
```
