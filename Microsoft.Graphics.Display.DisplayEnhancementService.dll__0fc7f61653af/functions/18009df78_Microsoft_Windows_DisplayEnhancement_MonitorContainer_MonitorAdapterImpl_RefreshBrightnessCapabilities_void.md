# Microsoft::Windows::DisplayEnhancement::MonitorContainer::MonitorAdapterImpl::RefreshBrightnessCapabilities(void)

- ea: `0x18009df78`
- end: `0x18009e87a`
- name: `?RefreshBrightnessCapabilities@MonitorAdapterImpl@MonitorContainer@DisplayEnhancement@Windows@Microsoft@@AEAAXXZ`
- size: `2306`
- prototype: `void __fastcall(Microsoft::Windows::DisplayEnhancement::MonitorContainer::MonitorAdapterImpl *__hidden this)`
- caller_count: `4`
- callee_count: `35`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18009b6d0`
- `0x18009b8f0`
- `0x18009bd60`
- `0x18009d6c0`

## callees

- `0x180005860`
- `0x180009014`
- `0x180009a84`
- `0x180009f68`
- `0x18000c234`
- `0x18000f778`
- `0x18000fb14`
- `0x1800121d0`
- `0x180013138`
- `0x180013578`
- `0x180029350`
- `0x180029404`
- `0x1800357d8`
- `0x180037470`
- `0x1800374b4`
- `0x18003b948`
- `0x18003c044`
- `0x18005b70c`
- `0x180063c54`
- `0x180063dd4`
- `0x180066344`
- `0x1800663d4`
- `0x1800804d0`
- `0x18009a150`
- `0x18009ae78`
- `0x18009b62c`
- `0x18009b67c`
- `0x18009c87c`
- `0x18009c8d0`
- `0x18009c934`
- `0x18009cd4c`
- `0x18009df78`
- `0x18009f3d0`
- `0x18009f498`
- `0x1800ed010`

## string_xrefs

- `0x18009e7f0`: `onecoreuap\drivers\mobilepc\displayenhancement\service\displayadapter\lib\displayadapter.cpp`
- `0x18009e805`: `onecoreuap\drivers\mobilepc\displayenhancement\service\displayadapter\lib\displayadapter.cpp`
- `0x18009e82c`: `onecoreuap\drivers\mobilepc\displayenhancement\service\displayadapter\lib\displayadapter.cpp`
- `0x18009e853`: `onecoreuap\drivers\mobilepc\displayenhancement\service\displayadapter\lib\displayadapter.cpp`
- `0x18009e868`: `onecoreuap\drivers\mobilepc\displayenhancement\service\displayadapter\lib\displayadapter.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall Microsoft::Windows::DisplayEnhancement::MonitorContainer::MonitorAdapterImpl::RefreshBrightnessCapabilities(
        Microsoft::Windows::DisplayEnhancement::MonitorContainer::MonitorAdapterImpl *this,
        __int64 a2,
        __int64 a3)
{
  Microsoft::Windows::DisplayEnhancement::MonitorContainer::MonitorAdapterImpl *v3; // rsi
  char *v4; // r12
  int v5; // eax
  int v6; // eax
  int v7; // edi
  __int64 NitRangesFromDisplayMonitorInternal; // rax
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // rax
  __int64 v12; // r9
  __int64 v13; // rdx
  int DisplayBrightnessLevel; // r15d
  const char *v15; // r9
  int v16; // ecx
  unsigned int v17; // r8d
  _DWORD *v18; // rdx
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // rax
  __int64 v24; // rdx
  __int64 v25; // rax
  __int64 v26; // r10
  __int64 v27; // r8
  __int64 v28; // r9
  __int64 v29; // rax
  __int64 v30; // r8
  __int64 v31; // rax
  __int64 v32; // r8
  __int64 v33; // rdx
  const char *v34; // r9
  unsigned int v35; // r15d
  int v36; // eax
  unsigned int v37; // edi
  int v38; // eax
  __int64 *v39; // rax
  __int64 (__fastcall ***v40)(_QWORD, GUID *, __int64); // rcx
  unsigned int v41; // eax
  unsigned int v42; // eax
  int v43; // [rsp+20h] [rbp-108h]
  _BYTE v44[4]; // [rsp+50h] [rbp-D8h] BYREF
  unsigned int v45; // [rsp+54h] [rbp-D4h] BYREF
  int v46; // [rsp+58h] [rbp-D0h] BYREF
  int v47; // [rsp+5Ch] [rbp-CCh] BYREF
  int v48; // [rsp+60h] [rbp-C8h] BYREF
  unsigned int v49; // [rsp+64h] [rbp-C4h] BYREF
  int v50; // [rsp+68h] [rbp-C0h] BYREF
  __int64 v51; // [rsp+70h] [rbp-B8h] BYREF
  int v52; // [rsp+78h] [rbp-B0h] BYREF
  int v53; // [rsp+7Ch] [rbp-ACh]
  __int64 v54; // [rsp+80h] [rbp-A8h] BYREF
  __int128 v55; // [rsp+88h] [rbp-A0h] BYREF
  __int64 v56; // [rsp+98h] [rbp-90h]
  Microsoft::Windows::DisplayEnhancement::MonitorContainer::MonitorAdapterImpl *v57; // [rsp+A0h] [rbp-88h] BYREF
  std::_Ref_count_base *v58; // [rsp+A8h] [rbp-80h]
  __int64 (__fastcall ***v59)(_QWORD, GUID *, __int64); // [rsp+B0h] [rbp-78h] BYREF
  unsigned __int64 v60; // [rsp+B8h] [rbp-70h] BYREF
  std::_Ref_count_base *v61; // [rsp+C0h] [rbp-68h]
  std::_Ref_count_base *v62[2]; // [rsp+C8h] [rbp-60h] BYREF
  __int64 v63; // [rsp+D8h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+0h]

  v3 = this;
  v57 = this;
  v4 = (char *)this + 8;
  Microsoft::Windows::DisplayEnhancement::MonitorContainer::MonitorAdapterImpl::GetDisplayMonitorFromDeviceId(
    &v59,
    (__int64)this + 8,
    a3);
  v54 = 0;
  v5 = Microsoft::WRL::ComPtr<Windows::Devices::Display::IDisplayMonitor>::As<Windows::Devices::Display::Internal::IDisplayMonitorInternal>(
         &v59,
         (__int64)&v54);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xD1,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\displayadapter\\lib\\displayadapter.cpp",
      (const char *)(unsigned int)v5,
      v43);
  v50 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v54 + 80LL))(v54, &v50);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xD4,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\displayadapter\\lib\\displayadapter.cpp",
      (const char *)(unsigned int)v6,
      v43);
  if ( v50 )
  {
    if ( v50 == 1 )
    {
      v7 = 1;
    }
    else
    {
      if ( (unsigned int)(v50 - 2) > 1 )
      {
        v41 = wil::verify_hresult<long>(2147942487LL);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x32E,
          (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\displayadapter\\lib\\displayadapter.cpp",
          (const char *)v41,
          v43);
      }
      v7 = 2;
    }
  }
  else
  {
    v7 = 0;
  }
  v46 = v7;
  v55 = 0;
  v56 = 0;
  if ( v7 == 2 )
  {
    v51 = v54;
    if ( v54 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 8LL))(v54);
    NitRangesFromDisplayMonitorInternal = Microsoft::Windows::DisplayEnhancement::MonitorContainer::MonitorAdapterImpl::GetNitRangesFromDisplayMonitorInternal(
                                            v62,
                                            &v51);
    std::vector<Microsoft::Windows::DisplayEnhancement::Foundation::MilliNitRange>::operator=(
      &v55,
      NitRangesFromDisplayMonitorInternal);
    std::vector<Microsoft::Windows::DisplayEnhancement::Transition::TransitionAccelerationTableEntry>::_Tidy(v62);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SenBfCd2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SenBfCd2>::GetImpl'::`2'::impl)
      && (_QWORD)v55 == *((_QWORD *)&v55 + 1) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_5d1638309ca23a32fb5c63fc7ed00874_Traceguids);
      }
      v7 = 0;
      v46 = 0;
    }
  }
  else if ( v7 == 1 )
  {
    v60 = 0x186A000000000LL;
    v61 = (std::_Ref_count_base *)1;
    std::vector<Microsoft::Windows::DisplayEnhancement::Foundation::MilliNitRange>::_Emplace_reallocate<Microsoft::Windows::DisplayEnhancement::Foundation::MilliNitRange const &>(
      &v55,
      0,
      &v60);
  }
  else if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ExternalBrightness>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ExternalBrightness>::GetImpl'::`2'::impl)
         && *((_DWORD *)v3 + 25) )
  {
    v60 = (unsigned __int64)v4;
    v48 = 0;
    v52 = 0;
    v49 = 0;
    v47 = 0;
    v45 = 0;
    try
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v11 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v4, v9, v10);
        WPP_SF_sS(*(_QWORD *)(v12 + 16), 14, (unsigned int)&WPP_5d1638309ca23a32fb5c63fc7ed00874_Traceguids, v12, v11);
      }
      *(_OWORD *)v62 = 0;
      Microsoft::Windows::DisplayEnhancement::Foundation::ColorManagerHelper::CreateColorManager(
        &v51,
        (__int64)v4,
        (int *)v62);
      winrt::impl::consume_Windows_Internal_Graphics_Display_DisplayColorManagement_IDisplayColorManagement<winrt::Windows::Internal::Graphics::Display::DisplayColorManagement::IDisplayColorManagement>::GetDisplayBrightnessSupport(
        (unsigned int)&v51,
        (unsigned int)&v48,
        (unsigned int)&v52,
        (unsigned int)&v49,
        (__int64)&v47,
        (__int64)&v45);
      if ( v48 )
      {
        if ( v52 )
        {
          if ( v52 != 1 )
          {
            v42 = wil::verify_hresult<long>(2147549183LL);
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x12A,
              (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\displayadapter\\lib\\displayadapter.cpp",
              (const char *)v42,
              v43);
          }
          DisplayBrightnessLevel = v47;
          if ( (unsigned int)v47 > 0x186A0 )
            DisplayBrightnessLevel = 100000;
          v53 = DisplayBrightnessLevel;
          if ( v48 == 1 )
          {
            try
            {
              DisplayBrightnessLevel = winrt::impl::consume_Windows_Internal_Graphics_Display_DisplayColorManagement_IDisplayColorManagement<winrt::Windows::Internal::Graphics::Display::DisplayColorManagement::IDisplayColorManagement>::GetDisplayBrightnessLevel(&v51);
              v53 = DisplayBrightnessLevel;
            }
            catch ( ... )
            {
              wil::details::in1diag3::Log_CaughtException(
                retaddr,
                (void *)0x122,
                (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\displayadapter\\lib\\displayadapter.cpp",
                v15);
              DisplayBrightnessLevel = v53;
              v4 = (char *)v60;
              v3 = v57;
            }
          }
          v7 = 1;
        }
        else
        {
          DisplayBrightnessLevel = v47;
          if ( (unsigned int)v47 > 0x3A980 )
            DisplayBrightnessLevel = 240000;
          v7 = 2;
        }
        v46 = v7;
        _InterlockedExchange((volatile __int32 *)v3 + 26, DisplayBrightnessLevel);
        v16 = v47;
        v60 = __PAIR64__(v47, v49);
        v17 = v45;
        v61 = (std::_Ref_count_base *)v45;
        v18 = (_DWORD *)*((_QWORD *)&v55 + 1);
        if ( *((_QWORD *)&v55 + 1) == v56 )
        {
          std::vector<Microsoft::Windows::DisplayEnhancement::Foundation::MilliNitRange>::_Emplace_reallocate<Microsoft::Windows::DisplayEnhancement::Foundation::MilliNitRange const &>(
            &v55,
            *((_QWORD *)&v55 + 1),
            &v60);
        }
        else
        {
          **((_DWORD **)&v55 + 1) = v49;
          v18[1] = v16;
          v18[2] = v17;
          v18[3] = 0;
          *((_QWORD *)&v55 + 1) += 16LL;
        }
        Microsoft::Windows::DisplayEnhancement::Foundation::Utils::ConvertMilliNitsRangesToString(v62, &v55);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)v3 + 56, v19, v20);
          v23 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v4, v21, v22);
          v25 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v62, v24, v23);
          WPP_SF_sSSBrightnessControlMechanismTypeBrightnessSupportTypeSd(
            *(_QWORD *)(v26 + 16),
            v27,
            v28,
            v48,
            v7,
            v25,
            DisplayBrightnessLevel);
        }
        std::wstring::_Tidy_deallocate(v62);
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v29 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)v3 + 56, v13, WPP_GLOBAL_Control);
        v31 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v4, v29, v30);
        WPP_SF_sSS(*(_QWORD *)(v32 + 16), v31, v33);
      }
      winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Graphics::Display::DisplayColorManagement::DisplayColorManagement>::~IAsyncOperation<winrt::Windows::Internal::Graphics::Display::DisplayColorManagement::DisplayColorManagement>(&v51);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x150,
        (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\displayadapter\\lib\\displayadapter.cpp",
        v34);
      v7 = v46;
      v3 = v57;
    }
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DESFixHotkeyOSDBrightCapsChange>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DESFixHotkeyOSDBrightCapsChange>::GetImpl'::`2'::impl) )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SenBf2601>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SenBf2601>::GetImpl'::`2'::impl) )
    {
      v35 = *((_DWORD *)v3 + 25);
      if ( v35 == 1 )
      {
        if ( v50 == 1 )
        {
          v35 = 0;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_5d1638309ca23a32fb5c63fc7ed00874_Traceguids);
          }
          goto LABEL_63;
        }
      }
      else if ( !v35 )
      {
LABEL_63:
        v44[0] = 0;
        v45 = 0;
        std::make_shared<Microsoft::Windows::DisplayEnhancement::Foundation::BrightnessCapabilityWrapper,enum Microsoft::Windows::DisplayEnhancement::Foundation::BrightnessSupportType &,std::vector<Microsoft::Windows::DisplayEnhancement::Foundation::MilliNitRange> &,int,bool>(
          (unsigned int)&v57,
          (unsigned int)&v46,
          (unsigned int)&v55,
          (unsigned int)&v45,
          (__int64)v44);
        Microsoft::Windows::DisplayEnhancement::Foundation::ExclusiveSRWLockguard::ExclusiveSRWLockguard(
          (Microsoft::Windows::DisplayEnhancement::Foundation::ExclusiveSRWLockguard *)&v60,
          (Microsoft::Windows::DisplayEnhancement::MonitorContainer::MonitorAdapterImpl *)((char *)v3 + 112));
        std::shared_ptr<Microsoft::Windows::DisplayEnhancement::Foundation::BrightnessCapabilityWrapper>::operator=(
          (char *)v3 + 120,
          &v57);
        *((_DWORD *)v3 + 34) = v35;
        wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v60);
        Microsoft::Windows::DisplayEnhancement::Telemetry::DesTelemetry::GetOrMakeShared(&v60, (char *)v3 + 56);
        Microsoft::Windows::DisplayEnhancement::Telemetry::DesTelemetry::LogDisplayCapabilityEvent(v60, v35, &v57);
        if ( v61 )
          std::_Ref_count_base::_Decref(v61);
LABEL_79:
        if ( v58 )
          std::_Ref_count_base::_Decref(v58);
        goto LABEL_84;
      }
      if ( v7 == 2
        && !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ExternalBrightness>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ExternalBrightness>::GetImpl'::`2'::impl) )
      {
        v46 = 0;
        *(_OWORD *)v62 = 0;
        v63 = 0;
        std::vector<Microsoft::Windows::DisplayEnhancement::Foundation::MilliNitRange>::operator=(&v55, v62);
        std::vector<Microsoft::Windows::DisplayEnhancement::Transition::TransitionAccelerationTableEntry>::_Tidy(v62);
      }
      goto LABEL_63;
    }
    v45 = 0;
    v36 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v54 + 80LL))(v54, &v45);
    if ( v36 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x183,
        (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\displayadapter\\lib\\displayadapter.cpp",
        (const char *)(unsigned int)v36,
        v43);
    v37 = *((_DWORD *)v3 + 25);
    v38 = *((_DWORD *)v3 + 34);
    if ( v38 == 1 )
    {
      if ( v45 == 1 )
      {
        *((_DWORD *)v3 + 34) = 0;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_5d1638309ca23a32fb5c63fc7ed00874_Traceguids);
        }
        goto LABEL_77;
      }
    }
    else if ( !v38 )
    {
LABEL_77:
      v44[0] = 0;
      v49 = 0;
      std::make_shared<Microsoft::Windows::DisplayEnhancement::Foundation::BrightnessCapabilityWrapper,enum Microsoft::Windows::DisplayEnhancement::Foundation::BrightnessSupportType &,std::vector<Microsoft::Windows::DisplayEnhancement::Foundation::MilliNitRange> &,int,bool>(
        (unsigned int)&v57,
        (unsigned int)&v46,
        (unsigned int)&v55,
        (unsigned int)&v49,
        (__int64)v44);
      Microsoft::Windows::DisplayEnhancement::Foundation::ExclusiveSRWLockguard::ExclusiveSRWLockguard(
        (Microsoft::Windows::DisplayEnhancement::Foundation::ExclusiveSRWLockguard *)&v60,
        (Microsoft::Windows::DisplayEnhancement::MonitorContainer::MonitorAdapterImpl *)((char *)v3 + 112));
      std::shared_ptr<Microsoft::Windows::DisplayEnhancement::Foundation::BrightnessCapabilityWrapper>::operator=(
        (char *)v3 + 120,
        &v57);
      *((_DWORD *)v3 + 34) = v37;
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v60);
      Microsoft::Windows::DisplayEnhancement::Telemetry::DesTelemetry::GetOrMakeShared(&v60, (char *)v3 + 56);
      Microsoft::Windows::DisplayEnhancement::Telemetry::DesTelemetry::LogDisplayCapabilityEvent(v60, v37, &v57);
      if ( v61 )
        std::_Ref_count_base::_Decref(v61);
      goto LABEL_79;
    }
    if ( (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)v3 + 15) + 8LL))(*((_QWORD *)v3 + 15)) == 2
      && !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ExternalBrightness>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ExternalBrightness>::GetImpl'::`2'::impl) )
    {
      v46 = 0;
      *(_OWORD *)v62 = 0;
      v63 = 0;
      std::vector<Microsoft::Windows::DisplayEnhancement::Foundation::MilliNitRange>::operator=(&v55, v62);
      std::vector<Microsoft::Windows::DisplayEnhancement::Transition::TransitionAccelerationTableEntry>::_Tidy(v62);
    }
    goto LABEL_77;
  }
  Microsoft::Windows::DisplayEnhancement::Foundation::ExclusiveSRWLockguard::ExclusiveSRWLockguard(
    (Microsoft::Windows::DisplayEnhancement::Foundation::ExclusiveSRWLockguard *)&v60,
    (Microsoft::Windows::DisplayEnhancement::MonitorContainer::MonitorAdapterImpl *)((char *)v3 + 112));
  v44[0] = 0;
  v45 = 0;
  v39 = (__int64 *)std::make_shared<Microsoft::Windows::DisplayEnhancement::Foundation::BrightnessCapabilityWrapper,enum Microsoft::Windows::DisplayEnhancement::Foundation::BrightnessSupportType &,std::vector<Microsoft::Windows::DisplayEnhancement::Foundation::MilliNitRange> &,int,bool>(
                     (unsigned int)v62,
                     (unsigned int)&v46,
                     (unsigned int)&v55,
                     (unsigned int)&v45,
                     (__int64)v44);
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
    (_QWORD *)v3 + 15,
    v39);
  if ( v62[1] )
    std::_Ref_count_base::_Decref(v62[1]);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v60);
LABEL_84:
  std::vector<Microsoft::Windows::DisplayEnhancement::Transition::TransitionAccelerationTableEntry>::_Tidy(&v55);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v54);
  v40 = v59;
  if ( v59 )
  {
    v59 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64)))(*v40)[2])(v40);
  }
}

```

## disassembly

```asm
0x18009df78  mov     r11, rsp
0x18009df7b  push    rbx
0x18009df7c  push    rsi
0x18009df7d  push    rdi
0x18009df7e  push    r12
0x18009df80  push    r14
0x18009df82  push    r15
0x18009df84  sub     rsp, 0F8h
0x18009df8b  mov     rax, cs:__security_cookie
0x18009df92  xor     rax, rsp
0x18009df95  mov     [rsp+128h+var_40], rax
0x18009df9d  mov     rsi, rcx
0x18009dfa0  mov     [rsp+128h+var_88], rcx
0x18009dfa8  lea     r12, [rcx+8]
0x18009dfac  mov     rdx, r12
0x18009dfaf  lea     rcx, [r11-78h]
0x18009dfb3  call    ?GetDisplayMonitorFromDeviceId@MonitorAdapterImpl@MonitorContainer@DisplayEnhancement@Windows@Microsoft@@SA?AV?$ComPtr@UIDisplayMonitor@Display@Devices@Windows@@@WRL@5@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::DisplayEnhancement::MonitorContainer::MonitorAdapterImpl::GetDisplayMonitorFromDeviceId(std::wstring const &)
0x18009dfb8  nop
0x18009dfb9  xor     ebx, ebx
0x18009dfbb  mov     [rsp+128h+var_A8], rbx
0x18009dfc3  lea     rdx, [rsp+128h+var_A8]
0x18009dfcb  lea     rcx, [rsp+128h+var_78]
0x18009dfd3  call    ??$As@UIDisplayMonitorInternal@Internal@Display@Devices@Windows@@@?$ComPtr@UIDisplayMonitor@Display@Devices@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIDisplayMonitorInternal@Internal@Display@Devices@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Devices::Display::IDisplayMonitor>::As<Windows::Devices::Display::Internal::IDisplayMonitorInternal>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Devices::Display::Internal::IDisplayMonitorInternal>>)
0x18009dfd8  mov     rcx, [rsp+128h]; this
0x18009dfe0  test    eax, eax
0x18009dfe2  js      loc_18009E7ED
0x18009dfe8  mov     [rsp+128h+var_C0], ebx
0x18009dfec  mov     rcx, [rsp+128h+var_A8]
0x18009dff4  mov     rax, [rcx]
0x18009dff7  lea     rdx, [rsp+128h+var_C0]
0x18009dffc  mov     rax, [rax+50h]
0x18009e000  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e005  mov     rcx, [rsp+128h]; this
0x18009e00d  test    eax, eax
0x18009e00f  js      loc_18009E802
0x18009e015  mov     ecx, [rsp+128h+var_C0]
0x18009e019  test    ecx, ecx
0x18009e01b  jz      short loc_18009E03E
0x18009e01d  sub     ecx, 1
0x18009e020  jz      short loc_18009E037
0x18009e022  sub     ecx, 1
0x18009e025  jz      short loc_18009E030
0x18009e027  cmp     ecx, 1
0x18009e02a  jnz     loc_18009E817
0x18009e030  mov     edi, 2
0x18009e035  jmp     short loc_18009E040
0x18009e037  mov     edi, 1
0x18009e03c  jmp     short loc_18009E040
0x18009e03e  mov     edi, ebx
0x18009e040  mov     [rsp+128h+var_D0], edi
0x18009e044  xorps   xmm0, xmm0
0x18009e047  movdqu  [rsp+128h+var_A0], xmm0
0x18009e050  mov     [rsp+128h+var_90], rbx
0x18009e058  cmp     edi, 2
0x18009e05b  jnz     loc_18009E11B
0x18009e061  mov     rcx, [rsp+128h+var_A8]
0x18009e069  mov     [rsp+128h+var_B8], rcx
0x18009e06e  test    rcx, rcx
0x18009e071  jz      short loc_18009E080
0x18009e073  mov     rax, [rcx]
0x18009e076  mov     rax, [rax+8]
0x18009e07a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e07f  nop
0x18009e080  lea     rdx, [rsp+128h+var_B8]
0x18009e085  lea     rcx, [rsp+128h+var_60]
0x18009e08d  call    ?GetNitRangesFromDisplayMonitorInternal@MonitorAdapterImpl@MonitorContainer@DisplayEnhancement@Windows@Microsoft@@CA?AV?$vector@UMilliNitRange@Foundation@DisplayEnhancement@Windows@Microsoft@@V?$allocator@UMilliNitRange@Foundation@DisplayEnhancement@Windows@Microsoft@@@std@@@std@@V?$ComPtr@UIDisplayMonitorInternal@Internal@Display@Devices@Windows@@@WRL@5@@Z; Microsoft::Windows::DisplayEnhancement::MonitorContainer::MonitorAdapterImpl::GetNitRangesFromDisplayMonitorInternal(Microsoft::WRL::ComPtr<Windows::Devices::Display::Internal::IDisplayMonitorInternal>)
0x18009e092  mov     rdx, rax
0x18009e095  lea     rcx, [rsp+128h+var_A0]
0x18009e09d  call    ??4?$vector@UMilliNitRange@Foundation@DisplayEnhancement@Windows@Microsoft@@V?$allocator@UMilliNitRange@Foundation@DisplayEnhancement@Windows@Microsoft@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<Microsoft::Windows::DisplayEnhancement::Foundation::MilliNitRange>::operator=(std::vector<Microsoft::Windows::DisplayEnhancement::Foundation::MilliNitRange> &&)
0x18009e0a2  lea     rcx, [rsp+128h+var_60]
0x18009e0aa  call    ?_Tidy@?$vector@UTransitionAccelerationTableEntry@Transition@DisplayEnhancement@Windows@Microsoft@@V?$allocator@UTransitionAccelerationTableEntry@Transition@DisplayEnhancement@Windows@Microsoft@@@std@@@std@@AEAAXXZ; std::vector<Microsoft::Windows::DisplayEnhancement::Transition::TransitionAccelerationTableEntry>::_Tidy(void)
0x18009e0af  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SenBfCd2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SenBfCd2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SenBfCd2> `wil::Feature<__WilFeatureTraits_Feature_SenBfCd2>::GetImpl(void)'::`2'::impl
0x18009e0b6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SenBfCd2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SenBfCd2>::__private_IsEnabled(void)
0x18009e0bb  test    al, al
0x18009e0bd  jz      loc_18009E414
0x18009e0c3  mov     rax, qword ptr [rsp+128h+var_A0+8]
0x18009e0cb  cmp     qword ptr [rsp+128h+var_A0], rax
0x18009e0d3  jnz     loc_18009E414
0x18009e0d9  lea     r14, WPP_GLOBAL_Control
0x18009e0e0  mov     rcx, cs:WPP_GLOBAL_Control
0x18009e0e7  cmp     rcx, r14
0x18009e0ea  jz      short loc_18009E110
0x18009e0ec  test    dword ptr [rcx+1Ch], 100h
0x18009e0f3  jz      short loc_18009E110
0x18009e0f5  cmp     byte ptr [rcx+19h], 3
0x18009e0f9  jb      short loc_18009E110
0x18009e0fb  mov     edx, 0Dh
0x18009e100  lea     r8, WPP_5d1638309ca23a32fb5c63fc7ed00874_Traceguids
0x18009e107  mov     rcx, [rcx+10h]
0x18009e10b  call    WPP_SF_s
0x18009e110  mov     edi, ebx
0x18009e112  mov     [rsp+128h+var_D0], ebx
0x18009e116  jmp     loc_18009E41B
0x18009e11b  cmp     edi, 1
0x18009e11e  jnz     short loc_18009E15B
0x18009e120  mov     eax, 186A0h
0x18009e125  mov     dword ptr [rsp+128h+var_70+4], eax
0x18009e12c  mov     dword ptr [rsp+128h+var_70], ebx
0x18009e133  mov     [rsp+128h+var_68], 1
0x18009e13f  lea     r8, [rsp+128h+var_70]
0x18009e147  xor     edx, edx
0x18009e149  lea     rcx, [rsp+128h+var_A0]
0x18009e151  call    ??$_Emplace_reallocate@AEBUMilliNitRange@Foundation@DisplayEnhancement@Windows@Microsoft@@@?$vector@UMilliNitRange@Foundation@DisplayEnhancement@Windows@Microsoft@@V?$allocator@UMilliNitRange@Foundation@DisplayEnhancement@Windows@Microsoft@@@std@@@std@@AEAAPEAUMilliNitRange@Foundation@DisplayEnhancement@Windows@Microsoft@@QEAU23456@AEBU23456@@Z; std::vector<Microsoft::Windows::DisplayEnhancement::Foundation::MilliNitRange>::_Emplace_reallocate<Microsoft::Windows::DisplayEnhancement::Foundation::MilliNitRange const &>(Microsoft::Windows::DisplayEnhancement::Foundation::MilliNitRange * const,Microsoft::Windows::DisplayEnhancement::Foundation::MilliNitRange const &)
0x18009e156  jmp     loc_18009E414
0x18009e15b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ExternalBrightness@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ExternalBrightness@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ExternalBrightness> `wil::Feature<__WilFeatureTraits_Feature_ExternalBrightness>::GetImpl(void)'::`2'::impl
0x18009e162  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ExternalBrightness@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ExternalBrightness>::__private_IsEnabled(void)
0x18009e167  test    al, al
0x18009e169  jz      loc_18009E414
0x18009e16f  test    edi, edi
0x18009e171  jnz     loc_18009E414
0x18009e177  cmp     [rsi+64h], ebx
0x18009e17a  jz      loc_18009E414
0x18009e180  mov     [rsp+128h+var_70], r12
0x18009e188  mov     [rsp+128h+var_C8], ebx
0x18009e18c  mov     [rsp+128h+var_B0], ebx
0x18009e190  mov     [rsp+128h+var_C4], ebx
0x18009e194  mov     [rsp+128h+var_CC], ebx
0x18009e198  mov     [rsp+128h+var_D4], ebx
0x18009e19c  lea     r14, WPP_GLOBAL_Control
0x18009e1a3  mov     r9, cs:WPP_GLOBAL_Control
0x18009e1aa  cmp     r9, r14
0x18009e1ad  jz      short loc_18009E1E0
0x18009e1af  test    dword ptr [r9+1Ch], 100h
0x18009e1b7  jz      short loc_18009E1E0
0x18009e1b9  cmp     byte ptr [r9+19h], 4
0x18009e1be  jb      short loc_18009E1E0
0x18009e1c0  mov     rcx, r12
0x18009e1c3  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18009e1c8  lea     edx, [rdi+0Eh]
0x18009e1cb  mov     [rsp+128h+var_108], rax
0x18009e1d0  lea     r8, WPP_5d1638309ca23a32fb5c63fc7ed00874_Traceguids
0x18009e1d7  mov     rcx, [r9+10h]
0x18009e1db  call    WPP_SF_sS
0x18009e1e0  xorps   xmm0, xmm0
0x18009e1e3  movups  xmmword ptr [rsp+128h+var_60], xmm0
0x18009e1eb  lea     r8, [rsp+128h+var_60]
0x18009e1f3  mov     rdx, r12
0x18009e1f6  lea     rcx, [rsp+128h+var_B8]
0x18009e1fb  call    ?CreateColorManager@ColorManagerHelper@Foundation@DisplayEnhancement@Windows@Microsoft@@SA?AUDisplayColorManagement@6Display@Graphics@Internal@4winrt@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@@Z; Microsoft::Windows::DisplayEnhancement::Foundation::ColorManagerHelper::CreateColorManager(std::wstring const &,_GUID const &)
0x18009e200  nop
0x18009e201  lea     rax, [rsp+128h+var_D4]
0x18009e206  mov     [rsp+128h+var_100], rax
0x18009e20b  lea     rax, [rsp+128h+var_CC]
0x18009e210  mov     [rsp+128h+var_108], rax; int
0x18009e215  lea     r9, [rsp+128h+var_C4]
0x18009e21a  lea     r8, [rsp+128h+var_B0]
0x18009e21f  lea     rdx, [rsp+128h+var_C8]
0x18009e224  lea     rcx, [rsp+128h+var_B8]
0x18009e229  call    ?GetDisplayBrightnessSupport@?$consume_Windows_Internal_Graphics_Display_DisplayColorManagement_IDisplayColorManagement@UIDisplayColorManagement@DisplayColorManagement@Display@Graphics@Internal@Windows@winrt@@@impl@winrt@@QEBA@AEAW4BrightnessControlMechanismType@DisplayColorManagement@Display@Graphics@Internal@Windows@3@AEAW4BrightnessControlUnitType@567893@AEAI22@Z; winrt::impl::consume_Windows_Internal_Graphics_Display_DisplayColorManagement_IDisplayColorManagement<winrt::Windows::Internal::Graphics::Display::DisplayColorManagement::IDisplayColorManagement>::GetDisplayBrightnessSupport(winrt::Windows::Internal::Graphics::Display::DisplayColorManagement::BrightnessControlMechanismType &,winrt::Windows::Internal::Graphics::Display::DisplayColorManagement::BrightnessControlUnitType &,uint &,uint &,uint &)
0x18009e22e  cmp     [rsp+128h+var_C8], ebx
0x18009e232  jz      loc_18009E3B4
0x18009e238  mov     ecx, [rsp+128h+var_B0]
0x18009e23c  test    ecx, ecx
0x18009e23e  jz      short loc_18009E29E
0x18009e240  cmp     ecx, 1
0x18009e243  jnz     loc_18009E83E
0x18009e249  mov     r15d, [rsp+128h+var_CC]
0x18009e24e  mov     eax, 186A0h
0x18009e253  cmp     r15d, eax
0x18009e256  cmova   r15d, eax
0x18009e25a  mov     [rsp+128h+var_AC], r15d
0x18009e25f  cmp     [rsp+128h+var_C8], 1
0x18009e264  jnz     short loc_18009E297
0x18009e266  lea     rcx, [rsp+128h+var_B8]
0x18009e26b  call    ?GetDisplayBrightnessLevel@?$consume_Windows_Internal_Graphics_Display_DisplayColorManagement_IDisplayColorManagement@UIDisplayColorManagement@DisplayColorManagement@Display@Graphics@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Graphics_Display_DisplayColorManagement_IDisplayColorManagement<winrt::Windows::Internal::Graphics::Display::DisplayColorManagement::IDisplayColorManagement>::GetDisplayBrightnessLevel(void)
0x18009e270  mov     r15d, eax
0x18009e273  mov     [rsp+128h+var_AC], eax
0x18009e277  jmp     short loc_18009E297
0x18009e279  xor     ebx, ebx
0x18009e27b  lea     r14, WPP_GLOBAL_Control
0x18009e282  mov     r15d, [rsp+128h+var_AC]
0x18009e287  mov     r12, [rsp+128h+var_70]
0x18009e28f  mov     rsi, [rsp+128h+var_88]
0x18009e297  mov     edi, 1
0x18009e29c  jmp     short loc_18009E2B4
0x18009e29e  mov     r15d, [rsp+128h+var_CC]
0x18009e2a3  mov     eax, 3A980h
0x18009e2a8  cmp     r15d, eax
0x18009e2ab  cmova   r15d, eax
0x18009e2af  mov     edi, 2
0x18009e2b4  mov     [rsp+128h+var_D0], edi
0x18009e2b8  mov     eax, r15d
0x18009e2bb  xchg    eax, [rsi+68h]
0x18009e2be  mov     ecx, [rsp+128h+var_CC]
0x18009e2c2  mov     dword ptr [rsp+128h+var_70+4], ecx
0x18009e2c9  mov     eax, [rsp+128h+var_C4]
0x18009e2cd  mov     dword ptr [rsp+128h+var_70], eax
0x18009e2d4  mov     r8d, [rsp+128h+var_D4]
0x18009e2d9  mov     dword ptr [rsp+128h+var_68], r8d
0x18009e2e1  mov     dword ptr [rsp+128h+var_68+4], ebx
0x18009e2e8  mov     rdx, qword ptr [rsp+128h+var_A0+8]
0x18009e2f0  cmp     rdx, [rsp+128h+var_90]
0x18009e2f8  jz      short loc_18009E311
0x18009e2fa  mov     [rdx], eax
0x18009e2fc  mov     [rdx+4], ecx
0x18009e2ff  mov     [rdx+8], r8d
0x18009e303  mov     [rdx+0Ch], ebx
0x18009e306  add     qword ptr [rsp+128h+var_A0+8], 10h
0x18009e30f  jmp     short loc_18009E326
0x18009e311  lea     r8, [rsp+128h+var_70]
0x18009e319  lea     rcx, [rsp+128h+var_A0]
0x18009e321  call    ??$_Emplace_reallocate@AEBUMilliNitRange@Foundation@DisplayEnhancement@Windows@Microsoft@@@?$vector@UMilliNitRange@Foundation@DisplayEnhancement@Windows@Microsoft@@V?$allocator@UMilliNitRange@Foundation@DisplayEnhancement@Windows@Microsoft@@@std@@@std@@AEAAPEAUMilliNitRange@Foundation@DisplayEnhancement@Windows@Microsoft@@QEAU23456@AEBU23456@@Z; std::vector<Microsoft::Windows::DisplayEnhancement::Foundation::MilliNitRange>::_Emplace_reallocate<Microsoft::Windows::DisplayEnhancement::Foundation::MilliNitRange const &>(Microsoft::Windows::DisplayEnhancement::Foundation::MilliNitRange * const,Microsoft::Windows::DisplayEnhancement::Foundation::MilliNitRange const &)
0x18009e326  lea     rdx, [rsp+128h+var_A0]
0x18009e32e  lea     rcx, [rsp+128h+var_60]
0x18009e336  call    ?ConvertMilliNitsRangesToString@Utils@Foundation@DisplayEnhancement@Windows@Microsoft@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$vector@UMilliNitRange@Foundation@DisplayEnhancement@Windows@Microsoft@@V?$allocator@UMilliNitRange@Foundation@DisplayEnhancement@Windows@Microsoft@@@std@@@7@@Z; Microsoft::Windows::DisplayEnhancement::Foundation::Utils::ConvertMilliNitsRangesToString(std::vector<Microsoft::Windows::DisplayEnhancement::Foundation::MilliNitRange> const &)
0x18009e33b  mov     r10, cs:WPP_GLOBAL_Control
0x18009e342  cmp     r10, r14
0x18009e345  jz      short loc_18009E3A5
0x18009e347  test    dword ptr [r10+1Ch], 100h
0x18009e34f  jz      short loc_18009E3A5
0x18009e351  cmp     byte ptr [r10+19h], 4
0x18009e356  jb      short loc_18009E3A5
0x18009e358  lea     rcx, [rsi+38h]
0x18009e35c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18009e361  mov     r9, rax
0x18009e364  mov     rcx, r12
0x18009e367  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18009e36c  mov     r8, rax
0x18009e36f  lea     rcx, [rsp+128h+var_60]
0x18009e377  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18009e37c  mov     dword ptr [rsp+128h+var_E0], r15d; char
0x18009e381  mov     [rsp+128h+var_E8], rax; __int64
0x18009e386  mov     [rsp+128h+var_F0], edi; int
0x18009e38a  mov     edx, [rsp+128h+var_C8]
0x18009e38e  mov     [rsp+128h+var_F8], edx; int
0x18009e392  mov     [rsp+128h+var_100], r9; __int64
0x18009e397  mov     [rsp+128h+var_108], r8; __int64
0x18009e39c  mov     rcx, [r10+10h]; LoggerHandle
0x18009e3a0  call    WPP_SF_sSSBrightnessControlMechanismTypeBrightnessSupportTypeSd
0x18009e3a5  lea     rcx, [rsp+128h+var_60]
0x18009e3ad  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009e3b2  jmp     short loc_18009E3F9
0x18009e3b4  mov     r8, cs:WPP_GLOBAL_Control
0x18009e3bb  cmp     r8, r14
0x18009e3be  jz      short loc_18009E3F9
0x18009e3c0  test    dword ptr [r8+1Ch], 100h
0x18009e3c8  jz      short loc_18009E3F9
0x18009e3ca  cmp     byte ptr [r8+19h], 4
0x18009e3cf  jb      short loc_18009E3F9
0x18009e3d1  lea     rcx, [rsi+38h]
0x18009e3d5  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18009e3da  mov     rdx, rax
0x18009e3dd  mov     rcx, r12
0x18009e3e0  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18009e3e5  mov     [rsp+128h+var_100], rdx; __int64
0x18009e3ea  mov     [rsp+128h+var_108], rax; __int64
0x18009e3ef  mov     rcx, [r8+10h]; LoggerHandle
0x18009e3f3  call    WPP_SF_sSS
0x18009e3f8  nop
0x18009e3f9  lea     rcx, [rsp+128h+var_B8]
0x18009e3fe  call    ??1?$IAsyncOperation@UDisplayColorManagement@1Display@Graphics@Internal@Windows@winrt@@@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Graphics::Display::DisplayColorManagement::DisplayColorManagement>::~IAsyncOperation<winrt::Windows::Internal::Graphics::Display::DisplayColorManagement::DisplayColorManagement>(void)
0x18009e403  nop
0x18009e404  jmp     short loc_18009E41B
0x18009e406  xor     ebx, ebx
0x18009e408  mov     edi, [rsp+128h+var_D0]
0x18009e40c  mov     rsi, [rsp+128h+var_88]
0x18009e414  lea     r14, WPP_GLOBAL_Control
0x18009e41b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DESFixHotkeyOSDBrightCapsChange@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DESFixHotkeyOSDBrightCapsChange@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DESFixHotkeyOSDBrightCapsChange> `wil::Feature<__WilFeatureTraits_Feature_DESFixHotkeyOSDBrightCapsChange>::GetImpl(void)'::`2'::impl
0x18009e422  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DESFixHotkeyOSDBrightCapsChange@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DESFixHotkeyOSDBrightCapsChange>::__private_IsEnabled(void)
0x18009e427  test    al, al
0x18009e429  jz      loc_18009E71E
0x18009e42f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SenBf2601@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SenBf2601@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SenBf2601> `wil::Feature<__WilFeatureTraits_Feature_SenBf2601>::GetImpl(void)'::`2'::impl
0x18009e436  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SenBf2601@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SenBf2601>::__private_IsEnabled(void)
0x18009e43b  test    al, al
0x18009e43d  jz      loc_18009E588
0x18009e443  mov     r15d, [rsi+64h]
0x18009e447  cmp     r15d, 1
0x18009e44b  jnz     short loc_18009E489
0x18009e44d  cmp     [rsp+128h+var_C0], r15d
0x18009e452  jnz     short loc_18009E48E
0x18009e454  mov     r15d, ebx
0x18009e457  mov     rcx, cs:WPP_GLOBAL_Control
0x18009e45e  cmp     rcx, r14
0x18009e461  jz      short loc_18009E4DD
0x18009e463  test    dword ptr [rcx+1Ch], 100h
0x18009e46a  jz      short loc_18009E4DD
0x18009e46c  cmp     byte ptr [rcx+19h], 2
0x18009e470  jb      short loc_18009E4DD
0x18009e472  mov     edx, 11h
0x18009e477  lea     r8, WPP_5d1638309ca23a32fb5c63fc7ed00874_Traceguids
0x18009e47e  mov     rcx, [rcx+10h]
0x18009e482  call    WPP_SF_s
0x18009e487  jmp     short loc_18009E4DD
0x18009e489  test    r15d, r15d
0x18009e48c  jz      short loc_18009E4DD
0x18009e48e  cmp     edi, 2
0x18009e491  jnz     short loc_18009E4DD
0x18009e493  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ExternalBrightness@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ExternalBrightness@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ExternalBrightness> `wil::Feature<__WilFeatureTraits_Feature_ExternalBrightness>::GetImpl(void)'::`2'::impl
0x18009e49a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ExternalBrightness@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ExternalBrightness>::__private_IsEnabled(void)
0x18009e49f  test    al, al
0x18009e4a1  jnz     short loc_18009E4DD
0x18009e4a3  mov     [rsp+128h+var_D0], ebx
0x18009e4a7  xorps   xmm0, xmm0
0x18009e4aa  movdqu  xmmword ptr [rsp+128h+var_60], xmm0
0x18009e4b3  mov     [rsp+128h+var_50], rbx
0x18009e4bb  lea     rdx, [rsp+128h+var_60]
0x18009e4c3  lea     rcx, [rsp+128h+var_A0]
0x18009e4cb  call    ??4?$vector@UMilliNitRange@Foundation@DisplayEnhancement@Windows@Microsoft@@V?$allocator@UMilliNitRange@Foundation@DisplayEnhancement@Windows@Microsoft@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<Microsoft::Windows::DisplayEnhancement::Foundation::MilliNitRange>::operator=(std::vector<Microsoft::Windows::DisplayEnhancement::Foundation::MilliNitRange> &&)
0x18009e4d0  lea     rcx, [rsp+128h+var_60]
0x18009e4d8  call    ?_Tidy@?$vector@UTransitionAccelerationTableEntry@Transition@DisplayEnhancement@Windows@Microsoft@@V?$allocator@UTransitionAccelerationTableEntry@Transition@DisplayEnhancement@Windows@Microsoft@@@std@@@std@@AEAAXXZ; std::vector<Microsoft::Windows::DisplayEnhancement::Transition::TransitionAccelerationTableEntry>::_Tidy(void)
  ... truncated ...
```
