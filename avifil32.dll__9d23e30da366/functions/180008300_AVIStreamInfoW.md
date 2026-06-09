# AVIStreamInfoW

- ea: `0x180008300`
- end: `0x180008349`
- name: `AVIStreamInfoW`
- size: `73`
- prototype: `HRESULT __stdcall(PAVISTREAM pavi, LPAVISTREAMINFOW psi, LONG lSize)`
- caller_count: `13`
- callee_count: `2`
- tags: ``

## callers

- `0x180001fe0`
- `0x180003050`
- `0x1800034e4`
- `0x180003968`
- `0x1800049d0`
- `0x180004f2c`
- `0x180005470`
- `0x180007e50`
- `0x1800081c0`
- `0x18000d590`
- `0x1800106f0`
- `0x180011944`
- `0x180012224`

## callees

- `0x180001d0c`
- `0x180018010`

## pseudocode

```c
HRESULT __stdcall AVIStreamInfoW(PAVISTREAM pavi, LPAVISTREAMINFOW psi, LONG lSize)
{
  memset_0(psi, 0, lSize);
  return ((__int64 (__fastcall *)(PAVISTREAM, LPAVISTREAMINFOW, _QWORD))pavi->lpVtbl->Info)(
           pavi,
           psi,
           (unsigned int)lSize);
}

```

## disassembly

```asm
0x180008300  mov     [rsp+arg_0], rbx
0x180008305  mov     [rsp+arg_8], rsi
0x18000830a  push    rdi
0x18000830b  sub     rsp, 20h
0x18000830f  mov     rdi, rdx
0x180008312  movsxd  rbx, r8d
0x180008315  mov     rsi, rcx
0x180008318  mov     r8, rbx; Size
0x18000831b  mov     rcx, rdi; void *
0x18000831e  xor     edx, edx; Val
0x180008320  call    memset_0
0x180008325  mov     rax, [rsi]
0x180008328  mov     r8d, ebx
0x18000832b  mov     rdx, rdi
0x18000832e  mov     rcx, rsi
0x180008331  mov     rax, [rax+20h]
0x180008335  mov     rbx, [rsp+28h+arg_0]
0x18000833a  mov     rsi, [rsp+28h+arg_8]
0x18000833f  add     rsp, 20h
0x180008343  pop     rdi
0x180008344  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
