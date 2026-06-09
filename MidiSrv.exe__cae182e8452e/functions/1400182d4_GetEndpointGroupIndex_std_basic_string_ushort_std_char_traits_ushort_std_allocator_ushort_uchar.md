# GetEndpointGroupIndex(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,uchar &)

- ea: `0x1400182d4`
- end: `0x14001876a`
- name: `?GetEndpointGroupIndex@@YAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAE@Z`
- size: `1174`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `18`
- tags: `service_task, broker_com_uri`

## callers

- `0x140018f54`
- `0x14001a680`

## callees

- `0x140001ce8`
- `0x140001f28`
- `0x1400054c0`
- `0x140007c20`
- `0x14000984c`
- `0x14000a6b4`
- `0x14000cc2c`
- `0x140012008`
- `0x140012b5c`
- `0x1400133f0`
- `0x1400135f8`
- `0x1400140c4`
- `0x140014688`
- `0x140014f04`
- `0x1400182d4`
- `0x14001bd28`
- `0x14001c390`
- `0x14001ecb4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x140018459`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x140018459`

## string_xrefs

- `0x1400185ff`: `avcore\midi2\service\exe\midiclientmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=13 #try_helpers=1
__int64 __fastcall GetEndpointGroupIndex(_QWORD *a1, wchar_t *a2)
{
  _DWORD *v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9
  const char *v7; // rax
  __int64 v8; // rdx
  __int64 *v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rax
  unsigned __int8 v12; // al
  _DWORD *v14; // rcx
  __int64 v15; // r8
  __int64 v16; // r9
  _QWORD *v17; // rax
  int v18; // [rsp+20h] [rbp-E8h]
  const char *v19; // [rsp+50h] [rbp-B8h] BYREF
  const wchar_t *v20; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v21; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v22; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v23; // [rsp+70h] [rbp-98h] BYREF
  const char *v24; // [rsp+78h] [rbp-90h] BYREF
  const wchar_t *v25; // [rsp+80h] [rbp-88h] BYREF
  __int128 v26; // [rsp+88h] [rbp-80h] BYREF
  __int64 *v27; // [rsp+98h] [rbp-70h]
  const wchar_t *v28; // [rsp+A0h] [rbp-68h]
  int *v29; // [rsp+A8h] [rbp-60h] BYREF
  int v30; // [rsp+B0h] [rbp-58h] BYREF
  int v31; // [rsp+B4h] [rbp-54h]
  const wchar_t *v32; // [rsp+C0h] [rbp-48h]
  __int64 v33; // [rsp+C8h] [rbp-40h] BYREF
  char v34; // [rsp+D0h] [rbp-38h]
  __int64 *v35; // [rsp+D8h] [rbp-30h]
  _QWORD *v36; // [rsp+E0h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  v36 = a1;
  v25 = a2;
  v4 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v4 > 4u )
  {
    if ( a1[3] <= 7u )
      v7 = (const char *)a1;
    else
      v7 = (const char *)*a1;
    v19 = v7;
    v20 = L"Enter";
    v21 = 0;
    v24 = "GetEndpointGroupIndex";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (__int64)v4,
      (__int64)qword_140087A00,
      v5,
      v6,
      &v24,
      (__int64)&v21,
      &v20,
      &v19);
  }
  *(_BYTE *)a2 = -1;
  v26 = 0;
  v27 = 0;
  winrt::single_threaded_vector<winrt::hstring,std::allocator<winrt::hstring>>(&v20, (__int64 *)&v26);
  std::vector<winrt::hstring>::~vector<winrt::hstring>((__int64)&v26);
  v30 = 1;
  v31 = 41;
  v32 = L"{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} 18";
  v29 = &v30;
  winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::Append(
    &v20,
    &v29);
  LODWORD(v21) = 1;
  winrt::param::async_iterable<winrt::hstring>::async_iterable<winrt::hstring>(&v33, &v20);
  v8 = a1[2];
  v24 = (const char *)(a1 + 3);
  if ( a1[3] <= 7u )
    v9 = a1;
  else
    v9 = (__int64 *)*a1;
  if ( (_DWORD)v8 )
  {
    if ( *((_WORD *)v9 + (unsigned int)v8) )
      abort();
    v30 = 1;
    v31 = v8;
    v32 = (const wchar_t *)v9;
    v29 = &v30;
  }
  else
  {
    v29 = 0;
  }
  *(_QWORD *)&v26 = &v29;
  *((_QWORD *)&v26 + 1) = &v33;
  v27 = &v21;
  v35 = &qword_1400969F8;
  _InterlockedIncrement64(&qword_1400969F8);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2> )
  {
    `winrt::Windows::Devices::Enumeration::DeviceInformation::CreateFromIdAsync'::`2'::_lambda_1_::operator()(
      (__int64)&v26,
      &v19,
      (__int64 **)&winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>);
    _InterlockedDecrement64(&qword_1400969F8);
  }
  else
  {
    _InterlockedDecrement64(&qword_1400969F8);
    ___call_AEAV_lambda_1___1__CreateFromIdAsync_DeviceInformation_Enumeration_Devices_Windows_winrt__SA_AEBUhstring_param_7_AEBU__async_iterable_Uhstring_winrt___97_AEBW4DeviceInformationKind_4567__Z____factory_cache_entry_UDeviceInformation_Enumeration_Devices_Windows_winrt__UIDeviceInformationStatics2_2345__impl_winrt__QEAA_A_PAEAV_lambda_1___1__CreateFromIdAsync_DeviceInformation_Enumeration_Devices_Windows_2_SA_AEBUhstring_param_2_AEBU__async_iterable_Uhstring_winrt___param_2_AEBW4DeviceInformationKind_6782__Z__Z(
      v9,
      (__int64)&v19,
      (__int64)&v26);
  }
  winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Devices::Enumeration::DeviceInformation>,winrt::Windows::Devices::Enumeration::DeviceInformation>::get(
    &v19,
    &v23);
  if ( v19 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v19);
  if ( v34 )
  {
    v10 = v33;
  }
  else
  {
    v10 = 0;
    v33 = 0;
  }
  if ( v10 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v33);
  v11 = winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Properties(
          &v23,
          &v19);
  *((_QWORD *)&v26 + 1) = 0x2900000001LL;
  v28 = L"{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} 18";
  *(_QWORD *)&v26 = (char *)&v26 + 8;
  winrt::impl::consume_Windows_Foundation_Collections_IMapView<winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Windows::Foundation::IInspectable>,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(
    v11,
    &v22,
    &v26);
  if ( v19 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v19);
  if ( v22 && (v12 = winrt::unbox_value<unsigned int>(&v22), *(_BYTE *)a2 = v12, v12 > 0xFu) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x15E,
      (unsigned int)"avcore\\midi2\\service\\exe\\midiclientmanager.cpp",
      (const char *)0x800701DALL,
      v18);
    if ( v22 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v22);
    if ( v23 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v23);
    if ( v20 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v20);
    std::wstring::~wstring((char **)a1);
    return 2147942874LL;
  }
  else
  {
    v14 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
    if ( *v14 > 4u )
    {
      LODWORD(v21) = *(unsigned __int8 *)a2;
      if ( a1[3] <= 7u )
        v17 = a1;
      else
        v17 = (_QWORD *)*a1;
      v36 = v17;
      v25 = L"Exit";
      v24 = 0;
      v19 = "GetEndpointGroupIndex";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        (__int64)v14,
        (__int64)&unk_140087A88,
        v15,
        v16,
        &v19,
        (__int64)&v24,
        &v25,
        &v36);
    }
    if ( v22 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v22);
    if ( v23 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v23);
    if ( v20 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v20);
    std::wstring::~wstring((char **)a1);
    return 0;
  }
}

```

## disassembly

```asm
0x1400182d4  mov     r11, rsp
0x1400182d7  mov     [r11+18h], rbx
0x1400182db  mov     [r11+20h], rsi
0x1400182df  push    rdi
0x1400182e0  push    r14
0x1400182e2  push    r15
0x1400182e4  sub     rsp, 0F0h
0x1400182eb  mov     rax, cs:__security_cookie
0x1400182f2  xor     rax, rsp
0x1400182f5  mov     [rsp+108h+var_20], rax
0x1400182fd  mov     rsi, rdx
0x140018300  mov     rdi, rcx
0x140018303  mov     [r11-28h], rcx
0x140018307  mov     [rsp+108h+var_88], rdx
0x14001830f  xor     ebx, ebx
0x140018311  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x140018316  mov     rcx, [rax+8]
0x14001831a  mov     eax, [rcx]
0x14001831c  cmp     eax, 4
0x14001831f  jbe     short loc_140018388
0x140018321  cmp     qword ptr [rdi+18h], 7
0x140018326  jbe     short loc_14001832D
0x140018328  mov     rax, [rdi]
0x14001832b  jmp     short loc_140018330
0x14001832d  mov     rax, rdi
0x140018330  mov     [rsp+108h+var_B8], rax
0x140018335  lea     rax, aEnter; "Enter"
0x14001833c  mov     [rsp+108h+var_B0], rax
0x140018341  mov     [rsp+108h+var_A8], rbx
0x140018346  lea     r14, aGetendpointgro; "GetEndpointGroupIndex"
0x14001834d  mov     [rsp+108h+var_90], r14
0x140018352  lea     rax, [rsp+108h+var_B8]
0x140018357  mov     [rsp+108h+var_D0], rax
0x14001835c  lea     rax, [rsp+108h+var_B0]
0x140018361  mov     [rsp+108h+var_D8], rax
0x140018366  lea     rax, [rsp+108h+var_A8]
0x14001836b  mov     [rsp+108h+var_E0], rax
0x140018370  lea     rax, [rsp+108h+var_90]
0x140018375  mov     [rsp+108h+var_E8], rax
0x14001837a  lea     rdx, qword_140087A00
0x140018381  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x140018386  jmp     short loc_14001838F
0x140018388  lea     r14, aGetendpointgro; "GetEndpointGroupIndex"
0x14001838f  mov     byte ptr [rsi], 0FFh
0x140018392  xorps   xmm0, xmm0
0x140018395  movdqu  [rsp+108h+var_80], xmm0
0x14001839e  mov     [rsp+108h+var_70], rbx
0x1400183a6  lea     rdx, [rsp+108h+var_80]
0x1400183ae  lea     rcx, [rsp+108h+var_B0]
0x1400183b3  call    ??$single_threaded_vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@winrt@@YA?AU?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@0@$$QEAV?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@@Z; winrt::single_threaded_vector<winrt::hstring,std::allocator<winrt::hstring>>(std::vector<winrt::hstring> &&)
0x1400183b8  nop
0x1400183b9  lea     rcx, [rsp+108h+var_80]
0x1400183c1  call    ??1?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@QEAA@XZ; std::vector<winrt::hstring>::~vector<winrt::hstring>(void)
0x1400183c6  mov     [rsp+108h+var_58], 1
0x1400183d1  mov     [rsp+108h+var_54], 29h ; ')'
0x1400183dc  lea     rax, a3f114a6a11fa4b_6; "{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} "...
0x1400183e3  mov     [rsp+108h+var_48], rax
0x1400183eb  lea     rax, [rsp+108h+var_58]
0x1400183f3  mov     [rsp+108h+var_60], rax
0x1400183fb  lea     rdx, [rsp+108h+var_60]
0x140018403  lea     rcx, [rsp+108h+var_B0]
0x140018408  call    ?Append@?$consume_Windows_Foundation_Collections_IVector@U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@winrt@@Uhstring@5@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::Append(winrt::param::hstring const &)
0x14001840d  mov     dword ptr [rsp+108h+var_A8], 1
0x140018415  lea     rdx, [rsp+108h+var_B0]
0x14001841a  lea     rcx, [rsp+108h+var_40]
0x140018422  call    ??$?0U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@winrt@@$0A@@?$async_iterable@Uhstring@winrt@@@param@winrt@@QEAA@AEBU?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@2@@Z; winrt::param::async_iterable<winrt::hstring>::async_iterable<winrt::hstring>(winrt::Windows::Foundation::Collections::IVector<winrt::hstring> const &)
0x140018427  nop
0x140018428  mov     rdx, [rdi+10h]
0x14001842c  lea     r15, [rdi+18h]
0x140018430  mov     [rsp+108h+var_90], r15
0x140018435  cmp     qword ptr [r15], 7
0x140018439  jbe     short loc_140018440
0x14001843b  mov     rcx, [rdi]
0x14001843e  jmp     short loc_140018443
0x140018440  mov     rcx, rdi
0x140018443  test    edx, edx
0x140018445  jnz     short loc_140018451
0x140018447  mov     [rsp+108h+var_60], rbx
0x14001844f  jmp     short loc_14001848A
0x140018451  mov     eax, edx
0x140018453  cmp     [rcx+rax*2], bx
0x140018457  jz      short loc_140018460
0x140018459  call    cs:__imp_abort
0x140018460  mov     [rsp+108h+var_58], 1
0x14001846b  mov     [rsp+108h+var_54], edx
0x140018472  mov     [rsp+108h+var_48], rcx
0x14001847a  lea     rax, [rsp+108h+var_58]
0x140018482  mov     [rsp+108h+var_60], rax
0x14001848a  lea     rax, [rsp+108h+var_60]
0x140018492  mov     qword ptr [rsp+108h+var_80], rax
0x14001849a  lea     rax, [rsp+108h+var_40]
0x1400184a2  mov     qword ptr [rsp+108h+var_80+8], rax
0x1400184aa  lea     rax, [rsp+108h+var_A8]
0x1400184af  mov     [rsp+108h+var_70], rax
0x1400184b7  lea     rax, qword_1400969F8
0x1400184be  mov     [rsp+108h+var_30], rax
0x1400184c6  lock inc cs:qword_1400969F8
0x1400184ce  cmp     cs:??$factory_cache_entry_v@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@impl@winrt@@3U?$factory_cache_entry@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@12@A, rbx; factory_cache_entry<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>::winrt::factory_cache_entry<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2> winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>
0x1400184d5  jz      short loc_1400184FB
0x1400184d7  lea     r8, ??$factory_cache_entry_v@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@impl@winrt@@3U?$factory_cache_entry@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@12@A; factory_cache_entry<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>::winrt::factory_cache_entry<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2> winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>
0x1400184de  lea     rdx, [rsp+108h+var_B8]
0x1400184e3  lea     rcx, [rsp+108h+var_80]
0x1400184eb  call    ??R_lambda_1_@?1??CreateFromIdAsync@DeviceInformation@Enumeration@Devices@Windows@winrt@@SA@AEBUhstring@param@6@AEBU?$async_iterable@Uhstring@winrt@@@86@AEBW4DeviceInformationKind@3456@@Z@QEBA@AEBUIDeviceInformationStatics2@3456@@Z; `winrt::Windows::Devices::Enumeration::DeviceInformation::CreateFromIdAsync(winrt::param::hstring const &,winrt::param::async_iterable<winrt::hstring> const &,winrt::Windows::Devices::Enumeration::DeviceInformationKind const &)'::`2'::_lambda_1_::operator()(winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2 const &)
0x1400184f0  nop
0x1400184f1  lock dec cs:qword_1400969F8
0x1400184f9  jmp     short loc_140018516
0x1400184fb  lock dec cs:qword_1400969F8
0x140018503  lea     r8, [rsp+108h+var_80]
0x14001850b  lea     rdx, [rsp+108h+var_B8]
0x140018510  call    ??$call@AEAV_lambda_1_@?1??CreateFromIdAsync@DeviceInformation@Enumeration@Devices@Windows@winrt@@SA@AEBUhstring@param@7@AEBU?$async_iterable@Uhstring@winrt@@@97@AEBW4DeviceInformationKind@4567@@Z@@?$factory_cache_entry@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateFromIdAsync@DeviceInformation@Enumeration@Devices@Windows@2@SA@AEBUhstring@param@2@AEBU?$async_iterable@Uhstring@winrt@@@param@2@AEBW4DeviceInformationKind@6782@@Z@@Z
0x140018515  nop
0x140018516  lea     rdx, [rsp+108h+var_98]
0x14001851b  lea     rcx, [rsp+108h+var_B8]
0x140018520  call    ?get@?$consume_Windows_Foundation_IAsyncOperation@U?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@UDeviceInformation@Enumeration@Devices@34@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Devices::Enumeration::DeviceInformation>,winrt::Windows::Devices::Enumeration::DeviceInformation>::get(void)
0x140018525  nop
0x140018526  cmp     [rsp+108h+var_B8], rbx
0x14001852b  jz      short loc_140018538
0x14001852d  lea     rcx, [rsp+108h+var_B8]
0x140018532  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x140018537  nop
0x140018538  cmp     [rsp+108h+var_38], bl
0x14001853f  jnz     short loc_14001854E
0x140018541  mov     rax, rbx
0x140018544  mov     [rsp+108h+var_40], rbx
0x14001854c  jmp     short loc_140018556
0x14001854e  mov     rax, [rsp+108h+var_40]
0x140018556  test    rax, rax
0x140018559  jz      short loc_140018568
0x14001855b  lea     rcx, [rsp+108h+var_40]
0x140018563  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x140018568  lea     rdx, [rsp+108h+var_B8]
0x14001856d  lea     rcx, [rsp+108h+var_98]
0x140018572  call    ?Properties@?$consume_Windows_Devices_Enumeration_IDeviceInformation@UIDeviceInformation@Enumeration@Devices@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Properties(void)
0x140018577  nop
0x140018578  mov     dword ptr [rsp+108h+var_80+8], 1
0x140018583  mov     dword ptr [rsp+108h+var_80+0Ch], 29h ; ')'
0x14001858e  lea     rcx, a3f114a6a11fa4b_6; "{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} "...
0x140018595  mov     [rsp+108h+var_68], rcx
0x14001859d  lea     rcx, [rsp+108h+var_80+8]
0x1400185a5  mov     qword ptr [rsp+108h+var_80], rcx
0x1400185ad  lea     r8, [rsp+108h+var_80]
0x1400185b5  lea     rdx, [rsp+108h+var_A0]
0x1400185ba  mov     rcx, rax
0x1400185bd  call    ?Lookup@?$consume_Windows_Foundation_Collections_IMapView@U?$IMapView@Uhstring@winrt@@UIInspectable@Foundation@Windows@2@@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMapView<winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Windows::Foundation::IInspectable>,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(winrt::param::hstring const &)
0x1400185c2  nop
0x1400185c3  cmp     [rsp+108h+var_B8], rbx
0x1400185c8  jz      short loc_1400185D4
0x1400185ca  lea     rcx, [rsp+108h+var_B8]
0x1400185cf  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1400185d4  cmp     [rsp+108h+var_A0], rbx
0x1400185d9  jz      loc_140018676
0x1400185df  lea     rcx, [rsp+108h+var_A0]
0x1400185e4  call    ??$unbox_value@I@winrt@@YAIAEBUIInspectable@Foundation@Windows@0@@Z; winrt::unbox_value<uint>(winrt::Windows::Foundation::IInspectable const &)
0x1400185e9  mov     [rsi], al
0x1400185eb  cmp     al, 0Fh
0x1400185ed  jbe     short loc_140018656
0x1400185ef  mov     rcx, [rsp+108h]; this
0x1400185f7  mov     esi, 800701DAh
0x1400185fc  mov     r9d, esi; char *
0x1400185ff  lea     r8, aAvcoreMidi2Ser_1; "avcore\\midi2\\service\\exe\\midiclient"...
0x140018606  mov     edx, 15Eh; void *
0x14001860b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140018610  nop
0x140018611  cmp     [rsp+108h+var_A0], rbx
0x140018616  jz      short loc_140018623
0x140018618  lea     rcx, [rsp+108h+var_A0]
0x14001861d  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x140018622  nop
0x140018623  cmp     [rsp+108h+var_98], rbx
0x140018628  jz      short loc_140018635
0x14001862a  lea     rcx, [rsp+108h+var_98]
0x14001862f  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x140018634  nop
0x140018635  cmp     [rsp+108h+var_B0], rbx
0x14001863a  jz      short loc_140018647
0x14001863c  lea     rcx, [rsp+108h+var_B0]
0x140018641  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x140018646  nop
0x140018647  mov     rcx, rdi; void *
0x14001864a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001864f  mov     eax, esi
0x140018651  jmp     loc_140018741
0x140018656  jmp     short loc_140018676
0x140018658  xor     ebx, ebx
0x14001865a  lea     r14, aGetendpointgro; "GetEndpointGroupIndex"
0x140018661  mov     rsi, [rsp+108h+var_88]
0x140018669  mov     rdi, [rsp+108h+var_28]
0x140018671  mov     r15, [rsp+108h+var_90]
0x140018676  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14001867b  mov     rcx, [rax+8]
0x14001867f  mov     eax, [rcx]
0x140018681  cmp     eax, 4
0x140018684  jbe     short loc_140018701
0x140018686  movzx   eax, byte ptr [rsi]
0x140018689  mov     dword ptr [rsp+108h+var_A8], eax
0x14001868d  cmp     qword ptr [r15], 7
0x140018691  jbe     short loc_140018698
0x140018693  mov     rax, [rdi]
0x140018696  jmp     short loc_14001869B
0x140018698  mov     rax, rdi
0x14001869b  mov     [rsp+108h+var_28], rax
0x1400186a3  lea     rax, aExit; "Exit"
0x1400186aa  mov     [rsp+108h+var_88], rax
0x1400186b2  mov     [rsp+108h+var_90], rbx
0x1400186b7  mov     [rsp+108h+var_B8], r14
0x1400186bc  lea     rax, [rsp+108h+var_A8]
0x1400186c1  mov     [rsp+108h+var_C8], rax
0x1400186c6  lea     rax, [rsp+108h+var_28]
0x1400186ce  mov     [rsp+108h+var_D0], rax
0x1400186d3  lea     rax, [rsp+108h+var_88]
0x1400186db  mov     [rsp+108h+var_D8], rax
0x1400186e0  lea     rax, [rsp+108h+var_90]
0x1400186e5  mov     [rsp+108h+var_E0], rax
0x1400186ea  lea     rax, [rsp+108h+var_B8]
0x1400186ef  mov     [rsp+108h+var_E8], rax
0x1400186f4  lea     rdx, unk_140087A88
0x1400186fb  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x140018700  nop
0x140018701  cmp     [rsp+108h+var_A0], rbx
0x140018706  jz      short loc_140018713
0x140018708  lea     rcx, [rsp+108h+var_A0]
0x14001870d  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x140018712  nop
0x140018713  cmp     [rsp+108h+var_98], rbx
0x140018718  jz      short loc_140018725
0x14001871a  lea     rcx, [rsp+108h+var_98]
0x14001871f  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x140018724  nop
0x140018725  cmp     [rsp+108h+var_B0], rbx
0x14001872a  jz      short loc_140018737
0x14001872c  lea     rcx, [rsp+108h+var_B0]
0x140018731  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x140018736  nop
0x140018737  mov     rcx, rdi; void *
0x14001873a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001873f  xor     eax, eax
0x140018741  mov     rcx, [rsp+108h+var_20]
0x140018749  xor     rcx, rsp; StackCookie
0x14001874c  call    __security_check_cookie
0x140018751  lea     r11, [rsp+108h+var_18]
0x140018759  mov     rbx, [r11+30h]
0x14001875d  mov     rsi, [r11+38h]
0x140018761  mov     rsp, r11
0x140018764  pop     r15
0x140018766  pop     r14
0x140018768  pop     rdi
0x140018769  retn
```
