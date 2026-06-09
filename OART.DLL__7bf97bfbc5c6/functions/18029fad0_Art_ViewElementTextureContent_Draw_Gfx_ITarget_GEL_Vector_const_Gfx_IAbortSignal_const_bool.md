# Art::ViewElementTextureContent::Draw(Gfx::ITarget &,GEL::Vector const &,Gfx::IAbortSignal const *,bool)

- ea: `0x18029fad0`
- end: `0x1802a022f`
- name: `?Draw@ViewElementTextureContent@Art@@UEAA_NAEAUITarget@Gfx@@AEBUVector@GEL@@PEBUIAbortSignal@4@_N@Z`
- size: `1887`
- prototype: `bool __fastcall(Art::ViewElementTextureContent *__hidden this, struct Gfx::ITarget *, const struct GEL::Vector *, const struct Gfx::IAbortSignal *, bool)`
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config`

## callees

- `0x180024f50`
- `0x180037370`
- `0x180064400`
- `0x18006a4cc`
- `0x180070240`
- `0x180070fe0`
- `0x180071000`
- `0x1800713c0`
- `0x180071720`
- `0x18011fc50`
- `0x18029f48c`
- `0x18029fad0`
- `0x1806a5054`
- `0x1806a5084`
- `0x1806a51d0`
- `0x1806a57c4`

## import_xrefs

- `gfx!??0SpriteClipRectCachingPolicy@Gfx@@QEAA@AEBU?$TRect@V?$TUnits@HUDevicePixels@Math@@@Math@@@Math@@@Z` at `0x18029fc0e`
- `gfx!??0SpriteClipRectCachingPolicy@Gfx@@QEAA@AEBU?$TRect@V?$TUnits@HUDevicePixels@Math@@@Math@@@Math@@@Z` at `0x18029fc0e`
- `gfx!?ToggleCachingForCurrentThread@IInkStrokeCollection@Gfx@@SAX_N@Z` at `0x18029ff73`
- `gfx!?ToggleCachingForCurrentThread@IInkStrokeCollection@Gfx@@SAX_N@Z` at `0x1802a01b9`
- `gfx!?ToggleCachingForCurrentThread@IInkStrokeCollection@Gfx@@SAX_N@Z` at `0x18029ff73`
- `gfx!?ToggleCachingForCurrentThread@IInkStrokeCollection@Gfx@@SAX_N@Z` at `0x1802a01b9`
- `gfx!?FIsCachingEnabledForCurrentThread@IInkStrokeCollection@Gfx@@SA_NXZ` at `0x18029fd57`
- `gfx!?FIsCachingEnabledForCurrentThread@IInkStrokeCollection@Gfx@@SA_NXZ` at `0x18029ff65`
- `gfx!?FIsCachingEnabledForCurrentThread@IInkStrokeCollection@Gfx@@SA_NXZ` at `0x18029fd57`
- `gfx!?FIsCachingEnabledForCurrentThread@IInkStrokeCollection@Gfx@@SA_NXZ` at `0x18029ff65`
- `gfx!?Get@DefaultQualityPolicy@Gfx@@SAAEBV12@XZ` at `0x18029fd93`
- `gfx!?Get@DefaultQualityPolicy@Gfx@@SAAEBV12@XZ` at `0x18029fddf`
- `gfx!?Get@DefaultQualityPolicy@Gfx@@SAAEBV12@XZ` at `0x18029fd93`
- `gfx!?Get@DefaultQualityPolicy@Gfx@@SAAEBV12@XZ` at `0x18029fddf`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1802a01c9`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1802a0204`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1802a01c9`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1802a0204`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1802a00d0`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1802a00d0`

## pseudocode

```c
char __fastcall Art::ViewElementTextureContent::Draw(
        struct Ofc::CProxyPtrImpl **this,
        struct Gfx::ITarget *a2,
        const struct GEL::Vector *a3,
        const struct Gfx::IAbortSignal *a4,
        bool a5)
{
  struct Ofc::CProxyPtrImpl *v7; // rax
  struct Ofc::CProxyPtrImpl **Checked; // rax
  __int64 v9; // rcx
  struct Ofc::CProxyPtrImpl **v10; // rbx
  void *v11; // rax
  __int64 v12; // rbx
  char *v13; // rax
  double v14; // xmm1_8
  double v15; // xmm0_8
  double v16; // xmm3_8
  __int64 v17; // rcx
  void *v18; // rdi
  struct Ofc::CProxyPtrImpl *v19; // rax
  __int64 v20; // rsi
  __int64 v21; // r15
  int v22; // esi
  double v23; // xmm8_8
  char v24; // r12
  int v25; // eax
  void ***v26; // r14
  __int64 v27; // rax
  __int64 *v28; // rdi
  __int64 v29; // rax
  struct Ofc::CProxyPtrImpl *v30; // rcx
  double v31; // xmm5_8
  double v32; // xmm3_8
  double v33; // xmm1_8
  double v34; // xmm4_8
  double v35; // xmm2_8
  double v36; // xmm0_8
  double v37; // xmm3_8
  double v38; // xmm1_8
  double v39; // xmm1_8
  __int128 v40; // xmm1
  __int64 v41; // rsi
  __int64 v42; // rax
  char v43; // di
  _QWORD *v44; // r9
  Art::View *v45; // rcx
  __int64 v46; // rdx
  __int64 v48; // rdx
  __int64 v49; // rax
  _BYTE *v50; // rax
  struct Ofc::CProxyPtrImpl *v51; // [rsp+48h] [rbp-C0h] BYREF
  Ofc::CProxyPtrImpl *v52; // [rsp+58h] [rbp-B0h] BYREF
  struct Ofc::CProxyPtrImpl *v53; // [rsp+60h] [rbp-A8h] BYREF
  struct Ofc::CProxyPtrImpl *v54; // [rsp+68h] [rbp-A0h] BYREF
  struct Ofc::CProxyPtrImpl *v55; // [rsp+70h] [rbp-98h] BYREF
  __int64 v56; // [rsp+78h] [rbp-90h]
  struct Ofc::CProxyPtrImpl *v57; // [rsp+80h] [rbp-88h] BYREF
  struct Ofc::CProxyPtrImpl *v58; // [rsp+88h] [rbp-80h] BYREF
  struct Gfx::ITarget *v59; // [rsp+90h] [rbp-78h]
  const struct Gfx::IAbortSignal *v60; // [rsp+98h] [rbp-70h]
  __int64 v61; // [rsp+A0h] [rbp-68h]
  _QWORD v62[2]; // [rsp+A8h] [rbp-60h] BYREF
  _QWORD v63[6]; // [rsp+B8h] [rbp-50h] BYREF
  int v64; // [rsp+E8h] [rbp-20h]
  int v65; // [rsp+ECh] [rbp-1Ch]
  __int128 v66; // [rsp+F0h] [rbp-18h]
  double v67; // [rsp+100h] [rbp-8h]
  double v68; // [rsp+108h] [rbp+0h]
  __int128 v69; // [rsp+110h] [rbp+8h]
  __int128 v70; // [rsp+120h] [rbp+18h]
  void **v71; // [rsp+138h] [rbp+30h] BYREF
  int v72; // [rsp+140h] [rbp+38h]
  int v73; // [rsp+144h] [rbp+3Ch]
  struct Ofc::CProxyPtrImpl *v74; // [rsp+148h] [rbp+40h]
  _QWORD v75[6]; // [rsp+150h] [rbp+48h] BYREF
  __m128i si128; // [rsp+180h] [rbp+78h] BYREF
  void **v77; // [rsp+190h] [rbp+88h]
  char v78; // [rsp+198h] [rbp+90h]
  _BYTE v79[40]; // [rsp+1A0h] [rbp+98h] BYREF
  _BYTE v80[8]; // [rsp+1C8h] [rbp+C0h] BYREF
  struct Ofc::CProxyPtrImpl *v81; // [rsp+1D0h] [rbp+C8h] BYREF
  struct Ofc::CProxyPtrImpl *v82[3]; // [rsp+1D8h] [rbp+D0h] BYREF
  _BYTE *v83; // [rsp+1F0h] [rbp+E8h]
  int v84; // [rsp+258h] [rbp+150h]
  int v85; // [rsp+25Ch] [rbp+154h]
  struct Ofc::CProxyPtrImpl *v86[4]; // [rsp+260h] [rbp+158h] BYREF
  _BYTE v87[8]; // [rsp+280h] [rbp+178h] BYREF
  void **v88; // [rsp+288h] [rbp+180h] BYREF
  int v89; // [rsp+290h] [rbp+188h]
  struct Ofc::CProxyPtrImpl *v90; // [rsp+298h] [rbp+190h] BYREF
  _BYTE v91[208]; // [rsp+2A0h] [rbp+198h] BYREF

  v60 = a4;
  v59 = a2;
  v7 = Ofc::CProxyPtrImpl::CheckedStrongAddRef(this[3]);
  v52 = v7;
  if ( !*((_QWORD *)v7 + 2) )
  {
    MsoShipAssertTagProc(3741730);
    goto LABEL_46;
  }
  Checked = (struct Ofc::CProxyPtrImpl **)Ofc::CProxyPtrImpl::GetChecked(v7);
  v54 = Ofc::CProxyPtrImpl::CheckedStrongAddRef(Checked[20]);
  v9 = *((_QWORD *)v54 + 2);
  if ( v9 )
  {
    v10 = (struct Ofc::CProxyPtrImpl **)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 32LL))(v9);
    Ofc::CProxyPtrImpl::DtorStrongRelease(&v54);
  }
  else
  {
    Ofc::CProxyPtrImpl::DtorStrongRelease(&v54);
    v10 = (struct Ofc::CProxyPtrImpl **)&`Ofc::CProxyPtrImpl::GetSentinel'::`2'::s_pProxyPtrSentinel;
  }
  v51 = Ofc::CProxyPtrImpl::CheckedStrongAddRef(*v10);
  if ( !*((_QWORD *)v51 + 2) )
  {
    MsoShipAssertTagProc(3741731);
LABEL_45:
    Ofc::CProxyPtrImpl::DtorStrongRelease(&v51);
LABEL_46:
    Ofc::CProxyPtrImpl::DtorStrongRelease(&v52);
    return 0;
  }
  v11 = Ofc::CProxyPtrImpl::GetChecked(v52);
  v62[0] = &Art::ViewElementShapeFilter::`vftable';
  v62[1] = v11;
  v12 = *((_QWORD *)Ofc::CProxyPtrImpl::GetChecked(v52) + 18);
  v75[5] = v12;
  if ( v12 )
    (**(void (__fastcall ***)(__int64))v12)(v12);
  Art::View::Info::Info((Art::View::Info *)v80);
  v13 = (char *)Ofc::CProxyPtrImpl::GetChecked(v51);
  Art::View::Info::operator=(v80, v13 + 40);
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  Gfx::SpriteClipRectCachingPolicy::SpriteClipRectCachingPolicy(v79, &si128);
  if ( !v83 )
  {
    v50 = v79;
    if ( !a5 )
      v50 = v83;
    v83 = v50;
  }
  v14 = *((double *)a3 + 1);
  v15 = DOUBLE_0_5;
  if ( v14 < 0.0 )
    v16 = DOUBLE_N0_5;
  else
    v16 = DOUBLE_0_5;
  if ( *(double *)a3 < 0.0 )
    v15 = DOUBLE_N0_5;
  v84 = (int)(v15 + *(double *)a3);
  v85 = (int)(v14 + v16);
  LOBYTE(v56) = 0;
  if ( *((_DWORD *)v51 + 1) != 0x80000000 )
    _InterlockedIncrement((volatile signed __int32 *)v51 + 1);
  v57 = v51;
  v55 = Ofc::CProxyPtrImpl::CheckedStrongAddRef(v51);
  v17 = *((_QWORD *)v55 + 2);
  if ( v17 )
  {
    LOBYTE(v56) = (*(_BYTE *)(v17 + 545) & 2) != 0;
    *(_BYTE *)(v17 + 545) |= 2u;
  }
  Ofc::CProxyPtrImpl::DtorStrongRelease(&v55);
  v58 = Ofc::CProxyPtrImpl::CheckedStrongAddRef(v51);
  Art::ViewInfoRestorer::ViewInfoRestorer(&v90, &v58, v80);
  Ofc::CProxyPtrImpl::DtorStrongRelease(&v58);
  v18 = Ofc::CProxyPtrImpl::GetChecked(v51);
  v19 = (struct Ofc::CProxyPtrImpl *)v62;
  if ( *((_BYTE *)this + 36) )
    v19 = 0;
  v55 = v19;
  CodeMarker(8853);
  v20 = *((_QWORD *)v18 + 26);
  v21 = v20 & 2;
  LODWORD(v54) = (*((_DWORD *)v18 + 52) & 2) != 0 ? 8 : -1;
  v22 = 8 * (v20 & 1);
  *(_QWORD *)&v23 = *(_OWORD *)&_mm_unpackhi_pd((__m128d)0LL, (__m128d)0LL);
  v77 = &Gfx::InkStrokeCollectionCachingStateRestorer::`vftable';
  v24 = Gfx::IInkStrokeCollection::FIsCachingEnabledForCurrentThread();
  v78 = v24;
  if ( !Art::s_pHost )
  {
    CrashWithRecovery(0x1E44D300u, 0);
LABEL_41:
    Art::ViewInfoRestorer::~ViewInfoRestorer(&v90);
    v53 = Ofc::CProxyPtrImpl::CheckedStrongAddRef(v57);
    v48 = *((_QWORD *)v53 + 2);
    if ( v48 )
      *(_BYTE *)(v48 + 545) = *(_BYTE *)(v48 + 545) & 0xFD | (2 * (v56 & 1));
    Ofc::CProxyPtrImpl::DtorStrongRelease(&v53);
    Ofc::CProxyPtrImpl::DtorWeakRelease(&v57);
    Mso::TCntPtr<Art::Resource>::Clear(v87);
    Ofc::CProxyPtrImpl::DtorStrongRelease(v86);
    Ofc::CProxyPtrImpl::DtorWeakRelease(v82);
    Ofc::CProxyPtrImpl::DtorStrongRelease(&v81);
    if ( v12 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL))(v12);
    goto LABEL_45;
  }
  if ( (*(unsigned __int8 (__fastcall **)(struct Art::IAppHost *, __int64))(*(_QWORD *)Art::s_pHost + 200LL))(
         Art::s_pHost,
         119) )
  {
    v49 = *((_QWORD *)v18 + 26);
    if ( (v49 & 8) != 0 && ((v49 & 0x4000000) == 0 || (v49 & 0x20000) != 0) )
      Gfx::IInkStrokeCollection::ToggleCachingForCurrentThread(0);
  }
  Gfx::DefaultQualityPolicy::Get();
  v25 = *((_DWORD *)v18 + 50);
  v88 = &Art::RenderOptionsBase::`vftable';
  v89 = v25;
  v53 = (struct Ofc::CProxyPtrImpl *)*((_QWORD *)v18 + 12);
  v26 = &v88;
  if ( *((_QWORD *)v18 + 11) )
    v26 = (void ***)*((_QWORD *)v18 + 11);
  v61 = *((_QWORD *)v18 + 10);
  v27 = *((_QWORD *)v18 + 9);
  if ( !v27 )
    v27 = Gfx::DefaultQualityPolicy::Get();
  v75[0] = v27;
  v75[1] = v61;
  v75[2] = v60;
  v75[3] = v26;
  v75[4] = v53;
  if ( v21 || v22 )
  {
    v71 = &Gfx::ShapeFlagsFilter::`vftable';
    v72 = (int)v54;
    v73 = v22;
    v74 = v55;
    v28 = (__int64 *)*((_QWORD *)v18 + 47);
    v29 = (*(__int64 (__fastcall **)(__int64 *))(*v28 + 152))(v28);
    v30 = (struct Ofc::CProxyPtrImpl *)&v71;
  }
  else
  {
    v28 = (__int64 *)*((_QWORD *)v18 + 47);
    v29 = (*(__int64 (__fastcall **)(__int64 *))(*v28 + 152))(v28);
    v30 = v55;
  }
  v31 = *(double *)(v29 + 40);
  v32 = *(double *)(v29 + 24);
  v33 = *(double *)(v29 + 8);
  v34 = *(double *)(v29 + 32) * 0.0 + v31;
  v35 = *(double *)(v29 + 16) * 0.0 + v32;
  v36 = *(double *)v29 * 0.0 + v33;
  v37 = v32 * 0.0 + *(double *)(v29 + 16);
  v38 = v33 * 0.0 + *(double *)v29;
  *(double *)&v63[4] = v31 * 0.0 + *(double *)(v29 + 32) + 0.0;
  *(double *)&v63[3] = v35;
  *(double *)&v63[2] = v37;
  *(double *)&v63[1] = v36;
  *(double *)v63 = v38;
  *(double *)&v63[5] = v34 + v23;
  v64 = *(_DWORD *)(v29 + 48);
  v65 = *(_DWORD *)(v29 + 52);
  v66 = *(_OWORD *)(v29 + 56);
  v39 = *(double *)(v29 + 80) - v23;
  v67 = *(double *)(v29 + 72) - 0.0;
  v68 = v39;
  v69 = *(_OWORD *)(v29 + 88);
  v40 = *(_OWORD *)(v29 + 104);
  v41 = (__int64)v59;
  v42 = *v28;
  v70 = v40;
  v43 = (*(__int64 (__fastcall **)(__int64 *, struct Gfx::ITarget *, _QWORD *, _QWORD *, struct Ofc::CProxyPtrImpl *, __int64, _BYTE))(v42 + 248))(
          v28,
          v59,
          v63,
          v75,
          v30,
          v12,
          0);
  if ( v24 != (unsigned __int8)Gfx::IInkStrokeCollection::FIsCachingEnabledForCurrentThread() )
    Gfx::IInkStrokeCollection::ToggleCachingForCurrentThread(v24);
  CodeMarker(8854);
  if ( !v43 )
    goto LABEL_41;
  v44 = v62;
  if ( *((_BYTE *)this + 36) )
    v44 = 0;
  sub_18029F48C(v41, (__int64)&v51, &v52, v44, v60, v12);
  v45 = (Art::View *)*((_QWORD *)v90 + 2);
  if ( v45 )
    Art::View::SetViewInfoImpl(v45);
  Art::View::Info::~Info((Art::View::Info *)v91);
  Ofc::CProxyPtrImpl::DtorStrongRelease(&v90);
  v53 = Ofc::CProxyPtrImpl::CheckedStrongAddRef(v57);
  v46 = *((_QWORD *)v53 + 2);
  if ( v46 )
    *(_BYTE *)(v46 + 545) = *(_BYTE *)(v46 + 545) & 0xFD | (2 * (v56 & 1));
  Ofc::CProxyPtrImpl::DtorStrongRelease(&v53);
  Ofc::CProxyPtrImpl::DtorWeakRelease(&v57);
  Mso::TCntPtr<Art::Resource>::Clear(v87);
  Ofc::CProxyPtrImpl::DtorStrongRelease(v86);
  Ofc::CProxyPtrImpl::DtorWeakRelease(v82);
  Ofc::CProxyPtrImpl::DtorStrongRelease(&v81);
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL))(v12);
  Ofc::CProxyPtrImpl::DtorStrongRelease(&v51);
  Ofc::CProxyPtrImpl::DtorStrongRelease(&v52);
  return 1;
}

```

## disassembly

```asm
0x18029fad0  mov     rax, rsp
0x18029fad3  push    rbp
0x18029fad4  push    rbx
0x18029fad5  push    rsi
0x18029fad6  push    rdi
0x18029fad7  push    r12
0x18029fad9  push    r13
0x18029fadb  push    r14
0x18029fadd  push    r15
0x18029fadf  lea     rbp, [rax-2E8h]
0x18029fae6  sub     rsp, 3A8h
0x18029faed  movaps  xmmword ptr [rax-58h], xmm6
0x18029faf1  movaps  xmmword ptr [rax-68h], xmm7
0x18029faf5  movaps  xmmword ptr [rax-78h], xmm8
0x18029fafa  mov     rax, cs:__security_cookie
0x18029fb01  xor     rax, rsp
0x18029fb04  mov     [rbp+2E0h+var_78], rax
0x18029fb0b  mov     [rbp+2E0h+var_350], r9
0x18029fb0f  mov     rdi, r8
0x18029fb12  mov     [rbp+2E0h+var_358], rdx
0x18029fb16  mov     r13, rcx
0x18029fb19  mov     rcx, [rcx+18h]; struct Ofc::CProxyPtrImpl *
0x18029fb1d  call    ?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAddRef(Ofc::CProxyPtrImpl *)
0x18029fb22  mov     [rsp+3E0h+var_390], rax
0x18029fb27  xor     r14d, r14d
0x18029fb2a  cmp     [rax+10h], r14
0x18029fb2e  jz      loc_1802A01C4
0x18029fb34  mov     rcx, rax; this
0x18029fb37  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x18029fb3c  mov     rcx, [rax+0A0h]; struct Ofc::CProxyPtrImpl *
0x18029fb43  call    ?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAddRef(Ofc::CProxyPtrImpl *)
0x18029fb48  mov     [rsp+3E0h+var_380], rax
0x18029fb4d  mov     rcx, [rax+10h]
0x18029fb51  test    rcx, rcx
0x18029fb54  jz      loc_1802A020F
0x18029fb5a  mov     rax, [rcx]
0x18029fb5d  mov     rax, [rax+20h]
0x18029fb61  call    cs:__guard_dispatch_icall_fptr
0x18029fb67  mov     rbx, rax
0x18029fb6a  lea     rcx, [rsp+3E0h+var_380]; struct Ofc::CProxyPtrImpl **
0x18029fb6f  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x18029fb74  nop
0x18029fb75  mov     rcx, [rbx]; struct Ofc::CProxyPtrImpl *
0x18029fb78  call    ?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAddRef(Ofc::CProxyPtrImpl *)
0x18029fb7d  mov     [rsp+3E0h+var_3A0], rax
0x18029fb82  cmp     [rax+10h], r14
0x18029fb86  jz      loc_1802A01FF
0x18029fb8c  mov     rcx, [rsp+3E0h+var_390]; this
0x18029fb91  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x18029fb96  lea     rcx, ??_7ViewElementShapeFilter@Art@@6B@; const Art::ViewElementShapeFilter::`vftable'
0x18029fb9d  mov     [rbp+2E0h+var_340], rcx
0x18029fba1  mov     [rbp+2E0h+var_338], rax
0x18029fba5  mov     rcx, [rsp+3E0h+var_390]; this
0x18029fbaa  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x18029fbaf  mov     rbx, [rax+90h]
0x18029fbb6  mov     [rbp+2E0h+var_270], rbx
0x18029fbba  test    rbx, rbx
0x18029fbbd  jz      short loc_18029FBD0
0x18029fbbf  mov     rax, [rbx]
0x18029fbc2  mov     rcx, rbx
0x18029fbc5  mov     rax, [rax]
0x18029fbc8  call    cs:__guard_dispatch_icall_fptr
0x18029fbce  nop
0x18029fbcf  nop
0x18029fbd0  lea     rcx, [rbp+2E0h+var_220]; this
0x18029fbd7  call    ??0Info@View@Art@@QEAA@XZ; Art::View::Info::Info(void)
0x18029fbdc  mov     rcx, [rsp+3E0h+var_3A0]; this
0x18029fbe1  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x18029fbe6  lea     rdx, [rax+28h]
0x18029fbea  lea     rcx, [rbp+2E0h+var_220]
0x18029fbf1  call    ??4Info@View@Art@@QEAAAEAU012@AEBU012@@Z; Art::View::Info::operator=(Art::View::Info const &)
0x18029fbf6  movdqa  xmm0, cs:__xmm@7fffffff7fffffff8000000080000000
0x18029fbfe  movdqu  [rbp+2E0h+var_268], xmm0
0x18029fc03  lea     rdx, [rbp+2E0h+var_268]
0x18029fc07  lea     rcx, [rbp+2E0h+var_248]
0x18029fc0e  call    cs:__imp_??0SpriteClipRectCachingPolicy@Gfx@@QEAA@AEBU?$TRect@V?$TUnits@HUDevicePixels@Math@@@Math@@@Math@@@Z; Gfx::SpriteClipRectCachingPolicy::SpriteClipRectCachingPolicy(Math::TRect<Math::TUnits<int,Math::DevicePixels>> const &)
0x18029fc14  mov     rcx, [rbp+2E0h+var_1F8]
0x18029fc1b  test    rcx, rcx
0x18029fc1e  jz      loc_1802A01D1
0x18029fc24  movsd   xmm1, qword ptr [rdi+8]
0x18029fc29  xorps   xmm6, xmm6
0x18029fc2c  movsd   xmm2, cs:__real@bfe0000000000000
0x18029fc34  movsd   xmm0, cs:__real@3fe0000000000000
0x18029fc3c  comisd  xmm1, xmm6
0x18029fc40  jb      loc_1802A01EF
0x18029fc46  movaps  xmm3, xmm0
0x18029fc49  movsd   xmm4, qword ptr [rdi]
0x18029fc4d  comisd  xmm4, xmm6
0x18029fc51  jb      loc_1802A01F7
0x18029fc57  addsd   xmm0, xmm4
0x18029fc5b  cvttsd2si ecx, xmm0
0x18029fc5f  addsd   xmm1, xmm3
0x18029fc63  cvttsd2si eax, xmm1
0x18029fc67  mov     [rbp+2E0h+var_190], ecx
0x18029fc6d  mov     [rbp+2E0h+var_18C], eax
0x18029fc73  mov     byte ptr [rsp+3E0h+var_370], r14b
0x18029fc78  mov     rcx, [rsp+3E0h+var_3A0]; struct Ofc::CProxyPtrImpl *
0x18029fc7d  mov     eax, [rcx+4]
0x18029fc80  cmp     eax, 80000000h
0x18029fc85  jnz     loc_1802A0225
0x18029fc8b  mov     [rsp+3E0h+var_368], rcx
0x18029fc90  call    ?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAddRef(Ofc::CProxyPtrImpl *)
0x18029fc95  mov     [rsp+3E0h+var_378], rax
0x18029fc9a  mov     rcx, [rax+10h]
0x18029fc9e  test    rcx, rcx
0x18029fca1  jz      short loc_18029FCB8
0x18029fca3  mov     al, [rcx+221h]
0x18029fca9  shr     al, 1
0x18029fcab  and     al, 1
0x18029fcad  mov     byte ptr [rsp+3E0h+var_370], al
0x18029fcb1  or      byte ptr [rcx+221h], 2
0x18029fcb8  lea     rcx, [rsp+3E0h+var_378]; struct Ofc::CProxyPtrImpl **
0x18029fcbd  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x18029fcc2  mov     rcx, [rsp+3E0h+var_3A0]; struct Ofc::CProxyPtrImpl *
0x18029fcc7  call    ?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAddRef(Ofc::CProxyPtrImpl *)
0x18029fccc  mov     [rbp+2E0h+var_360], rax
0x18029fcd0  lea     r8, [rbp+2E0h+var_220]
0x18029fcd7  lea     rdx, [rbp+2E0h+var_360]
0x18029fcdb  lea     rcx, [rbp+2E0h+var_150]
0x18029fce2  call    ??0ViewInfoRestorer@Art@@QEAA@AEBV?$TSharedPtr@VView@Art@@@Ofc@@AEBUInfo@View@1@@Z; Art::ViewInfoRestorer::ViewInfoRestorer(Ofc::TSharedPtr<Art::View> const &,Art::View::Info const &)
0x18029fce7  lea     rcx, [rbp+2E0h+var_360]; struct Ofc::CProxyPtrImpl **
0x18029fceb  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x18029fcf0  mov     rcx, [rsp+3E0h+var_3A0]; this
0x18029fcf5  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x18029fcfa  mov     rdi, rax
0x18029fcfd  lea     rax, [rbp+2E0h+var_340]
0x18029fd01  cmp     [r13+24h], r14b
0x18029fd05  cmovnz  rax, r14
0x18029fd09  mov     [rsp+3E0h+var_378], rax
0x18029fd0e  xorps   xmm7, xmm7
0x18029fd11  mov     ecx, 2295h
0x18029fd16  call    CodeMarker
0x18029fd1b  mov     rsi, [rdi+0D0h]
0x18029fd22  mov     r15, rsi
0x18029fd25  and     r15d, 2
0x18029fd29  mov     eax, r15d
0x18029fd2c  neg     rax
0x18029fd2f  sbb     eax, eax
0x18029fd31  and     eax, 9
0x18029fd34  dec     eax
0x18029fd36  mov     dword ptr [rsp+3E0h+var_380], eax
0x18029fd3a  and     esi, 1
0x18029fd3d  shl     esi, 3
0x18029fd40  xorps   xmm8, xmm8
0x18029fd44  unpckhpd xmm8, xmm7
0x18029fd49  lea     rax, ??_7InkStrokeCollectionCachingStateRestorer@Gfx@@6B@; const Gfx::InkStrokeCollectionCachingStateRestorer::`vftable'
0x18029fd50  mov     [rbp+2E0h+var_258], rax
0x18029fd57  call    cs:__imp_?FIsCachingEnabledForCurrentThread@IInkStrokeCollection@Gfx@@SA_NXZ; Gfx::IInkStrokeCollection::FIsCachingEnabledForCurrentThread(void)
0x18029fd5d  mov     r12b, al
0x18029fd60  mov     [rbp+2E0h+var_250], al
0x18029fd66  mov     rcx, cs:?s_pHost@Art@@3PEAVIAppHost@1@EA; Art::IAppHost * Art::s_pHost
0x18029fd6d  test    rcx, rcx
0x18029fd70  jz      loc_1802A00C9
0x18029fd76  mov     rax, [rcx]
0x18029fd79  mov     edx, 77h ; 'w'
0x18029fd7e  mov     rax, [rax+0C8h]
0x18029fd85  call    cs:__guard_dispatch_icall_fptr
0x18029fd8b  test    al, al
0x18029fd8d  jnz     loc_1802A0196
0x18029fd93  call    cs:__imp_?Get@DefaultQualityPolicy@Gfx@@SAAEBV12@XZ; Gfx::DefaultQualityPolicy::Get(void)
0x18029fd99  mov     eax, [rdi+0C8h]
0x18029fd9f  lea     rcx, ??_7RenderOptionsBase@Art@@6B@; const Art::RenderOptionsBase::`vftable'
0x18029fda6  mov     [rbp+2E0h+var_160], rcx
0x18029fdad  xor     ecx, ecx
0x18029fdaf  mov     [rbp+2E0h+var_158], eax
0x18029fdb5  mov     rax, [rdi+60h]
0x18029fdb9  mov     [rsp+3E0h+var_388], rax
0x18029fdbe  lea     r14, [rbp+2E0h+var_160]
0x18029fdc5  cmp     [rdi+58h], rcx
0x18029fdc9  cmovnz  r14, [rdi+58h]
0x18029fdce  mov     rax, [rdi+50h]
0x18029fdd2  mov     [rbp+2E0h+var_348], rax
0x18029fdd6  mov     rax, [rdi+48h]
0x18029fdda  test    rax, rax
0x18029fddd  jnz     short loc_18029FDE5
0x18029fddf  call    cs:__imp_?Get@DefaultQualityPolicy@Gfx@@SAAEBV12@XZ; Gfx::DefaultQualityPolicy::Get(void)
0x18029fde5  mov     [rbp+2E0h+var_298], rax
0x18029fde9  mov     rax, [rbp+2E0h+var_348]
0x18029fded  mov     [rbp+2E0h+var_290], rax
0x18029fdf1  mov     rax, [rbp+2E0h+var_350]
0x18029fdf5  mov     [rbp+2E0h+var_288], rax
0x18029fdf9  mov     [rbp+2E0h+var_280], r14
0x18029fdfd  mov     rax, [rsp+3E0h+var_388]
0x18029fe02  mov     [rbp+2E0h+var_278], rax
0x18029fe06  xor     r14d, r14d
0x18029fe09  test    r15, r15
0x18029fe0c  jnz     short loc_18029FE33
0x18029fe0e  test    esi, esi
0x18029fe10  jnz     short loc_18029FE33
0x18029fe12  mov     rdi, [rdi+178h]
0x18029fe19  mov     rax, [rdi]
0x18029fe1c  mov     rcx, rdi
0x18029fe1f  mov     rax, [rax+98h]
0x18029fe26  call    cs:__guard_dispatch_icall_fptr
0x18029fe2c  mov     rcx, [rsp+3E0h+var_378]
0x18029fe31  jmp     short loc_18029FE6F
0x18029fe33  lea     rax, ??_7ShapeFlagsFilter@Gfx@@6B@; const Gfx::ShapeFlagsFilter::`vftable'
0x18029fe3a  mov     [rbp+2E0h+var_2B0], rax
0x18029fe3e  mov     eax, dword ptr [rsp+3E0h+var_380]
0x18029fe42  mov     [rbp+2E0h+var_2A8], eax
0x18029fe45  mov     [rbp+2E0h+var_2A4], esi
0x18029fe48  mov     rcx, [rsp+3E0h+var_378]
0x18029fe4d  mov     [rbp+2E0h+var_2A0], rcx
0x18029fe51  mov     rdi, [rdi+178h]
0x18029fe58  mov     rax, [rdi]
0x18029fe5b  mov     rcx, rdi
0x18029fe5e  mov     rax, [rax+98h]
0x18029fe65  call    cs:__guard_dispatch_icall_fptr
0x18029fe6b  lea     rcx, [rbp+2E0h+var_2B0]
0x18029fe6f  movsd   xmm4, qword ptr [rax+20h]
0x18029fe74  movsd   xmm2, qword ptr [rax+10h]
0x18029fe79  movsd   xmm0, qword ptr [rax]
0x18029fe7d  movsd   xmm5, qword ptr [rax+28h]
0x18029fe82  mulsd   xmm4, xmm6
0x18029fe86  movsd   xmm3, qword ptr [rax+18h]
0x18029fe8b  mulsd   xmm2, xmm6
0x18029fe8f  movsd   xmm1, qword ptr [rax+8]
0x18029fe94  mulsd   xmm0, xmm6
0x18029fe98  addsd   xmm4, xmm5
0x18029fe9c  addsd   xmm2, xmm3
0x18029fea0  addsd   xmm0, xmm1
0x18029fea4  mulsd   xmm5, xmm6
0x18029fea8  mulsd   xmm3, xmm6
0x18029feac  mulsd   xmm1, xmm6
0x18029feb0  addsd   xmm5, qword ptr [rax+20h]
0x18029feb5  addsd   xmm3, qword ptr [rax+10h]
0x18029feba  addsd   xmm1, qword ptr [rax]
0x18029febe  addsd   xmm5, xmm7
0x18029fec2  movsd   [rbp+2E0h+var_310], xmm5
0x18029fec7  movsd   [rbp+2E0h+var_318], xmm2
0x18029fecc  movsd   [rbp+2E0h+var_320], xmm3
0x18029fed1  movsd   [rbp+2E0h+var_328], xmm0
0x18029fed6  movsd   [rbp+2E0h+var_330], xmm1
0x18029fedb  addsd   xmm4, xmm8
0x18029fee0  movsd   [rbp+2E0h+var_308], xmm4
0x18029fee5  movss   xmm0, dword ptr [rax+30h]
0x18029feea  movss   [rbp+2E0h+var_300], xmm0
0x18029feef  movss   xmm1, dword ptr [rax+34h]
0x18029fef4  movss   [rbp+2E0h+var_2FC], xmm1
0x18029fef9  movups  xmm0, xmmword ptr [rax+38h]
0x18029fefd  movdqu  [rbp+2E0h+var_2F8], xmm0
0x18029ff02  movsd   xmm0, qword ptr [rax+48h]
0x18029ff07  movsd   xmm1, qword ptr [rax+50h]
0x18029ff0c  subsd   xmm0, xmm7
0x18029ff10  subsd   xmm1, xmm8
0x18029ff15  movsd   [rbp+2E0h+var_2E8], xmm0
0x18029ff1a  movsd   [rbp+2E0h+var_2E0], xmm1
0x18029ff1f  movups  xmm0, xmmword ptr [rax+58h]
0x18029ff23  mov     [rsp+3E0h+var_3B0], r14b
0x18029ff28  movdqu  [rbp+2E0h+var_2D8], xmm0
0x18029ff2d  mov     qword ptr [rsp+3E0h+var_3B8], rbx
0x18029ff32  movups  xmm1, xmmword ptr [rax+68h]
0x18029ff36  mov     rsi, [rbp+2E0h+var_358]
0x18029ff3a  mov     [rsp+3E0h+var_3C0], rcx
0x18029ff3f  mov     rax, [rdi]
0x18029ff42  movdqu  [rbp+2E0h+var_2C8], xmm1
0x18029ff47  lea     r9, [rbp+2E0h+var_298]
0x18029ff4b  lea     r8, [rbp+2E0h+var_330]
0x18029ff4f  mov     rdx, rsi
0x18029ff52  mov     rcx, rdi
0x18029ff55  mov     rax, [rax+0F8h]
0x18029ff5c  call    cs:__guard_dispatch_icall_fptr
0x18029ff62  mov     dil, al
0x18029ff65  call    cs:__imp_?FIsCachingEnabledForCurrentThread@IInkStrokeCollection@Gfx@@SA_NXZ; Gfx::IInkStrokeCollection::FIsCachingEnabledForCurrentThread(void)
0x18029ff6b  cmp     r12b, al
0x18029ff6e  jz      short loc_18029FF7A
0x18029ff70  mov     cl, r12b
0x18029ff73  call    cs:__imp_?ToggleCachingForCurrentThread@IInkStrokeCollection@Gfx@@SAX_N@Z; Gfx::IInkStrokeCollection::ToggleCachingForCurrentThread(bool)
0x18029ff79  nop
0x18029ff7a  mov     ecx, 2296h
0x18029ff7f  call    CodeMarker
0x18029ff84  test    dil, dil
0x18029ff87  jz      loc_1802A00D7
0x18029ff8d  lea     r9, [rbp+2E0h+var_340]
0x18029ff91  cmp     [r13+24h], r14b
0x18029ff95  cmovnz  r9, r14
0x18029ff99  mov     qword ptr [rsp+3E0h+var_3B8], rbx
0x18029ff9e  mov     rax, [rbp+2E0h+var_350]
0x18029ffa2  mov     [rsp+3E0h+var_3C0], rax
0x18029ffa7  lea     r8, [rsp+3E0h+var_390]
0x18029ffac  lea     rdx, [rsp+3E0h+var_3A0]
0x18029ffb1  mov     rcx, rsi
0x18029ffb4  call    sub_18029F48C
0x18029ffb9  mov     rax, [rbp+2E0h+var_150]
0x18029ffc0  mov     rcx, [rax+10h]; this
0x18029ffc4  test    rcx, rcx
0x18029ffc7  jz      short loc_18029FFDA
0x18029ffc9  lea     r8, [rbp+2E0h+var_148]
0x18029ffd0  lea     rdx, [rsp+3E0h+var_398]
0x18029ffd5  call    ?SetViewInfoImpl@View@Art@@AEAA?AV?$TBitset@E$00@Ofc@@AEBUInfo@12@@Z; Art::View::SetViewInfoImpl(Art::View::Info const &)
0x18029ffda  lea     rcx, [rbp+2E0h+var_148]; this
0x18029ffe1  call    ??1Info@View@Art@@QEAA@XZ; Art::View::Info::~Info(void)
0x18029ffe6  lea     rcx, [rbp+2E0h+var_150]; struct Ofc::CProxyPtrImpl **
0x18029ffed  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x18029fff2  mov     rcx, [rsp+3E0h+var_368]; struct Ofc::CProxyPtrImpl *
0x18029fff7  call    ?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAddRef(Ofc::CProxyPtrImpl *)
0x18029fffc  mov     [rsp+3E0h+var_388], rax
0x1802a0001  mov     rdx, [rax+10h]
0x1802a0005  test    rdx, rdx
0x1802a0008  jz      short loc_1802A0023
  ... truncated ...
```
