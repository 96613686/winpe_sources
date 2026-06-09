# Kerb3961::Aes8009::Initialize(void)

- ea: `0x180014680`
- end: `0x180014796`
- name: `?Initialize@Aes8009@Kerb3961@@EEAA?AU?$ReturnType@UStatusOnly@Kerb3961@@$1??$SingleGetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEAU32@AEAU12@@Z@2@XZ`
- size: `278`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180002fc0`
- `0x180014680`
- `0x180018044`

## import_xrefs

- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800146af`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18001471b`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800146af`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18001471b`
- `bcrypt!BCryptGetProperty` at `0x180014759`
- `bcrypt!BCryptGetProperty` at `0x180014759`
- `bcrypt!BCryptSetProperty` at `0x1800146ef`
- `bcrypt!BCryptSetProperty` at `0x1800146ef`

## string_xrefs

- `0x1800146bb`: `BCryptOpenAlgorithmProvider(&m_cipherHandle, BCRYPT_AES_ALGORITHM, nullptr, 0)`
- `0x180014727`: `BCryptOpenAlgorithmProvider(&m_checksumHandle, m_hashAlgorithmName, nullptr, BCRYPT_ALG_HANDLE_HMAC_FLAG)`

## pseudocode

```c
NTSTATUS *__fastcall Kerb3961::Aes8009::Initialize(__int64 a1, NTSTATUS *a2)
{
  BCRYPT_HANDLE *v2; // r14
  NTSTATUS Property; // edi
  int v6; // r8d
  char *v7; // rcx
  ULONG pcbResult; // [rsp+60h] [rbp+8h] BYREF

  v2 = (BCRYPT_HANDLE *)(a1 + 144);
  pcbResult = 0;
  Property = BCryptOpenAlgorithmProvider((BCRYPT_ALG_HANDLE *)(a1 + 144), L"AES", 0, 0);
  if ( Property >= 0 )
  {
    Property = BCryptSetProperty(*v2, L"ChainingMode", (PUCHAR)L"ChainingModeCBC", 0x20u, 0);
    if ( Property >= 0 )
    {
      Property = BCryptOpenAlgorithmProvider((BCRYPT_ALG_HANDLE *)(a1 + 152), *(LPCWSTR *)(a1 + 96), 0, 8u);
      if ( Property >= 0 )
      {
        Property = BCryptGetProperty(
                     *(BCRYPT_HANDLE *)(a1 + 152),
                     L"HashDigestLength",
                     (PUCHAR)(a1 + 160),
                     4u,
                     &pcbResult,
                     0);
        if ( Property >= 0 )
        {
          *(_BYTE *)(a1 + 164) = wil::details::FeatureImpl<__WilFeatureTraits_Feature_AesSha2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AesSha2>::GetImpl'::`2'::impl);
          *a2 = 0;
          return a2;
        }
        v7 = "BCryptGetProperty(m_checksumHandle, BCRYPT_HASH_LENGTH, reinterpret_cast<uint8_t*>(&m_checksumLength), size"
             "of(m_checksumLength), &ignore, 0)";
      }
      else
      {
        v7 = "BCryptOpenAlgorithmProvider(&m_checksumHandle, m_hashAlgorithmName, nullptr, BCRYPT_ALG_HANDLE_HMAC_FLAG)";
      }
    }
    else
    {
      v7 = "BCryptSetProperty(m_cipherHandle, BCRYPT_CHAINING_MODE, (PUCHAR)BCRYPT_CHAIN_MODE_CBC, sizeof(BCRYPT_CHAIN_MODE_CBC), 0 )";
    }
  }
  else
  {
    v7 = "BCryptOpenAlgorithmProvider(&m_cipherHandle, BCRYPT_AES_ALGORITHM, nullptr, 0)";
  }
  Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)v7, (const char *)(unsigned int)Property, v6);
  *a2 = Property;
  return a2;
}

```

## disassembly

```asm
0x180014680  push    rbx
0x180014682  push    rsi
0x180014683  push    rdi
0x180014684  push    r14
0x180014686  sub     rsp, 38h
0x18001468a  lea     r14, [rcx+90h]
0x180014691  mov     [rsp+58h+pcbResult], 0
0x180014699  mov     rbx, rdx
0x18001469c  mov     rsi, rcx
0x18001469f  mov     rcx, r14; phAlgorithm
0x1800146a2  lea     rdx, aAes; "AES"
0x1800146a9  xor     r9d, r9d; dwFlags
0x1800146ac  xor     r8d, r8d; pszImplementation
0x1800146af  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1800146b5  mov     edi, eax
0x1800146b7  test    eax, eax
0x1800146b9  jns     short loc_1800146D0
0x1800146bb  lea     rcx, aBcryptopenalgo_4; "BCryptOpenAlgorithmProvider(&m_cipherHa"...
0x1800146c2  mov     edx, edi; char *
0x1800146c4  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x1800146c9  mov     [rbx], edi
0x1800146cb  jmp     loc_180014789
0x1800146d0  mov     rcx, [r14]; hObject
0x1800146d3  lea     r8, pbInput; "ChainingModeCBC"
0x1800146da  mov     r9d, 20h ; ' '; cbInput
0x1800146e0  mov     [rsp+58h+dwFlags], 0; dwFlags
0x1800146e8  lea     rdx, aChainingmode; "ChainingMode"
0x1800146ef  call    cs:__imp_BCryptSetProperty
0x1800146f5  mov     edi, eax
0x1800146f7  test    eax, eax
0x1800146f9  jns     short loc_180014704
0x1800146fb  lea     rcx, aBcryptsetprope; "BCryptSetProperty(m_cipherHandle, BCRYP"...
0x180014702  jmp     short loc_1800146C2
0x180014704  mov     rdx, [rsi+60h]; pszAlgId
0x180014708  lea     r14, [rsi+98h]
0x18001470f  mov     rcx, r14; phAlgorithm
0x180014712  mov     r9d, 8; dwFlags
0x180014718  xor     r8d, r8d; pszImplementation
0x18001471b  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180014721  mov     edi, eax
0x180014723  test    eax, eax
0x180014725  jns     short loc_180014730
0x180014727  lea     rcx, aBcryptopenalgo_0; "BCryptOpenAlgorithmProvider(&m_checksum"...
0x18001472e  jmp     short loc_1800146C2
0x180014730  mov     rcx, [r14]; hObject
0x180014733  lea     rax, [rsp+58h+pcbResult]
0x180014738  lea     r8, [rsi+0A0h]; pbOutput
0x18001473f  mov     [rsp+58h+var_30], 0; dwFlags
0x180014747  mov     r9d, 4; cbOutput
0x18001474d  mov     qword ptr [rsp+58h+dwFlags], rax; pcbResult
0x180014752  lea     rdx, pszProperty; "HashDigestLength"
0x180014759  call    cs:__imp_BCryptGetProperty
0x18001475f  mov     edi, eax
0x180014761  test    eax, eax
0x180014763  jns     short loc_180014771
0x180014765  lea     rcx, aBcryptgetprope_0; "BCryptGetProperty(m_checksumHandle, BCR"...
0x18001476c  jmp     loc_1800146C2
0x180014771  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AesSha2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AesSha2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AesSha2> `wil::Feature<__WilFeatureTraits_Feature_AesSha2>::GetImpl(void)'::`2'::impl
0x180014778  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AesSha2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AesSha2>::__private_IsEnabled(void)
0x18001477d  mov     [rsi+0A4h], al
0x180014783  mov     dword ptr [rbx], 0
0x180014789  mov     rax, rbx
0x18001478c  add     rsp, 38h
0x180014790  pop     r14
0x180014792  pop     rdi
0x180014793  pop     rsi
0x180014794  pop     rbx
0x180014795  retn
```
