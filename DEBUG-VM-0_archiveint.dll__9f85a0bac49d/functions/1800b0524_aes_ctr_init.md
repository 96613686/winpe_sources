# aes_ctr_init

- ea: `0x1800b0524`
- end: `0x1800b0726`
- name: `aes_ctr_init`
- size: `514`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800e8ee8`
- `0x1801165c4`
- `0x180116778`

## callees

- `0x180014fc0`
- `0x1800b0524`

## import_xrefs

- `bcrypt!BCryptGetProperty` at `0x1800b05ed`
- `bcrypt!BCryptGetProperty` at `0x1800b0633`
- `bcrypt!BCryptGetProperty` at `0x1800b05ed`
- `bcrypt!BCryptGetProperty` at `0x1800b0633`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800b05b9`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800b05b9`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800b0694`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800b0706`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800b0694`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800b0706`
- `bcrypt!BCryptSetProperty` at `0x1800b0684`
- `bcrypt!BCryptSetProperty` at `0x1800b0684`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x1800b06cc`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x1800b06cc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800b06a8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800b06a8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b0652`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b0652`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b0644`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b069a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b0644`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b069a`

## pseudocode

```c
__int64 __fastcall aes_ctr_init(__int64 a1, UCHAR *a2, __int64 a3)
{
  ULONG v3; // esi
  unsigned int v6; // ebx
  unsigned int v7; // ebx
  HANDLE ProcessHeap; // rax
  UCHAR *v9; // rax
  BCRYPT_ALG_HANDLE v10; // rcx
  UCHAR *v11; // rbx
  NTSTATUS v12; // eax
  BCRYPT_ALG_HANDLE v13; // rcx
  HANDLE v14; // rax
  __int64 result; // rax
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+40h] [rbp-30h] BYREF
  UCHAR v17[4]; // [rsp+48h] [rbp-28h] BYREF
  ULONG pcbResult; // [rsp+4Ch] [rbp-24h] BYREF
  BCRYPT_KEY_HANDLE phKey; // [rsp+50h] [rbp-20h] BYREF
  UCHAR pbOutput[8]; // [rsp+58h] [rbp-18h] BYREF
  int v21; // [rsp+60h] [rbp-10h]

  phAlgorithm = 0;
  phKey = 0;
  v3 = a3;
  *(_DWORD *)v17 = 0;
  pcbResult = 0;
  *(_QWORD *)pbOutput = 0;
  v21 = 0;
  *(_QWORD *)a1 = 0;
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 16) = 0;
  switch ( a3 )
  {
    case 16LL:
      v6 = 128;
      break;
    case 24LL:
      v6 = 192;
      break;
    case 32LL:
      v6 = 256;
      break;
    default:
      return 0xFFFFFFFFLL;
  }
  if ( BCryptOpenAlgorithmProvider(&phAlgorithm, L"AES", L"Microsoft Primitive Provider", 0) < 0 )
    return 0xFFFFFFFFLL;
  if ( BCryptGetProperty(phAlgorithm, L"KeyLengths", pbOutput, 0xCu, &pcbResult, 0) < 0
    || *(_DWORD *)pbOutput > v6
    || *(_DWORD *)&pbOutput[4] < v6
    || BCryptGetProperty(phAlgorithm, L"ObjectLength", v17, 4u, &pcbResult, 0) < 0 )
  {
    v10 = phAlgorithm;
    goto LABEL_19;
  }
  v7 = *(_DWORD *)v17;
  ProcessHeap = GetProcessHeap();
  v9 = (UCHAR *)HeapAlloc(ProcessHeap, 0, v7);
  v10 = phAlgorithm;
  v11 = v9;
  if ( !v9 )
  {
LABEL_19:
    BCryptCloseAlgorithmProvider(v10, 0);
    return 0xFFFFFFFFLL;
  }
  v12 = BCryptSetProperty(phAlgorithm, L"ChainingMode", (PUCHAR)L"ChainingModeECB", 0x20u, 0);
  v13 = phAlgorithm;
  if ( v12 >= 0 )
  {
    if ( BCryptGenerateSymmetricKey(phAlgorithm, &phKey, v11, *(ULONG *)v17, a2, v3, 0) >= 0 )
    {
      *(_QWORD *)a1 = phAlgorithm;
      *(_QWORD *)(a1 + 8) = phKey;
      *(_DWORD *)(a1 + 24) = *(_DWORD *)v17;
      result = 0;
      *(_QWORD *)(a1 + 16) = v11;
      *(_DWORD *)(a1 + 60) = 16;
      return result;
    }
    v13 = phAlgorithm;
  }
  BCryptCloseAlgorithmProvider(v13, 0);
  v14 = GetProcessHeap();
  HeapFree(v14, 0, v11);
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x1800b0524  push    rbp
0x1800b0526  push    rbx
0x1800b0527  push    rsi
0x1800b0528  push    rdi
0x1800b0529  push    r14
0x1800b052b  mov     rbp, rsp
0x1800b052e  sub     rsp, 70h
0x1800b0532  mov     rax, cs:__security_cookie
0x1800b0539  xor     rax, rsp
0x1800b053c  mov     [rbp+var_8], rax
0x1800b0540  xor     eax, eax
0x1800b0542  mov     [rbp+phAlgorithm], 0
0x1800b054a  mov     [rbp+phKey], 0
0x1800b0552  mov     rsi, r8
0x1800b0555  mov     dword ptr [rbp+var_28], 0
0x1800b055c  mov     r14, rdx
0x1800b055f  mov     [rbp+var_24], 0
0x1800b0566  mov     rdi, rcx
0x1800b0569  mov     qword ptr [rbp+pbOutput], rax
0x1800b056d  mov     [rbp+var_10], eax
0x1800b0570  mov     [rcx], rax
0x1800b0573  mov     [rcx+8], rax
0x1800b0577  mov     [rcx+10h], rax
0x1800b057b  cmp     r8, 10h
0x1800b057f  jz      short loc_1800B059F
0x1800b0581  cmp     r8, 18h
0x1800b0585  jz      short loc_1800B0598
0x1800b0587  cmp     r8, 20h ; ' '
0x1800b058b  jnz     loc_1800B070C
0x1800b0591  mov     ebx, 100h
0x1800b0596  jmp     short loc_1800B05A4
0x1800b0598  mov     ebx, 0C0h
0x1800b059d  jmp     short loc_1800B05A4
0x1800b059f  mov     ebx, 80h
0x1800b05a4  xor     r9d, r9d; dwFlags
0x1800b05a7  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x1800b05ae  lea     rdx, aAes; "AES"
0x1800b05b5  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x1800b05b9  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1800b05bf  test    eax, eax
0x1800b05c1  js      loc_1800B070C
0x1800b05c7  mov     rcx, [rbp+phAlgorithm]; hObject
0x1800b05cb  lea     rax, [rbp+var_24]
0x1800b05cf  mov     [rsp+70h+dwFlags], 0; dwFlags
0x1800b05d7  lea     r8, [rbp+pbOutput]; pbOutput
0x1800b05db  mov     r9d, 0Ch; cbOutput
0x1800b05e1  mov     [rsp+70h+pcbResult], rax; pcbResult
0x1800b05e6  lea     rdx, pszProperty; "KeyLengths"
0x1800b05ed  call    cs:__imp_BCryptGetProperty
0x1800b05f3  test    eax, eax
0x1800b05f5  js      loc_1800B0700
0x1800b05fb  cmp     dword ptr [rbp+pbOutput], ebx
0x1800b05fe  ja      loc_1800B0700
0x1800b0604  cmp     dword ptr [rbp+pbOutput+4], ebx
0x1800b0607  jb      loc_1800B0700
0x1800b060d  mov     rcx, [rbp+phAlgorithm]; hObject
0x1800b0611  lea     rax, [rbp+var_24]
0x1800b0615  mov     [rsp+70h+dwFlags], 0; dwFlags
0x1800b061d  lea     r8, [rbp+var_28]; pbOutput
0x1800b0621  mov     r9d, 4; cbOutput
0x1800b0627  mov     [rsp+70h+pcbResult], rax; pcbResult
0x1800b062c  lea     rdx, aObjectlength; "ObjectLength"
0x1800b0633  call    cs:__imp_BCryptGetProperty
0x1800b0639  test    eax, eax
0x1800b063b  js      loc_1800B0700
0x1800b0641  mov     ebx, dword ptr [rbp+var_28]
0x1800b0644  call    cs:__imp_GetProcessHeap
0x1800b064a  mov     r8d, ebx; dwBytes
0x1800b064d  xor     edx, edx; dwFlags
0x1800b064f  mov     rcx, rax; hHeap
0x1800b0652  call    cs:__imp_HeapAlloc
0x1800b0658  mov     rcx, [rbp+phAlgorithm]; hObject
0x1800b065c  mov     rbx, rax
0x1800b065f  test    rax, rax
0x1800b0662  jz      loc_1800B0704
0x1800b0668  mov     r9d, 20h ; ' '; cbInput
0x1800b066e  mov     dword ptr [rsp+70h+pcbResult], 0; dwFlags
0x1800b0676  lea     r8, pbInput; "ChainingModeECB"
0x1800b067d  lea     rdx, aChainingmode; "ChainingMode"
0x1800b0684  call    cs:__imp_BCryptSetProperty
0x1800b068a  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x1800b068e  test    eax, eax
0x1800b0690  jns     short loc_1800B06B0
0x1800b0692  xor     edx, edx; dwFlags
0x1800b0694  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1800b069a  call    cs:__imp_GetProcessHeap
0x1800b06a0  mov     r8, rbx; lpMem
0x1800b06a3  xor     edx, edx; dwFlags
0x1800b06a5  mov     rcx, rax; hHeap
0x1800b06a8  call    cs:__imp_HeapFree
0x1800b06ae  jmp     short loc_1800B070C
0x1800b06b0  mov     r9d, dword ptr [rbp+var_28]; cbKeyObject
0x1800b06b4  lea     rdx, [rbp+phKey]; phKey
0x1800b06b8  mov     [rsp+70h+var_40], 0; dwFlags
0x1800b06c0  mov     r8, rbx; pbKeyObject
0x1800b06c3  mov     [rsp+70h+dwFlags], esi; cbSecret
0x1800b06c7  mov     [rsp+70h+pcbResult], r14; pbSecret
0x1800b06cc  call    cs:__imp_BCryptGenerateSymmetricKey
0x1800b06d2  test    eax, eax
0x1800b06d4  jns     short loc_1800B06DC
0x1800b06d6  mov     rcx, [rbp+phAlgorithm]
0x1800b06da  jmp     short loc_1800B0692
0x1800b06dc  mov     rax, [rbp+phAlgorithm]
0x1800b06e0  mov     [rdi], rax
0x1800b06e3  mov     rax, [rbp+phKey]
0x1800b06e7  mov     [rdi+8], rax
0x1800b06eb  mov     eax, dword ptr [rbp+var_28]
0x1800b06ee  mov     [rdi+18h], eax
0x1800b06f1  xor     eax, eax
0x1800b06f3  mov     [rdi+10h], rbx
0x1800b06f7  mov     dword ptr [rdi+3Ch], 10h
0x1800b06fe  jmp     short loc_1800B070F
0x1800b0700  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x1800b0704  xor     edx, edx; dwFlags
0x1800b0706  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1800b070c  or      eax, 0FFFFFFFFh
0x1800b070f  mov     rcx, [rbp+var_8]
0x1800b0713  xor     rcx, rsp; StackCookie
0x1800b0716  call    __security_check_cookie
0x1800b071b  add     rsp, 70h
0x1800b071f  pop     r14
0x1800b0721  pop     rdi
0x1800b0722  pop     rsi
0x1800b0723  pop     rbx
0x1800b0724  pop     rbp
0x1800b0725  retn
```
