# CScanner::~CScanner(void)

- ea: `0x100401900`
- end: `0x100401971`
- name: `??1CScanner@@UEAA@XZ`
- size: `113`
- prototype: `void __fastcall(CScanner *__hidden this)`
- caller_count: `92`
- callee_count: `3`
- tags: ``

## callers

- `0x100401ad0`
- `0x100401db0`
- `0x100401de0`
- `0x1004020a0`
- `0x1004020e0`
- `0x1004021a0`
- `0x100402230`
- `0x100402280`
- `0x100402be0`
- `0x100402c20`
- `0x100402c80`
- `0x100402d20`
- `0x1004032e0`
- `0x100403590`
- `0x100403710`
- `0x100403880`
- `0x100403b50`
- `0x100403ec0`
- `0x1004041e0`
- `0x100404240`
- `0x1004042c0`
- `0x1004042f0`
- `0x1004046c0`
- `0x100404700`
- `0x1004047a0`
- `0x100404840`
- `0x100404870`
- `0x1004048d0`
- `0x100404cb0`
- `0x100406010`
- `0x1004099b0`
- `0x100409b80`
- `0x100409c40`
- `0x100409cf0`
- `0x100409d30`
- `0x100409e40`
- `0x100409eb0`
- `0x10040acd0`
- `0x10040ae90`
- `0x10040b0a0`
- `0x100410d70`
- `0x100411350`
- `0x100414150`
- `0x100452f50`
- `0x10046a030`
- `0x10046a17e`
- `0x10046a20c`
- `0x10046a46b`
- `0x10046a51b`
- `0x10046a7da`

## callees

- `0x100401b10`
- `0x100420a70`
- `0x100421170`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall CScanner::~CScanner(CScanner *this)
{
  *(_QWORD *)this = &CScanner::`vftable';
  *((_QWORD *)this + 58) = &CScanner::CIntersectionPool::`vftable';
  ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>((char *)this + 472);
  CAutoArray<CScanner::CMasterChain,7,Default_Allocator<CScanner::CMasterChain>>::~CAutoArray<CScanner::CMasterChain,7,Default_Allocator<CScanner::CMasterChain>>((char *)this + 392);
  CScanner::CChainList::~CChainList((CScanner *)((char *)this + 8));
  *(_QWORD *)this = &IMglGeometrySink::`vftable';
}

```

## disassembly

```asm
0x100401900  mov     [rsp+arg_0], rcx
0x100401905  push    rbx
0x100401906  sub     rsp, 30h
0x10040190a  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x100401913  mov     rbx, rcx
0x100401916  lea     rax, ??_7CScanner@@6B@; const CScanner::`vftable'
0x10040191d  mov     [rcx], rax
0x100401920  add     rcx, 1D0h
0x100401927  mov     [rsp+38h+arg_8], rcx
0x10040192c  lea     rax, ??_7CIntersectionPool@CScanner@@6B@; const CScanner::CIntersectionPool::`vftable'
0x100401933  mov     [rcx], rax
0x100401936  add     rcx, 8
0x10040193a  mov     [rsp+38h+arg_10], rcx
0x10040193f  call    ??1?$ArrayOverPages@VCLineSegmentIntersection@RobustIntersections@@V?$SOS_Or_CRT_Allocator@VCLineSegmentIntersection@RobustIntersections@@@@@@QEAA@XZ; ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(void)
0x100401944  nop
0x100401945  lea     rcx, [rbx+188h]
0x10040194c  mov     [rsp+38h+arg_18], rcx
0x100401951  call    ??1?$CAutoArray@VCMasterChain@CScanner@@$06V?$Default_Allocator@VCMasterChain@CScanner@@@@@@QEAA@XZ; CAutoArray<CScanner::CMasterChain,7,Default_Allocator<CScanner::CMasterChain>>::~CAutoArray<CScanner::CMasterChain,7,Default_Allocator<CScanner::CMasterChain>>(void)
0x100401956  nop
0x100401957  lea     rcx, [rbx+8]; this
0x10040195b  call    ??1CChainList@CScanner@@QEAA@XZ; CScanner::CChainList::~CChainList(void)
0x100401960  nop
0x100401961  lea     rax, ??_7IMglGeometrySink@@6B@; const IMglGeometrySink::`vftable'
0x100401968  mov     [rbx], rax
0x10040196b  add     rsp, 30h
0x10040196f  pop     rbx
0x100401970  retn
```
