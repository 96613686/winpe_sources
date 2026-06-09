# Mso::SVG::FeDiffuseLightingRenderer::ApplyUnaryFilter(GEL::IEffect const &,Mso::SVG::StyleResolveChain const &,GEL::Rect const &,Mso::SVG::PrimitiveUnitResolver const &,GEL::IColorResolver const *)

- ea: `0x1800fb820`
- end: `0x1800fba34`
- name: `?ApplyUnaryFilter@FeDiffuseLightingRenderer@SVG@Mso@@UEBA?AV?$TCntPtr@$$CBUIEffect@GEL@@@Ofc@@AEBUIEffect@GEL@@AEBVStyleResolveChain@23@AEBURect@7@AEBVPrimitiveUnitResolver@23@PEBUIColorResolver@7@@Z`
- size: `532`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800fb820`
- `0x1800fbda0`
- `0x1800fbee0`
- `0x18013e010`
- `0x18013f760`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800fba1f`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800fba2d`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800fba1f`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800fba2d`
- `gfx!?Create@IEffectBumpMapDiffuse@GEL@@SA?AV?$TCntPtr@UIEffectBumpMapDiffuse@GEL@@@Ofc@@AEBUIEffect@2@NAEBUILightSource@2@W4ColorSpace@2@NPEBU?$TVector2@N@Math@@@Z` at `0x1800fb9b2`
- `gfx!?Create@IEffectBumpMapDiffuse@GEL@@SA?AV?$TCntPtr@UIEffectBumpMapDiffuse@GEL@@@Ofc@@AEBUIEffect@2@NAEBUILightSource@2@W4ColorSpace@2@NPEBU?$TVector2@N@Math@@@Z` at `0x1800fb9b2`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall Mso::SVG::FeDiffuseLightingRenderer::ApplyUnaryFilter(
        __int64 a1,
        _QWORD *a2,
        __int64 a3,
        _QWORD *a4,
        int a5,
        __int64 a6)
{
  _QWORD *v9; // rbx
  __int64 v10; // rdi
  double v11; // xmm2_8
  double v12; // xmm0_8
  __int128 *v13; // r15
  __int64 v14; // xmm6_8
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int16 *v17; // rcx
  __int64 v18; // rax
  char v19; // r12
  __int64 v20; // rcx
  _QWORD *v21; // rax
  __int64 v22; // r8
  __int64 *v23; // rax
  __int64 v24; // rcx
  __int64 v26; // [rsp+48h] [rbp-28h] BYREF
  __int128 v27; // [rsp+50h] [rbp-20h] BYREF
  __int64 v28; // [rsp+A0h] [rbp+30h] BYREF

  v9 = *(_QWORD **)(a1 + 16);
  if ( !v9 )
  {
LABEL_24:
    CrashWithRecovery(0x1E3C3843u, 0);
    JUMPOUT(0x1800FBA33LL);
  }
  _castguard_slow_path_check_user_handled(*v9, 9176, 2760);
  _castguard_slow_path_check_user_handled(*v9, 11752, 184);
  _castguard_slow_path_check_user_handled(*v9, 11752, 0);
  v27 = *((_OWORD *)v9 + 31);
  v10 = a6;
  v11 = *(double *)&v27;
  if ( *(_DWORD *)(a6 + 32) == 1 )
  {
    v11 = *(double *)&v27 * (*(double *)(a6 + 16) - *(double *)a6);
    *(double *)&v27 = v11;
    v12 = *((double *)&v27 + 1) * (*(double *)(a6 + 24) - *(double *)(a6 + 8));
    *((double *)&v27 + 1) = v12;
  }
  else
  {
    v12 = *((double *)&v27 + 1);
  }
  if ( v11 <= 0.0 || (v13 = &v27, v12 <= 0.0) )
    v13 = 0;
  v14 = v9[65];
  v15 = a4[1];
  v16 = *(_QWORD *)(v15 + 16);
  if ( v16 )
  {
    v17 = (__int16 *)(v16 + 1320);
  }
  else
  {
    v17 = &Mso::SVG::StyleMetaData<1>::initial;
    if ( *(_QWORD *)(v15 + 8) )
      v17 = (__int16 *)&Mso::SVG::StyleMetaData<1>::inherit;
  }
  if ( !*((_BYTE *)v17 + 1) )
  {
    if ( *a4 )
      v18 = Mso::SVG::StyleResolveChain::Get<1>();
    else
      v18 = Mso::SVG::StyleResolveChain::GetNormal<1>(a4, *(_QWORD *)(v15 + 8));
    v17 = (__int16 *)v18;
  }
  v19 = *(_BYTE *)v17;
  v20 = v9[61];
  if ( !v20 )
  {
    CrashWithRecovery(0x21D758Bu, 0);
    goto LABEL_24;
  }
  v21 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, __int64 *, _QWORD *, __int64))(*(_QWORD *)v20 + 176LL))(
                    v20,
                    &v26,
                    a4,
                    v10);
  v23 = (__int64 *)GEL::IEffectBumpMapDiffuse::Create(&v28, a3, v22, *v21, v19, v14, v13);
  v24 = *v23;
  *v23 = 0;
  *a2 = v24;
  if ( v28 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 8LL))(v28);
  if ( v26 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 8LL))(v26);
  return a2;
}

```

## disassembly

```asm
0x1800fb820  mov     rax, rsp
0x1800fb823  mov     [rax+10h], rbx
0x1800fb827  mov     [rax+18h], rsi
0x1800fb82b  mov     [rax+20h], rdi
0x1800fb82f  push    rbp
0x1800fb830  push    r12
0x1800fb832  push    r13
0x1800fb834  push    r14
0x1800fb836  push    r15
0x1800fb838  mov     rbp, rsp
0x1800fb83b  sub     rsp, 70h
0x1800fb83f  movaps  xmmword ptr [rax-38h], xmm6
0x1800fb843  mov     rsi, r9
0x1800fb846  mov     r13, r8
0x1800fb849  mov     r14, rdx
0x1800fb84c  xor     r12d, r12d
0x1800fb84f  mov     rbx, [rcx+10h]
0x1800fb853  test    rbx, rbx
0x1800fb856  jz      loc_1800FBA26
0x1800fb85c  mov     edx, 23D8h
0x1800fb861  mov     r8d, 0AC8h
0x1800fb867  mov     rcx, [rbx]
0x1800fb86a  call    __castguard_slow_path_check_user_handled
0x1800fb86f  mov     edi, 2DE8h
0x1800fb874  test    rbx, rbx
0x1800fb877  jz      short loc_1800FB88B
0x1800fb879  mov     r8d, 0B8h
0x1800fb87f  mov     edx, edi
0x1800fb881  mov     rcx, [rbx]
0x1800fb884  call    __castguard_slow_path_check_user_handled
0x1800fb889  jmp     short loc_1800FB88E
0x1800fb88b  mov     rbx, r12
0x1800fb88e  test    rbx, rbx
0x1800fb891  jz      short loc_1800FB8A3
0x1800fb893  xor     r8d, r8d
0x1800fb896  mov     rdx, rdi
0x1800fb899  mov     rcx, [rbx]
0x1800fb89c  call    __castguard_slow_path_check_user_handled
0x1800fb8a1  jmp     short loc_1800FB8A6
0x1800fb8a3  mov     rbx, r12
0x1800fb8a6  movups  xmm0, xmmword ptr [rbx+1F0h]
0x1800fb8ad  movdqu  [rbp+var_20], xmm0
0x1800fb8b2  mov     rdi, [rbp+arg_28]
0x1800fb8b6  movsd   xmm2, qword ptr [rbp+var_20]
0x1800fb8bb  cmp     dword ptr [rdi+20h], 1
0x1800fb8bf  jnz     short loc_1800FB8ED
0x1800fb8c1  movsd   xmm0, qword ptr [rdi+10h]
0x1800fb8c6  subsd   xmm0, qword ptr [rdi]
0x1800fb8ca  mulsd   xmm2, xmm0
0x1800fb8ce  movsd   qword ptr [rbp+var_20], xmm2
0x1800fb8d3  movsd   xmm1, qword ptr [rdi+18h]
0x1800fb8d8  subsd   xmm1, qword ptr [rdi+8]
0x1800fb8dd  movsd   xmm0, qword ptr [rbp+var_20+8]
0x1800fb8e2  mulsd   xmm0, xmm1
0x1800fb8e6  movsd   qword ptr [rbp+var_20+8], xmm0
0x1800fb8eb  jmp     short loc_1800FB8F2
0x1800fb8ed  movsd   xmm0, qword ptr [rbp+var_20+8]
0x1800fb8f2  xorps   xmm1, xmm1
0x1800fb8f5  comisd  xmm2, xmm1
0x1800fb8f9  jbe     short loc_1800FB905
0x1800fb8fb  comisd  xmm0, xmm1
0x1800fb8ff  lea     r15, [rbp+var_20]
0x1800fb903  ja      short loc_1800FB908
0x1800fb905  mov     r15, r12
0x1800fb908  movsd   xmm6, qword ptr [rbx+208h]
0x1800fb910  mov     rdx, [rsi+8]
0x1800fb914  mov     rcx, [rdx+10h]
0x1800fb918  test    rcx, rcx
0x1800fb91b  jz      short loc_1800FB926
0x1800fb91d  add     rcx, 528h
0x1800fb924  jmp     short loc_1800FB93A
0x1800fb926  cmp     [rdx+8], r12
0x1800fb92a  lea     rcx, ?initial@?$StyleMetaData@$00@SVG@Mso@@2V?$optional@W4ColorSpace@GEL@@@std@@B; std::optional<GEL::ColorSpace> const Mso::SVG::StyleMetaData<1>::initial
0x1800fb931  jz      short loc_1800FB93A
0x1800fb933  lea     rcx, ?inherit@?$StyleMetaData@$00@SVG@Mso@@2V?$optional@W4ColorSpace@GEL@@@std@@B; std::optional<GEL::ColorSpace> const Mso::SVG::StyleMetaData<1>::inherit
0x1800fb93a  mov     eax, 8
0x1800fb93f  cmp     [rcx+1], r12b
0x1800fb943  jnz     short loc_1800FB963
0x1800fb945  mov     rcx, [rsi]
0x1800fb948  test    rcx, rcx
0x1800fb94b  jz      short loc_1800FB954
0x1800fb94d  call    ??$Get@$00@StyleResolveChain@SVG@Mso@@QEBAAEBW4ColorSpace@GEL@@XZ; Mso::SVG::StyleResolveChain::Get<1>(void)
0x1800fb952  jmp     short loc_1800FB960
0x1800fb954  mov     rdx, [rax+rdx]
0x1800fb958  mov     rcx, rsi
0x1800fb95b  call    ??$GetNormal@$00@StyleResolveChain@SVG@Mso@@AEBAAEBW4ColorSpace@GEL@@AEBVStyle@12@@Z; Mso::SVG::StyleResolveChain::GetNormal<1>(Mso::SVG::Style const &)
0x1800fb960  mov     rcx, rax
0x1800fb963  mov     r12b, [rcx]
0x1800fb966  mov     rcx, [rbx+1E8h]
0x1800fb96d  test    rcx, rcx
0x1800fb970  jz      loc_1800FBA18
0x1800fb976  mov     rax, [rcx]
0x1800fb979  mov     r9, rdi
0x1800fb97c  mov     r8, rsi
0x1800fb97f  lea     rdx, [rbp+var_28]
0x1800fb983  mov     rax, [rax+0B0h]
0x1800fb98a  call    cs:__guard_dispatch_icall_fptr
0x1800fb990  mov     [rsp+70h+var_40], r15
0x1800fb995  movsd   [rsp+70h+var_48], xmm6
0x1800fb99b  mov     [rsp+70h+var_50], r12b
0x1800fb9a0  mov     r9, [rax]
0x1800fb9a3  movsd   xmm2, qword ptr [rbx+200h]
0x1800fb9ab  mov     rdx, r13
0x1800fb9ae  lea     rcx, [rbp+arg_0]
0x1800fb9b2  call    cs:__imp_?Create@IEffectBumpMapDiffuse@GEL@@SA?AV?$TCntPtr@UIEffectBumpMapDiffuse@GEL@@@Ofc@@AEBUIEffect@2@NAEBUILightSource@2@W4ColorSpace@2@NPEBU?$TVector2@N@Math@@@Z; GEL::IEffectBumpMapDiffuse::Create(GEL::IEffect const &,double,GEL::ILightSource const &,GEL::ColorSpace,double,Math::TVector2<double> const *)
0x1800fb9b8  mov     rcx, [rax]
0x1800fb9bb  mov     qword ptr [rax], 0
0x1800fb9c2  mov     [r14], rcx
0x1800fb9c5  mov     rcx, [rbp+arg_0]
0x1800fb9c9  test    rcx, rcx
0x1800fb9cc  jz      short loc_1800FB9DC
0x1800fb9ce  mov     rax, [rcx]
0x1800fb9d1  mov     rax, [rax+8]
0x1800fb9d5  call    cs:__guard_dispatch_icall_fptr
0x1800fb9db  nop
0x1800fb9dc  mov     rcx, [rbp+var_28]
0x1800fb9e0  test    rcx, rcx
0x1800fb9e3  jz      short loc_1800FB9F2
0x1800fb9e5  mov     rax, [rcx]
0x1800fb9e8  mov     rax, [rax+8]
0x1800fb9ec  call    cs:__guard_dispatch_icall_fptr
0x1800fb9f2  mov     rax, r14
0x1800fb9f5  lea     r11, [rsp+70h+var_s0]
0x1800fb9fa  mov     rbx, [r11+38h]
0x1800fb9fe  mov     rsi, [r11+40h]
0x1800fba02  mov     rdi, [r11+48h]
0x1800fba06  movaps  xmm6, [rsp+70h+var_10]
0x1800fba0b  mov     rsp, r11
0x1800fba0e  pop     r15
0x1800fba10  pop     r14
0x1800fba12  pop     r13
0x1800fba14  pop     r12
0x1800fba16  pop     rbp
0x1800fba17  retn
0x1800fba18  xor     edx, edx
0x1800fba1a  mov     ecx, 21D758Bh
0x1800fba1f  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1800fba25  nop
0x1800fba26  xor     edx, edx
0x1800fba28  mov     ecx, 1E3C3843h
0x1800fba2d  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
```
