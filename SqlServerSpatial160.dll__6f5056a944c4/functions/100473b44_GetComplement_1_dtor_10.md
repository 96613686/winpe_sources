# _GetComplement_::_1_::dtor$10

- ea: `0x100473b44`
- end: `0x100473b54`
- name: `_GetComplement_::_1_::dtor$10`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x10041e710`

## pseudocode

```c
__int64 __fastcall GetComplement_::_1_::dtor_10(__int64 a1, __int64 a2)
{
  return CAutoArray<RobustIntersections::CLineSegmentIntersection *,0,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection *>>::~CAutoArray<RobustIntersections::CLineSegmentIntersection *,0,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection *>>((_QWORD *)(*(_QWORD *)(a2 + 96) + 40LL));
}

```

## disassembly

```asm
0x100473b44  mov     rcx, [rdx+60h]
0x100473b4b  add     rcx, 28h ; '('
0x100473b4f  jmp     ??1?$CAutoArray@PEAVCLineSegmentIntersection@RobustIntersections@@$0A@V?$SOS_Or_CRT_Allocator@PEAVCLineSegmentIntersection@RobustIntersections@@@@@@QEAA@XZ; CAutoArray<RobustIntersections::CLineSegmentIntersection *,0,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection *>>::~CAutoArray<RobustIntersections::CLineSegmentIntersection *,0,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection *>>(void)
```
