# ModernDeployment::Autopilot::Core::DeviceLinkManager::ConfigureDeviceLinkAsync(HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *,Windows::Foundation::IAsyncOperationWithProgress<ModernDeployment::Autopilot::Core::ConfigureDeviceLinkResult,ModernDeployment::Autopilot::Core::DeviceLinkConfigurationStatus> * *)

- ea: `0x18012a620`
- end: `0x18012aa03`
- name: `?ConfigureDeviceLinkAsync@DeviceLinkManager@Core@Autopilot@ModernDeployment@@UEAAJPEAUHSTRING__@@0PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@PEAPEAU?$IAsyncOperationWithProgress@W4ConfigureDeviceLinkResult@Core@Autopilot@ModernDeployment@@W4DeviceLinkConfigurationStatus@234@@89@@Z`
- size: `995`
- prototype: `__int64 __fastcall(__int64, HSTRING, HSTRING, __int64 *, __int64)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000b820`
- `0x180067008`
- `0x180067a54`
- `0x18007755c`
- `0x1800801fc`
- `0x1800839bc`
- `0x1800868d4`
- `0x1800d9718`
- `0x1800da468`
- `0x1801270b0`
- `0x1801271bc`
- `0x1801278b8`
- `0x18012a620`
- `0x1801fa010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18012a7c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18012a850`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18012a7c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18012a850`

## string_xrefs

- `0x18012a67c`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkmanager.cpp`
- `0x18012a6a9`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkmanager.cpp`
- `0x18012a6d6`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkmanager.cpp`
- `0x18012a703`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkmanager.cpp`
- `0x18012a774`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkmanager.cpp`
- `0x18012a7f4`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkmanager.cpp`
- `0x18012a882`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall ModernDeployment::Autopilot::Core::DeviceLinkManager::ConfigureDeviceLinkAsync(
        __int64 a1,
        HSTRING a2,
        HSTRING a3,
        __int64 *a4,
        __int64 a5)
{
  __int64 v10; // rax
  int v11; // eax
  unsigned int v12; // ebx
  __int64 v13; // rcx
  PCWSTR StringRawBuffer; // rdx
  __int64 v15; // rcx
  PCWSTR v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // rax
  __int64 v19; // r8
  __int64 v20; // rcx
  int v21; // [rsp+20h] [rbp-E8h]
  __int64 *v22; // [rsp+30h] [rbp-D8h] BYREF
  _BYTE v23[12]; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v24; // [rsp+48h] [rbp-C0h] BYREF
  _BYTE v25[80]; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v26; // [rsp+A0h] [rbp-68h] BYREF
  _BYTE v27[16]; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v28; // [rsp+B8h] [rbp-50h]
  _BYTE v29[16]; // [rsp+C8h] [rbp-40h] BYREF
  __int64 v30; // [rsp+D8h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl'::`2'::impl) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A2,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\devicelink\\devicelinkmanager.cpp",
      (const char *)0x80004001LL,
      v21);
    return 2147500033LL;
  }
  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A4,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\devicelink\\devicelinkmanager.cpp",
      (const char *)0x80070057LL,
      v21);
    return 2147942487LL;
  }
  if ( !a3 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A5,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\devicelink\\devicelinkmanager.cpp",
      (const char *)0x80070057LL,
      v21);
    return 2147942487LL;
  }
  if ( !a5 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\devicelink\\devicelinkmanager.cpp",
      (const char *)0x80004003LL,
      v21);
    return 2147500035LL;
  }
  v24 = a1;
  if ( a1 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  v26 = 0;
  v22 = &v26;
  v10 = Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(&v22);
  v11 = Microsoft::WRL::AsWeak<ModernDeployment::Autopilot::Core::IDeviceProvisioningStatusCallback>(a1, v10);
  v12 = v11;
  if ( v11 >= 0 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
    std::wstring::wstring(v27, StringRawBuffer);
    if ( v28 )
    {
      v16 = WindowsGetStringRawBuffer(a3, 0);
      std::wstring::wstring(v29, v16);
      if ( v30 )
      {
        v22 = 0;
        if ( a4 )
        {
          *(_QWORD *)v23 = a4;
          Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<ModernDeployment::Autopilot::Core::IDiscoveryUrlRequestInfo *>>::InternalAddRef(v23);
          *(_QWORD *)v23 = 0;
          v22 = a4;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v23);
        }
        v18 = ModernDeployment::Autopilot::Core::DeviceLinkManager::ConfigureDeviceLinkAsync_::_3_::_lambda_1_::_lambda_1_(
                (unsigned int)v25,
                (unsigned int)&v26,
                (unsigned int)v27,
                (unsigned int)v29,
                (__int64)&v22);
        *(_DWORD *)v23 = 3;
        *(_QWORD *)&v23[4] = 128;
        v12 = Windows::Internal::MakeAsyncOperationWithProgress_Windows::Internal::ProgressResult_Windows::Internal::CBasicResult_enum_ModernDeployment::Autopilot::Core::ConfigureDeviceLinkResult_0__enum_ModernDeployment::Autopilot::Core::DeviceLinkConfigurationStatus__enum_ModernDeployment::Autopilot::Core::ConfigureDeviceLinkResult_enum_ModernDeployment::Autopilot::Core::DeviceLinkConfigurationStatus_Windows::Internal::ComTaskPoolHandler__ModernDeployment::Autopilot::Core::DeviceLinkManager::ConfigureDeviceLinkAsync_::_3_::_lambda_1___(
                v23,
                a5,
                v19,
                v18);
        ModernDeployment::Autopilot::Core::DeviceLinkManager::ConfigureDeviceLinkAsync_::_3_::_lambda_1_::__lambda_1_(v25);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22);
        std::wstring::_Tidy_deallocate(v29);
        std::wstring::_Tidy_deallocate(v27);
        v20 = v26;
        if ( v26 )
        {
          v26 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
        }
        goto LABEL_27;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1AF,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\devicelink\\devicelinkmanager.cpp",
        (const char *)0x80070057LL,
        v21);
      std::wstring::_Tidy_deallocate(v29);
      std::wstring::_Tidy_deallocate(v27);
      v17 = v26;
      if ( v26 )
      {
        v26 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1AD,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\devicelink\\devicelinkmanager.cpp",
        (const char *)0x80070057LL,
        v21);
      std::wstring::_Tidy_deallocate(v27);
      v15 = v26;
      if ( v26 )
      {
        v26 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      }
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v24);
    return 2147942487LL;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1AA,
    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\devicelink\\devicelinkmanager.cpp",
    (const char *)(unsigned int)v11,
    v21);
  v13 = v26;
  if ( v26 )
  {
    v26 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  }
LABEL_27:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v24);
  return v12;
}

```

## disassembly

```asm
0x18012a620  mov     [rsp+arg_0], rbx
0x18012a625  mov     [rsp+arg_18], rsi
0x18012a62a  push    rdi
0x18012a62b  push    r14
0x18012a62d  push    r15
0x18012a62f  sub     rsp, 0F0h
0x18012a636  mov     rax, cs:__security_cookie
0x18012a63d  xor     rax, rsp
0x18012a640  mov     [rsp+108h+var_20], rax
0x18012a648  mov     rdi, r9
0x18012a64b  mov     r14, r8
0x18012a64e  mov     rsi, rdx
0x18012a651  mov     rbx, rcx
0x18012a654  mov     r15, [rsp+108h+arg_20]
0x18012a65c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x18012a663  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x18012a668  test    al, al
0x18012a66a  jnz     short loc_18012A694
0x18012a66c  mov     rcx, [rsp+108h]; this
0x18012a674  mov     ebx, 80004001h
0x18012a679  mov     r9d, ebx; char *
0x18012a67c  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\moderndeployment\\au"...
0x18012a683  mov     edx, 1A2h; void *
0x18012a688  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012a68d  mov     eax, ebx
0x18012a68f  jmp     loc_18012A9D9
0x18012a694  test    rsi, rsi
0x18012a697  jnz     short loc_18012A6C1
0x18012a699  mov     rcx, [rsp+108h]; this
0x18012a6a1  mov     ebx, 80070057h
0x18012a6a6  mov     r9d, ebx; char *
0x18012a6a9  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\moderndeployment\\au"...
0x18012a6b0  mov     edx, 1A4h; void *
0x18012a6b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012a6ba  mov     eax, ebx
0x18012a6bc  jmp     loc_18012A9D9
0x18012a6c1  test    r14, r14
0x18012a6c4  jnz     short loc_18012A6EE
0x18012a6c6  mov     rcx, [rsp+108h]; this
0x18012a6ce  mov     ebx, 80070057h
0x18012a6d3  mov     r9d, ebx; char *
0x18012a6d6  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\moderndeployment\\au"...
0x18012a6dd  mov     edx, 1A5h; void *
0x18012a6e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012a6e7  mov     eax, ebx
0x18012a6e9  jmp     loc_18012A9D9
0x18012a6ee  test    r15, r15
0x18012a6f1  jnz     short loc_18012A71B
0x18012a6f3  mov     rcx, [rsp+108h]; this
0x18012a6fb  mov     ebx, 80004003h
0x18012a700  mov     r9d, ebx; char *
0x18012a703  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\moderndeployment\\au"...
0x18012a70a  mov     edx, 1A6h; void *
0x18012a70f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012a714  mov     eax, ebx
0x18012a716  jmp     loc_18012A9D9
0x18012a71b  mov     [rsp+108h+var_C0], rbx
0x18012a720  test    rbx, rbx
0x18012a723  jz      short loc_18012A735
0x18012a725  mov     rax, [rbx]
0x18012a728  mov     rcx, rbx
0x18012a72b  mov     rax, [rax+8]
0x18012a72f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012a734  nop
0x18012a735  mov     [rsp+108h+var_68], 0
0x18012a741  lea     rax, [rsp+108h+var_68]
0x18012a749  mov     [rsp+108h+var_D8], rax
0x18012a74e  lea     rcx, [rsp+108h+var_D8]
0x18012a753  call    ??B?$ComPtrRef@VWeakRef@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAAPEAVWeakRef@23@XZ; Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(void)
0x18012a758  mov     rdx, rax
0x18012a75b  mov     rcx, rbx
0x18012a75e  call    ??$AsWeak@UIDeviceProvisioningStatusCallback@Core@Autopilot@ModernDeployment@@@WRL@Microsoft@@YAJPEAUIDeviceProvisioningStatusCallback@Core@Autopilot@ModernDeployment@@PEAVWeakRef@01@@Z; Microsoft::WRL::AsWeak<ModernDeployment::Autopilot::Core::IDeviceProvisioningStatusCallback>(ModernDeployment::Autopilot::Core::IDeviceProvisioningStatusCallback *,Microsoft::WRL::WeakRef *)
0x18012a763  mov     ebx, eax
0x18012a765  test    eax, eax
0x18012a767  jns     short loc_18012A7BD
0x18012a769  mov     rcx, [rsp+108h]; this
0x18012a771  mov     r9d, eax; char *
0x18012a774  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\moderndeployment\\au"...
0x18012a77b  mov     edx, 1AAh; void *
0x18012a780  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012a785  nop
0x18012a786  mov     rcx, [rsp+108h+var_68]
0x18012a78e  test    rcx, rcx
0x18012a791  jz      short loc_18012A7AC
0x18012a793  mov     [rsp+108h+var_68], 0
0x18012a79f  mov     rax, [rcx]
0x18012a7a2  mov     rax, [rax+10h]
0x18012a7a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012a7ab  nop
0x18012a7ac  lea     rcx, [rsp+108h+var_C0]
0x18012a7b1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18012a7b6  mov     eax, ebx
0x18012a7b8  jmp     loc_18012A9D9
0x18012a7bd  xor     edx, edx; length
0x18012a7bf  mov     rcx, rsi; string
0x18012a7c2  call    cs:__imp_WindowsGetStringRawBuffer
0x18012a7c8  mov     rdx, rax
0x18012a7cb  lea     rcx, [rsp+108h+var_60]
0x18012a7d3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18012a7d8  nop
0x18012a7d9  cmp     [rsp+108h+var_50], 0
0x18012a7e2  jnz     short loc_18012A84B
0x18012a7e4  mov     rcx, [rsp+108h]; this
0x18012a7ec  mov     ebx, 80070057h
0x18012a7f1  mov     r9d, ebx; char *
0x18012a7f4  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\moderndeployment\\au"...
0x18012a7fb  mov     edx, 1ADh; void *
0x18012a800  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012a805  nop
0x18012a806  lea     rcx, [rsp+108h+var_60]
0x18012a80e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012a813  nop
0x18012a814  mov     rcx, [rsp+108h+var_68]
0x18012a81c  test    rcx, rcx
0x18012a81f  jz      short loc_18012A83A
0x18012a821  mov     [rsp+108h+var_68], 0
0x18012a82d  mov     rax, [rcx]
0x18012a830  mov     rax, [rax+10h]
0x18012a834  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012a839  nop
0x18012a83a  lea     rcx, [rsp+108h+var_C0]
0x18012a83f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18012a844  mov     eax, ebx
0x18012a846  jmp     loc_18012A9D9
0x18012a84b  xor     edx, edx; length
0x18012a84d  mov     rcx, r14; string
0x18012a850  call    cs:__imp_WindowsGetStringRawBuffer
0x18012a856  mov     rdx, rax
0x18012a859  lea     rcx, [rsp+108h+var_40]
0x18012a861  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18012a866  nop
0x18012a867  cmp     [rsp+108h+var_30], 0
0x18012a870  jnz     short loc_18012A8E7
0x18012a872  mov     rcx, [rsp+108h]; this
0x18012a87a  mov     ebx, 80070057h
0x18012a87f  mov     r9d, ebx; char *
0x18012a882  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\moderndeployment\\au"...
0x18012a889  mov     edx, 1AFh; void *
0x18012a88e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012a893  nop
0x18012a894  lea     rcx, [rsp+108h+var_40]
0x18012a89c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012a8a1  nop
0x18012a8a2  lea     rcx, [rsp+108h+var_60]
0x18012a8aa  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012a8af  nop
0x18012a8b0  mov     rcx, [rsp+108h+var_68]
0x18012a8b8  test    rcx, rcx
0x18012a8bb  jz      short loc_18012A8D6
0x18012a8bd  mov     [rsp+108h+var_68], 0
0x18012a8c9  mov     rax, [rcx]
0x18012a8cc  mov     rax, [rax+10h]
0x18012a8d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012a8d5  nop
0x18012a8d6  lea     rcx, [rsp+108h+var_C0]
0x18012a8db  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18012a8e0  mov     eax, ebx
0x18012a8e2  jmp     loc_18012A9D9
0x18012a8e7  mov     [rsp+108h+var_D8], 0
0x18012a8f0  test    rdi, rdi
0x18012a8f3  jz      short loc_18012A91C
0x18012a8f5  mov     [rsp+108h+var_D0], rdi
0x18012a8fa  lea     rcx, [rsp+108h+var_D0]
0x18012a8ff  call    ?InternalAddRef@?$ComPtr@U?$IAsyncOperationCompletedHandler@PEAUIDiscoveryUrlRequestInfo@Core@Autopilot@ModernDeployment@@@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<ModernDeployment::Autopilot::Core::IDiscoveryUrlRequestInfo *>>::InternalAddRef(void)
0x18012a904  mov     [rsp+108h+var_D0], 0
0x18012a90d  mov     [rsp+108h+var_D8], rdi
0x18012a912  lea     rcx, [rsp+108h+var_D0]
0x18012a917  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18012a91c  lea     rax, [rsp+108h+var_D8]
0x18012a921  mov     qword ptr [rsp+108h+var_E8], rax
0x18012a926  lea     r9, [rsp+108h+var_40]
0x18012a92e  lea     r8, [rsp+108h+var_60]
0x18012a936  lea     rdx, [rsp+108h+var_68]
0x18012a93e  lea     rcx, [rsp+108h+var_B8]
0x18012a943  call    _ModernDeployment__Autopilot__Core__DeviceLinkManager__ConfigureDeviceLinkAsync____3____lambda_1____lambda_1_
0x18012a948  nop
0x18012a949  mov     dword ptr [rsp+108h+var_D0], 3
0x18012a951  mov     [rsp+108h+var_D0+4], 80h
0x18012a95a  mov     r9, rax
0x18012a95d  mov     rdx, r15
0x18012a960  lea     rcx, [rsp+108h+var_D0]
0x18012a965  call    Windows__Internal__MakeAsyncOperationWithProgress_Windows__Internal__ProgressResult_Windows__Internal__CBasicResult_enum_ModernDeployment__Autopilot__Core__ConfigureDeviceLinkResult_0__enum_ModernDeployment__Autopilot__Core__DeviceLinkConfigurationStatus__enum_ModernDeployment__Autopilot__Core__ConfigureDeviceLinkResult_enum_ModernDeployment__Autopilot__Core__DeviceLinkConfigurationStatus_Windows__Internal__ComTaskPoolHandler__ModernDeployment__Autopilot__Core__DeviceLinkManager__ConfigureDeviceLinkAsync____3____lambda_1___
0x18012a96a  mov     ebx, eax
0x18012a96c  lea     rcx, [rsp+108h+var_B8]
0x18012a971  call    _ModernDeployment__Autopilot__Core__DeviceLinkManager__ConfigureDeviceLinkAsync____3____lambda_1_____lambda_1_
0x18012a976  nop
0x18012a977  lea     rcx, [rsp+108h+var_D8]
0x18012a97c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18012a981  nop
0x18012a982  lea     rcx, [rsp+108h+var_40]
0x18012a98a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012a98f  nop
0x18012a990  lea     rcx, [rsp+108h+var_60]
0x18012a998  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012a99d  nop
0x18012a99e  mov     rcx, [rsp+108h+var_68]
0x18012a9a6  test    rcx, rcx
0x18012a9a9  jz      short loc_18012A9C4
0x18012a9ab  mov     [rsp+108h+var_68], 0
0x18012a9b7  mov     rax, [rcx]
0x18012a9ba  mov     rax, [rax+10h]
0x18012a9be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012a9c3  nop
0x18012a9c4  lea     rcx, [rsp+108h+var_C0]
0x18012a9c9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18012a9ce  mov     eax, ebx
0x18012a9d0  jmp     short loc_18012A9D9
0x18012a9d2  mov     eax, dword ptr [rsp+108h+var_68]
0x18012a9d9  mov     rcx, [rsp+108h+var_20]
0x18012a9e1  xor     rcx, rsp; StackCookie
0x18012a9e4  call    __security_check_cookie
0x18012a9e9  lea     r11, [rsp+108h+var_18]
0x18012a9f1  mov     rbx, [r11+20h]
0x18012a9f5  mov     rsi, [r11+38h]
0x18012a9f9  mov     rsp, r11
0x18012a9fc  pop     r15
0x18012a9fe  pop     r14
0x18012aa00  pop     rdi
0x18012aa01  retn
```
