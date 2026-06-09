# KerberosCryptoPolicy::OpenChecksumAlgorithm(ulong,Kerb3961::KeyUsage)

- ea: `0x14001e6c8`
- end: `0x14001e77a`
- name: `?OpenChecksumAlgorithm@KerberosCryptoPolicy@@QEAAPEAUChecksumAlgorithm@Kerb3961@@KW4KeyUsage@3@@Z`
- size: `178`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14001ac5c`

## callees

- `0x14001e5c8`
- `0x14001e6c8`
- `0x14001ec20`
- `0x14003a010`

## string_xrefs

- `0x14001e75a`: `KerberosCryptoPolicy::OpenChecksumAlgorithm`

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
    v7 = (__int64 *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *, _QWORD, __int64))(v6 + 128))(
                      *(_QWORD *)a1,
                      v11,
                      a2,
                      0x200000011LL);
  }
  else
  {
    SecondPartner = KerberosCryptoPolicy::GetSecondPartner(a1);
    v7 = (__int64 *)(*(__int64 (__fastcall **)(__int64 *, _BYTE *, _QWORD, __int64, __int64, struct Kerb3961::CipherPartnerHandle *))(v6 + 112))(
                      v5,
                      v11,
                      a2,
                      0x200000011LL,
                      (__int64)a1 + 16,
                      SecondPartner);
  }
  v9 = *v7;
  if ( !*v7 )
    KerberosCryptoPolicy::TraceKeyUsageRequirements(a1, 0x200000011LL, "KerberosCryptoPolicy::OpenChecksumAlgorithm");
  return v9;
}

```

## disassembly

```asm
0x14001e6c8  push    rbx
0x14001e6ca  push    rbp
0x14001e6cb  push    rsi
0x14001e6cc  push    rdi
0x14001e6cd  push    r14
0x14001e6cf  sub     rsp, 50h
0x14001e6d3  cmp     cs:?isolatedMode@KerberosCryptoPolicy@@0_NA, 0; bool KerberosCryptoPolicy::isolatedMode
0x14001e6da  mov     r14d, edx
0x14001e6dd  mov     rbx, rcx
0x14001e6e0  jnz     short loc_14001E6EC
0x14001e6e2  cmp     byte ptr [rcx+8], 0
0x14001e6e6  jnz     short loc_14001E6EC
0x14001e6e8  xor     al, al
0x14001e6ea  jmp     short loc_14001E6EE
0x14001e6ec  mov     al, 1
0x14001e6ee  mov     rdi, [rcx]
0x14001e6f1  mov     rbp, [rdi]
0x14001e6f4  test    al, al
0x14001e6f6  jz      short loc_14001E71E
0x14001e6f8  mov     rax, [rbp+80h]
0x14001e6ff  lea     rdx, [rsp+78h+var_38]
0x14001e704  mov     rsi, 200000011h
0x14001e70e  mov     r8d, r14d
0x14001e711  mov     r9, rsi
0x14001e714  mov     rcx, rdi
0x14001e717  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001e71c  jmp     short loc_14001E752
0x14001e71e  call    ?GetSecondPartner@KerberosCryptoPolicy@@AEAAAEAUCipherPartnerHandle@Kerb3961@@XZ; KerberosCryptoPolicy::GetSecondPartner(void)
0x14001e723  mov     [rsp+78h+var_50], rax
0x14001e728  lea     rcx, [rbx+10h]
0x14001e72c  mov     rax, [rbp+70h]
0x14001e730  lea     rdx, [rsp+78h+var_38]
0x14001e735  mov     [rsp+78h+var_58], rcx
0x14001e73a  mov     rsi, 200000011h
0x14001e744  mov     rcx, rdi
0x14001e747  mov     r9, rsi
0x14001e74a  mov     r8d, r14d
0x14001e74d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001e752  mov     rdi, [rax]
0x14001e755  test    rdi, rdi
0x14001e758  jnz     short loc_14001E76C
0x14001e75a  lea     r8, aKerberoscrypto_2; "KerberosCryptoPolicy::OpenChecksumAlgor"...
0x14001e761  mov     rdx, rsi
0x14001e764  mov     rcx, rbx
0x14001e767  call    ?TraceKeyUsageRequirements@KerberosCryptoPolicy@@AEBAXW4KeyUsage@Kerb3961@@PEBD@Z; KerberosCryptoPolicy::TraceKeyUsageRequirements(Kerb3961::KeyUsage,char const *)
0x14001e76c  mov     rax, rdi
0x14001e76f  add     rsp, 50h
0x14001e773  pop     r14
0x14001e775  pop     rdi
0x14001e776  pop     rsi
0x14001e777  pop     rbp
0x14001e778  pop     rbx
0x14001e779  retn
```
