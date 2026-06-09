# _GetComplement_::_1_::dtor$1

- ea: `0x100473aec`
- end: `0x100473af8`
- name: `_GetComplement_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x10040acd0`

## pseudocode

```c
void __fastcall GetComplement_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  CGeodeticBoolean::~CGeodeticBoolean((CGeodeticBoolean *)(a2 + 512));
}

```

## disassembly

```asm
0x100473aec  lea     rcx, [rdx+200h]; this
0x100473af3  jmp     ??1CGeodeticBoolean@@UEAA@XZ; CGeodeticBoolean::~CGeodeticBoolean(void)
```
