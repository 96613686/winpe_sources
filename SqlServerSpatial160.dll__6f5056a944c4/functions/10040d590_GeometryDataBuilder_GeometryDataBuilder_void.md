# GeometryDataBuilder::~GeometryDataBuilder(void)

- ea: `0x10040d590`
- end: `0x10040d5de`
- name: `??1GeometryDataBuilder@@UEAA@XZ`
- size: `78`
- prototype: `void __fastcall(GeometryDataBuilder *__hidden this)`
- caller_count: `36`
- callee_count: `1`
- tags: ``

## callers

- `0x10046e2e0`
- `0x10046e350`
- `0x10046e37b`
- `0x10046e3bf`
- `0x10046e42a`
- `0x10046e4c0`
- `0x10046e560`
- `0x10046e5d0`
- `0x10046ea10`
- `0x10046ef10`
- `0x10046f0d0`
- `0x10046f740`
- `0x10046fdc4`
- `0x1004720b0`
- `0x100472230`
- `0x100472630`
- `0x100472860`
- `0x100472940`
- `0x100473820`
- `0x100473ae0`
- `0x100473cb8`
- `0x100474068`
- `0x100474174`
- `0x100474318`
- `0x100474450`
- `0x100474a60`
- `0x100474df0`
- `0x100476520`
- `0x100476544`
- `0x1004765a8`
- `0x10047660c`
- `0x100476670`
- `0x1004766d4`
- `0x100476738`
- `0x1004767f0`
- `0x100476b3c`

## callees

- `0x100421170`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall GeometryDataBuilder::~GeometryDataBuilder(GeometryDataBuilder *this)
{
  ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>((char *)this + 80);
  ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>((char *)this + 56);
  ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>((char *)this + 32);
  ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>((char *)this + 8);
  *(_QWORD *)this = &IMglGeometrySink::`vftable';
}

```

## disassembly

```asm
0x10040d590  mov     [rsp+arg_0], rcx
0x10040d595  push    rbx
0x10040d596  sub     rsp, 30h
0x10040d59a  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x10040d5a3  mov     rbx, rcx
0x10040d5a6  add     rcx, 50h ; 'P'
0x10040d5aa  call    ??1?$ArrayOverPages@VCLineSegmentIntersection@RobustIntersections@@V?$SOS_Or_CRT_Allocator@VCLineSegmentIntersection@RobustIntersections@@@@@@QEAA@XZ; ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(void)
0x10040d5af  nop
0x10040d5b0  lea     rcx, [rbx+38h]
0x10040d5b4  call    ??1?$ArrayOverPages@VCLineSegmentIntersection@RobustIntersections@@V?$SOS_Or_CRT_Allocator@VCLineSegmentIntersection@RobustIntersections@@@@@@QEAA@XZ; ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(void)
0x10040d5b9  nop
0x10040d5ba  lea     rcx, [rbx+20h]
0x10040d5be  call    ??1?$ArrayOverPages@VCLineSegmentIntersection@RobustIntersections@@V?$SOS_Or_CRT_Allocator@VCLineSegmentIntersection@RobustIntersections@@@@@@QEAA@XZ; ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(void)
0x10040d5c3  nop
0x10040d5c4  lea     rcx, [rbx+8]
0x10040d5c8  call    ??1?$ArrayOverPages@VCLineSegmentIntersection@RobustIntersections@@V?$SOS_Or_CRT_Allocator@VCLineSegmentIntersection@RobustIntersections@@@@@@QEAA@XZ; ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(void)
0x10040d5cd  nop
0x10040d5ce  lea     rax, ??_7IMglGeometrySink@@6B@; const IMglGeometrySink::`vftable'
0x10040d5d5  mov     [rbx], rax
0x10040d5d8  add     rsp, 30h
0x10040d5dc  pop     rbx
0x10040d5dd  retn
```
