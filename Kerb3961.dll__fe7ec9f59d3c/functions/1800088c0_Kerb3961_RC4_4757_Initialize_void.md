# Kerb3961::RC4_4757::Initialize(void)

- ea: `0x1800088c0`
- end: `0x18000896c`
- name: `?Initialize@RC4_4757@Kerb3961@@EEAA?AU?$ReturnType@UStatusOnly@Kerb3961@@$1??$SingleGetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEAU32@AEAU12@@Z@2@XZ`
- size: `172`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180002fc0`
- `0x1800088c0`

## import_xrefs

- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800088e6`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180008918`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18000893e`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800088e6`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180008918`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18000893e`

## string_xrefs

- `0x1800088f2`: `BCryptOpenAlgorithmProvider(&m_cipherHandle, BCRYPT_RC4_ALGORITHM, nullptr, 0)`
- `0x180008924`: `BCryptOpenAlgorithmProvider(&m_checksumHandle, BCRYPT_MD5_ALGORITHM, nullptr, BCRYPT_ALG_HANDLE_HMAC_FLAG)`
- `0x18000894a`: `BCryptOpenAlgorithmProvider(&m_hashHandle, BCRYPT_MD5_ALGORITHM, nullptr, 0)`

## pseudocode

```c
NTSTATUS *__fastcall Kerb3961::RC4_4757::Initialize(BCRYPT_ALG_HANDLE *a1, NTSTATUS *a2)
{
  NTSTATUS v4; // edi
  int v5; // r8d
  char *v6; // rcx

  v4 = BCryptOpenAlgorithmProvider(a1 + 10, L"RC4", 0, 0);
  if ( v4 >= 0 )
  {
    v4 = BCryptOpenAlgorithmProvider(a1 + 12, L"MD5", 0, 8u);
    if ( v4 >= 0 )
    {
      v4 = BCryptOpenAlgorithmProvider(a1 + 11, L"MD5", 0, 0);
      if ( v4 >= 0 )
      {
        *a2 = 0;
        return a2;
      }
      v6 = "BCryptOpenAlgorithmProvider(&m_hashHandle, BCRYPT_MD5_ALGORITHM, nullptr, 0)";
    }
    else
    {
      v6 = "BCryptOpenAlgorithmProvider(&m_checksumHandle, BCRYPT_MD5_ALGORITHM, nullptr, BCRYPT_ALG_HANDLE_HMAC_FLAG)";
    }
  }
  else
  {
    v6 = "BCryptOpenAlgorithmProvider(&m_cipherHandle, BCRYPT_RC4_ALGORITHM, nullptr, 0)";
  }
  Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)v6, (const char *)(unsigned int)v4, v5);
  *a2 = v4;
  return a2;
}

```

## disassembly

```asm
0x1800088c0  mov     [rsp+arg_0], rbx
0x1800088c5  mov     [rsp+arg_8], rsi
0x1800088ca  push    rdi
0x1800088cb  sub     rsp, 20h
0x1800088cf  mov     rbx, rdx
0x1800088d2  mov     rsi, rcx
0x1800088d5  add     rcx, 50h ; 'P'; phAlgorithm
0x1800088d9  lea     rdx, pszAlgId; "RC4"
0x1800088e0  xor     r9d, r9d; dwFlags
0x1800088e3  xor     r8d, r8d; pszImplementation
0x1800088e6  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1800088ec  mov     edi, eax
0x1800088ee  test    eax, eax
0x1800088f0  jns     short loc_180008904
0x1800088f2  lea     rcx, aBcryptopenalgo_5; "BCryptOpenAlgorithmProvider(&m_cipherHa"...
0x1800088f9  mov     edx, edi; char *
0x1800088fb  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180008900  mov     [rbx], edi
0x180008902  jmp     short loc_180008959
0x180008904  lea     rcx, [rsi+60h]; phAlgorithm
0x180008908  mov     r9d, 8; dwFlags
0x18000890e  xor     r8d, r8d; pszImplementation
0x180008911  lea     rdx, aMd5; "MD5"
0x180008918  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18000891e  mov     edi, eax
0x180008920  test    eax, eax
0x180008922  jns     short loc_18000892D
0x180008924  lea     rcx, aBcryptopenalgo; "BCryptOpenAlgorithmProvider(&m_checksum"...
0x18000892b  jmp     short loc_1800088F9
0x18000892d  lea     rcx, [rsi+58h]; phAlgorithm
0x180008931  xor     r9d, r9d; dwFlags
0x180008934  xor     r8d, r8d; pszImplementation
0x180008937  lea     rdx, aMd5; "MD5"
0x18000893e  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180008944  mov     edi, eax
0x180008946  test    eax, eax
0x180008948  jns     short loc_180008953
0x18000894a  lea     rcx, aBcryptopenalgo_2; "BCryptOpenAlgorithmProvider(&m_hashHand"...
0x180008951  jmp     short loc_1800088F9
0x180008953  mov     dword ptr [rbx], 0
0x180008959  mov     rsi, [rsp+28h+arg_8]
0x18000895e  mov     rax, rbx
0x180008961  mov     rbx, [rsp+28h+arg_0]
0x180008966  add     rsp, 20h
0x18000896a  pop     rdi
0x18000896b  retn
```
