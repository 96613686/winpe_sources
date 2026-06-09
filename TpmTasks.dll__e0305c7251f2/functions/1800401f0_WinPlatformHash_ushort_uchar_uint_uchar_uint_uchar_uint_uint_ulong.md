# WinPlatformHash(ushort *,uchar *,uint,uchar *,uint,uchar *,uint,uint *,ulong)

- ea: `0x1800401f0`
- end: `0x1800403d4`
- name: `?WinPlatformHash@@YAJPEAGPEAEI1I1IPEAIK@Z`
- size: `484`
- prototype: `__int64 __usercall@<rax>(LPCWSTR pszAlgId@<rcx>, PUCHAR pbInput@<rdx>, ULONG cbInput@<r8d>, unsigned __int8 *@<r9>, ULONG, PUCHAR, ULONG cbOutput, unsigned int *, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180007894`
- `0x180007900`
- `0x1800085d4`
- `0x1800401f0`

## import_xrefs

- `bcrypt!BCryptCreateHash` at `0x18004033d`
- `bcrypt!BCryptCreateHash` at `0x18004033d`
- `bcrypt!BCryptHashData` at `0x180040356`
- `bcrypt!BCryptHashData` at `0x180040356`
- `bcrypt!BCryptDestroyHash` at `0x180040382`
- `bcrypt!BCryptDestroyHash` at `0x180040382`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800403be`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800403be`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180040254`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180040254`
- `bcrypt!BCryptGetProperty` at `0x18004028b`
- `bcrypt!BCryptGetProperty` at `0x1800402df`
- `bcrypt!BCryptGetProperty` at `0x18004028b`
- `bcrypt!BCryptGetProperty` at `0x1800402df`
- `bcrypt!BCryptFinishHash` at `0x180040371`
- `bcrypt!BCryptFinishHash` at `0x180040371`

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
0x1800401f0  mov     [rsp-30h+pbSecret], r9
0x1800401f5  push    rbp
0x1800401f6  push    rbx
0x1800401f7  push    rdi
0x1800401f8  push    r12
0x1800401fa  push    r13
0x1800401fc  push    r14
0x1800401fe  mov     rbp, rsp
0x180040201  sub     rsp, 68h
0x180040205  xor     eax, eax
0x180040207  mov     r12d, r8d
0x18004020a  mov     r13, rdx
0x18004020d  mov     [rbp+phAlgorithm], rax
0x180040211  mov     [rbp+phHash], rax
0x180040215  mov     dword ptr [rbp+var_28], eax
0x180040218  mov     dword ptr [rbp+pbOutput], eax
0x18004021b  mov     [rbp+var_24], eax
0x18004021e  cmp     [rbp+cbOutput], eax
0x180040221  jz      short loc_180040229
0x180040223  cmp     [rbp+arg_28], rax
0x180040227  jz      short loc_180040232
0x180040229  mov     r14, [rbp+arg_38]
0x18004022d  test    r14, r14
0x180040230  jnz     short loc_18004023C
0x180040232  mov     eax, 80070057h
0x180040237  jmp     loc_1800403C6
0x18004023c  mov     r9d, [rbp+dwFlags]; dwFlags
0x180040240  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x180040247  mov     rdx, rcx; pszAlgId
0x18004024a  mov     [r14], eax
0x18004024d  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x180040251  mov     rdi, rax
0x180040254  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18004025a  mov     ebx, eax
0x18004025c  test    eax, eax
0x18004025e  js      loc_180040379
0x180040264  mov     ecx, 4
0x180040269  mov     [rsp+68h+cbSecret], edi; dwFlags
0x18004026d  mov     [rbp+var_24], ecx
0x180040270  lea     rax, [rbp+var_24]
0x180040274  mov     r9d, ecx; cbOutput
0x180040277  mov     [rsp+68h+pcbResult], rax; pcbResult
0x18004027c  mov     rcx, [rbp+phAlgorithm]; hObject
0x180040280  lea     r8, [rbp+pbOutput]; pbOutput
0x180040284  lea     rdx, aHashdigestleng; "HashDigestLength"
0x18004028b  call    cs:__imp_BCryptGetProperty
0x180040291  mov     ebx, eax
0x180040293  test    eax, eax
0x180040295  js      loc_180040379
0x18004029b  mov     eax, dword ptr [rbp+pbOutput]
0x18004029e  mov     [r14], eax
0x1800402a1  cmp     [rbp+cbOutput], edi
0x1800402a4  jz      loc_180040379
0x1800402aa  cmp     [rbp+cbOutput], eax
0x1800402ad  jnb     short loc_1800402B9
0x1800402af  mov     ebx, 0C0000023h
0x1800402b4  jmp     loc_180040379
0x1800402b9  mov     rcx, [rbp+phAlgorithm]; hObject
0x1800402bd  lea     rax, [rbp+var_24]
0x1800402c1  mov     r9d, 4; cbOutput
0x1800402c7  mov     [rsp+68h+cbSecret], edi; dwFlags
0x1800402cb  lea     r8, [rbp+var_28]; pbOutput
0x1800402cf  mov     [rbp+var_24], r9d
0x1800402d3  lea     rdx, aObjectlength; "ObjectLength"
0x1800402da  mov     [rsp+68h+pcbResult], rax; pcbResult
0x1800402df  call    cs:__imp_BCryptGetProperty
0x1800402e5  mov     ebx, eax
0x1800402e7  test    eax, eax
0x1800402e9  js      loc_180040379
0x1800402ef  mov     ecx, dword ptr [rbp+var_28]; Size
0x1800402f2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800402f7  mov     r8d, dword ptr [rbp+var_28]; Size
0x1800402fb  xor     edx, edx; Val
0x1800402fd  mov     rcx, rax; void *
0x180040300  mov     rdi, rax
0x180040303  call    memset_0
0x180040308  mov     r8d, dword ptr [rbp+var_28]; Size
0x18004030c  xor     edx, edx; Val
0x18004030e  mov     rcx, rdi; void *
0x180040311  call    memset_0
0x180040316  mov     eax, [rbp+arg_20]
0x180040319  lea     rdx, [rbp+phHash]; phHash
0x18004031d  mov     r9d, dword ptr [rbp+var_28]; cbHashObject
0x180040321  mov     r8, rdi; pbHashObject
0x180040324  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x180040328  mov     [rsp+68h+var_38], 0; dwFlags
0x180040330  mov     [rsp+68h+cbSecret], eax; cbSecret
0x180040334  mov     rax, [rbp+pbSecret]
0x180040338  mov     [rsp+68h+pcbResult], rax; pbSecret
0x18004033d  call    cs:__imp_BCryptCreateHash
0x180040343  mov     ebx, eax
0x180040345  test    eax, eax
0x180040347  js      short loc_180040379
0x180040349  mov     rcx, [rbp+phHash]; hHash
0x18004034d  xor     r9d, r9d; dwFlags
0x180040350  mov     r8d, r12d; cbInput
0x180040353  mov     rdx, r13; pbInput
0x180040356  call    cs:__imp_BCryptHashData
0x18004035c  mov     ebx, eax
0x18004035e  test    eax, eax
0x180040360  js      short loc_180040379
0x180040362  mov     r8d, [rbp+cbOutput]; cbOutput
0x180040366  xor     r9d, r9d; dwFlags
0x180040369  mov     rdx, [rbp+arg_28]; pbOutput
0x18004036d  mov     rcx, [rbp+phHash]; hHash
0x180040371  call    cs:__imp_BCryptFinishHash
0x180040377  mov     ebx, eax
0x180040379  mov     rcx, [rbp+phHash]; hHash
0x18004037d  test    rcx, rcx
0x180040380  jz      short loc_180040388
0x180040382  call    cs:__imp_BCryptDestroyHash
0x180040388  test    rdi, rdi
0x18004038b  jz      short loc_1800403AC
0x18004038d  mov     eax, dword ptr [rbp+var_28]
0x180040390  mov     rcx, rdi
0x180040393  test    rax, rax
0x180040396  jz      short loc_1800403A4
0x180040398  mov     byte ptr [rcx], 0
0x18004039b  inc     rcx
0x18004039e  sub     rax, 1
0x1800403a2  jnz     short loc_180040398
0x1800403a4  mov     rcx, rdi; Block
0x1800403a7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800403ac  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x1800403b0  mov     dword ptr [rbp+var_28], 0
0x1800403b7  test    rcx, rcx
0x1800403ba  jz      short loc_1800403C4
0x1800403bc  xor     edx, edx; dwFlags
0x1800403be  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1800403c4  mov     eax, ebx
0x1800403c6  add     rsp, 68h
0x1800403ca  pop     r14
0x1800403cc  pop     r13
0x1800403ce  pop     r12
0x1800403d0  pop     rdi
0x1800403d1  pop     rbx
0x1800403d2  pop     rbp
0x1800403d3  retn
```
