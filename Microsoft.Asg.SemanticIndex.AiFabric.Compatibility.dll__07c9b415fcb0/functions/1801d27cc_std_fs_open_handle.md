# __std_fs_open_handle

- ea: `0x1801d27cc`
- end: `0x1801d2823`
- name: `__std_fs_open_handle`
- size: `87`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1801d249c`
- `0x1801d2824`

## callees

- `0x1801d27cc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1801d280e`
- `KERNEL32!GetLastError` at `0x1801d280e`
- `KERNEL32!CreateFileW` at `0x1801d27ff`
- `KERNEL32!CreateFileW` at `0x1801d27ff`

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
0x1801d27cc  mov     [rsp+arg_0], rbx
0x1801d27d1  push    rdi
0x1801d27d2  sub     rsp, 40h
0x1801d27d6  mov     eax, r8d
0x1801d27d9  mov     r10, rdx
0x1801d27dc  xor     edi, edi
0x1801d27de  mov     rbx, rcx
0x1801d27e1  mov     [rsp+48h+hTemplateFile], rdi; hTemplateFile
0x1801d27e6  mov     edx, eax; dwDesiredAccess
0x1801d27e8  mov     [rsp+48h+dwFlagsAndAttributes], r9d; dwFlagsAndAttributes
0x1801d27ed  mov     rcx, r10; lpFileName
0x1801d27f0  xor     r9d, r9d; lpSecurityAttributes
0x1801d27f3  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x1801d27fb  lea     r8d, [rdi+7]; dwShareMode
0x1801d27ff  call    cs:__imp_CreateFileW
0x1801d2805  mov     [rbx], rax
0x1801d2808  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801d280c  jnz     short loc_1801D2816
0x1801d280e  call    cs:__imp_GetLastError
0x1801d2814  mov     edi, eax
0x1801d2816  mov     rbx, [rsp+48h+arg_0]
0x1801d281b  mov     eax, edi
0x1801d281d  add     rsp, 40h
0x1801d2821  pop     rdi
0x1801d2822  retn
```
