# _CSingleSideReducer::SetAttribute_::_1_::dtor$6

- ea: `0x100476e38`
- end: `0x100476e48`
- name: `_CSingleSideReducer::SetAttribute_::_1_::dtor$6`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x10041e710`

## pseudocode

```c
__int64 __fastcall CSingleSideReducer::SetAttribute_::_1_::dtor_6(__int64 a1, __int64 a2)
{
  return CAutoArray<RobustIntersections::CLineSegmentIntersection *,0,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection *>>::~CAutoArray<RobustIntersections::CLineSegmentIntersection *,0,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection *>>((_QWORD *)(a2 + 104));
}

```

## disassembly

```asm
0x100476e38  lea     rcx, [rdx+40h]
0x100476e3f  add     rcx, 28h ; '('
0x100476e43  jmp     ??1?$CAutoArray@PEAVCLineSegmentIntersection@RobustIntersections@@$0A@V?$SOS_Or_CRT_Allocator@PEAVCLineSegmentIntersection@RobustIntersections@@@@@@QEAA@XZ; CAutoArray<RobustIntersections::CLineSegmentIntersection *,0,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection *>>::~CAutoArray<RobustIntersections::CLineSegmentIntersection *,0,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection *>>(void)
```
