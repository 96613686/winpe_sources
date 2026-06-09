# Mso::SVG::TextRenderer::ComputePath(Mso::SVG::StyleResolveChain const &,GEL::Rect *)

- ea: `0x180136110`
- end: `0x1801362ea`
- name: `?ComputePath@TextRenderer@SVG@Mso@@UEAA?AV?$TCntPtr@$$CBUIPath@GEL@@@3@AEBVStyleResolveChain@23@PEAURect@GEL@@@Z`
- size: `474`
- prototype: `__int64 __fastcall(Mso::SVG::TextRenderer *this)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x18000d5e0`
- `0x180041df8`
- `0x180041e94`
- `0x180043c28`
- `0x180132ba4`
- `0x1801360b4`
- `0x180136110`
- `0x18013e0c0`
- `0x18013f810`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1801362d5`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1801362e3`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1801362d5`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1801362e3`
- `gfx!?Create@IEmptyPath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@XZ` at `0x1801361f1`
- `gfx!?Create@IEmptyPath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@XZ` at `0x1801361f1`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Mso::SVG::TextRenderer::ComputePath(
        Mso::SVG::TextRenderer *this,
        __int64 a2,
        __int64 a3,
        struct GEL::Rect *a4)
{
  _QWORD *v8; // rsi
  __int64 v9; // rax
  __int64 v10; // rcx
  __int64 *v11; // rax
  bool v12; // zf
  __int64 *v13; // rax
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v17; // [rsp+50h] [rbp-1h] BYREF
  _QWORD v18[3]; // [rsp+58h] [rbp+7h] BYREF
  _OWORD v19[2]; // [rsp+70h] [rbp+1Fh] BYREF
  __int64 v20; // [rsp+B8h] [rbp+67h] BYREF

  v8 = (_QWORD *)*((_QWORD *)this + 2);
  if ( !v8 )
  {
LABEL_19:
    CrashWithRecovery(0x1E3C3843u, 0);
    JUMPOUT(0x1801362E9LL);
  }
  _castguard_slow_path_check_user_handled(*v8, 6792, 0);
  v9 = (*(__int64 (__fastcall **)(_QWORD *))(*v8 + 104LL))(v8);
  v18[0] = a3;
  v18[1] = v9;
  v18[2] = *(_QWORD *)(a3 + 16);
  memset(v19, 0, sizeof(v19));
  if ( !a4 )
  {
    v10 = *(_QWORD *)(v9 + 16);
    if ( v10 )
    {
      v11 = (__int64 *)(v10 + 392);
    }
    else if ( !*(_BYTE *)(v9 + 24) || (v12 = *(_QWORD *)(v9 + 8) == 0, v11 = Mso::SVG::StyleMetaData<33>::inherit, v12) )
    {
      v11 = (__int64 *)&Mso::SVG::StyleMetaData<33>::initial;
    }
    if ( !*((_BYTE *)v11 + 32) )
      v11 = (__int64 *)Mso::SVG::StyleResolveChain::Get<33>(a3);
    if ( v11[2] )
      Mso::SVG::Environment::QueryClipPath(*(_QWORD *)(*((_QWORD *)this + 3) + 64LL));
  }
  Mso::SVG::TextRenderer::ComputeBoundingBox(
    this,
    (const struct Mso::SVG::StyleResolveChain *)v18,
    (struct GEL::Rect *)v19);
  v13 = (__int64 *)GEL::IEmptyPath::Create(&v17);
  v14 = *v13;
  *v13 = 0;
  v20 = v14;
  if ( v17 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 8LL))(v17);
  v15 = *((_QWORD *)this + 10);
  if ( !v15 )
  {
    CrashWithRecovery(0x1E3C3840u, 0);
    goto LABEL_19;
  }
  Mso::SVG::TSpanRenderer::AnalyzeText(
    v15,
    v18,
    0,
    (__int64)v19,
    (__int64)Mso::SVG::TextRenderer::ComputePathTextItem,
    (__int64)&v20,
    0,
    0);
  Mso::SVG::RenderableRenderer::ApplyStandardPathEffects((_DWORD)this, a2, v20, (unsigned int)v18, (__int64)v19, 0);
  Mso::SVG::RenderableRenderer::EndRendering(this, (const struct GEL::Rect *)v19, a4, 1);
  if ( v20 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 8LL))(v20);
  return a2;
}

```

## disassembly

```asm
0x180136110  mov     rax, rsp
0x180136113  mov     [rax+10h], rbx
0x180136117  mov     [rax+18h], rsi
0x18013611b  mov     [rax+20h], rdi
0x18013611f  push    rbp
0x180136120  push    r14
0x180136122  push    r15
0x180136124  lea     rbp, [rax-5Fh]
0x180136128  sub     rsp, 90h
0x18013612f  mov     r15, r9
0x180136132  mov     r14, r8
0x180136135  mov     rdi, rdx
0x180136138  mov     rbx, rcx
0x18013613b  mov     rsi, [rcx+10h]
0x18013613f  test    rsi, rsi
0x180136142  jz      loc_1801362DC
0x180136148  xor     r8d, r8d
0x18013614b  mov     edx, 1A88h
0x180136150  mov     rcx, [rsi]
0x180136153  call    __castguard_slow_path_check_user_handled
0x180136158  mov     rax, [rsi]
0x18013615b  mov     rcx, rsi
0x18013615e  mov     rax, [rax+68h]
0x180136162  call    cs:__guard_dispatch_icall_fptr
0x180136168  mov     [rbp+57h+var_50], r14
0x18013616c  mov     [rbp+57h+var_48], rax
0x180136170  mov     rcx, [r14+10h]
0x180136174  mov     [rbp+57h+var_40], rcx
0x180136178  xorps   xmm0, xmm0
0x18013617b  movups  [rbp+57h+var_38], xmm0
0x18013617f  xorps   xmm1, xmm1
0x180136182  movups  [rbp+57h+var_28], xmm1
0x180136186  test    r15, r15
0x180136189  jnz     short loc_1801361DD
0x18013618b  mov     rcx, [rax+10h]
0x18013618f  test    rcx, rcx
0x180136192  jz      short loc_18013619D
0x180136194  lea     rax, [rcx+188h]
0x18013619b  jmp     short loc_1801361B8
0x18013619d  cmp     byte ptr [rax+18h], 0
0x1801361a1  jz      short loc_1801361B1
0x1801361a3  cmp     qword ptr [rax+8], 0
0x1801361a8  lea     rax, ?inherit@?$StyleMetaData@$0CB@@SVG@Mso@@2V?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@B; std::optional<std::wstring> const Mso::SVG::StyleMetaData<33>::inherit
0x1801361af  jnz     short loc_1801361B8
0x1801361b1  lea     rax, ?initial@?$StyleMetaData@$0CB@@SVG@Mso@@2V?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@B; std::optional<std::wstring> const Mso::SVG::StyleMetaData<33>::initial
0x1801361b8  cmp     byte ptr [rax+20h], 0
0x1801361bc  jnz     short loc_1801361C6
0x1801361be  mov     rcx, r14
0x1801361c1  call    ??$Get@$0CB@@StyleResolveChain@SVG@Mso@@QEBAAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; Mso::SVG::StyleResolveChain::Get<33>(void)
0x1801361c6  cmp     qword ptr [rax+10h], 0
0x1801361cb  jz      short loc_1801361DD
0x1801361cd  mov     rcx, [rbx+18h]
0x1801361d1  mov     rdx, rax
0x1801361d4  mov     rcx, [rcx+40h]
0x1801361d8  call    ?QueryClipPath@Environment@SVG@Mso@@QEAAPEAVClipPathContext@23@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Mso::SVG::Environment::QueryClipPath(std::wstring const &)
0x1801361dd  lea     r8, [rbp+57h+var_38]; struct GEL::Rect *
0x1801361e1  lea     rdx, [rbp+57h+var_50]; struct Mso::SVG::StyleResolveChain *
0x1801361e5  mov     rcx, rbx; this
0x1801361e8  call    ?ComputeBoundingBox@TextRenderer@SVG@Mso@@AEAAXAEBVStyleResolveChain@23@PEAURect@GEL@@@Z; Mso::SVG::TextRenderer::ComputeBoundingBox(Mso::SVG::StyleResolveChain const &,GEL::Rect *)
0x1801361ed  lea     rcx, [rbp+57h+var_58]
0x1801361f1  call    cs:__imp_?Create@IEmptyPath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@XZ; GEL::IEmptyPath::Create(void)
0x1801361f7  mov     rcx, [rax]
0x1801361fa  mov     qword ptr [rax], 0
0x180136201  mov     [rbp+57h+arg_0], rcx
0x180136205  mov     rcx, [rbp+57h+var_58]
0x180136209  test    rcx, rcx
0x18013620c  jz      short loc_18013621C
0x18013620e  mov     rax, [rcx]
0x180136211  mov     rax, [rax+8]
0x180136215  call    cs:__guard_dispatch_icall_fptr
0x18013621b  nop
0x18013621c  mov     rcx, [rbx+50h]
0x180136220  test    rcx, rcx
0x180136223  jz      loc_1801362CE
0x180136229  mov     [rsp+0A0h+var_68], 0
0x180136232  mov     [rsp+0A0h+var_70], 0
0x18013623b  lea     rax, [rbp+57h+arg_0]
0x18013623f  mov     [rsp+0A0h+var_78], rax
0x180136244  lea     rax, ?ComputePathTextItem@TextRenderer@SVG@Mso@@CAXPEAXAEBUTextChunkItem@23@W4TextAnchor@23@AEBUFont@GEL@@AEBUtag_SCRIPT_ANALYSIS@@PEB_WI_N6AEBV?$vector@GV?$allocator@G@std@@@std@@AEBV?$vector@MV?$allocator@M@std@@@std@@8AEBV?$vector@UVector@GEL@@V?$allocator@UVector@GEL@@@std@@@std@@MMMM7AEBU?$TAffine3x3@N@Math@@AEBUTextRenderingParams@23@@Z; Mso::SVG::TextRenderer::ComputePathTextItem(void *,Mso::SVG::TextChunkItem const &,Mso::SVG::TextAnchor,GEL::Font const &,tag_SCRIPT_ANALYSIS const &,wchar_t const *,uint,bool,bool,std::vector<ushort> const &,std::vector<float> const &,std::vector<float> const &,std::vector<GEL::Vector> const &,float,float,float,float,std::vector<ushort> const &,Math::TAffine3x3<double> const &,Mso::SVG::TextRenderingParams const &)
0x18013624b  mov     [rsp+0A0h+var_80], rax
0x180136250  lea     r9, [rbp+57h+var_38]
0x180136254  xor     r8d, r8d
0x180136257  lea     rdx, [rbp+57h+var_50]
0x18013625b  call    ?AnalyzeText@TSpanRenderer@SVG@Mso@@QEAAXAEBVStyleResolveChain@23@_NPEBURect@GEL@@P6AXPEAXAEBUTextChunkItem@23@W4TextAnchor@23@AEBUFont@6@AEBUtag_SCRIPT_ANALYSIS@@PEB_WI11AEBV?$vector@GV?$allocator@G@std@@@std@@AEBV?$vector@MV?$allocator@M@std@@@std@@AEBV?$vector@MV?$allocator@M@std@@@std@@AEBV?$vector@UVector@GEL@@V?$allocator@UVector@GEL@@@std@@@std@@MMMM9AEBU?$TAffine3x3@N@Math@@AEBUTextRenderingParams@23@@Z3PEBUIColorResolver@6@PEBUTextRenderingParams@23@@Z; Mso::SVG::TSpanRenderer::AnalyzeText(Mso::SVG::StyleResolveChain const &,bool,GEL::Rect const *,void (*)(void *,Mso::SVG::TextChunkItem const &,Mso::SVG::TextAnchor,GEL::Font const &,tag_SCRIPT_ANALYSIS const &,wchar_t const *,uint,bool,bool,std::vector<ushort> const &,std::vector<float> const &,std::vector<float> const &,std::vector<GEL::Vector> const &,float,float,float,float,std::vector<ushort> const &,Math::TAffine3x3<double> const &,Mso::SVG::TextRenderingParams const &),void *,GEL::IColorResolver const *,Mso::SVG::TextRenderingParams const *)
0x180136260  mov     [rsp+0A0h+var_78], 0
0x180136269  lea     rax, [rbp+57h+var_38]
0x18013626d  mov     [rsp+0A0h+var_80], rax
0x180136272  lea     r9, [rbp+57h+var_50]
0x180136276  mov     r8, [rbp+57h+arg_0]
0x18013627a  mov     rdx, rdi
0x18013627d  mov     rcx, rbx
0x180136280  call    ?ApplyStandardPathEffects@RenderableRenderer@SVG@Mso@@QEBA?AV?$TCntPtr@$$CBUIPath@GEL@@@3@AEBUIPath@GEL@@AEBVStyleResolveChain@23@PEBURect@6@PEBU?$TAffine3x3@N@Math@@@Z; Mso::SVG::RenderableRenderer::ApplyStandardPathEffects(GEL::IPath const &,Mso::SVG::StyleResolveChain const &,GEL::Rect const *,Math::TAffine3x3<double> const *)
0x180136285  mov     r9b, 1; bool
0x180136288  mov     r8, r15; struct GEL::Rect *
0x18013628b  lea     rdx, [rbp+57h+var_38]; struct GEL::Rect *
0x18013628f  mov     rcx, rbx; this
0x180136292  call    ?EndRendering@RenderableRenderer@SVG@Mso@@QEBAXAEBURect@GEL@@PEAU45@_N@Z; Mso::SVG::RenderableRenderer::EndRendering(GEL::Rect const &,GEL::Rect *,bool)
0x180136297  nop
0x180136298  mov     rcx, [rbp+57h+arg_0]
0x18013629c  test    rcx, rcx
0x18013629f  jz      short loc_1801362AE
0x1801362a1  mov     rax, [rcx]
0x1801362a4  mov     rax, [rax+8]
0x1801362a8  call    cs:__guard_dispatch_icall_fptr
0x1801362ae  mov     rax, rdi
0x1801362b1  lea     r11, [rsp+0A0h+var_10]
0x1801362b9  mov     rbx, [r11+28h]
0x1801362bd  mov     rsi, [r11+30h]
0x1801362c1  mov     rdi, [r11+38h]
0x1801362c5  mov     rsp, r11
0x1801362c8  pop     r15
0x1801362ca  pop     r14
0x1801362cc  pop     rbp
0x1801362cd  retn
0x1801362ce  xor     edx, edx
0x1801362d0  mov     ecx, 1E3C3840h
0x1801362d5  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1801362db  nop
0x1801362dc  xor     edx, edx
0x1801362de  mov     ecx, 1E3C3843h
0x1801362e3  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
```
