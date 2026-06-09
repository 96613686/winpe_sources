# _ComputeBounds_::_1_::dtor$1

- ea: `0x100475c9c`
- end: `0x100475ca8`
- name: `_ComputeBounds_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x100401480`

## pseudocode

```c
void __fastcall ComputeBounds_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  CGeometrySinkD::~CGeometrySinkD((CGeometrySinkD *)(a2 + 80));
}

```

## disassembly

```asm
0x100475c9c  lea     rcx, [rdx+50h]; this
0x100475ca3  jmp     ??1CGeometrySinkD@@UEAA@XZ
```
