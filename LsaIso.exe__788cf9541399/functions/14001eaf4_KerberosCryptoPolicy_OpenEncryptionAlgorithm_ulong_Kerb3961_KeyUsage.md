# KerberosCryptoPolicy::OpenEncryptionAlgorithm(ulong,Kerb3961::KeyUsage)

- ea: `0x14001eaf4`
- end: `0x14001eb92`
- name: `?OpenEncryptionAlgorithm@KerberosCryptoPolicy@@QEBAPEAUEncryptionAlgorithm@Kerb3961@@KW4KeyUsage@3@@Z`
- size: `158`
- prototype: ``
- caller_count: `6`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14001bfa8`
- `0x14001e468`
- `0x14001e780`
- `0x14001eb98`
- `0x14001efd0`
- `0x14001f460`

## callees

- `0x14001e648`
- `0x14001eaf4`
- `0x14001ec20`
- `0x14003a010`

## string_xrefs

- `0x14001eb72`: `KerberosCryptoPolicy::OpenEncryptionAlgorithm`

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
0x14001eaf4  push    rbx
0x14001eaf6  push    rbp
0x14001eaf7  push    rsi
0x14001eaf8  push    rdi
0x14001eaf9  push    r14
0x14001eafb  sub     rsp, 50h
0x14001eaff  cmp     cs:?isolatedMode@KerberosCryptoPolicy@@0_NA, 0; bool KerberosCryptoPolicy::isolatedMode
0x14001eb06  mov     rsi, r8
0x14001eb09  mov     r14d, edx
0x14001eb0c  mov     rbx, rcx
0x14001eb0f  jnz     short loc_14001EB1B
0x14001eb11  cmp     byte ptr [rcx+8], 0
0x14001eb15  jnz     short loc_14001EB1B
0x14001eb17  xor     al, al
0x14001eb19  jmp     short loc_14001EB1D
0x14001eb1b  mov     al, 1
0x14001eb1d  mov     rdi, [rcx]
0x14001eb20  mov     rbp, [rdi]
0x14001eb23  test    al, al
0x14001eb25  jz      short loc_14001EB40
0x14001eb27  mov     rax, [rbp+78h]
0x14001eb2b  lea     rdx, [rsp+78h+var_38]
0x14001eb30  mov     r9, rsi
0x14001eb33  mov     r8d, r14d
0x14001eb36  mov     rcx, rdi
0x14001eb39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001eb3e  jmp     short loc_14001EB6A
0x14001eb40  call    ?GetSecondPartner@KerberosCryptoPolicy@@AEBAAEBUCipherPartnerHandle@Kerb3961@@XZ; KerberosCryptoPolicy::GetSecondPartner(void)
0x14001eb45  mov     [rsp+78h+var_50], rax
0x14001eb4a  lea     rcx, [rbx+10h]
0x14001eb4e  mov     rax, [rbp+68h]
0x14001eb52  lea     rdx, [rsp+78h+var_38]
0x14001eb57  mov     [rsp+78h+var_58], rcx
0x14001eb5c  mov     r9, rsi
0x14001eb5f  mov     rcx, rdi
0x14001eb62  mov     r8d, r14d
0x14001eb65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001eb6a  mov     rdi, [rax]
0x14001eb6d  test    rdi, rdi
0x14001eb70  jnz     short loc_14001EB84
0x14001eb72  lea     r8, aKerberoscrypto_0; "KerberosCryptoPolicy::OpenEncryptionAlg"...
0x14001eb79  mov     rdx, rsi
0x14001eb7c  mov     rcx, rbx
0x14001eb7f  call    ?TraceKeyUsageRequirements@KerberosCryptoPolicy@@AEBAXW4KeyUsage@Kerb3961@@PEBD@Z; KerberosCryptoPolicy::TraceKeyUsageRequirements(Kerb3961::KeyUsage,char const *)
0x14001eb84  mov     rax, rdi
0x14001eb87  add     rsp, 50h
0x14001eb8b  pop     r14
0x14001eb8d  pop     rdi
0x14001eb8e  pop     rsi
0x14001eb8f  pop     rbp
0x14001eb90  pop     rbx
0x14001eb91  retn
```
