# ComputeHash(uchar const *,unsigned __int64,uchar *,ulong)

- ea: `0x180061bd4`
- end: `0x180061f39`
- name: `?ComputeHash@@YAJPEBE_KPEAEK@Z`
- size: `869`
- prototype: `__int64 __fastcall(PUCHAR pbInput, ULONG cbInput, PUCHAR pbOutput, unsigned int)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18001b050`
- `0x180081040`

## callees

- `0x1800133c4`
- `0x180029a20`
- `0x18005305c`
- `0x18005437c`
- `0x180061bac`
- `0x180061bd4`
- `0x180061f40`
- `0x180063c98`
- `0x1800768a0`
- `0x18007bdbc`

## import_xrefs

- `bcrypt!BCryptFinishHash` at `0x180061eab`
- `bcrypt!BCryptFinishHash` at `0x180061eab`
- `bcrypt!BCryptCreateHash` at `0x180061de2`
- `bcrypt!BCryptCreateHash` at `0x180061de2`
- `bcrypt!BCryptGetProperty` at `0x180061cf9`
- `bcrypt!BCryptGetProperty` at `0x180061cf9`
- `bcrypt!BCryptHashData` at `0x180061e46`
- `bcrypt!BCryptHashData` at `0x180061e46`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180061c79`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180061c79`
- `bcrypt!BCryptDestroyHash` at `0x180061c38`
- `bcrypt!BCryptDestroyHash` at `0x180061d9a`
- `bcrypt!BCryptDestroyHash` at `0x180061c38`
- `bcrypt!BCryptDestroyHash` at `0x180061d9a`

## pseudocode

```c
__int64 __fastcall ComputeHash(PUCHAR pbInput, ULONG cbInput, UCHAR *pbOutput, ULONG a4)
{
  NTSTATUS v8; // eax
  unsigned int v9; // ebx
  NTSTATUS Property; // eax
  unsigned int v11; // ebx
  UCHAR *v12; // rbx
  ULONG v13; // r15d
  BCRYPT_HASH_HANDLE v14; // rdi
  NTSTATUS v15; // eax
  const struct std::nothrow_t *v16; // rdx
  unsigned int v17; // edi
  NTSTATUS v18; // eax
  const struct std::nothrow_t *v19; // rdx
  NTSTATUS v20; // eax
  const struct std::nothrow_t *v21; // rdx
  const struct std::nothrow_t *v22; // rdx
  int pcbResult; // [rsp+20h] [rbp-78h]
  int pcbResulta; // [rsp+20h] [rbp-78h]
  int pcbResultb; // [rsp+20h] [rbp-78h]
  ULONG v26; // [rsp+40h] [rbp-58h] BYREF
  BCRYPT_HASH_HANDLE hHash; // [rsp+48h] [rbp-50h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+50h] [rbp-48h] BYREF
  PUCHAR pbHashObject[8]; // [rsp+58h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]
  ULONG pbOutputa; // [rsp+B8h] [rbp+20h] BYREF

  pbOutputa = a4;
  phAlgorithm = 0;
  hHash = 0;
  v26 = 0;
  if ( !pbInput )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x204,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\uihelper.cpp",
      (const char *)0x80090027LL,
      pcbResult);
    return 2148073511LL;
  }
  *(_OWORD *)pbOutput = 0;
  *((_DWORD *)pbOutput + 4) = 0;
  v8 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA1", 0, 0);
  if ( v8 < 0 )
  {
    v9 = wil::details::in1diag3::Return_NtStatus(
           retaddr,
           (void *)0x20C,
           (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\uihelper.cpp",
           (const char *)(unsigned int)v8,
           pcbResult);
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hHash);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
    return v9;
  }
  pbOutputa = 0;
  Property = BCryptGetProperty(phAlgorithm, L"ObjectLength", (PUCHAR)&pbOutputa, 4u, &v26, 0);
  if ( Property < 0 )
  {
    v11 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)0x214,
            (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\uihelper.cpp",
            (const char *)(unsigned int)Property,
            pcbResulta);
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hHash);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
    return v11;
  }
  wil::make_unique_nothrow<unsigned char [0]>(pbHashObject, pbOutputa);
  v12 = pbHashObject[0];
  if ( !pbHashObject[0] )
  {
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hHash);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
    return 2147942408LL;
  }
  v13 = pbOutputa;
  v14 = hHash;
  if ( hHash )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)pbHashObject);
    BCryptDestroyHash(v14);
    wil::last_error_context::~last_error_context((wil::last_error_context *)pbHashObject);
  }
  hHash = 0;
  v15 = BCryptCreateHash(phAlgorithm, &hHash, v12, v13, 0, 0, 0);
  if ( v15 < 0 )
  {
    v17 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)0x21E,
            (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\uihelper.cpp",
            (const char *)(unsigned int)v15,
            pcbResultb);
    if ( v12 )
      operator delete(v12, v16);
LABEL_22:
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hHash);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
    return v17;
  }
  v18 = BCryptHashData(hHash, pbInput, cbInput, 0);
  if ( v18 < 0 )
  {
    v17 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)0x223,
            (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\uihelper.cpp",
            (const char *)(unsigned int)v18,
            pcbResultb);
    if ( v12 )
      operator delete(v12, v19);
    goto LABEL_22;
  }
  v20 = BCryptFinishHash(hHash, pbOutput, 0x14u, 0);
  if ( v20 < 0 )
  {
    v17 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)0x228,
            (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\uihelper.cpp",
            (const char *)(unsigned int)v20,
            pcbResultb);
    if ( v12 )
      operator delete(v12, v22);
    goto LABEL_22;
  }
  if ( v12 )
    operator delete(v12, v21);
  wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hHash);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
  return 0;
}

```

## disassembly

```asm
0x180061bd4  mov     rax, rsp
0x180061bd7  mov     [rax+20h], r9d
0x180061bdb  push    rbx
0x180061bdc  push    rsi
0x180061bdd  push    rdi
0x180061bde  push    r12
0x180061be0  push    r14
0x180061be2  push    r15
0x180061be4  sub     rsp, 68h
0x180061be8  mov     r14, r8
0x180061beb  mov     r12, rdx
0x180061bee  mov     rsi, rcx
0x180061bf1  mov     qword ptr [rax-48h], 0
0x180061bf9  mov     qword ptr [rax-50h], 0
0x180061c01  mov     dword ptr [rax-58h], 0
0x180061c08  test    rcx, rcx
0x180061c0b  jnz     short loc_180061C5A
0x180061c0d  mov     rcx, [rsp+98h]; this
0x180061c15  mov     ebx, 80090027h
0x180061c1a  mov     r9d, ebx; char *
0x180061c1d  lea     r8, aOnecoreBaseNgs_26; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180061c24  mov     edx, 204h; void *
0x180061c29  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180061c2e  mov     rcx, [rsp+98h+hHash]; hHash
0x180061c33  test    rcx, rcx
0x180061c36  jz      short loc_180061C44
0x180061c38  call    cs:__imp_BCryptDestroyHash
0x180061c3f  nop     dword ptr [rax+rax+00h]
0x180061c44  mov     rcx, [rsp+98h+phAlgorithm]; this
0x180061c49  test    rcx, rcx
0x180061c4c  jz      short loc_180061C53
0x180061c4e  call    ?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAXPEAX@Z; wil::details::BCryptCloseAlgorithmProviderNoFlags(void *)
0x180061c53  mov     eax, ebx
0x180061c55  jmp     loc_180061F2A
0x180061c5a  xorps   xmm0, xmm0
0x180061c5d  xor     eax, eax
0x180061c5f  movups  xmmword ptr [r8], xmm0
0x180061c63  mov     [r8+10h], eax
0x180061c67  xor     r9d, r9d; dwFlags
0x180061c6a  xor     r8d, r8d; pszImplementation
0x180061c6d  lea     rdx, aSha1_0; "SHA1"
0x180061c74  lea     rcx, [rsp+98h+phAlgorithm]; phAlgorithm
0x180061c79  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180061c80  nop     dword ptr [rax+rax+00h]
0x180061c85  test    eax, eax
0x180061c87  jns     short loc_180061CC2
0x180061c89  mov     rcx, [rsp+98h]; this
0x180061c91  mov     r9d, eax; char *
0x180061c94  lea     r8, aOnecoreBaseNgs_26; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180061c9b  mov     edx, 20Ch; void *
0x180061ca0  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180061ca5  mov     ebx, eax
0x180061ca7  lea     rcx, [rsp+98h+hHash]
0x180061cac  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180061cb1  lea     rcx, [rsp+98h+phAlgorithm]
0x180061cb6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180061cbb  mov     eax, ebx
0x180061cbd  jmp     loc_180061F2A
0x180061cc2  mov     [rsp+98h+pbOutput], 0
0x180061ccd  mov     [rsp+98h+dwFlags], 0; dwFlags
0x180061cd5  lea     rax, [rsp+98h+var_58]
0x180061cda  mov     [rsp+98h+pcbResult], rax; int
0x180061cdf  mov     r9d, 4; cbOutput
0x180061ce5  lea     r8, [rsp+98h+pbOutput]; pbOutput
0x180061ced  lea     rdx, aObjectlength; "ObjectLength"
0x180061cf4  mov     rcx, [rsp+98h+phAlgorithm]; hObject
0x180061cf9  call    cs:__imp_BCryptGetProperty
0x180061d00  nop     dword ptr [rax+rax+00h]
0x180061d05  test    eax, eax
0x180061d07  jns     short loc_180061D42
0x180061d09  mov     rcx, [rsp+98h]; this
0x180061d11  mov     r9d, eax; char *
0x180061d14  lea     r8, aOnecoreBaseNgs_26; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180061d1b  mov     edx, 214h; void *
0x180061d20  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180061d25  mov     ebx, eax
0x180061d27  lea     rcx, [rsp+98h+hHash]
0x180061d2c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180061d31  lea     rcx, [rsp+98h+phAlgorithm]
0x180061d36  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180061d3b  mov     eax, ebx
0x180061d3d  jmp     loc_180061F2A
0x180061d42  mov     edx, [rsp+98h+pbOutput]
0x180061d49  lea     rcx, [rsp+98h+pbHashObject]
0x180061d4e  call    ??$make_unique_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<uchar [0]>(unsigned __int64)
0x180061d53  mov     rbx, [rsp+98h+pbHashObject]
0x180061d58  test    rbx, rbx
0x180061d5b  jnz     short loc_180061D7B
0x180061d5d  lea     rcx, [rsp+98h+hHash]
0x180061d62  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180061d67  lea     rcx, [rsp+98h+phAlgorithm]
0x180061d6c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180061d71  mov     eax, 80070008h
0x180061d76  jmp     loc_180061F2A
0x180061d7b  mov     r15d, [rsp+98h+pbOutput]
0x180061d83  mov     rdi, [rsp+98h+hHash]
0x180061d88  test    rdi, rdi
0x180061d8b  jz      short loc_180061DB0
0x180061d8d  lea     rcx, [rsp+98h+pbHashObject]; this
0x180061d92  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180061d97  mov     rcx, rdi; hHash
0x180061d9a  call    cs:__imp_BCryptDestroyHash
0x180061da1  nop     dword ptr [rax+rax+00h]
0x180061da6  lea     rcx, [rsp+98h+pbHashObject]; this
0x180061dab  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180061db0  mov     [rsp+98h+hHash], 0
0x180061db9  mov     [rsp+98h+var_68], 0; dwFlags
0x180061dc1  mov     [rsp+98h+dwFlags], 0; cbSecret
0x180061dc9  mov     [rsp+98h+pcbResult], 0; int
0x180061dd2  mov     r9d, r15d; cbHashObject
0x180061dd5  mov     r8, rbx; pbHashObject
0x180061dd8  lea     rdx, [rsp+98h+hHash]; phHash
0x180061ddd  mov     rcx, [rsp+98h+phAlgorithm]; hAlgorithm
0x180061de2  call    cs:__imp_BCryptCreateHash
0x180061de9  nop     dword ptr [rax+rax+00h]
0x180061dee  test    eax, eax
0x180061df0  jns     short loc_180061E38
0x180061df2  mov     rcx, [rsp+98h]; this
0x180061dfa  mov     r9d, eax; char *
0x180061dfd  lea     r8, aOnecoreBaseNgs_26; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180061e04  mov     edx, 21Eh; void *
0x180061e09  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180061e0e  mov     edi, eax
0x180061e10  test    rbx, rbx
0x180061e13  jz      short loc_180061E1D
0x180061e15  mov     rcx, rbx; void *
0x180061e18  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180061e1d  lea     rcx, [rsp+98h+hHash]
0x180061e22  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180061e27  lea     rcx, [rsp+98h+phAlgorithm]
0x180061e2c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180061e31  mov     eax, edi
0x180061e33  jmp     loc_180061F2A
0x180061e38  mov     r8d, r12d; cbInput
0x180061e3b  xor     r9d, r9d; dwFlags
0x180061e3e  mov     rdx, rsi; pbInput
0x180061e41  mov     rcx, [rsp+98h+hHash]; hHash
0x180061e46  call    cs:__imp_BCryptHashData
0x180061e4d  nop     dword ptr [rax+rax+00h]
0x180061e52  test    eax, eax
0x180061e54  jns     short loc_180061E9C
0x180061e56  mov     rcx, [rsp+98h]; this
0x180061e5e  mov     r9d, eax; char *
0x180061e61  lea     r8, aOnecoreBaseNgs_26; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180061e68  mov     edx, 223h; void *
0x180061e6d  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180061e72  mov     edi, eax
0x180061e74  test    rbx, rbx
0x180061e77  jz      short loc_180061E81
0x180061e79  mov     rcx, rbx; void *
0x180061e7c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180061e81  lea     rcx, [rsp+98h+hHash]
0x180061e86  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180061e8b  lea     rcx, [rsp+98h+phAlgorithm]
0x180061e90  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180061e95  mov     eax, edi
0x180061e97  jmp     loc_180061F2A
0x180061e9c  xor     r9d, r9d; dwFlags
0x180061e9f  lea     r8d, [r9+14h]; cbOutput
0x180061ea3  mov     rdx, r14; pbOutput
0x180061ea6  mov     rcx, [rsp+98h+hHash]; hHash
0x180061eab  call    cs:__imp_BCryptFinishHash
0x180061eb2  nop     dword ptr [rax+rax+00h]
0x180061eb7  test    eax, eax
0x180061eb9  jns     short loc_180061EFE
0x180061ebb  mov     rcx, [rsp+98h]; this
0x180061ec3  mov     r9d, eax; char *
0x180061ec6  lea     r8, aOnecoreBaseNgs_26; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180061ecd  mov     edx, 228h; void *
0x180061ed2  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180061ed7  mov     edi, eax
0x180061ed9  test    rbx, rbx
0x180061edc  jz      short loc_180061EE6
0x180061ede  mov     rcx, rbx; void *
0x180061ee1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180061ee6  lea     rcx, [rsp+98h+hHash]
0x180061eeb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180061ef0  lea     rcx, [rsp+98h+phAlgorithm]
0x180061ef5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180061efa  mov     eax, edi
0x180061efc  jmp     short loc_180061F2A
0x180061efe  test    rbx, rbx
0x180061f01  jz      short loc_180061F0B
0x180061f03  mov     rcx, rbx; void *
0x180061f06  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180061f0b  lea     rcx, [rsp+98h+hHash]
0x180061f10  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180061f15  lea     rcx, [rsp+98h+phAlgorithm]
0x180061f1a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180061f1f  xor     eax, eax
0x180061f21  jmp     short loc_180061F2A
0x180061f23  mov     eax, [rsp+98h+pbOutput]
0x180061f2a  add     rsp, 68h
0x180061f2e  pop     r15
0x180061f30  pop     r14
0x180061f32  pop     r12
0x180061f34  pop     rdi
0x180061f35  pop     rsi
0x180061f36  pop     rbx
0x180061f37  retn
```
