# ComputeHash(uchar *,unsigned __int64,uchar *,unsigned __int64,uchar *,unsigned __int64,unsigned __int64 *)

- ea: `0x140058a2c`
- end: `0x140058ca3`
- name: `?ComputeHash@@YAJPEAE_K0101PEA_K@Z`
- size: `631`
- prototype: `__int64 __fastcall(PUCHAR pbInput, __int64, unsigned __int8 *, __int64, unsigned __int8 *, unsigned __int64 pbOutput, unsigned __int64 *)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14000e9e0`
- `0x140010270`
- `0x140063f10`

## callees

- `0x14000a420`
- `0x14002b430`
- `0x140058624`
- `0x1400589a0`
- `0x1400589e8`
- `0x140058a2c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140058b7f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140058c7b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140058b7f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140058c7b`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x140058a61`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x140058a61`
- `bcrypt!BCryptGetProperty` at `0x140058aaa`
- `bcrypt!BCryptGetProperty` at `0x140058b25`
- `bcrypt!BCryptGetProperty` at `0x140058aaa`
- `bcrypt!BCryptGetProperty` at `0x140058b25`
- `bcrypt!BCryptCreateHash` at `0x140058baf`
- `bcrypt!BCryptCreateHash` at `0x140058baf`
- `bcrypt!BCryptHashData` at `0x140058bf2`
- `bcrypt!BCryptHashData` at `0x140058c1b`
- `bcrypt!BCryptHashData` at `0x140058bf2`
- `bcrypt!BCryptHashData` at `0x140058c1b`
- `bcrypt!BCryptFinishHash` at `0x140058c41`
- `bcrypt!BCryptFinishHash` at `0x140058c41`

## string_xrefs

- `0x140058abf`: `onecore\ds\security\biometrics\service\trustlet\exe\crypto.cpp`
- `0x140058aec`: `onecore\ds\security\biometrics\service\trustlet\exe\crypto.cpp`
- `0x140058b5d`: `onecore\ds\security\biometrics\service\trustlet\exe\crypto.cpp`
- `0x140058bc4`: `onecore\ds\security\biometrics\service\trustlet\exe\crypto.cpp`

## pseudocode

```c
__int64 __fastcall ComputeHash(
        PUCHAR pbInput,
        __int64 a2,
        unsigned __int8 *a3,
        __int64 a4,
        unsigned __int8 *a5,
        unsigned __int64 pbOutput,
        unsigned __int64 *a7)
{
  NTSTATUS v10; // eax
  unsigned int v11; // ebx
  __int64 v12; // r9
  __int64 v13; // rdx
  NTSTATUS Property; // eax
  __int64 v15; // rdx
  HLOCAL v16; // rcx
  NTSTATUS v17; // eax
  __int64 v18; // rdx
  HLOCAL v19; // rcx
  int pcbResult; // [rsp+20h] [rbp-48h]
  int pcbResulta; // [rsp+20h] [rbp-48h]
  ULONG v23; // [rsp+40h] [rbp-28h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-20h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+50h] [rbp-18h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm[2]; // [rsp+58h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+30h]
  __int64 v28; // [rsp+A8h] [rbp+40h] BYREF

  v28 = a2;
  phAlgorithm[0] = 0;
  v10 = BCryptOpenAlgorithmProvider(phAlgorithm, L"SHA256", 0, 0);
  v11 = v10;
  if ( v10 < 0 )
  {
    v12 = (unsigned int)v10;
    v13 = 295;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\crypto.cpp",
      (const char *)v12,
      pcbResult);
    goto LABEL_28;
  }
  LODWORD(pbOutput) = 0;
  v23 = 0;
  Property = BCryptGetProperty(phAlgorithm[0], L"HashDigestLength", (PUCHAR)&pbOutput, 4u, &v23, 0);
  if ( Property < 0 )
  {
    v15 = 307;
LABEL_5:
    v11 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)v15,
            (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\crypto.cpp",
            (const char *)(unsigned int)Property,
            pcbResult);
    goto LABEL_28;
  }
  if ( (unsigned int)pbOutput < 0x20 )
  {
    v11 = -2147024809;
    v12 = 2147942487LL;
    v13 = 310;
    goto LABEL_8;
  }
  LODWORD(v28) = 0;
  Property = BCryptGetProperty(phAlgorithm[0], L"ObjectLength", (PUCHAR)&v28, 4u, &v23, 0);
  if ( Property < 0 )
  {
    v15 = 320;
    goto LABEL_5;
  }
  wil::make_unique_hlocal<unsigned char [0]>(&hMem, (unsigned int)v28);
  if ( !hMem )
  {
    v11 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x145,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\crypto.cpp",
      (const char *)0x8007000ELL,
      pcbResult);
    goto LABEL_13;
  }
  phHash = 0;
  v17 = BCryptCreateHash(phAlgorithm[0], &phHash, (PUCHAR)hMem, v28, 0, 0, 0);
  if ( v17 < 0 )
  {
    v18 = 336;
LABEL_17:
    v11 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)v18,
            (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\crypto.cpp",
            (const char *)(unsigned int)v17,
            pcbResulta);
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phHash);
LABEL_13:
    v16 = hMem;
    hMem = 0;
    if ( v16 )
      LocalFree(v16);
    goto LABEL_28;
  }
  v17 = BCryptHashData(phHash, pbInput, 0x78u, 0);
  if ( v17 < 0 )
  {
    v18 = 343;
    goto LABEL_17;
  }
  if ( a4 )
  {
    v17 = BCryptHashData(phHash, a3, a4, 0);
    if ( v17 < 0 )
    {
      v18 = 352;
      goto LABEL_17;
    }
  }
  v17 = BCryptFinishHash(phHash, a5, 0x20u, 0);
  if ( v17 < 0 )
  {
    v18 = 360;
    goto LABEL_17;
  }
  *a7 = (unsigned int)pbOutput;
  wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phHash);
  v19 = hMem;
  hMem = 0;
  if ( v19 )
    LocalFree(v19);
  v11 = 0;
LABEL_28:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(phAlgorithm);
  return v11;
}

```

## disassembly

```asm
0x140058a2c  mov     [rsp-30h+arg_8], rdx
0x140058a31  push    rbp
0x140058a32  push    rbx
0x140058a33  push    rsi
0x140058a34  push    rdi
0x140058a35  push    r14
0x140058a37  push    r15
0x140058a39  mov     rbp, rsp
0x140058a3c  sub     rsp, 68h
0x140058a40  mov     rdi, r9
0x140058a43  mov     r14, r8
0x140058a46  mov     rsi, rcx
0x140058a49  xor     r15d, r15d
0x140058a4c  mov     [rbp+phAlgorithm], r15
0x140058a50  xor     r9d, r9d; dwFlags
0x140058a53  xor     r8d, r8d; pszImplementation
0x140058a56  lea     rdx, pszAlgId; "SHA256"
0x140058a5d  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x140058a61  call    cs:__imp_BCryptOpenAlgorithmProvider
0x140058a68  nop     dword ptr [rax+rax+00h]
0x140058a6d  mov     ebx, eax
0x140058a6f  test    eax, eax
0x140058a71  jns     short loc_140058A7D
0x140058a73  mov     r9d, eax
0x140058a76  mov     edx, 127h
0x140058a7b  jmp     short loc_140058AEC
0x140058a7d  mov     dword ptr [rbp+pbOutput], r15d
0x140058a81  mov     [rbp+var_28], r15d
0x140058a85  mov     [rsp+68h+dwFlags], r15d; dwFlags
0x140058a8a  lea     rax, [rbp+var_28]
0x140058a8e  mov     [rsp+68h+pcbResult], rax; int
0x140058a93  mov     ebx, 4
0x140058a98  mov     r9d, ebx; cbOutput
0x140058a9b  lea     r8, [rbp+pbOutput]; pbOutput
0x140058a9f  lea     rdx, pszProperty; "HashDigestLength"
0x140058aa6  mov     rcx, [rbp+phAlgorithm]; hObject
0x140058aaa  call    cs:__imp_BCryptGetProperty
0x140058ab1  nop     dword ptr [rax+rax+00h]
0x140058ab6  test    eax, eax
0x140058ab8  jns     short loc_140058AD9
0x140058aba  mov     edx, 133h; void *
0x140058abf  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\biometrics\\serv"...
0x140058ac6  mov     r9d, eax; char *
0x140058ac9  mov     rcx, [rbp+30h]; this
0x140058acd  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x140058ad2  mov     ebx, eax
0x140058ad4  jmp     loc_140058C8A
0x140058ad9  cmp     dword ptr [rbp+pbOutput], 20h ; ' '
0x140058add  jnb     short loc_140058B01
0x140058adf  mov     ebx, 80070057h
0x140058ae4  mov     r9d, ebx; char *
0x140058ae7  mov     edx, 136h; void *
0x140058aec  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\biometrics\\serv"...
0x140058af3  mov     rcx, [rbp+30h]; this
0x140058af7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140058afc  jmp     loc_140058C8A
0x140058b01  mov     dword ptr [rbp+arg_8], r15d
0x140058b05  mov     [rsp+68h+dwFlags], r15d; dwFlags
0x140058b0a  lea     rax, [rbp+var_28]
0x140058b0e  mov     [rsp+68h+pcbResult], rax; int
0x140058b13  mov     r9d, ebx; cbOutput
0x140058b16  lea     r8, [rbp+arg_8]; pbOutput
0x140058b1a  lea     rdx, aObjectlength; "ObjectLength"
0x140058b21  mov     rcx, [rbp+phAlgorithm]; hObject
0x140058b25  call    cs:__imp_BCryptGetProperty
0x140058b2c  nop     dword ptr [rax+rax+00h]
0x140058b31  test    eax, eax
0x140058b33  jns     short loc_140058B3C
0x140058b35  mov     edx, 140h
0x140058b3a  jmp     short loc_140058ABF
0x140058b3c  mov     edx, dword ptr [rbp+arg_8]
0x140058b3f  lea     rcx, [rbp+hMem]
0x140058b43  call    ??$make_unique_hlocal@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal<uchar [0]>(unsigned __int64)
0x140058b48  mov     r8, [rbp+hMem]; pbHashObject
0x140058b4c  test    r8, r8
0x140058b4f  jnz     short loc_140058B90
0x140058b51  mov     rcx, [rbp+30h]; this
0x140058b55  mov     ebx, 8007000Eh
0x140058b5a  mov     r9d, ebx; char *
0x140058b5d  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\biometrics\\serv"...
0x140058b64  mov     edx, 145h; void *
0x140058b69  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140058b6e  mov     rcx, [rbp+hMem]; hMem
0x140058b72  mov     [rbp+hMem], r15
0x140058b76  test    rcx, rcx
0x140058b79  jz      loc_140058C8A
0x140058b7f  call    cs:__imp_LocalFree
0x140058b86  nop     dword ptr [rax+rax+00h]
0x140058b8b  jmp     loc_140058C8A
0x140058b90  mov     [rbp+phHash], r15
0x140058b94  mov     [rsp+68h+var_38], r15d; dwFlags
0x140058b99  mov     [rsp+68h+dwFlags], r15d; cbSecret
0x140058b9e  mov     [rsp+68h+pcbResult], r15; int
0x140058ba3  mov     r9d, dword ptr [rbp+arg_8]; cbHashObject
0x140058ba7  lea     rdx, [rbp+phHash]; phHash
0x140058bab  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x140058baf  call    cs:__imp_BCryptCreateHash
0x140058bb6  nop     dword ptr [rax+rax+00h]
0x140058bbb  test    eax, eax
0x140058bbd  jns     short loc_140058BE4
0x140058bbf  mov     edx, 150h; void *
0x140058bc4  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\biometrics\\serv"...
0x140058bcb  mov     r9d, eax; char *
0x140058bce  mov     rcx, [rbp+30h]; this
0x140058bd2  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x140058bd7  mov     ebx, eax
0x140058bd9  lea     rcx, [rbp+phHash]
0x140058bdd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x140058be2  jmp     short loc_140058B6E
0x140058be4  xor     r9d, r9d; dwFlags
0x140058be7  lea     r8d, [r9+78h]; cbInput
0x140058beb  mov     rdx, rsi; pbInput
0x140058bee  mov     rcx, [rbp+phHash]; hHash
0x140058bf2  call    cs:__imp_BCryptHashData
0x140058bf9  nop     dword ptr [rax+rax+00h]
0x140058bfe  test    eax, eax
0x140058c00  jns     short loc_140058C09
0x140058c02  mov     edx, 157h
0x140058c07  jmp     short loc_140058BC4
0x140058c09  test    rdi, rdi
0x140058c0c  jz      short loc_140058C32
0x140058c0e  mov     r8d, edi; cbInput
0x140058c11  xor     r9d, r9d; dwFlags
0x140058c14  mov     rdx, r14; pbInput
0x140058c17  mov     rcx, [rbp+phHash]; hHash
0x140058c1b  call    cs:__imp_BCryptHashData
0x140058c22  nop     dword ptr [rax+rax+00h]
0x140058c27  test    eax, eax
0x140058c29  jns     short loc_140058C32
0x140058c2b  mov     edx, 160h
0x140058c30  jmp     short loc_140058BC4
0x140058c32  xor     r9d, r9d; dwFlags
0x140058c35  lea     r8d, [r9+20h]; cbOutput
0x140058c39  mov     rdx, [rbp+arg_20]; pbOutput
0x140058c3d  mov     rcx, [rbp+phHash]; hHash
0x140058c41  call    cs:__imp_BCryptFinishHash
0x140058c48  nop     dword ptr [rax+rax+00h]
0x140058c4d  test    eax, eax
0x140058c4f  jns     short loc_140058C5B
0x140058c51  mov     edx, 168h
0x140058c56  jmp     loc_140058BC4
0x140058c5b  mov     ecx, dword ptr [rbp+pbOutput]
0x140058c5e  mov     rax, [rbp+arg_30]
0x140058c62  mov     [rax], rcx
0x140058c65  lea     rcx, [rbp+phHash]
0x140058c69  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x140058c6e  mov     rcx, [rbp+hMem]; hMem
0x140058c72  mov     [rbp+hMem], r15
0x140058c76  test    rcx, rcx
0x140058c79  jz      short loc_140058C87
0x140058c7b  call    cs:__imp_LocalFree
0x140058c82  nop     dword ptr [rax+rax+00h]
0x140058c87  mov     ebx, r15d
0x140058c8a  lea     rcx, [rbp+phAlgorithm]
0x140058c8e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140058c93  mov     eax, ebx
0x140058c95  add     rsp, 68h
0x140058c99  pop     r15
0x140058c9b  pop     r14
0x140058c9d  pop     rdi
0x140058c9e  pop     rsi
0x140058c9f  pop     rbx
0x140058ca0  pop     rbp
0x140058ca1  retn
```
