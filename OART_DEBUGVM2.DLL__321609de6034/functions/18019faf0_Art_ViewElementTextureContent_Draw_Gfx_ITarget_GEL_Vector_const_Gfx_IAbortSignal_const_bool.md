# Art::ViewElementTextureContent::Draw(Gfx::ITarget &,GEL::Vector const &,Gfx::IAbortSignal const *,bool)

- ea: `0x18019faf0`
- end: `0x1801a06bb`
- name: `?Draw@ViewElementTextureContent@Art@@UEAA_NAEAUITarget@Gfx@@AEBUVector@GEL@@PEBUIAbortSignal@4@_N@Z`
- size: `3019`
- prototype: `bool __fastcall(Art::ViewElementTextureContent *__hidden this, struct Gfx::ITarget *, const struct GEL::Vector *, const struct Gfx::IAbortSignal *, bool)`
- caller_count: `0`
- callee_count: `17`
- tags: `registry_config`

## callees

- `0x1800d1790`
- `0x180105200`
- `0x180113048`
- `0x180113510`
- `0x180144500`
- `0x18019faf0`
- `0x1801abdbc`
- `0x1802778d0`
- `0x180278de0`
- `0x180279000`
- `0x180279010`
- `0x180279030`
- `0x180279050`
- `0x1806bc2a8`
- `0x1806bc4f0`
- `0x1806bc6a8`
- `0x1806d19bc`

## import_xrefs

- `gfx!??0SpriteClipRectCachingPolicy@Gfx@@QEAA@AEBU?$TRect@V?$TUnits@HUDevicePixels@Math@@@Math@@@Math@@@Z` at `0x1801a0077`
- `gfx!??0SpriteClipRectCachingPolicy@Gfx@@QEAA@AEBU?$TRect@V?$TUnits@HUDevicePixels@Math@@@Math@@@Math@@@Z` at `0x1801a0077`
- `gfx!?ToggleCachingForCurrentThread@IInkStrokeCollection@Gfx@@SAX_N@Z` at `0x1801a056c`
- `gfx!?ToggleCachingForCurrentThread@IInkStrokeCollection@Gfx@@SAX_N@Z` at `0x1801a0654`
- `gfx!?ToggleCachingForCurrentThread@IInkStrokeCollection@Gfx@@SAX_N@Z` at `0x1801a056c`
- `gfx!?ToggleCachingForCurrentThread@IInkStrokeCollection@Gfx@@SAX_N@Z` at `0x1801a0654`
- `gfx!?FIsCachingEnabledForCurrentThread@IInkStrokeCollection@Gfx@@SA_NXZ` at `0x1801a01bb`
- `gfx!?FIsCachingEnabledForCurrentThread@IInkStrokeCollection@Gfx@@SA_NXZ` at `0x1801a03ed`
- `gfx!?FIsCachingEnabledForCurrentThread@IInkStrokeCollection@Gfx@@SA_NXZ` at `0x1801a01bb`
- `gfx!?FIsCachingEnabledForCurrentThread@IInkStrokeCollection@Gfx@@SA_NXZ` at `0x1801a03ed`
- `gfx!?Get@DefaultQualityPolicy@Gfx@@SAAEBV12@XZ` at `0x1801a01f4`
- `gfx!?Get@DefaultQualityPolicy@Gfx@@SAAEBV12@XZ` at `0x1801a0240`
- `gfx!?Get@DefaultQualityPolicy@Gfx@@SAAEBV12@XZ` at `0x1801a01f4`
- `gfx!?Get@DefaultQualityPolicy@Gfx@@SAAEBV12@XZ` at `0x1801a0240`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1801a0664`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1801a0699`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1801a0664`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1801a0699`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1801a0562`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1801a0562`

## pseudocode

```c
char __fastcall Art::ViewElementTextureContent::Draw(
        struct Ofc::CProxyPtrImpl **this,
        struct Gfx::ITarget *a2,
        const struct GEL::Vector *a3,
        const struct Gfx::IAbortSignal *a4,
        bool a5)
{
  _QWORD *v5; // r14
  struct Ofc::CProxyPtrImpl *v8; // rax
  struct Ofc::CProxyPtrImpl **Checked; // rax
  __int64 v10; // rcx
  struct Ofc::CProxyPtrImpl **v11; // rbx
  void *v12; // rax
  __int64 v13; // rbx
  struct Ofc::CProxyPtrImpl **v14; // rax
  __int64 v15; // rdx
  __int64 v16; // rdx
  __int64 v17; // rdx
  struct Ofc::CProxyPtrImpl *v18; // r8
  int v19; // r9d
  int v20; // r10d
  __int64 v21; // r11
  char v22; // si
  void (__fastcall ***v23)(_QWORD, __int64, struct Ofc::CProxyPtrImpl *); // rcx
  void (__fastcall ***v24)(_QWORD, __int64, struct Ofc::CProxyPtrImpl *); // rdx
  struct Ofc::CProxyPtrImpl *v25; // rcx
  struct Ofc::CProxyPtrImpl *v26; // rcx
  double v27; // rcx
  double v28; // rcx
  __int64 v29; // rcx
  __int64 v30; // rcx
  double v31; // rcx
  int v32; // xmm2_4
  int v33; // xmm3_4
  __int128 v34; // xmm1
  struct Ofc::CProxyPtrImpl *v35; // rax
  __int64 v36; // rax
  double v37; // xmm1_8
  double v38; // xmm0_8
  double v39; // xmm3_8
  __int64 v40; // rcx
  __int64 *v41; // rdi
  struct Ofc::CProxyPtrImpl *v42; // rax
  __int64 v43; // r15
  int v44; // r13d
  __int64 v45; // rsi
  double v46; // xmm8_8
  char v47; // r12
  int v48; // eax
  void ***v49; // r14
  __int64 v50; // rax
  __int64 v51; // rax
  struct Ofc::CProxyPtrImpl *v52; // rcx
  double v53; // xmm5_8
  double v54; // xmm3_8
  double v55; // xmm1_8
  double v56; // xmm4_8
  double v57; // xmm2_8
  double v58; // xmm0_8
  double v59; // xmm3_8
  double v60; // xmm1_8
  double v61; // xmm1_8
  __int128 v62; // xmm1
  __int64 v63; // rax
  _QWORD *v64; // r9
  Art::View *v65; // rcx
  __int64 v66; // rdx
  void (__fastcall ***v67)(_QWORD, _QWORD, struct Ofc::CProxyPtrImpl *); // rcx
  __int64 v69; // rdx
  __int64 v70; // rax
  double v71; // rax
  struct Ofc::CProxyPtrImpl *v72; // [rsp+48h] [rbp-C0h] BYREF
  struct Ofc::CProxyPtrImpl *v73; // [rsp+50h] [rbp-B8h] BYREF
  Ofc::CProxyPtrImpl *v74; // [rsp+60h] [rbp-A8h] BYREF
  struct Ofc::CProxyPtrImpl *v75; // [rsp+68h] [rbp-A0h] BYREF
  struct Ofc::CProxyPtrImpl *v76; // [rsp+70h] [rbp-98h] BYREF
  __int64 v77; // [rsp+78h] [rbp-90h]
  struct Ofc::CProxyPtrImpl *v78; // [rsp+80h] [rbp-88h] BYREF
  struct Ofc::CProxyPtrImpl *v79; // [rsp+88h] [rbp-80h] BYREF
  struct Gfx::ITarget *v80; // [rsp+90h] [rbp-78h]
  const struct Gfx::IAbortSignal *v81; // [rsp+98h] [rbp-70h]
  __int64 v82; // [rsp+A0h] [rbp-68h]
  _QWORD v83[2]; // [rsp+A8h] [rbp-60h] BYREF
  void **v84; // [rsp+B8h] [rbp-50h] BYREF
  int v85; // [rsp+C0h] [rbp-48h]
  int v86; // [rsp+C4h] [rbp-44h]
  struct Ofc::CProxyPtrImpl *v87; // [rsp+C8h] [rbp-40h]
  _QWORD v88[6]; // [rsp+D0h] [rbp-38h] BYREF
  __m128i si128; // [rsp+100h] [rbp-8h] BYREF
  void **v90; // [rsp+110h] [rbp+8h]
  char v91; // [rsp+118h] [rbp+10h]
  _BYTE v92[40]; // [rsp+120h] [rbp+18h] BYREF
  char v93[8]; // [rsp+148h] [rbp+40h] BYREF
  struct Ofc::CProxyPtrImpl *v94; // [rsp+150h] [rbp+48h] BYREF
  struct Ofc::CProxyPtrImpl *v95; // [rsp+158h] [rbp+50h] BYREF
  double v96; // [rsp+160h] [rbp+58h]
  double v97; // [rsp+168h] [rbp+60h]
  double v98; // [rsp+170h] [rbp+68h]
  __int64 v99; // [rsp+178h] [rbp+70h]
  __int64 v100; // [rsp+180h] [rbp+78h]
  int v101; // [rsp+188h] [rbp+80h]
  int v102; // [rsp+18Ch] [rbp+84h]
  int v103; // [rsp+190h] [rbp+88h]
  int v104; // [rsp+194h] [rbp+8Ch]
  int v105; // [rsp+198h] [rbp+90h]
  int v106; // [rsp+19Ch] [rbp+94h]
  int v107; // [rsp+1A0h] [rbp+98h]
  int v108; // [rsp+1A4h] [rbp+9Ch]
  int v109; // [rsp+1C0h] [rbp+B8h]
  int v110; // [rsp+1C4h] [rbp+BCh]
  __int128 v111; // [rsp+1C8h] [rbp+C0h]
  struct Ofc::CProxyPtrImpl *v112; // [rsp+1D8h] [rbp+D0h]
  struct Ofc::CProxyPtrImpl *v113; // [rsp+1E0h] [rbp+D8h] BYREF
  int v114; // [rsp+1E8h] [rbp+E0h]
  int v115; // [rsp+1ECh] [rbp+E4h]
  __int64 v116; // [rsp+1F0h] [rbp+E8h]
  char v117; // [rsp+1F8h] [rbp+F0h]
  char v118; // [rsp+1F9h] [rbp+F1h]
  void (__fastcall ***v119)(_QWORD, __int64, struct Ofc::CProxyPtrImpl *); // [rsp+200h] [rbp+F8h] BYREF
  double v120; // [rsp+208h] [rbp+100h] BYREF
  struct Ofc::CProxyPtrImpl *v121; // [rsp+210h] [rbp+108h] BYREF
  struct Ofc::CProxyPtrImpl *v122; // [rsp+218h] [rbp+110h] BYREF
  double v123; // [rsp+220h] [rbp+118h]
  double v124; // [rsp+228h] [rbp+120h]
  double v125; // [rsp+230h] [rbp+128h]
  __int64 v126; // [rsp+238h] [rbp+130h]
  _BYTE v127[24]; // [rsp+240h] [rbp+138h]
  double v128; // [rsp+258h] [rbp+150h]
  __int128 v129; // [rsp+260h] [rbp+158h]
  __int128 v130; // [rsp+270h] [rbp+168h]
  int v131; // [rsp+280h] [rbp+178h]
  int v132; // [rsp+284h] [rbp+17Ch]
  __int128 v133; // [rsp+288h] [rbp+180h]
  __int64 v134; // [rsp+298h] [rbp+190h]
  struct Ofc::CProxyPtrImpl *v135; // [rsp+2A0h] [rbp+198h] BYREF
  __int64 v136; // [rsp+2A8h] [rbp+1A0h]
  __int64 v137; // [rsp+2B0h] [rbp+1A8h]
  char v138; // [rsp+2B8h] [rbp+1B0h]
  char v139; // [rsp+2B9h] [rbp+1B1h]
  void (__fastcall ***v140)(_QWORD, __int64, struct Ofc::CProxyPtrImpl *); // [rsp+2C0h] [rbp+1B8h]
  void **v141; // [rsp+2C8h] [rbp+1C0h] BYREF
  int v142; // [rsp+2D0h] [rbp+1C8h]
  struct Ofc::CProxyPtrImpl *v143; // [rsp+2D8h] [rbp+1D0h] BYREF
  char v144[208]; // [rsp+2E0h] [rbp+1D8h] BYREF

  v81 = a4;
  v80 = a2;
  v79 = (struct Ofc::CProxyPtrImpl *)this;
  v8 = Ofc::CProxyPtrImpl::CheckedStrongAddRef(this[3]);
  v74 = v8;
  if ( !*((_QWORD *)v8 + 2) )
  {
    MsoShipAssertTagProc(3741730);
    goto LABEL_50;
  }
  Checked = (struct Ofc::CProxyPtrImpl **)Ofc::CProxyPtrImpl::GetChecked(v8);
  v73 = Ofc::CProxyPtrImpl::CheckedStrongAddRef(Checked[20]);
  v10 = *((_QWORD *)v73 + 2);
  if ( v10 )
  {
    v11 = (struct Ofc::CProxyPtrImpl **)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 32LL))(v10);
    Ofc::CProxyPtrImpl::DtorStrongRelease(&v73);
  }
  else
  {
    Ofc::CProxyPtrImpl::DtorStrongRelease(&v73);
    v11 = (struct Ofc::CProxyPtrImpl **)&`Ofc::CProxyPtrImpl::GetSentinel'::`2'::s_pProxyPtrSentinel;
  }
  v72 = Ofc::CProxyPtrImpl::CheckedStrongAddRef(*v11);
  if ( !*((_QWORD *)v72 + 2) )
  {
    MsoShipAssertTagProc(3741731);
LABEL_49:
    Ofc::CProxyPtrImpl::DtorStrongRelease(&v72);
LABEL_50:
    Ofc::CProxyPtrImpl::DtorStrongRelease(&v74);
    return 0;
  }
  v12 = Ofc::CProxyPtrImpl::GetChecked(v74);
  v83[0] = &Art::ViewElementShapeFilter::`vftable';
  v83[1] = v12;
  v13 = *((_QWORD *)Ofc::CProxyPtrImpl::GetChecked(v74) + 18);
  v88[5] = v13;
  if ( v13 )
    (**(void (__fastcall ***)(__int64))v13)(v13);
  Art::View::Info::Info((Art::View::Info *)v93);
  v14 = (struct Ofc::CProxyPtrImpl **)Ofc::CProxyPtrImpl::GetChecked(v72);
  v120 = COERCE_DOUBLE(&Art::View::Info::`vftable');
  v121 = Ofc::CProxyPtrImpl::StrongAddRef(v14[6]);
  v122 = Ofc::CProxyPtrImpl::WeakAddRef(*(struct Ofc::CProxyPtrImpl **)(v15 + 56));
  v123 = *(double *)(v16 + 64);
  v124 = *(double *)(v16 + 72);
  v125 = *(double *)(v16 + 80);
  v126 = *(_QWORD *)(v16 + 88);
  *(_QWORD *)v127 = *(_QWORD *)(v16 + 96);
  *(_OWORD *)&v127[8] = *(_OWORD *)(v16 + 104);
  v128 = *(double *)(v16 + 120);
  *(_QWORD *)&v129 = *(_QWORD *)(v16 + 128);
  *((_QWORD *)&v129 + 1) = &v120;
  *(_QWORD *)&v130 = &v120;
  *((_QWORD *)&v130 + 1) = &v120;
  v131 = *(_DWORD *)(v16 + 160);
  v132 = *(_DWORD *)(v16 + 164);
  v133 = *(_OWORD *)(v16 + 168);
  v134 = *(_QWORD *)(v16 + 184);
  v18 = Ofc::CProxyPtrImpl::StrongAddRef(*(struct Ofc::CProxyPtrImpl **)(v16 + 192));
  v135 = v18;
  v136 = 0;
  v19 = *(_DWORD *)(v17 + 200);
  LODWORD(v136) = v19;
  v20 = *(_DWORD *)(v17 + 204);
  HIDWORD(v136) = v20;
  v21 = *(_QWORD *)(v17 + 208);
  v137 = v21;
  v22 = *(_BYTE *)(v17 + 216);
  v138 = v22;
  LOBYTE(v5) = *(_BYTE *)(v17 + 217);
  v139 = (char)v5;
  v23 = *(void (__fastcall ****)(_QWORD, __int64, struct Ofc::CProxyPtrImpl *))(v17 + 224);
  v140 = v23;
  if ( v23 )
  {
    (**v23)(v23, v17, v18);
    v23 = v140;
    LOBYTE(v5) = v139;
    v22 = v138;
    v21 = v137;
    v20 = HIDWORD(v136);
    v19 = v136;
    v18 = v135;
  }
  v24 = v119;
  v119 = v23;
  v140 = v24;
  v25 = v94;
  v94 = v121;
  v121 = v25;
  v26 = v95;
  v95 = v122;
  v122 = v26;
  v27 = v96;
  v96 = v123;
  v123 = v27;
  v28 = v98;
  v98 = v125;
  v125 = v28;
  v29 = v99;
  v99 = v126;
  v126 = v29;
  v30 = v100;
  v100 = *(_QWORD *)v127;
  *(_QWORD *)v127 = v30;
  v31 = v97;
  v97 = v124;
  v124 = v31;
  LODWORD(v31) = v101;
  v101 = *(_DWORD *)&v127[8];
  *(_DWORD *)&v127[8] = LODWORD(v31);
  LODWORD(v31) = v102;
  v102 = *(_DWORD *)&v127[12];
  *(_DWORD *)&v127[12] = LODWORD(v31);
  LODWORD(v31) = v103;
  v103 = *(_DWORD *)&v127[16];
  *(_DWORD *)&v127[16] = LODWORD(v31);
  LODWORD(v31) = v104;
  v104 = *(_DWORD *)&v127[20];
  *(_DWORD *)&v127[20] = LODWORD(v31);
  LODWORD(v31) = v105;
  v105 = LODWORD(v128);
  LODWORD(v128) = LODWORD(v31);
  LODWORD(v31) = v106;
  v106 = HIDWORD(v128);
  HIDWORD(v128) = LODWORD(v31);
  LODWORD(v31) = v107;
  v107 = v129;
  LODWORD(v129) = LODWORD(v31);
  LODWORD(v31) = v108;
  v108 = DWORD1(v129);
  DWORD1(v129) = LODWORD(v31);
  v32 = v109;
  v33 = v110;
  v109 = v131;
  v110 = v132;
  v131 = v32;
  v132 = v33;
  v34 = v111;
  v111 = v133;
  v133 = v34;
  LODWORD(v31) = (_DWORD)v112;
  LODWORD(v112) = v134;
  LODWORD(v134) = LODWORD(v31);
  LODWORD(v31) = HIDWORD(v112);
  HIDWORD(v112) = HIDWORD(v134);
  HIDWORD(v134) = LODWORD(v31);
  v35 = v113;
  v113 = v18;
  v135 = v35;
  LODWORD(v35) = v114;
  v114 = v19;
  LODWORD(v136) = (_DWORD)v35;
  LODWORD(v35) = v115;
  v115 = v20;
  HIDWORD(v136) = (_DWORD)v35;
  v36 = v116;
  v116 = v21;
  v137 = v36;
  LOBYTE(v36) = v117;
  v117 = v22;
  v138 = v36;
  LOBYTE(v36) = v118;
  v118 = (char)v5;
  v139 = v36;
  if ( v24 )
  {
    v140 = 0;
    ((void (__fastcall *)(void (__fastcall ***)(_QWORD, __int64, struct Ofc::CProxyPtrImpl *)))(*v24)[1])(v24);
  }
  Ofc::CProxyPtrImpl::DtorStrongRelease(&v135);
  Ofc::CProxyPtrImpl::DtorWeakRelease(&v122);
  Ofc::CProxyPtrImpl::DtorStrongRelease(&v121);
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  Gfx::SpriteClipRectCachingPolicy::SpriteClipRectCachingPolicy(v92, &si128);
  if ( v98 == 0.0 )
  {
    v71 = COERCE_DOUBLE(v92);
    if ( !a5 )
      v71 = v98;
    v98 = v71;
  }
  v37 = *((double *)a3 + 1);
  v38 = DOUBLE_0_5;
  if ( v37 < 0.0 )
    v39 = DOUBLE_N0_5;
  else
    v39 = DOUBLE_0_5;
  if ( *(double *)a3 < 0.0 )
    v38 = DOUBLE_N0_5;
  LODWORD(v73) = (int)(v38 + *(double *)a3);
  HIDWORD(v73) = (int)(v37 + v39);
  v112 = v73;
  LOBYTE(v77) = 0;
  v78 = Ofc::CProxyPtrImpl::WeakAddRef(v72);
  v75 = Ofc::CProxyPtrImpl::CheckedStrongAddRef(v78);
  v40 = *((_QWORD *)v75 + 2);
  if ( v40 )
  {
    LOBYTE(v77) = (*(_BYTE *)(v40 + 545) & 2) != 0;
    *(_BYTE *)(v40 + 545) |= 2u;
  }
  Ofc::CProxyPtrImpl::DtorStrongRelease(&v75);
  v73 = Ofc::CProxyPtrImpl::CheckedStrongAddRef(v72);
  Art::ViewInfoRestorer::ViewInfoRestorer(&v143, &v73, v93);
  Ofc::CProxyPtrImpl::DtorStrongRelease(&v73);
  v41 = (__int64 *)Ofc::CProxyPtrImpl::GetChecked(v72);
  v42 = (struct Ofc::CProxyPtrImpl *)v83;
  if ( *((_BYTE *)this + 36) )
    v42 = 0;
  v75 = v42;
  CodeMarker(8853);
  v43 = v41[26] & 2;
  v44 = (v41[26] & 2) != 0 ? 8 : -1;
  v45 = 8 * ((unsigned int)v41[26] & 1);
  *(_QWORD *)&v46 = *(_OWORD *)&_mm_unpackhi_pd((__m128d)0LL, (__m128d)0LL);
  v90 = &Gfx::InkStrokeCollectionCachingStateRestorer::`vftable';
  v47 = Gfx::IInkStrokeCollection::FIsCachingEnabledForCurrentThread();
  v91 = v47;
  if ( !Art::s_pHost )
  {
    CrashWithRecovery(0x1E44D300u, 0);
LABEL_44:
    Gfx::IInkStrokeCollection::ToggleCachingForCurrentThread(v47);
    goto LABEL_31;
  }
  if ( (*(unsigned __int8 (__fastcall **)(struct Art::IAppHost *, __int64))(*(_QWORD *)Art::s_pHost + 200LL))(
         Art::s_pHost,
         119) )
  {
    v70 = v41[26];
    if ( (v70 & 8) != 0 && ((v70 & 0x4000000) == 0 || (v70 & 0x20000) != 0) )
      Gfx::IInkStrokeCollection::ToggleCachingForCurrentThread(0);
  }
  Gfx::DefaultQualityPolicy::Get();
  v48 = *((_DWORD *)v41 + 50);
  v141 = &Art::RenderOptionsBase::`vftable';
  v142 = v48;
  v76 = (struct Ofc::CProxyPtrImpl *)v41[12];
  v49 = &v141;
  if ( v41[11] )
    v49 = (void ***)v41[11];
  v82 = v41[10];
  v50 = v41[9];
  if ( !v50 )
    v50 = Gfx::DefaultQualityPolicy::Get();
  v88[0] = v50;
  v88[1] = v82;
  v88[2] = v81;
  v88[3] = v49;
  v88[4] = v76;
  v5 = 0;
  if ( v43 || (_DWORD)v45 )
  {
    v84 = &Gfx::ShapeFlagsFilter::`vftable';
    v85 = v44;
    v86 = v45;
    v87 = v75;
    v41 = (__int64 *)v41[47];
    v51 = (*(__int64 (__fastcall **)(__int64 *))(*v41 + 152))(v41);
    v52 = (struct Ofc::CProxyPtrImpl *)&v84;
  }
  else
  {
    v41 = (__int64 *)v41[47];
    v51 = (*(__int64 (__fastcall **)(__int64 *))(*v41 + 152))(v41);
    v52 = v75;
  }
  v53 = *(double *)(v51 + 40);
  v54 = *(double *)(v51 + 24);
  v55 = *(double *)(v51 + 8);
  v56 = *(double *)(v51 + 32) * 0.0 + v53;
  v57 = *(double *)(v51 + 16) * 0.0 + v54;
  v58 = *(double *)v51 * 0.0 + v55;
  v59 = v54 * 0.0 + *(double *)(v51 + 16);
  v60 = v55 * 0.0 + *(double *)v51;
  v124 = v53 * 0.0 + *(double *)(v51 + 32) + 0.0;
  v123 = v57;
  v122 = *(struct Ofc::CProxyPtrImpl **)&v59;
  v121 = *(struct Ofc::CProxyPtrImpl **)&v58;
  v120 = v60;
  v125 = v56 + v46;
  v126 = *(_QWORD *)(v51 + 48);
  *(_OWORD *)v127 = *(_OWORD *)(v51 + 56);
  v61 = *(double *)(v51 + 80) - v46;
  *(double *)&v127[16] = *(double *)(v51 + 72) - 0.0;
  v128 = v61;
  v129 = *(_OWORD *)(v51 + 88);
  v62 = *(_OWORD *)(v51 + 104);
  v45 = (__int64)v80;
  v63 = *v41;
  v130 = v62;
  LOBYTE(v41) = (*(__int64 (__fastcall **)(__int64 *, struct Gfx::ITarget *, double *, _QWORD *, struct Ofc::CProxyPtrImpl *, __int64, _BYTE))(v63 + 248))(
                  v41,
                  v80,
                  &v120,
                  v88,
                  v52,
                  v13,
                  0);
  if ( v47 != (unsigned __int8)Gfx::IInkStrokeCollection::FIsCachingEnabledForCurrentThread() )
    goto LABEL_44;
LABEL_31:
  CodeMarker(8854);
  if ( !(_BYTE)v41 )
  {
    Art::ViewInfoRestorer::~ViewInfoRestorer(&v143);
    v76 = Ofc::CProxyPtrImpl::CheckedStrongAddRef(v78);
    v69 = *((_QWORD *)v76 + 2);
    if ( v69 )
      *(_BYTE *)(v69 + 545) = *(_BYTE *)(v69 + 545) & 0xFD | (2 * (v77 & 1));
    Ofc::CProxyPtrImpl::DtorStrongRelease(&v76);
    Ofc::CProxyPtrImpl::DtorWeakRelease(&v78);
    Mso::TCntPtr<Mso::PlatformCanvas::IPlatformCanvas>::Clear(&v119);
    Ofc::CProxyPtrImpl::DtorStrongRelease(&v113);
    Ofc::CProxyPtrImpl::DtorWeakRelease(&v95);
    Ofc::CProxyPtrImpl::DtorStrongRelease(&v94);
    if ( v13 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 8LL))(v13);
    goto LABEL_49;
  }
  v64 = v83;
  if ( *((_BYTE *)v79 + 36) != (_BYTE)v5 )
    v64 = v5;
  sub_1801ABDBC(v45, (__int64)&v72, &v74, v64, v81, v13);
  v65 = (Art::View *)*((_QWORD *)v143 + 2);
  if ( v65 )
    Art::View::SetViewInfoImpl(v65);
  Art::View::Info::~Info((Art::View::Info *)v144);
  Ofc::CProxyPtrImpl::DtorStrongRelease(&v143);
  v79 = Ofc::CProxyPtrImpl::CheckedStrongAddRef(v78);
  v66 = *((_QWORD *)v79 + 2);
  if ( v66 )
    *(_BYTE *)(v66 + 545) = *(_BYTE *)(v66 + 545) & 0xFD | (2 * (v77 & 1));
  Ofc::CProxyPtrImpl::DtorStrongRelease(&v79);
  Ofc::CProxyPtrImpl::DtorWeakRelease(&v78);
  v67 = v119;
  if ( v119 )
  {
    v119 = (void (__fastcall ***)(_QWORD, __int64, struct Ofc::CProxyPtrImpl *))v5;
    ((void (__fastcall *)(void (__fastcall ***)(_QWORD, _QWORD, struct Ofc::CProxyPtrImpl *)))(*v67)[1])(v67);
  }
  Ofc::CProxyPtrImpl::DtorStrongRelease(&v113);
  Ofc::CProxyPtrImpl::DtorWeakRelease(&v95);
  Ofc::CProxyPtrImpl::DtorStrongRelease(&v94);
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 8LL))(v13);
  Ofc::CProxyPtrImpl::DtorStrongRelease(&v72);
  Ofc::CProxyPtrImpl::DtorStrongRelease(&v74);
  return 1;
}

```

## disassembly

```asm
0x18019faf0  mov     rax, rsp
0x18019faf3  push    rbp
0x18019faf4  push    rbx
0x18019faf5  push    rsi
0x18019faf6  push    rdi
0x18019faf7  push    r12
0x18019faf9  push    r13
0x18019fafb  push    r14
0x18019fafd  push    r15
0x18019faff  lea     rbp, [rax-328h]
0x18019fb06  sub     rsp, 3E8h
0x18019fb0d  movaps  xmmword ptr [rax-58h], xmm6
0x18019fb11  movaps  xmmword ptr [rax-68h], xmm7
0x18019fb15  movaps  xmmword ptr [rax-78h], xmm8
0x18019fb1a  mov     rax, cs:__security_cookie
0x18019fb21  xor     rax, rsp
0x18019fb24  mov     [rbp+320h+var_78], rax
0x18019fb2b  mov     [rbp+320h+var_390], r9
0x18019fb2f  mov     rdi, r8
0x18019fb32  mov     [rbp+320h+var_398], rdx
0x18019fb36  mov     r15, rcx
0x18019fb39  mov     [rbp+320h+var_3A0], rcx
0x18019fb3d  mov     rcx, [rcx+18h]; struct Ofc::CProxyPtrImpl *
0x18019fb41  call    ?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAddRef(Ofc::CProxyPtrImpl *)
0x18019fb46  mov     [rsp+420h+var_3C8], rax
0x18019fb4b  xor     r12d, r12d
0x18019fb4e  cmp     [rax+10h], r12
0x18019fb52  jz      loc_1801A065F
0x18019fb58  mov     rcx, rax; this
0x18019fb5b  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x18019fb60  mov     rcx, [rax+0A0h]; struct Ofc::CProxyPtrImpl *
0x18019fb67  call    ?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAddRef(Ofc::CProxyPtrImpl *)
0x18019fb6c  mov     [rsp+420h+var_3D8], rax
0x18019fb71  mov     rcx, [rax+10h]
0x18019fb75  test    rcx, rcx
0x18019fb78  jz      loc_1801A06A4
0x18019fb7e  mov     rax, [rcx]
0x18019fb81  mov     rax, [rax+20h]
0x18019fb85  call    cs:__guard_dispatch_icall_fptr
0x18019fb8b  mov     rbx, rax
0x18019fb8e  lea     rcx, [rsp+420h+var_3D8]; struct Ofc::CProxyPtrImpl **
0x18019fb93  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x18019fb98  nop
0x18019fb99  mov     rcx, [rbx]; struct Ofc::CProxyPtrImpl *
0x18019fb9c  call    ?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAddRef(Ofc::CProxyPtrImpl *)
0x18019fba1  mov     [rsp+420h+var_3E0], rax
0x18019fba6  cmp     [rax+10h], r12
0x18019fbaa  jz      loc_1801A0694
0x18019fbb0  mov     rcx, [rsp+420h+var_3C8]; this
0x18019fbb5  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x18019fbba  lea     rcx, ??_7ViewElementShapeFilter@Art@@6B@; const Art::ViewElementShapeFilter::`vftable'
0x18019fbc1  mov     [rbp+320h+var_380], rcx
0x18019fbc5  mov     [rbp+320h+var_378], rax
0x18019fbc9  mov     rcx, [rsp+420h+var_3C8]; this
0x18019fbce  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x18019fbd3  mov     rbx, [rax+90h]
0x18019fbda  mov     [rbp+320h+var_330], rbx
0x18019fbde  test    rbx, rbx
0x18019fbe1  jz      short loc_18019FBF3
0x18019fbe3  mov     rax, [rbx]
0x18019fbe6  mov     rcx, rbx
0x18019fbe9  mov     rax, [rax]
0x18019fbec  call    cs:__guard_dispatch_icall_fptr
0x18019fbf2  nop
0x18019fbf3  lea     rcx, [rbp+320h+var_2E0]; this
0x18019fbf7  call    ??0Info@View@Art@@QEAA@XZ; Art::View::Info::Info(void)
0x18019fbfc  mov     rcx, [rsp+420h+var_3E0]; this
0x18019fc01  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x18019fc06  mov     rdx, rax
0x18019fc09  lea     rax, ??_7Info@View@Art@@6B@; const Art::View::Info::`vftable'
0x18019fc10  mov     [rbp+320h+var_220], rax
0x18019fc17  mov     rcx, [rdx+30h]; struct Ofc::CProxyPtrImpl *
0x18019fc1b  call    ?StrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::StrongAddRef(Ofc::CProxyPtrImpl *)
0x18019fc20  mov     [rbp+320h+var_218], rax
0x18019fc27  mov     rcx, [rdx+38h]; struct Ofc::CProxyPtrImpl *
0x18019fc2b  call    ?WeakAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::WeakAddRef(Ofc::CProxyPtrImpl *)
0x18019fc30  mov     [rbp+320h+var_210], rax
0x18019fc37  mov     rcx, [rdx+40h]
0x18019fc3b  mov     [rbp+320h+var_208], rcx
0x18019fc42  mov     rcx, [rdx+48h]
0x18019fc46  mov     [rbp+320h+var_200], rcx
0x18019fc4d  mov     rax, [rdx+50h]
0x18019fc51  mov     [rbp+320h+var_1F8], rax
0x18019fc58  mov     rax, [rdx+58h]
0x18019fc5c  mov     [rbp+320h+var_1F0], rax
0x18019fc63  mov     rax, [rdx+60h]
0x18019fc67  mov     qword ptr [rbp+320h+var_1E8], rax
0x18019fc6e  movups  xmm0, xmmword ptr [rdx+68h]
0x18019fc72  movdqu  [rbp+320h+var_1E8+8], xmm0
0x18019fc7a  mov     rax, [rdx+78h]
0x18019fc7e  mov     [rbp+320h+var_1D0], rax
0x18019fc85  mov     rax, [rdx+80h]
0x18019fc8c  mov     qword ptr [rbp+320h+var_1C8], rax
0x18019fc93  lea     rax, [rbp+320h+var_220]
0x18019fc9a  mov     qword ptr [rbp+320h+var_1C8+8], rax
0x18019fca1  lea     rax, [rbp+320h+var_220]
0x18019fca8  mov     qword ptr [rbp+320h+var_1B8], rax
0x18019fcaf  lea     rax, [rbp+320h+var_220]
0x18019fcb6  mov     qword ptr [rbp+320h+var_1B8+8], rax
0x18019fcbd  movss   xmm0, dword ptr [rdx+0A0h]
0x18019fcc5  movss   [rbp+320h+var_1A8], xmm0
0x18019fccd  movss   xmm1, dword ptr [rdx+0A4h]
0x18019fcd5  movss   [rbp+320h+var_1A4], xmm1
0x18019fcdd  movups  xmm0, xmmword ptr [rdx+0A8h]
0x18019fce4  movdqu  [rbp+320h+var_1A0], xmm0
0x18019fcec  mov     rax, [rdx+0B8h]
0x18019fcf3  mov     [rbp+320h+var_190], rax
0x18019fcfa  mov     rcx, [rdx+0C0h]; struct Ofc::CProxyPtrImpl *
0x18019fd01  call    ?StrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::StrongAddRef(Ofc::CProxyPtrImpl *)
0x18019fd06  mov     r8, rax
0x18019fd09  mov     [rbp+320h+var_188], rax
0x18019fd10  xor     eax, eax
0x18019fd12  mov     [rbp+320h+var_180], rax
0x18019fd19  mov     r9d, [rdx+0C8h]
0x18019fd20  mov     dword ptr [rbp+320h+var_180], r9d
0x18019fd27  mov     r10d, [rdx+0CCh]
0x18019fd2e  mov     dword ptr [rbp+320h+var_180+4], r10d
0x18019fd35  mov     r11, [rdx+0D0h]
0x18019fd3c  mov     [rbp+320h+var_178], r11
0x18019fd43  mov     sil, [rdx+0D8h]
0x18019fd4a  mov     [rbp+320h+var_170], sil
0x18019fd51  mov     r14b, [rdx+0D9h]
0x18019fd58  mov     [rbp+320h+var_16F], r14b
0x18019fd5f  mov     rcx, [rdx+0E0h]
0x18019fd66  mov     [rbp+320h+var_168], rcx
0x18019fd6d  test    rcx, rcx
0x18019fd70  jz      short loc_18019FDAF
0x18019fd72  mov     rax, [rcx]
0x18019fd75  mov     rax, [rax]
0x18019fd78  call    cs:__guard_dispatch_icall_fptr
0x18019fd7e  mov     rcx, [rbp+320h+var_168]
0x18019fd85  mov     r14b, [rbp+320h+var_16F]
0x18019fd8c  mov     sil, [rbp+320h+var_170]
0x18019fd93  mov     r11, [rbp+320h+var_178]
0x18019fd9a  mov     r10d, dword ptr [rbp+320h+var_180+4]
0x18019fda1  mov     r9d, dword ptr [rbp+320h+var_180]
0x18019fda8  mov     r8, [rbp+320h+var_188]
0x18019fdaf  mov     rdx, [rbp+320h+var_228]
0x18019fdb6  mov     [rbp+320h+var_228], rcx
0x18019fdbd  mov     [rbp+320h+var_168], rdx
0x18019fdc4  mov     rcx, [rbp+320h+var_2D8]
0x18019fdc8  mov     rax, [rbp+320h+var_218]
0x18019fdcf  mov     [rbp+320h+var_2D8], rax
0x18019fdd3  mov     [rbp+320h+var_218], rcx
0x18019fdda  mov     rcx, [rbp+320h+var_2D0]
0x18019fdde  mov     rax, [rbp+320h+var_210]
0x18019fde5  mov     [rbp+320h+var_2D0], rax
0x18019fde9  mov     [rbp+320h+var_210], rcx
0x18019fdf0  mov     rcx, [rbp+320h+var_2C8]
0x18019fdf4  mov     rax, [rbp+320h+var_208]
0x18019fdfb  mov     [rbp+320h+var_2C8], rax
0x18019fdff  mov     [rbp+320h+var_208], rcx
0x18019fe06  mov     rcx, [rbp+320h+var_2B8]
0x18019fe0a  mov     rax, [rbp+320h+var_1F8]
0x18019fe11  mov     [rbp+320h+var_2B8], rax
0x18019fe15  mov     [rbp+320h+var_1F8], rcx
0x18019fe1c  mov     rcx, [rbp+320h+var_2B0]
0x18019fe20  mov     rax, [rbp+320h+var_1F0]
0x18019fe27  mov     [rbp+320h+var_2B0], rax
0x18019fe2b  mov     [rbp+320h+var_1F0], rcx
0x18019fe32  mov     rcx, [rbp+320h+var_2A8]
0x18019fe36  mov     rax, qword ptr [rbp+320h+var_1E8]
0x18019fe3d  mov     [rbp+320h+var_2A8], rax
0x18019fe41  mov     qword ptr [rbp+320h+var_1E8], rcx
0x18019fe48  mov     rcx, [rbp+320h+var_2C0]
0x18019fe4c  mov     rax, [rbp+320h+var_200]
0x18019fe53  mov     [rbp+320h+var_2C0], rax
0x18019fe57  mov     [rbp+320h+var_200], rcx
0x18019fe5e  mov     ecx, [rbp+320h+var_2A0]
0x18019fe64  mov     eax, dword ptr [rbp+320h+var_1E8+8]
0x18019fe6a  mov     [rbp+320h+var_2A0], eax
0x18019fe70  mov     dword ptr [rbp+320h+var_1E8+8], ecx
0x18019fe76  mov     ecx, [rbp+320h+var_29C]
0x18019fe7c  mov     eax, dword ptr [rbp+320h+var_1E8+0Ch]
0x18019fe82  mov     [rbp+320h+var_29C], eax
0x18019fe88  mov     dword ptr [rbp+320h+var_1E8+0Ch], ecx
0x18019fe8e  mov     ecx, [rbp+320h+var_298]
0x18019fe94  mov     eax, dword ptr [rbp+320h+var_1D8]
0x18019fe9a  mov     [rbp+320h+var_298], eax
0x18019fea0  mov     dword ptr [rbp+320h+var_1D8], ecx
0x18019fea6  mov     ecx, [rbp+320h+var_294]
0x18019feac  mov     eax, dword ptr [rbp+320h+var_1D8+4]
0x18019feb2  mov     [rbp+320h+var_294], eax
0x18019feb8  mov     dword ptr [rbp+320h+var_1D8+4], ecx
0x18019febe  mov     ecx, [rbp+320h+var_290]
0x18019fec4  mov     eax, dword ptr [rbp+320h+var_1D0]
0x18019feca  mov     [rbp+320h+var_290], eax
0x18019fed0  mov     dword ptr [rbp+320h+var_1D0], ecx
0x18019fed6  mov     ecx, [rbp+320h+var_28C]
0x18019fedc  mov     eax, dword ptr [rbp+320h+var_1D0+4]
0x18019fee2  mov     [rbp+320h+var_28C], eax
0x18019fee8  mov     dword ptr [rbp+320h+var_1D0+4], ecx
0x18019feee  mov     ecx, [rbp+320h+var_288]
0x18019fef4  mov     eax, dword ptr [rbp+320h+var_1C8]
0x18019fefa  mov     [rbp+320h+var_288], eax
0x18019ff00  mov     dword ptr [rbp+320h+var_1C8], ecx
0x18019ff06  mov     ecx, [rbp+320h+var_284]
0x18019ff0c  mov     eax, dword ptr [rbp+320h+var_1C8+4]
0x18019ff12  mov     [rbp+320h+var_284], eax
0x18019ff18  mov     dword ptr [rbp+320h+var_1C8+4], ecx
0x18019ff1e  movss   xmm2, [rbp+320h+var_268]
0x18019ff26  movss   xmm3, [rbp+320h+var_264]
0x18019ff2e  movss   xmm0, [rbp+320h+var_1A8]
0x18019ff36  movss   [rbp+320h+var_268], xmm0
0x18019ff3e  movss   xmm1, [rbp+320h+var_1A4]
0x18019ff46  movss   [rbp+320h+var_264], xmm1
0x18019ff4e  movss   [rbp+320h+var_1A8], xmm2
0x18019ff56  movss   [rbp+320h+var_1A4], xmm3
0x18019ff5e  movaps  xmm1, [rbp+320h+var_260]
0x18019ff65  movaps  xmm0, [rbp+320h+var_1A0]
0x18019ff6c  movdqu  [rbp+320h+var_260], xmm0
0x18019ff74  movdqu  [rbp+320h+var_1A0], xmm1
0x18019ff7c  mov     ecx, dword ptr [rbp+320h+var_250]
0x18019ff82  mov     eax, dword ptr [rbp+320h+var_190]
0x18019ff88  mov     dword ptr [rbp+320h+var_250], eax
0x18019ff8e  mov     dword ptr [rbp+320h+var_190], ecx
0x18019ff94  mov     ecx, dword ptr [rbp+320h+var_250+4]
0x18019ff9a  mov     eax, dword ptr [rbp+320h+var_190+4]
0x18019ffa0  mov     dword ptr [rbp+320h+var_250+4], eax
0x18019ffa6  mov     dword ptr [rbp+320h+var_190+4], ecx
0x18019ffac  mov     rax, [rbp+320h+var_248]
0x18019ffb3  mov     [rbp+320h+var_248], r8
0x18019ffba  mov     [rbp+320h+var_188], rax
0x18019ffc1  mov     eax, [rbp+320h+var_240]
0x18019ffc7  mov     [rbp+320h+var_240], r9d
0x18019ffce  mov     dword ptr [rbp+320h+var_180], eax
0x18019ffd4  mov     eax, [rbp+320h+var_23C]
0x18019ffda  mov     [rbp+320h+var_23C], r10d
0x18019ffe1  mov     dword ptr [rbp+320h+var_180+4], eax
0x18019ffe7  mov     rax, [rbp+320h+var_238]
0x18019ffee  mov     [rbp+320h+var_238], r11
0x18019fff5  mov     [rbp+320h+var_178], rax
0x18019fffc  mov     al, [rbp+320h+var_230]
0x1801a0002  mov     [rbp+320h+var_230], sil
0x1801a0009  mov     [rbp+320h+var_170], al
0x1801a000f  mov     al, [rbp+320h+var_22F]
0x1801a0015  mov     [rbp+320h+var_22F], r14b
0x1801a001c  mov     [rbp+320h+var_16F], al
0x1801a0022  test    rdx, rdx
0x1801a0025  jz      short loc_1801A003E
0x1801a0027  mov     [rbp+320h+var_168], r12
0x1801a002e  mov     rax, [rdx]
0x1801a0031  mov     rcx, rdx
0x1801a0034  mov     rax, [rax+8]
0x1801a0038  call    cs:__guard_dispatch_icall_fptr
0x1801a003e  lea     rcx, [rbp+320h+var_188]; struct Ofc::CProxyPtrImpl **
0x1801a0045  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x1801a004a  lea     rcx, [rbp+320h+var_210]; struct Ofc::CProxyPtrImpl **
0x1801a0051  call    ?DtorWeakRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorWeakRelease(Ofc::CProxyPtrImpl * &)
0x1801a0056  lea     rcx, [rbp+320h+var_218]; struct Ofc::CProxyPtrImpl **
0x1801a005d  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x1801a0062  movdqa  xmm0, cs:__xmm@7fffffff7fffffff8000000080000000
0x1801a006a  movdqu  [rbp+320h+var_328], xmm0
0x1801a006f  lea     rdx, [rbp+320h+var_328]
0x1801a0073  lea     rcx, [rbp+320h+var_308]
0x1801a0077  call    cs:__imp_??0SpriteClipRectCachingPolicy@Gfx@@QEAA@AEBU?$TRect@V?$TUnits@HUDevicePixels@Math@@@Math@@@Math@@@Z; Gfx::SpriteClipRectCachingPolicy::SpriteClipRectCachingPolicy(Math::TRect<Math::TUnits<int,Math::DevicePixels>> const &)
0x1801a007d  mov     rcx, [rbp+320h+var_2B8]
0x1801a0081  test    rcx, rcx
0x1801a0084  jz      loc_1801A066C
0x1801a008a  movsd   xmm1, qword ptr [rdi+8]
0x1801a008f  xorps   xmm6, xmm6
0x1801a0092  movsd   xmm2, cs:__real@bfe0000000000000
0x1801a009a  movsd   xmm0, cs:__real@3fe0000000000000
0x1801a00a2  comisd  xmm1, xmm6
0x1801a00a6  jb      loc_1801A0684
0x1801a00ac  movaps  xmm3, xmm0
0x1801a00af  movsd   xmm4, qword ptr [rdi]
0x1801a00b3  comisd  xmm4, xmm6
0x1801a00b7  jb      loc_1801A068C
0x1801a00bd  addsd   xmm0, xmm4
0x1801a00c1  cvttsd2si eax, xmm0
0x1801a00c5  mov     dword ptr [rsp+420h+var_3D8], eax
0x1801a00c9  addsd   xmm1, xmm3
0x1801a00cd  cvttsd2si eax, xmm1
0x1801a00d1  mov     dword ptr [rsp+420h+var_3D8+4], eax
0x1801a00d5  mov     rax, [rsp+420h+var_3D8]
0x1801a00da  mov     [rbp+320h+var_250], rax
0x1801a00e1  mov     byte ptr [rsp+420h+var_3B0], r12b
0x1801a00e6  mov     rcx, [rsp+420h+var_3E0]; struct Ofc::CProxyPtrImpl *
0x1801a00eb  call    ?WeakAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::WeakAddRef(Ofc::CProxyPtrImpl *)
0x1801a00f0  mov     [rsp+420h+var_3A8], rax
0x1801a00f5  mov     rcx, rax; struct Ofc::CProxyPtrImpl *
0x1801a00f8  call    ?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAddRef(Ofc::CProxyPtrImpl *)
0x1801a00fd  mov     [rsp+420h+var_3C0], rax
0x1801a0102  mov     rcx, [rax+10h]
0x1801a0106  test    rcx, rcx
0x1801a0109  jz      short loc_1801A0120
0x1801a010b  mov     al, [rcx+221h]
0x1801a0111  shr     al, 1
0x1801a0113  and     al, 1
0x1801a0115  mov     byte ptr [rsp+420h+var_3B0], al
0x1801a0119  or      byte ptr [rcx+221h], 2
0x1801a0120  lea     rcx, [rsp+420h+var_3C0]; struct Ofc::CProxyPtrImpl **
0x1801a0125  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x1801a012a  mov     rcx, [rsp+420h+var_3E0]; struct Ofc::CProxyPtrImpl *
0x1801a012f  call    ?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAddRef(Ofc::CProxyPtrImpl *)
0x1801a0134  mov     [rsp+420h+var_3D8], rax
0x1801a0139  lea     r8, [rbp+320h+var_2E0]
0x1801a013d  lea     rdx, [rsp+420h+var_3D8]
0x1801a0142  lea     rcx, [rbp+320h+var_150]
  ... truncated ...
```
