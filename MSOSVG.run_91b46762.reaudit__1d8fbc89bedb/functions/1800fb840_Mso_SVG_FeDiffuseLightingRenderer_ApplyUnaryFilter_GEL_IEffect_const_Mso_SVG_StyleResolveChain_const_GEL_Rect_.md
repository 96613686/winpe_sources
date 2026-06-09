# Mso::SVG::FeDiffuseLightingRenderer::ApplyUnaryFilter(GEL::IEffect const &,Mso::SVG::StyleResolveChain const &,GEL::Rect const &,Mso::SVG::PrimitiveUnitResolver const &,GEL::IColorResolver const *)

- ea: `0x1800fb840`
- end: `0x1800fba54`
- name: `?ApplyUnaryFilter@FeDiffuseLightingRenderer@SVG@Mso@@UEBA?AV?$TCntPtr@$$CBUIEffect@GEL@@@Ofc@@AEBUIEffect@GEL@@AEBVStyleResolveChain@23@AEBURect@7@AEBVPrimitiveUnitResolver@23@PEBUIColorResolver@7@@Z`
- size: `532`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, __int64, _QWORD *, int, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800fb840`
- `0x1800fbdc0`
- `0x1800fbf00`
- `0x18013e0c0`
- `0x18013f810`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800fba3f`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800fba4d`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800fba3f`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800fba4d`
- `gfx!?Create@IEffectBumpMapDiffuse@GEL@@SA?AV?$TCntPtr@UIEffectBumpMapDiffuse@GEL@@@Ofc@@AEBUIEffect@2@NAEBUILightSource@2@W4ColorSpace@2@NPEBU?$TVector2@N@Math@@@Z` at `0x1800fb9d2`
- `gfx!?Create@IEffectBumpMapDiffuse@GEL@@SA?AV?$TCntPtr@UIEffectBumpMapDiffuse@GEL@@@Ofc@@AEBUIEffect@2@NAEBUILightSource@2@W4ColorSpace@2@NPEBU?$TVector2@N@Math@@@Z` at `0x1800fb9d2`

## pseudocode

```c
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
    JUMPOUT(0x1800FBA53LL);
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
0x1800fb840  mov     rax, rsp
0x1800fb843  mov     [rax+10h], rbx
0x1800fb847  mov     [rax+18h], rsi
0x1800fb84b  mov     [rax+20h], rdi
0x1800fb84f  push    rbp
0x1800fb850  push    r12
0x1800fb852  push    r13
0x1800fb854  push    r14
0x1800fb856  push    r15
0x1800fb858  mov     rbp, rsp
0x1800fb85b  sub     rsp, 70h
0x1800fb85f  movaps  xmmword ptr [rax-38h], xmm6
0x1800fb863  mov     rsi, r9
0x1800fb866  mov     r13, r8
0x1800fb869  mov     r14, rdx
0x1800fb86c  xor     r12d, r12d
0x1800fb86f  mov     rbx, [rcx+10h]
0x1800fb873  test    rbx, rbx
0x1800fb876  jz      loc_1800FBA46
0x1800fb87c  mov     edx, 23D8h
0x1800fb881  mov     r8d, 0AC8h
0x1800fb887  mov     rcx, [rbx]
0x1800fb88a  call    __castguard_slow_path_check_user_handled
0x1800fb88f  mov     edi, 2DE8h
0x1800fb894  test    rbx, rbx
0x1800fb897  jz      short loc_1800FB8AB
0x1800fb899  mov     r8d, 0B8h
0x1800fb89f  mov     edx, edi
0x1800fb8a1  mov     rcx, [rbx]
0x1800fb8a4  call    __castguard_slow_path_check_user_handled
0x1800fb8a9  jmp     short loc_1800FB8AE
0x1800fb8ab  mov     rbx, r12
0x1800fb8ae  test    rbx, rbx
0x1800fb8b1  jz      short loc_1800FB8C3
0x1800fb8b3  xor     r8d, r8d
0x1800fb8b6  mov     rdx, rdi
0x1800fb8b9  mov     rcx, [rbx]
0x1800fb8bc  call    __castguard_slow_path_check_user_handled
0x1800fb8c1  jmp     short loc_1800FB8C6
0x1800fb8c3  mov     rbx, r12
0x1800fb8c6  movups  xmm0, xmmword ptr [rbx+1F0h]
0x1800fb8cd  movdqu  [rbp+var_20], xmm0
0x1800fb8d2  mov     rdi, [rbp+arg_28]
0x1800fb8d6  movsd   xmm2, qword ptr [rbp+var_20]
0x1800fb8db  cmp     dword ptr [rdi+20h], 1
0x1800fb8df  jnz     short loc_1800FB90D
0x1800fb8e1  movsd   xmm0, qword ptr [rdi+10h]
0x1800fb8e6  subsd   xmm0, qword ptr [rdi]
0x1800fb8ea  mulsd   xmm2, xmm0
0x1800fb8ee  movsd   qword ptr [rbp+var_20], xmm2
0x1800fb8f3  movsd   xmm1, qword ptr [rdi+18h]
0x1800fb8f8  subsd   xmm1, qword ptr [rdi+8]
0x1800fb8fd  movsd   xmm0, qword ptr [rbp+var_20+8]
0x1800fb902  mulsd   xmm0, xmm1
0x1800fb906  movsd   qword ptr [rbp+var_20+8], xmm0
0x1800fb90b  jmp     short loc_1800FB912
0x1800fb90d  movsd   xmm0, qword ptr [rbp+var_20+8]
0x1800fb912  xorps   xmm1, xmm1
0x1800fb915  comisd  xmm2, xmm1
0x1800fb919  jbe     short loc_1800FB925
0x1800fb91b  comisd  xmm0, xmm1
0x1800fb91f  lea     r15, [rbp+var_20]
0x1800fb923  ja      short loc_1800FB928
0x1800fb925  mov     r15, r12
0x1800fb928  movsd   xmm6, qword ptr [rbx+208h]
0x1800fb930  mov     rdx, [rsi+8]
0x1800fb934  mov     rcx, [rdx+10h]
0x1800fb938  test    rcx, rcx
0x1800fb93b  jz      short loc_1800FB946
0x1800fb93d  add     rcx, 528h
0x1800fb944  jmp     short loc_1800FB95A
0x1800fb946  cmp     [rdx+8], r12
0x1800fb94a  lea     rcx, ?initial@?$StyleMetaData@$00@SVG@Mso@@2V?$optional@W4ColorSpace@GEL@@@std@@B; std::optional<GEL::ColorSpace> const Mso::SVG::StyleMetaData<1>::initial
0x1800fb951  jz      short loc_1800FB95A
0x1800fb953  lea     rcx, ?inherit@?$StyleMetaData@$00@SVG@Mso@@2V?$optional@W4ColorSpace@GEL@@@std@@B; std::optional<GEL::ColorSpace> const Mso::SVG::StyleMetaData<1>::inherit
0x1800fb95a  mov     eax, 8
0x1800fb95f  cmp     [rcx+1], r12b
0x1800fb963  jnz     short loc_1800FB983
0x1800fb965  mov     rcx, [rsi]
0x1800fb968  test    rcx, rcx
0x1800fb96b  jz      short loc_1800FB974
0x1800fb96d  call    ??$Get@$00@StyleResolveChain@SVG@Mso@@QEBAAEBW4ColorSpace@GEL@@XZ; Mso::SVG::StyleResolveChain::Get<1>(void)
0x1800fb972  jmp     short loc_1800FB980
0x1800fb974  mov     rdx, [rax+rdx]
0x1800fb978  mov     rcx, rsi
0x1800fb97b  call    ??$GetNormal@$00@StyleResolveChain@SVG@Mso@@AEBAAEBW4ColorSpace@GEL@@AEBVStyle@12@@Z; Mso::SVG::StyleResolveChain::GetNormal<1>(Mso::SVG::Style const &)
0x1800fb980  mov     rcx, rax
0x1800fb983  mov     r12b, [rcx]
0x1800fb986  mov     rcx, [rbx+1E8h]
0x1800fb98d  test    rcx, rcx
0x1800fb990  jz      loc_1800FBA38
0x1800fb996  mov     rax, [rcx]
0x1800fb999  mov     r9, rdi
0x1800fb99c  mov     r8, rsi
0x1800fb99f  lea     rdx, [rbp+var_28]
0x1800fb9a3  mov     rax, [rax+0B0h]
0x1800fb9aa  call    cs:__guard_dispatch_icall_fptr
0x1800fb9b0  mov     [rsp+70h+var_40], r15
0x1800fb9b5  movsd   [rsp+70h+var_48], xmm6
0x1800fb9bb  mov     [rsp+70h+var_50], r12b
0x1800fb9c0  mov     r9, [rax]
0x1800fb9c3  movsd   xmm2, qword ptr [rbx+200h]
0x1800fb9cb  mov     rdx, r13
0x1800fb9ce  lea     rcx, [rbp+arg_0]
0x1800fb9d2  call    cs:__imp_?Create@IEffectBumpMapDiffuse@GEL@@SA?AV?$TCntPtr@UIEffectBumpMapDiffuse@GEL@@@Ofc@@AEBUIEffect@2@NAEBUILightSource@2@W4ColorSpace@2@NPEBU?$TVector2@N@Math@@@Z; GEL::IEffectBumpMapDiffuse::Create(GEL::IEffect const &,double,GEL::ILightSource const &,GEL::ColorSpace,double,Math::TVector2<double> const *)
0x1800fb9d8  mov     rcx, [rax]
0x1800fb9db  mov     qword ptr [rax], 0
0x1800fb9e2  mov     [r14], rcx
0x1800fb9e5  mov     rcx, [rbp+arg_0]
0x1800fb9e9  test    rcx, rcx
0x1800fb9ec  jz      short loc_1800FB9FC
0x1800fb9ee  mov     rax, [rcx]
0x1800fb9f1  mov     rax, [rax+8]
0x1800fb9f5  call    cs:__guard_dispatch_icall_fptr
0x1800fb9fb  nop
0x1800fb9fc  mov     rcx, [rbp+var_28]
0x1800fba00  test    rcx, rcx
0x1800fba03  jz      short loc_1800FBA12
0x1800fba05  mov     rax, [rcx]
0x1800fba08  mov     rax, [rax+8]
0x1800fba0c  call    cs:__guard_dispatch_icall_fptr
0x1800fba12  mov     rax, r14
0x1800fba15  lea     r11, [rsp+70h+var_s0]
0x1800fba1a  mov     rbx, [r11+38h]
0x1800fba1e  mov     rsi, [r11+40h]
0x1800fba22  mov     rdi, [r11+48h]
0x1800fba26  movaps  xmm6, [rsp+70h+var_10]
0x1800fba2b  mov     rsp, r11
0x1800fba2e  pop     r15
0x1800fba30  pop     r14
0x1800fba32  pop     r13
0x1800fba34  pop     r12
0x1800fba36  pop     rbp
0x1800fba37  retn
0x1800fba38  xor     edx, edx
0x1800fba3a  mov     ecx, 21D758Bh
0x1800fba3f  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1800fba45  nop
0x1800fba46  xor     edx, edx
0x1800fba48  mov     ecx, 1E3C3843h
0x1800fba4d  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
```
