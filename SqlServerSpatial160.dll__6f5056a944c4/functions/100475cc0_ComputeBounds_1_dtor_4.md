# _ComputeBounds_::_1_::dtor$4

- ea: `0x100475cc0`
- end: `0x100475ccc`
- name: `_ComputeBounds_::_1_::dtor$4`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1004013d0`

## pseudocode

```c
void __fastcall ComputeBounds_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  IMglGeometrySink::~IMglGeometrySink((IMglGeometrySink *)(a2 + 80));
}

```

## disassembly

```asm
0x100475cc0  lea     rcx, [rdx+50h]; this
0x100475cc7  jmp     ??1IMglGeometrySink@@UEAA@XZ
```
