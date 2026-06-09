# ??$call@AEAV_lambda_8990dbc09aa93641535709401a2a7a41_@@@?$factory_cache_entry@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_8990dbc09aa93641535709401a2a7a41_@@@Z

- ea: `0x1800086e0`
- end: `0x1800087f0`
- name: `??$call@AEAV_lambda_8990dbc09aa93641535709401a2a7a41_@@@?$factory_cache_entry@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_8990dbc09aa93641535709401a2a7a41_@@@Z`
- size: `272`
- prototype: `__int64 __fastcall(void (__fastcall ***)(_QWORD, __int64 *, __int64 **), __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18000bf48`

## callees

- `0x180003495`
- `0x18000750c`
- `0x1800086e0`
- `0x180008c80`
- `0x18000a2b0`
- `0x18000a360`
- `0x18000ab94`
- `0x180018010`

## pseudocode

```c
__int64 __fastcall winrt::impl::factory_cache_entry<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>::call<_lambda_8990dbc09aa93641535709401a2a7a41_ &>(
        void (__fastcall ***a1)(_QWORD, __int64 *, __int64 **),
        __int64 a2,
        __int64 a3)
{
  signed __int64 v5; // rdi
  _QWORD v7[2]; // [rsp+28h] [rbp-38h] BYREF
  _BYTE v8[40]; // [rsp+38h] [rbp-28h] BYREF
  void (__fastcall ***v9)(_QWORD, __int64 *, __int64 **); // [rsp+80h] [rbp+20h] BYREF
  __int64 *v10; // [rsp+98h] [rbp+38h] BYREF

  v9 = a1;
  v7[0] = L"Windows.Devices.Enumeration.DeviceInformation";
  v7[1] = 45;
  winrt::param::hstring::hstring(v8, v7);
  winrt::get_activation_factory<winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>(&v9, v8);
  v5 = (signed __int64)v9;
  if ( v9 && (v10 = 0, (**v9)(v9, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v10), v10) )
  {
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v10);
    v10 = &qword_180022848;
    _InterlockedIncrement64(&qword_180022848);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>,
            v5,
            0) )
    {
      v9 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &ListEntry);
    }
    _lambda_8990dbc09aa93641535709401a2a7a41_::operator()(
      a3,
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>);
    _InterlockedDecrement64(&qword_180022848);
  }
  else
  {
    _lambda_8990dbc09aa93641535709401a2a7a41_::operator()(a3, a2, &v9);
  }
  winrt::Windows::Devices::Enumeration::IDeviceInformation::~IDeviceInformation((winrt::Windows::Devices::Enumeration::IDeviceInformation *)&v9);
  return a2;
}

```

## disassembly

```asm
0x1800086e0  mov     [rsp-18h+arg_8], rbx
0x1800086e5  mov     [rsp-18h+arg_0], rcx
0x1800086ea  push    rbp
0x1800086eb  push    rsi
0x1800086ec  push    rdi
0x1800086ed  mov     rbp, rsp
0x1800086f0  sub     rsp, 60h
0x1800086f4  mov     rsi, r8
0x1800086f7  mov     rbx, rdx
0x1800086fa  lea     rax, aWindowsDevices; "Windows.Devices.Enumeration.DeviceInfor"...
0x180008701  mov     [rbp+var_38], rax
0x180008705  mov     [rbp+var_30], 2Dh ; '-'
0x18000870d  lea     rdx, [rbp+var_38]
0x180008711  lea     rcx, [rbp+var_28]
0x180008715  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::param::hstring::hstring(std::basic_string_view<ushort> const &)
0x18000871a  lea     rdx, [rbp+var_28]
0x18000871e  lea     rcx, [rbp+arg_0]
0x180008722  call    ??$get_activation_factory@UIDeviceInformationStatics2@Enumeration@Devices@Windows@winrt@@@winrt@@YA?AUIDeviceInformationStatics2@Enumeration@Devices@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>(winrt::param::hstring const &)
0x180008727  nop
0x180008728  mov     rdi, [rbp+arg_0]
0x18000872c  test    rdi, rdi
0x18000872f  jz      loc_1800087C4
0x180008735  mov     [rbp+arg_18], 0
0x18000873d  mov     rax, [rdi]
0x180008740  lea     r8, [rbp+arg_18]
0x180008744  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18000874b  mov     rcx, rdi
0x18000874e  mov     rax, [rax]
0x180008751  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008756  mov     rax, [rbp+arg_18]
0x18000875a  mov     [rbp+arg_18], rax
0x18000875e  test    rax, rax
0x180008761  jz      short loc_1800087C4
0x180008763  lea     rcx, [rbp+arg_18]
0x180008767  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000876c  lea     rax, qword_180022848
0x180008773  mov     [rbp+arg_18], rax
0x180008777  lock inc cs:qword_180022848
0x18000877f  xor     eax, eax
0x180008781  lock cmpxchg cs:??$factory_cache_entry_v@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@impl@winrt@@3U?$factory_cache_entry@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@12@A, rdi; factory_cache_entry<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>::winrt::factory_cache_entry<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2> winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>
0x18000878a  jnz     short loc_1800087A7
0x18000878c  mov     [rbp+arg_0], 0
0x180008794  lea     rdx, ListEntry; ListEntry
0x18000879b  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x1800087a2  call    WINRT_IMPL_InterlockedPushEntrySList
0x1800087a7  lea     r8, ??$factory_cache_entry_v@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@impl@winrt@@3U?$factory_cache_entry@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@12@A; factory_cache_entry<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>::winrt::factory_cache_entry<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2> winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>
0x1800087ae  mov     rdx, rbx
0x1800087b1  mov     rcx, rsi
0x1800087b4  call    ??R_lambda_8990dbc09aa93641535709401a2a7a41_@@QEBA@AEBUIDeviceInformationStatics2@Enumeration@Devices@Windows@winrt@@@Z; _lambda_8990dbc09aa93641535709401a2a7a41_::operator()(winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2 const &)
0x1800087b9  nop
0x1800087ba  lock dec cs:qword_180022848
0x1800087c2  jmp     short loc_1800087D4
0x1800087c4  lea     r8, [rbp+arg_0]
0x1800087c8  mov     rdx, rbx
0x1800087cb  mov     rcx, rsi
0x1800087ce  call    ??R_lambda_8990dbc09aa93641535709401a2a7a41_@@QEBA@AEBUIDeviceInformationStatics2@Enumeration@Devices@Windows@winrt@@@Z; _lambda_8990dbc09aa93641535709401a2a7a41_::operator()(winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2 const &)
0x1800087d3  nop
0x1800087d4  lea     rcx, [rbp+arg_0]; this
0x1800087d8  call    ??1IDeviceInformation@Enumeration@Devices@Windows@winrt@@QEAA@XZ; winrt::Windows::Devices::Enumeration::IDeviceInformation::~IDeviceInformation(void)
0x1800087dd  mov     rax, rbx
0x1800087e0  mov     rbx, [rsp+60h+arg_8]
0x1800087e8  add     rsp, 60h
0x1800087ec  pop     rdi
0x1800087ed  pop     rsi
0x1800087ee  pop     rbp
0x1800087ef  retn
```
