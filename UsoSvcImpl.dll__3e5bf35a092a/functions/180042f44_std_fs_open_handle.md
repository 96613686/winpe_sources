# __std_fs_open_handle

- ea: `0x180042f44`
- end: `0x180042f9b`
- name: `__std_fs_open_handle`
- size: `87`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180043090`
- `0x180043328`

## callees

- `0x180042f44`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042f86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042f86`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180042f77`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180042f77`

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
0x180042f44  mov     [rsp+arg_0], rbx
0x180042f49  push    rdi
0x180042f4a  sub     rsp, 40h
0x180042f4e  mov     eax, r8d
0x180042f51  mov     r10, rdx
0x180042f54  xor     edi, edi
0x180042f56  mov     rbx, rcx
0x180042f59  mov     [rsp+48h+hTemplateFile], rdi; hTemplateFile
0x180042f5e  mov     edx, eax; dwDesiredAccess
0x180042f60  mov     [rsp+48h+dwFlagsAndAttributes], r9d; dwFlagsAndAttributes
0x180042f65  mov     rcx, r10; lpFileName
0x180042f68  xor     r9d, r9d; lpSecurityAttributes
0x180042f6b  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x180042f73  lea     r8d, [rdi+7]; dwShareMode
0x180042f77  call    cs:__imp_CreateFileW
0x180042f7d  mov     [rbx], rax
0x180042f80  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180042f84  jnz     short loc_180042F8E
0x180042f86  call    cs:__imp_GetLastError
0x180042f8c  mov     edi, eax
0x180042f8e  mov     rbx, [rsp+48h+arg_0]
0x180042f93  mov     eax, edi
0x180042f95  add     rsp, 40h
0x180042f99  pop     rdi
0x180042f9a  retn
```
