# SQL_Memblock<RobustIntersections::CLineSegmentIntersection>::~SQL_Memblock<RobustIntersections::CLineSegmentIntersection>(void)

- ea: `0x1004019e0`
- end: `0x1004019fb`
- name: `??1?$SQL_Memblock@VCLineSegmentIntersection@RobustIntersections@@@@QEAA@XZ`
- size: `27`
- prototype: ``
- caller_count: `28`
- callee_count: `1`
- tags: ``

## callers

- `0x100469cf0`
- `0x100469d62`
- `0x100469db0`
- `0x100469e5b`
- `0x100469e77`
- `0x100469e93`
- `0x10046a050`
- `0x10046a080`
- `0x10046a0dc`
- `0x10046a10c`
- `0x10046a162`
- `0x10046a7be`
- `0x10046aa58`
- `0x10046abb8`
- `0x10046acb1`
- `0x10046af2b`
- `0x10046b19b`
- `0x10046b25f`
- `0x10046b2af`
- `0x10046b538`
- `0x10046b709`
- `0x10046c99b`
- `0x10046ca5b`
- `0x10046cadb`
- `0x10046d37d`
- `0x10046d3ec`
- `0x10046d6f1`
- `0x10046d760`

## callees

- `0x100421170`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall SQL_Memblock<RobustIntersections::CLineSegmentIntersection>::~SQL_Memblock<RobustIntersections::CLineSegmentIntersection>(
        __int64 a1)
{
  ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(a1);
}

```

## disassembly

```asm
0x1004019e0  mov     [rsp+arg_0], rcx
0x1004019e5  sub     rsp, 38h
0x1004019e9  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1004019f2  add     rsp, 38h
0x1004019f6  jmp     ??1?$ArrayOverPages@VCLineSegmentIntersection@RobustIntersections@@V?$SOS_Or_CRT_Allocator@VCLineSegmentIntersection@RobustIntersections@@@@@@QEAA@XZ; ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(void)
```
