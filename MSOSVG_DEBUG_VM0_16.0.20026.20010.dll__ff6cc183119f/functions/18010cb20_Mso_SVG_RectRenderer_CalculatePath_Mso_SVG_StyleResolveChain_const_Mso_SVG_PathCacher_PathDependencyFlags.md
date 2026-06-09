# Mso::SVG::RectRenderer::CalculatePath(Mso::SVG::StyleResolveChain const &,Mso::SVG::PathCacher::PathDependencyFlags &)

- ea: `0x18010cb20`
- end: `0x18010ce96`
- name: `?CalculatePath@RectRenderer@SVG@Mso@@UEAA?AV?$TCntPtr@$$CBUIPath@GEL@@@3@AEBVStyleResolveChain@23@AEAW4PathDependencyFlags@PathCacher@23@@Z`
- size: `886`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18010cb20`
- `0x1801395a4`
- `0x18013e010`
- `0x18013f760`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18010ce8f`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18010ce8f`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18010cd04`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18010cd04`
- `gfx!?Create@IRectanglePath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@AEBU?$TRect@N@Math@@@Z` at `0x18010cdab`
- `gfx!?Create@IRectanglePath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@AEBU?$TRect@N@Math@@@Z` at `0x18010cdab`
- `gfx!?Create@IRoundedRectanglePath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@AEBU?$TRect@N@Math@@AEBU?$TVector2@N@6@@Z` at `0x18010cdeb`
- `gfx!?Create@IRoundedRectanglePath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@AEBU?$TRect@N@Math@@AEBU?$TVector2@N@6@@Z` at `0x18010cdeb`

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
    JUMPOUT(0x18010CE95LL);
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
0x18010cb20  mov     rax, rsp
0x18010cb23  mov     [rax+10h], rbx
0x18010cb27  mov     [rax+18h], rsi
0x18010cb2b  push    rbp
0x18010cb2c  push    rdi
0x18010cb2d  push    r12
0x18010cb2f  push    r14
0x18010cb31  push    r15
0x18010cb33  lea     rbp, [rax-5Fh]
0x18010cb37  sub     rsp, 100h
0x18010cb3e  movaps  xmmword ptr [rax-38h], xmm6
0x18010cb42  movaps  xmmword ptr [rax-48h], xmm7
0x18010cb46  movaps  xmmword ptr [rax-58h], xmm8
0x18010cb4b  movaps  xmmword ptr [rax-68h], xmm9
0x18010cb50  movaps  xmmword ptr [rax-78h], xmm10
0x18010cb55  movaps  xmmword ptr [rax-88h], xmm11
0x18010cb5d  movaps  xmmword ptr [rax-98h], xmm12
0x18010cb65  mov     r14, r8
0x18010cb68  mov     r15, rdx
0x18010cb6b  mov     r12, [rcx+10h]
0x18010cb6f  test    r12, r12
0x18010cb72  jz      loc_18010CE88
0x18010cb78  xor     r8d, r8d
0x18010cb7b  mov     edx, 12A0h
0x18010cb80  mov     rcx, [r12]
0x18010cb84  call    __castguard_slow_path_check_user_handled
0x18010cb89  lea     rdx, [r12+198h]; struct Mso::SVG::Length *
0x18010cb91  movups  xmm7, xmmword ptr [r12+1D8h]
0x18010cb9a  movups  [rsp+120h+var_F0+8], xmm7
0x18010cb9f  movsd   xmm0, qword ptr [r12+1E8h]
0x18010cba9  movsd   [rsp+120h+var_D8], xmm0
0x18010cbaf  movups  xmm6, xmmword ptr [r12+1F0h]
0x18010cbb8  movups  [rbp+57h+var_D0], xmm6
0x18010cbbc  movsd   xmm0, qword ptr [r12+200h]
0x18010cbc6  movsd   [rbp+57h+var_C0], xmm0
0x18010cbcb  mov     r8, r14; struct Mso::SVG::StyleResolveChain *
0x18010cbce  mov     rcx, [r14+10h]; this
0x18010cbd2  call    ?ResolveLength@LengthResolver@SVG@Mso@@AEBANAEBULength@23@AEBVStyleResolveChain@23@@Z; Mso::SVG::LengthResolver::ResolveLength(Mso::SVG::Length const &,Mso::SVG::StyleResolveChain const &)
0x18010cbd7  movaps  xmm11, xmm0
0x18010cbdb  mov     r8, r14; struct Mso::SVG::StyleResolveChain *
0x18010cbde  lea     rdx, [r12+1A8h]; struct Mso::SVG::Length *
0x18010cbe6  mov     rcx, [r14+10h]; this
0x18010cbea  call    ?ResolveLength@LengthResolver@SVG@Mso@@AEBANAEBULength@23@AEBVStyleResolveChain@23@@Z; Mso::SVG::LengthResolver::ResolveLength(Mso::SVG::Length const &,Mso::SVG::StyleResolveChain const &)
0x18010cbef  movaps  xmm12, xmm0
0x18010cbf3  mov     r8, r14; struct Mso::SVG::StyleResolveChain *
0x18010cbf6  lea     rdx, [r12+1B8h]; struct Mso::SVG::Length *
0x18010cbfe  mov     rcx, [r14+10h]; this
0x18010cc02  call    ?ResolveLength@LengthResolver@SVG@Mso@@AEBANAEBULength@23@AEBVStyleResolveChain@23@@Z; Mso::SVG::LengthResolver::ResolveLength(Mso::SVG::Length const &,Mso::SVG::StyleResolveChain const &)
0x18010cc07  movaps  xmm9, xmm0
0x18010cc0b  mov     r8, r14; struct Mso::SVG::StyleResolveChain *
0x18010cc0e  lea     rdx, [r12+1C8h]; struct Mso::SVG::Length *
0x18010cc16  mov     rcx, [r14+10h]; this
0x18010cc1a  call    ?ResolveLength@LengthResolver@SVG@Mso@@AEBANAEBULength@23@AEBVStyleResolveChain@23@@Z; Mso::SVG::LengthResolver::ResolveLength(Mso::SVG::Length const &,Mso::SVG::StyleResolveChain const &)
0x18010cc1f  movaps  xmm8, xmm0
0x18010cc23  xorps   xmm10, xmm10
0x18010cc27  comisd  xmm10, xmm9
0x18010cc2c  jnb     loc_18010CE3F
0x18010cc32  comisd  xmm10, xmm0
0x18010cc37  jnb     loc_18010CE3F
0x18010cc3d  mov     al, byte ptr [rsp+120h+var_D8]
0x18010cc41  test    al, al
0x18010cc43  jnz     short loc_18010CC92
0x18010cc45  cmp     byte ptr [rbp+57h+var_C0], al
0x18010cc48  jnz     short loc_18010CC55
0x18010cc4a  xorps   xmm1, xmm1
0x18010cc4d  xorps   xmm6, xmm6
0x18010cc50  jmp     loc_18010CD32
0x18010cc55  movd    eax, xmm6
0x18010cc59  test    eax, eax
0x18010cc5b  jz      short loc_18010CC85
0x18010cc5d  cmp     eax, 3
0x18010cc60  jz      short loc_18010CC85
0x18010cc62  unpckhpd xmm6, xmm6
0x18010cc66  movsd   [rsp+120h+var_E0], xmm6
0x18010cc6c  cmp     eax, 1
0x18010cc6f  jnz     short loc_18010CC7B
0x18010cc71  mov     dword ptr [rsp+120h+var_F0+8], 2
0x18010cc79  jmp     short loc_18010CC8B
0x18010cc7b  mov     dword ptr [rsp+120h+var_F0+8], 1
0x18010cc83  jmp     short loc_18010CC8B
0x18010cc85  movdqu  [rsp+120h+var_F0+8], xmm6
0x18010cc8b  lea     rdx, [rsp+120h+var_F0+8]
0x18010cc90  jmp     short loc_18010CD10
0x18010cc92  cmp     byte ptr [rbp+57h+var_C0], 0
0x18010cc96  jnz     short loc_18010CCED
0x18010cc98  test    al, al
0x18010cc9a  jz      short loc_18010CCF1
0x18010cc9c  mov     r8, r14; struct Mso::SVG::StyleResolveChain *
0x18010cc9f  lea     rdx, [rsp+120h+var_F0+8]; struct Mso::SVG::Length *
0x18010cca4  mov     rcx, [r14+10h]; this
0x18010cca8  call    ?ResolveLength@LengthResolver@SVG@Mso@@AEBANAEBULength@23@AEBVStyleResolveChain@23@@Z; Mso::SVG::LengthResolver::ResolveLength(Mso::SVG::Length const &,Mso::SVG::StyleResolveChain const &)
0x18010ccad  movaps  xmm6, xmm0
0x18010ccb0  movd    eax, xmm7
0x18010ccb4  test    eax, eax
0x18010ccb6  jz      short loc_18010CCE0
0x18010ccb8  cmp     eax, 3
0x18010ccbb  jz      short loc_18010CCE0
0x18010ccbd  unpckhpd xmm7, xmm7
0x18010ccc1  movsd   [rsp+120h+var_E0], xmm7
0x18010ccc7  cmp     eax, 1
0x18010ccca  jnz     short loc_18010CCD6
0x18010cccc  mov     dword ptr [rsp+120h+var_F0+8], 2
0x18010ccd4  jmp     short loc_18010CCE6
0x18010ccd6  mov     dword ptr [rsp+120h+var_F0+8], 1
0x18010ccde  jmp     short loc_18010CCE6
0x18010cce0  movdqu  [rsp+120h+var_F0+8], xmm7
0x18010cce6  lea     rdx, [rsp+120h+var_F0+8]
0x18010cceb  jmp     short loc_18010CD23
0x18010cced  test    al, al
0x18010ccef  jnz     short loc_18010CD0B
0x18010ccf1  mov     [rsp+120h+Reserved], 0; Reserved
0x18010ccfa  xor     r9d, r9d; LineNo
0x18010ccfd  xor     r8d, r8d; FileName
0x18010cd00  xor     edx, edx; FunctionName
0x18010cd02  xor     ecx, ecx; Expression
0x18010cd04  call    cs:__imp__invoke_watson
0x18010cd0b  lea     rdx, [rsp+120h+var_F0+8]; struct Mso::SVG::Length *
0x18010cd10  mov     r8, r14; struct Mso::SVG::StyleResolveChain *
0x18010cd13  mov     rcx, [r14+10h]; this
0x18010cd17  call    ?ResolveLength@LengthResolver@SVG@Mso@@AEBANAEBULength@23@AEBVStyleResolveChain@23@@Z; Mso::SVG::LengthResolver::ResolveLength(Mso::SVG::Length const &,Mso::SVG::StyleResolveChain const &)
0x18010cd1c  movaps  xmm6, xmm0
0x18010cd1f  lea     rdx, [rbp+57h+var_D0]; struct Mso::SVG::Length *
0x18010cd23  mov     r8, r14; struct Mso::SVG::StyleResolveChain *
0x18010cd26  mov     rcx, [r14+10h]; this
0x18010cd2a  call    ?ResolveLength@LengthResolver@SVG@Mso@@AEBANAEBULength@23@AEBVStyleResolveChain@23@@Z; Mso::SVG::LengthResolver::ResolveLength(Mso::SVG::Length const &,Mso::SVG::StyleResolveChain const &)
0x18010cd2f  movaps  xmm1, xmm0
0x18010cd32  movaps  xmm0, xmm6
0x18010cd35  addsd   xmm0, xmm6
0x18010cd39  movsd   xmm2, cs:__real@3fe0000000000000
0x18010cd41  comisd  xmm0, xmm9
0x18010cd46  jbe     short loc_18010CD50
0x18010cd48  movaps  xmm6, xmm9
0x18010cd4c  mulsd   xmm6, xmm2
0x18010cd50  movaps  xmm0, xmm1
0x18010cd53  addsd   xmm0, xmm1
0x18010cd57  comisd  xmm0, xmm8
0x18010cd5c  jbe     short loc_18010CD66
0x18010cd5e  movaps  xmm1, xmm8
0x18010cd62  mulsd   xmm1, xmm2
0x18010cd66  mov     qword ptr [rsp+120h+var_F0+8], 0
0x18010cd6f  ucomisd xmm6, xmm10
0x18010cd74  jp      short loc_18010CDB3
0x18010cd76  jnz     short loc_18010CDB3
0x18010cd78  ucomisd xmm1, xmm10
0x18010cd7d  jp      short loc_18010CDB3
0x18010cd7f  jnz     short loc_18010CDB3
0x18010cd81  movsd   qword ptr [rbp+57h+var_D0], xmm11
0x18010cd87  movsd   qword ptr [rbp+57h+var_D0+8], xmm12
0x18010cd8d  addsd   xmm9, xmm11
0x18010cd92  movsd   [rbp+57h+var_C0], xmm9
0x18010cd98  addsd   xmm8, xmm12
0x18010cd9d  movsd   [rbp+57h+var_B8], xmm8
0x18010cda3  lea     rdx, [rbp+57h+var_D0]
0x18010cda7  lea     rcx, [rbp+57h+arg_0]
0x18010cdab  call    cs:__imp_?Create@IRectanglePath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@AEBU?$TRect@N@Math@@@Z; GEL::IRectanglePath::Create(Math::TRect<double> const &)
0x18010cdb1  jmp     short loc_18010CDF1
0x18010cdb3  movsd   qword ptr [rbp+57h+var_D0], xmm6
0x18010cdb8  movsd   qword ptr [rbp+57h+var_D0+8], xmm1
0x18010cdbd  movsd   [rbp+57h+var_B0], xmm11
0x18010cdc3  movsd   [rbp+57h+var_A8], xmm12
0x18010cdc9  addsd   xmm9, xmm11
0x18010cdce  movsd   [rbp+57h+var_A0], xmm9
0x18010cdd4  addsd   xmm8, xmm12
0x18010cdd9  movsd   [rbp+57h+var_98], xmm8
0x18010cddf  lea     r8, [rbp+57h+var_D0]
0x18010cde3  lea     rdx, [rbp+57h+var_B0]
0x18010cde7  lea     rcx, [rbp+57h+arg_0]
0x18010cdeb  call    cs:__imp_?Create@IRoundedRectanglePath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@AEBU?$TRect@N@Math@@AEBU?$TVector2@N@6@@Z; GEL::IRoundedRectanglePath::Create(Math::TRect<double> const &,Math::TVector2<double> const &)
0x18010cdf1  mov     rbx, [rax]
0x18010cdf4  mov     qword ptr [rax], 0
0x18010cdfb  mov     rcx, [rbp+57h+arg_0]
0x18010cdff  test    rcx, rcx
0x18010ce02  jz      short loc_18010CE11
0x18010ce04  mov     rax, [rcx]
0x18010ce07  mov     rax, [rax+8]
0x18010ce0b  call    cs:__guard_dispatch_icall_fptr
0x18010ce11  test    rbx, rbx
0x18010ce14  jz      short loc_18010CE25
0x18010ce16  mov     rax, [rbx]
0x18010ce19  mov     rcx, rbx
0x18010ce1c  mov     rax, [rax]
0x18010ce1f  call    cs:__guard_dispatch_icall_fptr
0x18010ce25  mov     [r15], rbx
0x18010ce28  test    rbx, rbx
0x18010ce2b  jz      short loc_18010CE46
0x18010ce2d  mov     rax, [rbx]
0x18010ce30  mov     rcx, rbx
0x18010ce33  mov     rax, [rax+8]
0x18010ce37  call    cs:__guard_dispatch_icall_fptr
0x18010ce3d  jmp     short loc_18010CE46
0x18010ce3f  mov     qword ptr [r15], 0
0x18010ce46  mov     rax, r15
0x18010ce49  lea     r11, [rsp+120h+var_20]
0x18010ce51  mov     rbx, [r11+38h]
0x18010ce55  mov     rsi, [r11+40h]
0x18010ce59  movaps  xmm6, xmmword ptr [r11-10h]
0x18010ce5e  movaps  xmm7, xmmword ptr [r11-20h]
0x18010ce63  movaps  xmm8, xmmword ptr [r11-30h]
0x18010ce68  movaps  xmm9, xmmword ptr [r11-40h]
0x18010ce6d  movaps  xmm10, xmmword ptr [r11-50h]
0x18010ce72  movaps  xmm11, xmmword ptr [r11-60h]
0x18010ce77  movaps  xmm12, xmmword ptr [r11-70h]
0x18010ce7c  mov     rsp, r11
0x18010ce7f  pop     r15
0x18010ce81  pop     r14
0x18010ce83  pop     r12
0x18010ce85  pop     rdi
0x18010ce86  pop     rbp
0x18010ce87  retn
0x18010ce88  xor     edx, edx
0x18010ce8a  mov     ecx, 1E3C3843h
0x18010ce8f  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
```
