# Mso::SVG::ShapeRenderer::ComputePath(Mso::SVG::StyleResolveChain const &,GEL::Rect *)

- ea: `0x18010bcb0`
- end: `0x18010bed9`
- name: `?ComputePath@ShapeRenderer@SVG@Mso@@UEAA?AV?$TCntPtr@$$CBUIPath@GEL@@@3@AEBVStyleResolveChain@23@PEAURect@GEL@@@Z`
- size: `553`
- prototype: `__int64 __fastcall(Mso::SVG::RenderableRenderer *this)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x18000d5e0`
- `0x180041df8`
- `0x180041e94`
- `0x180043c28`
- `0x18010b9e8`
- `0x18010bcb0`
- `0x18010d1bc`
- `0x18010d5cc`
- `0x18013e0c0`
- `0x18013f810`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18010bec4`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18010bed2`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18010bec4`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18010bed2`
- `gfx!?Create@IEmptyPath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@XZ` at `0x18010bdfc`
- `gfx!?Create@IEmptyPath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@XZ` at `0x18010bdfc`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall Mso::SVG::ShapeRenderer::ComputePath(
        Mso::SVG::RenderableRenderer *this,
        _QWORD *a2,
        __int64 a3,
        struct GEL::Rect *a4)
{
  _QWORD *v8; // r14
  __int64 v9; // rdx
  __int64 v10; // rax
  __int64 *v11; // rax
  __int64 v12; // rax
  __int64 *v13; // rax
  __int64 v14; // rbx
  void (__fastcall ****v15)(_QWORD); // rax
  void (__fastcall ***v16)(_QWORD); // rcx
  __int64 v18; // [rsp+38h] [rbp-48h] BYREF
  __int64 v19; // [rsp+40h] [rbp-40h] BYREF
  __int64 v20; // [rsp+48h] [rbp-38h]
  __int64 v21; // [rsp+50h] [rbp-30h]
  _OWORD v22[2]; // [rsp+58h] [rbp-28h] BYREF
  __int64 v23; // [rsp+A0h] [rbp+20h] BYREF

  v8 = (_QWORD *)*((_QWORD *)this + 2);
  if ( !v8 )
  {
    CrashWithRecovery(0x1E3C3843u, 0);
    JUMPOUT(0x18010BED8LL);
  }
  _castguard_slow_path_check_user_handled(*v8, 3968, 800);
  v9 = (*(__int64 (__fastcall **)(_QWORD *))(*v8 + 104LL))(v8);
  v19 = a3;
  v20 = v9;
  v21 = *(_QWORD *)(a3 + 16);
  memset(v22, 0, sizeof(v22));
  if ( !a4 )
  {
    v10 = *(_QWORD *)(v9 + 16);
    if ( v10 )
    {
      v11 = (__int64 *)(v10 + 392);
    }
    else if ( !*(_BYTE *)(v9 + 24) || (v11 = Mso::SVG::StyleMetaData<33>::inherit, !*(_QWORD *)(v9 + 8)) )
    {
      v11 = (__int64 *)&Mso::SVG::StyleMetaData<33>::initial;
    }
    if ( !*((_BYTE *)v11 + 32) )
    {
      v11 = (__int64 *)Mso::SVG::StyleResolveChain::Get<33>(a3);
      v9 = v20;
      a3 = v19;
    }
    if ( v11[2] )
    {
      Mso::SVG::Environment::QueryClipPath(*(_QWORD *)(*((_QWORD *)this + 3) + 64LL));
      v9 = v20;
      a3 = v19;
    }
  }
  v12 = *(_QWORD *)(v9 + 16);
  if ( v12 )
  {
    v13 = (__int64 *)(v12 + 808);
  }
  else
  {
    v13 = &Mso::SVG::StyleMetaData<16>::initial;
    if ( *(_QWORD *)(v9 + 8) )
      v13 = &Mso::SVG::StyleMetaData<16>::inherit;
  }
  if ( !*((_BYTE *)v13 + 4) )
  {
    if ( a3 )
      v13 = (__int64 *)Mso::SVG::StyleResolveChain::Get<16>(a3);
    else
      v13 = (__int64 *)Mso::SVG::StyleResolveChain::GetNormal<16>(&v19, *(_QWORD *)(v9 + 8));
  }
  Mso::SVG::ShapeRenderer::GetEffectivePath(this, &v23, &v19, *(_DWORD *)v13);
  v14 = v23;
  if ( v23 )
  {
    (*(void (__fastcall **)(__int64, _OWORD *))(*(_QWORD *)v23 + 104LL))(v23, v22);
    Mso::SVG::RenderableRenderer::ApplyStandardPathEffects(
      (_DWORD)this,
      (unsigned int)&v18,
      v14,
      (unsigned int)&v19,
      (__int64)v22,
      0);
    Mso::SVG::RenderableRenderer::EndRendering(this, (const struct GEL::Rect *)v22, a4, 1);
    *a2 = v18;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
  }
  else
  {
    v15 = (void (__fastcall ****)(_QWORD))GEL::IEmptyPath::Create(&v18);
    v16 = *v15;
    *a2 = *v15;
    if ( v16 )
      (**v16)(v16);
    if ( v18 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 8LL))(v18);
  }
  return a2;
}

```

## disassembly

```asm
0x18010bcb0  mov     [rsp-18h+arg_8], rbx
0x18010bcb5  mov     [rsp-18h+arg_10], rsi
0x18010bcba  mov     [rsp-18h+arg_18], rdi
0x18010bcbf  push    rbp
0x18010bcc0  push    r14
0x18010bcc2  push    r15
0x18010bcc4  mov     rbp, rsp
0x18010bcc7  sub     rsp, 80h
0x18010bcce  mov     r15, r9
0x18010bcd1  mov     rbx, r8
0x18010bcd4  mov     rdi, rdx
0x18010bcd7  mov     rsi, rcx
0x18010bcda  mov     r14, [rcx+10h]
0x18010bcde  test    r14, r14
0x18010bce1  jz      loc_18010BECB
0x18010bce7  mov     edx, 0F80h
0x18010bcec  mov     r8d, 320h
0x18010bcf2  mov     rcx, [r14]
0x18010bcf5  call    __castguard_slow_path_check_user_handled
0x18010bcfa  mov     rax, [r14]
0x18010bcfd  mov     rcx, r14
0x18010bd00  mov     rax, [rax+68h]
0x18010bd04  call    cs:__guard_dispatch_icall_fptr
0x18010bd0a  mov     rdx, rax
0x18010bd0d  mov     [rbp+var_40], rbx
0x18010bd11  mov     [rbp+var_38], rax
0x18010bd15  mov     rax, [rbx+10h]
0x18010bd19  mov     [rbp+var_30], rax
0x18010bd1d  xorps   xmm0, xmm0
0x18010bd20  movups  [rbp+var_28], xmm0
0x18010bd24  xorps   xmm1, xmm1
0x18010bd27  movups  [rbp+var_18], xmm1
0x18010bd2b  test    r15, r15
0x18010bd2e  jnz     short loc_18010BD91
0x18010bd30  mov     rax, [rdx+10h]
0x18010bd34  test    rax, rax
0x18010bd37  jz      short loc_18010BD41
0x18010bd39  add     rax, 188h
0x18010bd3f  jmp     short loc_18010BD5C
0x18010bd41  cmp     byte ptr [rdx+18h], 0
0x18010bd45  jz      short loc_18010BD55
0x18010bd47  cmp     qword ptr [rdx+8], 0
0x18010bd4c  lea     rax, ?inherit@?$StyleMetaData@$0CB@@SVG@Mso@@2V?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@B; std::optional<std::wstring> const Mso::SVG::StyleMetaData<33>::inherit
0x18010bd53  jnz     short loc_18010BD5C
0x18010bd55  lea     rax, ?initial@?$StyleMetaData@$0CB@@SVG@Mso@@2V?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@B; std::optional<std::wstring> const Mso::SVG::StyleMetaData<33>::initial
0x18010bd5c  cmp     byte ptr [rax+20h], 0
0x18010bd60  jnz     short loc_18010BD72
0x18010bd62  mov     rcx, rbx
0x18010bd65  call    ??$Get@$0CB@@StyleResolveChain@SVG@Mso@@QEBAAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; Mso::SVG::StyleResolveChain::Get<33>(void)
0x18010bd6a  mov     rdx, [rbp+var_38]
0x18010bd6e  mov     rbx, [rbp+var_40]
0x18010bd72  cmp     qword ptr [rax+10h], 0
0x18010bd77  jz      short loc_18010BD91
0x18010bd79  mov     rcx, [rsi+18h]
0x18010bd7d  mov     rdx, rax
0x18010bd80  mov     rcx, [rcx+40h]
0x18010bd84  call    ?QueryClipPath@Environment@SVG@Mso@@QEAAPEAVClipPathContext@23@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Mso::SVG::Environment::QueryClipPath(std::wstring const &)
0x18010bd89  mov     rdx, [rbp+var_38]
0x18010bd8d  mov     rbx, [rbp+var_40]
0x18010bd91  mov     rax, [rdx+10h]
0x18010bd95  test    rax, rax
0x18010bd98  jz      short loc_18010BDA2
0x18010bd9a  add     rax, 328h
0x18010bda0  jmp     short loc_18010BDB9
0x18010bda2  lea     rax, ?initial@?$StyleMetaData@$0BA@@SVG@Mso@@2V?$optional@W4FillMode@Path@Graphics@Mso@@@std@@B; std::optional<Mso::Graphics::Path::FillMode> const Mso::SVG::StyleMetaData<16>::initial
0x18010bda9  lea     rcx, ?inherit@?$StyleMetaData@$0BA@@SVG@Mso@@2V?$optional@W4FillMode@Path@Graphics@Mso@@@std@@B; std::optional<Mso::Graphics::Path::FillMode> const Mso::SVG::StyleMetaData<16>::inherit
0x18010bdb0  cmp     qword ptr [rdx+8], 0
0x18010bdb5  cmovnz  rax, rcx
0x18010bdb9  cmp     byte ptr [rax+4], 0
0x18010bdbd  jnz     short loc_18010BDDB
0x18010bdbf  test    rbx, rbx
0x18010bdc2  jz      short loc_18010BDCE
0x18010bdc4  mov     rcx, rbx
0x18010bdc7  call    ??$Get@$0BA@@StyleResolveChain@SVG@Mso@@QEBAAEBW4FillMode@Path@Graphics@2@XZ; Mso::SVG::StyleResolveChain::Get<16>(void)
0x18010bdcc  jmp     short loc_18010BDDB
0x18010bdce  mov     rdx, [rdx+8]
0x18010bdd2  lea     rcx, [rbp+var_40]
0x18010bdd6  call    ??$GetNormal@$0BA@@StyleResolveChain@SVG@Mso@@AEBAAEBW4FillMode@Path@Graphics@2@AEBVStyle@12@@Z; Mso::SVG::StyleResolveChain::GetNormal<16>(Mso::SVG::Style const &)
0x18010bddb  mov     r9d, [rax]
0x18010bdde  lea     r8, [rbp+var_40]
0x18010bde2  lea     rdx, [rbp+arg_0]
0x18010bde6  mov     rcx, rsi
0x18010bde9  call    ?GetEffectivePath@ShapeRenderer@SVG@Mso@@AEAA?AV?$TCntPtr@$$CBUIPath@GEL@@@3@AEBVStyleResolveChain@23@W4FillMode@Path@Graphics@3@@Z; Mso::SVG::ShapeRenderer::GetEffectivePath(Mso::SVG::StyleResolveChain const &,Mso::Graphics::Path::FillMode)
0x18010bdee  nop
0x18010bdef  mov     rbx, [rbp+arg_0]
0x18010bdf3  test    rbx, rbx
0x18010bdf6  jnz     short loc_18010BE32
0x18010bdf8  lea     rcx, [rbp+var_48]
0x18010bdfc  call    cs:__imp_?Create@IEmptyPath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@XZ; GEL::IEmptyPath::Create(void)
0x18010be02  mov     rcx, [rax]
0x18010be05  mov     [rdi], rcx
0x18010be08  test    rcx, rcx
0x18010be0b  jz      short loc_18010BE19
0x18010be0d  mov     rax, [rcx]
0x18010be10  mov     rax, [rax]
0x18010be13  call    cs:__guard_dispatch_icall_fptr
0x18010be19  mov     rcx, [rbp+var_48]
0x18010be1d  test    rcx, rcx
0x18010be20  jz      short loc_18010BE30
0x18010be22  mov     rax, [rcx]
0x18010be25  mov     rax, [rax+8]
0x18010be29  call    cs:__guard_dispatch_icall_fptr
0x18010be2f  nop
0x18010be30  jmp     short loc_18010BE9D
0x18010be32  test    rbx, rbx
0x18010be35  jz      loc_18010BEBD
0x18010be3b  mov     rax, [rbx]
0x18010be3e  lea     rdx, [rbp+var_28]
0x18010be42  mov     rcx, rbx
0x18010be45  mov     rax, [rax+68h]
0x18010be49  call    cs:__guard_dispatch_icall_fptr
0x18010be4f  mov     [rsp+80h+var_58], 0
0x18010be58  lea     rax, [rbp+var_28]
0x18010be5c  mov     [rsp+80h+var_60], rax
0x18010be61  lea     r9, [rbp+var_40]
0x18010be65  mov     r8, rbx
0x18010be68  lea     rdx, [rbp+var_48]
0x18010be6c  mov     rcx, rsi
0x18010be6f  call    ?ApplyStandardPathEffects@RenderableRenderer@SVG@Mso@@QEBA?AV?$TCntPtr@$$CBUIPath@GEL@@@3@AEBUIPath@GEL@@AEBVStyleResolveChain@23@PEBURect@6@PEBU?$TAffine3x3@N@Math@@@Z; Mso::SVG::RenderableRenderer::ApplyStandardPathEffects(GEL::IPath const &,Mso::SVG::StyleResolveChain const &,GEL::Rect const *,Math::TAffine3x3<double> const *)
0x18010be74  mov     r9b, 1; bool
0x18010be77  mov     r8, r15; struct GEL::Rect *
0x18010be7a  lea     rdx, [rbp+var_28]; struct GEL::Rect *
0x18010be7e  mov     rcx, rsi; this
0x18010be81  call    ?EndRendering@RenderableRenderer@SVG@Mso@@QEBAXAEBURect@GEL@@PEAU45@_N@Z; Mso::SVG::RenderableRenderer::EndRendering(GEL::Rect const &,GEL::Rect *,bool)
0x18010be86  mov     rax, [rbp+var_48]
0x18010be8a  mov     [rdi], rax
0x18010be8d  mov     rax, [rbx]
0x18010be90  mov     rcx, rbx
0x18010be93  mov     rax, [rax+8]
0x18010be97  call    cs:__guard_dispatch_icall_fptr
0x18010be9d  mov     rax, rdi
0x18010bea0  lea     r11, [rsp+80h+var_s0]
0x18010bea8  mov     rbx, [r11+28h]
0x18010beac  mov     rsi, [r11+30h]
0x18010beb0  mov     rdi, [r11+38h]
0x18010beb4  mov     rsp, r11
0x18010beb7  pop     r15
0x18010beb9  pop     r14
0x18010bebb  pop     rbp
0x18010bebc  retn
0x18010bebd  xor     edx, edx
0x18010bebf  mov     ecx, 1E3C3840h
0x18010bec4  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x18010beca  nop
0x18010becb  xor     edx, edx
0x18010becd  mov     ecx, 1E3C3843h
0x18010bed2  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
```
