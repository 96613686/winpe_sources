# CtapCborClientPinHMACLargeBlobsRequest

- ea: `0x1800c9150`
- end: `0x1800c92d6`
- name: `CtapCborClientPinHMACLargeBlobsRequest`
- size: `390`
- prototype: `__int64 __fastcall(ULONG cbSecret, PUCHAR pbSecret)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800da540`
- `0x1800dce74`

## callees

- `0x18002bbf4`
- `0x1800c9150`
- `0x18013c090`

## import_xrefs

- `CRYPT32!CryptHashCertificate2` at `0x1800c9253`
- `CRYPT32!CryptHashCertificate2` at `0x1800c9253`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800c92ab`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800c92ab`
- `bcrypt!BCryptDestroyHash` at `0x1800c929a`
- `bcrypt!BCryptDestroyHash` at `0x1800c929a`
- `bcrypt!BCryptFinishHash` at `0x1800c9289`
- `bcrypt!BCryptFinishHash` at `0x1800c9289`
- `bcrypt!BCryptHashData` at `0x1800c9209`
- `bcrypt!BCryptHashData` at `0x1800c9270`
- `bcrypt!BCryptHashData` at `0x1800c9209`
- `bcrypt!BCryptHashData` at `0x1800c9270`
- `bcrypt!BCryptCreateHash` at `0x1800c91ea`
- `bcrypt!BCryptCreateHash` at `0x1800c91ea`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800c91bf`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800c91bf`

## pseudocode

```c
__int64 __fastcall CtapCborClientPinHMACLargeBlobsRequest(ULONG cbSecret, PUCHAR pbSecret, __int64 a3, UCHAR *a4)
{
  int v5; // eax
  unsigned int v9; // ebx
  DWORD v10; // eax
  const BYTE *v11; // r9
  NTSTATUS NonzeroLastError; // eax
  DWORD pcbComputedHash; // [rsp+40h] [rbp-49h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+48h] [rbp-41h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+50h] [rbp-39h] BYREF
  UCHAR pbInput[16]; // [rsp+58h] [rbp-31h] BYREF
  __int128 v18; // [rsp+68h] [rbp-21h]
  __int16 v19; // [rsp+78h] [rbp-11h]
  int v20; // [rsp+7Ah] [rbp-Fh]
  BYTE pbComputedHash[16]; // [rsp+80h] [rbp-9h] BYREF
  __int128 v22; // [rsp+90h] [rbp+7h]

  v5 = *(_DWORD *)(a3 + 16);
  phAlgorithm = 0;
  phHash = 0;
  v19 = 12;
  v20 = v5;
  *(__m128i *)pbInput = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v18 = *(_OWORD *)pbInput;
  v9 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA256", 0, 8u);
  if ( !v9 )
  {
    v9 = BCryptCreateHash(phAlgorithm, &phHash, 0, 0, pbSecret, cbSecret, 0);
    if ( !v9 )
    {
      v9 = BCryptHashData(phHash, pbInput, 0x26u, 0);
      if ( !v9 )
      {
        v10 = *(_DWORD *)(a3 + 4);
        if ( v10 )
        {
          v11 = *(const BYTE **)(a3 + 8);
          pcbComputedHash = 32;
          *(_OWORD *)pbComputedHash = 0;
          v22 = 0;
          if ( !CryptHashCertificate2(L"SHA256", 0, 0, v11, v10, pbComputedHash, &pcbComputedHash)
            || pcbComputedHash != 32 )
          {
            NonzeroLastError = _GetNonzeroLastError();
            goto LABEL_9;
          }
          v9 = BCryptHashData(phHash, pbComputedHash, 0x20u, 0);
          if ( v9 )
            goto LABEL_10;
        }
        NonzeroLastError = BCryptFinishHash(phHash, a4, 0x20u, 0);
LABEL_9:
        v9 = NonzeroLastError;
      }
    }
  }
LABEL_10:
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  return v9;
}

```

## disassembly

```asm
0x1800c9150  push    rbp
0x1800c9152  push    rbx
0x1800c9153  push    rsi
0x1800c9154  push    rdi
0x1800c9155  push    r14
0x1800c9157  push    r15
0x1800c9159  lea     rbp, [rsp-2Fh]
0x1800c915e  sub     rsp, 0B8h
0x1800c9165  mov     rax, cs:__security_cookie
0x1800c916c  xor     rax, rsp
0x1800c916f  mov     [rbp+57h+var_40], rax
0x1800c9173  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x1800c917b  mov     r15, r9
0x1800c917e  mov     eax, [r8+10h]
0x1800c9182  mov     rdi, r8
0x1800c9185  mov     r14, rdx
0x1800c9188  mov     [rbp+57h+phAlgorithm], 0
0x1800c9190  mov     esi, ecx
0x1800c9192  mov     [rbp+57h+phHash], 0
0x1800c919a  mov     r9d, 8; dwFlags
0x1800c91a0  mov     [rbp+57h+var_68], 0Ch
0x1800c91a6  xor     r8d, r8d; pszImplementation
0x1800c91a9  mov     [rbp+57h+var_66], eax
0x1800c91ac  lea     rdx, pwszCNGHashAlgid; "SHA256"
0x1800c91b3  lea     rcx, [rbp+57h+phAlgorithm]; phAlgorithm
0x1800c91b7  movups  xmmword ptr [rbp+57h+pbInput], xmm0
0x1800c91bb  movups  [rbp+57h+var_78], xmm0
0x1800c91bf  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1800c91c5  mov     ebx, eax
0x1800c91c7  test    eax, eax
0x1800c91c9  jnz     loc_1800C9291
0x1800c91cf  mov     rcx, [rbp+57h+phAlgorithm]; hAlgorithm
0x1800c91d3  lea     rdx, [rbp+57h+phHash]; phHash
0x1800c91d7  mov     [rsp+0E0h+dwFlags], eax; dwFlags
0x1800c91db  xor     r9d, r9d; cbHashObject
0x1800c91de  mov     [rsp+0E0h+cbSecret], esi; cbSecret
0x1800c91e2  xor     r8d, r8d; pbHashObject
0x1800c91e5  mov     [rsp+0E0h+pbSecret], r14; pbSecret
0x1800c91ea  call    cs:__imp_BCryptCreateHash
0x1800c91f0  mov     ebx, eax
0x1800c91f2  test    eax, eax
0x1800c91f4  jnz     loc_1800C9291
0x1800c91fa  mov     rcx, [rbp+57h+phHash]; hHash
0x1800c91fe  lea     r8d, [rax+26h]; cbInput
0x1800c9202  xor     r9d, r9d; dwFlags
0x1800c9205  lea     rdx, [rbp+57h+pbInput]; pbInput
0x1800c9209  call    cs:__imp_BCryptHashData
0x1800c920f  mov     ebx, eax
0x1800c9211  test    eax, eax
0x1800c9213  jnz     short loc_1800C9291
0x1800c9215  mov     eax, [rdi+4]
0x1800c9218  lea     esi, [rbx+20h]
0x1800c921b  test    eax, eax
0x1800c921d  jz      short loc_1800C927C
0x1800c921f  mov     r9, [rdi+8]; pbEncoded
0x1800c9223  lea     rdx, [rbp+57h+pcbComputedHash]
0x1800c9227  mov     qword ptr [rsp+0E0h+dwFlags], rdx; pcbComputedHash
0x1800c922c  lea     rcx, pwszCNGHashAlgid; "SHA256"
0x1800c9233  lea     rdx, [rbp+57h+pbComputedHash]
0x1800c9237  mov     [rbp+57h+pcbComputedHash], esi
0x1800c923a  mov     qword ptr [rsp+0E0h+cbSecret], rdx; pbComputedHash
0x1800c923f  xorps   xmm0, xmm0
0x1800c9242  xor     edx, edx; dwFlags
0x1800c9244  mov     dword ptr [rsp+0E0h+pbSecret], eax; cbEncoded
0x1800c9248  xor     r8d, r8d; pvReserved
0x1800c924b  movups  xmmword ptr [rbp+57h+pbComputedHash], xmm0
0x1800c924f  movups  [rbp+57h+var_50], xmm0
0x1800c9253  call    cs:__imp_CryptHashCertificate2
0x1800c9259  test    eax, eax
0x1800c925b  jz      short loc_1800C92CF
0x1800c925d  cmp     [rbp+57h+pcbComputedHash], esi
0x1800c9260  jnz     short loc_1800C92CF
0x1800c9262  mov     rcx, [rbp+57h+phHash]; hHash
0x1800c9266  lea     rdx, [rbp+57h+pbComputedHash]; pbInput
0x1800c926a  xor     r9d, r9d; dwFlags
0x1800c926d  mov     r8d, esi; cbInput
0x1800c9270  call    cs:__imp_BCryptHashData
0x1800c9276  mov     ebx, eax
0x1800c9278  test    eax, eax
0x1800c927a  jnz     short loc_1800C9291
0x1800c927c  mov     rcx, [rbp+57h+phHash]; hHash
0x1800c9280  xor     r9d, r9d; dwFlags
0x1800c9283  mov     r8d, esi; cbOutput
0x1800c9286  mov     rdx, r15; pbOutput
0x1800c9289  call    cs:__imp_BCryptFinishHash
0x1800c928f  mov     ebx, eax
0x1800c9291  mov     rcx, [rbp+57h+phHash]; hHash
0x1800c9295  test    rcx, rcx
0x1800c9298  jz      short loc_1800C92A0
0x1800c929a  call    cs:__imp_BCryptDestroyHash
0x1800c92a0  mov     rcx, [rbp+57h+phAlgorithm]; hAlgorithm
0x1800c92a4  test    rcx, rcx
0x1800c92a7  jz      short loc_1800C92B1
0x1800c92a9  xor     edx, edx; dwFlags
0x1800c92ab  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1800c92b1  mov     eax, ebx
0x1800c92b3  mov     rcx, [rbp+57h+var_40]
0x1800c92b7  xor     rcx, rsp; StackCookie
0x1800c92ba  call    __security_check_cookie
0x1800c92bf  add     rsp, 0B8h
0x1800c92c6  pop     r15
0x1800c92c8  pop     r14
0x1800c92ca  pop     rdi
0x1800c92cb  pop     rsi
0x1800c92cc  pop     rbx
0x1800c92cd  pop     rbp
0x1800c92ce  retn
0x1800c92cf  call    ?_GetNonzeroLastError@@YAKXZ; _GetNonzeroLastError(void)
0x1800c92d4  jmp     short loc_1800C928F
```
