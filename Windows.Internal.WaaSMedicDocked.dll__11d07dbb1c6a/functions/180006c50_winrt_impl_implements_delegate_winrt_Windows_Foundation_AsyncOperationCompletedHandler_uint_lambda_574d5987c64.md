# winrt::impl::implements_delegate<winrt::Windows::Foundation::AsyncOperationCompletedHandler<uint>,_lambda_574d5987c64a6b3f18218f4a51f47ca3_>::AddRef(void)

- ea: `0x180006c50`
- end: `0x180006c59`
- name: `?AddRef@?$implements_delegate@U?$AsyncOperationCompletedHandler@I@Foundation@Windows@winrt@@V_lambda_574d5987c64a6b3f18218f4a51f47ca3_@@@impl@winrt@@UEAAIXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180009544`

## pseudocode

```c
unsigned int __fastcall winrt::impl::implements_delegate<winrt::Windows::Foundation::AsyncOperationCompletedHandler<unsigned int>,_lambda_574d5987c64a6b3f18218f4a51f47ca3_>::AddRef(
        __int64 a1)
{
  return winrt::impl::implements_delegate_base::increment_reference((winrt::impl::implements_delegate_base *)(a1 + 8));
}

```

## disassembly

```asm
0x180006c50  add     rcx, 8; this
0x180006c54  jmp     ?increment_reference@implements_delegate_base@impl@winrt@@QEAAIXZ; winrt::impl::implements_delegate_base::increment_reference(void)
```
