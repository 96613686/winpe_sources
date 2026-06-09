# ?AddRef@?$implements_delegate@UAsyncActionCompletedHandler@Foundation@Windows@winrt@@Ushared_type@?1???$wait_for_completed@UIAsyncAction@Foundation@Windows@winrt@@@impl@4@YA?A_PAEBUIAsyncAction@234@I@Z@@impl@winrt@@UEAAIXZ

- ea: `0x180007040`
- end: `0x180007049`
- name: `?AddRef@?$implements_delegate@UAsyncActionCompletedHandler@Foundation@Windows@winrt@@Ushared_type@?1???$wait_for_completed@UIAsyncAction@Foundation@Windows@winrt@@@impl@4@YA?A_PAEBUIAsyncAction@234@I@Z@@impl@winrt@@UEAAIXZ`
- size: `9`
- prototype: `unsigned int __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000ed58`

## pseudocode

```c
unsigned int __fastcall _AddRef___implements_delegate_UAsyncActionCompletedHandler_Foundation_Windows_winrt__Ushared_type__1____wait_for_completed_UIAsyncAction_Foundation_Windows_winrt___impl_4_YA_A_PAEBUIAsyncAction_234_I_Z__impl_winrt__UEAAIXZ(
        __int64 a1)
{
  return winrt::impl::implements_delegate_base::increment_reference((winrt::impl::implements_delegate_base *)(a1 + 8));
}

```

## disassembly

```asm
0x180007040  add     rcx, 8; this
0x180007044  jmp     ?increment_reference@implements_delegate_base@impl@winrt@@QEAAIXZ; winrt::impl::implements_delegate_base::increment_reference(void)
```
