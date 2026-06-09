# Microsoft::Windows::Autopilot::HardwareInfo::GetTpmEkPubByteData(std::vector<uchar,std::allocator<uchar>> &)

- ea: `0x180197c2c`
- end: `0x180197e31`
- name: `?GetTpmEkPubByteData@HardwareInfo@Autopilot@Windows@Microsoft@@SAJAEAV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `517`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18013f1b4`

## callees

- `0x180067a54`
- `0x18006dfb8`
- `0x18006e89c`
- `0x180077384`
- `0x1800801fc`
- `0x1801320e0`
- `0x180136a00`
- `0x180197c2c`

## import_xrefs

- `ncrypt!NCryptGetProperty` at `0x180197d29`
- `ncrypt!NCryptGetProperty` at `0x180197dd8`
- `ncrypt!NCryptGetProperty` at `0x180197d29`
- `ncrypt!NCryptGetProperty` at `0x180197dd8`
- `ncrypt!NCryptOpenStorageProvider` at `0x180197cba`
- `ncrypt!NCryptOpenStorageProvider` at `0x180197cba`

## string_xrefs

- `0x180197c5b`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`
- `0x180197cce`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`
- `0x180197d3d`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`
- `0x180197d8e`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`
- `0x180197dec`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::Windows::Autopilot::HardwareInfo::GetTpmEkPubByteData(PBYTE *a1)
{
  const char *v2; // r9
  __int64 result; // rax
  NCRYPT_PROV_HANDLE *v4; // rax
  SECURITY_STATUS v5; // eax
  unsigned int v6; // ebx
  NCRYPT_HANDLE *v7; // rbx
  NCRYPT_HANDLE v8; // rcx
  SECURITY_STATUS Property; // eax
  unsigned int v10; // edi
  NCRYPT_HANDLE v11; // rcx
  SECURITY_STATUS v12; // eax
  unsigned int v13; // ebx
  int pcbResult; // [rsp+20h] [rbp-48h]
  int pcbResulta; // [rsp+20h] [rbp-48h]
  int pcbResultb; // [rsp+20h] [rbp-48h]
  _BYTE v17[4]; // [rsp+30h] [rbp-38h] BYREF
  DWORD cbOutput; // [rsp+34h] [rbp-34h] BYREF
  DWORD v19; // [rsp+38h] [rbp-30h] BYREF
  __int128 v20; // [rsp+40h] [rbp-28h] BYREF
  std::_Ref_count_base *v21[2]; // [rsp+50h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  try
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl'::`2'::impl) )
    {
      v20 = 0;
      *(_OWORD *)v21 = 0;
      std::shared_ptr<Microsoft::Windows::Autopilot::Diagnostics::EtwProcessingDataEntry>::operator=(&v20, v21);
      if ( v21[1] )
        std::_Ref_count_base::_Decref(v21[1]);
      v4 = (NCRYPT_PROV_HANDLE *)wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>>>::addressof<wistd::integral_constant<unsigned __int64,0>,0>(&v20);
      v5 = NCryptOpenStorageProvider(v4, L"Microsoft Platform Crypto Provider", 0);
      v6 = v5;
      if ( v5 >= 0 )
      {
        cbOutput = 0;
        v7 = (NCRYPT_HANDLE *)v20;
        if ( (_QWORD)v20 )
          v8 = *(_QWORD *)v20;
        else
          v8 = 0;
        Property = NCryptGetProperty(v8, L"PCP_EKPUB", 0, 0, &cbOutput, 0);
        v10 = Property;
        if ( Property >= 0 )
        {
          v19 = 0;
          std::vector<unsigned char>::_Resize<std::_Value_init_tag>(a1, cbOutput, v17);
          if ( *a1 )
          {
            if ( v7 )
              v11 = *v7;
            else
              v11 = 0;
            v12 = NCryptGetProperty(v11, L"PCP_EKPUB", *a1, cbOutput, &v19, 0);
            v13 = v12;
            if ( v12 >= 0 )
            {
              std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(&v20);
              result = 0;
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x11E,
                (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
                (const char *)(unsigned int)v12,
                pcbResultb);
              std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(&v20);
              result = v13;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x11C,
              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
              (const char *)0x8007000ELL,
              pcbResulta);
            std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(&v20);
            result = 2147942414LL;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x118,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
            (const char *)(unsigned int)Property,
            pcbResulta);
          std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(&v20);
          result = v10;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x115,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
          (const char *)(unsigned int)v5,
          pcbResult);
        std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(&v20);
        result = v6;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x109,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
        (const char *)0x80004001LL,
        pcbResult);
      result = 2147500033LL;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x122,
                           (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
                           v2);
  }
  return result;
}

```

## disassembly

```asm
0x180197c2c  mov     [rsp+arg_8], rbx
0x180197c31  mov     [rsp+arg_10], rsi
0x180197c36  push    rdi
0x180197c37  sub     rsp, 60h
0x180197c3b  mov     rsi, rcx
0x180197c3e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x180197c45  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x180197c4a  test    al, al
0x180197c4c  jnz     short loc_180197C73
0x180197c4e  mov     rcx, [rsp+68h]; this
0x180197c53  mov     ebx, 80004001h
0x180197c58  mov     r9d, ebx; char *
0x180197c5b  lea     r8, aOnecoreuapAdmi_125; "onecoreuap\\admin\\moderndeployment\\au"...
0x180197c62  mov     edx, 109h; void *
0x180197c67  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180197c6c  mov     eax, ebx
0x180197c6e  jmp     loc_180197E1E
0x180197c73  xorps   xmm0, xmm0
0x180197c76  xorps   xmm1, xmm1
0x180197c79  movdqu  [rsp+68h+var_28], xmm1
0x180197c7f  movdqu  xmmword ptr [rsp+68h+var_18], xmm0
0x180197c85  lea     rdx, [rsp+68h+var_18]
0x180197c8a  lea     rcx, [rsp+68h+var_28]
0x180197c8f  call    ??4?$shared_ptr@VEtwProcessingDataEntry@Diagnostics@Autopilot@Windows@Microsoft@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Microsoft::Windows::Autopilot::Diagnostics::EtwProcessingDataEntry>::operator=(std::shared_ptr<Microsoft::Windows::Autopilot::Diagnostics::EtwProcessingDataEntry> &&)
0x180197c94  mov     rcx, [rsp+68h+var_18+8]; this
0x180197c99  test    rcx, rcx
0x180197c9c  jz      short loc_180197CA3
0x180197c9e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180197ca3  lea     rcx, [rsp+68h+var_28]
0x180197ca8  call    ??$addressof@U?$integral_constant@_K$0A@@wistd@@$0A@@?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAPEA_KXZ; wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>>>::addressof<wistd::integral_constant<unsigned __int64,0>,0>(void)
0x180197cad  xor     r8d, r8d; dwFlags
0x180197cb0  lea     rdx, pszProviderName; "Microsoft Platform Crypto Provider"
0x180197cb7  mov     rcx, rax; phProvider
0x180197cba  call    cs:__imp_NCryptOpenStorageProvider
0x180197cc0  mov     ebx, eax
0x180197cc2  test    eax, eax
0x180197cc4  jns     short loc_180197CF1
0x180197cc6  mov     rcx, [rsp+68h]; this
0x180197ccb  mov     r9d, eax; char *
0x180197cce  lea     r8, aOnecoreuapAdmi_125; "onecoreuap\\admin\\moderndeployment\\au"...
0x180197cd5  mov     edx, 115h; void *
0x180197cda  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180197cdf  nop
0x180197ce0  lea     rcx, [rsp+68h+var_28]
0x180197ce5  call    ??1?$shared_ptr@V?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@std@@QEAA@XZ; std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(void)
0x180197cea  mov     eax, ebx
0x180197cec  jmp     loc_180197E1E
0x180197cf1  mov     [rsp+68h+cbOutput], 0
0x180197cf9  mov     rbx, qword ptr [rsp+68h+var_28]
0x180197cfe  test    rbx, rbx
0x180197d01  jz      short loc_180197D08
0x180197d03  mov     rcx, [rbx]
0x180197d06  jmp     short loc_180197D0A
0x180197d08  xor     ecx, ecx; hObject
0x180197d0a  mov     [rsp+68h+dwFlags], 0; dwFlags
0x180197d12  lea     rax, [rsp+68h+cbOutput]
0x180197d17  mov     [rsp+68h+pcbResult], rax; int
0x180197d1c  xor     r9d, r9d; cbOutput
0x180197d1f  xor     r8d, r8d; pbOutput
0x180197d22  lea     rdx, aPcpEkpub; "PCP_EKPUB"
0x180197d29  call    cs:__imp_NCryptGetProperty
0x180197d2f  mov     edi, eax
0x180197d31  test    eax, eax
0x180197d33  jns     short loc_180197D60
0x180197d35  mov     rcx, [rsp+68h]; this
0x180197d3a  mov     r9d, eax; char *
0x180197d3d  lea     r8, aOnecoreuapAdmi_125; "onecoreuap\\admin\\moderndeployment\\au"...
0x180197d44  mov     edx, 118h; void *
0x180197d49  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180197d4e  nop
0x180197d4f  lea     rcx, [rsp+68h+var_28]
0x180197d54  call    ??1?$shared_ptr@V?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@std@@QEAA@XZ; std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(void)
0x180197d59  mov     eax, edi
0x180197d5b  jmp     loc_180197E1E
0x180197d60  mov     [rsp+68h+var_30], 0
0x180197d68  mov     edx, [rsp+68h+cbOutput]
0x180197d6c  lea     r8, [rsp+68h+var_38]
0x180197d71  mov     rcx, rsi
0x180197d74  call    ??$_Resize@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180197d79  mov     r8, [rsi]; pbOutput
0x180197d7c  test    r8, r8
0x180197d7f  jnz     short loc_180197DAE
0x180197d81  mov     rcx, [rsp+68h]; this
0x180197d86  mov     ebx, 8007000Eh
0x180197d8b  mov     r9d, ebx; char *
0x180197d8e  lea     r8, aOnecoreuapAdmi_125; "onecoreuap\\admin\\moderndeployment\\au"...
0x180197d95  mov     edx, 11Ch; void *
0x180197d9a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180197d9f  nop
0x180197da0  lea     rcx, [rsp+68h+var_28]
0x180197da5  call    ??1?$shared_ptr@V?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@std@@QEAA@XZ; std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(void)
0x180197daa  mov     eax, ebx
0x180197dac  jmp     short loc_180197E1E
0x180197dae  test    rbx, rbx
0x180197db1  jz      short loc_180197DB8
0x180197db3  mov     rcx, [rbx]
0x180197db6  jmp     short loc_180197DBA
0x180197db8  xor     ecx, ecx; hObject
0x180197dba  mov     [rsp+68h+dwFlags], 0; dwFlags
0x180197dc2  lea     rax, [rsp+68h+var_30]
0x180197dc7  mov     [rsp+68h+pcbResult], rax; int
0x180197dcc  mov     r9d, [rsp+68h+cbOutput]; cbOutput
0x180197dd1  lea     rdx, aPcpEkpub; "PCP_EKPUB"
0x180197dd8  call    cs:__imp_NCryptGetProperty
0x180197dde  mov     ebx, eax
0x180197de0  test    eax, eax
0x180197de2  jns     short loc_180197E0C
0x180197de4  mov     rcx, [rsp+68h]; this
0x180197de9  mov     r9d, eax; char *
0x180197dec  lea     r8, aOnecoreuapAdmi_125; "onecoreuap\\admin\\moderndeployment\\au"...
0x180197df3  mov     edx, 11Eh; void *
0x180197df8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180197dfd  nop
0x180197dfe  lea     rcx, [rsp+68h+var_28]
0x180197e03  call    ??1?$shared_ptr@V?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@std@@QEAA@XZ; std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(void)
0x180197e08  mov     eax, ebx
0x180197e0a  jmp     short loc_180197E1E
0x180197e0c  lea     rcx, [rsp+68h+var_28]
0x180197e11  call    ??1?$shared_ptr@V?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@std@@QEAA@XZ; std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(void)
0x180197e16  xor     eax, eax
0x180197e18  jmp     short loc_180197E1E
0x180197e1a  mov     eax, [rsp+68h+var_30]
0x180197e1e  lea     r11, [rsp+68h+var_8]
0x180197e23  mov     rbx, [r11+18h]
0x180197e27  mov     rsi, [r11+20h]
0x180197e2b  mov     rsp, r11
0x180197e2e  pop     rdi
0x180197e2f  retn
```
