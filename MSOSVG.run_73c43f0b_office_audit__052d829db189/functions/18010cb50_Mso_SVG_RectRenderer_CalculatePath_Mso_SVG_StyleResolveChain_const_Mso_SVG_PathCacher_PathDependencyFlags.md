# Mso::SVG::RectRenderer::CalculatePath(Mso::SVG::StyleResolveChain const &,Mso::SVG::PathCacher::PathDependencyFlags &)

- ea: `0x18010cb50`
- end: `0x18010cec6`
- name: `?CalculatePath@RectRenderer@SVG@Mso@@UEAA?AV?$TCntPtr@$$CBUIPath@GEL@@@3@AEBVStyleResolveChain@23@AEAW4PathDependencyFlags@PathCacher@23@@Z`
- size: `886`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18010cb50`
- `0x1801395e4`
- `0x18013e0c0`
- `0x18013f810`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18010cebf`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18010cebf`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18010cd34`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18010cd34`
- `gfx!?Create@IRectanglePath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@AEBU?$TRect@N@Math@@@Z` at `0x18010cddb`
- `gfx!?Create@IRectanglePath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@AEBU?$TRect@N@Math@@@Z` at `0x18010cddb`
- `gfx!?Create@IRoundedRectanglePath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@AEBU?$TRect@N@Math@@AEBU?$TVector2@N@6@@Z` at `0x18010ce1b`
- `gfx!?Create@IRoundedRectanglePath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@AEBU?$TRect@N@Math@@AEBU?$TVector2@N@6@@Z` at `0x18010ce1b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall Mso::SVG::RectRenderer::CalculatePath(__int64 a1, _QWORD *a2, __int64 a3)
{
  __int64 v5; // r12
  __m128d v6; // xmm7
  __m128d v7; // xmm6
  double v8; // xmm11_8
  double v9; // xmm12_8
  double v10; // xmm9_8
  double v11; // xmm0_8
  double v12; // xmm8_8
  double v13; // xmm1_8
  double v14; // xmm6_8
  int v15; // eax
  int v16; // eax
  const struct Mso::SVG::Length *v17; // rdx
  __int64 *v18; // rax
  __int64 v19; // rbx
  __m128d v21; // [rsp+40h] [rbp-91h] BYREF
  __int64 v22; // [rsp+50h] [rbp-81h]
  __m128d v23; // [rsp+58h] [rbp-79h] BYREF
  double v24; // [rsp+68h] [rbp-69h]
  double v25; // [rsp+70h] [rbp-61h]
  _QWORD v26[18]; // [rsp+78h] [rbp-59h] BYREF
  __int64 v27; // [rsp+138h] [rbp+67h] BYREF

  v5 = *(_QWORD *)(a1 + 16);
  if ( !v5 )
  {
    CrashWithRecovery(0x1E3C3843u, 0);
    JUMPOUT(0x18010CEC5LL);
  }
  _castguard_slow_path_check_user_handled(*(_QWORD *)v5, 4768, 0);
  v6 = *(__m128d *)(v5 + 472);
  v21 = v6;
  v22 = *(_QWORD *)(v5 + 488);
  v7 = *(__m128d *)(v5 + 496);
  v23 = v7;
  v24 = *(double *)(v5 + 512);
  v8 = Mso::SVG::LengthResolver::ResolveLength(
         *(Mso::SVG::LengthResolver **)(a3 + 16),
         (const struct Mso::SVG::Length *)(v5 + 408),
         (const struct Mso::SVG::StyleResolveChain *)a3);
  v9 = Mso::SVG::LengthResolver::ResolveLength(
         *(Mso::SVG::LengthResolver **)(a3 + 16),
         (const struct Mso::SVG::Length *)(v5 + 424),
         (const struct Mso::SVG::StyleResolveChain *)a3);
  v10 = Mso::SVG::LengthResolver::ResolveLength(
          *(Mso::SVG::LengthResolver **)(a3 + 16),
          (const struct Mso::SVG::Length *)(v5 + 440),
          (const struct Mso::SVG::StyleResolveChain *)a3);
  v11 = Mso::SVG::LengthResolver::ResolveLength(
          *(Mso::SVG::LengthResolver **)(a3 + 16),
          (const struct Mso::SVG::Length *)(v5 + 456),
          (const struct Mso::SVG::StyleResolveChain *)a3);
  v12 = v11;
  if ( v10 <= 0.0 || v11 <= 0.0 )
  {
    *a2 = 0;
    return a2;
  }
  if ( (_BYTE)v22 )
  {
    if ( !LOBYTE(v24) )
    {
      v14 = Mso::SVG::LengthResolver::ResolveLength(
              *(Mso::SVG::LengthResolver **)(a3 + 16),
              (const struct Mso::SVG::Length *)&v21,
              (const struct Mso::SVG::StyleResolveChain *)a3);
      v16 = _mm_cvtsi128_si32((__m128i)v6);
      if ( !v16 || v16 == 3 )
      {
        v21 = v6;
      }
      else
      {
        *(_QWORD *)&v21.m128d_f64[1] = *(_OWORD *)&_mm_unpackhi_pd(v6, v6);
        if ( v16 == 1 )
          LODWORD(v21.m128d_f64[0]) = 2;
        else
          LODWORD(v21.m128d_f64[0]) = 1;
      }
      v17 = (const struct Mso::SVG::Length *)&v21;
      goto LABEL_22;
    }
LABEL_21:
    v14 = Mso::SVG::LengthResolver::ResolveLength(
            *(Mso::SVG::LengthResolver **)(a3 + 16),
            (const struct Mso::SVG::Length *)&v21,
            (const struct Mso::SVG::StyleResolveChain *)a3);
    v17 = (const struct Mso::SVG::Length *)&v23;
LABEL_22:
    v13 = Mso::SVG::LengthResolver::ResolveLength(
            *(Mso::SVG::LengthResolver **)(a3 + 16),
            v17,
            (const struct Mso::SVG::StyleResolveChain *)a3);
    goto LABEL_23;
  }
  if ( LOBYTE(v24) )
  {
    v15 = _mm_cvtsi128_si32((__m128i)v7);
    if ( !v15 || v15 == 3 )
    {
      v21 = v7;
    }
    else
    {
      *(_QWORD *)&v21.m128d_f64[1] = *(_OWORD *)&_mm_unpackhi_pd(v7, v7);
      if ( v15 == 1 )
        LODWORD(v21.m128d_f64[0]) = 2;
      else
        LODWORD(v21.m128d_f64[0]) = 1;
    }
    goto LABEL_21;
  }
  v13 = 0.0;
  v14 = 0.0;
LABEL_23:
  if ( v14 + v14 > v10 )
    v14 = v10 * 0.5;
  if ( v13 + v13 > v12 )
    v13 = v12 * 0.5;
  v21.m128d_f64[0] = 0.0;
  if ( v14 == 0.0 && v13 == 0.0 )
  {
    v23.m128d_f64[0] = v8;
    v23.m128d_f64[1] = v9;
    v24 = v10 + v8;
    v25 = v12 + v9;
    v18 = (__int64 *)GEL::IRectanglePath::Create(&v27, &v23);
  }
  else
  {
    v23.m128d_f64[0] = v14;
    v23.m128d_f64[1] = v13;
    *(double *)v26 = v8;
    *(double *)&v26[1] = v9;
    *(double *)&v26[2] = v10 + v8;
    *(double *)&v26[3] = v12 + v9;
    v18 = (__int64 *)GEL::IRoundedRectanglePath::Create(&v27, v26, &v23);
  }
  v19 = *v18;
  *v18 = 0;
  if ( v27 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 8LL))(v27);
  if ( v19 )
    (**(void (__fastcall ***)(__int64))v19)(v19);
  *a2 = v19;
  if ( v19 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 8LL))(v19);
  return a2;
}

```

## disassembly

```asm
0x18010cb50  mov     rax, rsp
0x18010cb53  mov     [rax+10h], rbx
0x18010cb57  mov     [rax+18h], rsi
0x18010cb5b  push    rbp
0x18010cb5c  push    rdi
0x18010cb5d  push    r12
0x18010cb5f  push    r14
0x18010cb61  push    r15
0x18010cb63  lea     rbp, [rax-5Fh]
0x18010cb67  sub     rsp, 100h
0x18010cb6e  movaps  xmmword ptr [rax-38h], xmm6
0x18010cb72  movaps  xmmword ptr [rax-48h], xmm7
0x18010cb76  movaps  xmmword ptr [rax-58h], xmm8
0x18010cb7b  movaps  xmmword ptr [rax-68h], xmm9
0x18010cb80  movaps  xmmword ptr [rax-78h], xmm10
0x18010cb85  movaps  xmmword ptr [rax-88h], xmm11
0x18010cb8d  movaps  xmmword ptr [rax-98h], xmm12
0x18010cb95  mov     r14, r8
0x18010cb98  mov     r15, rdx
0x18010cb9b  mov     r12, [rcx+10h]
0x18010cb9f  test    r12, r12
0x18010cba2  jz      loc_18010CEB8
0x18010cba8  xor     r8d, r8d
0x18010cbab  mov     edx, 12A0h
0x18010cbb0  mov     rcx, [r12]
0x18010cbb4  call    __castguard_slow_path_check_user_handled
0x18010cbb9  lea     rdx, [r12+198h]; struct Mso::SVG::Length *
0x18010cbc1  movups  xmm7, xmmword ptr [r12+1D8h]
0x18010cbca  movups  [rsp+120h+var_F0+8], xmm7
0x18010cbcf  movsd   xmm0, qword ptr [r12+1E8h]
0x18010cbd9  movsd   [rsp+120h+var_D8], xmm0
0x18010cbdf  movups  xmm6, xmmword ptr [r12+1F0h]
0x18010cbe8  movups  [rbp+57h+var_D0], xmm6
0x18010cbec  movsd   xmm0, qword ptr [r12+200h]
0x18010cbf6  movsd   [rbp+57h+var_C0], xmm0
0x18010cbfb  mov     r8, r14; struct Mso::SVG::StyleResolveChain *
0x18010cbfe  mov     rcx, [r14+10h]; this
0x18010cc02  call    ?ResolveLength@LengthResolver@SVG@Mso@@AEBANAEBULength@23@AEBVStyleResolveChain@23@@Z; Mso::SVG::LengthResolver::ResolveLength(Mso::SVG::Length const &,Mso::SVG::StyleResolveChain const &)
0x18010cc07  movaps  xmm11, xmm0
0x18010cc0b  mov     r8, r14; struct Mso::SVG::StyleResolveChain *
0x18010cc0e  lea     rdx, [r12+1A8h]; struct Mso::SVG::Length *
0x18010cc16  mov     rcx, [r14+10h]; this
0x18010cc1a  call    ?ResolveLength@LengthResolver@SVG@Mso@@AEBANAEBULength@23@AEBVStyleResolveChain@23@@Z; Mso::SVG::LengthResolver::ResolveLength(Mso::SVG::Length const &,Mso::SVG::StyleResolveChain const &)
0x18010cc1f  movaps  xmm12, xmm0
0x18010cc23  mov     r8, r14; struct Mso::SVG::StyleResolveChain *
0x18010cc26  lea     rdx, [r12+1B8h]; struct Mso::SVG::Length *
0x18010cc2e  mov     rcx, [r14+10h]; this
0x18010cc32  call    ?ResolveLength@LengthResolver@SVG@Mso@@AEBANAEBULength@23@AEBVStyleResolveChain@23@@Z; Mso::SVG::LengthResolver::ResolveLength(Mso::SVG::Length const &,Mso::SVG::StyleResolveChain const &)
0x18010cc37  movaps  xmm9, xmm0
0x18010cc3b  mov     r8, r14; struct Mso::SVG::StyleResolveChain *
0x18010cc3e  lea     rdx, [r12+1C8h]; struct Mso::SVG::Length *
0x18010cc46  mov     rcx, [r14+10h]; this
0x18010cc4a  call    ?ResolveLength@LengthResolver@SVG@Mso@@AEBANAEBULength@23@AEBVStyleResolveChain@23@@Z; Mso::SVG::LengthResolver::ResolveLength(Mso::SVG::Length const &,Mso::SVG::StyleResolveChain const &)
0x18010cc4f  movaps  xmm8, xmm0
0x18010cc53  xorps   xmm10, xmm10
0x18010cc57  comisd  xmm10, xmm9
0x18010cc5c  jnb     loc_18010CE6F
0x18010cc62  comisd  xmm10, xmm0
0x18010cc67  jnb     loc_18010CE6F
0x18010cc6d  mov     al, byte ptr [rsp+120h+var_D8]
0x18010cc71  test    al, al
0x18010cc73  jnz     short loc_18010CCC2
0x18010cc75  cmp     byte ptr [rbp+57h+var_C0], al
0x18010cc78  jnz     short loc_18010CC85
0x18010cc7a  xorps   xmm1, xmm1
0x18010cc7d  xorps   xmm6, xmm6
0x18010cc80  jmp     loc_18010CD62
0x18010cc85  movd    eax, xmm6
0x18010cc89  test    eax, eax
0x18010cc8b  jz      short loc_18010CCB5
0x18010cc8d  cmp     eax, 3
0x18010cc90  jz      short loc_18010CCB5
0x18010cc92  unpckhpd xmm6, xmm6
0x18010cc96  movsd   [rsp+120h+var_E0], xmm6
0x18010cc9c  cmp     eax, 1
0x18010cc9f  jnz     short loc_18010CCAB
0x18010cca1  mov     dword ptr [rsp+120h+var_F0+8], 2
0x18010cca9  jmp     short loc_18010CCBB
0x18010ccab  mov     dword ptr [rsp+120h+var_F0+8], 1
0x18010ccb3  jmp     short loc_18010CCBB
0x18010ccb5  movdqu  [rsp+120h+var_F0+8], xmm6
0x18010ccbb  lea     rdx, [rsp+120h+var_F0+8]
0x18010ccc0  jmp     short loc_18010CD40
0x18010ccc2  cmp     byte ptr [rbp+57h+var_C0], 0
0x18010ccc6  jnz     short loc_18010CD1D
0x18010ccc8  test    al, al
0x18010ccca  jz      short loc_18010CD21
0x18010cccc  mov     r8, r14; struct Mso::SVG::StyleResolveChain *
0x18010cccf  lea     rdx, [rsp+120h+var_F0+8]; struct Mso::SVG::Length *
0x18010ccd4  mov     rcx, [r14+10h]; this
0x18010ccd8  call    ?ResolveLength@LengthResolver@SVG@Mso@@AEBANAEBULength@23@AEBVStyleResolveChain@23@@Z; Mso::SVG::LengthResolver::ResolveLength(Mso::SVG::Length const &,Mso::SVG::StyleResolveChain const &)
0x18010ccdd  movaps  xmm6, xmm0
0x18010cce0  movd    eax, xmm7
0x18010cce4  test    eax, eax
0x18010cce6  jz      short loc_18010CD10
0x18010cce8  cmp     eax, 3
0x18010cceb  jz      short loc_18010CD10
0x18010cced  unpckhpd xmm7, xmm7
0x18010ccf1  movsd   [rsp+120h+var_E0], xmm7
0x18010ccf7  cmp     eax, 1
0x18010ccfa  jnz     short loc_18010CD06
0x18010ccfc  mov     dword ptr [rsp+120h+var_F0+8], 2
0x18010cd04  jmp     short loc_18010CD16
0x18010cd06  mov     dword ptr [rsp+120h+var_F0+8], 1
0x18010cd0e  jmp     short loc_18010CD16
0x18010cd10  movdqu  [rsp+120h+var_F0+8], xmm7
0x18010cd16  lea     rdx, [rsp+120h+var_F0+8]
0x18010cd1b  jmp     short loc_18010CD53
0x18010cd1d  test    al, al
0x18010cd1f  jnz     short loc_18010CD3B
0x18010cd21  mov     [rsp+120h+Reserved], 0; Reserved
0x18010cd2a  xor     r9d, r9d; LineNo
0x18010cd2d  xor     r8d, r8d; FileName
0x18010cd30  xor     edx, edx; FunctionName
0x18010cd32  xor     ecx, ecx; Expression
0x18010cd34  call    cs:__imp__invoke_watson
0x18010cd3b  lea     rdx, [rsp+120h+var_F0+8]; struct Mso::SVG::Length *
0x18010cd40  mov     r8, r14; struct Mso::SVG::StyleResolveChain *
0x18010cd43  mov     rcx, [r14+10h]; this
0x18010cd47  call    ?ResolveLength@LengthResolver@SVG@Mso@@AEBANAEBULength@23@AEBVStyleResolveChain@23@@Z; Mso::SVG::LengthResolver::ResolveLength(Mso::SVG::Length const &,Mso::SVG::StyleResolveChain const &)
0x18010cd4c  movaps  xmm6, xmm0
0x18010cd4f  lea     rdx, [rbp+57h+var_D0]; struct Mso::SVG::Length *
0x18010cd53  mov     r8, r14; struct Mso::SVG::StyleResolveChain *
0x18010cd56  mov     rcx, [r14+10h]; this
0x18010cd5a  call    ?ResolveLength@LengthResolver@SVG@Mso@@AEBANAEBULength@23@AEBVStyleResolveChain@23@@Z; Mso::SVG::LengthResolver::ResolveLength(Mso::SVG::Length const &,Mso::SVG::StyleResolveChain const &)
0x18010cd5f  movaps  xmm1, xmm0
0x18010cd62  movaps  xmm0, xmm6
0x18010cd65  addsd   xmm0, xmm6
0x18010cd69  movsd   xmm2, cs:__real@3fe0000000000000
0x18010cd71  comisd  xmm0, xmm9
0x18010cd76  jbe     short loc_18010CD80
0x18010cd78  movaps  xmm6, xmm9
0x18010cd7c  mulsd   xmm6, xmm2
0x18010cd80  movaps  xmm0, xmm1
0x18010cd83  addsd   xmm0, xmm1
0x18010cd87  comisd  xmm0, xmm8
0x18010cd8c  jbe     short loc_18010CD96
0x18010cd8e  movaps  xmm1, xmm8
0x18010cd92  mulsd   xmm1, xmm2
0x18010cd96  mov     qword ptr [rsp+120h+var_F0+8], 0
0x18010cd9f  ucomisd xmm6, xmm10
0x18010cda4  jp      short loc_18010CDE3
0x18010cda6  jnz     short loc_18010CDE3
0x18010cda8  ucomisd xmm1, xmm10
0x18010cdad  jp      short loc_18010CDE3
0x18010cdaf  jnz     short loc_18010CDE3
0x18010cdb1  movsd   qword ptr [rbp+57h+var_D0], xmm11
0x18010cdb7  movsd   qword ptr [rbp+57h+var_D0+8], xmm12
0x18010cdbd  addsd   xmm9, xmm11
0x18010cdc2  movsd   [rbp+57h+var_C0], xmm9
0x18010cdc8  addsd   xmm8, xmm12
0x18010cdcd  movsd   [rbp+57h+var_B8], xmm8
0x18010cdd3  lea     rdx, [rbp+57h+var_D0]
0x18010cdd7  lea     rcx, [rbp+57h+arg_0]
0x18010cddb  call    cs:__imp_?Create@IRectanglePath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@AEBU?$TRect@N@Math@@@Z; GEL::IRectanglePath::Create(Math::TRect<double> const &)
0x18010cde1  jmp     short loc_18010CE21
0x18010cde3  movsd   qword ptr [rbp+57h+var_D0], xmm6
0x18010cde8  movsd   qword ptr [rbp+57h+var_D0+8], xmm1
0x18010cded  movsd   [rbp+57h+var_B0], xmm11
0x18010cdf3  movsd   [rbp+57h+var_A8], xmm12
0x18010cdf9  addsd   xmm9, xmm11
0x18010cdfe  movsd   [rbp+57h+var_A0], xmm9
0x18010ce04  addsd   xmm8, xmm12
0x18010ce09  movsd   [rbp+57h+var_98], xmm8
0x18010ce0f  lea     r8, [rbp+57h+var_D0]
0x18010ce13  lea     rdx, [rbp+57h+var_B0]
0x18010ce17  lea     rcx, [rbp+57h+arg_0]
0x18010ce1b  call    cs:__imp_?Create@IRoundedRectanglePath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@AEBU?$TRect@N@Math@@AEBU?$TVector2@N@6@@Z; GEL::IRoundedRectanglePath::Create(Math::TRect<double> const &,Math::TVector2<double> const &)
0x18010ce21  mov     rbx, [rax]
0x18010ce24  mov     qword ptr [rax], 0
0x18010ce2b  mov     rcx, [rbp+57h+arg_0]
0x18010ce2f  test    rcx, rcx
0x18010ce32  jz      short loc_18010CE41
0x18010ce34  mov     rax, [rcx]
0x18010ce37  mov     rax, [rax+8]
0x18010ce3b  call    cs:__guard_dispatch_icall_fptr
0x18010ce41  test    rbx, rbx
0x18010ce44  jz      short loc_18010CE55
0x18010ce46  mov     rax, [rbx]
0x18010ce49  mov     rcx, rbx
0x18010ce4c  mov     rax, [rax]
0x18010ce4f  call    cs:__guard_dispatch_icall_fptr
0x18010ce55  mov     [r15], rbx
0x18010ce58  test    rbx, rbx
0x18010ce5b  jz      short loc_18010CE76
0x18010ce5d  mov     rax, [rbx]
0x18010ce60  mov     rcx, rbx
0x18010ce63  mov     rax, [rax+8]
0x18010ce67  call    cs:__guard_dispatch_icall_fptr
0x18010ce6d  jmp     short loc_18010CE76
0x18010ce6f  mov     qword ptr [r15], 0
0x18010ce76  mov     rax, r15
0x18010ce79  lea     r11, [rsp+120h+var_20]
0x18010ce81  mov     rbx, [r11+38h]
0x18010ce85  mov     rsi, [r11+40h]
0x18010ce89  movaps  xmm6, xmmword ptr [r11-10h]
0x18010ce8e  movaps  xmm7, xmmword ptr [r11-20h]
0x18010ce93  movaps  xmm8, xmmword ptr [r11-30h]
0x18010ce98  movaps  xmm9, xmmword ptr [r11-40h]
0x18010ce9d  movaps  xmm10, xmmword ptr [r11-50h]
0x18010cea2  movaps  xmm11, xmmword ptr [r11-60h]
0x18010cea7  movaps  xmm12, xmmword ptr [r11-70h]
0x18010ceac  mov     rsp, r11
0x18010ceaf  pop     r15
0x18010ceb1  pop     r14
0x18010ceb3  pop     r12
0x18010ceb5  pop     rdi
0x18010ceb6  pop     rbp
0x18010ceb7  retn
0x18010ceb8  xor     edx, edx
0x18010ceba  mov     ecx, 1E3C3843h
0x18010cebf  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
```
