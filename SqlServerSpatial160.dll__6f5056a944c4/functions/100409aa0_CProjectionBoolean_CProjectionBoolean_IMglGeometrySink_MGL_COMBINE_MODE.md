# CProjectionBoolean::CProjectionBoolean(IMglGeometrySink *,MGL_COMBINE_MODE)

- ea: `0x100409aa0`
- end: `0x100409b6c`
- name: `??0CProjectionBoolean@@QEAA@PEAUIMglGeometrySink@@W4MGL_COMBINE_MODE@@@Z`
- size: `204`
- prototype: `CProjectionBoolean *__high(struct IMglGeometrySink *, enum MGL_COMBINE_MODE)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x10040abd0`
- `0x1004190d0`
- `0x10041aca0`

## callees

- `0x10043b830`
- `0x100445370`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CProjectionBoolean::CProjectionBoolean(__int64 a1, struct IMglGeometrySink *a2, int a3)
{
  __int64 v6; // rdi

  *(_QWORD *)a1 = &CProjectionScannerModule::`vftable';
  v6 = a1 + 96;
  *(_QWORD *)(a1 + 8) = a1 + 96;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  *(_QWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 40) = 0;
  *(_QWORD *)(a1 + 48) = 0;
  *(_QWORD *)(a1 + 56) = 0;
  *(_DWORD *)(a1 + 64) = 0;
  *(_QWORD *)(a1 + 80) = 0;
  *(_BYTE *)(a1 + 90) = 0;
  *(_QWORD *)a1 = &CProjectionBoolean::`vftable';
  C2ShapesProcessor::C2ShapesProcessor((C2ShapesProcessor *)(a1 + 96), 0, 0);
  *(_QWORD *)v6 = &CBoolean::`vftable';
  *(_QWORD *)(v6 + 560) = a1 + 672;
  *(_DWORD *)(v6 + 568) = a3;
  CReconstructor::CReconstructor((CReconstructor *)(a1 + 672), a2, 0, 0);
  *(_QWORD *)(a1 + 672) = &CStructuredReconstructor::`vftable';
  *(_BYTE *)(a1 + 816) = 0;
  *(_QWORD *)(a1 + 80) = a2;
  return a1;
}

```

## disassembly

```asm
0x100409aa0  mov     [rsp+arg_0], rcx
0x100409aa5  push    rbx
0x100409aa6  push    rbp
0x100409aa7  push    rsi
0x100409aa8  push    rdi
0x100409aa9  push    r14
0x100409aab  sub     rsp, 30h
0x100409aaf  mov     [rsp+58h+var_38], 0FFFFFFFFFFFFFFFEh
0x100409ab8  mov     esi, r8d
0x100409abb  mov     rbp, rdx
0x100409abe  mov     r14, rcx
0x100409ac1  lea     rax, ??_7CProjectionScannerModule@@6B@; const CProjectionScannerModule::`vftable'
0x100409ac8  mov     [rcx], rax
0x100409acb  lea     rdi, [rcx+60h]
0x100409acf  mov     [rcx+8], rdi
0x100409ad3  xor     eax, eax
0x100409ad5  mov     [rcx+10h], rax
0x100409ad9  mov     [rcx+18h], rax
0x100409add  mov     [rcx+20h], rax
0x100409ae1  mov     [rcx+28h], rax
0x100409ae5  mov     [rcx+30h], rax
0x100409ae9  mov     [rcx+38h], rax
0x100409aed  mov     [rcx+40h], eax
0x100409af0  mov     [rcx+50h], rax
0x100409af4  mov     [rcx+5Ah], al
0x100409af7  lea     rax, ??_7CProjectionBoolean@@6B@; const CProjectionBoolean::`vftable'
0x100409afe  mov     [rcx], rax
0x100409b01  mov     [rsp+58h+arg_8], rdi
0x100409b06  xor     r8d, r8d; bool
0x100409b09  xor     edx, edx; bool
0x100409b0b  mov     rcx, rdi; this
0x100409b0e  call    ??0C2ShapesProcessor@@QEAA@_N0@Z; C2ShapesProcessor::C2ShapesProcessor(bool,bool)
0x100409b13  nop
0x100409b14  lea     rax, ??_7CBoolean@@6B@; const CBoolean::`vftable'
0x100409b1b  mov     [rdi], rax
0x100409b1e  lea     rbx, [r14+2A0h]
0x100409b25  mov     [rdi+230h], rbx
0x100409b2c  mov     [rdi+238h], esi
0x100409b32  mov     [rsp+58h+arg_18], rbx
0x100409b37  xor     r9d, r9d; bool
0x100409b3a  xor     r8d, r8d; bool
0x100409b3d  mov     rdx, rbp; struct IMglGeometrySink *
0x100409b40  mov     rcx, rbx; this
0x100409b43  call    ??0CReconstructor@@QEAA@PEAUIMglGeometrySink@@_N1@Z; CReconstructor::CReconstructor(IMglGeometrySink *,bool,bool)
0x100409b48  nop
0x100409b49  lea     rax, ??_7CStructuredReconstructor@@6B@; const CStructuredReconstructor::`vftable'
0x100409b50  mov     [rbx], rax
0x100409b53  mov     byte ptr [rbx+90h], 0
0x100409b5a  mov     [r14+50h], rbp
0x100409b5e  mov     rax, r14
0x100409b61  add     rsp, 30h
0x100409b65  pop     r14
0x100409b67  pop     rdi
0x100409b68  pop     rsi
0x100409b69  pop     rbp
0x100409b6a  pop     rbx
0x100409b6b  retn
```
