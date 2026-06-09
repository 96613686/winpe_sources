# utl::default_delete<KerberosCryptoPolicy>::operator()(KerberosCryptoPolicy *)

- ea: `0x14001abc8`
- end: `0x14001abf0`
- name: `??R?$default_delete@VKerberosCryptoPolicy@@@utl@@QEBAXPEAVKerberosCryptoPolicy@@@Z`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x14001ab60`

## callees

- `0x140003a70`
- `0x14001ab7c`
- `0x14001abc8`

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
0x14001abc8  test    rdx, rdx
0x14001abcb  jz      short locret_14001ABEF
0x14001abcd  push    rbx
0x14001abce  sub     rsp, 20h
0x14001abd2  mov     rcx, rdx; this
0x14001abd5  mov     rbx, rdx
0x14001abd8  call    ??1KerberosCryptoPolicy@@QEAA@XZ; KerberosCryptoPolicy::~KerberosCryptoPolicy(void)
0x14001abdd  mov     edx, 80h; struct std::nothrow_t *
0x14001abe2  mov     rcx, rbx; void *
0x14001abe5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001abea  add     rsp, 20h
0x14001abee  pop     rbx
0x14001abef  retn
```
