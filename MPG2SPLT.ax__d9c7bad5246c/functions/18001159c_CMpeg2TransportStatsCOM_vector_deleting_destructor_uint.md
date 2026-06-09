# CMpeg2TransportStatsCOM::`vector deleting destructor'(uint)

- ea: `0x18001159c`
- end: `0x1800115de`
- name: `??_ECMpeg2TransportStatsCOM@@UEAAPEAXI@Z`
- size: `66`
- prototype: `void *__fastcall(CMpeg2TransportStatsCOM *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180011110`

## callees

- `0x180001048`
- `0x18001159c`
- `0x18001186c`

## pseudocode

```c
CMpeg2TransportStatsCOM *__fastcall CMpeg2TransportStatsCOM::`vector deleting destructor'(
        CMpeg2TransportStatsCOM *this,
        char a2)
{
  CMpeg2SharedMem *v3; // rcx

  v3 = (CMpeg2TransportStatsCOM *)((char *)this + 8);
  *(_QWORD *)v3 = &CMpeg2SharedMem::`vftable';
  CMpeg2SharedMem::Free_(v3);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18001159c  mov     [rsp+arg_0], rbx
0x1800115a1  push    rdi
0x1800115a2  sub     rsp, 20h
0x1800115a6  mov     rdi, rcx
0x1800115a9  lea     rax, ??_7CMpeg2SharedMem@@6B@; const CMpeg2SharedMem::`vftable'
0x1800115b0  add     rcx, 8; this
0x1800115b4  mov     ebx, edx
0x1800115b6  mov     [rcx], rax
0x1800115b9  call    ?Free_@CMpeg2SharedMem@@AEAAXXZ; CMpeg2SharedMem::Free_(void)
0x1800115be  test    bl, 1
0x1800115c1  jz      short loc_1800115D0
0x1800115c3  mov     edx, 30h ; '0'; unsigned __int64
0x1800115c8  mov     rcx, rdi; void *
0x1800115cb  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800115d0  mov     rbx, [rsp+28h+arg_0]
0x1800115d5  mov     rax, rdi
0x1800115d8  add     rsp, 20h
0x1800115dc  pop     rdi
0x1800115dd  retn
```
