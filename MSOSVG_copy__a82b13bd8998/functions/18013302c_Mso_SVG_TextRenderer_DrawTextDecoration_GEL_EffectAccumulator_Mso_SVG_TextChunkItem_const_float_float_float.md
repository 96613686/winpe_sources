# Mso::SVG::TextRenderer::DrawTextDecoration(GEL::EffectAccumulator &,Mso::SVG::TextChunkItem const &,float,float,float)

- ea: `0x18013302c`
- end: `0x1801331ec`
- name: `?DrawTextDecoration@TextRenderer@SVG@Mso@@CAXAEAVEffectAccumulator@GEL@@AEBUTextChunkItem@23@MMM@Z`
- size: `448`
- prototype: `void __usercall(struct GEL::EffectAccumulator *this@<rcx>, const struct Mso::SVG::TextChunkItem *@<rdx>, float@<xmm2>, float@<xmm3>, float)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180133570`

## callees

- `0x18004e660`
- `0x18013302c`
- `0x18013f810`

## import_xrefs

- `gfx!?Create@IRectanglePath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@AEBU?$TRect@N@Math@@@Z` at `0x180133098`
- `gfx!?Create@IRectanglePath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@AEBU?$TRect@N@Math@@@Z` at `0x180133098`
- `gfx!?Create@IEffectFilledPath@GEL@@SA?AV?$TCntPtr@UIEffectFilledPath@GEL@@@Ofc@@AEBUIPath@2@AEBUIBrush@2@PEBU?$TAffine3x3@N@Math@@@Z` at `0x180133168`
- `gfx!?Create@IEffectFilledPath@GEL@@SA?AV?$TCntPtr@UIEffectFilledPath@GEL@@@Ofc@@AEBUIPath@2@AEBUIBrush@2@PEBU?$TAffine3x3@N@Math@@@Z` at `0x180133168`
- `gfx!?Create@IEffectPennedPath@GEL@@SA?AV?$TCntPtr@UIEffectPennedPath@GEL@@@Ofc@@AEBUIPath@2@AEBUIPen@2@@Z` at `0x1801330fa`
- `gfx!?Create@IEffectPennedPath@GEL@@SA?AV?$TCntPtr@UIEffectPennedPath@GEL@@@Ofc@@AEBUIPath@2@AEBUIPen@2@@Z` at `0x1801330fa`
- `gfx!?Create@IEffectPennedBrushPath@GEL@@SA?AV?$TCntPtr@UIEffectPennedBrushPath@GEL@@@Ofc@@AEBUIPath@2@AEBUIPen@2@AEBUIBrush@2@_N@Z` at `0x1801330f2`
- `gfx!?Create@IEffectPennedBrushPath@GEL@@SA?AV?$TCntPtr@UIEffectPennedBrushPath@GEL@@@Ofc@@AEBUIPath@2@AEBUIPen@2@AEBUIBrush@2@_N@Z` at `0x1801330f2`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Mso::SVG::TextRenderer::DrawTextDecoration(
        struct GEL::EffectAccumulator *this,
        const struct Mso::SVG::TextChunkItem *a2,
        float a3,
        float a4,
        float a5)
{
  __int64 *v7; // rax
  __int64 v8; // rsi
  const struct GEL::IEffect **v9; // rax
  const struct GEL::IEffect *v10; // rbx
  __int64 v11; // r8
  const struct GEL::IEffect *v12; // rbx
  __int64 v13; // [rsp+30h] [rbp-40h] BYREF
  _QWORD v14[2]; // [rsp+38h] [rbp-38h] BYREF
  _QWORD v15[5]; // [rsp+48h] [rbp-28h] BYREF
  const struct GEL::IEffect *v16; // [rsp+98h] [rbp+28h] BYREF

  if ( *((_QWORD *)a2 + 24) || *((_QWORD *)a2 + 26) )
  {
    v15[0] = 0;
    *(double *)&v15[1] = a3;
    *(double *)&v15[2] = a5;
    *(double *)&v15[3] = (float)(a3 + a4);
    v7 = (__int64 *)GEL::IRectanglePath::Create(&v13, v15);
    v8 = *v7;
    *v7 = 0;
    v14[1] = v8;
    if ( v13 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 8LL))(v13);
    if ( *((_QWORD *)a2 + 24) )
    {
      v16 = 0;
      if ( *((_QWORD *)a2 + 25) )
        v9 = (const struct GEL::IEffect **)GEL::IEffectPennedBrushPath::Create(v14, v8);
      else
        v9 = (const struct GEL::IEffect **)GEL::IEffectPennedPath::Create(v14, v8);
      v10 = *v9;
      if ( *v9 )
        (**(void (__fastcall ***)(const struct GEL::IEffect *))v10)(*v9);
      v16 = v10;
      if ( v14[0] )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v14[0] + 8LL))(v14[0]);
      GEL::EffectAccumulator::Add(this, v10);
      if ( v10 )
        (*(void (__fastcall **)(const struct GEL::IEffect *))(*(_QWORD *)v10 + 8LL))(v10);
    }
    v11 = *((_QWORD *)a2 + 26);
    if ( v11 )
    {
      v12 = *(const struct GEL::IEffect **)GEL::IEffectFilledPath::Create(&v16, v8, v11, 0);
      v14[0] = v12;
      if ( v12 )
        (**(void (__fastcall ***)(const struct GEL::IEffect *))v12)(v12);
      if ( v16 )
        (*(void (__fastcall **)(const struct GEL::IEffect *))(*(_QWORD *)v16 + 8LL))(v16);
      GEL::EffectAccumulator::Add(this, v12);
      if ( v12 )
        (*(void (__fastcall **)(const struct GEL::IEffect *))(*(_QWORD *)v12 + 8LL))(v12);
    }
    if ( v8 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
  }
}

```

## disassembly

```asm
0x18013302c  mov     [rsp-18h+arg_0], rbx
0x180133031  mov     [rsp-18h+arg_10], rsi
0x180133036  push    rbp
0x180133037  push    rdi
0x180133038  push    r14
0x18013303a  mov     rbp, rsp
0x18013303d  sub     rsp, 70h
0x180133041  mov     rdi, rdx
0x180133044  mov     r14, rcx
0x180133047  cmp     qword ptr [rdx+0C0h], 0
0x18013304f  jnz     short loc_18013305F
0x180133051  cmp     qword ptr [rdx+0D0h], 0
0x180133059  jz      loc_1801331D7
0x18013305f  xorps   xmm0, xmm0
0x180133062  movsd   [rbp+var_28], xmm0
0x180133067  xorps   xmm1, xmm1
0x18013306a  cvtss2sd xmm1, xmm2
0x18013306e  movsd   [rbp+var_20], xmm1
0x180133073  movss   xmm0, [rbp+arg_20]
0x180133078  cvtps2pd xmm0, xmm0
0x18013307b  movsd   [rbp+var_18], xmm0
0x180133080  addss   xmm2, xmm3
0x180133084  xorps   xmm0, xmm0
0x180133087  cvtss2sd xmm0, xmm2
0x18013308b  movsd   [rbp+var_10], xmm0
0x180133090  lea     rdx, [rbp+var_28]
0x180133094  lea     rcx, [rbp+var_40]
0x180133098  call    cs:__imp_?Create@IRectanglePath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@AEBU?$TRect@N@Math@@@Z; GEL::IRectanglePath::Create(Math::TRect<double> const &)
0x18013309e  mov     rsi, [rax]
0x1801330a1  mov     qword ptr [rax], 0
0x1801330a8  mov     [rbp+var_30], rsi
0x1801330ac  mov     rcx, [rbp+var_40]
0x1801330b0  test    rcx, rcx
0x1801330b3  jz      short loc_1801330C2
0x1801330b5  mov     rax, [rcx]
0x1801330b8  mov     rax, [rax+8]
0x1801330bc  call    cs:__guard_dispatch_icall_fptr
0x1801330c2  mov     r8, [rdi+0C0h]
0x1801330c9  test    r8, r8
0x1801330cc  jz      loc_180133152
0x1801330d2  mov     [rbp+arg_8], 0
0x1801330da  mov     r9, [rdi+0C8h]
0x1801330e1  mov     rdx, rsi
0x1801330e4  lea     rcx, [rbp+var_38]
0x1801330e8  test    r9, r9
0x1801330eb  jz      short loc_1801330FA
0x1801330ed  mov     [rsp+70h+var_50], 0
0x1801330f2  call    cs:__imp_?Create@IEffectPennedBrushPath@GEL@@SA?AV?$TCntPtr@UIEffectPennedBrushPath@GEL@@@Ofc@@AEBUIPath@2@AEBUIPen@2@AEBUIBrush@2@_N@Z; GEL::IEffectPennedBrushPath::Create(GEL::IPath const &,GEL::IPen const &,GEL::IBrush const &,bool)
0x1801330f8  jmp     short loc_180133100
0x1801330fa  call    cs:__imp_?Create@IEffectPennedPath@GEL@@SA?AV?$TCntPtr@UIEffectPennedPath@GEL@@@Ofc@@AEBUIPath@2@AEBUIPen@2@@Z; GEL::IEffectPennedPath::Create(GEL::IPath const &,GEL::IPen const &)
0x180133100  mov     rbx, [rax]
0x180133103  test    rbx, rbx
0x180133106  jz      short loc_180133117
0x180133108  mov     rax, [rbx]
0x18013310b  mov     rcx, rbx
0x18013310e  mov     rax, [rax]
0x180133111  call    cs:__guard_dispatch_icall_fptr
0x180133117  mov     rcx, [rbp+var_38]
0x18013311b  test    rcx, rcx
0x18013311e  mov     [rbp+arg_8], rbx
0x180133122  jz      short loc_180133131
0x180133124  mov     rax, [rcx]
0x180133127  mov     rax, [rax+8]
0x18013312b  call    cs:__guard_dispatch_icall_fptr
0x180133131  mov     rdx, rbx; struct GEL::IEffect *
0x180133134  mov     rcx, r14; this
0x180133137  call    ?Add@EffectAccumulator@GEL@@QEAAXAEBUIEffect@2@@Z; GEL::EffectAccumulator::Add(GEL::IEffect const &)
0x18013313c  nop
0x18013313d  test    rbx, rbx
0x180133140  jz      short loc_180133152
0x180133142  mov     rax, [rbx]
0x180133145  mov     rcx, rbx
0x180133148  mov     rax, [rax+8]
0x18013314c  call    cs:__guard_dispatch_icall_fptr
0x180133152  mov     r8, [rdi+0D0h]
0x180133159  test    r8, r8
0x18013315c  jz      short loc_1801331C2
0x18013315e  xor     r9d, r9d
0x180133161  mov     rdx, rsi
0x180133164  lea     rcx, [rbp+arg_8]
0x180133168  call    cs:__imp_?Create@IEffectFilledPath@GEL@@SA?AV?$TCntPtr@UIEffectFilledPath@GEL@@@Ofc@@AEBUIPath@2@AEBUIBrush@2@PEBU?$TAffine3x3@N@Math@@@Z; GEL::IEffectFilledPath::Create(GEL::IPath const &,GEL::IBrush const &,Math::TAffine3x3<double> const *)
0x18013316e  mov     rbx, [rax]
0x180133171  mov     [rbp+var_38], rbx
0x180133175  test    rbx, rbx
0x180133178  jz      short loc_18013318A
0x18013317a  mov     rax, [rbx]
0x18013317d  mov     rcx, rbx
0x180133180  mov     rax, [rax]
0x180133183  call    cs:__guard_dispatch_icall_fptr
0x180133189  nop
0x18013318a  mov     rcx, [rbp+arg_8]
0x18013318e  test    rcx, rcx
0x180133191  jz      short loc_1801331A0
0x180133193  mov     rax, [rcx]
0x180133196  mov     rax, [rax+8]
0x18013319a  call    cs:__guard_dispatch_icall_fptr
0x1801331a0  mov     rdx, rbx; struct GEL::IEffect *
0x1801331a3  mov     rcx, r14; this
0x1801331a6  call    ?Add@EffectAccumulator@GEL@@QEAAXAEBUIEffect@2@@Z; GEL::EffectAccumulator::Add(GEL::IEffect const &)
0x1801331ab  nop
0x1801331ac  test    rbx, rbx
0x1801331af  jz      short loc_1801331C2
0x1801331b1  mov     rax, [rbx]
0x1801331b4  mov     rcx, rbx
0x1801331b7  mov     rax, [rax+8]
0x1801331bb  call    cs:__guard_dispatch_icall_fptr
0x1801331c1  nop
0x1801331c2  test    rsi, rsi
0x1801331c5  jz      short loc_1801331D7
0x1801331c7  mov     rax, [rsi]
0x1801331ca  mov     rcx, rsi
0x1801331cd  mov     rax, [rax+8]
0x1801331d1  call    cs:__guard_dispatch_icall_fptr
0x1801331d7  lea     r11, [rsp+70h+var_s0]
0x1801331dc  mov     rbx, [r11+20h]
0x1801331e0  mov     rsi, [r11+30h]
0x1801331e4  mov     rsp, r11
0x1801331e7  pop     r14
0x1801331e9  pop     rdi
0x1801331ea  pop     rbp
0x1801331eb  retn
```
