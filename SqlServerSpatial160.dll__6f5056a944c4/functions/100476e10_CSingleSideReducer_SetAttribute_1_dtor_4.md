# _CSingleSideReducer::SetAttribute_::_1_::dtor$4

- ea: `0x100476e10`
- end: `0x100476e1c`
- name: `_CSingleSideReducer::SetAttribute_::_1_::dtor$4`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x10041e710`

## pseudocode

```c
__int64 __fastcall CSingleSideReducer::SetAttribute_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  return CAutoArray<RobustIntersections::CLineSegmentIntersection *,0,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection *>>::~CAutoArray<RobustIntersections::CLineSegmentIntersection *,0,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection *>>(*(_QWORD **)(a2 + 176));
}

```

## disassembly

```asm
0x100476e10  mov     rcx, [rdx+0B0h]
0x100476e17  jmp     ??1?$CAutoArray@PEAVCLineSegmentIntersection@RobustIntersections@@$0A@V?$SOS_Or_CRT_Allocator@PEAVCLineSegmentIntersection@RobustIntersections@@@@@@QEAA@XZ; CAutoArray<RobustIntersections::CLineSegmentIntersection *,0,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection *>>::~CAutoArray<RobustIntersections::CLineSegmentIntersection *,0,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection *>>(void)
```
