# StoreEventListenerImpl::OnProgress(IUnknown *,IUnknown *)

- ea: `0x1800f9920`
- end: `0x1800f9dcc`
- name: `?OnProgress@StoreEventListenerImpl@@UEAAJPEAUIUnknown@@0@Z`
- size: `1196`
- prototype: `__int64 __fastcall(StoreEventListenerImpl *__hidden this, struct IUnknown *, struct IUnknown *)`
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x18001aca4`
- `0x18002dde0`
- `0x18008d550`
- `0x1800cd444`
- `0x1800f9920`
- `0x180159d04`
- `0x180161204`
- `0x180175534`
- `0x1801756f4`
- `0x1801762c0`
- `0x180195820`
- `0x1801f7af8`
- `0x180201e50`
- `0x18025b010`
- `0x18025bd50`
- `0x18025d2e0`
- `0x18025ebe0`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800f9ab5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800f9b2d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800f9ab5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800f9b2d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f9bc1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f9bd1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f9c4e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f9c91`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f9cc0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f9d03`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f9d13`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f9bc1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f9bd1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f9c4e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f9c91`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f9cc0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f9d03`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f9d13`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f9b7e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f9b8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f9d5e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f9d95`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f9b7e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f9b8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f9d5e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f9d95`

## string_xrefs

- `0x1800f9a10`: `shellcommon\shell\tiles\curatedtilecollections\storeeventlistener\lib\storeeventlistenerimpl.cpp`
- `0x1800f9a48`: `shellcommon\shell\tiles\curatedtilecollections\storeeventlistener\lib\storeeventlistenerimpl.cpp`
- `0x1800f9a7e`: `shellcommon\shell\tiles\curatedtilecollections\storeeventlistener\lib\storeeventlistenerimpl.cpp`
- `0x1800f9ae2`: `shellcommon\shell\tiles\curatedtilecollections\storeeventlistener\lib\storeeventlistenerimpl.cpp`
- `0x1800f9c0a`: `shellcommon\shell\tiles\curatedtilecollections\storeeventlistener\lib\storeeventlistenerimpl.cpp`
- `0x1800f9c7a`: `shellcommon\shell\tiles\curatedtilecollections\storeeventlistener\lib\storeeventlistenerimpl.cpp`
- `0x1800f9cec`: `shellcommon\shell\tiles\curatedtilecollections\storeeventlistener\lib\storeeventlistenerimpl.cpp`
- `0x1800f9d2f`: `AppInstallOnProgressActivity`

## pseudocode

```c
// Hidden C++ exception states: #wind=7 #try_helpers=1
__int64 __fastcall StoreEventListenerImpl::OnProgress(RTL_SRWLOCK *this, struct IUnknown *a2, struct IUnknown *a3)
{
  struct IUnknownVtbl *lpVtbl; // rax
  int v5; // eax
  unsigned int v6; // ebx
  int v7; // eax
  int v8; // eax
  int HasKey; // eax
  char v11; // bl
  const unsigned __int16 *v12; // rbx
  const unsigned __int16 *v13; // rax
  StoreEventListenerImpl *v14; // rcx
  int v15; // eax
  int v16; // ecx
  struct WindowsUpdate::Internal::IInstallItem *v17; // rdi
  __int64 (__fastcall *v18)(struct WindowsUpdate::Internal::IInstallItem *, HSTRING *); // rbx
  int v19; // eax
  unsigned int v20; // ebx
  struct WindowsUpdate::Internal::IInstallItem *v21; // rdi
  __int64 (__fastcall *v22)(struct WindowsUpdate::Internal::IInstallItem *, HSTRING *); // rbx
  int v23; // eax
  unsigned int v24; // ebx
  unsigned int v25; // ebx
  PCWSTR v26; // rax
  int v27; // [rsp+20h] [rbp-1B8h] BYREF
  HSTRING v28; // [rsp+28h] [rbp-1B0h] BYREF
  struct WindowsUpdate::Internal::IInstallItem *v29; // [rsp+30h] [rbp-1A8h] BYREF
  unsigned int v30; // [rsp+38h] [rbp-1A0h] BYREF
  HSTRING string; // [rsp+40h] [rbp-198h] BYREF
  struct Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppData *StringRawBuffer; // [rsp+48h] [rbp-190h] BYREF
  int v33; // [rsp+50h] [rbp-188h] BYREF
  RTL_SRWLOCK *v34; // [rsp+58h] [rbp-180h] BYREF
  _QWORD v35[42]; // [rsp+60h] [rbp-178h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+0h]

  lpVtbl = a3->lpVtbl;
  v29 = 0;
  v5 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct WindowsUpdate::Internal::IInstallItem **))lpVtbl->QueryInterface)(
         a3,
         &GUID_54f920df_4081_4dc8_af9d_115f147abeb2,
         &v29);
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x76,
      (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\storeeventlistener\\lib\\storeeventlistenerimpl.cpp",
      (const char *)(unsigned int)v5,
      v27);
    if ( v29 )
      (*(void (__fastcall **)(struct WindowsUpdate::Internal::IInstallItem *))(*(_QWORD *)v29 + 16LL))(v29);
    return v6;
  }
  v33 = 0;
  v30 = 0;
  v7 = (*(__int64 (__fastcall **)(struct WindowsUpdate::Internal::IInstallItem *, int *))(*(_QWORD *)v29 + 56LL))(
         v29,
         &v33);
  v6 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7A,
      (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\storeeventlistener\\lib\\storeeventlistenerimpl.cpp",
      (const char *)(unsigned int)v7,
      v27);
    if ( v29 )
      (*(void (__fastcall **)(struct WindowsUpdate::Internal::IInstallItem *))(*(_QWORD *)v29 + 16LL))(v29);
    return v6;
  }
  v8 = (*(__int64 (__fastcall **)(struct WindowsUpdate::Internal::IInstallItem *, unsigned int *))(*(_QWORD *)v29 + 64LL))(
         v29,
         &v30);
  v6 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7B,
      (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\storeeventlistener\\lib\\storeeventlistenerimpl.cpp",
      (const char *)(unsigned int)v8,
      v27);
    if ( v29 )
      (*(void (__fastcall **)(struct WindowsUpdate::Internal::IInstallItem *))(*(_QWORD *)v29 + 16LL))(v29);
    return v6;
  }
  if ( (v33 & 0xFFFFFFFB) == 0 && v30 <= 0xC )
  {
    v16 = 4545;
    if ( _bittest(&v16, v30) )
    {
      v28 = 0;
      v17 = v29;
      v18 = *(__int64 (__fastcall **)(struct WindowsUpdate::Internal::IInstallItem *, HSTRING *))(*(_QWORD *)v29 + 48LL);
      WindowsDeleteString(0);
      v28 = 0;
      v19 = v18(v17, &v28);
      v20 = v19;
      if ( v19 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x89,
          (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\storeeventlistener\\lib\\storeeventlistenerimpl.cpp",
          (const char *)(unsigned int)v19,
          v27);
        WindowsDeleteString(v28);
        v28 = 0;
        wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v29);
        return v20;
      }
      string = 0;
      v21 = v29;
      v22 = *(__int64 (__fastcall **)(struct WindowsUpdate::Internal::IInstallItem *, HSTRING *))(*(_QWORD *)v29 + 112LL);
      WindowsDeleteString(0);
      string = 0;
      v23 = v22(v21, &string);
      v24 = v23;
      if ( v23 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x8E,
          (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\storeeventlistener\\lib\\storeeventlistenerimpl.cpp",
          (const char *)(unsigned int)v23,
          v27);
        WindowsDeleteString(string);
        string = 0;
        WindowsDeleteString(v28);
        v28 = 0;
        wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v29);
        return v24;
      }
      wil::ActivityBase<StartLayoutTelemetryLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<StartLayoutTelemetryLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v35);
      v35[0] = &StartPlaceHolderTelemetry::AppInstallOnProgressActivity::`vftable';
      StartPlaceHolderTelemetry::AppInstallOnProgressActivity::StartActivity((StartPlaceHolderTelemetry::AppInstallOnProgressActivity *)v35);
      StringRawBuffer = (struct Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppData *)WindowsGetStringRawBuffer(string, 0);
      StartPlaceHolderTelemetry::AppInstallOnProgressActivity::LogState<unsigned short const *,enum WindowsUpdate::Internal::InstallState &>(
        v35,
        &StringRawBuffer,
        &v30);
      if ( (Microsoft_Windows_ShellCommon_StartLayoutPopulationEnableBits & 1) != 0 )
      {
        v25 = v30;
        v26 = WindowsGetStringRawBuffer(string, 0);
        McTemplateU0zq_EventWriteTransfer(
          &Microsoft_Windows_StartLayoutPopulation_Provider_Context,
          InstallOnProgress,
          v26,
          v25);
      }
      LOBYTE(v27) = 0;
      AcquireSRWLockExclusive(this + 6);
      StringRawBuffer = (struct Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppData *)&this[6];
      HasKey = Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,WindowsInternal::Shell::UnifiedTile::UnifiedTile *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<WindowsInternal::Shell::UnifiedTile::UnifiedTile *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,WindowsInternal::Shell::UnifiedTile::UnifiedTile *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::HasKey(
                 this[7].Ptr,
                 v28,
                 &v27);
      if ( HasKey < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x98,
          (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\storeeventlistener\\lib\\storeeventlistenerimpl.cpp",
          (const char *)(unsigned int)HasKey,
          v27);
      v11 = v27;
      if ( !(_BYTE)v27 )
      {
        LOBYTE(v27) = 0;
        v15 = Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::Insert(
                this[7].Ptr,
                v28,
                0,
                &v27);
        if ( v15 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x9E,
            (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\storeeventlistener\\lib\\storeeventlistenerimpl.cpp",
            (const char *)(unsigned int)v15,
            v27);
      }
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&StringRawBuffer);
      if ( !v11 )
      {
        StoreEventListenerImpl::GetAppData(this, &StringRawBuffer, v29, v28);
        LOBYTE(v27) = 0;
        AcquireSRWLockExclusive(this + 6);
        v34 = this + 6;
        Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::Insert(
          this[7].Ptr,
          v28,
          StringRawBuffer,
          &v27);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v34);
        StoreEventListenerImpl::CreatePlaceholderTile((StoreEventListenerImpl *)this, StringRawBuffer, v29);
        wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&StringRawBuffer);
      }
      v12 = WindowsGetStringRawBuffer(string, 0);
      v13 = WindowsGetStringRawBuffer(v28, 0);
      StoreEventListenerImpl::PublishAppLifecycleWnfStateIfNecessary(
        v14,
        v13,
        v12,
        &WNF_SHEL_START_APPLIFECYCLE_DOWNLOAD_STARTED);
      wil::ActivityBase<StartLayoutTelemetryLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v35);
      StartPlaceHolderTelemetry::AppInstallOnProgressActivity::~AppInstallOnProgressActivity((StartPlaceHolderTelemetry::AppInstallOnProgressActivity *)v35);
      WindowsDeleteString(string);
      string = 0;
      WindowsDeleteString(v28);
    }
  }
  if ( v29 )
    (*(void (__fastcall **)(struct WindowsUpdate::Internal::IInstallItem *))(*(_QWORD *)v29 + 16LL))(v29);
  return 0;
}

```

## disassembly

```asm
0x1800f9920  mov     [rsp+arg_8], rbx
0x1800f9925  push    rsi
0x1800f9926  push    rdi
0x1800f9927  push    r14
0x1800f9929  sub     rsp, 1C0h
0x1800f9930  mov     rax, cs:__security_cookie
0x1800f9937  xor     rax, rsp
0x1800f993a  mov     [rsp+1D8h+var_28], rax
0x1800f9942  mov     r9, r8
0x1800f9945  mov     rsi, rcx
0x1800f9948  mov     rax, [r8]
0x1800f994b  xor     r14d, r14d
0x1800f994e  mov     [rsp+1D8h+var_1A8], r14
0x1800f9953  lea     r8, [rsp+1D8h+var_1A8]
0x1800f9958  lea     rdx, _GUID_54f920df_4081_4dc8_af9d_115f147abeb2
0x1800f995f  mov     rcx, r9
0x1800f9962  mov     rax, [rax]
0x1800f9965  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f996a  mov     ebx, eax
0x1800f996c  test    eax, eax
0x1800f996e  js      loc_1800F9A3D
0x1800f9974  mov     [rsp+1D8h+var_188], r14d
0x1800f9979  mov     [rsp+1D8h+var_1A0], r14d
0x1800f997e  mov     rcx, [rsp+1D8h+var_1A8]
0x1800f9983  mov     rax, [rcx]
0x1800f9986  lea     rdx, [rsp+1D8h+var_188]
0x1800f998b  mov     rax, [rax+38h]
0x1800f998f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f9994  mov     ebx, eax
0x1800f9996  test    eax, eax
0x1800f9998  js      loc_1800F9A73
0x1800f999e  mov     rcx, [rsp+1D8h+var_1A8]
0x1800f99a3  mov     rax, [rcx]
0x1800f99a6  lea     rdx, [rsp+1D8h+var_1A0]
0x1800f99ab  mov     rax, [rax+40h]
0x1800f99af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f99b4  mov     ebx, eax
0x1800f99b6  test    eax, eax
0x1800f99b8  js      short loc_1800F9A05
0x1800f99ba  test    [rsp+1D8h+var_188], 0FFFFFFFBh
0x1800f99c2  jz      loc_1800F9C20
0x1800f99c8  mov     rcx, [rsp+1D8h+var_1A8]
0x1800f99cd  test    rcx, rcx
0x1800f99d0  jz      short loc_1800F99DF
0x1800f99d2  mov     rax, [rcx]
0x1800f99d5  mov     rax, [rax+10h]
0x1800f99d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f99de  nop
0x1800f99df  xor     eax, eax
0x1800f99e1  mov     rcx, [rsp+1D8h+var_28]
0x1800f99e9  xor     rcx, rsp; StackCookie
0x1800f99ec  call    __security_check_cookie
0x1800f99f1  mov     rbx, [rsp+1D8h+arg_8]
0x1800f99f9  add     rsp, 1C0h
0x1800f9a00  pop     r14
0x1800f9a02  pop     rdi
0x1800f9a03  pop     rsi
0x1800f9a04  retn
0x1800f9a05  mov     rcx, [rsp+1D8h]; this
0x1800f9a0d  mov     r9d, ebx; char *
0x1800f9a10  lea     r8, aShellcommonShe_106; "shellcommon\\shell\\tiles\\curatedtilec"...
0x1800f9a17  mov     edx, 7Bh ; '{'; void *
0x1800f9a1c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f9a21  nop
0x1800f9a22  mov     rcx, [rsp+1D8h+var_1A8]
0x1800f9a27  test    rcx, rcx
0x1800f9a2a  jz      short loc_1800F9A39
0x1800f9a2c  mov     rax, [rcx]
0x1800f9a2f  mov     rax, [rax+10h]
0x1800f9a33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f9a38  nop
0x1800f9a39  mov     eax, ebx
0x1800f9a3b  jmp     short loc_1800F99E1
0x1800f9a3d  mov     rcx, [rsp+1D8h]; this
0x1800f9a45  mov     r9d, ebx; char *
0x1800f9a48  lea     r8, aShellcommonShe_106; "shellcommon\\shell\\tiles\\curatedtilec"...
0x1800f9a4f  mov     edx, 76h ; 'v'; void *
0x1800f9a54  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f9a59  nop
0x1800f9a5a  mov     rcx, [rsp+1D8h+var_1A8]
0x1800f9a5f  test    rcx, rcx
0x1800f9a62  jz      short loc_1800F9A71
0x1800f9a64  mov     rax, [rcx]
0x1800f9a67  mov     rax, [rax+10h]
0x1800f9a6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f9a70  nop
0x1800f9a71  jmp     short loc_1800F9A39
0x1800f9a73  mov     rcx, [rsp+1D8h]; this
0x1800f9a7b  mov     r9d, ebx; char *
0x1800f9a7e  lea     r8, aShellcommonShe_106; "shellcommon\\shell\\tiles\\curatedtilec"...
0x1800f9a85  mov     edx, 7Ah ; 'z'; void *
0x1800f9a8a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f9a8f  nop
0x1800f9a90  mov     rcx, [rsp+1D8h+var_1A8]
0x1800f9a95  test    rcx, rcx
0x1800f9a98  jz      short loc_1800F9AA7
0x1800f9a9a  mov     rax, [rcx]
0x1800f9a9d  mov     rax, [rax+10h]
0x1800f9aa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f9aa6  nop
0x1800f9aa7  jmp     short loc_1800F9A39
0x1800f9aa9  mov     byte ptr [rsp+1D8h+var_1B8], r14b; int
0x1800f9aae  lea     rdi, [rsi+30h]
0x1800f9ab2  mov     rcx, rdi; SRWLock
0x1800f9ab5  call    cs:__imp_AcquireSRWLockExclusive
0x1800f9abb  mov     [rsp+1D8h+var_190], rdi
0x1800f9ac0  lea     r8, [rsp+1D8h+var_1B8]
0x1800f9ac5  mov     rdx, [rsp+1D8h+var_1B0]
0x1800f9aca  mov     rcx, [rsi+38h]
0x1800f9ace  call    ?HasKey@?$HashMap@PEAUHSTRING__@@PEAVUnifiedTile@2Shell@WindowsInternal@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@6789@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@6789@U?$DefaultLifetimeTraits@PEAVUnifiedTile@1Shell@WindowsInternal@@@6789@U?$HashMapOptions@PEAUHSTRING__@@PEAVUnifiedTile@2Shell@WindowsInternal@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@6789@@Internal@Collections@Foundation@Windows@@UEAAJPEAUHSTRING__@@PEAE@Z; Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,WindowsInternal::Shell::UnifiedTile::UnifiedTile *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<WindowsInternal::Shell::UnifiedTile::UnifiedTile *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,WindowsInternal::Shell::UnifiedTile::UnifiedTile *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::HasKey(HSTRING__ *,uchar *)
0x1800f9ad3  mov     rcx, [rsp+1D8h]; this
0x1800f9adb  test    eax, eax
0x1800f9add  jns     short loc_1800F9AF3
0x1800f9adf  mov     r9d, eax; char *
0x1800f9ae2  lea     r8, aShellcommonShe_106; "shellcommon\\shell\\tiles\\curatedtilec"...
0x1800f9ae9  mov     edx, 98h; void *
0x1800f9aee  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800f9af3  mov     bl, byte ptr [rsp+1D8h+var_1B8]
0x1800f9af7  test    bl, bl
0x1800f9af9  jz      loc_1800F9BDC
0x1800f9aff  lea     rcx, [rsp+1D8h+var_190]
0x1800f9b04  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x1800f9b09  test    bl, bl
0x1800f9b0b  jnz     short loc_1800F9B77
0x1800f9b0d  mov     r9, [rsp+1D8h+var_1B0]
0x1800f9b12  mov     r8, [rsp+1D8h+var_1A8]
0x1800f9b17  lea     rdx, [rsp+1D8h+var_190]
0x1800f9b1c  mov     rcx, rsi
0x1800f9b1f  call    ?GetAppData@StoreEventListenerImpl@@AEAA?AV?$com_ptr_t@UIAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@Uerr_exception_policy@wil@@@wil@@PEAUIInstallItem@Internal@WindowsUpdate@@PEAUHSTRING__@@@Z; StoreEventListenerImpl::GetAppData(WindowsUpdate::Internal::IInstallItem *,HSTRING__ *)
0x1800f9b24  nop
0x1800f9b25  mov     byte ptr [rsp+1D8h+var_1B8], r14b
0x1800f9b2a  mov     rcx, rdi; SRWLock
0x1800f9b2d  call    cs:__imp_AcquireSRWLockExclusive
0x1800f9b33  mov     [rsp+1D8h+var_180], rdi
0x1800f9b38  lea     r9, [rsp+1D8h+var_1B8]
0x1800f9b3d  mov     r8, [rsp+1D8h+var_190]
0x1800f9b42  mov     rdx, [rsp+1D8h+var_1B0]
0x1800f9b47  mov     rcx, [rsi+38h]
0x1800f9b4b  call    ?Insert@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$HashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@4567@@Internal@Collections@Foundation@Windows@@UEAAJPEAUHSTRING__@@PEAUIInspectable@@PEAE@Z; Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::Insert(HSTRING__ *,IInspectable *,uchar *)
0x1800f9b50  lea     rcx, [rsp+1D8h+var_180]
0x1800f9b55  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x1800f9b5a  mov     r8, [rsp+1D8h+var_1A8]; struct WindowsUpdate::Internal::IInstallItem *
0x1800f9b5f  mov     rdx, [rsp+1D8h+var_190]; struct Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppData *
0x1800f9b64  mov     rcx, rsi; this
0x1800f9b67  call    ?CreatePlaceholderTile@StoreEventListenerImpl@@AEAAXPEAUIAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@PEAUIInstallItem@3WindowsUpdate@@@Z; StoreEventListenerImpl::CreatePlaceholderTile(Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppData *,WindowsUpdate::Internal::IInstallItem *)
0x1800f9b6c  nop
0x1800f9b6d  lea     rcx, [rsp+1D8h+var_190]; void *
0x1800f9b72  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x1800f9b77  xor     edx, edx; length
0x1800f9b79  mov     rcx, [rsp+1D8h+string]; string
0x1800f9b7e  call    cs:__imp_WindowsGetStringRawBuffer
0x1800f9b84  mov     rbx, rax
0x1800f9b87  xor     edx, edx; length
0x1800f9b89  mov     rcx, [rsp+1D8h+var_1B0]; string
0x1800f9b8e  call    cs:__imp_WindowsGetStringRawBuffer
0x1800f9b94  lea     r9, WNF_SHEL_START_APPLIFECYCLE_DOWNLOAD_STARTED; struct _WNF_STATE_NAME *
0x1800f9b9b  mov     r8, rbx; unsigned __int16 *
0x1800f9b9e  mov     rdx, rax; unsigned __int16 *
0x1800f9ba1  call    ?PublishAppLifecycleWnfStateIfNecessary@StoreEventListenerImpl@@AEAAXPEBG0AEBU_WNF_STATE_NAME@@@Z; StoreEventListenerImpl::PublishAppLifecycleWnfStateIfNecessary(ushort const *,ushort const *,_WNF_STATE_NAME const &)
0x1800f9ba6  lea     rcx, [rsp+1D8h+var_178]
0x1800f9bab  call    ?Stop@?$ActivityBase@VStartLayoutTelemetryLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<StartLayoutTelemetryLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800f9bb0  nop
0x1800f9bb1  lea     rcx, [rsp+1D8h+var_178]; this
0x1800f9bb6  call    ??1AppInstallOnProgressActivity@StartPlaceHolderTelemetry@@QEAA@XZ; StartPlaceHolderTelemetry::AppInstallOnProgressActivity::~AppInstallOnProgressActivity(void)
0x1800f9bbb  nop
0x1800f9bbc  mov     rcx, [rsp+1D8h+string]; string
0x1800f9bc1  call    cs:__imp_WindowsDeleteString
0x1800f9bc7  mov     [rsp+1D8h+string], r14
0x1800f9bcc  mov     rcx, [rsp+1D8h+var_1B0]; string
0x1800f9bd1  call    cs:__imp_WindowsDeleteString
0x1800f9bd7  jmp     loc_1800F99C8
0x1800f9bdc  mov     byte ptr [rsp+1D8h+var_1B8], r14b; int
0x1800f9be1  lea     r9, [rsp+1D8h+var_1B8]
0x1800f9be6  xor     r8d, r8d
0x1800f9be9  mov     rdx, [rsp+1D8h+var_1B0]
0x1800f9bee  mov     rcx, [rsi+38h]
0x1800f9bf2  call    ?Insert@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$HashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@4567@@Internal@Collections@Foundation@Windows@@UEAAJPEAUHSTRING__@@PEAUIInspectable@@PEAE@Z; Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::Insert(HSTRING__ *,IInspectable *,uchar *)
0x1800f9bf7  mov     rcx, [rsp+1D8h]; this
0x1800f9bff  test    eax, eax
0x1800f9c01  jns     loc_1800F9AFF
0x1800f9c07  mov     r9d, eax; char *
0x1800f9c0a  lea     r8, aShellcommonShe_106; "shellcommon\\shell\\tiles\\curatedtilec"...
0x1800f9c11  mov     edx, 9Eh; void *
0x1800f9c16  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800f9c1b  jmp     loc_1800F9AFF
0x1800f9c20  mov     eax, [rsp+1D8h+var_1A0]
0x1800f9c24  cmp     eax, 0Ch
0x1800f9c27  ja      loc_1800F99C8
0x1800f9c2d  mov     ecx, 11C1h
0x1800f9c32  bt      ecx, eax
0x1800f9c35  jnb     loc_1800F99C8
0x1800f9c3b  mov     [rsp+1D8h+var_1B0], r14
0x1800f9c40  mov     rdi, [rsp+1D8h+var_1A8]
0x1800f9c45  mov     rax, [rdi]
0x1800f9c48  mov     rbx, [rax+30h]
0x1800f9c4c  xor     ecx, ecx; string
0x1800f9c4e  call    cs:__imp_WindowsDeleteString
0x1800f9c54  mov     [rsp+1D8h+var_1B0], r14
0x1800f9c59  lea     rdx, [rsp+1D8h+var_1B0]
0x1800f9c5e  mov     rcx, rdi
0x1800f9c61  mov     rax, rbx
0x1800f9c64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f9c69  mov     ebx, eax
0x1800f9c6b  test    eax, eax
0x1800f9c6d  jns     short loc_1800F9CAD
0x1800f9c6f  mov     rcx, [rsp+1D8h]; this
0x1800f9c77  mov     r9d, eax; char *
0x1800f9c7a  lea     r8, aShellcommonShe_106; "shellcommon\\shell\\tiles\\curatedtilec"...
0x1800f9c81  mov     edx, 89h; void *
0x1800f9c86  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f9c8b  nop
0x1800f9c8c  mov     rcx, [rsp+1D8h+var_1B0]; string
0x1800f9c91  call    cs:__imp_WindowsDeleteString
0x1800f9c97  mov     [rsp+1D8h+var_1B0], r14
0x1800f9c9c  lea     rcx, [rsp+1D8h+var_1A8]; void *
0x1800f9ca1  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x1800f9ca6  mov     eax, ebx
0x1800f9ca8  jmp     loc_1800F99E1
0x1800f9cad  mov     [rsp+1D8h+string], r14
0x1800f9cb2  mov     rdi, [rsp+1D8h+var_1A8]
0x1800f9cb7  mov     rax, [rdi]
0x1800f9cba  mov     rbx, [rax+70h]
0x1800f9cbe  xor     ecx, ecx; string
0x1800f9cc0  call    cs:__imp_WindowsDeleteString
0x1800f9cc6  mov     [rsp+1D8h+string], r14
0x1800f9ccb  lea     rdx, [rsp+1D8h+string]
0x1800f9cd0  mov     rcx, rdi
0x1800f9cd3  mov     rax, rbx
0x1800f9cd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f9cdb  mov     ebx, eax
0x1800f9cdd  test    eax, eax
0x1800f9cdf  jns     short loc_1800F9D2F
0x1800f9ce1  mov     rcx, [rsp+1D8h]; this
0x1800f9ce9  mov     r9d, eax; char *
0x1800f9cec  lea     r8, aShellcommonShe_106; "shellcommon\\shell\\tiles\\curatedtilec"...
0x1800f9cf3  mov     edx, 8Eh; void *
0x1800f9cf8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f9cfd  nop
0x1800f9cfe  mov     rcx, [rsp+1D8h+string]; string
0x1800f9d03  call    cs:__imp_WindowsDeleteString
0x1800f9d09  mov     [rsp+1D8h+string], r14
0x1800f9d0e  mov     rcx, [rsp+1D8h+var_1B0]; string
0x1800f9d13  call    cs:__imp_WindowsDeleteString
0x1800f9d19  mov     [rsp+1D8h+var_1B0], r14
0x1800f9d1e  lea     rcx, [rsp+1D8h+var_1A8]; void *
0x1800f9d23  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x1800f9d28  mov     eax, ebx
0x1800f9d2a  jmp     loc_1800F99E1
0x1800f9d2f  lea     rdx, aAppinstallonpr; "AppInstallOnProgressActivity"
0x1800f9d36  lea     rcx, [rsp+1D8h+var_178]; struct wil::details::IFailureCallback *
0x1800f9d3b  call    ??0?$ActivityBase@VStartLayoutTelemetryLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<StartLayoutTelemetryLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<StartLayoutTelemetryLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800f9d40  lea     rax, ??_7AppInstallOnProgressActivity@StartPlaceHolderTelemetry@@6B@; const StartPlaceHolderTelemetry::AppInstallOnProgressActivity::`vftable'
0x1800f9d47  mov     [rsp+1D8h+var_178], rax
0x1800f9d4c  lea     rcx, [rsp+1D8h+var_178]; this
0x1800f9d51  call    ?StartActivity@AppInstallOnProgressActivity@StartPlaceHolderTelemetry@@QEAAXXZ; StartPlaceHolderTelemetry::AppInstallOnProgressActivity::StartActivity(void)
0x1800f9d56  nop
0x1800f9d57  xor     edx, edx; length
0x1800f9d59  mov     rcx, [rsp+1D8h+string]; string
0x1800f9d5e  call    cs:__imp_WindowsGetStringRawBuffer
0x1800f9d64  mov     [rsp+1D8h+var_190], rax
0x1800f9d69  lea     r8, [rsp+1D8h+var_1A0]
0x1800f9d6e  lea     rdx, [rsp+1D8h+var_190]
0x1800f9d73  lea     rcx, [rsp+1D8h+var_178]
0x1800f9d78  call    ??$LogState@PEBGAEAW4InstallState@Internal@WindowsUpdate@@@AppInstallOnProgressActivity@StartPlaceHolderTelemetry@@QEAAX$$QEAPEBGAEAW4InstallState@Internal@WindowsUpdate@@@Z; StartPlaceHolderTelemetry::AppInstallOnProgressActivity::LogState<ushort const *,WindowsUpdate::Internal::InstallState &>(ushort const * &&,WindowsUpdate::Internal::InstallState &)
0x1800f9d7d  test    cs:Microsoft_Windows_ShellCommon_StartLayoutPopulationEnableBits, 1
0x1800f9d84  jz      loc_1800F9AA9
0x1800f9d8a  mov     ebx, [rsp+1D8h+var_1A0]
0x1800f9d8e  xor     edx, edx; length
0x1800f9d90  mov     rcx, [rsp+1D8h+string]; string
0x1800f9d95  call    cs:__imp_WindowsGetStringRawBuffer
0x1800f9d9b  mov     r9d, ebx
0x1800f9d9e  mov     r8, rax
0x1800f9da1  lea     rdx, InstallOnProgress
0x1800f9da8  lea     rcx, Microsoft_Windows_StartLayoutPopulation_Provider_Context
0x1800f9daf  call    McTemplateU0zq_EventWriteTransfer
0x1800f9db4  jmp     loc_1800F9AA9
0x1800f9db9  lea     rcx, [rsp+1D8h+var_1A8]; void *
0x1800f9dbe  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x1800f9dc3  mov     eax, dword ptr [rsp+1D8h+var_1B0]
0x1800f9dc7  jmp     loc_1800F99E1
```
