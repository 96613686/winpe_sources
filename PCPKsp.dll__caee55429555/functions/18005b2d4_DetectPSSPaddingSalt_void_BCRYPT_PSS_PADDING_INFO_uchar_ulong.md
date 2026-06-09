# DetectPSSPaddingSalt(void *,_BCRYPT_PSS_PADDING_INFO *,uchar *,ulong)

- ea: `0x18005b2d4`
- end: `0x18005b653`
- name: `?DetectPSSPaddingSalt@@YAJPEAXPEAU_BCRYPT_PSS_PADDING_INFO@@PEAEK@Z`
- size: `895`
- prototype: `__int64 __fastcall(BCRYPT_KEY_HANDLE hKey, struct _BCRYPT_PSS_PADDING_INFO *, unsigned __int8 *, unsigned int)`
- caller_count: `3`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x18002e900`
- `0x18008c15c`
- `0x18008cb50`

## callees

- `0x1800133c4`
- `0x180014a60`
- `0x1800157c0`
- `0x180028cd8`
- `0x180029a20`
- `0x18005b2d4`
- `0x180061bac`
- `0x180063c98`
- `0x1800768a0`
- `0x18007bdbc`

## import_xrefs

- `bcrypt!BCryptGetProperty` at `0x18005b369`
- `bcrypt!BCryptGetProperty` at `0x18005b3bc`
- `bcrypt!BCryptGetProperty` at `0x18005b369`
- `bcrypt!BCryptGetProperty` at `0x18005b3bc`
- `bcrypt!BCryptEncrypt` at `0x18005b408`
- `bcrypt!BCryptEncrypt` at `0x18005b46e`
- `bcrypt!BCryptEncrypt` at `0x18005b408`
- `bcrypt!BCryptEncrypt` at `0x18005b46e`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18005b329`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18005b329`

## pseudocode

```c
__int64 __fastcall DetectPSSPaddingSalt(
        BCRYPT_KEY_HANDLE hKey,
        struct _BCRYPT_PSS_PADDING_INFO *a2,
        unsigned __int8 *a3,
        ULONG a4)
{
  const WCHAR *pszAlgId; // rdx
  NTSTATUS Property; // eax
  __int64 v10; // rdx
  unsigned int v11; // ebx
  PUCHAR v12; // rbx
  NTSTATUS v13; // eax
  const struct std::nothrow_t *v14; // rdx
  int v15; // edi
  const struct std::nothrow_t *v16; // rdx
  unsigned int v17; // esi
  const struct std::nothrow_t *v18; // rdx
  PUCHAR v19; // rdi
  int v20; // eax
  const struct std::nothrow_t *v21; // rdx
  unsigned int v22; // r14d
  const struct std::nothrow_t *v23; // rdx
  ULONG v24; // r9d
  unsigned int i; // r8d
  char v26; // cl
  int pcbResult; // [rsp+20h] [rbp-39h]
  int pcbResulta; // [rsp+20h] [rbp-39h]
  int pcbResultb; // [rsp+20h] [rbp-39h]
  UCHAR pbOutput[4]; // [rsp+50h] [rbp-9h] BYREF
  ULONG v32; // [rsp+54h] [rbp-5h] BYREF
  UCHAR v33[4]; // [rsp+58h] [rbp-1h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+60h] [rbp+7h] BYREF
  PUCHAR v35; // [rsp+68h] [rbp+Fh] BYREF
  int *v36[4]; // [rsp+70h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]
  ULONG cbOutput; // [rsp+C8h] [rbp+6Fh] BYREF

  KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)v36, L"DetectPSSPaddingSalt", 1);
  pszAlgId = a2->pszAlgId;
  v32 = 0;
  phAlgorithm = 0;
  Property = BCryptOpenAlgorithmProvider(&phAlgorithm, pszAlgId, 0, 0);
  if ( Property < 0 )
  {
    v10 = 2199;
LABEL_5:
    v11 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)v10,
            (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmhelpers20.cpp",
            (const char *)(unsigned int)Property,
            pcbResult);
LABEL_36:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
    KspFunctionLogger::~KspFunctionLogger(v36);
    return v11;
  }
  *(_DWORD *)pbOutput = 0;
  Property = BCryptGetProperty(phAlgorithm, L"HashDigestLength", pbOutput, 4u, &v32, 0);
  if ( Property < 0 )
  {
    v10 = 2207;
    goto LABEL_5;
  }
  *(_DWORD *)v33 = 0;
  Property = BCryptGetProperty(phAlgorithm, L"ObjectLength", v33, 4u, &v32, 0);
  if ( Property < 0 )
  {
    v10 = 2215;
    goto LABEL_5;
  }
  cbOutput = 0;
  Property = BCryptEncrypt(hKey, a3, a4, 0, 0, 0, 0, 0, &cbOutput, 1u);
  if ( Property < 0 )
  {
    v10 = 2228;
    goto LABEL_5;
  }
  wil::make_unique_nothrow<unsigned char [0]>(&v35, cbOutput);
  v12 = v35;
  if ( !v35 )
    goto LABEL_46;
  v13 = BCryptEncrypt(hKey, a3, a4, 0, 0, 0, v35, cbOutput, &cbOutput, 1u);
  if ( v13 < 0 )
  {
    v15 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)0x8BF,
            (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmhelpers20.cpp",
            (const char *)(unsigned int)v13,
            pcbResulta);
    if ( v12 )
      operator delete(v12, v14);
    v11 = v15;
    goto LABEL_36;
  }
  if ( v12[cbOutput - 1] != 0xBC )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8C3,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmhelpers20.cpp",
      (const char *)0x80090005LL,
      pcbResulta);
LABEL_33:
    if ( v12 )
      operator delete(v12, v16);
    v11 = -2146893819;
    goto LABEL_36;
  }
  v17 = cbOutput - *(_DWORD *)pbOutput - 1;
  wil::make_unique_nothrow<unsigned char [0]>(&v35, v17);
  v19 = v35;
  if ( !v35 )
  {
    if ( v12 )
      operator delete(v12, v18);
LABEL_46:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
    KspFunctionLogger::~KspFunctionLogger(v36);
    return 2147942408LL;
  }
  v20 = MaskGeneration(
          phAlgorithm,
          *(unsigned int *)pbOutput,
          *(unsigned int *)v33,
          &v12[v17],
          *(unsigned int *)pbOutput,
          v35,
          v17);
  v22 = v20;
  if ( v20 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8D2,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmhelpers20.cpp",
      (const char *)(unsigned int)v20,
      pcbResultb);
    if ( v19 )
      operator delete(v19, v23);
    if ( v12 )
      operator delete(v12, v23);
    v11 = v22;
    goto LABEL_36;
  }
  v24 = v17;
  for ( i = 0; i < v17; ++i )
  {
    --v24;
    v21 = (const struct std::nothrow_t *)(unsigned __int8)(v12[i] ^ v19[i]);
    v26 = (v12[i] ^ v19[i]) & 0x7F;
    if ( i )
      v26 = v12[i] ^ v19[i];
    if ( v26 == 1 )
      break;
    if ( v26 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8E7,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmhelpers20.cpp",
        (const char *)0x80090005LL,
        pcbResultb);
      if ( v19 )
        operator delete(v19, v16);
      goto LABEL_33;
    }
  }
  a2->cbSalt = v24;
  if ( v19 )
    operator delete(v19, v21);
  if ( v12 )
    operator delete(v12, v21);
  if ( phAlgorithm )
    wil::details::BCryptCloseAlgorithmProviderNoFlags((wil::details *)phAlgorithm, v21);
  KspFunctionLogger::~KspFunctionLogger(v36);
  return 0;
}

```

## disassembly

```asm
0x18005b2d4  mov     [rsp-8+arg_0], rbx
0x18005b2d9  mov     [rsp-8+arg_10], rsi
0x18005b2de  push    rbp
0x18005b2df  push    rdi
0x18005b2e0  push    r12
0x18005b2e2  push    r14
0x18005b2e4  push    r15
0x18005b2e6  lea     rbp, [rsp-37h]
0x18005b2eb  sub     rsp, 90h
0x18005b2f2  mov     rsi, r8
0x18005b2f5  mov     r15, rdx
0x18005b2f8  mov     r14, rcx
0x18005b2fb  lea     rdx, aDetectpsspaddi; "DetectPSSPaddingSalt"
0x18005b302  mov     r8b, 1; bool
0x18005b305  lea     rcx, [rbp+57h+var_40]; this
0x18005b309  mov     edi, r9d
0x18005b30c  call    ??0KspFunctionLogger@@QEAA@QEBG_N@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,bool)
0x18005b311  mov     rdx, [r15]; pszAlgId
0x18005b314  lea     rcx, [rbp+57h+phAlgorithm]; phAlgorithm
0x18005b318  xor     r12d, r12d
0x18005b31b  xor     r9d, r9d; dwFlags
0x18005b31e  xor     r8d, r8d; pszImplementation
0x18005b321  mov     [rbp+57h+var_5C], r12d
0x18005b325  mov     [rbp+57h+phAlgorithm], r12
0x18005b329  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18005b330  nop     dword ptr [rax+rax+00h]
0x18005b335  test    eax, eax
0x18005b337  jns     short loc_18005B340
0x18005b339  mov     edx, 897h
0x18005b33e  jmp     short loc_18005B37E
0x18005b340  mov     rcx, [rbp+57h+phAlgorithm]; hObject
0x18005b344  lea     rax, [rbp+57h+var_5C]
0x18005b348  mov     ebx, 4
0x18005b34d  mov     [rsp+0B0h+dwFlags], r12d; dwFlags
0x18005b352  mov     r9d, ebx; cbOutput
0x18005b355  mov     dword ptr [rbp+57h+pbOutput], r12d
0x18005b359  lea     r8, [rbp+57h+pbOutput]; pbOutput
0x18005b35d  mov     [rsp+0B0h+pcbResult], rax; int
0x18005b362  lea     rdx, aHashdigestleng; "HashDigestLength"
0x18005b369  call    cs:__imp_BCryptGetProperty
0x18005b370  nop     dword ptr [rax+rax+00h]
0x18005b375  test    eax, eax
0x18005b377  jns     short loc_18005B398
0x18005b379  mov     edx, 89Fh; void *
0x18005b37e  mov     rcx, [rbp+5Fh]; this
0x18005b382  lea     r8, aOnecoreBaseNgs_14; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18005b389  mov     r9d, eax; char *
0x18005b38c  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18005b391  mov     ebx, eax
0x18005b393  jmp     loc_18005B5C3
0x18005b398  mov     rcx, [rbp+57h+phAlgorithm]; hObject
0x18005b39c  lea     rax, [rbp+57h+var_5C]
0x18005b3a0  mov     [rsp+0B0h+dwFlags], r12d; dwFlags
0x18005b3a5  lea     r8, [rbp+57h+var_58]; pbOutput
0x18005b3a9  mov     r9d, ebx; cbOutput
0x18005b3ac  mov     [rsp+0B0h+pcbResult], rax; pcbResult
0x18005b3b1  lea     rdx, aObjectlength; "ObjectLength"
0x18005b3b8  mov     dword ptr [rbp+57h+var_58], r12d
0x18005b3bc  call    cs:__imp_BCryptGetProperty
0x18005b3c3  nop     dword ptr [rax+rax+00h]
0x18005b3c8  test    eax, eax
0x18005b3ca  jns     short loc_18005B3D3
0x18005b3cc  mov     edx, 8A7h
0x18005b3d1  jmp     short loc_18005B37E
0x18005b3d3  mov     [rsp+0B0h+var_68], 1; dwFlags
0x18005b3db  lea     rax, [rbp+57h+arg_8]
0x18005b3df  mov     [rsp+0B0h+var_70], rax; pcbResult
0x18005b3e4  xor     r9d, r9d; pPaddingInfo
0x18005b3e7  mov     [rsp+0B0h+cbOutput], r12d; cbOutput
0x18005b3ec  mov     r8d, edi; cbInput
0x18005b3ef  mov     [rsp+0B0h+var_80], r12; pbOutput
0x18005b3f4  mov     rdx, rsi; pbInput
0x18005b3f7  mov     [rsp+0B0h+dwFlags], r12d; cbIV
0x18005b3fc  mov     rcx, r14; hKey
0x18005b3ff  mov     [rsp+0B0h+pcbResult], r12; pbIV
0x18005b404  mov     [rbp+57h+arg_8], r12d
0x18005b408  call    cs:__imp_BCryptEncrypt
0x18005b40f  nop     dword ptr [rax+rax+00h]
0x18005b414  test    eax, eax
0x18005b416  jns     short loc_18005B422
0x18005b418  mov     edx, 8B4h
0x18005b41d  jmp     loc_18005B37E
0x18005b422  mov     edx, [rbp+57h+arg_8]
0x18005b425  lea     rcx, [rbp+57h+var_48]
0x18005b429  call    ??$make_unique_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<uchar [0]>(unsigned __int64)
0x18005b42e  mov     rbx, [rbp+57h+var_48]
0x18005b432  test    rbx, rbx
0x18005b435  jz      loc_18005B61F
0x18005b43b  mov     eax, [rbp+57h+arg_8]
0x18005b43e  lea     rcx, [rbp+57h+arg_8]
0x18005b442  mov     [rsp+0B0h+var_68], 1; dwFlags
0x18005b44a  xor     r9d, r9d; pPaddingInfo
0x18005b44d  mov     [rsp+0B0h+var_70], rcx; pcbResult
0x18005b452  mov     r8d, edi; cbInput
0x18005b455  mov     [rsp+0B0h+cbOutput], eax; cbOutput
0x18005b459  mov     rdx, rsi; pbInput
0x18005b45c  mov     [rsp+0B0h+var_80], rbx; pbOutput
0x18005b461  mov     rcx, r14; hKey
0x18005b464  mov     [rsp+0B0h+dwFlags], r12d; cbIV
0x18005b469  mov     [rsp+0B0h+pcbResult], r12; int
0x18005b46e  call    cs:__imp_BCryptEncrypt
0x18005b475  nop     dword ptr [rax+rax+00h]
0x18005b47a  test    eax, eax
0x18005b47c  jns     short loc_18005B4AC
0x18005b47e  mov     rcx, [rbp+5Fh]; this
0x18005b482  lea     r8, aOnecoreBaseNgs_14; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18005b489  mov     r9d, eax; char *
0x18005b48c  mov     edx, 8BFh; void *
0x18005b491  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18005b496  mov     edi, eax
0x18005b498  test    rbx, rbx
0x18005b49b  jz      short loc_18005B4A5
0x18005b49d  mov     rcx, rbx; void *
0x18005b4a0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18005b4a5  mov     ebx, edi
0x18005b4a7  jmp     loc_18005B5C3
0x18005b4ac  mov     esi, [rbp+57h+arg_8]
0x18005b4af  lea     eax, [rsi-1]
0x18005b4b2  cmp     byte ptr [rax+rbx], 0BCh
0x18005b4b6  jz      short loc_18005B4D8
0x18005b4b8  mov     rcx, [rbp+5Fh]; this
0x18005b4bc  lea     r8, aOnecoreBaseNgs_14; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18005b4c3  mov     r9d, 80090005h; char *
0x18005b4c9  mov     edx, 8C3h; void *
0x18005b4ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005b4d3  jmp     loc_18005B5B1
0x18005b4d8  sub     esi, dword ptr [rbp+57h+pbOutput]
0x18005b4db  lea     rcx, [rbp+57h+var_48]
0x18005b4df  dec     esi
0x18005b4e1  mov     edx, esi
0x18005b4e3  call    ??$make_unique_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<uchar [0]>(unsigned __int64)
0x18005b4e8  mov     rdi, [rbp+57h+var_48]
0x18005b4ec  test    rdi, rdi
0x18005b4ef  jz      loc_18005B612
0x18005b4f5  mov     edx, dword ptr [rbp+57h+pbOutput]; unsigned int
0x18005b4f8  lea     r9, [rsi+rbx]; unsigned __int8 *
0x18005b4fc  mov     r8d, dword ptr [rbp+57h+var_58]; unsigned int
0x18005b500  mov     rcx, [rbp+57h+phAlgorithm]; void *
0x18005b504  mov     dword ptr [rsp+0B0h+var_80], esi; unsigned int
0x18005b508  mov     qword ptr [rsp+0B0h+dwFlags], rdi; unsigned __int8 *
0x18005b50d  mov     dword ptr [rsp+0B0h+pcbResult], edx; int
0x18005b511  call    ?MaskGeneration@@YAJPEAXKKPEAEK1K@Z; MaskGeneration(void *,ulong,ulong,uchar *,ulong,uchar *,ulong)
0x18005b516  mov     r14d, eax
0x18005b519  test    eax, eax
0x18005b51b  jns     short loc_18005B554
0x18005b51d  mov     rcx, [rbp+5Fh]; this
0x18005b521  lea     r8, aOnecoreBaseNgs_14; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18005b528  mov     r9d, eax; char *
0x18005b52b  mov     edx, 8D2h; void *
0x18005b530  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005b535  test    rdi, rdi
0x18005b538  jz      short loc_18005B542
0x18005b53a  mov     rcx, rdi; void *
0x18005b53d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18005b542  test    rbx, rbx
0x18005b545  jz      short loc_18005B54F
0x18005b547  mov     rcx, rbx; void *
0x18005b54a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18005b54f  mov     ebx, r14d
0x18005b552  jmp     short loc_18005B5C3
0x18005b554  mov     r9d, esi
0x18005b557  mov     r8d, r12d
0x18005b55a  cmp     r8d, esi
0x18005b55d  jnb     short loc_18005B5D9
0x18005b55f  mov     eax, r8d
0x18005b562  dec     r9d
0x18005b565  mov     cl, [rax+rdi]
0x18005b568  xor     cl, [rax+rbx]
0x18005b56b  movzx   edx, cl
0x18005b56e  mov     al, dl
0x18005b570  and     al, 7Fh
0x18005b572  test    r8d, r8d
0x18005b575  movzx   ecx, al
0x18005b578  cmovnz  ecx, edx
0x18005b57b  cmp     cl, 1
0x18005b57e  jz      short loc_18005B5D9
0x18005b580  test    cl, cl
0x18005b582  jnz     short loc_18005B589
0x18005b584  inc     r8d
0x18005b587  jmp     short loc_18005B55A
0x18005b589  mov     rcx, [rbp+5Fh]; this
0x18005b58d  lea     r8, aOnecoreBaseNgs_14; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18005b594  mov     r9d, 80090005h; char *
0x18005b59a  mov     edx, 8E7h; void *
0x18005b59f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005b5a4  test    rdi, rdi
0x18005b5a7  jz      short loc_18005B5B1
0x18005b5a9  mov     rcx, rdi; void *
0x18005b5ac  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18005b5b1  test    rbx, rbx
0x18005b5b4  jz      short loc_18005B5BE
0x18005b5b6  mov     rcx, rbx; void *
0x18005b5b9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18005b5be  mov     ebx, 80090005h
0x18005b5c3  lea     rcx, [rbp+57h+phAlgorithm]
0x18005b5c7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18005b5cc  lea     rcx, [rbp+57h+var_40]; this
0x18005b5d0  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x18005b5d5  mov     eax, ebx
0x18005b5d7  jmp     short loc_18005B636
0x18005b5d9  mov     [r15+8], r9d
0x18005b5dd  test    rdi, rdi
0x18005b5e0  jz      short loc_18005B5EA
0x18005b5e2  mov     rcx, rdi; void *
0x18005b5e5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18005b5ea  test    rbx, rbx
0x18005b5ed  jz      short loc_18005B5F7
0x18005b5ef  mov     rcx, rbx; void *
0x18005b5f2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18005b5f7  mov     rcx, [rbp+57h+phAlgorithm]; this
0x18005b5fb  test    rcx, rcx
0x18005b5fe  jz      short loc_18005B605
0x18005b600  call    ?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAXPEAX@Z; wil::details::BCryptCloseAlgorithmProviderNoFlags(void *)
0x18005b605  lea     rcx, [rbp+57h+var_40]; this
0x18005b609  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x18005b60e  xor     eax, eax
0x18005b610  jmp     short loc_18005B636
0x18005b612  test    rbx, rbx
0x18005b615  jz      short loc_18005B61F
0x18005b617  mov     rcx, rbx; void *
0x18005b61a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18005b61f  lea     rcx, [rbp+57h+phAlgorithm]
0x18005b623  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18005b628  lea     rcx, [rbp+57h+var_40]; this
0x18005b62c  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x18005b631  mov     eax, 80070008h
0x18005b636  lea     r11, [rsp+0B0h+var_20]
0x18005b63e  mov     rbx, [r11+30h]
0x18005b642  mov     rsi, [r11+40h]
0x18005b646  mov     rsp, r11
0x18005b649  pop     r15
0x18005b64b  pop     r14
0x18005b64d  pop     r12
0x18005b64f  pop     rdi
0x18005b650  pop     rbp
0x18005b651  retn
```
