# _Concurrency::details::_Task_impl_base::_CancelWithException_::_1_::dtor$0

- ea: `0x18001830e`
- end: `0x18001831a`
- name: `_Concurrency::details::_Task_impl_base::_CancelWithException_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x18000ffdc`

## pseudocode

```c
void __fastcall Concurrency::details::_Task_impl_base::_CancelWithException_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  Concurrency::details::_TaskCreationCallstack::~_TaskCreationCallstack((char **)(a2 + 64));
}

```

## disassembly

```asm
0x18001830e  lea     rcx, [rdx+40h]; this
0x180018315  jmp     ??1_TaskCreationCallstack@details@Concurrency@@QEAA@XZ; Concurrency::details::_TaskCreationCallstack::~_TaskCreationCallstack(void)
```
