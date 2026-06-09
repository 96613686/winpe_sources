# m7_ipps_BitRev1_C

- ea: `0x1800259e0`
- end: `0x180025f8b`
- name: `m7_ipps_BitRev1_C`
- size: `1451`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x180019b10`
- `0x180019cb0`
- `0x180019eb0`
- `0x18001a6e0`
- `0x18001a900`
- `0x18001aa94`
- `0x1800387d8`
- `0x1800388c4`

## callees

- `0x1800259e0`

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
0x1800259e0  push    rbx
0x1800259e1  push    rsi
0x1800259e2  push    rdi
0x1800259e3  push    rbp
0x1800259e4  push    r12
0x1800259e6  push    r13
0x1800259e8  sub     rsp, 0E8h
0x1800259ef  movdqa  [rsp+118h+var_58], xmm7
0x1800259f8  movdqa  [rsp+118h+var_48], xmm6
0x180025a01  mov     rdi, rcx
0x180025a04  mov     rsi, rdx
0x180025a07  mov     rdx, r8
0x180025a0a  mov     r12, rdi
0x180025a0d  mov     r10, rsi
0x180025a10  cmp     r10, 8
0x180025a14  jz      loc_180025F35
0x180025a1a  mov     rbx, rdx
0x180025a1d  mov     rax, r10
0x180025a20  shr     rax, 4
0x180025a24  lea     rbx, [rbx+rax*4]
0x180025a28  shl     r10, 1
0x180025a2b  lea     rax, [r10+r10*2]
0x180025a2f  mov     r11, r12
0x180025a32  lea     r13, [r10+r12-20h]
0x180025a37  test    r12, 0Fh
0x180025a3e  jnz     loc_180025CBE
0x180025a44  movsxd  r12, dword ptr [rbx-4]
0x180025a48  lea     r12, [r11+r12*4]
0x180025a4c  sub     rbx, 4
0x180025a50  cmp     r12, r13
0x180025a53  jl      loc_180025CAC
0x180025a59  jz      loc_180025BEA
0x180025a5f  movaps  xmm7, xmmword ptr [r13+0]
0x180025a64  movaps  xmm0, xmmword ptr [r13+10h]
0x180025a69  movaps  [rsp+118h+var_D8], xmm7
0x180025a6e  movaps  xmm7, xmmword ptr [r12]
0x180025a73  movaps  xmm1, xmmword ptr [r12+10h]
0x180025a79  movaps  [rsp+118h+var_118], xmm7
0x180025a7d  movaps  xmm7, xmmword ptr [r10+r13]
0x180025a82  movaps  xmm2, xmmword ptr [r10+r13+10h]
0x180025a88  movaps  [rsp+118h+var_C8], xmm7
0x180025a8d  movaps  xmm7, xmmword ptr [r10+r12]
0x180025a92  movaps  xmm3, xmmword ptr [r10+r12+10h]
0x180025a98  movaps  [rsp+118h+var_108], xmm7
0x180025a9d  movaps  xmm7, xmmword ptr [r13+r10*2+0]
0x180025aa3  movaps  xmm4, xmmword ptr [r13+r10*2+10h]
0x180025aa9  movaps  [rsp+118h+var_B8], xmm7
0x180025aae  movaps  xmm7, xmmword ptr [r12+r10*2]
0x180025ab3  movaps  xmm5, xmmword ptr [r12+r10*2+10h]
0x180025ab9  movaps  [rsp+118h+var_F8], xmm7
0x180025abe  movaps  xmm7, xmm0
0x180025ac1  movlhps xmm0, xmm4
0x180025ac4  movhlps xmm4, xmm7
0x180025ac7  movaps  [rsp+118h+var_98], xmm0
0x180025acf  movaps  xmm7, xmm1
0x180025ad2  movlhps xmm1, xmm5
0x180025ad5  movhlps xmm5, xmm7
0x180025ad8  movaps  [rsp+118h+var_78], xmm1
0x180025ae0  movaps  xmm7, xmmword ptr [rax+r13]
0x180025ae5  movaps  xmm0, xmmword ptr [rax+r13+10h]
0x180025aeb  movaps  [rsp+118h+var_A8], xmm7
0x180025af0  movaps  xmm7, xmmword ptr [rax+r12]
0x180025af5  movaps  xmm1, xmmword ptr [rax+r12+10h]
0x180025afb  movaps  [rsp+118h+var_E8], xmm7
0x180025b00  movaps  xmm7, xmm2
0x180025b03  movlhps xmm2, xmm0
0x180025b06  movhlps xmm0, xmm7
0x180025b09  movaps  [rsp+118h+var_88], xmm2
0x180025b11  movaps  xmm7, xmm3
0x180025b14  movlhps xmm3, xmm1
0x180025b17  movhlps xmm1, xmm7
0x180025b1a  movaps  [rsp+118h+var_68], xmm3
0x180025b22  movaps  xmmword ptr [rax+r12], xmm4
0x180025b27  movaps  xmmword ptr [rax+r12+10h], xmm0
0x180025b2d  movaps  xmmword ptr [rax+r13], xmm5
0x180025b32  movaps  xmmword ptr [rax+r13+10h], xmm1
0x180025b38  movaps  xmm0, [rsp+118h+var_D8]
0x180025b3d  movaps  xmm1, [rsp+118h+var_B8]
0x180025b42  movaps  xmm7, xmm0
0x180025b45  movlhps xmm0, xmm1
0x180025b48  movhlps xmm1, xmm7
0x180025b4b  movaps  xmm4, [rsp+118h+var_C8]
0x180025b50  movaps  xmm5, [rsp+118h+var_A8]
0x180025b55  movaps  xmm7, xmm4
0x180025b58  movlhps xmm4, xmm5
0x180025b5b  movhlps xmm5, xmm7
0x180025b5e  movaps  xmmword ptr [r12+r10*2], xmm1
0x180025b63  movaps  xmmword ptr [r12+r10*2+10h], xmm5
0x180025b69  movaps  xmm1, [rsp+118h+var_118]
0x180025b6d  movaps  xmm2, [rsp+118h+var_F8]
0x180025b72  movaps  xmm7, xmm1
0x180025b75  movlhps xmm1, xmm2
0x180025b78  movhlps xmm2, xmm7
0x180025b7b  movaps  xmm5, [rsp+118h+var_108]
0x180025b80  movaps  xmm6, [rsp+118h+var_E8]
0x180025b85  movaps  xmm7, xmm5
0x180025b88  movlhps xmm5, xmm6
0x180025b8b  movhlps xmm6, xmm7
0x180025b8e  movaps  xmmword ptr [r13+r10*2+0], xmm2
0x180025b94  movaps  xmmword ptr [r13+r10*2+10h], xmm6
0x180025b9a  movaps  xmm2, [rsp+118h+var_98]
0x180025ba2  movaps  xmm3, [rsp+118h+var_88]
0x180025baa  movaps  xmm6, [rsp+118h+var_78]
0x180025bb2  movaps  xmm7, [rsp+118h+var_68]
0x180025bba  movaps  xmmword ptr [r10+r12], xmm2
0x180025bbf  movaps  xmmword ptr [r10+r12+10h], xmm3
0x180025bc5  movaps  xmmword ptr [r10+r13], xmm6
0x180025bca  movaps  xmmword ptr [r10+r13+10h], xmm7
0x180025bd0  movaps  xmmword ptr [r12], xmm0
0x180025bd5  movaps  xmmword ptr [r12+10h], xmm4
0x180025bdb  movaps  xmmword ptr [r13+0], xmm1
0x180025be0  movaps  xmmword ptr [r13+10h], xmm5
0x180025be5  jmp     loc_180025CAC
0x180025bea  movaps  xmm7, xmmword ptr [r12]
0x180025bef  movaps  xmm1, xmmword ptr [r12+10h]
0x180025bf5  movaps  [rsp+118h+var_118], xmm7
0x180025bf9  movaps  xmm7, xmmword ptr [r10+r12]
0x180025bfe  movaps  xmm3, xmmword ptr [r10+r12+10h]
0x180025c04  movaps  [rsp+118h+var_108], xmm7
0x180025c09  movaps  xmm7, xmmword ptr [r12+r10*2]
0x180025c0e  movaps  xmm5, xmmword ptr [r12+r10*2+10h]
0x180025c14  movaps  [rsp+118h+var_F8], xmm7
0x180025c19  movaps  xmm7, xmm1
0x180025c1c  movlhps xmm1, xmm5
0x180025c1f  movhlps xmm5, xmm7
0x180025c22  movaps  [rsp+118h+var_78], xmm1
0x180025c2a  movaps  xmm7, xmmword ptr [rax+r12]
0x180025c2f  movaps  xmm1, xmmword ptr [rax+r12+10h]
0x180025c35  movaps  [rsp+118h+var_E8], xmm7
0x180025c3a  movaps  xmm7, xmm3
0x180025c3d  movlhps xmm3, xmm1
0x180025c40  movhlps xmm1, xmm7
0x180025c43  movaps  [rsp+118h+var_68], xmm3
0x180025c4b  movaps  xmmword ptr [rax+r13], xmm5
0x180025c50  movaps  xmmword ptr [rax+r13+10h], xmm1
0x180025c56  movaps  xmm1, [rsp+118h+var_118]
0x180025c5a  movaps  xmm2, [rsp+118h+var_F8]
0x180025c5f  movaps  xmm7, xmm1
0x180025c62  movlhps xmm1, xmm2
0x180025c65  movhlps xmm2, xmm7
0x180025c68  movaps  xmm5, [rsp+118h+var_108]
0x180025c6d  movaps  xmm6, [rsp+118h+var_E8]
0x180025c72  movaps  xmm7, xmm5
0x180025c75  movlhps xmm5, xmm6
0x180025c78  movhlps xmm6, xmm7
0x180025c7b  movaps  xmmword ptr [r13+r10*2+0], xmm2
0x180025c81  movaps  xmmword ptr [r13+r10*2+10h], xmm6
0x180025c87  movaps  xmm6, [rsp+118h+var_78]
0x180025c8f  movaps  xmm7, [rsp+118h+var_68]
0x180025c97  movaps  xmmword ptr [r10+r13], xmm6
0x180025c9c  movaps  xmmword ptr [r10+r13+10h], xmm7
0x180025ca2  movaps  xmmword ptr [r13+0], xmm1
0x180025ca7  movaps  xmmword ptr [r13+10h], xmm5
0x180025cac  sub     r13, 20h ; ' '
0x180025cb0  cmp     r13, rdi
0x180025cb3  jge     loc_180025A44
0x180025cb9  jmp     loc_180025F69
0x180025cbe  movsxd  r12, dword ptr [rbx-4]
0x180025cc2  lea     r12, [r11+r12*4]
0x180025cc6  sub     rbx, 4
0x180025cca  cmp     r12, r13
0x180025ccd  jl      loc_180025F26
0x180025cd3  jz      loc_180025E64
0x180025cd9  movups  xmm7, xmmword ptr [r13+0]
0x180025cde  movups  xmm0, xmmword ptr [r13+10h]
0x180025ce3  movaps  [rsp+118h+var_D8], xmm7
0x180025ce8  movups  xmm7, xmmword ptr [r12]
0x180025ced  movups  xmm1, xmmword ptr [r12+10h]
0x180025cf3  movaps  [rsp+118h+var_118], xmm7
0x180025cf7  movups  xmm7, xmmword ptr [r10+r13]
0x180025cfc  movups  xmm2, xmmword ptr [r10+r13+10h]
0x180025d02  movaps  [rsp+118h+var_C8], xmm7
0x180025d07  movups  xmm7, xmmword ptr [r10+r12]
0x180025d0c  movups  xmm3, xmmword ptr [r10+r12+10h]
0x180025d12  movaps  [rsp+118h+var_108], xmm7
0x180025d17  movups  xmm7, xmmword ptr [r13+r10*2+0]
0x180025d1d  movups  xmm4, xmmword ptr [r13+r10*2+10h]
0x180025d23  movaps  [rsp+118h+var_B8], xmm7
0x180025d28  movups  xmm7, xmmword ptr [r12+r10*2]
0x180025d2d  movups  xmm5, xmmword ptr [r12+r10*2+10h]
0x180025d33  movaps  [rsp+118h+var_F8], xmm7
0x180025d38  movaps  xmm7, xmm0
0x180025d3b  movlhps xmm0, xmm4
0x180025d3e  movhlps xmm4, xmm7
0x180025d41  movaps  [rsp+118h+var_98], xmm0
0x180025d49  movaps  xmm7, xmm1
0x180025d4c  movlhps xmm1, xmm5
0x180025d4f  movhlps xmm5, xmm7
0x180025d52  movaps  [rsp+118h+var_78], xmm1
0x180025d5a  movups  xmm7, xmmword ptr [rax+r13]
0x180025d5f  movups  xmm0, xmmword ptr [rax+r13+10h]
0x180025d65  movaps  [rsp+118h+var_A8], xmm7
0x180025d6a  movups  xmm7, xmmword ptr [rax+r12]
0x180025d6f  movups  xmm1, xmmword ptr [rax+r12+10h]
0x180025d75  movaps  [rsp+118h+var_E8], xmm7
0x180025d7a  movaps  xmm7, xmm2
0x180025d7d  movlhps xmm2, xmm0
0x180025d80  movhlps xmm0, xmm7
0x180025d83  movaps  [rsp+118h+var_88], xmm2
0x180025d8b  movaps  xmm7, xmm3
0x180025d8e  movlhps xmm3, xmm1
0x180025d91  movhlps xmm1, xmm7
0x180025d94  movaps  [rsp+118h+var_68], xmm3
0x180025d9c  movups  xmmword ptr [rax+r12], xmm4
0x180025da1  movups  xmmword ptr [rax+r12+10h], xmm0
0x180025da7  movups  xmmword ptr [rax+r13], xmm5
0x180025dac  movups  xmmword ptr [rax+r13+10h], xmm1
0x180025db2  movaps  xmm0, [rsp+118h+var_D8]
0x180025db7  movaps  xmm1, [rsp+118h+var_B8]
0x180025dbc  movaps  xmm7, xmm0
0x180025dbf  movlhps xmm0, xmm1
0x180025dc2  movhlps xmm1, xmm7
0x180025dc5  movaps  xmm4, [rsp+118h+var_C8]
0x180025dca  movaps  xmm5, [rsp+118h+var_A8]
0x180025dcf  movaps  xmm7, xmm4
0x180025dd2  movlhps xmm4, xmm5
0x180025dd5  movhlps xmm5, xmm7
0x180025dd8  movups  xmmword ptr [r12+r10*2], xmm1
0x180025ddd  movups  xmmword ptr [r12+r10*2+10h], xmm5
0x180025de3  movaps  xmm1, [rsp+118h+var_118]
0x180025de7  movaps  xmm2, [rsp+118h+var_F8]
0x180025dec  movaps  xmm7, xmm1
0x180025def  movlhps xmm1, xmm2
0x180025df2  movhlps xmm2, xmm7
0x180025df5  movaps  xmm5, [rsp+118h+var_108]
0x180025dfa  movaps  xmm6, [rsp+118h+var_E8]
0x180025dff  movaps  xmm7, xmm5
0x180025e02  movlhps xmm5, xmm6
0x180025e05  movhlps xmm6, xmm7
0x180025e08  movups  xmmword ptr [r13+r10*2+0], xmm2
0x180025e0e  movups  xmmword ptr [r13+r10*2+10h], xmm6
0x180025e14  movaps  xmm2, [rsp+118h+var_98]
0x180025e1c  movaps  xmm3, [rsp+118h+var_88]
0x180025e24  movaps  xmm6, [rsp+118h+var_78]
0x180025e2c  movaps  xmm7, [rsp+118h+var_68]
0x180025e34  movups  xmmword ptr [r10+r12], xmm2
0x180025e39  movups  xmmword ptr [r10+r12+10h], xmm3
0x180025e3f  movups  xmmword ptr [r10+r13], xmm6
0x180025e44  movups  xmmword ptr [r10+r13+10h], xmm7
0x180025e4a  movups  xmmword ptr [r12], xmm0
0x180025e4f  movups  xmmword ptr [r12+10h], xmm4
0x180025e55  movups  xmmword ptr [r13+0], xmm1
0x180025e5a  movups  xmmword ptr [r13+10h], xmm5
0x180025e5f  jmp     loc_180025F26
0x180025e64  movups  xmm7, xmmword ptr [r12]
0x180025e69  movups  xmm1, xmmword ptr [r12+10h]
0x180025e6f  movaps  [rsp+118h+var_118], xmm7
0x180025e73  movups  xmm7, xmmword ptr [r10+r12]
0x180025e78  movups  xmm3, xmmword ptr [r10+r12+10h]
0x180025e7e  movaps  [rsp+118h+var_108], xmm7
0x180025e83  movups  xmm7, xmmword ptr [r12+r10*2]
0x180025e88  movups  xmm5, xmmword ptr [r12+r10*2+10h]
0x180025e8e  movaps  [rsp+118h+var_F8], xmm7
0x180025e93  movaps  xmm7, xmm1
0x180025e96  movlhps xmm1, xmm5
0x180025e99  movhlps xmm5, xmm7
0x180025e9c  movaps  [rsp+118h+var_78], xmm1
0x180025ea4  movups  xmm7, xmmword ptr [rax+r12]
0x180025ea9  movups  xmm1, xmmword ptr [rax+r12+10h]
0x180025eaf  movaps  [rsp+118h+var_E8], xmm7
0x180025eb4  movaps  xmm7, xmm3
0x180025eb7  movlhps xmm3, xmm1
0x180025eba  movhlps xmm1, xmm7
0x180025ebd  movaps  [rsp+118h+var_68], xmm3
0x180025ec5  movups  xmmword ptr [rax+r13], xmm5
0x180025eca  movups  xmmword ptr [rax+r13+10h], xmm1
0x180025ed0  movaps  xmm1, [rsp+118h+var_118]
0x180025ed4  movaps  xmm2, [rsp+118h+var_F8]
0x180025ed9  movaps  xmm7, xmm1
0x180025edc  movlhps xmm1, xmm2
0x180025edf  movhlps xmm2, xmm7
0x180025ee2  movaps  xmm5, [rsp+118h+var_108]
0x180025ee7  movaps  xmm6, [rsp+118h+var_E8]
0x180025eec  movaps  xmm7, xmm5
0x180025eef  movlhps xmm5, xmm6
0x180025ef2  movhlps xmm6, xmm7
0x180025ef5  movups  xmmword ptr [r13+r10*2+0], xmm2
0x180025efb  movups  xmmword ptr [r13+r10*2+10h], xmm6
0x180025f01  movaps  xmm6, [rsp+118h+var_78]
0x180025f09  movaps  xmm7, [rsp+118h+var_68]
0x180025f11  movups  xmmword ptr [r10+r13], xmm6
0x180025f16  movups  xmmword ptr [r10+r13+10h], xmm7
0x180025f1c  movups  xmmword ptr [r13+0], xmm1
0x180025f21  movups  xmmword ptr [r13+10h], xmm5
0x180025f26  sub     r13, 20h ; ' '
0x180025f2a  cmp     r13, rdi
0x180025f2d  jge     loc_180025CBE
0x180025f33  jmp     short loc_180025F69
0x180025f35  movsd   xmm0, qword ptr [r12+8]
0x180025f3c  movsd   xmm1, qword ptr [r12+18h]
0x180025f43  movsd   xmm2, qword ptr [r12+20h]
0x180025f4a  movsd   xmm3, qword ptr [r12+30h]
0x180025f51  movlps  qword ptr [r12+8], xmm2
0x180025f57  movlps  qword ptr [r12+18h], xmm3
0x180025f5d  movlps  qword ptr [r12+20h], xmm0
0x180025f63  movlps  qword ptr [r12+30h], xmm1
0x180025f69  movdqa  xmm7, [rsp+118h+var_58]
0x180025f72  movdqa  xmm6, [rsp+118h+var_48]
0x180025f7b  add     rsp, 0E8h
0x180025f82  pop     r13
  ... truncated ...
```
