# CMarkup::LoadFromInfo(CDoc::LOADINFO *,unsigned __int64,ushort const *,PARSER_RESTART_TYPE)

- ea: `0x18022080c`
- end: `0x18022271f`
- name: `?LoadFromInfo@CMarkup@@QEAAJPEAULOADINFO@CDoc@@_KPEBGW4PARSER_RESTART_TYPE@@@Z`
- size: `7955`
- prototype: ``
- caller_count: `6`
- callee_count: `98`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180493ae0`
- `0x18069c3f4`
- `0x180775430`
- `0x1807acfa4`
- `0x18080c558`
- `0x1808349dc`

## callees

- `0x1800076b0`
- `0x18000781c`
- `0x18000894c`
- `0x180036bd4`
- `0x1800ad370`
- `0x1800bc2b4`
- `0x1800de754`
- `0x1800e2b08`
- `0x1800e2b60`
- `0x1800e3e8c`
- `0x180135278`
- `0x180154a54`
- `0x1801bf344`
- `0x1801bf528`
- `0x1801c0b08`
- `0x1801cd5ac`
- `0x18021d8d0`
- `0x18021f9bc`
- `0x18021fb58`
- `0x1802202a8`
- `0x180220394`
- `0x180220544`
- `0x18022080c`
- `0x180222728`
- `0x1802227e8`
- `0x18022289c`
- `0x1802229b0`
- `0x1802229c0`
- `0x180222bb0`
- `0x180222d9c`
- `0x180223a8c`
- `0x18022408c`
- `0x1802bf820`
- `0x1802e4fb4`
- `0x1802e5024`
- `0x1802f4b90`
- `0x1802fd8ec`
- `0x18030035c`
- `0x180300fa8`
- `0x180370004`
- `0x18043c328`
- `0x18048360c`
- `0x180491d9c`
- `0x1804dd180`
- `0x1804dd22c`
- `0x1804e223c`
- `0x1804e23dc`
- `0x1804eaea4`
- `0x1804ec98c`
- `0x1804f5814`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x180221d5e`
- `msvcrt!_wcsnicmp` at `0x180221d5e`
- `KERNEL32!CompareStringW` at `0x180221af0`
- `KERNEL32!CompareStringW` at `0x180221af0`
- `iertutil!CreateUri` at `0x1802210a7`
- `iertutil!CreateUri` at `0x1802210a7`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180221dbf`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180221e3d`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180221dbf`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180221e3d`
- `ole32!CreateBindCtx` at `0x180221efe`
- `ole32!CreateBindCtx` at `0x180221efe`
- `WININET!HttpDuplicateDependencyHandle` at `0x18022147f`
- `WININET!HttpDuplicateDependencyHandle` at `0x18022147f`
- `urlmon!__imp_CoInternetSetBrowserEmulationState` at `0x180222623`
- `urlmon!__imp_CoInternetSetBrowserEmulationState` at `0x180222623`
- `OLEAUT32!__imp_SysFreeString` at `0x180220c82`
- `OLEAUT32!__imp_SysFreeString` at `0x180220c8c`
- `OLEAUT32!__imp_SysFreeString` at `0x180220c96`
- `OLEAUT32!__imp_SysFreeString` at `0x1802210b5`
- `OLEAUT32!__imp_SysFreeString` at `0x18022206f`
- `OLEAUT32!__imp_SysFreeString` at `0x1802226c4`
- `OLEAUT32!__imp_SysFreeString` at `0x1802226e0`
- `OLEAUT32!__imp_SysFreeString` at `0x1802226fc`
- `OLEAUT32!__imp_SysFreeString` at `0x180220c82`
- `OLEAUT32!__imp_SysFreeString` at `0x180220c8c`
- `OLEAUT32!__imp_SysFreeString` at `0x180220c96`
- `OLEAUT32!__imp_SysFreeString` at `0x1802210b5`
- `OLEAUT32!__imp_SysFreeString` at `0x18022206f`
- `OLEAUT32!__imp_SysFreeString` at `0x1802226c4`
- `OLEAUT32!__imp_SysFreeString` at `0x1802226e0`
- `OLEAUT32!__imp_SysFreeString` at `0x1802226fc`
- `OLEAUT32!__imp_VariantClear` at `0x1802211bd`
- `OLEAUT32!__imp_VariantClear` at `0x18022122b`
- `OLEAUT32!__imp_VariantClear` at `0x180221594`
- `OLEAUT32!__imp_VariantClear` at `0x180221b94`
- `OLEAUT32!__imp_VariantClear` at `0x18022215e`
- `OLEAUT32!__imp_VariantClear` at `0x1802211bd`
- `OLEAUT32!__imp_VariantClear` at `0x18022122b`
- `OLEAUT32!__imp_VariantClear` at `0x180221594`
- `OLEAUT32!__imp_VariantClear` at `0x180221b94`
- `OLEAUT32!__imp_VariantClear` at `0x18022215e`

## pseudocode

```c
__int64 __fastcall CMarkup::LoadFromInfo(__int64 *a1, _QWORD *a2, unsigned __int64 a3, __int64 a4, int a5)
{
  struct IUnknown **v7; // rcx
  _OWORD *v8; // rax
  __int64 v9; // rdx
  __int128 v10; // xmm1
  __int128 v11; // xmm0
  __int128 v12; // xmm1
  __int128 v13; // xmm0
  __int128 v14; // xmm1
  __int128 v15; // xmm0
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  __int64 v18; // rax
  __int64 v19; // r13
  unsigned __int16 *v20; // rbx
  unsigned __int16 *v21; // rdi
  __int64 v22; // rax
  void (__fastcall *v23)(__int64 *, _QWORD, __int64); // rax
  char v24; // al
  HRESULT Uri; // r14d
  __int64 v26; // rax
  struct IUnknown *v27; // rcx
  struct IUnknown *v28; // rcx
  __int64 v29; // rax
  unsigned int v30; // r10d
  struct IMoniker *v31; // r8
  unsigned __int64 v32; // r9
  struct IUri *v33; // r12
  __int16 v34; // dx
  struct IBindCtx *v35; // r12
  struct CDwnDoc *DwnDoc; // rax
  CBaseFT *v37; // rsi
  CDwnDoc *v38; // rax
  void *v39; // r8
  void *v40; // r8
  void *v41; // r8
  struct IUnknown *v42; // rcx
  unsigned int v43; // edx
  void *v44; // r8
  struct IBindCtx *v45; // rcx
  int v46; // esi
  int v47; // eax
  struct IBindCtx *v48; // rcx
  int v49; // eax
  int v50; // esi
  struct IBindCtx *v51; // rcx
  int v52; // eax
  int v53; // esi
  __int64 v55; // rcx
  CMarkup *v56; // rsi
  CDwnDoc *v57; // rax
  __int64 v58; // rax
  unsigned __int64 v59; // rsi
  __int16 v60; // r12
  int v61; // esi
  struct IUri *v62; // rsi
  bool v63; // si
  bool v64; // r14
  CBase *v65; // rsi
  __int64 v66; // rcx
  int v67; // eax
  __int64 v68; // rax
  void *v69; // rcx
  HTTP_DEPENDENCY_HANDLE v70; // rax
  const unsigned __int16 *v71; // r8
  HRESULT v72; // eax
  __int64 v73; // r8
  __int64 v74; // rax
  CDoc *v75; // rcx
  unsigned int v76; // esi
  int v77; // edx
  __int64 v78; // rcx
  unsigned int v79; // r8d
  int v80; // eax
  int v81; // eax
  int v82; // eax
  __int64 v83; // rcx
  unsigned __int16 *v84; // rsi
  struct IBindCtx *v85; // r14
  unsigned __int16 *v86; // rdx
  unsigned int v87; // r8d
  int IsPrimaryMarkup; // eax
  __int16 v89; // r10
  __int64 v90; // rax
  struct IBindCtx *v91; // r12
  struct IUnknown *v92; // rsi
  int UriFromMoniker; // eax
  struct CAttrArray **v94; // rax
  __int64 v95; // rax
  CMarkup *v96; // rax
  CMarkup *v97; // rsi
  struct IUri *v98; // rax
  int v99; // eax
  int v100; // esi
  char v101; // al
  __int16 v102; // r14
  __int64 v103; // rdx
  _OWORD *v104; // rax
  _OWORD *v105; // rcx
  __int128 v106; // xmm1
  __int128 v107; // xmm0
  __int128 v108; // xmm1
  __int128 v109; // xmm0
  __int128 v110; // xmm1
  __int128 v111; // xmm0
  __int128 v112; // xmm1
  __int128 v113; // xmm1
  __int128 v114; // xmm0
  __int64 v115; // rax
  struct IUnknown *v116; // rsi
  CAPState *v117; // rcx
  const unsigned __int16 *v118; // rax
  __int64 v119; // rax
  CDoc *v120; // rcx
  const unsigned __int16 *v121; // rsi
  int v122; // ecx
  __int64 v123; // rax
  WCHAR v124; // dx
  WCHAR v125; // cx
  const WCHAR *v126; // r8
  const WCHAR *i; // r9
  unsigned __int16 v128; // ax
  int v129; // eax
  struct IUnknown *v130; // r10
  int v131; // eax
  __int64 v132; // rax
  CMarkup *v133; // rcx
  unsigned __int16 *v134; // r10
  __int64 v135; // rax
  __int64 v136; // rcx
  CMarkup *v137; // rcx
  unsigned int CodePageCore; // r12d
  int v139; // eax
  bool v140; // zf
  unsigned __int16 *v141; // rcx
  __int64 v142; // r10
  int v143; // eax
  struct IUnknown **v144; // r14
  _DWORD *v145; // rsi
  struct IUnknown *v146; // rcx
  bool v147; // r8
  struct IUnknown *v148; // rcx
  int v149; // r14d
  int v150; // r9d
  struct COmWindowProxy *OuterWindow; // rsi
  __int64 v152; // rax
  unsigned __int64 v153; // rsi
  __int64 v154; // rax
  unsigned __int64 v155; // kr00_8
  void *v156; // rax
  int BindContextParam; // eax
  struct COmWindowProxy *v158; // rax
  int v159; // eax
  __int64 v160; // rcx
  int v161; // edx
  int v162; // ecx
  CMarkup *v163; // r14
  unsigned int URLCodePage; // r14d
  const unsigned __int16 *Url; // rax
  void *v166; // r8
  int v167; // eax
  unsigned int lpString2; // [rsp+20h] [rbp-E0h]
  int cchCount2; // [rsp+28h] [rbp-D8h]
  struct CDwnDoc *v170; // [rsp+40h] [rbp-C0h]
  LPCWSTR pwzURI; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v172; // [rsp+50h] [rbp-B0h] BYREF
  HTTP_DEPENDENCY_HANDLE phDuplicatedDependencyHandle; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int64 v174; // [rsp+60h] [rbp-A0h]
  BSTR bstrString; // [rsp+68h] [rbp-98h] BYREF
  struct IUri *v176; // [rsp+70h] [rbp-90h] BYREF
  IUri *pIUri; // [rsp+78h] [rbp-88h] BYREF
  int v178; // [rsp+80h] [rbp-80h]
  unsigned __int16 *v179; // [rsp+88h] [rbp-78h] BYREF
  struct CWindow *v180; // [rsp+90h] [rbp-70h] BYREF
  int v181; // [rsp+98h] [rbp-68h]
  struct IUnknown *v182; // [rsp+A0h] [rbp-60h] BYREF
  IUri *ppURI; // [rsp+A8h] [rbp-58h] BYREF
  VARIANTARG pvarg; // [rsp+B0h] [rbp-50h] BYREF
  _DWORD v185[2]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v186; // [rsp+D0h] [rbp-30h]
  __int64 v187; // [rsp+D8h] [rbp-28h]
  __int64 v188; // [rsp+E0h] [rbp-20h]
  int v189; // [rsp+E8h] [rbp-18h]
  struct IMoniker *v190; // [rsp+F0h] [rbp-10h] BYREF
  struct IUnknown *v191; // [rsp+F8h] [rbp-8h] BYREF
  struct IUnknown *v192; // [rsp+100h] [rbp+0h] BYREF
  BSTR v193; // [rsp+108h] [rbp+8h] BYREF
  BSTR v194[2]; // [rsp+110h] [rbp+10h] BYREF
  VARIANTARG v195; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int16 *v196; // [rsp+140h] [rbp+40h]
  struct IUnknown *v197; // [rsp+150h] [rbp+50h] BYREF
  LPBC ppbc; // [rsp+158h] [rbp+58h] BYREF
  struct IUnknown *v199; // [rsp+160h] [rbp+60h] BYREF
  CMarkup *v200; // [rsp+168h] [rbp+68h]
  IUri *v201; // [rsp+170h] [rbp+70h]
  void **v202; // [rsp+178h] [rbp+78h] BYREF
  struct IBindCtx *v203; // [rsp+180h] [rbp+80h]
  int v204; // [rsp+188h] [rbp+88h]
  BSTR v205[2]; // [rsp+190h] [rbp+90h]
  int v206; // [rsp+1A0h] [rbp+A0h]
  void **v207; // [rsp+1A8h] [rbp+A8h] BYREF
  struct IBindCtx *v208; // [rsp+1B0h] [rbp+B0h]
  int v209; // [rsp+1B8h] [rbp+B8h]
  BSTR v210[2]; // [rsp+1C0h] [rbp+C0h]
  int v211; // [rsp+1D0h] [rbp+D0h]
  void **v212; // [rsp+1D8h] [rbp+D8h] BYREF
  struct IBindCtx *v213; // [rsp+1E0h] [rbp+E0h]
  int v214; // [rsp+1E8h] [rbp+E8h]
  wchar_t *String1[2]; // [rsp+1F0h] [rbp+F0h]
  int v216; // [rsp+200h] [rbp+100h]
  __int64 v217; // [rsp+208h] [rbp+108h]
  struct IUnknown *v218[4]; // [rsp+210h] [rbp+110h] BYREF
  struct IUnknown *v219; // [rsp+230h] [rbp+130h] BYREF
  const WCHAR *v220; // [rsp+238h] [rbp+138h]
  struct IUri *v221; // [rsp+240h] [rbp+140h]
  void *v222; // [rsp+248h] [rbp+148h]
  unsigned __int16 *v223; // [rsp+250h] [rbp+150h]
  struct IBindCtx *v224; // [rsp+258h] [rbp+158h]
  struct IUnknown *v225; // [rsp+260h] [rbp+160h]
  int v226; // [rsp+27Ch] [rbp+17Ch]
  int v227; // [rsp+288h] [rbp+188h]
  int v228; // [rsp+28Ch] [rbp+18Ch]
  __int64 v229; // [rsp+290h] [rbp+190h]
  void *v230; // [rsp+2A8h] [rbp+1A8h]
  void *v231; // [rsp+2B0h] [rbp+1B0h]
  void *v232; // [rsp+2B8h] [rbp+1B8h]
  unsigned int v233; // [rsp+2C8h] [rbp+1C8h]
  unsigned int v234; // [rsp+2CCh] [rbp+1CCh]
  int v235; // [rsp+2D0h] [rbp+1D0h]
  struct IUri *v236; // [rsp+2E0h] [rbp+1E0h]
  int v237; // [rsp+310h] [rbp+210h]
  unsigned int v238; // [rsp+314h] [rbp+214h]
  char v239; // [rsp+318h] [rbp+218h]
  unsigned __int16 v240; // [rsp+31Ch] [rbp+21Ch]
  char v241; // [rsp+31Eh] [rbp+21Eh]
  _BYTE v242[88]; // [rsp+320h] [rbp+220h] BYREF
  int v243; // [rsp+378h] [rbp+278h]
  int v244; // [rsp+37Ch] [rbp+27Ch]
  CDownloadInitiatorInfo *v245; // [rsp+3A8h] [rbp+2A8h]
  int v246; // [rsp+3B0h] [rbp+2B0h]
  __int64 v247; // [rsp+3D0h] [rbp+2D0h]
  _BYTE v248[448]; // [rsp+460h] [rbp+360h] BYREF

  v174 = a3;
  v217 = a4;
  memset_0(v242, 0, 0x138u);
  v7 = v218;
  v197 = 0;
  v8 = a2;
  v176 = 0;
  pIUri = 0;
  v9 = 2;
  do
  {
    v10 = v8[1];
    *(_OWORD *)v7 = *v8;
    v11 = v8[2];
    *((_OWORD *)v7 + 1) = v10;
    v12 = v8[3];
    *((_OWORD *)v7 + 2) = v11;
    v13 = v8[4];
    *((_OWORD *)v7 + 3) = v12;
    v14 = v8[5];
    *((_OWORD *)v7 + 4) = v13;
    v15 = v8[6];
    *((_OWORD *)v7 + 5) = v14;
    v16 = v8[7];
    v8 += 8;
    *((_OWORD *)v7 + 6) = v15;
    *((_OWORD *)v7 + 7) = v16;
    v7 += 16;
    --v9;
  }
  while ( v9 );
  v17 = *v8;
  v18 = a1[40];
  v19 = 0;
  *(_OWORD *)v7 = v17;
  if ( v18 )
    v19 = *(_QWORD *)(v18 + 16);
  v192 = 0;
  v214 = 11;
  v209 = 11;
  v204 = 11;
  v199 = 0;
  v201 = 0;
  v20 = 0;
  ppURI = 0;
  v21 = 0;
  v185[0] = 0;
  v22 = *a1;
  v182 = 0;
  bstrString = 0;
  v193 = 0;
  v194[0] = 0;
  ppbc = 0;
  v191 = 0;
  v212 = &CUString::`vftable';
  v213 = 0;
  *(_OWORD *)String1 = 0;
  v216 = 0;
  v207 = &CUString::`vftable';
  v208 = 0;
  *(_OWORD *)v210 = 0;
  v211 = 0;
  v202 = &CUString::`vftable';
  v203 = 0;
  *(_OWORD *)v205 = 0;
  v206 = 0;
  v190 = 0;
  v172 = 0;
  v179 = 0;
  v186 = 0;
  v187 = 0;
  v188 = 0;
  v180 = (struct CWindow *)a1;
  if ( *(__int64 (__fastcall **)())(v22 + 984) != _vtguard )
    goto LABEL_72;
  v23 = *(void (__fastcall **)(__int64 *, _QWORD, __int64))(v22 + 1144);
  v200 = 0;
  v23(a1, 0, 128);
  if ( !v19 || (v24 = *((_BYTE *)a1 + 98), (v24 & 0x20) != 0) )
  {
    Uri = -2147467259;
    CMarkup::CLock::~CLock((CMarkup::CLock *)&v180);
    goto LABEL_109;
  }
  *((_BYTE *)a1 + 98) = v24 | 0x20;
  if ( *(__int64 (__fastcall **)())(*a1 + 984) != _vtguard )
    goto LABEL_72;
  (*(void (__fastcall **)(__int64 *))(*a1 + 1152))(a1);
  Uri = CMarkup::EnforceSandbox((CMarkup *)a1, (const struct SandboxFlags *)(v19 + 6428));
  *((_BYTE *)a1 + 104) ^= (*((_BYTE *)a1 + 104) ^ (32 * *(_BYTE *)(v19 + 6428))) & 0x20;
  if ( Uri < 0 )
    goto LABEL_109;
  v26 = a1[44];
  if ( v26 )
  {
    v55 = *(_QWORD *)(v26 + 120);
    if ( v55 )
    {
      v56 = *(CMarkup **)(v55 + 104);
      v200 = v56;
      if ( v56 )
        CMarkup::ShowWaitCursor(v56, 1);
    }
  }
  v27 = v218[0];
  a2[10] = 0;
  a2[19] = 0;
  a2[20] = 0;
  a2[21] = 0;
  a2[7] = 0;
  if ( v27 )
    ((void (__fastcall *)(struct IUnknown *))v27->lpVtbl->AddRef)(v27);
  v28 = v219;
  if ( v219 )
    ((void (__fastcall *)(struct IUnknown *))v219->lpVtbl->AddRef)(v219);
  v29 = a1[44];
  LOWORD(v30) = v240;
  if ( v29
    && (*(_BYTE *)(v29 + 16) & 1) == 0
    && (v28 = *(struct IUnknown **)(*(_QWORD *)(v29 + 120) + 104LL)) != 0
    && (unsigned int)CMarkup::IsPrimaryMarkup((CMarkup *)v28) )
  {
    v122 = *(_DWORD *)(v19 + 4864);
    v181 = 1;
    *(_DWORD *)(v19 + 4864) = v122
                            ^ ((unsigned __int16)v122
                             ^ (unsigned __int16)((unsigned __int16)(v30 >> 7) << 13))
                            & 0x2000;
    v28 = (struct IUnknown *)(*((_DWORD *)a1 + 190)
                            ^ ((unsigned __int8)*((_DWORD *)a1 + 190)
                             ^ (unsigned __int8)(4 * (v30 >> 7)))
                            & 4u);
    *((_DWORD *)a1 + 190) = (_DWORD)v28;
  }
  else
  {
    v181 = 0;
  }
  *((_BYTE *)a1 + 104) ^= (*((_BYTE *)a1 + 104) ^ (16 * ((unsigned __int16)v30 >> 11))) & 0x10;
  if ( (v30 & 0x1000) != 0 )
    *((_DWORD *)a1 + 188) |= 0x20000000u;
  if ( (v241 & 1) != 0 )
  {
    v123 = a1[44];
    if ( v123 )
      *(_BYTE *)(*(_QWORD *)(v123 + 120) + 226LL) |= 1u;
  }
  *(_DWORD *)(v19 + 4856) &= 0xFFFC3FFF;
  *(_QWORD *)(v19 + 4464) = 0;
  Uri = CMarkup::EnsureMoniker((CMarkup *)v28, (struct CDoc::LOADINFO *)v218);
  if ( Uri )
    goto LABEL_109;
  v33 = v221;
  if ( v221 )
  {
    Uri = CUString::Set((CUString *)&v212, v221, Uri_PROPERTY_SCHEME_NAME);
    if ( Uri < 0 )
      goto LABEL_109;
  }
  *((_BYTE *)a1 + 106) &= ~0x20u;
  v34 = v174;
  *((_BYTE *)a1 + 106) |= (v174 >> 34) & 0x20;
  if ( !v219 )
  {
    pwzURI = (LPCWSTR)v224;
LABEL_24:
    Uri = CMarkup::GetUri((const struct CMarkup *const)a1, &v176);
    v35 = 0;
    goto LABEL_25;
  }
  v90 = a1[44];
  if ( !v90 || v90 != *(_QWORD *)(v19 + 824) )
    goto LABEL_161;
  v139 = *(_DWORD *)(v19 + 4860);
  if ( (v139 & 4) == 0
    && ((v139 & 8) == 0 || (a1[94] & 0x100000) == 0 && (v34 & 0x800) == 0)
    && (v229 || v216 != 5 || _wcsnicmp(String1[1], L"mhtml", 5u)) )
  {
    goto LABEL_161;
  }
  v140 = (*(_BYTE *)(v19 + 4860) & 8) == 0;
  v141 = 0;
  pwzURI = 0;
  if ( !v140 && (a1[94] & 0x100000) == 0 )
  {
    v142 = *(_QWORD *)(v19 + 4392);
    if ( v142 )
    {
      v143 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, LPCWSTR *))(*(_QWORD *)v142 + 160LL))(
               *(_QWORD *)(v19 + 4392),
               0,
               0,
               &pwzURI);
      v141 = (unsigned __int16 *)pwzURI;
      Uri = v143;
      if ( v143 < 0 )
      {
        CoTaskMemFree((LPVOID)pwzURI);
        goto LABEL_109;
      }
    }
  }
  v144 = (struct IUnknown **)(v19 + 4392);
  if ( !*(_QWORD *)(v19 + 4392) )
    goto LABEL_267;
  v145 = a1 + 94;
  LOBYTE(v31) = (a1[94] & 0x100000) == 0;
  if ( ((unsigned __int8)v31 & ((*(_BYTE *)(v19 + 4860) & 8) == 0)) != 0 )
    goto LABEL_267;
  if ( !v141 )
    goto LABEL_269;
  if ( !IsEqualUri(v33, v141, (unsigned int)v31, v32) )
  {
LABEL_267:
    TSmartPointer<CTransitionClient>::~TSmartPointer<CTransitionClient>((void *)(v19 + 4392));
    v146 = v219;
    *v144 = v219;
    ((void (__fastcall *)(struct IUnknown *))v146->lpVtbl->AddRef)(v146);
    *(_DWORD *)(v19 + 4860) |= 8u;
    v145 = a1 + 94;
  }
  v141 = (unsigned __int16 *)pwzURI;
LABEL_269:
  CoTaskMemFree(v141);
  v148 = v219;
  if ( (v174 & 0x800) == 0 )
    v148 = *v144;
  CreateURLMonikerForMHTHandler((struct IMoniker *)v148, &v190, v147);
  v149 = (*v145 & 0x100000) != 0 ? v226 : 0;
  TSmartPointer<CTransitionClient>::~TSmartPointer<CTransitionClient>((void *)(v19 + 4384));
  Uri = MimeOleObjectFromMoniker(v149, (_DWORD)v190, (_DWORD)v224, v150, v19 + 4384, (__int64)&v191);
  ((void (__fastcall *)(struct IMoniker *))v190->lpVtbl->Release)(v190);
  v35 = 0;
  if ( Uri < 0 )
    goto LABEL_30;
  ReplaceInterfaceFn(&v219, v191);
  Uri = CMarkup::ReplaceMonikerPtr((CMarkup *)a1, (struct IMoniker *)v191);
  if ( Uri )
    goto LABEL_30;
  if ( (*(_BYTE *)(v19 + 4860) & 4) == 0 )
  {
LABEL_161:
    v91 = v224;
    goto LABEL_162;
  }
  Uri = CreateBindCtx(0, &ppbc);
  if ( Uri < 0 )
    goto LABEL_30;
  v91 = ppbc;
  v224 = ppbc;
LABEL_162:
  v92 = v219;
  pwzURI = (LPCWSTR)v91;
  if ( !v219 )
    goto LABEL_24;
  UriFromMoniker = GetUriFromMoniker((struct IMoniker *)v219, v91, v31, 4u, lpString2, &pIUri);
  v35 = 0;
  Uri = UriFromMoniker;
  if ( !UriFromMoniker )
  {
    Uri = CMarkup::ReplaceMonikerPtr((CMarkup *)a1, (struct IMoniker *)v92);
    if ( !Uri )
    {
      v176 = pIUri;
      if ( pIUri )
        ((void (__fastcall *)(IUri *))pIUri->lpVtbl->AddRef)(pIUri);
      goto LABEL_26;
    }
  }
LABEL_25:
  if ( Uri )
    goto LABEL_30;
LABEL_26:
  Uri = CUString::Set((CUString *)&v202, v176, Uri_PROPERTY_ABSOLUTE_URI);
  if ( Uri < 0 )
    goto LABEL_30;
  v178 = IsSpecialUrl(v176);
  DwnDoc = CMarkup::GetDwnDoc((CMarkup *)a1);
  v37 = DwnDoc;
  if ( DwnDoc )
  {
    if ( a1 == *((__int64 **)DwnDoc + 14) )
      CDwnDoc::Disconnect(DwnDoc);
    CBaseFT::Release(v37);
    CBase::AddPointer(a1, 2147554357LL, 0);
  }
  v38 = (CDwnDoc *)MemoryProtection::HeapAllocClear<1>(g_hProcessHeap, 832);
  if ( !v38 || (v57 = CDwnDoc::CDwnDoc(v38), (v170 = v57) == 0) )
  {
    Uri = -2147024882;
    goto LABEL_30;
  }
  LOWORD(cchCount2) = 0;
  *(_QWORD *)&v195.vt = 26;
  *(_OWORD *)&v195.decVal.Lo32 = (unsigned __int64)v57;
  Uri = CAttrArray::Set(a1 + 3, 2147554357LL, &v195, 0, 4, cchCount2, 0);
  if ( !Uri )
  {
    v58 = a1[44];
    v180 = 0;
    if ( v58 )
    {
      v83 = *(_QWORD *)(v58 + 120);
      if ( v83 )
        v180 = *(struct CWindow **)(v83 + 136);
    }
    Uri = CUString::Set((CUString *)&v207, pIUri, Uri_PROPERTY_ABSOLUTE_URI);
    if ( Uri >= 0 )
    {
      if ( (*((_DWORD *)a1 + 187) & 0x8000000) == 0 || (*(_DWORD *)(v19 + 4864) & 0x2000) != 0 )
      {
        v59 = v174;
LABEL_79:
        if ( (*(_DWORD *)(v19 + 4856) & 0x40000000) != 0 )
        {
          if ( *(char *)(v19 + 4868) < 0 )
            CDoc::OnAmbientPropertyChange((CDoc *)v19, -5512);
        }
        else
        {
          CDoc::SetLoadfFromPrefs((CDoc *)v19);
        }
        if ( !*(_QWORD *)(v19 + 5552) )
        {
          Uri = CDoc::QueryVersionHost((CDoc *)v19);
          if ( Uri )
            goto LABEL_30;
        }
        Uri = CMarkup::HandleHistoryAndNavContext((CMarkup *)a1, (struct CDoc::LOADINFO *)v218);
        if ( Uri )
          goto LABEL_30;
        v60 = v226;
        v185[1] = v226;
        if ( (v59 & 0x200000000LL) != 0 )
        {
          LODWORD(v186) = 8;
          v61 = 8;
          HIDWORD(v188) = 8;
        }
        else
        {
          v61 = HIDWORD(v188);
        }
        if ( !(unsigned __int8)IsWebPlatformHostBehaviorSupported<13>(
                                 *(unsigned int *)(v19 + 5040),
                                 *(unsigned int *)(v19 + 5044),
                                 *(unsigned int *)(v19 + 5052),
                                 *(unsigned int *)(v19 + 5048)) )
        {
          v61 |= 0x200000u;
          HIDWORD(v188) = v61;
        }
        if ( !(unsigned __int8)IsWebPlatformHostBehaviorSupported<12>(
                                 *(unsigned int *)(v19 + 5040),
                                 *(unsigned int *)(v19 + 5044),
                                 *(unsigned int *)(v19 + 5052),
                                 *(unsigned int *)(v19 + 5048))
          && !a1[176] )
        {
          if ( *(__int64 (__fastcall **)())(*a1 + 984) != _vtguard )
            goto LABEL_72;
          v68 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64))(*a1 + 1000))(a1, 0, 1);
          if ( a1 == (__int64 *)v68 )
          {
            HIDWORD(v188) = v61 | 0x100000;
          }
          else if ( v68 )
          {
            v69 = *(void **)(v68 + 1408);
            v70 = 0;
            phDuplicatedDependencyHandle = 0;
            if ( v69 )
            {
              HttpDuplicateDependencyHandle(v69, &phDuplicatedDependencyHandle);
              v70 = phDuplicatedDependencyHandle;
            }
            a1[176] = (__int64)v70;
          }
        }
        v189 = v227;
        if ( !pwzURI )
        {
          v35 = 0;
          goto LABEL_90;
        }
        memset(&pvarg, 0, sizeof(pvarg));
        if ( CDoc::QueryService((CDoc *)v19, &IID_IHTMLWindow2, &IID_IHTMLWindow2, (void **)&v192) )
          goto LABEL_150;
        COmWindowProxy::get_opener((COmWindowProxy *)(*(_QWORD *)(v19 + 824) + 48LL), &pvarg);
        if ( !pvarg.vt )
        {
          VariantClear(&pvarg);
          if ( ((unsigned int (__fastcall *)(struct IUnknown *, VARIANTARG *))v192->lpVtbl[8].QueryInterface)(
                 v192,
                 &pvarg) )
          {
            goto LABEL_150;
          }
          v65 = *(CBase **)(v19 + 824);
          v66 = *((_QWORD *)v65 + 14);
          v195 = pvarg;
          v67 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v66 + 184LL))(v66, &v195);
          Uri = CBase::SetErrorInfo(v65, v67);
          if ( Uri )
            goto LABEL_108;
          if ( pvarg.vt == 9
            && ((**(unsigned int (__fastcall ***)(LONGLONG, GUID *, struct IUnknown **))pvarg.llVal)(
                  pvarg.llVal,
                  &IID_IHTMLWindow2,
                  &v199)
             || ((unsigned int (__fastcall *)(struct IUnknown *, struct IUnknown **))v199->lpVtbl[17].AddRef)(
                  v199,
                  &v182)
             || ((unsigned int (__fastcall *)(struct IUnknown *, BSTR *))v182->lpVtbl[13].AddRef)(v182, &v193)) )
          {
            goto LABEL_150;
          }
        }
        v130 = v182;
        if ( !v182 )
          goto LABEL_290;
        v126 = v220;
        if ( !v220 )
          goto LABEL_290;
        for ( i = L"about:blank"; ; ++i )
        {
          v124 = *v126;
          v125 = *i;
          if ( !*v126 )
          {
            v131 = -(v125 != 0);
            goto LABEL_219;
          }
          if ( v124 == v125 )
            goto LABEL_213;
          v128 = v125 - 65;
          if ( (unsigned __int16)(v124 - 65) <= 0x19u )
          {
            v124 += 32;
            if ( v128 > 0x19u )
              goto LABEL_227;
          }
          else if ( v128 > 0x19u )
          {
            goto LABEL_216;
          }
          v125 += 32;
LABEL_227:
          if ( v124 != v125 )
          {
LABEL_216:
            if ( ((v124 | v125) & 0xFF80) == 0 )
              goto LABEL_290;
            v129 = CompareStringW(0, 0x31001u, v126, -1, i, -1);
            if ( v129 <= 0 )
              goto LABEL_290;
            v130 = v182;
            v131 = v129 - 2;
LABEL_219:
            if ( !v131 )
            {
              phDuplicatedDependencyHandle = 0;
              if ( ((__int64 (__fastcall *)(struct IUnknown *, GUID *, HTTP_DEPENDENCY_HANDLE *))v130->lpVtbl->QueryInterface)(
                     v130,
                     &GUID_30510417_98b5_11cf_bb82_00aa00bdce0b,
                     &phDuplicatedDependencyHandle) >= 0 )
              {
                memset(&v195, 0, sizeof(v195));
                if ( (*(int (__fastcall **)(HTTP_DEPENDENCY_HANDLE, VARIANTARG *))(*(_QWORD *)phDuplicatedDependencyHandle
                                                                                 + 64LL))(
                       phDuplicatedDependencyHandle,
                       &v195) >= 0
                  && v195.vt == 4
                  && (unsigned int)CVariant::CoerceNumericToI4((CVariant *)&v195) )
                {
                  v238 = 10000 * v195.lVal;
                }
                (*(void (__fastcall **)(HTTP_DEPENDENCY_HANDLE))(*(_QWORD *)phDuplicatedDependencyHandle + 16LL))(phDuplicatedDependencyHandle);
                VariantClear(&v195);
              }
            }
LABEL_290:
            if ( !((unsigned int (__fastcall *)(struct IUnknown *, BSTR *))v192->lpVtbl[9].QueryInterface)(
                    v192,
                    &bstrString) )
            {
              if ( (*(_DWORD *)(v19 + 4864) & 0x800000) != 0
                && (unsigned int)CMarkup::IsPrimaryMarkup((CMarkup *)a1)
                && (!bstrString || !*bstrString) )
              {
                OuterWindow = CDoc::GetOuterWindow((CDoc *)v19);
                if ( OuterWindow )
                {
                  if ( bstrString )
                  {
                    SysFreeString(bstrString);
                    bstrString = 0;
                  }
                  CWindow::get_name((CWindow *)(*((_QWORD *)OuterWindow + 15) + 48LL), &bstrString);
                }
              }
              if ( (unsigned int)CMarkup::IsPrimaryMarkup((CMarkup *)a1)
                || (v132 = a1[44]) != 0
                && ((*(_BYTE *)(v132 + 16) & 1) == 0
                  ? (v133 = *(CMarkup **)(*(_QWORD *)(v132 + 120) + 104LL))
                  : (v133 = 0),
                    (unsigned int)CMarkup::IsPrimaryMarkup(v133)) )
              {
                if ( v134 )
                {
                  if ( *v134 )
                  {
                    Uri = COmWindowProxy::put_name((COmWindowProxy *)(*(_QWORD *)(v19 + 824) + 48LL), v134);
                    if ( Uri )
                    {
LABEL_108:
                      VariantClear(&pvarg);
                      goto LABEL_109;
                    }
                  }
                }
              }
            }
LABEL_150:
            v84 = 0;
            v85 = (struct IBindCtx *)pwzURI;
            GetBindContextParam((struct IBindCtx *)pwzURI, (struct CStr *)&v172, 0);
            GetBindContextParam(v85, v86, v87, (unsigned __int64 *)&ppURI);
            IsPrimaryMarkup = CMarkup::IsPrimaryMarkup((CMarkup *)a1);
            v89 = 0;
            if ( (IsPrimaryMarkup
               || (unsigned int)CMarkup::IsPendingPrimaryMarkup((CMarkup *)a1) && (v240 & 0x100) != 0
               || (a1[94] & 0x10) != 0)
              && pvarg.vt != v89 )
            {
              v20 = v172;
              v35 = 0;
              if ( v172 && *((_DWORD *)v172 - 1) >= 2u )
              {
LABEL_154:
                v84 = v20;
              }
              else if ( v193 )
              {
                CStr::Set((CStr *)&v172, v193);
                v20 = v172;
                goto LABEL_154;
              }
LABEL_155:
              if ( !v178 )
              {
LABEL_156:
                if ( !v84 || !*v84 )
                  goto LABEL_157;
                Uri = CMarkup::SetAAcreatorUrl((CMarkup *)a1, v84);
                if ( !Uri )
                {
                  if ( (a1[94] & 0x10) != 0 )
                  {
                    v135 = a1[44];
                    if ( v135 )
                    {
                      v136 = *(_QWORD *)(v135 + 120);
                      if ( v136 )
                      {
                        v137 = *(CMarkup **)(v136 + 104);
                        if ( v137 )
                        {
                          if ( (*((_DWORD *)v137 + 187) & 0x10000000) != 0 )
                            CMarkup::SetAAcreatorUrl(v137, v84);
                        }
                      }
                    }
                  }
                  goto LABEL_157;
                }
LABEL_313:
                VariantClear(&pvarg);
                goto LABEL_30;
              }
LABEL_312:
              Uri = AddBindContextParam(v85, (struct CStr *)&v172, 0, 0, 0);
              if ( !Uri )
                goto LABEL_156;
              goto LABEL_313;
            }
            if ( (unsigned int)CMarkup::IsPendingPrimaryMarkup((CMarkup *)a1) && (v60 & 0x400) == 0 )
            {
              v20 = v172;
              v35 = 0;
              goto LABEL_155;
            }
            v20 = v172;
            v35 = 0;
            if ( v178 )
            {
              v84 = v172;
              goto LABEL_312;
            }
LABEL_157:
            Uri = CMarkup::ProcessHTMLLoadOptions((CMarkup *)a1, (struct CDoc::LOADINFO *)v218);
            if ( Uri )
              goto LABEL_313;
            Uri = CMarkup::ProcessDwnBindInfo(
                    (CMarkup *)a1,
                    (struct CDoc::LOADINFO *)v218,
                    (struct CMarkup::LOADFLAGS *)v185,
                    v210[1],
                    v180,
                    v193);
            if ( Uri )
              goto LABEL_313;
            VariantClear(&pvarg);
            v35 = v224;
            v201 = ppURI;
LABEL_90:
            if ( pIUri )
            {
              pwzURI = 0;
              LODWORD(v172) = 0;
              ppURI = 0;
              Uri = GetUrlFromUri(pIUri, 2u, (unsigned __int16 **)&pwzURI, (unsigned int *)&v172);
              if ( Uri >= 0 )
                Uri = CreateUri(pwzURI, 0x3002B80u, 0, &ppURI);
              SysFreeString((BSTR)pwzURI);
              if ( Uri < 0 )
                goto LABEL_109;
              ReleaseInterface((struct IUnknown *)pIUri);
              pIUri = ppURI;
              Uri = CMarkup::SetUri((struct CMarkup *)a1, ppURI);
              if ( Uri )
                goto LABEL_109;
              if ( v223 )
              {
                Uri = CMarkup::SetUrlSearch((struct CMarkup *)a1, v223);
                if ( Uri )
                  goto LABEL_109;
              }
              v62 = v236;
              LODWORD(v172) = CMarkup::SetOriginalUri((struct CMarkup *)a1, v236);
              Uri = (int)v172;
              if ( (_DWORD)v172 )
                goto LABEL_109;
              LODWORD(phDuplicatedDependencyHandle) = 0;
              if ( v62
                && ((int (__fastcall *)(struct IUri *, __int64, HTTP_DEPENDENCY_HANDLE *))v62->lpVtbl->HasProperty)(
                     v62,
                     5,
                     &phDuplicatedDependencyHandle) >= 0
                && (_DWORD)phDuplicatedDependencyHandle
                && !v222 )
              {
                CUString::CUString((CUString *)&v195, v62, Uri_PROPERTY_FRAGMENT, (int *)&v172);
                Uri = (int)v172;
                if ( !(_DWORD)v172 )
                {
                  v152 = -1;
                  do
                    ++v152;
                  while ( v196[v152] );
                  v153 = v152 + 1;
                  v155 = v152 + 1;
                  v154 = 2 * (v152 + 1);
                  if ( !is_mul_ok(v155, 2u) )
                    v154 = -1;
                  v156 = (void *)MemoryProtection::HeapAlloc<0>(g_hProcessHeap, v154);
                  v222 = v156;
                  if ( v156 )
                  {
                    Uri = StringCchCopyW((unsigned __int16 *)v156, v153, v196);
                    *(_QWORD *)&v195.vt = &CUString::`vftable';
                    if ( !Uri )
                    {
                      CUString::Set((CUString *)&v195, 0, Uri_PROPERTY_RAW_URI);
                      goto LABEL_98;
                    }
LABEL_333:
                    CUString::Set((CUString *)&v195, 0, Uri_PROPERTY_RAW_URI);
                    goto LABEL_109;
                  }
                  Uri = -2147024882;
                }
                *(_QWORD *)&v195.vt = &CUString::`vftable';
                goto LABEL_333;
              }
LABEL_98:
              v63 = 0;
              if ( v35 )
              {
                BindContextParam = GetBindContextParam(v35, (struct CStr *)&v179, L"BIND_CONTEXT_BASE_DOMAIN");
                v21 = v179;
                v35 = 0;
                v63 = BindContextParam >= 0;
              }
              v64 = (char)v35;
              if ( *((int *)a1 + 212) >= 110000 )
                v64 = CMarkup::ApplyCreatorDomainChange((CMarkup *)a1, v174, v63, (struct CStr *)&v179, v180);
              CMarkup::UpdateSecurityID((CMarkup *)a1);
              if ( v64 )
              {
                v158 = CMarkup::Window((CMarkup *)a1);
                if ( v158 )
                  *((_DWORD *)v158 + 42) |= 1u;
              }
              CDoc::DeferUpdateTitle((CDoc *)v19);
            }
            else
            {
              v35 = 0;
            }
            if ( v178 == (_DWORD)v35 || (v159 = IsScriptUri(v176), v71 = v20, !v159) )
              v71 = v205[1];
            v72 = CMarkup::HandleSSLSecurity(
                    (CMarkup *)a1,
                    (struct CDoc::LOADINFO *)v218,
                    v71,
                    (struct CMarkup::LOADFLAGS *)v185,
                    (struct IMoniker **)&v197);
            Uri = v72;
            if ( v72 == -2147024891 )
            {
              if ( v200 )
                *((_BYTE *)v200 + 104) |= 1u;
              goto LABEL_30;
            }
            if ( v72 )
              goto LABEL_30;
            Uri = CMarkup::ProcessLoadFlags(
                    (CMarkup *)a1,
                    (struct CDoc::LOADINFO *)v218,
                    (struct CMarkup::LOADFLAGS *)v185);
            if ( Uri )
              goto LABEL_30;
            if ( v238 )
            {
              LOBYTE(v73) = v239;
              (*(void (__fastcall **)(__int64 *, _QWORD, __int64))(a1[103] + 32))(a1 + 103, v238, v73);
            }
            if ( v237 && *((_BYTE *)a1 + 864) == (_BYTE)v35 )
            {
              v160 = (unsigned __int64)(a1 + 104) & -(__int64)(a1 + 103 != 0);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v160 + 24LL))(v160);
            }
            v74 = a1[40];
            v75 = (CDoc *)v35;
            if ( v74 )
              v75 = *(CDoc **)(v74 + 16);
            v76 = v235;
            if ( v235 )
            {
              if ( v235 == 1 )
                goto LABEL_346;
              goto LABEL_354;
            }
            Uri = -2147467259;
            if ( v75 )
            {
              v76 = ++v235;
              if ( (unsigned int)CDoc::IsCpAutoDetect(v75) )
              {
                v80 = 50001;
                if ( g_cpDefault == 932 )
                  v80 = v77;
                v234 = v80;
              }
              else
              {
                v161 = 65001;
                v162 = *(_DWORD *)(*(_QWORD *)(v78 + 1008) + 80LL);
                if ( v162 - 1200 > v79 )
                  v161 = v162;
                v234 = v161;
              }
LABEL_346:
              if ( v180 )
              {
                v163 = (CMarkup *)*((_QWORD *)v180 + 13);
                if ( v163 )
                {
                  if ( (unsigned int)CMarkup::AccessAllowed((CMarkup *)a1, *((struct CMarkup *const *)v180 + 13)) )
                  {
                    CodePageCore = *((_DWORD *)v163 + 194);
                    if ( !CodePageCore )
                      CodePageCore = CMarkup::GetCodePageCore(v163);
                    if ( WindowsCodePageFromCodePage(CodePageCore) == 932 )
                    {
                      v234 = 50932;
                    }
                    else if ( (*((_DWORD *)v163 + 187) & 0x1000000) != 0 )
                    {
                      v234 = 50001;
                    }
                    else
                    {
                      v76 = 4;
                      v234 = CodePageCore;
                      v235 = 4;
                    }
                    v35 = 0;
                  }
                }
              }
LABEL_354:
              URLCodePage = v233;
              if ( !v233 )
              {
                URLCodePage = CMarkup::GetURLCodePage((CMarkup *)a1);
                v233 = URLCodePage;
              }
              CMarkup::SwitchCodePage(a1, v234, v76);
              if ( *(__int64 (__fastcall **)())(*a1 + 144) == _vtguard )
              {
                v94 = (struct CAttrArray **)(*(__int64 (__fastcall **)(__int64 *))(*a1 + 792))(a1);
                Uri = CAttrArray::SetSimple(
                        v94,
                        (const struct PROPERTYDESC *)&s_propdescCMarkupcodepageurl,
                        URLCodePage,
                        0);
                goto LABEL_169;
              }
            }
            else
            {
LABEL_169:
              if ( Uri )
                goto LABEL_30;
              v95 = *a1;
              v194[0] = (BSTR)v35;
              if ( *(__int64 (__fastcall **)())(v95 + 984) == _vtguard )
              {
                v96 = (CMarkup *)(*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64))(v95 + 1000))(a1, 0, 1);
                v97 = v96;
                if ( v96 )
                {
                  v98 = CMarkup::Uri(v96);
                  if ( v98 )
                    ((void (__fastcall *)(struct IUri *, BSTR *))v98->lpVtbl->GetAbsoluteUri)(v98, v194);
                }
                if ( (*(_BYTE *)(v19 + 4860) & 1) == 0 )
                {
                  GetPrivacIESettingsMode();
                  if ( v97 != (CMarkup *)a1 )
                    HIDWORD(v188) |= 0x800000u;
                  LODWORD(v186) = v186 | 0x800000;
                }
                if ( v97 == (CMarkup *)a1 )
                  HIDWORD(v188) |= 0x4000u;
                if ( DevToolbarHelper::IsDevConsoleRecording()
                  && ((unsigned int)CMarkup::IsPrimaryMarkup((CMarkup *)a1)
                   || (unsigned int)CMarkup::IsPendingPrimaryMarkup((CMarkup *)a1))
                  && (v174 & 0x800) == 0
                  && (*(_DWORD *)(v19 + 4864) & 0x6804000) == 0 )
                {
                  v179 = (unsigned __int16 *)v35;
                  if ( !(unsigned int)FormatAlloc(0, &v179, 0x100u, (const unsigned __int16 *)0xB12B) )
                  {
                    Url = CMarkup::GetUrl((const struct CMarkup *const)a1);
                    DevToolbarHelper::ConsoleWrite(L"HTML", DCML_INFORMATIONAL, 1300, v179, Url);
                    MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, v179, v166);
                  }
                }
                Uri = CMarkup::PrepareDwnDoc(a1, v170, v218, v205[1], v185, v217, v194[0], a5);
                if ( Uri )
                  goto LABEL_109;
                v99 = CMarkup::IsPrimaryMarkup((CMarkup *)a1);
                v100 = v228;
                if ( v99 || (unsigned int)CMarkup::IsPendingPrimaryMarkup((CMarkup *)a1) )
                {
                  v101 = IsWebPlatformHostBehaviorSupported<17>(
                           *(unsigned int *)(v19 + 5040),
                           *(unsigned int *)(v19 + 5044),
                           *(unsigned int *)(v19 + 5052),
                           *(unsigned int *)(v19 + 5048));
                  v102 = v174;
                  if ( !v101 && (v174 & 0x800) == 0 && !v100 )
                  {
                    v103 = 3;
                    v104 = (_OWORD *)((char *)v170 + 196);
                    v105 = v248;
                    do
                    {
                      v106 = v104[1];
                      *v105 = *v104;
                      v107 = v104[2];
                      v105[1] = v106;
                      v108 = v104[3];
                      v105[2] = v107;
                      v109 = v104[4];
                      v105[3] = v108;
                      v110 = v104[5];
                      v105[4] = v109;
                      v111 = v104[6];
                      v105[5] = v110;
                      v112 = v104[7];
                      v104 += 8;
                      v105[6] = v111;
                      v105[7] = v112;
                      v105 += 8;
                      --v103;
                    }
                    while ( v103 );
                    v113 = v104[1];
                    *v105 = *v104;
                    v114 = v104[2];
                    v115 = *((_QWORD *)v104 + 6);
                    v105[1] = v113;
                    v105[2] = v114;
                    *((_QWORD *)v105 + 6) = v115;
                    CMarkup::OutputCompatViewConsoleMessage(
                      (CMarkup *)a1,
                      (const struct __MIDL___MIDL_itf_browsermode_0000_0000_0011 *)v248);
                  }
                }
                else
                {
                  v102 = v174;
                }
                if ( DevToolbarHelper::IsDevConsoleRecording()
                  && ((unsigned int)CMarkup::IsPrimaryMarkup((CMarkup *)a1)
                   || (unsigned int)CMarkup::IsPendingPrimaryMarkup((CMarkup *)a1))
                  && !(unsigned __int8)IsWebPlatformHostBehaviorSupported<17>(
                                         *(unsigned int *)(v19 + 5040),
                                         *(unsigned int *)(v19 + 5044),
                                         *(unsigned int *)(v19 + 5052),
                                         *(unsigned int *)(v19 + 5048))
                  && (v102 & 0x800) == 0
                  && !v100
                  && (*(_DWORD *)(v19 + 4864) & 0x6804000) == 0 )
                {
                  CMarkup::OutputMinLayoutWidthCVListConsoleMessage((CMarkup *)a1);
                }
                v116 = v225;
                if ( v225 )
                {
                  Uri = CBase::AddPointer(a1, 2147554355LL, v225);
                  if ( Uri )
                    goto LABEL_109;
                  _InterlockedIncrement((volatile signed __int32 *)&v116[2]);
                }
                Uri = CMarkup::PrepareHtmlLoadInfo(
                        (CMarkup *)a1,
                        (struct HTMLOADINFO *)v242,
                        (struct CDoc::LOADINFO *)v218,
                        v176,
                        (struct IMoniker *)v197,
                        v170);
                *(_QWORD *)(v247 + 136) |= (unsigned __int64)v201 & 0x200000000000000LL;
                if ( !Uri )
                {
                  if ( CMarkup::GetStmDirty((CMarkup *)a1) )
                  {
                    *(_DWORD *)(v19 + 180) = 0x7FFFFFFF;
                  }
                  else if ( CMarkup::HasPrimaryWindow((CMarkup *)a1) )
                  {
                    *(_DWORD *)(v19 + 180) = 0;
                  }
                  CMarkup::HandlePicsSupport((CMarkup *)a1, (struct CDoc::LOADINFO *)v218);
                  v244 = (v240 >> 6) & 1;
                  v117 = (CAPState *)a1[27];
                  v243 = (v240 >> 7) & 1;
                  if ( v117 )
                  {
                    CAPState::Attach(v117, (struct CMarkup *)a1);
                    v121 = CMarkup::GetUrl((const struct CMarkup *const)a1);
                    if ( (unsigned int)IsPhishFilterPage(v121, *(_QWORD *)(v19 + 4704)) )
                    {
                      *(_DWORD *)(a1[27] + 8) |= 1u;
                      CAPState::SetThreats((CAPState *)a1[27], v121);
                    }
                  }
                  v118 = CMarkup::GetUrl((const struct CMarkup *const)a1);
                  if ( CURLBlock::s_IsBlockPageUrl(v118) )
                    *((_BYTE *)a1 + 249) = 1;
                  if ( (a1[94] & 0x100000) != 0
                    && v181
                    && (*(_DWORD *)(v19 + 4864) & 0x4000) == 0
                    && (!(unsigned int)CFeatureControlKey::_CoInternetIsFeatureEnabledInternal((CFeatureControlKey *)&FCK::FEATURE_SET_BROWSER_EMULATION_STATE)
                     || CDoc::HasExplicitWebPlatformVersion((CDoc *)v19)) )
                  {
                    memset_0(v248, 0, 0x1B8u);
                    if ( (int)CMarkup::GetEmulationState(
                                (CMarkup *)a1,
                                (struct __MIDL___MIDL_itf_browsermode_0000_0000_0011 *)v248) >= 0 )
                      CoInternetSetBrowserEmulationState(v248);
                  }
                  if ( (*((_DWORD *)v170 + 39) & 0x200000) != 0 && (*((_BYTE *)v170 + 152) & 0x10) != 0 )
                    DeleteAppCacheStorageForUri(v176);
                  v119 = a1[40];
                  v35 = 0;
                  v120 = 0;
                  if ( v119 )
                    v120 = *(CDoc **)(v119 + 16);
                  if ( CDoc::IsPrerendered(v120) )
                  {
                    if ( (v174 & 0x2000000000LL) != 0 )
                    {
                      v167 = 99;
                    }
                    else
                    {
                      v167 = 98;
                      if ( (v174 & 0x4000000000LL) != 0 )
                        v167 = 100;
                    }
                    v246 = v167;
                  }
                  Uri = CMarkup::Load((CMarkup *)a1, (struct HTMLOADINFO *)v242);
                  goto LABEL_30;
                }
LABEL_109:
                v35 = 0;
                goto LABEL_30;
              }
            }
LABEL_72:
            _report_securityfailure(1);
          }
LABEL_213:
          ++v126;
        }
      }
      v81 = *(_DWORD *)(v19 + 4868);
      v59 = v174;
      if ( (v81 & 0x800000) == 0 || (v81 & 0x80u) != 0 || (v174 & 0x800) != 0 )
        goto LABEL_79;
      v82 = 0;
      LODWORD(phDuplicatedDependencyHandle) = 0;
      if ( v210[1] && *(_QWORD *)(v19 + 5136) )
      {
        Uri = CDoc::IsErrorUrl((CDoc *)v19, v210[1], (int *)&phDuplicatedDependencyHandle);
        if ( Uri )
          goto LABEL_30;
        v82 = (int)phDuplicatedDependencyHandle;
      }
      if ( v82 )
        goto LABEL_79;
      Uri = CMarkup::CheckZoneCrossing((CMarkup *)a1, pIUri);
      if ( !Uri )
        goto LABEL_79;
    }
  }
LABEL_30:
  *((_BYTE *)a1 + 98) &= ~0x20u;
  if ( v19 )
    *(_DWORD *)(v19 + 4860) &= ~4u;
  ReleaseInterface((struct IUnknown *)v176);
  ReleaseInterface((struct IUnknown *)pIUri);
  ReleaseInterface(v197);
  ReleaseInterface((struct IUnknown *)ppbc);
  ReleaseInterface(v191);
  ReleaseInterface(v218[0]);
  ReleaseInterface(v219);
  MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, v230, v39);
  MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, v231, v40);
  MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, v232, v41);
  v42 = v225 + 3;
  if ( !v225 )
    v42 = (struct IUnknown *)v35;
  ReleaseInterface(v42);
  ReleaseInterface(v192);
  ReleaseInterface(v199);
  ReleaseInterface(v182);
  SysFreeString(bstrString);
  SysFreeString(v193);
  SysFreeString(v194[0]);
  if ( v222 )
    MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, v222, v44);
  if ( Uri && v200 && (*((_BYTE *)v200 + 16) & 2) == 0 )
    CMarkup::ShowWaitCursor(v200, 0);
  v45 = v203;
  v202 = &CUString::`vftable';
  v46 = (int)v35;
  LOBYTE(v46) = v203 != 0;
  v47 = (int)v35;
  if ( v46 || (LOBYTE(v47) = v204 != 11, v47) )
  {
    if ( v205[0] )
    {
      SysFreeString(v205[0]);
      v45 = v203;
      v205[0] = (BSTR)v35;
    }
    v205[1] = (BSTR)v35;
    v206 = (int)v35;
    if ( v46 && v45 )
    {
      ((void (__fastcall *)(struct IBindCtx *))v45->lpVtbl->Release)(v45);
      v203 = v35;
    }
  }
  v48 = v208;
  v50 = (int)v35;
  v204 = 11;
  v49 = (int)v35;
  v207 = &CUString::`vftable';
  LOBYTE(v50) = v208 != 0;
  if ( v50 || (LOBYTE(v49) = v209 != 11, v49) )
  {
    if ( v210[0] )
    {
      SysFreeString(v210[0]);
      v48 = v208;
      v210[0] = (BSTR)v35;
    }
    v210[1] = (BSTR)v35;
    v211 = (int)v35;
    if ( v50 && v48 )
    {
      ((void (__fastcall *)(struct IBindCtx *))v48->lpVtbl->Release)(v48);
      v208 = v35;
    }
  }
  v51 = v213;
  v53 = (int)v35;
  v209 = 11;
  v52 = (int)v35;
  v212 = &CUString::`vftable';
  LOBYTE(v53) = v213 != 0;
  if ( v53 || (LOBYTE(v52) = v214 != 11, v52) )
  {
    if ( String1[0] )
    {
      SysFreeString(String1[0]);
      v51 = v213;
      String1[0] = (wchar_t *)v35;
    }
    String1[1] = (wchar_t *)v35;
    v216 = (int)v35;
    if ( v53 && v51 )
    {
      ((void (__fastcall *)(struct IBindCtx *))v51->lpVtbl->Release)(v51);
      v213 = v35;
    }
  }
  v214 = 11;
  if ( v21 )
    MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, v21 - 2, v44);
  if ( v20 )
    MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, v20 - 2, v44);
  if ( v245 )
    CDownloadInitiatorInfo::`scalar deleting destructor'(v245, v43);
  return (unsigned int)Uri;
}

```

## disassembly

```asm
0x18022080c  mov     [rsp-8+arg_10], rbx
0x180220811  push    rbp
0x180220812  push    rsi
0x180220813  push    rdi
0x180220814  push    r12
0x180220816  push    r13
0x180220818  push    r14
0x18022081a  push    r15
0x18022081c  lea     rbp, [rsp-530h]
0x180220824  sub     rsp, 630h
0x18022082b  mov     rax, cs:__security_cookie
0x180220832  xor     rax, rsp
0x180220835  mov     [rbp+560h+var_40], rax
0x18022083c  mov     [rsp+660h+var_600], r8
0x180220841  mov     r12, rdx
0x180220844  mov     r15, rcx
0x180220847  mov     [rbp+560h+var_458], r9
0x18022084e  xor     edx, edx; Val
0x180220850  lea     rcx, [rbp+560h+var_340]; void *
0x180220857  mov     r8d, 138h; Size
0x18022085d  call    memset_0
0x180220862  xor     esi, esi
0x180220864  lea     rcx, [rbp+560h+var_450]
0x18022086b  mov     [rbp+560h+var_510], rsi
0x18022086f  mov     rax, r12
0x180220872  mov     [rsp+660h+var_5F0], rsi
0x180220877  mov     [rsp+660h+pIUri], rsi
0x18022087c  lea     edx, [rsi+2]
0x18022087f  lea     r8d, [rdx+7Eh]
0x180220883  movups  xmm0, xmmword ptr [rax]
0x180220886  movups  xmm1, xmmword ptr [rax+10h]
0x18022088a  movups  xmmword ptr [rcx], xmm0
0x18022088d  movups  xmm0, xmmword ptr [rax+20h]
0x180220891  movups  xmmword ptr [rcx+10h], xmm1
0x180220895  movups  xmm1, xmmword ptr [rax+30h]
0x180220899  movups  xmmword ptr [rcx+20h], xmm0
0x18022089d  movups  xmm0, xmmword ptr [rax+40h]
0x1802208a1  movups  xmmword ptr [rcx+30h], xmm1
0x1802208a5  movups  xmm1, xmmword ptr [rax+50h]
0x1802208a9  movups  xmmword ptr [rcx+40h], xmm0
0x1802208ad  movups  xmm0, xmmword ptr [rax+60h]
0x1802208b1  movups  xmmword ptr [rcx+50h], xmm1
0x1802208b5  movups  xmm1, xmmword ptr [rax+70h]
0x1802208b9  add     rax, r8
0x1802208bc  movups  xmmword ptr [rcx+60h], xmm0
0x1802208c0  movups  xmmword ptr [rcx+70h], xmm1
0x1802208c4  add     rcx, r8
0x1802208c7  sub     rdx, 1
0x1802208cb  jnz     short loc_180220883
0x1802208cd  movups  xmm0, xmmword ptr [rax]
0x1802208d0  mov     rax, [r15+140h]
0x1802208d7  mov     r13, rsi
0x1802208da  movups  xmmword ptr [rcx], xmm0
0x1802208dd  test    rax, rax
0x1802208e0  jz      short loc_1802208E6
0x1802208e2  mov     r13, [rax+10h]
0x1802208e6  mov     eax, 0Bh
0x1802208eb  mov     [rbp+560h+var_560], rsi
0x1802208ef  mov     [rbp+560h+var_478], eax
0x1802208f5  lea     rcx, ??_7CUString@@6B@; const CUString::`vftable'
0x1802208fc  mov     [rbp+560h+var_4A8], eax
0x180220902  lea     r14, __vtguard
0x180220909  mov     [rbp+560h+var_4D8], eax
0x18022090f  xorps   xmm0, xmm0
0x180220912  mov     rax, rsi
0x180220915  mov     [rbp+560h+var_500], rsi
0x180220919  mov     [rbp+560h+var_4F0], rax
0x18022091d  mov     rbx, rsi
0x180220920  mov     [rbp+560h+ppURI], rax
0x180220924  mov     rdi, rsi
0x180220927  mov     [rbp+560h+var_598], eax
0x18022092a  mov     rax, [r15]
0x18022092d  mov     [rbp+560h+var_5C0], rsi
0x180220931  mov     [rsp+660h+bstrString], rsi
0x180220936  mov     [rbp+560h+var_558], rsi
0x18022093a  mov     [rbp+560h+var_550], rsi
0x18022093e  mov     [rbp+560h+ppbc], rsi
0x180220942  mov     [rbp+560h+var_568], rsi
0x180220946  mov     [rbp+560h+var_488], rcx
0x18022094d  mov     [rbp+560h+var_480], rsi
0x180220954  movdqu  xmmword ptr [rbp+560h+String1], xmm0
0x18022095c  mov     [rbp+560h+var_460], esi
0x180220962  mov     [rbp+560h+var_4B8], rcx
0x180220969  mov     [rbp+560h+var_4B0], rsi
0x180220970  movdqu  xmmword ptr [rbp+560h+var_4A0], xmm0
0x180220978  mov     [rbp+560h+var_490], esi
0x18022097e  mov     [rbp+560h+var_4E8], rcx
0x180220982  mov     [rbp+560h+var_4E0], rsi
0x180220989  movdqu  xmmword ptr [rbp+560h+var_4D0], xmm0
0x180220991  mov     [rbp+560h+var_4C0], esi
0x180220997  mov     [rbp+560h+var_570], rsi
0x18022099b  mov     [rsp+660h+var_610], rbx
0x1802209a0  mov     [rbp+560h+var_5D8], rsi
0x1802209a4  mov     [rbp+560h+var_590], rsi
0x1802209a8  mov     [rbp+560h+var_588], rsi
0x1802209ac  mov     [rbp+560h+var_580], rsi
0x1802209b0  mov     [rbp+560h+var_5D0], r15
0x1802209b4  cmp     [rax+3D8h], r14
0x1802209bb  jnz     loc_180220ED4
0x1802209c1  mov     rax, [rax+478h]
0x1802209c8  mov     rcx, r15
0x1802209cb  mov     [rbp+560h+var_4F8], rsi
0x1802209cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802209d4  test    r13, r13
0x1802209d7  jz      loc_18022267A
0x1802209dd  mov     al, [r15+62h]
0x1802209e1  test    al, 20h
0x1802209e3  jnz     loc_18022267A
0x1802209e9  or      al, 20h
0x1802209eb  mov     [r15+62h], al
0x1802209ef  mov     rax, [r15]
0x1802209f2  cmp     [rax+3D8h], r14
0x1802209f9  jnz     loc_180220ED4
0x1802209ff  mov     rax, [rax+480h]
0x180220a06  mov     rcx, r15
0x180220a09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180220a0e  lea     rsi, [r13+191Ch]
0x180220a15  mov     rcx, r15; this
0x180220a18  mov     rdx, rsi; struct SandboxFlags *
0x180220a1b  call    ?EnforceSandbox@CMarkup@@QEAAJAEBUSandboxFlags@@@Z; CMarkup::EnforceSandbox(SandboxFlags const &)
0x180220a20  mov     r14d, eax
0x180220a23  mov     al, [rsi]
0x180220a25  shl     al, 5
0x180220a28  xor     esi, esi
0x180220a2a  xor     al, [r15+68h]
0x180220a2e  and     al, 20h
0x180220a30  xor     [r15+68h], al
0x180220a34  test    r14d, r14d
0x180220a37  js      loc_180221231
0x180220a3d  mov     rax, [r15+160h]
0x180220a44  lea     r14d, [rsi+1]
0x180220a48  test    rax, rax
0x180220a4b  jnz     loc_180220E97
0x180220a51  mov     rcx, [rbp+560h+var_450]
0x180220a58  mov     [r12+50h], rsi
0x180220a5d  mov     [r12+98h], rsi
0x180220a65  mov     [r12+0A0h], rsi
0x180220a6d  mov     [r12+0A8h], rsi
0x180220a75  mov     [r12+38h], rsi
0x180220a7a  test    rcx, rcx
0x180220a7d  jnz     loc_180221CB6
0x180220a83  mov     rcx, [rbp+560h+var_430]; this
0x180220a8a  test    rcx, rcx
0x180220a8d  jnz     loc_180220EC3
0x180220a93  mov     rax, [r15+160h]
0x180220a9a  movzx   r10d, [rbp+560h+var_344]
0x180220aa2  test    rax, rax
0x180220aa5  jnz     loc_1802219FC
0x180220aab  mov     [rbp+560h+var_5C8], esi
0x180220aae  movzx   eax, r10w
0x180220ab2  shr     ax, 0Bh
0x180220ab6  shl     al, 4
0x180220ab9  xor     al, [r15+68h]
0x180220abd  and     al, 10h
0x180220abf  xor     [r15+68h], al
0x180220ac3  bt      r10w, 0Ch
0x180220ac9  jb      loc_180221CC7
0x180220acf  test    [rbp+560h+var_342], r14b
0x180220ad6  jnz     loc_180221A6B
0x180220adc  and     dword ptr [r13+12F8h], 0FFFC3FFFh
0x180220ae7  lea     rdx, [rbp+560h+var_450]; struct CDoc::LOADINFO *
0x180220aee  mov     [r13+1170h], rbx
0x180220af5  call    ?EnsureMoniker@CMarkup@@QEAAJPEAULOADINFO@CDoc@@@Z; CMarkup::EnsureMoniker(CDoc::LOADINFO *)
0x180220afa  mov     r14d, eax
0x180220afd  test    eax, eax
0x180220aff  jnz     loc_180221231
0x180220b05  mov     r12, [rbp+560h+var_420]
0x180220b0c  test    r12, r12
0x180220b0f  jnz     loc_180221CD5
0x180220b15  and     byte ptr [r15+6Ah], 0DFh
0x180220b1a  mov     rdx, [rsp+660h+var_600]
0x180220b1f  mov     rax, rdx
0x180220b22  shr     rax, 22h
0x180220b26  and     al, 20h
0x180220b28  or      [r15+6Ah], al
0x180220b2c  cmp     [rbp+560h+var_430], rsi
0x180220b33  jnz     loc_1802215B1
0x180220b39  mov     rax, [rbp+560h+var_408]
0x180220b40  mov     [rsp+660h+pwzURI], rax
0x180220b45  lea     rdx, [rsp+660h+var_5F0]; struct IUri **
0x180220b4a  mov     rcx, r15; struct CMarkup *
0x180220b4d  call    ?GetUri@CMarkup@@SAJQEBV1@PEAPEAUIUri@@@Z; CMarkup::GetUri(CMarkup const * const,IUri * *)
0x180220b52  mov     r14d, eax
0x180220b55  xor     r12d, r12d
0x180220b58  test    r14d, r14d
0x180220b5b  jnz     short loc_180220BBC
0x180220b5d  mov     rdx, [rsp+660h+var_5F0]; struct IUri *
0x180220b62  lea     rcx, [rbp+560h+var_4E8]; this
0x180220b66  xor     r8d, r8d; enum __MIDL_IUri_0001
0x180220b69  call    ?Set@CUString@@QEAAJPEAUIUri@@W4__MIDL_IUri_0001@@@Z; CUString::Set(IUri *,__MIDL_IUri_0001)
0x180220b6e  mov     r14d, eax
0x180220b71  test    eax, eax
0x180220b73  js      short loc_180220BBC
0x180220b75  mov     rcx, [rsp+660h+var_5F0]; struct IUri *
0x180220b7a  call    ?IsSpecialUrl@@YAHPEAUIUri@@@Z; IsSpecialUrl(IUri *)
0x180220b7f  mov     rcx, r15; this
0x180220b82  mov     [rbp+560h+var_5E0], eax
0x180220b85  call    ?GetDwnDoc@CMarkup@@QEAAPEAVCDwnDoc@@XZ; CMarkup::GetDwnDoc(void)
0x180220b8a  mov     rsi, rax
0x180220b8d  mov     r14d, 80011435h
0x180220b93  test    rax, rax
0x180220b96  jnz     loc_180221F1F
0x180220b9c  mov     rcx, cs:g_hProcessHeap
0x180220ba3  mov     edx, 340h
0x180220ba8  call    ??$HeapAllocClear@$00@MemoryProtection@@YAPEAXPEAX_K@Z; MemoryProtection::HeapAllocClear<1>(void *,unsigned __int64)
0x180220bad  test    rax, rax
0x180220bb0  jnz     loc_180220EDF
0x180220bb6  mov     r14d, 8007000Eh
0x180220bbc  and     byte ptr [r15+62h], 0DFh
0x180220bc1  test    r13, r13
0x180220bc4  jnz     loc_18022268E
0x180220bca  mov     rcx, [rsp+660h+var_5F0]; struct IUnknown *
0x180220bcf  call    ?ReleaseInterface@@YAXPEAUIUnknown@@@Z; ReleaseInterface(IUnknown *)
0x180220bd4  mov     rcx, [rsp+660h+pIUri]; struct IUnknown *
0x180220bd9  call    ?ReleaseInterface@@YAXPEAUIUnknown@@@Z; ReleaseInterface(IUnknown *)
0x180220bde  mov     rcx, [rbp+560h+var_510]; struct IUnknown *
0x180220be2  call    ?ReleaseInterface@@YAXPEAUIUnknown@@@Z; ReleaseInterface(IUnknown *)
0x180220be7  mov     rcx, [rbp+560h+ppbc]; struct IUnknown *
0x180220beb  call    ?ReleaseInterface@@YAXPEAUIUnknown@@@Z; ReleaseInterface(IUnknown *)
0x180220bf0  mov     rcx, [rbp+560h+var_568]; struct IUnknown *
0x180220bf4  call    ?ReleaseInterface@@YAXPEAUIUnknown@@@Z; ReleaseInterface(IUnknown *)
0x180220bf9  mov     rcx, [rbp+560h+var_450]; struct IUnknown *
0x180220c00  call    ?ReleaseInterface@@YAXPEAUIUnknown@@@Z; ReleaseInterface(IUnknown *)
0x180220c05  mov     rcx, [rbp+560h+var_430]; struct IUnknown *
0x180220c0c  call    ?ReleaseInterface@@YAXPEAUIUnknown@@@Z; ReleaseInterface(IUnknown *)
0x180220c11  mov     rdx, [rbp+560h+var_3B8]; void *
0x180220c18  mov     rcx, cs:g_hProcessHeap; this
0x180220c1f  call    ?HeapFree@MemoryProtection@@YAHPEAX0@Z; MemoryProtection::HeapFree(void *,void *)
0x180220c24  mov     rdx, [rbp+560h+var_3B0]; void *
0x180220c2b  mov     rcx, cs:g_hProcessHeap; this
0x180220c32  call    ?HeapFree@MemoryProtection@@YAHPEAX0@Z; MemoryProtection::HeapFree(void *,void *)
0x180220c37  mov     rdx, [rbp+560h+var_3A8]; void *
0x180220c3e  mov     rcx, cs:g_hProcessHeap; this
0x180220c45  call    ?HeapFree@MemoryProtection@@YAHPEAX0@Z; MemoryProtection::HeapFree(void *,void *)
0x180220c4a  mov     rsi, [rbp+560h+var_400]
0x180220c51  lea     rcx, [rsi+18h]
0x180220c55  test    rsi, rsi
0x180220c58  jnz     short loc_180220C5D
0x180220c5a  mov     rcx, r12; struct IUnknown *
0x180220c5d  call    ?ReleaseInterface@@YAXPEAUIUnknown@@@Z; ReleaseInterface(IUnknown *)
0x180220c62  mov     rcx, [rbp+560h+var_560]; struct IUnknown *
0x180220c66  call    ?ReleaseInterface@@YAXPEAUIUnknown@@@Z; ReleaseInterface(IUnknown *)
0x180220c6b  mov     rcx, [rbp+560h+var_500]; struct IUnknown *
0x180220c6f  call    ?ReleaseInterface@@YAXPEAUIUnknown@@@Z; ReleaseInterface(IUnknown *)
0x180220c74  mov     rcx, [rbp+560h+var_5C0]; struct IUnknown *
0x180220c78  call    ?ReleaseInterface@@YAXPEAUIUnknown@@@Z; ReleaseInterface(IUnknown *)
0x180220c7d  mov     rcx, [rsp+660h+bstrString]; bstrString
0x180220c82  call    cs:__imp_SysFreeString
0x180220c88  mov     rcx, [rbp+560h+var_558]; bstrString
0x180220c8c  call    cs:__imp_SysFreeString
0x180220c92  mov     rcx, [rbp+560h+var_550]; bstrString
0x180220c96  call    cs:__imp_SysFreeString
0x180220c9c  mov     rax, [rbp+560h+var_418]
0x180220ca3  test    rax, rax
0x180220ca6  jnz     loc_18022269B
0x180220cac  test    r14d, r14d
0x180220caf  jnz     loc_1802226AF
0x180220cb5  mov     rcx, [rbp+560h+var_4E0]
0x180220cbc  lea     r13, ??_7CUString@@6B@; const CUString::`vftable'
0x180220cc3  test    rcx, rcx
0x180220cc6  mov     [rbp+560h+var_4E8], r13
0x180220cca  mov     esi, r12d
0x180220ccd  mov     r15d, 0Bh
0x180220cd3  setnz   sil
0x180220cd7  mov     eax, r12d
0x180220cda  cmp     [rbp+560h+var_4D8], r15d
0x180220ce1  setnz   al
0x180220ce4  test    esi, esi
0x180220ce6  jz      loc_180220E70
0x180220cec  mov     rax, [rbp+560h+var_4D0]
0x180220cf3  test    rax, rax
0x180220cf6  jnz     loc_1802226C1
0x180220cfc  mov     [rbp+560h+var_4D0+8], r12
0x180220d03  mov     [rbp+560h+var_4C0], r12d
0x180220d0a  test    esi, esi
0x180220d0c  jz      short loc_180220D26
0x180220d0e  test    rcx, rcx
0x180220d11  jz      short loc_180220D26
0x180220d13  mov     rax, [rcx]
0x180220d16  mov     rax, [rax+10h]
0x180220d1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180220d1f  mov     [rbp+560h+var_4E0], r12
0x180220d26  mov     rcx, [rbp+560h+var_4B0]
0x180220d2d  mov     esi, r12d
0x180220d30  test    rcx, rcx
0x180220d33  mov     [rbp+560h+var_4D8], r15d
0x180220d3a  mov     eax, r12d
0x180220d3d  mov     [rbp+560h+var_4B8], r13
0x180220d44  setnz   sil
0x180220d48  cmp     [rbp+560h+var_4A8], r15d
0x180220d4f  setnz   al
0x180220d52  test    esi, esi
0x180220d54  jz      loc_180220E7D
0x180220d5a  mov     rax, [rbp+560h+var_4A0]
0x180220d61  test    rax, rax
0x180220d64  jnz     loc_1802226DD
0x180220d6a  mov     [rbp+560h+var_4A0+8], r12
0x180220d71  mov     [rbp+560h+var_490], r12d
0x180220d78  test    esi, esi
0x180220d7a  jz      short loc_180220D94
  ... truncated ...
```
