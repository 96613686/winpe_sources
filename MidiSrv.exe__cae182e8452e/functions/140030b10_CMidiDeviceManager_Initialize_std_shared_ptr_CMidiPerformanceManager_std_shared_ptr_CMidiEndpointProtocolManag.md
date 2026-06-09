# CMidiDeviceManager::Initialize(std::shared_ptr<CMidiPerformanceManager> &,std::shared_ptr<CMidiEndpointProtocolManager> &,std::shared_ptr<CMidiConfigurationManager> &,std::shared_ptr<CMidiClientManager> &)

- ea: `0x140030b10`
- end: `0x140031826`
- name: `?Initialize@CMidiDeviceManager@@UEAAJAEAV?$shared_ptr@VCMidiPerformanceManager@@@std@@AEAV?$shared_ptr@VCMidiEndpointProtocolManager@@@3@AEAV?$shared_ptr@VCMidiConfigurationManager@@@3@AEAV?$shared_ptr@VCMidiClientManager@@@3@@Z`
- size: `3350`
- prototype: `__int64 __fastcall(__int64, _QWORD *, _QWORD *, _QWORD *, __int64)`
- caller_count: `0`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x14000179c`
- `0x14000183c`
- `0x1400018e4`
- `0x140002580`
- `0x14000307c`
- `0x1400054c0`
- `0x140007c20`
- `0x14000984c`
- `0x14000c598`
- `0x1400144ac`
- `0x140022f94`
- `0x1400238a4`
- `0x140024010`
- `0x1400252b8`
- `0x1400282e0`
- `0x140029448`
- `0x140030b10`
- `0x14005a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140030edf`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140030edf`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140030c68`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140030c68`

## string_xrefs

- `0x140030d58`: `Getting transport configuration JSON`
- `0x140030f82`: `Activating transport configuration manager.`
- `0x1400310ff`: `Failed to initialize transport configuration manager.`
- `0x140030ef4`: `avcore\midi2\service\exe\mididevicemanager.cpp`
- `0x1400310d5`: `avcore\midi2\service\exe\mididevicemanager.cpp`
- `0x1400312d5`: `avcore\midi2\service\exe\mididevicemanager.cpp`
- `0x14003151f`: `avcore\midi2\service\exe\mididevicemanager.cpp`
- `0x1400312ff`: `Failed to update configuration.`
- `0x140031367`: `Configuration updated.`
- `0x1400311c0`: `Updating transport configuration`
- `0x14003127b`: `Config update not implemented for this transport.`
- `0x140031048`: `Transport transport configuration manager activation failed with null result.`
- `0x1400313de`: `Transport transport configuration manager activation failed.`
- `0x140030c53`: `MidisrvTransferComplete`

## pseudocode

```c
__int64 __fastcall CMidiDeviceManager::Initialize(__int64 a1, _QWORD *a2, _QWORD *a3, _QWORD *a4, __int64 a5)
{
  _DWORD *v7; // rcx
  int v8; // r8d
  int v9; // r9d
  __int64 v10; // rax
  __int64 v11; // rcx
  volatile signed __int32 *v12; // rsi
  _DWORD *v13; // rcx
  int v14; // r8d
  int v15; // r9d
  IID *v16; // rsi
  _DWORD *v17; // rcx
  int v18; // r8d
  int v19; // r9d
  struct _GUID *v20; // rdx
  _DWORD *v21; // rcx
  int v22; // r8d
  int v23; // r9d
  LPVOID v24; // rcx
  HRESULT v25; // eax
  _DWORD *v26; // rcx
  int v27; // r8d
  int v28; // r9d
  int *v29; // rax
  __int16 *v30; // rdx
  _DWORD *v31; // rcx
  int v32; // r8d
  int v33; // r9d
  LPVOID v34; // r14
  __int64 (__fastcall *v35)(LPVOID, GUID *, const char **); // r12
  const char *v36; // rcx
  int v37; // r14d
  _DWORD *v38; // rcx
  int v39; // r8d
  int v40; // r9d
  int *v41; // rax
  __int64 *v42; // rdx
  int v43; // eax
  int v44; // r14d
  _DWORD *v45; // rcx
  int v46; // r8d
  int v47; // r9d
  GUID *p_rguid; // rax
  __int16 *v49; // rdx
  const char **v50; // rax
  const char *v51; // rcx
  const char *v52; // r14
  _DWORD *v53; // rcx
  int v54; // r8d
  int v55; // r9d
  _QWORD *v56; // rdx
  int v57; // eax
  _DWORD *v58; // rcx
  _DWORD *v59; // rcx
  int v60; // r8d
  int v61; // r9d
  LPVOID v62; // r14
  __int64 (__fastcall *v63)(LPVOID, GUID *, _QWORD *); // r12
  __int64 v64; // rcx
  int v65; // eax
  __int64 v66; // r14
  _DWORD *v67; // rcx
  int v68; // r8d
  int v69; // r9d
  _DWORD *v70; // rcx
  int v71; // r8d
  int v72; // r9d
  const wchar_t *v73; // rax
  __int16 *v74; // rdx
  _QWORD *v75; // rdx
  __int64 v76; // rax
  __int64 v77; // rdx
  volatile signed __int32 *v78; // rsi
  int pdwType; // [rsp+20h] [rbp-2B8h]
  int *pvData; // [rsp+28h] [rbp-2B0h]
  int *pvDataa; // [rsp+28h] [rbp-2B0h]
  int *pvDatab; // [rsp+28h] [rbp-2B0h]
  const wchar_t **pcbData; // [rsp+30h] [rbp-2A8h]
  const wchar_t **pcbDataa; // [rsp+30h] [rbp-2A8h]
  const wchar_t **pcbDatab; // [rsp+30h] [rbp-2A8h]
  GUID *v87; // [rsp+38h] [rbp-2A0h]
  GUID *v88; // [rsp+38h] [rbp-2A0h]
  GUID *v89; // [rsp+40h] [rbp-298h]
  int v90[2]; // [rsp+50h] [rbp-288h] BYREF
  const wchar_t *v91; // [rsp+58h] [rbp-280h] BYREF
  const wchar_t *v92; // [rsp+60h] [rbp-278h] BYREF
  int v93[2]; // [rsp+68h] [rbp-270h] BYREF
  GUID rguid; // [rsp+70h] [rbp-268h] BYREF
  LPVOID ppv; // [rsp+80h] [rbp-258h] BYREF
  const char *v96; // [rsp+88h] [rbp-250h] BYREF
  _QWORD v97[3]; // [rsp+90h] [rbp-248h] BYREF
  int v98; // [rsp+A8h] [rbp-230h] BYREF
  __int64 *v99; // [rsp+B0h] [rbp-228h] BYREF
  DWORD v100; // [rsp+B8h] [rbp-220h] BYREF
  _QWORD *v101; // [rsp+C0h] [rbp-218h]
  IID *v102; // [rsp+C8h] [rbp-210h]
  __int64 v103[4]; // [rsp+D0h] [rbp-208h] BYREF
  __int64 v104; // [rsp+F0h] [rbp-1E8h]
  IID *rclsid[5]; // [rsp+F8h] [rbp-1E0h] BYREF
  char v106[224]; // [rsp+120h] [rbp-1B8h] BYREF
  _QWORD v107[18]; // [rsp+200h] [rbp-D8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+0h]

  v97[2] = a1;
  v101 = a2;
  v104 = a5;
  v98 = 0;
  v100 = 4;
  v7 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v7 > 4u )
  {
    v99 = (__int64 *)a1;
    ppv = "CMidiDeviceManager::Initialize";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      (_DWORD)v7,
      (unsigned int)qword_140089368,
      v8,
      v9,
      (__int64)&ppv,
      (__int64)&v99);
  }
  v99 = (__int64 *)(a1 + 48);
  v10 = a4[1];
  if ( v10 )
    _InterlockedIncrement((volatile signed __int32 *)(v10 + 8));
  v11 = a4[1];
  *(_QWORD *)(a1 + 48) = *a4;
  v12 = *(volatile signed __int32 **)(a1 + 56);
  *(_QWORD *)(a1 + 56) = v11;
  if ( v12 )
  {
    if ( _InterlockedExchangeAdd(v12 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
      if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
    }
  }
  if ( !RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Drivers32",
          L"MidisrvTransferComplete",
          0x18u,
          0,
          &v98,
          &v100)
    && v98 != 1 )
  {
    v13 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
    if ( *v13 > 2u )
    {
      ppv = L"AudioEndpointBuilder retains control of Midi port registration, unable to take exclusive control of midi ports.";
      v97[0] = a1;
      v96 = "CMidiDeviceManager::Initialize";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v13,
        (unsigned int)word_140088BC2,
        v14,
        v15,
        (__int64)&v96,
        (__int64)v97,
        (__int64)&ppv);
    }
    *(_BYTE *)(a1 + 160) = 0;
  }
  CMidiConfigurationManager::GetEnabledTransports(*v99, rclsid);
  v16 = rclsid[0];
  v102 = rclsid[1];
  while ( 1 )
  {
    v97[1] = v16;
    if ( v16 == v102 )
      break;
    ppv = 0;
    v97[0] = 0;
    v96 = 0;
    v17 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
    if ( *v17 > 4u )
    {
      *(_QWORD *)v93 = v16;
      *(_QWORD *)v90 = L"Getting transport configuration JSON";
      v91 = (const wchar_t *)a1;
      v92 = (const wchar_t *)"CMidiDeviceManager::Initialize";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>>(
        (_DWORD)v17,
        (unsigned int)&dword_140089C1C,
        v18,
        v19,
        (__int64)&v92,
        (__int64)&v91,
        (__int64)v90,
        (__int64)v93);
    }
    rguid = *v16;
    CMidiConfigurationManager::GetSavedConfigurationForTransport(*v99, v107, &rguid);
    v21 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
    if ( *v21 > 4u )
    {
      v92 = (const wchar_t *)v16;
      v91 = L"CoCreating transport layer";
      *(_QWORD *)v90 = a1;
      *(_QWORD *)v93 = "CMidiDeviceManager::Initialize";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>>(
        (_DWORD)v21,
        (unsigned int)byte_14008A365,
        v22,
        v23,
        (__int64)v93,
        (__int64)v90,
        (__int64)&v91,
        (__int64)&v92);
    }
    rguid = *v16;
    if ( (int)WindowsMidiServicesInternal::IsComponentPermitted(&rguid, v20) < 0 )
    {
      std::wstring::~wstring(v107);
      if ( v96 )
        (*(void (__fastcall **)(const char *))(*(_QWORD *)v96 + 16LL))(v96);
      if ( v97[0] )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v97[0] + 16LL))(v97[0]);
      if ( ppv )
        goto LABEL_94;
      goto LABEL_95;
    }
    v24 = ppv;
    ppv = 0;
    if ( v24 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v24 + 16LL))(v24);
    v25 = CoCreateInstance(v16, 0, 0x17u, &GUID_ea264200_3328_49e5_8815_73649a8748be, &ppv);
    if ( v25 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x95,
        (unsigned int)"avcore\\midi2\\service\\exe\\mididevicemanager.cpp",
        (const char *)(unsigned int)v25,
        pdwType);
    if ( !ppv )
    {
      v26 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
      if ( *v26 <= 2u )
        goto LABEL_89;
      v92 = (const wchar_t *)v16;
      v91 = L"Transport Transport activation failed (nullptr return).";
      *(_QWORD *)v90 = a1;
      *(_QWORD *)v93 = "CMidiDeviceManager::Initialize";
      v87 = (GUID *)&v92;
      pcbData = &v91;
      pvData = v90;
      v29 = v93;
      v30 = word_14008914A;
LABEL_76:
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>>(
        (_DWORD)v26,
        (_DWORD)v30,
        v27,
        v28,
        (__int64)v29,
        (__int64)pvData,
        (__int64)pcbData,
        (__int64)v87);
      goto LABEL_89;
    }
    v31 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
    if ( *v31 > 4u )
    {
      v92 = (const wchar_t *)v16;
      v91 = L"Activating transport configuration manager.";
      *(_QWORD *)v90 = a1;
      *(_QWORD *)v93 = "CMidiDeviceManager::Initialize";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>>(
        (_DWORD)v31,
        (unsigned int)byte_140088B31,
        v32,
        v33,
        (__int64)v93,
        (__int64)v90,
        (__int64)&v91,
        (__int64)&v92);
    }
    v34 = ppv;
    v35 = *(__int64 (__fastcall **)(LPVOID, GUID *, const char **))(*(_QWORD *)ppv + 24LL);
    v36 = v96;
    v96 = 0;
    if ( v36 )
      (*(void (__fastcall **)(const char *))(*(_QWORD *)v36 + 16LL))(v36);
    v37 = v35(v34, &GUID_f19dd642_1809_4497_9eee_f230b11bd6fb, &v96);
    if ( v37 < 0 )
    {
      v58 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
      if ( *v58 > 2u )
      {
        v93[0] = v37;
        *(_QWORD *)&rguid.Data1 = a1;
        v107[16] = v16;
        v107[17] = 16;
        v107[14] = L"Transport transport configuration manager activation failed.";
        v107[15] = 122;
        v107[12] = v93;
        v107[13] = 4;
        v107[10] = &rguid;
        v107[11] = 8;
        v107[8] = "CMidiDeviceManager::Initialize";
        v107[9] = 31;
        pdwType = 7;
        tlgWriteTransfer_EventWriteTransfer(v58, &dword_140088B74, 0, 0);
      }
    }
    else
    {
      if ( !v96 )
      {
        v38 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
        if ( *v38 <= 2u )
          goto LABEL_67;
        v92 = (const wchar_t *)v16;
        v91 = L"Transport transport configuration manager activation failed with null result.";
        *(_QWORD *)v90 = a1;
        *(_QWORD *)v93 = "CMidiDeviceManager::Initialize";
        v88 = (GUID *)&v92;
        pcbDataa = &v91;
        pvDataa = v90;
        v41 = v93;
        v42 = qword_140089B58;
        goto LABEL_42;
      }
      rguid = *v16;
      v43 = (*(__int64 (__fastcall **)(const char *, GUID *, __int64, __int64))(*(_QWORD *)v96 + 24LL))(
              v96,
              &rguid,
              a1,
              *v99);
      v44 = v43;
      if ( v43 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xB4,
          (unsigned int)"avcore\\midi2\\service\\exe\\mididevicemanager.cpp",
          (const char *)(unsigned int)v43,
          pdwType);
        v45 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
        if ( *v45 <= 2u )
          goto LABEL_67;
        v92 = (const wchar_t *)v16;
        v91 = L"Failed to initialize transport configuration manager.";
        *(_QWORD *)v90 = a1;
        *(_QWORD *)&rguid.Data1 = "CMidiDeviceManager::Initialize";
        v89 = (GUID *)&v92;
        pcbDatab = &v91;
        pvDatab = v90;
        p_rguid = &rguid;
        v49 = (__int16 *)byte_140089481;
LABEL_46:
        v93[0] = v44;
LABEL_47:
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
          (_DWORD)v45,
          (_DWORD)v49,
          v46,
          v47,
          (__int64)p_rguid,
          (__int64)pvDatab,
          (__int64)pcbDatab,
          (__int64)v93,
          (__int64)v89);
        goto LABEL_67;
      }
      v50 = (const char **)std::map<_GUID,wil::com_ptr_t<IMidiTransportConfigurationManager,wil::err_returncode_policy>,GUIDCompare,std::allocator<std::pair<_GUID const,wil::com_ptr_t<IMidiTransportConfigurationManager,wil::err_returncode_policy>>>>::operator[](
                             a1 + 80,
                             v16);
      v51 = v96;
      v52 = *v50;
      *v50 = v96;
      if ( v51 )
        (*(void (__fastcall **)(const char *))(*(_QWORD *)v51 + 8LL))(v51);
      if ( v52 )
        (*(void (__fastcall **)(const char *))(*(_QWORD *)v52 + 16LL))(v52);
      if ( v107[2] )
      {
        v53 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
        if ( *v53 > 4u )
        {
          *(_QWORD *)&rguid.Data1 = v16;
          v92 = L"Updating transport configuration";
          v91 = (const wchar_t *)a1;
          *(_QWORD *)v90 = "CMidiDeviceManager::Initialize";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>>(
            (_DWORD)v53,
            (unsigned int)byte_140089391,
            v54,
            v55,
            (__int64)v90,
            (__int64)&v91,
            (__int64)&v92,
            (__int64)&rguid);
        }
        v103[0] = 0;
        v56 = v107;
        if ( v107[3] > 7u )
          v56 = (_QWORD *)v107[0];
        v57 = (*(__int64 (__fastcall **)(const char *, _QWORD *, __int64 *))(*(_QWORD *)v96 + 32LL))(v96, v56, v103);
        v44 = v57;
        if ( v57 >= 0 )
        {
          v38 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
          if ( *v38 > 4u )
          {
            *(_QWORD *)&rguid.Data1 = v16;
            v92 = L"Configuration updated.";
            v91 = (const wchar_t *)a1;
            *(_QWORD *)v90 = "CMidiDeviceManager::Initialize";
            v88 = &rguid;
            pcbDataa = &v92;
            pvDataa = (int *)&v91;
            v41 = v90;
            v42 = (__int64 *)byte_140089D85;
LABEL_42:
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>>(
              (_DWORD)v38,
              (_DWORD)v42,
              v39,
              v40,
              (__int64)v41,
              (__int64)pvDataa,
              (__int64)pcbDataa,
              (__int64)v88);
          }
        }
        else if ( v57 == -2147467263 )
        {
          v45 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
          if ( *v45 > 3u )
          {
            *(_QWORD *)&rguid.Data1 = v16;
            v93[0] = -2147467263;
            v92 = L"Config update not implemented for this transport.";
            v91 = (const wchar_t *)a1;
            *(_QWORD *)v90 = "CMidiDeviceManager::Initialize";
            v89 = &rguid;
            pcbDatab = &v92;
            pvDatab = (int *)&v91;
            p_rguid = (GUID *)v90;
            v49 = &word_14008927E;
            goto LABEL_47;
          }
        }
        else
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0xE7,
            (unsigned int)"avcore\\midi2\\service\\exe\\mididevicemanager.cpp",
            (const char *)(unsigned int)v57,
            pdwType);
          v45 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
          if ( *v45 > 2u )
          {
            *(_QWORD *)&rguid.Data1 = v16;
            v92 = L"Failed to update configuration.";
            v91 = (const wchar_t *)a1;
            *(_QWORD *)v90 = "CMidiDeviceManager::Initialize";
            v89 = &rguid;
            pcbDatab = &v92;
            pvDatab = (int *)&v91;
            p_rguid = (GUID *)v90;
            v49 = &word_14008918E;
            goto LABEL_46;
          }
        }
      }
    }
LABEL_67:
    v59 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
    if ( *v59 > 4u )
    {
      *(_QWORD *)&rguid.Data1 = v16;
      v92 = L"Activating transport layer IMidiEndpointManager";
      v91 = (const wchar_t *)a1;
      *(_QWORD *)v90 = "CMidiDeviceManager::Initialize";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>>(
        (_DWORD)v59,
        (unsigned int)&word_14008943E,
        v60,
        v61,
        (__int64)v90,
        (__int64)&v91,
        (__int64)&v92,
        (__int64)&rguid);
    }
    v62 = ppv;
    v63 = *(__int64 (__fastcall **)(LPVOID, GUID *, _QWORD *))(*(_QWORD *)ppv + 24LL);
    v64 = v97[0];
    v97[0] = 0;
    if ( v64 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
    v65 = v63(v62, &GUID_badff6d2_0e3c_4009_a473_6ba82c008662, v97);
    if ( v65 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x12D,
        (unsigned int)"avcore\\midi2\\service\\exe\\mididevicemanager.cpp",
        (const char *)(unsigned int)v65,
        pdwType);
    if ( !v97[0] )
    {
      v26 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
      if ( *v26 <= 2u )
        goto LABEL_89;
      *(_QWORD *)&rguid.Data1 = v16;
      v92 = L"Transport transport endpoint manager initialization failed.";
      v91 = (const wchar_t *)a1;
      *(_QWORD *)v90 = "CMidiDeviceManager::Initialize";
      v87 = &rguid;
      pcbData = &v92;
      pvData = (int *)&v91;
      v29 = v90;
      v30 = (__int16 *)byte_140088D51;
      goto LABEL_76;
    }
    *(_QWORD *)v93 = *a3;
    v66 = *(_QWORD *)v93;
    if ( *(_QWORD *)v93 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v93 + 8LL))(*(_QWORD *)v93);
    v67 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
    if ( *v67 > 4u )
    {
      *(_QWORD *)&rguid.Data1 = v16;
      v92 = L"Initializing transport layer Midi Endpoint Manager";
      v91 = (const wchar_t *)a1;
      *(_QWORD *)v90 = "CMidiDeviceManager::Initialize";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>>(
        (_DWORD)v67,
        (unsigned int)&word_140088D0E,
        v68,
        v69,
        (__int64)v90,
        (__int64)&v91,
        (__int64)&v92,
        (__int64)&rguid);
    }
    if ( (*(int (__fastcall **)(_QWORD, __int64, __int64))(*(_QWORD *)v97[0] + 24LL))(v97[0], a1, v66) < 0 )
    {
      v70 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
      if ( *v70 <= 2u )
        goto LABEL_87;
      v73 = L"Transport transport initialization failed.";
      v74 = &word_1400892CE;
    }
    else
    {
      std::_Tree<std::_Tmap_traits<_GUID,wil::com_ptr_t<IMidiEndpointManager,wil::err_returncode_policy>,GUIDCompare,std::allocator<std::pair<_GUID const,wil::com_ptr_t<IMidiEndpointManager,wil::err_returncode_policy>>>,0>>::emplace<_GUID const &,wil::com_ptr_t<IMidiEndpointManager,wil::err_returncode_policy>>(
        a1 + 64,
        v106,
        v16,
        v97);
      v70 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
      if ( *v70 <= 4u )
        goto LABEL_87;
      v73 = L"Midi Endpoint Manager initialized";
      v74 = word_14008A65A;
    }
    v92 = v73;
    *(_QWORD *)&rguid.Data1 = v16;
    v91 = (const wchar_t *)a1;
    *(_QWORD *)v90 = "CMidiDeviceManager::Initialize";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>>(
      (_DWORD)v70,
      (_DWORD)v74,
      v71,
      v72,
      (__int64)v90,
      (__int64)&v91,
      (__int64)&v92,
      (__int64)&rguid);
LABEL_87:
    if ( v66 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v66 + 16LL))(v66);
LABEL_89:
    std::wstring::~wstring(v107);
    if ( v96 )
      (*(void (__fastcall **)(const char *))(*(_QWORD *)v96 + 16LL))(v96);
    if ( v97[0] )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v97[0] + 16LL))(v97[0]);
    if ( ppv )
LABEL_94:
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
LABEL_95:
    ++v16;
  }
  std::vector<_GUID>::~vector<_GUID>(rclsid);
  v75 = v101;
  v76 = v101[1];
  if ( v76 )
    _InterlockedIncrement((volatile signed __int32 *)(v76 + 8));
  v77 = v75[1];
  *(_QWORD *)(a1 + 32) = *v101;
  v78 = *(volatile signed __int32 **)(a1 + 40);
  *(_QWORD *)(a1 + 40) = v77;
  if ( v78 )
  {
    if ( _InterlockedExchangeAdd(v78 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v78)(v78);
      if ( _InterlockedExchangeAdd(v78 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v78 + 8LL))(v78);
    }
  }
  std::shared_ptr<CMidiSessionTracker>::operator=(a1 + 16, v104);
  return 0;
}

```

## disassembly

```asm
0x140030b10  mov     [rsp+arg_10], r8
0x140030b15  push    rbx
0x140030b16  push    rsi
0x140030b17  push    rdi
0x140030b18  push    r12
0x140030b1a  push    r14
0x140030b1c  push    r15
0x140030b1e  sub     rsp, 2A8h
0x140030b25  mov     rax, cs:__security_cookie
0x140030b2c  xor     rax, rsp
0x140030b2f  mov     [rsp+2D8h+var_48], rax
0x140030b37  mov     rsi, r9
0x140030b3a  mov     rdi, rcx
0x140030b3d  mov     [rsp+2D8h+var_238], rcx
0x140030b45  mov     [rsp+2D8h+var_218], rdx
0x140030b4d  mov     rax, [rsp+2D8h+arg_20]
0x140030b55  mov     [rsp+2D8h+var_1E8], rax
0x140030b5d  xor     ebx, ebx
0x140030b5f  mov     [rsp+2D8h+var_230], ebx
0x140030b66  mov     [rsp+2D8h+var_220], 4
0x140030b71  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x140030b76  mov     rcx, [rax+8]
0x140030b7a  mov     eax, [rcx]
0x140030b7c  cmp     eax, 4
0x140030b7f  jbe     short loc_140030BC0
0x140030b81  mov     [rsp+2D8h+var_228], rdi
0x140030b89  lea     r15, aCmidideviceman_7; "CMidiDeviceManager::Initialize"
0x140030b90  mov     [rsp+2D8h+ppv], r15
0x140030b98  lea     rax, [rsp+2D8h+var_228]
0x140030ba0  mov     [rsp+2D8h+pvData], rax
0x140030ba5  lea     rax, [rsp+2D8h+ppv]
0x140030bad  mov     [rsp+2D8h+pdwType], rax
0x140030bb2  lea     rdx, qword_140089368
0x140030bb9  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x140030bbe  jmp     short loc_140030BC7
0x140030bc0  lea     r15, aCmidideviceman_7; "CMidiDeviceManager::Initialize"
0x140030bc7  lea     rdx, [rdi+30h]
0x140030bcb  mov     [rsp+2D8h+var_228], rdx
0x140030bd3  mov     rax, [rsi+8]
0x140030bd7  test    rax, rax
0x140030bda  jz      short loc_140030BE0
0x140030bdc  lock inc dword ptr [rax+8]
0x140030be0  mov     rcx, [rsi+8]
0x140030be4  mov     rax, [rsi]
0x140030be7  mov     [rdx], rax
0x140030bea  mov     rsi, [rdx+8]
0x140030bee  mov     [rdx+8], rcx
0x140030bf2  test    rsi, rsi
0x140030bf5  jz      short loc_140030C2E
0x140030bf7  or      eax, 0FFFFFFFFh
0x140030bfa  lock xadd [rsi+8], eax
0x140030bff  cmp     eax, 1
0x140030c02  jnz     short loc_140030C2E
0x140030c04  mov     rax, [rsi]
0x140030c07  mov     rcx, rsi
0x140030c0a  mov     rax, [rax]
0x140030c0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030c12  or      eax, 0FFFFFFFFh
0x140030c15  lock xadd [rsi+0Ch], eax
0x140030c1a  cmp     eax, 1
0x140030c1d  jnz     short loc_140030C2E
0x140030c1f  mov     rax, [rsi]
0x140030c22  mov     rcx, rsi
0x140030c25  mov     rax, [rax+8]
0x140030c29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030c2e  lea     rax, [rsp+2D8h+var_220]
0x140030c36  mov     [rsp+2D8h+pcbData], rax; pcbData
0x140030c3b  lea     rax, [rsp+2D8h+var_230]
0x140030c43  mov     [rsp+2D8h+pvData], rax; pvData
0x140030c48  mov     [rsp+2D8h+pdwType], rbx; pdwType
0x140030c4d  mov     r9d, 18h; dwFlags
0x140030c53  lea     r8, aMidisrvtransfe; "MidisrvTransferComplete"
0x140030c5a  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x140030c61  mov     rcx, 0FFFFFFFF80000002h; hkey
0x140030c68  call    cs:__imp_RegGetValueW
0x140030c6e  test    eax, eax
0x140030c70  jnz     short loc_140030CE4
0x140030c72  cmp     [rsp+2D8h+var_230], 1
0x140030c7a  jz      short loc_140030CE4
0x140030c7c  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x140030c81  mov     rcx, [rax+8]
0x140030c85  mov     eax, [rcx]
0x140030c87  cmp     eax, 2
0x140030c8a  jbe     short loc_140030CDE
0x140030c8c  lea     rax, aAudioendpointb; "AudioEndpointBuilder retains control of"...
0x140030c93  mov     [rsp+2D8h+ppv], rax
0x140030c9b  mov     [rsp+2D8h+var_248], rdi
0x140030ca3  mov     [rsp+2D8h+var_250], r15
0x140030cab  lea     rax, [rsp+2D8h+ppv]
0x140030cb3  mov     [rsp+2D8h+pcbData], rax
0x140030cb8  lea     rax, [rsp+2D8h+var_248]
0x140030cc0  mov     [rsp+2D8h+pvData], rax
0x140030cc5  lea     rax, [rsp+2D8h+var_250]
0x140030ccd  mov     [rsp+2D8h+pdwType], rax
0x140030cd2  lea     rdx, word_140088BC2
0x140030cd9  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x140030cde  mov     [rdi+0A0h], bl
0x140030ce4  lea     rdx, [rsp+2D8h+rclsid]
0x140030cec  mov     rcx, [rsp+2D8h+var_228]
0x140030cf4  mov     rcx, [rcx]
0x140030cf7  call    ?GetEnabledTransports@CMidiConfigurationManager@@QEBA?AV?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@XZ; CMidiConfigurationManager::GetEnabledTransports(void)
0x140030cfc  nop
0x140030cfd  mov     rsi, [rsp+2D8h+rclsid]
0x140030d05  mov     rax, [rsp+2D8h+var_1D8]
0x140030d0d  mov     [rsp+2D8h+var_210], rax
0x140030d15  mov     [rsp+2D8h+var_240], rsi
0x140030d1d  cmp     rsi, [rsp+2D8h+var_210]
0x140030d25  jz      loc_140031779
0x140030d2b  mov     [rsp+2D8h+ppv], rbx
0x140030d33  mov     [rsp+2D8h+var_248], rbx
0x140030d3b  mov     [rsp+2D8h+var_250], rbx
0x140030d43  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x140030d48  mov     rcx, [rax+8]
0x140030d4c  mov     eax, [rcx]
0x140030d4e  cmp     eax, 4
0x140030d51  jbe     short loc_140030DA2
0x140030d53  mov     qword ptr [rsp+2D8h+var_270], rsi
0x140030d58  lea     rax, aGettingTranspo; "Getting transport configuration JSON"
0x140030d5f  mov     qword ptr [rsp+2D8h+var_288], rax
0x140030d64  mov     [rsp+2D8h+var_280], rdi
0x140030d69  mov     [rsp+2D8h+var_278], r15
0x140030d6e  lea     rax, [rsp+2D8h+var_270]
0x140030d73  mov     [rsp+2D8h+var_2A0], rax
0x140030d78  lea     rax, [rsp+2D8h+var_288]
0x140030d7d  mov     [rsp+2D8h+pcbData], rax
0x140030d82  lea     rax, [rsp+2D8h+var_280]
0x140030d87  mov     [rsp+2D8h+pvData], rax
0x140030d8c  lea     rax, [rsp+2D8h+var_278]
0x140030d91  mov     [rsp+2D8h+pdwType], rax
0x140030d96  lea     rdx, dword_140089C1C
0x140030d9d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByRef<16> const &)
0x140030da2  movups  xmm0, xmmword ptr [rsi]
0x140030da5  movdqu  xmmword ptr [rsp+2D8h+rguid.Data1], xmm0
0x140030dab  lea     r8, [rsp+2D8h+rguid]
0x140030db0  lea     rdx, [rsp+2D8h+var_D8]
0x140030db8  mov     rcx, [rsp+2D8h+var_228]
0x140030dc0  mov     rcx, [rcx]
0x140030dc3  call    ?GetSavedConfigurationForTransport@CMidiConfigurationManager@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_GUID@@@Z; CMidiConfigurationManager::GetSavedConfigurationForTransport(_GUID)
0x140030dc8  nop
0x140030dc9  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x140030dce  mov     rcx, [rax+8]
0x140030dd2  mov     eax, [rcx]
0x140030dd4  cmp     eax, 4
0x140030dd7  jbe     short loc_140030E28
0x140030dd9  mov     [rsp+2D8h+var_278], rsi
0x140030dde  lea     rax, aCocreatingTran; "CoCreating transport layer"
0x140030de5  mov     [rsp+2D8h+var_280], rax
0x140030dea  mov     qword ptr [rsp+2D8h+var_288], rdi
0x140030def  mov     qword ptr [rsp+2D8h+var_270], r15
0x140030df4  lea     rax, [rsp+2D8h+var_278]
0x140030df9  mov     [rsp+2D8h+var_2A0], rax
0x140030dfe  lea     rax, [rsp+2D8h+var_280]
0x140030e03  mov     [rsp+2D8h+pcbData], rax
0x140030e08  lea     rax, [rsp+2D8h+var_288]
0x140030e0d  mov     [rsp+2D8h+pvData], rax
0x140030e12  lea     rax, [rsp+2D8h+var_270]
0x140030e17  mov     [rsp+2D8h+pdwType], rax
0x140030e1c  lea     rdx, byte_14008A365
0x140030e23  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByRef<16> const &)
0x140030e28  movups  xmm0, xmmword ptr [rsi]
0x140030e2b  movdqu  xmmword ptr [rsp+2D8h+rguid.Data1], xmm0
0x140030e31  lea     rcx, [rsp+2D8h+rguid]; rguid
0x140030e36  call    ?IsComponentPermitted@WindowsMidiServicesInternal@@YAJU_GUID@@@Z; WindowsMidiServicesInternal::IsComponentPermitted(_GUID)
0x140030e3b  test    eax, eax
0x140030e3d  jns     short loc_140030EA0
0x140030e3f  lea     rcx, [rsp+2D8h+var_D8]; void *
0x140030e47  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140030e4c  nop
0x140030e4d  mov     rcx, [rsp+2D8h+var_250]
0x140030e55  test    rcx, rcx
0x140030e58  jz      short loc_140030E67
0x140030e5a  mov     rax, [rcx]
0x140030e5d  mov     rax, [rax+10h]
0x140030e61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030e66  nop
0x140030e67  mov     rcx, [rsp+2D8h+var_248]
0x140030e6f  test    rcx, rcx
0x140030e72  jz      short loc_140030E81
0x140030e74  mov     rax, [rcx]
0x140030e77  mov     rax, [rax+10h]
0x140030e7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030e80  nop
0x140030e81  mov     rcx, [rsp+2D8h+ppv]
0x140030e89  test    rcx, rcx
0x140030e8c  jz      short loc_140030E9B
0x140030e8e  mov     rax, [rcx]
0x140030e91  mov     rax, [rax+10h]
0x140030e95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030e9a  nop
0x140030e9b  jmp     loc_14003176C
0x140030ea0  mov     rcx, [rsp+2D8h+ppv]
0x140030ea8  mov     [rsp+2D8h+ppv], rbx
0x140030eb0  test    rcx, rcx
0x140030eb3  jz      short loc_140030EC2
0x140030eb5  mov     rax, [rcx]
0x140030eb8  mov     rax, [rax+10h]
0x140030ebc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030ec1  nop
0x140030ec2  lea     rax, [rsp+2D8h+ppv]
0x140030eca  mov     [rsp+2D8h+pdwType], rax; int
0x140030ecf  lea     r9, _GUID_ea264200_3328_49e5_8815_73649a8748be; riid
0x140030ed6  xor     edx, edx; pUnkOuter
0x140030ed8  lea     r8d, [rdx+17h]; dwClsContext
0x140030edc  mov     rcx, rsi; rclsid
0x140030edf  call    cs:__imp_CoCreateInstance
0x140030ee5  mov     rcx, [rsp+2D8h]; this
0x140030eed  test    eax, eax
0x140030eef  jns     short loc_140030F05
0x140030ef1  mov     r9d, eax; char *
0x140030ef4  lea     r8, aAvcoreMidi2Ser_9; "avcore\\midi2\\service\\exe\\mididevice"...
0x140030efb  mov     edx, 95h; void *
0x140030f00  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140030f05  cmp     [rsp+2D8h+ppv], rbx
0x140030f0d  jnz     short loc_140030F6D
0x140030f0f  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x140030f14  mov     rcx, [rax+8]
0x140030f18  mov     eax, [rcx]
0x140030f1a  cmp     eax, 2
0x140030f1d  jbe     loc_1400316F5
0x140030f23  mov     [rsp+2D8h+var_278], rsi
0x140030f28  lea     rax, aTransportTrans_1; "Transport Transport activation failed ("...
0x140030f2f  mov     [rsp+2D8h+var_280], rax
0x140030f34  mov     qword ptr [rsp+2D8h+var_288], rdi
0x140030f39  mov     qword ptr [rsp+2D8h+var_270], r15
0x140030f3e  lea     rax, [rsp+2D8h+var_278]
0x140030f43  mov     [rsp+2D8h+var_2A0], rax
0x140030f48  lea     rax, [rsp+2D8h+var_280]
0x140030f4d  mov     [rsp+2D8h+pcbData], rax
0x140030f52  lea     rax, [rsp+2D8h+var_288]
0x140030f57  mov     [rsp+2D8h+pvData], rax
0x140030f5c  lea     rax, [rsp+2D8h+var_270]
0x140030f61  lea     rdx, word_14008914A
0x140030f68  jmp     loc_140031593
0x140030f6d  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x140030f72  mov     rcx, [rax+8]
0x140030f76  mov     eax, [rcx]
0x140030f78  cmp     eax, 4
0x140030f7b  jbe     short loc_140030FCC
0x140030f7d  mov     [rsp+2D8h+var_278], rsi
0x140030f82  lea     rax, aActivatingTran; "Activating transport configuration mana"...
0x140030f89  mov     [rsp+2D8h+var_280], rax
0x140030f8e  mov     qword ptr [rsp+2D8h+var_288], rdi
0x140030f93  mov     qword ptr [rsp+2D8h+var_270], r15
0x140030f98  lea     rax, [rsp+2D8h+var_278]
0x140030f9d  mov     [rsp+2D8h+var_2A0], rax
0x140030fa2  lea     rax, [rsp+2D8h+var_280]
0x140030fa7  mov     [rsp+2D8h+pcbData], rax
0x140030fac  lea     rax, [rsp+2D8h+var_288]
0x140030fb1  mov     [rsp+2D8h+pvData], rax
0x140030fb6  lea     rax, [rsp+2D8h+var_270]
0x140030fbb  mov     [rsp+2D8h+pdwType], rax; int
0x140030fc0  lea     rdx, byte_140088B31
0x140030fc7  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByRef<16> const &)
0x140030fcc  mov     r14, [rsp+2D8h+ppv]
0x140030fd4  mov     rax, [r14]
0x140030fd7  mov     r12, [rax+18h]
0x140030fdb  mov     rcx, [rsp+2D8h+var_250]
0x140030fe3  mov     [rsp+2D8h+var_250], rbx
0x140030feb  test    rcx, rcx
0x140030fee  jz      short loc_140030FFD
0x140030ff0  mov     rdx, [rcx]
0x140030ff3  mov     rax, [rdx+10h]
0x140030ff7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030ffc  nop
0x140030ffd  lea     r8, [rsp+2D8h+var_250]
0x140031005  lea     rdx, _GUID_f19dd642_1809_4497_9eee_f230b11bd6fb
0x14003100c  mov     rcx, r14
0x14003100f  mov     rax, r12
0x140031012  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140031017  mov     r14d, eax
0x14003101a  test    eax, eax
0x14003101c  js      loc_1400313AC
0x140031022  mov     rcx, [rsp+2D8h+var_250]
0x14003102a  test    rcx, rcx
0x14003102d  jnz     short loc_140031097
0x14003102f  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x140031034  mov     rcx, [rax+8]
0x140031038  mov     eax, [rcx]
0x14003103a  cmp     eax, 2
0x14003103d  jbe     loc_140031466
0x140031043  mov     [rsp+2D8h+var_278], rsi
0x140031048  lea     rax, aTransportTrans_0; "Transport transport configuration manag"...
0x14003104f  mov     [rsp+2D8h+var_280], rax
0x140031054  mov     qword ptr [rsp+2D8h+var_288], rdi
0x140031059  mov     qword ptr [rsp+2D8h+var_270], r15
0x14003105e  lea     rax, [rsp+2D8h+var_278]
0x140031063  mov     [rsp+2D8h+var_2A0], rax
0x140031068  lea     rax, [rsp+2D8h+var_280]
0x14003106d  mov     [rsp+2D8h+pcbData], rax
0x140031072  lea     rax, [rsp+2D8h+var_288]
0x140031077  mov     [rsp+2D8h+pvData], rax
0x14003107c  lea     rax, [rsp+2D8h+var_270]
0x140031081  lea     rdx, qword_140089B58
0x140031088  mov     [rsp+2D8h+pdwType], rax
0x14003108d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByRef<16> const &)
0x140031092  jmp     loc_140031466
0x140031097  movups  xmm0, xmmword ptr [rsi]
0x14003109a  movdqu  xmmword ptr [rsp+2D8h+rguid.Data1], xmm0
0x1400310a0  mov     rax, [rcx]
0x1400310a3  mov     r9, [rsp+2D8h+var_228]
  ... truncated ...
```
