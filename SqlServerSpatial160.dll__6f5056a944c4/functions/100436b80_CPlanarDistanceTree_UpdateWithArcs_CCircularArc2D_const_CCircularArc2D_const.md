# CPlanarDistanceTree::UpdateWithArcs(CCircularArc2D const &,CCircularArc2D const &)

- ea: `0x100436b80`
- end: `0x100436fe2`
- name: `?UpdateWithArcs@CPlanarDistanceTree@@IEAAXAEBVCCircularArc2D@@0@Z`
- size: `1122`
- prototype: `void __fastcall(CPlanarDistanceTree *__hidden this, const struct CCircularArc2D *, const struct CCircularArc2D *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x1004364d0`

## callees

- `0x100436b80`
- `0x10044bf00`
- `0x10044c8c0`

## pseudocode

```c
void __fastcall CPlanarDistanceTree::UpdateWithArcs(
        CPlanarDistanceTree *this,
        const struct CCircularArc2D *a2,
        const struct CCircularArc2D *a3)
{
  __int64 v6; // rax
  double v7; // xmm1_8
  __int128 v8; // xmm0
  __int128 v9; // xmm1
  char PointNearestToPoint; // al
  __int64 v11; // rcx
  double v12; // xmm1_8
  __int128 v13; // xmm1
  double v14; // xmm2_8
  double v15; // xmm3_8
  double v16; // xmm1_8
  double v17; // xmm1_8
  char v18; // al
  __int64 v19; // rcx
  double v20; // xmm1_8
  __int128 v21; // xmm1
  double v22; // xmm2_8
  double v23; // xmm3_8
  double v24; // xmm1_8
  double v25; // xmm1_8
  char v26; // al
  __int64 v27; // rcx
  double v28; // xmm1_8
  double v29; // xmm2_8
  double v30; // xmm2_8
  __int128 v31; // xmm0
  double v32; // xmm3_8
  double v33; // xmm2_8
  char v34; // al
  __int64 v35; // rcx
  double v36; // xmm1_8
  double v37; // xmm2_8
  double v38; // xmm2_8
  __int128 v39; // xmm0
  double v40; // xmm3_8
  double v41; // xmm1_8
  __int128 v42; // [rsp+20h] [rbp-20h] BYREF
  __int128 v43; // [rsp+30h] [rbp-10h] BYREF

  if ( (unsigned __int8)CCircularArc2D::GetPointNearestToArc(a2, a3, &v42, &v43) )
  {
    v6 = *((_QWORD *)this + 38);
    v7 = (*((double *)&v43 + 1) - *((double *)&v42 + 1)) * (*((double *)&v43 + 1) - *((double *)&v42 + 1))
       + (*(double *)&v43 - *(double *)&v42) * (*(double *)&v43 - *(double *)&v42);
    if ( *(double *)v6 > v7 )
    {
      v8 = v42;
      *(double *)v6 = v7;
      v9 = v43;
      *(_OWORD *)(v6 + 8) = v8;
      *(_OWORD *)(v6 + 24) = v9;
    }
    return;
  }
  PointNearestToPoint = CCircularArc2D::GetPointNearestToPoint(a3, (char *)a2 + 88, &v43);
  v11 = *((_QWORD *)this + 38);
  if ( PointNearestToPoint )
  {
    v12 = (*((double *)&v43 + 1) - *((double *)a2 + 12)) * (*((double *)&v43 + 1) - *((double *)a2 + 12))
        + (*(double *)&v43 - *((double *)a2 + 11)) * (*(double *)&v43 - *((double *)a2 + 11));
    if ( *(double *)v11 > v12 )
    {
      *(double *)v11 = v12;
      v13 = v43;
      *(_OWORD *)(v11 + 8) = *(_OWORD *)((char *)a2 + 88);
      *(_OWORD *)(v11 + 24) = v13;
    }
  }
  else
  {
    v14 = *((double *)a2 + 11);
    v15 = *((double *)a2 + 12);
    v16 = (*((double *)a3 + 11) - v14) * (*((double *)a3 + 11) - v14)
        + (*((double *)a3 + 12) - v15) * (*((double *)a3 + 12) - v15);
    if ( *(double *)v11 > v16 )
    {
      *(double *)v11 = v16;
      *(_OWORD *)(v11 + 8) = *(_OWORD *)((char *)a2 + 88);
      *(_OWORD *)(v11 + 24) = *(_OWORD *)((char *)a3 + 88);
      v11 = *((_QWORD *)this + 38);
      v14 = *((double *)a2 + 11);
      v15 = *((double *)a2 + 12);
    }
    v17 = (*((double *)a3 + 13) - v14) * (*((double *)a3 + 13) - v14)
        + (*((double *)a3 + 14) - v15) * (*((double *)a3 + 14) - v15);
    if ( *(double *)v11 > v17 )
    {
      *(double *)v11 = v17;
      *(_OWORD *)(v11 + 8) = *(_OWORD *)((char *)a2 + 88);
      *(_OWORD *)(v11 + 24) = *(_OWORD *)((char *)a3 + 104);
    }
  }
  v18 = CCircularArc2D::GetPointNearestToPoint(a3, (char *)a2 + 104, &v43);
  v19 = *((_QWORD *)this + 38);
  if ( v18 )
  {
    v20 = (*((double *)&v43 + 1) - *((double *)a2 + 14)) * (*((double *)&v43 + 1) - *((double *)a2 + 14))
        + (*(double *)&v43 - *((double *)a2 + 13)) * (*(double *)&v43 - *((double *)a2 + 13));
    if ( *(double *)v19 > v20 )
    {
      *(double *)v19 = v20;
      v21 = v43;
      *(_OWORD *)(v19 + 8) = *(_OWORD *)((char *)a2 + 104);
      *(_OWORD *)(v19 + 24) = v21;
    }
  }
  else
  {
    v22 = *((double *)a2 + 13);
    v23 = *((double *)a2 + 14);
    v24 = (*((double *)a3 + 11) - v22) * (*((double *)a3 + 11) - v22)
        + (*((double *)a3 + 12) - v23) * (*((double *)a3 + 12) - v23);
    if ( *(double *)v19 > v24 )
    {
      *(double *)v19 = v24;
      *(_OWORD *)(v19 + 8) = *(_OWORD *)((char *)a2 + 104);
      *(_OWORD *)(v19 + 24) = *(_OWORD *)((char *)a3 + 88);
      v19 = *((_QWORD *)this + 38);
      v22 = *((double *)a2 + 13);
      v23 = *((double *)a2 + 14);
    }
    v25 = (*((double *)a3 + 14) - v23) * (*((double *)a3 + 14) - v23)
        + (*((double *)a3 + 13) - v22) * (*((double *)a3 + 13) - v22);
    if ( *(double *)v19 > v25 )
    {
      *(double *)v19 = v25;
      *(_OWORD *)(v19 + 8) = *(_OWORD *)((char *)a2 + 104);
      *(_OWORD *)(v19 + 24) = *(_OWORD *)((char *)a3 + 104);
    }
  }
  v26 = CCircularArc2D::GetPointNearestToPoint(a2, (char *)a3 + 88, &v43);
  v27 = *((_QWORD *)this + 38);
  v28 = *((double *)a3 + 11);
  v29 = *((double *)a3 + 12);
  if ( v26 )
  {
    v30 = (v29 - *((double *)&v43 + 1)) * (v29 - *((double *)&v43 + 1))
        + (v28 - *(double *)&v43) * (v28 - *(double *)&v43);
    if ( *(double *)v27 <= v30 )
      goto LABEL_26;
    v31 = v43;
    *(double *)v27 = v30;
    goto LABEL_25;
  }
  v32 = (v29 - *((double *)a2 + 12)) * (v29 - *((double *)a2 + 12))
      + (v28 - *((double *)a2 + 11)) * (v28 - *((double *)a2 + 11));
  if ( *(double *)v27 > v32 )
  {
    *(double *)v27 = v32;
    *(_OWORD *)(v27 + 8) = *(_OWORD *)((char *)a2 + 88);
    *(_OWORD *)(v27 + 24) = *(_OWORD *)((char *)a3 + 88);
    v27 = *((_QWORD *)this + 38);
    v28 = *((double *)a3 + 11);
    v29 = *((double *)a3 + 12);
  }
  v33 = (v29 - *((double *)a2 + 14)) * (v29 - *((double *)a2 + 14))
      + (v28 - *((double *)a2 + 13)) * (v28 - *((double *)a2 + 13));
  if ( *(double *)v27 > v33 )
  {
    *(double *)v27 = v33;
    v31 = *(_OWORD *)((char *)a2 + 104);
LABEL_25:
    *(_OWORD *)(v27 + 8) = v31;
    *(_OWORD *)(v27 + 24) = *(_OWORD *)((char *)a3 + 88);
  }
LABEL_26:
  v34 = CCircularArc2D::GetPointNearestToPoint(a2, (char *)a3 + 104, &v43);
  v35 = *((_QWORD *)this + 38);
  v36 = *((double *)a3 + 13);
  v37 = *((double *)a3 + 14);
  if ( v34 )
  {
    v38 = (v37 - *((double *)&v43 + 1)) * (v37 - *((double *)&v43 + 1))
        + (v36 - *(double *)&v43) * (v36 - *(double *)&v43);
    if ( *(double *)v35 <= v38 )
      return;
    v39 = v43;
    *(double *)v35 = v38;
    goto LABEL_33;
  }
  v40 = (v36 - *((double *)a2 + 11)) * (v36 - *((double *)a2 + 11))
      + (v37 - *((double *)a2 + 12)) * (v37 - *((double *)a2 + 12));
  if ( *(double *)v35 > v40 )
  {
    *(double *)v35 = v40;
    *(_OWORD *)(v35 + 8) = *(_OWORD *)((char *)a2 + 88);
    *(_OWORD *)(v35 + 24) = *(_OWORD *)((char *)a3 + 104);
    v35 = *((_QWORD *)this + 38);
    v36 = *((double *)a3 + 13);
    v37 = *((double *)a3 + 14);
  }
  v41 = (v36 - *((double *)a2 + 13)) * (v36 - *((double *)a2 + 13))
      + (v37 - *((double *)a2 + 14)) * (v37 - *((double *)a2 + 14));
  if ( *(double *)v35 > v41 )
  {
    *(double *)v35 = v41;
    v39 = *(_OWORD *)((char *)a2 + 104);
LABEL_33:
    *(_OWORD *)(v35 + 8) = v39;
    *(_OWORD *)(v35 + 24) = *(_OWORD *)((char *)a3 + 104);
  }
}

```

## disassembly

```asm
0x100436b80  mov     [rsp-18h+arg_18], rdi
0x100436b85  push    rbp
0x100436b86  push    r13
0x100436b88  push    r15
0x100436b8a  mov     rbp, rsp
0x100436b8d  sub     rsp, 40h
0x100436b91  mov     rdi, r8
0x100436b94  lea     r9, [rbp+var_10]
0x100436b98  mov     r13, rdx
0x100436b9b  lea     r8, [rbp+var_20]
0x100436b9f  mov     r15, rcx
0x100436ba2  mov     rdx, rdi
0x100436ba5  mov     rcx, r13
0x100436ba8  call    ?GetPointNearestToArc@CCircularArc2D@@QEBA_NAEBV1@AEAV?$CMglPoint@N@@1@Z; CCircularArc2D::GetPointNearestToArc(CCircularArc2D const &,CMglPoint<double> &,CMglPoint<double> &)
0x100436bad  test    al, al
0x100436baf  jz      short loc_100436C09
0x100436bb1  movsd   xmm0, qword ptr [rbp+var_10]
0x100436bb6  subsd   xmm0, qword ptr [rbp+var_20]
0x100436bbb  movsd   xmm1, qword ptr [rbp+var_10+8]
0x100436bc0  subsd   xmm1, qword ptr [rbp+var_20+8]
0x100436bc5  mov     rax, [r15+130h]
0x100436bcc  mulsd   xmm0, xmm0
0x100436bd0  mulsd   xmm1, xmm1
0x100436bd4  addsd   xmm1, xmm0
0x100436bd8  movsd   xmm0, qword ptr [rax]
0x100436bdc  comisd  xmm0, xmm1
0x100436be0  jbe     loc_100436FD3
0x100436be6  movups  xmm0, [rbp+var_20]
0x100436bea  movsd   qword ptr [rax], xmm1
0x100436bee  movups  xmm1, [rbp+var_10]
0x100436bf2  movups  xmmword ptr [rax+8], xmm0
0x100436bf6  movups  xmmword ptr [rax+18h], xmm1
0x100436bfa  mov     rdi, [rsp+40h+arg_18]
0x100436bff  add     rsp, 40h
0x100436c03  pop     r15
0x100436c05  pop     r13
0x100436c07  pop     rbp
0x100436c08  retn
0x100436c09  mov     [rsp+40h+arg_0], rbx
0x100436c0e  lea     r8, [rbp+var_10]
0x100436c12  mov     [rsp+40h+arg_8], rsi
0x100436c17  lea     rdx, [r13+58h]
0x100436c1b  mov     rcx, rdi
0x100436c1e  mov     [rsp+40h+arg_10], r14
0x100436c23  call    ?GetPointNearestToPoint@CCircularArc2D@@QEBA_NAEBV?$CMglPoint@N@@AEAV2@@Z; CCircularArc2D::GetPointNearestToPoint(CMglPoint<double> const &,CMglPoint<double> &)
0x100436c28  mov     rcx, [r15+130h]
0x100436c2f  test    al, al
0x100436c31  jz      short loc_100436C7D
0x100436c33  movsd   xmm0, qword ptr [rbp+var_10]
0x100436c38  subsd   xmm0, qword ptr [r13+58h]
0x100436c3e  movsd   xmm1, qword ptr [rbp+var_10+8]
0x100436c43  subsd   xmm1, qword ptr [r13+60h]
0x100436c49  mulsd   xmm0, xmm0
0x100436c4d  mulsd   xmm1, xmm1
0x100436c51  addsd   xmm1, xmm0
0x100436c55  movsd   xmm0, qword ptr [rcx]
0x100436c59  comisd  xmm0, xmm1
0x100436c5d  jbe     loc_100436D16
0x100436c63  movsd   qword ptr [rcx], xmm1
0x100436c67  movups  xmm0, xmmword ptr [r13+58h]
0x100436c6c  movups  xmm1, [rbp+var_10]
0x100436c70  movups  xmmword ptr [rcx+8], xmm0
0x100436c74  movups  xmmword ptr [rcx+18h], xmm1
0x100436c78  jmp     loc_100436D16
0x100436c7d  movsd   xmm0, qword ptr [rdi+60h]
0x100436c82  movsd   xmm2, qword ptr [r13+58h]
0x100436c88  movsd   xmm1, qword ptr [rdi+58h]
0x100436c8d  movsd   xmm3, qword ptr [r13+60h]
0x100436c93  subsd   xmm1, xmm2
0x100436c97  subsd   xmm0, xmm3
0x100436c9b  mulsd   xmm1, xmm1
0x100436c9f  mulsd   xmm0, xmm0
0x100436ca3  addsd   xmm1, xmm0
0x100436ca7  movsd   xmm0, qword ptr [rcx]
0x100436cab  comisd  xmm0, xmm1
0x100436caf  jbe     short loc_100436CD9
0x100436cb1  movsd   qword ptr [rcx], xmm1
0x100436cb5  movups  xmm0, xmmword ptr [r13+58h]
0x100436cba  movups  xmmword ptr [rcx+8], xmm0
0x100436cbe  movups  xmm0, xmmword ptr [rdi+58h]
0x100436cc2  movups  xmmword ptr [rcx+18h], xmm0
0x100436cc6  mov     rcx, [r15+130h]
0x100436ccd  movsd   xmm2, qword ptr [r13+58h]
0x100436cd3  movsd   xmm3, qword ptr [r13+60h]
0x100436cd9  movsd   xmm0, qword ptr [rdi+70h]
0x100436cde  movsd   xmm1, qword ptr [rdi+68h]
0x100436ce3  subsd   xmm0, xmm3
0x100436ce7  subsd   xmm1, xmm2
0x100436ceb  mulsd   xmm0, xmm0
0x100436cef  mulsd   xmm1, xmm1
0x100436cf3  addsd   xmm1, xmm0
0x100436cf7  movsd   xmm0, qword ptr [rcx]
0x100436cfb  comisd  xmm0, xmm1
0x100436cff  jbe     short loc_100436D16
0x100436d01  movsd   qword ptr [rcx], xmm1
0x100436d05  movups  xmm0, xmmword ptr [r13+58h]
0x100436d0a  movups  xmmword ptr [rcx+8], xmm0
0x100436d0e  movups  xmm0, xmmword ptr [rdi+68h]
0x100436d12  movups  xmmword ptr [rcx+18h], xmm0
0x100436d16  lea     r8, [rbp+var_10]
0x100436d1a  mov     rcx, rdi
0x100436d1d  lea     rdx, [r13+68h]
0x100436d21  call    ?GetPointNearestToPoint@CCircularArc2D@@QEBA_NAEBV?$CMglPoint@N@@AEAV2@@Z; CCircularArc2D::GetPointNearestToPoint(CMglPoint<double> const &,CMglPoint<double> &)
0x100436d26  mov     rcx, [r15+130h]
0x100436d2d  test    al, al
0x100436d2f  jz      short loc_100436D7B
0x100436d31  movsd   xmm0, qword ptr [rbp+var_10]
0x100436d36  subsd   xmm0, qword ptr [r13+68h]
0x100436d3c  movsd   xmm1, qword ptr [rbp+var_10+8]
0x100436d41  subsd   xmm1, qword ptr [r13+70h]
0x100436d47  mulsd   xmm0, xmm0
0x100436d4b  mulsd   xmm1, xmm1
0x100436d4f  addsd   xmm1, xmm0
0x100436d53  movsd   xmm0, qword ptr [rcx]
0x100436d57  comisd  xmm0, xmm1
0x100436d5b  jbe     loc_100436E14
0x100436d61  movsd   qword ptr [rcx], xmm1
0x100436d65  movups  xmm0, xmmword ptr [r13+68h]
0x100436d6a  movups  xmm1, [rbp+var_10]
0x100436d6e  movups  xmmword ptr [rcx+8], xmm0
0x100436d72  movups  xmmword ptr [rcx+18h], xmm1
0x100436d76  jmp     loc_100436E14
0x100436d7b  movsd   xmm0, qword ptr [rdi+60h]
0x100436d80  movsd   xmm2, qword ptr [r13+68h]
0x100436d86  movsd   xmm1, qword ptr [rdi+58h]
0x100436d8b  movsd   xmm3, qword ptr [r13+70h]
0x100436d91  subsd   xmm1, xmm2
0x100436d95  subsd   xmm0, xmm3
0x100436d99  mulsd   xmm1, xmm1
0x100436d9d  mulsd   xmm0, xmm0
0x100436da1  addsd   xmm1, xmm0
0x100436da5  movsd   xmm0, qword ptr [rcx]
0x100436da9  comisd  xmm0, xmm1
0x100436dad  jbe     short loc_100436DD7
0x100436daf  movsd   qword ptr [rcx], xmm1
0x100436db3  movups  xmm0, xmmword ptr [r13+68h]
0x100436db8  movups  xmmword ptr [rcx+8], xmm0
0x100436dbc  movups  xmm0, xmmword ptr [rdi+58h]
0x100436dc0  movups  xmmword ptr [rcx+18h], xmm0
0x100436dc4  mov     rcx, [r15+130h]
0x100436dcb  movsd   xmm2, qword ptr [r13+68h]
0x100436dd1  movsd   xmm3, qword ptr [r13+70h]
0x100436dd7  movsd   xmm0, qword ptr [rdi+68h]
0x100436ddc  movsd   xmm1, qword ptr [rdi+70h]
0x100436de1  subsd   xmm0, xmm2
0x100436de5  subsd   xmm1, xmm3
0x100436de9  mulsd   xmm0, xmm0
0x100436ded  mulsd   xmm1, xmm1
0x100436df1  addsd   xmm1, xmm0
0x100436df5  movsd   xmm0, qword ptr [rcx]
0x100436df9  comisd  xmm0, xmm1
0x100436dfd  jbe     short loc_100436E14
0x100436dff  movsd   qword ptr [rcx], xmm1
0x100436e03  movups  xmm0, xmmword ptr [r13+68h]
0x100436e08  movups  xmmword ptr [rcx+8], xmm0
0x100436e0c  movups  xmm0, xmmword ptr [rdi+68h]
0x100436e10  movups  xmmword ptr [rcx+18h], xmm0
0x100436e14  lea     r8, [rbp+var_10]
0x100436e18  mov     rcx, r13
0x100436e1b  lea     rdx, [rdi+58h]
0x100436e1f  call    ?GetPointNearestToPoint@CCircularArc2D@@QEBA_NAEBV?$CMglPoint@N@@AEAV2@@Z; CCircularArc2D::GetPointNearestToPoint(CMglPoint<double> const &,CMglPoint<double> &)
0x100436e24  mov     rcx, [r15+130h]
0x100436e2b  movsd   xmm1, qword ptr [rdi+58h]
0x100436e30  movsd   xmm2, qword ptr [rdi+60h]
0x100436e35  test    al, al
0x100436e37  jz      short loc_100436E67
0x100436e39  subsd   xmm2, qword ptr [rbp+var_10+8]
0x100436e3e  subsd   xmm1, qword ptr [rbp+var_10]
0x100436e43  movsd   xmm0, qword ptr [rcx]
0x100436e47  mulsd   xmm2, xmm2
0x100436e4b  mulsd   xmm1, xmm1
0x100436e4f  addsd   xmm2, xmm1
0x100436e53  comisd  xmm0, xmm2
0x100436e57  jbe     loc_100436EEC
0x100436e5d  movups  xmm0, [rbp+var_10]
0x100436e61  movsd   qword ptr [rcx], xmm2
0x100436e65  jmp     short loc_100436EE0
0x100436e67  movaps  xmm0, xmm1
0x100436e6a  movaps  xmm3, xmm2
0x100436e6d  subsd   xmm0, qword ptr [r13+58h]
0x100436e73  subsd   xmm3, qword ptr [r13+60h]
0x100436e79  mulsd   xmm0, xmm0
0x100436e7d  mulsd   xmm3, xmm3
0x100436e81  addsd   xmm3, xmm0
0x100436e85  movsd   xmm0, qword ptr [rcx]
0x100436e89  comisd  xmm0, xmm3
0x100436e8d  jbe     short loc_100436EB5
0x100436e8f  movsd   qword ptr [rcx], xmm3
0x100436e93  movups  xmm0, xmmword ptr [r13+58h]
0x100436e98  movups  xmmword ptr [rcx+8], xmm0
0x100436e9c  movups  xmm0, xmmword ptr [rdi+58h]
0x100436ea0  movups  xmmword ptr [rcx+18h], xmm0
0x100436ea4  mov     rcx, [r15+130h]
0x100436eab  movsd   xmm1, qword ptr [rdi+58h]
0x100436eb0  movsd   xmm2, qword ptr [rdi+60h]
0x100436eb5  subsd   xmm2, qword ptr [r13+70h]
0x100436ebb  subsd   xmm1, qword ptr [r13+68h]
0x100436ec1  movsd   xmm0, qword ptr [rcx]
0x100436ec5  mulsd   xmm2, xmm2
0x100436ec9  mulsd   xmm1, xmm1
0x100436ecd  addsd   xmm2, xmm1
0x100436ed1  comisd  xmm0, xmm2
0x100436ed5  jbe     short loc_100436EEC
0x100436ed7  movsd   qword ptr [rcx], xmm2
0x100436edb  movups  xmm0, xmmword ptr [r13+68h]
0x100436ee0  movups  xmmword ptr [rcx+8], xmm0
0x100436ee4  movups  xmm0, xmmword ptr [rdi+58h]
0x100436ee8  movups  xmmword ptr [rcx+18h], xmm0
0x100436eec  lea     r8, [rbp+var_10]
0x100436ef0  mov     rcx, r13
0x100436ef3  lea     rdx, [rdi+68h]
0x100436ef7  call    ?GetPointNearestToPoint@CCircularArc2D@@QEBA_NAEBV?$CMglPoint@N@@AEAV2@@Z; CCircularArc2D::GetPointNearestToPoint(CMglPoint<double> const &,CMglPoint<double> &)
0x100436efc  mov     rcx, [r15+130h]
0x100436f03  movsd   xmm1, qword ptr [rdi+68h]
0x100436f08  mov     r14, [rsp+40h+arg_10]
0x100436f0d  movsd   xmm2, qword ptr [rdi+70h]
0x100436f12  test    al, al
0x100436f14  jz      short loc_100436F44
0x100436f16  subsd   xmm2, qword ptr [rbp+var_10+8]
0x100436f1b  subsd   xmm1, qword ptr [rbp+var_10]
0x100436f20  movsd   xmm0, qword ptr [rcx]
0x100436f24  mulsd   xmm2, xmm2
0x100436f28  mulsd   xmm1, xmm1
0x100436f2c  addsd   xmm2, xmm1
0x100436f30  comisd  xmm0, xmm2
0x100436f34  jbe     loc_100436FC9
0x100436f3a  movups  xmm0, [rbp+var_10]
0x100436f3e  movsd   qword ptr [rcx], xmm2
0x100436f42  jmp     short loc_100436FBD
0x100436f44  movaps  xmm0, xmm2
0x100436f47  movaps  xmm3, xmm1
0x100436f4a  subsd   xmm3, qword ptr [r13+58h]
0x100436f50  subsd   xmm0, qword ptr [r13+60h]
0x100436f56  mulsd   xmm3, xmm3
0x100436f5a  mulsd   xmm0, xmm0
0x100436f5e  addsd   xmm3, xmm0
0x100436f62  movsd   xmm0, qword ptr [rcx]
0x100436f66  comisd  xmm0, xmm3
0x100436f6a  jbe     short loc_100436F92
0x100436f6c  movsd   qword ptr [rcx], xmm3
0x100436f70  movups  xmm0, xmmword ptr [r13+58h]
0x100436f75  movups  xmmword ptr [rcx+8], xmm0
0x100436f79  movups  xmm0, xmmword ptr [rdi+68h]
0x100436f7d  movups  xmmword ptr [rcx+18h], xmm0
0x100436f81  mov     rcx, [r15+130h]
0x100436f88  movsd   xmm1, qword ptr [rdi+68h]
0x100436f8d  movsd   xmm2, qword ptr [rdi+70h]
0x100436f92  subsd   xmm1, qword ptr [r13+68h]
0x100436f98  subsd   xmm2, qword ptr [r13+70h]
0x100436f9e  movsd   xmm0, qword ptr [rcx]
0x100436fa2  mulsd   xmm1, xmm1
0x100436fa6  mulsd   xmm2, xmm2
0x100436faa  addsd   xmm1, xmm2
0x100436fae  comisd  xmm0, xmm1
0x100436fb2  jbe     short loc_100436FC9
0x100436fb4  movsd   qword ptr [rcx], xmm1
0x100436fb8  movups  xmm0, xmmword ptr [r13+68h]
0x100436fbd  movups  xmmword ptr [rcx+8], xmm0
0x100436fc1  movups  xmm0, xmmword ptr [rdi+68h]
0x100436fc5  movups  xmmword ptr [rcx+18h], xmm0
0x100436fc9  mov     rbx, [rsp+40h+arg_0]
0x100436fce  mov     rsi, [rsp+40h+arg_8]
0x100436fd3  mov     rdi, [rsp+40h+arg_18]
0x100436fd8  add     rsp, 40h
0x100436fdc  pop     r15
0x100436fde  pop     r13
0x100436fe0  pop     rbp
0x100436fe1  retn
```
