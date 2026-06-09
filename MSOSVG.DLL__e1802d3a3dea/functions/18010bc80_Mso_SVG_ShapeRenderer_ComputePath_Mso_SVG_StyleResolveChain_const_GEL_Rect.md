# Mso::SVG::ShapeRenderer::ComputePath(Mso::SVG::StyleResolveChain const &,GEL::Rect *)

- ea: `0x18010bc80`
- end: `0x18010bea9`
- name: `?ComputePath@ShapeRenderer@SVG@Mso@@UEAA?AV?$TCntPtr@$$CBUIPath@GEL@@@3@AEBVStyleResolveChain@23@PEAURect@GEL@@@Z`
- size: `553`
- prototype: `__int64 __fastcall(Mso::SVG::RenderableRenderer *this)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x18000d5e0`
- `0x180041de0`
- `0x180041e7c`
- `0x180043c10`
- `0x18010b9b8`
- `0x18010bc80`
- `0x18010d18c`
- `0x18010d59c`
- `0x18013e010`
- `0x18013f760`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18010be94`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18010bea2`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18010be94`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18010bea2`
- `gfx!?Create@IEmptyPath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@XZ` at `0x18010bdcc`
- `gfx!?Create@IEmptyPath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@XZ` at `0x18010bdcc`

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
    JUMPOUT(0x18010BEA8LL);
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
0x18010bc80  mov     [rsp-18h+arg_8], rbx
0x18010bc85  mov     [rsp-18h+arg_10], rsi
0x18010bc8a  mov     [rsp-18h+arg_18], rdi
0x18010bc8f  push    rbp
0x18010bc90  push    r14
0x18010bc92  push    r15
0x18010bc94  mov     rbp, rsp
0x18010bc97  sub     rsp, 80h
0x18010bc9e  mov     r15, r9
0x18010bca1  mov     rbx, r8
0x18010bca4  mov     rdi, rdx
0x18010bca7  mov     rsi, rcx
0x18010bcaa  mov     r14, [rcx+10h]
0x18010bcae  test    r14, r14
0x18010bcb1  jz      loc_18010BE9B
0x18010bcb7  mov     edx, 0F80h
0x18010bcbc  mov     r8d, 320h
0x18010bcc2  mov     rcx, [r14]
0x18010bcc5  call    __castguard_slow_path_check_user_handled
0x18010bcca  mov     rax, [r14]
0x18010bccd  mov     rcx, r14
0x18010bcd0  mov     rax, [rax+68h]
0x18010bcd4  call    cs:__guard_dispatch_icall_fptr
0x18010bcda  mov     rdx, rax
0x18010bcdd  mov     [rbp+var_40], rbx
0x18010bce1  mov     [rbp+var_38], rax
0x18010bce5  mov     rax, [rbx+10h]
0x18010bce9  mov     [rbp+var_30], rax
0x18010bced  xorps   xmm0, xmm0
0x18010bcf0  movups  [rbp+var_28], xmm0
0x18010bcf4  xorps   xmm1, xmm1
0x18010bcf7  movups  [rbp+var_18], xmm1
0x18010bcfb  test    r15, r15
0x18010bcfe  jnz     short loc_18010BD61
0x18010bd00  mov     rax, [rdx+10h]
0x18010bd04  test    rax, rax
0x18010bd07  jz      short loc_18010BD11
0x18010bd09  add     rax, 188h
0x18010bd0f  jmp     short loc_18010BD2C
0x18010bd11  cmp     byte ptr [rdx+18h], 0
0x18010bd15  jz      short loc_18010BD25
0x18010bd17  cmp     qword ptr [rdx+8], 0
0x18010bd1c  lea     rax, ?inherit@?$StyleMetaData@$0CB@@SVG@Mso@@2V?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@B; std::optional<std::wstring> const Mso::SVG::StyleMetaData<33>::inherit
0x18010bd23  jnz     short loc_18010BD2C
0x18010bd25  lea     rax, ?initial@?$StyleMetaData@$0CB@@SVG@Mso@@2V?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@B; std::optional<std::wstring> const Mso::SVG::StyleMetaData<33>::initial
0x18010bd2c  cmp     byte ptr [rax+20h], 0
0x18010bd30  jnz     short loc_18010BD42
0x18010bd32  mov     rcx, rbx
0x18010bd35  call    ??$Get@$0CB@@StyleResolveChain@SVG@Mso@@QEBAAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; Mso::SVG::StyleResolveChain::Get<33>(void)
0x18010bd3a  mov     rdx, [rbp+var_38]
0x18010bd3e  mov     rbx, [rbp+var_40]
0x18010bd42  cmp     qword ptr [rax+10h], 0
0x18010bd47  jz      short loc_18010BD61
0x18010bd49  mov     rcx, [rsi+18h]
0x18010bd4d  mov     rdx, rax
0x18010bd50  mov     rcx, [rcx+40h]
0x18010bd54  call    ?QueryClipPath@Environment@SVG@Mso@@QEAAPEAVClipPathContext@23@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Mso::SVG::Environment::QueryClipPath(std::wstring const &)
0x18010bd59  mov     rdx, [rbp+var_38]
0x18010bd5d  mov     rbx, [rbp+var_40]
0x18010bd61  mov     rax, [rdx+10h]
0x18010bd65  test    rax, rax
0x18010bd68  jz      short loc_18010BD72
0x18010bd6a  add     rax, 328h
0x18010bd70  jmp     short loc_18010BD89
0x18010bd72  lea     rax, ?initial@?$StyleMetaData@$0BA@@SVG@Mso@@2V?$optional@W4FillMode@Path@Graphics@Mso@@@std@@B; std::optional<Mso::Graphics::Path::FillMode> const Mso::SVG::StyleMetaData<16>::initial
0x18010bd79  lea     rcx, ?inherit@?$StyleMetaData@$0BA@@SVG@Mso@@2V?$optional@W4FillMode@Path@Graphics@Mso@@@std@@B; std::optional<Mso::Graphics::Path::FillMode> const Mso::SVG::StyleMetaData<16>::inherit
0x18010bd80  cmp     qword ptr [rdx+8], 0
0x18010bd85  cmovnz  rax, rcx
0x18010bd89  cmp     byte ptr [rax+4], 0
0x18010bd8d  jnz     short loc_18010BDAB
0x18010bd8f  test    rbx, rbx
0x18010bd92  jz      short loc_18010BD9E
0x18010bd94  mov     rcx, rbx
0x18010bd97  call    ??$Get@$0BA@@StyleResolveChain@SVG@Mso@@QEBAAEBW4FillMode@Path@Graphics@2@XZ; Mso::SVG::StyleResolveChain::Get<16>(void)
0x18010bd9c  jmp     short loc_18010BDAB
0x18010bd9e  mov     rdx, [rdx+8]
0x18010bda2  lea     rcx, [rbp+var_40]
0x18010bda6  call    ??$GetNormal@$0BA@@StyleResolveChain@SVG@Mso@@AEBAAEBW4FillMode@Path@Graphics@2@AEBVStyle@12@@Z; Mso::SVG::StyleResolveChain::GetNormal<16>(Mso::SVG::Style const &)
0x18010bdab  mov     r9d, [rax]
0x18010bdae  lea     r8, [rbp+var_40]
0x18010bdb2  lea     rdx, [rbp+arg_0]
0x18010bdb6  mov     rcx, rsi
0x18010bdb9  call    ?GetEffectivePath@ShapeRenderer@SVG@Mso@@AEAA?AV?$TCntPtr@$$CBUIPath@GEL@@@3@AEBVStyleResolveChain@23@W4FillMode@Path@Graphics@3@@Z; Mso::SVG::ShapeRenderer::GetEffectivePath(Mso::SVG::StyleResolveChain const &,Mso::Graphics::Path::FillMode)
0x18010bdbe  nop
0x18010bdbf  mov     rbx, [rbp+arg_0]
0x18010bdc3  test    rbx, rbx
0x18010bdc6  jnz     short loc_18010BE02
0x18010bdc8  lea     rcx, [rbp+var_48]
0x18010bdcc  call    cs:__imp_?Create@IEmptyPath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@XZ; GEL::IEmptyPath::Create(void)
0x18010bdd2  mov     rcx, [rax]
0x18010bdd5  mov     [rdi], rcx
0x18010bdd8  test    rcx, rcx
0x18010bddb  jz      short loc_18010BDE9
0x18010bddd  mov     rax, [rcx]
0x18010bde0  mov     rax, [rax]
0x18010bde3  call    cs:__guard_dispatch_icall_fptr
0x18010bde9  mov     rcx, [rbp+var_48]
0x18010bded  test    rcx, rcx
0x18010bdf0  jz      short loc_18010BE00
0x18010bdf2  mov     rax, [rcx]
0x18010bdf5  mov     rax, [rax+8]
0x18010bdf9  call    cs:__guard_dispatch_icall_fptr
0x18010bdff  nop
0x18010be00  jmp     short loc_18010BE6D
0x18010be02  test    rbx, rbx
0x18010be05  jz      loc_18010BE8D
0x18010be0b  mov     rax, [rbx]
0x18010be0e  lea     rdx, [rbp+var_28]
0x18010be12  mov     rcx, rbx
0x18010be15  mov     rax, [rax+68h]
0x18010be19  call    cs:__guard_dispatch_icall_fptr
0x18010be1f  mov     [rsp+80h+var_58], 0
0x18010be28  lea     rax, [rbp+var_28]
0x18010be2c  mov     [rsp+80h+var_60], rax
0x18010be31  lea     r9, [rbp+var_40]
0x18010be35  mov     r8, rbx
0x18010be38  lea     rdx, [rbp+var_48]
0x18010be3c  mov     rcx, rsi
0x18010be3f  call    ?ApplyStandardPathEffects@RenderableRenderer@SVG@Mso@@QEBA?AV?$TCntPtr@$$CBUIPath@GEL@@@3@AEBUIPath@GEL@@AEBVStyleResolveChain@23@PEBURect@6@PEBU?$TAffine3x3@N@Math@@@Z; Mso::SVG::RenderableRenderer::ApplyStandardPathEffects(GEL::IPath const &,Mso::SVG::StyleResolveChain const &,GEL::Rect const *,Math::TAffine3x3<double> const *)
0x18010be44  mov     r9b, 1; bool
0x18010be47  mov     r8, r15; struct GEL::Rect *
0x18010be4a  lea     rdx, [rbp+var_28]; struct GEL::Rect *
0x18010be4e  mov     rcx, rsi; this
0x18010be51  call    ?EndRendering@RenderableRenderer@SVG@Mso@@QEBAXAEBURect@GEL@@PEAU45@_N@Z; Mso::SVG::RenderableRenderer::EndRendering(GEL::Rect const &,GEL::Rect *,bool)
0x18010be56  mov     rax, [rbp+var_48]
0x18010be5a  mov     [rdi], rax
0x18010be5d  mov     rax, [rbx]
0x18010be60  mov     rcx, rbx
0x18010be63  mov     rax, [rax+8]
0x18010be67  call    cs:__guard_dispatch_icall_fptr
0x18010be6d  mov     rax, rdi
0x18010be70  lea     r11, [rsp+80h+var_s0]
0x18010be78  mov     rbx, [r11+28h]
0x18010be7c  mov     rsi, [r11+30h]
0x18010be80  mov     rdi, [r11+38h]
0x18010be84  mov     rsp, r11
0x18010be87  pop     r15
0x18010be89  pop     r14
0x18010be8b  pop     rbp
0x18010be8c  retn
0x18010be8d  xor     edx, edx
0x18010be8f  mov     ecx, 1E3C3840h
0x18010be94  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x18010be9a  nop
0x18010be9b  xor     edx, edx
0x18010be9d  mov     ecx, 1E3C3843h
0x18010bea2  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
```
