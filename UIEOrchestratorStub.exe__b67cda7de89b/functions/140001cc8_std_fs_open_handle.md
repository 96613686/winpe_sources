# __std_fs_open_handle

- ea: `0x140001cc8`
- end: `0x140001d1b`
- name: `__std_fs_open_handle`
- size: `83`
- prototype: `DWORD __fastcall(__int64 *, __int64, unsigned int, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x14000193c`

## callees

- `0x1400017e4`
- `0x140001cc8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140001d14`

## pseudocode

```c
DWORD __fastcall _std_fs_open_handle(__int64 *a1, __int64 a2, unsigned int a3, int a4)
{
  __int64 File; // rax

  File = anonymous_namespace_::__vcp_CreateFile(a2, a3, 7, 0, 3u, a4, 0);
  *a1 = File;
  if ( File == -1 )
    return GetLastError();
  else
    return 0;
}

```

## disassembly

```asm
0x140001cc8  push    rbx
0x140001cca  sub     rsp, 40h
0x140001cce  mov     eax, r8d
0x140001cd1  mov     [rsp+48h+var_18], 0
0x140001cda  mov     [rsp+48h+var_20], r9d
0x140001cdf  mov     r10, rdx
0x140001ce2  xor     r9d, r9d
0x140001ce5  mov     [rsp+48h+var_28], 3
0x140001ced  mov     rbx, rcx
0x140001cf0  mov     edx, eax
0x140001cf2  mov     rcx, r10
0x140001cf5  lea     r8d, [r9+7]
0x140001cf9  call    _anonymous_namespace_____vcp_CreateFile
0x140001cfe  mov     [rbx], rax
0x140001d01  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140001d05  jz      short loc_140001D0F
0x140001d07  xor     eax, eax
0x140001d09  add     rsp, 40h
0x140001d0d  pop     rbx
0x140001d0e  retn
0x140001d0f  add     rsp, 40h
0x140001d13  pop     rbx
0x140001d14  jmp     cs:__imp_GetLastError
```
