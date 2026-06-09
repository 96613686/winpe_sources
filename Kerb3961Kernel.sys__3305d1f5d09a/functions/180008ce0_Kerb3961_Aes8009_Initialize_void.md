# Kerb3961::Aes8009::Initialize(void)

- ea: `0x180008ce0`
- end: `0x180008e04`
- name: `?Initialize@Aes8009@Kerb3961@@EEAA?AU?$ReturnType@UStatusOnly@Kerb3961@@$1??$SingleGetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEAU32@AEAU12@@Z@2@XZ`
- size: `292`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180008ce0`
- `0x1800118cc`

## import_xrefs

- `cng!BCryptGetProperty` at `0x180008dcb`
- `cng!BCryptGetProperty` at `0x180008dcb`
- `cng!BCryptSetProperty` at `0x180008d55`
- `cng!BCryptSetProperty` at `0x180008d55`
- `cng!BCryptOpenAlgorithmProvider` at `0x180008d0f`
- `cng!BCryptOpenAlgorithmProvider` at `0x180008d87`
- `cng!BCryptOpenAlgorithmProvider` at `0x180008d0f`
- `cng!BCryptOpenAlgorithmProvider` at `0x180008d87`

## string_xrefs

- `0x180008d21`: `BCryptOpenAlgorithmProvider(&m_cipherHandle, BCRYPT_AES_ALGORITHM, nullptr, 0)`
- `0x180008d99`: `BCryptOpenAlgorithmProvider(&m_checksumHandle, m_hashAlgorithmName, nullptr, BCRYPT_ALG_HANDLE_HMAC_FLAG)`

## pseudocode

```c
NTSTATUS *__fastcall Kerb3961::Aes8009::Initialize(__int64 a1, NTSTATUS *a2)
{
  BCRYPT_HANDLE *v2; // r14
  NTSTATUS Property; // esi
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
          *(_BYTE *)(a1 + 164) = 1;
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
0x180008ce0  push    rbx
0x180008ce2  push    rsi
0x180008ce3  push    rdi
0x180008ce4  push    r14
0x180008ce6  sub     rsp, 38h
0x180008cea  lea     r14, [rcx+90h]
0x180008cf1  mov     [rsp+58h+pcbResult], 0
0x180008cf9  mov     rbx, rdx
0x180008cfc  mov     rdi, rcx
0x180008cff  mov     rcx, r14; phAlgorithm
0x180008d02  lea     rdx, pszAlgId; "AES"
0x180008d09  xor     r9d, r9d; dwFlags
0x180008d0c  xor     r8d, r8d; pszImplementation
0x180008d0f  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180008d16  nop     dword ptr [rax+rax+00h]
0x180008d1b  mov     esi, eax
0x180008d1d  test    eax, eax
0x180008d1f  jns     short loc_180008D36
0x180008d21  lea     rcx, aBcryptopenalgo_4; "BCryptOpenAlgorithmProvider(&m_cipherHa"...
0x180008d28  mov     edx, esi; char *
0x180008d2a  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180008d2f  mov     [rbx], esi
0x180008d31  jmp     loc_180008DF6
0x180008d36  mov     rcx, [r14]; hObject
0x180008d39  lea     r8, pbInput; "ChainingModeCBC"
0x180008d40  mov     r9d, 20h ; ' '; cbInput
0x180008d46  mov     [rsp+58h+dwFlags], 0; dwFlags
0x180008d4e  lea     rdx, pszProperty; "ChainingMode"
0x180008d55  call    cs:__imp_BCryptSetProperty
0x180008d5c  nop     dword ptr [rax+rax+00h]
0x180008d61  mov     esi, eax
0x180008d63  test    eax, eax
0x180008d65  jns     short loc_180008D70
0x180008d67  lea     rcx, aBcryptsetprope; "BCryptSetProperty(m_cipherHandle, BCRYP"...
0x180008d6e  jmp     short loc_180008D28
0x180008d70  mov     rdx, [rdi+60h]; pszAlgId
0x180008d74  lea     r14, [rdi+98h]
0x180008d7b  mov     rcx, r14; phAlgorithm
0x180008d7e  mov     r9d, 8; dwFlags
0x180008d84  xor     r8d, r8d; pszImplementation
0x180008d87  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180008d8e  nop     dword ptr [rax+rax+00h]
0x180008d93  mov     esi, eax
0x180008d95  test    eax, eax
0x180008d97  jns     short loc_180008DA2
0x180008d99  lea     rcx, aBcryptopenalgo_0; "BCryptOpenAlgorithmProvider(&m_checksum"...
0x180008da0  jmp     short loc_180008D28
0x180008da2  mov     rcx, [r14]; hObject
0x180008da5  lea     rax, [rsp+58h+pcbResult]
0x180008daa  lea     r8, [rdi+0A0h]; pbOutput
0x180008db1  mov     [rsp+58h+var_30], 0; dwFlags
0x180008db9  mov     r9d, 4; cbOutput
0x180008dbf  mov     qword ptr [rsp+58h+dwFlags], rax; pcbResult
0x180008dc4  lea     rdx, aHashdigestleng; "HashDigestLength"
0x180008dcb  call    cs:__imp_BCryptGetProperty
0x180008dd2  nop     dword ptr [rax+rax+00h]
0x180008dd7  mov     esi, eax
0x180008dd9  test    eax, eax
0x180008ddb  jns     short loc_180008DE9
0x180008ddd  lea     rcx, aBcryptgetprope_0; "BCryptGetProperty(m_checksumHandle, BCR"...
0x180008de4  jmp     loc_180008D28
0x180008de9  mov     byte ptr [rdi+0A4h], 1
0x180008df0  mov     dword ptr [rbx], 0
0x180008df6  mov     rax, rbx
0x180008df9  add     rsp, 38h
0x180008dfd  pop     r14
0x180008dff  pop     rdi
0x180008e00  pop     rsi
0x180008e01  pop     rbx
0x180008e02  retn
```
