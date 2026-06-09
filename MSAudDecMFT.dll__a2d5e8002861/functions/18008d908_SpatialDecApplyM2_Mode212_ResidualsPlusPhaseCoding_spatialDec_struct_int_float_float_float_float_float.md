# SpatialDecApplyM2_Mode212_ResidualsPlusPhaseCoding(spatialDec_struct *,int,float,float * *,float * *,float * *,float * *)

- ea: `0x18008d908`
- end: `0x18008dcc2`
- name: `?SpatialDecApplyM2_Mode212_ResidualsPlusPhaseCoding@@YA?AW4SACDEC_ERROR@@PEAUspatialDec_struct@@HMPEAPEAM111@Z`
- size: `954`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18007ed44`

## callees

- `0x18008d908`

## pseudocode

```c
__int64 __fastcall SpatialDecApplyM2_Mode212_ResidualsPlusPhaseCoding(
        __int64 a1,
        __int64 a2,
        float a3,
        float **a4,
        float **a5,
        __int64 a6,
        __int64 a7)
{
  __int64 v9; // rdx
  __int64 v10; // rax
  float *v11; // rcx
  float *v12; // r8
  __int64 v13; // r13
  int v14; // r11d
  float *v15; // rdx
  float *v16; // rax
  float *v17; // r14
  float *v18; // rsi
  float *v19; // rdi
  float *v20; // rbp
  __int64 v21; // r8
  __int64 *v22; // rdx
  float *v23; // r12
  __int64 *v24; // rcx
  __int64 v25; // r11
  __int64 v26; // rbx
  __int64 v27; // r13
  __int64 *v28; // rdx
  __int64 v29; // r9
  int v30; // ecx
  int v31; // edx
  float *v32; // r15
  __int64 v33; // r8
  float v34; // xmm7_4
  int v35; // r9d
  __m128 v36; // xmm6
  float v37; // xmm7_4
  __m128 v38; // xmm6
  float v39; // xmm8_4
  float v40; // xmm4_4
  float v41; // xmm5_4
  float v42; // xmm2_4
  float v43; // xmm0_4
  float v44; // xmm3_4
  int v45; // eax
  int v46; // r11d
  int v47; // edx
  float v48; // xmm6_4
  float v49; // xmm7_4
  float v50; // xmm8_4
  float v51; // xmm4_4
  float v52; // xmm5_4
  float v53; // xmm2_4
  float v54; // xmm0_4
  float v55; // xmm3_4
  __int64 v57; // [rsp+0h] [rbp-C8h]
  __int64 v58; // [rsp+8h] [rbp-C0h]
  __int64 v59; // [rsp+10h] [rbp-B8h]
  __int64 v60; // [rsp+18h] [rbp-B0h]
  __int64 v61; // [rsp+20h] [rbp-A8h]
  __int64 v62; // [rsp+28h] [rbp-A0h]
  float *v63; // [rsp+30h] [rbp-98h]
  float *v64; // [rsp+38h] [rbp-90h]
  float *v65; // [rsp+40h] [rbp-88h]
  float *v66; // [rsp+48h] [rbp-80h]
  int v67; // [rsp+D0h] [rbp+8h]
  int v68; // [rsp+D8h] [rbp+10h]

  if ( *(int *)(a1 + 96) > 0 )
  {
    v9 = *(int *)(a1 + 196);
    v10 = *(_QWORD *)(a1 + 200);
    v11 = *a4;
    v12 = a4[1];
    v13 = a7;
    v14 = 0;
    v67 = *(char *)(v9 + v10 - 1) + 1;
    v68 = 0;
    v63 = *a4;
    v15 = *a5;
    v16 = a5[1];
    v66 = v16;
    v64 = *a5;
    v65 = v12;
    do
    {
      v17 = v16;
      v18 = v15;
      v19 = v11;
      v20 = v12;
      v21 = v14;
      v22 = *(__int64 **)(*(_QWORD *)(a1 + 1016) + 8LL * v14);
      v23 = *(float **)(v13 + 8LL * v14);
      v24 = *(__int64 **)(*(_QWORD *)(a1 + 1024) + 8LL * v14);
      v25 = v22[1];
      v57 = *v22;
      v26 = *v24;
      v27 = *v22;
      v28 = *(__int64 **)(*(_QWORD *)(a1 + 1032) + 8 * v21);
      v61 = *v24;
      v62 = v25;
      v29 = *v28;
      v58 = *v28;
      v30 = 0;
      v59 = **(_QWORD **)(*(_QWORD *)(a1 + 1040) + 8 * v21);
      v60 = v28[1];
      v31 = 3;
      v32 = *(float **)(a6 + 8 * v21);
      v33 = 0;
      do
      {
        v34 = *(float *)(v29 + 4 * v33);
        v35 = *(_DWORD *)(a1 + 4 * v33 + 224);
        v36 = (__m128)*(unsigned int *)(v59 + 4 * v33);
        v37 = (float)(v34 - (float)(v34 * a3)) + (float)(a3 * *(float *)(v27 + 4 * v33));
        v36.m128_f32[0] = (float)(v36.m128_f32[0] - (float)(*(float *)(v59 + 4 * v33) * a3))
                        + (float)(a3 * *(float *)(v26 + 4 * v33));
        v38 = _mm_xor_ps(v36, (__m128)_xmm);
        v39 = (float)(*(float *)(v60 + 4 * v33) - (float)(*(float *)(v60 + 4 * v33) * a3))
            + (float)(a3 * *(float *)(v25 + 4 * v33));
        do
        {
          v40 = *v19++;
          v41 = *v18;
          v42 = *v20;
          v43 = *v18;
          v44 = *v17;
          ++v18;
          ++v20;
          ++v17;
          *v32++ = (float)((float)(v40 * v37) - (float)(v43 * v38.m128_f32[0])) + (float)(v42 * v39);
          *v23++ = (float)((float)(v41 * v37) + (float)(v40 * v38.m128_f32[0])) + (float)(v44 * v39);
          if ( v31 > 0 )
            v38 = _mm_xor_ps(v38, (__m128)_xmm);
          v45 = v31 - 1;
          if ( v31 <= 0 )
            v45 = v31;
          v31 = v45;
          --v35;
        }
        while ( v35 );
        v29 = v58;
        ++v30;
        ++v33;
      }
      while ( v30 < 2 );
      v46 = v68;
      v13 = a7;
      if ( v30 < v67 )
      {
        do
        {
          v47 = *(_DWORD *)(a1 + 4LL * v30 + 224);
          v48 = (float)(*(float *)(v58 + 4LL * v30) - (float)(*(float *)(v58 + 4LL * v30) * a3))
              + (float)(a3 * *(float *)(v57 + 4LL * v30));
          v49 = (float)(*(float *)(v59 + 4LL * v30) - (float)(*(float *)(v59 + 4LL * v30) * a3))
              + (float)(a3 * *(float *)(v61 + 4LL * v30));
          v50 = (float)(*(float *)(v60 + 4LL * v30) - (float)(*(float *)(v60 + 4LL * v30) * a3))
              + (float)(a3 * *(float *)(v62 + 4LL * v30));
          do
          {
            v51 = *v19++;
            v52 = *v18;
            v53 = *v20;
            v54 = *v18;
            v55 = *v17;
            ++v18;
            ++v20;
            ++v17;
            *v32++ = (float)((float)(v51 * v48) - (float)(v54 * v49)) + (float)(v53 * v50);
            *v23++ = (float)((float)(v52 * v48) + (float)(v51 * v49)) + (float)(v55 * v50);
            --v47;
          }
          while ( v47 );
          ++v30;
        }
        while ( v30 < v67 );
        v46 = v68;
        v13 = a7;
      }
      v11 = v63;
      v14 = v46 + 1;
      v15 = v64;
      v12 = v65;
      v16 = v66;
      v68 = v14;
    }
    while ( v14 < *(_DWORD *)(a1 + 96) );
  }
  return 0;
}

```

## disassembly

```asm
0x18008d908  mov     rax, rsp
0x18008d90b  mov     [rax+18h], rbx
0x18008d90f  mov     [rax+10h], edx
0x18008d912  push    rbp
0x18008d913  push    rsi
0x18008d914  push    rdi
0x18008d915  push    r12
0x18008d917  push    r13
0x18008d919  push    r14
0x18008d91b  push    r15
0x18008d91d  sub     rsp, 90h
0x18008d924  cmp     dword ptr [rcx+60h], 0
0x18008d928  mov     r10, rcx
0x18008d92b  movaps  xmmword ptr [rax-48h], xmm6
0x18008d92f  movaps  xmmword ptr [rax-58h], xmm7
0x18008d933  movaps  xmmword ptr [rax-68h], xmm8
0x18008d938  movaps  xmmword ptr [rax-78h], xmm9
0x18008d93d  movaps  xmm9, xmm2
0x18008d941  jle     loc_18008DC90
0x18008d947  movsxd  rdx, dword ptr [rcx+0C4h]
0x18008d94e  mov     rax, [rcx+0C8h]
0x18008d955  mov     rcx, [r9]
0x18008d958  mov     r8, [r9+8]
0x18008d95c  mov     r13, [rsp+0C8h+arg_30]
0x18008d964  movsx   ebx, byte ptr [rdx+rax-1]
0x18008d969  mov     rax, [rsp+0C8h+arg_20]
0x18008d971  inc     ebx
0x18008d973  xor     r11d, r11d
0x18008d976  mov     [rsp+0C8h+arg_0], ebx
0x18008d97d  mov     [rsp+0C8h+arg_8], r11d
0x18008d985  mov     [rsp+0C8h+var_98], rcx
0x18008d98a  mov     rdx, [rax]
0x18008d98d  mov     rax, [rax+8]
0x18008d991  mov     [rsp+0C8h+var_80], rax
0x18008d996  mov     [rsp+0C8h+var_90], rdx
0x18008d99b  mov     [rsp+0C8h+var_88], r8
0x18008d9a0  mov     r14, rax
0x18008d9a3  mov     rsi, rdx
0x18008d9a6  mov     rax, [r10+3F8h]
0x18008d9ad  mov     rdi, rcx
0x18008d9b0  mov     rbp, r8
0x18008d9b3  movsxd  r8, r11d
0x18008d9b6  mov     rdx, [rax+r8*8]
0x18008d9ba  mov     rax, [r10+400h]
0x18008d9c1  mov     r12, [r13+r8*8+0]
0x18008d9c6  mov     r9, [rdx]
0x18008d9c9  mov     rcx, [rax+r8*8]
0x18008d9cd  mov     r11, [rdx+8]
0x18008d9d1  mov     rax, [r10+408h]
0x18008d9d8  mov     [rsp+0C8h+var_C8], r9
0x18008d9dc  mov     rbx, [rcx]
0x18008d9df  mov     r13, [rsp+0C8h+var_C8]
0x18008d9e3  mov     rdx, [rax+r8*8]
0x18008d9e7  mov     rax, [r10+410h]
0x18008d9ee  mov     [rsp+0C8h+var_A8], rbx
0x18008d9f3  mov     [rsp+0C8h+var_A0], r11
0x18008d9f8  mov     r9, [rdx]
0x18008d9fb  mov     rcx, [rax+r8*8]
0x18008d9ff  mov     [rsp+0C8h+var_C0], r9
0x18008da04  mov     rax, [rcx]
0x18008da07  xor     ecx, ecx
0x18008da09  mov     [rsp+0C8h+var_B8], rax
0x18008da0e  mov     rax, [rdx+8]
0x18008da12  mov     [rsp+0C8h+var_B0], rax
0x18008da17  mov     rax, [rsp+0C8h+arg_28]
0x18008da1f  lea     edx, [rcx+3]
0x18008da22  mov     r15, [rax+r8*8]
0x18008da26  xor     r8d, r8d
0x18008da29  movss   xmm7, dword ptr [r9+r8*4]
0x18008da2f  movaps  xmm1, xmm9
0x18008da33  mulss   xmm1, dword ptr [r13+r8*4+0]
0x18008da3a  movaps  xmm0, xmm7
0x18008da3d  mov     rax, [rsp+0C8h+var_B8]
0x18008da42  mov     r9d, [r10+r8*4+0E0h]
0x18008da4a  mulss   xmm0, xmm9
0x18008da4f  movss   xmm6, dword ptr [rax+r8*4]
0x18008da55  mov     rax, [rsp+0C8h+var_B0]
0x18008da5a  subss   xmm7, xmm0
0x18008da5e  movaps  xmm0, xmm6
0x18008da61  mulss   xmm0, xmm9
0x18008da66  movss   xmm8, dword ptr [rax+r8*4]
0x18008da6c  addss   xmm7, xmm1
0x18008da70  movaps  xmm1, xmm9
0x18008da74  mulss   xmm1, dword ptr [rbx+r8*4]
0x18008da7a  subss   xmm6, xmm0
0x18008da7e  movaps  xmm0, xmm8
0x18008da82  mulss   xmm0, xmm9
0x18008da87  addss   xmm6, xmm1
0x18008da8b  movaps  xmm1, xmm9
0x18008da8f  mulss   xmm1, dword ptr [r11+r8*4]
0x18008da95  subss   xmm8, xmm0
0x18008da9a  xorps   xmm6, cs:__xmm@80000000800000008000000080000000
0x18008daa1  addss   xmm8, xmm1
0x18008daa6  movss   xmm4, dword ptr [rdi]
0x18008daaa  add     rdi, 4
0x18008daae  movss   xmm5, dword ptr [rsi]
0x18008dab2  movaps  xmm1, xmm4
0x18008dab5  movss   xmm2, dword ptr [rbp+0]
0x18008daba  movaps  xmm0, xmm5
0x18008dabd  movss   xmm3, dword ptr [r14]
0x18008dac2  add     rsi, 4
0x18008dac6  mulss   xmm1, xmm7
0x18008daca  add     rbp, 4
0x18008dace  add     r14, 4
0x18008dad2  mulss   xmm5, xmm7
0x18008dad6  mulss   xmm0, xmm6
0x18008dada  mulss   xmm4, xmm6
0x18008dade  subss   xmm1, xmm0
0x18008dae2  mulss   xmm2, xmm8
0x18008dae7  addss   xmm5, xmm4
0x18008daeb  mulss   xmm3, xmm8
0x18008daf0  addss   xmm1, xmm2
0x18008daf4  addss   xmm5, xmm3
0x18008daf8  movss   dword ptr [r15], xmm1
0x18008dafd  add     r15, 4
0x18008db01  movss   dword ptr [r12], xmm5
0x18008db07  add     r12, 4
0x18008db0b  test    edx, edx
0x18008db0d  jle     short loc_18008DB16
0x18008db0f  xorps   xmm6, cs:__xmm@80000000800000008000000080000000
0x18008db16  test    edx, edx
0x18008db18  lea     eax, [rdx-1]
0x18008db1b  cmovle  eax, edx
0x18008db1e  mov     edx, eax
0x18008db20  sub     r9d, 1
0x18008db24  jnz     short loc_18008DAA6
0x18008db26  mov     r9, [rsp+0C8h+var_C0]
0x18008db2b  inc     ecx
0x18008db2d  inc     r8
0x18008db30  cmp     ecx, 2
0x18008db33  jl      loc_18008DA29
0x18008db39  mov     ebx, [rsp+0C8h+arg_0]
0x18008db40  mov     r11d, [rsp+0C8h+arg_8]
0x18008db48  mov     r13, [rsp+0C8h+arg_30]
0x18008db50  cmp     ecx, ebx
0x18008db52  jge     loc_18008DC67
0x18008db58  mov     r9, [rsp+0C8h+var_C8]
0x18008db5c  mov     r8, [rsp+0C8h+var_A8]
0x18008db61  mov     r13, [rsp+0C8h+var_A0]
0x18008db66  mov     r11, [rsp+0C8h+var_C0]
0x18008db6b  mov     rdx, [rsp+0C8h+var_B8]
0x18008db70  movaps  xmm1, xmm9
0x18008db74  movsxd  rax, ecx
0x18008db77  mulss   xmm1, dword ptr [r9+rax*4]
0x18008db7d  movss   xmm7, dword ptr [rdx+rax*4]
0x18008db82  movss   xmm6, dword ptr [r11+rax*4]
0x18008db88  mov     rdx, [rsp+0C8h+var_B0]
0x18008db8d  movaps  xmm0, xmm6
0x18008db90  mulss   xmm0, xmm9
0x18008db95  movss   xmm8, dword ptr [rdx+rax*4]
0x18008db9b  mov     edx, [r10+rax*4+0E0h]
0x18008dba3  subss   xmm6, xmm0
0x18008dba7  movaps  xmm0, xmm7
0x18008dbaa  mulss   xmm0, xmm9
0x18008dbaf  addss   xmm6, xmm1
0x18008dbb3  movaps  xmm1, xmm9
0x18008dbb7  mulss   xmm1, dword ptr [r8+rax*4]
0x18008dbbd  subss   xmm7, xmm0
0x18008dbc1  movaps  xmm0, xmm8
0x18008dbc5  mulss   xmm0, xmm9
0x18008dbca  addss   xmm7, xmm1
0x18008dbce  movaps  xmm1, xmm9
0x18008dbd2  mulss   xmm1, dword ptr [r13+rax*4+0]
0x18008dbd9  subss   xmm8, xmm0
0x18008dbde  addss   xmm8, xmm1
0x18008dbe3  movss   xmm4, dword ptr [rdi]
0x18008dbe7  add     rdi, 4
0x18008dbeb  movss   xmm5, dword ptr [rsi]
0x18008dbef  movaps  xmm1, xmm4
0x18008dbf2  movss   xmm2, dword ptr [rbp+0]
0x18008dbf7  movaps  xmm0, xmm5
0x18008dbfa  movss   xmm3, dword ptr [r14]
0x18008dbff  add     rsi, 4
0x18008dc03  mulss   xmm1, xmm6
0x18008dc07  add     rbp, 4
0x18008dc0b  add     r14, 4
0x18008dc0f  mulss   xmm5, xmm6
0x18008dc13  mulss   xmm0, xmm7
0x18008dc17  mulss   xmm4, xmm7
0x18008dc1b  subss   xmm1, xmm0
0x18008dc1f  mulss   xmm2, xmm8
0x18008dc24  addss   xmm5, xmm4
0x18008dc28  mulss   xmm3, xmm8
0x18008dc2d  addss   xmm1, xmm2
0x18008dc31  addss   xmm5, xmm3
0x18008dc35  movss   dword ptr [r15], xmm1
0x18008dc3a  add     r15, 4
0x18008dc3e  movss   dword ptr [r12], xmm5
0x18008dc44  add     r12, 4
0x18008dc48  sub     edx, 1
0x18008dc4b  jnz     short loc_18008DBE3
0x18008dc4d  inc     ecx
0x18008dc4f  cmp     ecx, ebx
0x18008dc51  jl      loc_18008DB6B
0x18008dc57  mov     r11d, [rsp+0C8h+arg_8]
0x18008dc5f  mov     r13, [rsp+0C8h+arg_30]
0x18008dc67  mov     rcx, [rsp+0C8h+var_98]
0x18008dc6c  inc     r11d
0x18008dc6f  mov     rdx, [rsp+0C8h+var_90]
0x18008dc74  mov     r8, [rsp+0C8h+var_88]
0x18008dc79  mov     rax, [rsp+0C8h+var_80]
0x18008dc7e  mov     [rsp+0C8h+arg_8], r11d
0x18008dc86  cmp     r11d, [r10+60h]
0x18008dc8a  jl      loc_18008D9A0
0x18008dc90  movaps  xmm7, [rsp+0C8h+var_58]
0x18008dc95  lea     r11, [rsp+0C8h+var_38]
0x18008dc9d  mov     rbx, [r11+50h]
0x18008dca1  xor     eax, eax
0x18008dca3  movaps  xmm6, xmmword ptr [r11-10h]
0x18008dca8  movaps  xmm8, xmmword ptr [r11-30h]
0x18008dcad  movaps  xmm9, xmmword ptr [r11-40h]
0x18008dcb2  mov     rsp, r11
0x18008dcb5  pop     r15
0x18008dcb7  pop     r14
0x18008dcb9  pop     r13
0x18008dcbb  pop     r12
0x18008dcbd  pop     rdi
0x18008dcbe  pop     rsi
0x18008dcbf  pop     rbp
0x18008dcc0  retn
```
