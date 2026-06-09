# KerberosCryptoPolicy::GetEncryptionTypes(Kerb3961::KeyUsage)

- ea: `0x18001782c`
- end: `0x1800178ed`
- name: `?GetEncryptionTypes@KerberosCryptoPolicy@@QEBA?AV?$unique_ptr@V?$vector@KV?$allocator@K@utl@@@utl@@U?$default_delete@V?$vector@KV?$allocator@K@utl@@@utl@@@2@@utl@@W4KeyUsage@Kerb3961@@@Z`
- size: `193`
- prototype: `__int64 __fastcall(KerberosCryptoPolicy *this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x18001773c`

## callees

- `0x18000ef40`
- `0x180014da0`
- `0x1800170a0`
- `0x1800176b4`
- `0x1800176e4`
- `0x18001782c`
- `0x180029010`

## pseudocode

```c
_QWORD *__fastcall KerberosCryptoPolicy::GetEncryptionTypes(KerberosCryptoPolicy *this, _QWORD *a2, __int64 a3)
{
  __int64 v5; // r14
  __int64 v6; // rdi
  void (__fastcall *v7)(__int64, __int64 *, unsigned __int64, char *, const struct Kerb3961::CipherPartnerHandle *); // rbx
  const struct Kerb3961::CipherPartnerHandle *SecondPartner; // rax
  __int64 v10; // [rsp+30h] [rbp-28h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-20h]
  int v12; // [rsp+40h] [rbp-18h]
  __int64 v13; // [rsp+A0h] [rbp+48h] BYREF

  v13 = a3;
  utl::make_unique<utl::vector<unsigned long,utl::allocator<unsigned long>>,,0>(&v13);
  v5 = v13;
  if ( v13 )
  {
    v6 = *(_QWORD *)this;
    v7 = *(void (__fastcall **)(__int64, __int64 *, unsigned __int64, char *, const struct Kerb3961::CipherPartnerHandle *))(**(_QWORD **)this + 168LL);
    SecondPartner = KerberosCryptoPolicy::GetSecondPartner(this);
    v7(v6, &v10, 0x8000000000000002uLL, (char *)this + 16, SecondPartner);
    if ( v12 >= 0
      && (unsigned __int8)utl::vector<unsigned long,utl::allocator<unsigned long>>::assign<unsigned int const *,void>(
                            v5,
                            hMem,
                            (char *)hMem + 4 * v10) )
    {
      v13 = 0;
      *a2 = v5;
    }
    else
    {
      *a2 = 0;
    }
    operator delete(hMem);
  }
  else
  {
    *a2 = 0;
  }
  utl::unique_ptr<utl::vector<Kerb3961::EncryptionAlgorithm *,utl::allocator<Kerb3961::EncryptionAlgorithm *>>,utl::default_delete<utl::vector<Kerb3961::EncryptionAlgorithm *,utl::allocator<Kerb3961::EncryptionAlgorithm *>>>>::~unique_ptr<utl::vector<Kerb3961::EncryptionAlgorithm *,utl::allocator<Kerb3961::EncryptionAlgorithm *>>,utl::default_delete<utl::vector<Kerb3961::EncryptionAlgorithm *,utl::allocator<Kerb3961::EncryptionAlgorithm *>>>>(&v13);
  return a2;
}

```

## disassembly

```asm
0x18001782c  mov     [rsp-30h+arg_10], r8
0x180017831  push    rbp
0x180017832  push    rbx
0x180017833  push    rsi
0x180017834  push    rdi
0x180017835  push    r14
0x180017837  push    r15
0x180017839  mov     rbp, rsp
0x18001783c  sub     rsp, 58h
0x180017840  mov     r15, rcx
0x180017843  mov     rsi, rdx
0x180017846  lea     rcx, [rbp+arg_10]
0x18001784a  call    ??$make_unique@V?$vector@KV?$allocator@K@utl@@@utl@@$$V$0A@@utl@@YA?AV?$unique_ptr@V?$vector@KV?$allocator@K@utl@@@utl@@U?$default_delete@V?$vector@KV?$allocator@K@utl@@@utl@@@2@@0@XZ; utl::make_unique<utl::vector<ulong,utl::allocator<ulong>>,,0>(void)
0x18001784f  mov     r14, [rbp+arg_10]
0x180017853  test    r14, r14
0x180017856  jnz     short loc_18001785D
0x180017858  mov     [rsi], r14
0x18001785b  jmp     short loc_1800178D4
0x18001785d  mov     rdi, [r15]
0x180017860  mov     rcx, r15; this
0x180017863  mov     rax, [rdi]
0x180017866  mov     rbx, [rax+0A8h]
0x18001786d  call    ?GetSecondPartner@KerberosCryptoPolicy@@AEBAAEBUCipherPartnerHandle@Kerb3961@@XZ; KerberosCryptoPolicy::GetSecondPartner(void)
0x180017872  mov     [rsp+58h+var_38], rax
0x180017877  lea     r9, [r15+10h]
0x18001787b  mov     rax, rbx
0x18001787e  lea     rdx, [rbp+var_28]
0x180017882  mov     r8, 8000000000000002h
0x18001788c  mov     rcx, rdi
0x18001788f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017894  cmp     [rbp+var_18], 0
0x180017898  jge     short loc_1800178A3
0x18001789a  mov     qword ptr [rsi], 0
0x1800178a1  jmp     short loc_1800178C6
0x1800178a3  mov     rdx, [rbp+hMem]
0x1800178a7  mov     rcx, r14
0x1800178aa  mov     rax, [rbp+var_28]
0x1800178ae  lea     r8, [rdx+rax*4]
0x1800178b2  call    ??$assign@PEBIX@?$vector@KV?$allocator@K@utl@@@utl@@QEAA_NPEBI0@Z; utl::vector<ulong,utl::allocator<ulong>>::assign<uint const *,void>(uint const *,uint const *)
0x1800178b7  test    al, al
0x1800178b9  jz      short loc_18001789A
0x1800178bb  mov     [rbp+arg_10], 0
0x1800178c3  mov     [rsi], r14
0x1800178c6  mov     rcx, [rbp+hMem]; hMem
0x1800178ca  mov     edx, 4
0x1800178cf  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800178d4  lea     rcx, [rbp+arg_10]
0x1800178d8  call    ??1?$unique_ptr@V?$vector@PEAUEncryptionAlgorithm@Kerb3961@@V?$allocator@PEAUEncryptionAlgorithm@Kerb3961@@@utl@@@utl@@U?$default_delete@V?$vector@PEAUEncryptionAlgorithm@Kerb3961@@V?$allocator@PEAUEncryptionAlgorithm@Kerb3961@@@utl@@@utl@@@2@@utl@@QEAA@XZ; utl::unique_ptr<utl::vector<Kerb3961::EncryptionAlgorithm *,utl::allocator<Kerb3961::EncryptionAlgorithm *>>,utl::default_delete<utl::vector<Kerb3961::EncryptionAlgorithm *,utl::allocator<Kerb3961::EncryptionAlgorithm *>>>>::~unique_ptr<utl::vector<Kerb3961::EncryptionAlgorithm *,utl::allocator<Kerb3961::EncryptionAlgorithm *>>,utl::default_delete<utl::vector<Kerb3961::EncryptionAlgorithm *,utl::allocator<Kerb3961::EncryptionAlgorithm *>>>>(void)
0x1800178dd  mov     rax, rsi
0x1800178e0  add     rsp, 58h
0x1800178e4  pop     r15
0x1800178e6  pop     r14
0x1800178e8  pop     rdi
0x1800178e9  pop     rsi
0x1800178ea  pop     rbx
0x1800178eb  pop     rbp
0x1800178ec  retn
```
