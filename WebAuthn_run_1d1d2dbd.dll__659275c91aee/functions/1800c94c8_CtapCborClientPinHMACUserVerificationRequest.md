# CtapCborClientPinHMACUserVerificationRequest

- ea: `0x1800c94c8`
- end: `0x1800c9605`
- name: `CtapCborClientPinHMACUserVerificationRequest`
- size: `317`
- prototype: `__int64 __fastcall(ULONG cbSecret, PUCHAR pbSecret)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800d9008`

## callees

- `0x180007f90`
- `0x18001cd78`
- `0x1800c94c8`
- `0x1800d42c4`

## import_xrefs

- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800c95f0`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800c95f0`
- `bcrypt!BCryptDestroyHash` at `0x1800c95df`
- `bcrypt!BCryptDestroyHash` at `0x1800c95df`
- `bcrypt!BCryptFinishHash` at `0x1800c95ce`
- `bcrypt!BCryptFinishHash` at `0x1800c95ce`
- `bcrypt!BCryptHashData` at `0x1800c955e`
- `bcrypt!BCryptHashData` at `0x1800c95ab`
- `bcrypt!BCryptHashData` at `0x1800c955e`
- `bcrypt!BCryptHashData` at `0x1800c95ab`
- `bcrypt!BCryptCreateHash` at `0x1800c9534`
- `bcrypt!BCryptCreateHash` at `0x1800c9534`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800c9508`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800c9508`

## pseudocode

```c
__int64 __fastcall CtapCborClientPinHMACUserVerificationRequest(ULONG cbSecret, PUCHAR pbSecret, __int64 a3, UCHAR *a4)
{
  unsigned int v8; // ebx
  __int64 v9; // rcx
  unsigned int v10; // eax
  NTSTATUS v11; // eax
  UCHAR pbInput[4]; // [rsp+40h] [rbp-28h] BYREF
  _BYTE v14[4]; // [rsp+44h] [rbp-24h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+48h] [rbp-20h] BYREF
  PUCHAR v16; // [rsp+50h] [rbp-18h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+58h] [rbp-10h] BYREF

  phAlgorithm = 0;
  phHash = 0;
  v8 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA256", 0, 8u);
  if ( !v8 )
  {
    v8 = BCryptCreateHash(phAlgorithm, &phHash, 0, 0, pbSecret, cbSecret, 0);
    if ( !v8 )
    {
      pbInput[0] = *(_BYTE *)a3;
      pbInput[1] = *(_BYTE *)(a3 + 4);
      v8 = BCryptHashData(phHash, pbInput, 2u, 0);
      if ( !v8 )
      {
        v9 = *(_QWORD *)(a3 + 8);
        if ( v9 )
        {
          *(_DWORD *)pbInput = 0;
          v16 = 0;
          v10 = CtapCborEncodeFingerprintSubCommandPara(v9, pbInput, &v16, v14);
          if ( v10 )
          {
            v11 = CtapCborErrorToWin32Error(v10);
LABEL_9:
            v8 = v11;
            goto LABEL_10;
          }
          v8 = BCryptHashData(phHash, v16, *(ULONG *)pbInput, 0);
          FidoFree(v16);
          if ( v8 )
            goto LABEL_10;
        }
        v11 = BCryptFinishHash(phHash, a4, 0x20u, 0);
        goto LABEL_9;
      }
    }
  }
LABEL_10:
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  return v8;
}

```

## disassembly

```asm
0x1800c94c8  push    rbp
0x1800c94ca  push    rbx
0x1800c94cb  push    rsi
0x1800c94cc  push    rdi
0x1800c94cd  push    r14
0x1800c94cf  push    r15
0x1800c94d1  mov     rbp, rsp
0x1800c94d4  sub     rsp, 68h
0x1800c94d8  mov     r15, r9
0x1800c94db  mov     [rbp+phAlgorithm], 0
0x1800c94e3  mov     rdi, r8
0x1800c94e6  mov     [rbp+phHash], 0
0x1800c94ee  mov     rsi, rdx
0x1800c94f1  mov     r14d, ecx
0x1800c94f4  mov     r9d, 8; dwFlags
0x1800c94fa  lea     rdx, pwszCNGHashAlgid; "SHA256"
0x1800c9501  xor     r8d, r8d; pszImplementation
0x1800c9504  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x1800c9508  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1800c950e  mov     ebx, eax
0x1800c9510  test    eax, eax
0x1800c9512  jnz     loc_1800C95D6
0x1800c9518  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x1800c951c  lea     rdx, [rbp+phHash]; phHash
0x1800c9520  mov     [rsp+68h+dwFlags], eax; dwFlags
0x1800c9524  xor     r9d, r9d; cbHashObject
0x1800c9527  mov     [rsp+68h+cbSecret], r14d; cbSecret
0x1800c952c  xor     r8d, r8d; pbHashObject
0x1800c952f  mov     [rsp+68h+pbSecret], rsi; pbSecret
0x1800c9534  call    cs:__imp_BCryptCreateHash
0x1800c953a  mov     ebx, eax
0x1800c953c  test    eax, eax
0x1800c953e  jnz     loc_1800C95D6
0x1800c9544  mov     al, [rdi]
0x1800c9546  lea     r8d, [rbx+2]; cbInput
0x1800c954a  mov     rcx, [rbp+phHash]; hHash
0x1800c954e  lea     rdx, [rbp+pbInput]; pbInput
0x1800c9552  mov     [rbp+pbInput], al
0x1800c9555  xor     r9d, r9d; dwFlags
0x1800c9558  mov     al, [rdi+4]
0x1800c955b  mov     [rbp+pbInput+1], al
0x1800c955e  call    cs:__imp_BCryptHashData
0x1800c9564  mov     ebx, eax
0x1800c9566  test    eax, eax
0x1800c9568  jnz     short loc_1800C95D6
0x1800c956a  mov     rcx, [rdi+8]
0x1800c956e  test    rcx, rcx
0x1800c9571  jz      short loc_1800C95C0
0x1800c9573  lea     r9, [rbp+var_24]
0x1800c9577  mov     dword ptr [rbp+pbInput], eax
0x1800c957a  lea     r8, [rbp+var_18]
0x1800c957e  mov     [rbp+var_18], 0
0x1800c9586  lea     rdx, [rbp+pbInput]
0x1800c958a  call    CtapCborEncodeFingerprintSubCommandPara
0x1800c958f  test    eax, eax
0x1800c9591  jz      short loc_1800C959C
0x1800c9593  mov     ecx, eax
0x1800c9595  call    CtapCborErrorToWin32Error
0x1800c959a  jmp     short loc_1800C95D4
0x1800c959c  mov     r8d, dword ptr [rbp+pbInput]; cbInput
0x1800c95a0  xor     r9d, r9d; dwFlags
0x1800c95a3  mov     rdx, [rbp+var_18]; pbInput
0x1800c95a7  mov     rcx, [rbp+phHash]; hHash
0x1800c95ab  call    cs:__imp_BCryptHashData
0x1800c95b1  mov     rcx, [rbp+var_18]; void *
0x1800c95b5  mov     ebx, eax
0x1800c95b7  call    ?FidoFree@@YAXPEAX@Z; FidoFree(void *)
0x1800c95bc  test    ebx, ebx
0x1800c95be  jnz     short loc_1800C95D6
0x1800c95c0  mov     rcx, [rbp+phHash]; hHash
0x1800c95c4  xor     r9d, r9d; dwFlags
0x1800c95c7  mov     rdx, r15; pbOutput
0x1800c95ca  lea     r8d, [r9+20h]; cbOutput
0x1800c95ce  call    cs:__imp_BCryptFinishHash
0x1800c95d4  mov     ebx, eax
0x1800c95d6  mov     rcx, [rbp+phHash]; hHash
0x1800c95da  test    rcx, rcx
0x1800c95dd  jz      short loc_1800C95E5
0x1800c95df  call    cs:__imp_BCryptDestroyHash
0x1800c95e5  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x1800c95e9  test    rcx, rcx
0x1800c95ec  jz      short loc_1800C95F6
0x1800c95ee  xor     edx, edx; dwFlags
0x1800c95f0  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1800c95f6  mov     eax, ebx
0x1800c95f8  add     rsp, 68h
0x1800c95fc  pop     r15
0x1800c95fe  pop     r14
0x1800c9600  pop     rdi
0x1800c9601  pop     rsi
0x1800c9602  pop     rbx
0x1800c9603  pop     rbp
0x1800c9604  retn
```
