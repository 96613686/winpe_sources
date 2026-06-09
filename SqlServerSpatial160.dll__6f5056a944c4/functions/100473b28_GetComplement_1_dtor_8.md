# _GetComplement_::_1_::dtor$8

- ea: `0x100473b28`
- end: `0x100473b34`
- name: `_GetComplement_::_1_::dtor$8`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x100401480`

## pseudocode

```c
void __fastcall GetComplement_::_1_::dtor_8(__int64 a1, __int64 a2)
{
  CGeometrySinkD::~CGeometrySinkD(*(CGeometrySinkD **)(a2 + 96));
}

```

## disassembly

```asm
0x100473b28  mov     rcx, [rdx+60h]; this
0x100473b2f  jmp     ??1CGeometrySinkD@@UEAA@XZ
```
