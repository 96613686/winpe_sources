# StoreEventListenerImpl::OnCompleted(IUnknown *,IUnknown *)

- ea: `0x1801749d0`
- end: `0x180174ede`
- name: `?OnCompleted@StoreEventListenerImpl@@UEAAJPEAUIUnknown@@0@Z`
- size: `1294`
- prototype: `__int64 __fastcall(StoreEventListenerImpl *__hidden this, struct IUnknown *, struct IUnknown *)`
- caller_count: `0`
- callee_count: `26`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18000befc`
- `0x18000ce94`
- `0x18001ac50`
- `0x18001aca4`
- `0x18002dde0`
- `0x18008d550`
- `0x1800b4fd0`
- `0x1800b6ec0`
- `0x1800cd444`
- `0x18010d0f0`
- `0x18015a108`
- `0x18015a52c`
- `0x18015a718`
- `0x1801740c4`
- `0x1801749d0`
- `0x180174ee4`
- `0x180175534`
- `0x1801756f4`
- `0x180175780`
- `0x180195820`
- `0x1801f7af8`
- `0x180201e50`
- `0x18025acbc`
- `0x18025af7c`
- `0x18025eb34`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180174e4c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180174e4c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180174b0d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180174b50`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180174b7f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180174bc2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180174bd2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180174e90`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180174ea0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180174b0d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180174b50`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180174b7f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180174bc2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180174bd2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180174e90`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180174ea0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180174c26`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180174c5c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180174c9b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180174cab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180174df4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180174e04`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180174c26`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180174c5c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180174c9b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180174cab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180174df4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180174e04`

## string_xrefs

- `0x180174a2b`: `shellcommon\shell\tiles\curatedtilecollections\storeeventlistener\lib\storeeventlistenerimpl.cpp`
- `0x180174a7f`: `shellcommon\shell\tiles\curatedtilecollections\storeeventlistener\lib\storeeventlistenerimpl.cpp`
- `0x180174ac9`: `shellcommon\shell\tiles\curatedtilecollections\storeeventlistener\lib\storeeventlistenerimpl.cpp`
- `0x180174b39`: `shellcommon\shell\tiles\curatedtilecollections\storeeventlistener\lib\storeeventlistenerimpl.cpp`
- `0x180174bab`: `shellcommon\shell\tiles\curatedtilecollections\storeeventlistener\lib\storeeventlistenerimpl.cpp`
- `0x180174bee`: `AppInstallCompleteActivity`

## pseudocode

```c
// Hidden C++ exception states: #wind=12 #try_helpers=1
__int64 __fastcall StoreEventListenerImpl::OnCompleted(RTL_SRWLOCK *this, struct IUnknown *a2, struct IUnknown *a3)
{
  struct IUnknownVtbl *lpVtbl; // rax
  int v5; // eax
  unsigned int v6; // ebx
  int v8; // eax
  unsigned int v9; // ebx
  int v10; // eax
  unsigned int v11; // ebx
  struct WindowsUpdate::Internal::IInstallItem *v12; // rdi
  __int64 (__fastcall *v13)(struct WindowsUpdate::Internal::IInstallItem *, HSTRING *); // rbx
  int v14; // eax
  unsigned int v15; // ebx
  struct WindowsUpdate::Internal::IInstallItem *v16; // rdi
  __int64 (__fastcall *v17)(struct WindowsUpdate::Internal::IInstallItem *, HSTRING *); // rbx
  int v18; // eax
  unsigned int v19; // ebx
  unsigned int v20; // ebx
  PCWSTR v21; // rax
  const unsigned __int16 *v22; // rbx
  const unsigned __int16 *v23; // rax
  StoreEventListenerImpl *v24; // rcx
  __int64 v25; // r8
  int v26; // r9d
  RTL_SRWLOCK **PlaceholderTileTransformer; // rax
  RTL_SRWLOCK *v28; // rbx
  __int64 v29; // rax
  __int64 (__fastcall *v30)(RTL_SRWLOCK *, _BYTE *, __int64); // r9
  const unsigned __int16 *v31; // rbx
  const unsigned __int16 *v32; // rax
  StoreEventListenerImpl *v33; // rcx
  int v34; // [rsp+20h] [rbp-208h]
  struct WindowsUpdate::Internal::IInstallItem *v35; // [rsp+40h] [rbp-1E8h] BYREF
  HSTRING string; // [rsp+48h] [rbp-1E0h] BYREF
  unsigned int v37; // [rsp+50h] [rbp-1D8h] BYREF
  HSTRING v38; // [rsp+58h] [rbp-1D0h] BYREF
  int v39; // [rsp+60h] [rbp-1C8h] BYREF
  PCWSTR StringRawBuffer; // [rsp+68h] [rbp-1C0h] BYREF
  RTL_SRWLOCK *v41; // [rsp+70h] [rbp-1B8h] BYREF
  _QWORD v42[2]; // [rsp+78h] [rbp-1B0h] BYREF
  char v43[8]; // [rsp+88h] [rbp-1A0h] BYREF
  _BYTE v44[16]; // [rsp+90h] [rbp-198h] BYREF
  char v45[8]; // [rsp+A0h] [rbp-188h] BYREF
  std::_Ref_count_base *v46; // [rsp+A8h] [rbp-180h]
  _QWORD v47[42]; // [rsp+B0h] [rbp-178h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+228h] [rbp+0h]

  lpVtbl = a3->lpVtbl;
  v35 = 0;
  v5 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct WindowsUpdate::Internal::IInstallItem **))lpVtbl->QueryInterface)(
         a3,
         &GUID_54f920df_4081_4dc8_af9d_115f147abeb2,
         &v35);
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC0,
      (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\storeeventlistener\\lib\\storeeventlistenerimpl.cpp",
      (const char *)(unsigned int)v5,
      v34);
    wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v35);
    return v6;
  }
  v39 = 0;
  v37 = 0;
  v8 = (*(__int64 (__fastcall **)(struct WindowsUpdate::Internal::IInstallItem *, int *))(*(_QWORD *)v35 + 56LL))(
         v35,
         &v39);
  v9 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC4,
      (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\storeeventlistener\\lib\\storeeventlistenerimpl.cpp",
      (const char *)(unsigned int)v8,
      v34);
    wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v35);
    return v9;
  }
  v10 = (*(__int64 (__fastcall **)(struct WindowsUpdate::Internal::IInstallItem *, unsigned int *))(*(_QWORD *)v35 + 64LL))(
          v35,
          &v37);
  v11 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC5,
      (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\storeeventlistener\\lib\\storeeventlistenerimpl.cpp",
      (const char *)(unsigned int)v10,
      v34);
    wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v35);
    return v11;
  }
  if ( (v39 & 0xFFFFFFFB) == 0 )
  {
    string = 0;
    v12 = v35;
    v13 = *(__int64 (__fastcall **)(struct WindowsUpdate::Internal::IInstallItem *, HSTRING *))(*(_QWORD *)v35 + 48LL);
    WindowsDeleteString(0);
    string = 0;
    v14 = v13(v12, &string);
    v15 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xCA,
        (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\storeeventlistener\\lib\\storeeventlistenerimpl.cpp",
        (const char *)(unsigned int)v14,
        v34);
      WindowsDeleteString(string);
      string = 0;
      wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v35);
      return v15;
    }
    v38 = 0;
    v16 = v35;
    v17 = *(__int64 (__fastcall **)(struct WindowsUpdate::Internal::IInstallItem *, HSTRING *))(*(_QWORD *)v35 + 112LL);
    WindowsDeleteString(0);
    v38 = 0;
    v18 = v17(v16, &v38);
    v19 = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xCF,
        (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\storeeventlistener\\lib\\storeeventlistenerimpl.cpp",
        (const char *)(unsigned int)v18,
        v34);
      WindowsDeleteString(v38);
      v38 = 0;
      WindowsDeleteString(string);
      string = 0;
      wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v35);
      return v19;
    }
    wil::ActivityBase<StartLayoutTelemetryLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<StartLayoutTelemetryLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v47);
    v47[0] = &StartPlaceHolderTelemetry::AppInstallCompleteActivity::`vftable';
    StartPlaceHolderTelemetry::AppInstallCompleteActivity::StartActivity((StartPlaceHolderTelemetry::AppInstallCompleteActivity *)v47);
    StringRawBuffer = WindowsGetStringRawBuffer(v38, 0);
    StartPlaceHolderTelemetry::AppInstallCompleteActivity::LogState<unsigned short const *,enum WindowsUpdate::Internal::InstallState &>(
      v47,
      &StringRawBuffer,
      &v37);
    if ( (Microsoft_Windows_ShellCommon_StartLayoutPopulationEnableBits & 1) != 0 )
    {
      v20 = v37;
      v21 = WindowsGetStringRawBuffer(v38, 0);
      McTemplateU0zq_EventWriteTransfer(
        &Microsoft_Windows_StartLayoutPopulation_Provider_Context,
        InstallComplete,
        v21,
        v20);
    }
    if ( v37 == 5 )
    {
      StoreEventListenerImpl::RemovePlaceholdertile((StoreEventListenerImpl *)this, string, v35);
      v22 = WindowsGetStringRawBuffer(v38, 0);
      v23 = WindowsGetStringRawBuffer(string, 0);
      StoreEventListenerImpl::PublishAppLifecycleWnfStateIfNecessary(
        v24,
        v23,
        v22,
        &WNF_SHEL_START_APPLIFECYCLE_INSTALL_FINISHED);
    }
    else if ( v37 == 4 )
    {
      StoreEventListenerImpl::GetAppData(this, &StringRawBuffer, v35, string);
      v25 = *(_QWORD *)StoreEventListenerImpl::GetUserFromInstallItem(this, v42, v35);
      PlaceholderTileTransformer = (RTL_SRWLOCK **)DataStoreCache::PlaceholderTileTransformer::CreatePlaceholderTileTransformer(
                                                     (unsigned int)v44,
                                                     0,
                                                     v25,
                                                     v26,
                                                     0,
                                                     0,
                                                     0);
      v28 = *PlaceholderTileTransformer;
      *PlaceholderTileTransformer = 0;
      v41 = v28;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v44);
      wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(v42);
      (*((void (__fastcall **)(RTL_SRWLOCK *, char *))v28->Ptr + 10))(v28, v45);
      v42[0] = this;
      v42[1] = v35;
      if ( v35 )
        (*(void (__fastcall **)(struct WindowsUpdate::Internal::IInstallItem *))(*(_QWORD *)v35 + 8LL))(v35);
      wil::com_ptr_t<Windows::Foundation::IAsyncAction,wil::err_exception_policy>::com_ptr_t<Windows::Foundation::IAsyncAction,wil::err_exception_policy>(
        v43,
        v28);
      ForEachApp<_lambda_3bcd5f19bc5f32682702b982507cf16e_>(StringRawBuffer, v42);
      v29 = std::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemUpdaterImpl<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>,DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>,DataStoreCache::CloudUtil::Internal::CloudItemManager<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>>::CloudItemAction<Windows::Data::PlaceholderTileCollection>>::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemUpdaterImpl<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>,DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>,DataStoreCache::CloudUtil::Internal::CloudItemManager<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>>::CloudItemAction<Windows::Data::PlaceholderTileCollection>>(
              v42,
              v45);
      if ( !*(_QWORD *)v30(v28, v44, v29) )
        Concurrency::details::_DefaultTaskHelper::_NoCallOnDefaultTask_ErrorImpl();
      Concurrency::details::_Task_impl_base::_Wait();
      std::shared_ptr<DataStoreCache::CDSDataTransformer::CDSDataTransformer<Windows::Data::CuratedTileCollection::TileCollectionContainer,IInspectable>>::~shared_ptr<DataStoreCache::CDSDataTransformer::CDSDataTransformer<Windows::Data::CuratedTileCollection::TileCollectionContainer,IInspectable>>(v44);
      v31 = WindowsGetStringRawBuffer(v38, 0);
      v32 = WindowsGetStringRawBuffer(string, 0);
      StoreEventListenerImpl::PublishAppLifecycleWnfStateIfNecessary(
        v33,
        v32,
        v31,
        &WNF_SHEL_START_APPLIFECYCLE_INSTALL_FINISHED);
      if ( v46 )
        std::_Ref_count_base::_Decref(v46);
      wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v41);
      wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&StringRawBuffer);
    }
    AcquireSRWLockExclusive(this + 6);
    v41 = this + 6;
    Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::Remove(
      this[7].Ptr,
      string);
    wil::ActivityBase<StartLayoutTelemetryLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v47);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v41);
    StartPlaceHolderTelemetry::AppInstallCompleteActivity::~AppInstallCompleteActivity((StartPlaceHolderTelemetry::AppInstallCompleteActivity *)v47);
    WindowsDeleteString(v38);
    v38 = 0;
    WindowsDeleteString(string);
  }
  wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v35);
  return 0;
}

```

## disassembly

```asm
0x1801749d0  mov     [rsp+arg_8], rbx
0x1801749d5  push    rsi
0x1801749d6  push    rdi
0x1801749d7  push    r14
0x1801749d9  sub     rsp, 210h
0x1801749e0  mov     rax, cs:__security_cookie
0x1801749e7  xor     rax, rsp
0x1801749ea  mov     [rsp+228h+var_28], rax
0x1801749f2  mov     r9, r8
0x1801749f5  mov     rsi, rcx
0x1801749f8  mov     rax, [r8]
0x1801749fb  xor     r14d, r14d
0x1801749fe  mov     [rsp+228h+var_1E8], r14
0x180174a03  lea     r8, [rsp+228h+var_1E8]
0x180174a08  lea     rdx, _GUID_54f920df_4081_4dc8_af9d_115f147abeb2
0x180174a0f  mov     rcx, r9
0x180174a12  mov     rax, [rax]
0x180174a15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180174a1a  mov     ebx, eax
0x180174a1c  test    eax, eax
0x180174a1e  jns     short loc_180174A4E
0x180174a20  mov     rcx, [rsp+228h]; this
0x180174a28  mov     r9d, eax; char *
0x180174a2b  lea     r8, aShellcommonShe_106; "shellcommon\\shell\\tiles\\curatedtilec"...
0x180174a32  mov     edx, 0C0h; void *
0x180174a37  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180174a3c  nop
0x180174a3d  lea     rcx, [rsp+228h+var_1E8]; void *
0x180174a42  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x180174a47  mov     eax, ebx
0x180174a49  jmp     loc_180174EB9
0x180174a4e  mov     [rsp+228h+var_1C8], r14d
0x180174a53  mov     [rsp+228h+var_1D8], r14d
0x180174a58  mov     rcx, [rsp+228h+var_1E8]
0x180174a5d  mov     rax, [rcx]
0x180174a60  lea     rdx, [rsp+228h+var_1C8]
0x180174a65  mov     rax, [rax+38h]
0x180174a69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180174a6e  mov     ebx, eax
0x180174a70  test    eax, eax
0x180174a72  jns     short loc_180174AA2
0x180174a74  mov     rcx, [rsp+228h]; this
0x180174a7c  mov     r9d, eax; char *
0x180174a7f  lea     r8, aShellcommonShe_106; "shellcommon\\shell\\tiles\\curatedtilec"...
0x180174a86  mov     edx, 0C4h; void *
0x180174a8b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180174a90  nop
0x180174a91  lea     rcx, [rsp+228h+var_1E8]; void *
0x180174a96  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x180174a9b  mov     eax, ebx
0x180174a9d  jmp     loc_180174EB9
0x180174aa2  mov     rcx, [rsp+228h+var_1E8]
0x180174aa7  mov     rax, [rcx]
0x180174aaa  lea     rdx, [rsp+228h+var_1D8]
0x180174aaf  mov     rax, [rax+40h]
0x180174ab3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180174ab8  mov     ebx, eax
0x180174aba  test    eax, eax
0x180174abc  jns     short loc_180174AEC
0x180174abe  mov     rcx, [rsp+228h]; this
0x180174ac6  mov     r9d, eax; char *
0x180174ac9  lea     r8, aShellcommonShe_106; "shellcommon\\shell\\tiles\\curatedtilec"...
0x180174ad0  mov     edx, 0C5h; void *
0x180174ad5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180174ada  nop
0x180174adb  lea     rcx, [rsp+228h+var_1E8]; void *
0x180174ae0  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x180174ae5  mov     eax, ebx
0x180174ae7  jmp     loc_180174EB9
0x180174aec  test    [rsp+228h+var_1C8], 0FFFFFFFBh
0x180174af4  jnz     loc_180174EA7
0x180174afa  mov     [rsp+228h+string], r14
0x180174aff  mov     rdi, [rsp+228h+var_1E8]
0x180174b04  mov     rax, [rdi]
0x180174b07  mov     rbx, [rax+30h]
0x180174b0b  xor     ecx, ecx; string
0x180174b0d  call    cs:__imp_WindowsDeleteString
0x180174b13  mov     [rsp+228h+string], r14
0x180174b18  lea     rdx, [rsp+228h+string]
0x180174b1d  mov     rcx, rdi
0x180174b20  mov     rax, rbx
0x180174b23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180174b28  mov     ebx, eax
0x180174b2a  test    eax, eax
0x180174b2c  jns     short loc_180174B6C
0x180174b2e  mov     rcx, [rsp+228h]; this
0x180174b36  mov     r9d, eax; char *
0x180174b39  lea     r8, aShellcommonShe_106; "shellcommon\\shell\\tiles\\curatedtilec"...
0x180174b40  mov     edx, 0CAh; void *
0x180174b45  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180174b4a  nop
0x180174b4b  mov     rcx, [rsp+228h+string]; string
0x180174b50  call    cs:__imp_WindowsDeleteString
0x180174b56  mov     [rsp+228h+string], r14
0x180174b5b  lea     rcx, [rsp+228h+var_1E8]; void *
0x180174b60  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x180174b65  mov     eax, ebx
0x180174b67  jmp     loc_180174EB9
0x180174b6c  mov     [rsp+228h+var_1D0], r14
0x180174b71  mov     rdi, [rsp+228h+var_1E8]
0x180174b76  mov     rax, [rdi]
0x180174b79  mov     rbx, [rax+70h]
0x180174b7d  xor     ecx, ecx; string
0x180174b7f  call    cs:__imp_WindowsDeleteString
0x180174b85  mov     [rsp+228h+var_1D0], r14
0x180174b8a  lea     rdx, [rsp+228h+var_1D0]
0x180174b8f  mov     rcx, rdi
0x180174b92  mov     rax, rbx
0x180174b95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180174b9a  mov     ebx, eax
0x180174b9c  test    eax, eax
0x180174b9e  jns     short loc_180174BEE
0x180174ba0  mov     rcx, [rsp+228h]; this
0x180174ba8  mov     r9d, eax; char *
0x180174bab  lea     r8, aShellcommonShe_106; "shellcommon\\shell\\tiles\\curatedtilec"...
0x180174bb2  mov     edx, 0CFh; void *
0x180174bb7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180174bbc  nop
0x180174bbd  mov     rcx, [rsp+228h+var_1D0]; string
0x180174bc2  call    cs:__imp_WindowsDeleteString
0x180174bc8  mov     [rsp+228h+var_1D0], r14
0x180174bcd  mov     rcx, [rsp+228h+string]; string
0x180174bd2  call    cs:__imp_WindowsDeleteString
0x180174bd8  mov     [rsp+228h+string], r14
0x180174bdd  lea     rcx, [rsp+228h+var_1E8]; void *
0x180174be2  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x180174be7  mov     eax, ebx
0x180174be9  jmp     loc_180174EB9
0x180174bee  lea     rdx, aAppinstallcomp; "AppInstallCompleteActivity"
0x180174bf5  lea     rcx, [rsp+228h+var_178]; struct wil::details::IFailureCallback *
0x180174bfd  call    ??0?$ActivityBase@VStartLayoutTelemetryLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<StartLayoutTelemetryLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<StartLayoutTelemetryLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180174c02  lea     rax, ??_7AppInstallCompleteActivity@StartPlaceHolderTelemetry@@6B@; const StartPlaceHolderTelemetry::AppInstallCompleteActivity::`vftable'
0x180174c09  mov     [rsp+228h+var_178], rax
0x180174c11  lea     rcx, [rsp+228h+var_178]; this
0x180174c19  call    ?StartActivity@AppInstallCompleteActivity@StartPlaceHolderTelemetry@@QEAAXXZ; StartPlaceHolderTelemetry::AppInstallCompleteActivity::StartActivity(void)
0x180174c1e  nop
0x180174c1f  xor     edx, edx; length
0x180174c21  mov     rcx, [rsp+228h+var_1D0]; string
0x180174c26  call    cs:__imp_WindowsGetStringRawBuffer
0x180174c2c  mov     [rsp+228h+var_1C0], rax
0x180174c31  lea     r8, [rsp+228h+var_1D8]
0x180174c36  lea     rdx, [rsp+228h+var_1C0]
0x180174c3b  lea     rcx, [rsp+228h+var_178]
0x180174c43  call    ??$LogState@PEBGAEAW4InstallState@Internal@WindowsUpdate@@@AppInstallCompleteActivity@StartPlaceHolderTelemetry@@QEAAX$$QEAPEBGAEAW4InstallState@Internal@WindowsUpdate@@@Z; StartPlaceHolderTelemetry::AppInstallCompleteActivity::LogState<ushort const *,WindowsUpdate::Internal::InstallState &>(ushort const * &&,WindowsUpdate::Internal::InstallState &)
0x180174c48  test    cs:Microsoft_Windows_ShellCommon_StartLayoutPopulationEnableBits, 1
0x180174c4f  jz      short loc_180174C7B
0x180174c51  mov     ebx, [rsp+228h+var_1D8]
0x180174c55  xor     edx, edx; length
0x180174c57  mov     rcx, [rsp+228h+var_1D0]; string
0x180174c5c  call    cs:__imp_WindowsGetStringRawBuffer
0x180174c62  mov     r9d, ebx
0x180174c65  mov     r8, rax
0x180174c68  lea     rdx, InstallComplete
0x180174c6f  lea     rcx, Microsoft_Windows_StartLayoutPopulation_Provider_Context
0x180174c76  call    McTemplateU0zq_EventWriteTransfer
0x180174c7b  cmp     [rsp+228h+var_1D8], 5
0x180174c80  jnz     short loc_180174CC8
0x180174c82  mov     r8, [rsp+228h+var_1E8]; struct WindowsUpdate::Internal::IInstallItem *
0x180174c87  mov     rdx, [rsp+228h+string]; HSTRING
0x180174c8c  mov     rcx, rsi; this
0x180174c8f  call    ?RemovePlaceholdertile@StoreEventListenerImpl@@AEAAXPEAUHSTRING__@@PEAUIInstallItem@Internal@WindowsUpdate@@@Z; StoreEventListenerImpl::RemovePlaceholdertile(HSTRING__ *,WindowsUpdate::Internal::IInstallItem *)
0x180174c94  xor     edx, edx; length
0x180174c96  mov     rcx, [rsp+228h+var_1D0]; string
0x180174c9b  call    cs:__imp_WindowsGetStringRawBuffer
0x180174ca1  mov     rbx, rax
0x180174ca4  xor     edx, edx; length
0x180174ca6  mov     rcx, [rsp+228h+string]; string
0x180174cab  call    cs:__imp_WindowsGetStringRawBuffer
0x180174cb1  lea     r9, WNF_SHEL_START_APPLIFECYCLE_INSTALL_FINISHED; struct _WNF_STATE_NAME *
0x180174cb8  mov     r8, rbx; unsigned __int16 *
0x180174cbb  mov     rdx, rax; unsigned __int16 *
0x180174cbe  call    ?PublishAppLifecycleWnfStateIfNecessary@StoreEventListenerImpl@@AEAAXPEBG0AEBU_WNF_STATE_NAME@@@Z; StoreEventListenerImpl::PublishAppLifecycleWnfStateIfNecessary(ushort const *,ushort const *,_WNF_STATE_NAME const &)
0x180174cc3  jmp     loc_180174E45
0x180174cc8  cmp     [rsp+228h+var_1D8], 4
0x180174ccd  jnz     loc_180174E45
0x180174cd3  mov     r9, [rsp+228h+string]
0x180174cd8  mov     r8, [rsp+228h+var_1E8]
0x180174cdd  lea     rdx, [rsp+228h+var_1C0]
0x180174ce2  mov     rcx, rsi
0x180174ce5  call    ?GetAppData@StoreEventListenerImpl@@AEAA?AV?$com_ptr_t@UIAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@Uerr_exception_policy@wil@@@wil@@PEAUIInstallItem@Internal@WindowsUpdate@@PEAUHSTRING__@@@Z; StoreEventListenerImpl::GetAppData(WindowsUpdate::Internal::IInstallItem *,HSTRING__ *)
0x180174cea  nop
0x180174ceb  mov     r8, [rsp+228h+var_1E8]
0x180174cf0  lea     rdx, [rsp+228h+var_1B0]
0x180174cf5  mov     rcx, rsi
0x180174cf8  call    ?GetUserFromInstallItem@StoreEventListenerImpl@@AEAA?AV?$com_ptr_t@UIUser@System@Windows@@Uerr_exception_policy@wil@@@wil@@PEAUIInstallItem@Internal@WindowsUpdate@@@Z; StoreEventListenerImpl::GetUserFromInstallItem(WindowsUpdate::Internal::IInstallItem *)
0x180174cfd  nop
0x180174cfe  mov     [rsp+228h+var_1F8], r14
0x180174d03  mov     [rsp+228h+var_200], r14
0x180174d08  mov     [rsp+228h+var_208], r14
0x180174d0d  mov     r8, [rax]
0x180174d10  xor     edx, edx
0x180174d12  lea     rcx, [rsp+228h+var_198]
0x180174d1a  call    ?CreatePlaceholderTileTransformer@PlaceholderTileTransformer@DataStoreCache@@YA?AV?$ComPtr@UIPlaceholderTileTransformer@PlaceholderTileTransformer@DataStoreCache@@@WRL@Microsoft@@PEAUIDataManager@2@PEAUIUser@System@Windows@@W4PlaceholderTileTransformerOptions@12@PEAUIMRTTransformer@2@PEAUIUnifiedTileManager@UnifiedTile@Shell@WindowsInternal@@PEAV?$shared_ptr@VIPlaceholderTileBatchCookie@PlaceholderTileTransformer@DataStoreCache@@@std@@@Z; DataStoreCache::PlaceholderTileTransformer::CreatePlaceholderTileTransformer(DataStoreCache::IDataManager *,Windows::System::IUser *,DataStoreCache::PlaceholderTileTransformer::PlaceholderTileTransformerOptions,DataStoreCache::IMRTTransformer *,WindowsInternal::Shell::UnifiedTile::IUnifiedTileManager *,std::shared_ptr<DataStoreCache::PlaceholderTileTransformer::IPlaceholderTileBatchCookie> *)
0x180174d1f  mov     rbx, [rax]
0x180174d22  mov     [rax], r14
0x180174d25  mov     [rsp+228h+var_1B8], rbx
0x180174d2a  lea     rcx, [rsp+228h+var_198]
0x180174d32  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180174d37  nop
0x180174d38  lea     rcx, [rsp+228h+var_1B0]; void *
0x180174d3d  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x180174d42  mov     rax, [rbx]
0x180174d45  lea     rdx, [rsp+228h+var_188]
0x180174d4d  mov     rcx, rbx
0x180174d50  mov     rax, [rax+50h]
0x180174d54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180174d59  nop
0x180174d5a  mov     [rsp+228h+var_1B0], rsi
0x180174d5f  mov     rcx, [rsp+228h+var_1E8]
0x180174d64  mov     [rsp+228h+var_1A8], rcx
0x180174d6c  test    rcx, rcx
0x180174d6f  jz      short loc_180174D7E
0x180174d71  mov     rax, [rcx]
0x180174d74  mov     rax, [rax+8]
0x180174d78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180174d7d  nop
0x180174d7e  mov     rdx, rbx
0x180174d81  lea     rcx, [rsp+228h+var_1A0]
0x180174d89  call    ??0?$com_ptr_t@UIAsyncAction@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAUIAsyncAction@Foundation@Windows@@@Z; wil::com_ptr_t<Windows::Foundation::IAsyncAction,wil::err_exception_policy>::com_ptr_t<Windows::Foundation::IAsyncAction,wil::err_exception_policy>(Windows::Foundation::IAsyncAction *)
0x180174d8e  lea     rdx, [rsp+228h+var_1B0]
0x180174d93  mov     rcx, [rsp+228h+var_1C0]
0x180174d98  call    ??$ForEachApp@V_lambda_3bcd5f19bc5f32682702b982507cf16e_@@@@YAXPEAUIAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@V_lambda_3bcd5f19bc5f32682702b982507cf16e_@@@Z; ForEachApp<_lambda_3bcd5f19bc5f32682702b982507cf16e_>(Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppData *,_lambda_3bcd5f19bc5f32682702b982507cf16e_)
0x180174d9d  mov     rax, [rbx]
0x180174da0  mov     r9, [rax+58h]
0x180174da4  lea     rdx, [rsp+228h+var_188]
0x180174dac  lea     rcx, [rsp+228h+var_1B0]
0x180174db1  call    ??0?$shared_ptr@U?$CloudItemAction@UPlaceholderTileCollection@Data@Windows@@@?$CloudItemUpdaterImpl@V?$GenericCloudItem@UPlaceholderTileCollection@Data@Windows@@$0A@@CloudUtil@DataStoreCache@@V?$CloudItemInternal@V?$GenericCloudItem@UPlaceholderTileCollection@Data@Windows@@$0A@@CloudUtil@DataStoreCache@@@Internal@23@V?$CloudItemManager@V?$GenericCloudItem@UPlaceholderTileCollection@Data@Windows@@$0A@@CloudUtil@DataStoreCache@@@523@@Internal@CloudUtil@DataStoreCache@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemUpdaterImpl<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>,DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>,DataStoreCache::CloudUtil::Internal::CloudItemManager<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>>::CloudItemAction<Windows::Data::PlaceholderTileCollection>>::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemUpdaterImpl<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>,DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>,DataStoreCache::CloudUtil::Internal::CloudItemManager<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>>::CloudItemAction<Windows::Data::PlaceholderTileCollection>>(std::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemUpdaterImpl<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>,DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>,DataStoreCache::CloudUtil::Internal::CloudItemManager<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>>::CloudItemAction<Windows::Data::PlaceholderTileCollection>> const &)
0x180174db6  mov     r8, rax
0x180174db9  lea     rdx, [rsp+228h+var_198]
0x180174dc1  mov     rcx, rbx
0x180174dc4  mov     rax, r9
0x180174dc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180174dcc  nop
0x180174dcd  mov     rcx, [rax]
0x180174dd0  test    rcx, rcx
0x180174dd3  jnz     short loc_180174DDA
0x180174dd5  call    ?_NoCallOnDefaultTask_ErrorImpl@_DefaultTaskHelper@details@Concurrency@@SAXXZ; Concurrency::details::_DefaultTaskHelper::_NoCallOnDefaultTask_ErrorImpl(void)
0x180174dda  call    ?_Wait@_Task_impl_base@details@Concurrency@@QEAA?AW4task_group_status@3@XZ; Concurrency::details::_Task_impl_base::_Wait(void)
0x180174ddf  nop
0x180174de0  lea     rcx, [rsp+228h+var_198]; void *
0x180174de8  call    ??1?$shared_ptr@V?$CDSDataTransformer@UTileCollectionContainer@CuratedTileCollection@Data@Windows@@UIInspectable@@@CDSDataTransformer@DataStoreCache@@@std@@QEAA@XZ; std::shared_ptr<DataStoreCache::CDSDataTransformer::CDSDataTransformer<Windows::Data::CuratedTileCollection::TileCollectionContainer,IInspectable>>::~shared_ptr<DataStoreCache::CDSDataTransformer::CDSDataTransformer<Windows::Data::CuratedTileCollection::TileCollectionContainer,IInspectable>>(void)
0x180174ded  xor     edx, edx; length
0x180174def  mov     rcx, [rsp+228h+var_1D0]; string
0x180174df4  call    cs:__imp_WindowsGetStringRawBuffer
0x180174dfa  mov     rbx, rax
0x180174dfd  xor     edx, edx; length
0x180174dff  mov     rcx, [rsp+228h+string]; string
0x180174e04  call    cs:__imp_WindowsGetStringRawBuffer
0x180174e0a  lea     r9, WNF_SHEL_START_APPLIFECYCLE_INSTALL_FINISHED; struct _WNF_STATE_NAME *
0x180174e11  mov     r8, rbx; unsigned __int16 *
0x180174e14  mov     rdx, rax; unsigned __int16 *
0x180174e17  call    ?PublishAppLifecycleWnfStateIfNecessary@StoreEventListenerImpl@@AEAAXPEBG0AEBU_WNF_STATE_NAME@@@Z; StoreEventListenerImpl::PublishAppLifecycleWnfStateIfNecessary(ushort const *,ushort const *,_WNF_STATE_NAME const &)
0x180174e1c  nop
0x180174e1d  mov     rcx, [rsp+228h+var_180]; this
0x180174e25  test    rcx, rcx
0x180174e28  jz      short loc_180174E30
0x180174e2a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180174e2f  nop
0x180174e30  lea     rcx, [rsp+228h+var_1B8]; void *
0x180174e35  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x180174e3a  nop
0x180174e3b  lea     rcx, [rsp+228h+var_1C0]; void *
0x180174e40  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x180174e45  lea     rbx, [rsi+30h]
0x180174e49  mov     rcx, rbx; SRWLock
0x180174e4c  call    cs:__imp_AcquireSRWLockExclusive
0x180174e52  mov     [rsp+228h+var_1B8], rbx
0x180174e57  mov     rdx, [rsp+228h+string]
0x180174e5c  mov     rcx, [rsi+38h]
0x180174e60  call    ?Remove@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$HashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@4567@@Internal@Collections@Foundation@Windows@@UEAAJPEAUHSTRING__@@@Z; Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::Remove(HSTRING__ *)
0x180174e65  lea     rcx, [rsp+228h+var_178]
0x180174e6d  call    ?Stop@?$ActivityBase@VStartLayoutTelemetryLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<StartLayoutTelemetryLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180174e72  lea     rcx, [rsp+228h+var_1B8]
0x180174e77  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x180174e7c  nop
0x180174e7d  lea     rcx, [rsp+228h+var_178]; this
0x180174e85  call    ??1AppInstallCompleteActivity@StartPlaceHolderTelemetry@@QEAA@XZ; StartPlaceHolderTelemetry::AppInstallCompleteActivity::~AppInstallCompleteActivity(void)
0x180174e8a  nop
0x180174e8b  mov     rcx, [rsp+228h+var_1D0]; string
0x180174e90  call    cs:__imp_WindowsDeleteString
0x180174e96  mov     [rsp+228h+var_1D0], r14
0x180174e9b  mov     rcx, [rsp+228h+string]; string
0x180174ea0  call    cs:__imp_WindowsDeleteString
0x180174ea6  nop
0x180174ea7  lea     rcx, [rsp+228h+var_1E8]; void *
0x180174eac  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x180174eb1  xor     eax, eax
0x180174eb3  jmp     short loc_180174EB9
0x180174eb5  mov     eax, [rsp+228h+var_1C8]
0x180174eb9  mov     rcx, [rsp+228h+var_28]
0x180174ec1  xor     rcx, rsp; StackCookie
0x180174ec4  call    __security_check_cookie
0x180174ec9  mov     rbx, [rsp+228h+arg_8]
0x180174ed1  add     rsp, 210h
0x180174ed8  pop     r14
0x180174eda  pop     rdi
0x180174edb  pop     rsi
0x180174edc  retn
```
