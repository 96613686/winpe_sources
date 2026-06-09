# _winrt::impl::delegate_winrt::Windows::Foundation::AsyncActionCompletedHandler__winrt::impl::wait_for_completed_winrt::Windows::Foundation::IAsyncAction__::_2_::shared_type_::Invoke_::_1_::catch$0

- ea: `0x180010471`
- end: `0x18001049d`
- name: `_winrt::impl::delegate_winrt::Windows::Foundation::AsyncActionCompletedHandler__winrt::impl::wait_for_completed_winrt::Windows::Foundation::IAsyncAction__::_2_::shared_type_::Invoke_::_1_::catch$0`
- size: `44`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000f4f4`

## pseudocode

```c
__int64 __fastcall winrt::impl::delegate_winrt::Windows::Foundation::AsyncActionCompletedHandler__winrt::impl::wait_for_completed_winrt::Windows::Foundation::IAsyncAction__::_2_::shared_type_::Invoke_::_1_::catch_0(
        __int64 a1,
        __int64 a2)
{
  *(_DWORD *)(a2 + 64) = *(_DWORD *)winrt::to_hresult(a2 + 64);
  return 0;
}

```

## disassembly

```asm
0x180010471  mov     [rsp+arg_8], rdx
0x180010476  push    rbp
0x180010477  sub     rsp, 20h
0x18001047b  mov     rbp, rdx
0x18001047e  lea     rcx, [rbp+40h]
0x180010482  call    ?to_hresult@winrt@@YA?AUhresult@1@XZ; winrt::to_hresult(void)
0x180010487  mov     ecx, [rax]
0x180010489  mov     [rbp+40h], ecx
0x18001048c  mov     rax, 0
0x180010496  add     rsp, 20h
0x18001049a  pop     rbp
0x18001049b  retn
```
