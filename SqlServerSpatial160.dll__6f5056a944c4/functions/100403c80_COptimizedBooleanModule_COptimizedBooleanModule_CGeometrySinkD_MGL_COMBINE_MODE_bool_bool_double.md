# COptimizedBooleanModule::COptimizedBooleanModule(CGeometrySinkD *,MGL_COMBINE_MODE,bool,bool,double)

- ea: `0x100403c80`
- end: `0x100403e10`
- name: `??0COptimizedBooleanModule@@QEAA@PEAVCGeometrySinkD@@W4MGL_COMBINE_MODE@@_N2N@Z`
- size: `400`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x10040f200`
- `0x10040fad0`

## callees

- `0x100401be0`
- `0x1004023f0`
- `0x10043b830`
- `0x100445370`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall COptimizedBooleanModule::COptimizedBooleanModule(__int64 a1, __int64 a2, int a3, bool a4, bool a5)
{
  __int64 v9; // r14
  _QWORD *v10; // rcx

  v9 = a1 + 192;
  CScannerModuleD::CScannerModuleD((CScannerModuleD *)a1, (struct CScanner *)(a1 + 192));
  *v10 = &COptimizedBooleanModule::`vftable';
  C2ShapesProcessor::C2ShapesProcessor((C2ShapesProcessor *)v9, a4, a5);
  *(_QWORD *)v9 = &CBoolean::`vftable';
  *(_QWORD *)(v9 + 560) = a1 + 768;
  *(_DWORD *)(v9 + 568) = a3;
  CReconstructor::CReconstructor((CReconstructor *)(a1 + 768), (struct IMglGeometrySink *)(a1 + 56), a4, a5);
  *(_QWORD *)(a1 + 768) = &CStructuredReconstructor::`vftable';
  *(_BYTE *)(a1 + 912) = 0;
  CBufferOptimizer::CBufferOptimizer((CBufferOptimizer *)(a1 + 920), (struct CGeometrySinkD *)v9);
  *(_QWORD *)(a1 + 1120) = &IMglGeometrySink::`vftable';
  *(_QWORD *)(a1 + 1120) = &CGeometrySinkD::`vftable';
  *(_QWORD *)(a1 + 1120) = &CDecorator::`vftable';
  *(_QWORD *)(a1 + 1128) = a1 + 8;
  *(_QWORD *)(a1 + 1120) = &CFlattener::`vftable';
  *(_QWORD *)(a1 + 1136) = 0;
  *(_QWORD *)(a1 + 1120) = &CPlanarFlattener::`vftable';
  *(_QWORD *)(a1 + 1160) = a1 + 1168;
  *(_QWORD *)(a1 + 1168) = &IMglGeometrySink::`vftable';
  *(_QWORD *)(a1 + 1168) = &CGeometrySinkD::`vftable';
  *(_QWORD *)(a1 + 1168) = &CDecorator::`vftable';
  *(_QWORD *)(a1 + 1176) = a2;
  *(_QWORD *)(a1 + 1168) = &CArcReconstructor::`vftable';
  *(_BYTE *)(a1 + 1184) = 0;
  *(_QWORD *)(a1 + 1200) = 0;
  *(_QWORD *)(a1 + 1192) = 0;
  *(_BYTE *)(a1 + 1216) = 0;
  *(_QWORD *)(a1 + 1224) = 0;
  *(_QWORD *)(a1 + 1232) = 0;
  *(_BYTE *)(a1 + 1240) = 0;
  *(_QWORD *)(a1 + 1248) = 0;
  *(_DWORD *)(a1 + 1256) = 0x80000000;
  *(_BYTE *)(a1 + 1260) = 1;
  *(_QWORD *)(a1 + 64) = a1 + 1168;
  *(_QWORD *)(a1 + 176) = a1 + 1168;
  return a1;
}

```

## disassembly

```asm
0x100403c80  mov     [rsp+arg_0], rcx
0x100403c85  push    rbp
0x100403c86  push    rsi
0x100403c87  push    r12
0x100403c89  push    r14
0x100403c8b  push    r15
0x100403c8d  sub     rsp, 40h
0x100403c91  mov     [rsp+68h+var_48], 0FFFFFFFFFFFFFFFEh
0x100403c9a  mov     [rsp+68h+arg_10], rbx
0x100403ca2  movzx   ebp, r9b
0x100403ca6  mov     esi, r8d
0x100403ca9  mov     r15, rdx
0x100403cac  mov     r12, rcx
0x100403caf  lea     r14, [rcx+0C0h]
0x100403cb6  mov     rdx, r14; struct CScanner *
0x100403cb9  call    ??0CScannerModuleD@@QEAA@AEAVCScanner@@@Z; CScannerModuleD::CScannerModuleD(CScanner &)
0x100403cbe  nop
0x100403cbf  lea     rax, ??_7COptimizedBooleanModule@@6B@; const COptimizedBooleanModule::`vftable'
0x100403cc6  mov     [rcx], rax
0x100403cc9  mov     [rsp+68h+arg_8], r14
0x100403cce  movzx   r8d, [rsp+68h+arg_20]; bool
0x100403cd7  movzx   edx, bpl; bool
0x100403cdb  mov     rcx, r14; this
0x100403cde  call    ??0C2ShapesProcessor@@QEAA@_N0@Z; C2ShapesProcessor::C2ShapesProcessor(bool,bool)
0x100403ce3  nop
0x100403ce4  lea     rax, ??_7CBoolean@@6B@; const CBoolean::`vftable'
0x100403ceb  mov     [r14], rax
0x100403cee  lea     rbx, [r12+300h]
0x100403cf6  mov     [r14+230h], rbx
0x100403cfd  mov     [r14+238h], esi
0x100403d04  mov     [rsp+68h+arg_28], rbx
0x100403d0c  lea     rdx, [r12+38h]; struct IMglGeometrySink *
0x100403d11  movzx   r9d, [rsp+68h+arg_20]; bool
0x100403d1a  movzx   r8d, bpl; bool
0x100403d1e  mov     rcx, rbx; this
0x100403d21  call    ??0CReconstructor@@QEAA@PEAUIMglGeometrySink@@_N1@Z; CReconstructor::CReconstructor(IMglGeometrySink *,bool,bool)
0x100403d26  nop
0x100403d27  lea     rax, ??_7CStructuredReconstructor@@6B@; const CStructuredReconstructor::`vftable'
0x100403d2e  mov     [rbx], rax
0x100403d31  mov     byte ptr [rbx+90h], 0
0x100403d38  lea     rcx, [r12+398h]; this
0x100403d40  mov     rdx, r14; struct CGeometrySinkD *
0x100403d43  call    ??0CBufferOptimizer@@QEAA@PEAVCGeometrySinkD@@@Z; CBufferOptimizer::CBufferOptimizer(CGeometrySinkD *)
0x100403d48  nop
0x100403d49  lea     rcx, [r12+460h]
0x100403d51  mov     [rsp+68h+var_40], rcx
0x100403d56  lea     r9, ??_7IMglGeometrySink@@6B@; const IMglGeometrySink::`vftable'
0x100403d5d  mov     [rcx], r9
0x100403d60  lea     r8, ??_7CGeometrySinkD@@6B@; const CGeometrySinkD::`vftable'
0x100403d67  mov     [rcx], r8
0x100403d6a  lea     rdx, ??_7CDecorator@@6B@; const CDecorator::`vftable'
0x100403d71  mov     [rcx], rdx
0x100403d74  lea     rax, [r12+8]
0x100403d79  mov     [rcx+8], rax
0x100403d7d  lea     rax, ??_7CFlattener@@6B@; const CFlattener::`vftable'
0x100403d84  mov     [rcx], rax
0x100403d87  xor     r10d, r10d
0x100403d8a  mov     [rcx+10h], r10
0x100403d8e  lea     rax, ??_7CPlanarFlattener@@6B@; const CPlanarFlattener::`vftable'
0x100403d95  mov     [rcx], rax
0x100403d98  lea     rax, [r12+490h]
0x100403da0  mov     [rcx+28h], rax
0x100403da4  mov     [rsp+68h+var_38], rax
0x100403da9  mov     [rax], r9
0x100403dac  mov     [rax], r8
0x100403daf  mov     [rax], rdx
0x100403db2  mov     [rax+8], r15
0x100403db6  lea     rcx, ??_7CArcReconstructor@@6B@; const CArcReconstructor::`vftable'
0x100403dbd  mov     [rax], rcx
0x100403dc0  mov     [rax+10h], r10b
0x100403dc4  mov     [rax+20h], r10
0x100403dc8  mov     [rax+18h], r10
0x100403dcc  mov     [rax+30h], r10b
0x100403dd0  mov     [rax+38h], r10
0x100403dd4  mov     [rax+40h], r10
0x100403dd8  mov     [rax+48h], r10b
0x100403ddc  mov     [rax+50h], r10
0x100403de0  mov     dword ptr [rax+58h], 80000000h
0x100403de7  mov     byte ptr [rax+5Ch], 1
0x100403deb  mov     [r12+40h], rax
0x100403df0  mov     [r12+0B0h], rax
0x100403df8  mov     rax, r12
0x100403dfb  mov     rbx, [rsp+68h+arg_10]
0x100403e03  add     rsp, 40h
0x100403e07  pop     r15
0x100403e09  pop     r14
0x100403e0b  pop     r12
0x100403e0d  pop     rsi
0x100403e0e  pop     rbp
0x100403e0f  retn
```
