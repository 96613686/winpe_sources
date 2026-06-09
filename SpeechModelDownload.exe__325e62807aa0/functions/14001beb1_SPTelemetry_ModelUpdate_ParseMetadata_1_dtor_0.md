# _SPTelemetry::ModelUpdate::ParseMetadata_::_1_::dtor$0

- ea: `0x14001beb1`
- end: `0x14001bebd`
- name: `_SPTelemetry::ModelUpdate::ParseMetadata_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x140004c40`

## pseudocode

```c
void __fastcall SPTelemetry::ModelUpdate::ParseMetadata_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  SpAutoLock::~SpAutoLock((struct _RTL_CRITICAL_SECTION **)(a2 + 104));
}

```

## disassembly

```asm
0x14001beb1  lea     rcx, [rdx+68h]; this
0x14001beb8  jmp     ??1SpAutoLock@@QEAA@XZ; SpAutoLock::~SpAutoLock(void)
```
