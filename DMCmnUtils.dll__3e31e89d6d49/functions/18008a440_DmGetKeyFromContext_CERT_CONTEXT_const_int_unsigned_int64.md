# DmGetKeyFromContext(_CERT_CONTEXT const *,int,unsigned __int64 *)

- ea: `0x18008a440`
- end: `0x18008a63d`
- name: `?DmGetKeyFromContext@@YAJPEBU_CERT_CONTEXT@@HPEA_K@Z`
- size: `509`
- prototype: `int(const struct _CERT_CONTEXT *, int, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180054ec0`
- `0x18005b914`
- `0x18005bd30`
- `0x18005cb4c`
- `0x18005cfac`
- `0x1800605a8`
- `0x1800609dc`
- `0x180061a64`
- `0x180062728`
- `0x180069ef0`
- `0x18008a440`
- `0x18008a650`

## import_xrefs

- `ncrypt!NCryptOpenStorageProvider` at `0x18008a524`
- `ncrypt!NCryptOpenStorageProvider` at `0x18008a524`
- `ncrypt!NCryptOpenKey` at `0x18008a576`
- `ncrypt!NCryptOpenKey` at `0x18008a576`

## string_xrefs

- `0x18008a4ab`: `DmGetKeyFromContext: DmGetActiveUserSid`
- `0x18008a53f`: `DmGetKeyFromContext: NCryptOpenStorageProvider`
- `0x18008a591`: `DmGetKeyFromContext: NCryptOpenKey`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall DmGetKeyFromContext(const struct _CERT_CONTEXT *a1, int a2, unsigned __int64 *a3)
{
  const CERT_CONTEXT *v5; // r14
  SECURITY_STATUS ActiveUserSid; // ebx
  const wchar_t *v7; // r8
  __int64 v8; // rcx
  const wchar_t *v9; // r8
  WCHAR *v10; // rcx
  WCHAR *v12; // rcx
  NCRYPT_PROV_HANDLE phProvider; // [rsp+30h] [rbp-30h] BYREF
  _BYTE v14[16]; // [rsp+38h] [rbp-28h] BYREF
  LPCWSTR *p_pszKeyName; // [rsp+48h] [rbp-18h] BYREF
  unsigned __int16 *v16; // [rsp+50h] [rbp-10h] BYREF
  char v17; // [rsp+58h] [rbp-8h]
  LPCWSTR pszKeyName; // [rsp+90h] [rbp+30h] BYREF
  unsigned __int16 *v19; // [rsp+A8h] [rbp+48h] BYREF

  v5 = a1;
  pszKeyName = 0;
  v19 = 0;
  v14[0] = 0;
  v14[2] = 0;
  if ( !a1 || !a3 )
  {
    ActiveUserSid = -2147024809;
    if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
    {
      v7 = L"DmGetKeyFromContext: InvalidArgs";
      goto LABEL_26;
    }
    goto LABEL_27;
  }
  if ( !a2 )
  {
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v19,
      0);
    ActiveUserSid = DmGetActiveUserSid(&v19);
    if ( ActiveUserSid < 0 )
    {
      if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
      {
        v7 = L"DmGetKeyFromContext: DmGetActiveUserSid";
LABEL_26:
        McTemplateU0zd_EventWriteTransfer(a1, EnterpriseDiagnosticsTPMFunctionFailure, v7, (unsigned int)ActiveUserSid);
        goto LABEL_27;
      }
      goto LABEL_27;
    }
    AutoImpersonate::ImpersonateSID((AutoImpersonate *)v14, v19);
  }
  p_pszKeyName = &pszKeyName;
  v16 = 0;
  v17 = 1;
  ActiveUserSid = DmGetKeyNameFromContext(v5, 1, &v16);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<unsigned short,wil::process_heap_deleter>>(&p_pszKeyName);
  a1 = (const struct _CERT_CONTEXT *)((unsigned int)ActiveUserSid >> 31);
  if ( ActiveUserSid < 0 )
  {
    if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
    {
      v7 = L"DmGetKeyFromContext: DmGetKeyNameFromContext";
      goto LABEL_26;
    }
LABEL_27:
    AutoImpersonate::~AutoImpersonate((AutoImpersonate *)v14);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v19);
    v12 = (WCHAR *)pszKeyName;
    pszKeyName = 0;
    if ( v12 )
      MemoryFree(v12);
    return (unsigned int)ActiveUserSid;
  }
  phProvider = 0;
  ActiveUserSid = NCryptOpenStorageProvider(&phProvider, L"Microsoft Platform Crypto Provider", 0);
  if ( ActiveUserSid < 0 )
  {
    if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) == 0 )
    {
LABEL_15:
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
      goto LABEL_27;
    }
    v9 = L"DmGetKeyFromContext: NCryptOpenStorageProvider";
LABEL_14:
    McTemplateU0zd_EventWriteTransfer(v8, EnterpriseDiagnosticsTPMFunctionFailure, v9, (unsigned int)ActiveUserSid);
    goto LABEL_15;
  }
  ActiveUserSid = NCryptOpenKey(phProvider, a3, pszKeyName, 0, 0);
  if ( ActiveUserSid < 0 )
  {
    if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) == 0 )
      goto LABEL_15;
    v9 = L"DmGetKeyFromContext: NCryptOpenKey";
    goto LABEL_14;
  }
  if ( !a2 )
    AutoImpersonate::RevertToSelf((AutoImpersonate *)v14);
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
  AutoImpersonate::~AutoImpersonate((AutoImpersonate *)v14);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v19);
  v10 = (WCHAR *)pszKeyName;
  pszKeyName = 0;
  if ( v10 )
    MemoryFree(v10);
  return 0;
}

```

## disassembly

```asm
0x18008a440  mov     [rsp-28h+arg_8], rbx
0x18008a445  push    rbp
0x18008a446  push    rsi
0x18008a447  push    rdi
0x18008a448  push    r14
0x18008a44a  push    r15
0x18008a44c  mov     rbp, rsp
0x18008a44f  sub     rsp, 60h
0x18008a453  mov     rsi, r8
0x18008a456  mov     edi, edx
0x18008a458  mov     r14, rcx
0x18008a45b  xor     r15d, r15d
0x18008a45e  mov     [rbp+pszKeyName], r15
0x18008a462  mov     [rbp+arg_18], r15
0x18008a466  mov     [rbp+var_28], r15b
0x18008a46a  mov     [rbp+var_26], r15b
0x18008a46e  test    rcx, rcx
0x18008a471  jz      loc_18008A5DB
0x18008a477  test    r8, r8
0x18008a47a  jz      loc_18008A5DB
0x18008a480  test    edx, edx
0x18008a482  jnz     short loc_18008A4C4
0x18008a484  xor     edx, edx
0x18008a486  lea     rcx, [rbp+arg_18]
0x18008a48a  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18008a48f  lea     rcx, [rbp+arg_18]; unsigned __int16 **
0x18008a493  call    ?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x18008a498  mov     ebx, eax
0x18008a49a  test    eax, eax
0x18008a49c  jns     short loc_18008A4B7
0x18008a49e  test    byte ptr cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 1
0x18008a4a5  jz      loc_18008A600
0x18008a4ab  lea     r8, aDmgetkeyfromco_3; "DmGetKeyFromContext: DmGetActiveUserSid"
0x18008a4b2  jmp     loc_18008A5F0
0x18008a4b7  mov     rdx, [rbp+arg_18]; unsigned __int16 *
0x18008a4bb  lea     rcx, [rbp+var_28]; this
0x18008a4bf  call    ?ImpersonateSID@AutoImpersonate@@QEAAJPEBG@Z; AutoImpersonate::ImpersonateSID(ushort const *)
0x18008a4c4  lea     rax, [rbp+pszKeyName]
0x18008a4c8  mov     [rbp+var_18], rax
0x18008a4cc  mov     [rbp+var_10], r15
0x18008a4d0  mov     [rbp+var_8], 1
0x18008a4d4  lea     r8, [rbp+var_10]; unsigned __int16 **
0x18008a4d8  mov     edx, 1; int
0x18008a4dd  mov     rcx, r14; pCert
0x18008a4e0  call    ?DmGetKeyNameFromContext@@YAJPEBU_CERT_CONTEXT@@HPEAPEAG@Z; DmGetKeyNameFromContext(_CERT_CONTEXT const *,int,ushort * *)
0x18008a4e5  mov     ebx, eax
0x18008a4e7  lea     rcx, [rbp+var_18]
0x18008a4eb  call    ??1?$out_param_t@V?$unique_ptr@GUprocess_heap_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<ushort,wil::process_heap_deleter>>(void)
0x18008a4f0  mov     ecx, ebx
0x18008a4f2  shr     ecx, 1Fh
0x18008a4f5  test    cl, cl
0x18008a4f7  jz      short loc_18008A512
0x18008a4f9  test    byte ptr cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 1
0x18008a500  jz      loc_18008A600
0x18008a506  lea     r8, aDmgetkeyfromco_2; "DmGetKeyFromContext: DmGetKeyNameFromCo"...
0x18008a50d  jmp     loc_18008A5F0
0x18008a512  mov     [rbp+phProvider], r15
0x18008a516  xor     r8d, r8d; dwFlags
0x18008a519  lea     rdx, aMicrosoftPlatf; "Microsoft Platform Crypto Provider"
0x18008a520  lea     rcx, [rbp+phProvider]; phProvider
0x18008a524  call    cs:__imp_NCryptOpenStorageProvider
0x18008a52b  nop     dword ptr [rax+rax+00h]
0x18008a530  mov     ebx, eax
0x18008a532  test    eax, eax
0x18008a534  jns     short loc_18008A563
0x18008a536  test    byte ptr cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 1
0x18008a53d  jz      short loc_18008A555
0x18008a53f  lea     r8, aDmgetkeyfromco_0; "DmGetKeyFromContext: NCryptOpenStorageP"...
0x18008a546  mov     r9d, ebx
0x18008a549  lea     rdx, EnterpriseDiagnosticsTPMFunctionFailure
0x18008a550  call    McTemplateU0zd_EventWriteTransfer
0x18008a555  lea     rcx, [rbp+phProvider]
0x18008a559  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18008a55e  jmp     loc_18008A600
0x18008a563  mov     [rsp+60h+dwFlags], r15d; dwFlags
0x18008a568  xor     r9d, r9d; dwLegacyKeySpec
0x18008a56b  mov     r8, [rbp+pszKeyName]; pszKeyName
0x18008a56f  mov     rdx, rsi; phKey
0x18008a572  mov     rcx, [rbp+phProvider]; hProvider
0x18008a576  call    cs:__imp_NCryptOpenKey
0x18008a57d  nop     dword ptr [rax+rax+00h]
0x18008a582  mov     ebx, eax
0x18008a584  test    eax, eax
0x18008a586  jns     short loc_18008A59A
0x18008a588  test    byte ptr cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 1
0x18008a58f  jz      short loc_18008A555
0x18008a591  lea     r8, aDmgetkeyfromco_1; "DmGetKeyFromContext: NCryptOpenKey"
0x18008a598  jmp     short loc_18008A546
0x18008a59a  test    edi, edi
0x18008a59c  jnz     short loc_18008A5A7
0x18008a59e  lea     rcx, [rbp+var_28]; this
0x18008a5a2  call    ?RevertToSelf@AutoImpersonate@@QEAAJXZ; AutoImpersonate::RevertToSelf(void)
0x18008a5a7  lea     rcx, [rbp+phProvider]
0x18008a5ab  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18008a5b0  nop
0x18008a5b1  lea     rcx, [rbp+var_28]; this
0x18008a5b5  call    ??1AutoImpersonate@@QEAA@XZ; AutoImpersonate::~AutoImpersonate(void)
0x18008a5ba  nop
0x18008a5bb  lea     rcx, [rbp+arg_18]
0x18008a5bf  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18008a5c4  nop
0x18008a5c5  mov     rcx, [rbp+pszKeyName]; void *
0x18008a5c9  mov     [rbp+pszKeyName], r15
0x18008a5cd  test    rcx, rcx
0x18008a5d0  jz      short loc_18008A5D7
0x18008a5d2  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x18008a5d7  xor     eax, eax
0x18008a5d9  jmp     short loc_18008A628
0x18008a5db  mov     ebx, 80070057h
0x18008a5e0  test    byte ptr cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 1
0x18008a5e7  jz      short loc_18008A600
0x18008a5e9  lea     r8, aDmgetkeyfromco_4; "DmGetKeyFromContext: InvalidArgs"
0x18008a5f0  mov     r9d, ebx
0x18008a5f3  lea     rdx, EnterpriseDiagnosticsTPMFunctionFailure
0x18008a5fa  call    McTemplateU0zd_EventWriteTransfer
0x18008a5ff  nop
0x18008a600  lea     rcx, [rbp+var_28]; this
0x18008a604  call    ??1AutoImpersonate@@QEAA@XZ; AutoImpersonate::~AutoImpersonate(void)
0x18008a609  nop
0x18008a60a  lea     rcx, [rbp+arg_18]
0x18008a60e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18008a613  nop
0x18008a614  mov     rcx, [rbp+pszKeyName]; void *
0x18008a618  mov     [rbp+pszKeyName], r15
0x18008a61c  test    rcx, rcx
0x18008a61f  jz      short loc_18008A626
0x18008a621  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x18008a626  mov     eax, ebx
0x18008a628  mov     rbx, [rsp+60h+arg_8]
0x18008a630  add     rsp, 60h
0x18008a634  pop     r15
0x18008a636  pop     r14
0x18008a638  pop     rdi
0x18008a639  pop     rsi
0x18008a63a  pop     rbp
0x18008a63b  retn
```
