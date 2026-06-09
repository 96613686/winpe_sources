# GetEndpointGenerateIncomingTimestamp(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,bool &,__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0002 &)

- ea: `0x140017f94`
- end: `0x1400182cd`
- name: `?GetEndpointGenerateIncomingTimestamp@@YAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEA_NAEAW4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0002@@@Z`
- size: `825`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `17`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400152d0`

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
- `0x14001386c`
- `0x1400140c4`
- `0x140014688`
- `0x140014f04`
- `0x140017f94`
- `0x14001bd28`
- `0x14001c390`
- `0x14001ecb4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1400180d6`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1400180d6`

## string_xrefs

- `0x140017fdb`: `GetEndpointGenerateIncomingTimestamp`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall GetEndpointGenerateIncomingTimestamp(_QWORD *a1, char *a2, _DWORD *a3)
{
  _DWORD *v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  _QWORD *v9; // rax
  char v10; // di
  __int64 v11; // rdx
  __int64 *v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  _DWORD *v16; // rcx
  __int64 v17; // r8
  __int64 v18; // r9
  _QWORD *v19; // rax
  const char *v21; // [rsp+50h] [rbp-59h] BYREF
  int v22; // [rsp+58h] [rbp-51h] BYREF
  __int64 v23; // [rsp+60h] [rbp-49h] BYREF
  const wchar_t *v24; // [rsp+68h] [rbp-41h] BYREF
  _QWORD *v25; // [rsp+70h] [rbp-39h] BYREF
  __int128 v26; // [rsp+78h] [rbp-31h] BYREF
  int *v27; // [rsp+88h] [rbp-21h]
  const wchar_t *v28; // [rsp+90h] [rbp-19h]
  int *v29; // [rsp+98h] [rbp-11h] BYREF
  int v30; // [rsp+A0h] [rbp-9h] BYREF
  int v31; // [rsp+A4h] [rbp-5h]
  const wchar_t *v32; // [rsp+B0h] [rbp+7h]
  __int64 v33; // [rsp+B8h] [rbp+Fh] BYREF
  char v34; // [rsp+C0h] [rbp+17h]
  __int64 *v35; // [rsp+C8h] [rbp+1Fh]
  _QWORD *v36; // [rsp+D0h] [rbp+27h]

  v36 = a1;
  v6 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v6 > 4u )
  {
    if ( a1[3] <= 7u )
      v9 = a1;
    else
      v9 = (_QWORD *)*a1;
    v25 = v9;
    v24 = L"Enter";
    v23 = 0;
    v21 = "GetEndpointGenerateIncomingTimestamp";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (__int64)v6,
      (__int64)word_140087762,
      v7,
      v8,
      &v21,
      (__int64)&v23,
      &v24,
      &v25);
  }
  if ( (*a3 & 0xFFFFFFFD) != 0 )
  {
    *a2 = 0;
  }
  else
  {
    v26 = 0;
    v27 = 0;
    winrt::single_threaded_vector<winrt::hstring,std::allocator<winrt::hstring>>(&v24, (__int64 *)&v26);
    std::vector<winrt::hstring>::~vector<winrt::hstring>((__int64)&v26);
    v10 = 1;
    v30 = 1;
    v31 = 41;
    v32 = L"{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} 10";
    v29 = &v30;
    winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::Append(
      &v24,
      &v29);
    v22 = 1;
    winrt::param::async_iterable<winrt::hstring>::async_iterable<winrt::hstring>(&v33, &v24);
    v11 = a1[2];
    if ( a1[3] <= 7u )
      v12 = a1;
    else
      v12 = (__int64 *)*a1;
    if ( (_DWORD)v11 )
    {
      if ( *((_WORD *)v12 + (unsigned int)v11) )
        abort();
      v30 = 1;
      v31 = v11;
      v32 = (const wchar_t *)v12;
      v29 = &v30;
    }
    else
    {
      v29 = 0;
    }
    *(_QWORD *)&v26 = &v29;
    *((_QWORD *)&v26 + 1) = &v33;
    v27 = &v22;
    v35 = &qword_1400969F8;
    _InterlockedAdd64(&qword_1400969F8, 1u);
    if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2> )
    {
      `winrt::Windows::Devices::Enumeration::DeviceInformation::CreateFromIdAsync'::`2'::_lambda_1_::operator()(
        (__int64)&v26,
        &v21,
        (__int64 **)&winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>);
      _InterlockedDecrement64(&qword_1400969F8);
    }
    else
    {
      _InterlockedDecrement64(&qword_1400969F8);
      ___call_AEAV_lambda_1___1__CreateFromIdAsync_DeviceInformation_Enumeration_Devices_Windows_winrt__SA_AEBUhstring_param_7_AEBU__async_iterable_Uhstring_winrt___97_AEBW4DeviceInformationKind_4567__Z____factory_cache_entry_UDeviceInformation_Enumeration_Devices_Windows_winrt__UIDeviceInformationStatics2_2345__impl_winrt__QEAA_A_PAEAV_lambda_1___1__CreateFromIdAsync_DeviceInformation_Enumeration_Devices_Windows_2_SA_AEBUhstring_param_2_AEBU__async_iterable_Uhstring_winrt___param_2_AEBW4DeviceInformationKind_6782__Z__Z(
        v12,
        (__int64)&v21,
        (__int64)&v26);
    }
    winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Devices::Enumeration::DeviceInformation>,winrt::Windows::Devices::Enumeration::DeviceInformation>::get(
      &v21,
      &v25);
    if ( v21 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v21);
    if ( v34 )
    {
      v13 = v33;
    }
    else
    {
      v13 = 0;
      v33 = 0;
    }
    if ( v13 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v33);
    v14 = winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Properties(
            &v25,
            &v21);
    *((_QWORD *)&v26 + 1) = 0x2900000001LL;
    v28 = L"{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} 10";
    *(_QWORD *)&v26 = (char *)&v26 + 8;
    winrt::impl::consume_Windows_Foundation_Collections_IMapView<winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Windows::Foundation::IInspectable>,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(
      v14,
      &v23,
      &v26);
    if ( v21 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v21);
    v15 = v23;
    if ( v23 )
    {
      v10 = winrt::unbox_value<bool>(&v23);
      v15 = v23;
    }
    *a2 = v10;
    if ( v15 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v23);
    if ( v25 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v25);
    if ( v24 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v24);
  }
  v16 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v16 > 4u )
  {
    v22 = (unsigned __int8)*a2;
    if ( a1[3] <= 7u )
      v19 = a1;
    else
      v19 = (_QWORD *)*a1;
    v25 = v19;
    v24 = L"Exit";
    v23 = 0;
    v21 = "GetEndpointGenerateIncomingTimestamp";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      (__int64)v16,
      (__int64)word_1400882AA,
      v17,
      v18,
      &v21,
      (__int64)&v23,
      &v24,
      &v25);
  }
  std::wstring::~wstring((char **)a1);
  return 0;
}

```

## disassembly

```asm
0x140017f94  mov     [rsp-8+arg_10], rbx
0x140017f99  mov     [rsp-8+arg_18], rsi
0x140017f9e  push    rbp
0x140017f9f  push    rdi
0x140017fa0  push    r12
0x140017fa2  push    r13
0x140017fa4  push    r14
0x140017fa6  lea     rbp, [rsp-37h]
0x140017fab  sub     rsp, 0E0h
0x140017fb2  mov     rax, cs:__security_cookie
0x140017fb9  xor     rax, rsp
0x140017fbc  mov     [rbp+57h+var_28], rax
0x140017fc0  mov     rdi, r8
0x140017fc3  mov     rsi, rdx
0x140017fc6  mov     rbx, rcx
0x140017fc9  mov     [rbp+57h+var_30], rcx
0x140017fcd  xor     r14d, r14d
0x140017fd0  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x140017fd5  mov     rcx, [rax+8]
0x140017fd9  mov     eax, [rcx]
0x140017fdb  lea     r13, aGetendpointgen; "GetEndpointGenerateIncomingTimestamp"
0x140017fe2  cmp     eax, 4
0x140017fe5  jbe     short loc_14001803D
0x140017fe7  cmp     qword ptr [rbx+18h], 7
0x140017fec  jbe     short loc_140017FF3
0x140017fee  mov     rax, [rbx]
0x140017ff1  jmp     short loc_140017FF6
0x140017ff3  mov     rax, rbx
0x140017ff6  mov     [rbp+57h+var_90], rax
0x140017ffa  lea     rax, aEnter; "Enter"
0x140018001  mov     [rbp+57h+var_98], rax
0x140018005  mov     [rbp+57h+var_A0], r14
0x140018009  mov     [rbp+57h+var_B0], r13
0x14001800d  lea     rax, [rbp+57h+var_90]
0x140018011  mov     [rsp+100h+var_C8], rax
0x140018016  lea     rax, [rbp+57h+var_98]
0x14001801a  mov     [rsp+100h+var_D0], rax
0x14001801f  lea     rax, [rbp+57h+var_A0]
0x140018023  mov     [rsp+100h+var_D8], rax
0x140018028  lea     rax, [rbp+57h+var_B0]
0x14001802c  mov     [rsp+100h+var_E0], rax
0x140018031  lea     rdx, word_140087762
0x140018038  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x14001803d  test    dword ptr [rdi], 0FFFFFFFDh
0x140018043  jz      short loc_14001804D
0x140018045  mov     [rsi], r14b
0x140018048  jmp     loc_140018225
0x14001804d  xorps   xmm0, xmm0
0x140018050  movdqu  [rbp+57h+var_88], xmm0
0x140018055  mov     [rbp+57h+var_78], r14
0x140018059  lea     rdx, [rbp+57h+var_88]
0x14001805d  lea     rcx, [rbp+57h+var_98]
0x140018061  call    ??$single_threaded_vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@winrt@@YA?AU?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@0@$$QEAV?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@@Z; winrt::single_threaded_vector<winrt::hstring,std::allocator<winrt::hstring>>(std::vector<winrt::hstring> &&)
0x140018066  nop
0x140018067  lea     rcx, [rbp+57h+var_88]
0x14001806b  call    ??1?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@QEAA@XZ; std::vector<winrt::hstring>::~vector<winrt::hstring>(void)
0x140018070  mov     edi, 1
0x140018075  mov     [rbp+57h+var_60], edi
0x140018078  mov     [rbp+57h+var_5C], 29h ; ')'
0x14001807f  lea     r12, a3f114a6a11fa4b_13; "{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} "...
0x140018086  mov     [rbp+57h+var_50], r12
0x14001808a  lea     rax, [rbp+57h+var_60]
0x14001808e  mov     [rbp+57h+var_68], rax
0x140018092  lea     rdx, [rbp+57h+var_68]
0x140018096  lea     rcx, [rbp+57h+var_98]
0x14001809a  call    ?Append@?$consume_Windows_Foundation_Collections_IVector@U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@winrt@@Uhstring@5@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::Append(winrt::param::hstring const &)
0x14001809f  mov     [rbp+57h+var_A8], edi
0x1400180a2  lea     rdx, [rbp+57h+var_98]
0x1400180a6  lea     rcx, [rbp+57h+var_48]
0x1400180aa  call    ??$?0U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@winrt@@$0A@@?$async_iterable@Uhstring@winrt@@@param@winrt@@QEAA@AEBU?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@2@@Z; winrt::param::async_iterable<winrt::hstring>::async_iterable<winrt::hstring>(winrt::Windows::Foundation::Collections::IVector<winrt::hstring> const &)
0x1400180af  nop
0x1400180b0  mov     rdx, [rbx+10h]
0x1400180b4  cmp     qword ptr [rbx+18h], 7
0x1400180b9  jbe     short loc_1400180C0
0x1400180bb  mov     rcx, [rbx]
0x1400180be  jmp     short loc_1400180C3
0x1400180c0  mov     rcx, rbx
0x1400180c3  test    edx, edx
0x1400180c5  jnz     short loc_1400180CD
0x1400180c7  mov     [rbp+57h+var_68], r14
0x1400180cb  jmp     short loc_1400180EF
0x1400180cd  mov     eax, edx
0x1400180cf  cmp     [rcx+rax*2], r14w
0x1400180d4  jz      short loc_1400180DD
0x1400180d6  call    cs:__imp_abort
0x1400180dd  mov     [rbp+57h+var_60], edi
0x1400180e0  mov     [rbp+57h+var_5C], edx
0x1400180e3  mov     [rbp+57h+var_50], rcx
0x1400180e7  lea     rax, [rbp+57h+var_60]
0x1400180eb  mov     [rbp+57h+var_68], rax
0x1400180ef  lea     rax, [rbp+57h+var_68]
0x1400180f3  mov     qword ptr [rbp+57h+var_88], rax
0x1400180f7  lea     rax, [rbp+57h+var_48]
0x1400180fb  mov     qword ptr [rbp+57h+var_88+8], rax
0x1400180ff  lea     rax, [rbp+57h+var_A8]
0x140018103  mov     [rbp+57h+var_78], rax
0x140018107  lea     rax, qword_1400969F8
0x14001810e  mov     [rbp+57h+var_38], rax
0x140018112  lock add cs:qword_1400969F8, rdi
0x14001811a  cmp     cs:??$factory_cache_entry_v@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@impl@winrt@@3U?$factory_cache_entry@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@12@A, r14; factory_cache_entry<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>::winrt::factory_cache_entry<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2> winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>
0x140018121  jz      short loc_140018142
0x140018123  lea     r8, ??$factory_cache_entry_v@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@impl@winrt@@3U?$factory_cache_entry@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@12@A; factory_cache_entry<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>::winrt::factory_cache_entry<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2> winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>
0x14001812a  lea     rdx, [rbp+57h+var_B0]
0x14001812e  lea     rcx, [rbp+57h+var_88]
0x140018132  call    ??R_lambda_1_@?1??CreateFromIdAsync@DeviceInformation@Enumeration@Devices@Windows@winrt@@SA@AEBUhstring@param@6@AEBU?$async_iterable@Uhstring@winrt@@@86@AEBW4DeviceInformationKind@3456@@Z@QEBA@AEBUIDeviceInformationStatics2@3456@@Z; `winrt::Windows::Devices::Enumeration::DeviceInformation::CreateFromIdAsync(winrt::param::hstring const &,winrt::param::async_iterable<winrt::hstring> const &,winrt::Windows::Devices::Enumeration::DeviceInformationKind const &)'::`2'::_lambda_1_::operator()(winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2 const &)
0x140018137  nop
0x140018138  lock dec cs:qword_1400969F8
0x140018140  jmp     short loc_140018158
0x140018142  lock dec cs:qword_1400969F8
0x14001814a  lea     r8, [rbp+57h+var_88]
0x14001814e  lea     rdx, [rbp+57h+var_B0]
0x140018152  call    ??$call@AEAV_lambda_1_@?1??CreateFromIdAsync@DeviceInformation@Enumeration@Devices@Windows@winrt@@SA@AEBUhstring@param@7@AEBU?$async_iterable@Uhstring@winrt@@@97@AEBW4DeviceInformationKind@4567@@Z@@?$factory_cache_entry@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateFromIdAsync@DeviceInformation@Enumeration@Devices@Windows@2@SA@AEBUhstring@param@2@AEBU?$async_iterable@Uhstring@winrt@@@param@2@AEBW4DeviceInformationKind@6782@@Z@@Z
0x140018157  nop
0x140018158  lea     rdx, [rbp+57h+var_90]
0x14001815c  lea     rcx, [rbp+57h+var_B0]
0x140018160  call    ?get@?$consume_Windows_Foundation_IAsyncOperation@U?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@UDeviceInformation@Enumeration@Devices@34@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Devices::Enumeration::DeviceInformation>,winrt::Windows::Devices::Enumeration::DeviceInformation>::get(void)
0x140018165  nop
0x140018166  cmp     [rbp+57h+var_B0], r14
0x14001816a  jz      short loc_140018176
0x14001816c  lea     rcx, [rbp+57h+var_B0]
0x140018170  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x140018175  nop
0x140018176  cmp     [rbp+57h+var_40], r14b
0x14001817a  jnz     short loc_140018185
0x14001817c  mov     rax, r14
0x14001817f  mov     [rbp+57h+var_48], rax
0x140018183  jmp     short loc_140018189
0x140018185  mov     rax, [rbp+57h+var_48]
0x140018189  test    rax, rax
0x14001818c  jz      short loc_140018197
0x14001818e  lea     rcx, [rbp+57h+var_48]
0x140018192  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x140018197  lea     rdx, [rbp+57h+var_B0]
0x14001819b  lea     rcx, [rbp+57h+var_90]
0x14001819f  call    ?Properties@?$consume_Windows_Devices_Enumeration_IDeviceInformation@UIDeviceInformation@Enumeration@Devices@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Properties(void)
0x1400181a4  nop
0x1400181a5  mov     dword ptr [rbp+57h+var_88+8], edi
0x1400181a8  mov     dword ptr [rbp+57h+var_88+0Ch], 29h ; ')'
0x1400181af  mov     [rbp+57h+var_70], r12
0x1400181b3  lea     rcx, [rbp+57h+var_88+8]
0x1400181b7  mov     qword ptr [rbp+57h+var_88], rcx
0x1400181bb  lea     r8, [rbp+57h+var_88]
0x1400181bf  lea     rdx, [rbp+57h+var_A0]
0x1400181c3  mov     rcx, rax
0x1400181c6  call    ?Lookup@?$consume_Windows_Foundation_Collections_IMapView@U?$IMapView@Uhstring@winrt@@UIInspectable@Foundation@Windows@2@@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMapView<winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Windows::Foundation::IInspectable>,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(winrt::param::hstring const &)
0x1400181cb  nop
0x1400181cc  cmp     [rbp+57h+var_B0], r14
0x1400181d0  jz      short loc_1400181DB
0x1400181d2  lea     rcx, [rbp+57h+var_B0]
0x1400181d6  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1400181db  mov     rax, [rbp+57h+var_A0]
0x1400181df  test    rax, rax
0x1400181e2  jz      short loc_1400181F4
0x1400181e4  lea     rcx, [rbp+57h+var_A0]
0x1400181e8  call    ??$unbox_value@_N@winrt@@YA_NAEBUIInspectable@Foundation@Windows@0@@Z; winrt::unbox_value<bool>(winrt::Windows::Foundation::IInspectable const &)
0x1400181ed  mov     dil, al
0x1400181f0  mov     rax, [rbp+57h+var_A0]
0x1400181f4  mov     [rsi], dil
0x1400181f7  test    rax, rax
0x1400181fa  jz      short loc_140018206
0x1400181fc  lea     rcx, [rbp+57h+var_A0]
0x140018200  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x140018205  nop
0x140018206  cmp     [rbp+57h+var_90], r14
0x14001820a  jz      short loc_140018216
0x14001820c  lea     rcx, [rbp+57h+var_90]
0x140018210  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x140018215  nop
0x140018216  cmp     [rbp+57h+var_98], r14
0x14001821a  jz      short loc_140018225
0x14001821c  lea     rcx, [rbp+57h+var_98]
0x140018220  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x140018225  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14001822a  mov     rcx, [rax+8]
0x14001822e  mov     eax, [rcx]
0x140018230  cmp     eax, 4
0x140018233  jbe     short loc_14001829B
0x140018235  movzx   eax, byte ptr [rsi]
0x140018238  mov     [rbp+57h+var_A8], eax
0x14001823b  cmp     qword ptr [rbx+18h], 7
0x140018240  jbe     short loc_140018247
0x140018242  mov     rax, [rbx]
0x140018245  jmp     short loc_14001824A
0x140018247  mov     rax, rbx
0x14001824a  mov     [rbp+57h+var_90], rax
0x14001824e  lea     rax, aExit; "Exit"
0x140018255  mov     [rbp+57h+var_98], rax
0x140018259  mov     [rbp+57h+var_A0], r14
0x14001825d  mov     [rbp+57h+var_B0], r13
0x140018261  lea     rax, [rbp+57h+var_A8]
0x140018265  mov     [rsp+100h+var_C0], rax
0x14001826a  lea     rax, [rbp+57h+var_90]
0x14001826e  mov     [rsp+100h+var_C8], rax
0x140018273  lea     rax, [rbp+57h+var_98]
0x140018277  mov     [rsp+100h+var_D0], rax
0x14001827c  lea     rax, [rbp+57h+var_A0]
0x140018280  mov     [rsp+100h+var_D8], rax
0x140018285  lea     rax, [rbp+57h+var_B0]
0x140018289  mov     [rsp+100h+var_E0], rax
0x14001828e  lea     rdx, word_1400882AA
0x140018295  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x14001829a  nop
0x14001829b  mov     rcx, rbx; void *
0x14001829e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400182a3  xor     eax, eax
0x1400182a5  mov     rcx, [rbp+57h+var_28]
0x1400182a9  xor     rcx, rsp; StackCookie
0x1400182ac  call    __security_check_cookie
0x1400182b1  lea     r11, [rsp+100h+var_20]
0x1400182b9  mov     rbx, [r11+40h]
0x1400182bd  mov     rsi, [r11+48h]
0x1400182c1  mov     rsp, r11
0x1400182c4  pop     r14
0x1400182c6  pop     r13
0x1400182c8  pop     r12
0x1400182ca  pop     rdi
0x1400182cb  pop     rbp
0x1400182cc  retn
```
