# _GetComplement_::_1_::dtor$79

- ea: `0x100473be2`
- end: `0x100473bee`
- name: `_GetComplement_::_1_::dtor$79`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x100401480`

## pseudocode

```c
void __fastcall GetComplement_::_1_::dtor_79(__int64 a1, __int64 a2)
{
  CGeometrySinkD::~CGeometrySinkD((CGeometrySinkD *)(a2 + 112));
}

```

## disassembly

```asm
0x100473be2  lea     rcx, [rdx+70h]; this
0x100473be9  jmp     ??1CGeometrySinkD@@UEAA@XZ; CGeometrySinkD::~CGeometrySinkD(void)
```
