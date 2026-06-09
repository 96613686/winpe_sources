# CMidiClientManager::CreateMidiClient(ushort const *,_GUID,ulong,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &,MIDISRV_CLIENTCREATION_PARAMS *,MIDISRV_CLIENT *,int)

- ea: `0x1400152d0`
- end: `0x14001647e`
- name: `?CreateMidiClient@CMidiClientManager@@QEAAJPEBGU_GUID@@KAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@PEAUMIDISRV_CLIENTCREATION_PARAMS@@PEAUMIDISRV_CLIENT@@H@Z`
- size: `4526`
- prototype: `__int64 __fastcall(PSRWLOCK SRWLock, const wchar_t *, _OWORD *, unsigned int, __int64, __int64, void *)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14003d0b0`

## callees

- `0x14000204c`
- `0x1400054c0`
- `0x1400060f8`
- `0x140007c20`
- `0x14000984c`
- `0x14000a6b4`
- `0x140013a38`
- `0x14001470c`
- `0x1400152d0`
- `0x140017838`
- `0x140017f94`
- `0x140018770`
- `0x140018f54`
- `0x1400193c4`
- `0x140019aac`
- `0x14001a084`
- `0x14001a680`
- `0x1400465a4`
- `0x14005a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400154bd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400154bd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140015582`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140015617`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400156b9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140015795`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140015854`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400159cf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140015aee`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140015bb1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140015cce`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140015db1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140015f2d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140016089`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400161a7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14001626a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14001635a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400163d5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140015582`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140015617`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400156b9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140015795`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140015854`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400159cf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140015aee`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140015bb1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140015cce`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140015db1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140015f2d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140016089`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400161a7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14001626a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14001635a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400163d5`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x14001554a`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x1400155df`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x140015681`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x14001575d`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x140015805`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x140015982`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x140015aa1`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x140015b64`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x140015c86`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x140015d62`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x140015ee0`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x14001603a`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x14001615a`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x14001621d`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x14001630d`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x140016388`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x14001554a`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x1400155df`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x140015681`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x14001575d`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x140015805`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x140015982`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x140015aa1`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x140015b64`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x140015c86`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x140015d62`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x140015ee0`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x14001603a`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x14001615a`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x14001621d`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x14001630d`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x140016388`

## string_xrefs

- `0x14001533c`: `avcore\midi2\service\exe\midiclientmanager.cpp`
- `0x140015524`: `avcore\midi2\service\exe\midiclientmanager.cpp`
- `0x1400155b9`: `avcore\midi2\service\exe\midiclientmanager.cpp`
- `0x14001565b`: `avcore\midi2\service\exe\midiclientmanager.cpp`
- `0x140015737`: `avcore\midi2\service\exe\midiclientmanager.cpp`
- `0x1400157df`: `avcore\midi2\service\exe\midiclientmanager.cpp`
- `0x140015945`: `avcore\midi2\service\exe\midiclientmanager.cpp`
- `0x140015a7b`: `avcore\midi2\service\exe\midiclientmanager.cpp`
- `0x140015b3e`: `avcore\midi2\service\exe\midiclientmanager.cpp`
- `0x140015c60`: `avcore\midi2\service\exe\midiclientmanager.cpp`
- `0x140015d25`: `avcore\midi2\service\exe\midiclientmanager.cpp`
- `0x140015ea3`: `avcore\midi2\service\exe\midiclientmanager.cpp`
- `0x140015ffd`: `avcore\midi2\service\exe\midiclientmanager.cpp`
- `0x140016134`: `avcore\midi2\service\exe\midiclientmanager.cpp`
- `0x1400161f7`: `avcore\midi2\service\exe\midiclientmanager.cpp`
- `0x1400162e7`: `avcore\midi2\service\exe\midiclientmanager.cpp`
- `0x14001542b`: `Session is invalid for this client process. Cannot create MIDI client.`
- `0x140015369`: `CMidiClientManager::CreateMidiClient`
- `0x14001543c`: `CMidiClientManager::CreateMidiClient`
- `0x140016409`: `CMidiClientManager::CreateMidiClient`
- `0x1400163f8`: `Complete.`

## pseudocode

```c
__int64 __fastcall CMidiClientManager::CreateMidiClient(
        PSRWLOCK SRWLock,
        const wchar_t *a2,
        _OWORD *a3,
        unsigned int a4,
        __int64 a5,
        __int64 a6,
        void *a7)
{
  __int64 v11; // rdx
  unsigned int v12; // ebx
  _DWORD *v14; // rcx
  int v15; // r8d
  int v16; // r9d
  PVOID Ptr; // rcx
  _DWORD *v18; // r8
  int v19; // r9d
  int v20; // eax
  int EndpointAlias; // eax
  void *v22; // rax
  int IncomingTimestamp; // eax
  __int128 *v24; // rdx
  unsigned int v25; // r14d
  int MidiClient; // eax
  __int128 *v27; // rdx
  int MidiDevice; // eax
  unsigned int *v29; // rbx
  int *v30; // rsi
  unsigned int *v31; // rdx
  int MidiTransform; // eax
  unsigned int v33; // esi
  int *v34; // rcx
  int *v35; // rsi
  int v36; // eax
  int v37; // eax
  int *v38; // rcx
  int *v39; // rsi
  int EndpointRequiresOutboundProtocolDownscaling; // eax
  int v41; // edx
  int MidiProtocolDownscalerTransform; // eax
  int *v43; // rbx
  int *v44; // rsi
  int v45; // eax
  int *v46; // rcx
  int *v47; // rsi
  int v48; // edx
  int MidiScheduler; // eax
  int *v50; // rbx
  int *v51; // rsi
  int v52; // eax
  int v53; // eax
  int *v54; // rcx
  PVOID v55; // rcx
  int v56; // eax
  _DWORD *v57; // rcx
  int v58; // r8d
  int v59; // r9d
  int v60; // [rsp+20h] [rbp-E0h]
  int v61; // [rsp+20h] [rbp-E0h]
  int v62[2]; // [rsp+20h] [rbp-E0h]
  int *v63; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int8 v64[8]; // [rsp+58h] [rbp-A8h] BYREF
  int *v65; // [rsp+60h] [rbp-A0h] BYREF
  int v66[2]; // [rsp+68h] [rbp-98h] BYREF
  HANDLE AvrtHandle; // [rsp+70h] [rbp-90h] BYREF
  const wchar_t *v68; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v69[2]; // [rsp+80h] [rbp-80h] BYREF
  char v70; // [rsp+90h] [rbp-70h]
  void *v71; // [rsp+98h] [rbp-68h] BYREF
  __int128 v72; // [rsp+A0h] [rbp-60h] BYREF
  int v73[4]; // [rsp+B0h] [rbp-50h] BYREF
  _OWORD v74[2]; // [rsp+C0h] [rbp-40h] BYREF
  char v75[32]; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v76; // [rsp+100h] [rbp+0h] BYREF
  __m128i si128; // [rsp+110h] [rbp+10h]
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]

  v66[0] = a4;
  v71 = a7;
  if ( *(_DWORD *)(a6 + 8) > 2u )
  {
    v11 = 985;
LABEL_3:
    v12 = -2147024809;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"avcore\\midi2\\service\\exe\\midiclientmanager.cpp",
      (const char *)v12,
      v60);
    return v12;
  }
  if ( (*(_DWORD *)a6 & 0xFFFFFFF8) != 0 )
  {
    v11 = 987;
    goto LABEL_3;
  }
  v14 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v14 > 4u )
  {
    v68 = a2;
    LODWORD(v63) = a4;
    AvrtHandle = a3;
    v65 = (int *)L"Enter";
    *(_QWORD *)&v72 = SRWLock;
    *(_QWORD *)v73 = "CMidiClientManager::CreateMidiClient";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
      (_DWORD)v14,
      (unsigned int)byte_140087FE9,
      v15,
      v16,
      (__int64)v73,
      (__int64)&v72,
      (__int64)&v65,
      (__int64)&AvrtHandle,
      (__int64)&v63,
      (__int64)&v68);
  }
  Ptr = SRWLock[7].Ptr;
  *(_OWORD *)v73 = *a3;
  v12 = (*(__int64 (__fastcall **)(PVOID, int *, _QWORD))(*(_QWORD *)Ptr + 8LL))(Ptr, v73, a4);
  if ( (v12 & 0x80000000) != 0 )
  {
    v18 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
    if ( *v18 > 2u )
    {
      *(_QWORD *)v73 = a2;
      LODWORD(v63) = v66[0];
      *(_QWORD *)&v72 = a3;
      v68 = L"Session is invalid for this client process. Cannot create MIDI client.";
      AvrtHandle = SRWLock;
      v65 = (int *)"CMidiClientManager::CreateMidiClient";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v18,
        (unsigned int)byte_1400872E3,
        (_DWORD)v18,
        v19,
        (__int64)&v65,
        (__int64)&AvrtHandle,
        (__int64)&v68,
        (__int64)&v72,
        (__int64)&v63,
        (__int64)v73);
    }
    v11 = 1016;
    goto LABEL_4;
  }
  memset_0(v71, 0, 0x58u);
  v69[0] = &v71;
  v69[1] = SRWLock;
  v70 = 1;
  AcquireSRWLockExclusive(SRWLock);
  *(_QWORD *)v73 = SRWLock;
  v65 = 0;
  v68 = 0;
  v63 = 0;
  AvrtHandle = 0;
  v76 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v76) = 0;
  v64[0] = 1;
  v74[0] = *(_OWORD *)a6;
  v74[1] = *(_OWORD *)(a6 + 16);
  v20 = EnableMmcss(&AvrtHandle, &SRWLock[15]);
  v12 = v20;
  if ( v20 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x454,
      (unsigned int)"avcore\\midi2\\service\\exe\\midiclientmanager.cpp",
      (const char *)(unsigned int)v20,
      v60);
    std::wstring::~wstring(&v76);
    if ( AvrtHandle )
      AvRevertMmThreadCharacteristics(AvrtHandle);
    if ( v63 )
      (*(void (__fastcall **)(int *))(*(_QWORD *)v63 + 16LL))(v63);
    if ( v65 )
      (*(void (__fastcall **)(int *))(*(_QWORD *)v65 + 16LL))(v65);
LABEL_170:
    ReleaseSRWLockExclusive(SRWLock);
    v70 = 0;
    CMidiClientManager::CreateMidiClient_::_2_::_lambda_1_::operator()(v69);
    return v12;
  }
  EndpointAlias = GetEndpointAlias(a2, &v76, (char *)v74 + 8);
  v12 = EndpointAlias;
  if ( EndpointAlias < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x459,
      (unsigned int)"avcore\\midi2\\service\\exe\\midiclientmanager.cpp",
      (const char *)(unsigned int)EndpointAlias,
      v60);
    std::wstring::~wstring(&v76);
    if ( AvrtHandle )
      AvRevertMmThreadCharacteristics(AvrtHandle);
    if ( v63 )
      (*(void (__fastcall **)(int *))(*(_QWORD *)v63 + 16LL))(v63);
    if ( v65 )
      (*(void (__fastcall **)(int *))(*(_QWORD *)v65 + 16LL))(v65);
    goto LABEL_170;
  }
  v22 = (void *)std::wstring::wstring(v75, &v76);
  IncomingTimestamp = GetEndpointGenerateIncomingTimestamp(v22);
  v12 = IncomingTimestamp;
  if ( IncomingTimestamp < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x460,
      (unsigned int)"avcore\\midi2\\service\\exe\\midiclientmanager.cpp",
      (const char *)(unsigned int)IncomingTimestamp,
      v60);
    std::wstring::~wstring(&v76);
    if ( AvrtHandle )
      AvRevertMmThreadCharacteristics(AvrtHandle);
    if ( v63 )
      (*(void (__fastcall **)(int *))(*(_QWORD *)v63 + 16LL))(v63);
    if ( v65 )
      (*(void (__fastcall **)(int *))(*(_QWORD *)v65 + 16LL))(v65);
    goto LABEL_170;
  }
  v24 = &v76;
  if ( si128.m128i_i64[1] > 7uLL )
    LODWORD(v24) = v76;
  v72 = *a3;
  v25 = v66[0];
  MidiClient = CMidiClientManager::GetMidiClient(
                 (_DWORD)SRWLock,
                 (_DWORD)v24,
                 (_DWORD)a2,
                 (unsigned int)&v72,
                 v66[0],
                 a6,
                 (__int64)v71,
                 a5,
                 (__int64)&v65,
                 v64[0]);
  v12 = MidiClient;
  if ( MidiClient < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x467,
      (unsigned int)"avcore\\midi2\\service\\exe\\midiclientmanager.cpp",
      (const char *)(unsigned int)MidiClient,
      v61);
    std::wstring::~wstring(&v76);
    if ( AvrtHandle )
      AvRevertMmThreadCharacteristics(AvrtHandle);
    if ( v63 )
      (*(void (__fastcall **)(int *))(*(_QWORD *)v63 + 16LL))(v63);
    if ( v65 )
      (*(void (__fastcall **)(int *))(*(_QWORD *)v65 + 16LL))(v65);
    goto LABEL_170;
  }
  v27 = &v76;
  if ( si128.m128i_i64[1] > 7uLL )
    v27 = (__int128 *)v76;
  MidiDevice = CMidiClientManager::GetMidiDevice(SRWLock, v27, v74, &v68);
  v12 = MidiDevice;
  if ( MidiDevice < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x470,
      (unsigned int)"avcore\\midi2\\service\\exe\\midiclientmanager.cpp",
      (const char *)(unsigned int)MidiDevice,
      v61);
    std::wstring::~wstring(&v76);
    if ( AvrtHandle )
      AvRevertMmThreadCharacteristics(AvrtHandle);
    if ( v63 )
      (*(void (__fastcall **)(int *))(*(_QWORD *)v63 + 16LL))(v63);
    if ( v68 )
      (*(void (__fastcall **)(const wchar_t *))(*(_QWORD *)v68 + 16LL))(v68);
    if ( v65 )
      (*(void (__fastcall **)(int *))(*(_QWORD *)v65 + 16LL))(v65);
    goto LABEL_170;
  }
  v29 = (unsigned int *)v68;
  (*(void (__fastcall **)(const wchar_t *, int *))(*(_QWORD *)v68 + 120LL))(v68, v65);
  if ( (v65[14] & 0xFFFFFFFD) == 0 )
  {
    v30 = v63;
    v31 = v29;
    v63 = (int *)v29;
    if ( v29 )
    {
      (*(void (__fastcall **)(unsigned int *, unsigned int *))(*(_QWORD *)v29 + 8LL))(v29, v29);
      v31 = (unsigned int *)v63;
    }
    if ( v30 )
    {
      (*(void (__fastcall **)(int *, unsigned int *))(*(_QWORD *)v30 + 16LL))(v30, v31);
      v31 = (unsigned int *)v63;
    }
    if ( !(*(unsigned int (__fastcall **)(int *, _QWORD))(*(_QWORD *)v65 + 96LL))(v65, v31[12]) )
    {
      *(_QWORD *)v66 = 0;
      MidiTransform = CMidiClientManager::GetMidiTransform(
                        (__int64)SRWLock,
                        a2,
                        0,
                        v63[12],
                        v65[12],
                        &v63,
                        (wchar_t *)v66);
      v33 = MidiTransform;
      if ( MidiTransform < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x485,
          (unsigned int)"avcore\\midi2\\service\\exe\\midiclientmanager.cpp",
          (const char *)(unsigned int)MidiTransform,
          v61);
        if ( *(_QWORD *)v66 )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v66 + 16LL))(*(_QWORD *)v66);
        std::wstring::~wstring(&v76);
        if ( AvrtHandle )
          AvRevertMmThreadCharacteristics(AvrtHandle);
        if ( v63 )
          (*(void (__fastcall **)(int *))(*(_QWORD *)v63 + 16LL))(v63);
        if ( v29 )
          (*(void (__fastcall **)(unsigned int *))(*(_QWORD *)v29 + 16LL))(v29);
        if ( v65 )
          (*(void (__fastcall **)(int *))(*(_QWORD *)v65 + 16LL))(v65);
LABEL_77:
        ReleaseSRWLockExclusive(SRWLock);
        v70 = 0;
        CMidiClientManager::CreateMidiClient_::_2_::_lambda_1_::operator()(v69);
        return v33;
      }
      (*(void (__fastcall **)(_QWORD, int *))(**(_QWORD **)v66 + 120LL))(*(_QWORD *)v66, v65);
      v34 = *(int **)v66;
      v35 = v63;
      v63 = *(int **)v66;
      if ( *(_QWORD *)v66 )
      {
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v66 + 8LL))(*(_QWORD *)v66);
        v34 = *(int **)v66;
      }
      if ( v35 )
      {
        (*(void (__fastcall **)(int *))(*(_QWORD *)v35 + 16LL))(v35);
        v34 = *(int **)v66;
      }
      if ( v34 )
        (*(void (__fastcall **)(int *))(*(_QWORD *)v34 + 16LL))(v34);
    }
    v36 = (*(__int64 (__fastcall **)(int *, _QWORD))(*(_QWORD *)v65 + 80LL))(v65, (unsigned int)v63[13]);
    v33 = v36;
    if ( v36 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x48B,
        (unsigned int)"avcore\\midi2\\service\\exe\\midiclientmanager.cpp",
        (const char *)(unsigned int)v36,
        v61);
      std::wstring::~wstring(&v76);
      if ( AvrtHandle )
        AvRevertMmThreadCharacteristics(AvrtHandle);
      if ( v63 )
        (*(void (__fastcall **)(int *))(*(_QWORD *)v63 + 16LL))(v63);
      if ( v29 )
        (*(void (__fastcall **)(unsigned int *))(*(_QWORD *)v29 + 16LL))(v29);
      if ( v65 )
        (*(void (__fastcall **)(int *))(*(_QWORD *)v65 + 16LL))(v65);
      goto LABEL_77;
    }
    *((_DWORD *)v71 + 20) = v65[12];
    v37 = (*(__int64 (__fastcall **)(int *, int **))(*(_QWORD *)v63 + 56LL))(v63, &v65);
    v33 = v37;
    if ( v37 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x48D,
        (unsigned int)"avcore\\midi2\\service\\exe\\midiclientmanager.cpp",
        (const char *)(unsigned int)v37,
        v61);
      std::wstring::~wstring(&v76);
      if ( AvrtHandle )
        AvRevertMmThreadCharacteristics(AvrtHandle);
      if ( v63 )
        (*(void (__fastcall **)(int *))(*(_QWORD *)v63 + 16LL))(v63);
      if ( v29 )
        (*(void (__fastcall **)(unsigned int *))(*(_QWORD *)v29 + 16LL))(v29);
      if ( v65 )
        (*(void (__fastcall **)(int *))(*(_QWORD *)v65 + 16LL))(v65);
      goto LABEL_77;
    }
    v38 = v63;
    v63 = 0;
    if ( v38 )
      (*(void (__fastcall **)(int *))(*(_QWORD *)v38 + 16LL))(v38);
  }
  if ( (unsigned int)(v65[14] - 1) <= 1 )
  {
    v39 = v63;
    v63 = (int *)v29;
    if ( v29 )
      (*(void (__fastcall **)(unsigned int *))(*(_QWORD *)v29 + 8LL))(v29);
    if ( v39 )
      (*(void (__fastcall **)(int *))(*(_QWORD *)v39 + 16LL))(v39);
    v64[0] = 0;
    EndpointRequiresOutboundProtocolDownscaling = GetEndpointRequiresOutboundProtocolDownscaling(
                                                    &v76,
                                                    *(unsigned int *)(a6 + 8),
                                                    v29[13],
                                                    v64);
    v33 = EndpointRequiresOutboundProtocolDownscaling;
    if ( EndpointRequiresOutboundProtocolDownscaling < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4A6,
        (unsigned int)"avcore\\midi2\\service\\exe\\midiclientmanager.cpp",
        (const char *)(unsigned int)EndpointRequiresOutboundProtocolDownscaling,
        v61);
      std::wstring::~wstring(&v76);
      if ( AvrtHandle )
        AvRevertMmThreadCharacteristics(AvrtHandle);
      if ( v63 )
        (*(void (__fastcall **)(int *))(*(_QWORD *)v63 + 16LL))(v63);
      (*(void (__fastcall **)(unsigned int *))(*(_QWORD *)v29 + 16LL))(v29);
      if ( v65 )
        (*(void (__fastcall **)(int *))(*(_QWORD *)v65 + 16LL))(v65);
      goto LABEL_77;
    }
    if ( v64[0] )
    {
      *(_QWORD *)v66 = 0;
      MidiProtocolDownscalerTransform = CMidiClientManager::GetMidiProtocolDownscalerTransform(
                                          (_DWORD)SRWLock,
                                          v41,
                                          (unsigned int)&v68,
                                          (unsigned int)&v63,
                                          (__int64)v66);
      v12 = MidiProtocolDownscalerTransform;
      if ( MidiProtocolDownscalerTransform < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4B0,
          (unsigned int)"avcore\\midi2\\service\\exe\\midiclientmanager.cpp",
          (const char *)(unsigned int)MidiProtocolDownscalerTransform,
          v61);
        if ( *(_QWORD *)v66 )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v66 + 16LL))(*(_QWORD *)v66);
        std::wstring::~wstring(&v76);
        if ( AvrtHandle )
          AvRevertMmThreadCharacteristics(AvrtHandle);
        if ( v63 )
          (*(void (__fastcall **)(int *))(*(_QWORD *)v63 + 16LL))(v63);
        if ( v68 )
          (*(void (__fastcall **)(const wchar_t *))(*(_QWORD *)v68 + 16LL))(v68);
        if ( v65 )
          (*(void (__fastcall **)(int *))(*(_QWORD *)v65 + 16LL))(v65);
        goto LABEL_170;
      }
      v43 = *(int **)v66;
      (*(void (__fastcall **)(_QWORD, int *))(**(_QWORD **)v66 + 120LL))(*(_QWORD *)v66, v65);
      v44 = v63;
      v63 = v43;
      if ( v43 )
        (*(void (__fastcall **)(int *))(*(_QWORD *)v43 + 8LL))(v43);
      if ( v44 )
        (*(void (__fastcall **)(int *))(*(_QWORD *)v44 + 16LL))(v44);
      if ( v43 )
        (*(void (__fastcall **)(int *))(*(_QWORD *)v43 + 16LL))(v43);
      v29 = (unsigned int *)v68;
    }
    if ( !(*(unsigned int (__fastcall **)(int *, _QWORD))(*(_QWORD *)v65 + 104LL))(v65, (unsigned int)v63[13]) )
    {
      *(_QWORD *)v66 = 0;
      v45 = CMidiClientManager::GetMidiTransform((__int64)SRWLock, a2, 1, v65[13], v63[13], &v63, (wchar_t *)v66);
      v33 = v45;
      if ( v45 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4C6,
          (unsigned int)"avcore\\midi2\\service\\exe\\midiclientmanager.cpp",
          (const char *)(unsigned int)v45,
          v61);
        if ( *(_QWORD *)v66 )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v66 + 16LL))(*(_QWORD *)v66);
        std::wstring::~wstring(&v76);
        if ( AvrtHandle )
          AvRevertMmThreadCharacteristics(AvrtHandle);
        if ( v63 )
          (*(void (__fastcall **)(int *))(*(_QWORD *)v63 + 16LL))(v63);
        if ( v29 )
          (*(void (__fastcall **)(unsigned int *))(*(_QWORD *)v29 + 16LL))(v29);
        if ( v65 )
          (*(void (__fastcall **)(int *))(*(_QWORD *)v65 + 16LL))(v65);
        goto LABEL_77;
      }
      (*(void (__fastcall **)(_QWORD, int *))(**(_QWORD **)v66 + 120LL))(*(_QWORD *)v66, v65);
      v46 = *(int **)v66;
      v47 = v63;
      v63 = *(int **)v66;
      if ( *(_QWORD *)v66 )
      {
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v66 + 8LL))(*(_QWORD *)v66);
        v46 = *(int **)v66;
      }
      if ( v47 )
      {
        (*(void (__fastcall **)(int *))(*(_QWORD *)v47 + 16LL))(v47);
        v46 = *(int **)v66;
      }
      if ( v46 )
        (*(void (__fastcall **)(int *))(*(_QWORD *)v46 + 16LL))(v46);
    }
    if ( (*(unsigned int (__fastcall **)(int *, __int64))(*(_QWORD *)v63 + 96LL))(v63, 2) )
    {
      *(_QWORD *)v66 = 0;
      MidiScheduler = CMidiClientManager::GetMidiScheduler(
                        (_DWORD)SRWLock,
                        v48,
                        (unsigned int)&v68,
                        (unsigned int)&v63,
                        (__int64)v66);
      v12 = MidiScheduler;
      if ( MidiScheduler < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4DA,
          (unsigned int)"avcore\\midi2\\service\\exe\\midiclientmanager.cpp",
          (const char *)(unsigned int)MidiScheduler,
          v61);
        if ( *(_QWORD *)v66 )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v66 + 16LL))(*(_QWORD *)v66);
        std::wstring::~wstring(&v76);
        if ( AvrtHandle )
          AvRevertMmThreadCharacteristics(AvrtHandle);
        if ( v63 )
          (*(void (__fastcall **)(int *))(*(_QWORD *)v63 + 16LL))(v63);
        if ( v68 )
          (*(void (__fastcall **)(const wchar_t *))(*(_QWORD *)v68 + 16LL))(v68);
        if ( v65 )
          (*(void (__fastcall **)(int *))(*(_QWORD *)v65 + 16LL))(v65);
        goto LABEL_170;
      }
      v50 = *(int **)v66;
      (*(void (__fastcall **)(_QWORD, int *))(**(_QWORD **)v66 + 120LL))(*(_QWORD *)v66, v65);
      v51 = v63;
      v63 = v50;
      if ( v50 )
        (*(void (__fastcall **)(int *))(*(_QWORD *)v50 + 8LL))(v50);
      if ( v51 )
        (*(void (__fastcall **)(int *))(*(_QWORD *)v51 + 16LL))(v51);
      if ( v50 )
        (*(void (__fastcall **)(int *))(*(_QWORD *)v50 + 16LL))(v50);
      v29 = (unsigned int *)v68;
    }
    v52 = (*(__int64 (__fastcall **)(int *, _QWORD))(*(_QWORD *)v65 + 88LL))(v65, (unsigned int)v63[12]);
    v33 = v52;
    if ( v52 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4E5,
        (unsigned int)"avcore\\midi2\\service\\exe\\midiclientmanager.cpp",
        (const char *)(unsigned int)v52,
        v61);
      std::wstring::~wstring(&v76);
      if ( AvrtHandle )
        AvRevertMmThreadCharacteristics(AvrtHandle);
      if ( v63 )
        (*(void (__fastcall **)(int *))(*(_QWORD *)v63 + 16LL))(v63);
      if ( v29 )
        (*(void (__fastcall **)(unsigned int *))(*(_QWORD *)v29 + 16LL))(v29);
      if ( v65 )
        (*(void (__fastcall **)(int *))(*(_QWORD *)v65 + 16LL))(v65);
      goto LABEL_77;
    }
    *((_DWORD *)v71 + 20) = v65[13];
    v53 = (*(__int64 (__fastcall **)(int *, int **))(*(_QWORD *)v65 + 56LL))(v65, &v63);
    v33 = v53;
    if ( v53 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4E7,
        (unsigned int)"avcore\\midi2\\service\\exe\\midiclientmanager.cpp",
        (const char *)(unsigned int)v53,
        v61);
      std::wstring::~wstring(&v76);
      if ( AvrtHandle )
        AvRevertMmThreadCharacteristics(AvrtHandle);
      if ( v63 )
        (*(void (__fastcall **)(int *))(*(_QWORD *)v63 + 16LL))(v63);
      if ( v29 )
        (*(void (__fastcall **)(unsigned int *))(*(_QWORD *)v29 + 16LL))(v29);
      if ( v65 )
        (*(void (__fastcall **)(int *))(*(_QWORD *)v65 + 16LL))(v65);
      goto LABEL_77;
    }
    v54 = v63;
    v63 = 0;
    if ( v54 )
      (*(void (__fastcall **)(int *))(*(_QWORD *)v54 + 16LL))(v54);
  }
  v55 = SRWLock[7].Ptr;
  v72 = *a3;
  *(_QWORD *)v62 = *((_QWORD *)v71 + 9);
  v56 = (*(__int64 (__fastcall **)(PVOID, __int128 *, _QWORD, const wchar_t *))(*(_QWORD *)v55 + 24LL))(
          v55,
          &v72,
          v25,
          a2);
  v33 = v56;
  if ( v56 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4EB,
      (unsigned int)"avcore\\midi2\\service\\exe\\midiclientmanager.cpp",
      (const char *)(unsigned int)v56,
      v62[0]);
    std::wstring::~wstring(&v76);
    if ( AvrtHandle )
      AvRevertMmThreadCharacteristics(AvrtHandle);
    if ( v63 )
      (*(void (__fastcall **)(int *))(*(_QWORD *)v63 + 16LL))(v63);
    if ( v29 )
      (*(void (__fastcall **)(unsigned int *))(*(_QWORD *)v29 + 16LL))(v29);
    if ( v65 )
      (*(void (__fastcall **)(int *))(*(_QWORD *)v65 + 16LL))(v65);
    goto LABEL_77;
  }
  std::wstring::~wstring(&v76);
  if ( AvrtHandle )
    AvRevertMmThreadCharacteristics(AvrtHandle);
  if ( v63 )
    (*(void (__fastcall **)(int *))(*(_QWORD *)v63 + 16LL))(v63);
  if ( v29 )
    (*(void (__fastcall **)(unsigned int *))(*(_QWORD *)v29 + 16LL))(v29);
  if ( v65 )
    (*(void (__fastcall **)(int *))(*(_QWORD *)v65 + 16LL))(v65);
  ReleaseSRWLockExclusive(SRWLock);
  v57 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v57 > 4u )
  {
    *(_QWORD *)v73 = a2;
    LODWORD(v63) = v25;
    *(_QWORD *)&v72 = a3;
    v68 = L"Complete.";
    AvrtHandle = SRWLock;
    v65 = (int *)"CMidiClientManager::CreateMidiClient";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
      (_DWORD)v57,
      (unsigned int)word_140087CCA,
      v58,
      v59,
      (__int64)&v65,
      (__int64)&AvrtHandle,
      (__int64)&v68,
      (__int64)&v72,
      (__int64)&v63,
      (__int64)v73);
  }
  return 0;
}

```

## disassembly

```asm
0x1400152d0  push    rbp
0x1400152d2  push    rbx
0x1400152d3  push    rsi
0x1400152d4  push    rdi
0x1400152d5  push    r12
0x1400152d7  push    r13
0x1400152d9  push    r14
0x1400152db  push    r15
0x1400152dd  lea     rbp, [rsp-38h]
0x1400152e2  sub     rsp, 138h
0x1400152e9  mov     rax, cs:__security_cookie
0x1400152f0  xor     rax, rsp
0x1400152f3  mov     [rbp+70h+var_50], rax
0x1400152f7  mov     ebx, r9d
0x1400152fa  mov     [rsp+170h+var_108], ebx
0x1400152fe  mov     r13, r8
0x140015301  mov     r15, rdx
0x140015304  mov     rdi, rcx
0x140015307  mov     rsi, [rbp+70h+arg_28]
0x14001530e  mov     r14, [rbp+70h+arg_20]
0x140015315  mov     rax, [rbp+70h+arg_30]
0x14001531c  mov     [rbp+70h+var_D8], rax
0x140015320  lea     r12, [rsi+8]
0x140015324  cmp     dword ptr [r12], 2
0x140015329  jbe     short loc_14001534F
0x14001532b  mov     edx, 3D9h; void *
0x140015330  mov     ebx, 80070057h
0x140015335  mov     rcx, [rbp+78h]; this
0x140015339  mov     r9d, ebx; char *
0x14001533c  lea     r8, aAvcoreMidi2Ser_1; "avcore\\midi2\\service\\exe\\midiclient"...
0x140015343  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140015348  mov     eax, ebx
0x14001534a  jmp     loc_14001645E
0x14001534f  test    dword ptr [rsi], 0FFFFFFF8h
0x140015355  jz      short loc_14001535E
0x140015357  mov     edx, 3DBh
0x14001535c  jmp     short loc_140015330
0x14001535e  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x140015363  mov     rcx, [rax+8]
0x140015367  mov     eax, [rcx]
0x140015369  lea     rdx, aCmidiclientman_8; "CMidiClientManager::CreateMidiClient"
0x140015370  cmp     eax, 4
0x140015373  jbe     short loc_1400153DD
0x140015375  mov     [rsp+170h+var_F8], r15
0x14001537a  mov     dword ptr [rsp+170h+var_120], ebx
0x14001537e  mov     [rsp+170h+AvrtHandle], r13
0x140015383  lea     rax, aEnter; "Enter"
0x14001538a  mov     [rsp+170h+var_110], rax
0x14001538f  mov     qword ptr [rbp+70h+var_D0], rdi
0x140015393  mov     qword ptr [rbp+70h+var_C0], rdx
0x140015397  lea     rax, [rsp+170h+var_F8]
0x14001539c  mov     [rsp+170h+var_128], rax
0x1400153a1  lea     rax, [rsp+170h+var_120]
0x1400153a6  mov     [rsp+170h+var_130], rax
0x1400153ab  lea     rax, [rsp+170h+AvrtHandle]
0x1400153b0  mov     [rsp+170h+var_138], rax
0x1400153b5  lea     rax, [rsp+170h+var_110]
0x1400153ba  mov     [rsp+170h+var_140], rax
0x1400153bf  lea     rax, [rbp+70h+var_D0]
0x1400153c3  mov     [rsp+170h+var_148], rax
0x1400153c8  lea     rax, [rbp+70h+var_C0]
0x1400153cc  mov     qword ptr [rsp+170h+var_150], rax; int
0x1400153d1  lea     rdx, byte_140087FE9
0x1400153d8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x1400153dd  mov     rcx, [rdi+38h]
0x1400153e1  movups  xmm0, xmmword ptr [r13+0]
0x1400153e6  movdqu  xmmword ptr [rbp+70h+var_C0], xmm0
0x1400153eb  mov     rax, [rcx]
0x1400153ee  mov     r8d, ebx
0x1400153f1  lea     rdx, [rbp+70h+var_C0]
0x1400153f5  mov     rax, [rax+8]
0x1400153f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400153fe  mov     ebx, eax
0x140015400  test    eax, eax
0x140015402  jns     loc_14001549B
0x140015408  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14001540d  mov     r8, [rax+8]
0x140015411  mov     ecx, [r8]
0x140015414  cmp     ecx, 2
0x140015417  jbe     short loc_140015491
0x140015419  mov     qword ptr [rbp+70h+var_C0], r15
0x14001541d  mov     r14d, [rsp+170h+var_108]
0x140015422  mov     dword ptr [rsp+170h+var_120], r14d
0x140015427  mov     qword ptr [rbp+70h+var_D0], r13
0x14001542b  lea     rax, aSessionIsInval; "Session is invalid for this client proc"...
0x140015432  mov     [rsp+170h+var_F8], rax
0x140015437  mov     [rsp+170h+AvrtHandle], rdi
0x14001543c  lea     rax, aCmidiclientman_8; "CMidiClientManager::CreateMidiClient"
0x140015443  mov     [rsp+170h+var_110], rax
0x140015448  lea     rax, [rbp+70h+var_C0]
0x14001544c  mov     [rsp+170h+var_128], rax
0x140015451  lea     rax, [rsp+170h+var_120]
0x140015456  mov     [rsp+170h+var_130], rax
0x14001545b  lea     rax, [rbp+70h+var_D0]
0x14001545f  mov     [rsp+170h+var_138], rax
0x140015464  lea     rax, [rsp+170h+var_F8]
0x140015469  mov     [rsp+170h+var_140], rax
0x14001546e  lea     rax, [rsp+170h+AvrtHandle]
0x140015473  mov     [rsp+170h+var_148], rax
0x140015478  lea     rax, [rsp+170h+var_110]
0x14001547d  mov     qword ptr [rsp+170h+var_150], rax
0x140015482  lea     rdx, byte_1400872E3
0x140015489  mov     rcx, r8
0x14001548c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x140015491  mov     edx, 3F8h
0x140015496  jmp     loc_140015335
0x14001549b  xor     edx, edx; Val
0x14001549d  lea     r8d, [rdx+58h]; Size
0x1400154a1  mov     rcx, [rbp+70h+var_D8]; void *
0x1400154a5  call    memset_0
0x1400154aa  lea     rax, [rbp+70h+var_D8]
0x1400154ae  mov     [rbp+70h+var_F0], rax
0x1400154b2  mov     [rbp+70h+var_E8], rdi
0x1400154b6  mov     [rbp+70h+var_E0], 1
0x1400154ba  mov     rcx, rdi; SRWLock
0x1400154bd  call    cs:__imp_AcquireSRWLockExclusive
0x1400154c3  mov     qword ptr [rbp+70h+var_C0], rdi
0x1400154c7  xor     eax, eax
0x1400154c9  mov     [rsp+170h+var_110], rax
0x1400154ce  mov     [rsp+170h+var_F8], rax
0x1400154d3  mov     [rsp+170h+var_120], rax
0x1400154d8  mov     [rsp+170h+AvrtHandle], rax
0x1400154dd  xorps   xmm0, xmm0
0x1400154e0  movups  [rbp+70h+var_70], xmm0
0x1400154e4  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1400154ec  movdqu  [rbp+70h+var_60], xmm1
0x1400154f1  mov     word ptr [rbp+70h+var_70], ax
0x1400154f5  mov     [rsp+170h+var_118], 1
0x1400154fa  movups  xmm0, xmmword ptr [rsi]
0x1400154fd  movups  [rbp+70h+var_B0], xmm0
0x140015501  movups  xmm1, xmmword ptr [rsi+10h]
0x140015505  movups  [rbp+70h+var_A0], xmm1
0x140015509  lea     rdx, [rdi+78h]
0x14001550d  lea     rcx, [rsp+170h+AvrtHandle]
0x140015512  call    ?EnableMmcss@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?AvRevertMmThreadCharacteristics@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@AEAK@Z; EnableMmcss(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&AvRevertMmThreadCharacteristics(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &,ulong &)
0x140015517  mov     ebx, eax
0x140015519  test    eax, eax
0x14001551b  jns     short loc_14001559C
0x14001551d  mov     rcx, [rbp+78h]; this
0x140015521  mov     r9d, eax; char *
0x140015524  lea     r8, aAvcoreMidi2Ser_1; "avcore\\midi2\\service\\exe\\midiclient"...
0x14001552b  mov     edx, 454h; void *
0x140015530  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140015535  nop
0x140015536  lea     rcx, [rbp+70h+var_70]; void *
0x14001553a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001553f  nop
0x140015540  mov     rcx, [rsp+170h+AvrtHandle]; AvrtHandle
0x140015545  test    rcx, rcx
0x140015548  jz      short loc_140015551
0x14001554a  call    cs:__imp_AvRevertMmThreadCharacteristics
0x140015550  nop
0x140015551  mov     rcx, [rsp+170h+var_120]
0x140015556  test    rcx, rcx
0x140015559  jz      short loc_140015568
0x14001555b  mov     rax, [rcx]
0x14001555e  mov     rax, [rax+10h]
0x140015562  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015567  nop
0x140015568  mov     rcx, [rsp+170h+var_110]
0x14001556d  test    rcx, rcx
0x140015570  jz      short loc_14001557F
0x140015572  mov     rax, [rcx]
0x140015575  mov     rax, [rax+10h]
0x140015579  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001557e  nop
0x14001557f  mov     rcx, rdi; SRWLock
0x140015582  call    cs:__imp_ReleaseSRWLockExclusive
0x140015588  nop
0x140015589  mov     [rbp+70h+var_E0], 0
0x14001558d  lea     rcx, [rbp+70h+var_F0]
0x140015591  call    _CMidiClientManager__CreateMidiClient____2____lambda_1___operator__
0x140015596  nop
0x140015597  jmp     loc_140015348
0x14001559c  lea     r8, [rbp+70h+var_B0+8]
0x1400155a0  lea     rdx, [rbp+70h+var_70]
0x1400155a4  mov     rcx, r15
0x1400155a7  call    ?GetEndpointAlias@@YAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAW4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0002@@@Z; GetEndpointAlias(ushort const *,std::wstring &,__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0002 &)
0x1400155ac  mov     ebx, eax
0x1400155ae  test    eax, eax
0x1400155b0  jns     short loc_140015631
0x1400155b2  mov     rcx, [rbp+78h]; this
0x1400155b6  mov     r9d, eax; char *
0x1400155b9  lea     r8, aAvcoreMidi2Ser_1; "avcore\\midi2\\service\\exe\\midiclient"...
0x1400155c0  mov     edx, 459h; void *
0x1400155c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400155ca  nop
0x1400155cb  lea     rcx, [rbp+70h+var_70]; void *
0x1400155cf  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400155d4  nop
0x1400155d5  mov     rcx, [rsp+170h+AvrtHandle]; AvrtHandle
0x1400155da  test    rcx, rcx
0x1400155dd  jz      short loc_1400155E6
0x1400155df  call    cs:__imp_AvRevertMmThreadCharacteristics
0x1400155e5  nop
0x1400155e6  mov     rcx, [rsp+170h+var_120]
0x1400155eb  test    rcx, rcx
0x1400155ee  jz      short loc_1400155FD
0x1400155f0  mov     rax, [rcx]
0x1400155f3  mov     rax, [rax+10h]
0x1400155f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400155fc  nop
0x1400155fd  mov     rcx, [rsp+170h+var_110]
0x140015602  test    rcx, rcx
0x140015605  jz      short loc_140015614
0x140015607  mov     rax, [rcx]
0x14001560a  mov     rax, [rax+10h]
0x14001560e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015613  nop
0x140015614  mov     rcx, rdi; SRWLock
0x140015617  call    cs:__imp_ReleaseSRWLockExclusive
0x14001561d  nop
0x14001561e  mov     [rbp+70h+var_E0], 0
0x140015622  lea     rcx, [rbp+70h+var_F0]
0x140015626  call    _CMidiClientManager__CreateMidiClient____2____lambda_1___operator__
0x14001562b  nop
0x14001562c  jmp     loc_140015348
0x140015631  lea     rdx, [rbp+70h+var_70]
0x140015635  lea     rcx, [rbp+70h+var_90]
0x140015639  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14001563e  mov     r8, r12
0x140015641  lea     rdx, [rsp+170h+var_118]
0x140015646  mov     rcx, rax; void *
0x140015649  call    ?GetEndpointGenerateIncomingTimestamp@@YAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEA_NAEAW4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0002@@@Z; GetEndpointGenerateIncomingTimestamp(std::wstring,bool &,__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0002 &)
0x14001564e  mov     ebx, eax
0x140015650  test    eax, eax
0x140015652  jns     short loc_1400156D3
0x140015654  mov     rcx, [rbp+78h]; this
0x140015658  mov     r9d, eax; char *
0x14001565b  lea     r8, aAvcoreMidi2Ser_1; "avcore\\midi2\\service\\exe\\midiclient"...
0x140015662  mov     edx, 460h; void *
0x140015667  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001566c  nop
0x14001566d  lea     rcx, [rbp+70h+var_70]; void *
0x140015671  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140015676  nop
0x140015677  mov     rcx, [rsp+170h+AvrtHandle]; AvrtHandle
0x14001567c  test    rcx, rcx
0x14001567f  jz      short loc_140015688
0x140015681  call    cs:__imp_AvRevertMmThreadCharacteristics
0x140015687  nop
0x140015688  mov     rcx, [rsp+170h+var_120]
0x14001568d  test    rcx, rcx
0x140015690  jz      short loc_14001569F
0x140015692  mov     rax, [rcx]
0x140015695  mov     rax, [rax+10h]
0x140015699  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001569e  nop
0x14001569f  mov     rcx, [rsp+170h+var_110]
0x1400156a4  test    rcx, rcx
0x1400156a7  jz      short loc_1400156B6
0x1400156a9  mov     rax, [rcx]
0x1400156ac  mov     rax, [rax+10h]
0x1400156b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400156b5  nop
0x1400156b6  mov     rcx, rdi; SRWLock
0x1400156b9  call    cs:__imp_ReleaseSRWLockExclusive
0x1400156bf  nop
0x1400156c0  mov     [rbp+70h+var_E0], 0
0x1400156c4  lea     rcx, [rbp+70h+var_F0]
0x1400156c8  call    _CMidiClientManager__CreateMidiClient____2____lambda_1___operator__
0x1400156cd  nop
0x1400156ce  jmp     loc_140015348
0x1400156d3  movzx   eax, [rsp+170h+var_118]
0x1400156d8  mov     rcx, [rbp+70h+var_D8]
0x1400156dc  lea     rdx, [rbp+70h+var_70]
0x1400156e0  cmp     qword ptr [rbp+70h+var_60+8], 7
0x1400156e5  cmova   rdx, qword ptr [rbp+70h+var_70]
0x1400156ea  movups  xmm0, xmmword ptr [r13+0]
0x1400156ef  movdqu  [rbp+70h+var_D0], xmm0
0x1400156f4  mov     dword ptr [rsp+170h+var_128], eax
0x1400156f8  lea     rax, [rsp+170h+var_110]
0x1400156fd  mov     [rsp+170h+var_130], rax
0x140015702  mov     [rsp+170h+var_138], r14
0x140015707  mov     [rsp+170h+var_140], rcx
0x14001570c  mov     [rsp+170h+var_148], rsi
0x140015711  mov     r14d, [rsp+170h+var_108]
0x140015716  mov     [rsp+170h+var_150], r14d; int
0x14001571b  lea     r9, [rbp+70h+var_D0]
0x14001571f  mov     r8, r15
0x140015722  mov     rcx, rdi
0x140015725  call    ?GetMidiClient@CMidiClientManager@@AEAAJPEBG0U_GUID@@KPEAUMIDISRV_CLIENTCREATION_PARAMS@@PEAUMIDISRV_CLIENT@@AEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@AEAV?$com_ptr_t@VCMidiPipe@@Uerr_returncode_policy@wil@@@6@H@Z; CMidiClientManager::GetMidiClient(ushort const *,ushort const *,_GUID,ulong,MIDISRV_CLIENTCREATION_PARAMS *,MIDISRV_CLIENT *,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &,wil::com_ptr_t<CMidiPipe,wil::err_returncode_policy> &,int)
0x14001572a  mov     ebx, eax
0x14001572c  test    eax, eax
0x14001572e  jns     short loc_1400157AF
0x140015730  mov     rcx, [rbp+78h]; this
0x140015734  mov     r9d, eax; char *
0x140015737  lea     r8, aAvcoreMidi2Ser_1; "avcore\\midi2\\service\\exe\\midiclient"...
0x14001573e  mov     edx, 467h; void *
0x140015743  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140015748  nop
0x140015749  lea     rcx, [rbp+70h+var_70]; void *
0x14001574d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140015752  nop
0x140015753  mov     rcx, [rsp+170h+AvrtHandle]; AvrtHandle
0x140015758  test    rcx, rcx
0x14001575b  jz      short loc_140015764
0x14001575d  call    cs:__imp_AvRevertMmThreadCharacteristics
0x140015763  nop
0x140015764  mov     rcx, [rsp+170h+var_120]
  ... truncated ...
```
