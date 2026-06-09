# CReconstructor::~CReconstructor(void)

- ea: `0x100401e40`
- end: `0x100401e6e`
- name: `??1CReconstructor@@UEAA@XZ`
- size: `46`
- prototype: `void __fastcall(CReconstructor *__hidden this)`
- caller_count: `26`
- callee_count: `1`
- tags: ``

## callers

- `0x10046a0b0`
- `0x10046a0d0`
- `0x10046a100`
- `0x10046a14f`
- `0x10046a7b2`
- `0x10046a8db`
- `0x10046aa4c`
- `0x10046abac`
- `0x10046aca5`
- `0x10046ad8b`
- `0x10046af1f`
- `0x10046affb`
- `0x10046b18f`
- `0x10046bfdf`
- `0x10046c938`
- `0x10046c98f`
- `0x10046c9f8`
- `0x10046ca4f`
- `0x10046cacf`
- `0x10046d371`
- `0x10046d3e0`
- `0x10046d6e5`
- `0x10046d754`
- `0x10046ea5f`
- `0x100472cd2`
- `0x1004756cf`

## callees

- `0x100421170`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CReconstructor::~CReconstructor(CReconstructor *this)
{
  *(_QWORD *)this = &CReconstructor::`vftable';
  ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>((__int64)this + 32);
}

```

## disassembly

```asm
0x100401e40  mov     [rsp+arg_0], rcx
0x100401e45  sub     rsp, 38h
0x100401e49  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x100401e52  lea     rax, ??_7CReconstructor@@6B@; const CReconstructor::`vftable'
0x100401e59  mov     [rcx], rax
0x100401e5c  add     rcx, 20h ; ' '
0x100401e60  mov     [rsp+38h+arg_8], rcx
0x100401e65  add     rsp, 38h
0x100401e69  jmp     ??1?$ArrayOverPages@VCLineSegmentIntersection@RobustIntersections@@V?$SOS_Or_CRT_Allocator@VCLineSegmentIntersection@RobustIntersections@@@@@@QEAA@XZ; ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(void)
```
