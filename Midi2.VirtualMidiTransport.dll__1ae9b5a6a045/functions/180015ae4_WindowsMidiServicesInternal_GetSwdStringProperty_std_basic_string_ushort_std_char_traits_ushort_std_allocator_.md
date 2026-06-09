# WindowsMidiServicesInternal::GetSwdStringProperty(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x180015ae4`
- end: `0x180015f86`
- name: `?GetSwdStringProperty@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@00@Z`
- size: `1186`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800159c8`

## callees

- `0x1800038f0`
- `0x180004718`
- `0x180004784`
- `0x18000bf6c`
- `0x18000cb48`
- `0x180012510`
- `0x180012f70`
- `0x180013398`
- `0x1800134d0`
- `0x180013f64`
- `0x1800143b0`
- `0x180014980`
- `0x180015ae4`
- `0x180016504`
- `0x180017edc`
- `0x1800194c8`
- `0x1800199b4`
- `0x18001a3fc`
- `0x18001a798`
- `0x180021010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180015c14`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180015d36`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180015d41`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180015e95`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180015ea0`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180015f72`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180015c14`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180015d36`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180015d41`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180015e95`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180015ea0`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180015f72`

## pseudocode

```c
// Hidden C++ exception states: #wind=23
winrt::impl *__fastcall WindowsMidiServicesInternal::GetSwdStringProperty(
        winrt::impl *a1,
        __int64 a2,
        __int64 a3,
        _OWORD *a4)
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
  _OWORD *v33; // rcx
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
  _OWORD *v46; // [rsp+70h] [rbp-69h]
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
  if ( *(_QWORD *)(a3 + 24) <= 7u )
    v7 = (const unsigned __int16 *)a3;
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
  if ( *(_QWORD *)(a2 + 24) <= 7u )
    v14 = (const unsigned __int16 *)a2;
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
  v52 = &qword_18002DA28;
  _InterlockedIncrement64(&qword_18002DA28);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2> )
  {
    `winrt::Windows::Devices::Enumeration::DeviceInformation::CreateFromIdAsync'::`2'::_lambda_1_::operator()(
      &v44,
      &v38,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>);
    _InterlockedAdd64(&qword_18002DA28, 0xFFFFFFFFFFFFFFFFuLL);
  }
  else
  {
    _InterlockedAdd64(&qword_18002DA28, 0xFFFFFFFFFFFFFFFFuLL);
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
    *(_OWORD *)a1 = *v46;
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
0x180015ae4  push    rbp
0x180015ae6  push    rbx
0x180015ae7  push    rsi
0x180015ae8  push    rdi
0x180015ae9  push    r12
0x180015aeb  push    r13
0x180015aed  push    r14
0x180015aef  push    r15
0x180015af1  lea     rbp, [rsp-1Fh]
0x180015af6  sub     rsp, 0F8h
0x180015afd  mov     rax, cs:__security_cookie
0x180015b04  xor     rax, rsp
0x180015b07  mov     [rbp+57h+var_48], rax
0x180015b0b  mov     rax, r9
0x180015b0e  mov     [rbp+57h+var_C0], rax
0x180015b12  mov     r12, r8
0x180015b15  mov     r13, rdx
0x180015b18  mov     r14, rcx
0x180015b1b  mov     [rbp+57h+var_B8], rcx
0x180015b1f  mov     [rbp+57h+var_60], rdx
0x180015b23  mov     [rbp+57h+var_58], r8
0x180015b27  mov     [rbp+57h+var_50], rax
0x180015b2b  xor     r15d, r15d
0x180015b2e  cmp     qword ptr [r8+18h], 7
0x180015b33  jbe     short loc_180015B3A
0x180015b35  mov     rdx, [r8]
0x180015b38  jmp     short loc_180015B3D
0x180015b3a  mov     rdx, r12; unsigned __int16 *
0x180015b3d  lea     rcx, [rsp+130h+lpMem]; this
0x180015b42  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x180015b47  nop
0x180015b48  mov     rdi, [rsp+130h+lpMem]
0x180015b4d  mov     rcx, rdi; this
0x180015b50  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x180015b55  mov     rbx, rax
0x180015b58  mov     [rbp+57h+var_98], rax
0x180015b5c  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180015b60  test    rdi, rdi
0x180015b63  jz      short loc_180015B88
0x180015b65  mov     eax, esi
0x180015b67  lock xadd [rdi+18h], eax
0x180015b6c  sub     eax, 1
0x180015b6f  jnz     loc_180015C0C
0x180015b75  nop
0x180015b76  call    WINRT_IMPL_GetProcessHeap
0x180015b7b  mov     rcx, rax; hHeap
0x180015b7e  mov     r8, rdi; lpMem
0x180015b81  xor     edx, edx; dwFlags
0x180015b83  call    WINRT_IMPL_HeapFree
0x180015b88  xorps   xmm0, xmm0
0x180015b8b  movdqu  [rsp+130h+var_E0], xmm0
0x180015b91  mov     [rbp+57h+var_D0], r15
0x180015b95  lea     rdx, [rsp+130h+var_E0]
0x180015b9a  lea     rcx, [rsp+130h+var_F0]
0x180015b9f  call    ??$single_threaded_vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@winrt@@YA?AU?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@0@$$QEAV?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@@Z; winrt::single_threaded_vector<winrt::hstring,std::allocator<winrt::hstring>>(std::vector<winrt::hstring> &&)
0x180015ba4  nop
0x180015ba5  lea     rcx, [rsp+130h+var_E0]
0x180015baa  call    ??1?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@QEAA@XZ; std::vector<winrt::hstring>::~vector<winrt::hstring>(void)
0x180015baf  mov     rcx, [rsp+130h+var_F0]
0x180015bb4  mov     [rsp+130h+lpMem], rcx
0x180015bb9  mov     dword ptr [rsp+130h+var_E0], 2ADh
0x180015bc1  lea     rax, aOnecoreuapInte_1; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x180015bc8  mov     qword ptr [rsp+130h+var_E0+8], rax
0x180015bcd  mov     [rbp+57h+var_D0], r15
0x180015bd1  mov     rax, [rcx]
0x180015bd4  mov     rdx, rbx
0x180015bd7  mov     rax, [rax+68h]
0x180015bdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015be0  test    eax, eax
0x180015be2  js      loc_180015F79
0x180015be8  mov     dword ptr [rsp+130h+var_F8], 1
0x180015bf0  lea     rdx, [rsp+130h+var_F0]
0x180015bf5  lea     rcx, [rbp+57h+var_B0]
0x180015bf9  call    ??$?0U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@winrt@@$0A@@?$async_iterable@Uhstring@winrt@@@param@winrt@@QEAA@AEBU?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@2@@Z; winrt::param::async_iterable<winrt::hstring>::async_iterable<winrt::hstring>(winrt::Windows::Foundation::Collections::IVector<winrt::hstring> const &)
0x180015bfe  nop
0x180015bff  cmp     qword ptr [r13+18h], 7
0x180015c04  jbe     short loc_180015C1B
0x180015c06  mov     rdx, [r13+0]
0x180015c0a  jmp     short loc_180015C1E
0x180015c0c  test    eax, eax
0x180015c0e  jns     loc_180015B88
0x180015c14  call    cs:__imp_abort
0x180015c1b  mov     rdx, r13; unsigned __int16 *
0x180015c1e  lea     rcx, [rbp+57h+var_B8]; this
0x180015c22  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x180015c27  nop
0x180015c28  mov     rdi, [rbp+57h+var_B8]
0x180015c2c  mov     rcx, rdi; this
0x180015c2f  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x180015c34  mov     r15, rax
0x180015c37  mov     [rbp+57h+var_90], rax
0x180015c3b  mov     [rbp+57h+var_80], rax
0x180015c3f  lea     rax, [rbp+57h+var_80]
0x180015c43  mov     qword ptr [rsp+130h+var_E0], rax
0x180015c48  lea     rax, [rbp+57h+var_B0]
0x180015c4c  mov     qword ptr [rsp+130h+var_E0+8], rax
0x180015c51  lea     rax, [rsp+130h+var_F8]
0x180015c56  mov     [rbp+57h+var_D0], rax
0x180015c5a  lea     rax, qword_18002DA28
0x180015c61  mov     [rbp+57h+var_88], rax
0x180015c65  lock inc cs:qword_18002DA28
0x180015c6d  cmp     cs:??$factory_cache_entry_v@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@impl@winrt@@3U?$factory_cache_entry@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@12@A, 0; factory_cache_entry<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>::winrt::factory_cache_entry<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2> winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>
0x180015c75  jz      short loc_180015C98
0x180015c77  lea     r8, ??$factory_cache_entry_v@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@impl@winrt@@3U?$factory_cache_entry@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@12@A; factory_cache_entry<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>::winrt::factory_cache_entry<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2> winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>
0x180015c7e  lea     rdx, [rsp+130h+var_110]
0x180015c83  lea     rcx, [rsp+130h+var_E0]
0x180015c88  call    ??R_lambda_1_@?1??CreateFromIdAsync@DeviceInformation@Enumeration@Devices@Windows@winrt@@SA@AEBUhstring@param@6@AEBU?$async_iterable@Uhstring@winrt@@@86@AEBW4DeviceInformationKind@3456@@Z@QEBA@AEBUIDeviceInformationStatics2@3456@@Z; `winrt::Windows::Devices::Enumeration::DeviceInformation::CreateFromIdAsync(winrt::param::hstring const &,winrt::param::async_iterable<winrt::hstring> const &,winrt::Windows::Devices::Enumeration::DeviceInformationKind const &)'::`2'::_lambda_1_::operator()(winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2 const &)
0x180015c8d  nop
0x180015c8e  lock add cs:qword_18002DA28, rsi
0x180015c96  jmp     short loc_180015CB0
0x180015c98  lock add cs:qword_18002DA28, rsi
0x180015ca0  lea     r8, [rsp+130h+var_E0]
0x180015ca5  lea     rdx, [rsp+130h+var_110]
0x180015caa  call    ??$call@AEAV_lambda_1_@?1??CreateFromIdAsync@DeviceInformation@Enumeration@Devices@Windows@winrt@@SA@AEBUhstring@param@7@AEBU?$async_iterable@Uhstring@winrt@@@97@AEBW4DeviceInformationKind@4567@@Z@@?$factory_cache_entry@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateFromIdAsync@DeviceInformation@Enumeration@Devices@Windows@2@SA@AEBUhstring@param@2@AEBU?$async_iterable@Uhstring@winrt@@@param@2@AEBW4DeviceInformationKind@6782@@Z@@Z
0x180015caf  nop
0x180015cb0  lea     rdx, [rsp+130h+var_100]
0x180015cb5  lea     rcx, [rsp+130h+var_110]
0x180015cba  call    ?get@?$consume_Windows_Foundation_IAsyncOperation@U?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@UDeviceInformation@Enumeration@Devices@34@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Devices::Enumeration::DeviceInformation>,winrt::Windows::Devices::Enumeration::DeviceInformation>::get(void)
0x180015cbf  nop
0x180015cc0  cmp     [rsp+130h+var_110], 0
0x180015cc6  jz      short loc_180015CD3
0x180015cc8  lea     rcx, [rsp+130h+var_110]
0x180015ccd  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180015cd2  nop
0x180015cd3  test    r15, r15
0x180015cd6  jz      short loc_180015CF8
0x180015cd8  mov     eax, esi
0x180015cda  lock xadd [r15+18h], eax
0x180015ce0  sub     eax, 1
0x180015ce3  jnz     short loc_180015D2F
0x180015ce5  nop
0x180015ce6  call    WINRT_IMPL_GetProcessHeap
0x180015ceb  mov     rcx, rax; hHeap
0x180015cee  mov     r8, r15; lpMem
0x180015cf1  xor     edx, edx; dwFlags
0x180015cf3  call    WINRT_IMPL_HeapFree
0x180015cf8  xor     r15d, r15d
0x180015cfb  test    rdi, rdi
0x180015cfe  jz      short loc_180015D20
0x180015d00  mov     eax, esi
0x180015d02  lock xadd [rdi+18h], eax
0x180015d07  sub     eax, 1
0x180015d0a  jnz     short loc_180015D3D
0x180015d0c  nop
0x180015d0d  call    WINRT_IMPL_GetProcessHeap
0x180015d12  mov     rcx, rax; hHeap
0x180015d15  mov     r8, rdi; lpMem
0x180015d18  xor     edx, edx; dwFlags
0x180015d1a  call    WINRT_IMPL_HeapFree
0x180015d1f  nop
0x180015d20  cmp     [rbp+57h+var_A8], r15b
0x180015d24  jnz     short loc_180015D48
0x180015d26  mov     rax, r15
0x180015d29  mov     [rbp+57h+var_B0], rax
0x180015d2d  jmp     short loc_180015D4C
0x180015d2f  xor     r15d, r15d
0x180015d32  test    eax, eax
0x180015d34  jns     short loc_180015CFB
0x180015d36  call    cs:__imp_abort
0x180015d3d  test    eax, eax
0x180015d3f  jns     short loc_180015D20
0x180015d41  call    cs:__imp_abort
0x180015d48  mov     rax, [rbp+57h+var_B0]
0x180015d4c  test    rax, rax
0x180015d4f  jz      short loc_180015D5A
0x180015d51  lea     rcx, [rbp+57h+var_B0]
0x180015d55  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180015d5a  lea     rdx, [rsp+130h+var_110]
0x180015d5f  lea     rcx, [rsp+130h+var_100]
0x180015d64  call    ?Properties@?$consume_Windows_Devices_Enumeration_IDeviceInformation@UIDeviceInformation@Enumeration@Devices@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Properties(void)
0x180015d69  nop
0x180015d6a  mov     qword ptr [rsp+130h+var_E0], rbx
0x180015d6f  lea     r8, [rsp+130h+var_E0]
0x180015d74  lea     rdx, [rsp+130h+var_108]
0x180015d79  mov     rcx, rax
0x180015d7c  call    ?Lookup@?$consume_Windows_Foundation_Collections_IMapView@U?$IMapView@Uhstring@winrt@@UIInspectable@Foundation@Windows@2@@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMapView<winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Windows::Foundation::IInspectable>,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(winrt::param::hstring const &)
0x180015d81  nop
0x180015d82  cmp     [rsp+130h+var_110], r15
0x180015d87  jz      short loc_180015D93
0x180015d89  lea     rcx, [rsp+130h+var_110]
0x180015d8e  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180015d93  mov     rax, [rsp+130h+var_108]
0x180015d98  test    rax, rax
0x180015d9b  jz      loc_180015EA7
0x180015da1  lea     rdx, [rsp+130h+var_108]
0x180015da6  lea     rcx, [rsp+130h+var_F8]
0x180015dab  call    ??$unbox_value@Uhstring@winrt@@@winrt@@YA?AUhstring@0@AEBUIInspectable@Foundation@Windows@0@@Z; winrt::unbox_value<winrt::hstring>(winrt::Windows::Foundation::IInspectable const &)
0x180015db0  nop
0x180015db1  mov     rdx, [rax]
0x180015db4  test    rdx, rdx
0x180015db7  jz      short loc_180015DBF
0x180015db9  mov     rdx, [rdx+10h]
0x180015dbd  jmp     short loc_180015DC6
0x180015dbf  lea     rdx, S2
0x180015dc6  xorps   xmm0, xmm0
0x180015dc9  movups  xmmword ptr [r14], xmm0
0x180015dcd  mov     [r14+10h], r15
0x180015dd1  mov     [r14+18h], r15
0x180015dd5  mov     r8, rsi
0x180015dd8  inc     r8
0x180015ddb  cmp     [rdx+r8*2], r15w
0x180015de0  jnz     short loc_180015DD8
0x180015de2  mov     rcx, r14
0x180015de5  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180015dea  nop
0x180015deb  mov     rdi, [rsp+130h+var_F8]
0x180015df0  test    rdi, rdi
0x180015df3  jz      short loc_180015E1D
0x180015df5  mov     eax, esi
0x180015df7  lock xadd [rdi+18h], eax
0x180015dfc  sub     eax, 1
0x180015dff  jnz     loc_180015E91
0x180015e05  nop
0x180015e06  call    WINRT_IMPL_GetProcessHeap
0x180015e0b  mov     rcx, rax; hHeap
0x180015e0e  mov     r8, rdi; lpMem
0x180015e11  xor     edx, edx; dwFlags
0x180015e13  call    WINRT_IMPL_HeapFree
0x180015e18  mov     [rsp+130h+var_F8], r15
0x180015e1d  cmp     [rsp+130h+var_108], r15
0x180015e22  jz      short loc_180015E2F
0x180015e24  lea     rcx, [rsp+130h+var_108]
0x180015e29  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180015e2e  nop
0x180015e2f  cmp     [rsp+130h+var_100], r15
0x180015e34  jz      short loc_180015E41
0x180015e36  lea     rcx, [rsp+130h+var_100]
0x180015e3b  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180015e40  nop
0x180015e41  cmp     [rsp+130h+lpMem], r15
0x180015e46  jz      short loc_180015E53
0x180015e48  lea     rcx, [rsp+130h+var_F0]
0x180015e4d  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180015e52  nop
0x180015e53  test    rbx, rbx
0x180015e56  jz      short loc_180015E76
0x180015e58  lock xadd [rbx+18h], esi
0x180015e5d  sub     esi, 1
0x180015e60  jnz     short loc_180015E9C
0x180015e62  nop
0x180015e63  call    WINRT_IMPL_GetProcessHeap
0x180015e68  mov     rcx, rax; hHeap
0x180015e6b  mov     r8, rbx; lpMem
0x180015e6e  xor     edx, edx; dwFlags
0x180015e70  call    WINRT_IMPL_HeapFree
0x180015e75  nop
0x180015e76  mov     rcx, r13
0x180015e79  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180015e7e  nop
0x180015e7f  mov     rcx, r12
0x180015e82  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180015e87  nop
0x180015e88  mov     rcx, [rbp+57h+var_C0]
0x180015e8c  jmp     loc_180015F46
0x180015e91  test    eax, eax
0x180015e93  jns     short loc_180015E18
0x180015e95  call    cs:__imp_abort
0x180015e9c  test    esi, esi
0x180015e9e  jns     short loc_180015E76
0x180015ea0  call    cs:__imp_abort
0x180015ea7  xorps   xmm0, xmm0
0x180015eaa  movups  xmmword ptr [r14], xmm0
0x180015eae  mov     [r14+10h], r15
0x180015eb2  mov     [r14+18h], r15
0x180015eb6  mov     rdi, [rbp+57h+var_C0]
0x180015eba  movups  xmm0, xmmword ptr [rdi]
0x180015ebd  movups  xmmword ptr [r14], xmm0
0x180015ec1  movups  xmm1, xmmword ptr [rdi+10h]
0x180015ec5  movups  xmmword ptr [r14+10h], xmm1
0x180015eca  mov     [rdi], r15w
0x180015ece  mov     [rdi+10h], r15
0x180015ed2  mov     qword ptr [rdi+18h], 7
0x180015eda  test    rax, rax
0x180015edd  jz      short loc_180015EEA
0x180015edf  lea     rcx, [rsp+130h+var_108]
0x180015ee4  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180015ee9  nop
0x180015eea  cmp     [rsp+130h+var_100], r15
0x180015eef  jz      short loc_180015EFC
0x180015ef1  lea     rcx, [rsp+130h+var_100]
0x180015ef6  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180015efb  nop
0x180015efc  cmp     [rsp+130h+lpMem], r15
0x180015f01  jz      short loc_180015F0E
0x180015f03  lea     rcx, [rsp+130h+var_F0]
0x180015f08  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180015f0d  nop
0x180015f0e  test    rbx, rbx
0x180015f11  jz      short loc_180015F31
0x180015f13  lock xadd [rbx+18h], esi
0x180015f18  sub     esi, 1
0x180015f1b  jnz     short loc_180015F6E
0x180015f1d  nop
0x180015f1e  call    WINRT_IMPL_GetProcessHeap
0x180015f23  mov     rcx, rax; hHeap
0x180015f26  mov     r8, rbx; lpMem
0x180015f29  xor     edx, edx; dwFlags
0x180015f2b  call    WINRT_IMPL_HeapFree
0x180015f30  nop
0x180015f31  mov     rcx, r13
  ... truncated ...
```
