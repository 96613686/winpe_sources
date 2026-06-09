# utl::default_delete<KerberosCryptoPolicy>::operator()(KerberosCryptoPolicy *)

- ea: `0x180009d20`
- end: `0x180009d48`
- name: `??R?$default_delete@VKerberosCryptoPolicy@@@utl@@QEBAXPEAVKerberosCryptoPolicy@@@Z`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x180009c88`

## callees

- `0x180001a00`
- `0x180009c88`
- `0x180009d20`

## pseudocode

```c
void __fastcall utl::default_delete<KerberosCryptoPolicy>::operator()(__int64 a1, KerberosCryptoPolicy *a2)
{
  if ( a2 )
  {
    KerberosCryptoPolicy::~KerberosCryptoPolicy(a2);
    operator delete(a2, (const struct std::nothrow_t *)0x80);
  }
}

```

## disassembly

```asm
0x180009d20  test    rdx, rdx
0x180009d23  jz      short locret_180009D47
0x180009d25  push    rbx
0x180009d26  sub     rsp, 20h
0x180009d2a  mov     rcx, rdx; this
0x180009d2d  mov     rbx, rdx
0x180009d30  call    ??1KerberosCryptoPolicy@@QEAA@XZ; KerberosCryptoPolicy::~KerberosCryptoPolicy(void)
0x180009d35  mov     edx, 80h; struct std::nothrow_t *
0x180009d3a  mov     rcx, rbx; void *
0x180009d3d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180009d42  add     rsp, 20h
0x180009d46  pop     rbx
0x180009d47  retn
```
