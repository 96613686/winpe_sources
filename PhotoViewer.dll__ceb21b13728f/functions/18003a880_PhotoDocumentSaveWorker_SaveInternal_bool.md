# PhotoDocumentSaveWorker::SaveInternal(bool)

- ea: `0x18003a880`
- end: `0x18003afbe`
- name: `?SaveInternal@PhotoDocumentSaveWorker@@AEAAX_N@Z`
- size: `1854`
- prototype: `void(PhotoDocumentSaveWorker *__hidden this, bool)`
- caller_count: `2`
- callee_count: `18`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180060f14`
- `0x18007ee80`

## callees

- `0x18000cb74`
- `0x180011908`
- `0x1800281bc`
- `0x180030b10`
- `0x1800335e8`
- `0x180038b30`
- `0x18003a880`
- `0x18003c650`
- `0x18003e068`
- `0x18003f800`
- `0x18005aebc`
- `0x180060c30`
- `0x18007852c`
- `0x180078cd0`
- `0x180079610`
- `0x180079774`
- `0x18007b018`
- `0x180080010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003a948`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003a948`
- `KERNEL32!GetFileAttributesExW` at `0x18003af1c`
- `KERNEL32!GetFileAttributesExW` at `0x18003af1c`
- `ole32!CoCreateInstance` at `0x18003a8e4`
- `ole32!CoCreateInstance` at `0x18003a8e4`
- `SHELL32!SHChangeNotify` at `0x18003aedb`
- `SHELL32!SHChangeNotify` at `0x18003aedb`
- `SHLWAPI!SHCreateStreamOnFileEx` at `0x18003a979`
- `SHLWAPI!SHCreateStreamOnFileEx` at `0x18003a9fe`
- `SHLWAPI!SHCreateStreamOnFileEx` at `0x18003a979`
- `SHLWAPI!SHCreateStreamOnFileEx` at `0x18003a9fe`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003a8f0`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003a925`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003a985`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003a9b3`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003a9d6`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003aa0a`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003aa36`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003aaef`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003ac9e`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003ae6b`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003ae74`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003ae7d`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003ae86`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003ae8f`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003ae98`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003aeba`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003a8f0`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003a925`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003a985`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003a9b3`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003a9d6`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003aa0a`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003aa36`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003aaef`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003ac9e`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003ae6b`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003ae74`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003ae7d`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003ae86`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003ae8f`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003ae98`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003aeba`
- `PhotoBase!?ThrowLastError@Base@@YAXXZ` at `0x18003af5a`
- `PhotoBase!?ThrowLastError@Base@@YAXXZ` at `0x18003af5a`
- `PhotoBase!?IsStreamTimerActive@Sqm@@YA_NKK@Z` at `0x18003aee8`
- `PhotoBase!?IsStreamTimerActive@Sqm@@YA_NKK@Z` at `0x18003aee8`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall PhotoDocumentSaveWorker::SaveInternal(PhotoDocumentSaveWorker *this, char a2)
{
  char v2; // si
  unsigned int v4; // r13d
  HRESULT Instance; // eax
  int v6; // edx
  CodecUtil *v7; // r14
  int v8; // eax
  int v9; // edx
  unsigned int v10; // ebx
  int v11; // eax
  const WCHAR *v12; // rcx
  unsigned int v13; // r12d
  HRESULT v14; // eax
  int v15; // edx
  int v16; // eax
  int v17; // edx
  int v18; // eax
  int v19; // edx
  HRESULT v20; // eax
  int v21; // edx
  int v22; // eax
  int v23; // edx
  struct IWICBitmapEncoder *v24; // r8
  __int64 v25; // rax
  struct IWICBitmapDecoder **v26; // r15
  unsigned int v27; // r8d
  int v28; // eax
  int v29; // edx
  int v30; // eax
  int v31; // edx
  struct IPropertyBag2 *v32; // r8
  int v33; // eax
  int v34; // edx
  int v35; // eax
  int v36; // edx
  struct IWICBitmapFrameEncode *v37; // r8
  bool v38; // r9
  unsigned int v39; // r9d
  unsigned int v40; // r8d
  struct IWICBitmapFrameEncode *v41; // rdx
  enum WICBitmapTransformOptions v42; // ebx
  struct IWICBitmapFrameDecode *v43; // r14
  CodecUtilPrivate *v44; // rsi
  enum WICBitmapTransformOptions v45; // r8d
  int v46; // eax
  int v47; // edx
  unsigned int v48; // ebx
  __int64 v49; // rax
  unsigned int v50; // r9d
  int v51; // eax
  int v52; // edx
  GUID v53; // xmm6
  const struct _GUID *v54; // rdx
  GUID v55; // xmm0
  _QWORD *v56; // rax
  int v57; // eax
  int v58; // edx
  _QWORD *v59; // rax
  _QWORD *v60; // rax
  int v61; // ebx
  _QWORD *v62; // rax
  int v63; // edx
  int v64; // eax
  int v65; // edx
  unsigned __int64 v66; // rdx
  Base *v67; // rcx
  unsigned int v68; // eax
  unsigned int v69; // r9d
  enum WICBitmapTransformOptions ppv; // [rsp+20h] [rbp-F8h]
  enum WICBitmapTransformOptions ppstm; // [rsp+28h] [rbp-F0h]
  enum WICBitmapTransformOptions v72; // [rsp+30h] [rbp-E8h] BYREF
  struct _GUID *v73; // [rsp+38h] [rbp-E0h] BYREF
  struct IWICBitmapFrameDecode *v74; // [rsp+40h] [rbp-D8h] BYREF
  struct IWICBitmapDecoder *v75; // [rsp+48h] [rbp-D0h] BYREF
  unsigned int v76; // [rsp+50h] [rbp-C8h] BYREF
  _DWORD v77[3]; // [rsp+54h] [rbp-C4h] BYREF
  unsigned int v78; // [rsp+60h] [rbp-B8h]
  IStream *v79; // [rsp+68h] [rbp-B0h] BYREF
  IStream *v80; // [rsp+70h] [rbp-A8h] BYREF
  CodecUtil *v81; // [rsp+78h] [rbp-A0h] BYREF
  int v82; // [rsp+80h] [rbp-98h] BYREF
  CodecUtilPrivate *v83; // [rsp+88h] [rbp-90h]
  _BYTE v84[16]; // [rsp+90h] [rbp-88h] BYREF
  GUID Buf2; // [rsp+A0h] [rbp-78h] BYREF
  __int128 FileInformation; // [rsp+B0h] [rbp-68h] BYREF
  __int128 v87; // [rsp+C0h] [rbp-58h]
  unsigned int v88; // [rsp+D0h] [rbp-48h]

  v2 = a2;
  LOBYTE(v72) = a2;
  v4 = 0;
  v81 = 0;
  Instance = CoCreateInstance(
               &CLSID_WICImagingFactory2,
               0,
               1u,
               &GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70,
               (LPVOID *)&v81);
  if ( Instance < 0 )
  {
    Base::Throw((Base *)(unsigned int)Instance, v6);
    __debugbreak();
  }
  v75 = 0;
  v7 = (PhotoDocumentSaveWorker *)((char *)this + 152);
  v8 = (*(__int64 (__fastcall **)(CodecUtil *, char *, _QWORD, struct IWICBitmapDecoder **))(*(_QWORD *)v81 + 64LL))(
         v81,
         (char *)this + 152,
         0,
         &v75);
  if ( v8 < 0 )
  {
    Base::Throw((Base *)(unsigned int)v8, v9);
    __debugbreak();
  }
  v10 = *((_DWORD *)this + 32);
  v78 = v10;
  v80 = 0;
  v79 = 0;
  v11 = _o__wcsicmp(*((_QWORD *)this + 12), *((_QWORD *)this + 13));
  v12 = (const WCHAR *)*((_QWORD *)this + 13);
  if ( v11 )
  {
    v20 = SHCreateStreamOnFileEx(v12, 1u, 0x80u, 1, 0, &v79);
    if ( v20 < 0 )
    {
      Base::Throw((Base *)(unsigned int)v20, v21);
      __debugbreak();
    }
    v13 = 2;
  }
  else
  {
    v13 = 2;
    v14 = SHCreateStreamOnFileEx(v12, 2u, 0x80u, 0, 0, &v80);
    if ( v14 < 0 )
    {
      Base::Throw((Base *)(unsigned int)v14, v15);
      __debugbreak();
    }
    v73 = 0;
    v16 = ((__int64 (__fastcall *)(IStream *, GUID *, struct _GUID **))v80->lpVtbl->QueryInterface)(
            v80,
            &GUID_8a87781b_39a7_4a1f_aab3_a39b9c34a7d9,
            &v73);
    if ( v16 < 0 )
    {
      Base::Throw((Base *)(unsigned int)v16, v17);
      __debugbreak();
    }
    v18 = (*(__int64 (__fastcall **)(struct _GUID *, IStream **))(*(_QWORD *)&v73->Data1 + 24LL))(v73, &v79);
    if ( v18 < 0 )
      Base::Throw((Base *)(unsigned int)v18, v19);
    ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&v73);
  }
  v22 = ((__int64 (__fastcall *)(struct IWICBitmapDecoder *, IStream *, __int64))v75->lpVtbl->QueryCapability)(
          v75,
          v79,
          2);
  if ( v22 < 0 )
  {
    Base::Throw((Base *)(unsigned int)v22, v23);
    __debugbreak();
  }
  if ( v10 == 1 )
  {
    if ( !*(_QWORD *)ATL::CAtlArray<NavigationBarButton,ATL::CElementTraits<NavigationBarButton>>::operator[](
                       (char *)this + 120,
                       0) )
    {
      LOBYTE(v72) = 0;
      v25 = ATL::CAtlArray<NavigationBarButton,ATL::CElementTraits<NavigationBarButton>>::operator[](
              (char *)this + 120,
              0);
      v26 = (struct IWICBitmapDecoder **)((char *)this + 112);
      LOBYTE(ppv) = v2;
      CodecUtil::CopyImageWithRotation(
        v81,
        *((struct IWICImagingFactory **)this + 14),
        v75,
        (struct IWICBitmapEncoder *)*(unsigned int *)(v25 + 16),
        ppv,
        (bool *)&v72);
      v13 = (_BYTE)v72 == WICBitmapTransformRotate0;
      goto LABEL_21;
    }
    v10 = v78;
  }
  v26 = (struct IWICBitmapDecoder **)((char *)this + 112);
  CodecUtil::CopyGlobalMetaData(*((CodecUtil **)this + 14), v75, v24);
  while ( v4 < v10 )
  {
    v74 = 0;
    v73 = 0;
    v30 = ((__int64 (__fastcall *)(struct IWICBitmapDecoder *, struct IWICBitmapFrameDecode **, struct _GUID **))v75->lpVtbl->GetColorContexts)(
            v75,
            &v74,
            &v73);
    if ( v30 < 0 )
    {
      Base::Throw((Base *)(unsigned int)v30, v31);
      break;
    }
    CodecUtil::ApplyDefaultImageQualitySettings(v7, v73, v32);
    v33 = ((__int64 (__fastcall *)(struct IWICBitmapFrameDecode *, struct _GUID *))v74->lpVtbl->GetSize)(v74, v73);
    if ( v33 < 0 )
      goto LABEL_56;
    *(_QWORD *)&v77[1] = 0;
    v35 = ((__int64 (__fastcall *)(struct IWICBitmapDecoder *, _QWORD, _DWORD *))(*v26)->lpVtbl->GetFrame)(
            *v26,
            v4,
            &v77[1]);
    if ( v35 < 0 )
    {
      Base::Throw((Base *)(unsigned int)v35, v36);
LABEL_56:
      Base::Throw((Base *)(unsigned int)v33, v34);
      __debugbreak();
    }
    LOBYTE(v37) = v2;
    CodecUtil::CopyAndSetUpFrameMetaData(*(CodecUtil **)&v77[1], v74, v37, v38);
    if ( *(_QWORD *)ATL::CAtlArray<NavigationBarButton,ATL::CElementTraits<NavigationBarButton>>::operator[](
                      (char *)this + 120,
                      v4) )
    {
      v48 = *(_DWORD *)(ATL::CAtlArray<NavigationBarButton,ATL::CElementTraits<NavigationBarButton>>::operator[](
                          (char *)this + 120,
                          v4)
                      + 12);
      v49 = ATL::CAtlArray<NavigationBarButton,ATL::CElementTraits<NavigationBarButton>>::operator[](
              (char *)this + 120,
              v4);
      CodecUtil::WriteFrameDimensionMetaData(
        (CodecUtil *)v74,
        (struct IWICBitmapFrameEncode *)*(unsigned int *)(v49 + 8),
        v48,
        v50);
      Buf2 = 0;
      v51 = (*(__int64 (__fastcall **)(_QWORD, GUID *))(**(_QWORD **)&v77[1] + 32LL))(*(_QWORD *)&v77[1], &Buf2);
      if ( v51 < 0 )
      {
        Base::Throw((Base *)(unsigned int)v51, v52);
        __debugbreak();
      }
      v53 = Buf2;
      if ( !memcmp_0(&GUID_WICPixelFormat8bppGray, &Buf2, 0x10u) )
      {
        v55 = GUID_WICPixelFormat24bppBGR;
        v53 = GUID_WICPixelFormat24bppBGR;
      }
      else
      {
        v55 = GUID_WICPixelFormat24bppBGR;
        if ( !memcmp_0(&GUID_WICPixelFormat16bppGray, &Buf2, 0x10u) )
          v53 = GUID_WICPixelFormat48bppRGB;
      }
      Buf2 = v53;
      if ( CodecUtil::IsWICPixelFormatIndexed((CodecUtil *)&Buf2, v54) )
        Buf2 = v55;
      v56 = (_QWORD *)ATL::CAtlArray<NavigationBarButton,ATL::CElementTraits<NavigationBarButton>>::operator[](
                        (char *)this + 120,
                        v4);
      v57 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v56 + 128LL))(*v56, (unsigned __int8)v72 ^ 1u);
      if ( v57 < 0 )
      {
        Base::Throw((Base *)(unsigned int)v57, v58);
        __debugbreak();
      }
      v59 = (_QWORD *)ATL::CAtlArray<NavigationBarButton,ATL::CElementTraits<NavigationBarButton>>::operator[](
                        (char *)this + 120,
                        v4);
      (*(void (__fastcall **)(_QWORD, char *))(*(_QWORD *)*v59 + 144LL))(*v59, (char *)this + 8);
      v82 = 0;
      v60 = (_QWORD *)ATL::CAtlArray<NavigationBarButton,ATL::CElementTraits<NavigationBarButton>>::operator[](
                        (char *)this + 120,
                        v4);
      v61 = (*(__int64 (__fastcall **)(_QWORD, struct IWICBitmapFrameDecode *, GUID *, int *))(*(_QWORD *)*v60 + 120LL))(
              *v60,
              v74,
              &Buf2,
              &v82);
      v62 = (_QWORD *)ATL::CAtlArray<NavigationBarButton,ATL::CElementTraits<NavigationBarButton>>::operator[](
                        (char *)this + 120,
                        v4);
      (*(void (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v62 + 144LL))(*v62, 0);
      if ( v61 < 0 )
      {
        Base::Throw((Base *)(unsigned int)v61, v63);
        __debugbreak();
      }
    }
    else
    {
      v76 = 0;
      v77[0] = 0;
      if ( (*(int (__fastcall **)(_QWORD, unsigned int *, _DWORD *))(**(_QWORD **)&v77[1] + 24LL))(
             *(_QWORD *)&v77[1],
             &v76,
             v77) >= 0 )
      {
        if ( *(_DWORD *)(ATL::CAtlArray<NavigationBarButton,ATL::CElementTraits<NavigationBarButton>>::operator[](
                           (char *)this + 120,
                           v4)
                       + 16) == 1
          || *(_DWORD *)(ATL::CAtlArray<NavigationBarButton,ATL::CElementTraits<NavigationBarButton>>::operator[](
                           (char *)this + 120,
                           v4)
                       + 16) == 3 )
        {
          v40 = v76;
          v41 = (struct IWICBitmapFrameEncode *)v77[0];
        }
        else
        {
          v40 = v77[0];
          v41 = (struct IWICBitmapFrameEncode *)v76;
        }
        CodecUtil::WriteFrameDimensionMetaData((CodecUtil *)v74, v41, v40, v39);
      }
      v42 = *(_DWORD *)(ATL::CAtlArray<NavigationBarButton,ATL::CElementTraits<NavigationBarButton>>::operator[](
                          (char *)this + 120,
                          v4)
                      + 16);
      v43 = v74;
      v44 = *(CodecUtilPrivate **)&v77[1];
      v83 = v81;
      if ( WICIsOrientationSupported(*v26) )
        v42 = CodecUtilPrivate::OrientateRotation(v44, (struct IWICBitmapFrameDecode *)(unsigned int)v42, v45);
      LOBYTE(ppstm) = v72;
      CodecUtilPrivate::CopyFrameImageDataWithRotationInternal(
        v83,
        (struct IUnknown *)v44,
        v43,
        (struct IWICBitmapFrameEncode *)(unsigned int)v42,
        v42,
        ppstm);
      v46 = ((__int64 (__fastcall *)(struct IWICBitmapFrameDecode *))v74->lpVtbl[1].AddRef)(v74);
      if ( v46 < 0 )
      {
        Base::Throw((Base *)(unsigned int)v46, v47);
        __debugbreak();
      }
    }
    ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&v77[1]);
    ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&v73);
    ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&v74);
    ++v4;
    v2 = v72;
    v10 = v78;
    v7 = (PhotoDocumentSaveWorker *)((char *)this + 152);
  }
  v64 = ((__int64 (__fastcall *)(struct IWICBitmapDecoder *))v75->lpVtbl->GetThumbnail)(v75);
  if ( v64 < 0 )
  {
    Base::Throw((Base *)(unsigned int)v64, v65);
    __debugbreak();
  }
LABEL_21:
  ATL::CComPtrBase<IWICBitmapDecoder>::Release(v26);
  ATL::CComPtrBase<IWICBitmapDecoder>::Release(&v75);
  ATL::CComPtrBase<IWICBitmapDecoder>::Release(&v79);
  if ( !*((_BYTE *)this + 172) && v80 )
  {
    v28 = ((__int64 (__fastcall *)(IStream *, _QWORD))v80->lpVtbl->Commit)(v80, 0);
    if ( v28 < 0 )
    {
      Base::Throw((Base *)(unsigned int)v28, v29);
      __debugbreak();
    }
    ATL::CComPtrBase<IWICBitmapDecoder>::Release(&v80);
    SHChangeNotify(0x2000, 5u, *((LPCVOID *)this + 13), 0);
  }
  if ( Sqm::IsStreamTimerActive((Sqm *)0x948, 0, v27) )
  {
    try
    {
      FileInformation = 0;
      v87 = 0;
      v88 = 0;
      if ( GetFileAttributesExW(*((LPCWSTR *)this + 13), GetFileExInfoStandard, &FileInformation) )
      {
        v73 = (struct _GUID *)__PAIR64__(HIDWORD(v87), v88);
        v68 = TweakerUtility::ConvertBytesToMegaBytes((TweakerUtility *)__PAIR64__(HIDWORD(v87), v88), v66);
        SetPixPerfSqmEventData(0, v68, v68, v69, v13);
      }
      else
      {
        Base::ThrowLastError(v67);
      }
    }
    catch ( Base::Exception v84 )
    {
      Base::Exception::~Exception((Base::Exception *)v84);
    }
  }
  ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&v79);
  ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&v80);
  ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&v75);
  ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&v81);
}

```

## disassembly

```asm
0x18003a880  mov     rax, rsp
0x18003a883  mov     [rax+10h], rbx
0x18003a887  mov     [rax+18h], rsi
0x18003a88b  push    rdi
0x18003a88c  push    r12
0x18003a88e  push    r13
0x18003a890  push    r14
0x18003a892  push    r15
0x18003a894  sub     rsp, 0F0h
0x18003a89b  movaps  xmmword ptr [rax-38h], xmm6
0x18003a89f  mov     rax, cs:__security_cookie
0x18003a8a6  xor     rax, rsp
0x18003a8a9  mov     [rsp+118h+var_40], rax
0x18003a8b1  mov     sil, dl
0x18003a8b4  mov     byte ptr [rsp+118h+var_E8], dl; bool
0x18003a8b8  mov     rdi, rcx
0x18003a8bb  xor     r13d, r13d
0x18003a8be  mov     [rsp+118h+var_A0], r13
0x18003a8c3  lea     rax, [rsp+118h+var_A0]
0x18003a8c8  mov     [rsp+118h+ppv], rax; ppv
0x18003a8cd  lea     r9, _GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70; riid
0x18003a8d4  lea     r15d, [r13+1]
0x18003a8d8  mov     r8d, r15d; dwClsContext
0x18003a8db  xor     edx, edx; pUnkOuter
0x18003a8dd  lea     rcx, CLSID_WICImagingFactory2; rclsid
0x18003a8e4  call    cs:__imp_CoCreateInstance
0x18003a8ea  test    eax, eax
0x18003a8ec  jns     short loc_18003A8F7
0x18003a8ee  mov     ecx, eax
0x18003a8f0  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18003a8f6  int     3; Trap to Debugger
0x18003a8f7  mov     [rsp+118h+var_D0], r13
0x18003a8fc  mov     rcx, [rsp+118h+var_A0]
0x18003a901  lea     r14, [rdi+98h]
0x18003a908  mov     rax, [rcx]
0x18003a90b  lea     r9, [rsp+118h+var_D0]
0x18003a910  xor     r8d, r8d
0x18003a913  mov     rdx, r14
0x18003a916  mov     rax, [rax+40h]
0x18003a91a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a91f  test    eax, eax
0x18003a921  jns     short loc_18003A92C
0x18003a923  mov     ecx, eax
0x18003a925  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18003a92b  int     3; Trap to Debugger
0x18003a92c  mov     ebx, [rdi+80h]
0x18003a932  mov     [rsp+118h+var_B8], ebx
0x18003a936  mov     [rsp+118h+var_A8], r13
0x18003a93b  mov     [rsp+118h+var_B0], r13
0x18003a940  mov     rdx, [rdi+68h]
0x18003a944  mov     rcx, [rdi+60h]
0x18003a948  call    cs:__imp__o__wcsicmp
0x18003a94e  mov     rcx, [rdi+68h]; pszFile
0x18003a952  mov     r8d, 80h; dwAttributes
0x18003a958  test    eax, eax
0x18003a95a  jnz     loc_18003A9E9
0x18003a960  lea     rax, [rsp+118h+var_A8]
0x18003a965  mov     [rsp+118h+ppstm], rax; ppstm
0x18003a96a  mov     [rsp+118h+ppv], r13; pstmTemplate
0x18003a96f  xor     r9d, r9d; fCreate
0x18003a972  lea     r12d, [r8-7Eh]
0x18003a976  mov     edx, r12d; grfMode
0x18003a979  call    cs:__imp_SHCreateStreamOnFileEx
0x18003a97f  test    eax, eax
0x18003a981  jns     short loc_18003A98C
0x18003a983  mov     ecx, eax
0x18003a985  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18003a98b  int     3; Trap to Debugger
0x18003a98c  mov     [rsp+118h+var_E0], r13
0x18003a991  mov     rcx, [rsp+118h+var_A8]
0x18003a996  mov     rax, [rcx]
0x18003a999  lea     r8, [rsp+118h+var_E0]
0x18003a99e  lea     rdx, _GUID_8a87781b_39a7_4a1f_aab3_a39b9c34a7d9
0x18003a9a5  mov     rax, [rax]
0x18003a9a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a9ad  test    eax, eax
0x18003a9af  jns     short loc_18003A9BA
0x18003a9b1  mov     ecx, eax
0x18003a9b3  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18003a9b9  int     3; Trap to Debugger
0x18003a9ba  mov     rcx, [rsp+118h+var_E0]
0x18003a9bf  mov     rax, [rcx]
0x18003a9c2  lea     rdx, [rsp+118h+var_B0]
0x18003a9c7  mov     rax, [rax+18h]
0x18003a9cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a9d0  test    eax, eax
0x18003a9d2  jns     short loc_18003A9DD
0x18003a9d4  mov     ecx, eax
0x18003a9d6  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18003a9dc  nop
0x18003a9dd  lea     rcx, [rsp+118h+var_E0]
0x18003a9e2  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x18003a9e7  jmp     short loc_18003AA17
0x18003a9e9  lea     rax, [rsp+118h+var_B0]
0x18003a9ee  mov     [rsp+118h+ppstm], rax; ppstm
0x18003a9f3  mov     [rsp+118h+ppv], r13; pstmTemplate
0x18003a9f8  mov     r9d, r15d; fCreate
0x18003a9fb  mov     edx, r15d; grfMode
0x18003a9fe  call    cs:__imp_SHCreateStreamOnFileEx
0x18003aa04  test    eax, eax
0x18003aa06  jns     short loc_18003AA11
0x18003aa08  mov     ecx, eax
0x18003aa0a  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18003aa10  int     3; Trap to Debugger
0x18003aa11  mov     r12d, 2
0x18003aa17  mov     rcx, [rsp+118h+var_D0]
0x18003aa1c  mov     rax, [rcx]
0x18003aa1f  mov     r8d, r12d
0x18003aa22  mov     rdx, [rsp+118h+var_B0]
0x18003aa27  mov     rax, [rax+18h]
0x18003aa2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003aa30  test    eax, eax
0x18003aa32  jns     short loc_18003AA3D
0x18003aa34  mov     ecx, eax
0x18003aa36  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18003aa3c  int     3; Trap to Debugger
0x18003aa3d  cmp     ebx, r15d
0x18003aa40  jnz     loc_18003AAFA
0x18003aa46  xor     edx, edx
0x18003aa48  lea     rcx, [rdi+78h]
0x18003aa4c  call    ??A?$CAtlArray@VNavigationBarButton@@V?$CElementTraits@VNavigationBarButton@@@ATL@@@ATL@@QEBAAEBVNavigationBarButton@@_K@Z; ATL::CAtlArray<NavigationBarButton,ATL::CElementTraits<NavigationBarButton>>::operator[](unsigned __int64)
0x18003aa51  cmp     [rax], r13
0x18003aa54  jnz     loc_18003AAF6
0x18003aa5a  mov     byte ptr [rsp+118h+var_E8], r13b; bool *
0x18003aa5f  xor     edx, edx
0x18003aa61  lea     rcx, [rdi+78h]
0x18003aa65  call    ??A?$CAtlArray@VNavigationBarButton@@V?$CElementTraits@VNavigationBarButton@@@ATL@@@ATL@@QEBAAEBVNavigationBarButton@@_K@Z; ATL::CAtlArray<NavigationBarButton,ATL::CElementTraits<NavigationBarButton>>::operator[](unsigned __int64)
0x18003aa6a  lea     r15, [rdi+70h]
0x18003aa6e  lea     rcx, [rsp+118h+var_E8]
0x18003aa73  mov     [rsp+118h+ppstm], rcx; bool
0x18003aa78  mov     byte ptr [rsp+118h+ppv], sil; enum WICBitmapTransformOptions
0x18003aa7d  mov     r9d, [rax+10h]; struct IWICBitmapEncoder *
0x18003aa81  mov     r8, [rsp+118h+var_D0]; struct IWICBitmapDecoder *
0x18003aa86  mov     rdx, [r15]; struct IWICImagingFactory *
0x18003aa89  mov     rcx, [rsp+118h+var_A0]; this
0x18003aa8e  call    ?CopyImageWithRotation@CodecUtil@@YAXPEAUIWICImagingFactory@@PEAUIWICBitmapDecoder@@PEAUIWICBitmapEncoder@@W4WICBitmapTransformOptions@@_NPEA_N@Z; CodecUtil::CopyImageWithRotation(IWICImagingFactory *,IWICBitmapDecoder *,IWICBitmapEncoder *,WICBitmapTransformOptions,bool,bool *)
0x18003aa93  mov     r12d, r13d
0x18003aa96  cmp     byte ptr [rsp+118h+var_E8], r13b
0x18003aa9b  setz    r12b
0x18003aa9f  mov     rcx, r15
0x18003aaa2  call    ?Release@?$CComPtrBase@UIWICBitmapDecoder@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IWICBitmapDecoder>::Release(void)
0x18003aaa7  lea     rcx, [rsp+118h+var_D0]
0x18003aaac  call    ?Release@?$CComPtrBase@UIWICBitmapDecoder@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IWICBitmapDecoder>::Release(void)
0x18003aab1  lea     rcx, [rsp+118h+var_B0]
0x18003aab6  call    ?Release@?$CComPtrBase@UIWICBitmapDecoder@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IWICBitmapDecoder>::Release(void)
0x18003aabb  mov     al, [rdi+0ACh]
0x18003aac1  test    al, al
0x18003aac3  jnz     loc_18003AEE1
0x18003aac9  mov     rcx, [rsp+118h+var_A8]
0x18003aace  test    rcx, rcx
0x18003aad1  jz      loc_18003AEE1
0x18003aad7  mov     rax, [rcx]
0x18003aada  xor     edx, edx
0x18003aadc  mov     rax, [rax+40h]
0x18003aae0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003aae5  test    eax, eax
0x18003aae7  jns     loc_18003AEC1
0x18003aaed  mov     ecx, eax
0x18003aaef  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18003aaf5  int     3; Trap to Debugger
0x18003aaf6  mov     ebx, [rsp+118h+var_B8]
0x18003aafa  lea     r15, [rdi+70h]
0x18003aafe  mov     rdx, [rsp+118h+var_D0]; struct IWICBitmapDecoder *
0x18003ab03  mov     rcx, [r15]; this
0x18003ab06  call    ?CopyGlobalMetaData@CodecUtil@@YAXPEAUIWICBitmapDecoder@@PEAUIWICBitmapEncoder@@@Z; CodecUtil::CopyGlobalMetaData(IWICBitmapDecoder *,IWICBitmapEncoder *)
0x18003ab0b  cmp     r13d, ebx
0x18003ab0e  jnb     loc_18003AE9F
0x18003ab14  xor     ebx, ebx
0x18003ab16  mov     [rsp+118h+var_D8], rbx
0x18003ab1b  mov     [rsp+118h+var_E0], rbx
0x18003ab20  mov     rcx, [rsp+118h+var_D0]
0x18003ab25  mov     rax, [rcx]
0x18003ab28  lea     r8, [rsp+118h+var_E0]
0x18003ab2d  lea     rdx, [rsp+118h+var_D8]
0x18003ab32  mov     rax, [rax+50h]
0x18003ab36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ab3b  test    eax, eax
0x18003ab3d  js      loc_18003AE96
0x18003ab43  mov     rdx, [rsp+118h+var_E0]; struct _GUID *
0x18003ab48  mov     rcx, r14; this
0x18003ab4b  call    ?ApplyDefaultImageQualitySettings@CodecUtil@@YAXPEBU_GUID@@PEAUIPropertyBag2@@@Z; CodecUtil::ApplyDefaultImageQualitySettings(_GUID const *,IPropertyBag2 *)
0x18003ab50  mov     rcx, [rsp+118h+var_D8]
0x18003ab55  mov     rax, [rcx]
0x18003ab58  mov     rdx, [rsp+118h+var_E0]
0x18003ab5d  mov     rax, [rax+18h]
0x18003ab61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ab66  test    eax, eax
0x18003ab68  js      loc_18003AE8D
0x18003ab6e  mov     qword ptr [rsp+118h+var_C4+4], rbx
0x18003ab73  mov     rcx, [r15]
0x18003ab76  mov     rax, [rcx]
0x18003ab79  lea     r8, [rsp+118h+var_C4+4]
0x18003ab7e  mov     edx, r13d
0x18003ab81  mov     rax, [rax+68h]
0x18003ab85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ab8a  test    eax, eax
0x18003ab8c  js      loc_18003AE84
0x18003ab92  mov     r8b, sil; struct IWICBitmapFrameEncode *
0x18003ab95  mov     rdx, [rsp+118h+var_D8]; struct IWICBitmapFrameDecode *
0x18003ab9a  mov     rcx, qword ptr [rsp+118h+var_C4+4]; this
0x18003ab9f  call    ?CopyAndSetUpFrameMetaData@CodecUtil@@YAXPEAUIWICBitmapFrameDecode@@PEAUIWICBitmapFrameEncode@@_N@Z; CodecUtil::CopyAndSetUpFrameMetaData(IWICBitmapFrameDecode *,IWICBitmapFrameEncode *,bool)
0x18003aba4  mov     esi, r13d
0x18003aba7  lea     r14, [rdi+78h]
0x18003abab  mov     edx, r13d
0x18003abae  mov     rcx, r14
0x18003abb1  call    ??A?$CAtlArray@VNavigationBarButton@@V?$CElementTraits@VNavigationBarButton@@@ATL@@@ATL@@QEBAAEBVNavigationBarButton@@_K@Z; ATL::CAtlArray<NavigationBarButton,ATL::CElementTraits<NavigationBarButton>>::operator[](unsigned __int64)
0x18003abb6  cmp     [rax], rbx
0x18003abb9  jnz     loc_18003ACA5
0x18003abbf  mov     [rsp+118h+var_C8], ebx
0x18003abc3  mov     dword ptr [rsp+118h+var_C4], ebx
0x18003abc7  mov     rcx, qword ptr [rsp+118h+var_C4+4]
0x18003abcc  mov     rax, [rcx]
0x18003abcf  lea     r8, [rsp+118h+var_C4]
0x18003abd4  lea     rdx, [rsp+118h+var_C8]
0x18003abd9  mov     rax, [rax+18h]
0x18003abdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003abe2  test    eax, eax
0x18003abe4  js      short loc_18003AC24
0x18003abe6  mov     edx, esi
0x18003abe8  mov     rcx, r14
0x18003abeb  call    ??A?$CAtlArray@VNavigationBarButton@@V?$CElementTraits@VNavigationBarButton@@@ATL@@@ATL@@QEBAAEBVNavigationBarButton@@_K@Z; ATL::CAtlArray<NavigationBarButton,ATL::CElementTraits<NavigationBarButton>>::operator[](unsigned __int64)
0x18003abf0  cmp     dword ptr [rax+10h], 1
0x18003abf4  jz      short loc_18003AC11
0x18003abf6  mov     edx, esi
0x18003abf8  mov     rcx, r14
0x18003abfb  call    ??A?$CAtlArray@VNavigationBarButton@@V?$CElementTraits@VNavigationBarButton@@@ATL@@@ATL@@QEBAAEBVNavigationBarButton@@_K@Z; ATL::CAtlArray<NavigationBarButton,ATL::CElementTraits<NavigationBarButton>>::operator[](unsigned __int64)
0x18003ac00  cmp     dword ptr [rax+10h], 3
0x18003ac04  jz      short loc_18003AC11
0x18003ac06  mov     r8d, dword ptr [rsp+118h+var_C4]
0x18003ac0b  mov     edx, [rsp+118h+var_C8]
0x18003ac0f  jmp     short loc_18003AC1A
0x18003ac11  mov     r8d, [rsp+118h+var_C8]; unsigned int
0x18003ac16  mov     edx, dword ptr [rsp+118h+var_C4]; struct IWICBitmapFrameEncode *
0x18003ac1a  mov     rcx, [rsp+118h+var_D8]; this
0x18003ac1f  call    ?WriteFrameDimensionMetaData@CodecUtil@@YAXPEAUIWICBitmapFrameEncode@@II@Z; CodecUtil::WriteFrameDimensionMetaData(IWICBitmapFrameEncode *,uint,uint)
0x18003ac24  mov     rdx, rsi
0x18003ac27  mov     rcx, r14
0x18003ac2a  call    ??A?$CAtlArray@VNavigationBarButton@@V?$CElementTraits@VNavigationBarButton@@@ATL@@@ATL@@QEBAAEBVNavigationBarButton@@_K@Z; ATL::CAtlArray<NavigationBarButton,ATL::CElementTraits<NavigationBarButton>>::operator[](unsigned __int64)
0x18003ac2f  mov     ebx, [rax+10h]
0x18003ac32  mov     r14, [rsp+118h+var_D8]
0x18003ac37  mov     rsi, qword ptr [rsp+118h+var_C4+4]
0x18003ac3c  mov     rax, [rsp+118h+var_A0]
0x18003ac41  mov     [rsp+118h+var_90], rax
0x18003ac49  mov     rcx, [r15]; struct IWICBitmapDecoder *
0x18003ac4c  call    ?WICIsOrientationSupported@@YA_NPEAUIWICBitmapDecoder@@@Z; WICIsOrientationSupported(IWICBitmapDecoder *)
0x18003ac51  test    al, al
0x18003ac53  jz      short loc_18003AC61
0x18003ac55  mov     edx, ebx; struct IWICBitmapFrameDecode *
0x18003ac57  mov     rcx, rsi; this
0x18003ac5a  call    ?OrientateRotation@CodecUtilPrivate@@YA?AW4WICBitmapTransformOptions@@PEAUIWICBitmapFrameDecode@@W42@@Z; CodecUtilPrivate::OrientateRotation(IWICBitmapFrameDecode *,WICBitmapTransformOptions)
0x18003ac5f  mov     ebx, eax
0x18003ac61  mov     dl, byte ptr [rsp+118h+var_E8]
0x18003ac65  mov     byte ptr [rsp+118h+ppstm], dl; enum WICBitmapTransformOptions
0x18003ac69  mov     dword ptr [rsp+118h+ppv], ebx; enum WICBitmapTransformOptions
0x18003ac6d  mov     r9d, ebx; struct IWICBitmapFrameEncode *
0x18003ac70  mov     r8, r14; struct IWICBitmapFrameDecode *
0x18003ac73  mov     rdx, rsi; struct IWICImagingFactory *
0x18003ac76  mov     rcx, [rsp+118h+var_90]; this
0x18003ac7e  call    ?CopyFrameImageDataWithRotationInternal@CodecUtilPrivate@@YAXPEAUIWICImagingFactory@@PEAUIWICBitmapFrameDecode@@PEAUIWICBitmapFrameEncode@@W4WICBitmapTransformOptions@@3_N@Z; CodecUtilPrivate::CopyFrameImageDataWithRotationInternal(IWICImagingFactory *,IWICBitmapFrameDecode *,IWICBitmapFrameEncode *,WICBitmapTransformOptions,WICBitmapTransformOptions,bool)
0x18003ac83  mov     rcx, [rsp+118h+var_D8]
0x18003ac88  mov     rax, [rcx]
0x18003ac8b  mov     rax, [rax+60h]
0x18003ac8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ac94  test    eax, eax
0x18003ac96  jns     loc_18003AE31
0x18003ac9c  mov     ecx, eax
0x18003ac9e  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18003aca4  int     3; Trap to Debugger
0x18003aca5  mov     rdx, rsi
0x18003aca8  mov     rcx, r14
0x18003acab  call    ??A?$CAtlArray@VNavigationBarButton@@V?$CElementTraits@VNavigationBarButton@@@ATL@@@ATL@@QEBAAEBVNavigationBarButton@@_K@Z; ATL::CAtlArray<NavigationBarButton,ATL::CElementTraits<NavigationBarButton>>::operator[](unsigned __int64)
0x18003acb0  mov     ebx, [rax+0Ch]
0x18003acb3  mov     rdx, rsi
0x18003acb6  mov     rcx, r14
0x18003acb9  call    ??A?$CAtlArray@VNavigationBarButton@@V?$CElementTraits@VNavigationBarButton@@@ATL@@@ATL@@QEBAAEBVNavigationBarButton@@_K@Z; ATL::CAtlArray<NavigationBarButton,ATL::CElementTraits<NavigationBarButton>>::operator[](unsigned __int64)
0x18003acbe  mov     r8d, ebx; unsigned int
0x18003acc1  mov     edx, [rax+8]; struct IWICBitmapFrameEncode *
0x18003acc4  mov     rcx, [rsp+118h+var_D8]; this
0x18003acc9  call    ?WriteFrameDimensionMetaData@CodecUtil@@YAXPEAUIWICBitmapFrameEncode@@II@Z; CodecUtil::WriteFrameDimensionMetaData(IWICBitmapFrameEncode *,uint,uint)
0x18003acce  xorps   xmm0, xmm0
0x18003acd1  movups  [rsp+118h+Buf2], xmm0
0x18003acd9  mov     rcx, qword ptr [rsp+118h+var_C4+4]
0x18003acde  mov     rax, [rcx]
0x18003ace1  lea     rdx, [rsp+118h+Buf2]
0x18003ace9  mov     rax, [rax+20h]
0x18003aced  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003acf2  test    eax, eax
0x18003acf4  js      loc_18003AE7B
0x18003acfa  movaps  xmm6, [rsp+118h+Buf2]
0x18003ad02  movdqa  [rsp+118h+Buf2], xmm6
0x18003ad0b  mov     ebx, 10h
0x18003ad10  mov     r8d, ebx; Size
0x18003ad13  lea     rdx, [rsp+118h+Buf2]; Buf2
0x18003ad1b  lea     rcx, GUID_WICPixelFormat8bppGray; Buf1
0x18003ad22  call    memcmp_0
0x18003ad27  test    eax, eax
0x18003ad29  jnz     short loc_18003AD38
0x18003ad2b  movups  xmm0, xmmword ptr cs:GUID_WICPixelFormat24bppBGR.Data1
0x18003ad32  movdqu  xmm6, xmm0
0x18003ad36  jmp     short loc_18003AD61
  ... truncated ...
```
