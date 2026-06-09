# _winrt::impl::produce_std::experimental::coroutine_traits_winrt::Windows::Foundation::IAsyncOperation_unsigned_int__winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper___::promise_type_winrt::Windows::Foundation::IAsyncOperation_unsigned_int___::put_Completed_::_1_::dtor$0

- ea: `0x18000b811`
- end: `0x18000b81d`
- name: `_winrt::impl::produce_std::experimental::coroutine_traits_winrt::Windows::Foundation::IAsyncOperation_unsigned_int__winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper___::promise_type_winrt::Windows::Foundation::IAsyncOperation_unsigned_int___::put_Completed_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180006a50`

## pseudocode

```c
void __fastcall winrt::impl::produce_std::experimental::coroutine_traits_winrt::Windows::Foundation::IAsyncOperation_unsigned_int__winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper___::promise_type_winrt::Windows::Foundation::IAsyncOperation_unsigned_int___::put_Completed_::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  winrt::slim_lock_guard::~slim_lock_guard((winrt::slim_lock_guard *)(a2 + 96));
}

```

## disassembly

```asm
0x18000b811  lea     rcx, [rdx+60h]; this
0x18000b818  jmp     ??1slim_lock_guard@winrt@@QEAA@XZ; winrt::slim_lock_guard::~slim_lock_guard(void)
```
