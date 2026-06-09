# _winrt::impl::invoke_winrt::Windows::Foundation::AsyncOperationCompletedHandler_unsigned_int__winrt::impl::promise_base_std::experimental::coroutine_traits_winrt::Windows::Foundation::IAsyncOperation_unsigned_int__winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper___::promise_type_winrt::Windows::Foundation::IAsyncOperation_unsigned_int__void__enum_winrt::Windows::Foundation::AsyncStatus__::_1_::catch$5

- ea: `0x18000b709`
- end: `0x18000b72f`
- name: `_winrt::impl::invoke_winrt::Windows::Foundation::AsyncOperationCompletedHandler_unsigned_int__winrt::impl::promise_base_std::experimental::coroutine_traits_winrt::Windows::Foundation::IAsyncOperation_unsigned_int__winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper___::promise_type_winrt::Windows::Foundation::IAsyncOperation_unsigned_int__void__enum_winrt::Windows::Foundation::AsyncStatus__::_1_::catch$5`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180009b4c`

## pseudocode

```c
__int64 __fastcall winrt::impl::invoke_winrt::Windows::Foundation::AsyncOperationCompletedHandler_unsigned_int__winrt::impl::promise_base_std::experimental::coroutine_traits_winrt::Windows::Foundation::IAsyncOperation_unsigned_int__winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper___::promise_type_winrt::Windows::Foundation::IAsyncOperation_unsigned_int__void__enum_winrt::Windows::Foundation::AsyncStatus__::_1_::catch_5(
        winrt::impl *a1,
        __int64 a2)
{
  *(_BYTE *)(a2 + 80) = winrt::impl::report_failed_invoke(a1);
  return 0;
}

```

## disassembly

```asm
0x18000b709  mov     [rsp+arg_8], rdx
0x18000b70e  push    rbp
0x18000b70f  sub     rsp, 20h
0x18000b713  mov     rbp, rdx
0x18000b716  call    ?report_failed_invoke@impl@winrt@@YA_NXZ; winrt::impl::report_failed_invoke(void)
0x18000b71b  mov     [rbp+50h], al
0x18000b71e  mov     rax, 0
0x18000b728  add     rsp, 20h
0x18000b72c  pop     rbp
0x18000b72d  retn
```
