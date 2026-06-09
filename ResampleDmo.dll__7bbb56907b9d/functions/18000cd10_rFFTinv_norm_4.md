# rFFTinv_norm_4

- ea: `0x18000cd10`
- end: `0x18000cd70`
- name: `rFFTinv_norm_4`
- size: `96`
- prototype: ``
- caller_count: `9`
- callee_count: `0`
- tags: ``

## callers

- `0x18000dd90`
- `0x18000e0cc`
- `0x18000efb0`
- `0x18000f364`
- `0x180010270`
- `0x180010624`
- `0x180048910`
- `0x1800496a0`
- `0x180049fb0`

## pseudocode

```c
void __fastcall rFFTinv_norm_4(float *a1, float *a2, float a3)
{
  float v3; // xmm3_4
  float v4; // xmm1_4
  float v5; // xmm4_4
  float v6; // xmm2_4

  v3 = (float)(*a1 + a1[1]) * a3;
  v4 = (float)(a1[2] + a1[2]) * a3;
  v5 = (float)(*a1 - a1[1]) * a3;
  v6 = (float)(a1[3] + a1[3]) * a3;
  *a2 = v4 + v3;
  a2[2] = v3 - v4;
  a2[3] = v6 + v5;
  a2[1] = v5 - v6;
}

```

## disassembly

```asm
0x18000cd10  movss   xmm4, dword ptr [rcx]
0x18000cd14  movss   xmm1, dword ptr [rcx+8]
0x18000cd19  movaps  xmm0, xmm2
0x18000cd1c  movss   xmm2, dword ptr [rcx+0Ch]
0x18000cd21  movaps  xmm3, xmm4
0x18000cd24  addss   xmm3, dword ptr [rcx+4]
0x18000cd29  subss   xmm4, dword ptr [rcx+4]
0x18000cd2e  mulss   xmm3, xmm0
0x18000cd32  addss   xmm1, xmm1
0x18000cd36  mulss   xmm1, xmm0
0x18000cd3a  mulss   xmm4, xmm0
0x18000cd3e  addss   xmm2, xmm2
0x18000cd42  mulss   xmm2, xmm0
0x18000cd46  movaps  xmm0, xmm1
0x18000cd49  addss   xmm0, xmm3
0x18000cd4d  subss   xmm3, xmm1
0x18000cd51  movss   dword ptr [rdx], xmm0
0x18000cd55  movss   dword ptr [rdx+8], xmm3
0x18000cd5a  movaps  xmm0, xmm4
0x18000cd5d  subss   xmm0, xmm2
0x18000cd61  addss   xmm2, xmm4
0x18000cd65  movss   dword ptr [rdx+0Ch], xmm2
0x18000cd6a  movss   dword ptr [rdx+4], xmm0
0x18000cd6f  retn
```
