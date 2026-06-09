# write_binary_nolock

- ea: `0x180014a44`
- end: `0x180014ab0`
- name: `write_binary_nolock`
- size: `108`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180014a44`

## import_xrefs

- `KERNEL32!WriteFile` at `0x180014a90`
- `KERNEL32!WriteFile` at `0x180014a90`
- `KERNEL32!GetLastError` at `0x180014a9a`
- `KERNEL32!GetLastError` at `0x180014a9a`

## pseudocode

```c
__int64 __fastcall write_binary_nolock(__int64 a1, int a2, const void *a3, DWORD a4)
{
  DWORD *v6; // r9
  void *v7; // rcx

  v6 = (DWORD *)(a1 + 4);
  v7 = *(void **)(_pioinfo[(__int64)a2 >> 6] + 72LL * (a2 & 0x3F) + 40);
  *(_QWORD *)a1 = 0;
  *(_DWORD *)(a1 + 8) = 0;
  if ( !WriteFile(v7, a3, a4, v6, 0) )
    *(_DWORD *)a1 = GetLastError();
  return a1;
}

```

## disassembly

```asm
0x180014a44  mov     [rsp+arg_0], rbx
0x180014a49  push    rdi
0x180014a4a  sub     rsp, 30h
0x180014a4e  mov     rdi, rcx
0x180014a51  movsxd  r10, edx
0x180014a54  mov     rax, r10
0x180014a57  lea     rcx, __pioinfo
0x180014a5e  sar     rax, 6
0x180014a62  mov     r11d, r9d
0x180014a65  mov     rbx, r8
0x180014a68  and     r10d, 3Fh
0x180014a6c  lea     r9, [rdi+4]; lpNumberOfBytesWritten
0x180014a70  mov     r8d, r11d; nNumberOfBytesToWrite
0x180014a73  mov     rax, [rcx+rax*8]
0x180014a77  lea     rdx, [r10+r10*8]
0x180014a7b  mov     rcx, [rax+rdx*8+28h]; hFile
0x180014a80  xor     eax, eax
0x180014a82  and     [rsp+38h+var_18], rax
0x180014a87  mov     rdx, rbx; lpBuffer
0x180014a8a  mov     [rdi], rax
0x180014a8d  mov     [rdi+8], eax
0x180014a90  call    cs:__imp_WriteFile
0x180014a96  test    eax, eax
0x180014a98  jnz     short loc_180014AA2
0x180014a9a  call    cs:__imp_GetLastError
0x180014aa0  mov     [rdi], eax
0x180014aa2  mov     rbx, [rsp+38h+arg_0]
0x180014aa7  mov     rax, rdi
0x180014aaa  add     rsp, 30h
0x180014aae  pop     rdi
0x180014aaf  retn
```
