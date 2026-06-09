# ModernDeployment::Autopilot::Core::DeviceLinkDiscoveryCache::WriteCachedDiscoveryInfo(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> const &)

- ea: `0x180131cb4`
- end: `0x180131ea2`
- name: `?WriteCachedDiscoveryInfo@DeviceLinkDiscoveryCache@Core@Autopilot@ModernDeployment@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@1@Z`
- size: `494`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18012c798`

## callees

- `0x18000b8f0`
- `0x180067e54`
- `0x180077de0`
- `0x180080c10`
- `0x180084d80`
- `0x180088144`
- `0x18008a454`
- `0x180131820`
- `0x180131cb4`
- `0x180131ea8`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180131dbf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180131dd3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180131dbf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180131dd3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180131d63`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180131d63`

## string_xrefs

- `0x180131cfb`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkdiscoverycache.cpp`
- `0x180131d7a`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkdiscoverycache.cpp`
- `0x180131df2`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkdiscoverycache.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ModernDeployment::Autopilot::Core::DeviceLinkDiscoveryCache::WriteCachedDiscoveryInfo(
        __int64 a1,
        HSTRING *a2,
        HSTRING *a3)
{
  unsigned int v6; // ebx
  unsigned int v7; // eax
  PCWSTR StringRawBuffer; // rbx
  PCWSTR v9; // rax
  __int64 v10; // rdx
  __int64 v11; // r9
  int v12; // eax
  int v13; // eax
  DWORD dwOptions; // [rsp+20h] [rbp-39h]
  DWORD dwOptionsa; // [rsp+20h] [rbp-39h]
  HKEY hKey; // [rsp+50h] [rbp-9h] BYREF
  _BYTE v18[32]; // [rsp+58h] [rbp-1h] BYREF
  _BYTE v19[32]; // [rsp+78h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl'::`2'::impl) )
  {
    hKey = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    v7 = RegCreateKeyExW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Microsoft\\Provisioning\\AutopilotSettings",
           0,
           0,
           0,
           0x20006u,
           0,
           &hKey,
           0);
    if ( v7 )
    {
      v6 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x47,
             (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\devicelink\\devicelinkdiscoverycache.cpp",
             (const char *)v7,
             dwOptionsa);
LABEL_16:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      return v6;
    }
    ModernDeployment::Autopilot::Core::DeviceLinkDiscoveryCache::CreateRegistryValueName(v19, a1, L"DiscoveryUrl");
    ModernDeployment::Autopilot::Core::DeviceLinkDiscoveryCache::CreateRegistryValueName(v18, a1, L"TenantIdHint");
    StringRawBuffer = WindowsGetStringRawBuffer(*a2, 0);
    v9 = WindowsGetStringRawBuffer(*a3, 0);
    if ( StringRawBuffer )
    {
      if ( v9 )
      {
        v12 = ModernDeployment::Autopilot::Core::DeviceLinkDiscoveryCache::WriteRegistryStringValue(hKey);
        v6 = v12;
        if ( v12 >= 0 )
        {
          v13 = ModernDeployment::Autopilot::Core::DeviceLinkDiscoveryCache::WriteRegistryStringValue(hKey);
          v6 = v13;
          if ( v13 >= 0 )
          {
            std::wstring::_Tidy_deallocate(v18);
            std::wstring::_Tidy_deallocate(v19);
            v6 = 0;
            goto LABEL_16;
          }
          v11 = (unsigned int)v13;
          v10 = 85;
        }
        else
        {
          v11 = (unsigned int)v12;
          v10 = 84;
        }
        goto LABEL_8;
      }
      v10 = 81;
    }
    else
    {
      v10 = 80;
    }
    v6 = -2147024809;
    v11 = 2147942487LL;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\devicelink\\devicelinkdiscoverycache.cpp",
      (const char *)v11,
      dwOptionsa);
    std::wstring::_Tidy_deallocate(v18);
    std::wstring::_Tidy_deallocate(v19);
    goto LABEL_16;
  }
  v6 = -2147467263;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x3B,
    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\devicelink\\devicelinkdiscoverycache.cpp",
    (const char *)0x80004001LL,
    dwOptions);
  return v6;
}

```

## disassembly

```asm
0x180131cb4  mov     [rsp-8+arg_18], rbx
0x180131cb9  push    rbp
0x180131cba  push    rsi
0x180131cbb  push    rdi
0x180131cbc  lea     rbp, [rsp-47h]
0x180131cc1  sub     rsp, 0A0h
0x180131cc8  mov     rax, cs:__security_cookie
0x180131ccf  xor     rax, rsp
0x180131cd2  mov     [rbp+57h+var_18], rax
0x180131cd6  mov     rsi, r8
0x180131cd9  mov     rdi, rdx
0x180131cdc  mov     rbx, rcx
0x180131cdf  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x180131ce6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x180131ceb  test    al, al
0x180131ced  jnz     short loc_180131D11
0x180131cef  mov     rcx, [rbp+5Fh]; this
0x180131cf3  mov     ebx, 80004001h
0x180131cf8  mov     r9d, ebx; char *
0x180131cfb  lea     r8, aOnecoreuapAdmi_24; "onecoreuap\\admin\\moderndeployment\\au"...
0x180131d02  mov     edx, 3Bh ; ';'; void *
0x180131d07  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180131d0c  jmp     loc_180131E80
0x180131d11  mov     [rbp+57h+hKey], 0
0x180131d19  xor     edx, edx
0x180131d1b  lea     rcx, [rbp+57h+hKey]
0x180131d1f  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180131d24  mov     [rsp+0B0h+lpdwDisposition], 0; lpdwDisposition
0x180131d2d  lea     rax, [rbp+57h+hKey]
0x180131d31  mov     [rsp+0B0h+phkResult], rax; phkResult
0x180131d36  mov     [rsp+0B0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180131d3f  mov     [rsp+0B0h+samDesired], 20006h; samDesired
0x180131d47  mov     [rsp+0B0h+dwOptions], 0; int
0x180131d4f  xor     r9d, r9d; lpClass
0x180131d52  xor     r8d, r8d; Reserved
0x180131d55  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Provisioning\\Auto"...
0x180131d5c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180131d63  call    cs:__imp_RegCreateKeyExW
0x180131d6a  nop     dword ptr [rax+rax+00h]
0x180131d6f  test    eax, eax
0x180131d71  jz      short loc_180131D92
0x180131d73  mov     rcx, [rbp+5Fh]; this
0x180131d77  mov     r9d, eax; char *
0x180131d7a  lea     r8, aOnecoreuapAdmi_24; "onecoreuap\\admin\\moderndeployment\\au"...
0x180131d81  mov     edx, 47h ; 'G'; void *
0x180131d86  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180131d8b  mov     ebx, eax
0x180131d8d  jmp     loc_180131E77
0x180131d92  lea     r8, aDiscoveryurl; "DiscoveryUrl"
0x180131d99  mov     rdx, rbx
0x180131d9c  lea     rcx, [rbp+57h+var_38]
0x180131da0  call    ?CreateRegistryValueName@DeviceLinkDiscoveryCache@Core@Autopilot@ModernDeployment@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV56@PEBG@Z; ModernDeployment::Autopilot::Core::DeviceLinkDiscoveryCache::CreateRegistryValueName(std::wstring const &,ushort const *)
0x180131da5  nop
0x180131da6  lea     r8, aTenantidhint; "TenantIdHint"
0x180131dad  mov     rdx, rbx
0x180131db0  lea     rcx, [rbp+57h+var_58]
0x180131db4  call    ?CreateRegistryValueName@DeviceLinkDiscoveryCache@Core@Autopilot@ModernDeployment@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV56@PEBG@Z; ModernDeployment::Autopilot::Core::DeviceLinkDiscoveryCache::CreateRegistryValueName(std::wstring const &,ushort const *)
0x180131db9  nop
0x180131dba  xor     edx, edx; length
0x180131dbc  mov     rcx, [rdi]; string
0x180131dbf  call    cs:__imp_WindowsGetStringRawBuffer
0x180131dc6  nop     dword ptr [rax+rax+00h]
0x180131dcb  mov     rbx, rax
0x180131dce  xor     edx, edx; length
0x180131dd0  mov     rcx, [rsi]; string
0x180131dd3  call    cs:__imp_WindowsGetStringRawBuffer
0x180131dda  nop     dword ptr [rax+rax+00h]
0x180131ddf  mov     rdi, rax
0x180131de2  test    rbx, rbx
0x180131de5  jnz     short loc_180131E18
0x180131de7  lea     edx, [rbx+50h]; void *
0x180131dea  mov     ebx, 80070057h
0x180131def  mov     r9d, ebx; char *
0x180131df2  lea     r8, aOnecoreuapAdmi_24; "onecoreuap\\admin\\moderndeployment\\au"...
0x180131df9  mov     rcx, [rbp+5Fh]; this
0x180131dfd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180131e02  nop
0x180131e03  lea     rcx, [rbp+57h+var_58]
0x180131e07  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180131e0c  nop
0x180131e0d  lea     rcx, [rbp+57h+var_38]
0x180131e11  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180131e16  jmp     short loc_180131E77
0x180131e18  test    rdi, rdi
0x180131e1b  jnz     short loc_180131E22
0x180131e1d  lea     edx, [rdi+51h]
0x180131e20  jmp     short loc_180131DEA
0x180131e22  mov     r8, rbx
0x180131e25  lea     rdx, [rbp+57h+var_38]
0x180131e29  mov     rcx, [rbp+57h+hKey]; hKey
0x180131e2d  call    ?WriteRegistryStringValue@DeviceLinkDiscoveryCache@Core@Autopilot@ModernDeployment@@CAJPEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; ModernDeployment::Autopilot::Core::DeviceLinkDiscoveryCache::WriteRegistryStringValue(HKEY__ *,std::wstring const &,ushort const *)
0x180131e32  mov     ebx, eax
0x180131e34  test    eax, eax
0x180131e36  jns     short loc_180131E42
0x180131e38  mov     r9d, eax
0x180131e3b  mov     edx, 54h ; 'T'
0x180131e40  jmp     short loc_180131DF2
0x180131e42  mov     r8, rdi
0x180131e45  lea     rdx, [rbp+57h+var_58]
0x180131e49  mov     rcx, [rbp+57h+hKey]; hKey
0x180131e4d  call    ?WriteRegistryStringValue@DeviceLinkDiscoveryCache@Core@Autopilot@ModernDeployment@@CAJPEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; ModernDeployment::Autopilot::Core::DeviceLinkDiscoveryCache::WriteRegistryStringValue(HKEY__ *,std::wstring const &,ushort const *)
0x180131e52  mov     ebx, eax
0x180131e54  test    eax, eax
0x180131e56  jns     short loc_180131E62
0x180131e58  mov     r9d, eax
0x180131e5b  mov     edx, 55h ; 'U'
0x180131e60  jmp     short loc_180131DF2
0x180131e62  lea     rcx, [rbp+57h+var_58]
0x180131e66  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180131e6b  nop
0x180131e6c  lea     rcx, [rbp+57h+var_38]
0x180131e70  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180131e75  xor     ebx, ebx
0x180131e77  lea     rcx, [rbp+57h+hKey]
0x180131e7b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180131e80  mov     eax, ebx
0x180131e82  mov     rcx, [rbp+57h+var_18]
0x180131e86  xor     rcx, rsp; StackCookie
0x180131e89  call    __security_check_cookie
0x180131e8e  mov     rbx, [rsp+0B0h+arg_18]
0x180131e96  add     rsp, 0A0h
0x180131e9d  pop     rdi
0x180131e9e  pop     rsi
0x180131e9f  pop     rbp
0x180131ea0  retn
```
