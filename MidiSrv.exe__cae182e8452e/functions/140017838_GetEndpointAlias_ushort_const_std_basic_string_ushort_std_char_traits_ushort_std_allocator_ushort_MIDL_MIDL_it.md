# GetEndpointAlias(ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0002 &)

- ea: `0x140017838`
- end: `0x140017f8c`
- name: `?GetEndpointAlias@@YAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAW4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0002@@@Z`
- size: `1876`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `28`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400152d0`

## callees

- `0x140001ce8`
- `0x1400054c0`
- `0x1400060d4`
- `0x14000617c`
- `0x1400061e8`
- `0x1400072d4`
- `0x140007c20`
- `0x14000984c`
- `0x14000a6b4`
- `0x14000ca00`
- `0x14000cc2c`
- `0x140012008`
- `0x140012b5c`
- `0x1400133f0`
- `0x1400136c4`
- `0x140013798`
- `0x140013a38`
- `0x1400140c4`
- `0x14001440c`
- `0x1400145bc`
- `0x140014688`
- `0x140014f04`
- `0x140017838`
- `0x14001bd28`
- `0x14001c390`
- `0x14001dccc`
- `0x14001ecb4`
- `0x14005a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1400179c5`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x140017c2c`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x140017c49`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1400179c5`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x140017c2c`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x140017c49`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x140017e93`

## string_xrefs

- `0x140017dc6`: `avcore\midi2\service\exe\midiclientmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=22
__int64 __fastcall GetEndpointAlias(void *a1, char *a2, _DWORD *a3)
{
  _DWORD *v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  unsigned __int64 v9; // r8
  __int64 v10; // rax
  __int64 v11; // rcx
  LPVOID v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  const wchar_t *v15; // rdx
  unsigned __int64 v16; // r8
  __int64 v17; // rax
  void *v18; // rdi
  int v19; // eax
  HANDLE ProcessHeap; // rax
  __int64 v21; // r15
  int v22; // eax
  __int64 v23; // rdx
  char *v24; // rcx
  __int64 v25; // rax
  __int64 v26; // rax
  void (__fastcall ****v27)(_QWORD, __int64 *, __int64 *); // rdi
  void (__fastcall ***v28)(_QWORD, __int64 *, __int64 *); // rcx
  char *v30; // rdi
  char *v31; // rcx
  char *v32; // rsi
  _DWORD *v33; // rcx
  __int64 v34; // r8
  __int64 v35; // r9
  int v36; // [rsp+20h] [rbp-E0h]
  const wchar_t *v37; // [rsp+40h] [rbp-C0h] BYREF
  void (__fastcall ***v38)(_QWORD, __int64 *, __int64 *); // [rsp+48h] [rbp-B8h] BYREF
  __int64 v39; // [rsp+50h] [rbp-B0h] BYREF
  int v40[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 Buf1; // [rsp+60h] [rbp-A0h] BYREF
  int v42; // [rsp+68h] [rbp-98h]
  int v43; // [rsp+6Ch] [rbp-94h]
  LPVOID lpMem; // [rsp+70h] [rbp-90h] BYREF
  __int128 *v45; // [rsp+78h] [rbp-88h]
  int *v46; // [rsp+80h] [rbp-80h]
  __int64 v47; // [rsp+88h] [rbp-78h] BYREF
  __int64 v48; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v49[32]; // [rsp+98h] [rbp-68h] BYREF
  __int128 v50; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v51; // [rsp+C8h] [rbp-38h]
  __int128 v52; // [rsp+D8h] [rbp-28h] BYREF
  int *v53; // [rsp+E8h] [rbp-18h]
  __int128 v54; // [rsp+F8h] [rbp-8h] BYREF
  __int128 v55; // [rsp+108h] [rbp+8h]
  _BYTE Buf2[16]; // [rsp+118h] [rbp+18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  v6 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v6 > 4u )
  {
    lpMem = a1;
    v37 = L"Enter";
    v39 = 0;
    *(_QWORD *)v40 = "GetEndpointAlias";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (__int64)v6,
      (__int64)&byte_140087C2F,
      v7,
      v8,
      v40,
      (__int64)&v39,
      &v37,
      &lpMem);
  }
  v54 = 0;
  v55 = 0;
  v9 = -1;
  do
    ++v9;
  while ( *((_WORD *)a1 + v9) );
  std::wstring::_Construct<1,unsigned short const *>((char **)&v54, a1, v9);
  v10 = std::wstring::wstring((__int64)&v52, (__int64)&v54);
  WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(&v50, v10);
  std::wstring::operator=((char **)a2, (__int64)&v50);
  std::wstring::~wstring((char **)&v50);
  std::wstring::~wstring((char **)&v54);
  v52 = 0;
  v53 = 0;
  winrt::single_threaded_vector<winrt::hstring,std::allocator<winrt::hstring>>(&v39, (__int64 *)&v52);
  std::vector<winrt::hstring>::~vector<winrt::hstring>((__int64)&v52);
  *((_QWORD *)&v50 + 1) = 0x2900000001LL;
  *((_QWORD *)&v51 + 1) = L"{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} 52";
  *(_QWORD *)&v50 = (char *)&v50 + 8;
  winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::Append(
    &v39,
    &v50);
  v40[0] = 1;
  winrt::param::async_iterable<winrt::hstring>::async_iterable<winrt::hstring>(&lpMem, &v39);
  v11 = -1;
  do
    ++v11;
  while ( *((_WORD *)a1 + v11) );
  if ( (_DWORD)v11 )
  {
    if ( *((_WORD *)a1 + (unsigned int)v11) )
      abort();
    DWORD2(v50) = 1;
    HIDWORD(v50) = v11;
    *((_QWORD *)&v51 + 1) = a1;
    *(_QWORD *)&v50 = (char *)&v50 + 8;
  }
  else
  {
    *(_QWORD *)&v50 = 0;
  }
  *(_QWORD *)&v52 = &v50;
  *((_QWORD *)&v52 + 1) = &lpMem;
  v53 = v40;
  Buf1 = (__int64)&qword_1400969F8;
  _InterlockedIncrement64(&qword_1400969F8);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2> )
  {
    `winrt::Windows::Devices::Enumeration::DeviceInformation::CreateFromIdAsync'::`2'::_lambda_1_::operator()(
      (__int64)&v52,
      &v37,
      (__int64 **)&winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>);
    _InterlockedAdd64(&qword_1400969F8, 0xFFFFFFFFFFFFFFFFuLL);
  }
  else
  {
    _InterlockedAdd64(&qword_1400969F8, 0xFFFFFFFFFFFFFFFFuLL);
    ___call_AEAV_lambda_1___1__CreateFromIdAsync_DeviceInformation_Enumeration_Devices_Windows_winrt__SA_AEBUhstring_param_7_AEBU__async_iterable_Uhstring_winrt___97_AEBW4DeviceInformationKind_4567__Z____factory_cache_entry_UDeviceInformation_Enumeration_Devices_Windows_winrt__UIDeviceInformationStatics2_2345__impl_winrt__QEAA_A_PAEAV_lambda_1___1__CreateFromIdAsync_DeviceInformation_Enumeration_Devices_Windows_2_SA_AEBUhstring_param_2_AEBU__async_iterable_Uhstring_winrt___param_2_AEBW4DeviceInformationKind_6782__Z__Z(
      (__int64 *)v11,
      (__int64)&v37,
      (__int64)&v52);
  }
  winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Devices::Enumeration::DeviceInformation>,winrt::Windows::Devices::Enumeration::DeviceInformation>::get(
    &v37,
    &v48);
  if ( v37 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v37);
  if ( (_BYTE)v45 )
  {
    v12 = lpMem;
  }
  else
  {
    v12 = 0;
    lpMem = 0;
  }
  if ( v12 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&lpMem);
  v13 = winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Properties(
          &v48,
          &v37);
  *((_QWORD *)&v54 + 1) = 0x2900000001LL;
  *((_QWORD *)&v55 + 1) = L"{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} 52";
  *(_QWORD *)&v54 = (char *)&v54 + 8;
  winrt::impl::consume_Windows_Foundation_Collections_IMapView<winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Windows::Foundation::IInspectable>,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(
    v13,
    &v38,
    &v54);
  if ( v37 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v37);
  if ( v38 )
  {
    v14 = winrt::unbox_value<winrt::hstring>(&lpMem, &v38);
    v15 = *(_QWORD *)v14 ? *(const wchar_t **)(*(_QWORD *)v14 + 16LL) : &S2;
    v50 = 0;
    v51 = 0;
    v16 = -1;
    do
      ++v16;
    while ( v15[v16] );
    std::wstring::_Construct<1,unsigned short const *>((char **)&v50, v15, v16);
    v17 = std::wstring::wstring((__int64)v49, (__int64)&v50);
    WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(&v52, v17);
    std::wstring::operator=((char **)a2, (__int64)&v52);
    std::wstring::~wstring((char **)&v52);
    std::wstring::~wstring((char **)&v50);
    v18 = lpMem;
    if ( lpMem )
    {
      v19 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
      if ( v19 )
      {
        if ( v19 < 0 )
          abort();
      }
      else
      {
        ProcessHeap = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(ProcessHeap, 0, v18);
      }
    }
  }
  v21 = v39;
  LODWORD(v52) = 717;
  *((_QWORD *)&v52 + 1) = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Foundation.Collections.h";
  v53 = 0;
  v22 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v39 + 120LL))(v39);
  if ( v22 < 0 )
    winrt::throw_hresult((unsigned int)v22, &v52);
  *((_QWORD *)&v50 + 1) = 0x2100000001LL;
  *((_QWORD *)&v51 + 1) = L"System.Devices.InterfaceClassGuid";
  *(_QWORD *)&v50 = (char *)&v50 + 8;
  winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::Append(
    &v39,
    &v50);
  v40[0] = 1;
  winrt::param::async_iterable<winrt::hstring>::async_iterable<winrt::hstring>(&v52, &v39);
  v23 = *((_QWORD *)a2 + 2);
  if ( *((_QWORD *)a2 + 3) <= 7u )
    v24 = a2;
  else
    v24 = *(char **)a2;
  if ( (_DWORD)v23 )
  {
    if ( *(_WORD *)&v24[2 * (unsigned int)v23] )
      abort();
    DWORD2(v50) = 1;
    HIDWORD(v50) = v23;
    *((_QWORD *)&v51 + 1) = v24;
    *(_QWORD *)&v50 = (char *)&v50 + 8;
  }
  else
  {
    *(_QWORD *)&v50 = 0;
  }
  lpMem = &v50;
  v45 = &v52;
  v46 = v40;
  Buf1 = (__int64)&qword_1400969F8;
  _InterlockedIncrement64(&qword_1400969F8);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2> )
  {
    `winrt::Windows::Devices::Enumeration::DeviceInformation::CreateFromIdAsync'::`2'::_lambda_1_::operator()(
      (__int64)&lpMem,
      &v37,
      (__int64 **)&winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>);
    _InterlockedAdd64(&qword_1400969F8, 0xFFFFFFFFFFFFFFFFuLL);
  }
  else
  {
    _InterlockedAdd64(&qword_1400969F8, 0xFFFFFFFFFFFFFFFFuLL);
    ___call_AEAV_lambda_1___1__CreateFromIdAsync_DeviceInformation_Enumeration_Devices_Windows_winrt__SA_AEBUhstring_param_7_AEBU__async_iterable_Uhstring_winrt___97_AEBW4DeviceInformationKind_4567__Z____factory_cache_entry_UDeviceInformation_Enumeration_Devices_Windows_winrt__UIDeviceInformationStatics2_2345__impl_winrt__QEAA_A_PAEAV_lambda_1___1__CreateFromIdAsync_DeviceInformation_Enumeration_Devices_Windows_2_SA_AEBUhstring_param_2_AEBU__async_iterable_Uhstring_winrt___param_2_AEBW4DeviceInformationKind_6782__Z__Z(
      (__int64 *)v24,
      (__int64)&v37,
      (__int64)&lpMem);
  }
  winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Devices::Enumeration::DeviceInformation>,winrt::Windows::Devices::Enumeration::DeviceInformation>::get(
    &v37,
    &v47);
  if ( v37 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v37);
  if ( BYTE8(v52) )
  {
    v25 = v52;
  }
  else
  {
    v25 = 0;
    *(_QWORD *)&v52 = 0;
  }
  if ( v25 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v52);
  v26 = winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Properties(
          &v47,
          &lpMem);
  *((_QWORD *)&v54 + 1) = 0x2100000001LL;
  *((_QWORD *)&v55 + 1) = L"System.Devices.InterfaceClassGuid";
  *(_QWORD *)&v54 = (char *)&v54 + 8;
  v27 = (void (__fastcall ****)(_QWORD, __int64 *, __int64 *))winrt::impl::consume_Windows_Foundation_Collections_IMapView<winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Windows::Foundation::IInspectable>,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(
                                                                v26,
                                                                &v37,
                                                                &v54);
  if ( &v38 != v27 )
  {
    if ( v38 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v38);
    v28 = *v27;
    *v27 = 0;
    v38 = v28;
  }
  if ( v37 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v37);
  if ( lpMem )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&lpMem);
  lpMem = 0;
  if ( winrt::Windows::Foundation::operator==(&v38, &lpMem) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x129,
      (unsigned int)"avcore\\midi2\\service\\exe\\midiclientmanager.cpp",
      (const char *)0x80070057LL,
      v36);
    if ( v47 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v47);
    if ( v38 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v38);
    if ( v48 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v48);
    if ( v21 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v39);
    return 2147942487LL;
  }
  else
  {
    winrt::unbox_value<winrt::guid>(Buf2, &v38);
    Buf1 = 0x423F3C03E7CCE071LL;
    v42 = 82957192;
    v43 = 726991453;
    if ( !memcmp_0(&Buf1, Buf2, 0x10u) )
      *a3 = 2;
    if ( *((_QWORD *)a2 + 3) <= 7u )
    {
      v30 = a2;
      v31 = a2;
    }
    else
    {
      v30 = *(char **)a2;
      v31 = *(char **)a2;
    }
    v32 = &v31[2 * *((_QWORD *)a2 + 2)];
    if ( *((_QWORD *)a2 + 3) > 7u )
      a2 = *(char **)a2;
    while ( a2 != v32 )
    {
      *(_WORD *)v30 = ((__int64 (__fastcall *)(_QWORD))_o_towlower)(*(unsigned __int16 *)a2);
      v30 += 2;
      a2 += 2;
    }
    v33 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
    if ( *v33 > 4u )
    {
      lpMem = a1;
      v37 = L"Exit";
      *(_QWORD *)v40 = 0;
      Buf1 = (__int64)"GetEndpointAlias";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        (__int64)v33,
        (__int64)byte_140087443,
        v34,
        v35,
        &Buf1,
        (__int64)v40,
        &v37,
        &lpMem);
    }
    if ( v47 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v47);
    if ( v38 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v38);
    if ( v48 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v48);
    if ( v21 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v39);
    return 0;
  }
}

```

## disassembly

```asm
0x140017838  mov     [rsp-8+arg_18], rbx
0x14001783d  push    rbp
0x14001783e  push    rsi
0x14001783f  push    rdi
0x140017840  push    r12
0x140017842  push    r13
0x140017844  push    r14
0x140017846  push    r15
0x140017848  lea     rbp, [rsp-30h]
0x14001784d  sub     rsp, 130h
0x140017854  mov     rax, cs:__security_cookie
0x14001785b  xor     rax, rsp
0x14001785e  mov     [rbp+60h+var_38], rax
0x140017862  mov     rsi, r8
0x140017865  mov     rbx, rdx
0x140017868  mov     r14, rcx
0x14001786b  xor     r12d, r12d
0x14001786e  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x140017873  mov     rcx, [rax+8]
0x140017877  mov     eax, [rcx]
0x140017879  lea     rdx, aGetendpointali; "GetEndpointAlias"
0x140017880  cmp     eax, 4
0x140017883  jbe     short loc_1400178D4
0x140017885  mov     [rsp+160h+lpMem], r14
0x14001788a  lea     rax, aEnter; "Enter"
0x140017891  mov     [rsp+160h+var_120], rax
0x140017896  mov     [rsp+160h+var_110], r12
0x14001789b  mov     qword ptr [rsp+160h+var_108], rdx
0x1400178a0  lea     rax, [rsp+160h+lpMem]
0x1400178a5  mov     [rsp+160h+var_128], rax
0x1400178aa  lea     rax, [rsp+160h+var_120]
0x1400178af  mov     [rsp+160h+var_130], rax
0x1400178b4  lea     rax, [rsp+160h+var_110]
0x1400178b9  mov     [rsp+160h+var_138], rax
0x1400178be  lea     rax, [rsp+160h+var_108]
0x1400178c3  mov     qword ptr [rsp+160h+var_140], rax; int
0x1400178c8  lea     rdx, byte_140087C2F
0x1400178cf  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x1400178d4  xorps   xmm0, xmm0
0x1400178d7  movups  [rbp+60h+var_68], xmm0
0x1400178db  xorps   xmm1, xmm1
0x1400178de  movdqu  [rbp+60h+var_58], xmm1
0x1400178e3  or      r13, 0FFFFFFFFFFFFFFFFh
0x1400178e7  mov     r8, r13
0x1400178ea  inc     r8
0x1400178ed  cmp     [r14+r8*2], r12w
0x1400178f2  jnz     short loc_1400178EA
0x1400178f4  mov     rdx, r14
0x1400178f7  lea     rcx, [rbp+60h+var_68]
0x1400178fb  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140017900  nop
0x140017901  lea     rdx, [rbp+60h+var_68]
0x140017905  lea     rcx, [rbp+60h+var_88]
0x140017909  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14001790e  mov     rdx, rax
0x140017911  lea     rcx, [rbp+60h+var_A8]
0x140017915  call    ?ToLowerTrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(std::wstring)
0x14001791a  lea     rdx, [rbp+60h+var_A8]
0x14001791e  mov     rcx, rbx
0x140017921  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x140017926  lea     rcx, [rbp+60h+var_A8]; void *
0x14001792a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001792f  nop
0x140017930  lea     rcx, [rbp+60h+var_68]; void *
0x140017934  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140017939  xorps   xmm0, xmm0
0x14001793c  movdqu  [rbp+60h+var_88], xmm0
0x140017941  mov     [rbp+60h+var_78], r12
0x140017945  lea     rdx, [rbp+60h+var_88]
0x140017949  lea     rcx, [rsp+160h+var_110]
0x14001794e  call    ??$single_threaded_vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@winrt@@YA?AU?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@0@$$QEAV?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@@Z; winrt::single_threaded_vector<winrt::hstring,std::allocator<winrt::hstring>>(std::vector<winrt::hstring> &&)
0x140017953  nop
0x140017954  lea     rcx, [rbp+60h+var_88]
0x140017958  call    ??1?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@QEAA@XZ; std::vector<winrt::hstring>::~vector<winrt::hstring>(void)
0x14001795d  mov     dword ptr [rbp+60h+var_A8+8], 1
0x140017964  mov     edi, 29h ; ')'
0x140017969  mov     dword ptr [rbp+60h+var_A8+0Ch], edi
0x14001796c  lea     r15, a3f114a6a11fa4b; "{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} "...
0x140017973  mov     [rbp+60h+var_90], r15
0x140017977  lea     rax, [rbp+60h+var_A8+8]
0x14001797b  mov     qword ptr [rbp+60h+var_A8], rax
0x14001797f  lea     rdx, [rbp+60h+var_A8]
0x140017983  lea     rcx, [rsp+160h+var_110]
0x140017988  call    ?Append@?$consume_Windows_Foundation_Collections_IVector@U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@winrt@@Uhstring@5@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::Append(winrt::param::hstring const &)
0x14001798d  mov     [rsp+160h+var_108], 1
0x140017995  lea     rdx, [rsp+160h+var_110]
0x14001799a  lea     rcx, [rsp+160h+lpMem]
0x14001799f  call    ??$?0U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@winrt@@$0A@@?$async_iterable@Uhstring@winrt@@@param@winrt@@QEAA@AEBU?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@2@@Z; winrt::param::async_iterable<winrt::hstring>::async_iterable<winrt::hstring>(winrt::Windows::Foundation::Collections::IVector<winrt::hstring> const &)
0x1400179a4  nop
0x1400179a5  mov     rcx, r13
0x1400179a8  inc     rcx
0x1400179ab  cmp     [r14+rcx*2], r12w
0x1400179b0  jnz     short loc_1400179A8
0x1400179b2  test    ecx, ecx
0x1400179b4  jnz     short loc_1400179BC
0x1400179b6  mov     qword ptr [rbp+60h+var_A8], r12
0x1400179ba  jmp     short loc_1400179E2
0x1400179bc  mov     eax, ecx
0x1400179be  cmp     [r14+rax*2], r12w
0x1400179c3  jz      short loc_1400179CC
0x1400179c5  call    cs:__imp_abort
0x1400179cc  mov     dword ptr [rbp+60h+var_A8+8], 1
0x1400179d3  mov     dword ptr [rbp+60h+var_A8+0Ch], ecx
0x1400179d6  mov     [rbp+60h+var_90], r14
0x1400179da  lea     rax, [rbp+60h+var_A8+8]
0x1400179de  mov     qword ptr [rbp+60h+var_A8], rax
0x1400179e2  lea     rax, [rbp+60h+var_A8]
0x1400179e6  mov     qword ptr [rbp+60h+var_88], rax
0x1400179ea  lea     rax, [rsp+160h+lpMem]
0x1400179ef  mov     qword ptr [rbp+60h+var_88+8], rax
0x1400179f3  lea     rax, [rsp+160h+var_108]
0x1400179f8  mov     [rbp+60h+var_78], rax
0x1400179fc  lea     rax, qword_1400969F8
0x140017a03  mov     [rsp+160h+Buf1], rax
0x140017a08  lock inc cs:qword_1400969F8
0x140017a10  cmp     cs:??$factory_cache_entry_v@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@impl@winrt@@3U?$factory_cache_entry@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@12@A, r12; factory_cache_entry<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>::winrt::factory_cache_entry<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2> winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>
0x140017a17  jz      short loc_140017A39
0x140017a19  lea     r8, ??$factory_cache_entry_v@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@impl@winrt@@3U?$factory_cache_entry@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@12@A; factory_cache_entry<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>::winrt::factory_cache_entry<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2> winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>
0x140017a20  lea     rdx, [rsp+160h+var_120]
0x140017a25  lea     rcx, [rbp+60h+var_88]
0x140017a29  call    ??R_lambda_1_@?1??CreateFromIdAsync@DeviceInformation@Enumeration@Devices@Windows@winrt@@SA@AEBUhstring@param@6@AEBU?$async_iterable@Uhstring@winrt@@@86@AEBW4DeviceInformationKind@3456@@Z@QEBA@AEBUIDeviceInformationStatics2@3456@@Z; `winrt::Windows::Devices::Enumeration::DeviceInformation::CreateFromIdAsync(winrt::param::hstring const &,winrt::param::async_iterable<winrt::hstring> const &,winrt::Windows::Devices::Enumeration::DeviceInformationKind const &)'::`2'::_lambda_1_::operator()(winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2 const &)
0x140017a2e  nop
0x140017a2f  lock add cs:qword_1400969F8, r13
0x140017a37  jmp     short loc_140017A50
0x140017a39  lock add cs:qword_1400969F8, r13
0x140017a41  lea     r8, [rbp+60h+var_88]
0x140017a45  lea     rdx, [rsp+160h+var_120]
0x140017a4a  call    ??$call@AEAV_lambda_1_@?1??CreateFromIdAsync@DeviceInformation@Enumeration@Devices@Windows@winrt@@SA@AEBUhstring@param@7@AEBU?$async_iterable@Uhstring@winrt@@@97@AEBW4DeviceInformationKind@4567@@Z@@?$factory_cache_entry@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateFromIdAsync@DeviceInformation@Enumeration@Devices@Windows@2@SA@AEBUhstring@param@2@AEBU?$async_iterable@Uhstring@winrt@@@param@2@AEBW4DeviceInformationKind@6782@@Z@@Z
0x140017a4f  nop
0x140017a50  lea     rdx, [rbp+60h+var_D0]
0x140017a54  lea     rcx, [rsp+160h+var_120]
0x140017a59  call    ?get@?$consume_Windows_Foundation_IAsyncOperation@U?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@UDeviceInformation@Enumeration@Devices@34@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Devices::Enumeration::DeviceInformation>,winrt::Windows::Devices::Enumeration::DeviceInformation>::get(void)
0x140017a5e  nop
0x140017a5f  cmp     [rsp+160h+var_120], r12
0x140017a64  jz      short loc_140017A71
0x140017a66  lea     rcx, [rsp+160h+var_120]
0x140017a6b  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x140017a70  nop
0x140017a71  cmp     byte ptr [rsp+160h+var_E8], r12b
0x140017a76  jnz     short loc_140017A82
0x140017a78  mov     rax, r12
0x140017a7b  mov     [rsp+160h+lpMem], rax
0x140017a80  jmp     short loc_140017A87
0x140017a82  mov     rax, [rsp+160h+lpMem]
0x140017a87  test    rax, rax
0x140017a8a  jz      short loc_140017A96
0x140017a8c  lea     rcx, [rsp+160h+lpMem]
0x140017a91  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x140017a96  lea     rdx, [rsp+160h+var_120]
0x140017a9b  lea     rcx, [rbp+60h+var_D0]
0x140017a9f  call    ?Properties@?$consume_Windows_Devices_Enumeration_IDeviceInformation@UIDeviceInformation@Enumeration@Devices@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Properties(void)
0x140017aa4  nop
0x140017aa5  mov     dword ptr [rbp+60h+var_68+8], 1
0x140017aac  mov     dword ptr [rbp+60h+var_68+0Ch], edi
0x140017aaf  mov     qword ptr [rbp+60h+var_58+8], r15
0x140017ab3  lea     rcx, [rbp+60h+var_68+8]
0x140017ab7  mov     qword ptr [rbp+60h+var_68], rcx
0x140017abb  lea     r8, [rbp+60h+var_68]
0x140017abf  lea     rdx, [rsp+160h+var_118]
0x140017ac4  mov     rcx, rax
0x140017ac7  call    ?Lookup@?$consume_Windows_Foundation_Collections_IMapView@U?$IMapView@Uhstring@winrt@@UIInspectable@Foundation@Windows@2@@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMapView<winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Windows::Foundation::IInspectable>,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(winrt::param::hstring const &)
0x140017acc  nop
0x140017acd  cmp     [rsp+160h+var_120], r12
0x140017ad2  jz      short loc_140017ADE
0x140017ad4  lea     rcx, [rsp+160h+var_120]
0x140017ad9  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x140017ade  cmp     [rsp+160h+var_118], r12
0x140017ae3  jz      loc_140017B9B
0x140017ae9  lea     rdx, [rsp+160h+var_118]
0x140017aee  lea     rcx, [rsp+160h+lpMem]
0x140017af3  call    ??$unbox_value@Uhstring@winrt@@@winrt@@YA?AUhstring@0@AEBUIInspectable@Foundation@Windows@0@@Z; winrt::unbox_value<winrt::hstring>(winrt::Windows::Foundation::IInspectable const &)
0x140017af8  nop
0x140017af9  mov     rdx, [rax]
0x140017afc  test    rdx, rdx
0x140017aff  jz      short loc_140017B07
0x140017b01  mov     rdx, [rdx+10h]
0x140017b05  jmp     short loc_140017B0E
0x140017b07  lea     rdx, S2
0x140017b0e  xorps   xmm0, xmm0
0x140017b11  movups  [rbp+60h+var_A8], xmm0
0x140017b15  xorps   xmm1, xmm1
0x140017b18  movdqu  xmmword ptr [rbp-38h], xmm1
0x140017b1d  mov     r8, r13
0x140017b20  inc     r8
0x140017b23  cmp     [rdx+r8*2], r12w
0x140017b28  jnz     short loc_140017B20
0x140017b2a  lea     rcx, [rbp+60h+var_A8]
0x140017b2e  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140017b33  nop
0x140017b34  lea     rdx, [rbp+60h+var_A8]
0x140017b38  lea     rcx, [rbp+60h+var_C8]
0x140017b3c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140017b41  mov     rdx, rax
0x140017b44  lea     rcx, [rbp+60h+var_88]
0x140017b48  call    ?ToLowerTrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(std::wstring)
0x140017b4d  lea     rdx, [rbp+60h+var_88]
0x140017b51  mov     rcx, rbx
0x140017b54  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x140017b59  lea     rcx, [rbp+60h+var_88]; void *
0x140017b5d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140017b62  nop
0x140017b63  lea     rcx, [rbp+60h+var_A8]; void *
0x140017b67  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140017b6c  nop
0x140017b6d  mov     rdi, [rsp+160h+lpMem]
0x140017b72  test    rdi, rdi
0x140017b75  jz      short loc_140017B9B
0x140017b77  mov     eax, r13d
0x140017b7a  lock xadd [rdi+18h], eax
0x140017b7f  sub     eax, 1
0x140017b82  jnz     loc_140017C24
0x140017b88  nop
0x140017b89  call    WINRT_IMPL_GetProcessHeap
0x140017b8e  mov     rcx, rax; hHeap
0x140017b91  mov     r8, rdi; lpMem
0x140017b94  xor     edx, edx; dwFlags
0x140017b96  call    WINRT_IMPL_HeapFree
0x140017b9b  mov     r15, [rsp+160h+var_110]
0x140017ba0  mov     dword ptr [rbp+60h+var_88], 2CDh
0x140017ba7  lea     rax, aOnecoreuapInte_1; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x140017bae  mov     qword ptr [rbp+60h+var_88+8], rax
0x140017bb2  mov     [rbp+60h+var_78], r12
0x140017bb6  mov     rax, [r15]
0x140017bb9  mov     rcx, r15
0x140017bbc  mov     rax, [rax+78h]
0x140017bc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017bc5  test    eax, eax
0x140017bc7  js      loc_140017F80
0x140017bcd  mov     dword ptr [rbp+60h+var_A8+8], 1
0x140017bd4  mov     edi, 21h ; '!'
0x140017bd9  mov     dword ptr [rbp+60h+var_A8+0Ch], edi
0x140017bdc  lea     rax, aSystemDevicesI; "System.Devices.InterfaceClassGuid"
0x140017be3  mov     [rbp+60h+var_90], rax
0x140017be7  lea     rax, [rbp+60h+var_A8+8]
0x140017beb  mov     qword ptr [rbp+60h+var_A8], rax
0x140017bef  lea     rdx, [rbp+60h+var_A8]
0x140017bf3  lea     rcx, [rsp+160h+var_110]
0x140017bf8  call    ?Append@?$consume_Windows_Foundation_Collections_IVector@U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@winrt@@Uhstring@5@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::Append(winrt::param::hstring const &)
0x140017bfd  mov     [rsp+160h+var_108], 1
0x140017c05  lea     rdx, [rsp+160h+var_110]
0x140017c0a  lea     rcx, [rbp+60h+var_88]
0x140017c0e  call    ??$?0U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@winrt@@$0A@@?$async_iterable@Uhstring@winrt@@@param@winrt@@QEAA@AEBU?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@2@@Z; winrt::param::async_iterable<winrt::hstring>::async_iterable<winrt::hstring>(winrt::Windows::Foundation::Collections::IVector<winrt::hstring> const &)
0x140017c13  nop
0x140017c14  mov     rdx, [rbx+10h]
0x140017c18  cmp     qword ptr [rbx+18h], 7
0x140017c1d  jbe     short loc_140017C33
0x140017c1f  mov     rcx, [rbx]
0x140017c22  jmp     short loc_140017C36
0x140017c24  test    eax, eax
0x140017c26  jns     loc_140017B9B
0x140017c2c  call    cs:__imp_abort
0x140017c33  mov     rcx, rbx
0x140017c36  test    edx, edx
0x140017c38  jnz     short loc_140017C40
0x140017c3a  mov     qword ptr [rbp+60h+var_A8], r12
0x140017c3e  jmp     short loc_140017C66
0x140017c40  mov     eax, edx
0x140017c42  cmp     [rcx+rax*2], r12w
0x140017c47  jz      short loc_140017C50
0x140017c49  call    cs:__imp_abort
0x140017c50  mov     dword ptr [rbp+60h+var_A8+8], 1
0x140017c57  mov     dword ptr [rbp+60h+var_A8+0Ch], edx
0x140017c5a  mov     [rbp+60h+var_90], rcx
0x140017c5e  lea     rax, [rbp+60h+var_A8+8]
0x140017c62  mov     qword ptr [rbp+60h+var_A8], rax
0x140017c66  lea     rax, [rbp+60h+var_A8]
0x140017c6a  mov     [rsp+160h+lpMem], rax
0x140017c6f  lea     rax, [rbp+60h+var_88]
0x140017c73  mov     [rsp+160h+var_E8], rax
0x140017c78  lea     rax, [rsp+160h+var_108]
0x140017c7d  mov     [rbp+60h+var_E0], rax
0x140017c81  lea     rax, qword_1400969F8
0x140017c88  mov     [rsp+160h+Buf1], rax
0x140017c8d  lock inc cs:qword_1400969F8
0x140017c95  cmp     cs:??$factory_cache_entry_v@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@impl@winrt@@3U?$factory_cache_entry@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@12@A, r12; factory_cache_entry<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>::winrt::factory_cache_entry<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2> winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>
0x140017c9c  jz      short loc_140017CBF
0x140017c9e  lea     r8, ??$factory_cache_entry_v@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@impl@winrt@@3U?$factory_cache_entry@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@12@A; factory_cache_entry<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>::winrt::factory_cache_entry<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2> winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>
0x140017ca5  lea     rdx, [rsp+160h+var_120]
0x140017caa  lea     rcx, [rsp+160h+lpMem]
0x140017caf  call    ??R_lambda_1_@?1??CreateFromIdAsync@DeviceInformation@Enumeration@Devices@Windows@winrt@@SA@AEBUhstring@param@6@AEBU?$async_iterable@Uhstring@winrt@@@86@AEBW4DeviceInformationKind@3456@@Z@QEBA@AEBUIDeviceInformationStatics2@3456@@Z; `winrt::Windows::Devices::Enumeration::DeviceInformation::CreateFromIdAsync(winrt::param::hstring const &,winrt::param::async_iterable<winrt::hstring> const &,winrt::Windows::Devices::Enumeration::DeviceInformationKind const &)'::`2'::_lambda_1_::operator()(winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2 const &)
0x140017cb4  nop
0x140017cb5  lock add cs:qword_1400969F8, r13
0x140017cbd  jmp     short loc_140017CD7
0x140017cbf  lock add cs:qword_1400969F8, r13
0x140017cc7  lea     r8, [rsp+160h+lpMem]
0x140017ccc  lea     rdx, [rsp+160h+var_120]
0x140017cd1  call    ??$call@AEAV_lambda_1_@?1??CreateFromIdAsync@DeviceInformation@Enumeration@Devices@Windows@winrt@@SA@AEBUhstring@param@7@AEBU?$async_iterable@Uhstring@winrt@@@97@AEBW4DeviceInformationKind@4567@@Z@@?$factory_cache_entry@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateFromIdAsync@DeviceInformation@Enumeration@Devices@Windows@2@SA@AEBUhstring@param@2@AEBU?$async_iterable@Uhstring@winrt@@@param@2@AEBW4DeviceInformationKind@6782@@Z@@Z
0x140017cd6  nop
0x140017cd7  lea     rdx, [rbp+60h+var_D8]
0x140017cdb  lea     rcx, [rsp+160h+var_120]
0x140017ce0  call    ?get@?$consume_Windows_Foundation_IAsyncOperation@U?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@UDeviceInformation@Enumeration@Devices@34@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Devices::Enumeration::DeviceInformation>,winrt::Windows::Devices::Enumeration::DeviceInformation>::get(void)
0x140017ce5  nop
0x140017ce6  cmp     [rsp+160h+var_120], r12
0x140017ceb  jz      short loc_140017CF8
0x140017ced  lea     rcx, [rsp+160h+var_120]
0x140017cf2  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x140017cf7  nop
0x140017cf8  cmp     byte ptr [rbp+60h+var_88+8], r12b
0x140017cfc  jnz     short loc_140017D07
0x140017cfe  mov     rax, r12
  ... truncated ...
```
