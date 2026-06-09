# ModernDeployment::Autopilot::Core::DeviceLinkDiscoveryCache::WriteCachedDiscoveryInfo(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> const &)

- ea: `0x18012dfac`
- end: `0x18012e187`
- name: `?WriteCachedDiscoveryInfo@DeviceLinkDiscoveryCache@Core@Autopilot@ModernDeployment@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@1@Z`
- size: `475`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180128b08`

## callees

- `0x18000b820`
- `0x180067a54`
- `0x18007755c`
- `0x1800801fc`
- `0x180084208`
- `0x1800873a4`
- `0x180089614`
- `0x18012db30`
- `0x18012dfac`
- `0x18012e190`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18012e0b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18012e0bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18012e0b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18012e0bf`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18012e05b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18012e05b`

## string_xrefs

- `0x18012dff3`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkdiscoverycache.cpp`
- `0x18012e06c`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkdiscoverycache.cpp`
- `0x18012e0d8`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkdiscoverycache.cpp`

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
0x18012dfac  mov     [rsp-8+arg_18], rbx
0x18012dfb1  push    rbp
0x18012dfb2  push    rsi
0x18012dfb3  push    rdi
0x18012dfb4  lea     rbp, [rsp-47h]
0x18012dfb9  sub     rsp, 0A0h
0x18012dfc0  mov     rax, cs:__security_cookie
0x18012dfc7  xor     rax, rsp
0x18012dfca  mov     [rbp+57h+var_18], rax
0x18012dfce  mov     rsi, r8
0x18012dfd1  mov     rdi, rdx
0x18012dfd4  mov     rbx, rcx
0x18012dfd7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x18012dfde  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x18012dfe3  test    al, al
0x18012dfe5  jnz     short loc_18012E009
0x18012dfe7  mov     rcx, [rbp+5Fh]; this
0x18012dfeb  mov     ebx, 80004001h
0x18012dff0  mov     r9d, ebx; char *
0x18012dff3  lea     r8, aOnecoreuapAdmi_24; "onecoreuap\\admin\\moderndeployment\\au"...
0x18012dffa  mov     edx, 3Bh ; ';'; void *
0x18012dfff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012e004  jmp     loc_18012E166
0x18012e009  mov     [rbp+57h+hKey], 0
0x18012e011  xor     edx, edx
0x18012e013  lea     rcx, [rbp+57h+hKey]
0x18012e017  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18012e01c  mov     [rsp+0B0h+lpdwDisposition], 0; lpdwDisposition
0x18012e025  lea     rax, [rbp+57h+hKey]
0x18012e029  mov     [rsp+0B0h+phkResult], rax; phkResult
0x18012e02e  mov     [rsp+0B0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18012e037  mov     [rsp+0B0h+samDesired], 20006h; samDesired
0x18012e03f  mov     [rsp+0B0h+dwOptions], 0; int
0x18012e047  xor     r9d, r9d; lpClass
0x18012e04a  xor     r8d, r8d; Reserved
0x18012e04d  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Provisioning\\Auto"...
0x18012e054  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18012e05b  call    cs:__imp_RegCreateKeyExW
0x18012e061  test    eax, eax
0x18012e063  jz      short loc_18012E084
0x18012e065  mov     rcx, [rbp+5Fh]; this
0x18012e069  mov     r9d, eax; char *
0x18012e06c  lea     r8, aOnecoreuapAdmi_24; "onecoreuap\\admin\\moderndeployment\\au"...
0x18012e073  mov     edx, 47h ; 'G'; void *
0x18012e078  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18012e07d  mov     ebx, eax
0x18012e07f  jmp     loc_18012E15D
0x18012e084  lea     r8, aDiscoveryurl; "DiscoveryUrl"
0x18012e08b  mov     rdx, rbx
0x18012e08e  lea     rcx, [rbp+57h+var_38]
0x18012e092  call    ?CreateRegistryValueName@DeviceLinkDiscoveryCache@Core@Autopilot@ModernDeployment@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV56@PEBG@Z; ModernDeployment::Autopilot::Core::DeviceLinkDiscoveryCache::CreateRegistryValueName(std::wstring const &,ushort const *)
0x18012e097  nop
0x18012e098  lea     r8, aTenantidhint; "TenantIdHint"
0x18012e09f  mov     rdx, rbx
0x18012e0a2  lea     rcx, [rbp+57h+var_58]
0x18012e0a6  call    ?CreateRegistryValueName@DeviceLinkDiscoveryCache@Core@Autopilot@ModernDeployment@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV56@PEBG@Z; ModernDeployment::Autopilot::Core::DeviceLinkDiscoveryCache::CreateRegistryValueName(std::wstring const &,ushort const *)
0x18012e0ab  nop
0x18012e0ac  xor     edx, edx; length
0x18012e0ae  mov     rcx, [rdi]; string
0x18012e0b1  call    cs:__imp_WindowsGetStringRawBuffer
0x18012e0b7  mov     rbx, rax
0x18012e0ba  xor     edx, edx; length
0x18012e0bc  mov     rcx, [rsi]; string
0x18012e0bf  call    cs:__imp_WindowsGetStringRawBuffer
0x18012e0c5  mov     rdi, rax
0x18012e0c8  test    rbx, rbx
0x18012e0cb  jnz     short loc_18012E0FE
0x18012e0cd  lea     edx, [rbx+50h]; void *
0x18012e0d0  mov     ebx, 80070057h
0x18012e0d5  mov     r9d, ebx; char *
0x18012e0d8  lea     r8, aOnecoreuapAdmi_24; "onecoreuap\\admin\\moderndeployment\\au"...
0x18012e0df  mov     rcx, [rbp+5Fh]; this
0x18012e0e3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012e0e8  nop
0x18012e0e9  lea     rcx, [rbp+57h+var_58]
0x18012e0ed  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012e0f2  nop
0x18012e0f3  lea     rcx, [rbp+57h+var_38]
0x18012e0f7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012e0fc  jmp     short loc_18012E15D
0x18012e0fe  test    rdi, rdi
0x18012e101  jnz     short loc_18012E108
0x18012e103  lea     edx, [rdi+51h]
0x18012e106  jmp     short loc_18012E0D0
0x18012e108  mov     r8, rbx
0x18012e10b  lea     rdx, [rbp+57h+var_38]
0x18012e10f  mov     rcx, [rbp+57h+hKey]; hKey
0x18012e113  call    ?WriteRegistryStringValue@DeviceLinkDiscoveryCache@Core@Autopilot@ModernDeployment@@CAJPEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; ModernDeployment::Autopilot::Core::DeviceLinkDiscoveryCache::WriteRegistryStringValue(HKEY__ *,std::wstring const &,ushort const *)
0x18012e118  mov     ebx, eax
0x18012e11a  test    eax, eax
0x18012e11c  jns     short loc_18012E128
0x18012e11e  mov     r9d, eax
0x18012e121  mov     edx, 54h ; 'T'
0x18012e126  jmp     short loc_18012E0D8
0x18012e128  mov     r8, rdi
0x18012e12b  lea     rdx, [rbp+57h+var_58]
0x18012e12f  mov     rcx, [rbp+57h+hKey]; hKey
0x18012e133  call    ?WriteRegistryStringValue@DeviceLinkDiscoveryCache@Core@Autopilot@ModernDeployment@@CAJPEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; ModernDeployment::Autopilot::Core::DeviceLinkDiscoveryCache::WriteRegistryStringValue(HKEY__ *,std::wstring const &,ushort const *)
0x18012e138  mov     ebx, eax
0x18012e13a  test    eax, eax
0x18012e13c  jns     short loc_18012E148
0x18012e13e  mov     r9d, eax
0x18012e141  mov     edx, 55h ; 'U'
0x18012e146  jmp     short loc_18012E0D8
0x18012e148  lea     rcx, [rbp+57h+var_58]
0x18012e14c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012e151  nop
0x18012e152  lea     rcx, [rbp+57h+var_38]
0x18012e156  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012e15b  xor     ebx, ebx
0x18012e15d  lea     rcx, [rbp+57h+hKey]
0x18012e161  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18012e166  mov     eax, ebx
0x18012e168  mov     rcx, [rbp+57h+var_18]
0x18012e16c  xor     rcx, rsp; StackCookie
0x18012e16f  call    __security_check_cookie
0x18012e174  mov     rbx, [rsp+0B0h+arg_18]
0x18012e17c  add     rsp, 0A0h
0x18012e183  pop     rdi
0x18012e184  pop     rsi
0x18012e185  pop     rbp
0x18012e186  retn
```
