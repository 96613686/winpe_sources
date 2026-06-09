# CHashAlg::CHashAlg(_TNO_HASH_ALG_ID)

- ea: `0x180137870`
- end: `0x1801379a8`
- name: `??0CHashAlg@@IEAA@W4_TNO_HASH_ALG_ID@@@Z`
- size: `312`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180137f94`

## callees

- `0x180020058`
- `0x1800201c0`
- `0x180137870`
- `0x1801381b0`

## import_xrefs

- `bcrypt!BCryptGetProperty` at `0x180137964`
- `bcrypt!BCryptGetProperty` at `0x180137964`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180137916`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180137932`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180137916`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180137932`

## pseudocode

```c
__int64 __fastcall CHashAlg::CHashAlg(__int64 a1, int a2)
{
  BCRYPT_HANDLE *v3; // r14
  int v4; // edx
  int v5; // edx
  int v6; // edx
  const WCHAR *v7; // rsi
  NTSTATUS Property; // edi
  ULONG pcbResult; // [rsp+68h] [rbp+10h] BYREF

  *(_DWORD *)(a1 + 8) = 0;
  *(_QWORD *)a1 = &CHashAlg::`vftable';
  v3 = (BCRYPT_HANDLE *)(a1 + 16);
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  *(_DWORD *)(a1 + 32) = 0;
  *(_DWORD *)(a1 + 36) = a2;
  pcbResult = 0;
  v4 = a2 - 1;
  if ( v4 )
  {
    v5 = v4 - 1;
    if ( v5 )
    {
      v6 = v5 - 1;
      if ( v6 )
      {
        if ( v6 != 1 )
          ApplicationError::Throw(L"AlgIdToAlgoString", -2147024809);
        ApplicationError::Throw(L"AlgIdToAlgoString -- truncated SHA-512 not supported by CHashAlg", -2147024809);
      }
      v7 = L"SHA512";
    }
    else
    {
      v7 = L"SHA384";
    }
  }
  else
  {
    v7 = L"SHA256";
  }
  Property = BCryptOpenAlgorithmProvider((BCRYPT_ALG_HANDLE *)(a1 + 16), v7, 0, 0);
  if ( Property >= 0 )
  {
    Property = BCryptOpenAlgorithmProvider((BCRYPT_ALG_HANDLE *)(a1 + 24), v7, 0, 8u);
    if ( Property >= 0 )
      Property = BCryptGetProperty(*v3, L"HashDigestLength", (PUCHAR)(a1 + 32), 4u, &pcbResult, 0);
  }
  if ( (Property & 0xC0000000) == 0xC0000000 )
  {
    CHashAlg::Reset((CHashAlg *)a1);
    if ( Property < 0 )
      NtError::Throw(L"CHashAlg::CHashAlg", Property);
  }
  return a1;
}

```

## disassembly

```asm
0x180137870  mov     [rsp+arg_10], rbx
0x180137875  mov     [rsp+arg_0], rcx
0x18013787a  push    rbp
0x18013787b  push    rsi
0x18013787c  push    rdi
0x18013787d  push    r14
0x18013787f  push    r15
0x180137881  sub     rsp, 30h
0x180137885  mov     rbx, rcx
0x180137888  mov     dword ptr [rcx+8], 0
0x18013788f  lea     rax, ??_7CHashAlg@@6B@; const CHashAlg::`vftable'
0x180137896  mov     [rcx], rax
0x180137899  lea     r14, [rcx+10h]
0x18013789d  mov     qword ptr [r14], 0
0x1801378a4  mov     qword ptr [rcx+18h], 0
0x1801378ac  mov     dword ptr [rcx+20h], 0
0x1801378b3  mov     [rcx+24h], edx
0x1801378b6  mov     [rsp+58h+arg_8], 0
0x1801378be  sub     edx, 1
0x1801378c1  jz      short loc_180137903
0x1801378c3  sub     edx, 1
0x1801378c6  jz      short loc_1801378FA
0x1801378c8  sub     edx, 1
0x1801378cb  jz      short loc_1801378F1
0x1801378cd  cmp     edx, 1
0x1801378d0  mov     edx, 80070057h; int
0x1801378d5  jz      short loc_1801378E4
0x1801378d7  lea     rcx, aAlgidtoalgostr; "AlgIdToAlgoString"
0x1801378de  call    ?Throw@ApplicationError@@SAXPEBGJ@Z; ApplicationError::Throw(ushort const *,long)
0x1801378e4  lea     rcx, aAlgidtoalgostr_0; "AlgIdToAlgoString -- truncated SHA-512 "...
0x1801378eb  call    ?Throw@ApplicationError@@SAXPEBGJ@Z; ApplicationError::Throw(ushort const *,long)
0x1801378f1  lea     rsi, aSha512; "SHA512"
0x1801378f8  jmp     short loc_18013790A
0x1801378fa  lea     rsi, aSha384; "SHA384"
0x180137901  jmp     short loc_18013790A
0x180137903  lea     rsi, aSha256; "SHA256"
0x18013790a  xor     r9d, r9d; dwFlags
0x18013790d  xor     r8d, r8d; pszImplementation
0x180137910  mov     rdx, rsi; pszAlgId
0x180137913  mov     rcx, r14; phAlgorithm
0x180137916  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18013791c  mov     edi, eax
0x18013791e  test    eax, eax
0x180137920  js      short loc_18013796C
0x180137922  mov     r9d, 8; dwFlags
0x180137928  xor     r8d, r8d; pszImplementation
0x18013792b  mov     rdx, rsi; pszAlgId
0x18013792e  lea     rcx, [rbx+18h]; phAlgorithm
0x180137932  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180137938  mov     edi, eax
0x18013793a  test    eax, eax
0x18013793c  js      short loc_18013796C
0x18013793e  mov     [rsp+58h+dwFlags], 0; dwFlags
0x180137946  lea     rax, [rsp+58h+arg_8]
0x18013794b  mov     [rsp+58h+pcbResult], rax; pcbResult
0x180137950  mov     r9d, 4; cbOutput
0x180137956  lea     r8, [rbx+20h]; pbOutput
0x18013795a  lea     rdx, aHashdigestleng; "HashDigestLength"
0x180137961  mov     rcx, [r14]; hObject
0x180137964  call    cs:__imp_BCryptGetProperty
0x18013796a  mov     edi, eax
0x18013796c  mov     eax, edi
0x18013796e  mov     ecx, 0C0000000h
0x180137973  and     eax, ecx
0x180137975  cmp     eax, ecx
0x180137977  jnz     short loc_180137994
0x180137979  mov     rcx, rbx; this
0x18013797c  call    ?Reset@CHashAlg@@IEAAXXZ; CHashAlg::Reset(void)
0x180137981  test    edi, edi
0x180137983  jns     short loc_180137994
0x180137985  mov     edx, edi; int
0x180137987  lea     rcx, aChashalgChasha; "CHashAlg::CHashAlg"
0x18013798e  call    ?Throw@NtError@@SAXPEBGJ@Z; NtError::Throw(ushort const *,long)
0x180137994  mov     rax, rbx
0x180137997  mov     rbx, [rsp+58h+arg_10]
0x18013799c  add     rsp, 30h
0x1801379a0  pop     r15
0x1801379a2  pop     r14
0x1801379a4  pop     rdi
0x1801379a5  pop     rsi
0x1801379a6  pop     rbp
0x1801379a7  retn
```
