# CMidiDeviceManager::ActivateVirtualParentDevice(ulong,_DEVPROPERTY const *,_SW_DEVICE_CREATE_INFO const *,ushort * *)

- ea: `0x14002c6b0`
- end: `0x14002ce15`
- name: `?ActivateVirtualParentDevice@CMidiDeviceManager@@UEAAJKPEBU_DEVPROPERTY@@PEBU_SW_DEVICE_CREATE_INFO@@PEAPEAG@Z`
- size: `1893`
- prototype: `__int64 __fastcall(CMidiDeviceManager *__hidden this, unsigned int, const struct _DEVPROPERTY *, const struct _SW_DEVICE_CREATE_INFO *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `17`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x14000183c`
- `0x1400018e4`
- `0x1400054e4`
- `0x140005868`
- `0x140008b34`
- `0x14000984c`
- `0x14000a6b4`
- `0x14000c55c`
- `0x14000e1f8`
- `0x1400274d8`
- `0x14002790c`
- `0x140028c74`
- `0x14002c6b0`
- `0x140034800`
- `0x1400357b8`
- `0x140035ae0`
- `0x140035b6c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x14002c7c0`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x14002c7c0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x14002caaf`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x14002ccce`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x14002caaf`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x14002ccce`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14002c800`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14002c800`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002c7d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002c7e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002c7d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002c7e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002c7ec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002ca8e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002cb03`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002cb4e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002cbd1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002cc8b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002cd11`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002cd45`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002c7ec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002ca8e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002cb03`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002cb4e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002cbd1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002cc8b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002cd11`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002cd45`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceCreate` at `0x14002ca40`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceCreate` at `0x14002ca40`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002cb93`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002cb93`

## string_xrefs

- `0x14002cdde`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x14002ce03`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x14002c72f`: `avcore\midi2\service\exe\mididevicemanager.cpp`
- `0x14002ca67`: `avcore\midi2\service\exe\mididevicemanager.cpp`
- `0x14002cadc`: `avcore\midi2\service\exe\mididevicemanager.cpp`
- `0x14002cb27`: `avcore\midi2\service\exe\mididevicemanager.cpp`
- `0x14002cbaa`: `avcore\midi2\service\exe\mididevicemanager.cpp`
- `0x14002cce7`: `avcore\midi2\service\exe\mididevicemanager.cpp`

## pseudocode

```c
__int64 __fastcall CMidiDeviceManager::ActivateVirtualParentDevice(
        CMidiDeviceManager *this,
        unsigned int a2,
        const struct _DEVPROPERTY *a3,
        const struct _SW_DEVICE_CREATE_INFO *a4,
        unsigned __int16 **a5)
{
  _DWORD *v9; // rcx
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 v12; // rdx
  int v13; // ebx
  LPVOID *v15; // r13
  _DWORD *v16; // rdi
  void *v17; // rdx
  unsigned int v18; // r8d
  const char *v19; // r9
  HANDLE Event; // r14
  DWORD LastError; // esi
  __int64 v22; // r8
  const char *v23; // r9
  DEVPROPGUID *v24; // r8
  __int64 v25; // rsi
  unsigned int v26; // ebx
  DEVPROPGUID *v27; // rdx
  const struct _DEVPROPERTY *v28; // rax
  __int64 v29; // rdx
  char IsEnabled; // al
  LPVOID v31; // rbx
  __int64 v32; // rcx
  DEVPROPGUID *v33; // rdx
  __int64 v34; // r8
  const char *v35; // r9
  DWORD v36; // eax
  unsigned __int64 v37; // r8
  const char *v38; // r9
  __int64 v39; // r8
  const char *v40; // r9
  __int64 v41; // r8
  const char *v42; // r9
  void *v43; // rbx
  const unsigned __int16 *v44; // rdx
  char *cotaskmem_string_nothrow; // rax
  __int64 v46; // r8
  const char *v47; // r9
  _DWORD *v48; // rcx
  __int64 v49; // r8
  __int64 v50; // r9
  CMidiDeviceManager *v51; // rbx
  _MIDIPARENTDEVICE **v52; // rdx
  __int64 v53; // r8
  const char *v54; // r9
  DWORD v55; // eax
  const char *v56; // r9
  __int64 v57; // r8
  const char *v58; // r9
  __int64 v59; // r8
  const char *v60; // r9
  int v61; // [rsp+28h] [rbp-91h]
  int v62; // [rsp+28h] [rbp-91h]
  char v63; // [rsp+48h] [rbp-71h] BYREF
  int v64[4]; // [rsp+50h] [rbp-69h] BYREF
  DEVPROPGUID *v65; // [rsp+60h] [rbp-59h]
  HANDLE hObject[2]; // [rsp+68h] [rbp-51h]
  DEVPROPGUID fmtid; // [rsp+78h] [rbp-41h] BYREF
  DEVPROPGUID pid; // [rsp+88h] [rbp-31h]
  DEVPROPGUID v69; // [rsp+98h] [rbp-21h]
  int v70[2]; // [rsp+A8h] [rbp-11h] BYREF
  void *Block; // [rsp+B0h] [rbp-9h]
  CMidiDeviceManager *v72; // [rsp+B8h] [rbp-1h] BYREF
  const char *v73; // [rsp+C0h] [rbp+7h] BYREF
  char v74; // [rsp+C8h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+110h] [rbp+57h]
  LPVOID pv; // [rsp+130h] [rbp+77h] BYREF

  pv = a4;
  v9 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v9 > 4u )
  {
    Block = this;
    *(_QWORD *)v70 = "CMidiDeviceManager::ActivateVirtualParentDevice";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      (__int64)v9,
      (__int64)byte_14008A1FD,
      v10,
      v11,
      v70);
  }
  if ( !a4 )
  {
    v12 = 666;
LABEL_5:
    v13 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"avcore\\midi2\\service\\exe\\mididevicemanager.cpp",
      (const char *)0x80070057LL,
      v61);
    return (unsigned int)v13;
  }
  v15 = (LPVOID *)a5;
  if ( !a5 )
  {
    v12 = 667;
    goto LABEL_5;
  }
  v16 = operator new(0x48u);
  *(_QWORD *)v16 = 1;
  *((_QWORD *)v16 + 8) = 0;
  *((_QWORD *)v16 + 1) = 0;
  *((_QWORD *)v16 + 2) = 0;
  *((_QWORD *)v16 + 3) = 0;
  *((_OWORD *)v16 + 2) = 0;
  *((_QWORD *)v16 + 6) = 0;
  *((_QWORD *)v16 + 7) = 7;
  *((_WORD *)v16 + 16) = 0;
  *(_QWORD *)v70 = v16;
  *(_OWORD *)hObject = 0;
  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  if ( !Event )
    wil::details::in1diag3::Throw_GetLastError(retaddr, v17, v18, v19);
  GetLastError();
  if ( hObject[1] )
  {
    LastError = GetLastError();
    if ( !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v22, v23);
    SetLastError(LastError);
  }
  Block = v16;
  hObject[1] = Event;
  hObject[0] = v16;
  *(_OWORD *)v64 = 0;
  v24 = 0;
  v65 = 0;
  v25 = -1;
  v63 = -1;
  if ( a2 && a3 )
  {
    v26 = 0;
    v27 = *(DEVPROPGUID **)&v64[2];
    do
    {
      v28 = &a3[v26];
      if ( v27 == v24 )
      {
        std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(v64, v27, &a3[v26]);
        v27 = *(DEVPROPGUID **)&v64[2];
      }
      else
      {
        *v27 = v28->CompKey.Key.fmtid;
        v27[1] = *(DEVPROPGUID *)&v28->CompKey.Key.pid;
        v27[2] = *(DEVPROPGUID *)&v28->Type;
        v27 = (DEVPROPGUID *)(*(_QWORD *)&v64[2] + 48LL);
        *(_QWORD *)&v64[2] += 48LL;
      }
      ++v26;
      v24 = v65;
    }
    while ( v26 < a2 );
  }
  else
  {
    v27 = *(DEVPROPGUID **)&v64[2];
  }
  fmtid = DEVPKEY_Device_PresenceNotForDevice.fmtid;
  pid = (DEVPROPGUID)DEVPKEY_Device_PresenceNotForDevice.pid;
  *(_QWORD *)&v69.Data1 = 0x100000011LL;
  *(_QWORD *)v69.Data4 = &v63;
  if ( v27 == v24 )
  {
    std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(v64, v27, &fmtid);
    v29 = *(_QWORD *)&v64[2];
  }
  else
  {
    *v27 = DEVPKEY_Device_PresenceNotForDevice.fmtid;
    v27[1] = pid;
    v27[2] = v69;
    v29 = *(_QWORD *)&v64[2] + 48LL;
    *(_QWORD *)&v64[2] += 48LL;
  }
  fmtid = DEVPKEY_Device_NoConnectSound.fmtid;
  pid = (DEVPROPGUID)DEVPKEY_Device_NoConnectSound.pid;
  *(_QWORD *)&v69.Data1 = 0x100000011LL;
  *(_QWORD *)v69.Data4 = &v63;
  if ( (DEVPROPGUID *)v29 == v65 )
  {
    std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(v64, v29, &fmtid);
  }
  else
  {
    *(DEVPROPGUID *)v29 = DEVPKEY_Device_NoConnectSound.fmtid;
    *(DEVPROPGUID *)(v29 + 16) = pid;
    *(DEVPROPGUID *)(v29 + 32) = v69;
    *(_QWORD *)&v64[2] += 48LL;
  }
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2ContainerIds>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2ContainerIds>::GetImpl'::`2'::impl);
  v31 = pv;
  if ( IsEnabled )
  {
    fmtid = DEVPKEY_Device_FriendlyName.fmtid;
    pid = (DEVPROPGUID)DEVPKEY_Device_FriendlyName.pid;
    v69.Data1 = 18;
    v32 = *((_QWORD *)pv + 6);
    do
      ++v25;
    while ( *(_WORD *)(v32 + 2 * v25) );
    *(_DWORD *)&v69.Data2 = 2 * v25 + 2;
    *(_QWORD *)v69.Data4 = v32;
    v33 = *(DEVPROPGUID **)&v64[2];
    if ( *(DEVPROPGUID **)&v64[2] == v65 )
    {
      std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(v64, *(_QWORD *)&v64[2], &fmtid);
    }
    else
    {
      **(_OWORD **)&v64[2] = DEVPKEY_Device_FriendlyName.fmtid;
      v33[1] = pid;
      v33[2] = v69;
      *(_QWORD *)&v64[2] += 48LL;
    }
  }
  fmtid = (DEVPROPGUID)((unsigned __int64)hObject[0] + 8);
  LOBYTE(pid.Data1) = 1;
  v62 = v64[0];
  v13 = SwDeviceCreate(
          L"MIDISRV",
          L"HTREE\\ROOT\\0",
          v31,
          0xAAAAAAAAAAAAAAABuLL * ((__int64)(*(_QWORD *)&v64[2] - *(_QWORD *)v64) >> 4));
  if ( LOBYTE(pid.Data1) )
    wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSWDEVICE__ *,void (*)(HSWDEVICE__ *),&void SwDeviceClose(HSWDEVICE__ *),wistd::integral_constant<unsigned __int64,0>,HSWDEVICE__ *,HSWDEVICE__ *,0,std::nullptr_t>>>>::reset(
      *(_QWORD *)&fmtid.Data1,
      *(_QWORD *)fmtid.Data4);
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2C7,
      (unsigned int)"avcore\\midi2\\service\\exe\\mididevicemanager.cpp",
      (const char *)(unsigned int)v13,
      v62);
    std::vector<_DEVPROPERTY>::~vector<_DEVPROPERTY>((char **)v64);
    if ( hObject[1] )
    {
      if ( !CloseHandle(hObject[1]) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v34, v35);
    }
LABEL_80:
    _MIDIPARENTDEVICE::~_MIDIPARENTDEVICE((_MIDIPARENTDEVICE *)Block);
    operator delete(Block);
    return (unsigned int)v13;
  }
  v36 = WaitForSingleObjectEx(hObject[1], 0x2710u, 0);
  if ( v36 == 258 )
  {
    wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSWDEVICE__ *,void (*)(HSWDEVICE__ *),&void SwDeviceClose(HSWDEVICE__ *),wistd::integral_constant<unsigned __int64,0>,HSWDEVICE__ *,HSWDEVICE__ *,0,std::nullptr_t>>>>::reset(
      v16 + 2,
      0);
    v55 = WaitForSingleObjectEx(hObject[1], 0x2710u, 0);
    if ( v55 != 258 && v55 )
      wil::details::in1diag3::FailFast_Unexpected(
        retaddr,
        (void *)0xB0F,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v56);
    v13 = v16[16];
    if ( v13 >= 0 )
    {
      v13 = -2147467259;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2D5,
        (unsigned int)"avcore\\midi2\\service\\exe\\mididevicemanager.cpp",
        (const char *)0x80004005LL,
        v62);
      std::vector<_DEVPROPERTY>::~vector<_DEVPROPERTY>((char **)v64);
      if ( hObject[1] && !CloseHandle(hObject[1]) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v59, v60);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2D4,
        (unsigned int)"avcore\\midi2\\service\\exe\\mididevicemanager.cpp",
        (const char *)(unsigned int)v13,
        v62);
      std::vector<_DEVPROPERTY>::~vector<_DEVPROPERTY>((char **)v64);
      if ( hObject[1] && !CloseHandle(hObject[1]) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v57, v58);
    }
    goto LABEL_80;
  }
  if ( v36 )
    wil::details::in1diag3::FailFast_Unexpected(
      retaddr,
      (void *)0xB0F,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v38);
  v13 = *((_DWORD *)hObject[0] + 16);
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2D9,
      (unsigned int)"avcore\\midi2\\service\\exe\\mididevicemanager.cpp",
      (const char *)(unsigned int)v13,
      v62);
    std::vector<_DEVPROPERTY>::~vector<_DEVPROPERTY>((char **)v64);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v39, v40);
    goto LABEL_80;
  }
  if ( *(_DWORD *)hObject[0] != 2 )
  {
    v13 = -2147467259;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2DA,
      (unsigned int)"avcore\\midi2\\service\\exe\\mididevicemanager.cpp",
      (const char *)0x80004005LL,
      v62);
    std::vector<_DEVPROPERTY>::~vector<_DEVPROPERTY>((char **)v64);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v41, v42);
    goto LABEL_80;
  }
  v43 = 0;
  v44 = (const unsigned __int16 *)((char *)hObject[0] + 32);
  if ( *((_QWORD *)hObject[0] + 7) > 7u )
    v44 = *(const unsigned __int16 **)v44;
  cotaskmem_string_nothrow = (char *)wil::make_cotaskmem_string_nothrow((wil *)&pv, v44, v37);
  if ( &v74 != cotaskmem_string_nothrow )
  {
    v43 = *(void **)cotaskmem_string_nothrow;
    *(_QWORD *)cotaskmem_string_nothrow = 0;
  }
  if ( pv )
    CoTaskMemFree(pv);
  if ( !v43 )
  {
    v13 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2DE,
      (unsigned int)"avcore\\midi2\\service\\exe\\mididevicemanager.cpp",
      (const char *)0x8007000ELL,
      v62);
    std::vector<_DEVPROPERTY>::~vector<_DEVPROPERTY>((char **)v64);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v46, v47);
    goto LABEL_80;
  }
  *v15 = v43;
  v48 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v48 <= 4u )
  {
    v51 = this;
  }
  else
  {
    pv = *v15;
    v51 = this;
    v72 = this;
    v73 = "CMidiDeviceManager::ActivateVirtualParentDevice";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
      (__int64)v48,
      (__int64)byte_140089F2B,
      v49,
      v50,
      &v73,
      (__int64)&v72,
      &pv);
  }
  if ( *((int *)hObject[0] + 16) >= 0 )
  {
    v52 = (_MIDIPARENTDEVICE **)*((_QWORD *)v51 + 22);
    if ( v52 == *((_MIDIPARENTDEVICE ***)v51 + 23) )
    {
      std::vector<std::unique_ptr<_MIDIPARENTDEVICE>>::_Emplace_reallocate<std::unique_ptr<_MIDIPARENTDEVICE>>(
        (_MIDIPARENTDEVICE ***)v51 + 21,
        v52,
        (__int64 *)v70);
      v16 = *(_DWORD **)v70;
    }
    else
    {
      v16 = 0;
      *v52 = (_MIDIPARENTDEVICE *)Block;
      *((_QWORD *)v51 + 22) += 8LL;
    }
  }
  std::vector<_DEVPROPERTY>::~vector<_DEVPROPERTY>((char **)v64);
  if ( hObject[1] && !CloseHandle(hObject[1]) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v53, v54);
  if ( v16 )
  {
    _MIDIPARENTDEVICE::~_MIDIPARENTDEVICE((_MIDIPARENTDEVICE *)v16);
    operator delete(v16);
  }
  return 0;
}

```

## disassembly

```asm
0x14002c6b0  mov     rax, rsp
0x14002c6b3  mov     [rax+10h], rbx
0x14002c6b7  mov     [rax+20h], r9
0x14002c6bb  mov     [rax+8], rcx
0x14002c6bf  push    rbp
0x14002c6c0  push    rsi
0x14002c6c1  push    rdi
0x14002c6c2  push    r12
0x14002c6c4  push    r13
0x14002c6c6  push    r14
0x14002c6c8  push    r15
0x14002c6ca  lea     rbp, [rax-57h]
0x14002c6ce  sub     rsp, 0D0h
0x14002c6d5  mov     rbx, r9
0x14002c6d8  mov     r15, r8
0x14002c6db  mov     r12d, edx
0x14002c6de  mov     rdi, rcx
0x14002c6e1  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14002c6e6  mov     rcx, [rax+8]
0x14002c6ea  mov     eax, [rcx]
0x14002c6ec  lea     rdx, aCmidideviceman_1; "CMidiDeviceManager::ActivateVirtualPare"...
0x14002c6f3  cmp     eax, 4
0x14002c6f6  jbe     short loc_14002C71E
0x14002c6f8  mov     [rbp+4Fh+Block], rdi
0x14002c6fc  mov     qword ptr [rbp+4Fh+var_60], rdx
0x14002c700  lea     rax, [rbp+4Fh+Block]
0x14002c704  mov     [rsp+100h+var_D8], rax
0x14002c709  lea     rax, [rbp+4Fh+var_60]
0x14002c70d  mov     qword ptr [rsp+100h+var_E0], rax; int
0x14002c712  lea     rdx, byte_14008A1FD
0x14002c719  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x14002c71e  xor     esi, esi
0x14002c720  test    rbx, rbx
0x14002c723  jnz     short loc_14002C75F
0x14002c725  mov     edx, 29Ah; void *
0x14002c72a  mov     ebx, 80070057h
0x14002c72f  lea     r8, aAvcoreMidi2Ser_9; "avcore\\midi2\\service\\exe\\mididevice"...
0x14002c736  mov     r9d, ebx; char *
0x14002c739  mov     rcx, [rbp+57h]; this
0x14002c73d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002c742  mov     eax, ebx
0x14002c744  mov     rbx, [rsp+100h+arg_8]
0x14002c74c  add     rsp, 0D0h
0x14002c753  pop     r15
0x14002c755  pop     r14
0x14002c757  pop     r13
0x14002c759  pop     r12
0x14002c75b  pop     rdi
0x14002c75c  pop     rsi
0x14002c75d  pop     rbp
0x14002c75e  retn
0x14002c75f  mov     r13, [rbp+4Fh+arg_20]
0x14002c763  test    r13, r13
0x14002c766  jnz     short loc_14002C76F
0x14002c768  mov     edx, 29Bh
0x14002c76d  jmp     short loc_14002C72A
0x14002c76f  mov     ecx, 48h ; 'H'; Size
0x14002c774  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14002c779  mov     rdi, rax
0x14002c77c  mov     qword ptr [rax], 1
0x14002c783  mov     [rax+40h], rsi
0x14002c787  mov     [rax+8], rsi
0x14002c78b  mov     [rax+10h], rsi
0x14002c78f  mov     [rax+18h], rsi
0x14002c793  xorps   xmm0, xmm0
0x14002c796  movups  xmmword ptr [rax+20h], xmm0
0x14002c79a  mov     [rax+30h], rsi
0x14002c79e  mov     qword ptr [rax+38h], 7
0x14002c7a6  mov     [rax+20h], si
0x14002c7aa  mov     qword ptr [rbp+4Fh+var_60], rax
0x14002c7ae  movdqu  xmmword ptr [rbp+4Fh+hObject], xmm0
0x14002c7b3  mov     r9d, 1F0003h; dwDesiredAccess
0x14002c7b9  xor     r8d, r8d; dwFlags
0x14002c7bc  xor     edx, edx; lpName
0x14002c7be  xor     ecx, ecx; lpEventAttributes
0x14002c7c0  call    cs:__imp_CreateEventExW
0x14002c7c6  mov     r14, rax
0x14002c7c9  test    rax, rax
0x14002c7cc  jz      loc_14002CDC5
0x14002c7d2  call    cs:__imp_GetLastError
0x14002c7d8  mov     rbx, [rbp+4Fh+hObject+8]
0x14002c7dc  test    rbx, rbx
0x14002c7df  jz      short loc_14002C806
0x14002c7e1  call    cs:__imp_GetLastError
0x14002c7e7  mov     esi, eax
0x14002c7e9  mov     rcx, rbx; hObject
0x14002c7ec  call    cs:__imp_CloseHandle
0x14002c7f2  mov     rcx, [rbp+57h]; this
0x14002c7f6  test    eax, eax
0x14002c7f8  jz      loc_14002CDCF
0x14002c7fe  mov     ecx, esi; dwErrCode
0x14002c800  call    cs:__imp_SetLastError
0x14002c806  mov     [rbp+4Fh+Block], rdi
0x14002c80a  mov     [rbp+4Fh+hObject+8], r14
0x14002c80e  mov     [rbp+4Fh+hObject], rdi
0x14002c812  xorps   xmm0, xmm0
0x14002c815  movdqu  xmmword ptr [rbp+4Fh+var_B8], xmm0
0x14002c81a  xor     r14d, r14d
0x14002c81d  mov     r8d, r14d
0x14002c820  mov     [rbp+4Fh+var_A8], r14
0x14002c824  or      rsi, 0FFFFFFFFFFFFFFFFh
0x14002c828  mov     [rbp+4Fh+var_C0], sil
0x14002c82c  test    r12d, r12d
0x14002c82f  jz      short loc_14002C890
0x14002c831  test    r15, r15
0x14002c834  jz      short loc_14002C890
0x14002c836  mov     ebx, r14d
0x14002c839  mov     rdx, qword ptr [rbp+4Fh+var_B8+8]
0x14002c83d  mov     eax, ebx
0x14002c83f  lea     rax, [rax+rax*2]
0x14002c843  shl     rax, 4
0x14002c847  add     rax, r15
0x14002c84a  cmp     rdx, r8
0x14002c84d  jz      short loc_14002C873
0x14002c84f  movups  xmm0, xmmword ptr [rax]
0x14002c852  movups  xmmword ptr [rdx], xmm0
0x14002c855  movups  xmm1, xmmword ptr [rax+10h]
0x14002c859  movups  xmmword ptr [rdx+10h], xmm1
0x14002c85d  movups  xmm0, xmmword ptr [rax+20h]
0x14002c861  movups  xmmword ptr [rdx+20h], xmm0
0x14002c865  mov     rdx, qword ptr [rbp+4Fh+var_B8+8]
0x14002c869  add     rdx, 30h ; '0'
0x14002c86d  mov     qword ptr [rbp+4Fh+var_B8+8], rdx
0x14002c871  jmp     short loc_14002C883
0x14002c873  mov     r8, rax
0x14002c876  lea     rcx, [rbp+4Fh+var_B8]
0x14002c87a  call    ??$_Emplace_reallocate@U_DEVPROPERTY@@@?$vector@U_DEVPROPERTY@@V?$allocator@U_DEVPROPERTY@@@std@@@std@@AEAAPEAU_DEVPROPERTY@@QEAU2@$$QEAU2@@Z; std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(_DEVPROPERTY * const,_DEVPROPERTY &&)
0x14002c87f  mov     rdx, qword ptr [rbp+4Fh+var_B8+8]
0x14002c883  inc     ebx
0x14002c885  mov     r8, [rbp+4Fh+var_A8]
0x14002c889  cmp     ebx, r12d
0x14002c88c  jb      short loc_14002C83D
0x14002c88e  jmp     short loc_14002C894
0x14002c890  mov     rdx, qword ptr [rbp+4Fh+var_B8+8]
0x14002c894  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_PresenceNotForDevice.fmtid.Data1
0x14002c89b  movups  [rbp+4Fh+var_90], xmm0
0x14002c89f  mov     eax, cs:DEVPKEY_Device_PresenceNotForDevice.pid
0x14002c8a5  mov     dword ptr [rbp+4Fh+var_80], eax
0x14002c8a8  mov     dword ptr [rbp+4Fh+var_80+4], r14d
0x14002c8ac  mov     qword ptr [rbp+4Fh+var_80+8], r14
0x14002c8b0  mov     ebx, 11h
0x14002c8b5  mov     dword ptr [rbp+4Fh+var_70], ebx
0x14002c8b8  lea     r15d, [rbx-10h]
0x14002c8bc  mov     dword ptr [rbp+4Fh+var_70+4], r15d
0x14002c8c0  lea     rax, [rbp+4Fh+var_C0]
0x14002c8c4  mov     qword ptr [rbp+4Fh+var_70+8], rax
0x14002c8c8  cmp     rdx, r8
0x14002c8cb  jz      short loc_14002C8EE
0x14002c8cd  movups  xmmword ptr [rdx], xmm0
0x14002c8d0  movups  xmm0, [rbp+4Fh+var_80]
0x14002c8d4  movups  xmmword ptr [rdx+10h], xmm0
0x14002c8d8  movups  xmm1, [rbp+4Fh+var_70]
0x14002c8dc  movups  xmmword ptr [rdx+20h], xmm1
0x14002c8e0  mov     rdx, qword ptr [rbp+4Fh+var_B8+8]
0x14002c8e4  add     rdx, 30h ; '0'
0x14002c8e8  mov     qword ptr [rbp+4Fh+var_B8+8], rdx
0x14002c8ec  jmp     short loc_14002C8FF
0x14002c8ee  lea     r8, [rbp+4Fh+var_90]
0x14002c8f2  lea     rcx, [rbp+4Fh+var_B8]
0x14002c8f6  call    ??$_Emplace_reallocate@U_DEVPROPERTY@@@?$vector@U_DEVPROPERTY@@V?$allocator@U_DEVPROPERTY@@@std@@@std@@AEAAPEAU_DEVPROPERTY@@QEAU2@$$QEAU2@@Z; std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(_DEVPROPERTY * const,_DEVPROPERTY &&)
0x14002c8fb  mov     rdx, qword ptr [rbp+4Fh+var_B8+8]
0x14002c8ff  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_NoConnectSound.fmtid.Data1
0x14002c906  movups  [rbp+4Fh+var_90], xmm0
0x14002c90a  mov     eax, cs:DEVPKEY_Device_NoConnectSound.pid
0x14002c910  mov     dword ptr [rbp+4Fh+var_80], eax
0x14002c913  mov     dword ptr [rbp+4Fh+var_80+4], r14d
0x14002c917  mov     qword ptr [rbp+4Fh+var_80+8], r14
0x14002c91b  mov     dword ptr [rbp+4Fh+var_70], ebx
0x14002c91e  mov     dword ptr [rbp+4Fh+var_70+4], r15d
0x14002c922  lea     rax, [rbp+4Fh+var_C0]
0x14002c926  mov     qword ptr [rbp+4Fh+var_70+8], rax
0x14002c92a  cmp     rdx, [rbp+4Fh+var_A8]
0x14002c92e  jz      short loc_14002C94A
0x14002c930  movups  xmmword ptr [rdx], xmm0
0x14002c933  movups  xmm0, [rbp+4Fh+var_80]
0x14002c937  movups  xmmword ptr [rdx+10h], xmm0
0x14002c93b  movups  xmm1, [rbp+4Fh+var_70]
0x14002c93f  movups  xmmword ptr [rdx+20h], xmm1
0x14002c943  add     qword ptr [rbp+4Fh+var_B8+8], 30h ; '0'
0x14002c948  jmp     short loc_14002C957
0x14002c94a  lea     r8, [rbp+4Fh+var_90]
0x14002c94e  lea     rcx, [rbp+4Fh+var_B8]
0x14002c952  call    ??$_Emplace_reallocate@U_DEVPROPERTY@@@?$vector@U_DEVPROPERTY@@V?$allocator@U_DEVPROPERTY@@@std@@@std@@AEAAPEAU_DEVPROPERTY@@QEAU2@$$QEAU2@@Z; std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(_DEVPROPERTY * const,_DEVPROPERTY &&)
0x14002c957  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_MIDI2ContainerIds@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2ContainerIds@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2ContainerIds> `wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2ContainerIds>::GetImpl(void)'::`2'::impl
0x14002c95e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2ContainerIds@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2ContainerIds>::__private_IsEnabled(void)
0x14002c963  mov     rbx, [rbp+4Fh+pv]
0x14002c967  test    al, al
0x14002c969  jz      short loc_14002C9DB
0x14002c96b  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_FriendlyName.fmtid.Data1
0x14002c972  movups  [rbp+4Fh+var_90], xmm0
0x14002c976  mov     eax, cs:DEVPKEY_Device_FriendlyName.pid
0x14002c97c  mov     dword ptr [rbp+4Fh+var_80], eax
0x14002c97f  mov     dword ptr [rbp+4Fh+var_80+4], r14d
0x14002c983  mov     qword ptr [rbp+4Fh+var_80+8], r14
0x14002c987  mov     dword ptr [rbp+4Fh+var_70], 12h
0x14002c98e  mov     rcx, [rbx+30h]
0x14002c992  inc     rsi
0x14002c995  cmp     [rcx+rsi*2], r14w
0x14002c99a  jnz     short loc_14002C992
0x14002c99c  lea     eax, ds:2[rsi*2]
0x14002c9a3  mov     dword ptr [rbp+4Fh+var_70+4], eax
0x14002c9a6  mov     qword ptr [rbp+4Fh+var_70+8], rcx
0x14002c9aa  mov     rdx, qword ptr [rbp+4Fh+var_B8+8]
0x14002c9ae  cmp     rdx, [rbp+4Fh+var_A8]
0x14002c9b2  jz      short loc_14002C9CE
0x14002c9b4  movups  xmmword ptr [rdx], xmm0
0x14002c9b7  movups  xmm0, [rbp+4Fh+var_80]
0x14002c9bb  movups  xmmword ptr [rdx+10h], xmm0
0x14002c9bf  movups  xmm1, [rbp+4Fh+var_70]
0x14002c9c3  movups  xmmword ptr [rdx+20h], xmm1
0x14002c9c7  add     qword ptr [rbp+4Fh+var_B8+8], 30h ; '0'
0x14002c9cc  jmp     short loc_14002C9DB
0x14002c9ce  lea     r8, [rbp+4Fh+var_90]
0x14002c9d2  lea     rcx, [rbp+4Fh+var_B8]
0x14002c9d6  call    ??$_Emplace_reallocate@U_DEVPROPERTY@@@?$vector@U_DEVPROPERTY@@V?$allocator@U_DEVPROPERTY@@@std@@@std@@AEAAPEAU_DEVPROPERTY@@QEAU2@$$QEAU2@@Z; std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(_DEVPROPERTY * const,_DEVPROPERTY &&)
0x14002c9db  mov     rax, [rbp+4Fh+hObject]
0x14002c9df  add     rax, 8
0x14002c9e3  mov     qword ptr [rbp+4Fh+var_90], rax
0x14002c9e7  mov     qword ptr [rbp+4Fh+var_90+8], r14
0x14002c9eb  mov     byte ptr [rbp+4Fh+var_80], r15b
0x14002c9ef  mov     rax, qword ptr [rbp+4Fh+var_B8]
0x14002c9f3  mov     r9, qword ptr [rbp+4Fh+var_B8+8]
0x14002c9f7  sub     r9, rax
0x14002c9fa  sar     r9, 4
0x14002c9fe  mov     rcx, 0AAAAAAAAAAAAAAABh
0x14002ca08  imul    r9, rcx
0x14002ca0c  lea     rcx, [rbp+4Fh+var_90+8]
0x14002ca10  mov     [rsp+38h], rcx
0x14002ca15  lea     rcx, [rbp+4Fh+hObject]
0x14002ca19  mov     [rsp+100h+var_D0], rcx
0x14002ca1e  lea     rcx, ?SwMidiParentDeviceCreateCallback@@YAXPEAUHSWDEVICE__@@JPEAXPEBG@Z; SwMidiParentDeviceCreateCallback(HSWDEVICE__ *,long,void *,ushort const *)
0x14002ca25  mov     [rsp+100h+var_D8], rcx
0x14002ca2a  mov     qword ptr [rsp+100h+var_E0], rax; int
0x14002ca2f  mov     r8, rbx
0x14002ca32  lea     rdx, aHtreeRoot0; "HTREE\\ROOT\\0"
0x14002ca39  lea     rcx, aMidisrv; "MIDISRV"
0x14002ca40  call    cs:__imp_SwDeviceCreate
0x14002ca46  mov     ebx, eax
0x14002ca48  cmp     byte ptr [rbp+4Fh+var_80], r14b
0x14002ca4c  jz      short loc_14002CA5C
0x14002ca4e  mov     rdx, qword ptr [rbp+4Fh+var_90+8]
0x14002ca52  mov     rcx, qword ptr [rbp+4Fh+var_90]
0x14002ca56  call    ?reset@?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSWDEVICE__@@P6AXPEAU1@@Z$1?SwDeviceClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAXPEAUHSWDEVICE__@@@Z; wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSWDEVICE__ *,void (*)(HSWDEVICE__ *),&SwDeviceClose(HSWDEVICE__ *),wistd::integral_constant<unsigned __int64,0>,HSWDEVICE__ *,HSWDEVICE__ *,0,std::nullptr_t>>>>::reset(HSWDEVICE__ *)
0x14002ca5b  nop
0x14002ca5c  test    ebx, ebx
0x14002ca5e  jns     short loc_14002CAA1
0x14002ca60  mov     rcx, [rbp+57h]; this
0x14002ca64  mov     r9d, ebx; char *
0x14002ca67  lea     r8, aAvcoreMidi2Ser_9; "avcore\\midi2\\service\\exe\\mididevice"...
0x14002ca6e  mov     edx, 2C7h; void *
0x14002ca73  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002ca78  lea     rcx, [rbp+4Fh+var_B8]
0x14002ca7c  call    ??1?$vector@U_DEVPROPERTY@@V?$allocator@U_DEVPROPERTY@@@std@@@std@@QEAA@XZ; std::vector<_DEVPROPERTY>::~vector<_DEVPROPERTY>(void)
0x14002ca81  mov     rcx, [rbp+4Fh+hObject+8]; hObject
0x14002ca85  test    rcx, rcx
0x14002ca88  jz      loc_14002CD4F
0x14002ca8e  call    cs:__imp_CloseHandle
0x14002ca94  test    eax, eax
0x14002ca96  jz      loc_14002CD7A
0x14002ca9c  jmp     loc_14002CD4F
0x14002caa1  xor     r8d, r8d; bAlertable
0x14002caa4  mov     ebx, 2710h
0x14002caa9  mov     edx, ebx; dwMilliseconds
0x14002caab  mov     rcx, [rbp+4Fh+hObject+8]; hHandle
0x14002caaf  call    cs:__imp_WaitForSingleObjectEx
0x14002cab5  mov     esi, 102h
0x14002caba  cmp     eax, esi
0x14002cabc  jz      loc_14002CCBA
0x14002cac2  test    eax, eax
0x14002cac4  jnz     loc_14002CDDA
0x14002caca  mov     rdx, [rbp+4Fh+hObject]
0x14002cace  mov     ebx, [rdx+40h]
0x14002cad1  test    ebx, ebx
0x14002cad3  jns     short loc_14002CB16
0x14002cad5  mov     rcx, [rbp+57h]; this
0x14002cad9  mov     r9d, ebx; char *
0x14002cadc  lea     r8, aAvcoreMidi2Ser_9; "avcore\\midi2\\service\\exe\\mididevice"...
0x14002cae3  mov     edx, 2D9h; void *
0x14002cae8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002caed  lea     rcx, [rbp+4Fh+var_B8]
0x14002caf1  call    ??1?$vector@U_DEVPROPERTY@@V?$allocator@U_DEVPROPERTY@@@std@@@std@@QEAA@XZ; std::vector<_DEVPROPERTY>::~vector<_DEVPROPERTY>(void)
0x14002caf6  mov     rcx, [rbp+4Fh+hObject+8]; hObject
0x14002cafa  test    rcx, rcx
0x14002cafd  jz      loc_14002CD4F
0x14002cb03  call    cs:__imp_CloseHandle
0x14002cb09  test    eax, eax
0x14002cb0b  jz      loc_14002CD89
0x14002cb11  jmp     loc_14002CD4F
0x14002cb16  cmp     dword ptr [rdx], 2
0x14002cb19  jz      short loc_14002CB61
0x14002cb1b  mov     rcx, [rbp+57h]; this
0x14002cb1f  mov     ebx, 80004005h
0x14002cb24  mov     r9d, ebx; char *
0x14002cb27  lea     r8, aAvcoreMidi2Ser_9; "avcore\\midi2\\service\\exe\\mididevice"...
0x14002cb2e  mov     edx, 2DAh; void *
0x14002cb33  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002cb38  lea     rcx, [rbp+4Fh+var_B8]
0x14002cb3c  call    ??1?$vector@U_DEVPROPERTY@@V?$allocator@U_DEVPROPERTY@@@std@@@std@@QEAA@XZ; std::vector<_DEVPROPERTY>::~vector<_DEVPROPERTY>(void)
0x14002cb41  mov     rcx, [rbp+4Fh+hObject+8]; hObject
0x14002cb45  test    rcx, rcx
  ... truncated ...
```
