# SystemSettings::SecureAssessment::SetTemporarySingleAppSid(ushort const *)

- ea: `0x14006bb9c`
- end: `0x14006bccb`
- name: `?SetTemporarySingleAppSid@SecureAssessment@SystemSettings@@YAJPEBG@Z`
- size: `303`
- prototype: `__int64 __fastcall(SystemSettings::SecureAssessment *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14006a198`

## callees

- `0x14000ed38`
- `0x14001f3f8`
- `0x140069eb0`
- `0x14006bb9c`
- `0x14006bcd4`

## import_xrefs

- `KERNEL32!RegCreateKeyExW` at `0x14006bc19`
- `KERNEL32!RegCreateKeyExW` at `0x14006bc58`
- `KERNEL32!RegCreateKeyExW` at `0x14006bc19`
- `KERNEL32!RegCreateKeyExW` at `0x14006bc58`
- `KERNEL32!RegSetValueExW` at `0x14006bc9c`
- `KERNEL32!RegSetValueExW` at `0x14006bc9c`

## string_xrefs

- `0x14006bc91`: `TemporaryUserSid`
- `0x14006bc0b`: `Software\Microsoft\Windows\AssignedAccessSettingsPage`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::SecureAssessment::SetTemporarySingleAppSid(
        SystemSettings::SecureAssessment *this,
        const unsigned __int16 *a2)
{
  unsigned int v2; // ebx
  __int64 v3; // rdx
  const char *v4; // r9
  unsigned int v5; // ebx
  unsigned int v6; // eax
  unsigned int dwOptions; // [rsp+20h] [rbp-50h]
  HKEY *p_hKey; // [rsp+50h] [rbp-20h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-18h] BYREF
  char v11; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+8h]
  DWORD dwDisposition; // [rsp+80h] [rbp+10h] BYREF
  int v14; // [rsp+84h] [rbp+14h]
  HKEY hKey; // [rsp+88h] [rbp+18h] BYREF

  v14 = HIDWORD(this);
  hKey = 0;
  dwDisposition = 0;
  phkResult = 0;
  v11 = 1;
  p_hKey = &hKey;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UnblockingTestTakingInAdminless>::__private_IsEnabled(
                          `wil::Feature<__WilFeatureTraits_Feature_UnblockingTestTakingInAdminless>::GetImpl'::`2'::impl,
                          a2) )
  {
    v2 = RegCreateKeyExW(
           HKEY_LOCAL_MACHINE,
           L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\SecureAssessment",
           0,
           0,
           0,
           0xF003Fu,
           0,
           &phkResult,
           &dwDisposition);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
    if ( v2 )
    {
      v3 = 51;
      goto LABEL_4;
    }
  }
  else
  {
    v2 = RegCreateKeyExW(
           HKEY_CURRENT_USER,
           L"Software\\Microsoft\\Windows\\AssignedAccessSettingsPage",
           0,
           0,
           0,
           0xF003Fu,
           0,
           &phkResult,
           &dwDisposition);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
    if ( v2 )
    {
      v3 = 55;
LABEL_4:
      v4 = (const char *)v2;
      goto LABEL_5;
    }
  }
  v6 = RegSetValueExW(hKey, L"TemporaryUserSid", 0, 1u, (const BYTE *)&Data, 2u);
  if ( !v6 )
  {
    v5 = 0;
    goto LABEL_11;
  }
  v4 = (const char *)v6;
  v3 = 58;
LABEL_5:
  v5 = wil::details::in1diag3::Return_Win32(
         retaddr,
         (void *)v3,
         (unsigned int)"admin\\edu\\secureassessment\\ux\\secureassessmenthandlers\\adminflow\\SecureAssessmentAdminFlowHandler.h",
         v4,
         dwOptions);
LABEL_11:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return v5;
}

```

## disassembly

```asm
0x14006bb9c  mov     [rsp-8+arg_10], rbx
0x14006bba1  mov     qword ptr [rsp-8+dwDisposition], rcx
0x14006bba6  push    rbp
0x14006bba7  mov     rbp, rsp
0x14006bbaa  sub     rsp, 70h
0x14006bbae  mov     [rbp+hKey], 0
0x14006bbb6  mov     [rbp+dwDisposition], 0
0x14006bbbd  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UnblockingTestTakingInAdminless@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UnblockingTestTakingInAdminless@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UnblockingTestTakingInAdminless> `wil::Feature<__WilFeatureTraits_Feature_UnblockingTestTakingInAdminless>::GetImpl(void)'::`2'::impl
0x14006bbc4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UnblockingTestTakingInAdminless@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UnblockingTestTakingInAdminless>::__private_IsEnabled(void)
0x14006bbc9  mov     [rbp+var_18], 0
0x14006bbd1  mov     [rbp+var_10], 1
0x14006bbd5  xor     r9d, r9d; lpClass
0x14006bbd8  xor     r8d, r8d; Reserved
0x14006bbdb  test    al, al
0x14006bbdd  lea     rax, [rbp+hKey]
0x14006bbe1  mov     [rbp+var_20], rax
0x14006bbe5  lea     rax, [rbp+dwDisposition]
0x14006bbe9  mov     [rsp+70h+lpdwDisposition], rax; lpdwDisposition
0x14006bbee  lea     rax, [rbp+var_18]
0x14006bbf2  mov     [rsp+70h+phkResult], rax; phkResult
0x14006bbf7  mov     [rsp+70h+lpSecurityAttributes], r8; lpSecurityAttributes
0x14006bbfc  mov     [rsp+70h+samDesired], 0F003Fh; samDesired
0x14006bc04  mov     [rsp+70h+dwOptions], r8d; unsigned int
0x14006bc09  jnz     short loc_14006BC4A
0x14006bc0b  lea     rdx, ?c_temporaryStoreKeyPath@@3QBGB; "Software\\Microsoft\\Windows\\AssignedA"...
0x14006bc12  mov     rcx, 0FFFFFFFF80000001h; hKey
0x14006bc19  call    cs:__imp_RegCreateKeyExW
0x14006bc1f  mov     ebx, eax
0x14006bc21  lea     rcx, [rbp+var_20]
0x14006bc25  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x14006bc2a  test    ebx, ebx
0x14006bc2c  jz      short loc_14006BC74
0x14006bc2e  mov     edx, 37h ; '7'; void *
0x14006bc33  mov     r9d, ebx; char *
0x14006bc36  mov     rcx, [rbp+8]; this
0x14006bc3a  lea     r8, aAdminEduSecure_1; "admin\\edu\\secureassessment\\ux\\secur"...
0x14006bc41  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x14006bc46  mov     ebx, eax
0x14006bc48  jmp     short loc_14006BCB2
0x14006bc4a  lea     rdx, ?c_temporaryStoreKeyPathAdminless@@3QBGB; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x14006bc51  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14006bc58  call    cs:__imp_RegCreateKeyExW
0x14006bc5e  mov     ebx, eax
0x14006bc60  lea     rcx, [rbp+var_20]
0x14006bc64  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x14006bc69  test    ebx, ebx
0x14006bc6b  jz      short loc_14006BC74
0x14006bc6d  mov     edx, 33h ; '3'
0x14006bc72  jmp     short loc_14006BC33
0x14006bc74  mov     [rsp+70h+samDesired], 2; cbData
0x14006bc7c  lea     rax, Data
0x14006bc83  mov     qword ptr [rsp+70h+dwOptions], rax; lpData
0x14006bc88  mov     r9d, 1; dwType
0x14006bc8e  xor     r8d, r8d; Reserved
0x14006bc91  lea     rdx, ?c_temporaryStoreUserSidValueName@@3QBGB; "TemporaryUserSid"
0x14006bc98  mov     rcx, [rbp+hKey]; hKey
0x14006bc9c  call    cs:__imp_RegSetValueExW
0x14006bca2  test    eax, eax
0x14006bca4  jz      short loc_14006BCB0
0x14006bca6  mov     r9d, eax
0x14006bca9  mov     edx, 3Ah ; ':'
0x14006bcae  jmp     short loc_14006BC36
0x14006bcb0  xor     ebx, ebx
0x14006bcb2  lea     rcx, [rbp+hKey]
0x14006bcb6  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x14006bcbb  mov     eax, ebx
0x14006bcbd  mov     rbx, [rsp+70h+arg_10]
0x14006bcc5  add     rsp, 70h
0x14006bcc9  pop     rbp
0x14006bcca  retn
```
