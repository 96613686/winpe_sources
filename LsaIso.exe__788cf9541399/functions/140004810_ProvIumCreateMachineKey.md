# ProvIumCreateMachineKey

- ea: `0x140004810`
- end: `0x140004b6a`
- name: `ProvIumCreateMachineKey`
- size: `858`
- prototype: `__int64 __fastcall(__int64, unsigned int *, void **)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x140004810`
- `0x140004ca8`
- `0x140005820`
- `0x140036f94`
- `0x140038d10`
- `0x140038dd0`
- `0x14003a010`

## import_xrefs

- `bcrypt!BCryptDestroyKey` at `0x140004afd`
- `bcrypt!BCryptDestroyKey` at `0x140004afd`
- `bcrypt!BCryptFinalizeKeyPair` at `0x140004905`
- `bcrypt!BCryptFinalizeKeyPair` at `0x140004905`
- `bcrypt!BCryptGenerateKeyPair` at `0x1400048c8`
- `bcrypt!BCryptGenerateKeyPair` at `0x1400048c8`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x140004882`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x140004882`
- `bcrypt!BCryptExportKey` at `0x140004960`
- `bcrypt!BCryptExportKey` at `0x140004a5a`
- `bcrypt!BCryptExportKey` at `0x140004960`
- `bcrypt!BCryptExportKey` at `0x140004a5a`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x140004b0e`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x140004b0e`

## string_xrefs

- `0x140004add`: `ProvIumCreateMachineKey`

## pseudocode

```c
__int64 __fastcall ProvIumCreateMachineKey(__int64 a1, unsigned int *a2, void **a3)
{
  UCHAR *p_pcbResult; // rbx
  NTSTATUS v6; // edi
  _QWORD *v7; // rcx
  int v8; // edx
  unsigned __int64 v9; // rdi
  __int64 v10; // rcx
  unsigned __int64 v11; // rcx
  void *v12; // rsp
  void *v13; // rsp
  UCHAR *v14; // rax
  __int64 v15; // rax
  UCHAR *v16; // rcx
  __int64 v18; // [rsp+0h] [rbp-40h] BYREF
  ULONG pcbResult; // [rsp+40h] [rbp+0h] BYREF
  BCRYPT_KEY_HANDLE phKey; // [rsp+48h] [rbp+8h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+50h] [rbp+10h] BYREF
  __int128 v22; // [rsp+58h] [rbp+18h] BYREF
  __int128 v23; // [rsp+68h] [rbp+28h]
  __int64 v24; // [rsp+78h] [rbp+38h]

  phAlgorithm = 0;
  phKey = 0;
  v24 = 0;
  pcbResult = 0;
  v22 = 0;
  v23 = 0;
  if ( !a2 || !a3 )
    return 3221225485LL;
  p_pcbResult = 0;
  v6 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"RSA", 0, 0);
  if ( v6 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_41;
    v8 = 19;
    goto LABEL_40;
  }
  v6 = BCryptGenerateKeyPair(phAlgorithm, &phKey, 0x800u, 0);
  if ( v6 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_41;
    v8 = 20;
    goto LABEL_40;
  }
  v6 = BCryptFinalizeKeyPair(phKey, 0);
  if ( v6 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_41;
    v8 = 21;
    goto LABEL_40;
  }
  v6 = BCryptExportKey(phKey, 0, L"RSAPRIVATEBLOB", 0, 0, &pcbResult, 0);
  if ( v6 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_41;
    v8 = 22;
    goto LABEL_40;
  }
  v9 = pcbResult;
  if ( !pcbResult
    || pcbResult > (unsigned __int64)g_ulMaxStackAllocSize
    || (unsigned __int64)pcbResult + g_ulAdditionalProbeSize + 8 < pcbResult
    || !(unsigned int)VerifyStackAvailable() )
  {
    goto LABEL_54;
  }
  v10 = v9 + 23;
  if ( v9 + 23 <= v9 + 8 )
    v10 = 0xFFFFFFFFFFFFFF0LL;
  v11 = v10 & 0xFFFFFFFFFFFFFFF0uLL;
  v12 = alloca(v11);
  v13 = alloca(v11);
  p_pcbResult = (UCHAR *)&pcbResult;
  if ( &v18 == (__int64 *)-64LL || (pcbResult = 1801679955, (p_pcbResult = (UCHAR *)&phKey) == 0) )
  {
LABEL_54:
    if ( v9 + 8 >= v9 )
    {
      v14 = (UCHAR *)((__int64 (*)(void))g_pfnAllocate)();
      p_pcbResult = v14;
      if ( v14 )
      {
        *(_DWORD *)v14 = 1885431112;
        p_pcbResult = v14 + 8;
      }
    }
  }
  if ( p_pcbResult )
  {
    v6 = BCryptExportKey(phKey, 0, L"RSAPRIVATEBLOB", p_pcbResult, pcbResult, &pcbResult, 0);
    if ( v6 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_41;
      v8 = 23;
    }
    else
    {
      *((_QWORD *)&v22 + 1) = L"RSAPRIVATEBLOB";
      *(_QWORD *)&v22 = L"RSA";
      LODWORD(v23) = pcbResult;
      *((_QWORD *)&v23 + 1) = p_pcbResult;
      LODWORD(v24) = 1;
      v6 = LsaIsoEncryptAsymmetricKeyBlob((struct _LSA_ISO_ASYMMETRIC_KEY_BLOB *)&v22, a3, a2);
      if ( v6 >= 0 )
        goto LABEL_41;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_41;
      v8 = 24;
    }
LABEL_40:
    WPP_SF_sd(
      v7[2],
      v8,
      (unsigned int)&WPP_51646ada86fc316e06b18fa5421f3daa_Traceguids,
      (unsigned int)"ProvIumCreateMachineKey",
      v6);
    goto LABEL_41;
  }
  v6 = -1073741801;
LABEL_41:
  if ( phKey )
    BCryptDestroyKey(phKey);
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  if ( p_pcbResult )
  {
    v15 = pcbResult;
    v16 = p_pcbResult;
    if ( pcbResult )
    {
      do
      {
        *v16++ = 0;
        --v15;
      }
      while ( v15 );
    }
    if ( *((_DWORD *)p_pcbResult - 2) == 1885431112 )
      ((void (*)(void))g_pfnFree)();
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140004810  push    rbp
0x140004812  push    rbx
0x140004813  push    rsi
0x140004814  push    rdi
0x140004815  push    r13
0x140004817  push    r14
0x140004819  sub     rsp, 98h
0x140004820  lea     rbp, [rsp+40h]
0x140004825  mov     rax, cs:__security_cookie
0x14000482c  xor     rax, rbp
0x14000482f  mov     [rbp+80h+var_38], rax
0x140004833  xor     eax, eax
0x140004835  mov     [rbp+80h+phAlgorithm], 0
0x14000483d  mov     [rbp+80h+phKey], 0
0x140004845  xorps   xmm0, xmm0
0x140004848  mov     [rbp+80h+var_48], rax
0x14000484c  mov     rsi, r8
0x14000484f  mov     [rbp+80h+var_80], eax
0x140004852  mov     r14, rdx
0x140004855  movups  [rbp+80h+var_68], xmm0
0x140004859  movups  [rbp+80h+var_58], xmm0
0x14000485d  test    rdx, rdx
0x140004860  jz      loc_140004B4C
0x140004866  test    r8, r8
0x140004869  jz      loc_140004B4C
0x14000486f  xor     r9d, r9d; dwFlags
0x140004872  lea     rdx, aRsa; "RSA"
0x140004879  xor     r8d, r8d; pszImplementation
0x14000487c  lea     rcx, [rbp+80h+phAlgorithm]; phAlgorithm
0x140004880  xor     ebx, ebx
0x140004882  call    cs:__imp_BCryptOpenAlgorithmProvider
0x140004888  mov     edi, eax
0x14000488a  test    eax, eax
0x14000488c  jns     short loc_1400048B7
0x14000488e  mov     rcx, cs:WPP_GLOBAL_Control
0x140004895  lea     rax, WPP_GLOBAL_Control
0x14000489c  cmp     rcx, rax
0x14000489f  jz      loc_140004AF4
0x1400048a5  test    byte ptr [rcx+1Ch], 1
0x1400048a9  jz      loc_140004AF4
0x1400048af  lea     edx, [rbx+13h]
0x1400048b2  jmp     loc_140004AD9
0x1400048b7  mov     rcx, [rbp+80h+phAlgorithm]; hAlgorithm
0x1400048bb  lea     rdx, [rbp+80h+phKey]; phKey
0x1400048bf  xor     r9d, r9d; dwFlags
0x1400048c2  mov     r8d, 800h; dwLength
0x1400048c8  call    cs:__imp_BCryptGenerateKeyPair
0x1400048ce  mov     edi, eax
0x1400048d0  test    eax, eax
0x1400048d2  jns     short loc_1400048FF
0x1400048d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400048db  lea     rax, WPP_GLOBAL_Control
0x1400048e2  cmp     rcx, rax
0x1400048e5  jz      loc_140004AF4
0x1400048eb  test    byte ptr [rcx+1Ch], 1
0x1400048ef  jz      loc_140004AF4
0x1400048f5  mov     edx, 14h
0x1400048fa  jmp     loc_140004AD9
0x1400048ff  mov     rcx, [rbp+80h+phKey]; hKey
0x140004903  xor     edx, edx; dwFlags
0x140004905  call    cs:__imp_BCryptFinalizeKeyPair
0x14000490b  mov     edi, eax
0x14000490d  test    eax, eax
0x14000490f  jns     short loc_14000493C
0x140004911  mov     rcx, cs:WPP_GLOBAL_Control
0x140004918  lea     rax, WPP_GLOBAL_Control
0x14000491f  cmp     rcx, rax
0x140004922  jz      loc_140004AF4
0x140004928  test    byte ptr [rcx+1Ch], 1
0x14000492c  jz      loc_140004AF4
0x140004932  mov     edx, 15h
0x140004937  jmp     loc_140004AD9
0x14000493c  mov     rcx, [rbp+80h+phKey]; hKey
0x140004940  lea     rax, [rbp+80h+var_80]
0x140004944  mov     [rsp+0C0h+dwFlags], ebx; dwFlags
0x140004948  lea     r13, pszBlobType; "RSAPRIVATEBLOB"
0x14000494f  mov     [rsp+0C0h+pcbResult], rax; pcbResult
0x140004954  mov     r8, r13; pszBlobType
0x140004957  xor     r9d, r9d; pbOutput
0x14000495a  mov     [rsp+0C0h+cbOutput], ebx; cbOutput
0x14000495e  xor     edx, edx; hExportKey
0x140004960  call    cs:__imp_BCryptExportKey
0x140004966  mov     edi, eax
0x140004968  test    eax, eax
0x14000496a  jz      short loc_140004997
0x14000496c  mov     rcx, cs:WPP_GLOBAL_Control
0x140004973  lea     rax, WPP_GLOBAL_Control
0x14000497a  cmp     rcx, rax
0x14000497d  jz      loc_140004AF4
0x140004983  test    byte ptr [rcx+1Ch], 1
0x140004987  jz      loc_140004AF4
0x14000498d  mov     edx, 16h
0x140004992  jmp     loc_140004AD9
0x140004997  mov     edi, [rbp+80h+var_80]
0x14000499a  test    rdi, rdi
0x14000499d  jz      short loc_140004A00
0x14000499f  cmp     rdi, cs:g_ulMaxStackAllocSize
0x1400049a6  ja      short loc_140004A00
0x1400049a8  mov     rcx, cs:g_ulAdditionalProbeSize
0x1400049af  add     rcx, 8
0x1400049b3  add     rcx, rdi
0x1400049b6  cmp     rcx, rdi
0x1400049b9  jb      short loc_140004A00
0x1400049bb  call    VerifyStackAvailable
0x1400049c0  test    eax, eax
0x1400049c2  jz      short loc_140004A00
0x1400049c4  lea     rax, [rdi+8]
0x1400049c8  lea     rcx, [rax+0Fh]
0x1400049cc  cmp     rcx, rax
0x1400049cf  ja      short loc_1400049DB
0x1400049d1  mov     rcx, 0FFFFFFFFFFFFFF0h
0x1400049db  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1400049df  mov     rax, rcx
0x1400049e2  call    _alloca_probe
0x1400049e7  sub     rsp, rcx
0x1400049ea  lea     rbx, [rsp+0C0h+var_80]
0x1400049ef  test    rbx, rbx
0x1400049f2  jz      short loc_140004A00
0x1400049f4  mov     dword ptr [rbx], 6B637453h
0x1400049fa  add     rbx, 8
0x1400049fe  jnz     short loc_140004A27
0x140004a00  lea     rcx, [rdi+8]
0x140004a04  cmp     rcx, rdi
0x140004a07  jb      short loc_140004A27
0x140004a09  mov     rax, cs:g_pfnAllocate
0x140004a10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004a15  mov     rbx, rax
0x140004a18  test    rax, rax
0x140004a1b  jz      short loc_140004A27
0x140004a1d  mov     dword ptr [rax], 70616548h
0x140004a23  add     rbx, 8
0x140004a27  test    rbx, rbx
0x140004a2a  jnz     short loc_140004A36
0x140004a2c  mov     edi, 0C0000017h
0x140004a31  jmp     loc_140004AF4
0x140004a36  mov     rcx, [rbp+80h+phKey]; hKey
0x140004a3a  lea     rax, [rbp+80h+var_80]
0x140004a3e  mov     [rsp+0C0h+dwFlags], 0; dwFlags
0x140004a46  mov     r9, rbx; pbOutput
0x140004a49  mov     [rsp+0C0h+pcbResult], rax; pcbResult
0x140004a4e  mov     r8, r13; pszBlobType
0x140004a51  mov     eax, [rbp+80h+var_80]
0x140004a54  xor     edx, edx; hExportKey
0x140004a56  mov     [rsp+0C0h+cbOutput], eax; cbOutput
0x140004a5a  call    cs:__imp_BCryptExportKey
0x140004a60  mov     edi, eax
0x140004a62  test    eax, eax
0x140004a64  jz      short loc_140004A86
0x140004a66  mov     rcx, cs:WPP_GLOBAL_Control
0x140004a6d  lea     rax, WPP_GLOBAL_Control
0x140004a74  cmp     rcx, rax
0x140004a77  jz      short loc_140004AF4
0x140004a79  test    byte ptr [rcx+1Ch], 1
0x140004a7d  jz      short loc_140004AF4
0x140004a7f  mov     edx, 17h
0x140004a84  jmp     short loc_140004AD9
0x140004a86  lea     rax, aRsa; "RSA"
0x140004a8d  mov     qword ptr [rbp+80h+var_68+8], r13
0x140004a91  mov     qword ptr [rbp+80h+var_68], rax
0x140004a95  lea     rcx, [rbp+80h+var_68]; struct _LSA_ISO_ASYMMETRIC_KEY_BLOB *
0x140004a99  mov     eax, [rbp+80h+var_80]
0x140004a9c  mov     r8, r14; unsigned int *
0x140004a9f  mov     rdx, rsi; void **
0x140004aa2  mov     dword ptr [rbp+80h+var_58], eax
0x140004aa5  mov     qword ptr [rbp+80h+var_58+8], rbx
0x140004aa9  mov     dword ptr [rbp+80h+var_48], 1
0x140004ab0  call    ?LsaIsoEncryptAsymmetricKeyBlob@@YAJPEAU_LSA_ISO_ASYMMETRIC_KEY_BLOB@@PEAPEAXPEAK@Z; LsaIsoEncryptAsymmetricKeyBlob(_LSA_ISO_ASYMMETRIC_KEY_BLOB *,void * *,ulong *)
0x140004ab5  mov     edi, eax
0x140004ab7  test    eax, eax
0x140004ab9  jns     short loc_140004AF4
0x140004abb  mov     rcx, cs:WPP_GLOBAL_Control
0x140004ac2  lea     rax, WPP_GLOBAL_Control
0x140004ac9  cmp     rcx, rax
0x140004acc  jz      short loc_140004AF4
0x140004ace  test    byte ptr [rcx+1Ch], 1
0x140004ad2  jz      short loc_140004AF4
0x140004ad4  mov     edx, 18h
0x140004ad9  mov     rcx, [rcx+10h]
0x140004add  lea     r9, aProviumcreatem_1; "ProvIumCreateMachineKey"
0x140004ae4  lea     r8, WPP_51646ada86fc316e06b18fa5421f3daa_Traceguids
0x140004aeb  mov     [rsp+0C0h+cbOutput], edi
0x140004aef  call    WPP_SF_sd
0x140004af4  mov     rcx, [rbp+80h+phKey]; hKey
0x140004af8  test    rcx, rcx
0x140004afb  jz      short loc_140004B03
0x140004afd  call    cs:__imp_BCryptDestroyKey
0x140004b03  mov     rcx, [rbp+80h+phAlgorithm]; hAlgorithm
0x140004b07  test    rcx, rcx
0x140004b0a  jz      short loc_140004B14
0x140004b0c  xor     edx, edx; dwFlags
0x140004b0e  call    cs:__imp_BCryptCloseAlgorithmProvider
0x140004b14  test    rbx, rbx
0x140004b17  jz      short loc_140004B48
0x140004b19  mov     eax, [rbp+80h+var_80]
0x140004b1c  mov     rcx, rbx
0x140004b1f  test    rax, rax
0x140004b22  jz      short loc_140004B30
0x140004b24  mov     byte ptr [rcx], 0
0x140004b27  inc     rcx
0x140004b2a  sub     rax, 1
0x140004b2e  jnz     short loc_140004B24
0x140004b30  lea     rcx, [rbx-8]
0x140004b34  cmp     dword ptr [rcx], 70616548h
0x140004b3a  jnz     short loc_140004B48
0x140004b3c  mov     rax, cs:g_pfnFree
0x140004b43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004b48  mov     eax, edi
0x140004b4a  jmp     short loc_140004B51
0x140004b4c  mov     eax, 0C000000Dh
0x140004b51  mov     rcx, [rbp+80h+var_38]
0x140004b55  xor     rcx, rbp; StackCookie
0x140004b58  call    __security_check_cookie
0x140004b5d  lea     rsp, [rbp+58h]
0x140004b61  pop     r14
0x140004b63  pop     r13
0x140004b65  pop     rdi
0x140004b66  pop     rsi
0x140004b67  pop     rbx
0x140004b68  pop     rbp
0x140004b69  retn
```
