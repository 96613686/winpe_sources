# __std_fs_open_handle

- ea: `0x180002390`
- end: `0x1800023e7`
- name: `__std_fs_open_handle`
- size: `87`
- prototype: `__int64 __fastcall(_QWORD *, const WCHAR *, DWORD, DWORD dwFlagsAndAttributes)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002018`

## callees

- `0x180002390`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800023d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800023d2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800023c3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800023c3`

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
0x180002390  mov     [rsp+arg_0], rbx
0x180002395  push    rdi
0x180002396  sub     rsp, 40h
0x18000239a  mov     eax, r8d
0x18000239d  mov     r10, rdx
0x1800023a0  xor     edi, edi
0x1800023a2  mov     rbx, rcx
0x1800023a5  mov     [rsp+48h+hTemplateFile], rdi; hTemplateFile
0x1800023aa  mov     edx, eax; dwDesiredAccess
0x1800023ac  mov     [rsp+48h+dwFlagsAndAttributes], r9d; dwFlagsAndAttributes
0x1800023b1  mov     rcx, r10; lpFileName
0x1800023b4  xor     r9d, r9d; lpSecurityAttributes
0x1800023b7  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x1800023bf  lea     r8d, [rdi+7]; dwShareMode
0x1800023c3  call    cs:__imp_CreateFileW
0x1800023c9  mov     [rbx], rax
0x1800023cc  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800023d0  jnz     short loc_1800023DA
0x1800023d2  call    cs:__imp_GetLastError
0x1800023d8  mov     edi, eax
0x1800023da  mov     rbx, [rsp+48h+arg_0]
0x1800023df  mov     eax, edi
0x1800023e1  add     rsp, 40h
0x1800023e5  pop     rdi
0x1800023e6  retn
```
