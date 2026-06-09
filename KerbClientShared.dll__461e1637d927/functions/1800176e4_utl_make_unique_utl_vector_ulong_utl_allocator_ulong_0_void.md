# utl::make_unique<utl::vector<ulong,utl::allocator<ulong>>,,0>(void)

- ea: `0x1800176e4`
- end: `0x180017717`
- name: `??$make_unique@V?$vector@KV?$allocator@K@utl@@@utl@@$$V$0A@@utl@@YA?AV?$unique_ptr@V?$vector@KV?$allocator@K@utl@@@utl@@U?$default_delete@V?$vector@KV?$allocator@K@utl@@@utl@@@2@@0@XZ`
- size: `51`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001782c`

## callees

- `0x18000ef4c`
- `0x1800176e4`
- `0x180017720`

## pseudocode

```c
_QWORD *__fastcall utl::make_unique<utl::vector<unsigned long,utl::allocator<unsigned long>>,,0>(_QWORD *a1)
{
  void *v2; // rax

  v2 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v2 )
    v2 = (void *)utl::vector<Kerb3961::EncryptionAlgorithm *,utl::allocator<Kerb3961::EncryptionAlgorithm *>>::vector<Kerb3961::EncryptionAlgorithm *,utl::allocator<Kerb3961::EncryptionAlgorithm *>>(v2);
  *a1 = v2;
  return a1;
}

```

## disassembly

```asm
0x1800176e4  push    rbx
0x1800176e6  sub     rsp, 20h
0x1800176ea  mov     rbx, rcx
0x1800176ed  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800176f4  mov     ecx, 18h; unsigned __int64
0x1800176f9  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800176fe  test    rax, rax
0x180017701  jz      short loc_18001770B
0x180017703  mov     rcx, rax
0x180017706  call    ??0?$vector@PEAUEncryptionAlgorithm@Kerb3961@@V?$allocator@PEAUEncryptionAlgorithm@Kerb3961@@@utl@@@utl@@QEAA@XZ; utl::vector<Kerb3961::EncryptionAlgorithm *,utl::allocator<Kerb3961::EncryptionAlgorithm *>>::vector<Kerb3961::EncryptionAlgorithm *,utl::allocator<Kerb3961::EncryptionAlgorithm *>>(void)
0x18001770b  mov     [rbx], rax
0x18001770e  mov     rax, rbx
0x180017711  add     rsp, 20h
0x180017715  pop     rbx
0x180017716  retn
```
