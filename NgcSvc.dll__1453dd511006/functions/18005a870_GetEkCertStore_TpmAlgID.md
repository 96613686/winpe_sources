# GetEkCertStore(TpmAlgID)

- ea: `0x18005a870`
- end: `0x18005aaf5`
- name: `?GetEkCertStore@@YAPEAXW4TpmAlgID@@@Z`
- size: `645`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x1800add5c`

## callees

- `0x18000e570`
- `0x18000e960`
- `0x180032b6c`
- `0x180032c20`
- `0x180049c40`
- `0x18005a870`
- `0x18005cee0`
- `0x18005dd44`
- `0x18008f398`
- `0x1800ad554`
- `0x1800ad64c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005a953`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005aa14`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005a953`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005aa14`
- `ntdll!RtlGetPersistedStateLocation` at `0x18005a8f2`
- `ntdll!RtlGetPersistedStateLocation` at `0x18005a8f2`
- `CRYPT32!CertOpenStore` at `0x18005a980`
- `CRYPT32!CertOpenStore` at `0x18005aa43`
- `CRYPT32!CertOpenStore` at `0x18005a980`
- `CRYPT32!CertOpenStore` at `0x18005aa43`

## string_xrefs

- `0x18005a8e9`: `System\CurrentControlSet\Services\TPM\WMI\Endorsement\EKCertStore`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 GetEkCertStore()
{
  char **v0; // rcx
  LSTATUS v1; // eax
  bool v2; // sf
  const char *v3; // r9
  __int64 v4; // rbx
  LSTATUS v5; // eax
  bool v6; // sf
  const char *v7; // r9
  int dwOptions; // [rsp+20h] [rbp-E0h]
  HKEY phkResult; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v11; // [rsp+58h] [rbp-A8h] BYREF
  HCERTSTORE v12; // [rsp+60h] [rbp-A0h] BYREF
  int v13; // [rsp+68h] [rbp-98h] BYREF
  char *v14[4]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR SubKey[264]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  std::wstring::wstring(v14, L"TPMCoreProvisioningEKCertificates");
  memset_0(SubKey, 0, 0x208u);
  v13 = 520;
  v0 = v14;
  if ( v14[3] > (char *)7 )
    v0 = (char **)v14[0];
  RtlGetPersistedStateLocation(
    v0,
    0,
    L"System\\CurrentControlSet\\Services\\TPM\\WMI\\Endorsement\\EKCertStore",
    0,
    SubKey,
    520,
    &v13);
  v11 = 0;
  phkResult = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &phkResult,
    0);
  v1 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0xF003Fu, 0, &phkResult, 0);
  v2 = v1 < 0;
  if ( v1 > 0 )
    v2 = 1;
  if ( v2 )
  {
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &phkResult,
      0);
    v5 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0x20019u, 0, &phkResult, 0);
    v6 = v5 < 0;
    if ( v5 > 0 )
      v6 = 1;
    if ( v6 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xCD,
        (unsigned int)"onecore\\base\\ngscb\\tpmhli\\lib\\ekcert.cpp",
        (const char *)0x80070005LL,
        dwOptions);
    v12 = CertOpenStore((LPCSTR)4, 0, 0, 0x8000u, phkResult);
    __4__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CertCloseStoreNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil___wil__QEAAAEAV01___QEAV01__Z(
      &v11,
      &v12);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CertCloseStoreNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v12);
    v4 = v11;
    if ( !v11 )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0xC8,
        (unsigned int)"onecore\\base\\ngscb\\tpmhli\\lib\\ekcert.cpp",
        v7);
  }
  else
  {
    v12 = CertOpenStore((LPCSTR)4, 0, 0, 0, phkResult);
    __4__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CertCloseStoreNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil___wil__QEAAAEAV01___QEAV01__Z(
      &v11,
      &v12);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CertCloseStoreNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v12);
    v4 = v11;
    if ( !v11 )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0xB3,
        (unsigned int)"onecore\\base\\ngscb\\tpmhli\\lib\\ekcert.cpp",
        v3);
  }
  v11 = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CertCloseStoreNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v11);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v14);
  return v4;
}

```

## disassembly

```asm
0x18005a870  mov     [rsp-8+arg_0], rbx
0x18005a875  push    rbp
0x18005a876  lea     rbp, [rsp-1B0h]
0x18005a87e  sub     rsp, 2B0h
0x18005a885  mov     rax, cs:__security_cookie
0x18005a88c  xor     rax, rsp
0x18005a88f  mov     [rbp+1B0h+var_10], rax
0x18005a896  lea     rdx, aTpmcoreprovisi_0; "TPMCoreProvisioningEKCertificates"
0x18005a89d  lea     rcx, [rsp+2B0h+var_240]
0x18005a8a2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005a8a7  nop
0x18005a8a8  mov     ebx, 208h
0x18005a8ad  mov     r8d, ebx; Size
0x18005a8b0  xor     edx, edx; Val
0x18005a8b2  lea     rcx, [rbp+1B0h+SubKey]; void *
0x18005a8b6  call    memset_0
0x18005a8bb  mov     [rsp+2B0h+var_248], ebx
0x18005a8bf  lea     rcx, [rsp+2B0h+var_240]
0x18005a8c4  cmp     [rbp+1B0h+var_228], 7
0x18005a8c9  cmova   rcx, [rsp+2B0h+var_240]
0x18005a8cf  lea     rax, [rsp+2B0h+var_248]
0x18005a8d4  mov     [rsp+2B0h+lpSecurityAttributes], rax
0x18005a8d9  mov     [rsp+2B0h+samDesired], ebx
0x18005a8dd  lea     rax, [rbp+1B0h+SubKey]
0x18005a8e1  mov     qword ptr [rsp+2B0h+dwOptions], rax
0x18005a8e6  xor     r9d, r9d
0x18005a8e9  lea     r8, aSystemCurrentc_6; "System\\CurrentControlSet\\Services\\TP"...
0x18005a8f0  xor     edx, edx
0x18005a8f2  call    cs:__imp_RtlGetPersistedStateLocation
0x18005a8f8  mov     [rsp+2B0h+var_258], 0
0x18005a901  mov     [rsp+2B0h+var_260], 0
0x18005a90a  xor     edx, edx
0x18005a90c  lea     rcx, [rsp+2B0h+var_260]
0x18005a911  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18005a916  mov     [rsp+2B0h+lpdwDisposition], 0; lpdwDisposition
0x18005a91f  lea     rax, [rsp+2B0h+var_260]
0x18005a924  mov     [rsp+2B0h+phkResult], rax; phkResult
0x18005a929  mov     [rsp+2B0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18005a932  mov     [rsp+2B0h+samDesired], 0F003Fh; samDesired
0x18005a93a  mov     [rsp+2B0h+dwOptions], 0; dwOptions
0x18005a942  xor     r9d, r9d; lpClass
0x18005a945  xor     r8d, r8d; Reserved
0x18005a948  lea     rdx, [rbp+1B0h+SubKey]; lpSubKey
0x18005a94c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005a953  call    cs:__imp_RegCreateKeyExW
0x18005a959  mov     ebx, 80070000h
0x18005a95e  test    eax, eax
0x18005a960  jle     short loc_18005A969
0x18005a962  movzx   eax, ax
0x18005a965  or      eax, ebx
0x18005a967  test    eax, eax
0x18005a969  js      short loc_18005A9CB
0x18005a96b  mov     rax, [rsp+2B0h+var_260]
0x18005a970  mov     qword ptr [rsp+2B0h+dwOptions], rax; pvPara
0x18005a975  xor     r9d, r9d; dwFlags
0x18005a978  xor     r8d, r8d; hCryptProv
0x18005a97b  xor     edx, edx; dwEncodingType
0x18005a97d  lea     ecx, [rdx+4]; lpszStoreProvider
0x18005a980  call    cs:__imp_CertOpenStore
0x18005a986  mov     [rsp+2B0h+var_250], rax
0x18005a98b  lea     rdx, [rsp+2B0h+var_250]
0x18005a990  lea     rcx, [rsp+2B0h+var_258]
0x18005a995  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CertCloseStoreNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z
0x18005a99a  lea     rcx, [rsp+2B0h+var_250]
0x18005a99f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CertCloseStoreNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18005a9a4  mov     rcx, [rbp+1B8h]; this
0x18005a9ab  mov     rbx, [rsp+2B0h+var_258]
0x18005a9b0  test    rbx, rbx
0x18005a9b3  jnz     loc_18005AA8A
0x18005a9b9  lea     r8, aOnecoreBaseNgs_8; "onecore\\base\\ngscb\\tpmhli\\lib\\ekce"...
0x18005a9c0  mov     edx, 0B3h; void *
0x18005a9c5  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18005a9cb  xor     edx, edx
0x18005a9cd  lea     rcx, [rsp+2B0h+var_260]
0x18005a9d2  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18005a9d7  mov     [rsp+2B0h+lpdwDisposition], 0; lpdwDisposition
0x18005a9e0  lea     rax, [rsp+2B0h+var_260]
0x18005a9e5  mov     [rsp+2B0h+phkResult], rax; phkResult
0x18005a9ea  mov     [rsp+2B0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18005a9f3  mov     [rsp+2B0h+samDesired], 20019h; samDesired
0x18005a9fb  mov     [rsp+2B0h+dwOptions], 0; int
0x18005aa03  xor     r9d, r9d; lpClass
0x18005aa06  xor     r8d, r8d; Reserved
0x18005aa09  lea     rdx, [rbp+1B0h+SubKey]; lpSubKey
0x18005aa0d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005aa14  call    cs:__imp_RegCreateKeyExW
0x18005aa1a  test    eax, eax
0x18005aa1c  jle     short loc_18005AA25
0x18005aa1e  movzx   eax, ax
0x18005aa21  or      eax, ebx
0x18005aa23  test    eax, eax
0x18005aa25  js      loc_18005AAD6
0x18005aa2b  mov     rax, [rsp+2B0h+var_260]
0x18005aa30  mov     qword ptr [rsp+2B0h+dwOptions], rax; pvPara
0x18005aa35  mov     r9d, 8000h; dwFlags
0x18005aa3b  xor     r8d, r8d; hCryptProv
0x18005aa3e  xor     edx, edx; dwEncodingType
0x18005aa40  lea     ecx, [rdx+4]; lpszStoreProvider
0x18005aa43  call    cs:__imp_CertOpenStore
0x18005aa49  mov     [rsp+2B0h+var_250], rax
0x18005aa4e  lea     rdx, [rsp+2B0h+var_250]
0x18005aa53  lea     rcx, [rsp+2B0h+var_258]
0x18005aa58  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CertCloseStoreNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z
0x18005aa5d  lea     rcx, [rsp+2B0h+var_250]
0x18005aa62  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CertCloseStoreNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18005aa67  mov     rcx, [rbp+1B8h]; this
0x18005aa6e  mov     rbx, [rsp+2B0h+var_258]
0x18005aa73  test    rbx, rbx
0x18005aa76  jnz     short loc_18005AA8A
0x18005aa78  lea     r8, aOnecoreBaseNgs_8; "onecore\\base\\ngscb\\tpmhli\\lib\\ekce"...
0x18005aa7f  mov     edx, 0C8h; void *
0x18005aa84  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18005aa8a  mov     [rsp+2B0h+var_258], 0
0x18005aa93  lea     rcx, [rsp+2B0h+var_260]
0x18005aa98  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18005aa9d  nop
0x18005aa9e  lea     rcx, [rsp+2B0h+var_258]
0x18005aaa3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CertCloseStoreNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18005aaa8  nop
0x18005aaa9  lea     rcx, [rsp+2B0h+var_240]
0x18005aaae  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x18005aab3  mov     rax, rbx
0x18005aab6  mov     rcx, [rbp+1B0h+var_10]
0x18005aabd  xor     rcx, rsp; StackCookie
0x18005aac0  call    __security_check_cookie
0x18005aac5  mov     rbx, [rsp+2B0h+arg_0]
0x18005aacd  add     rsp, 2B0h
0x18005aad4  pop     rbp
0x18005aad5  retn
0x18005aad6  mov     rcx, [rbp+1B8h]; this
0x18005aadd  mov     r9d, 80070005h; char *
0x18005aae3  lea     r8, aOnecoreBaseNgs_8; "onecore\\base\\ngscb\\tpmhli\\lib\\ekce"...
0x18005aaea  mov     edx, 0CDh; void *
0x18005aaef  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
