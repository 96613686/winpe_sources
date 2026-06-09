# _anonymous_namespace_::TryGetHandlersFromAppExtension

- ea: `0x18002ee68`
- end: `0x18002f522`
- name: `_anonymous_namespace_::TryGetHandlersFromAppExtension`
- size: `1722`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `26`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000ee64`
- `0x1800346c0`

## callees

- `0x180004a54`
- `0x180006b1c`
- `0x18000ed50`
- `0x18000ff08`
- `0x180010934`
- `0x180010958`
- `0x180011054`
- `0x180016b38`
- `0x180018f2c`
- `0x180018fe0`
- `0x1800190fc`
- `0x18001d3e0`
- `0x18001f4bc`
- `0x180022648`
- `0x180027328`
- `0x1800273ac`
- `0x18002766c`
- `0x1800280d4`
- `0x18002ee68`
- `0x18002f528`
- `0x18002f54c`
- `0x18002f5b8`
- `0x18002f63c`
- `0x1800348e8`
- `0x180037780`
- `0x180038ad6`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002ef9c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002ef9c`
- `ext-ms-onecore-appmodel-staterepository-internal-l1-1-3!SRDictionaryToPropertySet` at `0x18002f097`
- `ext-ms-onecore-appmodel-staterepository-internal-l1-1-3!SRDictionaryToPropertySet` at `0x18002f097`

## string_xrefs

- `0x18002ef3a`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`
- `0x18002efad`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`
- `0x18002f0a8`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`
- `0x18002f1ac`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`
- `0x18002f28d`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`
- `0x18002f36e`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`
- `0x18002f463`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`
- `0x18002ef10`: `Windows.Internal.StateRepository.ApplicationExtension`
- `0x18002ef6e`: `Windows.Internal.StateRepository.AppExtension`
- `0x18002f020`: `com.microsoft.cloudfiles`
- `0x18002efce`: `windows.appExtension`
- `0x18002f3b2`: `StorageProviderShareLinkSource`

## pseudocode

```c
// Hidden C++ exception states: #wind=27
__int64 __fastcall anonymous_namespace_::TryGetHandlersFromAppExtension(
        __int64 a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5)
{
  int v9; // eax
  __int64 v10; // rbx
  int ActivationFactory; // eax
  unsigned int v12; // ebx
  int v13; // r15d
  struct IUnknown *v14; // rdx
  void **v15; // rax
  PVOID Reserved1; // rbx
  int v17; // eax
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  StateRepoHelpers *v21; // rax
  struct _GUID *v22; // r8
  int v23; // eax
  __int64 v24; // rax
  __int64 v25; // rax
  StateRepoHelpers *v26; // rax
  struct _GUID *v27; // r8
  int v28; // eax
  __int64 v29; // rax
  __int64 v30; // rax
  StateRepoHelpers *v31; // rax
  struct _GUID *v32; // r8
  int v33; // eax
  __int64 v34; // rax
  __int64 v35; // rax
  StateRepoHelpers *v36; // rax
  struct _GUID *v37; // r8
  int v38; // eax
  __int64 v40; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v41; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v42; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v43; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v44[8]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v45; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v46; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v47; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v48[8]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v49[8]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v50; // [rsp+70h] [rbp-90h] BYREF
  __int64 v51; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v52[8]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v53[8]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v54[32]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v55[32]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v56; // [rsp+D0h] [rbp-30h]
  _BYTE v57[32]; // [rsp+D8h] [rbp-28h] BYREF
  HSTRING_HEADER pv; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v59; // [rsp+110h] [rbp+10h]
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  v56 = a1;
  if ( a2 )
    *(GUID *)a2 = GUID_NULL;
  if ( a3 )
    *(GUID *)a3 = GUID_NULL;
  if ( a4 )
    *(GUID *)a4 = GUID_NULL;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SCFTest>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SCFTest>::GetImpl'::`2'::impl)
    && a5 )
  {
    *(GUID *)a5 = GUID_NULL;
  }
  v50 = 0;
  v59 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &pv,
    L"Windows.Internal.StateRepository.ApplicationExtension",
    0x36u,
    0x35u);
  v9 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>>(
         v59,
         &v50);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xC7,
      (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
      (const char *)(unsigned int)v9,
      v40);
  wil::convert_from_abi<winrt::Windows::Internal::StateRepository::IApplicationExtensionStatics>(v53, v50);
  v46 = 0;
  v59 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &pv,
    L"Windows.Internal.StateRepository.AppExtension",
    0x2Eu,
    0x2Du);
  v10 = v59;
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v46);
  ActivationFactory = RoGetActivationFactory(v10, &GUID_21374459_f51f_462a_a7c1_53b8c35dd20b, &v46);
  if ( ActivationFactory < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xCB,
      (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v40);
  wil::convert_from_abi<winrt::Windows::Internal::StateRepository::IAppExtensionStatics>(v52, v46);
  winrt::param::hstring::hstring((winrt::param::hstring *)&pv, L"windows.appExtension");
  winrt::impl::consume_Windows_Internal_StateRepository_IApplicationExtensionStatics<winrt::Windows::Internal::StateRepository::IApplicationExtensionStatics>::FindByApplicationAndCategory(
    v53,
    v49,
    a1,
    &pv);
  v12 = 0;
  v13 = winrt::impl::consume_Windows_Internal_IMicrosoftGraphRecentItemInfo<winrt::Windows::Internal::IMicrosoftGraphRecentItemInfo>::LocationOrigin(v49);
  while ( v12 != v13 )
  {
    winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::MicrosoftGraphRecentItemInfo>,winrt::Windows::Internal::MicrosoftGraphRecentItemInfo>::GetAt(
      v49,
      v48,
      v12);
    winrt::param::hstring::hstring((winrt::param::hstring *)v57, L"com.microsoft.cloudfiles");
    winrt::impl::consume_Windows_Internal_StateRepository_IAppExtensionStatics<winrt::Windows::Internal::StateRepository::IAppExtensionStatics>::TryGetByExtensionAndName(
      v52,
      &v45,
      v48,
      v57);
    if ( v45 )
    {
      winrt::impl::consume_Windows_Internal_StateRepository_IAppExtension<winrt::Windows::Internal::StateRepository::IAppExtension>::Get_Dictionary(
        &v45,
        &pv);
      v47 = 0;
      v15 = winrt::put_abi((winrt *)&v47, v14);
      Reserved1 = pv.Reserved.Reserved1;
      v17 = SRDictionaryToPropertySet(*(unsigned int *)&pv.Reserved.Reserved2[8], pv.Reserved.Reserved1, v15);
      if ( v17 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xD8,
          (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
          (const char *)(unsigned int)v17,
          v40);
      winrt::param::hstring::hstring((winrt::param::hstring *)v57, (const unsigned __int16 *const)&stru_180091600);
      v18 = winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(
              &v47,
              &v51,
              v57);
      winrt::Windows::Foundation::IUnknown::as<winrt::Windows::Foundation::Collections::IPropertySet>(v18, v44);
      if ( v51 )
        winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v51);
      if ( a2 )
      {
        winrt::param::hstring::hstring((winrt::param::hstring *)v54, L"HandlerFactory");
        v19 = winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(
                v44,
                &v40,
                v54);
        winrt::Windows::Foundation::IUnknown::as<winrt::Windows::Foundation::Collections::IPropertySet>(v19, &v43);
        if ( v40 )
          winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v40);
        winrt::param::hstring::hstring((winrt::param::hstring *)v55, (const unsigned __int16 *const)&stru_180092898);
        v20 = winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(
                &v43,
                &v41,
                v55);
        winrt::unbox_value<winrt::hstring>(&v42, v20);
        if ( v41 )
          winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v41);
        v21 = (StateRepoHelpers *)winrt::hstring::c_str((winrt::hstring *)&v42);
        v23 = StateRepoHelpers::ParseCLSID(v21, a2, v22);
        if ( v23 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xDF,
            (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
            (const char *)(unsigned int)v23,
            v40);
        winrt::handle_type<winrt::impl::hstring_traits>::close(&v42);
        winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Internal::Storage::PerFolderRootInfo>::~IIterator<winrt::Windows::Internal::Storage::PerFolderRootInfo>(&v43);
      }
      if ( a3 )
      {
        winrt::param::hstring::hstring((winrt::param::hstring *)v55, L"PropertyHandler");
        v24 = winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::TryLookup(
                v44,
                &v43,
                v55);
        winrt::Windows::Foundation::IUnknown::as<winrt::Windows::Foundation::Collections::IPropertySet>(v24, &v40);
        if ( v43 )
          winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v43);
        if ( v40 )
        {
          winrt::param::hstring::hstring((winrt::param::hstring *)v54, (const unsigned __int16 *const)&stru_180092898);
          v25 = winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(
                  &v40,
                  &v42,
                  v54);
          winrt::unbox_value<winrt::hstring>(&v41, v25);
          if ( v42 )
            winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v42);
          v26 = (StateRepoHelpers *)winrt::hstring::c_str((winrt::hstring *)&v41);
          v28 = StateRepoHelpers::ParseCLSID(v26, a3, v27);
          if ( v28 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0xE8,
              (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
              (const char *)(unsigned int)v28,
              v40);
          winrt::handle_type<winrt::impl::hstring_traits>::close(&v41);
        }
        winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Internal::Storage::PerFolderRootInfo>::~IIterator<winrt::Windows::Internal::Storage::PerFolderRootInfo>(&v40);
      }
      if ( a4 )
      {
        winrt::param::hstring::hstring((winrt::param::hstring *)v55, L"StorageProviderStatusUISourceFactory");
        v29 = winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::TryLookup(
                v44,
                &v43,
                v55);
        winrt::Windows::Foundation::IUnknown::as<winrt::Windows::Foundation::Collections::IPropertySet>(v29, &v40);
        if ( v43 )
          winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v43);
        if ( v40 )
        {
          winrt::param::hstring::hstring((winrt::param::hstring *)v54, (const unsigned __int16 *const)&stru_180092898);
          v30 = winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(
                  &v40,
                  &v42,
                  v54);
          winrt::unbox_value<winrt::hstring>(&v41, v30);
          if ( v42 )
            winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v42);
          v31 = (StateRepoHelpers *)winrt::hstring::c_str((winrt::hstring *)&v41);
          v33 = StateRepoHelpers::ParseCLSID(v31, a4, v32);
          if ( v33 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0xF2,
              (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
              (const char *)(unsigned int)v33,
              v40);
          winrt::handle_type<winrt::impl::hstring_traits>::close(&v41);
        }
        winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Internal::Storage::PerFolderRootInfo>::~IIterator<winrt::Windows::Internal::Storage::PerFolderRootInfo>(&v40);
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SCFTest>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SCFTest>::GetImpl'::`2'::impl)
        && a5 )
      {
        winrt::param::hstring::hstring((winrt::param::hstring *)v55, L"StorageProviderShareLinkSource");
        v34 = winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::TryLookup(
                v44,
                &v43,
                v55);
        winrt::Windows::Foundation::IUnknown::as<winrt::Windows::Foundation::Collections::IPropertySet>(v34, &v40);
        if ( v43 )
          winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v43);
        if ( v40 )
        {
          winrt::param::hstring::hstring((winrt::param::hstring *)v54, (const unsigned __int16 *const)&stru_180092898);
          v35 = winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(
                  &v40,
                  &v42,
                  v54);
          winrt::unbox_value<winrt::hstring>(&v41, v35);
          if ( v42 )
            winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v42);
          v36 = (StateRepoHelpers *)winrt::hstring::c_str((winrt::hstring *)&v41);
          v38 = StateRepoHelpers::ParseCLSID(v36, a5, v37);
          if ( v38 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0xFE,
              (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
              (const char *)(unsigned int)v38,
              v40);
          winrt::handle_type<winrt::impl::hstring_traits>::close(&v41);
        }
        winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Internal::Storage::PerFolderRootInfo>::~IIterator<winrt::Windows::Internal::Storage::PerFolderRootInfo>(&v40);
      }
      winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Internal::Storage::PerFolderRootInfo>::~IIterator<winrt::Windows::Internal::Storage::PerFolderRootInfo>(v44);
      winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Internal::Storage::PerFolderRootInfo>::~IIterator<winrt::Windows::Internal::Storage::PerFolderRootInfo>(&v47);
      if ( Reserved1 )
        CoTaskMemFree_0(Reserved1);
      winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Internal::Storage::PerFolderRootInfo>::~IIterator<winrt::Windows::Internal::Storage::PerFolderRootInfo>(&v45);
      winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Internal::Storage::PerFolderRootInfo>::~IIterator<winrt::Windows::Internal::Storage::PerFolderRootInfo>(v48);
      break;
    }
    winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Internal::Storage::PerFolderRootInfo>::~IIterator<winrt::Windows::Internal::Storage::PerFolderRootInfo>(&v45);
    winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Internal::Storage::PerFolderRootInfo>::~IIterator<winrt::Windows::Internal::Storage::PerFolderRootInfo>(v48);
    ++v12;
  }
  winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Internal::Storage::PerFolderRootInfo>::~IIterator<winrt::Windows::Internal::Storage::PerFolderRootInfo>(v49);
  winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Internal::Storage::PerFolderRootInfo>::~IIterator<winrt::Windows::Internal::Storage::PerFolderRootInfo>(v52);
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v46);
  winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Internal::Storage::PerFolderRootInfo>::~IIterator<winrt::Windows::Internal::Storage::PerFolderRootInfo>(v53);
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v50);
  return winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Internal::Storage::PerFolderRootInfo>::~IIterator<winrt::Windows::Internal::Storage::PerFolderRootInfo>(a1);
}

```

## disassembly

```asm
0x18002ee68  push    rbp
0x18002ee6a  push    rbx
0x18002ee6b  push    rsi
0x18002ee6c  push    rdi
0x18002ee6d  push    r12
0x18002ee6f  push    r13
0x18002ee71  push    r14
0x18002ee73  push    r15
0x18002ee75  lea     rbp, [rsp-28h]
0x18002ee7a  sub     rsp, 128h
0x18002ee81  mov     rax, cs:__security_cookie
0x18002ee88  xor     rax, rsp
0x18002ee8b  mov     [rbp+60h+var_48], rax
0x18002ee8f  mov     r14, r9
0x18002ee92  mov     rsi, r8
0x18002ee95  mov     rdi, rdx
0x18002ee98  mov     r13, rcx
0x18002ee9b  mov     [rbp+60h+var_90], rcx
0x18002ee9f  mov     r12, [rbp+60h+arg_20]
0x18002eea6  xor     r15d, r15d
0x18002eea9  test    rdx, rdx
0x18002eeac  jz      short loc_18002EEB9
0x18002eeae  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18002eeb5  movdqu  xmmword ptr [rdx], xmm0
0x18002eeb9  test    rsi, rsi
0x18002eebc  jz      short loc_18002EECA
0x18002eebe  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18002eec5  movdqu  xmmword ptr [r8], xmm0
0x18002eeca  test    r14, r14
0x18002eecd  jz      short loc_18002EEDB
0x18002eecf  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18002eed6  movdqu  xmmword ptr [r9], xmm0
0x18002eedb  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SCFTest@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SCFTest@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SCFTest> `wil::Feature<__WilFeatureTraits_Feature_SCFTest>::GetImpl(void)'::`2'::impl
0x18002eee2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SCFTest@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SCFTest>::__private_IsEnabled(void)
0x18002eee7  test    al, al
0x18002eee9  jz      short loc_18002EEFD
0x18002eeeb  test    r12, r12
0x18002eeee  jz      short loc_18002EEFD
0x18002eef0  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18002eef7  movdqu  xmmword ptr [r12], xmm0
0x18002eefd  mov     [rsp+160h+var_F0], r15
0x18002ef02  mov     [rbp+60h+var_50], r15
0x18002ef06  mov     r9d, 35h ; '5'; unsigned int
0x18002ef0c  lea     r8d, [r9+1]; unsigned int
0x18002ef10  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_ApplicationExtension@@3QBGB; "Windows.Internal.StateRepository.Applic"...
0x18002ef17  lea     rcx, [rbp+60h+pv]; hstringHeader
0x18002ef1b  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18002ef20  nop
0x18002ef21  lea     rdx, [rsp+160h+var_F0]
0x18002ef26  mov     rcx, [rbp+60h+var_50]
0x18002ef2a  call    ??$GetActivationFactory@V?$ComPtr@UIApplicationExtensionStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIApplicationExtensionStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>>)
0x18002ef2f  mov     rcx, [rbp+68h]; this
0x18002ef33  test    eax, eax
0x18002ef35  jns     short loc_18002EF4C
0x18002ef37  mov     r9d, eax; char *
0x18002ef3a  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\fileexplorer\\windo"...
0x18002ef41  mov     edx, 0C7h; void *
0x18002ef46  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002ef4c  mov     rdx, [rsp+160h+var_F0]
0x18002ef51  lea     rcx, [rbp+60h+var_D8]
0x18002ef55  call    ??$convert_from_abi@UIApplicationExtensionStatics@StateRepository@Internal@Windows@winrt@@@wil@@YA?AUIApplicationExtensionStatics@StateRepository@Internal@Windows@winrt@@PEAUIUnknown@@@Z; wil::convert_from_abi<winrt::Windows::Internal::StateRepository::IApplicationExtensionStatics>(IUnknown *)
0x18002ef5a  nop
0x18002ef5b  mov     [rsp+160h+var_110], r15
0x18002ef60  mov     [rbp+60h+var_50], r15
0x18002ef64  mov     r9d, 2Dh ; '-'; unsigned int
0x18002ef6a  lea     r8d, [r9+1]; unsigned int
0x18002ef6e  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_AppExtension@@3QBGB; "Windows.Internal.StateRepository.AppExt"...
0x18002ef75  lea     rcx, [rbp+60h+pv]; hstringHeader
0x18002ef79  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18002ef7e  nop
0x18002ef7f  mov     rbx, [rbp+60h+var_50]
0x18002ef83  lea     rcx, [rsp+160h+var_110]
0x18002ef88  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18002ef8d  lea     r8, [rsp+160h+var_110]
0x18002ef92  lea     rdx, _GUID_21374459_f51f_462a_a7c1_53b8c35dd20b
0x18002ef99  mov     rcx, rbx
0x18002ef9c  call    cs:__imp_RoGetActivationFactory
0x18002efa2  mov     rcx, [rbp+68h]; this
0x18002efa6  test    eax, eax
0x18002efa8  jns     short loc_18002EFBF
0x18002efaa  mov     r9d, eax; char *
0x18002efad  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\fileexplorer\\windo"...
0x18002efb4  mov     edx, 0CBh; void *
0x18002efb9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002efbf  mov     rdx, [rsp+160h+var_110]
0x18002efc4  lea     rcx, [rbp+60h+var_E0]
0x18002efc8  call    ??$convert_from_abi@UIAppExtensionStatics@StateRepository@Internal@Windows@winrt@@@wil@@YA?AUIAppExtensionStatics@StateRepository@Internal@Windows@winrt@@PEAUIUnknown@@@Z; wil::convert_from_abi<winrt::Windows::Internal::StateRepository::IAppExtensionStatics>(IUnknown *)
0x18002efcd  nop
0x18002efce  lea     rdx, aWindowsAppexte; "windows.appExtension"
0x18002efd5  lea     rcx, [rbp+60h+pv]; this
0x18002efd9  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18002efde  lea     r9, [rbp+60h+pv]
0x18002efe2  mov     r8, r13
0x18002efe5  lea     rdx, [rsp+160h+var_F8]
0x18002efea  lea     rcx, [rbp+60h+var_D8]
0x18002efee  call    ?FindByApplicationAndCategory@?$consume_Windows_Internal_StateRepository_IApplicationExtensionStatics@UIApplicationExtensionStatics@StateRepository@Internal@Windows@winrt@@@impl@winrt@@QEBA@AEBUApplication@StateRepository@Internal@Windows@3@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Internal_StateRepository_IApplicationExtensionStatics<winrt::Windows::Internal::StateRepository::IApplicationExtensionStatics>::FindByApplicationAndCategory(winrt::Windows::Internal::StateRepository::Application const &,winrt::param::hstring const &)
0x18002eff3  nop
0x18002eff4  mov     ebx, r15d
0x18002eff7  lea     rcx, [rsp+160h+var_F8]
0x18002effc  call    ?LocationOrigin@?$consume_Windows_Internal_IMicrosoftGraphRecentItemInfo@UIMicrosoftGraphRecentItemInfo@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_IMicrosoftGraphRecentItemInfo<winrt::Windows::Internal::IMicrosoftGraphRecentItemInfo>::LocationOrigin(void)
0x18002f001  mov     r15d, eax
0x18002f004  cmp     ebx, r15d
0x18002f007  jz      loc_18002F4C5
0x18002f00d  mov     r8d, ebx
0x18002f010  lea     rdx, [rsp+160h+var_100]
0x18002f015  lea     rcx, [rsp+160h+var_F8]
0x18002f01a  call    ?GetAt@?$consume_Windows_Foundation_Collections_IVectorView@U?$IVectorView@UMicrosoftGraphRecentItemInfo@Internal@Windows@winrt@@@Collections@Foundation@Windows@winrt@@UMicrosoftGraphRecentItemInfo@Internal@45@@impl@winrt@@QEBA@I@Z; winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::MicrosoftGraphRecentItemInfo>,winrt::Windows::Internal::MicrosoftGraphRecentItemInfo>::GetAt(uint)
0x18002f01f  nop
0x18002f020  lea     rdx, aComMicrosoftCl; "com.microsoft.cloudfiles"
0x18002f027  lea     rcx, [rbp+60h+var_88]; this
0x18002f02b  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18002f030  lea     r9, [rbp+60h+var_88]
0x18002f034  lea     r8, [rsp+160h+var_100]
0x18002f039  lea     rdx, [rsp+160h+var_118]
0x18002f03e  lea     rcx, [rbp+60h+var_E0]
0x18002f042  call    ?TryGetByExtensionAndName@?$consume_Windows_Internal_StateRepository_IAppExtensionStatics@UIAppExtensionStatics@StateRepository@Internal@Windows@winrt@@@impl@winrt@@QEBA@AEBUApplicationExtension@StateRepository@Internal@Windows@3@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Internal_StateRepository_IAppExtensionStatics<winrt::Windows::Internal::StateRepository::IAppExtensionStatics>::TryGetByExtensionAndName(winrt::Windows::Internal::StateRepository::ApplicationExtension const &,winrt::param::hstring const &)
0x18002f047  nop
0x18002f048  cmp     [rsp+160h+var_118], 0
0x18002f04e  jnz     short loc_18002F069
0x18002f050  lea     rcx, [rsp+160h+var_118]
0x18002f055  call    ??1?$IIterator@UPerFolderRootInfo@Storage@Internal@Windows@winrt@@@Collections@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Internal::Storage::PerFolderRootInfo>::~IIterator<winrt::Windows::Internal::Storage::PerFolderRootInfo>(void)
0x18002f05a  nop
0x18002f05b  lea     rcx, [rsp+160h+var_100]
0x18002f060  call    ??1?$IIterator@UPerFolderRootInfo@Storage@Internal@Windows@winrt@@@Collections@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Internal::Storage::PerFolderRootInfo>::~IIterator<winrt::Windows::Internal::Storage::PerFolderRootInfo>(void)
0x18002f065  inc     ebx
0x18002f067  jmp     short loc_18002F004
0x18002f069  lea     rdx, [rbp+60h+pv]
0x18002f06d  lea     rcx, [rsp+160h+var_118]
0x18002f072  call    ?Get_Dictionary@?$consume_Windows_Internal_StateRepository_IAppExtension@UIAppExtension@StateRepository@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_StateRepository_IAppExtension<winrt::Windows::Internal::StateRepository::IAppExtension>::Get_Dictionary(void)
0x18002f077  nop
0x18002f078  xor     r15d, r15d
0x18002f07b  mov     [rsp+160h+var_108], r15
0x18002f080  lea     rcx, [rsp+160h+var_108]; this
0x18002f085  call    ?put_abi@winrt@@YAPEAPEAXAEAUIUnknown@Foundation@Windows@1@@Z; winrt::put_abi(winrt::Windows::Foundation::IUnknown &)
0x18002f08a  mov     r8, rax
0x18002f08d  mov     rbx, [rbp+60h+pv]
0x18002f091  mov     rdx, rbx
0x18002f094  mov     ecx, [rbp+60h+var_60]
0x18002f097  call    cs:__imp_SRDictionaryToPropertySet
0x18002f09d  mov     rcx, [rbp+68h]; this
0x18002f0a1  test    eax, eax
0x18002f0a3  jns     short loc_18002F0BA
0x18002f0a5  mov     r9d, eax; char *
0x18002f0a8  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\fileexplorer\\windo"...
0x18002f0af  mov     edx, 0D8h; void *
0x18002f0b4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002f0ba  lea     rdx, stru_180091600; unsigned __int16 *
0x18002f0c1  lea     rcx, [rbp+60h+var_88]; this
0x18002f0c5  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18002f0ca  lea     r8, [rbp+60h+var_88]
0x18002f0ce  lea     rdx, [rsp+160h+var_E8]
0x18002f0d3  lea     rcx, [rsp+160h+var_108]
0x18002f0d8  call    ?Lookup@?$consume_Windows_Foundation_Collections_IMap@UIPropertySet@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(winrt::param::hstring const &)
0x18002f0dd  nop
0x18002f0de  lea     rdx, [rsp+160h+var_120]
0x18002f0e3  mov     rcx, rax
0x18002f0e6  call    ??$as@UIPropertySet@Collections@Foundation@Windows@winrt@@@IUnknown@Foundation@Windows@winrt@@QEBA?A_PXZ
0x18002f0eb  nop
0x18002f0ec  cmp     [rsp+160h+var_E8], r15
0x18002f0f1  jz      short loc_18002F0FD
0x18002f0f3  lea     rcx, [rsp+160h+var_E8]
0x18002f0f8  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x18002f0fd  test    rdi, rdi
0x18002f100  jz      loc_18002F1D3
0x18002f106  lea     rdx, aHandlerfactory_0; "HandlerFactory"
0x18002f10d  lea     rcx, [rbp+60h+var_D0]; this
0x18002f111  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18002f116  lea     r8, [rbp+60h+var_D0]
0x18002f11a  lea     rdx, [rsp+160h+var_140]
0x18002f11f  lea     rcx, [rsp+160h+var_120]
0x18002f124  call    ?Lookup@?$consume_Windows_Foundation_Collections_IMap@UIPropertySet@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(winrt::param::hstring const &)
0x18002f129  nop
0x18002f12a  lea     rdx, [rsp+160h+var_128]
0x18002f12f  mov     rcx, rax
0x18002f132  call    ??$as@UIPropertySet@Collections@Foundation@Windows@winrt@@@IUnknown@Foundation@Windows@winrt@@QEBA?A_PXZ
0x18002f137  nop
0x18002f138  cmp     [rsp+160h+var_140], r15
0x18002f13d  jz      short loc_18002F149
0x18002f13f  lea     rcx, [rsp+160h+var_140]
0x18002f144  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x18002f149  lea     rdx, stru_180092898; unsigned __int16 *
0x18002f150  lea     rcx, [rbp+60h+var_B0]; this
0x18002f154  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18002f159  lea     r8, [rbp+60h+var_B0]
0x18002f15d  lea     rdx, [rsp+160h+var_138]
0x18002f162  lea     rcx, [rsp+160h+var_128]
0x18002f167  call    ?Lookup@?$consume_Windows_Foundation_Collections_IMap@UIPropertySet@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(winrt::param::hstring const &)
0x18002f16c  nop
0x18002f16d  mov     rdx, rax
0x18002f170  lea     rcx, [rsp+160h+var_130]
0x18002f175  call    ??$unbox_value@Uhstring@winrt@@@winrt@@YA?AUhstring@0@AEBUIInspectable@Foundation@Windows@0@@Z; winrt::unbox_value<winrt::hstring>(winrt::Windows::Foundation::IInspectable const &)
0x18002f17a  nop
0x18002f17b  cmp     [rsp+160h+var_138], r15
0x18002f180  jz      short loc_18002F18C
0x18002f182  lea     rcx, [rsp+160h+var_138]
0x18002f187  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x18002f18c  lea     rcx, [rsp+160h+var_130]; this
0x18002f191  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18002f196  mov     rcx, rax; this
0x18002f199  mov     rdx, rdi; unsigned __int16 *
0x18002f19c  call    ?ParseCLSID@StateRepoHelpers@@YAJPEBGPEAU_GUID@@@Z; StateRepoHelpers::ParseCLSID(ushort const *,_GUID *)
0x18002f1a1  mov     rcx, [rbp+68h]; this
0x18002f1a5  test    eax, eax
0x18002f1a7  jns     short loc_18002F1BE
0x18002f1a9  mov     r9d, eax; char *
0x18002f1ac  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\fileexplorer\\windo"...
0x18002f1b3  mov     edx, 0DFh; void *
0x18002f1b8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002f1be  lea     rcx, [rsp+160h+var_130]
0x18002f1c3  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18002f1c8  nop
0x18002f1c9  lea     rcx, [rsp+160h+var_128]
0x18002f1ce  call    ??1?$IIterator@UPerFolderRootInfo@Storage@Internal@Windows@winrt@@@Collections@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Internal::Storage::PerFolderRootInfo>::~IIterator<winrt::Windows::Internal::Storage::PerFolderRootInfo>(void)
0x18002f1d3  test    rsi, rsi
0x18002f1d6  jz      loc_18002F2B4
0x18002f1dc  lea     rdx, aPropertyhandle; "PropertyHandler"
0x18002f1e3  lea     rcx, [rbp+60h+var_B0]; this
0x18002f1e7  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18002f1ec  lea     r8, [rbp+60h+var_B0]
0x18002f1f0  lea     rdx, [rsp+160h+var_128]
0x18002f1f5  lea     rcx, [rsp+160h+var_120]
0x18002f1fa  call    ?TryLookup@?$consume_Windows_Foundation_Collections_IMap@UIPropertySet@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::TryLookup(winrt::param::hstring const &)
0x18002f1ff  nop
0x18002f200  lea     rdx, [rsp+160h+var_140]
0x18002f205  mov     rcx, rax
0x18002f208  call    ??$as@UIPropertySet@Collections@Foundation@Windows@winrt@@@IUnknown@Foundation@Windows@winrt@@QEBA?A_PXZ
0x18002f20d  nop
0x18002f20e  cmp     [rsp+160h+var_128], r15
0x18002f213  jz      short loc_18002F21F
0x18002f215  lea     rcx, [rsp+160h+var_128]
0x18002f21a  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x18002f21f  cmp     [rsp+160h+var_140], r15
0x18002f224  jz      loc_18002F2AA
0x18002f22a  lea     rdx, stru_180092898; unsigned __int16 *
0x18002f231  lea     rcx, [rbp+60h+var_D0]; this
0x18002f235  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18002f23a  lea     r8, [rbp+60h+var_D0]
0x18002f23e  lea     rdx, [rsp+160h+var_130]
0x18002f243  lea     rcx, [rsp+160h+var_140]
0x18002f248  call    ?Lookup@?$consume_Windows_Foundation_Collections_IMap@UIPropertySet@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(winrt::param::hstring const &)
0x18002f24d  nop
0x18002f24e  mov     rdx, rax
0x18002f251  lea     rcx, [rsp+160h+var_138]
0x18002f256  call    ??$unbox_value@Uhstring@winrt@@@winrt@@YA?AUhstring@0@AEBUIInspectable@Foundation@Windows@0@@Z; winrt::unbox_value<winrt::hstring>(winrt::Windows::Foundation::IInspectable const &)
0x18002f25b  nop
0x18002f25c  cmp     [rsp+160h+var_130], r15
0x18002f261  jz      short loc_18002F26D
0x18002f263  lea     rcx, [rsp+160h+var_130]
0x18002f268  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x18002f26d  lea     rcx, [rsp+160h+var_138]; this
0x18002f272  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18002f277  mov     rcx, rax; this
0x18002f27a  mov     rdx, rsi; unsigned __int16 *
0x18002f27d  call    ?ParseCLSID@StateRepoHelpers@@YAJPEBGPEAU_GUID@@@Z; StateRepoHelpers::ParseCLSID(ushort const *,_GUID *)
0x18002f282  mov     rcx, [rbp+68h]; this
0x18002f286  test    eax, eax
0x18002f288  jns     short loc_18002F29F
0x18002f28a  mov     r9d, eax; char *
0x18002f28d  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\fileexplorer\\windo"...
0x18002f294  mov     edx, 0E8h; void *
0x18002f299  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002f29f  lea     rcx, [rsp+160h+var_138]
0x18002f2a4  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18002f2a9  nop
0x18002f2aa  lea     rcx, [rsp+160h+var_140]
0x18002f2af  call    ??1?$IIterator@UPerFolderRootInfo@Storage@Internal@Windows@winrt@@@Collections@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Internal::Storage::PerFolderRootInfo>::~IIterator<winrt::Windows::Internal::Storage::PerFolderRootInfo>(void)
0x18002f2b4  test    r14, r14
0x18002f2b7  jz      loc_18002F395
0x18002f2bd  lea     rdx, aStorageprovide_2; "StorageProviderStatusUISourceFactory"
0x18002f2c4  lea     rcx, [rbp+60h+var_B0]; this
0x18002f2c8  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18002f2cd  lea     r8, [rbp+60h+var_B0]
0x18002f2d1  lea     rdx, [rsp+160h+var_128]
0x18002f2d6  lea     rcx, [rsp+160h+var_120]
0x18002f2db  call    ?TryLookup@?$consume_Windows_Foundation_Collections_IMap@UIPropertySet@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::TryLookup(winrt::param::hstring const &)
0x18002f2e0  nop
0x18002f2e1  lea     rdx, [rsp+160h+var_140]
0x18002f2e6  mov     rcx, rax
0x18002f2e9  call    ??$as@UIPropertySet@Collections@Foundation@Windows@winrt@@@IUnknown@Foundation@Windows@winrt@@QEBA?A_PXZ
0x18002f2ee  nop
0x18002f2ef  cmp     [rsp+160h+var_128], r15
0x18002f2f4  jz      short loc_18002F300
0x18002f2f6  lea     rcx, [rsp+160h+var_128]
0x18002f2fb  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x18002f300  cmp     [rsp+160h+var_140], r15
0x18002f305  jz      loc_18002F38B
0x18002f30b  lea     rdx, stru_180092898; unsigned __int16 *
0x18002f312  lea     rcx, [rbp+60h+var_D0]; this
0x18002f316  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18002f31b  lea     r8, [rbp+60h+var_D0]
0x18002f31f  lea     rdx, [rsp+160h+var_130]
0x18002f324  lea     rcx, [rsp+160h+var_140]
0x18002f329  call    ?Lookup@?$consume_Windows_Foundation_Collections_IMap@UIPropertySet@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(winrt::param::hstring const &)
0x18002f32e  nop
0x18002f32f  mov     rdx, rax
0x18002f332  lea     rcx, [rsp+160h+var_138]
0x18002f337  call    ??$unbox_value@Uhstring@winrt@@@winrt@@YA?AUhstring@0@AEBUIInspectable@Foundation@Windows@0@@Z; winrt::unbox_value<winrt::hstring>(winrt::Windows::Foundation::IInspectable const &)
0x18002f33c  nop
0x18002f33d  cmp     [rsp+160h+var_130], r15
0x18002f342  jz      short loc_18002F34E
  ... truncated ...
```
