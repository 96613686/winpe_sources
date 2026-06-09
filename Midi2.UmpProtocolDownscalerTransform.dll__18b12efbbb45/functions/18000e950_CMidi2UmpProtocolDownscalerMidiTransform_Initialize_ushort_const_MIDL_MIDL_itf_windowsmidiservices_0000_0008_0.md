# CMidi2UmpProtocolDownscalerMidiTransform::Initialize(ushort const *,__MIDL___MIDL_itf_windowsmidiservices_0000_0008_0001 *,ulong *,IMidiCallback *,__int64,IMidiDeviceManager *)

- ea: `0x18000e950`
- end: `0x18000f737`
- name: `?Initialize@CMidi2UmpProtocolDownscalerMidiTransform@@UEAAJPEBGPEAU__MIDL___MIDL_itf_windowsmidiservices_0000_0008_0001@@PEAKPEAUIMidiCallback@@_JPEAUIMidiDeviceManager@@@Z`
- size: `3559`
- prototype: `__int64 __fastcall(CMidi2UmpProtocolDownscalerMidiTransform *__hidden this, const unsigned __int16 *, struct __MIDL___MIDL_itf_windowsmidiservices_0000_0008_0001 *, unsigned int *, struct IMidiCallback *, __int64, struct IMidiDeviceManager *)`
- caller_count: `0`
- callee_count: `36`
- tags: `file_ops, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1800016dc`
- `0x180002e70`
- `0x180002e94`
- `0x180002ec0`
- `0x180002f04`
- `0x180003ab0`
- `0x180003b1c`
- `0x180008924`
- `0x180009ce8`
- `0x18000a798`
- `0x18000b10c`
- `0x18000b1d0`
- `0x18000b238`
- `0x18000b8fc`
- `0x18000bafc`
- `0x18000c140`
- `0x18000c264`
- `0x18000c450`
- `0x18000c62c`
- `0x18000d0ac`
- `0x18000d118`
- `0x18000d188`
- `0x18000d1f8`
- `0x18000d4d4`
- `0x18000d5a0`
- `0x18000d66c`
- `0x18000d70c`
- `0x18000e640`
- `0x18000e950`
- `0x18000f7f4`
- `0x18000fe40`
- `0x180011044`
- `0x1800116c4`
- `0x180011a4c`
- `0x180011e0c`
- `0x180013010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18000ec62`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18000f001`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18000f21c`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18000f6f4`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18000ec62`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18000f001`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18000f21c`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18000f6f4`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x18000eac4`

## string_xrefs

- `0x18000e9a7`: `CMidi2UmpProtocolDownscalerMidiTransform::Initialize`
- `0x18000e9f4`: `avcore\midi2\transform\umpprotocoldownscaler\midi2.umpprotocoldownscalermiditransform.cpp`
- `0x18000ed88`: `avcore\midi2\transform\umpprotocoldownscaler\midi2.umpprotocoldownscalermiditransform.cpp`
- `0x18000ee0c`: `avcore\midi2\transform\umpprotocoldownscaler\midi2.umpprotocoldownscalermiditransform.cpp`
- `0x18000ee9e`: `avcore\midi2\transform\umpprotocoldownscaler\midi2.umpprotocoldownscalermiditransform.cpp`
- `0x18000ef36`: `avcore\midi2\transform\umpprotocoldownscaler\midi2.umpprotocoldownscalermiditransform.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMidi2UmpProtocolDownscalerMidiTransform::Initialize(
        CMidi2UmpProtocolDownscalerMidiTransform *this,
        const unsigned __int16 *a2,
        struct __MIDL___MIDL_itf_windowsmidiservices_0000_0008_0001 *a3,
        unsigned int *a4,
        struct IMidiCallback *a5,
        __int64 a6)
{
  _DWORD *v9; // rcx
  int v10; // r8d
  int v11; // r9d
  __int64 v12; // rdx
  __int64 v14; // r8
  __int64 v15; // r13
  __int64 v16; // rbx
  __int128 *v17; // r15
  __int128 *v18; // rcx
  unsigned __int16 *v19; // rbx
  unsigned __int16 *v20; // rsi
  char **v21; // rbx
  unsigned __int64 v22; // rdx
  char *v23; // rax
  char *v24; // rcx
  unsigned int v25; // edx
  __int64 v26; // rbx
  struct winrt::impl::shared_hstring_header *v27; // rbx
  unsigned int v28; // edx
  struct winrt::impl::shared_hstring_header *v29; // rbx
  __int64 v30; // rcx
  int v31; // eax
  LPVOID v32; // rbx
  const wchar_t *v33; // rax
  __int64 v34; // rax
  __int64 v35; // rax
  __int64 v36; // rax
  __int64 v37; // rax
  __int64 *v38; // rsi
  __int64 *v39; // rdx
  unsigned int v40; // edx
  void *v41; // rbx
  int v42; // eax
  HANDLE ProcessHeap; // rax
  volatile signed __int32 *v44; // r13
  __int64 v45; // rdi
  struct winrt::impl::shared_hstring_header *v46; // rbx
  __int64 v47; // rax
  __int64 v48; // rax
  void *v49; // rdi
  int v50; // eax
  HANDLE v51; // rax
  void *v52; // rdi
  int v53; // eax
  HANDLE v54; // rax
  int v55; // eax
  HANDLE v56; // rax
  _BYTE *v57; // rax
  char *v58; // rbx
  char *v59; // rdi
  char *v60; // rcx
  __int64 *v61; // r15
  __int64 v62; // rcx
  __int64 v63; // rax
  __int64 v64; // rax
  char *v65; // rbx
  __int64 v66; // rcx
  int v67; // eax
  LPVOID v68; // rbx
  __int64 *v69; // rdi
  __int64 v70; // rsi
  __int64 v71; // rax
  __int64 v72; // rcx
  const wchar_t *v73; // rsi
  int v74; // eax
  LPVOID v75; // rbx
  LPVOID *v76; // rdi
  LPVOID v77; // rax
  LPVOID v78; // rax
  __int64 v79; // rcx
  LPVOID v80; // rdi
  int v81; // eax
  LPVOID v82; // rbx
  LPVOID *v83; // r12
  LPVOID v84; // rax
  LPVOID v85; // rax
  __int64 v86; // rcx
  int v87; // eax
  void *v88; // rbx
  int v89; // eax
  HANDLE v90; // rax
  int v91; // r14d
  HANDLE v92; // rax
  int v93; // [rsp+20h] [rbp-E0h]
  LPVOID v94; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID v95; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v96; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v97; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v98; // [rsp+60h] [rbp-A0h] BYREF
  char v99; // [rsp+70h] [rbp-90h]
  LPVOID lpMem[2]; // [rsp+80h] [rbp-80h] BYREF
  __int128 *Src; // [rsp+90h] [rbp-70h] BYREF
  __int128 v102; // [rsp+98h] [rbp-68h]
  __int64 v103; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v104; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v105; // [rsp+C0h] [rbp-40h] BYREF
  const wchar_t *v106; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v107; // [rsp+D0h] [rbp-30h] BYREF
  LPVOID v108; // [rsp+D8h] [rbp-28h] BYREF
  LPVOID v109; // [rsp+E0h] [rbp-20h] BYREF
  _QWORD v110[2]; // [rsp+E8h] [rbp-18h] BYREF
  _QWORD v111[2]; // [rsp+F8h] [rbp-8h] BYREF
  _QWORD v112[2]; // [rsp+108h] [rbp+8h] BYREF
  const wchar_t *v113; // [rsp+118h] [rbp+18h] BYREF
  const wchar_t *v114; // [rsp+120h] [rbp+20h]
  const wchar_t *v115; // [rsp+128h] [rbp+28h]
  char v116; // [rsp+130h] [rbp+30h] BYREF
  __int128 v117; // [rsp+138h] [rbp+38h] BYREF
  __int64 v118; // [rsp+148h] [rbp+48h]
  const wchar_t *v119; // [rsp+150h] [rbp+50h]
  __int128 v120; // [rsp+158h] [rbp+58h] BYREF
  __int128 v121; // [rsp+168h] [rbp+68h]
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]

  v9 = (_DWORD *)*((_QWORD *)MidiUmpProtocolDownscalerTransformTelemetryProvider::Instance() + 1);
  if ( *v9 > 4u )
  {
    lpMem[0] = (LPVOID)a2;
    v106 = L"Enter";
    v95 = this;
    v94 = "CMidi2UmpProtocolDownscalerMidiTransform::Initialize";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (_DWORD)v9,
      (unsigned int)&dword_18001739C,
      v10,
      v11,
      (__int64)&v94,
      (__int64)&v95,
      (__int64)&v106,
      (__int64)lpMem);
  }
  if ( *(_DWORD *)a3 != 2 )
  {
    v12 = 39;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"avcore\\midi2\\transform\\umpprotocoldownscaler\\midi2.umpprotocoldownscalermiditransform.cpp",
      (const char *)0x8007065ELL,
      v93);
    return 2147944030LL;
  }
  if ( *((_DWORD *)a3 + 1) != 2 )
  {
    v12 = 40;
    goto LABEL_5;
  }
  v117 = 0;
  v118 = 0;
  v119 = 0;
  v14 = -1;
  do
    ++v14;
  while ( a2[v14] );
  std::wstring::_Construct<1,unsigned short const *>(&v117, a2);
  v15 = std::wstring::wstring(&v98, &v117);
  v16 = std::wstring::wstring(&v113, v15);
  std::wstring::wstring(&Src, v16);
  WindowsMidiServicesInternal::InPlaceTrim(&Src);
  std::wstring::~wstring(v16);
  std::wstring::wstring(&v120, &Src);
  v17 = &v120;
  if ( *((_QWORD *)&v121 + 1) > 7u )
    v17 = (__int128 *)v120;
  v18 = &v120;
  if ( *((_QWORD *)&v121 + 1) > 7u )
    v18 = (__int128 *)v120;
  v19 = (unsigned __int16 *)v18 + v121;
  v20 = (unsigned __int16 *)&v120;
  if ( *((_QWORD *)&v121 + 1) > 7u )
    v20 = (unsigned __int16 *)v120;
  while ( v20 != v19 )
  {
    *(_WORD *)v17 = ((__int64 (__fastcall *)(_QWORD))_o_towlower)(*v20);
    v17 = (__int128 *)((char *)v17 + 2);
    ++v20;
  }
  std::wstring::~wstring(&Src);
  std::wstring::~wstring(v15);
  v21 = (char **)((char *)this + 104);
  if ( (__int128 *)((char *)this + 104) != &v120 )
  {
    v22 = *((_QWORD *)this + 16);
    if ( v22 > 7 )
    {
      v23 = *v21;
      if ( 2 * v22 + 2 < 0x1000 )
      {
        v24 = *v21;
      }
      else
      {
        v24 = (char *)*((_QWORD *)v23 - 1);
        if ( (unsigned __int64)(v23 - v24 - 8) > 0x1F )
          __fastfail(5u);
      }
      operator delete(v24);
    }
    *(_OWORD *)v21 = v120;
    *(_OWORD *)((char *)this + 120) = v121;
    *(_QWORD *)&v121 = 0;
    *((_QWORD *)&v121 + 1) = 7;
    LOWORD(v120) = 0;
  }
  std::wstring::~wstring(&v120);
  std::wstring::~wstring(&v117);
  v26 = *((_QWORD *)this + 17);
  *((_QWORD *)this + 17) = a5;
  if ( a5 )
    (*(void (__fastcall **)(struct IMidiCallback *))(*(_QWORD *)a5 + 8LL))(a5);
  if ( v26 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
  *((_QWORD *)this + 18) = a6;
  v27 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)0x2A, v25);
  memcpy_s((char *)v27 + 28, 0x54u, L"{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} 151", 0x54u);
  lpMem[0] = v27;
  v29 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)0x2A, v28);
  memcpy_s((char *)v29 + 28, 0x54u, L"{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} 150", 0x54u);
  lpMem[1] = v29;
  *(_QWORD *)&v98 = lpMem;
  *((_QWORD *)&v98 + 1) = &Src;
  winrt::param::async_iterable<winrt::hstring>::async_iterable<winrt::hstring>(&v113, &v98);
  v30 = -1;
  do
    ++v30;
  while ( a2[v30] );
  if ( (_DWORD)v30 )
  {
    if ( a2[(unsigned int)v30] )
      abort();
    DWORD2(v117) = 1;
    HIDWORD(v117) = v30;
    v119 = a2;
    *(_QWORD *)&v117 = (char *)&v117 + 8;
  }
  else
  {
    *(_QWORD *)&v117 = 0;
  }
  *(_QWORD *)&v98 = &v117;
  *((_QWORD *)&v98 + 1) = &v113;
  _InterlockedAdd64(&qword_18001B928, 1u);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics> )
  {
    v94 = 0;
    LODWORD(Src) = 792;
    *(_QWORD *)&v102 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt/Windows.Devices.Enumeration.h";
    *((_QWORD *)&v102 + 1) = 0;
    v31 = (*(__int64 (__fastcall **)(__int64, _QWORD, const wchar_t *, LPVOID *))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics>
                                                                                + 56LL))(
            winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics>,
            v117,
            v113,
            &v94);
    if ( v31 < 0 )
      winrt::throw_hresult((unsigned int)v31, &Src);
    v32 = v94;
    _InterlockedAdd64(&qword_18001B928, 0xFFFFFFFFFFFFFFFFuLL);
  }
  else
  {
    _InterlockedAdd64(&qword_18001B928, 0xFFFFFFFFFFFFFFFFuLL);
    ___call_AEAV_lambda_1___1__CreateFromIdAsync_DeviceInformation_Enumeration_Devices_Windows_winrt__SA_AEBUhstring_param_7_AEBU__async_iterable_Uhstring_winrt___97__Z____factory_cache_entry_UDeviceInformation_Enumeration_Devices_Windows_winrt__UIDeviceInformationStatics_2345__impl_winrt__QEAA_A_PAEAV_lambda_1___1__CreateFromIdAsync_DeviceInformation_Enumeration_Devices_Windows_2_SA_AEBUhstring_param_2_AEBU__async_iterable_Uhstring_winrt___param_2__Z__Z(
      0,
      &v94,
      &v98);
    v32 = v94;
  }
  winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Devices::Enumeration::DeviceInformation>,winrt::Windows::Devices::Enumeration::DeviceInformation>::get(
    &v94,
    &v96);
  if ( v32 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v94);
  if ( (_BYTE)v114 )
  {
    v33 = v113;
  }
  else
  {
    v33 = 0;
    v113 = 0;
  }
  if ( v33 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v113);
  `eh vector destructor iterator'(lpMem, 8u, 2u, (void (*)(void *))winrt::hstring::~hstring);
  lpMem[0] = 0;
  if ( (unsigned __int8)winrt::Windows::Foundation::operator==(&v96, lpMem) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x38,
      (unsigned int)"avcore\\midi2\\transform\\umpprotocoldownscaler\\midi2.umpprotocoldownscalermiditransform.cpp",
      (const char *)0x80070057LL,
      v93);
LABEL_68:
    if ( v96 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v96);
    return 2147942487LL;
  }
  v34 = winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Properties(
          &v96,
          &v94);
  *((_QWORD *)&v117 + 1) = 0x2A00000001LL;
  v119 = L"{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} 151";
  *(_QWORD *)&v117 = (char *)&v117 + 8;
  winrt::impl::consume_Windows_Foundation_Collections_IMapView<winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Windows::Foundation::IInspectable>,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(
    v34,
    &v97,
    &v117);
  if ( v94 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v94);
  lpMem[0] = 0;
  if ( (unsigned __int8)winrt::Windows::Foundation::operator==(&v97, lpMem) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3B,
      (unsigned int)"avcore\\midi2\\transform\\umpprotocoldownscaler\\midi2.umpprotocoldownscalermiditransform.cpp",
      (const char *)0x80070057LL,
      v93);
LABEL_66:
    if ( v97 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v97);
    goto LABEL_68;
  }
  *((_BYTE *)this + 98) = winrt::unbox_value<bool>(&v97);
  v35 = winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Properties(
          &v96,
          &v94);
  *((_QWORD *)&v117 + 1) = 0x2A00000001LL;
  v119 = L"{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} 150";
  *(_QWORD *)&v117 = (char *)&v117 + 8;
  winrt::impl::consume_Windows_Foundation_Collections_IMapView<winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Windows::Foundation::IInspectable>,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(
    v35,
    &v103,
    &v117);
  if ( v94 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v94);
  lpMem[0] = 0;
  if ( (unsigned __int8)winrt::Windows::Foundation::operator==(&v97, lpMem) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3F,
      (unsigned int)"avcore\\midi2\\transform\\umpprotocoldownscaler\\midi2.umpprotocoldownscalermiditransform.cpp",
      (const char *)0x80070057LL,
      v93);
LABEL_64:
    if ( v103 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v103);
    goto LABEL_66;
  }
  *((_BYTE *)this + 99) = winrt::unbox_value<bool>(&v103);
  v95 = 0;
  v36 = winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Properties(
          &v96,
          &v94);
  *((_QWORD *)&v117 + 1) = 0x1F00000001LL;
  v119 = L"System.Devices.DeviceInstanceId";
  *(_QWORD *)&v117 = (char *)&v117 + 8;
  winrt::impl::consume_Windows_Foundation_Collections_IMapView<winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Windows::Foundation::IInspectable>,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(
    v36,
    &v105,
    &v117);
  if ( v94 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v94);
  lpMem[0] = 0;
  if ( (unsigned __int8)winrt::Windows::Foundation::operator==(&v105, lpMem) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x46,
      (unsigned int)"avcore\\midi2\\transform\\umpprotocoldownscaler\\midi2.umpprotocoldownscalermiditransform.cpp",
      (const char *)0x80070057LL,
      v93);
    if ( v105 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v105);
    goto LABEL_64;
  }
  v37 = winrt::unbox_value<winrt::hstring>(lpMem, &v105);
  v38 = &qword_180015B20;
  if ( *(_QWORD *)v37 )
    v39 = *(__int64 **)(*(_QWORD *)v37 + 16LL);
  else
    v39 = &qword_180015B20;
  winrt::hstring::operator=(&v95, v39);
  v41 = lpMem[0];
  if ( lpMem[0] )
  {
    v42 = _InterlockedDecrement((volatile signed __int32 *)lpMem[0] + 6);
    if ( v42 )
    {
      if ( v42 < 0 )
        abort();
    }
    else
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, v41);
    }
  }
  v44 = (volatile signed __int32 *)v95;
  if ( v95 )
  {
    v45 = *((unsigned int *)v95 + 1);
    v38 = (__int64 *)*((_QWORD *)v95 + 2);
  }
  else
  {
    v45 = 0;
  }
  if ( (_DWORD)v45 == -34 )
  {
    v46 = 0;
  }
  else
  {
    v46 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)(unsigned int)(v45 + 34), v40);
    memcpy_s(*((void *const *)v46 + 2), 0x44u, L"System.Devices.DeviceInstanceId:=\"", 0x44u);
    memcpy_s((void *const)(*((_QWORD *)v46 + 2) + 68LL), 2 * v45, v38, 2 * v45);
  }
  lpMem[0] = v46;
  v47 = winrt::operator+(&v94, lpMem, L"\" AND ");
  v48 = winrt::operator+(
          &v95,
          v47,
          L"System.Devices.InterfaceClassGuid:=\"{6994AD04-93EF-11D0-A3CC-00A0C9223196}\" AND ");
  winrt::operator+(lpMem, v48, L"System.Devices.InterfaceEnabled: = System.StructuredQueryType.Boolean#True");
  v49 = v95;
  if ( v95 )
  {
    v50 = _InterlockedDecrement((volatile signed __int32 *)v95 + 6);
    if ( v50 )
    {
      if ( v50 < 0 )
        goto LABEL_103;
    }
    else
    {
      v51 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v51, 0, v49);
    }
    v95 = 0;
  }
  v52 = v94;
  if ( v94 )
  {
    v53 = _InterlockedDecrement((volatile signed __int32 *)v94 + 6);
    if ( v53 )
    {
      if ( v53 < 0 )
        goto LABEL_103;
    }
    else
    {
      v54 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v54, 0, v52);
    }
    v94 = 0;
  }
  if ( !v46 )
    goto LABEL_98;
  v55 = _InterlockedDecrement((volatile signed __int32 *)v46 + 6);
  if ( !v55 )
  {
    v56 = WINRT_IMPL_GetProcessHeap();
    WINRT_IMPL_HeapFree(v56, 0, v46);
    goto LABEL_98;
  }
  if ( v55 < 0 )
LABEL_103:
    abort();
LABEL_98:
  LODWORD(v94) = 1;
  v113 = L"{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} 400";
  v114 = L"{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} 151";
  v115 = L"{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} 150";
  v98 = 0;
  v57 = operator new(0x30u);
  v58 = v57 + 24;
  v57[24] = 0;
  v59 = v57 + 16;
  *((_QWORD *)v57 + 2) = &winrt::impl::produce<winrt::impl::scoped_input_iterable<winrt::hstring,unsigned short const * const *>,winrt::Windows::Foundation::Collections::IIterable<winrt::hstring>>::`vftable';
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *((_DWORD *)v57 + 2) = 1;
  *(_QWORD *)v57 = &winrt::impl::scoped_input_iterable<winrt::hstring,unsigned short const * const *>::`vftable';
  *((_QWORD *)v57 + 4) = &v113;
  v60 = &v116;
  *((_QWORD *)v57 + 5) = &v116;
  if ( (_QWORD)v98 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v98);
  *(_QWORD *)&v98 = v59;
  *((_QWORD *)&v98 + 1) = v58;
  v99 = 1;
  *(LPVOID *)&v117 = lpMem[0];
  Src = &v117;
  *(_QWORD *)&v102 = &v98;
  *((_QWORD *)&v102 + 1) = &v94;
  _InterlockedAdd64(&qword_18001B948, 1u);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2> )
  {
    `winrt::Windows::Devices::Enumeration::DeviceInformation::CreateWatcher'::`2'::_lambda_1_::operator()(
      &Src,
      &v104,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>);
    _InterlockedAdd64(&qword_18001B948, 0xFFFFFFFFFFFFFFFFuLL);
  }
  else
  {
    _InterlockedAdd64(&qword_18001B948, 0xFFFFFFFFFFFFFFFFuLL);
    ___call_AEAV_lambda_1___1__CreateWatcher_DeviceInformation_Enumeration_Devices_Windows_winrt__SA_AEBUhstring_param_7_AEBU__iterable_Uhstring_winrt___97_AEBW4DeviceInformationKind_4567__Z____factory_cache_entry_UDeviceInformation_Enumeration_Devices_Windows_winrt__UIDeviceInformationStatics2_2345__impl_winrt__QEAA_A_PAEAV_lambda_1___1__CreateWatcher_DeviceInformation_Enumeration_Devices_Windows_2_SA_AEBUhstring_param_2_AEBU__iterable_Uhstring_winrt___param_2_AEBW4DeviceInformationKind_6782__Z__Z(
      v60,
      &v104,
      &Src);
  }
  v61 = (__int64 *)((char *)this + 152);
  if ( (__int64 *)((char *)this + 152) == &v104 )
  {
    v63 = v104;
  }
  else
  {
    if ( *v61 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((char *)this + 152);
    v62 = v104;
    v63 = 0;
    v104 = 0;
    *v61 = v62;
  }
  if ( v63 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v104);
  if ( *((_QWORD *)&v98 + 1) )
    **((_BYTE **)&v98 + 1) = 1;
  if ( v99 )
  {
    v64 = v98;
  }
  else
  {
    v64 = 0;
    *(_QWORD *)&v98 = 0;
  }
  if ( v64 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v98);
  *(_QWORD *)&v102 = &CMidi2UmpProtocolDownscalerMidiTransform::OnDeviceRemoved;
  DWORD2(v102) = 0;
  HIDWORD(v102) = HIDWORD(v98);
  v65 = (char *)operator new(0x28u);
  *((_DWORD *)v65 + 2) = 1;
  *((_QWORD *)v65 + 2) = this;
  *(_OWORD *)(v65 + 24) = v102;
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *(_QWORD *)v65 = ___7__delegate_U__TypedEventHandler_UDeviceWatcher_Enumeration_Devices_Windows_winrt__UDeviceInformation_2345__Foundation_Windows_winrt__V_lambda_16____0_____0VCMidi2UmpProtocolDownscalerMidiTransform__P80_EAAJUDeviceWatcher_Enumeration_Devices_Windows_winrt__UDeviceInformation_2345__Z_1234_QEAA_PEAVCMidi2UmpProtocolDownscalerMidiTransform__P86_EAAJUDeviceWatcher_Enumeration_Devices_34_UDeviceInformation_8934__Z_Z__impl_winrt__6B_;
  v113 = (const wchar_t *)v65;
  *(_QWORD *)&v98 = &CMidi2UmpProtocolDownscalerMidiTransform::OnDeviceRemoved;
  DWORD2(v98) = 0;
  winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformationUpdate>::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformationUpdate>(
    &v106,
    this,
    &v98);
  *(_QWORD *)&v98 = &CMidi2UmpProtocolDownscalerMidiTransform::OnDeviceUpdated;
  DWORD2(v98) = 0;
  winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformationUpdate>::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformationUpdate>(
    &v94,
    this,
    &v98);
  v95 = 0;
  v66 = *v61;
  LODWORD(Src) = 1938;
  *(_QWORD *)&v102 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Devices.Enumeration.h";
  *((_QWORD *)&v102 + 1) = 0;
  v67 = (*(__int64 (__fastcall **)(__int64, char *, LPVOID *))(*(_QWORD *)v66 + 48LL))(v66, v65, &v95);
  if ( v67 < 0 )
    winrt::throw_hresult((unsigned int)v67, &Src);
  v68 = v95;
  winrt::weak_ref<winrt::Windows::Devices::Enumeration::IDeviceWatcher>::weak_ref<winrt::Windows::Devices::Enumeration::IDeviceWatcher>(
    &v98,
    (char *)this + 152);
  *((_QWORD *)&v98 + 1) = v68;
  v69 = (__int64 *)((char *)this + 160);
  v70 = v98;
  *(_QWORD *)&v98 = 0;
  v110[0] = 0;
  v107 = v70;
  if ( v110 != (_QWORD *)((char *)this + 160) )
  {
    v71 = *v69;
    *v69 = 0;
    v110[0] = v71;
  }
  if ( v69 == &v107 )
  {
    if ( v70 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v107);
  }
  else
  {
    if ( *v69 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v69);
    *v69 = v70;
  }
  v110[1] = *((_QWORD *)this + 21);
  *((_QWORD *)this + 21) = v68;
  __1__event_revoker_UIDeviceWatcher_Enumeration_Devices_Windows_winrt___MP8type___abi_UIDeviceWatcher_Enumeration_Devices_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BDI_AA_impl_winrt__QEAA_XZ(v110);
  __1__event_revoker_UIDeviceWatcher_Enumeration_Devices_Windows_winrt___MP8type___abi_UIDeviceWatcher_Enumeration_Devices_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BDI_AA_impl_winrt__QEAA_XZ(&v98);
  v95 = 0;
  v72 = *v61;
  LODWORD(Src) = 2014;
  *(_QWORD *)&v102 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Devices.Enumeration.h";
  *((_QWORD *)&v102 + 1) = 0;
  v73 = v106;
  v74 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, LPVOID *))(*(_QWORD *)v72 + 80LL))(v72, v106, &v95);
  if ( v74 < 0 )
    winrt::throw_hresult((unsigned int)v74, &Src);
  v75 = v95;
  winrt::weak_ref<winrt::Windows::Devices::Enumeration::IDeviceWatcher>::weak_ref<winrt::Windows::Devices::Enumeration::IDeviceWatcher>(
    &v98,
    (char *)this + 152);
  *((_QWORD *)&v98 + 1) = v75;
  v76 = (LPVOID *)((char *)this + 176);
  v77 = (LPVOID)v98;
  v95 = (LPVOID)v98;
  *(_QWORD *)&v98 = 0;
  v111[0] = 0;
  v108 = v95;
  if ( v111 != (_QWORD *)((char *)this + 176) )
  {
    v78 = *v76;
    *v76 = 0;
    v111[0] = v78;
    v77 = v95;
  }
  if ( v76 == &v108 )
  {
    if ( v77 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v108);
  }
  else
  {
    if ( *v76 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((char *)this + 176);
    *v76 = v95;
  }
  v111[1] = *((_QWORD *)this + 23);
  *((_QWORD *)this + 23) = v75;
  __1__event_revoker_UIDeviceWatcher_Enumeration_Devices_Windows_winrt___MP8type___abi_UIDeviceWatcher_Enumeration_Devices_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BFI_AA_impl_winrt__QEAA_XZ(v111);
  __1__event_revoker_UIDeviceWatcher_Enumeration_Devices_Windows_winrt___MP8type___abi_UIDeviceWatcher_Enumeration_Devices_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BFI_AA_impl_winrt__QEAA_XZ(&v98);
  v95 = 0;
  v79 = *v61;
  LODWORD(Src) = 1976;
  *(_QWORD *)&v102 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Devices.Enumeration.h";
  *((_QWORD *)&v102 + 1) = 0;
  v80 = v94;
  v81 = (*(__int64 (__fastcall **)(__int64, LPVOID, LPVOID *))(*(_QWORD *)v79 + 64LL))(v79, v94, &v95);
  if ( v81 < 0 )
    winrt::throw_hresult((unsigned int)v81, &Src);
  v82 = v95;
  winrt::weak_ref<winrt::Windows::Devices::Enumeration::IDeviceWatcher>::weak_ref<winrt::Windows::Devices::Enumeration::IDeviceWatcher>(
    &v98,
    (char *)this + 152);
  *((_QWORD *)&v98 + 1) = v82;
  v83 = (LPVOID *)((char *)this + 192);
  v84 = (LPVOID)v98;
  v95 = (LPVOID)v98;
  *(_QWORD *)&v98 = 0;
  v112[0] = 0;
  v109 = v95;
  if ( v112 != v83 )
  {
    v85 = *v83;
    *v83 = 0;
    v112[0] = v85;
    v84 = v95;
  }
  if ( v83 == &v109 )
  {
    if ( v84 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v109);
  }
  else
  {
    if ( *v83 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v83);
    *v83 = v95;
  }
  v112[1] = v83[1];
  v83[1] = v82;
  __1__event_revoker_UIDeviceWatcher_Enumeration_Devices_Windows_winrt___MP8type___abi_UIDeviceWatcher_Enumeration_Devices_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BEI_AA_impl_winrt__QEAA_XZ(v112);
  __1__event_revoker_UIDeviceWatcher_Enumeration_Devices_Windows_winrt___MP8type___abi_UIDeviceWatcher_Enumeration_Devices_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BEI_AA_impl_winrt__QEAA_XZ(&v98);
  v86 = *v61;
  LODWORD(Src) = 2145;
  *(_QWORD *)&v102 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Devices.Enumeration.h";
  *((_QWORD *)&v102 + 1) = 0;
  v87 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v86 + 136LL))(v86);
  if ( v87 < 0 )
    winrt::throw_hresult((unsigned int)v87, &Src);
  if ( v80 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v94);
  if ( v73 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v106);
  winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v113);
  v88 = lpMem[0];
  if ( lpMem[0] )
  {
    v89 = _InterlockedDecrement((volatile signed __int32 *)lpMem[0] + 6);
    if ( v89 )
    {
      if ( v89 < 0 )
        goto LABEL_168;
    }
    else
    {
      v90 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v90, 0, v88);
    }
  }
  if ( v105 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v105);
  if ( !v44 )
    goto LABEL_160;
  v91 = _InterlockedDecrement(v44 + 6);
  if ( v91 )
  {
    if ( v91 >= 0 )
      goto LABEL_160;
LABEL_168:
    abort();
  }
  v92 = WINRT_IMPL_GetProcessHeap();
  WINRT_IMPL_HeapFree(v92, 0, (LPVOID)v44);
LABEL_160:
  if ( v103 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v103);
  if ( v97 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v97);
  if ( v96 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v96);
  return 0;
}

```

## disassembly

```asm
0x18000e950  mov     [rsp-8+arg_10], rbx
0x18000e955  push    rbp
0x18000e956  push    rsi
0x18000e957  push    rdi
0x18000e958  push    r12
0x18000e95a  push    r13
0x18000e95c  push    r14
0x18000e95e  push    r15
0x18000e960  lea     rbp, [rsp-80h]
0x18000e965  sub     rsp, 180h
0x18000e96c  mov     rax, cs:__security_cookie
0x18000e973  xor     rax, rsp
0x18000e976  mov     [rbp+0B0h+var_38], rax
0x18000e97a  mov     rbx, r8
0x18000e97d  mov     rdi, rdx
0x18000e980  mov     r12, rcx
0x18000e983  call    ?Instance@MidiUmpProtocolDownscalerTransformTelemetryProvider@@KAPEAV1@XZ; MidiUmpProtocolDownscalerTransformTelemetryProvider::Instance(void)
0x18000e988  mov     rcx, [rax+8]
0x18000e98c  mov     eax, [rcx]
0x18000e98e  cmp     eax, 4
0x18000e991  jbe     short loc_18000E9E5
0x18000e993  mov     [rbp+0B0h+lpMem], rdi
0x18000e997  lea     rax, aEnter; "Enter"
0x18000e99e  mov     [rbp+0B0h+var_E8], rax
0x18000e9a2  mov     [rsp+1B0h+var_168], r12
0x18000e9a7  lea     rax, aCmidi2umpproto_1; "CMidi2UmpProtocolDownscalerMidiTransfor"...
0x18000e9ae  mov     [rsp+1B0h+var_170], rax
0x18000e9b3  lea     rax, [rbp+0B0h+lpMem]
0x18000e9b7  mov     [rsp+1B0h+var_178], rax
0x18000e9bc  lea     rax, [rbp+0B0h+var_E8]
0x18000e9c0  mov     [rsp+1B0h+var_180], rax
0x18000e9c5  lea     rax, [rsp+1B0h+var_168]
0x18000e9ca  mov     [rsp+1B0h+var_188], rax
0x18000e9cf  lea     rax, [rsp+1B0h+var_170]
0x18000e9d4  mov     qword ptr [rsp+1B0h+var_190], rax; int
0x18000e9d9  lea     rdx, dword_18001739C
0x18000e9e0  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18000e9e5  cmp     dword ptr [rbx], 2
0x18000e9e8  jz      short loc_18000EA11
0x18000e9ea  mov     edx, 27h ; '''; void *
0x18000e9ef  mov     ebx, 8007065Eh
0x18000e9f4  lea     r8, aAvcoreMidi2Tra; "avcore\\midi2\\transform\\umpprotocoldo"...
0x18000e9fb  mov     r9d, ebx; char *
0x18000e9fe  mov     rcx, [rbp+0B8h]; this
0x18000ea05  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ea0a  mov     eax, ebx
0x18000ea0c  jmp     loc_18000F6C8
0x18000ea11  cmp     dword ptr [rbx+4], 2
0x18000ea15  jz      short loc_18000EA1E
0x18000ea17  mov     edx, 28h ; '('
0x18000ea1c  jmp     short loc_18000E9EF
0x18000ea1e  xorps   xmm0, xmm0
0x18000ea21  movups  [rbp+0B0h+var_78], xmm0
0x18000ea25  xor     eax, eax
0x18000ea27  mov     [rbp+0B0h+var_68], rax
0x18000ea2b  mov     [rbp+0B0h+var_60], rax
0x18000ea2f  or      r14, 0FFFFFFFFFFFFFFFFh
0x18000ea33  mov     r8, r14
0x18000ea36  inc     r8
0x18000ea39  cmp     [rdi+r8*2], ax
0x18000ea3e  jnz     short loc_18000EA36
0x18000ea40  mov     rdx, rdi
0x18000ea43  lea     rcx, [rbp+0B0h+var_78]
0x18000ea47  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000ea4c  lea     rdx, [rbp+0B0h+var_78]
0x18000ea50  lea     rcx, [rsp+1B0h+var_150]
0x18000ea55  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000ea5a  mov     r13, rax
0x18000ea5d  mov     rdx, rax
0x18000ea60  lea     rcx, [rbp+0B0h+var_98]
0x18000ea64  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000ea69  mov     rbx, rax
0x18000ea6c  mov     rdx, rax
0x18000ea6f  lea     rcx, [rbp+0B0h+Src]
0x18000ea73  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000ea78  lea     rcx, [rbp+0B0h+Src]; Src
0x18000ea7c  call    ?InPlaceTrim@WindowsMidiServicesInternal@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; WindowsMidiServicesInternal::InPlaceTrim(std::wstring &)
0x18000ea81  mov     rcx, rbx
0x18000ea84  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000ea89  lea     rdx, [rbp+0B0h+Src]
0x18000ea8d  lea     rcx, [rbp+0B0h+var_58]
0x18000ea91  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000ea96  lea     r15, [rbp+0B0h+var_58]
0x18000ea9a  mov     r8, qword ptr [rbp+0B0h+var_58]
0x18000ea9e  cmp     qword ptr [rbp+0B0h+var_48+8], 7
0x18000eaa3  cmova   r15, r8
0x18000eaa7  lea     rcx, [rbp+0B0h+var_58]
0x18000eaab  cmova   rcx, r8
0x18000eaaf  mov     rax, qword ptr [rbp+0B0h+var_48]
0x18000eab3  lea     rbx, [rcx+rax*2]
0x18000eab7  lea     rsi, [rbp+0B0h+var_58]
0x18000eabb  cmova   rsi, r8
0x18000eabf  jmp     short loc_18000EADC
0x18000eac1  movzx   ecx, word ptr [rsi]
0x18000eac4  mov     rax, cs:__imp__o_towlower
0x18000eacb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ead0  mov     [r15], ax
0x18000ead4  lea     r15, [r15+2]
0x18000ead8  add     rsi, 2
0x18000eadc  cmp     rsi, rbx
0x18000eadf  jnz     short loc_18000EAC1
0x18000eae1  lea     rcx, [rbp+0B0h+Src]
0x18000eae5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000eaea  mov     rcx, r13
0x18000eaed  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000eaf2  lea     rbx, [r12+68h]
0x18000eaf7  lea     rax, [rbp+0B0h+var_58]
0x18000eafb  cmp     rbx, rax
0x18000eafe  jz      short loc_18000EB69
0x18000eb00  mov     rdx, [rbx+18h]
0x18000eb04  cmp     rdx, 7
0x18000eb08  jbe     short loc_18000EB44
0x18000eb0a  mov     rax, [rbx]
0x18000eb0d  lea     rdx, ds:2[rdx*2]
0x18000eb15  cmp     rdx, 1000h
0x18000eb1c  jb      short loc_18000EB3C
0x18000eb1e  mov     rcx, [rax-8]
0x18000eb22  sub     rax, rcx
0x18000eb25  sub     rax, 8
0x18000eb29  cmp     rax, 1Fh
0x18000eb2d  ja      short loc_18000EB35
0x18000eb2f  add     rdx, 27h ; '''
0x18000eb33  jmp     short loc_18000EB3F
0x18000eb35  mov     ecx, 5
0x18000eb3a  int     29h; Win8: RtlFailFast(ecx)
0x18000eb3c  mov     rcx, rax; Block
0x18000eb3f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000eb44  movups  xmm0, [rbp+0B0h+var_58]
0x18000eb48  movups  xmmword ptr [rbx], xmm0
0x18000eb4b  movups  xmm1, [rbp+0B0h+var_48]
0x18000eb4f  movups  xmmword ptr [rbx+10h], xmm1
0x18000eb53  xor     r15d, r15d
0x18000eb56  mov     qword ptr [rbp+0B0h+var_48], r15
0x18000eb5a  mov     qword ptr [rbp+0B0h+var_48+8], 7
0x18000eb62  mov     word ptr [rbp+0B0h+var_58], r15w
0x18000eb67  jmp     short loc_18000EB6C
0x18000eb69  xor     r15d, r15d
0x18000eb6c  lea     rcx, [rbp+0B0h+var_58]
0x18000eb70  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000eb75  lea     rcx, [rbp+0B0h+var_78]
0x18000eb79  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000eb7e  nop
0x18000eb7f  mov     rbx, [r12+88h]
0x18000eb87  mov     rcx, [rbp+0B0h+arg_20]
0x18000eb8e  mov     [r12+88h], rcx
0x18000eb96  test    rcx, rcx
0x18000eb99  jz      short loc_18000EBA7
0x18000eb9b  mov     rax, [rcx]
0x18000eb9e  mov     rax, [rax+8]
0x18000eba2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eba7  test    rbx, rbx
0x18000ebaa  jz      short loc_18000EBBC
0x18000ebac  mov     rax, [rbx]
0x18000ebaf  mov     rcx, rbx
0x18000ebb2  mov     rax, [rax+10h]
0x18000ebb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ebbb  nop
0x18000ebbc  mov     rax, [rbp+0B0h+arg_28]
0x18000ebc3  mov     [r12+90h], rax
0x18000ebcb  mov     r13d, 2Ah ; '*'
0x18000ebd1  mov     ecx, r13d; this
0x18000ebd4  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x18000ebd9  mov     rbx, rax
0x18000ebdc  lea     rcx, [rax+1Ch]; Destination
0x18000ebe0  lea     esi, [r13+2Ah]
0x18000ebe4  mov     r9d, esi; SourceSize
0x18000ebe7  lea     r8, a3f114a6a11fa4b_1; "{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} "...
0x18000ebee  mov     edx, esi; DestinationSize
0x18000ebf0  call    memcpy_s
0x18000ebf5  mov     [rbp+0B0h+lpMem], rbx
0x18000ebf9  mov     ecx, r13d; this
0x18000ebfc  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x18000ec01  mov     rbx, rax
0x18000ec04  lea     rcx, [rax+1Ch]; Destination
0x18000ec08  mov     r9d, esi; SourceSize
0x18000ec0b  lea     r8, a3f114a6a11fa4b; "{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} "...
0x18000ec12  mov     edx, esi; DestinationSize
0x18000ec14  call    memcpy_s
0x18000ec19  mov     [rbp+0B0h+var_128], rbx
0x18000ec1d  lea     rax, [rbp+0B0h+lpMem]
0x18000ec21  mov     qword ptr [rsp+1B0h+var_150], rax
0x18000ec26  lea     rax, [rbp+0B0h+Src]
0x18000ec2a  mov     qword ptr [rsp+1B0h+var_150+8], rax
0x18000ec2f  lea     rdx, [rsp+1B0h+var_150]
0x18000ec34  lea     rcx, [rbp+0B0h+var_98]
0x18000ec38  call    ??0?$async_iterable@Uhstring@winrt@@@param@winrt@@QEAA@V?$initializer_list@Uhstring@winrt@@@std@@@Z; winrt::param::async_iterable<winrt::hstring>::async_iterable<winrt::hstring>(std::initializer_list<winrt::hstring>)
0x18000ec3d  mov     rcx, r14
0x18000ec40  inc     rcx
0x18000ec43  cmp     [rdi+rcx*2], r15w
0x18000ec48  jnz     short loc_18000EC40
0x18000ec4a  mov     esi, 1
0x18000ec4f  test    ecx, ecx
0x18000ec51  jnz     short loc_18000EC59
0x18000ec53  mov     qword ptr [rbp+0B0h+var_78], r15
0x18000ec57  jmp     short loc_18000EC7B
0x18000ec59  mov     eax, ecx
0x18000ec5b  cmp     [rdi+rax*2], r15w
0x18000ec60  jz      short loc_18000EC69
0x18000ec62  call    cs:__imp_abort
0x18000ec69  mov     dword ptr [rbp+0B0h+var_78+8], esi
0x18000ec6c  mov     dword ptr [rbp+0B0h+var_78+0Ch], ecx
0x18000ec6f  mov     [rbp+0B0h+var_60], rdi
0x18000ec73  lea     rax, [rbp+0B0h+var_78+8]
0x18000ec77  mov     qword ptr [rbp+0B0h+var_78], rax
0x18000ec7b  lea     rax, [rbp+0B0h+var_78]
0x18000ec7f  mov     qword ptr [rsp+1B0h+var_150], rax
0x18000ec84  lea     rax, [rbp+0B0h+var_98]
0x18000ec88  mov     qword ptr [rsp+1B0h+var_150+8], rax
0x18000ec8d  lock add cs:qword_18001B928, rsi
0x18000ec95  mov     rcx, cs:??$factory_cache_entry_v@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics@2345@@12@A; factory_cache_entry<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics>::winrt::factory_cache_entry<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics>
0x18000ec9c  test    rcx, rcx
0x18000ec9f  jz      short loc_18000ECF1
0x18000eca1  mov     [rsp+1B0h+var_170], r15
0x18000eca6  mov     dword ptr [rbp+0B0h+Src], 318h
0x18000ecad  lea     rax, aOnecoreuapInte_5; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x18000ecb4  mov     qword ptr [rbp+0B0h+var_118], rax
0x18000ecb8  mov     qword ptr [rbp+0B0h+var_118+8], r15
0x18000ecbc  mov     rax, [rcx]
0x18000ecbf  lea     r9, [rsp+1B0h+var_170]
0x18000ecc4  mov     r8, [rbp+0B0h+var_98]
0x18000ecc8  mov     rdx, qword ptr [rbp+0B0h+var_78]
0x18000eccc  mov     rax, [rax+38h]
0x18000ecd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ecd5  test    eax, eax
0x18000ecd7  js      loc_18000F707
0x18000ecdd  mov     rbx, [rsp+1B0h+var_170]
0x18000ece2  mov     [rsp+1B0h+var_170], rbx
0x18000ece7  lock add cs:qword_18001B928, r14
0x18000ecef  jmp     short loc_18000ED0D
0x18000ecf1  lock add cs:qword_18001B928, r14
0x18000ecf9  lea     r8, [rsp+1B0h+var_150]
0x18000ecfe  lea     rdx, [rsp+1B0h+var_170]
0x18000ed03  call    ??$call@AEAV_lambda_1_@?1??CreateFromIdAsync@DeviceInformation@Enumeration@Devices@Windows@winrt@@SA@AEBUhstring@param@7@AEBU?$async_iterable@Uhstring@winrt@@@97@@Z@@?$factory_cache_entry@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateFromIdAsync@DeviceInformation@Enumeration@Devices@Windows@2@SA@AEBUhstring@param@2@AEBU?$async_iterable@Uhstring@winrt@@@param@2@@Z@@Z
0x18000ed08  mov     rbx, [rsp+1B0h+var_170]
0x18000ed0d  lea     rdx, [rsp+1B0h+var_160]
0x18000ed12  lea     rcx, [rsp+1B0h+var_170]
0x18000ed17  call    ?get@?$consume_Windows_Foundation_IAsyncOperation@U?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@UDeviceInformation@Enumeration@Devices@34@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Devices::Enumeration::DeviceInformation>,winrt::Windows::Devices::Enumeration::DeviceInformation>::get(void)
0x18000ed1c  test    rbx, rbx
0x18000ed1f  jz      short loc_18000ED2B
0x18000ed21  lea     rcx, [rsp+1B0h+var_170]
0x18000ed26  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000ed2b  cmp     byte ptr [rbp+0B0h+var_90], r15b
0x18000ed2f  jnz     short loc_18000ED3A
0x18000ed31  mov     rax, r15
0x18000ed34  mov     [rbp+0B0h+var_98], rax
0x18000ed38  jmp     short loc_18000ED3E
0x18000ed3a  mov     rax, [rbp+0B0h+var_98]
0x18000ed3e  test    rax, rax
0x18000ed41  jz      short loc_18000ED4C
0x18000ed43  lea     rcx, [rbp+0B0h+var_98]
0x18000ed47  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000ed4c  lea     r9, ??1hstring@winrt@@QEAA@XZ; void (*)(void *)
0x18000ed53  mov     edx, 8; unsigned __int64
0x18000ed58  lea     r8d, [rdx-6]; unsigned __int64
0x18000ed5c  lea     rcx, [rbp+0B0h+lpMem]; void *
0x18000ed60  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18000ed65  mov     [rbp+0B0h+lpMem], r15
0x18000ed69  lea     rdx, [rbp+0B0h+lpMem]
0x18000ed6d  lea     rcx, [rsp+1B0h+var_160]
0x18000ed72  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x18000ed77  test    al, al
0x18000ed79  jz      short loc_18000ED9E
0x18000ed7b  mov     rcx, [rbp+0B8h]; this
0x18000ed82  mov     r9d, 80070057h; char *
0x18000ed88  lea     r8, aAvcoreMidi2Tra; "avcore\\midi2\\transform\\umpprotocoldo"...
0x18000ed8f  mov     edx, 38h ; '8'; void *
0x18000ed94  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ed99  jmp     loc_18000EF76
0x18000ed9e  lea     rdx, [rsp+1B0h+var_170]
0x18000eda3  lea     rcx, [rsp+1B0h+var_160]
0x18000eda8  call    ?Properties@?$consume_Windows_Devices_Enumeration_IDeviceInformation@UIDeviceInformation@Enumeration@Devices@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Properties(void)
0x18000edad  mov     dword ptr [rbp+0B0h+var_78+8], esi
0x18000edb0  mov     dword ptr [rbp+0B0h+var_78+0Ch], r13d
0x18000edb4  lea     rcx, a3f114a6a11fa4b_1; "{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} "...
0x18000edbb  mov     [rbp+0B0h+var_60], rcx
0x18000edbf  lea     rcx, [rbp+0B0h+var_78+8]
0x18000edc3  mov     qword ptr [rbp+0B0h+var_78], rcx
0x18000edc7  lea     r8, [rbp+0B0h+var_78]
0x18000edcb  lea     rdx, [rsp+1B0h+var_158]
0x18000edd0  mov     rcx, rax
0x18000edd3  call    ?Lookup@?$consume_Windows_Foundation_Collections_IMapView@U?$IMapView@Uhstring@winrt@@UIInspectable@Foundation@Windows@2@@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMapView<winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Windows::Foundation::IInspectable>,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(winrt::param::hstring const &)
0x18000edd8  cmp     [rsp+1B0h+var_170], r15
0x18000eddd  jz      short loc_18000EDE9
0x18000eddf  lea     rcx, [rsp+1B0h+var_170]
0x18000ede4  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000ede9  mov     [rbp+0B0h+lpMem], r15
0x18000eded  lea     rdx, [rbp+0B0h+lpMem]
0x18000edf1  lea     rcx, [rsp+1B0h+var_158]
0x18000edf6  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x18000edfb  test    al, al
0x18000edfd  jz      short loc_18000EE22
0x18000edff  mov     rcx, [rbp+0B8h]; this
0x18000ee06  mov     r9d, 80070057h; char *
0x18000ee0c  lea     r8, aAvcoreMidi2Tra; "avcore\\midi2\\transform\\umpprotocoldo"...
0x18000ee13  mov     edx, 3Bh ; ';'; void *
0x18000ee18  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ee1d  jmp     loc_18000EF65
0x18000ee22  lea     rcx, [rsp+1B0h+var_158]
0x18000ee27  call    ??$unbox_value@_N@winrt@@YA_NAEBUIInspectable@Foundation@Windows@0@@Z; winrt::unbox_value<bool>(winrt::Windows::Foundation::IInspectable const &)
0x18000ee2c  mov     [r12+62h], al
  ... truncated ...
```
