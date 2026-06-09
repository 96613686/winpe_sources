# CImageTranscode::TranscodeImage(IShellItem *,uint,uint,ulong,IStream *,uint *,uint *)

- ea: `0x180013e70`
- end: `0x180014b74`
- name: `?TranscodeImage@CImageTranscode@@UEAAJPEAUIShellItem@@IIKPEAUIStream@@PEAI2@Z`
- size: `3332`
- prototype: `__int64 __fastcall(CImageTranscode *this, struct IShellItem *, unsigned int, unsigned int, char, struct _GUID *, unsigned int *, unsigned int *)`
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180005960`
- `0x180007804`
- `0x18000a620`
- `0x18000dce0`
- `0x18000e950`
- `0x18000fc84`
- `0x1800110b8`
- `0x180013e70`
- `0x180014b7c`
- `0x180016020`
- `0x1800169b8`
- `0x18002648c`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800149b2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800149b2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180013f65`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180013fc2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800148b8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180013f65`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180013fc2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800148b8`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18001453c`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18001453c`
- `WindowsCodecs!WICConvertBitmapSource` at `0x1800144eb`
- `WindowsCodecs!WICConvertBitmapSource` at `0x1800144eb`
- `OLEAUT32!__imp_VariantClear` at `0x180014655`
- `OLEAUT32!__imp_VariantClear` at `0x180014655`

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
      v18 = (unsigned int)dword_180090F00[i];
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
0x180013e70  mov     rax, rsp
0x180013e73  mov     [rax+8], rbx
0x180013e77  push    rbp
0x180013e78  push    rsi
0x180013e79  push    rdi
0x180013e7a  push    r12
0x180013e7c  push    r13
0x180013e7e  push    r14
0x180013e80  push    r15
0x180013e82  lea     rbp, [rax-0C8h]
0x180013e89  sub     rsp, 190h
0x180013e90  movaps  xmmword ptr [rax-48h], xmm6
0x180013e94  mov     rax, cs:__security_cookie
0x180013e9b  xor     rax, rsp
0x180013e9e  mov     [rbp+0C0h+var_50], rax
0x180013ea2  mov     ebx, r9d
0x180013ea5  mov     esi, r8d
0x180013ea8  mov     r12, rdx
0x180013eab  mov     rcx, [rbp+0C0h+arg_28]; struct _GUID *
0x180013eb2  mov     [rbp+0C0h+var_130], rcx
0x180013eb6  mov     rax, [rbp+0C0h+arg_30]
0x180013ebd  mov     [rbp+0C0h+var_F0], rax
0x180013ec1  mov     r13, [rbp+0C0h+arg_38]
0x180013ec8  xor     r15d, r15d
0x180013ecb  test    rax, rax
0x180013ece  jz      short loc_180013ED3
0x180013ed0  mov     [rax], r15d
0x180013ed3  test    r13, r13
0x180013ed6  jz      short loc_180013EDC
0x180013ed8  mov     [r13+0], r15d
0x180013edc  test    r12, r12
0x180013edf  jz      loc_180014B43
0x180013ee5  test    rcx, rcx
0x180013ee8  jz      loc_180014B43
0x180013eee  mov     r14d, dword ptr [rbp+0C0h+arg_20]
0x180013ef5  mov     eax, r14d
0x180013ef8  and     eax, 3
0x180013efb  mov     edi, 1
0x180013f00  sub     eax, edi
0x180013f02  cmp     eax, edi
0x180013f04  ja      loc_180014B43
0x180013f0a  test    r8d, r8d
0x180013f0d  jnz     short loc_180013F1E
0x180013f0f  test    ebx, ebx
0x180013f11  jnz     loc_180014B43
0x180013f17  or      esi, 0FFFFFFFFh
0x180013f1a  mov     ebx, esi
0x180013f1c  jmp     short loc_180013F26
0x180013f1e  test    ebx, ebx
0x180013f20  jz      loc_180014B43
0x180013f26  mov     rax, cs:WPP_GLOBAL_Control
0x180013f2d  mov     r8, [rax+38h]; unsigned __int64
0x180013f31  test    r8, r8
0x180013f34  jz      short loc_180013F43
0x180013f36  mov     r9b, dil; unsigned __int8
0x180013f39  mov     edx, 11h; unsigned int
0x180013f3e  call    ?ShellPrivateTraceEvent@@YAXPEBU_GUID@@K_KE@Z; ShellPrivateTraceEvent(_GUID const *,ulong,unsigned __int64,uchar)
0x180013f43  mov     [rsp+1C0h+var_160], r15
0x180013f48  lea     rax, [rsp+1C0h+var_160]
0x180013f4d  mov     [rsp+1C0h+ppv], rax; ppv
0x180013f52  lea     r9, _GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70; riid
0x180013f59  mov     r8d, edi; dwClsContext
0x180013f5c  xor     edx, edx; pUnkOuter
0x180013f5e  lea     rcx, CLSID_WICImagingFactory2; rclsid
0x180013f65  call    cs:__imp_CoCreateInstance
0x180013f6b  mov     edi, eax
0x180013f6d  mov     rcx, r15
0x180013f70  mov     [rsp+1C0h+var_148], rcx
0x180013f75  mov     [rbp+0C0h+var_100], r15
0x180013f79  mov     eax, 8000FFFFh
0x180013f7e  test    edi, edi
0x180013f80  js      loc_180014242
0x180013f86  mov     eax, 400h
0x180013f8b  cmp     esi, eax
0x180013f8d  ja      loc_18001410E
0x180013f93  cmp     ebx, eax
0x180013f95  ja      loc_18001410E
0x180013f9b  mov     [rsp+1C0h+var_180], 0
0x180013fa4  lea     rax, [rsp+1C0h+var_180]
0x180013fa9  mov     [rsp+1C0h+ppv], rax; ppv
0x180013fae  lea     r9, _GUID_f676c15d_596a_4ce2_8234_33996f445db1; riid
0x180013fb5  xor     edx, edx; pUnkOuter
0x180013fb7  lea     r8d, [rdx+1]; dwClsContext
0x180013fbb  lea     rcx, CLSID_LocalThumbnailCache; rclsid
0x180013fc2  call    cs:__imp_CoCreateInstance
0x180013fc8  mov     edi, eax
0x180013fca  test    eax, eax
0x180013fcc  js      loc_1800140FC
0x180013fd2  mov     dword ptr [rsp+1C0h+var_178], 0
0x180013fda  xorps   xmm0, xmm0
0x180013fdd  movups  xmmword ptr [rbp+0C0h+pvarg], xmm0
0x180013fe1  mov     [rsp+1C0h+var_168], 0
0x180013fea  mov     r10, [rsp+1C0h+var_180]
0x180013fef  mov     rax, [r10]
0x180013ff2  mov     r11, [rax+18h]
0x180013ff6  mov     edx, esi
0x180013ff8  cmp     esi, ebx
0x180013ffa  cmovbe  edx, ebx
0x180013ffd  xor     ecx, ecx
0x180013fff  lea     r9, __ImageBase
0x180014006  cmp     ecx, 4
0x180014009  jnb     short loc_18001401F
0x18001400b  movsxd  rax, ecx
0x18001400e  mov     r8d, ds:rva dword_180090F00[r9+rax*4]
0x180014016  cmp     edx, r8d
0x180014019  jbe     short loc_180014025
0x18001401b  inc     ecx
0x18001401d  jmp     short loc_180014006
0x18001401f  mov     r8d, 400h
0x180014025  lea     rax, [rbp+0C0h+pvarg]
0x180014029  mov     [rsp+1C0h+var_190], rax
0x18001402e  lea     rax, [rsp+1C0h+var_178]
0x180014033  mov     [rsp+1C0h+var_198], rax
0x180014038  lea     rax, [rsp+1C0h+var_168]
0x18001403d  mov     [rsp+1C0h+ppv], rax
0x180014042  xor     r9d, r9d
0x180014045  mov     rdx, r12
0x180014048  mov     rcx, r10
0x18001404b  mov     rax, r11
0x18001404e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014053  mov     edi, eax
0x180014055  test    eax, eax
0x180014057  js      loc_1800140F1
0x18001405d  test    byte ptr [rsp+1C0h+var_178], 1
0x180014062  jz      short loc_18001406E
0x180014064  mov     edi, 80004005h
0x180014069  jmp     loc_1800140F1
0x18001406e  mov     qword ptr [rbp+0C0h+Buf1], 0
0x180014076  mov     rcx, [rsp+1C0h+var_168]
0x18001407b  mov     rax, [rcx]
0x18001407e  lea     rdx, [rbp+0C0h+Buf1]
0x180014082  mov     rax, [rax+18h]
0x180014086  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001408b  mov     edi, eax
0x18001408d  test    eax, eax
0x18001408f  js      short loc_1800140F1
0x180014091  mov     [rsp+1C0h+var_170], 0
0x18001409a  mov     rcx, [rsp+1C0h+var_160]
0x18001409f  mov     rax, [rcx]
0x1800140a2  lea     rdx, [rsp+1C0h+var_170]
0x1800140a7  mov     [rsp+1C0h+ppv], rdx
0x1800140ac  xor     r9d, r9d
0x1800140af  xor     r8d, r8d
0x1800140b2  mov     rdx, qword ptr [rbp+0C0h+Buf1]
0x1800140b6  mov     rax, [rax+0A8h]
0x1800140bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800140c2  mov     edi, eax
0x1800140c4  test    eax, eax
0x1800140c6  js      short loc_1800140E6
0x1800140c8  mov     rcx, [rsp+1C0h+var_170]
0x1800140cd  mov     rax, [rcx]
0x1800140d0  lea     r8, [rsp+1C0h+var_148]
0x1800140d5  lea     rdx, _GUID_00000120_a8f2_4877_ba0a_fd2b6645fb94
0x1800140dc  mov     rax, [rax]
0x1800140df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800140e4  mov     edi, eax
0x1800140e6  lea     rcx, [rsp+1C0h+var_170]
0x1800140eb  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800140f0  nop
0x1800140f1  lea     rcx, [rsp+1C0h+var_168]
0x1800140f6  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800140fb  nop
0x1800140fc  lea     rcx, [rsp+1C0h+var_180]
0x180014101  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180014106  test    edi, edi
0x180014108  jns     loc_180014231
0x18001410e  mov     [rsp+1C0h+var_180], 0
0x180014117  mov     rax, [r12]
0x18001411b  lea     rcx, [rsp+1C0h+var_180]
0x180014120  mov     [rsp+1C0h+ppv], rcx
0x180014125  lea     r9, _GUID_0000000c_0000_0000_c000_000000000046
0x18001412c  lea     r8, BHID_Stream
0x180014133  xor     edx, edx
0x180014135  mov     rcx, r12
0x180014138  mov     rax, [rax+18h]
0x18001413c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014141  mov     edi, eax
0x180014143  mov     [rsp+1C0h+var_168], 0
0x18001414c  test    eax, eax
0x18001414e  js      loc_18001421C
0x180014154  mov     rcx, [rsp+1C0h+var_160]
0x180014159  mov     rax, [rcx]
0x18001415c  lea     rdx, [rsp+1C0h+var_168]
0x180014161  mov     [rsp+1C0h+ppv], rdx
0x180014166  xor     r9d, r9d
0x180014169  xor     r8d, r8d
0x18001416c  mov     rdx, [rsp+1C0h+var_180]
0x180014171  mov     rax, [rax+20h]
0x180014175  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001417a  mov     edi, eax
0x18001417c  test    eax, eax
0x18001417e  js      loc_18001421C
0x180014184  mov     dword ptr [rsp+1C0h+var_178], 0
0x18001418c  mov     rcx, [rsp+1C0h+var_168]
0x180014191  mov     rax, [rcx]
0x180014194  lea     rdx, [rsp+1C0h+var_178]
0x180014199  mov     rax, [rax+60h]
0x18001419d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800141a2  mov     edi, eax
0x1800141a4  cmp     dword ptr [rsp+1C0h+var_178], 0
0x1800141a9  jbe     short loc_180014217
0x1800141ab  test    eax, eax
0x1800141ad  js      short loc_18001421C
0x1800141af  mov     rcx, [rsp+1C0h+var_168]
0x1800141b4  mov     rax, [rcx]
0x1800141b7  lea     r8, [rbp+0C0h+var_100]
0x1800141bb  xor     edx, edx
0x1800141bd  mov     rax, [rax+68h]
0x1800141c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800141c6  mov     edi, eax
0x1800141c8  test    eax, eax
0x1800141ca  js      short loc_18001421C
0x1800141cc  mov     rcx, [rsp+1C0h+var_148]
0x1800141d1  test    rcx, rcx
0x1800141d4  jz      short loc_1800141EC
0x1800141d6  mov     [rsp+1C0h+var_148], 0
0x1800141df  mov     rax, [rcx]
0x1800141e2  mov     rax, [rax+10h]
0x1800141e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800141eb  nop
0x1800141ec  lea     rax, [rsp+1C0h+var_148]
0x1800141f1  mov     [rsp+1C0h+ppv], rax; struct IWICBitmapSource **
0x1800141f6  mov     r9b, 1; bool
0x1800141f9  mov     r8, [rbp+0C0h+var_100]; struct IWICBitmapFrameDecode *
0x1800141fd  mov     rdx, [rsp+1C0h+var_168]; struct IWICBitmapDecoder *
0x180014202  mov     rcx, [rsp+1C0h+var_160]; struct IWICImagingFactory *
0x180014207  call    ?WICOrientateFrame@@YAJPEAUIWICImagingFactory@@PEAUIWICBitmapDecoder@@PEAUIWICBitmapFrameDecode@@_NPEAPEAUIWICBitmapSource@@@Z; WICOrientateFrame(IWICImagingFactory *,IWICBitmapDecoder *,IWICBitmapFrameDecode *,bool,IWICBitmapSource * *)
0x18001420c  mov     edi, eax
0x18001420e  test    eax, eax
0x180014210  js      short loc_18001421C
0x180014212  mov     r15b, 1
0x180014215  jmp     short loc_18001421C
0x180014217  mov     edi, 8000FFFFh
0x18001421c  lea     rcx, [rsp+1C0h+var_168]
0x180014221  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180014226  nop
0x180014227  lea     rcx, [rsp+1C0h+var_180]
0x18001422c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180014231  mov     rcx, [rsp+1C0h+var_148]
0x180014236  test    rcx, rcx
0x180014239  jnz     short loc_180014245
0x18001423b  mov     eax, 8000FFFFh
0x180014240  test    edi, edi
0x180014242  cmovns  edi, eax
0x180014245  mov     [rbp+0C0h+var_118], 0
0x18001424d  test    edi, edi
0x18001424f  js      loc_18001438C
0x180014255  mov     dword ptr [rsp+1C0h+var_168], 0
0x18001425d  mov     dword ptr [rsp+1C0h+var_178], 0
0x180014265  mov     rax, [rcx]
0x180014268  lea     r8, [rsp+1C0h+var_178]
0x18001426d  lea     rdx, [rsp+1C0h+var_168]
0x180014272  mov     rax, [rax+18h]
0x180014276  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001427b  mov     edi, eax
0x18001427d  test    eax, eax
0x18001427f  js      loc_18001438C
0x180014285  mov     ecx, dword ptr [rsp+1C0h+var_178]
0x180014289  mov     eax, dword ptr [rsp+1C0h+var_168]
0x18001428d  cmp     eax, esi
0x18001428f  ja      short loc_1800142BB
0x180014291  cmp     ecx, ebx
0x180014293  ja      short loc_1800142BB
0x180014295  mov     esi, eax
0x180014297  mov     ebx, ecx
0x180014299  mov     rcx, [rsp+1C0h+var_148]
0x18001429e  mov     rax, [rcx]
0x1800142a1  lea     r8, [rbp+0C0h+var_118]
0x1800142a5  lea     rdx, _GUID_00000120_a8f2_4877_ba0a_fd2b6645fb94
0x1800142ac  mov     rax, [rax]
0x1800142af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800142b4  mov     edi, eax
0x1800142b6  jmp     loc_18001438C
0x1800142bb  xorps   xmm1, xmm1
0x1800142be  cvtsi2sd xmm1, rax
0x1800142c3  xorps   xmm2, xmm2
0x1800142c6  cvtsi2sd xmm2, rcx
0x1800142cb  mov     eax, ebx
0x1800142cd  xorps   xmm0, xmm0
0x1800142d0  cvtsi2sd xmm0, rax
0x1800142d5  divsd   xmm0, xmm2
0x1800142d9  mulsd   xmm0, xmm1
0x1800142dd  cvttsd2si rax, xmm0
0x1800142e2  mov     ecx, esi
0x1800142e4  cmp     esi, eax
0x1800142e6  cmovnb  ecx, eax
0x1800142e9  mov     eax, esi
0x1800142eb  xorps   xmm0, xmm0
0x1800142ee  cvtsi2sd xmm0, rax
0x1800142f3  divsd   xmm0, xmm1
0x1800142f7  mulsd   xmm0, xmm2
0x1800142fb  cvttsd2si rax, xmm0
0x180014300  cmp     ebx, eax
0x180014302  cmovnb  ebx, eax
0x180014305  mov     esi, ecx
0x180014307  mov     eax, 1
0x18001430c  cmp     ecx, eax
0x18001430e  cmovbe  esi, eax
0x180014311  cmp     ebx, eax
0x180014313  cmovbe  ebx, eax
  ... truncated ...
```
