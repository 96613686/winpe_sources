# KerberosCryptoPolicy::OpenChecksumAlgorithm(ulong,Kerb3961::KeyUsage)

- ea: `0x1800178f4`
- end: `0x180017996`
- name: `?OpenChecksumAlgorithm@KerberosCryptoPolicy@@QEAAPEAUChecksumAlgorithm@Kerb3961@@KW4KeyUsage@3@@Z`
- size: `162`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180009c50`

## callees

- `0x18000e5e0`
- `0x1800171cc`
- `0x1800178f4`
- `0x180029010`

## string_xrefs

- `0x180017977`: `KerberosCryptoPolicy::OpenChecksumAlgorithm`

## pseudocode

```c
__int64 __fastcall KerberosCryptoPolicy::OpenChecksumAlgorithm(KerberosCryptoPolicy *a1, unsigned int a2)
{
  bool v4; // al
  __int64 *v5; // rdi
  __int64 v6; // rbp
  __int64 *v7; // rax
  struct Kerb3961::CipherPartnerHandle *SecondPartner; // rax
  __int64 v9; // rdi
  _BYTE v11[56]; // [rsp+40h] [rbp-38h] BYREF

  v4 = KerberosCryptoPolicy::isolatedMode || *((_BYTE *)a1 + 8);
  v5 = *(__int64 **)a1;
  v6 = **(_QWORD **)a1;
  if ( v4 )
  {
    v7 = (__int64 *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *, _QWORD, __int64))(v6 + 128))(*(_QWORD *)a1, v11, a2, 17);
  }
  else
  {
    SecondPartner = KerberosCryptoPolicy::GetSecondPartner(a1);
    v7 = (__int64 *)(*(__int64 (__fastcall **)(__int64 *, _BYTE *, _QWORD, __int64, __int64, struct Kerb3961::CipherPartnerHandle *))(v6 + 112))(
                      v5,
                      v11,
                      a2,
                      17,
                      (__int64)a1 + 16,
                      SecondPartner);
  }
  v9 = *v7;
  if ( !*v7 )
    KerberosCryptoPolicy::TraceKeyUsageRequirements(a1, 17, "KerberosCryptoPolicy::OpenChecksumAlgorithm");
  return v9;
}

```

## disassembly

```asm
0x1800178f4  push    rbx
0x1800178f6  push    rbp
0x1800178f7  push    rdi
0x1800178f8  push    r14
0x1800178fa  sub     rsp, 58h
0x1800178fe  cmp     cs:?isolatedMode@KerberosCryptoPolicy@@0_NA, 0; bool KerberosCryptoPolicy::isolatedMode
0x180017905  mov     r14d, edx
0x180017908  mov     rbx, rcx
0x18001790b  jnz     short loc_180017917
0x18001790d  cmp     byte ptr [rcx+8], 0
0x180017911  jnz     short loc_180017917
0x180017913  xor     al, al
0x180017915  jmp     short loc_180017919
0x180017917  mov     al, 1
0x180017919  mov     rdi, [rcx]
0x18001791c  mov     rbp, [rdi]
0x18001791f  test    al, al
0x180017921  jz      short loc_180017942
0x180017923  mov     rax, [rbp+80h]
0x18001792a  lea     rdx, [rsp+78h+var_38]
0x18001792f  mov     r9d, 11h
0x180017935  mov     r8d, r14d
0x180017938  mov     rcx, rdi
0x18001793b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017940  jmp     short loc_18001796F
0x180017942  call    ?GetSecondPartner@KerberosCryptoPolicy@@AEAAAEAUCipherPartnerHandle@Kerb3961@@XZ; KerberosCryptoPolicy::GetSecondPartner(void)
0x180017947  mov     [rsp+78h+var_50], rax
0x18001794c  lea     rcx, [rbx+10h]
0x180017950  mov     rax, [rbp+70h]
0x180017954  lea     rdx, [rsp+78h+var_38]
0x180017959  mov     [rsp+78h+var_58], rcx
0x18001795e  mov     r9d, 11h
0x180017964  mov     rcx, rdi
0x180017967  mov     r8d, r14d
0x18001796a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001796f  mov     rdi, [rax]
0x180017972  test    rdi, rdi
0x180017975  jnz     short loc_180017989
0x180017977  lea     r8, aKerberoscrypto_2; "KerberosCryptoPolicy::OpenChecksumAlgor"...
0x18001797e  mov     rcx, rbx
0x180017981  lea     edx, [rdi+11h]
0x180017984  call    ?TraceKeyUsageRequirements@KerberosCryptoPolicy@@AEBAXW4KeyUsage@Kerb3961@@PEBD@Z; KerberosCryptoPolicy::TraceKeyUsageRequirements(Kerb3961::KeyUsage,char const *)
0x180017989  mov     rax, rdi
0x18001798c  add     rsp, 58h
0x180017990  pop     r14
0x180017992  pop     rdi
0x180017993  pop     rbp
0x180017994  pop     rbx
0x180017995  retn
```
