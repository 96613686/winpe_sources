# Kerb3961::RC4_4757::Initialize(void)

- ea: `0x18000ff70`
- end: `0x18001002f`
- name: `?Initialize@RC4_4757@Kerb3961@@EEAA?AU?$ReturnType@UStatusOnly@Kerb3961@@$1??$SingleGetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEAU32@AEAU12@@Z@2@XZ`
- size: `191`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000ff70`
- `0x1800118cc`

## import_xrefs

- `cng!BCryptOpenAlgorithmProvider` at `0x18000ff96`
- `cng!BCryptOpenAlgorithmProvider` at `0x18000ffce`
- `cng!BCryptOpenAlgorithmProvider` at `0x18000fffa`
- `cng!BCryptOpenAlgorithmProvider` at `0x18000ff96`
- `cng!BCryptOpenAlgorithmProvider` at `0x18000ffce`
- `cng!BCryptOpenAlgorithmProvider` at `0x18000fffa`

## string_xrefs

- `0x18000ffa8`: `BCryptOpenAlgorithmProvider(&m_cipherHandle, BCRYPT_RC4_ALGORITHM, nullptr, 0)`
- `0x18000ffe0`: `BCryptOpenAlgorithmProvider(&m_checksumHandle, BCRYPT_MD5_ALGORITHM, nullptr, BCRYPT_ALG_HANDLE_HMAC_FLAG)`
- `0x18001000c`: `BCryptOpenAlgorithmProvider(&m_hashHandle, BCRYPT_MD5_ALGORITHM, nullptr, 0)`

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
0x18000ff70  mov     [rsp+arg_0], rbx
0x18000ff75  mov     [rsp+arg_8], rsi
0x18000ff7a  push    rdi
0x18000ff7b  sub     rsp, 20h
0x18000ff7f  mov     rbx, rdx
0x18000ff82  mov     rsi, rcx
0x18000ff85  add     rcx, 50h ; 'P'; phAlgorithm
0x18000ff89  lea     rdx, aRc4; "RC4"
0x18000ff90  xor     r9d, r9d; dwFlags
0x18000ff93  xor     r8d, r8d; pszImplementation
0x18000ff96  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18000ff9d  nop     dword ptr [rax+rax+00h]
0x18000ffa2  mov     edi, eax
0x18000ffa4  test    eax, eax
0x18000ffa6  jns     short loc_18000FFBA
0x18000ffa8  lea     rcx, aBcryptopenalgo_5; "BCryptOpenAlgorithmProvider(&m_cipherHa"...
0x18000ffaf  mov     edx, edi; char *
0x18000ffb1  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000ffb6  mov     [rbx], edi
0x18000ffb8  jmp     short loc_18001001B
0x18000ffba  lea     rcx, [rsi+60h]; phAlgorithm
0x18000ffbe  mov     r9d, 8; dwFlags
0x18000ffc4  xor     r8d, r8d; pszImplementation
0x18000ffc7  lea     rdx, aMd5; "MD5"
0x18000ffce  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18000ffd5  nop     dword ptr [rax+rax+00h]
0x18000ffda  mov     edi, eax
0x18000ffdc  test    eax, eax
0x18000ffde  jns     short loc_18000FFE9
0x18000ffe0  lea     rcx, aBcryptopenalgo; "BCryptOpenAlgorithmProvider(&m_checksum"...
0x18000ffe7  jmp     short loc_18000FFAF
0x18000ffe9  lea     rcx, [rsi+58h]; phAlgorithm
0x18000ffed  xor     r9d, r9d; dwFlags
0x18000fff0  xor     r8d, r8d; pszImplementation
0x18000fff3  lea     rdx, aMd5; "MD5"
0x18000fffa  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180010001  nop     dword ptr [rax+rax+00h]
0x180010006  mov     edi, eax
0x180010008  test    eax, eax
0x18001000a  jns     short loc_180010015
0x18001000c  lea     rcx, aBcryptopenalgo_2; "BCryptOpenAlgorithmProvider(&m_hashHand"...
0x180010013  jmp     short loc_18000FFAF
0x180010015  mov     dword ptr [rbx], 0
0x18001001b  mov     rsi, [rsp+28h+arg_8]
0x180010020  mov     rax, rbx
0x180010023  mov     rbx, [rsp+28h+arg_0]
0x180010028  add     rsp, 20h
0x18001002c  pop     rdi
0x18001002d  retn
```
