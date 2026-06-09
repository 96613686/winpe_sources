# ModernDeployment::Autopilot::Core::TpmOperations::GetLinkIdInfo(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18013ab68`
- end: `0x18013af15`
- name: `?GetLinkIdInfo@TpmOperations@Core@Autopilot@ModernDeployment@@QEAAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z`
- size: `941`
- prototype: ``
- caller_count: `3`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x180128b08`
- `0x180130b9c`
- `0x18013f1b4`

## callees

- `0x18000b820`
- `0x180067a54`
- `0x18007755c`
- `0x1800801fc`
- `0x1800839bc`
- `0x18013395c`
- `0x1801343e0`
- `0x180134bec`
- `0x18013ab68`
- `0x180145504`
- `0x180145634`
- `0x180145d90`
- `0x180145efc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18013ac5a`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18013ac5a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18013adca`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18013adca`

## string_xrefs

- `0x18013ad74`: `DeviceLinkCreationTimeUtc`
- `0x18013ae30`: `DeviceLinkCreationTimeUtc`
- `0x18013abf9`: `DeviceLinkId`
- `0x18013aca6`: `DeviceLinkId`
- `0x18013abb2`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x18013ac71`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x18013acf5`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x18013ad3f`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x18013adfb`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x18013ae7a`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x18013aebd`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall ModernDeployment::Autopilot::Core::TpmOperations::GetLinkIdInfo(__int64 a1, __int64 a2, __int64 a3)
{
  int v6; // ebx
  HRESULT v7; // eax
  unsigned int v8; // ebx
  int v9; // ebx
  int GuidStringFromGuid; // eax
  unsigned int v11; // ebx
  int Iso8601TimeFromUefi; // ebx
  int v13; // eax
  unsigned int v14; // ebx
  int v15; // ebx
  int v16; // eax
  unsigned int v17; // ebx
  int v18; // [rsp+20h] [rbp-98h]
  _BYTE v19[32]; // [rsp+28h] [rbp-90h] BYREF
  _BYTE v20[32]; // [rsp+48h] [rbp-70h] BYREF
  _OWORD v21[2]; // [rsp+68h] [rbp-50h] BYREF
  GUID pguid; // [rsp+88h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl'::`2'::impl) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3DA,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\tpmoperations.cpp",
      (const char *)0x80004001LL,
      v18);
    return 2147500033LL;
  }
  v21[0] = 0;
  v21[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v21[0]) = 0;
  std::wstring::wstring(v19, L"{B3DE75DA-819C-4FD5-9F01-C3D49E8CBBD7}");
  std::wstring::wstring(&pguid, L"DeviceLinkId");
  v6 = ModernDeployment::Autopilot::Core::DeviceLinkUefi::LoadGuidFromUefi(&pguid, v19, v21);
  std::wstring::_Tidy_deallocate(&pguid);
  std::wstring::_Tidy_deallocate(v19);
  if ( v6 >= 0 )
  {
    std::wstring::wstring(v19, L"{B3DE75DA-819C-4FD5-9F01-C3D49E8CBBD7}");
    std::wstring::wstring(v20, L"DeviceLinkCreationTimeUtc");
    Iso8601TimeFromUefi = ModernDeployment::Autopilot::Core::DeviceLinkUefi::LoadIso8601TimeFromUefi(v20, v19, a3);
    std::wstring::_Tidy_deallocate(v20);
    std::wstring::_Tidy_deallocate(v19);
    if ( Iso8601TimeFromUefi >= 0 )
      goto LABEL_15;
  }
  else
  {
    pguid = 0;
    v7 = CoCreateGuid(&pguid);
    v8 = v7;
    if ( v7 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3E8,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\tpmoperations.cpp",
        (const char *)(unsigned int)v7,
        v18);
      std::wstring::_Tidy_deallocate(v21);
      return v8;
    }
    std::wstring::wstring(v20, L"{B3DE75DA-819C-4FD5-9F01-C3D49E8CBBD7}");
    std::wstring::wstring(v19, L"DeviceLinkId");
    v9 = ModernDeployment::Autopilot::Core::DeviceLinkUefi::StoreGuidToUefi(v19, v20, &pguid);
    std::wstring::_Tidy_deallocate(v19);
    std::wstring::_Tidy_deallocate(v20);
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3ED,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\tpmoperations.cpp",
        (const char *)(unsigned int)v9,
        v18);
      std::wstring::_Tidy_deallocate(v21);
      return (unsigned int)v9;
    }
    GuidStringFromGuid = ModernDeployment::Autopilot::Core::DeviceLinkEncoding::GetGuidStringFromGuid(&pguid);
    v11 = GuidStringFromGuid;
    if ( GuidStringFromGuid < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3EE,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\tpmoperations.cpp",
        (const char *)(unsigned int)GuidStringFromGuid,
        v18);
      std::wstring::_Tidy_deallocate(v21);
      return v11;
    }
  }
  pguid = 0;
  GetSystemTime((LPSYSTEMTIME)&pguid);
  *(_WORD *)&pguid.Data4[6] = 0;
  v13 = ModernDeployment::Autopilot::Core::DeviceLinkEncoding::SystemTimeToIso8601String(&pguid, a3);
  v14 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x405,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\tpmoperations.cpp",
      (const char *)(unsigned int)v13,
      v18);
    std::wstring::_Tidy_deallocate(v21);
    return v14;
  }
  std::wstring::wstring(v19, L"{B3DE75DA-819C-4FD5-9F01-C3D49E8CBBD7}");
  std::wstring::wstring(v20, L"DeviceLinkCreationTimeUtc");
  v15 = ModernDeployment::Autopilot::Core::DeviceLinkUefi::StoreSystemTimeToUefi(v20, v19, a3);
  std::wstring::_Tidy_deallocate(v20);
  std::wstring::_Tidy_deallocate(v19);
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x40A,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\tpmoperations.cpp",
      (const char *)(unsigned int)v15,
      v18);
    std::wstring::_Tidy_deallocate(v21);
    return (unsigned int)v15;
  }
LABEL_15:
  v16 = ModernDeployment::Autopilot::Core::DeviceLinkEncoding::EnsureGuidFormat(v21, 1, a2);
  v17 = v16;
  if ( v16 >= 0 )
  {
    std::wstring::_Tidy_deallocate(v21);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x40E,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\tpmoperations.cpp",
      (const char *)(unsigned int)v16,
      v18);
    std::wstring::_Tidy_deallocate(v21);
    return v17;
  }
}

```

## disassembly

```asm
0x18013ab68  mov     [rsp+arg_0], rbx
0x18013ab6d  mov     [rsp+arg_18], rsi
0x18013ab72  push    rdi
0x18013ab73  sub     rsp, 0B0h
0x18013ab7a  mov     rax, cs:__security_cookie
0x18013ab81  xor     rax, rsp
0x18013ab84  mov     [rsp+0B8h+var_10], rax
0x18013ab8c  mov     rdi, r8
0x18013ab8f  mov     rsi, rdx
0x18013ab92  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x18013ab99  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x18013ab9e  test    al, al
0x18013aba0  jnz     short loc_18013ABCA
0x18013aba2  mov     rcx, [rsp+0B8h]; this
0x18013abaa  mov     ebx, 80004001h
0x18013abaf  mov     r9d, ebx; char *
0x18013abb2  lea     r8, aOnecoreuapAdmi_130; "onecoreuap\\admin\\moderndeployment\\au"...
0x18013abb9  mov     edx, 3DAh; void *
0x18013abbe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013abc3  mov     eax, ebx
0x18013abc5  jmp     loc_18013AEEF
0x18013abca  xorps   xmm0, xmm0
0x18013abcd  movups  [rsp+0B8h+var_50], xmm0
0x18013abd2  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18013abda  movdqu  [rsp+0B8h+var_40], xmm1
0x18013abe0  xor     eax, eax
0x18013abe2  mov     word ptr [rsp+0B8h+var_50], ax
0x18013abe7  lea     rdx, aB3de75da819c4f; "{B3DE75DA-819C-4FD5-9F01-C3D49E8CBBD7}"
0x18013abee  lea     rcx, [rsp+0B8h+var_90]
0x18013abf3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18013abf8  nop
0x18013abf9  lea     rdx, aDevicelinkid; "DeviceLinkId"
0x18013ac00  lea     rcx, [rsp+0B8h+pguid]
0x18013ac08  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18013ac0d  nop
0x18013ac0e  lea     r8, [rsp+0B8h+var_50]
0x18013ac13  lea     rdx, [rsp+0B8h+var_90]
0x18013ac18  lea     rcx, [rsp+0B8h+pguid]
0x18013ac20  call    ?LoadGuidFromUefi@DeviceLinkUefi@Core@Autopilot@ModernDeployment@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAV56@@Z; ModernDeployment::Autopilot::Core::DeviceLinkUefi::LoadGuidFromUefi(std::wstring const &,std::wstring const &,std::wstring &)
0x18013ac25  mov     ebx, eax
0x18013ac27  lea     rcx, [rsp+0B8h+pguid]
0x18013ac2f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013ac34  nop
0x18013ac35  lea     rcx, [rsp+0B8h+var_90]
0x18013ac3a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013ac3f  test    ebx, ebx
0x18013ac41  jns     loc_18013AD62
0x18013ac47  xorps   xmm0, xmm0
0x18013ac4a  movups  xmmword ptr [rsp+0B8h+pguid.Data1], xmm0
0x18013ac52  lea     rcx, [rsp+0B8h+pguid]; pguid
0x18013ac5a  call    cs:__imp_CoCreateGuid
0x18013ac60  mov     ebx, eax
0x18013ac62  test    eax, eax
0x18013ac64  jns     short loc_18013AC94
0x18013ac66  mov     rcx, [rsp+0B8h]; this
0x18013ac6e  mov     r9d, eax; char *
0x18013ac71  lea     r8, aOnecoreuapAdmi_130; "onecoreuap\\admin\\moderndeployment\\au"...
0x18013ac78  mov     edx, 3E8h; void *
0x18013ac7d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013ac82  nop
0x18013ac83  lea     rcx, [rsp+0B8h+var_50]
0x18013ac88  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013ac8d  mov     eax, ebx
0x18013ac8f  jmp     loc_18013AEEF
0x18013ac94  lea     rdx, aB3de75da819c4f; "{B3DE75DA-819C-4FD5-9F01-C3D49E8CBBD7}"
0x18013ac9b  lea     rcx, [rsp+0B8h+var_70]
0x18013aca0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18013aca5  nop
0x18013aca6  lea     rdx, aDevicelinkid; "DeviceLinkId"
0x18013acad  lea     rcx, [rsp+0B8h+var_90]
0x18013acb2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18013acb7  nop
0x18013acb8  lea     r8, [rsp+0B8h+pguid]
0x18013acc0  lea     rdx, [rsp+0B8h+var_70]
0x18013acc5  lea     rcx, [rsp+0B8h+var_90]
0x18013acca  call    ?StoreGuidToUefi@DeviceLinkUefi@Core@Autopilot@ModernDeployment@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEBU_GUID@@@Z; ModernDeployment::Autopilot::Core::DeviceLinkUefi::StoreGuidToUefi(std::wstring const &,std::wstring const &,_GUID const &)
0x18013accf  mov     ebx, eax
0x18013acd1  lea     rcx, [rsp+0B8h+var_90]
0x18013acd6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013acdb  nop
0x18013acdc  lea     rcx, [rsp+0B8h+var_70]
0x18013ace1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013ace6  test    ebx, ebx
0x18013ace8  jns     short loc_18013AD18
0x18013acea  mov     rcx, [rsp+0B8h]; this
0x18013acf2  mov     r9d, ebx; char *
0x18013acf5  lea     r8, aOnecoreuapAdmi_130; "onecoreuap\\admin\\moderndeployment\\au"...
0x18013acfc  mov     edx, 3EDh; void *
0x18013ad01  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013ad06  nop
0x18013ad07  lea     rcx, [rsp+0B8h+var_50]
0x18013ad0c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013ad11  mov     eax, ebx
0x18013ad13  jmp     loc_18013AEEF
0x18013ad18  lea     r8, [rsp+0B8h+var_50]
0x18013ad1d  lea     rcx, [rsp+0B8h+pguid]; rguid
0x18013ad25  call    ?GetGuidStringFromGuid@DeviceLinkEncoding@Core@Autopilot@ModernDeployment@@SAJAEBU_GUID@@W4GuidFormat@1234@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ModernDeployment::Autopilot::Core::DeviceLinkEncoding::GetGuidStringFromGuid(_GUID const &,ModernDeployment::Autopilot::Core::DeviceLinkEncoding::GuidFormat,std::wstring &)
0x18013ad2a  mov     ebx, eax
0x18013ad2c  test    eax, eax
0x18013ad2e  jns     loc_18013ADB7
0x18013ad34  mov     rcx, [rsp+0B8h]; this
0x18013ad3c  mov     r9d, eax; char *
0x18013ad3f  lea     r8, aOnecoreuapAdmi_130; "onecoreuap\\admin\\moderndeployment\\au"...
0x18013ad46  mov     edx, 3EEh; void *
0x18013ad4b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013ad50  nop
0x18013ad51  lea     rcx, [rsp+0B8h+var_50]
0x18013ad56  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013ad5b  mov     eax, ebx
0x18013ad5d  jmp     loc_18013AEEF
0x18013ad62  lea     rdx, aB3de75da819c4f; "{B3DE75DA-819C-4FD5-9F01-C3D49E8CBBD7}"
0x18013ad69  lea     rcx, [rsp+0B8h+var_90]
0x18013ad6e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18013ad73  nop
0x18013ad74  lea     rdx, aDevicelinkcrea; "DeviceLinkCreationTimeUtc"
0x18013ad7b  lea     rcx, [rsp+0B8h+var_70]
0x18013ad80  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18013ad85  nop
0x18013ad86  mov     r8, rdi
0x18013ad89  lea     rdx, [rsp+0B8h+var_90]
0x18013ad8e  lea     rcx, [rsp+0B8h+var_70]
0x18013ad93  call    ?LoadIso8601TimeFromUefi@DeviceLinkUefi@Core@Autopilot@ModernDeployment@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAV56@@Z; ModernDeployment::Autopilot::Core::DeviceLinkUefi::LoadIso8601TimeFromUefi(std::wstring const &,std::wstring const &,std::wstring &)
0x18013ad98  mov     ebx, eax
0x18013ad9a  lea     rcx, [rsp+0B8h+var_70]
0x18013ad9f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013ada4  nop
0x18013ada5  lea     rcx, [rsp+0B8h+var_90]
0x18013adaa  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013adaf  test    ebx, ebx
0x18013adb1  jns     loc_18013AE9A
0x18013adb7  xorps   xmm0, xmm0
0x18013adba  movups  xmmword ptr [rsp+0B8h+pguid.Data1], xmm0
0x18013adc2  lea     rcx, [rsp+0B8h+pguid]; lpSystemTime
0x18013adca  call    cs:__imp_GetSystemTime
0x18013add0  xor     eax, eax
0x18013add2  mov     word ptr [rsp+0B8h+pguid.Data4+6], ax
0x18013adda  mov     rdx, rdi
0x18013addd  lea     rcx, [rsp+0B8h+pguid]
0x18013ade5  call    ?SystemTimeToIso8601String@DeviceLinkEncoding@Core@Autopilot@ModernDeployment@@SAJAEBU_SYSTEMTIME@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ModernDeployment::Autopilot::Core::DeviceLinkEncoding::SystemTimeToIso8601String(_SYSTEMTIME const &,std::wstring &)
0x18013adea  mov     ebx, eax
0x18013adec  test    eax, eax
0x18013adee  jns     short loc_18013AE1E
0x18013adf0  mov     rcx, [rsp+0B8h]; this
0x18013adf8  mov     r9d, eax; char *
0x18013adfb  lea     r8, aOnecoreuapAdmi_130; "onecoreuap\\admin\\moderndeployment\\au"...
0x18013ae02  mov     edx, 405h; void *
0x18013ae07  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013ae0c  nop
0x18013ae0d  lea     rcx, [rsp+0B8h+var_50]
0x18013ae12  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013ae17  mov     eax, ebx
0x18013ae19  jmp     loc_18013AEEF
0x18013ae1e  lea     rdx, aB3de75da819c4f; "{B3DE75DA-819C-4FD5-9F01-C3D49E8CBBD7}"
0x18013ae25  lea     rcx, [rsp+0B8h+var_90]
0x18013ae2a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18013ae2f  nop
0x18013ae30  lea     rdx, aDevicelinkcrea; "DeviceLinkCreationTimeUtc"
0x18013ae37  lea     rcx, [rsp+0B8h+var_70]
0x18013ae3c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18013ae41  nop
0x18013ae42  mov     r8, rdi
0x18013ae45  lea     rdx, [rsp+0B8h+var_90]
0x18013ae4a  lea     rcx, [rsp+0B8h+var_70]
0x18013ae4f  call    ?StoreSystemTimeToUefi@DeviceLinkUefi@Core@Autopilot@ModernDeployment@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00@Z; ModernDeployment::Autopilot::Core::DeviceLinkUefi::StoreSystemTimeToUefi(std::wstring const &,std::wstring const &,std::wstring const &)
0x18013ae54  mov     ebx, eax
0x18013ae56  lea     rcx, [rsp+0B8h+var_70]
0x18013ae5b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013ae60  nop
0x18013ae61  lea     rcx, [rsp+0B8h+var_90]
0x18013ae66  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013ae6b  test    ebx, ebx
0x18013ae6d  jns     short loc_18013AE9A
0x18013ae6f  mov     rcx, [rsp+0B8h]; this
0x18013ae77  mov     r9d, ebx; char *
0x18013ae7a  lea     r8, aOnecoreuapAdmi_130; "onecoreuap\\admin\\moderndeployment\\au"...
0x18013ae81  mov     edx, 40Ah; void *
0x18013ae86  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013ae8b  nop
0x18013ae8c  lea     rcx, [rsp+0B8h+var_50]
0x18013ae91  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013ae96  mov     eax, ebx
0x18013ae98  jmp     short loc_18013AEEF
0x18013ae9a  mov     r8, rsi
0x18013ae9d  mov     edx, 1
0x18013aea2  lea     rcx, [rsp+0B8h+var_50]
0x18013aea7  call    ?EnsureGuidFormat@DeviceLinkEncoding@Core@Autopilot@ModernDeployment@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4GuidFormat@1234@AEAV56@@Z; ModernDeployment::Autopilot::Core::DeviceLinkEncoding::EnsureGuidFormat(std::wstring const &,ModernDeployment::Autopilot::Core::DeviceLinkEncoding::GuidFormat,std::wstring &)
0x18013aeac  mov     ebx, eax
0x18013aeae  test    eax, eax
0x18013aeb0  jns     short loc_18013AEDD
0x18013aeb2  mov     rcx, [rsp+0B8h]; this
0x18013aeba  mov     r9d, eax; char *
0x18013aebd  lea     r8, aOnecoreuapAdmi_130; "onecoreuap\\admin\\moderndeployment\\au"...
0x18013aec4  mov     edx, 40Eh; void *
0x18013aec9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013aece  nop
0x18013aecf  lea     rcx, [rsp+0B8h+var_50]
0x18013aed4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013aed9  mov     eax, ebx
0x18013aedb  jmp     short loc_18013AEEF
0x18013aedd  lea     rcx, [rsp+0B8h+var_50]
0x18013aee2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013aee7  xor     eax, eax
0x18013aee9  jmp     short loc_18013AEEF
0x18013aeeb  mov     eax, [rsp+0B8h+var_98]
0x18013aeef  mov     rcx, [rsp+0B8h+var_10]
0x18013aef7  xor     rcx, rsp; StackCookie
0x18013aefa  call    __security_check_cookie
0x18013aeff  lea     r11, [rsp+0B8h+var_8]
0x18013af07  mov     rbx, [r11+10h]
0x18013af0b  mov     rsi, [r11+28h]
0x18013af0f  mov     rsp, r11
0x18013af12  pop     rdi
0x18013af13  retn
```
