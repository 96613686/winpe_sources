# RobustIntersections::CLineSegmentIntersection::YXSortTransverseIntersectionAndPoint(RobustIntersections::CLineSegmentIntersection const &,double const * const)

- ea: `0x100448310`
- end: `0x1004484ed`
- name: `?YXSortTransverseIntersectionAndPoint@CLineSegmentIntersection@RobustIntersections@@SA?AW4COMPARISON@2@AEBV12@QEBN@Z`
- size: `477`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x10043ef20`
- `0x10043f140`
- `0x100449740`

## callees

- `0x100448310`
- `0x1004499a0`
- `0x100449c10`

## pseudocode

```c
__int64 __fastcall RobustIntersections::CLineSegmentIntersection::YXSortTransverseIntersectionAndPoint(
        __int64 a1,
        double *a2,
        __int64 a3)
{
  double v3; // xmm5_8
  double v4; // xmm7_8
  double v6; // xmm2_8
  double v8; // xmm0_8
  double v9; // xmm1_8
  double v10; // xmm4_8
  double v11; // xmm6_8
  double v12; // xmm3_8
  unsigned int v13; // ecx
  double v14; // xmm4_8
  double v15; // xmm3_8
  double v16; // xmm6_8
  double v17; // xmm0_8
  double v18; // xmm1_8
  double v19; // xmm0_8
  double v20; // xmm3_8
  double v21; // xmm4_8
  unsigned int v22; // eax
  char v23; // r8

  v3 = *(double *)(a1 + 56);
  LOBYTE(a3) = 0;
  v4 = *(double *)(a1 + 8);
  v6 = v3 + *(double *)(a1 + 40);
  v8 = v4 + v3;
  v9 = v6 - *(double *)(a1 + 24);
  if ( v3 <= v4 + v3 )
  {
    v10 = *(double *)(a1 + 8) + v3;
    v8 = *(double *)(a1 + 56);
  }
  else
  {
    v10 = *(double *)(a1 + 56);
  }
  if ( v6 <= v9 )
  {
    v11 = v6 - *(double *)(a1 + 24);
    v9 = *(double *)(a1 + 56) + *(double *)(a1 + 40);
  }
  else
  {
    v11 = *(double *)(a1 + 56) + *(double *)(a1 + 40);
  }
  v12 = a2[1];
  if ( fmax(v8, v9) <= v12 )
  {
    if ( v12 > fmin(v10, v11) )
      return (unsigned int)-1;
    if ( *(_BYTE *)(a1 + 113) && *(_BYTE *)(a1 + 112) )
    {
      v14 = *(double *)(a1 + 72);
      v15 = v12 - v3;
      v16 = *(double *)(a1 + 64);
      v17 = v14 * v4;
      v18 = v15 * v16;
      if ( v14 * v4 != v15 * v16 )
      {
        if ( *(_DWORD *)(a1 + 100) == 1 )
        {
          v22 = -1;
          if ( v17 > v18 )
            return 1;
        }
        else
        {
          v22 = 1;
          if ( v17 > v18 )
            return (unsigned int)-1;
        }
        return v22;
      }
      if ( COERCE_DOUBLE(*(_QWORD *)&v14 & _xmm) <= 67108864.0
        && COERCE_DOUBLE(*(_QWORD *)&v4 & _xmm) <= 67108864.0
        && COERCE_DOUBLE(*(_QWORD *)&v16 & _xmm) <= 67108864.0
        && COERCE_DOUBLE(*(_QWORD *)&v15 & _xmm) <= 67108864.0 )
      {
        LOBYTE(a3) = 1;
        v19 = *a2 - *(double *)(a1 + 48);
        v20 = *(double *)a1 * v14;
        v21 = v19 * v16;
        if ( v20 != v19 * v16 )
        {
          if ( *(_DWORD *)(a1 + 100) == 1 )
          {
            v22 = -1;
            if ( v20 > v21 )
              return 1;
          }
          else
          {
            v22 = 1;
            if ( v20 > v21 )
              return (unsigned int)-1;
          }
          return v22;
        }
        if ( COERCE_DOUBLE(*(_QWORD *)a1 & _xmm) <= 67108864.0 && COERCE_DOUBLE(*(_QWORD *)&v19 & _xmm) <= 67108864.0 )
          return 0;
      }
    }
    v13 = RobustIntersections::CLineSegmentIntersection::YXSortTransverseIntersectionAndPointUsingIntervalArithmetic(
            a1,
            a2,
            a3);
    if ( v13 != 0x80000000 )
      return v13;
    return (unsigned int)RobustIntersections::CLineSegmentIntersection::YXSortTransverseIntersectionAndPointUsingExactArithmetic(
                           a1,
                           a2,
                           v23);
  }
  return 1;
}

```

## disassembly

```asm
0x100448310  mov     [rsp+arg_0], rbx
0x100448315  push    rdi
0x100448316  sub     rsp, 40h
0x10044831a  movsd   xmm5, qword ptr [rcx+38h]
0x10044831f  xor     r8b, r8b
0x100448322  movaps  xmm2, xmm5
0x100448325  movaps  [rsp+48h+var_28], xmm7
0x10044832a  movsd   xmm7, qword ptr [rcx+8]
0x10044832f  mov     rdi, rdx
0x100448332  addsd   xmm2, qword ptr [rcx+28h]
0x100448337  movaps  xmm0, xmm7
0x10044833a  mov     rbx, rcx
0x10044833d  addsd   xmm0, xmm5
0x100448341  movaps  xmm1, xmm2
0x100448344  subsd   xmm1, qword ptr [rcx+18h]
0x100448349  comisd  xmm5, xmm0
0x10044834d  jbe     short loc_100448354
0x10044834f  movaps  xmm4, xmm5
0x100448352  jmp     short loc_10044835A
0x100448354  movaps  xmm4, xmm0
0x100448357  movaps  xmm0, xmm5
0x10044835a  comisd  xmm2, xmm1
0x10044835e  movaps  [rsp+48h+var_18], xmm6
0x100448363  jbe     short loc_10044836A
0x100448365  movaps  xmm6, xmm2
0x100448368  jmp     short loc_100448370
0x10044836a  movaps  xmm6, xmm1
0x10044836d  movaps  xmm1, xmm2
0x100448370  movsd   xmm3, qword ptr [rdx+8]
0x100448375  maxsd   xmm0, xmm1
0x100448379  comisd  xmm0, xmm3
0x10044837d  jbe     short loc_100448389
0x10044837f  mov     ecx, 1
0x100448384  jmp     loc_1004484D6
0x100448389  minsd   xmm4, xmm6
0x10044838d  comisd  xmm3, xmm4
0x100448391  jbe     short loc_10044839D
0x100448393  mov     ecx, 0FFFFFFFFh
0x100448398  jmp     loc_1004484D6
0x10044839d  cmp     [rcx+71h], r8b
0x1004483a1  jz      loc_1004484BB
0x1004483a7  cmp     [rcx+70h], r8b
0x1004483ab  jz      loc_1004484BB
0x1004483b1  movsd   xmm4, qword ptr [rcx+48h]
0x1004483b6  subsd   xmm3, xmm5
0x1004483ba  movsd   xmm6, qword ptr [rcx+40h]
0x1004483bf  movaps  xmm0, xmm4
0x1004483c2  mulsd   xmm0, xmm7
0x1004483c6  movaps  xmm1, xmm3
0x1004483c9  mulsd   xmm1, xmm6
0x1004483cd  ucomisd xmm0, xmm1
0x1004483d1  jp      loc_10044848F
0x1004483d7  jnz     loc_10044848F
0x1004483dd  movsd   xmm1, qword ptr cs:__xmm@7fffffffffffffff7fffffffffffffff
0x1004483e5  movaps  xmm0, xmm4
0x1004483e8  movsd   xmm2, cs:__real@4190000000000000
0x1004483f0  andps   xmm0, xmm1
0x1004483f3  comisd  xmm2, xmm0
0x1004483f7  jb      loc_1004484BB
0x1004483fd  andps   xmm7, xmm1
0x100448400  comisd  xmm2, xmm7
0x100448404  jb      loc_1004484BB
0x10044840a  movaps  xmm0, xmm6
0x10044840d  andps   xmm0, xmm1
0x100448410  comisd  xmm2, xmm0
0x100448414  jb      loc_1004484BB
0x10044841a  andps   xmm3, xmm1
0x10044841d  comisd  xmm2, xmm3
0x100448421  jb      loc_1004484BB
0x100448427  movsd   xmm0, qword ptr [rdx]
0x10044842b  mov     r8b, 1
0x10044842e  subsd   xmm0, qword ptr [rcx+30h]
0x100448433  movsd   xmm5, qword ptr [rcx]
0x100448437  movaps  xmm3, xmm5
0x10044843a  mulsd   xmm3, xmm4
0x10044843e  movaps  xmm4, xmm0
0x100448441  mulsd   xmm4, xmm6
0x100448445  ucomisd xmm3, xmm4
0x100448449  jp      short loc_100448463
0x10044844b  jnz     short loc_100448463
0x10044844d  andps   xmm5, xmm1
0x100448450  comisd  xmm2, xmm5
0x100448454  jb      short loc_1004484BB
0x100448456  andps   xmm0, xmm1
0x100448459  comisd  xmm2, xmm0
0x10044845d  jb      short loc_1004484BB
0x10044845f  xor     ecx, ecx
0x100448461  jmp     short loc_1004484D6
0x100448463  cmp     dword ptr [rcx+64h], 1
0x100448467  jnz     short loc_10044847C
0x100448469  comisd  xmm3, xmm4
0x10044846d  mov     eax, 0FFFFFFFFh
0x100448472  mov     ecx, 1
0x100448477  cmova   eax, ecx
0x10044847a  jmp     short loc_1004484D4
0x10044847c  comisd  xmm3, xmm4
0x100448480  mov     eax, 1
0x100448485  mov     ecx, 0FFFFFFFFh
0x10044848a  cmova   eax, ecx
0x10044848d  jmp     short loc_1004484D4
0x10044848f  cmp     dword ptr [rcx+64h], 1
0x100448493  jnz     short loc_1004484A8
0x100448495  comisd  xmm0, xmm1
0x100448499  mov     eax, 0FFFFFFFFh
0x10044849e  mov     ecx, 1
0x1004484a3  cmova   eax, ecx
0x1004484a6  jmp     short loc_1004484D4
0x1004484a8  comisd  xmm0, xmm1
0x1004484ac  mov     eax, 1
0x1004484b1  mov     ecx, 0FFFFFFFFh
0x1004484b6  cmova   eax, ecx
0x1004484b9  jmp     short loc_1004484D4
0x1004484bb  call    ?YXSortTransverseIntersectionAndPointUsingIntervalArithmetic@CLineSegmentIntersection@RobustIntersections@@CA?AW4COMPARISON@2@AEBV12@QEBN_N@Z; RobustIntersections::CLineSegmentIntersection::YXSortTransverseIntersectionAndPointUsingIntervalArithmetic(RobustIntersections::CLineSegmentIntersection const &,double const * const,bool)
0x1004484c0  mov     ecx, eax
0x1004484c2  cmp     eax, 80000000h
0x1004484c7  jnz     short loc_1004484D6
0x1004484c9  mov     rdx, rdi
0x1004484cc  mov     rcx, rbx
0x1004484cf  call    ?YXSortTransverseIntersectionAndPointUsingExactArithmetic@CLineSegmentIntersection@RobustIntersections@@CA?AW4COMPARISON@2@AEBV12@QEBN_N@Z; RobustIntersections::CLineSegmentIntersection::YXSortTransverseIntersectionAndPointUsingExactArithmetic(RobustIntersections::CLineSegmentIntersection const &,double const * const,bool)
0x1004484d4  mov     ecx, eax
0x1004484d6  movaps  xmm6, [rsp+48h+var_18]
0x1004484db  mov     eax, ecx
0x1004484dd  mov     rbx, [rsp+48h+arg_0]
0x1004484e2  movaps  xmm7, [rsp+48h+var_28]
0x1004484e7  add     rsp, 40h
0x1004484eb  pop     rdi
0x1004484ec  retn
```
