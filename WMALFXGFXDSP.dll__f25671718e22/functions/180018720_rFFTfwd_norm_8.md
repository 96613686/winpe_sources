# rFFTfwd_norm_8

- ea: `0x180018720`
- end: `0x18001883a`
- name: `rFFTfwd_norm_8`
- size: `282`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180018af0`
- `0x180018ccc`
- `0x180019cb0`
- `0x180019eb0`
- `0x18001af50`
- `0x18001b150`

## pseudocode

```c
void __fastcall rFFTfwd_norm_8(float *a1, float *a2, float a3)
{
  float v4; // xmm3_4
  float v5; // xmm5_4
  float v6; // xmm4_4
  float v7; // xmm5_4
  float v8; // xmm2_4
  float v9; // xmm3_4
  float v10; // xmm1_4
  float v11; // xmm6_4
  float v12; // xmm0_4
  float v13; // xmm5_4
  float v14; // xmm0_4
  float v15; // xmm1_4
  float v16; // xmm4_4
  float v17; // xmm5_4
  float v18; // xmm2_4
  float v19; // xmm3_4

  v4 = (float)(*a1 + a1[4]) * a3;
  v5 = (float)(a1[2] + a1[6]) * a3;
  v6 = *a1 - a1[4];
  a2[6] = (float)(a1[2] - a1[6]) * a3;
  a2[4] = v4 - v5;
  v7 = v5 + v4;
  a2[2] = v6 * a3;
  *a2 = v7;
  v8 = (float)(a1[1] + a1[5]) * a3;
  v9 = (float)(a1[1] - a1[5]) * a3;
  v10 = (float)((float)(a1[3] + a1[7]) * a3) + v8;
  v11 = (float)(a1[3] - a1[7]) * a3;
  a2[5] = (float)((float)(a1[3] + a1[7]) * a3) - v8;
  v12 = v7;
  v13 = v7 + v10;
  v14 = v12 - v10;
  v15 = a2[6];
  *a2 = v13;
  a2[1] = v14;
  v16 = (float)(v9 + v11) * -0.70710677;
  v17 = (float)(v9 - v11) * 0.70710677;
  v18 = a2[2] - v17;
  v19 = a2[2] + v17;
  a2[3] = v16 - v15;
  a2[2] = v19;
  a2[6] = v18;
  a2[7] = v15 + v16;
}

```

## disassembly

```asm
0x180018720  sub     rsp, 28h
0x180018724  movss   xmm4, dword ptr [rcx]
0x180018728  movss   xmm1, dword ptr [rcx+8]
0x18001872d  movaps  [rsp+28h+var_18], xmm6
0x180018732  movaps  xmm5, xmm1
0x180018735  movaps  xmm3, xmm4
0x180018738  movaps  [rsp+28h+var_28], xmm7
0x18001873c  addss   xmm3, dword ptr [rcx+10h]
0x180018741  addss   xmm5, dword ptr [rcx+18h]
0x180018746  subss   xmm1, dword ptr [rcx+18h]
0x18001874b  movaps  xmm7, xmm2
0x18001874e  mulss   xmm3, xmm7
0x180018752  mulss   xmm5, xmm7
0x180018756  mulss   xmm1, xmm7
0x18001875a  movaps  xmm0, xmm3
0x18001875d  subss   xmm4, dword ptr [rcx+10h]
0x180018762  subss   xmm0, xmm5
0x180018766  movss   dword ptr [rdx+18h], xmm1
0x18001876b  mulss   xmm4, xmm7
0x18001876f  movss   dword ptr [rdx+10h], xmm0
0x180018774  addss   xmm5, xmm3
0x180018778  movss   dword ptr [rdx+8], xmm4
0x18001877d  movss   dword ptr [rdx], xmm5
0x180018781  movss   xmm6, dword ptr [rcx+0Ch]
0x180018786  movss   xmm3, dword ptr [rcx+4]
0x18001878b  movaps  xmm1, xmm6
0x18001878e  movaps  xmm2, xmm3
0x180018791  addss   xmm1, dword ptr [rcx+1Ch]
0x180018796  addss   xmm2, dword ptr [rcx+14h]
0x18001879b  subss   xmm3, dword ptr [rcx+14h]
0x1800187a0  mulss   xmm1, xmm7
0x1800187a4  mulss   xmm2, xmm7
0x1800187a8  mulss   xmm3, xmm7
0x1800187ac  movaps  xmm0, xmm1
0x1800187af  subss   xmm6, dword ptr [rcx+1Ch]
0x1800187b4  subss   xmm0, xmm2
0x1800187b8  addss   xmm1, xmm2
0x1800187bc  mulss   xmm6, xmm7
0x1800187c0  movaps  xmm7, [rsp+28h+var_28]
0x1800187c4  movss   dword ptr [rdx+14h], xmm0
0x1800187c9  movss   xmm4, xmm3
0x1800187cd  movaps  xmm0, xmm5
0x1800187d0  addss   xmm5, xmm1
0x1800187d4  subss   xmm0, xmm1
0x1800187d8  movss   xmm1, dword ptr [rdx+18h]
0x1800187dd  movss   dword ptr [rdx], xmm5
0x1800187e1  addss   xmm4, xmm6
0x1800187e5  movss   dword ptr [rdx+4], xmm0
0x1800187ea  movaps  xmm5, xmm3
0x1800187ed  mulss   xmm4, cs:__real@bf3504f3
0x1800187f5  movss   xmm3, dword ptr [rdx+8]
0x1800187fa  subss   xmm5, xmm6
0x1800187fe  movaps  xmm6, [rsp+28h+var_18]
0x180018803  movaps  xmm2, xmm3
0x180018806  movaps  xmm0, xmm4
0x180018809  mulss   xmm5, cs:__real@3f3504f3
0x180018811  subss   xmm0, xmm1
0x180018815  addss   xmm1, xmm4
0x180018819  subss   xmm2, xmm5
0x18001881d  addss   xmm3, xmm5
0x180018821  movss   dword ptr [rdx+0Ch], xmm0
0x180018826  movss   dword ptr [rdx+8], xmm3
0x18001882b  movss   dword ptr [rdx+18h], xmm2
0x180018830  movss   dword ptr [rdx+1Ch], xmm1
0x180018835  add     rsp, 28h
0x180018839  retn
```
