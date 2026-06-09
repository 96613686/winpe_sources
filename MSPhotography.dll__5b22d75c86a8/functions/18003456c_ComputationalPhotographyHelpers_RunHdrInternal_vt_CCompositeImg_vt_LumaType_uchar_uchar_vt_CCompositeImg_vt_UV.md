# ComputationalPhotographyHelpers::RunHdrInternal(vt::CCompositeImg<vt::LumaType<uchar>,uchar> *,vt::CCompositeImg<vt::UVType<uchar>,vt::UVType<uchar>> *,vt::CCompositeImg<vt::LumaType<uchar>,uchar> *,vt::CCompositeImg<vt::UVType<uchar>,vt::UVType<uchar>> *,vt::CCompositeImg<vt::LumaType<uchar>,uchar> *,vt::CCompositeImg<vt::UVType<uchar>,vt::UVType<uchar>> *,DXGI_COLOR_SPACE_TYPE,int,int,float,ImageFusionSettings *)

- ea: `0x18003456c`
- end: `0x18003545b`
- name: `?RunHdrInternal@ComputationalPhotographyHelpers@@YA?AW4FusionResult@1@PEAV?$CCompositeImg@V?$LumaType@E@vt@@E@vt@@PEAV?$CCompositeImg@V?$UVType@E@vt@@V12@@4@0101W4DXGI_COLOR_SPACE_TYPE@@HHMPEAUImageFusionSettings@@@Z`
- size: `3823`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64, int, int pExceptionObject, int, float, __int64)`
- caller_count: `1`
- callee_count: `25`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180030a8c`

## callees

- `0x180001850`
- `0x18000290c`
- `0x180002fb0`
- `0x180002fd4`
- `0x180003094`
- `0x18002adc0`
- `0x180030850`
- `0x180030880`
- `0x1800309c0`
- `0x180032ba4`
- `0x180032ccc`
- `0x180032d48`
- `0x180032f08`
- `0x180033ecc`
- `0x18003456c`
- `0x1800814d4`
- `0x180082544`
- `0x1800826cc`
- `0x180084ef8`
- `0x180086438`
- `0x18008fa64`
- `0x18008ff88`
- `0x1800b6f90`
- `0x1800b708c`
- `0x1800b74fc`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoTransformError` at `0x1800346d5`
- `api-ms-win-core-winrt-error-l1-1-0!RoTransformError` at `0x180034817`
- `api-ms-win-core-winrt-error-l1-1-0!RoTransformError` at `0x18003493a`
- `api-ms-win-core-winrt-error-l1-1-0!RoTransformError` at `0x180034b85`
- `api-ms-win-core-winrt-error-l1-1-0!RoTransformError` at `0x180034de7`
- `api-ms-win-core-winrt-error-l1-1-0!RoTransformError` at `0x180034fef`
- `api-ms-win-core-winrt-error-l1-1-0!RoTransformError` at `0x1800350e2`
- `api-ms-win-core-winrt-error-l1-1-0!RoTransformError` at `0x1800352e2`
- `api-ms-win-core-winrt-error-l1-1-0!RoTransformError` at `0x1800346d5`
- `api-ms-win-core-winrt-error-l1-1-0!RoTransformError` at `0x180034817`
- `api-ms-win-core-winrt-error-l1-1-0!RoTransformError` at `0x18003493a`
- `api-ms-win-core-winrt-error-l1-1-0!RoTransformError` at `0x180034b85`
- `api-ms-win-core-winrt-error-l1-1-0!RoTransformError` at `0x180034de7`
- `api-ms-win-core-winrt-error-l1-1-0!RoTransformError` at `0x180034fef`
- `api-ms-win-core-winrt-error-l1-1-0!RoTransformError` at `0x1800350e2`
- `api-ms-win-core-winrt-error-l1-1-0!RoTransformError` at `0x1800352e2`
- `api-ms-win-core-processthreads-l1-1-1!IsProcessorFeaturePresent` at `0x1800345a3`
- `api-ms-win-core-processthreads-l1-1-1!IsProcessorFeaturePresent` at `0x1800345b6`
- `api-ms-win-core-processthreads-l1-1-1!IsProcessorFeaturePresent` at `0x1800345a3`
- `api-ms-win-core-processthreads-l1-1-1!IsProcessorFeaturePresent` at `0x1800345b6`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
__int64 __fastcall ComputationalPhotographyHelpers::RunHdrInternal(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int a7,
        int pExceptionObject,
        int a9,
        float a10,
        ComputationalPhotographyHelpers::ImageFusion *a11)
{
  int v13; // ebx
  int v14; // eax
  double v15; // xmm6_8
  double v16; // xmm0_8
  int v17; // r12d
  unsigned int v18; // r14d
  __int64 v19; // rbx
  int Internal; // esi
  int v21; // ebx
  bool v22; // zf
  unsigned int v23; // ebx
  __int64 v24; // rcx
  int v25; // eax
  int v26; // esi
  int v27; // ebx
  int v28; // esi
  ComputationalPhotographyHelpers::ImageFusion *v29; // rax
  ComputationalPhotographyHelpers::ImageFusion *v30; // r14
  int v31; // eax
  unsigned int v32; // edx
  int v33; // r15d
  __int64 v34; // rcx
  __int64 v35; // rcx
  __int64 v37; // rcx
  __int64 v38; // rcx
  int v39; // eax
  int v40; // r14d
  int v41; // ebx
  bool v42; // zf
  __int64 v43; // rcx
  int v44; // r15d
  int v45; // eax
  __int64 v46; // rcx
  __int64 v47; // rcx
  vt::CImg *v48; // rcx
  int v49; // eax
  int v50; // r14d
  int v51; // ebx
  bool v52; // zf
  vt::CImg *v53; // rcx
  __int64 v54; // rcx
  int v55; // eax
  __int64 v56; // rcx
  __int64 v57; // rcx
  int v58; // eax
  int v59; // r14d
  __int64 v60; // rcx
  __int64 v61; // rcx
  int v62; // eax
  int v63; // r14d
  int v64; // edx
  __int64 v65; // rcx
  int v66; // r8d
  int v67; // r9d
  int v68; // eax
  __int64 v69; // rcx
  int v70; // edi
  unsigned __int8 *v71; // [rsp+28h] [rbp-110h]
  unsigned __int8 *v72; // [rsp+28h] [rbp-110h]
  unsigned __int8 *v73; // [rsp+28h] [rbp-110h]
  unsigned __int8 *v74; // [rsp+28h] [rbp-110h]
  unsigned __int8 *v75; // [rsp+28h] [rbp-110h]
  unsigned __int8 *v76; // [rsp+28h] [rbp-110h]
  int v77; // [rsp+68h] [rbp-D0h]
  int v78; // [rsp+68h] [rbp-D0h]
  int v79; // [rsp+80h] [rbp-B8h]
  int v80; // [rsp+80h] [rbp-B8h]
  __int64 v81[4]; // [rsp+B8h] [rbp-80h] BYREF
  int v82; // [rsp+D8h] [rbp-60h]
  __int64 v83[4]; // [rsp+F0h] [rbp-48h] BYREF
  int v84; // [rsp+110h] [rbp-28h]
  __int64 v85[4]; // [rsp+128h] [rbp-10h] BYREF
  int v86; // [rsp+148h] [rbp+10h]
  __int64 v87[4]; // [rsp+160h] [rbp+28h] BYREF
  int v88; // [rsp+180h] [rbp+48h]
  _BYTE v89[40]; // [rsp+198h] [rbp+60h] BYREF
  _BYTE v90[40]; // [rsp+1C0h] [rbp+88h] BYREF
  void **v91; // [rsp+1E8h] [rbp+B0h] BYREF
  int v92; // [rsp+1F4h] [rbp+BCh]
  int v93; // [rsp+1F8h] [rbp+C0h]
  ComputationalPhotographyHelpers *v94; // [rsp+200h] [rbp+C8h]
  unsigned __int8 *v95; // [rsp+208h] [rbp+D0h]
  _QWORD v96[3]; // [rsp+220h] [rbp+E8h] BYREF
  unsigned __int8 *v97; // [rsp+238h] [rbp+100h]
  int v98; // [rsp+240h] [rbp+108h]
  _BYTE v99[40]; // [rsp+258h] [rbp+120h] BYREF
  _BYTE v100[40]; // [rsp+280h] [rbp+148h] BYREF
  _QWORD v101[3]; // [rsp+2A8h] [rbp+170h] BYREF
  unsigned __int8 *v102; // [rsp+2C0h] [rbp+188h]
  int v103; // [rsp+2C8h] [rbp+190h]
  _QWORD v104[3]; // [rsp+2E0h] [rbp+1A8h] BYREF
  unsigned __int8 *v105; // [rsp+2F8h] [rbp+1C0h]
  int v106; // [rsp+300h] [rbp+1C8h]
  _QWORD v107[3]; // [rsp+318h] [rbp+1E0h] BYREF
  unsigned __int8 *v108; // [rsp+330h] [rbp+1F8h]
  int v109; // [rsp+338h] [rbp+200h]
  __int64 v110; // [rsp+350h] [rbp+218h] BYREF
  int v111; // [rsp+35Ch] [rbp+224h]
  int v112; // [rsp+360h] [rbp+228h]
  unsigned __int8 *v113; // [rsp+368h] [rbp+230h]
  int v114; // [rsp+370h] [rbp+238h]
  __int64 v115; // [rsp+388h] [rbp+250h] BYREF
  unsigned int v116; // [rsp+394h] [rbp+25Ch]
  unsigned int v117; // [rsp+398h] [rbp+260h]
  int v118[2]; // [rsp+3A0h] [rbp+268h]
  unsigned __int8 *v119; // [rsp+3A8h] [rbp+270h]
  __int64 v120; // [rsp+3C0h] [rbp+288h] BYREF
  int v121; // [rsp+3CCh] [rbp+294h]
  int v122; // [rsp+3D0h] [rbp+298h]
  unsigned __int8 *v123; // [rsp+3D8h] [rbp+2A0h]
  int v124; // [rsp+3E0h] [rbp+2A8h]
  __int64 v125; // [rsp+3F8h] [rbp+2C0h] BYREF
  int v126; // [rsp+404h] [rbp+2CCh]
  int v127; // [rsp+408h] [rbp+2D0h]
  unsigned __int8 *v128; // [rsp+410h] [rbp+2D8h]
  int v129; // [rsp+418h] [rbp+2E0h]

  if ( !IsProcessorFeaturePresent(0xAu) || !IsProcessorFeaturePresent(6u) )
    return 3;
  v13 = *(_DWORD *)(a1 + 16);
  v14 = *(_DWORD *)(a1 + 12);
  if ( v14 >= v13 )
    v14 = *(_DWORD *)(a1 + 16);
  v15 = o_log_0((double)v14);
  v16 = o_log_0(2.0);
  v17 = (int)floor(v15 / v16);
  if ( v17 < 4 )
    v17 = 4;
  pExceptionObject = v17;
  v18 = *(_DWORD *)(a1 + 12) / 2;
  v19 = (unsigned int)(v13 / 2);
  vt::CCompositeImg<vt::LumaType<unsigned char>,unsigned char>::CCompositeImg<vt::LumaType<unsigned char>,unsigned char>(
    &v125,
    v18,
    v19);
  vt::CCompositeImg<vt::LumaType<unsigned char>,unsigned char>::CCompositeImg<vt::LumaType<unsigned char>,unsigned char>(
    &v120,
    v18,
    (unsigned int)v19);
  vt::CCompositeImg<vt::LumaType<unsigned char>,unsigned char>::CCompositeImg<vt::LumaType<unsigned char>,unsigned char>(&v115);
  vt::CCompositeImg<vt::LumaType<unsigned char>,unsigned char>::CCompositeImg<vt::LumaType<unsigned char>,unsigned char>(&v110);
  if ( !v128 || !v123 )
    goto LABEL_40;
  vt::CCompositeImg<vt::LumaType<unsigned char>,unsigned char>::CCompositeImg<vt::LumaType<unsigned char>,unsigned char>(v87);
  vt::CCompositeImg<vt::LumaType<unsigned char>,unsigned char>::CCompositeImg<vt::LumaType<unsigned char>,unsigned char>(v85);
  vt::CCompositeImg<vt::UVType<unsigned char>,vt::UVType<unsigned char>>::CCompositeImg<vt::UVType<unsigned char>,vt::UVType<unsigned char>>(v83);
  vt::CCompositeImg<vt::UVType<unsigned char>,vt::UVType<unsigned char>>::CCompositeImg<vt::UVType<unsigned char>,vt::UVType<unsigned char>>(v81);
  Internal = vt::CImg::CreateInternal((__int64)&v115, v18, v19, 12648448, (__int64)v71, 0);
  if ( Internal < 0
    || (Internal = vt::CImg::CreateInternal(
                     (__int64)v87,
                     *(_DWORD *)(a1 + 12),
                     *(_DWORD *)(a1 + 16),
                     12648448,
                     (__int64)v72,
                     0),
        Internal < 0)
    || (Internal = vt::CImg::CreateInternal((__int64)v83, v18, v19, 12713992, (__int64)v73, 0), Internal < 0)
    || (Internal = vt::CImg::CreateInternal((__int64)&v110, v18, v19, 12648448, (__int64)v74, 0), Internal < 0)
    || (Internal = vt::CImg::CreateInternal(
                     (__int64)v85,
                     *(_DWORD *)(a1 + 12),
                     *(_DWORD *)(a1 + 16),
                     12648448,
                     (__int64)v75,
                     0),
        Internal < 0)
    || (Internal = vt::CImg::CreateInternal((__int64)v81, v18, v19, 12713992, (__int64)v76, 0), Internal < 0) )
  {
    RoTransformError((unsigned int)Internal, 0, 0);
    v21 = 0;
    v22 = Internal == -2147024882;
LABEL_11:
    LOBYTE(v21) = !v22;
    v23 = v21 + 2;
LABEL_12:
    v81[0] = (__int64)&vt::CTypedImg<int>::`vftable';
    vt::CImg::~CImg((vt::CImg *)v81);
    v83[0] = (__int64)&vt::CTypedImg<int>::`vftable';
    vt::CImg::~CImg((vt::CImg *)v83);
    v85[0] = (__int64)&vt::CTypedImg<int>::`vftable';
    vt::CImg::~CImg((vt::CImg *)v85);
    v87[0] = (__int64)&vt::CTypedImg<int>::`vftable';
    vt::CImg::~CImg((vt::CImg *)v87);
LABEL_41:
    v110 = (__int64)&vt::CTypedImg<int>::`vftable';
    vt::CImg::~CImg((vt::CImg *)&v110);
    v115 = (__int64)&vt::CTypedImg<int>::`vftable';
    vt::CImg::~CImg((vt::CImg *)&v115);
    v120 = (__int64)&vt::CTypedImg<int>::`vftable';
    vt::CImg::~CImg((vt::CImg *)&v120);
    v125 = (__int64)&vt::CTypedImg<int>::`vftable';
    vt::CImg::~CImg((vt::CImg *)&v125);
    return v23;
  }
  v24 = (unsigned int)(a7 - 5);
  if ( a7 == 5 )
    goto LABEL_26;
  v24 = (unsigned int)(a7 - 6);
  if ( a7 != 6 )
  {
    v24 = (unsigned int)(a7 - 7);
    if ( a7 == 7 )
    {
LABEL_26:
      v28 = 0;
      v27 = 255;
      goto LABEL_27;
    }
    v24 = (unsigned int)(a7 - 8);
    if ( a7 != 8 )
    {
      if ( a7 != 9 )
      {
        v25 = MF::OriginateError<20>(v24, L"Invalid color space");
        v26 = v25;
        if ( v25 < 0 )
        {
          RoTransformError((unsigned int)v25, 0, 0);
          v21 = 0;
          v22 = v26 == -2147024882;
          goto LABEL_11;
        }
      }
      goto LABEL_26;
    }
  }
  v27 = 235;
  v28 = 16;
LABEL_27:
  if ( (unsigned int)dword_18015F098 > 5 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v24,
      qword_180151EC8);
  v29 = (ComputationalPhotographyHelpers::ImageFusion *)operator new(
                                                          0x73A0u,
                                                          (const struct std::nothrow_t *)&std::nothrow);
  a11 = v29;
  if ( v29 )
    v30 = (ComputationalPhotographyHelpers::ImageFusion *)ComputationalPhotographyHelpers::ImageFusion::ImageFusion(v29);
  else
    v30 = 0;
  if ( !v30 )
  {
    pExceptionObject = 2;
    throw (ErrorCode *)&pExceptionObject;
  }
  v31 = ComputationalPhotographyHelpers::ImageFusion::FusionHdr(
          v30,
          a4,
          a5,
          a6,
          (__int64)v87,
          (__int64)v83,
          (__int64)v85,
          (__int64)v81,
          (__int64)&v125,
          (__int64)&v120,
          (__int64)&v115,
          (__int64)&v110,
          a7,
          v17);
  v33 = v31;
  if ( v31 < 0 )
  {
    RoTransformError((unsigned int)v31, 0, 0);
    v21 = 0;
    v22 = v33 == -2147024882;
    goto LABEL_11;
  }
  ComputationalPhotographyHelpers::ImageFusion::`scalar deleting destructor'(v30, v32);
  if ( (unsigned int)dword_18015F098 > 5 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v34,
      word_180151F2A);
  PLaplacianPyramidMultiThreaded<2>::PLaplacianPyramidMultiThreaded<2>(v90);
  PLaplacianPyramidMultiThreaded<2>::PLaplacianPyramidMultiThreaded<2>(v89);
  vt::CCompositeImg<vt::LumaType<unsigned char>,unsigned char>::CCompositeImg<vt::LumaType<unsigned char>,unsigned char>(
    &v91,
    v116,
    v117);
  if ( !v94 )
    goto LABEL_38;
  if ( (unsigned int)dword_18015F098 > 5 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v35,
      word_180152052);
  ComputationalPhotographyHelpers::DilationBuffer(
    v94,
    (unsigned __int8 *)(unsigned int)v95,
    *(__int64 *)v118,
    (unsigned __int8 *)(unsigned int)v119,
    v93,
    v92);
  vt::CImg::Clear((vt::CImg *)&v115, 0);
  if ( (unsigned int)dword_18015F098 > 5 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v37,
      &dword_1801518FC);
  vt::CCompositeImg<vt::LumaType<unsigned char>,unsigned char>::CCompositeImg<vt::LumaType<unsigned char>,unsigned char>(
    v101,
    *(unsigned int *)(a1 + 12),
    *(unsigned int *)(a1 + 16));
  if ( !v102 )
  {
    v101[0] = &vt::CTypedImg<int>::`vftable';
    vt::CImg::~CImg((vt::CImg *)v101);
LABEL_38:
    v91 = &vt::CTypedImg<int>::`vftable';
    vt::CImg::~CImg((vt::CImg *)&v91);
LABEL_39:
    PLaplacianPyramidMultiThreaded<1>::~PLaplacianPyramidMultiThreaded<1>(v89);
    PLaplacianPyramidMultiThreaded<1>::~PLaplacianPyramidMultiThreaded<1>(v90);
    v81[0] = (__int64)&vt::CTypedImg<int>::`vftable';
    vt::CImg::~CImg((vt::CImg *)v81);
    v83[0] = (__int64)&vt::CTypedImg<int>::`vftable';
    vt::CImg::~CImg((vt::CImg *)v83);
    v85[0] = (__int64)&vt::CTypedImg<int>::`vftable';
    vt::CImg::~CImg((vt::CImg *)v85);
    v87[0] = (__int64)&vt::CTypedImg<int>::`vftable';
    vt::CImg::~CImg((vt::CImg *)v87);
LABEL_40:
    v23 = 2;
    goto LABEL_41;
  }
  if ( (unsigned int)dword_18015F098 > 5 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v38,
      qword_180151D98);
  v39 = ComputationalPhotographyHelpers::ImageFusion::BlurAndScaleX2MultiThreaded(
          (const unsigned __int8 *)v94,
          2 * v92,
          2 * v93,
          (int)v95,
          v102,
          v103);
  v40 = v39;
  if ( v39 < 0 )
  {
    RoTransformError((unsigned int)v39, 0, 0);
    v41 = 0;
    v42 = v40 == -2147024882;
LABEL_53:
    LOBYTE(v41) = !v42;
    v23 = v41 + 2;
    v101[0] = &vt::CTypedImg<int>::`vftable';
    vt::CImg::~CImg((vt::CImg *)v101);
    v91 = &vt::CTypedImg<int>::`vftable';
    vt::CImg::~CImg((vt::CImg *)&v91);
LABEL_54:
    PLaplacianPyramidMultiThreaded<1>::~PLaplacianPyramidMultiThreaded<1>(v89);
    PLaplacianPyramidMultiThreaded<1>::~PLaplacianPyramidMultiThreaded<1>(v90);
    goto LABEL_12;
  }
  vt::CImg::Clear((vt::CImg *)&v91, 0);
  if ( (unsigned int)dword_18015F098 > 5 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v43,
      word_180151FB2);
  if ( (unsigned int)dword_18015F098 > 5 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v43,
      word_180151E32);
  v44 = pExceptionObject;
  v45 = BlendTwo(
          (unsigned int)v90,
          (unsigned int)v89,
          *(_QWORD *)(a1 + 24),
          *(_DWORD *)(a1 + 32),
          *(_QWORD *)(a2 + 24),
          *(_DWORD *)(a2 + 32),
          v87[3],
          v88,
          v83[3],
          v84,
          (__int64)v102,
          v103,
          v77,
          *(_DWORD *)(a1 + 12),
          *(_DWORD *)(a1 + 16),
          v79,
          pExceptionObject);
  if ( v45 )
  {
    v41 = 0;
    v42 = v45 == 2;
    goto LABEL_53;
  }
  vt::CImg::Clear((vt::CImg *)v101, 0);
  vt::CImg::Clear((vt::CImg *)v87, 0);
  vt::CImg::Clear((vt::CImg *)v83, 0);
  if ( (unsigned int)dword_18015F098 > 5 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v46,
      byte_1801518DD);
  v101[0] = &vt::CTypedImg<int>::`vftable';
  vt::CImg::~CImg((vt::CImg *)v101);
  v91 = &vt::CTypedImg<int>::`vftable';
  vt::CImg::~CImg((vt::CImg *)&v91);
  PLaplacianPyramidMultiThreaded<2>::PLaplacianPyramidMultiThreaded<2>(v100);
  PLaplacianPyramidMultiThreaded<2>::PLaplacianPyramidMultiThreaded<2>(v99);
  vt::CCompositeImg<vt::LumaType<unsigned char>,unsigned char>::CCompositeImg<vt::LumaType<unsigned char>,unsigned char>(
    v104,
    *(unsigned int *)(a1 + 12),
    *(unsigned int *)(a1 + 16));
  if ( !v105 )
  {
    v104[0] = &vt::CTypedImg<int>::`vftable';
    v48 = (vt::CImg *)v104;
LABEL_65:
    vt::CImg::~CImg(v48);
    PLaplacianPyramidMultiThreaded<1>::~PLaplacianPyramidMultiThreaded<1>(v99);
    PLaplacianPyramidMultiThreaded<1>::~PLaplacianPyramidMultiThreaded<1>(v100);
    goto LABEL_39;
  }
  if ( (unsigned int)dword_18015F098 > 5 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v47,
      &byte_1801517D7);
  v49 = ComputationalPhotographyHelpers::ImageFusion::BlurAndScaleX2MultiThreaded(
          v113,
          2 * v111,
          2 * v112,
          v114,
          v105,
          v106);
  v50 = v49;
  if ( v49 < 0 )
  {
    RoTransformError((unsigned int)v49, 0, 0);
    v51 = 0;
    v52 = v50 == -2147024882;
LABEL_70:
    LOBYTE(v51) = !v52;
    v23 = v51 + 2;
    v104[0] = &vt::CTypedImg<int>::`vftable';
    v53 = (vt::CImg *)v104;
LABEL_71:
    vt::CImg::~CImg(v53);
    PLaplacianPyramidMultiThreaded<1>::~PLaplacianPyramidMultiThreaded<1>(v99);
    PLaplacianPyramidMultiThreaded<1>::~PLaplacianPyramidMultiThreaded<1>(v100);
    goto LABEL_54;
  }
  vt::CImg::Clear((vt::CImg *)&v110, 0);
  if ( (unsigned int)dword_18015F098 > 5 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v54,
      &byte_18015183F);
  if ( (unsigned int)dword_18015F098 > 5 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v54,
      byte_180151921);
  v55 = BlendTwo(
          (unsigned int)v100,
          (unsigned int)v99,
          *(_QWORD *)(a5 + 24),
          *(_DWORD *)(a5 + 32),
          *(_QWORD *)(a6 + 24),
          *(_DWORD *)(a6 + 32),
          v85[3],
          v86,
          v81[3],
          v82,
          (__int64)v105,
          v106,
          v78,
          *(_DWORD *)(a1 + 12),
          *(_DWORD *)(a1 + 16),
          v80,
          v44);
  if ( v55 )
  {
    v51 = 0;
    v52 = v55 == 2;
    goto LABEL_70;
  }
  vt::CImg::Clear((vt::CImg *)v104, 0);
  vt::CImg::Clear((vt::CImg *)v85, 0);
  vt::CImg::Clear((vt::CImg *)v81, 0);
  if ( (unsigned int)dword_18015F098 > 5 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v56,
      &dword_180151C5C);
  v104[0] = &vt::CTypedImg<int>::`vftable';
  vt::CImg::~CImg((vt::CImg *)v104);
  vt::CCompositeImg<vt::LumaType<unsigned char>,unsigned char>::CCompositeImg<vt::LumaType<unsigned char>,unsigned char>(
    v96,
    *(unsigned int *)(a1 + 12),
    *(unsigned int *)(a1 + 16));
  if ( !v97 )
  {
LABEL_81:
    v96[0] = &vt::CTypedImg<int>::`vftable';
    v48 = (vt::CImg *)v96;
    goto LABEL_65;
  }
  if ( (unsigned int)dword_18015F098 > 5 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v57,
      word_180151BB2);
  v58 = ComputationalPhotographyHelpers::ImageFusion::BlurAndScaleX2MultiThreaded(
          v128,
          2 * v126,
          2 * v127,
          v129,
          v97,
          v98);
  v59 = v58;
  if ( v58 < 0 )
  {
    RoTransformError((unsigned int)v58, 0, 0);
    v23 = (v59 != -2147024882) + 2;
LABEL_86:
    v96[0] = &vt::CTypedImg<int>::`vftable';
    v53 = (vt::CImg *)v96;
    goto LABEL_71;
  }
  vt::CImg::Clear((vt::CImg *)&v125, 0);
  if ( (unsigned int)dword_18015F098 > 5 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v60,
      &dword_180151A6C);
  vt::CCompositeImg<vt::LumaType<unsigned char>,unsigned char>::CCompositeImg<vt::LumaType<unsigned char>,unsigned char>(
    v107,
    *(unsigned int *)(a1 + 12),
    *(unsigned int *)(a1 + 16));
  if ( !v108 )
  {
    v107[0] = &vt::CTypedImg<int>::`vftable';
    vt::CImg::~CImg((vt::CImg *)v107);
    goto LABEL_81;
  }
  if ( (unsigned int)dword_18015F098 > 5 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v61,
      &byte_180151AFF);
  v62 = ComputationalPhotographyHelpers::ImageFusion::BlurAndScaleX2MultiThreaded(
          v123,
          2 * v121,
          2 * v122,
          v124,
          v108,
          v109);
  v63 = v62;
  if ( v62 < 0 )
  {
    RoTransformError((unsigned int)v62, 0, 0);
    v23 = (v63 != -2147024882) + 2;
    v107[0] = &vt::CTypedImg<int>::`vftable';
    vt::CImg::~CImg((vt::CImg *)v107);
    goto LABEL_86;
  }
  vt::CImg::Clear((vt::CImg *)&v120, 0);
  if ( (unsigned int)dword_18015F098 > 5 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v65,
      word_180151982);
  if ( (unsigned int)dword_18015F098 > 5 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v65,
      &word_1801517B6);
  v68 = BlendThree(
          a3,
          v64,
          v66,
          v67,
          *(_QWORD *)(a3 + 24),
          *(_DWORD *)(a3 + 32),
          *(_QWORD *)(a4 + 24),
          *(_DWORD *)(a4 + 32),
          (__int64)v97,
          v98,
          (__int64)v108,
          v109,
          (__int64)v90,
          (__int64)v89,
          (__int64)v100,
          (__int64)v99,
          *(_DWORD *)(a1 + 12),
          *(_DWORD *)(a1 + 16),
          v44,
          v28,
          v27);
  if ( v68 )
  {
    v23 = (v68 != 2) + 2;
    v107[0] = &vt::CTypedImg<int>::`vftable';
    vt::CImg::~CImg((vt::CImg *)v107);
    vt::CCompositeImg<vt::LumaType<unsigned char>,unsigned char>::~CCompositeImg<vt::LumaType<unsigned char>,unsigned char>(v96);
LABEL_106:
    PLaplacianPyramidMultiThreaded<1>::~PLaplacianPyramidMultiThreaded<1>(v99);
    PLaplacianPyramidMultiThreaded<1>::~PLaplacianPyramidMultiThreaded<1>(v100);
    PLaplacianPyramidMultiThreaded<1>::~PLaplacianPyramidMultiThreaded<1>(v89);
    PLaplacianPyramidMultiThreaded<1>::~PLaplacianPyramidMultiThreaded<1>(v90);
    vt::CCompositeImg<vt::LumaType<unsigned char>,unsigned char>::~CCompositeImg<vt::LumaType<unsigned char>,unsigned char>(v81);
    vt::CCompositeImg<vt::LumaType<unsigned char>,unsigned char>::~CCompositeImg<vt::LumaType<unsigned char>,unsigned char>(v83);
    vt::CCompositeImg<vt::LumaType<unsigned char>,unsigned char>::~CCompositeImg<vt::LumaType<unsigned char>,unsigned char>(v85);
    vt::CCompositeImg<vt::LumaType<unsigned char>,unsigned char>::~CCompositeImg<vt::LumaType<unsigned char>,unsigned char>(v87);
    vt::CCompositeImg<vt::LumaType<unsigned char>,unsigned char>::~CCompositeImg<vt::LumaType<unsigned char>,unsigned char>(&v110);
    vt::CCompositeImg<vt::LumaType<unsigned char>,unsigned char>::~CCompositeImg<vt::LumaType<unsigned char>,unsigned char>(&v115);
    vt::CCompositeImg<vt::LumaType<unsigned char>,unsigned char>::~CCompositeImg<vt::LumaType<unsigned char>,unsigned char>(&v120);
    vt::CCompositeImg<vt::LumaType<unsigned char>,unsigned char>::~CCompositeImg<vt::LumaType<unsigned char>,unsigned char>(&v125);
    return v23;
  }
  vt::CImg::Clear((vt::CImg *)v96, 0);
  vt::CImg::Clear((vt::CImg *)v107, 0);
  if ( (unsigned int)dword_18015F098 > 5 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v69,
      &word_180151ADE);
  vt::CCompositeImg<vt::LumaType<unsigned char>,unsigned char>::~CCompositeImg<vt::LumaType<unsigned char>,unsigned char>(v107);
  vt::CCompositeImg<vt::LumaType<unsigned char>,unsigned char>::~CCompositeImg<vt::LumaType<unsigned char>,unsigned char>(v96);
  v70 = ComputationalPhotographyHelpers::ImageFusion::StretchImageLum(
          *(unsigned __int8 **)(a1 + 24),
          *(_DWORD *)(a1 + 32),
          *(_DWORD *)(a1 + 12),
          *(_DWORD *)(a1 + 16),
          v28,
          v27);
  if ( v70 < 0
    || (v70 = ComputationalPhotographyHelpers::ImageFusion::BoostSaturationMultiThreaded(
                *(unsigned __int8 **)(a2 + 24),
                *(_DWORD *)(a2 + 32),
                *(_DWORD *)(a2 + 12),
                *(_DWORD *)(a2 + 16),
                a10),
        v70 < 0) )
  {
    RoTransformError((unsigned int)v70, 0, 0);
    v23 = (v70 != -2147024882) + 2;
    goto LABEL_106;
  }
  PLaplacianPyramidMultiThreaded<1>::~PLaplacianPyramidMultiThreaded<1>(v99);
  PLaplacianPyramidMultiThreaded<1>::~PLaplacianPyramidMultiThreaded<1>(v100);
  PLaplacianPyramidMultiThreaded<1>::~PLaplacianPyramidMultiThreaded<1>(v89);
  PLaplacianPyramidMultiThreaded<1>::~PLaplacianPyramidMultiThreaded<1>(v90);
  vt::CCompositeImg<vt::LumaType<unsigned char>,unsigned char>::~CCompositeImg<vt::LumaType<unsigned char>,unsigned char>(v81);
  vt::CCompositeImg<vt::LumaType<unsigned char>,unsigned char>::~CCompositeImg<vt::LumaType<unsigned char>,unsigned char>(v83);
  vt::CCompositeImg<vt::LumaType<unsigned char>,unsigned char>::~CCompositeImg<vt::LumaType<unsigned char>,unsigned char>(v85);
  vt::CCompositeImg<vt::LumaType<unsigned char>,unsigned char>::~CCompositeImg<vt::LumaType<unsigned char>,unsigned char>(v87);
  vt::CCompositeImg<vt::LumaType<unsigned char>,unsigned char>::~CCompositeImg<vt::LumaType<unsigned char>,unsigned char>(&v110);
  vt::CCompositeImg<vt::LumaType<unsigned char>,unsigned char>::~CCompositeImg<vt::LumaType<unsigned char>,unsigned char>(&v115);
  vt::CCompositeImg<vt::LumaType<unsigned char>,unsigned char>::~CCompositeImg<vt::LumaType<unsigned char>,unsigned char>(&v120);
  vt::CCompositeImg<vt::LumaType<unsigned char>,unsigned char>::~CCompositeImg<vt::LumaType<unsigned char>,unsigned char>(&v125);
  return 0;
}

```

## disassembly

```asm
0x18003456c  mov     rax, rsp
0x18003456f  mov     [rax+8], rbx
0x180034573  mov     [rax+20h], r9
0x180034577  mov     [rax+18h], r8
0x18003457b  push    rbp
0x18003457c  push    rsi
0x18003457d  push    rdi
0x18003457e  push    r12
0x180034580  push    r13
0x180034582  push    r14
0x180034584  push    r15
0x180034586  lea     rbp, [rax-348h]
0x18003458d  sub     rsp, 440h
0x180034594  movaps  xmmword ptr [rax-48h], xmm6
0x180034598  mov     r13, rdx
0x18003459b  mov     rdi, rcx
0x18003459e  mov     ecx, 0Ah; ProcessorFeature
0x1800345a3  call    cs:__imp_IsProcessorFeaturePresent
0x1800345a9  xor     esi, esi
0x1800345ab  test    eax, eax
0x1800345ad  jz      loc_180035418
0x1800345b3  lea     ecx, [rsi+6]; ProcessorFeature
0x1800345b6  call    cs:__imp_IsProcessorFeaturePresent
0x1800345bc  test    eax, eax
0x1800345be  jz      loc_180035418
0x1800345c4  mov     ebx, [rdi+10h]
0x1800345c7  mov     eax, [rdi+0Ch]
0x1800345ca  cmp     eax, ebx
0x1800345cc  cmovge  eax, ebx
0x1800345cf  movd    xmm0, eax
0x1800345d3  cvtdq2pd xmm0, xmm0; X
0x1800345d7  call    _o_log_0
0x1800345dc  movaps  xmm6, xmm0
0x1800345df  movsd   xmm0, cs:__real@4000000000000000; X
0x1800345e7  call    _o_log_0
0x1800345ec  divsd   xmm6, xmm0
0x1800345f0  movaps  xmm0, xmm6; X
0x1800345f3  call    floor
0x1800345f8  cvttsd2si r12d, xmm0
0x1800345fd  lea     eax, [rsi+4]
0x180034600  cmp     r12d, eax
0x180034603  cmovl   r12d, eax
0x180034607  mov     [rbp+340h+pExceptionObject], r12d
0x18003460e  mov     eax, [rdi+0Ch]
0x180034611  cdq
0x180034612  sub     eax, edx
0x180034614  sar     eax, 1
0x180034616  mov     r14d, eax
0x180034619  mov     eax, ebx
0x18003461b  cdq
0x18003461c  sub     eax, edx
0x18003461e  sar     eax, 1
0x180034620  mov     ebx, eax
0x180034622  mov     r8d, eax
0x180034625  mov     edx, r14d
0x180034628  lea     rcx, [rbp+340h+var_80]
0x18003462f  call    ??0?$CCompositeImg@V?$LumaType@E@vt@@E@vt@@QEAA@HHW4AlignMode@1@@Z; vt::CCompositeImg<vt::LumaType<uchar>,uchar>::CCompositeImg<vt::LumaType<uchar>,uchar>(int,int,vt::AlignMode)
0x180034634  nop
0x180034635  mov     r8d, ebx
0x180034638  mov     edx, r14d
0x18003463b  lea     rcx, [rbp+340h+var_B8]
0x180034642  call    ??0?$CCompositeImg@V?$LumaType@E@vt@@E@vt@@QEAA@HHW4AlignMode@1@@Z; vt::CCompositeImg<vt::LumaType<uchar>,uchar>::CCompositeImg<vt::LumaType<uchar>,uchar>(int,int,vt::AlignMode)
0x180034647  nop
0x180034648  lea     rcx, [rbp+340h+var_F0]; void *
0x18003464f  call    ??0?$CCompositeImg@V?$LumaType@E@vt@@E@vt@@QEAA@XZ; vt::CCompositeImg<vt::LumaType<uchar>,uchar>::CCompositeImg<vt::LumaType<uchar>,uchar>(void)
0x180034654  nop
0x180034655  lea     rcx, [rbp+340h+var_128]; void *
0x18003465c  call    ??0?$CCompositeImg@V?$LumaType@E@vt@@E@vt@@QEAA@XZ; vt::CCompositeImg<vt::LumaType<uchar>,uchar>::CCompositeImg<vt::LumaType<uchar>,uchar>(void)
0x180034661  nop
0x180034662  lea     r15, ??_7?$CTypedImg@H@vt@@6B@; const vt::CTypedImg<int>::`vftable'
0x180034669  cmp     [rbp+340h+var_68], rsi
0x180034670  jz      loc_180034A1C
0x180034676  cmp     [rbp+340h+var_A0], rsi
0x18003467d  jz      loc_180034A1C
0x180034683  lea     rcx, [rbp+340h+var_318]; void *
0x180034687  call    ??0?$CCompositeImg@V?$LumaType@E@vt@@E@vt@@QEAA@XZ; vt::CCompositeImg<vt::LumaType<uchar>,uchar>::CCompositeImg<vt::LumaType<uchar>,uchar>(void)
0x18003468c  nop
0x18003468d  lea     rcx, [rbp+340h+var_350]; void *
0x180034691  call    ??0?$CCompositeImg@V?$LumaType@E@vt@@E@vt@@QEAA@XZ; vt::CCompositeImg<vt::LumaType<uchar>,uchar>::CCompositeImg<vt::LumaType<uchar>,uchar>(void)
0x180034696  nop
0x180034697  lea     rcx, [rbp+340h+var_388]
0x18003469b  call    ??0?$CCompositeImg@V?$UVType@E@vt@@V12@@vt@@QEAA@XZ; vt::CCompositeImg<vt::UVType<uchar>,vt::UVType<uchar>>::CCompositeImg<vt::UVType<uchar>,vt::UVType<uchar>>(void)
0x1800346a0  nop
0x1800346a1  lea     rcx, [rbp+340h+var_3C0]
0x1800346a5  call    ??0?$CCompositeImg@V?$UVType@E@vt@@V12@@vt@@QEAA@XZ; vt::CCompositeImg<vt::UVType<uchar>,vt::UVType<uchar>>::CCompositeImg<vt::UVType<uchar>,vt::UVType<uchar>>(void)
0x1800346aa  nop
0x1800346ab  mov     byte ptr [rsp+470h+var_448], sil
0x1800346b0  mov     r9d, 0C10000h
0x1800346b6  mov     r8d, ebx
0x1800346b9  mov     edx, r14d
0x1800346bc  lea     rcx, [rbp+340h+var_F0]
0x1800346c3  call    ?CreateInternal@CImg@vt@@AEAAJHHHW4AlignMode@2@_N@Z; vt::CImg::CreateInternal(int,int,int,vt::AlignMode,bool)
0x1800346c8  mov     esi, eax
0x1800346ca  test    eax, eax
0x1800346cc  jns     short loc_180034726
0x1800346ce  xor     r8d, r8d
0x1800346d1  xor     edx, edx
0x1800346d3  mov     ecx, esi
0x1800346d5  call    cs:__imp_RoTransformError
0x1800346db  nop
0x1800346dc  xor     ebx, ebx
0x1800346de  cmp     esi, 8007000Eh
0x1800346e4  setnz   bl
0x1800346e7  add     ebx, 2
0x1800346ea  mov     [rbp+340h+var_3C0], r15
0x1800346ee  lea     rcx, [rbp+340h+var_3C0]; this
0x1800346f2  call    ??1CImg@vt@@UEAA@XZ; vt::CImg::~CImg(void)
0x1800346f7  nop
0x1800346f8  mov     [rbp+340h+var_388], r15
0x1800346fc  lea     rcx, [rbp+340h+var_388]; this
0x180034700  call    ??1CImg@vt@@UEAA@XZ; vt::CImg::~CImg(void)
0x180034705  nop
0x180034706  mov     [rbp+340h+var_350], r15
0x18003470a  lea     rcx, [rbp+340h+var_350]; this
0x18003470e  call    ??1CImg@vt@@UEAA@XZ; vt::CImg::~CImg(void)
0x180034713  nop
0x180034714  mov     [rbp+340h+var_318], r15
0x180034718  lea     rcx, [rbp+340h+var_318]; this
0x18003471c  call    ??1CImg@vt@@UEAA@XZ; vt::CImg::~CImg(void)
0x180034721  jmp     loc_180034A21
0x180034726  mov     byte ptr [rsp+470h+var_448], 0
0x18003472b  mov     r9d, 0C10000h
0x180034731  mov     r8d, [rdi+10h]
0x180034735  mov     edx, [rdi+0Ch]
0x180034738  lea     rcx, [rbp+340h+var_318]
0x18003473c  call    ?CreateInternal@CImg@vt@@AEAAJHHHW4AlignMode@2@_N@Z; vt::CImg::CreateInternal(int,int,int,vt::AlignMode,bool)
0x180034741  mov     esi, eax
0x180034743  test    eax, eax
0x180034745  js      short loc_1800346CE
0x180034747  mov     byte ptr [rsp+470h+var_448], 0
0x18003474c  mov     r9d, 0C20008h
0x180034752  mov     r8d, ebx
0x180034755  mov     edx, r14d
0x180034758  lea     rcx, [rbp+340h+var_388]
0x18003475c  call    ?CreateInternal@CImg@vt@@AEAAJHHHW4AlignMode@2@_N@Z; vt::CImg::CreateInternal(int,int,int,vt::AlignMode,bool)
0x180034761  mov     esi, eax
0x180034763  test    eax, eax
0x180034765  js      loc_1800346CE
0x18003476b  mov     byte ptr [rsp+470h+var_448], 0
0x180034770  mov     r9d, 0C10000h
0x180034776  mov     r8d, ebx
0x180034779  mov     edx, r14d
0x18003477c  lea     rcx, [rbp+340h+var_128]
0x180034783  call    ?CreateInternal@CImg@vt@@AEAAJHHHW4AlignMode@2@_N@Z; vt::CImg::CreateInternal(int,int,int,vt::AlignMode,bool)
0x180034788  mov     esi, eax
0x18003478a  test    eax, eax
0x18003478c  js      loc_1800346CE
0x180034792  mov     byte ptr [rsp+470h+var_448], 0
0x180034797  mov     r9d, 0C10000h
0x18003479d  mov     r8d, [rdi+10h]
0x1800347a1  mov     edx, [rdi+0Ch]
0x1800347a4  lea     rcx, [rbp+340h+var_350]
0x1800347a8  call    ?CreateInternal@CImg@vt@@AEAAJHHHW4AlignMode@2@_N@Z; vt::CImg::CreateInternal(int,int,int,vt::AlignMode,bool)
0x1800347ad  mov     esi, eax
0x1800347af  test    eax, eax
0x1800347b1  js      loc_1800346CE
0x1800347b7  mov     byte ptr [rsp+470h+var_448], 0
0x1800347bc  mov     r9d, 0C20008h
0x1800347c2  mov     r8d, ebx
0x1800347c5  mov     edx, r14d
0x1800347c8  lea     rcx, [rbp+340h+var_3C0]
0x1800347cc  call    ?CreateInternal@CImg@vt@@AEAAJHHHW4AlignMode@2@_N@Z; vt::CImg::CreateInternal(int,int,int,vt::AlignMode,bool)
0x1800347d1  mov     esi, eax
0x1800347d3  test    eax, eax
0x1800347d5  js      loc_1800346CE
0x1800347db  mov     r15d, [rbp+340h+arg_30]
0x1800347e2  mov     ecx, r15d
0x1800347e5  sub     ecx, 5
0x1800347e8  jz      short loc_18003483E
0x1800347ea  sub     ecx, 1
0x1800347ed  jz      short loc_180034832
0x1800347ef  sub     ecx, 1
0x1800347f2  jz      short loc_18003483E
0x1800347f4  sub     ecx, 1
0x1800347f7  jz      short loc_180034832
0x1800347f9  cmp     ecx, 1
0x1800347fc  jz      short loc_18003483E
0x1800347fe  lea     rdx, aInvalidColorSp; "Invalid color space"
0x180034805  call    ??$OriginateError@$0BE@@MF@@YAJJAEAY0BE@$$CBG@Z; MF::OriginateError<20>(long,ushort const (&)[20])
0x18003480a  mov     esi, eax
0x18003480c  test    eax, eax
0x18003480e  jns     short loc_18003483E
0x180034810  xor     r8d, r8d
0x180034813  xor     edx, edx
0x180034815  mov     ecx, eax
0x180034817  call    cs:__imp_RoTransformError
0x18003481d  nop
0x18003481e  xor     ebx, ebx
0x180034820  cmp     esi, 8007000Eh
0x180034826  lea     r15, ??_7?$CTypedImg@H@vt@@6B@; const vt::CTypedImg<int>::`vftable'
0x18003482d  jmp     loc_1800346E4
0x180034832  mov     ebx, 0EBh
0x180034837  mov     esi, 10h
0x18003483c  jmp     short loc_180034845
0x18003483e  xor     esi, esi
0x180034840  mov     ebx, 0FFh
0x180034845  mov     eax, cs:dword_18015F098
0x18003484b  cmp     eax, 5
0x18003484e  jbe     short loc_18003485C
0x180034850  lea     rdx, qword_180151EC8
0x180034857  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18003485c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180034863  mov     ecx, 73A0h; unsigned __int64
0x180034868  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003486d  mov     [rbp+340h+arg_50], rax
0x180034874  test    rax, rax
0x180034877  jz      short loc_180034886
0x180034879  mov     rcx, rax; this
0x18003487c  call    ??0ImageFusion@ComputationalPhotographyHelpers@@QEAA@XZ; ComputationalPhotographyHelpers::ImageFusion::ImageFusion(void)
0x180034881  mov     r14, rax
0x180034884  jmp     short loc_180034889
0x180034886  xor     r14d, r14d
0x180034889  test    r14, r14
0x18003488c  jz      loc_18003543D
0x180034892  mov     [rsp+470h+var_3F0], r12d; int
0x18003489a  mov     [rsp+470h+var_3F8], r15d; int
0x18003489f  lea     rax, [rbp+340h+var_128]
0x1800348a6  mov     [rsp+470h+var_400], rax; __int64
0x1800348ab  lea     rax, [rbp+340h+var_F0]
0x1800348b2  mov     [rsp+470h+var_408], rax; __int64
0x1800348b7  lea     rax, [rbp+340h+var_B8]
0x1800348be  mov     [rsp+470h+var_410], rax; __int64
0x1800348c3  lea     rax, [rbp+340h+var_80]
0x1800348ca  mov     [rsp+470h+var_418], rax; __int64
0x1800348cf  lea     rax, [rbp+340h+var_3C0]
0x1800348d3  mov     [rsp+470h+var_420], rax; __int64
0x1800348d8  lea     rax, [rbp+340h+var_350]
0x1800348dc  mov     [rsp+470h+var_428], rax; __int64
0x1800348e1  lea     rax, [rbp+340h+var_388]
0x1800348e5  mov     [rsp+470h+var_430], rax; __int64
0x1800348ea  lea     rax, [rbp+340h+var_318]
0x1800348ee  mov     [rsp+470h+var_438], rax; __int64
0x1800348f3  mov     r12, [rbp+340h+arg_28]
0x1800348fa  mov     [rsp+470h+var_440], r12; int
0x1800348ff  mov     rax, [rbp+340h+arg_20]
0x180034906  mov     [rsp+470h+var_448], rax; __int64
0x18003490b  mov     rax, [rbp+340h+arg_18]
0x180034912  mov     [rsp+470h+var_450], rax; __int64
0x180034917  mov     r9, [rbp+340h+arg_10]
0x18003491e  mov     r8, r13
0x180034921  mov     rdx, rdi
0x180034924  mov     rcx, r14; this
0x180034927  call    ?FusionHdr@ImageFusion@ComputationalPhotographyHelpers@@QEAAJPEAV?$CCompositeImg@V?$LumaType@E@vt@@E@vt@@PEAV?$CCompositeImg@V?$UVType@E@vt@@V12@@4@010101010000W4DXGI_COLOR_SPACE_TYPE@@HH@Z; ComputationalPhotographyHelpers::ImageFusion::FusionHdr(vt::CCompositeImg<vt::LumaType<uchar>,uchar> *,vt::CCompositeImg<vt::UVType<uchar>,vt::UVType<uchar>> *,vt::CCompositeImg<vt::LumaType<uchar>,uchar> *,vt::CCompositeImg<vt::UVType<uchar>,vt::UVType<uchar>> *,vt::CCompositeImg<vt::LumaType<uchar>,uchar> *,vt::CCompositeImg<vt::UVType<uchar>,vt::UVType<uchar>> *,vt::CCompositeImg<vt::LumaType<uchar>,uchar> *,vt::CCompositeImg<vt::UVType<uchar>,vt::UVType<uchar>> *,vt::CCompositeImg<vt::LumaType<uchar>,uchar> *,vt::CCompositeImg<vt::UVType<uchar>,vt::UVType<uchar>> *,vt::CCompositeImg<vt::LumaType<uchar>,uchar> *,vt::CCompositeImg<vt::LumaType<uchar>,uchar> *,vt::CCompositeImg<vt::LumaType<uchar>,uchar> *,vt::CCompositeImg<vt::LumaType<uchar>,uchar> *,DXGI_COLOR_SPACE_TYPE,int,int)
0x18003492c  mov     r15d, eax
0x18003492f  test    eax, eax
0x180034931  jns     short loc_18003494F
0x180034933  xor     r8d, r8d
0x180034936  xor     edx, edx
0x180034938  mov     ecx, eax
0x18003493a  call    cs:__imp_RoTransformError
0x180034940  nop
0x180034941  xor     ebx, ebx
0x180034943  cmp     r15d, 8007000Eh
0x18003494a  jmp     loc_180034826
0x18003494f  mov     rcx, r14; this
0x180034952  call    ??_GImageFusion@ComputationalPhotographyHelpers@@QEAAPEAXI@Z; ComputationalPhotographyHelpers::ImageFusion::`scalar deleting destructor'(uint)
0x180034957  mov     eax, cs:dword_18015F098
0x18003495d  mov     r15d, 5
0x180034963  cmp     eax, r15d
0x180034966  jbe     short loc_180034974
0x180034968  lea     rdx, word_180151F2A
0x18003496f  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180034974  lea     rcx, [rbp+340h+var_2B8]
0x18003497b  call    ??0?$PLaplacianPyramidMultiThreaded@$01@@QEAA@XZ; PLaplacianPyramidMultiThreaded<2>::PLaplacianPyramidMultiThreaded<2>(void)
0x180034980  nop
0x180034981  lea     rcx, [rbp+340h+var_2E0]
0x180034985  call    ??0?$PLaplacianPyramidMultiThreaded@$01@@QEAA@XZ; PLaplacianPyramidMultiThreaded<2>::PLaplacianPyramidMultiThreaded<2>(void)
0x18003498a  nop
0x18003498b  mov     r8d, [rbp+340h+var_E0]
0x180034992  mov     edx, [rbp+340h+var_E4]
0x180034998  lea     rcx, [rbp+340h+var_290]
0x18003499f  call    ??0?$CCompositeImg@V?$LumaType@E@vt@@E@vt@@QEAA@HHW4AlignMode@1@@Z; vt::CCompositeImg<vt::LumaType<uchar>,uchar>::CCompositeImg<vt::LumaType<uchar>,uchar>(int,int,vt::AlignMode)
0x1800349a4  nop
0x1800349a5  cmp     [rbp+340h+var_278], 0
0x1800349ad  jnz     loc_180034A77
0x1800349b3  lea     r15, ??_7?$CTypedImg@H@vt@@6B@; const vt::CTypedImg<int>::`vftable'
0x1800349ba  mov     [rbp+340h+var_290], r15
0x1800349c1  lea     rcx, [rbp+340h+var_290]; this
0x1800349c8  call    ??1CImg@vt@@UEAA@XZ; vt::CImg::~CImg(void)
0x1800349cd  nop
0x1800349ce  lea     rcx, [rbp+340h+var_2E0]
0x1800349d2  call    ??1?$PLaplacianPyramidMultiThreaded@$00@@QEAA@XZ; PLaplacianPyramidMultiThreaded<1>::~PLaplacianPyramidMultiThreaded<1>(void)
0x1800349d7  nop
0x1800349d8  lea     rcx, [rbp+340h+var_2B8]
0x1800349df  call    ??1?$PLaplacianPyramidMultiThreaded@$00@@QEAA@XZ; PLaplacianPyramidMultiThreaded<1>::~PLaplacianPyramidMultiThreaded<1>(void)
0x1800349e4  nop
0x1800349e5  mov     [rbp+340h+var_3C0], r15
0x1800349e9  lea     rcx, [rbp+340h+var_3C0]; this
0x1800349ed  call    ??1CImg@vt@@UEAA@XZ; vt::CImg::~CImg(void)
0x1800349f2  nop
0x1800349f3  mov     [rbp+340h+var_388], r15
0x1800349f7  lea     rcx, [rbp+340h+var_388]; this
0x1800349fb  call    ??1CImg@vt@@UEAA@XZ; vt::CImg::~CImg(void)
0x180034a00  nop
0x180034a01  mov     [rbp+340h+var_350], r15
0x180034a05  lea     rcx, [rbp+340h+var_350]; this
0x180034a09  call    ??1CImg@vt@@UEAA@XZ; vt::CImg::~CImg(void)
0x180034a0e  nop
0x180034a0f  mov     [rbp+340h+var_318], r15
0x180034a13  lea     rcx, [rbp+340h+var_318]; this
  ... truncated ...
```
