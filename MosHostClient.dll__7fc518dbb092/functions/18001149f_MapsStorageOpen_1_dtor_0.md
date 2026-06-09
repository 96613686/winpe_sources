# _MapsStorageOpen_::_1_::dtor$0

- ea: `0x18001149f`
- end: `0x1800114ab`
- name: `_MapsStorageOpen_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180009304`

## pseudocode

```c
void __fastcall MapsStorageOpen_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  OfflineMapsTelemetry::ClientOpenConnectionActivity::~ClientOpenConnectionActivity((OfflineMapsTelemetry::ClientOpenConnectionActivity *)(a2 + 64));
}

```

## disassembly

```asm
0x18001149f  lea     rcx, [rdx+40h]; this
0x1800114a6  jmp     ??1ClientOpenConnectionActivity@OfflineMapsTelemetry@@QEAA@XZ; OfflineMapsTelemetry::ClientOpenConnectionActivity::~ClientOpenConnectionActivity(void)
```
