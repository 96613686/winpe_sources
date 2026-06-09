# CPlanarDistanceTree::UpdateWithPointAndArc(CMglPoint<double> const &,CCircularArc2D const &,bool)

- ea: `0x100436970`
- end: `0x100436b72`
- name: `?UpdateWithPointAndArc@CPlanarDistanceTree@@IEAAXAEBV?$CMglPoint@N@@AEBVCCircularArc2D@@_N@Z`
- size: `514`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x100436290`
- `0x1004364d0`

## callees

- `0x100436970`
- `0x10044bf00`

## pseudocode

```c
__int64 __fastcall CPlanarDistanceTree::UpdateWithPointAndArc(__int64 a1, double *a2, double *a3, char a4)
{
  __int64 result; // rax
  __int64 v9; // r10
  double v10; // xmm2_8
  double v11; // xmm1_8
  double v12; // xmm3_8
  double v13; // xmm1_8
  __int128 v14; // xmm0
  double v15; // xmm2_8
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  double v18; // xmm0_8
  double v19; // xmm1_8
  double v20; // xmm0_8
  double v21; // xmm1_8
  __int128 v22; // xmm0
  double v23; // xmm0_8
  double v24; // xmm1_8
  double v25; // xmm0_8
  double v26; // xmm1_8
  double v27[3]; // [rsp+20h] [rbp-18h] BYREF

  result = CCircularArc2D::GetPointNearestToPoint(a3, a2, v27);
  v9 = *(_QWORD *)(a1 + 304);
  if ( (_BYTE)result )
  {
    v10 = *a2;
    v11 = a2[1];
    v12 = *(double *)v9;
    if ( a4 )
    {
      v13 = (v11 - v27[1]) * (v11 - v27[1]) + (v10 - v27[0]) * (v10 - v27[0]);
      if ( v12 > v13 )
      {
        v14 = *(_OWORD *)v27;
        *(double *)v9 = v13;
        *(_OWORD *)(v9 + 8) = v14;
        *(_OWORD *)(v9 + 24) = *(_OWORD *)a2;
      }
    }
    else
    {
      v15 = (v27[1] - v11) * (v27[1] - v11) + (v27[0] - v10) * (v27[0] - v10);
      if ( v12 > v15 )
      {
        v16 = *(_OWORD *)v27;
        *(double *)v9 = v15;
        v17 = *(_OWORD *)a2;
        *(_OWORD *)(v9 + 24) = v16;
        *(_OWORD *)(v9 + 8) = v17;
      }
    }
    return result;
  }
  if ( a4 )
  {
    v18 = a2[1] - a3[12];
    v19 = (*a2 - a3[11]) * (*a2 - a3[11]) + v18 * v18;
    if ( *(double *)v9 > v19 )
    {
      *(double *)v9 = v19;
      *(_OWORD *)(v9 + 8) = *(_OWORD *)(a3 + 11);
      *(_OWORD *)(v9 + 24) = *(_OWORD *)a2;
    }
    v20 = a2[1] - a3[14];
    result = *(_QWORD *)(a1 + 304);
    v21 = (*a2 - a3[13]) * (*a2 - a3[13]) + v20 * v20;
    if ( *(double *)result > v21 )
    {
      *(double *)result = v21;
      *(_OWORD *)(result + 8) = *(_OWORD *)(a3 + 13);
      v22 = *(_OWORD *)a2;
LABEL_16:
      *(_OWORD *)(result + 24) = v22;
    }
  }
  else
  {
    v23 = a3[12] - a2[1];
    v24 = (a3[11] - *a2) * (a3[11] - *a2) + v23 * v23;
    if ( *(double *)v9 > v24 )
    {
      *(double *)v9 = v24;
      *(_OWORD *)(v9 + 8) = *(_OWORD *)a2;
      *(_OWORD *)(v9 + 24) = *(_OWORD *)(a3 + 11);
    }
    result = *(_QWORD *)(a1 + 304);
    v25 = a3[14] - a2[1];
    v26 = (a3[13] - *a2) * (a3[13] - *a2) + v25 * v25;
    if ( *(double *)result > v26 )
    {
      *(double *)result = v26;
      *(_OWORD *)(result + 8) = *(_OWORD *)a2;
      v22 = *(_OWORD *)(a3 + 13);
      goto LABEL_16;
    }
  }
  return result;
}

```

## disassembly

```asm
0x100436970  mov     [rsp+arg_0], rbx
0x100436975  mov     [rsp+arg_8], rbp
0x10043697a  mov     [rsp+arg_10], rsi
0x10043697f  push    rdi
0x100436980  sub     rsp, 30h
0x100436984  mov     rdi, r8
0x100436987  mov     rbp, rcx
0x10043698a  mov     rcx, rdi
0x10043698d  lea     r8, [rsp+38h+var_18]
0x100436992  movzx   esi, r9b
0x100436996  mov     rbx, rdx
0x100436999  call    ?GetPointNearestToPoint@CCircularArc2D@@QEBA_NAEBV?$CMglPoint@N@@AEAV2@@Z; CCircularArc2D::GetPointNearestToPoint(CMglPoint<double> const &,CMglPoint<double> &)
0x10043699e  mov     r10, [rbp+130h]
0x1004369a5  test    al, al
0x1004369a7  jz      loc_100436A44
0x1004369ad  movsd   xmm2, qword ptr [rbx]
0x1004369b1  movsd   xmm1, qword ptr [rbx+8]
0x1004369b6  movsd   xmm3, qword ptr [r10]
0x1004369bb  test    sil, sil
0x1004369be  jz      short loc_1004369FE
0x1004369c0  subsd   xmm1, [rsp+38h+var_18+8]
0x1004369c6  subsd   xmm2, [rsp+38h+var_18]
0x1004369cc  mulsd   xmm1, xmm1
0x1004369d0  mulsd   xmm2, xmm2
0x1004369d4  addsd   xmm1, xmm2
0x1004369d8  comisd  xmm3, xmm1
0x1004369dc  jbe     loc_100436B5D
0x1004369e2  movups  xmm0, xmmword ptr [rsp+38h+var_18]
0x1004369e7  movsd   qword ptr [r10], xmm1
0x1004369ec  movups  xmmword ptr [r10+8], xmm0
0x1004369f1  movups  xmm0, xmmword ptr [rbx]
0x1004369f4  movups  xmmword ptr [r10+18h], xmm0
0x1004369f9  jmp     loc_100436B5D
0x1004369fe  movsd   xmm0, [rsp+38h+var_18]
0x100436a04  subsd   xmm0, xmm2
0x100436a08  movsd   xmm2, [rsp+38h+var_18+8]
0x100436a0e  subsd   xmm2, xmm1
0x100436a12  mulsd   xmm0, xmm0
0x100436a16  mulsd   xmm2, xmm2
0x100436a1a  addsd   xmm2, xmm0
0x100436a1e  comisd  xmm3, xmm2
0x100436a22  jbe     loc_100436B5D
0x100436a28  movups  xmm1, xmmword ptr [rsp+38h+var_18]
0x100436a2d  movsd   qword ptr [r10], xmm2
0x100436a32  movups  xmm0, xmmword ptr [rbx]
0x100436a35  movups  xmmword ptr [r10+18h], xmm1
0x100436a3a  movups  xmmword ptr [r10+8], xmm0
0x100436a3f  jmp     loc_100436B5D
0x100436a44  test    sil, sil
0x100436a47  jz      loc_100436AD5
0x100436a4d  movsd   xmm0, qword ptr [rbx+8]
0x100436a52  subsd   xmm0, qword ptr [rdi+60h]
0x100436a57  movsd   xmm1, qword ptr [rbx]
0x100436a5b  subsd   xmm1, qword ptr [rdi+58h]
0x100436a60  mulsd   xmm0, xmm0
0x100436a64  mulsd   xmm1, xmm1
0x100436a68  addsd   xmm1, xmm0
0x100436a6c  movsd   xmm0, qword ptr [r10]
0x100436a71  comisd  xmm0, xmm1
0x100436a75  jbe     short loc_100436A8D
0x100436a77  movsd   qword ptr [r10], xmm1
0x100436a7c  movups  xmm0, xmmword ptr [rdi+58h]
0x100436a80  movups  xmmword ptr [r10+8], xmm0
0x100436a85  movups  xmm0, xmmword ptr [rbx]
0x100436a88  movups  xmmword ptr [r10+18h], xmm0
0x100436a8d  movsd   xmm0, qword ptr [rbx+8]
0x100436a92  subsd   xmm0, qword ptr [rdi+70h]
0x100436a97  movsd   xmm1, qword ptr [rbx]
0x100436a9b  subsd   xmm1, qword ptr [rdi+68h]
0x100436aa0  mov     rax, [rbp+130h]
0x100436aa7  mulsd   xmm0, xmm0
0x100436aab  mulsd   xmm1, xmm1
0x100436aaf  addsd   xmm1, xmm0
0x100436ab3  movsd   xmm0, qword ptr [rax]
0x100436ab7  comisd  xmm0, xmm1
0x100436abb  jbe     loc_100436B5D
0x100436ac1  movsd   qword ptr [rax], xmm1
0x100436ac5  movups  xmm0, xmmword ptr [rdi+68h]
0x100436ac9  movups  xmmword ptr [rax+8], xmm0
0x100436acd  movups  xmm0, xmmword ptr [rbx]
0x100436ad0  jmp     loc_100436B59
0x100436ad5  movsd   xmm0, qword ptr [rdi+60h]
0x100436ada  subsd   xmm0, qword ptr [rbx+8]
0x100436adf  movsd   xmm1, qword ptr [rdi+58h]
0x100436ae4  subsd   xmm1, qword ptr [rbx]
0x100436ae8  mulsd   xmm0, xmm0
0x100436aec  mulsd   xmm1, xmm1
0x100436af0  addsd   xmm1, xmm0
0x100436af4  movsd   xmm0, qword ptr [r10]
0x100436af9  comisd  xmm0, xmm1
0x100436afd  jbe     short loc_100436B1E
0x100436aff  movsd   qword ptr [r10], xmm1
0x100436b04  movups  xmm0, xmmword ptr [rbx]
0x100436b07  movups  xmmword ptr [r10+8], xmm0
0x100436b0c  movups  xmm0, xmmword ptr [rdi+58h]
0x100436b10  movups  xmmword ptr [r10+18h], xmm0
0x100436b15  mov     rax, [rbp+130h]
0x100436b1c  jmp     short loc_100436B21
0x100436b1e  mov     rax, r10
0x100436b21  movsd   xmm0, qword ptr [rdi+70h]
0x100436b26  subsd   xmm0, qword ptr [rbx+8]
0x100436b2b  movsd   xmm1, qword ptr [rdi+68h]
0x100436b30  subsd   xmm1, qword ptr [rbx]
0x100436b34  mulsd   xmm0, xmm0
0x100436b38  mulsd   xmm1, xmm1
0x100436b3c  addsd   xmm1, xmm0
0x100436b40  movsd   xmm0, qword ptr [rax]
0x100436b44  comisd  xmm0, xmm1
0x100436b48  jbe     short loc_100436B5D
0x100436b4a  movsd   qword ptr [rax], xmm1
0x100436b4e  movups  xmm0, xmmword ptr [rbx]
0x100436b51  movups  xmmword ptr [rax+8], xmm0
0x100436b55  movups  xmm0, xmmword ptr [rdi+68h]
0x100436b59  movups  xmmword ptr [rax+18h], xmm0
0x100436b5d  mov     rbx, [rsp+38h+arg_0]
0x100436b62  mov     rbp, [rsp+38h+arg_8]
0x100436b67  mov     rsi, [rsp+38h+arg_10]
0x100436b6c  add     rsp, 30h
0x100436b70  pop     rdi
0x100436b71  retn
```
