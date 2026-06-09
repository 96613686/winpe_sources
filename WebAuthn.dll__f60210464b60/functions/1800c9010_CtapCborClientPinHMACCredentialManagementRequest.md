# CtapCborClientPinHMACCredentialManagementRequest

- ea: `0x1800c9010`
- end: `0x1800c9147`
- name: `CtapCborClientPinHMACCredentialManagementRequest`
- size: `311`
- prototype: `__int64 __fastcall(ULONG cbSecret, PUCHAR pbSecret)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800d8d68`

## callees

- `0x180007f90`
- `0x18001cd78`
- `0x1800c9010`
- `0x1800d3cc0`

## import_xrefs

- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800c9132`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800c9132`
- `bcrypt!BCryptDestroyHash` at `0x1800c9121`
- `bcrypt!BCryptDestroyHash` at `0x1800c9121`
- `bcrypt!BCryptFinishHash` at `0x1800c9110`
- `bcrypt!BCryptFinishHash` at `0x1800c9110`
- `bcrypt!BCryptHashData` at `0x1800c90a0`
- `bcrypt!BCryptHashData` at `0x1800c90ed`
- `bcrypt!BCryptHashData` at `0x1800c90a0`
- `bcrypt!BCryptHashData` at `0x1800c90ed`
- `bcrypt!BCryptCreateHash` at `0x1800c907c`
- `bcrypt!BCryptCreateHash` at `0x1800c907c`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800c9050`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800c9050`

## pseudocode

```c
__int64 __fastcall CtapCborClientPinHMACCredentialManagementRequest(
        ULONG cbSecret,
        PUCHAR pbSecret,
        __int64 a3,
        UCHAR *a4)
{
  unsigned int v8; // ebx
  __int64 v9; // rcx
  unsigned int v10; // eax
  NTSTATUS v11; // eax
  UCHAR pbInput[4]; // [rsp+40h] [rbp-38h] BYREF
  ULONG cbInput; // [rsp+44h] [rbp-34h] BYREF
  _BYTE v15[8]; // [rsp+48h] [rbp-30h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+50h] [rbp-28h] BYREF
  PUCHAR v17; // [rsp+58h] [rbp-20h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+60h] [rbp-18h] BYREF

  phAlgorithm = 0;
  phHash = 0;
  v8 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA256", 0, 8u);
  if ( !v8 )
  {
    v8 = BCryptCreateHash(phAlgorithm, &phHash, 0, 0, pbSecret, cbSecret, 0);
    if ( !v8 )
    {
      pbInput[0] = *(_BYTE *)a3;
      v8 = BCryptHashData(phHash, pbInput, 1u, 0);
      if ( !v8 )
      {
        v9 = *(_QWORD *)(a3 + 8);
        if ( v9 )
        {
          cbInput = 0;
          v17 = 0;
          v10 = CtapCborEncodeCredentialManagementSubCommandPara(v9, &cbInput, &v17, v15);
          if ( v10 )
          {
            v11 = CtapCborErrorToWin32Error(v10);
LABEL_9:
            v8 = v11;
            goto LABEL_10;
          }
          v8 = BCryptHashData(phHash, v17, cbInput, 0);
          FidoFree(v17);
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
0x1800c9010  push    rbp
0x1800c9012  push    rbx
0x1800c9013  push    rsi
0x1800c9014  push    rdi
0x1800c9015  push    r14
0x1800c9017  push    r15
0x1800c9019  mov     rbp, rsp
0x1800c901c  sub     rsp, 78h
0x1800c9020  mov     r15, r9
0x1800c9023  mov     [rbp+phAlgorithm], 0
0x1800c902b  mov     rdi, r8
0x1800c902e  mov     [rbp+phHash], 0
0x1800c9036  mov     rsi, rdx
0x1800c9039  mov     r14d, ecx
0x1800c903c  mov     r9d, 8; dwFlags
0x1800c9042  lea     rdx, pwszCNGHashAlgid; "SHA256"
0x1800c9049  xor     r8d, r8d; pszImplementation
0x1800c904c  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x1800c9050  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1800c9056  mov     ebx, eax
0x1800c9058  test    eax, eax
0x1800c905a  jnz     loc_1800C9118
0x1800c9060  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x1800c9064  lea     rdx, [rbp+phHash]; phHash
0x1800c9068  mov     [rsp+78h+dwFlags], eax; dwFlags
0x1800c906c  xor     r9d, r9d; cbHashObject
0x1800c906f  mov     [rsp+78h+cbSecret], r14d; cbSecret
0x1800c9074  xor     r8d, r8d; pbHashObject
0x1800c9077  mov     [rsp+78h+pbSecret], rsi; pbSecret
0x1800c907c  call    cs:__imp_BCryptCreateHash
0x1800c9082  mov     ebx, eax
0x1800c9084  test    eax, eax
0x1800c9086  jnz     loc_1800C9118
0x1800c908c  mov     al, [rdi]
0x1800c908e  lea     r8d, [rbx+1]; cbInput
0x1800c9092  mov     rcx, [rbp+phHash]; hHash
0x1800c9096  lea     rdx, [rbp+pbInput]; pbInput
0x1800c909a  xor     r9d, r9d; dwFlags
0x1800c909d  mov     [rbp+pbInput], al
0x1800c90a0  call    cs:__imp_BCryptHashData
0x1800c90a6  mov     ebx, eax
0x1800c90a8  test    eax, eax
0x1800c90aa  jnz     short loc_1800C9118
0x1800c90ac  mov     rcx, [rdi+8]
0x1800c90b0  test    rcx, rcx
0x1800c90b3  jz      short loc_1800C9102
0x1800c90b5  lea     r9, [rbp+var_30]
0x1800c90b9  mov     [rbp+cbInput], eax
0x1800c90bc  lea     r8, [rbp+var_20]
0x1800c90c0  mov     [rbp+var_20], 0
0x1800c90c8  lea     rdx, [rbp+cbInput]
0x1800c90cc  call    CtapCborEncodeCredentialManagementSubCommandPara
0x1800c90d1  test    eax, eax
0x1800c90d3  jz      short loc_1800C90DE
0x1800c90d5  mov     ecx, eax
0x1800c90d7  call    CtapCborErrorToWin32Error
0x1800c90dc  jmp     short loc_1800C9116
0x1800c90de  mov     r8d, [rbp+cbInput]; cbInput
0x1800c90e2  xor     r9d, r9d; dwFlags
0x1800c90e5  mov     rdx, [rbp+var_20]; pbInput
0x1800c90e9  mov     rcx, [rbp+phHash]; hHash
0x1800c90ed  call    cs:__imp_BCryptHashData
0x1800c90f3  mov     rcx, [rbp+var_20]; void *
0x1800c90f7  mov     ebx, eax
0x1800c90f9  call    ?FidoFree@@YAXPEAX@Z; FidoFree(void *)
0x1800c90fe  test    ebx, ebx
0x1800c9100  jnz     short loc_1800C9118
0x1800c9102  mov     rcx, [rbp+phHash]; hHash
0x1800c9106  xor     r9d, r9d; dwFlags
0x1800c9109  mov     rdx, r15; pbOutput
0x1800c910c  lea     r8d, [r9+20h]; cbOutput
0x1800c9110  call    cs:__imp_BCryptFinishHash
0x1800c9116  mov     ebx, eax
0x1800c9118  mov     rcx, [rbp+phHash]; hHash
0x1800c911c  test    rcx, rcx
0x1800c911f  jz      short loc_1800C9127
0x1800c9121  call    cs:__imp_BCryptDestroyHash
0x1800c9127  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x1800c912b  test    rcx, rcx
0x1800c912e  jz      short loc_1800C9138
0x1800c9130  xor     edx, edx; dwFlags
0x1800c9132  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1800c9138  mov     eax, ebx
0x1800c913a  add     rsp, 78h
0x1800c913e  pop     r15
0x1800c9140  pop     r14
0x1800c9142  pop     rdi
0x1800c9143  pop     rsi
0x1800c9144  pop     rbx
0x1800c9145  pop     rbp
0x1800c9146  retn
```
