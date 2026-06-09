# CPlanarRTree::ComputeLeafEnvelope(CRTree::Node &)

- ea: `0x10042fe80`
- end: `0x100430181`
- name: `?ComputeLeafEnvelope@CPlanarRTree@@MEBAJAEAUNode@CRTree@@@Z`
- size: `769`
- prototype: `__int64 __fastcall(CPlanarRTree *__hidden this, struct Node *)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x100420ae0`
- `0x10042fe80`
- `0x10044cf80`

## import_xrefs

- `api-ms-win-crt-math-l1-1-0!_isnan` at `0x10042ffa1`
- `api-ms-win-crt-math-l1-1-0!_isnan` at `0x10042ffaf`
- `api-ms-win-crt-math-l1-1-0!_isnan` at `0x100430017`
- `api-ms-win-crt-math-l1-1-0!_isnan` at `0x100430025`
- `api-ms-win-crt-math-l1-1-0!_isnan` at `0x10042ffa1`
- `api-ms-win-crt-math-l1-1-0!_isnan` at `0x10042ffaf`
- `api-ms-win-crt-math-l1-1-0!_isnan` at `0x100430017`
- `api-ms-win-crt-math-l1-1-0!_isnan` at `0x100430025`

## pseudocode

```c
__int64 __fastcall CPlanarRTree::ComputeLeafEnvelope(CPlanarRTree *this, struct Node *a2)
{
  struct Node *v2; // r14
  char v3; // bl
  int lpVtbl_high; // r12d
  unsigned int lpVtbl; // r15d
  double v7; // xmm8_8
  double v8; // xmm10_8
  double v9; // xmm6_8
  double v10; // xmm7_8
  __int64 v11; // rcx
  __int64 v12; // rax
  int v13; // esi
  double *v14; // rdi
  double v15; // xmm0_8
  double v16; // xmm9_8
  double v17; // xmm0_8
  double v18; // xmm9_8
  __m128d v19; // xmm0
  __m128d v20; // xmm0
  __int128 v22; // [rsp+20h] [rbp-E0h] BYREF
  __int128 v23; // [rsp+30h] [rbp-D0h]
  char v24; // [rsp+40h] [rbp-C0h]
  _QWORD v25[22]; // [rsp+50h] [rbp-B0h] BYREF

  v2 = a2;
  v3 = 0;
  lpVtbl_high = HIDWORD(a2->lpVtbl);
  lpVtbl = (unsigned int)a2->lpVtbl;
  v22 = _xmm_ffefffffffffffff7fefffffffffffff;
  v7 = *((double *)&_xmm_ffefffffffffffff7fefffffffffffff + 1);
  v8 = *(double *)&_xmm_ffefffffffffffff7fefffffffffffff;
  v23 = _xmm_ffefffffffffffff7fefffffffffffff;
  v9 = *((double *)&_xmm_ffefffffffffffff7fefffffffffffff + 1);
  v10 = *(double *)&_xmm_ffefffffffffffff7fefffffffffffff;
  if ( !lpVtbl_high )
    goto LABEL_38;
  do
  {
    v11 = *(unsigned int *)(*(_QWORD *)(*((_QWORD *)this + 9) + 8LL * (lpVtbl / *((_DWORD *)this + 21)))
                          + 4LL * (lpVtbl % *((_DWORD *)this + 21)));
    v12 = *((_QWORD *)this + 22);
    v13 = *(_DWORD *)(v12 + 8 * v11 + 4);
    v14 = (double *)(*((_QWORD *)this + 25) + 16LL * *(unsigned int *)(v12 + 8 * v11));
    v15 = *v14;
    if ( v8 > *v14 )
    {
      *(double *)&v22 = *v14;
      v8 = v15;
    }
    if ( v15 > v7 )
    {
      *((double *)&v22 + 1) = v15;
      v7 = v15;
    }
    v16 = v14[1];
    if ( v10 > v16 )
    {
      v10 = v14[1];
      *(double *)&v23 = v10;
    }
    if ( v16 > v9 )
    {
      v9 = v16;
      *((double *)&v23 + 1) = v16;
    }
    if ( v3 || _isnan(v15) || _isnan(v16) )
      v3 = 1;
    v24 = v3;
    if ( v13 == 2 )
    {
      v17 = v14[2];
      if ( v8 > v17 )
      {
        *(double *)&v22 = v14[2];
        v8 = v17;
      }
      if ( v17 > v7 )
      {
        *((double *)&v22 + 1) = v17;
        v7 = v17;
      }
      v18 = v14[3];
    }
    else
    {
      if ( v13 != 3 )
        goto LABEL_36;
      v25[0] = &CGeodeticCircularArc::`vftable';
      CCircularArc<CMglPoint<double>>::ConstructFrom3Points(v25, v14, v14 + 2);
      v25[0] = &CGeodeticCircularArc::`vftable';
      if ( *(double *)&v25[16] != 0.0 )
      {
        CCircularArc2D::UpdateBounds((CCircularArc2D *)v25, (struct CBounds *)&v22);
        v3 = v24;
        v9 = *((double *)&v23 + 1);
        v10 = *(double *)&v23;
        v7 = *((double *)&v22 + 1);
        v8 = *(double *)&v22;
        goto LABEL_36;
      }
      v17 = v14[4];
      if ( v8 > v17 )
      {
        *(double *)&v22 = v14[4];
        v8 = v17;
      }
      if ( v17 > v7 )
      {
        *((double *)&v22 + 1) = v17;
        v7 = v17;
      }
      v18 = v14[5];
    }
    if ( v10 > v18 )
    {
      v10 = v18;
      *(double *)&v23 = v18;
    }
    if ( v18 > v9 )
    {
      v9 = v18;
      *((double *)&v23 + 1) = v18;
    }
    if ( v3 || _isnan(v17) || _isnan(v18) )
      v3 = 1;
LABEL_36:
    ++lpVtbl;
    --lpVtbl_high;
  }
  while ( lpVtbl_high );
  v2 = a2;
LABEL_38:
  if ( v3 )
  {
    v19 = _mm_cvtps_pd((__m128)LODWORD(FLOAT_QNAN));
    v20 = _mm_unpacklo_pd(v19, v19);
    *(__m128d *)&v2[1].lpVtbl = v20;
    *(__m128d *)&v2[3].lpVtbl = v20;
  }
  else
  {
    *(double *)&v2[1].lpVtbl = v8;
    *(double *)&v2[2].lpVtbl = v10;
    *(double *)&v2[3].lpVtbl = v7;
    *(double *)&v2[4].lpVtbl = v9;
  }
  return 0;
}

```

## disassembly

```asm
0x10042fe80  mov     rax, rsp
0x10042fe83  mov     [rax+10h], rdx
0x10042fe87  push    rbp
0x10042fe88  push    r14
0x10042fe8a  lea     rbp, [rsp-78h]
0x10042fe8f  sub     rsp, 178h
0x10042fe96  movaps  xmm0, cs:__xmm@ffefffffffffffff7fefffffffffffff
0x10042fe9d  mov     r14, rdx
0x10042fea0  movaps  xmmword ptr [rax-38h], xmm6
0x10042fea4  movaps  xmm1, xmm0
0x10042fea7  movaps  xmmword ptr [rax-48h], xmm7
0x10042feab  movaps  xmmword ptr [rax-58h], xmm8
0x10042feb0  movaps  xmmword ptr [rax-78h], xmm10
0x10042feb5  mov     [rax+8], rbx
0x10042feb9  xor     bl, bl
0x10042febb  mov     [rax-18h], r12
0x10042febf  mov     r12d, [rdx+4]
0x10042fec3  mov     [rax-20h], r13
0x10042fec7  mov     r13, rcx
0x10042feca  mov     [rax-28h], r15
0x10042fece  mov     r15d, [rdx]
0x10042fed1  movups  [rsp+180h+var_160], xmm0
0x10042fed6  movsd   xmm8, qword ptr [rsp+180h+var_160+8]
0x10042fedd  movsd   xmm10, qword ptr [rsp+180h+var_160]
0x10042fee4  movups  [rsp+180h+var_150], xmm0
0x10042fee9  movsd   xmm6, qword ptr [rsp+180h+var_150+8]
0x10042feef  movsd   xmm7, qword ptr [rsp+180h+var_150]
0x10042fef5  test    r12d, r12d
0x10042fef8  jz      loc_100430105
0x10042fefe  mov     [rax+18h], rsi
0x10042ff02  lea     r14, ??_7CGeodeticCircularArc@@6B@; const CGeodeticCircularArc::`vftable'
0x10042ff09  mov     [rax+20h], rdi
0x10042ff0d  movaps  xmmword ptr [rax-68h], xmm9
0x10042ff12  movaps  xmmword ptr [rax-88h], xmm11
0x10042ff1a  xorps   xmm11, xmm11
0x10042ff1e  xchg    ax, ax
0x10042ff20  xor     edx, edx
0x10042ff22  mov     eax, r15d
0x10042ff25  div     dword ptr [r13+54h]
0x10042ff29  mov     ecx, eax
0x10042ff2b  mov     rax, [r13+48h]
0x10042ff2f  mov     rax, [rax+rcx*8]
0x10042ff33  mov     ecx, [rax+rdx*4]
0x10042ff36  mov     rax, [r13+0B0h]
0x10042ff3d  mov     edi, [rax+rcx*8]
0x10042ff40  mov     esi, [rax+rcx*8+4]
0x10042ff44  shl     rdi, 4
0x10042ff48  add     rdi, [r13+0C8h]
0x10042ff4f  movsd   xmm0, qword ptr [rdi]; X
0x10042ff53  comisd  xmm10, xmm0
0x10042ff58  jbe     short loc_10042FF64
0x10042ff5a  movsd   qword ptr [rsp+180h+var_160], xmm0
0x10042ff60  movaps  xmm10, xmm0
0x10042ff64  comisd  xmm0, xmm8
0x10042ff69  jbe     short loc_10042FF75
0x10042ff6b  movsd   qword ptr [rsp+180h+var_160+8], xmm0
0x10042ff71  movaps  xmm8, xmm0
0x10042ff75  movsd   xmm9, qword ptr [rdi+8]
0x10042ff7b  comisd  xmm7, xmm9
0x10042ff80  jbe     short loc_10042FF8C
0x10042ff82  movaps  xmm7, xmm9
0x10042ff86  movsd   qword ptr [rsp+180h+var_150], xmm7
0x10042ff8c  comisd  xmm9, xmm6
0x10042ff91  jbe     short loc_10042FF9D
0x10042ff93  movaps  xmm6, xmm9
0x10042ff97  movsd   qword ptr [rsp+180h+var_150+8], xmm6
0x10042ff9d  test    bl, bl
0x10042ff9f  jnz     short loc_10042FFB9
0x10042ffa1  call    cs:__imp__isnan
0x10042ffa7  test    eax, eax
0x10042ffa9  jnz     short loc_10042FFB9
0x10042ffab  movaps  xmm0, xmm9; X
0x10042ffaf  call    cs:__imp__isnan
0x10042ffb5  test    eax, eax
0x10042ffb7  jz      short loc_10042FFBB
0x10042ffb9  mov     bl, 1
0x10042ffbb  mov     [rsp+180h+var_140], bl
0x10042ffbf  cmp     esi, 2
0x10042ffc2  jnz     short loc_10043003A
0x10042ffc4  movsd   xmm0, qword ptr [rdi+10h]; X
0x10042ffc9  comisd  xmm10, xmm0
0x10042ffce  jbe     short loc_10042FFDA
0x10042ffd0  movsd   qword ptr [rsp+180h+var_160], xmm0
0x10042ffd6  movaps  xmm10, xmm0
0x10042ffda  comisd  xmm0, xmm8
0x10042ffdf  jbe     short loc_10042FFEB
0x10042ffe1  movsd   qword ptr [rsp+180h+var_160+8], xmm0
0x10042ffe7  movaps  xmm8, xmm0
0x10042ffeb  movsd   xmm9, qword ptr [rdi+18h]
0x10042fff1  comisd  xmm7, xmm9
0x10042fff6  jbe     short loc_100430002
0x10042fff8  movaps  xmm7, xmm9
0x10042fffc  movsd   qword ptr [rsp+180h+var_150], xmm7
0x100430002  comisd  xmm9, xmm6
0x100430007  jbe     short loc_100430013
0x100430009  movaps  xmm6, xmm9
0x10043000d  movsd   qword ptr [rsp+180h+var_150+8], xmm6
0x100430013  test    bl, bl
0x100430015  jnz     short loc_100430033
0x100430017  call    cs:__imp__isnan
0x10043001d  test    eax, eax
0x10043001f  jnz     short loc_100430033
0x100430021  movaps  xmm0, xmm9; X
0x100430025  call    cs:__imp__isnan
0x10043002b  test    eax, eax
0x10043002d  jz      loc_1004300CF
0x100430033  mov     bl, 1
0x100430035  jmp     loc_1004300CF
0x10043003a  cmp     esi, 3
0x10043003d  jnz     loc_1004300CF
0x100430043  lea     r8, [rdi+10h]
0x100430047  mov     [rsp+180h+var_130], r14
0x10043004c  mov     rdx, rdi
0x10043004f  lea     rcx, [rsp+180h+var_130]
0x100430054  call    ?ConstructFrom3Points@?$CCircularArc@V?$CMglPoint@N@@@@QEAAXAEBV?$CMglPoint@N@@PEBV2@@Z; CCircularArc<CMglPoint<double>>::ConstructFrom3Points(CMglPoint<double> const &,CMglPoint<double> const *)
0x100430059  ucomisd xmm11, [rbp+80h+var_B0]
0x10043005f  lea     rax, ??_7CGeodeticCircularArc@@6B@; const CGeodeticCircularArc::`vftable'
0x100430066  mov     [rsp+180h+var_130], rax
0x10043006b  jp      short loc_1004300A1
0x10043006d  jnz     short loc_1004300A1
0x10043006f  movsd   xmm0, qword ptr [rdi+20h]
0x100430074  comisd  xmm10, xmm0
0x100430079  jbe     short loc_100430085
0x10043007b  movsd   qword ptr [rsp+180h+var_160], xmm0
0x100430081  movaps  xmm10, xmm0
0x100430085  comisd  xmm0, xmm8
0x10043008a  jbe     short loc_100430096
0x10043008c  movsd   qword ptr [rsp+180h+var_160+8], xmm0
0x100430092  movaps  xmm8, xmm0
0x100430096  movsd   xmm9, qword ptr [rdi+28h]
0x10043009c  jmp     loc_10042FFF1
0x1004300a1  lea     rdx, [rsp+180h+var_160]; struct CBounds *
0x1004300a6  lea     rcx, [rsp+180h+var_130]; this
0x1004300ab  call    ?UpdateBounds@CCircularArc2D@@QEBAXAEAVCBounds@@@Z; CCircularArc2D::UpdateBounds(CBounds &)
0x1004300b0  movzx   ebx, [rsp+180h+var_140]
0x1004300b5  movsd   xmm6, qword ptr [rsp+180h+var_150+8]
0x1004300bb  movsd   xmm7, qword ptr [rsp+180h+var_150]
0x1004300c1  movsd   xmm8, qword ptr [rsp+180h+var_160+8]
0x1004300c8  movsd   xmm10, qword ptr [rsp+180h+var_160]
0x1004300cf  inc     r15d
0x1004300d2  add     r12d, 0FFFFFFFFh
0x1004300d6  jnz     loc_10042FF20
0x1004300dc  mov     r14, [rbp+80h+arg_8]
0x1004300e3  movaps  xmm11, [rsp+180h+var_80]
0x1004300ec  movaps  xmm9, [rsp+180h+var_60]
0x1004300f5  mov     rdi, [rsp+180h+arg_18]
0x1004300fd  mov     rsi, [rsp+180h+arg_10]
0x100430105  mov     r15, [rsp+180h+var_20]
0x10043010d  test    bl, bl
0x10043010f  mov     rbx, [rsp+180h+arg_0]
0x100430117  mov     r13, [rsp+180h+var_18]
0x10043011f  mov     r12, [rsp+180h+var_10]
0x100430127  jz      short loc_100430144
0x100430129  movss   xmm0, cs:?FLOAT_QNAN@@3MB; float const FLOAT_QNAN
0x100430131  cvtps2pd xmm0, xmm0
0x100430134  unpcklpd xmm0, xmm0
0x100430138  movups  xmmword ptr [r14+8], xmm0
0x10043013d  movups  xmmword ptr [r14+18h], xmm0
0x100430142  jmp     short loc_10043015C
0x100430144  movsd   qword ptr [r14+8], xmm10
0x10043014a  movsd   qword ptr [r14+10h], xmm7
0x100430150  movsd   qword ptr [r14+18h], xmm8
0x100430156  movsd   qword ptr [r14+20h], xmm6
0x10043015c  lea     r11, [rsp+180h+var_8]
0x100430164  xor     eax, eax
0x100430166  movaps  xmm6, xmmword ptr [r11-28h]
0x10043016b  movaps  xmm7, xmmword ptr [r11-38h]
0x100430170  movaps  xmm8, xmmword ptr [r11-48h]
0x100430175  movaps  xmm10, xmmword ptr [r11-68h]
0x10043017a  mov     rsp, r11
0x10043017d  pop     r14
0x10043017f  pop     rbp
0x100430180  retn
```
