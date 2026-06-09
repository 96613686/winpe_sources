# u8_ipps_BitRev1_C

- ea: `0x18002c320`
- end: `0x18002c8cb`
- name: `u8_ipps_BitRev1_C`
- size: `1451`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x18000f680`
- `0x18000f820`
- `0x18000fa20`
- `0x180010270`
- `0x180010490`
- `0x180010624`
- `0x1800406c0`
- `0x1800407c0`

## callees

- `0x18002c320`

## pseudocode

```c
void __fastcall u8_ipps_BitRev1_C(double *a1, unsigned __int64 a2, __int64 a3)
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
0x18002c320  push    rbx
0x18002c321  push    rsi
0x18002c322  push    rdi
0x18002c323  push    rbp
0x18002c324  push    r12
0x18002c326  push    r13
0x18002c328  sub     rsp, 0E8h
0x18002c32f  movdqa  [rsp+118h+var_58], xmm7
0x18002c338  movdqa  [rsp+118h+var_48], xmm6
0x18002c341  mov     rdi, rcx
0x18002c344  mov     rsi, rdx
0x18002c347  mov     rdx, r8
0x18002c34a  mov     r12, rdi
0x18002c34d  mov     r10, rsi
0x18002c350  cmp     r10, 8
0x18002c354  jz      loc_18002C875
0x18002c35a  mov     rbx, rdx
0x18002c35d  mov     rax, r10
0x18002c360  shr     rax, 4
0x18002c364  lea     rbx, [rbx+rax*4]
0x18002c368  shl     r10, 1
0x18002c36b  lea     rax, [r10+r10*2]
0x18002c36f  mov     r11, r12
0x18002c372  lea     r13, [r10+r12-20h]
0x18002c377  test    r12, 0Fh
0x18002c37e  jnz     loc_18002C5FE
0x18002c384  movsxd  r12, dword ptr [rbx-4]
0x18002c388  lea     r12, [r11+r12*4]
0x18002c38c  sub     rbx, 4
0x18002c390  cmp     r12, r13
0x18002c393  jl      loc_18002C5EC
0x18002c399  jz      loc_18002C52A
0x18002c39f  movaps  xmm7, xmmword ptr [r13+0]
0x18002c3a4  movaps  xmm0, xmmword ptr [r13+10h]
0x18002c3a9  movaps  [rsp+118h+var_D8], xmm7
0x18002c3ae  movaps  xmm7, xmmword ptr [r12]
0x18002c3b3  movaps  xmm1, xmmword ptr [r12+10h]
0x18002c3b9  movaps  [rsp+118h+var_118], xmm7
0x18002c3bd  movaps  xmm7, xmmword ptr [r10+r13]
0x18002c3c2  movaps  xmm2, xmmword ptr [r10+r13+10h]
0x18002c3c8  movaps  [rsp+118h+var_C8], xmm7
0x18002c3cd  movaps  xmm7, xmmword ptr [r10+r12]
0x18002c3d2  movaps  xmm3, xmmword ptr [r10+r12+10h]
0x18002c3d8  movaps  [rsp+118h+var_108], xmm7
0x18002c3dd  movaps  xmm7, xmmword ptr [r13+r10*2+0]
0x18002c3e3  movaps  xmm4, xmmword ptr [r13+r10*2+10h]
0x18002c3e9  movaps  [rsp+118h+var_B8], xmm7
0x18002c3ee  movaps  xmm7, xmmword ptr [r12+r10*2]
0x18002c3f3  movaps  xmm5, xmmword ptr [r12+r10*2+10h]
0x18002c3f9  movaps  [rsp+118h+var_F8], xmm7
0x18002c3fe  movaps  xmm7, xmm0
0x18002c401  movlhps xmm0, xmm4
0x18002c404  movhlps xmm4, xmm7
0x18002c407  movaps  [rsp+118h+var_98], xmm0
0x18002c40f  movaps  xmm7, xmm1
0x18002c412  movlhps xmm1, xmm5
0x18002c415  movhlps xmm5, xmm7
0x18002c418  movaps  [rsp+118h+var_78], xmm1
0x18002c420  movaps  xmm7, xmmword ptr [rax+r13]
0x18002c425  movaps  xmm0, xmmword ptr [rax+r13+10h]
0x18002c42b  movaps  [rsp+118h+var_A8], xmm7
0x18002c430  movaps  xmm7, xmmword ptr [rax+r12]
0x18002c435  movaps  xmm1, xmmword ptr [rax+r12+10h]
0x18002c43b  movaps  [rsp+118h+var_E8], xmm7
0x18002c440  movaps  xmm7, xmm2
0x18002c443  movlhps xmm2, xmm0
0x18002c446  movhlps xmm0, xmm7
0x18002c449  movaps  [rsp+118h+var_88], xmm2
0x18002c451  movaps  xmm7, xmm3
0x18002c454  movlhps xmm3, xmm1
0x18002c457  movhlps xmm1, xmm7
0x18002c45a  movaps  [rsp+118h+var_68], xmm3
0x18002c462  movaps  xmmword ptr [rax+r12], xmm4
0x18002c467  movaps  xmmword ptr [rax+r12+10h], xmm0
0x18002c46d  movaps  xmmword ptr [rax+r13], xmm5
0x18002c472  movaps  xmmword ptr [rax+r13+10h], xmm1
0x18002c478  movaps  xmm0, [rsp+118h+var_D8]
0x18002c47d  movaps  xmm1, [rsp+118h+var_B8]
0x18002c482  movaps  xmm7, xmm0
0x18002c485  movlhps xmm0, xmm1
0x18002c488  movhlps xmm1, xmm7
0x18002c48b  movaps  xmm4, [rsp+118h+var_C8]
0x18002c490  movaps  xmm5, [rsp+118h+var_A8]
0x18002c495  movaps  xmm7, xmm4
0x18002c498  movlhps xmm4, xmm5
0x18002c49b  movhlps xmm5, xmm7
0x18002c49e  movaps  xmmword ptr [r12+r10*2], xmm1
0x18002c4a3  movaps  xmmword ptr [r12+r10*2+10h], xmm5
0x18002c4a9  movaps  xmm1, [rsp+118h+var_118]
0x18002c4ad  movaps  xmm2, [rsp+118h+var_F8]
0x18002c4b2  movaps  xmm7, xmm1
0x18002c4b5  movlhps xmm1, xmm2
0x18002c4b8  movhlps xmm2, xmm7
0x18002c4bb  movaps  xmm5, [rsp+118h+var_108]
0x18002c4c0  movaps  xmm6, [rsp+118h+var_E8]
0x18002c4c5  movaps  xmm7, xmm5
0x18002c4c8  movlhps xmm5, xmm6
0x18002c4cb  movhlps xmm6, xmm7
0x18002c4ce  movaps  xmmword ptr [r13+r10*2+0], xmm2
0x18002c4d4  movaps  xmmword ptr [r13+r10*2+10h], xmm6
0x18002c4da  movaps  xmm2, [rsp+118h+var_98]
0x18002c4e2  movaps  xmm3, [rsp+118h+var_88]
0x18002c4ea  movaps  xmm6, [rsp+118h+var_78]
0x18002c4f2  movaps  xmm7, [rsp+118h+var_68]
0x18002c4fa  movaps  xmmword ptr [r10+r12], xmm2
0x18002c4ff  movaps  xmmword ptr [r10+r12+10h], xmm3
0x18002c505  movaps  xmmword ptr [r10+r13], xmm6
0x18002c50a  movaps  xmmword ptr [r10+r13+10h], xmm7
0x18002c510  movaps  xmmword ptr [r12], xmm0
0x18002c515  movaps  xmmword ptr [r12+10h], xmm4
0x18002c51b  movaps  xmmword ptr [r13+0], xmm1
0x18002c520  movaps  xmmword ptr [r13+10h], xmm5
0x18002c525  jmp     loc_18002C5EC
0x18002c52a  movaps  xmm7, xmmword ptr [r12]
0x18002c52f  movaps  xmm1, xmmword ptr [r12+10h]
0x18002c535  movaps  [rsp+118h+var_118], xmm7
0x18002c539  movaps  xmm7, xmmword ptr [r10+r12]
0x18002c53e  movaps  xmm3, xmmword ptr [r10+r12+10h]
0x18002c544  movaps  [rsp+118h+var_108], xmm7
0x18002c549  movaps  xmm7, xmmword ptr [r12+r10*2]
0x18002c54e  movaps  xmm5, xmmword ptr [r12+r10*2+10h]
0x18002c554  movaps  [rsp+118h+var_F8], xmm7
0x18002c559  movaps  xmm7, xmm1
0x18002c55c  movlhps xmm1, xmm5
0x18002c55f  movhlps xmm5, xmm7
0x18002c562  movaps  [rsp+118h+var_78], xmm1
0x18002c56a  movaps  xmm7, xmmword ptr [rax+r12]
0x18002c56f  movaps  xmm1, xmmword ptr [rax+r12+10h]
0x18002c575  movaps  [rsp+118h+var_E8], xmm7
0x18002c57a  movaps  xmm7, xmm3
0x18002c57d  movlhps xmm3, xmm1
0x18002c580  movhlps xmm1, xmm7
0x18002c583  movaps  [rsp+118h+var_68], xmm3
0x18002c58b  movaps  xmmword ptr [rax+r13], xmm5
0x18002c590  movaps  xmmword ptr [rax+r13+10h], xmm1
0x18002c596  movaps  xmm1, [rsp+118h+var_118]
0x18002c59a  movaps  xmm2, [rsp+118h+var_F8]
0x18002c59f  movaps  xmm7, xmm1
0x18002c5a2  movlhps xmm1, xmm2
0x18002c5a5  movhlps xmm2, xmm7
0x18002c5a8  movaps  xmm5, [rsp+118h+var_108]
0x18002c5ad  movaps  xmm6, [rsp+118h+var_E8]
0x18002c5b2  movaps  xmm7, xmm5
0x18002c5b5  movlhps xmm5, xmm6
0x18002c5b8  movhlps xmm6, xmm7
0x18002c5bb  movaps  xmmword ptr [r13+r10*2+0], xmm2
0x18002c5c1  movaps  xmmword ptr [r13+r10*2+10h], xmm6
0x18002c5c7  movaps  xmm6, [rsp+118h+var_78]
0x18002c5cf  movaps  xmm7, [rsp+118h+var_68]
0x18002c5d7  movaps  xmmword ptr [r10+r13], xmm6
0x18002c5dc  movaps  xmmword ptr [r10+r13+10h], xmm7
0x18002c5e2  movaps  xmmword ptr [r13+0], xmm1
0x18002c5e7  movaps  xmmword ptr [r13+10h], xmm5
0x18002c5ec  sub     r13, 20h ; ' '
0x18002c5f0  cmp     r13, rdi
0x18002c5f3  jge     loc_18002C384
0x18002c5f9  jmp     loc_18002C8A9
0x18002c5fe  movsxd  r12, dword ptr [rbx-4]
0x18002c602  lea     r12, [r11+r12*4]
0x18002c606  sub     rbx, 4
0x18002c60a  cmp     r12, r13
0x18002c60d  jl      loc_18002C866
0x18002c613  jz      loc_18002C7A4
0x18002c619  movups  xmm7, xmmword ptr [r13+0]
0x18002c61e  movups  xmm0, xmmword ptr [r13+10h]
0x18002c623  movaps  [rsp+118h+var_D8], xmm7
0x18002c628  movups  xmm7, xmmword ptr [r12]
0x18002c62d  movups  xmm1, xmmword ptr [r12+10h]
0x18002c633  movaps  [rsp+118h+var_118], xmm7
0x18002c637  movups  xmm7, xmmword ptr [r10+r13]
0x18002c63c  movups  xmm2, xmmword ptr [r10+r13+10h]
0x18002c642  movaps  [rsp+118h+var_C8], xmm7
0x18002c647  movups  xmm7, xmmword ptr [r10+r12]
0x18002c64c  movups  xmm3, xmmword ptr [r10+r12+10h]
0x18002c652  movaps  [rsp+118h+var_108], xmm7
0x18002c657  movups  xmm7, xmmword ptr [r13+r10*2+0]
0x18002c65d  movups  xmm4, xmmword ptr [r13+r10*2+10h]
0x18002c663  movaps  [rsp+118h+var_B8], xmm7
0x18002c668  movups  xmm7, xmmword ptr [r12+r10*2]
0x18002c66d  movups  xmm5, xmmword ptr [r12+r10*2+10h]
0x18002c673  movaps  [rsp+118h+var_F8], xmm7
0x18002c678  movaps  xmm7, xmm0
0x18002c67b  movlhps xmm0, xmm4
0x18002c67e  movhlps xmm4, xmm7
0x18002c681  movaps  [rsp+118h+var_98], xmm0
0x18002c689  movaps  xmm7, xmm1
0x18002c68c  movlhps xmm1, xmm5
0x18002c68f  movhlps xmm5, xmm7
0x18002c692  movaps  [rsp+118h+var_78], xmm1
0x18002c69a  movups  xmm7, xmmword ptr [rax+r13]
0x18002c69f  movups  xmm0, xmmword ptr [rax+r13+10h]
0x18002c6a5  movaps  [rsp+118h+var_A8], xmm7
0x18002c6aa  movups  xmm7, xmmword ptr [rax+r12]
0x18002c6af  movups  xmm1, xmmword ptr [rax+r12+10h]
0x18002c6b5  movaps  [rsp+118h+var_E8], xmm7
0x18002c6ba  movaps  xmm7, xmm2
0x18002c6bd  movlhps xmm2, xmm0
0x18002c6c0  movhlps xmm0, xmm7
0x18002c6c3  movaps  [rsp+118h+var_88], xmm2
0x18002c6cb  movaps  xmm7, xmm3
0x18002c6ce  movlhps xmm3, xmm1
0x18002c6d1  movhlps xmm1, xmm7
0x18002c6d4  movaps  [rsp+118h+var_68], xmm3
0x18002c6dc  movups  xmmword ptr [rax+r12], xmm4
0x18002c6e1  movups  xmmword ptr [rax+r12+10h], xmm0
0x18002c6e7  movups  xmmword ptr [rax+r13], xmm5
0x18002c6ec  movups  xmmword ptr [rax+r13+10h], xmm1
0x18002c6f2  movaps  xmm0, [rsp+118h+var_D8]
0x18002c6f7  movaps  xmm1, [rsp+118h+var_B8]
0x18002c6fc  movaps  xmm7, xmm0
0x18002c6ff  movlhps xmm0, xmm1
0x18002c702  movhlps xmm1, xmm7
0x18002c705  movaps  xmm4, [rsp+118h+var_C8]
0x18002c70a  movaps  xmm5, [rsp+118h+var_A8]
0x18002c70f  movaps  xmm7, xmm4
0x18002c712  movlhps xmm4, xmm5
0x18002c715  movhlps xmm5, xmm7
0x18002c718  movups  xmmword ptr [r12+r10*2], xmm1
0x18002c71d  movups  xmmword ptr [r12+r10*2+10h], xmm5
0x18002c723  movaps  xmm1, [rsp+118h+var_118]
0x18002c727  movaps  xmm2, [rsp+118h+var_F8]
0x18002c72c  movaps  xmm7, xmm1
0x18002c72f  movlhps xmm1, xmm2
0x18002c732  movhlps xmm2, xmm7
0x18002c735  movaps  xmm5, [rsp+118h+var_108]
0x18002c73a  movaps  xmm6, [rsp+118h+var_E8]
0x18002c73f  movaps  xmm7, xmm5
0x18002c742  movlhps xmm5, xmm6
0x18002c745  movhlps xmm6, xmm7
0x18002c748  movups  xmmword ptr [r13+r10*2+0], xmm2
0x18002c74e  movups  xmmword ptr [r13+r10*2+10h], xmm6
0x18002c754  movaps  xmm2, [rsp+118h+var_98]
0x18002c75c  movaps  xmm3, [rsp+118h+var_88]
0x18002c764  movaps  xmm6, [rsp+118h+var_78]
0x18002c76c  movaps  xmm7, [rsp+118h+var_68]
0x18002c774  movups  xmmword ptr [r10+r12], xmm2
0x18002c779  movups  xmmword ptr [r10+r12+10h], xmm3
0x18002c77f  movups  xmmword ptr [r10+r13], xmm6
0x18002c784  movups  xmmword ptr [r10+r13+10h], xmm7
0x18002c78a  movups  xmmword ptr [r12], xmm0
0x18002c78f  movups  xmmword ptr [r12+10h], xmm4
0x18002c795  movups  xmmword ptr [r13+0], xmm1
0x18002c79a  movups  xmmword ptr [r13+10h], xmm5
0x18002c79f  jmp     loc_18002C866
0x18002c7a4  movups  xmm7, xmmword ptr [r12]
0x18002c7a9  movups  xmm1, xmmword ptr [r12+10h]
0x18002c7af  movaps  [rsp+118h+var_118], xmm7
0x18002c7b3  movups  xmm7, xmmword ptr [r10+r12]
0x18002c7b8  movups  xmm3, xmmword ptr [r10+r12+10h]
0x18002c7be  movaps  [rsp+118h+var_108], xmm7
0x18002c7c3  movups  xmm7, xmmword ptr [r12+r10*2]
0x18002c7c8  movups  xmm5, xmmword ptr [r12+r10*2+10h]
0x18002c7ce  movaps  [rsp+118h+var_F8], xmm7
0x18002c7d3  movaps  xmm7, xmm1
0x18002c7d6  movlhps xmm1, xmm5
0x18002c7d9  movhlps xmm5, xmm7
0x18002c7dc  movaps  [rsp+118h+var_78], xmm1
0x18002c7e4  movups  xmm7, xmmword ptr [rax+r12]
0x18002c7e9  movups  xmm1, xmmword ptr [rax+r12+10h]
0x18002c7ef  movaps  [rsp+118h+var_E8], xmm7
0x18002c7f4  movaps  xmm7, xmm3
0x18002c7f7  movlhps xmm3, xmm1
0x18002c7fa  movhlps xmm1, xmm7
0x18002c7fd  movaps  [rsp+118h+var_68], xmm3
0x18002c805  movups  xmmword ptr [rax+r13], xmm5
0x18002c80a  movups  xmmword ptr [rax+r13+10h], xmm1
0x18002c810  movaps  xmm1, [rsp+118h+var_118]
0x18002c814  movaps  xmm2, [rsp+118h+var_F8]
0x18002c819  movaps  xmm7, xmm1
0x18002c81c  movlhps xmm1, xmm2
0x18002c81f  movhlps xmm2, xmm7
0x18002c822  movaps  xmm5, [rsp+118h+var_108]
0x18002c827  movaps  xmm6, [rsp+118h+var_E8]
0x18002c82c  movaps  xmm7, xmm5
0x18002c82f  movlhps xmm5, xmm6
0x18002c832  movhlps xmm6, xmm7
0x18002c835  movups  xmmword ptr [r13+r10*2+0], xmm2
0x18002c83b  movups  xmmword ptr [r13+r10*2+10h], xmm6
0x18002c841  movaps  xmm6, [rsp+118h+var_78]
0x18002c849  movaps  xmm7, [rsp+118h+var_68]
0x18002c851  movups  xmmword ptr [r10+r13], xmm6
0x18002c856  movups  xmmword ptr [r10+r13+10h], xmm7
0x18002c85c  movups  xmmword ptr [r13+0], xmm1
0x18002c861  movups  xmmword ptr [r13+10h], xmm5
0x18002c866  sub     r13, 20h ; ' '
0x18002c86a  cmp     r13, rdi
0x18002c86d  jge     loc_18002C5FE
0x18002c873  jmp     short loc_18002C8A9
0x18002c875  movsd   xmm0, qword ptr [r12+8]
0x18002c87c  movsd   xmm1, qword ptr [r12+18h]
0x18002c883  movsd   xmm2, qword ptr [r12+20h]
0x18002c88a  movsd   xmm3, qword ptr [r12+30h]
0x18002c891  movlps  qword ptr [r12+8], xmm2
0x18002c897  movlps  qword ptr [r12+18h], xmm3
0x18002c89d  movlps  qword ptr [r12+20h], xmm0
0x18002c8a3  movlps  qword ptr [r12+30h], xmm1
0x18002c8a9  movdqa  xmm7, [rsp+118h+var_58]
0x18002c8b2  movdqa  xmm6, [rsp+118h+var_48]
0x18002c8bb  add     rsp, 0E8h
0x18002c8c2  pop     r13
  ... truncated ...
```
