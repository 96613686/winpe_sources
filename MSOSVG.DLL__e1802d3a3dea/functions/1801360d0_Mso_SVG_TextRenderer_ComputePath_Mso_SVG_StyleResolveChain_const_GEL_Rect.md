# Mso::SVG::TextRenderer::ComputePath(Mso::SVG::StyleResolveChain const &,GEL::Rect *)

- ea: `0x1801360d0`
- end: `0x1801362aa`
- name: `?ComputePath@TextRenderer@SVG@Mso@@UEAA?AV?$TCntPtr@$$CBUIPath@GEL@@@3@AEBVStyleResolveChain@23@PEAURect@GEL@@@Z`
- size: `474`
- prototype: `__int64 __fastcall(Mso::SVG::TextRenderer *this)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x18000d5e0`
- `0x180041de0`
- `0x180041e7c`
- `0x180043c10`
- `0x180132b64`
- `0x180136074`
- `0x1801360d0`
- `0x18013e010`
- `0x18013f760`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180136295`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1801362a3`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180136295`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1801362a3`
- `gfx!?Create@IEmptyPath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@XZ` at `0x1801361b1`
- `gfx!?Create@IEmptyPath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@XZ` at `0x1801361b1`

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
    JUMPOUT(0x1801362A9LL);
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
    (unsigned int)v18,
    0,
    (unsigned int)v19,
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
0x1801360d0  mov     rax, rsp
0x1801360d3  mov     [rax+10h], rbx
0x1801360d7  mov     [rax+18h], rsi
0x1801360db  mov     [rax+20h], rdi
0x1801360df  push    rbp
0x1801360e0  push    r14
0x1801360e2  push    r15
0x1801360e4  lea     rbp, [rax-5Fh]
0x1801360e8  sub     rsp, 90h
0x1801360ef  mov     r15, r9
0x1801360f2  mov     r14, r8
0x1801360f5  mov     rdi, rdx
0x1801360f8  mov     rbx, rcx
0x1801360fb  mov     rsi, [rcx+10h]
0x1801360ff  test    rsi, rsi
0x180136102  jz      loc_18013629C
0x180136108  xor     r8d, r8d
0x18013610b  mov     edx, 1A88h
0x180136110  mov     rcx, [rsi]
0x180136113  call    __castguard_slow_path_check_user_handled
0x180136118  mov     rax, [rsi]
0x18013611b  mov     rcx, rsi
0x18013611e  mov     rax, [rax+68h]
0x180136122  call    cs:__guard_dispatch_icall_fptr
0x180136128  mov     [rbp+57h+var_50], r14
0x18013612c  mov     [rbp+57h+var_48], rax
0x180136130  mov     rcx, [r14+10h]
0x180136134  mov     [rbp+57h+var_40], rcx
0x180136138  xorps   xmm0, xmm0
0x18013613b  movups  [rbp+57h+var_38], xmm0
0x18013613f  xorps   xmm1, xmm1
0x180136142  movups  [rbp+57h+var_28], xmm1
0x180136146  test    r15, r15
0x180136149  jnz     short loc_18013619D
0x18013614b  mov     rcx, [rax+10h]
0x18013614f  test    rcx, rcx
0x180136152  jz      short loc_18013615D
0x180136154  lea     rax, [rcx+188h]
0x18013615b  jmp     short loc_180136178
0x18013615d  cmp     byte ptr [rax+18h], 0
0x180136161  jz      short loc_180136171
0x180136163  cmp     qword ptr [rax+8], 0
0x180136168  lea     rax, ?inherit@?$StyleMetaData@$0CB@@SVG@Mso@@2V?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@B; std::optional<std::wstring> const Mso::SVG::StyleMetaData<33>::inherit
0x18013616f  jnz     short loc_180136178
0x180136171  lea     rax, ?initial@?$StyleMetaData@$0CB@@SVG@Mso@@2V?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@B; std::optional<std::wstring> const Mso::SVG::StyleMetaData<33>::initial
0x180136178  cmp     byte ptr [rax+20h], 0
0x18013617c  jnz     short loc_180136186
0x18013617e  mov     rcx, r14
0x180136181  call    ??$Get@$0CB@@StyleResolveChain@SVG@Mso@@QEBAAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; Mso::SVG::StyleResolveChain::Get<33>(void)
0x180136186  cmp     qword ptr [rax+10h], 0
0x18013618b  jz      short loc_18013619D
0x18013618d  mov     rcx, [rbx+18h]
0x180136191  mov     rdx, rax
0x180136194  mov     rcx, [rcx+40h]
0x180136198  call    ?QueryClipPath@Environment@SVG@Mso@@QEAAPEAVClipPathContext@23@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Mso::SVG::Environment::QueryClipPath(std::wstring const &)
0x18013619d  lea     r8, [rbp+57h+var_38]; struct GEL::Rect *
0x1801361a1  lea     rdx, [rbp+57h+var_50]; struct Mso::SVG::StyleResolveChain *
0x1801361a5  mov     rcx, rbx; this
0x1801361a8  call    ?ComputeBoundingBox@TextRenderer@SVG@Mso@@AEAAXAEBVStyleResolveChain@23@PEAURect@GEL@@@Z; Mso::SVG::TextRenderer::ComputeBoundingBox(Mso::SVG::StyleResolveChain const &,GEL::Rect *)
0x1801361ad  lea     rcx, [rbp+57h+var_58]
0x1801361b1  call    cs:__imp_?Create@IEmptyPath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@XZ; GEL::IEmptyPath::Create(void)
0x1801361b7  mov     rcx, [rax]
0x1801361ba  mov     qword ptr [rax], 0
0x1801361c1  mov     [rbp+57h+arg_0], rcx
0x1801361c5  mov     rcx, [rbp+57h+var_58]
0x1801361c9  test    rcx, rcx
0x1801361cc  jz      short loc_1801361DC
0x1801361ce  mov     rax, [rcx]
0x1801361d1  mov     rax, [rax+8]
0x1801361d5  call    cs:__guard_dispatch_icall_fptr
0x1801361db  nop
0x1801361dc  mov     rcx, [rbx+50h]
0x1801361e0  test    rcx, rcx
0x1801361e3  jz      loc_18013628E
0x1801361e9  mov     [rsp+0A0h+var_68], 0
0x1801361f2  mov     [rsp+0A0h+var_70], 0
0x1801361fb  lea     rax, [rbp+57h+arg_0]
0x1801361ff  mov     [rsp+0A0h+var_78], rax
0x180136204  lea     rax, ?ComputePathTextItem@TextRenderer@SVG@Mso@@CAXPEAXAEBUTextChunkItem@23@W4TextAnchor@23@AEBUFont@GEL@@AEBUtag_SCRIPT_ANALYSIS@@PEB_WI_N6AEBV?$vector@GV?$allocator@G@std@@@std@@AEBV?$vector@MV?$allocator@M@std@@@std@@8AEBV?$vector@UVector@GEL@@V?$allocator@UVector@GEL@@@std@@@std@@MMMM7AEBU?$TAffine3x3@N@Math@@AEBUTextRenderingParams@23@@Z; Mso::SVG::TextRenderer::ComputePathTextItem(void *,Mso::SVG::TextChunkItem const &,Mso::SVG::TextAnchor,GEL::Font const &,tag_SCRIPT_ANALYSIS const &,wchar_t const *,uint,bool,bool,std::vector<ushort> const &,std::vector<float> const &,std::vector<float> const &,std::vector<GEL::Vector> const &,float,float,float,float,std::vector<ushort> const &,Math::TAffine3x3<double> const &,Mso::SVG::TextRenderingParams const &)
0x18013620b  mov     [rsp+0A0h+var_80], rax
0x180136210  lea     r9, [rbp+57h+var_38]
0x180136214  xor     r8d, r8d
0x180136217  lea     rdx, [rbp+57h+var_50]
0x18013621b  call    ?AnalyzeText@TSpanRenderer@SVG@Mso@@QEAAXAEBVStyleResolveChain@23@_NPEBURect@GEL@@P6AXPEAXAEBUTextChunkItem@23@W4TextAnchor@23@AEBUFont@6@AEBUtag_SCRIPT_ANALYSIS@@PEB_WI11AEBV?$vector@GV?$allocator@G@std@@@std@@AEBV?$vector@MV?$allocator@M@std@@@std@@AEBV?$vector@MV?$allocator@M@std@@@std@@AEBV?$vector@UVector@GEL@@V?$allocator@UVector@GEL@@@std@@@std@@MMMM9AEBU?$TAffine3x3@N@Math@@AEBUTextRenderingParams@23@@Z3PEBUIColorResolver@6@PEBUTextRenderingParams@23@@Z; Mso::SVG::TSpanRenderer::AnalyzeText(Mso::SVG::StyleResolveChain const &,bool,GEL::Rect const *,void (*)(void *,Mso::SVG::TextChunkItem const &,Mso::SVG::TextAnchor,GEL::Font const &,tag_SCRIPT_ANALYSIS const &,wchar_t const *,uint,bool,bool,std::vector<ushort> const &,std::vector<float> const &,std::vector<float> const &,std::vector<GEL::Vector> const &,float,float,float,float,std::vector<ushort> const &,Math::TAffine3x3<double> const &,Mso::SVG::TextRenderingParams const &),void *,GEL::IColorResolver const *,Mso::SVG::TextRenderingParams const *)
0x180136220  mov     [rsp+0A0h+var_78], 0
0x180136229  lea     rax, [rbp+57h+var_38]
0x18013622d  mov     [rsp+0A0h+var_80], rax
0x180136232  lea     r9, [rbp+57h+var_50]
0x180136236  mov     r8, [rbp+57h+arg_0]
0x18013623a  mov     rdx, rdi
0x18013623d  mov     rcx, rbx
0x180136240  call    ?ApplyStandardPathEffects@RenderableRenderer@SVG@Mso@@QEBA?AV?$TCntPtr@$$CBUIPath@GEL@@@3@AEBUIPath@GEL@@AEBVStyleResolveChain@23@PEBURect@6@PEBU?$TAffine3x3@N@Math@@@Z; Mso::SVG::RenderableRenderer::ApplyStandardPathEffects(GEL::IPath const &,Mso::SVG::StyleResolveChain const &,GEL::Rect const *,Math::TAffine3x3<double> const *)
0x180136245  mov     r9b, 1; bool
0x180136248  mov     r8, r15; struct GEL::Rect *
0x18013624b  lea     rdx, [rbp+57h+var_38]; struct GEL::Rect *
0x18013624f  mov     rcx, rbx; this
0x180136252  call    ?EndRendering@RenderableRenderer@SVG@Mso@@QEBAXAEBURect@GEL@@PEAU45@_N@Z; Mso::SVG::RenderableRenderer::EndRendering(GEL::Rect const &,GEL::Rect *,bool)
0x180136257  nop
0x180136258  mov     rcx, [rbp+57h+arg_0]
0x18013625c  test    rcx, rcx
0x18013625f  jz      short loc_18013626E
0x180136261  mov     rax, [rcx]
0x180136264  mov     rax, [rax+8]
0x180136268  call    cs:__guard_dispatch_icall_fptr
0x18013626e  mov     rax, rdi
0x180136271  lea     r11, [rsp+0A0h+var_10]
0x180136279  mov     rbx, [r11+28h]
0x18013627d  mov     rsi, [r11+30h]
0x180136281  mov     rdi, [r11+38h]
0x180136285  mov     rsp, r11
0x180136288  pop     r15
0x18013628a  pop     r14
0x18013628c  pop     rbp
0x18013628d  retn
0x18013628e  xor     edx, edx
0x180136290  mov     ecx, 1E3C3840h
0x180136295  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x18013629b  nop
0x18013629c  xor     edx, edx
0x18013629e  mov     ecx, 1E3C3843h
0x1801362a3  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
```
