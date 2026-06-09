# _CDistanceFrom_CDistanceFromPoint_CDistanceFromLineSegment_CDistanceFromArc_::UpdateWithPoint_::_1_::dtor$6

- ea: `0x100475198`
- end: `0x1004751a4`
- name: `_CDistanceFrom_CDistanceFromPoint_CDistanceFromLineSegment_CDistanceFromArc_::UpdateWithPoint_::_1_::dtor$6`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x1004013d0`

## pseudocode

```c
void __fastcall CDistanceFrom_CDistanceFromPoint_CDistanceFromLineSegment_CDistanceFromArc_::UpdateWithPoint_::_1_::dtor_6(
        __int64 a1,
        __int64 a2)
{
  IMglGeometrySink::~IMglGeometrySink((IMglGeometrySink *)(a2 + 72));
}

```

## disassembly

```asm
0x100475198  lea     rcx, [rdx+48h]; this
0x10047519f  jmp     ??1IMglGeometrySink@@UEAA@XZ; IMglGeometrySink::~IMglGeometrySink(void)
```
