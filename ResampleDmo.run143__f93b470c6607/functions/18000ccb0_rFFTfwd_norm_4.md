# rFFTfwd_norm_4

- ea: `0x18000ccb0`
- end: `0x18000cd06`
- name: `rFFTfwd_norm_4`
- size: `86`
- prototype: ``
- caller_count: `9`
- callee_count: `0`
- tags: ``

## callers

- `0x18000d370`
- `0x18000d54c`
- `0x18000e560`
- `0x18000e760`
- `0x18000f820`
- `0x18000fa20`
- `0x1800483c0`
- `0x180049220`
- `0x180049fb0`

## pseudocode

```c
void __fastcall rFFTfwd_norm_4(float *a1, float *a2, float a3)
{
  float v4; // xmm2_4
  float v5; // xmm3_4
  float v6; // xmm1_4
  float v7; // xmm2_4

  v4 = a1[3];
  v5 = (float)(*a1 + a1[2]) * a3;
  v6 = (float)(a1[1] + v4) * a3;
  v7 = (float)(v4 - a1[1]) * a3;
  a2[2] = (float)(*a1 - a1[2]) * a3;
  *a2 = v6 + v5;
  a2[1] = v5 - v6;
  a2[3] = v7;
}

```

## disassembly

```asm
0x18000ccb0  movss   xmm4, dword ptr [rcx]
0x18000ccb4  movss   xmm1, dword ptr [rcx+4]
0x18000ccb9  movaps  xmm0, xmm2
0x18000ccbc  movss   xmm2, dword ptr [rcx+0Ch]
0x18000ccc1  movaps  xmm3, xmm4
0x18000ccc4  addss   xmm3, dword ptr [rcx+8]
0x18000ccc9  subss   xmm4, dword ptr [rcx+8]
0x18000ccce  addss   xmm1, xmm2
0x18000ccd2  subss   xmm2, dword ptr [rcx+4]
0x18000ccd7  mulss   xmm3, xmm0
0x18000ccdb  mulss   xmm1, xmm0
0x18000ccdf  mulss   xmm4, xmm0
0x18000cce3  mulss   xmm2, xmm0
0x18000cce7  movaps  xmm0, xmm3
0x18000ccea  subss   xmm0, xmm1
0x18000ccee  addss   xmm1, xmm3
0x18000ccf2  movss   dword ptr [rdx+8], xmm4
0x18000ccf7  movss   dword ptr [rdx], xmm1
0x18000ccfb  movss   dword ptr [rdx+4], xmm0
0x18000cd00  movss   dword ptr [rdx+0Ch], xmm2
0x18000cd05  retn
```
