# winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<bool>,winrt::Windows::System::Update::factory_implementation::SystemUpdateManager *,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncOperation<bool>,void>::~promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<bool>,winrt::Windows::System::Update::factory_implementation::SystemUpdateManager *,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncOperation<bool>,void>(void)

- ea: `0x18001f578`
- end: `0x18001f5b0`
- name: `??1?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@PEAUSystemUpdateManager@factory_implementation@Update@System@34@Uhstring@4@@experimental@std@@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@X@impl@winrt@@UEAA@XZ`
- size: `56`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `5`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001f938`
- `0x18001fe10`
- `0x18001fe90`
- `0x180020230`
- `0x180024f90`

## callees

- `0x180005a1c`
- `0x180005cc4`
- `0x180009918`
- `0x18001f578`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18001f59d`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18001f59d`

## pseudocode

```c
__int64 __fastcall winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<bool>,winrt::Windows::System::Update::factory_implementation::SystemUpdateManager *,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncOperation<bool>,void>::~promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<bool>,winrt::Windows::System::Update::factory_implementation::SystemUpdateManager *,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncOperation<bool>,void>(
        _QWORD *a1)
{
  _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_((_lambda_12ef4a55c56a96ec7ad58335194b061f_ *)(a1 + 11));
  if ( a1[10] )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 10);
  __ExceptionPtrDestroy(a1 + 7);
  return winrt::impl::root_implements<winrt::Windows::System::Update::factory_implementation::SystemUpdateManager,winrt::Windows::Foundation::IActivationFactory,winrt::Windows::System::Update::ISystemUpdateManagerStatics,winrt::static_lifetime>::~root_implements<winrt::Windows::System::Update::factory_implementation::SystemUpdateManager,winrt::Windows::Foundation::IActivationFactory,winrt::Windows::System::Update::ISystemUpdateManagerStatics,winrt::static_lifetime>(a1);
}

```

## disassembly

```asm
0x18001f578  push    rbx
0x18001f57a  sub     rsp, 20h
0x18001f57e  mov     rbx, rcx
0x18001f581  add     rcx, 58h ; 'X'; this
0x18001f585  call    ??1_lambda_12ef4a55c56a96ec7ad58335194b061f_@@QEAA@XZ; _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_(void)
0x18001f58a  lea     rcx, [rbx+50h]
0x18001f58e  cmp     qword ptr [rcx], 0
0x18001f592  jz      short loc_18001F599
0x18001f594  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001f599  lea     rcx, [rbx+38h]
0x18001f59d  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18001f5a3  mov     rcx, rbx
0x18001f5a6  add     rsp, 20h
0x18001f5aa  pop     rbx
0x18001f5ab  jmp     ??1?$root_implements@USystemUpdateManager@factory_implementation@Update@System@Windows@winrt@@UIActivationFactory@Foundation@56@UISystemUpdateManagerStatics@3456@Ustatic_lifetime@6@@impl@winrt@@MEAA@XZ; winrt::impl::root_implements<winrt::Windows::System::Update::factory_implementation::SystemUpdateManager,winrt::Windows::Foundation::IActivationFactory,winrt::Windows::System::Update::ISystemUpdateManagerStatics,winrt::static_lifetime>::~root_implements<winrt::Windows::System::Update::factory_implementation::SystemUpdateManager,winrt::Windows::Foundation::IActivationFactory,winrt::Windows::System::Update::ISystemUpdateManagerStatics,winrt::static_lifetime>(void)
```
