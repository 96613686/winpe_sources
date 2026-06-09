# px_ipps_cRealRecombine_32f

- ea: `0x1800249b0`
- end: `0x180024b70`
- name: `px_ipps_cRealRecombine_32f`
- size: `448`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180018af0`
- `0x180018ccc`

## callees

- `0x1800249b0`

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
0x1800249b0  cmp     edx, 1
0x1800249b3  jz      locret_180024B6F
0x1800249b9  sub     rsp, 48h
0x1800249bd  movaps  [rsp+48h+var_18], xmm6
0x1800249c2  movaps  [rsp+48h+var_28], xmm7
0x1800249c7  movaps  [rsp+48h+var_38], xmm8
0x1800249cd  lea     eax, ds:0FFFFFFFFFFFFFFFEh[rdx*2]
0x1800249d4  movaps  [rsp+48h+var_48], xmm9
0x1800249d9  test    r8d, r8d
0x1800249dc  jle     loc_180024AAF
0x1800249e2  cmp     edx, 2
0x1800249e5  jle     loc_180024A94
0x1800249eb  lea     r10, [r9+0Ch]
0x1800249ef  mov     r8, rcx
0x1800249f2  cdqe
0x1800249f4  sub     r8, r9
0x1800249f7  lea     r9d, [rdx-3]
0x1800249fb  lea     r11, [rcx+rax*4]
0x1800249ff  shr     r9d, 1
0x180024a02  inc     r9d
0x180024a05  movss   xmm5, dword ptr [r10]
0x180024a0a  movss   xmm2, dword ptr [r10-4]
0x180024a10  movss   xmm9, dword ptr [r8+r10-4]
0x180024a17  movaps  xmm0, xmm5
0x180024a1a  movaps  xmm4, xmm9
0x180024a1e  movaps  xmm3, xmm2
0x180024a21  movss   xmm6, dword ptr [r11+4]
0x180024a27  movss   xmm7, dword ptr [r11]
0x180024a2c  movss   xmm8, dword ptr [r8+r10]
0x180024a32  movaps  xmm1, xmm6
0x180024a35  subss   xmm4, xmm7
0x180024a39  addss   xmm1, xmm8
0x180024a3e  mulss   xmm5, xmm1
0x180024a42  mulss   xmm0, xmm4
0x180024a46  mulss   xmm2, xmm4
0x180024a4a  subss   xmm5, xmm2
0x180024a4e  mulss   xmm3, xmm1
0x180024a52  addss   xmm3, xmm0
0x180024a56  movaps  xmm0, xmm5
0x180024a59  subss   xmm5, xmm8
0x180024a5e  addss   xmm7, xmm3
0x180024a62  subss   xmm9, xmm3
0x180024a67  subss   xmm0, xmm6
0x180024a6b  movss   dword ptr [r8+r10-4], xmm7
0x180024a72  movss   dword ptr [r11], xmm9
0x180024a77  movss   dword ptr [r8+r10], xmm0
0x180024a7d  add     r10, 8
0x180024a81  movss   dword ptr [r11+4], xmm5
0x180024a87  sub     r11, 8
0x180024a8b  dec     r9
0x180024a8e  jnz     loc_180024A05
0x180024a94  movsxd  rax, edx
0x180024a97  movss   xmm0, dword ptr [rcx+rax*4+4]
0x180024a9d  xorps   xmm0, cs:__xmm@80000000800000008000000080000000
0x180024aa4  movss   dword ptr [rcx+rax*4+4], xmm0
0x180024aaa  jmp     loc_180024B56
0x180024aaf  cmp     edx, 2
0x180024ab2  jle     loc_180024B56
0x180024ab8  lea     r8, [rcx+0Ch]
0x180024abc  sub     r9, rcx
0x180024abf  cdqe
0x180024ac1  lea     r10, [rcx+rax*4]
0x180024ac5  lea     ecx, [rdx-3]
0x180024ac8  shr     ecx, 1
0x180024aca  inc     ecx
0x180024acc  movss   xmm6, dword ptr [r9+r8-4]
0x180024ad3  movss   xmm1, dword ptr [r9+r8]
0x180024ad9  movss   xmm7, dword ptr [r8-4]
0x180024adf  movaps  xmm4, xmm6
0x180024ae2  movaps  xmm3, xmm7
0x180024ae5  movaps  xmm0, xmm1
0x180024ae8  movss   xmm8, dword ptr [r10+4]
0x180024aee  movss   xmm9, dword ptr [r10]
0x180024af3  movss   xmm5, dword ptr [r8]
0x180024af8  movaps  xmm2, xmm8
0x180024afc  subss   xmm3, xmm9
0x180024b01  addss   xmm2, xmm5
0x180024b05  mulss   xmm4, xmm2
0x180024b09  mulss   xmm0, xmm3
0x180024b0d  mulss   xmm6, xmm3
0x180024b11  subss   xmm4, xmm0
0x180024b15  addss   xmm7, xmm4
0x180024b19  subss   xmm9, xmm4
0x180024b1e  mulss   xmm1, xmm2
0x180024b22  movss   dword ptr [r8-4], xmm7
0x180024b28  addss   xmm6, xmm1
0x180024b2c  subss   xmm5, xmm6
0x180024b30  subss   xmm8, xmm6
0x180024b35  movss   dword ptr [r8], xmm5
0x180024b3a  movss   dword ptr [r10], xmm9
0x180024b3f  movss   dword ptr [r10+4], xmm8
0x180024b45  sub     r10, 8
0x180024b49  add     r8, 8
0x180024b4d  dec     rcx
0x180024b50  jnz     loc_180024ACC
0x180024b56  movaps  xmm6, [rsp+48h+var_18]
0x180024b5b  movaps  xmm7, [rsp+48h+var_28]
0x180024b60  movaps  xmm8, [rsp+48h+var_38]
0x180024b66  movaps  xmm9, [rsp+48h+var_48]
0x180024b6b  add     rsp, 48h
0x180024b6f  retn
```
