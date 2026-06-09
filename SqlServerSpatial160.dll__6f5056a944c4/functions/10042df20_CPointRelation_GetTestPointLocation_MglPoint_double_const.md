# CPointRelation::GetTestPointLocation(MglPoint<double> const &)

- ea: `0x10042df20`
- end: `0x10042dfdd`
- name: `?GetTestPointLocation@CPointRelation@@IEAA?AW4SIDEINDICATOR@CLineSegmentIntersection@RobustIntersections@@AEBU?$MglPoint@N@@@Z`
- size: `189`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x10042d820`

## callees

- `0x10042df20`
- `0x100447250`

## pseudocode

```c
__int64 __fastcall CPointRelation::GetTestPointLocation(double *a1, double *a2)
{
  double v2; // xmm5_8
  double v3; // xmm2_8
  double v4; // xmm3_8
  double v5; // xmm6_8
  double v6; // xmm3_8

  v2 = a2[1] - a1[5];
  v3 = a1[6] - a1[4];
  v4 = a1[7] - a1[5];
  v5 = *a2 - a1[4];
  if ( COERCE_DOUBLE(*(_QWORD *)&v5 & _xmm) > 67108864.0
    || COERCE_DOUBLE(*(_QWORD *)&v2 & _xmm) > 67108864.0
    || COERCE_DOUBLE(*(_QWORD *)&v3 & _xmm) > 67108864.0
    || COERCE_DOUBLE(*(_QWORD *)&v4 & _xmm) > 67108864.0 )
  {
    return ComputeDeterminantExactSign(v5, v2, v3, v4);
  }
  v6 = v4 * v5 - v3 * v2;
  if ( v6 <= 0.0 )
    return (unsigned int)(v6 >= 0.0) - 1;
  else
    return 1;
}

```

## disassembly

```asm
0x10042df20  sub     rsp, 38h
0x10042df24  movsd   xmm1, qword ptr cs:__xmm@7fffffffffffffff7fffffffffffffff
0x10042df2c  movsd   xmm4, cs:__real@4190000000000000
0x10042df34  movsd   xmm5, qword ptr [rdx+8]
0x10042df39  movsd   xmm2, qword ptr [rcx+30h]
0x10042df3e  movsd   xmm3, qword ptr [rcx+38h]
0x10042df43  subsd   xmm5, qword ptr [rcx+28h]
0x10042df48  subsd   xmm2, qword ptr [rcx+20h]
0x10042df4d  subsd   xmm3, qword ptr [rcx+28h]
0x10042df52  movaps  [rsp+38h+var_18], xmm6
0x10042df57  movsd   xmm6, qword ptr [rdx]
0x10042df5b  subsd   xmm6, qword ptr [rcx+20h]
0x10042df60  movaps  xmm0, xmm6
0x10042df63  andps   xmm0, xmm1
0x10042df66  comisd  xmm4, xmm0
0x10042df6a  jb      short loc_10042DFC9
0x10042df6c  movaps  xmm0, xmm5
0x10042df6f  andps   xmm0, xmm1
0x10042df72  comisd  xmm4, xmm0
0x10042df76  jb      short loc_10042DFC9
0x10042df78  movaps  xmm0, xmm2
0x10042df7b  andps   xmm0, xmm1
0x10042df7e  comisd  xmm4, xmm0
0x10042df82  jb      short loc_10042DFC9
0x10042df84  movaps  xmm0, xmm3
0x10042df87  andps   xmm0, xmm1
0x10042df8a  comisd  xmm4, xmm0
0x10042df8e  jb      short loc_10042DFC9
0x10042df90  mulsd   xmm3, xmm6
0x10042df94  xorps   xmm0, xmm0
0x10042df97  mulsd   xmm2, xmm5
0x10042df9b  subsd   xmm3, xmm2
0x10042df9f  comisd  xmm3, xmm0
0x10042dfa3  jbe     short loc_10042DFB4
0x10042dfa5  mov     eax, 1
0x10042dfaa  movaps  xmm6, [rsp+38h+var_18]
0x10042dfaf  add     rsp, 38h
0x10042dfb3  retn
0x10042dfb4  xor     eax, eax
0x10042dfb6  comisd  xmm0, xmm3
0x10042dfba  setbe   al
0x10042dfbd  dec     eax
0x10042dfbf  movaps  xmm6, [rsp+38h+var_18]
0x10042dfc4  add     rsp, 38h
0x10042dfc8  retn
0x10042dfc9  movaps  xmm1, xmm5
0x10042dfcc  movaps  xmm0, xmm6
0x10042dfcf  movaps  xmm6, [rsp+38h+var_18]
0x10042dfd4  add     rsp, 38h
0x10042dfd8  jmp     ?ComputeDeterminantExactSign@@YA?AW4SIGNINDICATOR@RobustIntersections@@NNNN@Z; ComputeDeterminantExactSign(double,double,double,double)
```
