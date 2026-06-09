# _GetComplement_::_1_::dtor$6

- ea: `0x100473b04`
- end: `0x100473b10`
- name: `_GetComplement_::_1_::dtor$6`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x100401480`

## pseudocode

```c
void __fastcall GetComplement_::_1_::dtor_6(__int64 a1, __int64 a2)
{
  CGeometrySinkD::~CGeometrySinkD((CGeometrySinkD *)(a2 + 336));
}

```

## disassembly

```asm
0x100473b04  lea     rcx, [rdx+150h]; this
0x100473b0b  jmp     ??1CGeometrySinkD@@UEAA@XZ; CGeometrySinkD::~CGeometrySinkD(void)
```
