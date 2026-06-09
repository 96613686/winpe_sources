# _winrt::impl::delegate_winrt::Windows::Foundation::AsyncOperationCompletedHandler_winrt::Windows::Devices::Enumeration::DeviceInformation___winrt::impl::wait_for_completed_winrt::Windows::Foundation::IAsyncOperation_winrt::Windows::Devices::Enumeration::DeviceInformation____::_2_::shared_type_::Invoke_::_1_::catch$0

- ea: `0x1800125d4`
- end: `0x180012600`
- name: `_winrt::impl::delegate_winrt::Windows::Foundation::AsyncOperationCompletedHandler_winrt::Windows::Devices::Enumeration::DeviceInformation___winrt::impl::wait_for_completed_winrt::Windows::Foundation::IAsyncOperation_winrt::Windows::Devices::Enumeration::DeviceInformation____::_2_::shared_type_::Invoke_::_1_::catch$0`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180011d2c`

## pseudocode

```c
__int64 __fastcall winrt::impl::delegate_winrt::Windows::Foundation::AsyncOperationCompletedHandler_winrt::Windows::Devices::Enumeration::DeviceInformation___winrt::impl::wait_for_completed_winrt::Windows::Foundation::IAsyncOperation_winrt::Windows::Devices::Enumeration::DeviceInformation____::_2_::shared_type_::Invoke_::_1_::catch_0(
        __int64 a1,
        __int64 a2)
{
  *(_DWORD *)(a2 + 64) = *(_DWORD *)winrt::to_hresult(a2 + 64);
  return 0;
}

```

## disassembly

```asm
0x1800125d4  mov     [rsp+arg_8], rdx
0x1800125d9  push    rbp
0x1800125da  sub     rsp, 20h
0x1800125de  mov     rbp, rdx
0x1800125e1  lea     rcx, [rbp+40h]
0x1800125e5  call    ?to_hresult@winrt@@YA?AUhresult@1@XZ; winrt::to_hresult(void)
0x1800125ea  mov     ecx, [rax]
0x1800125ec  mov     [rbp+40h], ecx
0x1800125ef  mov     rax, 0
0x1800125f9  add     rsp, 20h
0x1800125fd  pop     rbp
0x1800125fe  retn
```
