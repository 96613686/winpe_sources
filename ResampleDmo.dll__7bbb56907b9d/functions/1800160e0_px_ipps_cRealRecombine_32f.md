# px_ipps_cRealRecombine_32f

- ea: `0x1800160e0`
- end: `0x1800162a0`
- name: `px_ipps_cRealRecombine_32f`
- size: `448`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000d370`
- `0x18000d54c`

## callees

- `0x1800160e0`

## pseudocode

```c
void __fastcall px_ipps_cRealRecombine_32f(__int64 a1, int a2, int a3, __int64 a4)
{
  int v4; // eax
  float *v5; // r10
  __int64 v6; // r8
  float *v7; // r11
  __int64 v8; // r9
  float v9; // xmm3_4
  float v10; // xmm8_4
  float v11; // xmm4_4
  float v12; // xmm1_4
  float v13; // xmm5_4
  float v14; // xmm3_4
  float v15; // xmm9_4
  float v16; // xmm0_4
  float *v17; // r8
  __int64 v18; // r9
  float *v19; // r10
  __int64 v20; // rcx
  float v21; // xmm6_4
  float v22; // xmm8_4
  float v23; // xmm9_4
  float v24; // xmm5_4
  float v25; // xmm3_4
  float v26; // xmm2_4
  float v27; // xmm4_4
  float v28; // xmm1_4
  float v29; // xmm6_4

  if ( a2 != 1 )
  {
    v4 = 2 * a2 - 2;
    if ( a3 <= 0 )
    {
      if ( a2 > 2 )
      {
        v17 = (float *)(a1 + 12);
        v18 = a4 - a1;
        v19 = (float *)(a1 + 4LL * v4);
        v20 = ((unsigned int)(a2 - 3) >> 1) + 1;
        do
        {
          v21 = *(float *)((char *)v17 + v18 - 4);
          v22 = v19[1];
          v23 = *v19;
          v24 = *v17;
          v25 = *(v17 - 1) - *v19;
          v26 = v22 + *v17;
          v27 = (float)(v21 * v26) - (float)(*(float *)((char *)v17 + v18) * v25);
          v28 = *(float *)((char *)v17 + v18) * v26;
          *(v17 - 1) = *(v17 - 1) + v27;
          v29 = (float)(v21 * v25) + v28;
          *v17 = v24 - v29;
          *v19 = v23 - v27;
          v19[1] = v22 - v29;
          v19 -= 2;
          v17 += 2;
          --v20;
        }
        while ( v20 );
      }
    }
    else
    {
      if ( a2 > 2 )
      {
        v5 = (float *)(a4 + 12);
        v6 = a1 - a4;
        v7 = (float *)(a1 + 4LL * v4);
        v8 = ((unsigned int)(a2 - 3) >> 1) + 1;
        do
        {
          v9 = *(v5 - 1);
          v10 = *(float *)((char *)v5 + v6);
          v11 = *(float *)((char *)v5 + v6 - 4) - *v7;
          v12 = v7[1] + v10;
          v13 = (float)(*v5 * v12) - (float)(v9 * v11);
          v14 = (float)(v9 * v12) + (float)(*v5 * v11);
          v15 = *(float *)((char *)v5 + v6 - 4) - v14;
          v16 = v13 - v7[1];
          *(float *)((char *)v5 + v6 - 4) = *v7 + v14;
          *v7 = v15;
          *(float *)((char *)v5 + v6) = v16;
          v5 += 2;
          v7[1] = v13 - v10;
          v7 -= 2;
          --v8;
        }
        while ( v8 );
      }
      *(_DWORD *)(a1 + 4LL * a2 + 4) ^= _xmm;
    }
  }
}

```

## disassembly

```asm
0x1800160e0  cmp     edx, 1
0x1800160e3  jz      locret_18001629F
0x1800160e9  sub     rsp, 48h
0x1800160ed  movaps  [rsp+48h+var_18], xmm6
0x1800160f2  movaps  [rsp+48h+var_28], xmm7
0x1800160f7  movaps  [rsp+48h+var_38], xmm8
0x1800160fd  lea     eax, ds:0FFFFFFFFFFFFFFFEh[rdx*2]
0x180016104  movaps  [rsp+48h+var_48], xmm9
0x180016109  test    r8d, r8d
0x18001610c  jle     loc_1800161DF
0x180016112  cmp     edx, 2
0x180016115  jle     loc_1800161C4
0x18001611b  lea     r10, [r9+0Ch]
0x18001611f  mov     r8, rcx
0x180016122  cdqe
0x180016124  sub     r8, r9
0x180016127  lea     r9d, [rdx-3]
0x18001612b  lea     r11, [rcx+rax*4]
0x18001612f  shr     r9d, 1
0x180016132  inc     r9d
0x180016135  movss   xmm5, dword ptr [r10]
0x18001613a  movss   xmm2, dword ptr [r10-4]
0x180016140  movss   xmm9, dword ptr [r8+r10-4]
0x180016147  movaps  xmm0, xmm5
0x18001614a  movaps  xmm4, xmm9
0x18001614e  movaps  xmm3, xmm2
0x180016151  movss   xmm6, dword ptr [r11+4]
0x180016157  movss   xmm7, dword ptr [r11]
0x18001615c  movss   xmm8, dword ptr [r8+r10]
0x180016162  movaps  xmm1, xmm6
0x180016165  subss   xmm4, xmm7
0x180016169  addss   xmm1, xmm8
0x18001616e  mulss   xmm5, xmm1
0x180016172  mulss   xmm0, xmm4
0x180016176  mulss   xmm2, xmm4
0x18001617a  subss   xmm5, xmm2
0x18001617e  mulss   xmm3, xmm1
0x180016182  addss   xmm3, xmm0
0x180016186  movaps  xmm0, xmm5
0x180016189  subss   xmm5, xmm8
0x18001618e  addss   xmm7, xmm3
0x180016192  subss   xmm9, xmm3
0x180016197  subss   xmm0, xmm6
0x18001619b  movss   dword ptr [r8+r10-4], xmm7
0x1800161a2  movss   dword ptr [r11], xmm9
0x1800161a7  movss   dword ptr [r8+r10], xmm0
0x1800161ad  add     r10, 8
0x1800161b1  movss   dword ptr [r11+4], xmm5
0x1800161b7  sub     r11, 8
0x1800161bb  dec     r9
0x1800161be  jnz     loc_180016135
0x1800161c4  movsxd  rax, edx
0x1800161c7  movss   xmm0, dword ptr [rcx+rax*4+4]
0x1800161cd  xorps   xmm0, cs:__xmm@80000000800000008000000080000000
0x1800161d4  movss   dword ptr [rcx+rax*4+4], xmm0
0x1800161da  jmp     loc_180016286
0x1800161df  cmp     edx, 2
0x1800161e2  jle     loc_180016286
0x1800161e8  lea     r8, [rcx+0Ch]
0x1800161ec  sub     r9, rcx
0x1800161ef  cdqe
0x1800161f1  lea     r10, [rcx+rax*4]
0x1800161f5  lea     ecx, [rdx-3]
0x1800161f8  shr     ecx, 1
0x1800161fa  inc     ecx
0x1800161fc  movss   xmm6, dword ptr [r9+r8-4]
0x180016203  movss   xmm1, dword ptr [r9+r8]
0x180016209  movss   xmm7, dword ptr [r8-4]
0x18001620f  movaps  xmm4, xmm6
0x180016212  movaps  xmm3, xmm7
0x180016215  movaps  xmm0, xmm1
0x180016218  movss   xmm8, dword ptr [r10+4]
0x18001621e  movss   xmm9, dword ptr [r10]
0x180016223  movss   xmm5, dword ptr [r8]
0x180016228  movaps  xmm2, xmm8
0x18001622c  subss   xmm3, xmm9
0x180016231  addss   xmm2, xmm5
0x180016235  mulss   xmm4, xmm2
0x180016239  mulss   xmm0, xmm3
0x18001623d  mulss   xmm6, xmm3
0x180016241  subss   xmm4, xmm0
0x180016245  addss   xmm7, xmm4
0x180016249  subss   xmm9, xmm4
0x18001624e  mulss   xmm1, xmm2
0x180016252  movss   dword ptr [r8-4], xmm7
0x180016258  addss   xmm6, xmm1
0x18001625c  subss   xmm5, xmm6
0x180016260  subss   xmm8, xmm6
0x180016265  movss   dword ptr [r8], xmm5
0x18001626a  movss   dword ptr [r10], xmm9
0x18001626f  movss   dword ptr [r10+4], xmm8
0x180016275  sub     r10, 8
0x180016279  add     r8, 8
0x18001627d  dec     rcx
0x180016280  jnz     loc_1800161FC
0x180016286  movaps  xmm6, [rsp+48h+var_18]
0x18001628b  movaps  xmm7, [rsp+48h+var_28]
0x180016290  movaps  xmm8, [rsp+48h+var_38]
0x180016296  movaps  xmm9, [rsp+48h+var_48]
0x18001629b  add     rsp, 48h
0x18001629f  retn
```
