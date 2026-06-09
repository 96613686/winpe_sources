# WinPlatformValidateRsaSignature(_BCRYPT_RSAKEY_BLOB *,_BCRYPT_PKCS1_PADDING_INFO *,uchar *,uint,uchar *,uint,uchar *)

- ea: `0x18009c6c0`
- end: `0x18009c7f3`
- name: `?WinPlatformValidateRsaSignature@@YAJPEAU_BCRYPT_RSAKEY_BLOB@@PEAU_BCRYPT_PKCS1_PADDING_INFO@@PEAEI2I2@Z`
- size: `307`
- prototype: `__int64 __fastcall(PUCHAR pbInput, struct _BCRYPT_PKCS1_PADDING_INFO *pPaddingInfo, PUCHAR pbHash, ULONG cbHash, PUCHAR pbSignature, ULONG cbSignature, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18009c6c0`

## import_xrefs

- `bcrypt!BCryptImportKeyPair` at `0x18009c744`
- `bcrypt!BCryptImportKeyPair` at `0x18009c744`
- `bcrypt!BCryptVerifySignature` at `0x18009c784`
- `bcrypt!BCryptVerifySignature` at `0x18009c784`
- `bcrypt!BCryptDestroyKey` at `0x18009c7c1`
- `bcrypt!BCryptDestroyKey` at `0x18009c7c1`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18009c7d9`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18009c7d9`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18009c6ff`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18009c6ff`

## pseudocode

```c
__int64 __fastcall WinPlatformValidateRsaSignature(
        PUCHAR pbInput,
        struct _BCRYPT_PKCS1_PADDING_INFO *pPaddingInfo,
        PUCHAR pbHash,
        ULONG cbHash,
        PUCHAR pbSignature,
        ULONG cbSignature,
        unsigned __int8 *a7)
{
  NTSTATUS v11; // ebx
  NTSTATUS v12; // eax
  BCRYPT_KEY_HANDLE phKey; // [rsp+40h] [rbp-38h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+48h] [rbp-30h] BYREF

  phAlgorithm = 0;
  phKey = 0;
  v11 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"RSA", L"Microsoft Primitive Provider", 0);
  if ( v11 >= 0 )
  {
    v11 = BCryptImportKeyPair(
            phAlgorithm,
            0,
            L"RSAPUBLICBLOB",
            &phKey,
            pbInput,
            *((_DWORD *)pbInput + 3) + 24 + *((_DWORD *)pbInput + 2),
            0);
    if ( v11 >= 0 )
    {
      v12 = BCryptVerifySignature(phKey, pPaddingInfo, pbHash, cbHash, pbSignature, cbSignature, 2u);
      v11 = v12;
      if ( v12 )
      {
        if ( v12 == -1073700864 )
        {
          v11 = 0;
          *a7 = 0;
        }
      }
      else
      {
        *a7 = 1;
      }
    }
  }
  if ( phKey )
    BCryptDestroyKey(phKey);
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18009c6c0  push    rbx
0x18009c6c2  push    rbp
0x18009c6c3  push    rsi
0x18009c6c4  push    rdi
0x18009c6c5  push    r14
0x18009c6c7  sub     rsp, 50h
0x18009c6cb  mov     esi, r9d
0x18009c6ce  mov     [rsp+78h+phAlgorithm], 0
0x18009c6d7  mov     rbp, r8
0x18009c6da  mov     [rsp+78h+phKey], 0
0x18009c6e3  mov     r14, rdx
0x18009c6e6  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x18009c6ed  mov     rdi, rcx
0x18009c6f0  lea     rdx, aRsa; "RSA"
0x18009c6f7  xor     r9d, r9d; dwFlags
0x18009c6fa  lea     rcx, [rsp+78h+phAlgorithm]; phAlgorithm
0x18009c6ff  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18009c706  nop     dword ptr [rax+rax+00h]
0x18009c70b  mov     ebx, eax
0x18009c70d  test    eax, eax
0x18009c70f  js      loc_18009C7B7
0x18009c715  mov     edx, [rdi+0Ch]
0x18009c718  lea     r9, [rsp+78h+phKey]; phKey
0x18009c71d  mov     ecx, [rdi+8]
0x18009c720  lea     r8, aRsapublicblob; "RSAPUBLICBLOB"
0x18009c727  add     edx, 18h
0x18009c72a  mov     [rsp+78h+dwFlags], 0; dwFlags
0x18009c732  add     ecx, edx
0x18009c734  xor     edx, edx; hImportKey
0x18009c736  mov     [rsp+78h+cbInput], ecx; cbInput
0x18009c73a  mov     rcx, [rsp+78h+phAlgorithm]; hAlgorithm
0x18009c73f  mov     [rsp+78h+pbInput], rdi; pbInput
0x18009c744  call    cs:__imp_BCryptImportKeyPair
0x18009c74b  nop     dword ptr [rax+rax+00h]
0x18009c750  mov     ebx, eax
0x18009c752  test    eax, eax
0x18009c754  js      short loc_18009C7B7
0x18009c756  mov     eax, [rsp+78h+cbSignature]
0x18009c75d  mov     r9d, esi; cbHash
0x18009c760  mov     rcx, [rsp+78h+phKey]; hKey
0x18009c765  mov     r8, rbp; pbHash
0x18009c768  mov     [rsp+78h+dwFlags], 2; dwFlags
0x18009c770  mov     rdx, r14; pPaddingInfo
0x18009c773  mov     [rsp+78h+cbInput], eax; cbSignature
0x18009c777  mov     rax, [rsp+78h+pbSignature]
0x18009c77f  mov     [rsp+78h+pbInput], rax; pbSignature
0x18009c784  call    cs:__imp_BCryptVerifySignature
0x18009c78b  nop     dword ptr [rax+rax+00h]
0x18009c790  mov     ebx, eax
0x18009c792  test    eax, eax
0x18009c794  jnz     short loc_18009C7A3
0x18009c796  mov     rax, [rsp+78h+arg_30]
0x18009c79e  mov     byte ptr [rax], 1
0x18009c7a1  jmp     short loc_18009C7B7
0x18009c7a3  cmp     eax, 0C000A000h
0x18009c7a8  jnz     short loc_18009C7B7
0x18009c7aa  mov     rax, [rsp+78h+arg_30]
0x18009c7b2  xor     ebx, ebx
0x18009c7b4  mov     byte ptr [rax], 0
0x18009c7b7  mov     rcx, [rsp+78h+phKey]; hKey
0x18009c7bc  test    rcx, rcx
0x18009c7bf  jz      short loc_18009C7CD
0x18009c7c1  call    cs:__imp_BCryptDestroyKey
0x18009c7c8  nop     dword ptr [rax+rax+00h]
0x18009c7cd  mov     rcx, [rsp+78h+phAlgorithm]; hAlgorithm
0x18009c7d2  test    rcx, rcx
0x18009c7d5  jz      short loc_18009C7E5
0x18009c7d7  xor     edx, edx; dwFlags
0x18009c7d9  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18009c7e0  nop     dword ptr [rax+rax+00h]
0x18009c7e5  mov     eax, ebx
0x18009c7e7  add     rsp, 50h
0x18009c7eb  pop     r14
0x18009c7ed  pop     rdi
0x18009c7ee  pop     rsi
0x18009c7ef  pop     rbp
0x18009c7f0  pop     rbx
0x18009c7f1  retn
```
