# GetEkCertStore(TpmAlgID)

- ea: `0x180098fcc`
- end: `0x18009926b`
- name: `?GetEkCertStore@@YAPEAXW4TpmAlgID@@@Z`
- size: `671`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180099274`

## callees

- `0x180007270`
- `0x180007c7c`
- `0x180053990`
- `0x18005b73c`
- `0x18005bb6c`
- `0x18005bb94`
- `0x18005bbf0`
- `0x18005d010`
- `0x18005d6e0`
- `0x180098950`
- `0x180098aa4`
- `0x180098fcc`
- `0x180099950`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800990b2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180099172`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800990b2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180099172`
- `ntdll!RtlGetPersistedStateLocation` at `0x18009904b`
- `ntdll!RtlGetPersistedStateLocation` at `0x18009904b`
- `CRYPT32!CertOpenStore` at `0x1800990e5`
- `CRYPT32!CertOpenStore` at `0x1800991a7`
- `CRYPT32!CertOpenStore` at `0x1800990e5`
- `CRYPT32!CertOpenStore` at `0x1800991a7`

## string_xrefs

- `0x180099042`: `System\CurrentControlSet\Services\TPM\WMI\Endorsement\EKCertStore`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 GetEkCertStore()
{
  __int64 v0; // rax
  LSTATUS v1; // eax
  bool v2; // sf
  unsigned int v3; // r8d
  const char *v4; // r9
  __int64 v5; // rbx
  LSTATUS v6; // eax
  bool v7; // sf
  unsigned int v8; // r8d
  const char *v9; // r9
  unsigned int v11; // eax
  int dwOptions; // [rsp+20h] [rbp-E0h]
  HKEY phkResult; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v14; // [rsp+58h] [rbp-A8h] BYREF
  HCERTSTORE v15; // [rsp+60h] [rbp-A0h] BYREF
  int v16; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v17[32]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR SubKey[264]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  std::wstring::wstring(v17, L"TPMCoreProvisioningEKCertificates");
  memset_0(SubKey, 0, 0x208u);
  v16 = 520;
  v0 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v17);
  RtlGetPersistedStateLocation(
    v0,
    0,
    L"System\\CurrentControlSet\\Services\\TPM\\WMI\\Endorsement\\EKCertStore",
    0,
    SubKey,
    520,
    &v16);
  v14 = 0;
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
    v6 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0x20019u, 0, &phkResult, 0);
    v7 = v6 < 0;
    if ( v6 > 0 )
      v7 = 1;
    if ( v7 )
    {
      v11 = wil::verify_hresult<long>(2147942405LL);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xCD,
        (unsigned int)"onecore\\base\\ngscb\\tpmhli\\lib\\ekcert.cpp",
        (const char *)v11,
        dwOptions);
    }
    v15 = CertOpenStore((LPCSTR)4, 0, 0, 0x8000u, phkResult);
    __4__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CertCloseStoreNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil___wil__QEAAAEAV01___QEAV01__Z(
      &v14,
      &v15);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CertCloseStoreNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v15);
    v5 = v14;
    if ( !v14 )
      wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0xC8, v8, v9);
  }
  else
  {
    v15 = CertOpenStore((LPCSTR)4, 0, 0, 0, phkResult);
    __4__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CertCloseStoreNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil___wil__QEAAAEAV01___QEAV01__Z(
      &v14,
      &v15);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CertCloseStoreNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v15);
    v5 = v14;
    if ( !v14 )
      wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0xB3, v3, v4);
  }
  v14 = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CertCloseStoreNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v14);
  std::wstring::_Tidy_deallocate(v17);
  return v5;
}

```

## disassembly

```asm
0x180098fcc  mov     [rsp-8+arg_0], rbx
0x180098fd1  push    rbp
0x180098fd2  lea     rbp, [rsp-1B0h]
0x180098fda  sub     rsp, 2B0h
0x180098fe1  mov     rax, cs:__security_cookie
0x180098fe8  xor     rax, rsp
0x180098feb  mov     [rbp+1B0h+var_10], rax
0x180098ff2  lea     rdx, aTpmcoreprovisi_1; "TPMCoreProvisioningEKCertificates"
0x180098ff9  lea     rcx, [rsp+2B0h+var_240]
0x180098ffe  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180099003  nop
0x180099004  mov     ebx, 208h
0x180099009  mov     r8d, ebx; Size
0x18009900c  xor     edx, edx; Val
0x18009900e  lea     rcx, [rbp+1B0h+SubKey]; void *
0x180099012  call    memset_0
0x180099017  mov     [rsp+2B0h+var_248], ebx
0x18009901b  lea     rcx, [rsp+2B0h+var_240]
0x180099020  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180099025  mov     rcx, rax
0x180099028  lea     rax, [rsp+2B0h+var_248]
0x18009902d  mov     [rsp+2B0h+lpSecurityAttributes], rax
0x180099032  mov     [rsp+2B0h+samDesired], ebx
0x180099036  lea     rax, [rbp+1B0h+SubKey]
0x18009903a  mov     qword ptr [rsp+2B0h+dwOptions], rax
0x18009903f  xor     r9d, r9d
0x180099042  lea     r8, aSystemCurrentc_1; "System\\CurrentControlSet\\Services\\TP"...
0x180099049  xor     edx, edx
0x18009904b  call    cs:__imp_RtlGetPersistedStateLocation
0x180099052  nop     dword ptr [rax+rax+00h]
0x180099057  mov     [rsp+2B0h+var_258], 0
0x180099060  mov     [rsp+2B0h+var_260], 0
0x180099069  xor     edx, edx
0x18009906b  lea     rcx, [rsp+2B0h+var_260]
0x180099070  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180099075  mov     [rsp+2B0h+lpdwDisposition], 0; lpdwDisposition
0x18009907e  lea     rax, [rsp+2B0h+var_260]
0x180099083  mov     [rsp+2B0h+phkResult], rax; phkResult
0x180099088  mov     [rsp+2B0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180099091  mov     [rsp+2B0h+samDesired], 0F003Fh; samDesired
0x180099099  mov     [rsp+2B0h+dwOptions], 0; dwOptions
0x1800990a1  xor     r9d, r9d; lpClass
0x1800990a4  xor     r8d, r8d; Reserved
0x1800990a7  lea     rdx, [rbp+1B0h+SubKey]; lpSubKey
0x1800990ab  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800990b2  call    cs:__imp_RegCreateKeyExW
0x1800990b9  nop     dword ptr [rax+rax+00h]
0x1800990be  mov     ebx, 80070000h
0x1800990c3  test    eax, eax
0x1800990c5  jle     short loc_1800990CE
0x1800990c7  movzx   eax, ax
0x1800990ca  or      eax, ebx
0x1800990cc  test    eax, eax
0x1800990ce  js      short loc_180099129
0x1800990d0  mov     rax, [rsp+2B0h+var_260]
0x1800990d5  mov     qword ptr [rsp+2B0h+dwOptions], rax; pvPara
0x1800990da  xor     r9d, r9d; dwFlags
0x1800990dd  xor     r8d, r8d; hCryptProv
0x1800990e0  xor     edx, edx; dwEncodingType
0x1800990e2  lea     ecx, [rdx+4]; lpszStoreProvider
0x1800990e5  call    cs:__imp_CertOpenStore
0x1800990ec  nop     dword ptr [rax+rax+00h]
0x1800990f1  mov     [rsp+2B0h+var_250], rax
0x1800990f6  lea     rdx, [rsp+2B0h+var_250]
0x1800990fb  lea     rcx, [rsp+2B0h+var_258]
0x180099100  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CertCloseStoreNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z
0x180099105  lea     rcx, [rsp+2B0h+var_250]
0x18009910a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CertCloseStoreNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18009910f  mov     rcx, [rbp+1B8h]; this
0x180099116  mov     rbx, [rsp+2B0h+var_258]
0x18009911b  test    rbx, rbx
0x18009911e  jz      loc_18009923A
0x180099124  jmp     loc_1800991E2
0x180099129  xor     edx, edx
0x18009912b  lea     rcx, [rsp+2B0h+var_260]
0x180099130  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180099135  mov     [rsp+2B0h+lpdwDisposition], 0; lpdwDisposition
0x18009913e  lea     rax, [rsp+2B0h+var_260]
0x180099143  mov     [rsp+2B0h+phkResult], rax; phkResult
0x180099148  mov     [rsp+2B0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180099151  mov     [rsp+2B0h+samDesired], 20019h; samDesired
0x180099159  mov     [rsp+2B0h+dwOptions], 0; int
0x180099161  xor     r9d, r9d; lpClass
0x180099164  xor     r8d, r8d; Reserved
0x180099167  lea     rdx, [rbp+1B0h+SubKey]; lpSubKey
0x18009916b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180099172  call    cs:__imp_RegCreateKeyExW
0x180099179  nop     dword ptr [rax+rax+00h]
0x18009917e  test    eax, eax
0x180099180  jle     short loc_180099189
0x180099182  movzx   eax, ax
0x180099185  or      eax, ebx
0x180099187  test    eax, eax
0x180099189  js      loc_180099245
0x18009918f  mov     rax, [rsp+2B0h+var_260]
0x180099194  mov     qword ptr [rsp+2B0h+dwOptions], rax; pvPara
0x180099199  mov     r9d, 8000h; dwFlags
0x18009919f  xor     r8d, r8d; hCryptProv
0x1800991a2  xor     edx, edx; dwEncodingType
0x1800991a4  lea     ecx, [rdx+4]; lpszStoreProvider
0x1800991a7  call    cs:__imp_CertOpenStore
0x1800991ae  nop     dword ptr [rax+rax+00h]
0x1800991b3  mov     [rsp+2B0h+var_250], rax
0x1800991b8  lea     rdx, [rsp+2B0h+var_250]
0x1800991bd  lea     rcx, [rsp+2B0h+var_258]
0x1800991c2  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CertCloseStoreNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z
0x1800991c7  lea     rcx, [rsp+2B0h+var_250]
0x1800991cc  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CertCloseStoreNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800991d1  mov     rcx, [rbp+1B8h]; this
0x1800991d8  mov     rbx, [rsp+2B0h+var_258]
0x1800991dd  test    rbx, rbx
0x1800991e0  jz      short loc_18009922F
0x1800991e2  mov     [rsp+2B0h+var_258], 0
0x1800991eb  lea     rcx, [rsp+2B0h+var_260]
0x1800991f0  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800991f5  nop
0x1800991f6  lea     rcx, [rsp+2B0h+var_258]
0x1800991fb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CertCloseStoreNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180099200  nop
0x180099201  lea     rcx, [rsp+2B0h+var_240]
0x180099206  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009920b  mov     rax, rbx
0x18009920e  mov     rcx, [rbp+1B0h+var_10]
0x180099215  xor     rcx, rsp; StackCookie
0x180099218  call    __security_check_cookie
0x18009921d  mov     rbx, [rsp+2B0h+arg_0]
0x180099225  add     rsp, 2B0h
0x18009922c  pop     rbp
0x18009922d  retn
0x18009922f  mov     edx, 0C8h; void *
0x180099234  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18009923a  mov     edx, 0B3h; void *
0x18009923f  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180099245  mov     ecx, 80070005h
0x18009924a  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18009924f  mov     r9d, eax; char *
0x180099252  mov     rcx, [rbp+1B8h]; this
0x180099259  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\tpmhli\\lib\\ekce"...
0x180099260  mov     edx, 0CDh; void *
0x180099265  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
