# DataStoreCache::MRTHelper::ResolvePathInternal(HSTRING__ *,DataStoreCache::MRTHelper::ImageResolutionType,DEVICE_SCALE_FACTOR,ushort,ushort,RESOURCE_CONTRAST const *,ushort const *,ushort const *,RESOURCE_CONTRAST *,ushort * *,ushort * *)

- ea: `0x18000d258`
- end: `0x18000db0d`
- name: `?ResolvePathInternal@MRTHelper@DataStoreCache@@IEAA?AVHString@Wrappers@WRL@Microsoft@@PEAUHSTRING__@@W4ImageResolutionType@12@W4DEVICE_SCALE_FACTOR@@GGPEBW4RESOURCE_CONTRAST@@PEBG4PEAW4RESOURCE_CONTRAST@@PEAPEAG6@Z`
- size: `2229`
- prototype: `struct Microsoft::WRL::Wrappers::HString __high(HSTRING, enum DataStoreCache::MRTHelper::ImageResolutionType, enum DEVICE_SCALE_FACTOR, unsigned __int16, unsigned __int16, const enum RESOURCE_CONTRAST *, const unsigned __int16 *, const unsigned __int16 *, enum RESOURCE_CONTRAST *, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `27`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180041be4`
- `0x1800a061c`

## callees

- `0x18000ce94`
- `0x18000d258`
- `0x18000db14`
- `0x18000dc10`
- `0x18000dcc8`
- `0x18000dd8c`
- `0x18000dde8`
- `0x18000de8c`
- `0x18000dec0`
- `0x18000e158`
- `0x18000e220`
- `0x18000eb38`
- `0x18001aca4`
- `0x18001dac0`
- `0x18001dfb8`
- `0x18002f1fc`
- `0x1800a3798`
- `0x1800dadbc`
- `0x1800db12c`
- `0x1800f0854`
- `0x180159460`
- `0x180161204`
- `0x1801ad744`
- `0x180201e50`
- `0x18022b750`
- `0x18036c10c`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000d3ba`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000d400`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000d3ba`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000d400`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d55b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d5e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d6b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d55b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d5e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d6b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000d56d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000d56d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000d30d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000d38d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000d3da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000da0e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000da74`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000da83`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000d30d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000d38d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000d3da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000da0e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000da74`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000da83`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d597`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d71f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d7fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d811`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d597`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d71f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d7fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d811`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x18000d986`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x18000d986`

## string_xrefs

- `0x18000d393`: `shellcommon\shell\datastorecache\transformers\mrttransformer\lib\mrthelper.cpp`
- `0x18000d98e`: `shellcommon\shell\datastorecache\transformers\mrttransformer\lib\mrthelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
HSTRING *__fastcall DataStoreCache::MRTHelper::ResolvePathInternal(
        DataStoreCache::MRTHelper *a1,
        HSTRING *a2,
        __int64 a3,
        unsigned int a4,
        unsigned int a5,
        unsigned __int16 a6,
        unsigned __int16 a7,
        _DWORD *a8,
        __int64 a9,
        void *a10,
        _DWORD *a11,
        unsigned __int16 **a12,
        unsigned __int16 **a13)
{
  DataStoreCache::MRTHelper *v14; // rbx
  int v15; // edi
  const WCHAR *StringRawBuffer; // r12
  char v17; // si
  __int64 v18; // r14
  HSTRING v19; // rsi
  const WCHAR *v20; // rax
  const WCHAR *v21; // rax
  DataStoreCache::MRTHelper *v22; // rsi
  int v23; // eax
  HSTRING v24; // rdx
  HSTRING v25; // rbx
  __int64 (__fastcall *v26)(HSTRING, GUID *, UINT32 *); // rdi
  int v27; // eax
  __int64 v28; // rcx
  struct IResourceMap *v29; // rcx
  HSTRING v30; // rcx
  UINT32 v31; // edi
  const WCHAR *v32; // rbx
  HRESULT v33; // eax
  __int64 v34; // rdx
  int v36; // eax
  __int64 v37; // rcx
  int v38; // eax
  HANDLE v39; // rbx
  void *v40; // rdi
  int v41; // eax
  __int64 v42; // rcx
  unsigned __int64 i; // rax
  unsigned __int16 **v44; // r8
  int v45; // eax
  void *v46; // rdx
  void *v47; // rcx
  int v48; // eax
  void *v49; // rcx
  HRESULT v50; // eax
  __int64 v51; // r9
  __int64 v52; // rdx
  const WCHAR *v53; // rax
  __int64 v54; // rdi
  __int64 (__fastcall *v55)(__int64, PCWSTR, PCNZWCH *); // rbx
  PCWSTR v56; // rax
  int v57; // eax
  struct IResourceMap *v58; // rsi
  __int64 (__fastcall *v59)(struct IResourceMap *, PCWSTR, PCWSTR, _QWORD); // rdi
  PCWSTR v60; // rbx
  PCWSTR v61; // rax
  int v62; // eax
  void *v63; // rdx
  HSTRING *bIgnoreCase; // [rsp+20h] [rbp-E0h]
  int bIgnoreCasea; // [rsp+20h] [rbp-E0h]
  char v66; // [rsp+70h] [rbp-90h]
  UINT32 v67[2]; // [rsp+78h] [rbp-88h] BYREF
  struct IResourceMap *v68; // [rsp+80h] [rbp-80h] BYREF
  PCNZWCH sourceString; // [rsp+88h] [rbp-78h] BYREF
  UINT32 v70[2]; // [rsp+90h] [rbp-70h]
  __int64 v71; // [rsp+98h] [rbp-68h]
  HANDLE hObject; // [rsp+A0h] [rbp-60h] BYREF
  HSTRING v73; // [rsp+A8h] [rbp-58h] BYREF
  HSTRING string; // [rsp+B0h] [rbp-50h] BYREF
  UINT32 length; // [rsp+B8h] [rbp-48h] BYREF
  unsigned int v76; // [rsp+BCh] [rbp-44h]
  int v77; // [rsp+C0h] [rbp-40h]
  DataStoreCache::MRTHelper *v78; // [rsp+C8h] [rbp-38h]
  unsigned __int16 **v79; // [rsp+D0h] [rbp-30h]
  _DWORD *v80; // [rsp+D8h] [rbp-28h]
  __int64 v81; // [rsp+E0h] [rbp-20h]
  _DWORD *v82; // [rsp+E8h] [rbp-18h]
  void *v83; // [rsp+F0h] [rbp-10h]
  unsigned __int16 **v84; // [rsp+F8h] [rbp-8h]
  HSTRING *v85; // [rsp+100h] [rbp+0h]
  void **v86; // [rsp+110h] [rbp+10h] BYREF
  char v87[272]; // [rsp+118h] [rbp+18h] BYREF
  char v88[8]; // [rsp+228h] [rbp+128h] BYREF
  char v89[48]; // [rsp+230h] [rbp+130h] BYREF
  WCHAR pszOutBuf[264]; // [rsp+260h] [rbp+160h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4C8h] [rbp+3C8h]

  v76 = a4;
  v14 = a1;
  v78 = a1;
  v85 = a2;
  v82 = a8;
  v81 = a9;
  v83 = a10;
  v80 = a11;
  v79 = a12;
  v84 = a13;
  v15 = 0;
  v77 = 0;
  if ( a11 )
    *a11 = 0;
  if ( a12 )
    *a12 = 0;
  if ( a13 )
    *a13 = 0;
  DataStoreCache::MRTHelper::SimplifyFullyQualifiedResourceStringIfApplicable(&string, a3);
  length = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(string, &length);
  wil::ActivityBase<MRTTransformerLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<MRTTransformerLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)&v86);
  v86 = &MRTTransformerTelemetry::ResolveMrtString::`vftable';
  MRTTransformerTelemetry::ResolveMrtString::StartActivity(&v86, 1, StringRawBuffer);
  v17 = 0;
  v18 = -1;
  *(_QWORD *)v70 = -1;
  v71 = -1;
  sourceString = 0;
  if ( length < 2 || *StringRawBuffer != 64 || StringRawBuffer[1] == 123 )
  {
    *(_QWORD *)v70 = -1;
    v71 = -1;
    v19 = string;
    v73 = string;
    sourceString = 0;
    v67[0] = 0;
    v20 = WindowsGetStringRawBuffer(string, v67);
    if ( v67[0] >= 5 && CompareStringOrdinal(v20, 5, L"file:", 5, 1) == 2 )
    {
      v66 = 1;
      *(_QWORD *)v67 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v67);
      v36 = DataStoreCache::MRTHelper::EnsureAppUriResolver(v14, (struct IAppUriResolver **)v67);
      v15 = v36;
      if ( v36 >= 0 )
      {
        v54 = *(_QWORD *)v67;
        v55 = *(__int64 (__fastcall **)(__int64, PCWSTR, PCNZWCH *))(**(_QWORD **)v67 + 56LL);
        v56 = WindowsGetStringRawBuffer(v19, 0);
        v57 = v55(v54, v56, &sourceString);
        v15 = v57;
        if ( v57 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x3C8,
            (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\mrttransformer\\lib\\mrthelper.cpp",
            (const char *)(unsigned int)v57,
            (int)bIgnoreCase);
          v47 = v67;
          goto LABEL_78;
        }
        v49 = v67;
LABEL_85:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v49);
        v15 = 0;
        goto LABEL_13;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3C4,
        (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\mrttransformer\\lib\\mrthelper.cpp",
        (const char *)(unsigned int)v36,
        (int)bIgnoreCase);
      v37 = *(_QWORD *)v67;
      if ( *(_QWORD *)v67 )
      {
        *(_QWORD *)v67 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
      }
    }
    else
    {
      v66 = 0;
      v67[0] = 0;
      v21 = WindowsGetStringRawBuffer(v19, v67);
      if ( v67[0] >= 0xB && CompareStringOrdinal(v21, 11, L"ms-appdata:", 11, 1) == 2 )
      {
        v66 = 1;
        if ( *((_QWORD *)v14 + 1) )
        {
          v68 = 0;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
          v48 = DataStoreCache::MRTHelper::EnsureAppUriResolver(v14, &v68);
          v15 = v48;
          if ( v48 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x3D1,
              (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\mrttransformer\\lib\\mrthelper.cpp",
              (const char *)(unsigned int)v48,
              (int)bIgnoreCase);
LABEL_77:
            v47 = &v68;
LABEL_78:
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v47);
            goto LABEL_13;
          }
          DataStoreCache::MRTHelper::TryImpersonateUserIfApplicable(v14, &hObject);
          v58 = v68;
          v59 = *(__int64 (__fastcall **)(struct IResourceMap *, PCWSTR, PCWSTR, _QWORD))(*(_QWORD *)v68 + 48LL);
          v60 = WindowsGetStringRawBuffer(*((HSTRING *)v14 + 1), 0);
          v61 = WindowsGetStringRawBuffer(v73, 0);
          bIgnoreCase = (HSTRING *)&sourceString;
          v62 = v59(v58, v61, v60, 0);
          v15 = v62;
          if ( v62 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x3DC,
              (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\mrttransformer\\lib\\mrthelper.cpp",
              (const char *)(unsigned int)v62,
              (int)&sourceString);
            if ( hObject != (HANDLE)-1LL )
              wil::details::RevertImpersonateToken(hObject, v46);
            goto LABEL_77;
          }
          if ( hObject != (HANDLE)-1LL )
            wil::details::RevertImpersonateToken(hObject, v63);
          v49 = &v68;
          goto LABEL_85;
        }
      }
    }
LABEL_13:
    if ( v66 )
    {
      v17 = 0;
LABEL_27:
      v14 = v78;
      goto LABEL_28;
    }
    v73 = 0;
    v68 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v73);
    v22 = v78;
    v23 = DataStoreCache::MRTHelper::TryEnsureResourceManagerAndMap(v78, (struct IMrtResourceManager **)&v73, &v68);
    if ( v23 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x17E,
        (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\mrttransformer\\lib\\mrthelper.cpp",
        (const char *)(unsigned int)v23,
        (int)bIgnoreCase);
    *(_QWORD *)v67 = 0;
    v25 = v73;
    if ( v73 )
    {
      v26 = *(__int64 (__fastcall **)(HSTRING, GUID *, UINT32 *))(*(_QWORD *)v73 + 72LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v67);
      v27 = v26(v25, &GUID_e3c22b30_8502_4b2f_9133_559674587e51, v67);
      if ( v27 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x185,
          (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\mrttransformer\\lib\\mrthelper.cpp",
          (const char *)(unsigned int)v27,
          (int)bIgnoreCase);
    }
    if ( !*(_QWORD *)v67 || !v68 )
    {
      v17 = 1;
      v15 = -2147023728;
LABEL_21:
      v28 = *(_QWORD *)v67;
      if ( *(_QWORD *)v67 )
      {
        *(_QWORD *)v67 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
      }
      v29 = v68;
      if ( v68 )
      {
        v68 = 0;
        (*(void (__fastcall **)(struct IResourceMap *))(*(_QWORD *)v29 + 16LL))(v29);
      }
      v30 = v73;
      if ( v73 )
      {
        v73 = 0;
        (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v30 + 16LL))(v30);
      }
      goto LABEL_27;
    }
    v39 = 0;
    hObject = 0;
    if ( *((_QWORD *)v22 + 1) && ShellMRTHelper::Common::HasMsAppXUriScheme((ShellMRTHelper::Common *)string, v24) )
    {
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &hObject,
        0);
      v45 = ShellMRTHelper::Common::ConvertMsAppXUriToMsResourceUri(
              (ShellMRTHelper::Common *)string,
              (HSTRING)&hObject,
              v44);
      v15 = v45;
      if ( v45 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x197,
          (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\mrttransformer\\lib\\mrthelper.cpp",
          (const char *)(unsigned int)v45,
          (int)bIgnoreCase);
        v39 = hObject;
LABEL_66:
        if ( v39 )
          CoTaskMemFree(v39);
        v17 = 0;
        goto LABEL_21;
      }
      v39 = hObject;
      StringRawBuffer = (const WCHAR *)hObject;
    }
    v40 = v83;
    if ( v83 )
    {
      if ( sourceString )
      {
        CoTaskMemFree((LPVOID)sourceString);
        sourceString = 0;
      }
      *(_QWORD *)v70 = -1;
      v71 = -1;
      v41 = DataStoreCache::MRTHelper::ResolveImageWithAlternateForm(
              StringRawBuffer,
              v76,
              v68,
              *(struct IResourceContext **)v67,
              a5,
              a6,
              a7,
              v82,
              v81,
              v40,
              v80,
              v79,
              v84,
              (LPVOID *)&sourceString);
    }
    else
    {
      if ( sourceString )
      {
        CoTaskMemFree((LPVOID)sourceString);
        sourceString = 0;
      }
      *(_QWORD *)v70 = -1;
      v71 = -1;
      LODWORD(bIgnoreCase) = a5;
      v41 = DataStoreCache::MRTHelper::ResolveImageWithoutAlternateForm(StringRawBuffer, v76, v68, *(_QWORD *)v67);
    }
    v15 = v41;
    if ( v41 >= 0 )
    {
      if ( *(_QWORD *)v70 == -1 )
      {
        if ( sourceString )
        {
          v42 = -1;
          do
            ++v42;
          while ( sourceString[v42] );
          *(_QWORD *)v70 = v42;
        }
        else
        {
          *(_QWORD *)v70 = 0;
        }
      }
      for ( i = 0; i < *(_QWORD *)v70; ++i )
      {
        if ( sourceString[i] == 47 )
          sourceString[i] = 92;
      }
    }
    goto LABEL_66;
  }
  v50 = SHLoadIndirectString(StringRawBuffer, pszOutBuf, 0x104u, 0);
  v15 = v50;
  if ( v50 < 0 )
  {
    v51 = (unsigned int)v50;
    v52 = 1012;
LABEL_90:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v52,
      (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\mrttransformer\\lib\\mrthelper.cpp",
      (const char *)v51,
      (int)bIgnoreCase);
    goto LABEL_28;
  }
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &hObject,
    pszOutBuf,
    -1);
  v53 = (const WCHAR *)hObject;
  hObject = 0;
  sourceString = v53;
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hObject);
  if ( !sourceString )
  {
    v15 = -2147024882;
    v51 = 2147942414LL;
    v52 = 1015;
    goto LABEL_90;
  }
  v15 = 0;
LABEL_28:
  *a2 = 0;
  v77 = 1;
  if ( v15 < 0 )
  {
    WindowsDeleteString(0);
    *a2 = 0;
    v38 = ShellMRTHelper::Common::TryFallbackToFilePath(
            *((ShellMRTHelper::Common **)v14 + 2),
            *((HSTRING *)v14 + 1),
            string,
            (HSTRING)a2,
            bIgnoreCase);
    if ( v38 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1F0,
        (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\mrttransformer\\lib\\mrthelper.cpp",
        (const char *)(unsigned int)v38,
        bIgnoreCasea);
    v34 = 0;
    if ( !v17 )
      v34 = (unsigned int)v15;
  }
  else
  {
    if ( *(_QWORD *)v70 == -1 )
    {
      if ( sourceString )
      {
        do
          ++v18;
        while ( sourceString[v18] );
        *(_QWORD *)v70 = v18;
      }
      else
      {
        *(_QWORD *)v70 = 0;
      }
    }
    v31 = v70[0];
    v32 = &String1;
    if ( sourceString )
      v32 = sourceString;
    WindowsDeleteString(0);
    *a2 = 0;
    v33 = WindowsCreateString(v32, v31, a2);
    if ( v33 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1E5,
        (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\mrttransformer\\lib\\mrthelper.cpp",
        (const char *)(unsigned int)v33,
        (int)bIgnoreCase);
    v34 = 0;
  }
  wil::ActivityBase<MRTTransformerLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v86, v34);
  if ( sourceString )
  {
    CoTaskMemFree((LPVOID)sourceString);
    sourceString = 0;
  }
  *(_QWORD *)v70 = 0;
  v71 = 0;
  v86 = &MRTTransformerTelemetry::ResolveMrtString::`vftable';
  wil::ActivityBase<MRTTransformerLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v86);
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v89);
  wil::details::shared_object<wil::ActivityBase<MRTTransformerLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<MRTTransformerLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(v88);
  wil::ActivityBase<MRTTransformerLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<MRTTransformerLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<MRTTransformerLogging,_TlgReflectorTag_Param0IsProviderType>(v87);
  WindowsDeleteString(string);
  return a2;
}

```

## disassembly

```asm
0x18000d258  push    rbp
0x18000d25a  push    rbx
0x18000d25b  push    rsi
0x18000d25c  push    rdi
0x18000d25d  push    r12
0x18000d25f  push    r13
0x18000d261  push    r14
0x18000d263  push    r15
0x18000d265  lea     rbp, [rsp-388h]
0x18000d26d  sub     rsp, 488h
0x18000d274  mov     rax, cs:__security_cookie
0x18000d27b  xor     rax, rsp
0x18000d27e  mov     [rbp+3C0h+var_50], rax
0x18000d285  mov     [rbp+3C0h+var_404], r9d
0x18000d289  mov     r13, rdx
0x18000d28c  mov     rbx, rcx
0x18000d28f  mov     [rbp+3C0h+var_3F8], rcx
0x18000d293  mov     [rbp+3C0h+var_3C0], rdx
0x18000d297  mov     rax, [rbp+3C0h+arg_38]
0x18000d29e  mov     [rbp+3C0h+var_3D8], rax
0x18000d2a2  mov     rax, [rbp+3C0h+arg_40]
0x18000d2a9  mov     [rbp+3C0h+var_3E0], rax
0x18000d2ad  mov     rax, [rbp+3C0h+arg_48]
0x18000d2b4  mov     [rbp+3C0h+var_3D0], rax
0x18000d2b8  mov     rcx, [rbp+3C0h+arg_50]
0x18000d2bf  mov     [rbp+3C0h+var_3E8], rcx
0x18000d2c3  mov     rax, [rbp+3C0h+arg_58]
0x18000d2ca  mov     [rbp+3C0h+var_3F0], rax
0x18000d2ce  mov     rdx, [rbp+3C0h+arg_60]
0x18000d2d5  mov     [rbp+3C0h+var_3C8], rdx
0x18000d2d9  xor     edi, edi
0x18000d2db  mov     [rbp+3C0h+var_400], edi
0x18000d2de  test    rcx, rcx
0x18000d2e1  jz      short loc_18000D2E5
0x18000d2e3  mov     [rcx], edi
0x18000d2e5  test    rax, rax
0x18000d2e8  jz      short loc_18000D2ED
0x18000d2ea  mov     [rax], rdi
0x18000d2ed  test    rdx, rdx
0x18000d2f0  jz      short loc_18000D2F5
0x18000d2f2  mov     [rdx], rdi
0x18000d2f5  mov     rdx, r8
0x18000d2f8  lea     rcx, [rbp+3C0h+string]
0x18000d2fc  call    ?SimplifyFullyQualifiedResourceStringIfApplicable@MRTHelper@DataStoreCache@@KA?AVHString@Wrappers@WRL@Microsoft@@PEAUHSTRING__@@@Z; DataStoreCache::MRTHelper::SimplifyFullyQualifiedResourceStringIfApplicable(HSTRING__ *)
0x18000d301  nop
0x18000d302  mov     [rbp+3C0h+length], edi
0x18000d305  lea     rdx, [rbp+3C0h+length]; length
0x18000d309  mov     rcx, [rbp+3C0h+string]; string
0x18000d30d  call    cs:__imp_WindowsGetStringRawBuffer
0x18000d313  mov     r12, rax
0x18000d316  lea     rdx, aResolvemrtstri; "ResolveMrtString"
0x18000d31d  lea     rcx, [rbp+3C0h+var_3B0]; struct wil::details::IFailureCallback *
0x18000d321  call    ??0?$ActivityBase@VMRTTransformerLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<MRTTransformerLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<MRTTransformerLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18000d326  lea     rax, ??_7ResolveMrtString@MRTTransformerTelemetry@@6B@; const MRTTransformerTelemetry::ResolveMrtString::`vftable'
0x18000d32d  mov     [rbp+3C0h+var_3B0], rax
0x18000d331  mov     r8, r12
0x18000d334  mov     edx, 1
0x18000d339  lea     rcx, [rbp+3C0h+var_3B0]
0x18000d33d  call    ?StartActivity@ResolveMrtString@MRTTransformerTelemetry@@QEAAXW4MRTResolutionType@MRTHelper@DataStoreCache@@PEBG@Z; MRTTransformerTelemetry::ResolveMrtString::StartActivity(DataStoreCache::MRTHelper::MRTResolutionType,ushort const *)
0x18000d342  nop
0x18000d343  mov     sil, dil
0x18000d346  mov     [rsp+4C0h+var_44F], dil
0x18000d34b  or      r14, 0FFFFFFFFFFFFFFFFh
0x18000d34f  mov     qword ptr [rbp+3C0h+var_430], r14
0x18000d353  mov     [rbp+3C0h+var_428], r14
0x18000d357  mov     [rbp+3C0h+sourceString], rdi
0x18000d35b  cmp     [rbp+3C0h+length], 2
0x18000d35f  jb      short loc_18000D36D
0x18000d361  cmp     word ptr [r12], 40h ; '@'
0x18000d367  jz      loc_18000D966
0x18000d36d  mov     qword ptr [rbp+3C0h+var_430], r14
0x18000d371  mov     [rbp+3C0h+var_428], r14
0x18000d375  mov     rsi, [rbp+3C0h+string]
0x18000d379  mov     [rbp+3C0h+var_418], rsi
0x18000d37d  mov     [rbp+3C0h+sourceString], rdi
0x18000d381  mov     [rsp+4C0h+var_448], edi
0x18000d385  lea     rdx, [rsp+4C0h+var_448]; length
0x18000d38a  mov     rcx, rsi; string
0x18000d38d  call    cs:__imp_WindowsGetStringRawBuffer
0x18000d393  lea     r15, aShellcommonShe_207; "shellcommon\\shell\\datastorecache\\tra"...
0x18000d39a  mov     edx, 5; cchCount1
0x18000d39f  cmp     [rsp+4C0h+var_448], edx
0x18000d3a3  jb      short loc_18000D3C9
0x18000d3a5  mov     [rsp+4C0h+bIgnoreCase], 1; int
0x18000d3ad  mov     r9d, edx; cchCount2
0x18000d3b0  lea     r8, ?c_fileUriScheme@Common@ShellMRTHelper@@3QBGB; "file:"
0x18000d3b7  mov     rcx, rax; lpString1
0x18000d3ba  call    cs:__imp_CompareStringOrdinal
0x18000d3c0  cmp     eax, 2
0x18000d3c3  jz      loc_18000D631
0x18000d3c9  mov     [rsp+4C0h+var_450], dil
0x18000d3ce  mov     [rsp+4C0h+var_448], edi
0x18000d3d2  lea     rdx, [rsp+4C0h+var_448]; length
0x18000d3d7  mov     rcx, rsi; string
0x18000d3da  call    cs:__imp_WindowsGetStringRawBuffer
0x18000d3e0  mov     edx, 0Bh; cchCount1
0x18000d3e5  cmp     [rsp+4C0h+var_448], edx
0x18000d3e9  jb      short loc_18000D40F
0x18000d3eb  mov     [rsp+4C0h+bIgnoreCase], 1; int
0x18000d3f3  mov     r9d, edx; cchCount2
0x18000d3f6  lea     r8, ?c_msAppDataUriScheme@Common@ShellMRTHelper@@3QBGB; "ms-appdata:"
0x18000d3fd  mov     rcx, rax; lpString1
0x18000d400  call    cs:__imp_CompareStringOrdinal
0x18000d406  cmp     eax, 2
0x18000d409  jz      loc_18000D8FE
0x18000d40f  cmp     [rsp+4C0h+var_450], 0
0x18000d414  jnz     loc_18000DAF6
0x18000d41a  xor     edi, edi
0x18000d41c  mov     [rbp+3C0h+var_418], rdi
0x18000d420  mov     [rbp+3C0h+var_440], rdi
0x18000d424  lea     rcx, [rbp+3C0h+var_440]
0x18000d428  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000d42d  lea     rcx, [rbp+3C0h+var_418]
0x18000d431  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000d436  lea     r8, [rbp+3C0h+var_440]; struct IResourceMap **
0x18000d43a  lea     rdx, [rbp+3C0h+var_418]; struct IMrtResourceManager **
0x18000d43e  mov     rsi, [rbp+3C0h+var_3F8]
0x18000d442  mov     rcx, rsi; this
0x18000d445  call    ?TryEnsureResourceManagerAndMap@MRTHelper@DataStoreCache@@IEAAJPEAPEAUIMrtResourceManager@@PEAPEAUIResourceMap@@@Z; DataStoreCache::MRTHelper::TryEnsureResourceManagerAndMap(IMrtResourceManager * *,IResourceMap * *)
0x18000d44a  mov     rcx, [rbp+3C8h]; this
0x18000d451  test    eax, eax
0x18000d453  js      loc_18000D60F
0x18000d459  mov     qword ptr [rsp+4C0h+var_448], rdi
0x18000d45e  mov     rbx, [rbp+3C0h+var_418]
0x18000d462  test    rbx, rbx
0x18000d465  jz      short loc_18000D4A0
0x18000d467  mov     rax, [rbx]
0x18000d46a  mov     rdi, [rax+48h]
0x18000d46e  lea     rcx, [rsp+4C0h+var_448]
0x18000d473  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000d478  lea     r8, [rsp+4C0h+var_448]
0x18000d47d  lea     rdx, _GUID_e3c22b30_8502_4b2f_9133_559674587e51
0x18000d484  mov     rcx, rbx
0x18000d487  mov     rax, rdi
0x18000d48a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d48f  mov     rcx, [rbp+3C8h]; this
0x18000d496  xor     edi, edi
0x18000d498  test    eax, eax
0x18000d49a  js      loc_18000D699
0x18000d4a0  cmp     qword ptr [rsp+4C0h+var_448], rdi
0x18000d4a5  jz      short loc_18000D4B1
0x18000d4a7  cmp     [rbp+3C0h+var_440], rdi
0x18000d4ab  jnz     loc_18000D6F8
0x18000d4b1  mov     sil, 1
0x18000d4b4  mov     edi, 80070490h
0x18000d4b9  xor     r12d, r12d
0x18000d4bc  mov     rcx, qword ptr [rsp+4C0h+var_448]
0x18000d4c1  test    rcx, rcx
0x18000d4c4  jz      short loc_18000D4D8
0x18000d4c6  mov     qword ptr [rsp+4C0h+var_448], r12
0x18000d4cb  mov     rax, [rcx]
0x18000d4ce  mov     rax, [rax+10h]
0x18000d4d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d4d7  nop
0x18000d4d8  mov     rcx, [rbp+3C0h+var_440]
0x18000d4dc  test    rcx, rcx
0x18000d4df  jz      short loc_18000D4F2
0x18000d4e1  mov     [rbp+3C0h+var_440], r12
0x18000d4e5  mov     rax, [rcx]
0x18000d4e8  mov     rax, [rax+10h]
0x18000d4ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d4f1  nop
0x18000d4f2  mov     rcx, [rbp+3C0h+var_418]
0x18000d4f6  test    rcx, rcx
0x18000d4f9  jz      short loc_18000D50C
0x18000d4fb  mov     [rbp+3C0h+var_418], r12
0x18000d4ff  mov     rax, [rcx]
0x18000d502  mov     rax, [rax+10h]
0x18000d506  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d50b  nop
0x18000d50c  mov     rbx, [rbp+3C0h+var_3F8]
0x18000d510  mov     [r13+0], r12
0x18000d514  mov     [rbp+3C0h+var_400], 1
0x18000d51b  test    edi, edi
0x18000d51d  js      loc_18000D6AE
0x18000d523  cmp     qword ptr [rbp+3C0h+var_430], r14
0x18000d527  jnz     short loc_18000D544
0x18000d529  mov     rax, [rbp+3C0h+sourceString]
0x18000d52d  test    rax, rax
0x18000d530  jz      loc_18000DB03
0x18000d536  inc     r14
0x18000d539  cmp     [rax+r14*2], r12w
0x18000d53e  jnz     short loc_18000D536
0x18000d540  mov     qword ptr [rbp+3C0h+var_430], r14
0x18000d544  mov     edi, [rbp+3C0h+var_430]
0x18000d547  mov     rax, [rbp+3C0h+sourceString]
0x18000d54b  lea     rbx, String1
0x18000d552  test    rax, rax
0x18000d555  cmovnz  rbx, rax
0x18000d559  xor     ecx, ecx; string
0x18000d55b  call    cs:__imp_WindowsDeleteString
0x18000d561  mov     [r13+0], r12
0x18000d565  mov     r8, r13; string
0x18000d568  mov     edx, edi; length
0x18000d56a  mov     rcx, rbx; sourceString
0x18000d56d  call    cs:__imp_WindowsCreateString
0x18000d573  mov     rcx, [rbp+3C8h]; this
0x18000d57a  test    eax, eax
0x18000d57c  js      loc_18000D620
0x18000d582  xor     edx, edx
0x18000d584  lea     rcx, [rbp+3C0h+var_3B0]
0x18000d588  call    ?Stop@?$ActivityBase@VMRTTransformerLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<MRTTransformerLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18000d58d  nop
0x18000d58e  mov     rcx, [rbp+3C0h+sourceString]; pv
0x18000d592  test    rcx, rcx
0x18000d595  jz      short loc_18000D5A1
0x18000d597  call    cs:__imp_CoTaskMemFree
0x18000d59d  mov     [rbp+3C0h+sourceString], r12
0x18000d5a1  mov     qword ptr [rbp+3C0h+var_430], r12
0x18000d5a5  mov     [rbp+3C0h+var_428], r12
0x18000d5a9  lea     rax, ??_7ResolveMrtString@MRTTransformerTelemetry@@6B@; const MRTTransformerTelemetry::ResolveMrtString::`vftable'
0x18000d5b0  mov     [rbp+3C0h+var_3B0], rax
0x18000d5b4  lea     rcx, [rbp+3C0h+var_3B0]
0x18000d5b8  call    ?Destroy@?$ActivityBase@VMRTTransformerLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<MRTTransformerLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18000d5bd  lea     rcx, [rbp+3C0h+var_290]; this
0x18000d5c4  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x18000d5c9  lea     rcx, [rbp+3C0h+var_298]
0x18000d5d0  call    ?reset@?$shared_object@V?$ActivityData@VMRTTransformerLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VMRTTransformerLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<MRTTransformerLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<MRTTransformerLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x18000d5d5  lea     rcx, [rbp+3C0h+var_3A8]
0x18000d5d9  call    ??1?$ActivityData@VMRTTransformerLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VMRTTransformerLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<MRTTransformerLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<MRTTransformerLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<MRTTransformerLogging,_TlgReflectorTag_Param0IsProviderType>(void)
0x18000d5de  nop
0x18000d5df  mov     rcx, [rbp+3C0h+string]; string
0x18000d5e3  call    cs:__imp_WindowsDeleteString
0x18000d5e9  mov     rax, r13
0x18000d5ec  mov     rcx, [rbp+3C0h+var_50]
0x18000d5f3  xor     rcx, rsp; StackCookie
0x18000d5f6  call    __security_check_cookie
0x18000d5fb  add     rsp, 488h
0x18000d602  pop     r15
0x18000d604  pop     r14
0x18000d606  pop     r13
0x18000d608  pop     r12
0x18000d60a  pop     rdi
0x18000d60b  pop     rsi
0x18000d60c  pop     rbx
0x18000d60d  pop     rbp
0x18000d60e  retn
0x18000d60f  mov     r9d, eax; char *
0x18000d612  mov     r8, r15; unsigned int
0x18000d615  mov     edx, 17Eh; void *
0x18000d61a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000d620  mov     r9d, eax; char *
0x18000d623  mov     r8, r15; unsigned int
0x18000d626  mov     edx, 1E5h; void *
0x18000d62b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000d631  mov     [rsp+4C0h+var_450], 1
0x18000d636  mov     qword ptr [rsp+4C0h+var_448], rdi
0x18000d63b  lea     rcx, [rsp+4C0h+var_448]
0x18000d640  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000d645  lea     rdx, [rsp+4C0h+var_448]; struct IAppUriResolver **
0x18000d64a  mov     rcx, rbx; this
0x18000d64d  call    ?EnsureAppUriResolver@MRTHelper@DataStoreCache@@IEAAJPEAPEAUIAppUriResolver@@@Z; DataStoreCache::MRTHelper::EnsureAppUriResolver(IAppUriResolver * *)
0x18000d652  mov     edi, eax
0x18000d654  test    eax, eax
0x18000d656  jns     loc_18000D9FD
0x18000d65c  mov     rcx, [rbp+3C8h]; this
0x18000d663  mov     r9d, eax; char *
0x18000d666  mov     r8, r15; unsigned int
0x18000d669  mov     edx, 3C4h; void *
0x18000d66e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d673  nop
0x18000d674  mov     rcx, qword ptr [rsp+4C0h+var_448]
0x18000d679  test    rcx, rcx
0x18000d67c  jz      short loc_18000D694
0x18000d67e  mov     qword ptr [rsp+4C0h+var_448], 0
0x18000d687  mov     rax, [rcx]
0x18000d68a  mov     rax, [rax+10h]
0x18000d68e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d693  nop
0x18000d694  jmp     loc_18000D40F
0x18000d699  mov     r9d, eax; char *
0x18000d69c  mov     r8, r15; unsigned int
0x18000d69f  mov     edx, 185h; void *
0x18000d6a4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000d6a9  jmp     loc_18000D4A0
0x18000d6ae  xor     ecx, ecx; string
0x18000d6b0  call    cs:__imp_WindowsDeleteString
0x18000d6b6  mov     [r13+0], r12
0x18000d6ba  mov     r9, r13; HSTRING
0x18000d6bd  mov     r8, [rbp+3C0h+string]; HSTRING
0x18000d6c1  mov     rdx, [rbx+8]; HSTRING
0x18000d6c5  mov     rcx, [rbx+10h]; this
0x18000d6c9  call    ?TryFallbackToFilePath@Common@ShellMRTHelper@@YAJPEAUHSTRING__@@00PEAPEAU3@@Z; ShellMRTHelper::Common::TryFallbackToFilePath(HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ * *)
0x18000d6ce  mov     rcx, [rbp+3C8h]; this
0x18000d6d5  test    eax, eax
0x18000d6d7  js      short loc_18000D6E7
0x18000d6d9  mov     edx, r12d
0x18000d6dc  test    sil, sil
0x18000d6df  cmovz   edx, edi
0x18000d6e2  jmp     loc_18000D584
0x18000d6e7  mov     r9d, eax; char *
0x18000d6ea  mov     r8, r15; unsigned int
0x18000d6ed  mov     edx, 1F0h; void *
0x18000d6f2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000d6f8  mov     rbx, rdi
0x18000d6fb  mov     [rbp+3C0h+hObject], rbx
0x18000d6ff  cmp     [rsi+8], rdi
0x18000d703  jnz     loc_18000D883
0x18000d709  mov     rdi, [rbp+3C0h+var_3D0]
0x18000d70d  mov     rcx, [rbp+3C0h+sourceString]; pv
  ... truncated ...
```
