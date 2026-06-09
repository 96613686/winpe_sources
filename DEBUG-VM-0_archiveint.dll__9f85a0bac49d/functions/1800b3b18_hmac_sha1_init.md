# __hmac_sha1_init

- ea: `0x1800b3b18`
- end: `0x1800b3c60`
- name: `__hmac_sha1_init`
- size: `328`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800e8ee8`
- `0x1801165c4`
- `0x180116778`

## callees

- `0x1800b3b18`

## import_xrefs

- `bcrypt!BCryptGetProperty` at `0x1800b3bab`
- `bcrypt!BCryptGetProperty` at `0x1800b3bab`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800b3b73`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800b3b73`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800b3bbb`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800b3c11`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800b3bbb`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800b3c11`
- `bcrypt!BCryptCreateHash` at `0x1800b3c01`
- `bcrypt!BCryptCreateHash` at `0x1800b3c01`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800b3c25`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800b3c25`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b3bd4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b3bd4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b3bc6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b3c17`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b3bc6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b3c17`

## pseudocode

```c
__int64 __fastcall _hmac_sha1_init(__int64 a1, UCHAR *a2, ULONG a3)
{
  __int64 result; // rax
  BCRYPT_ALG_HANDLE v7; // rcx
  unsigned int v8; // ebx
  HANDLE ProcessHeap; // rax
  LPVOID v10; // rax
  void *v11; // rbx
  HANDLE v12; // rax
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+40h] [rbp-10h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+48h] [rbp-8h] BYREF
  unsigned int pbOutput; // [rsp+70h] [rbp+20h] BYREF
  ULONG pcbResult; // [rsp+88h] [rbp+38h] BYREF

  *(_QWORD *)a1 = 0;
  phAlgorithm = 0;
  phHash = 0;
  pbOutput = 0;
  pcbResult = 0;
  if ( BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA1", L"Microsoft Primitive Provider", 8u) < 0 )
    return 0xFFFFFFFFLL;
  if ( BCryptGetProperty(phAlgorithm, L"HashDigestLength", (PUCHAR)&pbOutput, 4u, &pcbResult, 0) < 0 )
  {
    v7 = phAlgorithm;
LABEL_5:
    BCryptCloseAlgorithmProvider(v7, 0);
    return 0xFFFFFFFFLL;
  }
  v8 = pbOutput;
  ProcessHeap = GetProcessHeap();
  v10 = HeapAlloc(ProcessHeap, 0, v8);
  v7 = phAlgorithm;
  v11 = v10;
  if ( !v10 )
    goto LABEL_5;
  if ( BCryptCreateHash(phAlgorithm, &phHash, 0, 0, a2, a3, 0x20u) < 0 )
  {
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
    v12 = GetProcessHeap();
    HeapFree(v12, 0, v11);
    return 0xFFFFFFFFLL;
  }
  *(_QWORD *)a1 = phAlgorithm;
  *(_QWORD *)(a1 + 8) = phHash;
  *(_DWORD *)(a1 + 16) = pbOutput;
  result = 0;
  *(_QWORD *)(a1 + 24) = v11;
  return result;
}

```

## disassembly

```asm
0x1800b3b18  mov     [rsp-18h+arg_8], rbx
0x1800b3b1d  mov     [rsp-18h+arg_10], rsi
0x1800b3b22  push    rbp
0x1800b3b23  push    rdi
0x1800b3b24  push    r14
0x1800b3b26  mov     rbp, rsp
0x1800b3b29  sub     rsp, 50h
0x1800b3b2d  mov     rsi, r8
0x1800b3b30  mov     qword ptr [rcx], 0
0x1800b3b37  mov     r14, rdx
0x1800b3b3a  mov     [rbp+phAlgorithm], 0
0x1800b3b42  mov     rdi, rcx
0x1800b3b45  mov     [rbp+phHash], 0
0x1800b3b4d  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x1800b3b54  mov     [rbp+pbOutput], 0
0x1800b3b5b  lea     rdx, aSha1; "SHA1"
0x1800b3b62  mov     [rbp+arg_18], 0
0x1800b3b69  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x1800b3b6d  mov     r9d, 8; dwFlags
0x1800b3b73  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1800b3b79  test    eax, eax
0x1800b3b7b  jns     short loc_1800B3B85
0x1800b3b7d  or      eax, 0FFFFFFFFh
0x1800b3b80  jmp     loc_1800B3C4B
0x1800b3b85  mov     rcx, [rbp+phAlgorithm]; hObject
0x1800b3b89  lea     rax, [rbp+arg_18]
0x1800b3b8d  mov     [rsp+50h+dwFlags], 0; dwFlags
0x1800b3b95  lea     r8, [rbp+pbOutput]; pbOutput
0x1800b3b99  mov     r9d, 4; cbOutput
0x1800b3b9f  mov     [rsp+50h+pcbResult], rax; pcbResult
0x1800b3ba4  lea     rdx, aHashdigestleng; "HashDigestLength"
0x1800b3bab  call    cs:__imp_BCryptGetProperty
0x1800b3bb1  test    eax, eax
0x1800b3bb3  jns     short loc_1800B3BC3
0x1800b3bb5  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x1800b3bb9  xor     edx, edx; dwFlags
0x1800b3bbb  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1800b3bc1  jmp     short loc_1800B3B7D
0x1800b3bc3  mov     ebx, [rbp+pbOutput]
0x1800b3bc6  call    cs:__imp_GetProcessHeap
0x1800b3bcc  mov     r8d, ebx; dwBytes
0x1800b3bcf  xor     edx, edx; dwFlags
0x1800b3bd1  mov     rcx, rax; hHeap
0x1800b3bd4  call    cs:__imp_HeapAlloc
0x1800b3bda  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x1800b3bde  mov     rbx, rax
0x1800b3be1  test    rax, rax
0x1800b3be4  jz      short loc_1800B3BB9
0x1800b3be6  mov     [rsp+50h+var_20], 20h ; ' '; dwFlags
0x1800b3bee  lea     rdx, [rbp+phHash]; phHash
0x1800b3bf2  mov     [rsp+50h+dwFlags], esi; cbSecret
0x1800b3bf6  xor     r9d, r9d; cbHashObject
0x1800b3bf9  xor     r8d, r8d; pbHashObject
0x1800b3bfc  mov     [rsp+50h+pcbResult], r14; pbSecret
0x1800b3c01  call    cs:__imp_BCryptCreateHash
0x1800b3c07  test    eax, eax
0x1800b3c09  jns     short loc_1800B3C30
0x1800b3c0b  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x1800b3c0f  xor     edx, edx; dwFlags
0x1800b3c11  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1800b3c17  call    cs:__imp_GetProcessHeap
0x1800b3c1d  mov     r8, rbx; lpMem
0x1800b3c20  xor     edx, edx; dwFlags
0x1800b3c22  mov     rcx, rax; hHeap
0x1800b3c25  call    cs:__imp_HeapFree
0x1800b3c2b  jmp     loc_1800B3B7D
0x1800b3c30  mov     rax, [rbp+phAlgorithm]
0x1800b3c34  mov     [rdi], rax
0x1800b3c37  mov     rax, [rbp+phHash]
0x1800b3c3b  mov     [rdi+8], rax
0x1800b3c3f  mov     eax, [rbp+pbOutput]
0x1800b3c42  mov     [rdi+10h], eax
0x1800b3c45  xor     eax, eax
0x1800b3c47  mov     [rdi+18h], rbx
0x1800b3c4b  lea     r11, [rsp+50h+var_s0]
0x1800b3c50  mov     rbx, [r11+28h]
0x1800b3c54  mov     rsi, [r11+30h]
0x1800b3c58  mov     rsp, r11
0x1800b3c5b  pop     r14
0x1800b3c5d  pop     rdi
0x1800b3c5e  pop     rbp
0x1800b3c5f  retn
```
