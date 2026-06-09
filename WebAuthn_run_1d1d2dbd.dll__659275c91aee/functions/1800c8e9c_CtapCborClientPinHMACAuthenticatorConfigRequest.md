# CtapCborClientPinHMACAuthenticatorConfigRequest

- ea: `0x1800c8e9c`
- end: `0x1800c9008`
- name: `CtapCborClientPinHMACAuthenticatorConfigRequest`
- size: `364`
- prototype: `__int64 __fastcall(ULONG cbSecret, PUCHAR pbSecret)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800d8d68`

## callees

- `0x180007f90`
- `0x18001cd78`
- `0x1800c8e9c`
- `0x1800d6b18`
- `0x18013c090`

## import_xrefs

- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800c8fe4`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800c8fe4`
- `bcrypt!BCryptDestroyHash` at `0x1800c8fd3`
- `bcrypt!BCryptDestroyHash` at `0x1800c8fd3`
- `bcrypt!BCryptFinishHash` at `0x1800c8fc2`
- `bcrypt!BCryptFinishHash` at `0x1800c8fc2`
- `bcrypt!BCryptHashData` at `0x1800c8f52`
- `bcrypt!BCryptHashData` at `0x1800c8f9f`
- `bcrypt!BCryptHashData` at `0x1800c8f52`
- `bcrypt!BCryptHashData` at `0x1800c8f9f`
- `bcrypt!BCryptCreateHash` at `0x1800c8f33`
- `bcrypt!BCryptCreateHash` at `0x1800c8f33`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800c8f08`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800c8f08`

## pseudocode

```c
__int64 __fastcall CtapCborClientPinHMACAuthenticatorConfigRequest(
        ULONG cbSecret,
        PUCHAR pbSecret,
        char *a3,
        UCHAR *a4)
{
  unsigned int v8; // ebx
  __int64 v9; // rcx
  unsigned int v10; // eax
  NTSTATUS v11; // eax
  ULONG cbInput; // [rsp+40h] [rbp-39h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+48h] [rbp-31h] BYREF
  PUCHAR v15; // [rsp+50h] [rbp-29h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+58h] [rbp-21h] BYREF
  _BYTE v17[8]; // [rsp+60h] [rbp-19h] BYREF
  UCHAR pbInput[16]; // [rsp+68h] [rbp-11h] BYREF
  __int128 v19; // [rsp+78h] [rbp-1h]
  char v20; // [rsp+88h] [rbp+Fh]
  char v21; // [rsp+89h] [rbp+10h]

  v21 = *a3;
  phAlgorithm = 0;
  phHash = 0;
  v20 = 13;
  *(__m128i *)pbInput = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v19 = *(_OWORD *)pbInput;
  v8 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA256", 0, 8u);
  if ( !v8 )
  {
    v8 = BCryptCreateHash(phAlgorithm, &phHash, 0, 0, pbSecret, cbSecret, 0);
    if ( !v8 )
    {
      v8 = BCryptHashData(phHash, pbInput, 0x22u, 0);
      if ( !v8 )
      {
        v9 = *((_QWORD *)a3 + 2);
        if ( v9 )
        {
          cbInput = 0;
          v15 = 0;
          v10 = CtapCborEncodeSetMinPinLengthSubCommandPara(v9, &cbInput, &v15, v17);
          if ( v10 )
          {
            v11 = CtapCborErrorToWin32Error(v10);
LABEL_9:
            v8 = v11;
            goto LABEL_10;
          }
          v8 = BCryptHashData(phHash, v15, cbInput, 0);
          FidoFree(v15);
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
0x1800c8e9c  push    rbp
0x1800c8e9e  push    rbx
0x1800c8e9f  push    rsi
0x1800c8ea0  push    rdi
0x1800c8ea1  push    r14
0x1800c8ea3  push    r15
0x1800c8ea5  lea     rbp, [rsp-2Fh]
0x1800c8eaa  sub     rsp, 0A8h
0x1800c8eb1  mov     rax, cs:__security_cookie
0x1800c8eb8  xor     rax, rsp
0x1800c8ebb  mov     [rbp+57h+var_40], rax
0x1800c8ebf  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x1800c8ec7  mov     r15, r9
0x1800c8eca  mov     al, [r8]
0x1800c8ecd  mov     rdi, r8
0x1800c8ed0  mov     r14, rdx
0x1800c8ed3  mov     [rbp+57h+var_47], al
0x1800c8ed6  mov     esi, ecx
0x1800c8ed8  mov     [rbp+57h+phAlgorithm], 0
0x1800c8ee0  mov     r9d, 8; dwFlags
0x1800c8ee6  mov     [rbp+57h+phHash], 0
0x1800c8eee  xor     r8d, r8d; pszImplementation
0x1800c8ef1  mov     [rbp+57h+var_48], 0Dh
0x1800c8ef5  lea     rdx, pwszCNGHashAlgid; "SHA256"
0x1800c8efc  lea     rcx, [rbp+57h+phAlgorithm]; phAlgorithm
0x1800c8f00  movups  xmmword ptr [rbp+57h+pbInput], xmm0
0x1800c8f04  movups  [rbp+57h+var_58], xmm0
0x1800c8f08  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1800c8f0e  mov     ebx, eax
0x1800c8f10  test    eax, eax
0x1800c8f12  jnz     loc_1800C8FCA
0x1800c8f18  mov     rcx, [rbp+57h+phAlgorithm]; hAlgorithm
0x1800c8f1c  lea     rdx, [rbp+57h+phHash]; phHash
0x1800c8f20  mov     [rsp+0D0h+dwFlags], eax; dwFlags
0x1800c8f24  xor     r9d, r9d; cbHashObject
0x1800c8f27  mov     [rsp+0D0h+cbSecret], esi; cbSecret
0x1800c8f2b  xor     r8d, r8d; pbHashObject
0x1800c8f2e  mov     [rsp+0D0h+pbSecret], r14; pbSecret
0x1800c8f33  call    cs:__imp_BCryptCreateHash
0x1800c8f39  mov     ebx, eax
0x1800c8f3b  test    eax, eax
0x1800c8f3d  jnz     loc_1800C8FCA
0x1800c8f43  mov     rcx, [rbp+57h+phHash]; hHash
0x1800c8f47  lea     r8d, [rax+22h]; cbInput
0x1800c8f4b  xor     r9d, r9d; dwFlags
0x1800c8f4e  lea     rdx, [rbp+57h+pbInput]; pbInput
0x1800c8f52  call    cs:__imp_BCryptHashData
0x1800c8f58  mov     ebx, eax
0x1800c8f5a  test    eax, eax
0x1800c8f5c  jnz     short loc_1800C8FCA
0x1800c8f5e  mov     rcx, [rdi+10h]
0x1800c8f62  test    rcx, rcx
0x1800c8f65  jz      short loc_1800C8FB4
0x1800c8f67  lea     r9, [rbp+57h+var_70]
0x1800c8f6b  mov     [rbp+57h+cbInput], eax
0x1800c8f6e  lea     r8, [rbp+57h+var_80]
0x1800c8f72  mov     [rbp+57h+var_80], 0
0x1800c8f7a  lea     rdx, [rbp+57h+cbInput]
0x1800c8f7e  call    CtapCborEncodeSetMinPinLengthSubCommandPara
0x1800c8f83  test    eax, eax
0x1800c8f85  jz      short loc_1800C8F90
0x1800c8f87  mov     ecx, eax
0x1800c8f89  call    CtapCborErrorToWin32Error
0x1800c8f8e  jmp     short loc_1800C8FC8
0x1800c8f90  mov     r8d, [rbp+57h+cbInput]; cbInput
0x1800c8f94  xor     r9d, r9d; dwFlags
0x1800c8f97  mov     rdx, [rbp+57h+var_80]; pbInput
0x1800c8f9b  mov     rcx, [rbp+57h+phHash]; hHash
0x1800c8f9f  call    cs:__imp_BCryptHashData
0x1800c8fa5  mov     rcx, [rbp+57h+var_80]; void *
0x1800c8fa9  mov     ebx, eax
0x1800c8fab  call    ?FidoFree@@YAXPEAX@Z; FidoFree(void *)
0x1800c8fb0  test    ebx, ebx
0x1800c8fb2  jnz     short loc_1800C8FCA
0x1800c8fb4  mov     rcx, [rbp+57h+phHash]; hHash
0x1800c8fb8  xor     r9d, r9d; dwFlags
0x1800c8fbb  mov     rdx, r15; pbOutput
0x1800c8fbe  lea     r8d, [r9+20h]; cbOutput
0x1800c8fc2  call    cs:__imp_BCryptFinishHash
0x1800c8fc8  mov     ebx, eax
0x1800c8fca  mov     rcx, [rbp+57h+phHash]; hHash
0x1800c8fce  test    rcx, rcx
0x1800c8fd1  jz      short loc_1800C8FD9
0x1800c8fd3  call    cs:__imp_BCryptDestroyHash
0x1800c8fd9  mov     rcx, [rbp+57h+phAlgorithm]; hAlgorithm
0x1800c8fdd  test    rcx, rcx
0x1800c8fe0  jz      short loc_1800C8FEA
0x1800c8fe2  xor     edx, edx; dwFlags
0x1800c8fe4  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1800c8fea  mov     eax, ebx
0x1800c8fec  mov     rcx, [rbp+57h+var_40]
0x1800c8ff0  xor     rcx, rsp; StackCookie
0x1800c8ff3  call    __security_check_cookie
0x1800c8ff8  add     rsp, 0A8h
0x1800c8fff  pop     r15
0x1800c9001  pop     r14
0x1800c9003  pop     rdi
0x1800c9004  pop     rsi
0x1800c9005  pop     rbx
0x1800c9006  pop     rbp
0x1800c9007  retn
```
