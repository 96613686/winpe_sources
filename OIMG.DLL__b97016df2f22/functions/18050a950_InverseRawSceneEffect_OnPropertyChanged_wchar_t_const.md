# InverseRawSceneEffect::OnPropertyChanged(wchar_t const *)

- ea: `0x18050a950`
- end: `0x18050ccf1`
- name: `?OnPropertyChanged@InverseRawSceneEffect@@UEAAJPEB_W@Z`
- size: `9121`
- prototype: `int(InverseRawSceneEffect *__hidden this, const wchar_t *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1804c6944`
- `0x18050a950`
- `0x18056dce0`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x18050aa35`
- `KERNEL32!CompareStringW` at `0x18050aa60`
- `KERNEL32!CompareStringW` at `0x18050aa8b`
- `KERNEL32!CompareStringW` at `0x18050aab6`
- `KERNEL32!CompareStringW` at `0x18050aae1`
- `KERNEL32!CompareStringW` at `0x18050ab0c`
- `KERNEL32!CompareStringW` at `0x18050ab37`
- `KERNEL32!CompareStringW` at `0x18050aebc`
- `KERNEL32!CompareStringW` at `0x18050b23d`
- `KERNEL32!CompareStringW` at `0x18050b3ea`
- `KERNEL32!CompareStringW` at `0x18050b4dc`
- `KERNEL32!CompareStringW` at `0x18050b750`
- `KERNEL32!CompareStringW` at `0x18050b82c`
- `KERNEL32!CompareStringW` at `0x18050b908`
- `KERNEL32!CompareStringW` at `0x18050b935`
- `KERNEL32!CompareStringW` at `0x18050b962`
- `KERNEL32!CompareStringW` at `0x18050b98f`
- `KERNEL32!CompareStringW` at `0x18050bbfe`
- `KERNEL32!CompareStringW` at `0x18050bc2b`
- `KERNEL32!CompareStringW` at `0x18050bc58`
- `KERNEL32!CompareStringW` at `0x18050bd79`
- `KERNEL32!CompareStringW` at `0x18050be96`
- `KERNEL32!CompareStringW` at `0x18050c077`
- `KERNEL32!CompareStringW` at `0x18050c181`
- `KERNEL32!CompareStringW` at `0x18050c28b`
- `KERNEL32!CompareStringW` at `0x18050c400`
- `KERNEL32!CompareStringW` at `0x18050c4dc`
- `KERNEL32!CompareStringW` at `0x18050aa35`
- `KERNEL32!CompareStringW` at `0x18050aa60`
- `KERNEL32!CompareStringW` at `0x18050aa8b`
- `KERNEL32!CompareStringW` at `0x18050aab6`
- `KERNEL32!CompareStringW` at `0x18050aae1`
- `KERNEL32!CompareStringW` at `0x18050ab0c`
- `KERNEL32!CompareStringW` at `0x18050ab37`
- `KERNEL32!CompareStringW` at `0x18050aebc`
- `KERNEL32!CompareStringW` at `0x18050b23d`
- `KERNEL32!CompareStringW` at `0x18050b3ea`
- `KERNEL32!CompareStringW` at `0x18050b4dc`
- `KERNEL32!CompareStringW` at `0x18050b750`
- `KERNEL32!CompareStringW` at `0x18050b82c`
- `KERNEL32!CompareStringW` at `0x18050b908`
- `KERNEL32!CompareStringW` at `0x18050b935`
- `KERNEL32!CompareStringW` at `0x18050b962`
- `KERNEL32!CompareStringW` at `0x18050b98f`
- `KERNEL32!CompareStringW` at `0x18050bbfe`
- `KERNEL32!CompareStringW` at `0x18050bc2b`
- `KERNEL32!CompareStringW` at `0x18050bc58`
- `KERNEL32!CompareStringW` at `0x18050bd79`
- `KERNEL32!CompareStringW` at `0x18050be96`
- `KERNEL32!CompareStringW` at `0x18050c077`
- `KERNEL32!CompareStringW` at `0x18050c181`
- `KERNEL32!CompareStringW` at `0x18050c28b`
- `KERNEL32!CompareStringW` at `0x18050c400`
- `KERNEL32!CompareStringW` at `0x18050c4dc`
- `OLEAUT32!__imp_VariantInit` at `0x18050a9b4`
- `OLEAUT32!__imp_VariantInit` at `0x18050a9b4`
- `OLEAUT32!__imp_VariantClear` at `0x18050acc4`
- `OLEAUT32!__imp_VariantClear` at `0x18050ad01`
- `OLEAUT32!__imp_VariantClear` at `0x18050ae61`
- `OLEAUT32!__imp_VariantClear` at `0x18050b052`
- `OLEAUT32!__imp_VariantClear` at `0x18050b1e2`
- `OLEAUT32!__imp_VariantClear` at `0x18050bd20`
- `OLEAUT32!__imp_VariantClear` at `0x18050be3d`
- `OLEAUT32!__imp_VariantClear` at `0x18050acc4`
- `OLEAUT32!__imp_VariantClear` at `0x18050ad01`
- `OLEAUT32!__imp_VariantClear` at `0x18050ae61`
- `OLEAUT32!__imp_VariantClear` at `0x18050b052`
- `OLEAUT32!__imp_VariantClear` at `0x18050b1e2`
- `OLEAUT32!__imp_VariantClear` at `0x18050bd20`
- `OLEAUT32!__imp_VariantClear` at `0x18050be3d`

## string_xrefs

- `0x18050ab1f`: `ExposureCompensation`
- `0x18050aaf4`: `HighlightRecoveryCaptureOneCompliant`
- `0x18050c435`: `CurveDataCache`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall InverseRawSceneEffect::OnPropertyChanged(InverseRawSceneEffect *this, const wchar_t *a2)
{
  int v4; // eax
  int v5; // eax
  __int64 v6; // rcx
  __int64 (__fastcall *v7)(__int64, const wchar_t *, __int64 **); // rax
  int v8; // eax
  __int64 v9; // rax
  int v10; // eax
  int v11; // eax
  __int64 v12; // rax
  int v13; // ebx
  __int64 result; // rax
  int v15; // eax
  __int64 v16; // rax
  int v17; // eax
  int v18; // eax
  __int64 v19; // rax
  int v20; // ebx
  __int64 v21; // rcx
  __int64 (__fastcall *v22)(__int64, const wchar_t *, __int64 **); // rax
  int v23; // eax
  __int64 v24; // rax
  int v25; // eax
  int v26; // eax
  __int64 v27; // rax
  int v28; // ebx
  int v29; // eax
  __int64 v30; // rax
  int v31; // eax
  int v32; // eax
  __int64 v33; // rax
  int v34; // ebx
  int v35; // eax
  __int64 v36; // rax
  int v37; // eax
  int v38; // eax
  __int64 v39; // rax
  int v40; // eax
  int v41; // eax
  __int64 v42; // rax
  int v43; // eax
  int v44; // eax
  __int64 v45; // rax
  int v46; // eax
  int v47; // eax
  __int64 v48; // rax
  int v49; // eax
  int v50; // eax
  __int64 v51; // rax
  int v52; // eax
  BOOL v53; // ebx
  int v54; // eax
  int v55; // eax
  BOOL v56; // ebx
  int v57; // eax
  int v58; // eax
  int v59; // eax
  __int64 v60; // rax
  int v61; // eax
  int v62; // eax
  __int64 v63; // rax
  int v64; // eax
  int v65; // eax
  __int64 v66; // rax
  int v67; // eax
  double v68; // xmm6_8
  int v69; // eax
  __int64 v70; // rax
  int v71; // ebx
  LONG v72; // ebx
  int v73; // eax
  __int64 v74; // rax
  int v75; // ebx
  int v76; // eax
  __int64 v77; // rax
  int v78; // eax
  int v79; // eax
  __int64 v80; // rax
  int v81; // eax
  int v82; // eax
  __int64 v83; // rax
  int v84; // eax
  int v85; // eax
  __int64 v86; // rax
  int v87; // eax
  BOOL v88; // ebx
  int v89; // eax
  int v90; // eax
  int v91; // eax
  int v92; // eax
  BOOL v93; // ebx
  int v94; // eax
  int v95; // eax
  int iVal; // ebx
  BOOL v97; // esi
  int v98; // eax
  int v99; // eax
  int v100; // eax
  int v101; // eax
  int v102; // eax
  __int64 v103; // rax
  int v104; // eax
  int v105; // eax
  __int64 v106; // rax
  int v107; // eax
  int v108; // eax
  __int64 v109; // rax
  int v110; // eax
  int v111; // [rsp+30h] [rbp-A8h] BYREF
  _DWORD v112[4]; // [rsp+38h] [rbp-A0h] BYREF
  VARIANTARG pvarg; // [rsp+48h] [rbp-90h] BYREF
  VARIANTARG v114; // [rsp+60h] [rbp-78h] BYREF
  VARIANTARG v115[2]; // [rsp+80h] [rbp-58h] BYREF
  __int64 *v116; // [rsp+E8h] [rbp+10h] BYREF

  try
  {
    if ( !a2 )
      ATL::BaseAtlThrow(-2147467261);
    v4 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 16) + 272LL))(*((_QWORD *)this + 16));
    if ( v4 < 0 )
      ATL::BaseAtlThrow(v4);
    memset(&pvarg, 0, sizeof(pvarg));
    VariantInit(&pvarg);
    v5 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, VARIANTARG *))(**((_QWORD **)this + 16) + 96LL))(
           *((_QWORD *)this + 16),
           a2,
           &pvarg);
    if ( v5 == -2147024882 || v5 == -2045378032 || v5 == -2045312765 || v5 == -2045247216 )
      ATL::BaseAtlThrow(v5);
    if ( v5 < 0 )
      ATL::BaseAtlThrow(v5);
    if ( CompareStringW(0x7Fu, 1u, a2, -1, L"WhiteBalance", -1) == 2
      || CompareStringW(0x7Fu, 1u, a2, -1, L"_BaselineExposure", -1) == 2
      || CompareStringW(0x7Fu, 1u, a2, -1, L"_CameraMatrix", -1) == 2
      || CompareStringW(0x7Fu, 1u, a2, -1, L"Gain", -1) == 2
      || CompareStringW(0x7Fu, 1u, a2, -1, L"EnableWhiteBalance", -1) == 2
      || CompareStringW(0x7Fu, 1u, a2, -1, L"HighlightRecoveryCaptureOneCompliant", -1) == 2 )
    {
      v116 = 0;
      v108 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, __int64 **))(**((_QWORD **)this + 18) + 152LL))(
               *((_QWORD *)this + 18),
               L"RawColorEffect",
               &v116);
      if ( v108 < 0 )
        ATL::BaseAtlThrow(v108);
      if ( !v116 )
        ATL::BaseAtlThrow(-2045247222);
      (*(void (__fastcall **)(__int64 *))(*v116 + 16))(v116);
      v109 = *v116;
      v115[0] = pvarg;
      v110 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, VARIANTARG *))(v109 + 104))(v116, a2, v115);
      if ( v110 == -2147024882 || v110 == -2045378032 || v110 == -2045312765 || v110 == -2045247216 )
        ATL::BaseAtlThrow(v110);
      if ( v110 < 0 )
        ATL::BaseAtlThrow(v110);
    }
    else if ( CompareStringW(0x7Fu, 1u, a2, -1, L"ExposureCompensation", -1) == 2 )
    {
      v6 = *((_QWORD *)this + 18);
      v116 = 0;
      v7 = *(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 **))(*(_QWORD *)v6 + 152LL);
      if ( pvarg.dblVal <= 0.0 )
      {
        v15 = v7(v6, L"RawColorEffect", &v116);
        if ( v15 < 0 )
          ATL::BaseAtlThrow(v15);
        if ( !v116 )
          ATL::BaseAtlThrow(-2045247222);
        (*(void (__fastcall **)(__int64 *))(*v116 + 16))(v116);
        v16 = *v116;
        v115[0] = pvarg;
        v17 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, VARIANTARG *))(v16 + 104))(v116, a2, v115);
        if ( v17 == -2147024882 || v17 == -2045378032 || v17 == -2045312765 || v17 == -2045247216 )
          ATL::BaseAtlThrow(v17);
        if ( v17 < 0 )
          ATL::BaseAtlThrow(v17);
        if ( *((_BYTE *)this + 160) )
        {
          v116 = 0;
          v18 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, __int64 **))(**((_QWORD **)this + 18) + 152LL))(
                  *((_QWORD *)this + 18),
                  L"ExposureCurveEffect",
                  &v116);
          if ( v18 < 0 )
            ATL::BaseAtlThrow(v18);
          if ( !v116 )
            ATL::BaseAtlThrow(-2045247222);
          (*(void (__fastcall **)(__int64 *))(*v116 + 16))(v116);
          v19 = *v116;
          v114.vt = 5;
          v114.llVal = 0;
          v115[0] = v114;
          v20 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, VARIANTARG *))(v19 + 104))(v116, a2, v115);
          VariantClear(&v114);
          if ( v20 == -2147024882 || v20 == -2045378032 || v20 == -2045312765 || v20 == -2045247216 )
            ATL::BaseAtlThrow(v20);
          if ( v20 < 0 )
            ATL::BaseAtlThrow(v20);
          *((_BYTE *)this + 160) = 0;
        }
      }
      else
      {
        v8 = v7(v6, L"ExposureCurveEffect", &v116);
        if ( v8 < 0 )
          ATL::BaseAtlThrow(v8);
        if ( !v116 )
          ATL::BaseAtlThrow(-2045247222);
        (*(void (__fastcall **)(__int64 *))(*v116 + 16))(v116);
        v9 = *v116;
        v114 = pvarg;
        v10 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, VARIANTARG *))(v9 + 104))(v116, a2, &v114);
        if ( v10 == -2147024882 || v10 == -2045378032 || v10 == -2045312765 || v10 == -2045247216 )
          ATL::BaseAtlThrow(v10);
        if ( v10 < 0 )
          ATL::BaseAtlThrow(v10);
        if ( !*((_BYTE *)this + 160) )
        {
          v116 = 0;
          v11 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, __int64 **))(**((_QWORD **)this + 18) + 152LL))(
                  *((_QWORD *)this + 18),
                  L"RawColorEffect",
                  &v116);
          if ( v11 < 0 )
            ATL::BaseAtlThrow(v11);
          if ( !v116 )
            ATL::BaseAtlThrow(-2045247222);
          (*(void (__fastcall **)(__int64 *))(*v116 + 16))(v116);
          v12 = *v116;
          v114.vt = 5;
          v114.llVal = 0;
          v115[0] = v114;
          v13 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, VARIANTARG *))(v12 + 104))(v116, a2, v115);
          VariantClear(&v114);
          if ( v13 == -2147024882 || v13 == -2045378032 || v13 == -2045312765 || v13 == -2045247216 )
            ATL::BaseAtlThrow(v13);
          if ( v13 < 0 )
            ATL::BaseAtlThrow(v13);
          *((_BYTE *)this + 160) = 1;
        }
      }
    }
    else if ( CompareStringW(0x7Fu, 1u, a2, -1, L"Saturation", -1) == 2 )
    {
      v21 = *((_QWORD *)this + 18);
      v116 = 0;
      v22 = *(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 **))(*(_QWORD *)v21 + 152LL);
      if ( pvarg.dblVal <= 0.0 )
      {
        v29 = v22(v21, L"RawColorEffect", &v116);
        if ( v29 < 0 )
          ATL::BaseAtlThrow(v29);
        if ( !v116 )
          ATL::BaseAtlThrow(-2045247222);
        (*(void (__fastcall **)(__int64 *))(*v116 + 16))(v116);
        v30 = *v116;
        v115[0] = pvarg;
        v31 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, VARIANTARG *))(v30 + 104))(v116, a2, v115);
        if ( v31 == -2147024882 || v31 == -2045378032 || v31 == -2045312765 || v31 == -2045247216 )
          ATL::BaseAtlThrow(v31);
        if ( v31 < 0 )
          ATL::BaseAtlThrow(v31);
        if ( *((_BYTE *)this + 161) )
        {
          v116 = 0;
          v32 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, __int64 **))(**((_QWORD **)this + 18) + 152LL))(
                  *((_QWORD *)this + 18),
                  L"SaturationEffect",
                  &v116);
          if ( v32 < 0 )
            ATL::BaseAtlThrow(v32);
          if ( !v116 )
            ATL::BaseAtlThrow(-2045247222);
          (*(void (__fastcall **)(__int64 *))(*v116 + 16))(v116);
          v33 = *v116;
          v114.vt = 5;
          v114.llVal = 0;
          v115[0] = v114;
          v34 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, VARIANTARG *))(v33 + 104))(v116, a2, v115);
          VariantClear(&v114);
          if ( v34 == -2147024882 || v34 == -2045378032 || v34 == -2045312765 || v34 == -2045247216 )
            ATL::BaseAtlThrow(v34);
          if ( v34 < 0 )
            ATL::BaseAtlThrow(v34);
          *((_BYTE *)this + 161) = 0;
        }
      }
      else
      {
        v23 = v22(v21, L"SaturationEffect", &v116);
        if ( v23 < 0 )
          ATL::BaseAtlThrow(v23);
        if ( !v116 )
          ATL::BaseAtlThrow(-2045247222);
        (*(void (__fastcall **)(__int64 *))(*v116 + 16))(v116);
        v24 = *v116;
        v115[0] = pvarg;
        v25 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, VARIANTARG *))(v24 + 104))(v116, a2, v115);
        if ( v25 == -2147024882 || v25 == -2045378032 || v25 == -2045312765 || v25 == -2045247216 )
          ATL::BaseAtlThrow(v25);
        if ( v25 < 0 )
          ATL::BaseAtlThrow(v25);
        if ( !*((_BYTE *)this + 161) )
        {
          v116 = 0;
          v26 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, __int64 **))(**((_QWORD **)this + 18) + 152LL))(
                  *((_QWORD *)this + 18),
                  L"RawColorEffect",
                  &v116);
          if ( v26 < 0 )
            ATL::BaseAtlThrow(v26);
          if ( !v116 )
            ATL::BaseAtlThrow(-2045247222);
          (*(void (__fastcall **)(__int64 *))(*v116 + 16))(v116);
          v27 = *v116;
          v114.vt = 5;
          v114.llVal = 0;
          v115[0] = v114;
          v28 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, VARIANTARG *))(v27 + 104))(v116, a2, v115);
          VariantClear(&v114);
          if ( v28 == -2147024882 || v28 == -2045378032 || v28 == -2045312765 || v28 == -2045247216 )
            ATL::BaseAtlThrow(v28);
          if ( v28 < 0 )
            ATL::BaseAtlThrow(v28);
          *((_BYTE *)this + 161) = 1;
        }
      }
    }
    else if ( CompareStringW(0x7Fu, 1u, a2, -1, L"Contrast", -1) == 2 )
    {
      v116 = 0;
      v35 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, __int64 **))(**((_QWORD **)this + 18) + 152LL))(
              *((_QWORD *)this + 18),
              L"ContrastEffect",
              &v116);
      if ( v35 < 0 )
        ATL::BaseAtlThrow(v35);
      if ( !v116 )
        ATL::BaseAtlThrow(-2045247222);
      (*(void (__fastcall **)(__int64 *))(*v116 + 16))(v116);
      v36 = *v116;
      v115[0] = pvarg;
      v37 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, VARIANTARG *))(v36 + 104))(v116, a2, v115);
      if ( v37 == -2147024882 || v37 == -2045378032 || v37 == -2045312765 || v37 == -2045247216 )
        ATL::BaseAtlThrow(v37);
      if ( v37 < 0 )
        ATL::BaseAtlThrow(v37);
      v116 = 0;
      v38 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, __int64 **))(**((_QWORD **)this + 18) + 152LL))(
              *((_QWORD *)this + 18),
              L"PostFilmContrastEffect",
              &v116);
      if ( v38 < 0 )
        ATL::BaseAtlThrow(v38);
      if ( !v116 )
        ATL::BaseAtlThrow(-2045247222);
      (*(void (__fastcall **)(__int64 *))(*v116 + 16))(v116);
      v39 = *v116;
      v115[0] = pvarg;
      v40 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, VARIANTARG *))(v39 + 104))(v116, a2, v115);
      if ( v40 == -2147024882 || v40 == -2045378032 || v40 == -2045312765 || v40 == -2045247216 )
        ATL::BaseAtlThrow(v40);
      if ( v40 < 0 )
        ATL::BaseAtlThrow(v40);
    }
    else if ( CompareStringW(0x7Fu, 1u, a2, -1, L"Brightness", -1) == 2 )
    {
      v116 = 0;
      v41 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, __int64 **))(**((_QWORD **)this + 18) + 152LL))(
              *((_QWORD *)this + 18),
              L"BrightnessEffect",
              &v116);
      if ( v41 < 0 )
        ATL::BaseAtlThrow(v41);
      if ( !v116 )
        ATL::BaseAtlThrow(-2045247222);
      (*(void (__fastcall **)(__int64 *))(*v116 + 16))(v116);
      v42 = *v116;
      v115[0] = pvarg;
      v43 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, VARIANTARG *))(v42 + 104))(v116, a2, v115);
      if ( v43 == -2147024882 || v43 == -2045378032 || v43 == -2045312765 || v43 == -2045247216 )
        ATL::BaseAtlThrow(v43);
      if ( v43 < 0 )
        ATL::BaseAtlThrow(v43);
    }
    else if ( CompareStringW(0x7Fu, 1u, a2, -1, L"FilmCurvePoints", -1) == 2 )
    {
      v116 = 0;
      v44 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, __int64 **))(**((_QWORD **)this + 18) + 152LL))(
              *((_QWORD *)this + 18),
              L"FilmCurveEffect",
              &v116);
      if ( v44 < 0 )
        ATL::BaseAtlThrow(v44);
      if ( !v116 )
        ATL::BaseAtlThrow(-2045247222);
      (*(void (__fastcall **)(__int64 *))(*v116 + 16))(v116);
      v45 = *v116;
      v115[0] = pvarg;
      v46 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, VARIANTARG *))(v45 + 104))(v116, L"CurvePts0", v115);
      if ( v46 == -2147024882 || v46 == -2045378032 || v46 == -2045312765 || v46 == -2045247216 )
        ATL::BaseAtlThrow(v46);
      if ( v46 < 0 )
        ATL::BaseAtlThrow(v46);
      v116 = 0;
      v47 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, __int64 **))(**((_QWORD **)this + 18) + 152LL))(
              *((_QWORD *)this + 18),
              L"FilmCurveEffect",
              &v116);
      if ( v47 < 0 )
        ATL::BaseAtlThrow(v47);
      if ( !v116 )
        ATL::BaseAtlThrow(-2045247222);
      (*(void (__fastcall **)(__int64 *))(*v116 + 16))(v116);
      v48 = *v116;
      v115[0] = pvarg;
      v49 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, VARIANTARG *))(v48 + 104))(v116, L"CurvePts1", v115);
      if ( v49 == -2147024882 || v49 == -2045378032 || v49 == -2045312765 || v49 == -2045247216 )
        ATL::BaseAtlThrow(v49);
      if ( v49 < 0 )
        ATL::BaseAtlThrow(v49);
      v116 = 0;
      v50 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, __int64 **))(**((_QWORD **)this + 18) + 152LL))(
              *((_QWORD *)this + 18),
              L"FilmCurveEffect",
              &v116);
      if ( v50 < 0 )
        ATL::BaseAtlThrow(v50);
      if ( !v116 )
        ATL::BaseAtlThrow(-2045247222);
      (*(void (__fastcall **)(__int64 *))(*v116 + 16))(v116);
      v51 = *v116;
      v115[0] = pvarg;
      v52 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, VARIANTARG *))(v51 + 104))(v116, L"CurvePts2", v115);
      if ( v52 == -2147024882 || v52 == -2045378032 || v52 == -2045312765 || v52 == -2045247216 )
        ATL::BaseAtlThrow(v52);
      if ( v52 < 0 )
        ATL::BaseAtlThrow(v52);
    }
    else if ( CompareStringW(0x7Fu, 1u, a2, -1, L"EnableFilmCurve", -1) == 2 )
    {
      v53 = pvarg.iVal != 0;
      v116 = 0;
      v54 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, __int64 **))(**((_QWORD **)this + 18) + 152LL))(
              *((_QWORD *)this + 18),
              L"FilmCurveEffect",
              &v116);
      if ( v54 < 0 )
        ATL::BaseAtlThrow(v54);
      if ( !v116 )
        ATL::BaseAtlThrow(-2045247222);
      (*(void (__fastcall **)(__int64 *))(*v116 + 16))(v116);
      v55 = (*(__int64 (__fastcall **)(__int64 *, BOOL))(*v116 + 192))(v116, v53);
      if ( v55 == -2147024882 || v55 == -2045378032 || v55 == -2045312765 || v55 == -2045247216 )
        ATL::BaseAtlThrow(v55);
      if ( v55 < 0 )
        ATL::BaseAtlThrow(v55);
    }
    else if ( CompareStringW(0x7Fu, 1u, a2, -1, L"EnableGamma", -1) == 2 )
    {
      v56 = pvarg.iVal != 0;
      v116 = 0;
      v57 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, __int64 **))(**((_QWORD **)this + 18) + 152LL))(
              *((_QWORD *)this + 18),
              L"GammaEffect",
              &v116);
      if ( v57 < 0 )
        ATL::BaseAtlThrow(v57);
      if ( !v116 )
        ATL::BaseAtlThrow(-2045247222);
      (*(void (__fastcall **)(__int64 *))(*v116 + 16))(v116);
      v58 = (*(__int64 (__fastcall **)(__int64 *, BOOL))(*v116 + 192))(v116, v56);
      if ( v58 == -2147024882 || v58 == -2045378032 || v58 == -2045312765 || v58 == -2045247216 )
        ATL::BaseAtlThrow(v58);
      if ( v58 < 0 )
        ATL::BaseAtlThrow(v58);
    }
    else if ( CompareStringW(0x7Fu, 1u, a2, -1, L"BlackPointIn", -1) == 2
           || CompareStringW(0x7Fu, 1u, a2, -1, L"Midpoint", -1) == 2
           || CompareStringW(0x7Fu, 1u, a2, -1, L"WhitePointIn", -1) == 2 )
    {
      v116 = 0;
      v105 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, __int64 **))(**((_QWORD **)this + 18) + 152LL))(
               *((_QWORD *)this + 18),
               L"LevelsEffect1",
               &v116);
      if ( v105 < 0 )
        ATL::BaseAtlThrow(v105);
      if ( !v116 )
        ATL::BaseAtlThrow(-2045247222);
      (*(void (__fastcall **)(__int64 *))(*v116 + 16))(v116);
      v106 = *v116;
      v115[0] = pvarg;
      v107 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, VARIANTARG *))(v106 + 104))(v116, a2, v115);
      if ( v107 == -2147024882 || v107 == -2045378032 || v107 == -2045312765 || v107 == -2045247216 )
        ATL::BaseAtlThrow(v107);
      if ( v107 < 0 )
        ATL::BaseAtlThrow(v107);
    }
    else if ( CompareStringW(0x7Fu, 1u, a2, -1, L"CurvePoints", -1) == 2 )
    {
      v116 = 0;
      v59 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, __int64 **))(**((_QWORD **)this + 18) + 152LL))(
              *((_QWORD *)this + 18),
              L"CurveEffect",
              &v116);
      if ( v59 < 0 )
        ATL::BaseAtlThrow(v59);
      if ( !v116 )
        ATL::BaseAtlThrow(-2045247222);
      (*(void (__fastcall **)(__int64 *))(*v116 + 16))(v116);
      v60 = *v116;
      v115[0] = pvarg;
      v61 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, VARIANTARG *))(v60 + 104))(v116, L"CurvePts0", v115);
      if ( v61 == -2147024882 || v61 == -2045378032 || v61 == -2045312765 || v61 == -2045247216 )
        ATL::BaseAtlThrow(v61);
      if ( v61 < 0 )
        ATL::BaseAtlThrow(v61);
      v116 = 0;
      v62 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, __int64 **))(**((_QWORD **)this + 18) + 152LL))(
              *((_QWORD *)this + 18),
              L"CurveEffect",
              &v116);
      if ( v62 < 0 )
        ATL::BaseAtlThrow(v62);
      if ( !v116 )
        ATL::BaseAtlThrow(-2045247222);
      (*(void (__fastcall **)(__int64 *))(*v116 + 16))(v116);
      v63 = *v116;
      v115[0] = pvarg;
      v64 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, VARIANTARG *))(v63 + 104))(v116, L"CurvePts1", v115);
      if ( v64 == -2147024882 || v64 == -2045378032 || v64 == -2045312765 || v64 == -2045247216 )
        ATL::BaseAtlThrow(v64);
      if ( v64 < 0 )
        ATL::BaseAtlThrow(v64);
      v116 = 0;
      v65 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, __int64 **))(**((_QWORD **)this + 18) + 152LL))(
              *((_QWORD *)this + 18),
              L"CurveEffect",
              &v116);
      if ( v65 < 0 )
        ATL::BaseAtlThrow(v65);
      if ( !v116 )
        ATL::BaseAtlThrow(-2045247222);
      (*(void (__fastcall **)(__int64 *))(*v116 + 16))(v116);
      v66 = *v116;
      v115[0] = pvarg;
      v67 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, VARIANTARG *))(v66 + 104))(v116, L"CurvePts2", v115);
      if ( v67 == -2147024882 || v67 == -2045378032 || v67 == -2045312765 || v67 == -2045247216 )
        ATL::BaseAtlThrow(v67);
      if ( v67 < 0 )
        ATL::BaseAtlThrow(v67);
    }
    else if ( CompareStringW(0x7Fu, 1u, a2, -1, L"BlackPointOut", -1) == 2
           || CompareStringW(0x7Fu, 1u, a2, -1, L"WhitePointOut", -1) == 2 )
    {
      v116 = 0;
      v102 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, __int64 **))(**((_QWORD **)this + 18) + 152LL))(
               *((_QWORD *)this + 18),
               L"LevelsEffect2",
               &v116);
      if ( v102 < 0 )
        ATL::BaseAtlThrow(v102);
      if ( !v116 )
        ATL::BaseAtlThrow(-2045247222);
      (*(void (__fastcall **)(__int64 *))(*v116 + 16))(v116);
      v103 = *v116;
      v115[0] = pvarg;
      v104 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, VARIANTARG *))(v103 + 104))(v116, a2, v115);
      if ( v104 == -2147024882 || v104 == -2045378032 || v104 == -2045312765 || v104 == -2045247216 )
        ATL::BaseAtlThrow(v104);
      if ( v104 < 0 )
        ATL::BaseAtlThrow(v104);
    }
    else if ( CompareStringW(0x7Fu, 1u, a2, -1, L"Shadow", -1) == 2 )
    {
      v68 = pvarg.dblVal * 0.003;
      v116 = 0;
      v69 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, __int64 **))(**((_QWORD **)this + 18) + 152LL))(
              *((_QWORD *)this + 18),
              L"DarkExpandEffect",
              &v116);
      if ( v69 < 0 )
        ATL::BaseAtlThrow(v69);
      if ( !v116 )
        ATL::BaseAtlThrow(-2045247222);
      (*(void (__fastcall **)(__int64 *))(*v116 + 16))(v116);
      v70 = *v116;
      v114.vt = 5;
      v114.dblVal = v68;
      v115[0] = v114;
      v71 = (*(__int64 (__fastcall **)(__int64 *, const WCHAR *, VARIANTARG *))(v70 + 104))(v116, L"Midpoint", v115);
      VariantClear(&v114);
      if ( v71 == -2147024882 || v71 == -2045378032 || v71 == -2045312765 || v71 == -2045247216 )
        ATL::BaseAtlThrow(v71);
      if ( v71 < 0 )
        ATL::BaseAtlThrow(v71);
    }
    else if ( CompareStringW(0x7Fu, 1u, a2, -1, L"UseColorEngineModel", -1) == 2 )
    {
      v72 = pvarg.iVal != 0;
      v116 = 0;
      v73 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, __int64 **))(**((_QWORD **)this + 18) + 152LL))(
              *((_QWORD *)this + 18),
              L"ColorProfileMultiplexerEffect",
              &v116);
      if ( v73 < 0 )
        ATL::BaseAtlThrow(v73);
      if ( !v116 )
        ATL::BaseAtlThrow(-2045247222);
      (*(void (__fastcall **)(__int64 *))(*v116 + 16))(v116);
      v74 = *v116;
      v114.vt = 3;
      v114.lVal = v72;
      v115[0] = v114;
      v75 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, VARIANTARG *))(v74 + 104))(
              v116,
              L"OutputIndex",
              v115);
      VariantClear(&v114);
      if ( v75 == -2147024882 || v75 == -2045378032 || v75 == -2045312765 || v75 == -2045247216 )
        ATL::BaseAtlThrow(v75);
      if ( v75 < 0 )
        ATL::BaseAtlThrow(v75);
    }
    else if ( CompareStringW(0x7Fu, 1u, a2, -1, L"DestinationColorProfile", -1) == 2 )
    {
      v116 = 0;
      v76 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, __int64 **))(**((_QWORD **)this + 18) + 152LL))(
              *((_QWORD *)this + 18),
              L"ColorEngineEffect",
              &v116);
      if ( v76 < 0 )
        ATL::BaseAtlThrow(v76);
      if ( !v116 )
        ATL::BaseAtlThrow(-2045247222);
      (*(void (__fastcall **)(__int64 *))(*v116 + 16))(v116);
      v77 = *v116;
      v115[0] = pvarg;
      v78 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, VARIANTARG *))(v77 + 104))(
              v116,
              L"SourceColorProfile",
              v115);
      if ( v78 <= -2045181697 || (unsigned int)(v78 + 2045181694) <= 0x79E6FEFD )
      {
        if ( v78 != -2147024882 && v78 != -2045378032 && v78 != -2045312765 && v78 != -2045247216 )
          ATL::BaseAtlThrow(v78);
        ATL::BaseAtlThrow(v78);
      }
      v116 = 0;
      v79 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, __int64 **))(**((_QWORD **)this + 18) + 152LL))(
              *((_QWORD *)this + 18),
              L"ColorManagementEffect",
              &v116);
      if ( v79 < 0 )
        ATL::BaseAtlThrow(v79);
      if ( !v116 )
        ATL::BaseAtlThrow(-2045247222);
      (*(void (__fastcall **)(__int64 *))(*v116 + 16))(v116);
      v80 = *v116;
      v115[0] = pvarg;
      v81 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, VARIANTARG *))(v80 + 104))(
              v116,
              L"SourceColorProfile",
              v115);
      if ( v81 <= -2045181697 || (unsigned int)(v81 + 2045181694) <= 0x79E6FEFD )
      {
        if ( v81 != -2147024882 && v81 != -2045378032 && v81 != -2045312765 && v81 != -2045247216 )
          ATL::BaseAtlThrow(v81);
        ATL::BaseAtlThrow(v81);
      }
    }
    else if ( CompareStringW(0x7Fu, 1u, a2, -1, L"CameraICCProfile", -1) == 2 )
    {
      v116 = 0;
      v82 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, __int64 **))(**((_QWORD **)this + 18) + 152LL))(
              *((_QWORD *)this + 18),
              L"ColorManagementEffect",
              &v116);
      if ( v82 < 0 )
        ATL::BaseAtlThrow(v82);
      if ( !v116 )
        ATL::BaseAtlThrow(-2045247222);
      (*(void (__fastcall **)(__int64 *))(*v116 + 16))(v116);
      v83 = *v116;
      v115[0] = pvarg;
      v84 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, VARIANTARG *))(v83 + 104))(
              v116,
              L"DestinationColorProfile",
              v115);
      if ( v84 <= -2045181697 || (unsigned int)(v84 + 2045181694) <= 0x79E6FEFD )
      {
        if ( v84 != -2147024882 && v84 != -2045378032 && v84 != -2045312765 && v84 != -2045247216 )
          ATL::BaseAtlThrow(v84);
        ATL::BaseAtlThrow(v84);
      }
    }
    else if ( CompareStringW(0x7Fu, 1u, a2, -1, L"CameraColorEngineProfile", -1) == 2 )
    {
      v116 = 0;
      v85 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, __int64 **))(**((_QWORD **)this + 18) + 152LL))(
              *((_QWORD *)this + 18),
              L"ColorEngineEffect",
              &v116);
      if ( v85 < 0 )
        ATL::BaseAtlThrow(v85);
      if ( !v116 )
        ATL::BaseAtlThrow(-2045247222);
      (*(void (__fastcall **)(__int64 *))(*v116 + 16))(v116);
      v86 = *v116;
      v115[0] = pvarg;
      v87 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, VARIANTARG *))(v86 + 104))(
              v116,
              L"DestinationColorProfile",
              v115);
      if ( v87 <= -2045181697 || (unsigned int)(v87 + 2045181694) <= 0x79E6FEFD )
      {
        if ( v87 != -2147024882 && v87 != -2045378032 && v87 != -2045312765 && v87 != -2045247216 )
          ATL::BaseAtlThrow(v87);
        ATL::BaseAtlThrow(v87);
      }
    }
    else if ( CompareStringW(0x7Fu, 1u, a2, -1, L"EnableColorManagement", -1) == 2 )
    {
      v88 = pvarg.iVal != 0;
      v116 = 0;
      v89 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, __int64 **))(**((_QWORD **)this + 18) + 152LL))(
              *((_QWORD *)this + 18),
              L"ColorManagementEffect",
              &v116);
      if ( v89 < 0 )
        ATL::BaseAtlThrow(v89);
      if ( !v116 )
        ATL::BaseAtlThrow(-2045247222);
      (*(void (__fastcall **)(__int64 *))(*v116 + 16))(v116);
      v90 = (*(__int64 (__fastcall **)(__int64 *, BOOL))(*v116 + 192))(v116, v88);
      if ( v90 == -2147024882 || v90 == -2045378032 || v90 == -2045312765 || v90 == -2045247216 )
        ATL::BaseAtlThrow(v90);
      if ( v90 < 0 )
        ATL::BaseAtlThrow(v90);
      v116 = 0;
      v91 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, __int64 **))(**((_QWORD **)this + 18) + 152LL))(
              *((_QWORD *)this + 18),
              L"ColorEngineEffect",
              &v116);
      if ( v91 < 0 )
        ATL::BaseAtlThrow(v91);
      if ( !v116 )
        ATL::BaseAtlThrow(-2045247222);
      (*(void (__fastcall **)(__int64 *))(*v116 + 16))(v116);
      v92 = (*(__int64 (__fastcall **)(__int64 *, BOOL))(*v116 + 192))(v116, v88);
      if ( v92 == -2147024882 || v92 == -2045378032 || v92 == -2045312765 || v92 == -2045247216 )
        ATL::BaseAtlThrow(v92);
      if ( v92 < 0 )
        ATL::BaseAtlThrow(v92);
    }
    else if ( CompareStringW(0x7Fu, 1u, a2, -1, L"EnableCaching", -1) == 2 )
    {
      v93 = pvarg.iVal != 0;
      v116 = 0;
      v94 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, __int64 **))(**((_QWORD **)this + 18) + 152LL))(
              *((_QWORD *)this + 18),
              L"CurveDataCache",
              &v116);
      if ( v94 < 0 )
        ATL::BaseAtlThrow(v94);
      if ( !v116 )
        ATL::BaseAtlThrow(-2045247222);
      (*(void (__fastcall **)(__int64 *))(*v116 + 16))(v116);
      v95 = (*(__int64 (__fastcall **)(__int64 *, BOOL))(*v116 + 192))(v116, v93);
      if ( v95 == -2147024882 || v95 == -2045378032 || v95 == -2045312765 || v95 == -2045247216 )
        ATL::BaseAtlThrow(v95);
      if ( v95 < 0 )
        ATL::BaseAtlThrow(v95);
    }
    else if ( CompareStringW(0x7Fu, 1u, a2, -1, L"EnablePostFilmCurveContrast", -1) == 2 )
    {
      iVal = pvarg.iVal;
      v97 = pvarg.iVal != 0;
      v116 = 0;
      v98 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, __int64 **))(**((_QWORD **)this + 18) + 152LL))(
              *((_QWORD *)this + 18),
              L"ContrastEffect",
              &v116);
      if ( v98 < 0 )
        ATL::BaseAtlThrow(v98);
      if ( !v116 )
        ATL::BaseAtlThrow(-2045247222);
      (*(void (__fastcall **)(__int64 *))(*v116 + 16))(v116);
      v99 = (*(__int64 (__fastcall **)(__int64 *, bool))(*v116 + 192))(v116, iVal == 0);
      if ( v99 == -2147024882 || v99 == -2045378032 || v99 == -2045312765 || v99 == -2045247216 )
        ATL::BaseAtlThrow(v99);
      if ( v99 < 0 )
        ATL::BaseAtlThrow(v99);
      v116 = 0;
      v100 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, __int64 **))(**((_QWORD **)this + 18) + 152LL))(
               *((_QWORD *)this + 18),
               L"PostFilmContrastEffect",
               &v116);
      if ( v100 < 0 )
        ATL::BaseAtlThrow(v100);
      if ( !v116 )
        ATL::BaseAtlThrow(-2045247222);
      (*(void (__fastcall **)(__int64 *))(*v116 + 16))(v116);
      v101 = (*(__int64 (__fastcall **)(__int64 *, BOOL))(*v116 + 192))(v116, v97);
      if ( v101 == -2147024882 || v101 == -2045378032 || v101 == -2045312765 || v101 == -2045247216 )
        ATL::BaseAtlThrow(v101);
      if ( v101 < 0 )
        ATL::BaseAtlThrow(v101);
    }
    VariantClear(&pvarg);
    result = 0;
  }
  catch ( Base::Exception v112 )
  {
    LODWORD(v116) = v112[2];
    goto LABEL_300;
  }
  catch ( long v111 )
  {
    LODWORD(v116) = v111;
LABEL_300:
    result = (unsigned int)v116;
    if ( (_WORD)v116 == 534 )
      return 2249588993LL;
  }
  return result;
}

```

## disassembly

```asm
0x18050a950  mov     rax, rsp
0x18050a953  mov     [rax+8], rbx
0x18050a957  mov     [rax+18h], rsi
0x18050a95b  push    rdi
0x18050a95c  push    r12
0x18050a95e  push    r13
0x18050a960  push    r14
0x18050a962  push    r15
0x18050a964  sub     rsp, 0B0h
0x18050a96b  movaps  xmmword ptr [rax-38h], xmm6
0x18050a96f  mov     rbx, rdx
0x18050a972  mov     rdi, rcx
0x18050a975  xor     r14d, r14d
0x18050a978  test    rdx, rdx
0x18050a97b  jz      loc_18050C8BF
0x18050a981  mov     rcx, [rcx+80h]
0x18050a988  mov     rax, [rcx]
0x18050a98b  mov     rax, [rax+110h]
0x18050a992  call    cs:__guard_dispatch_icall_fptr
0x18050a998  test    eax, eax
0x18050a99a  js      loc_18050C8C9
0x18050a9a0  xorps   xmm0, xmm0
0x18050a9a3  xor     eax, eax
0x18050a9a5  movups  xmmword ptr [rsp+0D8h+pvarg], xmm0
0x18050a9aa  mov     qword ptr [rsp+0D8h+pvarg+10h], rax
0x18050a9af  lea     rcx, [rsp+0D8h+pvarg]; pvarg
0x18050a9b4  call    cs:__imp_VariantInit
0x18050a9ba  mov     rcx, [rdi+80h]
0x18050a9c1  mov     rax, [rcx]
0x18050a9c4  lea     r8, [rsp+0D8h+pvarg]
0x18050a9c9  mov     rdx, rbx
0x18050a9cc  mov     rax, [rax+60h]
0x18050a9d0  call    cs:__guard_dispatch_icall_fptr
0x18050a9d6  cmp     eax, 8007000Eh
0x18050a9db  jz      loc_18050CCDA
0x18050a9e1  mov     r13d, 86160210h
0x18050a9e7  cmp     eax, r13d
0x18050a9ea  jz      loc_18050CCDA
0x18050a9f0  mov     r12d, 86170103h
0x18050a9f6  cmp     eax, r12d
0x18050a9f9  jz      loc_18050CCDA
0x18050a9ff  mov     r15d, 86180110h
0x18050aa05  cmp     eax, r15d
0x18050aa08  jz      loc_18050CCDA
0x18050aa0e  test    eax, eax
0x18050aa10  js      loc_18050C8D4
0x18050aa16  or      esi, 0FFFFFFFFh
0x18050aa19  mov     [rsp+0D8h+cchCount2], esi; cchCount2
0x18050aa1d  lea     rax, aWhitebalance_0; "WhiteBalance"
0x18050aa24  mov     [rsp+0D8h+lpString2], rax; lpString2
0x18050aa29  mov     r9d, esi; cchCount1
0x18050aa2c  mov     r8, rbx; lpString1
0x18050aa2f  lea     edx, [rsi+2]; dwCmpFlags
0x18050aa32  lea     ecx, [rdx+7Eh]; Locale
0x18050aa35  call    cs:__imp_CompareStringW
0x18050aa3b  cmp     eax, 2
0x18050aa3e  jz      loc_18050C7C5
0x18050aa44  mov     [rsp+0D8h+cchCount2], esi; cchCount2
0x18050aa48  lea     rax, aBaselineexposu; "_BaselineExposure"
0x18050aa4f  mov     [rsp+0D8h+lpString2], rax; lpString2
0x18050aa54  mov     r9d, esi; cchCount1
0x18050aa57  mov     r8, rbx; lpString1
0x18050aa5a  lea     edx, [rsi+2]; dwCmpFlags
0x18050aa5d  lea     ecx, [rdx+7Eh]; Locale
0x18050aa60  call    cs:__imp_CompareStringW
0x18050aa66  cmp     eax, 2
0x18050aa69  jz      loc_18050C7C5
0x18050aa6f  mov     [rsp+0D8h+cchCount2], esi; cchCount2
0x18050aa73  lea     rax, aCameramatrix; "_CameraMatrix"
0x18050aa7a  mov     [rsp+0D8h+lpString2], rax; lpString2
0x18050aa7f  mov     r9d, esi; cchCount1
0x18050aa82  mov     r8, rbx; lpString1
0x18050aa85  lea     edx, [rsi+2]; dwCmpFlags
0x18050aa88  lea     ecx, [rdx+7Eh]; Locale
0x18050aa8b  call    cs:__imp_CompareStringW
0x18050aa91  cmp     eax, 2
0x18050aa94  jz      loc_18050C7C5
0x18050aa9a  mov     [rsp+0D8h+cchCount2], esi; cchCount2
0x18050aa9e  lea     rax, aGain; "Gain"
0x18050aaa5  mov     [rsp+0D8h+lpString2], rax; lpString2
0x18050aaaa  mov     r9d, esi; cchCount1
0x18050aaad  mov     r8, rbx; lpString1
0x18050aab0  lea     edx, [rsi+2]; dwCmpFlags
0x18050aab3  lea     ecx, [rdx+7Eh]; Locale
0x18050aab6  call    cs:__imp_CompareStringW
0x18050aabc  cmp     eax, 2
0x18050aabf  jz      loc_18050C7C5
0x18050aac5  mov     [rsp+0D8h+cchCount2], esi; cchCount2
0x18050aac9  lea     rax, aEnablewhitebal; "EnableWhiteBalance"
0x18050aad0  mov     [rsp+0D8h+lpString2], rax; lpString2
0x18050aad5  mov     r9d, esi; cchCount1
0x18050aad8  mov     r8, rbx; lpString1
0x18050aadb  lea     edx, [rsi+2]; dwCmpFlags
0x18050aade  lea     ecx, [rdx+7Eh]; Locale
0x18050aae1  call    cs:__imp_CompareStringW
0x18050aae7  cmp     eax, 2
0x18050aaea  jz      loc_18050C7C5
0x18050aaf0  mov     [rsp+0D8h+cchCount2], esi; cchCount2
0x18050aaf4  lea     rax, aHighlightrecov; "HighlightRecoveryCaptureOneCompliant"
0x18050aafb  mov     [rsp+0D8h+lpString2], rax; lpString2
0x18050ab00  mov     r9d, esi; cchCount1
0x18050ab03  mov     r8, rbx; lpString1
0x18050ab06  lea     edx, [rsi+2]; dwCmpFlags
0x18050ab09  lea     ecx, [rdx+7Eh]; Locale
0x18050ab0c  call    cs:__imp_CompareStringW
0x18050ab12  cmp     eax, 2
0x18050ab15  jz      loc_18050C7C5
0x18050ab1b  mov     [rsp+0D8h+cchCount2], esi; cchCount2
0x18050ab1f  lea     rax, aExposurecompen; "ExposureCompensation"
0x18050ab26  mov     [rsp+0D8h+lpString2], rax; lpString2
0x18050ab2b  mov     r9d, esi; cchCount1
0x18050ab2e  mov     r8, rbx; lpString1
0x18050ab31  lea     edx, [rsi+2]; dwCmpFlags
0x18050ab34  lea     ecx, [rdx+7Eh]; Locale
0x18050ab37  call    cs:__imp_CompareStringW
0x18050ab3d  cmp     eax, 2
0x18050ab40  jnz     loc_18050AE9E
0x18050ab46  mov     rcx, [rdi+90h]
0x18050ab4d  xorps   xmm6, xmm6
0x18050ab50  movsd   xmm0, qword ptr [rsp+0D8h+pvarg+8]
0x18050ab56  mov     [rsp+0D8h+arg_8], r14
0x18050ab5e  lea     r8, [rsp+0D8h+arg_8]
0x18050ab66  mov     rax, [rcx]
0x18050ab69  mov     rax, [rax+98h]
0x18050ab70  comisd  xmm0, xmm6
0x18050ab74  jbe     loc_18050AD0E
0x18050ab7a  lea     rdx, aExposurecurvee; "ExposureCurveEffect"
0x18050ab81  call    cs:__guard_dispatch_icall_fptr
0x18050ab87  test    eax, eax
0x18050ab89  js      loc_18050C8DB
0x18050ab8f  mov     rcx, [rsp+0D8h+arg_8]
0x18050ab97  test    rcx, rcx
0x18050ab9a  jz      loc_18050C8E2
0x18050aba0  mov     rax, [rcx]
0x18050aba3  mov     rax, [rax+10h]
0x18050aba7  call    cs:__guard_dispatch_icall_fptr
0x18050abad  mov     rcx, [rsp+0D8h+arg_8]
0x18050abb5  mov     rax, [rcx]
0x18050abb8  movups  xmm0, xmmword ptr [rsp+0D8h+pvarg]
0x18050abbd  movaps  xmmword ptr [rsp+0D8h+var_78], xmm0
0x18050abc2  movsd   xmm1, qword ptr [rsp+0D8h+pvarg+10h]
0x18050abc8  movsd   qword ptr [rsp+0D8h+var_78+10h], xmm1
0x18050abce  lea     r8, [rsp+0D8h+var_78]
0x18050abd3  mov     rdx, rbx
0x18050abd6  mov     rax, [rax+68h]
0x18050abda  call    cs:__guard_dispatch_icall_fptr
0x18050abe0  mov     esi, 8007000Eh
0x18050abe5  cmp     eax, esi
0x18050abe7  jz      loc_18050C919
0x18050abed  cmp     eax, r13d
0x18050abf0  jz      loc_18050C919
0x18050abf6  cmp     eax, r12d
0x18050abf9  jz      loc_18050C919
0x18050abff  cmp     eax, r15d
0x18050ac02  jz      loc_18050C919
0x18050ac08  test    eax, eax
0x18050ac0a  js      loc_18050C8EC
0x18050ac10  cmp     [rdi+0A0h], r14b
0x18050ac17  jnz     loc_18050ACFC
0x18050ac1d  mov     [rsp+0D8h+arg_8], r14
0x18050ac25  mov     rcx, [rdi+90h]
0x18050ac2c  mov     rax, [rcx]
0x18050ac2f  lea     r8, [rsp+0D8h+arg_8]
0x18050ac37  lea     rdx, aRawcoloreffect; "RawColorEffect"
0x18050ac3e  mov     rax, [rax+98h]
0x18050ac45  call    cs:__guard_dispatch_icall_fptr
0x18050ac4b  test    eax, eax
0x18050ac4d  js      loc_18050C8F3
0x18050ac53  mov     rcx, [rsp+0D8h+arg_8]
0x18050ac5b  test    rcx, rcx
0x18050ac5e  jz      loc_18050C8FA
0x18050ac64  mov     rax, [rcx]
0x18050ac67  mov     rax, [rax+10h]
0x18050ac6b  call    cs:__guard_dispatch_icall_fptr
0x18050ac71  mov     rcx, [rsp+0D8h+arg_8]
0x18050ac79  mov     rax, [rcx]
0x18050ac7c  mov     edx, 5
0x18050ac81  mov     word ptr [rsp+0D8h+var_78], dx
0x18050ac86  movsd   qword ptr [rsp+0D8h+var_78+8], xmm6
0x18050ac8c  movups  xmm0, xmmword ptr [rsp+0D8h+var_78]
0x18050ac91  movaps  [rsp+0D8h+var_58], xmm0
0x18050ac99  movsd   xmm1, qword ptr [rsp+0D8h+var_78+10h]
0x18050ac9f  movsd   [rsp+0D8h+var_48], xmm1
0x18050aca8  lea     r8, [rsp+0D8h+var_58]
0x18050acb0  mov     rdx, rbx
0x18050acb3  mov     rax, [rax+68h]
0x18050acb7  call    cs:__guard_dispatch_icall_fptr
0x18050acbd  mov     ebx, eax
0x18050acbf  lea     rcx, [rsp+0D8h+var_78]; pvarg
0x18050acc4  call    cs:__imp_VariantClear
0x18050acca  cmp     ebx, esi
0x18050accc  jz      loc_18050C912
0x18050acd2  cmp     ebx, r13d
0x18050acd5  jz      loc_18050C912
0x18050acdb  cmp     ebx, r12d
0x18050acde  jz      loc_18050C912
0x18050ace4  cmp     ebx, r15d
0x18050ace7  jz      loc_18050C912
0x18050aced  test    ebx, ebx
0x18050acef  js      loc_18050C904
0x18050acf5  mov     byte ptr [rdi+0A0h], 1
0x18050acfc  lea     rcx, [rsp+0D8h+pvarg]; pvarg
0x18050ad01  call    cs:__imp_VariantClear
0x18050ad07  xor     eax, eax
0x18050ad09  jmp     loc_18050C89D
0x18050ad0e  lea     rdx, aRawcoloreffect; "RawColorEffect"
0x18050ad15  call    cs:__guard_dispatch_icall_fptr
0x18050ad1b  test    eax, eax
0x18050ad1d  js      loc_18050C920
0x18050ad23  mov     rcx, [rsp+0D8h+arg_8]
0x18050ad2b  test    rcx, rcx
0x18050ad2e  jz      loc_18050C927
0x18050ad34  mov     rax, [rcx]
0x18050ad37  mov     rax, [rax+10h]
0x18050ad3b  call    cs:__guard_dispatch_icall_fptr
0x18050ad41  mov     rcx, [rsp+0D8h+arg_8]
0x18050ad49  mov     rax, [rcx]
0x18050ad4c  movups  xmm0, xmmword ptr [rsp+0D8h+pvarg]
0x18050ad51  movaps  [rsp+0D8h+var_58], xmm0
0x18050ad59  movsd   xmm1, qword ptr [rsp+0D8h+pvarg+10h]
0x18050ad5f  movsd   [rsp+0D8h+var_48], xmm1
0x18050ad68  lea     r8, [rsp+0D8h+var_58]
0x18050ad70  mov     rdx, rbx
0x18050ad73  mov     rax, [rax+68h]
0x18050ad77  call    cs:__guard_dispatch_icall_fptr
0x18050ad7d  mov     esi, 8007000Eh
0x18050ad82  cmp     eax, esi
0x18050ad84  jz      loc_18050C957
0x18050ad8a  cmp     eax, r13d
0x18050ad8d  jz      loc_18050C957
0x18050ad93  cmp     eax, r12d
0x18050ad96  jz      loc_18050C957
0x18050ad9c  cmp     eax, r15d
0x18050ad9f  jz      loc_18050C957
0x18050ada5  test    eax, eax
0x18050ada7  js      loc_18050C931
0x18050adad  cmp     [rdi+0A0h], r14b
0x18050adb4  jz      loc_18050ACFC
0x18050adba  mov     [rsp+0D8h+arg_8], r14
0x18050adc2  mov     rcx, [rdi+90h]
0x18050adc9  mov     rax, [rcx]
0x18050adcc  lea     r8, [rsp+0D8h+arg_8]
0x18050add4  lea     rdx, aExposurecurvee; "ExposureCurveEffect"
0x18050addb  mov     rax, [rax+98h]
0x18050ade2  call    cs:__guard_dispatch_icall_fptr
0x18050ade8  test    eax, eax
0x18050adea  js      loc_18050C938
0x18050adf0  mov     rcx, [rsp+0D8h+arg_8]
0x18050adf8  test    rcx, rcx
0x18050adfb  jz      loc_18050C93F
0x18050ae01  mov     rax, [rcx]
0x18050ae04  mov     rax, [rax+10h]
0x18050ae08  call    cs:__guard_dispatch_icall_fptr
0x18050ae0e  mov     rcx, [rsp+0D8h+arg_8]
0x18050ae16  mov     rax, [rcx]
0x18050ae19  mov     edx, 5
0x18050ae1e  mov     word ptr [rsp+0D8h+var_78], dx
0x18050ae23  movsd   qword ptr [rsp+0D8h+var_78+8], xmm6
0x18050ae29  movups  xmm0, xmmword ptr [rsp+0D8h+var_78]
0x18050ae2e  movaps  [rsp+0D8h+var_58], xmm0
0x18050ae36  movsd   xmm1, qword ptr [rsp+0D8h+var_78+10h]
0x18050ae3c  movsd   [rsp+0D8h+var_48], xmm1
0x18050ae45  lea     r8, [rsp+0D8h+var_58]
0x18050ae4d  mov     rdx, rbx
0x18050ae50  mov     rax, [rax+68h]
0x18050ae54  call    cs:__guard_dispatch_icall_fptr
0x18050ae5a  mov     ebx, eax
0x18050ae5c  lea     rcx, [rsp+0D8h+var_78]; pvarg
0x18050ae61  call    cs:__imp_VariantClear
0x18050ae67  cmp     ebx, esi
0x18050ae69  jz      loc_18050C950
0x18050ae6f  cmp     ebx, r13d
0x18050ae72  jz      loc_18050C950
0x18050ae78  cmp     ebx, r12d
0x18050ae7b  jz      loc_18050C950
0x18050ae81  cmp     ebx, r15d
0x18050ae84  jz      loc_18050C950
0x18050ae8a  test    ebx, ebx
0x18050ae8c  js      loc_18050C949
0x18050ae92  mov     [rdi+0A0h], r14b
0x18050ae99  jmp     loc_18050ACFC
0x18050ae9e  mov     [rsp+0D8h+cchCount2], esi; cchCount2
0x18050aea2  lea     rax, aSaturation; "Saturation"
0x18050aea9  mov     [rsp+0D8h+lpString2], rax; lpString2
0x18050aeae  mov     r9d, esi; cchCount1
0x18050aeb1  mov     r8, rbx; lpString1
0x18050aeb4  mov     edx, 1; dwCmpFlags
0x18050aeb9  lea     ecx, [rdx+7Eh]; Locale
0x18050aebc  call    cs:__imp_CompareStringW
0x18050aec2  cmp     eax, 2
0x18050aec5  jnz     loc_18050B21F
0x18050aecb  mov     rcx, [rdi+90h]
0x18050aed2  xorps   xmm6, xmm6
0x18050aed5  movsd   xmm0, qword ptr [rsp+0D8h+pvarg+8]
0x18050aedb  mov     [rsp+0D8h+arg_8], r14
0x18050aee3  lea     r8, [rsp+0D8h+arg_8]
0x18050aeeb  mov     rax, [rcx]
0x18050aeee  mov     rax, [rax+98h]
0x18050aef5  comisd  xmm0, xmm6
0x18050aef9  jbe     loc_18050B08F
  ... truncated ...
```
