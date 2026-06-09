# GetEkCertStore(TpmAlgID)

- ea: `0x1800454ec`
- end: `0x180045757`
- name: `?GetEkCertStore@@YAPEAXW4TpmAlgID@@@Z`
- size: `619`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180045760`

## callees

- `0x1800078b0`
- `0x1800085d4`
- `0x18000d06c`
- `0x18000d524`
- `0x18000e48c`
- `0x180023634`
- `0x18002386c`
- `0x180024780`
- `0x180034138`
- `0x180044520`
- `0x180045160`
- `0x1800454ec`
- `0x180045948`

## import_xrefs

- `ntdll!RtlGetPersistedStateLocation` at `0x18004556b`
- `ntdll!RtlGetPersistedStateLocation` at `0x18004556b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800455c5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180045672`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800455c5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180045672`
- `CRYPT32!CertOpenStore` at `0x1800455f2`
- `CRYPT32!CertOpenStore` at `0x1800456a1`
- `CRYPT32!CertOpenStore` at `0x1800455f2`
- `CRYPT32!CertOpenStore` at `0x1800456a1`

## string_xrefs

- `0x180045562`: `System\CurrentControlSet\Services\TPM\WMI\Endorsement\EKCertStore`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 GetEkCertStore()
{
  __int64 v0; // rax
  HKEY *phkResult; // rax
  LSTATUS Key; // eax
  bool v3; // sf
  unsigned int v4; // r8d
  const char *v5; // r9
  __int64 v6; // rbx
  HKEY *v7; // rax
  LSTATUS v8; // eax
  bool v9; // sf
  unsigned int v10; // r8d
  const char *v11; // r9
  unsigned int v13; // eax
  unsigned int v14; // r8d
  int dwOptions; // [rsp+20h] [rbp-E0h]
  __int64 v16; // [rsp+50h] [rbp-B0h] BYREF
  void *pvPara; // [rsp+58h] [rbp-A8h] BYREF
  HCERTSTORE v18; // [rsp+60h] [rbp-A0h] BYREF
  int v19; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v20[32]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR SubKey[264]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  std::wstring::wstring((__int64)v20, (__int64)L"TPMCoreProvisioningEKCertificates");
  memset_0(SubKey, 0, 0x208u);
  v19 = 520;
  v0 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v20);
  RtlGetPersistedStateLocation(
    v0,
    0,
    L"System\\CurrentControlSet\\Services\\TPM\\WMI\\Endorsement\\EKCertStore",
    0,
    SubKey,
    520,
    &v19);
  v16 = 0;
  pvPara = 0;
  phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&pvPara);
  Key = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0xF003Fu, 0, phkResult, 0);
  v3 = Key < 0;
  if ( Key > 0 )
    v3 = 1;
  if ( v3 )
  {
    v7 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&pvPara);
    v8 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0x20019u, 0, v7, 0);
    v9 = v8 < 0;
    if ( v8 > 0 )
      v9 = 1;
    if ( v9 )
    {
      v13 = wil::verify_hresult<long>(2147942405LL);
      wil::details::in1diag3::Throw_Hr(retaddr, (void *)0xCD, v14, (const char *)v13, dwOptions);
    }
    v18 = CertOpenStore((LPCSTR)4, 0, 0, 0x8000u, pvPara);
    __4__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CertCloseStoreNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil___wil__QEAAAEAV01___QEAV01__Z(
      &v16,
      &v18);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CertCloseStoreNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v18);
    v6 = v16;
    if ( !v16 )
      wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0xC8, v10, v11);
  }
  else
  {
    v18 = CertOpenStore((LPCSTR)4, 0, 0, 0, pvPara);
    __4__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CertCloseStoreNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil___wil__QEAAAEAV01___QEAV01__Z(
      &v16,
      &v18);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CertCloseStoreNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v18);
    v6 = v16;
    if ( !v16 )
      wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0xB3, v4, v5);
  }
  v16 = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>((HKEY *)&pvPara);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CertCloseStoreNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v16);
  std::wstring::_Tidy_deallocate(v20);
  return v6;
}

```

## disassembly

```asm
0x1800454ec  mov     [rsp-8+arg_0], rbx
0x1800454f1  push    rbp
0x1800454f2  lea     rbp, [rsp-1B0h]
0x1800454fa  sub     rsp, 2B0h
0x180045501  mov     rax, cs:__security_cookie
0x180045508  xor     rax, rsp
0x18004550b  mov     [rbp+1B0h+var_10], rax
0x180045512  lea     rdx, aTpmcoreprovisi_1; "TPMCoreProvisioningEKCertificates"
0x180045519  lea     rcx, [rsp+2B0h+var_240]
0x18004551e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180045523  nop
0x180045524  mov     ebx, 208h
0x180045529  mov     r8d, ebx; Size
0x18004552c  xor     edx, edx; Val
0x18004552e  lea     rcx, [rbp+1B0h+SubKey]; void *
0x180045532  call    memset_0
0x180045537  mov     [rsp+2B0h+var_248], ebx
0x18004553b  lea     rcx, [rsp+2B0h+var_240]
0x180045540  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180045545  mov     rcx, rax
0x180045548  lea     rax, [rsp+2B0h+var_248]
0x18004554d  mov     [rsp+2B0h+lpSecurityAttributes], rax
0x180045552  mov     [rsp+2B0h+samDesired], ebx
0x180045556  lea     rax, [rbp+1B0h+SubKey]
0x18004555a  mov     qword ptr [rsp+2B0h+dwOptions], rax
0x18004555f  xor     r9d, r9d
0x180045562  lea     r8, aSystemCurrentc_11; "System\\CurrentControlSet\\Services\\TP"...
0x180045569  xor     edx, edx
0x18004556b  call    cs:__imp_RtlGetPersistedStateLocation
0x180045571  mov     [rsp+2B0h+var_260], 0
0x18004557a  mov     [rsp+2B0h+pvPara], 0
0x180045583  lea     rcx, [rsp+2B0h+pvPara]
0x180045588  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x18004558d  mov     [rsp+2B0h+lpdwDisposition], 0; lpdwDisposition
0x180045596  mov     [rsp+2B0h+phkResult], rax; phkResult
0x18004559b  mov     [rsp+2B0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800455a4  mov     [rsp+2B0h+samDesired], 0F003Fh; samDesired
0x1800455ac  mov     [rsp+2B0h+dwOptions], 0; dwOptions
0x1800455b4  xor     r9d, r9d; lpClass
0x1800455b7  xor     r8d, r8d; Reserved
0x1800455ba  lea     rdx, [rbp+1B0h+SubKey]; lpSubKey
0x1800455be  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800455c5  call    cs:__imp_RegCreateKeyExW
0x1800455cb  mov     ebx, 80070000h
0x1800455d0  test    eax, eax
0x1800455d2  jle     short loc_1800455DB
0x1800455d4  movzx   eax, ax
0x1800455d7  or      eax, ebx
0x1800455d9  test    eax, eax
0x1800455db  js      short loc_180045630
0x1800455dd  mov     rax, [rsp+2B0h+pvPara]
0x1800455e2  mov     qword ptr [rsp+2B0h+dwOptions], rax; pvPara
0x1800455e7  xor     r9d, r9d; dwFlags
0x1800455ea  xor     r8d, r8d; hCryptProv
0x1800455ed  xor     edx, edx; dwEncodingType
0x1800455ef  lea     ecx, [rdx+4]; lpszStoreProvider
0x1800455f2  call    cs:__imp_CertOpenStore
0x1800455f8  mov     [rsp+2B0h+var_250], rax
0x1800455fd  lea     rdx, [rsp+2B0h+var_250]
0x180045602  lea     rcx, [rsp+2B0h+var_260]
0x180045607  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CertCloseStoreNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z
0x18004560c  lea     rcx, [rsp+2B0h+var_250]
0x180045611  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CertCloseStoreNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180045616  mov     rcx, [rbp+1B8h]; this
0x18004561d  mov     rbx, [rsp+2B0h+var_260]
0x180045622  test    rbx, rbx
0x180045625  jz      loc_18004572D
0x18004562b  jmp     loc_1800456D6
0x180045630  lea     rcx, [rsp+2B0h+pvPara]
0x180045635  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x18004563a  mov     [rsp+2B0h+lpdwDisposition], 0; lpdwDisposition
0x180045643  mov     [rsp+2B0h+phkResult], rax; phkResult
0x180045648  mov     [rsp+2B0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180045651  mov     [rsp+2B0h+samDesired], 20019h; samDesired
0x180045659  mov     [rsp+2B0h+dwOptions], 0; int
0x180045661  xor     r9d, r9d; lpClass
0x180045664  xor     r8d, r8d; Reserved
0x180045667  lea     rdx, [rbp+1B0h+SubKey]; lpSubKey
0x18004566b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180045672  call    cs:__imp_RegCreateKeyExW
0x180045678  test    eax, eax
0x18004567a  jle     short loc_180045683
0x18004567c  movzx   eax, ax
0x18004567f  or      eax, ebx
0x180045681  test    eax, eax
0x180045683  js      loc_180045738
0x180045689  mov     rax, [rsp+2B0h+pvPara]
0x18004568e  mov     qword ptr [rsp+2B0h+dwOptions], rax; pvPara
0x180045693  mov     r9d, 8000h; dwFlags
0x180045699  xor     r8d, r8d; hCryptProv
0x18004569c  xor     edx, edx; dwEncodingType
0x18004569e  lea     ecx, [rdx+4]; lpszStoreProvider
0x1800456a1  call    cs:__imp_CertOpenStore
0x1800456a7  mov     [rsp+2B0h+var_250], rax
0x1800456ac  lea     rdx, [rsp+2B0h+var_250]
0x1800456b1  lea     rcx, [rsp+2B0h+var_260]
0x1800456b6  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CertCloseStoreNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z
0x1800456bb  lea     rcx, [rsp+2B0h+var_250]
0x1800456c0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CertCloseStoreNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800456c5  mov     rcx, [rbp+1B8h]; this
0x1800456cc  mov     rbx, [rsp+2B0h+var_260]
0x1800456d1  test    rbx, rbx
0x1800456d4  jz      short loc_180045722
0x1800456d6  mov     [rsp+2B0h+var_260], 0
0x1800456df  lea     rcx, [rsp+2B0h+pvPara]
0x1800456e4  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800456e9  nop
0x1800456ea  lea     rcx, [rsp+2B0h+var_260]
0x1800456ef  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CertCloseStoreNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800456f4  nop
0x1800456f5  lea     rcx, [rsp+2B0h+var_240]
0x1800456fa  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800456ff  mov     rax, rbx
0x180045702  mov     rcx, [rbp+1B0h+var_10]
0x180045709  xor     rcx, rsp; StackCookie
0x18004570c  call    __security_check_cookie
0x180045711  mov     rbx, [rsp+2B0h+arg_0]
0x180045719  add     rsp, 2B0h
0x180045720  pop     rbp
0x180045721  retn
0x180045722  mov     edx, 0C8h; void *
0x180045727  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18004572d  mov     edx, 0B3h; void *
0x180045732  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180045738  mov     ecx, 80070005h
0x18004573d  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180045742  mov     r9d, eax; char *
0x180045745  mov     rcx, [rbp+1B8h]; this
0x18004574c  mov     edx, 0CDh; void *
0x180045751  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
