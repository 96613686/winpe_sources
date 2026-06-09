# _CSingleSideReducer::ShapeData::_ShapeData_::_1_::dtor$1

- ea: `0x100476e60`
- end: `0x100476e70`
- name: `_CSingleSideReducer::ShapeData::_ShapeData_::_1_::dtor$1`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x10041e710`

## pseudocode

```c
__int64 __fastcall CSingleSideReducer::ShapeData::_ShapeData_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return CAutoArray<RobustIntersections::CLineSegmentIntersection *,0,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection *>>::~CAutoArray<RobustIntersections::CLineSegmentIntersection *,0,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection *>>((_QWORD *)(*(_QWORD *)(a2 + 64) + 40LL));
}

```

## disassembly

```asm
0x100476e60  mov     rcx, [rdx+40h]
0x100476e67  add     rcx, 28h ; '('
0x100476e6b  jmp     ??1?$CAutoArray@PEAVCLineSegmentIntersection@RobustIntersections@@$0A@V?$SOS_Or_CRT_Allocator@PEAVCLineSegmentIntersection@RobustIntersections@@@@@@QEAA@XZ
```
