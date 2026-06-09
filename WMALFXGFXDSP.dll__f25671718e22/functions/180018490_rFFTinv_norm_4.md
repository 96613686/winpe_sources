# rFFTinv_norm_4

- ea: `0x180018490`
- end: `0x1800184f0`
- name: `rFFTinv_norm_4`
- size: `96`
- prototype: ``
- caller_count: `9`
- callee_count: `0`
- tags: ``

## callers

- `0x1800194e0`
- `0x18001981c`
- `0x18001a6e0`
- `0x18001aa94`
- `0x18001b980`
- `0x18001bd34`
- `0x18001d3d0`
- `0x18001e160`
- `0x18001ea70`

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
0x180018490  movss   xmm4, dword ptr [rcx]
0x180018494  movss   xmm1, dword ptr [rcx+8]
0x180018499  movaps  xmm0, xmm2
0x18001849c  movss   xmm2, dword ptr [rcx+0Ch]
0x1800184a1  movaps  xmm3, xmm4
0x1800184a4  addss   xmm3, dword ptr [rcx+4]
0x1800184a9  subss   xmm4, dword ptr [rcx+4]
0x1800184ae  mulss   xmm3, xmm0
0x1800184b2  addss   xmm1, xmm1
0x1800184b6  mulss   xmm1, xmm0
0x1800184ba  mulss   xmm4, xmm0
0x1800184be  addss   xmm2, xmm2
0x1800184c2  mulss   xmm2, xmm0
0x1800184c6  movaps  xmm0, xmm1
0x1800184c9  addss   xmm0, xmm3
0x1800184cd  subss   xmm3, xmm1
0x1800184d1  movss   dword ptr [rdx], xmm0
0x1800184d5  movss   dword ptr [rdx+8], xmm3
0x1800184da  movaps  xmm0, xmm4
0x1800184dd  subss   xmm0, xmm2
0x1800184e1  addss   xmm2, xmm4
0x1800184e5  movss   dword ptr [rdx+0Ch], xmm2
0x1800184ea  movss   dword ptr [rdx+4], xmm0
0x1800184ef  retn
```
