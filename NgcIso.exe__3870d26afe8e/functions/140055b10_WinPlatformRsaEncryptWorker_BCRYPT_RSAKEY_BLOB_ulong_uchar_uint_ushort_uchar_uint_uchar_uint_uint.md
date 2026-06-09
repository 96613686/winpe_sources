# WinPlatformRsaEncryptWorker(_BCRYPT_RSAKEY_BLOB *,ulong,uchar *,uint,ushort,uchar *,uint,uchar *,uint,uint *)

- ea: `0x140055b10`
- end: `0x140055c97`
- name: `?WinPlatformRsaEncryptWorker@@YAJPEAU_BCRYPT_RSAKEY_BLOB@@KPEAEIG1I1IPEAI@Z`
- size: `391`
- prototype: `__int64 __usercall@<rax>(PUCHAR pbInput@<rcx>, unsigned int@<edx>, unsigned __int8 *@<r8>, unsigned int@<r9d>, unsigned __int16, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140055b10`

## import_xrefs

- `bcrypt!BCryptDestroyKey` at `0x140055c62`
- `bcrypt!BCryptDestroyKey` at `0x140055c62`
- `bcrypt!BCryptEncrypt` at `0x140055c4a`
- `bcrypt!BCryptEncrypt` at `0x140055c4a`
- `bcrypt!BCryptImportKeyPair` at `0x140055b9b`
- `bcrypt!BCryptImportKeyPair` at `0x140055b9b`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x140055b55`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x140055b55`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x140055c73`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x140055c73`

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
0x140055b10  push    rbp
0x140055b12  push    rbx
0x140055b13  push    rsi
0x140055b14  push    rdi
0x140055b15  push    r12
0x140055b17  push    r14
0x140055b19  push    r15
0x140055b1b  mov     rbp, rsp
0x140055b1e  sub     rsp, 80h
0x140055b25  mov     r15d, r9d
0x140055b28  mov     [rbp+phAlgorithm], 0
0x140055b30  mov     r12, r8
0x140055b33  mov     [rbp+phKey], 0
0x140055b3b  mov     edi, edx
0x140055b3d  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x140055b44  mov     r14, rcx
0x140055b47  lea     rdx, aRsa; "RSA"
0x140055b4e  xor     r9d, r9d; dwFlags
0x140055b51  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x140055b55  call    cs:__imp_BCryptOpenAlgorithmProvider
0x140055b5b  mov     rsi, [rbp+arg_48]
0x140055b62  mov     ebx, eax
0x140055b64  test    eax, eax
0x140055b66  js      loc_140055C59
0x140055b6c  mov     ecx, [r14+0Ch]
0x140055b70  lea     r9, [rbp+phKey]; phKey
0x140055b74  mov     edx, [r14+8]
0x140055b78  lea     r8, aRsapublicblob; "RSAPUBLICBLOB"
0x140055b7f  add     ecx, 18h
0x140055b82  mov     [rsp+80h+dwFlags], 0; dwFlags
0x140055b8a  add     edx, ecx
0x140055b8c  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x140055b90  mov     [rsp+80h+cbInput], edx; cbInput
0x140055b94  xor     edx, edx; hImportKey
0x140055b96  mov     [rsp+80h+pbInput], r14; pbInput
0x140055b9b  call    cs:__imp_BCryptImportKeyPair
0x140055ba1  mov     ebx, eax
0x140055ba3  test    eax, eax
0x140055ba5  js      loc_140055C59
0x140055bab  cmp     edi, 2
0x140055bae  jnz     short loc_140055BB9
0x140055bb0  mov     [rsp+80h+var_38], edi
0x140055bb4  xor     r9d, r9d
0x140055bb7  jmp     short loc_140055C17
0x140055bb9  mov     r8d, 4
0x140055bbf  cmp     edi, r8d
0x140055bc2  jnz     loc_140055C54
0x140055bc8  movzx   ecx, [rbp+arg_20]
0x140055bcc  cmp     cx, 0Bh
0x140055bd0  jz      short loc_140055BDF
0x140055bd2  cmp     cx, r8w
0x140055bd6  jz      short loc_140055BDF
0x140055bd8  mov     ebx, 0C000000Dh
0x140055bdd  jmp     short loc_140055C59
0x140055bdf  cmp     cx, 0Bh
0x140055be3  mov     [rbp+var_C], 0
0x140055bea  lea     rax, aSha256; "SHA256"
0x140055bf1  mov     [rsp+80h+var_38], r8d; dwFlags
0x140055bf6  lea     rdx, aSha1; "SHA1"
0x140055bfd  cmovnz  rax, rdx
0x140055c01  lea     r9, [rbp+pPaddingInfo]; pPaddingInfo
0x140055c05  mov     [rbp+pPaddingInfo], rax
0x140055c09  mov     rax, [rbp+arg_28]
0x140055c0d  mov     [rbp+var_18], rax
0x140055c11  mov     eax, [rbp+arg_30]
0x140055c14  mov     [rbp+var_10], eax
0x140055c17  mov     eax, [rbp+arg_40]
0x140055c1d  mov     r8d, r15d; cbInput
0x140055c20  mov     rcx, [rbp+phKey]; hKey
0x140055c24  mov     rdx, r12; pbInput
0x140055c27  mov     [rsp+80h+pcbResult], rsi; pcbResult
0x140055c2c  mov     [rsp+80h+cbOutput], eax; cbOutput
0x140055c30  mov     rax, [rbp+pbOutput]
0x140055c34  mov     qword ptr [rsp+80h+dwFlags], rax; pbOutput
0x140055c39  mov     [rsp+80h+cbInput], 0; cbIV
0x140055c41  mov     [rsp+80h+pbInput], 0; pbIV
0x140055c4a  call    cs:__imp_BCryptEncrypt
0x140055c50  mov     ebx, eax
0x140055c52  jmp     short loc_140055C59
0x140055c54  mov     ebx, 0C00000BBh
0x140055c59  mov     rcx, [rbp+phKey]; hKey
0x140055c5d  test    rcx, rcx
0x140055c60  jz      short loc_140055C68
0x140055c62  call    cs:__imp_BCryptDestroyKey
0x140055c68  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x140055c6c  test    rcx, rcx
0x140055c6f  jz      short loc_140055C79
0x140055c71  xor     edx, edx; dwFlags
0x140055c73  call    cs:__imp_BCryptCloseAlgorithmProvider
0x140055c79  test    ebx, ebx
0x140055c7b  jz      short loc_140055C83
0x140055c7d  mov     dword ptr [rsi], 0
0x140055c83  mov     eax, ebx
0x140055c85  add     rsp, 80h
0x140055c8c  pop     r15
0x140055c8e  pop     r14
0x140055c90  pop     r12
0x140055c92  pop     rdi
0x140055c93  pop     rsi
0x140055c94  pop     rbx
0x140055c95  pop     rbp
0x140055c96  retn
```
