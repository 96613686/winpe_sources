# _ComputeBounds_::_1_::dtor$2

- ea: `0x100475c90`
- end: `0x100475c9c`
- name: `_ComputeBounds_::_1_::dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1004013d0`

## pseudocode

```c
void __fastcall ComputeBounds_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  IMglGeometrySink::~IMglGeometrySink((IMglGeometrySink *)(a2 + 80));
}

```

## disassembly

```asm
0x100475c90  lea     rcx, [rdx+50h]; this
0x100475c97  jmp     ??1IMglGeometrySink@@UEAA@XZ
```
