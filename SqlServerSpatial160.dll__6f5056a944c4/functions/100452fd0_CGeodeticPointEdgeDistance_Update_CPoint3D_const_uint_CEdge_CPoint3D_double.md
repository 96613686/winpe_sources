# CGeodeticPointEdgeDistance::Update(CPoint3D const &,uint,CEdge<CPoint3D,double> *)

- ea: `0x100452fd0`
- end: `0x1004532d4`
- name: `?Update@CGeodeticPointEdgeDistance@@QEAAXAEBVCPoint3D@@IPEAV?$CEdge@VCPoint3D@@N@@@Z`
- size: `772`
- prototype: `__int64 __fastcall(CGeodeticPointEdgeDistance *this)`
- caller_count: `4`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x100409450`
- `0x100455310`
- `0x1004553d0`
- `0x1004556e0`

## callees

- `0x100452fd0`
- `0x1004532e0`
- `0x100453640`
- `0x100468a30`
- `0x100469a98`
- `0x100469af8`

## pseudocode

```c
void __fastcall CGeodeticPointEdgeDistance::Update(CGeodeticPointEdgeDistance *this, _QWORD *a2, int a3, _DWORD *a4)
{
  double v8; // xmm0_8
  __int64 v9; // rcx
  double v10; // xmm6_8
  double v11; // xmm0_8
  __int64 v12; // rdx
  double v13; // xmm0_8
  __m128d v14; // xmm0
  __int64 v15; // xmm1_8
  __int64 v16; // xmm4_8
  __int64 v17; // xmm3_8
  __int64 v18; // xmm2_8
  __int64 v19; // rdx
  __int64 v20; // rax
  __int64 v21; // rcx
  __int64 v22; // [rsp+20h] [rbp-E8h] BYREF
  __int64 v23; // [rsp+28h] [rbp-E0h]
  __int64 v24; // [rsp+30h] [rbp-D8h]
  __int128 v25; // [rsp+38h] [rbp-D0h] BYREF
  __int128 v26; // [rsp+50h] [rbp-B8h] BYREF

  v8 = (*(double (__fastcall **)(_DWORD *, _QWORD *, __int64 *))(*(_QWORD *)a4 + 40LL))(a4, a2, &v22);
  v9 = *((_QWORD *)this + 90);
  if ( *(_BYTE *)(v9 + 8) )
  {
    if ( a3 )
    {
      if ( *(double *)(v9 + 32) > v8 )
      {
        *(_QWORD *)(v9 + 40) = *a2;
        *(_QWORD *)(v9 + 48) = a2[1];
        *(_QWORD *)(v9 + 56) = a2[2];
        *(_QWORD *)(v9 + 64) = v22;
        *(_QWORD *)(v9 + 72) = v23;
        *(_QWORD *)(v9 + 80) = v24;
        *(double *)(v9 + 32) = v8;
      }
    }
    else if ( *(double *)(v9 + 32) > v8 )
    {
      *(_QWORD *)(v9 + 40) = v22;
      *(_QWORD *)(v9 + 48) = v23;
      *(_QWORD *)(v9 + 56) = v24;
      *(_QWORD *)(v9 + 64) = *a2;
      *(_QWORD *)(v9 + 72) = a2[1];
      *(_QWORD *)(v9 + 80) = a2[2];
      *(double *)(v9 + 32) = v8;
    }
  }
  else
  {
    v10 = *(double *)(v9 + 24);
    if ( v8 < v10 )
    {
      v11 = v8 < 0.0 ? sqrt_0(v8) : sqrt(v8);
      v13 = asin_0(v11 * 0.5);
      if ( (v13 + v13) * (v13 + v13) < v10 )
      {
        *((_DWORD *)this + 204) = a3;
        *((_QWORD *)this + 92) = a4;
        a4[61] = 0;
        v14 = *(__m128d *)a2;
        v15 = a2[2];
        v16 = CPoint3D::s_zero;
        v17 = *((_QWORD *)&CPoint3D::s_zero + 1);
        v18 = qword_10049A770;
        *((_QWORD *)this + 93) = *a2;
        *((_QWORD *)this + 95) = v15;
        *((_QWORD *)this + 94) = *(_OWORD *)&_mm_unpackhi_pd(v14, v14);
        *((_QWORD *)this + 96) = v16;
        *((_QWORD *)this + 97) = v17;
        *((_QWORD *)this + 98) = v18;
        *((_QWORD *)this + 99) = v16;
        *((_QWORD *)this + 100) = v17;
        *((_QWORD *)this + 101) = v18;
        *((_QWORD *)this + 6) = *((_QWORD *)this + 93);
        *((_QWORD *)this + 7) = *((_QWORD *)this + 94);
        *((_QWORD *)this + 8) = *((_QWORD *)this + 95);
        *((_QWORD *)this + 9) = *((_QWORD *)this + 96);
        *((_QWORD *)this + 10) = *((_QWORD *)this + 97);
        *((_QWORD *)this + 11) = *((_QWORD *)this + 98);
        *((_QWORD *)this + 12) = *((_QWORD *)this + 99);
        *((_QWORD *)this + 13) = *((_QWORD *)this + 100);
        *((_QWORD *)this + 14) = *((_QWORD *)this + 101);
        if ( (unsigned __int8)CGeodeticPointEdgeDistance::Evaluate(this, v12, &v26) )
        {
          while ( (unsigned __int8)CGeodeticPointEdgeDistance::Evaluate(this, v19, &v25) )
          {
            if ( *((double *)&v26 + 1) < 0.0 && *((double *)&v25 + 1) > 0.0 )
              CGeodeticPointEdgeDistance::FindMinimum(this);
            v20 = *((_QWORD *)this + 90);
            v26 = v25;
            if ( *(double *)(v20 + 88) >= *(double *)(v20 + 32) )
              break;
            v21 = *((_QWORD *)this + 92);
            v19 = *(unsigned int *)(v21 + 244);
            if ( (unsigned int)v19 >= *(_DWORD *)(v21 + 240) - 1 )
              break;
            *(_DWORD *)(v21 + 244) = v19 + 1;
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x100452fd0  mov     [rsp+arg_10], rbx
0x100452fd5  push    rbp
0x100452fd6  push    rsi
0x100452fd7  push    rdi
0x100452fd8  sub     rsp, 0F0h
0x100452fdf  mov     rax, cs:__security_cookie
0x100452fe6  xor     rax, rsp
0x100452fe9  mov     [rsp+108h+var_48], rax
0x100452ff1  mov     rax, [r9]
0x100452ff4  mov     ebp, r8d
0x100452ff7  mov     rbx, rcx
0x100452ffa  lea     r8, [rsp+108h+var_E8]
0x100452fff  mov     rcx, r9
0x100453002  mov     rsi, r9
0x100453005  mov     rdi, rdx
0x100453008  call    qword ptr [rax+28h]
0x10045300b  mov     rcx, [rbx+2D0h]
0x100453012  movaps  xmm2, xmm0
0x100453015  cmp     byte ptr [rcx+8], 0
0x100453019  jz      loc_1004530C5
0x10045301f  test    ebp, ebp
0x100453021  jnz     short loc_100453074
0x100453023  movsd   xmm1, qword ptr [rcx+20h]
0x100453028  comisd  xmm1, xmm0
0x10045302c  jbe     loc_1004532B1
0x100453032  movsd   xmm0, [rsp+108h+var_E8]
0x100453038  movsd   qword ptr [rcx+28h], xmm0
0x10045303d  movsd   xmm1, [rsp+108h+var_E0]
0x100453043  movsd   qword ptr [rcx+30h], xmm1
0x100453048  movsd   xmm0, [rsp+108h+var_D8]
0x10045304e  movsd   qword ptr [rcx+38h], xmm0
0x100453053  mov     rax, [rdi]
0x100453056  mov     [rcx+40h], rax
0x10045305a  mov     rax, [rdi+8]
0x10045305e  mov     [rcx+48h], rax
0x100453062  mov     rax, [rdi+10h]
0x100453066  mov     [rcx+50h], rax
0x10045306a  movsd   qword ptr [rcx+20h], xmm2
0x10045306f  jmp     loc_1004532B1
0x100453074  movsd   xmm0, qword ptr [rcx+20h]
0x100453079  comisd  xmm0, xmm2
0x10045307d  jbe     loc_1004532B1
0x100453083  mov     rax, [rdi]
0x100453086  mov     [rcx+28h], rax
0x10045308a  mov     rax, [rdi+8]
0x10045308e  mov     [rcx+30h], rax
0x100453092  mov     rax, [rdi+10h]
0x100453096  mov     [rcx+38h], rax
0x10045309a  movsd   xmm0, [rsp+108h+var_E8]
0x1004530a0  movsd   qword ptr [rcx+40h], xmm0
0x1004530a5  movsd   xmm1, [rsp+108h+var_E0]
0x1004530ab  movsd   qword ptr [rcx+48h], xmm1
0x1004530b0  movsd   xmm0, [rsp+108h+var_D8]
0x1004530b6  movsd   qword ptr [rcx+50h], xmm0
0x1004530bb  movsd   qword ptr [rcx+20h], xmm2
0x1004530c0  jmp     loc_1004532B1
0x1004530c5  movaps  [rsp+108h+var_28], xmm6
0x1004530cd  movsd   xmm6, qword ptr [rcx+18h]
0x1004530d2  comisd  xmm2, xmm6
0x1004530d6  jnb     loc_1004532A9
0x1004530dc  xorps   xmm0, xmm0
0x1004530df  ucomisd xmm0, xmm2
0x1004530e3  ja      short loc_1004530EE
0x1004530e5  xorps   xmm0, xmm0
0x1004530e8  sqrtsd  xmm0, xmm2
0x1004530ec  jmp     short loc_1004530F6
0x1004530ee  movaps  xmm0, xmm2; X
0x1004530f1  call    sqrt_0
0x1004530f6  mulsd   xmm0, cs:__real@3fe0000000000000; X
0x1004530fe  call    asin_0
0x100453103  addsd   xmm0, xmm0
0x100453107  mulsd   xmm0, xmm0
0x10045310b  comisd  xmm0, xmm6
0x10045310f  setnb   al
0x100453112  test    al, al
0x100453114  jnz     loc_1004532A9
0x10045311a  mov     [rbx+330h], ebp
0x100453120  lea     r8, [rsp+108h+var_B8]
0x100453125  mov     [rbx+2E0h], rsi
0x10045312c  mov     rcx, rbx
0x10045312f  mov     dword ptr [rsi+0F4h], 0
0x100453139  xorps   xmm6, xmm6
0x10045313c  movups  xmm0, xmmword ptr [rdi]
0x10045313f  movsd   xmm1, qword ptr [rdi+10h]
0x100453144  movsd   xmm4, qword ptr cs:?s_zero@CPoint3D@@2V1@A; CPoint3D CPoint3D::s_zero
0x10045314c  movsd   xmm3, qword ptr cs:?s_zero@CPoint3D@@2V1@A+8; CPoint3D CPoint3D::s_zero
0x100453154  movsd   xmm2, cs:qword_10049A770
0x10045315c  movsd   qword ptr [rbx+2E8h], xmm0
0x100453164  movsd   qword ptr [rbx+2F8h], xmm1
0x10045316c  xorps   xmm1, xmm1
0x10045316f  unpckhpd xmm0, xmm0
0x100453173  movsd   qword ptr [rbx+2F0h], xmm0
0x10045317b  movsd   qword ptr [rbx+300h], xmm4
0x100453183  movsd   qword ptr [rbx+308h], xmm3
0x10045318b  movsd   qword ptr [rbx+310h], xmm2
0x100453193  movsd   qword ptr [rbx+318h], xmm4
0x10045319b  movsd   qword ptr [rbx+320h], xmm3
0x1004531a3  movsd   qword ptr [rbx+328h], xmm2
0x1004531ab  mov     rax, [rbx+2E8h]
0x1004531b2  mov     [rbx+30h], rax
0x1004531b6  mov     rax, [rbx+2F0h]
0x1004531bd  mov     [rbx+38h], rax
0x1004531c1  mov     rax, [rbx+2F8h]
0x1004531c8  mov     [rbx+40h], rax
0x1004531cc  mov     rax, [rbx+300h]
0x1004531d3  mov     [rbx+48h], rax
0x1004531d7  mov     rax, [rbx+308h]
0x1004531de  mov     [rbx+50h], rax
0x1004531e2  mov     rax, [rbx+310h]
0x1004531e9  mov     [rbx+58h], rax
0x1004531ed  mov     rax, [rbx+318h]
0x1004531f4  mov     [rbx+60h], rax
0x1004531f8  mov     rax, [rbx+320h]
0x1004531ff  mov     [rbx+68h], rax
0x100453203  mov     rax, [rbx+328h]
0x10045320a  mov     [rbx+70h], rax
0x10045320e  call    ?Evaluate@CGeodeticPointEdgeDistance@@QEAA_NNAEAV?$CDifferentiable@N@@@Z; CGeodeticPointEdgeDistance::Evaluate(double,CDifferentiable<double> &)
0x100453213  test    al, al
0x100453215  jz      loc_1004532A9
0x10045321b  movaps  [rsp+108h+var_38], xmm7
0x100453223  movsd   xmm7, cs:__real@3ff0000000000000
0x10045322b  nop     dword ptr [rax+rax+00h]
0x100453230  lea     r8, [rsp+108h+var_D0]
0x100453235  movaps  xmm1, xmm7
0x100453238  mov     rcx, rbx
0x10045323b  call    ?Evaluate@CGeodeticPointEdgeDistance@@QEAA_NNAEAV?$CDifferentiable@N@@@Z; CGeodeticPointEdgeDistance::Evaluate(double,CDifferentiable<double> &)
0x100453240  test    al, al
0x100453242  jz      short loc_1004532A1
0x100453244  comisd  xmm6, qword ptr [rsp+108h+var_B8+8]
0x10045324a  jbe     short loc_100453260
0x10045324c  movsd   xmm0, qword ptr [rsp+108h+var_D0+8]
0x100453252  comisd  xmm0, xmm6
0x100453256  jbe     short loc_100453260
0x100453258  mov     rcx, rbx; this
0x10045325b  call    ?FindMinimum@CGeodeticPointEdgeDistance@@IEAAXXZ; CGeodeticPointEdgeDistance::FindMinimum(void)
0x100453260  movups  xmm0, [rsp+108h+var_D0]
0x100453265  mov     rax, [rbx+2D0h]
0x10045326c  movups  [rsp+108h+var_B8], xmm0
0x100453271  movsd   xmm0, qword ptr [rax+58h]
0x100453276  comisd  xmm0, qword ptr [rax+20h]
0x10045327b  jnb     short loc_1004532A1
0x10045327d  mov     rcx, [rbx+2E0h]
0x100453284  mov     eax, [rcx+0F0h]
0x10045328a  mov     edx, [rcx+0F4h]
0x100453290  dec     eax
0x100453292  cmp     edx, eax
0x100453294  jnb     short loc_1004532A1
0x100453296  lea     eax, [rdx+1]
0x100453299  mov     [rcx+0F4h], eax
0x10045329f  jmp     short loc_100453230
0x1004532a1  movaps  xmm7, [rsp+108h+var_38]
0x1004532a9  movaps  xmm6, [rsp+108h+var_28]
0x1004532b1  mov     rcx, [rsp+108h+var_48]
0x1004532b9  xor     rcx, rsp; StackCookie
0x1004532bc  call    __security_check_cookie
0x1004532c1  mov     rbx, [rsp+108h+arg_10]
0x1004532c9  add     rsp, 0F0h
0x1004532d0  pop     rdi
0x1004532d1  pop     rsi
0x1004532d2  pop     rbp
0x1004532d3  retn
```
