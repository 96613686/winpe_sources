# _ArrayOverPages_CSingleSideReducer::ShapeData_Default_Allocator_CSingleSideReducer::ShapeData___::_ArrayOverPages_CSingleSideReducer::ShapeData_Default_Allocator_CSingleSideReducer::ShapeData____::_1_::dtor$0

- ea: `0x10046c2f0`
- end: `0x10046c2fc`
- name: `_ArrayOverPages_CSingleSideReducer::ShapeData_Default_Allocator_CSingleSideReducer::ShapeData___::_ArrayOverPages_CSingleSideReducer::ShapeData_Default_Allocator_CSingleSideReducer::ShapeData____::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x10041e710`

## pseudocode

```c
__int64 __fastcall ArrayOverPages_CSingleSideReducer::ShapeData_Default_Allocator_CSingleSideReducer::ShapeData___::_ArrayOverPages_CSingleSideReducer::ShapeData_Default_Allocator_CSingleSideReducer::ShapeData____::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  return CAutoArray<RobustIntersections::CLineSegmentIntersection *,0,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection *>>::~CAutoArray<RobustIntersections::CLineSegmentIntersection *,0,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection *>>(*(_QWORD **)(a2 + 64));
}

```

## disassembly

```asm
0x10046c2f0  mov     rcx, [rdx+40h]
0x10046c2f7  jmp     ??1?$CAutoArray@PEAVCLineSegmentIntersection@RobustIntersections@@$0A@V?$SOS_Or_CRT_Allocator@PEAVCLineSegmentIntersection@RobustIntersections@@@@@@QEAA@XZ; CAutoArray<RobustIntersections::CLineSegmentIntersection *,0,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection *>>::~CAutoArray<RobustIntersections::CLineSegmentIntersection *,0,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection *>>(void)
```
