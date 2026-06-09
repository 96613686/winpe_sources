# _CSingleSideReducer::_CSingleSideReducer_::_1_::dtor$3

- ea: `0x100476ddf`
- end: `0x100476df2`
- name: `_CSingleSideReducer::_CSingleSideReducer_::_1_::dtor$3`
- size: `19`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x10041e710`

## pseudocode

```c
__int64 __fastcall CSingleSideReducer::_CSingleSideReducer_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  return CAutoArray<RobustIntersections::CLineSegmentIntersection *,0,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection *>>::~CAutoArray<RobustIntersections::CLineSegmentIntersection *,0,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection *>>((_QWORD *)(*(_QWORD *)(a2 + 96) + 160LL));
}

```

## disassembly

```asm
0x100476ddf  mov     rcx, [rdx+60h]
0x100476de6  add     rcx, 0A0h
0x100476ded  jmp     ??1?$CAutoArray@PEAVCLineSegmentIntersection@RobustIntersections@@$0A@V?$SOS_Or_CRT_Allocator@PEAVCLineSegmentIntersection@RobustIntersections@@@@@@QEAA@XZ; CAutoArray<RobustIntersections::CLineSegmentIntersection *,0,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection *>>::~CAutoArray<RobustIntersections::CLineSegmentIntersection *,0,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection *>>(void)
```
