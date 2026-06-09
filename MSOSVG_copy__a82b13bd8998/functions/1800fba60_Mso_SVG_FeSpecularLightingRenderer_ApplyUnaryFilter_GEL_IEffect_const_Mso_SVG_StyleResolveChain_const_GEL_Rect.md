# Mso::SVG::FeSpecularLightingRenderer::ApplyUnaryFilter(GEL::IEffect const &,Mso::SVG::StyleResolveChain const &,GEL::Rect const &,Mso::SVG::PrimitiveUnitResolver const &,GEL::IColorResolver const *)

- ea: `0x1800fba60`
- end: `0x1800fbc74`
- name: `?ApplyUnaryFilter@FeSpecularLightingRenderer@SVG@Mso@@UEBA?AV?$TCntPtr@$$CBUIEffect@GEL@@@Ofc@@AEBUIEffect@GEL@@AEBVStyleResolveChain@23@AEBURect@7@AEBVPrimitiveUnitResolver@23@PEBUIColorResolver@7@@Z`
- size: `532`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, __int64, _QWORD *, int, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800fba60`
- `0x1800fbdc0`
- `0x1800fbf00`
- `0x18013e0c0`
- `0x18013f810`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800fbc5f`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800fbc6d`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800fbc5f`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800fbc6d`
- `gfx!?Create@IEffectBumpMapSpecular@GEL@@SA?AV?$TCntPtr@UIEffectBumpMapSpecular@GEL@@@Ofc@@AEBUIEffect@2@NAEBUILightSource@2@W4ColorSpace@2@NNPEBU?$TVector2@N@Math@@@Z` at `0x1800fbbea`
- `gfx!?Create@IEffectBumpMapSpecular@GEL@@SA?AV?$TCntPtr@UIEffectBumpMapSpecular@GEL@@@Ofc@@AEBUIEffect@2@NAEBUILightSource@2@W4ColorSpace@2@NNPEBU?$TVector2@N@Math@@@Z` at `0x1800fbbea`

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
    JUMPOUT(0x1800FBC73LL);
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
0x1800fba60  mov     rax, rsp
0x1800fba63  mov     [rax+10h], rbx
0x1800fba67  mov     [rax+18h], rsi
0x1800fba6b  mov     [rax+20h], rdi
0x1800fba6f  push    rbp
0x1800fba70  push    r12
0x1800fba72  push    r13
0x1800fba74  push    r14
0x1800fba76  push    r15
0x1800fba78  mov     rbp, rsp
0x1800fba7b  sub     rsp, 80h
0x1800fba82  movaps  xmmword ptr [rax-38h], xmm6
0x1800fba86  movaps  xmmword ptr [rax-48h], xmm7
0x1800fba8a  mov     rsi, r9
0x1800fba8d  mov     r13, r8
0x1800fba90  mov     r14, rdx
0x1800fba93  xor     r12d, r12d
0x1800fba96  mov     rbx, [rcx+10h]
0x1800fba9a  test    rbx, rbx
0x1800fba9d  jz      loc_1800FBC66
0x1800fbaa3  mov     edx, 23D8h
0x1800fbaa8  mov     r8d, 0AC8h
0x1800fbaae  mov     rcx, [rbx]
0x1800fbab1  call    __castguard_slow_path_check_user_handled
0x1800fbab6  test    rbx, rbx
0x1800fbab9  jz      short loc_1800FBACD
0x1800fbabb  xor     r8d, r8d
0x1800fbabe  mov     edx, 2EA0h
0x1800fbac3  mov     rcx, [rbx]
0x1800fbac6  call    __castguard_slow_path_check_user_handled
0x1800fbacb  jmp     short loc_1800FBAD0
0x1800fbacd  mov     rbx, r12
0x1800fbad0  movups  xmm0, xmmword ptr [rbx+1F0h]
0x1800fbad7  movdqu  [rbp+var_30], xmm0
0x1800fbadc  mov     rdi, [rbp+arg_28]
0x1800fbae0  movsd   xmm2, qword ptr [rbp+var_30]
0x1800fbae5  cmp     dword ptr [rdi+20h], 1
0x1800fbae9  jnz     short loc_1800FBB17
0x1800fbaeb  movsd   xmm0, qword ptr [rdi+10h]
0x1800fbaf0  subsd   xmm0, qword ptr [rdi]
0x1800fbaf4  mulsd   xmm2, xmm0
0x1800fbaf8  movsd   qword ptr [rbp+var_30], xmm2
0x1800fbafd  movsd   xmm1, qword ptr [rdi+18h]
0x1800fbb02  subsd   xmm1, qword ptr [rdi+8]
0x1800fbb07  movsd   xmm0, qword ptr [rbp+var_30+8]
0x1800fbb0c  mulsd   xmm0, xmm1
0x1800fbb10  movsd   qword ptr [rbp+var_30+8], xmm0
0x1800fbb15  jmp     short loc_1800FBB1C
0x1800fbb17  movsd   xmm0, qword ptr [rbp+var_30+8]
0x1800fbb1c  xorps   xmm1, xmm1
0x1800fbb1f  comisd  xmm2, xmm1
0x1800fbb23  jbe     short loc_1800FBB2F
0x1800fbb25  comisd  xmm0, xmm1
0x1800fbb29  lea     r15, [rbp+var_30]
0x1800fbb2d  ja      short loc_1800FBB32
0x1800fbb2f  mov     r15, r12
0x1800fbb32  movsd   xmm6, qword ptr [rbx+210h]
0x1800fbb3a  movsd   xmm7, qword ptr [rbx+208h]
0x1800fbb42  mov     rdx, [rsi+8]
0x1800fbb46  mov     rcx, [rdx+10h]
0x1800fbb4a  test    rcx, rcx
0x1800fbb4d  jz      short loc_1800FBB58
0x1800fbb4f  add     rcx, 528h
0x1800fbb56  jmp     short loc_1800FBB6C
0x1800fbb58  cmp     [rdx+8], r12
0x1800fbb5c  lea     rcx, ?initial@?$StyleMetaData@$00@SVG@Mso@@2V?$optional@W4ColorSpace@GEL@@@std@@B; std::optional<GEL::ColorSpace> const Mso::SVG::StyleMetaData<1>::initial
0x1800fbb63  jz      short loc_1800FBB6C
0x1800fbb65  lea     rcx, ?inherit@?$StyleMetaData@$00@SVG@Mso@@2V?$optional@W4ColorSpace@GEL@@@std@@B; std::optional<GEL::ColorSpace> const Mso::SVG::StyleMetaData<1>::inherit
0x1800fbb6c  mov     eax, 8
0x1800fbb71  cmp     [rcx+1], r12b
0x1800fbb75  jnz     short loc_1800FBB95
0x1800fbb77  mov     rcx, [rsi]
0x1800fbb7a  test    rcx, rcx
0x1800fbb7d  jz      short loc_1800FBB86
0x1800fbb7f  call    ??$Get@$00@StyleResolveChain@SVG@Mso@@QEBAAEBW4ColorSpace@GEL@@XZ; Mso::SVG::StyleResolveChain::Get<1>(void)
0x1800fbb84  jmp     short loc_1800FBB92
0x1800fbb86  mov     rdx, [rax+rdx]
0x1800fbb8a  mov     rcx, rsi
0x1800fbb8d  call    ??$GetNormal@$00@StyleResolveChain@SVG@Mso@@AEBAAEBW4ColorSpace@GEL@@AEBVStyle@12@@Z; Mso::SVG::StyleResolveChain::GetNormal<1>(Mso::SVG::Style const &)
0x1800fbb92  mov     rcx, rax
0x1800fbb95  mov     r12b, [rcx]
0x1800fbb98  mov     rcx, [rbx+1E8h]
0x1800fbb9f  test    rcx, rcx
0x1800fbba2  jz      loc_1800FBC58
0x1800fbba8  mov     rax, [rcx]
0x1800fbbab  mov     r9, rdi
0x1800fbbae  mov     r8, rsi
0x1800fbbb1  lea     rdx, [rbp+var_38]
0x1800fbbb5  mov     rax, [rax+0B0h]
0x1800fbbbc  call    cs:__guard_dispatch_icall_fptr
0x1800fbbc2  mov     [rsp+80h+var_48], r15
0x1800fbbc7  movsd   [rsp+80h+var_50], xmm6
0x1800fbbcd  movsd   [rsp+80h+var_58], xmm7
0x1800fbbd3  mov     [rsp+80h+var_60], r12b
0x1800fbbd8  mov     r9, [rax]
0x1800fbbdb  movsd   xmm2, qword ptr [rbx+200h]
0x1800fbbe3  mov     rdx, r13
0x1800fbbe6  lea     rcx, [rbp+arg_0]
0x1800fbbea  call    cs:__imp_?Create@IEffectBumpMapSpecular@GEL@@SA?AV?$TCntPtr@UIEffectBumpMapSpecular@GEL@@@Ofc@@AEBUIEffect@2@NAEBUILightSource@2@W4ColorSpace@2@NNPEBU?$TVector2@N@Math@@@Z; GEL::IEffectBumpMapSpecular::Create(GEL::IEffect const &,double,GEL::ILightSource const &,GEL::ColorSpace,double,double,Math::TVector2<double> const *)
0x1800fbbf0  mov     rcx, [rax]
0x1800fbbf3  mov     qword ptr [rax], 0
0x1800fbbfa  mov     [r14], rcx
0x1800fbbfd  mov     rcx, [rbp+arg_0]
0x1800fbc01  test    rcx, rcx
0x1800fbc04  jz      short loc_1800FBC14
0x1800fbc06  mov     rax, [rcx]
0x1800fbc09  mov     rax, [rax+8]
0x1800fbc0d  call    cs:__guard_dispatch_icall_fptr
0x1800fbc13  nop
0x1800fbc14  mov     rcx, [rbp+var_38]
0x1800fbc18  test    rcx, rcx
0x1800fbc1b  jz      short loc_1800FBC2A
0x1800fbc1d  mov     rax, [rcx]
0x1800fbc20  mov     rax, [rax+8]
0x1800fbc24  call    cs:__guard_dispatch_icall_fptr
0x1800fbc2a  mov     rax, r14
0x1800fbc2d  lea     r11, [rsp+80h+var_s0]
0x1800fbc35  mov     rbx, [r11+38h]
0x1800fbc39  mov     rsi, [r11+40h]
0x1800fbc3d  mov     rdi, [r11+48h]
0x1800fbc41  movaps  xmm6, [rsp+80h+var_10]
0x1800fbc46  movaps  xmm7, [rsp+80h+var_20]
0x1800fbc4b  mov     rsp, r11
0x1800fbc4e  pop     r15
0x1800fbc50  pop     r14
0x1800fbc52  pop     r13
0x1800fbc54  pop     r12
0x1800fbc56  pop     rbp
0x1800fbc57  retn
0x1800fbc58  xor     edx, edx
0x1800fbc5a  mov     ecx, 21D758Bh
0x1800fbc5f  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1800fbc65  nop
0x1800fbc66  xor     edx, edx
0x1800fbc68  mov     ecx, 1E3C3843h
0x1800fbc6d  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
```
