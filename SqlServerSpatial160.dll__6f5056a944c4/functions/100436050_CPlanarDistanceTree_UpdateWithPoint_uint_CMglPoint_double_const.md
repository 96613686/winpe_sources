# CPlanarDistanceTree::UpdateWithPoint(uint,CMglPoint<double> const *)

- ea: `0x100436050`
- end: `0x100436285`
- name: `?UpdateWithPoint@CPlanarDistanceTree@@IEAAXIPEBV?$CMglPoint@N@@@Z`
- size: `565`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x100435fb0`

## callees

- `0x100420ae0`
- `0x100436050`
- `0x100436700`
- `0x10044bf00`

## pseudocode

```c
_UNKNOWN **__fastcall CPlanarDistanceTree::UpdateWithPoint(__int64 a1, int a2, double *a3, __int64 a4)
{
  _UNKNOWN **result; // rax
  int v7; // edx
  int v8; // edx
  __int64 v9; // r9
  double *v10; // rsi
  __int64 v11; // rbx
  double v12; // xmm6_8
  double v13; // xmm7_8
  double v14; // xmm6_8
  __int128 v15; // xmm0
  double v16; // xmm1_8
  __int128 v17; // xmm0
  double v18; // xmm6_8
  double v19; // xmm1_8
  __int128 v20; // [rsp+28h] [rbp-E0h] BYREF
  __int128 v21; // [rsp+38h] [rbp-D0h]
  _QWORD v22[11]; // [rsp+48h] [rbp-C0h] BYREF
  __int128 v23; // [rsp+A0h] [rbp-68h]
  double v24[3]; // [rsp+B0h] [rbp-58h]
  double v25; // [rsp+C8h] [rbp-40h]
  _UNKNOWN *retaddr; // [rsp+120h] [rbp+18h] BYREF

  result = &retaddr;
  v7 = a2 - 1;
  if ( v7 )
  {
    v8 = v7 - 1;
    if ( !v8 )
    {
      LOBYTE(a4) = 1;
      v20 = *(_OWORD *)a3;
      v21 = *((_OWORD *)a3 + 1);
      return (_UNKNOWN **)CPlanarDistanceTree::UpdateWithPointAndLine(a1, a1 + 216, &v20, a4);
    }
    if ( v8 == 1 )
    {
      v22[0] = &CGeodeticCircularArc::`vftable';
      CCircularArc<CMglPoint<double>>::ConstructFrom3Points(v22, a3, a3 + 2);
      v22[0] = &CGeodeticCircularArc::`vftable';
      v10 = (double *)(a1 + 216);
      if ( v25 == 0.0 )
      {
        LOBYTE(v9) = 1;
        v20 = *(_OWORD *)a3;
        v21 = *((_OWORD *)a3 + 2);
        return (_UNKNOWN **)CPlanarDistanceTree::UpdateWithPointAndLine(a1, a1 + 216, &v20, v9);
      }
      v11 = *(_QWORD *)(a1 + 304);
      v12 = *(double *)(a1 + 224);
      v13 = *v10;
      result = (_UNKNOWN **)CCircularArc2D::GetPointNearestToPoint(v22, a1 + 216, &v20);
      if ( (_BYTE)result )
      {
        v14 = (v12 - *((double *)&v20 + 1)) * (v12 - *((double *)&v20 + 1))
            + (v13 - *(double *)&v20) * (v13 - *(double *)&v20);
        if ( *(double *)v11 <= v14 )
          return result;
        v15 = v20;
        *(double *)v11 = v14;
        goto LABEL_9;
      }
      v16 = (v12 - *((double *)&v23 + 1)) * (v12 - *((double *)&v23 + 1))
          + (v13 - *(double *)&v23) * (v13 - *(double *)&v23);
      if ( *(double *)v11 > v16 )
      {
        v17 = v23;
        *(double *)v11 = v16;
        *(_OWORD *)(v11 + 8) = v17;
        *(_OWORD *)(v11 + 24) = *(_OWORD *)v10;
        v11 = *(_QWORD *)(a1 + 304);
        v13 = *v10;
        v12 = *(double *)(a1 + 224);
      }
      v18 = (v12 - v24[1]) * (v12 - v24[1]) + (v13 - v24[0]) * (v13 - v24[0]);
      if ( *(double *)v11 > v18 )
      {
        v15 = *(_OWORD *)v24;
        *(double *)v11 = v18;
LABEL_9:
        *(_OWORD *)(v11 + 8) = v15;
        *(_OWORD *)(v11 + 24) = *(_OWORD *)v10;
      }
    }
  }
  else
  {
    result = *(_UNKNOWN ***)(a1 + 304);
    v19 = (*(double *)(a1 + 224) - a3[1]) * (*(double *)(a1 + 224) - a3[1])
        + (*(double *)(a1 + 216) - *a3) * (*(double *)(a1 + 216) - *a3);
    if ( *(double *)result > v19 )
    {
      *(double *)result = v19;
      *(_OWORD *)(result + 1) = *(_OWORD *)a3;
      *(_OWORD *)(result + 3) = *(_OWORD *)(a1 + 216);
    }
  }
  return result;
}

```

## disassembly

```asm
0x100436050  mov     rax, rsp
0x100436053  mov     [rax+10h], rbx
0x100436057  mov     [rax+18h], rdi
0x10043605b  push    rbp
0x10043605c  lea     rbp, [rax-18h]
0x100436060  sub     rsp, 110h
0x100436067  mov     rbx, r8
0x10043606a  mov     rdi, rcx
0x10043606d  sub     edx, 1
0x100436070  jz      loc_10043622D
0x100436076  sub     edx, 1
0x100436079  jz      loc_100436201
0x10043607f  cmp     edx, 1
0x100436082  jnz     loc_100436172
0x100436088  mov     [rax+8], rsi
0x10043608c  lea     rcx, [rsp+110h+var_D0]
0x100436091  lea     rax, ??_7CGeodeticCircularArc@@6B@; const CGeodeticCircularArc::`vftable'
0x100436098  add     r8, 10h
0x10043609c  mov     rdx, rbx
0x10043609f  mov     [rsp+110h+var_D0], rax
0x1004360a4  call    ?ConstructFrom3Points@?$CCircularArc@V?$CMglPoint@N@@@@QEAAXAEBV?$CMglPoint@N@@PEBV2@@Z; CCircularArc<CMglPoint<double>>::ConstructFrom3Points(CMglPoint<double> const &,CMglPoint<double> const *)
0x1004360a9  xorps   xmm0, xmm0
0x1004360ac  lea     rax, ??_7CGeodeticCircularArc@@6B@; const CGeodeticCircularArc::`vftable'
0x1004360b3  ucomisd xmm0, [rbp+10h+var_50]
0x1004360b8  mov     [rsp+110h+var_D0], rax
0x1004360bd  lea     rsi, [rdi+0D8h]
0x1004360c4  jp      short loc_1004360EE
0x1004360c6  jnz     short loc_1004360EE
0x1004360c8  movups  xmm0, xmmword ptr [rbx]
0x1004360cb  mov     r9b, 1
0x1004360ce  lea     r8, [rsp+110h+var_F8+8]
0x1004360d3  mov     rdx, rsi
0x1004360d6  mov     rcx, rdi
0x1004360d9  movups  [rsp+110h+var_F8+8], xmm0
0x1004360de  movups  xmm0, xmmword ptr [rbx+20h]
0x1004360e2  movups  xmmword ptr [rsp+110h+var_E8+8], xmm0
0x1004360e7  call    ?UpdateWithPointAndLine@CPlanarDistanceTree@@IEAAXAEBV?$CMglPoint@N@@AEBV?$CLineSegment@V?$CMglPoint@N@@@@_N@Z; CPlanarDistanceTree::UpdateWithPointAndLine(CMglPoint<double> const &,CLineSegment<CMglPoint<double>> const &,bool)
0x1004360ec  jmp     short loc_10043616A
0x1004360ee  mov     rbx, [rdi+130h]
0x1004360f5  lea     r8, [rsp+110h+var_F8+8]
0x1004360fa  movaps  [rsp+110h+var_18+8], xmm6
0x100436102  lea     rcx, [rsp+110h+var_D0]
0x100436107  movsd   xmm6, qword ptr [rsi+8]
0x10043610c  mov     rdx, rsi
0x10043610f  movaps  [rsp+110h+var_28+8], xmm7
0x100436117  movsd   xmm7, qword ptr [rsi]
0x10043611b  call    ?GetPointNearestToPoint@CCircularArc2D@@QEBA_NAEBV?$CMglPoint@N@@AEAV2@@Z; CCircularArc2D::GetPointNearestToPoint(CMglPoint<double> const &,CMglPoint<double> &)
0x100436120  test    al, al
0x100436122  jz      short loc_100436187
0x100436124  subsd   xmm6, qword ptr [rsp+110h+var_E8]
0x10043612a  subsd   xmm7, qword ptr [rsp+110h+var_F8+8]
0x100436130  movsd   xmm0, qword ptr [rbx]
0x100436134  mulsd   xmm6, xmm6
0x100436138  mulsd   xmm7, xmm7
0x10043613c  addsd   xmm6, xmm7
0x100436140  comisd  xmm0, xmm6
0x100436144  jbe     short loc_10043615A
0x100436146  movups  xmm0, [rsp+110h+var_F8+8]
0x10043614b  movsd   qword ptr [rbx], xmm6
0x10043614f  movups  xmmword ptr [rbx+8], xmm0
0x100436153  movups  xmm0, xmmword ptr [rsi]
0x100436156  movups  xmmword ptr [rbx+18h], xmm0
0x10043615a  movaps  xmm6, [rsp+110h+var_18+8]
0x100436162  movaps  xmm7, [rsp+110h+var_28+8]
0x10043616a  mov     rsi, [rsp+110h+arg_0]
0x100436172  lea     r11, [rsp+110h+var_s0]
0x10043617a  mov     rbx, [r11+18h]
0x10043617e  mov     rdi, [r11+20h]
0x100436182  mov     rsp, r11
0x100436185  pop     rbp
0x100436186  retn
0x100436187  movaps  xmm0, xmm7
0x10043618a  movaps  xmm1, xmm6
0x10043618d  subsd   xmm0, qword ptr [rbp+10h+var_78]
0x100436192  subsd   xmm1, qword ptr [rbp+10h+var_78+8]
0x100436197  mulsd   xmm0, xmm0
0x10043619b  mulsd   xmm1, xmm1
0x10043619f  addsd   xmm1, xmm0
0x1004361a3  movsd   xmm0, qword ptr [rbx]
0x1004361a7  comisd  xmm0, xmm1
0x1004361ab  jbe     short loc_1004361D0
0x1004361ad  movups  xmm0, [rbp+10h+var_78]
0x1004361b1  movsd   qword ptr [rbx], xmm1
0x1004361b5  movups  xmmword ptr [rbx+8], xmm0
0x1004361b9  movups  xmm0, xmmword ptr [rsi]
0x1004361bc  movups  xmmword ptr [rbx+18h], xmm0
0x1004361c0  mov     rbx, [rdi+130h]
0x1004361c7  movsd   xmm7, qword ptr [rsi]
0x1004361cb  movsd   xmm6, qword ptr [rsi+8]
0x1004361d0  subsd   xmm6, [rbp+10h+var_68+8]
0x1004361d5  subsd   xmm7, [rbp+10h+var_68]
0x1004361da  movsd   xmm0, qword ptr [rbx]
0x1004361de  mulsd   xmm6, xmm6
0x1004361e2  mulsd   xmm7, xmm7
0x1004361e6  addsd   xmm6, xmm7
0x1004361ea  comisd  xmm0, xmm6
0x1004361ee  jbe     loc_10043615A
0x1004361f4  movups  xmm0, xmmword ptr [rbp+10h+var_68]
0x1004361f8  movsd   qword ptr [rbx], xmm6
0x1004361fc  jmp     loc_10043614F
0x100436201  movups  xmm0, xmmword ptr [r8]
0x100436205  lea     rdx, [rcx+0D8h]
0x10043620c  mov     r9b, 1
0x10043620f  movups  [rsp+110h+var_F8+8], xmm0
0x100436214  movups  xmm0, xmmword ptr [r8+10h]
0x100436219  lea     r8, [rsp+110h+var_F8+8]
0x10043621e  movups  xmmword ptr [rsp+110h+var_E8+8], xmm0
0x100436223  call    ?UpdateWithPointAndLine@CPlanarDistanceTree@@IEAAXAEBV?$CMglPoint@N@@AEBV?$CLineSegment@V?$CMglPoint@N@@@@_N@Z; CPlanarDistanceTree::UpdateWithPointAndLine(CMglPoint<double> const &,CLineSegment<CMglPoint<double>> const &,bool)
0x100436228  jmp     loc_100436172
0x10043622d  movsd   xmm0, qword ptr [rcx+0D8h]
0x100436235  subsd   xmm0, qword ptr [r8]
0x10043623a  movsd   xmm1, qword ptr [rcx+0E0h]
0x100436242  subsd   xmm1, qword ptr [r8+8]
0x100436248  mov     rax, [rcx+130h]
0x10043624f  mulsd   xmm0, xmm0
0x100436253  mulsd   xmm1, xmm1
0x100436257  addsd   xmm1, xmm0
0x10043625b  movsd   xmm0, qword ptr [rax]
0x10043625f  comisd  xmm0, xmm1
0x100436263  jbe     loc_100436172
0x100436269  movsd   qword ptr [rax], xmm1
0x10043626d  movups  xmm0, xmmword ptr [r8]
0x100436271  movups  xmmword ptr [rax+8], xmm0
0x100436275  movups  xmm0, xmmword ptr [rcx+0D8h]
0x10043627c  movups  xmmword ptr [rax+18h], xmm0
0x100436280  jmp     loc_100436172
```
