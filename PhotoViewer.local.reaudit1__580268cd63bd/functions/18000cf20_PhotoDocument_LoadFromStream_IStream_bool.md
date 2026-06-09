# PhotoDocument::LoadFromStream(IStream *,bool)

- ea: `0x18000cf20`
- end: `0x18000d736`
- name: `?LoadFromStream@PhotoDocument@@AEAAXPEAUIStream@@_N@Z`
- size: `2070`
- prototype: `void __fastcall(PhotoDocument *__hidden this, struct IStream *, bool)`
- caller_count: `2`
- callee_count: `22`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180036f20`
- `0x18005f1bc`

## callees

- `0x18000b2b4`
- `0x18000b590`
- `0x18000cb74`
- `0x18000cf20`
- `0x18000d73c`
- `0x18000d850`
- `0x180011190`
- `0x180023ff0`
- `0x180029f30`
- `0x180032e08`
- `0x1800334e8`
- `0x1800368a4`
- `0x180037d38`
- `0x180038640`
- `0x18003945c`
- `0x18003f800`
- `0x180040264`
- `0x180059900`
- `0x18005e57c`
- `0x18005e5f0`
- `0x18007926c`
- `0x180080010`

## import_xrefs

- `USER32!SetTimer` at `0x18000d6bb`
- `USER32!SetTimer` at `0x18000d6bb`
- `ole32!CoCreateInstance` at `0x18000cf94`
- `ole32!CoCreateInstance` at `0x18000cf94`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18000cfa0`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18000d02a`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18000d032`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18000d08a`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18000d140`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18000d1f1`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18000d222`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18000d253`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18000d35a`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18000d38e`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18000d3c2`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18000d3f2`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18000d427`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18000d5bb`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18000d613`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18000d63d`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18000d6a3`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18000d722`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18000d72e`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18000cfa0`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18000d02a`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18000d032`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18000d08a`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18000d140`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18000d1f1`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18000d222`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18000d253`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18000d35a`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18000d38e`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18000d3c2`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18000d3f2`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18000d427`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18000d5bb`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18000d613`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18000d63d`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18000d6a3`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18000d722`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18000d72e`
- `PhotoBase!?StopStreamTimer@Sqm@@YAXKK@Z` at `0x18000d4ef`
- `PhotoBase!?StopStreamTimer@Sqm@@YAXKK@Z` at `0x18000d4ef`
- `PhotoBase!?IsStreamTimerActive@Sqm@@YA_NKK@Z` at `0x18000d4dd`
- `PhotoBase!?IsStreamTimerActive@Sqm@@YA_NKK@Z` at `0x18000d4dd`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
void __fastcall PhotoDocument::LoadFromStream(LPVOID *this, struct IStream *a2, char a3)
{
  _QWORD *v3; // rsi
  struct IWICBitmapFrameDecode *v4; // r12
  struct IWICImagingFactory **v5; // r13
  char *v6; // r14
  unsigned int v7; // r15d
  PhotoDocument *v9; // rdi
  HRESULT Instance; // eax
  int v11; // edx
  int v12; // eax
  struct IWICBitmapDecoder *v13; // rdx
  unsigned int v14; // esi
  struct IWICBitmapDecoder *v15; // rdx
  bool v16; // al
  int v17; // eax
  int v18; // edx
  __int64 v19; // rax
  char v20; // al
  unsigned int v21; // eax
  int v22; // eax
  int v23; // edx
  const unsigned __int16 *v24; // rcx
  __int64 v25; // rbx
  unsigned __int64 v26; // rax
  unsigned int i; // ebx
  int v28; // eax
  int v29; // edx
  int v30; // eax
  int v31; // edx
  int v32; // eax
  int v33; // edx
  __int64 v34; // rax
  unsigned int v35; // edx
  _BYTE *v36; // rsi
  __int64 v37; // rax
  int v38; // r8d
  const unsigned __int16 *v39; // rdx
  int RangedIntRegValue; // r8d
  char v41; // cl
  struct ISharedBitmap *v42; // rbx
  int v43; // eax
  int v44; // edx
  int v45; // eax
  int v46; // edx
  struct IWICBitmapSource *v47; // r13
  int v48; // eax
  int v49; // edx
  int v50; // eax
  int v51; // edx
  int v52; // eax
  int v53; // edx
  PhotoDocument *v54; // rcx
  unsigned int v55; // ebx
  double v56; // rdx
  __int64 v57; // rcx
  unsigned int v58; // r8d
  _QWORD *v59; // rax
  double v60; // rcx
  struct IWICBitmapFrameDecode *v61; // rdx
  int v62; // eax
  int v63; // edx
  __int64 v64; // r9
  __int64 v65; // rdx
  int v66; // eax
  int v67; // edx
  int v68; // eax
  int v69; // edx
  struct IUnknown *v70; // r14
  __int64 v71; // rcx
  __int64 v72; // rcx
  int v73; // eax
  int v74; // edx
  int v75; // eax
  unsigned int v77; // [rsp+34h] [rbp-144h] BYREF
  unsigned int v78; // [rsp+38h] [rbp-140h] BYREF
  struct IWICBitmapDecoder *v79; // [rsp+40h] [rbp-138h] BYREF
  unsigned int v80[2]; // [rsp+48h] [rbp-130h] BYREF
  unsigned int v81; // [rsp+50h] [rbp-128h]
  struct IWICBitmapSource *v82; // [rsp+58h] [rbp-120h] BYREF
  struct IWICBitmapFrameDecode *v83; // [rsp+60h] [rbp-118h] BYREF
  struct IUnknown *v84; // [rsp+68h] [rbp-110h] BYREF
  double v85; // [rsp+70h] [rbp-108h] BYREF
  double v86; // [rsp+78h] [rbp-100h] BYREF
  struct IWICBitmapFrameDecode *v87; // [rsp+80h] [rbp-F8h] BYREF
  struct ISharedBitmap *v88; // [rsp+88h] [rbp-F0h] BYREF
  LPVOID *v89; // [rsp+90h] [rbp-E8h]
  char *v90; // [rsp+98h] [rbp-E0h]
  _BYTE *v91; // [rsp+A0h] [rbp-D8h]
  _BYTE v92[16]; // [rsp+A8h] [rbp-D0h] BYREF
  _BYTE v93[16]; // [rsp+B8h] [rbp-C0h] BYREF
  __int128 v94; // [rsp+C8h] [rbp-B0h] BYREF
  struct _GUID v95; // [rsp+D8h] [rbp-A0h] BYREF
  _BYTE v96[16]; // [rsp+F0h] [rbp-88h] BYREF
  int v97; // [rsp+100h] [rbp-78h]
  int v98; // [rsp+104h] [rbp-74h]

  try
  {
    v9 = (PhotoDocument *)this;
    v89 = this;
    if ( !a2 )
      goto LABEL_112;
    v5 = (struct IWICImagingFactory **)(this + 25);
    v7 = 1;
    if ( !this[25] )
    {
      Instance = CoCreateInstance(
                   &CLSID_WICImagingFactory2,
                   0,
                   1u,
                   &GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70,
                   this + 25);
      if ( Instance < 0 )
        Base::Throw((Base *)(unsigned int)Instance, v11);
    }
    v4 = 0;
    v79 = 0;
    v12 = ((__int64 (__fastcall *)(struct IWICImagingFactory *, struct IStream *, _QWORD, _QWORD, struct IWICBitmapDecoder **))(*v5)->lpVtbl->CreateDecoderFromStream)(
            *v5,
            a2,
            0,
            0,
            &v79);
    v14 = v12;
    if ( v12 < 0 )
    {
      if ( v12 == -2003292336 )
      {
        memset_0(v96, 0, 0x50u);
        if ( ((int (__fastcall *)(struct IStream *, _BYTE *, __int64))a2->lpVtbl->Stat)(a2, v96, 1) >= 0 && !v98 && !v97 )
          Base::Throw((Base *)0x800710D2LL, (_DWORD)v13);
      }
      Base::Throw((Base *)v14, (_DWORD)v13);
    }
    v16 = CodecUtil::IsRawImage((CodecUtil *)v79, v13) && !CodecUtil::IsRotatableRawImage((CodecUtil *)v79, v15);
    *((_BYTE *)v9 + 344) = v16;
    v94 = 0;
    v17 = ((__int64 (__fastcall *)(struct IWICBitmapDecoder *, __int128 *))v79->lpVtbl->GetContainerFormat)(v79, &v94);
    if ( v17 < 0 )
      Base::Throw((Base *)(unsigned int)v17, v18);
    v6 = (char *)v9 + 272;
    v19 = v94 - *((_QWORD *)v9 + 34);
    if ( (_QWORD)v94 == *((_QWORD *)v9 + 34) )
      v19 = *((_QWORD *)&v94 + 1) - *((_QWORD *)v9 + 35);
    if ( v19 )
    {
      *(_OWORD *)v6 = v94;
      *(_QWORD *)v80 = 0;
      if ( ((int (__fastcall *)(struct IWICImagingFactory *, __int64, _QWORD, unsigned int *))(*v5)->lpVtbl->CreateEncoder)(
             *v5,
             (__int64)v9 + 272,
             0,
             v80) >= 0
        && *(_QWORD *)v80 )
      {
        v20 = 32;
      }
      else
      {
        v20 = 0;
      }
      *((_BYTE *)v9 + 176) &= ~0x20u;
      *((_BYTE *)v9 + 176) |= v20;
      ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(v80);
    }
    v3 = (_QWORD *)((char *)v9 + 296);
    v21 = *((_DWORD *)v9 + 76);
    if ( v21 )
      goto LABEL_29;
    while ( 1 )
    {
      v21 = v7;
LABEL_29:
      v81 = v21;
      v77 = (unsigned int)v4;
      v22 = ((__int64 (__fastcall *)(struct IWICBitmapDecoder *, unsigned int *))v79->lpVtbl->GetFrameCount)(v79, &v77);
      if ( v22 < 0 )
        Base::Throw((Base *)(unsigned int)v22, v23);
      if ( v77 )
        break;
      Base::Throw((Base *)0x80004005LL, v23);
LABEL_112:
      Base::Throw((Base *)0x80004003LL, (_DWORD)a2);
    }
    v25 = v77;
    if ( (unsigned __int64)v77 > v3[2] )
    {
      if ( !(unsigned __int8)ATL::CAtlArray<PhotoDocumentFrame,ATL::CElementTraits<PhotoDocumentFrame>>::GrowBuffer(
                               v3,
                               v77) )
      {
LABEL_40:
        for ( i = (unsigned int)v4; i < v77; ++i )
        {
          v83 = v4;
          v28 = ((__int64 (__fastcall *)(struct IWICBitmapDecoder *, _QWORD, struct IWICBitmapFrameDecode **))v79->lpVtbl->GetFrame)(
                  v79,
                  i,
                  &v83);
          if ( v28 < 0 )
            Base::Throw((Base *)(unsigned int)v28, v29);
          v82 = (struct IWICBitmapSource *)v4;
          v30 = WICOrientateFrame(*v5, v79, v83, 0, &v82);
          if ( v30 < 0 )
            Base::Throw((Base *)(unsigned int)v30, v31);
          v80[0] = (unsigned int)v4;
          v78 = (unsigned int)v4;
          v32 = ((__int64 (__fastcall *)(struct IWICBitmapSource *, unsigned int *, unsigned int *))v82->lpVtbl->GetSize)(
                  v82,
                  v80,
                  &v78);
          if ( v32 < 0 )
            Base::Throw((Base *)(unsigned int)v32, v33);
          v34 = ATL::CAtlArray<PhotoDocumentFrame,ATL::CElementTraits<PhotoDocumentFrame>>::GetAt(v3, i);
          v35 = v78;
          *(_DWORD *)(v34 + 52) = v80[0];
          *(_DWORD *)(v34 + 56) = v35;
          ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&v82);
          ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&v83);
        }
        v90 = v6;
        v36 = (char *)v9 + 176;
        v91 = (char *)v9 + 176;
        if ( (*((_BYTE *)v9 + 176) & 4) == 0 )
          goto LABEL_54;
        v37 = *(_QWORD *)v6 - *(_QWORD *)&GUID_ContainerFormatJpeg.Data1;
        if ( *(_QWORD *)v6 == *(_QWORD *)&GUID_ContainerFormatJpeg.Data1 )
          v37 = *((_QWORD *)v6 + 1) - *(_QWORD *)GUID_ContainerFormatJpeg.Data4;
        if ( v37 )
        {
LABEL_54:
          v38 = 0;
          v39 = L"PreviewMode";
        }
        else
        {
          v38 = 3;
          v39 = L"DblClkJpgPreviewMode";
        }
        RangedIntRegValue = GetRangedIntRegValue(v24, v39, v38, 0, 3);
        v41 = v7;
        if ( RangedIntRegValue != 3 )
          v41 = a3;
        if ( !v41 )
        {
          try
          {
            v88 = (struct ISharedBitmap *)v4;
            PhotoDocument::GetThumbnail(v9, &v88, RangedIntRegValue);
            v42 = v88;
            if ( v88 )
            {
              v87 = v4;
              v43 = ((__int64 (__fastcall *)(struct IWICBitmapDecoder *, _QWORD, struct IWICBitmapFrameDecode **))v79->lpVtbl->GetFrame)(
                      v79,
                      0,
                      &v87);
              if ( v43 < 0 )
                Base::Throw((Base *)(unsigned int)v43, v44);
              v82 = (struct IWICBitmapSource *)v4;
              v45 = WICOrientateFrame(*v5, v79, v87, 0, &v82);
              if ( v45 < 0 )
                Base::Throw((Base *)(unsigned int)v45, v46);
              v95 = 0;
              v47 = v82;
              v48 = ((__int64 (__fastcall *)(struct IWICBitmapSource *, struct _GUID *))v82->lpVtbl->GetPixelFormat)(
                      v82,
                      &v95);
              if ( v48 < 0 )
                Base::Throw((Base *)(unsigned int)v48, v49);
              v78 = (unsigned int)v4;
              v80[0] = (unsigned int)v4;
              v50 = ((__int64 (__fastcall *)(struct IWICBitmapSource *, unsigned int *, unsigned int *))v47->lpVtbl->GetSize)(
                      v47,
                      &v78,
                      v80);
              if ( v50 < 0 )
                Base::Throw((Base *)(unsigned int)v50, v51);
              v86 = 0.0;
              v85 = 0.0;
              v52 = ((__int64 (__fastcall *)(struct IWICBitmapSource *, double *, double *))v47->lpVtbl->GetResolution)(
                      v47,
                      &v86,
                      &v85);
              if ( v52 < 0 )
                Base::Throw((Base *)(unsigned int)v52, v53);
              v83 = v4;
              PhotoDocument::CreateImageLayerFromThumbnail(v54, v42, (struct IImageLayer **)&v83, v78, v80[0]);
              PhotoDocument::SetImageLayerIntoFrame(v9, 0, (struct IImageLayer *)v83, &v95, v86, v85);
              ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&v83);
              ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&v82);
              ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&v87);
            }
            ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&v88);
          }
          catch ( Base::Exception v92 )
          {
            Base::Exception::~Exception((Base::Exception *)v92);
            v7 = 1;
            v4 = 0;
            v6 = v90;
            v9 = (PhotoDocument *)v89;
            v36 = v91;
          }
        }
        v55 = v81;
        if ( Sqm::IsStreamTimerActive((Sqm *)0x948, v7, RangedIntRegValue) )
          Sqm::StopStreamTimer((Sqm *)0x948, v7, v58);
        if ( v77 != v55 )
        {
          if ( *((_DWORD *)v9 + 72) >= v77 )
            (*(void (__fastcall **)(__int64, _QWORD))(*((_QWORD *)v9 + 3) + 40LL))((__int64)v9 + 24, 0);
          v56 = *((double *)v9 + 27);
          v85 = v56;
          while ( v56 != 0.0 )
          {
            v59 = (_QWORD *)ATL::CAtlList<ATL::CComQIPtr<IEaselPhodeoEventSink,&__s_GUID const _GUID_c7061507_0070_4aad_8548_fd93e8221e42>,ATL::CComQIPtrElementTraits<IEaselPhodeoEventSink,&__s_GUID const _GUID_c7061507_0070_4aad_8548_fd93e8221e42>>::GetAt();
            ATL::CComQIPtr<IMultiPageEventSink,&__s_GUID const _GUID_8b39cf88_257a_497f_b632_57f90bc4aa08>::CComQIPtr<IMultiPageEventSink,&__s_GUID const _GUID_8b39cf88_257a_497f_b632_57f90bc4aa08>(
              &v86,
              *v59);
            v60 = v86;
            if ( v86 != 0.0 )
            {
              v61 = (struct IWICBitmapFrameDecode *)((char *)v9 + 24);
              if ( !v9 )
                v61 = v4;
              (*(void (__fastcall **)(double, struct IWICBitmapFrameDecode *, _QWORD))(**(_QWORD **)&v86 + 24LL))(
                COERCE_DOUBLE(*(_QWORD *)&v86),
                v61,
                v77);
            }
            ATL::CAtlList<ATL::CComQIPtr<IEaselPhodeoEventSink,&__s_GUID const _GUID_c7061507_0070_4aad_8548_fd93e8221e42>,ATL::CComQIPtrElementTraits<IEaselPhodeoEventSink,&__s_GUID const _GUID_c7061507_0070_4aad_8548_fd93e8221e42>>::GetNext(
              *(_QWORD *)&v60,
              &v85);
            ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&v86);
            v56 = v85;
          }
        }
        if ( *((_DWORD *)v9 + 47) != -2147483638 )
        {
          *v36 &= ~0x10u;
          *((_DWORD *)v9 + 47) = -2147483638;
          PhotoDocument::Notify(v9, v7);
        }
        v84 = (struct IUnknown *)v4;
        v62 = ATL::CComCreator<ATL::CComObject<PhotoDocumentLoadWorker>>::CreateInstance(v57, *(_QWORD *)&v56, &v84);
        if ( v62 < 0 )
          Base::Throw((Base *)(unsigned int)v62, v63);
        if ( (*v36 & 1) == 0 )
          goto LABEL_93;
        LOBYTE(v64) = 0;
        if ( *((_DWORD *)v9 + 47) != 1 )
        {
          v65 = *(_QWORD *)v6 - *(_QWORD *)&GUID_ContainerFormatGif.Data1;
          if ( *(_QWORD *)v6 == *(_QWORD *)&GUID_ContainerFormatGif.Data1 )
            v65 = *((_QWORD *)v6 + 1) - *(_QWORD *)GUID_ContainerFormatGif.Data4;
          if ( !v65 )
LABEL_93:
            LOBYTE(v64) = 1;
        }
        v66 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, _QWORD, __int64))v84->lpVtbl[2].Release)(
                v84,
                *((_QWORD *)v9 + 42),
                *((_QWORD *)v9 + 6),
                v64);
        if ( v66 < 0 )
          Base::Throw((Base *)(unsigned int)v66, v67);
        v68 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD))v84->lpVtbl[1].Release)(
                v84,
                (unsigned int)((*v36 & 8) != 0) - 1);
        if ( v68 < 0 )
          Base::Throw((Base *)(unsigned int)v68, v69);
        v70 = v84;
        v71 = *((_QWORD *)v9 + 26);
        if ( v71 )
          (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v71 + 72LL))(v71, *((_QWORD *)v9 + 41));
        if ( *((struct IUnknown **)v9 + 26) != v70 )
          ATL::AtlComPtrAssign((struct IUnknown **)v9 + 26, v70);
        if ( (*v36 & 4) != 0 )
        {
          v72 = *((_QWORD *)v9 + 26);
          if ( v72 )
          {
            v73 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v72 + 24LL))(v72);
            if ( v73 < 0 )
              Base::Throw((Base *)(unsigned int)v73, v74);
          }
        }
        else
        {
          SetTimer(*((HWND *)v9 + 6), 0x6D61u, v7, 0);
        }
        if ( v84 )
          ((void (__fastcall *)(struct IUnknown *))v84->lpVtbl->Release)(v84);
        if ( v79 )
          ((void (__fastcall *)(struct IWICBitmapDecoder *))v79->lpVtbl->Release)(v79);
        return;
      }
      ATL::CAtlArray<PhotoDocumentFrame,ATL::CElementTraits<PhotoDocumentFrame>>::CallConstructors(
        *v3 + 80LL * v3[1],
        v25 - v3[1]);
    }
    else
    {
      v26 = v3[1];
      if ( v77 <= v26 )
      {
        if ( v77 < v26 )
          ATL::CAtlArray<PhotoDocumentFrame,ATL::CElementTraits<PhotoDocumentFrame>>::CallDestructors(
            *v3 + 80LL * v77,
            v26 - v77);
      }
      else
      {
        ATL::CAtlArray<PhotoDocumentFrame,ATL::CElementTraits<PhotoDocumentFrame>>::CallConstructors(
          *v3 + 80 * v26,
          v77 - v26);
      }
    }
    v3[1] = v25;
    goto LABEL_40;
  }
  catch ( Base::Exception v93 )
  {
    v75 = Base::Exception::operator long(v93);
    PhotoDocument::SetLoadStatus((PhotoDocument *)v89, v75);
    throw;
  }
}

```

## disassembly

```asm
0x18000cf20  mov     [rsp+arg_10], rbx
0x18000cf25  mov     [rsp+arg_18], rsi
0x18000cf2a  push    rdi
0x18000cf2b  push    r12
0x18000cf2d  push    r13
0x18000cf2f  push    r14
0x18000cf31  push    r15
0x18000cf33  sub     rsp, 150h
0x18000cf3a  mov     rax, cs:__security_cookie
0x18000cf41  xor     rax, rsp
0x18000cf44  mov     [rsp+178h+var_38], rax
0x18000cf4c  mov     [rsp+178h+var_148], r8b
0x18000cf51  mov     rbx, rdx
0x18000cf54  mov     rdi, rcx
0x18000cf57  mov     [rsp+178h+var_E8], rcx
0x18000cf5f  test    rdx, rdx
0x18000cf62  jz      loc_18000D729
0x18000cf68  lea     r13, [rcx+0C8h]
0x18000cf6f  mov     r15d, 1
0x18000cf75  cmp     qword ptr [r13+0], 0
0x18000cf7a  jnz     short loc_18000CFA6
0x18000cf7c  mov     [rsp+178h+ppv], r13; ppv
0x18000cf81  lea     r9, _GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70; riid
0x18000cf88  mov     r8d, r15d; dwClsContext
0x18000cf8b  xor     edx, edx; pUnkOuter
0x18000cf8d  lea     rcx, CLSID_WICImagingFactory2; rclsid
0x18000cf94  call    cs:__imp_CoCreateInstance
0x18000cf9a  test    eax, eax
0x18000cf9c  jns     short loc_18000CFA6
0x18000cf9e  mov     ecx, eax
0x18000cfa0  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18000cfa6  xor     r12d, r12d
0x18000cfa9  mov     [rsp+178h+var_138], r12
0x18000cfae  mov     rcx, [r13+0]
0x18000cfb2  mov     rax, [rcx]
0x18000cfb5  lea     rdx, [rsp+178h+var_138]
0x18000cfba  mov     [rsp+178h+ppv], rdx
0x18000cfbf  xor     r9d, r9d
0x18000cfc2  xor     r8d, r8d
0x18000cfc5  mov     rdx, rbx
0x18000cfc8  mov     rax, [rax+20h]
0x18000cfcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cfd1  mov     esi, eax
0x18000cfd3  test    eax, eax
0x18000cfd5  jns     short loc_18000D038
0x18000cfd7  cmp     eax, 88982F50h
0x18000cfdc  jnz     short loc_18000D030
0x18000cfde  xor     edx, edx; Val
0x18000cfe0  mov     r8d, 50h ; 'P'; Size
0x18000cfe6  lea     rcx, [rsp+178h+var_88]; void *
0x18000cfee  call    memset_0
0x18000cff3  mov     rdx, [rbx]
0x18000cff6  mov     rax, [rdx+60h]
0x18000cffa  mov     r8d, r15d
0x18000cffd  lea     rdx, [rsp+178h+var_88]
0x18000d005  mov     rcx, rbx
0x18000d008  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d00d  test    eax, eax
0x18000d00f  js      short loc_18000D030
0x18000d011  cmp     [rsp+178h+var_74], r12d
0x18000d019  jnz     short loc_18000D030
0x18000d01b  cmp     [rsp+178h+var_78], r12d
0x18000d023  jnz     short loc_18000D030
0x18000d025  mov     ecx, 800710D2h
0x18000d02a  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18000d030  mov     ecx, esi
0x18000d032  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18000d038  mov     rcx, [rsp+178h+var_138]; this
0x18000d03d  call    ?IsRawImage@CodecUtil@@YA_NPEAUIWICBitmapDecoder@@@Z; CodecUtil::IsRawImage(IWICBitmapDecoder *)
0x18000d042  test    al, al
0x18000d044  jz      short loc_18000D058
0x18000d046  mov     rcx, [rsp+178h+var_138]; this
0x18000d04b  call    ?IsRotatableRawImage@CodecUtil@@YA_NPEAUIWICBitmapDecoder@@@Z; CodecUtil::IsRotatableRawImage(IWICBitmapDecoder *)
0x18000d050  test    al, al
0x18000d052  jnz     short loc_18000D058
0x18000d054  mov     al, 1
0x18000d056  jmp     short loc_18000D05A
0x18000d058  xor     al, al
0x18000d05a  mov     [rdi+158h], al
0x18000d060  xorps   xmm0, xmm0
0x18000d063  movups  [rsp+178h+var_B0], xmm0
0x18000d06b  mov     rcx, [rsp+178h+var_138]
0x18000d070  mov     rax, [rcx]
0x18000d073  lea     rdx, [rsp+178h+var_B0]
0x18000d07b  mov     rax, [rax+28h]
0x18000d07f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d084  test    eax, eax
0x18000d086  jns     short loc_18000D090
0x18000d088  mov     ecx, eax
0x18000d08a  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18000d090  lea     r14, [rdi+110h]
0x18000d097  mov     rax, qword ptr [rsp+178h+var_B0]
0x18000d09f  sub     rax, [r14]
0x18000d0a2  jnz     short loc_18000D0B0
0x18000d0a4  mov     rax, qword ptr [rsp+178h+var_B0+8]
0x18000d0ac  sub     rax, [r14+8]
0x18000d0b0  test    rax, rax
0x18000d0b3  jz      short loc_18000D10A
0x18000d0b5  movups  xmm0, [rsp+178h+var_B0]
0x18000d0bd  movups  xmmword ptr [r14], xmm0
0x18000d0c1  mov     qword ptr [rsp+178h+var_130], r12
0x18000d0c6  mov     rcx, [r13+0]
0x18000d0ca  mov     rax, [rcx]
0x18000d0cd  lea     r9, [rsp+178h+var_130]
0x18000d0d2  xor     r8d, r8d
0x18000d0d5  mov     rdx, r14
0x18000d0d8  mov     rax, [rax+40h]
0x18000d0dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d0e1  test    eax, eax
0x18000d0e3  js      short loc_18000D0F1
0x18000d0e5  cmp     qword ptr [rsp+178h+var_130], 0
0x18000d0eb  jz      short loc_18000D0F1
0x18000d0ed  mov     al, 20h ; ' '
0x18000d0ef  jmp     short loc_18000D0F3
0x18000d0f1  xor     al, al
0x18000d0f3  and     byte ptr [rdi+0B0h], 0DFh
0x18000d0fa  or      [rdi+0B0h], al
0x18000d100  lea     rcx, [rsp+178h+var_130]
0x18000d105  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x18000d10a  lea     rsi, [rdi+128h]
0x18000d111  mov     eax, [rsi+8]
0x18000d114  cmp     eax, 1
0x18000d117  cmovb   eax, r15d
0x18000d11b  mov     [rsp+178h+var_128], eax
0x18000d11f  mov     [rsp+178h+var_144], r12d
0x18000d124  mov     rcx, [rsp+178h+var_138]
0x18000d129  mov     rax, [rcx]
0x18000d12c  lea     rdx, [rsp+178h+var_144]
0x18000d131  mov     rax, [rax+60h]
0x18000d135  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d13a  test    eax, eax
0x18000d13c  jns     short loc_18000D146
0x18000d13e  mov     ecx, eax
0x18000d140  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18000d146  mov     eax, [rsp+178h+var_144]
0x18000d14a  test    eax, eax
0x18000d14c  jz      loc_18000D71D
0x18000d152  mov     ebx, eax
0x18000d154  cmp     rax, [rsi+10h]
0x18000d158  ja      short loc_18000D194
0x18000d15a  mov     rax, [rsi+8]
0x18000d15e  cmp     rbx, rax
0x18000d161  jbe     short loc_18000D17A
0x18000d163  mov     edx, ebx
0x18000d165  sub     rdx, rax
0x18000d168  lea     rcx, [rax+rax*4]
0x18000d16c  shl     rcx, 4
0x18000d170  add     rcx, [rsi]
0x18000d173  call    ?CallConstructors@?$CAtlArray@VPhotoDocumentFrame@@V?$CElementTraits@VPhotoDocumentFrame@@@ATL@@@ATL@@CAXPEAVPhotoDocumentFrame@@_K@Z; ATL::CAtlArray<PhotoDocumentFrame,ATL::CElementTraits<PhotoDocumentFrame>>::CallConstructors(PhotoDocumentFrame *,unsigned __int64)
0x18000d178  jmp     short loc_18000D1BD
0x18000d17a  jnb     short loc_18000D1BD
0x18000d17c  sub     rax, rbx
0x18000d17f  lea     rcx, [rbx+rbx*4]
0x18000d183  shl     rcx, 4
0x18000d187  add     rcx, [rsi]
0x18000d18a  mov     rdx, rax
0x18000d18d  call    ?CallDestructors@?$CAtlArray@VPhotoDocumentFrame@@V?$CElementTraits@VPhotoDocumentFrame@@@ATL@@@ATL@@CAXPEAVPhotoDocumentFrame@@_K@Z; ATL::CAtlArray<PhotoDocumentFrame,ATL::CElementTraits<PhotoDocumentFrame>>::CallDestructors(PhotoDocumentFrame *,unsigned __int64)
0x18000d192  jmp     short loc_18000D1BD
0x18000d194  mov     rdx, rbx
0x18000d197  mov     rcx, rsi
0x18000d19a  call    ?GrowBuffer@?$CAtlArray@VPhotoDocumentFrame@@V?$CElementTraits@VPhotoDocumentFrame@@@ATL@@@ATL@@AEAA_N_K@Z; ATL::CAtlArray<PhotoDocumentFrame,ATL::CElementTraits<PhotoDocumentFrame>>::GrowBuffer(unsigned __int64)
0x18000d19f  test    al, al
0x18000d1a1  jz      short loc_18000D1C1
0x18000d1a3  mov     rax, [rsi+8]
0x18000d1a7  mov     rdx, rbx
0x18000d1aa  sub     rdx, rax
0x18000d1ad  lea     rcx, [rax+rax*4]
0x18000d1b1  shl     rcx, 4
0x18000d1b5  add     rcx, [rsi]
0x18000d1b8  call    ?CallConstructors@?$CAtlArray@VPhotoDocumentFrame@@V?$CElementTraits@VPhotoDocumentFrame@@@ATL@@@ATL@@CAXPEAVPhotoDocumentFrame@@_K@Z; ATL::CAtlArray<PhotoDocumentFrame,ATL::CElementTraits<PhotoDocumentFrame>>::CallConstructors(PhotoDocumentFrame *,unsigned __int64)
0x18000d1bd  mov     [rsi+8], rbx
0x18000d1c1  mov     ebx, r12d
0x18000d1c4  cmp     ebx, [rsp+178h+var_144]
0x18000d1c8  jnb     loc_18000D28D
0x18000d1ce  mov     [rsp+178h+var_118], r12
0x18000d1d3  mov     rcx, [rsp+178h+var_138]
0x18000d1d8  mov     rax, [rcx]
0x18000d1db  lea     r8, [rsp+178h+var_118]
0x18000d1e0  mov     edx, ebx
0x18000d1e2  mov     rax, [rax+68h]
0x18000d1e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d1eb  test    eax, eax
0x18000d1ed  jns     short loc_18000D1F7
0x18000d1ef  mov     ecx, eax
0x18000d1f1  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18000d1f7  mov     [rsp+178h+var_120], r12
0x18000d1fc  lea     rax, [rsp+178h+var_120]
0x18000d201  mov     [rsp+178h+ppv], rax; struct IWICBitmapSource **
0x18000d206  xor     r9d, r9d; bool
0x18000d209  mov     r8, [rsp+178h+var_118]; struct IWICBitmapFrameDecode *
0x18000d20e  mov     rdx, [rsp+178h+var_138]; struct IWICBitmapDecoder *
0x18000d213  mov     rcx, [r13+0]; struct IWICImagingFactory *
0x18000d217  call    ?WICOrientateFrame@@YAJPEAUIWICImagingFactory@@PEAUIWICBitmapDecoder@@PEAUIWICBitmapFrameDecode@@_NPEAPEAUIWICBitmapSource@@@Z; WICOrientateFrame(IWICImagingFactory *,IWICBitmapDecoder *,IWICBitmapFrameDecode *,bool,IWICBitmapSource * *)
0x18000d21c  test    eax, eax
0x18000d21e  jns     short loc_18000D228
0x18000d220  mov     ecx, eax
0x18000d222  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18000d228  mov     [rsp+178h+var_130], r12d
0x18000d22d  mov     [rsp+178h+var_140], r12d
0x18000d232  mov     rcx, [rsp+178h+var_120]
0x18000d237  mov     rax, [rcx]
0x18000d23a  lea     r8, [rsp+178h+var_140]
0x18000d23f  lea     rdx, [rsp+178h+var_130]
0x18000d244  mov     rax, [rax+18h]
0x18000d248  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d24d  test    eax, eax
0x18000d24f  jns     short loc_18000D259
0x18000d251  mov     ecx, eax
0x18000d253  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18000d259  mov     edx, ebx
0x18000d25b  mov     rcx, rsi
0x18000d25e  call    ?GetAt@?$CAtlArray@VPhotoDocumentFrame@@V?$CElementTraits@VPhotoDocumentFrame@@@ATL@@@ATL@@QEAAAEAVPhotoDocumentFrame@@_K@Z; ATL::CAtlArray<PhotoDocumentFrame,ATL::CElementTraits<PhotoDocumentFrame>>::GetAt(unsigned __int64)
0x18000d263  mov     edx, [rsp+178h+var_140]
0x18000d267  mov     ecx, [rsp+178h+var_130]
0x18000d26b  mov     [rax+34h], ecx
0x18000d26e  mov     [rax+38h], edx
0x18000d271  lea     rcx, [rsp+178h+var_120]
0x18000d276  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x18000d27b  nop
0x18000d27c  lea     rcx, [rsp+178h+var_118]
0x18000d281  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x18000d286  inc     ebx
0x18000d288  jmp     loc_18000D1C4
0x18000d28d  mov     [rsp+178h+var_E0], r14
0x18000d295  lea     rsi, [rdi+0B0h]
0x18000d29c  mov     [rsp+178h+var_D8], rsi
0x18000d2a4  test    byte ptr [rsi], 4
0x18000d2a7  jz      short loc_18000D2D4
0x18000d2a9  mov     rax, [r14]
0x18000d2ac  sub     rax, qword ptr cs:GUID_ContainerFormatJpeg.Data1
0x18000d2b3  jnz     short loc_18000D2C0
0x18000d2b5  mov     rax, [r14+8]
0x18000d2b9  sub     rax, qword ptr cs:GUID_ContainerFormatJpeg.Data4
0x18000d2c0  test    rax, rax
0x18000d2c3  jnz     short loc_18000D2D4
0x18000d2c5  mov     r8d, 3
0x18000d2cb  lea     rdx, aDblclkjpgprevi; "DblClkJpgPreviewMode"
0x18000d2d2  jmp     short loc_18000D2DE
0x18000d2d4  xor     r8d, r8d; int
0x18000d2d7  lea     rdx, aPreviewmode; "PreviewMode"
0x18000d2de  mov     dword ptr [rsp+178h+ppv], 3; int
0x18000d2e6  xor     r9d, r9d; int
0x18000d2e9  call    ?GetRangedIntRegValue@@YAHPEBG0HHH@Z; GetRangedIntRegValue(ushort const *,ushort const *,int,int,int)
0x18000d2ee  mov     r8d, eax; int
0x18000d2f1  mov     ecx, r15d
0x18000d2f4  movzx   eax, [rsp+178h+var_148]
0x18000d2f9  cmp     r8d, 3
0x18000d2fd  cmovnz  ecx, eax
0x18000d300  test    cl, cl
0x18000d302  jnz     loc_18000D4D1
0x18000d308  mov     [rsp+178h+var_F0], r12
0x18000d310  lea     rdx, [rsp+178h+var_F0]; struct ISharedBitmap **
0x18000d318  mov     rcx, rdi; this
0x18000d31b  call    ?GetThumbnail@PhotoDocument@@AEAAXPEAPEAUISharedBitmap@@H@Z; PhotoDocument::GetThumbnail(ISharedBitmap * *,int)
0x18000d320  mov     rbx, [rsp+178h+var_F0]
0x18000d328  test    rbx, rbx
0x18000d32b  jz      loc_18000D4A0
0x18000d331  mov     [rsp+178h+var_F8], r12
0x18000d339  mov     rcx, [rsp+178h+var_138]
0x18000d33e  mov     rax, [rcx]
0x18000d341  lea     r8, [rsp+178h+var_F8]
0x18000d349  xor     edx, edx
0x18000d34b  mov     rax, [rax+68h]
0x18000d34f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d354  test    eax, eax
0x18000d356  jns     short loc_18000D360
0x18000d358  mov     ecx, eax
0x18000d35a  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18000d360  mov     [rsp+178h+var_120], r12
0x18000d365  lea     rax, [rsp+178h+var_120]
0x18000d36a  mov     [rsp+178h+ppv], rax; struct IWICBitmapSource **
0x18000d36f  xor     r9d, r9d; bool
0x18000d372  mov     r8, [rsp+178h+var_F8]; struct IWICBitmapFrameDecode *
0x18000d37a  mov     rdx, [rsp+178h+var_138]; struct IWICBitmapDecoder *
0x18000d37f  mov     rcx, [r13+0]; struct IWICImagingFactory *
0x18000d383  call    ?WICOrientateFrame@@YAJPEAUIWICImagingFactory@@PEAUIWICBitmapDecoder@@PEAUIWICBitmapFrameDecode@@_NPEAPEAUIWICBitmapSource@@@Z; WICOrientateFrame(IWICImagingFactory *,IWICBitmapDecoder *,IWICBitmapFrameDecode *,bool,IWICBitmapSource * *)
0x18000d388  test    eax, eax
0x18000d38a  jns     short loc_18000D394
0x18000d38c  mov     ecx, eax
0x18000d38e  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18000d394  xorps   xmm0, xmm0
0x18000d397  movups  xmmword ptr [rsp+178h+var_A0.Data1], xmm0
0x18000d39f  mov     r13, [rsp+178h+var_120]
0x18000d3a4  mov     rax, [r13+0]
0x18000d3a8  lea     rdx, [rsp+178h+var_A0]
0x18000d3b0  mov     rcx, r13
0x18000d3b3  mov     rax, [rax+20h]
0x18000d3b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3bc  test    eax, eax
0x18000d3be  jns     short loc_18000D3C8
0x18000d3c0  mov     ecx, eax
0x18000d3c2  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18000d3c8  mov     [rsp+178h+var_140], r12d
0x18000d3cd  mov     [rsp+178h+var_130], r12d
0x18000d3d2  mov     rax, [r13+0]
0x18000d3d6  lea     r8, [rsp+178h+var_130]
0x18000d3db  lea     rdx, [rsp+178h+var_140]
0x18000d3e0  mov     rcx, r13
0x18000d3e3  mov     rax, [rax+18h]
0x18000d3e7  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
