# CRawImageReader::DecodePreview(void)

- ea: `0x1800a8df0`
- end: `0x1800a9847`
- name: `?DecodePreview@CRawImageReader@@AEAAJXZ`
- size: `2647`
- prototype: `__int64 __fastcall(CRawImageReader *__hidden this)`
- caller_count: `3`
- callee_count: `19`
- tags: `broker_com_uri`

## callers

- `0x1800a7520`
- `0x1800a8588`
- `0x1800aafe0`

## callees

- `0x180001220`
- `0x180001710`
- `0x180002040`
- `0x1800020a0`
- `0x1800023a0`
- `0x180002590`
- `0x180002a00`
- `0x180007700`
- `0x180009d90`
- `0x18009b9e4`
- `0x18009c44c`
- `0x18009e8b8`
- `0x1800a2d70`
- `0x1800a34f8`
- `0x1800a4024`
- `0x1800a7f98`
- `0x1800a8df0`
- `0x1800affb0`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800a9197`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800a9197`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800a97f7`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800a97f7`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800a9160`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800a9160`

## string_xrefs

- `0x1800a8e37`: `CRawImageReader::DecodePreview`
- `0x1800a8ebd`: `CRawImageReader::DecodePreview`
- `0x1800a90e6`: `CRawImageReader::DecodePreview`
- `0x1800a9217`: `CRawImageReader::DecodePreview`
- `0x1800a9446`: `CRawImageReader::DecodePreview`
- `0x1800a96a5`: `CRawImageReader::DecodePreview`
- `0x1800a97ce`: `CRawImageReader::DecodePreview`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CRawImageReader::DecodePreview(CRawImageReader *this)
{
  HGLOBAL v2; // r12
  int *v3; // r9
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v5; // ebx
  unsigned int v6; // ebx
  unsigned int *v7; // r15
  int v8; // ecx
  int v9; // r8d
  int v10; // r9d
  int v11; // eax
  int v12; // ecx
  int v13; // r8d
  int v14; // r9d
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  _QWORD *v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // r13
  int v20; // eax
  void ***v21; // rcx
  struct CallStackContext *v22; // rax
  HRESULT v23; // eax
  void ***v24; // rcx
  struct CallStackContext *v25; // rax
  int v26; // r8d
  int v27; // eax
  void ***v28; // rcx
  int v29; // eax
  void ***v30; // rcx
  struct IWICImagingFactory *v31; // rbx
  HRESULT (__stdcall *CreateDecoderFromStream)(IWICImagingFactory *, IStream *, const GUID *, WICDecodeOptions, IWICBitmapDecoder **); // rdi
  int v33; // eax
  __int64 v34; // rdx
  __int64 v35; // r8
  unsigned __int64 v36; // rbx
  __int64 (__fastcall *v37)(unsigned __int64, _QWORD, _QWORD *); // rdi
  int v38; // eax
  void ***v39; // rcx
  struct CallStackContext *v40; // rax
  int v41; // r8d
  __int64 v42; // rbx
  __int64 (__fastcall *v43)(__int64, GUID *, char *); // rdi
  int v44; // eax
  void ***v45; // rcx
  PVOID *v46; // r10
  struct IWICImagingFactory *v47; // rbx
  HRESULT (__stdcall *CreateBitmapFromMemory)(IWICImagingFactory *, UINT, UINT, REFWICPixelFormatGUID, UINT, UINT, BYTE *, IWICBitmap **); // rdi
  int v49; // eax
  void ***v50; // rcx
  struct CallStackContext *v51; // rax
  int v52; // r8d
  int v53; // eax
  void ***v54; // rcx
  void ***v55; // rcx
  struct CallStackContext *v56; // rax
  int v58; // [rsp+28h] [rbp-69h]
  struct IWICImagingFactory *v59; // [rsp+58h] [rbp-39h] BYREF
  _BYTE v60[8]; // [rsp+60h] [rbp-31h] BYREF
  LPSTREAM ppstm; // [rsp+68h] [rbp-29h] BYREF
  unsigned __int64 v62; // [rsp+70h] [rbp-21h] BYREF
  int v63; // [rsp+78h] [rbp-19h] BYREF
  __int64 v64; // [rsp+80h] [rbp-11h]
  _BYTE v65[32]; // [rsp+88h] [rbp-9h] BYREF
  _QWORD v66[2]; // [rsp+A8h] [rbp+17h] BYREF

  v64 = -2;
  v2 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v60, "CRawImageReader::DecodePreview", 920);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 34) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v5 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 34) + 296LL))(*((_QWORD *)this + 34));
    *((_OWORD *)ThreadRelativeContext + 125) = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _QWORD *))(**((_QWORD **)this + 34) + 280LL))(
                                                            *((_QWORD *)this + 34),
                                                            v66);
    *((_DWORD *)ThreadRelativeContext + 504) = v5;
  }
  v6 = 0;
  v7 = (unsigned int *)((char *)this + 56);
  CTraceBase::CAutoTrace::CAutoTrace(
    (CTraceBase::CAutoTrace *)v65,
    (struct CTraceBase *)(((unsigned __int64)this + 56) & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64)),
    "CRawImageReader::DecodePreview",
    v3,
    v58);
  if ( *((_BYTE *)this + 105) )
    goto LABEL_155;
  if ( (unsigned int)dword_1800E50F0 > 4 )
  {
    v66[0] = this;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
      v8,
      (unsigned int)&byte_1800D73BF,
      v9,
      v10,
      (__int64)v66);
  }
  v11 = LibRaw::unpack_thumb(*((LibRaw **)this + 18));
  v63 = v11;
  *((_BYTE *)this + 105) = 1;
  if ( (unsigned int)dword_1800E50F0 > 4 )
  {
    LODWORD(ppstm) = v11;
    v66[0] = this;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      v12,
      (unsigned int)byte_1800D737B,
      v13,
      v14,
      (__int64)v66,
      (__int64)&ppstm);
    v11 = v63;
  }
  if ( v11 == -5 )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      goto LABEL_15;
    }
    v16 = 78;
    goto LABEL_14;
  }
  if ( v11 )
  {
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      goto LABEL_15;
    }
    v18 = 79;
    goto LABEL_21;
  }
  v19 = (*(__int64 (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 18) + 24LL))(*((_QWORD *)this + 18), &v63);
  if ( !v19 )
  {
    v11 = v63;
    if ( v63 == -5 )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
        goto LABEL_15;
      }
      v16 = (unsigned int)(v63 + 85);
LABEL_14:
      WPP_SF_D(v15[2], v16, &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids, *v7);
LABEL_15:
      v6 = 0;
      goto LABEL_155;
    }
    if ( v63 )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
        goto LABEL_15;
      }
      v18 = 81;
LABEL_21:
      WPP_SF_Dd(v17[2], v18, &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids, *v7, v11);
      goto LABEL_15;
    }
  }
  v59 = 0;
  Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease(&v59);
  v20 = CRawImageReader::CreateWICFactory(this, &v59);
  v6 = v20;
  if ( v20 >= 0 )
  {
    if ( *(_DWORD *)v19 == 1 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          83,
          &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
          *v7,
          *(_DWORD *)(v19 + 12));
      }
      v2 = GlobalAlloc(0, *(unsigned int *)(v19 + 12));
      if ( !v2 )
      {
        v6 = -2147024882;
LABEL_152:
        Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease(&v59);
LABEL_153:
        LibRaw::dcraw_clear_mem((struct libraw_processed_image_t *)v19);
        if ( v2 )
          GlobalFree(v2);
        goto LABEL_155;
      }
      ppstm = 0;
      Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease(&ppstm);
      v23 = CreateStreamOnHGlobal(v2, 1, &ppstm);
      v6 = v23;
      if ( v23 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 84, &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids, *v7, v23);
        }
        v24 = (void ***)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v24 = &off_1800E5190;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
        }
        if ( !*((_BYTE *)v24 + 8) )
          goto LABEL_63;
        v25 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v24);
        if ( *((_DWORD *)v25 + 499) == v6 )
          goto LABEL_63;
        v26 = 984;
        goto LABEL_62;
      }
      v2 = 0;
      v27 = ((__int64 (__fastcall *)(LPSTREAM, __int64, _QWORD, _QWORD))ppstm->lpVtbl->Write)(
              ppstm,
              v19 + 16,
              *(unsigned int *)(v19 + 12),
              0);
      v6 = v27;
      if ( v27 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 85, &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids, *v7, v27);
        }
        v28 = (void ***)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v28 = &off_1800E5190;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
        }
        if ( !*((_BYTE *)v28 + 8) )
          goto LABEL_63;
        v25 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v28);
        if ( *((_DWORD *)v25 + 499) == v6 )
          goto LABEL_63;
        v26 = 986;
        goto LABEL_62;
      }
      v66[0] = 0;
      v29 = ((__int64 (__fastcall *)(LPSTREAM, _QWORD, _QWORD, _QWORD))ppstm->lpVtbl->Seek)(ppstm, 0, 0, 0);
      v6 = v29;
      if ( v29 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 86, &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids, *v7, v29);
        }
        v30 = (void ***)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v30 = &off_1800E5190;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
        }
        if ( !*((_BYTE *)v30 + 8) )
          goto LABEL_63;
        v25 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v30);
        if ( *((_DWORD *)v25 + 499) == v6 )
          goto LABEL_63;
        v26 = 987;
LABEL_62:
        CallStackContext::TraceFailure(v25, "CRawImageReader::DecodePreview", v26, v6);
LABEL_63:
        Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease(&ppstm);
        goto LABEL_152;
      }
      v62 = 0;
      v31 = v59;
      CreateDecoderFromStream = v59->lpVtbl->CreateDecoderFromStream;
      Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease(&v62);
      v33 = ((__int64 (__fastcall *)(struct IWICImagingFactory *, LPSTREAM, _QWORD, _QWORD, unsigned __int64 *))CreateDecoderFromStream)(
              v31,
              ppstm,
              0,
              0,
              &v62);
      if ( v33 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_DqD(*((_QWORD *)WPP_GLOBAL_Control + 2), v34, v35, *v7, this, v33);
        }
        v6 = 0;
        goto LABEL_97;
      }
      v66[0] = 0;
      v36 = v62;
      v37 = *(__int64 (__fastcall **)(unsigned __int64, _QWORD, _QWORD *))(*(_QWORD *)v62 + 104LL);
      Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease(v66);
      v38 = v37(v36, 0, v66);
      v6 = v38;
      if ( v38 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 87, &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids, *v7, v38);
        }
        v39 = (void ***)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v39 = &off_1800E5190;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
        }
        if ( !*((_BYTE *)v39 + 8) )
          goto LABEL_96;
        v40 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v39);
        if ( *((_DWORD *)v40 + 499) == v6 )
          goto LABEL_96;
        v41 = 994;
LABEL_95:
        CallStackContext::TraceFailure(v40, "CRawImageReader::DecodePreview", v41, v6);
LABEL_96:
        Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease(v66);
LABEL_97:
        Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease(&v62);
        goto LABEL_63;
      }
      v42 = v66[0];
      v43 = **(__int64 (__fastcall ***)(__int64, GUID *, char *))v66[0];
      Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease((char *)this + 232);
      v44 = v43(v42, &GUID_00000120_a8f2_4877_ba0a_fd2b6645fb94, (char *)this + 232);
      v6 = v44;
      if ( v44 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 88, &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids, *v7, v44);
        }
        v45 = (void ***)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v45 = &off_1800E5190;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
        }
        if ( !*((_BYTE *)v45 + 8) )
          goto LABEL_96;
        v40 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v45);
        if ( *((_DWORD *)v40 + 499) == v6 )
          goto LABEL_96;
        v41 = 995;
        goto LABEL_95;
      }
      Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease(v66);
      Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease(&v62);
      Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease(&ppstm);
LABEL_142:
      Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease(&v59);
      v2 = 0;
      goto LABEL_153;
    }
    v46 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids, *v7);
      v46 = (PVOID *)WPP_GLOBAL_Control;
    }
    v62 = *(unsigned __int16 *)(v19 + 6)
        * (unsigned __int64)(*(unsigned __int16 *)(v19 + 8) * (*(unsigned __int16 *)(v19 + 10) >> 3));
    if ( v62 > 0xFFFFFFFF )
    {
      v6 = -2147024362;
      if ( v46 != &WPP_GLOBAL_Control && (*((_BYTE *)v46 + 28) & 1) != 0 && *((_BYTE *)v46 + 25) >= 4u )
        WPP_SF_Dd(v46[2], 92, &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids, *v7, -2147024362);
      v55 = (void ***)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v55 = &off_1800E5190;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
      }
      if ( *((_BYTE *)v55 + 8) )
      {
        v56 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v55);
        if ( *((_DWORD *)v56 + 499) != -2147024362 )
          CallStackContext::TraceFailure(v56, "CRawImageReader::DecodePreview", 1010, -2147024362);
      }
      goto LABEL_152;
    }
    v66[0] = 0;
    v47 = v59;
    CreateBitmapFromMemory = v59->lpVtbl->CreateBitmapFromMemory;
    Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease(v66);
    v49 = ((__int64 (__fastcall *)(struct IWICImagingFactory *, _QWORD, _QWORD, GUID *, _DWORD, _DWORD, __int64, _QWORD *))CreateBitmapFromMemory)(
            v47,
            *(unsigned __int16 *)(v19 + 6),
            *(unsigned __int16 *)(v19 + 4),
            &GUID_WICPixelFormat24bppRGB,
            v62,
            *(_DWORD *)(v19 + 12),
            v19 + 16,
            v66);
    v6 = v49;
    if ( v49 >= 0 )
    {
      v53 = Microsoft::WRL::ComPtr<IWICBitmap>::As<IWICBitmapSource>(v66, (char *)this + 232);
      v6 = v53;
      if ( v53 >= 0 )
      {
        Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease(v66);
        goto LABEL_142;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 94, &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids, *v7, v53);
      }
      v54 = (void ***)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v54 = &off_1800E5190;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
      }
      if ( !*((_BYTE *)v54 + 8)
        || (v51 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v54), *((_DWORD *)v51 + 499) == v6) )
      {
LABEL_130:
        Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease(v66);
        goto LABEL_152;
      }
      v52 = 1013;
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 93, &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids, *v7, v49);
      }
      v50 = (void ***)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v50 = &off_1800E5190;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
      }
      if ( !*((_BYTE *)v50 + 8) )
        goto LABEL_130;
      v51 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v50);
      if ( *((_DWORD *)v51 + 499) == v6 )
        goto LABEL_130;
      v52 = 1012;
    }
    CallStackContext::TraceFailure(v51, "CRawImageReader::DecodePreview", v52, v6);
    goto LABEL_130;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 82, &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids, *v7, v20);
  }
  v21 = (void ***)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v21 = &off_1800E5190;
    CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
  }
  if ( *((_BYTE *)v21 + 8) )
  {
    v22 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v21);
    if ( *((_DWORD *)v22 + 499) != v6 )
      CallStackContext::TraceFailure(v22, "CRawImageReader::DecodePreview", 975, v6);
  }
  Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease(&v59);
  v2 = 0;
  if ( v19 )
    goto LABEL_153;
LABEL_155:
  CTraceBase::CAutoTrace::~CAutoTrace((CTraceBase::CAutoTrace *)v65);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v60);
  return v6;
}

```

## disassembly

```asm
0x1800a8df0  mov     rax, rsp
0x1800a8df3  push    rbp
0x1800a8df4  push    r12
0x1800a8df6  push    r13
0x1800a8df8  push    r14
0x1800a8dfa  push    r15
0x1800a8dfc  lea     rbp, [rax-5Fh]
0x1800a8e00  sub     rsp, 0C0h
0x1800a8e07  mov     [rbp+57h+var_68], 0FFFFFFFFFFFFFFFEh
0x1800a8e0f  mov     [rax+10h], rbx
0x1800a8e13  mov     [rax+18h], rsi
0x1800a8e17  mov     [rax+20h], rdi
0x1800a8e1b  mov     rax, cs:__security_cookie
0x1800a8e22  xor     rax, rsp
0x1800a8e25  mov     [rbp+57h+var_30], rax
0x1800a8e29  mov     rsi, rcx
0x1800a8e2c  xor     edi, edi
0x1800a8e2e  mov     r12d, edi
0x1800a8e31  mov     r8d, 398h; int
0x1800a8e37  lea     rdx, aCrawimagereade_20; "CRawImageReader::DecodePreview"
0x1800a8e3e  lea     rcx, [rbp+57h+var_88]; this
0x1800a8e42  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800a8e47  nop
0x1800a8e48  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800a8e4f  cmp     [rcx+8], dil
0x1800a8e53  jz      short loc_1800A8EAB
0x1800a8e55  cmp     [rsi+110h], rdi
0x1800a8e5c  jz      short loc_1800A8EAB
0x1800a8e5e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a8e63  mov     rdi, rax
0x1800a8e66  mov     rcx, [rsi+110h]
0x1800a8e6d  mov     rax, [rcx]
0x1800a8e70  mov     rax, [rax+128h]
0x1800a8e77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8e7c  mov     ebx, eax
0x1800a8e7e  mov     rcx, [rsi+110h]
0x1800a8e85  mov     rax, [rcx]
0x1800a8e88  lea     rdx, [rbp+57h+var_40]
0x1800a8e8c  mov     rax, [rax+118h]
0x1800a8e93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8e98  movups  xmm0, xmmword ptr [rax]
0x1800a8e9b  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1800a8ea3  mov     [rdi+7E0h], ebx
0x1800a8ea9  xor     edi, edi
0x1800a8eab  mov     ebx, edi
0x1800a8ead  lea     r15, [rsi+38h]
0x1800a8eb1  mov     rax, rsi
0x1800a8eb4  neg     rax
0x1800a8eb7  sbb     rdx, rdx
0x1800a8eba  and     rdx, r15; struct CTraceBase *
0x1800a8ebd  lea     r8, aCrawimagereade_20; "CRawImageReader::DecodePreview"
0x1800a8ec4  lea     rcx, [rbp+57h+var_60]; this
0x1800a8ec8  call    ??0CAutoTrace@CTraceBase@@QEAA@PEAV1@PEBDPEAJH@Z; CTraceBase::CAutoTrace::CAutoTrace(CTraceBase *,char const *,long *,int)
0x1800a8ecd  nop
0x1800a8ece  cmp     [rsi+69h], dil
0x1800a8ed2  jnz     loc_1800A9804
0x1800a8ed8  mov     ebx, 4
0x1800a8edd  cmp     cs:dword_1800E50F0, ebx
0x1800a8ee3  jbe     short loc_1800A8EFE
0x1800a8ee5  mov     [rbp+57h+var_40], rsi
0x1800a8ee9  lea     rax, [rbp+57h+var_40]
0x1800a8eed  mov     [rsp+0E0h+var_C0], rax
0x1800a8ef2  lea     rdx, byte_1800D73BF
0x1800a8ef9  call    ??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)
0x1800a8efe  mov     rcx, [rsi+90h]; this
0x1800a8f05  call    ?unpack_thumb@LibRaw@@QEAAHXZ; LibRaw::unpack_thumb(void)
0x1800a8f0a  mov     [rbp+57h+var_70], eax
0x1800a8f0d  mov     byte ptr [rsi+69h], 1
0x1800a8f11  cmp     cs:dword_1800E50F0, ebx
0x1800a8f17  jbe     short loc_1800A8F41
0x1800a8f19  mov     dword ptr [rbp+57h+ppstm], eax
0x1800a8f1c  mov     [rbp+57h+var_40], rsi
0x1800a8f20  lea     rax, [rbp+57h+ppstm]
0x1800a8f24  mov     [rsp+0E0h+var_B8], rax
0x1800a8f29  lea     rax, [rbp+57h+var_40]
0x1800a8f2d  mov     [rsp+0E0h+var_C0], rax
0x1800a8f32  lea     rdx, byte_1800D737B
0x1800a8f39  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x1800a8f3e  mov     eax, [rbp+57h+var_70]
0x1800a8f41  cmp     eax, 0FFFFFFFBh
0x1800a8f44  jnz     short loc_1800A8F81
0x1800a8f46  lea     r14, WPP_GLOBAL_Control
0x1800a8f4d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a8f54  cmp     rcx, r14
0x1800a8f57  jz      short loc_1800A8F7A
0x1800a8f59  test    byte ptr [rcx+1Ch], 1
0x1800a8f5d  jz      short loc_1800A8F7A
0x1800a8f5f  cmp     [rcx+19h], bl
0x1800a8f62  jb      short loc_1800A8F7A
0x1800a8f64  lea     edx, [rax+53h]
0x1800a8f67  mov     r9d, [r15]
0x1800a8f6a  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800a8f71  mov     rcx, [rcx+10h]
0x1800a8f75  call    WPP_SF_D
0x1800a8f7a  mov     ebx, edi
0x1800a8f7c  jmp     loc_1800A9804
0x1800a8f81  test    eax, eax
0x1800a8f83  jz      short loc_1800A8FC1
0x1800a8f85  lea     r14, WPP_GLOBAL_Control
0x1800a8f8c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a8f93  cmp     rcx, r14
0x1800a8f96  jz      short loc_1800A8F7A
0x1800a8f98  test    byte ptr [rcx+1Ch], 1
0x1800a8f9c  jz      short loc_1800A8F7A
0x1800a8f9e  cmp     [rcx+19h], bl
0x1800a8fa1  jb      short loc_1800A8F7A
0x1800a8fa3  mov     edx, 4Fh ; 'O'
0x1800a8fa8  mov     dword ptr [rsp+0E0h+var_C0], eax
0x1800a8fac  mov     r9d, [r15]
0x1800a8faf  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800a8fb6  mov     rcx, [rcx+10h]
0x1800a8fba  call    WPP_SF_Dd
0x1800a8fbf  jmp     short loc_1800A8F7A
0x1800a8fc1  mov     rcx, [rsi+90h]
0x1800a8fc8  mov     rax, [rcx]
0x1800a8fcb  lea     rdx, [rbp+57h+var_70]
0x1800a8fcf  mov     rax, [rax+18h]
0x1800a8fd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8fd8  mov     r13, rax
0x1800a8fdb  test    rax, rax
0x1800a8fde  jnz     short loc_1800A9052
0x1800a8fe0  mov     eax, [rbp+57h+var_70]
0x1800a8fe3  cmp     eax, 0FFFFFFFBh
0x1800a8fe6  jnz     short loc_1800A901A
0x1800a8fe8  lea     r14, WPP_GLOBAL_Control
0x1800a8fef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a8ff6  cmp     rcx, r14
0x1800a8ff9  jz      loc_1800A8F7A
0x1800a8fff  test    byte ptr [rcx+1Ch], 1
0x1800a9003  jz      loc_1800A8F7A
0x1800a9009  cmp     [rcx+19h], bl
0x1800a900c  jb      loc_1800A8F7A
0x1800a9012  lea     edx, [rax+55h]
0x1800a9015  jmp     loc_1800A8F67
0x1800a901a  test    eax, eax
0x1800a901c  jz      short loc_1800A9052
0x1800a901e  lea     r14, WPP_GLOBAL_Control
0x1800a9025  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a902c  cmp     rcx, r14
0x1800a902f  jz      loc_1800A8F7A
0x1800a9035  test    byte ptr [rcx+1Ch], 1
0x1800a9039  jz      loc_1800A8F7A
0x1800a903f  cmp     [rcx+19h], bl
0x1800a9042  jb      loc_1800A8F7A
0x1800a9048  mov     edx, 51h ; 'Q'
0x1800a904d  jmp     loc_1800A8FA8
0x1800a9052  mov     [rbp+57h+var_90], rdi
0x1800a9056  lea     rcx, [rbp+57h+var_90]
0x1800a905a  call    ?InternalRelease@?$ComPtr@UIWICMetadataBlockReader@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease(void)
0x1800a905f  lea     rdx, [rbp+57h+var_90]; struct IWICImagingFactory **
0x1800a9063  mov     rcx, rsi; this
0x1800a9066  call    ?CreateWICFactory@CRawImageReader@@AEAAJPEAPEAUIWICImagingFactory@@@Z; CRawImageReader::CreateWICFactory(IWICImagingFactory * *)
0x1800a906b  mov     ebx, eax
0x1800a906d  test    eax, eax
0x1800a906f  jns     loc_1800A9110
0x1800a9075  lea     r14, WPP_GLOBAL_Control
0x1800a907c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a9083  cmp     rcx, r14
0x1800a9086  jz      short loc_1800A90B0
0x1800a9088  test    byte ptr [rcx+1Ch], 1
0x1800a908c  jz      short loc_1800A90B0
0x1800a908e  cmp     byte ptr [rcx+19h], 4
0x1800a9092  jb      short loc_1800A90B0
0x1800a9094  mov     edx, 52h ; 'R'
0x1800a9099  mov     dword ptr [rsp+0E0h+var_C0], eax
0x1800a909d  mov     r9d, [r15]
0x1800a90a0  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800a90a7  mov     rcx, [rcx+10h]
0x1800a90ab  call    WPP_SF_Dd
0x1800a90b0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a90b7  test    rcx, rcx
0x1800a90ba  jnz     short loc_1800A90CA
0x1800a90bc  lea     rcx, off_1800E5190; this
0x1800a90c3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a90ca  cmp     [rcx+8], dil
0x1800a90ce  jz      short loc_1800A90F6
0x1800a90d0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a90d5  cmp     [rax+7CCh], ebx
0x1800a90db  jz      short loc_1800A90F6
0x1800a90dd  mov     r9d, ebx; int
0x1800a90e0  mov     r8d, 3CFh; int
0x1800a90e6  lea     rdx, aCrawimagereade_20; "CRawImageReader::DecodePreview"
0x1800a90ed  mov     rcx, rax; this
0x1800a90f0  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a90f5  nop
0x1800a90f6  lea     rcx, [rbp+57h+var_90]
0x1800a90fa  call    ?InternalRelease@?$ComPtr@UIWICMetadataBlockReader@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease(void)
0x1800a90ff  mov     r12, rdi
0x1800a9102  test    r13, r13
0x1800a9105  jz      loc_1800A9804
0x1800a910b  jmp     loc_1800A97E7
0x1800a9110  cmp     dword ptr [r13+0], 1
0x1800a9115  jnz     loc_1800A956D
0x1800a911b  lea     r14, WPP_GLOBAL_Control
0x1800a9122  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a9129  cmp     rcx, r14
0x1800a912c  jz      short loc_1800A915A
0x1800a912e  test    byte ptr [rcx+1Ch], 1
0x1800a9132  jz      short loc_1800A915A
0x1800a9134  cmp     byte ptr [rcx+19h], 4
0x1800a9138  jb      short loc_1800A915A
0x1800a913a  mov     edx, 53h ; 'S'
0x1800a913f  mov     eax, [r13+0Ch]
0x1800a9143  mov     dword ptr [rsp+0E0h+var_C0], eax
0x1800a9147  mov     r9d, [r15]
0x1800a914a  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800a9151  mov     rcx, [rcx+10h]
0x1800a9155  call    WPP_SF_Dd
0x1800a915a  mov     edx, [r13+0Ch]; dwBytes
0x1800a915e  xor     ecx, ecx; uFlags
0x1800a9160  call    cs:__imp_GlobalAlloc
0x1800a9167  nop     dword ptr [rax+rax+00h]
0x1800a916c  mov     r12, rax
0x1800a916f  test    rax, rax
0x1800a9172  jnz     short loc_1800A917E
0x1800a9174  mov     ebx, 8007000Eh
0x1800a9179  jmp     loc_1800A97DE
0x1800a917e  mov     [rbp+57h+ppstm], rdi
0x1800a9182  lea     rcx, [rbp+57h+ppstm]
0x1800a9186  call    ?InternalRelease@?$ComPtr@UIWICMetadataBlockReader@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease(void)
0x1800a918b  lea     r8, [rbp+57h+ppstm]; ppstm
0x1800a918f  mov     edx, 1; fDeleteOnRelease
0x1800a9194  mov     rcx, r12; hGlobal
0x1800a9197  call    cs:__imp_CreateStreamOnHGlobal
0x1800a919e  nop     dword ptr [rax+rax+00h]
0x1800a91a3  mov     ebx, eax
0x1800a91a5  test    eax, eax
0x1800a91a7  jns     loc_1800A9235
0x1800a91ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a91b4  cmp     rcx, r14
0x1800a91b7  jz      short loc_1800A91E1
0x1800a91b9  test    byte ptr [rcx+1Ch], 1
0x1800a91bd  jz      short loc_1800A91E1
0x1800a91bf  cmp     byte ptr [rcx+19h], 4
0x1800a91c3  jb      short loc_1800A91E1
0x1800a91c5  mov     edx, 54h ; 'T'
0x1800a91ca  mov     dword ptr [rsp+0E0h+var_C0], eax
0x1800a91ce  mov     r9d, [r15]
0x1800a91d1  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800a91d8  mov     rcx, [rcx+10h]
0x1800a91dc  call    WPP_SF_Dd
0x1800a91e1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a91e8  test    rcx, rcx
0x1800a91eb  jnz     short loc_1800A91FB
0x1800a91ed  lea     rcx, off_1800E5190; this
0x1800a91f4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a91fb  cmp     [rcx+8], dil
0x1800a91ff  jz      short loc_1800A9227
0x1800a9201  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a9206  cmp     [rax+7CCh], ebx
0x1800a920c  jz      short loc_1800A9227
0x1800a920e  mov     r8d, 3D8h; int
0x1800a9214  mov     r9d, ebx; int
0x1800a9217  lea     rdx, aCrawimagereade_20; "CRawImageReader::DecodePreview"
0x1800a921e  mov     rcx, rax; this
0x1800a9221  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a9226  nop
0x1800a9227  lea     rcx, [rbp+57h+ppstm]
0x1800a922b  call    ?InternalRelease@?$ComPtr@UIWICMetadataBlockReader@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease(void)
0x1800a9230  jmp     loc_1800A97DE
0x1800a9235  mov     r12, rdi
0x1800a9238  lea     rdx, [r13+10h]
0x1800a923c  mov     rcx, [rbp+57h+ppstm]
0x1800a9240  mov     rax, [rcx]
0x1800a9243  xor     r9d, r9d
0x1800a9246  mov     r8d, [r13+0Ch]
0x1800a924a  mov     rax, [rax+20h]
0x1800a924e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a9253  mov     ebx, eax
0x1800a9255  test    eax, eax
0x1800a9257  jns     short loc_1800A92CD
0x1800a9259  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a9260  cmp     rcx, r14
0x1800a9263  jz      short loc_1800A928D
0x1800a9265  test    byte ptr [rcx+1Ch], 1
0x1800a9269  jz      short loc_1800A928D
0x1800a926b  cmp     byte ptr [rcx+19h], 4
0x1800a926f  jb      short loc_1800A928D
0x1800a9271  mov     edx, 55h ; 'U'
0x1800a9276  mov     dword ptr [rsp+0E0h+var_C0], eax
0x1800a927a  mov     r9d, [r15]
0x1800a927d  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800a9284  mov     rcx, [rcx+10h]
0x1800a9288  call    WPP_SF_Dd
0x1800a928d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a9294  test    rcx, rcx
0x1800a9297  jnz     short loc_1800A92A7
0x1800a9299  lea     rcx, off_1800E5190; this
0x1800a92a0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a92a7  cmp     [rcx+8], dil
0x1800a92ab  jz      loc_1800A9227
0x1800a92b1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a92b6  cmp     [rax+7CCh], ebx
0x1800a92bc  jz      loc_1800A9227
0x1800a92c2  mov     r8d, 3DAh
0x1800a92c8  jmp     loc_1800A9214
0x1800a92cd  mov     [rbp+57h+var_40], 0
0x1800a92d5  mov     rcx, [rbp+57h+ppstm]
0x1800a92d9  mov     rax, [rcx]
0x1800a92dc  xor     r9d, r9d
  ... truncated ...
```
