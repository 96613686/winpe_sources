# _DdcTaskSchedulerWrapper::EnableTaskIfExists_::_1_::dtor$0

- ea: `0x18000bdc3`
- end: `0x18000bdcf`
- name: `_DdcTaskSchedulerWrapper::EnableTaskIfExists_::_1_::dtor$0`
- size: `12`
- prototype: `_QWORD *__fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800047c8`

## pseudocode

```c
_QWORD *__fastcall DdcTaskSchedulerWrapper::EnableTaskIfExists_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<IRegisteredTask>::~ComPtr<IRegisteredTask>((_QWORD *)(a2 + 48));
}

```

## disassembly

```asm
0x18000bdc3  lea     rcx, [rdx+30h]
0x18000bdca  jmp     ??1?$ComPtr@UIRegisteredTask@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<IRegisteredTask>::~ComPtr<IRegisteredTask>(void)
```
