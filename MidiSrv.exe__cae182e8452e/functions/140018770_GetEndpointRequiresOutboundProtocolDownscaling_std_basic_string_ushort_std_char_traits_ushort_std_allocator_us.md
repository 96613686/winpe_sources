# GetEndpointRequiresOutboundProtocolDownscaling(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0002,__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0001,bool &)

- ea: `0x140018770`
- end: `0x140018a88`
- name: `?GetEndpointRequiresOutboundProtocolDownscaling@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0002@@W4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0001@@AEA_N@Z`
- size: `792`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400152d0`

## callees

- `0x140001ce8`
- `0x140001f28`
- `0x14000984c`
- `0x14000cc2c`
- `0x140012008`
- `0x140012b5c`
- `0x1400133f0`
- `0x140013528`
- `0x1400140c4`
- `0x140014688`
- `0x140014f04`
- `0x140018770`
- `0x14001bd28`
- `0x14001c390`
- `0x14001ecb4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1400188ac`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1400188ac`

## string_xrefs

- `0x1400187aa`: `GetEndpointRequiresOutboundProtocolDownscaling`
- `0x1400189f4`: `GetEndpointRequiresOutboundProtocolDownscaling`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall GetEndpointRequiresOutboundProtocolDownscaling(__int64 *a1, int a2, int a3, _BYTE *a4)
{
  _DWORD *v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r9
  _QWORD *v11; // rdi
  __int64 *v12; // rax
  __int64 v13; // rdx
  __int64 *v14; // rcx
  __int64 v15; // rax
  __int64 v16; // rax
  _DWORD *v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  const char *v21; // [rsp+50h] [rbp-49h] BYREF
  __int64 v22; // [rsp+58h] [rbp-41h] BYREF
  const wchar_t *v23; // [rsp+60h] [rbp-39h] BYREF
  __int128 v24; // [rsp+68h] [rbp-31h] BYREF
  int *v25; // [rsp+78h] [rbp-21h]
  const wchar_t *v26; // [rsp+80h] [rbp-19h]
  int *v27; // [rsp+88h] [rbp-11h] BYREF
  int v28; // [rsp+90h] [rbp-9h] BYREF
  int v29; // [rsp+94h] [rbp-5h]
  const wchar_t *v30; // [rsp+A0h] [rbp+7h]
  __int64 v31; // [rsp+A8h] [rbp+Fh] BYREF
  char v32; // [rsp+B0h] [rbp+17h]
  __int64 *v33; // [rsp+B8h] [rbp+1Fh]
  int v34; // [rsp+110h] [rbp+77h] BYREF
  __int64 *v35; // [rsp+118h] [rbp+7Fh] BYREF

  v8 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  v11 = a1 + 3;
  if ( *v8 > 4u )
  {
    if ( *v11 <= 7u )
      v12 = a1;
    else
      v12 = (__int64 *)*a1;
    v35 = v12;
    v23 = L"Enter";
    v22 = 0;
    v21 = "GetEndpointRequiresOutboundProtocolDownscaling";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (__int64)v8,
      (__int64)byte_140087499,
      v9,
      v10,
      &v21,
      (__int64)&v22,
      &v23,
      &v35);
  }
  *a4 = 0;
  if ( a3 == 2 && (unsigned int)(a2 - 1) <= 1 )
  {
    v24 = 0;
    v25 = 0;
    winrt::single_threaded_vector<winrt::hstring,std::allocator<winrt::hstring>>(&v22, (__int64 *)&v24);
    std::vector<winrt::hstring>::~vector<winrt::hstring>((__int64)&v24);
    v28 = 1;
    v29 = 40;
    v30 = L"{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} 3";
    v27 = &v28;
    winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::Append(
      &v22,
      &v27);
    v34 = 1;
    winrt::param::async_iterable<winrt::hstring>::async_iterable<winrt::hstring>(&v31, &v22);
    v13 = a1[2];
    if ( *v11 <= 7u )
      v14 = a1;
    else
      v14 = (__int64 *)*a1;
    if ( (_DWORD)v13 )
    {
      if ( *((_WORD *)v14 + (unsigned int)v13) )
        abort();
      v28 = 1;
      v29 = v13;
      v30 = (const wchar_t *)v14;
      v27 = &v28;
    }
    else
    {
      v27 = 0;
    }
    *(_QWORD *)&v24 = &v27;
    *((_QWORD *)&v24 + 1) = &v31;
    v25 = &v34;
    v33 = &qword_1400969F8;
    _InterlockedAdd64(&qword_1400969F8, 1u);
    if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2> )
    {
      `winrt::Windows::Devices::Enumeration::DeviceInformation::CreateFromIdAsync'::`2'::_lambda_1_::operator()(
        (__int64)&v24,
        &v35,
        (__int64 **)&winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>);
      _InterlockedDecrement64(&qword_1400969F8);
    }
    else
    {
      _InterlockedDecrement64(&qword_1400969F8);
      ___call_AEAV_lambda_1___1__CreateFromIdAsync_DeviceInformation_Enumeration_Devices_Windows_winrt__SA_AEBUhstring_param_7_AEBU__async_iterable_Uhstring_winrt___97_AEBW4DeviceInformationKind_4567__Z____factory_cache_entry_UDeviceInformation_Enumeration_Devices_Windows_winrt__UIDeviceInformationStatics2_2345__impl_winrt__QEAA_A_PAEAV_lambda_1___1__CreateFromIdAsync_DeviceInformation_Enumeration_Devices_Windows_2_SA_AEBUhstring_param_2_AEBU__async_iterable_Uhstring_winrt___param_2_AEBW4DeviceInformationKind_6782__Z__Z(
        v14,
        (__int64)&v35,
        (__int64)&v24);
    }
    winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Devices::Enumeration::DeviceInformation>,winrt::Windows::Devices::Enumeration::DeviceInformation>::get(
      &v35,
      &v23);
    if ( v35 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v35);
    if ( v32 )
    {
      v15 = v31;
    }
    else
    {
      v15 = 0;
      v31 = 0;
    }
    if ( v15 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v31);
    v16 = winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Properties(
            &v23,
            &v35);
    *((_QWORD *)&v24 + 1) = 0x2800000001LL;
    v26 = L"{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} 3";
    *(_QWORD *)&v24 = (char *)&v24 + 8;
    winrt::impl::consume_Windows_Foundation_Collections_IMapView<winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Windows::Foundation::IInspectable>,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(
      v16,
      &v21,
      &v24);
    if ( v35 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v35);
    if ( v21 && (unsigned __int8)winrt::unbox_value<unsigned char>(&v21) == 1 )
      *a4 = 1;
    if ( v21 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v21);
    if ( v23 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v23);
    if ( v22 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v22);
  }
  v17 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v17 > 4u )
  {
    v34 = (unsigned __int8)*a4;
    if ( *v11 > 7u )
      a1 = (__int64 *)*a1;
    v35 = a1;
    v23 = L"Exit";
    v22 = 0;
    v21 = "GetEndpointRequiresOutboundProtocolDownscaling";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      (__int64)v17,
      (__int64)&byte_14008840F,
      v18,
      v19,
      &v21,
      (__int64)&v22,
      &v23,
      &v35);
  }
  return 0;
}

```

## disassembly

```asm
0x140018770  mov     [rsp-8+arg_0], rbx
0x140018775  push    rbp
0x140018776  push    rsi
0x140018777  push    rdi
0x140018778  push    r12
0x14001877a  push    r13
0x14001877c  push    r14
0x14001877e  push    r15
0x140018780  lea     rbp, [rsp-27h]
0x140018785  sub     rsp, 0C0h
0x14001878c  mov     r15, r9
0x14001878f  mov     esi, r8d
0x140018792  mov     r14d, edx
0x140018795  mov     rbx, rcx
0x140018798  xor     r12d, r12d
0x14001879b  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x1400187a0  mov     rcx, [rax+8]
0x1400187a4  mov     eax, [rcx]
0x1400187a6  lea     rdi, [rbx+18h]
0x1400187aa  lea     r13, aGetendpointreq; "GetEndpointRequiresOutboundProtocolDown"...
0x1400187b1  cmp     eax, 4
0x1400187b4  jbe     short loc_14001880B
0x1400187b6  cmp     qword ptr [rdi], 7
0x1400187ba  jbe     short loc_1400187C1
0x1400187bc  mov     rax, [rbx]
0x1400187bf  jmp     short loc_1400187C4
0x1400187c1  mov     rax, rbx
0x1400187c4  mov     [rbp+57h+arg_18], rax
0x1400187c8  lea     rax, aEnter; "Enter"
0x1400187cf  mov     [rbp+57h+var_90], rax
0x1400187d3  mov     [rbp+57h+var_98], r12
0x1400187d7  mov     [rbp+57h+var_A0], r13
0x1400187db  lea     rax, [rbp+57h+arg_18]
0x1400187df  mov     [rsp+0F0h+var_B8], rax
0x1400187e4  lea     rax, [rbp+57h+var_90]
0x1400187e8  mov     [rsp+0F0h+var_C0], rax
0x1400187ed  lea     rax, [rbp+57h+var_98]
0x1400187f1  mov     [rsp+0F0h+var_C8], rax
0x1400187f6  lea     rax, [rbp+57h+var_A0]
0x1400187fa  mov     [rsp+0F0h+var_D0], rax
0x1400187ff  lea     rdx, byte_140087499
0x140018806  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x14001880b  mov     [r15], r12b
0x14001880e  cmp     esi, 2
0x140018811  jnz     loc_1400189FB
0x140018817  lea     eax, [r14-1]
0x14001881b  mov     esi, 1
0x140018820  cmp     eax, esi
0x140018822  ja      loc_1400189FB
0x140018828  xorps   xmm0, xmm0
0x14001882b  movdqu  [rbp+57h+var_88], xmm0
0x140018830  mov     [rbp+57h+var_78], r12
0x140018834  lea     rdx, [rbp+57h+var_88]
0x140018838  lea     rcx, [rbp+57h+var_98]
0x14001883c  call    ??$single_threaded_vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@winrt@@YA?AU?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@0@$$QEAV?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@@Z; winrt::single_threaded_vector<winrt::hstring,std::allocator<winrt::hstring>>(std::vector<winrt::hstring> &&)
0x140018841  nop
0x140018842  lea     rcx, [rbp+57h+var_88]
0x140018846  call    ??1?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@QEAA@XZ; std::vector<winrt::hstring>::~vector<winrt::hstring>(void)
0x14001884b  mov     [rbp+57h+var_60], esi
0x14001884e  lea     r14d, [rsi+27h]
0x140018852  mov     [rbp+57h+var_5C], r14d
0x140018856  lea     r13, a3f114a6a11fa4b_11; "{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} "...
0x14001885d  mov     [rbp+57h+var_50], r13
0x140018861  lea     rax, [rbp+57h+var_60]
0x140018865  mov     [rbp+57h+var_68], rax
0x140018869  lea     rdx, [rbp+57h+var_68]
0x14001886d  lea     rcx, [rbp+57h+var_98]
0x140018871  call    ?Append@?$consume_Windows_Foundation_Collections_IVector@U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@winrt@@Uhstring@5@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::Append(winrt::param::hstring const &)
0x140018876  mov     [rbp+57h+arg_10], esi
0x140018879  lea     rdx, [rbp+57h+var_98]
0x14001887d  lea     rcx, [rbp+57h+var_48]
0x140018881  call    ??$?0U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@winrt@@$0A@@?$async_iterable@Uhstring@winrt@@@param@winrt@@QEAA@AEBU?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@2@@Z; winrt::param::async_iterable<winrt::hstring>::async_iterable<winrt::hstring>(winrt::Windows::Foundation::Collections::IVector<winrt::hstring> const &)
0x140018886  nop
0x140018887  mov     rdx, [rbx+10h]
0x14001888b  cmp     qword ptr [rdi], 7
0x14001888f  jbe     short loc_140018896
0x140018891  mov     rcx, [rbx]
0x140018894  jmp     short loc_140018899
0x140018896  mov     rcx, rbx
0x140018899  test    edx, edx
0x14001889b  jnz     short loc_1400188A3
0x14001889d  mov     [rbp+57h+var_68], r12
0x1400188a1  jmp     short loc_1400188C5
0x1400188a3  mov     eax, edx
0x1400188a5  cmp     [rcx+rax*2], r12w
0x1400188aa  jz      short loc_1400188B3
0x1400188ac  call    cs:__imp_abort
0x1400188b3  mov     [rbp+57h+var_60], esi
0x1400188b6  mov     [rbp+57h+var_5C], edx
0x1400188b9  mov     [rbp+57h+var_50], rcx
0x1400188bd  lea     rax, [rbp+57h+var_60]
0x1400188c1  mov     [rbp+57h+var_68], rax
0x1400188c5  lea     rax, [rbp+57h+var_68]
0x1400188c9  mov     qword ptr [rbp+57h+var_88], rax
0x1400188cd  lea     rax, [rbp+57h+var_48]
0x1400188d1  mov     qword ptr [rbp+57h+var_88+8], rax
0x1400188d5  lea     rax, [rbp+57h+arg_10]
0x1400188d9  mov     [rbp+57h+var_78], rax
0x1400188dd  lea     rax, qword_1400969F8
0x1400188e4  mov     [rbp+57h+var_38], rax
0x1400188e8  lock add cs:qword_1400969F8, rsi
0x1400188f0  cmp     cs:??$factory_cache_entry_v@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@impl@winrt@@3U?$factory_cache_entry@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@12@A, r12; factory_cache_entry<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>::winrt::factory_cache_entry<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2> winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>
0x1400188f7  jz      short loc_140018918
0x1400188f9  lea     r8, ??$factory_cache_entry_v@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@impl@winrt@@3U?$factory_cache_entry@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@12@A; factory_cache_entry<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>::winrt::factory_cache_entry<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2> winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>
0x140018900  lea     rdx, [rbp+57h+arg_18]
0x140018904  lea     rcx, [rbp+57h+var_88]
0x140018908  call    ??R_lambda_1_@?1??CreateFromIdAsync@DeviceInformation@Enumeration@Devices@Windows@winrt@@SA@AEBUhstring@param@6@AEBU?$async_iterable@Uhstring@winrt@@@86@AEBW4DeviceInformationKind@3456@@Z@QEBA@AEBUIDeviceInformationStatics2@3456@@Z; `winrt::Windows::Devices::Enumeration::DeviceInformation::CreateFromIdAsync(winrt::param::hstring const &,winrt::param::async_iterable<winrt::hstring> const &,winrt::Windows::Devices::Enumeration::DeviceInformationKind const &)'::`2'::_lambda_1_::operator()(winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2 const &)
0x14001890d  nop
0x14001890e  lock dec cs:qword_1400969F8
0x140018916  jmp     short loc_14001892E
0x140018918  lock dec cs:qword_1400969F8
0x140018920  lea     r8, [rbp+57h+var_88]
0x140018924  lea     rdx, [rbp+57h+arg_18]
0x140018928  call    ??$call@AEAV_lambda_1_@?1??CreateFromIdAsync@DeviceInformation@Enumeration@Devices@Windows@winrt@@SA@AEBUhstring@param@7@AEBU?$async_iterable@Uhstring@winrt@@@97@AEBW4DeviceInformationKind@4567@@Z@@?$factory_cache_entry@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateFromIdAsync@DeviceInformation@Enumeration@Devices@Windows@2@SA@AEBUhstring@param@2@AEBU?$async_iterable@Uhstring@winrt@@@param@2@AEBW4DeviceInformationKind@6782@@Z@@Z
0x14001892d  nop
0x14001892e  lea     rdx, [rbp+57h+var_90]
0x140018932  lea     rcx, [rbp+57h+arg_18]
0x140018936  call    ?get@?$consume_Windows_Foundation_IAsyncOperation@U?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@UDeviceInformation@Enumeration@Devices@34@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Devices::Enumeration::DeviceInformation>,winrt::Windows::Devices::Enumeration::DeviceInformation>::get(void)
0x14001893b  nop
0x14001893c  cmp     [rbp+57h+arg_18], r12
0x140018940  jz      short loc_14001894C
0x140018942  lea     rcx, [rbp+57h+arg_18]
0x140018946  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x14001894b  nop
0x14001894c  cmp     [rbp+57h+var_40], r12b
0x140018950  jnz     short loc_14001895B
0x140018952  mov     rax, r12
0x140018955  mov     [rbp+57h+var_48], rax
0x140018959  jmp     short loc_14001895F
0x14001895b  mov     rax, [rbp+57h+var_48]
0x14001895f  test    rax, rax
0x140018962  jz      short loc_14001896D
0x140018964  lea     rcx, [rbp+57h+var_48]
0x140018968  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x14001896d  lea     rdx, [rbp+57h+arg_18]
0x140018971  lea     rcx, [rbp+57h+var_90]
0x140018975  call    ?Properties@?$consume_Windows_Devices_Enumeration_IDeviceInformation@UIDeviceInformation@Enumeration@Devices@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Properties(void)
0x14001897a  nop
0x14001897b  mov     dword ptr [rbp+57h+var_88+8], esi
0x14001897e  mov     dword ptr [rbp+57h+var_88+0Ch], r14d
0x140018982  mov     [rbp+57h+var_70], r13
0x140018986  lea     rcx, [rbp+57h+var_88+8]
0x14001898a  mov     qword ptr [rbp+57h+var_88], rcx
0x14001898e  lea     r8, [rbp+57h+var_88]
0x140018992  lea     rdx, [rbp+57h+var_A0]
0x140018996  mov     rcx, rax
0x140018999  call    ?Lookup@?$consume_Windows_Foundation_Collections_IMapView@U?$IMapView@Uhstring@winrt@@UIInspectable@Foundation@Windows@2@@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMapView<winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Windows::Foundation::IInspectable>,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(winrt::param::hstring const &)
0x14001899e  nop
0x14001899f  cmp     [rbp+57h+arg_18], r12
0x1400189a3  jz      short loc_1400189AE
0x1400189a5  lea     rcx, [rbp+57h+arg_18]
0x1400189a9  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1400189ae  cmp     [rbp+57h+var_A0], r12
0x1400189b2  jz      short loc_1400189C5
0x1400189b4  lea     rcx, [rbp+57h+var_A0]
0x1400189b8  call    ??$unbox_value@E@winrt@@YAEAEBUIInspectable@Foundation@Windows@0@@Z; winrt::unbox_value<uchar>(winrt::Windows::Foundation::IInspectable const &)
0x1400189bd  cmp     al, sil
0x1400189c0  jnz     short loc_1400189C5
0x1400189c2  mov     [r15], sil
0x1400189c5  cmp     [rbp+57h+var_A0], r12
0x1400189c9  jz      short loc_1400189D5
0x1400189cb  lea     rcx, [rbp+57h+var_A0]
0x1400189cf  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1400189d4  nop
0x1400189d5  cmp     [rbp+57h+var_90], r12
0x1400189d9  jz      short loc_1400189E5
0x1400189db  lea     rcx, [rbp+57h+var_90]
0x1400189df  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1400189e4  nop
0x1400189e5  cmp     [rbp+57h+var_98], r12
0x1400189e9  jz      short loc_1400189F4
0x1400189eb  lea     rcx, [rbp+57h+var_98]
0x1400189ef  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1400189f4  lea     r13, aGetendpointreq; "GetEndpointRequiresOutboundProtocolDown"...
0x1400189fb  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x140018a00  mov     rcx, [rax+8]
0x140018a04  mov     eax, [rcx]
0x140018a06  cmp     eax, 4
0x140018a09  jbe     short loc_140018A6B
0x140018a0b  movzx   eax, byte ptr [r15]
0x140018a0f  mov     [rbp+57h+arg_10], eax
0x140018a12  cmp     qword ptr [rdi], 7
0x140018a16  jbe     short loc_140018A1B
0x140018a18  mov     rbx, [rbx]
0x140018a1b  mov     [rbp+57h+arg_18], rbx
0x140018a1f  lea     rax, aExit; "Exit"
0x140018a26  mov     [rbp+57h+var_90], rax
0x140018a2a  mov     [rbp+57h+var_98], r12
0x140018a2e  mov     [rbp+57h+var_A0], r13
0x140018a32  lea     rax, [rbp+57h+arg_10]
0x140018a36  mov     [rsp+0F0h+var_B0], rax
0x140018a3b  lea     rax, [rbp+57h+arg_18]
0x140018a3f  mov     [rsp+0F0h+var_B8], rax
0x140018a44  lea     rax, [rbp+57h+var_90]
0x140018a48  mov     [rsp+0F0h+var_C0], rax
0x140018a4d  lea     rax, [rbp+57h+var_98]
0x140018a51  mov     [rsp+0F0h+var_C8], rax
0x140018a56  lea     rax, [rbp+57h+var_A0]
0x140018a5a  mov     [rsp+0F0h+var_D0], rax
0x140018a5f  lea     rdx, byte_14008840F
0x140018a66  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x140018a6b  xor     eax, eax
0x140018a6d  mov     rbx, [rsp+0F0h+arg_0]
0x140018a75  add     rsp, 0C0h
0x140018a7c  pop     r15
0x140018a7e  pop     r14
0x140018a80  pop     r13
0x140018a82  pop     r12
0x140018a84  pop     rdi
0x140018a85  pop     rsi
0x140018a86  pop     rbp
0x140018a87  retn
```
