# WinPlatformHash(ushort *,uchar *,uint,uchar *,uint,uchar *,uint,uint *,ulong)

- ea: `0x180162530`
- end: `0x180162714`
- name: `?WinPlatformHash@@YAJPEAGPEAEI1I1IPEAIK@Z`
- size: `484`
- prototype: `__int64 __usercall@<rax>(LPCWSTR pszAlgId@<rcx>, PUCHAR pbInput@<rdx>, ULONG cbInput@<r8d>, unsigned __int8 *@<r9>, ULONG, PUCHAR, ULONG cbOutput, unsigned int *, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000bd0c`
- `0x18000bd74`
- `0x18000c414`
- `0x180162530`

## import_xrefs

- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1801626fe`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1801626fe`
- `bcrypt!BCryptDestroyHash` at `0x1801626c2`
- `bcrypt!BCryptDestroyHash` at `0x1801626c2`
- `bcrypt!BCryptFinishHash` at `0x1801626b1`
- `bcrypt!BCryptFinishHash` at `0x1801626b1`
- `bcrypt!BCryptHashData` at `0x180162696`
- `bcrypt!BCryptHashData` at `0x180162696`
- `bcrypt!BCryptCreateHash` at `0x18016267d`
- `bcrypt!BCryptCreateHash` at `0x18016267d`
- `bcrypt!BCryptGetProperty` at `0x1801625cb`
- `bcrypt!BCryptGetProperty` at `0x18016261f`
- `bcrypt!BCryptGetProperty` at `0x1801625cb`
- `bcrypt!BCryptGetProperty` at `0x18016261f`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180162594`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180162594`

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
0x180162530  mov     [rsp-30h+pbSecret], r9
0x180162535  push    rbp
0x180162536  push    rbx
0x180162537  push    rdi
0x180162538  push    r12
0x18016253a  push    r13
0x18016253c  push    r14
0x18016253e  mov     rbp, rsp
0x180162541  sub     rsp, 68h
0x180162545  xor     eax, eax
0x180162547  mov     r12d, r8d
0x18016254a  mov     r13, rdx
0x18016254d  mov     [rbp+phAlgorithm], rax
0x180162551  mov     [rbp+phHash], rax
0x180162555  mov     dword ptr [rbp+var_28], eax
0x180162558  mov     dword ptr [rbp+pbOutput], eax
0x18016255b  mov     [rbp+var_24], eax
0x18016255e  cmp     [rbp+cbOutput], eax
0x180162561  jz      short loc_180162569
0x180162563  cmp     [rbp+arg_28], rax
0x180162567  jz      short loc_180162572
0x180162569  mov     r14, [rbp+arg_38]
0x18016256d  test    r14, r14
0x180162570  jnz     short loc_18016257C
0x180162572  mov     eax, 80070057h
0x180162577  jmp     loc_180162706
0x18016257c  mov     r9d, [rbp+dwFlags]; dwFlags
0x180162580  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x180162587  mov     rdx, rcx; pszAlgId
0x18016258a  mov     [r14], eax
0x18016258d  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x180162591  mov     rdi, rax
0x180162594  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18016259a  mov     ebx, eax
0x18016259c  test    eax, eax
0x18016259e  js      loc_1801626B9
0x1801625a4  mov     ecx, 4
0x1801625a9  mov     [rsp+68h+cbSecret], edi; dwFlags
0x1801625ad  mov     [rbp+var_24], ecx
0x1801625b0  lea     rax, [rbp+var_24]
0x1801625b4  mov     r9d, ecx; cbOutput
0x1801625b7  mov     [rsp+68h+pcbResult], rax; pcbResult
0x1801625bc  mov     rcx, [rbp+phAlgorithm]; hObject
0x1801625c0  lea     r8, [rbp+pbOutput]; pbOutput
0x1801625c4  lea     rdx, pszProperty; "HashDigestLength"
0x1801625cb  call    cs:__imp_BCryptGetProperty
0x1801625d1  mov     ebx, eax
0x1801625d3  test    eax, eax
0x1801625d5  js      loc_1801626B9
0x1801625db  mov     eax, dword ptr [rbp+pbOutput]
0x1801625de  mov     [r14], eax
0x1801625e1  cmp     [rbp+cbOutput], edi
0x1801625e4  jz      loc_1801626B9
0x1801625ea  cmp     [rbp+cbOutput], eax
0x1801625ed  jnb     short loc_1801625F9
0x1801625ef  mov     ebx, 0C0000023h
0x1801625f4  jmp     loc_1801626B9
0x1801625f9  mov     rcx, [rbp+phAlgorithm]; hObject
0x1801625fd  lea     rax, [rbp+var_24]
0x180162601  mov     r9d, 4; cbOutput
0x180162607  mov     [rsp+68h+cbSecret], edi; dwFlags
0x18016260b  lea     r8, [rbp+var_28]; pbOutput
0x18016260f  mov     [rbp+var_24], r9d
0x180162613  lea     rdx, aObjectlength; "ObjectLength"
0x18016261a  mov     [rsp+68h+pcbResult], rax; pcbResult
0x18016261f  call    cs:__imp_BCryptGetProperty
0x180162625  mov     ebx, eax
0x180162627  test    eax, eax
0x180162629  js      loc_1801626B9
0x18016262f  mov     ecx, dword ptr [rbp+var_28]; Size
0x180162632  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180162637  mov     r8d, dword ptr [rbp+var_28]; Size
0x18016263b  xor     edx, edx; Val
0x18016263d  mov     rcx, rax; void *
0x180162640  mov     rdi, rax
0x180162643  call    memset_0
0x180162648  mov     r8d, dword ptr [rbp+var_28]; Size
0x18016264c  xor     edx, edx; Val
0x18016264e  mov     rcx, rdi; void *
0x180162651  call    memset_0
0x180162656  mov     eax, [rbp+arg_20]
0x180162659  lea     rdx, [rbp+phHash]; phHash
0x18016265d  mov     r9d, dword ptr [rbp+var_28]; cbHashObject
0x180162661  mov     r8, rdi; pbHashObject
0x180162664  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x180162668  mov     [rsp+68h+var_38], 0; dwFlags
0x180162670  mov     [rsp+68h+cbSecret], eax; cbSecret
0x180162674  mov     rax, [rbp+pbSecret]
0x180162678  mov     [rsp+68h+pcbResult], rax; pbSecret
0x18016267d  call    cs:__imp_BCryptCreateHash
0x180162683  mov     ebx, eax
0x180162685  test    eax, eax
0x180162687  js      short loc_1801626B9
0x180162689  mov     rcx, [rbp+phHash]; hHash
0x18016268d  xor     r9d, r9d; dwFlags
0x180162690  mov     r8d, r12d; cbInput
0x180162693  mov     rdx, r13; pbInput
0x180162696  call    cs:__imp_BCryptHashData
0x18016269c  mov     ebx, eax
0x18016269e  test    eax, eax
0x1801626a0  js      short loc_1801626B9
0x1801626a2  mov     r8d, [rbp+cbOutput]; cbOutput
0x1801626a6  xor     r9d, r9d; dwFlags
0x1801626a9  mov     rdx, [rbp+arg_28]; pbOutput
0x1801626ad  mov     rcx, [rbp+phHash]; hHash
0x1801626b1  call    cs:__imp_BCryptFinishHash
0x1801626b7  mov     ebx, eax
0x1801626b9  mov     rcx, [rbp+phHash]; hHash
0x1801626bd  test    rcx, rcx
0x1801626c0  jz      short loc_1801626C8
0x1801626c2  call    cs:__imp_BCryptDestroyHash
0x1801626c8  test    rdi, rdi
0x1801626cb  jz      short loc_1801626EC
0x1801626cd  mov     eax, dword ptr [rbp+var_28]
0x1801626d0  mov     rcx, rdi
0x1801626d3  test    rax, rax
0x1801626d6  jz      short loc_1801626E4
0x1801626d8  mov     byte ptr [rcx], 0
0x1801626db  inc     rcx
0x1801626de  sub     rax, 1
0x1801626e2  jnz     short loc_1801626D8
0x1801626e4  mov     rcx, rdi; Block
0x1801626e7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1801626ec  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x1801626f0  mov     dword ptr [rbp+var_28], 0
0x1801626f7  test    rcx, rcx
0x1801626fa  jz      short loc_180162704
0x1801626fc  xor     edx, edx; dwFlags
0x1801626fe  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180162704  mov     eax, ebx
0x180162706  add     rsp, 68h
0x18016270a  pop     r14
0x18016270c  pop     r13
0x18016270e  pop     r12
0x180162710  pop     rdi
0x180162711  pop     rbx
0x180162712  pop     rbp
0x180162713  retn
```
