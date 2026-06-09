# DataStoreCache::AppResolverTransformer::GetVerbs(WindowsInternal::Shell::UnifiedTile::IUnifiedTile *,WindowsInternal::Shell::UnifiedTile::IVerbEnumerationArgs *,Windows::Foundation::Collections::IVectorView<WindowsInternal::Shell::UnifiedTile::TileVerb *> * *)

- ea: `0x18013f6a0`
- end: `0x18014050d`
- name: `?GetVerbs@AppResolverTransformer@DataStoreCache@@UEAAJPEAUIUnifiedTile@UnifiedTile@Shell@WindowsInternal@@PEAUIVerbEnumerationArgs@456@PEAPEAU?$IVectorView@PEAVTileVerb@UnifiedTile@Shell@WindowsInternal@@@Collections@Foundation@Windows@@@Z`
- size: `3693`
- prototype: ``
- caller_count: `0`
- callee_count: `29`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18000ce94`
- `0x18001aca4`
- `0x180021dd8`
- `0x180022020`
- `0x18002ca10`
- `0x180033860`
- `0x180035a98`
- `0x18003640c`
- `0x18003d71c`
- `0x18004ffc0`
- `0x18008272c`
- `0x1800dab70`
- `0x1800dd06c`
- `0x180118dcc`
- `0x18011b860`
- `0x180125178`
- `0x18013006c`
- `0x18013f6a0`
- `0x180140aa4`
- `0x1801593b0`
- `0x180161204`
- `0x1801a31d4`
- `0x1801a4a64`
- `0x1801a53f0`
- `0x1801b80a8`
- `0x180201e50`
- `0x18031c37c`
- `0x18031c8b0`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18013f971`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18013fa32`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18013fa71`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18013fcdd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18013fd6b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18013fdc5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18013fe03`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18013ff45`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801403fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18013f971`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18013fa32`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18013fa71`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18013fcdd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18013fd6b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18013fdc5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18013fe03`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18013ff45`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801403fc`
- `SHCORE!__imp_SHWindowsPolicy` at `0x18013fe87`
- `SHCORE!__imp_SHWindowsPolicy` at `0x18013fe87`

## string_xrefs

- `0x18013f780`: `shellcommon\shell\datastorecache\transformers\appresolvertransformer\lib\appresolvertransformer.cpp`
- `0x18013f7d4`: `shellcommon\shell\datastorecache\transformers\appresolvertransformer\lib\appresolvertransformer.cpp`
- `0x18013f831`: `shellcommon\shell\datastorecache\transformers\appresolvertransformer\lib\appresolvertransformer.cpp`
- `0x18013f87c`: `shellcommon\shell\datastorecache\transformers\appresolvertransformer\lib\appresolvertransformer.cpp`
- `0x18013f8b4`: `shellcommon\shell\datastorecache\transformers\appresolvertransformer\lib\appresolvertransformer.cpp`
- `0x18013f977`: `shellcommon\shell\datastorecache\transformers\appresolvertransformer\lib\appresolvertransformer.cpp`
- `0x18013f9b1`: `shellcommon\shell\datastorecache\transformers\appresolvertransformer\lib\appresolvertransformer.cpp`
- `0x18013f9ba`: `shellcommon\shell\datastorecache\transformers\appresolvertransformer\lib\appresolvertransformer.cpp`
- `0x1801404fb`: `shellcommon\shell\datastorecache\transformers\appresolvertransformer\lib\appresolvertransformer.cpp`
- `0x18013fd22`: `Uninstall`
- `0x1801400f1`: `TabletMode_OpenNewWindow`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
__int64 __fastcall DataStoreCache::AppResolverTransformer::GetVerbs(
        __int64 a1,
        struct WindowsInternal::Shell::UnifiedTile::IUnifiedTile *a2,
        struct WindowsInternal::Shell::UnifiedTile::IVerbEnumerationArgs *a3,
        _QWORD *a4)
{
  const char *v7; // r9
  __int64 v8; // rcx
  int v9; // eax
  unsigned int v10; // ebx
  __int64 (__fastcall *v11)(struct WindowsInternal::Shell::UnifiedTile::IVerbEnumerationArgs *, GUID *, __int64 *); // rbx
  int v12; // eax
  DataStoreCache::AppResolverTransformer *v13; // r15
  int v14; // eax
  __int64 (__fastcall *v15)(struct WindowsInternal::Shell::UnifiedTile::IUnifiedTile *, struct WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier **); // rbx
  int v16; // eax
  __int64 v17; // rdx
  char v18; // r14
  __int64 v19; // rbx
  __int64 (__fastcall *v20)(__int64, int *, _QWORD); // rdi
  _QWORD *v21; // rax
  __int64 v22; // rax
  __int64 v23; // rdi
  __int64 (__fastcall *v24)(__int64, const struct _GUID *, GUID *, __int64); // rbx
  __int64 v25; // rax
  __int64 v26; // rcx
  const char *v27; // r9
  int v28; // eax
  __int64 v29; // rdi
  __int64 (__fastcall *v30)(__int64, HSTRING *); // rbx
  int v31; // eax
  int TileVerbProviderDesktopBroker; // eax
  __int64 v33; // rdx
  unsigned __int64 v34; // r9
  struct WindowsInternal::Shell::UnifiedTile::Private::ITileVerbProviderDesktopBrokerStatics *v35; // rdi
  __int64 (__fastcall *v36)(struct WindowsInternal::Shell::UnifiedTile::Private::ITileVerbProviderDesktopBrokerStatics *, HSTRING, struct WindowsInternal::Shell::UnifiedTile::IVerbEnumerationArgs *, __int64 *); // rbx
  int v37; // eax
  unsigned int v38; // ecx
  __int64 (__fastcall *v39)(struct WindowsInternal::Shell::UnifiedTile::Private::ITileVerbProviderDesktopBrokerStatics *, HSTRING, struct WindowsInternal::Shell::UnifiedTile::IVerbEnumerationArgs *, __int64 *); // rbx
  int v40; // ecx
  int v41; // r15d
  struct WindowsInternal::Shell::UnifiedTile::ITileVerb **Reserved1; // r13
  int v43; // eax
  int v44; // eax
  HSTRING v45; // rdi
  __int64 (__fastcall *v46)(HSTRING, HSTRING *); // rbx
  int v47; // eax
  bool v48; // al
  __int64 v49; // rbx
  __int64 v50; // rax
  char v51; // bl
  DataStoreCache::AppResolverTransformer *v52; // r13
  int UninstallVerb; // eax
  __int64 v54; // rdx
  int *v55; // rcx
  int v56; // eax
  int v57; // r15d
  char v58; // al
  __int64 v59; // r12
  int v60; // eax
  __int64 v61; // rdx
  __int64 v62; // rdi
  __int64 (__fastcall *v63)(__int64, HSTRING, char *); // rbx
  int v64; // eax
  int v65; // eax
  wil::details::in1diag3 *v66; // rcx
  __int64 v67; // rdx
  __int64 v68; // rdi
  __int64 (__fastcall *v69)(__int64, HSTRING, char *); // rbx
  int v70; // eax
  __int64 v71; // rdx
  struct WindowsInternal::Shell::UnifiedTile::IVerbEnumerationArgs *v73; // [rsp+20h] [rbp-2C8h]
  char v74[8]; // [rsp+40h] [rbp-2A8h] BYREF
  HSTRING v75; // [rsp+48h] [rbp-2A0h] BYREF
  __int64 v76; // [rsp+50h] [rbp-298h] BYREF
  struct DataStoreCache::IDataStorePropertyBag *v77; // [rsp+58h] [rbp-290h] BYREF
  struct WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier *v78; // [rsp+60h] [rbp-288h] BYREF
  _BYTE v79[8]; // [rsp+68h] [rbp-280h] BYREF
  __int64 v80; // [rsp+70h] [rbp-278h] BYREF
  __int64 v81; // [rsp+78h] [rbp-270h] BYREF
  DataStoreCache::AppResolverTransformer *v82; // [rsp+80h] [rbp-268h] BYREF
  int v83; // [rsp+88h] [rbp-260h] BYREF
  struct WindowsInternal::Shell::UnifiedTile::Private::ITileVerbProviderDesktopBrokerStatics *v84; // [rsp+90h] [rbp-258h] BYREF
  __int64 v85; // [rsp+98h] [rbp-250h] BYREF
  __int64 v86; // [rsp+A0h] [rbp-248h] BYREF
  HSTRING string; // [rsp+A8h] [rbp-240h] BYREF
  int v88[2]; // [rsp+B0h] [rbp-238h] BYREF
  struct WindowsInternal::Shell::UnifiedTile::IUnifiedTile *v89; // [rsp+B8h] [rbp-230h] BYREF
  HSTRING v90; // [rsp+C0h] [rbp-228h] BYREF
  DataStoreCache::AppResolverTransformer *v91; // [rsp+C8h] [rbp-220h]
  __int64 v92; // [rsp+D0h] [rbp-218h] BYREF
  int v93; // [rsp+D8h] [rbp-210h] BYREF
  int v94; // [rsp+DCh] [rbp-20Ch] BYREF
  int v95; // [rsp+E0h] [rbp-208h] BYREF
  struct WindowsInternal::Shell::UnifiedTile::IVerbEnumerationArgs *v96; // [rsp+E8h] [rbp-200h] BYREF
  _QWORD v97[2]; // [rsp+F0h] [rbp-1F8h] BYREF
  _QWORD *v98; // [rsp+100h] [rbp-1E8h]
  _BYTE v99[8]; // [rsp+108h] [rbp-1E0h] BYREF
  int v100; // [rsp+110h] [rbp-1D8h]
  _BYTE v101[8]; // [rsp+128h] [rbp-1C0h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+130h] [rbp-1B8h] BYREF
  HSTRING v103; // [rsp+148h] [rbp-1A0h]
  _QWORD v104[42]; // [rsp+150h] [rbp-198h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2E8h] [rbp+0h]

  v98 = a4;
  v89 = a2;
  v92 = a1;
  v97[0] = a2;
  v96 = a3;
  LODWORD(v85) = 0;
  LODWORD(v82) = 0;
  *a4 = 0;
  wil::ActivityBase<DataStoreTransformerLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DataStoreTransformerLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v104,
    "AppResolverTransformer_GetVerbs");
  v104[0] = &DataStoreTransformerTelemetry::AppResolverTransformer_GetVerbs::`vftable';
  DataStoreTransformerTelemetry::AppResolverTransformer_GetVerbs::StartActivity((DataStoreTransformerTelemetry::AppResolverTransformer_GetVerbs *)v104);
  if ( !a3 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x152,
      (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\appresolvertransformer\\lib\\appresolvertransformer.cpp",
      v7);
  v86 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v86);
  v9 = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<WindowsInternal::Shell::UnifiedTile::TileVerb,Windows::Foundation::Collections::Internal::AgileVector<WindowsInternal::Shell::UnifiedTile::TileVerb *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<WindowsInternal::Shell::UnifiedTile::TileVerb *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<WindowsInternal::Shell::UnifiedTile::TileVerb *>,0>>(
         v8,
         &v86);
  v10 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x155,
      (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\appresolvertransformer\\lib\\appresolvertransformer.cpp",
      (const char *)(unsigned int)v9,
      (int)v73);
LABEL_117:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v86);
    DataStoreTransformerTelemetry::AppResolverTransformer_GetVerbs::~AppResolverTransformer_GetVerbs((DataStoreTransformerTelemetry::AppResolverTransformer_GetVerbs *)v104);
    return v10;
  }
  v76 = 0;
  v11 = **(__int64 (__fastcall ***)(struct WindowsInternal::Shell::UnifiedTile::IVerbEnumerationArgs *, GUID *, __int64 *))a3;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v76);
  v12 = v11(a3, &GUID_3b8c9be7_fc8c_42e2_a6b5_7005aa719c35, &v76);
  v10 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x158,
      (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\appresolvertransformer\\lib\\appresolvertransformer.cpp",
      (const char *)(unsigned int)v12,
      (int)v73);
LABEL_116:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v76);
    goto LABEL_117;
  }
  v78 = 0;
  v77 = 0;
  v74[0] = 0;
  v13 = (DataStoreCache::AppResolverTransformer *)(a1 - 48);
  v91 = (DataStoreCache::AppResolverTransformer *)(a1 - 48);
  v14 = (*(__int64 (__fastcall **)(__int64, _QWORD, char *))(*(_QWORD *)v76 + 48LL))(
          v76,
          *(_QWORD *)(a1 - 48 + 256),
          v74);
  if ( v14 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x15D,
      (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\appresolvertransformer\\lib\\appresolvertransformer.cpp",
      (const char *)(unsigned int)v14,
      (int)v73);
LABEL_19:
    v18 = 1;
    goto LABEL_20;
  }
  if ( !v74[0] )
    goto LABEL_19;
  v15 = *(__int64 (__fastcall **)(struct WindowsInternal::Shell::UnifiedTile::IUnifiedTile *, struct WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier **))(*(_QWORD *)a2 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v78);
  v16 = v15(a2, &v78);
  v10 = v16;
  if ( v16 < 0 )
  {
    v17 = 351;
LABEL_114:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\appresolvertransformer\\lib\\appresolvertransformer.cpp",
      (const char *)(unsigned int)v16,
      (int)v73);
    goto LABEL_115;
  }
  v93 = 0;
  v16 = (*(__int64 (__fastcall **)(struct WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier *, int *))(*(_QWORD *)v78 + 48LL))(
          v78,
          &v93);
  v10 = v16;
  if ( v16 < 0 )
  {
    v17 = 354;
    goto LABEL_114;
  }
  v18 = 1;
  if ( v93 == 2 )
  {
    v74[0] = 1;
    try
    {
      v19 = *(_QWORD *)(a1 + 104);
      v20 = *(__int64 (__fastcall **)(__int64, int *, _QWORD))(*(_QWORD *)v19 + 40LL);
      v21 = (_QWORD *)DataStoreCache::DataItemIdentifier::DataItemIdentifier(
                        (DataStoreCache::DataItemIdentifier *)&string,
                        v78);
      v22 = v20(v19, v88, *v21);
      v23 = *(_QWORD *)v22;
      v24 = *(__int64 (__fastcall **)(__int64, const struct _GUID *, GUID *, __int64))(**(_QWORD **)v22 + 48LL);
      v25 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::Private::IUnifiedTilePrivate>>(&v77);
      v74[0] = v24(v23, &c_appResolverTransformerId, &GUID_9dbb8733_cc6a_4eba_92cc_25fc80f0c2cb, v25);
      v26 = *(_QWORD *)v88;
      if ( *(_QWORD *)v88 )
      {
        *(_QWORD *)v88 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
      }
      WindowsDeleteString(string);
    }
    catch ( ... )
    {
      LODWORD(v85) = wil::details::in1diag3::Return_CaughtException(
                       retaddr,
                       (void *)0x16D,
                       (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\appresolvertransformer\\lib\\appr"
                                     "esolvertransformer.cpp",
                       v27);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v77);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v78);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v76);
      v10 = v85;
      goto LABEL_117;
    }
  }
  else
  {
    v74[0] = 0;
  }
LABEL_20:
  if ( !v74[0] || !v77 )
    goto LABEL_112;
  v81 = 0;
  v28 = Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier>::As<WindowsInternal::Shell::UnifiedTile::IWin32UnifiedTileIdentifier>(
          &v78,
          &v81);
  v10 = v28;
  if ( v28 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x174,
      (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\appresolvertransformer\\lib\\appresolvertransformer.cpp",
      (const char *)(unsigned int)v28,
      (int)v73);
LABEL_24:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v81);
LABEL_115:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v77);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v78);
    goto LABEL_116;
  }
  v75 = 0;
  v29 = v81;
  v30 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v81 + 48LL);
  WindowsDeleteString(0);
  v75 = 0;
  v31 = v30(v29, &v75);
  v10 = v31;
  if ( v31 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x177,
      (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\appresolvertransformer\\lib\\appresolvertransformer.cpp",
      (const char *)(unsigned int)v31,
      (int)v73);
LABEL_27:
    WindowsDeleteString(v75);
    v75 = 0;
    goto LABEL_24;
  }
  v80 = 0;
  v84 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v84);
  TileVerbProviderDesktopBroker = DataStoreCache::AppResolverTransformer::GetTileVerbProviderDesktopBroker(v13, 0, &v84);
  v10 = TileVerbProviderDesktopBroker;
  if ( TileVerbProviderDesktopBroker < 0 )
  {
    v33 = 380;
LABEL_30:
    v34 = (unsigned int)TileVerbProviderDesktopBroker;
LABEL_31:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v33,
      (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\appresolvertransformer\\lib\\appresolvertransformer.cpp",
      (const char *)v34,
      (int)v73);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v84);
LABEL_32:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v80);
    goto LABEL_27;
  }
  v35 = v84;
  v36 = *(__int64 (__fastcall **)(struct WindowsInternal::Shell::UnifiedTile::Private::ITileVerbProviderDesktopBrokerStatics *, HSTRING, struct WindowsInternal::Shell::UnifiedTile::IVerbEnumerationArgs *, __int64 *))(*(_QWORD *)v84 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v80);
  v37 = v36(v35, v75, a3, &v80);
  v10 = v37;
  if ( v37 < 0 )
  {
    if ( !IsServerFailedError(v37) )
    {
      v34 = v38;
      v33 = 387;
      goto LABEL_31;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v84);
    TileVerbProviderDesktopBroker = DataStoreCache::AppResolverTransformer::GetTileVerbProviderDesktopBroker(
                                      v13,
                                      1,
                                      &v84);
    v10 = TileVerbProviderDesktopBroker;
    if ( TileVerbProviderDesktopBroker < 0 )
    {
      v33 = 388;
      goto LABEL_30;
    }
    v35 = v84;
    v39 = *(__int64 (__fastcall **)(struct WindowsInternal::Shell::UnifiedTile::Private::ITileVerbProviderDesktopBrokerStatics *, HSTRING, struct WindowsInternal::Shell::UnifiedTile::IVerbEnumerationArgs *, __int64 *))(*(_QWORD *)v84 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v80);
    TileVerbProviderDesktopBroker = v39(v35, v75, a3, &v80);
    v10 = TileVerbProviderDesktopBroker;
    if ( TileVerbProviderDesktopBroker < 0 )
    {
      v33 = 389;
      goto LABEL_30;
    }
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v84);
  v94 = 0;
  LOBYTE(v35) = 0;
  LODWORD(v82) = (_DWORD)v35;
  wil::GetRangeNoThrow<WindowsInternal::Shell::UnifiedTile::Private::UnifiedTileVerbProvider *>(v99, v80, &v94);
  wil::vector_range_nothrow<Windows::Foundation::Collections::IVectorView<WindowsInternal::Shell::UnifiedTile::TileVerb *>>::begin(
    v99,
    &hstringHeader);
  v40 = v100;
  v83 = v100;
  v41 = *(_DWORD *)&hstringHeader.Reserved.Reserved2[8];
  Reserved1 = (struct WindowsInternal::Shell::UnifiedTile::ITileVerb **)hstringHeader.Reserved.Reserved1;
  while ( *(int *)Reserved1[2] >= 0 && v41 != v40 )
  {
    string = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&string);
    v43 = DataStoreCache::AppResolverTransformer::ReprocessTileShellItemVerb(
            v91,
            Reserved1[4],
            v89,
            v77,
            a3,
            (struct WindowsInternal::Shell::UnifiedTile::ITileVerb **)&string);
    if ( v43 >= 0 )
    {
      if ( string )
      {
        v44 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v86 + 104LL))(v86);
        v10 = v44;
        if ( v44 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x192,
            (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\appresolvertransformer\\lib\\appresolvertransformer.cpp",
            (const char *)(unsigned int)v44,
            (int)v73);
LABEL_53:
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&string);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v101);
LABEL_54:
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v80);
          WindowsDeleteString(v75);
          v75 = 0;
          goto LABEL_24;
        }
        v90 = 0;
        v45 = string;
        v46 = *(__int64 (__fastcall **)(HSTRING, HSTRING *))(*(_QWORD *)string + 64LL);
        WindowsDeleteString(0);
        v90 = 0;
        v47 = v46(v45, &v90);
        v10 = v47;
        if ( v47 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x194,
            (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\appresolvertransformer\\lib\\appresolvertransformer.cpp",
            (const char *)(unsigned int)v47,
            (int)v73);
          WindowsDeleteString(v90);
          v90 = 0;
          goto LABEL_53;
        }
        v103 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Uninstall", 0xAu, 9u);
        v48 = DataStoreCache::AppResolverTransformer::AreStringsEqualCaseInsensitive(v90, v103);
        LODWORD(v35) = (unsigned __int8)v82;
        if ( v48 )
          LODWORD(v35) = 1;
        LODWORD(v82) = (_DWORD)v35;
        WindowsDeleteString(v90);
        v90 = 0;
      }
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x190,
        (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\appresolvertransformer\\lib\\appresolvertransformer.cpp",
        (const char *)(unsigned int)v43,
        (int)v73);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&string);
    wil::vector_range_nothrow<Windows::Foundation::Collections::IVectorView<Windows::Services::Store::StoreAvailability *>>::get_at_current(
      Reserved1,
      (unsigned int)++v41);
    v40 = v83;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v101);
  v10 = v94;
  if ( v94 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x19B,
      (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\appresolvertransformer\\lib\\appresolvertransformer.cpp",
      (const char *)(unsigned int)v94,
      (int)v73);
    goto LABEL_54;
  }
  v49 = wil::convert_from_abi<winrt::WindowsInternal::Shell::UnifiedTile::IUnifiedTile>(&v89, v89);
  if ( (_BYTE)v35
    || (unsigned int)SHWindowsPolicy(POLID_NoUninstallFromStart)
    || (v50 = std::find_if<std::pair<unsigned short const *,bool (*)(void)> *,_lambda_7279b51452658a7d10556febb09a5f05_>(
                &`DataStoreCache::AppResolverTransformer::ShouldAddUninstallVerb'::`2'::tileUninstallInfo,
                &`wil::details::FeatureLogging::StaticHandle::StaticHandle'::`2'::__hInner,
                v49),
        (__int64 *)v50 == &`wil::details::FeatureLogging::StaticHandle::StaticHandle'::`2'::__hInner) )
  {
    v51 = 0;
  }
  else
  {
    v51 = (*(__int64 (**)(void))(v50 + 8))();
  }
  winrt::WindowsInternal::Shell::JumpList::Private::IJumpListImageHelpersStatics::~IJumpListImageHelpersStatics((winrt::WindowsInternal::Shell::JumpList::Private::IJumpListImageHelpersStatics *)&v89);
  if ( v51 )
  {
    *(_QWORD *)v88 = 0;
    v52 = v91;
    UninstallVerb = DataStoreCache::AppResolverTransformer::CreateUninstallVerb(
                      (_DWORD)v91,
                      (_DWORD)a3,
                      0,
                      (_DWORD)v77,
                      (__int64)v88);
    v10 = UninstallVerb;
    if ( UninstallVerb < 0 )
    {
      v54 = 416;
LABEL_66:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v54,
        (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\appresolvertransformer\\lib\\appresolvertransformer.cpp",
        (const char *)(unsigned int)UninstallVerb,
        (int)v73);
      v55 = v88;
LABEL_67:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v55);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v80);
      WindowsDeleteString(v75);
      v75 = 0;
      goto LABEL_24;
    }
    UninstallVerb = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v86 + 104LL))(v86, *(_QWORD *)v88);
    v10 = UninstallVerb;
    if ( UninstallVerb < 0 )
    {
      v54 = 417;
      goto LABEL_66;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v88);
  }
  else
  {
    v52 = v91;
  }
  v95 = 0;
  v56 = (*(__int64 (__fastcall **)(__int64, _QWORD, char *))(*(_QWORD *)v76 + 56LL))(v76, 0, v74);
  if ( v56 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\appresolvertransformer\\lib\\appresolvertransformer.cpp",
      (const char *)(unsigned int)v56,
      (int)v73);
LABEL_74:
    v57 = v85;
LABEL_75:
    v58 = 0;
    goto LABEL_76;
  }
  if ( !v74[0] )
    goto LABEL_74;
  v62 = v76;
  v63 = *(__int64 (__fastcall **)(__int64, HSTRING, char *))(*(_QWORD *)v76 + 64LL);
  v103 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"TabletMode_OpenNewWindow", 0x19u, 0x18u);
  v57 = 1;
  LODWORD(v82) = 1;
  v64 = v63(v62, v103, v74);
  if ( v64 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x1A7,
      (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\appresolvertransformer\\lib\\appresolvertransformer.cpp",
      (const char *)(unsigned int)v64,
      (int)v73);
    goto LABEL_75;
  }
  if ( !v74[0] )
    goto LABEL_75;
  v79[0] = 0;
  if ( (int)wil::wnf_query_nothrow<int>(retaddr, v79, &v95) < 0 || !v79[0] || !v95 )
    goto LABEL_75;
  v58 = 1;
LABEL_76:
  if ( (v57 & 1) != 0 )
    v57 &= ~1u;
  if ( v58 )
  {
    v85 = 0;
    v89 = 0;
    v59 = v92;
    v92 = *(_QWORD *)(v92 + 208);
    v91 = *(DataStoreCache::AppResolverTransformer **)(v59 + 200);
    v83 = 4;
    v82 = v52;
    v73 = (struct WindowsInternal::Shell::UnifiedTile::IVerbEnumerationArgs *)&v96;
    v60 = Microsoft::WRL::Details::MakeAndInitialize<WindowsInternal::Shell::UnifiedTile::Private::TileActivateVerb,WindowsInternal::Shell::UnifiedTile::ITileVerb,WindowsInternal::Shell::UnifiedTile::IUnifiedTile * &,DataStoreCache::AppResolverTransformer *,enum WindowsInternal::Shell::UnifiedTile::ActivationOptions,WindowsInternal::Shell::UnifiedTile::IVerbEnumerationArgs * &,WindowsInternal::Shell::UnifiedTile::Private::IVerbStringHelperStatics *,HSTRING__ *,std::nullptr_t>(
            &v85,
            v97,
            &v82,
            &v83);
    v10 = v60;
    if ( v60 < 0 )
    {
      v61 = 435;
LABEL_81:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v61,
        (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\appresolvertransformer\\lib\\appresolvertransformer.cpp",
        (const char *)(unsigned int)v60,
        (int)&v96);
      v55 = (int *)&v85;
      goto LABEL_67;
    }
    v60 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v86 + 104LL))(v86, v85);
    v10 = v60;
    if ( v60 < 0 )
    {
      v61 = 436;
      goto LABEL_81;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v85);
  }
  else
  {
    v59 = v92;
  }
  v65 = (*(__int64 (__fastcall **)(__int64, _QWORD, char *))(*(_QWORD *)v76 + 56LL))(v76, 0, v74);
  v66 = retaddr;
  if ( v65 >= 0 )
  {
    if ( !v74[0] )
      goto LABEL_101;
    v68 = v76;
    v69 = *(__int64 (__fastcall **)(__int64, HSTRING, char *))(*(_QWORD *)v76 + 64LL);
    v103 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Settings", 9u, 8u);
    LODWORD(v82) = v57 | 2;
    v65 = v69(v68, v103, v74);
    v66 = retaddr;
    if ( v65 >= 0 )
    {
      if ( v74[0] )
        goto LABEL_102;
      goto LABEL_101;
    }
    v67 = 441;
  }
  else
  {
    v67 = 440;
  }
  wil::details::in1diag3::_Log_Hr(
    v66,
    (void *)v67,
    (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\appresolvertransformer\\lib\\appresolvertransformer.cpp",
    (const char *)(unsigned int)v65,
    (int)v73);
LABEL_101:
  v18 = 0;
LABEL_102:
  if ( v18 )
  {
    v92 = 0;
    (*(void (__fastcall **)(struct DataStoreCache::IDataStorePropertyBag *, _GUID **, __int64 *))(*(_QWORD *)v77 + 32LL))(
      v77,
      &DataStoreCache::AppResolverProperties::SettingsCommand,
      &v92);
    if ( v92 )
    {
      if ( *(_WORD *)v92 )
      {
        v82 = 0;
        v89 = 0;
        v91 = *(DataStoreCache::AppResolverTransformer **)(v59 + 208);
        v97[1] = *(_QWORD *)(v59 + 200);
        v83 = 32;
        hstringHeader.Reserved.Reserved1 = v52;
        v73 = (struct WindowsInternal::Shell::UnifiedTile::IVerbEnumerationArgs *)&v96;
        v70 = Microsoft::WRL::Details::MakeAndInitialize<WindowsInternal::Shell::UnifiedTile::Private::TileActivateVerb,WindowsInternal::Shell::UnifiedTile::ITileVerb,WindowsInternal::Shell::UnifiedTile::IUnifiedTile * &,DataStoreCache::AppResolverTransformer *,enum WindowsInternal::Shell::UnifiedTile::ActivationOptions,WindowsInternal::Shell::UnifiedTile::IVerbEnumerationArgs * &,WindowsInternal::Shell::UnifiedTile::Private::IVerbStringHelperStatics *,HSTRING__ *,std::nullptr_t>(
                &v82,
                v97,
                &hstringHeader,
                &v83);
        v10 = v70;
        if ( v70 < 0 )
        {
          v71 = 465;
LABEL_107:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v71,
            (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\appresolvertransformer\\lib\\appresolvertransformer.cpp",
            (const char *)(unsigned int)v70,
            (int)&v96);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v82);
          goto LABEL_32;
        }
        v70 = (*(__int64 (__fastcall **)(__int64, DataStoreCache::AppResolverTransformer *))(*(_QWORD *)v86 + 104LL))(
                v86,
                v82);
        v10 = v70;
        if ( v70 < 0 )
        {
          v71 = 466;
          goto LABEL_107;
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v82);
      }
    }
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v80);
  WindowsDeleteString(v75);
  v75 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v81);
LABEL_112:
  v16 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v86 + 64LL))(v86, v98);
  v10 = v16;
  if ( v16 < 0 )
  {
    v17 = 472;
    goto LABEL_114;
  }
  wil::ActivityBase<DataStoreTransformerLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v104);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v77);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v78);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v76);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v86);
  DataStoreTransformerTelemetry::AppResolverTransformer_GetVerbs::~AppResolverTransformer_GetVerbs((DataStoreTransformerTelemetry::AppResolverTransformer_GetVerbs *)v104);
  return 0;
}

```

## disassembly

```asm
0x18013f6a0  mov     r11, rsp
0x18013f6a3  push    rbx
0x18013f6a4  push    rsi
0x18013f6a5  push    rdi
0x18013f6a6  push    r12
0x18013f6a8  push    r13
0x18013f6aa  push    r14
0x18013f6ac  push    r15
0x18013f6ae  sub     rsp, 2B0h
0x18013f6b5  mov     rax, cs:__security_cookie
0x18013f6bc  xor     rax, rsp
0x18013f6bf  mov     [rsp+2E8h+var_48], rax
0x18013f6c7  mov     [rsp+2E8h+var_1E8], r9
0x18013f6cf  mov     r12, r8
0x18013f6d2  mov     rdi, rdx
0x18013f6d5  mov     [r11-230h], rdx
0x18013f6dc  mov     rsi, rcx
0x18013f6df  mov     [rsp+2E8h+var_218], rcx
0x18013f6e7  mov     [r11-1F8h], rdx
0x18013f6ee  mov     [r11-200h], r8
0x18013f6f5  xor     r13d, r13d
0x18013f6f8  mov     eax, r13d
0x18013f6fb  mov     dword ptr [rsp+2E8h+var_250], eax
0x18013f702  mov     dword ptr [rsp+2E8h+var_268], eax
0x18013f709  mov     [r9], r13
0x18013f70c  lea     rdx, aAppresolvertra_1; "AppResolverTransformer_GetVerbs"
0x18013f713  lea     rcx, [r11-198h]
0x18013f71a  call    ??0?$ActivityBase@VDataStoreTransformerLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<DataStoreTransformerLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DataStoreTransformerLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18013f71f  lea     rax, ??_7AppResolverTransformer_GetVerbs@DataStoreTransformerTelemetry@@6B@; const DataStoreTransformerTelemetry::AppResolverTransformer_GetVerbs::`vftable'
0x18013f726  mov     [rsp+2E8h+var_198], rax
0x18013f72e  lea     rcx, [rsp+2E8h+var_198]; this
0x18013f736  call    ?StartActivity@AppResolverTransformer_GetVerbs@DataStoreTransformerTelemetry@@QEAAXXZ; DataStoreTransformerTelemetry::AppResolverTransformer_GetVerbs::StartActivity(void)
0x18013f73b  nop
0x18013f73c  mov     rcx, [rsp+2E8h]; this
0x18013f744  test    r12, r12
0x18013f747  jz      loc_1801404FB
0x18013f74d  mov     [rsp+2E8h+var_248], r13
0x18013f755  lea     rcx, [rsp+2E8h+var_248]
0x18013f75d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18013f762  lea     rdx, [rsp+2E8h+var_248]
0x18013f76a  call    ??$CreateExternalObjectVector@VTileVerb@UnifiedTile@Shell@WindowsInternal@@V?$AgileVector@PEAVTileVerb@UnifiedTile@Shell@WindowsInternal@@U?$DefaultEqualityPredicate@PEAVTileVerb@UnifiedTile@Shell@WindowsInternal@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAVTileVerb@UnifiedTile@Shell@WindowsInternal@@@6789@$0A@@Internal@Collections@Foundation@Windows@@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVTileVerb@UnifiedTile@Shell@WindowsInternal@@U?$DefaultEqualityPredicate@PEAVTileVerb@UnifiedTile@Shell@WindowsInternal@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAVTileVerb@UnifiedTile@Shell@WindowsInternal@@@6789@$0A@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<WindowsInternal::Shell::UnifiedTile::TileVerb,Windows::Foundation::Collections::Internal::AgileVector<WindowsInternal::Shell::UnifiedTile::TileVerb *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<WindowsInternal::Shell::UnifiedTile::TileVerb *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<WindowsInternal::Shell::UnifiedTile::TileVerb *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<WindowsInternal::Shell::UnifiedTile::TileVerb *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<WindowsInternal::Shell::UnifiedTile::TileVerb *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<WindowsInternal::Shell::UnifiedTile::TileVerb *>,0> * *)
0x18013f76f  mov     ebx, eax
0x18013f771  test    eax, eax
0x18013f773  jns     short loc_18013F796
0x18013f775  mov     rcx, [rsp+2E8h]; this
0x18013f77d  mov     r9d, eax; char *
0x18013f780  lea     r8, aShellcommonShe_148; "shellcommon\\shell\\datastorecache\\tra"...
0x18013f787  mov     edx, 155h; void *
0x18013f78c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013f791  jmp     loc_18014046D
0x18013f796  mov     [rsp+2E8h+var_298], r13
0x18013f79b  mov     rax, [r12]
0x18013f79f  mov     rbx, [rax]
0x18013f7a2  lea     rcx, [rsp+2E8h+var_298]
0x18013f7a7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18013f7ac  lea     r8, [rsp+2E8h+var_298]
0x18013f7b1  lea     rdx, _GUID_3b8c9be7_fc8c_42e2_a6b5_7005aa719c35
0x18013f7b8  mov     rcx, r12
0x18013f7bb  mov     rax, rbx
0x18013f7be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013f7c3  mov     ebx, eax
0x18013f7c5  test    eax, eax
0x18013f7c7  jns     short loc_18013F7EA
0x18013f7c9  mov     rcx, [rsp+2E8h]; this
0x18013f7d1  mov     r9d, eax; char *
0x18013f7d4  lea     r8, aShellcommonShe_148; "shellcommon\\shell\\datastorecache\\tra"...
0x18013f7db  mov     edx, 158h; void *
0x18013f7e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013f7e5  jmp     loc_180140462
0x18013f7ea  mov     [rsp+2E8h+var_288], r13
0x18013f7ef  mov     [rsp+2E8h+var_290], r13
0x18013f7f4  mov     [rsp+2E8h+var_2A8], r13b
0x18013f7f9  mov     rcx, [rsp+2E8h+var_298]
0x18013f7fe  lea     r15, [rsi-30h]
0x18013f802  mov     [rsp+2E8h+var_220], r15
0x18013f80a  mov     rax, [rcx]
0x18013f80d  lea     r8, [rsp+2E8h+var_2A8]
0x18013f812  mov     rdx, [r15+100h]
0x18013f819  mov     rax, [rax+30h]
0x18013f81d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013f822  mov     rcx, [rsp+2E8h]; this
0x18013f82a  test    eax, eax
0x18013f82c  jns     short loc_18013F84A
0x18013f82e  mov     r9d, eax; char *
0x18013f831  lea     rsi, aShellcommonShe_148; "shellcommon\\shell\\datastorecache\\tra"...
0x18013f838  mov     r8, rsi; unsigned int
0x18013f83b  mov     edx, 15Dh; void *
0x18013f840  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18013f845  jmp     loc_18013F9C1
0x18013f84a  cmp     [rsp+2E8h+var_2A8], r13b
0x18013f84f  jz      loc_18013F9BA
0x18013f855  mov     rax, [rdi]
0x18013f858  mov     rbx, [rax+30h]
0x18013f85c  lea     rcx, [rsp+2E8h+var_288]
0x18013f861  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18013f866  lea     rdx, [rsp+2E8h+var_288]
0x18013f86b  mov     rcx, rdi
0x18013f86e  mov     rax, rbx
0x18013f871  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013f876  mov     ebx, eax
0x18013f878  test    eax, eax
0x18013f87a  jns     short loc_18013F88D
0x18013f87c  lea     r8, aShellcommonShe_148; "shellcommon\\shell\\datastorecache\\tra"...
0x18013f883  mov     edx, 15Fh
0x18013f888  jmp     loc_18014043B
0x18013f88d  mov     [rsp+2E8h+var_210], r13d
0x18013f895  mov     rcx, [rsp+2E8h+var_288]
0x18013f89a  mov     rax, [rcx]
0x18013f89d  lea     rdx, [rsp+2E8h+var_210]
0x18013f8a5  mov     rax, [rax+30h]
0x18013f8a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013f8ae  mov     ebx, eax
0x18013f8b0  test    eax, eax
0x18013f8b2  jns     short loc_18013F8C5
0x18013f8b4  lea     r8, aShellcommonShe_148; "shellcommon\\shell\\datastorecache\\tra"...
0x18013f8bb  mov     edx, 162h
0x18013f8c0  jmp     loc_18014043B
0x18013f8c5  mov     r14d, 1
0x18013f8cb  cmp     [rsp+2E8h+var_210], 2
0x18013f8d3  jnz     loc_18013F9AC
0x18013f8d9  mov     [rsp+2E8h+var_2A8], r14b
0x18013f8de  mov     rbx, [rsi+68h]
0x18013f8e2  mov     rax, [rbx]
0x18013f8e5  mov     rdi, [rax+28h]
0x18013f8e9  mov     rdx, [rsp+2E8h+var_288]; struct WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier *
0x18013f8ee  lea     rcx, [rsp+2E8h+string]; this
0x18013f8f6  call    ??0DataItemIdentifier@DataStoreCache@@QEAA@PEAUIUnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@@@Z; DataStoreCache::DataItemIdentifier::DataItemIdentifier(WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier *)
0x18013f8fb  nop
0x18013f8fc  mov     r8, [rax]
0x18013f8ff  lea     rdx, [rsp+2E8h+var_238]
0x18013f907  mov     rcx, rbx
0x18013f90a  mov     rax, rdi
0x18013f90d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013f912  nop
0x18013f913  mov     rdi, [rax]
0x18013f916  mov     rax, [rdi]
0x18013f919  mov     rbx, [rax+30h]
0x18013f91d  lea     rcx, [rsp+2E8h+var_290]
0x18013f922  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIUnifiedTilePrivate@Private@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIUnifiedTilePrivate@Private@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::Private::IUnifiedTilePrivate>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::Private::IUnifiedTilePrivate>>)
0x18013f927  mov     r9, rax
0x18013f92a  lea     r8, _GUID_9dbb8733_cc6a_4eba_92cc_25fc80f0c2cb
0x18013f931  lea     rdx, c_appResolverTransformerId
0x18013f938  mov     rcx, rdi
0x18013f93b  mov     rax, rbx
0x18013f93e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013f943  mov     [rsp+2E8h+var_2A8], al
0x18013f947  mov     rcx, qword ptr [rsp+2E8h+var_238]
0x18013f94f  test    rcx, rcx
0x18013f952  jz      short loc_18013F969
0x18013f954  mov     qword ptr [rsp+2E8h+var_238], r13
0x18013f95c  mov     rax, [rcx]
0x18013f95f  mov     rax, [rax+10h]
0x18013f963  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013f968  nop
0x18013f969  mov     rcx, [rsp+2E8h+string]; string
0x18013f971  call    cs:__imp_WindowsDeleteString
0x18013f977  lea     rsi, aShellcommonShe_148; "shellcommon\\shell\\datastorecache\\tra"...
0x18013f97e  jmp     short loc_18013F9C7
0x18013f980  lea     rcx, [rsp+2E8h+var_290]
0x18013f985  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18013f98a  nop
0x18013f98b  lea     rcx, [rsp+2E8h+var_288]
0x18013f990  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18013f995  nop
0x18013f996  lea     rcx, [rsp+2E8h+var_298]
0x18013f99b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18013f9a0  mov     ebx, dword ptr [rsp+2E8h+var_250]
0x18013f9a7  jmp     loc_18014046D
0x18013f9ac  mov     [rsp+2E8h+var_2A8], r13b
0x18013f9b1  lea     rsi, aShellcommonShe_148; "shellcommon\\shell\\datastorecache\\tra"...
0x18013f9b8  jmp     short loc_18013F9C7
0x18013f9ba  lea     rsi, aShellcommonShe_148; "shellcommon\\shell\\datastorecache\\tra"...
0x18013f9c1  mov     r14d, 1
0x18013f9c7  cmp     [rsp+2E8h+var_2A8], r13b
0x18013f9cc  jz      loc_180140411
0x18013f9d2  cmp     [rsp+2E8h+var_290], r13
0x18013f9d7  jz      loc_180140411
0x18013f9dd  mov     [rsp+2E8h+var_270], r13
0x18013f9e2  lea     rdx, [rsp+2E8h+var_270]
0x18013f9e7  lea     rcx, [rsp+2E8h+var_288]
0x18013f9ec  call    ??$As@UIWin32UnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@@@?$ComPtr@UIUnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIWin32UnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier>::As<WindowsInternal::Shell::UnifiedTile::IWin32UnifiedTileIdentifier>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::IWin32UnifiedTileIdentifier>>)
0x18013f9f1  mov     ebx, eax
0x18013f9f3  test    eax, eax
0x18013f9f5  jns     short loc_18013FA1F
0x18013f9f7  mov     rcx, [rsp+2E8h]; this
0x18013f9ff  mov     r9d, eax; char *
0x18013fa02  mov     r8, rsi; unsigned int
0x18013fa05  mov     edx, 174h; void *
0x18013fa0a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013fa0f  nop
0x18013fa10  lea     rcx, [rsp+2E8h+var_270]
0x18013fa15  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18013fa1a  jmp     loc_18014044C
0x18013fa1f  mov     [rsp+2E8h+var_2A0], r13
0x18013fa24  mov     rdi, [rsp+2E8h+var_270]
0x18013fa29  mov     rax, [rdi]
0x18013fa2c  mov     rbx, [rax+30h]
0x18013fa30  xor     ecx, ecx; string
0x18013fa32  call    cs:__imp_WindowsDeleteString
0x18013fa38  mov     [rsp+2E8h+var_2A0], r13
0x18013fa3d  lea     rdx, [rsp+2E8h+var_2A0]
0x18013fa42  mov     rcx, rdi
0x18013fa45  mov     rax, rbx
0x18013fa48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013fa4d  mov     ebx, eax
0x18013fa4f  test    eax, eax
0x18013fa51  jns     short loc_18013FA7E
0x18013fa53  mov     rcx, [rsp+2E8h]; this
0x18013fa5b  mov     r9d, eax; char *
0x18013fa5e  mov     r8, rsi; unsigned int
0x18013fa61  mov     edx, 177h; void *
0x18013fa66  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013fa6b  nop
0x18013fa6c  mov     rcx, [rsp+2E8h+var_2A0]; string
0x18013fa71  call    cs:__imp_WindowsDeleteString
0x18013fa77  mov     [rsp+2E8h+var_2A0], r13
0x18013fa7c  jmp     short loc_18013FA10
0x18013fa7e  mov     [rsp+2E8h+var_278], r13
0x18013fa83  mov     [rsp+2E8h+var_258], r13
0x18013fa8b  lea     rcx, [rsp+2E8h+var_258]
0x18013fa93  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18013fa98  lea     r8, [rsp+2E8h+var_258]; struct WindowsInternal::Shell::UnifiedTile::Private::ITileVerbProviderDesktopBrokerStatics **
0x18013faa0  xor     edx, edx; bool
0x18013faa2  mov     rcx, r15; this
0x18013faa5  call    ?GetTileVerbProviderDesktopBroker@AppResolverTransformer@DataStoreCache@@AEAAJ_NPEAPEAUITileVerbProviderDesktopBrokerStatics@Private@UnifiedTile@Shell@WindowsInternal@@@Z; DataStoreCache::AppResolverTransformer::GetTileVerbProviderDesktopBroker(bool,WindowsInternal::Shell::UnifiedTile::Private::ITileVerbProviderDesktopBrokerStatics * *)
0x18013faaa  mov     ebx, eax
0x18013faac  test    eax, eax
0x18013faae  jns     short loc_18013FAE3
0x18013fab0  mov     edx, 17Ch; void *
0x18013fab5  mov     r9d, eax; char *
0x18013fab8  mov     r8, rsi; unsigned int
0x18013fabb  mov     rcx, [rsp+2E8h]; this
0x18013fac3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013fac8  nop
0x18013fac9  lea     rcx, [rsp+2E8h+var_258]
0x18013fad1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18013fad6  nop
0x18013fad7  lea     rcx, [rsp+2E8h+var_278]
0x18013fadc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18013fae1  jmp     short loc_18013FA6C
0x18013fae3  mov     rdi, [rsp+2E8h+var_258]
0x18013faeb  mov     rax, [rdi]
0x18013faee  mov     rbx, [rax+30h]
0x18013faf2  lea     rcx, [rsp+2E8h+var_278]
0x18013faf7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18013fafc  lea     r9, [rsp+2E8h+var_278]
0x18013fb01  mov     r8, r12
0x18013fb04  mov     rdx, [rsp+2E8h+var_2A0]
0x18013fb09  mov     rcx, rdi
0x18013fb0c  mov     rax, rbx
0x18013fb0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013fb14  mov     ebx, eax
0x18013fb16  test    eax, eax
0x18013fb18  jns     loc_18013FBA4
0x18013fb1e  mov     ecx, eax; int
0x18013fb20  call    ?IsServerFailedError@@YA_NJ@Z; IsServerFailedError(long)
0x18013fb25  test    al, al
0x18013fb27  jnz     short loc_18013FB33
0x18013fb29  mov     r9d, ecx
0x18013fb2c  mov     edx, 183h
0x18013fb31  jmp     short loc_18013FAB8
0x18013fb33  lea     rcx, [rsp+2E8h+var_258]
0x18013fb3b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18013fb40  lea     r8, [rsp+2E8h+var_258]; struct WindowsInternal::Shell::UnifiedTile::Private::ITileVerbProviderDesktopBrokerStatics **
0x18013fb48  mov     dl, r14b; bool
0x18013fb4b  mov     rcx, r15; this
0x18013fb4e  call    ?GetTileVerbProviderDesktopBroker@AppResolverTransformer@DataStoreCache@@AEAAJ_NPEAPEAUITileVerbProviderDesktopBrokerStatics@Private@UnifiedTile@Shell@WindowsInternal@@@Z; DataStoreCache::AppResolverTransformer::GetTileVerbProviderDesktopBroker(bool,WindowsInternal::Shell::UnifiedTile::Private::ITileVerbProviderDesktopBrokerStatics * *)
0x18013fb53  mov     ebx, eax
0x18013fb55  test    eax, eax
0x18013fb57  jns     short loc_18013FB63
0x18013fb59  mov     edx, 184h
0x18013fb5e  jmp     loc_18013FAB5
0x18013fb63  mov     rdi, [rsp+2E8h+var_258]
0x18013fb6b  mov     rax, [rdi]
0x18013fb6e  mov     rbx, [rax+30h]
0x18013fb72  lea     rcx, [rsp+2E8h+var_278]
0x18013fb77  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18013fb7c  lea     r9, [rsp+2E8h+var_278]
0x18013fb81  mov     r8, r12
0x18013fb84  mov     rdx, [rsp+2E8h+var_2A0]
0x18013fb89  mov     rcx, rdi
0x18013fb8c  mov     rax, rbx
0x18013fb8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013fb94  mov     ebx, eax
0x18013fb96  test    eax, eax
0x18013fb98  jns     short loc_18013FBA4
0x18013fb9a  mov     edx, 185h
0x18013fb9f  jmp     loc_18013FAB5
0x18013fba4  lea     rcx, [rsp+2E8h+var_258]
0x18013fbac  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18013fbb1  mov     dword ptr [rsp+2E8h+var_20C], r13d
0x18013fbb9  mov     dil, r13b
0x18013fbbc  mov     dword ptr [rsp+2E8h+var_268], edi
0x18013fbc3  lea     r8, [rsp+2E8h+var_20C]
0x18013fbcb  mov     rdx, [rsp+2E8h+var_278]
0x18013fbd0  lea     rcx, [rsp+2E8h+var_1E0]
0x18013fbd8  call    ??$GetRangeNoThrow@PEAVUnifiedTileVerbProvider@Private@UnifiedTile@Shell@WindowsInternal@@@wil@@YA?AV?$vector_range_nothrow@U?$IVectorView@PEAVUnifiedTileVerbProvider@Private@UnifiedTile@Shell@WindowsInternal@@@Collections@Foundation@Windows@@@0@PEAU?$IVectorView@PEAVUnifiedTileVerbProvider@Private@UnifiedTile@Shell@WindowsInternal@@@Collections@Foundation@Windows@@PEAJ@Z; wil::GetRangeNoThrow<WindowsInternal::Shell::UnifiedTile::Private::UnifiedTileVerbProvider *>(Windows::Foundation::Collections::IVectorView<WindowsInternal::Shell::UnifiedTile::Private::UnifiedTileVerbProvider *> *,long *)
0x18013fbdd  nop
0x18013fbde  lea     rdx, [rsp+2E8h+hstringHeader]
0x18013fbe6  lea     rcx, [rsp+2E8h+var_1E0]
  ... truncated ...
```
