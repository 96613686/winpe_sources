# CSingleSideReducer::FIsPointCloseToLine(CMglPoint<double> const &,CMglPoint<double> const &,CMglPoint<double> const &)

- ea: `0x100437f10`
- end: `0x10043801e`
- name: `?FIsPointCloseToLine@CSingleSideReducer@@AEAA_NAEBV?$CMglPoint@N@@00@Z`
- size: `270`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x100438030`

## callees

- `0x100437f10`

## pseudocode

```c
bool __fastcall CSingleSideReducer::FIsPointCloseToLine(__int64 a1, double *a2, double *a3, double *a4)
{
  double v4; // xmm4_8
  double v5; // xmm2_8
  double v6; // xmm6_8
  double v7; // xmm7_8
  double v8; // xmm8_8
  bool v9; // cf
  double v10; // xmm5_8
  double v11; // xmm3_8
  double v12; // xmm7_8
  double v13; // xmm2_8

  v4 = a2[1] - a3[1];
  v5 = a3[1] - a4[1];
  v6 = *a2 - *a3;
  v7 = *a3 - *a4;
  v8 = *(double *)(a1 + 32);
  if ( v4 * v5 + v6 * v7 <= 0.0 )
  {
    v10 = *a2 - *a4;
    v11 = a2[1] - a4[1];
    v12 = v7 * -1.0;
    v13 = v5 * -1.0;
    if ( v11 * v13 + v10 * v12 <= 0.0 )
      v9 = (v13 * v13 + v12 * v12) * v8 < (v12 * v4 - v13 * v6) * (v12 * v4 - v13 * v6);
    else
      v9 = v8 < v11 * v11 + v10 * v10;
  }
  else
  {
    v9 = v8 < v4 * v4 + v6 * v6;
  }
  return !v9;
}

```

## disassembly

```asm
0x100437f10  sub     rsp, 48h
0x100437f14  movsd   xmm5, qword ptr [rdx]
0x100437f18  movsd   xmm3, qword ptr [rdx+8]
0x100437f1d  movsd   xmm2, qword ptr [r8+8]
0x100437f23  movaps  xmm4, xmm3
0x100437f26  subsd   xmm4, qword ptr [r8+8]
0x100437f2c  subsd   xmm2, qword ptr [r9+8]
0x100437f32  movaps  [rsp+48h+var_18], xmm6
0x100437f37  movaps  xmm6, xmm5
0x100437f3a  subsd   xmm6, qword ptr [r8]
0x100437f3f  movaps  [rsp+48h+var_28], xmm7
0x100437f44  movsd   xmm7, qword ptr [r8]
0x100437f49  movaps  xmm1, xmm4
0x100437f4c  subsd   xmm7, qword ptr [r9]
0x100437f51  movaps  [rsp+48h+var_38], xmm8
0x100437f57  movsd   xmm8, qword ptr [rcx+20h]
0x100437f5d  movaps  xmm0, xmm6
0x100437f60  mulsd   xmm1, xmm2
0x100437f64  movaps  [rsp+48h+var_48], xmm11
0x100437f69  xorps   xmm11, xmm11
0x100437f6d  mulsd   xmm0, xmm7
0x100437f71  addsd   xmm1, xmm0
0x100437f75  comisd  xmm1, xmm11
0x100437f7a  jbe     short loc_100437F8F
0x100437f7c  mulsd   xmm4, xmm4
0x100437f80  mulsd   xmm6, xmm6
0x100437f84  addsd   xmm4, xmm6
0x100437f88  comisd  xmm8, xmm4
0x100437f8d  jmp     short loc_100438001
0x100437f8f  subsd   xmm5, qword ptr [r9]
0x100437f94  subsd   xmm3, qword ptr [r9+8]
0x100437f9a  mulsd   xmm7, cs:__real@bff0000000000000
0x100437fa2  mulsd   xmm2, cs:__real@bff0000000000000
0x100437faa  movaps  xmm1, xmm3
0x100437fad  movaps  xmm0, xmm5
0x100437fb0  mulsd   xmm0, xmm7
0x100437fb4  mulsd   xmm1, xmm2
0x100437fb8  addsd   xmm1, xmm0
0x100437fbc  comisd  xmm1, xmm11
0x100437fc1  jbe     short loc_100437FD6
0x100437fc3  mulsd   xmm3, xmm3
0x100437fc7  mulsd   xmm5, xmm5
0x100437fcb  addsd   xmm3, xmm5
0x100437fcf  comisd  xmm8, xmm3
0x100437fd4  jmp     short loc_100438001
0x100437fd6  movaps  xmm0, xmm2
0x100437fd9  movaps  xmm1, xmm7
0x100437fdc  mulsd   xmm1, xmm4
0x100437fe0  mulsd   xmm2, xmm2
0x100437fe4  mulsd   xmm0, xmm6
0x100437fe8  mulsd   xmm7, xmm7
0x100437fec  subsd   xmm1, xmm0
0x100437ff0  addsd   xmm2, xmm7
0x100437ff4  mulsd   xmm1, xmm1
0x100437ff8  mulsd   xmm2, xmm8
0x100437ffd  comisd  xmm2, xmm1
0x100438001  movaps  xmm6, [rsp+48h+var_18]
0x100438006  setnb   al
0x100438009  movaps  xmm7, [rsp+48h+var_28]
0x10043800e  movaps  xmm8, [rsp+48h+var_38]
0x100438014  movaps  xmm11, [rsp+48h+var_48]
0x100438019  add     rsp, 48h
0x10043801d  retn
```
