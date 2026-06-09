# Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicy(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18002b8c0`
- end: `0x18002baae`
- name: `?ReadPolicy@CapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@QEBA?AV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@7@0@Z`
- size: `494`
- prototype: `HKEY __fastcall(__int64, HKEY, __int64, __int64)`
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180029960`
- `0x18002bab4`

## callees

- `0x18001c330`
- `0x180021550`
- `0x18002166c`
- `0x1800222c8`
- `0x180023074`
- `0x1800236ac`
- `0x180023b38`
- `0x180024aa4`
- `0x18002a438`
- `0x18002b8c0`
- `0x18002c710`
- `0x18002caac`
- `0x18002ee78`
- `0x180032a6c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002b9fc`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002b9fc`

## string_xrefs

- `0x18002b9ee`: `Software\Microsoft\Windows\CurrentVersion\CapabilityAccessManager`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
HKEY __fastcall Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicy(
        __int64 a1,
        HKEY a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v5; // rbx
  HKEY v6; // rdi
  __int64 Policy; // rax
  std::_Ref_count_base *v9; // rcx
  std::_Ref_count_base *v10; // rsi
  __int64 v11; // rax
  __int64 v12; // rdx
  __int64 v13; // r8
  unsigned int v14; // eax
  _QWORD *i; // rbx
  DWORD dwOptions; // [rsp+20h] [rbp-39h]
  HKEY phkResult; // [rsp+50h] [rbp-9h] BYREF
  std::_Ref_count_base *v19; // [rsp+58h] [rbp-1h]
  std::_Ref_count_base *v20[2]; // [rsp+60h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  v5 = a3;
  v6 = a2;
  phkResult = a2;
  *(_OWORD *)v20 = 0;
  LOBYTE(a3) = 3;
  LOBYTE(a2) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAM_CUASupport>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_CAM_CUASupport>::GetImpl'::`2'::impl,
    a2,
    a3);
  Policy = Windows::Internal::CapabilityAccess::Private::ModernPolicy::PolicyManager::GetPolicy(&phkResult, v5);
  std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityHandler>::operator=(v20, Policy);
  v9 = v19;
  if ( v19 )
    std::_Ref_count_base::_Decref(v19);
  v10 = v20[0];
  if ( v20[0] )
    goto LABEL_26;
  v11 = Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadLegacyPolicyFromRegistry(
          a1,
          &phkResult,
          v5);
  std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityHandler>::operator=(v20, v11);
  v9 = v19;
  if ( v19 )
    std::_Ref_count_base::_Decref(v19);
  v10 = v20[0];
  if ( v20[0] )
  {
LABEL_26:
    if ( Windows::Internal::CapabilityAccess::Private::IsCTARegionActive(v9) )
    {
      *((std::_Ref_count_base **)v6 + 1) = v20[1];
LABEL_9:
      *(_QWORD *)v6 = v10;
      return v6;
    }
    LOBYTE(v13) = 3;
    LOBYTE(v12) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAM_CUASupport>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_CAM_CUASupport>::GetImpl'::`2'::impl,
      v12,
      v13);
    if ( !*(_QWORD *)(a4 + 16) )
    {
      std::_Hash<std::_Umap_traits<std::wstring,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy>>,0>>::clear((char *)v10 + 168);
      *((std::_Ref_count_base **)v6 + 1) = v20[1];
      goto LABEL_9;
    }
    phkResult = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &phkResult,
      0);
    v14 = RegCreateKeyExW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\CapabilityAccessManager",
            0,
            0,
            0,
            0x20119u,
            0,
            &phkResult,
            0);
    if ( v14 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x32F,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilitypolicystore.cpp",
        (const char *)v14,
        dwOptions);
    if ( (unsigned __int8)Windows::Internal::CapabilityAccess::Private::Globals::RegistryConfig::IsRestrictedExceptionsPolicyApplied(&phkResult) )
    {
      i = (_QWORD *)*((_QWORD *)v10 + 22);
LABEL_15:
      for ( i = (_QWORD *)*i;
            i != *((_QWORD **)v10 + 22);
            i = (_QWORD *)std::_Hash<std::_Umap_traits<std::wstring,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy>>,0>>::_Unchecked_erase(
                            (char *)v10 + 168,
                            i) )
      {
        if ( (unsigned int)Windows::Internal::CapabilityAccess::Private::GetPackageComplianceClassification(i + 2, a4) == 2 )
          goto LABEL_15;
      }
    }
    *(_QWORD *)v6 = v10;
    *((std::_Ref_count_base **)v6 + 1) = v20[1];
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  }
  else
  {
    *(_QWORD *)v6 = 0;
    *((_QWORD *)v6 + 1) = 0;
    if ( v20[1] )
      std::_Ref_count_base::_Decref(v20[1]);
  }
  return v6;
}

```

## disassembly

```asm
0x18002b8c0  push    rbp
0x18002b8c2  push    rbx
0x18002b8c3  push    rsi
0x18002b8c4  push    rdi
0x18002b8c5  push    r14
0x18002b8c7  push    r15
0x18002b8c9  lea     rbp, [rsp-2Fh]
0x18002b8ce  sub     rsp, 88h
0x18002b8d5  mov     r15, r9
0x18002b8d8  mov     rbx, r8
0x18002b8db  mov     rdi, rdx
0x18002b8de  mov     r14, rcx
0x18002b8e1  mov     [rbp+57h+var_60], rdx
0x18002b8e5  xorps   xmm0, xmm0
0x18002b8e8  movdqu  xmmword ptr [rbp+57h+var_50], xmm0
0x18002b8ed  mov     r8b, 3
0x18002b8f0  mov     dl, 1
0x18002b8f2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CAM_CUASupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CAM_CUASupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAM_CUASupport> `wil::Feature<__WilFeatureTraits_Feature_CAM_CUASupport>::GetImpl(void)'::`2'::impl
0x18002b8f9  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_CAM_CUASupport@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAM_CUASupport>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18002b8fe  mov     rdx, rbx
0x18002b901  lea     rcx, [rbp+57h+var_60]
0x18002b905  call    ?GetPolicy@PolicyManager@ModernPolicy@Private@CapabilityAccess@Internal@Windows@@SA?AV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@8@@Z; Windows::Internal::CapabilityAccess::Private::ModernPolicy::PolicyManager::GetPolicy(std::wstring const &)
0x18002b90a  mov     rdx, rax
0x18002b90d  lea     rcx, [rbp+57h+var_50]
0x18002b911  call    ??4?$shared_ptr@VCapabilityHandler@Private@CapabilityAccess@Internal@Windows@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityHandler>::operator=(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityHandler> &&)
0x18002b916  mov     rcx, [rbp+57h+var_58]; this
0x18002b91a  test    rcx, rcx
0x18002b91d  jz      short loc_18002B924
0x18002b91f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002b924  mov     rsi, [rbp+57h+var_50]
0x18002b928  test    rsi, rsi
0x18002b92b  jnz     short loc_18002B963
0x18002b92d  mov     r8, rbx
0x18002b930  lea     rdx, [rbp+57h+var_60]
0x18002b934  mov     rcx, r14
0x18002b937  call    ?ReadLegacyPolicyFromRegistry@CapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@QEBA?AV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@7@@Z; Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadLegacyPolicyFromRegistry(std::wstring const &)
0x18002b93c  mov     rdx, rax
0x18002b93f  lea     rcx, [rbp+57h+var_50]
0x18002b943  call    ??4?$shared_ptr@VCapabilityHandler@Private@CapabilityAccess@Internal@Windows@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityHandler>::operator=(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityHandler> &&)
0x18002b948  mov     rcx, [rbp+57h+var_58]; this
0x18002b94c  test    rcx, rcx
0x18002b94f  jz      short loc_18002B956
0x18002b951  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002b956  mov     rsi, [rbp+57h+var_50]
0x18002b95a  test    rsi, rsi
0x18002b95d  jz      loc_18002BA69
0x18002b963  call    ?IsCTARegionActive@Private@CapabilityAccess@Internal@Windows@@YA_NXZ; Windows::Internal::CapabilityAccess::Private::IsCTARegionActive(void)
0x18002b968  test    al, al
0x18002b96a  jz      short loc_18002B97C
0x18002b96c  mov     rcx, [rbp+57h+var_50+8]
0x18002b970  mov     [rdi+8], rcx
0x18002b974  mov     [rdi], rsi
0x18002b977  jmp     loc_18002BA86
0x18002b97c  mov     r8b, 3
0x18002b97f  mov     dl, 1
0x18002b981  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CAM_CUASupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CAM_CUASupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAM_CUASupport> `wil::Feature<__WilFeatureTraits_Feature_CAM_CUASupport>::GetImpl(void)'::`2'::impl
0x18002b988  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_CAM_CUASupport@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAM_CUASupport>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18002b98d  cmp     qword ptr [r15+10h], 0
0x18002b992  jnz     short loc_18002B9AA
0x18002b994  lea     rcx, [rsi+0A8h]
0x18002b99b  call    ?clear@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VCapabilityAppPolicy@Private@CapabilityAccess@Internal@Windows@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VCapabilityAppPolicy@Private@CapabilityAccess@Internal@Windows@@@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Hash<std::_Umap_traits<std::wstring,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy>>,0>>::clear(void)
0x18002b9a0  mov     rax, [rbp+57h+var_50+8]
0x18002b9a4  mov     [rdi+8], rax
0x18002b9a8  jmp     short loc_18002B974
0x18002b9aa  mov     [rbp+57h+var_60], 0
0x18002b9b2  xor     edx, edx
0x18002b9b4  lea     rcx, [rbp+57h+var_60]
0x18002b9b8  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18002b9bd  mov     [rsp+0B0h+lpdwDisposition], 0; lpdwDisposition
0x18002b9c6  lea     rax, [rbp+57h+var_60]
0x18002b9ca  mov     [rsp+0B0h+phkResult], rax; phkResult
0x18002b9cf  mov     [rsp+0B0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18002b9d8  mov     [rsp+0B0h+samDesired], 20119h; samDesired
0x18002b9e0  mov     [rsp+0B0h+dwOptions], 0; unsigned int
0x18002b9e8  xor     r9d, r9d; lpClass
0x18002b9eb  xor     r8d, r8d; Reserved
0x18002b9ee  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18002b9f5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002b9fc  call    cs:__imp_RegCreateKeyExW
0x18002ba02  mov     rcx, [rbp+5Fh]; this
0x18002ba06  test    eax, eax
0x18002ba08  jnz     loc_18002BA99
0x18002ba0e  lea     rcx, [rbp+57h+var_60]
0x18002ba12  call    ?IsRestrictedExceptionsPolicyApplied@RegistryConfig@Globals@Private@CapabilityAccess@Internal@Windows@@SA_NAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Windows::Internal::CapabilityAccess::Private::Globals::RegistryConfig::IsRestrictedExceptionsPolicyApplied(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &)
0x18002ba17  test    al, al
0x18002ba19  jz      short loc_18002BA50
0x18002ba1b  lea     r14, [rsi+0A8h]
0x18002ba22  mov     rbx, [r14+8]
0x18002ba26  mov     rbx, [rbx]
0x18002ba29  cmp     rbx, [r14+8]
0x18002ba2d  jz      short loc_18002BA50
0x18002ba2f  lea     rcx, [rbx+10h]
0x18002ba33  mov     rdx, r15
0x18002ba36  call    ?GetPackageComplianceClassification@Private@CapabilityAccess@Internal@Windows@@YA?AW4PackageComplianceClassification@1234@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; Windows::Internal::CapabilityAccess::Private::GetPackageComplianceClassification(std::wstring const &,std::wstring const &)
0x18002ba3b  cmp     eax, 2
0x18002ba3e  jz      short loc_18002BA26
0x18002ba40  mov     rdx, rbx
0x18002ba43  mov     rcx, r14
0x18002ba46  call    ?_Unchecked_erase@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VCapabilityAppPolicy@Private@CapabilityAccess@Internal@Windows@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VCapabilityAppPolicy@Private@CapabilityAccess@Internal@Windows@@@std@@@2@$0A@@std@@@std@@AEAAPEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VCapabilityAppPolicy@Private@CapabilityAccess@Internal@Windows@@@std@@PEAX@2@PEAU32@@Z; std::_Hash<std::_Umap_traits<std::wstring,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy>>,0>>::_Unchecked_erase(std::_List_node<std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy>,void *> *)
0x18002ba4b  mov     rbx, rax
0x18002ba4e  jmp     short loc_18002BA29
0x18002ba50  mov     [rdi], rsi
0x18002ba53  mov     rax, [rbp+57h+var_50+8]
0x18002ba57  mov     [rdi+8], rax
0x18002ba5b  lea     rcx, [rbp+57h+var_60]
0x18002ba5f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002ba64  jmp     loc_18002B977
0x18002ba69  mov     qword ptr [rdi], 0
0x18002ba70  mov     qword ptr [rdi+8], 0
0x18002ba78  mov     rcx, [rbp+57h+var_50+8]; this
0x18002ba7c  test    rcx, rcx
0x18002ba7f  jz      short loc_18002BA86
0x18002ba81  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002ba86  mov     rax, rdi
0x18002ba89  add     rsp, 88h
0x18002ba90  pop     r15
0x18002ba92  pop     r14
0x18002ba94  pop     rdi
0x18002ba95  pop     rsi
0x18002ba96  pop     rbx
0x18002ba97  pop     rbp
0x18002ba98  retn
0x18002ba99  mov     r9d, eax; char *
0x18002ba9c  lea     r8, aOnecoreBaseDev_1; "onecore\\base\\devices\\cam\\core\\capa"...
0x18002baa3  mov     edx, 32Fh; void *
0x18002baa8  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
