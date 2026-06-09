# _ServiceBase::_ServiceMainInner_::_1_::dtor$0

- ea: `0x180011137`
- end: `0x180011143`
- name: `_ServiceBase::_ServiceMainInner_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x18000de74`

## pseudocode

```c
void __fastcall ServiceBase::_ServiceMainInner_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  ServiceHostTelemetry::ServiceStartActivity::~ServiceStartActivity((ServiceHostTelemetry::ServiceStartActivity *)(a2 + 80));
}

```

## disassembly

```asm
0x180011137  lea     rcx, [rdx+50h]; this
0x18001113e  jmp     ??1ServiceStartActivity@ServiceHostTelemetry@@QEAA@XZ; ServiceHostTelemetry::ServiceStartActivity::~ServiceStartActivity(void)
```
