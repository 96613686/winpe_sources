# Mso::SVG::MaskRenderer::ComputeMask(Mso::SVG::StyleResolveChain const &,GEL::Rect const *)

- ea: `0x1801028f0`
- end: `0x180102d52`
- name: `?ComputeMask@MaskRenderer@SVG@Mso@@QEAA?AV?$TCntPtr@UIEffect@GEL@@@3@AEBVStyleResolveChain@23@PEBURect@GEL@@@Z`
- size: `1122`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180042308`

## callees

- `0x18003fd34`
- `0x18004e760`
- `0x1801028f0`
- `0x1801395e4`
- `0x18013e0c0`
- `0x18013f7e8`
- `0x18013f810`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180102d3d`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180102d4b`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180102d3d`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180102d4b`
- `gfx!?Create@IEffectClip@GEL@@SA?AV?$TCntPtr@UIEffectClip@GEL@@@Ofc@@AEBUIEffect@2@AEBU?$TRect@N@Math@@W4CombineMode@2@@Z` at `0x180102bce`
- `gfx!?Create@IEffectClip@GEL@@SA?AV?$TCntPtr@UIEffectClip@GEL@@@Ofc@@AEBUIEffect@2@AEBU?$TRect@N@Math@@W4CombineMode@2@@Z` at `0x180102bce`
- `gfx!?Create@IEffectAlphaModulateBinary@GEL@@SA?AV?$TCntPtr@UIEffectAlphaModulateBinary@GEL@@@Ofc@@AEBUIEffect@2@0@Z` at `0x180102c5d`
- `gfx!?Create@IEffectAlphaModulateBinary@GEL@@SA?AV?$TCntPtr@UIEffectAlphaModulateBinary@GEL@@@Ofc@@AEBUIEffect@2@0@Z` at `0x180102c5d`
- `gfx!?Create@IEffectLuminanceToAlpha@GEL@@SA?AV?$TCntPtr@UIEffectLuminanceToAlpha@GEL@@@Ofc@@AEBUIEffect@2@W4ColorSpace@2@@Z` at `0x180102bff`
- `gfx!?Create@IEffectLuminanceToAlpha@GEL@@SA?AV?$TCntPtr@UIEffectLuminanceToAlpha@GEL@@@Ofc@@AEBUIEffect@2@W4ColorSpace@2@@Z` at `0x180102bff`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
_QWORD *__fastcall Mso::SVG::MaskRenderer::ComputeMask(__int64 a1, _QWORD *a2, __int64 a3, double *a4)
{
  __int64 v8; // rbx
  int v9; // esi
  int v10; // r12d
  Mso::SVG::LengthResolver *p_si128; // rsi
  __int64 v12; // rax
  __m128i *v13; // rsi
  __int64 v14; // rax
  double v15; // xmm6_8
  double v16; // xmm7_8
  double v17; // xmm8_8
  double v18; // xmm0_8
  double v19; // xmm9_8
  double v20; // xmm2_8
  double v21; // xmm1_8
  __int64 v22; // rcx
  double v23; // xmm4_8
  double v24; // xmm2_8
  double v25; // xmm3_8
  _QWORD *EffectOrEmptyContainer; // rax
  __int64 *v27; // rax
  __int64 v28; // r9
  __int64 v29; // rbx
  __int64 v30; // rcx
  __int64 v31; // rcx
  _QWORD *v32; // rax
  __int64 *v33; // rax
  __int64 v34; // rsi
  __int64 v35; // rdx
  __int64 v36; // rdi
  _QWORD *v37; // rax
  void (__fastcall ***v38)(_QWORD); // r15
  __int64 v40; // [rsp+38h] [rbp-D0h] BYREF
  __int128 v41; // [rsp+40h] [rbp-C8h] BYREF
  _QWORD v42[2]; // [rsp+50h] [rbp-B8h] BYREF
  Mso::SVG::LengthResolver *v43; // [rsp+60h] [rbp-A8h]
  __int64 v44; // [rsp+68h] [rbp-A0h]
  double v45; // [rsp+78h] [rbp-90h] BYREF
  __int128 v46; // [rsp+80h] [rbp-88h]
  double v47; // [rsp+90h] [rbp-78h]
  double v48; // [rsp+98h] [rbp-70h]
  double v49; // [rsp+A0h] [rbp-68h]
  __m128i si128; // [rsp+A8h] [rbp-60h] BYREF
  double v51; // [rsp+B8h] [rbp-50h]
  _QWORD v52[13]; // [rsp+C0h] [rbp-48h] BYREF
  __int64 v53; // [rsp+158h] [rbp+50h] BYREF

  v8 = *(_QWORD *)(a1 + 16);
  if ( !v8 )
  {
LABEL_44:
    CrashWithRecovery(0x1E3C3843u, 0);
    JUMPOUT(0x180102D51LL);
  }
  _castguard_slow_path_check_user_handled(*(_QWORD *)v8, 8048, 0);
  v9 = *(_DWORD *)(v8 + 328);
  LODWORD(v53) = v9;
  v10 = *(_DWORD *)(v8 + 332);
  if ( !*(_BYTE *)(v8 + 400) )
  {
    *a2 = 0;
    return a2;
  }
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v51 = sqrt_0(1.0);
  if ( v9 )
    p_si128 = (Mso::SVG::LengthResolver *)&si128;
  else
    p_si128 = *(Mso::SVG::LengthResolver **)(a3 + 16);
  v12 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 104LL))(v8);
  v42[0] = 0;
  v42[1] = v12;
  v43 = p_si128;
  if ( v10 )
    v13 = &si128;
  else
    v13 = *(__m128i **)(a3 + 16);
  v14 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 104LL))(v8);
  v52[0] = 0;
  v52[1] = v14;
  v52[2] = v13;
  v15 = Mso::SVG::LengthResolver::ResolveLength(
          v43,
          (const struct Mso::SVG::Length *)(v8 + 336),
          (const struct Mso::SVG::StyleResolveChain *)v42);
  v16 = Mso::SVG::LengthResolver::ResolveLength(
          v43,
          (const struct Mso::SVG::Length *)(v8 + 352),
          (const struct Mso::SVG::StyleResolveChain *)v42);
  v17 = Mso::SVG::LengthResolver::ResolveLength(
          v43,
          (const struct Mso::SVG::Length *)(v8 + 368),
          (const struct Mso::SVG::StyleResolveChain *)v42);
  v18 = Mso::SVG::LengthResolver::ResolveLength(
          v43,
          (const struct Mso::SVG::Length *)(v8 + 384),
          (const struct Mso::SVG::StyleResolveChain *)v42);
  v19 = v18;
  if ( (_DWORD)v53 == 1 )
  {
    v20 = a4[2] - *a4;
    v17 = v17 * v20;
    v21 = a4[3] - a4[1];
    v19 = v18 * v21;
    v15 = v15 * v20 + *a4;
    v16 = v16 * v21 + a4[1];
  }
  v41 = 0;
  v22 = *(_QWORD *)(a1 + 32);
  if ( !v22 )
  {
    CrashWithRecovery(0x1E3C3840u, 0);
    goto LABEL_44;
  }
  (*(void (__fastcall **)(__int64, __int128 *, _QWORD *, _QWORD, _QWORD))(*(_QWORD *)v22 + 32LL))(v22, &v41, v52, 0, 0);
  v44 = 0;
  if ( v10 == 1 )
  {
    v23 = a4[1];
    v24 = a4[3] - v23;
    v25 = *a4;
    v45 = a4[2] - *a4;
    v46 = 0;
    v47 = v24;
    v48 = v25 + 0.0;
    v49 = v23 + 0.0;
    EffectOrEmptyContainer = (_QWORD *)GEL::EffectAccumulator::GetEffectOrEmptyContainer(&v41, &v40);
    v27 = (__int64 *)Mso::SVG::ApplyTransform(&v53, *EffectOrEmptyContainer, &v45);
    v29 = *v27;
    *v27 = 0;
    v44 = v29;
    v30 = v53;
    if ( v53 )
    {
      v53 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 8LL))(v30);
    }
    v31 = v40;
  }
  else
  {
    v32 = (_QWORD *)GEL::EffectAccumulator::GetEffectOrEmptyContainer(&v41, &v53);
    v29 = *v32;
    if ( *v32 )
      (**(void (__fastcall ***)(_QWORD))v29)(*v32);
    v44 = v29;
    v31 = v53;
  }
  if ( v31 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 8LL))(v31);
  v45 = v15;
  *(double *)&v46 = v16;
  *((double *)&v46 + 1) = v17 + v15;
  v47 = v19 + v16;
  LOBYTE(v28) = 1;
  v33 = (__int64 *)GEL::IEffectClip::Create(&v53, v29, &v45, v28);
  v34 = *v33;
  *v33 = 0;
  v52[3] = v34;
  if ( v53 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 8LL))(v53);
  v36 = *(_QWORD *)GEL::IEffectLuminanceToAlpha::Create(&v40, v34, 0);
  v52[4] = v36;
  if ( v36 )
    (**(void (__fastcall ***)(__int64))v36)(v36);
  if ( v40 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 8LL))(v40);
  LOBYTE(v35) = 1;
  if ( (*(unsigned __int8 (__fastcall **)(__int64, __int64))(*(_QWORD *)v34 + 88LL))(v34, v35) )
  {
    *a2 = v36;
  }
  else
  {
    v37 = (_QWORD *)GEL::IEffectAlphaModulateBinary::Create(&v53, v36, v34);
    v38 = (void (__fastcall ***)(_QWORD))*v37;
    if ( *v37 )
      (**v38)(*v37);
    if ( v53 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 8LL))(v53);
    *a2 = v38;
    if ( v36 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 8LL))(v36);
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 8LL))(v34);
  if ( v29 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 8LL))(v29);
  if ( *((_QWORD *)&v41 + 1) )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v41 + 1) + 8LL))(*((_QWORD *)&v41 + 1));
  if ( (_QWORD)v41 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v41 + 8LL))(v41);
  return a2;
}

```

## disassembly

```asm
0x1801028f0  mov     rax, rsp
0x1801028f3  mov     [rax+10h], rbx
0x1801028f7  mov     [rax+18h], rsi
0x1801028fb  mov     [rax+20h], rdi
0x1801028ff  push    rbp
0x180102900  push    r12
0x180102902  push    r13
0x180102904  push    r14
0x180102906  push    r15
0x180102908  lea     rbp, [rax-48h]
0x18010290c  sub     rsp, 120h
0x180102913  movaps  xmmword ptr [rax-38h], xmm6
0x180102917  movaps  xmmword ptr [rax-48h], xmm7
0x18010291b  movaps  xmmword ptr [rax-58h], xmm8
0x180102920  movaps  xmmword ptr [rax-68h], xmm9
0x180102925  mov     rdi, r9
0x180102928  mov     r15, r8
0x18010292b  mov     r14, rdx
0x18010292e  mov     r13, rcx
0x180102931  mov     rbx, [rcx+10h]
0x180102935  test    rbx, rbx
0x180102938  jz      loc_180102D44
0x18010293e  xor     r8d, r8d
0x180102941  mov     edx, 1F70h
0x180102946  mov     rcx, [rbx]
0x180102949  call    __castguard_slow_path_check_user_handled
0x18010294e  mov     esi, [rbx+148h]
0x180102954  mov     dword ptr [rbp+40h+arg_0], esi
0x180102957  mov     r12d, [rbx+14Ch]
0x18010295e  cmp     byte ptr [rbx+190h], 0
0x180102965  jnz     short loc_180102973
0x180102967  mov     qword ptr [r14], 0
0x18010296e  jmp     loc_180102CFE
0x180102973  movdqa  xmm0, cs:__xmm@3ff00000000000003ff0000000000000
0x18010297b  movups  [rbp+40h+var_A0], xmm0
0x18010297f  movsd   xmm0, cs:__real@3ff0000000000000; X
0x180102987  call    sqrt_0
0x18010298c  movsd   [rbp+40h+var_90], xmm0
0x180102991  test    esi, esi
0x180102993  jnz     short loc_18010299B
0x180102995  mov     rsi, [r15+10h]
0x180102999  jmp     short loc_18010299F
0x18010299b  lea     rsi, [rbp+40h+var_A0]
0x18010299f  mov     rax, [rbx]
0x1801029a2  mov     rcx, rbx
0x1801029a5  mov     rax, [rax+68h]
0x1801029a9  call    cs:__guard_dispatch_icall_fptr
0x1801029af  mov     [rsp+140h+var_F8], 0
0x1801029b8  mov     [rsp+140h+var_F0], rax
0x1801029bd  mov     [rsp+140h+var_E8], rsi
0x1801029c2  test    r12d, r12d
0x1801029c5  jnz     short loc_1801029CD
0x1801029c7  mov     rsi, [r15+10h]
0x1801029cb  jmp     short loc_1801029D1
0x1801029cd  lea     rsi, [rbp+40h+var_A0]
0x1801029d1  mov     rax, [rbx]
0x1801029d4  mov     rcx, rbx
0x1801029d7  mov     rax, [rax+68h]
0x1801029db  call    cs:__guard_dispatch_icall_fptr
0x1801029e1  mov     [rbp+40h+var_88], 0
0x1801029e9  mov     [rbp+40h+var_80], rax
0x1801029ed  mov     [rbp+40h+var_78], rsi
0x1801029f1  lea     rdx, [rbx+150h]; struct Mso::SVG::Length *
0x1801029f8  lea     r8, [rsp+140h+var_F8]; struct Mso::SVG::StyleResolveChain *
0x1801029fd  mov     rcx, [rsp+140h+var_E8]; this
0x180102a02  call    ?ResolveLength@LengthResolver@SVG@Mso@@AEBANAEBULength@23@AEBVStyleResolveChain@23@@Z; Mso::SVG::LengthResolver::ResolveLength(Mso::SVG::Length const &,Mso::SVG::StyleResolveChain const &)
0x180102a07  movaps  xmm6, xmm0
0x180102a0a  lea     rdx, [rbx+160h]; struct Mso::SVG::Length *
0x180102a11  lea     r8, [rsp+140h+var_F8]; struct Mso::SVG::StyleResolveChain *
0x180102a16  mov     rcx, [rsp+140h+var_E8]; this
0x180102a1b  call    ?ResolveLength@LengthResolver@SVG@Mso@@AEBANAEBULength@23@AEBVStyleResolveChain@23@@Z; Mso::SVG::LengthResolver::ResolveLength(Mso::SVG::Length const &,Mso::SVG::StyleResolveChain const &)
0x180102a20  movaps  xmm7, xmm0
0x180102a23  lea     rdx, [rbx+170h]; struct Mso::SVG::Length *
0x180102a2a  lea     r8, [rsp+140h+var_F8]; struct Mso::SVG::StyleResolveChain *
0x180102a2f  mov     rcx, [rsp+140h+var_E8]; this
0x180102a34  call    ?ResolveLength@LengthResolver@SVG@Mso@@AEBANAEBULength@23@AEBVStyleResolveChain@23@@Z; Mso::SVG::LengthResolver::ResolveLength(Mso::SVG::Length const &,Mso::SVG::StyleResolveChain const &)
0x180102a39  movaps  xmm8, xmm0
0x180102a3d  lea     rdx, [rbx+180h]; struct Mso::SVG::Length *
0x180102a44  lea     r8, [rsp+140h+var_F8]; struct Mso::SVG::StyleResolveChain *
0x180102a49  mov     rcx, [rsp+140h+var_E8]; this
0x180102a4e  call    ?ResolveLength@LengthResolver@SVG@Mso@@AEBANAEBULength@23@AEBVStyleResolveChain@23@@Z; Mso::SVG::LengthResolver::ResolveLength(Mso::SVG::Length const &,Mso::SVG::StyleResolveChain const &)
0x180102a53  movaps  xmm9, xmm0
0x180102a57  cmp     dword ptr [rbp+40h+arg_0], 1
0x180102a5b  jnz     short loc_180102A8B
0x180102a5d  movsd   xmm2, qword ptr [rdi+10h]
0x180102a62  subsd   xmm2, qword ptr [rdi]
0x180102a66  mulsd   xmm8, xmm2
0x180102a6b  movsd   xmm1, qword ptr [rdi+18h]
0x180102a70  subsd   xmm1, qword ptr [rdi+8]
0x180102a75  mulsd   xmm9, xmm1
0x180102a7a  mulsd   xmm6, xmm2
0x180102a7e  addsd   xmm6, qword ptr [rdi]
0x180102a82  mulsd   xmm7, xmm1
0x180102a86  addsd   xmm7, qword ptr [rdi+8]
0x180102a8b  xorps   xmm0, xmm0
0x180102a8e  movdqu  [rsp+140h+var_110+8], xmm0
0x180102a94  mov     rcx, [r13+20h]
0x180102a98  xor     r13d, r13d
0x180102a9b  test    rcx, rcx
0x180102a9e  jz      loc_180102D36
0x180102aa4  mov     rax, [rcx]
0x180102aa7  mov     [rsp+140h+var_120], r13
0x180102aac  xor     r9d, r9d
0x180102aaf  lea     r8, [rbp+40h+var_88]
0x180102ab3  lea     rdx, [rsp+140h+var_110+8]
0x180102ab8  mov     rax, [rax+20h]
0x180102abc  call    cs:__guard_dispatch_icall_fptr
0x180102ac2  mov     [rsp+140h+var_E0], r13
0x180102ac7  lea     rcx, [rsp+140h+var_110+8]
0x180102acc  cmp     r12d, 1
0x180102ad0  jnz     loc_180102B62
0x180102ad6  movsd   xmm4, qword ptr [rdi+8]
0x180102adb  movsd   xmm2, qword ptr [rdi+18h]
0x180102ae0  subsd   xmm2, xmm4
0x180102ae4  movsd   xmm3, qword ptr [rdi]
0x180102ae8  movsd   xmm0, qword ptr [rdi+10h]
0x180102aed  subsd   xmm0, xmm3
0x180102af1  movsd   qword ptr [rsp+140h+var_D0], xmm0
0x180102af7  xorps   xmm1, xmm1
0x180102afa  movups  [rsp+140h+var_D0+8], xmm1
0x180102aff  movsd   [rbp+40h+var_B8], xmm2
0x180102b04  xorps   xmm0, xmm0
0x180102b07  addsd   xmm3, xmm0
0x180102b0b  movsd   [rbp+40h+var_B0], xmm3
0x180102b10  addsd   xmm4, xmm0
0x180102b14  movsd   [rbp+40h+var_A8], xmm4
0x180102b19  lea     rdx, [rsp+140h+var_110]
0x180102b1e  call    ?GetEffectOrEmptyContainer@EffectAccumulator@GEL@@QEAA?AV?$TCntPtr@$$CBUIEffect@GEL@@@Ofc@@XZ; GEL::EffectAccumulator::GetEffectOrEmptyContainer(void)
0x180102b23  lea     r8, [rsp+140h+var_D0]
0x180102b28  mov     rdx, [rax]
0x180102b2b  lea     rcx, [rbp+40h+arg_0]
0x180102b2f  nop
0x180102b30  call    ?ApplyTransform@SVG@Mso@@YA?AV?$TCntPtr@$$CBUIEffect@GEL@@@2@AEBUIEffect@GEL@@AEBU?$TAffine3x3@N@Math@@@Z; Mso::SVG::ApplyTransform(GEL::IEffect const &,Math::TAffine3x3<double> const &)
0x180102b35  mov     rbx, [rax]
0x180102b38  mov     [rax], r13
0x180102b3b  mov     [rsp+140h+var_E0], rbx
0x180102b40  mov     rcx, [rbp+40h+arg_0]
0x180102b44  test    rcx, rcx
0x180102b47  jz      short loc_180102B5B
0x180102b49  mov     [rbp+40h+arg_0], r13
0x180102b4d  mov     rax, [rcx]
0x180102b50  mov     rax, [rax+8]
0x180102b54  call    cs:__guard_dispatch_icall_fptr
0x180102b5a  nop
0x180102b5b  mov     rcx, qword ptr [rsp+140h+var_110]
0x180102b60  jmp     short loc_180102B8B
0x180102b62  lea     rdx, [rbp+40h+arg_0]
0x180102b66  call    ?GetEffectOrEmptyContainer@EffectAccumulator@GEL@@QEAA?AV?$TCntPtr@$$CBUIEffect@GEL@@@Ofc@@XZ; GEL::EffectAccumulator::GetEffectOrEmptyContainer(void)
0x180102b6b  mov     rbx, [rax]
0x180102b6e  test    rbx, rbx
0x180102b71  jz      short loc_180102B82
0x180102b73  mov     rax, [rbx]
0x180102b76  mov     rcx, rbx
0x180102b79  mov     rax, [rax]
0x180102b7c  call    cs:__guard_dispatch_icall_fptr
0x180102b82  mov     [rsp+140h+var_E0], rbx
0x180102b87  mov     rcx, [rbp+40h+arg_0]
0x180102b8b  test    rcx, rcx
0x180102b8e  jz      short loc_180102B9D
0x180102b90  mov     rax, [rcx]
0x180102b93  mov     rax, [rax+8]
0x180102b97  call    cs:__guard_dispatch_icall_fptr
0x180102b9d  movsd   qword ptr [rsp+140h+var_D0], xmm6
0x180102ba3  movsd   qword ptr [rsp+140h+var_D0+8], xmm7
0x180102ba9  addsd   xmm8, xmm6
0x180102bae  movsd   [rbp+40h+var_C0], xmm8
0x180102bb4  addsd   xmm9, xmm7
0x180102bb9  movsd   [rbp+40h+var_B8], xmm9
0x180102bbf  mov     r9b, 1
0x180102bc2  lea     r8, [rsp+140h+var_D0]
0x180102bc7  mov     rdx, rbx
0x180102bca  lea     rcx, [rbp+40h+arg_0]
0x180102bce  call    cs:__imp_?Create@IEffectClip@GEL@@SA?AV?$TCntPtr@UIEffectClip@GEL@@@Ofc@@AEBUIEffect@2@AEBU?$TRect@N@Math@@W4CombineMode@2@@Z; GEL::IEffectClip::Create(GEL::IEffect const &,Math::TRect<double> const &,GEL::CombineMode)
0x180102bd4  mov     rsi, [rax]
0x180102bd7  mov     [rax], r13
0x180102bda  mov     [rbp+40h+var_70], rsi
0x180102bde  mov     rcx, [rbp+40h+arg_0]
0x180102be2  test    rcx, rcx
0x180102be5  jz      short loc_180102BF4
0x180102be7  mov     rax, [rcx]
0x180102bea  mov     rax, [rax+8]
0x180102bee  call    cs:__guard_dispatch_icall_fptr
0x180102bf4  xor     r8d, r8d
0x180102bf7  mov     rdx, rsi
0x180102bfa  lea     rcx, [rsp+140h+var_110]
0x180102bff  call    cs:__imp_?Create@IEffectLuminanceToAlpha@GEL@@SA?AV?$TCntPtr@UIEffectLuminanceToAlpha@GEL@@@Ofc@@AEBUIEffect@2@W4ColorSpace@2@@Z; GEL::IEffectLuminanceToAlpha::Create(GEL::IEffect const &,GEL::ColorSpace)
0x180102c05  mov     rdi, [rax]
0x180102c08  mov     [rbp+40h+var_68], rdi
0x180102c0c  test    rdi, rdi
0x180102c0f  jz      short loc_180102C21
0x180102c11  mov     rax, [rdi]
0x180102c14  mov     rcx, rdi
0x180102c17  mov     rax, [rax]
0x180102c1a  call    cs:__guard_dispatch_icall_fptr
0x180102c20  nop
0x180102c21  mov     rcx, qword ptr [rsp+140h+var_110]
0x180102c26  test    rcx, rcx
0x180102c29  jz      short loc_180102C38
0x180102c2b  mov     rax, [rcx]
0x180102c2e  mov     rax, [rax+8]
0x180102c32  call    cs:__guard_dispatch_icall_fptr
0x180102c38  mov     rax, [rsi]
0x180102c3b  mov     dl, 1
0x180102c3d  mov     rcx, rsi
0x180102c40  mov     rax, [rax+58h]
0x180102c44  call    cs:__guard_dispatch_icall_fptr
0x180102c4a  test    al, al
0x180102c4c  jz      short loc_180102C53
0x180102c4e  mov     [r14], rdi
0x180102c51  jmp     short loc_180102CA9
0x180102c53  mov     r8, rsi
0x180102c56  mov     rdx, rdi
0x180102c59  lea     rcx, [rbp+40h+arg_0]
0x180102c5d  call    cs:__imp_?Create@IEffectAlphaModulateBinary@GEL@@SA?AV?$TCntPtr@UIEffectAlphaModulateBinary@GEL@@@Ofc@@AEBUIEffect@2@0@Z; GEL::IEffectAlphaModulateBinary::Create(GEL::IEffect const &,GEL::IEffect const &)
0x180102c63  mov     r15, [rax]
0x180102c66  test    r15, r15
0x180102c69  jz      short loc_180102C7A
0x180102c6b  mov     rax, [r15]
0x180102c6e  mov     rcx, r15
0x180102c71  mov     rax, [rax]
0x180102c74  call    cs:__guard_dispatch_icall_fptr
0x180102c7a  mov     rcx, [rbp+40h+arg_0]
0x180102c7e  test    rcx, rcx
0x180102c81  jz      short loc_180102C90
0x180102c83  mov     rax, [rcx]
0x180102c86  mov     rax, [rax+8]
0x180102c8a  call    cs:__guard_dispatch_icall_fptr
0x180102c90  mov     [r14], r15
0x180102c93  test    rdi, rdi
0x180102c96  jz      short loc_180102CA9
0x180102c98  mov     rax, [rdi]
0x180102c9b  mov     rcx, rdi
0x180102c9e  mov     rax, [rax+8]
0x180102ca2  call    cs:__guard_dispatch_icall_fptr
0x180102ca8  nop
0x180102ca9  mov     rax, [rsi]
0x180102cac  mov     rcx, rsi
0x180102caf  mov     rax, [rax+8]
0x180102cb3  call    cs:__guard_dispatch_icall_fptr
0x180102cb9  test    rbx, rbx
0x180102cbc  jz      short loc_180102CD0
0x180102cbe  mov     rax, [rbx]
0x180102cc1  mov     rcx, rbx
0x180102cc4  mov     rax, [rax+8]
0x180102cc8  call    cs:__guard_dispatch_icall_fptr
0x180102cce  nop
0x180102ccf  nop
0x180102cd0  mov     rcx, [rsp+140h+var_100]
0x180102cd5  test    rcx, rcx
0x180102cd8  jz      short loc_180102CE7
0x180102cda  mov     rax, [rcx]
0x180102cdd  mov     rax, [rax+8]
0x180102ce1  call    cs:__guard_dispatch_icall_fptr
0x180102ce7  mov     rcx, qword ptr [rsp+140h+var_110+8]
0x180102cec  test    rcx, rcx
0x180102cef  jz      short loc_180102CFE
0x180102cf1  mov     rax, [rcx]
0x180102cf4  mov     rax, [rax+8]
0x180102cf8  call    cs:__guard_dispatch_icall_fptr
0x180102cfe  mov     rax, r14
0x180102d01  lea     r11, [rsp+140h+var_20]
0x180102d09  mov     rbx, [r11+38h]
0x180102d0d  mov     rsi, [r11+40h]
0x180102d11  mov     rdi, [r11+48h]
0x180102d15  movaps  xmm6, xmmword ptr [r11-10h]
0x180102d1a  movaps  xmm7, xmmword ptr [r11-20h]
0x180102d1f  movaps  xmm8, xmmword ptr [r11-30h]
0x180102d24  movaps  xmm9, xmmword ptr [r11-40h]
0x180102d29  mov     rsp, r11
0x180102d2c  pop     r15
0x180102d2e  pop     r14
0x180102d30  pop     r13
0x180102d32  pop     r12
0x180102d34  pop     rbp
0x180102d35  retn
0x180102d36  xor     edx, edx
0x180102d38  mov     ecx, 1E3C3840h
0x180102d3d  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x180102d43  nop
0x180102d44  xor     edx, edx
0x180102d46  mov     ecx, 1E3C3843h
0x180102d4b  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
```
