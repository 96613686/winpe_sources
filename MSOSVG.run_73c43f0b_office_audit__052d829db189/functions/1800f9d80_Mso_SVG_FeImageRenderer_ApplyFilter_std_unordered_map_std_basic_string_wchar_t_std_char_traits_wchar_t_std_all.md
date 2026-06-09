# Mso::SVG::FeImageRenderer::ApplyFilter(std::unordered_map<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,Ofc::TCntPtr<GEL::IEffect const>,std::hash<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>,std::equal_to<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,Ofc::TCntPtr<GEL::IEffect const>>>> const &,GEL::IEffect const &,GEL::IEffect const &,Mso::SVG::StyleResolveChain const &,GEL::Rect const &,Mso::SVG::PrimitiveUnitResolver const &,GEL::IColorResolver const *)

- ea: `0x1800f9d80`
- end: `0x1800fa337`
- name: `?ApplyFilter@FeImageRenderer@SVG@Mso@@UEBA?AV?$TCntPtr@$$CBUIEffect@GEL@@@Ofc@@AEBV?$unordered_map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$TCntPtr@$$CBUIEffect@GEL@@@Ofc@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$TCntPtr@$$CBUIEffect@GEL@@@Ofc@@@std@@@2@@std@@AEBUIEffect@GEL@@1AEBVStyleResolveChain@23@AEBURect@9@AEBVPrimitiveUnitResolver@23@PEBUIColorResolver@9@@Z`
- size: `1463`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x18000d67c`
- `0x18003fd34`
- `0x1800435fc`
- `0x18004c058`
- `0x18004e760`
- `0x1800f5db0`
- `0x1800f9d80`
- `0x18013e0c0`
- `0x18013f810`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800fa2f8`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800fa306`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800fa314`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800fa322`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800fa330`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800fa2f8`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800fa306`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800fa314`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800fa322`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800fa330`
- `gfx!?Create@IEffectContainer@GEL@@SA?AV?$TCntPtr@UIEffectContainer@GEL@@@Ofc@@XZ` at `0x1800fa2a3`
- `gfx!?Create@IEffectContainer@GEL@@SA?AV?$TCntPtr@UIEffectContainer@GEL@@@Ofc@@XZ` at `0x1800fa2a3`
- `gfx!?Create@IEffectImage@GEL@@SA?AV?$TCntPtr@UIEffectImage@GEL@@@Ofc@@AEBUIImage@2@AEBU?$TRect@N@Math@@AEBU?$TRect@V?$TUnits@NUDevicePixels@Math@@@Math@@@7@@Z` at `0x1800fa06f`
- `gfx!?Create@IEffectImage@GEL@@SA?AV?$TCntPtr@UIEffectImage@GEL@@@Ofc@@AEBUIImage@2@AEBU?$TRect@N@Math@@AEBU?$TRect@V?$TUnits@NUDevicePixels@Math@@@Math@@@7@@Z` at `0x1800fa06f`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
_QWORD *__fastcall Mso::SVG::FeImageRenderer::ApplyFilter(
        __int64 a1,
        _QWORD *a2,
        __int64 a3,
        __int64 a4,
        int a5,
        double a6,
        __m128d *a7,
        int a8,
        __int64 a9)
{
  _QWORD *v11; // rbx
  __int64 v12; // rdi
  __int64 v13; // rax
  __m128d v14; // xmm7
  __m128d v15; // xmm5
  double v16; // xmm4_8
  double v17; // xmm0_8
  int v18; // ecx
  double v19; // xmm6_8
  double v20; // xmm2_8
  double v21; // xmm3_8
  double v22; // xmm1_8
  double v23; // xmm2_8
  int v24; // ecx
  int v25; // ecx
  int v26; // ecx
  int v27; // ecx
  int v28; // ecx
  int v29; // ecx
  int v30; // ecx
  int v31; // ecx
  double v32; // xmm2_8
  double v33; // xmm3_8
  int v34; // ecx
  int v35; // ecx
  int v36; // ecx
  int v37; // ecx
  int v38; // ecx
  int v39; // ecx
  int v40; // ecx
  int v41; // ecx
  double v42; // xmm3_8
  double v43; // xmm0_8
  int v44; // ecx
  int v45; // ecx
  int v46; // ecx
  int v47; // ecx
  int v48; // ecx
  int v49; // ecx
  int v50; // ecx
  int v51; // ecx
  double v52; // xmm0_8
  double v53; // xmm1_8
  int v54; // ecx
  int v55; // ecx
  int v56; // ecx
  int v57; // ecx
  int v58; // ecx
  int v59; // ecx
  int v60; // ecx
  int v61; // ecx
  __int64 *v62; // rax
  __int64 Renderable; // rax
  _QWORD *v64; // rax
  _QWORD *v65; // rdi
  _QWORD *v66; // rcx
  __int64 v67; // rax
  __int64 v68; // rax
  _QWORD *v69; // rcx
  __m128d *v70; // rbx
  __m128d v71; // xmm2
  _QWORD *EffectOrEmptyContainer; // rax
  void (__fastcall ****v73)(_QWORD); // rax
  void (__fastcall ***v74)(_QWORD); // rcx
  _QWORD *v75; // rcx
  __int64 v76; // rcx
  __int128 v78; // [rsp+38h] [rbp-A1h] BYREF
  __m128d v79; // [rsp+48h] [rbp-91h] BYREF
  __m128d v80; // [rsp+58h] [rbp-81h]
  __m128d v81; // [rsp+68h] [rbp-71h] BYREF
  __m128d v82; // [rsp+78h] [rbp-61h]
  _QWORD *v83; // [rsp+90h] [rbp-49h]
  __int64 v84; // [rsp+98h] [rbp-41h] BYREF
  _OWORD v85[5]; // [rsp+A0h] [rbp-39h] BYREF
  _QWORD *v86; // [rsp+118h] [rbp+3Fh] BYREF

  v11 = *(_QWORD **)(a1 + 16);
  if ( !v11 )
    goto LABEL_93;
  _castguard_slow_path_check_user_handled(*v11, 9176, 2760);
  _castguard_slow_path_check_user_handled(*v11, 9360, 0);
  v12 = v11[62];
  if ( v12 )
  {
    v13 = *(_QWORD *)(*(__int64 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)v12 + 56LL))(v11[62], &v78);
    v14 = *a7;
    v79 = *a7;
    v15 = a7[1];
    v80 = v15;
    v81 = 0;
    v16 = (double)(int)v13;
    v82.m128d_f64[0] = (double)(int)v13;
    v17 = (double)SHIDWORD(v13);
    v82.m128d_f64[1] = (double)SHIDWORD(v13);
    v18 = *((_DWORD *)v11 + 122);
    if ( !v18 )
    {
LABEL_60:
      v62 = (__int64 *)GEL::IEffectImage::Create(&v86, v12, &v79, &v81);
      goto LABEL_88;
    }
    v19 = v17 / v16;
    v20 = a7[1].m128d_f64[0] - a7->m128d_f64[0];
    v21 = a7[1].m128d_f64[1] - a7->m128d_f64[1];
    v22 = v21 / v20;
    if ( !*((_DWORD *)v11 + 123) )
    {
      if ( v22 > v19 )
      {
        v23 = v20 * v19;
        v24 = v18 - 1;
        if ( !v24 )
          goto LABEL_20;
        v25 = v24 - 1;
        if ( v25 )
        {
          v26 = v25 - 1;
          if ( !v26 )
            goto LABEL_17;
          v27 = v26 - 1;
          if ( !v27 )
            goto LABEL_20;
          v28 = v27 - 1;
          if ( v28 )
          {
            v29 = v28 - 1;
            if ( v29 )
            {
              v30 = v29 - 1;
              if ( v30 )
              {
                v31 = v30 - 1;
                if ( v31 )
                {
                  if ( v31 == 1 )
                    goto LABEL_17;
LABEL_94:
                  CrashWithRecovery(0x21D7560u, 0);
                  __debugbreak();
                }
                goto LABEL_18;
              }
LABEL_20:
              v32 = v23 + _mm_unpackhi_pd(v14, v14).m128d_f64[0];
              goto LABEL_19;
            }
LABEL_17:
            v79.m128d_f64[1] = _mm_unpackhi_pd(v15, v15).m128d_f64[0] - v23;
            goto LABEL_60;
          }
        }
LABEL_18:
        v79.m128d_f64[1] = (v80.m128d_f64[1] + v79.m128d_f64[1] - v23) * 0.5;
        v32 = v23 + v79.m128d_f64[1];
LABEL_19:
        v80.m128d_f64[1] = v32;
        goto LABEL_60;
      }
      v33 = v21 / v19;
      v34 = v18 - 1;
      if ( !v34 )
        goto LABEL_32;
      v35 = v34 - 1;
      if ( v35 )
      {
        v36 = v35 - 1;
        if ( !v36 )
          goto LABEL_30;
        v37 = v36 - 1;
        if ( !v37 )
          goto LABEL_32;
        v38 = v37 - 1;
        if ( v38 )
        {
          v39 = v38 - 1;
          if ( v39 )
          {
            v40 = v39 - 1;
            if ( v40 )
            {
              v41 = v40 - 1;
              if ( v41 )
              {
                if ( v41 != 1 )
                {
                  CrashWithRecovery(0x21D7561u, 0);
                  __debugbreak();
                }
                goto LABEL_30;
              }
              goto LABEL_31;
            }
LABEL_32:
            v42 = v33 + v14.m128d_f64[0];
            goto LABEL_33;
          }
LABEL_30:
          v79.m128d_f64[0] = v15.m128d_f64[0] - v33;
          goto LABEL_60;
        }
      }
LABEL_31:
      v79.m128d_f64[0] = (v80.m128d_f64[0] + v79.m128d_f64[0] - v33) * 0.5;
      v42 = v33 + v79.m128d_f64[0];
LABEL_33:
      v80.m128d_f64[0] = v42;
      goto LABEL_60;
    }
    if ( v22 > v19 )
    {
      v43 = v17 / v22;
      v44 = v18 - 1;
      if ( !v44 )
        goto LABEL_46;
      v45 = v44 - 1;
      if ( v45 )
      {
        v46 = v45 - 1;
        if ( !v46 )
          goto LABEL_44;
        v47 = v46 - 1;
        if ( !v47 )
          goto LABEL_46;
        v48 = v47 - 1;
        if ( v48 )
        {
          v49 = v48 - 1;
          if ( v49 )
          {
            v50 = v49 - 1;
            if ( v50 )
            {
              v51 = v50 - 1;
              if ( v51 )
              {
                if ( v51 != 1 )
                {
                  CrashWithRecovery(0x21D7562u, 0);
                  JUMPOUT(0x1800FA336LL);
                }
                goto LABEL_44;
              }
              goto LABEL_45;
            }
LABEL_46:
            v52 = v43 + 0.0;
            goto LABEL_47;
          }
LABEL_44:
          v81.m128d_f64[0] = v16 - v43;
          goto LABEL_60;
        }
      }
LABEL_45:
      v81.m128d_f64[0] = (v16 + 0.0 - v43) * 0.5;
      v52 = v43 + v81.m128d_f64[0];
LABEL_47:
      v82.m128d_f64[0] = v52;
      goto LABEL_60;
    }
    v53 = v22 * v16;
    v54 = v18 - 1;
    if ( v54 )
    {
      v55 = v54 - 1;
      if ( !v55 )
        goto LABEL_58;
      v56 = v55 - 1;
      if ( !v56 )
        goto LABEL_57;
      v57 = v56 - 1;
      if ( !v57 )
        goto LABEL_59;
      v58 = v57 - 1;
      if ( !v58 )
        goto LABEL_58;
      v59 = v58 - 1;
      if ( !v59 )
      {
LABEL_57:
        v81.m128d_f64[1] = v17 - v53;
        goto LABEL_60;
      }
      v60 = v59 - 1;
      if ( v60 )
      {
        v61 = v60 - 1;
        if ( v61 )
        {
          if ( v61 == 1 )
            goto LABEL_57;
          CrashWithRecovery(0x21D7563u, 0);
LABEL_93:
          CrashWithRecovery(0x1E3C3843u, 0);
          goto LABEL_94;
        }
LABEL_58:
        v81.m128d_f64[1] = (v17 + 0.0 - v53) * 0.5;
        v82.m128d_f64[1] = v81.m128d_f64[1] + v53;
        goto LABEL_60;
      }
    }
LABEL_59:
    v82.m128d_f64[1] = v53 + 0.0;
    goto LABEL_60;
  }
  if ( !*((_BYTE *)v11 + 504) )
  {
    v62 = (__int64 *)GEL::IEffectContainer::Create(&v86);
LABEL_88:
    v76 = *v62;
    *v62 = 0;
    *a2 = v76;
    v69 = v86;
    if ( v86 )
    {
      v68 = *v86;
      goto LABEL_90;
    }
    return a2;
  }
  v83 = 0;
  v78 = 0;
  if ( v11[66]
    && (Renderable = Mso::SVG::Environment::QueryRenderable(*(_QWORD *)(*(_QWORD *)(a1 + 24) + 64LL), v11 + 64)) != 0 )
  {
    v64 = (_QWORD *)Mso::SVG::RenderableRenderer::Create(&v86, Renderable, *(_QWORD *)(a1 + 24));
    v65 = (_QWORD *)*v64;
    *v64 = 0;
    v83 = v65;
    v66 = v86;
    if ( v86 )
    {
      v86 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v66 + 8LL))(v66);
    }
    v67 = (*(__int64 (__fastcall **)(_QWORD *))(*v11 + 104LL))(v11);
    v79.m128d_f64[0] = a6;
    *(_QWORD *)&v79.m128d_f64[1] = v67;
    v80.m128d_f64[0] = *(double *)(*(_QWORD *)&a6 + 16LL);
    if ( *(_BYTE *)Mso::SVG::StyleResolveChain::Get<30>(&v79) )
    {
      v70 = a7;
      v81 = *a7;
      v82 = a7[1];
      if ( v65 )
      {
        Mso::SVG::EnvironmentRenderer::BeginRecursion(*(Mso::SVG::EnvironmentRenderer **)(a1 + 24));
        (*(void (__fastcall **)(_QWORD *, __int128 *, __m128d *, __m128d *, __int64))(*v65 + 32LL))(
          v65,
          &v78,
          &v79,
          &v81,
          a9);
        --**(_DWORD **)(a1 + 24);
      }
      v71 = *v70;
      v85[0] = _mm_load_si128((const __m128i *)&_xmm);
      v85[1] = _mm_load_si128((const __m128i *)&_xmm);
      v85[2] = v71;
      EffectOrEmptyContainer = (_QWORD *)GEL::EffectAccumulator::GetEffectOrEmptyContainer(&v78, &v84);
      v73 = (void (__fastcall ****)(_QWORD))Mso::SVG::ApplyTransform(&v86, *EffectOrEmptyContainer, v85);
      v74 = *v73;
      *a2 = *v73;
      if ( v74 )
        (**v74)(v74);
      v75 = v86;
      if ( v86 )
      {
        v86 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v75 + 8LL))(v75);
      }
      if ( v84 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v84 + 8LL))(v84);
    }
    else
    {
      GEL::EffectAccumulator::GetEffectOrEmptyContainer(&v78, a2);
    }
    if ( *((_QWORD *)&v78 + 1) )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v78 + 1) + 8LL))(*((_QWORD *)&v78 + 1));
    if ( (_QWORD)v78 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v78 + 8LL))(v78);
    if ( v65 )
    {
      v68 = *v65;
      v69 = v65;
LABEL_90:
      (*(void (__fastcall **)(_QWORD *))(v68 + 8))(v69);
    }
  }
  else
  {
    GEL::EffectAccumulator::GetEffectOrEmptyContainer(&v78, a2);
    if ( *((_QWORD *)&v78 + 1) )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v78 + 1) + 8LL))(*((_QWORD *)&v78 + 1));
    if ( (_QWORD)v78 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v78 + 8LL))(v78);
  }
  return a2;
}

```

## disassembly

```asm
0x1800f9d80  mov     rax, rsp
0x1800f9d83  mov     [rax+10h], rbx
0x1800f9d87  mov     [rax+18h], rsi
0x1800f9d8b  push    rbp
0x1800f9d8c  push    rdi
0x1800f9d8d  push    r14
0x1800f9d8f  lea     rbp, [rax-37h]
0x1800f9d93  sub     rsp, 0F0h
0x1800f9d9a  movaps  xmmword ptr [rax-28h], xmm6
0x1800f9d9e  movaps  xmmword ptr [rax-38h], xmm7
0x1800f9da2  mov     rsi, rdx
0x1800f9da5  mov     r14, rcx
0x1800f9da8  mov     rbx, [rcx+10h]
0x1800f9dac  test    rbx, rbx
0x1800f9daf  jz      loc_1800FA2FF
0x1800f9db5  mov     edx, 23D8h
0x1800f9dba  mov     r8d, 0AC8h
0x1800f9dc0  mov     rcx, [rbx]
0x1800f9dc3  call    __castguard_slow_path_check_user_handled
0x1800f9dc8  test    rbx, rbx
0x1800f9dcb  jz      short loc_1800F9DDD
0x1800f9dcd  xor     r8d, r8d
0x1800f9dd0  mov     edx, 2490h
0x1800f9dd5  mov     rcx, [rbx]
0x1800f9dd8  call    __castguard_slow_path_check_user_handled
0x1800f9ddd  mov     rdi, [rbx+1F0h]
0x1800f9de4  test    rdi, rdi
0x1800f9de7  jz      loc_1800FA07A
0x1800f9ded  mov     rax, [rdi]
0x1800f9df0  lea     rdx, [rsp+100h+var_D8+8]
0x1800f9df5  mov     rcx, rdi
0x1800f9df8  mov     rax, [rax+38h]
0x1800f9dfc  call    cs:__guard_dispatch_icall_fptr
0x1800f9e02  mov     rax, [rax]
0x1800f9e05  mov     rdx, [rbp+2Fh+arg_30]
0x1800f9e09  movups  xmm7, xmmword ptr [rdx]
0x1800f9e0c  movups  [rsp+100h+var_C8+8], xmm7
0x1800f9e11  movups  xmm5, xmmword ptr [rdx+10h]
0x1800f9e15  movups  [rsp+100h+var_B8+8], xmm5
0x1800f9e1a  xorps   xmm0, xmm0
0x1800f9e1d  movups  [rbp+2Fh+var_A0], xmm0
0x1800f9e21  mov     ecx, eax
0x1800f9e23  xorps   xmm4, xmm4
0x1800f9e26  cvtsi2sd xmm4, rcx
0x1800f9e2b  movsd   qword ptr [rbp+2Fh+var_90], xmm4
0x1800f9e30  shr     rax, 20h
0x1800f9e34  xorps   xmm0, xmm0
0x1800f9e37  cvtsi2sd xmm0, rax
0x1800f9e3c  movsd   qword ptr [rbp+2Fh+var_90+8], xmm0
0x1800f9e41  mov     ecx, [rbx+1E8h]
0x1800f9e47  test    ecx, ecx
0x1800f9e49  jz      loc_1800FA05F
0x1800f9e4f  movaps  xmm6, xmm0
0x1800f9e52  divsd   xmm6, xmm4
0x1800f9e56  movsd   xmm2, qword ptr [rdx+10h]
0x1800f9e5b  subsd   xmm2, qword ptr [rdx]
0x1800f9e5f  movsd   xmm3, qword ptr [rdx+18h]
0x1800f9e64  subsd   xmm3, qword ptr [rdx+8]
0x1800f9e69  movaps  xmm1, xmm3
0x1800f9e6c  divsd   xmm1, xmm2
0x1800f9e70  cmp     dword ptr [rbx+1ECh], 0
0x1800f9e77  jnz     loc_1800F9F77
0x1800f9e7d  comisd  xmm1, xmm6
0x1800f9e81  jbe     short loc_1800F9F00
0x1800f9e83  mulsd   xmm2, xmm6
0x1800f9e87  sub     ecx, 1
0x1800f9e8a  jz      short loc_1800F9EF6
0x1800f9e8c  sub     ecx, 1
0x1800f9e8f  jz      short loc_1800F9ECB
0x1800f9e91  sub     ecx, 1
0x1800f9e94  jz      short loc_1800F9EB8
0x1800f9e96  sub     ecx, 1
0x1800f9e99  jz      short loc_1800F9EF6
0x1800f9e9b  sub     ecx, 1
0x1800f9e9e  jz      short loc_1800F9ECB
0x1800f9ea0  sub     ecx, 1
0x1800f9ea3  jz      short loc_1800F9EB8
0x1800f9ea5  sub     ecx, 1
0x1800f9ea8  jz      short loc_1800F9EF6
0x1800f9eaa  sub     ecx, 1
0x1800f9ead  jz      short loc_1800F9ECB
0x1800f9eaf  cmp     ecx, 1
0x1800f9eb2  jnz     loc_1800FA30D
0x1800f9eb8  unpckhpd xmm5, xmm5
0x1800f9ebc  subsd   xmm5, xmm2
0x1800f9ec0  movsd   qword ptr [rsp+100h+var_B8], xmm5
0x1800f9ec6  jmp     loc_1800FA05F
0x1800f9ecb  movsd   xmm0, [rbp+2Fh+var_A8]
0x1800f9ed0  addsd   xmm0, qword ptr [rsp+100h+var_B8]
0x1800f9ed6  subsd   xmm0, xmm2
0x1800f9eda  mulsd   xmm0, cs:__real@3fe0000000000000
0x1800f9ee2  movsd   qword ptr [rsp+100h+var_B8], xmm0
0x1800f9ee8  addsd   xmm2, xmm0
0x1800f9eec  movsd   [rbp+2Fh+var_A8], xmm2
0x1800f9ef1  jmp     loc_1800FA05F
0x1800f9ef6  unpckhpd xmm7, xmm7
0x1800f9efa  addsd   xmm2, xmm7
0x1800f9efe  jmp     short loc_1800F9EEC
0x1800f9f00  divsd   xmm3, xmm6
0x1800f9f04  sub     ecx, 1
0x1800f9f07  jz      short loc_1800F9F68
0x1800f9f09  sub     ecx, 1
0x1800f9f0c  jz      short loc_1800F9F44
0x1800f9f0e  sub     ecx, 1
0x1800f9f11  jz      short loc_1800F9F35
0x1800f9f13  sub     ecx, 1
0x1800f9f16  jz      short loc_1800F9F68
0x1800f9f18  sub     ecx, 1
0x1800f9f1b  jz      short loc_1800F9F44
0x1800f9f1d  sub     ecx, 1
0x1800f9f20  jz      short loc_1800F9F35
0x1800f9f22  sub     ecx, 1
0x1800f9f25  jz      short loc_1800F9F68
0x1800f9f27  sub     ecx, 1
0x1800f9f2a  jz      short loc_1800F9F44
0x1800f9f2c  cmp     ecx, 1
0x1800f9f2f  jnz     loc_1800FA31B
0x1800f9f35  subsd   xmm5, xmm3
0x1800f9f39  movsd   qword ptr [rsp+100h+var_C8+8], xmm5
0x1800f9f3f  jmp     loc_1800FA05F
0x1800f9f44  movsd   xmm0, qword ptr [rsp+100h+var_B8+8]
0x1800f9f4a  addsd   xmm0, qword ptr [rsp+100h+var_C8+8]
0x1800f9f50  subsd   xmm0, xmm3
0x1800f9f54  mulsd   xmm0, cs:__real@3fe0000000000000
0x1800f9f5c  movsd   qword ptr [rsp+100h+var_C8+8], xmm0
0x1800f9f62  addsd   xmm3, xmm0
0x1800f9f66  jmp     short loc_1800F9F6C
0x1800f9f68  addsd   xmm3, xmm7
0x1800f9f6c  movsd   qword ptr [rsp+100h+var_B8+8], xmm3
0x1800f9f72  jmp     loc_1800FA05F
0x1800f9f77  comisd  xmm1, xmm6
0x1800f9f7b  jbe     short loc_1800F9FEE
0x1800f9f7d  divsd   xmm0, xmm1
0x1800f9f81  sub     ecx, 1
0x1800f9f84  jz      short loc_1800F9FDF
0x1800f9f86  sub     ecx, 1
0x1800f9f89  jz      short loc_1800F9FC0
0x1800f9f8b  sub     ecx, 1
0x1800f9f8e  jz      short loc_1800F9FB2
0x1800f9f90  sub     ecx, 1
0x1800f9f93  jz      short loc_1800F9FDF
0x1800f9f95  sub     ecx, 1
0x1800f9f98  jz      short loc_1800F9FC0
0x1800f9f9a  sub     ecx, 1
0x1800f9f9d  jz      short loc_1800F9FB2
0x1800f9f9f  sub     ecx, 1
0x1800f9fa2  jz      short loc_1800F9FDF
0x1800f9fa4  sub     ecx, 1
0x1800f9fa7  jz      short loc_1800F9FC0
0x1800f9fa9  cmp     ecx, 1
0x1800f9fac  jnz     loc_1800FA329
0x1800f9fb2  subsd   xmm4, xmm0
0x1800f9fb6  movsd   qword ptr [rbp+2Fh+var_A0], xmm4
0x1800f9fbb  jmp     loc_1800FA05F
0x1800f9fc0  addsd   xmm4, cs:__real@0000000000000000
0x1800f9fc8  subsd   xmm4, xmm0
0x1800f9fcc  mulsd   xmm4, cs:__real@3fe0000000000000
0x1800f9fd4  movsd   qword ptr [rbp+2Fh+var_A0], xmm4
0x1800f9fd9  addsd   xmm0, xmm4
0x1800f9fdd  jmp     short loc_1800F9FE7
0x1800f9fdf  addsd   xmm0, cs:__real@0000000000000000
0x1800f9fe7  movsd   qword ptr [rbp+2Fh+var_90], xmm0
0x1800f9fec  jmp     short loc_1800FA05F
0x1800f9fee  mulsd   xmm1, xmm4
0x1800f9ff2  sub     ecx, 1
0x1800f9ff5  jz      short loc_1800FA052
0x1800f9ff7  sub     ecx, 1
0x1800f9ffa  jz      short loc_1800FA02E
0x1800f9ffc  sub     ecx, 1
0x1800f9fff  jz      short loc_1800FA023
0x1800fa001  sub     ecx, 1
0x1800fa004  jz      short loc_1800FA052
0x1800fa006  sub     ecx, 1
0x1800fa009  jz      short loc_1800FA02E
0x1800fa00b  sub     ecx, 1
0x1800fa00e  jz      short loc_1800FA023
0x1800fa010  sub     ecx, 1
0x1800fa013  jz      short loc_1800FA052
0x1800fa015  sub     ecx, 1
0x1800fa018  jz      short loc_1800FA02E
0x1800fa01a  cmp     ecx, 1
0x1800fa01d  jnz     loc_1800FA2F1
0x1800fa023  subsd   xmm0, xmm1
0x1800fa027  movsd   qword ptr [rbp+2Fh+var_A0+8], xmm0
0x1800fa02c  jmp     short loc_1800FA05F
0x1800fa02e  addsd   xmm0, cs:__real@0000000000000000
0x1800fa036  subsd   xmm0, xmm1
0x1800fa03a  mulsd   xmm0, cs:__real@3fe0000000000000
0x1800fa042  movsd   qword ptr [rbp+2Fh+var_A0+8], xmm0
0x1800fa047  addsd   xmm0, xmm1
0x1800fa04b  movsd   qword ptr [rbp+2Fh+var_90+8], xmm0
0x1800fa050  jmp     short loc_1800FA05F
0x1800fa052  addsd   xmm1, cs:__real@0000000000000000
0x1800fa05a  movsd   qword ptr [rbp+2Fh+var_90+8], xmm1
0x1800fa05f  lea     r9, [rbp+2Fh+var_A0]
0x1800fa063  lea     r8, [rsp+100h+var_C8+8]
0x1800fa068  mov     rdx, rdi
0x1800fa06b  lea     rcx, [rbp+2Fh+arg_0]
0x1800fa06f  call    cs:__imp_?Create@IEffectImage@GEL@@SA?AV?$TCntPtr@UIEffectImage@GEL@@@Ofc@@AEBUIImage@2@AEBU?$TRect@N@Math@@AEBU?$TRect@V?$TUnits@NUDevicePixels@Math@@@Math@@@7@@Z; GEL::IEffectImage::Create(GEL::IImage const &,Math::TRect<double> const &,Math::TRect<Math::TUnits<double,Math::DevicePixels>> const &)
0x1800fa075  jmp     loc_1800FA2A9
0x1800fa07a  cmp     byte ptr [rbx+1F8h], 0
0x1800fa081  jz      loc_1800FA29F
0x1800fa087  lea     rdx, [rbx+200h]
0x1800fa08e  mov     [rbp+2Fh+var_78], 0
0x1800fa096  xorps   xmm0, xmm0
0x1800fa099  movdqu  [rsp+100h+var_D8+8], xmm0
0x1800fa09f  cmp     qword ptr [rdx+10h], 0
0x1800fa0a4  jz      short loc_1800FA0B8
0x1800fa0a6  mov     rax, [r14+18h]
0x1800fa0aa  mov     rcx, [rax+40h]
0x1800fa0ae  call    ?QueryRenderable@Environment@SVG@Mso@@QEAAPEAVRenderableContext@23@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Mso::SVG::Environment::QueryRenderable(std::wstring const &)
0x1800fa0b3  test    rax, rax
0x1800fa0b6  jnz     short loc_1800FA0FA
0x1800fa0b8  mov     rdx, rsi
0x1800fa0bb  lea     rcx, [rsp+100h+var_D8+8]
0x1800fa0c0  call    ?GetEffectOrEmptyContainer@EffectAccumulator@GEL@@QEAA?AV?$TCntPtr@$$CBUIEffect@GEL@@@Ofc@@XZ; GEL::EffectAccumulator::GetEffectOrEmptyContainer(void)
0x1800fa0c5  mov     rcx, qword ptr [rsp+100h+var_C8]
0x1800fa0ca  test    rcx, rcx
0x1800fa0cd  jz      short loc_1800FA0DD
0x1800fa0cf  nop
0x1800fa0d0  mov     rax, [rcx]
0x1800fa0d3  mov     rax, [rax+8]
0x1800fa0d7  call    cs:__guard_dispatch_icall_fptr
0x1800fa0dd  mov     rcx, qword ptr [rsp+100h+var_D8+8]
0x1800fa0e2  test    rcx, rcx
0x1800fa0e5  jz      short loc_1800FA0F5
0x1800fa0e7  mov     rax, [rcx]
0x1800fa0ea  mov     rax, [rax+8]
0x1800fa0ee  call    cs:__guard_dispatch_icall_fptr
0x1800fa0f4  nop
0x1800fa0f5  jmp     loc_1800FA2CC
0x1800fa0fa  mov     r8, [r14+18h]
0x1800fa0fe  mov     rdx, rax
0x1800fa101  lea     rcx, [rbp+2Fh+arg_0]
0x1800fa105  call    ?Create@RenderableRenderer@SVG@Mso@@SA?AV?$TCntPtr@VRenderableRenderer@SVG@Mso@@@3@AEAVRenderableContext@23@AEAVEnvironmentRenderer@23@@Z; Mso::SVG::RenderableRenderer::Create(Mso::SVG::RenderableContext &,Mso::SVG::EnvironmentRenderer &)
0x1800fa10a  mov     rdi, [rax]
0x1800fa10d  mov     qword ptr [rax], 0
0x1800fa114  mov     [rbp+2Fh+var_78], rdi
0x1800fa118  mov     rcx, [rbp+2Fh+arg_0]
0x1800fa11c  test    rcx, rcx
0x1800fa11f  jz      short loc_1800FA136
0x1800fa121  mov     [rbp+2Fh+arg_0], 0
0x1800fa129  mov     rax, [rcx]
0x1800fa12c  mov     rax, [rax+8]
0x1800fa130  call    cs:__guard_dispatch_icall_fptr
0x1800fa136  mov     rax, [rbx]
0x1800fa139  mov     rcx, rbx
0x1800fa13c  mov     rax, [rax+68h]
0x1800fa140  call    cs:__guard_dispatch_icall_fptr
0x1800fa146  mov     rcx, [rbp+2Fh+arg_28]
0x1800fa14a  mov     qword ptr [rsp+100h+var_C8+8], rcx
0x1800fa14f  mov     qword ptr [rsp+100h+var_B8], rax
0x1800fa154  mov     rax, [rcx+10h]
0x1800fa158  mov     qword ptr [rsp+100h+var_B8+8], rax
0x1800fa15d  lea     rcx, [rsp+100h+var_C8+8]
0x1800fa162  call    ??$Get@$0BO@@StyleResolveChain@SVG@Mso@@QEBAAEB_NXZ; Mso::SVG::StyleResolveChain::Get<30>(void)
0x1800fa167  cmp     byte ptr [rax], 0
0x1800fa16a  jnz     short loc_1800FA1BD
0x1800fa16c  mov     rdx, rsi
0x1800fa16f  lea     rcx, [rsp+100h+var_D8+8]
0x1800fa174  call    ?GetEffectOrEmptyContainer@EffectAccumulator@GEL@@QEAA?AV?$TCntPtr@$$CBUIEffect@GEL@@@Ofc@@XZ; GEL::EffectAccumulator::GetEffectOrEmptyContainer(void)
0x1800fa179  nop
0x1800fa17a  mov     rcx, qword ptr [rsp+100h+var_C8]
0x1800fa17f  test    rcx, rcx
0x1800fa182  jz      short loc_1800FA191
0x1800fa184  mov     rax, [rcx]
0x1800fa187  mov     rax, [rax+8]
0x1800fa18b  call    cs:__guard_dispatch_icall_fptr
0x1800fa191  mov     rcx, qword ptr [rsp+100h+var_D8+8]
0x1800fa196  test    rcx, rcx
0x1800fa199  jz      short loc_1800FA1A9
0x1800fa19b  mov     rax, [rcx]
0x1800fa19e  mov     rax, [rax+8]
0x1800fa1a2  call    cs:__guard_dispatch_icall_fptr
0x1800fa1a8  nop
0x1800fa1a9  test    rdi, rdi
0x1800fa1ac  jz      loc_1800FA2CC
0x1800fa1b2  mov     rax, [rdi]
0x1800fa1b5  mov     rcx, rdi
0x1800fa1b8  jmp     loc_1800FA2C2
0x1800fa1bd  mov     rbx, [rbp+2Fh+arg_30]
0x1800fa1c1  movups  xmm0, xmmword ptr [rbx]
0x1800fa1c4  movups  [rbp+2Fh+var_A0], xmm0
0x1800fa1c8  movups  xmm1, xmmword ptr [rbx+10h]
0x1800fa1cc  movups  [rbp+2Fh+var_90], xmm1
0x1800fa1d0  test    rdi, rdi
0x1800fa1d3  jz      short loc_1800FA20B
0x1800fa1d5  mov     rcx, [r14+18h]; this
0x1800fa1d9  call    ?BeginRecursion@EnvironmentRenderer@SVG@Mso@@QEAAXXZ; Mso::SVG::EnvironmentRenderer::BeginRecursion(void)
0x1800fa1de  mov     rax, [rdi]
0x1800fa1e1  mov     rcx, [rbp+2Fh+arg_40]
0x1800fa1e5  mov     [rsp+100h+var_E0], rcx
0x1800fa1ea  lea     r9, [rbp+2Fh+var_A0]
0x1800fa1ee  lea     r8, [rsp+100h+var_C8+8]
0x1800fa1f3  lea     rdx, [rsp+100h+var_D8+8]
0x1800fa1f8  mov     rcx, rdi
0x1800fa1fb  mov     rax, [rax+20h]
0x1800fa1ff  call    cs:__guard_dispatch_icall_fptr
0x1800fa205  mov     rax, [r14+18h]
0x1800fa209  dec     dword ptr [rax]
  ... truncated ...
```
