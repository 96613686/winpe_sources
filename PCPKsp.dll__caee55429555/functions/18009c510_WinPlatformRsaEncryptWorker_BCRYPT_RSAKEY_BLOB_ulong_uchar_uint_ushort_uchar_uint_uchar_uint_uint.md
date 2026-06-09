# WinPlatformRsaEncryptWorker(_BCRYPT_RSAKEY_BLOB *,ulong,uchar *,uint,ushort,uchar *,uint,uchar *,uint,uint *)

- ea: `0x18009c510`
- end: `0x18009c6b9`
- name: `?WinPlatformRsaEncryptWorker@@YAJPEAU_BCRYPT_RSAKEY_BLOB@@KPEAEIG1I1IPEAI@Z`
- size: `425`
- prototype: `__int64 __usercall@<rax>(PUCHAR pbInput@<rcx>, unsigned int@<edx>, unsigned __int8 *@<r8>, unsigned int@<r9d>, unsigned __int16, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18009c510`

## import_xrefs

- `bcrypt!BCryptImportKeyPair` at `0x18009c5a1`
- `bcrypt!BCryptImportKeyPair` at `0x18009c5a1`
- `bcrypt!BCryptEncrypt` at `0x18009c659`
- `bcrypt!BCryptEncrypt` at `0x18009c659`
- `bcrypt!BCryptDestroyKey` at `0x18009c677`
- `bcrypt!BCryptDestroyKey` at `0x18009c677`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18009c68e`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18009c68e`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18009c555`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18009c555`

## pseudocode

```c
__int64 __fastcall WinPlatformRsaEncryptWorker(
        PUCHAR pbInput,
        int a2,
        unsigned __int8 *a3,
        ULONG a4,
        unsigned __int16 a5,
        unsigned __int8 *a6,
        unsigned int a7,
        unsigned __int8 *pbOutput,
        ULONG cbOutput,
        unsigned int *pcbResult)
{
  NTSTATUS v14; // ebx
  NTSTATUS v15; // eax
  const wchar_t *v16; // rax
  BCRYPT_KEY_HANDLE phKey; // [rsp+50h] [rbp-30h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+58h] [rbp-28h] BYREF
  _QWORD pPaddingInfo[2]; // [rsp+60h] [rbp-20h] BYREF
  unsigned int v21; // [rsp+70h] [rbp-10h]
  int v22; // [rsp+74h] [rbp-Ch]

  phAlgorithm = 0;
  phKey = 0;
  v14 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"RSA", L"Microsoft Primitive Provider", 0);
  if ( v14 >= 0 )
  {
    v14 = BCryptImportKeyPair(
            phAlgorithm,
            0,
            L"RSAPUBLICBLOB",
            &phKey,
            pbInput,
            *((_DWORD *)pbInput + 3) + 24 + *((_DWORD *)pbInput + 2),
            0);
    if ( v14 >= 0 )
    {
      if ( a2 == 2 )
      {
        v15 = BCryptEncrypt(phKey, a3, a4, 0, 0, 0, pbOutput, cbOutput, pcbResult, 2u);
LABEL_12:
        v14 = v15;
        goto LABEL_14;
      }
      if ( a2 == 4 )
      {
        if ( a5 != 11 && a5 != 4 )
        {
          v14 = -1073741811;
          goto LABEL_14;
        }
        v22 = 0;
        v16 = L"SHA256";
        if ( a5 != 11 )
          v16 = L"SHA1";
        pPaddingInfo[0] = v16;
        pPaddingInfo[1] = a6;
        v21 = a7;
        v15 = BCryptEncrypt(phKey, a3, a4, pPaddingInfo, 0, 0, pbOutput, cbOutput, pcbResult, 4u);
        goto LABEL_12;
      }
      v14 = -1073741637;
    }
  }
LABEL_14:
  if ( phKey )
    BCryptDestroyKey(phKey);
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  if ( v14 )
    *pcbResult = 0;
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18009c510  push    rbp
0x18009c512  push    rbx
0x18009c513  push    rsi
0x18009c514  push    rdi
0x18009c515  push    r12
0x18009c517  push    r14
0x18009c519  push    r15
0x18009c51b  mov     rbp, rsp
0x18009c51e  sub     rsp, 80h
0x18009c525  mov     r15d, r9d
0x18009c528  mov     [rbp+phAlgorithm], 0
0x18009c530  mov     r12, r8
0x18009c533  mov     [rbp+phKey], 0
0x18009c53b  mov     edi, edx
0x18009c53d  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x18009c544  mov     r14, rcx
0x18009c547  lea     rdx, aRsa; "RSA"
0x18009c54e  xor     r9d, r9d; dwFlags
0x18009c551  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x18009c555  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18009c55c  nop     dword ptr [rax+rax+00h]
0x18009c561  mov     rsi, [rbp+arg_48]
0x18009c568  mov     ebx, eax
0x18009c56a  test    eax, eax
0x18009c56c  js      loc_18009C66E
0x18009c572  mov     ecx, [r14+0Ch]
0x18009c576  lea     r9, [rbp+phKey]; phKey
0x18009c57a  mov     edx, [r14+8]
0x18009c57e  lea     r8, aRsapublicblob; "RSAPUBLICBLOB"
0x18009c585  add     ecx, 18h
0x18009c588  mov     [rsp+80h+dwFlags], 0; dwFlags
0x18009c590  add     edx, ecx
0x18009c592  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x18009c596  mov     [rsp+80h+cbInput], edx; cbInput
0x18009c59a  xor     edx, edx; hImportKey
0x18009c59c  mov     [rsp+80h+pbInput], r14; pbInput
0x18009c5a1  call    cs:__imp_BCryptImportKeyPair
0x18009c5a8  nop     dword ptr [rax+rax+00h]
0x18009c5ad  mov     ebx, eax
0x18009c5af  test    eax, eax
0x18009c5b1  js      loc_18009C66E
0x18009c5b7  cmp     edi, 2
0x18009c5ba  jnz     short loc_18009C5C5
0x18009c5bc  mov     [rsp+80h+var_38], edi
0x18009c5c0  xor     r9d, r9d
0x18009c5c3  jmp     short loc_18009C626
0x18009c5c5  mov     r8d, 4
0x18009c5cb  cmp     edi, r8d
0x18009c5ce  jnz     loc_18009C669
0x18009c5d4  movzx   ecx, [rbp+arg_20]
0x18009c5d8  cmp     cx, 0Bh
0x18009c5dc  jz      short loc_18009C5EE
0x18009c5de  cmp     cx, r8w
0x18009c5e2  jz      short loc_18009C5EE
0x18009c5e4  mov     ebx, 0C000000Dh
0x18009c5e9  jmp     loc_18009C66E
0x18009c5ee  cmp     cx, 0Bh
0x18009c5f2  mov     [rbp+var_C], 0
0x18009c5f9  lea     rax, aSha256_0; "SHA256"
0x18009c600  mov     [rsp+80h+var_38], r8d; dwFlags
0x18009c605  lea     rdx, aSha1_0; "SHA1"
0x18009c60c  cmovnz  rax, rdx
0x18009c610  lea     r9, [rbp+pPaddingInfo]; pPaddingInfo
0x18009c614  mov     [rbp+pPaddingInfo], rax
0x18009c618  mov     rax, [rbp+arg_28]
0x18009c61c  mov     [rbp+var_18], rax
0x18009c620  mov     eax, [rbp+arg_30]
0x18009c623  mov     [rbp+var_10], eax
0x18009c626  mov     eax, [rbp+arg_40]
0x18009c62c  mov     r8d, r15d; cbInput
0x18009c62f  mov     rcx, [rbp+phKey]; hKey
0x18009c633  mov     rdx, r12; pbInput
0x18009c636  mov     [rsp+80h+pcbResult], rsi; pcbResult
0x18009c63b  mov     [rsp+80h+cbOutput], eax; cbOutput
0x18009c63f  mov     rax, [rbp+pbOutput]
0x18009c643  mov     qword ptr [rsp+80h+dwFlags], rax; pbOutput
0x18009c648  mov     [rsp+80h+cbInput], 0; cbIV
0x18009c650  mov     [rsp+80h+pbInput], 0; pbIV
0x18009c659  call    cs:__imp_BCryptEncrypt
0x18009c660  nop     dword ptr [rax+rax+00h]
0x18009c665  mov     ebx, eax
0x18009c667  jmp     short loc_18009C66E
0x18009c669  mov     ebx, 0C00000BBh
0x18009c66e  mov     rcx, [rbp+phKey]; hKey
0x18009c672  test    rcx, rcx
0x18009c675  jz      short loc_18009C683
0x18009c677  call    cs:__imp_BCryptDestroyKey
0x18009c67e  nop     dword ptr [rax+rax+00h]
0x18009c683  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x18009c687  test    rcx, rcx
0x18009c68a  jz      short loc_18009C69A
0x18009c68c  xor     edx, edx; dwFlags
0x18009c68e  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18009c695  nop     dword ptr [rax+rax+00h]
0x18009c69a  test    ebx, ebx
0x18009c69c  jz      short loc_18009C6A4
0x18009c69e  mov     dword ptr [rsi], 0
0x18009c6a4  mov     eax, ebx
0x18009c6a6  add     rsp, 80h
0x18009c6ad  pop     r15
0x18009c6af  pop     r14
0x18009c6b1  pop     r12
0x18009c6b3  pop     rdi
0x18009c6b4  pop     rsi
0x18009c6b5  pop     rbx
0x18009c6b6  pop     rbp
0x18009c6b7  retn
```
