# ModernDeployment::Autopilot::Core::TpmOperations::GetLinkIdInfo(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18013ebb0`
- end: `0x18013ef69`
- name: `?GetLinkIdInfo@TpmOperations@Core@Autopilot@ModernDeployment@@QEAAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z`
- size: `953`
- prototype: ``
- caller_count: `3`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x18012c798`
- `0x18013491c`
- `0x1801432a8`

## callees

- `0x18000b8f0`
- `0x180067e54`
- `0x180077de0`
- `0x180080c10`
- `0x180084574`
- `0x1801377e4`
- `0x180138278`
- `0x180138aa0`
- `0x18013ebb0`
- `0x1801493e8`
- `0x180149518`
- `0x180149c84`
- `0x180149df4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18013eca2`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18013eca2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18013ee18`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18013ee18`

## string_xrefs

- `0x18013edc2`: `DeviceLinkCreationTimeUtc`
- `0x18013ee84`: `DeviceLinkCreationTimeUtc`
- `0x18013ec41`: `DeviceLinkId`
- `0x18013ecf4`: `DeviceLinkId`
- `0x18013ebfa`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x18013ecbf`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x18013ed43`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x18013ed8d`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x18013ee4f`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x18013eece`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x18013ef11`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`

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
0x18013ebb0  mov     [rsp+arg_0], rbx
0x18013ebb5  mov     [rsp+arg_18], rsi
0x18013ebba  push    rdi
0x18013ebbb  sub     rsp, 0B0h
0x18013ebc2  mov     rax, cs:__security_cookie
0x18013ebc9  xor     rax, rsp
0x18013ebcc  mov     [rsp+0B8h+var_10], rax
0x18013ebd4  mov     rdi, r8
0x18013ebd7  mov     rsi, rdx
0x18013ebda  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x18013ebe1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x18013ebe6  test    al, al
0x18013ebe8  jnz     short loc_18013EC12
0x18013ebea  mov     rcx, [rsp+0B8h]; this
0x18013ebf2  mov     ebx, 80004001h
0x18013ebf7  mov     r9d, ebx; char *
0x18013ebfa  lea     r8, aOnecoreuapAdmi_130; "onecoreuap\\admin\\moderndeployment\\au"...
0x18013ec01  mov     edx, 3DAh; void *
0x18013ec06  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013ec0b  mov     eax, ebx
0x18013ec0d  jmp     loc_18013EF43
0x18013ec12  xorps   xmm0, xmm0
0x18013ec15  movups  [rsp+0B8h+var_50], xmm0
0x18013ec1a  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18013ec22  movdqu  [rsp+0B8h+var_40], xmm1
0x18013ec28  xor     eax, eax
0x18013ec2a  mov     word ptr [rsp+0B8h+var_50], ax
0x18013ec2f  lea     rdx, aB3de75da819c4f; "{B3DE75DA-819C-4FD5-9F01-C3D49E8CBBD7}"
0x18013ec36  lea     rcx, [rsp+0B8h+var_90]
0x18013ec3b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18013ec40  nop
0x18013ec41  lea     rdx, aDevicelinkid; "DeviceLinkId"
0x18013ec48  lea     rcx, [rsp+0B8h+pguid]
0x18013ec50  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18013ec55  nop
0x18013ec56  lea     r8, [rsp+0B8h+var_50]
0x18013ec5b  lea     rdx, [rsp+0B8h+var_90]
0x18013ec60  lea     rcx, [rsp+0B8h+pguid]
0x18013ec68  call    ?LoadGuidFromUefi@DeviceLinkUefi@Core@Autopilot@ModernDeployment@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAV56@@Z; ModernDeployment::Autopilot::Core::DeviceLinkUefi::LoadGuidFromUefi(std::wstring const &,std::wstring const &,std::wstring &)
0x18013ec6d  mov     ebx, eax
0x18013ec6f  lea     rcx, [rsp+0B8h+pguid]
0x18013ec77  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013ec7c  nop
0x18013ec7d  lea     rcx, [rsp+0B8h+var_90]
0x18013ec82  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013ec87  test    ebx, ebx
0x18013ec89  jns     loc_18013EDB0
0x18013ec8f  xorps   xmm0, xmm0
0x18013ec92  movups  xmmword ptr [rsp+0B8h+pguid.Data1], xmm0
0x18013ec9a  lea     rcx, [rsp+0B8h+pguid]; pguid
0x18013eca2  call    cs:__imp_CoCreateGuid
0x18013eca9  nop     dword ptr [rax+rax+00h]
0x18013ecae  mov     ebx, eax
0x18013ecb0  test    eax, eax
0x18013ecb2  jns     short loc_18013ECE2
0x18013ecb4  mov     rcx, [rsp+0B8h]; this
0x18013ecbc  mov     r9d, eax; char *
0x18013ecbf  lea     r8, aOnecoreuapAdmi_130; "onecoreuap\\admin\\moderndeployment\\au"...
0x18013ecc6  mov     edx, 3E8h; void *
0x18013eccb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013ecd0  nop
0x18013ecd1  lea     rcx, [rsp+0B8h+var_50]
0x18013ecd6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013ecdb  mov     eax, ebx
0x18013ecdd  jmp     loc_18013EF43
0x18013ece2  lea     rdx, aB3de75da819c4f; "{B3DE75DA-819C-4FD5-9F01-C3D49E8CBBD7}"
0x18013ece9  lea     rcx, [rsp+0B8h+var_70]
0x18013ecee  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18013ecf3  nop
0x18013ecf4  lea     rdx, aDevicelinkid; "DeviceLinkId"
0x18013ecfb  lea     rcx, [rsp+0B8h+var_90]
0x18013ed00  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18013ed05  nop
0x18013ed06  lea     r8, [rsp+0B8h+pguid]
0x18013ed0e  lea     rdx, [rsp+0B8h+var_70]
0x18013ed13  lea     rcx, [rsp+0B8h+var_90]
0x18013ed18  call    ?StoreGuidToUefi@DeviceLinkUefi@Core@Autopilot@ModernDeployment@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEBU_GUID@@@Z; ModernDeployment::Autopilot::Core::DeviceLinkUefi::StoreGuidToUefi(std::wstring const &,std::wstring const &,_GUID const &)
0x18013ed1d  mov     ebx, eax
0x18013ed1f  lea     rcx, [rsp+0B8h+var_90]
0x18013ed24  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013ed29  nop
0x18013ed2a  lea     rcx, [rsp+0B8h+var_70]
0x18013ed2f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013ed34  test    ebx, ebx
0x18013ed36  jns     short loc_18013ED66
0x18013ed38  mov     rcx, [rsp+0B8h]; this
0x18013ed40  mov     r9d, ebx; char *
0x18013ed43  lea     r8, aOnecoreuapAdmi_130; "onecoreuap\\admin\\moderndeployment\\au"...
0x18013ed4a  mov     edx, 3EDh; void *
0x18013ed4f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013ed54  nop
0x18013ed55  lea     rcx, [rsp+0B8h+var_50]
0x18013ed5a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013ed5f  mov     eax, ebx
0x18013ed61  jmp     loc_18013EF43
0x18013ed66  lea     r8, [rsp+0B8h+var_50]
0x18013ed6b  lea     rcx, [rsp+0B8h+pguid]; rguid
0x18013ed73  call    ?GetGuidStringFromGuid@DeviceLinkEncoding@Core@Autopilot@ModernDeployment@@SAJAEBU_GUID@@W4GuidFormat@1234@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ModernDeployment::Autopilot::Core::DeviceLinkEncoding::GetGuidStringFromGuid(_GUID const &,ModernDeployment::Autopilot::Core::DeviceLinkEncoding::GuidFormat,std::wstring &)
0x18013ed78  mov     ebx, eax
0x18013ed7a  test    eax, eax
0x18013ed7c  jns     loc_18013EE05
0x18013ed82  mov     rcx, [rsp+0B8h]; this
0x18013ed8a  mov     r9d, eax; char *
0x18013ed8d  lea     r8, aOnecoreuapAdmi_130; "onecoreuap\\admin\\moderndeployment\\au"...
0x18013ed94  mov     edx, 3EEh; void *
0x18013ed99  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013ed9e  nop
0x18013ed9f  lea     rcx, [rsp+0B8h+var_50]
0x18013eda4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013eda9  mov     eax, ebx
0x18013edab  jmp     loc_18013EF43
0x18013edb0  lea     rdx, aB3de75da819c4f; "{B3DE75DA-819C-4FD5-9F01-C3D49E8CBBD7}"
0x18013edb7  lea     rcx, [rsp+0B8h+var_90]
0x18013edbc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18013edc1  nop
0x18013edc2  lea     rdx, aDevicelinkcrea; "DeviceLinkCreationTimeUtc"
0x18013edc9  lea     rcx, [rsp+0B8h+var_70]
0x18013edce  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18013edd3  nop
0x18013edd4  mov     r8, rdi
0x18013edd7  lea     rdx, [rsp+0B8h+var_90]
0x18013eddc  lea     rcx, [rsp+0B8h+var_70]
0x18013ede1  call    ?LoadIso8601TimeFromUefi@DeviceLinkUefi@Core@Autopilot@ModernDeployment@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAV56@@Z; ModernDeployment::Autopilot::Core::DeviceLinkUefi::LoadIso8601TimeFromUefi(std::wstring const &,std::wstring const &,std::wstring &)
0x18013ede6  mov     ebx, eax
0x18013ede8  lea     rcx, [rsp+0B8h+var_70]
0x18013eded  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013edf2  nop
0x18013edf3  lea     rcx, [rsp+0B8h+var_90]
0x18013edf8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013edfd  test    ebx, ebx
0x18013edff  jns     loc_18013EEEE
0x18013ee05  xorps   xmm0, xmm0
0x18013ee08  movups  xmmword ptr [rsp+0B8h+pguid.Data1], xmm0
0x18013ee10  lea     rcx, [rsp+0B8h+pguid]; lpSystemTime
0x18013ee18  call    cs:__imp_GetSystemTime
0x18013ee1f  nop     dword ptr [rax+rax+00h]
0x18013ee24  xor     eax, eax
0x18013ee26  mov     word ptr [rsp+0B8h+pguid.Data4+6], ax
0x18013ee2e  mov     rdx, rdi
0x18013ee31  lea     rcx, [rsp+0B8h+pguid]
0x18013ee39  call    ?SystemTimeToIso8601String@DeviceLinkEncoding@Core@Autopilot@ModernDeployment@@SAJAEBU_SYSTEMTIME@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ModernDeployment::Autopilot::Core::DeviceLinkEncoding::SystemTimeToIso8601String(_SYSTEMTIME const &,std::wstring &)
0x18013ee3e  mov     ebx, eax
0x18013ee40  test    eax, eax
0x18013ee42  jns     short loc_18013EE72
0x18013ee44  mov     rcx, [rsp+0B8h]; this
0x18013ee4c  mov     r9d, eax; char *
0x18013ee4f  lea     r8, aOnecoreuapAdmi_130; "onecoreuap\\admin\\moderndeployment\\au"...
0x18013ee56  mov     edx, 405h; void *
0x18013ee5b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013ee60  nop
0x18013ee61  lea     rcx, [rsp+0B8h+var_50]
0x18013ee66  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013ee6b  mov     eax, ebx
0x18013ee6d  jmp     loc_18013EF43
0x18013ee72  lea     rdx, aB3de75da819c4f; "{B3DE75DA-819C-4FD5-9F01-C3D49E8CBBD7}"
0x18013ee79  lea     rcx, [rsp+0B8h+var_90]
0x18013ee7e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18013ee83  nop
0x18013ee84  lea     rdx, aDevicelinkcrea; "DeviceLinkCreationTimeUtc"
0x18013ee8b  lea     rcx, [rsp+0B8h+var_70]
0x18013ee90  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18013ee95  nop
0x18013ee96  mov     r8, rdi
0x18013ee99  lea     rdx, [rsp+0B8h+var_90]
0x18013ee9e  lea     rcx, [rsp+0B8h+var_70]
0x18013eea3  call    ?StoreSystemTimeToUefi@DeviceLinkUefi@Core@Autopilot@ModernDeployment@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00@Z; ModernDeployment::Autopilot::Core::DeviceLinkUefi::StoreSystemTimeToUefi(std::wstring const &,std::wstring const &,std::wstring const &)
0x18013eea8  mov     ebx, eax
0x18013eeaa  lea     rcx, [rsp+0B8h+var_70]
0x18013eeaf  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013eeb4  nop
0x18013eeb5  lea     rcx, [rsp+0B8h+var_90]
0x18013eeba  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013eebf  test    ebx, ebx
0x18013eec1  jns     short loc_18013EEEE
0x18013eec3  mov     rcx, [rsp+0B8h]; this
0x18013eecb  mov     r9d, ebx; char *
0x18013eece  lea     r8, aOnecoreuapAdmi_130; "onecoreuap\\admin\\moderndeployment\\au"...
0x18013eed5  mov     edx, 40Ah; void *
0x18013eeda  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013eedf  nop
0x18013eee0  lea     rcx, [rsp+0B8h+var_50]
0x18013eee5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013eeea  mov     eax, ebx
0x18013eeec  jmp     short loc_18013EF43
0x18013eeee  mov     r8, rsi
0x18013eef1  mov     edx, 1
0x18013eef6  lea     rcx, [rsp+0B8h+var_50]
0x18013eefb  call    ?EnsureGuidFormat@DeviceLinkEncoding@Core@Autopilot@ModernDeployment@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4GuidFormat@1234@AEAV56@@Z; ModernDeployment::Autopilot::Core::DeviceLinkEncoding::EnsureGuidFormat(std::wstring const &,ModernDeployment::Autopilot::Core::DeviceLinkEncoding::GuidFormat,std::wstring &)
0x18013ef00  mov     ebx, eax
0x18013ef02  test    eax, eax
0x18013ef04  jns     short loc_18013EF31
0x18013ef06  mov     rcx, [rsp+0B8h]; this
0x18013ef0e  mov     r9d, eax; char *
0x18013ef11  lea     r8, aOnecoreuapAdmi_130; "onecoreuap\\admin\\moderndeployment\\au"...
0x18013ef18  mov     edx, 40Eh; void *
0x18013ef1d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013ef22  nop
0x18013ef23  lea     rcx, [rsp+0B8h+var_50]
0x18013ef28  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013ef2d  mov     eax, ebx
0x18013ef2f  jmp     short loc_18013EF43
0x18013ef31  lea     rcx, [rsp+0B8h+var_50]
0x18013ef36  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013ef3b  xor     eax, eax
0x18013ef3d  jmp     short loc_18013EF43
0x18013ef3f  mov     eax, [rsp+0B8h+var_98]
0x18013ef43  mov     rcx, [rsp+0B8h+var_10]
0x18013ef4b  xor     rcx, rsp; StackCookie
0x18013ef4e  call    __security_check_cookie
0x18013ef53  lea     r11, [rsp+0B8h+var_8]
0x18013ef5b  mov     rbx, [r11+10h]
0x18013ef5f  mov     rsi, [r11+28h]
0x18013ef63  mov     rsp, r11
0x18013ef66  pop     rdi
0x18013ef67  retn
```
