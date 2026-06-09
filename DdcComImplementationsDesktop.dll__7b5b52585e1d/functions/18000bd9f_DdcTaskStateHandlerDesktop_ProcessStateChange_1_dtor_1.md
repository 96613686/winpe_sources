# _DdcTaskStateHandlerDesktop::ProcessStateChange_::_1_::dtor$1

- ea: `0x18000bd9f`
- end: `0x18000bdab`
- name: `_DdcTaskStateHandlerDesktop::ProcessStateChange_::_1_::dtor$1`
- size: `12`
- prototype: `_QWORD *__fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1800047c8`

## pseudocode

```c
_QWORD *__fastcall DdcTaskStateHandlerDesktop::ProcessStateChange_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<IRegisteredTask>::~ComPtr<IRegisteredTask>((_QWORD *)(a2 + 312));
}

```

## disassembly

```asm
0x18000bd9f  lea     rcx, [rdx+138h]
0x18000bda6  jmp     ??1?$ComPtr@UIRegisteredTask@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<IRegisteredTask>::~ComPtr<IRegisteredTask>(void)
```
