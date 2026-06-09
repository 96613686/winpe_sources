# SessionManagerBrokerImpl::Start(wchar_t const *,wchar_t const *,__MIDL___MIDL_itf_iupdatemodelcacheondriverupdate_0000_0000_0001,IUpdateModelCacheOnDriverUpdateEvents *,char const *,unsigned __int64 *)

- ea: `0x180065ea0`
- end: `0x18006697d`
- name: `?Start@SessionManagerBrokerImpl@@UEAAJPEB_W0W4__MIDL___MIDL_itf_iupdatemodelcacheondriverupdate_0000_0000_0001@@PEAUIUpdateModelCacheOnDriverUpdateEvents@@PEBDPEA_K@Z`
- size: `2781`
- prototype: `__int64 __fastcall(__int64, const wchar_t *, wchar_t *, int, struct IUnknown *, char *, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `27`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180004ca0`
- `0x180005140`
- `0x180005758`
- `0x180007ad0`
- `0x18000b044`
- `0x18000b064`
- `0x1800189b8`
- `0x180054f34`
- `0x1800556b8`
- `0x180059d4c`
- `0x180059dd0`
- `0x18005a140`
- `0x18005a438`
- `0x18005a5e8`
- `0x18005b580`
- `0x18005c8dc`
- `0x18005cdd0`
- `0x18005d270`
- `0x18006180c`
- `0x180065c04`
- `0x180065ea0`
- `0x180067270`
- `0x18006870c`
- `0x180069cec`
- `0x18006a284`
- `0x18006c26c`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066190`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066190`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800661a3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800661a3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800661ae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800661ae`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800661c7`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800661c7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006619b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180066206`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800662ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006646e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180066603`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180066820`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800668d4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006619b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180066206`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800662ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006646e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180066603`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180066820`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800668d4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800660c7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800660c7`
- `msvcp_win!_Mtx_unlock` at `0x1800663c3`
- `msvcp_win!_Mtx_unlock` at `0x1800666d0`
- `msvcp_win!_Mtx_unlock` at `0x1800663c3`
- `msvcp_win!_Mtx_unlock` at `0x1800666d0`
- `msvcp_win!_Mtx_lock` at `0x180066366`
- `msvcp_win!_Mtx_lock` at `0x18006668b`
- `msvcp_win!_Mtx_lock` at `0x180066366`
- `msvcp_win!_Mtx_lock` at `0x18006668b`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180066375`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18006638f`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18006669a`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800666b4`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180066375`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18006638f`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18006669a`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800666b4`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800661f0`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180066267`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800661f0`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180066267`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18006616b`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18006616b`

## string_xrefs

- `0x18006696a`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x1800660ce`: `UpdateModelCacheOnDriverUpdateStart`
- `0x180065f2d`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\sessionmanagerbrokerimpl.cpp`
- `0x180065f5a`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\sessionmanagerbrokerimpl.cpp`
- `0x180065f87`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\sessionmanagerbrokerimpl.cpp`
- `0x180065fb4`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\sessionmanagerbrokerimpl.cpp`
- `0x180066009`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\sessionmanagerbrokerimpl.cpp`
- `0x180066084`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\sessionmanagerbrokerimpl.cpp`
- `0x1800661dd`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\sessionmanagerbrokerimpl.cpp`
- `0x18006628a`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\sessionmanagerbrokerimpl.cpp`
- `0x180066565`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\sessionmanagerbrokerimpl.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall SessionManagerBrokerImpl::Start(
        __int64 a1,
        const wchar_t *a2,
        wchar_t *a3,
        int a4,
        struct IUnknown *a5,
        char *a6,
        unsigned __int64 *a7)
{
  __int64 result; // rax
  bool v9; // dl
  TraceLoggingCorrelationVector *v10; // rax
  TraceLoggingCorrelationVector *v11; // r15
  const char *v12; // r9
  TraceLoggingCorrelationVector *v13; // rax
  TraceLoggingCorrelationVector *v14; // rdi
  HRESULT v15; // eax
  HANDLE v16; // rsi
  DWORD LastError; // edi
  HANDLE CurrentThread; // rax
  const char *v19; // r9
  unsigned int v20; // ebx
  int v21; // eax
  unsigned int v22; // edi
  __int64 v23; // rdi
  __int64 v24; // rdi
  _QWORD *v25; // rcx
  _QWORD *i; // rax
  volatile signed __int32 *v27; // rdi
  volatile signed __int32 *v28; // rdi
  wil *v29; // rcx
  __int64 updated; // rdi
  SessionManagerBrokerImpl *v31; // rcx
  int v32; // eax
  unsigned int v33; // esi
  volatile signed __int32 *v34; // rdi
  __int64 v35; // rbx
  __int64 v36; // rdi
  const wchar_t *v37; // rsi
  __int64 v38; // rbx
  _QWORD *v39; // rax
  volatile signed __int32 *v40; // rdi
  volatile signed __int32 *v41; // rdi
  volatile signed __int32 *v42; // rdi
  volatile signed __int32 *v43; // rdi
  int v44; // [rsp+20h] [rbp-2F8h]
  int v45; // [rsp+20h] [rbp-2F8h]
  int v46; // [rsp+20h] [rbp-2F8h]
  int v47; // [rsp+20h] [rbp-2F8h]
  bool v48; // [rsp+30h] [rbp-2E8h] BYREF
  HANDLE hObject; // [rsp+38h] [rbp-2E0h] BYREF
  int v50; // [rsp+40h] [rbp-2D8h] BYREF
  unsigned __int64 v51; // [rsp+48h] [rbp-2D0h] BYREF
  signed __int64 v52; // [rsp+50h] [rbp-2C8h] BYREF
  void *v53; // [rsp+58h] [rbp-2C0h]
  const wchar_t *v54; // [rsp+60h] [rbp-2B8h] BYREF
  volatile signed __int32 *v55; // [rsp+68h] [rbp-2B0h]
  wchar_t *v56; // [rsp+70h] [rbp-2A8h]
  __int64 v57; // [rsp+78h] [rbp-2A0h]
  volatile signed __int32 *v58; // [rsp+80h] [rbp-298h]
  int v59[2]; // [rsp+88h] [rbp-290h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+90h] [rbp-288h] BYREF
  struct IUnknown *v61; // [rsp+98h] [rbp-280h] BYREF
  __int64 v62; // [rsp+A0h] [rbp-278h]
  unsigned __int64 *v63; // [rsp+A8h] [rbp-270h]
  char v64[8]; // [rsp+B0h] [rbp-268h] BYREF
  volatile signed __int32 *v65; // [rsp+B8h] [rbp-260h]
  unsigned __int64 *v66; // [rsp+C0h] [rbp-258h]
  bool *v67; // [rsp+C8h] [rbp-250h]
  _QWORD *v68; // [rsp+D0h] [rbp-248h]
  char *v69; // [rsp+D8h] [rbp-240h]
  char v70; // [rsp+E0h] [rbp-238h]
  _QWORD v71[42]; // [rsp+F0h] [rbp-228h] BYREF
  char v72[144]; // [rsp+240h] [rbp-D8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+318h] [rbp+0h]

  v59[0] = a4;
  v56 = a3;
  v52 = (signed __int64)a2;
  v62 = a1;
  v54 = a2;
  v50 = a4;
  v61 = a5;
  v63 = a7;
  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3CD,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\sessionmanagerbrokerimpl.cpp",
      (const char *)0x80070057LL,
      v45);
    return 2147942487LL;
  }
  if ( !a3 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3CE,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\sessionmanagerbrokerimpl.cpp",
      (const char *)0x80070057LL,
      v45);
    return 2147942487LL;
  }
  if ( !a5 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3CF,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\sessionmanagerbrokerimpl.cpp",
      (const char *)0x80070057LL,
      v45);
    return 2147942487LL;
  }
  if ( !a7 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3D0,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\sessionmanagerbrokerimpl.cpp",
      (const char *)0x80070057LL,
      v45);
    return 2147942487LL;
  }
  try
  {
    v53 = 0;
    if ( a6 && (unsigned __int8)TraceLoggingCorrelationVector::ValidateImpl(a6, 0) )
    {
      v10 = TraceLoggingCorrelationVector::Extend(a6, v9);
      v11 = v10;
      v53 = v10;
      if ( !v10 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3DA,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\sessionmanagerbrokerimpl.cpp",
          (const char *)0x8007000ELL,
          v45);
        return 2147942414LL;
      }
    }
    else
    {
      v13 = (TraceLoggingCorrelationVector *)operator new(0x90u);
      v10 = TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(v13);
      v11 = v10;
      v53 = v10;
    }
    v14 = v10;
    memset_0(v72, 0, 0x81u);
    if ( TraceLoggingCorrelationVector::ToString(v11, v72) )
    {
      v48 = 0;
      v51 = 0;
      SystemTimeAsFileTime = 0;
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
        v71,
        "UpdateModelCacheOnDriverUpdateStart");
      v71[0] = &TelemetryLogger::UpdateModelCacheOnDriverUpdateStart::`vftable';
      TelemetryLogger::UpdateModelCacheOnDriverUpdateStart::StartActivity(
        (TelemetryLogger::UpdateModelCacheOnDriverUpdateStart *)v71,
        a2,
        v59[0],
        SystemTimeAsFileTime,
        v72);
      v66 = &v51;
      v67 = &v48;
      v68 = v71;
      v69 = v72;
      v70 = 1;
      wil::init_once<void (*)(void)>();
      hObject = 0;
      v15 = CoImpersonateClient();
      if ( v15 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x14B1,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
          (const char *)(unsigned int)v15,
          v46);
      v16 = hObject;
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      {
        LastError = GetLastError();
        CloseHandle(v16);
        SetLastError(LastError);
      }
      hObject = 0;
      CurrentThread = GetCurrentThread();
      if ( OpenThreadToken(CurrentThread, 0xEu, 1, &hObject) )
      {
        CoRevertToSelf();
        v21 = SetProxyBlanketImpersonationLevelAndDynamicCloaking(a5);
        v22 = v21;
        if ( v21 >= 0 )
        {
          v23 = v62;
          ThreadSafeContainer_std::list_std::shared_ptr_SessionManagerBrokerImpl::UpdateModelCacheOnDriverUpdate__std::allocator_std::shared_ptr_SessionManagerBrokerImpl::UpdateModelCacheOnDriverUpdate_______::Find__lambda_6244c2e93103651f21cd979fc257d526____((_Mtx_t)(v62 + 40));
          if ( v57 )
          {
            std::make_shared<EventsPair,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,IUpdateModelCacheOnDriverUpdateEvents * &>(
              &v54,
              &hObject,
              &v61);
            v24 = v57 + 80;
            v56 = (wchar_t *)(v57 + 80);
            if ( _Mtx_lock((_Mtx_t)(v57 + 80)) )
              std::_Throw_Cpp_error(5);
            if ( *(_DWORD *)(v24 + 76) == 0x7FFFFFFF )
            {
              *(_DWORD *)(v24 + 76) = 2147483646;
              std::_Throw_Cpp_error(6);
            }
            v25 = *(_QWORD **)(v24 + 80);
            for ( i = (_QWORD *)*v25; i != v25; i = (_QWORD *)*i )
            {
              if ( *(struct IUnknown **)(i[2] + 8LL) == a5 )
                goto LABEL_43;
            }
            std::list<std::shared_ptr<EventsPair>>::push_back(v24 + 80, &v54);
LABEL_43:
            _Mtx_unlock((_Mtx_t)v24);
            *v63 = *(_QWORD *)(v57 + 40);
            v27 = v55;
            if ( v55 )
            {
              if ( _InterlockedExchangeAdd(v55 + 2, 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v27)(v27);
                if ( _InterlockedExchangeAdd(v27 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v27 + 8LL))(v27);
              }
            }
            v28 = v58;
            if ( v58 )
            {
              if ( _InterlockedExchangeAdd(v58 + 2, 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v28)(v28);
                if ( _InterlockedExchangeAdd(v28 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v28 + 8LL))(v28);
              }
            }
            if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
              CloseHandle(hObject);
            TelemetryLogger::UpdateModelCacheOnDriverUpdateStart::Stop(
              (TelemetryLogger::UpdateModelCacheOnDriverUpdateStart *)v71,
              v51,
              v48,
              v72);
            v71[0] = &TelemetryLogger::UpdateModelCacheOnDriverUpdateStart::`vftable';
            wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v71);
            wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v71);
            if ( v11 )
              operator delete(v11, 0x90u);
            return 0;
          }
          try
          {
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v23 + 32) + 72LL))(*(_QWORD *)(v23 + 32));
          }
          catch ( ... )
          {
            v50 = wil::ResultFromCaughtException(v29);
            TelemetryLogger::UpdateModelCacheOnDriverUpdateStart::UpdateModelCacheOnDriverUpdateWinAppSDKRegistrationFailed<long>(
              &v50,
              v72);
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x411,
              (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\sessionmanagerbrokerimpl.cpp",
              (const char *)0x80073CF6LL,
              v44);
            v43 = v58;
            if ( v58 )
            {
              if ( _InterlockedExchangeAdd(v58 + 2, 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v43)(v43);
                if ( _InterlockedExchangeAdd(v43 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v43 + 8LL))(v43);
              }
            }
            if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
              CloseHandle(hObject);
            TelemetryLogger::UpdateModelCacheOnDriverUpdateStart::Stop(
              (TelemetryLogger::UpdateModelCacheOnDriverUpdateStart *)v71,
              v51,
              v48,
              v72);
            v71[0] = &TelemetryLogger::UpdateModelCacheOnDriverUpdateStart::`vftable';
            wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v71);
            wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v71);
            if ( v53 )
              operator delete(v53, 0x90u);
            return 2147958006LL;
          }
          v52 = _InterlockedIncrement64(&SessionManagerBrokerImpl::s_cookieCount);
          *(_QWORD *)v59 = operator new(0xE8u);
          updated = std::_Ref_count_obj2<SessionManagerBrokerImpl::UpdateModelCacheOnDriverUpdate>::_Ref_count_obj2<SessionManagerBrokerImpl::UpdateModelCacheOnDriverUpdate>(
                      v59[0],
                      (unsigned int)&v54,
                      (unsigned int)&v50,
                      (unsigned int)&v52,
                      (__int64)v72);
          v54 = (const wchar_t *)(updated + 16);
          v55 = (volatile signed __int32 *)updated;
          v32 = SessionManagerBrokerImpl::CopyDriverToLocalStorage(
                  v31,
                  v56,
                  (struct SessionManagerBrokerImpl::UpdateModelCacheOnDriverUpdate *)(updated + 16),
                  (struct TelemetryLogger::UpdateModelCacheOnDriverUpdateStart *)v71);
          v33 = v32;
          if ( v32 >= 0 )
          {
            std::make_shared<EventsPair,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,IUpdateModelCacheOnDriverUpdateEvents * &>(
              v64,
              &hObject,
              &v61);
            v56 = (wchar_t *)(updated + 96);
            if ( _Mtx_lock((_Mtx_t)(updated + 96)) )
              std::_Throw_Cpp_error(5);
            if ( *(_DWORD *)(updated + 172) == 0x7FFFFFFF )
            {
              *(_DWORD *)(updated + 172) = 2147483646;
              std::_Throw_Cpp_error(6);
            }
            std::list<std::shared_ptr<EventsPair>>::push_back(updated + 176, v64);
            _Mtx_unlock((_Mtx_t)(updated + 96));
            v35 = v62;
            ThreadSafeContainer<std::list<std::shared_ptr<SessionManagerBrokerImpl::UpdateModelCacheOnDriverUpdate>>>::Insert(
              v62 + 40,
              &v54);
            v36 = v35 - 24;
            v37 = v54;
            v38 = *((_QWORD *)v54 + 5);
            v39 = operator new(0x3B0u);
            v39[1] = SessionManagerBrokerImpl::CacheModels__DestroyCoro_2;
            *v39 = SessionManagerBrokerImpl::CacheModels__ResumeCoro_1;
            v39[3] = v36;
            v39[4] = v38;
            *((_DWORD *)v39 + 10) = 65538;
            *((_BYTE *)v39 + 17) = 0;
            SessionManagerBrokerImpl::CacheModels__ResumeCoro_1(v39);
            v51 = *((_QWORD *)v37 + 5);
            *v63 = v51;
            v48 = 1;
            v40 = v65;
            if ( v65 )
            {
              if ( _InterlockedExchangeAdd(v65 + 2, 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v40)(v40);
                if ( _InterlockedExchangeAdd(v40 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v40 + 8LL))(v40);
              }
            }
            v41 = v55;
            if ( v55 )
            {
              if ( _InterlockedExchangeAdd(v55 + 2, 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v41)(v41);
                if ( _InterlockedExchangeAdd(v41 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v41 + 8LL))(v41);
              }
            }
            v42 = v58;
            if ( v58 )
            {
              if ( _InterlockedExchangeAdd(v58 + 2, 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v42)(v42);
                if ( _InterlockedExchangeAdd(v42 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v42 + 8LL))(v42);
              }
            }
            if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
              CloseHandle(hObject);
            TelemetryLogger::UpdateModelCacheOnDriverUpdateStart::Stop(
              (TelemetryLogger::UpdateModelCacheOnDriverUpdateStart *)v71,
              v51,
              v48,
              v72);
            v71[0] = &TelemetryLogger::UpdateModelCacheOnDriverUpdateStart::`vftable';
            wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v71);
            wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v71);
            if ( v11 )
              operator delete(v11, 0x90u);
            return 0;
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x416,
              (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\sessionmanagerbrokerimpl.cpp",
              (const char *)(unsigned int)v32,
              v47);
            if ( updated )
            {
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)(updated + 8), 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(__int64))updated)(updated);
                if ( _InterlockedExchangeAdd((volatile signed __int32 *)(updated + 12), 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)updated + 8LL))(updated);
              }
            }
            v34 = v58;
            if ( v58 )
            {
              if ( _InterlockedExchangeAdd(v58 + 2, 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v34)(v34);
                if ( _InterlockedExchangeAdd(v34 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v34 + 8LL))(v34);
              }
            }
            if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
              CloseHandle(hObject);
            TelemetryLogger::UpdateModelCacheOnDriverUpdateStart::Stop(
              (TelemetryLogger::UpdateModelCacheOnDriverUpdateStart *)v71,
              v51,
              v48,
              v72);
            v71[0] = &TelemetryLogger::UpdateModelCacheOnDriverUpdateStart::`vftable';
            wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v71);
            wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v71);
            if ( v11 )
              operator delete(v11, 0x90u);
            return v33;
          }
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3F5,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\sessionmanagerbrokerimpl.cpp",
          (const char *)(unsigned int)v21,
          v46);
        if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          CloseHandle(hObject);
        TelemetryLogger::UpdateModelCacheOnDriverUpdateStart::Stop(
          (TelemetryLogger::UpdateModelCacheOnDriverUpdateStart *)v71,
          v51,
          v48,
          v72);
        v71[0] = &TelemetryLogger::UpdateModelCacheOnDriverUpdateStart::`vftable';
        wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v71);
        wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v71);
        if ( v11 )
          operator delete(v11, 0x90u);
        result = v22;
      }
      else
      {
        v20 = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x3F3,
                (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\sessionmanagerbrokerimpl.cpp",
                v19);
        CoRevertToSelf();
        if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          CloseHandle(hObject);
        TelemetryLogger::UpdateModelCacheOnDriverUpdateStart::Stop(
          (TelemetryLogger::UpdateModelCacheOnDriverUpdateStart *)v71,
          v51,
          v48,
          v72);
        v71[0] = &TelemetryLogger::UpdateModelCacheOnDriverUpdateStart::`vftable';
        wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v71);
        wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v71);
        if ( v11 )
          operator delete(v11, 0x90u);
        result = v20;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3DE,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\sessionmanagerbrokerimpl.cpp",
        (const char *)0x8007000ELL,
        v45);
      if ( v14 )
        operator delete(v14, 0x90u);
      result = 2147942414LL;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x422,
                           (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\sessionman"
                                         "agerbrokerimpl.cpp",
                           v12);
  }
  return result;
}

```

## disassembly

```asm
0x180065ea0  push    rbx
0x180065ea2  push    rsi
0x180065ea3  push    rdi
0x180065ea4  push    r12
0x180065ea6  push    r13
0x180065ea8  push    r14
0x180065eaa  push    r15
0x180065eac  sub     rsp, 2E0h
0x180065eb3  mov     rax, cs:__security_cookie
0x180065eba  xor     rax, rsp
0x180065ebd  mov     [rsp+318h+var_48], rax
0x180065ec5  mov     eax, r9d
0x180065ec8  mov     [rsp+318h+var_290], eax
0x180065ecf  mov     [rsp+318h+var_2A8], r8
0x180065ed4  mov     rsi, rdx
0x180065ed7  mov     [rsp+318h+var_2C8], rdx
0x180065edc  mov     [rsp+318h+var_278], rcx
0x180065ee4  mov     rbx, [rsp+318h+arg_20]
0x180065eec  mov     [rsp+318h+var_2B8], rdx
0x180065ef1  mov     [rsp+318h+var_2D8], eax
0x180065ef5  mov     [rsp+318h+var_280], rbx
0x180065efd  mov     rdi, [rsp+318h+arg_28]
0x180065f05  mov     rax, [rsp+318h+arg_30]
0x180065f0d  mov     [rsp+318h+var_270], rax
0x180065f15  xor     r14d, r14d
0x180065f18  test    rdx, rdx
0x180065f1b  jnz     short loc_180065F45
0x180065f1d  mov     rcx, [rsp+318h]; this
0x180065f25  mov     ebx, 80070057h
0x180065f2a  mov     r9d, ebx; char *
0x180065f2d  lea     r8, aOnecoreuapBase_11; "onecoreuap\\base\\appmodel\\search\\com"...
0x180065f34  mov     edx, 3CDh; void *
0x180065f39  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180065f3e  mov     eax, ebx
0x180065f40  jmp     loc_180066944
0x180065f45  test    r8, r8
0x180065f48  jnz     short loc_180065F72
0x180065f4a  mov     rcx, [rsp+318h]; this
0x180065f52  mov     ebx, 80070057h
0x180065f57  mov     r9d, ebx; char *
0x180065f5a  lea     r8, aOnecoreuapBase_11; "onecoreuap\\base\\appmodel\\search\\com"...
0x180065f61  mov     edx, 3CEh; void *
0x180065f66  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180065f6b  mov     eax, ebx
0x180065f6d  jmp     loc_180066944
0x180065f72  test    rbx, rbx
0x180065f75  jnz     short loc_180065F9F
0x180065f77  mov     rcx, [rsp+318h]; this
0x180065f7f  mov     ebx, 80070057h
0x180065f84  mov     r9d, ebx; char *
0x180065f87  lea     r8, aOnecoreuapBase_11; "onecoreuap\\base\\appmodel\\search\\com"...
0x180065f8e  mov     edx, 3CFh; void *
0x180065f93  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180065f98  mov     eax, ebx
0x180065f9a  jmp     loc_180066944
0x180065f9f  test    rax, rax
0x180065fa2  jnz     short loc_180065FCC
0x180065fa4  mov     rcx, [rsp+318h]; this
0x180065fac  mov     ebx, 80070057h
0x180065fb1  mov     r9d, ebx; char *
0x180065fb4  lea     r8, aOnecoreuapBase_11; "onecoreuap\\base\\appmodel\\search\\com"...
0x180065fbb  mov     edx, 3D0h; void *
0x180065fc0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180065fc5  mov     eax, ebx
0x180065fc7  jmp     loc_180066944
0x180065fcc  mov     [rsp+318h+var_2C0], r14
0x180065fd1  test    rdi, rdi
0x180065fd4  jz      short loc_18006602A
0x180065fd6  xor     edx, edx
0x180065fd8  mov     rcx, rdi
0x180065fdb  call    ?ValidateImpl@TraceLoggingCorrelationVector@@CA?AW4CvVersion@1@PEBD_N@Z; TraceLoggingCorrelationVector::ValidateImpl(char const *,bool)
0x180065fe0  test    al, al
0x180065fe2  jz      short loc_18006602A
0x180065fe4  mov     rcx, rdi; char *
0x180065fe7  call    ?Extend@TraceLoggingCorrelationVector@@SAPEAV1@PEBD_N@Z; TraceLoggingCorrelationVector::Extend(char const *,bool)
0x180065fec  mov     r15, rax
0x180065fef  mov     [rsp+318h+var_2C0], rax
0x180065ff4  test    rax, rax
0x180065ff7  jnz     short loc_180066022
0x180065ff9  mov     rcx, [rsp+318h]; this
0x180066001  mov     ebx, 8007000Eh
0x180066006  mov     r9d, ebx; char *
0x180066009  lea     r8, aOnecoreuapBase_11; "onecoreuap\\base\\appmodel\\search\\com"...
0x180066010  mov     edx, 3DAh; void *
0x180066015  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006601a  nop
0x18006601b  mov     eax, ebx
0x18006601d  jmp     loc_180066944
0x180066022  mov     r12d, 90h
0x180066028  jmp     short loc_180066048
0x18006602a  mov     r12d, 90h
0x180066030  mov     ecx, r12d; Size
0x180066033  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180066038  mov     rcx, rax; this
0x18006603b  call    ??0TraceLoggingCorrelationVector@@QEAA@XZ; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)
0x180066040  mov     r15, rax
0x180066043  mov     [rsp+318h+var_2C0], rax
0x180066048  mov     rdi, rax
0x18006604b  xor     edx, edx; Val
0x18006604d  mov     r8d, 81h; Size
0x180066053  lea     rcx, [rsp+318h+var_D8]; void *
0x18006605b  call    memset_0
0x180066060  lea     rdx, [rsp+318h+var_D8]; char *
0x180066068  mov     rcx, r15; this
0x18006606b  call    ?ToString@TraceLoggingCorrelationVector@@QEAA_NPEAD@Z; TraceLoggingCorrelationVector::ToString(char *)
0x180066070  test    al, al
0x180066072  jnz     short loc_1800660AD
0x180066074  mov     rcx, [rsp+318h]; this
0x18006607c  mov     ebx, 8007000Eh
0x180066081  mov     r9d, ebx; char *
0x180066084  lea     r8, aOnecoreuapBase_11; "onecoreuap\\base\\appmodel\\search\\com"...
0x18006608b  mov     edx, 3DEh; void *
0x180066090  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180066095  nop
0x180066096  test    rdi, rdi
0x180066099  jz      short loc_1800660A6
0x18006609b  mov     rdx, r12; unsigned __int64
0x18006609e  mov     rcx, rdi; void *
0x1800660a1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800660a6  mov     eax, ebx
0x1800660a8  jmp     loc_180066944
0x1800660ad  mov     [rsp+318h+var_2E8], r14b
0x1800660b2  mov     [rsp+318h+var_2D0], r14
0x1800660b7  mov     qword ptr [rsp+318h+SystemTimeAsFileTime.dwLowDateTime], r14
0x1800660bf  lea     rcx, [rsp+318h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800660c7  call    cs:__imp_GetSystemTimeAsFileTime
0x1800660cd  nop
0x1800660ce  lea     rdx, aUpdatemodelcac; "UpdateModelCacheOnDriverUpdateStart"
0x1800660d5  lea     rcx, [rsp+318h+var_228]
0x1800660dd  call    ??0?$ActivityBase@VTelemetryLogger@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800660e2  lea     r13, ??_7UpdateModelCacheOnDriverUpdateStart@TelemetryLogger@@6B@; const TelemetryLogger::UpdateModelCacheOnDriverUpdateStart::`vftable'
0x1800660e9  mov     [rsp+318h+var_228], r13
0x1800660f1  lea     rax, [rsp+318h+var_D8]
0x1800660f9  mov     qword ptr [rsp+318h+var_2F8], rax; int
0x1800660fe  mov     r9, qword ptr [rsp+318h+SystemTimeAsFileTime.dwLowDateTime]; struct _FILETIME
0x180066106  mov     r8d, [rsp+318h+var_290]; int
0x18006610e  mov     rdx, rsi; wchar_t *
0x180066111  lea     rcx, [rsp+318h+var_228]; this
0x180066119  call    ?StartActivity@UpdateModelCacheOnDriverUpdateStart@TelemetryLogger@@QEAAXPEB_WHU_FILETIME@@PEBD@Z; TelemetryLogger::UpdateModelCacheOnDriverUpdateStart::StartActivity(wchar_t const *,int,_FILETIME,char const *)
0x18006611e  nop
0x18006611f  lea     rax, [rsp+318h+var_2D0]
0x180066124  mov     [rsp+318h+var_258], rax
0x18006612c  lea     rax, [rsp+318h+var_2E8]
0x180066131  mov     [rsp+318h+var_250], rax
0x180066139  lea     rax, [rsp+318h+var_228]
0x180066141  mov     [rsp+318h+var_248], rax
0x180066149  lea     rax, [rsp+318h+var_D8]
0x180066151  mov     [rsp+318h+var_240], rax
0x180066159  mov     [rsp+318h+var_238], 1
0x180066161  call    ??$init_once@P6AXXZ@wil@@YA_NAEAT_RTL_RUN_ONCE@@P6AXXZ@Z; wil::init_once<void (*)(void)>(_RTL_RUN_ONCE &,void (*)(void))
0x180066166  mov     [rsp+318h+hObject], r14
0x18006616b  call    cs:__imp_CoImpersonateClient
0x180066171  mov     rcx, [rsp+318h]; this
0x180066179  test    eax, eax
0x18006617b  js      loc_180066967
0x180066181  mov     rsi, [rsp+318h+hObject]
0x180066186  lea     rax, [rsi-1]
0x18006618a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18006618e  ja      short loc_1800661A9
0x180066190  call    cs:__imp_GetLastError
0x180066196  mov     edi, eax
0x180066198  mov     rcx, rsi; hObject
0x18006619b  call    cs:__imp_CloseHandle
0x1800661a1  mov     ecx, edi; dwErrCode
0x1800661a3  call    cs:__imp_SetLastError
0x1800661a9  mov     [rsp+318h+hObject], r14
0x1800661ae  call    cs:__imp_GetCurrentThread
0x1800661b4  lea     r9, [rsp+318h+hObject]; TokenHandle
0x1800661b9  mov     esi, 1
0x1800661be  mov     r8d, esi; OpenAsSelf
0x1800661c1  lea     edx, [rsi+0Dh]; DesiredAccess
0x1800661c4  mov     rcx, rax; ThreadHandle
0x1800661c7  call    cs:__imp_OpenThreadToken
0x1800661cd  test    eax, eax
0x1800661cf  jnz     loc_180066267
0x1800661d5  mov     rcx, [rsp+318h]; this
0x1800661dd  lea     r8, aOnecoreuapBase_11; "onecoreuap\\base\\appmodel\\search\\com"...
0x1800661e4  mov     edx, 3F3h; void *
0x1800661e9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800661ee  mov     ebx, eax
0x1800661f0  call    cs:__imp_CoRevertToSelf
0x1800661f6  nop
0x1800661f7  mov     rcx, [rsp+318h+hObject]; hObject
0x1800661fc  lea     rdx, [rcx-1]
0x180066200  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180066204  ja      short loc_18006620D
0x180066206  call    cs:__imp_CloseHandle
0x18006620c  nop
0x18006620d  lea     r9, [rsp+318h+var_D8]; char *
0x180066215  mov     r8b, [rsp+318h+var_2E8]; bool
0x18006621a  mov     rdx, [rsp+318h+var_2D0]; unsigned __int64
0x18006621f  lea     rcx, [rsp+318h+var_228]; this
0x180066227  call    ?Stop@UpdateModelCacheOnDriverUpdateStart@TelemetryLogger@@QEAAX_K_NPEBD@Z; TelemetryLogger::UpdateModelCacheOnDriverUpdateStart::Stop(unsigned __int64,bool,char const *)
0x18006622c  nop
0x18006622d  mov     [rsp+318h+var_228], r13
0x180066235  lea     rcx, [rsp+318h+var_228]
0x18006623d  call    ?Destroy@?$ActivityBase@VTelemetryLogger@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180066242  lea     rcx, [rsp+318h+var_228]
0x18006624a  call    ??1?$ActivityBase@VTelemetryLogger@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x18006624f  nop
0x180066250  test    r15, r15
0x180066253  jz      short loc_180066260
0x180066255  mov     rdx, r12; unsigned __int64
0x180066258  mov     rcx, r15; void *
0x18006625b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180066260  mov     eax, ebx
0x180066262  jmp     loc_180066944
0x180066267  call    cs:__imp_CoRevertToSelf
0x18006626d  mov     rcx, rbx; struct IUnknown *
0x180066270  call    ?SetProxyBlanketImpersonationLevelAndDynamicCloaking@@YAJPEAUIUnknown@@@Z; SetProxyBlanketImpersonationLevelAndDynamicCloaking(IUnknown *)
0x180066275  mov     edi, eax
0x180066277  test    eax, eax
0x180066279  jns     loc_18006630C
0x18006627f  mov     rcx, [rsp+318h]; this
0x180066287  mov     r9d, eax; char *
0x18006628a  lea     r8, aOnecoreuapBase_11; "onecoreuap\\base\\appmodel\\search\\com"...
0x180066291  mov     edx, 3F5h; void *
0x180066296  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006629b  nop
0x18006629c  mov     rcx, [rsp+318h+hObject]; hObject
0x1800662a1  lea     rax, [rcx-1]
0x1800662a5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800662a9  ja      short loc_1800662B2
0x1800662ab  call    cs:__imp_CloseHandle
0x1800662b1  nop
0x1800662b2  lea     r9, [rsp+318h+var_D8]; char *
0x1800662ba  mov     r8b, [rsp+318h+var_2E8]; bool
0x1800662bf  mov     rdx, [rsp+318h+var_2D0]; unsigned __int64
0x1800662c4  lea     rcx, [rsp+318h+var_228]; this
0x1800662cc  call    ?Stop@UpdateModelCacheOnDriverUpdateStart@TelemetryLogger@@QEAAX_K_NPEBD@Z; TelemetryLogger::UpdateModelCacheOnDriverUpdateStart::Stop(unsigned __int64,bool,char const *)
0x1800662d1  nop
0x1800662d2  mov     [rsp+318h+var_228], r13
0x1800662da  lea     rcx, [rsp+318h+var_228]
0x1800662e2  call    ?Destroy@?$ActivityBase@VTelemetryLogger@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800662e7  lea     rcx, [rsp+318h+var_228]
0x1800662ef  call    ??1?$ActivityBase@VTelemetryLogger@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x1800662f4  nop
0x1800662f5  test    r15, r15
0x1800662f8  jz      short loc_180066305
0x1800662fa  mov     rdx, r12; unsigned __int64
0x1800662fd  mov     rcx, r15; void *
0x180066300  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180066305  mov     eax, edi
0x180066307  jmp     loc_180066944
0x18006630c  mov     rax, [rsp+318h+var_2C8]
0x180066311  mov     [rsp+318h+var_2C8], rax
0x180066316  mov     rdi, [rsp+318h+var_278]
0x18006631e  lea     rcx, [rdi+28h]; _Mtx_t
0x180066322  lea     r8, [rsp+318h+var_2C8]
0x180066327  lea     rdx, [rsp+318h+var_2A0]
0x18006632c  call    ThreadSafeContainer_std__list_std__shared_ptr_SessionManagerBrokerImpl__UpdateModelCacheOnDriverUpdate__std__allocator_std__shared_ptr_SessionManagerBrokerImpl__UpdateModelCacheOnDriverUpdate_________Find__lambda_6244c2e93103651f21cd979fc257d526____
0x180066331  nop
0x180066332  cmp     [rsp+318h+var_2A0], r14
0x180066337  jz      loc_1800664CF
0x18006633d  lea     r8, [rsp+318h+var_280]
0x180066345  lea     rdx, [rsp+318h+hObject]
0x18006634a  lea     rcx, [rsp+318h+var_2B8]
0x18006634f  call    ??$make_shared@UEventsPair@@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@AEAPEAUIUpdateModelCacheOnDriverUpdateEvents@@@std@@YA?AV?$shared_ptr@UEventsPair@@@0@$$QEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@AEAPEAUIUpdateModelCacheOnDriverUpdateEvents@@@Z; std::make_shared<EventsPair,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,IUpdateModelCacheOnDriverUpdateEvents * &>(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&,IUpdateModelCacheOnDriverUpdateEvents * &)
0x180066354  nop
0x180066355  mov     rdi, [rsp+318h+var_2A0]
0x18006635a  add     rdi, 50h ; 'P'
0x18006635e  mov     [rsp+318h+var_2A8], rdi
0x180066363  mov     rcx, rdi; _Mtx_t
0x180066366  call    cs:__imp__Mtx_lock
0x18006636c  test    eax, eax
0x18006636e  jz      short loc_18006637B
0x180066370  mov     ecx, 5
0x180066375  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18006637b  mov     eax, [rdi+4Ch]
0x18006637e  cmp     eax, 7FFFFFFFh
0x180066383  jnz     short loc_180066396
0x180066385  dec     eax
0x180066387  mov     [rdi+4Ch], eax
0x18006638a  mov     ecx, 6
0x18006638f  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180066395  nop
0x180066396  mov     rcx, [rdi+50h]
0x18006639a  mov     rax, [rcx]
0x18006639d  cmp     rax, rcx
0x1800663a0  jz      short loc_1800663B1
0x1800663a2  mov     rdx, [rax+10h]
0x1800663a6  cmp     [rdx+8], rbx
0x1800663aa  jz      short loc_1800663C0
0x1800663ac  mov     rax, [rax]
0x1800663af  jmp     short loc_18006639D
0x1800663b1  lea     rdx, [rsp+318h+var_2B8]
0x1800663b6  lea     rcx, [rdi+50h]
0x1800663ba  call    ?push_back@?$list@V?$shared_ptr@UEventsPair@@@std@@V?$allocator@V?$shared_ptr@UEventsPair@@@std@@@2@@std@@QEAAXAEBV?$shared_ptr@UEventsPair@@@2@@Z; std::list<std::shared_ptr<EventsPair>>::push_back(std::shared_ptr<EventsPair> const &)
0x1800663bf  nop
0x1800663c0  mov     rcx, rdi; _Mtx_t
0x1800663c3  call    cs:__imp__Mtx_unlock
0x1800663c9  mov     rax, [rsp+318h+var_2A0]
0x1800663ce  mov     rcx, [rax+28h]
0x1800663d2  mov     rdx, [rsp+318h+var_270]
0x1800663da  mov     [rdx], rcx
0x1800663dd  mov     rdi, [rsp+318h+var_2B0]
0x1800663e2  or      ebx, 0FFFFFFFFh
0x1800663e5  test    rdi, rdi
0x1800663e8  jz      short loc_18006641E
0x1800663ea  mov     eax, ebx
  ... truncated ...
```
