# CLineStringChecker::CompareSegmentsBySlope(CLineStringChecker::CSegment const &,CLineStringChecker::CSegment const &)

- ea: `0x10042c6f0`
- end: `0x10042c788`
- name: `?CompareSegmentsBySlope@CLineStringChecker@@AEAA?AW4SIGNINDICATOR@RobustIntersections@@AEBUCSegment@1@0@Z`
- size: `152`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x10042c570`
- `0x10042c790`

## callees

- `0x10042c6f0`
- `0x100447250`

## pseudocode

```c
__int64 __fastcall CLineStringChecker::CompareSegmentsBySlope(__int64 a1, unsigned int *a2, unsigned int *a3)
{
  __int64 v3; // r9
  double v4; // xmm0_8
  double v5; // xmm1_8
  double v6; // xmm2_8
  double v7; // xmm3_8

  v3 = *(_QWORD *)(a1 + 536);
  v4 = *(double *)(v3 + 16LL * *a2) - *(double *)(v3 + 16LL * a2[1]);
  v5 = *(double *)(v3 + 16LL * *a2 + 8) - *(double *)(v3 + 16LL * a2[1] + 8);
  v6 = *(double *)(v3 + 16LL * *a3) - *(double *)(v3 + 16LL * a3[1]);
  v7 = *(double *)(v3 + 16LL * *a3 + 8) - *(double *)(v3 + 16LL * a3[1] + 8);
  if ( v4 < 0.0 || v4 == 0.0 && v5 < 0.0 )
  {
    *(_QWORD *)&v4 ^= _xmm;
    *(_QWORD *)&v5 ^= _xmm;
  }
  if ( v6 < 0.0 || v6 == 0.0 && v7 < 0.0 )
  {
    *(_QWORD *)&v6 ^= _xmm;
    *(_QWORD *)&v7 ^= _xmm;
  }
  return ComputeDeterminantExactSign(v4, v5, v6, v7);
}

```

## disassembly

```asm
0x10042c6f0  mov     r9, [rcx+218h]
0x10042c6f7  xorps   xmm4, xmm4
0x10042c6fa  mov     r10d, [rdx]
0x10042c6fd  mov     ecx, [rdx+4]
0x10042c700  add     r10, r10
0x10042c703  mov     edx, [r8]
0x10042c706  add     rcx, rcx
0x10042c709  mov     eax, [r8+4]
0x10042c70d  add     rdx, rdx
0x10042c710  movsd   xmm5, qword ptr cs:__xmm@80000000000000008000000000000000
0x10042c718  add     rax, rax
0x10042c71b  movsd   xmm0, qword ptr [r9+r10*8]
0x10042c721  subsd   xmm0, qword ptr [r9+rcx*8]
0x10042c727  movsd   xmm1, qword ptr [r9+r10*8+8]
0x10042c72e  movsd   xmm2, qword ptr [r9+rdx*8]
0x10042c734  movsd   xmm3, qword ptr [r9+rdx*8+8]
0x10042c73b  subsd   xmm1, qword ptr [r9+rcx*8+8]
0x10042c742  comisd  xmm4, xmm0
0x10042c746  subsd   xmm2, qword ptr [r9+rax*8]
0x10042c74c  subsd   xmm3, qword ptr [r9+rax*8+8]
0x10042c753  ja      short loc_10042C763
0x10042c755  ucomisd xmm0, xmm4
0x10042c759  jp      short loc_10042C769
0x10042c75b  jnz     short loc_10042C769
0x10042c75d  comisd  xmm4, xmm1
0x10042c761  jbe     short loc_10042C769
0x10042c763  xorps   xmm0, xmm5
0x10042c766  xorps   xmm1, xmm5
0x10042c769  comisd  xmm4, xmm2
0x10042c76d  ja      short loc_10042C77D
0x10042c76f  ucomisd xmm2, xmm4
0x10042c773  jp      short loc_10042C783
0x10042c775  jnz     short loc_10042C783
0x10042c777  comisd  xmm4, xmm3
0x10042c77b  jbe     short loc_10042C783
0x10042c77d  xorps   xmm2, xmm5
0x10042c780  xorps   xmm3, xmm5
0x10042c783  jmp     ?ComputeDeterminantExactSign@@YA?AW4SIGNINDICATOR@RobustIntersections@@NNNN@Z; ComputeDeterminantExactSign(double,double,double,double)
```
