# CMidi2KSAggregateMidiEndpointManager::OnDeviceUpdated(winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformationUpdate)

- ea: `0x180027f90`
- end: `0x1800284ad`
- name: `?OnDeviceUpdated@CMidi2KSAggregateMidiEndpointManager@@AEAAJUDeviceWatcher@Enumeration@Devices@Windows@winrt@@UDeviceInformationUpdate@3456@@Z`
- size: `1309`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180001a94`
- `0x180005020`
- `0x180005f2c`
- `0x180005fa4`
- `0x18000d430`
- `0x180010b94`
- `0x1800117d8`
- `0x180013118`
- `0x180014ff4`
- `0x18001a4a8`
- `0x18001fab0`
- `0x1800254f8`
- `0x180027f90`
- `0x180028bac`
- `0x18005e010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002811f`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800283e8`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002811f`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800283e8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180028322`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180028322`

## string_xrefs

- `0x18002805b`: `Device properties updated`
- `0x18002806b`: `CMidi2KSAggregateMidiEndpointManager::OnDeviceUpdated`
- `0x1800282f3`: `KSA Updated Property with Key: `

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall CMidi2KSAggregateMidiEndpointManager::OnDeviceUpdated(__int64 a1, _QWORD *a2, _QWORD *a3)
{
  _DWORD *v6; // rbx
  __int64 *v7; // rax
  __int64 v8; // rcx
  int v9; // eax
  __int64 v10; // rax
  int v11; // r8d
  int v12; // r9d
  const wchar_t *v13; // rax
  void *v14; // rbx
  int v15; // eax
  HANDLE ProcessHeap; // rax
  const wchar_t *v17; // r15
  int v18; // eax
  LPVOID v19; // rcx
  int v20; // eax
  const char *v21; // rdi
  int v22; // eax
  const char *v23; // rbx
  unsigned int v24; // esi
  int v25; // esi
  int v26; // eax
  unsigned int v27; // esi
  int v28; // eax
  const wchar_t *v29; // rdx
  __int64 v30; // r8
  __int64 v31; // rax
  void *v32; // rdi
  int v33; // eax
  HANDLE v34; // rax
  int v35; // eax
  char v37[8]; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID lpMem; // [rsp+58h] [rbp-A8h] BYREF
  const char *v39; // [rsp+60h] [rbp-A0h] BYREF
  const wchar_t *v40; // [rsp+68h] [rbp-98h] BYREF
  int v41; // [rsp+70h] [rbp-90h] BYREF
  const char *v42; // [rsp+78h] [rbp-88h]
  __int64 v43; // [rsp+80h] [rbp-80h]
  const char *v44; // [rsp+88h] [rbp-78h] BYREF
  const char *v45; // [rsp+90h] [rbp-70h] BYREF
  const wchar_t *v46; // [rsp+98h] [rbp-68h] BYREF
  _QWORD v47[3]; // [rsp+A0h] [rbp-60h] BYREF
  _OWORD v48[2]; // [rsp+B8h] [rbp-48h] BYREF
  _OWORD v49[2]; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v50[32]; // [rsp+F8h] [rbp-8h] BYREF

  v47[1] = a2;
  v47[2] = a3;
  LODWORD(v40) = 0;
  v6 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
  if ( *v6 > 4u )
  {
    v7 = (__int64 *)winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformationUpdate<winrt::Windows::Devices::Enumeration::IDeviceInformationUpdate>::Properties(
                      a3,
                      &v39);
    LODWORD(v40) = 0;
    v8 = *v7;
    v41 = 208;
    v42 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Foundation.Collections.h";
    v43 = 0;
    v9 = (*(__int64 (__fastcall **)(__int64, const wchar_t **))(*(_QWORD *)v8 + 56LL))(v8, &v40);
    if ( v9 < 0 )
      winrt::throw_hresult((unsigned int)v9, &v41);
    LODWORD(v44) = (_DWORD)v40;
    v10 = winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformationUpdate<winrt::Windows::Devices::Enumeration::IDeviceInformationUpdate>::Id(
            a3,
            &lpMem);
    if ( *(_QWORD *)v10 )
      v13 = *(const wchar_t **)(*(_QWORD *)v10 + 16LL);
    else
      v13 = &S1;
    v46 = v13;
    v40 = L"Device properties updated";
    v47[0] = a1;
    v45 = "CMidi2KSAggregateMidiEndpointManager::OnDeviceUpdated";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      (_DWORD)v6,
      (unsigned int)byte_180089129,
      v11,
      v12,
      (__int64)&v45,
      (__int64)v47,
      (__int64)&v40,
      (__int64)&v46,
      (__int64)&v44);
    v14 = lpMem;
    if ( lpMem )
    {
      v15 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
      if ( v15 )
      {
        if ( v15 < 0 )
          abort();
      }
      else
      {
        ProcessHeap = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(ProcessHeap, 0, v14);
      }
      lpMem = 0;
    }
    if ( v39 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v39);
  }
  winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformationUpdate<winrt::Windows::Devices::Enumeration::IDeviceInformationUpdate>::Properties(
    a3,
    &v46);
  v39 = 0;
  v17 = v46;
  lpMem = 0;
  if ( v46 )
  {
    v18 = (**(__int64 (__fastcall ***)(const wchar_t *, __int64 *, LPVOID *))v46)(
            v46,
            winrt::impl::guid_v<winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Foundation::IInspectable>>>,
            &lpMem);
    v19 = lpMem;
  }
  else
  {
    v18 = 0;
    v19 = 0;
  }
  v41 = 21;
  v42 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Foundation.Collections.h";
  v43 = 0;
  if ( v18 < 0 )
    winrt::throw_hresult((unsigned int)v18, &v41);
  v41 = 23;
  v42 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Foundation.Collections.h";
  v43 = 0;
  v20 = (*(__int64 (__fastcall **)(LPVOID, const char **))(*(_QWORD *)v19 + 48LL))(v19, &v39);
  if ( v20 < 0 )
    winrt::throw_hresult((unsigned int)v20, &v41);
  winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&lpMem);
  v21 = v39;
  v45 = v39;
  v37[0] = 0;
  v41 = 64;
  v42 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Foundation.Collections.h";
  v43 = 0;
  v22 = (*(__int64 (__fastcall **)(const char *, char *))(*(_QWORD *)v39 + 56LL))(v39, v37);
  if ( v22 < 0 )
    winrt::throw_hresult((unsigned int)v22, &v41);
  if ( v37[0] )
  {
    v23 = v21;
    v44 = v21;
  }
  else
  {
    v23 = 0;
    v44 = 0;
    if ( v21 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v45);
    v21 = 0;
  }
  v24 = 7;
  v45 = 0;
  while ( !(unsigned __int8)winrt::Windows::Foundation::operator==(&v44, &v45) )
  {
    v39 = 0;
    v25 = v24 | 0x10;
    LODWORD(v40) = v25;
    v41 = 46;
    v42 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Foundation.Collections.h";
    v43 = 0;
    v26 = (*(__int64 (__fastcall **)(const char *, const char **))(*(_QWORD *)v21 + 48LL))(v21, &v39);
    if ( v26 < 0 )
      winrt::throw_hresult((unsigned int)v26, &v41);
    lpMem = 0;
    v27 = v25 & 0xFFFFFFC7 | 0x28;
    LODWORD(v40) = v27;
    v41 = 118;
    v42 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Foundation.Collections.h";
    v43 = 0;
    v28 = (*(__int64 (__fastcall **)(const char *, LPVOID *))(*(_QWORD *)v39 + 48LL))(v39, &lpMem);
    if ( v28 < 0 )
      winrt::throw_hresult((unsigned int)v28, &v41);
    if ( lpMem )
      v29 = (const wchar_t *)*((_QWORD *)lpMem + 2);
    else
      v29 = &S1;
    memset(v49, 0, sizeof(v49));
    v30 = -1;
    do
      ++v30;
    while ( v29[v30] );
    std::wstring::_Construct<1,unsigned short const *>(v49);
    memset(v48, 0, sizeof(v48));
    std::wstring::_Construct<1,unsigned short const *>(v48);
    v31 = std::operator+<unsigned short>(v50, v48, v49);
    if ( *(_QWORD *)(v31 + 24) > 7u )
      v31 = *(_QWORD *)v31;
    OutputDebugStringW((LPCWSTR)v31);
    std::wstring::~wstring(v50);
    std::wstring::~wstring(v48);
    std::wstring::~wstring(v49);
    v24 = v27 & 0xFFFFFFDF;
    v32 = lpMem;
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
        v34 = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(v34, 0, v32);
      }
    }
    if ( v39 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v39);
    v37[0] = 0;
    v21 = v23;
    v41 = 82;
    v42 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Foundation.Collections.h";
    v43 = 0;
    v35 = (*(__int64 (__fastcall **)(const char *, char *))(*(_QWORD *)v23 + 64LL))(v23, v37);
    if ( v35 < 0 )
      winrt::throw_hresult((unsigned int)v35, &v41);
    if ( !v37[0] )
    {
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v44);
      v23 = 0;
      v44 = 0;
      v21 = 0;
    }
  }
  if ( v21 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v44);
  if ( v17 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v46);
  if ( *a2 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a2);
  if ( *a3 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a3);
  return 0;
}

```

## disassembly

```asm
0x180027f90  mov     [rsp-8+arg_0], rbx
0x180027f95  push    rbp
0x180027f96  push    rsi
0x180027f97  push    rdi
0x180027f98  push    r12
0x180027f9a  push    r13
0x180027f9c  push    r14
0x180027f9e  push    r15
0x180027fa0  lea     rbp, [rsp-20h]
0x180027fa5  sub     rsp, 120h
0x180027fac  mov     rax, cs:__security_cookie
0x180027fb3  xor     rax, rsp
0x180027fb6  mov     [rbp+50h+var_38], rax
0x180027fba  mov     r14, r8
0x180027fbd  mov     r12, rdx
0x180027fc0  mov     rdi, rcx
0x180027fc3  mov     [rbp+50h+var_A8], rdx
0x180027fc7  mov     [rbp+50h+var_A0], r8
0x180027fcb  xor     r13d, r13d
0x180027fce  mov     dword ptr [rsp+150h+var_E8], r13d
0x180027fd3  call    ?Instance@MidiKSAggregateTransportTelemetryProvider@@KAPEAV1@XZ; MidiKSAggregateTransportTelemetryProvider::Instance(void)
0x180027fd8  mov     rbx, [rax+8]
0x180027fdc  mov     eax, [rbx]
0x180027fde  lea     rsi, aOnecoreuapInte_0; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x180027fe5  cmp     eax, 4
0x180027fe8  jbe     loc_1800280F3
0x180027fee  lea     rdx, [rsp+150h+var_F0]
0x180027ff3  mov     rcx, r14
0x180027ff6  call    ?Properties@?$consume_Windows_Devices_Enumeration_IDeviceInformationUpdate@UIDeviceInformationUpdate@Enumeration@Devices@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformationUpdate<winrt::Windows::Devices::Enumeration::IDeviceInformationUpdate>::Properties(void)
0x180027ffb  nop
0x180027ffc  mov     dword ptr [rsp+150h+var_E8], r13d
0x180028001  mov     rcx, [rax]
0x180028004  mov     [rsp+150h+var_E0], 0D0h
0x18002800c  mov     [rsp+150h+var_D8], rsi
0x180028011  mov     [rbp+50h+var_D0], r13
0x180028015  mov     rax, [rcx]
0x180028018  lea     rdx, [rsp+150h+var_E8]
0x18002801d  mov     rax, [rax+38h]
0x180028021  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028026  test    eax, eax
0x180028028  js      loc_18002845F
0x18002802e  mov     eax, dword ptr [rsp+150h+var_E8]
0x180028032  mov     dword ptr [rbp+50h+var_C8], eax
0x180028035  lea     rdx, [rsp+150h+lpMem]
0x18002803a  mov     rcx, r14
0x18002803d  call    ?Id@?$consume_Windows_Devices_Enumeration_IDeviceInformationUpdate@UIDeviceInformationUpdate@Enumeration@Devices@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformationUpdate<winrt::Windows::Devices::Enumeration::IDeviceInformationUpdate>::Id(void)
0x180028042  mov     rcx, [rax]
0x180028045  test    rcx, rcx
0x180028048  jz      short loc_180028050
0x18002804a  mov     rax, [rcx+10h]
0x18002804e  jmp     short loc_180028057
0x180028050  lea     rax, S1
0x180028057  mov     [rbp+50h+var_B8], rax
0x18002805b  lea     rax, aDeviceProperti; "Device properties updated"
0x180028062  mov     [rsp+150h+var_E8], rax
0x180028067  mov     [rbp+50h+var_B0], rdi
0x18002806b  lea     rax, aCmidi2ksaggreg_5; "CMidi2KSAggregateMidiEndpointManager::O"...
0x180028072  mov     [rbp+50h+var_C0], rax
0x180028076  lea     rax, [rbp+50h+var_C8]
0x18002807a  mov     [rsp+150h+var_110], rax
0x18002807f  lea     rax, [rbp+50h+var_B8]
0x180028083  mov     [rsp+150h+var_118], rax
0x180028088  lea     rax, [rsp+150h+var_E8]
0x18002808d  mov     [rsp+150h+var_120], rax
0x180028092  lea     rax, [rbp+50h+var_B0]
0x180028096  mov     [rsp+150h+var_128], rax
0x18002809b  lea     rax, [rbp+50h+var_C0]
0x18002809f  mov     [rsp+150h+var_130], rax
0x1800280a4  lea     rdx, byte_180089129
0x1800280ab  mov     rcx, rbx
0x1800280ae  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1800280b3  mov     rbx, [rsp+150h+lpMem]
0x1800280b8  test    rbx, rbx
0x1800280bb  jz      short loc_1800280E2
0x1800280bd  or      eax, 0FFFFFFFFh
0x1800280c0  lock xadd [rbx+18h], eax
0x1800280c5  sub     eax, 1
0x1800280c8  jnz     short loc_18002811B
0x1800280ca  nop
0x1800280cb  call    WINRT_IMPL_GetProcessHeap
0x1800280d0  mov     rcx, rax; hHeap
0x1800280d3  mov     r8, rbx; lpMem
0x1800280d6  xor     edx, edx; dwFlags
0x1800280d8  call    WINRT_IMPL_HeapFree
0x1800280dd  mov     [rsp+150h+lpMem], r13
0x1800280e2  cmp     [rsp+150h+var_F0], r13
0x1800280e7  jz      short loc_1800280F3
0x1800280e9  lea     rcx, [rsp+150h+var_F0]
0x1800280ee  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800280f3  lea     rdx, [rbp+50h+var_B8]
0x1800280f7  mov     rcx, r14
0x1800280fa  call    ?Properties@?$consume_Windows_Devices_Enumeration_IDeviceInformationUpdate@UIDeviceInformationUpdate@Enumeration@Devices@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformationUpdate<winrt::Windows::Devices::Enumeration::IDeviceInformationUpdate>::Properties(void)
0x1800280ff  nop
0x180028100  mov     [rsp+150h+var_F0], r13
0x180028105  mov     r15, [rbp+50h+var_B8]
0x180028109  mov     [rsp+150h+lpMem], r13
0x18002810e  test    r15, r15
0x180028111  jnz     short loc_180028126
0x180028113  mov     eax, r13d
0x180028116  mov     rcx, r13
0x180028119  jmp     short loc_18002814A
0x18002811b  test    eax, eax
0x18002811d  jns     short loc_1800280DD
0x18002811f  call    cs:__imp_abort
0x180028126  mov     rax, [r15]
0x180028129  lea     r8, [rsp+150h+lpMem]
0x18002812e  lea     rdx, ??$guid_v@U?$IIterable@U?$IKeyValuePair@Uhstring@winrt@@UIInspectable@Foundation@Windows@2@@Collections@Foundation@Windows@winrt@@@Collections@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Foundation::IInspectable>>>
0x180028135  mov     rcx, r15
0x180028138  mov     rax, [rax]
0x18002813b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028140  mov     rcx, [rsp+150h+lpMem]
0x180028145  mov     [rsp+150h+lpMem], rcx
0x18002814a  mov     [rsp+150h+var_E0], 15h
0x180028152  mov     [rsp+150h+var_D8], rsi
0x180028157  mov     [rbp+50h+var_D0], r13
0x18002815b  test    eax, eax
0x18002815d  js      loc_18002846C
0x180028163  mov     [rsp+150h+var_E0], 17h
0x18002816b  mov     [rsp+150h+var_D8], rsi
0x180028170  mov     [rbp+50h+var_D0], r13
0x180028174  mov     rax, [rcx]
0x180028177  lea     rdx, [rsp+150h+var_F0]
0x18002817c  mov     rax, [rax+30h]
0x180028180  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028185  test    eax, eax
0x180028187  js      loc_180028479
0x18002818d  lea     rcx, [rsp+150h+lpMem]
0x180028192  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180028197  mov     rdi, [rsp+150h+var_F0]
0x18002819c  mov     [rbp+50h+var_C0], rdi
0x1800281a0  mov     [rsp+150h+var_100], r13b
0x1800281a5  mov     [rsp+150h+var_E0], 40h ; '@'
0x1800281ad  mov     [rsp+150h+var_D8], rsi
0x1800281b2  mov     [rbp+50h+var_D0], r13
0x1800281b6  mov     rax, [rdi]
0x1800281b9  lea     rdx, [rsp+150h+var_100]
0x1800281be  mov     rcx, rdi
0x1800281c1  mov     rax, [rax+38h]
0x1800281c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800281ca  test    eax, eax
0x1800281cc  js      loc_180028486
0x1800281d2  cmp     [rsp+150h+var_100], r13b
0x1800281d7  jnz     short loc_1800281F3
0x1800281d9  mov     rbx, r13
0x1800281dc  mov     [rbp+50h+var_C8], rbx
0x1800281e0  test    rdi, rdi
0x1800281e3  jz      short loc_1800281EE
0x1800281e5  lea     rcx, [rbp+50h+var_C0]
0x1800281e9  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800281ee  mov     rdi, r13
0x1800281f1  jmp     short loc_1800281FA
0x1800281f3  mov     rbx, rdi
0x1800281f6  mov     [rbp+50h+var_C8], rbx
0x1800281fa  mov     esi, 7
0x1800281ff  mov     [rbp+50h+var_C0], r13
0x180028203  lea     rdx, [rbp+50h+var_C0]
0x180028207  lea     rcx, [rbp+50h+var_C8]
0x18002820b  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x180028210  test    al, al
0x180028212  jnz     loc_1800283EF
0x180028218  mov     [rsp+150h+var_F0], r13
0x18002821d  or      esi, 10h
0x180028220  mov     dword ptr [rsp+150h+var_E8], esi
0x180028224  mov     [rsp+150h+var_E0], 2Eh ; '.'
0x18002822c  lea     rax, aOnecoreuapInte_0; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x180028233  mov     [rsp+150h+var_D8], rax
0x180028238  mov     [rbp+50h+var_D0], r13
0x18002823c  mov     rax, [rdi]
0x18002823f  lea     rdx, [rsp+150h+var_F0]
0x180028244  mov     rcx, rdi
0x180028247  mov     rax, [rax+30h]
0x18002824b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028250  test    eax, eax
0x180028252  js      loc_180028452
0x180028258  and     esi, 0FFFFFFEFh
0x18002825b  or      esi, 8
0x18002825e  mov     [rsp+150h+lpMem], r13
0x180028263  or      esi, 20h
0x180028266  mov     dword ptr [rsp+150h+var_E8], esi
0x18002826a  mov     rcx, [rsp+150h+var_F0]
0x18002826f  mov     [rsp+150h+var_E0], 76h ; 'v'
0x180028277  lea     rax, aOnecoreuapInte_0; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x18002827e  mov     [rsp+150h+var_D8], rax
0x180028283  mov     [rbp+50h+var_D0], r13
0x180028287  mov     rax, [rcx]
0x18002828a  lea     rdx, [rsp+150h+lpMem]
0x18002828f  mov     rax, [rax+30h]
0x180028293  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028298  test    eax, eax
0x18002829a  js      loc_1800284A0
0x1800282a0  mov     rax, [rsp+150h+lpMem]
0x1800282a5  test    rax, rax
0x1800282a8  jz      short loc_1800282B0
0x1800282aa  mov     rdx, [rax+10h]
0x1800282ae  jmp     short loc_1800282B7
0x1800282b0  lea     rdx, S1
0x1800282b7  xorps   xmm0, xmm0
0x1800282ba  movups  [rbp+50h+var_78], xmm0
0x1800282be  xorps   xmm1, xmm1
0x1800282c1  movdqu  [rbp+50h+var_68], xmm1
0x1800282c6  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800282ca  inc     r8
0x1800282cd  cmp     [rdx+r8*2], r13w
0x1800282d2  jnz     short loc_1800282CA
0x1800282d4  lea     rcx, [rbp+50h+var_78]
0x1800282d8  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800282dd  nop
0x1800282de  xorps   xmm0, xmm0
0x1800282e1  movups  [rbp+50h+var_98], xmm0
0x1800282e5  xorps   xmm1, xmm1
0x1800282e8  movdqu  [rbp+50h+var_88], xmm1
0x1800282ed  mov     r8d, 1Fh
0x1800282f3  lea     rdx, aKsaUpdatedProp; "KSA Updated Property with Key: "
0x1800282fa  lea     rcx, [rbp+50h+var_98]
0x1800282fe  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180028303  nop
0x180028304  lea     r8, [rbp+50h+var_78]
0x180028308  lea     rdx, [rbp+50h+var_98]
0x18002830c  lea     rcx, [rbp+50h+var_58]
0x180028310  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@0@Z; std::operator+<ushort>(std::wstring &&,std::wstring &&)
0x180028315  cmp     qword ptr [rax+18h], 7
0x18002831a  jbe     short loc_18002831F
0x18002831c  mov     rax, [rax]
0x18002831f  mov     rcx, rax; lpOutputString
0x180028322  call    cs:__imp_OutputDebugStringW
0x180028328  lea     rcx, [rbp+50h+var_58]; void *
0x18002832c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180028331  nop
0x180028332  lea     rcx, [rbp+50h+var_98]; void *
0x180028336  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002833b  nop
0x18002833c  lea     rcx, [rbp+50h+var_78]; void *
0x180028340  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180028345  and     esi, 0FFFFFFDFh
0x180028348  mov     rdi, [rsp+150h+lpMem]
0x18002834d  test    rdi, rdi
0x180028350  jz      short loc_180028378
0x180028352  or      eax, 0FFFFFFFFh
0x180028355  lock xadd [rdi+18h], eax
0x18002835a  sub     eax, 1
0x18002835d  jnz     short loc_180028374
0x18002835f  nop
0x180028360  call    WINRT_IMPL_GetProcessHeap
0x180028365  mov     rcx, rax; hHeap
0x180028368  mov     r8, rdi; lpMem
0x18002836b  xor     edx, edx; dwFlags
0x18002836d  call    WINRT_IMPL_HeapFree
0x180028372  jmp     short loc_180028378
0x180028374  test    eax, eax
0x180028376  js      short loc_1800283E8
0x180028378  cmp     [rsp+150h+var_F0], r13
0x18002837d  jz      short loc_180028389
0x18002837f  lea     rcx, [rsp+150h+var_F0]
0x180028384  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180028389  mov     [rsp+150h+var_100], r13b
0x18002838e  mov     rdi, rbx
0x180028391  mov     [rsp+150h+var_E0], 52h ; 'R'
0x180028399  lea     rax, aOnecoreuapInte_0; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x1800283a0  mov     [rsp+150h+var_D8], rax
0x1800283a5  mov     [rbp+50h+var_D0], r13
0x1800283a9  mov     rax, [rbx]
0x1800283ac  lea     rdx, [rsp+150h+var_100]
0x1800283b1  mov     rcx, rbx
0x1800283b4  mov     rax, [rax+40h]
0x1800283b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800283bd  test    eax, eax
0x1800283bf  js      loc_180028493
0x1800283c5  cmp     [rsp+150h+var_100], r13b
0x1800283ca  jnz     loc_180028203
0x1800283d0  lea     rcx, [rbp+50h+var_C8]
0x1800283d4  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800283d9  mov     rbx, r13
0x1800283dc  mov     [rbp+50h+var_C8], rbx
0x1800283e0  mov     rdi, r13
0x1800283e3  jmp     loc_180028203
0x1800283e8  call    cs:__imp_abort
0x1800283ef  test    rdi, rdi
0x1800283f2  jz      short loc_1800283FE
0x1800283f4  lea     rcx, [rbp+50h+var_C8]
0x1800283f8  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800283fd  nop
0x1800283fe  test    r15, r15
0x180028401  jz      short loc_18002840D
0x180028403  lea     rcx, [rbp+50h+var_B8]
0x180028407  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18002840c  nop
0x18002840d  cmp     [r12], r13
0x180028411  jz      short loc_18002841C
0x180028413  mov     rcx, r12
0x180028416  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18002841b  nop
0x18002841c  cmp     [r14], r13
0x18002841f  jz      short loc_180028429
0x180028421  mov     rcx, r14
0x180028424  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180028429  xor     eax, eax
0x18002842b  mov     rcx, [rbp+50h+var_38]
0x18002842f  xor     rcx, rsp; StackCookie
0x180028432  call    __security_check_cookie
0x180028437  mov     rbx, [rsp+150h+arg_0]
  ... truncated ...
```
