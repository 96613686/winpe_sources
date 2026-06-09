# Kerb3961::Aes3962::Initialize(void)

- ea: `0x18001b5f0`
- end: `0x18001b6d7`
- name: `?Initialize@Aes3962@Kerb3961@@EEAA?AU?$ReturnType@UStatusOnly@Kerb3961@@$1??$SingleGetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEAU32@AEAU12@@Z@2@XZ`
- size: `231`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180002fc0`
- `0x18001b5f0`

## import_xrefs

- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18001b617`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18001b680`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18001b6ac`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18001b617`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18001b680`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18001b6ac`
- `bcrypt!BCryptSetProperty` at `0x18001b657`
- `bcrypt!BCryptSetProperty` at `0x18001b657`

## string_xrefs

- `0x18001b623`: `BCryptOpenAlgorithmProvider(&m_cipherHandle, BCRYPT_AES_ALGORITHM, nullptr, 0)`
- `0x18001b68c`: `BCryptOpenAlgorithmProvider(&m_hashHandle, BCRYPT_SHA1_ALGORITHM, nullptr, 0)`
- `0x18001b6b8`: `BCryptOpenAlgorithmProvider(&m_checksumHandle, BCRYPT_SHA1_ALGORITHM, nullptr, BCRYPT_ALG_HANDLE_HMAC_FLAG)`

## pseudocode

```c
NTSTATUS *__fastcall Kerb3961::Aes3962::Initialize(BCRYPT_ALG_HANDLE *a1, NTSTATUS *a2)
{
  BCRYPT_HANDLE *v2; // r14
  NTSTATUS v5; // edi
  int v6; // r8d
  char *v7; // rcx

  v2 = a1 + 21;
  v5 = BCryptOpenAlgorithmProvider(a1 + 21, L"AES", 0, 0);
  if ( v5 >= 0 )
  {
    v5 = BCryptSetProperty(*v2, L"ChainingMode", (PUCHAR)L"ChainingModeCBC", 0x20u, 0);
    if ( v5 >= 0 )
    {
      v5 = BCryptOpenAlgorithmProvider(a1 + 22, L"SHA1", 0, 0);
      if ( v5 >= 0 )
      {
        v5 = BCryptOpenAlgorithmProvider(a1 + 23, L"SHA1", 0, 8u);
        if ( v5 >= 0 )
        {
          *a2 = 0;
          return a2;
        }
        v7 = "BCryptOpenAlgorithmProvider(&m_checksumHandle, BCRYPT_SHA1_ALGORITHM, nullptr, BCRYPT_ALG_HANDLE_HMAC_FLAG)";
      }
      else
      {
        v7 = "BCryptOpenAlgorithmProvider(&m_hashHandle, BCRYPT_SHA1_ALGORITHM, nullptr, 0)";
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
  Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)v7, (const char *)(unsigned int)v5, v6);
  *a2 = v5;
  return a2;
}

```

## disassembly

```asm
0x18001b5f0  push    rbx
0x18001b5f2  push    rsi
0x18001b5f3  push    rdi
0x18001b5f4  push    r14
0x18001b5f6  sub     rsp, 38h
0x18001b5fa  lea     r14, [rcx+0A8h]
0x18001b601  mov     rbx, rdx
0x18001b604  mov     rsi, rcx
0x18001b607  lea     rdx, aAes; "AES"
0x18001b60e  mov     rcx, r14; phAlgorithm
0x18001b611  xor     r9d, r9d; dwFlags
0x18001b614  xor     r8d, r8d; pszImplementation
0x18001b617  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18001b61d  mov     edi, eax
0x18001b61f  test    eax, eax
0x18001b621  jns     short loc_18001B638
0x18001b623  lea     rcx, aBcryptopenalgo_4; "BCryptOpenAlgorithmProvider(&m_cipherHa"...
0x18001b62a  mov     edx, edi; char *
0x18001b62c  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18001b631  mov     [rbx], edi
0x18001b633  jmp     loc_18001B6CA
0x18001b638  mov     rcx, [r14]; hObject
0x18001b63b  lea     r8, pbInput; "ChainingModeCBC"
0x18001b642  mov     r9d, 20h ; ' '; cbInput
0x18001b648  mov     [rsp+58h+dwFlags], 0; dwFlags
0x18001b650  lea     rdx, aChainingmode; "ChainingMode"
0x18001b657  call    cs:__imp_BCryptSetProperty
0x18001b65d  mov     edi, eax
0x18001b65f  test    eax, eax
0x18001b661  jns     short loc_18001B66C
0x18001b663  lea     rcx, aBcryptsetprope; "BCryptSetProperty(m_cipherHandle, BCRYP"...
0x18001b66a  jmp     short loc_18001B62A
0x18001b66c  lea     rcx, [rsi+0B0h]; phAlgorithm
0x18001b673  xor     r9d, r9d; dwFlags
0x18001b676  xor     r8d, r8d; pszImplementation
0x18001b679  lea     rdx, aSha1; "SHA1"
0x18001b680  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18001b686  mov     edi, eax
0x18001b688  test    eax, eax
0x18001b68a  jns     short loc_18001B695
0x18001b68c  lea     rcx, aBcryptopenalgo_3; "BCryptOpenAlgorithmProvider(&m_hashHand"...
0x18001b693  jmp     short loc_18001B62A
0x18001b695  lea     rcx, [rsi+0B8h]; phAlgorithm
0x18001b69c  mov     r9d, 8; dwFlags
0x18001b6a2  xor     r8d, r8d; pszImplementation
0x18001b6a5  lea     rdx, aSha1; "SHA1"
0x18001b6ac  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18001b6b2  mov     edi, eax
0x18001b6b4  test    eax, eax
0x18001b6b6  jns     short loc_18001B6C4
0x18001b6b8  lea     rcx, aBcryptopenalgo_1; "BCryptOpenAlgorithmProvider(&m_checksum"...
0x18001b6bf  jmp     loc_18001B62A
0x18001b6c4  mov     dword ptr [rbx], 0
0x18001b6ca  mov     rax, rbx
0x18001b6cd  add     rsp, 38h
0x18001b6d1  pop     r14
0x18001b6d3  pop     rdi
0x18001b6d4  pop     rsi
0x18001b6d5  pop     rbx
0x18001b6d6  retn
```
