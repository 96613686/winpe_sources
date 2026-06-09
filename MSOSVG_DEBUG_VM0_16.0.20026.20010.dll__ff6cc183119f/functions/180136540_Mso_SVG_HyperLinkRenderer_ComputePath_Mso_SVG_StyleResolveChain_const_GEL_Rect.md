# Mso::SVG::HyperLinkRenderer::ComputePath(Mso::SVG::StyleResolveChain const &,GEL::Rect *)

- ea: `0x180136540`
- end: `0x18013673c`
- name: `?ComputePath@HyperLinkRenderer@SVG@Mso@@UEAA?AV?$TCntPtr@$$CBUIPath@GEL@@@3@AEBVStyleResolveChain@23@PEAURect@GEL@@@Z`
- size: `508`
- prototype: `__int64 __fastcall(Mso::SVG::RenderableRenderer *this)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x18000d5e0`
- `0x180041de0`
- `0x180041e7c`
- `0x180043578`
- `0x180043c10`
- `0x1800447b0`
- `0x18004c038`
- `0x180136540`
- `0x18013e010`
- `0x18013f760`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180136727`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180136735`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180136727`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180136735`
- `gfx!?Create@IEmptyPath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@XZ` at `0x180136577`
- `gfx!?Create@IEmptyPath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@XZ` at `0x180136577`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall Mso::SVG::HyperLinkRenderer::ComputePath(
        Mso::SVG::RenderableRenderer *this,
        _QWORD *a2,
        __int64 a3,
        struct GEL::Rect *a4)
{
  void (__fastcall ****v8)(_QWORD); // rax
  void (__fastcall ***v9)(_QWORD); // rcx
  bool v10; // zf
  __int64 v11; // rcx
  __int64 v12; // rdi
  __int64 v13; // rax
  __int64 v14; // rdx
  wchar_t **v15; // rdx
  __int64 v16; // rax
  __int64 v17; // rcx
  __int64 v19; // [rsp+38h] [rbp-48h] BYREF
  __int64 v20; // [rsp+40h] [rbp-40h] BYREF
  __int64 v21; // [rsp+48h] [rbp-38h] BYREF
  __int64 v22; // [rsp+50h] [rbp-30h]
  __int64 v23; // [rsp+58h] [rbp-28h]
  _OWORD v24[2]; // [rsp+60h] [rbp-20h] BYREF

  if ( !Mso::SVG::RenderableRenderer::IsRenderingEnabled(this) )
  {
LABEL_2:
    v8 = (void (__fastcall ****)(_QWORD))GEL::IEmptyPath::Create(&v20);
    v9 = *v8;
    v10 = *v8 == 0;
    *a2 = *v8;
    if ( !v10 )
      (**v9)(v9);
    v11 = v20;
    if ( v20 )
      goto LABEL_25;
    return a2;
  }
  v12 = *((_QWORD *)this + 2);
  if ( !v12 )
  {
LABEL_28:
    CrashWithRecovery(0x1E3C3843u, 0);
    JUMPOUT(0x18013673BLL);
  }
  _castguard_slow_path_check_user_handled(*(_QWORD *)v12, 6192, 0);
  if ( *(_BYTE *)(v12 + 392) )
    goto LABEL_2;
  v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v12 + 104LL))(v12);
  v21 = a3;
  v22 = v13;
  v23 = *(_QWORD *)(a3 + 16);
  if ( !*(_BYTE *)Mso::SVG::StyleResolveChain::Get<30>(&v21) )
    goto LABEL_2;
  memset(v24, 0, sizeof(v24));
  if ( !a4 )
  {
    v14 = *(_QWORD *)(v22 + 16);
    if ( v14 )
    {
      v15 = (wchar_t **)(v14 + 392);
    }
    else if ( !*(_BYTE *)(v22 + 24) || (v15 = (wchar_t **)&Mso::SVG::StyleMetaData<33>::inherit, !*(_QWORD *)(v22 + 8)) )
    {
      v15 = &Mso::SVG::StyleMetaData<33>::initial;
    }
    if ( !*((_BYTE *)v15 + 32) )
    {
      if ( v21 )
        v16 = Mso::SVG::StyleResolveChain::Get<33>(v21);
      else
        v16 = Mso::SVG::StyleResolveChain::GetNormal<33>(&v21, *(_QWORD *)(v22 + 8));
      v15 = (wchar_t **)v16;
    }
    if ( v15[2] )
      Mso::SVG::Environment::QueryClipPath(*(_QWORD *)(*((_QWORD *)this + 3) + 64LL));
  }
  v17 = *((_QWORD *)this + 10);
  if ( !v17 )
  {
    CrashWithRecovery(0x1E3C3840u, 0);
    goto LABEL_28;
  }
  (*(void (__fastcall **)(__int64, __int64 *, __int64 *, _OWORD *))(*(_QWORD *)v17 + 24LL))(v17, &v19, &v21, v24);
  Mso::SVG::RenderableRenderer::ApplyStandardPathEffects(
    (_DWORD)this,
    (unsigned int)&v20,
    v19,
    (unsigned int)&v21,
    (__int64)v24,
    0);
  Mso::SVG::RenderableRenderer::EndRendering(this, (const struct GEL::Rect *)v24, a4, 1);
  *a2 = v20;
  v11 = v19;
  if ( v19 )
  {
    v19 = 0;
LABEL_25:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
  }
  return a2;
}

```

## disassembly

```asm
0x180136540  mov     [rsp-18h+arg_0], rbx
0x180136545  mov     [rsp-18h+arg_8], rsi
0x18013654a  mov     [rsp-18h+arg_10], rdi
0x18013654f  push    rbp
0x180136550  push    r14
0x180136552  push    r15
0x180136554  mov     rbp, rsp
0x180136557  sub     rsp, 80h
0x18013655e  mov     r15, r9
0x180136561  mov     r14, r8
0x180136564  mov     rbx, rdx
0x180136567  mov     rsi, rcx
0x18013656a  call    ?IsRenderingEnabled@RenderableRenderer@SVG@Mso@@QEBA_NXZ; Mso::SVG::RenderableRenderer::IsRenderingEnabled(void)
0x18013656f  test    al, al
0x180136571  jnz     short loc_1801365A6
0x180136573  lea     rcx, [rbp+var_40]
0x180136577  call    cs:__imp_?Create@IEmptyPath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@XZ; GEL::IEmptyPath::Create(void)
0x18013657d  mov     rcx, [rax]
0x180136580  test    rcx, rcx
0x180136583  mov     [rbx], rcx
0x180136586  jz      short loc_180136594
0x180136588  mov     rax, [rcx]
0x18013658b  mov     rax, [rax]
0x18013658e  call    cs:__guard_dispatch_icall_fptr
0x180136594  mov     rcx, [rbp+var_40]
0x180136598  test    rcx, rcx
0x18013659b  jz      loc_180136700
0x1801365a1  jmp     loc_1801366F3
0x1801365a6  mov     rdi, [rsi+10h]
0x1801365aa  test    rdi, rdi
0x1801365ad  jz      loc_18013672E
0x1801365b3  xor     r8d, r8d
0x1801365b6  mov     edx, 1830h
0x1801365bb  mov     rcx, [rdi]
0x1801365be  call    __castguard_slow_path_check_user_handled
0x1801365c3  cmp     byte ptr [rdi+188h], 0
0x1801365ca  jnz     short loc_180136573
0x1801365cc  mov     rax, [rdi]
0x1801365cf  mov     rcx, rdi
0x1801365d2  mov     rax, [rax+68h]
0x1801365d6  call    cs:__guard_dispatch_icall_fptr
0x1801365dc  mov     [rbp+var_38], r14
0x1801365e0  mov     [rbp+var_30], rax
0x1801365e4  mov     rax, [r14+10h]
0x1801365e8  mov     [rbp+var_28], rax
0x1801365ec  lea     rcx, [rbp+var_38]
0x1801365f0  call    ??$Get@$0BO@@StyleResolveChain@SVG@Mso@@QEBAAEB_NXZ; Mso::SVG::StyleResolveChain::Get<30>(void)
0x1801365f5  cmp     byte ptr [rax], 0
0x1801365f8  jz      loc_180136573
0x1801365fe  xorps   xmm0, xmm0
0x180136601  movups  [rbp+var_20], xmm0
0x180136605  xorps   xmm1, xmm1
0x180136608  movups  [rbp+var_10], xmm1
0x18013660c  test    r15, r15
0x18013660f  jnz     short loc_18013667D
0x180136611  mov     rax, [rbp+var_30]
0x180136615  mov     rdx, [rax+10h]
0x180136619  test    rdx, rdx
0x18013661c  jz      short loc_180136627
0x18013661e  add     rdx, 188h
0x180136625  jmp     short loc_180136642
0x180136627  cmp     byte ptr [rax+18h], 0
0x18013662b  jz      short loc_18013663B
0x18013662d  cmp     qword ptr [rax+8], 0
0x180136632  lea     rdx, ?inherit@?$StyleMetaData@$0CB@@SVG@Mso@@2V?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@B; std::optional<std::wstring> const Mso::SVG::StyleMetaData<33>::inherit
0x180136639  jnz     short loc_180136642
0x18013663b  lea     rdx, ?initial@?$StyleMetaData@$0CB@@SVG@Mso@@2V?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@B; std::optional<std::wstring> const Mso::SVG::StyleMetaData<33>::initial
0x180136642  cmp     byte ptr [rdx+20h], 0
0x180136646  jnz     short loc_180136668
0x180136648  mov     rcx, [rbp+var_38]
0x18013664c  test    rcx, rcx
0x18013664f  jz      short loc_180136658
0x180136651  call    ??$Get@$0CB@@StyleResolveChain@SVG@Mso@@QEBAAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; Mso::SVG::StyleResolveChain::Get<33>(void)
0x180136656  jmp     short loc_180136665
0x180136658  mov     rdx, [rax+8]
0x18013665c  lea     rcx, [rbp+var_38]
0x180136660  call    ??$GetNormal@$0CB@@StyleResolveChain@SVG@Mso@@AEBAAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBVStyle@12@@Z; Mso::SVG::StyleResolveChain::GetNormal<33>(Mso::SVG::Style const &)
0x180136665  mov     rdx, rax
0x180136668  cmp     qword ptr [rdx+10h], 0
0x18013666d  jz      short loc_18013667D
0x18013666f  mov     rax, [rsi+18h]
0x180136673  mov     rcx, [rax+40h]
0x180136677  call    ?QueryClipPath@Environment@SVG@Mso@@QEAAPEAVClipPathContext@23@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Mso::SVG::Environment::QueryClipPath(std::wstring const &)
0x18013667c  nop
0x18013667d  mov     rcx, [rsi+50h]
0x180136681  test    rcx, rcx
0x180136684  jz      loc_180136720
0x18013668a  mov     rax, [rcx]
0x18013668d  lea     r9, [rbp+var_20]
0x180136691  lea     r8, [rbp+var_38]
0x180136695  lea     rdx, [rbp+var_48]
0x180136699  mov     rax, [rax+18h]
0x18013669d  call    cs:__guard_dispatch_icall_fptr
0x1801366a3  mov     [rsp+80h+var_58], 0
0x1801366ac  lea     rax, [rbp+var_20]
0x1801366b0  mov     [rsp+80h+var_60], rax
0x1801366b5  lea     r9, [rbp+var_38]
0x1801366b9  mov     r8, [rbp+var_48]
0x1801366bd  lea     rdx, [rbp+var_40]
0x1801366c1  mov     rcx, rsi
0x1801366c4  call    ?ApplyStandardPathEffects@RenderableRenderer@SVG@Mso@@QEBA?AV?$TCntPtr@$$CBUIPath@GEL@@@3@AEBUIPath@GEL@@AEBVStyleResolveChain@23@PEBURect@6@PEBU?$TAffine3x3@N@Math@@@Z; Mso::SVG::RenderableRenderer::ApplyStandardPathEffects(GEL::IPath const &,Mso::SVG::StyleResolveChain const &,GEL::Rect const *,Math::TAffine3x3<double> const *)
0x1801366c9  mov     r9b, 1; bool
0x1801366cc  mov     r8, r15; struct GEL::Rect *
0x1801366cf  lea     rdx, [rbp+var_20]; struct GEL::Rect *
0x1801366d3  mov     rcx, rsi; this
0x1801366d6  call    ?EndRendering@RenderableRenderer@SVG@Mso@@QEBAXAEBURect@GEL@@PEAU45@_N@Z; Mso::SVG::RenderableRenderer::EndRendering(GEL::Rect const &,GEL::Rect *,bool)
0x1801366db  mov     rax, [rbp+var_40]
0x1801366df  mov     [rbx], rax
0x1801366e2  mov     rcx, [rbp+var_48]
0x1801366e6  test    rcx, rcx
0x1801366e9  jz      short loc_180136700
0x1801366eb  mov     [rbp+var_48], 0
0x1801366f3  mov     rax, [rcx]
0x1801366f6  mov     rax, [rax+8]
0x1801366fa  call    cs:__guard_dispatch_icall_fptr
0x180136700  mov     rax, rbx
0x180136703  lea     r11, [rsp+80h+var_s0]
0x18013670b  mov     rbx, [r11+20h]
0x18013670f  mov     rsi, [r11+28h]
0x180136713  mov     rdi, [r11+30h]
0x180136717  mov     rsp, r11
0x18013671a  pop     r15
0x18013671c  pop     r14
0x18013671e  pop     rbp
0x18013671f  retn
0x180136720  xor     edx, edx
0x180136722  mov     ecx, 1E3C3840h
0x180136727  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x18013672d  nop
0x18013672e  xor     edx, edx
0x180136730  mov     ecx, 1E3C3843h
0x180136735  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
```
