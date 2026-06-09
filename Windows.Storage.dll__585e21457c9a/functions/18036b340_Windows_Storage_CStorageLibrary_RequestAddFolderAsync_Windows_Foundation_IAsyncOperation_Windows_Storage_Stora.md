# Windows::Storage::CStorageLibrary::RequestAddFolderAsync(Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFolder *> * *)

- ea: `0x18036b340`
- end: `0x18036ba82`
- name: `?RequestAddFolderAsync@CStorageLibrary@Storage@Windows@@UEAAJPEAPEAU?$IAsyncOperation@PEAVStorageFolder@Storage@Windows@@@Foundation@3@@Z`
- size: `1858`
- prototype: ``
- caller_count: `0`
- callee_count: `22`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000d6cc`
- `0x18002a63c`
- `0x18002aa58`
- `0x1800308bc`
- `0x1800361c8`
- `0x180036710`
- `0x1800432f0`
- `0x1800d13a0`
- `0x1801e5f48`
- `0x1801f0248`
- `0x18036b2b0`
- `0x18036b340`
- `0x18036ba88`
- `0x1803745e8`
- `0x1803a4cb0`
- `0x1803a518c`
- `0x18049fd20`
- `0x1804a1460`
- `0x1804a22f8`
- `0x1804a8b90`
- `0x1804a9658`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18036b5cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18036b658`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18036b6db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18036b701`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18036b78d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18036b7b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18036b8bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18036b8e5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18036b95c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18036b982`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18036b5cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18036b658`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18036b6db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18036b701`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18036b78d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18036b7b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18036b8bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18036b8e5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18036b95c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18036b982`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x18036b44d`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x18036b4d5`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x18036b44d`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x18036b4d5`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall Windows::Storage::CStorageLibrary::RequestAddFolderAsync(__int64 a1, HWND *a2)
{
  HWND *v2; // r15
  __int64 (__fastcall ***v4)(_QWORD, GUID *, __int64 *); // rdi
  __int64 (__fastcall *v5)(_QWORD, GUID *, __int64 *); // rbx
  int v6; // eax
  int CoreWindowHandleForCallingThread; // ebx
  int AgileReference; // eax
  HWND *v9; // rdx
  __int64 v10; // rdx
  int v11; // eax
  __int64 v12; // rbx
  int v13; // eax
  int v14; // edi
  CallerIdentity *v15; // rax
  unsigned __int16 **v16; // rdx
  int CallingProcessPackageFullName; // eax
  __int64 v18; // rdi
  int v19; // eax
  int v20; // esi
  CallerIdentity *v21; // rax
  unsigned __int16 **v22; // rdx
  int CallingProcessAppId; // eax
  __int64 v24; // rsi
  int v25; // eax
  int v26; // r14d
  __int64 v27; // r14
  void *v28; // rax
  __int64 v29; // r8
  __int64 v31; // rdx
  __int64 v32; // rax
  __int64 v33; // r8
  int v34; // [rsp+20h] [rbp-E0h]
  int v35; // [rsp+20h] [rbp-E0h]
  LPVOID pv; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID v37; // [rsp+48h] [rbp-B8h] BYREF
  int v38; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v39; // [rsp+54h] [rbp-ACh]
  void *v40; // [rsp+60h] [rbp-A0h]
  _BYTE v41[384]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v42; // [rsp+1F0h] [rbp+F0h] BYREF
  __int64 v43; // [rsp+1F8h] [rbp+F8h] BYREF
  __int64 v44; // [rsp+200h] [rbp+100h] BYREF
  __int64 v45; // [rsp+208h] [rbp+108h] BYREF
  int v46[2]; // [rsp+210h] [rbp+110h] BYREF
  __int64 v47; // [rsp+218h] [rbp+118h] BYREF
  _QWORD v48[2]; // [rsp+220h] [rbp+120h] BYREF
  _QWORD v49[42]; // [rsp+230h] [rbp+130h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3B8h] [rbp+2B8h]

  v2 = a2;
  *a2 = 0;
  if ( !*(_QWORD *)(a1 + 200) )
  {
    v42 = 0;
    CoreWindowHandleForCallingThread = CallerIdentity::GetCoreWindowHandleForCallingThread((CallerIdentity *)&v42, a2);
    if ( CoreWindowHandleForCallingThread >= 0 )
    {
      *(_QWORD *)v46 = v42;
      v38 = 1;
      v39 = 128;
      v32 = Windows::Internal::MakeOpLambda_0_CStorageItemResult_Windows::Storage::IStorageFolder___lambda_d57dea6503c7e5ac40186487fd7806a6___(v46);
      CoreWindowHandleForCallingThread = Windows::Internal::MakeAsyncOperationHelper<CStorageItemResult<Windows::Storage::IStorageFolder>,Windows::Storage::StorageFolder *,Windows::Internal::ComTaskPoolHandler>(
                                           &v38,
                                           v2,
                                           v33,
                                           v32);
      if ( CoreWindowHandleForCallingThread >= 0 )
        return 0;
      v31 = 335;
    }
    else
    {
      v31 = 326;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v31,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\cstoragelibrary.cpp",
      (const char *)(unsigned int)CoreWindowHandleForCallingThread,
      v34);
    return (unsigned int)CoreWindowHandleForCallingThread;
  }
  LOBYTE(a2) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_StorageLibraryFolderSuggestionsUX>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_StorageLibraryFolderSuggestionsUX>::GetImpl'::`2'::impl,
    a2);
  wil::ActivityBase<Shell32Logging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Shell32Logging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v49);
  v49[0] = &Shell32LoggingTelemetry::StorageLibrary_RequestAddFolderAsync::`vftable';
  Shell32LoggingTelemetry::StorageLibrary_RequestAddFolderAsync::StartActivity((Shell32LoggingTelemetry::StorageLibrary_RequestAddFolderAsync *)v49);
  v45 = 0;
  v4 = *(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))(a1 + 200);
  v5 = **v4;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
  v6 = v5(v4, &GUID_6362d2dc_cb7e_4c61_a17f_c962790c307e, &v45);
  CoreWindowHandleForCallingThread = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8D,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\cstoragelibrary.cpp",
      (const char *)(unsigned int)v6,
      v34);
LABEL_66:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
    Shell32LoggingTelemetry::StorageLibrary_RequestAddFolderAsync::~StorageLibrary_RequestAddFolderAsync((Shell32LoggingTelemetry::StorageLibrary_RequestAddFolderAsync *)v49);
    return (unsigned int)CoreWindowHandleForCallingThread;
  }
  v43 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
  AgileReference = RoGetAgileReference(0, &GUID_6362d2dc_cb7e_4c61_a17f_c962790c307e, v45, &v43);
  CoreWindowHandleForCallingThread = AgileReference;
  if ( AgileReference < 0 )
  {
    v10 = 144;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\cstoragelibrary.cpp",
      (const char *)(unsigned int)AgileReference,
      v34);
LABEL_7:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
    goto LABEL_66;
  }
  v42 = 0;
  AgileReference = CallerIdentity::GetCoreWindowHandleForCallingThread((CallerIdentity *)&v42, v9);
  CoreWindowHandleForCallingThread = AgileReference;
  if ( AgileReference < 0 )
  {
    v10 = 147;
    goto LABEL_6;
  }
  v44 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
  v11 = RoGetAgileReference(0, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, *(_QWORD *)(a1 + 120), &v44);
  CoreWindowHandleForCallingThread = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x96,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\cstoragelibrary.cpp",
      (const char *)(unsigned int)v11,
      v34);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
    goto LABEL_7;
  }
  CreateRefCountedObj<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>,>(v46);
  v12 = *(_QWORD *)v46;
  v13 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Initialize(
          *(_QWORD *)v46 + 8LL,
          a1 + 88);
  v14 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x99,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\cstoragelibrary.cpp",
      (const char *)(unsigned int)v13,
      v34);
    if ( v12 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
LABEL_15:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
    CoreWindowHandleForCallingThread = v14;
    goto LABEL_66;
  }
  pv = 0;
  v15 = (CallerIdentity *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&pv);
  CallingProcessPackageFullName = CallerIdentity::GetCallingProcessPackageFullName(v15, v16);
  v14 = CallingProcessPackageFullName;
  if ( CallingProcessPackageFullName < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9C,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\cstoragelibrary.cpp",
      (const char *)(unsigned int)CallingProcessPackageFullName,
      v34);
    if ( pv )
      CoTaskMemFree(pv);
    if ( v12 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    goto LABEL_15;
  }
  CreateRefCountedObj<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>,>(v48);
  v18 = v48[0];
  v19 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
          v48[0] + 8LL,
          pv,
          -1);
  v20 = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9E,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\cstoragelibrary.cpp",
      (const char *)(unsigned int)v19,
      v34);
    if ( v18 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    if ( pv )
      CoTaskMemFree(pv);
    if ( v12 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
LABEL_29:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
    CoreWindowHandleForCallingThread = v20;
    goto LABEL_66;
  }
  v37 = 0;
  v21 = (CallerIdentity *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&v37);
  CallingProcessAppId = CallerIdentity::GetCallingProcessAppId(v21, v22);
  v20 = CallingProcessAppId;
  if ( CallingProcessAppId < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA1,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\cstoragelibrary.cpp",
      (const char *)(unsigned int)CallingProcessAppId,
      v34);
    if ( v37 )
      CoTaskMemFree(v37);
    if ( v18 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    if ( pv )
      CoTaskMemFree(pv);
    if ( v12 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    goto LABEL_29;
  }
  CreateRefCountedObj<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>,>(&v47);
  v24 = v47;
  v25 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
          v47 + 8,
          v37,
          -1);
  v26 = v25;
  if ( v25 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA3,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\cstoragelibrary.cpp",
      (const char *)(unsigned int)v25,
      v34);
    if ( v24 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    if ( v37 )
      CoTaskMemFree(v37);
    if ( v18 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    if ( pv )
      CoTaskMemFree(pv);
    if ( v12 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
LABEL_65:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
    CoreWindowHandleForCallingThread = v26;
    goto LABEL_66;
  }
  v27 = lambda_51384603797346d8cde30443967c5674_::_lambda_51384603797346d8cde30443967c5674_(
          (unsigned int)v41,
          (unsigned int)&v43,
          (unsigned int)&v44,
          (unsigned int)&v42,
          (__int64)v46,
          (__int64)v48,
          (__int64)v49,
          (__int64)&v47);
  v38 = 1;
  v39 = 129;
  v28 = operator new(0x198u, (const struct std::nothrow_t *)&std::nothrow);
  v40 = v28;
  if ( v28 )
    v28 = (void *)Windows::Internal::COperationLambdaVar_1__lambda_51384603797346d8cde30443967c5674__CStorageItemResult_Windows::Storage::IStorageFolder___::COperationLambdaVar_1__lambda_51384603797346d8cde30443967c5674__CStorageItemResult_Windows::Storage::IStorageFolder_____lambda_51384603797346d8cde30443967c5674___(
                    v28,
                    v27);
  v26 = Windows::Internal::MakeAsyncOperationHelper<CStorageItemResult<Windows::Storage::IStorageFolder>,Windows::Storage::StorageFolder *,Windows::Internal::ComTaskPoolHandler>(
          &v38,
          v2,
          v29,
          v28);
  lambda_51384603797346d8cde30443967c5674_::__lambda_51384603797346d8cde30443967c5674_(v41);
  if ( v26 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x13C,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\cstoragelibrary.cpp",
      (const char *)(unsigned int)v26,
      v35);
    if ( v24 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    if ( v37 )
      CoTaskMemFree(v37);
    if ( v18 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    if ( pv )
      CoTaskMemFree(pv);
    if ( v12 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    goto LABEL_65;
  }
  if ( v24 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  if ( v37 )
    CoTaskMemFree(v37);
  if ( v18 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  if ( pv )
    CoTaskMemFree(pv);
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
  Shell32LoggingTelemetry::StorageLibrary_RequestAddFolderAsync::~StorageLibrary_RequestAddFolderAsync((Shell32LoggingTelemetry::StorageLibrary_RequestAddFolderAsync *)v49);
  return 0;
}

```

## disassembly

```asm
0x18036b340  mov     [rsp-8+arg_10], rbx
0x18036b345  push    rbp
0x18036b346  push    rsi
0x18036b347  push    rdi
0x18036b348  push    r14
0x18036b34a  push    r15
0x18036b34c  lea     rbp, [rsp-290h]
0x18036b354  sub     rsp, 390h
0x18036b35b  mov     rax, cs:__security_cookie
0x18036b362  xor     rax, rsp
0x18036b365  mov     [rbp+2B0h+var_30], rax
0x18036b36c  mov     r15, rdx
0x18036b36f  mov     rsi, rcx
0x18036b372  mov     qword ptr [rdx], 0
0x18036b379  cmp     qword ptr [rcx+0C8h], 0
0x18036b381  jz      loc_18036B9F9
0x18036b387  mov     dl, 1
0x18036b389  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_StorageLibraryFolderSuggestionsUX@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_StorageLibraryFolderSuggestionsUX@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_StorageLibraryFolderSuggestionsUX> `wil::Feature<__WilFeatureTraits_Feature_StorageLibraryFolderSuggestionsUX>::GetImpl(void)'::`2'::impl
0x18036b390  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_StorageLibraryFolderSuggestionsUX@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_StorageLibraryFolderSuggestionsUX>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18036b395  lea     rcx, [rbp+2B0h+var_180]; struct wil::details::IFailureCallback *
0x18036b39c  call    ??0?$ActivityBase@VShell32Logging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<Shell32Logging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Shell32Logging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18036b3a1  lea     rax, ??_7StorageLibrary_RequestAddFolderAsync@Shell32LoggingTelemetry@@6B@; const Shell32LoggingTelemetry::StorageLibrary_RequestAddFolderAsync::`vftable'
0x18036b3a8  mov     [rbp+2B0h+var_180], rax
0x18036b3af  lea     rcx, [rbp+2B0h+var_180]; this
0x18036b3b6  call    ?StartActivity@StorageLibrary_RequestAddFolderAsync@Shell32LoggingTelemetry@@QEAAXXZ; Shell32LoggingTelemetry::StorageLibrary_RequestAddFolderAsync::StartActivity(void)
0x18036b3bb  nop
0x18036b3bc  mov     [rbp+2B0h+var_1A8], 0
0x18036b3c7  mov     rdi, [rsi+0C8h]
0x18036b3ce  mov     rax, [rdi]
0x18036b3d1  mov     rbx, [rax]
0x18036b3d4  lea     rcx, [rbp+2B0h+var_1A8]
0x18036b3db  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18036b3e0  lea     r8, [rbp+2B0h+var_1A8]
0x18036b3e7  lea     rdx, _GUID_6362d2dc_cb7e_4c61_a17f_c962790c307e
0x18036b3ee  mov     rcx, rdi
0x18036b3f1  mov     rax, rbx
0x18036b3f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18036b3f9  mov     ebx, eax
0x18036b3fb  test    eax, eax
0x18036b3fd  jns     short loc_18036B41F
0x18036b3ff  mov     rcx, [rbp+2B8h]; this
0x18036b406  mov     r9d, eax; char *
0x18036b409  lea     r8, aOnecoreuapShel_172; "onecoreuap\\shell\\windows.storage\\cst"...
0x18036b410  mov     edx, 8Dh; void *
0x18036b415  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18036b41a  jmp     loc_18036B91D
0x18036b41f  mov     [rbp+2B0h+var_1B8], 0
0x18036b42a  lea     rcx, [rbp+2B0h+var_1B8]
0x18036b431  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18036b436  lea     r9, [rbp+2B0h+var_1B8]
0x18036b43d  mov     r8, [rbp+2B0h+var_1A8]
0x18036b444  lea     rdx, _GUID_6362d2dc_cb7e_4c61_a17f_c962790c307e
0x18036b44b  xor     ecx, ecx
0x18036b44d  call    cs:__imp_RoGetAgileReference
0x18036b453  mov     ebx, eax
0x18036b455  test    eax, eax
0x18036b457  jns     short loc_18036B486
0x18036b459  mov     edx, 90h; void *
0x18036b45e  lea     r8, aOnecoreuapShel_172; "onecoreuap\\shell\\windows.storage\\cst"...
0x18036b465  mov     r9d, eax; char *
0x18036b468  mov     rcx, [rbp+2B8h]; this
0x18036b46f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18036b474  nop
0x18036b475  lea     rcx, [rbp+2B0h+var_1B8]
0x18036b47c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18036b481  jmp     loc_18036B91D
0x18036b486  mov     [rbp+2B0h+var_1C0], 0
0x18036b491  lea     rcx, [rbp+2B0h+var_1C0]; this
0x18036b498  call    ?GetCoreWindowHandleForCallingThread@CallerIdentity@@YAJPEAPEAUHWND__@@@Z; CallerIdentity::GetCoreWindowHandleForCallingThread(HWND__ * *)
0x18036b49d  mov     ebx, eax
0x18036b49f  test    eax, eax
0x18036b4a1  jns     short loc_18036B4AA
0x18036b4a3  mov     edx, 93h
0x18036b4a8  jmp     short loc_18036B45E
0x18036b4aa  mov     [rbp+2B0h+var_1B0], 0
0x18036b4b5  lea     rcx, [rbp+2B0h+var_1B0]
0x18036b4bc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18036b4c1  lea     r9, [rbp+2B0h+var_1B0]
0x18036b4c8  mov     r8, [rsi+78h]
0x18036b4cc  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe
0x18036b4d3  xor     ecx, ecx
0x18036b4d5  call    cs:__imp_RoGetAgileReference
0x18036b4db  mov     ebx, eax
0x18036b4dd  test    eax, eax
0x18036b4df  jns     short loc_18036B50E
0x18036b4e1  mov     rcx, [rbp+2B8h]; this
0x18036b4e8  mov     r9d, eax; char *
0x18036b4eb  lea     r8, aOnecoreuapShel_172; "onecoreuap\\shell\\windows.storage\\cst"...
0x18036b4f2  mov     edx, 96h; void *
0x18036b4f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18036b4fc  nop
0x18036b4fd  lea     rcx, [rbp+2B0h+var_1B0]
0x18036b504  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18036b509  jmp     loc_18036B475
0x18036b50e  lea     rcx, [rbp+2B0h+var_1A0]
0x18036b515  call    ??$CreateRefCountedObj@V?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@$$V@@YA?AV?$ComPtr@V?$CRefCountedObject@V?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@@@WRL@Microsoft@@XZ; CreateRefCountedObj<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>,>(void)
0x18036b51a  nop
0x18036b51b  lea     rdx, [rsi+58h]
0x18036b51f  mov     rbx, qword ptr [rbp+2B0h+var_1A0]
0x18036b526  lea     rcx, [rbx+8]
0x18036b52a  call    ?Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJAEBV123@@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Initialize(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> const &)
0x18036b52f  mov     edi, eax
0x18036b531  test    eax, eax
0x18036b533  jns     short loc_18036B586
0x18036b535  mov     rcx, [rbp+2B8h]; this
0x18036b53c  mov     r9d, eax; char *
0x18036b53f  lea     r8, aOnecoreuapShel_172; "onecoreuap\\shell\\windows.storage\\cst"...
0x18036b546  mov     edx, 99h; void *
0x18036b54b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18036b550  nop
0x18036b551  test    rbx, rbx
0x18036b554  jz      short loc_18036B566
0x18036b556  mov     rax, [rbx]
0x18036b559  mov     rcx, rbx
0x18036b55c  mov     rax, [rax+10h]
0x18036b560  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18036b565  nop
0x18036b566  lea     rcx, [rbp+2B0h+var_1B0]
0x18036b56d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18036b572  nop
0x18036b573  lea     rcx, [rbp+2B0h+var_1B8]
0x18036b57a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18036b57f  mov     ebx, edi
0x18036b581  jmp     loc_18036B91D
0x18036b586  mov     [rsp+3B0h+pv], 0
0x18036b58f  lea     rcx, [rsp+3B0h+pv]
0x18036b594  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x18036b599  mov     rcx, rax; this
0x18036b59c  call    ?GetCallingProcessPackageFullName@CallerIdentity@@YAJPEAPEAG@Z; CallerIdentity::GetCallingProcessPackageFullName(ushort * *)
0x18036b5a1  mov     edi, eax
0x18036b5a3  test    eax, eax
0x18036b5a5  jns     short loc_18036B5EE
0x18036b5a7  mov     rcx, [rbp+2B8h]; this
0x18036b5ae  mov     r9d, eax; char *
0x18036b5b1  lea     r8, aOnecoreuapShel_172; "onecoreuap\\shell\\windows.storage\\cst"...
0x18036b5b8  mov     edx, 9Ch; void *
0x18036b5bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18036b5c2  nop
0x18036b5c3  mov     rcx, [rsp+3B0h+pv]; pv
0x18036b5c8  test    rcx, rcx
0x18036b5cb  jz      short loc_18036B5D4
0x18036b5cd  call    cs:__imp_CoTaskMemFree
0x18036b5d3  nop
0x18036b5d4  test    rbx, rbx
0x18036b5d7  jz      short loc_18036B5E9
0x18036b5d9  mov     rax, [rbx]
0x18036b5dc  mov     rcx, rbx
0x18036b5df  mov     rax, [rax+10h]
0x18036b5e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18036b5e8  nop
0x18036b5e9  jmp     loc_18036B566
0x18036b5ee  lea     rcx, [rbp+2B0h+var_190]
0x18036b5f5  call    ??$CreateRefCountedObj@V?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@$$V@@YA?AV?$ComPtr@V?$CRefCountedObject@V?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@@@WRL@Microsoft@@XZ; CreateRefCountedObj<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>,>(void)
0x18036b5fa  nop
0x18036b5fb  mov     rdi, [rbp+2B0h+var_190]
0x18036b602  lea     rcx, [rdi+8]
0x18036b606  or      r14, 0FFFFFFFFFFFFFFFFh
0x18036b60a  mov     r8, r14
0x18036b60d  mov     rdx, [rsp+3B0h+pv]
0x18036b612  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18036b617  mov     esi, eax
0x18036b619  test    eax, eax
0x18036b61b  jns     short loc_18036B694
0x18036b61d  mov     rcx, [rbp+2B8h]; this
0x18036b624  mov     r9d, eax; char *
0x18036b627  lea     r8, aOnecoreuapShel_172; "onecoreuap\\shell\\windows.storage\\cst"...
0x18036b62e  mov     edx, 9Eh; void *
0x18036b633  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18036b638  nop
0x18036b639  test    rdi, rdi
0x18036b63c  jz      short loc_18036B64E
0x18036b63e  mov     rax, [rdi]
0x18036b641  mov     rcx, rdi
0x18036b644  mov     rax, [rax+10h]
0x18036b648  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18036b64d  nop
0x18036b64e  mov     rcx, [rsp+3B0h+pv]; pv
0x18036b653  test    rcx, rcx
0x18036b656  jz      short loc_18036B65F
0x18036b658  call    cs:__imp_CoTaskMemFree
0x18036b65e  nop
0x18036b65f  test    rbx, rbx
0x18036b662  jz      short loc_18036B674
0x18036b664  mov     rax, [rbx]
0x18036b667  mov     rcx, rbx
0x18036b66a  mov     rax, [rax+10h]
0x18036b66e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18036b673  nop
0x18036b674  lea     rcx, [rbp+2B0h+var_1B0]
0x18036b67b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18036b680  nop
0x18036b681  lea     rcx, [rbp+2B0h+var_1B8]
0x18036b688  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18036b68d  mov     ebx, esi
0x18036b68f  jmp     loc_18036B91D
0x18036b694  mov     [rsp+3B0h+var_368], 0
0x18036b69d  lea     rcx, [rsp+3B0h+var_368]
0x18036b6a2  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x18036b6a7  mov     rcx, rax; this
0x18036b6aa  call    ?GetCallingProcessAppId@CallerIdentity@@YAJPEAPEAG@Z; CallerIdentity::GetCallingProcessAppId(ushort * *)
0x18036b6af  mov     esi, eax
0x18036b6b1  test    eax, eax
0x18036b6b3  jns     short loc_18036B722
0x18036b6b5  mov     rcx, [rbp+2B8h]; this
0x18036b6bc  mov     r9d, eax; char *
0x18036b6bf  lea     r8, aOnecoreuapShel_172; "onecoreuap\\shell\\windows.storage\\cst"...
0x18036b6c6  mov     edx, 0A1h; void *
0x18036b6cb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18036b6d0  nop
0x18036b6d1  mov     rcx, [rsp+3B0h+var_368]; pv
0x18036b6d6  test    rcx, rcx
0x18036b6d9  jz      short loc_18036B6E2
0x18036b6db  call    cs:__imp_CoTaskMemFree
0x18036b6e1  nop
0x18036b6e2  test    rdi, rdi
0x18036b6e5  jz      short loc_18036B6F7
0x18036b6e7  mov     rax, [rdi]
0x18036b6ea  mov     rcx, rdi
0x18036b6ed  mov     rax, [rax+10h]
0x18036b6f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18036b6f6  nop
0x18036b6f7  mov     rcx, [rsp+3B0h+pv]; pv
0x18036b6fc  test    rcx, rcx
0x18036b6ff  jz      short loc_18036B708
0x18036b701  call    cs:__imp_CoTaskMemFree
0x18036b707  nop
0x18036b708  test    rbx, rbx
0x18036b70b  jz      short loc_18036B71D
0x18036b70d  mov     rax, [rbx]
0x18036b710  mov     rcx, rbx
0x18036b713  mov     rax, [rax+10h]
0x18036b717  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18036b71c  nop
0x18036b71d  jmp     loc_18036B674
0x18036b722  lea     rcx, [rbp+2B0h+var_198]
0x18036b729  call    ??$CreateRefCountedObj@V?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@$$V@@YA?AV?$ComPtr@V?$CRefCountedObject@V?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@@@WRL@Microsoft@@XZ; CreateRefCountedObj<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>,>(void)
0x18036b72e  nop
0x18036b72f  mov     rsi, [rbp+2B0h+var_198]
0x18036b736  lea     rcx, [rsi+8]
0x18036b73a  mov     r8, r14
0x18036b73d  mov     rdx, [rsp+3B0h+var_368]
0x18036b742  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18036b747  mov     r14d, eax
0x18036b74a  test    eax, eax
0x18036b74c  jns     loc_18036B7D4
0x18036b752  mov     rcx, [rbp+2B8h]; this
0x18036b759  mov     r9d, eax; char *
0x18036b75c  lea     r8, aOnecoreuapShel_172; "onecoreuap\\shell\\windows.storage\\cst"...
0x18036b763  mov     edx, 0A3h; void *
0x18036b768  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18036b76d  nop
0x18036b76e  test    rsi, rsi
0x18036b771  jz      short loc_18036B783
0x18036b773  mov     rax, [rsi]
0x18036b776  mov     rcx, rsi
0x18036b779  mov     rax, [rax+10h]
0x18036b77d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18036b782  nop
0x18036b783  mov     rcx, [rsp+3B0h+var_368]; pv
0x18036b788  test    rcx, rcx
0x18036b78b  jz      short loc_18036B794
0x18036b78d  call    cs:__imp_CoTaskMemFree
0x18036b793  nop
0x18036b794  test    rdi, rdi
0x18036b797  jz      short loc_18036B7A9
0x18036b799  mov     rax, [rdi]
0x18036b79c  mov     rcx, rdi
0x18036b79f  mov     rax, [rax+10h]
0x18036b7a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18036b7a8  nop
0x18036b7a9  mov     rcx, [rsp+3B0h+pv]; pv
0x18036b7ae  test    rcx, rcx
0x18036b7b1  jz      short loc_18036B7BA
0x18036b7b3  call    cs:__imp_CoTaskMemFree
0x18036b7b9  nop
0x18036b7ba  test    rbx, rbx
0x18036b7bd  jz      short loc_18036B7CF
0x18036b7bf  mov     rax, [rbx]
0x18036b7c2  mov     rcx, rbx
0x18036b7c5  mov     rax, [rax+10h]
0x18036b7c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18036b7ce  nop
0x18036b7cf  jmp     loc_18036B901
0x18036b7d4  lea     rax, [rbp+2B0h+var_198]
0x18036b7db  mov     [rsp+3B0h+var_378], rax
0x18036b7e0  lea     rax, [rbp+2B0h+var_180]
0x18036b7e7  mov     [rsp+3B0h+var_380], rax
0x18036b7ec  lea     rax, [rbp+2B0h+var_190]
0x18036b7f3  mov     [rsp+3B0h+var_388], rax
0x18036b7f8  lea     rax, [rbp+2B0h+var_1A0]
0x18036b7ff  mov     qword ptr [rsp+3B0h+var_390], rax; int
0x18036b804  lea     r9, [rbp+2B0h+var_1C0]
0x18036b80b  lea     r8, [rbp+2B0h+var_1B0]
0x18036b812  lea     rdx, [rbp+2B0h+var_1B8]
0x18036b819  lea     rcx, [rsp+3B0h+var_340]
0x18036b81e  call    _lambda_51384603797346d8cde30443967c5674____lambda_51384603797346d8cde30443967c5674_
0x18036b823  mov     r14, rax
0x18036b826  mov     [rsp+3B0h+var_360], 1
0x18036b82e  mov     [rsp+3B0h+var_35C], 81h
0x18036b837  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
  ... truncated ...
```
