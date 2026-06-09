# WinPlatformHash(ushort *,uchar *,uint,uchar *,uint,uchar *,uint,uint *,ulong)

- ea: `0x180166970`
- end: `0x180166b85`
- name: `?WinPlatformHash@@YAJPEAGPEAEI1I1IPEAIK@Z`
- size: `533`
- prototype: `__int64 __usercall@<rax>(LPCWSTR pszAlgId@<rcx>, PUCHAR pbInput@<rdx>, ULONG cbInput@<r8d>, unsigned __int8 *@<r9>, ULONG, PUCHAR, ULONG cbOutput, unsigned int *, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000bddc`
- `0x18000c2f0`
- `0x18000c504`
- `0x180166970`

## import_xrefs

- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180166b68`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180166b68`
- `bcrypt!BCryptDestroyHash` at `0x180166b26`
- `bcrypt!BCryptDestroyHash` at `0x180166b26`
- `bcrypt!BCryptFinishHash` at `0x180166b0f`
- `bcrypt!BCryptFinishHash` at `0x180166b0f`
- `bcrypt!BCryptHashData` at `0x180166aee`
- `bcrypt!BCryptHashData` at `0x180166aee`
- `bcrypt!BCryptCreateHash` at `0x180166acf`
- `bcrypt!BCryptCreateHash` at `0x180166acf`
- `bcrypt!BCryptGetProperty` at `0x180166a11`
- `bcrypt!BCryptGetProperty` at `0x180166a6b`
- `bcrypt!BCryptGetProperty` at `0x180166a11`
- `bcrypt!BCryptGetProperty` at `0x180166a6b`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1801669d4`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1801669d4`

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
0x180166970  mov     [rsp-30h+pbSecret], r9
0x180166975  push    rbp
0x180166976  push    rbx
0x180166977  push    rdi
0x180166978  push    r12
0x18016697a  push    r13
0x18016697c  push    r14
0x18016697e  mov     rbp, rsp
0x180166981  sub     rsp, 68h
0x180166985  xor     eax, eax
0x180166987  mov     r12d, r8d
0x18016698a  mov     r13, rdx
0x18016698d  mov     [rbp+phAlgorithm], rax
0x180166991  mov     [rbp+phHash], rax
0x180166995  mov     dword ptr [rbp+var_28], eax
0x180166998  mov     dword ptr [rbp+pbOutput], eax
0x18016699b  mov     [rbp+var_24], eax
0x18016699e  cmp     [rbp+cbOutput], eax
0x1801669a1  jz      short loc_1801669A9
0x1801669a3  cmp     [rbp+arg_28], rax
0x1801669a7  jz      short loc_1801669B2
0x1801669a9  mov     r14, [rbp+arg_38]
0x1801669ad  test    r14, r14
0x1801669b0  jnz     short loc_1801669BC
0x1801669b2  mov     eax, 80070057h
0x1801669b7  jmp     loc_180166B76
0x1801669bc  mov     r9d, [rbp+dwFlags]; dwFlags
0x1801669c0  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x1801669c7  mov     rdx, rcx; pszAlgId
0x1801669ca  mov     [r14], eax
0x1801669cd  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x1801669d1  mov     rdi, rax
0x1801669d4  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1801669db  nop     dword ptr [rax+rax+00h]
0x1801669e0  mov     ebx, eax
0x1801669e2  test    eax, eax
0x1801669e4  js      loc_180166B1D
0x1801669ea  mov     ecx, 4
0x1801669ef  mov     [rsp+68h+cbSecret], edi; dwFlags
0x1801669f3  mov     [rbp+var_24], ecx
0x1801669f6  lea     rax, [rbp+var_24]
0x1801669fa  mov     r9d, ecx; cbOutput
0x1801669fd  mov     [rsp+68h+pcbResult], rax; pcbResult
0x180166a02  mov     rcx, [rbp+phAlgorithm]; hObject
0x180166a06  lea     r8, [rbp+pbOutput]; pbOutput
0x180166a0a  lea     rdx, pszProperty; "HashDigestLength"
0x180166a11  call    cs:__imp_BCryptGetProperty
0x180166a18  nop     dword ptr [rax+rax+00h]
0x180166a1d  mov     ebx, eax
0x180166a1f  test    eax, eax
0x180166a21  js      loc_180166B1D
0x180166a27  mov     eax, dword ptr [rbp+pbOutput]
0x180166a2a  mov     [r14], eax
0x180166a2d  cmp     [rbp+cbOutput], edi
0x180166a30  jz      loc_180166B1D
0x180166a36  cmp     [rbp+cbOutput], eax
0x180166a39  jnb     short loc_180166A45
0x180166a3b  mov     ebx, 0C0000023h
0x180166a40  jmp     loc_180166B1D
0x180166a45  mov     rcx, [rbp+phAlgorithm]; hObject
0x180166a49  lea     rax, [rbp+var_24]
0x180166a4d  mov     r9d, 4; cbOutput
0x180166a53  mov     [rsp+68h+cbSecret], edi; dwFlags
0x180166a57  lea     r8, [rbp+var_28]; pbOutput
0x180166a5b  mov     [rbp+var_24], r9d
0x180166a5f  lea     rdx, aObjectlength; "ObjectLength"
0x180166a66  mov     [rsp+68h+pcbResult], rax; pcbResult
0x180166a6b  call    cs:__imp_BCryptGetProperty
0x180166a72  nop     dword ptr [rax+rax+00h]
0x180166a77  mov     ebx, eax
0x180166a79  test    eax, eax
0x180166a7b  js      loc_180166B1D
0x180166a81  mov     ecx, dword ptr [rbp+var_28]; Size
0x180166a84  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180166a89  mov     r8d, dword ptr [rbp+var_28]; Size
0x180166a8d  xor     edx, edx; Val
0x180166a8f  mov     rcx, rax; void *
0x180166a92  mov     rdi, rax
0x180166a95  call    memset_0
0x180166a9a  mov     r8d, dword ptr [rbp+var_28]; Size
0x180166a9e  xor     edx, edx; Val
0x180166aa0  mov     rcx, rdi; void *
0x180166aa3  call    memset_0
0x180166aa8  mov     eax, [rbp+arg_20]
0x180166aab  lea     rdx, [rbp+phHash]; phHash
0x180166aaf  mov     r9d, dword ptr [rbp+var_28]; cbHashObject
0x180166ab3  mov     r8, rdi; pbHashObject
0x180166ab6  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x180166aba  mov     [rsp+68h+var_38], 0; dwFlags
0x180166ac2  mov     [rsp+68h+cbSecret], eax; cbSecret
0x180166ac6  mov     rax, [rbp+pbSecret]
0x180166aca  mov     [rsp+68h+pcbResult], rax; pbSecret
0x180166acf  call    cs:__imp_BCryptCreateHash
0x180166ad6  nop     dword ptr [rax+rax+00h]
0x180166adb  mov     ebx, eax
0x180166add  test    eax, eax
0x180166adf  js      short loc_180166B1D
0x180166ae1  mov     rcx, [rbp+phHash]; hHash
0x180166ae5  xor     r9d, r9d; dwFlags
0x180166ae8  mov     r8d, r12d; cbInput
0x180166aeb  mov     rdx, r13; pbInput
0x180166aee  call    cs:__imp_BCryptHashData
0x180166af5  nop     dword ptr [rax+rax+00h]
0x180166afa  mov     ebx, eax
0x180166afc  test    eax, eax
0x180166afe  js      short loc_180166B1D
0x180166b00  mov     r8d, [rbp+cbOutput]; cbOutput
0x180166b04  xor     r9d, r9d; dwFlags
0x180166b07  mov     rdx, [rbp+arg_28]; pbOutput
0x180166b0b  mov     rcx, [rbp+phHash]; hHash
0x180166b0f  call    cs:__imp_BCryptFinishHash
0x180166b16  nop     dword ptr [rax+rax+00h]
0x180166b1b  mov     ebx, eax
0x180166b1d  mov     rcx, [rbp+phHash]; hHash
0x180166b21  test    rcx, rcx
0x180166b24  jz      short loc_180166B32
0x180166b26  call    cs:__imp_BCryptDestroyHash
0x180166b2d  nop     dword ptr [rax+rax+00h]
0x180166b32  test    rdi, rdi
0x180166b35  jz      short loc_180166B56
0x180166b37  mov     eax, dword ptr [rbp+var_28]
0x180166b3a  mov     rcx, rdi
0x180166b3d  test    rax, rax
0x180166b40  jz      short loc_180166B4E
0x180166b42  mov     byte ptr [rcx], 0
0x180166b45  inc     rcx
0x180166b48  sub     rax, 1
0x180166b4c  jnz     short loc_180166B42
0x180166b4e  mov     rcx, rdi; Block
0x180166b51  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180166b56  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x180166b5a  mov     dword ptr [rbp+var_28], 0
0x180166b61  test    rcx, rcx
0x180166b64  jz      short loc_180166B74
0x180166b66  xor     edx, edx; dwFlags
0x180166b68  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180166b6f  nop     dword ptr [rax+rax+00h]
0x180166b74  mov     eax, ebx
0x180166b76  add     rsp, 68h
0x180166b7a  pop     r14
0x180166b7c  pop     r13
0x180166b7e  pop     r12
0x180166b80  pop     rdi
0x180166b81  pop     rbx
0x180166b82  pop     rbp
0x180166b83  retn
```
