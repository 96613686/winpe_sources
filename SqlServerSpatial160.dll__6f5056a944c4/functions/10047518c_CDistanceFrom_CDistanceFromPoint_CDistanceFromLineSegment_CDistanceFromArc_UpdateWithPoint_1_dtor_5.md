# _CDistanceFrom_CDistanceFromPoint_CDistanceFromLineSegment_CDistanceFromArc_::UpdateWithPoint_::_1_::dtor$5

- ea: `0x10047518c`
- end: `0x100475198`
- name: `_CDistanceFrom_CDistanceFromPoint_CDistanceFromLineSegment_CDistanceFromArc_::UpdateWithPoint_::_1_::dtor$5`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x100401480`

## pseudocode

```c
void __fastcall CDistanceFrom_CDistanceFromPoint_CDistanceFromLineSegment_CDistanceFromArc_::UpdateWithPoint_::_1_::dtor_5(
        __int64 a1,
        __int64 a2)
{
  CGeometrySinkD::~CGeometrySinkD((CGeometrySinkD *)(a2 + 72));
}

```

## disassembly

```asm
0x10047518c  lea     rcx, [rdx+48h]; this
0x100475193  jmp     ??1CGeometrySinkD@@UEAA@XZ; CGeometrySinkD::~CGeometrySinkD(void)
```
