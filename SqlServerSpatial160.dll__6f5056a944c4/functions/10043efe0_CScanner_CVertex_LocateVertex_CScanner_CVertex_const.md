# CScanner::CVertex::LocateVertex(CScanner::CVertex const *)

- ea: `0x10043efe0`
- end: `0x10043f136`
- name: `?LocateVertex@CVertex@CScanner@@QEBA?AW4SIDEINDICATOR@CLineSegmentIntersection@RobustIntersections@@PEBV12@@Z`
- size: `342`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1004415c0`
- `0x1004425b0`

## callees

- `0x10043efe0`
- `0x100447250`
- `0x100447890`

## pseudocode

```c
__int64 __fastcall CScanner::CVertex::LocateVertex(__int64 a1, __int64 a2)
{
  unsigned int v2; // r8d
  __int64 v4; // rax
  double v5; // xmm0_8
  double v6; // xmm1_8
  double v7; // xmm2_8
  double v8; // xmm5_8
  double v9; // xmm6_8
  double v10; // xmm3_8
  double v11; // xmm3_8
  int v13; // edx
  __int64 v14; // rax
  __int64 v15; // rax
  __int128 v16; // xmm0
  double *v17; // rcx
  __int128 v18; // [rsp+20h] [rbp-38h] BYREF
  __int64 v19; // [rsp+30h] [rbp-28h]
  __int64 v20; // [rsp+38h] [rbp-20h]

  v2 = 0;
  if ( (*(_BYTE *)(a2 + 16) & 5) != 0 )
  {
    v4 = *(_QWORD *)(a1 + 40);
    if ( *(_DWORD *)(a1 + 16) == 1 )
    {
      v5 = *(double *)(a1 + 48);
      v6 = *(double *)(a1 + 56);
    }
    else
    {
      v5 = *(double *)(v4 + 48);
      v6 = *(double *)(v4 + 56);
      v4 = *(_QWORD *)(v4 + 40);
    }
    v7 = *(double *)(a2 + 48) - v5;
    v8 = *(double *)(v4 + 48) - v5;
    v9 = *(double *)(v4 + 56) - v6;
    v10 = *(double *)(a2 + 56) - v6;
    if ( COERCE_DOUBLE(*(_QWORD *)&v8 & _xmm) <= 67108864.0
      && COERCE_DOUBLE(*(_QWORD *)&v9 & _xmm) <= 67108864.0
      && COERCE_DOUBLE(*(_QWORD *)&v7 & _xmm) <= 67108864.0
      && COERCE_DOUBLE(*(_QWORD *)&v10 & _xmm) <= 67108864.0 )
    {
      v11 = v10 * v8 - v7 * v9;
      if ( v11 > 0.0 )
        return 1;
      LOBYTE(v2) = v11 >= 0.0;
      return v2 - 1;
    }
    return (unsigned int)ComputeDeterminantExactSign(v8, v9, v7, v10);
  }
  v13 = *(_DWORD *)(a1 + 16);
  v14 = a1;
  if ( v13 != 1 )
    v14 = *(_QWORD *)(a1 + 40);
  if ( *(_QWORD *)(a2 + 56) == v14 )
    return v2;
  v15 = *(_QWORD *)(a1 + 40);
  if ( v13 == 1 )
  {
    v16 = *(_OWORD *)(a1 + 48);
  }
  else
  {
    v16 = *(_OWORD *)(v15 + 48);
    v15 = *(_QWORD *)(v15 + 40);
  }
  v17 = *(double **)(a2 + 64);
  v18 = v16;
  v19 = *(_QWORD *)(v15 + 48);
  v20 = *(_QWORD *)(v15 + 56);
  return RobustIntersections::CLineSegmentIntersection::LocateTransverseIntersectionRelativeToLine(v17, (double *)&v18);
}

```

## disassembly

```asm
0x10043efe0  sub     rsp, 58h
0x10043efe4  xor     r8d, r8d
0x10043efe7  mov     r9, rdx
0x10043efea  test    byte ptr [rdx+10h], 5
0x10043efee  jz      loc_10043F0DC
0x10043eff4  cmp     dword ptr [rcx+10h], 1
0x10043eff8  movsd   xmm2, qword ptr [rdx+30h]
0x10043effd  movsd   xmm3, qword ptr [rdx+38h]
0x10043f002  mov     rax, [rcx+28h]
0x10043f006  movaps  [rsp+58h+var_18], xmm6
0x10043f00b  jnz     short loc_10043F019
0x10043f00d  movsd   xmm0, qword ptr [rcx+30h]
0x10043f012  movsd   xmm1, qword ptr [rcx+38h]
0x10043f017  jmp     short loc_10043F027
0x10043f019  movsd   xmm0, qword ptr [rax+30h]
0x10043f01e  movsd   xmm1, qword ptr [rax+38h]
0x10043f023  mov     rax, [rax+28h]
0x10043f027  movsd   xmm5, qword ptr [rax+30h]
0x10043f02c  subsd   xmm2, xmm0
0x10043f030  movsd   xmm6, qword ptr [rax+38h]
0x10043f035  subsd   xmm5, xmm0
0x10043f039  movsd   xmm4, cs:__real@4190000000000000
0x10043f041  subsd   xmm6, xmm1
0x10043f045  subsd   xmm3, xmm1
0x10043f049  movsd   xmm1, qword ptr cs:__xmm@7fffffffffffffff7fffffffffffffff
0x10043f051  movaps  xmm0, xmm5
0x10043f054  andps   xmm0, xmm1
0x10043f057  comisd  xmm4, xmm0
0x10043f05b  jb      short loc_10043F0C1
0x10043f05d  movaps  xmm0, xmm6
0x10043f060  andps   xmm0, xmm1
0x10043f063  comisd  xmm4, xmm0
0x10043f067  jb      short loc_10043F0C1
0x10043f069  movaps  xmm0, xmm2
0x10043f06c  andps   xmm0, xmm1
0x10043f06f  comisd  xmm4, xmm0
0x10043f073  jb      short loc_10043F0C1
0x10043f075  movaps  xmm0, xmm3
0x10043f078  andps   xmm0, xmm1
0x10043f07b  comisd  xmm4, xmm0
0x10043f07f  jb      short loc_10043F0C1
0x10043f081  mulsd   xmm3, xmm5
0x10043f085  xorps   xmm0, xmm0
0x10043f088  mulsd   xmm2, xmm6
0x10043f08c  subsd   xmm3, xmm2
0x10043f090  comisd  xmm3, xmm0
0x10043f094  jbe     short loc_10043F0A9
0x10043f096  movaps  xmm6, [rsp+58h+var_18]
0x10043f09b  mov     r8d, 1
0x10043f0a1  mov     eax, r8d
0x10043f0a4  add     rsp, 58h
0x10043f0a8  retn
0x10043f0a9  movaps  xmm6, [rsp+58h+var_18]
0x10043f0ae  comisd  xmm0, xmm3
0x10043f0b2  setbe   r8b
0x10043f0b6  dec     r8d
0x10043f0b9  mov     eax, r8d
0x10043f0bc  add     rsp, 58h
0x10043f0c0  retn
0x10043f0c1  movaps  xmm1, xmm6
0x10043f0c4  movaps  xmm0, xmm5
0x10043f0c7  call    ?ComputeDeterminantExactSign@@YA?AW4SIGNINDICATOR@RobustIntersections@@NNNN@Z; ComputeDeterminantExactSign(double,double,double,double)
0x10043f0cc  movaps  xmm6, [rsp+58h+var_18]
0x10043f0d1  mov     r8d, eax
0x10043f0d4  mov     eax, r8d
0x10043f0d7  add     rsp, 58h
0x10043f0db  retn
0x10043f0dc  mov     edx, [rcx+10h]
0x10043f0df  mov     rax, rcx
0x10043f0e2  cmp     edx, 1
0x10043f0e5  jz      short loc_10043F0EB
0x10043f0e7  mov     rax, [rcx+28h]
0x10043f0eb  cmp     [r9+38h], rax
0x10043f0ef  jz      short loc_10043F0D4
0x10043f0f1  mov     rax, [rcx+28h]
0x10043f0f5  cmp     edx, 1
0x10043f0f8  jnz     short loc_10043F100
0x10043f0fa  movups  xmm0, xmmword ptr [rcx+30h]
0x10043f0fe  jmp     short loc_10043F108
0x10043f100  movups  xmm0, xmmword ptr [rax+30h]
0x10043f104  mov     rax, [rax+28h]
0x10043f108  mov     rcx, [r9+40h]
0x10043f10c  lea     rdx, [rsp+58h+var_38]
0x10043f111  movups  [rsp+58h+var_38], xmm0
0x10043f116  movsd   xmm0, qword ptr [rax+30h]
0x10043f11b  movsd   [rsp+58h+var_28], xmm0
0x10043f121  movsd   xmm0, qword ptr [rax+38h]
0x10043f126  movsd   [rsp+58h+var_20], xmm0
0x10043f12c  call    ?LocateTransverseIntersectionRelativeToLine@CLineSegmentIntersection@RobustIntersections@@QEBA?AW4SIDEINDICATOR@12@QEBN@Z; RobustIntersections::CLineSegmentIntersection::LocateTransverseIntersectionRelativeToLine(double const * const)
0x10043f131  add     rsp, 58h
0x10043f135  retn
```
