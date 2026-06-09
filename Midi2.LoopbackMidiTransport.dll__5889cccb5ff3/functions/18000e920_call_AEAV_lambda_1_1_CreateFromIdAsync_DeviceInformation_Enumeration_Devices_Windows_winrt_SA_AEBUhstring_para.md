# ??$call@AEAV_lambda_1_@?1??CreateFromIdAsync@DeviceInformation@Enumeration@Devices@Windows@winrt@@SA@AEBUhstring@param@7@AEBU?$async_iterable@Uhstring@winrt@@@97@AEBW4DeviceInformationKind@4567@@Z@@?$factory_cache_entry@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateFromIdAsync@DeviceInformation@Enumeration@Devices@Windows@2@SA@AEBUhstring@param@2@AEBU?$async_iterable@Uhstring@winrt@@@param@2@AEBW4DeviceInformationKind@6782@@Z@@Z

- ea: `0x18000e920`
- end: `0x18000ea79`
- name: `??$call@AEAV_lambda_1_@?1??CreateFromIdAsync@DeviceInformation@Enumeration@Devices@Windows@winrt@@SA@AEBUhstring@param@7@AEBU?$async_iterable@Uhstring@winrt@@@97@AEBW4DeviceInformationKind@4567@@Z@@?$factory_cache_entry@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateFromIdAsync@DeviceInformation@Enumeration@Devices@Windows@2@SA@AEBUhstring@param@2@AEBU?$async_iterable@Uhstring@winrt@@@param@2@AEBW4DeviceInformationKind@6782@@Z@@Z`
- size: `345`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180011018`

## callees

- `0x1800051fd`
- `0x18000e920`
- `0x18000ea80`
- `0x1800100a8`
- `0x1800145d8`
- `0x180014974`
- `0x180032010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ___call_AEAV_lambda_1___1__CreateFromIdAsync_DeviceInformation_Enumeration_Devices_Windows_winrt__SA_AEBUhstring_param_7_AEBU__async_iterable_Uhstring_winrt___97_AEBW4DeviceInformationKind_4567__Z____factory_cache_entry_UDeviceInformation_Enumeration_Devices_Windows_winrt__UIDeviceInformationStatics2_2345__impl_winrt__QEAA_A_PAEAV_lambda_1___1__CreateFromIdAsync_DeviceInformation_Enumeration_Devices_Windows_2_SA_AEBUhstring_param_2_AEBU__async_iterable_Uhstring_winrt___param_2_AEBW4DeviceInformationKind_6782__Z__Z(
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
    v15 = &qword_18005FA68;
    _InterlockedIncrement64(&qword_18005FA68);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>,
            (signed __int64)v6,
            0) )
    {
      v6 = 0;
      v14 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &ListEntry);
    }
    `winrt::Windows::Devices::Enumeration::DeviceInformation::CreateFromIdAsync'::`2'::_lambda_1_::operator()(
      a3,
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>);
    _InterlockedDecrement64(&qword_18005FA68);
  }
  else
  {
    `winrt::Windows::Devices::Enumeration::DeviceInformation::CreateFromIdAsync'::`2'::_lambda_1_::operator()(
      a3,
      a2,
      &v14);
  }
  if ( v6 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((__int64 *)&v14);
  return a2;
}

```

## disassembly

```asm
0x18000e920  mov     [rsp-18h+arg_8], rbx
0x18000e925  mov     [rsp-18h+arg_0], rcx
0x18000e92a  push    rbp
0x18000e92b  push    rsi
0x18000e92c  push    rdi
0x18000e92d  mov     rbp, rsp
0x18000e930  sub     rsp, 60h
0x18000e934  mov     rsi, r8
0x18000e937  mov     rdi, rdx
0x18000e93a  mov     [rbp+var_18], 1
0x18000e941  mov     [rbp+var_14], 2Dh ; '-'
0x18000e948  lea     rax, aWindowsDevices; "Windows.Devices.Enumeration.DeviceInfor"...
0x18000e94f  mov     [rbp+var_8], rax
0x18000e953  lea     rax, [rbp+var_18]
0x18000e957  mov     [rbp+var_20], rax
0x18000e95b  mov     [rbp+arg_18], 0
0x18000e963  mov     [rbp+var_38], 181Ch
0x18000e96a  lea     rax, aOnecoreuapInte_0; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x18000e971  mov     [rbp+var_30], rax
0x18000e975  mov     [rbp+var_28], 0
0x18000e97d  lea     r9, [rbp+arg_18]
0x18000e981  lea     r8, ??$guid_v@UIDeviceInformationStatics2@Enumeration@Devices@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>
0x18000e988  lea     rdx, [rbp+var_20]
0x18000e98c  lea     rcx, [rbp+arg_0]
0x18000e990  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x18000e995  mov     ecx, dword ptr [rbp+arg_0]
0x18000e998  test    ecx, ecx
0x18000e99a  js      loc_18000EA6F
0x18000e9a0  mov     rbx, [rbp+arg_18]
0x18000e9a4  mov     [rbp+arg_0], rbx
0x18000e9a8  test    rbx, rbx
0x18000e9ab  jz      loc_18000EA3E
0x18000e9b1  mov     [rbp+arg_18], 0
0x18000e9b9  mov     rax, [rbx]
0x18000e9bc  lea     r8, [rbp+arg_18]
0x18000e9c0  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18000e9c7  mov     rcx, rbx
0x18000e9ca  mov     rax, [rax]
0x18000e9cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e9d2  mov     rax, [rbp+arg_18]
0x18000e9d6  mov     [rbp+arg_18], rax
0x18000e9da  test    rax, rax
0x18000e9dd  jz      short loc_18000EA3E
0x18000e9df  lea     rcx, [rbp+arg_18]
0x18000e9e3  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000e9e8  lea     rax, qword_18005FA68
0x18000e9ef  mov     [rbp+arg_18], rax
0x18000e9f3  lock inc cs:qword_18005FA68
0x18000e9fb  xor     eax, eax
0x18000e9fd  lock cmpxchg cs:??$factory_cache_entry_v@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@impl@winrt@@3U?$factory_cache_entry@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@12@A, rbx; factory_cache_entry<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>::winrt::factory_cache_entry<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2> winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>
0x18000ea06  jnz     short loc_18000EA21
0x18000ea08  xor     ebx, ebx
0x18000ea0a  mov     [rbp+arg_0], rbx
0x18000ea0e  lea     rdx, ListEntry; ListEntry
0x18000ea15  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18000ea1c  call    WINRT_IMPL_InterlockedPushEntrySList
0x18000ea21  lea     r8, ??$factory_cache_entry_v@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@impl@winrt@@3U?$factory_cache_entry@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@12@A; factory_cache_entry<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>::winrt::factory_cache_entry<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2> winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>
0x18000ea28  mov     rdx, rdi
0x18000ea2b  mov     rcx, rsi
0x18000ea2e  call    ??R_lambda_1_@?1??CreateFromIdAsync@DeviceInformation@Enumeration@Devices@Windows@winrt@@SA@AEBUhstring@param@6@AEBU?$async_iterable@Uhstring@winrt@@@86@AEBW4DeviceInformationKind@3456@@Z@QEBA@AEBUIDeviceInformationStatics2@3456@@Z; `winrt::Windows::Devices::Enumeration::DeviceInformation::CreateFromIdAsync(winrt::param::hstring const &,winrt::param::async_iterable<winrt::hstring> const &,winrt::Windows::Devices::Enumeration::DeviceInformationKind const &)'::`2'::_lambda_1_::operator()(winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2 const &)
0x18000ea33  nop
0x18000ea34  lock dec cs:qword_18005FA68
0x18000ea3c  jmp     short loc_18000EA4E
0x18000ea3e  lea     r8, [rbp+arg_0]
0x18000ea42  mov     rdx, rdi
0x18000ea45  mov     rcx, rsi
0x18000ea48  call    ??R_lambda_1_@?1??CreateFromIdAsync@DeviceInformation@Enumeration@Devices@Windows@winrt@@SA@AEBUhstring@param@6@AEBU?$async_iterable@Uhstring@winrt@@@86@AEBW4DeviceInformationKind@3456@@Z@QEBA@AEBUIDeviceInformationStatics2@3456@@Z; `winrt::Windows::Devices::Enumeration::DeviceInformation::CreateFromIdAsync(winrt::param::hstring const &,winrt::param::async_iterable<winrt::hstring> const &,winrt::Windows::Devices::Enumeration::DeviceInformationKind const &)'::`2'::_lambda_1_::operator()(winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2 const &)
0x18000ea4d  nop
0x18000ea4e  test    rbx, rbx
0x18000ea51  jz      short loc_18000EA5C
0x18000ea53  lea     rcx, [rbp+arg_0]
0x18000ea57  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000ea5c  mov     rax, rdi
0x18000ea5f  mov     rbx, [rsp+60h+arg_8]
0x18000ea67  add     rsp, 60h
0x18000ea6b  pop     rdi
0x18000ea6c  pop     rsi
0x18000ea6d  pop     rbp
0x18000ea6e  retn
0x18000ea6f  lea     rdx, [rbp+var_38]
0x18000ea73  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
