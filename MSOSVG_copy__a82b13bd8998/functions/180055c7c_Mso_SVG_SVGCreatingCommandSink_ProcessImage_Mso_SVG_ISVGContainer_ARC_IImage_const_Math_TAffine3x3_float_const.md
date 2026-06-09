# Mso::SVG::SVGCreatingCommandSink::ProcessImage(Mso::SVG::ISVGContainer &,ARC::IImage const &,Math::TAffine3x3<float> const &,Math::TRect<Math::TUnits<float,Math::DevicePixels>> const &,Math::TPoint2<float> const *,Math::TRect<Math::TUnits<float,Math::DevicePixels>> const *,ARC::InterpolationMode,Mso::FunctorRefThrow<Mso::SVG::IFilter & (void)> const &)

- ea: `0x180055c7c`
- end: `0x180056257`
- name: `?ProcessImage@SVGCreatingCommandSink@SVG@Mso@@AEAA?AV?$TCntPtr@UISVGShape@SVG@Mso@@@3@AEAUISVGContainer@23@AEBUIImage@ARC@@AEBU?$TAffine3x3@M@Math@@AEBU?$TRect@V?$TUnits@MUDevicePixels@Math@@@Math@@@9@PEBU?$TPoint2@M@9@PEBU?$TRect@V?$TUnits@MUDevicePixels@Math@@@Math@@@9@W4InterpolationMode@7@AEBV?$FunctorRefThrow@$$A6AAEAUIFilter@SVG@Mso@@XZ@3@@Z`
- size: `1499`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180055c7c`
- `0x180056460`

## callees

- `0x180007310`
- `0x18004f700`
- `0x1800555e4`
- `0x1800557b8`
- `0x180055c7c`
- `0x180059c94`
- `0x18005a16c`
- `0x18005a234`
- `0x18013f810`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180056250`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180056250`
- `gfx!?Create@IRectanglePath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@AEBU?$TRect@N@Math@@@Z` at `0x180055d4d`
- `gfx!?Create@IRectanglePath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@AEBU?$TRect@N@Math@@@Z` at `0x180055d4d`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
_QWORD *__fastcall Mso::SVG::SVGCreatingCommandSink::ProcessImage(
        _BYTE *a1,
        _QWORD *a2,
        int a3,
        __int64 *a4,
        __int64 a5,
        __m64 *a6,
        __int64 a7,
        __int64 a8,
        int a9,
        _QWORD *a10)
{
  __m64 *v14; // rdi
  __int64 v15; // rax
  __int64 v16; // rax
  void ***v17; // rax
  void **v18; // rbx
  __int64 *v19; // rax
  __int64 v20; // rcx
  __int64 v21; // rcx
  void (__fastcall **v22)(void **); // rax
  void **v23; // rcx
  __int64 v24; // rax
  unsigned __int8 (__fastcall **v25)(void **, GUID *, _QWORD *); // rax
  __int64 v26; // rcx
  __int64 v27; // rbx
  __int64 v28; // rbx
  __int64 v29; // rax
  __int64 v30; // rdi
  __int64 v31; // rbx
  _QWORD *v32; // rax
  __int64 v33; // rcx
  double v34; // r12
  _QWORD *v35; // rbx
  __int64 v36; // r14
  float *v37; // rsi
  __int64 v38; // rdi
  __int64 v39; // rax
  __int64 v40; // rdx
  __int64 v41; // rax
  __int64 v42; // rdx
  __int64 v43; // rax
  __int64 v44; // rdx
  __int64 v45; // rax
  __int64 v46; // r8
  void (__fastcall *v47)(__int64, double *); // rax
  float v48; // xmm0_4
  __int64 v49; // rax
  __int64 v51; // [rsp+58h] [rbp-79h] BYREF
  __int64 v52; // [rsp+60h] [rbp-71h] BYREF
  __int64 v53; // [rsp+68h] [rbp-69h] BYREF
  void **v54; // [rsp+70h] [rbp-61h] BYREF
  double v55; // [rsp+78h] [rbp-59h] BYREF
  double v56; // [rsp+80h] [rbp-51h]
  void **v57; // [rsp+88h] [rbp-49h] BYREF
  __int64 v58; // [rsp+90h] [rbp-41h]
  __int64 v59; // [rsp+A0h] [rbp-31h] BYREF
  _OWORD v60[2]; // [rsp+B0h] [rbp-21h] BYREF
  __int64 v61; // [rsp+120h] [rbp+4Fh] BYREF

  v14 = a6;
  v15 = *a4;
  v52 = 0;
  if ( (*(unsigned __int8 (__fastcall **)(__int64 *, GUID *, __int64 *))(v15 + 16))(
         a4,
         &GUID_5ecd01d8_2a41_4e65_a252_1457f8afa251,
         &v52) )
  {
    Mso::SVG::SVGCreatingCommandSink::ProcessBitmap(
      (_DWORD)a1,
      (_DWORD)a2,
      a3,
      v52,
      a5,
      LODWORD(FLOAT_1_0),
      a9,
      (__int64)v14);
    goto LABEL_30;
  }
  v16 = *a4;
  v53 = 0;
  if ( !(*(unsigned __int8 (__fastcall **)(__int64 *, GUID *, __int64 *))(v16 + 16))(
          a4,
          &GUID_0c26e307_cd0e_4aa1_92ad_b10a976b1d00,
          &v53) )
  {
    v24 = *a4;
    v54 = 0;
    if ( !(*(unsigned __int8 (__fastcall **)(__int64 *, GUID *, void ***))(v24 + 16))(
            a4,
            &GUID_e40deeae_2bd8_4409_b6ca_b10ebc214b24,
            &v54) )
    {
      a1[327] = 1;
      OExceptionLog::ThrowTag(591012934, 55, L"Unsupported image type");
    }
    v61 = 0;
    v25 = (unsigned __int8 (__fastcall **)(void **, GUID *, _QWORD *))*v54;
    v61 = 0;
    if ( v25[2](v54, &GUID_8744c74d_5c7f_44a2_9559_39a69079cfa7, &v61) )
    {
      v26 = *(_QWORD *)(*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v61 + 64LL))(v61, &v51);
      v57 = &Mso::SVG::AffineTransformEffectProgramConverter::`vftable';
      v58 = 0;
      (*(void (__fastcall **)(__int64, void ***))(*(_QWORD *)v26 + 16LL))(v26, &v57);
      v27 = v58;
      v57 = &Mso::SVG::AffineTransformEffectProgramConverter::`vftable';
      v58 = 0;
      if ( v51 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 8LL))(v51);
      if ( v27 )
      {
        a1[325] = 1;
        v28 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v27 + 24LL))(v27);
        v29 = Math::Inverse<float>(&v57, v28);
        v30 = Math::GetTransformedBounds<Math::TUnits<float,Math::DevicePixels>,float,Math::TUnits<float,Math::DevicePixels>>(
                &v55,
                v14,
                v29);
        v31 = Math::operator*<float,float,float>(v60, a5, v28);
        v32 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v61 + 56LL))(v61, &v51);
        Mso::SVG::SVGCreatingCommandSink::ProcessImage(
          (_DWORD)a1,
          (_DWORD)a2,
          a3,
          *v32,
          v31,
          v30,
          a7,
          a8,
          a9,
          (__int64)a10);
LABEL_21:
        if ( v51 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 8LL))(v51);
        if ( v61 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 8LL))(v61);
        v23 = v54;
        if ( !v54 )
          goto LABEL_28;
        v22 = (void (__fastcall **)(void **))*v54;
        goto LABEL_27;
      }
      v33 = *(_QWORD *)(*(__int64 (__fastcall **)(__int64, void ***))(*(_QWORD *)v61 + 64LL))(v61, &v57);
      v55 = COERCE_DOUBLE(&Mso::SVG::ShadowEffectProgramConverter::`vftable');
      v56 = 0.0;
      (*(void (__fastcall **)(__int64, double *))(*(_QWORD *)v33 + 16LL))(v33, &v55);
      v34 = v56;
      v55 = COERCE_DOUBLE(&Mso::SVG::ShadowEffectProgramConverter::`vftable');
      v56 = 0.0;
      if ( v57 )
        (*((void (__fastcall **)(void **))*v57 + 1))(v57);
      if ( v34 != 0.0 )
      {
        a1[325] = 1;
        (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v61 + 56LL))(v61, &v51);
        v35 = a10;
        Mso::SVG::SVGCreatingCommandSink::ProcessImage(
          (_DWORD)a1,
          (unsigned int)&v59,
          a3,
          v51,
          a5,
          (__int64)v14,
          a7,
          a8,
          a9,
          (__int64)a10);
        if ( !*v35 )
        {
          CrashWithRecovery(0x25D9805u, 0);
          JUMPOUT(0x180056256LL);
        }
        v36 = (*(__int64 (__fastcall **)(_QWORD *))*v35)(v35);
        (*(void (__fastcall **)(double))(**(_QWORD **)&v34 + 32LL))(COERCE_DOUBLE(*(_QWORD *)&v34));
        v37 = (float *)(*(__int64 (__fastcall **)(double))(**(_QWORD **)&v34 + 24LL))(COERCE_DOUBLE(*(_QWORD *)&v34));
        v38 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v36 + 72LL))(v36);
        v39 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v38 + 32LL))(v38, 0);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 24LL))(v39);
        LOBYTE(v40) = 1;
        v41 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v38 + 32LL))(v38, v40);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 24LL))(v41);
        LOBYTE(v42) = 2;
        v43 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v38 + 32LL))(v38, v42);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 24LL))(v43);
        LOBYTE(v44) = 3;
        v45 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v38 + 32LL))(v38, v44);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
        (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v38 + 24LL))(v38, 0);
        v46 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v36 + 80LL))(v36);
        v47 = *(void (__fastcall **)(__int64, double *))(*(_QWORD *)v46 + 32LL);
        v48 = v37[1];
        v55 = (float)(*v37 / 3.0);
        v56 = (float)(v48 / 3.0);
        v47(v46, &v55);
        v49 = v59;
        v59 = 0;
        *a2 = v49;
        goto LABEL_21;
      }
    }
    Ofc::TCntPtr<GEL::IPen>::~TCntPtr<GEL::IPen>(&v61);
    a1[326] = 1;
    OExceptionLog::ThrowTag(591012935, 55, L"Unsupported effect");
  }
  v60[0] = _mm_cvtps_pd((__m64)v14->m64_u64);
  v60[1] = _mm_cvtps_pd(v14[1]);
  v17 = (void ***)GEL::IRectanglePath::Create(&v51, v60);
  v18 = *v17;
  *v17 = 0;
  v57 = v18;
  if ( v51 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 8LL))(v51);
  v19 = (__int64 *)Mso::SVG::SVGCreatingCommandSink::ProcessCommandList(
                     (_DWORD)a1,
                     (unsigned int)&v61,
                     a3,
                     v53,
                     a5,
                     (__int64)v18);
  v20 = *v19;
  *v19 = 0;
  *a2 = v20;
  v21 = v61;
  if ( v61 )
  {
    v61 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 8LL))(v21);
  }
  if ( !v18 )
    goto LABEL_28;
  v22 = (void (__fastcall **)(void **))*v18;
  v23 = v18;
LABEL_27:
  v22[1](v23);
LABEL_28:
  if ( v53 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 8LL))(v53);
LABEL_30:
  if ( v52 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 8LL))(v52);
  return a2;
}

```

## disassembly

```asm
0x180055c7c  mov     rax, rsp
0x180055c7f  mov     [rax+8], rbx
0x180055c83  mov     [rax+10h], rsi
0x180055c87  mov     [rax+18h], rdi
0x180055c8b  push    rbp
0x180055c8c  push    r12
0x180055c8e  push    r13
0x180055c90  push    r14
0x180055c92  push    r15
0x180055c94  lea     rbp, [rax-2Fh]
0x180055c98  sub     rsp, 0D0h
0x180055c9f  mov     rbx, r9
0x180055ca2  mov     r14, r8
0x180055ca5  mov     r15, rdx
0x180055ca8  mov     rsi, rcx
0x180055cab  mov     rdi, [rbp+27h+arg_28]
0x180055caf  xor     r13d, r13d
0x180055cb2  mov     rax, [r9]
0x180055cb5  mov     [rbp+27h+var_98], r13
0x180055cb9  lea     r8, [rbp+27h+var_98]
0x180055cbd  lea     rdx, _GUID_5ecd01d8_2a41_4e65_a252_1457f8afa251
0x180055cc4  mov     rcx, r9
0x180055cc7  mov     rax, [rax+10h]
0x180055ccb  call    cs:__guard_dispatch_icall_fptr
0x180055cd1  test    al, al
0x180055cd3  jz      short loc_180055D0F
0x180055cd5  mov     qword ptr [rsp+0F0h+var_B8], rdi
0x180055cda  mov     eax, [rbp+27h+arg_40]
0x180055cdd  mov     dword ptr [rsp+0F0h+var_C0], eax
0x180055ce1  movss   xmm0, cs:__real@3f800000
0x180055ce9  movss   dword ptr [rsp+0F0h+var_C8], xmm0
0x180055cef  mov     rax, [rbp+27h+arg_20]
0x180055cf3  mov     [rsp+0F0h+var_D0], rax
0x180055cf8  mov     r9, [rbp+27h+var_98]
0x180055cfc  mov     r8, r14
0x180055cff  mov     rdx, r15
0x180055d02  mov     rcx, rsi
0x180055d05  call    ?ProcessBitmap@SVGCreatingCommandSink@SVG@Mso@@AEAA?AV?$TCntPtr@UISVGShape@SVG@Mso@@@3@AEAUISVGContainer@23@AEBUIBitmap@ARC@@AEBU?$TAffine3x3@M@Math@@MW4InterpolationMode@7@AEBU?$TRect@V?$TUnits@MUDevicePixels@Math@@@Math@@@9@@Z; Mso::SVG::SVGCreatingCommandSink::ProcessBitmap(Mso::SVG::ISVGContainer &,ARC::IBitmap const &,Math::TAffine3x3<float> const &,float,ARC::InterpolationMode,Math::TRect<Math::TUnits<float,Math::DevicePixels>> const &)
0x180055d0a  jmp     loc_1800561C5
0x180055d0f  mov     rax, [rbx]
0x180055d12  mov     [rbp+27h+var_90], r13
0x180055d16  lea     r8, [rbp+27h+var_90]
0x180055d1a  lea     rdx, _GUID_0c26e307_cd0e_4aa1_92ad_b10a976b1d00
0x180055d21  mov     rcx, rbx
0x180055d24  mov     rax, [rax+10h]
0x180055d28  call    cs:__guard_dispatch_icall_fptr
0x180055d2e  test    al, al
0x180055d30  jz      loc_180055DCC
0x180055d36  cvtps2pd xmm0, qword ptr [rdi]
0x180055d39  movups  [rbp+27h+var_48], xmm0
0x180055d3d  cvtps2pd xmm0, qword ptr [rdi+8]
0x180055d41  movups  [rbp+27h+var_38], xmm0
0x180055d45  lea     rdx, [rbp+27h+var_48]
0x180055d49  lea     rcx, [rbp+27h+var_A0]
0x180055d4d  call    cs:__imp_?Create@IRectanglePath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@AEBU?$TRect@N@Math@@@Z; GEL::IRectanglePath::Create(Math::TRect<double> const &)
0x180055d53  mov     rbx, [rax]
0x180055d56  mov     [rax], r13
0x180055d59  mov     [rbp+27h+var_70], rbx
0x180055d5d  mov     rcx, [rbp+27h+var_A0]
0x180055d61  test    rcx, rcx
0x180055d64  jz      short loc_180055D73
0x180055d66  mov     rax, [rcx]
0x180055d69  mov     rax, [rax+8]
0x180055d6d  call    cs:__guard_dispatch_icall_fptr
0x180055d73  mov     [rsp+0F0h+var_C8], rbx
0x180055d78  mov     rax, [rbp+27h+arg_20]
0x180055d7c  mov     [rsp+0F0h+var_D0], rax
0x180055d81  mov     r9, [rbp+27h+var_90]
0x180055d85  mov     r8, r14
0x180055d88  lea     rdx, [rbp+27h+arg_18]
0x180055d8c  mov     rcx, rsi
0x180055d8f  call    ?ProcessCommandList@SVGCreatingCommandSink@SVG@Mso@@AEAA?AV?$TCntPtr@UISVGContainer@SVG@Mso@@@3@AEAUISVGContainer@23@AEBUICommandList@ARC@@AEBU?$TAffine3x3@M@Math@@AEBUIPath@GEL@@@Z; Mso::SVG::SVGCreatingCommandSink::ProcessCommandList(Mso::SVG::ISVGContainer &,ARC::ICommandList const &,Math::TAffine3x3<float> const &,GEL::IPath const &)
0x180055d94  mov     rcx, [rax]
0x180055d97  mov     [rax], r13
0x180055d9a  mov     [r15], rcx
0x180055d9d  mov     rcx, [rbp+27h+arg_18]
0x180055da1  test    rcx, rcx
0x180055da4  jz      short loc_180055DB8
0x180055da6  mov     [rbp+27h+arg_18], r13
0x180055daa  mov     rax, [rcx]
0x180055dad  mov     rax, [rax+8]
0x180055db1  call    cs:__guard_dispatch_icall_fptr
0x180055db7  nop
0x180055db8  test    rbx, rbx
0x180055dbb  jz      loc_1800561AE
0x180055dc1  mov     rax, [rbx]
0x180055dc4  mov     rcx, rbx
0x180055dc7  jmp     loc_1800561A3
0x180055dcc  mov     rax, [rbx]
0x180055dcf  mov     [rbp+27h+var_88], r13
0x180055dd3  lea     r8, [rbp+27h+var_88]
0x180055dd7  lea     rdx, _GUID_e40deeae_2bd8_4409_b6ca_b10ebc214b24
0x180055dde  mov     rcx, rbx
0x180055de1  mov     rax, [rax+10h]
0x180055de5  call    cs:__guard_dispatch_icall_fptr
0x180055deb  test    al, al
0x180055ded  jz      loc_180056226
0x180055df3  mov     [rbp+27h+arg_18], r13
0x180055df7  mov     rcx, [rbp+27h+var_88]
0x180055dfb  mov     rax, [rcx]
0x180055dfe  mov     [rbp+27h+arg_18], r13
0x180055e02  lea     r8, [rbp+27h+arg_18]
0x180055e06  lea     rdx, _GUID_8744c74d_5c7f_44a2_9559_39a69079cfa7
0x180055e0d  mov     rax, [rax+10h]
0x180055e11  call    cs:__guard_dispatch_icall_fptr
0x180055e17  test    al, al
0x180055e19  jz      loc_1800561FF
0x180055e1f  mov     rcx, [rbp+27h+arg_18]
0x180055e23  mov     rax, [rcx]
0x180055e26  lea     rdx, [rbp+27h+var_A0]
0x180055e2a  mov     rax, [rax+40h]
0x180055e2e  call    cs:__guard_dispatch_icall_fptr
0x180055e34  nop
0x180055e35  mov     rcx, [rax]
0x180055e38  lea     r12, ??_7AffineTransformEffectProgramConverter@SVG@Mso@@6B@; const Mso::SVG::AffineTransformEffectProgramConverter::`vftable'
0x180055e3f  mov     [rbp+27h+var_70], r12
0x180055e43  mov     [rbp+27h+var_68], r13
0x180055e47  mov     rax, [rcx]
0x180055e4a  lea     rdx, [rbp+27h+var_70]
0x180055e4e  mov     rax, [rax+10h]
0x180055e52  call    cs:__guard_dispatch_icall_fptr
0x180055e58  mov     rbx, [rbp+27h+var_68]
0x180055e5c  mov     [rbp+27h+var_70], r12
0x180055e60  mov     [rbp+27h+var_68], r13
0x180055e64  mov     rcx, [rbp+27h+var_A0]
0x180055e68  test    rcx, rcx
0x180055e6b  jz      short loc_180055E7A
0x180055e6d  mov     rax, [rcx]
0x180055e70  mov     rax, [rax+8]
0x180055e74  call    cs:__guard_dispatch_icall_fptr
0x180055e7a  test    rbx, rbx
0x180055e7d  jz      loc_180055F25
0x180055e83  mov     byte ptr [rsi+145h], 1
0x180055e8a  mov     rax, [rbx]
0x180055e8d  mov     rcx, rbx
0x180055e90  mov     rax, [rax+18h]
0x180055e94  call    cs:__guard_dispatch_icall_fptr
0x180055e9a  mov     rbx, rax
0x180055e9d  mov     rdx, rax
0x180055ea0  lea     rcx, [rbp+27h+var_70]
0x180055ea4  call    ??$Inverse@M@Math@@YA?AU?$TAffine3x3@M@0@AEBU10@@Z; Math::Inverse<float>(Math::TAffine3x3<float> const &)
0x180055ea9  mov     r8, rax
0x180055eac  mov     rdx, rdi
0x180055eaf  lea     rcx, [rbp+27h+var_80]
0x180055eb3  call    ??$GetTransformedBounds@V?$TUnits@MUDevicePixels@Math@@@Math@@MV12@@Math@@YA?AU?$TRect@V?$TUnits@MUDevicePixels@Math@@@Math@@@0@AEBU10@AEBU?$TAffine3x3@M@0@@Z; Math::GetTransformedBounds<Math::TUnits<float,Math::DevicePixels>,float,Math::TUnits<float,Math::DevicePixels>>(Math::TRect<Math::TUnits<float,Math::DevicePixels>> const &,Math::TAffine3x3<float> const &)
0x180055eb8  mov     rdi, rax
0x180055ebb  mov     r8, rbx
0x180055ebe  mov     rdx, [rbp+27h+arg_20]
0x180055ec2  lea     rcx, [rbp+27h+var_48]
0x180055ec6  call    ??$?DMMM@Math@@YA?AU?$TAffine3x3@M@0@AEBU10@0@Z; Math::operator*<float,float,float>(Math::TAffine3x3<float> const &,Math::TAffine3x3<float> const &)
0x180055ecb  mov     rbx, rax
0x180055ece  mov     rcx, [rbp+27h+arg_18]
0x180055ed2  mov     rdx, [rcx]
0x180055ed5  mov     rax, [rdx+38h]
0x180055ed9  lea     rdx, [rbp+27h+var_A0]
0x180055edd  call    cs:__guard_dispatch_icall_fptr
0x180055ee3  mov     r9, [rax]
0x180055ee6  mov     rcx, [rbp+27h+arg_48]
0x180055eea  mov     [rsp+0F0h+var_A8], rcx
0x180055eef  mov     eax, [rbp+27h+arg_40]
0x180055ef2  mov     dword ptr [rsp+0F0h+var_B0], eax
0x180055ef6  mov     rax, [rbp+27h+arg_38]
0x180055efa  mov     qword ptr [rsp+0F0h+var_B8], rax
0x180055eff  mov     rax, [rbp+27h+arg_30]
0x180055f03  mov     [rsp+0F0h+var_C0], rax
0x180055f08  mov     [rsp+0F0h+var_C8], rdi
0x180055f0d  mov     [rsp+0F0h+var_D0], rbx
0x180055f12  mov     r8, r14
0x180055f15  mov     rdx, r15
0x180055f18  mov     rcx, rsi
0x180055f1b  call    ?ProcessImage@SVGCreatingCommandSink@SVG@Mso@@AEAA?AV?$TCntPtr@UISVGShape@SVG@Mso@@@3@AEAUISVGContainer@23@AEBUIImage@ARC@@AEBU?$TAffine3x3@M@Math@@AEBU?$TRect@V?$TUnits@MUDevicePixels@Math@@@Math@@@9@PEBU?$TPoint2@M@9@PEBU?$TRect@V?$TUnits@MUDevicePixels@Math@@@Math@@@9@W4InterpolationMode@7@AEBV?$FunctorRefThrow@$$A6AAEAUIFilter@SVG@Mso@@XZ@3@@Z; Mso::SVG::SVGCreatingCommandSink::ProcessImage(Mso::SVG::ISVGContainer &,ARC::IImage const &,Math::TAffine3x3<float> const &,Math::TRect<Math::TUnits<float,Math::DevicePixels>> const &,Math::TPoint2<float> const *,Math::TRect<Math::TUnits<float,Math::DevicePixels>> const *,ARC::InterpolationMode,Mso::FunctorRefThrow<Mso::SVG::IFilter & (void)> const &)
0x180055f20  jmp     loc_180056169
0x180055f25  mov     rcx, [rbp+27h+arg_18]
0x180055f29  mov     rax, [rcx]
0x180055f2c  lea     rdx, [rbp+27h+var_70]
0x180055f30  mov     rax, [rax+40h]
0x180055f34  call    cs:__guard_dispatch_icall_fptr
0x180055f3a  mov     rcx, [rax]
0x180055f3d  lea     rbx, ??_7ShadowEffectProgramConverter@SVG@Mso@@6B@; const Mso::SVG::ShadowEffectProgramConverter::`vftable'
0x180055f44  mov     [rbp+27h+var_80], rbx
0x180055f48  mov     [rbp+27h+var_78], r13
0x180055f4c  mov     rax, [rcx]
0x180055f4f  lea     rdx, [rbp+27h+var_80]
0x180055f53  mov     rax, [rax+10h]
0x180055f57  call    cs:__guard_dispatch_icall_fptr
0x180055f5d  mov     r12, [rbp+27h+var_78]
0x180055f61  mov     [rbp+27h+var_80], rbx
0x180055f65  mov     [rbp+27h+var_78], r13
0x180055f69  mov     rcx, [rbp+27h+var_70]
0x180055f6d  test    rcx, rcx
0x180055f70  jz      short loc_180055F7F
0x180055f72  mov     rax, [rcx]
0x180055f75  mov     rax, [rax+8]
0x180055f79  call    cs:__guard_dispatch_icall_fptr
0x180055f7f  test    r12, r12
0x180055f82  jz      loc_1800561FF
0x180055f88  mov     byte ptr [rsi+145h], 1
0x180055f8f  mov     rcx, [rbp+27h+arg_18]
0x180055f93  mov     rax, [rcx]
0x180055f96  lea     rdx, [rbp+27h+var_A0]
0x180055f9a  mov     rax, [rax+38h]
0x180055f9e  call    cs:__guard_dispatch_icall_fptr
0x180055fa4  mov     rbx, [rbp+27h+arg_48]
0x180055fa8  mov     [rsp+0F0h+var_A8], rbx
0x180055fad  mov     eax, [rbp+27h+arg_40]
0x180055fb0  mov     dword ptr [rsp+0F0h+var_B0], eax
0x180055fb4  mov     rax, [rbp+27h+arg_38]
0x180055fb8  mov     qword ptr [rsp+0F0h+var_B8], rax
0x180055fbd  mov     rax, [rbp+27h+arg_30]
0x180055fc1  mov     [rsp+0F0h+var_C0], rax
0x180055fc6  mov     [rsp+0F0h+var_C8], rdi
0x180055fcb  mov     rax, [rbp+27h+arg_20]
0x180055fcf  mov     [rsp+0F0h+var_D0], rax
0x180055fd4  mov     r9, [rbp+27h+var_A0]
0x180055fd8  mov     r8, r14
0x180055fdb  lea     rdx, [rbp+27h+var_58]
0x180055fdf  mov     rcx, rsi
0x180055fe2  call    ?ProcessImage@SVGCreatingCommandSink@SVG@Mso@@AEAA?AV?$TCntPtr@UISVGShape@SVG@Mso@@@3@AEAUISVGContainer@23@AEBUIImage@ARC@@AEBU?$TAffine3x3@M@Math@@AEBU?$TRect@V?$TUnits@MUDevicePixels@Math@@@Math@@@9@PEBU?$TPoint2@M@9@PEBU?$TRect@V?$TUnits@MUDevicePixels@Math@@@Math@@@9@W4InterpolationMode@7@AEBV?$FunctorRefThrow@$$A6AAEAUIFilter@SVG@Mso@@XZ@3@@Z; Mso::SVG::SVGCreatingCommandSink::ProcessImage(Mso::SVG::ISVGContainer &,ARC::IImage const &,Math::TAffine3x3<float> const &,Math::TRect<Math::TUnits<float,Math::DevicePixels>> const &,Math::TPoint2<float> const *,Math::TRect<Math::TUnits<float,Math::DevicePixels>> const *,ARC::InterpolationMode,Mso::FunctorRefThrow<Mso::SVG::IFilter & (void)> const &)
0x180055fe7  mov     rax, [rbx]
0x180055fea  test    rax, rax
0x180055fed  jz      loc_180056249
0x180055ff3  mov     rcx, rbx
0x180055ff6  mov     rax, [rax]
0x180055ff9  call    cs:__guard_dispatch_icall_fptr
0x180055fff  mov     r14, rax
0x180056002  mov     rdx, [r12]
0x180056006  mov     rcx, r12
0x180056009  mov     rax, [rdx+20h]
0x18005600d  call    cs:__guard_dispatch_icall_fptr
0x180056013  mov     rbx, rax
0x180056016  mov     rdx, [r12]
0x18005601a  mov     rcx, r12
0x18005601d  mov     rax, [rdx+18h]
0x180056021  call    cs:__guard_dispatch_icall_fptr
0x180056027  mov     rsi, rax
0x18005602a  mov     rcx, [r14]
0x18005602d  mov     rax, [rcx+48h]
0x180056031  mov     rcx, r14
0x180056034  call    cs:__guard_dispatch_icall_fptr
0x18005603a  mov     rdi, rax
0x18005603d  mov     rcx, [rax]
0x180056040  mov     rax, [rcx+20h]
0x180056044  xor     edx, edx
0x180056046  mov     rcx, rdi
0x180056049  call    cs:__guard_dispatch_icall_fptr
0x18005604f  mov     r8, rax
0x180056052  mov     rcx, [rax]
0x180056055  mov     rax, [rcx+18h]
0x180056059  movss   xmm1, dword ptr [rbx]
0x18005605d  cvtps2pd xmm1, xmm1
0x180056060  movaps  xmm2, xmm1
0x180056063  mov     rcx, r8
0x180056066  call    cs:__guard_dispatch_icall_fptr
0x18005606c  mov     rax, [rdi]
0x18005606f  mov     dl, 1
0x180056071  mov     rcx, rdi
0x180056074  mov     rax, [rax+20h]
0x180056078  call    cs:__guard_dispatch_icall_fptr
0x18005607e  mov     rdx, rax
0x180056081  mov     rcx, [rax]
0x180056084  mov     rax, [rcx+18h]
0x180056088  movss   xmm1, dword ptr [rbx+4]
0x18005608d  cvtps2pd xmm1, xmm1
0x180056090  movaps  xmm2, xmm1
0x180056093  mov     rcx, rdx
0x180056096  call    cs:__guard_dispatch_icall_fptr
0x18005609c  mov     rax, [rdi]
0x18005609f  mov     dl, 2
0x1800560a1  mov     rcx, rdi
0x1800560a4  mov     rax, [rax+20h]
0x1800560a8  call    cs:__guard_dispatch_icall_fptr
0x1800560ae  mov     rdx, rax
0x1800560b1  mov     rcx, [rax]
0x1800560b4  mov     rax, [rcx+18h]
0x1800560b8  movss   xmm1, dword ptr [rbx+8]
0x1800560bd  cvtps2pd xmm1, xmm1
0x1800560c0  movaps  xmm2, xmm1
0x1800560c3  mov     rcx, rdx
0x1800560c6  call    cs:__guard_dispatch_icall_fptr
0x1800560cc  mov     rax, [rdi]
0x1800560cf  mov     dl, 3
0x1800560d1  mov     rcx, rdi
0x1800560d4  mov     rax, [rax+20h]
0x1800560d8  call    cs:__guard_dispatch_icall_fptr
0x1800560de  mov     rdx, rax
0x1800560e1  mov     rcx, [rax]
0x1800560e4  mov     rax, [rcx+10h]
0x1800560e8  movss   xmm1, dword ptr [rbx+0Ch]
0x1800560ed  cvtps2pd xmm1, xmm1
0x1800560f0  xorps   xmm2, xmm2
0x1800560f3  mov     rcx, rdx
0x1800560f6  call    cs:__guard_dispatch_icall_fptr
0x1800560fc  mov     rax, [rdi]
0x1800560ff  xor     edx, edx
0x180056101  mov     rcx, rdi
0x180056104  mov     rax, [rax+18h]
0x180056108  call    cs:__guard_dispatch_icall_fptr
0x18005610e  mov     rax, [r14]
0x180056111  mov     rcx, r14
0x180056114  mov     rax, [rax+50h]
  ... truncated ...
```
