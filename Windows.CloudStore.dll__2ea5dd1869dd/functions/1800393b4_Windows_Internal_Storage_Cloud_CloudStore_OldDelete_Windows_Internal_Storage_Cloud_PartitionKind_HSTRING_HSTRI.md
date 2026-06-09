# Windows::Internal::Storage::Cloud::CloudStore::OldDelete(Windows::Internal::Storage::Cloud::PartitionKind,HSTRING__ *,HSTRING__ *,HSTRING__ *,unsigned __int64,Windows::Internal::Storage::Cloud::ICloudStoreSaveResult * *)

- ea: `0x1800393b4`
- end: `0x180039e5d`
- name: `?OldDelete@CloudStore@Cloud@Storage@Internal@Windows@@QEAAJW4PartitionKind@2345@PEAUHSTRING__@@11_KPEAPEAUICloudStoreSaveResult@2345@@Z`
- size: `2729`
- prototype: `__int64 __fastcall(__int64, unsigned int, HSTRING, HSTRING, HSTRING string, unsigned __int64, __int64 *)`
- caller_count: `1`
- callee_count: `38`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180114670`

## callees

- `0x18000dfe4`
- `0x18000e84c`
- `0x18000f4b4`
- `0x180010688`
- `0x180019720`
- `0x180021e20`
- `0x180023fd4`
- `0x180024020`
- `0x180024fd0`
- `0x18002570c`
- `0x1800393b4`
- `0x18003a428`
- `0x18003a478`
- `0x18003ac5c`
- `0x18003af1c`
- `0x18003b060`
- `0x18003b170`
- `0x180047904`
- `0x18005b244`
- `0x18005babc`
- `0x18005d4b8`
- `0x18005de38`
- `0x18005ded4`
- `0x18005e4a0`
- `0x18005f34c`
- `0x18005f748`
- `0x18005f914`
- `0x18006010c`
- `0x180062040`
- `0x1800626e8`
- `0x18009818c`
- `0x1800adea8`
- `0x1800c8458`
- `0x1800d1d50`
- `0x18010d418`
- `0x1801201a0`
- `0x1801236bc`
- `0x180208010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039830`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800399b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039830`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800399b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180039443`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180039451`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003945f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180039551`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180039443`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180039451`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003945f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180039551`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800394d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039514`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003983c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003984c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800399c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800399d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039a59`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039aa5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039ab5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039b19`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039b2d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039b88`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039b9c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039c0d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039c1d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039c98`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039ca8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039d57`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039d6b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039e17`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039e27`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800394d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039514`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003983c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003984c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800399c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800399d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039a59`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039aa5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039ab5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039b19`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039b2d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039b88`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039b9c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039c0d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039c1d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039c98`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039ca8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039d57`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039d6b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039e17`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039e27`

## string_xrefs

- `0x180039468`: `DeleteActivity`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall Windows::Internal::Storage::Cloud::CloudStore::OldDelete(
        __int64 a1,
        unsigned int a2,
        HSTRING a3,
        HSTRING a4,
        HSTRING string,
        unsigned __int64 a6,
        __int64 *a7)
{
  char v10; // r15
  const char *v11; // r9
  const unsigned __int16 *StringRawBuffer; // rsi
  PCWSTR v13; // rdi
  const unsigned __int16 *v14; // rbx
  unsigned int v15; // edi
  int EffectivePartition; // eax
  unsigned int v17; // ebx
  int DataStoreId; // eax
  unsigned int v19; // ebx
  const unsigned __int16 *v20; // rsi
  const char *v21; // r9
  int TypeServiceAttributesForId; // eax
  __int64 v23; // r8
  unsigned int v24; // ebx
  int RootFromAttribute; // ebx
  int v26; // eax
  unsigned int v27; // ebx
  __int64 (__fastcall ***v28)(struct Windows::Storage::Streams::IBuffer *, GUID *, std::_Ref_count_base ***); // rax
  unsigned __int64 v29; // rbx
  int v30; // edi
  struct Windows::Internal::Storage::Cloud::ICloudStoreData *v31; // rdi
  Windows::Internal::Storage::Cloud::CloudStoreSaveResult *v32; // rax
  __int64 v33; // rax
  struct Windows::Storage::Streams::IBuffer *v34; // rcx
  struct Windows::Storage::Streams::IBuffer *v35; // rcx
  void *v36; // rdx
  const char *v37; // r9
  __int64 result; // rax
  _QWORD *v39; // rax
  __int64 v40; // rdx
  __int64 v41; // rcx
  struct Windows::Storage::Streams::IBuffer *v42; // rcx
  struct Windows::Storage::Streams::IBuffer *v43; // rcx
  void *v44; // rdx
  int v45; // eax
  unsigned int v46; // ebx
  int v47; // eax
  unsigned int v48; // edi
  int v49; // [rsp+20h] [rbp-278h]
  int v50; // [rsp+20h] [rbp-278h]
  unsigned __int16 *v51; // [rsp+28h] [rbp-270h]
  struct Windows::Storage::Streams::IBuffer **v52; // [rsp+30h] [rbp-268h]
  HSTRING v53; // [rsp+50h] [rbp-248h] BYREF
  HSTRING v54; // [rsp+58h] [rbp-240h]
  struct Windows::Storage::Streams::IBuffer *v55; // [rsp+60h] [rbp-238h] BYREF
  struct Windows::Storage::Streams::IBuffer *v56; // [rsp+68h] [rbp-230h] BYREF
  HANDLE hObject; // [rsp+70h] [rbp-228h] BYREF
  LPVOID pv; // [rsp+78h] [rbp-220h] BYREF
  unsigned __int64 v59; // [rsp+80h] [rbp-218h] BYREF
  unsigned int v60; // [rsp+88h] [rbp-210h]
  struct Windows::Internal::Storage::Cloud::ICloudStoreData *v61; // [rsp+90h] [rbp-208h] BYREF
  HSTRING v62; // [rsp+98h] [rbp-200h]
  unsigned __int64 v63; // [rsp+A0h] [rbp-1F8h] BYREF
  __int64 *v64; // [rsp+A8h] [rbp-1F0h]
  void *p_pv; // [rsp+B0h] [rbp-1E8h] BYREF
  struct Windows::Internal::Storage::Cloud::ICloudStoreData *v66; // [rsp+B8h] [rbp-1E0h] BYREF
  char v67; // [rsp+C0h] [rbp-1D8h]
  unsigned __int64 v68; // [rsp+C8h] [rbp-1D0h]
  __int128 v69; // [rsp+D0h] [rbp-1C8h] BYREF
  _BYTE v70[32]; // [rsp+E0h] [rbp-1B8h] BYREF
  _QWORD v71[42]; // [rsp+100h] [rbp-198h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+0h]

  v62 = a3;
  v60 = a2;
  v64 = a7;
  v10 = 0;
  LODWORD(v59) = 0;
  try
  {
    if ( Windows::Internal::Storage::Cloud::CloudStore::ShouldUseActivityFeedForSync(
           (Windows::Internal::Storage::Cloud::CloudStore *)a1,
           a4) )
    {
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x64E,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
        v11);
    }
    EffectiveUserContext::Impersonate((void ***)(a1 + 200), &hObject);
    StringRawBuffer = WindowsGetStringRawBuffer(a4, 0);
    v13 = WindowsGetStringRawBuffer(string, 0);
    v14 = WindowsGetStringRawBuffer(a3, 0);
    wil::ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
      v71,
      "DeleteActivity");
    v71[0] = &Windows::Internal::Storage::Cloud::CloudStoreTelemetry::DeleteActivity::`vftable';
    v51 = (unsigned __int16 *)v13;
    v15 = v60;
    Windows::Internal::Storage::Cloud::CloudStoreTelemetry::DeleteActivity::StartActivity(
      (Windows::Internal::Storage::Cloud::CloudStoreTelemetry::DeleteActivity *)v71,
      byte_1802299F5,
      v60,
      v14,
      &LocaleName,
      v51,
      StringRawBuffer,
      a6);
    WindowsDeleteString(0);
    v53 = 0;
    EffectivePartition = Windows::Internal::Storage::Cloud::CloudStore::GetEffectivePartition(a1, v15, v62, 0);
    v17 = EffectivePartition;
    if ( EffectivePartition < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x65A,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
        (const char *)(unsigned int)EffectivePartition,
        (int)&v53);
      WindowsDeleteString(v53);
      v53 = 0;
      Windows::Internal::Storage::Cloud::CloudStoreTelemetry::DeleteActivity::~DeleteActivity((Windows::Internal::Storage::Cloud::CloudStoreTelemetry::DeleteActivity *)v71);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&hObject);
      return v17;
    }
    WindowsDeleteString(0);
    v54 = 0;
    DataStoreId = Windows::Internal::Storage::Cloud::CloudStore::GetDataStoreId(a1, v15, v53, a4);
    v19 = DataStoreId;
    if ( DataStoreId < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x65D,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
        (const char *)(unsigned int)DataStoreId,
        (int)string);
      WindowsDeleteString(v54);
      v54 = 0;
      WindowsDeleteString(v53);
      v53 = 0;
      Windows::Internal::Storage::Cloud::CloudStoreTelemetry::DeleteActivity::~DeleteActivity((Windows::Internal::Storage::Cloud::CloudStoreTelemetry::DeleteActivity *)v71);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&hObject);
      return v19;
    }
    v20 = WindowsGetStringRawBuffer(v54, 0);
    if ( IsASTAOrMainSTA() )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x660,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
        (const char *)0x8001010ELL,
        (int)string);
    if ( !a6 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x661,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
        v21);
    v69 = 0;
    TypeServiceAttributesForId = Windows::Internal::Storage::Cloud::CloudStore::GetTypeServiceAttributesForId(
                                   (Windows::Internal::Storage::Cloud::CloudStore *)a1,
                                   v20,
                                   (struct TypeAttributes *)&v69);
    v24 = TypeServiceAttributesForId;
    if ( TypeServiceAttributesForId < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x665,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
        (const char *)(unsigned int)TypeServiceAttributesForId,
        (int)string);
      WindowsDeleteString(v54);
      v54 = 0;
      WindowsDeleteString(v53);
      v53 = 0;
      Windows::Internal::Storage::Cloud::CloudStoreTelemetry::DeleteActivity::~DeleteActivity((Windows::Internal::Storage::Cloud::CloudStoreTelemetry::DeleteActivity *)v71);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&hObject);
      return v24;
    }
    pv = 0;
    p_pv = &pv;
    v66 = 0;
    v67 = 1;
    RootFromAttribute = CloudStoreUtilities::GetRootFromAttribute(a1 + 232, (unsigned int)v69, v23, &v66);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&p_pv);
    if ( RootFromAttribute < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x667,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
        (const char *)(unsigned int)RootFromAttribute,
        (int)string);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pv);
      WindowsDeleteString(v54);
      v54 = 0;
      WindowsDeleteString(v53);
      v53 = 0;
      Windows::Internal::Storage::Cloud::CloudStoreTelemetry::DeleteActivity::~DeleteActivity((Windows::Internal::Storage::Cloud::CloudStoreTelemetry::DeleteActivity *)v71);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&hObject);
      return (unsigned int)RootFromAttribute;
    }
    v56 = 0;
    v63 = 0;
    v55 = 0;
    v59 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v55);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v56);
    v26 = Windows::Internal::Storage::Cloud::CloudStore::LoadAndResolveInternal(
            (Windows::Internal::Storage::Cloud::CloudStore *)a1,
            v20,
            0,
            0,
            0,
            a6,
            &v56,
            &v63,
            &v55,
            &v59);
    v27 = v26;
    if ( v26 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x66D,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
        (const char *)(unsigned int)v26,
        v49);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v55);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v56);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pv);
      WindowsDeleteString(v54);
      v54 = 0;
      WindowsDeleteString(v53);
      v53 = 0;
      Windows::Internal::Storage::Cloud::CloudStoreTelemetry::DeleteActivity::~DeleteActivity((Windows::Internal::Storage::Cloud::CloudStoreTelemetry::DeleteActivity *)v71);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&hObject);
      return v27;
    }
    v28 = (__int64 (__fastcall ***)(struct Windows::Storage::Streams::IBuffer *, GUID *, std::_Ref_count_base ***))v55;
    if ( v55 )
    {
      v29 = v59;
    }
    else
    {
      v45 = Windows::Internal::Storage::Cloud::CloudStore::EnsureCloudStoreCache((Windows::Internal::Storage::Cloud::CloudStore *)a1);
      v46 = v45;
      if ( v45 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x670,
          (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
          (const char *)(unsigned int)v45,
          v49);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v55);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v56);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pv);
        WindowsDeleteString(v54);
        v54 = 0;
        WindowsDeleteString(v53);
        v53 = 0;
        Windows::Internal::Storage::Cloud::CloudStoreTelemetry::DeleteActivity::~DeleteActivity((Windows::Internal::Storage::Cloud::CloudStoreTelemetry::DeleteActivity *)v71);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&hObject);
        return v46;
      }
      v29 = v59;
      v52 = (struct Windows::Storage::Streams::IBuffer **)v59;
      v47 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, LPVOID, const unsigned __int16 *))(**(_QWORD **)(a1 + 496) + 48LL))(
              *(_QWORD *)(a1 + 496),
              v20,
              pv,
              L"Current");
      v48 = v47;
      if ( v47 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x671,
          (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
          (const char *)(unsigned int)v47,
          0);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v55);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v56);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pv);
        WindowsDeleteString(v54);
        v54 = 0;
        WindowsDeleteString(v53);
        v53 = 0;
        Windows::Internal::Storage::Cloud::CloudStoreTelemetry::DeleteActivity::~DeleteActivity((Windows::Internal::Storage::Cloud::CloudStoreTelemetry::DeleteActivity *)v71);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&hObject);
        return v48;
      }
      Windows::Internal::Storage::Cloud::CloudStore::RemoveFromSystemPartitionIndexIfNeeded(
        a1,
        v60,
        v53,
        a4,
        string,
        v29,
        v52);
      v28 = (__int64 (__fastcall ***)(struct Windows::Storage::Streams::IBuffer *, GUID *, std::_Ref_count_base ***))v55;
    }
    v61 = 0;
    p_pv = &v61;
    v66 = 0;
    v67 = 1;
    v30 = Windows::Internal::Storage::Cloud::CloudStore::CloudStoreData_OldCreateInstance(
            (Windows::Internal::Storage::Cloud::CloudStore *)a1,
            v62,
            a4,
            string,
            v28,
            v29,
            &v66);
    if ( v67 )
      wil::com_ptr_t<Windows::Internal::Storage::Cloud::State::ICloudStoreStateManager,wil::err_exception_policy>::attach(
        p_pv,
        v66);
    if ( v30 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x676,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
        (const char *)(unsigned int)v30,
        v50);
      wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(&v61);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v55);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v56);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pv);
      WindowsDeleteString(v54);
      v54 = 0;
      WindowsDeleteString(v53);
      v53 = 0;
      Windows::Internal::Storage::Cloud::CloudStoreTelemetry::DeleteActivity::~DeleteActivity((Windows::Internal::Storage::Cloud::CloudStoreTelemetry::DeleteActivity *)v71);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&hObject);
      result = (unsigned int)v30;
    }
    else
    {
      v31 = v61;
      v32 = (Windows::Internal::Storage::Cloud::CloudStoreSaveResult *)operator new(
                                                                         0x50u,
                                                                         (const struct std::nothrow_t *)std::nothrow);
      if ( v32 )
        v33 = Windows::Internal::Storage::Cloud::CloudStoreSaveResult::CloudStoreSaveResult(v32, v31);
      else
        v33 = 0;
      if ( v33 )
      {
        v63 = 0;
        *v64 = v33;
        if ( (Microsoft_Windows_CloudStoreEnableBits & 2) != 0 )
        {
          std::wstring::wstring(&p_pv);
          LODWORD(v59) = 1;
          v39 = (_QWORD *)WideStringToUtf8String(v70, &p_pv);
          v10 = 3;
          if ( v39[3] > 0xFu )
            v39 = (_QWORD *)*v39;
          McTemplateU0sx_EventWriteTransfer(v41, v40, v39, v29);
        }
        if ( (v10 & 2) != 0 )
        {
          v10 &= ~2u;
          std::string::_Tidy_deallocate(v70);
        }
        if ( (v10 & 1) != 0 && v68 > 7 )
          std::_Deallocate<16>(p_pv, 2 * v68 + 2);
        wil::ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
          v71,
          0);
        Windows::Internal::Storage::Cloud::CloudStoreTelemetry::DeleteActivity::Stop(
          (Windows::Internal::Storage::Cloud::CloudStoreTelemetry::DeleteActivity *)v71,
          byte_1802299F5,
          v29,
          &GUID_NULL,
          1);
        if ( v61 )
          (*(void (__fastcall **)(struct Windows::Internal::Storage::Cloud::ICloudStoreData *))(*(_QWORD *)v61 + 16LL))(v61);
        v34 = v55;
        if ( v55 )
        {
          v55 = 0;
          (*(void (__fastcall **)(struct Windows::Storage::Streams::IBuffer *))(*(_QWORD *)v34 + 16LL))(v34);
        }
        v35 = v56;
        if ( v56 )
        {
          v56 = 0;
          (*(void (__fastcall **)(struct Windows::Storage::Streams::IBuffer *))(*(_QWORD *)v35 + 16LL))(v35);
        }
        if ( pv )
          CoTaskMemFree(pv);
        WindowsDeleteString(v54);
        v54 = 0;
        WindowsDeleteString(v53);
        v53 = 0;
        v71[0] = &Windows::Internal::Storage::Cloud::CloudStoreTelemetry::DeleteActivity::`vftable';
        wil::ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v71);
        wil::ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v71);
        if ( hObject != (HANDLE)-1LL )
          wil::details::RevertImpersonateToken(hObject, v36);
        result = 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x678,
          (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
          (const char *)0x8007000ELL,
          v50);
        if ( v61 )
          (*(void (__fastcall **)(struct Windows::Internal::Storage::Cloud::ICloudStoreData *))(*(_QWORD *)v61 + 16LL))(v61);
        v42 = v55;
        if ( v55 )
        {
          v55 = 0;
          (*(void (__fastcall **)(struct Windows::Storage::Streams::IBuffer *))(*(_QWORD *)v42 + 16LL))(v42);
        }
        v43 = v56;
        if ( v56 )
        {
          v56 = 0;
          (*(void (__fastcall **)(struct Windows::Storage::Streams::IBuffer *))(*(_QWORD *)v43 + 16LL))(v43);
        }
        if ( pv )
          CoTaskMemFree(pv);
        WindowsDeleteString(v54);
        v54 = 0;
        WindowsDeleteString(v53);
        v53 = 0;
        v71[0] = &Windows::Internal::Storage::Cloud::CloudStoreTelemetry::DeleteActivity::`vftable';
        wil::ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v71);
        wil::ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v71);
        if ( hObject != (HANDLE)-1LL )
          wil::details::RevertImpersonateToken(hObject, v44);
        result = 2147942414LL;
      }
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x67E,
                           (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
                           v37);
  }
  return result;
}

```

## disassembly

```asm
0x1800393b4  push    rbx
0x1800393b6  push    rsi
0x1800393b7  push    rdi
0x1800393b8  push    r12
0x1800393ba  push    r13
0x1800393bc  push    r14
0x1800393be  push    r15
0x1800393c0  sub     rsp, 260h
0x1800393c7  mov     rax, cs:__security_cookie
0x1800393ce  xor     rax, rsp
0x1800393d1  mov     [rsp+298h+var_48], rax
0x1800393d9  mov     r12, r9
0x1800393dc  mov     rbx, r8
0x1800393df  mov     [rsp+298h+var_200], rbx
0x1800393e7  mov     [rsp+298h+var_210], edx
0x1800393ee  mov     r14, rcx
0x1800393f1  mov     r13, [rsp+298h+string]
0x1800393f9  mov     rax, [rsp+298h+arg_30]
0x180039401  mov     [rsp+298h+var_1F0], rax
0x180039409  xor     r15d, r15d
0x18003940c  mov     dword ptr [rsp+298h+var_218], r15d
0x180039414  mov     rdx, r9; HSTRING
0x180039417  call    ?ShouldUseActivityFeedForSync@CloudStore@Cloud@Storage@Internal@Windows@@AEAA_NPEAUHSTRING__@@@Z; Windows::Internal::Storage::Cloud::CloudStore::ShouldUseActivityFeedForSync(HSTRING__ *)
0x18003941c  mov     rcx, [rsp+298h]; this
0x180039424  test    al, al
0x180039426  jnz     loc_180039917
0x18003942c  lea     rcx, [r14+0C8h]
0x180039433  lea     rdx, [rsp+298h+hObject]
0x180039438  call    ?Impersonate@EffectiveUserContext@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@wil@@XZ; EffectiveUserContext::Impersonate(void)
0x18003943d  nop
0x18003943e  xor     edx, edx; length
0x180039440  mov     rcx, r12; string
0x180039443  call    cs:__imp_WindowsGetStringRawBuffer
0x180039449  mov     rsi, rax
0x18003944c  xor     edx, edx; length
0x18003944e  mov     rcx, r13; string
0x180039451  call    cs:__imp_WindowsGetStringRawBuffer
0x180039457  mov     rdi, rax
0x18003945a  xor     edx, edx; length
0x18003945c  mov     rcx, rbx; string
0x18003945f  call    cs:__imp_WindowsGetStringRawBuffer
0x180039465  mov     rbx, rax
0x180039468  lea     rdx, aDeleteactivity; "DeleteActivity"
0x18003946f  lea     rcx, [rsp+298h+var_198]
0x180039477  call    ??0?$ActivityBase@VCloudStoreTelemetry@Cloud@Storage@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18003947c  lea     rax, ??_7DeleteActivity@CloudStoreTelemetry@Cloud@Storage@Internal@Windows@@6B@; const Windows::Internal::Storage::Cloud::CloudStoreTelemetry::DeleteActivity::`vftable'
0x180039483  mov     [rsp+298h+var_198], rax
0x18003948b  mov     rax, [rsp+298h+arg_28]
0x180039493  mov     [rsp+298h+var_260], rax; unsigned __int64
0x180039498  mov     [rsp+298h+var_268], rsi; unsigned __int16 *
0x18003949d  mov     [rsp+298h+var_270], rdi; unsigned __int16 *
0x1800394a2  lea     rax, LocaleName
0x1800394a9  mov     [rsp+298h+var_278], rax; unsigned __int16 *
0x1800394ae  mov     r9, rbx; unsigned __int16 *
0x1800394b1  mov     edi, [rsp+298h+var_210]
0x1800394b8  mov     r8d, edi; unsigned int
0x1800394bb  lea     rdx, byte_1802299F5; char *
0x1800394c2  lea     rcx, [rsp+298h+var_198]; this
0x1800394ca  call    ?StartActivity@DeleteActivity@CloudStoreTelemetry@Cloud@Storage@Internal@Windows@@QEAAXPEBDIPEBG111_K@Z; Windows::Internal::Storage::Cloud::CloudStoreTelemetry::DeleteActivity::StartActivity(char const *,uint,ushort const *,ushort const *,ushort const *,ushort const *,unsigned __int64)
0x1800394cf  nop
0x1800394d0  xor     esi, esi
0x1800394d2  mov     [rsp+298h+var_248], rsi
0x1800394d7  xor     ecx, ecx; string
0x1800394d9  call    cs:__imp_WindowsDeleteString
0x1800394df  mov     [rsp+298h+var_248], rsi
0x1800394e4  lea     rax, [rsp+298h+var_248]
0x1800394e9  mov     [rsp+298h+var_278], rax; int
0x1800394ee  xor     r9d, r9d
0x1800394f1  mov     r8, [rsp+298h+var_200]
0x1800394f9  mov     edx, edi
0x1800394fb  mov     rcx, r14
0x1800394fe  call    ?GetEffectivePartition@CloudStore@Cloud@Storage@Internal@Windows@@AEAAJW4PartitionKind@2345@PEAUHSTRING__@@_NPEAPEAU7@@Z; Windows::Internal::Storage::Cloud::CloudStore::GetEffectivePartition(Windows::Internal::Storage::Cloud::PartitionKind,HSTRING__ *,bool,HSTRING__ * *)
0x180039503  mov     ebx, eax
0x180039505  test    eax, eax
0x180039507  js      loc_180039A37
0x18003950d  mov     [rsp+298h+var_240], rsi
0x180039512  xor     ecx, ecx; string
0x180039514  call    cs:__imp_WindowsDeleteString
0x18003951a  mov     [rsp+298h+var_240], rsi
0x18003951f  lea     rax, [rsp+298h+var_240]
0x180039524  mov     [rsp+298h+var_270], rax
0x180039529  mov     [rsp+298h+var_278], r13; int
0x18003952e  mov     r9, r12
0x180039531  mov     r8, [rsp+298h+var_248]
0x180039536  mov     edx, edi
0x180039538  mov     rcx, r14
0x18003953b  call    ?GetDataStoreId@CloudStore@Cloud@Storage@Internal@Windows@@AEAAJW4PartitionKind@2345@PEAUHSTRING__@@11PEAPEAU7@@Z; Windows::Internal::Storage::Cloud::CloudStore::GetDataStoreId(Windows::Internal::Storage::Cloud::PartitionKind,HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ * *)
0x180039540  mov     ebx, eax
0x180039542  test    eax, eax
0x180039544  js      loc_180039A83
0x18003954a  xor     edx, edx; length
0x18003954c  mov     rcx, [rsp+298h+var_240]; string
0x180039551  call    cs:__imp_WindowsGetStringRawBuffer
0x180039557  mov     rsi, rax
0x18003955a  call    ?IsASTAOrMainSTA@@YA_NXZ; IsASTAOrMainSTA(void)
0x18003955f  mov     rcx, [rsp+298h]; this
0x180039567  test    al, al
0x180039569  jnz     loc_180039ADF
0x18003956f  mov     rcx, [rsp+298h]; this
0x180039577  mov     rdi, [rsp+298h+arg_28]
0x18003957f  test    rdi, rdi
0x180039582  jz      loc_180039929
0x180039588  xorps   xmm0, xmm0
0x18003958b  movups  [rsp+298h+var_1C8], xmm0
0x180039593  lea     r8, [rsp+298h+var_1C8]; struct TypeAttributes *
0x18003959b  mov     rdx, rsi; unsigned __int16 *
0x18003959e  mov     rcx, r14; this
0x1800395a1  call    ?GetTypeServiceAttributesForId@CloudStore@Cloud@Storage@Internal@Windows@@AEAAJPEBGPEAUTypeAttributes@@@Z; Windows::Internal::Storage::Cloud::CloudStore::GetTypeServiceAttributesForId(ushort const *,TypeAttributes *)
0x1800395a6  mov     ebx, eax
0x1800395a8  test    eax, eax
0x1800395aa  js      loc_180039AF7
0x1800395b0  mov     [rsp+298h+pv], r15
0x1800395b5  lea     rax, [rsp+298h+pv]
0x1800395ba  mov     [rsp+298h+var_1E8], rax
0x1800395c2  mov     [rsp+298h+var_1E0], r15
0x1800395ca  mov     [rsp+298h+var_1D8], 1
0x1800395d2  lea     rcx, [r14+0E8h]
0x1800395d9  lea     r9, [rsp+298h+var_1E0]
0x1800395e1  mov     edx, dword ptr [rsp+298h+var_1C8]
0x1800395e8  call    ?GetRootFromAttribute@CloudStoreUtilities@@YAJAEBVEffectiveWebAccountContext@@W4ScopeValue@@W4TRIBIT@@PEAPEAG@Z; CloudStoreUtilities::GetRootFromAttribute(EffectiveWebAccountContext const &,ScopeValue,TRIBIT,ushort * *)
0x1800395ed  mov     ebx, eax
0x1800395ef  lea     rcx, [rsp+298h+var_1E8]
0x1800395f7  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x1800395fc  xor     eax, eax
0x1800395fe  test    ebx, ebx
0x180039600  js      loc_180039B5B
0x180039606  mov     [rsp+298h+var_230], rax
0x18003960b  mov     [rsp+298h+var_1F8], rax
0x180039613  mov     [rsp+298h+var_238], rax
0x180039618  mov     [rsp+298h+var_218], rax
0x180039620  lea     rcx, [rsp+298h+var_238]
0x180039625  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003962a  lea     rcx, [rsp+298h+var_230]
0x18003962f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180039634  lea     rax, [rsp+298h+var_218]
0x18003963c  mov     [rsp+298h+var_250], rax; unsigned __int64 *
0x180039641  lea     rax, [rsp+298h+var_238]
0x180039646  mov     [rsp+298h+var_258], rax; struct Windows::Storage::Streams::IBuffer **
0x18003964b  lea     rax, [rsp+298h+var_1F8]
0x180039653  mov     [rsp+298h+var_260], rax; unsigned __int64 *
0x180039658  lea     rax, [rsp+298h+var_230]
0x18003965d  mov     [rsp+298h+var_268], rax; struct Windows::Storage::Streams::IBuffer **
0x180039662  mov     [rsp+298h+var_270], rdi; unsigned __int64
0x180039667  xor     edi, edi
0x180039669  mov     [rsp+298h+var_278], rdi; int
0x18003966e  xor     r9d, r9d; unsigned __int64
0x180039671  xor     r8d, r8d; struct Windows::Storage::Streams::IBuffer *
0x180039674  mov     rdx, rsi; unsigned __int16 *
0x180039677  mov     rcx, r14; this
0x18003967a  call    ?LoadAndResolveInternal@CloudStore@Cloud@Storage@Internal@Windows@@AEAAJPEBGPEAUIBuffer@Streams@35@_K12PEAPEAU6735@PEA_K34@Z; Windows::Internal::Storage::Cloud::CloudStore::LoadAndResolveInternal(ushort const *,Windows::Storage::Streams::IBuffer *,unsigned __int64,Windows::Storage::Streams::IBuffer *,unsigned __int64,Windows::Storage::Streams::IBuffer * *,unsigned __int64 *,Windows::Storage::Streams::IBuffer * *,unsigned __int64 *)
0x18003967f  mov     ebx, eax
0x180039681  test    eax, eax
0x180039683  js      loc_180039BCA
0x180039689  mov     rax, [rsp+298h+var_238]
0x18003968e  test    rax, rax
0x180039691  jz      loc_180039C47
0x180039697  mov     rbx, [rsp+298h+var_218]
0x18003969f  mov     [rsp+298h+var_208], rdi
0x1800396a7  lea     rcx, [rsp+298h+var_208]
0x1800396af  mov     [rsp+298h+var_1E8], rcx
0x1800396b7  mov     [rsp+298h+var_1E0], rdi
0x1800396bf  mov     [rsp+298h+var_1D8], 1
0x1800396c7  lea     rcx, [rsp+298h+var_1E0]
0x1800396cf  mov     [rsp+298h+var_268], rcx; struct Windows::Internal::Storage::Cloud::ICloudStoreData **
0x1800396d4  mov     [rsp+298h+var_270], rbx; unsigned __int64
0x1800396d9  mov     [rsp+298h+var_278], rax; int
0x1800396de  mov     r9, r13; HSTRING
0x1800396e1  mov     r8, r12; HSTRING
0x1800396e4  mov     rdx, [rsp+298h+var_200]; HSTRING
0x1800396ec  mov     rcx, r14; this
0x1800396ef  call    ?CloudStoreData_OldCreateInstance@CloudStore@Cloud@Storage@Internal@Windows@@QEAAJPEAUHSTRING__@@00PEAUIBuffer@Streams@35@_KPEAPEAUICloudStoreData@2345@@Z; Windows::Internal::Storage::Cloud::CloudStore::CloudStoreData_OldCreateInstance(HSTRING__ *,HSTRING__ *,HSTRING__ *,Windows::Storage::Streams::IBuffer *,unsigned __int64,Windows::Internal::Storage::Cloud::ICloudStoreData * *)
0x1800396f4  mov     edi, eax
0x1800396f6  xor     r14d, r14d
0x1800396f9  cmp     [rsp+298h+var_1D8], r14b
0x180039701  jz      short loc_180039718
0x180039703  mov     rdx, [rsp+298h+var_1E0]
0x18003970b  mov     rcx, [rsp+298h+var_1E8]
0x180039713  call    ?attach@?$com_ptr_t@VICloudStoreStateManager@State@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAAXPEAVICloudStoreStateManager@State@Cloud@Storage@Internal@Windows@@@Z; wil::com_ptr_t<Windows::Internal::Storage::Cloud::State::ICloudStoreStateManager,wil::err_exception_policy>::attach(Windows::Internal::Storage::Cloud::State::ICloudStoreStateManager *)
0x180039718  test    edi, edi
0x18003971a  js      loc_180039DC6
0x180039720  mov     rdi, [rsp+298h+var_208]
0x180039728  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003972f  mov     ecx, 50h ; 'P'; unsigned __int64
0x180039734  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180039739  test    rax, rax
0x18003973c  jnz     loc_180039907
0x180039742  mov     rax, r14
0x180039745  test    rax, rax
0x180039748  jz      loc_18003993B
0x18003974e  mov     [rsp+298h+var_1F8], r14
0x180039756  mov     rcx, [rsp+298h+var_1F0]
0x18003975e  mov     [rcx], rax
0x180039761  test    cs:Microsoft_Windows_CloudStoreEnableBits, 2
0x180039768  jnz     loc_1800398B6
0x18003976e  test    r15b, 2
0x180039772  jnz     loc_180039A21
0x180039778  test    r15b, 1
0x18003977c  jz      short loc_1800397A1
0x18003977e  mov     rdx, [rsp+298h+var_1D0]
0x180039786  cmp     rdx, 7
0x18003978a  jbe     short loc_1800397A1
0x18003978c  lea     rdx, ds:2[rdx*2]
0x180039794  mov     rcx, [rsp+298h+var_1E8]
0x18003979c  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800397a1  xor     edx, edx
0x1800397a3  lea     rcx, [rsp+298h+var_198]
0x1800397ab  call    ?SetStopResult@?$ActivityBase@VCloudStoreTelemetry@Cloud@Storage@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXJPEAJ@Z; wil::ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x1800397b0  mov     byte ptr [rsp+298h+var_278], 1; bool
0x1800397b5  lea     r9, GUID_NULL; struct _GUID *
0x1800397bc  mov     r8, rbx; unsigned __int64
0x1800397bf  lea     rdx, byte_1802299F5; char *
0x1800397c6  lea     rcx, [rsp+298h+var_198]; this
0x1800397ce  call    ?Stop@DeleteActivity@CloudStoreTelemetry@Cloud@Storage@Internal@Windows@@QEAAXPEBD_KAEBU_GUID@@_N@Z; Windows::Internal::Storage::Cloud::CloudStoreTelemetry::DeleteActivity::Stop(char const *,unsigned __int64,_GUID const &,bool)
0x1800397d3  nop
0x1800397d4  mov     rcx, [rsp+298h+var_208]
0x1800397dc  test    rcx, rcx
0x1800397df  jz      short loc_1800397EE
0x1800397e1  mov     rax, [rcx]
0x1800397e4  mov     rax, [rax+10h]
0x1800397e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800397ed  nop
0x1800397ee  mov     rcx, [rsp+298h+var_238]
0x1800397f3  test    rcx, rcx
0x1800397f6  jz      short loc_18003980A
0x1800397f8  mov     [rsp+298h+var_238], r14
0x1800397fd  mov     rax, [rcx]
0x180039800  mov     rax, [rax+10h]
0x180039804  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039809  nop
0x18003980a  mov     rcx, [rsp+298h+var_230]
0x18003980f  test    rcx, rcx
0x180039812  jz      short loc_180039826
0x180039814  mov     [rsp+298h+var_230], r14
0x180039819  mov     rax, [rcx]
0x18003981c  mov     rax, [rax+10h]
0x180039820  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039825  nop
0x180039826  mov     rcx, [rsp+298h+pv]; pv
0x18003982b  test    rcx, rcx
0x18003982e  jz      short loc_180039837
0x180039830  call    cs:__imp_CoTaskMemFree
0x180039836  nop
0x180039837  mov     rcx, [rsp+298h+var_240]; string
0x18003983c  call    cs:__imp_WindowsDeleteString
0x180039842  mov     [rsp+298h+var_240], r14
0x180039847  mov     rcx, [rsp+298h+var_248]; string
0x18003984c  call    cs:__imp_WindowsDeleteString
0x180039852  mov     [rsp+298h+var_248], r14
0x180039857  lea     rax, ??_7DeleteActivity@CloudStoreTelemetry@Cloud@Storage@Internal@Windows@@6B@; const Windows::Internal::Storage::Cloud::CloudStoreTelemetry::DeleteActivity::`vftable'
0x18003985e  mov     [rsp+298h+var_198], rax
0x180039866  lea     rcx, [rsp+298h+var_198]
0x18003986e  call    ?Destroy@?$ActivityBase@VCloudStoreTelemetry@Cloud@Storage@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180039873  lea     rcx, [rsp+298h+var_198]
0x18003987b  call    ??1?$ActivityBase@VCloudStoreTelemetry@Cloud@Storage@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x180039880  nop
0x180039881  mov     rcx, [rsp+298h+hObject]; hObject
0x180039886  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18003988a  jz      short loc_180039891
0x18003988c  call    ?RevertImpersonateToken@details@wil@@YAXPEAX@Z; wil::details::RevertImpersonateToken(void *)
0x180039891  xor     eax, eax
0x180039893  mov     rcx, [rsp+298h+var_48]
0x18003989b  xor     rcx, rsp; StackCookie
0x18003989e  call    __security_check_cookie
0x1800398a3  add     rsp, 260h
0x1800398aa  pop     r15
0x1800398ac  pop     r14
0x1800398ae  pop     r13
0x1800398b0  pop     r12
0x1800398b2  pop     rdi
0x1800398b3  pop     rsi
0x1800398b4  pop     rbx
0x1800398b5  retn
0x1800398b6  mov     rdx, rsi
0x1800398b9  lea     rcx, [rsp+298h+var_1E8]
0x1800398c1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800398c6  nop
0x1800398c7  mov     dword ptr [rsp+298h+var_218], 1
0x1800398d2  lea     rdx, [rsp+298h+var_1E8]
0x1800398da  lea     rcx, [rsp+298h+var_1B8]
0x1800398e2  call    ?WideStringToUtf8String@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; WideStringToUtf8String(std::wstring const &)
0x1800398e7  mov     r15d, 3
0x1800398ed  mov     r9, rbx
0x1800398f0  cmp     qword ptr [rax+18h], 0Fh
0x1800398f5  jbe     short loc_1800398FA
0x1800398f7  mov     rax, [rax]
0x1800398fa  mov     r8, rax
0x1800398fd  call    McTemplateU0sx_EventWriteTransfer
0x180039902  jmp     loc_18003976E
0x180039907  mov     rdx, rdi; struct Windows::Internal::Storage::Cloud::ICloudStoreData *
0x18003990a  mov     rcx, rax; this
0x18003990d  call    ??0CloudStoreSaveResult@Cloud@Storage@Internal@Windows@@QEAA@PEAUICloudStoreData@1234@@Z; Windows::Internal::Storage::Cloud::CloudStoreSaveResult::CloudStoreSaveResult(Windows::Internal::Storage::Cloud::ICloudStoreData *)
0x180039912  jmp     loc_180039745
0x180039917  lea     r8, aOnecoreuapShel_44; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x18003991e  mov     edx, 64Eh; void *
0x180039923  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180039929  lea     r8, aOnecoreuapShel_44; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x180039930  mov     edx, 661h; void *
0x180039935  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18003993b  mov     rcx, [rsp+298h]; this
0x180039943  mov     ebx, 8007000Eh
  ... truncated ...
```
