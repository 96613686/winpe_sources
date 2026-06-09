# Mso::SVG::FeColorMatrixRenderer::ApplyUnaryFilter(GEL::IEffect const &,Mso::SVG::StyleResolveChain const &,GEL::Rect const &,Mso::SVG::PrimitiveUnitResolver const &,GEL::IColorResolver const *)

- ea: `0x1800fa340`
- end: `0x1800fa808`
- name: `?ApplyUnaryFilter@FeColorMatrixRenderer@SVG@Mso@@UEBA?AV?$TCntPtr@$$CBUIEffect@GEL@@@Ofc@@AEBUIEffect@GEL@@AEBVStyleResolveChain@23@AEBURect@7@AEBVPrimitiveUnitResolver@23@PEBUIColorResolver@7@@Z`
- size: `1224`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, void (__fastcall ***)(_QWORD), _QWORD *)`
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x1800fa340`
- `0x1800fbdc0`
- `0x1800fbf00`
- `0x18013d700`
- `0x18013e0c0`
- `0x18013e72c`
- `0x18013f794`
- `0x18013f7c4`
- `0x18013f7dc`
- `0x18013f810`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800fa801`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800fa801`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800fa66e`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800fa66e`
- `gfx!?Create@IEffectLuminanceToAlpha@GEL@@SA?AV?$TCntPtr@UIEffectLuminanceToAlpha@GEL@@@Ofc@@AEBUIEffect@2@W4ColorSpace@2@@Z` at `0x1800fa452`
- `gfx!?Create@IEffectLuminanceToAlpha@GEL@@SA?AV?$TCntPtr@UIEffectLuminanceToAlpha@GEL@@@Ofc@@AEBUIEffect@2@W4ColorSpace@2@@Z` at `0x1800fa452`
- `gfx!?Create@IEffectColorMatrix@GEL@@SA?AV?$TCntPtr@UIEffectColorMatrix@GEL@@@Ofc@@AEBUIEffect@2@AEBV?$array@N$0BE@@std@@W4ColorSpace@2@@Z` at `0x1800fa791`
- `gfx!?Create@IEffectColorMatrix@GEL@@SA?AV?$TCntPtr@UIEffectColorMatrix@GEL@@@Ofc@@AEBUIEffect@2@AEBV?$array@N$0BE@@std@@W4ColorSpace@2@@Z` at `0x1800fa791`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
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
    JUMPOUT(0x1800FA807LL);
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
0x1800fa340  mov     rax, rsp
0x1800fa343  push    rbp
0x1800fa344  push    rbx
0x1800fa345  push    rsi
0x1800fa346  push    rdi
0x1800fa347  push    r14
0x1800fa349  lea     rbp, [rax-78h]
0x1800fa34d  sub     rsp, 150h
0x1800fa354  movaps  xmmword ptr [rax-38h], xmm6
0x1800fa358  movaps  xmmword ptr [rax-48h], xmm7
0x1800fa35c  movaps  xmmword ptr [rax-58h], xmm8
0x1800fa361  movaps  xmmword ptr [rax-68h], xmm10
0x1800fa366  movaps  xmmword ptr [rax-78h], xmm11
0x1800fa36b  movaps  xmmword ptr [rax-88h], xmm12
0x1800fa373  mov     rax, cs:__security_cookie
0x1800fa37a  xor     rax, rsp
0x1800fa37d  mov     [rbp+70h+var_90], rax
0x1800fa381  mov     r14, r9
0x1800fa384  mov     rdi, r8
0x1800fa387  mov     rsi, rdx
0x1800fa38a  mov     [rsp+170h+var_140], rdx
0x1800fa38f  mov     rbx, [rcx+10h]
0x1800fa393  test    rbx, rbx
0x1800fa396  jz      loc_1800FA7FA
0x1800fa39c  mov     edx, 23D8h
0x1800fa3a1  mov     r8d, 0AC8h
0x1800fa3a7  mov     rcx, [rbx]
0x1800fa3aa  call    __castguard_slow_path_check_user_handled
0x1800fa3af  test    rbx, rbx
0x1800fa3b2  jz      short loc_1800FA3C4
0x1800fa3b4  xor     r8d, r8d
0x1800fa3b7  mov     edx, 2548h
0x1800fa3bc  mov     rcx, [rbx]
0x1800fa3bf  call    __castguard_slow_path_check_user_handled
0x1800fa3c4  cmp     byte ptr [rbx+208h], 0
0x1800fa3cb  jz      short loc_1800FA3E7
0x1800fa3cd  mov     [rsi], rdi
0x1800fa3d0  test    rdi, rdi
0x1800fa3d3  jz      loc_1800FA7BB
0x1800fa3d9  mov     rax, [rdi]
0x1800fa3dc  mov     rcx, rdi
0x1800fa3df  mov     rax, [rax]
0x1800fa3e2  jmp     loc_1800FA7B5
0x1800fa3e7  mov     rdx, [r14+8]
0x1800fa3eb  mov     rcx, [rdx+10h]
0x1800fa3ef  test    rcx, rcx
0x1800fa3f2  jz      short loc_1800FA3FD
0x1800fa3f4  add     rcx, 528h
0x1800fa3fb  jmp     short loc_1800FA412
0x1800fa3fd  cmp     qword ptr [rdx+8], 0
0x1800fa402  lea     rcx, ?initial@?$StyleMetaData@$00@SVG@Mso@@2V?$optional@W4ColorSpace@GEL@@@std@@B; std::optional<GEL::ColorSpace> const Mso::SVG::StyleMetaData<1>::initial
0x1800fa409  jz      short loc_1800FA412
0x1800fa40b  lea     rcx, ?inherit@?$StyleMetaData@$00@SVG@Mso@@2V?$optional@W4ColorSpace@GEL@@@std@@B; std::optional<GEL::ColorSpace> const Mso::SVG::StyleMetaData<1>::inherit
0x1800fa412  mov     eax, 8
0x1800fa417  cmp     byte ptr [rcx+1], 0
0x1800fa41b  jnz     short loc_1800FA43B
0x1800fa41d  mov     rcx, [r14]
0x1800fa420  test    rcx, rcx
0x1800fa423  jz      short loc_1800FA42C
0x1800fa425  call    ??$Get@$00@StyleResolveChain@SVG@Mso@@QEBAAEBW4ColorSpace@GEL@@XZ; Mso::SVG::StyleResolveChain::Get<1>(void)
0x1800fa42a  jmp     short loc_1800FA438
0x1800fa42c  mov     rdx, [rax+rdx]
0x1800fa430  mov     rcx, r14
0x1800fa433  call    ??$GetNormal@$00@StyleResolveChain@SVG@Mso@@AEBAAEBW4ColorSpace@GEL@@AEBVStyle@12@@Z; Mso::SVG::StyleResolveChain::GetNormal<1>(Mso::SVG::Style const &)
0x1800fa438  mov     rcx, rax
0x1800fa43b  mov     r14b, [rcx]
0x1800fa43e  cmp     byte ptr [rbx+1E8h], 3
0x1800fa445  jnz     short loc_1800FA47F
0x1800fa447  mov     r8b, r14b
0x1800fa44a  mov     rdx, rdi
0x1800fa44d  lea     rcx, [rsp+170h+var_140]
0x1800fa452  call    cs:__imp_?Create@IEffectLuminanceToAlpha@GEL@@SA?AV?$TCntPtr@UIEffectLuminanceToAlpha@GEL@@@Ofc@@AEBUIEffect@2@W4ColorSpace@2@@Z; GEL::IEffectLuminanceToAlpha::Create(GEL::IEffect const &,GEL::ColorSpace)
0x1800fa458  mov     rcx, [rax]
0x1800fa45b  mov     qword ptr [rax], 0
0x1800fa462  mov     [rsi], rcx
0x1800fa465  mov     rcx, [rsp+170h+var_140]
0x1800fa46a  test    rcx, rcx
0x1800fa46d  jz      loc_1800FA7BB
0x1800fa473  mov     rax, [rcx]
0x1800fa476  mov     rax, [rax+8]
0x1800fa47a  jmp     loc_1800FA7B5
0x1800fa47f  xor     edx, edx; Val
0x1800fa481  mov     r8d, 0A0h; Size
0x1800fa487  lea     rcx, [rsp+170h+var_130]; void *
0x1800fa48c  call    memset_0
0x1800fa491  movzx   ecx, byte ptr [rbx+1E8h]
0x1800fa498  test    ecx, ecx
0x1800fa49a  jz      loc_1800FA74B
0x1800fa4a0  sub     ecx, 1
0x1800fa4a3  jz      loc_1800FA641
0x1800fa4a9  cmp     ecx, 1
0x1800fa4ac  jnz     loc_1800FA781
0x1800fa4b2  mov     rcx, [rbx+1F0h]
0x1800fa4b9  mov     rax, [rbx+1F8h]
0x1800fa4c0  sub     rax, rcx
0x1800fa4c3  sar     rax, 3
0x1800fa4c7  test    rax, rax
0x1800fa4ca  jz      loc_1800FA65B
0x1800fa4d0  movsd   xmm6, qword ptr [rcx]
0x1800fa4d4  mulsd   xmm6, cs:__real@400921fb54442d18
0x1800fa4dc  divsd   xmm6, cs:__real@4066800000000000
0x1800fa4e4  movaps  xmm0, xmm6; X
0x1800fa4e7  call    cos_0
0x1800fa4ec  movaps  xmm12, xmm0
0x1800fa4f0  movaps  xmm0, xmm6; X
0x1800fa4f3  call    sin_0
0x1800fa4f8  movaps  xmm11, xmm0
0x1800fa4fc  movaps  xmm10, xmm0
0x1800fa500  movsd   xmm5, cs:__real@3fe6e147ae147ae1
0x1800fa508  mulsd   xmm10, xmm5
0x1800fa50d  movaps  xmm1, xmm12
0x1800fa511  mulsd   xmm1, xmm5
0x1800fa515  movaps  xmm8, xmm5
0x1800fa519  subsd   xmm8, xmm1
0x1800fa51e  movaps  xmm2, xmm12
0x1800fa522  mulsd   xmm2, cs:__real@3fb26e978d4fdf3b
0x1800fa52a  movsd   xmm6, cs:__real@3fb26e978d4fdf3b
0x1800fa532  subsd   xmm6, xmm2
0x1800fa536  movaps  xmm0, xmm12
0x1800fa53a  movsd   xmm2, cs:__real@3fcb4395810624dd
0x1800fa542  mulsd   xmm0, xmm2
0x1800fa546  movaps  xmm7, xmm2
0x1800fa549  subsd   xmm7, xmm0
0x1800fa54d  movaps  xmm1, xmm12
0x1800fa551  mulsd   xmm1, cs:__real@3fe92f1a9fbe76c9
0x1800fa559  addsd   xmm1, xmm2
0x1800fa55d  movaps  xmm0, xmm11
0x1800fa561  mulsd   xmm0, xmm2
0x1800fa565  subsd   xmm1, xmm0
0x1800fa569  movsd   [rsp+170h+var_130], xmm1
0x1800fa56f  movaps  xmm0, xmm8
0x1800fa573  subsd   xmm0, xmm10
0x1800fa578  movsd   [rsp+170h+var_128], xmm0
0x1800fa57e  movaps  xmm1, xmm11
0x1800fa582  mulsd   xmm1, cs:__real@3fedb22d0e560419
0x1800fa58a  addsd   xmm1, xmm6
0x1800fa58e  movsd   qword ptr [rsp+170h+var_120], xmm1
0x1800fa594  xorps   xmm3, xmm3
0x1800fa597  movups  xmmword ptr [rsp+170h+var_120+8], xmm3
0x1800fa59c  movaps  xmm0, xmm11
0x1800fa5a0  mulsd   xmm0, cs:__real@3fc24dd2f1a9fbe7
0x1800fa5a8  addsd   xmm0, xmm7
0x1800fa5ac  movsd   [rsp+170h+var_108], xmm0
0x1800fa5b2  movaps  xmm1, xmm12
0x1800fa5b6  mulsd   xmm1, cs:__real@3fd23d70a3d70a3d
0x1800fa5be  addsd   xmm1, xmm5
0x1800fa5c2  movaps  xmm0, xmm11
0x1800fa5c6  mulsd   xmm0, cs:__real@3fc1eb851eb851ec
0x1800fa5ce  addsd   xmm1, xmm0
0x1800fa5d2  movsd   [rsp+170h+var_100], xmm1
0x1800fa5d8  movaps  xmm1, xmm11
0x1800fa5dc  mulsd   xmm1, cs:__real@3fd21cac083126e9
0x1800fa5e4  subsd   xmm6, xmm1
0x1800fa5e8  movsd   [rsp+170h+var_F8], xmm6
0x1800fa5ee  movaps  xmm1, xmm11
0x1800fa5f2  mulsd   xmm1, cs:__real@3fe92f1a9fbe76c9
0x1800fa5fa  subsd   xmm7, xmm1
0x1800fa5fe  movsd   [rbp+70h+var_E0], xmm7
0x1800fa603  addsd   xmm8, xmm10
0x1800fa608  movsd   [rbp+70h+var_D8], xmm8
0x1800fa60e  mulsd   xmm12, cs:__real@3fedb22d0e560419
0x1800fa617  addsd   xmm12, cs:__real@3fb26e978d4fdf3b
0x1800fa620  mulsd   xmm11, cs:__real@3fb26e978d4fdf3b
0x1800fa629  addsd   xmm12, xmm11
0x1800fa62e  movsd   [rbp+70h+var_D0], xmm12
0x1800fa634  movsd   [rbp+70h+var_C8], xmm3
0x1800fa639  xorps   xmm1, xmm1
0x1800fa63c  jmp     loc_1800FA72E
0x1800fa641  mov     rcx, [rbx+1F0h]
0x1800fa648  mov     rax, [rbx+1F8h]
0x1800fa64f  sub     rax, rcx
0x1800fa652  sar     rax, 3
0x1800fa656  test    rax, rax
0x1800fa659  jnz     short loc_1800FA675
0x1800fa65b  mov     [rsp+170h+Reserved], 0; Reserved
0x1800fa664  xor     r9d, r9d; LineNo
0x1800fa667  xor     r8d, r8d; FileName
0x1800fa66a  xor     edx, edx; FunctionName
0x1800fa66c  xor     ecx, ecx; Expression
0x1800fa66e  call    cs:__imp__invoke_watson
0x1800fa675  movsd   xmm8, qword ptr [rcx]
0x1800fa67a  movaps  xmm0, xmm8
0x1800fa67e  movsd   xmm5, cs:__real@3fe6e147ae147ae1
0x1800fa686  mulsd   xmm0, xmm5
0x1800fa68a  movaps  xmm6, xmm5
0x1800fa68d  subsd   xmm6, xmm0
0x1800fa691  movaps  xmm1, xmm8
0x1800fa695  movsd   xmm7, cs:__real@3fb26e978d4fdf3b
0x1800fa69d  mulsd   xmm1, xmm7
0x1800fa6a1  movaps  xmm4, xmm7
0x1800fa6a4  subsd   xmm4, xmm1
0x1800fa6a8  movaps  xmm0, xmm8
0x1800fa6ac  movsd   xmm2, cs:__real@3fcb4395810624dd
0x1800fa6b4  mulsd   xmm0, xmm2
0x1800fa6b8  movaps  xmm3, xmm2
0x1800fa6bb  subsd   xmm3, xmm0
0x1800fa6bf  movaps  xmm1, xmm8
0x1800fa6c3  mulsd   xmm1, cs:__real@3fe92f1a9fbe76c9
0x1800fa6cb  addsd   xmm1, xmm2
0x1800fa6cf  movsd   [rsp+170h+var_130], xmm1
0x1800fa6d5  movsd   [rsp+170h+var_128], xmm6
0x1800fa6db  movsd   qword ptr [rsp+170h+var_120], xmm4
0x1800fa6e1  xorps   xmm1, xmm1
0x1800fa6e4  movups  xmmword ptr [rsp+170h+var_120+8], xmm1
0x1800fa6e9  movsd   [rsp+170h+var_108], xmm3
0x1800fa6ef  movaps  xmm0, xmm8
0x1800fa6f3  mulsd   xmm0, cs:__real@3fd23d70a3d70a3d
0x1800fa6fb  addsd   xmm0, xmm5
0x1800fa6ff  movsd   [rsp+170h+var_100], xmm0
0x1800fa705  movsd   [rsp+170h+var_F8], xmm4
0x1800fa70b  movsd   [rbp+70h+var_E0], xmm3
0x1800fa710  movsd   [rbp+70h+var_D8], xmm6
0x1800fa715  mulsd   xmm8, cs:__real@3fef6c8b43958106
0x1800fa71e  addsd   xmm8, xmm7
0x1800fa723  movsd   [rbp+70h+var_D0], xmm8
0x1800fa729  movsd   [rbp+70h+var_C8], xmm1
0x1800fa72e  xorps   xmm0, xmm0
0x1800fa731  movaps  [rbp+70h+var_C0], xmm0
0x1800fa735  movaps  [rbp+70h+var_F0], xmm0
0x1800fa739  movaps  [rbp+70h+var_B0], xmm1
0x1800fa73d  movdqa  xmm0, cs:__xmm@00000000000000003ff0000000000000
0x1800fa745  movaps  [rbp+70h+var_A0], xmm0
0x1800fa749  jmp     short loc_1800FA781
0x1800fa74b  mov     rdx, [rbx+1F0h]; Src
0x1800fa752  mov     rax, [rbx+1F8h]
0x1800fa759  sub     rax, rdx
0x1800fa75c  sar     rax, 3
0x1800fa760  mov     r8d, 14h
0x1800fa766  cmp     rax, r8
0x1800fa769  ja      short loc_1800FA773
0x1800fa76b  mov     r8, rax
0x1800fa76e  test    rax, rax
0x1800fa771  jz      short loc_1800FA781
0x1800fa773  shl     r8, 3; Size
0x1800fa777  lea     rcx, [rsp+170h+var_130]; void *
0x1800fa77c  call    memmove_0
0x1800fa781  mov     r9b, r14b
0x1800fa784  lea     r8, [rsp+170h+var_130]
0x1800fa789  mov     rdx, rdi
0x1800fa78c  lea     rcx, [rsp+170h+var_140]
0x1800fa791  call    cs:__imp_?Create@IEffectColorMatrix@GEL@@SA?AV?$TCntPtr@UIEffectColorMatrix@GEL@@@Ofc@@AEBUIEffect@2@AEBV?$array@N$0BE@@std@@W4ColorSpace@2@@Z; GEL::IEffectColorMatrix::Create(GEL::IEffect const &,std::array<double,20> const &,GEL::ColorSpace)
0x1800fa797  mov     rcx, [rax]
0x1800fa79a  mov     qword ptr [rax], 0
0x1800fa7a1  mov     [rsi], rcx
0x1800fa7a4  mov     rcx, [rsp+170h+var_140]
0x1800fa7a9  test    rcx, rcx
0x1800fa7ac  jz      short loc_1800FA7BB
0x1800fa7ae  mov     rdx, [rcx]
0x1800fa7b1  mov     rax, [rdx+8]
0x1800fa7b5  call    cs:__guard_dispatch_icall_fptr
0x1800fa7bb  mov     rax, rsi
0x1800fa7be  mov     rcx, [rbp+70h+var_90]
0x1800fa7c2  xor     rcx, rsp; StackCookie
0x1800fa7c5  call    __security_check_cookie
0x1800fa7ca  lea     r11, [rsp+170h+var_20]
0x1800fa7d2  movaps  xmm6, xmmword ptr [r11-10h]
0x1800fa7d7  movaps  xmm7, xmmword ptr [r11-20h]
0x1800fa7dc  movaps  xmm8, xmmword ptr [r11-30h]
0x1800fa7e1  movaps  xmm10, xmmword ptr [r11-40h]
0x1800fa7e6  movaps  xmm11, xmmword ptr [r11-50h]
0x1800fa7eb  movaps  xmm12, xmmword ptr [r11-60h]
0x1800fa7f0  mov     rsp, r11
0x1800fa7f3  pop     r14
0x1800fa7f5  pop     rdi
0x1800fa7f6  pop     rsi
0x1800fa7f7  pop     rbx
0x1800fa7f8  pop     rbp
0x1800fa7f9  retn
0x1800fa7fa  xor     edx, edx
0x1800fa7fc  mov     ecx, 1E3C3843h
0x1800fa801  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
```
