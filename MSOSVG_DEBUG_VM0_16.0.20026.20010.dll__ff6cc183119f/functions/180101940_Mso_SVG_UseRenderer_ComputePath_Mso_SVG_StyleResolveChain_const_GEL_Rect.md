# Mso::SVG::UseRenderer::ComputePath(Mso::SVG::StyleResolveChain const &,GEL::Rect *)

- ea: `0x180101940`
- end: `0x180101c72`
- name: `?ComputePath@UseRenderer@SVG@Mso@@UEAA?AV?$TCntPtr@$$CBUIPath@GEL@@@3@AEBVStyleResolveChain@23@PEAURect@GEL@@@Z`
- size: `818`
- prototype: `__int64 __fastcall(Mso::SVG::RenderableRenderer *this)`
- caller_count: `0`
- callee_count: `15`
- tags: `broker_com_uri`

## callees

- `0x18000d5e0`
- `0x18000d67c`
- `0x18003f8f0`
- `0x180041e7c`
- `0x180043578`
- `0x1800435e0`
- `0x180043c10`
- `0x1800447b0`
- `0x18004c038`
- `0x18004f518`
- `0x1800f5d90`
- `0x180101940`
- `0x1801395a4`
- `0x18013e010`
- `0x18013f760`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180101c5d`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180101c6b`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180101c5d`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180101c6b`
- `gfx!?Create@IEmptyPath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@XZ` at `0x180101a09`
- `gfx!?Create@IEmptyPath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@XZ` at `0x180101bff`
- `gfx!?Create@IEmptyPath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@XZ` at `0x180101a09`
- `gfx!?Create@IEmptyPath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@XZ` at `0x180101bff`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *__fastcall Mso::SVG::UseRenderer::ComputePath(
        Mso::SVG::RenderableRenderer *this,
        _QWORD *a2,
        __int64 a3,
        double *a4)
{
  _QWORD *v8; // r14
  __int64 Renderable; // rax
  __int64 v10; // rax
  void (__fastcall ****v11)(_QWORD); // rax
  void (__fastcall ***v12)(_QWORD); // rcx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rdx
  wchar_t **v16; // rdx
  __int64 v17; // rax
  double v18; // xmm6_8
  double v19; // xmm0_8
  double *TransformedBounds; // rax
  void (__fastcall ****v21)(_QWORD); // rax
  void (__fastcall ***v22)(_QWORD); // rcx
  bool v23; // zf
  __int64 v25; // [rsp+38h] [rbp-79h] BYREF
  __int64 v26; // [rsp+40h] [rbp-71h] BYREF
  __int64 v27; // [rsp+48h] [rbp-69h]
  Mso::SVG::LengthResolver *v28; // [rsp+50h] [rbp-61h]
  __int64 v29; // [rsp+58h] [rbp-59h] BYREF
  _OWORD v30[2]; // [rsp+68h] [rbp-49h] BYREF
  _OWORD v31[2]; // [rsp+88h] [rbp-29h] BYREF
  double v32; // [rsp+A8h] [rbp-9h]
  double v33; // [rsp+B0h] [rbp-1h]
  _BYTE v34[48]; // [rsp+B8h] [rbp+7h] BYREF
  __int64 v35; // [rsp+118h] [rbp+67h] BYREF

  v8 = (_QWORD *)*((_QWORD *)this + 2);
  if ( !v8 )
  {
LABEL_36:
    CrashWithRecovery(0x1E3C3843u, 0);
    JUMPOUT(0x180101C71LL);
  }
  _castguard_slow_path_check_user_handled(*v8, 6592, 0);
  if ( !Mso::SVG::RenderableRenderer::IsRenderingEnabled(this)
    || !v8[57]
    || (Renderable = Mso::SVG::Environment::QueryRenderable(*(_QWORD *)(*((_QWORD *)this + 3) + 64LL), v8 + 55)) == 0 )
  {
    v21 = (void (__fastcall ****)(_QWORD))GEL::IEmptyPath::Create(&v25);
    v22 = *v21;
    v23 = *v21 == 0;
    *a2 = *v21;
    if ( !v23 )
      (**v22)(v22);
    v14 = v25;
    if ( v25 )
      goto LABEL_33;
    return a2;
  }
  Mso::SVG::RenderableRenderer::Create(&v35, Renderable, *((_QWORD *)this + 3));
  v10 = (*(__int64 (__fastcall **)(_QWORD *))(*v8 + 104LL))(v8);
  v26 = a3;
  v27 = v10;
  v28 = *(Mso::SVG::LengthResolver **)(a3 + 16);
  if ( !*(_BYTE *)Mso::SVG::StyleResolveChain::Get<30>(&v26) )
  {
    v11 = (void (__fastcall ****)(_QWORD))GEL::IEmptyPath::Create(&v25);
    v12 = *v11;
    *a2 = *v11;
    if ( v12 )
      (**v12)(v12);
    v13 = v25;
    if ( v25 )
      goto LABEL_9;
    goto LABEL_10;
  }
  memset(v30, 0, sizeof(v30));
  if ( !a4 )
  {
    v15 = *(_QWORD *)(v27 + 16);
    if ( v15 )
    {
      v16 = (wchar_t **)(v15 + 392);
    }
    else if ( !*(_BYTE *)(v27 + 24) || (v16 = (wchar_t **)&Mso::SVG::StyleMetaData<33>::inherit, !*(_QWORD *)(v27 + 8)) )
    {
      v16 = &Mso::SVG::StyleMetaData<33>::initial;
    }
    if ( !*((_BYTE *)v16 + 32) )
    {
      if ( v26 )
        v17 = Mso::SVG::StyleResolveChain::Get<33>();
      else
        v17 = Mso::SVG::StyleResolveChain::GetNormal<33>(&v26, *(_QWORD *)(v27 + 8));
      v16 = (wchar_t **)v17;
    }
    if ( v16[2] )
      Mso::SVG::Environment::QueryClipPath(*(_QWORD *)(*((_QWORD *)this + 3) + 64LL));
  }
  Mso::SVG::EnvironmentRenderer::BeginRecursion(*((Mso::SVG::EnvironmentRenderer **)this + 3));
  if ( !v35 )
  {
    CrashWithRecovery(0x1E3C3840u, 0);
    goto LABEL_36;
  }
  (*(void (__fastcall **)(__int64, __int64 *, __int64 *, _OWORD *))(*(_QWORD *)v35 + 24LL))(v35, &v29, &v26, v30);
  --**((_DWORD **)this + 3);
  v18 = Mso::SVG::LengthResolver::ResolveLength(
          v28,
          (const struct Mso::SVG::Length *)(v8 + 49),
          (const struct Mso::SVG::StyleResolveChain *)&v26);
  v19 = Mso::SVG::LengthResolver::ResolveLength(
          v28,
          (const struct Mso::SVG::Length *)(v8 + 47),
          (const struct Mso::SVG::StyleResolveChain *)&v26);
  v31[0] = _mm_load_si128((const __m128i *)&_xmm);
  v31[1] = _mm_load_si128((const __m128i *)&_xmm);
  v32 = v19;
  v33 = v18;
  Math::operator*=<double,double,0>(v31, (char *)this + 32);
  Mso::SVG::RenderableRenderer::ApplyStandardPathEffects(
    (_DWORD)this,
    (unsigned int)&v25,
    v29,
    (unsigned int)&v26,
    (__int64)v30,
    (__int64)v31);
  if ( a4 )
  {
    TransformedBounds = (double *)GEL::Rect::GetTransformedBounds(v30, v34, v31);
    *a4 = fmin(*a4, *TransformedBounds);
    a4[2] = fmax(a4[2], TransformedBounds[2]);
    a4[1] = fmin(a4[1], TransformedBounds[1]);
    a4[3] = fmax(a4[3], TransformedBounds[3]);
  }
  *a2 = v25;
  v13 = v29;
  if ( v29 )
  {
    v29 = 0;
LABEL_9:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 8LL))(v13);
  }
LABEL_10:
  v14 = v35;
  if ( v35 )
  {
    v35 = 0;
LABEL_33:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
  }
  return a2;
}

```

## disassembly

```asm
0x180101940  mov     rax, rsp
0x180101943  mov     [rax+10h], rbx
0x180101947  mov     [rax+18h], rsi
0x18010194b  push    rbp
0x18010194c  push    rdi
0x18010194d  push    r13
0x18010194f  push    r14
0x180101951  push    r15
0x180101953  lea     rbp, [rax-5Fh]
0x180101957  sub     rsp, 0E0h
0x18010195e  movaps  xmmword ptr [rax-38h], xmm6
0x180101962  mov     rbx, r9
0x180101965  mov     r13, r8
0x180101968  mov     rdi, rdx
0x18010196b  mov     rsi, rcx
0x18010196e  mov     r14, [rcx+10h]
0x180101972  test    r14, r14
0x180101975  jz      loc_180101C64
0x18010197b  xor     r8d, r8d
0x18010197e  mov     edx, 19C0h
0x180101983  mov     rcx, [r14]
0x180101986  call    __castguard_slow_path_check_user_handled
0x18010198b  lea     r15, [r14+1B8h]
0x180101992  mov     rcx, rsi; this
0x180101995  call    ?IsRenderingEnabled@RenderableRenderer@SVG@Mso@@QEBA_NXZ; Mso::SVG::RenderableRenderer::IsRenderingEnabled(void)
0x18010199a  test    al, al
0x18010199c  jz      loc_180101BFB
0x1801019a2  cmp     qword ptr [r15+10h], 0
0x1801019a7  jz      loc_180101BFB
0x1801019ad  mov     rax, [rsi+18h]
0x1801019b1  mov     rdx, r15
0x1801019b4  mov     rcx, [rax+40h]
0x1801019b8  call    ?QueryRenderable@Environment@SVG@Mso@@QEAAPEAVRenderableContext@23@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Mso::SVG::Environment::QueryRenderable(std::wstring const &)
0x1801019bd  test    rax, rax
0x1801019c0  jz      loc_180101BFB
0x1801019c6  mov     r8, [rsi+18h]
0x1801019ca  mov     rdx, rax
0x1801019cd  lea     rcx, [rbp+57h+arg_0]
0x1801019d1  call    ?Create@RenderableRenderer@SVG@Mso@@SA?AV?$TCntPtr@VRenderableRenderer@SVG@Mso@@@3@AEAVRenderableContext@23@AEAVEnvironmentRenderer@23@@Z; Mso::SVG::RenderableRenderer::Create(Mso::SVG::RenderableContext &,Mso::SVG::EnvironmentRenderer &)
0x1801019d6  nop
0x1801019d7  mov     rax, [r14]
0x1801019da  mov     rcx, r14
0x1801019dd  mov     rax, [rax+68h]
0x1801019e1  call    cs:__guard_dispatch_icall_fptr
0x1801019e7  mov     [rbp+57h+var_C8], r13
0x1801019eb  mov     [rbp+57h+var_C0], rax
0x1801019ef  mov     rax, [r13+10h]
0x1801019f3  mov     [rbp+57h+var_B8], rax
0x1801019f7  lea     rcx, [rbp+57h+var_C8]
0x1801019fb  call    ??$Get@$0BO@@StyleResolveChain@SVG@Mso@@QEBAAEB_NXZ; Mso::SVG::StyleResolveChain::Get<30>(void)
0x180101a00  cmp     byte ptr [rax], 0
0x180101a03  jnz     short loc_180101A57
0x180101a05  lea     rcx, [rbp+57h+var_D0]
0x180101a09  call    cs:__imp_?Create@IEmptyPath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@XZ; GEL::IEmptyPath::Create(void)
0x180101a0f  mov     rcx, [rax]
0x180101a12  mov     [rdi], rcx
0x180101a15  test    rcx, rcx
0x180101a18  jz      short loc_180101A26
0x180101a1a  mov     rax, [rcx]
0x180101a1d  mov     rax, [rax]
0x180101a20  call    cs:__guard_dispatch_icall_fptr
0x180101a26  mov     rcx, [rbp+57h+var_D0]
0x180101a2a  test    rcx, rcx
0x180101a2d  jz      short loc_180101A3D
0x180101a2f  mov     rax, [rcx]
0x180101a32  mov     rax, [rax+8]
0x180101a36  call    cs:__guard_dispatch_icall_fptr
0x180101a3c  nop
0x180101a3d  mov     rcx, [rbp+57h+arg_0]
0x180101a41  test    rcx, rcx
0x180101a44  jz      loc_180101C32
0x180101a4a  mov     [rbp+57h+arg_0], 0
0x180101a52  jmp     loc_180101C25
0x180101a57  xorps   xmm0, xmm0
0x180101a5a  movups  [rbp+57h+var_A0], xmm0
0x180101a5e  xorps   xmm1, xmm1
0x180101a61  movups  [rbp+57h+var_90], xmm1
0x180101a65  test    rbx, rbx
0x180101a68  jnz     short loc_180101AD5
0x180101a6a  mov     rax, [rbp+57h+var_C0]
0x180101a6e  mov     rdx, [rax+10h]
0x180101a72  test    rdx, rdx
0x180101a75  jz      short loc_180101A80
0x180101a77  add     rdx, 188h
0x180101a7e  jmp     short loc_180101A9B
0x180101a80  cmp     byte ptr [rax+18h], 0
0x180101a84  jz      short loc_180101A94
0x180101a86  cmp     qword ptr [rax+8], 0
0x180101a8b  lea     rdx, ?inherit@?$StyleMetaData@$0CB@@SVG@Mso@@2V?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@B; std::optional<std::wstring> const Mso::SVG::StyleMetaData<33>::inherit
0x180101a92  jnz     short loc_180101A9B
0x180101a94  lea     rdx, ?initial@?$StyleMetaData@$0CB@@SVG@Mso@@2V?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@B; std::optional<std::wstring> const Mso::SVG::StyleMetaData<33>::initial
0x180101a9b  cmp     byte ptr [rdx+20h], 0
0x180101a9f  jnz     short loc_180101AC1
0x180101aa1  mov     rcx, [rbp+57h+var_C8]
0x180101aa5  test    rcx, rcx
0x180101aa8  jz      short loc_180101AB1
0x180101aaa  call    ??$Get@$0CB@@StyleResolveChain@SVG@Mso@@QEBAAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; Mso::SVG::StyleResolveChain::Get<33>(void)
0x180101aaf  jmp     short loc_180101ABE
0x180101ab1  mov     rdx, [rax+8]
0x180101ab5  lea     rcx, [rbp+57h+var_C8]
0x180101ab9  call    ??$GetNormal@$0CB@@StyleResolveChain@SVG@Mso@@AEBAAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBVStyle@12@@Z; Mso::SVG::StyleResolveChain::GetNormal<33>(Mso::SVG::Style const &)
0x180101abe  mov     rdx, rax
0x180101ac1  cmp     qword ptr [rdx+10h], 0
0x180101ac6  jz      short loc_180101AD5
0x180101ac8  mov     rax, [rsi+18h]
0x180101acc  mov     rcx, [rax+40h]
0x180101ad0  call    ?QueryClipPath@Environment@SVG@Mso@@QEAAPEAVClipPathContext@23@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Mso::SVG::Environment::QueryClipPath(std::wstring const &)
0x180101ad5  mov     rcx, [rsi+18h]; this
0x180101ad9  call    ?BeginRecursion@EnvironmentRenderer@SVG@Mso@@QEAAXXZ; Mso::SVG::EnvironmentRenderer::BeginRecursion(void)
0x180101ade  mov     rcx, [rbp+57h+arg_0]
0x180101ae2  test    rcx, rcx
0x180101ae5  jz      loc_180101C56
0x180101aeb  mov     rax, [rcx]
0x180101aee  lea     r9, [rbp+57h+var_A0]
0x180101af2  lea     r8, [rbp+57h+var_C8]
0x180101af6  lea     rdx, [rbp+57h+var_B0]
0x180101afa  mov     rax, [rax+18h]
0x180101afe  call    cs:__guard_dispatch_icall_fptr
0x180101b04  nop
0x180101b05  mov     rax, [rsi+18h]
0x180101b09  dec     dword ptr [rax]
0x180101b0b  lea     rdx, [r14+188h]; struct Mso::SVG::Length *
0x180101b12  lea     r8, [rbp+57h+var_C8]; struct Mso::SVG::StyleResolveChain *
0x180101b16  mov     rcx, [rbp+57h+var_B8]; this
0x180101b1a  call    ?ResolveLength@LengthResolver@SVG@Mso@@AEBANAEBULength@23@AEBVStyleResolveChain@23@@Z; Mso::SVG::LengthResolver::ResolveLength(Mso::SVG::Length const &,Mso::SVG::StyleResolveChain const &)
0x180101b1f  movaps  xmm6, xmm0
0x180101b22  lea     rdx, [r14+178h]; struct Mso::SVG::Length *
0x180101b29  lea     r8, [rbp+57h+var_C8]; struct Mso::SVG::StyleResolveChain *
0x180101b2d  mov     rcx, [rbp+57h+var_B8]; this
0x180101b31  call    ?ResolveLength@LengthResolver@SVG@Mso@@AEBANAEBULength@23@AEBVStyleResolveChain@23@@Z; Mso::SVG::LengthResolver::ResolveLength(Mso::SVG::Length const &,Mso::SVG::StyleResolveChain const &)
0x180101b36  movdqa  xmm1, cs:__xmm@00000000000000003ff0000000000000
0x180101b3e  movups  [rbp+57h+var_80], xmm1
0x180101b42  movdqa  xmm2, cs:__xmm@3ff00000000000000000000000000000
0x180101b4a  movups  [rbp+57h+var_70], xmm2
0x180101b4e  movsd   [rbp+57h+var_60], xmm0
0x180101b53  movsd   [rbp+57h+var_58], xmm6
0x180101b58  lea     rdx, [rsi+20h]
0x180101b5c  lea     rcx, [rbp+57h+var_80]
0x180101b60  call    ??$?XNN$0A@@Math@@YAAEAU?$TAffine3x3@N@0@AEAU10@AEBU10@@Z; Math::operator*=<double,double,0>(Math::TAffine3x3<double> &,Math::TAffine3x3<double> const &)
0x180101b65  lea     r9, [rbp+57h+var_80]
0x180101b69  mov     [rsp+100h+var_D8], r9
0x180101b6e  lea     rax, [rbp+57h+var_A0]
0x180101b72  mov     [rsp+100h+var_E0], rax
0x180101b77  lea     r9, [rbp+57h+var_C8]
0x180101b7b  mov     r8, [rbp+57h+var_B0]
0x180101b7f  lea     rdx, [rbp+57h+var_D0]
0x180101b83  mov     rcx, rsi
0x180101b86  call    ?ApplyStandardPathEffects@RenderableRenderer@SVG@Mso@@QEBA?AV?$TCntPtr@$$CBUIPath@GEL@@@3@AEBUIPath@GEL@@AEBVStyleResolveChain@23@PEBURect@6@PEBU?$TAffine3x3@N@Math@@@Z; Mso::SVG::RenderableRenderer::ApplyStandardPathEffects(GEL::IPath const &,Mso::SVG::StyleResolveChain const &,GEL::Rect const *,Math::TAffine3x3<double> const *)
0x180101b8b  test    rbx, rbx
0x180101b8e  jz      short loc_180101BDA
0x180101b90  lea     r8, [rbp+57h+var_80]
0x180101b94  lea     rdx, [rbp+57h+var_50]
0x180101b98  lea     rcx, [rbp+57h+var_A0]
0x180101b9c  call    ?GetTransformedBounds@Rect@GEL@@QEBA?AU12@AEBU?$TAffine3x3@N@Math@@@Z; GEL::Rect::GetTransformedBounds(Math::TAffine3x3<double> const &)
0x180101ba1  movsd   xmm0, qword ptr [rbx]
0x180101ba5  minsd   xmm0, qword ptr [rax]
0x180101ba9  movsd   qword ptr [rbx], xmm0
0x180101bad  movsd   xmm1, qword ptr [rbx+10h]
0x180101bb2  maxsd   xmm1, qword ptr [rax+10h]
0x180101bb7  movsd   qword ptr [rbx+10h], xmm1
0x180101bbc  movsd   xmm0, qword ptr [rbx+8]
0x180101bc1  minsd   xmm0, qword ptr [rax+8]
0x180101bc6  movsd   qword ptr [rbx+8], xmm0
0x180101bcb  movsd   xmm1, qword ptr [rbx+18h]
0x180101bd0  maxsd   xmm1, qword ptr [rax+18h]
0x180101bd5  movsd   qword ptr [rbx+18h], xmm1
0x180101bda  mov     rax, [rbp+57h+var_D0]
0x180101bde  mov     [rdi], rax
0x180101be1  mov     rcx, [rbp+57h+var_B0]
0x180101be5  test    rcx, rcx
0x180101be8  jz      loc_180101A3D
0x180101bee  mov     [rbp+57h+var_B0], 0
0x180101bf6  jmp     loc_180101A2F
0x180101bfb  lea     rcx, [rbp+57h+var_D0]
0x180101bff  call    cs:__imp_?Create@IEmptyPath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@XZ; GEL::IEmptyPath::Create(void)
0x180101c05  mov     rcx, [rax]
0x180101c08  test    rcx, rcx
0x180101c0b  mov     [rdi], rcx
0x180101c0e  jz      short loc_180101C1C
0x180101c10  mov     rax, [rcx]
0x180101c13  mov     rax, [rax]
0x180101c16  call    cs:__guard_dispatch_icall_fptr
0x180101c1c  mov     rcx, [rbp+57h+var_D0]
0x180101c20  test    rcx, rcx
0x180101c23  jz      short loc_180101C32
0x180101c25  mov     rax, [rcx]
0x180101c28  mov     rax, [rax+8]
0x180101c2c  call    cs:__guard_dispatch_icall_fptr
0x180101c32  mov     rax, rdi
0x180101c35  lea     r11, [rsp+100h+var_20]
0x180101c3d  mov     rbx, [r11+38h]
0x180101c41  mov     rsi, [r11+40h]
0x180101c45  movaps  xmm6, xmmword ptr [r11-10h]
0x180101c4a  mov     rsp, r11
0x180101c4d  pop     r15
0x180101c4f  pop     r14
0x180101c51  pop     r13
0x180101c53  pop     rdi
0x180101c54  pop     rbp
0x180101c55  retn
0x180101c56  xor     edx, edx
0x180101c58  mov     ecx, 1E3C3840h
0x180101c5d  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x180101c63  nop
0x180101c64  xor     edx, edx
0x180101c66  mov     ecx, 1E3C3843h
0x180101c6b  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
```
