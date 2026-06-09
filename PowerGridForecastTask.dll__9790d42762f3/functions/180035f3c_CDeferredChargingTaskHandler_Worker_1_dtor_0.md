# _CDeferredChargingTaskHandler::Worker_::_1_::dtor$0

- ea: `0x180035f3c`
- end: `0x180035f48`
- name: `_CDeferredChargingTaskHandler::Worker_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180028468`

## pseudocode

```c
void __fastcall CDeferredChargingTaskHandler::Worker_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  PowerGridForecastTaskTelemetry::GeneratePowerGridForecastActivity::~GeneratePowerGridForecastActivity((PowerGridForecastTaskTelemetry::GeneratePowerGridForecastActivity *)(a2 + 80));
}

```

## disassembly

```asm
0x180035f3c  lea     rcx, [rdx+50h]; this
0x180035f43  jmp     ??1GeneratePowerGridForecastActivity@PowerGridForecastTaskTelemetry@@QEAA@XZ; PowerGridForecastTaskTelemetry::GeneratePowerGridForecastActivity::~GeneratePowerGridForecastActivity(void)
```
