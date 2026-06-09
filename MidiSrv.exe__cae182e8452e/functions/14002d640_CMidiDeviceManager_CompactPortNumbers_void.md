# CMidiDeviceManager::CompactPortNumbers(void)

- ea: `0x14002d640`
- end: `0x14002dde0`
- name: `?CompactPortNumbers@CMidiDeviceManager@@AEAAJXZ`
- size: `1952`
- prototype: `__int64 __fastcall(CMidiDeviceManager *__hidden this)`
- caller_count: `2`
- callee_count: `32`
- tags: `service_task, broker_com_uri`

## callers

- `0x14002ddf0`
- `0x140032ff4`

## callees

- `0x1400018e4`
- `0x1400054c0`
- `0x1400054e4`
- `0x14000617c`
- `0x1400061e8`
- `0x1400072d4`
- `0x140007c20`
- `0x14000984c`
- `0x14000a6b4`
- `0x14000c7f4`
- `0x14000ca00`
- `0x14000cc2c`
- `0x14000cd78`
- `0x140012008`
- `0x1400133f0`
- `0x140013a38`
- `0x1400140c4`
- `0x140014f04`
- `0x14001dccc`
- `0x14001f95c`
- `0x140026754`
- `0x140026ce8`
- `0x1400274d8`
- `0x140028ab8`
- `0x140028c74`
- `0x140029350`
- `0x14002d640`
- `0x14002ed48`
- `0x140030a98`
- `0x140035858`
- `0x140035970`
- `0x14005a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x14002dd19`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x14002dd20`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x14002ddc6`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x14002ddcd`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x14002dd19`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x14002dd20`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x14002ddc6`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x14002ddcd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14002dcee`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14002ddb7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14002dcee`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14002ddb7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14002d6dc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14002d6dc`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceInterfacePropertySet` at `0x14002dc28`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceInterfacePropertySet` at `0x14002dc28`

## string_xrefs

- `0x14002dd31`: `avcore\midi2\service\exe\mididevicemanager.cpp`
- `0x14002d6a0`: `CMidiDeviceManager::CompactPortNumbers`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
__int64 __fastcall CMidiDeviceManager::CompactPortNumbers(CMidiDeviceManager *this)
{
  unsigned int v2; // esi
  _DWORD *v3; // rcx
  __int64 v4; // r8
  __int64 v5; // r9
  struct _RTL_CRITICAL_SECTION *v6; // rbx
  __int64 *v7; // rax
  int v8; // ebx
  _QWORD *v9; // rax
  unsigned int v10; // edx
  const wchar_t *v11; // r14
  __int64 v12; // rbx
  struct winrt::impl::shared_hstring_header *v13; // rdi
  __int64 v14; // rbx
  const wchar_t *v15; // r15
  int v16; // esi
  struct winrt::impl::shared_hstring_header *v17; // r14
  rsize_t v18; // rbx
  int v19; // eax
  HANDLE ProcessHeap; // rax
  __int64 AllAsync; // rax
  __int64 v22; // rax
  unsigned int v23; // r12d
  unsigned int v24; // edi
  int v25; // esi
  int v26; // eax
  unsigned int v27; // edx
  volatile signed __int32 *v28; // rbx
  __int64 v29; // rbx
  __int64 v30; // rax
  void *v31; // rbx
  int v32; // eax
  HANDLE v33; // rax
  unsigned int v34; // eax
  unsigned int v35; // r15d
  __int64 *v36; // r8
  __int64 *v37; // rcx
  __int64 *v38; // rdx
  __int64 v39; // rax
  __int64 v40; // rax
  CMidiDeviceManager *v41; // rax
  __int64 v42; // rbx
  __int64 v43; // rdi
  _WORD *v44; // rdx
  unsigned __int64 v45; // r8
  __int64 v46; // rax
  const wchar_t *p_S2; // rdx
  const wchar_t *v48; // rcx
  bool v49; // r15
  void *v50; // rdx
  __int64 *v51; // rcx
  __int64 v52; // rcx
  int v53; // eax
  unsigned int v54; // ebx
  int v55; // eax
  HANDLE v56; // rax
  signed __int32 v58; // r13d
  HANDLE v59; // rax
  int v60; // [rsp+20h] [rbp-E0h]
  __int64 v61; // [rsp+40h] [rbp-C0h] BYREF
  int v62; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int SwdPropertyFromDevice; // [rsp+4Ch] [rbp-B4h] BYREF
  __int64 v64; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v65; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v66; // [rsp+60h] [rbp-A0h] BYREF
  CMidiDeviceManager *v67; // [rsp+68h] [rbp-98h]
  const char *v68; // [rsp+70h] [rbp-90h] BYREF
  LPVOID lpMem; // [rsp+78h] [rbp-88h] BYREF
  __int64 *v70; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v71[2]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v72; // [rsp+98h] [rbp-68h] BYREF
  _QWORD v73[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v74; // [rsp+B0h] [rbp-50h] BYREF
  char v75; // [rsp+B8h] [rbp-48h]
  struct winrt::impl::shared_hstring_header *v76; // [rsp+C0h] [rbp-40h]
  __int128 v77; // [rsp+C8h] [rbp-38h] BYREF
  int v78; // [rsp+D8h] [rbp-28h]
  int v79; // [rsp+DCh] [rbp-24h]
  __int64 v80; // [rsp+E0h] [rbp-20h]
  int v81; // [rsp+E8h] [rbp-18h]
  int v82; // [rsp+ECh] [rbp-14h]
  __int64 *v83; // [rsp+F0h] [rbp-10h]
  struct _RTL_CRITICAL_SECTION *v84; // [rsp+F8h] [rbp-8h]
  __int64 *v85; // [rsp+100h] [rbp+0h]
  _BYTE v86[8]; // [rsp+108h] [rbp+8h] BYREF
  int v87; // [rsp+110h] [rbp+10h]
  struct winrt::impl::shared_hstring_header *v88; // [rsp+118h] [rbp+18h] BYREF
  wchar_t *S1[2]; // [rsp+138h] [rbp+38h] BYREF
  size_t N; // [rsp+148h] [rbp+48h]
  unsigned __int64 v91; // [rsp+150h] [rbp+50h]
  wchar_t *S2; // [rsp+158h] [rbp+58h] BYREF
  _DWORD v93[2]; // [rsp+160h] [rbp+60h] BYREF
  __int64 v94; // [rsp+168h] [rbp+68h]
  const wchar_t *v95; // [rsp+170h] [rbp+70h]
  __int128 v96; // [rsp+178h] [rbp+78h] BYREF
  __int64 v97; // [rsp+188h] [rbp+88h]
  __int64 v98; // [rsp+190h] [rbp+90h]
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+E8h]

  v67 = this;
  v2 = 0;
  LODWORD(v61) = 0;
  v3 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v3 > 4u )
  {
    v70 = (__int64 *)L"Enter";
    lpMem = this;
    v68 = "CMidiDeviceManager::CompactPortNumbers";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
      (__int64)v3,
      (__int64)&word_140088DDE,
      v4,
      v5,
      &v68,
      (__int64)&lpMem,
      &v70);
  }
  v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 96);
  EnterCriticalSection(v6);
  v84 = v6;
  v72 = 1;
  v7 = &v72;
  v70 = &v72;
LABEL_4:
  v8 = *(_DWORD *)v7;
  v71[0] = 0;
  v71[1] = 0;
  v9 = operator new(0x48u);
  *v9 = v9;
  v9[1] = v9;
  v9[2] = v9;
  *((_WORD *)v9 + 12) = 257;
  v71[0] = v9;
  v11 = L"System.Devices.InterfaceClassGuid:=\"{6DC23320-AB33-4CE4-80D4-BBB3EBBF2814}\"";
  if ( v8 != 1 )
    v11 = L"System.Devices.InterfaceClassGuid:=\"{504BE32C-CCF6-4D2C-B73F-6F8B3747E22B}\"";
  v12 = -1;
  do
    ++v12;
  while ( v11[v12] );
  if ( (_DWORD)v12 )
  {
    v13 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)(unsigned int)v12, v10);
    memcpy_s((char *)v13 + 28, 2LL * (unsigned int)v12, v11, 2LL * (unsigned int)v12);
  }
  else
  {
    v13 = 0;
  }
  v76 = v13;
  if ( v13 )
  {
    v14 = *((unsigned int *)v13 + 1);
    v15 = (const wchar_t *)*((_QWORD *)v13 + 2);
  }
  else
  {
    v15 = &::S2;
    v14 = 0;
  }
  v16 = v2 | 2;
  if ( (_DWORD)v14 == -77 )
  {
    v17 = 0;
  }
  else
  {
    v17 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)(unsigned int)(v14 + 77), v10);
    v18 = 2 * v14;
    memcpy_s(*((void *const *)v17 + 2), v18, v15, v18);
    memcpy_s(
      (void *const)(v18 + *((_QWORD *)v17 + 2)),
      0x9Au,
      L" AND System.Devices.InterfaceEnabled:=System.StructuredQueryType.Boolean#True",
      0x9Au);
  }
  v2 = v16 | 1;
  if ( v13 )
  {
    v19 = _InterlockedDecrement((volatile signed __int32 *)v13 + 6);
    if ( v19 )
    {
      if ( v19 < 0 )
        abort();
    }
    else
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, v13);
    }
  }
  v76 = v17;
  *(_OWORD *)S1 = 0;
  N = 0;
  winrt::single_threaded_vector<winrt::hstring,std::allocator<winrt::hstring>>(&v66, (__int64 *)S1);
  std::vector<winrt::hstring>::~vector<winrt::hstring>((__int64)S1);
  v93[0] = 1;
  v93[1] = 41;
  v95 = L"{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} 17";
  S2 = (wchar_t *)v93;
  winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::Append(
    &v66,
    &S2);
  winrt::param::async_iterable<winrt::hstring>::async_iterable<winrt::hstring>(&v74, &v66);
  v88 = v17;
  AllAsync = winrt::Windows::Devices::Enumeration::DeviceInformation::FindAllAsync(v73, &v88, &v74);
  winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Devices::Enumeration::DeviceInformationCollection>,winrt::Windows::Devices::Enumeration::DeviceInformationCollection>::get(
    AllAsync,
    &v65);
  if ( v73[0] )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v73);
  if ( v75 )
  {
    v22 = v74;
  }
  else
  {
    v22 = 0;
    v74 = 0;
  }
  if ( v22 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v74);
  v23 = 1;
  v24 = 0;
  winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Devices::Enumeration::DeviceInformation>,winrt::Windows::Devices::Enumeration::DeviceInformation>::end(
    &v65,
    v86);
  while ( v24 != v87 )
  {
    v64 = 0;
    v25 = v2 | 8;
    LODWORD(v61) = v25;
    LODWORD(S1[0]) = 494;
    S1[1] = (wchar_t *)"onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Foundation.Collections.h";
    N = 0;
    v26 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v65 + 48LL))(v65, v24, &v64);
    if ( v26 < 0 )
      winrt::throw_hresult((unsigned int)v26, S1);
    v2 = v25 & 0xFFFFFFF3 | 4;
    v85 = &v61;
    v61 = v64;
    if ( v64 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 8LL))(v64);
    v28 = (volatile signed __int32 *)winrt::impl::precreate_hstring_on_heap((winrt::impl *)0x29, v27);
    memcpy_s((void *const)(v28 + 7), 0x52u, L"{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} 17", 0x52u);
    v68 = (const char *)v28;
    SwdPropertyFromDevice = WindowsMidiServicesInternal::SafeGetSwdPropertyFromDeviceInformation<unsigned int>(
                              (volatile signed __int32 **)&v68,
                              &v61);
    if ( SwdPropertyFromDevice )
    {
      v29 = winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Id(
              &v64,
              &lpMem);
      v30 = std::map<unsigned int,std::wstring>::operator[](v71, &SwdPropertyFromDevice);
      std::wstring::operator=<winrt::hstring,0>(v30, v29);
      v31 = lpMem;
      if ( lpMem )
      {
        v32 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
        if ( v32 )
        {
          if ( v32 < 0 )
            abort();
        }
        else
        {
          v33 = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(v33, 0, v31);
        }
        lpMem = 0;
      }
      if ( SwdPropertyFromDevice > v23 )
        v23 = SwdPropertyFromDevice;
    }
    if ( v64 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v64);
    ++v24;
  }
  v34 = 1;
  v62 = 1;
  v35 = 1;
  LODWORD(v61) = 1;
  v36 = (__int64 *)v71[0];
  while ( 1 )
  {
    while ( 1 )
    {
      v37 = (__int64 *)v36[1];
      HIDWORD(S1[1]) = 0;
      v38 = v36;
      while ( !*((_BYTE *)v37 + 25) )
      {
        if ( *((_DWORD *)v37 + 8) >= v34 )
        {
          v38 = v37;
          v37 = (__int64 *)*v37;
        }
        else
        {
          v37 = (__int64 *)v37[2];
        }
      }
      if ( *((_BYTE *)v38 + 25) || v34 < *((_DWORD *)v38 + 8) )
        v38 = v36;
      if ( v38 != v36 || v34 > v23 )
        break;
      v62 = ++v34;
    }
    if ( v34 <= v35 )
      goto LABEL_81;
    v39 = std::map<unsigned int,std::wstring>::operator[](v71, &v62);
    v40 = std::wstring::wstring((__int64)&v96, v39);
    WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(&S2, v40);
    v2 |= 0x10u;
    v41 = v67;
    v42 = *((_QWORD *)v67 + 18);
    v43 = *((_QWORD *)v67 + 17);
    if ( v43 != v42 )
    {
      do
      {
        v44 = *(_WORD **)(*(_QWORD *)v43 + 40LL);
        v96 = 0;
        v97 = 0;
        v98 = 0;
        v45 = -1;
        do
          ++v45;
        while ( v44[v45] );
        std::wstring::_Construct<1,unsigned short const *>((char **)&v96, v44, v45);
        v46 = std::wstring::wstring((__int64)&v77, (__int64)&v96);
        WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(S1, v46);
        v2 |= 0x20u;
        p_S2 = (const wchar_t *)&S2;
        if ( (unsigned __int64)v95 > 7 )
          p_S2 = S2;
        v48 = (const wchar_t *)S1;
        if ( v91 > 7 )
          v48 = S1[0];
        if ( N == v94 )
        {
          if ( N )
            v49 = wmemcmp(v48, p_S2, N) == 0;
          else
            v49 = 1;
        }
        else
        {
          v49 = 0;
        }
        std::wstring::~wstring((char **)S1);
        std::wstring::~wstring((char **)&v96);
        if ( v49 )
          break;
        v43 += 8;
      }
      while ( v43 != v42 );
      v35 = v61;
      v41 = v67;
    }
    if ( v43 != *((_QWORD *)v41 + 18) )
      break;
LABEL_80:
    std::wstring::~wstring((char **)&S2);
    v36 = (__int64 *)v71[0];
    v34 = v62;
LABEL_81:
    LODWORD(v61) = ++v35;
    v62 = ++v34;
    if ( v34 > v23 )
    {
      if ( v65 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v65);
      if ( v66 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v66);
      if ( v17 )
      {
        v55 = _InterlockedDecrement((volatile signed __int32 *)v17 + 6);
        if ( v55 )
        {
          if ( v55 < 0 )
            abort();
        }
        else
        {
          v56 = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(v56, 0, v17);
        }
      }
      std::_Tree<std::_Tmap_traits<unsigned int,std::wstring,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<unsigned int,std::wstring,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,std::wstring>>,0>>(v71);
      v7 = (__int64 *)((char *)v70 + 4);
      v70 = v7;
      if ( v7 == v73 )
      {
        if ( v67 != (CMidiDeviceManager *)-96LL )
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v67 + 96));
        return 0;
      }
      goto LABEL_4;
    }
  }
  LODWORD(v61) = v35;
  *(_OWORD *)S1 = 0;
  N = 0;
  v77 = PKEY_MIDI_ServiceAssignedPortNumber;
  v78 = 17;
  v79 = 0;
  v80 = 0;
  v81 = 7;
  v82 = 4;
  v83 = &v61;
  std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(S1, 0, &v77);
  v50 = &S2;
  if ( (unsigned __int64)v95 > 7 )
    v50 = S2;
  v51 = *(__int64 **)(*(_QWORD *)v43 + 24LL);
  if ( v51 )
    v52 = *v51;
  else
    v52 = 0;
  v53 = SwDeviceInterfacePropertySet(v52, v50, 0xAAAAAAAAAAAAAAABuLL * (((char *)S1[1] - (char *)S1[0]) >> 4), S1[0]);
  v54 = v53;
  if ( v53 >= 0 )
  {
    std::vector<_DEVPROPERTY>::~vector<_DEVPROPERTY>((char **)S1);
    goto LABEL_80;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x8A2,
    (unsigned int)"avcore\\midi2\\service\\exe\\mididevicemanager.cpp",
    (const char *)(unsigned int)v53,
    v60);
  std::vector<_DEVPROPERTY>::~vector<_DEVPROPERTY>((char **)S1);
  std::wstring::~wstring((char **)&S2);
  if ( v65 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v65);
  if ( v66 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v66);
  if ( v17 )
  {
    v58 = _InterlockedExchangeAdd((volatile signed __int32 *)v17 + 6, 0xFFFFFFFF);
    if ( v58 == 1 )
    {
      v59 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v59, 0, v17);
    }
    else if ( v58 - 1 < 0 )
    {
      abort();
    }
  }
  std::_Tree<std::_Tmap_traits<unsigned int,std::wstring,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<unsigned int,std::wstring,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,std::wstring>>,0>>(v71);
  if ( v67 != (CMidiDeviceManager *)-96LL )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v67 + 96));
  return v54;
}

```

## disassembly

```asm
0x14002d640  push    rbp
0x14002d642  push    rbx
0x14002d643  push    rsi
0x14002d644  push    rdi
0x14002d645  push    r12
0x14002d647  push    r13
0x14002d649  push    r14
0x14002d64b  push    r15
0x14002d64d  lea     rbp, [rsp-0A8h]
0x14002d655  sub     rsp, 1A8h
0x14002d65c  mov     rax, cs:__security_cookie
0x14002d663  xor     rax, rsp
0x14002d666  mov     [rbp+0E0h+var_48], rax
0x14002d66d  mov     rbx, rcx
0x14002d670  mov     [rsp+1E0h+var_178], rcx
0x14002d675  xor     r12d, r12d
0x14002d678  mov     esi, r12d
0x14002d67b  mov     dword ptr [rsp+1E0h+var_1A0], r12d
0x14002d680  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14002d685  mov     rcx, [rax+8]
0x14002d689  mov     eax, [rcx]
0x14002d68b  cmp     eax, 4
0x14002d68e  jbe     short loc_14002D6D5
0x14002d690  lea     rax, aEnter; "Enter"
0x14002d697  mov     [rbp+0E0h+var_160], rax
0x14002d69b  mov     [rsp+1E0h+lpMem], rbx
0x14002d6a0  lea     rax, aCmidideviceman_5; "CMidiDeviceManager::CompactPortNumbers"
0x14002d6a7  mov     [rsp+1E0h+var_170], rax
0x14002d6ac  lea     rax, [rbp+0E0h+var_160]
0x14002d6b0  mov     [rsp+1E0h+var_1B0], rax
0x14002d6b5  lea     rax, [rsp+1E0h+lpMem]
0x14002d6ba  mov     [rsp+1E0h+var_1B8], rax
0x14002d6bf  lea     rax, [rsp+1E0h+var_170]
0x14002d6c4  mov     [rsp+1E0h+var_1C0], rax
0x14002d6c9  lea     rdx, word_140088DDE
0x14002d6d0  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x14002d6d5  add     rbx, 60h ; '`'
0x14002d6d9  mov     rcx, rbx; lpCriticalSection
0x14002d6dc  call    cs:__imp_EnterCriticalSection
0x14002d6e2  mov     [rbp+0E0h+var_E8], rbx
0x14002d6e6  mov     [rbp+0E0h+var_148], 1
0x14002d6ee  lea     rax, [rbp+0E0h+var_148]
0x14002d6f2  mov     [rbp+0E0h+var_160], rax
0x14002d6f6  or      r13, 0FFFFFFFFFFFFFFFFh
0x14002d6fa  mov     ebx, [rax]
0x14002d6fc  mov     [rbp+0E0h+var_158], r12
0x14002d700  mov     [rbp+0E0h+var_150], r12
0x14002d704  mov     ecx, 48h ; 'H'; Size
0x14002d709  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14002d70e  mov     [rax], rax
0x14002d711  mov     [rax+8], rax
0x14002d715  mov     [rax+10h], rax
0x14002d719  mov     word ptr [rax+18h], 101h
0x14002d71f  mov     [rbp+0E0h+var_158], rax
0x14002d723  lea     rax, aSystemDevicesI_1; "System.Devices.InterfaceClassGuid:=\"{5"...
0x14002d72a  lea     r14, aSystemDevicesI_0; "System.Devices.InterfaceClassGuid:=\"{6"...
0x14002d731  cmp     ebx, 1
0x14002d734  cmovnz  r14, rax
0x14002d738  mov     rbx, r13
0x14002d73b  inc     rbx
0x14002d73e  cmp     [r14+rbx*2], r12w
0x14002d743  jnz     short loc_14002D73B
0x14002d745  test    ebx, ebx
0x14002d747  jnz     short loc_14002D74E
0x14002d749  mov     rdi, r12
0x14002d74c  jmp     short loc_14002D76C
0x14002d74e  mov     ecx, ebx; this
0x14002d750  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x14002d755  mov     rdi, rax
0x14002d758  mov     edx, ebx
0x14002d75a  add     rdx, rdx; DestinationSize
0x14002d75d  lea     rcx, [rax+1Ch]; Destination
0x14002d761  mov     r9, rdx; SourceSize
0x14002d764  mov     r8, r14; Source
0x14002d767  call    memcpy_s
0x14002d76c  mov     [rbp+0E0h+var_120], rdi
0x14002d770  test    rdi, rdi
0x14002d773  jz      short loc_14002D77E
0x14002d775  mov     ebx, [rdi+4]
0x14002d778  mov     r15, [rdi+10h]
0x14002d77c  jmp     short loc_14002D788
0x14002d77e  lea     r15, S2
0x14002d785  mov     rbx, r12
0x14002d788  lea     ecx, [rbx+4Dh]; this
0x14002d78b  or      esi, 2
0x14002d78e  test    ecx, ecx
0x14002d790  jnz     short loc_14002D797
0x14002d792  mov     r14, r12
0x14002d795  jmp     short loc_14002D7D1
0x14002d797  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x14002d79c  mov     r14, rax
0x14002d79f  add     rbx, rbx
0x14002d7a2  mov     r9, rbx; SourceSize
0x14002d7a5  mov     r8, r15; Source
0x14002d7a8  mov     rdx, rbx; DestinationSize
0x14002d7ab  mov     rcx, [rax+10h]; Destination
0x14002d7af  call    memcpy_s
0x14002d7b4  mov     rcx, [r14+10h]
0x14002d7b8  add     rcx, rbx; Destination
0x14002d7bb  mov     eax, 9Ah
0x14002d7c0  mov     r9d, eax; SourceSize
0x14002d7c3  lea     r8, aAndSystemDevic; " AND System.Devices.InterfaceEnabled:=S"...
0x14002d7ca  mov     edx, eax; DestinationSize
0x14002d7cc  call    memcpy_s
0x14002d7d1  or      esi, 1
0x14002d7d4  test    rdi, rdi
0x14002d7d7  jz      short loc_14002D803
0x14002d7d9  mov     eax, r13d
0x14002d7dc  lock xadd [rdi+18h], eax
0x14002d7e1  sub     eax, 1
0x14002d7e4  jnz     short loc_14002D7FB
0x14002d7e6  nop
0x14002d7e7  call    WINRT_IMPL_GetProcessHeap
0x14002d7ec  mov     rcx, rax; hHeap
0x14002d7ef  mov     r8, rdi; lpMem
0x14002d7f2  xor     edx, edx; dwFlags
0x14002d7f4  call    WINRT_IMPL_HeapFree
0x14002d7f9  jmp     short loc_14002D803
0x14002d7fb  test    eax, eax
0x14002d7fd  js      loc_14002DD19
0x14002d803  mov     [rbp+0E0h+var_120], r14
0x14002d807  xorps   xmm0, xmm0
0x14002d80a  movdqu  xmmword ptr [rbp+0E0h+S1], xmm0
0x14002d80f  mov     [rbp+0E0h+N], r12
0x14002d813  lea     rdx, [rbp+0E0h+S1]
0x14002d817  lea     rcx, [rsp+1E0h+var_180]
0x14002d81c  call    ??$single_threaded_vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@winrt@@YA?AU?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@0@$$QEAV?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@@Z; winrt::single_threaded_vector<winrt::hstring,std::allocator<winrt::hstring>>(std::vector<winrt::hstring> &&)
0x14002d821  nop
0x14002d822  lea     rcx, [rbp+0E0h+S1]
0x14002d826  call    ??1?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@QEAA@XZ; std::vector<winrt::hstring>::~vector<winrt::hstring>(void)
0x14002d82b  mov     [rbp+0E0h+var_80], 1
0x14002d832  mov     [rbp+0E0h+var_7C], 29h ; ')'
0x14002d839  lea     rax, a3f114a6a11fa4b_0; "{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} "...
0x14002d840  mov     [rbp+0E0h+var_70], rax
0x14002d844  lea     rax, [rbp+0E0h+var_80]
0x14002d848  mov     [rbp+0E0h+S2], rax
0x14002d84c  lea     rdx, [rbp+0E0h+S2]
0x14002d850  lea     rcx, [rsp+1E0h+var_180]
0x14002d855  call    ?Append@?$consume_Windows_Foundation_Collections_IVector@U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@winrt@@Uhstring@5@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::Append(winrt::param::hstring const &)
0x14002d85a  lea     rdx, [rsp+1E0h+var_180]
0x14002d85f  lea     rcx, [rbp+0E0h+var_130]
0x14002d863  call    ??$?0U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@winrt@@$0A@@?$async_iterable@Uhstring@winrt@@@param@winrt@@QEAA@AEBU?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@2@@Z; winrt::param::async_iterable<winrt::hstring>::async_iterable<winrt::hstring>(winrt::Windows::Foundation::Collections::IVector<winrt::hstring> const &)
0x14002d868  nop
0x14002d869  mov     [rbp+0E0h+var_C8], r14
0x14002d86d  lea     r8, [rbp+0E0h+var_130]
0x14002d871  lea     rdx, [rbp+0E0h+var_C8]
0x14002d875  lea     rcx, [rbp+0E0h+var_140]
0x14002d879  call    ?FindAllAsync@DeviceInformation@Enumeration@Devices@Windows@winrt@@SA@AEBUhstring@param@5@AEBU?$async_iterable@Uhstring@winrt@@@75@@Z; winrt::Windows::Devices::Enumeration::DeviceInformation::FindAllAsync(winrt::param::hstring const &,winrt::param::async_iterable<winrt::hstring> const &)
0x14002d87e  nop
0x14002d87f  lea     rdx, [rsp+1E0h+var_188]
0x14002d884  mov     rcx, rax
0x14002d887  call    ?get@?$consume_Windows_Foundation_IAsyncOperation@U?$IAsyncOperation@UDeviceInformationCollection@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@UDeviceInformationCollection@Enumeration@Devices@34@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Devices::Enumeration::DeviceInformationCollection>,winrt::Windows::Devices::Enumeration::DeviceInformationCollection>::get(void)
0x14002d88c  nop
0x14002d88d  cmp     [rbp+0E0h+var_140], r12
0x14002d891  jz      short loc_14002D89D
0x14002d893  lea     rcx, [rbp+0E0h+var_140]
0x14002d897  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x14002d89c  nop
0x14002d89d  cmp     [rbp+0E0h+var_128], r12b
0x14002d8a1  jnz     short loc_14002D8AC
0x14002d8a3  mov     rax, r12
0x14002d8a6  mov     [rbp+0E0h+var_130], rax
0x14002d8aa  jmp     short loc_14002D8B0
0x14002d8ac  mov     rax, [rbp+0E0h+var_130]
0x14002d8b0  test    rax, rax
0x14002d8b3  jz      short loc_14002D8BE
0x14002d8b5  lea     rcx, [rbp+0E0h+var_130]
0x14002d8b9  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x14002d8be  mov     r12d, 1
0x14002d8c4  xor     r15d, r15d
0x14002d8c7  mov     edi, r15d
0x14002d8ca  lea     rdx, [rbp+0E0h+var_D8]
0x14002d8ce  lea     rcx, [rsp+1E0h+var_188]
0x14002d8d3  call    ?end@?$consume_Windows_Foundation_Collections_IIterable@U?$IVectorView@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Collections@Foundation@Windows@winrt@@UDeviceInformation@Enumeration@Devices@45@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Devices::Enumeration::DeviceInformation>,winrt::Windows::Devices::Enumeration::DeviceInformation>::end(void)
0x14002d8d8  cmp     edi, [rbp+0E0h+var_D0]
0x14002d8db  jz      loc_14002DA1D
0x14002d8e1  mov     [rsp+1E0h+var_190], r15
0x14002d8e6  or      esi, 8
0x14002d8e9  mov     dword ptr [rsp+1E0h+var_1A0], esi
0x14002d8ed  mov     rcx, [rsp+1E0h+var_188]
0x14002d8f2  mov     dword ptr [rbp+0E0h+S1], 1EEh
0x14002d8f9  lea     rax, aOnecoreuapInte_1; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x14002d900  mov     [rbp+0E0h+S1+8], rax
0x14002d904  mov     [rbp+0E0h+N], r15
0x14002d908  mov     rax, [rcx]
0x14002d90b  lea     r8, [rsp+1E0h+var_190]
0x14002d910  mov     edx, edi
0x14002d912  mov     rax, [rax+30h]
0x14002d916  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002d91b  test    eax, eax
0x14002d91d  js      loc_14002DDD4
0x14002d923  and     esi, 0FFFFFFF7h
0x14002d926  mov     dword ptr [rsp+1E0h+var_1A0], esi
0x14002d92a  or      esi, 4
0x14002d92d  lea     rax, [rsp+1E0h+var_1A0]
0x14002d932  mov     [rbp+0E0h+var_E0], rax
0x14002d936  mov     rcx, [rsp+1E0h+var_190]
0x14002d93b  mov     [rsp+1E0h+var_1A0], rcx
0x14002d940  test    rcx, rcx
0x14002d943  jz      short loc_14002D952
0x14002d945  mov     rax, [rcx]
0x14002d948  mov     rax, [rax+8]
0x14002d94c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002d951  nop
0x14002d952  mov     ecx, 29h ; ')'; this
0x14002d957  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x14002d95c  mov     rbx, rax
0x14002d95f  lea     rcx, [rax+1Ch]; Destination
0x14002d963  mov     eax, 52h ; 'R'
0x14002d968  mov     r9d, eax; SourceSize
0x14002d96b  lea     r8, a3f114a6a11fa4b_0; "{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} "...
0x14002d972  mov     edx, eax; DestinationSize
0x14002d974  call    memcpy_s
0x14002d979  mov     [rsp+1E0h+var_170], rbx
0x14002d97e  lea     rdx, [rsp+1E0h+var_1A0]
0x14002d983  lea     rcx, [rsp+1E0h+var_170]
0x14002d988  call    ??$SafeGetSwdPropertyFromDeviceInformation@I@WindowsMidiServicesInternal@@YAIUhstring@winrt@@UDeviceInformation@Enumeration@Devices@Windows@2@I@Z; WindowsMidiServicesInternal::SafeGetSwdPropertyFromDeviceInformation<uint>(winrt::hstring,winrt::Windows::Devices::Enumeration::DeviceInformation,uint)
0x14002d98d  mov     [rsp+1E0h+var_194], eax
0x14002d991  test    eax, eax
0x14002d993  jz      short loc_14002DA05
0x14002d995  lea     rdx, [rsp+1E0h+lpMem]
0x14002d99a  lea     rcx, [rsp+1E0h+var_190]
0x14002d99f  call    ?Id@?$consume_Windows_Devices_Enumeration_IDeviceInformation@UIDeviceInformation@Enumeration@Devices@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Id(void)
0x14002d9a4  mov     rbx, rax
0x14002d9a7  lea     rdx, [rsp+1E0h+var_194]
0x14002d9ac  lea     rcx, [rbp+0E0h+var_158]
0x14002d9b0  call    ??A?$map@IV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@I@2@V?$allocator@U?$pair@$$CBIV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@AEBI@Z; std::map<uint,std::wstring>::operator[](uint const &)
0x14002d9b5  mov     rcx, rax
0x14002d9b8  mov     rdx, rbx
0x14002d9bb  call    ??$?4Uhstring@winrt@@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBUhstring@winrt@@@Z; std::wstring::operator=<winrt::hstring,0>(winrt::hstring const &)
0x14002d9c0  nop
0x14002d9c1  mov     rbx, [rsp+1E0h+lpMem]
0x14002d9c6  test    rbx, rbx
0x14002d9c9  jz      short loc_14002D9FA
0x14002d9cb  mov     eax, r13d
0x14002d9ce  lock xadd [rbx+18h], eax
0x14002d9d3  sub     eax, 1
0x14002d9d6  jnz     short loc_14002D9ED
0x14002d9d8  nop
0x14002d9d9  call    WINRT_IMPL_GetProcessHeap
0x14002d9de  mov     rcx, rax; hHeap
0x14002d9e1  mov     r8, rbx; lpMem
0x14002d9e4  xor     edx, edx; dwFlags
0x14002d9e6  call    WINRT_IMPL_HeapFree
0x14002d9eb  jmp     short loc_14002D9F5
0x14002d9ed  test    eax, eax
0x14002d9ef  js      loc_14002DD20
0x14002d9f5  mov     [rsp+1E0h+lpMem], r15
0x14002d9fa  cmp     [rsp+1E0h+var_194], r12d
0x14002d9ff  cmova   r12d, [rsp+1E0h+var_194]
0x14002da05  cmp     [rsp+1E0h+var_190], r15
0x14002da0a  jz      short loc_14002DA16
0x14002da0c  lea     rcx, [rsp+1E0h+var_190]
0x14002da11  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x14002da16  inc     edi
0x14002da18  jmp     loc_14002D8D8
0x14002da1d  mov     eax, 1
0x14002da22  mov     [rsp+1E0h+var_198], eax
0x14002da26  mov     r15d, eax
0x14002da29  mov     dword ptr [rsp+1E0h+var_1A0], eax
0x14002da2d  mov     r8, [rbp+0E0h+var_158]
0x14002da31  xor     edi, edi
0x14002da33  mov     rcx, [r8+8]
0x14002da37  xor     edx, edx
0x14002da39  mov     dword ptr [rbp+0E0h+S1+0Ch], edx
0x14002da3c  mov     rdx, r8
0x14002da3f  jmp     short loc_14002DA52
0x14002da41  cmp     [rcx+20h], eax
0x14002da44  jnb     short loc_14002DA4C
0x14002da46  mov     rcx, [rcx+10h]
0x14002da4a  jmp     short loc_14002DA52
0x14002da4c  mov     rdx, rcx
0x14002da4f  mov     rcx, [rcx]
0x14002da52  cmp     [rcx+19h], dil
0x14002da56  jz      short loc_14002DA41
0x14002da58  cmp     [rdx+19h], dil
0x14002da5c  jnz     short loc_14002DA63
0x14002da5e  cmp     eax, [rdx+20h]
0x14002da61  jnb     short loc_14002DA66
0x14002da63  mov     rdx, r8
0x14002da66  cmp     rdx, r8
0x14002da69  jnz     short loc_14002DA78
0x14002da6b  cmp     eax, r12d
0x14002da6e  ja      short loc_14002DA78
0x14002da70  inc     eax
0x14002da72  mov     [rsp+1E0h+var_198], eax
0x14002da76  jmp     short loc_14002DA33
0x14002da78  cmp     eax, r15d
0x14002da7b  jbe     loc_14002DC53
0x14002da81  lea     rdx, [rsp+1E0h+var_198]
0x14002da86  lea     rcx, [rbp+0E0h+var_158]
0x14002da8a  call    ??A?$map@IV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@I@2@V?$allocator@U?$pair@$$CBIV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@AEBI@Z; std::map<uint,std::wstring>::operator[](uint const &)
0x14002da8f  mov     rdx, rax
0x14002da92  lea     rcx, [rbp+0E0h+var_68]
0x14002da96  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14002da9b  mov     rdx, rax
0x14002da9e  lea     rcx, [rbp+0E0h+S2]
0x14002daa2  call    ?ToLowerTrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(std::wstring)
0x14002daa7  or      esi, 10h
0x14002daaa  mov     rax, [rsp+1E0h+var_178]
  ... truncated ...
```
