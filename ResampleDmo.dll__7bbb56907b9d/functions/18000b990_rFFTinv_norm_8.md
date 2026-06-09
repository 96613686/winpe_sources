# rFFTinv_norm_8

- ea: `0x18000b990`
- end: `0x18000badb`
- name: `rFFTinv_norm_8`
- size: `331`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x18000dd90`
- `0x18000e0cc`
- `0x18000efb0`
- `0x18000f364`
- `0x180010270`
- `0x180010624`

## pseudocode

```c
_UNKNOWN **__fastcall rFFTinv_norm_8(float *a1, float *a2, float a3)
{
  _UNKNOWN **result; // rax
  float v5; // xmm1_4
  float v6; // xmm0_4
  float v7; // xmm9_4
  float v8; // xmm8_4
  float v9; // xmm7_4
  float v10; // xmm9_4
  float v11; // xmm6_4
  float v12; // xmm8_4
  float v13; // xmm3_4
  float v14; // xmm4_4
  float v15; // xmm1_4
  float v16; // xmm3_4
  float v17; // xmm2_4
  float v18; // xmm4_4
  float v19; // xmm2_4
  float v20; // xmm0_4
  float v21; // xmm4_4
  _UNKNOWN *retaddr; // [rsp+48h] [rbp+0h] BYREF

  result = &retaddr;
  v5 = (float)(*a1 - a1[1]) * a3;
  v6 = (float)(*a1 + a1[1]) * a3;
  v7 = (float)(a1[5] + a1[5]) * a3;
  v8 = (float)(a1[4] + a1[4]) * a3;
  v9 = v5 - v7;
  v10 = v7 + v5;
  v11 = v6 - v8;
  v12 = v8 + v6;
  a2[1] = v11;
  a2[4] = v9;
  a2[5] = v10;
  *a2 = v12;
  v13 = a1[2];
  v14 = a1[7];
  v15 = (float)(v13 - a1[6]) * a3;
  v16 = (float)((float)(v13 + a1[6]) * a3) + (float)((float)(v13 + a1[6]) * a3);
  v17 = a1[3] - v14;
  v18 = (float)(v14 + a1[3]) * a3;
  v19 = (float)(v17 * a3) + (float)(v17 * a3);
  v20 = (float)(v15 - v18) * 1.4142135;
  v21 = (float)(v18 + v15) * -1.4142135;
  a2[5] = v9 - v20;
  a2[4] = v12 - v16;
  *a2 = v16 + v12;
  a2[1] = v9 + v20;
  a2[6] = v11 + v19;
  a2[2] = v11 - v19;
  a2[7] = v10 - v21;
  a2[3] = v10 + v21;
  return result;
}

```

## disassembly

```asm
0x18000b990  mov     rax, rsp
0x18000b993  sub     rsp, 48h
0x18000b997  movss   xmm1, dword ptr [rcx]
0x18000b99b  movaps  xmm5, xmm2
0x18000b99e  movaps  xmmword ptr [rax-18h], xmm6
0x18000b9a2  movaps  xmm0, xmm1
0x18000b9a5  movaps  xmmword ptr [rax-28h], xmm7
0x18000b9a9  movaps  xmmword ptr [rax-38h], xmm8
0x18000b9ae  subss   xmm1, dword ptr [rcx+4]
0x18000b9b3  movss   xmm8, dword ptr [rcx+10h]
0x18000b9b9  addss   xmm0, dword ptr [rcx+4]
0x18000b9be  movaps  [rsp+48h+var_48], xmm9
0x18000b9c3  movss   xmm9, dword ptr [rcx+14h]
0x18000b9c9  mulss   xmm1, xmm5
0x18000b9cd  movaps  xmm7, xmm1
0x18000b9d0  mulss   xmm0, xmm5
0x18000b9d4  addss   xmm9, xmm9
0x18000b9d9  addss   xmm8, xmm8
0x18000b9de  movaps  xmm6, xmm0
0x18000b9e1  mulss   xmm9, xmm5
0x18000b9e6  mulss   xmm8, xmm5
0x18000b9eb  subss   xmm7, xmm9
0x18000b9f0  addss   xmm9, xmm1
0x18000b9f5  subss   xmm6, xmm8
0x18000b9fa  addss   xmm8, xmm0
0x18000b9ff  movss   dword ptr [rdx+4], xmm6
0x18000ba04  movss   dword ptr [rdx+10h], xmm7
0x18000ba09  movss   dword ptr [rdx+14h], xmm9
0x18000ba0f  movss   dword ptr [rdx], xmm8
0x18000ba14  movss   xmm1, dword ptr [rcx+8]
0x18000ba19  movaps  xmm3, xmm1
0x18000ba1c  subss   xmm1, dword ptr [rcx+18h]
0x18000ba21  addss   xmm3, dword ptr [rcx+18h]
0x18000ba26  movss   xmm4, dword ptr [rcx+1Ch]
0x18000ba2b  mulss   xmm1, xmm5
0x18000ba2f  mulss   xmm3, xmm5
0x18000ba33  movaps  xmm0, xmm1
0x18000ba36  movss   xmm2, dword ptr [rcx+0Ch]
0x18000ba3b  addss   xmm3, xmm3
0x18000ba3f  subss   xmm2, xmm4
0x18000ba43  addss   xmm4, dword ptr [rcx+0Ch]
0x18000ba48  mulss   xmm2, xmm5
0x18000ba4c  mulss   xmm4, xmm5
0x18000ba50  addss   xmm2, xmm2
0x18000ba54  subss   xmm0, xmm4
0x18000ba58  addss   xmm4, xmm1
0x18000ba5c  movaps  xmm1, xmm7
0x18000ba5f  mulss   xmm0, cs:__real@3fb504f3
0x18000ba67  mulss   xmm4, cs:__real@bfb504f3
0x18000ba6f  subss   xmm7, xmm0
0x18000ba73  addss   xmm1, xmm0
0x18000ba77  movaps  xmm0, xmm8
0x18000ba7b  subss   xmm0, xmm3
0x18000ba7f  addss   xmm3, xmm8
0x18000ba84  movss   dword ptr [rdx+14h], xmm7
0x18000ba89  movaps  xmm7, xmmword ptr [rax-28h]
0x18000ba8d  movaps  xmm8, xmmword ptr [rax-38h]
0x18000ba92  movss   dword ptr [rdx+10h], xmm0
0x18000ba97  movss   dword ptr [rdx], xmm3
0x18000ba9b  movss   dword ptr [rdx+4], xmm1
0x18000baa0  movaps  xmm0, xmm6
0x18000baa3  addss   xmm0, xmm2
0x18000baa7  subss   xmm6, xmm2
0x18000baab  movss   dword ptr [rdx+18h], xmm0
0x18000bab0  movss   dword ptr [rdx+8], xmm6
0x18000bab5  movaps  xmm6, xmmword ptr [rax-18h]
0x18000bab9  movaps  xmm0, xmm9
0x18000babd  subss   xmm9, xmm4
0x18000bac2  addss   xmm0, xmm4
0x18000bac6  movss   dword ptr [rdx+1Ch], xmm9
0x18000bacc  movss   dword ptr [rdx+0Ch], xmm0
0x18000bad1  movaps  xmm9, [rsp+48h+var_48]
0x18000bad6  add     rsp, 48h
0x18000bada  retn
```
