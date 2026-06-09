# HNS::Service::Network::LayeredResource::NetworkCreateLayered(HNS::Service::Network::ResourceRequirement const &,HNS::Service::Resource::ExternalAdapterResource::VariableSet,HNS::Service::Resource::HostPortResource::VariableSet)

- ea: `0x18016ae40`
- end: `0x18016b806`
- name: `?NetworkCreateLayered@LayeredResource@Network@Service@HNS@@AEAAXAEBUResourceRequirement@234@UVariableSet@ExternalAdapterResource@Resource@34@U6HostPortResource@834@@Z`
- size: `2502`
- prototype: ``
- caller_count: `1`
- callee_count: `38`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180168250`

## callees

- `0x180001b68`
- `0x18005f0c0`
- `0x18005f59c`
- `0x180061dc4`
- `0x1800666b4`
- `0x1800677fc`
- `0x18006c530`
- `0x18006cc2c`
- `0x18006ea40`
- `0x1800759d8`
- `0x180075aac`
- `0x18007f21c`
- `0x18008ab30`
- `0x18008eb18`
- `0x1800956dc`
- `0x1800bb74c`
- `0x1800c7e68`
- `0x1800c9b80`
- `0x1800fbd60`
- `0x180108a88`
- `0x180122dbc`
- `0x1801232dc`
- `0x18012610c`
- `0x180166344`
- `0x180168f58`
- `0x18016ae40`
- `0x18016e5e4`
- `0x18019dbb4`
- `0x1801bdc44`
- `0x1801d2c30`
- `0x18022abf0`
- `0x18022ac34`
- `0x18022c6d4`
- `0x18022cb88`
- `0x18022cde8`
- `0x18022ef7c`
- `0x180230118`
- `0x1802b7010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18016b767`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18016b767`
- `api-ms-win-core-synch-l1-2-0!WaitOnAddress` at `0x18016b72c`
- `api-ms-win-core-synch-l1-2-0!WaitOnAddress` at `0x18016b72c`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18016aefe`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18016aefe`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18016b5d4`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18016b5d4`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x18016af22`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x18016b5cd`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x18016af22`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x18016b5cd`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18016b6eb`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18016b744`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18016b6eb`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18016b744`

## string_xrefs

- `0x18016b7d9`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x18016b7f4`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x18016afac`: `onecore\vm\dv\net\hns\service\entity\layer\layeredresource.cpp`
- `0x18016afdc`: `onecore\vm\dv\net\hns\service\entity\layer\layeredresource.cpp`
- `0x18016b7c0`: `onecore\vm\dv\net\hns\service\entity\layer\layeredresource.cpp`
- `0x18016af9d`: `Find interface configuration failed`
- `0x18016ae9b`: `HNS::Service::Network::LayeredResource::NetworkCreateLayered`
- `0x18016b5a2`: `HNS::Service::Network::LayeredResource::NetworkCreateLayered`
- `0x18016b026`: `Find interface Ipv4 configuration failed`
- `0x18016afcd`: `Config helper init failed`
- `0x18016b45f`: `Apply static configuration failed`
- `0x18016b079`: `Find interface Ipv6 configuration failed`
- `0x18016b4eb`: `Apply interface Ipv6 configuration failed`
- `0x18016b4a7`: `Apply interface Ipv4 configuration failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
void __fastcall HNS::Service::Network::LayeredResource::NetworkCreateLayered(
        _QWORD *a1,
        IUnknown *a2,
        unsigned __int64 a3,
        IUnknown *a4)
{
  IUnknown *v4; // r12
  __int128 *v7; // rcx
  struct IWbemClassObject *v8; // rdi
  VmIPv6Configuration *v9; // rsi
  HRESULT v10; // eax
  HRESULT v11; // eax
  __int64 v12; // r8
  IUnknown *v13; // r15
  const struct _tlgProvider_t *v14; // rdx
  int v15; // eax
  const unsigned __int16 *v16; // rdx
  unsigned int NetworkConfigFromInstanceGuid; // eax
  const unsigned __int16 *v18; // rcx
  unsigned int Instance; // eax
  const unsigned __int16 *v20; // rcx
  unsigned int v21; // eax
  __int64 v22; // rbx
  struct _GUID *Activity; // rax
  volatile signed __int32 *v24; // rbx
  volatile signed __int32 *v25; // rbx
  __int64 v26; // rcx
  void (__fastcall *v27)(__int64, unsigned __int64 *); // r8
  __int64 v28; // rdx
  Vml::VmSharableObject *v29; // r14
  __int64 v30; // rbx
  unsigned int v31; // eax
  __int64 v32; // rax
  volatile signed __int32 *v33; // rbx
  int v34; // r12d
  __int64 v35; // rbx
  __int64 v36; // rax
  __int64 v37; // rbx
  __int64 v38; // r8
  GUID v39; // xmm0
  struct _GUID *v40; // rbx
  __int64 *v41; // rcx
  __int64 v42; // rax
  __int64 v43; // rdx
  unsigned int v44; // eax
  int v45; // r9d
  const unsigned __int16 *v46; // rdx
  unsigned int v47; // eax
  const char *v48; // r9
  const unsigned __int16 *v49; // rdx
  unsigned int v50; // eax
  volatile signed __int32 *v51; // rbx
  unsigned __int64 v52; // rdx
  _DWORD *v53; // r12
  int v54; // [rsp+20h] [rbp-E0h]
  char *v55; // [rsp+28h] [rbp-D8h]
  char *v56; // [rsp+28h] [rbp-D8h]
  char *v57; // [rsp+28h] [rbp-D8h]
  char *v58; // [rsp+28h] [rbp-D8h]
  char v59[8]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v60; // [rsp+38h] [rbp-C8h] BYREF
  char v61; // [rsp+40h] [rbp-C0h]
  HNS::Service::Interface::IResourceable *CompareAddress; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int64 UnbiasedTime[2]; // [rsp+50h] [rbp-B0h] BYREF
  IUnknown *v64[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v65; // [rsp+70h] [rbp-90h] BYREF
  IUnknown *v66; // [rsp+80h] [rbp-80h]
  __int64 v67; // [rsp+88h] [rbp-78h] BYREF
  volatile signed __int32 *v68; // [rsp+90h] [rbp-70h]
  IUnknown *ppOldObject; // [rsp+98h] [rbp-68h] BYREF
  struct IWbemClassObject *v70; // [rsp+A0h] [rbp-60h] BYREF
  struct VmIPv6Configuration *v71; // [rsp+A8h] [rbp-58h] BYREF
  Vml::VmSharableObject *v72; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int64 v73; // [rsp+B8h] [rbp-48h]
  unsigned __int64 v74; // [rsp+C0h] [rbp-40h]
  __int128 v75; // [rsp+C8h] [rbp-38h] BYREF
  char v76; // [rsp+D8h] [rbp-28h]
  int *v77; // [rsp+E0h] [rbp-20h]
  __int128 v78; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v79; // [rsp+F8h] [rbp-8h]
  IUnknown *v80; // [rsp+100h] [rbp+0h]
  char v81; // [rsp+108h] [rbp+8h]
  _BYTE v82[64]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int64 v83; // [rsp+150h] [rbp+50h]
  IUnknown *v84; // [rsp+158h] [rbp+58h]
  unsigned __int16 *v85[3]; // [rsp+160h] [rbp+60h] BYREF
  unsigned __int64 v86; // [rsp+178h] [rbp+78h]
  unsigned __int16 *v87[3]; // [rsp+180h] [rbp+80h] BYREF
  unsigned __int64 v88; // [rsp+198h] [rbp+98h]
  struct _GUID v89; // [rsp+1A0h] [rbp+A0h] BYREF
  struct _GUID v90; // [rsp+1B0h] [rbp+B0h] BYREF
  __int64 v91; // [rsp+1C0h] [rbp+C0h]
  __int16 v92; // [rsp+1C8h] [rbp+C8h]
  wil::details::in1diag3 *retaddr; // [rsp+218h] [rbp+118h]

  v4 = a4;
  v66 = a4;
  v73 = a3;
  v64[0] = a2;
  v60 = (unsigned __int64)a1;
  v83 = a3;
  v84 = a4;
  HNSTraceProvider::TraceEnter("HNS::Service::Network::LayeredResource::NetworkCreateLayered", 0x36Eu);
  v74 = a3 + 32;
  v7 = *(__int128 **)(a3 + 32);
  if ( *(__int128 **)(a3 + 40) == v7 )
    std::vector<wil::com_ptr_t<HNSObject,wil::err_exception_policy>>::_Xrange();
  v65 = *v7;
  v78 = 0;
  v79 = 0;
  v75 = 0;
  v76 = 0;
  v77 = &dword_1803840A8;
  v8 = 0;
  v70 = 0;
  v9 = 0;
  v71 = 0;
  v72 = 0;
  v10 = CoInitializeEx(0, 0);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x14D3,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
      (const char *)(unsigned int)v10,
      v54);
  v61 = 1;
  ppOldObject = 0;
  v11 = CoSwitchCallContext(0, &ppOldObject);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x37E,
      (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\entity\\layer\\layeredresource.cpp",
      (const char *)(unsigned int)v11,
      v54);
  v13 = ppOldObject;
  v80 = ppOldObject;
  v81 = 1;
  LOBYTE(v12) = 1;
  GuidToString(v87, &v65, v12);
  v15 = Win32NetworkAdapterConfigurationHelper::Initialize((Win32NetworkAdapterConfigurationHelper *)&v75, v14);
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0x393,
      (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\entity\\layer\\layeredresource.cpp",
      (const char *)(unsigned int)v15,
      (int)"Config helper init failed",
      v55);
  }
  else
  {
    Win32NetworkAdapterConfigurationHelper::BuildListOfTransientIpAddresses(&v75, &v78);
    v16 = (const unsigned __int16 *)v87;
    if ( v88 > 7 )
      v16 = v87[0];
    NetworkConfigFromInstanceGuid = Win32NetworkAdapterConfigurationHelper::FindNetworkConfigFromInstanceGuid(
                                      (Win32NetworkAdapterConfigurationHelper *)&v75,
                                      v16,
                                      &v70);
    wil::details::in1diag3::Log_IfFailedMsg(
      retaddr,
      (void *)0x38F,
      (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\entity\\layer\\layeredresource.cpp",
      (const char *)NetworkConfigFromInstanceGuid,
      (int)"Find interface configuration failed",
      v55);
    v8 = v70;
  }
  if ( !v8 )
  {
    v18 = (const unsigned __int16 *)v87;
    if ( v88 > 7 )
      v18 = v87[0];
    Instance = VmIPv6Configuration::GetInstance(v18, 2u, qword_18039AE68, &v71);
    wil::details::in1diag3::Log_IfFailedMsg(
      retaddr,
      (void *)0x39D,
      (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\entity\\layer\\layeredresource.cpp",
      (const char *)Instance,
      (int)"Find interface Ipv4 configuration failed",
      v56);
    v9 = v71;
  }
  v20 = (const unsigned __int16 *)v87;
  if ( v88 > 7 )
    v20 = v87[0];
  v21 = VmIPv6Configuration::GetInstance(v20, 0x17u, qword_18039AE68, &v72);
  wil::details::in1diag3::Log_IfFailedMsg(
    retaddr,
    (void *)0x3A4,
    (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\entity\\layer\\layeredresource.cpp",
    (const char *)v21,
    (int)"Find interface Ipv6 configuration failed",
    v56);
  v22 = a1[103];
  UnbiasedTime[0] = v73;
  CompareAddress = (HNS::Service::Interface::IResourceable *)(a1 + 102);
  Activity = HNS::Service::Interface::IResourceable::GetActivity(
               (HNS::Service::Interface::IResourceable *)(a1 + 102),
               &v89);
  HNS::Service::Resource::ResourceManager::GetActivity(v22, &v67, Activity);
  HNS::Service::Resource::Activity::AllocateResource<0,HNS::Service::Resource::ExternalAdapterResource::VariableSet *>(
    v67,
    &v65,
    UnbiasedTime,
    0);
  v24 = v68;
  if ( v68 )
  {
    if ( _InterlockedExchangeAdd(v68 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v24)(v24);
      if ( _InterlockedExchangeAdd(v24 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v24 + 8LL))(v24);
    }
  }
  std::shared_ptr<HNS::Service::Core::NamespaceEntityManager>::operator=(a1 + 156, &v65);
  v25 = (volatile signed __int32 *)*((_QWORD *)&v65 + 1);
  if ( *((_QWORD *)&v65 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v65 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v25)(v25);
      if ( _InterlockedExchangeAdd(v25 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v25 + 8LL))(v25);
    }
  }
  v26 = a1[154];
  v27 = *(void (__fastcall **)(__int64, unsigned __int64 *))(*(_QWORD *)v26 + 160LL);
  *(_OWORD *)UnbiasedTime = 0;
  v28 = a1[157];
  if ( v28 )
    _InterlockedIncrement((volatile signed __int32 *)(v28 + 8));
  UnbiasedTime[0] = a1[156];
  UnbiasedTime[1] = a1[157];
  v27(v26, UnbiasedTime);
  v29 = v72;
  if ( LOBYTE(v64[0][10].lpVtbl) == 1 )
  {
    v30 = *(_QWORD *)(v60 + 824);
    v64[0] = v4;
    v31 = (unsigned int)HNS::Service::Interface::IResourceable::GetActivity(CompareAddress, &v90);
    v32 = HNS::Service::Resource::ResourceManager::AllocateResource<22,HNS::Service::Resource::HostPortResource::VariableSet *>(
            v30,
            (unsigned int)&v65,
            v31,
            (unsigned int)v64,
            0);
    CompareAddress = (HNS::Service::Interface::IResourceable *)(v60 + 1208);
    std::shared_ptr<HNS::Service::Core::NamespaceEntityManager>::operator=(v60 + 1208, v32);
    v33 = (volatile signed __int32 *)*((_QWORD *)&v65 + 1);
    if ( *((_QWORD *)&v65 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v65 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v33)(v33);
        if ( _InterlockedExchangeAdd(v33 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v33 + 8LL))(v33);
      }
    }
    _InterlockedExchange((volatile __int32 *)(v60 + 1584), 0);
    HNS::Service::Core::InterfaceNotificationManager::GetInstance(&v67);
    v34 = v67;
    v35 = *(_QWORD *)(*(_QWORD *)CompareAddress + 3136LL);
    HNSObject::Get<_GUID>(*(_QWORD *)(v60 + 808), &v65, v60 + 752);
    v90 = GUID_NULL;
    v64[0] = (IUnknown *)operator new(0x30u);
    v36 = std::_Ref_count_obj2<HNS::Service::Events::EventRoute>::_Ref_count_obj2<HNS::Service::Events::EventRoute>(
            v64[0],
            &v90,
            &v65);
    UnbiasedTime[0] = v36 + 16;
    UnbiasedTime[1] = v36;
    HNS::Service::Events::FilteredEventManager<_NET_LUID_LH,NET_LUID_Comparator>::SubscribeEvent(
      v34 + 104,
      (unsigned int)&v89,
      28,
      3,
      (__int64)UnbiasedTime,
      v35);
    *(_QWORD *)&v65 = &v89;
    *((_QWORD *)&v65 + 1) = &v67;
    *(_QWORD *)&v90.Data1 = retaddr;
    *(_QWORD *)v90.Data4 = "onecore\\vm\\dv\\net\\hns\\service\\entity\\layer\\layeredresource.cpp";
    v91 = 0;
    v92 = 954;
    wil::scope_exit_log__lambda_deba094243c325adbef6a198e573833e___(v82, &v90, &v65);
    HNS::Service::Resource::HostPortResource::HardConnect(*(HNS::Service::Resource::HostPortResource **)CompareAddress);
    v37 = *(_QWORD *)CompareAddress;
    if ( (unsigned int)HNSObject::PropertyExists(
                         *(_QWORD *)(*(_QWORD *)CompareAddress + 2552LL),
                         *(_QWORD *)CompareAddress + 2496LL) )
    {
      v39 = GUID_NULL;
    }
    else
    {
      HNSObject::Get<_GUID>(*(_QWORD *)(v37 + 2552), &v90, v37 + 2496);
      v39 = v90;
    }
    v90 = v39;
    LOBYTE(v38) = 1;
    GuidToString(v85, &v90, v38);
    v40 = (struct _GUID *)v60;
    v41 = *(__int64 **)(v60 + 1232);
    v42 = *v41;
    *(_OWORD *)v64 = 0;
    v43 = *((_QWORD *)CompareAddress + 1);
    if ( v43 )
      _InterlockedIncrement((volatile signed __int32 *)(v43 + 8));
    v64[0] = *(IUnknown **)CompareAddress;
    v64[1] = *((IUnknown **)CompareAddress + 1);
    (*(void (__fastcall **)(__int64 *, IUnknown **))(v42 + 152))(v41, v64);
    v44 = Win32NetworkAdapterConfigurationHelper::ApplyNetworkStaticSettings((Win32NetworkAdapterConfigurationHelper *)&v75);
    wil::details::in1diag3::Log_IfFailedMsg(
      retaddr,
      (void *)0x3CA,
      (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\entity\\layer\\layeredresource.cpp",
      (const char *)v44,
      (int)"Apply static configuration failed",
      v57);
    if ( v9 )
    {
      v46 = (const unsigned __int16 *)v85;
      if ( v86 > 7 )
        v46 = v85[0];
      v47 = VmIPv6Configuration::Apply(v9, v46, 2u, v45);
      wil::details::in1diag3::Log_IfFailedMsg(
        retaddr,
        (void *)0x3D0,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\entity\\layer\\layeredresource.cpp",
        (const char *)v47,
        (int)"Apply interface Ipv4 configuration failed",
        v58);
    }
    else
    {
      if ( *(_DWORD *)qword_18039AE68 > 5u )
        tlgWriteTransfer_EventWriteTransfer(qword_18039AE68, byte_18033E0A3, 0, 0, 2, &v90);
      UnbiasedTime[0] = 0;
      QueryUnbiasedInterruptTime(UnbiasedTime);
      v52 = 0;
      v53 = (_DWORD *)(v60 + 1584);
      while ( !*v53 && v52 < 0x7530 )
      {
        LODWORD(CompareAddress) = *v53;
        if ( !WaitOnAddress(&v40[99], &CompareAddress, 4u, 30000 - v52) )
        {
          if ( GetLastError() != 1460 )
            wil::details::in1diag3::_FailFast_Unexpected(
              retaddr,
              (void *)0xDBF,
              (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
              v48);
          break;
        }
        v60 = 0;
        QueryUnbiasedInterruptTime(&v60);
        v52 = (v60 - UnbiasedTime[0]) / 0x2710;
      }
    }
    if ( v29 )
    {
      v49 = (const unsigned __int16 *)v85;
      if ( v86 > 7 )
        v49 = v85[0];
      v50 = VmIPv6Configuration::Apply(v29, v49, 0x17u, (int)v48);
      wil::details::in1diag3::Log_IfFailedMsg(
        retaddr,
        (void *)0x3E1,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\entity\\layer\\layeredresource.cpp",
        (const char *)v50,
        (int)"Apply interface Ipv6 configuration failed",
        v58);
    }
    v59[0] = 1;
    v90 = v40[63];
    HNSObject::Set<unsigned char>(*(_QWORD *)v40[64].Data4, &v40[61], v59, v40[64].Data1);
    std::wstring::~wstring(v85);
    wil::details::lambda_call_log__lambda_deba094243c325adbef6a198e573833e___::reset(v82);
    v51 = v68;
    if ( v68 )
    {
      if ( _InterlockedExchangeAdd(v68 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v51)(v51);
        if ( _InterlockedExchangeAdd(v51 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v51 + 8LL))(v51);
      }
    }
    v4 = v66;
  }
  else
  {
    v59[0] = 0;
    v89 = *(struct _GUID *)(v60 + 1008);
    HNSObject::Set<unsigned char>(*(_QWORD *)(v60 + 1032), v60 + 976, v59, *(unsigned int *)(v60 + 1024));
  }
  HNSTraceProvider::TraceSuccess("HNS::Service::Network::LayeredResource::NetworkCreateLayered", 0x3ECu);
  std::wstring::~wstring(v87);
  v64[0] = 0;
  CoSwitchCallContext(v13, v64);
  CoUninitialize();
  if ( v29 )
    Vml::VmSharableObject::DecrementUserCount(v29);
  if ( v9 )
    Vml::VmSharableObject::DecrementUserCount(v9);
  if ( v8 )
    ((void (__fastcall *)(struct IWbemClassObject *))v8->lpVtbl->Release)(v8);
  Win32NetworkAdapterConfigurationHelper::~Win32NetworkAdapterConfigurationHelper((Win32NetworkAdapterConfigurationHelper *)&v75);
  std::vector<std::pair<unsigned short,unsigned short>>::~vector<std::pair<unsigned short,unsigned short>>(&v78);
  std::wstring::~wstring((void *)(v73 + 56));
  std::vector<_GUID>::~vector<_GUID>(v74);
  std::wstring::~wstring(&v4[33]);
  std::wstring::~wstring(&v4[28]);
  std::wstring::~wstring(&v4[24]);
  std::wstring::~wstring(&v4[20]);
  std::wstring::~wstring(&v4[6]);
  std::wstring::~wstring(&v4[2]);
}

```

## disassembly

```asm
0x18016ae40  mov     [rsp-8+arg_8], rbx
0x18016ae45  push    rbp
0x18016ae46  push    rsi
0x18016ae47  push    rdi
0x18016ae48  push    r12
0x18016ae4a  push    r13
0x18016ae4c  push    r14
0x18016ae4e  push    r15
0x18016ae50  lea     rbp, [rsp-0E0h]
0x18016ae58  sub     rsp, 1E0h
0x18016ae5f  mov     rax, cs:__security_cookie
0x18016ae66  xor     rax, rsp
0x18016ae69  mov     [rbp+110h+var_40], rax
0x18016ae70  mov     r12, r9
0x18016ae73  mov     [rbp+110h+var_190], r9
0x18016ae77  mov     rbx, r8
0x18016ae7a  mov     [rbp+110h+var_158], rbx
0x18016ae7e  mov     [rsp+210h+var_1B0], rdx
0x18016ae83  mov     r14, rcx
0x18016ae86  mov     [rsp+210h+var_1D8], rcx
0x18016ae8b  mov     [rbp+110h+var_C0], rbx
0x18016ae8f  mov     [rbp+110h+var_B8], r9
0x18016ae93  xor     r13d, r13d
0x18016ae96  mov     edx, 36Eh; unsigned int
0x18016ae9b  lea     rcx, aHnsServiceNetw_64; "HNS::Service::Network::LayeredResource:"...
0x18016aea2  call    ?TraceEnter@HNSTraceProvider@@SAXPEBDI@Z; HNSTraceProvider::TraceEnter(char const *,uint)
0x18016aea7  lea     rax, [rbx+20h]
0x18016aeab  mov     [rbp+110h+var_150], rax
0x18016aeaf  mov     rcx, [rax]
0x18016aeb2  cmp     [rax+8], rcx
0x18016aeb6  jz      loc_18016B7EB
0x18016aebc  movups  xmm0, xmmword ptr [rcx]
0x18016aebf  movdqu  [rsp+210h+var_1A0], xmm0
0x18016aec5  xorps   xmm1, xmm1
0x18016aec8  movdqu  [rbp+110h+var_128], xmm1
0x18016aecd  mov     [rbp+110h+var_118], r13
0x18016aed1  xorps   xmm0, xmm0
0x18016aed4  movdqu  [rbp+110h+var_148], xmm0
0x18016aed9  mov     [rbp+110h+var_138], r13b
0x18016aedd  lea     rax, dword_1803840A8
0x18016aee4  mov     [rbp+110h+var_130], rax
0x18016aee8  mov     edi, r13d
0x18016aeeb  mov     [rbp+110h+var_170], r13
0x18016aeef  mov     esi, r13d
0x18016aef2  mov     [rbp+110h+var_168], r13
0x18016aef6  mov     [rbp+110h+var_160], r13
0x18016aefa  xor     edx, edx; dwCoInit
0x18016aefc  xor     ecx, ecx; pvReserved
0x18016aefe  call    cs:__imp_CoInitializeEx
0x18016af04  mov     rcx, [rbp+118h]; this
0x18016af0b  test    eax, eax
0x18016af0d  js      loc_18016B7F1
0x18016af13  mov     [rsp+210h+var_1D0], 1
0x18016af18  mov     [rbp+110h+ppOldObject], r13
0x18016af1c  lea     rdx, [rbp+110h+ppOldObject]; ppOldObject
0x18016af20  xor     ecx, ecx; pNewObject
0x18016af22  call    cs:__imp_CoSwitchCallContext
0x18016af28  mov     rcx, [rbp+118h]; this
0x18016af2f  test    eax, eax
0x18016af31  js      loc_18016B7BD
0x18016af37  mov     r15, [rbp+110h+ppOldObject]
0x18016af3b  mov     [rbp+110h+var_110], r15
0x18016af3f  mov     [rbp+110h+var_108], 1
0x18016af43  mov     r8b, 1
0x18016af46  lea     rdx, [rsp+210h+var_1A0]
0x18016af4b  lea     rcx, [rbp+110h+var_90]
0x18016af52  call    ?GuidToString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@_N@Z; GuidToString(_GUID const &,bool)
0x18016af57  nop
0x18016af58  lea     rcx, [rbp+110h+var_148]; this
0x18016af5c  call    ?Initialize@Win32NetworkAdapterConfigurationHelper@@QEAAJPEBU_tlgProvider_t@@@Z; Win32NetworkAdapterConfigurationHelper::Initialize(_tlgProvider_t const *)
0x18016af61  test    eax, eax
0x18016af63  js      short loc_18016AFC6
0x18016af65  lea     rdx, [rbp+110h+var_128]
0x18016af69  lea     rcx, [rbp+110h+var_148]
0x18016af6d  call    ?BuildListOfTransientIpAddresses@Win32NetworkAdapterConfigurationHelper@@QEAAXAEAV?$vector@KV?$allocator@K@std@@@std@@@Z; Win32NetworkAdapterConfigurationHelper::BuildListOfTransientIpAddresses(std::vector<ulong> &)
0x18016af72  lea     rdx, [rbp+110h+var_90]
0x18016af79  cmp     [rbp+110h+var_78], 7
0x18016af81  cmova   rdx, [rbp+110h+var_90]; unsigned __int16 *
0x18016af89  lea     r8, [rbp+110h+var_170]; struct IWbemClassObject **
0x18016af8d  lea     rcx, [rbp+110h+var_148]; this
0x18016af91  call    ?FindNetworkConfigFromInstanceGuid@Win32NetworkAdapterConfigurationHelper@@QEAAJPEBGPEAPEAUIWbemClassObject@@@Z; Win32NetworkAdapterConfigurationHelper::FindNetworkConfigFromInstanceGuid(ushort const *,IWbemClassObject * *)
0x18016af96  mov     rcx, [rbp+118h]; this
0x18016af9d  lea     rdx, aFindInterfaceC; "Find interface configuration failed"
0x18016afa4  mov     qword ptr [rsp+210h+var_1F0], rdx; int
0x18016afa9  mov     r9d, eax; char *
0x18016afac  lea     r13, aOnecoreVmDvNet_162; "onecore\\vm\\dv\\net\\hns\\service\\ent"...
0x18016afb3  mov     r8, r13; unsigned int
0x18016afb6  mov     edx, 38Fh; void *
0x18016afbb  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18016afc0  mov     rdi, [rbp+110h+var_170]
0x18016afc4  jmp     short loc_18016AFF0
0x18016afc6  mov     rcx, [rbp+118h]; this
0x18016afcd  lea     rdx, aConfigHelperIn; "Config helper init failed"
0x18016afd4  mov     qword ptr [rsp+210h+var_1F0], rdx; int
0x18016afd9  mov     r9d, eax; char *
0x18016afdc  lea     r13, aOnecoreVmDvNet_162; "onecore\\vm\\dv\\net\\hns\\service\\ent"...
0x18016afe3  mov     r8, r13; unsigned int
0x18016afe6  mov     edx, 393h; void *
0x18016afeb  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18016aff0  test    rdi, rdi
0x18016aff3  jnz     short loc_18016B046
0x18016aff5  lea     rcx, [rbp+110h+var_90]
0x18016affc  cmp     [rbp+110h+var_78], 7
0x18016b004  cmova   rcx, [rbp+110h+var_90]; unsigned __int16 *
0x18016b00c  lea     edx, [rdi+2]; unsigned __int16
0x18016b00f  lea     r9, [rbp+110h+var_168]; struct VmIPv6Configuration **
0x18016b013  mov     r8, cs:qword_18039AE68; struct _tlgProvider_t *
0x18016b01a  call    ?GetInstance@VmIPv6Configuration@@SAJPEBGGPEBU_tlgProvider_t@@PEAPEAV1@@Z; VmIPv6Configuration::GetInstance(ushort const *,ushort,_tlgProvider_t const *,VmIPv6Configuration * *)
0x18016b01f  mov     rcx, [rbp+118h]; this
0x18016b026  lea     rdx, aFindInterfaceI_0; "Find interface Ipv4 configuration faile"...
0x18016b02d  mov     qword ptr [rsp+210h+var_1F0], rdx; int
0x18016b032  mov     r9d, eax; char *
0x18016b035  mov     r8, r13; unsigned int
0x18016b038  mov     edx, 39Dh; void *
0x18016b03d  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18016b042  mov     rsi, [rbp+110h+var_168]
0x18016b046  lea     rcx, [rbp+110h+var_90]
0x18016b04d  cmp     [rbp+110h+var_78], 7
0x18016b055  cmova   rcx, [rbp+110h+var_90]; unsigned __int16 *
0x18016b05d  mov     edx, 17h; unsigned __int16
0x18016b062  lea     r9, [rbp+110h+var_160]; struct VmIPv6Configuration **
0x18016b066  mov     r8, cs:qword_18039AE68; struct _tlgProvider_t *
0x18016b06d  call    ?GetInstance@VmIPv6Configuration@@SAJPEBGGPEBU_tlgProvider_t@@PEAPEAV1@@Z; VmIPv6Configuration::GetInstance(ushort const *,ushort,_tlgProvider_t const *,VmIPv6Configuration * *)
0x18016b072  mov     rcx, [rbp+118h]; this
0x18016b079  lea     rdx, aFindInterfaceI; "Find interface Ipv6 configuration faile"...
0x18016b080  mov     qword ptr [rsp+210h+var_1F0], rdx; int
0x18016b085  mov     r9d, eax; char *
0x18016b088  mov     r8, r13; unsigned int
0x18016b08b  mov     edx, 3A4h; void *
0x18016b090  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18016b095  mov     rbx, [r14+338h]
0x18016b09c  mov     rax, [rbp+110h+var_158]
0x18016b0a0  mov     [rsp+210h+UnbiasedTime], rax
0x18016b0a5  lea     rax, [r14+330h]
0x18016b0ac  mov     [rsp+210h+CompareAddress], rax
0x18016b0b1  lea     rdx, [rbp+110h+var_70]; retstr
0x18016b0b8  mov     rcx, rax; this
0x18016b0bb  call    ?GetActivity@IResourceable@Interface@Service@HNS@@QEBA?AU_GUID@@XZ; HNS::Service::Interface::IResourceable::GetActivity(void)
0x18016b0c0  mov     r8, rax
0x18016b0c3  lea     rdx, [rbp+110h+var_188]
0x18016b0c7  mov     rcx, rbx
0x18016b0ca  call    ?GetActivity@ResourceManager@Resource@Service@HNS@@AEAA?AV?$shared_ptr@VActivity@Resource@Service@HNS@@@std@@AEBU_GUID@@@Z; HNS::Service::Resource::ResourceManager::GetActivity(_GUID const &)
0x18016b0cf  nop
0x18016b0d0  xor     r9d, r9d
0x18016b0d3  lea     r8, [rsp+210h+UnbiasedTime]
0x18016b0d8  lea     rdx, [rsp+210h+var_1A0]
0x18016b0dd  mov     rcx, [rbp+110h+var_188]
0x18016b0e1  call    ??$AllocateResource@$0A@PEAUVariableSet@ExternalAdapterResource@Resource@Service@HNS@@@Activity@Resource@Service@HNS@@QEAA?A_PAEBQEAUVariableSet@ExternalAdapterResource@123@E@Z
0x18016b0e6  nop
0x18016b0e7  mov     rbx, [rbp+110h+var_180]
0x18016b0eb  test    rbx, rbx
0x18016b0ee  jz      short loc_18016B127
0x18016b0f0  or      eax, 0FFFFFFFFh
0x18016b0f3  lock xadd [rbx+8], eax
0x18016b0f8  cmp     eax, 1
0x18016b0fb  jnz     short loc_18016B127
0x18016b0fd  mov     rax, [rbx]
0x18016b100  mov     rcx, rbx
0x18016b103  mov     rax, [rax]
0x18016b106  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016b10b  or      eax, 0FFFFFFFFh
0x18016b10e  lock xadd [rbx+0Ch], eax
0x18016b113  cmp     eax, 1
0x18016b116  jnz     short loc_18016B127
0x18016b118  mov     rax, [rbx]
0x18016b11b  mov     rcx, rbx
0x18016b11e  mov     rax, [rax+8]
0x18016b122  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016b127  lea     rcx, [r14+4E0h]
0x18016b12e  lea     rdx, [rsp+210h+var_1A0]
0x18016b133  call    ??4?$shared_ptr@VNamespaceEntityManager@Core@Service@HNS@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<HNS::Service::Core::NamespaceEntityManager>::operator=(std::shared_ptr<HNS::Service::Core::NamespaceEntityManager> &&)
0x18016b138  mov     rbx, qword ptr [rsp+210h+var_1A0+8]
0x18016b13d  test    rbx, rbx
0x18016b140  jz      short loc_18016B179
0x18016b142  or      eax, 0FFFFFFFFh
0x18016b145  lock xadd [rbx+8], eax
0x18016b14a  cmp     eax, 1
0x18016b14d  jnz     short loc_18016B179
0x18016b14f  mov     rax, [rbx]
0x18016b152  mov     rcx, rbx
0x18016b155  mov     rax, [rax]
0x18016b158  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016b15d  or      eax, 0FFFFFFFFh
0x18016b160  lock xadd [rbx+0Ch], eax
0x18016b165  cmp     eax, 1
0x18016b168  jnz     short loc_18016B179
0x18016b16a  mov     rax, [rbx]
0x18016b16d  mov     rcx, rbx
0x18016b170  mov     rax, [rax+8]
0x18016b174  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016b179  mov     rcx, [r14+4D0h]
0x18016b180  mov     rax, [rcx]
0x18016b183  mov     r8, [rax+0A0h]
0x18016b18a  xorps   xmm0, xmm0
0x18016b18d  movdqu  xmmword ptr [rsp+210h+UnbiasedTime], xmm0
0x18016b193  lea     rax, [r14+4E0h]
0x18016b19a  mov     rdx, [rax+8]
0x18016b19e  test    rdx, rdx
0x18016b1a1  jz      short loc_18016B1A7
0x18016b1a3  lock inc dword ptr [rdx+8]
0x18016b1a7  mov     rdx, [rax]
0x18016b1aa  mov     [rsp+210h+UnbiasedTime], rdx
0x18016b1af  mov     rdx, [rax+8]
0x18016b1b3  mov     [rsp+210h+UnbiasedTime+8], rdx
0x18016b1b8  lea     rdx, [rsp+210h+UnbiasedTime]
0x18016b1bd  mov     rax, r8
0x18016b1c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016b1c5  mov     r14, [rbp+110h+var_160]
0x18016b1c9  mov     rax, [rsp+210h+var_1B0]
0x18016b1ce  mov     rcx, [rsp+210h+var_1D8]
0x18016b1d3  cmp     byte ptr [rax+50h], 1
0x18016b1d7  jnz     loc_18016B779
0x18016b1dd  mov     rbx, [rcx+338h]
0x18016b1e4  mov     [rsp+210h+var_1B0], r12
0x18016b1e9  lea     rdx, [rbp+110h+var_60]; retstr
0x18016b1f0  mov     rcx, [rsp+210h+CompareAddress]; this
0x18016b1f5  call    ?GetActivity@IResourceable@Interface@Service@HNS@@QEBA?AU_GUID@@XZ; HNS::Service::Interface::IResourceable::GetActivity(void)
0x18016b1fa  mov     byte ptr [rsp+210h+var_1F0], 0
0x18016b1ff  lea     r9, [rsp+210h+var_1B0]
0x18016b204  mov     r8, rax
0x18016b207  lea     rdx, [rsp+210h+var_1A0]
0x18016b20c  mov     rcx, rbx
0x18016b20f  call    ??$AllocateResource@$0BG@PEAUVariableSet@HostPortResource@Resource@Service@HNS@@@ResourceManager@Resource@Service@HNS@@QEAA?A_PAEBU_GUID@@AEBQEAUVariableSet@HostPortResource@123@E@Z
0x18016b214  mov     r12, [rsp+210h+var_1D8]
0x18016b219  lea     rcx, [r12+4B8h]
0x18016b221  mov     [rsp+210h+CompareAddress], rcx
0x18016b226  mov     rdx, rax
0x18016b229  call    ??4?$shared_ptr@VNamespaceEntityManager@Core@Service@HNS@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<HNS::Service::Core::NamespaceEntityManager>::operator=(std::shared_ptr<HNS::Service::Core::NamespaceEntityManager> &&)
0x18016b22e  mov     rbx, qword ptr [rsp+210h+var_1A0+8]
0x18016b233  test    rbx, rbx
0x18016b236  jz      short loc_18016B26F
0x18016b238  or      eax, 0FFFFFFFFh
0x18016b23b  lock xadd [rbx+8], eax
0x18016b240  cmp     eax, 1
0x18016b243  jnz     short loc_18016B26F
0x18016b245  mov     rax, [rbx]
0x18016b248  mov     rcx, rbx
0x18016b24b  mov     rax, [rax]
0x18016b24e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016b253  or      eax, 0FFFFFFFFh
0x18016b256  lock xadd [rbx+0Ch], eax
0x18016b25b  cmp     eax, 1
0x18016b25e  jnz     short loc_18016B26F
0x18016b260  mov     rax, [rbx]
0x18016b263  mov     rcx, rbx
0x18016b266  mov     rax, [rax+8]
0x18016b26a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016b26f  xor     eax, eax
0x18016b271  xchg    eax, [r12+630h]
0x18016b279  lea     rcx, [rbp+110h+var_188]
0x18016b27d  call    ?GetInstance@InterfaceNotificationManager@Core@Service@HNS@@SA?AV?$shared_ptr@VInterfaceNotificationManager@Core@Service@HNS@@@std@@XZ; HNS::Service::Core::InterfaceNotificationManager::GetInstance(void)
0x18016b282  nop
0x18016b283  mov     r12, [rbp+110h+var_188]
0x18016b287  mov     rbx, [rsp+210h+CompareAddress]
0x18016b28c  mov     rbx, [rbx]
0x18016b28f  mov     rbx, [rbx+0C40h]
0x18016b296  mov     rcx, [rsp+210h+var_1D8]
0x18016b29b  lea     r8, [rcx+2F0h]
0x18016b2a2  lea     rdx, [rsp+210h+var_1A0]
0x18016b2a7  mov     rcx, [rcx+328h]
0x18016b2ae  call    ??$Get@U_GUID@@@HNSObject@@QEAA?AU_GUID@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; HNSObject::Get<_GUID>(std::wstring const &)
0x18016b2b3  nop
0x18016b2b4  movaps  xmm0, [rsp+210h+var_1A0]
0x18016b2b9  movdqa  [rsp+210h+var_1A0], xmm0
0x18016b2bf  movups  xmm1, xmmword ptr cs:GUID_NULL.Data1
0x18016b2c6  movdqu  xmmword ptr [rbp+110h+var_60.Data1], xmm1
0x18016b2ce  mov     ecx, 30h ; '0'; Size
0x18016b2d3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18016b2d8  mov     [rsp+210h+var_1B0], rax
0x18016b2dd  lea     r8, [rsp+210h+var_1A0]
0x18016b2e2  lea     rdx, [rbp+110h+var_60]
0x18016b2e9  mov     rcx, rax
0x18016b2ec  call    ??$?0AEAU_GUID@@AEAU0@@?$_Ref_count_obj2@VEventRoute@Events@Service@HNS@@@std@@QEAA@AEAU_GUID@@0@Z; std::_Ref_count_obj2<HNS::Service::Events::EventRoute>::_Ref_count_obj2<HNS::Service::Events::EventRoute>(_GUID &,_GUID &)
0x18016b2f1  nop
0x18016b2f2  lea     rdx, [rax+10h]
0x18016b2f6  mov     [rsp+210h+UnbiasedTime], rdx
0x18016b2fb  mov     [rsp+210h+UnbiasedTime+8], rax
0x18016b300  mov     [rsp+210h+var_1E8], rbx; char *
0x18016b305  lea     rax, [rsp+210h+UnbiasedTime]
0x18016b30a  mov     qword ptr [rsp+210h+var_1F0], rax
0x18016b30f  mov     r9d, 3
0x18016b315  lea     r8d, [r9+19h]
0x18016b319  lea     rdx, [rbp+110h+var_70]
0x18016b320  lea     rcx, [r12+68h]
0x18016b325  call    ?SubscribeEvent@?$FilteredEventManager@T_NET_LUID_LH@@UNET_LUID_Comparator@@@Events@Service@HNS@@QEAA?AU_GUID@@W4EventType@234@W4CallbackManagerTypes@234@V?$shared_ptr@VEventRoute@Events@Service@HNS@@@std@@T_NET_LUID_LH@@@Z; HNS::Service::Events::FilteredEventManager<_NET_LUID_LH,NET_LUID_Comparator>::SubscribeEvent(HNS::Service::Events::EventType,HNS::Service::Events::CallbackManagerTypes,std::shared_ptr<HNS::Service::Events::EventRoute>,_NET_LUID_LH)
0x18016b32a  lea     rax, [rbp+110h+var_70]
0x18016b331  mov     qword ptr [rsp+210h+var_1A0], rax
0x18016b336  lea     rax, [rbp+110h+var_188]
0x18016b33a  mov     qword ptr [rsp+210h+var_1A0+8], rax
0x18016b33f  mov     rax, [rbp+118h]
0x18016b346  mov     qword ptr [rbp+110h+var_60.Data1], rax
0x18016b34d  mov     qword ptr [rbp+110h+var_60.Data4], r13
0x18016b354  mov     [rbp+110h+var_50], 0
0x18016b35f  mov     eax, 3BAh
0x18016b364  mov     [rbp+110h+var_48], ax
0x18016b36b  lea     r8, [rsp+210h+var_1A0]
0x18016b370  lea     rdx, [rbp+110h+var_60]
0x18016b377  lea     rcx, [rbp+110h+var_100]
0x18016b37b  call    wil__scope_exit_log__lambda_deba094243c325adbef6a198e573833e___
0x18016b380  nop
  ... truncated ...
```
