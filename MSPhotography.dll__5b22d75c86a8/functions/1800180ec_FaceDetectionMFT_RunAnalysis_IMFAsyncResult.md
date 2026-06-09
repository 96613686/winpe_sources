# FaceDetectionMFT::RunAnalysis(IMFAsyncResult *)

- ea: `0x1800180ec`
- end: `0x18001929f`
- name: `?RunAnalysis@FaceDetectionMFT@@AEAAXPEAUIMFAsyncResult@@@Z`
- size: `4531`
- prototype: `void __fastcall(FaceDetectionMFT *__hidden this, struct IMFAsyncResult *)`
- caller_count: `2`
- callee_count: `36`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180015780`
- `0x18001aad4`

## callees

- `0x1800016b0`
- `0x180001784`
- `0x180002420`
- `0x180005660`
- `0x18000c0b8`
- `0x18000c0f8`
- `0x18000c4fc`
- `0x18000cf1c`
- `0x18000d434`
- `0x18000d748`
- `0x18000eacc`
- `0x18000f0f8`
- `0x18000f36c`
- `0x18000fcdc`
- `0x180010680`
- `0x180010fb0`
- `0x180011780`
- `0x180013b30`
- `0x1800146e4`
- `0x180014858`
- `0x180015004`
- `0x180015690`
- `0x180017f8c`
- `0x1800180ec`
- `0x18001bee4`
- `0x18001c310`
- `0x18001c4d8`
- `0x18001c70c`
- `0x18001c99c`
- `0x18001cb74`
- `0x18001d7d8`
- `0x180026668`
- `0x180131858`
- `0x180132398`
- `0x180132444`
- `0x180142010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018377`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001912e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001913d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018377`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001912e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001913d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800184ae`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800191a1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800191ab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800184ae`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800191a1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800191ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800191cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800191ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800191cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800191ea`
- `MFPlat!MFGetSystemTime` at `0x180018610`
- `MFPlat!MFGetSystemTime` at `0x180018610`

## pseudocode

```c
void __fastcall FaceDetectionMFT::RunAnalysis(FaceDetectionMFT *this, struct IMFAsyncResult *a2)
{
  unsigned int v3; // r12d
  __int64 v4; // rdi
  __int64 v5; // r15
  __int64 v6; // rsi
  CAggregatePhotographyTelemetry *v7; // r14
  signed __int32 v8; // ebx
  int v9; // eax
  __int64 v10; // rdx
  bool v11; // al
  int SampleRotation; // eax
  float v13; // xmm11_4
  __int64 v14; // rbx
  __int64 v15; // rbx
  __int64 v16; // rbx
  int v17; // eax
  int v18; // ecx
  int v19; // r8d
  int v20; // r9d
  int v21; // eax
  __int64 v22; // rcx
  int v23; // eax
  __int64 v24; // rdx
  FaceDetectionModelRunner *v25; // rbx
  unsigned __int8 *v26; // rcx
  unsigned int v27; // esi
  __int64 v28; // rdi
  __int64 (__fastcall *v29)(__int64, _QWORD, unsigned __int8 **); // rbx
  int updated; // eax
  int v31; // r8d
  __int64 v32; // rdx
  unsigned int v33; // r12d
  __int64 (__fastcall *v34)(__int64, __int64, const GUID *, _QWORD, unsigned int, int, __int64 *, _QWORD, GUID *, __int64 *); // rbx
  int v35; // eax
  __int64 v36; // rdx
  __int64 v37; // rdi
  __int64 (__fastcall *v38)(__int64, __int64, unsigned __int8 **); // rbx
  int v39; // eax
  __int64 v40; // rdx
  __int64 v41; // rdi
  __int64 (__fastcall *v42)(__int64, __int64, unsigned __int8 **); // rbx
  __int64 v43; // rdi
  __int64 (__fastcall *v44)(__int64, __int64, unsigned __int8 **); // rbx
  __int64 v45; // rdi
  __int64 (__fastcall *v46)(__int64, __int64, unsigned __int8 **); // rbx
  __int64 v47; // rdi
  __int64 (__fastcall *v48)(__int64, __int64, unsigned __int8 **); // rbx
  unsigned __int8 *v49; // rdi
  unsigned int v50; // esi
  __int64 v51; // rdi
  __int64 (__fastcall *v52)(__int64, _QWORD, unsigned __int8 **); // rbx
  int v53; // eax
  __int64 v54; // rcx
  float v55; // xmm6_4
  float v56; // xmm7_4
  float v57; // xmm8_4
  float v58; // xmm9_4
  __int64 (__fastcall *v59)(__int64, __int128 *, unsigned __int8 **); // rbx
  int v60; // eax
  __int64 v61; // rdx
  __int64 v62; // rdx
  int v63; // eax
  __int64 v64; // rdx
  void *v65; // rcx
  void *v66; // rcx
  unsigned int v67; // [rsp+68h] [rbp-A0h]
  unsigned __int8 *v68; // [rsp+70h] [rbp-98h] BYREF
  __int64 v69; // [rsp+78h] [rbp-90h] BYREF
  CAggregatePhotographyTelemetry *v70; // [rsp+80h] [rbp-88h]
  bool v71; // [rsp+88h] [rbp-80h] BYREF
  unsigned __int8 *v72; // [rsp+90h] [rbp-78h] BYREF
  unsigned __int8 *v73[2]; // [rsp+98h] [rbp-70h] BYREF
  unsigned int v74; // [rsp+A8h] [rbp-60h] BYREF
  unsigned int v75; // [rsp+ACh] [rbp-5Ch] BYREF
  int v76; // [rsp+B0h] [rbp-58h] BYREF
  __int64 v77; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v78[4]; // [rsp+C0h] [rbp-48h] BYREF
  __int16 v79; // [rsp+E0h] [rbp-28h]
  __int64 v80; // [rsp+E8h] [rbp-20h] BYREF
  __int64 v81; // [rsp+F0h] [rbp-18h] BYREF
  __int64 v82; // [rsp+F8h] [rbp-10h] BYREF
  __int64 v83; // [rsp+100h] [rbp-8h] BYREF
  __int64 v84; // [rsp+108h] [rbp+0h] BYREF
  __int64 v85; // [rsp+110h] [rbp+8h] BYREF
  __int64 v86; // [rsp+118h] [rbp+10h] BYREF
  __int128 v87; // [rsp+128h] [rbp+20h] BYREF
  __int128 v88; // [rsp+138h] [rbp+30h] BYREF
  _BYTE v89[16]; // [rsp+148h] [rbp+40h] BYREF
  __int128 v90; // [rsp+158h] [rbp+50h] BYREF
  __int64 v91; // [rsp+168h] [rbp+60h] BYREF
  int v92; // [rsp+170h] [rbp+68h]
  unsigned int v93; // [rsp+174h] [rbp+6Ch]
  unsigned __int8 *v94; // [rsp+178h] [rbp+70h] BYREF
  _BYTE v95[40]; // [rsp+180h] [rbp+78h] BYREF
  unsigned int v96; // [rsp+1A8h] [rbp+A0h]
  unsigned int v97; // [rsp+1ACh] [rbp+A4h]
  __int128 v98; // [rsp+1B0h] [rbp+A8h]
  __int128 v99; // [rsp+1C0h] [rbp+B8h]
  int v100; // [rsp+1D0h] [rbp+C8h]
  unsigned __int8 v101; // [rsp+1D4h] [rbp+CCh]
  __int64 v102; // [rsp+1F0h] [rbp+E8h]
  char v103; // [rsp+1F9h] [rbp+F1h]
  __int64 v104[3]; // [rsp+1FAh] [rbp+F2h] BYREF
  __int128 v105; // [rsp+218h] [rbp+110h]
  __int64 v106; // [rsp+230h] [rbp+128h]
  __int64 v107; // [rsp+238h] [rbp+130h]

  v3 = 0;
  v4 = 0;
  v86 = 0;
  v5 = 0;
  v85 = 0;
  v6 = 0;
  v84 = 0;
  v77 = 0;
  v80 = 0;
  v83 = 0;
  v82 = 0;
  v81 = 0;
  v7 = 0;
  v70 = 0;
  AnalysisParameters::AnalysisParameters((AnalysisParameters *)&v94);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_MediaQI2505>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_MediaQI2505>::GetImpl'::`2'::impl)
    || *((_QWORD *)this + 87)
    || *((_QWORD *)this + 83)
    || *((int *)this + 4370) < 0
    || (v8 = FaceDetectionMFT::InitializeSoftwareFaceDector(this),
        _InterlockedCompareExchange((volatile signed __int32 *)this + 4370, v8, 0),
        v8 >= 0) )
  {
    v9 = FaceDetectionMFT::ConvertSample(this, *((struct IMFSample **)this + 79), 0, 0);
    v8 = v9;
    if ( v9 < 0 )
    {
      if ( !g_wppLevels )
      {
LABEL_38:
        v7 = v70;
        goto LABEL_39;
      }
      v10 = 115;
LABEL_11:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, &WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids, this, v9);
      goto LABEL_38;
    }
    if ( *((_BYTE *)this + 1024) )
    {
      v71 = 0;
      if ( (unsigned __int8)byte_180160805 >= 0x20u )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 116, &WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids);
      v9 = FaceDetectionMFT::BrightenSample(this, *((struct IMFSample **)this + 80), &v71);
      v8 = v9;
      if ( v9 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_38;
        v10 = 117;
        goto LABEL_11;
      }
      v11 = !v71;
      *((_BYTE *)this + 1026) = !v71;
      if ( v11 )
      {
        if ( (unsigned __int8)byte_180160805 >= 0x20u )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 118, &WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids);
        if ( *((_DWORD *)this + 212) == 2 )
        {
          v8 = 0;
          v7 = 0;
          goto LABEL_39;
        }
        *((_DWORD *)this + 252) = *((_DWORD *)this + 253);
        SampleRotation = FaceDetectionMFT::GetSampleRotation(this);
        *((_DWORD *)this + 253) = SampleRotation;
        if ( SampleRotation != *((_DWORD *)this + 252) )
          *((_BYTE *)this + 712) = 1;
        v9 = FaceDetectionMFT::ConvertSample(this, *((struct IMFSample **)this + 79), 0, 0);
        v8 = v9;
        if ( v9 < 0 )
        {
          if ( !g_wppLevels )
            goto LABEL_38;
          v10 = 119;
          goto LABEL_11;
        }
      }
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 632);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 464));
    v74 = *((_DWORD *)this + 202);
    v76 = *((_DWORD *)this + 145);
    v75 = *((_DWORD *)this + 146);
    v13 = *((float *)this + 143);
    v67 = *((_DWORD *)this + 253);
    v14 = *((_QWORD *)this + 80);
    if ( v14 )
    {
      v73[0] = *((unsigned __int8 **)this + 80);
      Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Media::Core::LowLightFusionResult *,double>>::InternalAddRef(v73);
      v73[0] = 0;
      v4 = v14;
      v86 = v14;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v73);
    }
    v15 = *((_QWORD *)this + 81);
    if ( v15 )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v15 + 8LL))(*((_QWORD *)this + 81));
      v73[0] = 0;
      v5 = v15;
      v85 = v15;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v73);
    }
    v16 = *((_QWORD *)this + 82);
    if ( v16 )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v16 + 8LL))(*((_QWORD *)this + 82));
      v73[0] = 0;
      v6 = v16;
      v84 = v16;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v73);
    }
    Microsoft::WRL::ComPtr<Windows::Media::FaceAnalysis::IFaceTracker>::operator=(&v80, (char *)this + 664);
    Microsoft::WRL::ComPtr<Windows::Media::FaceAnalysis::IFaceTracker>::operator=(&v83, (char *)this + 672);
    Microsoft::WRL::ComPtr<Windows::Media::FaceAnalysis::IFaceTracker>::operator=(&v82, (char *)this + 680);
    Microsoft::WRL::ComPtr<Windows::Media::FaceAnalysis::IFaceTracker>::operator=(&v81, (char *)this + 688);
    v70 = (CAggregatePhotographyTelemetry *)*((_QWORD *)this + 2181);
    AnalysisParameters::operator=((__int64 *)&v94, (__int64 *)this + 95);
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 464));
    v17 = CCoreMFT::EnableLongRunningWorkQueue(this);
    v8 = v17;
    if ( v17 < 0 )
    {
      if ( g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 120, &WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids, this, v17);
      goto LABEL_37;
    }
    v69 = 0;
    if ( *((_BYTE *)this + 545) )
    {
      v75 = 0;
      v78[0] = (__int64)v78;
      v78[1] = (__int64)v78;
      v78[2] = 0;
      v78[3] = 0;
      v79 = 2048;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v69);
      v23 = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Media::FaceAnalysis::DetectedFace,Windows::Foundation::Collections::Internal::AgileVector<Windows::Media::FaceAnalysis::DetectedFace *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Media::FaceAnalysis::DetectedFace *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Media::FaceAnalysis::DetectedFace *>,0>>(
              v22,
              &v69);
      v8 = v23;
      if ( v23 < 0 )
      {
        if ( !g_wppLevels )
        {
LABEL_60:
          utl::_HashTable<Windows::Media::FaceAnalysis::IDetectedFace *,utl::pair<Windows::Media::FaceAnalysis::IDetectedFace * const,float>,utl::hash<Windows::Media::FaceAnalysis::IDetectedFace *>,utl::equal_to<Windows::Media::FaceAnalysis::IDetectedFace *>,utl::allocator<utl::pair<Windows::Media::FaceAnalysis::IDetectedFace * const,float>>,0>::_ClearList(v78);
          utl::_HashTable<enum SampleRotation,utl::pair<enum SampleRotation const,wistd::unique_ptr<FaceFilter,wistd::default_delete<FaceFilter>>>,utl::hash<enum SampleRotation>,utl::equal_to<enum SampleRotation>,utl::allocator<utl::pair<enum SampleRotation const,wistd::unique_ptr<FaceFilter,wistd::default_delete<FaceFilter>>>>,0>::_FreeBuckets(v78);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v69);
LABEL_37:
          v3 = v67;
          goto LABEL_38;
        }
        v24 = 121;
LABEL_59:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v24, &WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids, this, v23);
        goto LABEL_60;
      }
      v25 = (FaceDetectionModelRunner *)*((_QWORD *)this + 87);
      v73[0] = (unsigned __int8 *)v69;
      if ( v69 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v69 + 8LL))(v69);
      v26 = (unsigned __int8 *)*((_QWORD *)this + 81);
      v72 = v26;
      if ( v26 )
        (*(void (__fastcall **)(unsigned __int8 *))(*(_QWORD *)v26 + 8LL))(v26);
      v23 = FaceDetectionModelRunner::ProcessSample(v25, v67, (__int64)&v72, (__int64)v73, (__int64)v78, (__int64)v104);
      v8 = v23;
      if ( v23 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_60;
        v24 = 122;
        goto LABEL_59;
      }
      v23 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v69 + 56LL))(v69, &v75);
      v8 = v23;
      if ( v23 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_60;
        v24 = 123;
        goto LABEL_59;
      }
      v27 = 0;
      if ( v75 )
      {
        while ( 1 )
        {
          v68 = 0;
          v90 = 0;
          v28 = v69;
          v29 = *(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int8 **))(*(_QWORD *)v69 + 48LL);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v68);
          updated = v29(v28, v27, &v68);
          v8 = updated;
          if ( updated < 0 )
          {
            if ( g_wppLevels )
            {
              v32 = 124;
              goto LABEL_84;
            }
            goto LABEL_85;
          }
          updated = (*(__int64 (__fastcall **)(unsigned __int8 *, __int128 *))(*(_QWORD *)v68 + 48LL))(v68, &v90);
          v8 = updated;
          if ( updated < 0 )
            break;
          updated = FaceDetectionMFT::UpdateRectOrientation(this, &v90, v67);
          v8 = updated;
          if ( updated < 0 )
          {
            if ( g_wppLevels )
            {
              v32 = 126;
LABEL_84:
              WPP_SF_qD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                v32,
                &WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids,
                this,
                updated);
              goto LABEL_85;
            }
            goto LABEL_85;
          }
          v73[0] = v94;
          if ( v94 )
            (*(void (__fastcall **)(unsigned __int8 *))(*(_QWORD *)v94 + 8LL))(v94);
          v72 = v68;
          utl::unordered_map<Windows::Media::FaceAnalysis::IDetectedFace *,float,utl::hash<Windows::Media::FaceAnalysis::IDetectedFace *>,utl::equal_to<Windows::Media::FaceAnalysis::IDetectedFace *>,utl::allocator<utl::pair<Windows::Media::FaceAnalysis::IDetectedFace * const,float>>>::at(
            v78,
            &v72);
          v87 = v90;
          updated = FaceDetectionMFT::DeDuplicateAndUpdateFace(
                      (_DWORD)this,
                      (unsigned int)&v87,
                      v31,
                      (unsigned int)v73,
                      (__int64)v95);
          v8 = updated;
          if ( updated < 0 )
          {
            if ( !g_wppLevels )
              goto LABEL_85;
            v32 = 127;
            goto LABEL_84;
          }
          if ( (unsigned __int8)byte_180160805 >= 0x20u )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 27),
              128,
              &WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids,
              this,
              v67);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v68);
          if ( ++v27 >= v75 )
            goto LABEL_81;
        }
        if ( g_wppLevels )
        {
          v32 = 125;
          goto LABEL_84;
        }
LABEL_85:
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v68);
        goto LABEL_60;
      }
LABEL_81:
      utl::_HashTable<Windows::Media::FaceAnalysis::IDetectedFace *,utl::pair<Windows::Media::FaceAnalysis::IDetectedFace * const,float>,utl::hash<Windows::Media::FaceAnalysis::IDetectedFace *>,utl::equal_to<Windows::Media::FaceAnalysis::IDetectedFace *>,utl::allocator<utl::pair<Windows::Media::FaceAnalysis::IDetectedFace * const,float>>,0>::_ClearList(v78);
      utl::_HashTable<enum SampleRotation,utl::pair<enum SampleRotation const,wistd::unique_ptr<FaceFilter,wistd::default_delete<FaceFilter>>>,utl::hash<enum SampleRotation>,utl::equal_to<enum SampleRotation>,utl::allocator<utl::pair<enum SampleRotation const,wistd::unique_ptr<FaceFilter,wistd::default_delete<FaceFilter>>>>,0>::_FreeBuckets(v78);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v69);
LABEL_142:
      v102 = *((_QWORD *)this + 92);
      v3 = v67;
      if ( v101 && v100 == 2 && v67 != 3 )
      {
        AnalysisParameters::operator=((__int64 *)this + 95, (__int64 *)&v94);
        goto LABEL_38;
      }
      v69 = (__int64)this + 424;
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 424));
      v68 = (unsigned __int8 *)this + 464;
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 464));
      if ( !*((_BYTE *)this + 713) )
      {
        v73[0] = 0;
        v72 = 0;
        v63 = FaceDetectionMFT::HandleSoftwareMetadata(this, (struct AnalysisParameters *)&v94, v73, &v72);
        v8 = v63;
        if ( v63 >= 0 )
        {
          v65 = (void *)*((_QWORD *)this + 122);
          *((unsigned __int8 **)this + 122) = v73[0];
          if ( v65 )
            CoTaskMemFree(v65);
          v66 = (void *)*((_QWORD *)this + 123);
          *((_QWORD *)this + 123) = v72;
          if ( v66 )
            CoTaskMemFree(v66);
          *((_OWORD *)this + 51) = v98;
          *((_OWORD *)this + 52) = v99;
          *((_BYTE *)this + 889) = v103;
          *((_BYTE *)this + 890) = v104[0];
          *(_OWORD *)((char *)this + 920) = v105;
          *((_QWORD *)this + 110) = v102;
          *((_QWORD *)this + 118) = v106;
          v63 = FaceDetectionMFT::HandleSoftwareEvent(this, (struct AnalysisParameters *)&v94);
          v8 = v63;
          if ( v63 >= 0 || !g_wppLevels )
            goto LABEL_165;
          v64 = 146;
          goto LABEL_164;
        }
        if ( g_wppLevels )
        {
          v64 = 145;
LABEL_164:
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v64,
            &WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids,
            this,
            v63);
        }
      }
LABEL_165:
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 464));
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 424));
      goto LABEL_38;
    }
    v74 = 0;
    v68 = 0;
    v91 = 0;
    v33 = v76;
    v92 = v76;
    v93 = v75;
    v34 = *(__int64 (__fastcall **)(__int64, __int64, const GUID *, _QWORD, unsigned int, int, __int64 *, _QWORD, GUID *, __int64 *))(*(_QWORD *)v6 + 48LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v77);
    v35 = v34(v6, v4, &MFVideoFormat_NV12, v33, v75, 1, &v91, 0, &GUID_0cc06625_90fc_4c92_bd95_7ded21819d1c, &v77);
    v8 = v35;
    if ( v35 < 0 )
    {
      if ( !g_wppLevels )
      {
LABEL_96:
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v68);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v69);
        goto LABEL_37;
      }
      v36 = 129;
LABEL_95:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v36, &WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids, this, v35);
      goto LABEL_96;
    }
    if ( v101 && v100 == 2 )
    {
      v3 = v67;
      if ( v67 )
      {
        switch ( v67 )
        {
          case 1u:
            v43 = v83;
            v44 = *(__int64 (__fastcall **)(__int64, __int64, unsigned __int8 **))(*(_QWORD *)v83 + 48LL);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v68);
            v39 = v44(v43, v77, &v68);
            v8 = v39;
            if ( v39 < 0 )
            {
              if ( !g_wppLevels )
                goto LABEL_109;
              v40 = 131;
              goto LABEL_108;
            }
            break;
          case 2u:
            v41 = v82;
            v42 = *(__int64 (__fastcall **)(__int64, __int64, unsigned __int8 **))(*(_QWORD *)v82 + 48LL);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v68);
            v39 = v42(v41, v77, &v68);
            v8 = v39;
            if ( v39 < 0 )
            {
              if ( !g_wppLevels )
                goto LABEL_109;
              v40 = 132;
              goto LABEL_108;
            }
            break;
          case 3u:
            v37 = v81;
            v38 = *(__int64 (__fastcall **)(__int64, __int64, unsigned __int8 **))(*(_QWORD *)v81 + 48LL);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v68);
            v39 = v38(v37, v77, &v68);
            v8 = v39;
            if ( v39 < 0 )
            {
              if ( g_wppLevels )
              {
                v40 = 133;
LABEL_108:
                WPP_SF_qD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  v40,
                  &WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids,
                  this,
                  v39);
              }
LABEL_109:
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v68);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v69);
              goto LABEL_38;
            }
            break;
          default:
            if ( (unsigned __int8)byte_180160805 >= 0x20u )
              WPP_SF_q(
                *((_QWORD *)WPP_GLOBAL_Control + 27),
                134,
                &WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids,
                this);
            break;
        }
      }
      else
      {
        v45 = v80;
        v46 = *(__int64 (__fastcall **)(__int64, __int64, unsigned __int8 **))(*(_QWORD *)v80 + 48LL);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v68);
        v39 = v46(v45, v77, &v68);
        v8 = v39;
        if ( v39 < 0 )
        {
          if ( !g_wppLevels )
            goto LABEL_109;
          v40 = 130;
          goto LABEL_108;
        }
      }
    }
    else
    {
      v47 = v80;
      v48 = *(__int64 (__fastcall **)(__int64, __int64, unsigned __int8 **))(*(_QWORD *)v80 + 48LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v68);
      v35 = v48(v47, v77, &v68);
      v8 = v35;
      if ( v35 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_96;
        v36 = 135;
        goto LABEL_95;
      }
      v3 = v67;
    }
    v49 = v68;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v69);
    v8 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVector<Windows::Media::FaceAnalysis::DetectedFace *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVector<Windows::Media::FaceAnalysis::DetectedFace *> *>>(v49);
    if ( v8 < 0
      || (v8 = (*(__int64 (__fastcall **)(unsigned __int8 *, __int64 *))(*(_QWORD *)v49 + 64LL))(v49, &v69), v8 < 0) )
    {
      if ( g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 136, &WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids, this, v8);
      goto LABEL_109;
    }
    v39 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v69 + 56LL))(v69, &v74);
    v8 = v39;
    if ( v39 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_109;
      v40 = 137;
      goto LABEL_108;
    }
    v50 = 0;
    if ( !v74 )
    {
LABEL_141:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v68);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v69);
      goto LABEL_142;
    }
    while ( 1 )
    {
      v72 = 0;
      v90 = 0;
      v51 = v69;
      v52 = *(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int8 **))(*(_QWORD *)v69 + 48LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v72);
      v53 = v52(v51, v50, &v72);
      v8 = v53;
      if ( v53 < 0 )
        break;
      v53 = (*(__int64 (__fastcall **)(unsigned __int8 *, __int128 *))(*(_QWORD *)v72 + 48LL))(v72, &v90);
      v8 = v53;
      if ( v53 < 0 )
      {
        if ( g_wppLevels )
        {
          v62 = 139;
LABEL_155:
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v62,
            &WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids,
            this,
            v53);
          goto LABEL_150;
        }
        goto LABEL_150;
      }
      v53 = FaceDetectionMFT::UpdateRectOrientation(this, &v90, v3);
      v8 = v53;
      if ( v53 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_150;
        v62 = 140;
        goto LABEL_155;
      }
      v55 = (float)(int)v90 * v13;
      *(float *)v73 = v55;
      v56 = (float)SDWORD1(v90) * v13;
      *((float *)v73 + 1) = v56;
      v57 = (float)SDWORD2(v90) * v13;
      *(float *)&v73[1] = v57;
      v58 = (float)SHIDWORD(v90) * v13;
      *((float *)&v73[1] + 1) = v58;
      if ( (unsigned __int8)FaceDetectionMFT::ValidateRect(v54, v73, v96, v97) )
      {
        LODWORD(v90) = (int)(float)(v55 + 0.5);
        DWORD1(v90) = (int)(float)(v56 + 0.5);
        DWORD2(v90) = (int)(float)(v57 + 0.5);
        HIDWORD(v90) = (int)(float)(v58 + 0.5);
        v73[0] = 0;
        v59 = *(__int64 (__fastcall **)(__int64, __int128 *, unsigned __int8 **))(*(_QWORD *)v5 + 48LL);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v73);
        v88 = v90;
        v60 = v59(v5, &v88, v73);
        v8 = v60;
        if ( v60 < 0 )
        {
          if ( g_wppLevels )
          {
            v61 = 141;
LABEL_148:
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v61,
              &WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids,
              this,
              v60);
          }
LABEL_149:
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v73);
          goto LABEL_150;
        }
        v60 = (*(__int64 (__fastcall **)(unsigned __int8 *, unsigned __int8 *))(*(_QWORD *)v94 + 104LL))(v94, v73[0]);
        v8 = v60;
        if ( v60 < 0 )
        {
          if ( g_wppLevels )
          {
            v61 = 142;
            goto LABEL_148;
          }
          goto LABEL_149;
        }
        *(unsigned __int8 **)&v87 = v73[0];
        DWORD2(v87) = 1063675494;
        utl::_HashTable<Windows::Media::FaceAnalysis::IDetectedFace *,utl::pair<Windows::Media::FaceAnalysis::IDetectedFace * const,float>,utl::hash<Windows::Media::FaceAnalysis::IDetectedFace *>,utl::equal_to<Windows::Media::FaceAnalysis::IDetectedFace *>,utl::allocator<utl::pair<Windows::Media::FaceAnalysis::IDetectedFace * const,float>>,0>::_InsertImpl<utl::pair<Windows::Media::FaceAnalysis::IDetectedFace * const,float> const &>(
          v95,
          v89,
          &v87);
        if ( (unsigned __int8)byte_180160805 >= 0x20u )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 27),
            143,
            &WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids,
            this,
            v3);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v73);
      }
      else if ( (unsigned __int8)byte_180160805 >= 0x20u )
      {
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          144,
          &WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids,
          this,
          v50);
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v72);
      if ( ++v50 >= v74 )
        goto LABEL_141;
    }
    if ( g_wppLevels )
    {
      v62 = 138;
      goto LABEL_155;
    }
LABEL_150:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v72);
    goto LABEL_109;
  }
  if ( g_wppLevels )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 114, &WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids, this, v8);
LABEL_39:
  CCoreMFT::DisableLongRunningWorkQueue(this);
  CCoreMFT::CancelDeadline(this);
  if ( v8 < 0 )
  {
    if ( byte_180160805 )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), 147, &WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids, this, v8);
    if ( v7 )
    {
      CAggregatePhotographyTelemetry::AddData(v7, 4u, 0.0);
      if ( (unsigned int)dword_18015F0D0 > 5 )
      {
        if ( (unsigned __int8)tlgKeywordOn(&dword_18015F0D0, 0x400000000000LL) )
        {
          v76 = v8;
          v73[0] = (unsigned __int8 *)this + 17464;
          v74 = 1;
          v72 = "FaceDetection";
          v69 = 0x1000000;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
            v18,
            (unsigned int)byte_180151009,
            v19,
            v20,
            (__int64)&v69,
            (__int64)&v72,
            (__int64)&v74,
            (__int64)v73,
            (__int64)&v76);
        }
      }
    }
  }
  if ( !v101 || v100 != 2 || v3 == 3 )
  {
    if ( v7 )
    {
      v76 = 0;
      v21 = MFGetSystemTime();
      CAggregatePhotographyTelemetry::AddData(v7, 3u, (double)(v21 - (int)v107) / 10000.0);
      CAggregatePhotographyTelemetry::AddData(v7, 0xAu, (double)v101);
      CAggregatePhotographyTelemetry::AddData(v7, 0xBu, (double)v100);
      if ( v94 )
      {
        if ( (*(int (__fastcall **)(unsigned __int8 *, int *))(*(_QWORD *)v94 + 56LL))(v94, &v76) >= 0 )
          CAggregatePhotographyTelemetry::AddData(v7, 0xCu, (double)v76);
      }
    }
    FaceDetectionMFT::ResetAnalysisState(this);
  }
  AnalysisParameters::~AnalysisParameters((AnalysisParameters *)&v94);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v81);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v82);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v83);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v80);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v77);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v84);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v85);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v86);
}

```

## disassembly

```asm
0x1800180ec  mov     rax, rsp
0x1800180ef  push    rbp
0x1800180f0  push    rbx
0x1800180f1  push    rsi
0x1800180f2  push    rdi
0x1800180f3  push    r12
0x1800180f5  push    r13
0x1800180f7  push    r14
0x1800180f9  push    r15
0x1800180fb  lea     rbp, [rax-208h]
0x180018102  sub     rsp, 2C8h
0x180018109  movaps  xmmword ptr [rax-58h], xmm6
0x18001810d  movaps  xmmword ptr [rax-68h], xmm7
0x180018111  movaps  xmmword ptr [rax-78h], xmm8
0x180018116  movaps  xmmword ptr [rax-88h], xmm9
0x18001811e  movaps  xmmword ptr [rax-98h], xmm10
0x180018126  movaps  xmmword ptr [rax-0A8h], xmm11
0x18001812e  mov     rax, cs:__security_cookie
0x180018135  xor     rax, rsp
0x180018138  mov     [rbp+200h+var_B0], rax
0x18001813f  mov     r13, rcx
0x180018142  xor     ebx, ebx
0x180018144  mov     r12d, ebx
0x180018147  mov     edi, ebx
0x180018149  mov     [rbp+200h+var_1F0], rbx
0x18001814d  mov     r15d, ebx
0x180018150  mov     [rbp+200h+var_1F8], rbx
0x180018154  mov     esi, ebx
0x180018156  mov     [rbp+200h+var_200], rbx
0x18001815a  mov     [rbp+200h+var_250], rbx
0x18001815e  mov     [rbp+200h+var_220], rbx
0x180018162  mov     [rbp+200h+var_208], rbx
0x180018166  mov     [rbp+200h+var_210], rbx
0x18001816a  mov     [rbp+200h+var_218], rbx
0x18001816e  mov     r14d, ebx
0x180018171  mov     [rsp+300h+var_288], rbx
0x180018176  lea     rcx, [rbp+200h+var_190]; this
0x18001817a  call    ??0AnalysisParameters@@QEAA@XZ; AnalysisParameters::AnalysisParameters(void)
0x18001817f  nop
0x180018180  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_MediaQI2505@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_MediaQI2505@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MediaQI2505> `wil::Feature<__WilFeatureTraits_Feature_MediaQI2505>::GetImpl(void)'::`2'::impl
0x180018187  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_MediaQI2505@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MediaQI2505>::__private_IsEnabled(void)
0x18001818c  test    al, al
0x18001818e  jnz     short loc_1800181FA
0x180018190  cmp     [r13+2B8h], rbx
0x180018197  jnz     short loc_1800181FA
0x180018199  cmp     [r13+298h], rbx
0x1800181a0  jnz     short loc_1800181FA
0x1800181a2  mov     eax, [r13+4448h]
0x1800181a9  test    eax, eax
0x1800181ab  js      short loc_1800181FA
0x1800181ad  mov     rcx, r13; this
0x1800181b0  call    ?InitializeSoftwareFaceDector@FaceDetectionMFT@@AEAAJXZ; FaceDetectionMFT::InitializeSoftwareFaceDector(void)
0x1800181b5  mov     ebx, eax
0x1800181b7  xor     eax, eax
0x1800181b9  lock cmpxchg [r13+4448h], ebx
0x1800181c2  test    ebx, ebx
0x1800181c4  jns     short loc_1800181FA
0x1800181c6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800181cd  jb      loc_1800184FC
0x1800181d3  lea     edx, [r14+72h]
0x1800181d7  mov     [rsp+300h+var_2E0], ebx
0x1800181db  mov     r9, r13
0x1800181de  lea     r8, WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids
0x1800181e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800181ec  mov     rcx, [rcx+10h]
0x1800181f0  call    WPP_SF_qD
0x1800181f5  jmp     loc_1800184FC
0x1800181fa  lea     r14, [r13+278h]
0x180018201  xor     r9d, r9d; struct tagRECT *
0x180018204  xor     r8d, r8d; struct tagRECT *
0x180018207  mov     rdx, [r14]; struct IMFSample *
0x18001820a  mov     rcx, r13; this
0x18001820d  call    ?ConvertSample@FaceDetectionMFT@@AEAAJPEAUIMFSample@@PEAUtagRECT@@1@Z; FaceDetectionMFT::ConvertSample(IMFSample *,tagRECT *,tagRECT *)
0x180018212  mov     ebx, eax
0x180018214  test    eax, eax
0x180018216  jns     short loc_18001824D
0x180018218  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001821f  jb      loc_1800184F7
0x180018225  mov     edx, 73h ; 's'
0x18001822a  mov     [rsp+300h+var_2E0], eax
0x18001822e  mov     r9, r13
0x180018231  lea     r8, WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids
0x180018238  mov     rcx, cs:WPP_GLOBAL_Control
0x18001823f  mov     rcx, [rcx+10h]
0x180018243  call    WPP_SF_qD
0x180018248  jmp     loc_1800184F7
0x18001824d  cmp     byte ptr [r13+400h], 0
0x180018255  jz      loc_180018365
0x18001825b  mov     [rbp+200h+var_280], 0
0x18001825f  cmp     cs:byte_180160805, 20h ; ' '
0x180018266  jb      short loc_180018287
0x180018268  mov     edx, 74h ; 't'
0x18001826d  lea     r8, WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids
0x180018274  mov     rcx, cs:WPP_GLOBAL_Control
0x18001827b  mov     rcx, [rcx+0D8h]
0x180018282  call    WPP_SF_
0x180018287  lea     r8, [rbp+200h+var_280]; bool *
0x18001828b  mov     rdx, [r13+280h]; struct IMFSample *
0x180018292  mov     rcx, r13; this
0x180018295  call    ?BrightenSample@FaceDetectionMFT@@AEAAJPEAUIMFSample@@PEA_N@Z; FaceDetectionMFT::BrightenSample(IMFSample *,bool *)
0x18001829a  mov     ebx, eax
0x18001829c  test    eax, eax
0x18001829e  jns     short loc_1800182B7
0x1800182a0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800182a7  jb      loc_1800184F7
0x1800182ad  mov     edx, 75h ; 'u'
0x1800182b2  jmp     loc_18001822A
0x1800182b7  cmp     [rbp+200h+var_280], 0
0x1800182bb  setz    al
0x1800182be  mov     [r13+402h], al
0x1800182c5  test    al, al
0x1800182c7  jz      loc_180018365
0x1800182cd  cmp     cs:byte_180160805, 20h ; ' '
0x1800182d4  jb      short loc_1800182F5
0x1800182d6  mov     edx, 76h ; 'v'
0x1800182db  lea     r8, WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids
0x1800182e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800182e9  mov     rcx, [rcx+0D8h]
0x1800182f0  call    WPP_SF_
0x1800182f5  cmp     dword ptr [r13+350h], 2
0x1800182fd  jz      short loc_18001835B
0x1800182ff  mov     eax, [r13+3F4h]
0x180018306  mov     [r13+3F0h], eax
0x18001830d  mov     rcx, r13
0x180018310  call    ?GetSampleRotation@FaceDetectionMFT@@AEAA?AW4SampleRotation@@XZ; FaceDetectionMFT::GetSampleRotation(void)
0x180018315  mov     [r13+3F4h], eax
0x18001831c  cmp     eax, [r13+3F0h]
0x180018323  jz      short loc_18001832D
0x180018325  mov     byte ptr [r13+2C8h], 1
0x18001832d  xor     r9d, r9d; struct tagRECT *
0x180018330  xor     r8d, r8d; struct tagRECT *
0x180018333  mov     rdx, [r14]; struct IMFSample *
0x180018336  mov     rcx, r13; this
0x180018339  call    ?ConvertSample@FaceDetectionMFT@@AEAAJPEAUIMFSample@@PEAUtagRECT@@1@Z; FaceDetectionMFT::ConvertSample(IMFSample *,tagRECT *,tagRECT *)
0x18001833e  mov     ebx, eax
0x180018340  test    eax, eax
0x180018342  jns     short loc_180018365
0x180018344  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001834b  jb      loc_1800184F7
0x180018351  mov     edx, 77h ; 'w'
0x180018356  jmp     loc_18001822A
0x18001835b  xor     ebx, ebx
0x18001835d  mov     r14d, ebx
0x180018360  jmp     loc_1800184FC
0x180018365  mov     rcx, r14
0x180018368  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001836d  lea     r14, [r13+1D0h]
0x180018374  mov     rcx, r14; lpCriticalSection
0x180018377  call    cs:__imp_EnterCriticalSection
0x18001837d  mov     eax, [r13+328h]
0x180018384  mov     [rbp+200h+var_260], eax
0x180018387  mov     r12d, [r13+32Ch]
0x18001838e  mov     eax, [r13+244h]
0x180018395  mov     [rbp+200h+var_258], eax
0x180018398  mov     eax, [r13+248h]
0x18001839f  mov     [rbp+200h+var_25C], eax
0x1800183a2  movss   xmm11, dword ptr [r13+23Ch]
0x1800183ab  mov     eax, [r13+3F4h]
0x1800183b2  mov     [rsp+300h+var_2A0], eax
0x1800183b6  mov     rbx, [r13+280h]
0x1800183bd  test    rbx, rbx
0x1800183c0  jz      short loc_1800183E7
0x1800183c2  mov     [rbp+200h+var_270], rbx
0x1800183c6  lea     rcx, [rbp+200h+var_270]
0x1800183ca  call    ?InternalAddRef@?$ComPtr@U?$IAsyncOperationWithProgressCompletedHandler@PEAVLowLightFusionResult@Core@Media@Windows@@N@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Media::Core::LowLightFusionResult *,double>>::InternalAddRef(void)
0x1800183cf  mov     [rbp+200h+var_270], 0
0x1800183d7  mov     rdi, rbx
0x1800183da  mov     [rbp+200h+var_1F0], rbx
0x1800183de  lea     rcx, [rbp+200h+var_270]
0x1800183e2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800183e7  mov     rbx, [r13+288h]
0x1800183ee  test    rbx, rbx
0x1800183f1  jz      short loc_18001841B
0x1800183f3  mov     rax, [rbx]
0x1800183f6  mov     rcx, rbx
0x1800183f9  mov     rax, [rax+8]
0x1800183fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018402  nop
0x180018403  mov     [rbp+200h+var_270], 0
0x18001840b  mov     r15, rbx
0x18001840e  mov     [rbp+200h+var_1F8], rbx
0x180018412  lea     rcx, [rbp+200h+var_270]
0x180018416  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001841b  mov     rbx, [r13+290h]
0x180018422  test    rbx, rbx
0x180018425  jz      short loc_18001844F
0x180018427  mov     rax, [rbx]
0x18001842a  mov     rcx, rbx
0x18001842d  mov     rax, [rax+8]
0x180018431  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018436  nop
0x180018437  mov     [rbp+200h+var_270], 0
0x18001843f  mov     rsi, rbx
0x180018442  mov     [rbp+200h+var_200], rbx
0x180018446  lea     rcx, [rbp+200h+var_270]
0x18001844a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001844f  lea     rdx, [r13+298h]
0x180018456  lea     rcx, [rbp+200h+var_220]
0x18001845a  call    ??4?$ComPtr@UIFaceTracker@FaceAnalysis@Media@Windows@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<Windows::Media::FaceAnalysis::IFaceTracker>::operator=(Microsoft::WRL::ComPtr<Windows::Media::FaceAnalysis::IFaceTracker> const &)
0x18001845f  lea     rdx, [r13+2A0h]
0x180018466  lea     rcx, [rbp+200h+var_208]
0x18001846a  call    ??4?$ComPtr@UIFaceTracker@FaceAnalysis@Media@Windows@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<Windows::Media::FaceAnalysis::IFaceTracker>::operator=(Microsoft::WRL::ComPtr<Windows::Media::FaceAnalysis::IFaceTracker> const &)
0x18001846f  lea     rdx, [r13+2A8h]
0x180018476  lea     rcx, [rbp+200h+var_210]
0x18001847a  call    ??4?$ComPtr@UIFaceTracker@FaceAnalysis@Media@Windows@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<Windows::Media::FaceAnalysis::IFaceTracker>::operator=(Microsoft::WRL::ComPtr<Windows::Media::FaceAnalysis::IFaceTracker> const &)
0x18001847f  lea     rdx, [r13+2B0h]
0x180018486  lea     rcx, [rbp+200h+var_218]
0x18001848a  call    ??4?$ComPtr@UIFaceTracker@FaceAnalysis@Media@Windows@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<Windows::Media::FaceAnalysis::IFaceTracker>::operator=(Microsoft::WRL::ComPtr<Windows::Media::FaceAnalysis::IFaceTracker> const &)
0x18001848f  mov     rax, [r13+4428h]
0x180018496  mov     [rsp+300h+var_288], rax
0x18001849b  lea     rdx, [r13+2F8h]
0x1800184a2  lea     rcx, [rbp+200h+var_190]
0x1800184a6  call    ??4AnalysisParameters@@QEAAAEAU0@AEBU0@@Z; AnalysisParameters::operator=(AnalysisParameters const &)
0x1800184ab  mov     rcx, r14; lpCriticalSection
0x1800184ae  call    cs:__imp_LeaveCriticalSection
0x1800184b4  mov     rcx, r13; this
0x1800184b7  call    ?EnableLongRunningWorkQueue@CCoreMFT@@IEAAJXZ; CCoreMFT::EnableLongRunningWorkQueue(void)
0x1800184bc  mov     ebx, eax
0x1800184be  xor     ecx, ecx
0x1800184c0  test    eax, eax
0x1800184c2  jns     loc_18001874B
0x1800184c8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800184cf  jb      short loc_1800184F2
0x1800184d1  lea     edx, [rcx+78h]
0x1800184d4  mov     [rsp+300h+var_2E0], eax
0x1800184d8  mov     r9, r13
0x1800184db  lea     r8, WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids
0x1800184e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800184e9  mov     rcx, [rcx+10h]
0x1800184ed  call    WPP_SF_qD
0x1800184f2  mov     r12d, [rsp+300h+var_2A0]
0x1800184f7  mov     r14, [rsp+300h+var_288]
0x1800184fc  mov     rcx, r13; this
0x1800184ff  call    ?DisableLongRunningWorkQueue@CCoreMFT@@IEAAJXZ; CCoreMFT::DisableLongRunningWorkQueue(void)
0x180018504  mov     rcx, r13; this
0x180018507  call    ?CancelDeadline@CCoreMFT@@IEAAJXZ; CCoreMFT::CancelDeadline(void)
0x18001850c  test    ebx, ebx
0x18001850e  jns     loc_1800185E4
0x180018514  cmp     cs:byte_180160805, 1
0x18001851b  jb      short loc_180018543
0x18001851d  mov     edx, 93h
0x180018522  mov     [rsp+300h+var_2E0], ebx
0x180018526  mov     r9, r13
0x180018529  lea     r8, WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids
0x180018530  mov     rcx, cs:WPP_GLOBAL_Control
0x180018537  mov     rcx, [rcx+0D8h]
0x18001853e  call    WPP_SF_qD
0x180018543  test    r14, r14
0x180018546  jz      loc_1800185E4
0x18001854c  xorps   xmm2, xmm2; double
0x18001854f  mov     edx, 4; unsigned int
0x180018554  mov     rcx, r14; this
0x180018557  call    ?AddData@CAggregatePhotographyTelemetry@@QEAAXKN@Z; CAggregatePhotographyTelemetry::AddData(ulong,double)
0x18001855c  mov     eax, cs:dword_18015F0D0
0x180018562  cmp     eax, 5
0x180018565  jbe     short loc_1800185E4
0x180018567  mov     rdx, 400000000000h
0x180018571  lea     rcx, dword_18015F0D0
0x180018578  call    _tlgKeywordOn
0x18001857d  test    al, al
0x18001857f  jz      short loc_1800185E4
0x180018581  mov     [rbp+200h+var_258], ebx
0x180018584  lea     rax, [r13+4438h]
0x18001858b  mov     [rbp+200h+var_270], rax
0x18001858f  mov     [rbp+200h+var_260], 1
0x180018596  lea     rax, aFacedetection; "FaceDetection"
0x18001859d  mov     [rbp+200h+var_278], rax
0x1800185a1  mov     [rsp+300h+var_290], 1000000h
0x1800185aa  lea     rax, [rbp+200h+var_258]
0x1800185ae  mov     [rsp+300h+var_2C0], rax
0x1800185b3  lea     rax, [rbp+200h+var_270]
0x1800185b7  mov     [rsp+300h+var_2C8], rax
0x1800185bc  lea     rax, [rbp+200h+var_260]
0x1800185c0  mov     [rsp+300h+var_2D0], rax
0x1800185c5  lea     rax, [rbp+200h+var_278]
0x1800185c9  mov     [rsp+300h+var_2D8], rax
0x1800185ce  lea     rax, [rsp+300h+var_290]
0x1800185d3  mov     qword ptr [rsp+300h+var_2E0], rax
0x1800185d8  lea     rdx, byte_180151009
0x1800185df  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByRef@$0BA@@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByRef@$0BA@@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x1800185e4  cmp     [rbp+200h+var_134], 0
0x1800185eb  jz      short loc_180018600
0x1800185ed  cmp     [rbp+200h+var_138], 2
0x1800185f4  jnz     short loc_180018600
0x1800185f6  cmp     r12d, 3
0x1800185fa  jnz     loc_1800186AD
0x180018600  test    r14, r14
0x180018603  jz      loc_1800186A4
0x180018609  mov     [rbp+200h+var_258], 0
0x180018610  call    cs:__imp_MFGetSystemTime
0x180018616  sub     rax, [rbp+200h+var_D0]
0x18001861d  xorps   xmm2, xmm2
0x180018620  cvtsi2sd xmm2, rax
0x180018625  divsd   xmm2, cs:__real@40c3880000000000; double
0x18001862d  mov     edx, 3; unsigned int
0x180018632  mov     rcx, r14; this
0x180018635  call    ?AddData@CAggregatePhotographyTelemetry@@QEAAXKN@Z; CAggregatePhotographyTelemetry::AddData(ulong,double)
0x18001863a  movzx   eax, [rbp+200h+var_134]
0x180018641  movd    xmm2, eax
0x180018645  cvtdq2pd xmm2, xmm2; double
  ... truncated ...
```
