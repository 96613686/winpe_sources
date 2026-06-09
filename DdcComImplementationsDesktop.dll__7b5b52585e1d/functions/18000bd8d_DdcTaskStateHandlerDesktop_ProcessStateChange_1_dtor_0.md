# _DdcTaskStateHandlerDesktop::ProcessStateChange_::_1_::dtor$0

- ea: `0x18000bd8d`
- end: `0x18000bd99`
- name: `_DdcTaskStateHandlerDesktop::ProcessStateChange_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x18000b1c0`

## pseudocode

```c
void __fastcall DdcTaskStateHandlerDesktop::ProcessStateChange_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  DdcTaskSchedulerWrapper::~DdcTaskSchedulerWrapper((DdcTaskSchedulerWrapper *)(a2 + 64));
}

```

## disassembly

```asm
0x18000bd8d  lea     rcx, [rdx+40h]; this
0x18000bd94  jmp     ??1DdcTaskSchedulerWrapper@@QEAA@XZ; DdcTaskSchedulerWrapper::~DdcTaskSchedulerWrapper(void)
```
