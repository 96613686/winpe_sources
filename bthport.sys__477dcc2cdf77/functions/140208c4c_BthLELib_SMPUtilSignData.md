# BthLELib_SMPUtilSignData

- ea: `0x140208c4c`
- end: `0x140208e1e`
- name: `BthLELib_SMPUtilSignData`
- size: `466`
- prototype: `__int64 __usercall@<rax>(PUCHAR pbSecret@<rcx>, void *Src@<rdx>, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1401f3440`
- `0x1401f3790`

## callees

- `0x140161a00`
- `0x140161a28`
- `0x140165540`
- `0x140165640`
- `0x140208c4c`

## import_xrefs

- `ksecdd!BCryptCloseAlgorithmProvider` at `0x140208deb`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x140208deb`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x140208d0f`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x140208d0f`
- `ksecdd!BCryptCreateHash` at `0x140208d4b`
- `ksecdd!BCryptCreateHash` at `0x140208d4b`
- `ksecdd!BCryptHashData` at `0x140208d6a`
- `ksecdd!BCryptHashData` at `0x140208d6a`
- `ksecdd!BCryptFinishHash` at `0x140208d8a`
- `ksecdd!BCryptFinishHash` at `0x140208d8a`
- `ksecdd!BCryptDestroyHash` at `0x140208dd4`
- `ksecdd!BCryptDestroyHash` at `0x140208dd4`

## pseudocode

```c
__int64 __fastcall BthLELib_SMPUtilSignData(PUCHAR pbSecret, void *Src, unsigned __int16 a3, int a4, _QWORD *a5)
{
  size_t v6; // rbx
  ULONG v9; // r14d
  UCHAR *Pool; // rax
  UCHAR *v11; // rdi
  NTSTATUS v12; // ebx
  ULONG i; // r9d
  __int64 v14; // r8
  ULONG v15; // eax
  __int64 v16; // rax
  UCHAR v17; // dl
  __int64 v18; // r8
  char v19; // dl
  char *v20; // rcx
  BCRYPT_HASH_HANDLE phHash; // [rsp+40h] [rbp-30h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+48h] [rbp-28h] BYREF
  UCHAR pbOutput[16]; // [rsp+50h] [rbp-20h] BYREF

  v6 = a3;
  phAlgorithm = 0;
  phHash = 0;
  *(_OWORD *)pbOutput = 0;
  v9 = a3 + 4;
  Pool = (UCHAR *)BthLELibAllocatePoolEx(pbSecret, v9);
  v11 = Pool;
  if ( Pool )
  {
    memmove(Pool, Src, v6);
    *(_DWORD *)&v11[v6] = a4;
    for ( i = 0; i < v9 >> 1; v11[(unsigned int)v16] = v17 )
    {
      v14 = i;
      v15 = v9 - i++;
      v16 = v15 - 1;
      v17 = v11[v14];
      v11[v14] = v11[v16];
    }
    v12 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"AES-CMAC", L"Microsoft Primitive Provider", 0);
    if ( v12 >= 0 )
    {
      v12 = BCryptCreateHash(phAlgorithm, &phHash, 0, 0, pbSecret, 0x10u, 0);
      if ( v12 >= 0 )
      {
        v12 = BCryptHashData(phHash, v11, v9, 0);
        if ( v12 >= 0 )
        {
          v12 = BCryptFinishHash(phHash, pbOutput, 0x10u, 0);
          if ( v12 >= 0 )
          {
            v18 = 0;
            *a5 = *(_QWORD *)pbOutput;
            do
            {
              v19 = *((_BYTE *)a5 + v18);
              v20 = (char *)a5 - v18;
              *((_BYTE *)a5 + v18) = ((_BYTE *)a5 - v18)[7];
              ++v18;
              v20[7] = v19;
            }
            while ( v18 != 4 );
          }
        }
      }
    }
    SdpFreePool(v11);
  }
  else
  {
    v12 = -1073741670;
  }
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x140208c4c  mov     [rsp-38h+arg_18], rbx
0x140208c51  push    rbp
0x140208c52  push    rsi
0x140208c53  push    rdi
0x140208c54  push    r12
0x140208c56  push    r13
0x140208c58  push    r14
0x140208c5a  push    r15
0x140208c5c  mov     rbp, rsp
0x140208c5f  sub     rsp, 70h
0x140208c63  mov     rax, cs:__security_cookie
0x140208c6a  xor     rax, rsp
0x140208c6d  mov     [rbp+var_10], rax
0x140208c71  mov     rsi, [rbp+arg_20]
0x140208c75  mov     r12, rdx
0x140208c78  movzx   ebx, r8w
0x140208c7c  xorps   xmm0, xmm0
0x140208c7f  mov     r15d, r9d
0x140208c82  mov     [rbp+phAlgorithm], 0
0x140208c8a  mov     r13, rcx
0x140208c8d  mov     [rbp+phHash], 0
0x140208c95  movups  xmmword ptr [rbp+pbOutput], xmm0
0x140208c99  lea     r14d, [rbx+4]
0x140208c9d  mov     edx, r14d
0x140208ca0  call    BthLELibAllocatePoolEx
0x140208ca5  mov     rdi, rax
0x140208ca8  test    rax, rax
0x140208cab  jnz     short loc_140208CB7
0x140208cad  mov     ebx, 0C000009Ah
0x140208cb2  jmp     loc_140208DCB
0x140208cb7  mov     r8, rbx; Size
0x140208cba  mov     rdx, r12; Src
0x140208cbd  mov     rcx, rdi; void *
0x140208cc0  call    memmove
0x140208cc5  mov     r10d, r14d
0x140208cc8  mov     [rbx+rdi], r15d
0x140208ccc  shr     r10d, 1
0x140208ccf  mov     r9d, 0
0x140208cd5  jz      short loc_140208CFA
0x140208cd7  mov     r8d, r9d
0x140208cda  mov     eax, r14d
0x140208cdd  sub     eax, r9d
0x140208ce0  inc     r9d
0x140208ce3  dec     eax
0x140208ce5  mov     ecx, eax
0x140208ce7  mov     dl, [r8+rdi]
0x140208ceb  mov     al, [rax+rdi]
0x140208cee  mov     [r8+rdi], al
0x140208cf2  mov     [rcx+rdi], dl
0x140208cf5  cmp     r9d, r10d
0x140208cf8  jb      short loc_140208CD7
0x140208cfa  xor     r9d, r9d; dwFlags
0x140208cfd  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x140208d04  lea     rdx, aAesCmac; "AES-CMAC"
0x140208d0b  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x140208d0f  call    cs:__imp_BCryptOpenAlgorithmProvider
0x140208d16  nop     dword ptr [rax+rax+00h]
0x140208d1b  mov     ebx, eax
0x140208d1d  test    eax, eax
0x140208d1f  js      loc_140208DC3
0x140208d25  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x140208d29  lea     rdx, [rbp+phHash]; phHash
0x140208d2d  mov     [rsp+70h+dwFlags], 0; dwFlags
0x140208d35  mov     r15d, 10h
0x140208d3b  mov     [rsp+70h+cbSecret], r15d; cbSecret
0x140208d40  xor     r9d, r9d; cbHashObject
0x140208d43  xor     r8d, r8d; pbHashObject
0x140208d46  mov     [rsp+70h+pbSecret], r13; pbSecret
0x140208d4b  call    cs:__imp_BCryptCreateHash
0x140208d52  nop     dword ptr [rax+rax+00h]
0x140208d57  mov     ebx, eax
0x140208d59  test    eax, eax
0x140208d5b  js      short loc_140208DC3
0x140208d5d  mov     rcx, [rbp+phHash]; hHash
0x140208d61  xor     r9d, r9d; dwFlags
0x140208d64  mov     r8d, r14d; cbInput
0x140208d67  mov     rdx, rdi; pbInput
0x140208d6a  call    cs:__imp_BCryptHashData
0x140208d71  nop     dword ptr [rax+rax+00h]
0x140208d76  mov     ebx, eax
0x140208d78  test    eax, eax
0x140208d7a  js      short loc_140208DC3
0x140208d7c  mov     rcx, [rbp+phHash]; hHash
0x140208d80  lea     rdx, [rbp+pbOutput]; pbOutput
0x140208d84  xor     r9d, r9d; dwFlags
0x140208d87  mov     r8d, r15d; cbOutput
0x140208d8a  call    cs:__imp_BCryptFinishHash
0x140208d91  nop     dword ptr [rax+rax+00h]
0x140208d96  mov     ebx, eax
0x140208d98  test    eax, eax
0x140208d9a  js      short loc_140208DC3
0x140208d9c  mov     rax, qword ptr [rbp+pbOutput]
0x140208da0  xor     r8d, r8d
0x140208da3  mov     [rsi], rax
0x140208da6  mov     dl, [rsi+r8]
0x140208daa  mov     rcx, rsi
0x140208dad  sub     rcx, r8
0x140208db0  mov     al, [rcx+7]
0x140208db3  mov     [rsi+r8], al
0x140208db7  inc     r8
0x140208dba  mov     [rcx+7], dl
0x140208dbd  cmp     r8, 4
0x140208dc1  jnz     short loc_140208DA6
0x140208dc3  mov     rcx, rdi
0x140208dc6  call    SdpFreePool
0x140208dcb  mov     rcx, [rbp+phHash]; hHash
0x140208dcf  test    rcx, rcx
0x140208dd2  jz      short loc_140208DE0
0x140208dd4  call    cs:__imp_BCryptDestroyHash
0x140208ddb  nop     dword ptr [rax+rax+00h]
0x140208de0  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x140208de4  test    rcx, rcx
0x140208de7  jz      short loc_140208DF7
0x140208de9  xor     edx, edx; dwFlags
0x140208deb  call    cs:__imp_BCryptCloseAlgorithmProvider
0x140208df2  nop     dword ptr [rax+rax+00h]
0x140208df7  mov     eax, ebx
0x140208df9  mov     rcx, [rbp+var_10]
0x140208dfd  xor     rcx, rsp; StackCookie
0x140208e00  call    __security_check_cookie
0x140208e05  mov     rbx, [rsp+70h+arg_18]
0x140208e0d  add     rsp, 70h
0x140208e11  pop     r15
0x140208e13  pop     r14
0x140208e15  pop     r13
0x140208e17  pop     r12
0x140208e19  pop     rdi
0x140208e1a  pop     rsi
0x140208e1b  pop     rbp
0x140208e1c  retn
```
