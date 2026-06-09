# write_binary_nolock

- ea: `0x1800151a4`
- end: `0x180015210`
- name: `write_binary_nolock`
- size: `108`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x1800151a4`

## import_xrefs

- `KERNEL32!WriteFile` at `0x1800151f0`
- `KERNEL32!WriteFile` at `0x1800151f0`
- `KERNEL32!GetLastError` at `0x1800151fa`
- `KERNEL32!GetLastError` at `0x1800151fa`

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
0x1800151a4  mov     [rsp+arg_0], rbx
0x1800151a9  push    rdi
0x1800151aa  sub     rsp, 30h
0x1800151ae  mov     rdi, rcx
0x1800151b1  movsxd  r10, edx
0x1800151b4  mov     rax, r10
0x1800151b7  lea     rcx, __pioinfo
0x1800151be  sar     rax, 6
0x1800151c2  mov     r11d, r9d
0x1800151c5  mov     rbx, r8
0x1800151c8  and     r10d, 3Fh
0x1800151cc  lea     r9, [rdi+4]; lpNumberOfBytesWritten
0x1800151d0  mov     r8d, r11d; nNumberOfBytesToWrite
0x1800151d3  mov     rax, [rcx+rax*8]
0x1800151d7  lea     rdx, [r10+r10*8]
0x1800151db  mov     rcx, [rax+rdx*8+28h]; hFile
0x1800151e0  xor     eax, eax
0x1800151e2  and     [rsp+38h+var_18], rax
0x1800151e7  mov     rdx, rbx; lpBuffer
0x1800151ea  mov     [rdi], rax
0x1800151ed  mov     [rdi+8], eax
0x1800151f0  call    cs:__imp_WriteFile
0x1800151f6  test    eax, eax
0x1800151f8  jnz     short loc_180015202
0x1800151fa  call    cs:__imp_GetLastError
0x180015200  mov     [rdi], eax
0x180015202  mov     rbx, [rsp+38h+arg_0]
0x180015207  mov     rax, rdi
0x18001520a  add     rsp, 30h
0x18001520e  pop     rdi
0x18001520f  retn
```
