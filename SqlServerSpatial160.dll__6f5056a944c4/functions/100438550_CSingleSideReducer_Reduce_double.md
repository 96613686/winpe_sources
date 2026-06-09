# CSingleSideReducer::Reduce(double &)

- ea: `0x100438550`
- end: `0x100438d86`
- name: `?Reduce@CSingleSideReducer@@AEAAJAEAN@Z`
- size: `2102`
- prototype: `__int64 __fastcall(CSingleSideReducer *__hidden this, double *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x100437850`

## callees

- `0x100438030`
- `0x100438550`
- `0x100438fc0`

## pseudocode

```c
__int64 __fastcall CSingleSideReducer::Reduce(CSingleSideReducer *this, double *a2)
{
  unsigned int v2; // r13d
  char v3; // si
  unsigned int v4; // r9d
  double *v5; // rbp
  __int64 result; // rax
  double v8; // xmm1_8
  double v9; // xmm7_8
  double v10; // xmm8_8
  unsigned int v11; // r10d
  int v12; // eax
  unsigned int v13; // r8d
  int v14; // ecx
  __int64 v15; // rax
  __int64 v16; // r10
  __int64 v17; // r8
  __int64 v18; // rax
  __int64 v19; // rcx
  unsigned int v20; // r12d
  int v21; // eax
  unsigned int v22; // r8d
  int v23; // ecx
  __int64 v24; // rcx
  __int64 v25; // r8
  __int64 v26; // r14
  __int64 v27; // r15
  char v28; // di
  unsigned int v29; // eax
  char v30; // r11
  bool v31; // zf
  unsigned int v32; // esi
  unsigned int v33; // r12d
  unsigned int v34; // r13d
  __int64 v35; // rcx
  __int64 v36; // rdx
  int v37; // eax
  double *v38; // rdx
  double *v39; // r8
  double *v40; // r9
  double v41; // xmm6_8
  double v42; // xmm6_8
  double v43; // xmm6_8
  __int64 v44; // rcx
  __int64 v45; // rdx
  int v46; // eax
  double *v47; // rdx
  double *v48; // r8
  double *v49; // r9
  double v50; // xmm6_8
  double v51; // xmm6_8
  double v52; // xmm6_8
  unsigned int v53; // eax
  bool v54; // cf
  bool v55; // zf
  double *v56; // rdx
  double v57; // xmm6_8
  double v58; // xmm6_8
  double v59; // xmm6_8
  int v60; // [rsp+40h] [rbp-D8h]
  unsigned int v61; // [rsp+44h] [rbp-D4h]
  unsigned int v62; // [rsp+48h] [rbp-D0h]
  unsigned int v63; // [rsp+4Ch] [rbp-CCh]
  char v64; // [rsp+50h] [rbp-C8h]
  __int64 v65; // [rsp+58h] [rbp-C0h]
  char v66; // [rsp+120h] [rbp+8h]
  char v68; // [rsp+138h] [rbp+20h]

  v2 = *((_DWORD *)this + 38);
  v3 = 0;
  v61 = 0;
  v4 = 0;
  *a2 = 0.0;
  *((_DWORD *)this + 30) = 0;
  v5 = a2;
  result = *((unsigned int *)this + 39);
  v68 = 0;
  v60 = v2;
  if ( !(_DWORD)result )
    return result;
  v8 = *((double *)this + 14);
  v9 = v8 / (double)(int)result;
  v10 = v9 * 0.5;
  if ( v8 < v9 * 0.5 + 0.0 )
    return v4;
  while ( 1 )
  {
    v11 = 0;
LABEL_4:
    v12 = *((_DWORD *)this + 33);
    v13 = *((_DWORD *)this + 37);
    v63 = v11;
    v14 = v12 - 1;
    if ( !v12 )
      v14 = 0;
    if ( v11 < *((_DWORD *)this + 36) + v13 * v14 )
      break;
    v9 = v9 + v9;
    v10 = v9 * 0.5;
    if ( *((double *)this + 14) < v9 * 0.5 + *v5 )
      return v61;
  }
  v15 = *(_QWORD *)(*((_QWORD *)this + 17) + 8LL * (v11 / v13));
  v31 = *(_BYTE *)(v15 + 72LL * (v11 % v13)) == 0;
  v16 = v15 + 72LL * (v11 % v13);
  v65 = v16;
  if ( !v31 )
    goto LABEL_105;
  if ( *(_DWORD *)(v16 + 44) )
  {
    v17 = 0;
    do
    {
      v18 = *(_QWORD *)(v16 + 64);
      if ( !*(_BYTE *)(v18 + v17) )
      {
        *(_BYTE *)(v4 + v18) = 0;
        v19 = 2LL * v4++;
        *(_OWORD *)(*(_QWORD *)(v16 + 48) + 8 * v19) = *(_OWORD *)(*(_QWORD *)(v16 + 48) + 16LL * (unsigned int)v17);
      }
      v17 = (unsigned int)(v17 + 1);
    }
    while ( (unsigned int)v17 < *(_DWORD *)(v16 + 44) );
    *(_DWORD *)(v16 + 44) = v4;
    *(_DWORD *)(v16 + 60) = v4;
  }
  else
  {
    *((_DWORD *)this + 30) += *(_DWORD *)(v16 + 8) >> 3;
    if ( *((_DWORD *)this + 30) > 0x30D40u )
    {
      if ( OSYieldCallback )
      {
        OSYieldCallback();
        v16 = v65;
      }
      *((_DWORD *)this + 30) = 0;
    }
    result = CSingleSideReducer::ShapeData::PopulateSortedArray((CSingleSideReducer::ShapeData *)v16);
    v61 = result;
    if ( (int)result < 0 )
    {
      _mm_lfence();
      return result;
    }
    v16 = v65;
  }
  v4 = 0;
  v62 = 0;
  v20 = 0;
  while ( 1 )
  {
    v21 = *(_DWORD *)(v16 + 20);
    v22 = *(_DWORD *)(v16 + 36);
    v23 = v21 - 1;
    if ( !v21 )
      v23 = 0;
    if ( v20 >= *(_DWORD *)(v16 + 32) + v22 * v23 )
      goto LABEL_105;
    v24 = v20 / v22;
    v25 = v20 % v22;
    v26 = 56 * v25;
    v27 = *(_QWORD *)(*(_QWORD *)(v16 + 24) + 8 * v24);
    if ( *(_BYTE *)(v27 + 56 * v25 + 1) )
      goto LABEL_101;
    v28 = *(_BYTE *)(v27 + 56 * v25);
    v29 = *(_DWORD *)(v27 + v26 + 48);
    v30 = *((_BYTE *)this + 106) == (v20 == 0);
    v66 = v30;
    v64 = v30;
    v31 = v29 == 3;
    if ( v29 > 3 )
      break;
LABEL_79:
    if ( v31 )
    {
      if ( v20 )
      {
        v54 = v2 == 0;
        v55 = v2 == 1;
      }
      else
      {
        v54 = v2 < *(_DWORD *)(v16 + 4);
        v55 = v2 == *(_DWORD *)(v16 + 4);
      }
      if ( *((_BYTE *)this + 105) | (!v54 && !v55) )
      {
        if ( ++*((_DWORD *)this + 30) > 0x30D40u )
        {
          if ( OSYieldCallback )
            OSYieldCallback();
          *((_DWORD *)this + 30) = 0;
        }
        v56 = *(double **)(v27 + v26 + 32);
        if ( v64 == v28 )
          v57 = DOUBLE_N0_5;
        else
          v57 = DOUBLE_0_5;
        v58 = v57 * ((v56[5] - v56[3]) * (*v56 - v56[2]) - (v56[1] - v56[3]) * (v56[4] - v56[2]));
        if ( v58 <= 0.0 || v9 * 4.0 <= v58 || *((double *)this + 14) < v58 + *v5 )
        {
          v16 = v65;
        }
        else if ( (unsigned __int8)CSingleSideReducer::FTriangleConflictsWithOtherPoints(
                                     (_DWORD)this,
                                     (_DWORD)v56,
                                     (int)v56 + 16,
                                     (int)v56 + 32,
                                     *(_QWORD *)(v65 + 48),
                                     *(_QWORD *)(v65 + 64),
                                     *(_DWORD *)(v65 + 44),
                                     1) )
        {
          v16 = v65;
        }
        else
        {
          v59 = v58 + *v5;
          *v5 = v59;
          if ( v59 + v10 >= *((double *)this + 14) )
            v3 = 1;
          v68 = v3;
          if ( !v20 )
          {
            v2 -= *(_DWORD *)(v65 + 4);
            v60 = v2;
            *(_BYTE *)v65 = 1;
            if ( v3 )
              return v61;
            v4 = 0;
LABEL_105:
            v11 = v63 + 1;
            goto LABEL_4;
          }
          *(_BYTE *)(v27 + v26 + 1) = 1;
          v16 = v65;
          --*(_DWORD *)(v65 + 4);
          v60 = --v2;
        }
      }
    }
LABEL_101:
    v62 = ++v20;
    if ( v3 )
      return v61;
    v4 = 0;
  }
  v32 = 0;
  v33 = *(_DWORD *)(v27 + v26 + 48);
  v34 = 0;
  do
  {
    if ( v33 != 3 )
    {
      if ( ++*((_DWORD *)this + 30) > 0x30D40u )
      {
        if ( OSYieldCallback )
        {
          OSYieldCallback();
          v16 = v65;
          v30 = v66;
        }
        *((_DWORD *)this + 30) = 0;
      }
      v35 = *(_QWORD *)(v27 + v26 + 32);
      v36 = v32 - 1;
      v37 = *(_DWORD *)(v27 + v26 + 48);
      if ( !v32 )
        v36 = (unsigned int)(v37 - 1);
      v38 = (double *)(v35 + 16 * v36);
      v39 = (double *)(v35 + 16LL * v34);
      if ( v34 >= v37 - 1 )
        v40 = *(double **)(v27 + v26 + 32);
      else
        v40 = (double *)(v35 + 16LL * (v34 + 1));
      if ( v30 == v28 )
        v41 = DOUBLE_N0_5;
      else
        v41 = DOUBLE_0_5;
      v42 = v41 * ((v40[1] - v39[1]) * (*v38 - *v39) - (v38[1] - v39[1]) * (*v40 - *v39));
      if ( v42 > 0.0 && v9 > v42 && *((double *)this + 14) >= v42 + *a2 )
      {
        if ( !(unsigned __int8)CSingleSideReducer::FTriangleConflictsWithOtherPoints(
                                 (_DWORD)this,
                                 (_DWORD)v38,
                                 (_DWORD)v39,
                                 (_DWORD)v40,
                                 *(_QWORD *)(v16 + 48),
                                 *(_QWORD *)(v16 + 64),
                                 *(_DWORD *)(v16 + 44),
                                 0) )
        {
          v5 = a2;
          --v33;
          v43 = v42 + *a2;
          *a2 = v43;
          if ( v43 + v10 < *((double *)this + 14) )
          {
            if ( !v68 )
            {
              while ( v32 && v33 > 3 )
              {
                if ( ++*((_DWORD *)this + 30) > 0x30D40u )
                {
                  if ( OSYieldCallback )
                    OSYieldCallback();
                  *((_DWORD *)this + 30) = 0;
                }
                v44 = *(_QWORD *)(v27 + v26 + 32);
                v45 = v32 - 2;
                v46 = *(_DWORD *)(v27 + v26 + 48);
                if ( v32 <= 1 )
                  v45 = (unsigned int)(v46 - 1);
                v47 = (double *)(v44 + 16 * v45);
                v48 = (double *)(v44 + 16LL * (v32 - 1));
                if ( v34 >= v46 - 1 )
                  v49 = *(double **)(v27 + v26 + 32);
                else
                  v49 = (double *)(v44 + 16LL * (v34 + 1));
                v30 = v66;
                if ( v66 == v28 )
                  v50 = DOUBLE_N0_5;
                else
                  v50 = DOUBLE_0_5;
                v51 = v50 * ((v49[1] - v48[1]) * (*v47 - *v48) - (v47[1] - v48[1]) * (*v49 - *v48));
                if ( v51 <= 0.0 || v9 <= v51 || *((double *)this + 14) < v51 + *a2 )
                  goto LABEL_75;
                if ( (unsigned __int8)CSingleSideReducer::FTriangleConflictsWithOtherPoints(
                                        (_DWORD)this,
                                        (_DWORD)v47,
                                        (_DWORD)v48,
                                        (_DWORD)v49,
                                        *(_QWORD *)(v65 + 48),
                                        *(_QWORD *)(v65 + 64),
                                        *(_DWORD *)(v65 + 44),
                                        0) )
                  break;
                v52 = v51 + *a2;
                --v33;
                --v32;
                *a2 = v52;
                if ( v52 + v10 >= *((double *)this + 14) )
                {
                  v30 = v66;
                  v68 = 1;
                  goto LABEL_75;
                }
              }
            }
          }
          else
          {
            v68 = 1;
          }
          v30 = v66;
          goto LABEL_75;
        }
        v30 = v66;
      }
      *(_OWORD *)(*(_QWORD *)(v27 + v26 + 32) + 16LL * v32) = *(_OWORD *)(*(_QWORD *)(v27 + v26 + 32) + 16LL * v34);
      if ( *((_BYTE *)this + 16) )
        *(_QWORD *)(*(_QWORD *)(v27 + v26 + 40) + 8LL * v32) = *(_QWORD *)(*(_QWORD *)(v27 + v26 + 40) + 8LL * v34);
      v5 = a2;
      ++v32;
LABEL_75:
      v16 = v65;
      goto LABEL_76;
    }
    *(_OWORD *)(*(_QWORD *)(v27 + v26 + 32) + 16LL * v32) = *(_OWORD *)(*(_QWORD *)(v27 + v26 + 32) + 16LL * v34);
    if ( *((_BYTE *)this + 16) )
      *(_QWORD *)(*(_QWORD *)(v27 + v26 + 40) + 8LL * v32) = *(_QWORD *)(*(_QWORD *)(v27 + v26 + 40) + 8LL * v34);
    ++v32;
LABEL_76:
    ++v34;
    v53 = v32;
  }
  while ( v34 < *(_DWORD *)(v27 + v26 + 48) );
  *(_DWORD *)(v27 + v26 + 48) = v32;
  v3 = v68;
  if ( !v68 )
  {
    v31 = v53 == 3;
    v20 = v62;
    v2 = v60;
    goto LABEL_79;
  }
  return v61;
}

```

## disassembly

```asm
0x100438550  mov     [rsp+arg_8], rdx
0x100438555  push    rbx
0x100438556  push    rbp
0x100438557  push    rsi
0x100438558  push    r13
0x10043855a  sub     rsp, 0F8h
0x100438561  mov     r13d, [rcx+98h]
0x100438568  xor     eax, eax
0x10043856a  xor     sil, sil
0x10043856d  mov     [rsp+118h+var_D4], eax
0x100438571  mov     r9d, eax
0x100438574  mov     [rdx], rax
0x100438577  mov     [rcx+78h], eax
0x10043857a  mov     rbp, rdx
0x10043857d  mov     eax, [rcx+9Ch]
0x100438583  mov     rbx, rcx
0x100438586  mov     [rsp+118h+arg_18], esi
0x10043858d  mov     [rsp+118h+var_D8], r13d
0x100438592  test    eax, eax
0x100438594  jnz     short loc_1004385A3
0x100438596  add     rsp, 0F8h
0x10043859d  pop     r13
0x10043859f  pop     rsi
0x1004385a0  pop     rbp
0x1004385a1  pop     rbx
0x1004385a2  retn
0x1004385a3  movsd   xmm1, qword ptr [rcx+70h]
0x1004385a8  xorps   xmm0, xmm0
0x1004385ab  mov     [rsp+118h+var_28], rdi
0x1004385b3  mov     [rsp+118h+var_30], r12
0x1004385bb  mov     [rsp+118h+var_38], r14
0x1004385c3  mov     [rsp+118h+var_40], r15
0x1004385cb  movaps  [rsp+118h+var_58], xmm6
0x1004385d3  movaps  [rsp+118h+var_68], xmm7
0x1004385db  movaps  xmm7, xmm1
0x1004385de  movaps  [rsp+118h+var_78], xmm8
0x1004385e7  cvtsi2sd xmm0, rax
0x1004385ec  movaps  [rsp+118h+var_88], xmm9
0x1004385f5  movsd   xmm9, cs:__real@3fe0000000000000
0x1004385fe  divsd   xmm7, xmm0
0x100438602  movaps  [rsp+118h+var_98], xmm10
0x10043860b  movaps  xmm8, xmm7
0x10043860f  movaps  [rsp+118h+var_A8], xmm11
0x100438615  mulsd   xmm8, xmm9
0x10043861a  xorps   xmm11, xmm11
0x10043861e  movaps  [rsp+118h+var_B8], xmm12
0x100438624  movaps  xmm0, xmm8
0x100438628  addsd   xmm0, xmm11
0x10043862d  comisd  xmm1, xmm0
0x100438631  jb      loc_100438D14
0x100438637  movsd   xmm10, cs:__real@bfe0000000000000
0x100438640  movsd   xmm12, cs:__real@4010000000000000
0x100438649  nop     dword ptr [rax+00000000h]
0x100438650  mov     r10d, r9d
0x100438653  mov     eax, [rbx+84h]
0x100438659  test    eax, eax
0x10043865b  mov     r8d, [rbx+94h]
0x100438662  mov     [rsp+118h+var_CC], r10d
0x100438667  lea     ecx, [rax-1]
0x10043866a  cmovz   ecx, r9d
0x10043866e  imul    ecx, r8d
0x100438672  add     ecx, [rbx+90h]
0x100438678  cmp     r10d, ecx
0x10043867b  jnb     loc_100438CEA
0x100438681  xor     edx, edx
0x100438683  mov     eax, r10d
0x100438686  div     r8d
0x100438689  mov     ecx, edx
0x10043868b  mov     edx, eax
0x10043868d  mov     rax, [rbx+88h]
0x100438694  lea     rcx, [rcx+rcx*8]
0x100438698  mov     rax, [rax+rdx*8]
0x10043869c  cmp     byte ptr [rax+rcx*8], 0
0x1004386a0  lea     r10, [rax+rcx*8]
0x1004386a4  mov     [rsp+118h+var_C0], r10
0x1004386a9  jnz     loc_100438CDD
0x1004386af  mov     eax, [r10+2Ch]
0x1004386b3  test    eax, eax
0x1004386b5  jnz     short loc_1004386FF
0x1004386b7  mov     eax, [r10+8]
0x1004386bb  shr     eax, 3
0x1004386be  add     [rbx+78h], eax
0x1004386c1  cmp     dword ptr [rbx+78h], 30D40h
0x1004386c8  jbe     short loc_1004386E4
0x1004386ca  mov     rax, cs:?OSYieldCallback@@3P6AXXZEA; void (*OSYieldCallback)(void)
0x1004386d1  test    rax, rax
0x1004386d4  jz      short loc_1004386E0
0x1004386d6  call    rax ; void (*OSYieldCallback)(void)
0x1004386d8  mov     r10, [rsp+118h+var_C0]
0x1004386dd  xor     r9d, r9d
0x1004386e0  mov     [rbx+78h], r9d
0x1004386e4  mov     rcx, r10; this
0x1004386e7  call    ?PopulateSortedArray@ShapeData@CSingleSideReducer@@QEAAJXZ; CSingleSideReducer::ShapeData::PopulateSortedArray(void)
0x1004386ec  mov     [rsp+118h+var_D4], eax
0x1004386f0  test    eax, eax
0x1004386f2  js      loc_100438D7B
0x1004386f8  mov     r10, [rsp+118h+var_C0]
0x1004386fd  jmp     short loc_10043874B
0x1004386ff  xor     r8d, r8d
0x100438702  test    eax, eax
0x100438704  jz      short loc_100438743
0x100438706  nop     word ptr [rax+rax+00000000h]
0x100438710  mov     rax, [r10+40h]
0x100438714  mov     edx, r8d
0x100438717  cmp     byte ptr [rax+r8], 0
0x10043871c  jnz     short loc_10043873A
0x10043871e  mov     ecx, r9d
0x100438721  add     rdx, rdx
0x100438724  mov     byte ptr [rcx+rax], 0
0x100438728  add     rcx, rcx
0x10043872b  mov     rax, [r10+30h]
0x10043872f  inc     r9d
0x100438732  movups  xmm0, xmmword ptr [rax+rdx*8]
0x100438736  movups  xmmword ptr [rax+rcx*8], xmm0
0x10043873a  inc     r8d
0x10043873d  cmp     r8d, [r10+2Ch]
0x100438741  jb      short loc_100438710
0x100438743  mov     [r10+2Ch], r9d
0x100438747  mov     [r10+3Ch], r9d
0x10043874b  xor     r9d, r9d
0x10043874e  mov     [rsp+118h+var_D0], r9d
0x100438753  mov     r12d, r9d
0x100438756  test    sil, sil
0x100438759  jnz     loc_100438D80
0x10043875f  nop
0x100438760  mov     eax, [r10+14h]
0x100438764  test    eax, eax
0x100438766  mov     r8d, [r10+24h]
0x10043876a  lea     ecx, [rax-1]
0x10043876d  cmovz   ecx, r9d
0x100438771  imul    ecx, r8d
0x100438775  add     ecx, [r10+20h]
0x100438779  cmp     r12d, ecx
0x10043877c  jnb     loc_100438CDD
0x100438782  xor     edx, edx
0x100438784  mov     eax, r12d
0x100438787  div     r8d
0x10043878a  mov     ecx, eax
0x10043878c  mov     rax, [r10+18h]
0x100438790  mov     r8d, edx
0x100438793  imul    r14, r8, 38h ; '8'
0x100438797  mov     r15, [rax+rcx*8]
0x10043879b  cmp     byte ptr [r15+r14+1], 0
0x1004387a1  jnz     loc_100438CAD
0x1004387a7  movzx   eax, byte ptr [rbx+6Ah]
0x1004387ab  test    r12d, r12d
0x1004387ae  movzx   edi, byte ptr [r15+r14]
0x1004387b3  mov     ecx, r9d
0x1004387b6  setz    cl
0x1004387b9  mov     [rsp+118h+arg_10], dil
0x1004387c1  cmp     eax, ecx
0x1004387c3  mov     eax, [r15+r14+30h]
0x1004387c8  setz    r11b
0x1004387cc  mov     [rsp+118h+arg_0], r11b
0x1004387d4  mov     [rsp+118h+var_C8], r11b
0x1004387d9  cmp     eax, 3
0x1004387dc  jbe     loc_100438B6A
0x1004387e2  mov     esi, r9d
0x1004387e5  mov     r12d, eax
0x1004387e8  mov     r13d, r9d
0x1004387eb  nop     dword ptr [rax+rax+00h]
0x1004387f0  cmp     r12d, 3
0x1004387f4  jnz     short loc_10043882E
0x1004387f6  mov     rdx, [r15+r14+20h]
0x1004387fb  mov     ecx, r13d
0x1004387fe  add     rcx, rcx
0x100438801  mov     eax, esi
0x100438803  add     rax, rax
0x100438806  mov     r8d, r13d
0x100438809  mov     r9d, esi
0x10043880c  movups  xmm0, xmmword ptr [rdx+rcx*8]
0x100438810  movups  xmmword ptr [rdx+rax*8], xmm0
0x100438814  cmp     byte ptr [rbx+10h], 0
0x100438818  jz      short loc_100438827
0x10043881a  mov     rcx, [r15+r14+28h]
0x10043881f  mov     rax, [rcx+r8*8]
0x100438823  mov     [rcx+r9*8], rax
0x100438827  inc     esi
0x100438829  jmp     loc_100438B20
0x10043882e  inc     dword ptr [rbx+78h]
0x100438831  cmp     dword ptr [rbx+78h], 30D40h
0x100438838  jbe     short loc_10043885D
0x10043883a  mov     rax, cs:?OSYieldCallback@@3P6AXXZEA; void (*OSYieldCallback)(void)
0x100438841  test    rax, rax
0x100438844  jz      short loc_100438859
0x100438846  call    rax ; void (*OSYieldCallback)(void)
0x100438848  mov     r10, [rsp+118h+var_C0]
0x10043884d  xor     r9d, r9d
0x100438850  movzx   r11d, [rsp+118h+arg_0]
0x100438859  mov     [rbx+78h], r9d
0x10043885d  mov     rcx, [r15+r14+20h]
0x100438862  lea     edx, [rsi-1]
0x100438865  mov     eax, [r15+r14+30h]
0x10043886a  test    esi, esi
0x10043886c  jnz     short loc_100438871
0x10043886e  lea     edx, [rax-1]
0x100438871  shl     rdx, 4
0x100438875  add     rdx, rcx
0x100438878  mov     edi, r13d
0x10043887b  add     rdi, rdi
0x10043887e  mov     ebp, r13d
0x100438881  dec     eax
0x100438883  lea     r8, [rcx+rdi*8]
0x100438887  cmp     r13d, eax
0x10043888a  jnb     short loc_100438899
0x10043888c  lea     r9d, [r13+1]
0x100438890  shl     r9, 4
0x100438894  add     r9, rcx
0x100438897  jmp     short loc_10043889C
0x100438899  mov     r9, rcx
0x10043889c  movsd   xmm0, qword ptr [rdx]
0x1004388a0  subsd   xmm0, qword ptr [r8]
0x1004388a5  movsd   xmm4, qword ptr [r9+8]
0x1004388ab  subsd   xmm4, qword ptr [r8+8]
0x1004388b1  movsd   xmm1, qword ptr [rdx+8]
0x1004388b6  subsd   xmm1, qword ptr [r8+8]
0x1004388bc  mulsd   xmm4, xmm0
0x1004388c0  movsd   xmm0, qword ptr [r9]
0x1004388c5  subsd   xmm0, qword ptr [r8]
0x1004388ca  mulsd   xmm1, xmm0
0x1004388ce  subsd   xmm4, xmm1
0x1004388d2  cmp     r11b, [rsp+118h+arg_10]
0x1004388da  jnz     short loc_1004388E2
0x1004388dc  movaps  xmm6, xmm10
0x1004388e0  jmp     short loc_1004388E6
0x1004388e2  movaps  xmm6, xmm9
0x1004388e6  mulsd   xmm6, xmm4
0x1004388ea  comisd  xmm6, xmm11
0x1004388ef  jbe     loc_100438AEA
0x1004388f5  comisd  xmm7, xmm6
0x1004388f9  jbe     loc_100438AEA
0x1004388ff  mov     rax, [rsp+118h+arg_8]
0x100438907  movaps  xmm1, xmm6
0x10043890a  movsd   xmm0, qword ptr [rbx+70h]
0x10043890f  addsd   xmm1, qword ptr [rax]
0x100438913  comisd  xmm0, xmm1
0x100438917  jb      loc_100438AEA
0x10043891d  mov     eax, [r10+2Ch]
0x100438921  mov     rcx, rbx
0x100438924  mov     [rsp+118h+var_E0], 0
0x100438929  mov     [rsp+118h+var_E8], eax
0x10043892d  mov     rax, [r10+40h]
0x100438931  mov     [rsp+118h+var_F0], rax
0x100438936  mov     rax, [r10+30h]
0x10043893a  mov     [rsp+118h+var_F8], rax
0x10043893f  call    ?FTriangleConflictsWithOtherPoints@CSingleSideReducer@@AEAA_NAEBV?$CMglPoint@N@@00PEBV2@PEA_NI_N@Z; CSingleSideReducer::FTriangleConflictsWithOtherPoints(CMglPoint<double> const &,CMglPoint<double> const &,CMglPoint<double> const &,CMglPoint<double> const *,bool *,uint,bool)
0x100438944  test    al, al
0x100438946  jnz     loc_100438AE1
0x10043894c  mov     rbp, [rsp+118h+arg_8]
0x100438954  dec     r12d
0x100438957  addsd   xmm6, qword ptr [rbp+0]
0x10043895c  movsd   qword ptr [rbp+0], xmm6
0x100438961  addsd   xmm6, xmm8
0x100438966  comisd  xmm6, qword ptr [rbx+70h]
0x10043896b  jb      short loc_100438983
0x10043896d  mov     byte ptr [rsp+118h+arg_18], 1
0x100438975  movzx   r11d, [rsp+118h+arg_0]
0x10043897e  jmp     loc_100438B1B
0x100438983  cmp     byte ptr [rsp+118h+arg_18], 0
0x10043898b  jnz     short loc_100438975
0x10043898d  nop     dword ptr [rax]
0x100438990  test    esi, esi
0x100438992  jz      short loc_100438975
0x100438994  cmp     r12d, 3
0x100438998  jbe     short loc_100438975
0x10043899a  inc     dword ptr [rbx+78h]
0x10043899d  cmp     dword ptr [rbx+78h], 30D40h
0x1004389a4  jbe     short loc_1004389B9
0x1004389a6  mov     rax, cs:?OSYieldCallback@@3P6AXXZEA; void (*OSYieldCallback)(void)
0x1004389ad  test    rax, rax
0x1004389b0  jz      short loc_1004389B4
0x1004389b2  call    rax ; void (*OSYieldCallback)(void)
0x1004389b4  xor     eax, eax
0x1004389b6  mov     [rbx+78h], eax
0x1004389b9  mov     rcx, [r15+r14+20h]
0x1004389be  lea     edx, [rsi-2]
0x1004389c1  mov     eax, [r15+r14+30h]
0x1004389c6  cmp     esi, 1
0x1004389c9  ja      short loc_1004389CE
0x1004389cb  lea     edx, [rax-1]
0x1004389ce  shl     rdx, 4
0x1004389d2  lea     edi, [rsi-1]
0x1004389d5  add     rdx, rcx
0x1004389d8  mov     r8d, edi
0x1004389db  shl     r8, 4
0x1004389df  add     r8, rcx
0x1004389e2  dec     eax
0x1004389e4  cmp     r13d, eax
0x1004389e7  jnb     short loc_1004389F6
0x1004389e9  lea     r9d, [r13+1]
0x1004389ed  shl     r9, 4
0x1004389f1  add     r9, rcx
0x1004389f4  jmp     short loc_1004389F9
0x1004389f6  mov     r9, rcx
0x1004389f9  movsd   xmm0, qword ptr [rdx]
0x1004389fd  subsd   xmm0, qword ptr [r8]
0x100438a02  movsd   xmm4, qword ptr [r9+8]
0x100438a08  subsd   xmm4, qword ptr [r8+8]
0x100438a0e  movsd   xmm1, qword ptr [rdx+8]
0x100438a13  subsd   xmm1, qword ptr [r8+8]
  ... truncated ...
```
