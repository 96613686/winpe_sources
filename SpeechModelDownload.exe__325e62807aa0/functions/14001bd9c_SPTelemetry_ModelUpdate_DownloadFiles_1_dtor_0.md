# _SPTelemetry::ModelUpdate::DownloadFiles_::_1_::dtor$0

- ea: `0x14001bd9c`
- end: `0x14001bda8`
- name: `_SPTelemetry::ModelUpdate::DownloadFiles_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x140004c40`

## pseudocode

```c
void __fastcall SPTelemetry::ModelUpdate::DownloadFiles_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  SpAutoLock::~SpAutoLock((struct _RTL_CRITICAL_SECTION **)(a2 + 56));
}

```

## disassembly

```asm
0x14001bd9c  lea     rcx, [rdx+38h]; this
0x14001bda3  jmp     ??1SpAutoLock@@QEAA@XZ; SpAutoLock::~SpAutoLock(void)
```
