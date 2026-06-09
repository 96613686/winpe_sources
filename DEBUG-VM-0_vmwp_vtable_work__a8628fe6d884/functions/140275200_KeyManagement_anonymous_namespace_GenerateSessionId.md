# KeyManagement::_anonymous_namespace_::GenerateSessionId

- ea: `0x140275200`
- end: `0x140275362`
- name: `KeyManagement::_anonymous_namespace_::GenerateSessionId`
- size: `354`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140274b90`

## callees

- `0x140132940`
- `0x140275200`

## import_xrefs

- `bcrypt!BCryptFinishHash` at `0x14027530a`
- `bcrypt!BCryptFinishHash` at `0x14027530a`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x140275338`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x140275338`
- `bcrypt!BCryptDestroyHash` at `0x140275321`
- `bcrypt!BCryptDestroyHash` at `0x140275321`
- `bcrypt!BCryptHashData` at `0x1402752ea`
- `bcrypt!BCryptHashData` at `0x1402752ea`
- `bcrypt!BCryptCreateHash` at `0x1402752c9`
- `bcrypt!BCryptCreateHash` at `0x1402752c9`
- `bcrypt!BCryptGetProperty` at `0x140275290`
- `bcrypt!BCryptGetProperty` at `0x140275290`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x140275254`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x140275254`

## pseudocode

```c
__int64 __fastcall KeyManagement::_anonymous_namespace_::GenerateSessionId(__int64 a1, int a2, UCHAR *a3)
{
  NTSTATUS Property; // ebx
  BCRYPT_HASH_HANDLE phHash; // [rsp+40h] [rbp-20h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+48h] [rbp-18h] BYREF
  ULONG pcbResult; // [rsp+50h] [rbp-10h] BYREF
  UCHAR pbOutput[4]; // [rsp+54h] [rbp-Ch] BYREF

  phAlgorithm = 0;
  phHash = 0;
  pcbResult = 0;
  *(_DWORD *)pbOutput = 0;
  Property = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA256", 0, 0);
  if ( Property >= 0 )
  {
    Property = BCryptGetProperty(phAlgorithm, L"HashDigestLength", pbOutput, 4u, &pcbResult, 0);
    if ( Property >= 0 )
    {
      Property = BCryptCreateHash(phAlgorithm, &phHash, 0, 0, 0, 0, 0);
      if ( Property >= 0 )
      {
        Property = BCryptHashData(phHash, (PUCHAR)(a1 + 4), a2 - 4, 0);
        if ( Property >= 0 )
          Property = BCryptFinishHash(phHash, a3, 0x20u, 0);
      }
    }
  }
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  return Property | 0x10000000u;
}

```

## disassembly

```asm
0x140275200  push    rbp
0x140275202  push    rbx
0x140275203  push    rsi
0x140275204  push    rdi
0x140275205  push    r14
0x140275207  mov     rbp, rsp
0x14027520a  sub     rsp, 60h
0x14027520e  mov     rax, cs:__security_cookie
0x140275215  xor     rax, rsp
0x140275218  mov     [rbp+var_8], rax
0x14027521c  mov     rdi, r8
0x14027521f  mov     [rbp+phAlgorithm], 0
0x140275227  mov     r14, rdx
0x14027522a  mov     [rbp+phHash], 0
0x140275232  mov     rsi, rcx
0x140275235  mov     [rbp+var_10], 0
0x14027523c  xor     r8d, r8d; pszImplementation
0x14027523f  mov     dword ptr [rbp+pbOutput], 0
0x140275246  lea     rdx, pszAlgId; "SHA256"
0x14027524d  xor     r9d, r9d; dwFlags
0x140275250  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x140275254  call    cs:__imp_BCryptOpenAlgorithmProvider
0x14027525b  nop     dword ptr [rax+rax+00h]
0x140275260  mov     ebx, eax
0x140275262  test    eax, eax
0x140275264  js      loc_140275318
0x14027526a  mov     rcx, [rbp+phAlgorithm]; hObject
0x14027526e  lea     rax, [rbp+var_10]
0x140275272  mov     [rsp+60h+dwFlags], 0; dwFlags
0x14027527a  lea     r8, [rbp+pbOutput]; pbOutput
0x14027527e  mov     r9d, 4; cbOutput
0x140275284  mov     [rsp+60h+pcbResult], rax; pcbResult
0x140275289  lea     rdx, pszProperty; "HashDigestLength"
0x140275290  call    cs:__imp_BCryptGetProperty
0x140275297  nop     dword ptr [rax+rax+00h]
0x14027529c  mov     ebx, eax
0x14027529e  test    eax, eax
0x1402752a0  js      short loc_140275318
0x1402752a2  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x1402752a6  lea     rdx, [rbp+phHash]; phHash
0x1402752aa  mov     [rsp+60h+var_30], 0; dwFlags
0x1402752b2  xor     r9d, r9d; cbHashObject
0x1402752b5  mov     [rsp+60h+dwFlags], 0; cbSecret
0x1402752bd  xor     r8d, r8d; pbHashObject
0x1402752c0  mov     [rsp+60h+pcbResult], 0; pbSecret
0x1402752c9  call    cs:__imp_BCryptCreateHash
0x1402752d0  nop     dword ptr [rax+rax+00h]
0x1402752d5  mov     ebx, eax
0x1402752d7  test    eax, eax
0x1402752d9  js      short loc_140275318
0x1402752db  mov     rcx, [rbp+phHash]; hHash
0x1402752df  lea     r8d, [r14-4]; cbInput
0x1402752e3  lea     rdx, [rsi+4]; pbInput
0x1402752e7  xor     r9d, r9d; dwFlags
0x1402752ea  call    cs:__imp_BCryptHashData
0x1402752f1  nop     dword ptr [rax+rax+00h]
0x1402752f6  mov     ebx, eax
0x1402752f8  test    eax, eax
0x1402752fa  js      short loc_140275318
0x1402752fc  mov     rcx, [rbp+phHash]; hHash
0x140275300  xor     r9d, r9d; dwFlags
0x140275303  mov     rdx, rdi; pbOutput
0x140275306  lea     r8d, [r9+20h]; cbOutput
0x14027530a  call    cs:__imp_BCryptFinishHash
0x140275311  nop     dword ptr [rax+rax+00h]
0x140275316  mov     ebx, eax
0x140275318  mov     rcx, [rbp+phHash]; hHash
0x14027531c  test    rcx, rcx
0x14027531f  jz      short loc_14027532D
0x140275321  call    cs:__imp_BCryptDestroyHash
0x140275328  nop     dword ptr [rax+rax+00h]
0x14027532d  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x140275331  test    rcx, rcx
0x140275334  jz      short loc_140275344
0x140275336  xor     edx, edx; dwFlags
0x140275338  call    cs:__imp_BCryptCloseAlgorithmProvider
0x14027533f  nop     dword ptr [rax+rax+00h]
0x140275344  bts     ebx, 1Ch
0x140275348  mov     eax, ebx
0x14027534a  mov     rcx, [rbp+var_8]
0x14027534e  xor     rcx, rsp; StackCookie
0x140275351  call    __security_check_cookie
0x140275356  add     rsp, 60h
0x14027535a  pop     r14
0x14027535c  pop     rdi
0x14027535d  pop     rsi
0x14027535e  pop     rbx
0x14027535f  pop     rbp
0x140275360  retn
```
