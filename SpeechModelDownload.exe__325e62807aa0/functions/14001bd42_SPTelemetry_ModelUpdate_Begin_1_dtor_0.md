# _SPTelemetry::ModelUpdate::Begin_::_1_::dtor$0

- ea: `0x14001bd42`
- end: `0x14001bd4e`
- name: `_SPTelemetry::ModelUpdate::Begin_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x140004c40`

## pseudocode

```c
void __fastcall SPTelemetry::ModelUpdate::Begin_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  SpAutoLock::~SpAutoLock((struct _RTL_CRITICAL_SECTION **)(a2 + 32));
}

```

## disassembly

```asm
0x14001bd42  lea     rcx, [rdx+20h]; this
0x14001bd49  jmp     ??1SpAutoLock@@QEAA@XZ; SpAutoLock::~SpAutoLock(void)
```
