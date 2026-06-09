# ??$call@AEAV_lambda_1_@?1??CreateWatcher@DeviceInformation@Enumeration@Devices@Windows@winrt@@SA@AEBUhstring@param@7@AEBU?$iterable@Uhstring@winrt@@@97@AEBW4DeviceInformationKind@4567@@Z@@?$factory_cache_entry@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateWatcher@DeviceInformation@Enumeration@Devices@Windows@2@SA@AEBUhstring@param@2@AEBU?$iterable@Uhstring@winrt@@@param@2@AEBW4DeviceInformationKind@6782@@Z@@Z

- ea: `0x18000bafc`
- end: `0x18000bc55`
- name: `??$call@AEAV_lambda_1_@?1??CreateWatcher@DeviceInformation@Enumeration@Devices@Windows@winrt@@SA@AEBUhstring@param@7@AEBU?$iterable@Uhstring@winrt@@@97@AEBW4DeviceInformationKind@4567@@Z@@?$factory_cache_entry@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateWatcher@DeviceInformation@Enumeration@Devices@Windows@2@SA@AEBUhstring@param@2@AEBU?$iterable@Uhstring@winrt@@@param@2@AEBW4DeviceInformationKind@6782@@Z@@Z`
- size: `345`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000e950`

## callees

- `0x180003b9d`
- `0x18000bafc`
- `0x18000bc5c`
- `0x18000d70c`
- `0x180011a4c`
- `0x180011e0c`
- `0x180013010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ___call_AEAV_lambda_1___1__CreateWatcher_DeviceInformation_Enumeration_Devices_Windows_winrt__SA_AEBUhstring_param_7_AEBU__iterable_Uhstring_winrt___97_AEBW4DeviceInformationKind_4567__Z____factory_cache_entry_UDeviceInformation_Enumeration_Devices_Windows_winrt__UIDeviceInformationStatics2_2345__impl_winrt__QEAA_A_PAEAV_lambda_1___1__CreateWatcher_DeviceInformation_Enumeration_Devices_Windows_2_SA_AEBUhstring_param_2_AEBU__iterable_Uhstring_winrt___param_2_AEBW4DeviceInformationKind_6782__Z__Z(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v5; // r8
  __int64 *v6; // rbx
  unsigned int v8; // [rsp+28h] [rbp-38h] BYREF
  const char *v9; // [rsp+30h] [rbp-30h]
  __int64 v10; // [rsp+38h] [rbp-28h]
  _DWORD *v11; // [rsp+40h] [rbp-20h] BYREF
  _DWORD v12[4]; // [rsp+48h] [rbp-18h] BYREF
  const wchar_t *v13; // [rsp+58h] [rbp-8h]
  __int64 *v14; // [rsp+80h] [rbp+20h] BYREF
  __int64 *v15; // [rsp+98h] [rbp+38h] BYREF

  v14 = a1;
  v12[0] = 1;
  v12[1] = 45;
  v13 = L"Windows.Devices.Enumeration.DeviceInformation";
  v11 = v12;
  v15 = 0;
  v8 = 6172;
  v9 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt/base.h";
  v10 = 0;
  winrt::impl::get_runtime_activation_factory_impl<0>(
    &v14,
    &v11,
    (__int64)winrt::impl::guid_v<winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>,
    (__int64)&v15);
  if ( (int)v14 < 0 )
    winrt::throw_hresult((unsigned int)v14, &v8, v5);
  v6 = v15;
  v14 = v15;
  if ( v15
    && (v15 = 0,
        (*(void (__fastcall **)(__int64 *, __int64 *, __int64 **))*v6)(
          v6,
          &winrt::impl::guid_v<winrt::impl::IAgileObject>,
          &v15),
        v15) )
  {
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((__int64 *)&v15);
    v15 = &qword_18001B948;
    _InterlockedIncrement64(&qword_18001B948);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>,
            (signed __int64)v6,
            0) )
    {
      v6 = 0;
      v14 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_18001B950);
    }
    `winrt::Windows::Devices::Enumeration::DeviceInformation::CreateWatcher'::`2'::_lambda_1_::operator()(
      a3,
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>);
    _InterlockedDecrement64(&qword_18001B948);
  }
  else
  {
    `winrt::Windows::Devices::Enumeration::DeviceInformation::CreateWatcher'::`2'::_lambda_1_::operator()(a3, a2, &v14);
  }
  if ( v6 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((__int64 *)&v14);
  return a2;
}

```

## disassembly

```asm
0x18000bafc  mov     [rsp-18h+arg_8], rbx
0x18000bb01  mov     [rsp-18h+arg_0], rcx
0x18000bb06  push    rbp
0x18000bb07  push    rsi
0x18000bb08  push    rdi
0x18000bb09  mov     rbp, rsp
0x18000bb0c  sub     rsp, 60h
0x18000bb10  mov     rsi, r8
0x18000bb13  mov     rdi, rdx
0x18000bb16  mov     [rbp+var_18], 1
0x18000bb1d  mov     [rbp+var_14], 2Dh ; '-'
0x18000bb24  lea     rax, aWindowsDevices; "Windows.Devices.Enumeration.DeviceInfor"...
0x18000bb2b  mov     [rbp+var_8], rax
0x18000bb2f  lea     rax, [rbp+var_18]
0x18000bb33  mov     [rbp+var_20], rax
0x18000bb37  mov     [rbp+arg_18], 0
0x18000bb3f  mov     [rbp+var_38], 181Ch
0x18000bb46  lea     rax, aOnecoreuapInte_1; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x18000bb4d  mov     [rbp+var_30], rax
0x18000bb51  mov     [rbp+var_28], 0
0x18000bb59  lea     r9, [rbp+arg_18]
0x18000bb5d  lea     r8, ??$guid_v@UIDeviceInformationStatics2@Enumeration@Devices@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>
0x18000bb64  lea     rdx, [rbp+var_20]
0x18000bb68  lea     rcx, [rbp+arg_0]
0x18000bb6c  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x18000bb71  mov     ecx, dword ptr [rbp+arg_0]
0x18000bb74  test    ecx, ecx
0x18000bb76  js      loc_18000BC4B
0x18000bb7c  mov     rbx, [rbp+arg_18]
0x18000bb80  mov     [rbp+arg_0], rbx
0x18000bb84  test    rbx, rbx
0x18000bb87  jz      loc_18000BC1A
0x18000bb8d  mov     [rbp+arg_18], 0
0x18000bb95  mov     rax, [rbx]
0x18000bb98  lea     r8, [rbp+arg_18]
0x18000bb9c  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18000bba3  mov     rcx, rbx
0x18000bba6  mov     rax, [rax]
0x18000bba9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bbae  mov     rax, [rbp+arg_18]
0x18000bbb2  mov     [rbp+arg_18], rax
0x18000bbb6  test    rax, rax
0x18000bbb9  jz      short loc_18000BC1A
0x18000bbbb  lea     rcx, [rbp+arg_18]
0x18000bbbf  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000bbc4  lea     rax, qword_18001B948
0x18000bbcb  mov     [rbp+arg_18], rax
0x18000bbcf  lock inc cs:qword_18001B948
0x18000bbd7  xor     eax, eax
0x18000bbd9  lock cmpxchg cs:??$factory_cache_entry_v@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@impl@winrt@@3U?$factory_cache_entry@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@12@A, rbx; factory_cache_entry<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>::winrt::factory_cache_entry<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2> winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>
0x18000bbe2  jnz     short loc_18000BBFD
0x18000bbe4  xor     ebx, ebx
0x18000bbe6  mov     [rbp+arg_0], rbx
0x18000bbea  lea     rdx, stru_18001B950; ListEntry
0x18000bbf1  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18000bbf8  call    WINRT_IMPL_InterlockedPushEntrySList
0x18000bbfd  lea     r8, ??$factory_cache_entry_v@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@impl@winrt@@3U?$factory_cache_entry@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@12@A; factory_cache_entry<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>::winrt::factory_cache_entry<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2> winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>
0x18000bc04  mov     rdx, rdi
0x18000bc07  mov     rcx, rsi
0x18000bc0a  call    ??R_lambda_1_@?1??CreateWatcher@DeviceInformation@Enumeration@Devices@Windows@winrt@@SA@AEBUhstring@param@6@AEBU?$iterable@Uhstring@winrt@@@86@AEBW4DeviceInformationKind@3456@@Z@QEBA@AEBUIDeviceInformationStatics2@3456@@Z; `winrt::Windows::Devices::Enumeration::DeviceInformation::CreateWatcher(winrt::param::hstring const &,winrt::param::iterable<winrt::hstring> const &,winrt::Windows::Devices::Enumeration::DeviceInformationKind const &)'::`2'::_lambda_1_::operator()(winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2 const &)
0x18000bc0f  nop
0x18000bc10  lock dec cs:qword_18001B948
0x18000bc18  jmp     short loc_18000BC2A
0x18000bc1a  lea     r8, [rbp+arg_0]
0x18000bc1e  mov     rdx, rdi
0x18000bc21  mov     rcx, rsi
0x18000bc24  call    ??R_lambda_1_@?1??CreateWatcher@DeviceInformation@Enumeration@Devices@Windows@winrt@@SA@AEBUhstring@param@6@AEBU?$iterable@Uhstring@winrt@@@86@AEBW4DeviceInformationKind@3456@@Z@QEBA@AEBUIDeviceInformationStatics2@3456@@Z; `winrt::Windows::Devices::Enumeration::DeviceInformation::CreateWatcher(winrt::param::hstring const &,winrt::param::iterable<winrt::hstring> const &,winrt::Windows::Devices::Enumeration::DeviceInformationKind const &)'::`2'::_lambda_1_::operator()(winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2 const &)
0x18000bc29  nop
0x18000bc2a  test    rbx, rbx
0x18000bc2d  jz      short loc_18000BC38
0x18000bc2f  lea     rcx, [rbp+arg_0]
0x18000bc33  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000bc38  mov     rax, rdi
0x18000bc3b  mov     rbx, [rsp+60h+arg_8]
0x18000bc43  add     rsp, 60h
0x18000bc47  pop     rdi
0x18000bc48  pop     rsi
0x18000bc49  pop     rbp
0x18000bc4a  retn
0x18000bc4b  lea     rdx, [rbp+var_38]
0x18000bc4f  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
