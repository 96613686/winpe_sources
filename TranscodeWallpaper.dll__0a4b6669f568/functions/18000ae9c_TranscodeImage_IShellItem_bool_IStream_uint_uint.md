# TranscodeImage(IShellItem *,bool,IStream *,uint *,uint *)

- ea: `0x18000ae9c`
- end: `0x18000bc20`
- name: `?TranscodeImage@@YAJPEAUIShellItem@@_NPEAUIStream@@PEAI3@Z`
- size: `3460`
- prototype: `__int64 __fastcall(struct IShellItem *, __int64, struct IStream *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000ceb0`

## callees

- `0x180002170`
- `0x18000ae9c`
- `0x18000bc28`
- `0x18000bd3c`
- `0x18000bf5c`
- `0x18000d87c`
- `0x18000dd54`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000af34`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000af34`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000b1e5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000b238`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000b889`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000b1e5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000b238`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000b889`
- `WindowsCodecs!WICConvertBitmapSource` at `0x18000b715`
- `WindowsCodecs!WICConvertBitmapSource` at `0x18000b715`

## pseudocode

```c
__int64 __fastcall TranscodeImage(
        struct IShellItem *a1,
        __int64 a2,
        struct IStream *a3,
        unsigned int *a4,
        unsigned int *a5)
{
  unsigned int *v5; // r12
  unsigned int *v7; // r14
  HRESULT Instance; // ebx
  bool v9; // r13
  struct IShellItemVtbl *lpVtbl; // rax
  struct IWICImagingFactory *v11; // rbx
  HRESULT (__stdcall *CreateDecoderFromStream)(IWICImagingFactory *, IStream *, const GUID *, WICDecodeOptions, IWICBitmapDecoder **); // rdi
  struct IWICBitmapDecoder *v13; // rcx
  struct IWICBitmapDecoder *v14; // rbx
  HRESULT (__stdcall *GetFrame)(IWICBitmapDecoder *, UINT, IWICBitmapFrameDecode **); // rdi
  struct IWICBitmapFrameDecode *v16; // rcx
  struct IWICBitmapFrameDecode *v17; // rbx
  HRESULT (__stdcall *QueryInterface)(IWICBitmapFrameDecode *, const IID *const, void **); // rdi
  struct IWICBitmapSource *v19; // rcx
  unsigned int v20; // esi
  int v21; // r15d
  unsigned int v22; // ebx
  LSTATUS ValueW; // eax
  bool v24; // sf
  LSTATUS v25; // eax
  bool v26; // sf
  int v27; // ecx
  unsigned int v28; // eax
  struct IWICBitmapSource *v29; // rbx
  HRESULT (__stdcall *v30)(IWICBitmapSource *, const IID *const, void **); // rdi
  struct IWICBitmapSource *v31; // rcx
  double v32; // xmm3_8
  double v33; // xmm1_8
  unsigned int v34; // eax
  struct IWICImagingFactoryVtbl *v35; // rax
  int v36; // edx
  __int64 v37; // rbx
  __int64 (__fastcall *v38)(__int64, GUID *, struct IWICBitmapSource **); // rdi
  struct IWICBitmapSource *v39; // rcx
  IWICBitmapSource *v40; // rdi
  struct IWICBitmapFrameDecode *v41; // r14
  HRESULT (__stdcall *GetMetadataQueryReader)(IWICBitmapFrameDecode *, IWICMetadataQueryReader **); // r12
  struct IWICMetadataQueryReader *v43; // rcx
  unsigned int v44; // ecx
  unsigned int v45; // eax
  IWICBitmapSource *v46; // rdx
  IWICBitmapSource *v47; // rcx
  IWICBitmapSource *v48; // rdx
  IWICBitmapSource *v49; // rcx
  struct IWICImagingFactoryVtbl *v50; // rax
  struct IWICImagingFactoryVtbl *v51; // rax
  GUID *v52; // rdx
  __int64 v53; // rcx
  __int64 v54; // rax
  float v55; // xmm1_4
  LSTATUS v56; // eax
  bool v57; // sf
  struct IWICImagingFactoryVtbl *v58; // rax
  __int64 v59; // rbx
  void (__fastcall *v60)(__int64, __int64, DWORD *); // rsi
  __int64 (__fastcall ***v61)(__int64, GUID *, struct IWICBitmapSource **); // rcx
  char v63; // [rsp+40h] [rbp-C0h]
  unsigned int pvData; // [rsp+44h] [rbp-BCh] BYREF
  DWORD pcbData[2]; // [rsp+48h] [rbp-B8h] BYREF
  int v66; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v67; // [rsp+54h] [rbp-ACh] BYREF
  int v68; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v69; // [rsp+60h] [rbp-A0h] BYREF
  IWICBitmapSource *pISrc; // [rsp+68h] [rbp-98h] BYREF
  struct IWICBitmapSource *v71; // [rsp+70h] [rbp-90h] BYREF
  struct IWICBitmapSource *v72; // [rsp+78h] [rbp-88h] BYREF
  struct IWICImagingFactory *ppv; // [rsp+80h] [rbp-80h] BYREF
  struct IWICBitmapSource *v74; // [rsp+88h] [rbp-78h] BYREF
  struct IWICBitmapDecoder *v75; // [rsp+90h] [rbp-70h] BYREF
  __int64 v76; // [rsp+98h] [rbp-68h] BYREF
  IWICBitmapSource *ppIDst; // [rsp+A0h] [rbp-60h] BYREF
  struct IWICBitmapFrameDecode *v78; // [rsp+A8h] [rbp-58h] BYREF
  __int64 *v79; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v80; // [rsp+B8h] [rbp-48h] BYREF
  struct IWICMetadataQueryReader *v81; // [rsp+C0h] [rbp-40h] BYREF
  unsigned int *v82; // [rsp+C8h] [rbp-38h]
  __int64 v83; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v84; // [rsp+D8h] [rbp-28h] BYREF
  struct IStream *v85; // [rsp+E0h] [rbp-20h]
  _QWORD v86[3]; // [rsp+E8h] [rbp-18h] BYREF
  __int128 v87; // [rsp+100h] [rbp+0h]
  GUID v88; // [rsp+110h] [rbp+10h] BYREF
  __int64 v89; // [rsp+120h] [rbp+20h]
  GUID dstFormat; // [rsp+130h] [rbp+30h] BYREF
  __int128 Buf1; // [rsp+140h] [rbp+40h] BYREF

  v5 = a4;
  *(_QWORD *)&v88.Data1 = a4;
  v85 = a3;
  v7 = a5;
  v82 = a5;
  v83 = 0;
  v84 = 0;
  if ( a4 )
    *a4 = 0;
  if ( a5 )
    *a5 = 0;
  ppv = 0;
  Instance = CoCreateInstance(
               &CLSID_WICImagingFactory2,
               0,
               1u,
               &GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70,
               (LPVOID *)&ppv);
  v9 = 0;
  v72 = 0;
  v78 = 0;
  v75 = 0;
  Buf1 = 0;
  v63 = 0;
  if ( Instance < 0 )
    goto LABEL_27;
  lpVtbl = a1->lpVtbl;
  v74 = 0;
  Instance = ((__int64 (__fastcall *)(struct IShellItem *, _QWORD, const GUID *, GUID *, struct IWICBitmapSource **))lpVtbl->BindToHandler)(
               a1,
               0,
               &BHID_Stream,
               &GUID_0000000c_0000_0000_c000_000000000046,
               &v74);
  if ( Instance >= 0 )
  {
    v11 = ppv;
    CreateDecoderFromStream = ppv->lpVtbl->CreateDecoderFromStream;
    v13 = v75;
    v75 = 0;
    if ( v13 )
      ((void (__fastcall *)(struct IWICBitmapDecoder *))v13->lpVtbl->Release)(v13);
    Instance = ((__int64 (__fastcall *)(struct IWICImagingFactory *, struct IWICBitmapSource *, _QWORD, _QWORD, struct IWICBitmapDecoder **))CreateDecoderFromStream)(
                 v11,
                 v74,
                 0,
                 0,
                 &v75);
    if ( Instance >= 0 )
    {
      if ( ((int (__fastcall *)(struct IWICBitmapDecoder *, __int128 *))v75->lpVtbl->GetContainerFormat)(v75, &Buf1) >= 0 )
        v9 = memcmp_0(&Buf1, &GUID_ContainerFormatPng, 0x10u) == 0;
      pvData = 0;
      Instance = ((__int64 (__fastcall *)(struct IWICBitmapDecoder *, unsigned int *))v75->lpVtbl->GetFrameCount)(
                   v75,
                   &pvData);
      if ( Instance >= 0 )
      {
        if ( pvData )
        {
          v14 = v75;
          GetFrame = v75->lpVtbl->GetFrame;
          v16 = v78;
          v78 = 0;
          if ( v16 )
            ((void (__fastcall *)(struct IWICBitmapFrameDecode *))v16->lpVtbl->Release)(v16);
          Instance = ((__int64 (__fastcall *)(struct IWICBitmapDecoder *, _QWORD, struct IWICBitmapFrameDecode **))GetFrame)(
                       v14,
                       0,
                       &v78);
          if ( Instance >= 0 )
          {
            v17 = v78;
            QueryInterface = v78->lpVtbl->QueryInterface;
            v19 = v72;
            v72 = 0;
            if ( v19 )
              ((void (__fastcall *)(struct IWICBitmapSource *))v19->lpVtbl->Release)(v19);
            Instance = ((__int64 (__fastcall *)(struct IWICBitmapFrameDecode *, GUID *, struct IWICBitmapSource **))QueryInterface)(
                         v17,
                         &GUID_00000120_a8f2_4877_ba0a_fd2b6645fb94,
                         &v72);
            if ( Instance >= 0 )
            {
              ((void (__fastcall *)(struct IWICBitmapSource *, __int64 *, __int64 *))v72->lpVtbl->GetResolution)(
                v72,
                &v83,
                &v84);
              v63 = 1;
            }
          }
        }
        else
        {
          Instance = -2147418113;
        }
      }
    }
  }
  if ( v74 )
    ((void (__fastcall *)(struct IWICBitmapSource *))v74->lpVtbl->Release)(v74);
  if ( v72 )
  {
    if ( Instance >= 0 )
      Instance = ValidateBitmapProportions(v72);
  }
  else
  {
LABEL_27:
    if ( Instance >= 0 )
      Instance = -2147418113;
  }
  v71 = 0;
  v20 = -1;
  v21 = -1;
  v67 = 0;
  v68 = 0;
  if ( Instance >= 0 )
  {
    Instance = ((__int64 (__fastcall *)(struct IWICBitmapSource *, unsigned int *, int *))v72->lpVtbl->GetSize)(
                 v72,
                 &v67,
                 &v68);
    if ( Instance >= 0 )
    {
      v22 = -1;
      pvData = 0;
      v66 = 0;
      pcbData[0] = 4;
      ValueW = RegGetValueW(
                 HKEY_CURRENT_USER,
                 L"Control Panel\\Desktop",
                 L"MaxVirtualDesktopDimension",
                 0x10u,
                 0,
                 &pvData,
                 pcbData);
      v24 = ValueW < 0;
      if ( ValueW > 0 )
        v24 = 1;
      if ( v24 )
        goto LABEL_42;
      pcbData[0] = 4;
      v25 = RegGetValueW(HKEY_CURRENT_USER, L"Control Panel\\Desktop", L"MaxMonitorDimension", 0x10u, 0, &v66, pcbData);
      v26 = v25 < 0;
      if ( v25 > 0 )
        v26 = 1;
      if ( v26 )
      {
LABEL_42:
        v27 = v67;
        v21 = v68;
      }
      else
      {
        v27 = v67;
        v21 = v68;
        v28 = (int)fmax((double)v66 * ((double)(int)v67 / (double)v68), (double)v66 / ((double)(int)v67 / (double)v68));
        if ( pvData > v28 )
          v28 = pvData;
        if ( v28 != -1 )
          v22 = v28;
      }
      if ( v27 > v22 || v21 > v22 )
      {
        v33 = (double)(int)v22;
        v20 = v22;
        if ( v22 >= (int)((double)(int)v22 / (double)v21 * (double)v27) )
          v20 = (int)((double)(int)v22 / (double)v21 * (double)v27);
        v32 = (double)v21;
        v34 = (int)(v33 / (double)v27 * (double)v21);
        v21 = v22;
        if ( v22 >= v34 )
          v21 = (int)(v33 / (double)v27 * v32);
        if ( v20 <= 1 )
          v20 = 1;
        if ( (unsigned int)v21 <= 1 )
          v21 = 1;
        *(_QWORD *)pcbData = 0;
        v35 = ppv->lpVtbl;
        *(_QWORD *)pcbData = 0;
        Instance = ((__int64 (__fastcall *)(struct IWICImagingFactory *, DWORD *))v35->CreateBitmapScaler)(ppv, pcbData);
        if ( Instance >= 0 )
        {
          if ( !memcmp_0(&Buf1, &GUID_ContainerFormatJpeg, 0x10u) || (v36 = 3, v67 / v20 < 2) )
            v36 = 1;
          Instance = (*(__int64 (__fastcall **)(_QWORD, struct IWICBitmapSource *, _QWORD, _QWORD, int))(**(_QWORD **)pcbData + 64LL))(
                       *(_QWORD *)pcbData,
                       v72,
                       v20,
                       (unsigned int)v21,
                       v36);
          if ( Instance >= 0 )
          {
            v37 = *(_QWORD *)pcbData;
            v38 = ***(__int64 (__fastcall ****)(__int64, GUID *, struct IWICBitmapSource **))pcbData;
            v39 = v71;
            v71 = 0;
            if ( v39 )
              ((void (__fastcall *)(struct IWICBitmapSource *))v39->lpVtbl->Release)(v39);
            Instance = v38(v37, &GUID_00000120_a8f2_4877_ba0a_fd2b6645fb94, &v71);
          }
        }
        if ( *(_QWORD *)pcbData )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)pcbData + 16LL))(*(_QWORD *)pcbData);
      }
      else
      {
        v20 = v27;
        v29 = v72;
        v30 = v72->lpVtbl->QueryInterface;
        v31 = v71;
        v71 = 0;
        if ( v31 )
          ((void (__fastcall *)(struct IWICBitmapSource *))v31->lpVtbl->Release)(v31);
        Instance = ((__int64 (__fastcall *)(struct IWICBitmapSource *, GUID *, struct IWICBitmapSource **))v30)(
                     v29,
                     &GUID_00000120_a8f2_4877_ba0a_fd2b6645fb94,
                     &v71);
      }
    }
  }
  v40 = v71;
  v74 = v71;
  if ( v71 )
    ((void (__fastcall *)(struct IWICBitmapSource *))v71->lpVtbl->AddRef)(v71);
  v81 = 0;
  if ( Instance >= 0 && WICIsOrientationSupported(v75) )
  {
    v41 = v78;
    GetMetadataQueryReader = v78->lpVtbl->GetMetadataQueryReader;
    v43 = v81;
    v81 = 0;
    if ( v43 )
      ((void (__fastcall *)(struct IWICMetadataQueryReader *))v43->lpVtbl->Release)(v43);
    if ( ((int (__fastcall *)(struct IWICBitmapFrameDecode *, struct IWICMetadataQueryReader **))GetMetadataQueryReader)(
           v41,
           &v81) < 0 )
      goto LABEL_82;
    v74 = 0;
    if ( v40 )
      ((void (__fastcall *)(IWICBitmapSource *))v40->lpVtbl->Release)(v40);
    v74 = 0;
    Instance = WICCreateCachedOrientedBitmapSource(ppv, v71, v81, &v74);
    v40 = v74;
    if ( Instance < 0 )
      goto LABEL_82;
    pvData = 0;
    v66 = 0;
    Instance = ((__int64 (__fastcall *)(struct IWICBitmapSource *, unsigned int *, int *))v74->lpVtbl->GetSize)(
                 v74,
                 &pvData,
                 &v66);
    if ( Instance < 0 )
      goto LABEL_82;
    v44 = v67;
    if ( pvData < v66 )
      goto LABEL_80;
    if ( v67 <= v68 )
    {
LABEL_81:
      v67 = v68;
      v68 = v44;
      v45 = v20;
      v20 = v21;
      v21 = v45;
      goto LABEL_82;
    }
    if ( pvData <= v66 )
    {
LABEL_80:
      if ( v67 >= v68 )
        goto LABEL_81;
    }
LABEL_82:
    v5 = *(unsigned int **)&v88.Data1;
    v7 = v82;
  }
  pISrc = v40;
  if ( v40 )
    ((void (__fastcall *)(IWICBitmapSource *))v40->lpVtbl->AddRef)(v40);
  if ( Instance >= 0 && v63 )
  {
    v46 = pISrc;
    v47 = 0;
    pISrc = 0;
    if ( v46 )
    {
      ((void (__fastcall *)(IWICBitmapSource *))v46->lpVtbl->Release)(v46);
      v47 = pISrc;
    }
    pISrc = 0;
    if ( v47 )
      ((void (__fastcall *)(IWICBitmapSource *))v47->lpVtbl->Release)(v47);
    Instance = ColorCorrectImageWithWIC(ppv, v78, v40, &pISrc);
  }
  ppIDst = pISrc;
  if ( pISrc )
    ((void (__fastcall *)(IWICBitmapSource *))pISrc->lpVtbl->AddRef)(pISrc);
  dstFormat = GUID_WICPixelFormat24bppRGB;
  if ( Instance >= 0 )
  {
    v88 = 0;
    Instance = ((__int64 (__fastcall *)(IWICBitmapSource *, GUID *))pISrc->lpVtbl->GetPixelFormat)(pISrc, &v88);
    if ( Instance >= 0 )
    {
      if ( v9
        || !memcmp_0(&v88, &GUID_WICPixelFormat8bppGray, 0x10u)
        || !memcmp_0(&v88, &GUID_WICPixelFormat24bppRGB, 0x10u) )
      {
        dstFormat = v88;
      }
      else
      {
        if ( !memcmp_0(&v88, &GUID_WICPixelFormatBlackWhite, 0x10u)
          || !memcmp_0(&v88, &GUID_WICPixelFormat2bppGray, 0x10u)
          || !memcmp_0(&v88, &GUID_WICPixelFormat4bppGray, 0x10u) )
        {
          dstFormat = GUID_WICPixelFormat8bppGray;
        }
        v48 = ppIDst;
        v49 = 0;
        ppIDst = 0;
        if ( v48 )
        {
          ((void (__fastcall *)(IWICBitmapSource *))v48->lpVtbl->Release)(v48);
          v49 = ppIDst;
        }
        ppIDst = 0;
        if ( v49 )
          ((void (__fastcall *)(IWICBitmapSource *))v49->lpVtbl->Release)(v49);
        Instance = WICConvertBitmapSource(&dstFormat, pISrc, &ppIDst);
      }
    }
  }
  v80 = 0;
  if ( Instance >= 0 )
  {
    v50 = ppv->lpVtbl;
    v80 = 0;
    Instance = ((__int64 (__fastcall *)(struct IWICImagingFactory *, __int64 *))v50->CreateStream)(ppv, &v80);
    if ( Instance >= 0 )
      Instance = (*(__int64 (__fastcall **)(__int64, struct IStream *))(*(_QWORD *)v80 + 112LL))(v80, v85);
  }
  v79 = 0;
  if ( Instance >= 0 )
  {
    v51 = ppv->lpVtbl;
    v79 = 0;
    v52 = &GUID_ContainerFormatPng;
    if ( !v9 )
      v52 = &GUID_ContainerFormatJpeg;
    Instance = ((__int64 (__fastcall *)(struct IWICImagingFactory *, GUID *, GUID *, __int64 **))v51->CreateEncoder)(
                 ppv,
                 v52,
                 &GUID_VendorMicrosoft,
                 &v79);
    if ( Instance >= 0 )
      Instance = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64))(*v79 + 24))(v79, v80, 2);
  }
  v69 = 0;
  v53 = 0;
  v76 = 0;
  if ( Instance >= 0 )
  {
    v54 = *v79;
    v76 = 0;
    v69 = 0;
    Instance = (*(__int64 (__fastcall **)(__int64 *, __int64 *, __int64 *))(v54 + 80))(v79, &v69, &v76);
    if ( Instance >= 0 )
    {
      if ( v9 )
        goto LABEL_128;
      v55 = *(float *)&dword_180016690;
      if ( *(float *)&dword_180016690 == 0.0 )
      {
        v66 = 0;
        pcbData[0] = 4;
        v56 = RegGetValueW(HKEY_CURRENT_USER, L"Control Panel\\Desktop", L"JPEGImportQuality", 0x10u, 0, &v66, pcbData);
        v57 = v56 < 0;
        if ( v56 > 0 )
          v57 = 1;
        if ( v57 )
          v55 = FLOAT_85_0;
        else
          v55 = fminf(100.0, fmaxf((float)v66, 60.0));
        dword_180016690 = LODWORD(v55);
      }
      v86[0] = 0;
      v86[1] = 0;
      v87 = 0;
      v86[2] = L"ImageQuality";
      v88 = 0;
      v89 = 0;
      LOWORD(v88.Data1) = 4;
      *(float *)v88.Data4 = v55 / 100.0;
      Instance = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD *, GUID *))(*(_QWORD *)v76 + 32LL))(
                   v76,
                   1,
                   v86,
                   &v88);
      if ( Instance >= 0 )
      {
LABEL_128:
        Instance = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v69 + 24LL))(v69, v76);
        if ( Instance >= 0 )
        {
          Instance = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v69 + 40LL))(v69);
          if ( Instance >= 0 )
          {
            Instance = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v69 + 32LL))(
                         v69,
                         v20,
                         (unsigned int)v21);
            if ( Instance >= 0 )
            {
              (*(void (__fastcall **)(__int64, GUID *))(*(_QWORD *)v69 + 48LL))(v69, &dstFormat);
              if ( !v9 )
              {
                *(_QWORD *)pcbData = 0;
                v58 = ppv->lpVtbl;
                *(_QWORD *)pcbData = 0;
                if ( ((int (__fastcall *)(struct IWICImagingFactory *, DWORD *))v58->CreateColorContext)(ppv, pcbData) >= 0
                  && (*(int (__fastcall **)(_QWORD, __int64))(**(_QWORD **)pcbData + 40LL))(*(_QWORD *)pcbData, 1) >= 0 )
                {
                  v59 = v69;
                  v60 = *(void (__fastcall **)(__int64, __int64, DWORD *))(*(_QWORD *)v69 + 56LL);
                  v61 = *(__int64 (__fastcall ****)(__int64, GUID *, struct IWICBitmapSource **))pcbData;
                  *(_QWORD *)pcbData = 0;
                  if ( v61 )
                    ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, struct IWICBitmapSource **)))(*v61)[2])(v61);
                  v60(v59, 1, pcbData);
                }
                if ( *(_QWORD *)pcbData )
                  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)pcbData + 16LL))(*(_QWORD *)pcbData);
              }
              Instance = (*(__int64 (__fastcall **)(__int64, IWICBitmapSource *, _QWORD))(*(_QWORD *)v69 + 88LL))(
                           v69,
                           ppIDst,
                           0);
              if ( Instance >= 0 )
              {
                Instance = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v69 + 96LL))(v69);
                if ( Instance >= 0 )
                {
                  Instance = (*(__int64 (__fastcall **)(__int64 *))(*v79 + 88))(v79);
                  if ( Instance >= 0 )
                  {
                    if ( v5 )
                      *v5 = v67;
                    if ( v7 )
                      *v7 = v68;
                  }
                }
              }
            }
          }
        }
      }
    }
    v53 = v76;
  }
  if ( v53 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
  if ( v69 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v69 + 16LL))(v69);
  if ( v79 )
    (*(void (__fastcall **)(__int64 *))(*v79 + 16))(v79);
  if ( v80 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
  if ( ppIDst )
    ((void (__fastcall *)(IWICBitmapSource *))ppIDst->lpVtbl->Release)(ppIDst);
  if ( pISrc )
    ((void (__fastcall *)(IWICBitmapSource *))pISrc->lpVtbl->Release)(pISrc);
  if ( v81 )
    ((void (__fastcall *)(struct IWICMetadataQueryReader *))v81->lpVtbl->Release)(v81);
  if ( v40 )
    ((void (__fastcall *)(IWICBitmapSource *))v40->lpVtbl->Release)(v40);
  if ( v71 )
    ((void (__fastcall *)(struct IWICBitmapSource *))v71->lpVtbl->Release)(v71);
  if ( v75 )
    ((void (__fastcall *)(struct IWICBitmapDecoder *))v75->lpVtbl->Release)(v75);
  if ( v78 )
    ((void (__fastcall *)(struct IWICBitmapFrameDecode *))v78->lpVtbl->Release)(v78);
  if ( v72 )
    ((void (__fastcall *)(struct IWICBitmapSource *))v72->lpVtbl->Release)(v72);
  if ( ppv )
    ((void (__fastcall *)(struct IWICImagingFactory *))ppv->lpVtbl->Release)(ppv);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18000ae9c  mov     rax, rsp
0x18000ae9f  mov     [rax+10h], rbx
0x18000aea3  push    rbp
0x18000aea4  push    rsi
0x18000aea5  push    rdi
0x18000aea6  push    r12
0x18000aea8  push    r13
0x18000aeaa  push    r14
0x18000aeac  push    r15
0x18000aeae  lea     rbp, [rsp-70h]
0x18000aeb3  sub     rsp, 170h
0x18000aeba  movaps  xmmword ptr [rax-48h], xmm7
0x18000aebe  mov     rax, cs:__security_cookie
0x18000aec5  xor     rax, rsp
0x18000aec8  mov     [rbp+0A0h+var_50], rax
0x18000aecc  mov     r12, r9
0x18000aecf  mov     qword ptr [rbp+0A0h+var_90], r9
0x18000aed3  mov     [rbp+0A0h+var_C0], r8
0x18000aed7  mov     rdi, rcx
0x18000aeda  mov     r14, [rbp+0A0h+arg_20]
0x18000aee1  mov     [rbp+0A0h+var_D8], r14
0x18000aee5  xorps   xmm7, xmm7
0x18000aee8  movsd   [rbp+0A0h+var_D0], xmm7
0x18000aeed  movsd   [rbp+0A0h+var_C8], xmm7
0x18000aef2  test    r9, r9
0x18000aef5  jz      short loc_18000AEFE
0x18000aef7  mov     dword ptr [r9], 0
0x18000aefe  test    r14, r14
0x18000af01  jz      short loc_18000AF0A
0x18000af03  mov     dword ptr [r14], 0
0x18000af0a  mov     [rbp+0A0h+var_120], 0
0x18000af12  lea     rax, [rbp+0A0h+var_120]
0x18000af16  mov     [rsp+1A0h+ppv], rax; ppv
0x18000af1b  lea     r9, _GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70; riid
0x18000af22  mov     r15d, 1
0x18000af28  mov     r8d, r15d; dwClsContext
0x18000af2b  xor     edx, edx; pUnkOuter
0x18000af2d  lea     rcx, CLSID_WICImagingFactory2; rclsid
0x18000af34  call    cs:__imp_CoCreateInstance
0x18000af3a  mov     ebx, eax
0x18000af3c  xor     r13b, r13b
0x18000af3f  mov     [rsp+1A0h+var_128], 0
0x18000af48  mov     [rbp+0A0h+var_F8], 0
0x18000af50  mov     [rbp+0A0h+var_110], 0
0x18000af58  xorps   xmm0, xmm0
0x18000af5b  movups  [rbp+0A0h+Buf1], xmm0
0x18000af5f  mov     [rsp+1A0h+var_160], r13b
0x18000af64  mov     esi, 8000FFFFh
0x18000af69  test    eax, eax
0x18000af6b  js      loc_18000B13C
0x18000af71  mov     rax, [rdi]
0x18000af74  mov     [rbp+0A0h+var_118], 0
0x18000af7c  lea     rcx, [rbp+0A0h+var_118]
0x18000af80  mov     [rsp+1A0h+ppv], rcx
0x18000af85  lea     r9, _GUID_0000000c_0000_0000_c000_000000000046
0x18000af8c  lea     r8, BHID_Stream
0x18000af93  xor     edx, edx
0x18000af95  mov     rcx, rdi
0x18000af98  mov     rax, [rax+18h]
0x18000af9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000afa1  mov     ebx, eax
0x18000afa3  test    eax, eax
0x18000afa5  js      loc_18000B10F
0x18000afab  mov     rbx, [rbp+0A0h+var_120]
0x18000afaf  mov     rax, [rbx]
0x18000afb2  mov     rdi, [rax+20h]
0x18000afb6  mov     rcx, [rbp+0A0h+var_110]
0x18000afba  mov     [rbp+0A0h+var_110], 0
0x18000afc2  test    rcx, rcx
0x18000afc5  jz      short loc_18000AFD4
0x18000afc7  mov     rax, [rcx]
0x18000afca  mov     rax, [rax+10h]
0x18000afce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000afd3  nop
0x18000afd4  lea     rax, [rbp+0A0h+var_110]
0x18000afd8  mov     [rsp+1A0h+ppv], rax
0x18000afdd  xor     r9d, r9d
0x18000afe0  xor     r8d, r8d
0x18000afe3  mov     rdx, [rbp+0A0h+var_118]
0x18000afe7  mov     rcx, rbx
0x18000afea  mov     rax, rdi
0x18000afed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aff2  mov     ebx, eax
0x18000aff4  test    eax, eax
0x18000aff6  js      loc_18000B10F
0x18000affc  mov     rcx, [rbp+0A0h+var_110]
0x18000b000  mov     rax, [rcx]
0x18000b003  lea     rdx, [rbp+0A0h+Buf1]
0x18000b007  mov     rax, [rax+28h]
0x18000b00b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b010  test    eax, eax
0x18000b012  js      short loc_18000B034
0x18000b014  mov     r8d, 10h; Size
0x18000b01a  lea     rdx, GUID_ContainerFormatPng; Buf2
0x18000b021  lea     rcx, [rbp+0A0h+Buf1]; Buf1
0x18000b025  call    memcmp_0
0x18000b02a  movzx   r13d, r13b
0x18000b02e  test    eax, eax
0x18000b030  cmovz   r13d, r15d
0x18000b034  mov     [rsp+1A0h+var_15C], 0
0x18000b03c  mov     rcx, [rbp+0A0h+var_110]
0x18000b040  mov     rax, [rcx]
0x18000b043  lea     rdx, [rsp+1A0h+var_15C]
0x18000b048  mov     rax, [rax+60h]
0x18000b04c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b051  mov     ebx, eax
0x18000b053  test    eax, eax
0x18000b055  js      loc_18000B10F
0x18000b05b  cmp     [rsp+1A0h+var_15C], 0
0x18000b060  jbe     loc_18000B10D
0x18000b066  mov     rbx, [rbp+0A0h+var_110]
0x18000b06a  mov     rax, [rbx]
0x18000b06d  mov     rdi, [rax+68h]
0x18000b071  mov     rcx, [rbp+0A0h+var_F8]
0x18000b075  mov     [rbp+0A0h+var_F8], 0
0x18000b07d  test    rcx, rcx
0x18000b080  jz      short loc_18000B08F
0x18000b082  mov     rdx, [rcx]
0x18000b085  mov     rax, [rdx+10h]
0x18000b089  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b08e  nop
0x18000b08f  lea     r8, [rbp+0A0h+var_F8]
0x18000b093  xor     edx, edx
0x18000b095  mov     rcx, rbx
0x18000b098  mov     rax, rdi
0x18000b09b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b0a0  mov     ebx, eax
0x18000b0a2  test    eax, eax
0x18000b0a4  js      short loc_18000B10F
0x18000b0a6  mov     rbx, [rbp+0A0h+var_F8]
0x18000b0aa  mov     rax, [rbx]
0x18000b0ad  mov     rdi, [rax]
0x18000b0b0  mov     rcx, [rsp+1A0h+var_128]
0x18000b0b5  mov     [rsp+1A0h+var_128], 0
0x18000b0be  test    rcx, rcx
0x18000b0c1  jz      short loc_18000B0D0
0x18000b0c3  mov     rdx, [rcx]
0x18000b0c6  mov     rax, [rdx+10h]
0x18000b0ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b0cf  nop
0x18000b0d0  lea     r8, [rsp+1A0h+var_128]
0x18000b0d5  lea     rdx, _GUID_00000120_a8f2_4877_ba0a_fd2b6645fb94
0x18000b0dc  mov     rcx, rbx
0x18000b0df  mov     rax, rdi
0x18000b0e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b0e7  mov     ebx, eax
0x18000b0e9  test    eax, eax
0x18000b0eb  js      short loc_18000B10F
0x18000b0ed  mov     rcx, [rsp+1A0h+var_128]
0x18000b0f2  mov     rax, [rcx]
0x18000b0f5  lea     r8, [rbp+0A0h+var_C8]
0x18000b0f9  lea     rdx, [rbp+0A0h+var_D0]
0x18000b0fd  mov     rax, [rax+28h]
0x18000b101  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b106  mov     [rsp+1A0h+var_160], r15b
0x18000b10b  jmp     short loc_18000B10F
0x18000b10d  mov     ebx, esi
0x18000b10f  mov     rcx, [rbp+0A0h+var_118]
0x18000b113  test    rcx, rcx
0x18000b116  jz      short loc_18000B125
0x18000b118  mov     rax, [rcx]
0x18000b11b  mov     rax, [rax+10h]
0x18000b11f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b124  nop
0x18000b125  mov     rcx, [rsp+1A0h+var_128]; struct IWICBitmapSource *
0x18000b12a  test    rcx, rcx
0x18000b12d  jz      short loc_18000B13C
0x18000b12f  test    ebx, ebx
0x18000b131  js      short loc_18000B142
0x18000b133  call    ?ValidateBitmapProportions@@YAJPEAUIWICBitmapSource@@@Z; ValidateBitmapProportions(IWICBitmapSource *)
0x18000b138  mov     ebx, eax
0x18000b13a  jmp     short loc_18000B142
0x18000b13c  test    ebx, ebx
0x18000b13e  js      short loc_18000B142
0x18000b140  mov     ebx, esi
0x18000b142  mov     [rsp+1A0h+var_130], 0
0x18000b14b  or      esi, 0FFFFFFFFh
0x18000b14e  mov     r15d, esi
0x18000b151  mov     [rsp+1A0h+var_14C], 0
0x18000b159  mov     [rsp+1A0h+var_148], 0
0x18000b161  test    ebx, ebx
0x18000b163  js      loc_18000B435
0x18000b169  mov     rcx, [rsp+1A0h+var_128]
0x18000b16e  mov     rax, [rcx]
0x18000b171  lea     r8, [rsp+1A0h+var_148]
0x18000b176  lea     rdx, [rsp+1A0h+var_14C]
0x18000b17b  mov     rax, [rax+18h]
0x18000b17f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b184  mov     ebx, eax
0x18000b186  test    eax, eax
0x18000b188  js      loc_18000B435
0x18000b18e  mov     ebx, esi
0x18000b190  mov     [rsp+1A0h+var_15C], 0
0x18000b198  mov     [rsp+1A0h+var_150], 0
0x18000b1a0  mov     [rsp+1A0h+var_158], 4
0x18000b1a8  lea     rax, [rsp+1A0h+var_158]
0x18000b1ad  mov     [rsp+1A0h+pcbData], rax; pcbData
0x18000b1b2  lea     rax, [rsp+1A0h+var_15C]
0x18000b1b7  mov     [rsp+1A0h+pvData], rax; pvData
0x18000b1bc  mov     [rsp+1A0h+ppv], 0; pdwType
0x18000b1c5  mov     edi, 10h
0x18000b1ca  mov     r9d, edi; dwFlags
0x18000b1cd  lea     r8, Value; "MaxVirtualDesktopDimension"
0x18000b1d4  lea     rdx, SubKey; "Control Panel\\Desktop"
0x18000b1db  mov     r15, 0FFFFFFFF80000001h
0x18000b1e2  mov     rcx, r15; hkey
0x18000b1e5  call    cs:__imp_RegGetValueW
0x18000b1eb  test    eax, eax
0x18000b1ed  jle     short loc_18000B1F9
0x18000b1ef  movzx   eax, ax
0x18000b1f2  or      eax, 80070000h
0x18000b1f7  test    eax, eax
0x18000b1f9  js      loc_18000B29B
0x18000b1ff  mov     [rsp+1A0h+var_158], 4
0x18000b207  lea     rax, [rsp+1A0h+var_158]
0x18000b20c  mov     [rsp+1A0h+pcbData], rax; pcbData
0x18000b211  lea     rax, [rsp+1A0h+var_150]
0x18000b216  mov     [rsp+1A0h+pvData], rax; pvData
0x18000b21b  mov     [rsp+1A0h+ppv], 0; pdwType
0x18000b224  mov     r9d, edi; dwFlags
0x18000b227  lea     r8, aMaxmonitordime; "MaxMonitorDimension"
0x18000b22e  lea     rdx, SubKey; "Control Panel\\Desktop"
0x18000b235  mov     rcx, r15; hkey
0x18000b238  call    cs:__imp_RegGetValueW
0x18000b23e  test    eax, eax
0x18000b240  jle     short loc_18000B24C
0x18000b242  movzx   eax, ax
0x18000b245  or      eax, 80070000h
0x18000b24a  test    eax, eax
0x18000b24c  js      short loc_18000B29B
0x18000b24e  mov     ecx, [rsp+1A0h+var_14C]
0x18000b252  xorps   xmm2, xmm2
0x18000b255  cvtsi2sd xmm2, rcx
0x18000b25a  mov     r15d, [rsp+1A0h+var_148]
0x18000b25f  xorps   xmm0, xmm0
0x18000b262  cvtsi2sd xmm0, r15
0x18000b267  divsd   xmm2, xmm0
0x18000b26b  mov     eax, [rsp+1A0h+var_150]
0x18000b26f  xorps   xmm0, xmm0
0x18000b272  cvtsi2sd xmm0, rax
0x18000b277  movaps  xmm1, xmm0
0x18000b27a  mulsd   xmm1, xmm2
0x18000b27e  divsd   xmm0, xmm2
0x18000b282  maxsd   xmm1, xmm0
0x18000b286  cvttsd2si rax, xmm1
0x18000b28b  cmp     [rsp+1A0h+var_15C], eax
0x18000b28f  cmova   eax, [rsp+1A0h+var_15C]
0x18000b294  cmp     eax, esi
0x18000b296  cmovb   ebx, eax
0x18000b299  jmp     short loc_18000B2A4
0x18000b29b  mov     ecx, [rsp+1A0h+var_14C]
0x18000b29f  mov     r15d, [rsp+1A0h+var_148]
0x18000b2a4  cmp     ecx, ebx
0x18000b2a6  ja      short loc_18000B2F8
0x18000b2a8  cmp     r15d, ebx
0x18000b2ab  ja      short loc_18000B2F8
0x18000b2ad  mov     esi, ecx
0x18000b2af  mov     rbx, [rsp+1A0h+var_128]
0x18000b2b4  mov     rax, [rbx]
0x18000b2b7  mov     rdi, [rax]
0x18000b2ba  mov     rcx, [rsp+1A0h+var_130]
0x18000b2bf  mov     [rsp+1A0h+var_130], 0
0x18000b2c8  test    rcx, rcx
0x18000b2cb  jz      short loc_18000B2DA
0x18000b2cd  mov     rdx, [rcx]
0x18000b2d0  mov     rax, [rdx+10h]
0x18000b2d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b2d9  nop
0x18000b2da  lea     r8, [rsp+1A0h+var_130]
0x18000b2df  lea     rdx, _GUID_00000120_a8f2_4877_ba0a_fd2b6645fb94
0x18000b2e6  mov     rcx, rbx
0x18000b2e9  mov     rax, rdi
0x18000b2ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b2f1  mov     ebx, eax
0x18000b2f3  jmp     loc_18000B435
0x18000b2f8  mov     eax, ecx
0x18000b2fa  xorps   xmm2, xmm2
0x18000b2fd  cvtsi2sd xmm2, rax
0x18000b302  mov     eax, r15d
0x18000b305  xorps   xmm3, xmm3
0x18000b308  cvtsi2sd xmm3, rax
0x18000b30d  mov     eax, ebx
0x18000b30f  xorps   xmm1, xmm1
0x18000b312  cvtsi2sd xmm1, rax
0x18000b317  movaps  xmm0, xmm1
0x18000b31a  divsd   xmm0, xmm3
0x18000b31e  mulsd   xmm0, xmm2
0x18000b322  cvttsd2si rax, xmm0
0x18000b327  mov     esi, ebx
0x18000b329  cmp     ebx, eax
0x18000b32b  cmovnb  esi, eax
0x18000b32e  divsd   xmm1, xmm2
0x18000b332  mulsd   xmm1, xmm3
0x18000b336  cvttsd2si rax, xmm1
0x18000b33b  mov     r15d, ebx
0x18000b33e  cmp     ebx, eax
0x18000b340  cmovnb  r15d, eax
0x18000b344  mov     eax, 1
0x18000b349  cmp     esi, eax
0x18000b34b  cmovbe  esi, eax
  ... truncated ...
```
