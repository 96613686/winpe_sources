# rFFTfwd_4

- ea: `0x18000cc00`
- end: `0x18000cc43`
- name: `rFFTfwd_4`
- size: `67`
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
- `0x180047c40`
- `0x180048ab0`
- `0x180049840`

## pseudocode

```c
void __fastcall rFFTfwd_4(float *a1, float *a2)
{
  float v2; // xmm2_4
  float v3; // xmm3_4
  float v4; // xmm4_4
  float v5; // xmm1_4
  float v6; // xmm2_4

  v2 = a1[3];
  v3 = *a1 + a1[2];
  v4 = *a1 - a1[2];
  v5 = a1[1] + v2;
  v6 = v2 - a1[1];
  *a2 = v5 + v3;
  a2[1] = v3 - v5;
  a2[2] = v4;
  a2[3] = v6;
}

```

## disassembly

```asm
0x18000cc00  movss   xmm4, dword ptr [rcx]
0x18000cc04  movss   xmm2, dword ptr [rcx+0Ch]
0x18000cc09  movss   xmm1, dword ptr [rcx+4]
0x18000cc0e  movaps  xmm3, xmm4
0x18000cc11  addss   xmm3, dword ptr [rcx+8]
0x18000cc16  subss   xmm4, dword ptr [rcx+8]
0x18000cc1b  addss   xmm1, xmm2
0x18000cc1f  movaps  xmm0, xmm3
0x18000cc22  subss   xmm2, dword ptr [rcx+4]
0x18000cc27  subss   xmm0, xmm1
0x18000cc2b  addss   xmm1, xmm3
0x18000cc2f  movss   dword ptr [rdx], xmm1
0x18000cc33  movss   dword ptr [rdx+4], xmm0
0x18000cc38  movss   dword ptr [rdx+8], xmm4
0x18000cc3d  movss   dword ptr [rdx+0Ch], xmm2
0x18000cc42  retn
```
