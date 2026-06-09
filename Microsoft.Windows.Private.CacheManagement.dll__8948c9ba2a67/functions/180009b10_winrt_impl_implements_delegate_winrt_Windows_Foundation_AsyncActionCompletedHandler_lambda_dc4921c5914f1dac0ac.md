# winrt::impl::implements_delegate<winrt::Windows::Foundation::AsyncActionCompletedHandler,_lambda_dc4921c5914f1dac0ac69065375e73ef_>::AddRef(void)

- ea: `0x180009b10`
- end: `0x180009b19`
- name: `?AddRef@?$implements_delegate@UAsyncActionCompletedHandler@Foundation@Windows@winrt@@V_lambda_dc4921c5914f1dac0ac69065375e73ef_@@@impl@winrt@@UEAAIXZ`
- size: `9`
- prototype: `unsigned int __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000e7f0`

## pseudocode

```c
unsigned int __fastcall winrt::impl::implements_delegate<winrt::Windows::Foundation::AsyncActionCompletedHandler,_lambda_dc4921c5914f1dac0ac69065375e73ef_>::AddRef(
        __int64 a1)
{
  return winrt::impl::implements_delegate_base::increment_reference((winrt::impl::implements_delegate_base *)(a1 + 8));
}

```

## disassembly

```asm
0x180009b10  add     rcx, 8; this
0x180009b14  jmp     ?increment_reference@implements_delegate_base@impl@winrt@@QEAAIXZ; winrt::impl::implements_delegate_base::increment_reference(void)
```
