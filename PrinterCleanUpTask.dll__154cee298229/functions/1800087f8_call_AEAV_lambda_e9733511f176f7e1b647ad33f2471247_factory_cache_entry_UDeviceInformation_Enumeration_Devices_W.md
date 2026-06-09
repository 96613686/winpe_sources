# ??$call@AEAV_lambda_e9733511f176f7e1b647ad33f2471247_@@@?$factory_cache_entry@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_e9733511f176f7e1b647ad33f2471247_@@@Z

- ea: `0x1800087f8`
- end: `0x180008908`
- name: `??$call@AEAV_lambda_e9733511f176f7e1b647ad33f2471247_@@@?$factory_cache_entry@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_e9733511f176f7e1b647ad33f2471247_@@@Z`
- size: `272`
- prototype: `__int64 __fastcall(void (__fastcall ***)(_QWORD, __int64 *, __int64 **), __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18000c534`

## callees

- `0x180003495`
- `0x18000750c`
- `0x1800087f8`
- `0x180008c80`
- `0x18000a2b0`
- `0x18000a360`
- `0x18000ac14`
- `0x180018010`

## pseudocode

```c
__int64 __fastcall winrt::impl::factory_cache_entry<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>::call<_lambda_e9733511f176f7e1b647ad33f2471247_ &>(
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
    _lambda_e9733511f176f7e1b647ad33f2471247_::operator()(
      a3,
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>);
    _InterlockedDecrement64(&qword_180022848);
  }
  else
  {
    _lambda_e9733511f176f7e1b647ad33f2471247_::operator()(a3, a2, &v9);
  }
  winrt::Windows::Devices::Enumeration::IDeviceInformation::~IDeviceInformation((winrt::Windows::Devices::Enumeration::IDeviceInformation *)&v9);
  return a2;
}

```

## disassembly

```asm
0x1800087f8  mov     [rsp-18h+arg_8], rbx
0x1800087fd  mov     [rsp-18h+arg_0], rcx
0x180008802  push    rbp
0x180008803  push    rsi
0x180008804  push    rdi
0x180008805  mov     rbp, rsp
0x180008808  sub     rsp, 60h
0x18000880c  mov     rsi, r8
0x18000880f  mov     rbx, rdx
0x180008812  lea     rax, aWindowsDevices; "Windows.Devices.Enumeration.DeviceInfor"...
0x180008819  mov     [rbp+var_38], rax
0x18000881d  mov     [rbp+var_30], 2Dh ; '-'
0x180008825  lea     rdx, [rbp+var_38]
0x180008829  lea     rcx, [rbp+var_28]
0x18000882d  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::param::hstring::hstring(std::basic_string_view<ushort> const &)
0x180008832  lea     rdx, [rbp+var_28]
0x180008836  lea     rcx, [rbp+arg_0]
0x18000883a  call    ??$get_activation_factory@UIDeviceInformationStatics2@Enumeration@Devices@Windows@winrt@@@winrt@@YA?AUIDeviceInformationStatics2@Enumeration@Devices@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>(winrt::param::hstring const &)
0x18000883f  nop
0x180008840  mov     rdi, [rbp+arg_0]
0x180008844  test    rdi, rdi
0x180008847  jz      loc_1800088DC
0x18000884d  mov     [rbp+arg_18], 0
0x180008855  mov     rax, [rdi]
0x180008858  lea     r8, [rbp+arg_18]
0x18000885c  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x180008863  mov     rcx, rdi
0x180008866  mov     rax, [rax]
0x180008869  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000886e  mov     rax, [rbp+arg_18]
0x180008872  mov     [rbp+arg_18], rax
0x180008876  test    rax, rax
0x180008879  jz      short loc_1800088DC
0x18000887b  lea     rcx, [rbp+arg_18]
0x18000887f  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180008884  lea     rax, qword_180022848
0x18000888b  mov     [rbp+arg_18], rax
0x18000888f  lock inc cs:qword_180022848
0x180008897  xor     eax, eax
0x180008899  lock cmpxchg cs:??$factory_cache_entry_v@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@impl@winrt@@3U?$factory_cache_entry@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@12@A, rdi; factory_cache_entry<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>::winrt::factory_cache_entry<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2> winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>
0x1800088a2  jnz     short loc_1800088BF
0x1800088a4  mov     [rbp+arg_0], 0
0x1800088ac  lea     rdx, ListEntry; ListEntry
0x1800088b3  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x1800088ba  call    WINRT_IMPL_InterlockedPushEntrySList
0x1800088bf  lea     r8, ??$factory_cache_entry_v@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@impl@winrt@@3U?$factory_cache_entry@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@12@A; factory_cache_entry<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>::winrt::factory_cache_entry<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2> winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>
0x1800088c6  mov     rdx, rbx
0x1800088c9  mov     rcx, rsi
0x1800088cc  call    ??R_lambda_e9733511f176f7e1b647ad33f2471247_@@QEBA@AEBUIDeviceInformationStatics2@Enumeration@Devices@Windows@winrt@@@Z; _lambda_e9733511f176f7e1b647ad33f2471247_::operator()(winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2 const &)
0x1800088d1  nop
0x1800088d2  lock dec cs:qword_180022848
0x1800088da  jmp     short loc_1800088EC
0x1800088dc  lea     r8, [rbp+arg_0]
0x1800088e0  mov     rdx, rbx
0x1800088e3  mov     rcx, rsi
0x1800088e6  call    ??R_lambda_e9733511f176f7e1b647ad33f2471247_@@QEBA@AEBUIDeviceInformationStatics2@Enumeration@Devices@Windows@winrt@@@Z; _lambda_e9733511f176f7e1b647ad33f2471247_::operator()(winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2 const &)
0x1800088eb  nop
0x1800088ec  lea     rcx, [rbp+arg_0]; this
0x1800088f0  call    ??1IDeviceInformation@Enumeration@Devices@Windows@winrt@@QEAA@XZ; winrt::Windows::Devices::Enumeration::IDeviceInformation::~IDeviceInformation(void)
0x1800088f5  mov     rax, rbx
0x1800088f8  mov     rbx, [rsp+60h+arg_8]
0x180008900  add     rsp, 60h
0x180008904  pop     rdi
0x180008905  pop     rsi
0x180008906  pop     rbp
0x180008907  retn
```
