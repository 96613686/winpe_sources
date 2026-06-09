# CMidiDeviceManager::RebuildAndUpdateNameTableForMidi2EndpointWithFunctionBlocks(ushort const *,winrt::Windows::Devices::Enumeration::DeviceInformation,_MIDIPORT *)

- ea: `0x1400318c8`
- end: `0x1400324ac`
- name: `?RebuildAndUpdateNameTableForMidi2EndpointWithFunctionBlocks@CMidiDeviceManager@@AEAAJPEBGUDeviceInformation@Enumeration@Devices@Windows@winrt@@PEAU_MIDIPORT@@@Z`
- size: `3044`
- prototype: ``
- caller_count: `1`
- callee_count: `37`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x140032ff4`

## callees

- `0x140001ce8`
- `0x140002e24`
- `0x1400054c0`
- `0x14000617c`
- `0x1400061e8`
- `0x140006200`
- `0x1400072d4`
- `0x140007c20`
- `0x14000984c`
- `0x14000a6b4`
- `0x14000c7f4`
- `0x14000cc2c`
- `0x14000cd78`
- `0x14001440c`
- `0x1400145bc`
- `0x14001487c`
- `0x14001bd28`
- `0x14001c390`
- `0x140026754`
- `0x14002698c`
- `0x140026b34`
- `0x1400270dc`
- `0x1400285c4`
- `0x14002883c`
- `0x140028c74`
- `0x140028e18`
- `0x14003182c`
- `0x1400318c8`
- `0x14003550c`
- `0x140035d24`
- `0x140051dfc`
- `0x140052978`
- `0x1400529fc`
- `0x140052a80`
- `0x140052d7c`
- `0x1400537a0`
- `0x14005a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1400322e9`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1400322f0`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1400322f7`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1400324a5`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1400322e9`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1400322f0`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1400322f7`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1400324a5`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceInterfacePropertySet` at `0x140032322`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceInterfacePropertySet` at `0x140032322`

## string_xrefs

- `0x14003233c`: `avcore\midi2\service\exe\mididevicemanager.cpp`
- `0x140031922`: `CMidiDeviceManager::RebuildAndUpdateNameTableForMidi2EndpointWithFunctionBlocks`
- `0x140031f9d`: `CMidiDeviceManager::RebuildAndUpdateNameTableForMidi2EndpointWithFunctionBlocks`
- `0x1400321b6`: `CMidiDeviceManager::RebuildAndUpdateNameTableForMidi2EndpointWithFunctionBlocks`

## pseudocode

```c
// Hidden C++ exception states: #wind=26
__int64 __fastcall CMidiDeviceManager::RebuildAndUpdateNameTableForMidi2EndpointWithFunctionBlocks(
        volatile signed __int32 *a1,
        void *a2,
        struct winrt::impl::shared_hstring_header **a3,
        __int64 a4)
{
  __int64 v4; // r14
  struct winrt::impl::shared_hstring_header **v5; // rsi
  struct winrt::impl::shared_hstring_header *v8; // r15
  _DWORD *v9; // rcx
  __int64 v10; // r8
  __int64 v11; // r9
  const char *v12; // rdx
  struct winrt::impl::shared_hstring_header *v13; // rcx
  struct winrt::impl::shared_hstring_header *v14; // rbx
  unsigned __int8 SwdPropertyFromDevice; // al
  unsigned int v16; // ebx
  char v18; // r12
  unsigned int v19; // r13d
  unsigned int v20; // eax
  LPVOID v21; // rbx
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // r9
  char **v25; // rdx
  __int64 v26; // rcx
  unsigned int v27; // edx
  const char *v28; // rcx
  void **v29; // r14
  __int64 v30; // rdi
  volatile signed __int32 **v31; // rax
  void *v32; // rdi
  int v33; // eax
  HANDLE ProcessHeap; // rax
  __int64 v35; // rax
  void *v36; // rdi
  int v37; // eax
  HANDLE v38; // rax
  unsigned __int64 v39; // r8
  __int128 *v40; // rdx
  unsigned int v41; // r14d
  char v42; // si
  const char **v43; // r13
  const wchar_t *v44; // rdx
  unsigned __int64 v45; // r8
  const wchar_t *v46; // rdx
  unsigned __int64 v47; // r8
  __int64 v48; // r8
  const wchar_t *v49; // rdx
  unsigned __int64 v50; // r8
  int v51; // edx
  volatile signed __int32 *v52; // rdi
  _DWORD *v53; // rcx
  __int64 v54; // r8
  __int64 v55; // r9
  const char *v56; // rax
  const wchar_t *v57; // rdx
  unsigned __int64 v58; // r8
  const wchar_t *v59; // rdx
  unsigned __int64 v60; // r8
  __int64 v61; // r8
  const wchar_t *v62; // rdx
  unsigned __int64 v63; // r8
  int v64; // edx
  volatile signed __int32 *v65; // rdi
  _DWORD *v66; // rcx
  __int64 v67; // r8
  __int64 v68; // r9
  int *v69; // rax
  struct winrt::impl::shared_hstring_header **v70; // rax
  struct winrt::impl::shared_hstring_header *v71; // rcx
  int v72; // eax
  unsigned int v73; // edi
  int v74; // eax
  HANDLE v75; // rax
  volatile signed __int32 *v76; // rbx
  int v77; // eax
  HANDLE v78; // rax
  volatile signed __int32 *v79; // rbx
  int v80; // [rsp+20h] [rbp-E0h]
  __int16 v81; // [rsp+50h] [rbp-B0h] BYREF
  const char *v82; // [rsp+58h] [rbp-A8h] BYREF
  struct winrt::impl::shared_hstring_header *v83; // [rsp+60h] [rbp-A0h] BYREF
  struct winrt::impl::shared_hstring_header *v84; // [rsp+68h] [rbp-98h] BYREF
  int v85[2]; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v86; // [rsp+78h] [rbp-88h]
  unsigned int v87; // [rsp+7Ch] [rbp-84h]
  const char **v88; // [rsp+80h] [rbp-80h] BYREF
  int *v89; // [rsp+88h] [rbp-78h] BYREF
  volatile signed __int32 *v90; // [rsp+90h] [rbp-70h] BYREF
  LPVOID lpMem; // [rsp+98h] [rbp-68h] BYREF
  LPVOID v92; // [rsp+A0h] [rbp-60h] BYREF
  struct winrt::impl::shared_hstring_header *v93; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v94; // [rsp+B0h] [rbp-50h]
  struct WindowsMidiServicesNamingLib::MidiEndpointNameTable *v95; // [rsp+B8h] [rbp-48h] BYREF
  volatile signed __int32 *v96; // [rsp+C0h] [rbp-40h]
  __int128 v97; // [rsp+C8h] [rbp-38h] BYREF
  struct winrt::impl::shared_hstring_header *v98; // [rsp+D8h] [rbp-28h]
  LPVOID v99; // [rsp+E0h] [rbp-20h] BYREF
  volatile signed __int32 *v100; // [rsp+E8h] [rbp-18h]
  struct winrt::impl::shared_hstring_header **v101; // [rsp+F0h] [rbp-10h]
  __int64 v102; // [rsp+F8h] [rbp-8h] BYREF
  volatile signed __int32 *v103; // [rsp+100h] [rbp+0h]
  __int64 v104; // [rsp+108h] [rbp+8h] BYREF
  volatile signed __int32 *v105; // [rsp+110h] [rbp+10h]
  LPVOID pv; // [rsp+118h] [rbp+18h] BYREF
  int v107; // [rsp+120h] [rbp+20h]
  _OWORD v108[3]; // [rsp+128h] [rbp+28h] BYREF
  __int64 v109; // [rsp+158h] [rbp+58h]
  struct winrt::impl::shared_hstring_header **v110; // [rsp+160h] [rbp+60h]
  __int128 v111; // [rsp+170h] [rbp+70h] BYREF
  unsigned __int64 v112; // [rsp+180h] [rbp+80h]
  unsigned __int64 v113; // [rsp+188h] [rbp+88h]
  __int128 v114; // [rsp+190h] [rbp+90h] BYREF
  __int128 v115; // [rsp+1A0h] [rbp+A0h]
  __int128 v116; // [rsp+1B0h] [rbp+B0h] BYREF
  __int128 v117; // [rsp+1C0h] [rbp+C0h]
  __int128 v118; // [rsp+1D0h] [rbp+D0h] BYREF
  __int128 v119; // [rsp+1E0h] [rbp+E0h]
  void *Source[4]; // [rsp+1F0h] [rbp+F0h] BYREF
  char *v121[4]; // [rsp+210h] [rbp+110h] BYREF
  _OWORD Src[2]; // [rsp+230h] [rbp+130h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  v4 = a4;
  v94 = a4;
  v5 = a3;
  v101 = a3;
  v100 = a1;
  v110 = a3;
  v8 = 0;
  v9 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  v12 = "CMidiDeviceManager::RebuildAndUpdateNameTableForMidi2EndpointWithFunctionBlocks";
  if ( *v9 > 4u )
  {
    v92 = a2;
    lpMem = L"Enter";
    v90 = a1;
    v82 = "CMidiDeviceManager::RebuildAndUpdateNameTableForMidi2EndpointWithFunctionBlocks";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (__int64)v9,
      (__int64)&dword_14008A57C,
      v10,
      v11,
      &v82,
      (__int64)&v90,
      &lpMem,
      &v92);
  }
  v89 = (int *)&v84;
  v13 = *v5;
  v84 = v13;
  if ( v13 )
    (*(void (__fastcall **)(struct winrt::impl::shared_hstring_header *, const char *))(*(_QWORD *)v13 + 8LL))(v13, v12);
  v14 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)0x2A, (unsigned int)v12);
  memcpy_s((char *)v14 + 28, 0x54u, L"{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} 180", 0x54u);
  v83 = v14;
  SwdPropertyFromDevice = WindowsMidiServicesInternal::SafeGetSwdPropertyFromDeviceInformation<unsigned char>(
                            (volatile signed __int32 **)&v83,
                            &v84,
                            0);
  v16 = SwdPropertyFromDevice;
  if ( !SwdPropertyFromDevice )
  {
    if ( *v5 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v5);
    return 2147943568LL;
  }
  WindowsMidiServicesNamingLib::MidiEndpointNameTable::FromDeviceInfo(&v95, v5);
  memset(v108, 0, sizeof(v108));
  v109 = 0;
  WindowsMidiServicesNamingLib::MidiEndpointNameTable::MidiEndpointNameTable((WindowsMidiServicesNamingLib::MidiEndpointNameTable *)v108);
  winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Name(
    v5,
    &v99);
  v18 = 0;
  LOBYTE(v81) = 0;
  v19 = 0;
  v86 = 0;
  v20 = v16;
  v87 = v16;
  v21 = v99;
  if ( v20 )
  {
    do
    {
      if ( v19 >= 0x20 )
        break;
      memset(Src, 0, sizeof(Src));
      std::wstring::_Construct<1,unsigned short const *>((char **)Src, L"{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD}", 0x26u);
      std::wstring::operator+=(Src, L" ");
      v22 = std::to_wstring(&v118, v19 + 200);
      std::operator+<unsigned short>(v121, Src, v22);
      std::wstring::~wstring((char **)&v118);
      v23 = std::to_wstring(&v116, v19 + 300);
      std::operator+<unsigned short>(Source, Src, v23);
      std::wstring::~wstring((char **)&v116);
      v111 = 0;
      v112 = (unsigned __int64)v8;
      v113 = 7;
      LOWORD(v111) = (_WORD)v8;
      v24 = winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Properties(
              v5,
              &v93);
      v25 = v121;
      if ( v121[3] > (char *)7 )
        v25 = (char **)v121[0];
      v26 = -1;
      do
        ++v26;
      while ( *((_WORD *)v25 + v26) != (_WORD)v8 );
      if ( (_DWORD)v26 )
      {
        if ( *((_WORD *)v25 + (unsigned int)v26) != (_WORD)v8 )
          abort();
        DWORD2(v114) = 1;
        HIDWORD(v114) = v26;
        *((_QWORD *)&v115 + 1) = v25;
        *(_QWORD *)&v114 = (char *)&v114 + 8;
      }
      else
      {
        *(_QWORD *)&v114 = v8;
      }
      winrt::impl::consume_Windows_Foundation_Collections_IMapView<winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Windows::Foundation::IInspectable>,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(
        v24,
        &v83,
        &v114);
      if ( v93 != v8 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v93);
      v82 = (const char *)v8;
      if ( !winrt::Windows::Foundation::operator==((void (__fastcall ****)(_QWORD, __int64 *, __int64 *))&v83, &v82) )
      {
        v89 = v85;
        *(_QWORD *)v85 = v8;
        v88 = &v82;
        v28 = (const char *)*v5;
        v82 = v28;
        if ( v28 )
          (*(void (__fastcall **)(const char *))(*(_QWORD *)v28 + 8LL))(v28);
        v29 = Source;
        if ( Source[3] > (void *)7 )
          v29 = (void **)Source[0];
        v30 = -1;
        do
          ++v30;
        while ( *((_WORD *)v29 + v30) != (_WORD)v8 );
        if ( (_DWORD)v30 )
        {
          v8 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)(unsigned int)v30, v27);
          memcpy_s((char *)v8 + 28, 2LL * (unsigned int)v30, v29, 2LL * (unsigned int)v30);
        }
        v90 = (volatile signed __int32 *)v8;
        v31 = WindowsMidiServicesInternal::SafeGetSwdPropertyFromDeviceInformation<winrt::hstring>(
                (volatile signed __int32 **)&lpMem,
                &v90,
                &v82,
                (volatile signed __int32 **)v85);
        std::wstring::operator=<winrt::hstring,0>(&v111, v31);
        v32 = lpMem;
        v8 = 0;
        if ( lpMem )
        {
          v33 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
          if ( v33 )
          {
            if ( v33 < 0 )
              abort();
          }
          else
          {
            ProcessHeap = WINRT_IMPL_GetProcessHeap();
            WINRT_IMPL_HeapFree(ProcessHeap, 0, v32);
          }
          lpMem = 0;
        }
        if ( !v112 )
        {
          v35 = winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Name(
                  v5,
                  &v92);
          std::wstring::operator=<winrt::hstring,0>(&v111, v35);
          v36 = v92;
          if ( v92 )
          {
            v37 = _InterlockedDecrement((volatile signed __int32 *)v92 + 6);
            if ( v37 )
            {
              if ( v37 < 0 )
                abort();
            }
            else
            {
              v38 = WINRT_IMPL_GetProcessHeap();
              WINRT_IMPL_HeapFree(v38, 0, v36);
            }
            v92 = 0;
          }
        }
        v116 = 0;
        v117 = 0;
        v39 = 31;
        if ( v112 < 0x1F )
          v39 = v112;
        v40 = &v111;
        if ( v113 > 7 )
          v40 = (__int128 *)v111;
        std::wstring::_Construct<1,unsigned short const *>((char **)&v116, v40, v39);
        std::wstring::operator=((char **)&v111, (__int64)&v116);
        std::wstring::~wstring((char **)&v116);
        winrt::unbox_value<winrt::Windows::Foundation::IReferenceArray<unsigned char>>(&v84, &v83);
        v82 = 0;
        if ( !winrt::Windows::Foundation::operator==((void (__fastcall ****)(_QWORD, __int64 *, __int64 *))&v84, &v82) )
        {
          winrt::impl::consume_Windows_Foundation_IReferenceArray<winrt::Windows::Foundation::IReferenceArray<unsigned char>,unsigned char>::Value(
            &v84,
            &pv);
          v8 = (struct winrt::impl::shared_hstring_header *)pv;
          v41 = *((unsigned __int8 *)pv + 8);
          if ( v41 < v41 + *((unsigned __int8 *)pv + 9) )
          {
            v42 = v81;
            v43 = (const char **)v100;
            do
            {
              if ( (unsigned __int8)(*((_BYTE *)v8 + 5) - 2) <= 1u )
              {
                if ( v21 )
                  v44 = (const wchar_t *)*((_QWORD *)v21 + 2);
                else
                  v44 = &S2;
                v118 = 0;
                v119 = 0;
                v45 = -1;
                do
                  ++v45;
                while ( v44[v45] );
                std::wstring::_Construct<1,unsigned short const *>((char **)&v118, v44, v45);
                if ( v21 )
                  v46 = (const wchar_t *)*((_QWORD *)v21 + 2);
                else
                  v46 = &S2;
                v116 = 0;
                v117 = 0;
                v47 = -1;
                do
                  ++v47;
                while ( v46[v47] );
                std::wstring::_Construct<1,unsigned short const *>((char **)&v116, v46, v47);
                LOBYTE(v48) = v41;
                WindowsMidiServicesNamingLib::MidiEndpointNameTable::GetSourceEntry(v95, &v102, v48);
                v114 = 0;
                v115 = 0;
                if ( v102 )
                {
                  v49 = (const wchar_t *)(v102 + 8);
                  v50 = -1;
                  do
                    ++v50;
                  while ( v49[v50] );
                }
                else
                {
                  v50 = 0;
                  v49 = &S2;
                }
                std::wstring::_Construct<1,unsigned short const *>((char **)&v114, v49, v50);
                v52 = v103;
                if ( v103 )
                {
                  if ( _InterlockedExchangeAdd(v103 + 2, 0xFFFFFFFF) == 1 )
                  {
                    (**(void (__fastcall ***)(volatile signed __int32 *))v52)(v52);
                    if ( _InterlockedExchangeAdd(v52 + 3, 0xFFFFFFFF) == 1 )
                      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v52 + 8LL))(v52);
                  }
                }
                LOBYTE(v51) = v41;
                WindowsMidiServicesNamingLib::MidiEndpointNameTable::PopulateEntryForNativeUmpDevice(
                  (unsigned int)v108,
                  v51,
                  0,
                  (unsigned int)&v114,
                  (__int64)&v116,
                  (__int64)&v118,
                  (__int64)&v111,
                  v18);
                std::wstring::~wstring((char **)&v114);
                std::wstring::~wstring((char **)&v116);
                std::wstring::~wstring((char **)&v118);
                v53 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
                if ( *v53 > 4u )
                {
                  v56 = (const char *)&v111;
                  if ( v113 > 7 )
                    v56 = (const char *)v111;
                  v82 = v56;
                  v81 = (unsigned __int8)v41;
                  *(_QWORD *)v85 = L"Added midi input port name from function block name";
                  v88 = v43;
                  v89 = (int *)"CMidiDeviceManager::RebuildAndUpdateNameTableForMidi2EndpointWithFunctionBlocks";
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapSz<unsigned short>>(
                    (__int64)v53,
                    (__int64)&word_14008962E,
                    v54,
                    v55,
                    &v89,
                    (__int64)&v88,
                    v85,
                    (__int64)&v81,
                    &v82);
                }
                ++v18;
              }
              if ( ((*((_BYTE *)v8 + 5) - 1) & 0xFD) == 0 )
              {
                if ( v21 )
                  v57 = (const wchar_t *)*((_QWORD *)v21 + 2);
                else
                  v57 = &S2;
                v116 = 0;
                v117 = 0;
                v58 = -1;
                do
                  ++v58;
                while ( v57[v58] );
                std::wstring::_Construct<1,unsigned short const *>((char **)&v116, v57, v58);
                if ( v21 )
                  v59 = (const wchar_t *)*((_QWORD *)v21 + 2);
                else
                  v59 = &S2;
                v118 = 0;
                v119 = 0;
                v60 = -1;
                do
                  ++v60;
                while ( v59[v60] );
                std::wstring::_Construct<1,unsigned short const *>((char **)&v118, v59, v60);
                LOBYTE(v61) = v41;
                WindowsMidiServicesNamingLib::MidiEndpointNameTable::GetDestinationEntry(v95, &v104, v61);
                v114 = 0;
                v115 = 0;
                if ( v104 )
                {
                  v62 = (const wchar_t *)(v104 + 8);
                  v63 = -1;
                  do
                    ++v63;
                  while ( v62[v63] );
                }
                else
                {
                  v63 = 0;
                  v62 = &S2;
                }
                std::wstring::_Construct<1,unsigned short const *>((char **)&v114, v62, v63);
                v65 = v105;
                if ( v105 )
                {
                  if ( _InterlockedExchangeAdd(v105 + 2, 0xFFFFFFFF) == 1 )
                  {
                    (**(void (__fastcall ***)(volatile signed __int32 *))v65)(v65);
                    if ( _InterlockedExchangeAdd(v65 + 3, 0xFFFFFFFF) == 1 )
                      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v65 + 8LL))(v65);
                  }
                }
                LOBYTE(v64) = v41;
                WindowsMidiServicesNamingLib::MidiEndpointNameTable::PopulateEntryForNativeUmpDevice(
                  (unsigned int)v108,
                  v64,
                  1,
                  (unsigned int)&v114,
                  (__int64)&v118,
                  (__int64)&v116,
                  (__int64)&v111,
                  v42);
                std::wstring::~wstring((char **)&v114);
                std::wstring::~wstring((char **)&v118);
                std::wstring::~wstring((char **)&v116);
                v66 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
                if ( *v66 > 4u )
                {
                  v69 = (int *)&v111;
                  if ( v113 > 7 )
                    v69 = (int *)v111;
                  v89 = v69;
                  v81 = (unsigned __int8)v41;
                  v88 = (const char **)L"Added midi input port name from function block name";
                  v82 = (const char *)v43;
                  *(_QWORD *)v85 = "CMidiDeviceManager::RebuildAndUpdateNameTableForMidi2EndpointWithFunctionBlocks";
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapSz<unsigned short>>(
                    (__int64)v66,
                    (__int64)byte_14008A083,
                    v67,
                    v68,
                    v85,
                    (__int64)&v82,
                    &v88,
                    (__int64)&v81,
                    &v89);
                }
                ++v42;
              }
              LOBYTE(v41) = v41 + 1;
            }
            while ( (unsigned __int8)v41 < *((unsigned __int8 *)v8 + 9) + (unsigned int)*((unsigned __int8 *)v8 + 8) );
            LOBYTE(v81) = v42;
            v5 = v101;
            v19 = v86;
          }
          if ( v8 )
          {
            CoTaskMemFree_0(v8);
            v8 = 0;
            pv = 0;
            v107 = 0;
          }
        }
        if ( v84 != v8 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v84);
      }
      if ( v83 != v8 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v83);
      std::wstring::~wstring((char **)&v111);
      std::wstring::~wstring((char **)Source);
      std::wstring::~wstring(v121);
      std::wstring::~wstring((char **)Src);
      v86 = ++v19;
    }
    while ( v19 < v87 );
    v4 = v94;
  }
  v97 = 0;
  v98 = v8;
  if ( !WindowsMidiServicesNamingLib::MidiEndpointNameTable::IsEqualTo(
          (WindowsMidiServicesNamingLib::MidiEndpointNameTable *)v108,
          v95) )
  {
    WindowsMidiServicesNamingLib::MidiEndpointNameTable::WriteProperties(v108, &v97);
    v70 = *(struct winrt::impl::shared_hstring_header ***)(v4 + 24);
    v71 = v70 ? *v70 : v8;
    v72 = SwDeviceInterfacePropertySet(
            v71,
            *(_QWORD *)(v4 + 40),
            0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)&v97 + 1) - v97) >> 4),
            v97);
    v73 = v72;
    if ( v72 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA85,
        (unsigned int)"avcore\\midi2\\service\\exe\\mididevicemanager.cpp",
        (const char *)(unsigned int)v72,
        v80);
      std::vector<_DEVPROPERTY>::~vector<_DEVPROPERTY>((char **)&v97);
      if ( !v21 )
        goto LABEL_120;
      v74 = _InterlockedDecrement((volatile signed __int32 *)v21 + 6);
      if ( !v74 )
      {
        v75 = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(v75, 0, v21);
        goto LABEL_120;
      }
      if ( v74 >= 0 )
      {
LABEL_120:
        WindowsMidiServicesNamingLib::MidiEndpointNameTable::~MidiEndpointNameTable((WindowsMidiServicesNamingLib::MidiEndpointNameTable *)v108);
        v76 = v96;
        if ( v96 )
        {
          if ( _InterlockedExchangeAdd(v96 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v76)(v76);
            if ( _InterlockedExchangeAdd(v76 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v76 + 8LL))(v76);
          }
        }
        if ( *v5 != v8 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v5);
        return v73;
      }
LABEL_138:
      abort();
    }
  }
  std::vector<_DEVPROPERTY>::~vector<_DEVPROPERTY>((char **)&v97);
  if ( v21 )
  {
    v77 = _InterlockedDecrement((volatile signed __int32 *)v21 + 6);
    if ( v77 )
    {
      if ( v77 < 0 )
        goto LABEL_138;
    }
    else
    {
      v78 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v78, 0, v21);
    }
  }
  WindowsMidiServicesNamingLib::MidiEndpointNameTable::~MidiEndpointNameTable((WindowsMidiServicesNamingLib::MidiEndpointNameTable *)v108);
  v79 = v96;
  if ( v96 )
  {
    if ( _InterlockedExchangeAdd(v96 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v79)(v79);
      if ( _InterlockedExchangeAdd(v79 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v79 + 8LL))(v79);
    }
  }
  if ( *v5 != v8 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v5);
  return 0;
}

```

## disassembly

```asm
0x1400318c8  mov     [rsp-8+arg_0], rbx
0x1400318cd  push    rbp
0x1400318ce  push    rsi
0x1400318cf  push    rdi
0x1400318d0  push    r12
0x1400318d2  push    r13
0x1400318d4  push    r14
0x1400318d6  push    r15
0x1400318d8  lea     rbp, [rsp-160h]
0x1400318e0  sub     rsp, 260h
0x1400318e7  mov     rax, cs:__security_cookie
0x1400318ee  xor     rax, rsp
0x1400318f1  mov     [rbp+190h+var_40], rax
0x1400318f8  mov     r14, r9
0x1400318fb  mov     [rbp+190h+var_1E0], r9
0x1400318ff  mov     rsi, r8
0x140031902  mov     [rbp+190h+var_1A0], r8
0x140031906  mov     rbx, rdx
0x140031909  mov     rdi, rcx
0x14003190c  mov     [rbp+190h+var_1A8], rcx
0x140031910  mov     [rbp+190h+var_130], r8
0x140031914  xor     r15d, r15d
0x140031917  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14003191c  mov     rcx, [rax+8]
0x140031920  mov     eax, [rcx]
0x140031922  lea     rdx, aCmidideviceman_4; "CMidiDeviceManager::RebuildAndUpdateNam"...
0x140031929  cmp     eax, 4
0x14003192c  jbe     short loc_140031977
0x14003192e  mov     [rbp+190h+var_1F0], rbx
0x140031932  lea     rax, aEnter; "Enter"
0x140031939  mov     [rbp+190h+lpMem], rax
0x14003193d  mov     [rbp+190h+var_200], rdi
0x140031941  mov     [rsp+290h+var_238], rdx
0x140031946  lea     rax, [rbp+190h+var_1F0]
0x14003194a  mov     [rsp+290h+var_258], rax
0x14003194f  lea     rax, [rbp+190h+lpMem]
0x140031953  mov     [rsp+290h+var_260], rax
0x140031958  lea     rax, [rbp+190h+var_200]
0x14003195c  mov     [rsp+290h+var_268], rax
0x140031961  lea     rax, [rsp+290h+var_238]
0x140031966  mov     qword ptr [rsp+290h+var_270], rax
0x14003196b  lea     rdx, dword_14008A57C
0x140031972  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x140031977  lea     rax, [rsp+290h+var_228]
0x14003197c  mov     [rbp+190h+var_208], rax
0x140031980  mov     rcx, [rsi]
0x140031983  mov     [rsp+290h+var_228], rcx
0x140031988  test    rcx, rcx
0x14003198b  jz      short loc_14003199A
0x14003198d  mov     rax, [rcx]
0x140031990  mov     rax, [rax+8]
0x140031994  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140031999  nop
0x14003199a  mov     ecx, 2Ah ; '*'; this
0x14003199f  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x1400319a4  mov     rbx, rax
0x1400319a7  lea     rcx, [rax+1Ch]; Destination
0x1400319ab  mov     edx, 54h ; 'T'; DestinationSize
0x1400319b0  mov     r9d, edx; SourceSize
0x1400319b3  lea     r8, a3f114a6a11fa4b_2; "{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} "...
0x1400319ba  call    memcpy_s
0x1400319bf  mov     [rsp+290h+var_230], rbx
0x1400319c4  xor     r8d, r8d
0x1400319c7  lea     rdx, [rsp+290h+var_228]
0x1400319cc  lea     rcx, [rsp+290h+var_230]
0x1400319d1  call    ??$SafeGetSwdPropertyFromDeviceInformation@E@WindowsMidiServicesInternal@@YAEUhstring@winrt@@UDeviceInformation@Enumeration@Devices@Windows@2@E@Z; WindowsMidiServicesInternal::SafeGetSwdPropertyFromDeviceInformation<uchar>(winrt::hstring,winrt::Windows::Devices::Enumeration::DeviceInformation,uchar)
0x1400319d6  movzx   ebx, al
0x1400319d9  test    al, al
0x1400319db  jnz     short loc_1400319F4
0x1400319dd  cmp     [rsi], r15
0x1400319e0  jz      short loc_1400319EA
0x1400319e2  mov     rcx, rsi
0x1400319e5  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1400319ea  mov     eax, 80070490h
0x1400319ef  jmp     loc_140032473
0x1400319f4  mov     rdx, rsi
0x1400319f7  lea     rcx, [rbp+190h+var_1D8]
0x1400319fb  call    ?FromDeviceInfo@MidiEndpointNameTable@WindowsMidiServicesNamingLib@@SA?AV?$shared_ptr@VMidiEndpointNameTable@WindowsMidiServicesNamingLib@@@std@@AEBUDeviceInformation@Enumeration@Devices@Windows@winrt@@@Z; WindowsMidiServicesNamingLib::MidiEndpointNameTable::FromDeviceInfo(winrt::Windows::Devices::Enumeration::DeviceInformation const &)
0x140031a00  nop
0x140031a01  xorps   xmm0, xmm0
0x140031a04  xor     eax, eax
0x140031a06  movups  [rbp+190h+var_168], xmm0
0x140031a0a  movups  [rbp+190h+var_158], xmm0
0x140031a0e  movups  [rbp+190h+var_148], xmm0
0x140031a12  mov     [rbp+190h+var_138], rax
0x140031a16  lea     rcx, [rbp+190h+var_168]; this
0x140031a1a  call    ??0MidiEndpointNameTable@WindowsMidiServicesNamingLib@@QEAA@XZ; WindowsMidiServicesNamingLib::MidiEndpointNameTable::MidiEndpointNameTable(void)
0x140031a1f  nop
0x140031a20  lea     rdx, [rbp+190h+var_1B0]
0x140031a24  mov     rcx, rsi
0x140031a27  call    ?Name@?$consume_Windows_Devices_Enumeration_IDeviceInformation@UIDeviceInformation@Enumeration@Devices@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Name(void)
0x140031a2c  nop
0x140031a2d  mov     r12b, r15b
0x140031a30  mov     byte ptr [rsp+290h+var_240], r15b
0x140031a35  mov     r13d, r15d
0x140031a38  mov     [rsp+290h+var_218], r15d
0x140031a3d  mov     eax, ebx
0x140031a3f  mov     [rsp+290h+var_214], ebx
0x140031a43  mov     rbx, [rbp+190h+var_1B0]
0x140031a47  test    eax, eax
0x140031a49  jz      loc_1400322AD
0x140031a4f  cmp     r13d, 20h ; ' '
0x140031a53  jnb     loc_1400322A9
0x140031a59  xorps   xmm0, xmm0
0x140031a5c  movups  [rbp+190h+Src], xmm0
0x140031a63  xorps   xmm1, xmm1
0x140031a66  movdqu  [rbp+190h+var_50], xmm1
0x140031a6e  mov     r8d, 26h ; '&'
0x140031a74  lea     rdx, sz; "{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD}"
0x140031a7b  lea     rcx, [rbp+190h+Src]
0x140031a82  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140031a87  nop
0x140031a88  lea     rdx, asc_14007D9A4; " "
0x140031a8f  lea     rcx, [rbp+190h+Src]; Src
0x140031a96  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator+=(ushort const * const)
0x140031a9b  lea     edx, [r13+0C8h]
0x140031aa2  lea     rcx, [rbp+190h+var_C0]
0x140031aa9  call    ?to_wstring@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@I@Z; std::to_wstring(uint)
0x140031aae  nop
0x140031aaf  mov     r8, rax
0x140031ab2  lea     rdx, [rbp+190h+Src]
0x140031ab9  lea     rcx, [rbp+190h+var_80]
0x140031ac0  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@$$QEAV10@@Z; std::operator+<ushort>(std::wstring const &,std::wstring &&)
0x140031ac5  nop
0x140031ac6  lea     rcx, [rbp+190h+var_C0]; void *
0x140031acd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140031ad2  lea     edx, [r13+12Ch]
0x140031ad9  lea     rcx, [rbp+190h+var_E0]
0x140031ae0  call    ?to_wstring@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@I@Z; std::to_wstring(uint)
0x140031ae5  nop
0x140031ae6  mov     r8, rax
0x140031ae9  lea     rdx, [rbp+190h+Src]
0x140031af0  lea     rcx, [rbp+190h+Source]
0x140031af7  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@$$QEAV10@@Z; std::operator+<ushort>(std::wstring const &,std::wstring &&)
0x140031afc  nop
0x140031afd  lea     rcx, [rbp+190h+var_E0]; void *
0x140031b04  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140031b09  xorps   xmm0, xmm0
0x140031b0c  movups  [rbp+190h+var_120], xmm0
0x140031b10  mov     [rbp+190h+var_110], r15
0x140031b17  mov     [rbp+190h+var_108], 7
0x140031b22  mov     word ptr [rbp+190h+var_120], r15w
0x140031b27  lea     rdx, [rbp+190h+var_1E8]
0x140031b2b  mov     rcx, rsi
0x140031b2e  call    ?Properties@?$consume_Windows_Devices_Enumeration_IDeviceInformation@UIDeviceInformation@Enumeration@Devices@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Properties(void)
0x140031b33  mov     r9, rax
0x140031b36  lea     rdx, [rbp+190h+var_80]
0x140031b3d  cmp     [rbp+190h+var_68], 7
0x140031b45  cmova   rdx, [rbp+190h+var_80]
0x140031b4d  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140031b51  inc     rcx
0x140031b54  cmp     [rdx+rcx*2], r15w
0x140031b59  jnz     short loc_140031B51
0x140031b5b  test    ecx, ecx
0x140031b5d  jnz     short loc_140031B68
0x140031b5f  mov     qword ptr [rbp+190h+var_100], r15
0x140031b66  jmp     short loc_140031B9A
0x140031b68  mov     eax, ecx
0x140031b6a  cmp     [rdx+rax*2], r15w
0x140031b6f  jnz     loc_1400322F7
0x140031b75  mov     dword ptr [rbp+190h+var_100+8], 1
0x140031b7f  mov     dword ptr [rbp+190h+var_100+0Ch], ecx
0x140031b85  mov     [rbp+190h+var_E8], rdx
0x140031b8c  lea     rax, [rbp+190h+var_100+8]
0x140031b93  mov     qword ptr [rbp+190h+var_100], rax
0x140031b9a  lea     r8, [rbp+190h+var_100]
0x140031ba1  lea     rdx, [rsp+290h+var_230]
0x140031ba6  mov     rcx, r9
0x140031ba9  call    ?Lookup@?$consume_Windows_Foundation_Collections_IMapView@U?$IMapView@Uhstring@winrt@@UIInspectable@Foundation@Windows@2@@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMapView<winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Windows::Foundation::IInspectable>,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(winrt::param::hstring const &)
0x140031bae  nop
0x140031baf  cmp     [rbp+190h+var_1E8], r15
0x140031bb3  jz      short loc_140031BBE
0x140031bb5  lea     rcx, [rbp+190h+var_1E8]
0x140031bb9  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x140031bbe  mov     [rsp+290h+var_238], r15
0x140031bc3  lea     rdx, [rsp+290h+var_238]
0x140031bc8  lea     rcx, [rsp+290h+var_230]
0x140031bcd  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x140031bd2  test    al, al
0x140031bd4  jnz     loc_140032254
0x140031bda  lea     rax, [rsp+290h+var_220]
0x140031bdf  mov     [rbp+190h+var_208], rax
0x140031be3  mov     qword ptr [rsp+290h+var_220], r15
0x140031be8  lea     rax, [rsp+290h+var_238]
0x140031bed  mov     [rbp+190h+var_210], rax
0x140031bf1  mov     rcx, [rsi]
0x140031bf4  mov     [rsp+290h+var_238], rcx
0x140031bf9  test    rcx, rcx
0x140031bfc  jz      short loc_140031C0B
0x140031bfe  mov     rax, [rcx]
0x140031c01  mov     rax, [rax+8]
0x140031c05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140031c0a  nop
0x140031c0b  lea     r14, [rbp+190h+Source]
0x140031c12  cmp     [rbp+190h+var_88], 7
0x140031c1a  cmova   r14, [rbp+190h+Source]
0x140031c22  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140031c26  inc     rdi
0x140031c29  cmp     [r14+rdi*2], r15w
0x140031c2e  jnz     short loc_140031C26
0x140031c30  test    edi, edi
0x140031c32  jz      short loc_140031C52
0x140031c34  mov     ecx, edi; this
0x140031c36  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x140031c3b  mov     r15, rax
0x140031c3e  mov     edx, edi
0x140031c40  add     rdx, rdx; DestinationSize
0x140031c43  lea     rcx, [rax+1Ch]; Destination
0x140031c47  mov     r9, rdx; SourceSize
0x140031c4a  mov     r8, r14; Source
0x140031c4d  call    memcpy_s
0x140031c52  mov     [rbp+190h+var_200], r15
0x140031c56  lea     r9, [rsp+290h+var_220]
0x140031c5b  lea     r8, [rsp+290h+var_238]
0x140031c60  lea     rdx, [rbp+190h+var_200]
0x140031c64  lea     rcx, [rbp+190h+lpMem]
0x140031c68  call    ??$SafeGetSwdPropertyFromDeviceInformation@Uhstring@winrt@@@WindowsMidiServicesInternal@@YA?AUhstring@winrt@@U12@UDeviceInformation@Enumeration@Devices@Windows@2@0@Z; WindowsMidiServicesInternal::SafeGetSwdPropertyFromDeviceInformation<winrt::hstring>(winrt::hstring,winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::hstring)
0x140031c6d  nop
0x140031c6e  mov     rdx, rax
0x140031c71  lea     rcx, [rbp+190h+var_120]
0x140031c75  call    ??$?4Uhstring@winrt@@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBUhstring@winrt@@@Z; std::wstring::operator=<winrt::hstring,0>(winrt::hstring const &)
0x140031c7a  nop
0x140031c7b  mov     rdi, [rbp+190h+lpMem]
0x140031c7f  xor     r15d, r15d
0x140031c82  test    rdi, rdi
0x140031c85  jz      short loc_140031CB5
0x140031c87  or      eax, 0FFFFFFFFh
0x140031c8a  lock xadd [rdi+18h], eax
0x140031c8f  sub     eax, 1
0x140031c92  jnz     short loc_140031CA9
0x140031c94  nop
0x140031c95  call    WINRT_IMPL_GetProcessHeap
0x140031c9a  mov     rcx, rax; hHeap
0x140031c9d  mov     r8, rdi; lpMem
0x140031ca0  xor     edx, edx; dwFlags
0x140031ca2  call    WINRT_IMPL_HeapFree
0x140031ca7  jmp     short loc_140031CB1
0x140031ca9  test    eax, eax
0x140031cab  js      loc_1400322E9
0x140031cb1  mov     [rbp+190h+lpMem], r15
0x140031cb5  cmp     [rbp+190h+var_110], r15
0x140031cbc  jnz     short loc_140031D0F
0x140031cbe  lea     rdx, [rbp+190h+var_1F0]
0x140031cc2  mov     rcx, rsi
0x140031cc5  call    ?Name@?$consume_Windows_Devices_Enumeration_IDeviceInformation@UIDeviceInformation@Enumeration@Devices@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Name(void)
0x140031cca  nop
0x140031ccb  mov     rdx, rax
0x140031cce  lea     rcx, [rbp+190h+var_120]
0x140031cd2  call    ??$?4Uhstring@winrt@@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBUhstring@winrt@@@Z; std::wstring::operator=<winrt::hstring,0>(winrt::hstring const &)
0x140031cd7  nop
0x140031cd8  mov     rdi, [rbp+190h+var_1F0]
0x140031cdc  test    rdi, rdi
0x140031cdf  jz      short loc_140031D0F
0x140031ce1  or      eax, 0FFFFFFFFh
0x140031ce4  lock xadd [rdi+18h], eax
0x140031ce9  sub     eax, 1
0x140031cec  jnz     short loc_140031D03
0x140031cee  nop
0x140031cef  call    WINRT_IMPL_GetProcessHeap
0x140031cf4  mov     rcx, rax; hHeap
0x140031cf7  mov     r8, rdi; lpMem
0x140031cfa  xor     edx, edx; dwFlags
0x140031cfc  call    WINRT_IMPL_HeapFree
0x140031d01  jmp     short loc_140031D0B
0x140031d03  test    eax, eax
0x140031d05  js      loc_1400322F0
0x140031d0b  mov     [rbp+190h+var_1F0], r15
0x140031d0f  xorps   xmm0, xmm0
0x140031d12  movups  [rbp+190h+var_E0], xmm0
0x140031d19  xorps   xmm1, xmm1
0x140031d1c  movdqu  [rbp+190h+var_D0], xmm1
0x140031d24  mov     r8d, 1Fh
0x140031d2a  cmp     [rbp+190h+var_110], r8
0x140031d31  cmovb   r8, [rbp+190h+var_110]
0x140031d39  lea     rdx, [rbp+190h+var_120]
0x140031d3d  cmp     [rbp+190h+var_108], 7
0x140031d45  cmova   rdx, qword ptr [rbp+190h+var_120]
0x140031d4a  lea     rcx, [rbp+190h+var_E0]
0x140031d51  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140031d56  lea     rdx, [rbp+190h+var_E0]
0x140031d5d  lea     rcx, [rbp+190h+var_120]
0x140031d61  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x140031d66  lea     rcx, [rbp+190h+var_E0]; void *
0x140031d6d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140031d72  lea     rdx, [rsp+290h+var_230]
0x140031d77  lea     rcx, [rsp+290h+var_228]
0x140031d7c  call    ??$unbox_value@U?$IReferenceArray@E@Foundation@Windows@winrt@@@winrt@@YA?AU?$IReferenceArray@E@Foundation@Windows@0@AEBUIInspectable@230@@Z; winrt::unbox_value<winrt::Windows::Foundation::IReferenceArray<uchar>>(winrt::Windows::Foundation::IInspectable const &)
0x140031d81  nop
0x140031d82  mov     [rsp+290h+var_238], r15
0x140031d87  lea     rdx, [rsp+290h+var_238]
0x140031d8c  lea     rcx, [rsp+290h+var_228]
0x140031d91  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x140031d96  test    al, al
0x140031d98  jnz     loc_140032242
0x140031d9e  lea     rdx, [rbp+190h+pv]
0x140031da2  lea     rcx, [rsp+290h+var_228]
0x140031da7  call    ?Value@?$consume_Windows_Foundation_IReferenceArray@U?$IReferenceArray@E@Foundation@Windows@winrt@@E@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IReferenceArray<winrt::Windows::Foundation::IReferenceArray<uchar>,uchar>::Value(void)
0x140031dac  nop
0x140031dad  mov     r15, [rbp+190h+pv]
0x140031db1  movzx   r14d, byte ptr [r15+8]
  ... truncated ...
```
