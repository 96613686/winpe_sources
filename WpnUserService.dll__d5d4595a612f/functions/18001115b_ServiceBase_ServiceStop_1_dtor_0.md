# _ServiceBase::ServiceStop_::_1_::dtor$0

- ea: `0x18001115b`
- end: `0x180011167`
- name: `_ServiceBase::ServiceStop_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x18000dea0`

## pseudocode

```c
void __fastcall ServiceBase::ServiceStop_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  ServiceHostTelemetry::ServiceStopActivity::~ServiceStopActivity((ServiceHostTelemetry::ServiceStopActivity *)(a2 + 64));
}

```

## disassembly

```asm
0x18001115b  lea     rcx, [rdx+40h]; this
0x180011162  jmp     ??1ServiceStopActivity@ServiceHostTelemetry@@QEAA@XZ; ServiceHostTelemetry::ServiceStopActivity::~ServiceStopActivity(void)
```
