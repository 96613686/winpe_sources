# Mso::SVG::ImageRenderer::Render(GEL::EffectAccumulator &,Mso::SVG::StyleResolveChain const &,GEL::Rect *,GEL::IColorResolver const *)

- ea: `0x180102d70`
- end: `0x1801034d6`
- name: `?Render@ImageRenderer@SVG@Mso@@UEAAXAEAVEffectAccumulator@GEL@@AEBVStyleResolveChain@23@PEAURect@5@PEBUIColorResolver@5@@Z`
- size: `1894`
- prototype: `void __usercall(Mso::SVG::ImageRenderer *__hidden this@<rcx>, struct GEL::EffectAccumulator *@<rdx>, const struct Mso::SVG::StyleResolveChain *@<r8>, struct GEL::Rect *@<r9>, const struct GEL::IColorResolver *)`
- caller_count: `0`
- callee_count: `22`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000d5e0`
- `0x18001b64c`
- `0x18003f8f0`
- `0x180041df8`
- `0x180042580`
- `0x180043440`
- `0x180043594`
- `0x180043c28`
- `0x1800447d0`
- `0x18004c058`
- `0x18004e660`
- `0x18004f538`
- `0x180101720`
- `0x1801017b8`
- `0x180102d70`
- `0x1801034d8`
- `0x180103f34`
- `0x180103f90`
- `0x1801395e4`
- `0x180139658`
- `0x18013e0c0`
- `0x18013f810`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1801034cf`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1801034cf`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x18010303f`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x18010303f`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180103073`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180103073`
- `Mso20Win32Client!__imp_?ThrowOOM@@YAXXZ` at `0x18010304d`
- `Mso20Win32Client!__imp_?ThrowOOM@@YAXXZ` at `0x18010304d`
- `gfx!?Create@IRectanglePath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@AEBU?$TRect@N@Math@@@Z` at `0x180102ff9`
- `gfx!?Create@IRectanglePath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@AEBU?$TRect@N@Math@@@Z` at `0x180102ff9`
- `gfx!?Create@IEffectTransform@GEL@@SA?AV?$TCntPtr@UIEffectTransform@GEL@@@Ofc@@AEBUIEffect@2@AEBU?$TAffine3x3@N@Math@@@Z` at `0x180103182`
- `gfx!?Create@IEffectTransform@GEL@@SA?AV?$TCntPtr@UIEffectTransform@GEL@@@Ofc@@AEBUIEffect@2@AEBU?$TAffine3x3@N@Math@@@Z` at `0x180103182`
- `gfx!?Create@IEffectClip@GEL@@SA?AV?$TCntPtr@UIEffectClip@GEL@@@Ofc@@AEBUIEffect@2@AEBU?$TRect@N@Math@@W4CombineMode@2@@Z` at `0x1801031de`
- `gfx!?Create@IEffectClip@GEL@@SA?AV?$TCntPtr@UIEffectClip@GEL@@@Ofc@@AEBUIEffect@2@AEBU?$TRect@N@Math@@W4CombineMode@2@@Z` at `0x1801031de`
- `gfx!?Create@IEffectFilledPath@GEL@@SA?AV?$TCntPtr@UIEffectFilledPath@GEL@@@Ofc@@AEBUIPath@2@AEBUIBrush@2@PEBU?$TAffine3x3@N@Math@@@Z` at `0x1801030c3`
- `gfx!?Create@IEffectFilledPath@GEL@@SA?AV?$TCntPtr@UIEffectFilledPath@GEL@@@Ofc@@AEBUIPath@2@AEBUIBrush@2@PEBU?$TAffine3x3@N@Math@@@Z` at `0x1801030c3`
- `gfx!??0ImageFillInfo@GEL@@QEAA@XZ` at `0x180103029`
- `gfx!??0ImageFillInfo@GEL@@QEAA@XZ` at `0x180103029`
- `gfx!?Create@IBrushImage@GEL@@SA?AV?$TCntPtr@UIBrushImage@GEL@@@Ofc@@AEBUIImage@2@AEBUImageFillInfo@2@@Z` at `0x180103089`
- `gfx!?Create@IBrushImage@GEL@@SA?AV?$TCntPtr@UIBrushImage@GEL@@@Ofc@@AEBUIImage@2@AEBUImageFillInfo@2@@Z` at `0x180103089`
- `gfx!?Create@IEffectNearestNeighborInterpolation@GEL@@SA?AV?$TCntPtr@UIEffectNearestNeighborInterpolation@GEL@@@Ofc@@AEBUIEffect@2@@Z` at `0x180103354`
- `gfx!?Create@IEffectNearestNeighborInterpolation@GEL@@SA?AV?$TCntPtr@UIEffectNearestNeighborInterpolation@GEL@@@Ofc@@AEBUIEffect@2@@Z` at `0x180103354`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall Mso::SVG::ImageRenderer::Render(
        Mso::SVG::ImageRenderer *this,
        struct GEL::EffectAccumulator *a2,
        const struct Mso::SVG::StyleResolveChain *a3,
        struct GEL::Rect *a4,
        const struct GEL::IColorResolver *a5)
{
  _QWORD *v8; // r15
  __int64 v9; // rax
  __int64 v10; // rax
  __int16 *v11; // rax
  __int64 v12; // rdi
  __int64 v13; // rdx
  __int64 *v14; // rdx
  __int64 v15; // rax
  double v16; // xmm7_8
  double v17; // xmm6_8
  bool v18; // zf
  double v19; // xmm8_8
  double v20; // xmm9_8
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 *v23; // rax
  __int64 v24; // rcx
  unsigned int v25; // r8d
  Mso::Memory *v26; // rax
  void *v27; // rdx
  Mso::Memory *v28; // rbx
  __int64 *v29; // rax
  __int64 v30; // r12
  __int64 v31; // rdi
  __int64 *v32; // rax
  __int64 v33; // r14
  double v34; // xmm6_8
  double v35; // xmm0_8
  __int64 v36; // r9
  __int64 v37; // rbx
  _QWORD *v38; // rax
  __int64 *v39; // rax
  __int64 v40; // r13
  __int64 v41; // rax
  __int128 *TransformedBounds; // rax
  struct GEL::IEffect *v43; // rdi
  __int64 *v44; // rax
  const struct GEL::IEffect **v45; // rax
  const struct GEL::IEffect *v46; // r15
  __int128 *v47; // rax
  __int64 v48; // rcx
  __int64 v49; // [rsp+48h] [rbp-C0h] BYREF
  const struct Mso::SVG::StyleResolveChain *v50; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v51; // [rsp+58h] [rbp-B0h]
  Mso::SVG::LengthResolver *v52; // [rsp+60h] [rbp-A8h]
  struct GEL::IEffect *v53; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v54; // [rsp+70h] [rbp-98h]
  _QWORD v55[3]; // [rsp+78h] [rbp-90h] BYREF
  double v56; // [rsp+90h] [rbp-78h]
  double v57; // [rsp+98h] [rbp-70h]
  __int128 v58; // [rsp+A0h] [rbp-68h] BYREF
  __int128 v59; // [rsp+B0h] [rbp-58h]
  _OWORD v60[3]; // [rsp+C0h] [rbp-48h] BYREF
  _OWORD v61[2]; // [rsp+F0h] [rbp-18h] BYREF
  double v62; // [rsp+110h] [rbp+8h]
  double v63; // [rsp+118h] [rbp+10h]
  __int64 v64; // [rsp+120h] [rbp+18h]
  __int64 v65; // [rsp+128h] [rbp+20h]
  __int64 v66; // [rsp+130h] [rbp+28h]
  __int64 v67; // [rsp+138h] [rbp+30h]
  __int64 v68; // [rsp+140h] [rbp+38h]
  const struct GEL::IEffect *v69; // [rsp+148h] [rbp+40h]
  _BYTE v70[16]; // [rsp+158h] [rbp+50h] BYREF
  Mso::Memory *v71; // [rsp+168h] [rbp+60h]
  char v72; // [rsp+170h] [rbp+68h]
  char v73; // [rsp+191h] [rbp+89h]
  _OWORD v74[7]; // [rsp+198h] [rbp+90h] BYREF

  if ( Mso::SVG::RenderableRenderer::IsRenderingEnabled(this) )
  {
    v8 = (_QWORD *)*((_QWORD *)this + 2);
    if ( !v8 )
    {
      CrashWithRecovery(0x1E3C3843u, 0);
      JUMPOUT(0x1801034D5LL);
    }
    _castguard_slow_path_check_user_handled(*v8, 6392, 0);
    v9 = (*(__int64 (__fastcall **)(_QWORD *))(*v8 + 104LL))(v8);
    v50 = a3;
    v51 = v9;
    v52 = (Mso::SVG::LengthResolver *)*((_QWORD *)a3 + 2);
    if ( *(_BYTE *)Mso::SVG::StyleResolveChain::Get<30>(&v50) )
    {
      v10 = *(_QWORD *)(v51 + 16);
      if ( v10 )
      {
        v11 = (__int16 *)(v10 + 552);
      }
      else
      {
        v11 = &Mso::SVG::StyleMetaData<28>::initial;
        if ( *(_QWORD *)(v51 + 8) )
          v11 = (__int16 *)&Mso::SVG::StyleMetaData<28>::inherit;
      }
      if ( !*((_BYTE *)v11 + 1) )
      {
        if ( v50 )
          v11 = (__int16 *)Mso::SVG::StyleResolveChain::Get<28>();
        else
          v11 = (__int16 *)Mso::SVG::StyleResolveChain::GetNormal<28>(&v50, *(_QWORD *)(v51 + 8));
      }
      if ( *(_BYTE *)v11 )
      {
        v12 = v8[60];
        if ( v12 )
        {
          if ( !(*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)v12 + 96LL))(v8[60]) )
          {
            v58 = 0;
            v59 = 0;
            if ( !a4 )
            {
              v13 = *(_QWORD *)(v51 + 16);
              if ( v13 )
              {
                v14 = (__int64 *)(v13 + 392);
              }
              else if ( !*(_BYTE *)(v51 + 24) || (v14 = Mso::SVG::StyleMetaData<33>::inherit, !*(_QWORD *)(v51 + 8)) )
              {
                v14 = (__int64 *)&Mso::SVG::StyleMetaData<33>::initial;
              }
              if ( !*((_BYTE *)v14 + 32) )
              {
                if ( v50 )
                  v15 = Mso::SVG::StyleResolveChain::Get<33>();
                else
                  v15 = Mso::SVG::StyleResolveChain::GetNormal<33>(&v50, *(_QWORD *)(v51 + 8));
                v14 = (__int64 *)v15;
              }
              if ( v14[2] )
                Mso::SVG::Environment::QueryClipPath(*(_QWORD *)(*((_QWORD *)this + 3) + 64LL));
            }
            v60[0] = `GEL::GetIdentityMatrix'::`2'::s_identityMatrix;
            v60[1] = xmmword_1801820F8;
            v60[2] = xmmword_180182108;
            v16 = (double)(*(int (__fastcall **)(__int64))(*(_QWORD *)v12 + 40LL))(v12);
            v17 = (double)(*(int (__fastcall **)(__int64))(*(_QWORD *)v12 + 48LL))(v12);
            if ( v16 > 0.0 && v17 > 0.0 )
            {
              v18 = *((_BYTE *)this + 112) == 0;
              *((_QWORD *)this + 10) = 0;
              *((_QWORD *)this + 11) = 0;
              *((double *)this + 12) = v16;
              *((double *)this + 13) = v17;
              if ( v18 )
                *((_BYTE *)this + 112) = 1;
            }
            v19 = Mso::SVG::LengthResolver::ResolveLength(
                    v52,
                    (const struct Mso::SVG::Length *)(v8 + 51),
                    (const struct Mso::SVG::StyleResolveChain *)&v50);
            v20 = Mso::SVG::LengthResolver::ResolveLength(
                    v52,
                    (const struct Mso::SVG::Length *)(v8 + 53),
                    (const struct Mso::SVG::StyleResolveChain *)&v50);
            Mso::SVG::ViewboxAdapter::CalculateViewboxTransform((char *)this + 80, v21, v22, v60);
            *(_OWORD *)&v55[1] = 0;
            v56 = v16;
            v57 = v17;
            v23 = (__int64 *)GEL::IRectanglePath::Create(&v49, &v55[1]);
            v54 = *v23;
            v24 = v54;
            *v23 = 0;
            v64 = v24;
            if ( v49 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 8LL))(v49);
            GEL::ImageFillInfo::ImageFillInfo((GEL::ImageFillInfo *)v70);
            v72 = 4;
            v73 = 1;
            v26 = (Mso::Memory *)Mso::Memory::AllocateEx((Mso::Memory *)0x20, 0, v25);
            v28 = v26;
            if ( !v26 )
            {
              ThrowOOM();
              __debugbreak();
            }
            *(_QWORD *)v26 = 0;
            *((_QWORD *)v26 + 1) = 0;
            *((double *)v26 + 2) = v16;
            *((double *)v26 + 3) = v17;
            if ( v71 != v26 )
            {
              if ( v71 )
                Mso::Memory::Free(v71, v27);
              v71 = v28;
            }
            v29 = (__int64 *)GEL::IBrushImage::Create(&v49, v12, v70);
            v30 = *v29;
            *v29 = 0;
            v65 = v30;
            if ( v49 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 8LL))(v49);
            v31 = v54;
            v32 = (__int64 *)GEL::IEffectFilledPath::Create(&v53, v54, v30, 0);
            v33 = *v32;
            *v32 = 0;
            v66 = v33;
            if ( v53 )
              (*(void (__fastcall **)(struct GEL::IEffect *))(*(_QWORD *)v53 + 8LL))(v53);
            v34 = Mso::SVG::LengthResolver::ResolveLength(
                    v52,
                    (const struct Mso::SVG::Length *)(v8 + 49),
                    (const struct Mso::SVG::StyleResolveChain *)&v50);
            v35 = Mso::SVG::LengthResolver::ResolveLength(
                    v52,
                    (const struct Mso::SVG::Length *)(v8 + 47),
                    (const struct Mso::SVG::StyleResolveChain *)&v50);
            v61[0] = _mm_load_si128((const __m128i *)&_xmm);
            v61[1] = _mm_load_si128((const __m128i *)&_xmm);
            v62 = v35;
            v63 = v34;
            Math::operator*=<double,double,0>(v61, (char *)this + 32);
            if ( (unsigned __int8)Math::TAffine3x3<double>::IsIdentity(v60) )
            {
              if ( v33 )
                (**(void (__fastcall ***)(__int64))v33)(v33);
              v37 = v33;
            }
            else
            {
              v38 = (_QWORD *)GEL::IEffectTransform::Create(&v49, v33, v60);
              v37 = *v38;
              if ( *v38 )
                (**(void (__fastcall ***)(_QWORD))v37)(*v38);
              if ( v49 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 8LL))(v49);
            }
            v67 = v37;
            *(_OWORD *)&v55[1] = 0;
            v56 = v19;
            v57 = v20;
            LOBYTE(v36) = 1;
            v39 = (__int64 *)GEL::IEffectClip::Create(&v53, v37, &v55[1], v36);
            v40 = *v39;
            *v39 = 0;
            v68 = v40;
            if ( v53 )
              (*(void (__fastcall **)(struct GEL::IEffect *))(*(_QWORD *)v53 + 8LL))(v53);
            v41 = *(_QWORD *)v40;
            v74[0] = _mm_load_si128((const __m128i *)&_xmm);
            v74[1] = _mm_load_si128((const __m128i *)&_xmm);
            v74[2] = 0;
            (*(void (__fastcall **)(__int64, _OWORD *, __int128 *, _QWORD))(v41 + 48))(v40, v74, &v58, 0);
            Mso::SVG::RenderableRenderer::ApplyFilter((__int64)this, v55, v40, &v50, &v58, (__int64)a5);
            TransformedBounds = (__int128 *)GEL::Rect::GetTransformedBounds(&v58, &v55[1], v60);
            v58 = *TransformedBounds;
            v59 = TransformedBounds[1];
            if ( v55[0] )
            {
              *(_OWORD *)&v55[1] = 0;
              v56 = v19;
              v57 = v20;
              Mso::SVG::RenderableRenderer::ApplyStandardOverflowEffects(
                (_DWORD)this,
                (unsigned int)&v53,
                v55[0],
                (unsigned int)&v50,
                (__int64)&v55[1],
                (__int64)&v58);
              v43 = v53;
              if ( v53 )
              {
                v44 = *(__int64 **)(v51 + 16);
                if ( !v44 )
                {
                  if ( !*(_BYTE *)(v51 + 24) || (v44 = &Mso::SVG::StyleMetaData<47>::inherit, !*(_QWORD *)(v51 + 8)) )
                    v44 = &Mso::SVG::StyleMetaData<47>::initial;
                }
                if ( !*((_BYTE *)v44 + 4) )
                {
                  if ( v50 )
                    v44 = (__int64 *)Mso::SVG::StyleResolveChain::Get<47>();
                  else
                    v44 = (__int64 *)Mso::SVG::StyleResolveChain::GetNormal<47>(&v50, *(_QWORD *)(v51 + 8));
                }
                if ( *(_DWORD *)v44 == 1 )
                {
                  v45 = (const struct GEL::IEffect **)GEL::IEffectNearestNeighborInterpolation::Create(&v49, v43);
                  v46 = *v45;
                  *v45 = 0;
                  v69 = v46;
                  if ( v49 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 8LL))(v49);
                  GEL::EffectAccumulator::Add(a2, v46);
                  if ( v46 )
                    (*(void (__fastcall **)(const struct GEL::IEffect *))(*(_QWORD *)v46 + 8LL))(v46);
                }
                else
                {
                  GEL::EffectAccumulator::Add(a2, v43);
                }
              }
              if ( v43 )
                (*(void (__fastcall **)(struct GEL::IEffect *))(*(_QWORD *)v43 + 8LL))(v43);
              v31 = v54;
            }
            v47 = (__int128 *)GEL::Rect::GetTransformedBounds(&v58, &v55[1], v61);
            v58 = *v47;
            v59 = v47[1];
            Mso::SVG::RenderableRenderer::EndRendering(this, (const struct GEL::Rect *)&v58, a4, 0);
            v48 = v55[0];
            if ( v55[0] )
            {
              v55[0] = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 8LL))(v48);
            }
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 8LL))(v40);
            if ( v37 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 8LL))(v37);
            if ( v33 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 8LL))(v33);
            if ( v30 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 8LL))(v30);
            GEL::ImageFillInfo::~ImageFillInfo((GEL::ImageFillInfo *)v70);
            if ( v31 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 8LL))(v31);
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x180102d70  mov     rax, rsp
0x180102d73  mov     [rax+8], rbx
0x180102d77  mov     [rax+20h], r9
0x180102d7b  mov     [rax+10h], rdx
0x180102d7f  push    rbp
0x180102d80  push    rsi
0x180102d81  push    rdi
0x180102d82  push    r12
0x180102d84  push    r13
0x180102d86  push    r14
0x180102d88  push    r15
0x180102d8a  lea     rbp, [rax-138h]
0x180102d91  sub     rsp, 200h
0x180102d98  movaps  xmmword ptr [rax-48h], xmm6
0x180102d9c  movaps  xmmword ptr [rax-58h], xmm7
0x180102da0  movaps  xmmword ptr [rax-68h], xmm8
0x180102da5  movaps  xmmword ptr [rax-78h], xmm9
0x180102daa  mov     r14, r9
0x180102dad  mov     rbx, r8
0x180102db0  mov     rsi, rcx
0x180102db3  xor     r13d, r13d
0x180102db6  call    ?IsRenderingEnabled@RenderableRenderer@SVG@Mso@@QEBA_NXZ; Mso::SVG::RenderableRenderer::IsRenderingEnabled(void)
0x180102dbb  test    al, al
0x180102dbd  jz      loc_180103499
0x180102dc3  mov     r15, [rsi+10h]
0x180102dc7  test    r15, r15
0x180102dca  jz      loc_1801034C8
0x180102dd0  xor     r8d, r8d
0x180102dd3  mov     edx, 18F8h
0x180102dd8  mov     rcx, [r15]
0x180102ddb  call    __castguard_slow_path_check_user_handled
0x180102de0  mov     rax, [r15]
0x180102de3  mov     rcx, r15
0x180102de6  mov     rax, [rax+68h]
0x180102dea  call    cs:__guard_dispatch_icall_fptr
0x180102df0  mov     [rsp+230h+var_1E8], rbx
0x180102df5  mov     [rsp+230h+var_1E0], rax
0x180102dfa  mov     rax, [rbx+10h]
0x180102dfe  mov     [rsp+230h+var_1D8], rax
0x180102e03  lea     rcx, [rsp+230h+var_1E8]
0x180102e08  call    ??$Get@$0BO@@StyleResolveChain@SVG@Mso@@QEBAAEB_NXZ; Mso::SVG::StyleResolveChain::Get<30>(void)
0x180102e0d  cmp     [rax], r13b
0x180102e10  jz      loc_180103499
0x180102e16  mov     rdx, [rsp+230h+var_1E0]
0x180102e1b  mov     rax, [rdx+10h]
0x180102e1f  test    rax, rax
0x180102e22  jz      short loc_180102E2C
0x180102e24  add     rax, 228h
0x180102e2a  jmp     short loc_180102E42
0x180102e2c  lea     rax, ?initial@?$StyleMetaData@$0BM@@SVG@Mso@@2V?$optional@_N@std@@B; std::optional<bool> const Mso::SVG::StyleMetaData<28>::initial
0x180102e33  lea     rcx, ?inherit@?$StyleMetaData@$0BM@@SVG@Mso@@2V?$optional@_N@std@@B; std::optional<bool> const Mso::SVG::StyleMetaData<28>::inherit
0x180102e3a  cmp     [rdx+8], r13
0x180102e3e  cmovnz  rax, rcx
0x180102e42  cmp     [rax+1], r13b
0x180102e46  jnz     short loc_180102E67
0x180102e48  mov     rcx, [rsp+230h+var_1E8]
0x180102e4d  test    rcx, rcx
0x180102e50  jz      short loc_180102E59
0x180102e52  call    ??$Get@$0BM@@StyleResolveChain@SVG@Mso@@QEBAAEB_NXZ; Mso::SVG::StyleResolveChain::Get<28>(void)
0x180102e57  jmp     short loc_180102E67
0x180102e59  mov     rdx, [rdx+8]
0x180102e5d  lea     rcx, [rsp+230h+var_1E8]
0x180102e62  call    ??$GetNormal@$0BM@@StyleResolveChain@SVG@Mso@@AEBAAEB_NAEBVStyle@12@@Z; Mso::SVG::StyleResolveChain::GetNormal<28>(Mso::SVG::Style const &)
0x180102e67  cmp     [rax], r13b
0x180102e6a  jz      loc_180103499
0x180102e70  mov     rdi, [r15+1E0h]
0x180102e77  test    rdi, rdi
0x180102e7a  jz      loc_180103499
0x180102e80  mov     rax, [rdi]
0x180102e83  mov     rcx, rdi
0x180102e86  mov     rax, [rax+60h]
0x180102e8a  call    cs:__guard_dispatch_icall_fptr
0x180102e90  test    al, al
0x180102e92  jnz     loc_180103499
0x180102e98  xorps   xmm0, xmm0
0x180102e9b  movups  [rbp+130h+var_198], xmm0
0x180102e9f  xorps   xmm1, xmm1
0x180102ea2  movups  [rbp+130h+var_188], xmm1
0x180102ea6  test    r14, r14
0x180102ea9  jnz     short loc_180102F17
0x180102eab  mov     rax, [rsp+230h+var_1E0]
0x180102eb0  mov     rdx, [rax+10h]
0x180102eb4  test    rdx, rdx
0x180102eb7  jz      short loc_180102EC2
0x180102eb9  add     rdx, 188h
0x180102ec0  jmp     short loc_180102EDC
0x180102ec2  cmp     [rax+18h], r13b
0x180102ec6  jz      short loc_180102ED5
0x180102ec8  cmp     [rax+8], r13
0x180102ecc  lea     rdx, ?inherit@?$StyleMetaData@$0CB@@SVG@Mso@@2V?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@B; std::optional<std::wstring> const Mso::SVG::StyleMetaData<33>::inherit
0x180102ed3  jnz     short loc_180102EDC
0x180102ed5  lea     rdx, ?initial@?$StyleMetaData@$0CB@@SVG@Mso@@2V?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@B; std::optional<std::wstring> const Mso::SVG::StyleMetaData<33>::initial
0x180102edc  cmp     [rdx+20h], r13b
0x180102ee0  jnz     short loc_180102F04
0x180102ee2  mov     rcx, [rsp+230h+var_1E8]
0x180102ee7  test    rcx, rcx
0x180102eea  jz      short loc_180102EF3
0x180102eec  call    ??$Get@$0CB@@StyleResolveChain@SVG@Mso@@QEBAAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; Mso::SVG::StyleResolveChain::Get<33>(void)
0x180102ef1  jmp     short loc_180102F01
0x180102ef3  mov     rdx, [rax+8]
0x180102ef7  lea     rcx, [rsp+230h+var_1E8]
0x180102efc  call    ??$GetNormal@$0CB@@StyleResolveChain@SVG@Mso@@AEBAAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBVStyle@12@@Z; Mso::SVG::StyleResolveChain::GetNormal<33>(Mso::SVG::Style const &)
0x180102f01  mov     rdx, rax
0x180102f04  cmp     [rdx+10h], r13
0x180102f08  jz      short loc_180102F17
0x180102f0a  mov     rax, [rsi+18h]
0x180102f0e  mov     rcx, [rax+40h]
0x180102f12  call    ?QueryClipPath@Environment@SVG@Mso@@QEAAPEAVClipPathContext@23@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Mso::SVG::Environment::QueryClipPath(std::wstring const &)
0x180102f17  movups  xmm0, cs:?s_identityMatrix@?1??GetIdentityMatrix@GEL@@YAAEBU?$TAffine3x3@N@Math@@XZ@4U34@B; Math::TAffine3x3<double> const `GEL::GetIdentityMatrix(void)'::`2'::s_identityMatrix
0x180102f1e  movups  [rbp+130h+var_178], xmm0
0x180102f22  movups  xmm1, cs:xmmword_1801820F8
0x180102f29  movups  [rbp+130h+var_168], xmm1
0x180102f2d  movups  xmm0, cs:xmmword_180182108
0x180102f34  movups  [rbp+130h+var_158], xmm0
0x180102f38  mov     rax, [rdi]
0x180102f3b  mov     rcx, rdi
0x180102f3e  mov     rax, [rax+28h]
0x180102f42  call    cs:__guard_dispatch_icall_fptr
0x180102f48  movd    xmm7, eax
0x180102f4c  cvtdq2pd xmm7, xmm7
0x180102f50  mov     rax, [rdi]
0x180102f53  mov     rcx, rdi
0x180102f56  mov     rax, [rax+30h]
0x180102f5a  call    cs:__guard_dispatch_icall_fptr
0x180102f60  movd    xmm6, eax
0x180102f64  cvtdq2pd xmm6, xmm6
0x180102f68  lea     rbx, [rsi+50h]
0x180102f6c  xorps   xmm0, xmm0
0x180102f6f  comisd  xmm7, xmm0
0x180102f73  jbe     short loc_180102F96
0x180102f75  comisd  xmm6, xmm0
0x180102f79  jbe     short loc_180102F96
0x180102f7b  cmp     [rbx+20h], r13b
0x180102f7f  mov     [rbx], r13
0x180102f82  mov     [rsi+58h], r13
0x180102f86  movsd   qword ptr [rsi+60h], xmm7
0x180102f8b  movsd   qword ptr [rsi+68h], xmm6
0x180102f90  jnz     short loc_180102F96
0x180102f92  mov     byte ptr [rbx+20h], 1
0x180102f96  lea     rdx, [r15+198h]; struct Mso::SVG::Length *
0x180102f9d  lea     r8, [rsp+230h+var_1E8]; struct Mso::SVG::StyleResolveChain *
0x180102fa2  mov     rcx, [rsp+230h+var_1D8]; this
0x180102fa7  call    ?ResolveLength@LengthResolver@SVG@Mso@@AEBANAEBULength@23@AEBVStyleResolveChain@23@@Z; Mso::SVG::LengthResolver::ResolveLength(Mso::SVG::Length const &,Mso::SVG::StyleResolveChain const &)
0x180102fac  movaps  xmm8, xmm0
0x180102fb0  lea     rdx, [r15+1A8h]; struct Mso::SVG::Length *
0x180102fb7  lea     r8, [rsp+230h+var_1E8]; struct Mso::SVG::StyleResolveChain *
0x180102fbc  mov     rcx, [rsp+230h+var_1D8]; this
0x180102fc1  call    ?ResolveLength@LengthResolver@SVG@Mso@@AEBANAEBULength@23@AEBVStyleResolveChain@23@@Z; Mso::SVG::LengthResolver::ResolveLength(Mso::SVG::Length const &,Mso::SVG::StyleResolveChain const &)
0x180102fc6  movaps  xmm9, xmm0
0x180102fca  lea     r9, [rbp+130h+var_178]
0x180102fce  movaps  xmm2, xmm0
0x180102fd1  movaps  xmm1, xmm8
0x180102fd5  mov     rcx, rbx
0x180102fd8  call    ?CalculateViewboxTransform@ViewboxAdapter@SVG@Mso@@QEBAXNNAEAU?$TAffine3x3@N@Math@@@Z; Mso::SVG::ViewboxAdapter::CalculateViewboxTransform(double,double,Math::TAffine3x3<double> &)
0x180102fdd  xorps   xmm1, xmm1
0x180102fe0  movups  xmmword ptr [rsp+230h+var_1C0+8], xmm1
0x180102fe5  movsd   [rbp+130h+var_1A8], xmm7
0x180102fea  movsd   [rbp+130h+var_1A0], xmm6
0x180102fef  lea     rdx, [rsp+230h+var_1C0+8]
0x180102ff4  lea     rcx, [rsp+230h+var_1F0]
0x180102ff9  call    cs:__imp_?Create@IRectanglePath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@AEBU?$TRect@N@Math@@@Z; GEL::IRectanglePath::Create(Math::TRect<double> const &)
0x180102fff  mov     rcx, [rax]
0x180103002  mov     [rsp+230h+var_1C8], rcx
0x180103007  mov     [rax], r13
0x18010300a  mov     [rbp+130h+var_118], rcx
0x18010300e  mov     rcx, [rsp+230h+var_1F0]
0x180103013  test    rcx, rcx
0x180103016  jz      short loc_180103025
0x180103018  mov     rax, [rcx]
0x18010301b  mov     rax, [rax+8]
0x18010301f  call    cs:__guard_dispatch_icall_fptr
0x180103025  lea     rcx, [rbp+130h+var_E0]
0x180103029  call    cs:__imp_??0ImageFillInfo@GEL@@QEAA@XZ; GEL::ImageFillInfo::ImageFillInfo(void)
0x18010302f  mov     [rbp+130h+var_C8], 4
0x180103033  mov     [rbp+130h+var_A7], 1
0x18010303a  xor     edx, edx
0x18010303c  lea     ecx, [rdx+20h]
0x18010303f  call    cs:__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::AllocateEx(unsigned __int64,ulong)
0x180103045  mov     rbx, rax
0x180103048  test    rax, rax
0x18010304b  jnz     short loc_180103054
0x18010304d  call    cs:__imp_?ThrowOOM@@YAXXZ; ThrowOOM(void)
0x180103053  int     3; Trap to Debugger
0x180103054  mov     [rax], r13
0x180103057  mov     [rax+8], r13
0x18010305b  movsd   qword ptr [rax+10h], xmm7
0x180103060  movsd   qword ptr [rax+18h], xmm6
0x180103065  mov     rcx, [rbp+130h+var_D0]
0x180103069  cmp     rcx, rbx
0x18010306c  jz      short loc_18010307D
0x18010306e  test    rcx, rcx
0x180103071  jz      short loc_180103079
0x180103073  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x180103079  mov     [rbp+130h+var_D0], rbx
0x18010307d  lea     r8, [rbp+130h+var_E0]
0x180103081  mov     rdx, rdi
0x180103084  lea     rcx, [rsp+230h+var_1F0]
0x180103089  call    cs:__imp_?Create@IBrushImage@GEL@@SA?AV?$TCntPtr@UIBrushImage@GEL@@@Ofc@@AEBUIImage@2@AEBUImageFillInfo@2@@Z; GEL::IBrushImage::Create(GEL::IImage const &,GEL::ImageFillInfo const &)
0x18010308f  mov     r12, [rax]
0x180103092  mov     [rax], r13
0x180103095  mov     [rbp+130h+var_110], r12
0x180103099  mov     rcx, [rsp+230h+var_1F0]
0x18010309e  test    rcx, rcx
0x1801030a1  jz      short loc_1801030B0
0x1801030a3  mov     rax, [rcx]
0x1801030a6  mov     rax, [rax+8]
0x1801030aa  call    cs:__guard_dispatch_icall_fptr
0x1801030b0  xor     r9d, r9d
0x1801030b3  mov     r8, r12
0x1801030b6  mov     rdi, [rsp+230h+var_1C8]
0x1801030bb  mov     rdx, rdi
0x1801030be  lea     rcx, [rsp+230h+var_1D0]
0x1801030c3  call    cs:__imp_?Create@IEffectFilledPath@GEL@@SA?AV?$TCntPtr@UIEffectFilledPath@GEL@@@Ofc@@AEBUIPath@2@AEBUIBrush@2@PEBU?$TAffine3x3@N@Math@@@Z; GEL::IEffectFilledPath::Create(GEL::IPath const &,GEL::IBrush const &,Math::TAffine3x3<double> const *)
0x1801030c9  mov     r14, [rax]
0x1801030cc  mov     [rax], r13
0x1801030cf  mov     [rbp+130h+var_108], r14
0x1801030d3  mov     rcx, [rsp+230h+var_1D0]
0x1801030d8  test    rcx, rcx
0x1801030db  jz      short loc_1801030EA
0x1801030dd  mov     rax, [rcx]
0x1801030e0  mov     rax, [rax+8]
0x1801030e4  call    cs:__guard_dispatch_icall_fptr
0x1801030ea  lea     rdx, [r15+188h]; struct Mso::SVG::Length *
0x1801030f1  lea     r8, [rsp+230h+var_1E8]; struct Mso::SVG::StyleResolveChain *
0x1801030f6  mov     rcx, [rsp+230h+var_1D8]; this
0x1801030fb  call    ?ResolveLength@LengthResolver@SVG@Mso@@AEBANAEBULength@23@AEBVStyleResolveChain@23@@Z; Mso::SVG::LengthResolver::ResolveLength(Mso::SVG::Length const &,Mso::SVG::StyleResolveChain const &)
0x180103100  movaps  xmm6, xmm0
0x180103103  lea     rdx, [r15+178h]; struct Mso::SVG::Length *
0x18010310a  lea     r8, [rsp+230h+var_1E8]; struct Mso::SVG::StyleResolveChain *
0x18010310f  mov     rcx, [rsp+230h+var_1D8]; this
0x180103114  call    ?ResolveLength@LengthResolver@SVG@Mso@@AEBANAEBULength@23@AEBVStyleResolveChain@23@@Z; Mso::SVG::LengthResolver::ResolveLength(Mso::SVG::Length const &,Mso::SVG::StyleResolveChain const &)
0x180103119  movdqa  xmm1, cs:__xmm@00000000000000003ff0000000000000
0x180103121  movups  [rbp+130h+var_148], xmm1
0x180103125  movdqa  xmm2, cs:__xmm@3ff00000000000000000000000000000
0x18010312d  movups  [rbp+130h+var_138], xmm2
0x180103131  movsd   [rbp+130h+var_128], xmm0
0x180103136  movsd   [rbp+130h+var_120], xmm6
0x18010313b  lea     rdx, [rsi+20h]
0x18010313f  lea     rcx, [rbp+130h+var_148]
0x180103143  call    ??$?XNN$0A@@Math@@YAAEAU?$TAffine3x3@N@0@AEAU10@AEBU10@@Z; Math::operator*=<double,double,0>(Math::TAffine3x3<double> &,Math::TAffine3x3<double> const &)
0x180103148  movsd   xmm1, cs:__real@3cd203afa0000000
0x180103150  lea     rcx, [rbp+130h+var_178]
0x180103154  call    ?IsIdentity@?$TAffine3x3@N@Math@@QEBA_NN@Z; Math::TAffine3x3<double>::IsIdentity(double)
0x180103159  test    al, al
0x18010315b  jz      short loc_180103176
0x18010315d  test    r14, r14
0x180103160  jz      short loc_180103171
0x180103162  mov     rax, [r14]
0x180103165  mov     rcx, r14
0x180103168  mov     rax, [rax]
0x18010316b  call    cs:__guard_dispatch_icall_fptr
0x180103171  mov     rbx, r14
0x180103174  jmp     short loc_1801031B6
0x180103176  lea     r8, [rbp+130h+var_178]
0x18010317a  mov     rdx, r14
0x18010317d  lea     rcx, [rsp+230h+var_1F0]
0x180103182  call    cs:__imp_?Create@IEffectTransform@GEL@@SA?AV?$TCntPtr@UIEffectTransform@GEL@@@Ofc@@AEBUIEffect@2@AEBU?$TAffine3x3@N@Math@@@Z; GEL::IEffectTransform::Create(GEL::IEffect const &,Math::TAffine3x3<double> const &)
0x180103188  mov     rbx, [rax]
0x18010318b  test    rbx, rbx
0x18010318e  jz      short loc_18010319F
0x180103190  mov     rax, [rbx]
0x180103193  mov     rcx, rbx
0x180103196  mov     rax, [rax]
0x180103199  call    cs:__guard_dispatch_icall_fptr
0x18010319f  mov     rcx, [rsp+230h+var_1F0]
0x1801031a4  test    rcx, rcx
0x1801031a7  jz      short loc_1801031B6
0x1801031a9  mov     rax, [rcx]
0x1801031ac  mov     rax, [rax+8]
0x1801031b0  call    cs:__guard_dispatch_icall_fptr
0x1801031b6  mov     [rbp+130h+var_100], rbx
0x1801031ba  xorps   xmm0, xmm0
0x1801031bd  movups  xmmword ptr [rsp+230h+var_1C0+8], xmm0
0x1801031c2  movsd   [rbp+130h+var_1A8], xmm8
0x1801031c8  movsd   [rbp+130h+var_1A0], xmm9
0x1801031ce  mov     r9b, 1
0x1801031d1  lea     r8, [rsp+230h+var_1C0+8]
0x1801031d6  mov     rdx, rbx
0x1801031d9  lea     rcx, [rsp+230h+var_1D0]
0x1801031de  call    cs:__imp_?Create@IEffectClip@GEL@@SA?AV?$TCntPtr@UIEffectClip@GEL@@@Ofc@@AEBUIEffect@2@AEBU?$TRect@N@Math@@W4CombineMode@2@@Z; GEL::IEffectClip::Create(GEL::IEffect const &,Math::TRect<double> const &,GEL::CombineMode)
0x1801031e4  mov     r13, [rax]
0x1801031e7  mov     qword ptr [rax], 0
0x1801031ee  mov     [rbp+130h+var_F8], r13
0x1801031f2  mov     rcx, [rsp+230h+var_1D0]
0x1801031f7  test    rcx, rcx
0x1801031fa  jz      short loc_180103209
0x1801031fc  mov     rax, [rcx]
0x1801031ff  mov     rax, [rax+8]
0x180103203  call    cs:__guard_dispatch_icall_fptr
0x180103209  mov     rax, [r13+0]
0x18010320d  movdqa  xmm0, cs:__xmm@00000000000000003ff0000000000000
0x180103215  movups  [rbp+130h+var_A0], xmm0
0x18010321c  movdqa  xmm1, cs:__xmm@3ff00000000000000000000000000000
0x180103224  movups  [rbp+130h+var_90], xmm1
0x18010322b  xorps   xmm0, xmm0
0x18010322e  movups  [rbp+130h+var_80], xmm0
0x180103235  xor     r9d, r9d
0x180103238  lea     r8, [rbp+130h+var_198]
0x18010323c  lea     rdx, [rbp+130h+var_A0]
0x180103243  mov     rcx, r13
  ... truncated ...
```
