# utl::unique_ptr<utl::vector<Kerb3961::EncryptionAlgorithm *,utl::allocator<Kerb3961::EncryptionAlgorithm *>>,utl::default_delete<utl::vector<Kerb3961::EncryptionAlgorithm *,utl::allocator<Kerb3961::EncryptionAlgorithm *>>>>::~unique_ptr<utl::vector<Kerb3961::EncryptionAlgorithm *,utl::allocator<Kerb3961::EncryptionAlgorithm *>>,utl::default_delete<utl::vector<Kerb3961::EncryptionAlgorithm *,utl::allocator<Kerb3961::EncryptionAlgorithm *>>>>(void)

- ea: `0x180014da0`
- end: `0x180014dc9`
- name: `??1?$unique_ptr@V?$vector@PEAUEncryptionAlgorithm@Kerb3961@@V?$allocator@PEAUEncryptionAlgorithm@Kerb3961@@@utl@@@utl@@U?$default_delete@V?$vector@PEAUEncryptionAlgorithm@Kerb3961@@V?$allocator@PEAUEncryptionAlgorithm@Kerb3961@@@utl@@@utl@@@2@@utl@@QEAA@XZ`
- size: `41`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180015010`
- `0x18001773c`
- `0x18001782c`

## callees

- `0x18000e49c`
- `0x18000ef40`
- `0x180014da0`

## pseudocode

```c
HLOCAL __fastcall utl::unique_ptr<utl::vector<Kerb3961::EncryptionAlgorithm *,utl::allocator<Kerb3961::EncryptionAlgorithm *>>,utl::default_delete<utl::vector<Kerb3961::EncryptionAlgorithm *,utl::allocator<Kerb3961::EncryptionAlgorithm *>>>>::~unique_ptr<utl::vector<Kerb3961::EncryptionAlgorithm *,utl::allocator<Kerb3961::EncryptionAlgorithm *>>,utl::default_delete<utl::vector<Kerb3961::EncryptionAlgorithm *,utl::allocator<Kerb3961::EncryptionAlgorithm *>>>>(
        _QWORD *a1)
{
  void *v1; // rbx
  HLOCAL result; // rax

  v1 = (void *)*a1;
  if ( *a1 )
  {
    utl::vector<Kerb3961::EncryptionAlgorithm *,utl::allocator<Kerb3961::EncryptionAlgorithm *>>::_Uninit(*a1);
    return operator delete(v1);
  }
  return result;
}

```

## disassembly

```asm
0x180014da0  push    rbx
0x180014da2  sub     rsp, 20h
0x180014da6  mov     rbx, [rcx]
0x180014da9  test    rbx, rbx
0x180014dac  jz      short loc_180014DC3
0x180014dae  mov     rcx, rbx
0x180014db1  call    ?_Uninit@?$vector@PEAUEncryptionAlgorithm@Kerb3961@@V?$allocator@PEAUEncryptionAlgorithm@Kerb3961@@@utl@@@utl@@AEAAXXZ; utl::vector<Kerb3961::EncryptionAlgorithm *,utl::allocator<Kerb3961::EncryptionAlgorithm *>>::_Uninit(void)
0x180014db6  mov     edx, 18h
0x180014dbb  mov     rcx, rbx; hMem
0x180014dbe  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180014dc3  add     rsp, 20h
0x180014dc7  pop     rbx
0x180014dc8  retn
```
