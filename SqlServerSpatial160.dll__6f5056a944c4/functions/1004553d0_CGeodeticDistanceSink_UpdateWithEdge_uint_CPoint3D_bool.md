# CGeodeticDistanceSink::UpdateWithEdge(uint,CPoint3D *,bool)

- ea: `0x1004553d0`
- end: `0x1004556cb`
- name: `?UpdateWithEdge@CGeodeticDistanceSink@@IEAAXIPEAVCPoint3D@@_N@Z`
- size: `763`
- prototype: `void __fastcall(CGeodeticDistanceSink *__hidden this, unsigned int, struct CPoint3D *, bool)`
- caller_count: `2`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x1004558a0`
- `0x100456240`

## callees

- `0x10044dfc0`
- `0x100452fd0`
- `0x100454040`
- `0x1004553d0`
- `0x1004556e0`
- `0x100456540`
- `0x100457d00`
- `0x100458050`
- `0x100467f10`

## pseudocode

```c
void __fastcall CGeodeticDistanceSink::UpdateWithEdge(
        CGeodeticDistanceSink *this,
        int a2,
        struct CPoint3D *a3,
        bool a4)
{
  const struct CPoint3D *v9; // r8
  char *v10; // rbp
  char v11; // al
  const struct CPoint3D *v12; // r8
  char *v13; // r14
  char v14; // al
  __int64 v15; // rax
  __int64 v16; // rcx
  double v17; // xmm0_8
  __int64 v18; // rax
  double v19; // xmm3_8
  __int128 v20; // xmm0
  __int64 v21; // xmm1_8
  __int64 v22; // rcx
  unsigned int v23; // edx
  __int64 v24; // rcx
  unsigned int v25; // edx
  __int128 v26; // [rsp+30h] [rbp-58h] BYREF
  __int64 v27; // [rsp+40h] [rbp-48h]
  __int128 v28; // [rsp+48h] [rbp-40h] BYREF
  __int64 v29; // [rsp+58h] [rbp-30h]

  if ( *((_DWORD *)this + 1308) )
  {
    if ( a2 == 1 )
    {
      CGeodeticPointEdgeDistance::Update((CGeodeticDistanceSink *)((char *)this + 984), a3, 1, *((_DWORD **)this + 642));
    }
    else
    {
      v12 = (struct CPoint3D *)((char *)a3 + 24);
      if ( a2 == 2 )
      {
        v13 = (char *)this + 3256;
        v14 = CLinearEdge<CPoint3D,double>::Set((char *)this + 3256, a3, v12);
      }
      else
      {
        v13 = (char *)this + 3784;
        CGeodeticCircularArc::Construct(
          (CGeodeticDistanceSink *)((char *)this + 4056),
          a3,
          v12,
          *((double *)this + 475) / *((double *)this + 474));
        v14 = CCircularEdge::Set((CCircularEdge *)v13, (const struct CGeodeticCircularArc *)(v13 + 272));
      }
      if ( v14 )
      {
        *((_QWORD *)this + 641) = v13;
        CGeodeticDistanceSink::UpdateWithBoundary(
          this,
          1u,
          0,
          a3,
          (struct CPoint3D *)((char *)a3 + 24 * (unsigned int)(a2 - 1)),
          a4);
        v15 = *((_QWORD *)this + 655);
        if ( *(double *)(v15 + 88) < *(double *)(v15 + 32) )
        {
          v16 = 5168;
          if ( *((_QWORD *)this + 653) )
            v16 = 5192;
          CGeodeticDistanceSink::UpdateWithBoundary(
            this,
            0,
            1u,
            (CGeodeticDistanceSink *)((char *)this + 5144),
            (CGeodeticDistanceSink *)((char *)this + v16),
            *((_BYTE *)this + 5236) == 0);
          v15 = *((_QWORD *)this + 655);
        }
        if ( *(double *)(v15 + 88) < *(double *)(v15 + 32) )
        {
          if ( *(_BYTE *)(*((_QWORD *)this + 397) + 8LL) )
          {
            v17 = CEdge<CPoint3D,double>::SquaredSphereDistanceToEdge(
                    *((_QWORD *)this + 641),
                    *((_QWORD *)this + 642),
                    &v26,
                    &v28);
            v18 = *((_QWORD *)this + 397);
            v19 = v17;
            if ( *(double *)(v18 + 32) > v17 )
            {
              v20 = v28;
              *(_OWORD *)(v18 + 40) = v26;
              v21 = v27;
              *(_OWORD *)(v18 + 64) = v20;
              *(_QWORD *)&v20 = v29;
              *(_QWORD *)(v18 + 56) = v21;
              *(_QWORD *)(v18 + 80) = v20;
              *(double *)(v18 + 32) = v19;
            }
          }
          else
          {
            *((_QWORD *)this + 399) = *((_QWORD *)this + 641);
            *((_QWORD *)this + 400) = *((_QWORD *)this + 642);
            *(_DWORD *)(*((_QWORD *)this + 399) + 244LL) = 0;
LABEL_25:
            *(_DWORD *)(*((_QWORD *)this + 400) + 244LL) = 0;
            while ( 1 )
            {
              CGeodeticEdgeEdgeDistance::FindMinimum((CGeodeticDistanceSink *)((char *)this + 1808));
              if ( *(double *)(*((_QWORD *)this + 397) + 88LL) >= *(double *)(*((_QWORD *)this + 397) + 32LL) )
                break;
              v22 = *((_QWORD *)this + 400);
              v23 = *(_DWORD *)(v22 + 244);
              if ( v23 >= *(_DWORD *)(v22 + 240) - 1 )
              {
                v24 = *((_QWORD *)this + 399);
                v25 = *(_DWORD *)(v24 + 244);
                if ( v25 >= *(_DWORD *)(v24 + 240) - 1 )
                  return;
                *(_DWORD *)(v24 + 244) = v25 + 1;
                goto LABEL_25;
              }
              *(_DWORD *)(v22 + 244) = v23 + 1;
            }
          }
        }
      }
    }
  }
  else if ( a2 == 1 )
  {
    CGeodeticPointPointDistance::Update(
      (CGeodeticDistanceSink *)((char *)this + 8),
      a3,
      (CGeodeticDistanceSink *)((char *)this + 5144));
  }
  else
  {
    v9 = (struct CPoint3D *)((char *)a3 + 24);
    if ( a2 == 2 )
    {
      v10 = (char *)this + 3256;
      v11 = CLinearEdge<CPoint3D,double>::Set((char *)this + 3256, a3, v9);
    }
    else
    {
      v10 = (char *)this + 3784;
      CGeodeticCircularArc::Construct(
        (CGeodeticDistanceSink *)((char *)this + 4056),
        a3,
        v9,
        *((double *)this + 475) / *((double *)this + 474));
      v11 = CCircularEdge::Set((CCircularEdge *)v10, (const struct CGeodeticCircularArc *)(v10 + 272));
    }
    if ( v11 )
    {
      *((_QWORD *)this + 641) = v10;
      CGeodeticPointEdgeDistance::Update((CGeodeticDistanceSink *)((char *)this + 984), (_QWORD *)this + 643, 1, v10);
    }
  }
}

```

## disassembly

```asm
0x1004553d0  push    rbx
0x1004553d2  push    rbp
0x1004553d3  push    rsi
0x1004553d4  push    rdi
0x1004553d5  push    r15
0x1004553d7  sub     rsp, 60h
0x1004553db  cmp     dword ptr [rcx+1470h], 0
0x1004553e2  mov     ebp, edx
0x1004553e4  mov     rdx, r8; struct CPoint3D *
0x1004553e7  movzx   r15d, r9b
0x1004553eb  mov     rsi, r8
0x1004553ee  mov     rdi, rcx
0x1004553f1  jnz     loc_100455491
0x1004553f7  cmp     ebp, 1
0x1004553fa  jnz     short loc_100455416
0x1004553fc  lea     r8, [rcx+1418h]; struct CPoint3D *
0x100455403  add     rcx, 8; this
0x100455407  add     rsp, 60h
0x10045540b  pop     r15
0x10045540d  pop     rdi
0x10045540e  pop     rsi
0x10045540f  pop     rbp
0x100455410  pop     rbx
0x100455411  jmp     ?Update@CGeodeticPointPointDistance@@QEAAXAEBVCPoint3D@@0@Z; CGeodeticPointPointDistance::Update(CPoint3D const &,CPoint3D const &)
0x100455416  add     r8, 18h; struct CPoint3D *
0x10045541a  cmp     ebp, 2
0x10045541d  jnz     short loc_100455430
0x10045541f  lea     rbp, [rcx+0CB8h]
0x100455426  mov     rcx, rbp
0x100455429  call    ?Set@?$CLinearEdge@VCPoint3D@@N@@QEAA_NAEBVCPoint3D@@0@Z; CLinearEdge<CPoint3D,double>::Set(CPoint3D const &,CPoint3D const &)
0x10045542e  jmp     short loc_10045545C
0x100455430  lea     rbp, [rcx+0EC8h]
0x100455437  movsd   xmm3, qword ptr [rbp+10h]
0x10045543c  lea     rcx, [rbp+110h]; this
0x100455443  divsd   xmm3, qword ptr [rbp+8]; double
0x100455448  call    ?Construct@CGeodeticCircularArc@@QEAAXAEBVCPoint3D@@PEBV2@N@Z; CGeodeticCircularArc::Construct(CPoint3D const &,CPoint3D const *,double)
0x10045544d  lea     rdx, [rbp+110h]; struct CGeodeticCircularArc *
0x100455454  mov     rcx, rbp; this
0x100455457  call    ?Set@CCircularEdge@@QEAA_NAEBVCGeodeticCircularArc@@@Z; CCircularEdge::Set(CGeodeticCircularArc const &)
0x10045545c  test    al, al
0x10045545e  jz      loc_100455616
0x100455464  lea     rdx, [rdi+1418h]
0x10045546b  mov     [rdi+1408h], rbp
0x100455472  lea     rcx, [rdi+3D8h]; this
0x100455479  mov     r9, rbp
0x10045547c  mov     r8d, 1
0x100455482  add     rsp, 60h
0x100455486  pop     r15
0x100455488  pop     rdi
0x100455489  pop     rsi
0x10045548a  pop     rbp
0x10045548b  pop     rbx
0x10045548c  jmp     ?Update@CGeodeticPointEdgeDistance@@QEAAXAEBVCPoint3D@@IPEAV?$CEdge@VCPoint3D@@N@@@Z; CGeodeticPointEdgeDistance::Update(CPoint3D const &,uint,CEdge<CPoint3D,double> *)
0x100455491  cmp     ebp, 1
0x100455494  jnz     short loc_1004554B6
0x100455496  mov     r9, [rdi+1410h]
0x10045549d  add     rcx, 3D8h; this
0x1004554a4  mov     r8d, ebp
0x1004554a7  add     rsp, 60h
0x1004554ab  pop     r15
0x1004554ad  pop     rdi
0x1004554ae  pop     rsi
0x1004554af  pop     rbp
0x1004554b0  pop     rbx
0x1004554b1  jmp     ?Update@CGeodeticPointEdgeDistance@@QEAAXAEBVCPoint3D@@IPEAV?$CEdge@VCPoint3D@@N@@@Z; CGeodeticPointEdgeDistance::Update(CPoint3D const &,uint,CEdge<CPoint3D,double> *)
0x1004554b6  add     r8, 18h; struct CPoint3D *
0x1004554ba  mov     [rsp+88h+arg_18], r14
0x1004554c2  cmp     ebp, 2
0x1004554c5  jnz     short loc_1004554D8
0x1004554c7  lea     r14, [rcx+0CB8h]
0x1004554ce  mov     rcx, r14
0x1004554d1  call    ?Set@?$CLinearEdge@VCPoint3D@@N@@QEAA_NAEBVCPoint3D@@0@Z; CLinearEdge<CPoint3D,double>::Set(CPoint3D const &,CPoint3D const &)
0x1004554d6  jmp     short loc_100455506
0x1004554d8  lea     r14, [rcx+0EC8h]
0x1004554df  movsd   xmm3, qword ptr [r14+10h]
0x1004554e5  lea     rcx, [r14+110h]; this
0x1004554ec  divsd   xmm3, qword ptr [r14+8]; double
0x1004554f2  call    ?Construct@CGeodeticCircularArc@@QEAAXAEBVCPoint3D@@PEBV2@N@Z; CGeodeticCircularArc::Construct(CPoint3D const &,CPoint3D const *,double)
0x1004554f7  lea     rdx, [r14+110h]; struct CGeodeticCircularArc *
0x1004554fe  mov     rcx, r14; this
0x100455501  call    ?Set@CCircularEdge@@QEAA_NAEBVCGeodeticCircularArc@@@Z; CCircularEdge::Set(CGeodeticCircularArc const &)
0x100455506  test    al, al
0x100455508  jz      loc_10045560E
0x10045550e  xor     r8d, r8d; unsigned int
0x100455511  mov     [rsp+88h+var_60], r15b; bool
0x100455516  lea     eax, [rbp-1]
0x100455519  mov     [rdi+1408h], r14
0x100455520  lea     rax, [rax+rax*2]
0x100455524  mov     r9, rsi; struct CPoint3D *
0x100455527  lea     rcx, [rsi+rax*8]
0x10045552b  mov     [rsp+88h+var_68], rcx; struct CPoint3D *
0x100455530  lea     edx, [r8+1]; unsigned int
0x100455534  mov     rcx, rdi; this
0x100455537  call    ?UpdateWithBoundary@CGeodeticDistanceSink@@IEAAXIIAEAVCPoint3D@@0_N@Z; CGeodeticDistanceSink::UpdateWithBoundary(uint,uint,CPoint3D &,CPoint3D &,bool)
0x10045553c  mov     rax, [rdi+1478h]
0x100455543  movsd   xmm0, qword ptr [rax+58h]
0x100455548  comisd  xmm0, qword ptr [rax+20h]
0x10045554d  jnb     short loc_100455596
0x10045554f  cmp     byte ptr [rdi+1474h], 0
0x100455556  lea     r9, [rdi+1418h]; struct CPoint3D *
0x10045555d  mov     edx, 1448h
0x100455562  mov     ecx, 1430h
0x100455567  setz    al
0x10045556a  cmp     qword ptr [rdi+1468h], 0
0x100455572  mov     [rsp+88h+var_60], al; bool
0x100455576  cmovnz  ecx, edx
0x100455579  xor     edx, edx; unsigned int
0x10045557b  add     rcx, rdi
0x10045557e  mov     [rsp+88h+var_68], rcx; struct CPoint3D *
0x100455583  mov     rcx, rdi; this
0x100455586  lea     r8d, [rdx+1]; unsigned int
0x10045558a  call    ?UpdateWithBoundary@CGeodeticDistanceSink@@IEAAXIIAEAVCPoint3D@@0_N@Z; CGeodeticDistanceSink::UpdateWithBoundary(uint,uint,CPoint3D &,CPoint3D &,bool)
0x10045558f  mov     rax, [rdi+1478h]
0x100455596  movsd   xmm0, qword ptr [rax+58h]
0x10045559b  comisd  xmm0, qword ptr [rax+20h]
0x1004555a0  jnb     short loc_10045560E
0x1004555a2  mov     rax, [rdi+0C68h]
0x1004555a9  cmp     byte ptr [rax+8], 0
0x1004555ad  jz      short loc_100455621
0x1004555af  mov     rdx, [rdi+1410h]
0x1004555b6  lea     r9, [rsp+88h+var_40]
0x1004555bb  mov     rcx, [rdi+1408h]
0x1004555c2  lea     r8, [rsp+88h+var_58]
0x1004555c7  call    ?SquaredSphereDistanceToEdge@?$CEdge@VCPoint3D@@N@@QEBANAEBV1@AEAVCPoint3D@@1@Z; CEdge<CPoint3D,double>::SquaredSphereDistanceToEdge(CEdge<CPoint3D,double> const &,CPoint3D &,CPoint3D &)
0x1004555cc  mov     rax, [rdi+0C68h]
0x1004555d3  movaps  xmm3, xmm0
0x1004555d6  movsd   xmm1, qword ptr [rax+20h]
0x1004555db  comisd  xmm1, xmm0
0x1004555df  jbe     short loc_10045560E
0x1004555e1  movups  xmm1, [rsp+88h+var_58]
0x1004555e6  movups  xmm0, [rsp+88h+var_40]
0x1004555eb  movups  xmmword ptr [rax+28h], xmm1
0x1004555ef  movsd   xmm1, [rsp+88h+var_48]
0x1004555f5  movups  xmmword ptr [rax+40h], xmm0
0x1004555f9  movsd   xmm0, [rsp+88h+var_30]
0x1004555ff  movsd   qword ptr [rax+38h], xmm1
0x100455604  movsd   qword ptr [rax+50h], xmm0
0x100455609  movsd   qword ptr [rax+20h], xmm3
0x10045560e  mov     r14, [rsp+88h+arg_18]
0x100455616  add     rsp, 60h
0x10045561a  pop     r15
0x10045561c  pop     rdi
0x10045561d  pop     rsi
0x10045561e  pop     rbp
0x10045561f  pop     rbx
0x100455620  retn
0x100455621  mov     rax, [rdi+1408h]
0x100455628  xor     esi, esi
0x10045562a  mov     [rdi+0C78h], rax
0x100455631  mov     rax, [rdi+1410h]
0x100455638  mov     [rdi+0C80h], rax
0x10045563f  mov     rax, [rdi+0C78h]
0x100455646  mov     [rax+0F4h], esi
0x10045564c  nop     dword ptr [rax+00h]
0x100455650  mov     rax, [rdi+0C80h]
0x100455657  mov     [rax+0F4h], esi
0x10045565d  nop     dword ptr [rax]
0x100455660  lea     rcx, [rdi+710h]; this
0x100455667  call    ?FindMinimum@CGeodeticEdgeEdgeDistance@@IEAAXXZ; CGeodeticEdgeEdgeDistance::FindMinimum(void)
0x10045566c  mov     rax, [rdi+0C68h]
0x100455673  movsd   xmm0, qword ptr [rax+58h]
0x100455678  comisd  xmm0, qword ptr [rax+20h]
0x10045567d  jnb     short loc_10045560E
0x10045567f  mov     rcx, [rdi+0C80h]
0x100455686  mov     eax, [rcx+0F0h]
0x10045568c  mov     edx, [rcx+0F4h]
0x100455692  dec     eax
0x100455694  cmp     edx, eax
0x100455696  jnb     short loc_1004556A3
0x100455698  lea     eax, [rdx+1]
0x10045569b  mov     [rcx+0F4h], eax
0x1004556a1  jmp     short loc_100455660
0x1004556a3  mov     rcx, [rdi+0C78h]
0x1004556aa  mov     eax, [rcx+0F0h]
0x1004556b0  mov     edx, [rcx+0F4h]
0x1004556b6  dec     eax
0x1004556b8  cmp     edx, eax
0x1004556ba  jnb     loc_10045560E
0x1004556c0  lea     eax, [rdx+1]
0x1004556c3  mov     [rcx+0F4h], eax
0x1004556c9  jmp     short loc_100455650
```
