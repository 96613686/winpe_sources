# WinPlatformHash(ushort *,uchar *,uint,uchar *,uint,uchar *,uint,uint *,ulong)

- ea: `0x180063c70`
- end: `0x180063e85`
- name: `?WinPlatformHash@@YAJPEAGPEAEI1I1IPEAIK@Z`
- size: `533`
- prototype: `__int64 __usercall@<rax>(LPCWSTR pszAlgId@<rcx>, PUCHAR pbInput@<rdx>, ULONG cbInput@<r8d>, unsigned __int8 *@<r9>, ULONG, PUCHAR, ULONG cbOutput, unsigned int *, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18002cdec`
- `0x18002ce54`
- `0x18002d518`
- `0x180063c70`

## import_xrefs

- `bcrypt!BCryptCreateHash` at `0x180063dcf`
- `bcrypt!BCryptCreateHash` at `0x180063dcf`
- `bcrypt!BCryptHashData` at `0x180063dee`
- `bcrypt!BCryptHashData` at `0x180063dee`
- `bcrypt!BCryptFinishHash` at `0x180063e0f`
- `bcrypt!BCryptFinishHash` at `0x180063e0f`
- `bcrypt!BCryptDestroyHash` at `0x180063e26`
- `bcrypt!BCryptDestroyHash` at `0x180063e26`
- `bcrypt!BCryptGetProperty` at `0x180063d11`
- `bcrypt!BCryptGetProperty` at `0x180063d6b`
- `bcrypt!BCryptGetProperty` at `0x180063d11`
- `bcrypt!BCryptGetProperty` at `0x180063d6b`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180063cd4`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180063cd4`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180063e68`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180063e68`

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
0x180063c70  mov     [rsp-30h+pbSecret], r9
0x180063c75  push    rbp
0x180063c76  push    rbx
0x180063c77  push    rdi
0x180063c78  push    r12
0x180063c7a  push    r13
0x180063c7c  push    r14
0x180063c7e  mov     rbp, rsp
0x180063c81  sub     rsp, 68h
0x180063c85  xor     eax, eax
0x180063c87  mov     r12d, r8d
0x180063c8a  mov     r13, rdx
0x180063c8d  mov     [rbp+phAlgorithm], rax
0x180063c91  mov     [rbp+phHash], rax
0x180063c95  mov     dword ptr [rbp+var_28], eax
0x180063c98  mov     dword ptr [rbp+pbOutput], eax
0x180063c9b  mov     [rbp+var_24], eax
0x180063c9e  cmp     [rbp+cbOutput], eax
0x180063ca1  jz      short loc_180063CA9
0x180063ca3  cmp     [rbp+arg_28], rax
0x180063ca7  jz      short loc_180063CB2
0x180063ca9  mov     r14, [rbp+arg_38]
0x180063cad  test    r14, r14
0x180063cb0  jnz     short loc_180063CBC
0x180063cb2  mov     eax, 80070057h
0x180063cb7  jmp     loc_180063E76
0x180063cbc  mov     r9d, [rbp+dwFlags]; dwFlags
0x180063cc0  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x180063cc7  mov     rdx, rcx; pszAlgId
0x180063cca  mov     [r14], eax
0x180063ccd  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x180063cd1  mov     rdi, rax
0x180063cd4  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180063cdb  nop     dword ptr [rax+rax+00h]
0x180063ce0  mov     ebx, eax
0x180063ce2  test    eax, eax
0x180063ce4  js      loc_180063E1D
0x180063cea  mov     ecx, 4
0x180063cef  mov     [rsp+68h+cbSecret], edi; dwFlags
0x180063cf3  mov     [rbp+var_24], ecx
0x180063cf6  lea     rax, [rbp+var_24]
0x180063cfa  mov     r9d, ecx; cbOutput
0x180063cfd  mov     [rsp+68h+pcbResult], rax; pcbResult
0x180063d02  mov     rcx, [rbp+phAlgorithm]; hObject
0x180063d06  lea     r8, [rbp+pbOutput]; pbOutput
0x180063d0a  lea     rdx, pszProperty; "HashDigestLength"
0x180063d11  call    cs:__imp_BCryptGetProperty
0x180063d18  nop     dword ptr [rax+rax+00h]
0x180063d1d  mov     ebx, eax
0x180063d1f  test    eax, eax
0x180063d21  js      loc_180063E1D
0x180063d27  mov     eax, dword ptr [rbp+pbOutput]
0x180063d2a  mov     [r14], eax
0x180063d2d  cmp     [rbp+cbOutput], edi
0x180063d30  jz      loc_180063E1D
0x180063d36  cmp     [rbp+cbOutput], eax
0x180063d39  jnb     short loc_180063D45
0x180063d3b  mov     ebx, 0C0000023h
0x180063d40  jmp     loc_180063E1D
0x180063d45  mov     rcx, [rbp+phAlgorithm]; hObject
0x180063d49  lea     rax, [rbp+var_24]
0x180063d4d  mov     r9d, 4; cbOutput
0x180063d53  mov     [rsp+68h+cbSecret], edi; dwFlags
0x180063d57  lea     r8, [rbp+var_28]; pbOutput
0x180063d5b  mov     [rbp+var_24], r9d
0x180063d5f  lea     rdx, aObjectlength; "ObjectLength"
0x180063d66  mov     [rsp+68h+pcbResult], rax; pcbResult
0x180063d6b  call    cs:__imp_BCryptGetProperty
0x180063d72  nop     dword ptr [rax+rax+00h]
0x180063d77  mov     ebx, eax
0x180063d79  test    eax, eax
0x180063d7b  js      loc_180063E1D
0x180063d81  mov     ecx, dword ptr [rbp+var_28]; Size
0x180063d84  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180063d89  mov     r8d, dword ptr [rbp+var_28]; Size
0x180063d8d  xor     edx, edx; Val
0x180063d8f  mov     rcx, rax; void *
0x180063d92  mov     rdi, rax
0x180063d95  call    memset_0
0x180063d9a  mov     r8d, dword ptr [rbp+var_28]; Size
0x180063d9e  xor     edx, edx; Val
0x180063da0  mov     rcx, rdi; void *
0x180063da3  call    memset_0
0x180063da8  mov     eax, [rbp+arg_20]
0x180063dab  lea     rdx, [rbp+phHash]; phHash
0x180063daf  mov     r9d, dword ptr [rbp+var_28]; cbHashObject
0x180063db3  mov     r8, rdi; pbHashObject
0x180063db6  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x180063dba  mov     [rsp+68h+var_38], 0; dwFlags
0x180063dc2  mov     [rsp+68h+cbSecret], eax; cbSecret
0x180063dc6  mov     rax, [rbp+pbSecret]
0x180063dca  mov     [rsp+68h+pcbResult], rax; pbSecret
0x180063dcf  call    cs:__imp_BCryptCreateHash
0x180063dd6  nop     dword ptr [rax+rax+00h]
0x180063ddb  mov     ebx, eax
0x180063ddd  test    eax, eax
0x180063ddf  js      short loc_180063E1D
0x180063de1  mov     rcx, [rbp+phHash]; hHash
0x180063de5  xor     r9d, r9d; dwFlags
0x180063de8  mov     r8d, r12d; cbInput
0x180063deb  mov     rdx, r13; pbInput
0x180063dee  call    cs:__imp_BCryptHashData
0x180063df5  nop     dword ptr [rax+rax+00h]
0x180063dfa  mov     ebx, eax
0x180063dfc  test    eax, eax
0x180063dfe  js      short loc_180063E1D
0x180063e00  mov     r8d, [rbp+cbOutput]; cbOutput
0x180063e04  xor     r9d, r9d; dwFlags
0x180063e07  mov     rdx, [rbp+arg_28]; pbOutput
0x180063e0b  mov     rcx, [rbp+phHash]; hHash
0x180063e0f  call    cs:__imp_BCryptFinishHash
0x180063e16  nop     dword ptr [rax+rax+00h]
0x180063e1b  mov     ebx, eax
0x180063e1d  mov     rcx, [rbp+phHash]; hHash
0x180063e21  test    rcx, rcx
0x180063e24  jz      short loc_180063E32
0x180063e26  call    cs:__imp_BCryptDestroyHash
0x180063e2d  nop     dword ptr [rax+rax+00h]
0x180063e32  test    rdi, rdi
0x180063e35  jz      short loc_180063E56
0x180063e37  mov     eax, dword ptr [rbp+var_28]
0x180063e3a  mov     rcx, rdi
0x180063e3d  test    rax, rax
0x180063e40  jz      short loc_180063E4E
0x180063e42  mov     byte ptr [rcx], 0
0x180063e45  inc     rcx
0x180063e48  sub     rax, 1
0x180063e4c  jnz     short loc_180063E42
0x180063e4e  mov     rcx, rdi; Block
0x180063e51  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180063e56  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x180063e5a  mov     dword ptr [rbp+var_28], 0
0x180063e61  test    rcx, rcx
0x180063e64  jz      short loc_180063E74
0x180063e66  xor     edx, edx; dwFlags
0x180063e68  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180063e6f  nop     dword ptr [rax+rax+00h]
0x180063e74  mov     eax, ebx
0x180063e76  add     rsp, 68h
0x180063e7a  pop     r14
0x180063e7c  pop     r13
0x180063e7e  pop     r12
0x180063e80  pop     rdi
0x180063e81  pop     rbx
0x180063e82  pop     rbp
0x180063e83  retn
```
