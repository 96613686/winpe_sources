# CPlanarDistanceTree::UpdateWithLine(uint,CMglPoint<double> const *)

- ea: `0x100436290`
- end: `0x1004364c5`
- name: `?UpdateWithLine@CPlanarDistanceTree@@IEAAXIPEBV?$CMglPoint@N@@@Z`
- size: `565`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x100435fb0`

## callees

- `0x100420ae0`
- `0x100436290`
- `0x100436700`
- `0x100436970`
- `0x10044c120`

## pseudocode

```c
void __fastcall CPlanarDistanceTree::UpdateWithLine(__int64 a1, int a2, __int128 *a3)
{
  __int64 v4; // rbx
  int v5; // edx
  int v6; // edx
  __int64 v7; // r9
  __int64 v8; // r9
  __int128 *v9; // r8
  __int128 *v10; // rdx
  __int64 v11; // rax
  double v12; // xmm1_8
  __int128 v13; // xmm0
  __int128 v14; // xmm1
  __int64 v15; // r9
  __int64 v16; // r9
  __int64 v17; // r9
  __int128 v18; // [rsp+20h] [rbp-E0h] BYREF
  __int128 v19; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v20; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v21; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v22; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v23[11]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v24[16]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v25[24]; // [rsp+D8h] [rbp-28h] BYREF
  double v26; // [rsp+F0h] [rbp-10h]

  v4 = a1;
  v20 = *(_OWORD *)(a1 + 216);
  v21 = *(_OWORD *)(a1 + 232);
  v5 = a2 - 1;
  if ( !v5 )
  {
    v8 = 0;
    v9 = &v20;
    v10 = a3;
    goto LABEL_12;
  }
  v6 = v5 - 1;
  if ( !v6 )
  {
    v18 = *a3;
    v19 = a3[1];
    CPlanarDistanceTree::UpdateWithPointAndLine(a1, &v18, &v20, 0);
    CPlanarDistanceTree::UpdateWithPointAndLine(v4, &v19, &v20, 0);
    LOBYTE(v17) = 1;
    CPlanarDistanceTree::UpdateWithPointAndLine(v4, &v20, &v18, v17);
    LOBYTE(v8) = 1;
    v9 = &v18;
    a1 = v4;
    v10 = &v21;
    goto LABEL_12;
  }
  if ( v6 != 1 )
    return;
  v23[0] = &CGeodeticCircularArc::`vftable';
  CCircularArc<CMglPoint<double>>::ConstructFrom3Points(v23, a3, a3 + 1);
  v23[0] = &CGeodeticCircularArc::`vftable';
  if ( v26 == 0.0 )
  {
    v18 = *a3;
    v19 = a3[2];
    CPlanarDistanceTree::UpdateWithPointAndLine(v4, &v18, &v20, 0);
    CPlanarDistanceTree::UpdateWithPointAndLine(v4, &v19, &v20, 0);
    LOBYTE(v7) = 1;
    CPlanarDistanceTree::UpdateWithPointAndLine(v4, &v20, &v18, v7);
    LOBYTE(v8) = 1;
    v9 = &v18;
    a1 = v4;
    v10 = &v21;
LABEL_12:
    CPlanarDistanceTree::UpdateWithPointAndLine(a1, v10, v9, v8);
    return;
  }
  if ( (unsigned __int8)CCircularArc2D::GetPointNearestToLineSegment(v23, &v20, &v18, &v22) )
  {
    v11 = *(_QWORD *)(v4 + 304);
    v12 = (*((double *)&v18 + 1) - *((double *)&v22 + 1)) * (*((double *)&v18 + 1) - *((double *)&v22 + 1))
        + (*(double *)&v18 - *(double *)&v22) * (*(double *)&v18 - *(double *)&v22);
    if ( *(double *)v11 > v12 )
    {
      v13 = v22;
      *(double *)v11 = v12;
      v14 = v18;
      *(_OWORD *)(v11 + 8) = v13;
      *(_OWORD *)(v11 + 24) = v14;
    }
  }
  else
  {
    CPlanarDistanceTree::UpdateWithPointAndLine(v4, v24, &v20, 0);
    CPlanarDistanceTree::UpdateWithPointAndLine(v4, v25, &v20, 0);
    LOBYTE(v15) = 1;
    CPlanarDistanceTree::UpdateWithPointAndArc(v4, &v20, v23, v15);
    LOBYTE(v16) = 1;
    CPlanarDistanceTree::UpdateWithPointAndArc(v4, &v21, v23, v16);
  }
}

```

## disassembly

```asm
0x100436290  mov     [rsp-8+arg_0], rbx
0x100436295  mov     [rsp-8+arg_8], rdi
0x10043629a  push    rbp
0x10043629b  lea     rbp, [rsp-20h]
0x1004362a0  sub     rsp, 120h
0x1004362a7  mov     rdi, r8
0x1004362aa  mov     rbx, rcx
0x1004362ad  movups  xmm0, xmmword ptr [rcx+0D8h]
0x1004362b4  movups  [rsp+120h+var_E0], xmm0
0x1004362b9  movups  xmm0, xmmword ptr [rcx+0E8h]
0x1004362c0  movups  [rsp+120h+var_D0], xmm0
0x1004362c5  sub     edx, 1
0x1004362c8  jz      loc_1004364A0
0x1004362ce  sub     edx, 1
0x1004362d1  jz      loc_10043643F
0x1004362d7  cmp     edx, 1
0x1004362da  jnz     loc_1004364B0
0x1004362e0  lea     rax, ??_7CGeodeticCircularArc@@6B@; const CGeodeticCircularArc::`vftable'
0x1004362e7  add     r8, 10h
0x1004362eb  mov     rdx, rdi
0x1004362ee  mov     [rsp+120h+var_B0], rax
0x1004362f3  lea     rcx, [rsp+120h+var_B0]
0x1004362f8  call    ?ConstructFrom3Points@?$CCircularArc@V?$CMglPoint@N@@@@QEAAXAEBV?$CMglPoint@N@@PEBV2@@Z; CCircularArc<CMglPoint<double>>::ConstructFrom3Points(CMglPoint<double> const &,CMglPoint<double> const *)
0x1004362fd  xorps   xmm0, xmm0
0x100436300  lea     rax, ??_7CGeodeticCircularArc@@6B@; const CGeodeticCircularArc::`vftable'
0x100436307  ucomisd xmm0, [rbp+20h+var_30]
0x10043630c  mov     [rsp+120h+var_B0], rax
0x100436311  jp      short loc_10043637A
0x100436313  jnz     short loc_10043637A
0x100436315  movups  xmm0, xmmword ptr [rdi]
0x100436318  xor     r9d, r9d
0x10043631b  lea     r8, [rsp+120h+var_E0]
0x100436320  lea     rdx, [rsp+120h+var_100]
0x100436325  mov     rcx, rbx
0x100436328  movups  [rsp+120h+var_100], xmm0
0x10043632d  movups  xmm0, xmmword ptr [rdi+20h]
0x100436331  movups  [rsp+120h+var_F0], xmm0
0x100436336  call    ?UpdateWithPointAndLine@CPlanarDistanceTree@@IEAAXAEBV?$CMglPoint@N@@AEBV?$CLineSegment@V?$CMglPoint@N@@@@_N@Z; CPlanarDistanceTree::UpdateWithPointAndLine(CMglPoint<double> const &,CLineSegment<CMglPoint<double>> const &,bool)
0x10043633b  xor     r9d, r9d
0x10043633e  lea     r8, [rsp+120h+var_E0]
0x100436343  mov     rcx, rbx
0x100436346  lea     rdx, [rsp+120h+var_F0]
0x10043634b  call    ?UpdateWithPointAndLine@CPlanarDistanceTree@@IEAAXAEBV?$CMglPoint@N@@AEBV?$CLineSegment@V?$CMglPoint@N@@@@_N@Z; CPlanarDistanceTree::UpdateWithPointAndLine(CMglPoint<double> const &,CLineSegment<CMglPoint<double>> const &,bool)
0x100436350  mov     r9b, 1
0x100436353  lea     r8, [rsp+120h+var_100]
0x100436358  mov     rcx, rbx
0x10043635b  lea     rdx, [rsp+120h+var_E0]
0x100436360  call    ?UpdateWithPointAndLine@CPlanarDistanceTree@@IEAAXAEBV?$CMglPoint@N@@AEBV?$CLineSegment@V?$CMglPoint@N@@@@_N@Z; CPlanarDistanceTree::UpdateWithPointAndLine(CMglPoint<double> const &,CLineSegment<CMglPoint<double>> const &,bool)
0x100436365  mov     r9b, 1
0x100436368  lea     r8, [rsp+120h+var_100]
0x10043636d  mov     rcx, rbx
0x100436370  lea     rdx, [rsp+120h+var_D0]
0x100436375  jmp     loc_1004364AB
0x10043637a  lea     r9, [rsp+120h+var_C0]
0x10043637f  lea     r8, [rsp+120h+var_100]
0x100436384  lea     rdx, [rsp+120h+var_E0]
0x100436389  lea     rcx, [rsp+120h+var_B0]
0x10043638e  call    ?GetPointNearestToLineSegment@CCircularArc2D@@QEBA_NAEBV?$CLineSegment@V?$CMglPoint@N@@@@AEAV?$CMglPoint@N@@1@Z; CCircularArc2D::GetPointNearestToLineSegment(CLineSegment<CMglPoint<double>> const &,CMglPoint<double> &,CMglPoint<double> &)
0x100436393  test    al, al
0x100436395  jz      short loc_1004363EB
0x100436397  movsd   xmm0, qword ptr [rsp+120h+var_100]
0x10043639d  subsd   xmm0, qword ptr [rsp+120h+var_C0]
0x1004363a3  movsd   xmm1, qword ptr [rsp+120h+var_100+8]
0x1004363a9  subsd   xmm1, qword ptr [rsp+120h+var_C0+8]
0x1004363af  mov     rax, [rbx+130h]
0x1004363b6  mulsd   xmm0, xmm0
0x1004363ba  mulsd   xmm1, xmm1
0x1004363be  addsd   xmm1, xmm0
0x1004363c2  movsd   xmm0, qword ptr [rax]
0x1004363c6  comisd  xmm0, xmm1
0x1004363ca  jbe     loc_1004364B0
0x1004363d0  movups  xmm0, [rsp+120h+var_C0]
0x1004363d5  movsd   qword ptr [rax], xmm1
0x1004363d9  movups  xmm1, [rsp+120h+var_100]
0x1004363de  movups  xmmword ptr [rax+8], xmm0
0x1004363e2  movups  xmmword ptr [rax+18h], xmm1
0x1004363e6  jmp     loc_1004364B0
0x1004363eb  xor     r9d, r9d
0x1004363ee  lea     r8, [rsp+120h+var_E0]
0x1004363f3  lea     rdx, [rbp+20h+var_58]
0x1004363f7  mov     rcx, rbx
0x1004363fa  call    ?UpdateWithPointAndLine@CPlanarDistanceTree@@IEAAXAEBV?$CMglPoint@N@@AEBV?$CLineSegment@V?$CMglPoint@N@@@@_N@Z; CPlanarDistanceTree::UpdateWithPointAndLine(CMglPoint<double> const &,CLineSegment<CMglPoint<double>> const &,bool)
0x1004363ff  xor     r9d, r9d
0x100436402  lea     r8, [rsp+120h+var_E0]
0x100436407  mov     rcx, rbx
0x10043640a  lea     rdx, [rbp+20h+var_48]
0x10043640e  call    ?UpdateWithPointAndLine@CPlanarDistanceTree@@IEAAXAEBV?$CMglPoint@N@@AEBV?$CLineSegment@V?$CMglPoint@N@@@@_N@Z; CPlanarDistanceTree::UpdateWithPointAndLine(CMglPoint<double> const &,CLineSegment<CMglPoint<double>> const &,bool)
0x100436413  mov     r9b, 1
0x100436416  lea     r8, [rsp+120h+var_B0]
0x10043641b  mov     rcx, rbx
0x10043641e  lea     rdx, [rsp+120h+var_E0]
0x100436423  call    ?UpdateWithPointAndArc@CPlanarDistanceTree@@IEAAXAEBV?$CMglPoint@N@@AEBVCCircularArc2D@@_N@Z; CPlanarDistanceTree::UpdateWithPointAndArc(CMglPoint<double> const &,CCircularArc2D const &,bool)
0x100436428  mov     r9b, 1
0x10043642b  lea     r8, [rsp+120h+var_B0]
0x100436430  lea     rdx, [rsp+120h+var_D0]
0x100436435  mov     rcx, rbx
0x100436438  call    ?UpdateWithPointAndArc@CPlanarDistanceTree@@IEAAXAEBV?$CMglPoint@N@@AEBVCCircularArc2D@@_N@Z; CPlanarDistanceTree::UpdateWithPointAndArc(CMglPoint<double> const &,CCircularArc2D const &,bool)
0x10043643d  jmp     short loc_1004364B0
0x10043643f  movups  xmm0, xmmword ptr [r8]
0x100436443  xor     r9d, r9d
0x100436446  lea     rdx, [rsp+120h+var_100]
0x10043644b  movups  [rsp+120h+var_100], xmm0
0x100436450  movups  xmm0, xmmword ptr [r8+10h]
0x100436455  lea     r8, [rsp+120h+var_E0]
0x10043645a  movups  [rsp+120h+var_F0], xmm0
0x10043645f  call    ?UpdateWithPointAndLine@CPlanarDistanceTree@@IEAAXAEBV?$CMglPoint@N@@AEBV?$CLineSegment@V?$CMglPoint@N@@@@_N@Z; CPlanarDistanceTree::UpdateWithPointAndLine(CMglPoint<double> const &,CLineSegment<CMglPoint<double>> const &,bool)
0x100436464  xor     r9d, r9d
0x100436467  lea     r8, [rsp+120h+var_E0]
0x10043646c  mov     rcx, rbx
0x10043646f  lea     rdx, [rsp+120h+var_F0]
0x100436474  call    ?UpdateWithPointAndLine@CPlanarDistanceTree@@IEAAXAEBV?$CMglPoint@N@@AEBV?$CLineSegment@V?$CMglPoint@N@@@@_N@Z; CPlanarDistanceTree::UpdateWithPointAndLine(CMglPoint<double> const &,CLineSegment<CMglPoint<double>> const &,bool)
0x100436479  mov     r9b, 1
0x10043647c  lea     r8, [rsp+120h+var_100]
0x100436481  mov     rcx, rbx
0x100436484  lea     rdx, [rsp+120h+var_E0]
0x100436489  call    ?UpdateWithPointAndLine@CPlanarDistanceTree@@IEAAXAEBV?$CMglPoint@N@@AEBV?$CLineSegment@V?$CMglPoint@N@@@@_N@Z; CPlanarDistanceTree::UpdateWithPointAndLine(CMglPoint<double> const &,CLineSegment<CMglPoint<double>> const &,bool)
0x10043648e  mov     r9b, 1
0x100436491  lea     r8, [rsp+120h+var_100]
0x100436496  mov     rcx, rbx
0x100436499  lea     rdx, [rsp+120h+var_D0]
0x10043649e  jmp     short loc_1004364AB
0x1004364a0  xor     r9d, r9d
0x1004364a3  lea     r8, [rsp+120h+var_E0]
0x1004364a8  mov     rdx, rdi
0x1004364ab  call    ?UpdateWithPointAndLine@CPlanarDistanceTree@@IEAAXAEBV?$CMglPoint@N@@AEBV?$CLineSegment@V?$CMglPoint@N@@@@_N@Z; CPlanarDistanceTree::UpdateWithPointAndLine(CMglPoint<double> const &,CLineSegment<CMglPoint<double>> const &,bool)
0x1004364b0  lea     r11, [rsp+120h+var_s0]
0x1004364b8  mov     rbx, [r11+10h]
0x1004364bc  mov     rdi, [r11+18h]
0x1004364c0  mov     rsp, r11
0x1004364c3  pop     rbp
0x1004364c4  retn
```
