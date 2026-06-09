# CMidi2KSMidi::Initialize(ushort const *,__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0002,__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0005 *,ulong *,IMidiCallback *,__int64)

- ea: `0x1800124c8`
- end: `0x180013534`
- name: `?Initialize@CMidi2KSMidi@@QEAAJPEBGW4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0002@@PEAU__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0005@@PEAKPEAUIMidiCallback@@_J@Z`
- size: `4204`
- prototype: `__int64 __fastcall(_QWORD *, __int64, unsigned int, __int64, _DWORD *, void *)`
- caller_count: `3`
- callee_count: `35`
- tags: `service_task, broker_com_uri`

## callers

- `0x180015810`
- `0x180015b00`
- `0x180015e00`

## callees

- `0x1800017d0`
- `0x180004410`
- `0x180004bf0`
- `0x180005260`
- `0x18000526c`
- `0x1800052fc`
- `0x180005374`
- `0x18000a814`
- `0x18000c250`
- `0x18000d1c0`
- `0x18000db18`
- `0x18000effc`
- `0x18000f304`
- `0x18000f684`
- `0x18000f9fc`
- `0x18000fddc`
- `0x18000ff14`
- `0x180010008`
- `0x180010108`
- `0x180010da4`
- `0x1800112b0`
- `0x18001137c`
- `0x180011704`
- `0x1800124c8`
- `0x1800136e8`
- `0x180013920`
- `0x1800149d4`
- `0x1800259bc`
- `0x180025cfc`
- `0x180026760`
- `0x1800267e4`
- `0x1800285a0`
- `0x180028994`
- `0x18003cabc`
- `0x180041010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180012792`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180012a2a`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180012792`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180012a2a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012fdf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013150`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013217`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001334a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800133fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013452`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012fdf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013150`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013217`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001334a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800133fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013452`

## pseudocode

```c
__int64 __fastcall CMidi2KSMidi::Initialize(_QWORD *a1, __int64 a2, unsigned int a3, __int64 a4, _DWORD *a5, void *a6)
{
  __int64 v10; // rdx
  unsigned int *v12; // rcx
  int v13; // r8d
  int v14; // r9d
  unsigned int v15; // eax
  __int64 v16; // rsi
  __int64 v17; // rcx
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rdx
  __int64 v21; // rax
  __int64 v22; // r8
  const wchar_t *v23; // r9
  unsigned __int64 v24; // rdx
  void **v25; // rdi
  __int64 v26; // rbx
  void *v27; // rbx
  int v28; // eax
  HANDLE ProcessHeap; // rax
  __int64 v30; // rax
  __int64 *v31; // rbx
  __int64 v32; // rcx
  __int64 v33; // rax
  __int64 *v34; // rbx
  __int64 v35; // rcx
  char v36; // cl
  int RequiredBufferSize; // eax
  unsigned int v38; // ebx
  __int64 v39; // r9
  __int64 v40; // rdx
  void **v41; // rdx
  int v42; // eax
  __int64 v43; // rax
  __int64 *v44; // rbx
  __int64 v45; // rcx
  __int64 v46; // rdx
  unsigned int v47; // r14d
  __int64 v48; // rax
  __int64 *v49; // rbx
  __int64 v50; // rcx
  __int64 *v51; // rbx
  __int64 v52; // rcx
  unsigned int v53; // eax
  __int64 v54; // rax
  __int64 *v55; // rbx
  __int64 v56; // rcx
  unsigned int v57; // esi
  __int64 *v58; // rbx
  __int64 v59; // rcx
  char *Handle; // rbx
  bool v61; // zf
  unsigned int v62; // r15d
  _QWORD *v63; // rax
  _QWORD *v64; // rdi
  int v65; // eax
  unsigned int v66; // r14d
  _QWORD *v67; // r14
  __int64 v68; // rcx
  void *v69; // rax
  __int64 v70; // rdi
  int v71; // eax
  unsigned int v72; // esi
  __int64 v73; // rcx
  int v74; // [rsp+20h] [rbp-E0h]
  int v75; // [rsp+20h] [rbp-E0h]
  __int64 v76; // [rsp+28h] [rbp-D8h]
  __int64 v77; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD *v78; // [rsp+68h] [rbp-98h] BYREF
  __int64 v79; // [rsp+70h] [rbp-90h] BYREF
  __int64 v80; // [rsp+78h] [rbp-88h] BYREF
  __int64 v81; // [rsp+80h] [rbp-80h] BYREF
  LPVOID lpMem; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v83[2]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v84; // [rsp+98h] [rbp-68h] BYREF
  __int64 v85; // [rsp+A8h] [rbp-58h]
  const wchar_t *v86; // [rsp+B0h] [rbp-50h]
  __int128 v87; // [rsp+B8h] [rbp-48h] BYREF
  __int64 *v88; // [rsp+C8h] [rbp-38h]
  const wchar_t *v89; // [rsp+D0h] [rbp-30h]
  int v90; // [rsp+D8h] [rbp-28h]
  const wchar_t *v91; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v92; // [rsp+E8h] [rbp-18h] BYREF
  _QWORD *v93; // [rsp+F0h] [rbp-10h]
  _DWORD *v94; // [rsp+F8h] [rbp-8h]
  __int64 v95; // [rsp+100h] [rbp+0h]
  void *v96; // [rsp+108h] [rbp+8h]
  void *v97[2]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int64 v98; // [rsp+120h] [rbp+20h]
  unsigned __int64 v99; // [rsp+128h] [rbp+28h]
  __int64 v100; // [rsp+130h] [rbp+30h] BYREF
  char v101; // [rsp+138h] [rbp+38h]
  RTL_SRWLOCK SRWLock; // [rsp+140h] [rbp+40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  v95 = a2;
  v93 = a1;
  v94 = a5;
  v96 = a6;
  if ( a3 )
  {
    if ( a3 == 2 && !a6 )
    {
      v10 = 26;
      goto LABEL_4;
    }
  }
  else if ( !a6 )
  {
    v10 = 25;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"avcore\\midi2\\transport\\kstransport\\midi2.ksmidi.cpp",
      (const char *)0x80070057LL,
      v74);
    return 2147942487LL;
  }
  if ( !a2 )
  {
    v10 = 27;
    goto LABEL_4;
  }
  if ( !a5 )
  {
    v10 = 28;
    goto LABEL_4;
  }
  if ( !a4 )
  {
    v10 = 29;
    goto LABEL_4;
  }
  v12 = (unsigned int *)*((_QWORD *)MidiKSTransportTelemetryProvider::Instance() + 1);
  v15 = *v12;
  v90 = 4;
  if ( v15 > 4 )
  {
    v92 = (__int64)a6;
    v83[0] = a3;
    LODWORD(v80) = *(_DWORD *)(a4 + 4);
    v81 = a2;
    v91 = L"Enter";
    v78 = a1;
    lpMem = "CMidi2KSMidi::Initialize";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      (_DWORD)v12,
      (unsigned int)&dword_180068614,
      v13,
      v14,
      (__int64)&lpMem,
      (__int64)&v78,
      (__int64)&v91,
      (__int64)&v81,
      (__int64)&v80,
      (__int64)v83,
      (__int64)&v92);
  }
  v91 = 0;
  v92 = 0;
  *(_OWORD *)v97 = 0;
  v98 = 0;
  v99 = 7;
  LOWORD(v97[0]) = 0;
  v87 = 0;
  v88 = 0;
  winrt::single_threaded_vector<winrt::hstring,std::allocator<winrt::hstring>>(&v78, &v87);
  std::vector<winrt::hstring>::~vector<winrt::hstring>(&v87);
  *((_QWORD *)&v84 + 1) = 0x2800000001LL;
  v86 = L"{2BF8A79A-79FF-49BC-9126-372815B153C8},1";
  *(_QWORD *)&v84 = (char *)&v84 + 8;
  winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::Append(
    &v78,
    &v84);
  *((_QWORD *)&v84 + 1) = 0x2800000001LL;
  v86 = L"{2BF8A79A-79FF-49BC-9126-372815B153C8},2";
  *(_QWORD *)&v84 = (char *)&v84 + 8;
  winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::Append(
    &v78,
    &v84);
  *((_QWORD *)&v84 + 1) = 0x2800000001LL;
  v86 = L"{05279CB1-002F-4E6B-A3A3-29A87D82B4F7},1";
  *(_QWORD *)&v84 = (char *)&v84 + 8;
  winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::Append(
    &v78,
    &v84);
  *((_QWORD *)&v84 + 1) = 0x2800000001LL;
  v86 = L"{05279CB1-002F-4E6B-A3A3-29A87D82B4F7},2";
  *(_QWORD *)&v84 = (char *)&v84 + 8;
  winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::Append(
    &v78,
    &v84);
  *((_QWORD *)&v84 + 1) = 0x2800000001LL;
  v86 = L"{05279CB1-002F-4E6B-A3A3-29A87D82B4F7},3";
  *(_QWORD *)&v84 = (char *)&v84 + 8;
  winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::Append(
    &v78,
    &v84);
  *((_QWORD *)&v84 + 1) = 0x2100000001LL;
  v86 = L"System.Devices.InterfaceClassGuid";
  *(_QWORD *)&v84 = (char *)&v84 + 8;
  winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::Append(
    &v78,
    &v84);
  LODWORD(v80) = 1;
  winrt::param::async_iterable<winrt::hstring>::async_iterable<winrt::hstring>(&v100, &v78);
  v16 = -1;
  v17 = -1;
  do
    ++v17;
  while ( *(_WORD *)(a2 + 2 * v17) );
  if ( (_DWORD)v17 )
  {
    if ( *(_WORD *)(a2 + 2LL * (unsigned int)v17) )
      abort();
    DWORD2(v84) = 1;
    HIDWORD(v84) = v17;
    v86 = (const wchar_t *)a2;
    *(_QWORD *)&v84 = (char *)&v84 + 8;
  }
  else
  {
    *(_QWORD *)&v84 = 0;
  }
  *(_QWORD *)&v87 = &v84;
  *((_QWORD *)&v87 + 1) = &v100;
  v88 = &v80;
  lpMem = &qword_180071C88;
  _InterlockedAdd64(&qword_180071C88, 1u);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2> )
  {
    `winrt::Windows::Devices::Enumeration::DeviceInformation::CreateFromIdAsync'::`2'::_lambda_1_::operator()(
      &v87,
      v83,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>);
    _InterlockedAdd64(&qword_180071C88, 0xFFFFFFFFFFFFFFFFuLL);
  }
  else
  {
    _InterlockedAdd64(&qword_180071C88, 0xFFFFFFFFFFFFFFFFuLL);
    ___call_AEAV_lambda_1___1__CreateFromIdAsync_DeviceInformation_Enumeration_Devices_Windows_winrt__SA_AEBUhstring_param_7_AEBU__async_iterable_Uhstring_winrt___97_AEBW4DeviceInformationKind_4567__Z____factory_cache_entry_UDeviceInformation_Enumeration_Devices_Windows_winrt__UIDeviceInformationStatics2_2345__impl_winrt__QEAA_A_PAEAV_lambda_1___1__CreateFromIdAsync_DeviceInformation_Enumeration_Devices_Windows_2_SA_AEBUhstring_param_2_AEBU__async_iterable_Uhstring_winrt___param_2_AEBW4DeviceInformationKind_6782__Z__Z(
      v17,
      v83,
      &v87);
  }
  winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Devices::Enumeration::DeviceInformation>,winrt::Windows::Devices::Enumeration::DeviceInformation>::get(
    v83,
    &v79);
  if ( *(_QWORD *)v83 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v83);
  if ( v101 )
  {
    v18 = v100;
  }
  else
  {
    v18 = 0;
    v100 = 0;
  }
  if ( v18 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v100);
  v19 = winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Properties(
          &v79,
          &v81);
  *((_QWORD *)&v87 + 1) = 0x2800000001LL;
  v89 = L"{2BF8A79A-79FF-49BC-9126-372815B153C8},1";
  *(_QWORD *)&v87 = (char *)&v87 + 8;
  winrt::impl::consume_Windows_Foundation_Collections_IMapView<winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Windows::Foundation::IInspectable>,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(
    v19,
    &v77,
    &v87);
  if ( v81 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v81);
  lpMem = 0;
  if ( (unsigned __int8)winrt::Windows::Foundation::operator==(&v77, &lpMem) )
  {
    v20 = 66;
LABEL_37:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v20,
      (unsigned int)"avcore\\midi2\\transport\\kstransport\\midi2.ksmidi.cpp",
      (const char *)0x80070057LL,
      v74);
LABEL_146:
    if ( v77 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v77);
    if ( v79 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v79);
    if ( v78 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v78);
    v38 = -2147024809;
LABEL_217:
    std::wstring::~wstring(v97);
    return v38;
  }
  v21 = winrt::unbox_value<winrt::hstring>(&lpMem, &v77);
  if ( *(_QWORD *)v21 )
    v23 = *(const wchar_t **)(*(_QWORD *)v21 + 16LL);
  else
    v23 = &S1;
  v24 = -1;
  do
    ++v24;
  while ( v23[v24] );
  if ( v24 > v99 )
  {
    ____Reallocate_for_V_lambda_1___1_____Assign_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV23_QEBG_K_Z_PEBG___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign_G_01_AEAAAEAV01_QEBG0_Z_PEBG_Z(
      v97,
      v24,
      v22,
      v23);
  }
  else
  {
    v25 = v97;
    if ( v99 > 7 )
      v25 = (void **)v97[0];
    v98 = v24;
    v26 = 2 * v24;
    memmove_0(v25, v23, 2 * v24);
    *(_WORD *)((char *)v25 + v26) = 0;
  }
  v27 = lpMem;
  if ( lpMem )
  {
    v28 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
    if ( v28 )
    {
      if ( v28 < 0 )
        abort();
    }
    else
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, v27);
    }
  }
  v30 = winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Properties(
          &v79,
          v83);
  *((_QWORD *)&v84 + 1) = 0x2100000001LL;
  v86 = L"System.Devices.InterfaceClassGuid";
  *(_QWORD *)&v84 = (char *)&v84 + 8;
  v31 = (__int64 *)winrt::impl::consume_Windows_Foundation_Collections_IMapView<winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Windows::Foundation::IInspectable>,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(
                     v30,
                     &v80,
                     &v84);
  if ( &v77 != v31 )
  {
    if ( v77 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v77);
    v32 = *v31;
    *v31 = 0;
    v77 = v32;
  }
  if ( v80 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v80);
  if ( *(_QWORD *)v83 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v83);
  lpMem = 0;
  if ( (unsigned __int8)winrt::Windows::Foundation::operator==(&v77, &lpMem) )
  {
    v20 = 70;
    goto LABEL_37;
  }
  winrt::unbox_value<winrt::guid>(&v100, &v77);
  v33 = winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Properties(
          &v79,
          v83);
  *((_QWORD *)&v84 + 1) = 0x2800000001LL;
  v86 = L"{05279CB1-002F-4E6B-A3A3-29A87D82B4F7},3";
  *(_QWORD *)&v84 = (char *)&v84 + 8;
  v34 = (__int64 *)winrt::impl::consume_Windows_Foundation_Collections_IMapView<winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Windows::Foundation::IInspectable>,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(
                     v33,
                     &v80,
                     &v84);
  if ( &v77 != v34 )
  {
    if ( v77 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v77);
    v35 = *v34;
    *v34 = 0;
    v77 = v35;
  }
  if ( v80 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v80);
  if ( *(_QWORD *)v83 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v83);
  lpMem = 0;
  if ( (unsigned __int8)winrt::Windows::Foundation::operator==(&v77, &lpMem) )
  {
    v20 = 74;
    goto LABEL_37;
  }
  v36 = winrt::unbox_value<unsigned int>(&v77);
  if ( *(_DWORD *)(a4 + 4) == 1 )
  {
    v36 &= 3u;
  }
  else if ( *(_DWORD *)(a4 + 4) == 2 )
  {
    v36 &= 4u;
  }
  if ( (v36 & 4) != 0 )
  {
    *(_DWORD *)(a4 + 4) = 2;
  }
  else
  {
    if ( (v36 & 2) != 0 )
    {
      v90 = 2;
    }
    else
    {
      if ( (v36 & 1) == 0 )
      {
        v38 = -2147023266;
        v39 = 2147944030LL;
        v40 = 116;
        goto LABEL_210;
      }
      v90 = 1;
    }
    *(_DWORD *)(a4 + 4) = 1;
  }
  v83[0] = 0x2000;
  RequiredBufferSize = GetRequiredBufferSize(v83);
  v38 = RequiredBufferSize;
  if ( RequiredBufferSize < 0 )
  {
    v39 = (unsigned int)RequiredBufferSize;
    v40 = 121;
LABEL_210:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v40,
      (unsigned int)"avcore\\midi2\\transport\\kstransport\\midi2.ksmidi.cpp",
      (const char *)v39,
      v74);
    goto LABEL_211;
  }
  v41 = v97;
  if ( v99 > 7 )
    v41 = (void **)v97[0];
  v84 = 0;
  v85 = 0;
  v86 = 0;
  do
    ++v16;
  while ( *((_WORD *)v41 + v16) );
  std::wstring::_Construct<1,unsigned short const *>(&v84, v41, v16);
  KsHandleWrapper::KsHandleWrapper(&SRWLock, &v84);
  v42 = KsHandleWrapper::Open((KsHandleWrapper *)&SRWLock);
  v38 = v42;
  if ( v42 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7D,
      (unsigned int)"avcore\\midi2\\transport\\kstransport\\midi2.ksmidi.cpp",
      (const char *)(unsigned int)v42,
      v74);
    KsHandleWrapper::~KsHandleWrapper((KsHandleWrapper *)&SRWLock);
LABEL_211:
    if ( v77 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v77);
    if ( v79 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v79);
    if ( v78 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v78);
    goto LABEL_217;
  }
  v43 = winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Properties(
          &v79,
          &v80);
  if ( a3 == 2 )
  {
    *((_QWORD *)&v87 + 1) = 0x2800000001LL;
    v89 = L"{05279CB1-002F-4E6B-A3A3-29A87D82B4F7},1";
    *(_QWORD *)&v87 = (char *)&v87 + 8;
    v44 = (__int64 *)winrt::impl::consume_Windows_Foundation_Collections_IMapView<winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Windows::Foundation::IInspectable>,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(
                       v43,
                       &v81,
                       &v87);
    if ( &v77 != v44 )
    {
      if ( v77 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v77);
      v45 = *v44;
      *v44 = 0;
      v77 = v45;
    }
    if ( v81 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v81);
    if ( v80 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v80);
    lpMem = 0;
    if ( (unsigned __int8)winrt::Windows::Foundation::operator==(&v77, &lpMem) )
    {
      v46 = 130;
LABEL_145:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v46,
        (unsigned int)"avcore\\midi2\\transport\\kstransport\\midi2.ksmidi.cpp",
        (const char *)0x80070057LL,
        v74);
      KsHandleWrapper::~KsHandleWrapper((KsHandleWrapper *)&SRWLock);
      goto LABEL_146;
    }
    v47 = winrt::unbox_value<unsigned int>(&v77);
    v48 = winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Properties(
            &v79,
            &v80);
    *((_QWORD *)&v87 + 1) = 0x2800000001LL;
    v89 = L"{05279CB1-002F-4E6B-A3A3-29A87D82B4F7},2";
    *(_QWORD *)&v87 = (char *)&v87 + 8;
    v49 = (__int64 *)winrt::impl::consume_Windows_Foundation_Collections_IMapView<winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Windows::Foundation::IInspectable>,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(
                       v48,
                       &v81,
                       &v87);
    if ( &v77 != v49 )
    {
      if ( v77 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v77);
      v50 = *v49;
      *v49 = 0;
      v77 = v50;
    }
    if ( v81 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v81);
    if ( v80 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v80);
    lpMem = 0;
    if ( (unsigned __int8)winrt::Windows::Foundation::operator==(&v77, &lpMem) )
    {
      v46 = 134;
      goto LABEL_145;
    }
    goto LABEL_154;
  }
  *((_QWORD *)&v87 + 1) = 0x2800000001LL;
  v89 = L"{2BF8A79A-79FF-49BC-9126-372815B153C8},2";
  *(_QWORD *)&v87 = (char *)&v87 + 8;
  v51 = (__int64 *)winrt::impl::consume_Windows_Foundation_Collections_IMapView<winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Windows::Foundation::IInspectable>,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(
                     v43,
                     &v81,
                     &v87);
  if ( &v77 != v51 )
  {
    if ( v77 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v77);
    v52 = *v51;
    *v51 = 0;
    v77 = v52;
  }
  if ( v81 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v81);
  if ( v80 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v80);
  if ( v77 )
  {
    v53 = winrt::unbox_value<unsigned int>(&v77);
    v47 = v53;
LABEL_155:
    v57 = v53;
    goto LABEL_156;
  }
  v54 = winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Properties(
          &v79,
          &v80);
  if ( a3 )
  {
    *((_QWORD *)&v87 + 1) = 0x2800000001LL;
    v89 = L"{05279CB1-002F-4E6B-A3A3-29A87D82B4F7},2";
    *(_QWORD *)&v87 = (char *)&v87 + 8;
    v58 = (__int64 *)winrt::impl::consume_Windows_Foundation_Collections_IMapView<winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Windows::Foundation::IInspectable>,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(
                       v54,
                       &v81,
                       &v87);
    if ( &v77 != v58 )
    {
      if ( v77 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v77);
      v59 = *v58;
      *v58 = 0;
      v77 = v59;
    }
    if ( v81 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v81);
    if ( v80 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v80);
    lpMem = 0;
    if ( (unsigned __int8)winrt::Windows::Foundation::operator==(&v77, &lpMem) )
    {
      v46 = 155;
      goto LABEL_145;
    }
    v47 = 0;
LABEL_154:
    v53 = winrt::unbox_value<unsigned int>(&v77);
    goto LABEL_155;
  }
  *((_QWORD *)&v87 + 1) = 0x2800000001LL;
  v89 = L"{05279CB1-002F-4E6B-A3A3-29A87D82B4F7},1";
  *(_QWORD *)&v87 = (char *)&v87 + 8;
  v55 = (__int64 *)winrt::impl::consume_Windows_Foundation_Collections_IMapView<winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Windows::Foundation::IInspectable>,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(
                     v54,
                     &v81,
                     &v87);
  if ( &v77 != v55 )
  {
    if ( v77 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v77);
    v56 = *v55;
    *v55 = 0;
    v77 = v56;
  }
  if ( v81 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v81);
  if ( v80 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v80);
  lpMem = 0;
  if ( (unsigned __int8)winrt::Windows::Foundation::operator==(&v77, &lpMem) )
  {
    v46 = 149;
    goto LABEL_145;
  }
  v57 = 0;
  v47 = winrt::unbox_value<unsigned int>(&v77);
LABEL_156:
  Handle = (char *)KsHandleWrapper::GetHandle(&SRWLock);
  lpMem = Handle;
  if ( ((unsigned __int64)(Handle + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA2,
      (unsigned int)"avcore\\midi2\\transport\\kstransport\\midi2.ksmidi.cpp",
      (const char *)0x8007000ELL,
      v74);
    if ( (unsigned __int64)(Handle - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(Handle);
    KsHandleWrapper::~KsHandleWrapper((KsHandleWrapper *)&SRWLock);
    if ( v77 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v77);
    if ( v79 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v79);
    v61 = v78 == 0;
LABEL_199:
    if ( !v61 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v78);
    v38 = -2147024882;
    goto LABEL_217;
  }
  v62 = v83[0];
  if ( (a3 & 0xFFFFFFFD) != 0 )
  {
    v67 = v93;
  }
  else
  {
    v63 = operator new(0xA8u, (const struct std::nothrow_t *)std::nothrow);
    v64 = v63;
    v81 = (__int64)v63;
    if ( !v63 )
    {
      v91 = 0;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA7,
        (unsigned int)"avcore\\midi2\\transport\\kstransport\\midi2.ksmidi.cpp",
        (const char *)0x8007000ELL,
        v74);
      CloseHandle(Handle);
      KsHandleWrapper::~KsHandleWrapper((KsHandleWrapper *)&SRWLock);
      if ( v77 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v77);
      if ( v79 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v79);
      v61 = v78 == 0;
      goto LABEL_199;
    }
    memset_0(v63, 0, 0xA8u);
    v64[1] = 0;
    *((_DWORD *)v64 + 4) = 1;
    *((_BYTE *)v64 + 20) = 0;
    v64[3] = 0;
    v64[4] = 0;
    v64[5] = 0;
    v64[6] = 0;
    v64[7] = 0;
    v64[8] = 0;
    v64[9] = 0;
    v64[10] = 0;
    v64[11] = 0;
    v64[12] = 0;
    *((_DWORD *)v64 + 26) = 0;
    *v64 = &KSMidiInDevice::`vftable';
    v64[14] = 0;
    v64[15] = 0;
    v64[16] = 0;
    v64[17] = 0;
    v64[18] = 0;
    *((_DWORD *)v64 + 38) = 1;
    v64[20] = 0;
    v91 = (const wchar_t *)v64;
    v74 = v90;
    v65 = KSMidiInDevice::Initialize(v64, v95, Handle, v47);
    v66 = v65;
    if ( v65 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA8,
        (unsigned int)"avcore\\midi2\\transport\\kstransport\\midi2.ksmidi.cpp",
        (const char *)(unsigned int)v65,
        v74);
      CloseHandle(Handle);
      KsHandleWrapper::~KsHandleWrapper((KsHandleWrapper *)&SRWLock);
      if ( v77 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v77);
      if ( v79 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v79);
      if ( v78 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v78);
      std::wstring::~wstring(v97);
      (*(void (__fastcall **)(_QWORD *, __int64))(*v64 + 8LL))(v64, 1);
      return v66;
    }
    v91 = 0;
    v67 = v93;
    v68 = *v93;
    *v93 = v64;
    if ( v68 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v68 + 8LL))(v68, 1);
  }
  if ( a3 - 1 <= 1 )
  {
    v69 = operator new(0x70u, (const struct std::nothrow_t *)std::nothrow);
    v70 = (__int64)v69;
    v96 = v69;
    if ( !v69 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB0,
        (unsigned int)"avcore\\midi2\\transport\\kstransport\\midi2.ksmidi.cpp",
        (const char *)0x8007000ELL,
        v74);
      CloseHandle(Handle);
      KsHandleWrapper::~KsHandleWrapper((KsHandleWrapper *)&SRWLock);
      if ( v77 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v77);
      if ( v79 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v79);
      v61 = v78 == 0;
      goto LABEL_199;
    }
    memset_0(v69, 0, 0x70u);
    *(_QWORD *)(v70 + 8) = 0;
    *(_DWORD *)(v70 + 16) = 1;
    *(_BYTE *)(v70 + 20) = 0;
    *(_QWORD *)(v70 + 24) = 0;
    *(_QWORD *)(v70 + 32) = 0;
    *(_QWORD *)(v70 + 40) = 0;
    *(_QWORD *)(v70 + 48) = 0;
    *(_QWORD *)(v70 + 56) = 0;
    *(_QWORD *)(v70 + 64) = 0;
    *(_QWORD *)(v70 + 72) = 0;
    *(_QWORD *)(v70 + 80) = 0;
    *(_QWORD *)(v70 + 88) = 0;
    *(_QWORD *)(v70 + 96) = 0;
    *(_DWORD *)(v70 + 104) = 0;
    *(_QWORD *)v70 = &KSMidiOutDevice::`vftable';
    v92 = v70;
    LODWORD(v76) = v62;
    v71 = KSMidiOutDevice::Initialize(v70, v95, (__int64)Handle, v57, v90, v76, v94);
    v72 = v71;
    if ( v71 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB2,
        (unsigned int)"avcore\\midi2\\transport\\kstransport\\midi2.ksmidi.cpp",
        (const char *)(unsigned int)v71,
        v75);
      CloseHandle(Handle);
      KsHandleWrapper::~KsHandleWrapper((KsHandleWrapper *)&SRWLock);
      if ( v77 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v77);
      if ( v79 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v79);
      if ( v78 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v78);
      std::wstring::~wstring(v97);
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v70 + 8LL))(v70, 1);
      return v72;
    }
    v73 = v67[1];
    v67[1] = v70;
    if ( v73 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v73 + 8LL))(v73, 1);
  }
  CloseHandle(Handle);
  KsHandleWrapper::~KsHandleWrapper((KsHandleWrapper *)&SRWLock);
  if ( v77 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v77);
  if ( v79 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v79);
  if ( v78 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v78);
  std::wstring::~wstring(v97);
  return 0;
}

```

## disassembly

```asm
0x1800124c8  mov     [rsp-8+arg_10], rbx
0x1800124cd  push    rbp
0x1800124ce  push    rsi
0x1800124cf  push    rdi
0x1800124d0  push    r12
0x1800124d2  push    r13
0x1800124d4  push    r14
0x1800124d6  push    r15
0x1800124d8  lea     rbp, [rsp-130h]
0x1800124e0  sub     rsp, 230h
0x1800124e7  mov     rax, cs:__security_cookie
0x1800124ee  xor     rax, rsp
0x1800124f1  mov     [rbp+160h+var_40], rax
0x1800124f8  mov     r12, r9
0x1800124fb  mov     r13d, r8d
0x1800124fe  mov     rbx, rdx
0x180012501  mov     [rbp+160h+var_160], rdx
0x180012505  mov     rsi, rcx
0x180012508  mov     [rbp+160h+var_170], rcx
0x18001250c  mov     rax, [rbp+160h+arg_20]
0x180012513  mov     [rbp+160h+var_168], rax
0x180012517  mov     r14, [rbp+160h+arg_28]
0x18001251e  mov     [rbp+160h+var_158], r14
0x180012522  xor     r15d, r15d
0x180012525  test    r8d, r8d
0x180012528  jnz     short loc_180012556
0x18001252a  test    r14, r14
0x18001252d  jnz     short loc_180012567
0x18001252f  lea     edx, [r8+19h]; void *
0x180012533  mov     rcx, [rbp+168h]; this
0x18001253a  mov     r9d, 80070057h; char *
0x180012540  lea     r8, aAvcoreMidi2Tra_5; "avcore\\midi2\\transport\\kstransport\\"...
0x180012547  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001254c  mov     eax, 80070057h
0x180012551  jmp     loc_18001350A
0x180012556  cmp     r13d, 2
0x18001255a  jnz     short loc_180012567
0x18001255c  test    r14, r14
0x18001255f  jnz     short loc_180012567
0x180012561  lea     edx, [r13+18h]
0x180012565  jmp     short loc_180012533
0x180012567  test    rbx, rbx
0x18001256a  jnz     short loc_180012571
0x18001256c  lea     edx, [rbx+1Bh]
0x18001256f  jmp     short loc_180012533
0x180012571  test    rax, rax
0x180012574  jnz     short loc_18001257B
0x180012576  lea     edx, [rax+1Ch]
0x180012579  jmp     short loc_180012533
0x18001257b  test    r12, r12
0x18001257e  jnz     short loc_180012587
0x180012580  lea     edx, [r12+1Dh]
0x180012585  jmp     short loc_180012533
0x180012587  call    ?Instance@MidiKSTransportTelemetryProvider@@KAPEAV1@XZ; MidiKSTransportTelemetryProvider::Instance(void)
0x18001258c  mov     rcx, [rax+8]
0x180012590  mov     eax, [rcx]
0x180012592  mov     edi, 4
0x180012597  mov     [rbp+160h+var_188], edi
0x18001259a  cmp     eax, edi
0x18001259c  jbe     short loc_18001261B
0x18001259e  mov     [rbp+160h+var_178], r14
0x1800125a2  mov     [rbp+160h+var_1D0], r13d
0x1800125a6  mov     eax, [r12+4]
0x1800125ab  mov     dword ptr [rsp+260h+var_1E8], eax
0x1800125af  mov     [rbp+160h+var_1E0], rbx
0x1800125b3  lea     rax, aEnter; "Enter"
0x1800125ba  mov     [rbp+160h+var_180], rax
0x1800125be  mov     [rsp+260h+var_1F8], rsi
0x1800125c3  lea     rax, aCmidi2ksmidiIn; "CMidi2KSMidi::Initialize"
0x1800125ca  mov     [rbp+160h+lpMem], rax
0x1800125ce  lea     rax, [rbp+160h+var_178]
0x1800125d2  mov     [rsp+260h+var_210], rax
0x1800125d7  lea     rax, [rbp+160h+var_1D0]
0x1800125db  mov     [rsp+260h+var_218], rax
0x1800125e0  lea     rax, [rsp+260h+var_1E8]
0x1800125e5  mov     [rsp+260h+var_220], rax
0x1800125ea  lea     rax, [rbp+160h+var_1E0]
0x1800125ee  mov     [rsp+260h+var_228], rax
0x1800125f3  lea     rax, [rbp+160h+var_180]
0x1800125f7  mov     [rsp+260h+var_230], rax
0x1800125fc  lea     rax, [rsp+260h+var_1F8]
0x180012601  mov     [rsp+260h+var_238], rax
0x180012606  lea     rax, [rbp+160h+lpMem]
0x18001260a  mov     qword ptr [rsp+260h+var_240], rax; int
0x18001260f  lea     rdx, dword_180068614
0x180012616  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@U?$_tlgWrapperByVal@$03@@U4@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5AEBU?$_tlgWrapperByVal@$03@@64@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x18001261b  mov     [rbp+160h+var_180], r15
0x18001261f  mov     [rbp+160h+var_178], r15
0x180012623  xorps   xmm0, xmm0
0x180012626  movups  xmmword ptr [rbp+160h+var_150], xmm0
0x18001262a  mov     [rbp+160h+var_140], r15
0x18001262e  mov     [rbp+160h+var_138], 7
0x180012636  mov     word ptr [rbp+160h+var_150], r15w
0x18001263b  movdqu  [rbp+160h+var_1A8], xmm0
0x180012640  mov     [rbp+160h+var_198], r15
0x180012644  lea     rdx, [rbp+160h+var_1A8]
0x180012648  lea     rcx, [rsp+260h+var_1F8]
0x18001264d  call    ??$single_threaded_vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@winrt@@YA?AU?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@0@$$QEAV?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@@Z; winrt::single_threaded_vector<winrt::hstring,std::allocator<winrt::hstring>>(std::vector<winrt::hstring> &&)
0x180012652  nop
0x180012653  lea     rcx, [rbp+160h+var_1A8]
0x180012657  call    ??1?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@QEAA@XZ; std::vector<winrt::hstring>::~vector<winrt::hstring>(void)
0x18001265c  mov     r14d, 1
0x180012662  mov     dword ptr [rbp+160h+var_1C8+8], r14d
0x180012666  lea     esi, [r14+27h]
0x18001266a  mov     dword ptr [rbp+160h+var_1C8+0Ch], esi
0x18001266d  lea     rax, a2bf8a79a79ff49; "{2BF8A79A-79FF-49BC-9126-372815B153C8},"...
0x180012674  mov     [rbp+160h+var_1B0], rax
0x180012678  lea     rax, [rbp+160h+var_1C8+8]
0x18001267c  mov     qword ptr [rbp+160h+var_1C8], rax
0x180012680  lea     rdx, [rbp+160h+var_1C8]
0x180012684  lea     rcx, [rsp+260h+var_1F8]
0x180012689  call    ?Append@?$consume_Windows_Foundation_Collections_IVector@U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@winrt@@Uhstring@5@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::Append(winrt::param::hstring const &)
0x18001268e  mov     dword ptr [rbp+160h+var_1C8+8], r14d
0x180012692  mov     dword ptr [rbp+160h+var_1C8+0Ch], esi
0x180012695  lea     rax, a2bf8a79a79ff49_0; "{2BF8A79A-79FF-49BC-9126-372815B153C8},"...
0x18001269c  mov     [rbp+160h+var_1B0], rax
0x1800126a0  lea     rax, [rbp+160h+var_1C8+8]
0x1800126a4  mov     qword ptr [rbp+160h+var_1C8], rax
0x1800126a8  lea     rdx, [rbp+160h+var_1C8]
0x1800126ac  lea     rcx, [rsp+260h+var_1F8]
0x1800126b1  call    ?Append@?$consume_Windows_Foundation_Collections_IVector@U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@winrt@@Uhstring@5@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::Append(winrt::param::hstring const &)
0x1800126b6  mov     dword ptr [rbp+160h+var_1C8+8], r14d
0x1800126ba  mov     dword ptr [rbp+160h+var_1C8+0Ch], esi
0x1800126bd  lea     rax, a05279cb1002f4e; "{05279CB1-002F-4E6B-A3A3-29A87D82B4F7},"...
0x1800126c4  mov     [rbp+160h+var_1B0], rax
0x1800126c8  lea     rax, [rbp+160h+var_1C8+8]
0x1800126cc  mov     qword ptr [rbp+160h+var_1C8], rax
0x1800126d0  lea     rdx, [rbp+160h+var_1C8]
0x1800126d4  lea     rcx, [rsp+260h+var_1F8]
0x1800126d9  call    ?Append@?$consume_Windows_Foundation_Collections_IVector@U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@winrt@@Uhstring@5@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::Append(winrt::param::hstring const &)
0x1800126de  mov     dword ptr [rbp+160h+var_1C8+8], r14d
0x1800126e2  mov     dword ptr [rbp+160h+var_1C8+0Ch], esi
0x1800126e5  lea     rax, a05279cb1002f4e_1; "{05279CB1-002F-4E6B-A3A3-29A87D82B4F7},"...
0x1800126ec  mov     [rbp+160h+var_1B0], rax
0x1800126f0  lea     rax, [rbp+160h+var_1C8+8]
0x1800126f4  mov     qword ptr [rbp+160h+var_1C8], rax
0x1800126f8  lea     rdx, [rbp+160h+var_1C8]
0x1800126fc  lea     rcx, [rsp+260h+var_1F8]
0x180012701  call    ?Append@?$consume_Windows_Foundation_Collections_IVector@U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@winrt@@Uhstring@5@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::Append(winrt::param::hstring const &)
0x180012706  mov     dword ptr [rbp+160h+var_1C8+8], r14d
0x18001270a  mov     dword ptr [rbp+160h+var_1C8+0Ch], esi
0x18001270d  lea     rax, a05279cb1002f4e_0; "{05279CB1-002F-4E6B-A3A3-29A87D82B4F7},"...
0x180012714  mov     [rbp+160h+var_1B0], rax
0x180012718  lea     rax, [rbp+160h+var_1C8+8]
0x18001271c  mov     qword ptr [rbp+160h+var_1C8], rax
0x180012720  lea     rdx, [rbp+160h+var_1C8]
0x180012724  lea     rcx, [rsp+260h+var_1F8]
0x180012729  call    ?Append@?$consume_Windows_Foundation_Collections_IVector@U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@winrt@@Uhstring@5@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::Append(winrt::param::hstring const &)
0x18001272e  mov     dword ptr [rbp+160h+var_1C8+8], r14d
0x180012732  mov     dword ptr [rbp+160h+var_1C8+0Ch], 21h ; '!'
0x180012739  lea     rax, aSystemDevicesI_0; "System.Devices.InterfaceClassGuid"
0x180012740  mov     [rbp+160h+var_1B0], rax
0x180012744  lea     rax, [rbp+160h+var_1C8+8]
0x180012748  mov     qword ptr [rbp+160h+var_1C8], rax
0x18001274c  lea     rdx, [rbp+160h+var_1C8]
0x180012750  lea     rcx, [rsp+260h+var_1F8]
0x180012755  call    ?Append@?$consume_Windows_Foundation_Collections_IVector@U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@winrt@@Uhstring@5@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::Append(winrt::param::hstring const &)
0x18001275a  mov     dword ptr [rsp+260h+var_1E8], r14d
0x18001275f  lea     rdx, [rsp+260h+var_1F8]
0x180012764  lea     rcx, [rbp+160h+var_130]
0x180012768  call    ??$?0U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@winrt@@$0A@@?$async_iterable@Uhstring@winrt@@@param@winrt@@QEAA@AEBU?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@2@@Z; winrt::param::async_iterable<winrt::hstring>::async_iterable<winrt::hstring>(winrt::Windows::Foundation::Collections::IVector<winrt::hstring> const &)
0x18001276d  nop
0x18001276e  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180012772  mov     rcx, rsi
0x180012775  inc     rcx
0x180012778  cmp     [rbx+rcx*2], r15w
0x18001277d  jnz     short loc_180012775
0x18001277f  test    ecx, ecx
0x180012781  jnz     short loc_180012789
0x180012783  mov     qword ptr [rbp+160h+var_1C8], r15
0x180012787  jmp     short loc_1800127AC
0x180012789  mov     eax, ecx
0x18001278b  cmp     [rbx+rax*2], r15w
0x180012790  jz      short loc_180012799
0x180012792  call    cs:__imp_abort
0x180012799  mov     dword ptr [rbp+160h+var_1C8+8], r14d
0x18001279d  mov     dword ptr [rbp+160h+var_1C8+0Ch], ecx
0x1800127a0  mov     [rbp+160h+var_1B0], rbx
0x1800127a4  lea     rax, [rbp+160h+var_1C8+8]
0x1800127a8  mov     qword ptr [rbp+160h+var_1C8], rax
0x1800127ac  lea     rax, [rbp+160h+var_1C8]
0x1800127b0  mov     qword ptr [rbp+160h+var_1A8], rax
0x1800127b4  lea     rax, [rbp+160h+var_130]
0x1800127b8  mov     qword ptr [rbp+160h+var_1A8+8], rax
0x1800127bc  lea     rax, [rsp+260h+var_1E8]
0x1800127c1  mov     [rbp+160h+var_198], rax
0x1800127c5  lea     rax, qword_180071C88
0x1800127cc  mov     [rbp+160h+lpMem], rax
0x1800127d0  lock add cs:qword_180071C88, r14
0x1800127d8  cmp     cs:??$factory_cache_entry_v@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@impl@winrt@@3U?$factory_cache_entry@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@12@A, r15; factory_cache_entry<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>::winrt::factory_cache_entry<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2> winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>
0x1800127df  jz      short loc_180012800
0x1800127e1  lea     r8, ??$factory_cache_entry_v@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@impl@winrt@@3U?$factory_cache_entry@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@12@A; factory_cache_entry<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>::winrt::factory_cache_entry<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2> winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>
0x1800127e8  lea     rdx, [rbp+160h+var_1D0]
0x1800127ec  lea     rcx, [rbp+160h+var_1A8]
0x1800127f0  call    ??R_lambda_1_@?1??CreateFromIdAsync@DeviceInformation@Enumeration@Devices@Windows@winrt@@SA@AEBUhstring@param@6@AEBU?$async_iterable@Uhstring@winrt@@@86@AEBW4DeviceInformationKind@3456@@Z@QEBA@AEBUIDeviceInformationStatics2@3456@@Z; `winrt::Windows::Devices::Enumeration::DeviceInformation::CreateFromIdAsync(winrt::param::hstring const &,winrt::param::async_iterable<winrt::hstring> const &,winrt::Windows::Devices::Enumeration::DeviceInformationKind const &)'::`2'::_lambda_1_::operator()(winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2 const &)
0x1800127f5  nop
0x1800127f6  lock add cs:qword_180071C88, rsi
0x1800127fe  jmp     short loc_180012816
0x180012800  lock add cs:qword_180071C88, rsi
0x180012808  lea     r8, [rbp+160h+var_1A8]
0x18001280c  lea     rdx, [rbp+160h+var_1D0]
0x180012810  call    ??$call@AEAV_lambda_1_@?1??CreateFromIdAsync@DeviceInformation@Enumeration@Devices@Windows@winrt@@SA@AEBUhstring@param@7@AEBU?$async_iterable@Uhstring@winrt@@@97@AEBW4DeviceInformationKind@4567@@Z@@?$factory_cache_entry@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateFromIdAsync@DeviceInformation@Enumeration@Devices@Windows@2@SA@AEBUhstring@param@2@AEBU?$async_iterable@Uhstring@winrt@@@param@2@AEBW4DeviceInformationKind@6782@@Z@@Z
0x180012815  nop
0x180012816  lea     rdx, [rsp+260h+var_1F0]
0x18001281b  lea     rcx, [rbp+160h+var_1D0]
0x18001281f  call    ?get@?$consume_Windows_Foundation_IAsyncOperation@U?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@UDeviceInformation@Enumeration@Devices@34@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Devices::Enumeration::DeviceInformation>,winrt::Windows::Devices::Enumeration::DeviceInformation>::get(void)
0x180012824  nop
0x180012825  cmp     qword ptr [rbp+160h+var_1D0], r15
0x180012829  jz      short loc_180012835
0x18001282b  lea     rcx, [rbp+160h+var_1D0]
0x18001282f  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180012834  nop
0x180012835  cmp     [rbp+160h+var_128], r15b
0x180012839  jnz     short loc_180012844
0x18001283b  mov     rax, r15
0x18001283e  mov     [rbp+160h+var_130], rax
0x180012842  jmp     short loc_180012848
0x180012844  mov     rax, [rbp+160h+var_130]
0x180012848  test    rax, rax
0x18001284b  jz      short loc_180012856
0x18001284d  lea     rcx, [rbp+160h+var_130]
0x180012851  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180012856  lea     rdx, [rbp+160h+var_1E0]
0x18001285a  lea     rcx, [rsp+260h+var_1F0]
0x18001285f  call    ?Properties@?$consume_Windows_Devices_Enumeration_IDeviceInformation@UIDeviceInformation@Enumeration@Devices@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Properties(void)
0x180012864  nop
0x180012865  mov     dword ptr [rbp+160h+var_1A8+8], r14d
0x180012869  mov     dword ptr [rbp+160h+var_1A8+0Ch], 28h ; '('
0x180012870  lea     rcx, a2bf8a79a79ff49; "{2BF8A79A-79FF-49BC-9126-372815B153C8},"...
0x180012877  mov     [rbp+160h+var_190], rcx
0x18001287b  lea     rcx, [rbp+160h+var_1A8+8]
0x18001287f  mov     qword ptr [rbp+160h+var_1A8], rcx
0x180012883  lea     r8, [rbp+160h+var_1A8]
0x180012887  lea     rdx, [rsp+260h+var_200]
0x18001288c  mov     rcx, rax
0x18001288f  call    ?Lookup@?$consume_Windows_Foundation_Collections_IMapView@U?$IMapView@Uhstring@winrt@@UIInspectable@Foundation@Windows@2@@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMapView<winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Windows::Foundation::IInspectable>,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(winrt::param::hstring const &)
0x180012894  nop
0x180012895  cmp     [rbp+160h+var_1E0], r15
0x180012899  jz      short loc_1800128A4
0x18001289b  lea     rcx, [rbp+160h+var_1E0]
0x18001289f  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800128a4  mov     [rbp+160h+lpMem], r15
0x1800128a8  lea     rdx, [rbp+160h+lpMem]
0x1800128ac  lea     rcx, [rsp+260h+var_200]
0x1800128b1  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x1800128b6  test    al, al
0x1800128b8  jz      short loc_1800128DD
0x1800128ba  mov     edx, 42h ; 'B'; void *
0x1800128bf  mov     rcx, [rbp+168h]; this
0x1800128c6  mov     r9d, 80070057h; char *
0x1800128cc  lea     r8, aAvcoreMidi2Tra_5; "avcore\\midi2\\transport\\kstransport\\"...
0x1800128d3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800128d8  jmp     loc_180012F4A
0x1800128dd  lea     rdx, [rsp+260h+var_200]
0x1800128e2  lea     rcx, [rbp+160h+lpMem]
0x1800128e6  call    ??$unbox_value@Uhstring@winrt@@@winrt@@YA?AUhstring@0@AEBUIInspectable@Foundation@Windows@0@@Z; winrt::unbox_value<winrt::hstring>(winrt::Windows::Foundation::IInspectable const &)
0x1800128eb  nop
0x1800128ec  mov     r9, [rax]
0x1800128ef  test    r9, r9
0x1800128f2  jz      short loc_1800128FA
0x1800128f4  mov     r9, [r9+10h]
0x1800128f8  jmp     short loc_180012901
0x1800128fa  lea     r9, S1
0x180012901  mov     rdx, rsi
0x180012904  inc     rdx
0x180012907  cmp     [r9+rdx*2], r15w
0x18001290c  jnz     short loc_180012904
0x18001290e  cmp     rdx, [rbp+160h+var_138]
0x180012912  ja      short loc_180012944
0x180012914  lea     rdi, [rbp+160h+var_150]
0x180012918  cmp     [rbp+160h+var_138], 7
0x18001291d  cmova   rdi, [rbp+160h+var_150]
0x180012922  mov     [rbp+160h+var_140], rdx
0x180012926  lea     rbx, [rdx+rdx]
0x18001292a  mov     r8, rbx; Size
0x18001292d  mov     rdx, r9; Src
0x180012930  mov     rcx, rdi; void *
0x180012933  call    memmove_0
0x180012938  mov     [rdi+rbx], r15w
0x18001293d  mov     edi, 4
0x180012942  jmp     short loc_18001294E
0x180012944  lea     rcx, [rbp+160h+var_150]
0x180012948  call    ??$_Reallocate_for@V_lambda_1_@?1???$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV23@QEBG_K@Z@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Assign@G@01@AEAAAEAV01@QEBG0@Z@PEBG@Z; std::wstring::_Reallocate_for<`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *>(unsigned __int64,`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *)
0x18001294d  nop
0x18001294e  mov     rbx, [rbp+160h+lpMem]
0x180012952  test    rbx, rbx
0x180012955  jz      short loc_18001297A
0x180012957  mov     eax, esi
0x180012959  lock xadd [rbx+18h], eax
0x18001295e  sub     eax, 1
0x180012961  jnz     loc_180012A22
0x180012967  nop
0x180012968  call    WINRT_IMPL_GetProcessHeap
0x18001296d  mov     rcx, rax; hHeap
0x180012970  mov     r8, rbx; lpMem
0x180012973  xor     edx, edx; dwFlags
0x180012975  call    WINRT_IMPL_HeapFree
0x18001297a  lea     rdx, [rbp+160h+var_1D0]
0x18001297e  lea     rcx, [rsp+260h+var_1F0]
0x180012983  call    ?Properties@?$consume_Windows_Devices_Enumeration_IDeviceInformation@UIDeviceInformation@Enumeration@Devices@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Properties(void)
  ... truncated ...
```
