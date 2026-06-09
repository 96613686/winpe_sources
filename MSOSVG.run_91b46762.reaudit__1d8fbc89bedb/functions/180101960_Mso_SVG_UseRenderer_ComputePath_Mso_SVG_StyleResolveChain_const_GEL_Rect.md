# Mso::SVG::UseRenderer::ComputePath(Mso::SVG::StyleResolveChain const &,GEL::Rect *)

- ea: `0x180101960`
- end: `0x180101c92`
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
- `0x180041e94`
- `0x180043594`
- `0x1800435fc`
- `0x180043c28`
- `0x1800447d0`
- `0x18004c058`
- `0x18004f538`
- `0x1800f5db0`
- `0x180101960`
- `0x1801395e4`
- `0x18013e0c0`
- `0x18013f810`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180101c7d`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180101c8b`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180101c7d`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180101c8b`
- `gfx!?Create@IEmptyPath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@XZ` at `0x180101a29`
- `gfx!?Create@IEmptyPath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@XZ` at `0x180101c1f`
- `gfx!?Create@IEmptyPath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@XZ` at `0x180101a29`
- `gfx!?Create@IEmptyPath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@XZ` at `0x180101c1f`

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
  __int64 *v16; // rdx
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
    JUMPOUT(0x180101C91LL);
  }
  _castguard_slow_path_check_user_handled(*v8, 6592, 0);
  if ( !Mso::SVG::RenderableRenderer::IsRenderingEnabled(this)
    || !v8[57]
    || (Renderable = Mso::SVG::Environment::QueryRenderable(*(_QWORD *)(*((_QWORD *)this + 3) + 64LL))) == 0 )
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
      v16 = (__int64 *)(v15 + 392);
    }
    else if ( !*(_BYTE *)(v27 + 24) || (v16 = Mso::SVG::StyleMetaData<33>::inherit, !*(_QWORD *)(v27 + 8)) )
    {
      v16 = (__int64 *)&Mso::SVG::StyleMetaData<33>::initial;
    }
    if ( !*((_BYTE *)v16 + 32) )
    {
      if ( v26 )
        v17 = Mso::SVG::StyleResolveChain::Get<33>();
      else
        v17 = Mso::SVG::StyleResolveChain::GetNormal<33>(&v26, *(_QWORD *)(v27 + 8));
      v16 = (__int64 *)v17;
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
0x180101960  mov     rax, rsp
0x180101963  mov     [rax+10h], rbx
0x180101967  mov     [rax+18h], rsi
0x18010196b  push    rbp
0x18010196c  push    rdi
0x18010196d  push    r13
0x18010196f  push    r14
0x180101971  push    r15
0x180101973  lea     rbp, [rax-5Fh]
0x180101977  sub     rsp, 0E0h
0x18010197e  movaps  xmmword ptr [rax-38h], xmm6
0x180101982  mov     rbx, r9
0x180101985  mov     r13, r8
0x180101988  mov     rdi, rdx
0x18010198b  mov     rsi, rcx
0x18010198e  mov     r14, [rcx+10h]
0x180101992  test    r14, r14
0x180101995  jz      loc_180101C84
0x18010199b  xor     r8d, r8d
0x18010199e  mov     edx, 19C0h
0x1801019a3  mov     rcx, [r14]
0x1801019a6  call    __castguard_slow_path_check_user_handled
0x1801019ab  lea     r15, [r14+1B8h]
0x1801019b2  mov     rcx, rsi; this
0x1801019b5  call    ?IsRenderingEnabled@RenderableRenderer@SVG@Mso@@QEBA_NXZ; Mso::SVG::RenderableRenderer::IsRenderingEnabled(void)
0x1801019ba  test    al, al
0x1801019bc  jz      loc_180101C1B
0x1801019c2  cmp     qword ptr [r15+10h], 0
0x1801019c7  jz      loc_180101C1B
0x1801019cd  mov     rax, [rsi+18h]
0x1801019d1  mov     rdx, r15
0x1801019d4  mov     rcx, [rax+40h]
0x1801019d8  call    ?QueryRenderable@Environment@SVG@Mso@@QEAAPEAVRenderableContext@23@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Mso::SVG::Environment::QueryRenderable(std::wstring const &)
0x1801019dd  test    rax, rax
0x1801019e0  jz      loc_180101C1B
0x1801019e6  mov     r8, [rsi+18h]
0x1801019ea  mov     rdx, rax
0x1801019ed  lea     rcx, [rbp+57h+arg_0]
0x1801019f1  call    ?Create@RenderableRenderer@SVG@Mso@@SA?AV?$TCntPtr@VRenderableRenderer@SVG@Mso@@@3@AEAVRenderableContext@23@AEAVEnvironmentRenderer@23@@Z; Mso::SVG::RenderableRenderer::Create(Mso::SVG::RenderableContext &,Mso::SVG::EnvironmentRenderer &)
0x1801019f6  nop
0x1801019f7  mov     rax, [r14]
0x1801019fa  mov     rcx, r14
0x1801019fd  mov     rax, [rax+68h]
0x180101a01  call    cs:__guard_dispatch_icall_fptr
0x180101a07  mov     [rbp+57h+var_C8], r13
0x180101a0b  mov     [rbp+57h+var_C0], rax
0x180101a0f  mov     rax, [r13+10h]
0x180101a13  mov     [rbp+57h+var_B8], rax
0x180101a17  lea     rcx, [rbp+57h+var_C8]
0x180101a1b  call    ??$Get@$0BO@@StyleResolveChain@SVG@Mso@@QEBAAEB_NXZ; Mso::SVG::StyleResolveChain::Get<30>(void)
0x180101a20  cmp     byte ptr [rax], 0
0x180101a23  jnz     short loc_180101A77
0x180101a25  lea     rcx, [rbp+57h+var_D0]
0x180101a29  call    cs:__imp_?Create@IEmptyPath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@XZ; GEL::IEmptyPath::Create(void)
0x180101a2f  mov     rcx, [rax]
0x180101a32  mov     [rdi], rcx
0x180101a35  test    rcx, rcx
0x180101a38  jz      short loc_180101A46
0x180101a3a  mov     rax, [rcx]
0x180101a3d  mov     rax, [rax]
0x180101a40  call    cs:__guard_dispatch_icall_fptr
0x180101a46  mov     rcx, [rbp+57h+var_D0]
0x180101a4a  test    rcx, rcx
0x180101a4d  jz      short loc_180101A5D
0x180101a4f  mov     rax, [rcx]
0x180101a52  mov     rax, [rax+8]
0x180101a56  call    cs:__guard_dispatch_icall_fptr
0x180101a5c  nop
0x180101a5d  mov     rcx, [rbp+57h+arg_0]
0x180101a61  test    rcx, rcx
0x180101a64  jz      loc_180101C52
0x180101a6a  mov     [rbp+57h+arg_0], 0
0x180101a72  jmp     loc_180101C45
0x180101a77  xorps   xmm0, xmm0
0x180101a7a  movups  [rbp+57h+var_A0], xmm0
0x180101a7e  xorps   xmm1, xmm1
0x180101a81  movups  [rbp+57h+var_90], xmm1
0x180101a85  test    rbx, rbx
0x180101a88  jnz     short loc_180101AF5
0x180101a8a  mov     rax, [rbp+57h+var_C0]
0x180101a8e  mov     rdx, [rax+10h]
0x180101a92  test    rdx, rdx
0x180101a95  jz      short loc_180101AA0
0x180101a97  add     rdx, 188h
0x180101a9e  jmp     short loc_180101ABB
0x180101aa0  cmp     byte ptr [rax+18h], 0
0x180101aa4  jz      short loc_180101AB4
0x180101aa6  cmp     qword ptr [rax+8], 0
0x180101aab  lea     rdx, ?inherit@?$StyleMetaData@$0CB@@SVG@Mso@@2V?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@B; std::optional<std::wstring> const Mso::SVG::StyleMetaData<33>::inherit
0x180101ab2  jnz     short loc_180101ABB
0x180101ab4  lea     rdx, ?initial@?$StyleMetaData@$0CB@@SVG@Mso@@2V?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@B; std::optional<std::wstring> const Mso::SVG::StyleMetaData<33>::initial
0x180101abb  cmp     byte ptr [rdx+20h], 0
0x180101abf  jnz     short loc_180101AE1
0x180101ac1  mov     rcx, [rbp+57h+var_C8]
0x180101ac5  test    rcx, rcx
0x180101ac8  jz      short loc_180101AD1
0x180101aca  call    ??$Get@$0CB@@StyleResolveChain@SVG@Mso@@QEBAAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; Mso::SVG::StyleResolveChain::Get<33>(void)
0x180101acf  jmp     short loc_180101ADE
0x180101ad1  mov     rdx, [rax+8]
0x180101ad5  lea     rcx, [rbp+57h+var_C8]
0x180101ad9  call    ??$GetNormal@$0CB@@StyleResolveChain@SVG@Mso@@AEBAAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBVStyle@12@@Z; Mso::SVG::StyleResolveChain::GetNormal<33>(Mso::SVG::Style const &)
0x180101ade  mov     rdx, rax
0x180101ae1  cmp     qword ptr [rdx+10h], 0
0x180101ae6  jz      short loc_180101AF5
0x180101ae8  mov     rax, [rsi+18h]
0x180101aec  mov     rcx, [rax+40h]
0x180101af0  call    ?QueryClipPath@Environment@SVG@Mso@@QEAAPEAVClipPathContext@23@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Mso::SVG::Environment::QueryClipPath(std::wstring const &)
0x180101af5  mov     rcx, [rsi+18h]; this
0x180101af9  call    ?BeginRecursion@EnvironmentRenderer@SVG@Mso@@QEAAXXZ; Mso::SVG::EnvironmentRenderer::BeginRecursion(void)
0x180101afe  mov     rcx, [rbp+57h+arg_0]
0x180101b02  test    rcx, rcx
0x180101b05  jz      loc_180101C76
0x180101b0b  mov     rax, [rcx]
0x180101b0e  lea     r9, [rbp+57h+var_A0]
0x180101b12  lea     r8, [rbp+57h+var_C8]
0x180101b16  lea     rdx, [rbp+57h+var_B0]
0x180101b1a  mov     rax, [rax+18h]
0x180101b1e  call    cs:__guard_dispatch_icall_fptr
0x180101b24  nop
0x180101b25  mov     rax, [rsi+18h]
0x180101b29  dec     dword ptr [rax]
0x180101b2b  lea     rdx, [r14+188h]; struct Mso::SVG::Length *
0x180101b32  lea     r8, [rbp+57h+var_C8]; struct Mso::SVG::StyleResolveChain *
0x180101b36  mov     rcx, [rbp+57h+var_B8]; this
0x180101b3a  call    ?ResolveLength@LengthResolver@SVG@Mso@@AEBANAEBULength@23@AEBVStyleResolveChain@23@@Z; Mso::SVG::LengthResolver::ResolveLength(Mso::SVG::Length const &,Mso::SVG::StyleResolveChain const &)
0x180101b3f  movaps  xmm6, xmm0
0x180101b42  lea     rdx, [r14+178h]; struct Mso::SVG::Length *
0x180101b49  lea     r8, [rbp+57h+var_C8]; struct Mso::SVG::StyleResolveChain *
0x180101b4d  mov     rcx, [rbp+57h+var_B8]; this
0x180101b51  call    ?ResolveLength@LengthResolver@SVG@Mso@@AEBANAEBULength@23@AEBVStyleResolveChain@23@@Z; Mso::SVG::LengthResolver::ResolveLength(Mso::SVG::Length const &,Mso::SVG::StyleResolveChain const &)
0x180101b56  movdqa  xmm1, cs:__xmm@00000000000000003ff0000000000000
0x180101b5e  movups  [rbp+57h+var_80], xmm1
0x180101b62  movdqa  xmm2, cs:__xmm@3ff00000000000000000000000000000
0x180101b6a  movups  [rbp+57h+var_70], xmm2
0x180101b6e  movsd   [rbp+57h+var_60], xmm0
0x180101b73  movsd   [rbp+57h+var_58], xmm6
0x180101b78  lea     rdx, [rsi+20h]
0x180101b7c  lea     rcx, [rbp+57h+var_80]
0x180101b80  call    ??$?XNN$0A@@Math@@YAAEAU?$TAffine3x3@N@0@AEAU10@AEBU10@@Z; Math::operator*=<double,double,0>(Math::TAffine3x3<double> &,Math::TAffine3x3<double> const &)
0x180101b85  lea     r9, [rbp+57h+var_80]
0x180101b89  mov     [rsp+100h+var_D8], r9
0x180101b8e  lea     rax, [rbp+57h+var_A0]
0x180101b92  mov     [rsp+100h+var_E0], rax
0x180101b97  lea     r9, [rbp+57h+var_C8]
0x180101b9b  mov     r8, [rbp+57h+var_B0]
0x180101b9f  lea     rdx, [rbp+57h+var_D0]
0x180101ba3  mov     rcx, rsi
0x180101ba6  call    ?ApplyStandardPathEffects@RenderableRenderer@SVG@Mso@@QEBA?AV?$TCntPtr@$$CBUIPath@GEL@@@3@AEBUIPath@GEL@@AEBVStyleResolveChain@23@PEBURect@6@PEBU?$TAffine3x3@N@Math@@@Z; Mso::SVG::RenderableRenderer::ApplyStandardPathEffects(GEL::IPath const &,Mso::SVG::StyleResolveChain const &,GEL::Rect const *,Math::TAffine3x3<double> const *)
0x180101bab  test    rbx, rbx
0x180101bae  jz      short loc_180101BFA
0x180101bb0  lea     r8, [rbp+57h+var_80]
0x180101bb4  lea     rdx, [rbp+57h+var_50]
0x180101bb8  lea     rcx, [rbp+57h+var_A0]
0x180101bbc  call    ?GetTransformedBounds@Rect@GEL@@QEBA?AU12@AEBU?$TAffine3x3@N@Math@@@Z; GEL::Rect::GetTransformedBounds(Math::TAffine3x3<double> const &)
0x180101bc1  movsd   xmm0, qword ptr [rbx]
0x180101bc5  minsd   xmm0, qword ptr [rax]
0x180101bc9  movsd   qword ptr [rbx], xmm0
0x180101bcd  movsd   xmm1, qword ptr [rbx+10h]
0x180101bd2  maxsd   xmm1, qword ptr [rax+10h]
0x180101bd7  movsd   qword ptr [rbx+10h], xmm1
0x180101bdc  movsd   xmm0, qword ptr [rbx+8]
0x180101be1  minsd   xmm0, qword ptr [rax+8]
0x180101be6  movsd   qword ptr [rbx+8], xmm0
0x180101beb  movsd   xmm1, qword ptr [rbx+18h]
0x180101bf0  maxsd   xmm1, qword ptr [rax+18h]
0x180101bf5  movsd   qword ptr [rbx+18h], xmm1
0x180101bfa  mov     rax, [rbp+57h+var_D0]
0x180101bfe  mov     [rdi], rax
0x180101c01  mov     rcx, [rbp+57h+var_B0]
0x180101c05  test    rcx, rcx
0x180101c08  jz      loc_180101A5D
0x180101c0e  mov     [rbp+57h+var_B0], 0
0x180101c16  jmp     loc_180101A4F
0x180101c1b  lea     rcx, [rbp+57h+var_D0]
0x180101c1f  call    cs:__imp_?Create@IEmptyPath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@XZ; GEL::IEmptyPath::Create(void)
0x180101c25  mov     rcx, [rax]
0x180101c28  test    rcx, rcx
0x180101c2b  mov     [rdi], rcx
0x180101c2e  jz      short loc_180101C3C
0x180101c30  mov     rax, [rcx]
0x180101c33  mov     rax, [rax]
0x180101c36  call    cs:__guard_dispatch_icall_fptr
0x180101c3c  mov     rcx, [rbp+57h+var_D0]
0x180101c40  test    rcx, rcx
0x180101c43  jz      short loc_180101C52
0x180101c45  mov     rax, [rcx]
0x180101c48  mov     rax, [rax+8]
0x180101c4c  call    cs:__guard_dispatch_icall_fptr
0x180101c52  mov     rax, rdi
0x180101c55  lea     r11, [rsp+100h+var_20]
0x180101c5d  mov     rbx, [r11+38h]
0x180101c61  mov     rsi, [r11+40h]
0x180101c65  movaps  xmm6, xmmword ptr [r11-10h]
0x180101c6a  mov     rsp, r11
0x180101c6d  pop     r15
0x180101c6f  pop     r14
0x180101c71  pop     r13
0x180101c73  pop     rdi
0x180101c74  pop     rbp
0x180101c75  retn
0x180101c76  xor     edx, edx
0x180101c78  mov     ecx, 1E3C3840h
0x180101c7d  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x180101c83  nop
0x180101c84  xor     edx, edx
0x180101c86  mov     ecx, 1E3C3843h
0x180101c8b  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
```
