# _CDistanceFrom_CDistanceFromPoint_CDistanceFromLineSegment_CDistanceFromArc_::UpdateWithPoint_::_1_::dtor$0

- ea: `0x100475174`
- end: `0x100475180`
- name: `_CDistanceFrom_CDistanceFromPoint_CDistanceFromLineSegment_CDistanceFromArc_::UpdateWithPoint_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x100401720`

## pseudocode

```c
void __fastcall CDistanceFrom_CDistanceFromPoint_CDistanceFromLineSegment_CDistanceFromArc_::UpdateWithPoint_::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  CGridCoverageForHemisphere::~CGridCoverageForHemisphere((CGridCoverageForHemisphere *)(a2 + 72));
}

```

## disassembly

```asm
0x100475174  lea     rcx, [rdx+48h]; this
0x10047517b  jmp     ??1CGridCoverageForHemisphere@@UEAA@XZ; CGridCoverageForHemisphere::~CGridCoverageForHemisphere(void)
```
