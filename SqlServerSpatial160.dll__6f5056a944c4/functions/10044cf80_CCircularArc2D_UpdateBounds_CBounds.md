# CCircularArc2D::UpdateBounds(CBounds &)

- ea: `0x10044cf80`
- end: `0x10044d4c5`
- name: `?UpdateBounds@CCircularArc2D@@QEBAXAEAVCBounds@@@Z`
- size: `1349`
- prototype: `void __fastcall(CCircularArc2D *__hidden this, struct CBounds *)`
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x10042fe80`
- `0x100435c10`
- `0x100446f70`

## callees

- `0x100446530`
- `0x10044cf80`

## pseudocode

```c
void __fastcall CCircularArc2D::UpdateBounds(CCircularArc2D *this, struct CBounds *a2)
{
  double v4; // xmm2_8
  int v5; // edx
  double v6; // xmm4_8
  double v7; // xmm3_8
  double v8; // xmm8_8
  double v9; // xmm5_8
  _BOOL8 v10; // rax
  double v11; // xmm11_8
  double v12; // xmm11_8
  double v13; // xmm10_8
  double v14; // xmm9_8
  double v15; // xmm11_8
  double v16; // xmm1_8
  double v17; // xmm3_8
  double v18; // xmm4_8
  _BOOL8 v19; // rax
  double v20; // xmm9_8
  double v21; // xmm4_8
  double v22; // xmm3_8
  double v23; // xmm8_8
  double v24; // xmm4_8
  double v25; // xmm4_8
  double v26; // xmm3_8
  double v27; // xmm4_8
  _BOOL8 v28; // rax
  double v29; // xmm11_8
  double v30; // xmm10_8
  double v31; // xmm9_8
  double v32; // xmm8_8
  double v33; // xmm10_8
  double v34; // xmm10_8
  double v35; // xmm1_8
  double v36; // xmm3_8
  double v37; // xmm4_8
  _BOOL8 v38; // rax
  double v39; // xmm8_8
  double v40; // xmm3_8
  double v41; // xmm4_8
  double v42; // xmm1_8
  double v43; // xmm3_8
  double v44; // xmm3_8

  CBounds::UpdateWithPoint(a2, (char *)this + 104);
  if ( *((double *)this + 16) != 0.0 )
  {
    v4 = *((double *)this + 17);
    v5 = 0;
    v6 = *((double *)this + 3);
    v7 = *((double *)this + 5);
    *(_QWORD *)&v8 = *((_QWORD *)this + 18) & _xmm;
    v9 = v8 * *((double *)this + 19);
    if ( COERCE_DOUBLE(*(_QWORD *)&v4 & _xmm) < 0.7071067811865476 || v4 * v7 < 0.0 )
      LOBYTE(v10) = v7 >= v4 * v9;
    else
      v10 = v8 * v9 > COERCE_DOUBLE(*(_QWORD *)&v6 & _xmm) == v4 > 0.0;
    v11 = DOUBLE_1_0eN12;
    if ( v10 )
    {
      v12 = v6 / v9;
      v13 = v7 / v9;
      if ( v8 >= 1.414213562373095 || v13 < 0.0 )
        v14 = (v13 - v4) / v8;
      else
        v14 = v8 / (v4 + 1.0) - v12 * v12 / ((v13 + 1.0) * v8);
      v15 = v12 / v8 * v6 + *((double *)this + 1) + v7 * v14;
      v16 = COERCE_DOUBLE(*(_QWORD *)&v15 & _xmm) * 1.0e-12 + v15;
      v11 = DOUBLE_1_0eN12;
      if ( v16 > *((double *)a2 + 1) )
      {
        *((double *)a2 + 1) = v16;
        v4 = *((double *)this + 17);
      }
    }
    *(_QWORD *)&v17 = *(_QWORD *)&v7 ^ _xmm;
    *(_QWORD *)&v18 = *(_QWORD *)&v6 ^ _xmm;
    if ( COERCE_DOUBLE(*(_QWORD *)&v4 & _xmm) < 0.7071067811865476 || v4 * v17 < 0.0 )
      LOBYTE(v19) = v17 >= v4 * v9;
    else
      v19 = COERCE_DOUBLE(*((_QWORD *)this + 18) & _xmm) * v9 > COERCE_DOUBLE(*(_QWORD *)&v18 & _xmm) == v4 > 0.0;
    if ( v19 )
    {
      *(_QWORD *)&v20 = *((_QWORD *)this + 18) & _xmm;
      v21 = v18 / v9;
      v22 = v17 / v9;
      if ( v20 >= 1.414213562373095 || v22 < 0.0 )
        v23 = (v22 - v4) / v20;
      else
        v23 = v20 / (v4 + 1.0) - v21 * v21 / ((v22 + 1.0) * v20);
      v24 = v21 / v20 * *((double *)this + 3) + *((double *)this + 1) + v23 * *((double *)this + 5);
      v25 = v24 - COERCE_DOUBLE(*(_QWORD *)&v24 & _xmm) * v11;
      if ( *(double *)a2 > v25 )
      {
        *(double *)a2 = v25;
        v4 = *((double *)this + 17);
      }
    }
    v26 = *((double *)this + 4);
    v27 = *((double *)this + 6);
    if ( COERCE_DOUBLE(*(_QWORD *)&v4 & _xmm) < 0.7071067811865476 || v4 * v27 < 0.0 )
      LOBYTE(v28) = v27 >= v4 * v9;
    else
      v28 = COERCE_DOUBLE(*((_QWORD *)this + 18) & _xmm) * v9 > COERCE_DOUBLE(*(_QWORD *)&v26 & _xmm) == v4 > 0.0;
    if ( v28 )
    {
      *(_QWORD *)&v29 = *((_QWORD *)this + 18) & _xmm;
      v30 = v26 / v9;
      v31 = v27 / v9;
      if ( v29 >= 1.414213562373095 || v31 < 0.0 )
        v32 = (v31 - v4) / v29;
      else
        v32 = v29 / (v4 + 1.0) - v30 * v30 / ((v31 + 1.0) * v29);
      v33 = v30 / v29;
      v11 = DOUBLE_1_0eN12;
      v34 = v33 * v26 + *((double *)this + 2) + v27 * v32;
      v35 = COERCE_DOUBLE(*(_QWORD *)&v34 & _xmm) * 1.0e-12 + v34;
      if ( v35 > *((double *)a2 + 3) )
      {
        *((double *)a2 + 3) = v35;
        v4 = *((double *)this + 17);
      }
    }
    *(_QWORD *)&v36 = *(_QWORD *)&v26 ^ _xmm;
    *(_QWORD *)&v37 = *(_QWORD *)&v27 ^ _xmm;
    if ( COERCE_DOUBLE(*(_QWORD *)&v4 & _xmm) < 0.7071067811865476 || v4 * v37 < 0.0 )
    {
      LOBYTE(v38) = v37 >= v4 * v9;
    }
    else
    {
      LOBYTE(v5) = v4 > 0.0;
      v38 = COERCE_DOUBLE(*((_QWORD *)this + 18) & _xmm) * v9 > COERCE_DOUBLE(*(_QWORD *)&v36 & _xmm) == v5;
    }
    if ( v38 )
    {
      *(_QWORD *)&v39 = *((_QWORD *)this + 18) & _xmm;
      v40 = v36 / v9;
      v41 = v37 / v9;
      if ( v39 >= 1.414213562373095 || v41 < 0.0 )
        v42 = (v41 - v4) / v39;
      else
        v42 = v39 / (v4 + 1.0) - v40 * v40 / ((v41 + 1.0) * v39);
      v43 = v40 / v39 * *((double *)this + 4) + *((double *)this + 2) + v42 * *((double *)this + 6);
      v44 = v43 - COERCE_DOUBLE(*(_QWORD *)&v43 & _xmm) * v11;
      if ( *((double *)a2 + 2) > v44 )
        *((double *)a2 + 2) = v44;
    }
  }
}

```

## disassembly

```asm
0x10044cf80  mov     [rsp+arg_0], rbx
0x10044cf85  push    rdi
0x10044cf86  sub     rsp, 0C0h
0x10044cf8d  mov     rdi, rdx
0x10044cf90  movaps  [rsp+0C8h+var_28], xmm7
0x10044cf98  lea     rdx, [rcx+68h]
0x10044cf9c  mov     rbx, rcx
0x10044cf9f  mov     rcx, rdi
0x10044cfa2  call    ?UpdateWithPoint@CBounds@@QEAAXAEBV?$CMglPoint@N@@@Z; CBounds::UpdateWithPoint(CMglPoint<double> const &)
0x10044cfa7  xorps   xmm7, xmm7
0x10044cfaa  ucomisd xmm7, qword ptr [rbx+80h]
0x10044cfb2  jp      short loc_10044CFBA
0x10044cfb4  jz      loc_10044D4AC
0x10044cfba  movsd   xmm2, qword ptr [rbx+88h]
0x10044cfc2  xor     edx, edx
0x10044cfc4  movsd   xmm4, qword ptr [rbx+18h]
0x10044cfc9  movaps  xmm0, xmm2
0x10044cfcc  movsd   xmm3, qword ptr [rbx+28h]
0x10044cfd1  movaps  [rsp+0C8h+var_18], xmm6
0x10044cfd9  movsd   xmm6, qword ptr cs:__xmm@7fffffffffffffff7fffffffffffffff
0x10044cfe1  movaps  [rsp+0C8h+var_38], xmm8
0x10044cfea  andps   xmm0, xmm6
0x10044cfed  movsd   xmm8, qword ptr [rbx+90h]
0x10044cff6  movaps  [rsp+0C8h+var_68], xmm11
0x10044cffc  andps   xmm8, xmm6
0x10044d000  movaps  [rsp+0C8h+var_78], xmm12
0x10044d006  movaps  xmm5, xmm8
0x10044d00a  mulsd   xmm5, qword ptr [rbx+98h]
0x10044d012  movaps  [rsp+0C8h+var_88], xmm13
0x10044d018  movaps  [rsp+0C8h+var_98], xmm14
0x10044d01e  movsd   xmm14, cs:__real@3fe6a09e667f3bcd
0x10044d027  comisd  xmm14, xmm0
0x10044d02c  movaps  [rsp+0C8h+var_A8], xmm15
0x10044d032  ja      short loc_10044D068
0x10044d034  movaps  xmm0, xmm2
0x10044d037  mulsd   xmm0, xmm3
0x10044d03b  comisd  xmm7, xmm0
0x10044d03f  ja      short loc_10044D068
0x10044d041  mov     ecx, edx
0x10044d043  mov     eax, edx
0x10044d045  movaps  xmm0, xmm8
0x10044d049  movaps  xmm1, xmm4
0x10044d04c  mulsd   xmm0, xmm5
0x10044d050  andps   xmm1, xmm6
0x10044d053  comisd  xmm0, xmm1
0x10044d057  setnbe  cl
0x10044d05a  comisd  xmm2, xmm7
0x10044d05e  setnbe  al
0x10044d061  cmp     ecx, eax
0x10044d063  setz    al
0x10044d066  jmp     short loc_10044D076
0x10044d068  movaps  xmm0, xmm2
0x10044d06b  mulsd   xmm0, xmm5
0x10044d06f  comisd  xmm3, xmm0
0x10044d073  setnb   al
0x10044d076  movsd   xmm15, cs:__real@3ff6a09e667f3bcd
0x10044d07f  movsd   xmm12, cs:__real@3ff0000000000000
0x10044d088  movsd   xmm11, cs:__real@3d719799812dea11
0x10044d091  movaps  [rsp+0C8h+var_48], xmm9
0x10044d09a  movaps  [rsp+0C8h+var_58], xmm10
0x10044d0a0  test    al, al
0x10044d0a2  jz      loc_10044D154
0x10044d0a8  comisd  xmm8, xmm15
0x10044d0ad  movaps  xmm11, xmm4
0x10044d0b1  movaps  xmm10, xmm3
0x10044d0b5  divsd   xmm11, xmm5
0x10044d0ba  divsd   xmm10, xmm5
0x10044d0bf  jnb     short loc_10044D0F8
0x10044d0c1  comisd  xmm7, xmm10
0x10044d0c6  ja      short loc_10044D0F8
0x10044d0c8  addsd   xmm10, xmm12
0x10044d0cd  movaps  xmm0, xmm2
0x10044d0d0  movaps  xmm1, xmm11
0x10044d0d4  addsd   xmm0, xmm12
0x10044d0d9  mulsd   xmm1, xmm11
0x10044d0de  movaps  xmm9, xmm8
0x10044d0e2  mulsd   xmm10, xmm8
0x10044d0e7  divsd   xmm9, xmm0
0x10044d0ec  divsd   xmm1, xmm10
0x10044d0f1  subsd   xmm9, xmm1
0x10044d0f6  jmp     short loc_10044D106
0x10044d0f8  movaps  xmm9, xmm10
0x10044d0fc  subsd   xmm9, xmm2
0x10044d101  divsd   xmm9, xmm8
0x10044d106  divsd   xmm11, xmm8
0x10044d10b  movaps  xmm0, xmm3
0x10044d10e  mulsd   xmm11, xmm4
0x10044d113  mulsd   xmm0, xmm9
0x10044d118  addsd   xmm11, qword ptr [rbx+8]
0x10044d11e  addsd   xmm11, xmm0
0x10044d123  movaps  xmm1, xmm11
0x10044d127  andps   xmm1, xmm6
0x10044d12a  mulsd   xmm1, cs:__real@3d719799812dea11
0x10044d132  addsd   xmm1, xmm11
0x10044d137  movsd   xmm11, cs:__real@3d719799812dea11
0x10044d140  comisd  xmm1, qword ptr [rdi+8]
0x10044d145  jbe     short loc_10044D154
0x10044d147  movsd   qword ptr [rdi+8], xmm1
0x10044d14c  movsd   xmm2, qword ptr [rbx+88h]
0x10044d154  movsd   xmm13, qword ptr cs:__xmm@80000000000000008000000000000000
0x10044d15d  movaps  xmm0, xmm2
0x10044d160  andps   xmm0, xmm6
0x10044d163  xorps   xmm3, xmm13
0x10044d167  comisd  xmm14, xmm0
0x10044d16c  xorps   xmm4, xmm13
0x10044d170  ja      short loc_10044D1AD
0x10044d172  movaps  xmm0, xmm2
0x10044d175  mulsd   xmm0, xmm3
0x10044d179  comisd  xmm7, xmm0
0x10044d17d  ja      short loc_10044D1AD
0x10044d17f  movsd   xmm0, qword ptr [rbx+90h]
0x10044d187  mov     ecx, edx
0x10044d189  mov     eax, edx
0x10044d18b  andps   xmm0, xmm6
0x10044d18e  mulsd   xmm0, xmm5
0x10044d192  movaps  xmm1, xmm4
0x10044d195  andps   xmm1, xmm6
0x10044d198  comisd  xmm0, xmm1
0x10044d19c  setnbe  cl
0x10044d19f  comisd  xmm2, xmm7
0x10044d1a3  setnbe  al
0x10044d1a6  cmp     ecx, eax
0x10044d1a8  setz    al
0x10044d1ab  jmp     short loc_10044D1BB
0x10044d1ad  movaps  xmm0, xmm2
0x10044d1b0  mulsd   xmm0, xmm5
0x10044d1b4  comisd  xmm3, xmm0
0x10044d1b8  setnb   al
0x10044d1bb  test    al, al
0x10044d1bd  jz      loc_10044D25F
0x10044d1c3  movsd   xmm9, qword ptr [rbx+90h]
0x10044d1cc  andps   xmm9, xmm6
0x10044d1d0  comisd  xmm9, xmm15
0x10044d1d5  divsd   xmm4, xmm5
0x10044d1d9  divsd   xmm3, xmm5
0x10044d1dd  jnb     short loc_10044D212
0x10044d1df  comisd  xmm7, xmm3
0x10044d1e3  ja      short loc_10044D212
0x10044d1e5  addsd   xmm3, xmm12
0x10044d1ea  movaps  xmm0, xmm2
0x10044d1ed  movaps  xmm1, xmm4
0x10044d1f0  addsd   xmm0, xmm12
0x10044d1f5  mulsd   xmm1, xmm4
0x10044d1f9  movaps  xmm8, xmm9
0x10044d1fd  mulsd   xmm3, xmm9
0x10044d202  divsd   xmm8, xmm0
0x10044d207  divsd   xmm1, xmm3
0x10044d20b  subsd   xmm8, xmm1
0x10044d210  jmp     short loc_10044D220
0x10044d212  movaps  xmm8, xmm3
0x10044d216  subsd   xmm8, xmm2
0x10044d21b  divsd   xmm8, xmm9
0x10044d220  mulsd   xmm8, qword ptr [rbx+28h]
0x10044d226  divsd   xmm4, xmm9
0x10044d22b  mulsd   xmm4, qword ptr [rbx+18h]
0x10044d230  addsd   xmm4, qword ptr [rbx+8]
0x10044d235  addsd   xmm4, xmm8
0x10044d23a  movaps  xmm0, xmm4
0x10044d23d  andps   xmm0, xmm6
0x10044d240  mulsd   xmm0, xmm11
0x10044d245  subsd   xmm4, xmm0
0x10044d249  movsd   xmm0, qword ptr [rdi]
0x10044d24d  comisd  xmm0, xmm4
0x10044d251  jbe     short loc_10044D25F
0x10044d253  movsd   qword ptr [rdi], xmm4
0x10044d257  movsd   xmm2, qword ptr [rbx+88h]
0x10044d25f  movsd   xmm3, qword ptr [rbx+20h]
0x10044d264  movaps  xmm0, xmm2
0x10044d267  movsd   xmm4, qword ptr [rbx+30h]
0x10044d26c  andps   xmm0, xmm6
0x10044d26f  comisd  xmm14, xmm0
0x10044d274  ja      short loc_10044D2B1
0x10044d276  movaps  xmm0, xmm2
0x10044d279  mulsd   xmm0, xmm4
0x10044d27d  comisd  xmm7, xmm0
0x10044d281  ja      short loc_10044D2B1
0x10044d283  movsd   xmm0, qword ptr [rbx+90h]
0x10044d28b  mov     ecx, edx
0x10044d28d  mov     eax, edx
0x10044d28f  andps   xmm0, xmm6
0x10044d292  mulsd   xmm0, xmm5
0x10044d296  movaps  xmm1, xmm3
0x10044d299  andps   xmm1, xmm6
0x10044d29c  comisd  xmm0, xmm1
0x10044d2a0  setnbe  cl
0x10044d2a3  comisd  xmm2, xmm7
0x10044d2a7  setnbe  al
0x10044d2aa  cmp     ecx, eax
0x10044d2ac  setz    al
0x10044d2af  jmp     short loc_10044D2BF
0x10044d2b1  movaps  xmm0, xmm2
0x10044d2b4  mulsd   xmm0, xmm5
0x10044d2b8  comisd  xmm4, xmm0
0x10044d2bc  setnb   al
0x10044d2bf  test    al, al
0x10044d2c1  jz      loc_10044D37D
0x10044d2c7  movsd   xmm11, qword ptr [rbx+90h]
0x10044d2d0  movaps  xmm10, xmm3
0x10044d2d4  andps   xmm11, xmm6
0x10044d2d8  movaps  xmm9, xmm4
0x10044d2dc  comisd  xmm11, xmm15
0x10044d2e1  divsd   xmm10, xmm5
0x10044d2e6  divsd   xmm9, xmm5
0x10044d2eb  jnb     short loc_10044D324
0x10044d2ed  comisd  xmm7, xmm9
0x10044d2f2  ja      short loc_10044D324
0x10044d2f4  addsd   xmm9, xmm12
0x10044d2f9  movaps  xmm0, xmm2
0x10044d2fc  movaps  xmm1, xmm10
0x10044d300  addsd   xmm0, xmm12
0x10044d305  mulsd   xmm1, xmm10
0x10044d30a  movaps  xmm8, xmm11
0x10044d30e  mulsd   xmm9, xmm11
0x10044d313  divsd   xmm8, xmm0
0x10044d318  divsd   xmm1, xmm9
0x10044d31d  subsd   xmm8, xmm1
0x10044d322  jmp     short loc_10044D332
0x10044d324  movaps  xmm8, xmm9
0x10044d328  subsd   xmm8, xmm2
0x10044d32d  divsd   xmm8, xmm11
0x10044d332  divsd   xmm10, xmm11
0x10044d337  movsd   xmm11, cs:__real@3d719799812dea11
0x10044d340  movaps  xmm0, xmm4
0x10044d343  mulsd   xmm10, xmm3
0x10044d348  mulsd   xmm0, xmm8
0x10044d34d  addsd   xmm10, qword ptr [rbx+10h]
0x10044d353  addsd   xmm10, xmm0
0x10044d358  movaps  xmm1, xmm10
0x10044d35c  andps   xmm1, xmm6
0x10044d35f  mulsd   xmm1, xmm11
0x10044d364  addsd   xmm1, xmm10
0x10044d369  comisd  xmm1, qword ptr [rdi+18h]
0x10044d36e  jbe     short loc_10044D37D
0x10044d370  movsd   qword ptr [rdi+18h], xmm1
0x10044d375  movsd   xmm2, qword ptr [rbx+88h]
0x10044d37d  movaps  xmm10, [rsp+0C8h+var_58]
0x10044d383  movaps  xmm0, xmm2
0x10044d386  movaps  xmm9, [rsp+0C8h+var_48]
0x10044d38f  andps   xmm0, xmm6
0x10044d392  comisd  xmm14, xmm0
0x10044d397  movaps  xmm14, [rsp+0C8h+var_98]
0x10044d39d  xorps   xmm3, xmm13
0x10044d3a1  xorps   xmm4, xmm13
0x10044d3a5  movaps  xmm13, [rsp+0C8h+var_88]
0x10044d3ab  ja      short loc_10044D3E6
0x10044d3ad  movaps  xmm0, xmm2
0x10044d3b0  mulsd   xmm0, xmm4
0x10044d3b4  comisd  xmm7, xmm0
0x10044d3b8  ja      short loc_10044D3E6
0x10044d3ba  movsd   xmm0, qword ptr [rbx+90h]
0x10044d3c2  mov     eax, edx
0x10044d3c4  andps   xmm0, xmm6
0x10044d3c7  movaps  xmm1, xmm3
0x10044d3ca  mulsd   xmm0, xmm5
0x10044d3ce  andps   xmm1, xmm6
0x10044d3d1  comisd  xmm0, xmm1
0x10044d3d5  setnbe  al
0x10044d3d8  comisd  xmm2, xmm7
0x10044d3dc  setnbe  dl
0x10044d3df  cmp     eax, edx
0x10044d3e1  setz    al
0x10044d3e4  jmp     short loc_10044D3F4
0x10044d3e6  movaps  xmm0, xmm2
0x10044d3e9  mulsd   xmm0, xmm5
0x10044d3ed  comisd  xmm4, xmm0
0x10044d3f1  setnb   al
0x10044d3f4  test    al, al
0x10044d3f6  jz      loc_10044D489
0x10044d3fc  movsd   xmm8, qword ptr [rbx+90h]
0x10044d405  andps   xmm8, xmm6
0x10044d409  comisd  xmm8, xmm15
0x10044d40e  divsd   xmm3, xmm5
0x10044d412  divsd   xmm4, xmm5
0x10044d416  jnb     short loc_10044D446
0x10044d418  comisd  xmm7, xmm4
0x10044d41c  ja      short loc_10044D446
0x10044d41e  addsd   xmm4, xmm12
0x10044d423  movaps  xmm0, xmm3
0x10044d426  addsd   xmm2, xmm12
0x10044d42b  mulsd   xmm0, xmm3
0x10044d42f  movaps  xmm1, xmm8
0x10044d433  mulsd   xmm4, xmm8
0x10044d438  divsd   xmm1, xmm2
0x10044d43c  divsd   xmm0, xmm4
0x10044d440  subsd   xmm1, xmm0
0x10044d444  jmp     short loc_10044D452
0x10044d446  movaps  xmm1, xmm4
0x10044d449  subsd   xmm1, xmm2
0x10044d44d  divsd   xmm1, xmm8
0x10044d452  mulsd   xmm1, qword ptr [rbx+30h]
0x10044d457  divsd   xmm3, xmm8
0x10044d45c  mulsd   xmm3, qword ptr [rbx+20h]
0x10044d461  addsd   xmm3, qword ptr [rbx+10h]
0x10044d466  addsd   xmm3, xmm1
0x10044d46a  movaps  xmm0, xmm3
0x10044d46d  andps   xmm0, xmm6
0x10044d470  mulsd   xmm0, xmm11
0x10044d475  subsd   xmm3, xmm0
0x10044d479  movsd   xmm0, qword ptr [rdi+10h]
0x10044d47e  comisd  xmm0, xmm3
  ... truncated ...
```
