# CGeodeticPointPointDistance::Update(CPoint3D const &,CPoint3D const &)

- ea: `0x100457d00`
- end: `0x100457e7e`
- name: `?Update@CGeodeticPointPointDistance@@QEAAXAEBVCPoint3D@@0@Z`
- size: `382`
- prototype: `void __fastcall(CGeodeticPointPointDistance *__hidden this, const struct CPoint3D *, const struct CPoint3D *)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x100455310`
- `0x1004553d0`

## callees

- `0x100457d00`
- `0x10045d700`
- `0x100469a98`
- `0x100469af8`

## pseudocode

```c
void __fastcall CGeodeticPointPointDistance::Update(
        CGeodeticPointPointDistance *this,
        const struct CPoint3D *a2,
        const struct CPoint3D *a3)
{
  bool v6; // al
  __int64 v7; // rcx
  __m128d v8; // xmm2
  double v9; // xmm6_8
  double v10; // xmm0_8
  double v11; // xmm0_8
  double Distance; // xmm0_8
  __int64 v13; // rcx
  __int64 v14; // rax

  v6 = *((double *)this + 1) == *((double *)this + 2);
  v8 = (__m128d)*(unsigned __int64 *)a2;
  v7 = *((_QWORD *)this + 121);
  v8.m128d_f64[0] = (v8.m128d_f64[0] - *(double *)a3) * (v8.m128d_f64[0] - *(double *)a3)
                  + (*((double *)a2 + 1) - *((double *)a3 + 1)) * (*((double *)a2 + 1) - *((double *)a3 + 1))
                  + (*((double *)a2 + 2) - *((double *)a3 + 2)) * (*((double *)a2 + 2) - *((double *)a3 + 2));
  if ( v6 )
  {
    if ( *(double *)(v7 + 32) > v8.m128d_f64[0] )
    {
      *(_QWORD *)(v7 + 40) = *(_QWORD *)a2;
      *(_QWORD *)(v7 + 48) = *((_QWORD *)a2 + 1);
      *(_QWORD *)(v7 + 56) = *((_QWORD *)a2 + 2);
      *(_QWORD *)(v7 + 64) = *(_QWORD *)a3;
      *(_QWORD *)(v7 + 72) = *((_QWORD *)a3 + 1);
      *(_QWORD *)(v7 + 80) = *((_QWORD *)a3 + 2);
      *(double *)(v7 + 32) = v8.m128d_f64[0];
    }
  }
  else
  {
    v9 = *(double *)(v7 + 24);
    if ( v8.m128d_f64[0] < v9 )
    {
      if ( v8.m128d_f64[0] < 0.0 )
        v10 = sqrt_0(v8.m128d_f64[0]);
      else
        *(_QWORD *)&v10 = *(_OWORD *)&_mm_sqrt_pd(v8);
      v11 = asin_0(v10 * 0.5);
      if ( (v11 + v11) * (v11 + v11) < v9 )
      {
        Distance = CGeodeticLength::GetDistance(this, a2, a3);
        v13 = *((_QWORD *)this + 121);
        if ( *(double *)(v13 + 32) > Distance )
        {
          *(_QWORD *)(v13 + 40) = *(_QWORD *)a2;
          *(_QWORD *)(v13 + 48) = *((_QWORD *)a2 + 1);
          *(_QWORD *)(v13 + 56) = *((_QWORD *)a2 + 2);
          *(_QWORD *)(v13 + 64) = *(_QWORD *)a3;
          *(_QWORD *)(v13 + 72) = *((_QWORD *)a3 + 1);
          v14 = *((_QWORD *)a3 + 2);
          *(double *)(v13 + 32) = Distance;
          *(_QWORD *)(v13 + 80) = v14;
          *(double *)(v13 + 24) = Distance * Distance * *(double *)(v13 + 16);
        }
      }
    }
  }
}

```

## disassembly

```asm
0x100457d00  mov     [rsp+arg_0], rbx
0x100457d05  mov     [rsp+arg_8], rsi
0x100457d0a  push    rdi
0x100457d0b  sub     rsp, 30h
0x100457d0f  movsd   xmm0, qword ptr [rcx+8]
0x100457d14  mov     rbx, r8
0x100457d17  ucomisd xmm0, qword ptr [rcx+10h]
0x100457d1c  mov     rdi, rdx
0x100457d1f  mov     rsi, rcx
0x100457d22  jp      short loc_100457D2A
0x100457d24  jnz     short loc_100457D2A
0x100457d26  mov     al, 1
0x100457d28  jmp     short loc_100457D2C
0x100457d2a  xor     al, al
0x100457d2c  movsd   xmm3, qword ptr [rdx]
0x100457d30  movsd   xmm0, qword ptr [rdx+8]
0x100457d35  movaps  xmm2, xmm3
0x100457d38  movsd   xmm1, qword ptr [rdx+10h]
0x100457d3d  mov     rcx, [rcx+3C8h]
0x100457d44  subsd   xmm2, qword ptr [r8]
0x100457d49  subsd   xmm0, qword ptr [r8+8]
0x100457d4f  subsd   xmm1, qword ptr [r8+10h]
0x100457d55  mulsd   xmm2, xmm2
0x100457d59  mulsd   xmm0, xmm0
0x100457d5d  mulsd   xmm1, xmm1
0x100457d61  addsd   xmm2, xmm0
0x100457d65  addsd   xmm2, xmm1
0x100457d69  test    al, al
0x100457d6b  jz      short loc_100457DBD
0x100457d6d  movsd   xmm0, qword ptr [rcx+20h]
0x100457d72  comisd  xmm0, xmm2
0x100457d76  jbe     loc_100457E6E
0x100457d7c  movsd   qword ptr [rcx+28h], xmm3
0x100457d81  mov     rax, [rdx+8]
0x100457d85  mov     [rcx+30h], rax
0x100457d89  mov     rax, [rdx+10h]
0x100457d8d  mov     [rcx+38h], rax
0x100457d91  mov     rax, [r8]
0x100457d94  mov     [rcx+40h], rax
0x100457d98  mov     rax, [r8+8]
0x100457d9c  mov     [rcx+48h], rax
0x100457da0  mov     rax, [r8+10h]
0x100457da4  mov     [rcx+50h], rax
0x100457da8  movsd   qword ptr [rcx+20h], xmm2
0x100457dad  mov     rbx, [rsp+38h+arg_0]
0x100457db2  mov     rsi, [rsp+38h+arg_8]
0x100457db7  add     rsp, 30h
0x100457dbb  pop     rdi
0x100457dbc  retn
0x100457dbd  movaps  [rsp+38h+var_18], xmm6
0x100457dc2  movsd   xmm6, qword ptr [rcx+18h]
0x100457dc7  comisd  xmm2, xmm6
0x100457dcb  jnb     loc_100457E69
0x100457dd1  xorps   xmm0, xmm0
0x100457dd4  ucomisd xmm0, xmm2
0x100457dd8  ja      short loc_100457DE0
0x100457dda  sqrtpd  xmm0, xmm2
0x100457dde  jmp     short loc_100457DE8
0x100457de0  movaps  xmm0, xmm2; X
0x100457de3  call    sqrt_0
0x100457de8  mulsd   xmm0, cs:__real@3fe0000000000000; X
0x100457df0  call    asin_0
0x100457df5  addsd   xmm0, xmm0
0x100457df9  mulsd   xmm0, xmm0
0x100457dfd  comisd  xmm0, xmm6
0x100457e01  setnb   al
0x100457e04  test    al, al
0x100457e06  jnz     short loc_100457E69
0x100457e08  mov     r8, rbx; struct CPoint3D *
0x100457e0b  mov     rdx, rdi; struct CPoint3D *
0x100457e0e  mov     rcx, rsi; this
0x100457e11  call    ?GetDistance@CGeodeticLength@@QEAANAEBVCPoint3D@@0@Z; CGeodeticLength::GetDistance(CPoint3D const &,CPoint3D const &)
0x100457e16  mov     rcx, [rsi+3C8h]
0x100457e1d  movsd   xmm1, qword ptr [rcx+20h]
0x100457e22  comisd  xmm1, xmm0
0x100457e26  jbe     short loc_100457E69
0x100457e28  mov     rax, [rdi]
0x100457e2b  mov     [rcx+28h], rax
0x100457e2f  mov     rax, [rdi+8]
0x100457e33  mov     [rcx+30h], rax
0x100457e37  mov     rax, [rdi+10h]
0x100457e3b  mov     [rcx+38h], rax
0x100457e3f  mov     rax, [rbx]
0x100457e42  mov     [rcx+40h], rax
0x100457e46  mov     rax, [rbx+8]
0x100457e4a  mov     [rcx+48h], rax
0x100457e4e  mov     rax, [rbx+10h]
0x100457e52  movsd   qword ptr [rcx+20h], xmm0
0x100457e57  mulsd   xmm0, xmm0
0x100457e5b  mov     [rcx+50h], rax
0x100457e5f  mulsd   xmm0, qword ptr [rcx+10h]
0x100457e64  movsd   qword ptr [rcx+18h], xmm0
0x100457e69  movaps  xmm6, [rsp+38h+var_18]
0x100457e6e  mov     rbx, [rsp+38h+arg_0]
0x100457e73  mov     rsi, [rsp+38h+arg_8]
0x100457e78  add     rsp, 30h
0x100457e7c  pop     rdi
0x100457e7d  retn
```
