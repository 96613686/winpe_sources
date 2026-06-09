# CDistanceFromAtom::UpdateWithLineSegmentAndArc(CLineSegment<CMglPoint<double>> const &,CCircularArc2D const &,bool)

- ea: `0x100434110`
- end: `0x100434492`
- name: `?UpdateWithLineSegmentAndArc@CDistanceFromAtom@@IEAAXAEBV?$CLineSegment@V?$CMglPoint@N@@@@AEBVCCircularArc2D@@_N@Z`
- size: `898`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x100435520`
- `0x100435710`

## callees

- `0x100434110`
- `0x10044bf00`
- `0x10044c120`

## pseudocode

```c
__int64 __fastcall CDistanceFromAtom::UpdateWithLineSegmentAndArc(__int64 a1, double *a2, __int64 a3, char a4)
{
  __int64 result; // rax
  double v9; // xmm2_8
  double v10; // xmm1_8
  __int128 v11; // xmm0
  __int128 v12; // xmm1
  double v13; // xmm1_8
  __int128 v14; // xmm0
  __int128 v15; // xmm1
  double v16; // xmm5_8
  double v17; // xmm2_8
  double v18; // xmm3_8
  double v19; // xmm1_8
  double v20; // xmm8_8
  double v21; // xmm9_8
  double v22; // xmm7_8
  char v23; // r15
  double v24; // xmm4_8
  __int64 v25; // rax
  double v26; // xmm7_8
  double v27; // xmm0_8
  double v28; // xmm3_8
  double v29; // xmm1_8
  double v30; // xmm1_8
  __int128 v31; // xmm1
  double v32; // xmm2_8
  __int128 v33; // xmm0
  __int64 v34; // rcx
  double v35; // xmm2_8
  double v36; // xmm1_8
  double v37; // xmm3_8
  double v38; // xmm1_8
  __int128 v39; // xmm0
  double v40; // xmm2_8
  __int128 v41; // xmm1
  __int128 v42; // xmm0
  double v43; // xmm0_8
  double v44; // xmm1_8
  __int128 v45; // xmm0
  double v46; // xmm0_8
  double v47; // xmm1_8
  __int128 v48; // [rsp+20h] [rbp-60h] BYREF
  __int128 v49; // [rsp+30h] [rbp-50h] BYREF

  if ( (unsigned __int8)CCircularArc2D::GetPointNearestToLineSegment(a3, a2, &v49, &v48) )
  {
    result = *(_QWORD *)(a1 + 24);
    v9 = *(double *)result;
    if ( a4 )
    {
      v10 = (*((double *)&v49 + 1) - *((double *)&v48 + 1)) * (*((double *)&v49 + 1) - *((double *)&v48 + 1))
          + (*(double *)&v49 - *(double *)&v48) * (*(double *)&v49 - *(double *)&v48);
      if ( v9 > v10 )
      {
        v11 = v48;
        *(double *)result = v10;
        v12 = v49;
        *(_OWORD *)(result + 8) = v11;
        *(_OWORD *)(result + 24) = v12;
      }
    }
    else
    {
      v13 = (*((double *)&v48 + 1) - *((double *)&v49 + 1)) * (*((double *)&v48 + 1) - *((double *)&v49 + 1))
          + (*(double *)&v48 - *(double *)&v49) * (*(double *)&v48 - *(double *)&v49);
      if ( v9 > v13 )
      {
        v14 = v49;
        *(double *)result = v13;
        v15 = v48;
        *(_OWORD *)(result + 8) = v14;
        *(_OWORD *)(result + 24) = v15;
      }
    }
  }
  else
  {
    v16 = *(double *)(a3 + 104);
    v17 = *(double *)(a3 + 112);
    v18 = *a2 - v16;
    v19 = a2[1] - v17;
    v20 = a2[2] - v16;
    v21 = a2[3] - v17;
    *(_QWORD *)&v22 = COERCE_UNSIGNED_INT64((v21 - v19) * v19 + (v20 - v18) * v18) ^ _xmm;
    if ( v22 >= 0.0 )
    {
      v24 = (v21 - v19) * (v21 - v19) + (v20 - v18) * (v20 - v18);
      if ( v22 <= v24 )
      {
        v23 = 1;
        v25 = *(_QWORD *)(a1 + 24);
        v26 = v22 / v24;
        v27 = *(double *)v25;
        v28 = v18 * (1.0 - v26) + v16 + v20 * v26;
        v29 = v19 * (1.0 - v26) + v17 + v21 * v26;
        *(double *)&v49 = v28;
        *((double *)&v49 + 1) = v29;
        if ( a4 )
        {
          v30 = (v29 - v17) * (v29 - v17) + (v28 - v16) * (v28 - v16);
          if ( v27 > v30 )
          {
            *(double *)v25 = v30;
            v31 = v49;
            *(_OWORD *)(v25 + 8) = *(_OWORD *)(a3 + 104);
            *(_OWORD *)(v25 + 24) = v31;
          }
        }
        else
        {
          v32 = (v17 - v29) * (v17 - v29) + (v16 - v28) * (v16 - v28);
          if ( v27 > v32 )
          {
            v33 = v49;
            *(double *)v25 = v32;
            *(_OWORD *)(v25 + 8) = v33;
            *(_OWORD *)(v25 + 24) = *(_OWORD *)(a3 + 104);
          }
        }
      }
      else
      {
        v23 = 0;
      }
    }
    else
    {
      v23 = 0;
    }
    result = CCircularArc2D::GetPointNearestToPoint(a3, a2 + 2, &v48);
    if ( (_BYTE)result )
    {
      v34 = *(_QWORD *)(a1 + 24);
      v35 = a2[2];
      v36 = a2[3];
      v37 = *(double *)v34;
      if ( a4 )
      {
        v38 = (v36 - *((double *)&v48 + 1)) * (v36 - *((double *)&v48 + 1))
            + (v35 - *(double *)&v48) * (v35 - *(double *)&v48);
        if ( v37 > v38 )
        {
          v39 = v48;
          *(double *)v34 = v38;
          *(_OWORD *)(v34 + 8) = v39;
          *(_OWORD *)(v34 + 24) = *((_OWORD *)a2 + 1);
        }
      }
      else
      {
        v40 = (*((double *)&v48 + 1) - v36) * (*((double *)&v48 + 1) - v36)
            + (*(double *)&v48 - v35) * (*(double *)&v48 - v35);
        if ( v37 > v40 )
        {
          v41 = v48;
          *(double *)v34 = v40;
          v42 = *((_OWORD *)a2 + 1);
          *(_OWORD *)(v34 + 24) = v41;
          *(_OWORD *)(v34 + 8) = v42;
        }
      }
    }
    if ( !v23 && !(_BYTE)result )
    {
      result = *(_QWORD *)(a1 + 24);
      if ( a4 )
      {
        v43 = a2[2] - *(double *)(a3 + 104);
        v44 = (a2[3] - *(double *)(a3 + 112)) * (a2[3] - *(double *)(a3 + 112)) + v43 * v43;
        if ( *(double *)result <= v44 )
          return result;
        *(double *)result = v44;
        *(_OWORD *)(result + 8) = *(_OWORD *)(a3 + 104);
        v45 = *((_OWORD *)a2 + 1);
      }
      else
      {
        v46 = *(double *)(a3 + 104) - a2[2];
        v47 = (*(double *)(a3 + 112) - a2[3]) * (*(double *)(a3 + 112) - a2[3]) + v46 * v46;
        if ( *(double *)result <= v47 )
          return result;
        *(double *)result = v47;
        *(_OWORD *)(result + 8) = *((_OWORD *)a2 + 1);
        v45 = *(_OWORD *)(a3 + 104);
      }
      *(_OWORD *)(result + 24) = v45;
    }
  }
  return result;
}

```

## disassembly

```asm
0x100434110  mov     [rsp-18h+arg_8], rbx
0x100434115  mov     [rsp-18h+arg_10], rsi
0x10043411a  push    rbp
0x10043411b  push    rdi
0x10043411c  push    r14
0x10043411e  mov     rbp, rsp
0x100434121  sub     rsp, 80h
0x100434128  mov     rdi, r8
0x10043412b  movzx   esi, r9b
0x10043412f  mov     r14, rcx
0x100434132  lea     r9, [rbp+var_60]
0x100434136  mov     rcx, rdi
0x100434139  lea     r8, [rbp+var_50]
0x10043413d  mov     rbx, rdx
0x100434140  call    ?GetPointNearestToLineSegment@CCircularArc2D@@QEBA_NAEBV?$CLineSegment@V?$CMglPoint@N@@@@AEAV?$CMglPoint@N@@1@Z; CCircularArc2D::GetPointNearestToLineSegment(CLineSegment<CMglPoint<double>> const &,CMglPoint<double> &,CMglPoint<double> &)
0x100434145  test    al, al
0x100434147  jz      loc_1004341E0
0x10043414d  mov     rax, [r14+18h]
0x100434151  movsd   xmm2, qword ptr [rax]
0x100434155  test    sil, sil
0x100434158  jz      short loc_10043419D
0x10043415a  movsd   xmm0, qword ptr [rbp+var_50]
0x10043415f  movsd   xmm1, qword ptr [rbp+var_50+8]
0x100434164  subsd   xmm1, qword ptr [rbp+var_60+8]
0x100434169  subsd   xmm0, qword ptr [rbp+var_60]
0x10043416e  mulsd   xmm1, xmm1
0x100434172  mulsd   xmm0, xmm0
0x100434176  addsd   xmm1, xmm0
0x10043417a  comisd  xmm2, xmm1
0x10043417e  jbe     loc_10043447A
0x100434184  movups  xmm0, [rbp+var_60]
0x100434188  movsd   qword ptr [rax], xmm1
0x10043418c  movups  xmm1, [rbp+var_50]
0x100434190  movups  xmmword ptr [rax+8], xmm0
0x100434194  movups  xmmword ptr [rax+18h], xmm1
0x100434198  jmp     loc_10043447A
0x10043419d  movsd   xmm0, qword ptr [rbp+var_60]
0x1004341a2  movsd   xmm1, qword ptr [rbp+var_60+8]
0x1004341a7  subsd   xmm1, qword ptr [rbp+var_50+8]
0x1004341ac  subsd   xmm0, qword ptr [rbp+var_50]
0x1004341b1  mulsd   xmm1, xmm1
0x1004341b5  mulsd   xmm0, xmm0
0x1004341b9  addsd   xmm1, xmm0
0x1004341bd  comisd  xmm2, xmm1
0x1004341c1  jbe     loc_10043447A
0x1004341c7  movups  xmm0, [rbp+var_50]
0x1004341cb  movsd   qword ptr [rax], xmm1
0x1004341cf  movups  xmm1, [rbp+var_60]
0x1004341d3  movups  xmmword ptr [rax+8], xmm0
0x1004341d7  movups  xmmword ptr [rax+18h], xmm1
0x1004341db  jmp     loc_10043447A
0x1004341e0  movsd   xmm5, qword ptr [rdi+68h]
0x1004341e5  movsd   xmm2, qword ptr [rdi+70h]
0x1004341ea  movsd   xmm3, qword ptr [rbx]
0x1004341ee  movsd   xmm1, qword ptr [rbx+8]
0x1004341f3  subsd   xmm3, xmm5
0x1004341f7  mov     [rsp+80h+arg_0], r15
0x1004341ff  subsd   xmm1, xmm2
0x100434203  movaps  [rsp+80h+var_10], xmm6
0x100434208  movaps  [rsp+80h+var_20], xmm7
0x10043420d  movaps  [rsp+80h+var_30], xmm8
0x100434213  movsd   xmm8, qword ptr [rbx+10h]
0x100434219  movaps  [rsp+80h+var_40], xmm9
0x10043421f  subsd   xmm8, xmm5
0x100434224  movsd   xmm9, qword ptr [rbx+18h]
0x10043422a  subsd   xmm9, xmm2
0x10043422f  movaps  xmm6, xmm8
0x100434233  subsd   xmm6, xmm3
0x100434237  movaps  xmm4, xmm9
0x10043423b  subsd   xmm4, xmm1
0x10043423f  movaps  xmm0, xmm6
0x100434242  mulsd   xmm0, xmm3
0x100434246  movaps  xmm7, xmm4
0x100434249  mulsd   xmm7, xmm1
0x10043424d  addsd   xmm7, xmm0
0x100434251  xorps   xmm0, xmm0
0x100434254  xorps   xmm7, cs:__xmm@80000000000000008000000000000000
0x10043425b  comisd  xmm0, xmm7
0x10043425f  jbe     short loc_100434269
0x100434261  xor     r15b, r15b
0x100434264  jmp     loc_10043432F
0x100434269  mulsd   xmm4, xmm4
0x10043426d  mulsd   xmm6, xmm6
0x100434271  addsd   xmm4, xmm6
0x100434275  comisd  xmm7, xmm4
0x100434279  jbe     short loc_100434283
0x10043427b  xor     r15b, r15b
0x10043427e  jmp     loc_10043432F
0x100434283  movsd   xmm0, cs:__real@3ff0000000000000
0x10043428b  mov     r15b, 1
0x10043428e  mov     rax, [r14+18h]
0x100434292  divsd   xmm7, xmm4
0x100434296  mulsd   xmm8, xmm7
0x10043429b  subsd   xmm0, xmm7
0x10043429f  mulsd   xmm9, xmm7
0x1004342a4  mulsd   xmm3, xmm0
0x1004342a8  mulsd   xmm1, xmm0
0x1004342ac  movsd   xmm0, qword ptr [rax]
0x1004342b0  addsd   xmm3, xmm5
0x1004342b4  addsd   xmm1, xmm2
0x1004342b8  addsd   xmm3, xmm8
0x1004342bd  addsd   xmm1, xmm9
0x1004342c2  movsd   qword ptr [rbp+var_50], xmm3
0x1004342c7  movsd   qword ptr [rbp+var_50+8], xmm1
0x1004342cc  test    sil, sil
0x1004342cf  jz      short loc_100434301
0x1004342d1  subsd   xmm1, xmm2
0x1004342d5  subsd   xmm3, xmm5
0x1004342d9  mulsd   xmm1, xmm1
0x1004342dd  mulsd   xmm3, xmm3
0x1004342e1  addsd   xmm1, xmm3
0x1004342e5  comisd  xmm0, xmm1
0x1004342e9  jbe     short loc_10043432F
0x1004342eb  movsd   qword ptr [rax], xmm1
0x1004342ef  movups  xmm0, xmmword ptr [rdi+68h]
0x1004342f3  movups  xmm1, [rbp+var_50]
0x1004342f7  movups  xmmword ptr [rax+8], xmm0
0x1004342fb  movups  xmmword ptr [rax+18h], xmm1
0x1004342ff  jmp     short loc_10043432F
0x100434301  subsd   xmm2, xmm1
0x100434305  subsd   xmm5, xmm3
0x100434309  mulsd   xmm2, xmm2
0x10043430d  mulsd   xmm5, xmm5
0x100434311  addsd   xmm2, xmm5
0x100434315  comisd  xmm0, xmm2
0x100434319  jbe     short loc_10043432F
0x10043431b  movups  xmm0, [rbp+var_50]
0x10043431f  movsd   qword ptr [rax], xmm2
0x100434323  movups  xmmword ptr [rax+8], xmm0
0x100434327  movups  xmm0, xmmword ptr [rdi+68h]
0x10043432b  movups  xmmword ptr [rax+18h], xmm0
0x10043432f  lea     r8, [rbp+var_60]
0x100434333  mov     rcx, rdi
0x100434336  lea     rdx, [rbx+10h]
0x10043433a  call    ?GetPointNearestToPoint@CCircularArc2D@@QEBA_NAEBV?$CMglPoint@N@@AEAV2@@Z; CCircularArc2D::GetPointNearestToPoint(CMglPoint<double> const &,CMglPoint<double> &)
0x10043433f  movaps  xmm9, [rsp+80h+var_40]
0x100434345  movaps  xmm8, [rsp+80h+var_30]
0x10043434b  movaps  xmm7, [rsp+80h+var_20]
0x100434350  movaps  xmm6, [rsp+80h+var_10]
0x100434355  test    al, al
0x100434357  jz      loc_1004343DE
0x10043435d  mov     rcx, [r14+18h]
0x100434361  movsd   xmm2, qword ptr [rbx+10h]
0x100434366  movsd   xmm1, qword ptr [rbx+18h]
0x10043436b  movsd   xmm3, qword ptr [rcx]
0x10043436f  test    sil, sil
0x100434372  jz      short loc_1004343A6
0x100434374  subsd   xmm1, qword ptr [rbp+var_60+8]
0x100434379  subsd   xmm2, qword ptr [rbp+var_60]
0x10043437e  mulsd   xmm1, xmm1
0x100434382  mulsd   xmm2, xmm2
0x100434386  addsd   xmm1, xmm2
0x10043438a  comisd  xmm3, xmm1
0x10043438e  jbe     short loc_1004343DE
0x100434390  movups  xmm0, [rbp+var_60]
0x100434394  movsd   qword ptr [rcx], xmm1
0x100434398  movups  xmmword ptr [rcx+8], xmm0
0x10043439c  movups  xmm0, xmmword ptr [rbx+10h]
0x1004343a0  movups  xmmword ptr [rcx+18h], xmm0
0x1004343a4  jmp     short loc_1004343DE
0x1004343a6  movsd   xmm0, qword ptr [rbp+var_60]
0x1004343ab  subsd   xmm0, xmm2
0x1004343af  movsd   xmm2, qword ptr [rbp+var_60+8]
0x1004343b4  subsd   xmm2, xmm1
0x1004343b8  mulsd   xmm0, xmm0
0x1004343bc  mulsd   xmm2, xmm2
0x1004343c0  addsd   xmm2, xmm0
0x1004343c4  comisd  xmm3, xmm2
0x1004343c8  jbe     short loc_1004343DE
0x1004343ca  movups  xmm1, [rbp+var_60]
0x1004343ce  movsd   qword ptr [rcx], xmm2
0x1004343d2  movups  xmm0, xmmword ptr [rbx+10h]
0x1004343d6  movups  xmmword ptr [rcx+18h], xmm1
0x1004343da  movups  xmmword ptr [rcx+8], xmm0
0x1004343de  test    r15b, r15b
0x1004343e1  mov     r15, [rsp+80h+arg_0]
0x1004343e9  jnz     loc_10043447A
0x1004343ef  test    al, al
0x1004343f1  jnz     loc_10043447A
0x1004343f7  mov     rax, [r14+18h]
0x1004343fb  test    sil, sil
0x1004343fe  jz      short loc_10043443C
0x100434400  movsd   xmm0, qword ptr [rbx+10h]
0x100434405  subsd   xmm0, qword ptr [rdi+68h]
0x10043440a  movsd   xmm1, qword ptr [rbx+18h]
0x10043440f  subsd   xmm1, qword ptr [rdi+70h]
0x100434414  mulsd   xmm0, xmm0
0x100434418  mulsd   xmm1, xmm1
0x10043441c  addsd   xmm1, xmm0
0x100434420  movsd   xmm0, qword ptr [rax]
0x100434424  comisd  xmm0, xmm1
0x100434428  jbe     short loc_10043447A
0x10043442a  movsd   qword ptr [rax], xmm1
0x10043442e  movups  xmm0, xmmword ptr [rdi+68h]
0x100434432  movups  xmmword ptr [rax+8], xmm0
0x100434436  movups  xmm0, xmmword ptr [rbx+10h]
0x10043443a  jmp     short loc_100434476
0x10043443c  movsd   xmm0, qword ptr [rdi+68h]
0x100434441  subsd   xmm0, qword ptr [rbx+10h]
0x100434446  movsd   xmm1, qword ptr [rdi+70h]
0x10043444b  subsd   xmm1, qword ptr [rbx+18h]
0x100434450  mulsd   xmm0, xmm0
0x100434454  mulsd   xmm1, xmm1
0x100434458  addsd   xmm1, xmm0
0x10043445c  movsd   xmm0, qword ptr [rax]
0x100434460  comisd  xmm0, xmm1
0x100434464  jbe     short loc_10043447A
0x100434466  movsd   qword ptr [rax], xmm1
0x10043446a  movups  xmm0, xmmword ptr [rbx+10h]
0x10043446e  movups  xmmword ptr [rax+8], xmm0
0x100434472  movups  xmm0, xmmword ptr [rdi+68h]
0x100434476  movups  xmmword ptr [rax+18h], xmm0
0x10043447a  lea     r11, [rsp+80h+var_s0]
0x100434482  mov     rbx, [r11+28h]
0x100434486  mov     rsi, [r11+30h]
0x10043448a  mov     rsp, r11
0x10043448d  pop     r14
0x10043448f  pop     rdi
0x100434490  pop     rbp
0x100434491  retn
```
