# ModernDeployment::Autopilot::Core::DeviceLinkManager::ConfigureDeviceLinkAsync(HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *,Windows::Foundation::IAsyncOperationWithProgress<ModernDeployment::Autopilot::Core::ConfigureDeviceLinkResult,ModernDeployment::Autopilot::Core::DeviceLinkConfigurationStatus> * *)

- ea: `0x18012e2c0`
- end: `0x18012e6af`
- name: `?ConfigureDeviceLinkAsync@DeviceLinkManager@Core@Autopilot@ModernDeployment@@UEAAJPEAUHSTRING__@@0PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@PEAPEAU?$IAsyncOperationWithProgress@W4ConfigureDeviceLinkResult@Core@Autopilot@ModernDeployment@@W4DeviceLinkConfigurationStatus@234@@89@@Z`
- size: `1007`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000b8f0`
- `0x180067398`
- `0x180067e54`
- `0x180077de0`
- `0x180080c10`
- `0x180084574`
- `0x180087634`
- `0x1800dbea4`
- `0x1800dcc20`
- `0x18012ad34`
- `0x18012ae44`
- `0x18012b560`
- `0x18012e2c0`
- `0x180200010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18012e462`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18012e4f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18012e462`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18012e4f6`

## string_xrefs

- `0x18012e31c`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkmanager.cpp`
- `0x18012e349`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkmanager.cpp`
- `0x18012e376`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkmanager.cpp`
- `0x18012e3a3`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkmanager.cpp`
- `0x18012e414`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkmanager.cpp`
- `0x18012e49a`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkmanager.cpp`
- `0x18012e52e`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
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
      (void *)0x19D,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\devicelink\\devicelinkmanager.cpp",
      (const char *)0x80004001LL,
      v21);
    return 2147500033LL;
  }
  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x19F,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\devicelink\\devicelinkmanager.cpp",
      (const char *)0x80070057LL,
      v21);
    return 2147942487LL;
  }
  if ( !a3 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A0,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\devicelink\\devicelinkmanager.cpp",
      (const char *)0x80070057LL,
      v21);
    return 2147942487LL;
  }
  if ( !a5 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A1,
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
        (void *)0x1AA,
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
        (void *)0x1A8,
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
    (void *)0x1A5,
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
0x18012e2c0  mov     [rsp+arg_0], rbx
0x18012e2c5  mov     [rsp+arg_18], rsi
0x18012e2ca  push    rdi
0x18012e2cb  push    r14
0x18012e2cd  push    r15
0x18012e2cf  sub     rsp, 0F0h
0x18012e2d6  mov     rax, cs:__security_cookie
0x18012e2dd  xor     rax, rsp
0x18012e2e0  mov     [rsp+108h+var_20], rax
0x18012e2e8  mov     rdi, r9
0x18012e2eb  mov     r14, r8
0x18012e2ee  mov     rsi, rdx
0x18012e2f1  mov     rbx, rcx
0x18012e2f4  mov     r15, [rsp+108h+arg_20]
0x18012e2fc  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x18012e303  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x18012e308  test    al, al
0x18012e30a  jnz     short loc_18012E334
0x18012e30c  mov     rcx, [rsp+108h]; this
0x18012e314  mov     ebx, 80004001h
0x18012e319  mov     r9d, ebx; char *
0x18012e31c  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\moderndeployment\\au"...
0x18012e323  mov     edx, 19Dh; void *
0x18012e328  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012e32d  mov     eax, ebx
0x18012e32f  jmp     loc_18012E685
0x18012e334  test    rsi, rsi
0x18012e337  jnz     short loc_18012E361
0x18012e339  mov     rcx, [rsp+108h]; this
0x18012e341  mov     ebx, 80070057h
0x18012e346  mov     r9d, ebx; char *
0x18012e349  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\moderndeployment\\au"...
0x18012e350  mov     edx, 19Fh; void *
0x18012e355  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012e35a  mov     eax, ebx
0x18012e35c  jmp     loc_18012E685
0x18012e361  test    r14, r14
0x18012e364  jnz     short loc_18012E38E
0x18012e366  mov     rcx, [rsp+108h]; this
0x18012e36e  mov     ebx, 80070057h
0x18012e373  mov     r9d, ebx; char *
0x18012e376  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\moderndeployment\\au"...
0x18012e37d  mov     edx, 1A0h; void *
0x18012e382  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012e387  mov     eax, ebx
0x18012e389  jmp     loc_18012E685
0x18012e38e  test    r15, r15
0x18012e391  jnz     short loc_18012E3BB
0x18012e393  mov     rcx, [rsp+108h]; this
0x18012e39b  mov     ebx, 80004003h
0x18012e3a0  mov     r9d, ebx; char *
0x18012e3a3  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\moderndeployment\\au"...
0x18012e3aa  mov     edx, 1A1h; void *
0x18012e3af  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012e3b4  mov     eax, ebx
0x18012e3b6  jmp     loc_18012E685
0x18012e3bb  mov     [rsp+108h+var_C0], rbx
0x18012e3c0  test    rbx, rbx
0x18012e3c3  jz      short loc_18012E3D5
0x18012e3c5  mov     rax, [rbx]
0x18012e3c8  mov     rcx, rbx
0x18012e3cb  mov     rax, [rax+8]
0x18012e3cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012e3d4  nop
0x18012e3d5  mov     [rsp+108h+var_68], 0
0x18012e3e1  lea     rax, [rsp+108h+var_68]
0x18012e3e9  mov     [rsp+108h+var_D8], rax
0x18012e3ee  lea     rcx, [rsp+108h+var_D8]
0x18012e3f3  call    ??B?$ComPtrRef@VWeakRef@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAAPEAVWeakRef@23@XZ; Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(void)
0x18012e3f8  mov     rdx, rax
0x18012e3fb  mov     rcx, rbx
0x18012e3fe  call    ??$AsWeak@UIDeviceProvisioningStatusCallback@Core@Autopilot@ModernDeployment@@@WRL@Microsoft@@YAJPEAUIDeviceProvisioningStatusCallback@Core@Autopilot@ModernDeployment@@PEAVWeakRef@01@@Z; Microsoft::WRL::AsWeak<ModernDeployment::Autopilot::Core::IDeviceProvisioningStatusCallback>(ModernDeployment::Autopilot::Core::IDeviceProvisioningStatusCallback *,Microsoft::WRL::WeakRef *)
0x18012e403  mov     ebx, eax
0x18012e405  test    eax, eax
0x18012e407  jns     short loc_18012E45D
0x18012e409  mov     rcx, [rsp+108h]; this
0x18012e411  mov     r9d, eax; char *
0x18012e414  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\moderndeployment\\au"...
0x18012e41b  mov     edx, 1A5h; void *
0x18012e420  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012e425  nop
0x18012e426  mov     rcx, [rsp+108h+var_68]
0x18012e42e  test    rcx, rcx
0x18012e431  jz      short loc_18012E44C
0x18012e433  mov     [rsp+108h+var_68], 0
0x18012e43f  mov     rax, [rcx]
0x18012e442  mov     rax, [rax+10h]
0x18012e446  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012e44b  nop
0x18012e44c  lea     rcx, [rsp+108h+var_C0]
0x18012e451  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18012e456  mov     eax, ebx
0x18012e458  jmp     loc_18012E685
0x18012e45d  xor     edx, edx; length
0x18012e45f  mov     rcx, rsi; string
0x18012e462  call    cs:__imp_WindowsGetStringRawBuffer
0x18012e469  nop     dword ptr [rax+rax+00h]
0x18012e46e  mov     rdx, rax
0x18012e471  lea     rcx, [rsp+108h+var_60]
0x18012e479  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18012e47e  nop
0x18012e47f  cmp     [rsp+108h+var_50], 0
0x18012e488  jnz     short loc_18012E4F1
0x18012e48a  mov     rcx, [rsp+108h]; this
0x18012e492  mov     ebx, 80070057h
0x18012e497  mov     r9d, ebx; char *
0x18012e49a  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\moderndeployment\\au"...
0x18012e4a1  mov     edx, 1A8h; void *
0x18012e4a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012e4ab  nop
0x18012e4ac  lea     rcx, [rsp+108h+var_60]
0x18012e4b4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012e4b9  nop
0x18012e4ba  mov     rcx, [rsp+108h+var_68]
0x18012e4c2  test    rcx, rcx
0x18012e4c5  jz      short loc_18012E4E0
0x18012e4c7  mov     [rsp+108h+var_68], 0
0x18012e4d3  mov     rax, [rcx]
0x18012e4d6  mov     rax, [rax+10h]
0x18012e4da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012e4df  nop
0x18012e4e0  lea     rcx, [rsp+108h+var_C0]
0x18012e4e5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18012e4ea  mov     eax, ebx
0x18012e4ec  jmp     loc_18012E685
0x18012e4f1  xor     edx, edx; length
0x18012e4f3  mov     rcx, r14; string
0x18012e4f6  call    cs:__imp_WindowsGetStringRawBuffer
0x18012e4fd  nop     dword ptr [rax+rax+00h]
0x18012e502  mov     rdx, rax
0x18012e505  lea     rcx, [rsp+108h+var_40]
0x18012e50d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18012e512  nop
0x18012e513  cmp     [rsp+108h+var_30], 0
0x18012e51c  jnz     short loc_18012E593
0x18012e51e  mov     rcx, [rsp+108h]; this
0x18012e526  mov     ebx, 80070057h
0x18012e52b  mov     r9d, ebx; char *
0x18012e52e  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\moderndeployment\\au"...
0x18012e535  mov     edx, 1AAh; void *
0x18012e53a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012e53f  nop
0x18012e540  lea     rcx, [rsp+108h+var_40]
0x18012e548  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012e54d  nop
0x18012e54e  lea     rcx, [rsp+108h+var_60]
0x18012e556  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012e55b  nop
0x18012e55c  mov     rcx, [rsp+108h+var_68]
0x18012e564  test    rcx, rcx
0x18012e567  jz      short loc_18012E582
0x18012e569  mov     [rsp+108h+var_68], 0
0x18012e575  mov     rax, [rcx]
0x18012e578  mov     rax, [rax+10h]
0x18012e57c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012e581  nop
0x18012e582  lea     rcx, [rsp+108h+var_C0]
0x18012e587  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18012e58c  mov     eax, ebx
0x18012e58e  jmp     loc_18012E685
0x18012e593  mov     [rsp+108h+var_D8], 0
0x18012e59c  test    rdi, rdi
0x18012e59f  jz      short loc_18012E5C8
0x18012e5a1  mov     [rsp+108h+var_D0], rdi
0x18012e5a6  lea     rcx, [rsp+108h+var_D0]
0x18012e5ab  call    ?InternalAddRef@?$ComPtr@U?$IAsyncOperationCompletedHandler@PEAUIDiscoveryUrlRequestInfo@Core@Autopilot@ModernDeployment@@@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<ModernDeployment::Autopilot::Core::IDiscoveryUrlRequestInfo *>>::InternalAddRef(void)
0x18012e5b0  mov     [rsp+108h+var_D0], 0
0x18012e5b9  mov     [rsp+108h+var_D8], rdi
0x18012e5be  lea     rcx, [rsp+108h+var_D0]
0x18012e5c3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18012e5c8  lea     rax, [rsp+108h+var_D8]
0x18012e5cd  mov     qword ptr [rsp+108h+var_E8], rax
0x18012e5d2  lea     r9, [rsp+108h+var_40]
0x18012e5da  lea     r8, [rsp+108h+var_60]
0x18012e5e2  lea     rdx, [rsp+108h+var_68]
0x18012e5ea  lea     rcx, [rsp+108h+var_B8]
0x18012e5ef  call    _ModernDeployment__Autopilot__Core__DeviceLinkManager__ConfigureDeviceLinkAsync____3____lambda_1____lambda_1_
0x18012e5f4  nop
0x18012e5f5  mov     dword ptr [rsp+108h+var_D0], 3
0x18012e5fd  mov     [rsp+108h+var_D0+4], 80h
0x18012e606  mov     r9, rax
0x18012e609  mov     rdx, r15
0x18012e60c  lea     rcx, [rsp+108h+var_D0]
0x18012e611  call    Windows__Internal__MakeAsyncOperationWithProgress_Windows__Internal__ProgressResult_Windows__Internal__CBasicResult_enum_ModernDeployment__Autopilot__Core__ConfigureDeviceLinkResult_0__enum_ModernDeployment__Autopilot__Core__DeviceLinkConfigurationStatus__enum_ModernDeployment__Autopilot__Core__ConfigureDeviceLinkResult_enum_ModernDeployment__Autopilot__Core__DeviceLinkConfigurationStatus_Windows__Internal__ComTaskPoolHandler__ModernDeployment__Autopilot__Core__DeviceLinkManager__ConfigureDeviceLinkAsync____3____lambda_1___
0x18012e616  mov     ebx, eax
0x18012e618  lea     rcx, [rsp+108h+var_B8]
0x18012e61d  call    _ModernDeployment__Autopilot__Core__DeviceLinkManager__ConfigureDeviceLinkAsync____3____lambda_1_____lambda_1_
0x18012e622  nop
0x18012e623  lea     rcx, [rsp+108h+var_D8]
0x18012e628  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18012e62d  nop
0x18012e62e  lea     rcx, [rsp+108h+var_40]
0x18012e636  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012e63b  nop
0x18012e63c  lea     rcx, [rsp+108h+var_60]
0x18012e644  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012e649  nop
0x18012e64a  mov     rcx, [rsp+108h+var_68]
0x18012e652  test    rcx, rcx
0x18012e655  jz      short loc_18012E670
0x18012e657  mov     [rsp+108h+var_68], 0
0x18012e663  mov     rax, [rcx]
0x18012e666  mov     rax, [rax+10h]
0x18012e66a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012e66f  nop
0x18012e670  lea     rcx, [rsp+108h+var_C0]
0x18012e675  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18012e67a  mov     eax, ebx
0x18012e67c  jmp     short loc_18012E685
0x18012e67e  mov     eax, dword ptr [rsp+108h+var_68]
0x18012e685  mov     rcx, [rsp+108h+var_20]
0x18012e68d  xor     rcx, rsp; StackCookie
0x18012e690  call    __security_check_cookie
0x18012e695  lea     r11, [rsp+108h+var_18]
0x18012e69d  mov     rbx, [r11+20h]
0x18012e6a1  mov     rsi, [r11+38h]
0x18012e6a5  mov     rsp, r11
0x18012e6a8  pop     r15
0x18012e6aa  pop     r14
0x18012e6ac  pop     rdi
0x18012e6ad  retn
```
