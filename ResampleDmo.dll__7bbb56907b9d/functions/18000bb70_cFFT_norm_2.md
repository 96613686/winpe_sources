# cFFT_norm_2

- ea: `0x18000bb70`
- end: `0x18000bbb8`
- name: `cFFT_norm_2`
- size: `72`
- prototype: ``
- caller_count: `12`
- callee_count: `0`
- tags: ``

## callers

- `0x18000d210`
- `0x18000df70`
- `0x18000e3c0`
- `0x18000f1d0`
- `0x18000f680`
- `0x180010490`
- `0x180047aa0`
- `0x1800486b0`
- `0x180048910`
- `0x180049510`
- `0x1800496a0`
- `0x18004a2a0`

## pseudocode

```c
void __fastcall cFFT_norm_2(float *a1, float *a2, float a3)
{
  float v3; // xmm1_4
  float v4; // xmm3_4

  v3 = a1[2];
  v4 = a1[3];
  a2[2] = (float)(*a1 - v3) * a3;
  *a2 = (float)(v3 + *a1) * a3;
  a2[3] = (float)(a1[1] - v4) * a3;
  a2[1] = (float)(v4 + a1[1]) * a3;
}

```

## disassembly

```asm
0x18000bb70  movss   xmm1, dword ptr [rcx+8]
0x18000bb75  movss   xmm0, dword ptr [rcx]
0x18000bb79  movss   xmm3, dword ptr [rcx+0Ch]
0x18000bb7e  subss   xmm0, xmm1
0x18000bb82  mulss   xmm0, xmm2
0x18000bb86  movss   dword ptr [rdx+8], xmm0
0x18000bb8b  addss   xmm1, dword ptr [rcx]
0x18000bb8f  mulss   xmm1, xmm2
0x18000bb93  movss   dword ptr [rdx], xmm1
0x18000bb97  movss   xmm0, dword ptr [rcx+4]
0x18000bb9c  subss   xmm0, xmm3
0x18000bba0  mulss   xmm0, xmm2
0x18000bba4  movss   dword ptr [rdx+0Ch], xmm0
0x18000bba9  addss   xmm3, dword ptr [rcx+4]
0x18000bbae  mulss   xmm3, xmm2
0x18000bbb2  movss   dword ptr [rdx+4], xmm3
0x18000bbb7  retn
```
