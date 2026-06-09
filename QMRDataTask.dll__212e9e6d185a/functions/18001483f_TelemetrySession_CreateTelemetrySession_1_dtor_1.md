# _TelemetrySession::CreateTelemetrySession_::_1_::dtor$1

- ea: `0x18001483f`
- end: `0x18001484b`
- name: `_TelemetrySession::CreateTelemetrySession_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180004040`

## pseudocode

```c
void __fastcall TelemetrySession::CreateTelemetrySession_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  TelemetrySession::~TelemetrySession(*(TelemetrySession **)(a2 + 32));
}

```

## disassembly

```asm
0x18001483f  mov     rcx, [rdx+20h]; this
0x180014846  jmp     ??1TelemetrySession@@QEAA@XZ; TelemetrySession::~TelemetrySession(void)
```
