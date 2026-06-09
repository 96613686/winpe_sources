# _CDistanceFrom_CDistanceFromPoint_CDistanceFromLineSegment_CDistanceFromArc_::UpdateWithPoint_::_1_::dtor$4

- ea: `0x100475180`
- end: `0x10047518c`
- name: `_CDistanceFrom_CDistanceFromPoint_CDistanceFromLineSegment_CDistanceFromArc_::UpdateWithPoint_::_1_::dtor$4`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x100401590`

## pseudocode

```c
__int64 __fastcall CDistanceFrom_CDistanceFromPoint_CDistanceFromLineSegment_CDistanceFromArc_::UpdateWithPoint_::_1_::dtor_4(
        __int64 a1,
        __int64 a2)
{
  return CDistanceTo<CDistanceFromPoint,CDistanceFromLineSegment,CDistanceFromArc>::~CDistanceTo<CDistanceFromPoint,CDistanceFromLineSegment,CDistanceFromArc>(a2 + 72);
}

```

## disassembly

```asm
0x100475180  lea     rcx, [rdx+48h]
0x100475187  jmp     ??1?$CDistanceTo@VCDistanceFromPoint@@VCDistanceFromLineSegment@@VCDistanceFromArc@@@@UEAA@XZ; CDistanceTo<CDistanceFromPoint,CDistanceFromLineSegment,CDistanceFromArc>::~CDistanceTo<CDistanceFromPoint,CDistanceFromLineSegment,CDistanceFromArc>(void)
```
