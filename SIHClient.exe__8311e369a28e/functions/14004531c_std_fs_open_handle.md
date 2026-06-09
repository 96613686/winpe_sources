# __std_fs_open_handle

- ea: `0x14004531c`
- end: `0x140045373`
- name: `__std_fs_open_handle`
- size: `87`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140045468`

## callees

- `0x14004531c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004535e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004535e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14004534f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14004534f`

## pseudocode

```c
__int64 __fastcall _std_fs_open_handle(_QWORD *a1, const WCHAR *a2, __int64 a3, DWORD dwFlagsAndAttributes)
{
  unsigned int v4; // edi
  HANDLE FileW; // rax

  v4 = 0;
  FileW = CreateFileW(a2, 0x80u, 7u, 0, 3u, dwFlagsAndAttributes, 0);
  *a1 = FileW;
  if ( FileW == (HANDLE)-1LL )
    return GetLastError();
  return v4;
}

```

## disassembly

```asm
0x14004531c  mov     [rsp+arg_0], rbx
0x140045321  push    rdi
0x140045322  sub     rsp, 40h
0x140045326  mov     rax, rdx
0x140045329  xor     edi, edi
0x14004532b  mov     [rsp+48h+hTemplateFile], rdi; hTemplateFile
0x140045330  mov     rbx, rcx
0x140045333  mov     [rsp+48h+dwFlagsAndAttributes], r9d; dwFlagsAndAttributes
0x140045338  mov     edx, 80h; dwDesiredAccess
0x14004533d  xor     r9d, r9d; lpSecurityAttributes
0x140045340  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x140045348  lea     r8d, [rdi+7]; dwShareMode
0x14004534c  mov     rcx, rax; lpFileName
0x14004534f  call    cs:__imp_CreateFileW
0x140045355  mov     [rbx], rax
0x140045358  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14004535c  jnz     short loc_140045366
0x14004535e  call    cs:__imp_GetLastError
0x140045364  mov     edi, eax
0x140045366  mov     rbx, [rsp+48h+arg_0]
0x14004536b  mov     eax, edi
0x14004536d  add     rsp, 40h
0x140045371  pop     rdi
0x140045372  retn
```
