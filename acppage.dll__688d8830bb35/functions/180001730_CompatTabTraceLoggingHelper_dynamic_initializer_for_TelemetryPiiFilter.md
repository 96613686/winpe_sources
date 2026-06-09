# CompatTabTraceLoggingHelper::_dynamic_initializer_for__TelemetryPiiFilter__

- ea: `0x180001730`
- end: `0x18000173c`
- name: `CompatTabTraceLoggingHelper::_dynamic_initializer_for__TelemetryPiiFilter__`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180001d50`

## pseudocode

```c
int CompatTabTraceLoggingHelper::_dynamic_initializer_for__TelemetryPiiFilter__()
{
  return atexit((void (__cdecl *)())CompatTabTraceLoggingHelper::_dynamic_atexit_destructor_for__TelemetryPiiFilter__);
}

```

## disassembly

```asm
0x180001730  lea     rcx, CompatTabTraceLoggingHelper___dynamic_atexit_destructor_for__TelemetryPiiFilter__
0x180001737  jmp     atexit
```
