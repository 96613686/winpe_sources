# Mso::SVG::StylableRenderer::ComputeStroke(Mso::SVG::StyleResolveChain const &,GEL::Rect const *,Mso::TCntPtr<GEL::IPen> &,Mso::TCntPtr<GEL::IBrush> &,bool,GEL::IColorResolver const *)

- ea: `0x180040c38`
- end: `0x1800415bd`
- name: `?ComputeStroke@StylableRenderer@SVG@Mso@@QEBAXAEBVStyleResolveChain@23@PEBURect@GEL@@AEAV?$TCntPtr@UIPen@GEL@@@3@AEAV?$TCntPtr@UIBrush@GEL@@@3@_NPEBUIColorResolver@6@@Z`
- size: `2437`
- prototype: ``
- caller_count: `4`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x18004256c`
- `0x18010b868`
- `0x180131598`
- `0x18013215c`

## callees

- `0x1800091d0`
- `0x18000d260`
- `0x18000d70c`
- `0x180017384`
- `0x18001a978`
- `0x18001aa70`
- `0x18001aacc`
- `0x18001cd30`
- `0x18001cd88`
- `0x180023738`
- `0x1800239c8`
- `0x180040c38`
- `0x180043a70`
- `0x18010b168`
- `0x1801395a4`
- `0x18013d650`
- `0x18013f760`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180041566`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180041574`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180041580`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18004158c`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18004159a`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800415a8`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800415b6`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180041566`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180041574`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180041580`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18004158c`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18004159a`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800415a8`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800415b6`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180041450`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180041450`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180041449`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180041449`
- `gfx!?Create@IPen@GEL@@SA?AV?$TCntPtr@UIPen@GEL@@@Ofc@@NAEBUColor@2@@Z` at `0x180040de7`
- `gfx!?Create@IPen@GEL@@SA?AV?$TCntPtr@UIPen@GEL@@@Ofc@@NAEBUColor@2@@Z` at `0x1800410f9`
- `gfx!?Create@IPen@GEL@@SA?AV?$TCntPtr@UIPen@GEL@@@Ofc@@NAEBUColor@2@@Z` at `0x180041469`
- `gfx!?Create@IPen@GEL@@SA?AV?$TCntPtr@UIPen@GEL@@@Ofc@@NAEBUColor@2@@Z` at `0x180040de7`
- `gfx!?Create@IPen@GEL@@SA?AV?$TCntPtr@UIPen@GEL@@@Ofc@@NAEBUColor@2@@Z` at `0x1800410f9`
- `gfx!?Create@IPen@GEL@@SA?AV?$TCntPtr@UIPen@GEL@@@Ofc@@NAEBUColor@2@@Z` at `0x180041469`
- `gfx!?Create@IPen@GEL@@SA?AV?$TCntPtr@UIPen@GEL@@@Ofc@@N@Z` at `0x1800411de`
- `gfx!?Create@IPen@GEL@@SA?AV?$TCntPtr@UIPen@GEL@@@Ofc@@N@Z` at `0x1800411de`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall Mso::SVG::StylableRenderer::ComputeStroke(
        __int64 a1,
        const struct Mso::SVG::StyleResolveChain *a2,
        __int64 a3,
        Mso::SVG **a4,
        __int64 *a5,
        char a6,
        __int64 a7)
{
  double v11; // xmm0_8
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // r14
  Mso::SVG **v15; // rax
  Mso::SVG *v16; // rsi
  Mso::SVG *v17; // rcx
  Mso::SVG *v18; // rcx
  __int64 v19; // rcx
  struct CrashContext *v20; // rdx
  struct CrashContext *v21; // rdx
  __int32 v22; // xmm1_4
  char v23; // al
  __int64 v24; // rax
  Mso::SVG::Style *v25; // rcx
  struct Mso::SVG::Style *v26; // rax
  __int64 v27; // rcx
  _BYTE *v28; // r14
  __int64 v29; // rcx
  __int64 v30; // rax
  __int128 *v31; // rax
  __int64 v32; // rdx
  __int64 v33; // rax
  __int128 *v34; // rax
  Mso::SVG **v35; // rax
  const struct Mso::SVG::StyleResolveChain *v36; // r8
  Mso::SVG *v37; // r14
  Mso::SVG *v38; // rcx
  __int64 v39; // rcx
  char v40; // r14
  __int64 PaintServer; // rax
  Mso::SVG **v42; // rax
  Mso::SVG *v43; // r14
  Mso::SVG *v44; // rcx
  __int64 v45; // rcx
  __int64 v46; // r14
  __int64 v47; // rdx
  __int64 v48; // rcx
  __int64 v49; // rcx
  __int64 v50; // rax
  __int128 *v51; // rax
  __int64 v52; // rdx
  float v53; // xmm1_4
  __int64 v54; // rax
  __int128 *v55; // rax
  Mso::SVG *v56; // rcx
  __int64 v57; // rcx
  void *v58; // rcx
  Mso::SVG **v59; // rax
  Mso::SVG *v60; // r14
  Mso::SVG *v61; // rcx
  __int64 v62; // rcx
  Mso::SVG *v63; // rcx
  __int64 v64; // rcx
  __int64 v65; // [rsp+38h] [rbp-D0h] BYREF
  __m128i si128; // [rsp+40h] [rbp-C8h] BYREF
  __m128i v67; // [rsp+50h] [rbp-B8h] BYREF
  __m128i v68; // [rsp+60h] [rbp-A8h] BYREF
  _QWORD v69[3]; // [rsp+70h] [rbp-98h] BYREF
  void *Block[2]; // [rsp+88h] [rbp-80h] BYREF
  __m128i v71; // [rsp+98h] [rbp-70h]
  int v72; // [rsp+A8h] [rbp-60h] BYREF
  unsigned int v73; // [rsp+ACh] [rbp-5Ch]
  __m128i v74; // [rsp+B0h] [rbp-58h]
  _BYTE v75[16]; // [rsp+C0h] [rbp-48h] BYREF
  __int64 v76; // [rsp+D0h] [rbp-38h]

  Mso::SVG::StyleResolveChain::SpecialResolver<2,Mso::SVG::Paint>::operator()(&v65, &v72, a2, *((_QWORD *)a2 + 1));
  v11 = Mso::SVG::StyleResolveChain::Get<3>(a2);
  if ( v72 != 2 && v11 != 0.0 )
  {
LABEL_7:
    if ( a7 )
    {
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      if ( (*(unsigned __int8 (__fastcall **)(__int64, __m128i *))(*(_QWORD *)a7 + 32LL))(a7, &si128) )
      {
        if ( v72 != 2 && v11 != 0.0 )
        {
LABEL_13:
          v15 = (Mso::SVG **)GEL::IPen::Create(&v68, v12, &si128);
          v16 = *v15;
          if ( *v15 )
            (**(void (__fastcall ***)(Mso::SVG *))v16)(*v15);
          v17 = *a4;
          *a4 = v16;
          if ( v17 )
            (*(void (__fastcall **)(Mso::SVG *))(*(_QWORD *)v17 + 8LL))(v17);
          v18 = (Mso::SVG *)v68.m128i_i64[0];
          if ( !v68.m128i_i64[0] )
            goto LABEL_19;
          goto LABEL_18;
        }
        v13 = *(_QWORD *)(*(_QWORD *)(a1 + 24) + 64LL);
        v14 = *(_QWORD *)(v13 + 528);
        if ( v14 )
        {
          (**(void (__fastcall ***)(_QWORD))v14)(*(_QWORD *)(v13 + 528));
          Mso::SVG::LengthResolver::ResolveLength(
            *((Mso::SVG::LengthResolver **)a2 + 2),
            (const struct Mso::SVG::Length *)(v14 + 424),
            a2);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
          goto LABEL_13;
        }
        goto LABEL_136;
      }
    }
    if ( (unsigned int)(v72 - 3) <= 1 )
    {
      si128 = v74;
      v67 = v74;
      if ( a7 )
      {
        v20 = *(struct CrashContext **)(a1 + 16);
        if ( !v20 )
        {
LABEL_137:
          CrashWithRecovery(0x1E3C3843u, v20);
          goto LABEL_138;
        }
        (*(void (__fastcall **)(__int64, __int64, __m128i *))(*(_QWORD *)a7 + 16LL))(a7, (__int64)v20 + 216, &v67);
        v21 = *(struct CrashContext **)(a1 + 16);
        if ( !v21 )
        {
LABEL_138:
          CrashWithRecovery(0x1E3C3843u, v21);
          goto LABEL_139;
        }
        (*(void (__fastcall **)(__int64, __int64, __m128i *))(*(_QWORD *)a7 + 16LL))(a7, (__int64)v21 + 280, &v67);
        COERCE_FLOAT(v22 = _mm_load_si128((const __m128i *)&_xmm).m128i_i32[0]);
        if ( COERCE_FLOAT(COERCE_UNSIGNED_INT(*(float *)v67.m128i_i32 - *(float *)si128.m128i_i32) & v22) >= 0.00000023841858
          || COERCE_FLOAT(COERCE_UNSIGNED_INT(*(float *)&v67.m128i_i32[1] - *(float *)&si128.m128i_i32[1]) & v22) >= 0.00000023841858
          || COERCE_FLOAT(COERCE_UNSIGNED_INT(*(float *)&v67.m128i_i32[2] - *(float *)&si128.m128i_i32[2]) & v22) >= 0.00000023841858
          || (v23 = 0,
              COERCE_FLOAT(COERCE_UNSIGNED_INT(*(float *)&v67.m128i_i32[3] - *(float *)&si128.m128i_i32[3]) & v22) >= 0.00000023841858) )
        {
          v23 = 1;
        }
        if ( v23 )
        {
          v24 = *(_QWORD *)(a1 + 16);
          if ( !v24 )
          {
LABEL_139:
            CrashWithRecovery(0x1E3C3843u, 0);
            goto LABEL_140;
          }
          v69[0] = 0x200000003LL;
          *(__m128i *)&v69[1] = v67;
          *(_OWORD *)Block = 0;
          v71 = _mm_load_si128((const __m128i *)&_xmm);
          LOWORD(Block[0]) = 0;
          v25 = *(Mso::SVG::Style **)(v24 + 152);
          if ( !v25 )
          {
LABEL_140:
            CrashWithRecovery(0x1E3C3840u, 0);
            goto LABEL_141;
          }
          v26 = Mso::SVG::Style::EnsureWritable(v25);
          Mso::SVG::Style::Set<2>(v26, v69);
          std::wstring::~wstring(Block);
          si128 = v67;
          v27 = *(_QWORD *)(*(_QWORD *)(a1 + 24) + 64LL);
          v28 = *(_BYTE **)(v27 + 528);
          if ( !v28 )
          {
LABEL_141:
            CrashWithRecovery(0x1E3C3840u, 0);
            JUMPOUT(0x1800415BCLL);
          }
          (**(void (__fastcall ***)(_QWORD))v28)(*(_QWORD *)(v27 + 528));
          v28[536] = 1;
          (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v28 + 8LL))(v28);
        }
      }
      v29 = *((_QWORD *)a2 + 1);
      v30 = *(_QWORD *)(v29 + 16);
      if ( v30 )
      {
        v31 = (__int128 *)(v30 + 1080);
      }
      else
      {
        v31 = &Mso::SVG::StyleMetaData<9>::initial;
        if ( *(_QWORD *)(v29 + 8) )
          v31 = (__int128 *)&Mso::SVG::StyleMetaData<9>::inherit;
      }
      v32 = 8;
      if ( !*((_BYTE *)v31 + 8) )
      {
        if ( *(_QWORD *)a2 )
          v31 = (__int128 *)Mso::SVG::StyleResolveChain::Get<9>(*(_QWORD *)a2, 8);
        else
          v31 = (__int128 *)Mso::SVG::StyleResolveChain::GetNormal<9>(a2, *(_QWORD *)(v29 + 8));
      }
      *(float *)&si128.m128i_i32[3] = *(float *)&si128.m128i_i32[3] * (float)*(double *)v31;
      if ( a6 )
      {
        v32 = *((_QWORD *)a2 + 1);
        v33 = *(_QWORD *)(v32 + 16);
        if ( v33 )
        {
          v34 = (__int128 *)(v33 + 272);
        }
        else if ( !*(_BYTE *)(v32 + 24)
               || (v34 = (__int128 *)&Mso::SVG::StyleMetaData<36>::inherit, !*(_QWORD *)(v32 + 8)) )
        {
          v34 = &Mso::SVG::StyleMetaData<36>::initial;
        }
        if ( !*((_BYTE *)v34 + 8) )
        {
          if ( *(_QWORD *)a2 )
            v34 = (__int128 *)Mso::SVG::StyleResolveChain::Get<36>();
          else
            v34 = (__int128 *)Mso::SVG::StyleResolveChain::GetNormal<36>(a2, *(_QWORD *)(v32 + 8));
        }
        *(float *)&si128.m128i_i32[3] = *(float *)&si128.m128i_i32[3] * (float)*(double *)v34;
      }
      if ( *(float *)&si128.m128i_i32[3] <= 0.0 )
      {
LABEL_55:
        v18 = *a4;
        if ( !*a4 )
        {
LABEL_19:
          v19 = *a5;
          if ( *a5 )
          {
            *a5 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 8LL))(v19);
          }
          goto LABEL_134;
        }
        *a4 = 0;
LABEL_18:
        (*(void (__fastcall **)(Mso::SVG *))(*(_QWORD *)v18 + 8LL))(v18);
        goto LABEL_19;
      }
      v35 = (Mso::SVG **)GEL::IPen::Create(&v68, v32, &si128);
      v37 = *v35;
      if ( *v35 )
        (**(void (__fastcall ***)(Mso::SVG *))v37)(*v35);
      v38 = *a4;
      *a4 = v37;
      if ( v38 )
        (*(void (__fastcall **)(Mso::SVG *))(*(_QWORD *)v38 + 8LL))(v38);
      if ( v68.m128i_i64[0] )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v68.m128i_i64[0] + 8LL))(v68.m128i_i64[0]);
      v39 = *a5;
      if ( *a5 )
      {
        *a5 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 8LL))(v39);
      }
      goto LABEL_127;
    }
    v40 = 1;
    if ( !v76 )
      goto LABEL_86;
    PaintServer = Mso::SVG::Environment::QueryPaintServer(*(_QWORD *)(*(_QWORD *)(a1 + 24) + 64LL), v75);
    if ( !PaintServer )
      goto LABEL_86;
    Mso::SVG::PaintServerRenderer::Create(&v68, PaintServer, *(_QWORD *)(a1 + 24));
    if ( !v68.m128i_i64[0] )
    {
      CrashWithRecovery(0x1E3C3840u, 0);
LABEL_136:
      CrashWithRecovery(0x1E3C3840u, 0);
      goto LABEL_137;
    }
    (*(void (__fastcall **)(__int64, __m128i *, const struct Mso::SVG::StyleResolveChain *, __int64, char))(*(_QWORD *)v68.m128i_i64[0] + 32LL))(
      v68.m128i_i64[0],
      &v67,
      a2,
      a3,
      1);
    if ( v67.m128i_i64[0] )
    {
      v42 = (Mso::SVG **)GEL::IPen::Create(&si128);
      v43 = *v42;
      if ( *v42 )
        (**(void (__fastcall ***)(Mso::SVG *))v43)(*v42);
      v44 = *a4;
      *a4 = v43;
      if ( v44 )
        (*(void (__fastcall **)(Mso::SVG *))(*(_QWORD *)v44 + 8LL))(v44);
      if ( si128.m128i_i64[0] )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)si128.m128i_i64[0] + 8LL))(si128.m128i_i64[0]);
      v45 = v67.m128i_i64[0];
      v46 = v67.m128i_i64[0];
      if ( *a5 != v67.m128i_i64[0] )
      {
        if ( v67.m128i_i64[0] )
        {
          (**(void (***)(void))v67.m128i_i64[0])();
          v45 = v67.m128i_i64[0];
        }
        v47 = *a5;
        if ( *a5 )
        {
          *a5 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 8LL))(v47);
          v45 = v67.m128i_i64[0];
        }
        *a5 = v46;
      }
      v40 = 0;
      if ( v45 )
      {
        v67.m128i_i64[0] = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 8LL))(v45);
      }
    }
    v48 = v68.m128i_i64[0];
    if ( v68.m128i_i64[0] )
    {
      v68.m128i_i64[0] = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 8LL))(v48);
    }
    if ( v40 )
    {
LABEL_86:
      if ( v72 != 1 )
        goto LABEL_55;
      v69[0] = v73 | 0x200000000LL;
      *(__m128i *)&v69[1] = v74;
      *(_OWORD *)Block = 0;
      v71 = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(Block[0]) = 0;
      if ( v73 == 2 )
        goto LABEL_109;
      v68 = v74;
      v49 = *((_QWORD *)a2 + 1);
      v50 = *(_QWORD *)(v49 + 16);
      if ( v50 )
      {
        v51 = (__int128 *)(v50 + 1080);
      }
      else
      {
        v51 = &Mso::SVG::StyleMetaData<9>::initial;
        if ( *(_QWORD *)(v49 + 8) )
          v51 = (__int128 *)&Mso::SVG::StyleMetaData<9>::inherit;
      }
      v52 = 8;
      if ( !*((_BYTE *)v51 + 8) )
      {
        if ( *(_QWORD *)a2 )
          v51 = (__int128 *)Mso::SVG::StyleResolveChain::Get<9>(*(_QWORD *)a2, 8);
        else
          v51 = (__int128 *)Mso::SVG::StyleResolveChain::GetNormal<9>(a2, *(_QWORD *)(v49 + 8));
      }
      v53 = *(double *)v51;
      *(float *)&v68.m128i_i32[3] = v53;
      if ( a6 )
      {
        v52 = *((_QWORD *)a2 + 1);
        v54 = *(_QWORD *)(v52 + 16);
        if ( v54 )
        {
          v55 = (__int128 *)(v54 + 272);
        }
        else if ( !*(_BYTE *)(v52 + 24)
               || (v55 = (__int128 *)&Mso::SVG::StyleMetaData<36>::inherit, !*(_QWORD *)(v52 + 8)) )
        {
          v55 = &Mso::SVG::StyleMetaData<36>::initial;
        }
        if ( !*((_BYTE *)v55 + 8) )
        {
          if ( *(_QWORD *)a2 )
            v55 = (__int128 *)Mso::SVG::StyleResolveChain::Get<36>();
          else
            v55 = (__int128 *)Mso::SVG::StyleResolveChain::GetNormal<36>(a2, *(_QWORD *)(v52 + 8));
          v53 = *(float *)&v68.m128i_i32[3];
        }
        v53 = v53 * (float)*(double *)v55;
        *(float *)&v68.m128i_i32[3] = v53;
      }
      if ( v53 <= 0.0 )
      {
LABEL_109:
        v56 = *a4;
        if ( *a4 )
        {
          *a4 = 0;
          (*(void (__fastcall **)(Mso::SVG *))(*(_QWORD *)v56 + 8LL))(v56);
        }
        v57 = *a5;
        if ( *a5 )
        {
          *a5 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 8LL))(v57);
        }
        if ( v71.m128i_i64[1] > 7uLL )
        {
          v58 = Block[0];
          if ( (unsigned __int64)(2 * v71.m128i_i64[1] + 2) >= 0x1000 )
          {
            v58 = (void *)*((_QWORD *)Block[0] - 1);
            if ( (unsigned __int64)((char *)Block[0] - (char *)v58 - 8) > 0x1F )
              _invoke_watson(0, 0, 0, 0, 0);
          }
          free(v58);
        }
        goto LABEL_134;
      }
      v59 = (Mso::SVG **)GEL::IPen::Create(&si128, v52, &v68);
      v60 = *v59;
      if ( *v59 )
        (**(void (__fastcall ***)(Mso::SVG *))v60)(*v59);
      v61 = *a4;
      *a4 = v60;
      if ( v61 )
        (*(void (__fastcall **)(Mso::SVG *))(*(_QWORD *)v61 + 8LL))(v61);
      if ( si128.m128i_i64[0] )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)si128.m128i_i64[0] + 8LL))(si128.m128i_i64[0]);
      v62 = *a5;
      if ( *a5 )
      {
        *a5 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 8LL))(v62);
      }
      std::wstring::~wstring(Block);
    }
LABEL_127:
    if ( *a4 )
      Mso::SVG::SetPenProps(*a4, a2, v36);
    goto LABEL_134;
  }
  Mso::SVG::StyleResolveChain::SpecialResolver<10,Mso::SVG::Paint>::operator()(&v65, v69, a2, *((_QWORD *)a2 + 1));
  if ( a7 && (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)a7 + 40LL))(a7) && LODWORD(v69[0]) != 2 )
  {
    std::wstring::~wstring(Block);
    goto LABEL_7;
  }
  v63 = *a4;
  if ( *a4 )
  {
    *a4 = 0;
    (*(void (__fastcall **)(Mso::SVG *))(*(_QWORD *)v63 + 8LL))(v63);
  }
  v64 = *a5;
  if ( *a5 )
  {
    *a5 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 8LL))(v64);
  }
  std::wstring::~wstring(Block);
LABEL_134:
  std::wstring::~wstring(v75);
}

```

## disassembly

```asm
0x180040c38  mov     rax, rsp
0x180040c3b  push    rbp
0x180040c3c  push    rbx
0x180040c3d  push    rsi
0x180040c3e  push    rdi
0x180040c3f  push    r12
0x180040c41  push    r13
0x180040c43  push    r14
0x180040c45  push    r15
0x180040c47  lea     rbp, [rax-58h]
0x180040c4b  sub     rsp, 118h
0x180040c52  movaps  xmmword ptr [rax-58h], xmm6
0x180040c56  movaps  xmmword ptr [rax-68h], xmm7
0x180040c5a  movaps  xmmword ptr [rax-78h], xmm8
0x180040c5f  mov     rax, cs:__security_cookie
0x180040c66  xor     rax, rsp
0x180040c69  mov     [rbp+50h+var_78], rax
0x180040c6d  mov     rdi, r9
0x180040c70  mov     r12, r8
0x180040c73  mov     rsi, rdx
0x180040c76  mov     r15, rcx
0x180040c79  mov     rbx, [rbp+50h+arg_20]
0x180040c80  mov     r14, [rbp+50h+arg_30]
0x180040c87  xor     r13d, r13d
0x180040c8a  mov     r9, [rdx+8]
0x180040c8e  mov     r8, rdx
0x180040c91  lea     rdx, [rbp+50h+var_B0]
0x180040c95  lea     rcx, [rsp+150h+var_120]
0x180040c9a  call    ??R?$SpecialResolver@$01VPaint@SVG@Mso@@@StyleResolveChain@SVG@Mso@@QEBA?AVPaint@23@AEBV123@AEBVStyle@23@@Z; Mso::SVG::StyleResolveChain::SpecialResolver<2,Mso::SVG::Paint>::operator()(Mso::SVG::StyleResolveChain const &,Mso::SVG::Style const &)
0x180040c9f  mov     rcx, rsi
0x180040ca2  call    ??$Get@$02@StyleResolveChain@SVG@Mso@@QEBANXZ; Mso::SVG::StyleResolveChain::Get<3>(void)
0x180040ca7  movaps  xmm8, xmm0
0x180040cab  xorps   xmm7, xmm7
0x180040cae  cmp     [rbp+50h+var_B0], 2
0x180040cb2  jz      short loc_180040CBC
0x180040cb4  ucomisd xmm0, xmm7
0x180040cb8  jp      short loc_180040D07
0x180040cba  jnz     short loc_180040D07
0x180040cbc  mov     r9, [rsi+8]
0x180040cc0  mov     r8, rsi
0x180040cc3  lea     rdx, [rsp+150h+var_E8]
0x180040cc8  lea     rcx, [rsp+150h+var_120]
0x180040ccd  call    ??R?$SpecialResolver@$09VPaint@SVG@Mso@@@StyleResolveChain@SVG@Mso@@QEBA?AVPaint@23@AEBV123@AEBVStyle@23@@Z; Mso::SVG::StyleResolveChain::SpecialResolver<10,Mso::SVG::Paint>::operator()(Mso::SVG::StyleResolveChain const &,Mso::SVG::Style const &)
0x180040cd2  test    r14, r14
0x180040cd5  jz      loc_1800414E8
0x180040cdb  mov     rax, [r14]
0x180040cde  mov     rcx, r14
0x180040ce1  mov     rax, [rax+28h]
0x180040ce5  call    cs:__guard_dispatch_icall_fptr
0x180040ceb  test    al, al
0x180040ced  jz      loc_1800414E8
0x180040cf3  cmp     dword ptr [rsp+150h+var_E8], 2
0x180040cf8  jz      loc_1800414E8
0x180040cfe  lea     rcx, [rbp+50h+Block]; void *
0x180040d02  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180040d07  test    r14, r14
0x180040d0a  jz      loc_180040E54
0x180040d10  movdqa  xmm0, cs:__xmm@3f8000003f8000003f8000003f800000
0x180040d18  movups  [rsp+150h+var_120+8], xmm0
0x180040d1d  mov     rax, [r14]
0x180040d20  lea     rdx, [rsp+150h+var_120+8]
0x180040d25  mov     rcx, r14
0x180040d28  mov     rax, [rax+20h]
0x180040d2c  call    cs:__guard_dispatch_icall_fptr
0x180040d32  test    al, al
0x180040d34  jz      loc_180040E54
0x180040d3a  ucomisd xmm8, xmm7
0x180040d3f  jp      short loc_180040D4D
0x180040d41  jnz     short loc_180040D4D
0x180040d43  movsd   xmm6, cs:__real@3ff0000000000000
0x180040d4b  jmp     short loc_180040D51
0x180040d4d  movaps  xmm6, xmm8
0x180040d51  cmp     [rbp+50h+var_B0], 2
0x180040d55  jz      short loc_180040D60
0x180040d57  ucomisd xmm8, xmm7
0x180040d5c  jp      short loc_180040DDA
0x180040d5e  jnz     short loc_180040DDA
0x180040d60  mov     rax, [r15+18h]
0x180040d64  mov     rcx, [rax+40h]
0x180040d68  mov     r14, [rcx+210h]
0x180040d6f  test    r14, r14
0x180040d72  jz      short loc_180040D84
0x180040d74  mov     rax, [r14]
0x180040d77  mov     rcx, r14
0x180040d7a  mov     rax, [rax]
0x180040d7d  call    cs:__guard_dispatch_icall_fptr
0x180040d83  nop
0x180040d84  test    r14, r14
0x180040d87  jz      loc_18004156D
0x180040d8d  lea     rdx, [r14+1A8h]; struct Mso::SVG::Length *
0x180040d94  mov     r8, rsi; struct Mso::SVG::StyleResolveChain *
0x180040d97  mov     rcx, [rsi+10h]; this
0x180040d9b  call    ?ResolveLength@LengthResolver@SVG@Mso@@AEBANAEBULength@23@AEBVStyleResolveChain@23@@Z; Mso::SVG::LengthResolver::ResolveLength(Mso::SVG::Length const &,Mso::SVG::StyleResolveChain const &)
0x180040da0  movaps  xmm8, xmm0
0x180040da4  mov     rax, [r14]
0x180040da7  mov     rcx, r14
0x180040daa  mov     rax, [rax+8]
0x180040dae  call    cs:__guard_dispatch_icall_fptr
0x180040db4  movsd   xmm1, qword ptr [r12+10h]
0x180040dbb  subsd   xmm1, qword ptr [r12]
0x180040dc1  ucomisd xmm8, xmm7
0x180040dc6  jp      short loc_180040DCA
0x180040dc8  jz      short loc_180040DDA
0x180040dca  ucomisd xmm1, xmm7
0x180040dce  jp      short loc_180040DD2
0x180040dd0  jz      short loc_180040DDA
0x180040dd2  movaps  xmm6, xmm1
0x180040dd5  divsd   xmm6, xmm8
0x180040dda  lea     r8, [rsp+150h+var_120+8]
0x180040ddf  movaps  xmm1, xmm6
0x180040de2  lea     rcx, [rsp+150h+var_100+8]
0x180040de7  call    cs:__imp_?Create@IPen@GEL@@SA?AV?$TCntPtr@UIPen@GEL@@@Ofc@@NAEBUColor@2@@Z; GEL::IPen::Create(double,GEL::Color const &)
0x180040ded  mov     rsi, [rax]
0x180040df0  test    rsi, rsi
0x180040df3  jz      short loc_180040E04
0x180040df5  mov     rax, [rsi]
0x180040df8  mov     rcx, rsi
0x180040dfb  mov     rax, [rax]
0x180040dfe  call    cs:__guard_dispatch_icall_fptr
0x180040e04  mov     rcx, [rdi]
0x180040e07  mov     [rdi], rsi
0x180040e0a  test    rcx, rcx
0x180040e0d  jz      short loc_180040E1C
0x180040e0f  mov     rax, [rcx]
0x180040e12  mov     rax, [rax+8]
0x180040e16  call    cs:__guard_dispatch_icall_fptr
0x180040e1c  mov     rcx, qword ptr [rsp+150h+var_100+8]
0x180040e21  test    rcx, rcx
0x180040e24  jz      short loc_180040E33
0x180040e26  mov     rax, [rcx]
0x180040e29  mov     rax, [rax+8]
0x180040e2d  call    cs:__guard_dispatch_icall_fptr
0x180040e33  mov     rcx, [rbx]
0x180040e36  test    rcx, rcx
0x180040e39  jz      loc_180041523
0x180040e3f  mov     [rbx], r13
0x180040e42  mov     rax, [rcx]
0x180040e45  mov     rax, [rax+8]
0x180040e49  call    cs:__guard_dispatch_icall_fptr
0x180040e4f  jmp     loc_180041523
0x180040e54  mov     eax, [rbp+50h+var_B0]
0x180040e57  add     eax, 0FFFFFFFDh
0x180040e5a  cmp     eax, 1
0x180040e5d  ja      loc_180041166
0x180040e63  movups  xmm0, [rbp+50h+var_A8]
0x180040e67  movups  [rsp+150h+var_120+8], xmm0
0x180040e6c  movups  [rsp+150h+var_110+8], xmm0
0x180040e71  test    r14, r14
0x180040e74  jz      loc_180040FF5
0x180040e7a  mov     rax, [r14]
0x180040e7d  mov     rax, [rax+10h]
0x180040e81  mov     rdx, [r15+10h]
0x180040e85  test    rdx, rdx
0x180040e88  jz      loc_18004157B
0x180040e8e  add     rdx, 0D8h
0x180040e95  lea     r8, [rsp+150h+var_110+8]
0x180040e9a  mov     rcx, r14
0x180040e9d  call    cs:__guard_dispatch_icall_fptr
0x180040ea3  mov     rax, [r14]
0x180040ea6  mov     rax, [rax+10h]
0x180040eaa  mov     rdx, [r15+10h]
0x180040eae  test    rdx, rdx
0x180040eb1  jz      loc_180041587
0x180040eb7  add     rdx, 118h
0x180040ebe  lea     r8, [rsp+150h+var_110+8]
0x180040ec3  mov     rcx, r14
0x180040ec6  call    cs:__guard_dispatch_icall_fptr
0x180040ecc  movss   xmm0, dword ptr [rsp+150h+var_110+8]
0x180040ed2  subss   xmm0, dword ptr [rsp+150h+var_120+8]
0x180040ed8  movdqa  xmm1, cs:__xmm@7fffffff7fffffff7fffffff7fffffff
0x180040ee0  andps   xmm0, xmm1
0x180040ee3  movss   xmm2, cs:__real@34800000
0x180040eeb  comiss  xmm2, xmm0
0x180040eee  jbe     short loc_180040F2F
0x180040ef0  movss   xmm0, dword ptr [rsp+150h+var_110+0Ch]
0x180040ef6  subss   xmm0, dword ptr [rsp+150h+var_120+0Ch]
0x180040efc  andps   xmm0, xmm1
0x180040eff  comiss  xmm2, xmm0
0x180040f02  jbe     short loc_180040F2F
0x180040f04  movss   xmm0, dword ptr [rsp+150h+var_100]
0x180040f0a  subss   xmm0, dword ptr [rsp+150h+var_110]
0x180040f10  andps   xmm0, xmm1
0x180040f13  comiss  xmm2, xmm0
0x180040f16  jbe     short loc_180040F2F
0x180040f18  movss   xmm0, dword ptr [rsp+150h+var_100+4]
0x180040f1e  subss   xmm0, dword ptr [rsp+150h+var_110+4]
0x180040f24  andps   xmm0, xmm1
0x180040f27  comiss  xmm2, xmm0
0x180040f2a  mov     al, r13b
0x180040f2d  ja      short loc_180040F31
0x180040f2f  mov     al, 1
0x180040f31  test    al, al
0x180040f33  jz      loc_180040FF5
0x180040f39  mov     rax, [r15+10h]
0x180040f3d  test    rax, rax
0x180040f40  jz      loc_180041593
0x180040f46  mov     dword ptr [rsp+150h+var_E8], 3
0x180040f4e  mov     dword ptr [rsp+150h+var_E8+4], 2
0x180040f56  movups  xmm0, [rsp+150h+var_110+8]
0x180040f5b  movdqu  xmmword ptr [rsp+150h+var_E8+8], xmm0
0x180040f61  xorps   xmm1, xmm1
0x180040f64  movups  xmmword ptr [rbp+50h+Block], xmm1
0x180040f68  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x180040f70  movdqu  [rbp+50h+var_C0], xmm0
0x180040f75  mov     word ptr [rbp+50h+Block], r13w
0x180040f7a  mov     rcx, [rax+98h]; this
0x180040f81  test    rcx, rcx
0x180040f84  jz      loc_1800415A1
0x180040f8a  call    ?EnsureWritable@Style@SVG@Mso@@AEAAAEAV123@XZ; Mso::SVG::Style::EnsureWritable(void)
0x180040f8f  lea     rdx, [rsp+150h+var_E8]
0x180040f94  mov     rcx, rax
0x180040f97  call    ??$Set@$01@Style@SVG@Mso@@QEAAX$$QEAVPaint@12@@Z; Mso::SVG::Style::Set<2>(Mso::SVG::Paint &&)
0x180040f9c  nop
0x180040f9d  lea     rcx, [rbp+50h+Block]; void *
0x180040fa1  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180040fa6  movups  xmm0, [rsp+150h+var_110+8]
0x180040fab  movups  [rsp+150h+var_120+8], xmm0
0x180040fb0  mov     rax, [r15+18h]
0x180040fb4  mov     rcx, [rax+40h]
0x180040fb8  mov     r14, [rcx+210h]
0x180040fbf  test    r14, r14
0x180040fc2  jz      short loc_180040FD4
0x180040fc4  mov     rax, [r14]
0x180040fc7  mov     rcx, r14
0x180040fca  mov     rax, [rax]
0x180040fcd  call    cs:__guard_dispatch_icall_fptr
0x180040fd3  nop
0x180040fd4  test    r14, r14
0x180040fd7  jz      loc_1800415AF
0x180040fdd  mov     byte ptr [r14+218h], 1
0x180040fe5  mov     rax, [r14]
0x180040fe8  mov     rcx, r14
0x180040feb  mov     rax, [rax+8]
0x180040fef  call    cs:__guard_dispatch_icall_fptr
0x180040ff5  mov     rcx, [rsi+8]
0x180040ff9  mov     rax, [rcx+10h]
0x180040ffd  test    rax, rax
0x180041000  jz      short loc_18004100A
0x180041002  add     rax, 438h
0x180041008  jmp     short loc_18004101E
0x18004100a  cmp     [rcx+8], r13
0x18004100e  lea     rax, ?initial@?$StyleMetaData@$08@SVG@Mso@@2V?$optional@N@std@@B; std::optional<double> const Mso::SVG::StyleMetaData<9>::initial
0x180041015  jz      short loc_18004101E
0x180041017  lea     rax, ?inherit@?$StyleMetaData@$08@SVG@Mso@@2V?$optional@N@std@@B; std::optional<double> const Mso::SVG::StyleMetaData<9>::inherit
0x18004101e  mov     edx, 8
0x180041023  cmp     [rax+8], r13b
0x180041027  jnz     short loc_180041044
0x180041029  cmp     [rsi], r13
0x18004102c  jz      short loc_180041038
0x18004102e  mov     rcx, [rsi]
0x180041031  call    ??$Get@$08@StyleResolveChain@SVG@Mso@@QEBAAEBNXZ; Mso::SVG::StyleResolveChain::Get<9>(void)
0x180041036  jmp     short loc_180041044
0x180041038  mov     rdx, [rdx+rcx]
0x18004103c  mov     rcx, rsi
0x18004103f  call    ??$GetNormal@$08@StyleResolveChain@SVG@Mso@@AEBAAEBNAEBVStyle@12@@Z; Mso::SVG::StyleResolveChain::GetNormal<9>(Mso::SVG::Style const &)
0x180041044  movsd   xmm0, qword ptr [rax]
0x180041048  cvtpd2ps xmm0, xmm0
0x18004104c  movss   xmm1, dword ptr [rsp+150h+var_110+4]
0x180041052  mulss   xmm1, xmm0
0x180041056  movss   dword ptr [rsp+150h+var_110+4], xmm1
0x18004105c  cmp     [rbp+50h+arg_28], r13b
0x180041063  jz      short loc_1800410CD
0x180041065  mov     rdx, [rsi+8]
0x180041069  mov     rax, [rdx+10h]
0x18004106d  test    rax, rax
0x180041070  jz      short loc_18004107A
0x180041072  add     rax, 110h
0x180041078  jmp     short loc_180041094
0x18004107a  cmp     [rdx+18h], r13b
0x18004107e  jz      short loc_18004108D
0x180041080  cmp     [rdx+8], r13
0x180041084  lea     rax, ?inherit@?$StyleMetaData@$0CE@@SVG@Mso@@2V?$optional@N@std@@B; std::optional<double> const Mso::SVG::StyleMetaData<36>::inherit
0x18004108b  jnz     short loc_180041094
0x18004108d  lea     rax, ?initial@?$StyleMetaData@$0CE@@SVG@Mso@@2V?$optional@N@std@@B; std::optional<double> const Mso::SVG::StyleMetaData<36>::initial
0x180041094  cmp     [rax+8], r13b
0x180041098  jnz     short loc_1800410B5
0x18004109a  mov     rcx, [rsi]
0x18004109d  test    rcx, rcx
0x1800410a0  jz      short loc_1800410A9
0x1800410a2  call    ??$Get@$0CE@@StyleResolveChain@SVG@Mso@@QEBAAEBNXZ; Mso::SVG::StyleResolveChain::Get<36>(void)
0x1800410a7  jmp     short loc_1800410B5
0x1800410a9  mov     rdx, [rdx+8]
0x1800410ad  mov     rcx, rsi
0x1800410b0  call    ??$GetNormal@$0CE@@StyleResolveChain@SVG@Mso@@AEBAAEBNAEBVStyle@12@@Z; Mso::SVG::StyleResolveChain::GetNormal<36>(Mso::SVG::Style const &)
0x1800410b5  movsd   xmm0, qword ptr [rax]
0x1800410b9  cvtpd2ps xmm0, xmm0
0x1800410bd  movss   xmm1, dword ptr [rsp+150h+var_110+4]
0x1800410c3  mulss   xmm1, xmm0
0x1800410c7  movss   dword ptr [rsp+150h+var_110+4], xmm1
0x1800410cd  xorps   xmm0, xmm0
0x1800410d0  comiss  xmm0, dword ptr [rsp+150h+var_110+4]
0x1800410d5  jb      short loc_1800410EB
0x1800410d7  mov     rcx, [rdi]
0x1800410da  test    rcx, rcx
0x1800410dd  jz      loc_180040E33
0x1800410e3  mov     [rdi], r13
0x1800410e6  jmp     loc_180040E26
0x1800410eb  lea     r8, [rsp+150h+var_120+8]
0x1800410f0  movaps  xmm1, xmm8
0x1800410f4  lea     rcx, [rsp+150h+var_100+8]
  ... truncated ...
```
