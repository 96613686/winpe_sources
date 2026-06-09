# Mso::SVG::TextRenderer::RenderTextItem(void *,Mso::SVG::TextChunkItem const &,Mso::SVG::TextAnchor,GEL::Font const &,tag_SCRIPT_ANALYSIS const &,wchar_t const *,uint,bool,bool,std::vector<ushort,std::allocator<ushort>> const &,std::vector<float,std::allocator<float>> const &,std::vector<float,std::allocator<float>> const &,std::vector<GEL::Vector,std::allocator<GEL::Vector>> const &,float,float,float,float,std::vector<ushort,std::allocator<ushort>> const &,Math::TAffine3x3<double> const &,Mso::SVG::TextRenderingParams const &)

- ea: `0x180133530`
- end: `0x180133aac`
- name: `?RenderTextItem@TextRenderer@SVG@Mso@@CAXPEAXAEBUTextChunkItem@23@W4TextAnchor@23@AEBUFont@GEL@@AEBUtag_SCRIPT_ANALYSIS@@PEB_WI_N6AEBV?$vector@GV?$allocator@G@std@@@std@@AEBV?$vector@MV?$allocator@M@std@@@std@@8AEBV?$vector@UVector@GEL@@V?$allocator@UVector@GEL@@@std@@@std@@MMMM7AEBU?$TAffine3x3@N@Math@@AEBUTextRenderingParams@23@@Z`
- size: `1404`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x18003fd34`
- `0x18004e640`
- `0x18004e740`
- `0x180132fec`
- `0x180133248`
- `0x180133530`
- `0x18013f760`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1801336a9`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180133aa5`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1801336a9`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180133aa5`
- `gfx!?Create@IEffectGlyphs@GEL@@SA?AV?$TCntPtr@UIEffectGlyphs@GEL@@@Ofc@@AEBUtag_SCRIPT_ANALYSIS@@PEB_WIPEBGIPEBM3PEBUVector@2@MMMAEBUFont@2@PEBUIBrush@2@PEBUIPen@2@6IK2N@Z` at `0x180133817`
- `gfx!?Create@IEffectGlyphs@GEL@@SA?AV?$TCntPtr@UIEffectGlyphs@GEL@@@Ofc@@AEBUtag_SCRIPT_ANALYSIS@@PEB_WIPEBGIPEBM3PEBUVector@2@MMMAEBUFont@2@PEBUIBrush@2@PEBUIPen@2@6IK2N@Z` at `0x180133817`
- `gfx!?Create@IEffectContainer@GEL@@SA?AV?$TCntPtr@UIEffectContainer@GEL@@@Ofc@@XZ` at `0x1801338ba`
- `gfx!?Create@IEffectContainer@GEL@@SA?AV?$TCntPtr@UIEffectContainer@GEL@@@Ofc@@XZ` at `0x1801338ba`
- `gfx!?GetDefaultTypefaces@ITypefaceList@GEL@@SAAEAU12@XZ` at `0x180133570`
- `gfx!?GetDefaultTypefaces@ITypefaceList@GEL@@SAAEAU12@XZ` at `0x180133570`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
void __fastcall Mso::SVG::TextRenderer::RenderTextItem(
        GEL::EffectAccumulator *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned __int16 *a5,
        __int64 a6,
        unsigned int a7,
        __int64 a8,
        __int64 a9,
        _QWORD *a10,
        _QWORD *a11,
        _QWORD *a12,
        _QWORD *a13,
        float a14,
        int a15,
        int a16,
        float a17,
        __int64 *a18,
        __int64 a19)
{
  struct GEL::IEffect *DefaultTypefaces; // r10
  int v21; // edx
  float v22; // xmm7_4
  float v23; // xmm6_4
  __int64 v24; // rdi
  _QWORD *v25; // rcx
  __int64 v26; // rbx
  _QWORD *v27; // rcx
  __int64 v28; // r12
  int v29; // r14d
  __int64 v30; // r15
  __int64 *v31; // rax
  __int64 v32; // r14
  __int64 v33; // r12
  __int64 *v34; // rax
  __int64 v35; // r15
  _QWORD *EffectOrEmptyContainer; // rax
  struct GEL::IEffect *v37; // rsi
  __int128 v38; // [rsp+A8h] [rbp-80h] BYREF
  __int64 v39; // [rsp+B8h] [rbp-70h] BYREF
  struct GEL::IEffect *v40; // [rsp+C0h] [rbp-68h] BYREF
  __int64 v41; // [rsp+C8h] [rbp-60h] BYREF
  __int64 v42; // [rsp+D0h] [rbp-58h] BYREF
  __int64 v43; // [rsp+D8h] [rbp-50h] BYREF
  __int64 v44; // [rsp+E0h] [rbp-48h]
  __int64 v45; // [rsp+E8h] [rbp-40h]
  _BYTE v46[88]; // [rsp+F0h] [rbp-38h] BYREF
  __int64 v48; // [rsp+190h] [rbp+68h] BYREF
  __int64 v49; // [rsp+1A0h] [rbp+78h]

  v49 = a4;
  if ( *(_BYTE *)(a2 + 88) )
  {
    v38 = 0;
    DefaultTypefaces = (struct GEL::IEffect *)GEL::ITypefaceList::GetDefaultTypefaces();
    v40 = DefaultTypefaces;
    v21 = 0;
    v39 = 0;
    if ( (*(_BYTE *)(a2 + 136) & 3) != 0 )
    {
      (*(void (__fastcall **)(_QWORD, struct GEL::IEffect *, __int64, __int64 *))(**(_QWORD **)(a2 + 144) + 152LL))(
        *(_QWORD *)(a2 + 144),
        DefaultTypefaces,
        a2 + 144,
        &v39);
      v21 = v39;
    }
    v22 = a17;
    if ( (*(_BYTE *)(a2 + 136) & 1) != 0 )
      Mso::SVG::TextRenderer::DrawTextDecoration(
        (struct GEL::EffectAccumulator *)&v38,
        (const struct Mso::SVG::TextChunkItem *)a2,
        (float)v21,
        (float)SHIDWORD(v39),
        a17);
    v23 = a14;
    if ( (*(_BYTE *)(a2 + 136) & 2) != 0 )
      Mso::SVG::TextRenderer::DrawTextDecoration(
        (struct GEL::EffectAccumulator *)&v38,
        (const struct Mso::SVG::TextChunkItem *)a2,
        (float)((float)SHIDWORD(v39) * 0.5) + a14,
        (float)SHIDWORD(v39),
        v22);
    LOBYTE(v48) = 0;
    v24 = 0;
    v41 = 0;
    v25 = *(_QWORD **)(a2 + 120);
    if ( v25 )
    {
      Mso::SVG::TextRenderer::ApplyInverseTransformToBrush(v25, a19, (int)&v48, (__int64)v46, &v41);
      v24 = v41;
    }
    v26 = 0;
    v42 = 0;
    v27 = *(_QWORD **)(a2 + 112);
    if ( v27 )
    {
      Mso::SVG::TextRenderer::ApplyInverseTransformToBrush(v27, a19, (int)&v48, (__int64)v46, &v42);
      v26 = v42;
    }
    v28 = *a18;
    if ( !((a18[1] - *a18) >> 1) )
      _invoke_watson(0, 0, 0, 0, 0);
    v29 = (*a5 >> 10) & 1;
    v48 = v26;
    if ( v26 )
      (**(void (__fastcall ***)(__int64))v26)(v26);
    v30 = *(_QWORD *)(a2 + 104);
    v45 = v30;
    if ( v30 )
      (**(void (__fastcall ***)(__int64))v30)(v30);
    v44 = v24;
    if ( v24 )
      (**(void (__fastcall ***)(__int64))v24)(v24);
    if ( !((__int64)(a13[1] - *a13) >> 4) || !((__int64)(a12[1] - *a12) >> 2) || !((__int64)(a11[1] - *a11) >> 2) )
      _invoke_watson(0, 0, 0, 0, 0);
    v31 = (__int64 *)GEL::IEffectGlyphs::Create(
                       &v43,
                       a5,
                       a6,
                       a7,
                       *a10,
                       (__int64)(a10[1] - *a10) >> 1,
                       *a11,
                       *a12,
                       *a13,
                       LODWORD(v23),
                       a15,
                       a16,
                       v49,
                       v24,
                       v30,
                       v26,
                       v29,
                       -1,
                       v28,
                       *(_QWORD *)&DOUBLE_1_0);
    v32 = *v31;
    *v31 = 0;
    v44 = v32;
    if ( v43 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 8LL))(v43);
    if ( v24 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 8LL))(v24);
    if ( v30 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 8LL))(v30);
    if ( v26 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 8LL))(v26);
    v33 = v38;
    if ( (_QWORD)v38 )
    {
      if ( *((_QWORD *)&v38 + 1) )
      {
        (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)&v38 + 1) + 144LL))(*((_QWORD *)&v38 + 1), v32);
      }
      else
      {
        v34 = (__int64 *)GEL::IEffectContainer::Create(&v48);
        v35 = *v34;
        *v34 = 0;
        *((_QWORD *)&v38 + 1) = v35;
        if ( v48 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 8LL))(v48);
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v35 + 144LL))(v35, v33);
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v35 + 144LL))(v35, v32);
        (**(void (__fastcall ***)(__int64))v35)(v35);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 8LL))(v33);
        *(_QWORD *)&v38 = v35;
      }
    }
    else
    {
      if ( v32 )
        (**(void (__fastcall ***)(__int64))v32)(v32);
      *(_QWORD *)&v38 = v32;
    }
    if ( (*(_BYTE *)(a2 + 136) & 4) != 0 )
    {
      v48 = 0;
      (*(void (__fastcall **)(_QWORD, struct GEL::IEffect *, __int64, __int64 *))(**(_QWORD **)(a2 + 144) + 160LL))(
        *(_QWORD *)(a2 + 144),
        v40,
        a2 + 144,
        &v48);
      Mso::SVG::TextRenderer::DrawTextDecoration(
        (struct GEL::EffectAccumulator *)&v38,
        (const struct Mso::SVG::TextChunkItem *)a2,
        COERCE_FLOAT(COERCE_UNSIGNED_INT((float)(int)v48) ^ _xmm),
        (float)SHIDWORD(v48),
        v22);
    }
    EffectOrEmptyContainer = (_QWORD *)GEL::EffectAccumulator::GetEffectOrEmptyContainer(&v38, &v48);
    Mso::SVG::ApplyTransform(&v40, *EffectOrEmptyContainer, a19);
    if ( v48 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 8LL))(v48);
    v37 = v40;
    GEL::EffectAccumulator::Add(a1, v40);
    if ( v37 )
      (*(void (__fastcall **)(struct GEL::IEffect *))(*(_QWORD *)v37 + 8LL))(v37);
    if ( v32 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 8LL))(v32);
    if ( v26 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 8LL))(v26);
    if ( v24 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 8LL))(v24);
    if ( *((_QWORD *)&v38 + 1) )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v38 + 1) + 8LL))(*((_QWORD *)&v38 + 1));
    if ( (_QWORD)v38 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v38 + 8LL))(v38);
  }
}

```

## disassembly

```asm
0x180133530  mov     rax, rsp
0x180133533  mov     [rax+20h], r9
0x180133537  mov     [rax+8], rcx
0x18013353b  push    rbp
0x18013353c  push    rbx
0x18013353d  push    rsi
0x18013353e  push    rdi
0x18013353f  push    r12
0x180133541  push    r14
0x180133543  push    r15
0x180133545  lea     rbp, [rax-58h]
0x180133549  sub     rsp, 140h
0x180133550  movaps  xmmword ptr [rax-48h], xmm6
0x180133554  movaps  xmmword ptr [rax-58h], xmm7
0x180133558  mov     rsi, rdx
0x18013355b  xor     r15d, r15d
0x18013355e  cmp     [rdx+58h], r15b
0x180133562  jz      loc_180133A72
0x180133568  xorps   xmm0, xmm0
0x18013356b  movdqu  [rbp+50h+var_D0], xmm0
0x180133570  call    cs:__imp_?GetDefaultTypefaces@ITypefaceList@GEL@@SAAEAU12@XZ; GEL::ITypefaceList::GetDefaultTypefaces(void)
0x180133576  mov     r10, rax
0x180133579  mov     [rbp+50h+var_B8], rax
0x18013357d  mov     edx, r15d
0x180133580  mov     [rbp+50h+var_C0], rdx
0x180133584  test    byte ptr [rsi+88h], 3
0x18013358b  jz      short loc_1801335B2
0x18013358d  lea     r8, [rsi+90h]
0x180133594  mov     rcx, [r8]
0x180133597  mov     rdx, [rcx]
0x18013359a  mov     rax, [rdx+98h]
0x1801335a1  lea     r9, [rbp+50h+var_C0]
0x1801335a5  mov     rdx, r10
0x1801335a8  call    cs:__guard_dispatch_icall_fptr
0x1801335ae  mov     rdx, [rbp+50h+var_C0]
0x1801335b2  movss   xmm7, [rbp+50h+arg_80]
0x1801335ba  test    byte ptr [rsi+88h], 1
0x1801335c1  jz      short loc_1801335E4
0x1801335c3  movd    xmm3, dword ptr [rbp+50h+var_C0+4]
0x1801335c8  cvtdq2ps xmm3, xmm3; float
0x1801335cb  movd    xmm2, edx
0x1801335cf  cvtdq2ps xmm2, xmm2; float
0x1801335d2  movss   dword ptr [rsp+170h+Reserved], xmm7; float
0x1801335d8  mov     rdx, rsi; struct Mso::SVG::TextChunkItem *
0x1801335db  lea     rcx, [rbp+50h+var_D0]; this
0x1801335df  call    ?DrawTextDecoration@TextRenderer@SVG@Mso@@CAXAEAVEffectAccumulator@GEL@@AEBUTextChunkItem@23@MMM@Z; Mso::SVG::TextRenderer::DrawTextDecoration(GEL::EffectAccumulator &,Mso::SVG::TextChunkItem const &,float,float,float)
0x1801335e4  movss   xmm6, [rbp+50h+arg_68]
0x1801335ec  test    byte ptr [rsi+88h], 2
0x1801335f3  jz      short loc_18013361E
0x1801335f5  movd    xmm3, dword ptr [rbp+50h+var_C0+4]
0x1801335fa  cvtdq2ps xmm3, xmm3; float
0x1801335fd  movaps  xmm2, xmm3
0x180133600  mulss   xmm2, cs:__real@3f000000
0x180133608  addss   xmm2, xmm6; float
0x18013360c  movss   dword ptr [rsp+170h+Reserved], xmm7; float
0x180133612  mov     rdx, rsi; struct Mso::SVG::TextChunkItem *
0x180133615  lea     rcx, [rbp+50h+var_D0]; this
0x180133619  call    ?DrawTextDecoration@TextRenderer@SVG@Mso@@CAXAEAVEffectAccumulator@GEL@@AEBUTextChunkItem@23@MMM@Z; Mso::SVG::TextRenderer::DrawTextDecoration(GEL::EffectAccumulator &,Mso::SVG::TextChunkItem const &,float,float,float)
0x18013361e  mov     byte ptr [rbp+50h+arg_8], r15b
0x180133622  mov     rdi, r15
0x180133625  mov     [rbp+50h+var_B0], r15
0x180133629  mov     rcx, [rsi+78h]
0x18013362d  test    rcx, rcx
0x180133630  jz      short loc_180133653
0x180133632  lea     rax, [rbp+50h+var_B0]
0x180133636  mov     [rsp+170h+Reserved], rax
0x18013363b  lea     r9, [rbp+50h+var_88]
0x18013363f  lea     r8, [rbp+50h+arg_8]
0x180133643  mov     rdx, [rbp+50h+arg_90]
0x18013364a  call    ?ApplyInverseTransformToBrush@TextRenderer@SVG@Mso@@CAXAEBUIBrush@GEL@@AEBU?$TAffine3x3@N@Math@@AEA_NAEAU67@AEAV?$TCntPtr@UIBrush@GEL@@@3@@Z; Mso::SVG::TextRenderer::ApplyInverseTransformToBrush(GEL::IBrush const &,Math::TAffine3x3<double> const &,bool &,Math::TAffine3x3<double> &,Mso::TCntPtr<GEL::IBrush> &)
0x18013364f  mov     rdi, [rbp+50h+var_B0]
0x180133653  mov     rbx, r15
0x180133656  mov     [rbp+50h+var_A8], rbx
0x18013365a  mov     rcx, [rsi+70h]
0x18013365e  test    rcx, rcx
0x180133661  jz      short loc_180133684
0x180133663  lea     rax, [rbp+50h+var_A8]
0x180133667  mov     [rsp+170h+Reserved], rax
0x18013366c  lea     r9, [rbp+50h+var_88]
0x180133670  lea     r8, [rbp+50h+arg_8]
0x180133674  mov     rdx, [rbp+50h+arg_90]
0x18013367b  call    ?ApplyInverseTransformToBrush@TextRenderer@SVG@Mso@@CAXAEBUIBrush@GEL@@AEBU?$TAffine3x3@N@Math@@AEA_NAEAU67@AEAV?$TCntPtr@UIBrush@GEL@@@3@@Z; Mso::SVG::TextRenderer::ApplyInverseTransformToBrush(GEL::IBrush const &,Math::TAffine3x3<double> const &,bool &,Math::TAffine3x3<double> &,Mso::TCntPtr<GEL::IBrush> &)
0x180133680  mov     rbx, [rbp+50h+var_A8]
0x180133684  mov     rax, [rbp+50h+arg_88]
0x18013368b  mov     r12, [rax]
0x18013368e  mov     rcx, [rax+8]
0x180133692  sub     rcx, r12
0x180133695  sar     rcx, 1
0x180133698  jnz     short loc_1801336B0
0x18013369a  mov     [rsp+170h+Reserved], r15; Reserved
0x18013369f  xor     r9d, r9d; LineNo
0x1801336a2  xor     r8d, r8d; FileName
0x1801336a5  xor     edx, edx; FunctionName
0x1801336a7  xor     ecx, ecx; Expression
0x1801336a9  call    cs:__imp__invoke_watson
0x1801336b0  mov     rax, [rbp+50h+arg_20]
0x1801336b7  movzx   r14d, word ptr [rax]
0x1801336bb  shr     r14d, 0Ah
0x1801336bf  and     r14d, 1
0x1801336c3  mov     [rbp+50h+arg_8], rbx
0x1801336c7  test    rbx, rbx
0x1801336ca  jz      short loc_1801336DC
0x1801336cc  mov     rax, [rbx]
0x1801336cf  mov     rcx, rbx
0x1801336d2  mov     rax, [rax]
0x1801336d5  call    cs:__guard_dispatch_icall_fptr
0x1801336db  nop
0x1801336dc  mov     r15, [rsi+68h]
0x1801336e0  mov     [rbp+50h+var_90], r15
0x1801336e4  test    r15, r15
0x1801336e7  jz      short loc_1801336F9
0x1801336e9  mov     rax, [r15]
0x1801336ec  mov     rcx, r15
0x1801336ef  mov     rax, [rax]
0x1801336f2  call    cs:__guard_dispatch_icall_fptr
0x1801336f8  nop
0x1801336f9  mov     [rbp+50h+var_98], rdi
0x1801336fd  test    rdi, rdi
0x180133700  jz      short loc_180133712
0x180133702  mov     rax, [rdi]
0x180133705  mov     rcx, rdi
0x180133708  mov     rax, [rax]
0x18013370b  call    cs:__guard_dispatch_icall_fptr
0x180133711  nop
0x180133712  mov     rax, [rbp+50h+arg_60]
0x180133719  mov     r11, [rax]
0x18013371c  mov     rcx, [rax+8]
0x180133720  sub     rcx, r11
0x180133723  sar     rcx, 4
0x180133727  test    rcx, rcx
0x18013372a  jz      loc_180133A92
0x180133730  mov     rax, [rbp+50h+arg_58]
0x180133737  mov     r10, [rax]
0x18013373a  mov     rcx, [rax+8]
0x18013373e  sub     rcx, r10
0x180133741  sar     rcx, 2
0x180133745  test    rcx, rcx
0x180133748  jz      loc_180133A92
0x18013374e  mov     rax, [rbp+50h+arg_50]
0x180133755  mov     r9, [rax]
0x180133758  mov     rcx, [rax+8]
0x18013375c  sub     rcx, r9
0x18013375f  sar     rcx, 2
0x180133763  test    rcx, rcx
0x180133766  jz      loc_180133A92
0x18013376c  mov     rax, [rbp+50h+arg_48]
0x180133773  mov     r8, [rax]
0x180133776  mov     rcx, [rax+8]
0x18013377a  sub     rcx, r8
0x18013377d  sar     rcx, 1
0x180133780  movsd   xmm0, cs:__real@3ff0000000000000
0x180133788  movsd   [rsp+170h+var_D8], xmm0
0x180133791  mov     [rsp+170h+var_E0], r12
0x180133799  mov     dword ptr [rsp+170h+var_E8], 0FFFFFFFFh
0x1801337a4  mov     [rsp+170h+var_F0], r14d
0x1801337ac  mov     qword ptr [rsp+170h+var_F8], rbx
0x1801337b1  mov     [rsp+170h+var_100], r15
0x1801337b6  mov     [rsp+170h+var_108], rdi
0x1801337bb  mov     rax, [rbp+50h+arg_18]
0x1801337bf  mov     [rsp+170h+var_110], rax
0x1801337c4  movss   xmm0, [rbp+50h+arg_78]
0x1801337cc  movss   dword ptr [rsp+170h+var_118], xmm0
0x1801337d2  movss   xmm1, [rbp+50h+arg_70]
0x1801337da  movss   [rsp+170h+var_120], xmm1
0x1801337e0  movss   [rsp+170h+var_128], xmm6
0x1801337e6  mov     qword ptr [rsp+170h+var_130], r11
0x1801337eb  mov     [rsp+170h+var_138], r10
0x1801337f0  mov     [rsp+170h+var_140], r9
0x1801337f5  mov     dword ptr [rsp+170h+var_148], ecx
0x1801337f9  mov     [rsp+170h+Reserved], r8
0x1801337fe  mov     r9d, [rbp+50h+arg_30]
0x180133805  mov     r8, [rbp+50h+arg_28]
0x18013380c  mov     rdx, [rbp+50h+arg_20]
0x180133813  lea     rcx, [rbp+50h+var_A0]
0x180133817  call    cs:__imp_?Create@IEffectGlyphs@GEL@@SA?AV?$TCntPtr@UIEffectGlyphs@GEL@@@Ofc@@AEBUtag_SCRIPT_ANALYSIS@@PEB_WIPEBGIPEBM3PEBUVector@2@MMMAEBUFont@2@PEBUIBrush@2@PEBUIPen@2@6IK2N@Z; GEL::IEffectGlyphs::Create(tag_SCRIPT_ANALYSIS const &,wchar_t const *,uint,ushort const *,uint,float const *,float const *,GEL::Vector const *,float,float,float,GEL::Font const &,GEL::IBrush const *,GEL::IPen const *,GEL::IBrush const *,uint,ulong,ushort const *,double)
0x18013381d  mov     r14, [rax]
0x180133820  mov     qword ptr [rax], 0
0x180133827  mov     [rbp+50h+var_98], r14
0x18013382b  mov     rcx, [rbp+50h+var_A0]
0x18013382f  test    rcx, rcx
0x180133832  jz      short loc_180133842
0x180133834  mov     rax, [rcx]
0x180133837  mov     rax, [rax+8]
0x18013383b  call    cs:__guard_dispatch_icall_fptr
0x180133841  nop
0x180133842  test    rdi, rdi
0x180133845  jz      short loc_180133858
0x180133847  mov     rax, [rdi]
0x18013384a  mov     rcx, rdi
0x18013384d  mov     rax, [rax+8]
0x180133851  call    cs:__guard_dispatch_icall_fptr
0x180133857  nop
0x180133858  test    r15, r15
0x18013385b  jz      short loc_18013386E
0x18013385d  mov     rax, [r15]
0x180133860  mov     rcx, r15
0x180133863  mov     rax, [rax+8]
0x180133867  call    cs:__guard_dispatch_icall_fptr
0x18013386d  nop
0x18013386e  test    rbx, rbx
0x180133871  jz      short loc_180133883
0x180133873  mov     rax, [rbx]
0x180133876  mov     rcx, rbx
0x180133879  mov     rax, [rax+8]
0x18013387d  call    cs:__guard_dispatch_icall_fptr
0x180133883  mov     r12, qword ptr [rbp+50h+var_D0]
0x180133887  test    r12, r12
0x18013388a  jnz     short loc_1801338A9
0x18013388c  test    r14, r14
0x18013388f  jz      short loc_1801338A0
0x180133891  mov     rax, [r14]
0x180133894  mov     rcx, r14
0x180133897  mov     rax, [rax]
0x18013389a  call    cs:__guard_dispatch_icall_fptr
0x1801338a0  mov     qword ptr [rbp+50h+var_D0], r14
0x1801338a4  jmp     loc_180133949
0x1801338a9  mov     rcx, qword ptr [rbp+50h+var_D0+8]
0x1801338ad  test    rcx, rcx
0x1801338b0  jnz     loc_180133936
0x1801338b6  lea     rcx, [rbp+50h+arg_8]
0x1801338ba  call    cs:__imp_?Create@IEffectContainer@GEL@@SA?AV?$TCntPtr@UIEffectContainer@GEL@@@Ofc@@XZ; GEL::IEffectContainer::Create(void)
0x1801338c0  mov     r15, [rax]
0x1801338c3  mov     qword ptr [rax], 0
0x1801338ca  mov     qword ptr [rbp+50h+var_D0+8], r15
0x1801338ce  mov     rcx, [rbp+50h+arg_8]
0x1801338d2  test    rcx, rcx
0x1801338d5  jz      short loc_1801338E4
0x1801338d7  mov     rax, [rcx]
0x1801338da  mov     rax, [rax+8]
0x1801338de  call    cs:__guard_dispatch_icall_fptr
0x1801338e4  mov     rax, [r15]
0x1801338e7  mov     rdx, r12
0x1801338ea  mov     rcx, r15
0x1801338ed  mov     rax, [rax+90h]
0x1801338f4  call    cs:__guard_dispatch_icall_fptr
0x1801338fa  mov     rax, [r15]
0x1801338fd  mov     rdx, r14
0x180133900  mov     rcx, r15
0x180133903  mov     rax, [rax+90h]
0x18013390a  call    cs:__guard_dispatch_icall_fptr
0x180133910  mov     rax, [r15]
0x180133913  mov     rcx, r15
0x180133916  mov     rax, [rax]
0x180133919  call    cs:__guard_dispatch_icall_fptr
0x18013391f  mov     rax, [r12]
0x180133923  mov     rcx, r12
0x180133926  mov     rax, [rax+8]
0x18013392a  call    cs:__guard_dispatch_icall_fptr
0x180133930  mov     qword ptr [rbp+50h+var_D0], r15
0x180133934  jmp     short loc_180133949
0x180133936  mov     rax, [rcx]
0x180133939  mov     rdx, r14
0x18013393c  mov     rax, [rax+90h]
0x180133943  call    cs:__guard_dispatch_icall_fptr
0x180133949  test    byte ptr [rsi+88h], 4
0x180133950  jz      short loc_1801339A5
0x180133952  mov     [rbp+50h+arg_8], 0
0x18013395a  lea     r8, [rsi+90h]
0x180133961  mov     rcx, [r8]
0x180133964  mov     rax, [rcx]
0x180133967  lea     r9, [rbp+50h+arg_8]
0x18013396b  mov     rdx, [rbp+50h+var_B8]
0x18013396f  mov     rax, [rax+0A0h]
0x180133976  call    cs:__guard_dispatch_icall_fptr
0x18013397c  movd    xmm3, dword ptr [rbp+50h+arg_8+4]
0x180133981  cvtdq2ps xmm3, xmm3; float
0x180133984  movd    xmm2, dword ptr [rbp+50h+arg_8]
0x180133989  cvtdq2ps xmm2, xmm2
0x18013398c  xorps   xmm2, cs:__xmm@80000000800000008000000080000000; float
0x180133993  movss   dword ptr [rsp+170h+Reserved], xmm7; float
0x180133999  mov     rdx, rsi; struct Mso::SVG::TextChunkItem *
0x18013399c  lea     rcx, [rbp+50h+var_D0]; this
0x1801339a0  call    ?DrawTextDecoration@TextRenderer@SVG@Mso@@CAXAEAVEffectAccumulator@GEL@@AEBUTextChunkItem@23@MMM@Z; Mso::SVG::TextRenderer::DrawTextDecoration(GEL::EffectAccumulator &,Mso::SVG::TextChunkItem const &,float,float,float)
0x1801339a5  lea     rdx, [rbp+50h+arg_8]
0x1801339a9  lea     rcx, [rbp+50h+var_D0]
0x1801339ad  call    ?GetEffectOrEmptyContainer@EffectAccumulator@GEL@@QEAA?AV?$TCntPtr@$$CBUIEffect@GEL@@@Ofc@@XZ; GEL::EffectAccumulator::GetEffectOrEmptyContainer(void)
0x1801339b2  nop
0x1801339b3  mov     r8, [rbp+50h+arg_90]
0x1801339ba  mov     rdx, [rax]
0x1801339bd  lea     rcx, [rbp+50h+var_B8]
0x1801339c1  call    ?ApplyTransform@SVG@Mso@@YA?AV?$TCntPtr@$$CBUIEffect@GEL@@@2@AEBUIEffect@GEL@@AEBU?$TAffine3x3@N@Math@@@Z; Mso::SVG::ApplyTransform(GEL::IEffect const &,Math::TAffine3x3<double> const &)
0x1801339c6  nop
0x1801339c7  mov     rcx, [rbp+50h+arg_8]
0x1801339cb  test    rcx, rcx
0x1801339ce  jz      short loc_1801339DD
0x1801339d0  mov     rax, [rcx]
0x1801339d3  mov     rax, [rax+8]
0x1801339d7  call    cs:__guard_dispatch_icall_fptr
0x1801339dd  mov     rsi, [rbp+50h+var_B8]
0x1801339e1  mov     rdx, rsi; struct GEL::IEffect *
0x1801339e4  mov     rcx, [rbp+50h+arg_0]; this
0x1801339e8  call    ?Add@EffectAccumulator@GEL@@QEAAXAEBUIEffect@2@@Z; GEL::EffectAccumulator::Add(GEL::IEffect const &)
0x1801339ed  nop
0x1801339ee  test    rsi, rsi
0x1801339f1  jz      short loc_180133A04
0x1801339f3  mov     rax, [rsi]
0x1801339f6  mov     rcx, rsi
0x1801339f9  mov     rax, [rax+8]
0x1801339fd  call    cs:__guard_dispatch_icall_fptr
0x180133a03  nop
  ... truncated ...
```
