# __std_fs_open_handle

- ea: `0x18000dd34`
- end: `0x18000dd8b`
- name: `__std_fs_open_handle`
- size: `87`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000de80`

## callees

- `0x18000dd34`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dd76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dd76`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000dd67`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000dd67`

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
0x18000dd34  mov     [rsp+arg_0], rbx
0x18000dd39  push    rdi
0x18000dd3a  sub     rsp, 40h
0x18000dd3e  mov     rax, rdx
0x18000dd41  xor     edi, edi
0x18000dd43  mov     [rsp+48h+hTemplateFile], rdi; hTemplateFile
0x18000dd48  mov     rbx, rcx
0x18000dd4b  mov     [rsp+48h+dwFlagsAndAttributes], r9d; dwFlagsAndAttributes
0x18000dd50  mov     edx, 80h; dwDesiredAccess
0x18000dd55  xor     r9d, r9d; lpSecurityAttributes
0x18000dd58  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x18000dd60  lea     r8d, [rdi+7]; dwShareMode
0x18000dd64  mov     rcx, rax; lpFileName
0x18000dd67  call    cs:__imp_CreateFileW
0x18000dd6d  mov     [rbx], rax
0x18000dd70  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000dd74  jnz     short loc_18000DD7E
0x18000dd76  call    cs:__imp_GetLastError
0x18000dd7c  mov     edi, eax
0x18000dd7e  mov     rbx, [rsp+48h+arg_0]
0x18000dd83  mov     eax, edi
0x18000dd85  add     rsp, 40h
0x18000dd89  pop     rdi
0x18000dd8a  retn
```
