# _winrt::impl::invoke_winrt::Windows::Foundation::AsyncOperationCompletedHandler_unsigned_int__winrt::impl::promise_base_std::experimental::coroutine_traits_winrt::Windows::Foundation::IAsyncOperation_unsigned_int__winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper___::promise_type_winrt::Windows::Foundation::IAsyncOperation_unsigned_int__void__enum_winrt::Windows::Foundation::AsyncStatus__::_1_::dtor$0

- ea: `0x18000b6f7`
- end: `0x18000b703`
- name: `_winrt::impl::invoke_winrt::Windows::Foundation::AsyncOperationCompletedHandler_unsigned_int__winrt::impl::promise_base_std::experimental::coroutine_traits_winrt::Windows::Foundation::IAsyncOperation_unsigned_int__winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper___::promise_type_winrt::Windows::Foundation::IAsyncOperation_unsigned_int__void__enum_winrt::Windows::Foundation::AsyncStatus__::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800068c0`

## pseudocode

```c
__int64 __fastcall winrt::impl::invoke_winrt::Windows::Foundation::AsyncOperationCompletedHandler_unsigned_int__winrt::impl::promise_base_std::experimental::coroutine_traits_winrt::Windows::Foundation::IAsyncOperation_unsigned_int__winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper___::promise_type_winrt::Windows::Foundation::IAsyncOperation_unsigned_int__void__enum_winrt::Windows::Foundation::AsyncStatus__::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  return winrt::impl::producer_ref<winrt::Windows::Foundation::IAsyncOperation<unsigned int>>::~producer_ref<winrt::Windows::Foundation::IAsyncOperation<unsigned int>>(a2 + 80);
}

```

## disassembly

```asm
0x18000b6f7  lea     rcx, [rdx+50h]
0x18000b6fe  jmp     ??1?$producer_ref@U?$IAsyncOperation@I@Foundation@Windows@winrt@@@impl@winrt@@QEAA@XZ; winrt::impl::producer_ref<winrt::Windows::Foundation::IAsyncOperation<uint>>::~producer_ref<winrt::Windows::Foundation::IAsyncOperation<uint>>(void)
```
