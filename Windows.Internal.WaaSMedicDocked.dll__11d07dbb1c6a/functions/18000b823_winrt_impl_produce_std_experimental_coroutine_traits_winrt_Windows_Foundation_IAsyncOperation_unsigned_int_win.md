# _winrt::impl::produce_std::experimental::coroutine_traits_winrt::Windows::Foundation::IAsyncOperation_unsigned_int__winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper___::promise_type_winrt::Windows::Foundation::IAsyncOperation_unsigned_int___::put_Completed_::_1_::catch$3

- ea: `0x18000b823`
- end: `0x18000b84f`
- name: `_winrt::impl::produce_std::experimental::coroutine_traits_winrt::Windows::Foundation::IAsyncOperation_unsigned_int__winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper___::promise_type_winrt::Windows::Foundation::IAsyncOperation_unsigned_int___::put_Completed_::_1_::catch$3`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180009f70`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce_std::experimental::coroutine_traits_winrt::Windows::Foundation::IAsyncOperation_unsigned_int__winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper___::promise_type_winrt::Windows::Foundation::IAsyncOperation_unsigned_int___::put_Completed_::_1_::catch_3(
        __int64 a1,
        __int64 a2)
{
  *(_DWORD *)(a2 + 96) = *(_DWORD *)winrt::to_hresult(a2 + 96);
  return 0;
}

```

## disassembly

```asm
0x18000b823  mov     [rsp+arg_8], rdx
0x18000b828  push    rbp
0x18000b829  sub     rsp, 20h
0x18000b82d  mov     rbp, rdx
0x18000b830  lea     rcx, [rbp+60h]
0x18000b834  call    ?to_hresult@winrt@@YA?AUhresult@1@XZ; winrt::to_hresult(void)
0x18000b839  mov     ecx, [rax]
0x18000b83b  mov     [rbp+60h], ecx
0x18000b83e  mov     rax, 0
0x18000b848  add     rsp, 20h
0x18000b84c  pop     rbp
0x18000b84d  retn
```
