# ??$call@AEAV_lambda_1_@?1??CreateFromIdAsync@DeviceInformation@Enumeration@Devices@Windows@winrt@@SA@AEBUhstring@param@7@AEBU?$async_iterable@Uhstring@winrt@@@97@@Z@@?$factory_cache_entry@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateFromIdAsync@DeviceInformation@Enumeration@Devices@Windows@2@SA@AEBUhstring@param@2@AEBU?$async_iterable@Uhstring@winrt@@@param@2@@Z@@Z

- ea: `0x18000b8fc`
- end: `0x18000baf6`
- name: `??$call@AEAV_lambda_1_@?1??CreateFromIdAsync@DeviceInformation@Enumeration@Devices@Windows@winrt@@SA@AEBUhstring@param@7@AEBU?$async_iterable@Uhstring@winrt@@@97@@Z@@?$factory_cache_entry@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateFromIdAsync@DeviceInformation@Enumeration@Devices@Windows@2@SA@AEBUhstring@param@2@AEBU?$async_iterable@Uhstring@winrt@@@param@2@@Z@@Z`
- size: `506`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000e950`

## callees

- `0x180003b9d`
- `0x18000b8fc`
- `0x18000bc5c`
- `0x180011a4c`
- `0x180011e0c`
- `0x180013010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall ___call_AEAV_lambda_1___1__CreateFromIdAsync_DeviceInformation_Enumeration_Devices_Windows_winrt__SA_AEBUhstring_param_7_AEBU__async_iterable_Uhstring_winrt___97__Z____factory_cache_entry_UDeviceInformation_Enumeration_Devices_Windows_winrt__UIDeviceInformationStatics_2345__impl_winrt__QEAA_A_PAEAV_lambda_1___1__CreateFromIdAsync_DeviceInformation_Enumeration_Devices_Windows_2_SA_AEBUhstring_param_2_AEBU__async_iterable_Uhstring_winrt___param_2__Z__Z(
        __int64 a1,
        _QWORD *a2,
        _QWORD **a3)
{
  __int64 v5; // r8
  signed __int64 v6; // rbx
  signed int v7; // eax
  __int64 v8; // r8
  signed int v9; // eax
  __int64 v10; // r8
  unsigned int v12; // [rsp+40h] [rbp-40h] BYREF
  const char *v13; // [rsp+48h] [rbp-38h]
  __int64 v14; // [rsp+50h] [rbp-30h]
  _DWORD *v15; // [rsp+58h] [rbp-28h] BYREF
  _DWORD v16[4]; // [rsp+60h] [rbp-20h] BYREF
  const wchar_t *v17; // [rsp+70h] [rbp-10h]
  __int64 v18; // [rsp+A0h] [rbp+20h] BYREF
  __int64 v19; // [rsp+B8h] [rbp+38h] BYREF

  v18 = a1;
  v16[0] = 1;
  v16[1] = 45;
  v17 = L"Windows.Devices.Enumeration.DeviceInformation";
  v15 = v16;
  v19 = 0;
  v12 = 6172;
  v13 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt/base.h";
  v14 = 0;
  winrt::impl::get_runtime_activation_factory_impl<0>(
    &v18,
    &v15,
    (__int64)winrt::impl::guid_v<winrt::Windows::Devices::Enumeration::IDeviceInformationStatics>,
    (__int64)&v19);
  if ( (int)v18 < 0 )
    winrt::throw_hresult(v18, &v12, v5);
  v6 = v19;
  v18 = v19;
  if ( !v19
    || (v19 = 0,
        (**(void (__fastcall ***)(signed __int64, __int64 *, __int64 *))v6)(
          v6,
          &winrt::impl::guid_v<winrt::impl::IAgileObject>,
          &v19),
        !v19) )
  {
    v19 = 0;
    v12 = 792;
    v13 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt/Windows.Devices.Enumeration.h";
    v14 = 0;
    v9 = (*(__int64 (__fastcall **)(signed __int64, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v6 + 56LL))(
           v6,
           **a3,
           *a3[1],
           &v19);
    if ( v9 < 0 )
      winrt::throw_hresult(v9, &v12, v10);
    *a2 = v19;
    goto LABEL_11;
  }
  winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v19);
  _InterlockedIncrement64(&qword_18001B928);
  if ( !_InterlockedCompareExchange64(
          &winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics>,
          v6,
          0) )
  {
    v6 = 0;
    v18 = 0;
    WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &ListEntry);
  }
  v19 = 0;
  v12 = 792;
  v13 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt/Windows.Devices.Enumeration.h";
  v14 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64 *))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics>
                                                                     + 56LL))(
         winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics>,
         **a3,
         *a3[1],
         &v19);
  if ( v7 < 0 )
    winrt::throw_hresult(v7, &v12, v8);
  *a2 = v19;
  _InterlockedDecrement64(&qword_18001B928);
  if ( v6 )
LABEL_11:
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v18);
  return a2;
}

```

## disassembly

```asm
0x18000b8fc  mov     [rsp-18h+arg_8], rbx
0x18000b901  mov     [rsp-18h+arg_0], rcx
0x18000b906  push    rbp
0x18000b907  push    rsi
0x18000b908  push    rdi
0x18000b909  mov     rbp, rsp
0x18000b90c  sub     rsp, 80h
0x18000b913  mov     rsi, r8
0x18000b916  mov     rdi, rdx
0x18000b919  mov     [rbp+var_20], 1
0x18000b920  mov     [rbp+var_1C], 2Dh ; '-'
0x18000b927  lea     rax, aWindowsDevices; "Windows.Devices.Enumeration.DeviceInfor"...
0x18000b92e  mov     [rbp+var_10], rax
0x18000b932  lea     rax, [rbp+var_20]
0x18000b936  mov     [rbp+var_28], rax
0x18000b93a  mov     [rbp+arg_18], 0
0x18000b942  mov     [rbp+var_40], 181Ch
0x18000b949  lea     rax, aOnecoreuapInte_1; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x18000b950  mov     [rbp+var_38], rax
0x18000b954  mov     [rbp+var_30], 0
0x18000b95c  lea     r9, [rbp+arg_18]
0x18000b960  lea     r8, ??$guid_v@UIDeviceInformationStatics@Enumeration@Devices@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Devices::Enumeration::IDeviceInformationStatics>
0x18000b967  lea     rdx, [rbp+var_28]
0x18000b96b  lea     rcx, [rbp+arg_0]
0x18000b96f  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x18000b974  mov     ecx, dword ptr [rbp+arg_0]
0x18000b977  test    ecx, ecx
0x18000b979  js      loc_18000BAE0
0x18000b97f  mov     rbx, [rbp+arg_18]
0x18000b983  mov     [rbp+arg_0], rbx
0x18000b987  test    rbx, rbx
0x18000b98a  jz      loc_18000BA68
0x18000b990  mov     [rbp+arg_18], 0
0x18000b998  mov     rax, [rbx]
0x18000b99b  lea     r8, [rbp+arg_18]
0x18000b99f  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18000b9a6  mov     rcx, rbx
0x18000b9a9  mov     rax, [rax]
0x18000b9ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b9b1  mov     rax, [rbp+arg_18]
0x18000b9b5  mov     [rbp+arg_18], rax
0x18000b9b9  test    rax, rax
0x18000b9bc  jz      loc_18000BA68
0x18000b9c2  lea     rcx, [rbp+arg_18]
0x18000b9c6  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000b9cb  lea     rax, qword_18001B928
0x18000b9d2  mov     [rbp+var_48], rax
0x18000b9d6  lock inc cs:qword_18001B928
0x18000b9de  xor     eax, eax
0x18000b9e0  lock cmpxchg cs:??$factory_cache_entry_v@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics@2345@@12@A, rbx; factory_cache_entry<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics>::winrt::factory_cache_entry<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics>
0x18000b9e9  jnz     short loc_18000BA04
0x18000b9eb  xor     ebx, ebx
0x18000b9ed  mov     [rbp+arg_0], rbx
0x18000b9f1  lea     rdx, ListEntry; ListEntry
0x18000b9f8  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18000b9ff  call    WINRT_IMPL_InterlockedPushEntrySList
0x18000ba04  mov     [rbp+arg_18], 0
0x18000ba0c  mov     rcx, cs:??$factory_cache_entry_v@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics@2345@@12@A; factory_cache_entry<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics>::winrt::factory_cache_entry<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics>
0x18000ba13  mov     [rbp+var_40], 318h
0x18000ba1a  lea     rax, aOnecoreuapInte_5; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x18000ba21  mov     [rbp+var_38], rax
0x18000ba25  mov     [rbp+var_30], 0
0x18000ba2d  mov     rax, [rcx]
0x18000ba30  mov     r8, [rsi+8]
0x18000ba34  mov     rdx, [rsi]
0x18000ba37  lea     r9, [rbp+arg_18]
0x18000ba3b  mov     r8, [r8]
0x18000ba3e  mov     rdx, [rdx]
0x18000ba41  mov     rax, [rax+38h]
0x18000ba45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba4a  test    eax, eax
0x18000ba4c  js      loc_18000BAEA
0x18000ba52  mov     rax, [rbp+arg_18]
0x18000ba56  mov     [rdi], rax
0x18000ba59  lock dec cs:qword_18001B928
0x18000ba61  test    rbx, rbx
0x18000ba64  jz      short loc_18000BABE
0x18000ba66  jmp     short loc_18000BAB5
0x18000ba68  mov     [rbp+arg_18], 0
0x18000ba70  mov     [rbp+var_40], 318h
0x18000ba77  lea     rax, aOnecoreuapInte_5; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x18000ba7e  mov     [rbp+var_38], rax
0x18000ba82  mov     [rbp+var_30], 0
0x18000ba8a  mov     rax, [rbx]
0x18000ba8d  mov     r8, [rsi+8]
0x18000ba91  mov     rdx, [rsi]
0x18000ba94  lea     r9, [rbp+arg_18]
0x18000ba98  mov     r8, [r8]
0x18000ba9b  mov     rdx, [rdx]
0x18000ba9e  mov     rcx, rbx
0x18000baa1  mov     rax, [rax+38h]
0x18000baa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000baaa  test    eax, eax
0x18000baac  js      short loc_18000BAD4
0x18000baae  mov     rax, [rbp+arg_18]
0x18000bab2  mov     [rdi], rax
0x18000bab5  lea     rcx, [rbp+arg_0]
0x18000bab9  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000babe  mov     rax, rdi
0x18000bac1  mov     rbx, [rsp+80h+arg_8]
0x18000bac9  add     rsp, 80h
0x18000bad0  pop     rdi
0x18000bad1  pop     rsi
0x18000bad2  pop     rbp
0x18000bad3  retn
0x18000bad4  lea     rdx, [rbp+var_40]
0x18000bad8  mov     ecx, eax
0x18000bada  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18000bae0  lea     rdx, [rbp+var_40]
0x18000bae4  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18000baea  lea     rdx, [rbp+var_40]
0x18000baee  mov     ecx, eax
0x18000baf0  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
