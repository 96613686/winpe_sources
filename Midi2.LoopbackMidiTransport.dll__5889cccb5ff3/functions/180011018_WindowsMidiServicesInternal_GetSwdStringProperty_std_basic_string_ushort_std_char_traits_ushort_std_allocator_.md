# WindowsMidiServicesInternal::GetSwdStringProperty(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x180011018`
- end: `0x1800114ba`
- name: `?GetSwdStringProperty@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@00@Z`
- size: `1186`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `20`
- tags: `service_task, broker_com_uri`

## callers

- `0x180011980`

## callees

- `0x180004180`
- `0x18000509c`
- `0x180005108`
- `0x18000b740`
- `0x18000de70`
- `0x18000e178`
- `0x18000e920`
- `0x18000ed4c`
- `0x18000ee84`
- `0x18000f82c`
- `0x18000fc58`
- `0x1800100a8`
- `0x180011018`
- `0x1800120b8`
- `0x1800122f0`
- `0x1800139ac`
- `0x180013b14`
- `0x1800145d8`
- `0x180014974`
- `0x180032010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180011148`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001126a`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180011275`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800113c9`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800113d4`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800114a6`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180011148`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001126a`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180011275`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800113c9`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800113d4`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800114a6`

## pseudocode

```c
// Hidden C++ exception states: #wind=23
winrt::impl *__fastcall WindowsMidiServicesInternal::GetSwdStringProperty(
        winrt::impl *a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        void *a4)
{
  const unsigned __int16 *v7; // rdx
  volatile signed __int32 *v8; // rdi
  struct winrt::impl::hstring_header *v9; // rdx
  volatile signed __int32 *v10; // rbx
  int v11; // eax
  HANDLE ProcessHeap; // rax
  int v13; // eax
  const unsigned __int16 *v14; // rdx
  volatile signed __int32 *v15; // rdi
  struct winrt::impl::hstring_header *v16; // rdx
  __int64 v17; // rcx
  volatile signed __int32 *v18; // r15
  int v19; // eax
  HANDLE v20; // rax
  int v21; // eax
  HANDLE v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  const wchar_t *v26; // rdx
  __int64 v27; // r8
  void *v28; // rdi
  int v29; // eax
  HANDLE v30; // rax
  int v31; // esi
  HANDLE v32; // rax
  void *v33; // rcx
  _OWORD *v34; // rdi
  int v35; // esi
  HANDLE v36; // rax
  __int64 v38; // [rsp+20h] [rbp-B9h] BYREF
  __int64 v39; // [rsp+28h] [rbp-B1h] BYREF
  __int64 v40; // [rsp+30h] [rbp-A9h] BYREF
  LPVOID v41; // [rsp+38h] [rbp-A1h] BYREF
  void *v42; // [rsp+40h] [rbp-99h] BYREF
  LPVOID lpMem; // [rsp+48h] [rbp-91h] BYREF
  __int128 v44; // [rsp+50h] [rbp-89h] BYREF
  LPVOID *v45; // [rsp+60h] [rbp-79h]
  void *v46; // [rsp+70h] [rbp-69h]
  winrt::impl *v47; // [rsp+78h] [rbp-61h] BYREF
  __int64 v48; // [rsp+80h] [rbp-59h] BYREF
  char v49; // [rsp+88h] [rbp-51h]
  volatile signed __int32 *v50; // [rsp+98h] [rbp-41h]
  volatile signed __int32 *v51; // [rsp+A0h] [rbp-39h]
  __int64 *v52; // [rsp+A8h] [rbp-31h]
  _QWORD v53[7]; // [rsp+B0h] [rbp-29h] BYREF

  v46 = a4;
  v47 = a1;
  v53[4] = a2;
  v53[5] = a3;
  v53[6] = a4;
  if ( *((_QWORD *)a3 + 3) <= 7u )
    v7 = a3;
  else
    v7 = *(const unsigned __int16 **)a3;
  winrt::hstring::hstring((winrt::hstring *)&lpMem, v7);
  v8 = (volatile signed __int32 *)lpMem;
  v10 = (volatile signed __int32 *)winrt::impl::duplicate_hstring((winrt::impl *)lpMem, v9);
  v50 = v10;
  if ( v8 )
  {
    v11 = _InterlockedDecrement(v8 + 6);
    if ( v11 )
    {
      if ( v11 < 0 )
        abort();
    }
    else
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v8);
    }
  }
  v44 = 0;
  v45 = 0;
  winrt::single_threaded_vector<winrt::hstring,std::allocator<winrt::hstring>>(&v42, &v44);
  std::vector<winrt::hstring>::~vector<winrt::hstring>(&v44);
  lpMem = v42;
  LODWORD(v44) = 685;
  *((_QWORD *)&v44 + 1) = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt/Windows.Foundation.Collections.h";
  v45 = 0;
  v13 = (*(__int64 (__fastcall **)(void *, volatile signed __int32 *))(*(_QWORD *)v42 + 104LL))(v42, v10);
  if ( v13 < 0 )
    winrt::throw_hresult((unsigned int)v13, &v44);
  LODWORD(v41) = 1;
  winrt::param::async_iterable<winrt::hstring>::async_iterable<winrt::hstring>(&v48, &v42);
  if ( *((_QWORD *)a2 + 3) <= 7u )
    v14 = a2;
  else
    v14 = *(const unsigned __int16 **)a2;
  winrt::hstring::hstring((winrt::hstring *)&v47, v14);
  v15 = (volatile signed __int32 *)v47;
  v18 = (volatile signed __int32 *)winrt::impl::duplicate_hstring(v47, v16);
  v51 = v18;
  v53[0] = v18;
  *(_QWORD *)&v44 = v53;
  *((_QWORD *)&v44 + 1) = &v48;
  v45 = &v41;
  v52 = &qword_18005FA68;
  _InterlockedIncrement64(&qword_18005FA68);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2> )
  {
    `winrt::Windows::Devices::Enumeration::DeviceInformation::CreateFromIdAsync'::`2'::_lambda_1_::operator()(
      &v44,
      &v38,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>);
    _InterlockedAdd64(&qword_18005FA68, 0xFFFFFFFFFFFFFFFFuLL);
  }
  else
  {
    _InterlockedAdd64(&qword_18005FA68, 0xFFFFFFFFFFFFFFFFuLL);
    ___call_AEAV_lambda_1___1__CreateFromIdAsync_DeviceInformation_Enumeration_Devices_Windows_winrt__SA_AEBUhstring_param_7_AEBU__async_iterable_Uhstring_winrt___97_AEBW4DeviceInformationKind_4567__Z____factory_cache_entry_UDeviceInformation_Enumeration_Devices_Windows_winrt__UIDeviceInformationStatics2_2345__impl_winrt__QEAA_A_PAEAV_lambda_1___1__CreateFromIdAsync_DeviceInformation_Enumeration_Devices_Windows_2_SA_AEBUhstring_param_2_AEBU__async_iterable_Uhstring_winrt___param_2_AEBW4DeviceInformationKind_6782__Z__Z(
      v17,
      &v38,
      &v44);
  }
  winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Devices::Enumeration::DeviceInformation>,winrt::Windows::Devices::Enumeration::DeviceInformation>::get(
    &v38,
    &v40);
  if ( v38 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v38);
  if ( v18 )
  {
    v19 = _InterlockedDecrement(v18 + 6);
    if ( v19 )
    {
      if ( v19 < 0 )
        abort();
    }
    else
    {
      v20 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v20, 0, (LPVOID)v18);
    }
  }
  if ( v15 )
  {
    v21 = _InterlockedDecrement(v15 + 6);
    if ( v21 )
    {
      if ( v21 < 0 )
        abort();
    }
    else
    {
      v22 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v22, 0, (LPVOID)v15);
    }
  }
  if ( v49 )
  {
    v23 = v48;
  }
  else
  {
    v23 = 0;
    v48 = 0;
  }
  if ( v23 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v48);
  v24 = winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Properties(
          &v40,
          &v38);
  *(_QWORD *)&v44 = v10;
  winrt::impl::consume_Windows_Foundation_Collections_IMapView<winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Windows::Foundation::IInspectable>,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(
    v24,
    &v39,
    &v44);
  if ( v38 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v38);
  if ( v39 )
  {
    v25 = winrt::unbox_value<winrt::hstring>(&v41, &v39);
    if ( *(_QWORD *)v25 )
      v26 = *(const wchar_t **)(*(_QWORD *)v25 + 16LL);
    else
      v26 = &S2;
    *(_OWORD *)a1 = 0;
    *((_QWORD *)a1 + 2) = 0;
    *((_QWORD *)a1 + 3) = 0;
    v27 = -1;
    do
      ++v27;
    while ( v26[v27] );
    std::wstring::_Construct<1,unsigned short const *>(a1, v26);
    v28 = v41;
    if ( v41 )
    {
      v29 = _InterlockedDecrement((volatile signed __int32 *)v41 + 6);
      if ( v29 )
      {
        if ( v29 < 0 )
          abort();
      }
      else
      {
        v30 = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(v30, 0, v28);
      }
      v41 = 0;
    }
    if ( v39 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v39);
    if ( v40 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v40);
    if ( lpMem )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v42);
    if ( v10 )
    {
      v31 = _InterlockedDecrement(v10 + 6);
      if ( v31 )
      {
        if ( v31 < 0 )
          abort();
      }
      else
      {
        v32 = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(v32, 0, (LPVOID)v10);
      }
    }
    std::wstring::~wstring(a2);
    std::wstring::~wstring(a3);
    v33 = v46;
  }
  else
  {
    *(_OWORD *)a1 = 0;
    *((_QWORD *)a1 + 2) = 0;
    *((_QWORD *)a1 + 3) = 0;
    v34 = v46;
    *(_OWORD *)a1 = *(_OWORD *)v46;
    *((_OWORD *)a1 + 1) = v34[1];
    *(_WORD *)v34 = 0;
    *((_QWORD *)v34 + 2) = 0;
    *((_QWORD *)v34 + 3) = 7;
    if ( v40 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v40);
    if ( lpMem )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v42);
    if ( v10 )
    {
      v35 = _InterlockedDecrement(v10 + 6);
      if ( v35 )
      {
        if ( v35 < 0 )
          abort();
      }
      else
      {
        v36 = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(v36, 0, (LPVOID)v10);
      }
    }
    std::wstring::~wstring(a2);
    std::wstring::~wstring(a3);
    v33 = v34;
  }
  std::wstring::~wstring(v33);
  return a1;
}

```

## disassembly

```asm
0x180011018  push    rbp
0x18001101a  push    rbx
0x18001101b  push    rsi
0x18001101c  push    rdi
0x18001101d  push    r12
0x18001101f  push    r13
0x180011021  push    r14
0x180011023  push    r15
0x180011025  lea     rbp, [rsp-1Fh]
0x18001102a  sub     rsp, 0F8h
0x180011031  mov     rax, cs:__security_cookie
0x180011038  xor     rax, rsp
0x18001103b  mov     [rbp+57h+var_48], rax
0x18001103f  mov     rax, r9
0x180011042  mov     [rbp+57h+var_C0], rax
0x180011046  mov     r12, r8
0x180011049  mov     r13, rdx
0x18001104c  mov     r14, rcx
0x18001104f  mov     [rbp+57h+var_B8], rcx
0x180011053  mov     [rbp+57h+var_60], rdx
0x180011057  mov     [rbp+57h+var_58], r8
0x18001105b  mov     [rbp+57h+var_50], rax
0x18001105f  xor     r15d, r15d
0x180011062  cmp     qword ptr [r8+18h], 7
0x180011067  jbe     short loc_18001106E
0x180011069  mov     rdx, [r8]
0x18001106c  jmp     short loc_180011071
0x18001106e  mov     rdx, r12; unsigned __int16 *
0x180011071  lea     rcx, [rsp+130h+lpMem]; this
0x180011076  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x18001107b  nop
0x18001107c  mov     rdi, [rsp+130h+lpMem]
0x180011081  mov     rcx, rdi; this
0x180011084  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x180011089  mov     rbx, rax
0x18001108c  mov     [rbp+57h+var_98], rax
0x180011090  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180011094  test    rdi, rdi
0x180011097  jz      short loc_1800110BC
0x180011099  mov     eax, esi
0x18001109b  lock xadd [rdi+18h], eax
0x1800110a0  sub     eax, 1
0x1800110a3  jnz     loc_180011140
0x1800110a9  nop
0x1800110aa  call    WINRT_IMPL_GetProcessHeap
0x1800110af  mov     rcx, rax; hHeap
0x1800110b2  mov     r8, rdi; lpMem
0x1800110b5  xor     edx, edx; dwFlags
0x1800110b7  call    WINRT_IMPL_HeapFree
0x1800110bc  xorps   xmm0, xmm0
0x1800110bf  movdqu  [rsp+130h+var_E0], xmm0
0x1800110c5  mov     [rbp+57h+var_D0], r15
0x1800110c9  lea     rdx, [rsp+130h+var_E0]
0x1800110ce  lea     rcx, [rsp+130h+var_F0]
0x1800110d3  call    ??$single_threaded_vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@winrt@@YA?AU?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@0@$$QEAV?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@@Z; winrt::single_threaded_vector<winrt::hstring,std::allocator<winrt::hstring>>(std::vector<winrt::hstring> &&)
0x1800110d8  nop
0x1800110d9  lea     rcx, [rsp+130h+var_E0]
0x1800110de  call    ??1?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@QEAA@XZ; std::vector<winrt::hstring>::~vector<winrt::hstring>(void)
0x1800110e3  mov     rcx, [rsp+130h+var_F0]
0x1800110e8  mov     [rsp+130h+lpMem], rcx
0x1800110ed  mov     dword ptr [rsp+130h+var_E0], 2ADh
0x1800110f5  lea     rax, aOnecoreuapInte_1; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x1800110fc  mov     qword ptr [rsp+130h+var_E0+8], rax
0x180011101  mov     [rbp+57h+var_D0], r15
0x180011105  mov     rax, [rcx]
0x180011108  mov     rdx, rbx
0x18001110b  mov     rax, [rax+68h]
0x18001110f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011114  test    eax, eax
0x180011116  js      loc_1800114AD
0x18001111c  mov     dword ptr [rsp+130h+var_F8], 1
0x180011124  lea     rdx, [rsp+130h+var_F0]
0x180011129  lea     rcx, [rbp+57h+var_B0]
0x18001112d  call    ??$?0U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@winrt@@$0A@@?$async_iterable@Uhstring@winrt@@@param@winrt@@QEAA@AEBU?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@2@@Z; winrt::param::async_iterable<winrt::hstring>::async_iterable<winrt::hstring>(winrt::Windows::Foundation::Collections::IVector<winrt::hstring> const &)
0x180011132  nop
0x180011133  cmp     qword ptr [r13+18h], 7
0x180011138  jbe     short loc_18001114F
0x18001113a  mov     rdx, [r13+0]
0x18001113e  jmp     short loc_180011152
0x180011140  test    eax, eax
0x180011142  jns     loc_1800110BC
0x180011148  call    cs:__imp_abort
0x18001114f  mov     rdx, r13; unsigned __int16 *
0x180011152  lea     rcx, [rbp+57h+var_B8]; this
0x180011156  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x18001115b  nop
0x18001115c  mov     rdi, [rbp+57h+var_B8]
0x180011160  mov     rcx, rdi; this
0x180011163  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x180011168  mov     r15, rax
0x18001116b  mov     [rbp+57h+var_90], rax
0x18001116f  mov     [rbp+57h+var_80], rax
0x180011173  lea     rax, [rbp+57h+var_80]
0x180011177  mov     qword ptr [rsp+130h+var_E0], rax
0x18001117c  lea     rax, [rbp+57h+var_B0]
0x180011180  mov     qword ptr [rsp+130h+var_E0+8], rax
0x180011185  lea     rax, [rsp+130h+var_F8]
0x18001118a  mov     [rbp+57h+var_D0], rax
0x18001118e  lea     rax, qword_18005FA68
0x180011195  mov     [rbp+57h+var_88], rax
0x180011199  lock inc cs:qword_18005FA68
0x1800111a1  cmp     cs:??$factory_cache_entry_v@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@impl@winrt@@3U?$factory_cache_entry@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@12@A, 0; factory_cache_entry<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>::winrt::factory_cache_entry<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2> winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>
0x1800111a9  jz      short loc_1800111CC
0x1800111ab  lea     r8, ??$factory_cache_entry_v@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@impl@winrt@@3U?$factory_cache_entry@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@12@A; factory_cache_entry<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>::winrt::factory_cache_entry<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2> winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>
0x1800111b2  lea     rdx, [rsp+130h+var_110]
0x1800111b7  lea     rcx, [rsp+130h+var_E0]
0x1800111bc  call    ??R_lambda_1_@?1??CreateFromIdAsync@DeviceInformation@Enumeration@Devices@Windows@winrt@@SA@AEBUhstring@param@6@AEBU?$async_iterable@Uhstring@winrt@@@86@AEBW4DeviceInformationKind@3456@@Z@QEBA@AEBUIDeviceInformationStatics2@3456@@Z; `winrt::Windows::Devices::Enumeration::DeviceInformation::CreateFromIdAsync(winrt::param::hstring const &,winrt::param::async_iterable<winrt::hstring> const &,winrt::Windows::Devices::Enumeration::DeviceInformationKind const &)'::`2'::_lambda_1_::operator()(winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2 const &)
0x1800111c1  nop
0x1800111c2  lock add cs:qword_18005FA68, rsi
0x1800111ca  jmp     short loc_1800111E4
0x1800111cc  lock add cs:qword_18005FA68, rsi
0x1800111d4  lea     r8, [rsp+130h+var_E0]
0x1800111d9  lea     rdx, [rsp+130h+var_110]
0x1800111de  call    ??$call@AEAV_lambda_1_@?1??CreateFromIdAsync@DeviceInformation@Enumeration@Devices@Windows@winrt@@SA@AEBUhstring@param@7@AEBU?$async_iterable@Uhstring@winrt@@@97@AEBW4DeviceInformationKind@4567@@Z@@?$factory_cache_entry@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateFromIdAsync@DeviceInformation@Enumeration@Devices@Windows@2@SA@AEBUhstring@param@2@AEBU?$async_iterable@Uhstring@winrt@@@param@2@AEBW4DeviceInformationKind@6782@@Z@@Z
0x1800111e3  nop
0x1800111e4  lea     rdx, [rsp+130h+var_100]
0x1800111e9  lea     rcx, [rsp+130h+var_110]
0x1800111ee  call    ?get@?$consume_Windows_Foundation_IAsyncOperation@U?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@UDeviceInformation@Enumeration@Devices@34@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Devices::Enumeration::DeviceInformation>,winrt::Windows::Devices::Enumeration::DeviceInformation>::get(void)
0x1800111f3  nop
0x1800111f4  cmp     [rsp+130h+var_110], 0
0x1800111fa  jz      short loc_180011207
0x1800111fc  lea     rcx, [rsp+130h+var_110]
0x180011201  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180011206  nop
0x180011207  test    r15, r15
0x18001120a  jz      short loc_18001122C
0x18001120c  mov     eax, esi
0x18001120e  lock xadd [r15+18h], eax
0x180011214  sub     eax, 1
0x180011217  jnz     short loc_180011263
0x180011219  nop
0x18001121a  call    WINRT_IMPL_GetProcessHeap
0x18001121f  mov     rcx, rax; hHeap
0x180011222  mov     r8, r15; lpMem
0x180011225  xor     edx, edx; dwFlags
0x180011227  call    WINRT_IMPL_HeapFree
0x18001122c  xor     r15d, r15d
0x18001122f  test    rdi, rdi
0x180011232  jz      short loc_180011254
0x180011234  mov     eax, esi
0x180011236  lock xadd [rdi+18h], eax
0x18001123b  sub     eax, 1
0x18001123e  jnz     short loc_180011271
0x180011240  nop
0x180011241  call    WINRT_IMPL_GetProcessHeap
0x180011246  mov     rcx, rax; hHeap
0x180011249  mov     r8, rdi; lpMem
0x18001124c  xor     edx, edx; dwFlags
0x18001124e  call    WINRT_IMPL_HeapFree
0x180011253  nop
0x180011254  cmp     [rbp+57h+var_A8], r15b
0x180011258  jnz     short loc_18001127C
0x18001125a  mov     rax, r15
0x18001125d  mov     [rbp+57h+var_B0], rax
0x180011261  jmp     short loc_180011280
0x180011263  xor     r15d, r15d
0x180011266  test    eax, eax
0x180011268  jns     short loc_18001122F
0x18001126a  call    cs:__imp_abort
0x180011271  test    eax, eax
0x180011273  jns     short loc_180011254
0x180011275  call    cs:__imp_abort
0x18001127c  mov     rax, [rbp+57h+var_B0]
0x180011280  test    rax, rax
0x180011283  jz      short loc_18001128E
0x180011285  lea     rcx, [rbp+57h+var_B0]
0x180011289  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001128e  lea     rdx, [rsp+130h+var_110]
0x180011293  lea     rcx, [rsp+130h+var_100]
0x180011298  call    ?Properties@?$consume_Windows_Devices_Enumeration_IDeviceInformation@UIDeviceInformation@Enumeration@Devices@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Properties(void)
0x18001129d  nop
0x18001129e  mov     qword ptr [rsp+130h+var_E0], rbx
0x1800112a3  lea     r8, [rsp+130h+var_E0]
0x1800112a8  lea     rdx, [rsp+130h+var_108]
0x1800112ad  mov     rcx, rax
0x1800112b0  call    ?Lookup@?$consume_Windows_Foundation_Collections_IMapView@U?$IMapView@Uhstring@winrt@@UIInspectable@Foundation@Windows@2@@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMapView<winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Windows::Foundation::IInspectable>,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(winrt::param::hstring const &)
0x1800112b5  nop
0x1800112b6  cmp     [rsp+130h+var_110], r15
0x1800112bb  jz      short loc_1800112C7
0x1800112bd  lea     rcx, [rsp+130h+var_110]
0x1800112c2  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800112c7  mov     rax, [rsp+130h+var_108]
0x1800112cc  test    rax, rax
0x1800112cf  jz      loc_1800113DB
0x1800112d5  lea     rdx, [rsp+130h+var_108]
0x1800112da  lea     rcx, [rsp+130h+var_F8]
0x1800112df  call    ??$unbox_value@Uhstring@winrt@@@winrt@@YA?AUhstring@0@AEBUIInspectable@Foundation@Windows@0@@Z; winrt::unbox_value<winrt::hstring>(winrt::Windows::Foundation::IInspectable const &)
0x1800112e4  nop
0x1800112e5  mov     rdx, [rax]
0x1800112e8  test    rdx, rdx
0x1800112eb  jz      short loc_1800112F3
0x1800112ed  mov     rdx, [rdx+10h]
0x1800112f1  jmp     short loc_1800112FA
0x1800112f3  lea     rdx, S2
0x1800112fa  xorps   xmm0, xmm0
0x1800112fd  movups  xmmword ptr [r14], xmm0
0x180011301  mov     [r14+10h], r15
0x180011305  mov     [r14+18h], r15
0x180011309  mov     r8, rsi
0x18001130c  inc     r8
0x18001130f  cmp     [rdx+r8*2], r15w
0x180011314  jnz     short loc_18001130C
0x180011316  mov     rcx, r14
0x180011319  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001131e  nop
0x18001131f  mov     rdi, [rsp+130h+var_F8]
0x180011324  test    rdi, rdi
0x180011327  jz      short loc_180011351
0x180011329  mov     eax, esi
0x18001132b  lock xadd [rdi+18h], eax
0x180011330  sub     eax, 1
0x180011333  jnz     loc_1800113C5
0x180011339  nop
0x18001133a  call    WINRT_IMPL_GetProcessHeap
0x18001133f  mov     rcx, rax; hHeap
0x180011342  mov     r8, rdi; lpMem
0x180011345  xor     edx, edx; dwFlags
0x180011347  call    WINRT_IMPL_HeapFree
0x18001134c  mov     [rsp+130h+var_F8], r15
0x180011351  cmp     [rsp+130h+var_108], r15
0x180011356  jz      short loc_180011363
0x180011358  lea     rcx, [rsp+130h+var_108]
0x18001135d  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180011362  nop
0x180011363  cmp     [rsp+130h+var_100], r15
0x180011368  jz      short loc_180011375
0x18001136a  lea     rcx, [rsp+130h+var_100]
0x18001136f  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180011374  nop
0x180011375  cmp     [rsp+130h+lpMem], r15
0x18001137a  jz      short loc_180011387
0x18001137c  lea     rcx, [rsp+130h+var_F0]
0x180011381  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180011386  nop
0x180011387  test    rbx, rbx
0x18001138a  jz      short loc_1800113AA
0x18001138c  lock xadd [rbx+18h], esi
0x180011391  sub     esi, 1
0x180011394  jnz     short loc_1800113D0
0x180011396  nop
0x180011397  call    WINRT_IMPL_GetProcessHeap
0x18001139c  mov     rcx, rax; hHeap
0x18001139f  mov     r8, rbx; lpMem
0x1800113a2  xor     edx, edx; dwFlags
0x1800113a4  call    WINRT_IMPL_HeapFree
0x1800113a9  nop
0x1800113aa  mov     rcx, r13; void *
0x1800113ad  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800113b2  nop
0x1800113b3  mov     rcx, r12; void *
0x1800113b6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800113bb  nop
0x1800113bc  mov     rcx, [rbp+57h+var_C0]
0x1800113c0  jmp     loc_18001147A
0x1800113c5  test    eax, eax
0x1800113c7  jns     short loc_18001134C
0x1800113c9  call    cs:__imp_abort
0x1800113d0  test    esi, esi
0x1800113d2  jns     short loc_1800113AA
0x1800113d4  call    cs:__imp_abort
0x1800113db  xorps   xmm0, xmm0
0x1800113de  movups  xmmword ptr [r14], xmm0
0x1800113e2  mov     [r14+10h], r15
0x1800113e6  mov     [r14+18h], r15
0x1800113ea  mov     rdi, [rbp+57h+var_C0]
0x1800113ee  movups  xmm0, xmmword ptr [rdi]
0x1800113f1  movups  xmmword ptr [r14], xmm0
0x1800113f5  movups  xmm1, xmmword ptr [rdi+10h]
0x1800113f9  movups  xmmword ptr [r14+10h], xmm1
0x1800113fe  mov     [rdi], r15w
0x180011402  mov     [rdi+10h], r15
0x180011406  mov     qword ptr [rdi+18h], 7
0x18001140e  test    rax, rax
0x180011411  jz      short loc_18001141E
0x180011413  lea     rcx, [rsp+130h+var_108]
0x180011418  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001141d  nop
0x18001141e  cmp     [rsp+130h+var_100], r15
0x180011423  jz      short loc_180011430
0x180011425  lea     rcx, [rsp+130h+var_100]
0x18001142a  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001142f  nop
0x180011430  cmp     [rsp+130h+lpMem], r15
0x180011435  jz      short loc_180011442
0x180011437  lea     rcx, [rsp+130h+var_F0]
0x18001143c  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180011441  nop
0x180011442  test    rbx, rbx
0x180011445  jz      short loc_180011465
0x180011447  lock xadd [rbx+18h], esi
0x18001144c  sub     esi, 1
0x18001144f  jnz     short loc_1800114A2
0x180011451  nop
0x180011452  call    WINRT_IMPL_GetProcessHeap
0x180011457  mov     rcx, rax; hHeap
0x18001145a  mov     r8, rbx; lpMem
0x18001145d  xor     edx, edx; dwFlags
0x18001145f  call    WINRT_IMPL_HeapFree
0x180011464  nop
0x180011465  mov     rcx, r13; void *
  ... truncated ...
```
