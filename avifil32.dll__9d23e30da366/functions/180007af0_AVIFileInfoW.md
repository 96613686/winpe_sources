# AVIFileInfoW

- ea: `0x180007af0`
- end: `0x180007b39`
- name: `AVIFileInfoW`
- size: `73`
- prototype: `HRESULT __stdcall(PAVIFILE pfile, LPAVIFILEINFOW pfi, LONG lSize)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180001fe0`
- `0x180005470`
- `0x1800079f0`

## callees

- `0x180001d0c`
- `0x180018010`

## pseudocode

```c
HRESULT __stdcall AVIFileInfoW(PAVIFILE pfile, LPAVIFILEINFOW pfi, LONG lSize)
{
  memset_0(pfi, 0, lSize);
  return ((__int64 (__fastcall *)(PAVIFILE, LPAVIFILEINFOW, _QWORD))pfile->lpVtbl->Info)(
           pfile,
           pfi,
           (unsigned int)lSize);
}

```

## disassembly

```asm
0x180007af0  mov     [rsp+arg_0], rbx
0x180007af5  mov     [rsp+arg_8], rsi
0x180007afa  push    rdi
0x180007afb  sub     rsp, 20h
0x180007aff  mov     rdi, rdx
0x180007b02  movsxd  rbx, r8d
0x180007b05  mov     rsi, rcx
0x180007b08  mov     r8, rbx; Size
0x180007b0b  mov     rcx, rdi; void *
0x180007b0e  xor     edx, edx; Val
0x180007b10  call    memset_0
0x180007b15  mov     rax, [rsi]
0x180007b18  mov     r8d, ebx
0x180007b1b  mov     rdx, rdi
0x180007b1e  mov     rcx, rsi
0x180007b21  mov     rax, [rax+18h]
0x180007b25  mov     rbx, [rsp+28h+arg_0]
0x180007b2a  mov     rsi, [rsp+28h+arg_8]
0x180007b2f  add     rsp, 20h
0x180007b33  pop     rdi
0x180007b34  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
