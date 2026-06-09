# rFFT_norm_2

- ea: `0x18000cbd0`
- end: `0x18000cbf3`
- name: `rFFT_norm_2`
- size: `35`
- prototype: ``
- caller_count: `18`
- callee_count: `0`
- tags: ``

## callers

- `0x18000d370`
- `0x18000d54c`
- `0x18000dd90`
- `0x18000e0cc`
- `0x18000e560`
- `0x18000e760`
- `0x18000efb0`
- `0x18000f364`
- `0x18000f820`
- `0x18000fa20`
- `0x180010270`
- `0x180010624`
- `0x180047c40`
- `0x1800483c0`
- `0x180048ab0`
- `0x180049220`
- `0x180049840`
- `0x180049fb0`

## pseudocode

```c
void __fastcall rFFT_norm_2(float *a1, float *a2, float a3)
{
  float v3; // xmm1_4
  float v4; // xmm0_4
  float v5; // xmm1_4

  v3 = a1[1];
  v4 = (float)(*a1 - v3) * a3;
  v5 = (float)(v3 + *a1) * a3;
  a2[1] = v4;
  *a2 = v5;
}

```

## disassembly

```asm
0x18000cbd0  movss   xmm1, dword ptr [rcx+4]
0x18000cbd5  movss   xmm0, dword ptr [rcx]
0x18000cbd9  subss   xmm0, xmm1
0x18000cbdd  addss   xmm1, dword ptr [rcx]
0x18000cbe1  mulss   xmm0, xmm2
0x18000cbe5  mulss   xmm1, xmm2
0x18000cbe9  movss   dword ptr [rdx+4], xmm0
0x18000cbee  movss   dword ptr [rdx], xmm1
0x18000cbf2  retn
```
