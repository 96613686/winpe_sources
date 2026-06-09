# Mso::SVG::ShapeRenderer::Render(GEL::EffectAccumulator &,Mso::SVG::StyleResolveChain const &,GEL::Rect *,GEL::IColorResolver const *)

- ea: `0x18010beb0`
- end: `0x18010c62e`
- name: `?Render@ShapeRenderer@SVG@Mso@@UEAAXAEAVEffectAccumulator@GEL@@AEBVStyleResolveChain@23@PEAURect@5@PEBUIColorResolver@5@@Z`
- size: `1918`
- prototype: `void __usercall(Mso::SVG::ShapeRenderer *__hidden this@<rcx>, struct GEL::EffectAccumulator *@<rdx>, const struct Mso::SVG::StyleResolveChain *@<r8>, struct GEL::Rect *@<r9>, const struct GEL::IColorResolver *)`
- caller_count: `0`
- callee_count: `30`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800091d0`
- `0x18000d5e0`
- `0x18001aacc`
- `0x18001cd88`
- `0x180023738`
- `0x1800239c8`
- `0x1800415c0`
- `0x180041de0`
- `0x18004256c`
- `0x18004326c`
- `0x180043c10`
- `0x18004410c`
- `0x1800448b8`
- `0x18004e640`
- `0x18004e740`
- `0x1800f5d90`
- `0x18010b868`
- `0x18010b9b8`
- `0x18010beb0`
- `0x18010d1e8`
- `0x18010d244`
- `0x18010d2a0`
- `0x18010d2fc`
- `0x18010d5f4`
- `0x18010d64c`
- `0x18010d6a4`
- `0x18010d6fc`
- `0x18013d650`
- `0x18013e010`
- `0x18013f760`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18010c627`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18010c627`
- `gfx!?Create@IEffectContainer@GEL@@SA?AV?$TCntPtr@UIEffectContainer@GEL@@@Ofc@@XZ` at `0x18010c354`
- `gfx!?Create@IEffectContainer@GEL@@SA?AV?$TCntPtr@UIEffectContainer@GEL@@@Ofc@@XZ` at `0x18010c354`
- `gfx!?Create@IEffectFilledPath@GEL@@SA?AV?$TCntPtr@UIEffectFilledPath@GEL@@@Ofc@@AEBUIPath@2@AEBUIBrush@2@PEBU?$TAffine3x3@N@Math@@@Z` at `0x18010c2f9`
- `gfx!?Create@IEffectFilledPath@GEL@@SA?AV?$TCntPtr@UIEffectFilledPath@GEL@@@Ofc@@AEBUIPath@2@AEBUIBrush@2@PEBU?$TAffine3x3@N@Math@@@Z` at `0x18010c2f9`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
void __fastcall Mso::SVG::ShapeRenderer::Render(
        Mso::SVG::EnvironmentRenderer **this,
        struct GEL::EffectAccumulator *a2,
        const struct Mso::SVG::StyleResolveChain *a3,
        struct GEL::Rect *a4,
        const struct GEL::IColorResolver *a5)
{
  Mso::SVG::EnvironmentRenderer **v7; // rsi
  Mso::SVG::EnvironmentRenderer *v8; // r13
  __int64 v9; // r9
  __int64 v10; // rax
  wchar_t **v11; // rax
  __int64 v12; // rax
  __int128 *v13; // rax
  __int64 v14; // rax
  __int64 *v15; // rax
  struct GEL::IPath *v16; // rdi
  bool v17; // r14
  __int64 v18; // rdx
  __int64 v19; // rax
  __int64 *v20; // rbx
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 *v23; // r12
  __int64 v24; // rax
  __int64 v25; // r15
  wchar_t *v26; // r11
  __int64 *v27; // r15
  __int64 v28; // rax
  __int64 v29; // rax
  wchar_t **v30; // rax
  char v31; // al
  struct GEL::IColorResolver *v32; // r13
  __int64 v33; // rbx
  _QWORD *v34; // rax
  void (__fastcall ***v35)(_QWORD); // rsi
  __int64 v36; // rcx
  __int64 *v37; // rax
  __int64 v38; // r13
  __int64 v39; // rsi
  bool v40; // al
  __int64 *EffectOrEmptyContainer; // rax
  struct GEL::IEffect *v42; // rbx
  __int64 v43; // rcx
  bool v44; // [rsp+40h] [rbp-C0h] BYREF
  char v45; // [rsp+41h] [rbp-BFh]
  char v46; // [rsp+42h] [rbp-BEh]
  const struct Mso::SVG::StyleResolveChain *v47; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v48; // [rsp+50h] [rbp-B0h]
  __int64 v49; // [rsp+58h] [rbp-A8h]
  __int128 v50; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v51; // [rsp+70h] [rbp-90h]
  __int64 v52; // [rsp+78h] [rbp-88h] BYREF
  __int64 v53; // [rsp+80h] [rbp-80h] BYREF
  struct GEL::IEffect *v54; // [rsp+88h] [rbp-78h] BYREF
  struct GEL::IColorResolver *v55; // [rsp+90h] [rbp-70h]
  Mso::SVG::ShapeRenderer *v56; // [rsp+98h] [rbp-68h]
  struct GEL::IPath *v57; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v58; // [rsp+A8h] [rbp-58h] BYREF
  GEL::EffectAccumulator *v59; // [rsp+B0h] [rbp-50h]
  struct GEL::Rect *v60; // [rsp+B8h] [rbp-48h]
  __int128 v61[2]; // [rsp+C0h] [rbp-40h] BYREF
  int v62[6]; // [rsp+E0h] [rbp-20h] BYREF
  char v63[32]; // [rsp+F8h] [rbp-8h] BYREF
  int v64[6]; // [rsp+118h] [rbp+18h] BYREF
  char v65[32]; // [rsp+130h] [rbp+30h] BYREF

  v60 = a4;
  v59 = a2;
  v7 = this;
  v56 = (Mso::SVG::ShapeRenderer *)this;
  v55 = a5;
  v8 = this[2];
  if ( !v8 )
  {
    CrashWithRecovery(0x1E3C3843u, 0);
    JUMPOUT(0x18010C62DLL);
  }
  _castguard_slow_path_check_user_handled(*(_QWORD *)v8, 3968, 800);
  v9 = (*(__int64 (__fastcall **)(Mso::SVG::EnvironmentRenderer *))(*(_QWORD *)v8 + 104LL))(v8);
  v47 = a3;
  v48 = v9;
  v49 = *((_QWORD *)a3 + 2);
  memset(v61, 0, sizeof(v61));
  if ( !a4 )
  {
    v10 = *(_QWORD *)(v9 + 16);
    if ( v10 )
    {
      v11 = (wchar_t **)(v10 + 392);
    }
    else if ( !*(_BYTE *)(v9 + 24) || (v11 = (wchar_t **)&Mso::SVG::StyleMetaData<33>::inherit, !*(_QWORD *)(v9 + 8)) )
    {
      v11 = &Mso::SVG::StyleMetaData<33>::initial;
    }
    if ( !*((_BYTE *)v11 + 32) )
    {
      v11 = (wchar_t **)Mso::SVG::StyleResolveChain::Get<33>(a3);
      v9 = v48;
      a3 = v47;
    }
    if ( v11[2] )
    {
      Mso::SVG::Environment::QueryClipPath(*((_QWORD *)v7[3] + 8));
      v9 = v48;
      a3 = v47;
    }
  }
  v12 = *(_QWORD *)(v9 + 16);
  if ( v12 )
  {
    v13 = (__int128 *)(v12 + 272);
  }
  else if ( !*(_BYTE *)(v9 + 24) || (v13 = (__int128 *)&Mso::SVG::StyleMetaData<36>::inherit, !*(_QWORD *)(v9 + 8)) )
  {
    v13 = &Mso::SVG::StyleMetaData<36>::initial;
  }
  if ( !*((_BYTE *)v13 + 8) )
  {
    if ( a3 )
      Mso::SVG::StyleResolveChain::Get<36>(a3);
    else
      Mso::SVG::StyleResolveChain::GetNormal<36>(&v47, *(_QWORD *)(v9 + 8));
    v9 = v48;
  }
  Mso::SVG::StyleResolveChain::SpecialResolver<2,Mso::SVG::Paint>::operator()(&v44, v64, &v47, v9);
  Mso::SVG::StyleResolveChain::SpecialResolver<10,Mso::SVG::Paint>::operator()(&v44, v62, &v47, v48);
  v14 = *(_QWORD *)(v48 + 16);
  if ( v14 )
  {
    v15 = (__int64 *)(v14 + 992);
  }
  else
  {
    v15 = &Mso::SVG::StyleMetaData<11>::initial;
    if ( *(_QWORD *)(v48 + 8) )
      v15 = (__int64 *)&Mso::SVG::StyleMetaData<11>::inherit;
  }
  if ( !*((_BYTE *)v15 + 4) )
  {
    if ( v47 )
      v15 = (__int64 *)Mso::SVG::StyleResolveChain::Get<11>();
    else
      v15 = (__int64 *)Mso::SVG::StyleResolveChain::GetNormal<11>(&v47, *(_QWORD *)(v48 + 8));
  }
  Mso::SVG::ShapeRenderer::GetEffectivePath((Mso::SVG::RenderableRenderer *)v7, &v57, &v47, *(_DWORD *)v15);
  v16 = v57;
  if ( v57 )
  {
    (*(void (__fastcall **)(struct GEL::IPath *, __int128 *))(*(_QWORD *)v57 + 104LL))(v57, v61);
    v44 = (unsigned int)(v64[0] - 3) <= 1;
    v46 = (unsigned int)(v62[0] - 3) <= 1;
    v17 = v64[0] == 2 && (unsigned int)(v62[0] - 3) <= 1 || v62[0] == 2 && (unsigned int)(v64[0] - 3) <= 1;
    v18 = v48;
    v19 = *(_QWORD *)(v48 + 16);
    if ( v19 )
    {
      v20 = (__int64 *)(v19 + 920);
    }
    else
    {
      v20 = &Mso::SVG::StyleMetaData<13>::initial;
      if ( *(_QWORD *)(v48 + 8) )
        v20 = (__int64 *)&Mso::SVG::StyleMetaData<13>::inherit;
    }
    v51 = (__int64)v20;
    if ( !*((_BYTE *)v20 + 32) )
    {
      if ( v47 )
        v21 = Mso::SVG::StyleResolveChain::Get<13>();
      else
        v21 = Mso::SVG::StyleResolveChain::GetNormal<13>(&v47, *(_QWORD *)(v48 + 8));
      v18 = v48;
      v51 = v21;
      v20 = (__int64 *)v21;
    }
    v22 = *(_QWORD *)(v18 + 16);
    if ( v22 )
    {
      v23 = (__int64 *)(v22 + 872);
    }
    else
    {
      v23 = &Mso::SVG::StyleMetaData<14>::initial;
      if ( *(_QWORD *)(v18 + 8) )
        v23 = (__int64 *)&Mso::SVG::StyleMetaData<14>::inherit;
    }
    if ( !*((_BYTE *)v23 + 32) )
    {
      if ( v47 )
        v24 = Mso::SVG::StyleResolveChain::Get<14>();
      else
        v24 = Mso::SVG::StyleResolveChain::GetNormal<14>(&v47, *(_QWORD *)(v18 + 8));
      v18 = v48;
      v23 = (__int64 *)v24;
    }
    v25 = *(_QWORD *)(v18 + 16);
    v26 = 0;
    if ( v25 )
    {
      v27 = (__int64 *)(v25 + 824);
    }
    else
    {
      v27 = &Mso::SVG::StyleMetaData<15>::initial;
      if ( *(_QWORD *)(v18 + 8) )
        v27 = (__int64 *)&Mso::SVG::StyleMetaData<15>::inherit;
    }
    if ( !*((_BYTE *)v27 + 32) )
    {
      if ( v47 )
      {
        v28 = Mso::SVG::StyleResolveChain::Get<15>();
        v26 = 0;
      }
      else
      {
        v28 = Mso::SVG::StyleResolveChain::GetNormal<15>(&v47, *(_QWORD *)(v18 + 8));
      }
      v18 = v48;
      v27 = (__int64 *)v28;
    }
    v45 = (char)v26;
    if ( *((_BYTE *)v8 + 400) != (_BYTE)v26
      && ((wchar_t *)v20[2] != v26 || (wchar_t *)v23[2] != v26 || (wchar_t *)v27[2] != v26) )
    {
      v45 = 1;
      v17 = (char)v26;
    }
    if ( v17 )
    {
      v29 = *(_QWORD *)(v18 + 16);
      if ( v29 )
      {
        v30 = (wchar_t **)(v29 + 344);
      }
      else if ( *(_BYTE *)(v18 + 24) == (_BYTE)v26
             || (v30 = (wchar_t **)&Mso::SVG::StyleMetaData<34>::inherit, *(wchar_t **)(v18 + 8) == v26) )
      {
        v30 = &Mso::SVG::StyleMetaData<34>::initial;
      }
      if ( *((_BYTE *)v30 + 32) == (_BYTE)v26 )
      {
        if ( v47 )
        {
          v30 = (wchar_t **)Mso::SVG::StyleResolveChain::Get<34>();
          v26 = 0;
        }
        else
        {
          v30 = (wchar_t **)Mso::SVG::StyleResolveChain::GetNormal<34>(&v47, *(_QWORD *)(v18 + 8));
        }
      }
      if ( v30[2] != v26 )
        v17 = (char)v26;
    }
    v50 = 0;
    if ( !v17 || (v31 = 1, v46 == (_BYTE)v26) )
      v31 = (char)v26;
    v32 = v55;
    Mso::SVG::StylableRenderer::ComputeFill((__int64)v7, &v58, &v47, (__int64)v61, v31, (__int64)v55);
    v33 = v58;
    if ( v58 )
    {
      v34 = (_QWORD *)GEL::IEffectFilledPath::Create(&v52, v16, v58, 0);
      v35 = (void (__fastcall ***)(_QWORD))*v34;
      v36 = v50;
      if ( (_QWORD)v50 )
      {
        if ( *((_QWORD *)&v50 + 1) )
        {
          (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)&v50 + 1) + 144LL))(*((_QWORD *)&v50 + 1), *v34);
        }
        else
        {
          v37 = (__int64 *)GEL::IEffectContainer::Create(&v54);
          v38 = *v37;
          *v37 = 0;
          if ( *((_QWORD *)&v50 + 1) )
            (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v50 + 1) + 8LL))(*((_QWORD *)&v50 + 1));
          *((_QWORD *)&v50 + 1) = v38;
          if ( v54 )
          {
            (*(void (__fastcall **)(struct GEL::IEffect *))(*(_QWORD *)v54 + 8LL))(v54);
            v38 = *((_QWORD *)&v50 + 1);
          }
          (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v38 + 144LL))(v38, v50);
          (*(void (__fastcall **)(_QWORD, void (__fastcall ***)(_QWORD)))(**((_QWORD **)&v50 + 1) + 144LL))(
            *((_QWORD *)&v50 + 1),
            v35);
          v39 = *((_QWORD *)&v50 + 1);
          if ( *((_QWORD *)&v50 + 1) )
            (***((void (__fastcall ****)(_QWORD))&v50 + 1))(*((_QWORD *)&v50 + 1));
          if ( (_QWORD)v50 )
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v50 + 8LL))(v50);
          *(_QWORD *)&v50 = v39;
          v32 = v55;
        }
      }
      else
      {
        if ( v35 )
        {
          (**v35)(*v34);
          v36 = v50;
        }
        if ( v36 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 8LL))(v36);
        *(_QWORD *)&v50 = v35;
      }
      if ( v52 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 8LL))(v52);
      v7 = (Mso::SVG::EnvironmentRenderer **)v56;
    }
    if ( v33 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 8LL))(v33);
    v40 = v17 && v44;
    Mso::SVG::ShapeRenderer::DrawStroke(
      (Mso::SVG::ShapeRenderer *)v7,
      (struct GEL::EffectAccumulator *)&v50,
      (const struct Mso::SVG::StyleResolveChain *)&v47,
      v16,
      (const struct GEL::Rect *)v61,
      v40,
      v32);
    if ( v45 )
    {
      Mso::SVG::EnvironmentRenderer::BeginRecursion(v7[3]);
      (*((void (__fastcall **)(Mso::SVG::EnvironmentRenderer **, __int128 *, const struct Mso::SVG::StyleResolveChain **, __int64, __int64 *, __int64 *, struct GEL::IColorResolver *))*v7
       + 7))(
        v7,
        &v50,
        &v47,
        v51,
        v23,
        v27,
        v32);
      --*(_DWORD *)v7[3];
    }
    EffectOrEmptyContainer = (__int64 *)GEL::EffectAccumulator::GetEffectOrEmptyContainer(&v50, &v52);
    Mso::SVG::RenderableRenderer::ApplyFilter((__int64)v7, &v53, *EffectOrEmptyContainer, &v47, v61, (__int64)v32);
    if ( v52 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 8LL))(v52);
    if ( v53 )
    {
      Mso::SVG::RenderableRenderer::ApplyStandardEffects(
        (_DWORD)v7,
        (unsigned int)&v54,
        v53,
        (unsigned int)&v47,
        (__int64)v61,
        !v17,
        0);
      v42 = v54;
      if ( v54 )
        GEL::EffectAccumulator::Add(v59, v54);
      if ( v42 )
        (*(void (__fastcall **)(struct GEL::IEffect *))(*(_QWORD *)v42 + 8LL))(v42);
    }
    Mso::SVG::RenderableRenderer::EndRendering(
      (Mso::SVG::RenderableRenderer *)v7,
      (const struct GEL::Rect *)v61,
      v60,
      1);
    v43 = v53;
    if ( v53 )
    {
      v53 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 8LL))(v43);
    }
    if ( *((_QWORD *)&v50 + 1) )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v50 + 1) + 8LL))(*((_QWORD *)&v50 + 1));
    if ( (_QWORD)v50 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v50 + 8LL))(v50);
  }
  if ( v16 )
    (*(void (__fastcall **)(struct GEL::IPath *))(*(_QWORD *)v16 + 8LL))(v16);
  std::wstring::~wstring(v63);
  std::wstring::~wstring(v65);
}

```

## disassembly

```asm
0x18010beb0  mov     [rsp-8+arg_10], rbx
0x18010beb5  push    rbp
0x18010beb6  push    rsi
0x18010beb7  push    rdi
0x18010beb8  push    r12
0x18010beba  push    r13
0x18010bebc  push    r14
0x18010bebe  push    r15
0x18010bec0  lea     rbp, [rsp-60h]
0x18010bec5  sub     rsp, 160h
0x18010becc  mov     rax, cs:__security_cookie
0x18010bed3  xor     rax, rsp
0x18010bed6  mov     [rbp+90h+var_40], rax
0x18010beda  mov     rdi, r9
0x18010bedd  mov     [rbp+90h+var_D8], r9
0x18010bee1  mov     rbx, r8
0x18010bee4  mov     [rbp+90h+var_E0], rdx
0x18010bee8  mov     rsi, rcx
0x18010beeb  mov     [rbp+90h+var_F8], rcx
0x18010beef  mov     rax, [rbp+90h+arg_20]
0x18010bef6  mov     [rbp+90h+var_100], rax
0x18010befa  xor     r15d, r15d
0x18010befd  mov     r13, [rcx+10h]
0x18010bf01  test    r13, r13
0x18010bf04  jz      loc_18010C620
0x18010bf0a  mov     edx, 0F80h
0x18010bf0f  mov     r8d, 320h
0x18010bf15  mov     rcx, [r13+0]
0x18010bf19  call    __castguard_slow_path_check_user_handled
0x18010bf1e  mov     rax, [r13+0]
0x18010bf22  mov     rcx, r13
0x18010bf25  mov     rax, [rax+68h]
0x18010bf29  call    cs:__guard_dispatch_icall_fptr
0x18010bf2f  mov     r9, rax
0x18010bf32  mov     [rsp+190h+var_148], rbx
0x18010bf37  mov     [rsp+190h+var_140], rax
0x18010bf3c  mov     rax, [rbx+10h]
0x18010bf40  mov     [rsp+190h+var_138], rax
0x18010bf45  xorps   xmm0, xmm0
0x18010bf48  movups  [rbp+90h+var_D0], xmm0
0x18010bf4c  xorps   xmm1, xmm1
0x18010bf4f  movups  [rbp+90h+var_C0], xmm1
0x18010bf53  test    rdi, rdi
0x18010bf56  jnz     short loc_18010BFBB
0x18010bf58  mov     rax, [r9+10h]
0x18010bf5c  test    rax, rax
0x18010bf5f  jz      short loc_18010BF69
0x18010bf61  add     rax, 188h
0x18010bf67  jmp     short loc_18010BF83
0x18010bf69  cmp     [r9+18h], r15b
0x18010bf6d  jz      short loc_18010BF7C
0x18010bf6f  cmp     [r9+8], r15
0x18010bf73  lea     rax, ?inherit@?$StyleMetaData@$0CB@@SVG@Mso@@2V?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@B; std::optional<std::wstring> const Mso::SVG::StyleMetaData<33>::inherit
0x18010bf7a  jnz     short loc_18010BF83
0x18010bf7c  lea     rax, ?initial@?$StyleMetaData@$0CB@@SVG@Mso@@2V?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@B; std::optional<std::wstring> const Mso::SVG::StyleMetaData<33>::initial
0x18010bf83  cmp     [rax+20h], r15b
0x18010bf87  jnz     short loc_18010BF9B
0x18010bf89  mov     rcx, rbx
0x18010bf8c  call    ??$Get@$0CB@@StyleResolveChain@SVG@Mso@@QEBAAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; Mso::SVG::StyleResolveChain::Get<33>(void)
0x18010bf91  mov     r9, [rsp+190h+var_140]
0x18010bf96  mov     rbx, [rsp+190h+var_148]
0x18010bf9b  cmp     [rax+10h], r15
0x18010bf9f  jz      short loc_18010BFBB
0x18010bfa1  mov     rcx, [rsi+18h]
0x18010bfa5  mov     rdx, rax
0x18010bfa8  mov     rcx, [rcx+40h]
0x18010bfac  call    ?QueryClipPath@Environment@SVG@Mso@@QEAAPEAVClipPathContext@23@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Mso::SVG::Environment::QueryClipPath(std::wstring const &)
0x18010bfb1  mov     r9, [rsp+190h+var_140]
0x18010bfb6  mov     rbx, [rsp+190h+var_148]
0x18010bfbb  mov     rax, [r9+10h]
0x18010bfbf  test    rax, rax
0x18010bfc2  jz      short loc_18010BFCC
0x18010bfc4  add     rax, 110h
0x18010bfca  jmp     short loc_18010BFE6
0x18010bfcc  cmp     [r9+18h], r15b
0x18010bfd0  jz      short loc_18010BFDF
0x18010bfd2  cmp     [r9+8], r15
0x18010bfd6  lea     rax, ?inherit@?$StyleMetaData@$0CE@@SVG@Mso@@2V?$optional@N@std@@B; std::optional<double> const Mso::SVG::StyleMetaData<36>::inherit
0x18010bfdd  jnz     short loc_18010BFE6
0x18010bfdf  lea     rax, ?initial@?$StyleMetaData@$0CE@@SVG@Mso@@2V?$optional@N@std@@B; std::optional<double> const Mso::SVG::StyleMetaData<36>::initial
0x18010bfe6  cmp     [rax+8], r15b
0x18010bfea  jnz     short loc_18010C00E
0x18010bfec  test    rbx, rbx
0x18010bfef  jz      short loc_18010BFFB
0x18010bff1  mov     rcx, rbx
0x18010bff4  call    ??$Get@$0CE@@StyleResolveChain@SVG@Mso@@QEBAAEBNXZ; Mso::SVG::StyleResolveChain::Get<36>(void)
0x18010bff9  jmp     short loc_18010C009
0x18010bffb  mov     rdx, [r9+8]
0x18010bfff  lea     rcx, [rsp+190h+var_148]
0x18010c004  call    ??$GetNormal@$0CE@@StyleResolveChain@SVG@Mso@@AEBAAEBNAEBVStyle@12@@Z; Mso::SVG::StyleResolveChain::GetNormal<36>(Mso::SVG::Style const &)
0x18010c009  mov     r9, [rsp+190h+var_140]
0x18010c00e  lea     r8, [rsp+190h+var_148]
0x18010c013  lea     rdx, [rbp+90h+var_78]
0x18010c017  lea     rcx, [rsp+190h+var_150]
0x18010c01c  call    ??R?$SpecialResolver@$01VPaint@SVG@Mso@@@StyleResolveChain@SVG@Mso@@QEBA?AVPaint@23@AEBV123@AEBVStyle@23@@Z; Mso::SVG::StyleResolveChain::SpecialResolver<2,Mso::SVG::Paint>::operator()(Mso::SVG::StyleResolveChain const &,Mso::SVG::Style const &)
0x18010c021  nop
0x18010c022  mov     r9, [rsp+190h+var_140]
0x18010c027  lea     r8, [rsp+190h+var_148]
0x18010c02c  lea     rdx, [rbp+90h+var_B0]
0x18010c030  lea     rcx, [rsp+190h+var_150]
0x18010c035  call    ??R?$SpecialResolver@$09VPaint@SVG@Mso@@@StyleResolveChain@SVG@Mso@@QEBA?AVPaint@23@AEBV123@AEBVStyle@23@@Z; Mso::SVG::StyleResolveChain::SpecialResolver<10,Mso::SVG::Paint>::operator()(Mso::SVG::StyleResolveChain const &,Mso::SVG::Style const &)
0x18010c03a  nop
0x18010c03b  mov     rdx, [rsp+190h+var_140]
0x18010c040  mov     rax, [rdx+10h]
0x18010c044  test    rax, rax
0x18010c047  jz      short loc_18010C051
0x18010c049  add     rax, 3E0h
0x18010c04f  jmp     short loc_18010C067
0x18010c051  lea     rax, ?initial@?$StyleMetaData@$0L@@SVG@Mso@@2V?$optional@W4FillMode@Path@Graphics@Mso@@@std@@B; std::optional<Mso::Graphics::Path::FillMode> const Mso::SVG::StyleMetaData<11>::initial
0x18010c058  lea     rcx, ?inherit@?$StyleMetaData@$0L@@SVG@Mso@@2V?$optional@W4FillMode@Path@Graphics@Mso@@@std@@B; std::optional<Mso::Graphics::Path::FillMode> const Mso::SVG::StyleMetaData<11>::inherit
0x18010c05f  cmp     [rdx+8], r15
0x18010c063  cmovnz  rax, rcx
0x18010c067  cmp     [rax+4], r15b
0x18010c06b  jnz     short loc_18010C08C
0x18010c06d  mov     rcx, [rsp+190h+var_148]
0x18010c072  test    rcx, rcx
0x18010c075  jz      short loc_18010C07E
0x18010c077  call    ??$Get@$0L@@StyleResolveChain@SVG@Mso@@QEBAAEBW4FillMode@Path@Graphics@2@XZ; Mso::SVG::StyleResolveChain::Get<11>(void)
0x18010c07c  jmp     short loc_18010C08C
0x18010c07e  mov     rdx, [rdx+8]
0x18010c082  lea     rcx, [rsp+190h+var_148]
0x18010c087  call    ??$GetNormal@$0L@@StyleResolveChain@SVG@Mso@@AEBAAEBW4FillMode@Path@Graphics@2@AEBVStyle@12@@Z; Mso::SVG::StyleResolveChain::GetNormal<11>(Mso::SVG::Style const &)
0x18010c08c  mov     r9d, [rax]
0x18010c08f  lea     r8, [rsp+190h+var_148]
0x18010c094  lea     rdx, [rbp+90h+var_F0]
0x18010c098  mov     rcx, rsi
0x18010c09b  call    ?GetEffectivePath@ShapeRenderer@SVG@Mso@@AEAA?AV?$TCntPtr@$$CBUIPath@GEL@@@3@AEBVStyleResolveChain@23@W4FillMode@Path@Graphics@3@@Z; Mso::SVG::ShapeRenderer::GetEffectivePath(Mso::SVG::StyleResolveChain const &,Mso::Graphics::Path::FillMode)
0x18010c0a0  nop
0x18010c0a1  mov     rdi, [rbp+90h+var_F0]
0x18010c0a5  test    rdi, rdi
0x18010c0a8  jz      loc_18010C5D1
0x18010c0ae  mov     rax, [rdi]
0x18010c0b1  lea     rdx, [rbp+90h+var_D0]
0x18010c0b5  mov     rcx, rdi
0x18010c0b8  mov     rax, [rax+68h]
0x18010c0bc  call    cs:__guard_dispatch_icall_fptr
0x18010c0c2  mov     ecx, [rbp+90h+var_78]
0x18010c0c5  lea     eax, [rcx-3]
0x18010c0c8  cmp     eax, 1
0x18010c0cb  setbe   r8b
0x18010c0cf  mov     [rsp+190h+var_150], r8b
0x18010c0d4  mov     edx, [rbp+90h+var_B0]
0x18010c0d7  lea     eax, [rdx-3]
0x18010c0da  cmp     eax, 1
0x18010c0dd  setbe   al
0x18010c0e0  mov     [rsp+190h+var_14E], al
0x18010c0e4  cmp     ecx, 2
0x18010c0e7  jnz     short loc_18010C0ED
0x18010c0e9  test    al, al
0x18010c0eb  jnz     short loc_18010C0F7
0x18010c0ed  cmp     edx, 2
0x18010c0f0  jnz     short loc_18010C0FC
0x18010c0f2  test    r8b, r8b
0x18010c0f5  jz      short loc_18010C0FC
0x18010c0f7  mov     r14b, 1
0x18010c0fa  jmp     short loc_18010C0FF
0x18010c0fc  mov     r14b, r15b
0x18010c0ff  mov     rdx, [rsp+190h+var_140]
0x18010c104  mov     rax, [rdx+10h]
0x18010c108  test    rax, rax
0x18010c10b  jz      short loc_18010C116
0x18010c10d  lea     rbx, [rax+398h]
0x18010c114  jmp     short loc_18010C12C
0x18010c116  lea     rbx, ?initial@?$StyleMetaData@$0N@@SVG@Mso@@2V?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@B; std::optional<std::wstring> const Mso::SVG::StyleMetaData<13>::initial
0x18010c11d  lea     rax, ?inherit@?$StyleMetaData@$0N@@SVG@Mso@@2V?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@B; std::optional<std::wstring> const Mso::SVG::StyleMetaData<13>::inherit
0x18010c124  cmp     [rdx+8], r15
0x18010c128  cmovnz  rbx, rax
0x18010c12c  mov     [rsp+190h+var_120], rbx
0x18010c131  cmp     [rbx+20h], r15b
0x18010c135  jnz     short loc_18010C163
0x18010c137  mov     rcx, [rsp+190h+var_148]
0x18010c13c  test    rcx, rcx
0x18010c13f  jz      short loc_18010C148
0x18010c141  call    ??$Get@$0N@@StyleResolveChain@SVG@Mso@@QEBAAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; Mso::SVG::StyleResolveChain::Get<13>(void)
0x18010c146  jmp     short loc_18010C156
0x18010c148  mov     rdx, [rdx+8]
0x18010c14c  lea     rcx, [rsp+190h+var_148]
0x18010c151  call    ??$GetNormal@$0N@@StyleResolveChain@SVG@Mso@@AEBAAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBVStyle@12@@Z; Mso::SVG::StyleResolveChain::GetNormal<13>(Mso::SVG::Style const &)
0x18010c156  mov     rdx, [rsp+190h+var_140]
0x18010c15b  mov     [rsp+190h+var_120], rax
0x18010c160  mov     rbx, rax
0x18010c163  mov     rax, [rdx+10h]
0x18010c167  test    rax, rax
0x18010c16a  jz      short loc_18010C175
0x18010c16c  lea     r12, [rax+368h]
0x18010c173  jmp     short loc_18010C18B
0x18010c175  lea     r12, ?initial@?$StyleMetaData@$0O@@SVG@Mso@@2V?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@B; std::optional<std::wstring> const Mso::SVG::StyleMetaData<14>::initial
0x18010c17c  lea     rax, ?inherit@?$StyleMetaData@$0O@@SVG@Mso@@2V?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@B; std::optional<std::wstring> const Mso::SVG::StyleMetaData<14>::inherit
0x18010c183  cmp     [rdx+8], r15
0x18010c187  cmovnz  r12, rax
0x18010c18b  cmp     [r12+20h], r15b
0x18010c190  jnz     short loc_18010C1B9
0x18010c192  mov     rcx, [rsp+190h+var_148]
0x18010c197  test    rcx, rcx
0x18010c19a  jz      short loc_18010C1A3
0x18010c19c  call    ??$Get@$0O@@StyleResolveChain@SVG@Mso@@QEBAAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; Mso::SVG::StyleResolveChain::Get<14>(void)
0x18010c1a1  jmp     short loc_18010C1B1
0x18010c1a3  mov     rdx, [rdx+8]
0x18010c1a7  lea     rcx, [rsp+190h+var_148]
0x18010c1ac  call    ??$GetNormal@$0O@@StyleResolveChain@SVG@Mso@@AEBAAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBVStyle@12@@Z; Mso::SVG::StyleResolveChain::GetNormal<14>(Mso::SVG::Style const &)
0x18010c1b1  mov     rdx, [rsp+190h+var_140]
0x18010c1b6  mov     r12, rax
0x18010c1b9  mov     r15, [rdx+10h]
0x18010c1bd  xor     r11d, r11d
0x18010c1c0  test    r15, r15
0x18010c1c3  jz      short loc_18010C1CE
0x18010c1c5  add     r15, 338h
0x18010c1cc  jmp     short loc_18010C1E4
0x18010c1ce  lea     r15, ?initial@?$StyleMetaData@$0P@@SVG@Mso@@2V?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@B; std::optional<std::wstring> const Mso::SVG::StyleMetaData<15>::initial
0x18010c1d5  lea     rax, ?inherit@?$StyleMetaData@$0P@@SVG@Mso@@2V?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@B; std::optional<std::wstring> const Mso::SVG::StyleMetaData<15>::inherit
0x18010c1dc  cmp     [rdx+8], r11
0x18010c1e0  cmovnz  r15, rax
0x18010c1e4  cmp     [r15+20h], r11b
0x18010c1e8  jnz     short loc_18010C214
0x18010c1ea  mov     rcx, [rsp+190h+var_148]
0x18010c1ef  test    rcx, rcx
0x18010c1f2  jz      short loc_18010C1FE
0x18010c1f4  call    ??$Get@$0P@@StyleResolveChain@SVG@Mso@@QEBAAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; Mso::SVG::StyleResolveChain::Get<15>(void)
0x18010c1f9  xor     r11d, r11d
0x18010c1fc  jmp     short loc_18010C20C
0x18010c1fe  mov     rdx, [rdx+8]
0x18010c202  lea     rcx, [rsp+190h+var_148]
0x18010c207  call    ??$GetNormal@$0P@@StyleResolveChain@SVG@Mso@@AEBAAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBVStyle@12@@Z; Mso::SVG::StyleResolveChain::GetNormal<15>(Mso::SVG::Style const &)
0x18010c20c  mov     rdx, [rsp+190h+var_140]
0x18010c211  mov     r15, rax
0x18010c214  mov     [rsp+190h+var_14F], r11b
0x18010c219  cmp     [r13+190h], r11b
0x18010c220  jz      short loc_18010C23D
0x18010c222  cmp     [rbx+10h], r11
0x18010c226  jnz     short loc_18010C235
0x18010c228  cmp     [r12+10h], r11
0x18010c22d  jnz     short loc_18010C235
0x18010c22f  cmp     [r15+10h], r11
0x18010c233  jz      short loc_18010C23D
0x18010c235  mov     [rsp+190h+var_14F], 1
0x18010c23a  mov     r14b, r11b
0x18010c23d  test    r14b, r14b
0x18010c240  jz      short loc_18010C2A1
0x18010c242  mov     rax, [rdx+10h]
0x18010c246  test    rax, rax
0x18010c249  jz      short loc_18010C253
0x18010c24b  add     rax, 158h
0x18010c251  jmp     short loc_18010C26D
0x18010c253  cmp     [rdx+18h], r11b
0x18010c257  jz      short loc_18010C266
0x18010c259  cmp     [rdx+8], r11
0x18010c25d  lea     rax, ?inherit@?$StyleMetaData@$0CC@@SVG@Mso@@2V?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@B; std::optional<std::wstring> const Mso::SVG::StyleMetaData<34>::inherit
0x18010c264  jnz     short loc_18010C26D
0x18010c266  lea     rax, ?initial@?$StyleMetaData@$0CC@@SVG@Mso@@2V?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@B; std::optional<std::wstring> const Mso::SVG::StyleMetaData<34>::initial
0x18010c26d  cmp     [rax+20h], r11b
0x18010c271  jnz     short loc_18010C295
0x18010c273  mov     rcx, [rsp+190h+var_148]
0x18010c278  test    rcx, rcx
0x18010c27b  jz      short loc_18010C287
0x18010c27d  call    ??$Get@$0CC@@StyleResolveChain@SVG@Mso@@QEBAAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; Mso::SVG::StyleResolveChain::Get<34>(void)
0x18010c282  xor     r11d, r11d
0x18010c285  jmp     short loc_18010C295
0x18010c287  mov     rdx, [rdx+8]
0x18010c28b  lea     rcx, [rsp+190h+var_148]
0x18010c290  call    ??$GetNormal@$0CC@@StyleResolveChain@SVG@Mso@@AEBAAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBVStyle@12@@Z; Mso::SVG::StyleResolveChain::GetNormal<34>(Mso::SVG::Style const &)
0x18010c295  movzx   r14d, r14b
0x18010c299  cmp     [rax+10h], r11
0x18010c29d  cmovnz  r14d, r11d
0x18010c2a1  xorps   xmm0, xmm0
0x18010c2a4  movdqu  [rsp+190h+var_130], xmm0
0x18010c2aa  test    r14b, r14b
0x18010c2ad  jz      short loc_18010C2B8
0x18010c2af  cmp     [rsp+190h+var_14E], r11b
0x18010c2b4  mov     al, 1
0x18010c2b6  jnz     short loc_18010C2BB
0x18010c2b8  mov     al, r11b
0x18010c2bb  mov     r13, [rbp+90h+var_100]
0x18010c2bf  mov     qword ptr [rsp+190h+var_168], r13
0x18010c2c4  mov     byte ptr [rsp+190h+var_170], al
0x18010c2c8  lea     r9, [rbp+90h+var_D0]
0x18010c2cc  lea     r8, [rsp+190h+var_148]
0x18010c2d1  lea     rdx, [rbp+90h+var_E8]
0x18010c2d5  mov     rcx, rsi
0x18010c2d8  call    ?ComputeFill@StylableRenderer@SVG@Mso@@QEBA?AV?$TCntPtr@UIBrush@GEL@@@3@AEBVStyleResolveChain@23@PEBURect@GEL@@_NPEBUIColorResolver@7@@Z; Mso::SVG::StylableRenderer::ComputeFill(Mso::SVG::StyleResolveChain const &,GEL::Rect const *,bool,GEL::IColorResolver const *)
0x18010c2dd  nop
0x18010c2de  mov     rbx, [rbp+90h+var_E8]
0x18010c2e2  test    rbx, rbx
0x18010c2e5  jz      loc_18010C436
0x18010c2eb  xor     r9d, r9d
0x18010c2ee  mov     r8, rbx
0x18010c2f1  mov     rdx, rdi
0x18010c2f4  lea     rcx, [rsp+190h+var_118]
0x18010c2f9  call    cs:__imp_?Create@IEffectFilledPath@GEL@@SA?AV?$TCntPtr@UIEffectFilledPath@GEL@@@Ofc@@AEBUIPath@2@AEBUIBrush@2@PEBU?$TAffine3x3@N@Math@@@Z; GEL::IEffectFilledPath::Create(GEL::IPath const &,GEL::IBrush const &,Math::TAffine3x3<double> const *)
0x18010c2ff  nop
0x18010c300  mov     rsi, [rax]
0x18010c303  mov     rcx, qword ptr [rsp+190h+var_130]
0x18010c308  test    rcx, rcx
0x18010c30b  jnz     short loc_18010C342
0x18010c30d  test    rsi, rsi
0x18010c310  jz      short loc_18010C326
0x18010c312  mov     rax, [rsi]
0x18010c315  mov     rcx, rsi
0x18010c318  mov     rax, [rax]
0x18010c31b  call    cs:__guard_dispatch_icall_fptr
0x18010c321  mov     rcx, qword ptr [rsp+190h+var_130]
  ... truncated ...
```
