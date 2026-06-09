# _winrt::impl::delegate_winrt::Windows::Foundation::AsyncOperationCompletedHandler_unsigned_int___lambda_574d5987c64a6b3f18218f4a51f47ca3___::Invoke_::_1_::dtor$0

- ea: `0x18000b905`
- end: `0x18000b911`
- name: `_winrt::impl::delegate_winrt::Windows::Foundation::AsyncOperationCompletedHandler_unsigned_int___lambda_574d5987c64a6b3f18218f4a51f47ca3___::Invoke_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180006814`

## pseudocode

```c
__int64 __fastcall winrt::impl::delegate_winrt::Windows::Foundation::AsyncOperationCompletedHandler_unsigned_int___lambda_574d5987c64a6b3f18218f4a51f47ca3___::Invoke_::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  return winrt::Windows::Foundation::IAsyncOperation<unsigned int>::~IAsyncOperation<unsigned int>(a2 + 80);
}

```

## disassembly

```asm
0x18000b905  lea     rcx, [rdx+50h]
0x18000b90c  jmp     ??1?$IAsyncOperation@I@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IAsyncOperation<uint>::~IAsyncOperation<uint>(void)
```
