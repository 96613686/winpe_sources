# ApplySignaturePadding(ulong,void *,uchar *,ulong,uchar *,ulong)

- ea: `0x180065aa8`
- end: `0x180065d72`
- name: `?ApplySignaturePadding@@YAJKPEAXPEAEK1K@Z`
- size: `714`
- prototype: `__int64 __fastcall(unsigned int, void *, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config`

## callers

- `0x18006aa78`

## callees

- `0x1800133c4`
- `0x180014a60`
- `0x1800157c0`
- `0x180029a20`
- `0x180061bac`
- `0x180063c98`
- `0x180065aa8`
- `0x1800768a0`
- `0x1800912b4`

## import_xrefs

- `bcrypt!BCryptGetProperty` at `0x180065bbb`
- `bcrypt!BCryptGetProperty` at `0x180065c24`
- `bcrypt!BCryptGetProperty` at `0x180065c86`
- `bcrypt!BCryptGetProperty` at `0x180065bbb`
- `bcrypt!BCryptGetProperty` at `0x180065c24`
- `bcrypt!BCryptGetProperty` at `0x180065c86`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180065b53`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180065b53`

## pseudocode

```c
__int64 __fastcall ApplySignaturePadding(
        char a1,
        const WCHAR **a2,
        unsigned __int8 *a3,
        unsigned int a4,
        unsigned __int8 *a5,
        unsigned int a6)
{
  unsigned __int8 *v10; // rdi
  const WCHAR *v11; // rdx
  int v12; // eax
  unsigned int v13; // ebx
  __int64 v14; // r9
  __int64 v15; // rdx
  __int64 v16; // rdx
  NTSTATUS Property; // eax
  __int64 v18; // rdx
  unsigned int **v19; // rbx
  NTSTATUS v20; // eax
  const struct std::nothrow_t *v21; // rdx
  int v22; // edi
  __int64 v23; // rdx
  const struct std::nothrow_t *v24; // rdx
  int pcbResult; // [rsp+20h] [rbp-58h]
  int pcbResulta; // [rsp+20h] [rbp-58h]
  UCHAR pbOutput[4]; // [rsp+40h] [rbp-38h] BYREF
  ULONG v29; // [rsp+44h] [rbp-34h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+48h] [rbp-30h] BYREF
  PUCHAR v31; // [rsp+50h] [rbp-28h] BYREF
  int *v32[4]; // [rsp+58h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+30h]
  ULONG cbOutput; // [rsp+B8h] [rbp+40h] BYREF

  KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)v32, L"ApplySignaturePadding", 1);
  v29 = 0;
  if ( !a2 || !a3 || (v10 = a5) == 0 || (a1 & 2) == 0 )
  {
    v13 = -2146893785;
    v15 = 2030;
    v14 = 2148073511LL;
    goto LABEL_33;
  }
  v11 = *a2;
  if ( !*a2 )
  {
    v12 = ApplyPKCS1SigningFormat(0, 0, a3, a4, a5, a6, 0);
    v13 = v12;
    if ( v12 < 0 )
    {
      v14 = (unsigned int)v12;
      v15 = 2042;
LABEL_33:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v15,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmhelpers20.cpp",
        (const char *)v14,
        pcbResult);
      goto LABEL_34;
    }
    goto LABEL_31;
  }
  phAlgorithm = 0;
  if ( BCryptOpenAlgorithmProvider(&phAlgorithm, v11, 0, 0) >= 0 )
  {
    *(_DWORD *)pbOutput = 0;
    Property = BCryptGetProperty(phAlgorithm, L"HashDigestLength", pbOutput, 4u, &v29, 0);
    if ( Property < 0 )
    {
      v18 = 2060;
LABEL_14:
      v13 = wil::details::in1diag3::Return_NtStatus(
              retaddr,
              (void *)v18,
              (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmhelpers20.cpp",
              (const char *)(unsigned int)Property,
              pcbResult);
      goto LABEL_11;
    }
    if ( *(_DWORD *)pbOutput != a4 )
    {
      v13 = -2146893785;
      v16 = 2062;
      goto LABEL_10;
    }
    cbOutput = 0;
    Property = BCryptGetProperty(phAlgorithm, L"HashOIDList", 0, 0, &cbOutput, 0);
    if ( Property < 0 )
    {
      v18 = 2070;
      goto LABEL_14;
    }
    wil::make_unique_nothrow<unsigned char [0]>(&v31, cbOutput);
    v19 = (unsigned int **)v31;
    if ( !v31 )
    {
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
      v13 = -2147024888;
      goto LABEL_34;
    }
    v20 = BCryptGetProperty(phAlgorithm, L"HashOIDList", v31, cbOutput, &v29, 0);
    if ( v20 >= 0 )
    {
      if ( *(_DWORD *)v19 )
      {
        v22 = ApplyPKCS1SigningFormat(*((const unsigned __int8 **)v19[1] + 1), *v19[1], a3, a4, v10, a6, 1);
        if ( v22 >= 0 )
        {
          operator delete(v19, v24);
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
LABEL_31:
          v13 = 0;
          goto LABEL_34;
        }
        v23 = 2093;
      }
      else
      {
        v22 = -2146893779;
        v23 = 2084;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v23,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmhelpers20.cpp",
        (const char *)(unsigned int)v22,
        pcbResulta);
    }
    else
    {
      v22 = wil::details::in1diag3::Return_NtStatus(
              retaddr,
              (void *)0x820,
              (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmhelpers20.cpp",
              (const char *)(unsigned int)v20,
              pcbResulta);
      if ( !v19 )
      {
LABEL_24:
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
        v13 = v22;
        goto LABEL_34;
      }
    }
    operator delete(v19, v21);
    goto LABEL_24;
  }
  v13 = -2146893783;
  v16 = 2052;
LABEL_10:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v16,
    (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmhelpers20.cpp",
    (const char *)v13,
    pcbResult);
LABEL_11:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
LABEL_34:
  KspFunctionLogger::~KspFunctionLogger(v32);
  return v13;
}

```

## disassembly

```asm
0x180065aa8  push    rbp
0x180065aaa  push    rbx
0x180065aab  push    rsi
0x180065aac  push    rdi
0x180065aad  push    r14
0x180065aaf  push    r15
0x180065ab1  mov     rbp, rsp
0x180065ab4  sub     rsp, 78h
0x180065ab8  mov     r15, r8
0x180065abb  mov     r14, rdx
0x180065abe  mov     ebx, ecx
0x180065ac0  lea     rdx, aApplysignature; "ApplySignaturePadding"
0x180065ac7  mov     r8b, 1; bool
0x180065aca  lea     rcx, [rbp+var_20]; this
0x180065ace  mov     esi, r9d
0x180065ad1  call    ??0KspFunctionLogger@@QEAA@QEBG_N@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,bool)
0x180065ad6  mov     [rbp+var_34], 0
0x180065add  test    r14, r14
0x180065ae0  jz      loc_180065D3C
0x180065ae6  test    r15, r15
0x180065ae9  jz      loc_180065D3C
0x180065aef  mov     rdi, [rbp+arg_20]
0x180065af3  test    rdi, rdi
0x180065af6  jz      loc_180065D3C
0x180065afc  test    bl, 2
0x180065aff  jz      loc_180065D3C
0x180065b05  mov     rdx, [r14]; unsigned int
0x180065b08  test    rdx, rdx
0x180065b0b  jnz     short loc_180065B41
0x180065b0d  mov     eax, [rbp+arg_28]
0x180065b10  mov     r9d, esi; unsigned int
0x180065b13  mov     [rsp+78h+var_48], edx; int
0x180065b17  mov     r8, r15; unsigned __int8 *
0x180065b1a  mov     [rsp+78h+dwFlags], eax; unsigned int
0x180065b1e  xor     ecx, ecx; unsigned __int8 *
0x180065b20  mov     [rsp+78h+pcbResult], rdi; unsigned __int8 *
0x180065b25  call    ?ApplyPKCS1SigningFormat@@YAJPEBEK0KPEAEKH@Z; ApplyPKCS1SigningFormat(uchar const *,ulong,uchar const *,ulong,uchar *,ulong,int)
0x180065b2a  mov     ebx, eax
0x180065b2c  test    eax, eax
0x180065b2e  jns     loc_180065D38
0x180065b34  mov     r9d, eax
0x180065b37  mov     edx, 7FAh
0x180065b3c  jmp     loc_180065D49
0x180065b41  xor     r9d, r9d; dwFlags
0x180065b44  mov     [rbp+phAlgorithm], 0
0x180065b4c  xor     r8d, r8d; pszImplementation
0x180065b4f  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x180065b53  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180065b5a  nop     dword ptr [rax+rax+00h]
0x180065b5f  test    eax, eax
0x180065b61  jns     short loc_180065B8E
0x180065b63  mov     ebx, 80090029h
0x180065b68  mov     edx, 804h; void *
0x180065b6d  mov     rcx, [rbp+30h]; this
0x180065b71  lea     r8, aOnecoreBaseNgs_14; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180065b78  mov     r9d, ebx; char *
0x180065b7b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180065b80  lea     rcx, [rbp+phAlgorithm]
0x180065b84  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180065b89  jmp     loc_180065D59
0x180065b8e  mov     rcx, [rbp+phAlgorithm]; hObject
0x180065b92  lea     rax, [rbp+var_34]
0x180065b96  mov     [rsp+78h+dwFlags], 0; dwFlags
0x180065b9e  lea     r8, [rbp+pbOutput]; pbOutput
0x180065ba2  mov     r9d, 4; cbOutput
0x180065ba8  mov     [rsp+78h+pcbResult], rax; int
0x180065bad  lea     rdx, aHashdigestleng; "HashDigestLength"
0x180065bb4  mov     dword ptr [rbp+pbOutput], 0
0x180065bbb  call    cs:__imp_BCryptGetProperty
0x180065bc2  nop     dword ptr [rax+rax+00h]
0x180065bc7  test    eax, eax
0x180065bc9  jns     short loc_180065BE7
0x180065bcb  mov     edx, 80Ch; void *
0x180065bd0  mov     rcx, [rbp+30h]; this
0x180065bd4  lea     r8, aOnecoreBaseNgs_14; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180065bdb  mov     r9d, eax; char *
0x180065bde  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180065be3  mov     ebx, eax
0x180065be5  jmp     short loc_180065B80
0x180065be7  cmp     dword ptr [rbp+pbOutput], esi
0x180065bea  jz      short loc_180065BFB
0x180065bec  mov     ebx, 80090027h
0x180065bf1  mov     edx, 80Eh
0x180065bf6  jmp     loc_180065B6D
0x180065bfb  mov     rcx, [rbp+phAlgorithm]; hObject
0x180065bff  lea     rax, [rbp+cbOutput]
0x180065c03  mov     [rsp+78h+dwFlags], 0; dwFlags
0x180065c0b  lea     rdx, aHashoidlist; "HashOIDList"
0x180065c12  xor     r9d, r9d; cbOutput
0x180065c15  mov     [rsp+78h+pcbResult], rax; pcbResult
0x180065c1a  xor     r8d, r8d; pbOutput
0x180065c1d  mov     [rbp+cbOutput], 0
0x180065c24  call    cs:__imp_BCryptGetProperty
0x180065c2b  nop     dword ptr [rax+rax+00h]
0x180065c30  test    eax, eax
0x180065c32  jns     short loc_180065C3B
0x180065c34  mov     edx, 816h
0x180065c39  jmp     short loc_180065BD0
0x180065c3b  mov     edx, [rbp+cbOutput]
0x180065c3e  lea     rcx, [rbp+var_28]
0x180065c42  call    ??$make_unique_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<uchar [0]>(unsigned __int64)
0x180065c47  mov     rbx, [rbp+var_28]
0x180065c4b  test    rbx, rbx
0x180065c4e  jnz     short loc_180065C63
0x180065c50  lea     rcx, [rbp+phAlgorithm]
0x180065c54  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180065c59  mov     ebx, 80070008h
0x180065c5e  jmp     loc_180065D59
0x180065c63  mov     r9d, [rbp+cbOutput]; cbOutput
0x180065c67  lea     rax, [rbp+var_34]
0x180065c6b  mov     rcx, [rbp+phAlgorithm]; hObject
0x180065c6f  lea     rdx, aHashoidlist; "HashOIDList"
0x180065c76  mov     [rsp+78h+dwFlags], 0; dwFlags
0x180065c7e  mov     r8, rbx; pbOutput
0x180065c81  mov     [rsp+78h+pcbResult], rax; int
0x180065c86  call    cs:__imp_BCryptGetProperty
0x180065c8d  nop     dword ptr [rax+rax+00h]
0x180065c92  test    eax, eax
0x180065c94  jns     short loc_180065CCD
0x180065c96  mov     rcx, [rbp+30h]; this
0x180065c9a  lea     r8, aOnecoreBaseNgs_14; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180065ca1  mov     r9d, eax; char *
0x180065ca4  mov     edx, 820h; void *
0x180065ca9  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180065cae  mov     edi, eax
0x180065cb0  test    rbx, rbx
0x180065cb3  jz      short loc_180065CBD
0x180065cb5  mov     rcx, rbx; void *
0x180065cb8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180065cbd  lea     rcx, [rbp+phAlgorithm]
0x180065cc1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180065cc6  mov     ebx, edi
0x180065cc8  jmp     loc_180065D59
0x180065ccd  cmp     dword ptr [rbx], 0
0x180065cd0  jnz     short loc_180065CF1
0x180065cd2  mov     edi, 8009002Dh
0x180065cd7  mov     edx, 824h; void *
0x180065cdc  mov     rcx, [rbp+30h]; this
0x180065ce0  lea     r8, aOnecoreBaseNgs_14; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180065ce7  mov     r9d, edi; char *
0x180065cea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180065cef  jmp     short loc_180065CB5
0x180065cf1  mov     rcx, [rbx+8]
0x180065cf5  mov     r9d, esi; unsigned int
0x180065cf8  mov     eax, [rbp+arg_28]
0x180065cfb  mov     r8, r15; unsigned __int8 *
0x180065cfe  mov     [rsp+78h+var_48], 1; int
0x180065d06  mov     [rsp+78h+dwFlags], eax; unsigned int
0x180065d0a  mov     edx, [rcx]; unsigned int
0x180065d0c  mov     rcx, [rcx+8]; unsigned __int8 *
0x180065d10  mov     [rsp+78h+pcbResult], rdi; unsigned __int8 *
0x180065d15  call    ?ApplyPKCS1SigningFormat@@YAJPEBEK0KPEAEKH@Z; ApplyPKCS1SigningFormat(uchar const *,ulong,uchar const *,ulong,uchar *,ulong,int)
0x180065d1a  mov     edi, eax
0x180065d1c  test    eax, eax
0x180065d1e  jns     short loc_180065D27
0x180065d20  mov     edx, 82Dh
0x180065d25  jmp     short loc_180065CDC
0x180065d27  mov     rcx, rbx; void *
0x180065d2a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180065d2f  lea     rcx, [rbp+phAlgorithm]
0x180065d33  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180065d38  xor     ebx, ebx
0x180065d3a  jmp     short loc_180065D59
0x180065d3c  mov     ebx, 80090027h
0x180065d41  mov     edx, 7EEh; void *
0x180065d46  mov     r9d, ebx; char *
0x180065d49  mov     rcx, [rbp+30h]; this
0x180065d4d  lea     r8, aOnecoreBaseNgs_14; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180065d54  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180065d59  lea     rcx, [rbp+var_20]; this
0x180065d5d  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x180065d62  mov     eax, ebx
0x180065d64  add     rsp, 78h
0x180065d68  pop     r15
0x180065d6a  pop     r14
0x180065d6c  pop     rdi
0x180065d6d  pop     rsi
0x180065d6e  pop     rbx
0x180065d6f  pop     rbp
0x180065d70  retn
```
