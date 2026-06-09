# CompareSegments(void *,void const *,void const *)

- ea: `0x10042c570`
- end: `0x10042c6e2`
- name: `?CompareSegments@@YAHPEAXPEBX1@Z`
- size: `370`
- prototype: `int __cdecl(void *, const void *, const void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x10042c570`
- `0x10042c6f0`
- `0x100447250`

## pseudocode

```c
__int64 __fastcall CompareSegments(_QWORD *a1, unsigned int *a2, unsigned int *a3)
{
  __int64 result; // rax
  __int64 v7; // rax
  double v8; // xmm0_8
  double v9; // xmm1_8
  __int64 v10; // r9
  unsigned int v11; // edx
  double v12; // xmm1_8
  double v13; // xmm0_8
  bool v14; // cc
  unsigned int v15; // ecx
  double v16; // xmm1_8
  double v17; // xmm0_8
  bool v18; // cc
  double v19; // xmm0_8
  double v20; // xmm1_8
  bool v21; // cc

  result = CLineStringChecker::CompareSegmentsBySlope();
  if ( !(_DWORD)result )
  {
    v7 = a1[67];
    v8 = *(double *)(v7 + 16LL * *a2) - *(double *)(v7 + 16LL * a2[1]);
    v9 = *(double *)(v7 + 16LL * *a2 + 8) - *(double *)(v7 + 16LL * a2[1] + 8);
    if ( v8 < 0.0 || v8 == 0.0 && v9 < 0.0 )
    {
      *(_QWORD *)&v8 ^= _xmm;
      *(_QWORD *)&v9 ^= _xmm;
    }
    result = ComputeDeterminantExactSign(
               v8,
               v9,
               *(double *)(v7 + 16LL * *a2) - *(double *)(v7 + 16LL * a3[1]),
               *(double *)(v7 + 16LL * *a2 + 8) - *(double *)(v7 + 16LL * a3[1] + 8));
    if ( !(_DWORD)result )
    {
      v10 = a1[67];
      v11 = a2[1];
      v12 = *(double *)(v10 + 16LL * v11);
      v13 = *(double *)(v10 + 16LL * *a2);
      if ( v13 == v12 )
        v14 = *(double *)(v10 + 16LL * a2[1] + 8) <= *(double *)(v10 + 16LL * *a2 + 8);
      else
        v14 = v12 <= v13;
      v15 = a3[1];
      if ( !v14 )
        v11 = *a2;
      v16 = *(double *)(v10 + 16LL * v15);
      v17 = *(double *)(v10 + 16LL * *a3);
      if ( v17 == v16 )
        v18 = *(double *)(v10 + 16LL * v15 + 8) <= *(double *)(v10 + 16LL * *a3 + 8);
      else
        v18 = v16 <= v17;
      if ( !v18 )
        v15 = *a3;
      v19 = *(double *)(v10 + 16LL * v11);
      v20 = *(double *)(v10 + 16LL * v15);
      if ( v19 == v20 )
        v21 = *(double *)(v10 + 16LL * v15 + 8) <= *(double *)(v10 + 16LL * v11 + 8);
      else
        v21 = v20 <= v19;
      if ( !v21 )
        v15 = v11;
      result = 1;
      if ( v15 == v11 )
        return 0xFFFFFFFFLL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x10042c570  mov     [rsp+arg_0], rbx
0x10042c575  mov     [rsp+arg_8], rsi
0x10042c57a  push    rdi
0x10042c57b  sub     rsp, 20h
0x10042c57f  mov     rdi, r8
0x10042c582  mov     rbx, rdx
0x10042c585  mov     rsi, rcx
0x10042c588  call    ?CompareSegmentsBySlope@CLineStringChecker@@AEAA?AW4SIGNINDICATOR@RobustIntersections@@AEBUCSegment@1@0@Z; CLineStringChecker::CompareSegmentsBySlope(CLineStringChecker::CSegment const &,CLineStringChecker::CSegment const &)
0x10042c58d  test    eax, eax
0x10042c58f  jnz     loc_10042C6D2
0x10042c595  mov     rax, [rsi+218h]
0x10042c59c  xorps   xmm4, xmm4
0x10042c59f  mov     r8d, [rbx]
0x10042c5a2  mov     ecx, [rbx+4]
0x10042c5a5  add     r8, r8
0x10042c5a8  mov     edx, [rdi+4]
0x10042c5ab  add     rcx, rcx
0x10042c5ae  add     rdx, rdx
0x10042c5b1  movsd   xmm2, qword ptr [rax+r8*8]
0x10042c5b7  movsd   xmm3, qword ptr [rax+r8*8+8]
0x10042c5be  movaps  xmm0, xmm2
0x10042c5c1  subsd   xmm0, qword ptr [rax+rcx*8]
0x10042c5c6  subsd   xmm2, qword ptr [rax+rdx*8]
0x10042c5cb  movaps  xmm1, xmm3
0x10042c5ce  subsd   xmm1, qword ptr [rax+rcx*8+8]
0x10042c5d4  subsd   xmm3, qword ptr [rax+rdx*8+8]
0x10042c5da  comisd  xmm4, xmm0
0x10042c5de  ja      short loc_10042C5EE
0x10042c5e0  ucomisd xmm0, xmm4
0x10042c5e4  jp      short loc_10042C5FC
0x10042c5e6  jnz     short loc_10042C5FC
0x10042c5e8  comisd  xmm4, xmm1
0x10042c5ec  jbe     short loc_10042C5FC
0x10042c5ee  xorps   xmm0, cs:__xmm@80000000000000008000000000000000
0x10042c5f5  xorps   xmm1, cs:__xmm@80000000000000008000000000000000
0x10042c5fc  call    ?ComputeDeterminantExactSign@@YA?AW4SIGNINDICATOR@RobustIntersections@@NNNN@Z; ComputeDeterminantExactSign(double,double,double,double)
0x10042c601  test    eax, eax
0x10042c603  jnz     loc_10042C6D2
0x10042c609  mov     r9, [rsi+218h]
0x10042c610  mov     edx, [rbx+4]
0x10042c613  mov     r8d, [rbx]
0x10042c616  mov     ecx, edx
0x10042c618  add     rcx, rcx
0x10042c61b  mov     eax, r8d
0x10042c61e  add     rax, rax
0x10042c621  movsd   xmm1, qword ptr [r9+rcx*8]
0x10042c627  movsd   xmm0, qword ptr [r9+rax*8]
0x10042c62d  ucomisd xmm0, xmm1
0x10042c631  jp      short loc_10042C645
0x10042c633  jnz     short loc_10042C645
0x10042c635  movsd   xmm0, qword ptr [r9+rcx*8+8]
0x10042c63c  comisd  xmm0, qword ptr [r9+rax*8+8]
0x10042c643  jmp     short loc_10042C649
0x10042c645  comisd  xmm1, xmm0
0x10042c649  mov     ecx, [rdi+4]
0x10042c64c  cmova   edx, r8d
0x10042c650  mov     r10d, [rdi]
0x10042c653  mov     r8d, ecx
0x10042c656  add     r8, r8
0x10042c659  mov     eax, r10d
0x10042c65c  add     rax, rax
0x10042c65f  movsd   xmm1, qword ptr [r9+r8*8]
0x10042c665  movsd   xmm0, qword ptr [r9+rax*8]
0x10042c66b  ucomisd xmm0, xmm1
0x10042c66f  jp      short loc_10042C683
0x10042c671  jnz     short loc_10042C683
0x10042c673  movsd   xmm0, qword ptr [r9+r8*8+8]
0x10042c67a  comisd  xmm0, qword ptr [r9+rax*8+8]
0x10042c681  jmp     short loc_10042C687
0x10042c683  comisd  xmm1, xmm0
0x10042c687  cmova   ecx, r10d
0x10042c68b  mov     eax, edx
0x10042c68d  add     rax, rax
0x10042c690  mov     r8d, ecx
0x10042c693  add     r8, r8
0x10042c696  movsd   xmm0, qword ptr [r9+rax*8]
0x10042c69c  movsd   xmm1, qword ptr [r9+r8*8]
0x10042c6a2  ucomisd xmm0, xmm1
0x10042c6a6  jp      short loc_10042C6BA
0x10042c6a8  jnz     short loc_10042C6BA
0x10042c6aa  movsd   xmm0, qword ptr [r9+r8*8+8]
0x10042c6b1  comisd  xmm0, qword ptr [r9+rax*8+8]
0x10042c6b8  jmp     short loc_10042C6BE
0x10042c6ba  comisd  xmm1, xmm0
0x10042c6be  cmova   ecx, edx
0x10042c6c1  mov     eax, 1
0x10042c6c6  cmp     ecx, edx
0x10042c6c8  mov     r8d, 0FFFFFFFFh
0x10042c6ce  cmovz   eax, r8d
0x10042c6d2  mov     rbx, [rsp+28h+arg_0]
0x10042c6d7  mov     rsi, [rsp+28h+arg_8]
0x10042c6dc  add     rsp, 20h
0x10042c6e0  pop     rdi
0x10042c6e1  retn
```
