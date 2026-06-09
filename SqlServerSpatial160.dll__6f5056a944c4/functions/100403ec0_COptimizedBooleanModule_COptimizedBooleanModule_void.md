# COptimizedBooleanModule::~COptimizedBooleanModule(void)

- ea: `0x100403ec0`
- end: `0x100403fec`
- name: `??1COptimizedBooleanModule@@UEAA@XZ`
- size: `300`
- prototype: `void __fastcall(COptimizedBooleanModule *__hidden this)`
- caller_count: `21`
- callee_count: `4`
- tags: ``

## callers

- `0x100403e80`
- `0x100404e90`
- `0x100404ef0`
- `0x100405050`
- `0x1004050b0`
- `0x10040f200`
- `0x10040fad0`
- `0x10046b760`
- `0x10046b7b0`
- `0x10046b8a0`
- `0x10046b8f0`
- `0x10046f1b0`
- `0x10046f1df`
- `0x10046f2ae`
- `0x10046f37d`
- `0x10046f44c`
- `0x10046f7d8`
- `0x10046f807`
- `0x10046f8a6`
- `0x10046f945`
- `0x10046f9e4`

## callees

- `0x100401900`
- `0x1004025c0`
- `0x100403ec0`
- `0x100421170`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!free` at `0x100403f16`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x100403f16`

## pseudocode

```c
// Hidden C++ exception states: #wind=27
void __fastcall COptimizedBooleanModule::~COptimizedBooleanModule(COptimizedBooleanModule *this)
{
  _QWORD *v2; // rbx
  void *v3; // rdx

  v2 = (_QWORD *)((char *)this + 1168);
  *((_QWORD *)this + 146) = &CArcReconstructor::`vftable';
  v3 = (void *)*((_QWORD *)this + 150);
  if ( g_SOSHost )
  {
    if ( v3 )
      (*(void (__fastcall **)(_QWORD))(*g_SOSMemObj + 128LL))(g_SOSMemObj);
  }
  else
  {
    free(v3);
  }
  v2[4] = 0;
  v2[3] = 0;
  *v2 = &CDecorator::`vftable';
  *v2 = &IMglGeometrySink::`vftable';
  *((_QWORD *)this + 140) = &CPlanarFlattener::`vftable';
  *((_QWORD *)this + 140) = &CFlattener::`vftable';
  *((_QWORD *)this + 140) = &CDecorator::`vftable';
  *((_QWORD *)this + 140) = &IMglGeometrySink::`vftable';
  CBufferOptimizer::~CBufferOptimizer((COptimizedBooleanModule *)((char *)this + 920));
  *((_QWORD *)this + 96) = &CStructuredReconstructor::`vftable';
  *((_QWORD *)this + 96) = &CReconstructor::`vftable';
  ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>((__int64)this + 800);
  *((_QWORD *)this + 24) = &CBoolean::`vftable';
  *((_QWORD *)this + 24) = &C2ShapesProcessor::`vftable';
  CScanner::~CScanner((COptimizedBooleanModule *)((char *)this + 192));
  *(_QWORD *)this = &CScannerModuleD::`vftable';
  *((_QWORD *)this + 7) = &IMglGeometrySink::`vftable';
  *((_QWORD *)this + 1) = &IMglGeometrySink::`vftable';
}

```

## disassembly

```asm
0x100403ec0  mov     [rsp+arg_0], rcx
0x100403ec5  push    rbx
0x100403ec6  push    rsi
0x100403ec7  push    rdi
0x100403ec8  sub     rsp, 40h
0x100403ecc  mov     [rsp+58h+var_38], 0FFFFFFFFFFFFFFFEh
0x100403ed5  mov     rdi, rcx
0x100403ed8  lea     rbx, [rcx+490h]
0x100403edf  mov     [rsp+58h+arg_8], rbx
0x100403ee4  lea     rax, ??_7CArcReconstructor@@6B@; const CArcReconstructor::`vftable'
0x100403eeb  mov     [rbx], rax
0x100403eee  mov     rdx, [rbx+20h]
0x100403ef2  cmp     cs:?g_SOSHost@@3VSOS_AutoHost@@A, 0; SOS_AutoHost g_SOSHost
0x100403efa  jz      short loc_100403F13
0x100403efc  test    rdx, rdx
0x100403eff  jz      short loc_100403F1C
0x100403f01  mov     rcx, cs:?g_SOSMemObj@@3VSOS_AutoMemObj@@A; SOS_AutoMemObj g_SOSMemObj
0x100403f08  mov     rax, [rcx]
0x100403f0b  call    qword ptr [rax+80h]
0x100403f11  jmp     short loc_100403F1C
0x100403f13  mov     rcx, rdx; Block
0x100403f16  call    cs:__imp_free
0x100403f1c  xor     eax, eax
0x100403f1e  mov     [rbx+20h], rax
0x100403f22  mov     [rbx+18h], rax
0x100403f26  lea     rdx, ??_7CDecorator@@6B@; const CDecorator::`vftable'
0x100403f2d  mov     [rbx], rdx
0x100403f30  lea     rsi, ??_7IMglGeometrySink@@6B@; const IMglGeometrySink::`vftable'
0x100403f37  mov     [rbx], rsi
0x100403f3a  lea     rax, [rdi+460h]
0x100403f41  mov     [rsp+58h+arg_8], rax
0x100403f46  lea     rcx, ??_7CPlanarFlattener@@6B@; const CPlanarFlattener::`vftable'
0x100403f4d  mov     [rax], rcx
0x100403f50  lea     rcx, ??_7CFlattener@@6B@; const CFlattener::`vftable'
0x100403f57  mov     [rax], rcx
0x100403f5a  mov     [rax], rdx
0x100403f5d  mov     [rax], rsi
0x100403f60  lea     rcx, [rdi+398h]; this
0x100403f67  call    ??1CBufferOptimizer@@UEAA@XZ; CBufferOptimizer::~CBufferOptimizer(void)
0x100403f6c  nop
0x100403f6d  lea     rcx, [rdi+300h]
0x100403f74  mov     [rsp+58h+arg_10], rcx
0x100403f79  lea     rax, ??_7CStructuredReconstructor@@6B@; const CStructuredReconstructor::`vftable'
0x100403f80  mov     [rcx], rax
0x100403f83  lea     rax, ??_7CReconstructor@@6B@; const CReconstructor::`vftable'
0x100403f8a  mov     [rcx], rax
0x100403f8d  add     rcx, 20h ; ' '
0x100403f91  mov     [rsp+58h+arg_18], rcx
0x100403f96  call    ??1?$ArrayOverPages@VCLineSegmentIntersection@RobustIntersections@@V?$SOS_Or_CRT_Allocator@VCLineSegmentIntersection@RobustIntersections@@@@@@QEAA@XZ; ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(void)
0x100403f9b  nop
0x100403f9c  lea     rcx, [rdi+0C0h]; this
0x100403fa3  mov     [rsp+58h+var_30], rcx
0x100403fa8  lea     rax, ??_7CBoolean@@6B@; const CBoolean::`vftable'
0x100403faf  mov     [rcx], rax
0x100403fb2  lea     rax, ??_7C2ShapesProcessor@@6B@; const C2ShapesProcessor::`vftable'
0x100403fb9  mov     [rcx], rax
0x100403fbc  call    ??1CScanner@@UEAA@XZ; CScanner::~CScanner(void)
0x100403fc1  nop
0x100403fc2  lea     rax, ??_7CScannerModuleD@@6B@; const CScannerModuleD::`vftable'
0x100403fc9  mov     [rdi], rax
0x100403fcc  lea     rcx, [rdi+8]
0x100403fd0  mov     [rsp+58h+arg_0], rcx
0x100403fd5  lea     rax, [rcx+30h]
0x100403fd9  mov     [rsp+58h+var_28], rax
0x100403fde  mov     [rax], rsi
0x100403fe1  mov     [rcx], rsi
0x100403fe4  add     rsp, 40h
0x100403fe8  pop     rdi
0x100403fe9  pop     rsi
0x100403fea  pop     rbx
0x100403feb  retn
```
