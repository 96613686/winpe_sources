# GetDeviceSupportedDataFormat(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0001 &)

- ea: `0x140017404`
- end: `0x140017830`
- name: `?GetDeviceSupportedDataFormat@@YAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAW4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0001@@@Z`
- size: `1068`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `17`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400193c4`

## callees

- `0x140001ce8`
- `0x140001f28`
- `0x1400054c0`
- `0x140007c20`
- `0x14000984c`
- `0x14000cc2c`
- `0x140012008`
- `0x140012b5c`
- `0x1400133f0`
- `0x140013528`
- `0x1400140c4`
- `0x140014688`
- `0x140014f04`
- `0x140017404`
- `0x14001bd28`
- `0x14001c390`
- `0x14001ecb4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x140017586`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x140017586`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall GetDeviceSupportedDataFormat(char *a1, wchar_t *a2)
{
  wchar_t *v2; // rsi
  char *v3; // rdi
  _DWORD *v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9
  char *v7; // rax
  __int64 v8; // rdx
  const char *v9; // r15
  __int64 *v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rax
  bool v13; // zf
  const char *v14; // r9
  _DWORD *v15; // rcx
  __int64 v16; // r8
  __int64 v17; // r9
  char *v18; // rax
  const char *v20; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v21; // [rsp+58h] [rbp-B0h] BYREF
  char *v22; // [rsp+60h] [rbp-A8h] BYREF
  const char *v23; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v24; // [rsp+70h] [rbp-98h] BYREF
  __int64 v25; // [rsp+78h] [rbp-90h] BYREF
  const wchar_t *v26; // [rsp+80h] [rbp-88h] BYREF
  __int128 v27; // [rsp+88h] [rbp-80h] BYREF
  __int64 *v28; // [rsp+98h] [rbp-70h]
  const wchar_t *v29; // [rsp+A0h] [rbp-68h]
  int *v30; // [rsp+A8h] [rbp-60h] BYREF
  int v31; // [rsp+B0h] [rbp-58h] BYREF
  int v32; // [rsp+B4h] [rbp-54h]
  const wchar_t *v33; // [rsp+C0h] [rbp-48h]
  __int64 v34; // [rsp+C8h] [rbp-40h] BYREF
  char v35; // [rsp+D0h] [rbp-38h]
  __int64 *v36; // [rsp+D8h] [rbp-30h]
  char *v37; // [rsp+E0h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  v2 = a2;
  v3 = a1;
  v37 = a1;
  v26 = a2;
  v4 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v4 > 4u )
  {
    if ( *((_QWORD *)v3 + 3) <= 7u )
      v7 = v3;
    else
      v7 = *(char **)v3;
    v22 = v7;
    v20 = (const char *)L"Enter";
    v21 = 0;
    v23 = "GetDeviceSupportedDataFormat";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (__int64)v4,
      (__int64)&dword_140087954,
      v5,
      v6,
      &v23,
      (__int64)&v21,
      &v20,
      &v22);
  }
  v27 = 0;
  v28 = 0;
  winrt::single_threaded_vector<winrt::hstring,std::allocator<winrt::hstring>>(&v22, (__int64 *)&v27);
  std::vector<winrt::hstring>::~vector<winrt::hstring>((__int64)&v27);
  v31 = 1;
  v32 = 40;
  v33 = L"{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} 6";
  v30 = &v31;
  winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::Append(
    &v22,
    &v30);
  LODWORD(v21) = 1;
  winrt::param::async_iterable<winrt::hstring>::async_iterable<winrt::hstring>(&v34, &v22);
  v8 = *((_QWORD *)v3 + 2);
  v9 = v3 + 24;
  v23 = v3 + 24;
  if ( *((_QWORD *)v3 + 3) <= 7u )
    v10 = (__int64 *)v3;
  else
    v10 = *(__int64 **)v3;
  if ( (_DWORD)v8 )
  {
    if ( *((_WORD *)v10 + (unsigned int)v8) )
      abort();
    v31 = 1;
    v32 = v8;
    v33 = (const wchar_t *)v10;
    v30 = &v31;
  }
  else
  {
    v30 = 0;
  }
  *(_QWORD *)&v27 = &v30;
  *((_QWORD *)&v27 + 1) = &v34;
  v28 = &v21;
  v36 = &qword_1400969F8;
  _InterlockedIncrement64(&qword_1400969F8);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2> )
  {
    `winrt::Windows::Devices::Enumeration::DeviceInformation::CreateFromIdAsync'::`2'::_lambda_1_::operator()(
      (__int64)&v27,
      &v20,
      (__int64 **)&winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>);
    _InterlockedDecrement64(&qword_1400969F8);
  }
  else
  {
    _InterlockedDecrement64(&qword_1400969F8);
    ___call_AEAV_lambda_1___1__CreateFromIdAsync_DeviceInformation_Enumeration_Devices_Windows_winrt__SA_AEBUhstring_param_7_AEBU__async_iterable_Uhstring_winrt___97_AEBW4DeviceInformationKind_4567__Z____factory_cache_entry_UDeviceInformation_Enumeration_Devices_Windows_winrt__UIDeviceInformationStatics2_2345__impl_winrt__QEAA_A_PAEAV_lambda_1___1__CreateFromIdAsync_DeviceInformation_Enumeration_Devices_Windows_2_SA_AEBUhstring_param_2_AEBU__async_iterable_Uhstring_winrt___param_2_AEBW4DeviceInformationKind_6782__Z__Z(
      v10,
      (__int64)&v20,
      (__int64)&v27);
  }
  winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Devices::Enumeration::DeviceInformation>,winrt::Windows::Devices::Enumeration::DeviceInformation>::get(
    &v20,
    &v25);
  if ( v20 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v20);
  if ( v35 )
  {
    v11 = v34;
  }
  else
  {
    v11 = 0;
    v34 = 0;
  }
  if ( v11 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v34);
  v12 = winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Properties(
          &v25,
          &v20);
  *((_QWORD *)&v27 + 1) = 0x2800000001LL;
  v29 = L"{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} 6";
  *(_QWORD *)&v27 = (char *)&v27 + 8;
  winrt::impl::consume_Windows_Foundation_Collections_IMapView<winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Windows::Foundation::IInspectable>,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(
    v12,
    &v24,
    &v27);
  if ( v20 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v20);
  v13 = v24 == 0;
  *(_DWORD *)v2 = -1;
  if ( !v13 )
  {
    try
    {
      *(_DWORD *)v2 = (unsigned __int8)winrt::unbox_value<unsigned char>(&v24);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0xBA,
        (unsigned int)"avcore\\midi2\\service\\exe\\midiclientmanager.cpp",
        v14);
      v2 = (wchar_t *)v26;
      v3 = v37;
      v9 = v23;
    }
  }
  v15 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v15 > 4u )
  {
    LODWORD(v21) = *(_DWORD *)v2;
    if ( *(_QWORD *)v9 <= 7u )
      v18 = v3;
    else
      v18 = *(char **)v3;
    v37 = v18;
    v26 = L"Exit";
    v23 = 0;
    v20 = "GetDeviceSupportedDataFormat";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      (__int64)v15,
      (__int64)byte_140087F81,
      v16,
      v17,
      &v20,
      (__int64)&v23,
      &v26,
      &v37);
  }
  if ( v24 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v24);
  if ( v25 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v25);
  if ( v22 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v22);
  std::wstring::~wstring((char **)v3);
  return 0;
}

```

## disassembly

```asm
0x140017404  mov     r11, rsp
0x140017407  mov     [r11+18h], rbx
0x14001740b  mov     [r11+20h], rsi
0x14001740f  push    rdi
0x140017410  push    r14
0x140017412  push    r15
0x140017414  sub     rsp, 0F0h
0x14001741b  mov     rax, cs:__security_cookie
0x140017422  xor     rax, rsp
0x140017425  mov     [rsp+108h+var_20], rax
0x14001742d  mov     rsi, rdx
0x140017430  mov     rdi, rcx
0x140017433  mov     [r11-28h], rcx
0x140017437  mov     [rsp+108h+var_88], rdx
0x14001743f  xor     ebx, ebx
0x140017441  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x140017446  mov     rcx, [rax+8]
0x14001744a  mov     eax, [rcx]
0x14001744c  cmp     eax, 4
0x14001744f  jbe     short loc_1400174B8
0x140017451  cmp     qword ptr [rdi+18h], 7
0x140017456  jbe     short loc_14001745D
0x140017458  mov     rax, [rdi]
0x14001745b  jmp     short loc_140017460
0x14001745d  mov     rax, rdi
0x140017460  mov     [rsp+108h+var_A8], rax
0x140017465  lea     rax, aEnter; "Enter"
0x14001746c  mov     [rsp+108h+var_B8], rax
0x140017471  mov     [rsp+108h+var_B0], rbx
0x140017476  lea     r14, aGetdevicesuppo; "GetDeviceSupportedDataFormat"
0x14001747d  mov     [rsp+108h+var_A0], r14
0x140017482  lea     rax, [rsp+108h+var_A8]
0x140017487  mov     [rsp+108h+var_D0], rax
0x14001748c  lea     rax, [rsp+108h+var_B8]
0x140017491  mov     [rsp+108h+var_D8], rax
0x140017496  lea     rax, [rsp+108h+var_B0]
0x14001749b  mov     [rsp+108h+var_E0], rax
0x1400174a0  lea     rax, [rsp+108h+var_A0]
0x1400174a5  mov     [rsp+108h+var_E8], rax
0x1400174aa  lea     rdx, dword_140087954
0x1400174b1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x1400174b6  jmp     short loc_1400174BF
0x1400174b8  lea     r14, aGetdevicesuppo; "GetDeviceSupportedDataFormat"
0x1400174bf  xorps   xmm0, xmm0
0x1400174c2  movdqu  [rsp+108h+var_80], xmm0
0x1400174cb  mov     [rsp+108h+var_70], rbx
0x1400174d3  lea     rdx, [rsp+108h+var_80]
0x1400174db  lea     rcx, [rsp+108h+var_A8]
0x1400174e0  call    ??$single_threaded_vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@winrt@@YA?AU?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@0@$$QEAV?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@@Z; winrt::single_threaded_vector<winrt::hstring,std::allocator<winrt::hstring>>(std::vector<winrt::hstring> &&)
0x1400174e5  nop
0x1400174e6  lea     rcx, [rsp+108h+var_80]
0x1400174ee  call    ??1?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@QEAA@XZ; std::vector<winrt::hstring>::~vector<winrt::hstring>(void)
0x1400174f3  mov     [rsp+108h+var_58], 1
0x1400174fe  mov     [rsp+108h+var_54], 28h ; '('
0x140017509  lea     rax, a3f114a6a11fa4b_1; "{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} "...
0x140017510  mov     [rsp+108h+var_48], rax
0x140017518  lea     rax, [rsp+108h+var_58]
0x140017520  mov     [rsp+108h+var_60], rax
0x140017528  lea     rdx, [rsp+108h+var_60]
0x140017530  lea     rcx, [rsp+108h+var_A8]
0x140017535  call    ?Append@?$consume_Windows_Foundation_Collections_IVector@U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@winrt@@Uhstring@5@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::Append(winrt::param::hstring const &)
0x14001753a  mov     dword ptr [rsp+108h+var_B0], 1
0x140017542  lea     rdx, [rsp+108h+var_A8]
0x140017547  lea     rcx, [rsp+108h+var_40]
0x14001754f  call    ??$?0U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@winrt@@$0A@@?$async_iterable@Uhstring@winrt@@@param@winrt@@QEAA@AEBU?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@2@@Z; winrt::param::async_iterable<winrt::hstring>::async_iterable<winrt::hstring>(winrt::Windows::Foundation::Collections::IVector<winrt::hstring> const &)
0x140017554  nop
0x140017555  mov     rdx, [rdi+10h]
0x140017559  lea     r15, [rdi+18h]
0x14001755d  mov     [rsp+108h+var_A0], r15
0x140017562  cmp     qword ptr [r15], 7
0x140017566  jbe     short loc_14001756D
0x140017568  mov     rcx, [rdi]
0x14001756b  jmp     short loc_140017570
0x14001756d  mov     rcx, rdi
0x140017570  test    edx, edx
0x140017572  jnz     short loc_14001757E
0x140017574  mov     [rsp+108h+var_60], rbx
0x14001757c  jmp     short loc_1400175B7
0x14001757e  mov     eax, edx
0x140017580  cmp     [rcx+rax*2], bx
0x140017584  jz      short loc_14001758D
0x140017586  call    cs:__imp_abort
0x14001758d  mov     [rsp+108h+var_58], 1
0x140017598  mov     [rsp+108h+var_54], edx
0x14001759f  mov     [rsp+108h+var_48], rcx
0x1400175a7  lea     rax, [rsp+108h+var_58]
0x1400175af  mov     [rsp+108h+var_60], rax
0x1400175b7  lea     rax, [rsp+108h+var_60]
0x1400175bf  mov     qword ptr [rsp+108h+var_80], rax
0x1400175c7  lea     rax, [rsp+108h+var_40]
0x1400175cf  mov     qword ptr [rsp+108h+var_80+8], rax
0x1400175d7  lea     rax, [rsp+108h+var_B0]
0x1400175dc  mov     [rsp+108h+var_70], rax
0x1400175e4  lea     rax, qword_1400969F8
0x1400175eb  mov     [rsp+108h+var_30], rax
0x1400175f3  lock inc cs:qword_1400969F8
0x1400175fb  cmp     cs:??$factory_cache_entry_v@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@impl@winrt@@3U?$factory_cache_entry@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@12@A, rbx; factory_cache_entry<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>::winrt::factory_cache_entry<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2> winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>
0x140017602  jz      short loc_140017628
0x140017604  lea     r8, ??$factory_cache_entry_v@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@impl@winrt@@3U?$factory_cache_entry@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@12@A; factory_cache_entry<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>::winrt::factory_cache_entry<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2> winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>
0x14001760b  lea     rdx, [rsp+108h+var_B8]
0x140017610  lea     rcx, [rsp+108h+var_80]
0x140017618  call    ??R_lambda_1_@?1??CreateFromIdAsync@DeviceInformation@Enumeration@Devices@Windows@winrt@@SA@AEBUhstring@param@6@AEBU?$async_iterable@Uhstring@winrt@@@86@AEBW4DeviceInformationKind@3456@@Z@QEBA@AEBUIDeviceInformationStatics2@3456@@Z; `winrt::Windows::Devices::Enumeration::DeviceInformation::CreateFromIdAsync(winrt::param::hstring const &,winrt::param::async_iterable<winrt::hstring> const &,winrt::Windows::Devices::Enumeration::DeviceInformationKind const &)'::`2'::_lambda_1_::operator()(winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2 const &)
0x14001761d  nop
0x14001761e  lock dec cs:qword_1400969F8
0x140017626  jmp     short loc_140017643
0x140017628  lock dec cs:qword_1400969F8
0x140017630  lea     r8, [rsp+108h+var_80]
0x140017638  lea     rdx, [rsp+108h+var_B8]
0x14001763d  call    ??$call@AEAV_lambda_1_@?1??CreateFromIdAsync@DeviceInformation@Enumeration@Devices@Windows@winrt@@SA@AEBUhstring@param@7@AEBU?$async_iterable@Uhstring@winrt@@@97@AEBW4DeviceInformationKind@4567@@Z@@?$factory_cache_entry@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateFromIdAsync@DeviceInformation@Enumeration@Devices@Windows@2@SA@AEBUhstring@param@2@AEBU?$async_iterable@Uhstring@winrt@@@param@2@AEBW4DeviceInformationKind@6782@@Z@@Z
0x140017642  nop
0x140017643  lea     rdx, [rsp+108h+var_90]
0x140017648  lea     rcx, [rsp+108h+var_B8]
0x14001764d  call    ?get@?$consume_Windows_Foundation_IAsyncOperation@U?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@UDeviceInformation@Enumeration@Devices@34@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Devices::Enumeration::DeviceInformation>,winrt::Windows::Devices::Enumeration::DeviceInformation>::get(void)
0x140017652  nop
0x140017653  cmp     [rsp+108h+var_B8], rbx
0x140017658  jz      short loc_140017665
0x14001765a  lea     rcx, [rsp+108h+var_B8]
0x14001765f  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x140017664  nop
0x140017665  cmp     [rsp+108h+var_38], bl
0x14001766c  jnz     short loc_14001767B
0x14001766e  mov     rax, rbx
0x140017671  mov     [rsp+108h+var_40], rbx
0x140017679  jmp     short loc_140017683
0x14001767b  mov     rax, [rsp+108h+var_40]
0x140017683  test    rax, rax
0x140017686  jz      short loc_140017695
0x140017688  lea     rcx, [rsp+108h+var_40]
0x140017690  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x140017695  lea     rdx, [rsp+108h+var_B8]
0x14001769a  lea     rcx, [rsp+108h+var_90]
0x14001769f  call    ?Properties@?$consume_Windows_Devices_Enumeration_IDeviceInformation@UIDeviceInformation@Enumeration@Devices@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Properties(void)
0x1400176a4  nop
0x1400176a5  mov     dword ptr [rsp+108h+var_80+8], 1
0x1400176b0  mov     dword ptr [rsp+108h+var_80+0Ch], 28h ; '('
0x1400176bb  lea     rcx, a3f114a6a11fa4b_1; "{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} "...
0x1400176c2  mov     [rsp+108h+var_68], rcx
0x1400176ca  lea     rcx, [rsp+108h+var_80+8]
0x1400176d2  mov     qword ptr [rsp+108h+var_80], rcx
0x1400176da  lea     r8, [rsp+108h+var_80]
0x1400176e2  lea     rdx, [rsp+108h+var_98]
0x1400176e7  mov     rcx, rax
0x1400176ea  call    ?Lookup@?$consume_Windows_Foundation_Collections_IMapView@U?$IMapView@Uhstring@winrt@@UIInspectable@Foundation@Windows@2@@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMapView<winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Windows::Foundation::IInspectable>,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(winrt::param::hstring const &)
0x1400176ef  nop
0x1400176f0  cmp     [rsp+108h+var_B8], rbx
0x1400176f5  jz      short loc_140017701
0x1400176f7  lea     rcx, [rsp+108h+var_B8]
0x1400176fc  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x140017701  cmp     [rsp+108h+var_98], rbx
0x140017706  mov     dword ptr [rsi], 0FFFFFFFFh
0x14001770c  jz      short loc_14001773D
0x14001770e  lea     rcx, [rsp+108h+var_98]
0x140017713  call    ??$unbox_value@E@winrt@@YAEAEBUIInspectable@Foundation@Windows@0@@Z; winrt::unbox_value<uchar>(winrt::Windows::Foundation::IInspectable const &)
0x140017718  movzx   eax, al
0x14001771b  mov     [rsi], eax
0x14001771d  jmp     short loc_14001773D
0x14001771f  xor     ebx, ebx
0x140017721  lea     r14, aGetdevicesuppo; "GetDeviceSupportedDataFormat"
0x140017728  mov     rsi, [rsp+108h+var_88]
0x140017730  mov     rdi, [rsp+108h+var_28]
0x140017738  mov     r15, [rsp+108h+var_A0]
0x14001773d  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x140017742  mov     rcx, [rax+8]
0x140017746  mov     eax, [rcx]
0x140017748  cmp     eax, 4
0x14001774b  jbe     short loc_1400177C7
0x14001774d  mov     eax, [rsi]
0x14001774f  mov     dword ptr [rsp+108h+var_B0], eax
0x140017753  cmp     qword ptr [r15], 7
0x140017757  jbe     short loc_14001775E
0x140017759  mov     rax, [rdi]
0x14001775c  jmp     short loc_140017761
0x14001775e  mov     rax, rdi
0x140017761  mov     [rsp+108h+var_28], rax
0x140017769  lea     rax, aExit; "Exit"
0x140017770  mov     [rsp+108h+var_88], rax
0x140017778  mov     [rsp+108h+var_A0], rbx
0x14001777d  mov     [rsp+108h+var_B8], r14
0x140017782  lea     rax, [rsp+108h+var_B0]
0x140017787  mov     [rsp+108h+var_C8], rax
0x14001778c  lea     rax, [rsp+108h+var_28]
0x140017794  mov     [rsp+108h+var_D0], rax
0x140017799  lea     rax, [rsp+108h+var_88]
0x1400177a1  mov     [rsp+108h+var_D8], rax
0x1400177a6  lea     rax, [rsp+108h+var_A0]
0x1400177ab  mov     [rsp+108h+var_E0], rax
0x1400177b0  lea     rax, [rsp+108h+var_B8]
0x1400177b5  mov     [rsp+108h+var_E8], rax
0x1400177ba  lea     rdx, byte_140087F81
0x1400177c1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1400177c6  nop
0x1400177c7  cmp     [rsp+108h+var_98], rbx
0x1400177cc  jz      short loc_1400177D9
0x1400177ce  lea     rcx, [rsp+108h+var_98]
0x1400177d3  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1400177d8  nop
0x1400177d9  cmp     [rsp+108h+var_90], rbx
0x1400177de  jz      short loc_1400177EB
0x1400177e0  lea     rcx, [rsp+108h+var_90]
0x1400177e5  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1400177ea  nop
0x1400177eb  cmp     [rsp+108h+var_A8], rbx
0x1400177f0  jz      short loc_1400177FD
0x1400177f2  lea     rcx, [rsp+108h+var_A8]
0x1400177f7  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1400177fc  nop
0x1400177fd  mov     rcx, rdi; void *
0x140017800  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140017805  xor     eax, eax
0x140017807  mov     rcx, [rsp+108h+var_20]
0x14001780f  xor     rcx, rsp; StackCookie
0x140017812  call    __security_check_cookie
0x140017817  lea     r11, [rsp+108h+var_18]
0x14001781f  mov     rbx, [r11+30h]
0x140017823  mov     rsi, [r11+38h]
0x140017827  mov     rsp, r11
0x14001782a  pop     r15
0x14001782c  pop     r14
0x14001782e  pop     rdi
0x14001782f  retn
```
