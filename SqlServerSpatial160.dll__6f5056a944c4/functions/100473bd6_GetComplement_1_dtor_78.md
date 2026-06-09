# _GetComplement_::_1_::dtor$78

- ea: `0x100473bd6`
- end: `0x100473be2`
- name: `_GetComplement_::_1_::dtor$78`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1004013d0`

## pseudocode

```c
void __fastcall GetComplement_::_1_::dtor_78(__int64 a1, __int64 a2)
{
  IMglGeometrySink::~IMglGeometrySink((IMglGeometrySink *)(a2 + 336));
}

```

## disassembly

```asm
0x100473bd6  lea     rcx, [rdx+150h]; this
0x100473bdd  jmp     ??1IMglGeometrySink@@UEAA@XZ; IMglGeometrySink::~IMglGeometrySink(void)
```
