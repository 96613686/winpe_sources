# WinPlatformHash(ushort *,uchar *,uint,uchar *,uint,uchar *,uint,uint *,ulong)

- ea: `0x140055920`
- end: `0x140055b04`
- name: `?WinPlatformHash@@YAJPEAGPEAEI1I1IPEAIK@Z`
- size: `484`
- prototype: `__int64 __usercall@<rax>(LPCWSTR pszAlgId@<rcx>, PUCHAR pbInput@<rdx>, ULONG cbInput@<r8d>, unsigned __int8 *@<r9>, ULONG, PUCHAR, ULONG cbOutput, unsigned int *, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x14000f934`
- `0x140010514`
- `0x1400107b8`
- `0x140055920`

## import_xrefs

- `bcrypt!BCryptCreateHash` at `0x140055a6d`
- `bcrypt!BCryptCreateHash` at `0x140055a6d`
- `bcrypt!BCryptHashData` at `0x140055a86`
- `bcrypt!BCryptHashData` at `0x140055a86`
- `bcrypt!BCryptGetProperty` at `0x1400559bb`
- `bcrypt!BCryptGetProperty` at `0x140055a0f`
- `bcrypt!BCryptGetProperty` at `0x1400559bb`
- `bcrypt!BCryptGetProperty` at `0x140055a0f`
- `bcrypt!BCryptFinishHash` at `0x140055aa1`
- `bcrypt!BCryptFinishHash` at `0x140055aa1`
- `bcrypt!BCryptDestroyHash` at `0x140055ab2`
- `bcrypt!BCryptDestroyHash` at `0x140055ab2`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x140055984`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x140055984`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x140055aee`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x140055aee`

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
  NTSTATUS Property; // ebx
  void *v12; // rdi
  const struct std::nothrow_t *v13; // rdx
  ULONG v14; // eax
  __int64 v15; // rax
  _BYTE *v16; // rcx
  UCHAR v18[4]; // [rsp+40h] [rbp-28h] BYREF
  ULONG pcbResult; // [rsp+44h] [rbp-24h] BYREF
  UCHAR pbOutput[8]; // [rsp+48h] [rbp-20h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+50h] [rbp-18h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+58h] [rbp-10h] BYREF

  phAlgorithm = 0;
  phHash = 0;
  *(_DWORD *)v18 = 0;
  *(_DWORD *)pbOutput = 0;
  pcbResult = 0;
  if ( (!cbOutput || a6) && a8 )
  {
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
            Property = BCryptGetProperty(phAlgorithm, L"ObjectLength", v18, 4u, &pcbResult, 0);
            if ( Property >= 0 )
            {
              v12 = operator new[](*(unsigned int *)v18);
              memset_0(v12, 0, *(unsigned int *)v18);
              memset_0(v12, 0, *(unsigned int *)v18);
              Property = BCryptCreateHash(phAlgorithm, &phHash, (PUCHAR)v12, *(ULONG *)v18, a4, cbSecret, 0);
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
      v15 = *(unsigned int *)v18;
      v16 = v12;
      if ( *(_DWORD *)v18 )
      {
        do
        {
          *v16++ = 0;
          --v15;
        }
        while ( v15 );
      }
      operator delete(v12, v13);
    }
    *(_DWORD *)v18 = 0;
    if ( phAlgorithm )
      BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  }
  else
  {
    return (unsigned int)-1073741811;
  }
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x140055920  mov     [rsp-30h+pbSecret], r9
0x140055925  push    rbp
0x140055926  push    rbx
0x140055927  push    rdi
0x140055928  push    r12
0x14005592a  push    r13
0x14005592c  push    r14
0x14005592e  mov     rbp, rsp
0x140055931  sub     rsp, 68h
0x140055935  xor     eax, eax
0x140055937  mov     r12d, r8d
0x14005593a  mov     r13, rdx
0x14005593d  mov     [rbp+phAlgorithm], rax
0x140055941  mov     [rbp+phHash], rax
0x140055945  mov     dword ptr [rbp+var_28], eax
0x140055948  mov     dword ptr [rbp+pbOutput], eax
0x14005594b  mov     [rbp+var_24], eax
0x14005594e  cmp     [rbp+cbOutput], eax
0x140055951  jz      short loc_140055959
0x140055953  cmp     [rbp+arg_28], rax
0x140055957  jz      short loc_140055962
0x140055959  mov     r14, [rbp+arg_38]
0x14005595d  test    r14, r14
0x140055960  jnz     short loc_14005596C
0x140055962  mov     ebx, 0C000000Dh
0x140055967  jmp     loc_140055AF4
0x14005596c  mov     r9d, [rbp+dwFlags]; dwFlags
0x140055970  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x140055977  mov     rdx, rcx; pszAlgId
0x14005597a  mov     [r14], eax
0x14005597d  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x140055981  mov     rdi, rax
0x140055984  call    cs:__imp_BCryptOpenAlgorithmProvider
0x14005598a  mov     ebx, eax
0x14005598c  test    eax, eax
0x14005598e  js      loc_140055AA9
0x140055994  mov     ecx, 4
0x140055999  mov     [rsp+68h+cbSecret], edi; dwFlags
0x14005599d  mov     [rbp+var_24], ecx
0x1400559a0  lea     rax, [rbp+var_24]
0x1400559a4  mov     r9d, ecx; cbOutput
0x1400559a7  mov     [rsp+68h+pcbResult], rax; pcbResult
0x1400559ac  mov     rcx, [rbp+phAlgorithm]; hObject
0x1400559b0  lea     r8, [rbp+pbOutput]; pbOutput
0x1400559b4  lea     rdx, pszProperty; "HashDigestLength"
0x1400559bb  call    cs:__imp_BCryptGetProperty
0x1400559c1  mov     ebx, eax
0x1400559c3  test    eax, eax
0x1400559c5  js      loc_140055AA9
0x1400559cb  mov     eax, dword ptr [rbp+pbOutput]
0x1400559ce  mov     [r14], eax
0x1400559d1  cmp     [rbp+cbOutput], edi
0x1400559d4  jz      loc_140055AA9
0x1400559da  cmp     [rbp+cbOutput], eax
0x1400559dd  jnb     short loc_1400559E9
0x1400559df  mov     ebx, 0C0000023h
0x1400559e4  jmp     loc_140055AA9
0x1400559e9  mov     rcx, [rbp+phAlgorithm]; hObject
0x1400559ed  lea     rax, [rbp+var_24]
0x1400559f1  mov     r9d, 4; cbOutput
0x1400559f7  mov     [rsp+68h+cbSecret], edi; dwFlags
0x1400559fb  lea     r8, [rbp+var_28]; pbOutput
0x1400559ff  mov     [rbp+var_24], r9d
0x140055a03  lea     rdx, aObjectlength; "ObjectLength"
0x140055a0a  mov     [rsp+68h+pcbResult], rax; pcbResult
0x140055a0f  call    cs:__imp_BCryptGetProperty
0x140055a15  mov     ebx, eax
0x140055a17  test    eax, eax
0x140055a19  js      loc_140055AA9
0x140055a1f  mov     ecx, dword ptr [rbp+var_28]; unsigned __int64
0x140055a22  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x140055a27  mov     r8d, dword ptr [rbp+var_28]; Size
0x140055a2b  xor     edx, edx; Val
0x140055a2d  mov     rcx, rax; void *
0x140055a30  mov     rdi, rax
0x140055a33  call    memset_0
0x140055a38  mov     r8d, dword ptr [rbp+var_28]; Size
0x140055a3c  xor     edx, edx; Val
0x140055a3e  mov     rcx, rdi; void *
0x140055a41  call    memset_0
0x140055a46  mov     eax, [rbp+arg_20]
0x140055a49  lea     rdx, [rbp+phHash]; phHash
0x140055a4d  mov     r9d, dword ptr [rbp+var_28]; cbHashObject
0x140055a51  mov     r8, rdi; pbHashObject
0x140055a54  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x140055a58  mov     [rsp+68h+var_38], 0; dwFlags
0x140055a60  mov     [rsp+68h+cbSecret], eax; cbSecret
0x140055a64  mov     rax, [rbp+pbSecret]
0x140055a68  mov     [rsp+68h+pcbResult], rax; pbSecret
0x140055a6d  call    cs:__imp_BCryptCreateHash
0x140055a73  mov     ebx, eax
0x140055a75  test    eax, eax
0x140055a77  js      short loc_140055AA9
0x140055a79  mov     rcx, [rbp+phHash]; hHash
0x140055a7d  xor     r9d, r9d; dwFlags
0x140055a80  mov     r8d, r12d; cbInput
0x140055a83  mov     rdx, r13; pbInput
0x140055a86  call    cs:__imp_BCryptHashData
0x140055a8c  mov     ebx, eax
0x140055a8e  test    eax, eax
0x140055a90  js      short loc_140055AA9
0x140055a92  mov     r8d, [rbp+cbOutput]; cbOutput
0x140055a96  xor     r9d, r9d; dwFlags
0x140055a99  mov     rdx, [rbp+arg_28]; pbOutput
0x140055a9d  mov     rcx, [rbp+phHash]; hHash
0x140055aa1  call    cs:__imp_BCryptFinishHash
0x140055aa7  mov     ebx, eax
0x140055aa9  mov     rcx, [rbp+phHash]; hHash
0x140055aad  test    rcx, rcx
0x140055ab0  jz      short loc_140055AB8
0x140055ab2  call    cs:__imp_BCryptDestroyHash
0x140055ab8  test    rdi, rdi
0x140055abb  jz      short loc_140055ADC
0x140055abd  mov     eax, dword ptr [rbp+var_28]
0x140055ac0  mov     rcx, rdi
0x140055ac3  test    rax, rax
0x140055ac6  jz      short loc_140055AD4
0x140055ac8  mov     byte ptr [rcx], 0
0x140055acb  inc     rcx
0x140055ace  sub     rax, 1
0x140055ad2  jnz     short loc_140055AC8
0x140055ad4  mov     rcx, rdi; void *
0x140055ad7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140055adc  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x140055ae0  mov     dword ptr [rbp+var_28], 0
0x140055ae7  test    rcx, rcx
0x140055aea  jz      short loc_140055AF4
0x140055aec  xor     edx, edx; dwFlags
0x140055aee  call    cs:__imp_BCryptCloseAlgorithmProvider
0x140055af4  mov     eax, ebx
0x140055af6  add     rsp, 68h
0x140055afa  pop     r14
0x140055afc  pop     r13
0x140055afe  pop     r12
0x140055b00  pop     rdi
0x140055b01  pop     rbx
0x140055b02  pop     rbp
0x140055b03  retn
```
