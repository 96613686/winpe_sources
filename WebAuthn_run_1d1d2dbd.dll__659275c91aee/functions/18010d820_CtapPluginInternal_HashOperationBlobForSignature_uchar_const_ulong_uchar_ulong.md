# CtapPluginInternal::HashOperationBlobForSignature(uchar * const,ulong,uchar * *,ulong *)

- ea: `0x18010d820`
- end: `0x18010dbb2`
- name: `?HashOperationBlobForSignature@CtapPluginInternal@@YAJQEAEKPEAPEAEPEAK@Z`
- size: `914`
- prototype: `__int64 __fastcall(PUCHAR pbInput, ULONG cbInput, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180033970`
- `0x180119c80`

## callees

- `0x180022264`
- `0x180036da4`
- `0x18009b620`
- `0x18010c21c`
- `0x18010c27c`
- `0x18010d820`
- `0x18010f008`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18010d9bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18010da25`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18010daa7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18010db22`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18010db38`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18010db7a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18010d9bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18010da25`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18010daa7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18010db22`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18010db38`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18010db7a`
- `bcrypt!BCryptGetProperty` at `0x18010d8e9`
- `bcrypt!BCryptGetProperty` at `0x18010da6e`
- `bcrypt!BCryptGetProperty` at `0x18010d8e9`
- `bcrypt!BCryptGetProperty` at `0x18010da6e`
- `bcrypt!BCryptFinishHash` at `0x18010daea`
- `bcrypt!BCryptFinishHash` at `0x18010daea`
- `bcrypt!BCryptHashData` at `0x18010d9ec`
- `bcrypt!BCryptHashData` at `0x18010d9ec`
- `bcrypt!BCryptCreateHash` at `0x18010d978`
- `bcrypt!BCryptCreateHash` at `0x18010d978`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18010d877`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18010d877`

## string_xrefs

- `0x18010d895`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x18010d901`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x18010d99a`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x18010da04`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x18010da86`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x18010db02`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CtapPluginInternal::HashOperationBlobForSignature(
        PUCHAR pbInput,
        ULONG cbInput,
        PUCHAR *a3,
        unsigned __int8 **a4)
{
  NTSTATUS v8; // eax
  unsigned int v9; // ebx
  __int64 result; // rax
  NTSTATUS Property; // eax
  unsigned int v12; // ebx
  NTSTATUS v13; // ebx
  unsigned int v14; // ebx
  PUCHAR v15; // rcx
  NTSTATUS v16; // eax
  PUCHAR v17; // rcx
  NTSTATUS v18; // eax
  PUCHAR v19; // rcx
  NTSTATUS v20; // eax
  PUCHAR v21; // rcx
  PUCHAR v22; // rcx
  const char *v23; // r9
  PUCHAR v24; // rcx
  int pcbResult; // [rsp+20h] [rbp-A8h]
  int pcbResulta; // [rsp+20h] [rbp-A8h]
  int pcbResultb; // [rsp+20h] [rbp-A8h]
  int pcbResultc; // [rsp+20h] [rbp-A8h]
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+40h] [rbp-88h] BYREF
  PUCHAR pbHashObject; // [rsp+48h] [rbp-80h] BYREF
  BCRYPT_HASH_HANDLE hHash; // [rsp+50h] [rbp-78h] BYREF
  UCHAR v32[4]; // [rsp+58h] [rbp-70h] BYREF
  ULONG v33; // [rsp+5Ch] [rbp-6Ch] BYREF
  UCHAR pbOutput[4]; // [rsp+60h] [rbp-68h] BYREF
  PUCHAR v35; // [rsp+68h] [rbp-60h] BYREF
  BCRYPT_HASH_HANDLE *p_hHash; // [rsp+70h] [rbp-58h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+78h] [rbp-50h] BYREF
  char v38; // [rsp+80h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  phAlgorithm = 0;
  hHash = 0;
  *(_DWORD *)pbOutput = 0;
  v33 = 0;
  *(_DWORD *)v32 = 0;
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &phAlgorithm,
    0);
  v8 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA256", 0, 0);
  v9 = v8 | 0x10000000;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD3C,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
      (const char *)v9,
      pcbResult);
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hHash);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
    return v9;
  }
  Property = BCryptGetProperty(phAlgorithm, L"ObjectLength", pbOutput, 4u, &v33, 0);
  v12 = Property | 0x10000000;
  if ( Property < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD3D,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
      (const char *)v12,
      pcbResulta);
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hHash);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
    return v12;
  }
  try
  {
    wil::make_unique_cotaskmem<unsigned char [0]>(&pbHashObject, *(unsigned int *)pbOutput);
    p_hHash = &hHash;
    phHash = 0;
    v38 = 1;
    v13 = BCryptCreateHash(phAlgorithm, &phHash, pbHashObject, *(ULONG *)pbOutput, 0, 0, 0);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(&p_hHash);
    v14 = v13 | 0x10000000;
    if ( (v14 & 0x80000000) == 0 )
    {
      v16 = BCryptHashData(hHash, pbInput, cbInput, 0);
      v14 = v16 | 0x10000000;
      if ( v16 >= 0 )
      {
        v18 = BCryptGetProperty(phAlgorithm, L"HashDigestLength", v32, 4u, &v33, 0);
        v14 = v18 | 0x10000000;
        if ( v18 >= 0 )
        {
          wil::make_unique_cotaskmem<unsigned char [0]>(&v35, *(unsigned int *)v32);
          v20 = BCryptFinishHash(hHash, v35, *(ULONG *)v32, 0);
          v14 = v20 | 0x10000000;
          if ( v20 >= 0 )
          {
            *a3 = v35;
            *(_DWORD *)a4 = *(_DWORD *)v32;
            v35 = 0;
            v24 = pbHashObject;
            pbHashObject = 0;
            if ( v24 )
              CoTaskMemFree(v24);
            wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hHash);
            __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
            return 0;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xD43,
            (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
            (const char *)v14,
            pcbResultc);
          v21 = v35;
          v35 = 0;
          if ( v21 )
            CoTaskMemFree(v21);
          v22 = pbHashObject;
          pbHashObject = 0;
          if ( v22 )
            CoTaskMemFree(v22);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xD41,
            (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
            (const char *)v14,
            pcbResultc);
          v19 = pbHashObject;
          pbHashObject = 0;
          if ( v19 )
            CoTaskMemFree(v19);
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xD40,
          (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
          (const char *)v14,
          pcbResultb);
        v17 = pbHashObject;
        pbHashObject = 0;
        if ( v17 )
          CoTaskMemFree(v17);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD3F,
        (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
        (const char *)v14,
        pcbResultb);
      v15 = pbHashObject;
      pbHashObject = 0;
      if ( v15 )
        CoTaskMemFree(v15);
    }
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hHash);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
    result = v14;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xD49,
                           (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
                           v23);
  }
  return result;
}

```

## disassembly

```asm
0x18010d820  mov     rax, rsp
0x18010d823  push    rbx
0x18010d824  push    rsi
0x18010d825  push    rdi
0x18010d826  push    r12
0x18010d828  push    r13
0x18010d82a  push    r14
0x18010d82c  push    r15
0x18010d82e  sub     rsp, 90h
0x18010d835  mov     rdi, r9
0x18010d838  mov     rsi, r8
0x18010d83b  mov     r14d, edx
0x18010d83e  mov     r15, rcx
0x18010d841  xor     r12d, r12d
0x18010d844  mov     [rsp+0C8h+phAlgorithm], r12
0x18010d849  mov     [rax-78h], r12
0x18010d84d  mov     [rax-68h], r12d
0x18010d851  mov     [rax-6Ch], r12d
0x18010d855  mov     [rax-70h], r12d
0x18010d859  xor     edx, edx
0x18010d85b  lea     rcx, [rsp+0C8h+phAlgorithm]
0x18010d860  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18010d865  xor     r9d, r9d; dwFlags
0x18010d868  xor     r8d, r8d; pszImplementation
0x18010d86b  lea     rdx, pwszCNGHashAlgid; "SHA256"
0x18010d872  lea     rcx, [rsp+0C8h+phAlgorithm]; phAlgorithm
0x18010d877  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18010d87d  mov     ebx, eax
0x18010d87f  mov     r13d, 10000000h
0x18010d885  or      ebx, r13d
0x18010d888  jge     short loc_18010D8C3
0x18010d88a  mov     rcx, [rsp+0C8h]; this
0x18010d892  mov     r9d, ebx; char *
0x18010d895  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18010d89c  mov     edx, 0D3Ch; void *
0x18010d8a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010d8a6  nop
0x18010d8a7  lea     rcx, [rsp+0C8h+hHash]
0x18010d8ac  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18010d8b1  nop
0x18010d8b2  lea     rcx, [rsp+0C8h+phAlgorithm]
0x18010d8b7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18010d8bc  mov     eax, ebx
0x18010d8be  jmp     loc_18010DB9E
0x18010d8c3  mov     [rsp+0C8h+dwFlags], r12d; dwFlags
0x18010d8c8  lea     rax, [rsp+0C8h+var_6C]
0x18010d8cd  mov     [rsp+0C8h+pcbResult], rax; int
0x18010d8d2  mov     r9d, 4; cbOutput
0x18010d8d8  lea     r8, [rsp+0C8h+pbOutput]; pbOutput
0x18010d8dd  lea     rdx, aObjectlength; "ObjectLength"
0x18010d8e4  mov     rcx, [rsp+0C8h+phAlgorithm]; hObject
0x18010d8e9  call    cs:__imp_BCryptGetProperty
0x18010d8ef  mov     ebx, eax
0x18010d8f1  or      ebx, r13d
0x18010d8f4  jge     short loc_18010D92F
0x18010d8f6  mov     rcx, [rsp+0C8h]; this
0x18010d8fe  mov     r9d, ebx; char *
0x18010d901  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18010d908  mov     edx, 0D3Dh; void *
0x18010d90d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010d912  nop
0x18010d913  lea     rcx, [rsp+0C8h+hHash]
0x18010d918  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18010d91d  nop
0x18010d91e  lea     rcx, [rsp+0C8h+phAlgorithm]
0x18010d923  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18010d928  mov     eax, ebx
0x18010d92a  jmp     loc_18010DB9E
0x18010d92f  mov     edx, dword ptr [rsp+0C8h+pbOutput]
0x18010d933  lea     rcx, [rsp+0C8h+pbHashObject]
0x18010d938  call    ??$make_unique_cotaskmem@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_cotaskmem<uchar [0]>(unsigned __int64)
0x18010d93d  nop
0x18010d93e  lea     rax, [rsp+0C8h+hHash]
0x18010d943  mov     [rsp+0C8h+var_58], rax
0x18010d948  mov     [rsp+0C8h+phHash], r12
0x18010d94d  mov     [rsp+0C8h+var_48], 1
0x18010d955  mov     [rsp+0C8h+var_98], r12d; dwFlags
0x18010d95a  mov     [rsp+0C8h+dwFlags], r12d; cbSecret
0x18010d95f  mov     [rsp+0C8h+pcbResult], r12; int
0x18010d964  mov     r9d, dword ptr [rsp+0C8h+pbOutput]; cbHashObject
0x18010d969  mov     r8, [rsp+0C8h+pbHashObject]; pbHashObject
0x18010d96e  lea     rdx, [rsp+0C8h+phHash]; phHash
0x18010d973  mov     rcx, [rsp+0C8h+phAlgorithm]; hAlgorithm
0x18010d978  call    cs:__imp_BCryptCreateHash
0x18010d97e  mov     ebx, eax
0x18010d980  lea     rcx, [rsp+0C8h+var_58]
0x18010d985  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(void)
0x18010d98a  or      ebx, r13d
0x18010d98d  jns     short loc_18010D9DE
0x18010d98f  mov     rcx, [rsp+0C8h]; this
0x18010d997  mov     r9d, ebx; char *
0x18010d99a  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18010d9a1  mov     edx, 0D3Fh; void *
0x18010d9a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010d9ab  nop
0x18010d9ac  mov     rcx, [rsp+0C8h+pbHashObject]; pv
0x18010d9b1  mov     [rsp+0C8h+pbHashObject], r12
0x18010d9b6  test    rcx, rcx
0x18010d9b9  jz      short loc_18010D9C2
0x18010d9bb  call    cs:__imp_CoTaskMemFree
0x18010d9c1  nop
0x18010d9c2  lea     rcx, [rsp+0C8h+hHash]
0x18010d9c7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18010d9cc  nop
0x18010d9cd  lea     rcx, [rsp+0C8h+phAlgorithm]
0x18010d9d2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18010d9d7  mov     eax, ebx
0x18010d9d9  jmp     loc_18010DB9E
0x18010d9de  xor     r9d, r9d; dwFlags
0x18010d9e1  mov     r8d, r14d; cbInput
0x18010d9e4  mov     rdx, r15; pbInput
0x18010d9e7  mov     rcx, [rsp+0C8h+hHash]; hHash
0x18010d9ec  call    cs:__imp_BCryptHashData
0x18010d9f2  mov     ebx, eax
0x18010d9f4  or      ebx, r13d
0x18010d9f7  jge     short loc_18010DA48
0x18010d9f9  mov     rcx, [rsp+0C8h]; this
0x18010da01  mov     r9d, ebx; char *
0x18010da04  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18010da0b  mov     edx, 0D40h; void *
0x18010da10  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010da15  nop
0x18010da16  mov     rcx, [rsp+0C8h+pbHashObject]; pv
0x18010da1b  mov     [rsp+0C8h+pbHashObject], r12
0x18010da20  test    rcx, rcx
0x18010da23  jz      short loc_18010DA2C
0x18010da25  call    cs:__imp_CoTaskMemFree
0x18010da2b  nop
0x18010da2c  lea     rcx, [rsp+0C8h+hHash]
0x18010da31  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18010da36  nop
0x18010da37  lea     rcx, [rsp+0C8h+phAlgorithm]
0x18010da3c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18010da41  mov     eax, ebx
0x18010da43  jmp     loc_18010DB9E
0x18010da48  mov     [rsp+0C8h+dwFlags], r12d; dwFlags
0x18010da4d  lea     rax, [rsp+0C8h+var_6C]
0x18010da52  mov     [rsp+0C8h+pcbResult], rax; int
0x18010da57  mov     r9d, 4; cbOutput
0x18010da5d  lea     r8, [rsp+0C8h+var_70]; pbOutput
0x18010da62  lea     rdx, aHashdigestleng; "HashDigestLength"
0x18010da69  mov     rcx, [rsp+0C8h+phAlgorithm]; hObject
0x18010da6e  call    cs:__imp_BCryptGetProperty
0x18010da74  mov     ebx, eax
0x18010da76  or      ebx, r13d
0x18010da79  jge     short loc_18010DACA
0x18010da7b  mov     rcx, [rsp+0C8h]; this
0x18010da83  mov     r9d, ebx; char *
0x18010da86  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18010da8d  mov     edx, 0D41h; void *
0x18010da92  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010da97  nop
0x18010da98  mov     rcx, [rsp+0C8h+pbHashObject]; pv
0x18010da9d  mov     [rsp+0C8h+pbHashObject], r12
0x18010daa2  test    rcx, rcx
0x18010daa5  jz      short loc_18010DAAE
0x18010daa7  call    cs:__imp_CoTaskMemFree
0x18010daad  nop
0x18010daae  lea     rcx, [rsp+0C8h+hHash]
0x18010dab3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18010dab8  nop
0x18010dab9  lea     rcx, [rsp+0C8h+phAlgorithm]
0x18010dabe  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18010dac3  mov     eax, ebx
0x18010dac5  jmp     loc_18010DB9E
0x18010daca  mov     edx, dword ptr [rsp+0C8h+var_70]
0x18010dace  lea     rcx, [rsp+0C8h+var_60]
0x18010dad3  call    ??$make_unique_cotaskmem@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_cotaskmem<uchar [0]>(unsigned __int64)
0x18010dad8  xor     r9d, r9d; dwFlags
0x18010dadb  mov     r8d, dword ptr [rsp+0C8h+var_70]; cbOutput
0x18010dae0  mov     rdx, [rsp+0C8h+var_60]; pbOutput
0x18010dae5  mov     rcx, [rsp+0C8h+hHash]; hHash
0x18010daea  call    cs:__imp_BCryptFinishHash
0x18010daf0  mov     ebx, eax
0x18010daf2  or      ebx, r13d
0x18010daf5  jge     short loc_18010DB58
0x18010daf7  mov     rcx, [rsp+0C8h]; this
0x18010daff  mov     r9d, ebx; char *
0x18010db02  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18010db09  mov     edx, 0D43h; void *
0x18010db0e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010db13  mov     rcx, [rsp+0C8h+var_60]; pv
0x18010db18  mov     [rsp+0C8h+var_60], r12
0x18010db1d  test    rcx, rcx
0x18010db20  jz      short loc_18010DB29
0x18010db22  call    cs:__imp_CoTaskMemFree
0x18010db28  nop
0x18010db29  mov     rcx, [rsp+0C8h+pbHashObject]; pv
0x18010db2e  mov     [rsp+0C8h+pbHashObject], r12
0x18010db33  test    rcx, rcx
0x18010db36  jz      short loc_18010DB3F
0x18010db38  call    cs:__imp_CoTaskMemFree
0x18010db3e  nop
0x18010db3f  lea     rcx, [rsp+0C8h+hHash]
0x18010db44  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18010db49  nop
0x18010db4a  lea     rcx, [rsp+0C8h+phAlgorithm]
0x18010db4f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18010db54  mov     eax, ebx
0x18010db56  jmp     short loc_18010DB9E
0x18010db58  mov     rax, [rsp+0C8h+var_60]
0x18010db5d  mov     [rsi], rax
0x18010db60  mov     eax, dword ptr [rsp+0C8h+var_70]
0x18010db64  mov     [rdi], eax
0x18010db66  mov     [rsp+0C8h+var_60], r12
0x18010db6b  mov     rcx, [rsp+0C8h+pbHashObject]; pv
0x18010db70  mov     [rsp+0C8h+pbHashObject], r12
0x18010db75  test    rcx, rcx
0x18010db78  jz      short loc_18010DB81
0x18010db7a  call    cs:__imp_CoTaskMemFree
0x18010db80  nop
0x18010db81  lea     rcx, [rsp+0C8h+hHash]
0x18010db86  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18010db8b  nop
0x18010db8c  lea     rcx, [rsp+0C8h+phAlgorithm]
0x18010db91  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18010db96  xor     eax, eax
0x18010db98  jmp     short loc_18010DB9E
0x18010db9a  mov     eax, [rsp+0C8h+var_6C]
0x18010db9e  add     rsp, 90h
0x18010dba5  pop     r15
0x18010dba7  pop     r14
0x18010dba9  pop     r13
0x18010dbab  pop     r12
0x18010dbad  pop     rdi
0x18010dbae  pop     rsi
0x18010dbaf  pop     rbx
0x18010dbb0  retn
```
