# Kerb3961::Aes3962::Initialize(void)

- ea: `0x180005780`
- end: `0x180005880`
- name: `?Initialize@Aes3962@Kerb3961@@EEAA?AU?$ReturnType@UStatusOnly@Kerb3961@@$1??$SingleGetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEAU32@AEAU12@@Z@2@XZ`
- size: `256`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180005780`
- `0x1800118cc`

## import_xrefs

- `cng!BCryptSetProperty` at `0x1800057ed`
- `cng!BCryptSetProperty` at `0x1800057ed`
- `cng!BCryptOpenAlgorithmProvider` at `0x1800057a7`
- `cng!BCryptOpenAlgorithmProvider` at `0x18000581c`
- `cng!BCryptOpenAlgorithmProvider` at `0x18000584e`
- `cng!BCryptOpenAlgorithmProvider` at `0x1800057a7`
- `cng!BCryptOpenAlgorithmProvider` at `0x18000581c`
- `cng!BCryptOpenAlgorithmProvider` at `0x18000584e`

## string_xrefs

- `0x1800057b9`: `BCryptOpenAlgorithmProvider(&m_cipherHandle, BCRYPT_AES_ALGORITHM, nullptr, 0)`
- `0x18000582e`: `BCryptOpenAlgorithmProvider(&m_hashHandle, BCRYPT_SHA1_ALGORITHM, nullptr, 0)`
- `0x180005860`: `BCryptOpenAlgorithmProvider(&m_checksumHandle, BCRYPT_SHA1_ALGORITHM, nullptr, BCRYPT_ALG_HANDLE_HMAC_FLAG)`

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
0x180005780  push    rbx
0x180005782  push    rsi
0x180005783  push    rdi
0x180005784  push    r14
0x180005786  sub     rsp, 38h
0x18000578a  lea     r14, [rcx+0A8h]
0x180005791  mov     rbx, rdx
0x180005794  mov     rsi, rcx
0x180005797  lea     rdx, pszAlgId; "AES"
0x18000579e  mov     rcx, r14; phAlgorithm
0x1800057a1  xor     r9d, r9d; dwFlags
0x1800057a4  xor     r8d, r8d; pszImplementation
0x1800057a7  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1800057ae  nop     dword ptr [rax+rax+00h]
0x1800057b3  mov     edi, eax
0x1800057b5  test    eax, eax
0x1800057b7  jns     short loc_1800057CE
0x1800057b9  lea     rcx, aBcryptopenalgo_4; "BCryptOpenAlgorithmProvider(&m_cipherHa"...
0x1800057c0  mov     edx, edi; char *
0x1800057c2  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x1800057c7  mov     [rbx], edi
0x1800057c9  jmp     loc_180005872
0x1800057ce  mov     rcx, [r14]; hObject
0x1800057d1  lea     r8, pbInput; "ChainingModeCBC"
0x1800057d8  mov     r9d, 20h ; ' '; cbInput
0x1800057de  mov     [rsp+58h+dwFlags], 0; dwFlags
0x1800057e6  lea     rdx, pszProperty; "ChainingMode"
0x1800057ed  call    cs:__imp_BCryptSetProperty
0x1800057f4  nop     dword ptr [rax+rax+00h]
0x1800057f9  mov     edi, eax
0x1800057fb  test    eax, eax
0x1800057fd  jns     short loc_180005808
0x1800057ff  lea     rcx, aBcryptsetprope; "BCryptSetProperty(m_cipherHandle, BCRYP"...
0x180005806  jmp     short loc_1800057C0
0x180005808  lea     rcx, [rsi+0B0h]; phAlgorithm
0x18000580f  xor     r9d, r9d; dwFlags
0x180005812  xor     r8d, r8d; pszImplementation
0x180005815  lea     rdx, aSha1; "SHA1"
0x18000581c  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180005823  nop     dword ptr [rax+rax+00h]
0x180005828  mov     edi, eax
0x18000582a  test    eax, eax
0x18000582c  jns     short loc_180005837
0x18000582e  lea     rcx, aBcryptopenalgo_3; "BCryptOpenAlgorithmProvider(&m_hashHand"...
0x180005835  jmp     short loc_1800057C0
0x180005837  lea     rcx, [rsi+0B8h]; phAlgorithm
0x18000583e  mov     r9d, 8; dwFlags
0x180005844  xor     r8d, r8d; pszImplementation
0x180005847  lea     rdx, aSha1; "SHA1"
0x18000584e  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180005855  nop     dword ptr [rax+rax+00h]
0x18000585a  mov     edi, eax
0x18000585c  test    eax, eax
0x18000585e  jns     short loc_18000586C
0x180005860  lea     rcx, aBcryptopenalgo_1; "BCryptOpenAlgorithmProvider(&m_checksum"...
0x180005867  jmp     loc_1800057C0
0x18000586c  mov     dword ptr [rbx], 0
0x180005872  mov     rax, rbx
0x180005875  add     rsp, 38h
0x180005879  pop     r14
0x18000587b  pop     rdi
0x18000587c  pop     rsi
0x18000587d  pop     rbx
0x18000587e  retn
```
