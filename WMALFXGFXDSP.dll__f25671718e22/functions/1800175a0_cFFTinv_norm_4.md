# cFFTinv_norm_4

- ea: `0x1800175a0`
- end: `0x180017678`
- name: `cFFTinv_norm_4`
- size: `216`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x1800196c0`
- `0x18001a900`
- `0x18001bba0`
- `0x18001c700`
- `0x18001d570`
- `0x18001e300`

## pseudocode

```c
void __fastcall cFFTinv_norm_4(float *a1, float *a2, float a3)
{
  float v3; // xmm1_4
  float v4; // xmm6_4
  float v5; // xmm3_4
  float v6; // xmm1_4
  float v7; // xmm7_4
  float v8; // xmm3_4
  float v9; // xmm4_4
  float v10; // xmm1_4
  float v11; // xmm2_4

  v3 = a1[2];
  v4 = (float)(v3 - a1[6]) * a3;
  v5 = (float)(*a1 + a1[4]) * a3;
  v6 = (float)(v3 + a1[6]) * a3;
  v7 = (float)(*a1 - a1[4]) * a3;
  *a2 = v6 + v5;
  a2[4] = v5 - v6;
  v8 = (float)(a1[1] + a1[5]) * a3;
  v9 = (float)(a1[1] - a1[5]) * a3;
  v10 = (float)(a1[3] + a1[7]) * a3;
  v11 = (float)(a1[3] - a1[7]) * a3;
  a2[1] = v10 + v8;
  a2[5] = v8 - v10;
  a2[2] = v7 - v11;
  a2[6] = v11 + v7;
  a2[7] = v9 - v4;
  a2[3] = v9 + v4;
}

```

## disassembly

```asm
0x1800175a0  sub     rsp, 28h
0x1800175a4  movaps  xmm5, xmm2
0x1800175a7  movaps  [rsp+28h+var_18], xmm6
0x1800175ac  movss   xmm6, dword ptr [rcx+8]
0x1800175b1  movaps  xmm1, xmm6
0x1800175b4  movaps  [rsp+28h+var_28], xmm7
0x1800175b8  movss   xmm7, dword ptr [rcx]
0x1800175bc  subss   xmm6, dword ptr [rcx+18h]
0x1800175c1  movaps  xmm3, xmm7
0x1800175c4  addss   xmm3, dword ptr [rcx+10h]
0x1800175c9  addss   xmm1, dword ptr [rcx+18h]
0x1800175ce  subss   xmm7, dword ptr [rcx+10h]
0x1800175d3  mulss   xmm6, xmm5
0x1800175d7  mulss   xmm3, xmm5
0x1800175db  mulss   xmm1, xmm5
0x1800175df  mulss   xmm7, xmm5
0x1800175e3  movaps  xmm0, xmm1
0x1800175e6  addss   xmm0, xmm3
0x1800175ea  subss   xmm3, xmm1
0x1800175ee  movss   dword ptr [rdx], xmm0
0x1800175f2  movss   dword ptr [rdx+10h], xmm3
0x1800175f7  movss   xmm4, dword ptr [rcx+4]
0x1800175fc  movaps  xmm3, xmm4
0x1800175ff  subss   xmm4, dword ptr [rcx+14h]
0x180017604  movss   xmm2, dword ptr [rcx+0Ch]
0x180017609  addss   xmm3, dword ptr [rcx+14h]
0x18001760e  movaps  xmm1, xmm2
0x180017611  mulss   xmm3, xmm5
0x180017615  mulss   xmm4, xmm5
0x180017619  addss   xmm1, dword ptr [rcx+1Ch]
0x18001761e  subss   xmm2, dword ptr [rcx+1Ch]
0x180017623  mulss   xmm1, xmm5
0x180017627  mulss   xmm2, xmm5
0x18001762b  movaps  xmm0, xmm1
0x18001762e  addss   xmm0, xmm3
0x180017632  subss   xmm3, xmm1
0x180017636  movss   dword ptr [rdx+4], xmm0
0x18001763b  movss   dword ptr [rdx+14h], xmm3
0x180017640  movaps  xmm0, xmm7
0x180017643  subss   xmm0, xmm2
0x180017647  addss   xmm2, xmm7
0x18001764b  movaps  xmm7, [rsp+28h+var_28]
0x18001764f  movss   dword ptr [rdx+8], xmm0
0x180017654  movss   dword ptr [rdx+18h], xmm2
0x180017659  movaps  xmm0, xmm4
0x18001765c  subss   xmm0, xmm6
0x180017660  addss   xmm4, xmm6
0x180017664  movaps  xmm6, [rsp+28h+var_18]
0x180017669  movss   dword ptr [rdx+1Ch], xmm0
0x18001766e  movss   dword ptr [rdx+0Ch], xmm4
0x180017673  add     rsp, 28h
0x180017677  retn
```
