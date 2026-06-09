# m7_ipps_BitRev1_C

- ea: `0x180017110`
- end: `0x1800176bb`
- name: `m7_ipps_BitRev1_C`
- size: `1451`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x18000e3c0`
- `0x18000e560`
- `0x18000e760`
- `0x18000efb0`
- `0x18000f1d0`
- `0x18000f364`
- `0x180029f08`
- `0x180029ff4`

## callees

- `0x180017110`

## pseudocode

```c
void __fastcall m7_ipps_BitRev1_C(double *a1, unsigned __int64 a2, __int64 a3)
{
  __int64 v3; // rbx
  __int64 v4; // r10
  __int64 v5; // rax
  __m128 *v6; // r13
  __m128 *v7; // r12
  __m128 v8; // xmm4
  __m128 v9; // xmm5
  __m128 v10; // xmm7
  __m128 v11; // xmm0
  __m128 v12; // xmm4
  __m128 v13; // xmm7
  __m128 v14; // xmm1
  __m128 v15; // xmm5
  __m128 v16; // xmm0
  __m128 v17; // xmm1
  __m128 v18; // xmm7
  __m128 v19; // xmm2
  __m128 v20; // xmm0
  __m128 v21; // xmm7
  __m128 v22; // xmm3
  __m128 v23; // xmm1
  __m128 v24; // xmm5
  __m128 v25; // xmm5
  __m128 v26; // xmm7
  __m128 v27; // xmm1
  __m128 v28; // xmm5
  __m128 v29; // xmm1
  __m128 v30; // xmm7
  __m128 v31; // xmm3
  __m128 *v32; // r12
  __m128 v33; // xmm4
  __m128 v34; // xmm5
  __m128 v35; // xmm7
  __m128 v36; // xmm0
  __m128 v37; // xmm4
  __m128 v38; // xmm7
  __m128 v39; // xmm1
  __m128 v40; // xmm5
  __m128 v41; // xmm0
  __m128 v42; // xmm1
  __m128 v43; // xmm7
  __m128 v44; // xmm2
  __m128 v45; // xmm0
  __m128 v46; // xmm7
  __m128 v47; // xmm3
  __m128 v48; // xmm1
  __m128 v49; // xmm5
  __m128 v50; // xmm5
  __m128 v51; // xmm7
  __m128 v52; // xmm1
  __m128 v53; // xmm5
  __m128 v54; // xmm1
  __m128 v55; // xmm7
  __m128 v56; // xmm3
  __m128 v57; // xmm0
  __m128 v58; // xmm1
  __m128 v59; // xmm3
  __m128 v60; // [rsp+0h] [rbp-118h]
  __m128 v61; // [rsp+0h] [rbp-118h]
  __m128 v62; // [rsp+0h] [rbp-118h]
  __m128 v63; // [rsp+0h] [rbp-118h]
  __m128 v64; // [rsp+10h] [rbp-108h]
  __m128 v65; // [rsp+10h] [rbp-108h]
  __m128 v66; // [rsp+10h] [rbp-108h]
  __m128 v67; // [rsp+10h] [rbp-108h]
  __m128 v68; // [rsp+20h] [rbp-F8h]
  __m128 v69; // [rsp+20h] [rbp-F8h]
  __m128 v70; // [rsp+20h] [rbp-F8h]
  __m128 v71; // [rsp+20h] [rbp-F8h]
  __m128 v72; // [rsp+30h] [rbp-E8h]
  __m128 v73; // [rsp+30h] [rbp-E8h]
  __m128 v74; // [rsp+30h] [rbp-E8h]
  __m128 v75; // [rsp+30h] [rbp-E8h]
  __m128 v76; // [rsp+40h] [rbp-D8h]
  __m128 v77; // [rsp+40h] [rbp-D8h]
  __m128 v78; // [rsp+50h] [rbp-C8h]
  __m128 v79; // [rsp+50h] [rbp-C8h]
  __m128 v80; // [rsp+60h] [rbp-B8h]
  __m128 v81; // [rsp+60h] [rbp-B8h]
  __m128 v82; // [rsp+70h] [rbp-A8h]
  __m128 v83; // [rsp+70h] [rbp-A8h]
  __m128 v84; // [rsp+80h] [rbp-98h]
  __m128 v85; // [rsp+80h] [rbp-98h]
  __m128 v86; // [rsp+A0h] [rbp-78h]
  __m128 v87; // [rsp+A0h] [rbp-78h]
  __m128 v88; // [rsp+A0h] [rbp-78h]
  __m128 v89; // [rsp+A0h] [rbp-78h]

  if ( a2 == 8 )
  {
    v57 = (__m128)*((unsigned __int64 *)a1 + 1);
    v58 = (__m128)*((unsigned __int64 *)a1 + 3);
    v59 = (__m128)*((unsigned __int64 *)a1 + 6);
    _mm_storel_ps(a1 + 1, (__m128)*((unsigned __int64 *)a1 + 4));
    _mm_storel_ps(a1 + 3, v59);
    _mm_storel_ps(a1 + 4, v57);
    _mm_storel_ps(a1 + 6, v58);
  }
  else
  {
    v3 = a3 + 4 * (a2 >> 4);
    v4 = 2 * a2;
    v5 = 6 * a2;
    v6 = (__m128 *)((char *)a1 + 2 * a2 - 32);
    if ( ((unsigned __int8)a1 & 0xF) != 0 )
    {
      do
      {
        v32 = (__m128 *)((char *)a1 + 4 * *(int *)(v3 - 4));
        v3 -= 4;
        if ( (__int64)v32 >= (__int64)v6 )
        {
          if ( v32 == v6 )
          {
            v63 = *v32;
            v67 = *(__m128 *)((char *)v32 + v4);
            v50 = *(__m128 *)((char *)v32 + 4 * a2 + 16);
            v71 = *(__m128 *)((char *)v32 + 4 * a2);
            v51 = v32[1];
            v52 = _mm_movelh_ps(v51, v50);
            v53 = _mm_movehl_ps(v50, v51);
            v89 = v52;
            v54 = *(__m128 *)((char *)v32 + v5 + 16);
            v75 = *(__m128 *)((char *)v32 + v5);
            v55 = *(__m128 *)((char *)v32 + v4 + 16);
            v56 = _mm_movelh_ps(v55, v54);
            *(__m128 *)((char *)v6 + v5) = v53;
            *(__m128 *)((char *)v6 + v5 + 16) = _mm_movehl_ps(v54, v55);
            v48 = _mm_movelh_ps(v63, v71);
            v49 = _mm_movelh_ps(v67, v75);
            *(__m128 *)((char *)v6 + 4 * a2) = _mm_movehl_ps(v71, v63);
            *(__m128 *)((char *)v6 + 4 * a2 + 16) = _mm_movehl_ps(v75, v67);
            *(__m128 *)((char *)v6 + v4) = v89;
            *(__m128 *)((char *)v6 + v4 + 16) = v56;
          }
          else
          {
            v77 = *v6;
            v62 = *v32;
            v79 = *(__m128 *)((char *)v6 + v4);
            v66 = *(__m128 *)((char *)v32 + v4);
            v33 = *(__m128 *)((char *)v6 + 4 * a2 + 16);
            v81 = *(__m128 *)((char *)v6 + 4 * a2);
            v34 = *(__m128 *)((char *)v32 + 4 * a2 + 16);
            v70 = *(__m128 *)((char *)v32 + 4 * a2);
            v35 = v6[1];
            v36 = _mm_movelh_ps(v35, v33);
            v37 = _mm_movehl_ps(v33, v35);
            v85 = v36;
            v38 = v32[1];
            v39 = _mm_movelh_ps(v38, v34);
            v40 = _mm_movehl_ps(v34, v38);
            v88 = v39;
            v41 = *(__m128 *)((char *)v6 + v5 + 16);
            v83 = *(__m128 *)((char *)v6 + v5);
            v42 = *(__m128 *)((char *)v32 + v5 + 16);
            v74 = *(__m128 *)((char *)v32 + v5);
            v43 = *(__m128 *)((char *)v6 + v4 + 16);
            v44 = _mm_movelh_ps(v43, v41);
            v45 = _mm_movehl_ps(v41, v43);
            v46 = *(__m128 *)((char *)v32 + v4 + 16);
            v47 = _mm_movelh_ps(v46, v42);
            *(__m128 *)((char *)v32 + v5) = v37;
            *(__m128 *)((char *)v32 + v5 + 16) = v45;
            *(__m128 *)((char *)v6 + v5) = v40;
            *(__m128 *)((char *)v6 + v5 + 16) = _mm_movehl_ps(v42, v46);
            *(__m128 *)((char *)v32 + 4 * a2) = _mm_movehl_ps(v81, v77);
            *(__m128 *)((char *)v32 + 4 * a2 + 16) = _mm_movehl_ps(v83, v79);
            v48 = _mm_movelh_ps(v62, v70);
            v49 = _mm_movelh_ps(v66, v74);
            *(__m128 *)((char *)v6 + 4 * a2) = _mm_movehl_ps(v70, v62);
            *(__m128 *)((char *)v6 + 4 * a2 + 16) = _mm_movehl_ps(v74, v66);
            *(__m128 *)((char *)v32 + v4) = v85;
            *(__m128 *)((char *)v32 + v4 + 16) = v44;
            *(__m128 *)((char *)v6 + v4) = v88;
            *(__m128 *)((char *)v6 + v4 + 16) = v47;
            *v32 = _mm_movelh_ps(v77, v81);
            v32[1] = _mm_movelh_ps(v79, v83);
          }
          *v6 = v48;
          v6[1] = v49;
        }
        v6 -= 2;
      }
      while ( (__int64)v6 >= (__int64)a1 );
    }
    else
    {
      do
      {
        v7 = (__m128 *)((char *)a1 + 4 * *(int *)(v3 - 4));
        v3 -= 4;
        if ( (__int64)v7 >= (__int64)v6 )
        {
          if ( v7 == v6 )
          {
            v61 = *v7;
            v65 = *(__m128 *)((char *)v7 + v4);
            v25 = *(__m128 *)((char *)v7 + 4 * a2 + 16);
            v69 = *(__m128 *)((char *)v7 + 4 * a2);
            v26 = v7[1];
            v27 = _mm_movelh_ps(v26, v25);
            v28 = _mm_movehl_ps(v25, v26);
            v87 = v27;
            v29 = *(__m128 *)((char *)v7 + v5 + 16);
            v73 = *(__m128 *)((char *)v7 + v5);
            v30 = *(__m128 *)((char *)v7 + v4 + 16);
            v31 = _mm_movelh_ps(v30, v29);
            *(__m128 *)((char *)v6 + v5) = v28;
            *(__m128 *)((char *)v6 + v5 + 16) = _mm_movehl_ps(v29, v30);
            v23 = _mm_movelh_ps(v61, v69);
            v24 = _mm_movelh_ps(v65, v73);
            *(__m128 *)((char *)v6 + 4 * a2) = _mm_movehl_ps(v69, v61);
            *(__m128 *)((char *)v6 + 4 * a2 + 16) = _mm_movehl_ps(v73, v65);
            *(__m128 *)((char *)v6 + v4) = v87;
            *(__m128 *)((char *)v6 + v4 + 16) = v31;
          }
          else
          {
            v76 = *v6;
            v60 = *v7;
            v78 = *(__m128 *)((char *)v6 + v4);
            v64 = *(__m128 *)((char *)v7 + v4);
            v8 = *(__m128 *)((char *)v6 + 4 * a2 + 16);
            v80 = *(__m128 *)((char *)v6 + 4 * a2);
            v9 = *(__m128 *)((char *)v7 + 4 * a2 + 16);
            v68 = *(__m128 *)((char *)v7 + 4 * a2);
            v10 = v6[1];
            v11 = _mm_movelh_ps(v10, v8);
            v12 = _mm_movehl_ps(v8, v10);
            v84 = v11;
            v13 = v7[1];
            v14 = _mm_movelh_ps(v13, v9);
            v15 = _mm_movehl_ps(v9, v13);
            v86 = v14;
            v16 = *(__m128 *)((char *)v6 + v5 + 16);
            v82 = *(__m128 *)((char *)v6 + v5);
            v17 = *(__m128 *)((char *)v7 + v5 + 16);
            v72 = *(__m128 *)((char *)v7 + v5);
            v18 = *(__m128 *)((char *)v6 + v4 + 16);
            v19 = _mm_movelh_ps(v18, v16);
            v20 = _mm_movehl_ps(v16, v18);
            v21 = *(__m128 *)((char *)v7 + v4 + 16);
            v22 = _mm_movelh_ps(v21, v17);
            *(__m128 *)((char *)v7 + v5) = v12;
            *(__m128 *)((char *)v7 + v5 + 16) = v20;
            *(__m128 *)((char *)v6 + v5) = v15;
            *(__m128 *)((char *)v6 + v5 + 16) = _mm_movehl_ps(v17, v21);
            *(__m128 *)((char *)v7 + 4 * a2) = _mm_movehl_ps(v80, v76);
            *(__m128 *)((char *)v7 + 4 * a2 + 16) = _mm_movehl_ps(v82, v78);
            v23 = _mm_movelh_ps(v60, v68);
            v24 = _mm_movelh_ps(v64, v72);
            *(__m128 *)((char *)v6 + 4 * a2) = _mm_movehl_ps(v68, v60);
            *(__m128 *)((char *)v6 + 4 * a2 + 16) = _mm_movehl_ps(v72, v64);
            *(__m128 *)((char *)v7 + v4) = v84;
            *(__m128 *)((char *)v7 + v4 + 16) = v19;
            *(__m128 *)((char *)v6 + v4) = v86;
            *(__m128 *)((char *)v6 + v4 + 16) = v22;
            *v7 = _mm_movelh_ps(v76, v80);
            v7[1] = _mm_movelh_ps(v78, v82);
          }
          *v6 = v23;
          v6[1] = v24;
        }
        v6 -= 2;
      }
      while ( (__int64)v6 >= (__int64)a1 );
    }
  }
}

```

## disassembly

```asm
0x180017110  push    rbx
0x180017111  push    rsi
0x180017112  push    rdi
0x180017113  push    rbp
0x180017114  push    r12
0x180017116  push    r13
0x180017118  sub     rsp, 0E8h
0x18001711f  movdqa  [rsp+118h+var_58], xmm7
0x180017128  movdqa  [rsp+118h+var_48], xmm6
0x180017131  mov     rdi, rcx
0x180017134  mov     rsi, rdx
0x180017137  mov     rdx, r8
0x18001713a  mov     r12, rdi
0x18001713d  mov     r10, rsi
0x180017140  cmp     r10, 8
0x180017144  jz      loc_180017665
0x18001714a  mov     rbx, rdx
0x18001714d  mov     rax, r10
0x180017150  shr     rax, 4
0x180017154  lea     rbx, [rbx+rax*4]
0x180017158  shl     r10, 1
0x18001715b  lea     rax, [r10+r10*2]
0x18001715f  mov     r11, r12
0x180017162  lea     r13, [r10+r12-20h]
0x180017167  test    r12, 0Fh
0x18001716e  jnz     loc_1800173EE
0x180017174  movsxd  r12, dword ptr [rbx-4]
0x180017178  lea     r12, [r11+r12*4]
0x18001717c  sub     rbx, 4
0x180017180  cmp     r12, r13
0x180017183  jl      loc_1800173DC
0x180017189  jz      loc_18001731A
0x18001718f  movaps  xmm7, xmmword ptr [r13+0]
0x180017194  movaps  xmm0, xmmword ptr [r13+10h]
0x180017199  movaps  [rsp+118h+var_D8], xmm7
0x18001719e  movaps  xmm7, xmmword ptr [r12]
0x1800171a3  movaps  xmm1, xmmword ptr [r12+10h]
0x1800171a9  movaps  [rsp+118h+var_118], xmm7
0x1800171ad  movaps  xmm7, xmmword ptr [r10+r13]
0x1800171b2  movaps  xmm2, xmmword ptr [r10+r13+10h]
0x1800171b8  movaps  [rsp+118h+var_C8], xmm7
0x1800171bd  movaps  xmm7, xmmword ptr [r10+r12]
0x1800171c2  movaps  xmm3, xmmword ptr [r10+r12+10h]
0x1800171c8  movaps  [rsp+118h+var_108], xmm7
0x1800171cd  movaps  xmm7, xmmword ptr [r13+r10*2+0]
0x1800171d3  movaps  xmm4, xmmword ptr [r13+r10*2+10h]
0x1800171d9  movaps  [rsp+118h+var_B8], xmm7
0x1800171de  movaps  xmm7, xmmword ptr [r12+r10*2]
0x1800171e3  movaps  xmm5, xmmword ptr [r12+r10*2+10h]
0x1800171e9  movaps  [rsp+118h+var_F8], xmm7
0x1800171ee  movaps  xmm7, xmm0
0x1800171f1  movlhps xmm0, xmm4
0x1800171f4  movhlps xmm4, xmm7
0x1800171f7  movaps  [rsp+118h+var_98], xmm0
0x1800171ff  movaps  xmm7, xmm1
0x180017202  movlhps xmm1, xmm5
0x180017205  movhlps xmm5, xmm7
0x180017208  movaps  [rsp+118h+var_78], xmm1
0x180017210  movaps  xmm7, xmmword ptr [rax+r13]
0x180017215  movaps  xmm0, xmmword ptr [rax+r13+10h]
0x18001721b  movaps  [rsp+118h+var_A8], xmm7
0x180017220  movaps  xmm7, xmmword ptr [rax+r12]
0x180017225  movaps  xmm1, xmmword ptr [rax+r12+10h]
0x18001722b  movaps  [rsp+118h+var_E8], xmm7
0x180017230  movaps  xmm7, xmm2
0x180017233  movlhps xmm2, xmm0
0x180017236  movhlps xmm0, xmm7
0x180017239  movaps  [rsp+118h+var_88], xmm2
0x180017241  movaps  xmm7, xmm3
0x180017244  movlhps xmm3, xmm1
0x180017247  movhlps xmm1, xmm7
0x18001724a  movaps  [rsp+118h+var_68], xmm3
0x180017252  movaps  xmmword ptr [rax+r12], xmm4
0x180017257  movaps  xmmword ptr [rax+r12+10h], xmm0
0x18001725d  movaps  xmmword ptr [rax+r13], xmm5
0x180017262  movaps  xmmword ptr [rax+r13+10h], xmm1
0x180017268  movaps  xmm0, [rsp+118h+var_D8]
0x18001726d  movaps  xmm1, [rsp+118h+var_B8]
0x180017272  movaps  xmm7, xmm0
0x180017275  movlhps xmm0, xmm1
0x180017278  movhlps xmm1, xmm7
0x18001727b  movaps  xmm4, [rsp+118h+var_C8]
0x180017280  movaps  xmm5, [rsp+118h+var_A8]
0x180017285  movaps  xmm7, xmm4
0x180017288  movlhps xmm4, xmm5
0x18001728b  movhlps xmm5, xmm7
0x18001728e  movaps  xmmword ptr [r12+r10*2], xmm1
0x180017293  movaps  xmmword ptr [r12+r10*2+10h], xmm5
0x180017299  movaps  xmm1, [rsp+118h+var_118]
0x18001729d  movaps  xmm2, [rsp+118h+var_F8]
0x1800172a2  movaps  xmm7, xmm1
0x1800172a5  movlhps xmm1, xmm2
0x1800172a8  movhlps xmm2, xmm7
0x1800172ab  movaps  xmm5, [rsp+118h+var_108]
0x1800172b0  movaps  xmm6, [rsp+118h+var_E8]
0x1800172b5  movaps  xmm7, xmm5
0x1800172b8  movlhps xmm5, xmm6
0x1800172bb  movhlps xmm6, xmm7
0x1800172be  movaps  xmmword ptr [r13+r10*2+0], xmm2
0x1800172c4  movaps  xmmword ptr [r13+r10*2+10h], xmm6
0x1800172ca  movaps  xmm2, [rsp+118h+var_98]
0x1800172d2  movaps  xmm3, [rsp+118h+var_88]
0x1800172da  movaps  xmm6, [rsp+118h+var_78]
0x1800172e2  movaps  xmm7, [rsp+118h+var_68]
0x1800172ea  movaps  xmmword ptr [r10+r12], xmm2
0x1800172ef  movaps  xmmword ptr [r10+r12+10h], xmm3
0x1800172f5  movaps  xmmword ptr [r10+r13], xmm6
0x1800172fa  movaps  xmmword ptr [r10+r13+10h], xmm7
0x180017300  movaps  xmmword ptr [r12], xmm0
0x180017305  movaps  xmmword ptr [r12+10h], xmm4
0x18001730b  movaps  xmmword ptr [r13+0], xmm1
0x180017310  movaps  xmmword ptr [r13+10h], xmm5
0x180017315  jmp     loc_1800173DC
0x18001731a  movaps  xmm7, xmmword ptr [r12]
0x18001731f  movaps  xmm1, xmmword ptr [r12+10h]
0x180017325  movaps  [rsp+118h+var_118], xmm7
0x180017329  movaps  xmm7, xmmword ptr [r10+r12]
0x18001732e  movaps  xmm3, xmmword ptr [r10+r12+10h]
0x180017334  movaps  [rsp+118h+var_108], xmm7
0x180017339  movaps  xmm7, xmmword ptr [r12+r10*2]
0x18001733e  movaps  xmm5, xmmword ptr [r12+r10*2+10h]
0x180017344  movaps  [rsp+118h+var_F8], xmm7
0x180017349  movaps  xmm7, xmm1
0x18001734c  movlhps xmm1, xmm5
0x18001734f  movhlps xmm5, xmm7
0x180017352  movaps  [rsp+118h+var_78], xmm1
0x18001735a  movaps  xmm7, xmmword ptr [rax+r12]
0x18001735f  movaps  xmm1, xmmword ptr [rax+r12+10h]
0x180017365  movaps  [rsp+118h+var_E8], xmm7
0x18001736a  movaps  xmm7, xmm3
0x18001736d  movlhps xmm3, xmm1
0x180017370  movhlps xmm1, xmm7
0x180017373  movaps  [rsp+118h+var_68], xmm3
0x18001737b  movaps  xmmword ptr [rax+r13], xmm5
0x180017380  movaps  xmmword ptr [rax+r13+10h], xmm1
0x180017386  movaps  xmm1, [rsp+118h+var_118]
0x18001738a  movaps  xmm2, [rsp+118h+var_F8]
0x18001738f  movaps  xmm7, xmm1
0x180017392  movlhps xmm1, xmm2
0x180017395  movhlps xmm2, xmm7
0x180017398  movaps  xmm5, [rsp+118h+var_108]
0x18001739d  movaps  xmm6, [rsp+118h+var_E8]
0x1800173a2  movaps  xmm7, xmm5
0x1800173a5  movlhps xmm5, xmm6
0x1800173a8  movhlps xmm6, xmm7
0x1800173ab  movaps  xmmword ptr [r13+r10*2+0], xmm2
0x1800173b1  movaps  xmmword ptr [r13+r10*2+10h], xmm6
0x1800173b7  movaps  xmm6, [rsp+118h+var_78]
0x1800173bf  movaps  xmm7, [rsp+118h+var_68]
0x1800173c7  movaps  xmmword ptr [r10+r13], xmm6
0x1800173cc  movaps  xmmword ptr [r10+r13+10h], xmm7
0x1800173d2  movaps  xmmword ptr [r13+0], xmm1
0x1800173d7  movaps  xmmword ptr [r13+10h], xmm5
0x1800173dc  sub     r13, 20h ; ' '
0x1800173e0  cmp     r13, rdi
0x1800173e3  jge     loc_180017174
0x1800173e9  jmp     loc_180017699
0x1800173ee  movsxd  r12, dword ptr [rbx-4]
0x1800173f2  lea     r12, [r11+r12*4]
0x1800173f6  sub     rbx, 4
0x1800173fa  cmp     r12, r13
0x1800173fd  jl      loc_180017656
0x180017403  jz      loc_180017594
0x180017409  movups  xmm7, xmmword ptr [r13+0]
0x18001740e  movups  xmm0, xmmword ptr [r13+10h]
0x180017413  movaps  [rsp+118h+var_D8], xmm7
0x180017418  movups  xmm7, xmmword ptr [r12]
0x18001741d  movups  xmm1, xmmword ptr [r12+10h]
0x180017423  movaps  [rsp+118h+var_118], xmm7
0x180017427  movups  xmm7, xmmword ptr [r10+r13]
0x18001742c  movups  xmm2, xmmword ptr [r10+r13+10h]
0x180017432  movaps  [rsp+118h+var_C8], xmm7
0x180017437  movups  xmm7, xmmword ptr [r10+r12]
0x18001743c  movups  xmm3, xmmword ptr [r10+r12+10h]
0x180017442  movaps  [rsp+118h+var_108], xmm7
0x180017447  movups  xmm7, xmmword ptr [r13+r10*2+0]
0x18001744d  movups  xmm4, xmmword ptr [r13+r10*2+10h]
0x180017453  movaps  [rsp+118h+var_B8], xmm7
0x180017458  movups  xmm7, xmmword ptr [r12+r10*2]
0x18001745d  movups  xmm5, xmmword ptr [r12+r10*2+10h]
0x180017463  movaps  [rsp+118h+var_F8], xmm7
0x180017468  movaps  xmm7, xmm0
0x18001746b  movlhps xmm0, xmm4
0x18001746e  movhlps xmm4, xmm7
0x180017471  movaps  [rsp+118h+var_98], xmm0
0x180017479  movaps  xmm7, xmm1
0x18001747c  movlhps xmm1, xmm5
0x18001747f  movhlps xmm5, xmm7
0x180017482  movaps  [rsp+118h+var_78], xmm1
0x18001748a  movups  xmm7, xmmword ptr [rax+r13]
0x18001748f  movups  xmm0, xmmword ptr [rax+r13+10h]
0x180017495  movaps  [rsp+118h+var_A8], xmm7
0x18001749a  movups  xmm7, xmmword ptr [rax+r12]
0x18001749f  movups  xmm1, xmmword ptr [rax+r12+10h]
0x1800174a5  movaps  [rsp+118h+var_E8], xmm7
0x1800174aa  movaps  xmm7, xmm2
0x1800174ad  movlhps xmm2, xmm0
0x1800174b0  movhlps xmm0, xmm7
0x1800174b3  movaps  [rsp+118h+var_88], xmm2
0x1800174bb  movaps  xmm7, xmm3
0x1800174be  movlhps xmm3, xmm1
0x1800174c1  movhlps xmm1, xmm7
0x1800174c4  movaps  [rsp+118h+var_68], xmm3
0x1800174cc  movups  xmmword ptr [rax+r12], xmm4
0x1800174d1  movups  xmmword ptr [rax+r12+10h], xmm0
0x1800174d7  movups  xmmword ptr [rax+r13], xmm5
0x1800174dc  movups  xmmword ptr [rax+r13+10h], xmm1
0x1800174e2  movaps  xmm0, [rsp+118h+var_D8]
0x1800174e7  movaps  xmm1, [rsp+118h+var_B8]
0x1800174ec  movaps  xmm7, xmm0
0x1800174ef  movlhps xmm0, xmm1
0x1800174f2  movhlps xmm1, xmm7
0x1800174f5  movaps  xmm4, [rsp+118h+var_C8]
0x1800174fa  movaps  xmm5, [rsp+118h+var_A8]
0x1800174ff  movaps  xmm7, xmm4
0x180017502  movlhps xmm4, xmm5
0x180017505  movhlps xmm5, xmm7
0x180017508  movups  xmmword ptr [r12+r10*2], xmm1
0x18001750d  movups  xmmword ptr [r12+r10*2+10h], xmm5
0x180017513  movaps  xmm1, [rsp+118h+var_118]
0x180017517  movaps  xmm2, [rsp+118h+var_F8]
0x18001751c  movaps  xmm7, xmm1
0x18001751f  movlhps xmm1, xmm2
0x180017522  movhlps xmm2, xmm7
0x180017525  movaps  xmm5, [rsp+118h+var_108]
0x18001752a  movaps  xmm6, [rsp+118h+var_E8]
0x18001752f  movaps  xmm7, xmm5
0x180017532  movlhps xmm5, xmm6
0x180017535  movhlps xmm6, xmm7
0x180017538  movups  xmmword ptr [r13+r10*2+0], xmm2
0x18001753e  movups  xmmword ptr [r13+r10*2+10h], xmm6
0x180017544  movaps  xmm2, [rsp+118h+var_98]
0x18001754c  movaps  xmm3, [rsp+118h+var_88]
0x180017554  movaps  xmm6, [rsp+118h+var_78]
0x18001755c  movaps  xmm7, [rsp+118h+var_68]
0x180017564  movups  xmmword ptr [r10+r12], xmm2
0x180017569  movups  xmmword ptr [r10+r12+10h], xmm3
0x18001756f  movups  xmmword ptr [r10+r13], xmm6
0x180017574  movups  xmmword ptr [r10+r13+10h], xmm7
0x18001757a  movups  xmmword ptr [r12], xmm0
0x18001757f  movups  xmmword ptr [r12+10h], xmm4
0x180017585  movups  xmmword ptr [r13+0], xmm1
0x18001758a  movups  xmmword ptr [r13+10h], xmm5
0x18001758f  jmp     loc_180017656
0x180017594  movups  xmm7, xmmword ptr [r12]
0x180017599  movups  xmm1, xmmword ptr [r12+10h]
0x18001759f  movaps  [rsp+118h+var_118], xmm7
0x1800175a3  movups  xmm7, xmmword ptr [r10+r12]
0x1800175a8  movups  xmm3, xmmword ptr [r10+r12+10h]
0x1800175ae  movaps  [rsp+118h+var_108], xmm7
0x1800175b3  movups  xmm7, xmmword ptr [r12+r10*2]
0x1800175b8  movups  xmm5, xmmword ptr [r12+r10*2+10h]
0x1800175be  movaps  [rsp+118h+var_F8], xmm7
0x1800175c3  movaps  xmm7, xmm1
0x1800175c6  movlhps xmm1, xmm5
0x1800175c9  movhlps xmm5, xmm7
0x1800175cc  movaps  [rsp+118h+var_78], xmm1
0x1800175d4  movups  xmm7, xmmword ptr [rax+r12]
0x1800175d9  movups  xmm1, xmmword ptr [rax+r12+10h]
0x1800175df  movaps  [rsp+118h+var_E8], xmm7
0x1800175e4  movaps  xmm7, xmm3
0x1800175e7  movlhps xmm3, xmm1
0x1800175ea  movhlps xmm1, xmm7
0x1800175ed  movaps  [rsp+118h+var_68], xmm3
0x1800175f5  movups  xmmword ptr [rax+r13], xmm5
0x1800175fa  movups  xmmword ptr [rax+r13+10h], xmm1
0x180017600  movaps  xmm1, [rsp+118h+var_118]
0x180017604  movaps  xmm2, [rsp+118h+var_F8]
0x180017609  movaps  xmm7, xmm1
0x18001760c  movlhps xmm1, xmm2
0x18001760f  movhlps xmm2, xmm7
0x180017612  movaps  xmm5, [rsp+118h+var_108]
0x180017617  movaps  xmm6, [rsp+118h+var_E8]
0x18001761c  movaps  xmm7, xmm5
0x18001761f  movlhps xmm5, xmm6
0x180017622  movhlps xmm6, xmm7
0x180017625  movups  xmmword ptr [r13+r10*2+0], xmm2
0x18001762b  movups  xmmword ptr [r13+r10*2+10h], xmm6
0x180017631  movaps  xmm6, [rsp+118h+var_78]
0x180017639  movaps  xmm7, [rsp+118h+var_68]
0x180017641  movups  xmmword ptr [r10+r13], xmm6
0x180017646  movups  xmmword ptr [r10+r13+10h], xmm7
0x18001764c  movups  xmmword ptr [r13+0], xmm1
0x180017651  movups  xmmword ptr [r13+10h], xmm5
0x180017656  sub     r13, 20h ; ' '
0x18001765a  cmp     r13, rdi
0x18001765d  jge     loc_1800173EE
0x180017663  jmp     short loc_180017699
0x180017665  movsd   xmm0, qword ptr [r12+8]
0x18001766c  movsd   xmm1, qword ptr [r12+18h]
0x180017673  movsd   xmm2, qword ptr [r12+20h]
0x18001767a  movsd   xmm3, qword ptr [r12+30h]
0x180017681  movlps  qword ptr [r12+8], xmm2
0x180017687  movlps  qword ptr [r12+18h], xmm3
0x18001768d  movlps  qword ptr [r12+20h], xmm0
0x180017693  movlps  qword ptr [r12+30h], xmm1
0x180017699  movdqa  xmm7, [rsp+118h+var_58]
0x1800176a2  movdqa  xmm6, [rsp+118h+var_48]
0x1800176ab  add     rsp, 0E8h
0x1800176b2  pop     r13
  ... truncated ...
```
