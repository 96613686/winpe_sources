# Mso::SVG::TextRenderer::DrawTextDecoration(GEL::EffectAccumulator &,Mso::SVG::TextChunkItem const &,float,float,float)

- ea: `0x180132fec`
- end: `0x1801331ac`
- name: `?DrawTextDecoration@TextRenderer@SVG@Mso@@CAXAEAVEffectAccumulator@GEL@@AEBUTextChunkItem@23@MMM@Z`
- size: `448`
- prototype: `void __usercall(struct GEL::EffectAccumulator *this@<rcx>, const struct Mso::SVG::TextChunkItem *@<rdx>, float@<xmm2>, float@<xmm3>, float)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180133530`

## callees

- `0x18004e640`
- `0x180132fec`
- `0x18013f760`

## import_xrefs

- `gfx!?Create@IRectanglePath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@AEBU?$TRect@N@Math@@@Z` at `0x180133058`
- `gfx!?Create@IRectanglePath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@AEBU?$TRect@N@Math@@@Z` at `0x180133058`
- `gfx!?Create@IEffectFilledPath@GEL@@SA?AV?$TCntPtr@UIEffectFilledPath@GEL@@@Ofc@@AEBUIPath@2@AEBUIBrush@2@PEBU?$TAffine3x3@N@Math@@@Z` at `0x180133128`
- `gfx!?Create@IEffectFilledPath@GEL@@SA?AV?$TCntPtr@UIEffectFilledPath@GEL@@@Ofc@@AEBUIPath@2@AEBUIBrush@2@PEBU?$TAffine3x3@N@Math@@@Z` at `0x180133128`
- `gfx!?Create@IEffectPennedPath@GEL@@SA?AV?$TCntPtr@UIEffectPennedPath@GEL@@@Ofc@@AEBUIPath@2@AEBUIPen@2@@Z` at `0x1801330ba`
- `gfx!?Create@IEffectPennedPath@GEL@@SA?AV?$TCntPtr@UIEffectPennedPath@GEL@@@Ofc@@AEBUIPath@2@AEBUIPen@2@@Z` at `0x1801330ba`
- `gfx!?Create@IEffectPennedBrushPath@GEL@@SA?AV?$TCntPtr@UIEffectPennedBrushPath@GEL@@@Ofc@@AEBUIPath@2@AEBUIPen@2@AEBUIBrush@2@_N@Z` at `0x1801330b2`
- `gfx!?Create@IEffectPennedBrushPath@GEL@@SA?AV?$TCntPtr@UIEffectPennedBrushPath@GEL@@@Ofc@@AEBUIPath@2@AEBUIPen@2@AEBUIBrush@2@_N@Z` at `0x1801330b2`

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
0x180132fec  mov     [rsp-18h+arg_0], rbx
0x180132ff1  mov     [rsp-18h+arg_10], rsi
0x180132ff6  push    rbp
0x180132ff7  push    rdi
0x180132ff8  push    r14
0x180132ffa  mov     rbp, rsp
0x180132ffd  sub     rsp, 70h
0x180133001  mov     rdi, rdx
0x180133004  mov     r14, rcx
0x180133007  cmp     qword ptr [rdx+0C0h], 0
0x18013300f  jnz     short loc_18013301F
0x180133011  cmp     qword ptr [rdx+0D0h], 0
0x180133019  jz      loc_180133197
0x18013301f  xorps   xmm0, xmm0
0x180133022  movsd   [rbp+var_28], xmm0
0x180133027  xorps   xmm1, xmm1
0x18013302a  cvtss2sd xmm1, xmm2
0x18013302e  movsd   [rbp+var_20], xmm1
0x180133033  movss   xmm0, [rbp+arg_20]
0x180133038  cvtps2pd xmm0, xmm0
0x18013303b  movsd   [rbp+var_18], xmm0
0x180133040  addss   xmm2, xmm3
0x180133044  xorps   xmm0, xmm0
0x180133047  cvtss2sd xmm0, xmm2
0x18013304b  movsd   [rbp+var_10], xmm0
0x180133050  lea     rdx, [rbp+var_28]
0x180133054  lea     rcx, [rbp+var_40]
0x180133058  call    cs:__imp_?Create@IRectanglePath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@AEBU?$TRect@N@Math@@@Z; GEL::IRectanglePath::Create(Math::TRect<double> const &)
0x18013305e  mov     rsi, [rax]
0x180133061  mov     qword ptr [rax], 0
0x180133068  mov     [rbp+var_30], rsi
0x18013306c  mov     rcx, [rbp+var_40]
0x180133070  test    rcx, rcx
0x180133073  jz      short loc_180133082
0x180133075  mov     rax, [rcx]
0x180133078  mov     rax, [rax+8]
0x18013307c  call    cs:__guard_dispatch_icall_fptr
0x180133082  mov     r8, [rdi+0C0h]
0x180133089  test    r8, r8
0x18013308c  jz      loc_180133112
0x180133092  mov     [rbp+arg_8], 0
0x18013309a  mov     r9, [rdi+0C8h]
0x1801330a1  mov     rdx, rsi
0x1801330a4  lea     rcx, [rbp+var_38]
0x1801330a8  test    r9, r9
0x1801330ab  jz      short loc_1801330BA
0x1801330ad  mov     [rsp+70h+var_50], 0
0x1801330b2  call    cs:__imp_?Create@IEffectPennedBrushPath@GEL@@SA?AV?$TCntPtr@UIEffectPennedBrushPath@GEL@@@Ofc@@AEBUIPath@2@AEBUIPen@2@AEBUIBrush@2@_N@Z; GEL::IEffectPennedBrushPath::Create(GEL::IPath const &,GEL::IPen const &,GEL::IBrush const &,bool)
0x1801330b8  jmp     short loc_1801330C0
0x1801330ba  call    cs:__imp_?Create@IEffectPennedPath@GEL@@SA?AV?$TCntPtr@UIEffectPennedPath@GEL@@@Ofc@@AEBUIPath@2@AEBUIPen@2@@Z; GEL::IEffectPennedPath::Create(GEL::IPath const &,GEL::IPen const &)
0x1801330c0  mov     rbx, [rax]
0x1801330c3  test    rbx, rbx
0x1801330c6  jz      short loc_1801330D7
0x1801330c8  mov     rax, [rbx]
0x1801330cb  mov     rcx, rbx
0x1801330ce  mov     rax, [rax]
0x1801330d1  call    cs:__guard_dispatch_icall_fptr
0x1801330d7  mov     rcx, [rbp+var_38]
0x1801330db  test    rcx, rcx
0x1801330de  mov     [rbp+arg_8], rbx
0x1801330e2  jz      short loc_1801330F1
0x1801330e4  mov     rax, [rcx]
0x1801330e7  mov     rax, [rax+8]
0x1801330eb  call    cs:__guard_dispatch_icall_fptr
0x1801330f1  mov     rdx, rbx; struct GEL::IEffect *
0x1801330f4  mov     rcx, r14; this
0x1801330f7  call    ?Add@EffectAccumulator@GEL@@QEAAXAEBUIEffect@2@@Z; GEL::EffectAccumulator::Add(GEL::IEffect const &)
0x1801330fc  nop
0x1801330fd  test    rbx, rbx
0x180133100  jz      short loc_180133112
0x180133102  mov     rax, [rbx]
0x180133105  mov     rcx, rbx
0x180133108  mov     rax, [rax+8]
0x18013310c  call    cs:__guard_dispatch_icall_fptr
0x180133112  mov     r8, [rdi+0D0h]
0x180133119  test    r8, r8
0x18013311c  jz      short loc_180133182
0x18013311e  xor     r9d, r9d
0x180133121  mov     rdx, rsi
0x180133124  lea     rcx, [rbp+arg_8]
0x180133128  call    cs:__imp_?Create@IEffectFilledPath@GEL@@SA?AV?$TCntPtr@UIEffectFilledPath@GEL@@@Ofc@@AEBUIPath@2@AEBUIBrush@2@PEBU?$TAffine3x3@N@Math@@@Z; GEL::IEffectFilledPath::Create(GEL::IPath const &,GEL::IBrush const &,Math::TAffine3x3<double> const *)
0x18013312e  mov     rbx, [rax]
0x180133131  mov     [rbp+var_38], rbx
0x180133135  test    rbx, rbx
0x180133138  jz      short loc_18013314A
0x18013313a  mov     rax, [rbx]
0x18013313d  mov     rcx, rbx
0x180133140  mov     rax, [rax]
0x180133143  call    cs:__guard_dispatch_icall_fptr
0x180133149  nop
0x18013314a  mov     rcx, [rbp+arg_8]
0x18013314e  test    rcx, rcx
0x180133151  jz      short loc_180133160
0x180133153  mov     rax, [rcx]
0x180133156  mov     rax, [rax+8]
0x18013315a  call    cs:__guard_dispatch_icall_fptr
0x180133160  mov     rdx, rbx; struct GEL::IEffect *
0x180133163  mov     rcx, r14; this
0x180133166  call    ?Add@EffectAccumulator@GEL@@QEAAXAEBUIEffect@2@@Z; GEL::EffectAccumulator::Add(GEL::IEffect const &)
0x18013316b  nop
0x18013316c  test    rbx, rbx
0x18013316f  jz      short loc_180133182
0x180133171  mov     rax, [rbx]
0x180133174  mov     rcx, rbx
0x180133177  mov     rax, [rax+8]
0x18013317b  call    cs:__guard_dispatch_icall_fptr
0x180133181  nop
0x180133182  test    rsi, rsi
0x180133185  jz      short loc_180133197
0x180133187  mov     rax, [rsi]
0x18013318a  mov     rcx, rsi
0x18013318d  mov     rax, [rax+8]
0x180133191  call    cs:__guard_dispatch_icall_fptr
0x180133197  lea     r11, [rsp+70h+var_s0]
0x18013319c  mov     rbx, [r11+20h]
0x1801331a0  mov     rsi, [r11+30h]
0x1801331a4  mov     rsp, r11
0x1801331a7  pop     r14
0x1801331a9  pop     rdi
0x1801331aa  pop     rbp
0x1801331ab  retn
```
