# Windows::Internal::Storage::Cloud::CloudStore::OldLoad(Windows::Internal::Storage::Cloud::PartitionKind,HSTRING__ *,HSTRING__ *,HSTRING__ *,Windows::Internal::Storage::Cloud::LoadOptions,Windows::Internal::Storage::Cloud::ICloudStoreData * *)

- ea: `0x18005c204`
- end: `0x18005ceaf`
- name: `?OldLoad@CloudStore@Cloud@Storage@Internal@Windows@@QEAAJW4PartitionKind@2345@PEAUHSTRING__@@11W4LoadOptions@2345@PEAPEAUICloudStoreData@2345@@Z`
- size: `3243`
- prototype: `int __high(enum Windows::Internal::Storage::Cloud::PartitionKind, HSTRING, HSTRING, HSTRING, enum Windows::Internal::Storage::Cloud::LoadOptions, struct Windows::Internal::Storage::Cloud::ICloudStoreData **)`
- caller_count: `1`
- callee_count: `36`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180086f00`

## callees

- `0x18000f4b4`
- `0x180010688`
- `0x1800122f4`
- `0x180012630`
- `0x18001c620`
- `0x180021f40`
- `0x180023fd4`
- `0x180024020`
- `0x1800250e0`
- `0x180025508`
- `0x18002570c`
- `0x18005a524`
- `0x18005ba64`
- `0x18005bf1c`
- `0x18005c204`
- `0x18005cec0`
- `0x18005d004`
- `0x18005d4b8`
- `0x18005d938`
- `0x18005de0c`
- `0x18005de38`
- `0x18005ded4`
- `0x18005e4a0`
- `0x1800ae89c`
- `0x1800c8458`
- `0x1800d1d50`
- `0x1800d6e40`
- `0x1800e93e0`
- `0x1800ff3e8`
- `0x1801201a0`
- `0x1801202a0`
- `0x180120c94`
- `0x1801236bc`
- `0x180123882`
- `0x180124088`
- `0x180208010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18005c44d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18005c44d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005cd4b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005cd4b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005c8d0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005ca84`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005cc6b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005c8d0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005ca84`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005cc6b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005c823`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005c864`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005c823`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005c864`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18005ce0b`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18005ce0b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005c4d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005c8c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005ca75`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005cc5c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005cd8a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005c4d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005c8c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005c999`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005ca75`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005cc08`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005cc5c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005cd8a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005c2a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005c2ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005c2bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005c432`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005c2a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005c2ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005c2bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005c432`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c3dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c8da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ca8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005cc75`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005cce5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005cda2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c3dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c8da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ca8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005cc75`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005cce5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005cda2`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall Windows::Internal::Storage::Cloud::CloudStore::OldLoad(
        __int64 a1,
        unsigned int a2,
        HSTRING a3,
        HSTRING a4,
        HSTRING string,
        unsigned int a6,
        struct Windows::Internal::Storage::Cloud::ICloudStoreData **a7)
{
  HSTRING v7; // r12
  char v10; // r15
  const char *v11; // r9
  const unsigned __int16 *StringRawBuffer; // r14
  const unsigned __int16 *v13; // rsi
  const unsigned __int16 *v14; // rdi
  int DataStoreId; // eax
  unsigned int v16; // ebx
  HSTRING v17; // rdi
  RTL_SRWLOCK *v18; // rbx
  RTL_SRWLOCK *v19; // r14
  int v20; // ebx
  void *v21; // rax
  __int64 (__fastcall ***v22)(struct Windows::Storage::Streams::IBuffer *, GUID *, std::_Ref_count_base ***); // rax
  int Instance; // eax
  unsigned int v24; // ebx
  __int64 (__fastcall ***v25)(struct Windows::Storage::Streams::IBuffer *, GUID *, std::_Ref_count_base ***); // rsi
  unsigned int v26; // r13d
  int v27; // eax
  __int64 (__fastcall *v28)(struct Windows::Storage::Streams::IBuffer *, GUID *, std::_Ref_count_base ***); // rbx
  int v29; // eax
  wil::details::in1diag3 *v30; // rcx
  _QWORD *v31; // rcx
  unsigned __int64 v32; // rbx
  PSRWLOCK v33; // r12
  __int64 v34; // r15
  __int64 v35; // rcx
  __int64 v36; // rcx
  const struct std::nothrow_t *v37; // rdx
  HSTRING v38; // rcx
  char v39; // r15
  _QWORD *v40; // rax
  RTL_SRWLOCK *v41; // rbx
  int *v42; // rcx
  int v43; // eax
  __int64 (__fastcall ***v44)(struct Windows::Storage::Streams::IBuffer *, GUID *, std::_Ref_count_base ***); // rcx
  void *v45; // rcx
  void *v46; // rdx
  const char *v47; // r9
  __int64 result; // rax
  LPVOID v49; // r12
  __int64 (__fastcall ***v50)(_QWORD, GUID *, _QWORD *); // rbx
  _QWORD *v51; // rsi
  unsigned int v52; // eax
  void (__stdcall *v53)(LPVOID); // rax
  int v54; // ebx
  __int64 (__fastcall ***v55)(struct Windows::Storage::Streams::IBuffer *, GUID *, std::_Ref_count_base ***); // rcx
  void *v56; // rcx
  void *v57; // rdx
  unsigned __int8 *v58; // rsi
  size_t v59; // rbx
  __int64 v60; // rdx
  int v61; // eax
  __int64 v62; // rbx
  unsigned __int8 **v63; // r8
  __int64 v64; // r8
  void **v65; // rax
  __int64 (__fastcall ***v66)(struct Windows::Storage::Streams::IBuffer *, GUID *, std::_Ref_count_base ***); // rcx
  void *v67; // rcx
  void *v68; // rdx
  void *v69; // rdx
  void *v70; // rcx
  __int64 v71; // rdx
  size_t v72; // rbx
  const struct wil::FailureInfo *v73; // rdx
  int v74; // [rsp+20h] [rbp-308h]
  int v75; // [rsp+20h] [rbp-308h]
  _QWORD *v76; // [rsp+40h] [rbp-2E8h] BYREF
  unsigned int v77; // [rsp+48h] [rbp-2E0h] BYREF
  __int64 (__fastcall ***v78)(struct Windows::Storage::Streams::IBuffer *, GUID *, std::_Ref_count_base ***); // [rsp+50h] [rbp-2D8h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-2D0h] BYREF
  unsigned int v80; // [rsp+60h] [rbp-2C8h] BYREF
  HSTRING v81; // [rsp+68h] [rbp-2C0h] BYREF
  HSTRING v82; // [rsp+70h] [rbp-2B8h] BYREF
  unsigned __int64 v83; // [rsp+78h] [rbp-2B0h] BYREF
  HANDLE hObject; // [rsp+80h] [rbp-2A8h] BYREF
  PSRWLOCK SRWLock; // [rsp+88h] [rbp-2A0h] BYREF
  HSTRING v86; // [rsp+90h] [rbp-298h]
  struct Windows::Internal::Storage::Cloud::ICloudStoreData **v87; // [rsp+98h] [rbp-290h] BYREF
  __int64 v88; // [rsp+A0h] [rbp-288h] BYREF
  HSTRING v89; // [rsp+A8h] [rbp-280h]
  unsigned __int8 *v90[2]; // [rsp+B0h] [rbp-278h] BYREF
  __int128 v91; // [rsp+C0h] [rbp-268h]
  void *v92[2]; // [rsp+D0h] [rbp-258h] BYREF
  __m128i si128; // [rsp+E0h] [rbp-248h]
  void **v94; // [rsp+F0h] [rbp-238h] BYREF
  int v95; // [rsp+F8h] [rbp-230h] BYREF
  char v96; // [rsp+FCh] [rbp-22Ch]
  int v97; // [rsp+120h] [rbp-208h] BYREF
  const char *v98; // [rsp+128h] [rbp-200h]
  __int64 v99; // [rsp+130h] [rbp-1F8h]
  char v100; // [rsp+138h] [rbp-1F0h]
  int v101; // [rsp+140h] [rbp-1E8h]
  char v102[152]; // [rsp+148h] [rbp-1E0h] BYREF
  __int128 v103; // [rsp+1E0h] [rbp-148h]
  int v104; // [rsp+1F0h] [rbp-138h]
  __int64 v105; // [rsp+1F8h] [rbp-130h]
  int *v106; // [rsp+200h] [rbp-128h]
  unsigned __int64 v107; // [rsp+208h] [rbp-120h]
  __int64 v108; // [rsp+210h] [rbp-118h]
  void ***v109; // [rsp+218h] [rbp-110h]
  __int64 v110; // [rsp+220h] [rbp-108h]
  int v111; // [rsp+228h] [rbp-100h]
  int *v112; // [rsp+230h] [rbp-F8h]
  char v113; // [rsp+238h] [rbp-F0h]
  _BYTE v114[16]; // [rsp+240h] [rbp-E8h] BYREF
  const char *v115; // [rsp+250h] [rbp-D8h]
  __int64 v116; // [rsp+258h] [rbp-D0h]
  void **v117; // [rsp+260h] [rbp-C8h]
  int v118; // [rsp+268h] [rbp-C0h]
  int v119; // [rsp+26Ch] [rbp-BCh]
  PSRWLOCK *p_SRWLock; // [rsp+270h] [rbp-B8h]
  __int64 v121; // [rsp+278h] [rbp-B0h]
  _QWORD *v122; // [rsp+280h] [rbp-A8h]
  __int64 v123; // [rsp+288h] [rbp-A0h]
  HSTRING v124; // [rsp+290h] [rbp-98h]
  unsigned int v125; // [rsp+298h] [rbp-90h]
  int v126; // [rsp+29Ch] [rbp-8Ch]
  wil::details::in1diag3 *retaddr; // [rsp+328h] [rbp+0h]

  v7 = a4;
  v89 = a4;
  v82 = a3;
  v77 = a2;
  v81 = string;
  v87 = a7;
  v10 = 0;
  LODWORD(v76) = 0;
  try
  {
    if ( Windows::Internal::Storage::Cloud::CloudStore::ShouldUseActivityFeedForSync(
           (Windows::Internal::Storage::Cloud::CloudStore *)a1,
           a4) )
    {
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x2A9,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
        v11);
    }
    *a7 = 0;
    EffectiveUserContext::Impersonate((void ***)(a1 + 200), &hObject);
    StringRawBuffer = WindowsGetStringRawBuffer(v7, 0);
    v13 = WindowsGetStringRawBuffer(string, 0);
    v14 = WindowsGetStringRawBuffer(a3, 0);
    v95 = 0;
    v96 = 0;
    v100 = 0;
    v97 = 0;
    v98 = "LoadActivity";
    v99 = 0;
    v101 = 0;
    v103 = 0;
    memset_0(v102, 0, sizeof(v102));
    v104 = 1;
    v105 = 0;
    v106 = &v95;
    v107 = 0;
    v108 = 0;
    v109 = &v94;
    v110 = 0;
    v111 = 0;
    v112 = &v97;
    v113 = 0;
    v94 = &Windows::Internal::Storage::Cloud::CloudStoreTelemetry::LoadActivity::`vftable';
    Windows::Internal::Storage::Cloud::CloudStoreTelemetry::LoadActivity::StartActivity(
      (Windows::Internal::Storage::Cloud::CloudStoreTelemetry::LoadActivity *)&v94,
      byte_1802299F5,
      v77,
      v14,
      &LocaleName,
      v13,
      StringRawBuffer,
      a6);
    WindowsDeleteString(0);
    v86 = 0;
    DataStoreId = Windows::Internal::Storage::Cloud::CloudStore::HandleLoadOptionsAndGetDataStoreId(a1, v77, v82, v7);
    v16 = DataStoreId;
    if ( DataStoreId < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2BD,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
        (const char *)(unsigned int)DataStoreId,
        (int)v81);
      WindowsDeleteString(v86);
      v94 = &Windows::Internal::Storage::Cloud::CloudStoreTelemetry::LoadActivity::`vftable';
      wil::ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v94);
      wil::ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(&v94);
      if ( hObject != (HANDLE)-1LL )
        wil::details::RevertImpersonateToken(hObject, v69);
      result = v16;
    }
    else
    {
      v17 = v86;
      v18 = (RTL_SRWLOCK *)WindowsGetStringRawBuffer(v86, 0);
      SRWLock = v18;
      v19 = (RTL_SRWLOCK *)(a1 + 344);
      AcquireSRWLockShared((PSRWLOCK)(a1 + 344));
      v88 = a1 + 344;
      pv = 0;
      v80 = 0;
      v83 = 0;
      v90[0] = (unsigned __int8 *)&pv;
      v90[1] = 0;
      LOBYTE(v91) = 1;
      v20 = Windows::Internal::Storage::Cloud::CloudStore::LoadInternal(
              (__int64 **)a1,
              (const unsigned __int16 *)v18,
              &v90[1],
              &v80,
              &v83);
      if ( (_BYTE)v91 )
      {
        v21 = *(void **)v90[0];
        *(_QWORD *)v90[0] = v90[1];
        if ( v21 )
          CoTaskMemFree(v21);
      }
      if ( v20 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2C7,
          (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
          (const char *)(unsigned int)v20,
          v74);
        v70 = pv;
        pv = 0;
        if ( v70 )
          CoTaskMemFree(v70);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v88);
        WindowsDeleteString(v17);
        Windows::Internal::Storage::Cloud::CloudStoreTelemetry::LoadActivity::~LoadActivity((Windows::Internal::Storage::Cloud::CloudStoreTelemetry::LoadActivity *)&v94);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&hObject);
        result = (unsigned int)v20;
      }
      else
      {
        v22 = 0;
        v78 = 0;
        if ( v80 )
        {
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v78);
          v49 = pv;
          pv = 0;
          v78 = 0;
          v50 = 0;
          v76 = 0;
          v51 = operator new(0x70u, (const struct std::nothrow_t *)std::nothrow);
          if ( v51 )
          {
            Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<19>,Windows::Storage::Streams::IBuffer,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<19>,Windows::Storage::Streams::IBuffer,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>(v51);
            v51[10] = v49;
            v52 = v80;
            *((_DWORD *)v51 + 22) = v80;
            *((_DWORD *)v51 + 23) = v52;
            v53 = CoTaskMemFree;
            v51[12] = CoTaskMemFree;
            v51[13] = 0;
            *v51 = &Windows::Storage::Streams::CBuffer<void (*)(void *),Windows::Storage::Streams::DefaultMarshaler>::`vftable';
            v51[1] = &Windows::Storage::Streams::CBuffer<void (*)(void *),Windows::Storage::Streams::DefaultMarshaler>::`vftable'{for `IWeakReferenceSource'};
            v51[2] = &Windows::Storage::Streams::CBuffer<void (*)(void *),Windows::Storage::Streams::DefaultMarshaler>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<19>,1,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>'};
            v51[3] = &Windows::Storage::Streams::CBuffer<void (*)(void *),Windows::Storage::Streams::DefaultMarshaler>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<19>,1,IMarshal>'};
            v51[4] = &Windows::Storage::Streams::CBuffer<_lambda_e91de0ce91357f29f6aa486c2a1e2f5b_,Windows::Storage::Streams::DefaultMarshaler>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<19>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
            v50 = (__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *))v51;
            v76 = v51;
          }
          else
          {
            v51 = 0;
            v53 = CoTaskMemFree;
          }
          if ( v51 )
          {
            v54 = (**v50)(v50, &GUID_905a0fe0_bc53_11df_8c49_001e4fc686da, &v78);
          }
          else
          {
            v54 = -2147024882;
            ((void (__fastcall *)(LPVOID))v53)(v49);
          }
          if ( v51 )
            (*(void (__fastcall **)(_QWORD *))(*v51 + 16LL))(v51);
          if ( v54 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x2CC,
              (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
              (const char *)(unsigned int)v54,
              v74);
            v55 = v78;
            if ( v78 )
            {
              v78 = 0;
              ((void (__fastcall *)(__int64 (__fastcall ***)(struct Windows::Storage::Streams::IBuffer *, GUID *, std::_Ref_count_base ***)))(*v55)[2])(v55);
            }
            v56 = pv;
            pv = 0;
            if ( v56 )
              CoTaskMemFree(v56);
            if ( a1 != -344 )
              ReleaseSRWLockShared((PSRWLOCK)(a1 + 344));
            WindowsDeleteString(v17);
            v94 = &Windows::Internal::Storage::Cloud::CloudStoreTelemetry::LoadActivity::`vftable';
            wil::ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v94);
            wil::ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(&v94);
            if ( hObject != (HANDLE)-1LL )
              wil::details::RevertImpersonateToken(hObject, v57);
            return (unsigned int)v54;
          }
          v22 = v78;
          v7 = v89;
        }
        Instance = Windows::Internal::Storage::Cloud::CloudStore::CloudStoreData_OldCreateInstance(
                     (Windows::Internal::Storage::Cloud::CloudStore *)a1,
                     v82,
                     v7,
                     v81,
                     v22,
                     v83,
                     v87);
        v24 = Instance;
        if ( Instance >= 0 )
        {
          v25 = v78;
          v26 = 0;
          v81 = 0;
          v77 = 0;
          if ( v78 )
          {
            v27 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(struct Windows::Storage::Streams::IBuffer *, GUID *, std::_Ref_count_base ***), unsigned int *))(*v78)[7])(
                    v78,
                    &v77);
            if ( v27 < 0 )
            {
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x22,
                (unsigned int)"onecoreuap\\shell\\cloudstore\\logging\\logginghelpers.cpp",
                (const char *)(unsigned int)v27,
                v75);
            }
            else if ( v77 <= 0x4000 )
            {
              v76 = 0;
              v28 = **v25;
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v76);
              v29 = v28(
                      (struct Windows::Storage::Streams::IBuffer *)v25,
                      &GUID_905a0fef_bc53_11df_8c49_001e4fc686da,
                      (std::_Ref_count_base ***)&v76);
              v30 = retaddr;
              if ( v29 < 0 )
              {
                v71 = 37;
              }
              else
              {
                v82 = 0;
                v29 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING *))(*v76 + 24LL))(v76, &v82);
                v30 = retaddr;
                if ( v29 >= 0 )
                {
                  v81 = v82;
                  v26 = v77;
                  goto LABEL_16;
                }
                v71 = 40;
              }
              wil::details::in1diag3::_Log_Hr(
                v30,
                (void *)v71,
                (unsigned int)"onecoreuap\\shell\\cloudstore\\logging\\logginghelpers.cpp",
                (const char *)(unsigned int)v29,
                v75);
LABEL_16:
              v31 = v76;
              if ( v76 )
              {
                v76 = 0;
                (*(void (__fastcall **)(_QWORD *))(*v31 + 16LL))(v31);
              }
            }
          }
          if ( (Microsoft_Windows_CloudStoreEnableBits & 2) != 0 )
          {
            *(_OWORD *)v90 = 0;
            v91 = 0;
            v32 = -1;
            v33 = SRWLock;
            do
              ++v32;
            while ( *((_WORD *)&SRWLock->Ptr + v32) );
            if ( v32 > 0x7FFFFFFFFFFFFFFELL )
              std::_Xlength_error("string too long");
            if ( v32 <= 7 )
            {
              *(_QWORD *)&v91 = v32;
              *((_QWORD *)&v91 + 1) = 7;
              v72 = 2 * v32;
              memcpy_0(v90, SRWLock, v72);
              *(_WORD *)((char *)v90 + v72) = 0;
            }
            else
            {
              v34 = std::wstring::_Calculate_growth(v32);
              if ( (unsigned __int64)(v34 + 1) > 0x7FFFFFFFFFFFFFFFLL )
                std::_Throw_bad_array_new_length();
              v58 = (unsigned __int8 *)std::_Allocate<16,std::_Default_allocate_traits>(2 * (v34 + 1));
              v90[0] = v58;
              *(_QWORD *)&v91 = v32;
              *((_QWORD *)&v91 + 1) = v34;
              v59 = 2 * v32;
              memcpy_0(v58, v33, v59);
              *(_WORD *)&v58[v59] = 0;
            }
            LODWORD(v76) = 1;
            v60 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
            v61 = *(_DWORD *)(v60 + 136);
            v62 = v60 + 16;
            if ( (v61 & 1) == 0 )
            {
              *(_DWORD *)(v60 + 136) = v61 | 1;
              std::wstring_convert<std::codecvt_utf8<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::wstring_convert<std::codecvt_utf8<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>(v60 + 16);
              _tlregdtor(WideStringToUtf8String_::_2_::_dynamic_atexit_destructor_for__converter_utf8__);
            }
            v63 = v90;
            if ( *((_QWORD *)&v91 + 1) > 7u )
              v63 = (unsigned __int8 **)v90[0];
            std::wstring_convert<std::codecvt_utf8<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::to_bytes(
              v62,
              v92,
              v63,
              (char *)v63 + 2 * v91);
            v10 = 15;
            v65 = (void **)v92[0];
            if ( si128.m128i_i64[1] <= 0xFuLL )
              v65 = v92;
            LODWORD(v76) = v26;
            SRWLock = (PSRWLOCK)v83;
            v115 = byte_1802299F5;
            v116 = 1;
            if ( v65 )
            {
              v35 = -1;
              do
                ++v35;
              while ( *((_BYTE *)v65 + v35) );
              v36 = (unsigned int)(v35 + 1);
            }
            else
            {
              v65 = (void **)"NULL";
              v36 = 5;
            }
            v117 = v65;
            v118 = v36;
            v119 = 0;
            p_SRWLock = &SRWLock;
            v121 = 8;
            v122 = &v76;
            v123 = 4;
            v124 = v81;
            v125 = v26;
            v126 = 0;
            McGenEventWrite_EventWriteTransfer(v36, Debug_Loaded, v64, 6);
          }
          if ( (v10 & 2) != 0 )
          {
            v10 &= ~2u;
            if ( si128.m128i_i64[1] > 0xFuLL )
            {
              v37 = (const struct std::nothrow_t *)(si128.m128i_i64[1] + 1);
              v82 = (HSTRING)(si128.m128i_i64[1] + 1);
              v38 = (HSTRING)v92[0];
              v81 = (HSTRING)v92[0];
              if ( (unsigned __int64)(si128.m128i_i64[1] + 1) >= 0x1000 )
              {
                std::_Adjust_manually_vector_aligned((void **)&v81, (unsigned __int64 *)&v82);
                v37 = (const struct std::nothrow_t *)v82;
                v38 = v81;
              }
              operator delete(v38, v37);
            }
            si128 = _mm_load_si128((const __m128i *)&_xmm);
            LOBYTE(v92[0]) = 0;
          }
          if ( (v10 & 1) != 0 )
          {
            v10 &= ~1u;
            if ( *((_QWORD *)&v91 + 1) > 7u )
              std::_Deallocate<16>(v90[0], (const struct std::nothrow_t *)(2LL * *((_QWORD *)&v91 + 1) + 2));
          }
          if ( v107 )
          {
            v39 = v10 | 0x10;
            v41 = (RTL_SRWLOCK *)(((v107 + 8) & ((unsigned __int128)-(__int128)v107 >> 64)) + 256);
            AcquireSRWLockExclusive(v41);
            v40 = &v87;
          }
          else
          {
            v39 = v10 | 0x20;
            v40 = &SRWLock;
            v41 = 0;
          }
          *v40 = 0;
          if ( (v39 & 0x20) != 0 )
          {
            v39 &= ~0x20u;
            if ( SRWLock )
              ReleaseSRWLockExclusive(SRWLock);
          }
          if ( (v39 & 0x10) != 0 )
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v87);
          v42 = v106;
          v43 = v106[62];
          if ( v43 < 1 )
          {
            memset_0(v114, 0, 0x98u);
            wil::details::WilFailFast((wil::details *)v114, v73);
          }
          if ( v106[18] >= 0 )
            v106[18] = 0;
          v42[62] = v43 - 1;
          if ( v41 )
            ReleaseSRWLockExclusive(v41);
          Windows::Internal::Storage::Cloud::CloudStoreTelemetry::LoadActivity::Stop(
            (Windows::Internal::Storage::Cloud::CloudStoreTelemetry::LoadActivity *)&v94,
            byte_1802299F5,
            v80,
            v83,
            &GUID_NULL,
            1);
          v44 = v78;
          if ( v78 )
          {
            v78 = 0;
            ((void (__fastcall *)(__int64 (__fastcall ***)(struct Windows::Storage::Streams::IBuffer *, GUID *, std::_Ref_count_base ***)))(*v44)[2])(v44);
          }
          v45 = pv;
          pv = 0;
          if ( v45 )
            CoTaskMemFree(v45);
          if ( v19 )
            ReleaseSRWLockShared(v19);
          WindowsDeleteString(v17);
          v94 = &Windows::Internal::Storage::Cloud::CloudStoreTelemetry::LoadActivity::`vftable';
          wil::ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v94);
          wil::ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(&v94);
          if ( hObject != (HANDLE)-1LL )
            wil::details::RevertImpersonateToken(hObject, v46);
          return 0;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2CE,
          (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
          (const char *)(unsigned int)Instance,
          v75);
        v66 = v78;
        if ( v78 )
        {
          v78 = 0;
          ((void (__fastcall *)(__int64 (__fastcall ***)(struct Windows::Storage::Streams::IBuffer *, GUID *, std::_Ref_count_base ***)))(*v66)[2])(v66);
        }
        v67 = pv;
        pv = 0;
        if ( v67 )
          CoTaskMemFree(v67);
        if ( a1 != -344 )
          ReleaseSRWLockShared((PSRWLOCK)(a1 + 344));
        WindowsDeleteString(v17);
        v94 = &Windows::Internal::Storage::Cloud::CloudStoreTelemetry::LoadActivity::`vftable';
        wil::ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v94);
        wil::ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(&v94);
        if ( hObject != (HANDLE)-1LL )
          wil::details::RevertImpersonateToken(hObject, v68);
        result = v24;
      }
    }
  }
  catch ( ... )
  {
    LODWORD(v76) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0x2D5,
                     (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
                     v47);
    JUMPOUT(0x18005CEB0LL);
  }
  return result;
}

```

## disassembly

```asm
0x18005c204  push    rbx
0x18005c206  push    rsi
0x18005c207  push    rdi
0x18005c208  push    r12
0x18005c20a  push    r13
0x18005c20c  push    r14
0x18005c20e  push    r15
0x18005c210  sub     rsp, 2F0h
0x18005c217  mov     rax, cs:__security_cookie
0x18005c21e  xor     rax, rsp
0x18005c221  mov     [rsp+328h+var_48], rax
0x18005c229  mov     r12, r9
0x18005c22c  mov     [rsp+328h+var_280], r9
0x18005c234  mov     rdi, r8
0x18005c237  mov     [rsp+328h+var_2B8], r8
0x18005c23c  mov     [rsp+328h+var_2E0], edx
0x18005c240  mov     r13, rcx
0x18005c243  mov     rsi, [rsp+328h+string]
0x18005c24b  mov     [rsp+328h+var_2C0], rsi
0x18005c250  mov     rbx, [rsp+328h+arg_30]
0x18005c258  mov     [rsp+328h+var_290], rbx
0x18005c260  xor     r14d, r14d
0x18005c263  mov     r15d, r14d
0x18005c266  mov     dword ptr [rsp+328h+var_2E8], r14d
0x18005c26b  mov     rdx, r9; HSTRING
0x18005c26e  call    ?ShouldUseActivityFeedForSync@CloudStore@Cloud@Storage@Internal@Windows@@AEAA_NPEAUHSTRING__@@@Z; Windows::Internal::Storage::Cloud::CloudStore::ShouldUseActivityFeedForSync(HSTRING__ *)
0x18005c273  mov     rcx, [rsp+328h]; this
0x18005c27b  test    al, al
0x18005c27d  jnz     loc_18005CBAE
0x18005c283  mov     [rbx], r14
0x18005c286  lea     rcx, [r13+0C8h]
0x18005c28d  lea     rdx, [rsp+328h+hObject]
0x18005c295  call    ?Impersonate@EffectiveUserContext@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@wil@@XZ; EffectiveUserContext::Impersonate(void)
0x18005c29a  nop
0x18005c29b  xor     edx, edx; length
0x18005c29d  mov     rcx, r12; string
0x18005c2a0  call    cs:__imp_WindowsGetStringRawBuffer
0x18005c2a6  mov     r14, rax
0x18005c2a9  xor     edx, edx; length
0x18005c2ab  mov     rcx, rsi; string
0x18005c2ae  call    cs:__imp_WindowsGetStringRawBuffer
0x18005c2b4  mov     rsi, rax
0x18005c2b7  xor     edx, edx; length
0x18005c2b9  mov     rcx, rdi; string
0x18005c2bc  call    cs:__imp_WindowsGetStringRawBuffer
0x18005c2c2  mov     rdi, rax
0x18005c2c5  xor     ebx, ebx
0x18005c2c7  mov     [rsp+328h+var_230], ebx
0x18005c2ce  mov     [rsp+328h+var_22C], bl
0x18005c2d5  mov     [rsp+328h+var_1F0], bl
0x18005c2dc  mov     [rsp+328h+var_208], ebx
0x18005c2e3  lea     rax, aLoadactivity; "LoadActivity"
0x18005c2ea  mov     [rsp+328h+var_200], rax
0x18005c2f2  mov     [rsp+328h+var_1F8], rbx
0x18005c2fa  mov     [rsp+328h+var_1E8], ebx
0x18005c301  xorps   xmm0, xmm0
0x18005c304  movdqa  [rsp+328h+var_148], xmm0
0x18005c30d  xor     edx, edx; Val
0x18005c30f  mov     r8d, 98h; Size
0x18005c315  lea     rcx, [rsp+328h+var_1E0]; void *
0x18005c31d  call    memset_0
0x18005c322  mov     [rsp+328h+var_138], 1
0x18005c32d  xor     eax, eax
0x18005c32f  mov     [rsp+328h+var_130], rax
0x18005c337  lea     rax, [rsp+328h+var_230]
0x18005c33f  mov     [rsp+328h+var_128], rax
0x18005c347  mov     [rsp+328h+var_120], rbx
0x18005c34f  mov     [rsp+328h+var_118], rbx
0x18005c357  lea     rax, [rsp+328h+var_238]
0x18005c35f  mov     [rsp+328h+var_110], rax
0x18005c367  mov     [rsp+328h+var_108], rbx
0x18005c36f  mov     [rsp+328h+var_100], ebx
0x18005c376  lea     rax, [rsp+328h+var_208]
0x18005c37e  mov     [rsp+328h+var_F8], rax
0x18005c386  mov     [rsp+328h+var_F0], bl
0x18005c38d  lea     rax, ??_7LoadActivity@CloudStoreTelemetry@Cloud@Storage@Internal@Windows@@6B@; const Windows::Internal::Storage::Cloud::CloudStoreTelemetry::LoadActivity::`vftable'
0x18005c394  mov     [rsp+328h+var_238], rax
0x18005c39c  mov     ebx, [rsp+328h+arg_28]
0x18005c3a3  mov     [rsp+328h+var_2F0], ebx; unsigned int
0x18005c3a7  mov     [rsp+328h+var_2F8], r14; unsigned __int16 *
0x18005c3ac  mov     [rsp+328h+var_300], rsi; unsigned __int16 *
0x18005c3b1  lea     rax, LocaleName
0x18005c3b8  mov     [rsp+328h+var_308], rax; unsigned __int16 *
0x18005c3bd  mov     r9, rdi; unsigned __int16 *
0x18005c3c0  mov     r8d, [rsp+328h+var_2E0]; unsigned int
0x18005c3c5  lea     rdx, byte_1802299F5; char *
0x18005c3cc  lea     rcx, [rsp+328h+var_238]; this
0x18005c3d4  call    ?StartActivity@LoadActivity@CloudStoreTelemetry@Cloud@Storage@Internal@Windows@@QEAAXPEBDIPEBG111I@Z; Windows::Internal::Storage::Cloud::CloudStoreTelemetry::LoadActivity::StartActivity(char const *,uint,ushort const *,ushort const *,ushort const *,ushort const *,uint)
0x18005c3d9  nop
0x18005c3da  xor     ecx, ecx; string
0x18005c3dc  call    cs:__imp_WindowsDeleteString
0x18005c3e2  xor     esi, esi
0x18005c3e4  mov     [rsp+328h+var_298], rsi
0x18005c3ec  lea     rax, [rsp+328h+var_298]
0x18005c3f4  mov     [rsp+328h+var_2F8], rax
0x18005c3f9  mov     dword ptr [rsp+328h+var_300], ebx
0x18005c3fd  mov     rax, [rsp+328h+var_2C0]
0x18005c402  mov     [rsp+328h+var_308], rax; int
0x18005c407  mov     r9, r12
0x18005c40a  mov     r8, [rsp+328h+var_2B8]
0x18005c40f  mov     edx, [rsp+328h+var_2E0]
0x18005c413  mov     rcx, r13
0x18005c416  call    ?HandleLoadOptionsAndGetDataStoreId@CloudStore@Cloud@Storage@Internal@Windows@@AEAAJW4PartitionKind@2345@PEAUHSTRING__@@11W4LoadOptions@2345@PEAPEAU7@@Z; Windows::Internal::Storage::Cloud::CloudStore::HandleLoadOptionsAndGetDataStoreId(Windows::Internal::Storage::Cloud::PartitionKind,HSTRING__ *,HSTRING__ *,HSTRING__ *,Windows::Internal::Storage::Cloud::LoadOptions,HSTRING__ * *)
0x18005c41b  mov     ebx, eax
0x18005c41d  test    eax, eax
0x18005c41f  js      loc_18005CCC0
0x18005c425  xor     edx, edx; length
0x18005c427  mov     rdi, [rsp+328h+var_298]
0x18005c42f  mov     rcx, rdi; string
0x18005c432  call    cs:__imp_WindowsGetStringRawBuffer
0x18005c438  mov     rbx, rax
0x18005c43b  mov     [rsp+328h+SRWLock], rax
0x18005c443  lea     r14, [r13+158h]
0x18005c44a  mov     rcx, r14; SRWLock
0x18005c44d  call    cs:__imp_AcquireSRWLockShared
0x18005c453  mov     [rsp+328h+var_288], r14
0x18005c45b  mov     [rsp+328h+pv], rsi
0x18005c460  mov     [rsp+328h+var_2C8], esi
0x18005c464  mov     [rsp+328h+var_2B0], rsi
0x18005c469  lea     rax, [rsp+328h+pv]
0x18005c46e  mov     [rsp+328h+var_278], rax
0x18005c476  mov     [rsp+328h+var_278+8], rsi
0x18005c47e  mov     byte ptr [rsp+328h+var_268], 1
0x18005c486  lea     rax, [rsp+328h+var_2B0]
0x18005c48b  mov     [rsp+328h+var_308], rax; int
0x18005c490  lea     r9, [rsp+328h+var_2C8]; unsigned int *
0x18005c495  lea     r8, [rsp+328h+var_278+8]; unsigned __int8 **
0x18005c49d  mov     rdx, rbx; unsigned __int16 *
0x18005c4a0  mov     rcx, r13; this
0x18005c4a3  call    ?LoadInternal@CloudStore@Cloud@Storage@Internal@Windows@@AEAAJPEBGPEAPEAEPEAKPEA_K@Z; Windows::Internal::Storage::Cloud::CloudStore::LoadInternal(ushort const *,uchar * *,ulong *,unsigned __int64 *)
0x18005c4a8  mov     ebx, eax
0x18005c4aa  cmp     byte ptr [rsp+328h+var_268], sil
0x18005c4b2  jz      short loc_18005C4D8
0x18005c4b4  mov     rdx, [rsp+328h+var_278]
0x18005c4bc  mov     rax, [rdx]
0x18005c4bf  mov     rcx, [rsp+328h+var_278+8]
0x18005c4c7  mov     [rdx], rcx
0x18005c4ca  test    rax, rax
0x18005c4cd  jz      short loc_18005C4D8
0x18005c4cf  mov     rcx, rax; pv
0x18005c4d2  call    cs:__imp_CoTaskMemFree
0x18005c4d8  test    ebx, ebx
0x18005c4da  js      loc_18005CD5E
0x18005c4e0  mov     rax, rsi
0x18005c4e3  mov     [rsp+328h+var_2D8], rax
0x18005c4e8  cmp     [rsp+328h+var_2C8], esi
0x18005c4ec  ja      loc_18005C943
0x18005c4f2  mov     rcx, [rsp+328h+var_290]
0x18005c4fa  mov     [rsp+328h+var_2F8], rcx; struct Windows::Internal::Storage::Cloud::ICloudStoreData **
0x18005c4ff  mov     rcx, [rsp+328h+var_2B0]
0x18005c504  mov     [rsp+328h+var_300], rcx; unsigned __int64
0x18005c509  mov     [rsp+328h+var_308], rax; int
0x18005c50e  mov     r9, [rsp+328h+var_2C0]; HSTRING
0x18005c513  mov     r8, r12; HSTRING
0x18005c516  mov     rdx, [rsp+328h+var_2B8]; HSTRING
0x18005c51b  mov     rcx, r13; this
0x18005c51e  call    ?CloudStoreData_OldCreateInstance@CloudStore@Cloud@Storage@Internal@Windows@@QEAAJPEAUHSTRING__@@00PEAUIBuffer@Streams@35@_KPEAPEAUICloudStoreData@2345@@Z; Windows::Internal::Storage::Cloud::CloudStore::CloudStoreData_OldCreateInstance(HSTRING__ *,HSTRING__ *,HSTRING__ *,Windows::Storage::Streams::IBuffer *,unsigned __int64,Windows::Internal::Storage::Cloud::ICloudStoreData * *)
0x18005c523  mov     ebx, eax
0x18005c525  xor     r12d, r12d
0x18005c528  test    eax, eax
0x18005c52a  js      loc_18005CC14
0x18005c530  mov     rsi, [rsp+328h+var_2D8]
0x18005c535  mov     r13d, r12d
0x18005c538  mov     [rsp+328h+var_2C0], r12
0x18005c53d  mov     [rsp+328h+var_2E0], r12d
0x18005c542  test    rsi, rsi
0x18005c545  jz      loc_18005C60F
0x18005c54b  mov     rax, [rsi]
0x18005c54e  lea     rdx, [rsp+328h+var_2E0]
0x18005c553  mov     rcx, rsi
0x18005c556  mov     rax, [rax+38h]
0x18005c55a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c55f  mov     rcx, [rsp+328h]; this
0x18005c567  test    eax, eax
0x18005c569  js      loc_18005CDCB
0x18005c56f  cmp     [rsp+328h+var_2E0], 4000h
0x18005c577  ja      loc_18005C60F
0x18005c57d  mov     [rsp+328h+var_2E8], r12
0x18005c582  mov     rax, [rsi]
0x18005c585  mov     rbx, [rax]
0x18005c588  lea     rcx, [rsp+328h+var_2E8]
0x18005c58d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005c592  lea     r8, [rsp+328h+var_2E8]
0x18005c597  lea     rdx, _GUID_905a0fef_bc53_11df_8c49_001e4fc686da
0x18005c59e  mov     rcx, rsi
0x18005c5a1  mov     rax, rbx
0x18005c5a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c5a9  mov     rcx, [rsp+328h]
0x18005c5b1  test    eax, eax
0x18005c5b3  js      loc_18005CDE4
0x18005c5b9  mov     [rsp+328h+var_2B8], r12
0x18005c5be  mov     rcx, [rsp+328h+var_2E8]
0x18005c5c3  mov     rax, [rcx]
0x18005c5c6  lea     rdx, [rsp+328h+var_2B8]
0x18005c5cb  mov     rax, [rax+18h]
0x18005c5cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c5d4  mov     rcx, [rsp+328h]; this
0x18005c5dc  test    eax, eax
0x18005c5de  js      loc_18005CDEB
0x18005c5e4  mov     rax, [rsp+328h+var_2B8]
0x18005c5e9  mov     [rsp+328h+var_2C0], rax
0x18005c5ee  mov     r13d, [rsp+328h+var_2E0]
0x18005c5f3  mov     rcx, [rsp+328h+var_2E8]
0x18005c5f8  test    rcx, rcx
0x18005c5fb  jz      short loc_18005C60F
0x18005c5fd  mov     [rsp+328h+var_2E8], r12
0x18005c602  mov     rax, [rcx]
0x18005c605  mov     rax, [rax+10h]
0x18005c609  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c60e  nop
0x18005c60f  test    cs:Microsoft_Windows_CloudStoreEnableBits, 2
0x18005c616  jz      short loc_18005C690
0x18005c618  xorps   xmm0, xmm0
0x18005c61b  movups  xmmword ptr [rsp+328h+var_278], xmm0
0x18005c623  xorps   xmm1, xmm1
0x18005c626  movdqu  [rsp+328h+var_268], xmm1
0x18005c62f  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18005c633  mov     r12, [rsp+328h+SRWLock]
0x18005c63b  xor     edx, edx
0x18005c63d  inc     rbx
0x18005c640  cmp     [r12+rbx*2], dx
0x18005c645  jnz     short loc_18005C63D
0x18005c647  mov     r8, 7FFFFFFFFFFFFFFEh
0x18005c651  cmp     rbx, r8
0x18005c654  ja      loc_18005CE04
0x18005c65a  cmp     rbx, 7
0x18005c65e  jbe     loc_18005CE11
0x18005c664  mov     edx, 7
0x18005c669  mov     rcx, rbx
0x18005c66c  call    ?_Calculate_growth@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CA_K_K00@Z; std::wstring::_Calculate_growth(unsigned __int64,unsigned __int64,unsigned __int64)
0x18005c671  mov     r15, rax
0x18005c674  lea     rcx, [rax+1]
0x18005c678  mov     rax, 7FFFFFFFFFFFFFFFh
0x18005c682  cmp     rcx, rax
0x18005c685  jbe     loc_18005CAD9
0x18005c68b  call    ?_Throw_bad_array_new_length@std@@YAXXZ; std::_Throw_bad_array_new_length(void)
0x18005c690  lea     rsi, byte_1802299F5
0x18005c697  jmp     loc_18005C764
0x18005c69c  mov     dword ptr [rsp+328h+var_2E8], r13d
0x18005c6a1  mov     [rsp+328h+SRWLock], rcx
0x18005c6a9  lea     rsi, byte_1802299F5
0x18005c6b0  mov     [rsp+328h+var_D8], rsi
0x18005c6b8  mov     [rsp+328h+var_D0], 1
0x18005c6c4  test    rax, rax
0x18005c6c7  jz      loc_18005CE4C
0x18005c6cd  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18005c6d1  inc     rcx
0x18005c6d4  cmp     [rax+rcx], r12b
0x18005c6d8  jnz     short loc_18005C6D1
0x18005c6da  inc     ecx
0x18005c6dc  mov     [rsp+328h+var_C8], rax
0x18005c6e4  mov     [rsp+328h+var_C0], ecx
0x18005c6eb  mov     [rsp+328h+var_BC], r12d
0x18005c6f3  lea     rax, [rsp+328h+SRWLock]
0x18005c6fb  mov     [rsp+328h+var_B8], rax
0x18005c703  mov     [rsp+328h+var_B0], 8
0x18005c70f  lea     rax, [rsp+328h+var_2E8]
0x18005c714  mov     [rsp+328h+var_A8], rax
0x18005c71c  mov     [rsp+328h+var_A0], 4
0x18005c728  mov     rax, [rsp+328h+var_2C0]
0x18005c72d  mov     [rsp+328h+var_98], rax
0x18005c735  mov     [rsp+328h+var_90], r13d
0x18005c73d  mov     [rsp+328h+var_8C], r12d
0x18005c745  lea     rax, [rsp+328h+var_E8]
0x18005c74d  mov     [rsp+328h+var_308], rax
0x18005c752  mov     r9d, 6
0x18005c758  lea     rdx, Debug_Loaded
0x18005c75f  call    McGenEventWrite_EventWriteTransfer
0x18005c764  test    r15b, 2
0x18005c768  jz      short loc_18005C7BC
0x18005c76a  and     r15d, 0FFFFFFFDh
0x18005c76e  mov     rdx, [rsp+328h+var_240]
0x18005c776  cmp     rdx, 0Fh
0x18005c77a  jbe     short loc_18005C7A3
0x18005c77c  inc     rdx; struct std::nothrow_t *
0x18005c77f  mov     [rsp+328h+var_2B8], rdx
0x18005c784  mov     rcx, [rsp+328h+var_258]; void *
0x18005c78c  mov     [rsp+328h+var_2C0], rcx
0x18005c791  cmp     rdx, 1000h
0x18005c798  jnb     loc_18005CE5D
0x18005c79e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18005c7a3  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x18005c7ab  movdqu  xmmword ptr [rsp+0E0h], xmm0
0x18005c7b4  mov     byte ptr [rsp+328h+var_258], r12b
0x18005c7bc  test    r15b, 1
0x18005c7c0  jz      short loc_18005C7E9
0x18005c7c2  and     r15d, 0FFFFFFFEh
0x18005c7c6  mov     rdx, qword ptr [rsp+328h+var_268+8]
0x18005c7ce  cmp     rdx, 7
0x18005c7d2  jbe     short loc_18005C7E9
0x18005c7d4  lea     rdx, ds:2[rdx*2]
0x18005c7dc  mov     rcx, [rsp+328h+var_278]
0x18005c7e4  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18005c7e9  mov     rcx, [rsp+328h+var_120]
0x18005c7f1  test    rcx, rcx
0x18005c7f4  jnz     loc_18005CD30
0x18005c7fa  or      r15d, 20h
0x18005c7fe  lea     rax, [rsp+328h+SRWLock]
0x18005c806  mov     rbx, r12
0x18005c809  mov     [rax], r12
  ... truncated ...
```
