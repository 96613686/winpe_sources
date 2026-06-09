# px_ipps_rDftFwdRecombine_32f

- ea: `0x1800533bc`
- end: `0x1800534e9`
- name: `px_ipps_rDftFwdRecombine_32f`
- size: `301`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180047c40`

## callees

- `0x1800533bc`

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
0x1800533bc  sub     rsp, 48h
0x1800533c0  movss   xmm1, dword ptr [rcx+4]
0x1800533c5  movss   xmm0, dword ptr [rcx]
0x1800533c9  movaps  [rsp+48h+var_18], xmm6
0x1800533ce  movaps  [rsp+48h+var_28], xmm7
0x1800533d3  movaps  [rsp+48h+var_38], xmm8
0x1800533d9  mov     r9, r8
0x1800533dc  subss   xmm0, xmm1
0x1800533e0  addss   xmm1, dword ptr [rcx]
0x1800533e4  movaps  [rsp+48h+var_48], xmm9
0x1800533e9  movss   dword ptr [rcx], xmm1
0x1800533ed  movss   dword ptr [rcx+4], xmm0
0x1800533f2  cmp     edx, 1
0x1800533f5  jz      loc_1800534CF
0x1800533fb  lea     eax, ds:0FFFFFFFFFFFFFFFEh[rdx*2]
0x180053402  cmp     edx, 2
0x180053405  jle     loc_1800534B4
0x18005340b  lea     r10, [r8+0Ch]
0x18005340f  mov     r8, rcx
0x180053412  cdqe
0x180053414  sub     r8, r9
0x180053417  lea     r9d, [rdx-3]
0x18005341b  lea     r11, [rcx+rax*4]
0x18005341f  shr     r9d, 1
0x180053422  inc     r9d
0x180053425  movss   xmm5, dword ptr [r10]
0x18005342a  movss   xmm9, dword ptr [r8+r10-4]
0x180053431  movss   xmm6, dword ptr [r11+4]
0x180053437  movaps  xmm0, xmm5
0x18005343a  movaps  xmm4, xmm9
0x18005343e  movaps  xmm1, xmm6
0x180053441  movss   xmm7, dword ptr [r11]
0x180053446  movss   xmm8, dword ptr [r8+r10]
0x18005344c  movss   xmm2, dword ptr [r10-4]
0x180053452  movaps  xmm3, xmm2
0x180053455  subss   xmm4, xmm7
0x180053459  addss   xmm1, xmm8
0x18005345e  mulss   xmm5, xmm1
0x180053462  mulss   xmm0, xmm4
0x180053466  mulss   xmm2, xmm4
0x18005346a  subss   xmm5, xmm2
0x18005346e  mulss   xmm3, xmm1
0x180053472  addss   xmm3, xmm0
0x180053476  movaps  xmm0, xmm5
0x180053479  subss   xmm5, xmm8
0x18005347e  addss   xmm7, xmm3
0x180053482  subss   xmm9, xmm3
0x180053487  subss   xmm0, xmm6
0x18005348b  movss   dword ptr [r8+r10-4], xmm7
0x180053492  movss   dword ptr [r11], xmm9
0x180053497  movss   dword ptr [r8+r10], xmm0
0x18005349d  add     r10, 8
0x1800534a1  movss   dword ptr [r11+4], xmm5
0x1800534a7  sub     r11, 8
0x1800534ab  dec     r9
0x1800534ae  jnz     loc_180053425
0x1800534b4  test    dl, 1
0x1800534b7  jnz     short loc_1800534CF
0x1800534b9  movsxd  rax, edx
0x1800534bc  movss   xmm0, dword ptr [rcx+rax*4+4]
0x1800534c2  xorps   xmm0, cs:__xmm@80000000800000008000000080000000
0x1800534c9  movss   dword ptr [rcx+rax*4+4], xmm0
0x1800534cf  movaps  xmm6, [rsp+48h+var_18]
0x1800534d4  movaps  xmm7, [rsp+48h+var_28]
0x1800534d9  movaps  xmm8, [rsp+48h+var_38]
0x1800534df  movaps  xmm9, [rsp+48h+var_48]
0x1800534e4  add     rsp, 48h
0x1800534e8  retn
```
