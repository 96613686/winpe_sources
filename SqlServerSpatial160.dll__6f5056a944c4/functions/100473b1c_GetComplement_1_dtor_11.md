# _GetComplement_::_1_::dtor$11

- ea: `0x100473b1c`
- end: `0x100473b28`
- name: `_GetComplement_::_1_::dtor$11`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1004013d0`

## pseudocode

```c
void __fastcall GetComplement_::_1_::dtor_11(__int64 a1, __int64 a2)
{
  IMglGeometrySink::~IMglGeometrySink(*(IMglGeometrySink **)(a2 + 96));
}

```

## disassembly

```asm
0x100473b1c  mov     rcx, [rdx+60h]; this
0x100473b23  jmp     ??1IMglGeometrySink@@UEAA@XZ
```
