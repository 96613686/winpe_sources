# _GetComplement_::_1_::dtor$0

- ea: `0x100473ae0`
- end: `0x100473aec`
- name: `_GetComplement_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x10040d590`

## pseudocode

```c
void __fastcall GetComplement_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  GeometryDataBuilder::~GeometryDataBuilder((GeometryDataBuilder *)(a2 + 112));
}

```

## disassembly

```asm
0x100473ae0  lea     rcx, [rdx+70h]; this
0x100473ae7  jmp     ??1GeometryDataBuilder@@UEAA@XZ; GeometryDataBuilder::~GeometryDataBuilder(void)
```
