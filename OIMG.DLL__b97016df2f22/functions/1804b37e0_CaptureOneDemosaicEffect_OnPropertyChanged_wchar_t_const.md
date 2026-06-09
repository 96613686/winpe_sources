# CaptureOneDemosaicEffect::OnPropertyChanged(wchar_t const *)

- ea: `0x1804b37e0`
- end: `0x1804b48e1`
- name: `?OnPropertyChanged@CaptureOneDemosaicEffect@@UEAAJPEB_W@Z`
- size: `4353`
- prototype: `__int64 __fastcall(CaptureOneDemosaicEffect *__hidden this, PCNZWCH lpString1)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x1801a2ffc`
- `0x1801a31b8`
- `0x18048c8c8`
- `0x1804b2a10`
- `0x1804b37e0`
- `0x1804c6944`
- `0x18056dce0`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x1804b38b6`
- `KERNEL32!CompareStringW` at `0x1804b39a8`
- `KERNEL32!CompareStringW` at `0x1804b3d2b`
- `KERNEL32!CompareStringW` at `0x1804b3e16`
- `KERNEL32!CompareStringW` at `0x1804b3e41`
- `KERNEL32!CompareStringW` at `0x1804b3e6c`
- `KERNEL32!CompareStringW` at `0x1804b3e97`
- `KERNEL32!CompareStringW` at `0x1804b3ec2`
- `KERNEL32!CompareStringW` at `0x1804b3eed`
- `KERNEL32!CompareStringW` at `0x1804b3f18`
- `KERNEL32!CompareStringW` at `0x1804b3f43`
- `KERNEL32!CompareStringW` at `0x1804b3f6e`
- `KERNEL32!CompareStringW` at `0x1804b3f99`
- `KERNEL32!CompareStringW` at `0x1804b3fc4`
- `KERNEL32!CompareStringW` at `0x1804b3ffa`
- `KERNEL32!CompareStringW` at `0x1804b418b`
- `KERNEL32!CompareStringW` at `0x1804b4336`
- `KERNEL32!CompareStringW` at `0x1804b440b`
- `KERNEL32!CompareStringW` at `0x1804b44e0`
- `KERNEL32!CompareStringW` at `0x1804b45b5`
- `KERNEL32!CompareStringW` at `0x1804b38b6`
- `KERNEL32!CompareStringW` at `0x1804b39a8`
- `KERNEL32!CompareStringW` at `0x1804b3d2b`
- `KERNEL32!CompareStringW` at `0x1804b3e16`
- `KERNEL32!CompareStringW` at `0x1804b3e41`
- `KERNEL32!CompareStringW` at `0x1804b3e6c`
- `KERNEL32!CompareStringW` at `0x1804b3e97`
- `KERNEL32!CompareStringW` at `0x1804b3ec2`
- `KERNEL32!CompareStringW` at `0x1804b3eed`
- `KERNEL32!CompareStringW` at `0x1804b3f18`
- `KERNEL32!CompareStringW` at `0x1804b3f43`
- `KERNEL32!CompareStringW` at `0x1804b3f6e`
- `KERNEL32!CompareStringW` at `0x1804b3f99`
- `KERNEL32!CompareStringW` at `0x1804b3fc4`
- `KERNEL32!CompareStringW` at `0x1804b3ffa`
- `KERNEL32!CompareStringW` at `0x1804b418b`
- `KERNEL32!CompareStringW` at `0x1804b4336`
- `KERNEL32!CompareStringW` at `0x1804b440b`
- `KERNEL32!CompareStringW` at `0x1804b44e0`
- `KERNEL32!CompareStringW` at `0x1804b45b5`
- `OLEAUT32!__imp_VariantInit` at `0x1804b3838`
- `OLEAUT32!__imp_VariantInit` at `0x1804b3838`
- `OLEAUT32!__imp_VariantClear` at `0x1804b3cc0`
- `OLEAUT32!__imp_VariantClear` at `0x1804b468d`
- `OLEAUT32!__imp_VariantClear` at `0x1804b3cc0`
- `OLEAUT32!__imp_VariantClear` at `0x1804b468d`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1804b3aa4`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1804b3aa4`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1804b3cd6`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1804b3d04`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1804b3cd6`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1804b3d04`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1804b3b37`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1804b3bbe`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1804b3b37`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1804b3bbe`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1804b3b03`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1804b3b8e`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1804b3b03`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1804b3b8e`
- `OLEAUT32!__imp_SafeArrayLock` at `0x1804b3ac2`
- `OLEAUT32!__imp_SafeArrayLock` at `0x1804b3ac2`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x1804b3cc9`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x1804b3cee`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x1804b3cc9`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x1804b3cee`

## string_xrefs

- `0x1804b3f82`: `NoiseReductionAmount_Default`
- `0x1804b40eb`: `DemosaiGaussFilterCache`
- `0x1804b403b`: `DemosaicSigmaFilterCache`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CaptureOneDemosaicEffect::OnPropertyChanged(CaptureOneDemosaicEffect *this, PCNZWCH lpString1)
{
  int v4; // eax
  int v5; // eax
  int v6; // eax
  __int64 v7; // rax
  int v8; // eax
  int v9; // eax
  __int64 v10; // rax
  int v11; // eax
  SAFEARRAY *v12; // rax
  SAFEARRAY *v13; // rbx
  HRESULT v14; // eax
  int v15; // r14d
  HRESULT LBound; // eax
  __int64 cElements; // r15
  HRESULT UBound; // eax
  int v19; // r14d
  HRESULT v20; // eax
  HRESULT v21; // eax
  int v22; // eax
  __int64 v23; // rax
  int v24; // eax
  int v25; // eax
  __int64 v26; // rax
  int v27; // eax
  BOOL v28; // ebx
  int v29; // eax
  int v30; // eax
  int v31; // eax
  int v32; // eax
  int v33; // eax
  __int64 v34; // rax
  int v35; // eax
  int v36; // eax
  __int64 v37; // rax
  int v38; // eax
  int v39; // eax
  int v40; // eax
  int v41; // eax
  int v42; // eax
  int v43; // eax
  int v44; // eax
  int v45; // eax
  int v46; // eax
  __int64 result; // rax
  VARIANTARG pvarg; // [rsp+30h] [rbp-B8h] BYREF
  VARIANTARG v49; // [rsp+50h] [rbp-98h] BYREF
  VARIANTARG v50; // [rsp+70h] [rbp-78h] BYREF
  ULONG v51; // [rsp+90h] [rbp-58h] BYREF
  SAFEARRAY *v52; // [rsp+98h] [rbp-50h]
  _DWORD v53[18]; // [rsp+A0h] [rbp-48h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+F8h] [rbp+10h] BYREF
  LONG plUbound; // [rsp+100h] [rbp+18h] BYREF
  SAFEARRAY *psa; // [rsp+108h] [rbp+20h] BYREF

  try
  {
    if ( !lpString1 )
      ATL::BaseAtlThrow(-2147467261);
    v4 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 16) + 272LL))(*((_QWORD *)this + 16));
    if ( v4 < 0 )
      ATL::BaseAtlThrow(v4);
    memset(&pvarg, 0, sizeof(pvarg));
    VariantInit(&pvarg);
    v5 = (*(__int64 (__fastcall **)(_QWORD, PCNZWCH, VARIANTARG *))(**((_QWORD **)this + 16) + 96LL))(
           *((_QWORD *)this + 16),
           lpString1,
           &pvarg);
    if ( v5 == -2147024882 || v5 == -2045378032 || v5 == -2045312765 || v5 == -2045247216 )
      ATL::BaseAtlThrow(v5);
    if ( v5 < 0 )
      ATL::BaseAtlThrow(v5);
    if ( CompareStringW(0x7Fu, 1u, lpString1, -1, L"CameraCropSize", -1) == 2 )
    {
      rgsabound = 0;
      v6 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, SAFEARRAYBOUND *))(**((_QWORD **)this + 18) + 152LL))(
             *((_QWORD *)this + 18),
             L"CaptureOneEstimateGEffect",
             &rgsabound);
      if ( v6 < 0 )
        ATL::BaseAtlThrow(v6);
      if ( !*(_QWORD *)&rgsabound )
        ATL::BaseAtlThrow(-2045247222);
      (*(void (__fastcall **)(SAFEARRAYBOUND))(**(_QWORD **)&rgsabound + 16LL))(rgsabound);
      v7 = **(_QWORD **)&rgsabound;
      v50 = pvarg;
      v8 = (*(__int64 (__fastcall **)(SAFEARRAYBOUND, PCNZWCH, VARIANTARG *))(v7 + 104))(rgsabound, lpString1, &v50);
      if ( v8 == -2147024882 || v8 == -2045378032 || v8 == -2045312765 || v8 == -2045247216 )
        ATL::BaseAtlThrow(v8);
      if ( v8 < 0 )
        ATL::BaseAtlThrow(v8);
    }
    else if ( CompareStringW(0x7Fu, 1u, lpString1, -1, L"CameraCropOrigin", -1) == 2 )
    {
      rgsabound = 0;
      v9 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, SAFEARRAYBOUND *))(**((_QWORD **)this + 18) + 152LL))(
             *((_QWORD *)this + 18),
             L"CaptureOneEstimateGEffect",
             &rgsabound);
      if ( v9 < 0 )
        ATL::BaseAtlThrow(v9);
      if ( !*(_QWORD *)&rgsabound )
        ATL::BaseAtlThrow(-2045247222);
      (*(void (__fastcall **)(SAFEARRAYBOUND))(**(_QWORD **)&rgsabound + 16LL))(rgsabound);
      v10 = **(_QWORD **)&rgsabound;
      v49 = pvarg;
      v11 = (*(__int64 (__fastcall **)(SAFEARRAYBOUND, PCNZWCH, VARIANTARG *))(v10 + 104))(rgsabound, lpString1, &v49);
      if ( v11 == -2147024882 || v11 == -2045378032 || v11 == -2045312765 || v11 == -2045247216 )
        ATL::BaseAtlThrow(v11);
      if ( v11 < 0 )
        ATL::BaseAtlThrow(v11);
      ATL::CComSafeArray<int,3>::CComSafeArray<int,3>(&psa, pvarg.parray);
      rgsabound = (SAFEARRAYBOUND)2LL;
      v12 = SafeArrayCreate(3u, 1u, &rgsabound);
      v13 = v12;
      v52 = v12;
      if ( v12 )
        v14 = SafeArrayLock(v12);
      else
        v14 = -2147024882;
      if ( v14 < 0 )
        ATL::BaseAtlThrow(v14);
      v15 = *(_DWORD *)ATL::CComSafeArray<float,4>::GetAt(&psa, 0) & 1;
      if ( !v13 )
        ATL::BaseAtlThrow(-2147467259);
      rgsabound.cElements = 0;
      LBound = SafeArrayGetLBound(v13, 1u, (LONG *)&rgsabound);
      if ( LBound < 0 )
        ATL::BaseAtlThrow(LBound);
      cElements = (int)rgsabound.cElements;
      if ( (int)rgsabound.cElements > 0 )
        goto LABEL_169;
      rgsabound.cElements = 0;
      UBound = SafeArrayGetUBound(v13, 1u, (LONG *)&rgsabound);
      if ( UBound < 0 )
        ATL::BaseAtlThrow(UBound);
      if ( (rgsabound.cElements & 0x80000000) != 0 )
LABEL_169:
        ATL::BaseAtlThrow(-2147024809);
      *((_DWORD *)v13->pvData - cElements) = v15;
      v19 = *(_DWORD *)ATL::CComSafeArray<float,4>::GetAt(&psa, 1) & 1;
      rgsabound.cElements = 0;
      v20 = SafeArrayGetLBound(v13, 1u, (LONG *)&rgsabound);
      if ( v20 < 0 )
        ATL::BaseAtlThrow(v20);
      if ( (int)rgsabound.cElements > 1 )
        goto LABEL_168;
      plUbound = 0;
      v21 = SafeArrayGetUBound(v13, 1u, &plUbound);
      if ( v21 < 0 )
        ATL::BaseAtlThrow(v21);
      if ( plUbound < 1 )
LABEL_168:
        ATL::BaseAtlThrow(-2147024809);
      *((_DWORD *)v13->pvData + 1 - rgsabound.cElements) = v19;
      ATL::CComVariant::CComVariant(&v50.vt, v13);
      rgsabound = 0;
      v22 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, SAFEARRAYBOUND *))(**((_QWORD **)this + 18) + 152LL))(
              *((_QWORD *)this + 18),
              L"CaptureOneEstimateRBEffect",
              &rgsabound);
      if ( v22 < 0 )
        ATL::BaseAtlThrow(v22);
      if ( !*(_QWORD *)&rgsabound )
        ATL::BaseAtlThrow(-2045247222);
      (*(void (__fastcall **)(SAFEARRAYBOUND))(**(_QWORD **)&rgsabound + 16LL))(rgsabound);
      v23 = **(_QWORD **)&rgsabound;
      v49 = v50;
      v24 = (*(__int64 (__fastcall **)(SAFEARRAYBOUND, const WCHAR *, VARIANTARG *))(v23 + 104))(
              rgsabound,
              L"CFALeftTopOffset",
              &v49);
      if ( v24 == -2147024882 || v24 == -2045378032 || v24 == -2045312765 || v24 == -2045247216 )
        ATL::BaseAtlThrow(v24);
      if ( v24 < 0 )
        ATL::BaseAtlThrow(v24);
      VariantClear(&v50);
      if ( SafeArrayUnlock(v13) >= 0 )
        SafeArrayDestroy(v13);
      if ( psa && SafeArrayUnlock(psa) >= 0 )
        SafeArrayDestroy(psa);
    }
    else
    {
      if ( CompareStringW(0x7Fu, 1u, lpString1, -1, L"WhiteBalance", -1) == 2 )
      {
        rgsabound = 0;
        v25 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, SAFEARRAYBOUND *))(**((_QWORD **)this + 18) + 152LL))(
                *((_QWORD *)this + 18),
                L"CaptureOneEstimateRBEffect",
                &rgsabound);
        if ( v25 < 0 )
          ATL::BaseAtlThrow(v25);
        if ( !*(_QWORD *)&rgsabound )
          ATL::BaseAtlThrow(-2045247222);
        (*(void (__fastcall **)(SAFEARRAYBOUND))(**(_QWORD **)&rgsabound + 16LL))(rgsabound);
        v26 = **(_QWORD **)&rgsabound;
        v49 = pvarg;
        v27 = (*(__int64 (__fastcall **)(SAFEARRAYBOUND, PCNZWCH, VARIANTARG *))(v26 + 104))(rgsabound, lpString1, &v49);
        if ( v27 == -2147024882 || v27 == -2045378032 || v27 == -2045312765 || v27 == -2045247216 )
          ATL::BaseAtlThrow(v27);
        if ( v27 < 0 )
          ATL::BaseAtlThrow(v27);
      }
      else if ( CompareStringW(0x7Fu, 1u, lpString1, -1, L"ExposureNoiseCoefficient1", -1) != 2
             && CompareStringW(0x7Fu, 1u, lpString1, -1, L"ExposureNoiseCoefficient2", -1) != 2
             && CompareStringW(0x7Fu, 1u, lpString1, -1, L"ISO", -1) != 2
             && CompareStringW(0x7Fu, 1u, lpString1, -1, L"OutputSceneAdaptation", -1) != 2 )
      {
        if ( CompareStringW(0x7Fu, 1u, lpString1, -1, L"LumaNoiseReduction", -1) == 2
          || CompareStringW(0x7Fu, 1u, lpString1, -1, L"ExposureTimeSeconds", -1) == 2
          || CompareStringW(0x7Fu, 1u, lpString1, -1, L"NoiseDetailMapAttenuation", -1) == 2
          || CompareStringW(0x7Fu, 1u, lpString1, -1, L"CNRThreshold", -1) == 2
          || CompareStringW(0x7Fu, 1u, lpString1, -1, L"NoiseGreenRangeCoefficient", -1) == 2
          || CompareStringW(0x7Fu, 1u, lpString1, -1, L"NoiseReductionAmount_Default", -1) == 2 )
        {
          if ( pvarg.dblVal < 0.0 )
            ATL::BaseAtlThrow(-2147024809);
        }
        else
        {
          if ( CompareStringW(0x7Fu, 1u, lpString1, -1, L"ExposureNoiseTrend", -1) != 2 )
          {
            if ( CompareStringW(0x7Fu, 1u, lpString1, -1, L"EnableCaching", -1) == 2 )
            {
              if ( pvarg.vt != 11 )
                ATL::BaseAtlThrow(-2147024809);
              v28 = pvarg.iVal != 0;
              rgsabound = 0;
              v29 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, SAFEARRAYBOUND *))(**((_QWORD **)this + 18)
                                                                                         + 152LL))(
                      *((_QWORD *)this + 18),
                      L"DemosaicSigmaFilterCache",
                      &rgsabound);
              if ( v29 < 0 )
                ATL::BaseAtlThrow(v29);
              if ( !*(_QWORD *)&rgsabound )
                ATL::BaseAtlThrow(-2045247222);
              (*(void (__fastcall **)(SAFEARRAYBOUND))(**(_QWORD **)&rgsabound + 16LL))(rgsabound);
              v30 = (*(__int64 (__fastcall **)(SAFEARRAYBOUND, BOOL))(**(_QWORD **)&rgsabound + 192LL))(rgsabound, v28);
              if ( v30 == -2147024882 || v30 == -2045378032 || v30 == -2045312765 || v30 == -2045247216 )
                ATL::BaseAtlThrow(v30);
              if ( v30 < 0 )
                ATL::BaseAtlThrow(v30);
              rgsabound = 0;
              v31 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, SAFEARRAYBOUND *))(**((_QWORD **)this + 18)
                                                                                         + 152LL))(
                      *((_QWORD *)this + 18),
                      L"DemosaiGaussFilterCache",
                      &rgsabound);
              if ( v31 < 0 )
                ATL::BaseAtlThrow(v31);
              if ( !*(_QWORD *)&rgsabound )
                ATL::BaseAtlThrow(-2045247222);
              (*(void (__fastcall **)(SAFEARRAYBOUND))(**(_QWORD **)&rgsabound + 16LL))(rgsabound);
              v32 = (*(__int64 (__fastcall **)(SAFEARRAYBOUND, BOOL))(**(_QWORD **)&rgsabound + 192LL))(rgsabound, v28);
              if ( v32 == -2147024882 || v32 == -2045378032 || v32 == -2045312765 || v32 == -2045247216 )
                ATL::BaseAtlThrow(v32);
              if ( v32 < 0 )
                ATL::BaseAtlThrow(v32);
            }
            else if ( CompareStringW(0x7Fu, 1u, lpString1, -1, L"ForceDisableSSE", -1) == 2 )
            {
              rgsabound = 0;
              v33 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, SAFEARRAYBOUND *))(**((_QWORD **)this + 18)
                                                                                         + 152LL))(
                      *((_QWORD *)this + 18),
                      L"CaptureOneEstimateGEffect",
                      &rgsabound);
              if ( v33 < 0 )
                ATL::BaseAtlThrow(v33);
              if ( !*(_QWORD *)&rgsabound )
                ATL::BaseAtlThrow(-2045247222);
              (*(void (__fastcall **)(SAFEARRAYBOUND))(**(_QWORD **)&rgsabound + 16LL))(rgsabound);
              v34 = **(_QWORD **)&rgsabound;
              v49 = pvarg;
              v35 = (*(__int64 (__fastcall **)(SAFEARRAYBOUND, PCNZWCH, VARIANTARG *))(v34 + 104))(
                      rgsabound,
                      lpString1,
                      &v49);
              if ( v35 == -2147024882 || v35 == -2045378032 || v35 == -2045312765 || v35 == -2045247216 )
                ATL::BaseAtlThrow(v35);
              if ( v35 < 0 )
                ATL::BaseAtlThrow(v35);
              rgsabound = 0;
              v36 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, SAFEARRAYBOUND *))(**((_QWORD **)this + 18)
                                                                                         + 152LL))(
                      *((_QWORD *)this + 18),
                      L"CaptureOneEstimateRBEffect",
                      &rgsabound);
              if ( v36 < 0 )
                ATL::BaseAtlThrow(v36);
              if ( !*(_QWORD *)&rgsabound )
                ATL::BaseAtlThrow(-2045247222);
              (*(void (__fastcall **)(SAFEARRAYBOUND))(**(_QWORD **)&rgsabound + 16LL))(rgsabound);
              v37 = **(_QWORD **)&rgsabound;
              v49 = pvarg;
              v38 = (*(__int64 (__fastcall **)(SAFEARRAYBOUND, PCNZWCH, VARIANTARG *))(v37 + 104))(
                      rgsabound,
                      lpString1,
                      &v49);
              if ( v38 == -2147024882 || v38 == -2045378032 || v38 == -2045312765 || v38 == -2045247216 )
                ATL::BaseAtlThrow(v38);
              if ( v38 < 0 )
                ATL::BaseAtlThrow(v38);
            }
            else if ( CompareStringW(0x7Fu, 1u, lpString1, -1, L"IsEnabledEstimateG", -1) == 2 )
            {
              rgsabound = 0;
              v39 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, SAFEARRAYBOUND *))(**((_QWORD **)this + 18)
                                                                                         + 152LL))(
                      *((_QWORD *)this + 18),
                      L"CaptureOneEstimateGEffect",
                      &rgsabound);
              if ( v39 < 0 )
                ATL::BaseAtlThrow(v39);
              if ( !*(_QWORD *)&rgsabound )
                ATL::BaseAtlThrow(-2045247222);
              (*(void (__fastcall **)(SAFEARRAYBOUND))(**(_QWORD **)&rgsabound + 16LL))(rgsabound);
              v40 = (*(__int64 (__fastcall **)(SAFEARRAYBOUND, _QWORD))(**(_QWORD **)&rgsabound + 192LL))(
                      rgsabound,
                      (unsigned int)pvarg.iVal);
              if ( v40 == -2147024882 || v40 == -2045378032 || v40 == -2045312765 || v40 == -2045247216 )
                ATL::BaseAtlThrow(v40);
              if ( v40 < 0 )
                ATL::BaseAtlThrow(v40);
            }
            else if ( CompareStringW(0x7Fu, 1u, lpString1, -1, L"IsEnabledEstimateRB", -1) == 2 )
            {
              rgsabound = 0;
              v41 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, SAFEARRAYBOUND *))(**((_QWORD **)this + 18)
                                                                                         + 152LL))(
                      *((_QWORD *)this + 18),
                      L"CaptureOneEstimateRBEffect",
                      &rgsabound);
              if ( v41 < 0 )
                ATL::BaseAtlThrow(v41);
              if ( !*(_QWORD *)&rgsabound )
                ATL::BaseAtlThrow(-2045247222);
              (*(void (__fastcall **)(SAFEARRAYBOUND))(**(_QWORD **)&rgsabound + 16LL))(rgsabound);
              v42 = (*(__int64 (__fastcall **)(SAFEARRAYBOUND, _QWORD))(**(_QWORD **)&rgsabound + 192LL))(
                      rgsabound,
                      (unsigned int)pvarg.iVal);
              if ( v42 == -2147024882 || v42 == -2045378032 || v42 == -2045312765 || v42 == -2045247216 )
                ATL::BaseAtlThrow(v42);
              if ( v42 < 0 )
                ATL::BaseAtlThrow(v42);
            }
            else if ( CompareStringW(0x7Fu, 1u, lpString1, -1, L"IsEnabledNoiseSuppressG", -1) == 2 )
            {
              rgsabound = 0;
              v43 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, SAFEARRAYBOUND *))(**((_QWORD **)this + 18)
                                                                                         + 152LL))(
                      *((_QWORD *)this + 18),
                      L"CaptureOneGDenoiseEffect",
                      &rgsabound);
              if ( v43 < 0 )
                ATL::BaseAtlThrow(v43);
              if ( !*(_QWORD *)&rgsabound )
                ATL::BaseAtlThrow(-2045247222);
              (*(void (__fastcall **)(SAFEARRAYBOUND))(**(_QWORD **)&rgsabound + 16LL))(rgsabound);
              v44 = (*(__int64 (__fastcall **)(SAFEARRAYBOUND, _QWORD))(**(_QWORD **)&rgsabound + 192LL))(
                      rgsabound,
                      (unsigned int)pvarg.iVal);
              if ( v44 == -2147024882 || v44 == -2045378032 || v44 == -2045312765 || v44 == -2045247216 )
                ATL::BaseAtlThrow(v44);
              if ( v44 < 0 )
                ATL::BaseAtlThrow(v44);
            }
            else if ( CompareStringW(0x7Fu, 1u, lpString1, -1, L"IsEnabledNoiseSuppressRB", -1) == 2 )
            {
              rgsabound = 0;
              v45 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, SAFEARRAYBOUND *))(**((_QWORD **)this + 18)
                                                                                         + 152LL))(
                      *((_QWORD *)this + 18),
                      L"CaptureOneRBDenoiseEffect",
                      &rgsabound);
              if ( v45 < 0 )
                ATL::BaseAtlThrow(v45);
              if ( !*(_QWORD *)&rgsabound )
                ATL::BaseAtlThrow(-2045247222);
              (*(void (__fastcall **)(SAFEARRAYBOUND))(**(_QWORD **)&rgsabound + 16LL))(rgsabound);
              v46 = (*(__int64 (__fastcall **)(SAFEARRAYBOUND, _QWORD))(**(_QWORD **)&rgsabound + 192LL))(
                      rgsabound,
                      (unsigned int)pvarg.iVal);
              if ( v46 == -2147024882 || v46 == -2045378032 || v46 == -2045312765 || v46 == -2045247216 )
                ATL::BaseAtlThrow(v46);
              if ( v46 < 0 )
                ATL::BaseAtlThrow(v46);
            }
            goto LABEL_144;
          }
          if ( pvarg.lVal > 1u )
            ATL::BaseAtlThrow(-2147024809);
        }
      }
      CaptureOneDemosaicEffect::ConvertAndSetInternalParameters(this);
    }
LABEL_144:
    VariantClear(&pvarg);
    result = 0;
  }
  catch ( Base::Exception v53 )
  {
    rgsabound.cElements = v53[2];
    goto LABEL_145;
  }
  catch ( long v51 )
  {
    rgsabound.cElements = v51;
LABEL_145:
    result = rgsabound.cElements;
    if ( LOWORD(rgsabound.cElements) == 534 )
      return 2249588993LL;
  }
  return result;
}

```

## disassembly

```asm
0x1804b37e0  push    rbx
0x1804b37e2  push    rsi
0x1804b37e3  push    rdi
0x1804b37e4  push    r12
0x1804b37e6  push    r13
0x1804b37e8  push    r14
0x1804b37ea  push    r15
0x1804b37ec  sub     rsp, 0B0h
0x1804b37f3  mov     rbx, rdx
0x1804b37f6  mov     rsi, rcx
0x1804b37f9  xor     r12d, r12d
0x1804b37fc  test    rdx, rdx
0x1804b37ff  jz      loc_1804B46BD
0x1804b3805  mov     rcx, [rcx+80h]
0x1804b380c  mov     rax, [rcx]
0x1804b380f  mov     rax, [rax+110h]
0x1804b3816  call    cs:__guard_dispatch_icall_fptr
0x1804b381c  test    eax, eax
0x1804b381e  js      loc_1804B46C7
0x1804b3824  xorps   xmm0, xmm0
0x1804b3827  xor     eax, eax
0x1804b3829  movups  xmmword ptr [rsp+0E8h+pvarg], xmm0
0x1804b382e  mov     qword ptr [rsp+0E8h+pvarg+10h], rax
0x1804b3833  lea     rcx, [rsp+0E8h+pvarg]; pvarg
0x1804b3838  call    cs:__imp_VariantInit
0x1804b383e  mov     rcx, [rsi+80h]
0x1804b3845  mov     rax, [rcx]
0x1804b3848  lea     r8, [rsp+0E8h+pvarg]
0x1804b384d  mov     rdx, rbx
0x1804b3850  mov     rax, [rax+60h]
0x1804b3854  call    cs:__guard_dispatch_icall_fptr
0x1804b385a  cmp     eax, 8007000Eh
0x1804b385f  jz      loc_1804B48D1
0x1804b3865  cmp     eax, 86160210h
0x1804b386a  jz      loc_1804B48D1
0x1804b3870  cmp     eax, 86170103h
0x1804b3875  jz      loc_1804B48D1
0x1804b387b  cmp     eax, 86180110h
0x1804b3880  jz      loc_1804B48D1
0x1804b3886  test    eax, eax
0x1804b3888  js      loc_1804B46E1
0x1804b388e  or      r14d, 0FFFFFFFFh
0x1804b3892  mov     [rsp+0E8h+cchCount2], r14d; cchCount2
0x1804b3897  lea     rax, aCameracropsize; "CameraCropSize"
0x1804b389e  mov     [rsp+0E8h+lpString2], rax; lpString2
0x1804b38a3  mov     r9d, r14d; cchCount1
0x1804b38a6  mov     r8, rbx; lpString1
0x1804b38a9  lea     edi, [r14+2]
0x1804b38ad  mov     edx, edi; dwCmpFlags
0x1804b38af  lea     r15d, [rdi+7Eh]
0x1804b38b3  mov     ecx, r15d; Locale
0x1804b38b6  call    cs:__imp_CompareStringW
0x1804b38bc  lea     r13d, [r14+3]
0x1804b38c0  cmp     eax, r13d
0x1804b38c3  jnz     loc_1804B398C
0x1804b38c9  mov     qword ptr [rsp+0E8h+rgsabound.cElements], r12
0x1804b38d1  mov     rcx, [rsi+90h]
0x1804b38d8  mov     rax, [rcx]
0x1804b38db  lea     r8, [rsp+0E8h+rgsabound]
0x1804b38e3  lea     rdx, aCaptureoneesti; "CaptureOneEstimateGEffect"
0x1804b38ea  mov     rax, [rax+98h]
0x1804b38f1  call    cs:__guard_dispatch_icall_fptr
0x1804b38f7  test    eax, eax
0x1804b38f9  js      loc_1804B46E8
0x1804b38ff  mov     rcx, qword ptr [rsp+0E8h+rgsabound.cElements]
0x1804b3907  test    rcx, rcx
0x1804b390a  jz      loc_1804B46EF
0x1804b3910  mov     rax, [rcx]
0x1804b3913  mov     rax, [rax+10h]
0x1804b3917  call    cs:__guard_dispatch_icall_fptr
0x1804b391d  mov     rcx, qword ptr [rsp+0E8h+rgsabound.cElements]
0x1804b3925  mov     rax, [rcx]
0x1804b3928  movups  xmm0, xmmword ptr [rsp+0E8h+pvarg]
0x1804b392d  movaps  xmmword ptr [rsp+0E8h+var_78], xmm0
0x1804b3932  movsd   xmm1, qword ptr [rsp+0E8h+pvarg+10h]
0x1804b3938  movsd   qword ptr [rsp+0E8h+var_78+10h], xmm1
0x1804b3941  lea     r8, [rsp+0E8h+var_78]
0x1804b3946  mov     rdx, rbx
0x1804b3949  mov     rax, [rax+68h]
0x1804b394d  call    cs:__guard_dispatch_icall_fptr
0x1804b3953  cmp     eax, 8007000Eh
0x1804b3958  jz      loc_1804B4700
0x1804b395e  cmp     eax, 86160210h
0x1804b3963  jz      loc_1804B4700
0x1804b3969  cmp     eax, 86170103h
0x1804b396e  jz      loc_1804B4700
0x1804b3974  cmp     eax, 86180110h
0x1804b3979  jz      loc_1804B4700
0x1804b397f  test    eax, eax
0x1804b3981  js      loc_1804B46F9
0x1804b3987  jmp     loc_1804B4688
0x1804b398c  mov     [rsp+0E8h+cchCount2], r14d; cchCount2
0x1804b3991  lea     rax, aCameracroporig; "CameraCropOrigin"
0x1804b3998  mov     [rsp+0E8h+lpString2], rax; lpString2
0x1804b399d  mov     r9d, r14d; cchCount1
0x1804b39a0  mov     r8, rbx; lpString1
0x1804b39a3  mov     edx, edi; dwCmpFlags
0x1804b39a5  mov     ecx, r15d; Locale
0x1804b39a8  call    cs:__imp_CompareStringW
0x1804b39ae  cmp     eax, r13d
0x1804b39b1  jnz     loc_1804B3D0F
0x1804b39b7  mov     qword ptr [rsp+0E8h+rgsabound.cElements], r12
0x1804b39bf  mov     rcx, [rsi+90h]
0x1804b39c6  mov     rax, [rcx]
0x1804b39c9  lea     r8, [rsp+0E8h+rgsabound]
0x1804b39d1  lea     rdx, aCaptureoneesti; "CaptureOneEstimateGEffect"
0x1804b39d8  mov     rax, [rax+98h]
0x1804b39df  call    cs:__guard_dispatch_icall_fptr
0x1804b39e5  test    eax, eax
0x1804b39e7  js      loc_1804B4707
0x1804b39ed  mov     rcx, qword ptr [rsp+0E8h+rgsabound.cElements]
0x1804b39f5  test    rcx, rcx
0x1804b39f8  jz      loc_1804B470E
0x1804b39fe  mov     rax, [rcx]
0x1804b3a01  mov     rax, [rax+10h]
0x1804b3a05  call    cs:__guard_dispatch_icall_fptr
0x1804b3a0b  mov     rcx, qword ptr [rsp+0E8h+rgsabound.cElements]
0x1804b3a13  mov     rax, [rcx]
0x1804b3a16  movups  xmm0, xmmword ptr [rsp+0E8h+pvarg]
0x1804b3a1b  movaps  [rsp+0E8h+var_98], xmm0
0x1804b3a20  movsd   xmm1, qword ptr [rsp+0E8h+pvarg+10h]
0x1804b3a26  movsd   [rsp+0E8h+var_88], xmm1
0x1804b3a2c  lea     r8, [rsp+0E8h+var_98]
0x1804b3a31  mov     rdx, rbx
0x1804b3a34  mov     rax, [rax+68h]
0x1804b3a38  call    cs:__guard_dispatch_icall_fptr
0x1804b3a3e  mov     r14d, 8007000Eh
0x1804b3a44  cmp     eax, r14d
0x1804b3a47  jz      loc_1804B4795
0x1804b3a4d  cmp     eax, 86160210h
0x1804b3a52  jz      loc_1804B4795
0x1804b3a58  cmp     eax, 86170103h
0x1804b3a5d  jz      loc_1804B4795
0x1804b3a63  cmp     eax, 86180110h
0x1804b3a68  jz      loc_1804B4795
0x1804b3a6e  test    eax, eax
0x1804b3a70  js      loc_1804B4718
0x1804b3a76  mov     rdx, qword ptr [rsp+0E8h+pvarg+8]; psa
0x1804b3a7b  lea     rcx, [rsp+0E8h+psa]; ppsaOut
0x1804b3a83  call    ??0?$CComSafeArray@H$02@ATL@@QEAA@PEBUtagSAFEARRAY@@@Z; ATL::CComSafeArray<int,3>::CComSafeArray<int,3>(tagSAFEARRAY const *)
0x1804b3a88  nop
0x1804b3a89  mov     qword ptr [rsp+0E8h+rgsabound.cElements], 2
0x1804b3a95  mov     ecx, 3; vt
0x1804b3a9a  lea     r8, [rsp+0E8h+rgsabound]; rgsabound
0x1804b3aa2  mov     edx, edi; cDims
0x1804b3aa4  call    cs:__imp_SafeArrayCreate
0x1804b3aaa  mov     rbx, rax
0x1804b3aad  mov     [rsp+0E8h+var_50], rax
0x1804b3ab5  test    rax, rax
0x1804b3ab8  jnz     short loc_1804B3ABF
0x1804b3aba  mov     eax, r14d
0x1804b3abd  jmp     short loc_1804B3AC8
0x1804b3abf  mov     rcx, rbx; psa
0x1804b3ac2  call    cs:__imp_SafeArrayLock
0x1804b3ac8  test    eax, eax
0x1804b3aca  js      loc_1804B4723
0x1804b3ad0  xor     edx, edx
0x1804b3ad2  lea     rcx, [rsp+0E8h+psa]
0x1804b3ada  call    ?GetAt@?$CComSafeArray@M$03@ATL@@QEAAAEAMJ@Z; ATL::CComSafeArray<float,4>::GetAt(long)
0x1804b3adf  mov     r14d, [rax]
0x1804b3ae2  and     r14d, edi
0x1804b3ae5  test    rbx, rbx
0x1804b3ae8  jz      loc_1804B472E
0x1804b3aee  mov     [rsp+0E8h+rgsabound.cElements], r12d
0x1804b3af6  lea     r8, [rsp+0E8h+rgsabound]; plLbound
0x1804b3afe  mov     edx, edi; nDim
0x1804b3b00  mov     rcx, rbx; psa
0x1804b3b03  call    cs:__imp_SafeArrayGetLBound
0x1804b3b09  test    eax, eax
0x1804b3b0b  js      loc_1804B4738
0x1804b3b11  movsxd  r15, [rsp+0E8h+rgsabound.cElements]
0x1804b3b19  test    r15d, r15d
0x1804b3b1c  jg      loc_1804B4787
0x1804b3b22  mov     [rsp+0E8h+rgsabound.cElements], r12d
0x1804b3b2a  lea     r8, [rsp+0E8h+rgsabound]; plUbound
0x1804b3b32  mov     edx, edi; nDim
0x1804b3b34  mov     rcx, rbx; psa
0x1804b3b37  call    cs:__imp_SafeArrayGetUBound
0x1804b3b3d  test    eax, eax
0x1804b3b3f  js      loc_1804B473F
0x1804b3b45  cmp     [rsp+0E8h+rgsabound.cElements], r12d
0x1804b3b4d  jl      loc_1804B4787
0x1804b3b53  mov     rcx, r15
0x1804b3b56  shl     rcx, 2
0x1804b3b5a  mov     rax, [rbx+10h]
0x1804b3b5e  sub     rax, rcx
0x1804b3b61  mov     [rax], r14d
0x1804b3b64  mov     edx, edi
0x1804b3b66  lea     rcx, [rsp+0E8h+psa]
0x1804b3b6e  call    ?GetAt@?$CComSafeArray@M$03@ATL@@QEAAAEAMJ@Z; ATL::CComSafeArray<float,4>::GetAt(long)
0x1804b3b73  mov     r14d, [rax]
0x1804b3b76  and     r14d, edi
0x1804b3b79  mov     [rsp+0E8h+rgsabound.cElements], r12d
0x1804b3b81  lea     r8, [rsp+0E8h+rgsabound]; plLbound
0x1804b3b89  mov     edx, edi; nDim
0x1804b3b8b  mov     rcx, rbx; psa
0x1804b3b8e  call    cs:__imp_SafeArrayGetLBound
0x1804b3b94  test    eax, eax
0x1804b3b96  js      loc_1804B4746
0x1804b3b9c  cmp     [rsp+0E8h+rgsabound.cElements], edi
0x1804b3ba3  jg      loc_1804B477D
0x1804b3ba9  mov     [rsp+0E8h+plUbound], r12d
0x1804b3bb1  lea     r8, [rsp+0E8h+plUbound]; plUbound
0x1804b3bb9  mov     edx, edi; nDim
0x1804b3bbb  mov     rcx, rbx; psa
0x1804b3bbe  call    cs:__imp_SafeArrayGetUBound
0x1804b3bc4  test    eax, eax
0x1804b3bc6  js      loc_1804B474D
0x1804b3bcc  cmp     [rsp+0E8h+plUbound], edi
0x1804b3bd3  jl      loc_1804B477D
0x1804b3bd9  sub     edi, [rsp+0E8h+rgsabound.cElements]
0x1804b3be0  movsxd  rcx, edi
0x1804b3be3  mov     rax, [rbx+10h]
0x1804b3be7  mov     [rax+rcx*4], r14d
0x1804b3beb  mov     rdx, rbx; psa
0x1804b3bee  lea     rcx, [rsp+0E8h+var_78]; pvt
0x1804b3bf3  call    ??0CComVariant@ATL@@QEAA@PEBUtagSAFEARRAY@@@Z; ATL::CComVariant::CComVariant(tagSAFEARRAY const *)
0x1804b3bf8  nop
0x1804b3bf9  mov     qword ptr [rsp+0E8h+rgsabound.cElements], r12
0x1804b3c01  mov     rcx, [rsi+90h]
0x1804b3c08  mov     rax, [rcx]
0x1804b3c0b  lea     r8, [rsp+0E8h+rgsabound]
0x1804b3c13  lea     rdx, aCaptureoneesti_0; "CaptureOneEstimateRBEffect"
0x1804b3c1a  mov     rax, [rax+98h]
0x1804b3c21  call    cs:__guard_dispatch_icall_fptr
0x1804b3c27  test    eax, eax
0x1804b3c29  js      loc_1804B4759
0x1804b3c2f  mov     rcx, qword ptr [rsp+0E8h+rgsabound.cElements]
0x1804b3c37  test    rcx, rcx
0x1804b3c3a  jz      loc_1804B4760
0x1804b3c40  mov     rax, [rcx]
0x1804b3c43  mov     rax, [rax+10h]
0x1804b3c47  call    cs:__guard_dispatch_icall_fptr
0x1804b3c4d  mov     rcx, qword ptr [rsp+0E8h+rgsabound.cElements]
0x1804b3c55  mov     rax, [rcx]
0x1804b3c58  movups  xmm0, xmmword ptr [rsp+0E8h+var_78]
0x1804b3c5d  movaps  [rsp+0E8h+var_98], xmm0
0x1804b3c62  movsd   xmm1, qword ptr [rsp+0E8h+var_78+10h]
0x1804b3c6b  movsd   [rsp+0E8h+var_88], xmm1
0x1804b3c71  lea     r8, [rsp+0E8h+var_98]
0x1804b3c76  lea     rdx, aCfalefttopoffs; "CFALeftTopOffset"
0x1804b3c7d  mov     rax, [rax+68h]
0x1804b3c81  call    cs:__guard_dispatch_icall_fptr
0x1804b3c87  cmp     eax, 8007000Eh
0x1804b3c8c  jz      loc_1804B4771
0x1804b3c92  cmp     eax, 86160210h
0x1804b3c97  jz      loc_1804B4771
0x1804b3c9d  cmp     eax, 86170103h
0x1804b3ca2  jz      loc_1804B4771
0x1804b3ca8  cmp     eax, 86180110h
0x1804b3cad  jz      loc_1804B4771
0x1804b3cb3  test    eax, eax
0x1804b3cb5  js      loc_1804B476A
0x1804b3cbb  lea     rcx, [rsp+0E8h+var_78]; pvarg
0x1804b3cc0  call    cs:__imp_VariantClear
0x1804b3cc6  mov     rcx, rbx; psa
0x1804b3cc9  call    cs:__imp_SafeArrayUnlock
0x1804b3ccf  test    eax, eax
0x1804b3cd1  js      short loc_1804B3CDD
0x1804b3cd3  mov     rcx, rbx; psa
0x1804b3cd6  call    cs:__imp_SafeArrayDestroy
0x1804b3cdc  nop
0x1804b3cdd  mov     rcx, [rsp+0E8h+psa]; psa
0x1804b3ce5  test    rcx, rcx
0x1804b3ce8  jz      loc_1804B4688
0x1804b3cee  call    cs:__imp_SafeArrayUnlock
0x1804b3cf4  test    eax, eax
0x1804b3cf6  js      loc_1804B4688
0x1804b3cfc  mov     rcx, [rsp+0E8h+psa]; psa
0x1804b3d04  call    cs:__imp_SafeArrayDestroy
0x1804b3d0a  jmp     loc_1804B4688
0x1804b3d0f  mov     [rsp+0E8h+cchCount2], r14d; cchCount2
0x1804b3d14  lea     rax, aWhitebalance_0; "WhiteBalance"
0x1804b3d1b  mov     [rsp+0E8h+lpString2], rax; lpString2
0x1804b3d20  mov     r9d, r14d; cchCount1
0x1804b3d23  mov     r8, rbx; lpString1
0x1804b3d26  mov     edx, edi; dwCmpFlags
0x1804b3d28  mov     ecx, r15d; Locale
0x1804b3d2b  call    cs:__imp_CompareStringW
0x1804b3d31  cmp     eax, r13d
0x1804b3d34  jnz     loc_1804B3DFA
0x1804b3d3a  mov     qword ptr [rsp+0E8h+rgsabound.cElements], r12
0x1804b3d42  mov     rcx, [rsi+90h]
0x1804b3d49  mov     rax, [rcx]
0x1804b3d4c  lea     r8, [rsp+0E8h+rgsabound]
0x1804b3d54  lea     rdx, aCaptureoneesti_0; "CaptureOneEstimateRBEffect"
0x1804b3d5b  mov     rax, [rax+98h]
0x1804b3d62  call    cs:__guard_dispatch_icall_fptr
0x1804b3d68  test    eax, eax
0x1804b3d6a  js      loc_1804B479C
0x1804b3d70  mov     rcx, qword ptr [rsp+0E8h+rgsabound.cElements]
0x1804b3d78  test    rcx, rcx
0x1804b3d7b  jz      loc_1804B47A3
0x1804b3d81  mov     rax, [rcx]
0x1804b3d84  mov     rax, [rax+10h]
0x1804b3d88  call    cs:__guard_dispatch_icall_fptr
0x1804b3d8e  mov     rcx, qword ptr [rsp+0E8h+rgsabound.cElements]
0x1804b3d96  mov     rax, [rcx]
0x1804b3d99  movups  xmm0, xmmword ptr [rsp+0E8h+pvarg]
0x1804b3d9e  movaps  [rsp+0E8h+var_98], xmm0
  ... truncated ...
```
