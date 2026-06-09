# _TelemetrySession::CreateTelemetrySession_::_1_::dtor$1

- ea: `0x18000cbd4`
- end: `0x18000cbe0`
- name: `_TelemetrySession::CreateTelemetrySession_::_1_::dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000bfd0`

## pseudocode

```c
void __fastcall TelemetrySession::CreateTelemetrySession_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  TelemetrySession::~TelemetrySession(*(TelemetrySession **)(a2 + 32));
}

```

## disassembly

```asm
0x18000cbd4  mov     rcx, [rdx+20h]; this
0x18000cbdb  jmp     ??1TelemetrySession@@QEAA@XZ; TelemetrySession::~TelemetrySession(void)
```
