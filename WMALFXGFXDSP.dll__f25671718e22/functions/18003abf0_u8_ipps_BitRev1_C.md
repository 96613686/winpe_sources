# u8_ipps_BitRev1_C

- ea: `0x18003abf0`
- end: `0x18003b19b`
- name: `u8_ipps_BitRev1_C`
- size: `1451`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x18001adb0`
- `0x18001af50`
- `0x18001b150`
- `0x18001b980`
- `0x18001bba0`
- `0x18001bd34`
- `0x18004ef90`
- `0x18004f090`

## callees

- `0x18003abf0`

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
0x18003abf0  push    rbx
0x18003abf1  push    rsi
0x18003abf2  push    rdi
0x18003abf3  push    rbp
0x18003abf4  push    r12
0x18003abf6  push    r13
0x18003abf8  sub     rsp, 0E8h
0x18003abff  movdqa  [rsp+118h+var_58], xmm7
0x18003ac08  movdqa  [rsp+118h+var_48], xmm6
0x18003ac11  mov     rdi, rcx
0x18003ac14  mov     rsi, rdx
0x18003ac17  mov     rdx, r8
0x18003ac1a  mov     r12, rdi
0x18003ac1d  mov     r10, rsi
0x18003ac20  cmp     r10, 8
0x18003ac24  jz      loc_18003B145
0x18003ac2a  mov     rbx, rdx
0x18003ac2d  mov     rax, r10
0x18003ac30  shr     rax, 4
0x18003ac34  lea     rbx, [rbx+rax*4]
0x18003ac38  shl     r10, 1
0x18003ac3b  lea     rax, [r10+r10*2]
0x18003ac3f  mov     r11, r12
0x18003ac42  lea     r13, [r10+r12-20h]
0x18003ac47  test    r12, 0Fh
0x18003ac4e  jnz     loc_18003AECE
0x18003ac54  movsxd  r12, dword ptr [rbx-4]
0x18003ac58  lea     r12, [r11+r12*4]
0x18003ac5c  sub     rbx, 4
0x18003ac60  cmp     r12, r13
0x18003ac63  jl      loc_18003AEBC
0x18003ac69  jz      loc_18003ADFA
0x18003ac6f  movaps  xmm7, xmmword ptr [r13+0]
0x18003ac74  movaps  xmm0, xmmword ptr [r13+10h]
0x18003ac79  movaps  [rsp+118h+var_D8], xmm7
0x18003ac7e  movaps  xmm7, xmmword ptr [r12]
0x18003ac83  movaps  xmm1, xmmword ptr [r12+10h]
0x18003ac89  movaps  [rsp+118h+var_118], xmm7
0x18003ac8d  movaps  xmm7, xmmword ptr [r10+r13]
0x18003ac92  movaps  xmm2, xmmword ptr [r10+r13+10h]
0x18003ac98  movaps  [rsp+118h+var_C8], xmm7
0x18003ac9d  movaps  xmm7, xmmword ptr [r10+r12]
0x18003aca2  movaps  xmm3, xmmword ptr [r10+r12+10h]
0x18003aca8  movaps  [rsp+118h+var_108], xmm7
0x18003acad  movaps  xmm7, xmmword ptr [r13+r10*2+0]
0x18003acb3  movaps  xmm4, xmmword ptr [r13+r10*2+10h]
0x18003acb9  movaps  [rsp+118h+var_B8], xmm7
0x18003acbe  movaps  xmm7, xmmword ptr [r12+r10*2]
0x18003acc3  movaps  xmm5, xmmword ptr [r12+r10*2+10h]
0x18003acc9  movaps  [rsp+118h+var_F8], xmm7
0x18003acce  movaps  xmm7, xmm0
0x18003acd1  movlhps xmm0, xmm4
0x18003acd4  movhlps xmm4, xmm7
0x18003acd7  movaps  [rsp+118h+var_98], xmm0
0x18003acdf  movaps  xmm7, xmm1
0x18003ace2  movlhps xmm1, xmm5
0x18003ace5  movhlps xmm5, xmm7
0x18003ace8  movaps  [rsp+118h+var_78], xmm1
0x18003acf0  movaps  xmm7, xmmword ptr [rax+r13]
0x18003acf5  movaps  xmm0, xmmword ptr [rax+r13+10h]
0x18003acfb  movaps  [rsp+118h+var_A8], xmm7
0x18003ad00  movaps  xmm7, xmmword ptr [rax+r12]
0x18003ad05  movaps  xmm1, xmmword ptr [rax+r12+10h]
0x18003ad0b  movaps  [rsp+118h+var_E8], xmm7
0x18003ad10  movaps  xmm7, xmm2
0x18003ad13  movlhps xmm2, xmm0
0x18003ad16  movhlps xmm0, xmm7
0x18003ad19  movaps  [rsp+118h+var_88], xmm2
0x18003ad21  movaps  xmm7, xmm3
0x18003ad24  movlhps xmm3, xmm1
0x18003ad27  movhlps xmm1, xmm7
0x18003ad2a  movaps  [rsp+118h+var_68], xmm3
0x18003ad32  movaps  xmmword ptr [rax+r12], xmm4
0x18003ad37  movaps  xmmword ptr [rax+r12+10h], xmm0
0x18003ad3d  movaps  xmmword ptr [rax+r13], xmm5
0x18003ad42  movaps  xmmword ptr [rax+r13+10h], xmm1
0x18003ad48  movaps  xmm0, [rsp+118h+var_D8]
0x18003ad4d  movaps  xmm1, [rsp+118h+var_B8]
0x18003ad52  movaps  xmm7, xmm0
0x18003ad55  movlhps xmm0, xmm1
0x18003ad58  movhlps xmm1, xmm7
0x18003ad5b  movaps  xmm4, [rsp+118h+var_C8]
0x18003ad60  movaps  xmm5, [rsp+118h+var_A8]
0x18003ad65  movaps  xmm7, xmm4
0x18003ad68  movlhps xmm4, xmm5
0x18003ad6b  movhlps xmm5, xmm7
0x18003ad6e  movaps  xmmword ptr [r12+r10*2], xmm1
0x18003ad73  movaps  xmmword ptr [r12+r10*2+10h], xmm5
0x18003ad79  movaps  xmm1, [rsp+118h+var_118]
0x18003ad7d  movaps  xmm2, [rsp+118h+var_F8]
0x18003ad82  movaps  xmm7, xmm1
0x18003ad85  movlhps xmm1, xmm2
0x18003ad88  movhlps xmm2, xmm7
0x18003ad8b  movaps  xmm5, [rsp+118h+var_108]
0x18003ad90  movaps  xmm6, [rsp+118h+var_E8]
0x18003ad95  movaps  xmm7, xmm5
0x18003ad98  movlhps xmm5, xmm6
0x18003ad9b  movhlps xmm6, xmm7
0x18003ad9e  movaps  xmmword ptr [r13+r10*2+0], xmm2
0x18003ada4  movaps  xmmword ptr [r13+r10*2+10h], xmm6
0x18003adaa  movaps  xmm2, [rsp+118h+var_98]
0x18003adb2  movaps  xmm3, [rsp+118h+var_88]
0x18003adba  movaps  xmm6, [rsp+118h+var_78]
0x18003adc2  movaps  xmm7, [rsp+118h+var_68]
0x18003adca  movaps  xmmword ptr [r10+r12], xmm2
0x18003adcf  movaps  xmmword ptr [r10+r12+10h], xmm3
0x18003add5  movaps  xmmword ptr [r10+r13], xmm6
0x18003adda  movaps  xmmword ptr [r10+r13+10h], xmm7
0x18003ade0  movaps  xmmword ptr [r12], xmm0
0x18003ade5  movaps  xmmword ptr [r12+10h], xmm4
0x18003adeb  movaps  xmmword ptr [r13+0], xmm1
0x18003adf0  movaps  xmmword ptr [r13+10h], xmm5
0x18003adf5  jmp     loc_18003AEBC
0x18003adfa  movaps  xmm7, xmmword ptr [r12]
0x18003adff  movaps  xmm1, xmmword ptr [r12+10h]
0x18003ae05  movaps  [rsp+118h+var_118], xmm7
0x18003ae09  movaps  xmm7, xmmword ptr [r10+r12]
0x18003ae0e  movaps  xmm3, xmmword ptr [r10+r12+10h]
0x18003ae14  movaps  [rsp+118h+var_108], xmm7
0x18003ae19  movaps  xmm7, xmmword ptr [r12+r10*2]
0x18003ae1e  movaps  xmm5, xmmword ptr [r12+r10*2+10h]
0x18003ae24  movaps  [rsp+118h+var_F8], xmm7
0x18003ae29  movaps  xmm7, xmm1
0x18003ae2c  movlhps xmm1, xmm5
0x18003ae2f  movhlps xmm5, xmm7
0x18003ae32  movaps  [rsp+118h+var_78], xmm1
0x18003ae3a  movaps  xmm7, xmmword ptr [rax+r12]
0x18003ae3f  movaps  xmm1, xmmword ptr [rax+r12+10h]
0x18003ae45  movaps  [rsp+118h+var_E8], xmm7
0x18003ae4a  movaps  xmm7, xmm3
0x18003ae4d  movlhps xmm3, xmm1
0x18003ae50  movhlps xmm1, xmm7
0x18003ae53  movaps  [rsp+118h+var_68], xmm3
0x18003ae5b  movaps  xmmword ptr [rax+r13], xmm5
0x18003ae60  movaps  xmmword ptr [rax+r13+10h], xmm1
0x18003ae66  movaps  xmm1, [rsp+118h+var_118]
0x18003ae6a  movaps  xmm2, [rsp+118h+var_F8]
0x18003ae6f  movaps  xmm7, xmm1
0x18003ae72  movlhps xmm1, xmm2
0x18003ae75  movhlps xmm2, xmm7
0x18003ae78  movaps  xmm5, [rsp+118h+var_108]
0x18003ae7d  movaps  xmm6, [rsp+118h+var_E8]
0x18003ae82  movaps  xmm7, xmm5
0x18003ae85  movlhps xmm5, xmm6
0x18003ae88  movhlps xmm6, xmm7
0x18003ae8b  movaps  xmmword ptr [r13+r10*2+0], xmm2
0x18003ae91  movaps  xmmword ptr [r13+r10*2+10h], xmm6
0x18003ae97  movaps  xmm6, [rsp+118h+var_78]
0x18003ae9f  movaps  xmm7, [rsp+118h+var_68]
0x18003aea7  movaps  xmmword ptr [r10+r13], xmm6
0x18003aeac  movaps  xmmword ptr [r10+r13+10h], xmm7
0x18003aeb2  movaps  xmmword ptr [r13+0], xmm1
0x18003aeb7  movaps  xmmword ptr [r13+10h], xmm5
0x18003aebc  sub     r13, 20h ; ' '
0x18003aec0  cmp     r13, rdi
0x18003aec3  jge     loc_18003AC54
0x18003aec9  jmp     loc_18003B179
0x18003aece  movsxd  r12, dword ptr [rbx-4]
0x18003aed2  lea     r12, [r11+r12*4]
0x18003aed6  sub     rbx, 4
0x18003aeda  cmp     r12, r13
0x18003aedd  jl      loc_18003B136
0x18003aee3  jz      loc_18003B074
0x18003aee9  movups  xmm7, xmmword ptr [r13+0]
0x18003aeee  movups  xmm0, xmmword ptr [r13+10h]
0x18003aef3  movaps  [rsp+118h+var_D8], xmm7
0x18003aef8  movups  xmm7, xmmword ptr [r12]
0x18003aefd  movups  xmm1, xmmword ptr [r12+10h]
0x18003af03  movaps  [rsp+118h+var_118], xmm7
0x18003af07  movups  xmm7, xmmword ptr [r10+r13]
0x18003af0c  movups  xmm2, xmmword ptr [r10+r13+10h]
0x18003af12  movaps  [rsp+118h+var_C8], xmm7
0x18003af17  movups  xmm7, xmmword ptr [r10+r12]
0x18003af1c  movups  xmm3, xmmword ptr [r10+r12+10h]
0x18003af22  movaps  [rsp+118h+var_108], xmm7
0x18003af27  movups  xmm7, xmmword ptr [r13+r10*2+0]
0x18003af2d  movups  xmm4, xmmword ptr [r13+r10*2+10h]
0x18003af33  movaps  [rsp+118h+var_B8], xmm7
0x18003af38  movups  xmm7, xmmword ptr [r12+r10*2]
0x18003af3d  movups  xmm5, xmmword ptr [r12+r10*2+10h]
0x18003af43  movaps  [rsp+118h+var_F8], xmm7
0x18003af48  movaps  xmm7, xmm0
0x18003af4b  movlhps xmm0, xmm4
0x18003af4e  movhlps xmm4, xmm7
0x18003af51  movaps  [rsp+118h+var_98], xmm0
0x18003af59  movaps  xmm7, xmm1
0x18003af5c  movlhps xmm1, xmm5
0x18003af5f  movhlps xmm5, xmm7
0x18003af62  movaps  [rsp+118h+var_78], xmm1
0x18003af6a  movups  xmm7, xmmword ptr [rax+r13]
0x18003af6f  movups  xmm0, xmmword ptr [rax+r13+10h]
0x18003af75  movaps  [rsp+118h+var_A8], xmm7
0x18003af7a  movups  xmm7, xmmword ptr [rax+r12]
0x18003af7f  movups  xmm1, xmmword ptr [rax+r12+10h]
0x18003af85  movaps  [rsp+118h+var_E8], xmm7
0x18003af8a  movaps  xmm7, xmm2
0x18003af8d  movlhps xmm2, xmm0
0x18003af90  movhlps xmm0, xmm7
0x18003af93  movaps  [rsp+118h+var_88], xmm2
0x18003af9b  movaps  xmm7, xmm3
0x18003af9e  movlhps xmm3, xmm1
0x18003afa1  movhlps xmm1, xmm7
0x18003afa4  movaps  [rsp+118h+var_68], xmm3
0x18003afac  movups  xmmword ptr [rax+r12], xmm4
0x18003afb1  movups  xmmword ptr [rax+r12+10h], xmm0
0x18003afb7  movups  xmmword ptr [rax+r13], xmm5
0x18003afbc  movups  xmmword ptr [rax+r13+10h], xmm1
0x18003afc2  movaps  xmm0, [rsp+118h+var_D8]
0x18003afc7  movaps  xmm1, [rsp+118h+var_B8]
0x18003afcc  movaps  xmm7, xmm0
0x18003afcf  movlhps xmm0, xmm1
0x18003afd2  movhlps xmm1, xmm7
0x18003afd5  movaps  xmm4, [rsp+118h+var_C8]
0x18003afda  movaps  xmm5, [rsp+118h+var_A8]
0x18003afdf  movaps  xmm7, xmm4
0x18003afe2  movlhps xmm4, xmm5
0x18003afe5  movhlps xmm5, xmm7
0x18003afe8  movups  xmmword ptr [r12+r10*2], xmm1
0x18003afed  movups  xmmword ptr [r12+r10*2+10h], xmm5
0x18003aff3  movaps  xmm1, [rsp+118h+var_118]
0x18003aff7  movaps  xmm2, [rsp+118h+var_F8]
0x18003affc  movaps  xmm7, xmm1
0x18003afff  movlhps xmm1, xmm2
0x18003b002  movhlps xmm2, xmm7
0x18003b005  movaps  xmm5, [rsp+118h+var_108]
0x18003b00a  movaps  xmm6, [rsp+118h+var_E8]
0x18003b00f  movaps  xmm7, xmm5
0x18003b012  movlhps xmm5, xmm6
0x18003b015  movhlps xmm6, xmm7
0x18003b018  movups  xmmword ptr [r13+r10*2+0], xmm2
0x18003b01e  movups  xmmword ptr [r13+r10*2+10h], xmm6
0x18003b024  movaps  xmm2, [rsp+118h+var_98]
0x18003b02c  movaps  xmm3, [rsp+118h+var_88]
0x18003b034  movaps  xmm6, [rsp+118h+var_78]
0x18003b03c  movaps  xmm7, [rsp+118h+var_68]
0x18003b044  movups  xmmword ptr [r10+r12], xmm2
0x18003b049  movups  xmmword ptr [r10+r12+10h], xmm3
0x18003b04f  movups  xmmword ptr [r10+r13], xmm6
0x18003b054  movups  xmmword ptr [r10+r13+10h], xmm7
0x18003b05a  movups  xmmword ptr [r12], xmm0
0x18003b05f  movups  xmmword ptr [r12+10h], xmm4
0x18003b065  movups  xmmword ptr [r13+0], xmm1
0x18003b06a  movups  xmmword ptr [r13+10h], xmm5
0x18003b06f  jmp     loc_18003B136
0x18003b074  movups  xmm7, xmmword ptr [r12]
0x18003b079  movups  xmm1, xmmword ptr [r12+10h]
0x18003b07f  movaps  [rsp+118h+var_118], xmm7
0x18003b083  movups  xmm7, xmmword ptr [r10+r12]
0x18003b088  movups  xmm3, xmmword ptr [r10+r12+10h]
0x18003b08e  movaps  [rsp+118h+var_108], xmm7
0x18003b093  movups  xmm7, xmmword ptr [r12+r10*2]
0x18003b098  movups  xmm5, xmmword ptr [r12+r10*2+10h]
0x18003b09e  movaps  [rsp+118h+var_F8], xmm7
0x18003b0a3  movaps  xmm7, xmm1
0x18003b0a6  movlhps xmm1, xmm5
0x18003b0a9  movhlps xmm5, xmm7
0x18003b0ac  movaps  [rsp+118h+var_78], xmm1
0x18003b0b4  movups  xmm7, xmmword ptr [rax+r12]
0x18003b0b9  movups  xmm1, xmmword ptr [rax+r12+10h]
0x18003b0bf  movaps  [rsp+118h+var_E8], xmm7
0x18003b0c4  movaps  xmm7, xmm3
0x18003b0c7  movlhps xmm3, xmm1
0x18003b0ca  movhlps xmm1, xmm7
0x18003b0cd  movaps  [rsp+118h+var_68], xmm3
0x18003b0d5  movups  xmmword ptr [rax+r13], xmm5
0x18003b0da  movups  xmmword ptr [rax+r13+10h], xmm1
0x18003b0e0  movaps  xmm1, [rsp+118h+var_118]
0x18003b0e4  movaps  xmm2, [rsp+118h+var_F8]
0x18003b0e9  movaps  xmm7, xmm1
0x18003b0ec  movlhps xmm1, xmm2
0x18003b0ef  movhlps xmm2, xmm7
0x18003b0f2  movaps  xmm5, [rsp+118h+var_108]
0x18003b0f7  movaps  xmm6, [rsp+118h+var_E8]
0x18003b0fc  movaps  xmm7, xmm5
0x18003b0ff  movlhps xmm5, xmm6
0x18003b102  movhlps xmm6, xmm7
0x18003b105  movups  xmmword ptr [r13+r10*2+0], xmm2
0x18003b10b  movups  xmmword ptr [r13+r10*2+10h], xmm6
0x18003b111  movaps  xmm6, [rsp+118h+var_78]
0x18003b119  movaps  xmm7, [rsp+118h+var_68]
0x18003b121  movups  xmmword ptr [r10+r13], xmm6
0x18003b126  movups  xmmword ptr [r10+r13+10h], xmm7
0x18003b12c  movups  xmmword ptr [r13+0], xmm1
0x18003b131  movups  xmmword ptr [r13+10h], xmm5
0x18003b136  sub     r13, 20h ; ' '
0x18003b13a  cmp     r13, rdi
0x18003b13d  jge     loc_18003AECE
0x18003b143  jmp     short loc_18003B179
0x18003b145  movsd   xmm0, qword ptr [r12+8]
0x18003b14c  movsd   xmm1, qword ptr [r12+18h]
0x18003b153  movsd   xmm2, qword ptr [r12+20h]
0x18003b15a  movsd   xmm3, qword ptr [r12+30h]
0x18003b161  movlps  qword ptr [r12+8], xmm2
0x18003b167  movlps  qword ptr [r12+18h], xmm3
0x18003b16d  movlps  qword ptr [r12+20h], xmm0
0x18003b173  movlps  qword ptr [r12+30h], xmm1
0x18003b179  movdqa  xmm7, [rsp+118h+var_58]
0x18003b182  movdqa  xmm6, [rsp+118h+var_48]
0x18003b18b  add     rsp, 0E8h
0x18003b192  pop     r13
  ... truncated ...
```
