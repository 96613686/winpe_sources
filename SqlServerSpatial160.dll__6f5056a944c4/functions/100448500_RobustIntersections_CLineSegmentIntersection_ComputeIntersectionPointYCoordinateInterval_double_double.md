# RobustIntersections::CLineSegmentIntersection::ComputeIntersectionPointYCoordinateInterval(double &,double &)

- ea: `0x100448500`
- end: `0x100448783`
- name: `?ComputeIntersectionPointYCoordinateInterval@CLineSegmentIntersection@RobustIntersections@@AEBAXAEAN0@Z`
- size: `643`
- prototype: `void __fastcall(RobustIntersections::CLineSegmentIntersection *__hidden this, double *, double *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x100448160`

## callees

- `0x100448500`

## pseudocode

```c
void __fastcall RobustIntersections::CLineSegmentIntersection::ComputeIntersectionPointYCoordinateInterval(
        RobustIntersections::CLineSegmentIntersection *this,
        double *a2,
        double *a3)
{
  __int64 v3; // xmm0_8
  __int64 v4; // rax
  __int64 v5; // rax
  double v6; // xmm1_8
  __int64 v7; // rax
  double v8; // xmm2_8
  double v9; // xmm0_8
  unsigned __int64 v10; // rax
  double v11; // xmm1_8
  __int64 v12; // rax
  double v13; // xmm2_8
  double v14; // rax
  __int64 v15; // xmm0_8
  __int64 v16; // rax
  double v17; // xmm2_8
  double v18; // xmm0_8
  unsigned __int64 v19; // rax
  double v20; // xmm1_8
  __int64 v21; // rax
  double v22; // xmm2_8
  __int64 v23; // [rsp+8h] [rbp+8h]
  __int64 v24; // [rsp+8h] [rbp+8h]
  double v25; // [rsp+8h] [rbp+8h]
  double v26; // [rsp+8h] [rbp+8h]
  unsigned __int64 v27; // [rsp+8h] [rbp+8h]
  __int64 v28; // [rsp+8h] [rbp+8h]
  double v29; // [rsp+10h] [rbp+10h]
  double v30; // [rsp+10h] [rbp+10h]
  double v31; // [rsp+10h] [rbp+10h]
  unsigned __int64 v32; // [rsp+10h] [rbp+10h]

  v3 = COERCE_UNSIGNED_INT64(*((double *)this + 9) / *((double *)this + 8)) & _xmm;
  if ( v3 < 0 )
  {
    v4 = v3 + 1;
  }
  else
  {
    if ( (v3 & 0x7FFFFFFFFFFFFFFFLL) == 0 )
    {
      *(_QWORD *)&v29 = 0x8000000000000001uLL;
      goto LABEL_7;
    }
    v4 = v3 - 1;
  }
  v29 = *(double *)&v4;
LABEL_7:
  if ( v3 >= 0 )
  {
    v5 = v3 + 1;
  }
  else
  {
    if ( (v3 & 0x7FFFFFFFFFFFFFFFLL) == 0 )
    {
      v23 = 1;
      goto LABEL_13;
    }
    v5 = v3 - 1;
  }
  v23 = v5;
LABEL_13:
  v6 = *((double *)this + 1);
  if ( v6 > 0.0 )
  {
    v30 = v6 * v29;
    if ( v30 < 0.0 )
    {
      v7 = *(_QWORD *)&v30 + 1LL;
    }
    else
    {
      if ( (*(_QWORD *)&v30 & 0x7FFFFFFFFFFFFFFFLL) == 0 )
      {
        *(_QWORD *)&v31 = 0x8000000000000001uLL;
        goto LABEL_20;
      }
      v7 = *(_QWORD *)&v30 - 1LL;
    }
    v31 = *(double *)&v7;
LABEL_20:
    v8 = *((double *)this + 7);
    v9 = v8 + v31;
    if ( COERCE__INT64(v8 + v31) < 0 )
    {
      v10 = *(_QWORD *)&v9 + 1LL;
    }
    else
    {
      if ( !fabs(*((double *)this + 7) + v31) )
      {
        v32 = 0x8000000000000001uLL;
        goto LABEL_26;
      }
      v10 = *(_QWORD *)&v9 - 1LL;
    }
    v32 = v10;
LABEL_26:
    v11 = v6 * *(double *)&v23;
    *(_QWORD *)a2 = v32;
    if ( v11 >= 0.0 )
    {
      v12 = *(_QWORD *)&v11 + 1LL;
    }
    else
    {
      if ( (*(_QWORD *)&v11 & 0x7FFFFFFFFFFFFFFFLL) == 0 )
      {
        v24 = 1;
        goto LABEL_32;
      }
      v12 = *(_QWORD *)&v11 - 1LL;
    }
    v24 = v12;
LABEL_32:
    v13 = v8 + *(double *)&v24;
    v14 = v13;
    if ( v13 < 0.0 )
    {
      if ( (*(_QWORD *)&v13 & 0x7FFFFFFFFFFFFFFFLL) != 0 )
      {
LABEL_34:
        *(_QWORD *)a3 = *(_QWORD *)&v14 - 1LL;
        return;
      }
      goto LABEL_57;
    }
    goto LABEL_58;
  }
  if ( v6 == 0.0 )
  {
    v15 = *((_QWORD *)this + 7);
    *(_QWORD *)a2 = v15;
    *(_QWORD *)a3 = v15;
    return;
  }
  v25 = v6 * *(double *)&v23;
  if ( v25 < 0.0 )
  {
    v16 = *(_QWORD *)&v25 + 1LL;
  }
  else
  {
    if ( (*(_QWORD *)&v25 & 0x7FFFFFFFFFFFFFFFLL) == 0 )
    {
      *(_QWORD *)&v26 = 0x8000000000000001uLL;
      goto LABEL_43;
    }
    v16 = *(_QWORD *)&v25 - 1LL;
  }
  v26 = *(double *)&v16;
LABEL_43:
  v17 = *((double *)this + 7);
  v18 = v17 + v26;
  if ( COERCE__INT64(v17 + v26) < 0 )
  {
    v19 = *(_QWORD *)&v18 + 1LL;
  }
  else
  {
    if ( !fabs(*((double *)this + 7) + v26) )
    {
      v27 = 0x8000000000000001uLL;
      goto LABEL_49;
    }
    v19 = *(_QWORD *)&v18 - 1LL;
  }
  v27 = v19;
LABEL_49:
  v20 = v6 * v29;
  *(_QWORD *)a2 = v27;
  if ( v20 >= 0.0 )
  {
    v21 = *(_QWORD *)&v20 + 1LL;
  }
  else
  {
    if ( (*(_QWORD *)&v20 & 0x7FFFFFFFFFFFFFFFLL) == 0 )
    {
      v28 = 1;
      goto LABEL_55;
    }
    v21 = *(_QWORD *)&v20 - 1LL;
  }
  v28 = v21;
LABEL_55:
  v22 = v17 + *(double *)&v28;
  v14 = v22;
  if ( v22 < 0.0 )
  {
    if ( (*(_QWORD *)&v22 & 0x7FFFFFFFFFFFFFFFLL) != 0 )
      goto LABEL_34;
LABEL_57:
    *(_QWORD *)a3 = 1;
    return;
  }
LABEL_58:
  *(_QWORD *)a3 = *(_QWORD *)&v14 + 1LL;
}

```

## disassembly

```asm
0x100448500  movsd   xmm0, qword ptr [rcx+48h]
0x100448505  mov     r11, 8000000000000001h
0x10044850f  divsd   xmm0, qword ptr [rcx+40h]
0x100448514  mov     r9, 7FFFFFFFFFFFFFFFh
0x10044851e  andps   xmm0, cs:__xmm@7fffffffffffffff7fffffffffffffff
0x100448525  movsd   [rsp+arg_8], xmm0
0x10044852b  mov     rax, [rsp+arg_8]
0x100448530  bt      rax, 3Fh ; '?'
0x100448535  jb      short loc_100448548
0x100448537  test    r9, rax
0x10044853a  jz      short loc_100448541
0x10044853c  dec     rax
0x10044853f  jmp     short loc_10044854B
0x100448541  mov     [rsp+arg_8], r11
0x100448546  jmp     short loc_100448550
0x100448548  inc     rax
0x10044854b  mov     [rsp+arg_8], rax
0x100448550  movsd   [rsp+arg_0], xmm0
0x100448556  mov     rax, [rsp+arg_0]
0x10044855b  bt      rax, 3Fh ; '?'
0x100448560  jnb     short loc_100448577
0x100448562  test    r9, rax
0x100448565  jz      short loc_10044856C
0x100448567  dec     rax
0x10044856a  jmp     short loc_10044857A
0x10044856c  mov     [rsp+arg_0], 1
0x100448575  jmp     short loc_10044857F
0x100448577  inc     rax
0x10044857a  mov     [rsp+arg_0], rax
0x10044857f  movsd   xmm1, qword ptr [rcx+8]
0x100448584  xorps   xmm0, xmm0
0x100448587  comisd  xmm1, xmm0
0x10044858b  jbe     loc_100448676
0x100448591  movaps  xmm0, xmm1
0x100448594  mulsd   xmm0, [rsp+arg_8]
0x10044859a  movsd   [rsp+arg_8], xmm0
0x1004485a0  mov     rax, [rsp+arg_8]
0x1004485a5  bt      rax, 3Fh ; '?'
0x1004485aa  jb      short loc_1004485BD
0x1004485ac  test    r9, rax
0x1004485af  jz      short loc_1004485B6
0x1004485b1  dec     rax
0x1004485b4  jmp     short loc_1004485C0
0x1004485b6  mov     [rsp+arg_8], r11
0x1004485bb  jmp     short loc_1004485C5
0x1004485bd  inc     rax
0x1004485c0  mov     [rsp+arg_8], rax
0x1004485c5  movsd   xmm2, qword ptr [rcx+38h]
0x1004485ca  movaps  xmm0, xmm2
0x1004485cd  addsd   xmm0, [rsp+arg_8]
0x1004485d3  movsd   [rsp+arg_8], xmm0
0x1004485d9  mov     rax, [rsp+arg_8]
0x1004485de  bt      rax, 3Fh ; '?'
0x1004485e3  jb      short loc_1004485F6
0x1004485e5  test    r9, rax
0x1004485e8  jz      short loc_1004485EF
0x1004485ea  dec     rax
0x1004485ed  jmp     short loc_1004485F9
0x1004485ef  mov     [rsp+arg_8], r11
0x1004485f4  jmp     short loc_1004485FE
0x1004485f6  inc     rax
0x1004485f9  mov     [rsp+arg_8], rax
0x1004485fe  mulsd   xmm1, [rsp+arg_0]
0x100448604  movsd   xmm0, [rsp+arg_8]
0x10044860a  movsd   qword ptr [rdx], xmm0
0x10044860e  movsd   [rsp+arg_0], xmm1
0x100448614  mov     rax, [rsp+arg_0]
0x100448619  bt      rax, 3Fh ; '?'
0x10044861e  jnb     short loc_100448635
0x100448620  test    r9, rax
0x100448623  jz      short loc_10044862A
0x100448625  dec     rax
0x100448628  jmp     short loc_100448638
0x10044862a  mov     [rsp+arg_0], 1
0x100448633  jmp     short loc_10044863D
0x100448635  inc     rax
0x100448638  mov     [rsp+arg_0], rax
0x10044863d  addsd   xmm2, [rsp+arg_0]
0x100448643  movsd   [rsp+arg_0], xmm2
0x100448649  mov     rax, [rsp+arg_0]
0x10044864e  bt      rax, 3Fh ; '?'
0x100448653  jnb     loc_10044876F
0x100448659  test    r9, rax
0x10044865c  jz      loc_10044875A
0x100448662  dec     rax
0x100448665  mov     [rsp+arg_0], rax
0x10044866a  movsd   xmm0, [rsp+arg_0]
0x100448670  movsd   qword ptr [r8], xmm0
0x100448675  retn
0x100448676  ucomisd xmm1, xmm0
0x10044867a  jp      short loc_10044868D
0x10044867c  jnz     short loc_10044868D
0x10044867e  movsd   xmm0, qword ptr [rcx+38h]
0x100448683  movsd   qword ptr [rdx], xmm0
0x100448687  movsd   qword ptr [r8], xmm0
0x10044868c  retn
0x10044868d  movaps  xmm0, xmm1
0x100448690  mulsd   xmm0, [rsp+arg_0]
0x100448696  movsd   [rsp+arg_0], xmm0
0x10044869c  mov     rax, [rsp+arg_0]
0x1004486a1  bt      rax, 3Fh ; '?'
0x1004486a6  jb      short loc_1004486B9
0x1004486a8  test    r9, rax
0x1004486ab  jz      short loc_1004486B2
0x1004486ad  dec     rax
0x1004486b0  jmp     short loc_1004486BC
0x1004486b2  mov     [rsp+arg_0], r11
0x1004486b7  jmp     short loc_1004486C1
0x1004486b9  inc     rax
0x1004486bc  mov     [rsp+arg_0], rax
0x1004486c1  movsd   xmm2, qword ptr [rcx+38h]
0x1004486c6  movaps  xmm0, xmm2
0x1004486c9  addsd   xmm0, [rsp+arg_0]
0x1004486cf  movsd   [rsp+arg_0], xmm0
0x1004486d5  mov     rax, [rsp+arg_0]
0x1004486da  bt      rax, 3Fh ; '?'
0x1004486df  jb      short loc_1004486F2
0x1004486e1  test    r9, rax
0x1004486e4  jz      short loc_1004486EB
0x1004486e6  dec     rax
0x1004486e9  jmp     short loc_1004486F5
0x1004486eb  mov     [rsp+arg_0], r11
0x1004486f0  jmp     short loc_1004486FA
0x1004486f2  inc     rax
0x1004486f5  mov     [rsp+arg_0], rax
0x1004486fa  movsd   xmm0, [rsp+arg_0]
0x100448700  mulsd   xmm1, [rsp+arg_8]
0x100448706  movsd   qword ptr [rdx], xmm0
0x10044870a  movsd   [rsp+arg_0], xmm1
0x100448710  mov     rax, [rsp+arg_0]
0x100448715  bt      rax, 3Fh ; '?'
0x10044871a  jnb     short loc_100448731
0x10044871c  test    r9, rax
0x10044871f  jz      short loc_100448726
0x100448721  dec     rax
0x100448724  jmp     short loc_100448734
0x100448726  mov     [rsp+arg_0], 1
0x10044872f  jmp     short loc_100448739
0x100448731  inc     rax
0x100448734  mov     [rsp+arg_0], rax
0x100448739  addsd   xmm2, [rsp+arg_0]
0x10044873f  movsd   [rsp+arg_0], xmm2
0x100448745  mov     rax, [rsp+arg_0]
0x10044874a  bt      rax, 3Fh ; '?'
0x10044874f  jnb     short loc_10044876F
0x100448751  test    r9, rax
0x100448754  jnz     loc_100448662
0x10044875a  mov     [rsp+arg_0], 1
0x100448763  movsd   xmm0, [rsp+arg_0]
0x100448769  movsd   qword ptr [r8], xmm0
0x10044876e  retn
0x10044876f  inc     rax
0x100448772  mov     [rsp+arg_0], rax
0x100448777  movsd   xmm0, [rsp+arg_0]
0x10044877d  movsd   qword ptr [r8], xmm0
0x100448782  retn
```
