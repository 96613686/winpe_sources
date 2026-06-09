# ComputationalPhotographyHelpers::RunTwoFrameTemporalDenoise(vt::CCompositeImg<vt::LumaType<uchar>,uchar> *,vt::CCompositeImg<vt::UVType<uchar>,vt::UVType<uchar>> *,vt::CCompositeImg<vt::LumaType<uchar>,uchar> *,vt::CCompositeImg<vt::UVType<uchar>,vt::UVType<uchar>> *,double &,DXGI_COLOR_SPACE_TYPE,int,float,ImageFusionSettings *)

- ea: `0x180035464`
- end: `0x180035b81`
- name: `?RunTwoFrameTemporalDenoise@ComputationalPhotographyHelpers@@YA?AW4FusionResult@1@PEAV?$CCompositeImg@V?$LumaType@E@vt@@E@vt@@PEAV?$CCompositeImg@V?$UVType@E@vt@@V12@@4@01AEANW4DXGI_COLOR_SPACE_TYPE@@HMPEAUImageFusionSettings@@@Z`
- size: `1821`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180136d1c`

## callees

- `0x180001850`
- `0x1800018a0`
- `0x180002420`
- `0x18000290c`
- `0x180002fb0`
- `0x180002fd4`
- `0x180003094`
- `0x18002adc0`
- `0x180031598`
- `0x1800319a0`
- `0x180032ba4`
- `0x180032c08`
- `0x180032c6c`
- `0x180032f08`
- `0x180033380`
- `0x1800338c0`
- `0x180034114`
- `0x180035464`
- `0x1800814d4`
- `0x180082544`
- `0x180085384`
- `0x1800b6f90`
- `0x1800b708c`
- `0x1800d682c`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoTransformError` at `0x18003567c`
- `api-ms-win-core-winrt-error-l1-1-0!RoTransformError` at `0x18003574c`
- `api-ms-win-core-winrt-error-l1-1-0!RoTransformError` at `0x180035a46`
- `api-ms-win-core-winrt-error-l1-1-0!RoTransformError` at `0x18003567c`
- `api-ms-win-core-winrt-error-l1-1-0!RoTransformError` at `0x18003574c`
- `api-ms-win-core-winrt-error-l1-1-0!RoTransformError` at `0x180035a46`
- `api-ms-win-core-processthreads-l1-1-1!IsProcessorFeaturePresent` at `0x1800354b3`
- `api-ms-win-core-processthreads-l1-1-1!IsProcessorFeaturePresent` at `0x1800354c6`
- `api-ms-win-core-processthreads-l1-1-1!IsProcessorFeaturePresent` at `0x1800354b3`
- `api-ms-win-core-processthreads-l1-1-1!IsProcessorFeaturePresent` at `0x1800354c6`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall ComputationalPhotographyHelpers::RunTwoFrameTemporalDenoise(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        double *a5,
        DXGI_COLOR_SPACE_TYPE a6)
{
  __int64 v10; // rcx
  int v11; // esi
  int v12; // ebx
  int v13; // eax
  double v14; // xmm6_8
  double v15; // xmm0_8
  __int64 v16; // rcx
  int v17; // r13d
  unsigned int v19; // ebx
  __int64 v20; // rsi
  unsigned int v21; // ebx
  __int64 v22; // rcx
  int v23; // eax
  int v24; // ebx
  int v25; // ecx
  ComputationalPhotographyHelpers::ImageFusion *v26; // rax
  ComputationalPhotographyHelpers::ImageFusion *v27; // rbx
  int v28; // eax
  unsigned int v29; // edx
  int v30; // esi
  bool v31; // zf
  __int64 v32; // rcx
  int v33; // r8d
  int v34; // r9d
  __int64 v35; // rcx
  __int64 v36; // rcx
  __int64 v37; // rcx
  __int64 v38; // rcx
  __int64 v39; // rcx
  __int64 v40; // rcx
  int v41; // eax
  __int64 v42; // rcx
  __int64 v43; // rcx
  bool v44[8]; // [rsp+68h] [rbp-A0h] BYREF
  double *pExceptionObject; // [rsp+70h] [rbp-98h] BYREF
  __int64 v46[7]; // [rsp+78h] [rbp-90h] BYREF
  void **v47; // [rsp+B0h] [rbp-58h] BYREF
  int v48; // [rsp+BCh] [rbp-4Ch]
  int v49; // [rsp+C0h] [rbp-48h]
  unsigned __int8 *v50; // [rsp+C8h] [rbp-40h]
  int v51; // [rsp+D0h] [rbp-38h]
  _QWORD v52[3]; // [rsp+E8h] [rbp-20h] BYREF
  unsigned __int8 *v53; // [rsp+100h] [rbp-8h]
  int v54; // [rsp+108h] [rbp+0h]
  __int64 v55[7]; // [rsp+120h] [rbp+18h] BYREF
  _QWORD v56[7]; // [rsp+158h] [rbp+50h] BYREF
  ComputationalPhotographyHelpers::ImageFusion *v57; // [rsp+190h] [rbp+88h] BYREF
  int v58; // [rsp+198h] [rbp+90h]
  int v59; // [rsp+19Ch] [rbp+94h]

  pExceptionObject = a5;
  if ( !IsProcessorFeaturePresent(0xAu) || !IsProcessorFeaturePresent(6u) )
    return 3;
  if ( (unsigned int)dword_18015F098 > 5 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v10,
      byte_180151809);
  v11 = *(_DWORD *)(a1 + 16);
  v12 = *(_DWORD *)(a1 + 12);
  v13 = v12;
  if ( v12 >= v11 )
    v13 = *(_DWORD *)(a1 + 16);
  v14 = o_log_0((double)v13);
  v15 = o_log_0(2.0);
  v17 = (int)floor(v14 / v15);
  if ( v17 < 4 )
    v17 = 4;
  v44[0] = 0;
  if ( (unsigned int)dword_18015F098 > 5 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v16,
      &word_180151A9E);
  vt::CCompositeImg<vt::LumaType<unsigned char>,unsigned char>::CCompositeImg<vt::LumaType<unsigned char>,unsigned char>(
    v46,
    *(unsigned int *)(a1 + 12),
    *(unsigned int *)(a1 + 16));
  if ( !v46[3] )
    goto LABEL_12;
  v19 = v12 / 2;
  v20 = (unsigned int)(v11 / 2);
  vt::CCompositeImg<vt::UVType<unsigned char>,vt::UVType<unsigned char>>::CCompositeImg<vt::UVType<unsigned char>,vt::UVType<unsigned char>>(
    v55,
    v19,
    v20);
  if ( !v55[3] )
  {
LABEL_14:
    v55[0] = (__int64)&vt::CTypedImg<int>::`vftable';
    vt::CImg::~CImg((vt::CImg *)v55);
LABEL_12:
    v46[0] = (__int64)&vt::CTypedImg<int>::`vftable';
    vt::CImg::~CImg((vt::CImg *)v46);
    return 2;
  }
  vt::CCompositeImg<vt::LumaType<unsigned char>,unsigned char>::CCompositeImg<vt::LumaType<unsigned char>,unsigned char>(
    v52,
    *(unsigned int *)(a1 + 12),
    *(unsigned int *)(a1 + 16));
  if ( !v53 )
  {
LABEL_16:
    v52[0] = &vt::CTypedImg<int>::`vftable';
    vt::CImg::~CImg((vt::CImg *)v52);
    goto LABEL_14;
  }
  vt::CCompositeImg<vt::LumaType<unsigned char>,unsigned char>::CCompositeImg<vt::LumaType<unsigned char>,unsigned char>(
    &v47,
    v19,
    (unsigned int)v20);
  if ( !v50 )
  {
    v47 = &vt::CTypedImg<int>::`vftable';
    vt::CImg::~CImg((vt::CImg *)&v47);
    goto LABEL_16;
  }
  vt::CTypedImg<unsigned char>::CTypedImg<unsigned char>(v56, v19, (unsigned int)v20);
  if ( !v56[3] )
  {
    v21 = 2;
LABEL_87:
    v56[0] = &vt::CTypedImg<int>::`vftable';
    vt::CImg::~CImg((vt::CImg *)v56);
    v47 = &vt::CTypedImg<int>::`vftable';
    vt::CImg::~CImg((vt::CImg *)&v47);
    v52[0] = &vt::CTypedImg<int>::`vftable';
    vt::CImg::~CImg((vt::CImg *)v52);
    v55[0] = (__int64)&vt::CTypedImg<int>::`vftable';
    vt::CImg::~CImg((vt::CImg *)v55);
    v46[0] = (__int64)&vt::CTypedImg<int>::`vftable';
    vt::CImg::~CImg((vt::CImg *)v46);
    return v21;
  }
  v22 = (unsigned int)(a6 - 5);
  if ( a6 != DXGI_COLOR_SPACE_YCBCR_FULL_G22_NONE_P709_X601 )
  {
    v22 = (unsigned int)(a6 - 6);
    if ( a6 != DXGI_COLOR_SPACE_YCBCR_STUDIO_G22_LEFT_P601 )
    {
      v22 = (unsigned int)(a6 - 7);
      if ( a6 != DXGI_COLOR_SPACE_YCBCR_FULL_G22_LEFT_P601 )
      {
        v22 = (unsigned int)(a6 - 8);
        if ( (unsigned int)v22 >= 2 )
        {
          v23 = MF::OriginateError<20>(v22, L"Invalid color space");
          v24 = v23;
          if ( v23 < 0 )
          {
            RoTransformError((unsigned int)v23, 0, 0);
            v25 = 0;
LABEL_85:
            v31 = v24 == -2147024882;
            goto LABEL_86;
          }
        }
      }
    }
  }
  if ( (unsigned int)dword_18015F098 > 5 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v22,
      &byte_180152077);
  if ( (unsigned int)dword_18015F098 > 5 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v22,
      qword_180151940);
  v26 = (ComputationalPhotographyHelpers::ImageFusion *)operator new(
                                                          0x73A0u,
                                                          (const struct std::nothrow_t *)&std::nothrow);
  v57 = v26;
  if ( v26 )
    v27 = (ComputationalPhotographyHelpers::ImageFusion *)ComputationalPhotographyHelpers::ImageFusion::ImageFusion(v26);
  else
    v27 = 0;
  if ( !v27 )
  {
    LODWORD(pExceptionObject) = 2;
    throw (ErrorCode *)&pExceptionObject;
  }
  v28 = ComputationalPhotographyHelpers::ImageFusion::FusionTemporalDenoising(
          v27,
          a4,
          (__int64)v46,
          (__int64)v55,
          (struct vt::CImg *)v52,
          a6,
          v17,
          v44,
          pExceptionObject);
  v30 = v28;
  if ( v28 < 0 )
  {
    RoTransformError((unsigned int)v28, 0, 0);
    v25 = 0;
    v31 = v30 == -2147024882;
LABEL_86:
    LOBYTE(v25) = !v31;
    v21 = v25 + 2;
    goto LABEL_87;
  }
  ComputationalPhotographyHelpers::ImageFusion::`scalar deleting destructor'(v27, v29);
  if ( (unsigned int)dword_18015F098 > 5 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v32,
      qword_180151EE8);
  if ( !v44[0] )
  {
    if ( (unsigned int)dword_18015F098 > 5 )
    {
      LODWORD(pExceptionObject) = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        v32,
        (unsigned int)&byte_180151CF7,
        v33,
        v34,
        (__int64)&pExceptionObject);
    }
    if ( (unsigned int)dword_18015F098 > 5 )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        v32,
        byte_180151B31);
    v21 = 1;
    goto LABEL_87;
  }
  if ( (unsigned int)dword_18015F098 > 5 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v32,
      &byte_180151B67);
  pExceptionObject = 0;
  v57 = 0;
  v58 = v48;
  v59 = v49;
  v24 = vt::VtSeparableFilterBoxDecimate2to1(&v47, &v57, v52, 0);
  if ( v24 < 0 )
    goto LABEL_84;
  if ( (unsigned int)dword_18015F098 > 5 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v35,
      byte_180151A21);
  if ( (unsigned int)dword_18015F098 > 5 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v35,
      word_180151DCA);
  v24 = ComputationalPhotographyHelpers::ApplyThreshold(&v47);
  if ( v24 < 0 )
    goto LABEL_84;
  if ( (unsigned int)dword_18015F098 > 5 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v36,
      byte_180151F79);
  if ( (unsigned int)dword_18015F098 > 5 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v36,
      &word_180152016);
  v24 = ComputationalPhotographyHelpers::ManhattanDistanceTransform<unsigned char>(v56, &v47);
  if ( v24 < 0 )
    goto LABEL_84;
  if ( (unsigned int)dword_18015F098 > 5 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v37,
      qword_180151C20);
  if ( (unsigned int)dword_18015F098 > 5 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v37,
      byte_180151CB9);
  v24 = ComputationalPhotographyHelpers::ComputeBlendWeights<unsigned char>(&v47, v56);
  if ( v24 < 0 )
    goto LABEL_84;
  if ( (unsigned int)dword_18015F098 > 5 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v38,
      byte_180151C7B);
  if ( (unsigned int)dword_18015F098 > 5 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v38,
      byte_180151E51);
  v24 = ComputationalPhotographyHelpers::ImageFusion::BlurAndScaleX2MultiThreaded(v50, 2 * v48, 2 * v49, v51, v53, v54);
  if ( v24 < 0 )
    goto LABEL_84;
  if ( (unsigned int)dword_18015F098 > 5 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v39,
      byte_180151745);
  if ( (unsigned int)dword_18015F098 > 5 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v39,
      &dword_180151E8C);
  v44[0] = 1;
  v24 = ComputationalPhotographyHelpers::CompareMotionBlur(v44, a3, v46, v52);
  if ( v24 < 0 )
    goto LABEL_84;
  if ( (unsigned int)dword_18015F098 > 5 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v40,
      &dword_180151BE4);
  if ( (unsigned int)dword_18015F098 > 5 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v40,
      byte_180151871);
  v41 = v44[0]
      ? ComputationalPhotographyHelpers::MaskedAverage(a1, a2, a3, a4, (__int64)v46, (__int64)v55, (__int64)v52)
      : ComputationalPhotographyHelpers::MaskedAverage(
          a1,
          a2,
          (unsigned int)v46,
          (unsigned int)v55,
          a3,
          a4,
          (__int64)v52);
  v24 = v41;
  if ( v41 < 0 )
    goto LABEL_84;
  if ( (unsigned int)dword_18015F098 > 5 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v42,
      &dword_1801519B4);
  v24 = vt::CImg::Clear((vt::CImg *)v46, 0);
  if ( v24 < 0 || (v24 = vt::CImg::Clear((vt::CImg *)v55, 0), v24 < 0) )
  {
LABEL_84:
    RoTransformError((unsigned int)v24, 0, 0);
    v25 = 0;
    goto LABEL_85;
  }
  if ( (unsigned int)dword_18015F098 > 5 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v43,
      qword_180151780);
  v56[0] = &vt::CTypedImg<int>::`vftable';
  vt::CImg::~CImg((vt::CImg *)v56);
  v47 = &vt::CTypedImg<int>::`vftable';
  vt::CImg::~CImg((vt::CImg *)&v47);
  v52[0] = &vt::CTypedImg<int>::`vftable';
  vt::CImg::~CImg((vt::CImg *)v52);
  v55[0] = (__int64)&vt::CTypedImg<int>::`vftable';
  vt::CImg::~CImg((vt::CImg *)v55);
  v46[0] = (__int64)&vt::CTypedImg<int>::`vftable';
  vt::CImg::~CImg((vt::CImg *)v46);
  return 0;
}

```

## disassembly

```asm
0x180035464  mov     rax, rsp
0x180035467  push    rbp
0x180035468  push    rbx
0x180035469  push    rsi
0x18003546a  push    rdi
0x18003546b  push    r12
0x18003546d  push    r13
0x18003546f  push    r14
0x180035471  push    r15
0x180035473  lea     rbp, [rax-0F8h]
0x18003547a  sub     rsp, 1B8h
0x180035481  movaps  xmmword ptr [rax-58h], xmm6
0x180035485  mov     rax, cs:__security_cookie
0x18003548c  xor     rax, rsp
0x18003548f  mov     qword ptr [rbp+0F0h+var_58], rax
0x180035496  mov     r12, r9
0x180035499  mov     r14, r8
0x18003549c  mov     r15, rdx
0x18003549f  mov     rdi, rcx
0x1800354a2  mov     rax, [rbp+0F0h+arg_20]
0x1800354a9  mov     [rsp+1F0h+pExceptionObject], rax
0x1800354ae  mov     ecx, 0Ah; ProcessorFeature
0x1800354b3  call    cs:__imp_IsProcessorFeaturePresent
0x1800354b9  test    eax, eax
0x1800354bb  jz      loc_180035B36
0x1800354c1  mov     ecx, 6; ProcessorFeature
0x1800354c6  call    cs:__imp_IsProcessorFeaturePresent
0x1800354cc  test    eax, eax
0x1800354ce  jz      loc_180035B36
0x1800354d4  mov     eax, cs:dword_18015F098
0x1800354da  cmp     eax, 5
0x1800354dd  jbe     short loc_1800354EB
0x1800354df  lea     rdx, byte_180151809
0x1800354e6  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800354eb  mov     esi, [rdi+10h]
0x1800354ee  mov     ebx, [rdi+0Ch]
0x1800354f1  mov     eax, ebx
0x1800354f3  cmp     ebx, esi
0x1800354f5  cmovge  eax, esi
0x1800354f8  movd    xmm0, eax
0x1800354fc  cvtdq2pd xmm0, xmm0; X
0x180035500  call    _o_log_0
0x180035505  movaps  xmm6, xmm0
0x180035508  movsd   xmm0, cs:__real@4000000000000000; X
0x180035510  call    _o_log_0
0x180035515  divsd   xmm6, xmm0
0x180035519  movaps  xmm0, xmm6; X
0x18003551c  call    floor
0x180035521  cvttsd2si r13d, xmm0
0x180035526  mov     eax, 4
0x18003552b  cmp     r13d, eax
0x18003552e  cmovl   r13d, eax
0x180035532  mov     [rsp+1F0h+var_190], 0
0x180035537  mov     eax, cs:dword_18015F098
0x18003553d  cmp     eax, 5
0x180035540  jbe     short loc_18003554E
0x180035542  lea     rdx, word_180151A9E
0x180035549  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18003554e  mov     r8d, [rdi+10h]
0x180035552  mov     edx, [rdi+0Ch]
0x180035555  lea     rcx, [rsp+1F0h+var_180]
0x18003555a  call    ??0?$CCompositeImg@V?$LumaType@E@vt@@E@vt@@QEAA@HHW4AlignMode@1@@Z; vt::CCompositeImg<vt::LumaType<uchar>,uchar>::CCompositeImg<vt::LumaType<uchar>,uchar>(int,int,vt::AlignMode)
0x18003555f  nop
0x180035560  cmp     [rbp+0F0h+var_168], 0
0x180035565  jnz     short loc_180035587
0x180035567  lea     rdi, ??_7?$CTypedImg@H@vt@@6B@; const vt::CTypedImg<int>::`vftable'
0x18003556e  mov     [rsp+1F0h+var_180], rdi
0x180035573  lea     rcx, [rsp+1F0h+var_180]; this
0x180035578  call    ??1CImg@vt@@UEAA@XZ; vt::CImg::~CImg(void)
0x18003557d  mov     eax, 2
0x180035582  jmp     loc_180035B3B
0x180035587  mov     eax, ebx
0x180035589  cdq
0x18003558a  sub     eax, edx
0x18003558c  sar     eax, 1
0x18003558e  mov     ebx, eax
0x180035590  mov     eax, esi
0x180035592  cdq
0x180035593  sub     eax, edx
0x180035595  sar     eax, 1
0x180035597  mov     esi, eax
0x180035599  mov     r8d, eax
0x18003559c  mov     edx, ebx
0x18003559e  lea     rcx, [rbp+0F0h+var_D8]
0x1800355a2  call    ??0?$CCompositeImg@V?$UVType@E@vt@@V12@@vt@@QEAA@HHW4AlignMode@1@@Z; vt::CCompositeImg<vt::UVType<uchar>,vt::UVType<uchar>>::CCompositeImg<vt::UVType<uchar>,vt::UVType<uchar>>(int,int,vt::AlignMode)
0x1800355a7  nop
0x1800355a8  cmp     [rbp+0F0h+var_C0], 0
0x1800355ad  jnz     short loc_1800355C6
0x1800355af  lea     rdi, ??_7?$CTypedImg@H@vt@@6B@; const vt::CTypedImg<int>::`vftable'
0x1800355b6  mov     [rbp+0F0h+var_D8], rdi
0x1800355ba  lea     rcx, [rbp+0F0h+var_D8]; this
0x1800355be  call    ??1CImg@vt@@UEAA@XZ; vt::CImg::~CImg(void)
0x1800355c3  nop
0x1800355c4  jmp     short loc_18003556E
0x1800355c6  mov     r8d, [rdi+10h]
0x1800355ca  mov     edx, [rdi+0Ch]
0x1800355cd  lea     rcx, [rbp+0F0h+var_110]
0x1800355d1  call    ??0?$CCompositeImg@V?$LumaType@E@vt@@E@vt@@QEAA@HHW4AlignMode@1@@Z; vt::CCompositeImg<vt::LumaType<uchar>,uchar>::CCompositeImg<vt::LumaType<uchar>,uchar>(int,int,vt::AlignMode)
0x1800355d6  nop
0x1800355d7  cmp     [rbp+0F0h+var_F8], 0
0x1800355dc  jnz     short loc_1800355F5
0x1800355de  lea     rdi, ??_7?$CTypedImg@H@vt@@6B@; const vt::CTypedImg<int>::`vftable'
0x1800355e5  mov     [rbp+0F0h+var_110], rdi
0x1800355e9  lea     rcx, [rbp+0F0h+var_110]; this
0x1800355ed  call    ??1CImg@vt@@UEAA@XZ; vt::CImg::~CImg(void)
0x1800355f2  nop
0x1800355f3  jmp     short loc_1800355B6
0x1800355f5  mov     r8d, esi
0x1800355f8  mov     edx, ebx
0x1800355fa  lea     rcx, [rbp+0F0h+var_148]
0x1800355fe  call    ??0?$CCompositeImg@V?$LumaType@E@vt@@E@vt@@QEAA@HHW4AlignMode@1@@Z; vt::CCompositeImg<vt::LumaType<uchar>,uchar>::CCompositeImg<vt::LumaType<uchar>,uchar>(int,int,vt::AlignMode)
0x180035603  nop
0x180035604  cmp     [rbp+0F0h+var_130], 0
0x180035609  jnz     short loc_180035622
0x18003560b  lea     rdi, ??_7?$CTypedImg@H@vt@@6B@; const vt::CTypedImg<int>::`vftable'
0x180035612  mov     [rbp+0F0h+var_148], rdi
0x180035616  lea     rcx, [rbp+0F0h+var_148]; this
0x18003561a  call    ??1CImg@vt@@UEAA@XZ; vt::CImg::~CImg(void)
0x18003561f  nop
0x180035620  jmp     short loc_1800355E5
0x180035622  mov     r8d, esi
0x180035625  mov     edx, ebx
0x180035627  lea     rcx, [rbp+0F0h+var_A0]
0x18003562b  call    ??0?$CTypedImg@E@vt@@QEAA@HHHW4AlignMode@1@@Z; vt::CTypedImg<uchar>::CTypedImg<uchar>(int,int,int,vt::AlignMode)
0x180035630  nop
0x180035631  cmp     [rbp+0F0h+var_88], 0
0x180035636  jnz     short loc_180035642
0x180035638  mov     ebx, 2
0x18003563d  jmp     loc_1800357CB
0x180035642  mov     esi, [rbp+0F0h+arg_28]
0x180035648  mov     ecx, esi
0x18003564a  sub     ecx, 5
0x18003564d  jz      short loc_18003568A
0x18003564f  sub     ecx, 1
0x180035652  jz      short loc_18003568A
0x180035654  sub     ecx, 1
0x180035657  jz      short loc_18003568A
0x180035659  sub     ecx, 1
0x18003565c  jz      short loc_18003568A
0x18003565e  cmp     ecx, 1
0x180035661  jz      short loc_18003568A
0x180035663  lea     rdx, aInvalidColorSp; "Invalid color space"
0x18003566a  call    ??$OriginateError@$0BE@@MF@@YAJJAEAY0BE@$$CBG@Z; MF::OriginateError<20>(long,ushort const (&)[20])
0x18003566f  mov     ebx, eax
0x180035671  test    eax, eax
0x180035673  jns     short loc_18003568A
0x180035675  xor     r8d, r8d
0x180035678  xor     edx, edx
0x18003567a  mov     ecx, eax
0x18003567c  call    cs:__imp_RoTransformError
0x180035682  nop
0x180035683  xor     ecx, ecx
0x180035685  jmp     loc_180035A50
0x18003568a  mov     eax, cs:dword_18015F098
0x180035690  cmp     eax, 5
0x180035693  jbe     short loc_1800356A1
0x180035695  lea     rdx, byte_180152077
0x18003569c  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800356a1  mov     eax, cs:dword_18015F098
0x1800356a7  cmp     eax, 5
0x1800356aa  jbe     short loc_1800356B8
0x1800356ac  lea     rdx, qword_180151940
0x1800356b3  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800356b8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800356bf  mov     ecx, 73A0h; unsigned __int64
0x1800356c4  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800356c9  mov     [rbp+0F0h+var_68], rax
0x1800356d0  test    rax, rax
0x1800356d3  jz      short loc_1800356E2
0x1800356d5  mov     rcx, rax; this
0x1800356d8  call    ??0ImageFusion@ComputationalPhotographyHelpers@@QEAA@XZ; ComputationalPhotographyHelpers::ImageFusion::ImageFusion(void)
0x1800356dd  mov     rbx, rax
0x1800356e0  jmp     short loc_1800356E4
0x1800356e2  xor     ebx, ebx
0x1800356e4  test    rbx, rbx
0x1800356e7  jz      loc_180035B66
0x1800356ed  mov     rax, [rsp+1F0h+pExceptionObject]
0x1800356f2  mov     [rsp+1F0h+var_198], rax; double *
0x1800356f7  lea     rax, [rsp+1F0h+var_190]
0x1800356fc  mov     [rsp+1F0h+var_1A0], rax; bool *
0x180035701  mov     [rsp+1F0h+var_1A8], r13d; int
0x180035706  mov     [rsp+1F0h+var_1B0], esi; DXGI_COLOR_SPACE_TYPE
0x18003570a  lea     rax, [rbp+0F0h+var_110]
0x18003570e  mov     [rsp+1F0h+var_1B8], rax; struct vt::CImg *
0x180035713  lea     rax, [rbp+0F0h+var_D8]
0x180035717  mov     [rsp+1F0h+var_1C0], rax; __int64
0x18003571c  lea     rax, [rsp+1F0h+var_180]
0x180035721  mov     [rsp+1F0h+var_1C8], rax; __int64
0x180035726  mov     [rsp+1F0h+var_1D0], r12; __int64
0x18003572b  mov     r9, r14
0x18003572e  mov     r8, r15
0x180035731  mov     rdx, rdi
0x180035734  mov     rcx, rbx; this
0x180035737  call    ?FusionTemporalDenoising@ImageFusion@ComputationalPhotographyHelpers@@QEAAJPEAV?$CCompositeImg@V?$LumaType@E@vt@@E@vt@@PEAV?$CCompositeImg@V?$UVType@E@vt@@V12@@4@01010W4DXGI_COLOR_SPACE_TYPE@@HAEA_NAEAN@Z; ComputationalPhotographyHelpers::ImageFusion::FusionTemporalDenoising(vt::CCompositeImg<vt::LumaType<uchar>,uchar> *,vt::CCompositeImg<vt::UVType<uchar>,vt::UVType<uchar>> *,vt::CCompositeImg<vt::LumaType<uchar>,uchar> *,vt::CCompositeImg<vt::UVType<uchar>,vt::UVType<uchar>> *,vt::CCompositeImg<vt::LumaType<uchar>,uchar> *,vt::CCompositeImg<vt::UVType<uchar>,vt::UVType<uchar>> *,vt::CCompositeImg<vt::LumaType<uchar>,uchar> *,DXGI_COLOR_SPACE_TYPE,int,bool &,double &)
0x18003573c  mov     esi, eax
0x18003573e  xor     r13d, r13d
0x180035741  test    eax, eax
0x180035743  jns     short loc_180035761
0x180035745  xor     r8d, r8d
0x180035748  xor     edx, edx
0x18003574a  mov     ecx, eax
0x18003574c  call    cs:__imp_RoTransformError
0x180035752  nop
0x180035753  mov     ecx, r13d
0x180035756  cmp     esi, 8007000Eh
0x18003575c  jmp     loc_180035A56
0x180035761  mov     rcx, rbx; this
0x180035764  call    ??_GImageFusion@ComputationalPhotographyHelpers@@QEAAPEAXI@Z; ComputationalPhotographyHelpers::ImageFusion::`scalar deleting destructor'(uint)
0x180035769  mov     eax, cs:dword_18015F098
0x18003576f  mov     esi, 5
0x180035774  cmp     eax, esi
0x180035776  jbe     short loc_180035784
0x180035778  lea     rdx, qword_180151EE8
0x18003577f  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180035784  mov     eax, cs:dword_18015F098
0x18003578a  cmp     [rsp+1F0h+var_190], r13b
0x18003578f  jnz     short loc_1800357D0
0x180035791  cmp     eax, esi
0x180035793  jbe     short loc_1800357B0
0x180035795  mov     dword ptr [rsp+1F0h+pExceptionObject], r13d
0x18003579a  lea     rax, [rsp+1F0h+pExceptionObject]
0x18003579f  mov     [rsp+1F0h+var_1D0], rax
0x1800357a4  lea     rdx, byte_180151CF7
0x1800357ab  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800357b0  mov     eax, cs:dword_18015F098
0x1800357b6  cmp     eax, esi
0x1800357b8  jbe     short loc_1800357C6
0x1800357ba  lea     rdx, byte_180151B31
0x1800357c1  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800357c6  mov     ebx, 1
0x1800357cb  jmp     loc_180035A60
0x1800357d0  cmp     eax, esi
0x1800357d2  jbe     short loc_1800357E0
0x1800357d4  lea     rdx, byte_180151B67
0x1800357db  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800357e0  mov     [rsp+1F0h+pExceptionObject], r13
0x1800357e5  mov     eax, [rbp+0F0h+var_13C]
0x1800357e8  mov     ecx, [rbp+0F0h+var_138]
0x1800357eb  mov     [rbp+0F0h+var_68], r13
0x1800357f2  mov     [rbp+0F0h+var_60], eax
0x1800357f8  mov     [rbp+0F0h+var_5C], ecx
0x1800357fe  mov     r9, r13
0x180035801  lea     r8, [rbp+0F0h+var_110]
0x180035805  lea     rdx, [rbp+0F0h+var_68]
0x18003580c  lea     rcx, [rbp+0F0h+var_148]
0x180035810  call    ?VtSeparableFilterBoxDecimate2to1@vt@@YAJAEAVCImg@1@AEBVCRect@1@AEBV21@VCPoint@1@@Z; vt::VtSeparableFilterBoxDecimate2to1(vt::CImg &,vt::CRect const &,vt::CImg const &,vt::CPoint)
0x180035815  mov     ebx, eax
0x180035817  test    eax, eax
0x180035819  js      loc_180035A3F
0x18003581f  mov     eax, cs:dword_18015F098
0x180035825  cmp     eax, esi
0x180035827  jbe     short loc_180035835
0x180035829  lea     rdx, byte_180151A21
0x180035830  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180035835  mov     eax, cs:dword_18015F098
0x18003583b  cmp     eax, esi
0x18003583d  jbe     short loc_18003584B
0x18003583f  lea     rdx, word_180151DCA
0x180035846  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18003584b  lea     rcx, [rbp+0F0h+var_148]
0x18003584f  call    ?ApplyThreshold@ComputationalPhotographyHelpers@@YAJAEAV?$CCompositeImg@V?$LumaType@E@vt@@E@vt@@E@Z; ComputationalPhotographyHelpers::ApplyThreshold(vt::CCompositeImg<vt::LumaType<uchar>,uchar> &,uchar)
0x180035854  mov     ebx, eax
0x180035856  test    eax, eax
0x180035858  js      loc_180035A3F
0x18003585e  mov     eax, cs:dword_18015F098
0x180035864  cmp     eax, esi
0x180035866  jbe     short loc_180035874
0x180035868  lea     rdx, byte_180151F79
0x18003586f  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180035874  mov     eax, cs:dword_18015F098
0x18003587a  cmp     eax, esi
0x18003587c  jbe     short loc_18003588A
0x18003587e  lea     rdx, word_180152016
0x180035885  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18003588a  lea     rdx, [rbp+0F0h+var_148]
0x18003588e  lea     rcx, [rbp+0F0h+var_A0]
0x180035892  call    ??$ManhattanDistanceTransform@E@ComputationalPhotographyHelpers@@YAJAEAV?$CTypedImg@E@vt@@AEBV?$CCompositeImg@V?$LumaType@E@vt@@E@2@@Z; ComputationalPhotographyHelpers::ManhattanDistanceTransform<uchar>(vt::CTypedImg<uchar> &,vt::CCompositeImg<vt::LumaType<uchar>,uchar> const &)
0x180035897  mov     ebx, eax
0x180035899  test    eax, eax
0x18003589b  js      loc_180035A3F
0x1800358a1  mov     eax, cs:dword_18015F098
0x1800358a7  cmp     eax, esi
0x1800358a9  jbe     short loc_1800358B7
0x1800358ab  lea     rdx, qword_180151C20
0x1800358b2  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800358b7  mov     eax, cs:dword_18015F098
0x1800358bd  cmp     eax, esi
0x1800358bf  jbe     short loc_1800358CD
0x1800358c1  lea     rdx, byte_180151CB9
0x1800358c8  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800358cd  lea     rdx, [rbp+0F0h+var_A0]
0x1800358d1  lea     rcx, [rbp+0F0h+var_148]
0x1800358d5  call    ??$ComputeBlendWeights@E@ComputationalPhotographyHelpers@@YAJAEAV?$CCompositeImg@V?$LumaType@E@vt@@E@vt@@AEBV?$CTypedImg@E@2@EE@Z; ComputationalPhotographyHelpers::ComputeBlendWeights<uchar>(vt::CCompositeImg<vt::LumaType<uchar>,uchar> &,vt::CTypedImg<uchar> const &,uchar,uchar)
0x1800358da  mov     ebx, eax
0x1800358dc  test    eax, eax
0x1800358de  js      loc_180035A3F
0x1800358e4  mov     eax, cs:dword_18015F098
0x1800358ea  cmp     eax, esi
0x1800358ec  jbe     short loc_1800358FA
0x1800358ee  lea     rdx, byte_180151C7B
  ... truncated ...
```
