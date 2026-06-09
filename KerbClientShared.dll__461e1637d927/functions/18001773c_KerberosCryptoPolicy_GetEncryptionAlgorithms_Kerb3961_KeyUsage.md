# KerberosCryptoPolicy::GetEncryptionAlgorithms(Kerb3961::KeyUsage)

- ea: `0x18001773c`
- end: `0x180017823`
- name: `?GetEncryptionAlgorithms@KerberosCryptoPolicy@@QEBA?AV?$unique_ptr@V?$vector@PEAUEncryptionAlgorithm@Kerb3961@@V?$allocator@PEAUEncryptionAlgorithm@Kerb3961@@@utl@@@utl@@U?$default_delete@V?$vector@PEAUEncryptionAlgorithm@Kerb3961@@V?$allocator@PEAUEncryptionAlgorithm@Kerb3961@@@utl@@@utl@@@2@@utl@@W4KeyUsage@Kerb3961@@@Z`
- size: `231`
- prototype: `__int64 __fastcall(KerberosCryptoPolicy *this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180015010`

## callees

- `0x18000ef4c`
- `0x180014da0`
- `0x180017128`
- `0x18001760c`
- `0x180017720`
- `0x18001773c`
- `0x18001782c`

## pseudocode

```c
__int64 *__fastcall KerberosCryptoPolicy::GetEncryptionAlgorithms(KerberosCryptoPolicy *this, __int64 *a2, __int64 a3)
{
  void *v5; // rax
  __int64 v6; // r14
  unsigned int *v7; // rbx
  unsigned int *v8; // rdi
  __int64 v10; // [rsp+60h] [rbp+40h] BYREF
  unsigned int **v11; // [rsp+68h] [rbp+48h] BYREF

  v10 = a3;
  v5 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v5 )
  {
    v10 = 0;
    goto LABEL_13;
  }
  v10 = utl::vector<Kerb3961::EncryptionAlgorithm *,utl::allocator<Kerb3961::EncryptionAlgorithm *>>::vector<Kerb3961::EncryptionAlgorithm *,utl::allocator<Kerb3961::EncryptionAlgorithm *>>(v5);
  v6 = v10;
  if ( !v10 )
  {
LABEL_13:
    *a2 = 0;
    goto LABEL_14;
  }
  KerberosCryptoPolicy::GetEncryptionTypes(this);
  if ( v11 )
  {
    v7 = *v11;
    v8 = v11[1];
    while ( v7 != v8 )
    {
      v10 = KerberosCryptoPolicy::OpenEncryptionAlgorithm(this, *v7, 0x8000000000000002uLL);
      if ( v10 )
        utl::vector<Kerb3961::EncryptionAlgorithm *,utl::allocator<Kerb3961::EncryptionAlgorithm *>>::_PushBackOne<Kerb3961::EncryptionAlgorithm * const &>(
          v6,
          &v10);
      ++v7;
    }
    v10 = 0;
    *a2 = v6;
  }
  else
  {
    *a2 = 0;
  }
  utl::unique_ptr<utl::vector<Kerb3961::EncryptionAlgorithm *,utl::allocator<Kerb3961::EncryptionAlgorithm *>>,utl::default_delete<utl::vector<Kerb3961::EncryptionAlgorithm *,utl::allocator<Kerb3961::EncryptionAlgorithm *>>>>::~unique_ptr<utl::vector<Kerb3961::EncryptionAlgorithm *,utl::allocator<Kerb3961::EncryptionAlgorithm *>>,utl::default_delete<utl::vector<Kerb3961::EncryptionAlgorithm *,utl::allocator<Kerb3961::EncryptionAlgorithm *>>>>(&v11);
LABEL_14:
  utl::unique_ptr<utl::vector<Kerb3961::EncryptionAlgorithm *,utl::allocator<Kerb3961::EncryptionAlgorithm *>>,utl::default_delete<utl::vector<Kerb3961::EncryptionAlgorithm *,utl::allocator<Kerb3961::EncryptionAlgorithm *>>>>::~unique_ptr<utl::vector<Kerb3961::EncryptionAlgorithm *,utl::allocator<Kerb3961::EncryptionAlgorithm *>>,utl::default_delete<utl::vector<Kerb3961::EncryptionAlgorithm *,utl::allocator<Kerb3961::EncryptionAlgorithm *>>>>(&v10);
  return a2;
}

```

## disassembly

```asm
0x18001773c  mov     [rsp-28h+arg_0], rbx
0x180017741  mov     [rsp-28h+arg_10], r8
0x180017746  push    rbp
0x180017747  push    rsi
0x180017748  push    rdi
0x180017749  push    r14
0x18001774b  push    r15
0x18001774d  mov     rbp, rsp
0x180017750  sub     rsp, 20h
0x180017754  mov     rsi, rdx
0x180017757  mov     r15, rcx
0x18001775a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180017761  mov     ecx, 18h; unsigned __int64
0x180017766  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001776b  test    rax, rax
0x18001776e  jz      loc_1800177F7
0x180017774  mov     rcx, rax
0x180017777  call    ??0?$vector@PEAUEncryptionAlgorithm@Kerb3961@@V?$allocator@PEAUEncryptionAlgorithm@Kerb3961@@@utl@@@utl@@QEAA@XZ; utl::vector<Kerb3961::EncryptionAlgorithm *,utl::allocator<Kerb3961::EncryptionAlgorithm *>>::vector<Kerb3961::EncryptionAlgorithm *,utl::allocator<Kerb3961::EncryptionAlgorithm *>>(void)
0x18001777c  mov     [rbp+arg_10], rax
0x180017780  mov     r14, rax
0x180017783  test    rax, rax
0x180017786  jz      short loc_1800177FF
0x180017788  lea     rdx, [rbp+arg_18]
0x18001778c  mov     rcx, r15; this
0x18001778f  call    ?GetEncryptionTypes@KerberosCryptoPolicy@@QEBA?AV?$unique_ptr@V?$vector@KV?$allocator@K@utl@@@utl@@U?$default_delete@V?$vector@KV?$allocator@K@utl@@@utl@@@2@@utl@@W4KeyUsage@Kerb3961@@@Z; KerberosCryptoPolicy::GetEncryptionTypes(Kerb3961::KeyUsage)
0x180017794  mov     rdi, [rbp+arg_18]
0x180017798  test    rdi, rdi
0x18001779b  jz      short loc_1800177EE
0x18001779d  mov     rbx, [rdi]
0x1800177a0  mov     rdi, [rdi+8]
0x1800177a4  cmp     rbx, rdi
0x1800177a7  jz      short loc_1800177D8
0x1800177a9  mov     edx, [rbx]
0x1800177ab  mov     r8, 8000000000000002h
0x1800177b5  mov     rcx, r15
0x1800177b8  call    ?OpenEncryptionAlgorithm@KerberosCryptoPolicy@@QEBAPEAUEncryptionAlgorithm@Kerb3961@@KW4KeyUsage@3@@Z; KerberosCryptoPolicy::OpenEncryptionAlgorithm(ulong,Kerb3961::KeyUsage)
0x1800177bd  mov     [rbp+arg_10], rax
0x1800177c1  test    rax, rax
0x1800177c4  jz      short loc_1800177D2
0x1800177c6  lea     rdx, [rbp+arg_10]
0x1800177ca  mov     rcx, r14
0x1800177cd  call    ??$_PushBackOne@AEBQEAUEncryptionAlgorithm@Kerb3961@@@?$vector@PEAUEncryptionAlgorithm@Kerb3961@@V?$allocator@PEAUEncryptionAlgorithm@Kerb3961@@@utl@@@utl@@AEAA_NAEBQEAUEncryptionAlgorithm@Kerb3961@@@Z; utl::vector<Kerb3961::EncryptionAlgorithm *,utl::allocator<Kerb3961::EncryptionAlgorithm *>>::_PushBackOne<Kerb3961::EncryptionAlgorithm * const &>(Kerb3961::EncryptionAlgorithm * const &)
0x1800177d2  add     rbx, 4
0x1800177d6  jmp     short loc_1800177A4
0x1800177d8  mov     [rbp+arg_10], 0
0x1800177e0  mov     [rsi], r14
0x1800177e3  lea     rcx, [rbp+arg_18]
0x1800177e7  call    ??1?$unique_ptr@V?$vector@PEAUEncryptionAlgorithm@Kerb3961@@V?$allocator@PEAUEncryptionAlgorithm@Kerb3961@@@utl@@@utl@@U?$default_delete@V?$vector@PEAUEncryptionAlgorithm@Kerb3961@@V?$allocator@PEAUEncryptionAlgorithm@Kerb3961@@@utl@@@utl@@@2@@utl@@QEAA@XZ; utl::unique_ptr<utl::vector<Kerb3961::EncryptionAlgorithm *,utl::allocator<Kerb3961::EncryptionAlgorithm *>>,utl::default_delete<utl::vector<Kerb3961::EncryptionAlgorithm *,utl::allocator<Kerb3961::EncryptionAlgorithm *>>>>::~unique_ptr<utl::vector<Kerb3961::EncryptionAlgorithm *,utl::allocator<Kerb3961::EncryptionAlgorithm *>>,utl::default_delete<utl::vector<Kerb3961::EncryptionAlgorithm *,utl::allocator<Kerb3961::EncryptionAlgorithm *>>>>(void)
0x1800177ec  jmp     short loc_180017806
0x1800177ee  mov     qword ptr [rsi], 0
0x1800177f5  jmp     short loc_1800177E3
0x1800177f7  mov     [rbp+arg_10], 0
0x1800177ff  mov     qword ptr [rsi], 0
0x180017806  lea     rcx, [rbp+arg_10]
0x18001780a  call    ??1?$unique_ptr@V?$vector@PEAUEncryptionAlgorithm@Kerb3961@@V?$allocator@PEAUEncryptionAlgorithm@Kerb3961@@@utl@@@utl@@U?$default_delete@V?$vector@PEAUEncryptionAlgorithm@Kerb3961@@V?$allocator@PEAUEncryptionAlgorithm@Kerb3961@@@utl@@@utl@@@2@@utl@@QEAA@XZ; utl::unique_ptr<utl::vector<Kerb3961::EncryptionAlgorithm *,utl::allocator<Kerb3961::EncryptionAlgorithm *>>,utl::default_delete<utl::vector<Kerb3961::EncryptionAlgorithm *,utl::allocator<Kerb3961::EncryptionAlgorithm *>>>>::~unique_ptr<utl::vector<Kerb3961::EncryptionAlgorithm *,utl::allocator<Kerb3961::EncryptionAlgorithm *>>,utl::default_delete<utl::vector<Kerb3961::EncryptionAlgorithm *,utl::allocator<Kerb3961::EncryptionAlgorithm *>>>>(void)
0x18001780f  mov     rbx, [rsp+20h+arg_0]
0x180017814  mov     rax, rsi
0x180017817  add     rsp, 20h
0x18001781b  pop     r15
0x18001781d  pop     r14
0x18001781f  pop     rdi
0x180017820  pop     rsi
0x180017821  pop     rbp
0x180017822  retn
```
