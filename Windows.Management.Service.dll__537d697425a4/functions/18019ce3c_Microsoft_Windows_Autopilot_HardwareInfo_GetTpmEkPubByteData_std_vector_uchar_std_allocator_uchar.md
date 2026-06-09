# Microsoft::Windows::Autopilot::HardwareInfo::GetTpmEkPubByteData(std::vector<uchar,std::allocator<uchar>> &)

- ea: `0x18019ce3c`
- end: `0x18019d053`
- name: `?GetTpmEkPubByteData@HardwareInfo@Autopilot@Windows@Microsoft@@SAJAEAV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `535`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1801432a8`

## callees

- `0x180067e54`
- `0x18006e508`
- `0x18006ee48`
- `0x180077c04`
- `0x180080c10`
- `0x180135ea0`
- `0x18013a968`
- `0x18019ce3c`

## import_xrefs

- `ncrypt!NCryptGetProperty` at `0x18019cf3f`
- `ncrypt!NCryptGetProperty` at `0x18019cff4`
- `ncrypt!NCryptGetProperty` at `0x18019cf3f`
- `ncrypt!NCryptGetProperty` at `0x18019cff4`
- `ncrypt!NCryptOpenStorageProvider` at `0x18019ceca`
- `ncrypt!NCryptOpenStorageProvider` at `0x18019ceca`

## string_xrefs

- `0x18019ce6b`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`
- `0x18019cee4`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`
- `0x18019cf59`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`
- `0x18019cfaa`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`
- `0x18019d00e`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`

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
0x18019ce3c  mov     [rsp+arg_8], rbx
0x18019ce41  mov     [rsp+arg_10], rsi
0x18019ce46  push    rdi
0x18019ce47  sub     rsp, 60h
0x18019ce4b  mov     rsi, rcx
0x18019ce4e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x18019ce55  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x18019ce5a  test    al, al
0x18019ce5c  jnz     short loc_18019CE83
0x18019ce5e  mov     rcx, [rsp+68h]; this
0x18019ce63  mov     ebx, 80004001h
0x18019ce68  mov     r9d, ebx; char *
0x18019ce6b  lea     r8, aOnecoreuapAdmi_125; "onecoreuap\\admin\\moderndeployment\\au"...
0x18019ce72  mov     edx, 109h; void *
0x18019ce77  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18019ce7c  mov     eax, ebx
0x18019ce7e  jmp     loc_18019D040
0x18019ce83  xorps   xmm0, xmm0
0x18019ce86  xorps   xmm1, xmm1
0x18019ce89  movdqu  [rsp+68h+var_28], xmm1
0x18019ce8f  movdqu  xmmword ptr [rsp+68h+var_18], xmm0
0x18019ce95  lea     rdx, [rsp+68h+var_18]
0x18019ce9a  lea     rcx, [rsp+68h+var_28]
0x18019ce9f  call    ??4?$shared_ptr@VEtwProcessingDataEntry@Diagnostics@Autopilot@Windows@Microsoft@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Microsoft::Windows::Autopilot::Diagnostics::EtwProcessingDataEntry>::operator=(std::shared_ptr<Microsoft::Windows::Autopilot::Diagnostics::EtwProcessingDataEntry> &&)
0x18019cea4  mov     rcx, [rsp+68h+var_18+8]; this
0x18019cea9  test    rcx, rcx
0x18019ceac  jz      short loc_18019CEB3
0x18019ceae  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18019ceb3  lea     rcx, [rsp+68h+var_28]
0x18019ceb8  call    ??$addressof@U?$integral_constant@_K$0A@@wistd@@$0A@@?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAPEA_KXZ; wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>>>::addressof<wistd::integral_constant<unsigned __int64,0>,0>(void)
0x18019cebd  xor     r8d, r8d; dwFlags
0x18019cec0  lea     rdx, pszProviderName; "Microsoft Platform Crypto Provider"
0x18019cec7  mov     rcx, rax; phProvider
0x18019ceca  call    cs:__imp_NCryptOpenStorageProvider
0x18019ced1  nop     dword ptr [rax+rax+00h]
0x18019ced6  mov     ebx, eax
0x18019ced8  test    eax, eax
0x18019ceda  jns     short loc_18019CF07
0x18019cedc  mov     rcx, [rsp+68h]; this
0x18019cee1  mov     r9d, eax; char *
0x18019cee4  lea     r8, aOnecoreuapAdmi_125; "onecoreuap\\admin\\moderndeployment\\au"...
0x18019ceeb  mov     edx, 115h; void *
0x18019cef0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18019cef5  nop
0x18019cef6  lea     rcx, [rsp+68h+var_28]
0x18019cefb  call    ??1?$shared_ptr@V?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@std@@QEAA@XZ; std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(void)
0x18019cf00  mov     eax, ebx
0x18019cf02  jmp     loc_18019D040
0x18019cf07  mov     [rsp+68h+cbOutput], 0
0x18019cf0f  mov     rbx, qword ptr [rsp+68h+var_28]
0x18019cf14  test    rbx, rbx
0x18019cf17  jz      short loc_18019CF1E
0x18019cf19  mov     rcx, [rbx]
0x18019cf1c  jmp     short loc_18019CF20
0x18019cf1e  xor     ecx, ecx; hObject
0x18019cf20  mov     [rsp+68h+dwFlags], 0; dwFlags
0x18019cf28  lea     rax, [rsp+68h+cbOutput]
0x18019cf2d  mov     [rsp+68h+pcbResult], rax; int
0x18019cf32  xor     r9d, r9d; cbOutput
0x18019cf35  xor     r8d, r8d; pbOutput
0x18019cf38  lea     rdx, aPcpEkpub; "PCP_EKPUB"
0x18019cf3f  call    cs:__imp_NCryptGetProperty
0x18019cf46  nop     dword ptr [rax+rax+00h]
0x18019cf4b  mov     edi, eax
0x18019cf4d  test    eax, eax
0x18019cf4f  jns     short loc_18019CF7C
0x18019cf51  mov     rcx, [rsp+68h]; this
0x18019cf56  mov     r9d, eax; char *
0x18019cf59  lea     r8, aOnecoreuapAdmi_125; "onecoreuap\\admin\\moderndeployment\\au"...
0x18019cf60  mov     edx, 118h; void *
0x18019cf65  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18019cf6a  nop
0x18019cf6b  lea     rcx, [rsp+68h+var_28]
0x18019cf70  call    ??1?$shared_ptr@V?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@std@@QEAA@XZ; std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(void)
0x18019cf75  mov     eax, edi
0x18019cf77  jmp     loc_18019D040
0x18019cf7c  mov     [rsp+68h+var_30], 0
0x18019cf84  mov     edx, [rsp+68h+cbOutput]
0x18019cf88  lea     r8, [rsp+68h+var_38]
0x18019cf8d  mov     rcx, rsi
0x18019cf90  call    ??$_Resize@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18019cf95  mov     r8, [rsi]; pbOutput
0x18019cf98  test    r8, r8
0x18019cf9b  jnz     short loc_18019CFCA
0x18019cf9d  mov     rcx, [rsp+68h]; this
0x18019cfa2  mov     ebx, 8007000Eh
0x18019cfa7  mov     r9d, ebx; char *
0x18019cfaa  lea     r8, aOnecoreuapAdmi_125; "onecoreuap\\admin\\moderndeployment\\au"...
0x18019cfb1  mov     edx, 11Ch; void *
0x18019cfb6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18019cfbb  nop
0x18019cfbc  lea     rcx, [rsp+68h+var_28]
0x18019cfc1  call    ??1?$shared_ptr@V?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@std@@QEAA@XZ; std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(void)
0x18019cfc6  mov     eax, ebx
0x18019cfc8  jmp     short loc_18019D040
0x18019cfca  test    rbx, rbx
0x18019cfcd  jz      short loc_18019CFD4
0x18019cfcf  mov     rcx, [rbx]
0x18019cfd2  jmp     short loc_18019CFD6
0x18019cfd4  xor     ecx, ecx; hObject
0x18019cfd6  mov     [rsp+68h+dwFlags], 0; dwFlags
0x18019cfde  lea     rax, [rsp+68h+var_30]
0x18019cfe3  mov     [rsp+68h+pcbResult], rax; int
0x18019cfe8  mov     r9d, [rsp+68h+cbOutput]; cbOutput
0x18019cfed  lea     rdx, aPcpEkpub; "PCP_EKPUB"
0x18019cff4  call    cs:__imp_NCryptGetProperty
0x18019cffb  nop     dword ptr [rax+rax+00h]
0x18019d000  mov     ebx, eax
0x18019d002  test    eax, eax
0x18019d004  jns     short loc_18019D02E
0x18019d006  mov     rcx, [rsp+68h]; this
0x18019d00b  mov     r9d, eax; char *
0x18019d00e  lea     r8, aOnecoreuapAdmi_125; "onecoreuap\\admin\\moderndeployment\\au"...
0x18019d015  mov     edx, 11Eh; void *
0x18019d01a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18019d01f  nop
0x18019d020  lea     rcx, [rsp+68h+var_28]
0x18019d025  call    ??1?$shared_ptr@V?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@std@@QEAA@XZ; std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(void)
0x18019d02a  mov     eax, ebx
0x18019d02c  jmp     short loc_18019D040
0x18019d02e  lea     rcx, [rsp+68h+var_28]
0x18019d033  call    ??1?$shared_ptr@V?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@std@@QEAA@XZ; std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(void)
0x18019d038  xor     eax, eax
0x18019d03a  jmp     short loc_18019D040
0x18019d03c  mov     eax, [rsp+68h+var_30]
0x18019d040  lea     r11, [rsp+68h+var_8]
0x18019d045  mov     rbx, [r11+18h]
0x18019d049  mov     rsi, [r11+20h]
0x18019d04d  mov     rsp, r11
0x18019d050  pop     rdi
0x18019d051  retn
```
