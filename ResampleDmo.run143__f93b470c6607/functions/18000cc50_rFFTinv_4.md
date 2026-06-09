# rFFTinv_4

- ea: `0x18000cc50`
- end: `0x18000cc9d`
- name: `rFFTinv_4`
- size: `77`
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
- `0x1800483c0`
- `0x180049220`
- `0x180049fb0`

## pseudocode

```c
void __fastcall rFFTinv_4(float *a1, float *a2)
{
  float v2; // xmm3_4
  float v3; // xmm4_4
  float v4; // xmm1_4
  float v5; // xmm2_4

  v2 = *a1 + a1[1];
  v3 = *a1 - a1[1];
  v4 = a1[2] + a1[2];
  v5 = a1[3] + a1[3];
  a2[2] = v2 - v4;
  *a2 = v4 + v2;
  a2[3] = v5 + v3;
  a2[1] = v3 - v5;
}

```

## disassembly

```asm
0x18000cc50  movss   xmm4, dword ptr [rcx]
0x18000cc54  movss   xmm1, dword ptr [rcx+8]
0x18000cc59  movss   xmm2, dword ptr [rcx+0Ch]
0x18000cc5e  movaps  xmm3, xmm4
0x18000cc61  addss   xmm3, dword ptr [rcx+4]
0x18000cc66  subss   xmm4, dword ptr [rcx+4]
0x18000cc6b  addss   xmm1, xmm1
0x18000cc6f  movaps  xmm0, xmm3
0x18000cc72  subss   xmm0, xmm1
0x18000cc76  addss   xmm2, xmm2
0x18000cc7a  addss   xmm1, xmm3
0x18000cc7e  movss   dword ptr [rdx+8], xmm0
0x18000cc83  movss   dword ptr [rdx], xmm1
0x18000cc87  movaps  xmm0, xmm4
0x18000cc8a  subss   xmm0, xmm2
0x18000cc8e  addss   xmm2, xmm4
0x18000cc92  movss   dword ptr [rdx+0Ch], xmm2
0x18000cc97  movss   dword ptr [rdx+4], xmm0
0x18000cc9c  retn
```
