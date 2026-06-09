# __std_fs_open_handle

- ea: `0x180001cd8`
- end: `0x180001d2b`
- name: `__std_fs_open_handle`
- size: `83`
- prototype: `DWORD __fastcall(__int64 *, int, int, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000194c`

## callees

- `0x1800017f4`
- `0x180001cd8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001d24`

## pseudocode

```c
DWORD __fastcall _std_fs_open_handle(__int64 *a1, int a2, int a3, int a4)
{
  __int64 File; // rax

  File = anonymous_namespace_::__vcp_CreateFile(a2, a3, 7, 0, 3, a4, 0);
  *a1 = File;
  if ( File == -1 )
    return GetLastError();
  else
    return 0;
}

```

## disassembly

```asm
0x180001cd8  push    rbx
0x180001cda  sub     rsp, 40h
0x180001cde  mov     eax, r8d
0x180001ce1  mov     [rsp+48h+var_18], 0
0x180001cea  mov     [rsp+48h+var_20], r9d
0x180001cef  mov     r10, rdx
0x180001cf2  xor     r9d, r9d
0x180001cf5  mov     [rsp+48h+var_28], 3
0x180001cfd  mov     rbx, rcx
0x180001d00  mov     edx, eax
0x180001d02  mov     rcx, r10
0x180001d05  lea     r8d, [r9+7]
0x180001d09  call    _anonymous_namespace_____vcp_CreateFile
0x180001d0e  mov     [rbx], rax
0x180001d11  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180001d15  jz      short loc_180001D1F
0x180001d17  xor     eax, eax
0x180001d19  add     rsp, 40h
0x180001d1d  pop     rbx
0x180001d1e  retn
0x180001d1f  add     rsp, 40h
0x180001d23  pop     rbx
0x180001d24  jmp     cs:__imp_GetLastError
```
