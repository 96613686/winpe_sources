# _GetComplement_::_1_::dtor$80

- ea: `0x100473bee`
- end: `0x100473bfe`
- name: `_GetComplement_::_1_::dtor$80`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x100421170`

## pseudocode

```c
void __fastcall GetComplement_::_1_::dtor_80(__int64 a1, __int64 a2)
{
  ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(a2 + 120);
}

```

## disassembly

```asm
0x100473bee  lea     rcx, [rdx+70h]
0x100473bf5  add     rcx, 8
0x100473bf9  jmp     ??1?$ArrayOverPages@VCLineSegmentIntersection@RobustIntersections@@V?$SOS_Or_CRT_Allocator@VCLineSegmentIntersection@RobustIntersections@@@@@@QEAA@XZ; ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(void)
```
