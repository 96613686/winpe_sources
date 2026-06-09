# Windows::Internal::CapabilityAccess::Private::Globals::RegistryConfig::Initialize(void)

- ea: `0x18002ea0c`
- end: `0x18002eb2e`
- name: `?Initialize@RegistryConfig@Globals@Private@CapabilityAccess@Internal@Windows@@CAXXZ`
- size: `290`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002ecf8`

## callees

- `0x180021550`
- `0x1800236ac`
- `0x180023b38`
- `0x1800282e4`
- `0x180028320`
- `0x18002ea0c`
- `0x18002ede4`
- `0x18002ee78`
- `0x18002f800`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002ea65`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002ea65`

## string_xrefs

- `0x18002ea57`: `Software\Microsoft\Windows\CurrentVersion\CapabilityAccessManager`
- `0x18002eac2`: `PolicyTemplate`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void Windows::Internal::CapabilityAccess::Private::Globals::RegistryConfig::Initialize(void)
{
  unsigned int v0; // eax
  unsigned int Uint32Value; // eax
  bool *dwOptions; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  unsigned __int16 v4; // [rsp+60h] [rbp+8h] BYREF
  HKEY phkResult; // [rsp+68h] [rbp+10h] BYREF

  phkResult = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &phkResult,
    0);
  v0 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\CapabilityAccessManager",
         0,
         0,
         0,
         0x20119u,
         0,
         &phkResult,
         0);
  if ( v0 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x23B,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\synchronizationhelpers.cpp",
      (const char *)v0,
      (unsigned int)dwOptions);
  Windows::Internal::CapabilityAccess::Private::Globals::RegistryConfig::m_isFirstBoot = Windows::Internal::CapabilityAccess::Private::Globals::RegistryConfig::IsFirstBoot(&phkResult);
  Windows::Internal::CapabilityAccess::Private::Globals::RegistryConfig::m_enforceRestrictedExceptions = Windows::Internal::CapabilityAccess::Private::Globals::RegistryConfig::IsRestrictedExceptionsPolicyApplied(&phkResult);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CM_OneClick>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CM_OneClick>::GetImpl'::`2'::impl)
    || (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAM_AgenticSessionsBaseline>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CAM_AgenticSessionsBaseline>::GetImpl'::`2'::impl) )
  {
    LOBYTE(v4) = 0;
    Uint32Value = Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(
                    (Windows::Internal::CapabilityAccess::Private *)phkResult,
                    (HKEY)&stru_180055278,
                    L"PolicyTemplate",
                    &v4,
                    dwOptions);
    Windows::Internal::CapabilityAccess::Private::Globals::RegistryConfig::m_policyTemplate = (_BYTE)v4 != 0
                                                                                            ? Uint32Value
                                                                                            : 0;
  }
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CM_OneClick>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CM_OneClick>::GetImpl'::`2'::impl) )
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAM_AgenticSessionsBaseline>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CAM_AgenticSessionsBaseline>::GetImpl'::`2'::impl);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
}

```

## disassembly

```asm
0x18002ea0c  sub     rsp, 58h
0x18002ea10  mov     [rsp+58h+arg_8], 0
0x18002ea19  xor     edx, edx
0x18002ea1b  lea     rcx, [rsp+58h+arg_8]
0x18002ea20  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18002ea25  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x18002ea2e  lea     rax, [rsp+58h+arg_8]
0x18002ea33  mov     [rsp+58h+phkResult], rax; phkResult
0x18002ea38  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18002ea41  mov     [rsp+58h+samDesired], 20119h; samDesired
0x18002ea49  mov     dword ptr [rsp+58h+dwOptions], 0; unsigned int
0x18002ea51  xor     r9d, r9d; lpClass
0x18002ea54  xor     r8d, r8d; Reserved
0x18002ea57  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18002ea5e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002ea65  call    cs:__imp_RegCreateKeyExW
0x18002ea6b  mov     rcx, [rsp+58h]; this
0x18002ea70  test    eax, eax
0x18002ea72  jnz     loc_18002EB19
0x18002ea78  lea     rcx, [rsp+58h+arg_8]
0x18002ea7d  call    ?IsFirstBoot@RegistryConfig@Globals@Private@CapabilityAccess@Internal@Windows@@CA_NAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Windows::Internal::CapabilityAccess::Private::Globals::RegistryConfig::IsFirstBoot(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &)
0x18002ea82  mov     cs:?m_isFirstBoot@RegistryConfig@Globals@Private@CapabilityAccess@Internal@Windows@@0_NA, al; bool Windows::Internal::CapabilityAccess::Private::Globals::RegistryConfig::m_isFirstBoot
0x18002ea88  lea     rcx, [rsp+58h+arg_8]
0x18002ea8d  call    ?IsRestrictedExceptionsPolicyApplied@RegistryConfig@Globals@Private@CapabilityAccess@Internal@Windows@@SA_NAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Windows::Internal::CapabilityAccess::Private::Globals::RegistryConfig::IsRestrictedExceptionsPolicyApplied(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &)
0x18002ea92  mov     cs:?m_enforceRestrictedExceptions@RegistryConfig@Globals@Private@CapabilityAccess@Internal@Windows@@0_NA, al; bool Windows::Internal::CapabilityAccess::Private::Globals::RegistryConfig::m_enforceRestrictedExceptions
0x18002ea98  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CM_OneClick@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CM_OneClick@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CM_OneClick> `wil::Feature<__WilFeatureTraits_Feature_CM_OneClick>::GetImpl(void)'::`2'::impl
0x18002ea9f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CM_OneClick@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CM_OneClick>::__private_IsEnabled(void)
0x18002eaa4  test    al, al
0x18002eaa6  jnz     short loc_18002EAB8
0x18002eaa8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CAM_AgenticSessionsBaseline@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CAM_AgenticSessionsBaseline@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAM_AgenticSessionsBaseline> `wil::Feature<__WilFeatureTraits_Feature_CAM_AgenticSessionsBaseline>::GetImpl(void)'::`2'::impl
0x18002eaaf  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CAM_AgenticSessionsBaseline@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAM_AgenticSessionsBaseline>::__private_IsEnabled(void)
0x18002eab4  test    al, al
0x18002eab6  jz      short loc_18002EAED
0x18002eab8  mov     byte ptr [rsp+58h+arg_0], 0
0x18002eabd  lea     r9, [rsp+58h+arg_0]; unsigned __int16 *
0x18002eac2  lea     r8, aPolicytemplate; "PolicyTemplate"
0x18002eac9  lea     rdx, stru_180055278; HKEY
0x18002ead0  mov     rcx, [rsp+58h+arg_8]; this
0x18002ead5  call    ?RegGetUint32Value@Private@CapabilityAccess@Internal@Windows@@YAIPEAUHKEY__@@PEBG1PEA_N@Z; Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(HKEY__ *,ushort const *,ushort const *,bool *)
0x18002eada  mov     dl, byte ptr [rsp+58h+arg_0]
0x18002eade  neg     dl
0x18002eae0  sbb     r8d, r8d
0x18002eae3  and     r8d, eax
0x18002eae6  mov     cs:?m_policyTemplate@RegistryConfig@Globals@Private@CapabilityAccess@Internal@Windows@@0IA, r8d; uint Windows::Internal::CapabilityAccess::Private::Globals::RegistryConfig::m_policyTemplate
0x18002eaed  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CM_OneClick@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CM_OneClick@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CM_OneClick> `wil::Feature<__WilFeatureTraits_Feature_CM_OneClick>::GetImpl(void)'::`2'::impl
0x18002eaf4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CM_OneClick@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CM_OneClick>::__private_IsEnabled(void)
0x18002eaf9  test    al, al
0x18002eafb  jnz     short loc_18002EB0A
0x18002eafd  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CAM_AgenticSessionsBaseline@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CAM_AgenticSessionsBaseline@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAM_AgenticSessionsBaseline> `wil::Feature<__WilFeatureTraits_Feature_CAM_AgenticSessionsBaseline>::GetImpl(void)'::`2'::impl
0x18002eb04  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CAM_AgenticSessionsBaseline@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAM_AgenticSessionsBaseline>::__private_IsEnabled(void)
0x18002eb09  nop
0x18002eb0a  lea     rcx, [rsp+58h+arg_8]
0x18002eb0f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002eb14  add     rsp, 58h
0x18002eb18  retn
0x18002eb19  mov     r9d, eax; char *
0x18002eb1c  lea     r8, aOnecoreBaseDev_3; "onecore\\base\\devices\\cam\\core\\sync"...
0x18002eb23  mov     edx, 23Bh; void *
0x18002eb28  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
