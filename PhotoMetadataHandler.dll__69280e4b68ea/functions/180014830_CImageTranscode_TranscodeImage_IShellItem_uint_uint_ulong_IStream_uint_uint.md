# CImageTranscode::TranscodeImage(IShellItem *,uint,uint,ulong,IStream *,uint *,uint *)

- ea: `0x180014830`
- end: `0x18001555f`
- name: `?TranscodeImage@CImageTranscode@@UEAAJPEAUIShellItem@@IIKPEAUIStream@@PEAI2@Z`
- size: `3375`
- prototype: `__int64 __fastcall(CImageTranscode *this, struct IShellItem *, unsigned int, unsigned int, char, struct _GUID *, unsigned int *, unsigned int *)`
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180005a88`
- `0x180008b54`
- `0x18000aad0`
- `0x18000e3a0`
- `0x18000f050`
- `0x180010420`
- `0x18001186c`
- `0x180014830`
- `0x180015568`
- `0x180016a40`
- `0x180017408`
- `0x18002773c`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180015396`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180015396`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180014925`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180014988`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180015296`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180014925`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180014988`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180015296`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180014f0e`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180014f0e`
- `WindowsCodecs!WICConvertBitmapSource` at `0x180014eb7`
- `WindowsCodecs!WICConvertBitmapSource` at `0x180014eb7`
- `OLEAUT32!__imp_VariantClear` at `0x18001502d`
- `OLEAUT32!__imp_VariantClear` at `0x18001502d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CImageTranscode::TranscodeImage(
        CImageTranscode *this,
        struct IShellItem *a2,
        unsigned int a3,
        unsigned int a4,
        char a5,
        struct _GUID *a6,
        unsigned int *a7,
        unsigned int *a8)
{
  unsigned int v8; // ebx
  unsigned int v9; // esi
  char v11; // r15
  unsigned __int64 v12; // r8
  HRESULT Instance; // edi
  struct IWICBitmapSource *v14; // rcx
  bool v15; // sf
  unsigned int v16; // edx
  unsigned int i; // ecx
  __int64 v18; // r8
  int v19; // eax
  struct IWICBitmapSource *v20; // rcx
  unsigned int v21; // ecx
  const struct _GUID *v22; // rcx
  IStream *v23; // r15
  GUID *v24; // rdx
  const struct _GUID *v25; // rcx
  unsigned __int64 v26; // r8
  unsigned __int64 v27; // r8
  unsigned __int64 v28; // r8
  struct IUnknown *v29; // r10
  struct IUnknown *v30; // r10
  const struct _GUID *v31; // rcx
  int v32; // ebx
  LPSTREAM v33; // rbx
  _QWORD *v34; // rax
  unsigned __int64 v35; // r8
  unsigned __int64 v36; // r8
  struct IWICColorTransform *v38; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v39; // [rsp+50h] [rbp-B8h] BYREF
  double v40; // [rsp+58h] [rbp-B0h] BYREF
  struct IWICBitmapDecoder *v41; // [rsp+60h] [rbp-A8h] BYREF
  struct IWICImagingFactory *ppv; // [rsp+68h] [rbp-A0h] BYREF
  struct IUnknown *v43; // [rsp+70h] [rbp-98h] BYREF
  __int64 v44; // [rsp+78h] [rbp-90h] BYREF
  struct IWICBitmapSource *v45; // [rsp+80h] [rbp-88h] BYREF
  LPSTREAM ppstm; // [rsp+88h] [rbp-80h] BYREF
  IWICBitmapSource *pISrc; // [rsp+90h] [rbp-78h] BYREF
  struct _GUID *v48; // [rsp+98h] [rbp-70h] BYREF
  __int64 v49; // [rsp+A0h] [rbp-68h] BYREF
  IWICBitmapSource *ppIDst; // [rsp+A8h] [rbp-60h] BYREF
  struct IWICBitmapSource *v51; // [rsp+B0h] [rbp-58h] BYREF
  const struct _GUID *v52; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v53; // [rsp+C0h] [rbp-48h] BYREF
  struct IWICBitmapFrameDecode *v54; // [rsp+C8h] [rbp-40h] BYREF
  __int64 v55; // [rsp+D0h] [rbp-38h] BYREF
  unsigned int *v56; // [rsp+D8h] [rbp-30h]
  GUID Buf1; // [rsp+E8h] [rbp-20h] BYREF
  VARIANTARG pvarg; // [rsp+F8h] [rbp-10h] BYREF
  GUID dstFormat; // [rsp+118h] [rbp+10h] BYREF
  _QWORD v60[2]; // [rsp+128h] [rbp+20h] BYREF
  const wchar_t *v61; // [rsp+138h] [rbp+30h]
  __int128 v62; // [rsp+140h] [rbp+38h]

  v8 = a4;
  v9 = a3;
  v48 = a6;
  v56 = a7;
  v11 = 0;
  if ( a7 )
    *a7 = 0;
  if ( a8 )
    *a8 = 0;
  if ( !a2 || !a6 || (a5 & 3u) - 1 > 1 )
    return 2147942487LL;
  if ( !a3 )
  {
    if ( !a4 )
    {
      v9 = -1;
      v8 = -1;
      goto LABEL_12;
    }
    return 2147942487LL;
  }
  if ( !a4 )
    return 2147942487LL;
LABEL_12:
  v12 = *((_QWORD *)WPP_GLOBAL_Control + 7);
  if ( v12 )
    ShellPrivateTraceEvent(a6, 0x11u, v12, 1u);
  ppv = 0;
  Instance = CoCreateInstance(
               &CLSID_WICImagingFactory2,
               0,
               1u,
               &GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70,
               (LPVOID *)&ppv);
  v14 = 0;
  v45 = 0;
  v54 = 0;
  v15 = Instance < 0;
  if ( Instance < 0 )
    goto LABEL_47;
  if ( v9 > 0x400 || v8 > 0x400 )
    goto LABEL_34;
  *(double *)&v38 = 0.0;
  Instance = CoCreateInstance(
               &CLSID_LocalThumbnailCache,
               0,
               1u,
               &GUID_f676c15d_596a_4ce2_8234_33996f445db1,
               (LPVOID *)&v38);
  if ( Instance >= 0 )
  {
    LODWORD(v39) = 0;
    *(_OWORD *)&pvarg.vt = 0;
    v41 = 0;
    v16 = v9;
    if ( v9 <= v8 )
      v16 = v8;
    for ( i = 0; i < 4; ++i )
    {
      v18 = (unsigned int)dword_180091EC8[i];
      if ( v16 <= (unsigned int)v18 )
        goto LABEL_25;
    }
    v18 = 1024;
LABEL_25:
    Instance = ((__int64 (__fastcall *)(struct IWICColorTransform *, struct IShellItem *, __int64, _QWORD, struct IWICBitmapDecoder **, __int64 *, VARIANTARG *))v38->lpVtbl->GetSize)(
                 v38,
                 a2,
                 v18,
                 0,
                 &v41,
                 &v39,
                 &pvarg);
    if ( Instance >= 0 )
    {
      if ( (v39 & 1) != 0 )
      {
        Instance = -2147467259;
      }
      else
      {
        *(_QWORD *)&Buf1.Data1 = 0;
        Instance = ((__int64 (__fastcall *)(struct IWICBitmapDecoder *, GUID *))v41->lpVtbl->QueryCapability)(
                     v41,
                     &Buf1);
        if ( Instance >= 0 )
        {
          v40 = 0.0;
          Instance = ((__int64 (__fastcall *)(struct IWICImagingFactory *, _QWORD, _QWORD, _QWORD, double *))ppv->lpVtbl->CreateBitmapFromHBITMAP)(
                       ppv,
                       *(_QWORD *)&Buf1.Data1,
                       0,
                       0,
                       &v40);
          if ( Instance >= 0 )
            Instance = (***(__int64 (__fastcall ****)(double, GUID *, struct IWICBitmapSource **))&v40)(
                         COERCE_DOUBLE(*(_QWORD *)&v40),
                         &GUID_00000120_a8f2_4877_ba0a_fd2b6645fb94,
                         &v45);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v40);
        }
      }
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v41);
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v38);
  if ( Instance < 0 )
  {
LABEL_34:
    *(double *)&v38 = 0.0;
    Instance = ((__int64 (__fastcall *)(struct IShellItem *, _QWORD, const GUID *, GUID *, struct IWICColorTransform **))a2->lpVtbl->BindToHandler)(
                 a2,
                 0,
                 &BHID_Stream,
                 &GUID_0000000c_0000_0000_c000_000000000046,
                 &v38);
    v41 = 0;
    if ( Instance >= 0 )
    {
      Instance = ((__int64 (__fastcall *)(struct IWICImagingFactory *, struct IWICColorTransform *, _QWORD, _QWORD, struct IWICBitmapDecoder **))ppv->lpVtbl->CreateDecoderFromStream)(
                   ppv,
                   v38,
                   0,
                   0,
                   &v41);
      if ( Instance >= 0 )
      {
        LODWORD(v39) = 0;
        v19 = ((__int64 (__fastcall *)(struct IWICBitmapDecoder *, __int64 *))v41->lpVtbl->GetFrameCount)(v41, &v39);
        Instance = v19;
        if ( (_DWORD)v39 )
        {
          if ( v19 >= 0 )
          {
            Instance = ((__int64 (__fastcall *)(struct IWICBitmapDecoder *, _QWORD, struct IWICBitmapFrameDecode **))v41->lpVtbl->GetFrame)(
                         v41,
                         0,
                         &v54);
            if ( Instance >= 0 )
            {
              v20 = v45;
              if ( v45 )
              {
                v45 = 0;
                ((void (__fastcall *)(struct IWICBitmapSource *))v20->lpVtbl->Release)(v20);
              }
              Instance = WICOrientateFrame(ppv, v41, v54, 1, &v45);
              if ( Instance >= 0 )
                v11 = 1;
            }
          }
        }
        else
        {
          Instance = -2147418113;
        }
      }
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v41);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v38);
  }
  v14 = v45;
  if ( !v45 )
  {
    v15 = Instance < 0;
LABEL_47:
    if ( !v15 )
      Instance = -2147418113;
  }
  v51 = 0;
  if ( Instance >= 0 )
  {
    LODWORD(v41) = 0;
    LODWORD(v39) = 0;
    Instance = ((__int64 (__fastcall *)(struct IWICBitmapSource *, struct IWICBitmapDecoder **, __int64 *))v14->lpVtbl->GetSize)(
                 v14,
                 &v41,
                 &v39);
    if ( Instance >= 0 )
    {
      if ( (unsigned int)v41 > v9 || (unsigned int)v39 > v8 )
      {
        v21 = v9;
        if ( v9 >= (int)((double)(int)v8 / (double)(int)v39 * (double)(int)v41) )
          v21 = (int)((double)(int)v8 / (double)(int)v39 * (double)(int)v41);
        if ( v8 >= (int)((double)(int)v9 / (double)(int)v41 * (double)(int)v39) )
          v8 = (int)((double)(int)v9 / (double)(int)v41 * (double)(int)v39);
        v9 = v21;
        if ( v21 <= 1 )
          v9 = 1;
        if ( v8 <= 1 )
          v8 = 1;
        v40 = 0.0;
        Instance = ((__int64 (__fastcall *)(struct IWICImagingFactory *, double *))ppv->lpVtbl->CreateBitmapScaler)(
                     ppv,
                     &v40);
        if ( Instance >= 0 )
        {
          Instance = (*(__int64 (__fastcall **)(double, struct IWICBitmapSource *, _QWORD, _QWORD, int))(**(_QWORD **)&v40 + 64LL))(
                       COERCE_DOUBLE(*(_QWORD *)&v40),
                       v45,
                       v9,
                       v8,
                       3);
          if ( Instance >= 0 )
            Instance = (***(__int64 (__fastcall ****)(double, GUID *, struct IWICBitmapSource **))&v40)(
                         COERCE_DOUBLE(*(_QWORD *)&v40),
                         &GUID_00000120_a8f2_4877_ba0a_fd2b6645fb94,
                         &v51);
        }
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v40);
      }
      else
      {
        v9 = (unsigned int)v41;
        v8 = v39;
        Instance = ((__int64 (__fastcall *)(struct IWICBitmapSource *, GUID *, struct IWICBitmapSource **))v45->lpVtbl->QueryInterface)(
                     v45,
                     &GUID_00000120_a8f2_4877_ba0a_fd2b6645fb94,
                     &v51);
      }
    }
  }
  ATL::CComPtrBase<IWICBitmapSource>::CComPtrBase<IWICBitmapSource>(&pISrc, v51);
  if ( v11 )
  {
    *(double *)&v38 = 0.0;
    if ( (int)GetsRGBTransformer(v54, v51, ppv, &v38) >= 0 )
    {
      if ( pISrc )
        ATL::AtlComPtrAssign((struct IUnknown **)&pISrc, 0);
      Instance = ATL::CComPtrBase<IWICColorTransform>::QueryInterface<IWICBitmapSource>(&v38, &pISrc);
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v38);
  }
  ATL::CComPtrBase<IWICBitmapSource>::CComPtrBase<IWICBitmapSource>(&ppIDst, pISrc);
  dstFormat = GUID_WICPixelFormat24bppRGB;
  if ( Instance >= 0 )
  {
    Buf1 = 0;
    Instance = ((__int64 (__fastcall *)(IWICBitmapSource *, GUID *))pISrc->lpVtbl->GetPixelFormat)(pISrc, &Buf1);
    if ( Instance >= 0 )
    {
      if ( (a5 & 2) != 0 )
      {
        if ( !memcmp_0(&Buf1, &GUID_WICPixelFormat8bppGray, 0x10u)
          || !memcmp_0(&Buf1, &GUID_WICPixelFormat24bppRGB, 0x10u) )
        {
          dstFormat = Buf1;
          goto LABEL_84;
        }
        if ( !memcmp_0(&Buf1, &GUID_WICPixelFormatBlackWhite, 0x10u)
          || !memcmp_0(&Buf1, &GUID_WICPixelFormat2bppGray, 0x10u)
          || !memcmp_0(&Buf1, &GUID_WICPixelFormat4bppGray, 0x10u) )
        {
          dstFormat = GUID_WICPixelFormat8bppGray;
        }
      }
      if ( ppIDst )
        ATL::AtlComPtrAssign((struct IUnknown **)&ppIDst, 0);
      Instance = WICConvertBitmapSource(&dstFormat, pISrc, &ppIDst);
    }
  }
LABEL_84:
  ppstm = 0;
  if ( Instance < 0 )
  {
    v23 = (IStream *)v48;
  }
  else
  {
    memset_0(v60, 0, 0x50u);
    v23 = (IStream *)v48;
    Instance = (*(__int64 (__fastcall **)(struct _GUID *, _QWORD *, __int64))(*(_QWORD *)&v48->Data1 + 96LL))(
                 v48,
                 v60,
                 1);
    if ( Instance >= 0 )
      Instance = CreateStreamOnHGlobal(0, 1, &ppstm);
  }
  v49 = 0;
  if ( Instance >= 0 )
  {
    v24 = &GUID_ContainerFormatBmp;
    if ( (a5 & 1) == 0 )
      v24 = &GUID_ContainerFormatJpeg;
    Instance = ((__int64 (__fastcall *)(struct IWICImagingFactory *, GUID *, GUID *, __int64 *))ppv->lpVtbl->CreateEncoder)(
                 ppv,
                 v24,
                 &GUID_VendorMicrosoft,
                 &v49);
    if ( Instance >= 0 )
      Instance = (*(__int64 (__fastcall **)(__int64, LPSTREAM, __int64))(*(_QWORD *)v49 + 24LL))(v49, ppstm, 2);
  }
  v44 = 0;
  v53 = 0;
  if ( Instance >= 0 )
  {
    Instance = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64 *))(*(_QWORD *)v49 + 80LL))(v49, &v44, &v53);
    if ( Instance >= 0 )
    {
      if ( (a5 & 2) == 0 )
        goto LABEL_156;
      v60[0] = 0;
      v60[1] = 0;
      v62 = 0;
      v61 = L"ImageQuality";
      memset(&pvarg, 0, sizeof(pvarg));
      pvarg.vt = 4;
      pvarg.lVal = 1062836634;
      Instance = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD *, VARIANTARG *))(*(_QWORD *)v53 + 32LL))(
                   v53,
                   1,
                   v60,
                   &pvarg);
      VariantClear(&pvarg);
      if ( Instance >= 0 )
      {
LABEL_156:
        Instance = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v44 + 24LL))(v44, v53);
        if ( Instance >= 0 )
        {
          Instance = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v44 + 32LL))(v44, v9, v8);
          if ( Instance >= 0 )
          {
            v40 = 0.0;
            *(double *)&v38 = 0.0;
            GetResolutionDefaulted(v45, &v40, (double *)&v38);
            if ( v40 == 0.0
              || *(double *)&v38 == 0.0
              || (Instance = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v44 + 40LL))(v44), Instance >= 0) )
            {
              (*(void (__fastcall **)(__int64, GUID *))(*(_QWORD *)v44 + 48LL))(v44, &dstFormat);
              if ( (a5 & 2) != 0 )
              {
                v40 = 0.0;
                if ( ((int (__fastcall *)(struct IWICImagingFactory *, double *))ppv->lpVtbl->CreateColorContext)(
                       ppv,
                       &v40) >= 0
                  && (*(int (__fastcall **)(double, __int64))(**(_QWORD **)&v40 + 40LL))(
                       COERCE_DOUBLE(*(_QWORD *)&v40),
                       1) >= 0 )
                {
                  (*(void (__fastcall **)(__int64, __int64, double *))(*(_QWORD *)v44 + 56LL))(v44, 1, &v40);
                }
                ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v40);
              }
              v26 = *((_QWORD *)WPP_GLOBAL_Control + 7);
              if ( v26 )
                ShellPrivateTraceEvent(v25, 0x12u, v26, 1u);
              Instance = (*(__int64 (__fastcall **)(__int64, IWICBitmapSource *, _QWORD))(*(_QWORD *)v44 + 88LL))(
                           v44,
                           ppIDst,
                           0);
              v27 = *((_QWORD *)WPP_GLOBAL_Control + 7);
              if ( v27 )
                ShellPrivateTraceEvent(v22, 0x12u, v27, 2u);
              if ( Instance >= 0 )
              {
                Instance = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v44 + 96LL))(v44);
                if ( Instance >= 0 )
                {
                  Instance = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v49 + 88LL))(v49);
                  if ( Instance >= 0 )
                  {
                    if ( v56 )
                      *v56 = v9;
                    if ( a8 )
                      *a8 = v8;
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  v28 = *((_QWORD *)WPP_GLOBAL_Control + 7);
  if ( v28 )
    ShellPrivateTraceEvent(v22, 0x13u, v28, 1u);
  v52 = 0;
  v55 = 0;
  ((void (__fastcall *)(struct IShellItem *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
    a2,
    &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93,
    &v55);
  if ( Instance >= 0 && v55 )
    (*(void (__fastcall **)(__int64, __int64, GUID *, const struct _GUID **))(*(_QWORD *)v55 + 64LL))(
      v55,
      64,
      &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99,
      &v52);
  v29 = 0;
  v43 = 0;
  if ( Instance < 0 )
    goto LABEL_132;
  CoCreateInstance(&CLSID_PhotoPropertyStore, 0, 1u, &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, (LPVOID *)&v43);
  v29 = v43;
  if ( !v43 )
    goto LABEL_132;
  *(double *)&v38 = 0.0;
  ((void (__fastcall *)(struct IUnknown *, GUID *, struct IWICColorTransform **))v43->lpVtbl->QueryInterface)(
    v43,
    &GUID_b824b49d_22ac_4161_ac8a_9916e8fa3f7f,
    &v38);
  v30 = v43;
  if ( *(double *)&v38 == 0.0 )
    goto LABEL_129;
  if ( ((int (__fastcall *)(struct IWICColorTransform *, LPSTREAM, __int64))v38->lpVtbl->GetSize)(v38, ppstm, 2) < 0 )
  {
    v30 = v43;
LABEL_129:
    if ( v30 )
      ATL::AtlComPtrAssign(&v43, 0);
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v38);
  v29 = v43;
LABEL_132:
  v31 = v52;
  if ( v52 && v29 )
  {
    memset(&pvarg, 0, sizeof(pvarg));
    v32 = 0;
    while ( 1 )
    {
      if ( (*(int (__fastcall **)(const struct _GUID *, char *, VARIANTARG *))(*(_QWORD *)&v31->Data1 + 40LL))(
             v31,
             (char *)&kaTranscodeMetadataPropertyKeys + 20 * v32,
             &pvarg) >= 0
        && pvarg.vt )
      {
        ((void (__fastcall *)(struct IUnknown *, char *, VARIANTARG *))v43->lpVtbl[2].QueryInterface)(
          v43,
          (char *)&kaTranscodeMetadataPropertyKeys + 20 * v32,
          &pvarg);
        PropVariantClear((PROPVARIANT *)&pvarg);
      }
      if ( (unsigned int)++v32 >= 0x63 )
        break;
      v31 = v52;
    }
    ((void (__fastcall *)(struct IUnknown *))v43->lpVtbl[2].AddRef)(v43);
    v23 = (IStream *)v48;
  }
  if ( Instance >= 0 )
  {
    v33 = ppstm;
    if ( ppstm != v23 )
    {
      memset_0(v60, 0, 0x50u);
      v48 = 0;
      Instance = ((__int64 (__fastcall *)(LPSTREAM, _QWORD *, __int64))v33->lpVtbl->Stat)(v33, v60, 1);
      if ( Instance >= 0 )
      {
        Instance = ((__int64 (__fastcall *)(LPSTREAM, _QWORD, _QWORD, _QWORD))ppstm->lpVtbl->Seek)(ppstm, 0, 0, 0);
        if ( Instance >= 0 )
        {
          Instance = ((__int64 (__fastcall *)(LPSTREAM, IStream *, const wchar_t *, _QWORD, struct _GUID **))ppstm->lpVtbl->CopyTo)(
                       ppstm,
                       v23,
                       v61,
                       0,
                       &v48);
          if ( Instance >= 0 && v48 != (struct _GUID *)v61 )
            Instance = -2147467259;
        }
      }
    }
  }
  v34 = WPP_GLOBAL_Control;
  v35 = *((_QWORD *)WPP_GLOBAL_Control + 7);
  if ( v35 )
  {
    ShellPrivateTraceEvent(v31, 0x13u, v35, 2u);
    v34 = WPP_GLOBAL_Control;
  }
  v36 = v34[7];
  if ( v36 )
    ShellPrivateTraceEvent(v31, 0x11u, v36, 2u);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v43);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v55);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v52);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v53);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v44);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v49);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppstm);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppIDst);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&pISrc);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v51);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v54);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v45);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180014830  mov     rax, rsp
0x180014833  mov     [rax+8], rbx
0x180014837  push    rbp
0x180014838  push    rsi
0x180014839  push    rdi
0x18001483a  push    r12
0x18001483c  push    r13
0x18001483e  push    r14
0x180014840  push    r15
0x180014842  lea     rbp, [rax-0C8h]
0x180014849  sub     rsp, 190h
0x180014850  movaps  xmmword ptr [rax-48h], xmm6
0x180014854  mov     rax, cs:__security_cookie
0x18001485b  xor     rax, rsp
0x18001485e  mov     [rbp+0C0h+var_50], rax
0x180014862  mov     ebx, r9d
0x180014865  mov     esi, r8d
0x180014868  mov     r12, rdx
0x18001486b  mov     rcx, [rbp+0C0h+arg_28]; struct _GUID *
0x180014872  mov     [rbp+0C0h+var_130], rcx
0x180014876  mov     rax, [rbp+0C0h+arg_30]
0x18001487d  mov     [rbp+0C0h+var_F0], rax
0x180014881  mov     r13, [rbp+0C0h+arg_38]
0x180014888  xor     r15d, r15d
0x18001488b  test    rax, rax
0x18001488e  jz      short loc_180014893
0x180014890  mov     [rax], r15d
0x180014893  test    r13, r13
0x180014896  jz      short loc_18001489C
0x180014898  mov     [r13+0], r15d
0x18001489c  test    r12, r12
0x18001489f  jz      loc_18001552D
0x1800148a5  test    rcx, rcx
0x1800148a8  jz      loc_18001552D
0x1800148ae  mov     r14d, dword ptr [rbp+0C0h+arg_20]
0x1800148b5  mov     eax, r14d
0x1800148b8  and     eax, 3
0x1800148bb  mov     edi, 1
0x1800148c0  sub     eax, edi
0x1800148c2  cmp     eax, edi
0x1800148c4  ja      loc_18001552D
0x1800148ca  test    r8d, r8d
0x1800148cd  jnz     short loc_1800148DE
0x1800148cf  test    ebx, ebx
0x1800148d1  jnz     loc_18001552D
0x1800148d7  or      esi, 0FFFFFFFFh
0x1800148da  mov     ebx, esi
0x1800148dc  jmp     short loc_1800148E6
0x1800148de  test    ebx, ebx
0x1800148e0  jz      loc_18001552D
0x1800148e6  mov     rax, cs:WPP_GLOBAL_Control
0x1800148ed  mov     r8, [rax+38h]; unsigned __int64
0x1800148f1  test    r8, r8
0x1800148f4  jz      short loc_180014903
0x1800148f6  mov     r9b, dil; unsigned __int8
0x1800148f9  mov     edx, 11h; unsigned int
0x1800148fe  call    ?ShellPrivateTraceEvent@@YAXPEBU_GUID@@K_KE@Z; ShellPrivateTraceEvent(_GUID const *,ulong,unsigned __int64,uchar)
0x180014903  mov     [rsp+1C0h+var_160], r15
0x180014908  lea     rax, [rsp+1C0h+var_160]
0x18001490d  mov     [rsp+1C0h+ppv], rax; ppv
0x180014912  lea     r9, _GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70; riid
0x180014919  mov     r8d, edi; dwClsContext
0x18001491c  xor     edx, edx; pUnkOuter
0x18001491e  lea     rcx, CLSID_WICImagingFactory2; rclsid
0x180014925  call    cs:__imp_CoCreateInstance
0x18001492c  nop     dword ptr [rax+rax+00h]
0x180014931  mov     edi, eax
0x180014933  mov     rcx, r15
0x180014936  mov     [rsp+1C0h+var_148], rcx
0x18001493b  mov     [rbp+0C0h+var_100], r15
0x18001493f  mov     eax, 8000FFFFh
0x180014944  test    edi, edi
0x180014946  js      loc_180014C0E
0x18001494c  mov     eax, 400h
0x180014951  cmp     esi, eax
0x180014953  ja      loc_180014ADA
0x180014959  cmp     ebx, eax
0x18001495b  ja      loc_180014ADA
0x180014961  mov     [rsp+1C0h+var_180], 0
0x18001496a  lea     rax, [rsp+1C0h+var_180]
0x18001496f  mov     [rsp+1C0h+ppv], rax; ppv
0x180014974  lea     r9, _GUID_f676c15d_596a_4ce2_8234_33996f445db1; riid
0x18001497b  xor     edx, edx; pUnkOuter
0x18001497d  lea     r8d, [rdx+1]; dwClsContext
0x180014981  lea     rcx, CLSID_LocalThumbnailCache; rclsid
0x180014988  call    cs:__imp_CoCreateInstance
0x18001498f  nop     dword ptr [rax+rax+00h]
0x180014994  mov     edi, eax
0x180014996  test    eax, eax
0x180014998  js      loc_180014AC8
0x18001499e  mov     dword ptr [rsp+1C0h+var_178], 0
0x1800149a6  xorps   xmm0, xmm0
0x1800149a9  movups  xmmword ptr [rbp+0C0h+pvarg], xmm0
0x1800149ad  mov     [rsp+1C0h+var_168], 0
0x1800149b6  mov     r10, [rsp+1C0h+var_180]
0x1800149bb  mov     rax, [r10]
0x1800149be  mov     r11, [rax+18h]
0x1800149c2  mov     edx, esi
0x1800149c4  cmp     esi, ebx
0x1800149c6  cmovbe  edx, ebx
0x1800149c9  xor     ecx, ecx
0x1800149cb  lea     r9, __ImageBase
0x1800149d2  cmp     ecx, 4
0x1800149d5  jnb     short loc_1800149EB
0x1800149d7  movsxd  rax, ecx
0x1800149da  mov     r8d, ds:rva dword_180091EC8[r9+rax*4]
0x1800149e2  cmp     edx, r8d
0x1800149e5  jbe     short loc_1800149F1
0x1800149e7  inc     ecx
0x1800149e9  jmp     short loc_1800149D2
0x1800149eb  mov     r8d, 400h
0x1800149f1  lea     rax, [rbp+0C0h+pvarg]
0x1800149f5  mov     [rsp+1C0h+var_190], rax
0x1800149fa  lea     rax, [rsp+1C0h+var_178]
0x1800149ff  mov     [rsp+1C0h+var_198], rax
0x180014a04  lea     rax, [rsp+1C0h+var_168]
0x180014a09  mov     [rsp+1C0h+ppv], rax
0x180014a0e  xor     r9d, r9d
0x180014a11  mov     rdx, r12
0x180014a14  mov     rcx, r10
0x180014a17  mov     rax, r11
0x180014a1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a1f  mov     edi, eax
0x180014a21  test    eax, eax
0x180014a23  js      loc_180014ABD
0x180014a29  test    byte ptr [rsp+1C0h+var_178], 1
0x180014a2e  jz      short loc_180014A3A
0x180014a30  mov     edi, 80004005h
0x180014a35  jmp     loc_180014ABD
0x180014a3a  mov     qword ptr [rbp+0C0h+Buf1], 0
0x180014a42  mov     rcx, [rsp+1C0h+var_168]
0x180014a47  mov     rax, [rcx]
0x180014a4a  lea     rdx, [rbp+0C0h+Buf1]
0x180014a4e  mov     rax, [rax+18h]
0x180014a52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a57  mov     edi, eax
0x180014a59  test    eax, eax
0x180014a5b  js      short loc_180014ABD
0x180014a5d  mov     [rsp+1C0h+var_170], 0
0x180014a66  mov     rcx, [rsp+1C0h+var_160]
0x180014a6b  mov     rax, [rcx]
0x180014a6e  lea     rdx, [rsp+1C0h+var_170]
0x180014a73  mov     [rsp+1C0h+ppv], rdx
0x180014a78  xor     r9d, r9d
0x180014a7b  xor     r8d, r8d
0x180014a7e  mov     rdx, qword ptr [rbp+0C0h+Buf1]
0x180014a82  mov     rax, [rax+0A8h]
0x180014a89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a8e  mov     edi, eax
0x180014a90  test    eax, eax
0x180014a92  js      short loc_180014AB2
0x180014a94  mov     rcx, [rsp+1C0h+var_170]
0x180014a99  mov     rax, [rcx]
0x180014a9c  lea     r8, [rsp+1C0h+var_148]
0x180014aa1  lea     rdx, _GUID_00000120_a8f2_4877_ba0a_fd2b6645fb94
0x180014aa8  mov     rax, [rax]
0x180014aab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ab0  mov     edi, eax
0x180014ab2  lea     rcx, [rsp+1C0h+var_170]
0x180014ab7  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180014abc  nop
0x180014abd  lea     rcx, [rsp+1C0h+var_168]
0x180014ac2  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180014ac7  nop
0x180014ac8  lea     rcx, [rsp+1C0h+var_180]
0x180014acd  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180014ad2  test    edi, edi
0x180014ad4  jns     loc_180014BFD
0x180014ada  mov     [rsp+1C0h+var_180], 0
0x180014ae3  mov     rax, [r12]
0x180014ae7  lea     rcx, [rsp+1C0h+var_180]
0x180014aec  mov     [rsp+1C0h+ppv], rcx
0x180014af1  lea     r9, _GUID_0000000c_0000_0000_c000_000000000046
0x180014af8  lea     r8, BHID_Stream
0x180014aff  xor     edx, edx
0x180014b01  mov     rcx, r12
0x180014b04  mov     rax, [rax+18h]
0x180014b08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b0d  mov     edi, eax
0x180014b0f  mov     [rsp+1C0h+var_168], 0
0x180014b18  test    eax, eax
0x180014b1a  js      loc_180014BE8
0x180014b20  mov     rcx, [rsp+1C0h+var_160]
0x180014b25  mov     rax, [rcx]
0x180014b28  lea     rdx, [rsp+1C0h+var_168]
0x180014b2d  mov     [rsp+1C0h+ppv], rdx
0x180014b32  xor     r9d, r9d
0x180014b35  xor     r8d, r8d
0x180014b38  mov     rdx, [rsp+1C0h+var_180]
0x180014b3d  mov     rax, [rax+20h]
0x180014b41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b46  mov     edi, eax
0x180014b48  test    eax, eax
0x180014b4a  js      loc_180014BE8
0x180014b50  mov     dword ptr [rsp+1C0h+var_178], 0
0x180014b58  mov     rcx, [rsp+1C0h+var_168]
0x180014b5d  mov     rax, [rcx]
0x180014b60  lea     rdx, [rsp+1C0h+var_178]
0x180014b65  mov     rax, [rax+60h]
0x180014b69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b6e  mov     edi, eax
0x180014b70  cmp     dword ptr [rsp+1C0h+var_178], 0
0x180014b75  jbe     short loc_180014BE3
0x180014b77  test    eax, eax
0x180014b79  js      short loc_180014BE8
0x180014b7b  mov     rcx, [rsp+1C0h+var_168]
0x180014b80  mov     rax, [rcx]
0x180014b83  lea     r8, [rbp+0C0h+var_100]
0x180014b87  xor     edx, edx
0x180014b89  mov     rax, [rax+68h]
0x180014b8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b92  mov     edi, eax
0x180014b94  test    eax, eax
0x180014b96  js      short loc_180014BE8
0x180014b98  mov     rcx, [rsp+1C0h+var_148]
0x180014b9d  test    rcx, rcx
0x180014ba0  jz      short loc_180014BB8
0x180014ba2  mov     [rsp+1C0h+var_148], 0
0x180014bab  mov     rax, [rcx]
0x180014bae  mov     rax, [rax+10h]
0x180014bb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014bb7  nop
0x180014bb8  lea     rax, [rsp+1C0h+var_148]
0x180014bbd  mov     [rsp+1C0h+ppv], rax; struct IWICBitmapSource **
0x180014bc2  mov     r9b, 1; bool
0x180014bc5  mov     r8, [rbp+0C0h+var_100]; struct IWICBitmapFrameDecode *
0x180014bc9  mov     rdx, [rsp+1C0h+var_168]; struct IWICBitmapDecoder *
0x180014bce  mov     rcx, [rsp+1C0h+var_160]; struct IWICImagingFactory *
0x180014bd3  call    ?WICOrientateFrame@@YAJPEAUIWICImagingFactory@@PEAUIWICBitmapDecoder@@PEAUIWICBitmapFrameDecode@@_NPEAPEAUIWICBitmapSource@@@Z; WICOrientateFrame(IWICImagingFactory *,IWICBitmapDecoder *,IWICBitmapFrameDecode *,bool,IWICBitmapSource * *)
0x180014bd8  mov     edi, eax
0x180014bda  test    eax, eax
0x180014bdc  js      short loc_180014BE8
0x180014bde  mov     r15b, 1
0x180014be1  jmp     short loc_180014BE8
0x180014be3  mov     edi, 8000FFFFh
0x180014be8  lea     rcx, [rsp+1C0h+var_168]
0x180014bed  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180014bf2  nop
0x180014bf3  lea     rcx, [rsp+1C0h+var_180]
0x180014bf8  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180014bfd  mov     rcx, [rsp+1C0h+var_148]
0x180014c02  test    rcx, rcx
0x180014c05  jnz     short loc_180014C11
0x180014c07  mov     eax, 8000FFFFh
0x180014c0c  test    edi, edi
0x180014c0e  cmovns  edi, eax
0x180014c11  mov     [rbp+0C0h+var_118], 0
0x180014c19  test    edi, edi
0x180014c1b  js      loc_180014D58
0x180014c21  mov     dword ptr [rsp+1C0h+var_168], 0
0x180014c29  mov     dword ptr [rsp+1C0h+var_178], 0
0x180014c31  mov     rax, [rcx]
0x180014c34  lea     r8, [rsp+1C0h+var_178]
0x180014c39  lea     rdx, [rsp+1C0h+var_168]
0x180014c3e  mov     rax, [rax+18h]
0x180014c42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014c47  mov     edi, eax
0x180014c49  test    eax, eax
0x180014c4b  js      loc_180014D58
0x180014c51  mov     ecx, dword ptr [rsp+1C0h+var_178]
0x180014c55  mov     eax, dword ptr [rsp+1C0h+var_168]
0x180014c59  cmp     eax, esi
0x180014c5b  ja      short loc_180014C87
0x180014c5d  cmp     ecx, ebx
0x180014c5f  ja      short loc_180014C87
0x180014c61  mov     esi, eax
0x180014c63  mov     ebx, ecx
0x180014c65  mov     rcx, [rsp+1C0h+var_148]
0x180014c6a  mov     rax, [rcx]
0x180014c6d  lea     r8, [rbp+0C0h+var_118]
0x180014c71  lea     rdx, _GUID_00000120_a8f2_4877_ba0a_fd2b6645fb94
0x180014c78  mov     rax, [rax]
0x180014c7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014c80  mov     edi, eax
0x180014c82  jmp     loc_180014D58
0x180014c87  xorps   xmm1, xmm1
0x180014c8a  cvtsi2sd xmm1, rax
0x180014c8f  xorps   xmm2, xmm2
0x180014c92  cvtsi2sd xmm2, rcx
0x180014c97  mov     eax, ebx
0x180014c99  xorps   xmm0, xmm0
0x180014c9c  cvtsi2sd xmm0, rax
0x180014ca1  divsd   xmm0, xmm2
0x180014ca5  mulsd   xmm0, xmm1
0x180014ca9  cvttsd2si rax, xmm0
0x180014cae  mov     ecx, esi
0x180014cb0  cmp     esi, eax
0x180014cb2  cmovnb  ecx, eax
0x180014cb5  mov     eax, esi
0x180014cb7  xorps   xmm0, xmm0
0x180014cba  cvtsi2sd xmm0, rax
0x180014cbf  divsd   xmm0, xmm1
0x180014cc3  mulsd   xmm0, xmm2
0x180014cc7  cvttsd2si rax, xmm0
0x180014ccc  cmp     ebx, eax
0x180014cce  cmovnb  ebx, eax
0x180014cd1  mov     esi, ecx
0x180014cd3  mov     eax, 1
0x180014cd8  cmp     ecx, eax
0x180014cda  cmovbe  esi, eax
  ... truncated ...
```
