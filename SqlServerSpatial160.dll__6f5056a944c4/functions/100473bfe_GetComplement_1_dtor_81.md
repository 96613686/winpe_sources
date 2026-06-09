# _GetComplement_::_1_::dtor$81

- ea: `0x100473bfe`
- end: `0x100473c0e`
- name: `_GetComplement_::_1_::dtor$81`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x100421170`

## pseudocode

```c
void __fastcall GetComplement_::_1_::dtor_81(__int64 a1, __int64 a2)
{
  ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(a2 + 144);
}

```

## disassembly

```asm
0x100473bfe  lea     rcx, [rdx+70h]
0x100473c05  add     rcx, 20h ; ' '
0x100473c09  jmp     ??1?$ArrayOverPages@VCLineSegmentIntersection@RobustIntersections@@V?$SOS_Or_CRT_Allocator@VCLineSegmentIntersection@RobustIntersections@@@@@@QEAA@XZ; ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(void)
```
