# CMidiDeviceManager::AssignPortNumber(HSWDEVICE__ *,ushort *,__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0002)

- ea: `0x14002ce1c`
- end: `0x14002d639`
- name: `?AssignPortNumber@CMidiDeviceManager@@AEAAJPEAUHSWDEVICE__@@PEAGW4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0002@@@Z`
- size: `2077`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `32`
- tags: `service_task, broker_com_uri`

## callers

- `0x14002b1a0`
- `0x140032ff4`

## callees

- `0x140001ce8`
- `0x140005190`
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
- `0x140026ce8`
- `0x1400274d8`
- `0x140028a1c`
- `0x140028c74`
- `0x14002924c`
- `0x14002ce1c`
- `0x14002ed48`
- `0x140030a98`
- `0x140035858`
- `0x140035970`
- `0x14005a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x14002d0fe`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x14002d438`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x14002d43f`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x14002d446`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x14002d626`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x14002d0fe`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x14002d438`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x14002d43f`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x14002d446`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x14002d626`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceInterfacePropertySet` at `0x14002d4f6`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceInterfacePropertySet` at `0x14002d4f6`

## string_xrefs

- `0x14002d510`: `avcore\midi2\service\exe\mididevicemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=23
__int64 __fastcall CMidiDeviceManager::AssignPortNumber(void *a1, __int64 a2, void *a3, int a4)
{
  _DWORD *v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  unsigned __int64 v10; // r8
  __int64 v11; // rax
  _QWORD *v12; // rax
  unsigned int v13; // edx
  const wchar_t *v14; // r14
  __int64 v15; // rbx
  struct winrt::impl::shared_hstring_header *v16; // rdi
  __int64 v17; // rbx
  const wchar_t *v18; // r15
  struct winrt::impl::shared_hstring_header *v19; // r14
  rsize_t v20; // rbx
  int v21; // r12d
  int v22; // eax
  HANDLE ProcessHeap; // rax
  __int64 AllAsync; // rax
  __int64 v25; // rax
  unsigned int v26; // r13d
  int v27; // r12d
  int v28; // eax
  unsigned int v29; // r12d
  __int64 v30; // rax
  const wchar_t *v31; // rdx
  unsigned __int64 v32; // r8
  __int64 v33; // rax
  void *v34; // rbx
  int v35; // eax
  HANDLE v36; // rax
  size_t v37; // r8
  wchar_t **v38; // rdi
  wchar_t *v39; // rax
  unsigned __int64 v40; // rcx
  size_t v41; // rbx
  __int64 v42; // rax
  wchar_t **v43; // rdi
  char *v44; // rbx
  __int64 v45; // rax
  const wchar_t *v46; // rdx
  wchar_t **v47; // r9
  volatile signed __int32 *v48; // rbx
  volatile signed __int32 **v49; // rbx
  volatile signed __int32 **v50; // rax
  volatile signed __int32 **v51; // rdi
  volatile signed __int32 *v52; // r15
  volatile signed __int32 *v53; // rbx
  int v54; // ecx
  HANDLE v55; // rax
  void *v56; // rbx
  int v57; // eax
  HANDLE v58; // rax
  unsigned int i; // edx
  __int64 *v60; // rax
  __int64 *v61; // rcx
  int v62; // eax
  unsigned int v63; // ebx
  int v64; // esi
  HANDLE v65; // rax
  int v67; // esi
  HANDLE v68; // rax
  int v69; // [rsp+20h] [rbp-E0h]
  __int64 v70; // [rsp+40h] [rbp-C0h] BYREF
  const char *v71; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v72; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v73; // [rsp+58h] [rbp-A8h] BYREF
  LPVOID lpMem; // [rsp+60h] [rbp-A0h] BYREF
  const wchar_t *v75; // [rsp+68h] [rbp-98h] BYREF
  LPVOID v76; // [rsp+70h] [rbp-90h] BYREF
  int SwdPropertyFromDevice; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v78; // [rsp+7Ch] [rbp-84h] BYREF
  _QWORD v79[2]; // [rsp+80h] [rbp-80h] BYREF
  struct winrt::impl::shared_hstring_header *v80; // [rsp+90h] [rbp-70h]
  void *v81; // [rsp+98h] [rbp-68h]
  __int64 v82; // [rsp+A0h] [rbp-60h]
  __int128 v83; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v84; // [rsp+B8h] [rbp-48h]
  __int128 v85; // [rsp+C0h] [rbp-40h] BYREF
  int v86; // [rsp+D0h] [rbp-30h]
  int v87; // [rsp+D4h] [rbp-2Ch]
  __int64 v88; // [rsp+D8h] [rbp-28h]
  int v89; // [rsp+E0h] [rbp-20h]
  int v90; // [rsp+E4h] [rbp-1Ch]
  unsigned int *v91; // [rsp+E8h] [rbp-18h]
  __int64 *v92; // [rsp+F0h] [rbp-10h]
  __int128 v93; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v94; // [rsp+108h] [rbp+8h]
  __int64 v95; // [rsp+110h] [rbp+10h]
  __int128 v96; // [rsp+118h] [rbp+18h] BYREF
  __int64 v97; // [rsp+128h] [rbp+28h]
  const wchar_t *v98; // [rsp+130h] [rbp+30h]
  wchar_t *S1[2]; // [rsp+138h] [rbp+38h] BYREF
  size_t N; // [rsp+148h] [rbp+48h]
  unsigned __int64 v101; // [rsp+150h] [rbp+50h]
  wchar_t *S2[4]; // [rsp+158h] [rbp+58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]

  v81 = a3;
  v82 = a2;
  LODWORD(v72) = 0;
  v7 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v7 > 4u )
  {
    v76 = a3;
    v75 = L"Enter";
    lpMem = a1;
    v71 = "CMidiDeviceManager::AssignPortNumber";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (__int64)v7,
      (__int64)byte_140089A71,
      v8,
      v9,
      &v71,
      (__int64)&lpMem,
      &v75,
      &v76);
  }
  v96 = 0;
  v97 = 0;
  v98 = 0;
  v10 = -1;
  do
    ++v10;
  while ( *((_WORD *)a3 + v10) );
  std::wstring::_Construct<1,unsigned short const *>((char **)&v96, a3, v10);
  v11 = std::wstring::wstring((__int64)&v93, (__int64)&v96);
  WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(S2, v11);
  std::wstring::~wstring((char **)&v96);
  v79[0] = 0;
  v79[1] = 0;
  v12 = operator new(0x30u);
  *v12 = v12;
  v12[1] = v12;
  v12[2] = v12;
  *((_WORD *)v12 + 12) = 257;
  v79[0] = v12;
  v14 = L"System.Devices.InterfaceClassGuid:=\"{6DC23320-AB33-4CE4-80D4-BBB3EBBF2814}\"";
  if ( a4 != 1 )
    v14 = L"System.Devices.InterfaceClassGuid:=\"{504BE32C-CCF6-4D2C-B73F-6F8B3747E22B}\"";
  v15 = -1;
  do
    ++v15;
  while ( v14[v15] );
  if ( (_DWORD)v15 )
  {
    v16 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)(unsigned int)v15, v13);
    memcpy_s((char *)v16 + 28, 2LL * (unsigned int)v15, v14, 2LL * (unsigned int)v15);
  }
  else
  {
    v16 = 0;
  }
  v80 = v16;
  if ( v16 )
  {
    v17 = *((unsigned int *)v16 + 1);
    v18 = (const wchar_t *)*((_QWORD *)v16 + 2);
  }
  else
  {
    v18 = &::S2;
    v17 = 0;
  }
  if ( (_DWORD)v17 == -77 )
  {
    v19 = 0;
  }
  else
  {
    v19 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)(unsigned int)(v17 + 77), v13);
    v20 = 2 * v17;
    memcpy_s(*((void *const *)v19 + 2), v20, v18, v20);
    memcpy_s(
      (void *const)(v20 + *((_QWORD *)v19 + 2)),
      0x9Au,
      L" AND System.Devices.InterfaceEnabled:=System.StructuredQueryType.Boolean#True",
      0x9Au);
  }
  v21 = 7;
  if ( v16 )
  {
    v22 = _InterlockedDecrement((volatile signed __int32 *)v16 + 6);
    if ( v22 )
    {
      if ( v22 < 0 )
        abort();
    }
    else
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, v16);
    }
  }
  v80 = v19;
  v96 = 0;
  v97 = 0;
  winrt::single_threaded_vector<winrt::hstring,std::allocator<winrt::hstring>>(&v71, (__int64 *)&v96);
  std::vector<winrt::hstring>::~vector<winrt::hstring>((__int64)&v96);
  *((_QWORD *)&v96 + 1) = 0x2900000001LL;
  v98 = L"{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} 17";
  *(_QWORD *)&v96 = (char *)&v96 + 8;
  winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::Append(
    &v71,
    &v96);
  winrt::param::async_iterable<winrt::hstring>::async_iterable<winrt::hstring>(&v93, &v71);
  *(_QWORD *)&v85 = v19;
  AllAsync = winrt::Windows::Devices::Enumeration::DeviceInformation::FindAllAsync(&v70, &v85, &v93);
  winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Devices::Enumeration::DeviceInformationCollection>,winrt::Windows::Devices::Enumeration::DeviceInformationCollection>::get(
    AllAsync,
    &v73);
  if ( v70 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v70);
  if ( BYTE8(v93) )
  {
    v25 = v93;
  }
  else
  {
    v25 = 0;
    *(_QWORD *)&v93 = 0;
  }
  if ( v25 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v93);
  v26 = 0;
  winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Devices::Enumeration::DeviceInformation>,winrt::Windows::Devices::Enumeration::DeviceInformation>::end(
    &v73,
    &v96);
  while ( v26 != DWORD2(v96) )
  {
    v70 = 0;
    v27 = v21 | 0x10;
    LODWORD(v72) = v27;
    LODWORD(v93) = 494;
    *((_QWORD *)&v93 + 1) = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Foundation.Collections.h";
    v94 = 0;
    v28 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v73 + 48LL))(v73, v26, &v70);
    if ( v28 < 0 )
      winrt::throw_hresult((unsigned int)v28, &v93);
    v29 = v27 & 0xFFFFFFE7 | 8;
    LODWORD(v72) = v29;
    v30 = winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Id(
            &v70,
            &lpMem);
    if ( *(_QWORD *)v30 )
      v31 = *(const wchar_t **)(*(_QWORD *)v30 + 16LL);
    else
      v31 = &::S2;
    v93 = 0;
    v94 = 0;
    v95 = 0;
    v32 = -1;
    do
      ++v32;
    while ( v31[v32] );
    std::wstring::_Construct<1,unsigned short const *>((char **)&v93, v31, v32);
    v33 = std::wstring::wstring((__int64)&v85, (__int64)&v93);
    WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(S1, v33);
    v21 = v29 | 0x20;
    std::wstring::~wstring((char **)&v93);
    v34 = lpMem;
    if ( lpMem )
    {
      v35 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
      if ( v35 )
      {
        if ( v35 < 0 )
          abort();
      }
      else
      {
        v36 = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(v36, 0, v34);
      }
      lpMem = 0;
    }
    v37 = N;
    v38 = S1;
    v39 = S1[0];
    v40 = v101;
    if ( v101 > 7 )
      v38 = (wchar_t **)S1[0];
    if ( N >= 7 )
    {
      v41 = (size_t)v38 + 2 * N;
      v42 = _std_search_2(v38, v41, L".ble10#", 7);
      if ( v42 != v41 && ((v42 - (_QWORD)v38) & 0xFFFFFFFFFFFFFFFEuLL) != 0xFFFFFFFFFFFFFFFEuLL )
        goto LABEL_62;
      v40 = v101;
      v37 = N;
      v39 = S1[0];
    }
    v43 = S1;
    if ( v40 > 7 )
      v43 = (wchar_t **)v39;
    if ( v37 >= 0x1B )
    {
      v44 = (char *)v43 + 2 * v37;
      v45 = _std_search_2(v43, v44, L"#microsoftgswavetablesynth#", 27);
      if ( (char *)v45 != v44 && ((v45 - (_QWORD)v43) & 0xFFFFFFFFFFFFFFFEuLL) != 0xFFFFFFFFFFFFFFFEuLL )
        goto LABEL_62;
      v40 = v101;
      v37 = N;
      v39 = S1[0];
    }
    v46 = (const wchar_t *)S2;
    if ( S2[3] > (wchar_t *)7 )
      v46 = S2[0];
    v47 = S1;
    if ( v40 > 7 )
      v47 = (wchar_t **)v39;
    if ( (wchar_t *)v37 != S2[2] || v37 && wmemcmp((const wchar_t *)v47, v46, v37) )
    {
      v92 = &v72;
      v72 = v70;
      if ( v70 )
        (*(void (__fastcall **)(__int64, const wchar_t *, size_t, wchar_t **))(*(_QWORD *)v70 + 8LL))(
          v70,
          v46,
          v37,
          v47);
      v48 = (volatile signed __int32 *)winrt::impl::precreate_hstring_on_heap((winrt::impl *)0x29, (unsigned int)v46);
      memcpy_s((void *const)(v48 + 7), 0x52u, L"{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} 17", 0x52u);
      v75 = (const wchar_t *)v48;
      SwdPropertyFromDevice = WindowsMidiServicesInternal::SafeGetSwdPropertyFromDeviceInformation<unsigned int>(
                                (volatile signed __int32 **)&v75,
                                &v72);
      if ( SwdPropertyFromDevice )
      {
        v49 = (volatile signed __int32 **)winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Id(
                                            &v70,
                                            &v76);
        v50 = (volatile signed __int32 **)std::map<unsigned int,winrt::hstring>::operator[](v79, &SwdPropertyFromDevice);
        v51 = v50;
        if ( v50 != v49 )
        {
          v52 = *v49;
          *v49 = 0;
          v53 = *v50;
          if ( *v50 )
          {
            v54 = _InterlockedDecrement(v53 + 6);
            if ( v54 )
            {
              if ( v54 < 0 )
                abort();
            }
            else
            {
              v55 = WINRT_IMPL_GetProcessHeap();
              WINRT_IMPL_HeapFree(v55, 0, (LPVOID)v53);
            }
          }
          *v51 = v52;
        }
        v56 = v76;
        if ( v76 )
        {
          v57 = _InterlockedDecrement((volatile signed __int32 *)v76 + 6);
          if ( v57 )
          {
            if ( v57 < 0 )
              abort();
          }
          else
          {
            v58 = WINRT_IMPL_GetProcessHeap();
            WINRT_IMPL_HeapFree(v58, 0, v56);
          }
          v76 = 0;
        }
      }
    }
LABEL_62:
    std::wstring::~wstring((char **)S1);
    if ( v70 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v70);
    ++v26;
  }
  for ( i = 1; ; ++i )
  {
    v60 = *(__int64 **)(v79[0] + 8LL);
    HIDWORD(v96) = 0;
    v61 = (__int64 *)v79[0];
    while ( !*((_BYTE *)v60 + 25) )
    {
      if ( *((_DWORD *)v60 + 8) >= i )
      {
        v61 = v60;
        v60 = (__int64 *)*v60;
      }
      else
      {
        v60 = (__int64 *)v60[2];
      }
    }
    if ( *((_BYTE *)v61 + 25) || i < *((_DWORD *)v61 + 8) )
      v61 = (__int64 *)v79[0];
    if ( v61 == (__int64 *)v79[0] )
      break;
  }
  v78 = i;
  v83 = 0;
  v84 = 0;
  v85 = PKEY_MIDI_ServiceAssignedPortNumber;
  v86 = 17;
  v87 = 0;
  v88 = 0;
  v89 = 7;
  v90 = 4;
  v91 = &v78;
  std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(&v83, 0, &v85);
  v62 = SwDeviceInterfacePropertySet(v82, v81, 1, v83);
  v63 = v62;
  if ( v62 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x90A,
      (unsigned int)"avcore\\midi2\\service\\exe\\mididevicemanager.cpp",
      (const char *)(unsigned int)v62,
      v69);
    std::vector<_DEVPROPERTY>::~vector<_DEVPROPERTY>((char **)&v83);
    if ( v73 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v73);
    if ( v71 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v71);
    if ( !v19 )
      goto LABEL_102;
    v64 = _InterlockedDecrement((volatile signed __int32 *)v19 + 6);
    if ( !v64 )
    {
      v65 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v65, 0, v19);
      goto LABEL_102;
    }
    if ( v64 >= 0 )
    {
LABEL_102:
      std::_Tree<std::_Tmap_traits<unsigned int,winrt::hstring,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,winrt::hstring>>,0>>::~_Tree<std::_Tmap_traits<unsigned int,winrt::hstring,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,winrt::hstring>>,0>>(v79);
      std::wstring::~wstring((char **)S2);
      return v63;
    }
LABEL_112:
    abort();
  }
  std::vector<_DEVPROPERTY>::~vector<_DEVPROPERTY>((char **)&v83);
  if ( v73 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v73);
  if ( v71 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v71);
  if ( v19 )
  {
    v67 = _InterlockedDecrement((volatile signed __int32 *)v19 + 6);
    if ( v67 )
    {
      if ( v67 < 0 )
        goto LABEL_112;
    }
    else
    {
      v68 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v68, 0, v19);
    }
  }
  std::_Tree<std::_Tmap_traits<unsigned int,winrt::hstring,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,winrt::hstring>>,0>>::~_Tree<std::_Tmap_traits<unsigned int,winrt::hstring,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,winrt::hstring>>,0>>(v79);
  std::wstring::~wstring((char **)S2);
  return 0;
}

```

## disassembly

```asm
0x14002ce1c  mov     [rsp-8+arg_0], rbx
0x14002ce21  push    rbp
0x14002ce22  push    rsi
0x14002ce23  push    rdi
0x14002ce24  push    r12
0x14002ce26  push    r13
0x14002ce28  push    r14
0x14002ce2a  push    r15
0x14002ce2c  lea     rbp, [rsp-80h]
0x14002ce31  sub     rsp, 180h
0x14002ce38  mov     rax, cs:__security_cookie
0x14002ce3f  xor     rax, rsp
0x14002ce42  mov     [rbp+0B0h+var_38], rax
0x14002ce46  mov     edi, r9d
0x14002ce49  mov     r14, r8
0x14002ce4c  mov     [rbp+0B0h+var_118], r8
0x14002ce50  mov     [rbp+0B0h+var_110], rdx
0x14002ce54  mov     rbx, rcx
0x14002ce57  xor     r12d, r12d
0x14002ce5a  mov     dword ptr [rsp+1B0h+var_160], r12d
0x14002ce5f  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14002ce64  mov     rcx, [rax+8]
0x14002ce68  mov     eax, [rcx]
0x14002ce6a  cmp     eax, 4
0x14002ce6d  jbe     short loc_14002CEC5
0x14002ce6f  mov     [rsp+1B0h+var_140], r14
0x14002ce74  lea     rax, aEnter; "Enter"
0x14002ce7b  mov     [rsp+1B0h+var_148], rax
0x14002ce80  mov     [rsp+1B0h+lpMem], rbx
0x14002ce85  lea     rax, aCmidideviceman_2; "CMidiDeviceManager::AssignPortNumber"
0x14002ce8c  mov     [rsp+1B0h+var_168], rax
0x14002ce91  lea     rax, [rsp+1B0h+var_140]
0x14002ce96  mov     [rsp+1B0h+var_178], rax
0x14002ce9b  lea     rax, [rsp+1B0h+var_148]
0x14002cea0  mov     [rsp+1B0h+var_180], rax
0x14002cea5  lea     rax, [rsp+1B0h+lpMem]
0x14002ceaa  mov     [rsp+1B0h+var_188], rax
0x14002ceaf  lea     rax, [rsp+1B0h+var_168]
0x14002ceb4  mov     [rsp+1B0h+var_190], rax
0x14002ceb9  lea     rdx, byte_140089A71
0x14002cec0  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x14002cec5  xorps   xmm0, xmm0
0x14002cec8  movups  [rbp+0B0h+var_98], xmm0
0x14002cecc  mov     [rbp+0B0h+var_88], r12
0x14002ced0  mov     [rbp+0B0h+var_80], r12
0x14002ced4  or      rsi, 0FFFFFFFFFFFFFFFFh
0x14002ced8  mov     r8, rsi
0x14002cedb  inc     r8
0x14002cede  cmp     [r14+r8*2], r12w
0x14002cee3  jnz     short loc_14002CEDB
0x14002cee5  mov     rdx, r14
0x14002cee8  lea     rcx, [rbp+0B0h+var_98]
0x14002ceec  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14002cef1  nop
0x14002cef2  lea     rdx, [rbp+0B0h+var_98]
0x14002cef6  lea     rcx, [rbp+0B0h+var_B8]
0x14002cefa  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14002ceff  mov     rdx, rax
0x14002cf02  lea     rcx, [rbp+0B0h+S2]
0x14002cf06  call    ?ToLowerTrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(std::wstring)
0x14002cf0b  nop
0x14002cf0c  lea     rcx, [rbp+0B0h+var_98]; void *
0x14002cf10  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14002cf15  mov     [rbp+0B0h+var_130], r12
0x14002cf19  mov     [rbp+0B0h+var_128], r12
0x14002cf1d  mov     ecx, 30h ; '0'; Size
0x14002cf22  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14002cf27  mov     [rax], rax
0x14002cf2a  mov     [rax+8], rax
0x14002cf2e  mov     [rax+10h], rax
0x14002cf32  mov     word ptr [rax+18h], 101h
0x14002cf38  mov     [rbp+0B0h+var_130], rax
0x14002cf3c  lea     rax, aSystemDevicesI_1; "System.Devices.InterfaceClassGuid:=\"{5"...
0x14002cf43  lea     r14, aSystemDevicesI_0; "System.Devices.InterfaceClassGuid:=\"{6"...
0x14002cf4a  cmp     edi, 1
0x14002cf4d  cmovnz  r14, rax
0x14002cf51  mov     rbx, rsi
0x14002cf54  inc     rbx
0x14002cf57  cmp     [r14+rbx*2], r12w
0x14002cf5c  jnz     short loc_14002CF54
0x14002cf5e  test    ebx, ebx
0x14002cf60  jnz     short loc_14002CF67
0x14002cf62  mov     rdi, r12
0x14002cf65  jmp     short loc_14002CF85
0x14002cf67  mov     ecx, ebx; this
0x14002cf69  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x14002cf6e  mov     rdi, rax
0x14002cf71  mov     edx, ebx
0x14002cf73  add     rdx, rdx; DestinationSize
0x14002cf76  lea     rcx, [rax+1Ch]; Destination
0x14002cf7a  mov     r9, rdx; SourceSize
0x14002cf7d  mov     r8, r14; Source
0x14002cf80  call    memcpy_s
0x14002cf85  mov     [rbp+0B0h+var_120], rdi
0x14002cf89  test    rdi, rdi
0x14002cf8c  jz      short loc_14002CF97
0x14002cf8e  mov     ebx, [rdi+4]
0x14002cf91  mov     r15, [rdi+10h]
0x14002cf95  jmp     short loc_14002CFA1
0x14002cf97  lea     r15, S2
0x14002cf9e  mov     rbx, r12
0x14002cfa1  lea     ecx, [rbx+4Dh]; this
0x14002cfa4  test    ecx, ecx
0x14002cfa6  jnz     short loc_14002CFB0
0x14002cfa8  xor     r15d, r15d
0x14002cfab  mov     r14d, r15d
0x14002cfae  jmp     short loc_14002CFEB
0x14002cfb0  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x14002cfb5  mov     r14, rax
0x14002cfb8  add     rbx, rbx
0x14002cfbb  mov     r9, rbx; SourceSize
0x14002cfbe  mov     r8, r15; Source
0x14002cfc1  mov     rdx, rbx; DestinationSize
0x14002cfc4  mov     rcx, [rax+10h]; Destination
0x14002cfc8  call    memcpy_s
0x14002cfcd  mov     rcx, [r14+10h]
0x14002cfd1  add     rcx, rbx; Destination
0x14002cfd4  mov     edx, 9Ah; DestinationSize
0x14002cfd9  mov     r9d, edx; SourceSize
0x14002cfdc  lea     r8, aAndSystemDevic; " AND System.Devices.InterfaceEnabled:=S"...
0x14002cfe3  call    memcpy_s
0x14002cfe8  xor     r15d, r15d
0x14002cfeb  mov     r12d, 7
0x14002cff1  test    rdi, rdi
0x14002cff4  jz      short loc_14002D04A
0x14002cff6  mov     eax, esi
0x14002cff8  lock xadd [rdi+18h], eax
0x14002cffd  sub     eax, 1
0x14002d000  jnz     short loc_14002D017
0x14002d002  nop
0x14002d003  call    WINRT_IMPL_GetProcessHeap
0x14002d008  mov     rcx, rax; hHeap
0x14002d00b  mov     r8, rdi; lpMem
0x14002d00e  xor     edx, edx; dwFlags
0x14002d010  call    WINRT_IMPL_HeapFree
0x14002d015  jmp     short loc_14002D01F
0x14002d017  test    eax, eax
0x14002d019  js      loc_14002D0FE
0x14002d01f  mov     rdi, r15
0x14002d022  test    r15, r15
0x14002d025  jz      short loc_14002D04A
0x14002d027  mov     eax, esi
0x14002d029  lock xadd [rdi+18h], eax
0x14002d02e  sub     eax, 1
0x14002d031  jnz     loc_14002D0F6
0x14002d037  nop
0x14002d038  call    WINRT_IMPL_GetProcessHeap
0x14002d03d  mov     rcx, rax; hHeap
0x14002d040  mov     r8, r15; lpMem
0x14002d043  xor     edx, edx; dwFlags
0x14002d045  call    WINRT_IMPL_HeapFree
0x14002d04a  mov     [rbp+0B0h+var_120], r14
0x14002d04e  xorps   xmm0, xmm0
0x14002d051  movdqu  [rbp+0B0h+var_98], xmm0
0x14002d056  mov     [rbp+0B0h+var_88], r15
0x14002d05a  lea     rdx, [rbp+0B0h+var_98]
0x14002d05e  lea     rcx, [rsp+1B0h+var_168]
0x14002d063  call    ??$single_threaded_vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@winrt@@YA?AU?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@0@$$QEAV?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@@Z; winrt::single_threaded_vector<winrt::hstring,std::allocator<winrt::hstring>>(std::vector<winrt::hstring> &&)
0x14002d068  nop
0x14002d069  lea     rcx, [rbp+0B0h+var_98]
0x14002d06d  call    ??1?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@QEAA@XZ; std::vector<winrt::hstring>::~vector<winrt::hstring>(void)
0x14002d072  mov     dword ptr [rbp+0B0h+var_98+8], 1
0x14002d079  mov     dword ptr [rbp+0B0h+var_98+0Ch], 29h ; ')'
0x14002d080  lea     rax, a3f114a6a11fa4b_0; "{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} "...
0x14002d087  mov     [rbp+0B0h+var_80], rax
0x14002d08b  lea     rax, [rbp+0B0h+var_98+8]
0x14002d08f  mov     qword ptr [rbp+0B0h+var_98], rax
0x14002d093  lea     rdx, [rbp+0B0h+var_98]
0x14002d097  lea     rcx, [rsp+1B0h+var_168]
0x14002d09c  call    ?Append@?$consume_Windows_Foundation_Collections_IVector@U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@winrt@@Uhstring@5@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::Append(winrt::param::hstring const &)
0x14002d0a1  lea     rdx, [rsp+1B0h+var_168]
0x14002d0a6  lea     rcx, [rbp+0B0h+var_B8]
0x14002d0aa  call    ??$?0U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@winrt@@$0A@@?$async_iterable@Uhstring@winrt@@@param@winrt@@QEAA@AEBU?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@2@@Z; winrt::param::async_iterable<winrt::hstring>::async_iterable<winrt::hstring>(winrt::Windows::Foundation::Collections::IVector<winrt::hstring> const &)
0x14002d0af  nop
0x14002d0b0  mov     qword ptr [rbp+0B0h+var_F0], r14
0x14002d0b4  lea     r8, [rbp+0B0h+var_B8]
0x14002d0b8  lea     rdx, [rbp+0B0h+var_F0]
0x14002d0bc  lea     rcx, [rsp+1B0h+var_170]
0x14002d0c1  call    ?FindAllAsync@DeviceInformation@Enumeration@Devices@Windows@winrt@@SA@AEBUhstring@param@5@AEBU?$async_iterable@Uhstring@winrt@@@75@@Z; winrt::Windows::Devices::Enumeration::DeviceInformation::FindAllAsync(winrt::param::hstring const &,winrt::param::async_iterable<winrt::hstring> const &)
0x14002d0c6  nop
0x14002d0c7  lea     rdx, [rsp+1B0h+var_158]
0x14002d0cc  mov     rcx, rax
0x14002d0cf  call    ?get@?$consume_Windows_Foundation_IAsyncOperation@U?$IAsyncOperation@UDeviceInformationCollection@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@UDeviceInformationCollection@Enumeration@Devices@34@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Devices::Enumeration::DeviceInformationCollection>,winrt::Windows::Devices::Enumeration::DeviceInformationCollection>::get(void)
0x14002d0d4  nop
0x14002d0d5  cmp     [rsp+1B0h+var_170], r15
0x14002d0da  jz      short loc_14002D0E7
0x14002d0dc  lea     rcx, [rsp+1B0h+var_170]
0x14002d0e1  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x14002d0e6  nop
0x14002d0e7  cmp     byte ptr [rbp+0B0h+var_B8+8], r15b
0x14002d0eb  jnz     short loc_14002D105
0x14002d0ed  mov     rax, r15
0x14002d0f0  mov     qword ptr [rbp+0B0h+var_B8], rax
0x14002d0f4  jmp     short loc_14002D109
0x14002d0f6  test    eax, eax
0x14002d0f8  jns     loc_14002D04A
0x14002d0fe  call    cs:__imp_abort
0x14002d105  mov     rax, qword ptr [rbp+0B0h+var_B8]
0x14002d109  test    rax, rax
0x14002d10c  jz      short loc_14002D117
0x14002d10e  lea     rcx, [rbp+0B0h+var_B8]
0x14002d112  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x14002d117  mov     r13d, r15d
0x14002d11a  lea     rdx, [rbp+0B0h+var_98]
0x14002d11e  lea     rcx, [rsp+1B0h+var_158]
0x14002d123  call    ?end@?$consume_Windows_Foundation_Collections_IIterable@U?$IVectorView@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Collections@Foundation@Windows@winrt@@UDeviceInformation@Enumeration@Devices@45@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Devices::Enumeration::DeviceInformation>,winrt::Windows::Devices::Enumeration::DeviceInformation>::end(void)
0x14002d128  cmp     r13d, dword ptr [rbp+0B0h+var_98+8]
0x14002d12c  jz      loc_14002D44D
0x14002d132  mov     [rsp+1B0h+var_170], r15
0x14002d137  or      r12d, 10h
0x14002d13b  mov     dword ptr [rsp+1B0h+var_160], r12d
0x14002d140  mov     rcx, [rsp+1B0h+var_158]
0x14002d145  mov     dword ptr [rbp+0B0h+var_B8], 1EEh
0x14002d14c  lea     rax, aOnecoreuapInte_1; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x14002d153  mov     qword ptr [rbp+0B0h+var_B8+8], rax
0x14002d157  mov     [rbp+0B0h+var_A8], r15
0x14002d15b  mov     rax, [rcx]
0x14002d15e  lea     r8, [rsp+1B0h+var_170]
0x14002d163  mov     edx, r13d
0x14002d166  mov     rax, [rax+30h]
0x14002d16a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002d16f  test    eax, eax
0x14002d171  js      loc_14002D62D
0x14002d177  and     r12d, 0FFFFFFEFh
0x14002d17b  or      r12d, 8
0x14002d17f  mov     dword ptr [rsp+1B0h+var_160], r12d
0x14002d184  lea     rdx, [rsp+1B0h+lpMem]
0x14002d189  lea     rcx, [rsp+1B0h+var_170]
0x14002d18e  call    ?Id@?$consume_Windows_Devices_Enumeration_IDeviceInformation@UIDeviceInformation@Enumeration@Devices@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Id(void)
0x14002d193  nop
0x14002d194  mov     rdx, [rax]
0x14002d197  test    rdx, rdx
0x14002d19a  jz      short loc_14002D1A2
0x14002d19c  mov     rdx, [rdx+10h]
0x14002d1a0  jmp     short loc_14002D1A9
0x14002d1a2  lea     rdx, S2
0x14002d1a9  xorps   xmm0, xmm0
0x14002d1ac  movups  [rbp+0B0h+var_B8], xmm0
0x14002d1b0  mov     [rbp+0B0h+var_A8], r15
0x14002d1b4  mov     [rbp+0B0h+var_A0], r15
0x14002d1b8  mov     r8, rsi
0x14002d1bb  inc     r8
0x14002d1be  cmp     [rdx+r8*2], r15w
0x14002d1c3  jnz     short loc_14002D1BB
0x14002d1c5  lea     rcx, [rbp+0B0h+var_B8]
0x14002d1c9  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14002d1ce  nop
0x14002d1cf  lea     rdx, [rbp+0B0h+var_B8]
0x14002d1d3  lea     rcx, [rbp+0B0h+var_F0]
0x14002d1d7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14002d1dc  mov     rdx, rax
0x14002d1df  lea     rcx, [rbp+0B0h+S1]
0x14002d1e3  call    ?ToLowerTrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(std::wstring)
0x14002d1e8  or      r12d, 20h
0x14002d1ec  lea     rcx, [rbp+0B0h+var_B8]; void *
0x14002d1f0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14002d1f5  nop
0x14002d1f6  mov     rbx, [rsp+1B0h+lpMem]
0x14002d1fb  test    rbx, rbx
0x14002d1fe  jz      short loc_14002D22E
0x14002d200  mov     eax, esi
0x14002d202  lock xadd [rbx+18h], eax
0x14002d207  sub     eax, 1
0x14002d20a  jnz     short loc_14002D221
0x14002d20c  nop
0x14002d20d  call    WINRT_IMPL_GetProcessHeap
0x14002d212  mov     rcx, rax; hHeap
0x14002d215  mov     r8, rbx; lpMem
0x14002d218  xor     edx, edx; dwFlags
0x14002d21a  call    WINRT_IMPL_HeapFree
0x14002d21f  jmp     short loc_14002D229
0x14002d221  test    eax, eax
0x14002d223  js      loc_14002D438
0x14002d229  mov     [rsp+1B0h+lpMem], r15
0x14002d22e  mov     r8, [rbp+0B0h+N]
0x14002d232  lea     rdi, [rbp+0B0h+S1]
0x14002d236  mov     rax, [rbp+0B0h+S1]
0x14002d23a  mov     rcx, [rbp+0B0h+var_60]
0x14002d23e  cmp     rcx, 7
0x14002d242  cmova   rdi, rax
0x14002d246  cmp     r8, 7
0x14002d24a  jb      short loc_14002D28A
0x14002d24c  lea     rbx, [rdi+r8*2]
0x14002d250  mov     r9d, 7
0x14002d256  lea     r8, aBle10; ".ble10#"
0x14002d25d  mov     rdx, rbx
0x14002d260  mov     rcx, rdi
0x14002d263  call    __std_search_2
0x14002d268  cmp     rax, rbx
0x14002d26b  jz      short loc_14002D27E
0x14002d26d  sub     rax, rdi
0x14002d270  and     rax, 0FFFFFFFFFFFFFFFEh
0x14002d274  cmp     rax, 0FFFFFFFFFFFFFFFEh
0x14002d278  jnz     loc_14002D307
0x14002d27e  mov     rcx, [rbp+0B0h+var_60]
0x14002d282  mov     r8, [rbp+0B0h+N]
0x14002d286  mov     rax, [rbp+0B0h+S1]
0x14002d28a  lea     rdi, [rbp+0B0h+S1]
0x14002d28e  cmp     rcx, 7
0x14002d292  cmova   rdi, rax
  ... truncated ...
```
