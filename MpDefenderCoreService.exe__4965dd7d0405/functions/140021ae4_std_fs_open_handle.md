# __std_fs_open_handle

- ea: `0x140021ae4`
- end: `0x140021b3b`
- name: `__std_fs_open_handle`
- size: `87`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1400217b4`

## callees

- `0x140021ae4`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x140021b17`
- `KERNEL32!CreateFileW` at `0x140021b17`
- `KERNEL32!GetLastError` at `0x140021b26`
- `KERNEL32!GetLastError` at `0x140021b26`

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
0x140021ae4  mov     [rsp+arg_0], rbx
0x140021ae9  push    rdi
0x140021aea  sub     rsp, 40h
0x140021aee  mov     eax, r8d
0x140021af1  mov     r10, rdx
0x140021af4  xor     edi, edi
0x140021af6  mov     rbx, rcx
0x140021af9  mov     [rsp+48h+hTemplateFile], rdi; hTemplateFile
0x140021afe  mov     edx, eax; dwDesiredAccess
0x140021b00  mov     [rsp+48h+dwFlagsAndAttributes], r9d; dwFlagsAndAttributes
0x140021b05  mov     rcx, r10; lpFileName
0x140021b08  xor     r9d, r9d; lpSecurityAttributes
0x140021b0b  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x140021b13  lea     r8d, [rdi+7]; dwShareMode
0x140021b17  call    cs:__imp_CreateFileW
0x140021b1d  mov     [rbx], rax
0x140021b20  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140021b24  jnz     short loc_140021B2E
0x140021b26  call    cs:__imp_GetLastError
0x140021b2c  mov     edi, eax
0x140021b2e  mov     rbx, [rsp+48h+arg_0]
0x140021b33  mov     eax, edi
0x140021b35  add     rsp, 40h
0x140021b39  pop     rdi
0x140021b3a  retn
```
