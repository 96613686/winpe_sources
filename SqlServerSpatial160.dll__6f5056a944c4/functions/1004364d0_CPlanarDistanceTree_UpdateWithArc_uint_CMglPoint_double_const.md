# CPlanarDistanceTree::UpdateWithArc(uint,CMglPoint<double> const *)

- ea: `0x1004364d0`
- end: `0x1004366f7`
- name: `?UpdateWithArc@CPlanarDistanceTree@@IEAAXIPEBV?$CMglPoint@N@@@Z`
- size: `551`
- prototype: `__int64 __fastcall(CPlanarDistanceTree *this)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x100435fb0`

## callees

- `0x100420ae0`
- `0x1004364d0`
- `0x100436700`
- `0x100436970`
- `0x100436b80`
- `0x10044c120`
- `0x100468a30`

## pseudocode

```c
void __fastcall CPlanarDistanceTree::UpdateWithArc(CPlanarDistanceTree *this, int a2, __int128 *a3)
{
  CPlanarDistanceTree *v4; // rbx
  int v5; // edx
  int v6; // edx
  __int128 v7; // xmm0
  __int64 v8; // rdi
  __int64 v9; // r9
  __int64 v10; // rax
  double v11; // xmm1_8
  __int128 v12; // xmm0
  __int128 v13; // xmm1
  __int64 v14; // r9
  __int64 v15; // r8
  __int128 *v16; // rdx
  __int64 v17; // rax
  double v18; // xmm1_8
  __int128 v19; // xmm0
  __int128 v20; // xmm1
  __int128 v21; // [rsp+20h] [rbp-E0h] BYREF
  __int128 v22; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v23; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v24; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v25[22]; // [rsp+60h] [rbp-A0h] BYREF

  v4 = this;
  v5 = a2 - 1;
  if ( !v5 )
  {
    v15 = *((_QWORD *)this + 37);
    v16 = a3;
    goto LABEL_14;
  }
  v6 = v5 - 1;
  if ( v6 )
  {
    if ( v6 != 1 )
      return;
    v25[0] = &CGeodeticCircularArc::`vftable';
    CCircularArc<CMglPoint<double>>::ConstructFrom3Points(v25, a3, a3 + 1);
    v25[0] = &CGeodeticCircularArc::`vftable';
    if ( *(double *)&v25[16] != 0.0 )
    {
      CPlanarDistanceTree::UpdateWithArcs(
        v4,
        *((const struct CCircularArc2D **)v4 + 37),
        (const struct CCircularArc2D *)v25);
      return;
    }
    v23 = *a3;
    v7 = a3[2];
    v8 = *((_QWORD *)v4 + 37);
    v24 = v7;
    if ( (unsigned __int8)CCircularArc2D::GetPointNearestToLineSegment(v8, &v23, &v21, &v22) )
    {
      v10 = *((_QWORD *)v4 + 38);
      v11 = (*((double *)&v22 + 1) - *((double *)&v21 + 1)) * (*((double *)&v22 + 1) - *((double *)&v21 + 1))
          + (*(double *)&v22 - *(double *)&v21) * (*(double *)&v22 - *(double *)&v21);
      if ( *(double *)v10 > v11 )
      {
        v12 = v21;
        *(double *)v10 = v11;
        v13 = v22;
        *(_OWORD *)(v10 + 8) = v12;
        *(_OWORD *)(v10 + 24) = v13;
      }
      return;
    }
    goto LABEL_8;
  }
  v8 = *((_QWORD *)this + 37);
  v23 = *a3;
  v24 = a3[1];
  if ( !(unsigned __int8)CCircularArc2D::GetPointNearestToLineSegment(v8, &v23, &v22, &v21) )
  {
LABEL_8:
    LOBYTE(v9) = 1;
    CPlanarDistanceTree::UpdateWithPointAndLine(v4, v8 + 88, &v23, v9);
    LOBYTE(v14) = 1;
    CPlanarDistanceTree::UpdateWithPointAndLine(v4, v8 + 104, &v23, v14);
    CPlanarDistanceTree::UpdateWithPointAndArc(v4, &v23, v8, 0);
    v15 = v8;
    v16 = &v24;
    this = v4;
LABEL_14:
    CPlanarDistanceTree::UpdateWithPointAndArc(this, v16, v15, 0);
    return;
  }
  v17 = *((_QWORD *)v4 + 38);
  v18 = (*((double *)&v21 + 1) - *((double *)&v22 + 1)) * (*((double *)&v21 + 1) - *((double *)&v22 + 1))
      + (*(double *)&v21 - *(double *)&v22) * (*(double *)&v21 - *(double *)&v22);
  if ( *(double *)v17 > v18 )
  {
    v19 = v22;
    *(double *)v17 = v18;
    v20 = v21;
    *(_OWORD *)(v17 + 8) = v19;
    *(_OWORD *)(v17 + 24) = v20;
  }
}

```

## disassembly

```asm
0x1004364d0  mov     [rsp-8+arg_8], rbx
0x1004364d5  mov     [rsp-8+arg_18], rdi
0x1004364da  push    rbp
0x1004364db  lea     rbp, [rsp-20h]
0x1004364e0  sub     rsp, 120h
0x1004364e7  mov     rax, cs:__security_cookie
0x1004364ee  xor     rax, rsp
0x1004364f1  mov     [rbp+20h+var_10], rax
0x1004364f5  mov     rdi, r8
0x1004364f8  mov     rbx, rcx
0x1004364fb  sub     edx, 1
0x1004364fe  jz      loc_1004366C4
0x100436504  sub     edx, 1
0x100436507  jz      loc_10043663E
0x10043650d  cmp     edx, 1
0x100436510  jnz     loc_1004366D6
0x100436516  lea     rax, ??_7CGeodeticCircularArc@@6B@; const CGeodeticCircularArc::`vftable'
0x10043651d  add     r8, 10h
0x100436521  mov     rdx, rdi
0x100436524  mov     [rsp+120h+var_C0], rax
0x100436529  lea     rcx, [rsp+120h+var_C0]
0x10043652e  call    ?ConstructFrom3Points@?$CCircularArc@V?$CMglPoint@N@@@@QEAAXAEBV?$CMglPoint@N@@PEBV2@@Z; CCircularArc<CMglPoint<double>>::ConstructFrom3Points(CMglPoint<double> const &,CMglPoint<double> const *)
0x100436533  xorps   xmm0, xmm0
0x100436536  lea     rax, ??_7CGeodeticCircularArc@@6B@; const CGeodeticCircularArc::`vftable'
0x10043653d  ucomisd xmm0, [rbp+20h+var_40]
0x100436542  mov     [rsp+120h+var_C0], rax
0x100436547  jp      loc_100436625
0x10043654d  jnz     loc_100436625
0x100436553  movups  xmm0, xmmword ptr [rdi]
0x100436556  lea     r9, [rsp+120h+var_F0]
0x10043655b  lea     r8, [rsp+120h+var_100]
0x100436560  movups  [rsp+120h+var_E0], xmm0
0x100436565  lea     rdx, [rsp+120h+var_E0]
0x10043656a  movups  xmm0, xmmword ptr [rdi+20h]
0x10043656e  mov     rdi, [rbx+128h]
0x100436575  mov     rcx, rdi
0x100436578  movups  [rsp+120h+var_D0], xmm0
0x10043657d  call    ?GetPointNearestToLineSegment@CCircularArc2D@@QEBA_NAEBV?$CLineSegment@V?$CMglPoint@N@@@@AEAV?$CMglPoint@N@@1@Z; CCircularArc2D::GetPointNearestToLineSegment(CLineSegment<CMglPoint<double>> const &,CMglPoint<double> &,CMglPoint<double> &)
0x100436582  test    al, al
0x100436584  jz      short loc_1004365DA
0x100436586  movsd   xmm0, qword ptr [rsp+120h+var_F0]
0x10043658c  subsd   xmm0, qword ptr [rsp+120h+var_100]
0x100436592  movsd   xmm1, qword ptr [rsp+120h+var_F0+8]
0x100436598  subsd   xmm1, qword ptr [rsp+120h+var_100+8]
0x10043659e  mov     rax, [rbx+130h]
0x1004365a5  mulsd   xmm0, xmm0
0x1004365a9  mulsd   xmm1, xmm1
0x1004365ad  addsd   xmm1, xmm0
0x1004365b1  movsd   xmm0, qword ptr [rax]
0x1004365b5  comisd  xmm0, xmm1
0x1004365b9  jbe     loc_1004366D6
0x1004365bf  movups  xmm0, [rsp+120h+var_100]
0x1004365c4  movsd   qword ptr [rax], xmm1
0x1004365c8  movups  xmm1, [rsp+120h+var_F0]
0x1004365cd  movups  xmmword ptr [rax+8], xmm0
0x1004365d1  movups  xmmword ptr [rax+18h], xmm1
0x1004365d5  jmp     loc_1004366D6
0x1004365da  lea     rdx, [rdi+58h]
0x1004365de  mov     r9b, 1
0x1004365e1  lea     r8, [rsp+120h+var_E0]
0x1004365e6  mov     rcx, rbx
0x1004365e9  call    ?UpdateWithPointAndLine@CPlanarDistanceTree@@IEAAXAEBV?$CMglPoint@N@@AEBV?$CLineSegment@V?$CMglPoint@N@@@@_N@Z; CPlanarDistanceTree::UpdateWithPointAndLine(CMglPoint<double> const &,CLineSegment<CMglPoint<double>> const &,bool)
0x1004365ee  mov     r9b, 1
0x1004365f1  lea     r8, [rsp+120h+var_E0]
0x1004365f6  mov     rcx, rbx
0x1004365f9  lea     rdx, [rdi+68h]
0x1004365fd  call    ?UpdateWithPointAndLine@CPlanarDistanceTree@@IEAAXAEBV?$CMglPoint@N@@AEBV?$CLineSegment@V?$CMglPoint@N@@@@_N@Z; CPlanarDistanceTree::UpdateWithPointAndLine(CMglPoint<double> const &,CLineSegment<CMglPoint<double>> const &,bool)
0x100436602  xor     r9d, r9d
0x100436605  lea     rdx, [rsp+120h+var_E0]
0x10043660a  mov     r8, rdi
0x10043660d  mov     rcx, rbx
0x100436610  call    ?UpdateWithPointAndArc@CPlanarDistanceTree@@IEAAXAEBV?$CMglPoint@N@@AEBVCCircularArc2D@@_N@Z; CPlanarDistanceTree::UpdateWithPointAndArc(CMglPoint<double> const &,CCircularArc2D const &,bool)
0x100436615  mov     r8, rdi
0x100436618  lea     rdx, [rsp+120h+var_D0]
0x10043661d  mov     rcx, rbx
0x100436620  jmp     loc_1004366CE
0x100436625  mov     rdx, [rbx+128h]; struct CCircularArc2D *
0x10043662c  lea     r8, [rsp+120h+var_C0]; struct CCircularArc2D *
0x100436631  mov     rcx, rbx; this
0x100436634  call    ?UpdateWithArcs@CPlanarDistanceTree@@IEAAXAEBVCCircularArc2D@@0@Z; CPlanarDistanceTree::UpdateWithArcs(CCircularArc2D const &,CCircularArc2D const &)
0x100436639  jmp     loc_1004366D6
0x10043663e  movups  xmm0, xmmword ptr [r8]
0x100436642  mov     rdi, [rcx+128h]
0x100436649  lea     r9, [rsp+120h+var_100]
0x10043664e  lea     rdx, [rsp+120h+var_E0]
0x100436653  mov     rcx, rdi
0x100436656  movups  [rsp+120h+var_E0], xmm0
0x10043665b  movups  xmm0, xmmword ptr [r8+10h]
0x100436660  lea     r8, [rsp+120h+var_F0]
0x100436665  movups  [rsp+120h+var_D0], xmm0
0x10043666a  call    ?GetPointNearestToLineSegment@CCircularArc2D@@QEBA_NAEBV?$CLineSegment@V?$CMglPoint@N@@@@AEAV?$CMglPoint@N@@1@Z; CCircularArc2D::GetPointNearestToLineSegment(CLineSegment<CMglPoint<double>> const &,CMglPoint<double> &,CMglPoint<double> &)
0x10043666f  test    al, al
0x100436671  jz      loc_1004365DA
0x100436677  movsd   xmm0, qword ptr [rsp+120h+var_100]
0x10043667d  subsd   xmm0, qword ptr [rsp+120h+var_F0]
0x100436683  movsd   xmm1, qword ptr [rsp+120h+var_100+8]
0x100436689  subsd   xmm1, qword ptr [rsp+120h+var_F0+8]
0x10043668f  mov     rax, [rbx+130h]
0x100436696  mulsd   xmm0, xmm0
0x10043669a  mulsd   xmm1, xmm1
0x10043669e  addsd   xmm1, xmm0
0x1004366a2  movsd   xmm0, qword ptr [rax]
0x1004366a6  comisd  xmm0, xmm1
0x1004366aa  jbe     short loc_1004366D6
0x1004366ac  movups  xmm0, [rsp+120h+var_F0]
0x1004366b1  movsd   qword ptr [rax], xmm1
0x1004366b5  movups  xmm1, [rsp+120h+var_100]
0x1004366ba  movups  xmmword ptr [rax+8], xmm0
0x1004366be  movups  xmmword ptr [rax+18h], xmm1
0x1004366c2  jmp     short loc_1004366D6
0x1004366c4  mov     r8, [rcx+128h]
0x1004366cb  mov     rdx, rdi
0x1004366ce  xor     r9d, r9d
0x1004366d1  call    ?UpdateWithPointAndArc@CPlanarDistanceTree@@IEAAXAEBV?$CMglPoint@N@@AEBVCCircularArc2D@@_N@Z; CPlanarDistanceTree::UpdateWithPointAndArc(CMglPoint<double> const &,CCircularArc2D const &,bool)
0x1004366d6  mov     rcx, [rbp+20h+var_10]
0x1004366da  xor     rcx, rsp; StackCookie
0x1004366dd  call    __security_check_cookie
0x1004366e2  lea     r11, [rsp+120h+var_s0]
0x1004366ea  mov     rbx, [r11+18h]
0x1004366ee  mov     rdi, [r11+28h]
0x1004366f2  mov     rsp, r11
0x1004366f5  pop     rbp
0x1004366f6  retn
```
