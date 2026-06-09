# Mso::SVG::TextRenderer::RenderTextItem(void *,Mso::SVG::TextChunkItem const &,Mso::SVG::TextAnchor,GEL::Font const &,tag_SCRIPT_ANALYSIS const &,wchar_t const *,uint,bool,bool,std::vector<ushort,std::allocator<ushort>> const &,std::vector<float,std::allocator<float>> const &,std::vector<float,std::allocator<float>> const &,std::vector<GEL::Vector,std::allocator<GEL::Vector>> const &,float,float,float,float,std::vector<ushort,std::allocator<ushort>> const &,Math::TAffine3x3<double> const &,Mso::SVG::TextRenderingParams const &)

- ea: `0x180133570`
- end: `0x180133aec`
- name: `?RenderTextItem@TextRenderer@SVG@Mso@@CAXPEAXAEBUTextChunkItem@23@W4TextAnchor@23@AEBUFont@GEL@@AEBUtag_SCRIPT_ANALYSIS@@PEB_WI_N6AEBV?$vector@GV?$allocator@G@std@@@std@@AEBV?$vector@MV?$allocator@M@std@@@std@@8AEBV?$vector@UVector@GEL@@V?$allocator@UVector@GEL@@@std@@@std@@MMMM7AEBU?$TAffine3x3@N@Math@@AEBUTextRenderingParams@23@@Z`
- size: `1404`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x18003fd34`
- `0x18004e660`
- `0x18004e760`
- `0x18013302c`
- `0x180133288`
- `0x180133570`
- `0x18013f810`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1801336e9`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180133ae5`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1801336e9`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180133ae5`
- `gfx!?Create@IEffectGlyphs@GEL@@SA?AV?$TCntPtr@UIEffectGlyphs@GEL@@@Ofc@@AEBUtag_SCRIPT_ANALYSIS@@PEB_WIPEBGIPEBM3PEBUVector@2@MMMAEBUFont@2@PEBUIBrush@2@PEBUIPen@2@6IK2N@Z` at `0x180133857`
- `gfx!?Create@IEffectGlyphs@GEL@@SA?AV?$TCntPtr@UIEffectGlyphs@GEL@@@Ofc@@AEBUtag_SCRIPT_ANALYSIS@@PEB_WIPEBGIPEBM3PEBUVector@2@MMMAEBUFont@2@PEBUIBrush@2@PEBUIPen@2@6IK2N@Z` at `0x180133857`
- `gfx!?Create@IEffectContainer@GEL@@SA?AV?$TCntPtr@UIEffectContainer@GEL@@@Ofc@@XZ` at `0x1801338fa`
- `gfx!?Create@IEffectContainer@GEL@@SA?AV?$TCntPtr@UIEffectContainer@GEL@@@Ofc@@XZ` at `0x1801338fa`
- `gfx!?GetDefaultTypefaces@ITypefaceList@GEL@@SAAEAU12@XZ` at `0x1801335b0`
- `gfx!?GetDefaultTypefaces@ITypefaceList@GEL@@SAAEAU12@XZ` at `0x1801335b0`

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
0x180133570  mov     rax, rsp
0x180133573  mov     [rax+20h], r9
0x180133577  mov     [rax+8], rcx
0x18013357b  push    rbp
0x18013357c  push    rbx
0x18013357d  push    rsi
0x18013357e  push    rdi
0x18013357f  push    r12
0x180133581  push    r14
0x180133583  push    r15
0x180133585  lea     rbp, [rax-58h]
0x180133589  sub     rsp, 140h
0x180133590  movaps  xmmword ptr [rax-48h], xmm6
0x180133594  movaps  xmmword ptr [rax-58h], xmm7
0x180133598  mov     rsi, rdx
0x18013359b  xor     r15d, r15d
0x18013359e  cmp     [rdx+58h], r15b
0x1801335a2  jz      loc_180133AB2
0x1801335a8  xorps   xmm0, xmm0
0x1801335ab  movdqu  [rbp+50h+var_D0], xmm0
0x1801335b0  call    cs:__imp_?GetDefaultTypefaces@ITypefaceList@GEL@@SAAEAU12@XZ; GEL::ITypefaceList::GetDefaultTypefaces(void)
0x1801335b6  mov     r10, rax
0x1801335b9  mov     [rbp+50h+var_B8], rax
0x1801335bd  mov     edx, r15d
0x1801335c0  mov     [rbp+50h+var_C0], rdx
0x1801335c4  test    byte ptr [rsi+88h], 3
0x1801335cb  jz      short loc_1801335F2
0x1801335cd  lea     r8, [rsi+90h]
0x1801335d4  mov     rcx, [r8]
0x1801335d7  mov     rdx, [rcx]
0x1801335da  mov     rax, [rdx+98h]
0x1801335e1  lea     r9, [rbp+50h+var_C0]
0x1801335e5  mov     rdx, r10
0x1801335e8  call    cs:__guard_dispatch_icall_fptr
0x1801335ee  mov     rdx, [rbp+50h+var_C0]
0x1801335f2  movss   xmm7, [rbp+50h+arg_80]
0x1801335fa  test    byte ptr [rsi+88h], 1
0x180133601  jz      short loc_180133624
0x180133603  movd    xmm3, dword ptr [rbp+50h+var_C0+4]
0x180133608  cvtdq2ps xmm3, xmm3; float
0x18013360b  movd    xmm2, edx
0x18013360f  cvtdq2ps xmm2, xmm2; float
0x180133612  movss   dword ptr [rsp+170h+Reserved], xmm7; float
0x180133618  mov     rdx, rsi; struct Mso::SVG::TextChunkItem *
0x18013361b  lea     rcx, [rbp+50h+var_D0]; this
0x18013361f  call    ?DrawTextDecoration@TextRenderer@SVG@Mso@@CAXAEAVEffectAccumulator@GEL@@AEBUTextChunkItem@23@MMM@Z; Mso::SVG::TextRenderer::DrawTextDecoration(GEL::EffectAccumulator &,Mso::SVG::TextChunkItem const &,float,float,float)
0x180133624  movss   xmm6, [rbp+50h+arg_68]
0x18013362c  test    byte ptr [rsi+88h], 2
0x180133633  jz      short loc_18013365E
0x180133635  movd    xmm3, dword ptr [rbp+50h+var_C0+4]
0x18013363a  cvtdq2ps xmm3, xmm3; float
0x18013363d  movaps  xmm2, xmm3
0x180133640  mulss   xmm2, cs:__real@3f000000
0x180133648  addss   xmm2, xmm6; float
0x18013364c  movss   dword ptr [rsp+170h+Reserved], xmm7; float
0x180133652  mov     rdx, rsi; struct Mso::SVG::TextChunkItem *
0x180133655  lea     rcx, [rbp+50h+var_D0]; this
0x180133659  call    ?DrawTextDecoration@TextRenderer@SVG@Mso@@CAXAEAVEffectAccumulator@GEL@@AEBUTextChunkItem@23@MMM@Z; Mso::SVG::TextRenderer::DrawTextDecoration(GEL::EffectAccumulator &,Mso::SVG::TextChunkItem const &,float,float,float)
0x18013365e  mov     byte ptr [rbp+50h+arg_8], r15b
0x180133662  mov     rdi, r15
0x180133665  mov     [rbp+50h+var_B0], r15
0x180133669  mov     rcx, [rsi+78h]
0x18013366d  test    rcx, rcx
0x180133670  jz      short loc_180133693
0x180133672  lea     rax, [rbp+50h+var_B0]
0x180133676  mov     [rsp+170h+Reserved], rax
0x18013367b  lea     r9, [rbp+50h+var_88]
0x18013367f  lea     r8, [rbp+50h+arg_8]
0x180133683  mov     rdx, [rbp+50h+arg_90]
0x18013368a  call    ?ApplyInverseTransformToBrush@TextRenderer@SVG@Mso@@CAXAEBUIBrush@GEL@@AEBU?$TAffine3x3@N@Math@@AEA_NAEAU67@AEAV?$TCntPtr@UIBrush@GEL@@@3@@Z; Mso::SVG::TextRenderer::ApplyInverseTransformToBrush(GEL::IBrush const &,Math::TAffine3x3<double> const &,bool &,Math::TAffine3x3<double> &,Mso::TCntPtr<GEL::IBrush> &)
0x18013368f  mov     rdi, [rbp+50h+var_B0]
0x180133693  mov     rbx, r15
0x180133696  mov     [rbp+50h+var_A8], rbx
0x18013369a  mov     rcx, [rsi+70h]
0x18013369e  test    rcx, rcx
0x1801336a1  jz      short loc_1801336C4
0x1801336a3  lea     rax, [rbp+50h+var_A8]
0x1801336a7  mov     [rsp+170h+Reserved], rax
0x1801336ac  lea     r9, [rbp+50h+var_88]
0x1801336b0  lea     r8, [rbp+50h+arg_8]
0x1801336b4  mov     rdx, [rbp+50h+arg_90]
0x1801336bb  call    ?ApplyInverseTransformToBrush@TextRenderer@SVG@Mso@@CAXAEBUIBrush@GEL@@AEBU?$TAffine3x3@N@Math@@AEA_NAEAU67@AEAV?$TCntPtr@UIBrush@GEL@@@3@@Z; Mso::SVG::TextRenderer::ApplyInverseTransformToBrush(GEL::IBrush const &,Math::TAffine3x3<double> const &,bool &,Math::TAffine3x3<double> &,Mso::TCntPtr<GEL::IBrush> &)
0x1801336c0  mov     rbx, [rbp+50h+var_A8]
0x1801336c4  mov     rax, [rbp+50h+arg_88]
0x1801336cb  mov     r12, [rax]
0x1801336ce  mov     rcx, [rax+8]
0x1801336d2  sub     rcx, r12
0x1801336d5  sar     rcx, 1
0x1801336d8  jnz     short loc_1801336F0
0x1801336da  mov     [rsp+170h+Reserved], r15; Reserved
0x1801336df  xor     r9d, r9d; LineNo
0x1801336e2  xor     r8d, r8d; FileName
0x1801336e5  xor     edx, edx; FunctionName
0x1801336e7  xor     ecx, ecx; Expression
0x1801336e9  call    cs:__imp__invoke_watson
0x1801336f0  mov     rax, [rbp+50h+arg_20]
0x1801336f7  movzx   r14d, word ptr [rax]
0x1801336fb  shr     r14d, 0Ah
0x1801336ff  and     r14d, 1
0x180133703  mov     [rbp+50h+arg_8], rbx
0x180133707  test    rbx, rbx
0x18013370a  jz      short loc_18013371C
0x18013370c  mov     rax, [rbx]
0x18013370f  mov     rcx, rbx
0x180133712  mov     rax, [rax]
0x180133715  call    cs:__guard_dispatch_icall_fptr
0x18013371b  nop
0x18013371c  mov     r15, [rsi+68h]
0x180133720  mov     [rbp+50h+var_90], r15
0x180133724  test    r15, r15
0x180133727  jz      short loc_180133739
0x180133729  mov     rax, [r15]
0x18013372c  mov     rcx, r15
0x18013372f  mov     rax, [rax]
0x180133732  call    cs:__guard_dispatch_icall_fptr
0x180133738  nop
0x180133739  mov     [rbp+50h+var_98], rdi
0x18013373d  test    rdi, rdi
0x180133740  jz      short loc_180133752
0x180133742  mov     rax, [rdi]
0x180133745  mov     rcx, rdi
0x180133748  mov     rax, [rax]
0x18013374b  call    cs:__guard_dispatch_icall_fptr
0x180133751  nop
0x180133752  mov     rax, [rbp+50h+arg_60]
0x180133759  mov     r11, [rax]
0x18013375c  mov     rcx, [rax+8]
0x180133760  sub     rcx, r11
0x180133763  sar     rcx, 4
0x180133767  test    rcx, rcx
0x18013376a  jz      loc_180133AD2
0x180133770  mov     rax, [rbp+50h+arg_58]
0x180133777  mov     r10, [rax]
0x18013377a  mov     rcx, [rax+8]
0x18013377e  sub     rcx, r10
0x180133781  sar     rcx, 2
0x180133785  test    rcx, rcx
0x180133788  jz      loc_180133AD2
0x18013378e  mov     rax, [rbp+50h+arg_50]
0x180133795  mov     r9, [rax]
0x180133798  mov     rcx, [rax+8]
0x18013379c  sub     rcx, r9
0x18013379f  sar     rcx, 2
0x1801337a3  test    rcx, rcx
0x1801337a6  jz      loc_180133AD2
0x1801337ac  mov     rax, [rbp+50h+arg_48]
0x1801337b3  mov     r8, [rax]
0x1801337b6  mov     rcx, [rax+8]
0x1801337ba  sub     rcx, r8
0x1801337bd  sar     rcx, 1
0x1801337c0  movsd   xmm0, cs:__real@3ff0000000000000
0x1801337c8  movsd   [rsp+170h+var_D8], xmm0
0x1801337d1  mov     [rsp+170h+var_E0], r12
0x1801337d9  mov     dword ptr [rsp+170h+var_E8], 0FFFFFFFFh
0x1801337e4  mov     [rsp+170h+var_F0], r14d
0x1801337ec  mov     qword ptr [rsp+170h+var_F8], rbx
0x1801337f1  mov     [rsp+170h+var_100], r15
0x1801337f6  mov     [rsp+170h+var_108], rdi
0x1801337fb  mov     rax, [rbp+50h+arg_18]
0x1801337ff  mov     [rsp+170h+var_110], rax
0x180133804  movss   xmm0, [rbp+50h+arg_78]
0x18013380c  movss   dword ptr [rsp+170h+var_118], xmm0
0x180133812  movss   xmm1, [rbp+50h+arg_70]
0x18013381a  movss   [rsp+170h+var_120], xmm1
0x180133820  movss   [rsp+170h+var_128], xmm6
0x180133826  mov     qword ptr [rsp+170h+var_130], r11
0x18013382b  mov     [rsp+170h+var_138], r10
0x180133830  mov     [rsp+170h+var_140], r9
0x180133835  mov     dword ptr [rsp+170h+var_148], ecx
0x180133839  mov     [rsp+170h+Reserved], r8
0x18013383e  mov     r9d, [rbp+50h+arg_30]
0x180133845  mov     r8, [rbp+50h+arg_28]
0x18013384c  mov     rdx, [rbp+50h+arg_20]
0x180133853  lea     rcx, [rbp+50h+var_A0]
0x180133857  call    cs:__imp_?Create@IEffectGlyphs@GEL@@SA?AV?$TCntPtr@UIEffectGlyphs@GEL@@@Ofc@@AEBUtag_SCRIPT_ANALYSIS@@PEB_WIPEBGIPEBM3PEBUVector@2@MMMAEBUFont@2@PEBUIBrush@2@PEBUIPen@2@6IK2N@Z; GEL::IEffectGlyphs::Create(tag_SCRIPT_ANALYSIS const &,wchar_t const *,uint,ushort const *,uint,float const *,float const *,GEL::Vector const *,float,float,float,GEL::Font const &,GEL::IBrush const *,GEL::IPen const *,GEL::IBrush const *,uint,ulong,ushort const *,double)
0x18013385d  mov     r14, [rax]
0x180133860  mov     qword ptr [rax], 0
0x180133867  mov     [rbp+50h+var_98], r14
0x18013386b  mov     rcx, [rbp+50h+var_A0]
0x18013386f  test    rcx, rcx
0x180133872  jz      short loc_180133882
0x180133874  mov     rax, [rcx]
0x180133877  mov     rax, [rax+8]
0x18013387b  call    cs:__guard_dispatch_icall_fptr
0x180133881  nop
0x180133882  test    rdi, rdi
0x180133885  jz      short loc_180133898
0x180133887  mov     rax, [rdi]
0x18013388a  mov     rcx, rdi
0x18013388d  mov     rax, [rax+8]
0x180133891  call    cs:__guard_dispatch_icall_fptr
0x180133897  nop
0x180133898  test    r15, r15
0x18013389b  jz      short loc_1801338AE
0x18013389d  mov     rax, [r15]
0x1801338a0  mov     rcx, r15
0x1801338a3  mov     rax, [rax+8]
0x1801338a7  call    cs:__guard_dispatch_icall_fptr
0x1801338ad  nop
0x1801338ae  test    rbx, rbx
0x1801338b1  jz      short loc_1801338C3
0x1801338b3  mov     rax, [rbx]
0x1801338b6  mov     rcx, rbx
0x1801338b9  mov     rax, [rax+8]
0x1801338bd  call    cs:__guard_dispatch_icall_fptr
0x1801338c3  mov     r12, qword ptr [rbp+50h+var_D0]
0x1801338c7  test    r12, r12
0x1801338ca  jnz     short loc_1801338E9
0x1801338cc  test    r14, r14
0x1801338cf  jz      short loc_1801338E0
0x1801338d1  mov     rax, [r14]
0x1801338d4  mov     rcx, r14
0x1801338d7  mov     rax, [rax]
0x1801338da  call    cs:__guard_dispatch_icall_fptr
0x1801338e0  mov     qword ptr [rbp+50h+var_D0], r14
0x1801338e4  jmp     loc_180133989
0x1801338e9  mov     rcx, qword ptr [rbp+50h+var_D0+8]
0x1801338ed  test    rcx, rcx
0x1801338f0  jnz     loc_180133976
0x1801338f6  lea     rcx, [rbp+50h+arg_8]
0x1801338fa  call    cs:__imp_?Create@IEffectContainer@GEL@@SA?AV?$TCntPtr@UIEffectContainer@GEL@@@Ofc@@XZ; GEL::IEffectContainer::Create(void)
0x180133900  mov     r15, [rax]
0x180133903  mov     qword ptr [rax], 0
0x18013390a  mov     qword ptr [rbp+50h+var_D0+8], r15
0x18013390e  mov     rcx, [rbp+50h+arg_8]
0x180133912  test    rcx, rcx
0x180133915  jz      short loc_180133924
0x180133917  mov     rax, [rcx]
0x18013391a  mov     rax, [rax+8]
0x18013391e  call    cs:__guard_dispatch_icall_fptr
0x180133924  mov     rax, [r15]
0x180133927  mov     rdx, r12
0x18013392a  mov     rcx, r15
0x18013392d  mov     rax, [rax+90h]
0x180133934  call    cs:__guard_dispatch_icall_fptr
0x18013393a  mov     rax, [r15]
0x18013393d  mov     rdx, r14
0x180133940  mov     rcx, r15
0x180133943  mov     rax, [rax+90h]
0x18013394a  call    cs:__guard_dispatch_icall_fptr
0x180133950  mov     rax, [r15]
0x180133953  mov     rcx, r15
0x180133956  mov     rax, [rax]
0x180133959  call    cs:__guard_dispatch_icall_fptr
0x18013395f  mov     rax, [r12]
0x180133963  mov     rcx, r12
0x180133966  mov     rax, [rax+8]
0x18013396a  call    cs:__guard_dispatch_icall_fptr
0x180133970  mov     qword ptr [rbp+50h+var_D0], r15
0x180133974  jmp     short loc_180133989
0x180133976  mov     rax, [rcx]
0x180133979  mov     rdx, r14
0x18013397c  mov     rax, [rax+90h]
0x180133983  call    cs:__guard_dispatch_icall_fptr
0x180133989  test    byte ptr [rsi+88h], 4
0x180133990  jz      short loc_1801339E5
0x180133992  mov     [rbp+50h+arg_8], 0
0x18013399a  lea     r8, [rsi+90h]
0x1801339a1  mov     rcx, [r8]
0x1801339a4  mov     rax, [rcx]
0x1801339a7  lea     r9, [rbp+50h+arg_8]
0x1801339ab  mov     rdx, [rbp+50h+var_B8]
0x1801339af  mov     rax, [rax+0A0h]
0x1801339b6  call    cs:__guard_dispatch_icall_fptr
0x1801339bc  movd    xmm3, dword ptr [rbp+50h+arg_8+4]
0x1801339c1  cvtdq2ps xmm3, xmm3; float
0x1801339c4  movd    xmm2, dword ptr [rbp+50h+arg_8]
0x1801339c9  cvtdq2ps xmm2, xmm2
0x1801339cc  xorps   xmm2, cs:__xmm@80000000800000008000000080000000; float
0x1801339d3  movss   dword ptr [rsp+170h+Reserved], xmm7; float
0x1801339d9  mov     rdx, rsi; struct Mso::SVG::TextChunkItem *
0x1801339dc  lea     rcx, [rbp+50h+var_D0]; this
0x1801339e0  call    ?DrawTextDecoration@TextRenderer@SVG@Mso@@CAXAEAVEffectAccumulator@GEL@@AEBUTextChunkItem@23@MMM@Z; Mso::SVG::TextRenderer::DrawTextDecoration(GEL::EffectAccumulator &,Mso::SVG::TextChunkItem const &,float,float,float)
0x1801339e5  lea     rdx, [rbp+50h+arg_8]
0x1801339e9  lea     rcx, [rbp+50h+var_D0]
0x1801339ed  call    ?GetEffectOrEmptyContainer@EffectAccumulator@GEL@@QEAA?AV?$TCntPtr@$$CBUIEffect@GEL@@@Ofc@@XZ; GEL::EffectAccumulator::GetEffectOrEmptyContainer(void)
0x1801339f2  nop
0x1801339f3  mov     r8, [rbp+50h+arg_90]
0x1801339fa  mov     rdx, [rax]
0x1801339fd  lea     rcx, [rbp+50h+var_B8]
0x180133a01  call    ?ApplyTransform@SVG@Mso@@YA?AV?$TCntPtr@$$CBUIEffect@GEL@@@2@AEBUIEffect@GEL@@AEBU?$TAffine3x3@N@Math@@@Z; Mso::SVG::ApplyTransform(GEL::IEffect const &,Math::TAffine3x3<double> const &)
0x180133a06  nop
0x180133a07  mov     rcx, [rbp+50h+arg_8]
0x180133a0b  test    rcx, rcx
0x180133a0e  jz      short loc_180133A1D
0x180133a10  mov     rax, [rcx]
0x180133a13  mov     rax, [rax+8]
0x180133a17  call    cs:__guard_dispatch_icall_fptr
0x180133a1d  mov     rsi, [rbp+50h+var_B8]
0x180133a21  mov     rdx, rsi; struct GEL::IEffect *
0x180133a24  mov     rcx, [rbp+50h+arg_0]; this
0x180133a28  call    ?Add@EffectAccumulator@GEL@@QEAAXAEBUIEffect@2@@Z; GEL::EffectAccumulator::Add(GEL::IEffect const &)
0x180133a2d  nop
0x180133a2e  test    rsi, rsi
0x180133a31  jz      short loc_180133A44
0x180133a33  mov     rax, [rsi]
0x180133a36  mov     rcx, rsi
0x180133a39  mov     rax, [rax+8]
0x180133a3d  call    cs:__guard_dispatch_icall_fptr
0x180133a43  nop
  ... truncated ...
```
