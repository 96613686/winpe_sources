# Mso::SVG::FeColorMatrixRenderer::ApplyUnaryFilter(GEL::IEffect const &,Mso::SVG::StyleResolveChain const &,GEL::Rect const &,Mso::SVG::PrimitiveUnitResolver const &,GEL::IColorResolver const *)

- ea: `0x1800fa320`
- end: `0x1800fa7e8`
- name: `?ApplyUnaryFilter@FeColorMatrixRenderer@SVG@Mso@@UEBA?AV?$TCntPtr@$$CBUIEffect@GEL@@@Ofc@@AEBUIEffect@GEL@@AEBVStyleResolveChain@23@AEBURect@7@AEBVPrimitiveUnitResolver@23@PEBUIColorResolver@7@@Z`
- size: `1224`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x1800fa320`
- `0x1800fbda0`
- `0x1800fbee0`
- `0x18013d650`
- `0x18013e010`
- `0x18013e67c`
- `0x18013f6e4`
- `0x18013f714`
- `0x18013f72c`
- `0x18013f760`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800fa7e1`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800fa7e1`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800fa64e`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800fa64e`
- `gfx!?Create@IEffectLuminanceToAlpha@GEL@@SA?AV?$TCntPtr@UIEffectLuminanceToAlpha@GEL@@@Ofc@@AEBUIEffect@2@W4ColorSpace@2@@Z` at `0x1800fa432`
- `gfx!?Create@IEffectLuminanceToAlpha@GEL@@SA?AV?$TCntPtr@UIEffectLuminanceToAlpha@GEL@@@Ofc@@AEBUIEffect@2@W4ColorSpace@2@@Z` at `0x1800fa432`
- `gfx!?Create@IEffectColorMatrix@GEL@@SA?AV?$TCntPtr@UIEffectColorMatrix@GEL@@@Ofc@@AEBUIEffect@2@AEBV?$array@N$0BE@@std@@W4ColorSpace@2@@Z` at `0x1800fa771`
- `gfx!?Create@IEffectColorMatrix@GEL@@SA?AV?$TCntPtr@UIEffectColorMatrix@GEL@@@Ofc@@AEBUIEffect@2@AEBV?$array@N$0BE@@std@@W4ColorSpace@2@@Z` at `0x1800fa771`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall Mso::SVG::FeColorMatrixRenderer::ApplyUnaryFilter(
        __int64 a1,
        _QWORD *a2,
        void (__fastcall ***a3)(_QWORD),
        _QWORD *a4)
{
  _QWORD *v7; // rbx
  __int64 v8; // r8
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int16 *v11; // rcx
  __int64 v12; // rax
  char v13; // r14
  __int64 *v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // r9
  double *v18; // rcx
  double v19; // xmm6_8
  double v20; // xmm12_8
  double v21; // xmm0_8
  double v22; // xmm6_8
  double v23; // xmm7_8
  __int128 v24; // xmm1
  double *v25; // rcx
  double v26; // xmm8_8
  double v27; // xmm6_8
  double v28; // xmm4_8
  double v29; // xmm3_8
  const void *v30; // rdx
  unsigned __int64 v31; // rax
  __int64 v32; // r8
  __int64 *v33; // rax
  __int64 v34; // rcx
  _QWORD v36[2]; // [rsp+38h] [rbp-D0h] BYREF
  double v37; // [rsp+48h] [rbp-C0h] BYREF
  double v38; // [rsp+50h] [rbp-B8h]
  double v39[3]; // [rsp+58h] [rbp-B0h]
  double v40; // [rsp+70h] [rbp-98h]
  double v41; // [rsp+78h] [rbp-90h]
  double v42; // [rsp+80h] [rbp-88h]
  __int128 v43; // [rsp+88h] [rbp-80h]
  double v44; // [rsp+98h] [rbp-70h]
  double v45; // [rsp+A0h] [rbp-68h]
  double v46; // [rsp+A8h] [rbp-60h]
  __int64 v47; // [rsp+B0h] [rbp-58h]
  __int128 v48; // [rsp+B8h] [rbp-50h]
  __int128 v49; // [rsp+C8h] [rbp-40h]
  __m128i si128; // [rsp+D8h] [rbp-30h]

  v36[0] = a2;
  v7 = *(_QWORD **)(a1 + 16);
  if ( !v7 )
  {
    CrashWithRecovery(0x1E3C3843u, 0);
    JUMPOUT(0x1800FA7E7LL);
  }
  _castguard_slow_path_check_user_handled(*v7, 9176, 2760);
  _castguard_slow_path_check_user_handled(*v7, 9544, 0);
  if ( !*((_BYTE *)v7 + 520) )
  {
    v9 = a4[1];
    v10 = *(_QWORD *)(v9 + 16);
    if ( v10 )
    {
      v11 = (__int16 *)(v10 + 1320);
    }
    else
    {
      v11 = &Mso::SVG::StyleMetaData<1>::initial;
      if ( *(_QWORD *)(v9 + 8) )
        v11 = (__int16 *)&Mso::SVG::StyleMetaData<1>::inherit;
    }
    if ( !*((_BYTE *)v11 + 1) )
    {
      if ( *a4 )
        v12 = Mso::SVG::StyleResolveChain::Get<1>();
      else
        v12 = Mso::SVG::StyleResolveChain::GetNormal<1>(a4, *(_QWORD *)(v9 + 8));
      v11 = (__int16 *)v12;
    }
    v13 = *(_BYTE *)v11;
    if ( *((_BYTE *)v7 + 488) == 3 )
    {
      LOBYTE(v8) = *(_BYTE *)v11;
      v14 = (__int64 *)GEL::IEffectLuminanceToAlpha::Create(v36, a3, v8);
      v15 = *v14;
      *v14 = 0;
      *a2 = v15;
      v16 = v36[0];
      if ( !v36[0] )
        return a2;
LABEL_30:
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v36[0] + 8LL))(v16);
      return a2;
    }
    memset_0(&v37, 0, 0xA0u);
    switch ( *((_BYTE *)v7 + 488) )
    {
      case 0:
        v30 = (const void *)v7[62];
        v31 = (__int64)(v7[63] - (_QWORD)v30) >> 3;
        v32 = 20;
        if ( v31 > 0x14 || (v32 = (__int64)(v7[63] - (_QWORD)v30) >> 3, v31) )
          memmove_0(&v37, v30, 8 * v32);
LABEL_29:
        LOBYTE(v17) = v13;
        v33 = (__int64 *)GEL::IEffectColorMatrix::Create(v36, a3, &v37, v17);
        v34 = *v33;
        *v33 = 0;
        *a2 = v34;
        v16 = v36[0];
        if ( !v36[0] )
          return a2;
        goto LABEL_30;
      case 1:
        v25 = (double *)v7[62];
        if ( (__int64)(v7[63] - (_QWORD)v25) >> 3 )
        {
          v26 = *v25;
          v27 = 0.715 - *v25 * 0.715;
          v28 = 0.07199999999999999 - *v25 * 0.07199999999999999;
          v29 = 0.213 - *v25 * 0.213;
          v37 = *v25 * 0.787 + 0.213;
          v38 = v27;
          v39[0] = v28;
          v24 = 0;
          *(_OWORD *)&v39[1] = 0;
          v40 = v29;
          v41 = v26 * 0.285 + 0.715;
          v42 = v28;
          v44 = v29;
          v45 = v27;
          v46 = v26 * 0.982 + 0.07199999999999999;
          v47 = 0;
          goto LABEL_25;
        }
        break;
      case 2:
        v18 = (double *)v7[62];
        if ( (__int64)(v7[63] - (_QWORD)v18) >> 3 )
        {
          v19 = *v18 * 3.141592653589793 / 180.0;
          v20 = cos_0(v19);
          v21 = sin_0(v19);
          v22 = 0.07199999999999999 - v20 * 0.07199999999999999;
          v23 = 0.213 - v20 * 0.213;
          v37 = v20 * 0.787 + 0.213 - v21 * 0.213;
          v38 = 0.715 - v20 * 0.715 - v21 * 0.715;
          v39[0] = v21 * 0.928 + v22;
          *(_OWORD *)&v39[1] = 0;
          v40 = v21 * 0.143 + v23;
          v41 = v20 * 0.285 + 0.715 + v21 * 0.14;
          v42 = v22 - v21 * 0.283;
          v44 = v23 - v21 * 0.787;
          v45 = 0.715 - v20 * 0.715 + v21 * 0.715;
          v46 = v20 * 0.928 + 0.07199999999999999 + v21 * 0.07199999999999999;
          v47 = 0;
          v24 = 0;
LABEL_25:
          v48 = 0;
          v43 = 0;
          v49 = v24;
          si128 = _mm_load_si128((const __m128i *)&_xmm);
          goto LABEL_29;
        }
        break;
      default:
        goto LABEL_29;
    }
    _invoke_watson(0, 0, 0, 0, 0);
  }
  *a2 = a3;
  if ( a3 )
    (**a3)(a3);
  return a2;
}

```

## disassembly

```asm
0x1800fa320  mov     rax, rsp
0x1800fa323  push    rbp
0x1800fa324  push    rbx
0x1800fa325  push    rsi
0x1800fa326  push    rdi
0x1800fa327  push    r14
0x1800fa329  lea     rbp, [rax-78h]
0x1800fa32d  sub     rsp, 150h
0x1800fa334  movaps  xmmword ptr [rax-38h], xmm6
0x1800fa338  movaps  xmmword ptr [rax-48h], xmm7
0x1800fa33c  movaps  xmmword ptr [rax-58h], xmm8
0x1800fa341  movaps  xmmword ptr [rax-68h], xmm10
0x1800fa346  movaps  xmmword ptr [rax-78h], xmm11
0x1800fa34b  movaps  xmmword ptr [rax-88h], xmm12
0x1800fa353  mov     rax, cs:__security_cookie
0x1800fa35a  xor     rax, rsp
0x1800fa35d  mov     [rbp+70h+var_90], rax
0x1800fa361  mov     r14, r9
0x1800fa364  mov     rdi, r8
0x1800fa367  mov     rsi, rdx
0x1800fa36a  mov     [rsp+170h+var_140], rdx
0x1800fa36f  mov     rbx, [rcx+10h]
0x1800fa373  test    rbx, rbx
0x1800fa376  jz      loc_1800FA7DA
0x1800fa37c  mov     edx, 23D8h
0x1800fa381  mov     r8d, 0AC8h
0x1800fa387  mov     rcx, [rbx]
0x1800fa38a  call    __castguard_slow_path_check_user_handled
0x1800fa38f  test    rbx, rbx
0x1800fa392  jz      short loc_1800FA3A4
0x1800fa394  xor     r8d, r8d
0x1800fa397  mov     edx, 2548h
0x1800fa39c  mov     rcx, [rbx]
0x1800fa39f  call    __castguard_slow_path_check_user_handled
0x1800fa3a4  cmp     byte ptr [rbx+208h], 0
0x1800fa3ab  jz      short loc_1800FA3C7
0x1800fa3ad  mov     [rsi], rdi
0x1800fa3b0  test    rdi, rdi
0x1800fa3b3  jz      loc_1800FA79B
0x1800fa3b9  mov     rax, [rdi]
0x1800fa3bc  mov     rcx, rdi
0x1800fa3bf  mov     rax, [rax]
0x1800fa3c2  jmp     loc_1800FA795
0x1800fa3c7  mov     rdx, [r14+8]
0x1800fa3cb  mov     rcx, [rdx+10h]
0x1800fa3cf  test    rcx, rcx
0x1800fa3d2  jz      short loc_1800FA3DD
0x1800fa3d4  add     rcx, 528h
0x1800fa3db  jmp     short loc_1800FA3F2
0x1800fa3dd  cmp     qword ptr [rdx+8], 0
0x1800fa3e2  lea     rcx, ?initial@?$StyleMetaData@$00@SVG@Mso@@2V?$optional@W4ColorSpace@GEL@@@std@@B; std::optional<GEL::ColorSpace> const Mso::SVG::StyleMetaData<1>::initial
0x1800fa3e9  jz      short loc_1800FA3F2
0x1800fa3eb  lea     rcx, ?inherit@?$StyleMetaData@$00@SVG@Mso@@2V?$optional@W4ColorSpace@GEL@@@std@@B; std::optional<GEL::ColorSpace> const Mso::SVG::StyleMetaData<1>::inherit
0x1800fa3f2  mov     eax, 8
0x1800fa3f7  cmp     byte ptr [rcx+1], 0
0x1800fa3fb  jnz     short loc_1800FA41B
0x1800fa3fd  mov     rcx, [r14]
0x1800fa400  test    rcx, rcx
0x1800fa403  jz      short loc_1800FA40C
0x1800fa405  call    ??$Get@$00@StyleResolveChain@SVG@Mso@@QEBAAEBW4ColorSpace@GEL@@XZ; Mso::SVG::StyleResolveChain::Get<1>(void)
0x1800fa40a  jmp     short loc_1800FA418
0x1800fa40c  mov     rdx, [rax+rdx]
0x1800fa410  mov     rcx, r14
0x1800fa413  call    ??$GetNormal@$00@StyleResolveChain@SVG@Mso@@AEBAAEBW4ColorSpace@GEL@@AEBVStyle@12@@Z; Mso::SVG::StyleResolveChain::GetNormal<1>(Mso::SVG::Style const &)
0x1800fa418  mov     rcx, rax
0x1800fa41b  mov     r14b, [rcx]
0x1800fa41e  cmp     byte ptr [rbx+1E8h], 3
0x1800fa425  jnz     short loc_1800FA45F
0x1800fa427  mov     r8b, r14b
0x1800fa42a  mov     rdx, rdi
0x1800fa42d  lea     rcx, [rsp+170h+var_140]
0x1800fa432  call    cs:__imp_?Create@IEffectLuminanceToAlpha@GEL@@SA?AV?$TCntPtr@UIEffectLuminanceToAlpha@GEL@@@Ofc@@AEBUIEffect@2@W4ColorSpace@2@@Z; GEL::IEffectLuminanceToAlpha::Create(GEL::IEffect const &,GEL::ColorSpace)
0x1800fa438  mov     rcx, [rax]
0x1800fa43b  mov     qword ptr [rax], 0
0x1800fa442  mov     [rsi], rcx
0x1800fa445  mov     rcx, [rsp+170h+var_140]
0x1800fa44a  test    rcx, rcx
0x1800fa44d  jz      loc_1800FA79B
0x1800fa453  mov     rax, [rcx]
0x1800fa456  mov     rax, [rax+8]
0x1800fa45a  jmp     loc_1800FA795
0x1800fa45f  xor     edx, edx; Val
0x1800fa461  mov     r8d, 0A0h; Size
0x1800fa467  lea     rcx, [rsp+170h+var_130]; void *
0x1800fa46c  call    memset_0
0x1800fa471  movzx   ecx, byte ptr [rbx+1E8h]
0x1800fa478  test    ecx, ecx
0x1800fa47a  jz      loc_1800FA72B
0x1800fa480  sub     ecx, 1
0x1800fa483  jz      loc_1800FA621
0x1800fa489  cmp     ecx, 1
0x1800fa48c  jnz     loc_1800FA761
0x1800fa492  mov     rcx, [rbx+1F0h]
0x1800fa499  mov     rax, [rbx+1F8h]
0x1800fa4a0  sub     rax, rcx
0x1800fa4a3  sar     rax, 3
0x1800fa4a7  test    rax, rax
0x1800fa4aa  jz      loc_1800FA63B
0x1800fa4b0  movsd   xmm6, qword ptr [rcx]
0x1800fa4b4  mulsd   xmm6, cs:__real@400921fb54442d18
0x1800fa4bc  divsd   xmm6, cs:__real@4066800000000000
0x1800fa4c4  movaps  xmm0, xmm6; X
0x1800fa4c7  call    cos_0
0x1800fa4cc  movaps  xmm12, xmm0
0x1800fa4d0  movaps  xmm0, xmm6; X
0x1800fa4d3  call    sin_0
0x1800fa4d8  movaps  xmm11, xmm0
0x1800fa4dc  movaps  xmm10, xmm0
0x1800fa4e0  movsd   xmm5, cs:__real@3fe6e147ae147ae1
0x1800fa4e8  mulsd   xmm10, xmm5
0x1800fa4ed  movaps  xmm1, xmm12
0x1800fa4f1  mulsd   xmm1, xmm5
0x1800fa4f5  movaps  xmm8, xmm5
0x1800fa4f9  subsd   xmm8, xmm1
0x1800fa4fe  movaps  xmm2, xmm12
0x1800fa502  mulsd   xmm2, cs:__real@3fb26e978d4fdf3b
0x1800fa50a  movsd   xmm6, cs:__real@3fb26e978d4fdf3b
0x1800fa512  subsd   xmm6, xmm2
0x1800fa516  movaps  xmm0, xmm12
0x1800fa51a  movsd   xmm2, cs:__real@3fcb4395810624dd
0x1800fa522  mulsd   xmm0, xmm2
0x1800fa526  movaps  xmm7, xmm2
0x1800fa529  subsd   xmm7, xmm0
0x1800fa52d  movaps  xmm1, xmm12
0x1800fa531  mulsd   xmm1, cs:__real@3fe92f1a9fbe76c9
0x1800fa539  addsd   xmm1, xmm2
0x1800fa53d  movaps  xmm0, xmm11
0x1800fa541  mulsd   xmm0, xmm2
0x1800fa545  subsd   xmm1, xmm0
0x1800fa549  movsd   [rsp+170h+var_130], xmm1
0x1800fa54f  movaps  xmm0, xmm8
0x1800fa553  subsd   xmm0, xmm10
0x1800fa558  movsd   [rsp+170h+var_128], xmm0
0x1800fa55e  movaps  xmm1, xmm11
0x1800fa562  mulsd   xmm1, cs:__real@3fedb22d0e560419
0x1800fa56a  addsd   xmm1, xmm6
0x1800fa56e  movsd   qword ptr [rsp+170h+var_120], xmm1
0x1800fa574  xorps   xmm3, xmm3
0x1800fa577  movups  xmmword ptr [rsp+170h+var_120+8], xmm3
0x1800fa57c  movaps  xmm0, xmm11
0x1800fa580  mulsd   xmm0, cs:__real@3fc24dd2f1a9fbe7
0x1800fa588  addsd   xmm0, xmm7
0x1800fa58c  movsd   [rsp+170h+var_108], xmm0
0x1800fa592  movaps  xmm1, xmm12
0x1800fa596  mulsd   xmm1, cs:__real@3fd23d70a3d70a3d
0x1800fa59e  addsd   xmm1, xmm5
0x1800fa5a2  movaps  xmm0, xmm11
0x1800fa5a6  mulsd   xmm0, cs:__real@3fc1eb851eb851ec
0x1800fa5ae  addsd   xmm1, xmm0
0x1800fa5b2  movsd   [rsp+170h+var_100], xmm1
0x1800fa5b8  movaps  xmm1, xmm11
0x1800fa5bc  mulsd   xmm1, cs:__real@3fd21cac083126e9
0x1800fa5c4  subsd   xmm6, xmm1
0x1800fa5c8  movsd   [rsp+170h+var_F8], xmm6
0x1800fa5ce  movaps  xmm1, xmm11
0x1800fa5d2  mulsd   xmm1, cs:__real@3fe92f1a9fbe76c9
0x1800fa5da  subsd   xmm7, xmm1
0x1800fa5de  movsd   [rbp+70h+var_E0], xmm7
0x1800fa5e3  addsd   xmm8, xmm10
0x1800fa5e8  movsd   [rbp+70h+var_D8], xmm8
0x1800fa5ee  mulsd   xmm12, cs:__real@3fedb22d0e560419
0x1800fa5f7  addsd   xmm12, cs:__real@3fb26e978d4fdf3b
0x1800fa600  mulsd   xmm11, cs:__real@3fb26e978d4fdf3b
0x1800fa609  addsd   xmm12, xmm11
0x1800fa60e  movsd   [rbp+70h+var_D0], xmm12
0x1800fa614  movsd   [rbp+70h+var_C8], xmm3
0x1800fa619  xorps   xmm1, xmm1
0x1800fa61c  jmp     loc_1800FA70E
0x1800fa621  mov     rcx, [rbx+1F0h]
0x1800fa628  mov     rax, [rbx+1F8h]
0x1800fa62f  sub     rax, rcx
0x1800fa632  sar     rax, 3
0x1800fa636  test    rax, rax
0x1800fa639  jnz     short loc_1800FA655
0x1800fa63b  mov     [rsp+170h+Reserved], 0; Reserved
0x1800fa644  xor     r9d, r9d; LineNo
0x1800fa647  xor     r8d, r8d; FileName
0x1800fa64a  xor     edx, edx; FunctionName
0x1800fa64c  xor     ecx, ecx; Expression
0x1800fa64e  call    cs:__imp__invoke_watson
0x1800fa655  movsd   xmm8, qword ptr [rcx]
0x1800fa65a  movaps  xmm0, xmm8
0x1800fa65e  movsd   xmm5, cs:__real@3fe6e147ae147ae1
0x1800fa666  mulsd   xmm0, xmm5
0x1800fa66a  movaps  xmm6, xmm5
0x1800fa66d  subsd   xmm6, xmm0
0x1800fa671  movaps  xmm1, xmm8
0x1800fa675  movsd   xmm7, cs:__real@3fb26e978d4fdf3b
0x1800fa67d  mulsd   xmm1, xmm7
0x1800fa681  movaps  xmm4, xmm7
0x1800fa684  subsd   xmm4, xmm1
0x1800fa688  movaps  xmm0, xmm8
0x1800fa68c  movsd   xmm2, cs:__real@3fcb4395810624dd
0x1800fa694  mulsd   xmm0, xmm2
0x1800fa698  movaps  xmm3, xmm2
0x1800fa69b  subsd   xmm3, xmm0
0x1800fa69f  movaps  xmm1, xmm8
0x1800fa6a3  mulsd   xmm1, cs:__real@3fe92f1a9fbe76c9
0x1800fa6ab  addsd   xmm1, xmm2
0x1800fa6af  movsd   [rsp+170h+var_130], xmm1
0x1800fa6b5  movsd   [rsp+170h+var_128], xmm6
0x1800fa6bb  movsd   qword ptr [rsp+170h+var_120], xmm4
0x1800fa6c1  xorps   xmm1, xmm1
0x1800fa6c4  movups  xmmword ptr [rsp+170h+var_120+8], xmm1
0x1800fa6c9  movsd   [rsp+170h+var_108], xmm3
0x1800fa6cf  movaps  xmm0, xmm8
0x1800fa6d3  mulsd   xmm0, cs:__real@3fd23d70a3d70a3d
0x1800fa6db  addsd   xmm0, xmm5
0x1800fa6df  movsd   [rsp+170h+var_100], xmm0
0x1800fa6e5  movsd   [rsp+170h+var_F8], xmm4
0x1800fa6eb  movsd   [rbp+70h+var_E0], xmm3
0x1800fa6f0  movsd   [rbp+70h+var_D8], xmm6
0x1800fa6f5  mulsd   xmm8, cs:__real@3fef6c8b43958106
0x1800fa6fe  addsd   xmm8, xmm7
0x1800fa703  movsd   [rbp+70h+var_D0], xmm8
0x1800fa709  movsd   [rbp+70h+var_C8], xmm1
0x1800fa70e  xorps   xmm0, xmm0
0x1800fa711  movaps  [rbp+70h+var_C0], xmm0
0x1800fa715  movaps  [rbp+70h+var_F0], xmm0
0x1800fa719  movaps  [rbp+70h+var_B0], xmm1
0x1800fa71d  movdqa  xmm0, cs:__xmm@00000000000000003ff0000000000000
0x1800fa725  movaps  [rbp+70h+var_A0], xmm0
0x1800fa729  jmp     short loc_1800FA761
0x1800fa72b  mov     rdx, [rbx+1F0h]; Src
0x1800fa732  mov     rax, [rbx+1F8h]
0x1800fa739  sub     rax, rdx
0x1800fa73c  sar     rax, 3
0x1800fa740  mov     r8d, 14h
0x1800fa746  cmp     rax, r8
0x1800fa749  ja      short loc_1800FA753
0x1800fa74b  mov     r8, rax
0x1800fa74e  test    rax, rax
0x1800fa751  jz      short loc_1800FA761
0x1800fa753  shl     r8, 3; Size
0x1800fa757  lea     rcx, [rsp+170h+var_130]; void *
0x1800fa75c  call    memmove_0
0x1800fa761  mov     r9b, r14b
0x1800fa764  lea     r8, [rsp+170h+var_130]
0x1800fa769  mov     rdx, rdi
0x1800fa76c  lea     rcx, [rsp+170h+var_140]
0x1800fa771  call    cs:__imp_?Create@IEffectColorMatrix@GEL@@SA?AV?$TCntPtr@UIEffectColorMatrix@GEL@@@Ofc@@AEBUIEffect@2@AEBV?$array@N$0BE@@std@@W4ColorSpace@2@@Z; GEL::IEffectColorMatrix::Create(GEL::IEffect const &,std::array<double,20> const &,GEL::ColorSpace)
0x1800fa777  mov     rcx, [rax]
0x1800fa77a  mov     qword ptr [rax], 0
0x1800fa781  mov     [rsi], rcx
0x1800fa784  mov     rcx, [rsp+170h+var_140]
0x1800fa789  test    rcx, rcx
0x1800fa78c  jz      short loc_1800FA79B
0x1800fa78e  mov     rdx, [rcx]
0x1800fa791  mov     rax, [rdx+8]
0x1800fa795  call    cs:__guard_dispatch_icall_fptr
0x1800fa79b  mov     rax, rsi
0x1800fa79e  mov     rcx, [rbp+70h+var_90]
0x1800fa7a2  xor     rcx, rsp; StackCookie
0x1800fa7a5  call    __security_check_cookie
0x1800fa7aa  lea     r11, [rsp+170h+var_20]
0x1800fa7b2  movaps  xmm6, xmmword ptr [r11-10h]
0x1800fa7b7  movaps  xmm7, xmmword ptr [r11-20h]
0x1800fa7bc  movaps  xmm8, xmmword ptr [r11-30h]
0x1800fa7c1  movaps  xmm10, xmmword ptr [r11-40h]
0x1800fa7c6  movaps  xmm11, xmmword ptr [r11-50h]
0x1800fa7cb  movaps  xmm12, xmmword ptr [r11-60h]
0x1800fa7d0  mov     rsp, r11
0x1800fa7d3  pop     r14
0x1800fa7d5  pop     rdi
0x1800fa7d6  pop     rsi
0x1800fa7d7  pop     rbx
0x1800fa7d8  pop     rbp
0x1800fa7d9  retn
0x1800fa7da  xor     edx, edx
0x1800fa7dc  mov     ecx, 1E3C3843h
0x1800fa7e1  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
```
