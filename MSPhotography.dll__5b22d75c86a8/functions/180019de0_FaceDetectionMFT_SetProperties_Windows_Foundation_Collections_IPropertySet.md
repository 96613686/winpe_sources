# FaceDetectionMFT::SetProperties(Windows::Foundation::Collections::IPropertySet *)

- ea: `0x180019de0`
- end: `0x18001a91c`
- name: `?SetProperties@FaceDetectionMFT@@UEAAJPEAUIPropertySet@Collections@Foundation@Windows@@@Z`
- size: `2876`
- prototype: `__int64 __fastcall(FaceDetectionMFT *__hidden this, struct Windows::Foundation::Collections::IPropertySet *)`
- caller_count: `0`
- callee_count: `24`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002420`
- `0x1800028cc`
- `0x180003088`
- `0x1800035ac`
- `0x180005660`
- `0x180009784`
- `0x18000ad70`
- `0x18000ae08`
- `0x18000af44`
- `0x18000c0f8`
- `0x18000c18c`
- `0x18000c1d8`
- `0x18000c4b4`
- `0x18000c838`
- `0x18000f2f4`
- `0x180014ea0`
- `0x1800153b0`
- `0x1800154fc`
- `0x180019de0`
- `0x18001c51c`
- `0x18001c95c`
- `0x18001d3b0`
- `0x18001d658`
- `0x180142010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001a8c3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001a8c3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a3bb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a427`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a3bb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a427`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a3ca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a593`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a5a8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a3ca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a593`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a5a8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180019e71`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180019ea1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180019ed1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180019e71`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180019ea1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180019ed1`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001a3f3`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001a3f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180019e51`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180019e8b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180019ebb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180019e51`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180019e8b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180019ebb`

## pseudocode

```c
__int64 __fastcall FaceDetectionMFT::SetProperties(
        FaceDetectionMFT *this,
        struct Windows::Foundation::Collections::IPropertySet *a2)
{
  unsigned int v3; // r14d
  const unsigned __int16 (*v5)[14]; // rdx
  const unsigned __int16 (*v6)[27]; // rdx
  char v7; // r12
  char v8; // r13
  char v9; // r15
  __int64 (__fastcall *v10)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, __int64 *); // rbx
  int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // rdi
  int (__fastcall *v14)(__int64, HSTRING, __int64 *); // rbx
  __int64 v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rax
  __int64 v18; // rdi
  int (__fastcall *v19)(__int64, HSTRING, __int64 *); // rbx
  char IsEnabled; // al
  bool *v21; // rdx
  __int64 v22; // rdi
  int (__fastcall *v23)(__int64, HSTRING, __int64 *); // rbx
  __int64 v24; // rdi
  int (__fastcall *v25)(__int64, HSTRING, __int64 *); // rbx
  void **v26; // rbx
  unsigned int v27; // r15d
  void *v28; // rax
  const struct std::nothrow_t *v29; // rdx
  void *v30; // rdi
  void *v31; // rcx
  const struct winrt::impl::slim_source_location *v32; // rdx
  __int64 v33; // rdi
  int (__fastcall *v34)(__int64, HSTRING, __int64 *); // rbx
  char v35; // bl
  unsigned __int64 v36; // rdx
  const unsigned __int16 *v37; // rdx
  const unsigned __int16 *v38; // rdx
  char v39; // bl
  int v40; // eax
  _QWORD *v41; // rax
  int v42; // eax
  char v43; // al
  _QWORD *v44; // rax
  int v45; // eax
  __int64 v46; // rdi
  __int64 (__fastcall *v47)(__int64, HSTRING *); // rbx
  int v48; // eax
  __int64 v49; // rdx
  __int64 v50; // rdi
  __int64 (__fastcall *v51)(__int64, __int64 *); // rbx
  __int64 v52; // rdi
  __int64 (__fastcall *v53)(__int64, __int64 *); // rbx
  char v55; // [rsp+30h] [rbp-D0h] BYREF
  char v56; // [rsp+31h] [rbp-CFh]
  __int64 v57; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v58; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v59; // [rsp+48h] [rbp-B8h] BYREF
  PSRWLOCK SRWLock; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v61; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v62; // [rsp+60h] [rbp-A0h] BYREF
  HSTRING v63[4]; // [rsp+68h] [rbp-98h] BYREF
  HSTRING v64; // [rsp+88h] [rbp-78h] BYREF
  HSTRING_HEADER v65; // [rsp+90h] [rbp-70h] BYREF
  HSTRING string; // [rsp+A8h] [rbp-58h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+B0h] [rbp-50h] BYREF
  HSTRING v68; // [rsp+C8h] [rbp-38h] BYREF
  HSTRING_HEADER v69; // [rsp+D0h] [rbp-30h] BYREF
  HSTRING v70; // [rsp+E8h] [rbp-18h] BYREF
  HSTRING v71; // [rsp+108h] [rbp+8h] BYREF
  HSTRING v72; // [rsp+128h] [rbp+28h] BYREF

  v57 = 0;
  v3 = 0;
  v62 = 0;
  v59 = 0;
  Windows::Internal::StringReference::StringReference(&v71, (const unsigned __int16 (*)[21])a2);
  Windows::Internal::StringReference::StringReference(&v72, v5);
  Windows::Internal::StringReference::StringReference(&v70, v6);
  if ( WindowsCreateStringReference(L"UseWinMLFaceDetection", 0x15u, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  if ( WindowsCreateStringReference(L"NoArtificialBrightening", 0x17u, &v65, &v64) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  if ( WindowsCreateStringReference(L"AdaptiveFDRate", 0xEu, &v69, &v68) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v56 = 0;
  v7 = 0;
  v8 = 0;
  v9 = 0;
  if ( !a2 )
    goto LABEL_71;
  v10 = **(__int64 (__fastcall ***)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, __int64 *))a2;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v62);
  v11 = v10(a2, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, &v62);
  v3 = v11;
  if ( v11 >= 0 )
  {
    v13 = v62;
    v14 = *(int (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v62 + 48LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v57);
    if ( v14(v13, v70, &v57) >= 0 )
    {
      v11 = Microsoft::WRL::ComPtr<IInspectable>::As<Windows::Foundation::IPropertyValue>(&v57, &v59);
      v3 = v11;
      if ( v11 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_145;
        v12 = 42;
        goto LABEL_11;
      }
      v11 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v59 + 160LL))(v59, (char *)this + 17464);
      v3 = v11;
      if ( v11 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_145;
        v12 = 43;
        goto LABEL_11;
      }
      v15 = *((_QWORD *)this + 2181);
      if ( v15 )
      {
        v16 = *(_QWORD *)(v15 + 8);
        if ( v16 )
        {
          v17 = *(_QWORD *)(v16 + 8);
          if ( v17 )
            *(_OWORD *)(v17 + 120) = *(_OWORD *)((char *)this + 17464);
        }
      }
    }
    v18 = v62;
    v19 = *(int (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v62 + 48LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v57);
    if ( v19(v18, v71, &v57) >= 0 )
    {
      v55 = 0;
      v11 = Microsoft::WRL::ComPtr<IInspectable>::As<Windows::Foundation::IPropertyValue>(&v57, &v59);
      v3 = v11;
      if ( v11 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_145;
        v12 = 44;
        goto LABEL_11;
      }
      v11 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v59 + 144LL))(v59, &v55);
      v3 = v11;
      if ( v11 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_145;
        v12 = 45;
        goto LABEL_11;
      }
      IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_CameraQI2511>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CameraQI2511>::GetImpl'::`2'::impl);
      v21 = (bool *)this + 852;
      if ( IsEnabled && *v21 != (v55 != 0) )
        v56 = 1;
      *v21 = v55 != 0;
    }
    v22 = v62;
    v23 = *(int (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v62 + 48LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v57);
    if ( v23(v22, v72, &v57) >= 0 )
    {
      LODWORD(v58) = 0;
      v11 = Microsoft::WRL::ComPtr<IInspectable>::As<Windows::Foundation::IPropertyValue>(&v57, &v59);
      v3 = v11;
      if ( v11 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_145;
        v12 = 46;
        goto LABEL_11;
      }
      v11 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v59 + 96LL))(v59, &v58);
      v3 = v11;
      if ( v11 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_145;
        v12 = 47;
        goto LABEL_11;
      }
      if ( (unsigned int)v58 >= 3 )
      {
        v3 = -2147024809;
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            48,
            &WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids,
            this,
            -2147024809);
        goto LABEL_145;
      }
      *((_DWORD *)this + 212) = v58;
    }
    v24 = v62;
    v25 = *(int (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v62 + 48LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v57);
    if ( v25(v24, v64, &v57) >= 0 )
    {
      v55 = 0;
      v11 = Microsoft::WRL::ComPtr<IInspectable>::As<Windows::Foundation::IPropertyValue>(&v57, &v59);
      v3 = v11;
      if ( v11 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_145;
        v12 = 49;
        goto LABEL_11;
      }
      v11 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v59 + 144LL))(v59, &v55);
      v3 = v11;
      if ( v11 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_145;
        v12 = 50;
        goto LABEL_11;
      }
      v26 = (void **)((char *)this + 17416);
      v8 = 1;
      *((_BYTE *)this + 961) = v55 != 0;
      wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset((char *)this + 17416);
      if ( *((_BYTE *)this + 961) || !*((_BYTE *)this + 960) )
      {
        *((_BYTE *)this + 1024) = 0;
      }
      else
      {
        v27 = *((_DWORD *)this + 144) * *((_DWORD *)this + 144);
        v28 = operator new[](v27, (const struct std::nothrow_t *)&std::nothrow);
        v30 = v28;
        if ( v28 )
          memset_0(v28, 0, v27);
        else
          v30 = 0;
        v31 = *v26;
        SRWLock = 0;
        *v26 = v30;
        if ( v31 )
          operator delete(v31, v29);
        wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset(&SRWLock);
        LODWORD(v63[0]) = 0;
        *(_OWORD *)&v63[1] = 0;
        if ( !*v26 )
          winrt::throw_last_error((winrt *)v63, v32);
      }
    }
    v33 = v62;
    v34 = *(int (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v62 + 48LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v57);
    if ( v34(v33, string, &v57) >= 0 )
    {
      v55 = 0;
      v11 = Microsoft::WRL::ComPtr<IInspectable>::As<Windows::Foundation::IPropertyValue>(&v57, &v59);
      v3 = v11;
      if ( v11 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_145;
        v12 = 51;
        goto LABEL_11;
      }
      v11 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v59 + 144LL))(v59, &v55);
      v3 = v11;
      if ( v11 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_145;
        v12 = 52;
        goto LABEL_11;
      }
      v7 = 1;
      *((_BYTE *)this + 960) = v55 != 0;
    }
    v9 = v56;
LABEL_71:
    Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, (char *)this + 136);
    while ( 1 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 424));
      v35 = *((_BYTE *)this + 624);
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 424));
      if ( !v35 )
        break;
      v36 = (__int64)((unsigned __int128)(*((__int64 *)this + 69) * (__int128)0x346DC5D63886594BLL) >> 64) >> 11;
      Sleep(v36 + (v36 >> 63));
    }
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CameraQI2511>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CameraQI2511>::GetImpl'::`2'::impl) )
    {
      if ( v7 )
      {
        v43 = *((_BYTE *)this + 960);
        if ( *((_BYTE *)this + 545) != v43 )
        {
          if ( v43 )
          {
            if ( (int)FaceDetectionMFT::InitializeWinMLFaceDetector(this) < 0 )
            {
              *((_WORD *)this + 272) = 1;
              *((_BYTE *)this + 960) = 0;
            }
            else
            {
              *((_BYTE *)this + 544) = 0;
              *((_BYTE *)this + 960) = 1;
              if ( !v8 )
              {
                *((_BYTE *)this + 961) = 1;
                *((_BYTE *)this + 1024) = 0;
              }
            }
          }
          else
          {
            v55 = 0;
            *((_BYTE *)this + 544) = 1;
            v44 = (_QWORD *)Windows::Internal::StringReference::StringReference(
                              v63,
                              (const unsigned __int16 (*)[39])v37);
            if ( (int)Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Media::FaceAnalysis::IFaceTrackerStatics>>(
                        *v44,
                        (char *)this + 17440) < 0
              || (*(int (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 2180) + 72LL))(
                   *((_QWORD *)this + 2180),
                   &v55) < 0
              || !v55 )
            {
              *((_BYTE *)this + 544) = 0;
            }
            *((_BYTE *)this + 960) = 0;
            *((_BYTE *)this + 545) = 0;
            *(_OWORD *)v63 = 0;
            std::shared_ptr<PImage<short,1>>::operator=((char *)this + 696, v63);
            if ( v63[1] )
              std::_Ref_count_base::_Decref((std::_Ref_count_base *)v63[1]);
          }
          if ( *((_BYTE *)this + 544) )
          {
            v45 = FaceDetectionMFT::InitializeNUIFaceDetector(this);
            v3 = v45;
            if ( v45 < 0 )
            {
              if ( g_wppLevels )
                WPP_SF_qD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  55,
                  &WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids,
                  this,
                  v45);
              goto LABEL_143;
            }
          }
          *((_BYTE *)this + 712) = 1;
        }
      }
      goto LABEL_120;
    }
    if ( !v7 && !v9 )
      goto LABEL_120;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 504));
    v39 = *((_BYTE *)this + 960);
    if ( v39 )
    {
      if ( *((_BYTE *)this + 545) )
      {
        if ( *((_BYTE *)this + 852) )
          v40 = FaceDetectionMFT::InitializeWinMLFaceDetector(this);
        else
          v40 = FaceDetectionMFT::InitializeWinMLFaceDetectorWhileProcessing(this);
        if ( v40 < 0 )
        {
          v39 = 0;
        }
        else
        {
          *((_BYTE *)this + 544) = 0;
          *((_BYTE *)this + 960) = 1;
          if ( !v8 )
          {
            *((_BYTE *)this + 961) = 1;
            *((_BYTE *)this + 1024) = 0;
          }
        }
        if ( v39 )
          goto LABEL_96;
      }
      else if ( (unsigned __int8)byte_180160805 >= 0x20u )
      {
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), 53, &WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids, this, 0);
      }
    }
    v55 = 0;
    *((_BYTE *)this + 544) = 1;
    v41 = (_QWORD *)Windows::Internal::StringReference::StringReference(v63, (const unsigned __int16 (*)[39])v38);
    if ( (int)Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Media::FaceAnalysis::IFaceTrackerStatics>>(
                *v41,
                (char *)this + 17440) < 0
      || (*(int (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 2180) + 72LL))(*((_QWORD *)this + 2180), &v55) < 0
      || !v55 )
    {
      *((_BYTE *)this + 544) = 0;
    }
    *((_BYTE *)this + 960) = 0;
    *((_BYTE *)this + 545) = 0;
    *(_OWORD *)v63 = 0;
    std::shared_ptr<PImage<short,1>>::operator=((char *)this + 696, v63);
    if ( v63[1] )
      std::_Ref_count_base::_Decref((std::_Ref_count_base *)v63[1]);
LABEL_96:
    if ( *((_BYTE *)this + 544) )
    {
      v42 = FaceDetectionMFT::InitializeNUIFaceDetector(this);
      v3 = v42;
      if ( v42 < 0 )
      {
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            54,
            &WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids,
            this,
            v42);
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 504));
        goto LABEL_143;
      }
    }
    *((_BYTE *)this + 712) = 1;
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 504));
LABEL_120:
    if ( !*((_BYTE *)this + 852) || *((_DWORD *)this + 212) != 2 || !*((_BYTE *)this + 544) )
    {
LABEL_143:
      if ( SRWLock )
        ReleaseSRWLockExclusive(SRWLock);
      goto LABEL_145;
    }
    v46 = *((_QWORD *)this + 2180);
    v63[0] = 0;
    v61 = 0;
    v58 = 0;
    v47 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v46 + 48LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v63);
    v48 = v47(v46, v63);
    v3 = v48;
    if ( v48 >= 0 )
    {
      v50 = *((_QWORD *)this + 2180);
      v51 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v50 + 48LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v61);
      v48 = v51(v50, &v61);
      v3 = v48;
      if ( v48 >= 0 )
      {
        v52 = *((_QWORD *)this + 2180);
        v53 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v52 + 48LL);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v58);
        v48 = v53(v52, &v58);
        v3 = v48;
        if ( v48 >= 0 )
        {
          v48 = BlockOnCompletionAndGetResults<Windows::Media::FaceAnalysis::FaceTracker *,Windows::Media::FaceAnalysis::IFaceTracker>(
                  v63[0],
                  (char *)this + 672);
          v3 = v48;
          if ( v48 >= 0 )
          {
            v48 = BlockOnCompletionAndGetResults<Windows::Media::FaceAnalysis::FaceTracker *,Windows::Media::FaceAnalysis::IFaceTracker>(
                    v61,
                    (char *)this + 680);
            v3 = v48;
            if ( v48 >= 0 )
            {
              v48 = BlockOnCompletionAndGetResults<Windows::Media::FaceAnalysis::FaceTracker *,Windows::Media::FaceAnalysis::IFaceTracker>(
                      v58,
                      (char *)this + 688);
              v3 = v48;
              if ( v48 >= 0 || !g_wppLevels )
                goto LABEL_142;
              v49 = 61;
              goto LABEL_141;
            }
            if ( g_wppLevels )
            {
              v49 = 60;
              goto LABEL_141;
            }
          }
          else if ( g_wppLevels )
          {
            v49 = 59;
            goto LABEL_141;
          }
        }
        else if ( g_wppLevels )
        {
          v49 = 58;
          goto LABEL_141;
        }
      }
      else if ( g_wppLevels )
      {
        v49 = 57;
        goto LABEL_141;
      }
    }
    else if ( g_wppLevels )
    {
      v49 = 56;
LABEL_141:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v49, &WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids, this, v48);
    }
LABEL_142:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v58);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v61);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v63);
    goto LABEL_143;
  }
  if ( g_wppLevels )
  {
    v12 = 41;
LABEL_11:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, &WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids, this, v11);
  }
LABEL_145:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v59);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v62);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v57);
  return v3;
}

```

## disassembly

```asm
0x180019de0  mov     [rsp-8+arg_10], rbx
0x180019de5  push    rbp
0x180019de6  push    rsi
0x180019de7  push    rdi
0x180019de8  push    r12
0x180019dea  push    r13
0x180019dec  push    r14
0x180019dee  push    r15
0x180019df0  lea     rbp, [rsp-50h]
0x180019df5  sub     rsp, 150h
0x180019dfc  mov     rax, cs:__security_cookie
0x180019e03  xor     rax, rsp
0x180019e06  mov     [rbp+80h+var_38], rax
0x180019e0a  xor     ebx, ebx
0x180019e0c  mov     rsi, rcx
0x180019e0f  lea     rcx, [rbp+80h+var_78]; string
0x180019e13  mov     [rsp+180h+var_148], rbx
0x180019e18  mov     r14d, ebx
0x180019e1b  mov     [rsp+180h+var_120], rbx
0x180019e20  mov     [rsp+180h+var_138], rbx
0x180019e25  mov     rdi, rdx
0x180019e28  call    ??$?0$0BF@@StringReference@Internal@Windows@@QEAA@AEAY0BF@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[21])
0x180019e2d  lea     rcx, [rbp+80h+var_58]; string
0x180019e31  call    ??$?0$0O@@StringReference@Internal@Windows@@QEAA@AEAY0O@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[14])
0x180019e36  lea     rcx, [rbp+80h+var_98]; string
0x180019e3a  call    ??$?0$0BL@@StringReference@Internal@Windows@@QEAA@AEAY0BL@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[27])
0x180019e3f  lea     r9, [rbp+80h+string]; string
0x180019e43  lea     r8, [rbp+80h+hstringHeader]; hstringHeader
0x180019e47  lea     edx, [rbx+15h]; length
0x180019e4a  lea     rcx, aUsewinmlfacede; "UseWinMLFaceDetection"
0x180019e51  call    cs:__imp_WindowsCreateStringReference
0x180019e57  lea     r15d, [rbx+1]
0x180019e5b  mov     r12d, 0C000000Dh
0x180019e61  test    eax, eax
0x180019e63  jns     short loc_180019E77
0x180019e65  xor     r9d, r9d; lpArguments
0x180019e68  xor     r8d, r8d; nNumberOfArguments
0x180019e6b  mov     edx, r15d; dwExceptionFlags
0x180019e6e  mov     ecx, r12d; dwExceptionCode
0x180019e71  call    cs:__imp_RaiseException
0x180019e77  lea     r9, [rbp+80h+var_F8]; string
0x180019e7b  mov     edx, 17h; length
0x180019e80  lea     r8, [rbp+80h+var_F0]; hstringHeader
0x180019e84  lea     rcx, aNoartificialbr; "NoArtificialBrightening"
0x180019e8b  call    cs:__imp_WindowsCreateStringReference
0x180019e91  test    eax, eax
0x180019e93  jns     short loc_180019EA7
0x180019e95  xor     r9d, r9d; lpArguments
0x180019e98  xor     r8d, r8d; nNumberOfArguments
0x180019e9b  mov     edx, r15d; dwExceptionFlags
0x180019e9e  mov     ecx, r12d; dwExceptionCode
0x180019ea1  call    cs:__imp_RaiseException
0x180019ea7  lea     r9, [rbp+80h+var_B8]; string
0x180019eab  mov     edx, 0Eh; length
0x180019eb0  lea     r8, [rbp+80h+var_B0]; hstringHeader
0x180019eb4  lea     rcx, aAdaptivefdrate; "AdaptiveFDRate"
0x180019ebb  call    cs:__imp_WindowsCreateStringReference
0x180019ec1  test    eax, eax
0x180019ec3  jns     short loc_180019ED7
0x180019ec5  xor     r9d, r9d; lpArguments
0x180019ec8  xor     r8d, r8d; nNumberOfArguments
0x180019ecb  mov     edx, r15d; dwExceptionFlags
0x180019ece  mov     ecx, r12d; dwExceptionCode
0x180019ed1  call    cs:__imp_RaiseException
0x180019ed7  mov     [rsp+180h+var_14F], bl
0x180019edb  mov     r12b, bl
0x180019ede  mov     r13b, bl
0x180019ee1  mov     r15b, bl
0x180019ee4  test    rdi, rdi
0x180019ee7  jz      loc_18001A3A0
0x180019eed  mov     rax, [rdi]
0x180019ef0  lea     rcx, [rsp+180h+var_120]
0x180019ef5  mov     rbx, [rax]
0x180019ef8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180019efd  lea     r8, [rsp+180h+var_120]
0x180019f02  mov     rcx, rdi
0x180019f05  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x180019f0c  mov     rax, rbx
0x180019f0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019f14  xor     r15d, r15d
0x180019f17  mov     r14d, eax
0x180019f1a  test    eax, eax
0x180019f1c  jns     short loc_180019F52
0x180019f1e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180019f25  jb      loc_18001A8C9
0x180019f2b  lea     edx, [r15+29h]
0x180019f2f  mov     [rsp+180h+var_160], eax
0x180019f33  mov     rcx, cs:WPP_GLOBAL_Control
0x180019f3a  lea     r8, WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids
0x180019f41  mov     r9, rsi
0x180019f44  mov     rcx, [rcx+10h]
0x180019f48  call    WPP_SF_qD
0x180019f4d  jmp     loc_18001A8C9
0x180019f52  mov     rdi, [rsp+180h+var_120]
0x180019f57  lea     rcx, [rsp+180h+var_148]
0x180019f5c  mov     rax, [rdi]
0x180019f5f  mov     rbx, [rax+30h]
0x180019f63  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180019f68  mov     rdx, [rbp+80h+var_98]
0x180019f6c  lea     r8, [rsp+180h+var_148]
0x180019f71  mov     rcx, rdi
0x180019f74  mov     rax, rbx
0x180019f77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019f7c  test    eax, eax
0x180019f7e  js      loc_18001A010
0x180019f84  lea     rdx, [rsp+180h+var_138]
0x180019f89  lea     rcx, [rsp+180h+var_148]
0x180019f8e  call    ??$As@UIPropertyValue@Foundation@Windows@@@?$ComPtr@UIInspectable@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIPropertyValue@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IInspectable>::As<Windows::Foundation::IPropertyValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValue>>)
0x180019f93  mov     r14d, eax
0x180019f96  test    eax, eax
0x180019f98  jns     short loc_180019FAE
0x180019f9a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180019fa1  jb      loc_18001A8C9
0x180019fa7  mov     edx, 2Ah ; '*'
0x180019fac  jmp     short loc_180019F2F
0x180019fae  mov     rcx, [rsp+180h+var_138]
0x180019fb3  lea     rbx, [rsi+4438h]
0x180019fba  mov     rdx, rbx
0x180019fbd  mov     rax, [rcx]
0x180019fc0  mov     rax, [rax+0A0h]
0x180019fc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019fcc  mov     r14d, eax
0x180019fcf  test    eax, eax
0x180019fd1  jns     short loc_180019FEA
0x180019fd3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180019fda  jb      loc_18001A8C9
0x180019fe0  mov     edx, 2Bh ; '+'
0x180019fe5  jmp     loc_180019F2F
0x180019fea  mov     rax, [rsi+4428h]
0x180019ff1  test    rax, rax
0x180019ff4  jz      short loc_18001A010
0x180019ff6  mov     rcx, [rax+8]
0x180019ffa  test    rcx, rcx
0x180019ffd  jz      short loc_18001A010
0x180019fff  mov     rax, [rcx+8]
0x18001a003  test    rax, rax
0x18001a006  jz      short loc_18001A010
0x18001a008  movups  xmm0, xmmword ptr [rbx]
0x18001a00b  movdqu  xmmword ptr [rax+78h], xmm0
0x18001a010  mov     rdi, [rsp+180h+var_120]
0x18001a015  lea     rcx, [rsp+180h+var_148]
0x18001a01a  mov     rax, [rdi]
0x18001a01d  mov     rbx, [rax+30h]
0x18001a021  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001a026  mov     rdx, [rbp+80h+var_78]
0x18001a02a  lea     r8, [rsp+180h+var_148]
0x18001a02f  mov     rcx, rdi
0x18001a032  mov     rax, rbx
0x18001a035  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a03a  test    eax, eax
0x18001a03c  js      loc_18001A0E4
0x18001a042  lea     rdx, [rsp+180h+var_138]
0x18001a047  mov     [rsp+180h+var_150], r15b
0x18001a04c  lea     rcx, [rsp+180h+var_148]
0x18001a051  call    ??$As@UIPropertyValue@Foundation@Windows@@@?$ComPtr@UIInspectable@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIPropertyValue@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IInspectable>::As<Windows::Foundation::IPropertyValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValue>>)
0x18001a056  mov     r14d, eax
0x18001a059  test    eax, eax
0x18001a05b  jns     short loc_18001A074
0x18001a05d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001a064  jb      loc_18001A8C9
0x18001a06a  mov     edx, 2Ch ; ','
0x18001a06f  jmp     loc_180019F2F
0x18001a074  mov     rcx, [rsp+180h+var_138]
0x18001a079  lea     rdx, [rsp+180h+var_150]
0x18001a07e  mov     rax, [rcx]
0x18001a081  mov     rax, [rax+90h]
0x18001a088  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a08d  mov     r14d, eax
0x18001a090  test    eax, eax
0x18001a092  jns     short loc_18001A0AB
0x18001a094  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001a09b  jb      loc_18001A8C9
0x18001a0a1  mov     edx, 2Dh ; '-'
0x18001a0a6  jmp     loc_180019F2F
0x18001a0ab  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CameraQI2511@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CameraQI2511@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CameraQI2511> `wil::Feature<__WilFeatureTraits_Feature_CameraQI2511>::GetImpl(void)'::`2'::impl
0x18001a0b2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CameraQI2511@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CameraQI2511>::__private_IsEnabled(void)
0x18001a0b7  mov     r8b, [rsp+180h+var_150]
0x18001a0bc  lea     rdx, [rsi+354h]
0x18001a0c3  test    al, al
0x18001a0c5  jz      short loc_18001A0DC
0x18001a0c7  movzx   eax, byte ptr [rdx]
0x18001a0ca  test    r8b, r8b
0x18001a0cd  mov     ecx, r15d
0x18001a0d0  setnz   cl
0x18001a0d3  cmp     eax, ecx
0x18001a0d5  jz      short loc_18001A0DC
0x18001a0d7  mov     [rsp+180h+var_14F], 1
0x18001a0dc  test    r8b, r8b
0x18001a0df  setnz   al
0x18001a0e2  mov     [rdx], al
0x18001a0e4  mov     rdi, [rsp+180h+var_120]
0x18001a0e9  lea     rcx, [rsp+180h+var_148]
0x18001a0ee  mov     rax, [rdi]
0x18001a0f1  mov     rbx, [rax+30h]
0x18001a0f5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001a0fa  mov     rdx, [rbp+80h+var_58]
0x18001a0fe  lea     r8, [rsp+180h+var_148]
0x18001a103  mov     rcx, rdi
0x18001a106  mov     rax, rbx
0x18001a109  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a10e  test    eax, eax
0x18001a110  js      loc_18001A1AD
0x18001a116  lea     rdx, [rsp+180h+var_138]
0x18001a11b  mov     dword ptr [rsp+180h+var_140], r15d
0x18001a120  lea     rcx, [rsp+180h+var_148]
0x18001a125  call    ??$As@UIPropertyValue@Foundation@Windows@@@?$ComPtr@UIInspectable@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIPropertyValue@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IInspectable>::As<Windows::Foundation::IPropertyValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValue>>)
0x18001a12a  mov     r14d, eax
0x18001a12d  test    eax, eax
0x18001a12f  jns     short loc_18001A148
0x18001a131  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001a138  jb      loc_18001A8C9
0x18001a13e  mov     edx, 2Eh ; '.'
0x18001a143  jmp     loc_180019F2F
0x18001a148  mov     rcx, [rsp+180h+var_138]
0x18001a14d  lea     rdx, [rsp+180h+var_140]
0x18001a152  mov     rax, [rcx]
0x18001a155  mov     rax, [rax+60h]
0x18001a159  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a15e  mov     r14d, eax
0x18001a161  test    eax, eax
0x18001a163  jns     short loc_18001A17C
0x18001a165  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001a16c  jb      loc_18001A8C9
0x18001a172  mov     edx, 2Fh ; '/'
0x18001a177  jmp     loc_180019F2F
0x18001a17c  mov     eax, dword ptr [rsp+180h+var_140]
0x18001a180  cmp     eax, 3
0x18001a183  jb      short loc_18001A1A7
0x18001a185  mov     r14d, 80070057h
0x18001a18b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001a192  jb      loc_18001A8C9
0x18001a198  mov     edx, 30h ; '0'
0x18001a19d  mov     [rsp+180h+var_160], r14d
0x18001a1a2  jmp     loc_180019F33
0x18001a1a7  mov     [rsi+350h], eax
0x18001a1ad  mov     rdi, [rsp+180h+var_120]
0x18001a1b2  lea     rcx, [rsp+180h+var_148]
0x18001a1b7  mov     rax, [rdi]
0x18001a1ba  mov     rbx, [rax+30h]
0x18001a1be  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001a1c3  mov     rdx, [rbp+80h+var_F8]
0x18001a1c7  lea     r8, [rsp+180h+var_148]
0x18001a1cc  mov     rcx, rdi
0x18001a1cf  mov     rax, rbx
0x18001a1d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a1d7  test    eax, eax
0x18001a1d9  js      loc_18001A2F3
0x18001a1df  lea     rdx, [rsp+180h+var_138]
0x18001a1e4  mov     [rsp+180h+var_150], r15b
0x18001a1e9  lea     rcx, [rsp+180h+var_148]
0x18001a1ee  call    ??$As@UIPropertyValue@Foundation@Windows@@@?$ComPtr@UIInspectable@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIPropertyValue@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IInspectable>::As<Windows::Foundation::IPropertyValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValue>>)
0x18001a1f3  mov     r14d, eax
0x18001a1f6  test    eax, eax
0x18001a1f8  jns     short loc_18001A211
0x18001a1fa  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001a201  jb      loc_18001A8C9
0x18001a207  mov     edx, 31h ; '1'
0x18001a20c  jmp     loc_180019F2F
0x18001a211  mov     rcx, [rsp+180h+var_138]
0x18001a216  lea     rdx, [rsp+180h+var_150]
0x18001a21b  mov     rax, [rcx]
0x18001a21e  mov     rax, [rax+90h]
0x18001a225  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a22a  mov     r14d, eax
0x18001a22d  test    eax, eax
0x18001a22f  jns     short loc_18001A248
0x18001a231  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001a238  jb      loc_18001A8C9
0x18001a23e  mov     edx, 32h ; '2'
0x18001a243  jmp     loc_180019F2F
0x18001a248  cmp     [rsp+180h+var_150], r15b
0x18001a24d  lea     rbx, [rsi+4408h]
0x18001a254  mov     rcx, rbx
0x18001a257  mov     r13b, 1
0x18001a25a  setnz   al
0x18001a25d  mov     [rsi+3C1h], al
0x18001a263  call    ?reset@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::reset(std::nullptr_t)
0x18001a268  cmp     [rsi+3C1h], r15b
0x18001a26f  jnz     short loc_18001A2EC
0x18001a271  cmp     [rsi+3C0h], r15b
0x18001a278  jz      short loc_18001A2EC
0x18001a27a  mov     eax, [rsi+240h]
0x18001a280  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001a287  imul    eax, eax
0x18001a28a  mov     ecx, eax; unsigned __int64
0x18001a28c  mov     r15d, eax
0x18001a28f  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001a294  mov     rdi, rax
0x18001a297  test    rax, rax
0x18001a29a  jz      short loc_18001A2AE
0x18001a29c  mov     r8d, r15d; Size
0x18001a29f  xor     edx, edx; Val
0x18001a2a1  mov     rcx, rax; void *
0x18001a2a4  call    memset_0
0x18001a2a9  xor     r15d, r15d
0x18001a2ac  jmp     short loc_18001A2B4
0x18001a2ae  xor     r15d, r15d
0x18001a2b1  mov     edi, r15d
0x18001a2b4  mov     rcx, [rbx]; void *
0x18001a2b7  mov     [rsp+180h+SRWLock], r15
  ... truncated ...
```
