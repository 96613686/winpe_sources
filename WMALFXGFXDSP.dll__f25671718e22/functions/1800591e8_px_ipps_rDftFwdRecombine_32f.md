# px_ipps_rDftFwdRecombine_32f

- ea: `0x1800591e8`
- end: `0x180059315`
- name: `px_ipps_rDftFwdRecombine_32f`
- size: `301`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001c700`

## callees

- `0x1800591e8`

## pseudocode

```c
void __fastcall px_ipps_rDftFwdRecombine_32f(float *a1, int a2, __int64 a3)
{
  float v3; // xmm1_4
  float v4; // xmm0_4
  float *v5; // r10
  char *v6; // r8
  float *v7; // r11
  __int64 v8; // r9
  float v9; // xmm8_4
  float v10; // xmm3_4
  float v11; // xmm4_4
  float v12; // xmm1_4
  float v13; // xmm5_4
  float v14; // xmm3_4
  float v15; // xmm9_4
  float v16; // xmm0_4

  v3 = a1[1];
  v4 = *a1 - v3;
  *a1 = v3 + *a1;
  a1[1] = v4;
  if ( a2 != 1 )
  {
    if ( a2 > 2 )
    {
      v5 = (float *)(a3 + 12);
      v6 = (char *)a1 - a3;
      v7 = &a1[2 * a2 - 2];
      v8 = ((unsigned int)(a2 - 3) >> 1) + 1;
      do
      {
        v9 = *(float *)((char *)v5 + (_QWORD)v6);
        v10 = *(v5 - 1);
        v11 = *(float *)((char *)v5 + (_QWORD)v6 - 4) - *v7;
        v12 = v7[1] + v9;
        v13 = (float)(*v5 * v12) - (float)(v10 * v11);
        v14 = (float)(v10 * v12) + (float)(*v5 * v11);
        v15 = *(float *)((char *)v5 + (_QWORD)v6 - 4) - v14;
        v16 = v13 - v7[1];
        *(float *)((char *)v5 + (_QWORD)v6 - 4) = *v7 + v14;
        *v7 = v15;
        *(float *)((char *)v5 + (_QWORD)v6) = v16;
        v5 += 2;
        v7[1] = v13 - v9;
        v7 -= 2;
        --v8;
      }
      while ( v8 );
    }
    if ( (a2 & 1) == 0 )
      LODWORD(a1[a2 + 1]) ^= _xmm;
  }
}

```

## disassembly

```asm
0x1800591e8  sub     rsp, 48h
0x1800591ec  movss   xmm1, dword ptr [rcx+4]
0x1800591f1  movss   xmm0, dword ptr [rcx]
0x1800591f5  movaps  [rsp+48h+var_18], xmm6
0x1800591fa  movaps  [rsp+48h+var_28], xmm7
0x1800591ff  movaps  [rsp+48h+var_38], xmm8
0x180059205  mov     r9, r8
0x180059208  subss   xmm0, xmm1
0x18005920c  addss   xmm1, dword ptr [rcx]
0x180059210  movaps  [rsp+48h+var_48], xmm9
0x180059215  movss   dword ptr [rcx], xmm1
0x180059219  movss   dword ptr [rcx+4], xmm0
0x18005921e  cmp     edx, 1
0x180059221  jz      loc_1800592FB
0x180059227  lea     eax, ds:0FFFFFFFFFFFFFFFEh[rdx*2]
0x18005922e  cmp     edx, 2
0x180059231  jle     loc_1800592E0
0x180059237  lea     r10, [r8+0Ch]
0x18005923b  mov     r8, rcx
0x18005923e  cdqe
0x180059240  sub     r8, r9
0x180059243  lea     r9d, [rdx-3]
0x180059247  lea     r11, [rcx+rax*4]
0x18005924b  shr     r9d, 1
0x18005924e  inc     r9d
0x180059251  movss   xmm5, dword ptr [r10]
0x180059256  movss   xmm9, dword ptr [r8+r10-4]
0x18005925d  movss   xmm6, dword ptr [r11+4]
0x180059263  movaps  xmm0, xmm5
0x180059266  movaps  xmm4, xmm9
0x18005926a  movaps  xmm1, xmm6
0x18005926d  movss   xmm7, dword ptr [r11]
0x180059272  movss   xmm8, dword ptr [r8+r10]
0x180059278  movss   xmm2, dword ptr [r10-4]
0x18005927e  movaps  xmm3, xmm2
0x180059281  subss   xmm4, xmm7
0x180059285  addss   xmm1, xmm8
0x18005928a  mulss   xmm5, xmm1
0x18005928e  mulss   xmm0, xmm4
0x180059292  mulss   xmm2, xmm4
0x180059296  subss   xmm5, xmm2
0x18005929a  mulss   xmm3, xmm1
0x18005929e  addss   xmm3, xmm0
0x1800592a2  movaps  xmm0, xmm5
0x1800592a5  subss   xmm5, xmm8
0x1800592aa  addss   xmm7, xmm3
0x1800592ae  subss   xmm9, xmm3
0x1800592b3  subss   xmm0, xmm6
0x1800592b7  movss   dword ptr [r8+r10-4], xmm7
0x1800592be  movss   dword ptr [r11], xmm9
0x1800592c3  movss   dword ptr [r8+r10], xmm0
0x1800592c9  add     r10, 8
0x1800592cd  movss   dword ptr [r11+4], xmm5
0x1800592d3  sub     r11, 8
0x1800592d7  dec     r9
0x1800592da  jnz     loc_180059251
0x1800592e0  test    dl, 1
0x1800592e3  jnz     short loc_1800592FB
0x1800592e5  movsxd  rax, edx
0x1800592e8  movss   xmm0, dword ptr [rcx+rax*4+4]
0x1800592ee  xorps   xmm0, cs:__xmm@80000000800000008000000080000000
0x1800592f5  movss   dword ptr [rcx+rax*4+4], xmm0
0x1800592fb  movaps  xmm6, [rsp+48h+var_18]
0x180059300  movaps  xmm7, [rsp+48h+var_28]
0x180059305  movaps  xmm8, [rsp+48h+var_38]
0x18005930b  movaps  xmm9, [rsp+48h+var_48]
0x180059310  add     rsp, 48h
0x180059314  retn
```
