# GetEkCertStore(TpmAlgID)

- ea: `0x18006d0c0`
- end: `0x18006d375`
- name: `?GetEkCertStore@@YAPEAXW4TpmAlgID@@@Z`
- size: `693`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x1800c2650`

## callees

- `0x180022110`
- `0x180036ab4`
- `0x180046798`
- `0x18005305c`
- `0x18005437c`
- `0x180068eb8`
- `0x18006d0c0`
- `0x18006d388`
- `0x18006d3b0`
- `0x18006d3ec`
- `0x1800764d0`
- `0x18007704c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006d22f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006d22f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18006d19d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18006d28b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18006d19d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18006d28b`
- `ntdll!RtlGetPersistedStateLocation` at `0x18006d142`
- `ntdll!RtlGetPersistedStateLocation` at `0x18006d142`
- `CRYPT32!CertOpenStore` at `0x18006d1ce`
- `CRYPT32!CertOpenStore` at `0x18006d2c3`
- `CRYPT32!CertOpenStore` at `0x18006d1ce`
- `CRYPT32!CertOpenStore` at `0x18006d2c3`

## string_xrefs

- `0x18006d139`: `System\CurrentControlSet\Services\TPM\WMI\Endorsement\EKCertStoreECC`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 GetEkCertStore()
{
  _QWORD *v0; // rcx
  LSTATUS v1; // eax
  bool v2; // sf
  unsigned int v3; // r8d
  const char *v4; // r9
  __int64 v5; // rbx
  HKEY v6; // rbx
  LSTATUS v7; // eax
  bool v8; // sf
  unsigned int v9; // r8d
  const char *v10; // r9
  int dwOptions; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  HCERTSTORE v14; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v15; // [rsp+60h] [rbp-A0h] BYREF
  int v16; // [rsp+68h] [rbp-98h]
  _QWORD v17[4]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR SubKey[264]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  std::wstring::wstring(v17, L"TPMCoreProvisioningEKCertificatesECC");
  memset_0(SubKey, 0, 0x208u);
  v16 = 520;
  v0 = v17;
  if ( v17[3] > 7u )
    v0 = (_QWORD *)v17[0];
  RtlGetPersistedStateLocation(v0, 0, L"System\\CurrentControlSet\\Services\\TPM\\WMI\\Endorsement\\EKCertStoreECC", 0);
  v15 = 0;
  hKey = 0;
  v1 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0xF003Fu, 0, &hKey, 0);
  v2 = v1 < 0;
  if ( v1 > 0 )
    v2 = 1;
  if ( v2 )
  {
    v6 = hKey;
    if ( hKey )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v14);
      RegCloseKey(v6);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v14);
    }
    hKey = 0;
    v7 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0x20019u, 0, &hKey, 0);
    v8 = v7 < 0;
    if ( v7 > 0 )
      v8 = 1;
    if ( v8 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xCD,
        (unsigned int)"onecore\\base\\ngscb\\tpmhli\\lib\\ekcert.cpp",
        (const char *)0x80070005LL,
        dwOptions);
    v14 = CertOpenStore((LPCSTR)4, 0, 0, 0x8000u, hKey);
    __4__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CertCloseStoreNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil___wil__QEAAAEAV01___QEAV01__Z(
      &v15,
      &v14);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CertCloseStoreNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v14);
    v5 = v15;
    if ( !v15 )
      wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0xC8, v9, v10);
  }
  else
  {
    v14 = CertOpenStore((LPCSTR)4, 0, 0, 0, hKey);
    __4__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CertCloseStoreNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil___wil__QEAAAEAV01___QEAV01__Z(
      &v15,
      &v14);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CertCloseStoreNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v14);
    v5 = v15;
    if ( !v15 )
      wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0xB3, v3, v4);
  }
  v15 = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CertCloseStoreNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v15);
  std::wstring::~wstring(v17);
  return v5;
}

```

## disassembly

```asm
0x18006d0c0  mov     [rsp-8+arg_0], rbx
0x18006d0c5  push    rbp
0x18006d0c6  lea     rbp, [rsp-1B0h]
0x18006d0ce  sub     rsp, 2B0h
0x18006d0d5  mov     rax, cs:__security_cookie
0x18006d0dc  xor     rax, rsp
0x18006d0df  mov     [rbp+1B0h+var_10], rax
0x18006d0e6  lea     rdx, aTpmcoreprovisi_1; "TPMCoreProvisioningEKCertificatesECC"
0x18006d0ed  lea     rcx, [rsp+2B0h+var_240]
0x18006d0f2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18006d0f7  nop
0x18006d0f8  mov     ebx, 208h
0x18006d0fd  mov     r8d, ebx; Size
0x18006d100  xor     edx, edx; Val
0x18006d102  lea     rcx, [rbp+1B0h+SubKey]; void *
0x18006d106  call    memset_0
0x18006d10b  mov     [rsp+2B0h+var_248], ebx
0x18006d10f  lea     rcx, [rsp+2B0h+var_240]
0x18006d114  cmp     [rbp+1B0h+var_228], 7
0x18006d119  cmova   rcx, [rsp+2B0h+var_240]
0x18006d11f  lea     rax, [rsp+2B0h+var_248]
0x18006d124  mov     [rsp+2B0h+lpSecurityAttributes], rax
0x18006d129  mov     [rsp+2B0h+samDesired], ebx
0x18006d12d  lea     rax, [rbp+1B0h+SubKey]
0x18006d131  mov     qword ptr [rsp+2B0h+dwOptions], rax
0x18006d136  xor     r9d, r9d
0x18006d139  lea     r8, aSystemCurrentc_0; "System\\CurrentControlSet\\Services\\TP"...
0x18006d140  xor     edx, edx
0x18006d142  call    cs:__imp_RtlGetPersistedStateLocation
0x18006d149  nop     dword ptr [rax+rax+00h]
0x18006d14e  mov     [rsp+2B0h+var_250], 0
0x18006d157  mov     [rsp+2B0h+hKey], 0
0x18006d160  mov     [rsp+2B0h+lpdwDisposition], 0; lpdwDisposition
0x18006d169  lea     rax, [rsp+2B0h+hKey]
0x18006d16e  mov     [rsp+2B0h+phkResult], rax; phkResult
0x18006d173  mov     [rsp+2B0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18006d17c  mov     [rsp+2B0h+samDesired], 0F003Fh; samDesired
0x18006d184  mov     [rsp+2B0h+dwOptions], 0; dwOptions
0x18006d18c  xor     r9d, r9d; lpClass
0x18006d18f  xor     r8d, r8d; Reserved
0x18006d192  lea     rdx, [rbp+1B0h+SubKey]; lpSubKey
0x18006d196  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006d19d  call    cs:__imp_RegCreateKeyExW
0x18006d1a4  nop     dword ptr [rax+rax+00h]
0x18006d1a9  test    eax, eax
0x18006d1ab  jle     short loc_18006D1B7
0x18006d1ad  movzx   eax, ax
0x18006d1b0  or      eax, 80070000h
0x18006d1b5  test    eax, eax
0x18006d1b7  js      short loc_18006D218
0x18006d1b9  mov     rax, [rsp+2B0h+hKey]
0x18006d1be  mov     qword ptr [rsp+2B0h+dwOptions], rax; pvPara
0x18006d1c3  xor     r9d, r9d; dwFlags
0x18006d1c6  xor     r8d, r8d; hCryptProv
0x18006d1c9  xor     edx, edx; dwEncodingType
0x18006d1cb  lea     ecx, [rdx+4]; lpszStoreProvider
0x18006d1ce  call    cs:__imp_CertOpenStore
0x18006d1d5  nop     dword ptr [rax+rax+00h]
0x18006d1da  mov     [rsp+2B0h+var_258], rax
0x18006d1df  lea     rdx, [rsp+2B0h+var_258]
0x18006d1e4  lea     rcx, [rsp+2B0h+var_250]
0x18006d1e9  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CertCloseStoreNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z
0x18006d1ee  lea     rcx, [rsp+2B0h+var_258]
0x18006d1f3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CertCloseStoreNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18006d1f8  mov     rcx, [rbp+1B8h]; this
0x18006d1ff  mov     rbx, [rsp+2B0h+var_250]
0x18006d204  test    rbx, rbx
0x18006d207  jnz     loc_18006D309
0x18006d20d  mov     edx, 0B3h; void *
0x18006d212  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18006d218  mov     rbx, [rsp+2B0h+hKey]
0x18006d21d  test    rbx, rbx
0x18006d220  jz      short loc_18006D245
0x18006d222  lea     rcx, [rsp+2B0h+var_258]; this
0x18006d227  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18006d22c  mov     rcx, rbx; hKey
0x18006d22f  call    cs:__imp_RegCloseKey
0x18006d236  nop     dword ptr [rax+rax+00h]
0x18006d23b  lea     rcx, [rsp+2B0h+var_258]; this
0x18006d240  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18006d245  mov     [rsp+2B0h+hKey], 0
0x18006d24e  mov     [rsp+2B0h+lpdwDisposition], 0; lpdwDisposition
0x18006d257  lea     rax, [rsp+2B0h+hKey]
0x18006d25c  mov     [rsp+2B0h+phkResult], rax; phkResult
0x18006d261  mov     [rsp+2B0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18006d26a  mov     [rsp+2B0h+samDesired], 20019h; samDesired
0x18006d272  mov     [rsp+2B0h+dwOptions], 0; int
0x18006d27a  xor     r9d, r9d; lpClass
0x18006d27d  xor     r8d, r8d; Reserved
0x18006d280  lea     rdx, [rbp+1B0h+SubKey]; lpSubKey
0x18006d284  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006d28b  call    cs:__imp_RegCreateKeyExW
0x18006d292  nop     dword ptr [rax+rax+00h]
0x18006d297  test    eax, eax
0x18006d299  jle     short loc_18006D2A5
0x18006d29b  movzx   eax, ax
0x18006d29e  or      eax, 80070000h
0x18006d2a3  test    eax, eax
0x18006d2a5  js      loc_18006D356
0x18006d2ab  mov     rax, [rsp+2B0h+hKey]
0x18006d2b0  mov     qword ptr [rsp+2B0h+dwOptions], rax; pvPara
0x18006d2b5  mov     r9d, 8000h; dwFlags
0x18006d2bb  xor     r8d, r8d; hCryptProv
0x18006d2be  xor     edx, edx; dwEncodingType
0x18006d2c0  lea     ecx, [rdx+4]; lpszStoreProvider
0x18006d2c3  call    cs:__imp_CertOpenStore
0x18006d2ca  nop     dword ptr [rax+rax+00h]
0x18006d2cf  mov     [rsp+2B0h+var_258], rax
0x18006d2d4  lea     rdx, [rsp+2B0h+var_258]
0x18006d2d9  lea     rcx, [rsp+2B0h+var_250]
0x18006d2de  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CertCloseStoreNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z
0x18006d2e3  lea     rcx, [rsp+2B0h+var_258]
0x18006d2e8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CertCloseStoreNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18006d2ed  mov     rcx, [rbp+1B8h]; this
0x18006d2f4  mov     rbx, [rsp+2B0h+var_250]
0x18006d2f9  test    rbx, rbx
0x18006d2fc  jnz     short loc_18006D309
0x18006d2fe  mov     edx, 0C8h; void *
0x18006d303  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18006d309  mov     [rsp+2B0h+var_250], 0
0x18006d312  lea     rcx, [rsp+2B0h+hKey]
0x18006d317  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18006d31c  nop
0x18006d31d  lea     rcx, [rsp+2B0h+var_250]
0x18006d322  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CertCloseStoreNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18006d327  nop
0x18006d328  lea     rcx, [rsp+2B0h+var_240]
0x18006d32d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18006d332  mov     rax, rbx
0x18006d335  mov     rcx, [rbp+1B0h+var_10]
0x18006d33c  xor     rcx, rsp; StackCookie
0x18006d33f  call    __security_check_cookie
0x18006d344  mov     rbx, [rsp+2B0h+arg_0]
0x18006d34c  add     rsp, 2B0h
0x18006d353  pop     rbp
0x18006d354  retn
0x18006d356  mov     rcx, [rbp+1B8h]; this
0x18006d35d  mov     r9d, 80070005h; char *
0x18006d363  lea     r8, aOnecoreBaseNgs_28; "onecore\\base\\ngscb\\tpmhli\\lib\\ekce"...
0x18006d36a  mov     edx, 0CDh; void *
0x18006d36f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
