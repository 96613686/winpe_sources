# Mso::SVG::ShapeRenderer::Render(GEL::EffectAccumulator &,Mso::SVG::StyleResolveChain const &,GEL::Rect *,GEL::IColorResolver const *)

- ea: `0x18010bee0`
- end: `0x18010c65e`
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
- `0x1800415c4`
- `0x180041df8`
- `0x180042580`
- `0x180043290`
- `0x180043c28`
- `0x180044130`
- `0x1800448e0`
- `0x18004e660`
- `0x18004e760`
- `0x1800f5db0`
- `0x18010b898`
- `0x18010b9e8`
- `0x18010bee0`
- `0x18010d218`
- `0x18010d274`
- `0x18010d2d0`
- `0x18010d32c`
- `0x18010d624`
- `0x18010d67c`
- `0x18010d6d4`
- `0x18010d72c`
- `0x18013d700`
- `0x18013e0c0`
- `0x18013f810`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18010c657`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18010c657`
- `gfx!?Create@IEffectContainer@GEL@@SA?AV?$TCntPtr@UIEffectContainer@GEL@@@Ofc@@XZ` at `0x18010c384`
- `gfx!?Create@IEffectContainer@GEL@@SA?AV?$TCntPtr@UIEffectContainer@GEL@@@Ofc@@XZ` at `0x18010c384`
- `gfx!?Create@IEffectFilledPath@GEL@@SA?AV?$TCntPtr@UIEffectFilledPath@GEL@@@Ofc@@AEBUIPath@2@AEBUIBrush@2@PEBU?$TAffine3x3@N@Math@@@Z` at `0x18010c329`
- `gfx!?Create@IEffectFilledPath@GEL@@SA?AV?$TCntPtr@UIEffectFilledPath@GEL@@@Ofc@@AEBUIPath@2@AEBUIBrush@2@PEBU?$TAffine3x3@N@Math@@@Z` at `0x18010c329`

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
  __int64 *v11; // rax
  __int64 v12; // rax
  __int64 *v13; // rax
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
  __int64 v26; // r11
  __int64 *v27; // r15
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 *v30; // rax
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
  _OWORD v61[2]; // [rsp+C0h] [rbp-40h] BYREF
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
    JUMPOUT(0x18010C65DLL);
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
      v11 = (__int64 *)(v10 + 392);
    }
    else if ( !*(_BYTE *)(v9 + 24) || (v11 = Mso::SVG::StyleMetaData<33>::inherit, !*(_QWORD *)(v9 + 8)) )
    {
      v11 = (__int64 *)&Mso::SVG::StyleMetaData<33>::initial;
    }
    if ( !*((_BYTE *)v11 + 32) )
    {
      v11 = (__int64 *)Mso::SVG::StyleResolveChain::Get<33>(a3);
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
    v13 = (__int64 *)(v12 + 272);
  }
  else if ( !*(_BYTE *)(v9 + 24) || (v13 = Mso::SVG::StyleMetaData<36>::inherit, !*(_QWORD *)(v9 + 8)) )
  {
    v13 = (__int64 *)&Mso::SVG::StyleMetaData<36>::initial;
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
      v15 = &Mso::SVG::StyleMetaData<11>::inherit;
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
    (*(void (__fastcall **)(struct GEL::IPath *, _OWORD *))(*(_QWORD *)v57 + 104LL))(v57, v61);
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
        v20 = Mso::SVG::StyleMetaData<13>::inherit;
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
        v23 = Mso::SVG::StyleMetaData<14>::inherit;
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
        v27 = Mso::SVG::StyleMetaData<15>::inherit;
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
    v45 = v26;
    if ( *((_BYTE *)v8 + 400) != (_BYTE)v26 && (v20[2] != v26 || v23[2] != v26 || v27[2] != v26) )
    {
      v45 = 1;
      v17 = v26;
    }
    if ( v17 )
    {
      v29 = *(_QWORD *)(v18 + 16);
      if ( v29 )
      {
        v30 = (__int64 *)(v29 + 344);
      }
      else if ( *(_BYTE *)(v18 + 24) == (_BYTE)v26
             || (v30 = Mso::SVG::StyleMetaData<34>::inherit, *(_QWORD *)(v18 + 8) == v26) )
      {
        v30 = (__int64 *)&Mso::SVG::StyleMetaData<34>::initial;
      }
      if ( *((_BYTE *)v30 + 32) == (_BYTE)v26 )
      {
        if ( v47 )
        {
          v30 = (__int64 *)Mso::SVG::StyleResolveChain::Get<34>();
          v26 = 0;
        }
        else
        {
          v30 = (__int64 *)Mso::SVG::StyleResolveChain::GetNormal<34>(&v47, *(_QWORD *)(v18 + 8));
        }
      }
      if ( v30[2] != v26 )
        v17 = v26;
    }
    v50 = 0;
    if ( !v17 || (v31 = 1, v46 == (_BYTE)v26) )
      v31 = v26;
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
    Mso::SVG::RenderableRenderer::ApplyFilter(
      (__int64)v7,
      &v53,
      *EffectOrEmptyContainer,
      &v47,
      (double *)v61,
      (__int64)v32);
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
0x18010bee0  mov     [rsp-8+arg_10], rbx
0x18010bee5  push    rbp
0x18010bee6  push    rsi
0x18010bee7  push    rdi
0x18010bee8  push    r12
0x18010beea  push    r13
0x18010beec  push    r14
0x18010beee  push    r15
0x18010bef0  lea     rbp, [rsp-60h]
0x18010bef5  sub     rsp, 160h
0x18010befc  mov     rax, cs:__security_cookie
0x18010bf03  xor     rax, rsp
0x18010bf06  mov     [rbp+90h+var_40], rax
0x18010bf0a  mov     rdi, r9
0x18010bf0d  mov     [rbp+90h+var_D8], r9
0x18010bf11  mov     rbx, r8
0x18010bf14  mov     [rbp+90h+var_E0], rdx
0x18010bf18  mov     rsi, rcx
0x18010bf1b  mov     [rbp+90h+var_F8], rcx
0x18010bf1f  mov     rax, [rbp+90h+arg_20]
0x18010bf26  mov     [rbp+90h+var_100], rax
0x18010bf2a  xor     r15d, r15d
0x18010bf2d  mov     r13, [rcx+10h]
0x18010bf31  test    r13, r13
0x18010bf34  jz      loc_18010C650
0x18010bf3a  mov     edx, 0F80h
0x18010bf3f  mov     r8d, 320h
0x18010bf45  mov     rcx, [r13+0]
0x18010bf49  call    __castguard_slow_path_check_user_handled
0x18010bf4e  mov     rax, [r13+0]
0x18010bf52  mov     rcx, r13
0x18010bf55  mov     rax, [rax+68h]
0x18010bf59  call    cs:__guard_dispatch_icall_fptr
0x18010bf5f  mov     r9, rax
0x18010bf62  mov     [rsp+190h+var_148], rbx
0x18010bf67  mov     [rsp+190h+var_140], rax
0x18010bf6c  mov     rax, [rbx+10h]
0x18010bf70  mov     [rsp+190h+var_138], rax
0x18010bf75  xorps   xmm0, xmm0
0x18010bf78  movups  [rbp+90h+var_D0], xmm0
0x18010bf7c  xorps   xmm1, xmm1
0x18010bf7f  movups  [rbp+90h+var_C0], xmm1
0x18010bf83  test    rdi, rdi
0x18010bf86  jnz     short loc_18010BFEB
0x18010bf88  mov     rax, [r9+10h]
0x18010bf8c  test    rax, rax
0x18010bf8f  jz      short loc_18010BF99
0x18010bf91  add     rax, 188h
0x18010bf97  jmp     short loc_18010BFB3
0x18010bf99  cmp     [r9+18h], r15b
0x18010bf9d  jz      short loc_18010BFAC
0x18010bf9f  cmp     [r9+8], r15
0x18010bfa3  lea     rax, ?inherit@?$StyleMetaData@$0CB@@SVG@Mso@@2V?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@B; std::optional<std::wstring> const Mso::SVG::StyleMetaData<33>::inherit
0x18010bfaa  jnz     short loc_18010BFB3
0x18010bfac  lea     rax, ?initial@?$StyleMetaData@$0CB@@SVG@Mso@@2V?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@B; std::optional<std::wstring> const Mso::SVG::StyleMetaData<33>::initial
0x18010bfb3  cmp     [rax+20h], r15b
0x18010bfb7  jnz     short loc_18010BFCB
0x18010bfb9  mov     rcx, rbx
0x18010bfbc  call    ??$Get@$0CB@@StyleResolveChain@SVG@Mso@@QEBAAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; Mso::SVG::StyleResolveChain::Get<33>(void)
0x18010bfc1  mov     r9, [rsp+190h+var_140]
0x18010bfc6  mov     rbx, [rsp+190h+var_148]
0x18010bfcb  cmp     [rax+10h], r15
0x18010bfcf  jz      short loc_18010BFEB
0x18010bfd1  mov     rcx, [rsi+18h]
0x18010bfd5  mov     rdx, rax
0x18010bfd8  mov     rcx, [rcx+40h]
0x18010bfdc  call    ?QueryClipPath@Environment@SVG@Mso@@QEAAPEAVClipPathContext@23@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Mso::SVG::Environment::QueryClipPath(std::wstring const &)
0x18010bfe1  mov     r9, [rsp+190h+var_140]
0x18010bfe6  mov     rbx, [rsp+190h+var_148]
0x18010bfeb  mov     rax, [r9+10h]
0x18010bfef  test    rax, rax
0x18010bff2  jz      short loc_18010BFFC
0x18010bff4  add     rax, 110h
0x18010bffa  jmp     short loc_18010C016
0x18010bffc  cmp     [r9+18h], r15b
0x18010c000  jz      short loc_18010C00F
0x18010c002  cmp     [r9+8], r15
0x18010c006  lea     rax, ?inherit@?$StyleMetaData@$0CE@@SVG@Mso@@2V?$optional@N@std@@B; std::optional<double> const Mso::SVG::StyleMetaData<36>::inherit
0x18010c00d  jnz     short loc_18010C016
0x18010c00f  lea     rax, ?initial@?$StyleMetaData@$0CE@@SVG@Mso@@2V?$optional@N@std@@B; std::optional<double> const Mso::SVG::StyleMetaData<36>::initial
0x18010c016  cmp     [rax+8], r15b
0x18010c01a  jnz     short loc_18010C03E
0x18010c01c  test    rbx, rbx
0x18010c01f  jz      short loc_18010C02B
0x18010c021  mov     rcx, rbx
0x18010c024  call    ??$Get@$0CE@@StyleResolveChain@SVG@Mso@@QEBAAEBNXZ; Mso::SVG::StyleResolveChain::Get<36>(void)
0x18010c029  jmp     short loc_18010C039
0x18010c02b  mov     rdx, [r9+8]
0x18010c02f  lea     rcx, [rsp+190h+var_148]
0x18010c034  call    ??$GetNormal@$0CE@@StyleResolveChain@SVG@Mso@@AEBAAEBNAEBVStyle@12@@Z; Mso::SVG::StyleResolveChain::GetNormal<36>(Mso::SVG::Style const &)
0x18010c039  mov     r9, [rsp+190h+var_140]
0x18010c03e  lea     r8, [rsp+190h+var_148]
0x18010c043  lea     rdx, [rbp+90h+var_78]
0x18010c047  lea     rcx, [rsp+190h+var_150]
0x18010c04c  call    ??R?$SpecialResolver@$01VPaint@SVG@Mso@@@StyleResolveChain@SVG@Mso@@QEBA?AVPaint@23@AEBV123@AEBVStyle@23@@Z; Mso::SVG::StyleResolveChain::SpecialResolver<2,Mso::SVG::Paint>::operator()(Mso::SVG::StyleResolveChain const &,Mso::SVG::Style const &)
0x18010c051  nop
0x18010c052  mov     r9, [rsp+190h+var_140]
0x18010c057  lea     r8, [rsp+190h+var_148]
0x18010c05c  lea     rdx, [rbp+90h+var_B0]
0x18010c060  lea     rcx, [rsp+190h+var_150]
0x18010c065  call    ??R?$SpecialResolver@$09VPaint@SVG@Mso@@@StyleResolveChain@SVG@Mso@@QEBA?AVPaint@23@AEBV123@AEBVStyle@23@@Z; Mso::SVG::StyleResolveChain::SpecialResolver<10,Mso::SVG::Paint>::operator()(Mso::SVG::StyleResolveChain const &,Mso::SVG::Style const &)
0x18010c06a  nop
0x18010c06b  mov     rdx, [rsp+190h+var_140]
0x18010c070  mov     rax, [rdx+10h]
0x18010c074  test    rax, rax
0x18010c077  jz      short loc_18010C081
0x18010c079  add     rax, 3E0h
0x18010c07f  jmp     short loc_18010C097
0x18010c081  lea     rax, ?initial@?$StyleMetaData@$0L@@SVG@Mso@@2V?$optional@W4FillMode@Path@Graphics@Mso@@@std@@B; std::optional<Mso::Graphics::Path::FillMode> const Mso::SVG::StyleMetaData<11>::initial
0x18010c088  lea     rcx, ?inherit@?$StyleMetaData@$0L@@SVG@Mso@@2V?$optional@W4FillMode@Path@Graphics@Mso@@@std@@B; std::optional<Mso::Graphics::Path::FillMode> const Mso::SVG::StyleMetaData<11>::inherit
0x18010c08f  cmp     [rdx+8], r15
0x18010c093  cmovnz  rax, rcx
0x18010c097  cmp     [rax+4], r15b
0x18010c09b  jnz     short loc_18010C0BC
0x18010c09d  mov     rcx, [rsp+190h+var_148]
0x18010c0a2  test    rcx, rcx
0x18010c0a5  jz      short loc_18010C0AE
0x18010c0a7  call    ??$Get@$0L@@StyleResolveChain@SVG@Mso@@QEBAAEBW4FillMode@Path@Graphics@2@XZ; Mso::SVG::StyleResolveChain::Get<11>(void)
0x18010c0ac  jmp     short loc_18010C0BC
0x18010c0ae  mov     rdx, [rdx+8]
0x18010c0b2  lea     rcx, [rsp+190h+var_148]
0x18010c0b7  call    ??$GetNormal@$0L@@StyleResolveChain@SVG@Mso@@AEBAAEBW4FillMode@Path@Graphics@2@AEBVStyle@12@@Z; Mso::SVG::StyleResolveChain::GetNormal<11>(Mso::SVG::Style const &)
0x18010c0bc  mov     r9d, [rax]
0x18010c0bf  lea     r8, [rsp+190h+var_148]
0x18010c0c4  lea     rdx, [rbp+90h+var_F0]
0x18010c0c8  mov     rcx, rsi
0x18010c0cb  call    ?GetEffectivePath@ShapeRenderer@SVG@Mso@@AEAA?AV?$TCntPtr@$$CBUIPath@GEL@@@3@AEBVStyleResolveChain@23@W4FillMode@Path@Graphics@3@@Z; Mso::SVG::ShapeRenderer::GetEffectivePath(Mso::SVG::StyleResolveChain const &,Mso::Graphics::Path::FillMode)
0x18010c0d0  nop
0x18010c0d1  mov     rdi, [rbp+90h+var_F0]
0x18010c0d5  test    rdi, rdi
0x18010c0d8  jz      loc_18010C601
0x18010c0de  mov     rax, [rdi]
0x18010c0e1  lea     rdx, [rbp+90h+var_D0]
0x18010c0e5  mov     rcx, rdi
0x18010c0e8  mov     rax, [rax+68h]
0x18010c0ec  call    cs:__guard_dispatch_icall_fptr
0x18010c0f2  mov     ecx, [rbp+90h+var_78]
0x18010c0f5  lea     eax, [rcx-3]
0x18010c0f8  cmp     eax, 1
0x18010c0fb  setbe   r8b
0x18010c0ff  mov     [rsp+190h+var_150], r8b
0x18010c104  mov     edx, [rbp+90h+var_B0]
0x18010c107  lea     eax, [rdx-3]
0x18010c10a  cmp     eax, 1
0x18010c10d  setbe   al
0x18010c110  mov     [rsp+190h+var_14E], al
0x18010c114  cmp     ecx, 2
0x18010c117  jnz     short loc_18010C11D
0x18010c119  test    al, al
0x18010c11b  jnz     short loc_18010C127
0x18010c11d  cmp     edx, 2
0x18010c120  jnz     short loc_18010C12C
0x18010c122  test    r8b, r8b
0x18010c125  jz      short loc_18010C12C
0x18010c127  mov     r14b, 1
0x18010c12a  jmp     short loc_18010C12F
0x18010c12c  mov     r14b, r15b
0x18010c12f  mov     rdx, [rsp+190h+var_140]
0x18010c134  mov     rax, [rdx+10h]
0x18010c138  test    rax, rax
0x18010c13b  jz      short loc_18010C146
0x18010c13d  lea     rbx, [rax+398h]
0x18010c144  jmp     short loc_18010C15C
0x18010c146  lea     rbx, ?initial@?$StyleMetaData@$0N@@SVG@Mso@@2V?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@B; std::optional<std::wstring> const Mso::SVG::StyleMetaData<13>::initial
0x18010c14d  lea     rax, ?inherit@?$StyleMetaData@$0N@@SVG@Mso@@2V?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@B; std::optional<std::wstring> const Mso::SVG::StyleMetaData<13>::inherit
0x18010c154  cmp     [rdx+8], r15
0x18010c158  cmovnz  rbx, rax
0x18010c15c  mov     [rsp+190h+var_120], rbx
0x18010c161  cmp     [rbx+20h], r15b
0x18010c165  jnz     short loc_18010C193
0x18010c167  mov     rcx, [rsp+190h+var_148]
0x18010c16c  test    rcx, rcx
0x18010c16f  jz      short loc_18010C178
0x18010c171  call    ??$Get@$0N@@StyleResolveChain@SVG@Mso@@QEBAAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; Mso::SVG::StyleResolveChain::Get<13>(void)
0x18010c176  jmp     short loc_18010C186
0x18010c178  mov     rdx, [rdx+8]
0x18010c17c  lea     rcx, [rsp+190h+var_148]
0x18010c181  call    ??$GetNormal@$0N@@StyleResolveChain@SVG@Mso@@AEBAAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBVStyle@12@@Z; Mso::SVG::StyleResolveChain::GetNormal<13>(Mso::SVG::Style const &)
0x18010c186  mov     rdx, [rsp+190h+var_140]
0x18010c18b  mov     [rsp+190h+var_120], rax
0x18010c190  mov     rbx, rax
0x18010c193  mov     rax, [rdx+10h]
0x18010c197  test    rax, rax
0x18010c19a  jz      short loc_18010C1A5
0x18010c19c  lea     r12, [rax+368h]
0x18010c1a3  jmp     short loc_18010C1BB
0x18010c1a5  lea     r12, ?initial@?$StyleMetaData@$0O@@SVG@Mso@@2V?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@B; std::optional<std::wstring> const Mso::SVG::StyleMetaData<14>::initial
0x18010c1ac  lea     rax, ?inherit@?$StyleMetaData@$0O@@SVG@Mso@@2V?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@B; std::optional<std::wstring> const Mso::SVG::StyleMetaData<14>::inherit
0x18010c1b3  cmp     [rdx+8], r15
0x18010c1b7  cmovnz  r12, rax
0x18010c1bb  cmp     [r12+20h], r15b
0x18010c1c0  jnz     short loc_18010C1E9
0x18010c1c2  mov     rcx, [rsp+190h+var_148]
0x18010c1c7  test    rcx, rcx
0x18010c1ca  jz      short loc_18010C1D3
0x18010c1cc  call    ??$Get@$0O@@StyleResolveChain@SVG@Mso@@QEBAAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; Mso::SVG::StyleResolveChain::Get<14>(void)
0x18010c1d1  jmp     short loc_18010C1E1
0x18010c1d3  mov     rdx, [rdx+8]
0x18010c1d7  lea     rcx, [rsp+190h+var_148]
0x18010c1dc  call    ??$GetNormal@$0O@@StyleResolveChain@SVG@Mso@@AEBAAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBVStyle@12@@Z; Mso::SVG::StyleResolveChain::GetNormal<14>(Mso::SVG::Style const &)
0x18010c1e1  mov     rdx, [rsp+190h+var_140]
0x18010c1e6  mov     r12, rax
0x18010c1e9  mov     r15, [rdx+10h]
0x18010c1ed  xor     r11d, r11d
0x18010c1f0  test    r15, r15
0x18010c1f3  jz      short loc_18010C1FE
0x18010c1f5  add     r15, 338h
0x18010c1fc  jmp     short loc_18010C214
0x18010c1fe  lea     r15, ?initial@?$StyleMetaData@$0P@@SVG@Mso@@2V?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@B; std::optional<std::wstring> const Mso::SVG::StyleMetaData<15>::initial
0x18010c205  lea     rax, ?inherit@?$StyleMetaData@$0P@@SVG@Mso@@2V?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@B; std::optional<std::wstring> const Mso::SVG::StyleMetaData<15>::inherit
0x18010c20c  cmp     [rdx+8], r11
0x18010c210  cmovnz  r15, rax
0x18010c214  cmp     [r15+20h], r11b
0x18010c218  jnz     short loc_18010C244
0x18010c21a  mov     rcx, [rsp+190h+var_148]
0x18010c21f  test    rcx, rcx
0x18010c222  jz      short loc_18010C22E
0x18010c224  call    ??$Get@$0P@@StyleResolveChain@SVG@Mso@@QEBAAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; Mso::SVG::StyleResolveChain::Get<15>(void)
0x18010c229  xor     r11d, r11d
0x18010c22c  jmp     short loc_18010C23C
0x18010c22e  mov     rdx, [rdx+8]
0x18010c232  lea     rcx, [rsp+190h+var_148]
0x18010c237  call    ??$GetNormal@$0P@@StyleResolveChain@SVG@Mso@@AEBAAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBVStyle@12@@Z; Mso::SVG::StyleResolveChain::GetNormal<15>(Mso::SVG::Style const &)
0x18010c23c  mov     rdx, [rsp+190h+var_140]
0x18010c241  mov     r15, rax
0x18010c244  mov     [rsp+190h+var_14F], r11b
0x18010c249  cmp     [r13+190h], r11b
0x18010c250  jz      short loc_18010C26D
0x18010c252  cmp     [rbx+10h], r11
0x18010c256  jnz     short loc_18010C265
0x18010c258  cmp     [r12+10h], r11
0x18010c25d  jnz     short loc_18010C265
0x18010c25f  cmp     [r15+10h], r11
0x18010c263  jz      short loc_18010C26D
0x18010c265  mov     [rsp+190h+var_14F], 1
0x18010c26a  mov     r14b, r11b
0x18010c26d  test    r14b, r14b
0x18010c270  jz      short loc_18010C2D1
0x18010c272  mov     rax, [rdx+10h]
0x18010c276  test    rax, rax
0x18010c279  jz      short loc_18010C283
0x18010c27b  add     rax, 158h
0x18010c281  jmp     short loc_18010C29D
0x18010c283  cmp     [rdx+18h], r11b
0x18010c287  jz      short loc_18010C296
0x18010c289  cmp     [rdx+8], r11
0x18010c28d  lea     rax, ?inherit@?$StyleMetaData@$0CC@@SVG@Mso@@2V?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@B; std::optional<std::wstring> const Mso::SVG::StyleMetaData<34>::inherit
0x18010c294  jnz     short loc_18010C29D
0x18010c296  lea     rax, ?initial@?$StyleMetaData@$0CC@@SVG@Mso@@2V?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@B; std::optional<std::wstring> const Mso::SVG::StyleMetaData<34>::initial
0x18010c29d  cmp     [rax+20h], r11b
0x18010c2a1  jnz     short loc_18010C2C5
0x18010c2a3  mov     rcx, [rsp+190h+var_148]
0x18010c2a8  test    rcx, rcx
0x18010c2ab  jz      short loc_18010C2B7
0x18010c2ad  call    ??$Get@$0CC@@StyleResolveChain@SVG@Mso@@QEBAAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; Mso::SVG::StyleResolveChain::Get<34>(void)
0x18010c2b2  xor     r11d, r11d
0x18010c2b5  jmp     short loc_18010C2C5
0x18010c2b7  mov     rdx, [rdx+8]
0x18010c2bb  lea     rcx, [rsp+190h+var_148]
0x18010c2c0  call    ??$GetNormal@$0CC@@StyleResolveChain@SVG@Mso@@AEBAAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBVStyle@12@@Z; Mso::SVG::StyleResolveChain::GetNormal<34>(Mso::SVG::Style const &)
0x18010c2c5  movzx   r14d, r14b
0x18010c2c9  cmp     [rax+10h], r11
0x18010c2cd  cmovnz  r14d, r11d
0x18010c2d1  xorps   xmm0, xmm0
0x18010c2d4  movdqu  [rsp+190h+var_130], xmm0
0x18010c2da  test    r14b, r14b
0x18010c2dd  jz      short loc_18010C2E8
0x18010c2df  cmp     [rsp+190h+var_14E], r11b
0x18010c2e4  mov     al, 1
0x18010c2e6  jnz     short loc_18010C2EB
0x18010c2e8  mov     al, r11b
0x18010c2eb  mov     r13, [rbp+90h+var_100]
0x18010c2ef  mov     qword ptr [rsp+190h+var_168], r13
0x18010c2f4  mov     byte ptr [rsp+190h+var_170], al
0x18010c2f8  lea     r9, [rbp+90h+var_D0]
0x18010c2fc  lea     r8, [rsp+190h+var_148]
0x18010c301  lea     rdx, [rbp+90h+var_E8]
0x18010c305  mov     rcx, rsi
0x18010c308  call    ?ComputeFill@StylableRenderer@SVG@Mso@@QEBA?AV?$TCntPtr@UIBrush@GEL@@@3@AEBVStyleResolveChain@23@PEBURect@GEL@@_NPEBUIColorResolver@7@@Z; Mso::SVG::StylableRenderer::ComputeFill(Mso::SVG::StyleResolveChain const &,GEL::Rect const *,bool,GEL::IColorResolver const *)
0x18010c30d  nop
0x18010c30e  mov     rbx, [rbp+90h+var_E8]
0x18010c312  test    rbx, rbx
0x18010c315  jz      loc_18010C466
0x18010c31b  xor     r9d, r9d
0x18010c31e  mov     r8, rbx
0x18010c321  mov     rdx, rdi
0x18010c324  lea     rcx, [rsp+190h+var_118]
0x18010c329  call    cs:__imp_?Create@IEffectFilledPath@GEL@@SA?AV?$TCntPtr@UIEffectFilledPath@GEL@@@Ofc@@AEBUIPath@2@AEBUIBrush@2@PEBU?$TAffine3x3@N@Math@@@Z; GEL::IEffectFilledPath::Create(GEL::IPath const &,GEL::IBrush const &,Math::TAffine3x3<double> const *)
0x18010c32f  nop
0x18010c330  mov     rsi, [rax]
0x18010c333  mov     rcx, qword ptr [rsp+190h+var_130]
0x18010c338  test    rcx, rcx
0x18010c33b  jnz     short loc_18010C372
0x18010c33d  test    rsi, rsi
0x18010c340  jz      short loc_18010C356
0x18010c342  mov     rax, [rsi]
0x18010c345  mov     rcx, rsi
0x18010c348  mov     rax, [rax]
0x18010c34b  call    cs:__guard_dispatch_icall_fptr
0x18010c351  mov     rcx, qword ptr [rsp+190h+var_130]
  ... truncated ...
```
