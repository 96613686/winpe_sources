# Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IInspectable>>::ComPtrRef<Microsoft::WRL::ComPtr<IInspectable>>(Microsoft::WRL::ComPtr<IInspectable> *)

- ea: `0x18000bf70`
- end: `0x18000bf8d`
- name: `??0?$ComPtrRef@V?$ComPtr@UIInspectable@@@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAA@PEAV?$ComPtr@UIInspectable@@@23@@Z`
- size: `29`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000cdf4`
- `0x180018bd0`

## pseudocode

```c
_QWORD *__fastcall Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IInspectable>>::ComPtrRef<Microsoft::WRL::ComPtr<IInspectable>>(
        _QWORD *a1,
        __int64 a2)
{
  *a1 = a2;
  return a1;
}

```

## disassembly

```asm
0x18000bf70  mov     [rsp+arg_8], rdx
0x18000bf75  mov     [rsp+arg_0], rcx
0x18000bf7a  mov     rax, [rsp+arg_0]
0x18000bf7f  mov     rcx, [rsp+arg_8]
0x18000bf84  mov     [rax], rcx
0x18000bf87  mov     rax, [rsp+arg_0]
0x18000bf8c  retn
```
