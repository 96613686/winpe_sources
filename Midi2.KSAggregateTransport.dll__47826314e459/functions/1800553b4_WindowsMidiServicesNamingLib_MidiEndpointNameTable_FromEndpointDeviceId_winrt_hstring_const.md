# WindowsMidiServicesNamingLib::MidiEndpointNameTable::FromEndpointDeviceId(winrt::hstring const &)

- ea: `0x1800553b4`
- end: `0x180055790`
- name: `?FromEndpointDeviceId@MidiEndpointNameTable@WindowsMidiServicesNamingLib@@SA?AV?$shared_ptr@VMidiEndpointNameTable@WindowsMidiServicesNamingLib@@@std@@AEBUhstring@winrt@@@Z`
- size: `988`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001dd50`

## callees

- `0x180005070`
- `0x180005e16`
- `0x180005f44`
- `0x180010b94`
- `0x180012c1c`
- `0x180013f60`
- `0x180014d2c`
- `0x180014ff4`
- `0x1800154d4`
- `0x180019094`
- `0x180019b34`
- `0x18001a124`
- `0x18001a4a8`
- `0x18002215c`
- `0x1800537b0`
- `0x1800553b4`
- `0x180055798`
- `0x180056d10`
- `0x18005e010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18005563b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18005563b`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
_QWORD *__fastcall WindowsMidiServicesNamingLib::MidiEndpointNameTable::FromEndpointDeviceId(_QWORD *a1, __int64 *a2)
{
  _QWORD *v3; // r15
  __int64 v4; // rbx
  int v5; // eax
  __int64 *v6; // rdi
  __int64 *v7; // rax
  struct winrt::impl::shared_hstring_header *v8; // rax
  unsigned int v9; // edx
  struct winrt::impl::shared_hstring_header *v10; // rax
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // r9
  struct winrt::impl::shared_hstring_header *v14; // rdi
  _OWORD *v15; // rcx
  __int64 *v16; // rsi
  __int64 v18; // [rsp+30h] [rbp-88h] BYREF
  __int64 v19; // [rsp+38h] [rbp-80h] BYREF
  struct winrt::impl::shared_hstring_header *v20; // [rsp+40h] [rbp-78h] BYREF
  char v21; // [rsp+48h] [rbp-70h]
  __int128 pv; // [rsp+50h] [rbp-68h] BYREF
  __int64 v23; // [rsp+60h] [rbp-58h]
  const wchar_t *v24; // [rsp+68h] [rbp-50h]
  __int64 *v25; // [rsp+70h] [rbp-48h] BYREF
  __int64 v26; // [rsp+80h] [rbp-38h] BYREF
  __int64 *v28; // [rsp+D0h] [rbp+18h] BYREF
  __int64 v29; // [rsp+D8h] [rbp+20h] BYREF

  v3 = a1;
  pv = 0;
  v23 = 0;
  winrt::single_threaded_vector<winrt::hstring,std::allocator<winrt::hstring>>(&v29, &pv);
  std::vector<winrt::hstring>::~vector<winrt::hstring>(&pv);
  *((_QWORD *)&pv + 1) = 0x2A00000001LL;
  v24 = L"{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} 960";
  *(_QWORD *)&pv = (char *)&pv + 8;
  winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::Append(
    &v29,
    &pv);
  v4 = 0;
  v18 = 0;
  winrt::param::async_iterable<winrt::hstring>::async_iterable<winrt::hstring>(&v20, &v29);
  try
  {
    v26 = *a2;
    *(_QWORD *)&pv = &v26;
    *((_QWORD *)&pv + 1) = &v20;
    v25 = &qword_180096AE8;
    _InterlockedIncrement64(&qword_180096AE8);
    if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics> )
    {
      v28 = 0;
      LODWORD(pv) = 792;
      *((_QWORD *)&pv + 1) = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\windows.devices.enumeration.h";
      v23 = 0;
      v5 = (*(__int64 (__fastcall **)(__int64, __int64, struct winrt::impl::shared_hstring_header *, __int64 **))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics> + 56LL))(
             winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics>,
             v26,
             v20,
             &v28);
      if ( v5 < 0 )
        winrt::throw_hresult((unsigned int)v5, &pv);
      v6 = v28;
      _InterlockedDecrement64(&qword_180096AE8);
    }
    else
    {
      _InterlockedDecrement64(&qword_180096AE8);
      ___call_AEAV_lambda_1___1__CreateFromIdAsync_DeviceInformation_Enumeration_Devices_Windows_winrt__SA_AEBUhstring_param_7_AEBU__async_iterable_Uhstring_winrt___97__Z____factory_cache_entry_UDeviceInformation_Enumeration_Devices_Windows_winrt__UIDeviceInformationStatics_2345__impl_winrt__QEAA_A_PAEAV_lambda_1___1__CreateFromIdAsync_DeviceInformation_Enumeration_Devices_Windows_2_SA_AEBUhstring_param_2_AEBU__async_iterable_Uhstring_winrt___param_2__Z__Z(
        0,
        &v28,
        &pv);
      v6 = v28;
    }
    v7 = (__int64 *)winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Devices::Enumeration::DeviceInformation>,winrt::Windows::Devices::Enumeration::DeviceInformation>::get(
                      &v28,
                      &v19);
    if ( &v18 != v7 )
    {
      v4 = *v7;
      *v7 = 0;
      v18 = v4;
    }
    if ( v19 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v19);
    if ( v6 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v28);
    if ( v21 )
    {
      v8 = v20;
    }
    else
    {
      v8 = 0;
      v20 = 0;
    }
    if ( v8 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v20);
  }
  catch ( winrt::hresult_error )
  {
    v3 = a1;
    v4 = v18;
  }
  v28 = 0;
  if ( (unsigned __int8)winrt::Windows::Foundation::operator==(&v18, &v28) )
    goto LABEL_31;
  v28 = &v19;
  v19 = v4;
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 8LL))(v4);
  v10 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)0x2A, v9);
  v14 = v10;
  v15 = (_OWORD *)((char *)v10 + 28);
  if ( v10 == (struct winrt::impl::shared_hstring_header *)-28LL )
  {
    *(_DWORD *)_o__errno(v15, v11, v12, v13) = 22;
    invalid_parameter_noinfo();
  }
  else
  {
    *v15 = *(_OWORD *)L"{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} 960";
    *(_OWORD *)((char *)v10 + 44) = *(_OWORD *)L"A-11FA-4BD0-9D2C-6B7780CD80AD} 960";
    *(_OWORD *)((char *)v10 + 60) = *(_OWORD *)L"BD0-9D2C-6B7780CD80AD} 960";
    *(_OWORD *)((char *)v10 + 76) = *(_OWORD *)L"-6B7780CD80AD} 960";
    *(_OWORD *)((char *)v10 + 92) = *(_OWORD *)L"D80AD} 960";
    *((_DWORD *)v10 + 27) = *(_DWORD *)L"60";
  }
  v20 = v14;
  WindowsMidiServicesInternal::SafeGetSwdBinaryPropertyFromDeviceInformation(&v28, &v20, &v19);
  v25 = 0;
  if ( (unsigned __int8)winrt::Windows::Foundation::operator==(&v28, &v25) )
  {
    if ( v28 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v28);
LABEL_31:
    v16 = (__int64 *)operator new(0x48u);
    v28 = v16;
    *(_OWORD *)v16 = 0;
    *((_DWORD *)v16 + 2) = 1;
    *((_DWORD *)v16 + 3) = 1;
    *v16 = (__int64)&std::_Ref_count_obj2<WindowsMidiServicesNamingLib::MidiEndpointNameTable>::`vftable';
    *((_OWORD *)v16 + 1) = 0;
    *((_OWORD *)v16 + 2) = 0;
    *((_OWORD *)v16 + 3) = 0;
    v16[8] = 0;
    WindowsMidiServicesNamingLib::MidiEndpointNameTable::MidiEndpointNameTable((WindowsMidiServicesNamingLib::MidiEndpointNameTable *)(v16 + 2));
    *v3 = v16 + 2;
    v3[1] = v16;
    goto LABEL_32;
  }
  winrt::impl::consume_Windows_Foundation_IReferenceArray<winrt::Windows::Foundation::IReferenceArray<unsigned char>,unsigned char>::Value(
    &v28,
    &pv);
  WindowsMidiServicesNamingLib::MidiEndpointNameTable::FromPropertyData(v3, &pv);
  if ( (_QWORD)pv )
    CoTaskMemFree_0((LPVOID)pv);
  if ( v28 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v28);
LABEL_32:
  if ( v4 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v18);
  if ( v29 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v29);
  return v3;
}

```

## disassembly

```asm
0x1800553b4  mov     rax, rsp
0x1800553b7  mov     [rax+10h], rbx
0x1800553bb  mov     [rax+8], rcx
0x1800553bf  push    rsi
0x1800553c0  push    rdi
0x1800553c1  push    r15
0x1800553c3  sub     rsp, 0A0h
0x1800553ca  mov     rdi, rdx
0x1800553cd  mov     r15, rcx
0x1800553d0  xorps   xmm0, xmm0
0x1800553d3  movdqu  xmmword ptr [rax-68h], xmm0
0x1800553d8  mov     qword ptr [rax-58h], 0
0x1800553e0  lea     rdx, [rax-68h]
0x1800553e4  lea     rcx, [rax+20h]
0x1800553e8  call    ??$single_threaded_vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@winrt@@YA?AU?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@0@$$QEAV?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@@Z; winrt::single_threaded_vector<winrt::hstring,std::allocator<winrt::hstring>>(std::vector<winrt::hstring> &&)
0x1800553ed  nop
0x1800553ee  lea     rcx, [rsp+0B8h+pv]
0x1800553f3  call    ??1?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@QEAA@XZ; std::vector<winrt::hstring>::~vector<winrt::hstring>(void)
0x1800553f8  mov     dword ptr [rsp+0B8h+var_60], 1
0x180055400  mov     dword ptr [rsp+0B8h+var_60+4], 2Ah ; '*'
0x180055408  lea     rax, a3f114a6a11fa4b; "{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} "...
0x18005540f  mov     [rsp+0B8h+var_50], rax
0x180055414  lea     rax, [rsp+0B8h+var_60]
0x180055419  mov     [rsp+0B8h+pv], rax
0x18005541e  lea     rdx, [rsp+0B8h+pv]
0x180055423  lea     rcx, [rsp+0B8h+arg_18]
0x18005542b  call    ?Append@?$consume_Windows_Foundation_Collections_IVector@U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@winrt@@Uhstring@5@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::Append(winrt::param::hstring const &)
0x180055430  xor     ebx, ebx
0x180055432  mov     [rsp+0B8h+var_88], rbx
0x180055437  lea     rdx, [rsp+0B8h+arg_18]
0x18005543f  lea     rcx, [rsp+0B8h+var_78]
0x180055444  call    ??$?0U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@winrt@@$0A@@?$async_iterable@Uhstring@winrt@@@param@winrt@@QEAA@AEBU?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@2@@Z; winrt::param::async_iterable<winrt::hstring>::async_iterable<winrt::hstring>(winrt::Windows::Foundation::Collections::IVector<winrt::hstring> const &)
0x180055449  nop
0x18005544a  mov     rax, [rdi]
0x18005544d  mov     [rsp+0B8h+var_38], rax
0x180055455  lea     rax, [rsp+0B8h+var_38]
0x18005545d  mov     [rsp+0B8h+pv], rax
0x180055462  lea     rax, [rsp+0B8h+var_78]
0x180055467  mov     [rsp+0B8h+var_60], rax
0x18005546c  lea     rax, qword_180096AE8
0x180055473  mov     [rsp+0B8h+var_48], rax
0x180055478  lock inc cs:qword_180096AE8
0x180055480  mov     rcx, cs:??$factory_cache_entry_v@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics@2345@@12@A; factory_cache_entry<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics>::winrt::factory_cache_entry<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics>
0x180055487  test    rcx, rcx
0x18005548a  jz      short loc_1800554F0
0x18005548c  mov     [rsp+0B8h+arg_10], rbx
0x180055494  mov     dword ptr [rsp+0B8h+pv], 318h
0x18005549c  lea     rax, aOnecoreuapInte_6; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x1800554a3  mov     [rsp+0B8h+var_60], rax
0x1800554a8  mov     [rsp+0B8h+var_58], rbx
0x1800554ad  mov     rax, [rcx]
0x1800554b0  lea     r9, [rsp+0B8h+arg_10]
0x1800554b8  mov     r8, [rsp+0B8h+var_78]
0x1800554bd  mov     rdx, [rsp+0B8h+var_38]
0x1800554c5  mov     rax, [rax+38h]
0x1800554c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800554ce  test    eax, eax
0x1800554d0  js      loc_180055782
0x1800554d6  mov     rdi, [rsp+0B8h+arg_10]
0x1800554de  mov     [rsp+0B8h+arg_10], rdi
0x1800554e6  lock dec cs:qword_180096AE8
0x1800554ee  jmp     short loc_180055512
0x1800554f0  lock dec cs:qword_180096AE8
0x1800554f8  lea     r8, [rsp+0B8h+pv]
0x1800554fd  lea     rdx, [rsp+0B8h+arg_10]
0x180055505  call    ??$call@AEAV_lambda_1_@?1??CreateFromIdAsync@DeviceInformation@Enumeration@Devices@Windows@winrt@@SA@AEBUhstring@param@7@AEBU?$async_iterable@Uhstring@winrt@@@97@@Z@@?$factory_cache_entry@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateFromIdAsync@DeviceInformation@Enumeration@Devices@Windows@2@SA@AEBUhstring@param@2@AEBU?$async_iterable@Uhstring@winrt@@@param@2@@Z@@Z
0x18005550a  mov     rdi, [rsp+0B8h+arg_10]
0x180055512  lea     rdx, [rsp+0B8h+var_80]
0x180055517  lea     rcx, [rsp+0B8h+arg_10]
0x18005551f  call    ?get@?$consume_Windows_Foundation_IAsyncOperation@U?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@UDeviceInformation@Enumeration@Devices@34@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Devices::Enumeration::DeviceInformation>,winrt::Windows::Devices::Enumeration::DeviceInformation>::get(void)
0x180055524  lea     rcx, [rsp+0B8h+var_88]
0x180055529  cmp     rcx, rax
0x18005552c  jz      short loc_18005553D
0x18005552e  mov     rbx, [rax]
0x180055531  mov     qword ptr [rax], 0
0x180055538  mov     [rsp+0B8h+var_88], rbx
0x18005553d  cmp     [rsp+0B8h+var_80], 0
0x180055543  jz      short loc_180055550
0x180055545  lea     rcx, [rsp+0B8h+var_80]
0x18005554a  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18005554f  nop
0x180055550  test    rdi, rdi
0x180055553  jz      short loc_180055563
0x180055555  lea     rcx, [rsp+0B8h+arg_10]
0x18005555d  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180055562  nop
0x180055563  cmp     [rsp+0B8h+var_70], 0
0x180055568  jnz     short loc_180055573
0x18005556a  xor     eax, eax
0x18005556c  mov     [rsp+0B8h+var_78], rax
0x180055571  jmp     short loc_180055578
0x180055573  mov     rax, [rsp+0B8h+var_78]
0x180055578  test    rax, rax
0x18005557b  jz      short loc_180055588
0x18005557d  lea     rcx, [rsp+0B8h+var_78]
0x180055582  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180055587  nop
0x180055588  jmp     short loc_180055597
0x18005558a  mov     r15, [rsp+0B8h+arg_0]
0x180055592  mov     rbx, [rsp+0B8h+var_88]
0x180055597  mov     [rsp+0B8h+arg_10], 0
0x1800555a3  lea     rdx, [rsp+0B8h+arg_10]
0x1800555ab  lea     rcx, [rsp+0B8h+var_88]
0x1800555b0  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x1800555b5  test    al, al
0x1800555b7  jnz     loc_1800556EB
0x1800555bd  lea     rax, [rsp+0B8h+var_80]
0x1800555c2  mov     [rsp+0B8h+arg_10], rax
0x1800555ca  mov     [rsp+0B8h+var_80], rbx
0x1800555cf  test    rbx, rbx
0x1800555d2  jz      short loc_1800555E4
0x1800555d4  mov     rax, [rbx]
0x1800555d7  mov     rcx, rbx
0x1800555da  mov     rax, [rax+8]
0x1800555de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800555e3  nop
0x1800555e4  mov     ecx, 2Ah ; '*'; this
0x1800555e9  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x1800555ee  mov     rdi, rax
0x1800555f1  lea     rcx, [rax+1Ch]
0x1800555f5  test    rcx, rcx
0x1800555f8  jz      short loc_18005563B
0x1800555fa  movaps  xmm0, xmmword ptr cs:a3f114a6a11fa4b; "{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} "...
0x180055601  movups  xmmword ptr [rcx], xmm0
0x180055604  movaps  xmm1, xmmword ptr cs:a3f114a6a11fa4b+10h; "A-11FA-4BD0-9D2C-6B7780CD80AD} 960"
0x18005560b  movups  xmmword ptr [rcx+10h], xmm1
0x18005560f  movaps  xmm0, xmmword ptr cs:a3f114a6a11fa4b+20h; "BD0-9D2C-6B7780CD80AD} 960"
0x180055616  movups  xmmword ptr [rcx+20h], xmm0
0x18005561a  movaps  xmm1, xmmword ptr cs:a3f114a6a11fa4b+30h; "-6B7780CD80AD} 960"
0x180055621  movups  xmmword ptr [rcx+30h], xmm1
0x180055625  movaps  xmm0, xmmword ptr cs:a3f114a6a11fa4b+40h; "D80AD} 960"
0x18005562c  movups  xmmword ptr [rcx+40h], xmm0
0x180055630  mov     eax, dword ptr cs:a3f114a6a11fa4b+50h; "60"
0x180055636  mov     [rcx+50h], eax
0x180055639  jmp     short loc_18005564C
0x18005563b  call    cs:__imp__o__errno
0x180055641  mov     dword ptr [rax], 16h
0x180055647  call    _invalid_parameter_noinfo
0x18005564c  mov     [rsp+0B8h+var_78], rdi
0x180055651  lea     r8, [rsp+0B8h+var_80]
0x180055656  lea     rdx, [rsp+0B8h+var_78]
0x18005565b  lea     rcx, [rsp+0B8h+arg_10]
0x180055663  call    ?SafeGetSwdBinaryPropertyFromDeviceInformation@WindowsMidiServicesInternal@@YA?AU?$IReferenceArray@E@Foundation@Windows@winrt@@Uhstring@5@UDeviceInformation@Enumeration@Devices@45@@Z; WindowsMidiServicesInternal::SafeGetSwdBinaryPropertyFromDeviceInformation(winrt::hstring,winrt::Windows::Devices::Enumeration::DeviceInformation)
0x180055668  nop
0x180055669  mov     [rsp+0B8h+var_48], 0
0x180055672  lea     rdx, [rsp+0B8h+var_48]
0x180055677  lea     rcx, [rsp+0B8h+arg_10]
0x18005567f  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x180055684  test    al, al
0x180055686  jnz     short loc_1800556D3
0x180055688  lea     rdx, [rsp+0B8h+pv]
0x18005568d  lea     rcx, [rsp+0B8h+arg_10]
0x180055695  call    ?Value@?$consume_Windows_Foundation_IReferenceArray@U?$IReferenceArray@E@Foundation@Windows@winrt@@E@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IReferenceArray<winrt::Windows::Foundation::IReferenceArray<uchar>,uchar>::Value(void)
0x18005569a  nop
0x18005569b  lea     rdx, [rsp+0B8h+pv]
0x1800556a0  mov     rcx, r15
0x1800556a3  call    ?FromPropertyData@MidiEndpointNameTable@WindowsMidiServicesNamingLib@@SA?AV?$shared_ptr@VMidiEndpointNameTable@WindowsMidiServicesNamingLib@@@std@@AEBU?$com_array@E@winrt@@@Z; WindowsMidiServicesNamingLib::MidiEndpointNameTable::FromPropertyData(winrt::com_array<uchar> const &)
0x1800556a8  nop
0x1800556a9  mov     rcx, [rsp+0B8h+pv]; pv
0x1800556ae  test    rcx, rcx
0x1800556b1  jz      short loc_1800556B9
0x1800556b3  call    CoTaskMemFree_0
0x1800556b8  nop
0x1800556b9  cmp     [rsp+0B8h+arg_10], 0
0x1800556c2  jz      short loc_180055743
0x1800556c4  lea     rcx, [rsp+0B8h+arg_10]
0x1800556cc  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800556d1  jmp     short loc_180055743
0x1800556d3  cmp     [rsp+0B8h+arg_10], 0
0x1800556dc  jz      short loc_1800556EB
0x1800556de  lea     rcx, [rsp+0B8h+arg_10]
0x1800556e6  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800556eb  mov     ecx, 48h ; 'H'; Size
0x1800556f0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800556f5  mov     rsi, rax
0x1800556f8  mov     [rsp+0B8h+arg_10], rax
0x180055700  xorps   xmm0, xmm0
0x180055703  movups  xmmword ptr [rax], xmm0
0x180055706  mov     dword ptr [rax+8], 1
0x18005570d  mov     dword ptr [rax+0Ch], 1
0x180055714  lea     rax, ??_7?$_Ref_count_obj2@VMidiEndpointNameTable@WindowsMidiServicesNamingLib@@@std@@6B@; const std::_Ref_count_obj2<WindowsMidiServicesNamingLib::MidiEndpointNameTable>::`vftable'
0x18005571b  mov     [rsi], rax
0x18005571e  lea     rdi, [rsi+10h]
0x180055722  xor     eax, eax
0x180055724  movups  xmmword ptr [rdi], xmm0
0x180055727  movups  xmmword ptr [rdi+10h], xmm0
0x18005572b  movups  xmmword ptr [rdi+20h], xmm0
0x18005572f  mov     [rdi+30h], rax
0x180055733  mov     rcx, rdi; this
0x180055736  call    ??0MidiEndpointNameTable@WindowsMidiServicesNamingLib@@QEAA@XZ; WindowsMidiServicesNamingLib::MidiEndpointNameTable::MidiEndpointNameTable(void)
0x18005573b  nop
0x18005573c  mov     [r15], rdi
0x18005573f  mov     [r15+8], rsi
0x180055743  test    rbx, rbx
0x180055746  jz      short loc_180055753
0x180055748  lea     rcx, [rsp+0B8h+var_88]
0x18005574d  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180055752  nop
0x180055753  cmp     [rsp+0B8h+arg_18], 0
0x18005575c  jz      short loc_18005576B
0x18005575e  lea     rcx, [rsp+0B8h+arg_18]
0x180055766  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18005576b  mov     rax, r15
0x18005576e  mov     rbx, [rsp+0B8h+arg_8]
0x180055776  add     rsp, 0A0h
0x18005577d  pop     r15
0x18005577f  pop     rdi
0x180055780  pop     rsi
0x180055781  retn
0x180055782  lea     rdx, [rsp+0B8h+pv]
0x180055787  mov     ecx, eax
0x180055789  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
