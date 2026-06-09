# WinPlatformHash(ushort *,uchar *,uint,uchar *,uint,uchar *,uint,uint *,ulong)

- ea: `0x18002f010`
- end: `0x18002f1f4`
- name: `?WinPlatformHash@@YAJPEAGPEAEI1I1IPEAIK@Z`
- size: `484`
- prototype: `__int64 __usercall@<rax>(LPCWSTR pszAlgId@<rcx>, PUCHAR pbInput@<rdx>, ULONG cbInput@<r8d>, unsigned __int8 *@<r9>, ULONG, PUCHAR, ULONG cbOutput, unsigned int *, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18002f010`
- `0x18005d2ec`
- `0x18005db30`
- `0x18005dd44`

## import_xrefs

- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18002f1de`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18002f1de`
- `bcrypt!BCryptDestroyHash` at `0x18002f1a2`
- `bcrypt!BCryptDestroyHash` at `0x18002f1a2`
- `bcrypt!BCryptFinishHash` at `0x18002f191`
- `bcrypt!BCryptFinishHash` at `0x18002f191`
- `bcrypt!BCryptGetProperty` at `0x18002f0ab`
- `bcrypt!BCryptGetProperty` at `0x18002f0ff`
- `bcrypt!BCryptGetProperty` at `0x18002f0ab`
- `bcrypt!BCryptGetProperty` at `0x18002f0ff`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18002f074`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18002f074`
- `bcrypt!BCryptHashData` at `0x18002f176`
- `bcrypt!BCryptHashData` at `0x18002f176`
- `bcrypt!BCryptCreateHash` at `0x18002f15d`
- `bcrypt!BCryptCreateHash` at `0x18002f15d`

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
0x18002f010  mov     [rsp-30h+pbSecret], r9
0x18002f015  push    rbp
0x18002f016  push    rbx
0x18002f017  push    rdi
0x18002f018  push    r12
0x18002f01a  push    r13
0x18002f01c  push    r14
0x18002f01e  mov     rbp, rsp
0x18002f021  sub     rsp, 68h
0x18002f025  xor     eax, eax
0x18002f027  mov     r12d, r8d
0x18002f02a  mov     r13, rdx
0x18002f02d  mov     [rbp+phAlgorithm], rax
0x18002f031  mov     [rbp+phHash], rax
0x18002f035  mov     dword ptr [rbp+var_28], eax
0x18002f038  mov     dword ptr [rbp+pbOutput], eax
0x18002f03b  mov     [rbp+var_24], eax
0x18002f03e  cmp     [rbp+cbOutput], eax
0x18002f041  jz      short loc_18002F049
0x18002f043  cmp     [rbp+arg_28], rax
0x18002f047  jz      short loc_18002F052
0x18002f049  mov     r14, [rbp+arg_38]
0x18002f04d  test    r14, r14
0x18002f050  jnz     short loc_18002F05C
0x18002f052  mov     eax, 80070057h
0x18002f057  jmp     loc_18002F1E6
0x18002f05c  mov     r9d, [rbp+dwFlags]; dwFlags
0x18002f060  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x18002f067  mov     rdx, rcx; pszAlgId
0x18002f06a  mov     [r14], eax
0x18002f06d  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x18002f071  mov     rdi, rax
0x18002f074  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18002f07a  mov     ebx, eax
0x18002f07c  test    eax, eax
0x18002f07e  js      loc_18002F199
0x18002f084  mov     ecx, 4
0x18002f089  mov     [rsp+68h+cbSecret], edi; dwFlags
0x18002f08d  mov     [rbp+var_24], ecx
0x18002f090  lea     rax, [rbp+var_24]
0x18002f094  mov     r9d, ecx; cbOutput
0x18002f097  mov     [rsp+68h+pcbResult], rax; pcbResult
0x18002f09c  mov     rcx, [rbp+phAlgorithm]; hObject
0x18002f0a0  lea     r8, [rbp+pbOutput]; pbOutput
0x18002f0a4  lea     rdx, pszProperty; "HashDigestLength"
0x18002f0ab  call    cs:__imp_BCryptGetProperty
0x18002f0b1  mov     ebx, eax
0x18002f0b3  test    eax, eax
0x18002f0b5  js      loc_18002F199
0x18002f0bb  mov     eax, dword ptr [rbp+pbOutput]
0x18002f0be  mov     [r14], eax
0x18002f0c1  cmp     [rbp+cbOutput], edi
0x18002f0c4  jz      loc_18002F199
0x18002f0ca  cmp     [rbp+cbOutput], eax
0x18002f0cd  jnb     short loc_18002F0D9
0x18002f0cf  mov     ebx, 0C0000023h
0x18002f0d4  jmp     loc_18002F199
0x18002f0d9  mov     rcx, [rbp+phAlgorithm]; hObject
0x18002f0dd  lea     rax, [rbp+var_24]
0x18002f0e1  mov     r9d, 4; cbOutput
0x18002f0e7  mov     [rsp+68h+cbSecret], edi; dwFlags
0x18002f0eb  lea     r8, [rbp+var_28]; pbOutput
0x18002f0ef  mov     [rbp+var_24], r9d
0x18002f0f3  lea     rdx, aObjectlength; "ObjectLength"
0x18002f0fa  mov     [rsp+68h+pcbResult], rax; pcbResult
0x18002f0ff  call    cs:__imp_BCryptGetProperty
0x18002f105  mov     ebx, eax
0x18002f107  test    eax, eax
0x18002f109  js      loc_18002F199
0x18002f10f  mov     ecx, dword ptr [rbp+var_28]; Size
0x18002f112  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002f117  mov     r8d, dword ptr [rbp+var_28]; Size
0x18002f11b  xor     edx, edx; Val
0x18002f11d  mov     rcx, rax; void *
0x18002f120  mov     rdi, rax
0x18002f123  call    memset_0
0x18002f128  mov     r8d, dword ptr [rbp+var_28]; Size
0x18002f12c  xor     edx, edx; Val
0x18002f12e  mov     rcx, rdi; void *
0x18002f131  call    memset_0
0x18002f136  mov     eax, [rbp+arg_20]
0x18002f139  lea     rdx, [rbp+phHash]; phHash
0x18002f13d  mov     r9d, dword ptr [rbp+var_28]; cbHashObject
0x18002f141  mov     r8, rdi; pbHashObject
0x18002f144  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x18002f148  mov     [rsp+68h+var_38], 0; dwFlags
0x18002f150  mov     [rsp+68h+cbSecret], eax; cbSecret
0x18002f154  mov     rax, [rbp+pbSecret]
0x18002f158  mov     [rsp+68h+pcbResult], rax; pbSecret
0x18002f15d  call    cs:__imp_BCryptCreateHash
0x18002f163  mov     ebx, eax
0x18002f165  test    eax, eax
0x18002f167  js      short loc_18002F199
0x18002f169  mov     rcx, [rbp+phHash]; hHash
0x18002f16d  xor     r9d, r9d; dwFlags
0x18002f170  mov     r8d, r12d; cbInput
0x18002f173  mov     rdx, r13; pbInput
0x18002f176  call    cs:__imp_BCryptHashData
0x18002f17c  mov     ebx, eax
0x18002f17e  test    eax, eax
0x18002f180  js      short loc_18002F199
0x18002f182  mov     r8d, [rbp+cbOutput]; cbOutput
0x18002f186  xor     r9d, r9d; dwFlags
0x18002f189  mov     rdx, [rbp+arg_28]; pbOutput
0x18002f18d  mov     rcx, [rbp+phHash]; hHash
0x18002f191  call    cs:__imp_BCryptFinishHash
0x18002f197  mov     ebx, eax
0x18002f199  mov     rcx, [rbp+phHash]; hHash
0x18002f19d  test    rcx, rcx
0x18002f1a0  jz      short loc_18002F1A8
0x18002f1a2  call    cs:__imp_BCryptDestroyHash
0x18002f1a8  test    rdi, rdi
0x18002f1ab  jz      short loc_18002F1CC
0x18002f1ad  mov     eax, dword ptr [rbp+var_28]
0x18002f1b0  mov     rcx, rdi
0x18002f1b3  test    rax, rax
0x18002f1b6  jz      short loc_18002F1C4
0x18002f1b8  mov     byte ptr [rcx], 0
0x18002f1bb  inc     rcx
0x18002f1be  sub     rax, 1
0x18002f1c2  jnz     short loc_18002F1B8
0x18002f1c4  mov     rcx, rdi; Block
0x18002f1c7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002f1cc  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x18002f1d0  mov     dword ptr [rbp+var_28], 0
0x18002f1d7  test    rcx, rcx
0x18002f1da  jz      short loc_18002F1E4
0x18002f1dc  xor     edx, edx; dwFlags
0x18002f1de  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18002f1e4  mov     eax, ebx
0x18002f1e6  add     rsp, 68h
0x18002f1ea  pop     r14
0x18002f1ec  pop     r13
0x18002f1ee  pop     r12
0x18002f1f0  pop     rdi
0x18002f1f1  pop     rbx
0x18002f1f2  pop     rbp
0x18002f1f3  retn
```
