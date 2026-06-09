# _SPTelemetry::ModelUpdate::ModelUpdate_::_1_::dtor$0

- ea: `0x14001bd30`
- end: `0x14001bd3c`
- name: `_SPTelemetry::ModelUpdate::ModelUpdate_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x140004aec`

## pseudocode

```c
void __fastcall SPTelemetry::ModelUpdate::ModelUpdate_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  Windows::Speech::Session::FlightDataRecorder::~FlightDataRecorder(*(Windows::Speech::Session::FlightDataRecorder **)(a2 + 48));
}

```

## disassembly

```asm
0x14001bd30  mov     rcx, [rdx+30h]; this
0x14001bd37  jmp     ??1FlightDataRecorder@Session@Speech@Windows@@MEAA@XZ; Windows::Speech::Session::FlightDataRecorder::~FlightDataRecorder(void)
```
