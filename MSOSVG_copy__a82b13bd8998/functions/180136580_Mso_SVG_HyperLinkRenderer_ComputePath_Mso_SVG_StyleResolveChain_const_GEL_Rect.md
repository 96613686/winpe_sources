# Mso::SVG::HyperLinkRenderer::ComputePath(Mso::SVG::StyleResolveChain const &,GEL::Rect *)

- ea: `0x180136580`
- end: `0x18013677c`
- name: `?ComputePath@HyperLinkRenderer@SVG@Mso@@UEAA?AV?$TCntPtr@$$CBUIPath@GEL@@@3@AEBVStyleResolveChain@23@PEAURect@GEL@@@Z`
- size: `508`
- prototype: `__int64 __fastcall(Mso::SVG::RenderableRenderer *this)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x18000d5e0`
- `0x180041df8`
- `0x180041e94`
- `0x180043594`
- `0x180043c28`
- `0x1800447d0`
- `0x18004c058`
- `0x180136580`
- `0x18013e0c0`
- `0x18013f810`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180136767`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180136775`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180136767`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180136775`
- `gfx!?Create@IEmptyPath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@XZ` at `0x1801365b7`
- `gfx!?Create@IEmptyPath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@XZ` at `0x1801365b7`

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
  __int64 *v15; // rdx
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
    JUMPOUT(0x18013677BLL);
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
      v15 = (__int64 *)(v14 + 392);
    }
    else if ( !*(_BYTE *)(v22 + 24) || (v15 = Mso::SVG::StyleMetaData<33>::inherit, !*(_QWORD *)(v22 + 8)) )
    {
      v15 = (__int64 *)&Mso::SVG::StyleMetaData<33>::initial;
    }
    if ( !*((_BYTE *)v15 + 32) )
    {
      if ( v21 )
        v16 = Mso::SVG::StyleResolveChain::Get<33>(v21);
      else
        v16 = Mso::SVG::StyleResolveChain::GetNormal<33>(&v21, *(_QWORD *)(v22 + 8));
      v15 = (__int64 *)v16;
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
0x180136580  mov     [rsp-18h+arg_0], rbx
0x180136585  mov     [rsp-18h+arg_8], rsi
0x18013658a  mov     [rsp-18h+arg_10], rdi
0x18013658f  push    rbp
0x180136590  push    r14
0x180136592  push    r15
0x180136594  mov     rbp, rsp
0x180136597  sub     rsp, 80h
0x18013659e  mov     r15, r9
0x1801365a1  mov     r14, r8
0x1801365a4  mov     rbx, rdx
0x1801365a7  mov     rsi, rcx
0x1801365aa  call    ?IsRenderingEnabled@RenderableRenderer@SVG@Mso@@QEBA_NXZ; Mso::SVG::RenderableRenderer::IsRenderingEnabled(void)
0x1801365af  test    al, al
0x1801365b1  jnz     short loc_1801365E6
0x1801365b3  lea     rcx, [rbp+var_40]
0x1801365b7  call    cs:__imp_?Create@IEmptyPath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@XZ; GEL::IEmptyPath::Create(void)
0x1801365bd  mov     rcx, [rax]
0x1801365c0  test    rcx, rcx
0x1801365c3  mov     [rbx], rcx
0x1801365c6  jz      short loc_1801365D4
0x1801365c8  mov     rax, [rcx]
0x1801365cb  mov     rax, [rax]
0x1801365ce  call    cs:__guard_dispatch_icall_fptr
0x1801365d4  mov     rcx, [rbp+var_40]
0x1801365d8  test    rcx, rcx
0x1801365db  jz      loc_180136740
0x1801365e1  jmp     loc_180136733
0x1801365e6  mov     rdi, [rsi+10h]
0x1801365ea  test    rdi, rdi
0x1801365ed  jz      loc_18013676E
0x1801365f3  xor     r8d, r8d
0x1801365f6  mov     edx, 1830h
0x1801365fb  mov     rcx, [rdi]
0x1801365fe  call    __castguard_slow_path_check_user_handled
0x180136603  cmp     byte ptr [rdi+188h], 0
0x18013660a  jnz     short loc_1801365B3
0x18013660c  mov     rax, [rdi]
0x18013660f  mov     rcx, rdi
0x180136612  mov     rax, [rax+68h]
0x180136616  call    cs:__guard_dispatch_icall_fptr
0x18013661c  mov     [rbp+var_38], r14
0x180136620  mov     [rbp+var_30], rax
0x180136624  mov     rax, [r14+10h]
0x180136628  mov     [rbp+var_28], rax
0x18013662c  lea     rcx, [rbp+var_38]
0x180136630  call    ??$Get@$0BO@@StyleResolveChain@SVG@Mso@@QEBAAEB_NXZ; Mso::SVG::StyleResolveChain::Get<30>(void)
0x180136635  cmp     byte ptr [rax], 0
0x180136638  jz      loc_1801365B3
0x18013663e  xorps   xmm0, xmm0
0x180136641  movups  [rbp+var_20], xmm0
0x180136645  xorps   xmm1, xmm1
0x180136648  movups  [rbp+var_10], xmm1
0x18013664c  test    r15, r15
0x18013664f  jnz     short loc_1801366BD
0x180136651  mov     rax, [rbp+var_30]
0x180136655  mov     rdx, [rax+10h]
0x180136659  test    rdx, rdx
0x18013665c  jz      short loc_180136667
0x18013665e  add     rdx, 188h
0x180136665  jmp     short loc_180136682
0x180136667  cmp     byte ptr [rax+18h], 0
0x18013666b  jz      short loc_18013667B
0x18013666d  cmp     qword ptr [rax+8], 0
0x180136672  lea     rdx, ?inherit@?$StyleMetaData@$0CB@@SVG@Mso@@2V?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@B; std::optional<std::wstring> const Mso::SVG::StyleMetaData<33>::inherit
0x180136679  jnz     short loc_180136682
0x18013667b  lea     rdx, ?initial@?$StyleMetaData@$0CB@@SVG@Mso@@2V?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@B; std::optional<std::wstring> const Mso::SVG::StyleMetaData<33>::initial
0x180136682  cmp     byte ptr [rdx+20h], 0
0x180136686  jnz     short loc_1801366A8
0x180136688  mov     rcx, [rbp+var_38]
0x18013668c  test    rcx, rcx
0x18013668f  jz      short loc_180136698
0x180136691  call    ??$Get@$0CB@@StyleResolveChain@SVG@Mso@@QEBAAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; Mso::SVG::StyleResolveChain::Get<33>(void)
0x180136696  jmp     short loc_1801366A5
0x180136698  mov     rdx, [rax+8]
0x18013669c  lea     rcx, [rbp+var_38]
0x1801366a0  call    ??$GetNormal@$0CB@@StyleResolveChain@SVG@Mso@@AEBAAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBVStyle@12@@Z; Mso::SVG::StyleResolveChain::GetNormal<33>(Mso::SVG::Style const &)
0x1801366a5  mov     rdx, rax
0x1801366a8  cmp     qword ptr [rdx+10h], 0
0x1801366ad  jz      short loc_1801366BD
0x1801366af  mov     rax, [rsi+18h]
0x1801366b3  mov     rcx, [rax+40h]
0x1801366b7  call    ?QueryClipPath@Environment@SVG@Mso@@QEAAPEAVClipPathContext@23@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Mso::SVG::Environment::QueryClipPath(std::wstring const &)
0x1801366bc  nop
0x1801366bd  mov     rcx, [rsi+50h]
0x1801366c1  test    rcx, rcx
0x1801366c4  jz      loc_180136760
0x1801366ca  mov     rax, [rcx]
0x1801366cd  lea     r9, [rbp+var_20]
0x1801366d1  lea     r8, [rbp+var_38]
0x1801366d5  lea     rdx, [rbp+var_48]
0x1801366d9  mov     rax, [rax+18h]
0x1801366dd  call    cs:__guard_dispatch_icall_fptr
0x1801366e3  mov     [rsp+80h+var_58], 0
0x1801366ec  lea     rax, [rbp+var_20]
0x1801366f0  mov     [rsp+80h+var_60], rax
0x1801366f5  lea     r9, [rbp+var_38]
0x1801366f9  mov     r8, [rbp+var_48]
0x1801366fd  lea     rdx, [rbp+var_40]
0x180136701  mov     rcx, rsi
0x180136704  call    ?ApplyStandardPathEffects@RenderableRenderer@SVG@Mso@@QEBA?AV?$TCntPtr@$$CBUIPath@GEL@@@3@AEBUIPath@GEL@@AEBVStyleResolveChain@23@PEBURect@6@PEBU?$TAffine3x3@N@Math@@@Z; Mso::SVG::RenderableRenderer::ApplyStandardPathEffects(GEL::IPath const &,Mso::SVG::StyleResolveChain const &,GEL::Rect const *,Math::TAffine3x3<double> const *)
0x180136709  mov     r9b, 1; bool
0x18013670c  mov     r8, r15; struct GEL::Rect *
0x18013670f  lea     rdx, [rbp+var_20]; struct GEL::Rect *
0x180136713  mov     rcx, rsi; this
0x180136716  call    ?EndRendering@RenderableRenderer@SVG@Mso@@QEBAXAEBURect@GEL@@PEAU45@_N@Z; Mso::SVG::RenderableRenderer::EndRendering(GEL::Rect const &,GEL::Rect *,bool)
0x18013671b  mov     rax, [rbp+var_40]
0x18013671f  mov     [rbx], rax
0x180136722  mov     rcx, [rbp+var_48]
0x180136726  test    rcx, rcx
0x180136729  jz      short loc_180136740
0x18013672b  mov     [rbp+var_48], 0
0x180136733  mov     rax, [rcx]
0x180136736  mov     rax, [rax+8]
0x18013673a  call    cs:__guard_dispatch_icall_fptr
0x180136740  mov     rax, rbx
0x180136743  lea     r11, [rsp+80h+var_s0]
0x18013674b  mov     rbx, [r11+20h]
0x18013674f  mov     rsi, [r11+28h]
0x180136753  mov     rdi, [r11+30h]
0x180136757  mov     rsp, r11
0x18013675a  pop     r15
0x18013675c  pop     r14
0x18013675e  pop     rbp
0x18013675f  retn
0x180136760  xor     edx, edx
0x180136762  mov     ecx, 1E3C3840h
0x180136767  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x18013676d  nop
0x18013676e  xor     edx, edx
0x180136770  mov     ecx, 1E3C3843h
0x180136775  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
```
