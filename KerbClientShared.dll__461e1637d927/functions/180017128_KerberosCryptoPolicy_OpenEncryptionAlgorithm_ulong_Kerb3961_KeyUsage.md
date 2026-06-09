# KerberosCryptoPolicy::OpenEncryptionAlgorithm(ulong,Kerb3961::KeyUsage)

- ea: `0x180017128`
- end: `0x1800171c6`
- name: `?OpenEncryptionAlgorithm@KerberosCryptoPolicy@@QEBAPEAUEncryptionAlgorithm@Kerb3961@@KW4KeyUsage@3@@Z`
- size: `158`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `9`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000c1f0`
- `0x18000c50c`
- `0x18000c6ac`
- `0x18000e558`
- `0x180015010`
- `0x18001773c`
- `0x18001799c`
- `0x180018204`
- `0x180018320`

## callees

- `0x1800170a0`
- `0x180017128`
- `0x1800171cc`
- `0x180029010`

## string_xrefs

- `0x1800171a6`: `KerberosCryptoPolicy::OpenEncryptionAlgorithm`

## pseudocode

```c
__int64 __fastcall KerberosCryptoPolicy::OpenEncryptionAlgorithm(KerberosCryptoPolicy *a1, unsigned int a2, __int64 a3)
{
  bool v6; // al
  __int64 *v7; // rdi
  __int64 v8; // rbp
  __int64 *v9; // rax
  const struct Kerb3961::CipherPartnerHandle *SecondPartner; // rax
  __int64 v11; // rdi
  _BYTE v13[56]; // [rsp+40h] [rbp-38h] BYREF

  v6 = KerberosCryptoPolicy::isolatedMode || *((_BYTE *)a1 + 8);
  v7 = *(__int64 **)a1;
  v8 = **(_QWORD **)a1;
  if ( v6 )
  {
    v9 = (__int64 *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *, _QWORD, __int64))(v8 + 120))(*(_QWORD *)a1, v13, a2, a3);
  }
  else
  {
    SecondPartner = KerberosCryptoPolicy::GetSecondPartner(a1);
    v9 = (__int64 *)(*(__int64 (__fastcall **)(__int64 *, _BYTE *, _QWORD, __int64, __int64, const struct Kerb3961::CipherPartnerHandle *))(v8 + 104))(
                      v7,
                      v13,
                      a2,
                      a3,
                      (__int64)a1 + 16,
                      SecondPartner);
  }
  v11 = *v9;
  if ( !*v9 )
    KerberosCryptoPolicy::TraceKeyUsageRequirements(a1, a3, "KerberosCryptoPolicy::OpenEncryptionAlgorithm");
  return v11;
}

```

## disassembly

```asm
0x180017128  push    rbx
0x18001712a  push    rbp
0x18001712b  push    rsi
0x18001712c  push    rdi
0x18001712d  push    r14
0x18001712f  sub     rsp, 50h
0x180017133  cmp     cs:?isolatedMode@KerberosCryptoPolicy@@0_NA, 0; bool KerberosCryptoPolicy::isolatedMode
0x18001713a  mov     rsi, r8
0x18001713d  mov     r14d, edx
0x180017140  mov     rbx, rcx
0x180017143  jnz     short loc_18001714F
0x180017145  cmp     byte ptr [rcx+8], 0
0x180017149  jnz     short loc_18001714F
0x18001714b  xor     al, al
0x18001714d  jmp     short loc_180017151
0x18001714f  mov     al, 1
0x180017151  mov     rdi, [rcx]
0x180017154  mov     rbp, [rdi]
0x180017157  test    al, al
0x180017159  jz      short loc_180017174
0x18001715b  mov     rax, [rbp+78h]
0x18001715f  lea     rdx, [rsp+78h+var_38]
0x180017164  mov     r9, rsi
0x180017167  mov     r8d, r14d
0x18001716a  mov     rcx, rdi
0x18001716d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017172  jmp     short loc_18001719E
0x180017174  call    ?GetSecondPartner@KerberosCryptoPolicy@@AEBAAEBUCipherPartnerHandle@Kerb3961@@XZ; KerberosCryptoPolicy::GetSecondPartner(void)
0x180017179  mov     [rsp+78h+var_50], rax
0x18001717e  lea     rcx, [rbx+10h]
0x180017182  mov     rax, [rbp+68h]
0x180017186  lea     rdx, [rsp+78h+var_38]
0x18001718b  mov     [rsp+78h+var_58], rcx
0x180017190  mov     r9, rsi
0x180017193  mov     rcx, rdi
0x180017196  mov     r8d, r14d
0x180017199  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001719e  mov     rdi, [rax]
0x1800171a1  test    rdi, rdi
0x1800171a4  jnz     short loc_1800171B8
0x1800171a6  lea     r8, aKerberoscrypto_0; "KerberosCryptoPolicy::OpenEncryptionAlg"...
0x1800171ad  mov     rdx, rsi
0x1800171b0  mov     rcx, rbx
0x1800171b3  call    ?TraceKeyUsageRequirements@KerberosCryptoPolicy@@AEBAXW4KeyUsage@Kerb3961@@PEBD@Z; KerberosCryptoPolicy::TraceKeyUsageRequirements(Kerb3961::KeyUsage,char const *)
0x1800171b8  mov     rax, rdi
0x1800171bb  add     rsp, 50h
0x1800171bf  pop     r14
0x1800171c1  pop     rdi
0x1800171c2  pop     rsi
0x1800171c3  pop     rbp
0x1800171c4  pop     rbx
0x1800171c5  retn
```
