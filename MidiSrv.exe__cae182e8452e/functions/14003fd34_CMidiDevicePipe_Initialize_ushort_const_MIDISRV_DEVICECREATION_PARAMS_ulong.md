# CMidiDevicePipe::Initialize(ushort const *,MIDISRV_DEVICECREATION_PARAMS *,ulong *)

- ea: `0x14003fd34`
- end: `0x140040aa2`
- name: `?Initialize@CMidiDevicePipe@@QEAAJPEBGPEAUMIDISRV_DEVICECREATION_PARAMS@@PEAK@Z`
- size: `3438`
- prototype: `__int64 __fastcall(CMidiDevicePipe *__hidden this, const unsigned __int16 *, struct MIDISRV_DEVICECREATION_PARAMS *, unsigned int *)`
- caller_count: `1`
- callee_count: `22`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400193c4`

## callees

- `0x140001ce8`
- `0x1400054c0`
- `0x14000984c`
- `0x14000a6b4`
- `0x14000cc2c`
- `0x140012008`
- `0x140012b5c`
- `0x1400133f0`
- `0x1400136c4`
- `0x14001386c`
- `0x1400140c4`
- `0x1400145bc`
- `0x140014688`
- `0x140014f04`
- `0x14001b8c0`
- `0x14001bd28`
- `0x14001c390`
- `0x14001ecb4`
- `0x1400252b8`
- `0x140030a38`
- `0x14003fd34`
- `0x14005a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x14003ffa3`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x14003ffa3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14003fe08`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14003fe08`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14003fe67`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140040a04`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140040a6c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14003fe67`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140040a04`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140040a6c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14004026d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14004045e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140040650`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14004026d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14004045e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140040650`

## string_xrefs

- `0x14003fe4d`: `avcore\midi2\service\exe\mididevicepipe.cpp`
- `0x14004017a`: `avcore\midi2\service\exe\mididevicepipe.cpp`
- `0x140040285`: `avcore\midi2\service\exe\mididevicepipe.cpp`
- `0x140040313`: `avcore\midi2\service\exe\mididevicepipe.cpp`
- `0x140040397`: `avcore\midi2\service\exe\mididevicepipe.cpp`
- `0x140040476`: `avcore\midi2\service\exe\mididevicepipe.cpp`
- `0x140040504`: `avcore\midi2\service\exe\mididevicepipe.cpp`
- `0x140040588`: `avcore\midi2\service\exe\mididevicepipe.cpp`
- `0x140040668`: `avcore\midi2\service\exe\mididevicepipe.cpp`
- `0x1400406f6`: `avcore\midi2\service\exe\mididevicepipe.cpp`
- `0x14004076c`: `avcore\midi2\service\exe\mididevicepipe.cpp`
- `0x140040a19`: `avcore\midi2\service\exe\mididevicepipe.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CMidiDevicePipe::Initialize(
        CMidiDevicePipe *this,
        const unsigned __int16 *a2,
        struct MIDISRV_DEVICECREATION_PARAMS *a3,
        unsigned int *a4)
{
  const unsigned __int16 *v5; // r14
  CMidiDevicePipe *v6; // rsi
  _DWORD *v7; // rcx
  int v8; // r8d
  int v9; // r9d
  RTL_SRWLOCK *v10; // rdi
  int v11; // eax
  LSTATUS IsComponentPermitted; // r15d
  __int64 v14; // rcx
  const wchar_t *v15; // rax
  __int64 v16; // rax
  __int64 v17; // rdx
  GUID *v18; // rax
  GUID v19; // xmm0
  struct _GUID *v20; // rdx
  __int64 v21; // rdx
  _DWORD *v22; // rcx
  int v23; // r8d
  int v24; // r9d
  HRESULT v25; // eax
  LPVOID v26; // r15
  __int64 (__fastcall *v27)(LPVOID, GUID *, char *); // rax
  _QWORD *v28; // rcx
  int v29; // eax
  __int64 v30; // rcx
  int v31; // eax
  _DWORD *v32; // rcx
  int v33; // r8d
  int v34; // r9d
  HRESULT v35; // eax
  LPVOID v36; // r15
  __int64 (__fastcall *v37)(LPVOID, GUID *, char *); // rax
  _QWORD *v38; // rcx
  int v39; // eax
  __int64 v40; // rcx
  int v41; // eax
  _DWORD *v42; // rcx
  int v43; // r8d
  int v44; // r9d
  HRESULT v45; // eax
  LPVOID v46; // r15
  __int64 (__fastcall *v47)(LPVOID, GUID *, char *); // rax
  _QWORD *v48; // rcx
  int v49; // eax
  __int64 v50; // rcx
  int v51; // eax
  __int64 v52; // rax
  const char *v53; // r9
  char HasKey; // r15
  __int64 v55; // rax
  _DWORD *v56; // rcx
  int v57; // r8d
  int v58; // r9d
  GUID *ppv; // [rsp+20h] [rbp-148h]
  int ppva; // [rsp+20h] [rbp-148h]
  int ppvb; // [rsp+20h] [rbp-148h]
  int ppvc; // [rsp+20h] [rbp-148h]
  CMidiDevicePipe *v63; // [rsp+40h] [rbp-128h] BYREF
  __int64 v64; // [rsp+48h] [rbp-120h] BYREF
  __int64 v65; // [rsp+50h] [rbp-118h] BYREF
  LPVOID v66; // [rsp+58h] [rbp-110h] BYREF
  const wchar_t *v67; // [rsp+60h] [rbp-108h] BYREF
  unsigned int *v68; // [rsp+68h] [rbp-100h] BYREF
  struct MIDISRV_DEVICECREATION_PARAMS *v69; // [rsp+70h] [rbp-F8h] BYREF
  int *v70; // [rsp+78h] [rbp-F0h] BYREF
  int v71; // [rsp+80h] [rbp-E8h] BYREF
  int v72; // [rsp+84h] [rbp-E4h]
  const wchar_t *v73; // [rsp+90h] [rbp-D8h]
  const wchar_t *v74; // [rsp+98h] [rbp-D0h] BYREF
  char v75; // [rsp+A0h] [rbp-C8h]
  const unsigned __int16 *v76; // [rsp+A8h] [rbp-C0h] BYREF
  CMidiDevicePipe *v77; // [rsp+B0h] [rbp-B8h] BYREF
  const wchar_t *v78; // [rsp+B8h] [rbp-B0h] BYREF
  RTL_SRWLOCK *v79; // [rsp+C0h] [rbp-A8h] BYREF
  __int128 v80; // [rsp+C8h] [rbp-A0h] BYREF
  LPVOID *v81; // [rsp+D8h] [rbp-90h]
  const wchar_t *v82; // [rsp+E0h] [rbp-88h]
  char *v83; // [rsp+E8h] [rbp-80h]
  GUID rguid; // [rsp+F0h] [rbp-78h] BYREF
  __int128 v85; // [rsp+100h] [rbp-68h] BYREF
  unsigned __int64 v86; // [rsp+110h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+0h]

  v68 = a4;
  v69 = a3;
  v5 = a2;
  v6 = this;
  v77 = this;
  v78 = a2;
  v7 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v7 > 4u )
  {
    v76 = v5;
    v67 = L"Enter";
    v63 = v6;
    v66 = "CMidiDevicePipe::Initialize";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (_DWORD)v7,
      (unsigned int)byte_14008B5DD,
      v8,
      v9,
      (__int64)&v66,
      (__int64)&v63,
      (__int64)&v67,
      (__int64)&v76);
  }
  v10 = (RTL_SRWLOCK *)((char *)v6 + 120);
  v79 = (RTL_SRWLOCK *)((char *)v6 + 120);
  AcquireSRWLockExclusive((PSRWLOCK)v6 + 15);
  v83 = (char *)v6 + 120;
  v85 = 0;
  v86 = 0;
  v11 = CMidiPipe::Initialize(v6, v5, *((unsigned int *)a3 + 1));
  IsComponentPermitted = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x23,
      (unsigned int)"avcore\\midi2\\service\\exe\\mididevicepipe.cpp",
      (const char *)(unsigned int)v11,
      (int)ppv);
LABEL_5:
    if ( v6 != (CMidiDevicePipe *)-120LL )
      ReleaseSRWLockExclusive((PSRWLOCK)v6 + 15);
    return (unsigned int)IsComponentPermitted;
  }
  LODWORD(v85) = 0;
  DWORD1(v85) = *(_DWORD *)a3;
  *((_QWORD *)&v85 + 1) = 0x4197D8146B467626LL;
  v86 = 0xA5FB01B67128F595uLL;
  v80 = 0;
  v81 = 0;
  winrt::single_threaded_vector<winrt::hstring,std::allocator<winrt::hstring>>(&v63, &v80);
  std::vector<winrt::hstring>::~vector<winrt::hstring>(&v80);
  v71 = 1;
  v72 = 40;
  v73 = L"{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} 1";
  v70 = &v71;
  winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::Append(
    &v63,
    &v70);
  v71 = 1;
  v72 = 40;
  v73 = L"{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} 5";
  v70 = &v71;
  winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::Append(
    &v63,
    &v70);
  LODWORD(v66) = 1;
  winrt::param::async_iterable<winrt::hstring>::async_iterable<winrt::hstring>(&v74, &v63);
  v14 = -1;
  do
    ++v14;
  while ( v5[v14] );
  if ( (_DWORD)v14 )
  {
    if ( v5[(unsigned int)v14] )
      abort();
    v71 = 1;
    v72 = v14;
    v73 = v5;
    v70 = &v71;
  }
  else
  {
    v70 = 0;
  }
  *(_QWORD *)&v80 = &v70;
  *((_QWORD *)&v80 + 1) = &v74;
  v81 = &v66;
  *(_QWORD *)&rguid.Data1 = &qword_1400969F8;
  _InterlockedAdd64(&qword_1400969F8, 1u);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2> )
  {
    `winrt::Windows::Devices::Enumeration::DeviceInformation::CreateFromIdAsync'::`2'::_lambda_1_::operator()(
      &v80,
      &v67,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>);
    _InterlockedDecrement64(&qword_1400969F8);
  }
  else
  {
    _InterlockedDecrement64(&qword_1400969F8);
    ___call_AEAV_lambda_1___1__CreateFromIdAsync_DeviceInformation_Enumeration_Devices_Windows_winrt__SA_AEBUhstring_param_7_AEBU__async_iterable_Uhstring_winrt___97_AEBW4DeviceInformationKind_4567__Z____factory_cache_entry_UDeviceInformation_Enumeration_Devices_Windows_winrt__UIDeviceInformationStatics2_2345__impl_winrt__QEAA_A_PAEAV_lambda_1___1__CreateFromIdAsync_DeviceInformation_Enumeration_Devices_Windows_2_SA_AEBUhstring_param_2_AEBU__async_iterable_Uhstring_winrt___param_2_AEBW4DeviceInformationKind_6782__Z__Z(
      v14,
      &v67,
      &v80);
  }
  winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Devices::Enumeration::DeviceInformation>,winrt::Windows::Devices::Enumeration::DeviceInformation>::get(
    &v67,
    &v64);
  if ( v67 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v67);
  if ( v75 )
  {
    v15 = v74;
  }
  else
  {
    v15 = 0;
    v74 = 0;
  }
  if ( v15 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v74);
  v16 = winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Properties(
          &v64,
          &v76);
  *((_QWORD *)&v80 + 1) = 0x2800000001LL;
  v82 = L"{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} 1";
  *(_QWORD *)&v80 = (char *)&v80 + 8;
  winrt::impl::consume_Windows_Foundation_Collections_IMapView<winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Windows::Foundation::IInspectable>,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(
    v16,
    &v65,
    &v80);
  if ( v76 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v76);
  v67 = 0;
  if ( (unsigned __int8)winrt::Windows::Foundation::operator==(&v65, &v67) )
  {
    v17 = 51;
LABEL_119:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"avcore\\midi2\\service\\exe\\mididevicepipe.cpp",
      (const char *)0x80070057LL,
      (int)ppv);
    if ( v65 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v65);
    if ( v64 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v64);
    if ( v63 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v63);
    if ( v6 != (CMidiDevicePipe *)-120LL )
      ReleaseSRWLockExclusive((PSRWLOCK)v6 + 15);
    return 2147942487LL;
  }
  v18 = (GUID *)winrt::unbox_value<winrt::guid>(&rguid, &v65);
  v19 = *v18;
  *((GUID *)v6 + 8) = *v18;
  rguid = v19;
  IsComponentPermitted = WindowsMidiServicesInternal::IsComponentPermitted(&rguid, v20);
  if ( IsComponentPermitted < 0 )
  {
    v21 = 56;
LABEL_31:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v21,
      (unsigned int)"avcore\\midi2\\service\\exe\\mididevicepipe.cpp",
      (const char *)(unsigned int)IsComponentPermitted,
      (int)ppv);
LABEL_32:
    if ( v65 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v65);
    if ( v64 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v64);
    if ( v63 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v63);
    goto LABEL_5;
  }
  if ( *((_DWORD *)v69 + 1) == 2 )
  {
    v22 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
    if ( *v22 > 4u )
    {
      v69 = (struct MIDISRV_DEVICECREATION_PARAMS *)v5;
      v67 = L"Creating bidirectional flow";
      v74 = (const wchar_t *)v6;
      *(_QWORD *)&rguid.Data1 = "CMidiDevicePipe::Initialize";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v22,
        (unsigned int)byte_14008B711,
        v23,
        v24,
        (__int64)&rguid,
        (__int64)&v74,
        (__int64)&v67,
        (__int64)&v69);
    }
    v66 = 0;
    v25 = CoCreateInstance((const IID *const)v6 + 8, 0, 0x17u, &GUID_ea264200_3328_49e5_8815_73649a8748be, &v66);
    IsComponentPermitted = v25;
    if ( v25 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4A,
        (unsigned int)"avcore\\midi2\\service\\exe\\mididevicepipe.cpp",
        (const char *)(unsigned int)v25,
        ppva);
      if ( v66 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v66 + 16LL))(v66);
      goto LABEL_32;
    }
    v26 = v66;
    v27 = *(__int64 (__fastcall **)(LPVOID, GUID *, char *))(*(_QWORD *)v66 + 24LL);
    *(_QWORD *)&rguid.Data1 = v27;
    v28 = (_QWORD *)*((_QWORD *)v6 + 18);
    *((_QWORD *)v6 + 18) = 0;
    if ( v28 )
    {
      (*(void (__fastcall **)(_QWORD *, _QWORD))(*v28 + 16LL))(v28, *v28);
      v27 = *(__int64 (__fastcall **)(LPVOID, GUID *, char *))&rguid.Data1;
    }
    v29 = v27(v26, &GUID_b89bbb45_7001_4bea_bbd8_c7cc26e7836c, (char *)v6 + 144);
    IsComponentPermitted = v29;
    if ( v29 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4B,
        (unsigned int)"avcore\\midi2\\service\\exe\\mididevicepipe.cpp",
        (const char *)(unsigned int)v29,
        ppva);
      if ( v66 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v66 + 16LL))(v66);
      goto LABEL_32;
    }
    v30 = *((_QWORD *)v6 + 18);
    rguid = 0;
    LODWORD(ppv) = (_DWORD)v6;
    v31 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int128 *, unsigned int *))(*(_QWORD *)v30 + 24LL))(
            v30,
            v5,
            &v85,
            v68);
    IsComponentPermitted = v31;
    if ( v31 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4C,
        (unsigned int)"avcore\\midi2\\service\\exe\\mididevicepipe.cpp",
        (const char *)(unsigned int)v31,
        (int)v6);
      if ( v66 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v66 + 16LL))(v66);
      goto LABEL_32;
    }
  }
  else if ( *((_DWORD *)v69 + 1) )
  {
    if ( *((_DWORD *)v69 + 1) != 1 )
    {
      v17 = 117;
      goto LABEL_119;
    }
    v42 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
    if ( *v42 > 4u )
    {
      *(_QWORD *)&rguid.Data1 = v5;
      v74 = L"Creating output flow";
      v69 = v6;
      v67 = (const wchar_t *)"CMidiDevicePipe::Initialize";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v42,
        (unsigned int)byte_14008B6BB,
        v43,
        v44,
        (__int64)&v67,
        (__int64)&v69,
        (__int64)&v74,
        (__int64)&rguid);
    }
    v66 = 0;
    v45 = CoCreateInstance((const IID *const)v6 + 8, 0, 0x17u, &GUID_ea264200_3328_49e5_8815_73649a8748be, &v66);
    IsComponentPermitted = v45;
    if ( v45 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6F,
        (unsigned int)"avcore\\midi2\\service\\exe\\mididevicepipe.cpp",
        (const char *)(unsigned int)v45,
        ppvc);
      if ( v66 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v66 + 16LL))(v66);
      goto LABEL_32;
    }
    v46 = v66;
    v47 = *(__int64 (__fastcall **)(LPVOID, GUID *, char *))(*(_QWORD *)v66 + 24LL);
    *(_QWORD *)&rguid.Data1 = v47;
    v48 = (_QWORD *)*((_QWORD *)v6 + 20);
    *((_QWORD *)v6 + 20) = 0;
    if ( v48 )
    {
      (*(void (__fastcall **)(_QWORD *, _QWORD))(*v48 + 16LL))(v48, *v48);
      v47 = *(__int64 (__fastcall **)(LPVOID, GUID *, char *))&rguid.Data1;
    }
    v49 = v47(v46, &GUID_f328d645_7d6d_4924_a7e3_9dee245189f9, (char *)v6 + 160);
    IsComponentPermitted = v49;
    if ( v49 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x70,
        (unsigned int)"avcore\\midi2\\service\\exe\\mididevicepipe.cpp",
        (const char *)(unsigned int)v49,
        ppvc);
      if ( v66 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v66 + 16LL))(v66);
      goto LABEL_32;
    }
    v50 = *((_QWORD *)v6 + 20);
    rguid = 0;
    ppv = &rguid;
    v51 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int128 *, unsigned int *))(*(_QWORD *)v50 + 24LL))(
            v50,
            v5,
            &v85,
            v68);
    IsComponentPermitted = v51;
    if ( v51 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x71,
        (unsigned int)"avcore\\midi2\\service\\exe\\mididevicepipe.cpp",
        (const char *)(unsigned int)v51,
        (int)&rguid);
      if ( v66 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v66 + 16LL))(v66);
      goto LABEL_32;
    }
  }
  else
  {
    v32 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
    if ( *v32 > 4u )
    {
      *(_QWORD *)&rguid.Data1 = v5;
      v74 = L"Creating input flow";
      v69 = v6;
      v67 = (const wchar_t *)"CMidiDevicePipe::Initialize";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v32,
        (unsigned int)byte_14008B555,
        v33,
        v34,
        (__int64)&v67,
        (__int64)&v69,
        (__int64)&v74,
        (__int64)&rguid);
    }
    v66 = 0;
    v35 = CoCreateInstance((const IID *const)v6 + 8, 0, 0x17u, &GUID_ea264200_3328_49e5_8815_73649a8748be, &v66);
    IsComponentPermitted = v35;
    if ( v35 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5D,
        (unsigned int)"avcore\\midi2\\service\\exe\\mididevicepipe.cpp",
        (const char *)(unsigned int)v35,
        ppvb);
      if ( v66 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v66 + 16LL))(v66);
      goto LABEL_32;
    }
    v36 = v66;
    v37 = *(__int64 (__fastcall **)(LPVOID, GUID *, char *))(*(_QWORD *)v66 + 24LL);
    *(_QWORD *)&rguid.Data1 = v37;
    v38 = (_QWORD *)*((_QWORD *)v6 + 19);
    *((_QWORD *)v6 + 19) = 0;
    if ( v38 )
    {
      (*(void (__fastcall **)(_QWORD *, _QWORD))(*v38 + 16LL))(v38, *v38);
      v37 = *(__int64 (__fastcall **)(LPVOID, GUID *, char *))&rguid.Data1;
    }
    v39 = v37(v36, &GUID_6c4b8bf9_8133_4b41_8303_1fde78e20aca, (char *)v6 + 152);
    IsComponentPermitted = v39;
    if ( v39 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5E,
        (unsigned int)"avcore\\midi2\\service\\exe\\mididevicepipe.cpp",
        (const char *)(unsigned int)v39,
        ppvb);
      if ( v66 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v66 + 16LL))(v66);
      goto LABEL_32;
    }
    v40 = *((_QWORD *)v6 + 19);
    rguid = 0;
    LODWORD(ppv) = (_DWORD)v6;
    v41 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int128 *, unsigned int *))(*(_QWORD *)v40 + 24LL))(
            v40,
            v5,
            &v85,
            v68);
    IsComponentPermitted = v41;
    if ( v41 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5F,
        (unsigned int)"avcore\\midi2\\service\\exe\\mididevicepipe.cpp",
        (const char *)(unsigned int)v41,
        (int)v6);
      if ( v66 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v66 + 16LL))(v66);
      goto LABEL_32;
    }
  }
  if ( v66 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v66 + 16LL))(v66);
  if ( (*((_DWORD *)v6 + 14) & 0xFFFFFFFD) == 0 )
  {
    IsComponentPermitted = (*(__int64 (__fastcall **)(CMidiDevicePipe *, _QWORD))(*(_QWORD *)v6 + 80LL))(
                             v6,
                             DWORD1(v85));
    if ( IsComponentPermitted < 0 )
    {
      v21 = 125;
      goto LABEL_31;
    }
  }
  if ( (unsigned int)(*((_DWORD *)v6 + 14) - 1) <= 1 )
  {
    IsComponentPermitted = (*(__int64 (__fastcall **)(CMidiDevicePipe *, _QWORD))(*(_QWORD *)v6 + 88LL))(
                             v6,
                             DWORD1(v85));
    if ( IsComponentPermitted < 0 )
    {
      v21 = 130;
      goto LABEL_31;
    }
  }
  try
  {
    *((_BYTE *)v6 + 168) = 1;
    v52 = winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Properties(
            &v64,
            &v68);
    v71 = 1;
    v72 = 40;
    v73 = L"{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} 5";
    v70 = &v71;
    HasKey = winrt::impl::consume_Windows_Foundation_Collections_IMapView<winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Windows::Foundation::IInspectable>,winrt::hstring,winrt::Windows::Foundation::IInspectable>::HasKey(
               v52,
               &v70);
    if ( v68 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v68);
    if ( HasKey )
    {
      v55 = winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Properties(
              &v64,
              &v68);
      v71 = 1;
      v72 = 40;
      v73 = L"{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} 5";
      v70 = &v71;
      winrt::impl::consume_Windows_Foundation_Collections_IMapView<winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Windows::Foundation::IInspectable>,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(
        v55,
        &v67,
        &v70);
      if ( v68 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v68);
      *(_QWORD *)&rguid.Data1 = 0;
      if ( !(unsigned __int8)winrt::Windows::Foundation::operator==(&v67, &rguid) )
        *((_BYTE *)v6 + 168) = winrt::unbox_value<bool>(&v67);
      if ( v67 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v67);
    }
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x9C,
      (unsigned int)"avcore\\midi2\\service\\exe\\mididevicepipe.cpp",
      v53);
    v6 = v77;
    v5 = v78;
    v10 = v79;
  }
  v56 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v56 > 4u )
  {
    v79 = (RTL_SRWLOCK *)v5;
    v78 = L"Exit Success";
    v77 = v6;
    *(_QWORD *)&rguid.Data1 = "CMidiDevicePipe::Initialize";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (_DWORD)v56,
      (unsigned int)byte_14008B633,
      v57,
      v58,
      (__int64)&rguid,
      (__int64)&v77,
      (__int64)&v78,
      (__int64)&v79);
  }
  if ( v65 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v65);
  if ( v64 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v64);
  if ( v63 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v63);
  if ( v10 )
    ReleaseSRWLockExclusive(v10);
  return 0;
}

```

## disassembly

```asm
0x14003fd34  mov     rax, rsp
0x14003fd37  push    rbx
0x14003fd38  push    rsi
0x14003fd39  push    rdi
0x14003fd3a  push    r12
0x14003fd3c  push    r13
0x14003fd3e  push    r14
0x14003fd40  push    r15
0x14003fd42  sub     rsp, 130h
0x14003fd49  movaps  xmmword ptr [rax-48h], xmm6
0x14003fd4d  mov     rax, cs:__security_cookie
0x14003fd54  xor     rax, rsp
0x14003fd57  mov     [rsp+168h+var_50], rax
0x14003fd5f  mov     [rsp+168h+var_100], r9
0x14003fd64  mov     r12, r8
0x14003fd67  mov     [rsp+168h+var_F8], r8
0x14003fd6c  mov     r14, rdx
0x14003fd6f  mov     rsi, rcx
0x14003fd72  mov     [rsp+168h+var_B8], rcx
0x14003fd7a  mov     [rsp+168h+var_B0], rdx
0x14003fd82  xor     ebx, ebx
0x14003fd84  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14003fd89  mov     rcx, [rax+8]
0x14003fd8d  mov     eax, [rcx]
0x14003fd8f  cmp     eax, 4
0x14003fd92  jbe     short loc_14003FDF2
0x14003fd94  mov     [rsp+168h+var_C0], r14
0x14003fd9c  lea     rax, aEnter; "Enter"
0x14003fda3  mov     [rsp+168h+var_108], rax
0x14003fda8  mov     [rsp+168h+var_128], rsi
0x14003fdad  lea     r13, aCmididevicepip_0; "CMidiDevicePipe::Initialize"
0x14003fdb4  mov     [rsp+168h+var_110], r13
0x14003fdb9  lea     rax, [rsp+168h+var_C0]
0x14003fdc1  mov     [rsp+168h+var_130], rax
0x14003fdc6  lea     rax, [rsp+168h+var_108]
0x14003fdcb  mov     [rsp+168h+var_138], rax
0x14003fdd0  lea     rax, [rsp+168h+var_128]
0x14003fdd5  mov     [rsp+168h+var_140], rax
0x14003fdda  lea     rax, [rsp+168h+var_110]
0x14003fddf  mov     [rsp+168h+ppv], rax
0x14003fde4  lea     rdx, byte_14008B5DD
0x14003fdeb  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x14003fdf0  jmp     short loc_14003FDF9
0x14003fdf2  lea     r13, aCmididevicepip_0; "CMidiDevicePipe::Initialize"
0x14003fdf9  lea     rdi, [rsi+78h]
0x14003fdfd  mov     [rsp+168h+var_A8], rdi
0x14003fe05  mov     rcx, rdi; SRWLock
0x14003fe08  call    cs:__imp_AcquireSRWLockExclusive
0x14003fe0e  mov     [rsp+168h+var_80], rdi
0x14003fe16  xorps   xmm0, xmm0
0x14003fe19  xor     eax, eax
0x14003fe1b  movups  [rsp+168h+var_68], xmm0
0x14003fe23  mov     [rsp+168h+var_58], rax
0x14003fe2b  mov     r8d, [r12+4]
0x14003fe30  mov     rdx, r14
0x14003fe33  mov     rcx, rsi
0x14003fe36  call    ?Initialize@CMidiPipe@@UEAAJPEBGW4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0002@@@Z; CMidiPipe::Initialize(ushort const *,__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0002)
0x14003fe3b  mov     r15d, eax
0x14003fe3e  test    eax, eax
0x14003fe40  jns     short loc_14003FE75
0x14003fe42  mov     rcx, [rsp+168h]; this
0x14003fe4a  mov     r9d, eax; char *
0x14003fe4d  lea     r8, aAvcoreMidi2Ser_11; "avcore\\midi2\\service\\exe\\mididevice"...
0x14003fe54  mov     edx, 23h ; '#'; void *
0x14003fe59  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003fe5e  nop
0x14003fe5f  test    rdi, rdi
0x14003fe62  jz      short loc_14003FE6D
0x14003fe64  mov     rcx, rdi; SRWLock
0x14003fe67  call    cs:__imp_ReleaseSRWLockExclusive
0x14003fe6d  mov     eax, r15d
0x14003fe70  jmp     loc_140040A77
0x14003fe75  mov     dword ptr [rsp+168h+var_68], ebx
0x14003fe7c  mov     eax, [r12]
0x14003fe80  mov     dword ptr [rsp+168h+var_68+4], eax
0x14003fe87  mov     dword ptr [rsp+168h+var_68+8], 6B467626h
0x14003fe92  mov     dword ptr [rsp+168h+var_68+0Ch], 4197D814h
0x14003fe9d  mov     dword ptr [rsp+168h+var_58], 7128F595h
0x14003fea8  mov     dword ptr [rsp+168h+var_58+4], 0A5FB01B6h
0x14003feb3  mov     r15d, 1
0x14003feb9  xorps   xmm0, xmm0
0x14003febc  movdqu  [rsp+168h+var_A0], xmm0
0x14003fec5  mov     [rsp+168h+var_90], rbx
0x14003fecd  lea     rdx, [rsp+168h+var_A0]
0x14003fed5  lea     rcx, [rsp+168h+var_128]
0x14003feda  call    ??$single_threaded_vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@winrt@@YA?AU?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@0@$$QEAV?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@@Z; winrt::single_threaded_vector<winrt::hstring,std::allocator<winrt::hstring>>(std::vector<winrt::hstring> &&)
0x14003fedf  nop
0x14003fee0  lea     rcx, [rsp+168h+var_A0]
0x14003fee8  call    ??1?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@QEAA@XZ; std::vector<winrt::hstring>::~vector<winrt::hstring>(void)
0x14003feed  mov     [rsp+168h+var_E8], r15d
0x14003fef5  mov     [rsp+168h+var_E4], 28h ; '('
0x14003ff00  lea     r12, a3f114a6a11fa4b_15; "{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} "...
0x14003ff07  mov     [rsp+168h+var_D8], r12
0x14003ff0f  lea     rax, [rsp+168h+var_E8]
0x14003ff17  mov     [rsp+168h+var_F0], rax
0x14003ff1c  lea     rdx, [rsp+168h+var_F0]
0x14003ff21  lea     rcx, [rsp+168h+var_128]
0x14003ff26  call    ?Append@?$consume_Windows_Foundation_Collections_IVector@U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@winrt@@Uhstring@5@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::Append(winrt::param::hstring const &)
0x14003ff2b  mov     [rsp+168h+var_E8], r15d
0x14003ff33  mov     [rsp+168h+var_E4], 28h ; '('
0x14003ff3e  lea     rax, a3f114a6a11fa4b_5; "{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} "...
0x14003ff45  mov     [rsp+168h+var_D8], rax
0x14003ff4d  lea     rax, [rsp+168h+var_E8]
0x14003ff55  mov     [rsp+168h+var_F0], rax
0x14003ff5a  lea     rdx, [rsp+168h+var_F0]
0x14003ff5f  lea     rcx, [rsp+168h+var_128]
0x14003ff64  call    ?Append@?$consume_Windows_Foundation_Collections_IVector@U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@winrt@@Uhstring@5@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::Append(winrt::param::hstring const &)
0x14003ff69  mov     dword ptr [rsp+168h+var_110], r15d
0x14003ff6e  lea     rdx, [rsp+168h+var_128]
0x14003ff73  lea     rcx, [rsp+168h+var_D0]
0x14003ff7b  call    ??$?0U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@winrt@@$0A@@?$async_iterable@Uhstring@winrt@@@param@winrt@@QEAA@AEBU?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@2@@Z; winrt::param::async_iterable<winrt::hstring>::async_iterable<winrt::hstring>(winrt::Windows::Foundation::Collections::IVector<winrt::hstring> const &)
0x14003ff80  nop
0x14003ff81  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14003ff85  inc     rcx
0x14003ff88  cmp     [r14+rcx*2], bx
0x14003ff8d  jnz     short loc_14003FF85
0x14003ff8f  test    ecx, ecx
0x14003ff91  jnz     short loc_14003FF9A
0x14003ff93  mov     [rsp+168h+var_F0], rbx
0x14003ff98  jmp     short loc_14003FFCE
0x14003ff9a  mov     eax, ecx
0x14003ff9c  cmp     [r14+rax*2], bx
0x14003ffa1  jz      short loc_14003FFAA
0x14003ffa3  call    cs:__imp_abort
0x14003ffaa  mov     [rsp+168h+var_E8], r15d
0x14003ffb2  mov     [rsp+168h+var_E4], ecx
0x14003ffb9  mov     [rsp+168h+var_D8], r14
0x14003ffc1  lea     rax, [rsp+168h+var_E8]
0x14003ffc9  mov     [rsp+168h+var_F0], rax
0x14003ffce  lea     rax, [rsp+168h+var_F0]
0x14003ffd3  mov     qword ptr [rsp+168h+var_A0], rax
0x14003ffdb  lea     rax, [rsp+168h+var_D0]
0x14003ffe3  mov     qword ptr [rsp+168h+var_A0+8], rax
0x14003ffeb  lea     rax, [rsp+168h+var_110]
0x14003fff0  mov     [rsp+168h+var_90], rax
0x14003fff8  lea     rax, qword_1400969F8
0x14003ffff  mov     qword ptr [rsp+168h+rguid.Data1], rax
0x140040007  lock add cs:qword_1400969F8, r15
0x14004000f  cmp     cs:??$factory_cache_entry_v@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@impl@winrt@@3U?$factory_cache_entry@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@12@A, rbx; factory_cache_entry<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>::winrt::factory_cache_entry<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2> winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>
0x140040016  jz      short loc_14004003C
0x140040018  lea     r8, ??$factory_cache_entry_v@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@impl@winrt@@3U?$factory_cache_entry@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@12@A; factory_cache_entry<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>::winrt::factory_cache_entry<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2> winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>
0x14004001f  lea     rdx, [rsp+168h+var_108]
0x140040024  lea     rcx, [rsp+168h+var_A0]
0x14004002c  call    ??R_lambda_1_@?1??CreateFromIdAsync@DeviceInformation@Enumeration@Devices@Windows@winrt@@SA@AEBUhstring@param@6@AEBU?$async_iterable@Uhstring@winrt@@@86@AEBW4DeviceInformationKind@3456@@Z@QEBA@AEBUIDeviceInformationStatics2@3456@@Z; `winrt::Windows::Devices::Enumeration::DeviceInformation::CreateFromIdAsync(winrt::param::hstring const &,winrt::param::async_iterable<winrt::hstring> const &,winrt::Windows::Devices::Enumeration::DeviceInformationKind const &)'::`2'::_lambda_1_::operator()(winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2 const &)
0x140040031  nop
0x140040032  lock dec cs:qword_1400969F8
0x14004003a  jmp     short loc_140040057
0x14004003c  lock dec cs:qword_1400969F8
0x140040044  lea     r8, [rsp+168h+var_A0]
0x14004004c  lea     rdx, [rsp+168h+var_108]
0x140040051  call    ??$call@AEAV_lambda_1_@?1??CreateFromIdAsync@DeviceInformation@Enumeration@Devices@Windows@winrt@@SA@AEBUhstring@param@7@AEBU?$async_iterable@Uhstring@winrt@@@97@AEBW4DeviceInformationKind@4567@@Z@@?$factory_cache_entry@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateFromIdAsync@DeviceInformation@Enumeration@Devices@Windows@2@SA@AEBUhstring@param@2@AEBU?$async_iterable@Uhstring@winrt@@@param@2@AEBW4DeviceInformationKind@6782@@Z@@Z
0x140040056  nop
0x140040057  lea     rdx, [rsp+168h+var_120]
0x14004005c  lea     rcx, [rsp+168h+var_108]
0x140040061  call    ?get@?$consume_Windows_Foundation_IAsyncOperation@U?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@UDeviceInformation@Enumeration@Devices@34@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Devices::Enumeration::DeviceInformation>,winrt::Windows::Devices::Enumeration::DeviceInformation>::get(void)
0x140040066  nop
0x140040067  cmp     [rsp+168h+var_108], rbx
0x14004006c  jz      short loc_140040079
0x14004006e  lea     rcx, [rsp+168h+var_108]
0x140040073  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x140040078  nop
0x140040079  cmp     [rsp+168h+var_C8], bl
0x140040080  jnz     short loc_14004008F
0x140040082  mov     rax, rbx
0x140040085  mov     [rsp+168h+var_D0], rbx
0x14004008d  jmp     short loc_140040097
0x14004008f  mov     rax, [rsp+168h+var_D0]
0x140040097  test    rax, rax
0x14004009a  jz      short loc_1400400A9
0x14004009c  lea     rcx, [rsp+168h+var_D0]
0x1400400a4  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1400400a9  lea     rdx, [rsp+168h+var_C0]
0x1400400b1  lea     rcx, [rsp+168h+var_120]
0x1400400b6  call    ?Properties@?$consume_Windows_Devices_Enumeration_IDeviceInformation@UIDeviceInformation@Enumeration@Devices@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Properties(void)
0x1400400bb  nop
0x1400400bc  mov     dword ptr [rsp+168h+var_A0+8], r15d
0x1400400c4  mov     dword ptr [rsp+168h+var_A0+0Ch], 28h ; '('
0x1400400cf  mov     [rsp+168h+var_88], r12
0x1400400d7  lea     rcx, [rsp+168h+var_A0+8]
0x1400400df  mov     qword ptr [rsp+168h+var_A0], rcx
0x1400400e7  lea     r8, [rsp+168h+var_A0]
0x1400400ef  lea     rdx, [rsp+168h+var_118]
0x1400400f4  mov     rcx, rax
0x1400400f7  call    ?Lookup@?$consume_Windows_Foundation_Collections_IMapView@U?$IMapView@Uhstring@winrt@@UIInspectable@Foundation@Windows@2@@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMapView<winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Windows::Foundation::IInspectable>,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(winrt::param::hstring const &)
0x1400400fc  nop
0x1400400fd  cmp     [rsp+168h+var_C0], rbx
0x140040105  jz      short loc_140040114
0x140040107  lea     rcx, [rsp+168h+var_C0]
0x14004010f  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x140040114  mov     [rsp+168h+var_108], rbx
0x140040119  lea     rdx, [rsp+168h+var_108]
0x14004011e  lea     rcx, [rsp+168h+var_118]
0x140040123  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x140040128  test    al, al
0x14004012a  jz      short loc_140040136
0x14004012c  mov     edx, 33h ; '3'
0x140040131  jmp     loc_140040A13
0x140040136  lea     r12, [rsi+80h]
0x14004013d  lea     rdx, [rsp+168h+var_118]
0x140040142  lea     rcx, [rsp+168h+rguid]
0x14004014a  call    ??$unbox_value@Uguid@winrt@@@winrt@@YA?AUguid@0@AEBUIInspectable@Foundation@Windows@0@@Z; winrt::unbox_value<winrt::guid>(winrt::Windows::Foundation::IInspectable const &)
0x14004014f  movups  xmm0, xmmword ptr [rax]
0x140040152  movdqu  xmmword ptr [r12], xmm0
0x140040158  movdqu  xmmword ptr [rsp+168h+rguid.Data1], xmm0
0x140040161  lea     rcx, [rsp+168h+rguid]; rguid
0x140040169  call    ?IsComponentPermitted@WindowsMidiServicesInternal@@YAJU_GUID@@@Z; WindowsMidiServicesInternal::IsComponentPermitted(_GUID)
0x14004016e  mov     r15d, eax
0x140040171  test    eax, eax
0x140040173  jns     short loc_1400401D0
0x140040175  mov     edx, 38h ; '8'; void *
0x14004017a  lea     r8, aAvcoreMidi2Ser_11; "avcore\\midi2\\service\\exe\\mididevice"...
0x140040181  mov     r9d, r15d; char *
0x140040184  mov     rcx, [rsp+168h]; this
0x14004018c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140040191  nop
0x140040192  cmp     [rsp+168h+var_118], rbx
0x140040197  jz      short loc_1400401A4
0x140040199  lea     rcx, [rsp+168h+var_118]
0x14004019e  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1400401a3  nop
0x1400401a4  cmp     [rsp+168h+var_120], rbx
0x1400401a9  jz      short loc_1400401B6
0x1400401ab  lea     rcx, [rsp+168h+var_120]
0x1400401b0  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1400401b5  nop
0x1400401b6  cmp     [rsp+168h+var_128], rbx
0x1400401bb  jz      loc_14003FE5F
0x1400401c1  lea     rcx, [rsp+168h+var_128]
0x1400401c6  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1400401cb  jmp     loc_14003FE5F
0x1400401d0  xorps   xmm6, xmm6
0x1400401d3  mov     rax, [rsp+168h+var_F8]
0x1400401d8  cmp     dword ptr [rax+4], 2
0x1400401dc  jnz     loc_1400403CA
0x1400401e2  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x1400401e7  mov     rcx, [rax+8]
0x1400401eb  mov     eax, [rcx]
0x1400401ed  cmp     eax, 4
0x1400401f0  jbe     short loc_14004024E
0x1400401f2  mov     [rsp+168h+var_F8], r14
0x1400401f7  lea     rax, aCreatingBidire; "Creating bidirectional flow"
0x1400401fe  mov     [rsp+168h+var_108], rax
0x140040203  mov     [rsp+168h+var_D0], rsi
0x14004020b  mov     qword ptr [rsp+168h+rguid.Data1], r13
0x140040213  lea     rax, [rsp+168h+var_F8]
0x140040218  mov     [rsp+168h+var_130], rax
0x14004021d  lea     rax, [rsp+168h+var_108]
0x140040222  mov     [rsp+168h+var_138], rax
0x140040227  lea     rax, [rsp+168h+var_D0]
0x14004022f  mov     [rsp+168h+var_140], rax
0x140040234  lea     rax, [rsp+168h+rguid]
0x14004023c  mov     [rsp+168h+ppv], rax
0x140040241  lea     rdx, byte_14008B711
0x140040248  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x14004024d  nop
0x14004024e  mov     [rsp+168h+var_110], rbx
0x140040253  lea     rax, [rsp+168h+var_110]
0x140040258  mov     [rsp+168h+ppv], rax; int
0x14004025d  lea     r9, _GUID_ea264200_3328_49e5_8815_73649a8748be; riid
0x140040264  xor     edx, edx; pUnkOuter
0x140040266  lea     r8d, [rdx+17h]; dwClsContext
0x14004026a  mov     rcx, r12; rclsid
0x14004026d  call    cs:__imp_CoCreateInstance
0x140040273  mov     r15d, eax
0x140040276  test    eax, eax
0x140040278  jns     short loc_1400402B3
0x14004027a  mov     rcx, [rsp+168h]; this
0x140040282  mov     r9d, eax; char *
0x140040285  lea     r8, aAvcoreMidi2Ser_11; "avcore\\midi2\\service\\exe\\mididevice"...
0x14004028c  mov     edx, 4Ah ; 'J'; void *
0x140040291  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140040296  nop
0x140040297  mov     rcx, [rsp+168h+var_110]
0x14004029c  test    rcx, rcx
0x14004029f  jz      short loc_1400402AE
0x1400402a1  mov     rax, [rcx]
0x1400402a4  mov     rax, [rax+10h]
0x1400402a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400402ad  nop
0x1400402ae  jmp     loc_140040192
0x1400402b3  mov     r15, [rsp+168h+var_110]
0x1400402b8  mov     rax, [r15]
0x1400402bb  mov     rax, [rax+18h]
0x1400402bf  mov     qword ptr [rsp+168h+rguid.Data1], rax
0x1400402c7  lea     r12, [rsi+90h]
0x1400402ce  mov     rcx, [r12]
0x1400402d2  mov     [r12], rbx
0x1400402d6  test    rcx, rcx
0x1400402d9  jz      short loc_1400402EF
0x1400402db  mov     rdx, [rcx]
0x1400402de  mov     rax, [rdx+10h]
0x1400402e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400402e7  mov     rax, qword ptr [rsp+168h+rguid.Data1]
0x1400402ef  mov     r8, r12
0x1400402f2  lea     rdx, _GUID_b89bbb45_7001_4bea_bbd8_c7cc26e7836c
0x1400402f9  mov     rcx, r15
0x1400402fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140040301  mov     r15d, eax
0x140040304  test    eax, eax
0x140040306  jns     short loc_140040341
  ... truncated ...
```
