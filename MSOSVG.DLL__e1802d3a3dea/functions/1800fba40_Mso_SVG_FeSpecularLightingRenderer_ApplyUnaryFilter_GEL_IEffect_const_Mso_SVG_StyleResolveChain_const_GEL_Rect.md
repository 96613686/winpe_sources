# Mso::SVG::FeSpecularLightingRenderer::ApplyUnaryFilter(GEL::IEffect const &,Mso::SVG::StyleResolveChain const &,GEL::Rect const &,Mso::SVG::PrimitiveUnitResolver const &,GEL::IColorResolver const *)

- ea: `0x1800fba40`
- end: `0x1800fbc54`
- name: `?ApplyUnaryFilter@FeSpecularLightingRenderer@SVG@Mso@@UEBA?AV?$TCntPtr@$$CBUIEffect@GEL@@@Ofc@@AEBUIEffect@GEL@@AEBVStyleResolveChain@23@AEBURect@7@AEBVPrimitiveUnitResolver@23@PEBUIColorResolver@7@@Z`
- size: `532`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, __int64, _QWORD *, int, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800fba40`
- `0x1800fbda0`
- `0x1800fbee0`
- `0x18013e010`
- `0x18013f760`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800fbc3f`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800fbc4d`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800fbc3f`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800fbc4d`
- `gfx!?Create@IEffectBumpMapSpecular@GEL@@SA?AV?$TCntPtr@UIEffectBumpMapSpecular@GEL@@@Ofc@@AEBUIEffect@2@NAEBUILightSource@2@W4ColorSpace@2@NNPEBU?$TVector2@N@Math@@@Z` at `0x1800fbbca`
- `gfx!?Create@IEffectBumpMapSpecular@GEL@@SA?AV?$TCntPtr@UIEffectBumpMapSpecular@GEL@@@Ofc@@AEBUIEffect@2@NAEBUILightSource@2@W4ColorSpace@2@NNPEBU?$TVector2@N@Math@@@Z` at `0x1800fbbca`

## pseudocode

```c
_QWORD *__fastcall Mso::SVG::FeSpecularLightingRenderer::ApplyUnaryFilter(
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
  __int64 v15; // xmm7_8
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int16 *v18; // rcx
  __int64 v19; // rax
  char v20; // r12
  __int64 v21; // rcx
  _QWORD *v22; // rax
  __int64 v23; // r8
  __int64 *v24; // rax
  __int64 v25; // rcx
  __int64 v27; // [rsp+48h] [rbp-38h] BYREF
  __int128 v28; // [rsp+50h] [rbp-30h] BYREF
  __int64 v29; // [rsp+B0h] [rbp+30h] BYREF

  v9 = *(_QWORD **)(a1 + 16);
  if ( !v9 )
  {
LABEL_24:
    CrashWithRecovery(0x1E3C3843u, 0);
    JUMPOUT(0x1800FBC53LL);
  }
  _castguard_slow_path_check_user_handled(*v9, 9176, 2760);
  _castguard_slow_path_check_user_handled(*v9, 11936, 0);
  v28 = *((_OWORD *)v9 + 31);
  v10 = a6;
  v11 = *(double *)&v28;
  if ( *(_DWORD *)(a6 + 32) == 1 )
  {
    v11 = *(double *)&v28 * (*(double *)(a6 + 16) - *(double *)a6);
    *(double *)&v28 = v11;
    v12 = *((double *)&v28 + 1) * (*(double *)(a6 + 24) - *(double *)(a6 + 8));
    *((double *)&v28 + 1) = v12;
  }
  else
  {
    v12 = *((double *)&v28 + 1);
  }
  if ( v11 <= 0.0 || (v13 = &v28, v12 <= 0.0) )
    v13 = 0;
  v14 = v9[66];
  v15 = v9[65];
  v16 = a4[1];
  v17 = *(_QWORD *)(v16 + 16);
  if ( v17 )
  {
    v18 = (__int16 *)(v17 + 1320);
  }
  else
  {
    v18 = &Mso::SVG::StyleMetaData<1>::initial;
    if ( *(_QWORD *)(v16 + 8) )
      v18 = (__int16 *)&Mso::SVG::StyleMetaData<1>::inherit;
  }
  if ( !*((_BYTE *)v18 + 1) )
  {
    if ( *a4 )
      v19 = Mso::SVG::StyleResolveChain::Get<1>();
    else
      v19 = Mso::SVG::StyleResolveChain::GetNormal<1>(a4, *(_QWORD *)(v16 + 8));
    v18 = (__int16 *)v19;
  }
  v20 = *(_BYTE *)v18;
  v21 = v9[61];
  if ( !v21 )
  {
    CrashWithRecovery(0x21D758Bu, 0);
    goto LABEL_24;
  }
  v22 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, __int64 *, _QWORD *, __int64))(*(_QWORD *)v21 + 176LL))(
                    v21,
                    &v27,
                    a4,
                    v10);
  v24 = (__int64 *)GEL::IEffectBumpMapSpecular::Create(&v29, a3, v23, *v22, v20, v15, v14, v13);
  v25 = *v24;
  *v24 = 0;
  *a2 = v25;
  if ( v29 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 8LL))(v29);
  if ( v27 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 8LL))(v27);
  return a2;
}

```

## disassembly

```asm
0x1800fba40  mov     rax, rsp
0x1800fba43  mov     [rax+10h], rbx
0x1800fba47  mov     [rax+18h], rsi
0x1800fba4b  mov     [rax+20h], rdi
0x1800fba4f  push    rbp
0x1800fba50  push    r12
0x1800fba52  push    r13
0x1800fba54  push    r14
0x1800fba56  push    r15
0x1800fba58  mov     rbp, rsp
0x1800fba5b  sub     rsp, 80h
0x1800fba62  movaps  xmmword ptr [rax-38h], xmm6
0x1800fba66  movaps  xmmword ptr [rax-48h], xmm7
0x1800fba6a  mov     rsi, r9
0x1800fba6d  mov     r13, r8
0x1800fba70  mov     r14, rdx
0x1800fba73  xor     r12d, r12d
0x1800fba76  mov     rbx, [rcx+10h]
0x1800fba7a  test    rbx, rbx
0x1800fba7d  jz      loc_1800FBC46
0x1800fba83  mov     edx, 23D8h
0x1800fba88  mov     r8d, 0AC8h
0x1800fba8e  mov     rcx, [rbx]
0x1800fba91  call    __castguard_slow_path_check_user_handled
0x1800fba96  test    rbx, rbx
0x1800fba99  jz      short loc_1800FBAAD
0x1800fba9b  xor     r8d, r8d
0x1800fba9e  mov     edx, 2EA0h
0x1800fbaa3  mov     rcx, [rbx]
0x1800fbaa6  call    __castguard_slow_path_check_user_handled
0x1800fbaab  jmp     short loc_1800FBAB0
0x1800fbaad  mov     rbx, r12
0x1800fbab0  movups  xmm0, xmmword ptr [rbx+1F0h]
0x1800fbab7  movdqu  [rbp+var_30], xmm0
0x1800fbabc  mov     rdi, [rbp+arg_28]
0x1800fbac0  movsd   xmm2, qword ptr [rbp+var_30]
0x1800fbac5  cmp     dword ptr [rdi+20h], 1
0x1800fbac9  jnz     short loc_1800FBAF7
0x1800fbacb  movsd   xmm0, qword ptr [rdi+10h]
0x1800fbad0  subsd   xmm0, qword ptr [rdi]
0x1800fbad4  mulsd   xmm2, xmm0
0x1800fbad8  movsd   qword ptr [rbp+var_30], xmm2
0x1800fbadd  movsd   xmm1, qword ptr [rdi+18h]
0x1800fbae2  subsd   xmm1, qword ptr [rdi+8]
0x1800fbae7  movsd   xmm0, qword ptr [rbp+var_30+8]
0x1800fbaec  mulsd   xmm0, xmm1
0x1800fbaf0  movsd   qword ptr [rbp+var_30+8], xmm0
0x1800fbaf5  jmp     short loc_1800FBAFC
0x1800fbaf7  movsd   xmm0, qword ptr [rbp+var_30+8]
0x1800fbafc  xorps   xmm1, xmm1
0x1800fbaff  comisd  xmm2, xmm1
0x1800fbb03  jbe     short loc_1800FBB0F
0x1800fbb05  comisd  xmm0, xmm1
0x1800fbb09  lea     r15, [rbp+var_30]
0x1800fbb0d  ja      short loc_1800FBB12
0x1800fbb0f  mov     r15, r12
0x1800fbb12  movsd   xmm6, qword ptr [rbx+210h]
0x1800fbb1a  movsd   xmm7, qword ptr [rbx+208h]
0x1800fbb22  mov     rdx, [rsi+8]
0x1800fbb26  mov     rcx, [rdx+10h]
0x1800fbb2a  test    rcx, rcx
0x1800fbb2d  jz      short loc_1800FBB38
0x1800fbb2f  add     rcx, 528h
0x1800fbb36  jmp     short loc_1800FBB4C
0x1800fbb38  cmp     [rdx+8], r12
0x1800fbb3c  lea     rcx, ?initial@?$StyleMetaData@$00@SVG@Mso@@2V?$optional@W4ColorSpace@GEL@@@std@@B; std::optional<GEL::ColorSpace> const Mso::SVG::StyleMetaData<1>::initial
0x1800fbb43  jz      short loc_1800FBB4C
0x1800fbb45  lea     rcx, ?inherit@?$StyleMetaData@$00@SVG@Mso@@2V?$optional@W4ColorSpace@GEL@@@std@@B; std::optional<GEL::ColorSpace> const Mso::SVG::StyleMetaData<1>::inherit
0x1800fbb4c  mov     eax, 8
0x1800fbb51  cmp     [rcx+1], r12b
0x1800fbb55  jnz     short loc_1800FBB75
0x1800fbb57  mov     rcx, [rsi]
0x1800fbb5a  test    rcx, rcx
0x1800fbb5d  jz      short loc_1800FBB66
0x1800fbb5f  call    ??$Get@$00@StyleResolveChain@SVG@Mso@@QEBAAEBW4ColorSpace@GEL@@XZ; Mso::SVG::StyleResolveChain::Get<1>(void)
0x1800fbb64  jmp     short loc_1800FBB72
0x1800fbb66  mov     rdx, [rax+rdx]
0x1800fbb6a  mov     rcx, rsi
0x1800fbb6d  call    ??$GetNormal@$00@StyleResolveChain@SVG@Mso@@AEBAAEBW4ColorSpace@GEL@@AEBVStyle@12@@Z; Mso::SVG::StyleResolveChain::GetNormal<1>(Mso::SVG::Style const &)
0x1800fbb72  mov     rcx, rax
0x1800fbb75  mov     r12b, [rcx]
0x1800fbb78  mov     rcx, [rbx+1E8h]
0x1800fbb7f  test    rcx, rcx
0x1800fbb82  jz      loc_1800FBC38
0x1800fbb88  mov     rax, [rcx]
0x1800fbb8b  mov     r9, rdi
0x1800fbb8e  mov     r8, rsi
0x1800fbb91  lea     rdx, [rbp+var_38]
0x1800fbb95  mov     rax, [rax+0B0h]
0x1800fbb9c  call    cs:__guard_dispatch_icall_fptr
0x1800fbba2  mov     [rsp+80h+var_48], r15
0x1800fbba7  movsd   [rsp+80h+var_50], xmm6
0x1800fbbad  movsd   [rsp+80h+var_58], xmm7
0x1800fbbb3  mov     [rsp+80h+var_60], r12b
0x1800fbbb8  mov     r9, [rax]
0x1800fbbbb  movsd   xmm2, qword ptr [rbx+200h]
0x1800fbbc3  mov     rdx, r13
0x1800fbbc6  lea     rcx, [rbp+arg_0]
0x1800fbbca  call    cs:__imp_?Create@IEffectBumpMapSpecular@GEL@@SA?AV?$TCntPtr@UIEffectBumpMapSpecular@GEL@@@Ofc@@AEBUIEffect@2@NAEBUILightSource@2@W4ColorSpace@2@NNPEBU?$TVector2@N@Math@@@Z; GEL::IEffectBumpMapSpecular::Create(GEL::IEffect const &,double,GEL::ILightSource const &,GEL::ColorSpace,double,double,Math::TVector2<double> const *)
0x1800fbbd0  mov     rcx, [rax]
0x1800fbbd3  mov     qword ptr [rax], 0
0x1800fbbda  mov     [r14], rcx
0x1800fbbdd  mov     rcx, [rbp+arg_0]
0x1800fbbe1  test    rcx, rcx
0x1800fbbe4  jz      short loc_1800FBBF4
0x1800fbbe6  mov     rax, [rcx]
0x1800fbbe9  mov     rax, [rax+8]
0x1800fbbed  call    cs:__guard_dispatch_icall_fptr
0x1800fbbf3  nop
0x1800fbbf4  mov     rcx, [rbp+var_38]
0x1800fbbf8  test    rcx, rcx
0x1800fbbfb  jz      short loc_1800FBC0A
0x1800fbbfd  mov     rax, [rcx]
0x1800fbc00  mov     rax, [rax+8]
0x1800fbc04  call    cs:__guard_dispatch_icall_fptr
0x1800fbc0a  mov     rax, r14
0x1800fbc0d  lea     r11, [rsp+80h+var_s0]
0x1800fbc15  mov     rbx, [r11+38h]
0x1800fbc19  mov     rsi, [r11+40h]
0x1800fbc1d  mov     rdi, [r11+48h]
0x1800fbc21  movaps  xmm6, [rsp+80h+var_10]
0x1800fbc26  movaps  xmm7, [rsp+80h+var_20]
0x1800fbc2b  mov     rsp, r11
0x1800fbc2e  pop     r15
0x1800fbc30  pop     r14
0x1800fbc32  pop     r13
0x1800fbc34  pop     r12
0x1800fbc36  pop     rbp
0x1800fbc37  retn
0x1800fbc38  xor     edx, edx
0x1800fbc3a  mov     ecx, 21D758Bh
0x1800fbc3f  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1800fbc45  nop
0x1800fbc46  xor     edx, edx
0x1800fbc48  mov     ecx, 1E3C3843h
0x1800fbc4d  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
```
