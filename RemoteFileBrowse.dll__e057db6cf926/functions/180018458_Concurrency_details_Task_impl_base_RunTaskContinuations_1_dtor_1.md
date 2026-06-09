# _Concurrency::details::_Task_impl_base::_RunTaskContinuations_::_1_::dtor$1

- ea: `0x180018458`
- end: `0x180018464`
- name: `_Concurrency::details::_Task_impl_base::_RunTaskContinuations_::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x18000f8d4`

## pseudocode

```c
__int64 __fastcall Concurrency::details::_Task_impl_base::_RunTaskContinuations_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return std::_Func_class<void,>::~_Func_class<void,>(a2 + 64, a2);
}

```

## disassembly

```asm
0x180018458  lea     rcx, [rdx+40h]
0x18001845f  jmp     ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
```
