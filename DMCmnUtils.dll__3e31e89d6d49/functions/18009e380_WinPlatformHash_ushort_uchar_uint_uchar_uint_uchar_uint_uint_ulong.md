# WinPlatformHash(ushort *,uchar *,uint,uchar *,uint,uchar *,uint,uint *,ulong)

- ea: `0x18009e380`
- end: `0x18009e595`
- name: `?WinPlatformHash@@YAJPEAGPEAEI1I1IPEAIK@Z`
- size: `533`
- prototype: `__int64 __usercall@<rax>(LPCWSTR pszAlgId@<rcx>, PUCHAR pbInput@<rdx>, ULONG cbInput@<r8d>, unsigned __int8 *@<r9>, ULONG, PUCHAR, ULONG cbOutput, unsigned int *, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180007b00`
- `0x180007c7c`
- `0x180051d48`
- `0x18009e380`

## import_xrefs

- `bcrypt!BCryptHashData` at `0x18009e4fe`
- `bcrypt!BCryptHashData` at `0x18009e4fe`
- `bcrypt!BCryptFinishHash` at `0x18009e51f`
- `bcrypt!BCryptFinishHash` at `0x18009e51f`
- `bcrypt!BCryptDestroyHash` at `0x18009e536`
- `bcrypt!BCryptDestroyHash` at `0x18009e536`
- `bcrypt!BCryptCreateHash` at `0x18009e4df`
- `bcrypt!BCryptCreateHash` at `0x18009e4df`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18009e578`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18009e578`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18009e3e4`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18009e3e4`
- `bcrypt!BCryptGetProperty` at `0x18009e421`
- `bcrypt!BCryptGetProperty` at `0x18009e47b`
- `bcrypt!BCryptGetProperty` at `0x18009e421`
- `bcrypt!BCryptGetProperty` at `0x18009e47b`

## pseudocode

```c
__int64 __fastcall WinPlatformHash(
        LPCWSTR pszAlgId,
        PUCHAR pbInput,
        ULONG cbInput,
        unsigned __int8 *a4,
        ULONG cbSecret,
        PUCHAR a6,
        ULONG cbOutput,
        unsigned int *a8,
        ULONG dwFlags)
{
  void *v12; // rdi
  NTSTATUS Property; // ebx
  ULONG v14; // eax
  __int64 v15; // rax
  _BYTE *v16; // rcx
  UCHAR v17[4]; // [rsp+40h] [rbp-28h] BYREF
  ULONG pcbResult; // [rsp+44h] [rbp-24h] BYREF
  UCHAR pbOutput[8]; // [rsp+48h] [rbp-20h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+50h] [rbp-18h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+58h] [rbp-10h] BYREF

  phAlgorithm = 0;
  phHash = 0;
  *(_DWORD *)v17 = 0;
  *(_DWORD *)pbOutput = 0;
  pcbResult = 0;
  if ( cbOutput && !a6 || !a8 )
    return 2147942487LL;
  *a8 = 0;
  v12 = 0;
  Property = BCryptOpenAlgorithmProvider(&phAlgorithm, pszAlgId, L"Microsoft Primitive Provider", dwFlags);
  if ( Property >= 0 )
  {
    pcbResult = 4;
    Property = BCryptGetProperty(phAlgorithm, L"HashDigestLength", pbOutput, 4u, &pcbResult, 0);
    if ( Property >= 0 )
    {
      v14 = *(_DWORD *)pbOutput;
      *a8 = *(_DWORD *)pbOutput;
      if ( cbOutput )
      {
        if ( cbOutput >= v14 )
        {
          pcbResult = 4;
          Property = BCryptGetProperty(phAlgorithm, L"ObjectLength", v17, 4u, &pcbResult, 0);
          if ( Property >= 0 )
          {
            v12 = operator new(*(unsigned int *)v17);
            memset_0(v12, 0, *(unsigned int *)v17);
            memset_0(v12, 0, *(unsigned int *)v17);
            Property = BCryptCreateHash(phAlgorithm, &phHash, (PUCHAR)v12, *(ULONG *)v17, a4, cbSecret, 0);
            if ( Property >= 0 )
            {
              Property = BCryptHashData(phHash, pbInput, cbInput, 0);
              if ( Property >= 0 )
                Property = BCryptFinishHash(phHash, a6, cbOutput, 0);
            }
          }
        }
        else
        {
          Property = -1073741789;
        }
      }
    }
  }
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( v12 )
  {
    v15 = *(unsigned int *)v17;
    v16 = v12;
    if ( *(_DWORD *)v17 )
    {
      do
      {
        *v16++ = 0;
        --v15;
      }
      while ( v15 );
    }
    operator delete(v12);
  }
  *(_DWORD *)v17 = 0;
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x18009e380  mov     [rsp-30h+pbSecret], r9
0x18009e385  push    rbp
0x18009e386  push    rbx
0x18009e387  push    rdi
0x18009e388  push    r12
0x18009e38a  push    r13
0x18009e38c  push    r14
0x18009e38e  mov     rbp, rsp
0x18009e391  sub     rsp, 68h
0x18009e395  xor     eax, eax
0x18009e397  mov     r12d, r8d
0x18009e39a  mov     r13, rdx
0x18009e39d  mov     [rbp+phAlgorithm], rax
0x18009e3a1  mov     [rbp+phHash], rax
0x18009e3a5  mov     dword ptr [rbp+var_28], eax
0x18009e3a8  mov     dword ptr [rbp+pbOutput], eax
0x18009e3ab  mov     [rbp+var_24], eax
0x18009e3ae  cmp     [rbp+cbOutput], eax
0x18009e3b1  jz      short loc_18009E3B9
0x18009e3b3  cmp     [rbp+arg_28], rax
0x18009e3b7  jz      short loc_18009E3C2
0x18009e3b9  mov     r14, [rbp+arg_38]
0x18009e3bd  test    r14, r14
0x18009e3c0  jnz     short loc_18009E3CC
0x18009e3c2  mov     eax, 80070057h
0x18009e3c7  jmp     loc_18009E586
0x18009e3cc  mov     r9d, [rbp+dwFlags]; dwFlags
0x18009e3d0  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x18009e3d7  mov     rdx, rcx; pszAlgId
0x18009e3da  mov     [r14], eax
0x18009e3dd  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x18009e3e1  mov     rdi, rax
0x18009e3e4  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18009e3eb  nop     dword ptr [rax+rax+00h]
0x18009e3f0  mov     ebx, eax
0x18009e3f2  test    eax, eax
0x18009e3f4  js      loc_18009E52D
0x18009e3fa  mov     ecx, 4
0x18009e3ff  mov     [rsp+68h+cbSecret], edi; dwFlags
0x18009e403  mov     [rbp+var_24], ecx
0x18009e406  lea     rax, [rbp+var_24]
0x18009e40a  mov     r9d, ecx; cbOutput
0x18009e40d  mov     [rsp+68h+pcbResult], rax; pcbResult
0x18009e412  mov     rcx, [rbp+phAlgorithm]; hObject
0x18009e416  lea     r8, [rbp+pbOutput]; pbOutput
0x18009e41a  lea     rdx, pszProperty; "HashDigestLength"
0x18009e421  call    cs:__imp_BCryptGetProperty
0x18009e428  nop     dword ptr [rax+rax+00h]
0x18009e42d  mov     ebx, eax
0x18009e42f  test    eax, eax
0x18009e431  js      loc_18009E52D
0x18009e437  mov     eax, dword ptr [rbp+pbOutput]
0x18009e43a  mov     [r14], eax
0x18009e43d  cmp     [rbp+cbOutput], edi
0x18009e440  jz      loc_18009E52D
0x18009e446  cmp     [rbp+cbOutput], eax
0x18009e449  jnb     short loc_18009E455
0x18009e44b  mov     ebx, 0C0000023h
0x18009e450  jmp     loc_18009E52D
0x18009e455  mov     rcx, [rbp+phAlgorithm]; hObject
0x18009e459  lea     rax, [rbp+var_24]
0x18009e45d  mov     r9d, 4; cbOutput
0x18009e463  mov     [rsp+68h+cbSecret], edi; dwFlags
0x18009e467  lea     r8, [rbp+var_28]; pbOutput
0x18009e46b  mov     [rbp+var_24], r9d
0x18009e46f  lea     rdx, aObjectlength; "ObjectLength"
0x18009e476  mov     [rsp+68h+pcbResult], rax; pcbResult
0x18009e47b  call    cs:__imp_BCryptGetProperty
0x18009e482  nop     dword ptr [rax+rax+00h]
0x18009e487  mov     ebx, eax
0x18009e489  test    eax, eax
0x18009e48b  js      loc_18009E52D
0x18009e491  mov     ecx, dword ptr [rbp+var_28]; Size
0x18009e494  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18009e499  mov     r8d, dword ptr [rbp+var_28]; Size
0x18009e49d  xor     edx, edx; Val
0x18009e49f  mov     rcx, rax; void *
0x18009e4a2  mov     rdi, rax
0x18009e4a5  call    memset_0
0x18009e4aa  mov     r8d, dword ptr [rbp+var_28]; Size
0x18009e4ae  xor     edx, edx; Val
0x18009e4b0  mov     rcx, rdi; void *
0x18009e4b3  call    memset_0
0x18009e4b8  mov     eax, [rbp+arg_20]
0x18009e4bb  lea     rdx, [rbp+phHash]; phHash
0x18009e4bf  mov     r9d, dword ptr [rbp+var_28]; cbHashObject
0x18009e4c3  mov     r8, rdi; pbHashObject
0x18009e4c6  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x18009e4ca  mov     [rsp+68h+var_38], 0; dwFlags
0x18009e4d2  mov     [rsp+68h+cbSecret], eax; cbSecret
0x18009e4d6  mov     rax, [rbp+pbSecret]
0x18009e4da  mov     [rsp+68h+pcbResult], rax; pbSecret
0x18009e4df  call    cs:__imp_BCryptCreateHash
0x18009e4e6  nop     dword ptr [rax+rax+00h]
0x18009e4eb  mov     ebx, eax
0x18009e4ed  test    eax, eax
0x18009e4ef  js      short loc_18009E52D
0x18009e4f1  mov     rcx, [rbp+phHash]; hHash
0x18009e4f5  xor     r9d, r9d; dwFlags
0x18009e4f8  mov     r8d, r12d; cbInput
0x18009e4fb  mov     rdx, r13; pbInput
0x18009e4fe  call    cs:__imp_BCryptHashData
0x18009e505  nop     dword ptr [rax+rax+00h]
0x18009e50a  mov     ebx, eax
0x18009e50c  test    eax, eax
0x18009e50e  js      short loc_18009E52D
0x18009e510  mov     r8d, [rbp+cbOutput]; cbOutput
0x18009e514  xor     r9d, r9d; dwFlags
0x18009e517  mov     rdx, [rbp+arg_28]; pbOutput
0x18009e51b  mov     rcx, [rbp+phHash]; hHash
0x18009e51f  call    cs:__imp_BCryptFinishHash
0x18009e526  nop     dword ptr [rax+rax+00h]
0x18009e52b  mov     ebx, eax
0x18009e52d  mov     rcx, [rbp+phHash]; hHash
0x18009e531  test    rcx, rcx
0x18009e534  jz      short loc_18009E542
0x18009e536  call    cs:__imp_BCryptDestroyHash
0x18009e53d  nop     dword ptr [rax+rax+00h]
0x18009e542  test    rdi, rdi
0x18009e545  jz      short loc_18009E566
0x18009e547  mov     eax, dword ptr [rbp+var_28]
0x18009e54a  mov     rcx, rdi
0x18009e54d  test    rax, rax
0x18009e550  jz      short loc_18009E55E
0x18009e552  mov     byte ptr [rcx], 0
0x18009e555  inc     rcx
0x18009e558  sub     rax, 1
0x18009e55c  jnz     short loc_18009E552
0x18009e55e  mov     rcx, rdi; Block
0x18009e561  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18009e566  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x18009e56a  mov     dword ptr [rbp+var_28], 0
0x18009e571  test    rcx, rcx
0x18009e574  jz      short loc_18009E584
0x18009e576  xor     edx, edx; dwFlags
0x18009e578  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18009e57f  nop     dword ptr [rax+rax+00h]
0x18009e584  mov     eax, ebx
0x18009e586  add     rsp, 68h
0x18009e58a  pop     r14
0x18009e58c  pop     r13
0x18009e58e  pop     r12
0x18009e590  pop     rdi
0x18009e591  pop     rbx
0x18009e592  pop     rbp
0x18009e593  retn
```
