# GEN_PROJECT::CopyToITypeLib(IExeFile *)

- ea: `0x18012abcc`
- end: `0x18012cf5e`
- name: `?CopyToITypeLib@GEN_PROJECT@@QEAAJPEAUIExeFile@@@Z`
- size: `9106`
- prototype: `__int64 __fastcall(GEN_PROJECT *__hidden this, struct IExeFile *)`
- caller_count: `1`
- callee_count: `56`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18012549c`

## callees

- `0x18002be9c`
- `0x18008392c`
- `0x1800e6178`
- `0x1800e62d4`
- `0x1800e64cc`
- `0x1800e64dc`
- `0x1800ec670`
- `0x1801003dc`
- `0x180107260`
- `0x18010739c`
- `0x18011233c`
- `0x180118d28`
- `0x18011d9d4`
- `0x18011d9e8`
- `0x18011d9fc`
- `0x18011db84`
- `0x18011fd24`
- `0x18011fd40`
- `0x18011fd60`
- `0x18011fda8`
- `0x1801258a0`
- `0x1801258d0`
- `0x18012abcc`
- `0x180133038`
- `0x180133048`
- `0x1801331a8`
- `0x1801331dc`
- `0x180133b00`
- `0x180134fe8`
- `0x1801426f0`
- `0x18014275c`
- `0x180142894`
- `0x180142948`
- `0x1801487bc`
- `0x18014f0b0`
- `0x180176030`
- `0x18017608c`
- `0x1801761d0`
- `0x18017623c`
- `0x18017a42c`
- `0x18017a9a0`
- `0x18017ee30`
- `0x180180830`
- `0x1801810a0`
- `0x18019a06c`
- `0x18029a3a4`
- `0x18029aec4`
- `0x18029cb4c`
- `0x18029ce94`
- `0x18029d42c`

## import_xrefs

- `MSVCR100!strcpy_s` at `0x18012ad49`
- `MSVCR100!strcpy_s` at `0x18012ad49`
- `MSVCR100!remove` at `0x18012cf3e`
- `MSVCR100!remove` at `0x18012cf3e`
- `KERNEL32!GetTempPathA` at `0x18012acfd`
- `KERNEL32!GetTempPathA` at `0x18012acfd`
- `KERNEL32!GetTempFileNameA` at `0x18012ad2b`
- `KERNEL32!GetTempFileNameA` at `0x18012ad69`
- `KERNEL32!GetTempFileNameA` at `0x18012ad2b`
- `KERNEL32!GetTempFileNameA` at `0x18012ad69`
- `KERNEL32!MultiByteToWideChar` at `0x18012ada4`
- `KERNEL32!MultiByteToWideChar` at `0x18012ada4`
- `OLEAUT32!__imp_SysFreeString` at `0x18012cdac`
- `OLEAUT32!__imp_SysFreeString` at `0x18012cdba`
- `OLEAUT32!__imp_SysFreeString` at `0x18012cdc8`
- `OLEAUT32!__imp_SysFreeString` at `0x18012cdd6`
- `OLEAUT32!__imp_SysFreeString` at `0x18012cdac`
- `OLEAUT32!__imp_SysFreeString` at `0x18012cdba`
- `OLEAUT32!__imp_SysFreeString` at `0x18012cdc8`
- `OLEAUT32!__imp_SysFreeString` at `0x18012cdd6`

## pseudocode

```c
__int64 __fastcall GEN_PROJECT::CopyToITypeLib(
        GEN_PROJECT *this,
        const wchar_t *a2,
        const wchar_t *a3,
        unsigned int a4)
{
  enum tagSYSKIND Syskind; // eax
  unsigned __int16 v6; // ax
  struct _GUID *v7; // rax
  unsigned int v8; // eax
  INSTMGR *v9; // rax
  INSTMGR *v10; // rax
  unsigned int v11; // eax
  INSTMGR *v12; // rax
  void **v13; // rdx
  void **v14; // r8
  int v15; // r9d
  struct INSTMGR *v16; // rax
  void **v17; // rdx
  void **v18; // r8
  int v19; // r9d
  INSTMGR *v20; // rax
  INSTMGR *v21; // rax
  void **v22; // rdx
  void **v23; // r8
  int v24; // r9d
  serProcTemplate *v25; // rax
  TYPE_DATA *v26; // rax
  serProcTemplate *v27; // rax
  TYPE_DATA *v28; // rax
  serProcTemplate *v29; // rax
  TYPE_DATA *v30; // rax
  serProcTemplate *v31; // rax
  TYPE_DATA *v32; // rax
  int v33; // eax
  void **v34; // rdx
  void **v35; // r8
  int v36; // r9d
  INSTMGR *v37; // rax
  unsigned int v38; // eax
  struct ITypeInfo *v39; // rax
  TYPE_DATA *v40; // rax
  serProcTemplate *v41; // rax
  TYPE_DATA *v42; // rax
  serProcTemplate *v43; // rax
  TYPE_DATA *v44; // rax
  serProcTemplate *v45; // rax
  TYPE_DATA *v46; // rax
  serProcTemplate *v47; // rax
  TYPE_DATA *v48; // rax
  LPWSTR lpWideCharStr; // [rsp+20h] [rbp-2470h]
  LPWSTR lpWideCharStra; // [rsp+20h] [rbp-2470h]
  BSTR *cchWideChar; // [rsp+28h] [rbp-2468h]
  struct _msotcr *v52; // [rsp+30h] [rbp-2460h]
  struct IMsoToolbar *v53; // [rsp+38h] [rbp-2458h]
  int Dtmbrs; // [rsp+40h] [rbp-2450h]
  int v55; // [rsp+40h] [rbp-2450h]
  struct ITypeInfo *v56; // [rsp+48h] [rbp-2448h] BYREF
  unsigned int i; // [rsp+50h] [rbp-2440h]
  unsigned int v58; // [rsp+54h] [rbp-243Ch]
  __int64 *v59; // [rsp+58h] [rbp-2438h] BYREF
  struct ITypeInfo *v60; // [rsp+60h] [rbp-2430h] BYREF
  unsigned int v61; // [rsp+68h] [rbp-2428h]
  __int64 *v62; // [rsp+70h] [rbp-2420h] BYREF
  DYN_TYPEMEMBERS *v63; // [rsp+78h] [rbp-2418h] BYREF
  unsigned int v64; // [rsp+80h] [rbp-2410h]
  __int64 v65; // [rsp+88h] [rbp-2408h] BYREF
  __int64 v66; // [rsp+90h] [rbp-2400h] BYREF
  struct ITypeInfo *v67; // [rsp+98h] [rbp-23F8h] BYREF
  _BYTE v68[24]; // [rsp+A0h] [rbp-23F0h] BYREF
  int v69; // [rsp+B8h] [rbp-23D8h]
  int v70; // [rsp+BCh] [rbp-23D4h]
  int v71; // [rsp+C0h] [rbp-23D0h]
  BOOL v72; // [rsp+C4h] [rbp-23CCh]
  __int64 v73; // [rsp+C8h] [rbp-23C8h] BYREF
  BSTR bstrString; // [rsp+D0h] [rbp-23C0h] BYREF
  struct GEN_PROJECT *v75; // [rsp+D8h] [rbp-23B8h]
  BSTR v76; // [rsp+E0h] [rbp-23B0h] BYREF
  EVENT_SOURCE_TABLE *v77; // [rsp+E8h] [rbp-23A8h] BYREF
  BSTR v78; // [rsp+F0h] [rbp-23A0h] BYREF
  unsigned int v79; // [rsp+F8h] [rbp-2398h]
  int v80; // [rsp+FCh] [rbp-2394h] BYREF
  RECTYPE_DEFN *v81; // [rsp+100h] [rbp-2390h]
  unsigned int v82; // [rsp+108h] [rbp-2388h] BYREF
  RECTYPE_DEFN *v83; // [rsp+110h] [rbp-2380h]
  unsigned int v84; // [rsp+118h] [rbp-2378h]
  unsigned int v85; // [rsp+11Ch] [rbp-2374h]
  unsigned int v86; // [rsp+120h] [rbp-2370h]
  int v87; // [rsp+124h] [rbp-236Ch] BYREF
  unsigned int v88; // [rsp+128h] [rbp-2368h]
  unsigned int v89; // [rsp+12Ch] [rbp-2364h] BYREF
  unsigned int v90; // [rsp+130h] [rbp-2360h]
  struct ITypeInfo *v91; // [rsp+138h] [rbp-2358h]
  __int64 v92; // [rsp+140h] [rbp-2350h] BYREF
  struct ITypeInfo *v93; // [rsp+148h] [rbp-2348h]
  struct ITypeInfo *v94; // [rsp+150h] [rbp-2340h]
  struct ITypeInfo *v95; // [rsp+158h] [rbp-2338h]
  __int64 v96; // [rsp+160h] [rbp-2330h]
  BASIC_TYPEROOT *v97; // [rsp+168h] [rbp-2328h]
  struct ITypeLibVtbl *v98; // [rsp+170h] [rbp-2320h]
  BASIC_TYPEROOT *lpVtbl; // [rsp+178h] [rbp-2318h]
  __int64 v100; // [rsp+180h] [rbp-2310h]
  BASIC_TYPEROOT *v101; // [rsp+188h] [rbp-2308h]
  BASIC_TYPEROOT *v102; // [rsp+190h] [rbp-2300h]
  struct ITypeInfoVtbl *v103; // [rsp+198h] [rbp-22F8h]
  unsigned __int64 v104; // [rsp+1A0h] [rbp-22F0h]
  struct ITypeInfoVtbl *v105; // [rsp+1A8h] [rbp-22E8h]
  EBTHREAD *v106; // [rsp+1B0h] [rbp-22E0h]
  BASIC_TYPEROOT *v107; // [rsp+1B8h] [rbp-22D8h]
  GEN_PROJECT *v108; // [rsp+1C0h] [rbp-22D0h]
  BASIC_TYPEROOT *v109; // [rsp+1C8h] [rbp-22C8h]
  BASIC_TYPEROOT *v110; // [rsp+1D0h] [rbp-22C0h]
  struct ITypeInfoVtbl *v111; // [rsp+1D8h] [rbp-22B8h]
  DYN_TYPEMEMBERS *v112; // [rsp+1E0h] [rbp-22B0h]
  BASIC_TYPEROOT *v113; // [rsp+1E8h] [rbp-22A8h]
  VAR_DEFN *v114; // [rsp+1F0h] [rbp-22A0h]
  CMsoToolbarUser *v115; // [rsp+1F8h] [rbp-2298h]
  GEN_PROJECT *v116; // [rsp+200h] [rbp-2290h]
  BASIC_TYPEROOT *v117; // [rsp+208h] [rbp-2288h]
  BASIC_TYPEROOT *v118; // [rsp+210h] [rbp-2280h]
  struct ITypeInfoVtbl *v119; // [rsp+218h] [rbp-2278h]
  DYN_TYPEMEMBERS *v120; // [rsp+220h] [rbp-2270h]
  BASIC_TYPEROOT *v121; // [rsp+228h] [rbp-2268h]
  BASIC_TYPEROOT *v122; // [rsp+230h] [rbp-2260h]
  BASIC_TYPEROOT *v123; // [rsp+238h] [rbp-2258h]
  struct ITypeInfoVtbl *v124; // [rsp+240h] [rbp-2250h]
  BASIC_TYPEROOT *v125; // [rsp+248h] [rbp-2248h]
  BASIC_TYPEROOT *v126; // [rsp+250h] [rbp-2240h]
  struct ITypeInfoVtbl *v127; // [rsp+258h] [rbp-2238h]
  BASIC_TYPEROOT *v128; // [rsp+260h] [rbp-2230h]
  CMsoToolbarUser *v129; // [rsp+268h] [rbp-2228h]
  struct ITypeInfoVtbl *v130; // [rsp+270h] [rbp-2220h]
  struct ITypeInfoVtbl *v131; // [rsp+278h] [rbp-2218h]
  BASIC_TYPEROOT *v132; // [rsp+280h] [rbp-2210h]
  BASIC_TYPEROOT *v133; // [rsp+288h] [rbp-2208h]
  BASIC_TYPEROOT *v134; // [rsp+290h] [rbp-2200h]
  CMsoToolbarUser *v135; // [rsp+298h] [rbp-21F8h]
  __int64 v136; // [rsp+2A0h] [rbp-21F0h]
  BASIC_TYPEROOT *v137; // [rsp+2A8h] [rbp-21E8h]
  __int64 v138; // [rsp+2B0h] [rbp-21E0h]
  struct ITypeInfoVtbl *v139; // [rsp+2B8h] [rbp-21D8h]
  BASIC_TYPEROOT *v140; // [rsp+2C0h] [rbp-21D0h]
  BASIC_TYPEROOT *v141; // [rsp+2C8h] [rbp-21C8h]
  BSTR v142; // [rsp+2D0h] [rbp-21C0h]
  BASIC_TYPEROOT *v143; // [rsp+2D8h] [rbp-21B8h]
  __int64 v144; // [rsp+2E0h] [rbp-21B0h]
  struct ITypeInfoVtbl *v145; // [rsp+2E8h] [rbp-21A8h]
  BASIC_TYPEROOT *v146; // [rsp+2F0h] [rbp-21A0h]
  __int64 v147; // [rsp+2F8h] [rbp-2198h]
  BASIC_TYPEROOT *v148; // [rsp+300h] [rbp-2190h]
  CMsoToolbarUser *v149; // [rsp+308h] [rbp-2188h]
  BASIC_TYPEROOT *v150; // [rsp+310h] [rbp-2180h]
  BASIC_TYPEROOT *v151; // [rsp+318h] [rbp-2178h]
  __int64 v152; // [rsp+320h] [rbp-2170h]
  BASIC_TYPEROOT *v153; // [rsp+328h] [rbp-2168h]
  BASIC_TYPEROOT *v154; // [rsp+330h] [rbp-2160h]
  __int64 v155; // [rsp+338h] [rbp-2158h]
  __int64 v156; // [rsp+340h] [rbp-2150h]
  __int16 v157; // [rsp+348h] [rbp-2148h] BYREF
  int v158; // [rsp+350h] [rbp-2140h]
  struct _GUID v159; // [rsp+360h] [rbp-2130h] BYREF
  char v160[128]; // [rsp+370h] [rbp-2120h] BYREF
  CHAR TempFileName[2048]; // [rsp+3F0h] [rbp-20A0h] BYREF
  CHAR Buffer[2048]; // [rsp+BF0h] [rbp-18A0h] BYREF
  WCHAR WideCharStr[2048]; // [rsp+13F0h] [rbp-10A0h] BYREF
  struct ICreateTypeInfo *v164; // [rsp+23F0h] [rbp-A0h] BYREF
  unsigned int m; // [rsp+23F8h] [rbp-98h] BYREF
  unsigned int j; // [rsp+23FCh] [rbp-94h]
  struct ITypeLib *v167; // [rsp+2400h] [rbp-90h] BYREF
  BASIC_TYPEROOT **v168; // [rsp+2408h] [rbp-88h] BYREF
  unsigned int v169; // [rsp+2410h] [rbp-80h]
  unsigned int v170; // [rsp+2414h] [rbp-7Ch]
  struct ITypeInfo *v171; // [rsp+2418h] [rbp-78h]
  struct ICreateTypeInfo *v172; // [rsp+2420h] [rbp-70h] BYREF
  unsigned __int8 *v173; // [rsp+2428h] [rbp-68h]
  unsigned int v174; // [rsp+2430h] [rbp-60h] BYREF
  unsigned int k; // [rsp+2434h] [rbp-5Ch]
  __int64 v176; // [rsp+2438h] [rbp-58h] BYREF
  unsigned int v177; // [rsp+2440h] [rbp-50h] BYREF
  unsigned int n; // [rsp+2444h] [rbp-4Ch]
  unsigned int ii; // [rsp+2448h] [rbp-48h]
  unsigned int v180; // [rsp+244Ch] [rbp-44h] BYREF
  unsigned int v181; // [rsp+2450h] [rbp-40h] BYREF
  unsigned int v182; // [rsp+2454h] [rbp-3Ch]
  int v183; // [rsp+2458h] [rbp-38h]
  RECTYPE_DEFN *v184; // [rsp+2460h] [rbp-30h]
  unsigned __int16 v185; // [rsp+2468h] [rbp-28h]
  __int64 v186; // [rsp+2470h] [rbp-20h]

  CMsoDropdownUser::Dropping((const wchar_t *)this, a2, a3, a4, (uintptr_t)lpWideCharStr);
  v167 = 0;
  v66 = 0;
  v62 = 0;
  v183 = 0;
  v56 = 0;
  v171 = 0;
  v176 = 0;
  v59 = 0;
  v172 = 0;
  v170 = -1;
  v182 = 0;
  bstrString = 0;
  v76 = 0;
  v142 = 0;
  v78 = 0;
  v136 = 0;
  v65 = 0;
  v164 = 0;
  v155 = 0;
  v60 = 0;
  v173 = 0;
  v168 = 0;
  v156 = 0;
  v186 = 0;
  if ( !GetTempPathA(0x800u, Buffer) )
    return 2147650723LL;
  if ( !GetTempFileNameA(Buffer, "pub", 0, TempFileName) )
  {
    strcpy_s(Buffer, 0x800u, ".\\");
    if ( !GetTempFileNameA(Buffer, "pub", 0, TempFileName) )
      return 2147650723LL;
  }
  MultiByteToWideChar(0, 0, TempFileName, -1, WideCharStr, 2048);
  Syskind = GEN_PROJECT::GetSyskind(this);
  Dtmbrs = CreateTypeLib2Wrap((unsigned int)Syskind, WideCharStr, &v62);
  if ( Dtmbrs >= 0 )
  {
    (*(void (__fastcall **)(__int64 *, GUID *, struct ITypeLib **))*v62)(v62, &IID_ITypeLib, &v167);
    (*(void (__fastcall **)(__int64 *, GUID *, __int64 *))*v62)(v62, &IID_ICreateTypeLib2, &v73);
    v157 = 3;
    v158 = 1153;
    (*(void (__fastcall **)(__int64, GUID *, __int16 *))(*(_QWORD *)v73 + 112LL))(
      v73,
      &GUID_FuncCustDataReturnErrors,
      &v157);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v73 + 16LL))(v73);
    if ( *((_QWORD *)PebappCur() + 27) || (Dtmbrs = LoadStdoleTypeinfos(), Dtmbrs >= 0) )
    {
      v171 = (struct ITypeInfo *)*((_QWORD *)PebappCur() + 27);
      ((void (__fastcall *)(struct ITypeInfo *))v171->lpVtbl->AddRef)(v171);
      Dtmbrs = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*v62 + 80))(v62, 0);
      if ( Dtmbrs >= 0 )
      {
        cchWideChar = &v78;
        lpWideCharStra = (LPWSTR)&v82;
        Dtmbrs = (*(__int64 (__fastcall **)(GEN_PROJECT *, __int64, BSTR *, BSTR *))(*(_QWORD *)this + 72LL))(
                   this,
                   0xFFFFFFFFLL,
                   &bstrString,
                   &v76);
        if ( Dtmbrs >= 0 )
        {
          if ( !bstrString
            || (Dtmbrs = (*(__int64 (__fastcall **)(__int64 *, BSTR))(*v62 + 32))(v62, bstrString), Dtmbrs >= 0) )
          {
            if ( !v76 || (Dtmbrs = (*(__int64 (__fastcall **)(__int64 *, BSTR))(*v62 + 56))(v62, v76), Dtmbrs >= 0) )
            {
              Dtmbrs = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*v62 + 72))(v62, v82);
              if ( Dtmbrs >= 0 )
              {
                if ( !v78 || (Dtmbrs = (*(__int64 (__fastcall **)(__int64 *, BSTR))(*v62 + 64))(v62, v78), Dtmbrs >= 0) )
                {
                  v185 = GEN_PROJECT::MinorVerNum(this);
                  v6 = GEN_PROJECT::MajorVerNum(this);
                  v152 = *v62;
                  Dtmbrs = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD))(v152 + 40))(v62, v6, v185);
                  if ( Dtmbrs < 0
                    || (v7 = GEN_PROJECT::Guid(this, &v159),
                        v147 = *v62,
                        Dtmbrs = (*(__int64 (__fastcall **)(__int64 *, struct _GUID *))(v147 + 48))(v62, v7),
                        Dtmbrs < 0)
                    || ((*((_DWORD *)this + 78) & 0x10) == 0 ? (v70 = 0) : (v70 = 2),
                        v8 = v70 | *((unsigned __int16 *)this + 280),
                        v96 = *v62,
                        Dtmbrs = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(v96 + 88))(v62, v8),
                        Dtmbrs < 0) )
                  {
                    (*(void (__fastcall **)(GEN_PROJECT *, __int64))(*(_QWORD *)this + 96LL))(this, v136);
                  }
                  else
                  {
                    v64 = (*(__int64 (__fastcall **)(GEN_PROJECT *))(*(_QWORD *)this + 24LL))(this);
                    for ( i = 0; i < v64; ++i )
                    {
                      Dtmbrs = (*(__int64 (__fastcall **)(GEN_PROJECT *, _QWORD, struct ITypeInfo **))(*(_QWORD *)this + 32LL))(
                                 this,
                                 i,
                                 &v56);
                      if ( Dtmbrs < 0 )
                        goto LABEL_239;
                      lpVtbl = (BASIC_TYPEROOT *)v56[5].lpVtbl;
                      Dtmbrs = BASIC_TYPEROOT::EnsureInDeclaredState(lpVtbl, 0, 0);
                      if ( Dtmbrs < 0 )
                        goto LABEL_239;
                      if ( BASIC_TYPEINFO::GetTypeKind((BASIC_TYPEINFO *)v56) == TKIND_MAX )
                      {
                        v131 = v56[5].lpVtbl;
                        if ( (unsigned int)BASIC_TYPEROOT::Access(v131) == 1 )
                        {
                          v101 = (BASIC_TYPEROOT *)v56[5].lpVtbl;
                          v9 = BASIC_TYPEROOT::Pinstmgr(v101);
                          v58 = INSTMGR::ItypExe(v9);
                          if ( v58 != -1 && (v170 == -1 || v58 > v170) )
                            v170 = v58;
                        }
                      }
                      if ( v56 )
                      {
                        ((void (__fastcall *)(struct ITypeInfo *))v56->lpVtbl->Release)(v56);
                        v56 = 0;
                      }
                    }
                    v84 = v64;
                    v186 = ProfMemZalloc(v64 + 1);
                    if ( v186 )
                    {
                      v58 = 0;
                      while ( v58 <= v170 && v170 != -1 )
                      {
                        v71 = 0;
                        v64 = (*(__int64 (__fastcall **)(GEN_PROJECT *))(*(_QWORD *)this + 24LL))(this);
                        i = 0;
                        while ( i < v64 && v58 <= v170 )
                        {
                          Dtmbrs = (*(__int64 (__fastcall **)(GEN_PROJECT *, _QWORD, struct ITypeInfo **))(*(_QWORD *)this + 32LL))(
                                     this,
                                     i,
                                     &v56);
                          if ( Dtmbrs < 0 )
                            goto LABEL_239;
                          v154 = (BASIC_TYPEROOT *)v56[5].lpVtbl;
                          v10 = BASIC_TYPEROOT::Pinstmgr(v154);
                          v11 = INSTMGR::ItypExe(v10);
                          if ( v11 == v58 )
                          {
                            v103 = v56[5].lpVtbl;
                            if ( (unsigned int)BASIC_TYPEROOT::Access(v103) == 1 && !*(_BYTE *)(v186 + i) )
                            {
                              v133 = (BASIC_TYPEROOT *)v56[5].lpVtbl;
                              Dtmbrs = BASIC_TYPEROOT::GetDtmbrs(v133, &v63);
                              if ( Dtmbrs < 0 )
                                goto LABEL_239;
                              if ( (unsigned int)GEN_PROJECT::MakeCompatibleServer(this) )
                              {
                                if ( (unsigned int)GEN_PROJECT::IsProjectIncompatible(this) )
                                {
                                  v105 = v56[5].lpVtbl;
                                  if ( (int)BASIC_TYPEROOT::CompState(v105) <= 2 )
                                  {
                                    v151 = (BASIC_TYPEROOT *)v56[5].lpVtbl;
                                    BASIC_TYPEROOT::AssignClassIID(v151);
                                  }
                                }
                              }
                              Dtmbrs = DYN_TYPEMEMBERS::CopyToITypeLib(v63, v167, v171, 1);
                              if ( Dtmbrs < 0 )
                                goto LABEL_239;
                              *(_BYTE *)(v186 + i) = 1;
                              v91 = DYN_TYPEMEMBERS::PtinfoCopy(v63);
                              Dtmbrs = ((__int64 (__fastcall *)(struct ITypeInfo *, __int64 *, unsigned int *))v91->lpVtbl->GetContainingTypeLib)(
                                         v91,
                                         &v66,
                                         &v177);
                              if ( Dtmbrs < 0 )
                                goto LABEL_239;
                              (*(void (__fastcall **)(__int64))(*(_QWORD *)v66 + 16LL))(v66);
                              v107 = (BASIC_TYPEROOT *)v56[5].lpVtbl;
                              v12 = BASIC_TYPEROOT::Pinstmgr(v107);
                              INSTMGR::SetItypExe(v12, v177);
                              v135 = (CMsoToolbarUser *)v56[5].lpVtbl;
                              v72 = CMsoToolbarUser::FCtlCustomized(
                                      v135,
                                      v13,
                                      v14,
                                      v15,
                                      (int)lpWideCharStra,
                                      (int)cchWideChar,
                                      v52,
                                      v53,
                                      Dtmbrs) != 0;
                              v109 = (BASIC_TYPEROOT *)v56[5].lpVtbl;
                              v16 = BASIC_TYPEROOT::Pinstmgr(v109);
                              v182 = v72 + *((unsigned __int16 *)v16 + 140) + v177;
                              v183 = 1;
                              v84 = i;
                              ++v58;
                              v71 = 1;
                              if ( !(unsigned int)GEN_PROJECT::FOldCompatExe(this) )
                              {
                                v149 = (CMsoToolbarUser *)v56[5].lpVtbl;
                                if ( (unsigned int)CMsoToolbarUser::FCtlCustomized(
                                                     v149,
                                                     v17,
                                                     v18,
                                                     v19,
                                                     (int)lpWideCharStra,
                                                     (int)cchWideChar,
                                                     v52,
                                                     v53,
                                                     v55) )
                                  ++v58;
                              }
                            }
                          }
                          ++i;
                          if ( v56 )
                          {
                            ((void (__fastcall *)(struct ITypeInfo *))v56->lpVtbl->Release)(v56);
                            v56 = 0;
                          }
                        }
                        if ( !v71 )
                          ++v58;
                      }
                      v64 = (*(__int64 (__fastcall **)(GEN_PROJECT *))(*(_QWORD *)this + 24LL))(this);
                      for ( i = 0; i < v64; ++i )
                      {
                        Dtmbrs = (*(__int64 (__fastcall **)(GEN_PROJECT *, _QWORD, struct ITypeInfo **))(*(_QWORD *)this + 32LL))(
                                   this,
                                   i,
                                   &v56);
                        if ( Dtmbrs < 0 )
                          goto LABEL_239;
                        if ( BASIC_TYPEINFO::GetTypeKind((BASIC_TYPEINFO *)v56) == TKIND_MAX )
                        {
                          v111 = v56[5].lpVtbl;
                          if ( (unsigned int)BASIC_TYPEROOT::Access(v111) == 1 )
                          {
                            v137 = (BASIC_TYPEROOT *)v56[5].lpVtbl;
                            v20 = BASIC_TYPEROOT::Pinstmgr(v137);
                            if ( INSTMGR::ItypExe(v20) == -1 )
                            {
                              v113 = (BASIC_TYPEROOT *)v56[5].lpVtbl;
                              Dtmbrs = BASIC_TYPEROOT::GetDtmbrs(v113, &v63);
                              if ( Dtmbrs < 0 )
                                goto LABEL_239;
                              Dtmbrs = DYN_TYPEMEMBERS::CopyToITypeLib(v63, v167, v171, 1);
                              if ( Dtmbrs < 0 )
                                goto LABEL_239;
                              v183 = 1;
                              v95 = DYN_TYPEMEMBERS::PtinfoCopy(v63);
                              Dtmbrs = ((__int64 (__fastcall *)(struct ITypeInfo *, __int64 *, unsigned int *))v95->lpVtbl->GetContainingTypeLib)(
                                         v95,
                                         &v66,
                                         &v177);
                              if ( Dtmbrs < 0 )
                                goto LABEL_239;
                              (*(void (__fastcall **)(__int64))(*(_QWORD *)v66 + 16LL))(v66);
                              v153 = (BASIC_TYPEROOT *)v56[5].lpVtbl;
                              v21 = BASIC_TYPEROOT::Pinstmgr(v153);
                              INSTMGR::SetItypExe(v21, v177);
                              v115 = (CMsoToolbarUser *)v56[5].lpVtbl;
                              if ( (unsigned int)CMsoToolbarUser::FCtlCustomized(
                                                   v115,
                                                   v22,
                                                   v23,
                                                   v24,
                                                   (int)lpWideCharStra,
                                                   (int)cchWideChar,
                                                   v52,
                                                   v53,
                                                   Dtmbrs) )
                                v69 = 2;
                              else
                                v69 = 1;
                              v182 = v69 + v177;
                            }
                          }
                        }
                        if ( v56 )
                        {
                          ((void (__fastcall *)(struct ITypeInfo *))v56->lpVtbl->Release)(v56);
                          v56 = 0;
                        }
                      }
                      v58 = v182;
                      v169 = v182;
                      for ( i = 0; i < v64; ++i )
                      {
                        Dtmbrs = (*(__int64 (__fastcall **)(GEN_PROJECT *, _QWORD, struct ITypeInfo **))(*(_QWORD *)this + 32LL))(
                                   this,
                                   i,
                                   &v56);
                        if ( Dtmbrs < 0 )
                          goto LABEL_239;
                        if ( BASIC_TYPEINFO::GetTypeKind((BASIC_TYPEINFO *)v56) == TKIND_MAX )
                        {
                          v139 = v56[5].lpVtbl;
                          if ( (unsigned int)BASIC_TYPEROOT::Access(v139) == 1 )
                          {
                            v117 = (BASIC_TYPEROOT *)v56[5].lpVtbl;
                            if ( (unsigned int)BASIC_TYPEROOT::FHasSource(v117) )
                            {
                              v146 = (BASIC_TYPEROOT *)v56[5].lpVtbl;
                              Dtmbrs = BASIC_TYPEROOT::GetDtmbrs(v146, &v63);
                              if ( Dtmbrs < 0 )
                                goto LABEL_239;
                              Dtmbrs = DYN_TYPEMEMBERS::CopyToITypeLibEvent(v63, v167, v171);
                              if ( Dtmbrs < 0 )
                                goto LABEL_239;
                              ++v169;
                            }
                          }
                        }
                        if ( v56 )
                        {
                          ((void (__fastcall *)(struct ITypeInfo *))v56->lpVtbl->Release)(v56);
                          v56 = 0;
                        }
                      }
                      for ( i = 0; i < v64; ++i )
                      {
                        Dtmbrs = (*(__int64 (__fastcall **)(GEN_PROJECT *, _QWORD, struct ITypeInfo **))(*(_QWORD *)this + 32LL))(
                                   this,
                                   i,
                                   &v56);
                        if ( Dtmbrs < 0 )
                          goto LABEL_239;
                        if ( BASIC_TYPEINFO::GetTypeKind((BASIC_TYPEINFO *)v56) == TKIND_MAX )
                        {
                          v119 = v56[5].lpVtbl;
                          if ( (unsigned int)BASIC_TYPEROOT::Access(v119) == 1 )
                          {
                            v141 = (BASIC_TYPEROOT *)v56[5].lpVtbl;
                            v25 = BASIC_TYPEROOT::Pdtmbrs(v141);
                            v26 = (TYPE_DATA *)serProcTemplate::PvTemplate(v25);
                            for ( j = TYPE_DATA::HdefnFirstTypeDefn(v26); j != -1; j = MEMBER_DEFN::DwHelpContext(v184) )
                            {
                              v121 = (BASIC_TYPEROOT *)v56[5].lpVtbl;
                              v27 = BASIC_TYPEROOT::Pdtmbrs(v121);
                              v28 = (TYPE_DATA *)serProcTemplate::PvTemplate(v27);
                              v184 = TYPE_DATA::QvfdefnOfHvfdefn(v28, j, 0);
                              if ( (unsigned int)RECTYPE_DEFN::Access((__int64)v184) == 1 )
                              {
                                if ( (unsigned int)RECTYPE_DEFN::IsEnum(v184) )
                                {
                                  v148 = (BASIC_TYPEROOT *)v56[5].lpVtbl;
                                  Dtmbrs = BASIC_TYPEROOT::GetDtmbrs(v148, &v63);
                                  if ( Dtmbrs < 0 )
                                    goto LABEL_239;
                                  Dtmbrs = DYN_TYPEMEMBERS::CopyToITypeLibEnum(v63, v167, j, v171);
                                  if ( Dtmbrs < 0 )
                                    goto LABEL_239;
                                }
                              }
                            }
                            v123 = (BASIC_TYPEROOT *)v56[5].lpVtbl;
                            v29 = BASIC_TYPEROOT::Pdtmbrs(v123);
                            v30 = (TYPE_DATA *)serProcTemplate::PvTemplate(v29);
                            for ( j = TYPE_DATA::HdefnFirstTypeDefn(v30); j != -1; j = MEMBER_DEFN::DwHelpContext(v184) )
                            {
                              v143 = (BASIC_TYPEROOT *)v56[5].lpVtbl;
                              v31 = BASIC_TYPEROOT::Pdtmbrs(v143);
                              v32 = (TYPE_DATA *)serProcTemplate::PvTemplate(v31);
                              v184 = TYPE_DATA::QvfdefnOfHvfdefn(v32, j, 0);
                              if ( (unsigned int)RECTYPE_DEFN::Access((__int64)v184) == 1
                                && !(unsigned int)RECTYPE_DEFN::IsEnum(v184) )
                              {
                                v125 = (BASIC_TYPEROOT *)v56[5].lpVtbl;
                                Dtmbrs = BASIC_TYPEROOT::GetDtmbrs(v125, &v63);
                                if ( Dtmbrs < 0 )
                                  goto LABEL_239;
                                Dtmbrs = DYN_TYPEMEMBERS::CopyToITypeLibUDT(v63, v167, j, v171);
                                if ( Dtmbrs < 0 )
                                  goto LABEL_239;
                              }
                            }
                          }
                        }
                        if ( v56 )
                        {
                          ((void (__fastcall *)(struct ITypeInfo *))v56->lpVtbl->Release)(v56);
                          v56 = 0;
                        }
                      }
                      for ( i = 0; i < v64; ++i )
                      {
                        Dtmbrs = (*(__int64 (__fastcall **)(GEN_PROJECT *, _QWORD, struct ITypeInfo **))(*(_QWORD *)this + 32LL))(
                                   this,
                                   i,
                                   &v56);
                        if ( Dtmbrs < 0 )
                          goto LABEL_239;
                        v150 = (BASIC_TYPEROOT *)v56[5].lpVtbl;
                        v63 = BASIC_TYPEROOT::Pdtmbrs(v150);
                        if ( DYN_TYPEMEMBERS::PtinfoCopy(v63) )
                        {
                          v94 = DYN_TYPEMEMBERS::PtinfoCopy(v63);
                          ((void (__fastcall *)(struct ITypeInfo *, GUID *, struct ICreateTypeInfo **))v94->lpVtbl->QueryInterface)(
                            v94,
                            &IID_ICreateTypeInfo,
                            &v172);
                          v127 = v56[5].lpVtbl;
                          v33 = BASIC_TYPEROOT::Access(v127);
                          Dtmbrs = DYN_TYPEMEMBERS::CopyDataToITypeInfo(v63, v56, v172, v33);
                          if ( Dtmbrs < 0 )
                            goto LABEL_239;
                          Dtmbrs = ((__int64 (__fastcall *)(struct ICreateTypeInfo *))v172->lpVtbl->LayOut)(v172);
                          if ( Dtmbrs < 0 )
                            goto LABEL_239;
                          if ( v172 )
                          {
                            ((void (__fastcall *)(struct ICreateTypeInfo *))v172->lpVtbl->Release)(v172);
                            v172 = 0;
                          }
                          v145 = v56[5].lpVtbl;
                          if ( (unsigned int)BASIC_TYPEROOT::Access(v145) == 1 )
                          {
                            v129 = (CMsoToolbarUser *)v56[5].lpVtbl;
                            if ( (unsigned int)CMsoToolbarUser::FCtlCustomized(
                                                 v129,
                                                 v34,
                                                 v35,
                                                 v36,
                                                 (int)lpWideCharStra,
                                                 (int)cchWideChar,
                                                 v52,
                                                 v53,
                                                 Dtmbrs) )
                            {
                              v97 = (BASIC_TYPEROOT *)v56[5].lpVtbl;
                              v37 = BASIC_TYPEROOT::Pinstmgr(v97);
                              v38 = INSTMGR::ItypExe(v37);
                              v98 = v167->lpVtbl;
                              Dtmbrs = ((__int64 (__fastcall *)(struct ITypeLib *, _QWORD, __int64 *))v98->GetTypeInfo)(
                                         v167,
                                         v38 + 1,
                                         &v176);
                              if ( Dtmbrs < 0 )
                                goto LABEL_239;
                              (**(void (__fastcall ***)(__int64, GUID *, __int64 **))v176)(
                                v176,
                                &IID_ICreateTypeInfo,
                                &v59);
                              v61 = 0;
                              v39 = DYN_TYPEMEMBERS::PtinfoCopy(v63);
                              v100 = *v59;
                              Dtmbrs = (*(__int64 (__fastcall **)(__int64 *, struct ITypeInfo *, unsigned int *))(v100 + 64))(
                                         v59,
                                         v39,
                                         &v174);
                              if ( Dtmbrs < 0 )
                                goto LABEL_239;
                              Dtmbrs = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD))(*v59 + 80))(
                                         v59,
                                         v61,
                                         v174);
                              if ( Dtmbrs < 0 )
                                goto LABEL_239;
                              Dtmbrs = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64))(*v59 + 88))(v59, v61, 1);
                              if ( Dtmbrs < 0 )
                                goto LABEL_239;
                              v102 = (BASIC_TYPEROOT *)v56[5].lpVtbl;
                              Dtmbrs = BASIC_TYPEROOT::GetEventSourceTable(v102, &v77);
                              if ( Dtmbrs < 0 )
                                goto LABEL_239;
                              Dtmbrs = EVENT_SOURCE_TABLE::GetSourceCount(v77, &v180);
                              if ( Dtmbrs < 0 )
                                goto LABEL_239;
                              LOBYTE(v52) = 1;
                              TempBufferEx::TempBufferEx((TempBufferEx *)v68, 0x78u, 0, 4LL * v180, v160, 0);
                              v75 = NAMMGR::Pgenproj((NAMMGR *)v68);
                              if ( !v75 )
                              {
                                v88 = -2147024882;
                                TempBufferEx::~TempBufferEx((TempBufferEx *)v68);
                                return v88;
                              }
                              v104 = 4LL * v180;
                              memset(v75, 0, v104);
                              v106 = (EBTHREAD *)v56[5].lpVtbl;
                              v173 = EBTHREAD::PbListColorBuf(v106);
                              if ( v173 )
                              {
                                v67 = 0;
                                Dtmbrs = (*(__int64 (__fastcall **)(unsigned __int8 *, __int64 *))(*(_QWORD *)v173 + 24LL))(
                                           v173,
                                           &v92);
                                if ( Dtmbrs < 0 )
                                  goto LABEL_142;
                                v90 = *(unsigned __int16 *)(v92 + 52);
                                (*(void (__fastcall **)(unsigned __int8 *, __int64))(*(_QWORD *)v173 + 152LL))(
                                  v173,
                                  v92);
                                for ( k = 0; k < v90; ++k )
                                {
                                  (*(void (__fastcall **)(unsigned __int8 *, _QWORD, int *))(*(_QWORD *)v173 + 72LL))(
                                    v173,
                                    k,
                                    &v87);
                                  if ( (v87 & 1) == 0 )
                                  {
                                    Dtmbrs = (*(__int64 (__fastcall **)(unsigned __int8 *, _QWORD, unsigned int *))(*(_QWORD *)v173 + 64LL))(
                                               v173,
                                               k,
                                               &v181);
                                    if ( Dtmbrs < 0 )
                                      goto LABEL_142;
                                    Dtmbrs = (*(__int64 (__fastcall **)(unsigned __int8 *, _QWORD, struct ITypeInfo **))(*(_QWORD *)v173 + 112LL))(
                                               v173,
                                               v181,
                                               &v67);
                                    if ( Dtmbrs < 0 )
                                      goto LABEL_142;
                                    Dtmbrs = GetCompatibleInterface((struct BASIC_TYPEINFO *)v56, v67, &v60, &m);
                                    if ( v67 )
                                    {
                                      ((void (__fastcall *)(struct ITypeInfo *))v67->lpVtbl->Release)(v67);
                                      v67 = 0;
                                    }
                                    if ( Dtmbrs >= 0 )
                                    {
                                      ++v61;
                                      if ( ((__int64 (__fastcall *)(struct ITypeInfo *, GUID *, BASIC_TYPEROOT ***))v60->lpVtbl->QueryInterface)(
                                             v60,
                                             &IID_BASIC_TYPEINFO,
                                             &v168) >= 0 )
                                      {
                                        v108 = v168[19];
                                        if ( v108 == this )
                                        {
                                          if ( v60 )
                                          {
                                            ((void (__fastcall *)(struct ITypeInfo *))v60->lpVtbl->Release)(v60);
                                            v60 = 0;
                                          }
                                          v110 = v168[5];
                                          v112 = BASIC_TYPEROOT::Pdtmbrs(v110);
                                          v60 = DYN_TYPEMEMBERS::PtinfoCopy(v112);
                                          ((void (__fastcall *)(struct ITypeInfo *))v60->lpVtbl->AddRef)(v60);
                                        }
                                        if ( v168 )
                                        {
                                          (*((void (__fastcall **)(BASIC_TYPEROOT **))*v168 + 2))(v168);
                                          v168 = 0;
                                        }
                                      }
                                      Dtmbrs = (*(__int64 (__fastcall **)(__int64 *, struct ITypeInfo *, unsigned int *))(*v59 + 64))(
                                                 v59,
                                                 v60,
                                                 &v181);
                                      if ( v60 )
                                      {
                                        ((void (__fastcall *)(struct ITypeInfo *))v60->lpVtbl->Release)(v60);
                                        v60 = 0;
                                      }
                                      if ( Dtmbrs < 0 )
                                        goto LABEL_142;
                                      Dtmbrs = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD))(*v59 + 80))(
                                                 v59,
                                                 v61,
                                                 v181);
                                      if ( Dtmbrs < 0 )
                                        goto LABEL_142;
                                      Dtmbrs = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD))(*v59 + 88))(
                                                 v59,
                                                 v61,
                                                 0);
                                      if ( Dtmbrs < 0 )
                                        goto LABEL_142;
                                      *((_DWORD *)v75 + m) = 1;
                                    }
                                    else if ( (*((_DWORD *)this + 76) & 0x40000) == 0 || Dtmbrs != -2146771274 )
                                    {
                                      if ( v60 )
                                      {
                                        ((void (__fastcall *)(struct ITypeInfo *))v60->lpVtbl->Release)(v60);
                                        v60 = 0;
                                      }
                                      goto LABEL_142;
                                    }
                                  }
                                }
                              }
                              for ( m = 0; m < v180; ++m )
                              {
                                Dtmbrs = EVENT_SOURCE_TABLE::GetIsCookieOfSource(v77, m, &v80);
                                if ( Dtmbrs < 0 )
                                  goto LABEL_142;
                                if ( v80 )
                                {
                                  Dtmbrs = EVENT_SOURCE_TABLE::GetHdefnOfSource(v77, m, &v89);
                                  if ( Dtmbrs < 0 )
                                    goto LABEL_142;
                                  v40 = (TYPE_DATA *)serProcTemplate::PvTemplate(v63);
                                  v114 = TYPE_DATA::QvfdefnOfHvfdefn(v40, v89, 0);
                                  if ( (unsigned int)VAR_DEFN::IsImplements(v114) )
                                  {
                                    if ( !*((_DWORD *)v75 + m) )
                                    {
                                      Dtmbrs = EVENT_SOURCE_TABLE::GetPtinfoOfSource(v77, m, &v60);
                                      if ( Dtmbrs < 0 )
                                        goto LABEL_142;
                                      ++v61;
                                      if ( ((__int64 (__fastcall *)(struct ITypeInfo *, GUID *, BASIC_TYPEROOT ***))v60->lpVtbl->QueryInterface)(
                                             v60,
                                             &IID_BASIC_TYPEINFO,
                                             &v168) >= 0 )
                                      {
                                        v116 = v168[19];
                                        if ( v116 == this )
                                        {
                                          if ( v60 )
                                          {
                                            ((void (__fastcall *)(struct ITypeInfo *))v60->lpVtbl->Release)(v60);
                                            v60 = 0;
                                          }
                                          v118 = v168[5];
                                          v120 = BASIC_TYPEROOT::Pdtmbrs(v118);
                                          v60 = DYN_TYPEMEMBERS::PtinfoCopy(v120);
                                          ((void (__fastcall *)(struct ITypeInfo *))v60->lpVtbl->AddRef)(v60);
                                        }
                                        if ( v168 )
                                        {
                                          (*((void (__fastcall **)(BASIC_TYPEROOT **))*v168 + 2))(v168);
                                          v168 = 0;
                                        }
                                      }
                                      Dtmbrs = (*(__int64 (__fastcall **)(__int64 *, struct ITypeInfo *, unsigned int *))(*v59 + 64))(
                                                 v59,
                                                 v60,
                                                 &v174);
                                      if ( v60 )
                                      {
                                        ((void (__fastcall *)(struct ITypeInfo *))v60->lpVtbl->Release)(v60);
                                        v60 = 0;
                                      }
                                      if ( Dtmbrs < 0 )
                                        goto LABEL_142;
                                      Dtmbrs = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD))(*v59 + 80))(
                                                 v59,
                                                 v61,
                                                 v174);
                                      if ( Dtmbrs < 0 )
                                        goto LABEL_142;
                                      Dtmbrs = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD))(*v59 + 88))(
                                                 v59,
                                                 v61,
                                                 0);
                                      if ( Dtmbrs < 0 )
                                        goto LABEL_142;
                                    }
                                  }
                                }
                              }
                              v122 = (BASIC_TYPEROOT *)v56[5].lpVtbl;
                              if ( (unsigned int)BASIC_TYPEROOT::FHasSource(v122) )
                              {
                                v85 = v58;
                                Dtmbrs = ((__int64 (__fastcall *)(struct ITypeLib *, _QWORD, __int64 *))v167->lpVtbl->GetTypeInfo)(
                                           v167,
                                           v58++,
                                           &v65);
                                if ( Dtmbrs < 0 )
                                  goto LABEL_142;
                                (**(void (__fastcall ***)(__int64, GUID *, struct ICreateTypeInfo **))v65)(
                                  v65,
                                  &IID_ICreateTypeInfo,
                                  &v164);
                                Dtmbrs = DYN_TYPEMEMBERS::CopyDataToITypeInfoEvent(v63, v56, v164);
                                if ( Dtmbrs >= 0 )
                                {
                                  Dtmbrs = ((__int64 (__fastcall *)(struct ICreateTypeInfo *))v164->lpVtbl->LayOut)(v164);
                                  if ( Dtmbrs >= 0 )
                                  {
                                    ++v61;
                                    Dtmbrs = (*(__int64 (__fastcall **)(__int64 *, __int64, unsigned int *))(*v59 + 64))(
                                               v59,
                                               v65,
                                               &v174);
                                    if ( Dtmbrs >= 0 )
                                    {
                                      Dtmbrs = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD))(*v59 + 80))(
                                                 v59,
                                                 v61,
                                                 v174);
                                      if ( Dtmbrs >= 0 )
                                        Dtmbrs = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64))(*v59 + 88))(
                                                   v59,
                                                   v61,
                                                   3);
                                    }
                                  }
                                }
                                if ( v164 )
                                {
                                  ((void (__fastcall *)(struct ICreateTypeInfo *))v164->lpVtbl->Release)(v164);
                                  v164 = 0;
                                }
                                if ( v65 )
                                {
                                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
                                  v65 = 0;
                                }
                                if ( Dtmbrs < 0 )
                                  goto LABEL_142;
                              }
                              Dtmbrs = (*(__int64 (__fastcall **)(__int64 *))(*v59 + 200))(v59);
                              if ( Dtmbrs < 0 )
                              {
LABEL_142:
                                TempBufferEx::~TempBufferEx((TempBufferEx *)v68);
                                goto LABEL_239;
                              }
                              if ( v59 )
                              {
                                (*(void (__fastcall **)(__int64 *))(*v59 + 16))(v59);
                                v59 = 0;
                              }
                              if ( v176 )
                              {
                                (*(void (__fastcall **)(__int64))(*(_QWORD *)v176 + 16LL))(v176);
                                v176 = 0;
                              }
                              TempBufferEx::~TempBufferEx((TempBufferEx *)v68);
                            }
                          }
                          if ( BASIC_TYPEINFO::GetTypeKind((BASIC_TYPEINFO *)v56) == TKIND_MAX )
                          {
                            v124 = v56[5].lpVtbl;
                            if ( (unsigned int)BASIC_TYPEROOT::Access(v124) == 1 )
                            {
                              v126 = (BASIC_TYPEROOT *)v56[5].lpVtbl;
                              v41 = BASIC_TYPEROOT::Pdtmbrs(v126);
                              v42 = (TYPE_DATA *)serProcTemplate::PvTemplate(v41);
                              for ( n = TYPE_DATA::HdefnFirstTypeDefn(v42); n != -1; n = MEMBER_DEFN::DwHelpContext(v81) )
                              {
                                v128 = (BASIC_TYPEROOT *)v56[5].lpVtbl;
                                v43 = BASIC_TYPEROOT::Pdtmbrs(v128);
                                v44 = (TYPE_DATA *)serProcTemplate::PvTemplate(v43);
                                v81 = TYPE_DATA::QvfdefnOfHvfdefn(v44, n, 0);
                                if ( (unsigned int)RECTYPE_DEFN::Access((__int64)v81) == 1
                                  && (unsigned int)RECTYPE_DEFN::IsEnum(v81) )
                                {
                                  v79 = v169;
                                  Dtmbrs = ((__int64 (__fastcall *)(struct ITypeLib *, _QWORD, __int64 *))v167->lpVtbl->GetTypeInfo)(
                                             v167,
                                             v169++,
                                             &v65);
                                  if ( Dtmbrs < 0 )
                                    goto LABEL_239;
                                  (**(void (__fastcall ***)(__int64, GUID *, struct ICreateTypeInfo **))v65)(
                                    v65,
                                    &IID_ICreateTypeInfo,
                                    &v164);
                                  DYN_TYPEMEMBERS::CopyDataToITypeInfoEnum(v63, v56, n, v164);
                                  Dtmbrs = ((__int64 (__fastcall *)(struct ICreateTypeInfo *))v164->lpVtbl->LayOut)(v164);
                                  if ( Dtmbrs < 0 )
                                    goto LABEL_239;
                                  if ( v164 )
                                  {
                                    ((void (__fastcall *)(struct ICreateTypeInfo *))v164->lpVtbl->Release)(v164);
                                    v164 = 0;
                                  }
                                  if ( v65 )
                                  {
                                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
                                    v65 = 0;
                                  }
                                }
                              }
                            }
                          }
                          if ( BASIC_TYPEINFO::GetTypeKind((BASIC_TYPEINFO *)v56) == TKIND_MAX )
                          {
                            v130 = v56[5].lpVtbl;
                            if ( (unsigned int)BASIC_TYPEROOT::Access(v130) == 1 )
                            {
                              v132 = (BASIC_TYPEROOT *)v56[5].lpVtbl;
                              v45 = BASIC_TYPEROOT::Pdtmbrs(v132);
                              v46 = (TYPE_DATA *)serProcTemplate::PvTemplate(v45);
                              for ( ii = TYPE_DATA::HdefnFirstTypeDefn(v46); ii != -1; ii = MEMBER_DEFN::DwHelpContext(v83) )
                              {
                                v134 = (BASIC_TYPEROOT *)v56[5].lpVtbl;
                                v47 = BASIC_TYPEROOT::Pdtmbrs(v134);
                                v48 = (TYPE_DATA *)serProcTemplate::PvTemplate(v47);
                                v83 = TYPE_DATA::QvfdefnOfHvfdefn(v48, ii, 0);
                                if ( (unsigned int)RECTYPE_DEFN::Access((__int64)v83) == 1
                                  && !(unsigned int)RECTYPE_DEFN::IsEnum(v83) )
                                {
                                  v86 = v169;
                                  Dtmbrs = ((__int64 (__fastcall *)(struct ITypeLib *, _QWORD, __int64 *))v167->lpVtbl->GetTypeInfo)(
                                             v167,
                                             v169++,
                                             &v65);
                                  if ( Dtmbrs < 0 )
                                    goto LABEL_239;
                                  (**(void (__fastcall ***)(__int64, GUID *, struct ICreateTypeInfo **))v65)(
                                    v65,
                                    &IID_ICreateTypeInfo,
                                    &v164);
                                  DYN_TYPEMEMBERS::CopyDataToITypeInfoUDT(v63, v56, ii, v164);
                                  if ( v164 )
                                  {
                                    ((void (__fastcall *)(struct ICreateTypeInfo *))v164->lpVtbl->Release)(v164);
                                    v164 = 0;
                                  }
                                  if ( v65 )
                                  {
                                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
                                    v65 = 0;
                                  }
                                }
                              }
                            }
                          }
                        }
                        if ( v56 )
                        {
                          ((void (__fastcall *)(struct ITypeInfo *))v56->lpVtbl->Release)(v56);
                          v56 = 0;
                        }
                      }
                      Dtmbrs = (*(__int64 (__fastcall **)(__int64 *))(*v62 + 96))(v62);
                    }
                    else
                    {
                      Dtmbrs = -2147024882;
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_239:
  if ( v186 )
    ProfMemFree(v186);
  if ( v168 )
  {
    (*((void (__fastcall **)(BASIC_TYPEROOT **))*v168 + 2))(v168);
    v168 = 0;
  }
  for ( i = 0; i < v64; ++i )
  {
    v138 = *((_QWORD *)GEN_PROJECT::Qte(this, i) + 1);
    v140 = *(BASIC_TYPEROOT **)(v138 + 40);
    v63 = BASIC_TYPEROOT::Pdtmbrs(v140);
    if ( DYN_TYPEMEMBERS::PtinfoCopy(v63) )
    {
      v93 = DYN_TYPEMEMBERS::PtinfoCopy(v63);
      ((void (__fastcall *)(struct ITypeInfo *))v93->lpVtbl->Release)(v93);
      DYN_TYPEMEMBERS::SetPtinfoCopy(v63, 0);
    }
  }
  SysFreeString(bstrString);
  SysFreeString(v76);
  SysFreeString(v78);
  SysFreeString(v142);
  if ( v172 )
  {
    ((void (__fastcall *)(struct ICreateTypeInfo *))v172->lpVtbl->Release)(v172);
    v172 = 0;
  }
  if ( v59 )
  {
    (*(void (__fastcall **)(__int64 *))(*v59 + 16))(v59);
    v59 = 0;
  }
  if ( v176 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v176 + 16LL))(v176);
    v176 = 0;
  }
  if ( v56 )
  {
    ((void (__fastcall *)(struct ITypeInfo *))v56->lpVtbl->Release)(v56);
    v56 = 0;
  }
  if ( v171 )
  {
    ((void (__fastcall *)(struct ITypeInfo *))v171->lpVtbl->Release)(v171);
    v171 = 0;
  }
  if ( v167 )
  {
    ((void (__fastcall *)(struct ITypeLib *))v167->lpVtbl->Release)(v167);
    v167 = 0;
  }
  if ( v62 )
  {
    (*(void (__fastcall **)(__int64 *))(*v62 + 16))(v62);
    v62 = 0;
  }
  if ( Dtmbrs >= 0 )
  {
    if ( v183 )
    {
      v144 = (*(__int64 (__fastcall **)(const wchar_t *, __int64, __int64, const wchar_t *, const char *))(*(_QWORD *)a2 + 88LL))(
               a2,
               2,
               1,
               L"typelib",
               "VBA_TypeLib");
      if ( !(*(unsigned int (__fastcall **)(const wchar_t *, __int64, WCHAR *, __int64))(*(_QWORD *)a2 + 32LL))(
              a2,
              v144,
              WideCharStr,
              1) )
        return (unsigned int)-2147287011;
    }
    else
    {
      remove(TempFileName);
    }
  }
  return (unsigned int)Dtmbrs;
}

```

## disassembly

```asm
0x18012abcc  mov     [rsp-8+arg_8], rdx
0x18012abd1  mov     [rsp-8+arg_0], rcx
0x18012abd6  push    rbp
0x18012abd7  mov     rbp, rsp
0x18012abda  push    rdi
0x18012abdb  mov     eax, 2488h
0x18012abe0  call    _alloca_probe
0x18012abe5  sub     rsp, rax
0x18012abe8  mov     rax, cs:__security_cookie
0x18012abef  xor     rax, rsp
0x18012abf2  mov     [rbp+var_18], rax
0x18012abf6  mov     rcx, [rbp+arg_0]; wchar_t *
0x18012abfa  call    ?Dropping@CMsoDropdownUser@@UEAAXPEAUIMsoControl@@PEAPEAXPEAUHFONT__@@@Z; CMsoDropdownUser::Dropping(IMsoControl *,void * *,HFONT__ *)
0x18012abff  mov     [rsp+2490h+var_90], 0
0x18012ac0b  mov     [rsp+2490h+var_2400], 0
0x18012ac17  mov     [rsp+2490h+var_2420], 0
0x18012ac20  mov     [rbp+var_38], 0
0x18012ac27  mov     [rsp+2490h+var_2448], 0
0x18012ac30  mov     [rbp+var_78], 0
0x18012ac38  mov     [rbp+var_58], 0
0x18012ac40  mov     [rsp+2490h+var_2438], 0
0x18012ac49  mov     [rbp+var_70], 0
0x18012ac51  mov     [rbp+var_7C], 0FFFFFFFFh
0x18012ac58  mov     [rbp+var_3C], 0
0x18012ac5f  mov     [rsp+2490h+bstrString], 0
0x18012ac6b  mov     [rsp+2490h+var_23B0], 0
0x18012ac77  mov     [rsp+2490h+var_21C0], 0
0x18012ac83  mov     [rsp+2490h+var_23A0], 0
0x18012ac8f  mov     [rsp+2490h+var_21F0], 0
0x18012ac9b  mov     [rsp+2490h+var_2408], 0
0x18012aca7  mov     [rsp+2490h+var_A0], 0
0x18012acb3  mov     [rsp+2490h+var_2158], 0
0x18012acbf  mov     [rsp+2490h+var_2430], 0
0x18012acc8  mov     [rbp+var_68], 0
0x18012acd0  mov     [rsp+2490h+var_88], 0
0x18012acdc  mov     [rsp+2490h+var_2150], 0
0x18012ace8  mov     [rbp+var_20], 0
0x18012acf0  lea     rdx, [rsp+2490h+Buffer]; lpBuffer
0x18012acf8  mov     ecx, 800h; nBufferLength
0x18012acfd  call    cs:__imp_GetTempPathA
0x18012ad03  test    eax, eax
0x18012ad05  jnz     short loc_18012AD11
0x18012ad07  mov     eax, 80028CA3h
0x18012ad0c  jmp     loc_18012CF48
0x18012ad11  lea     r9, [rsp+2490h+TempFileName]; lpTempFileName
0x18012ad19  xor     r8d, r8d; uUnique
0x18012ad1c  lea     rdx, aPub; "pub"
0x18012ad23  lea     rcx, [rsp+2490h+Buffer]; lpPathName
0x18012ad2b  call    cs:__imp_GetTempFileNameA
0x18012ad31  test    eax, eax
0x18012ad33  jnz     short loc_18012AD7D
0x18012ad35  lea     r8, asc_1803B5480; ".\\"
0x18012ad3c  mov     edx, 800h; SizeInBytes
0x18012ad41  lea     rcx, [rsp+2490h+Buffer]; Destination
0x18012ad49  call    cs:__imp_strcpy_s
0x18012ad4f  lea     r9, [rsp+2490h+TempFileName]; lpTempFileName
0x18012ad57  xor     r8d, r8d; uUnique
0x18012ad5a  lea     rdx, aPub; "pub"
0x18012ad61  lea     rcx, [rsp+2490h+Buffer]; lpPathName
0x18012ad69  call    cs:__imp_GetTempFileNameA
0x18012ad6f  test    eax, eax
0x18012ad71  jnz     short loc_18012AD7D
0x18012ad73  mov     eax, 80028CA3h
0x18012ad78  jmp     loc_18012CF48
0x18012ad7d  mov     [rsp+2490h+cchWideChar], 800h; cchWideChar
0x18012ad85  lea     rax, [rsp+2490h+WideCharStr]
0x18012ad8d  mov     [rsp+2490h+lpWideCharStr], rax; lpWideCharStr
0x18012ad92  mov     r9d, 0FFFFFFFFh; cbMultiByte
0x18012ad98  lea     r8, [rsp+2490h+TempFileName]; lpMultiByteStr
0x18012ada0  xor     edx, edx; dwFlags
0x18012ada2  xor     ecx, ecx; CodePage
0x18012ada4  call    cs:__imp_MultiByteToWideChar
0x18012adaa  mov     rcx, [rbp+arg_0]; this
0x18012adae  call    ?GetSyskind@GEN_PROJECT@@QEAA?AW4tagSYSKIND@@XZ; GEN_PROJECT::GetSyskind(void)
0x18012adb3  lea     r8, [rsp+2490h+var_2420]
0x18012adb8  lea     rdx, [rsp+2490h+WideCharStr]
0x18012adc0  mov     ecx, eax
0x18012adc2  call    CreateTypeLib2Wrap
0x18012adc7  mov     [rsp+2490h+var_2450], eax
0x18012adcb  cmp     [rsp+2490h+var_2450], 0
0x18012add0  jge     short loc_18012ADD7
0x18012add2  jmp     loc_18012CCBA
0x18012add7  mov     rax, [rsp+2490h+var_2420]
0x18012addc  mov     rax, [rax]
0x18012addf  lea     r8, [rsp+2490h+var_90]
0x18012ade7  lea     rdx, IID_ITypeLib
0x18012adee  mov     rcx, [rsp+2490h+var_2420]
0x18012adf3  call    qword ptr [rax]
0x18012adf5  mov     rax, [rsp+2490h+var_2420]
0x18012adfa  mov     rax, [rax]
0x18012adfd  lea     r8, [rsp+2490h+var_23C8]
0x18012ae05  lea     rdx, IID_ICreateTypeLib2
0x18012ae0c  mov     rcx, [rsp+2490h+var_2420]
0x18012ae11  call    qword ptr [rax]
0x18012ae13  mov     eax, 3
0x18012ae18  mov     [rsp+2490h+var_2148], ax
0x18012ae20  mov     [rsp+2490h+var_2140], 481h
0x18012ae2b  mov     rax, [rsp+2490h+var_23C8]
0x18012ae33  mov     rax, [rax]
0x18012ae36  lea     r8, [rsp+2490h+var_2148]
0x18012ae3e  lea     rdx, GUID_FuncCustDataReturnErrors
0x18012ae45  mov     rcx, [rsp+2490h+var_23C8]
0x18012ae4d  call    qword ptr [rax+70h]
0x18012ae50  mov     rax, [rsp+2490h+var_23C8]
0x18012ae58  mov     rax, [rax]
0x18012ae5b  mov     rcx, [rsp+2490h+var_23C8]
0x18012ae63  call    qword ptr [rax+10h]
0x18012ae66  call    ?PebappCur@@YAPEAVEBAPP@@XZ; PebappCur(void)
0x18012ae6b  cmp     qword ptr [rax+0D8h], 0
0x18012ae73  jnz     short loc_18012AE8A
0x18012ae75  call    ?LoadStdoleTypeinfos@@YAJXZ; LoadStdoleTypeinfos(void)
0x18012ae7a  mov     [rsp+2490h+var_2450], eax
0x18012ae7e  cmp     [rsp+2490h+var_2450], 0
0x18012ae83  jge     short loc_18012AE8A
0x18012ae85  jmp     loc_18012CCBA
0x18012ae8a  call    ?PebappCur@@YAPEAVEBAPP@@XZ; PebappCur(void)
0x18012ae8f  mov     rax, [rax+0D8h]
0x18012ae96  mov     [rbp+var_78], rax
0x18012ae9a  mov     rax, [rbp+var_78]
0x18012ae9e  mov     rax, [rax]
0x18012aea1  mov     rcx, [rbp+var_78]
0x18012aea5  call    qword ptr [rax+8]
0x18012aea8  mov     rax, [rsp+2490h+var_2420]
0x18012aead  mov     rax, [rax]
0x18012aeb0  xor     edx, edx
0x18012aeb2  mov     rcx, [rsp+2490h+var_2420]
0x18012aeb7  call    qword ptr [rax+50h]
0x18012aeba  mov     [rsp+2490h+var_2450], eax
0x18012aebe  cmp     [rsp+2490h+var_2450], 0
0x18012aec3  jge     short loc_18012AECA
0x18012aec5  jmp     loc_18012CCBA
0x18012aeca  mov     rax, [rbp+arg_0]
0x18012aece  mov     rax, [rax]
0x18012aed1  lea     rcx, [rsp+2490h+var_23A0]
0x18012aed9  mov     qword ptr [rsp+2490h+cchWideChar], rcx
0x18012aede  lea     rcx, [rsp+2490h+var_2388]
0x18012aee6  mov     [rsp+2490h+lpWideCharStr], rcx
0x18012aeeb  lea     r9, [rsp+2490h+var_23B0]
0x18012aef3  lea     r8, [rsp+2490h+bstrString]
0x18012aefb  mov     edx, 0FFFFFFFFh
0x18012af00  mov     rcx, [rbp+arg_0]
0x18012af04  call    qword ptr [rax+48h]
0x18012af07  mov     [rsp+2490h+var_2450], eax
0x18012af0b  cmp     [rsp+2490h+var_2450], 0
0x18012af10  jge     short loc_18012AF17
0x18012af12  jmp     loc_18012CCBA
0x18012af17  cmp     [rsp+2490h+bstrString], 0
0x18012af20  jz      short loc_18012AF4A
0x18012af22  mov     rax, [rsp+2490h+var_2420]
0x18012af27  mov     rax, [rax]
0x18012af2a  mov     rdx, [rsp+2490h+bstrString]
0x18012af32  mov     rcx, [rsp+2490h+var_2420]
0x18012af37  call    qword ptr [rax+20h]
0x18012af3a  mov     [rsp+2490h+var_2450], eax
0x18012af3e  cmp     [rsp+2490h+var_2450], 0
0x18012af43  jge     short loc_18012AF4A
0x18012af45  jmp     loc_18012CCBA
0x18012af4a  cmp     [rsp+2490h+var_23B0], 0
0x18012af53  jz      short loc_18012AF7D
0x18012af55  mov     rax, [rsp+2490h+var_2420]
0x18012af5a  mov     rax, [rax]
0x18012af5d  mov     rdx, [rsp+2490h+var_23B0]
0x18012af65  mov     rcx, [rsp+2490h+var_2420]
0x18012af6a  call    qword ptr [rax+38h]
0x18012af6d  mov     [rsp+2490h+var_2450], eax
0x18012af71  cmp     [rsp+2490h+var_2450], 0
0x18012af76  jge     short loc_18012AF7D
0x18012af78  jmp     loc_18012CCBA
0x18012af7d  mov     rax, [rsp+2490h+var_2420]
0x18012af82  mov     rax, [rax]
0x18012af85  mov     edx, [rsp+2490h+var_2388]
0x18012af8c  mov     rcx, [rsp+2490h+var_2420]
0x18012af91  call    qword ptr [rax+48h]
0x18012af94  mov     [rsp+2490h+var_2450], eax
0x18012af98  cmp     [rsp+2490h+var_2450], 0
0x18012af9d  jge     short loc_18012AFA4
0x18012af9f  jmp     loc_18012CCBA
0x18012afa4  cmp     [rsp+2490h+var_23A0], 0
0x18012afad  jz      short loc_18012AFD7
0x18012afaf  mov     rax, [rsp+2490h+var_2420]
0x18012afb4  mov     rax, [rax]
0x18012afb7  mov     rdx, [rsp+2490h+var_23A0]
0x18012afbf  mov     rcx, [rsp+2490h+var_2420]
0x18012afc4  call    qword ptr [rax+40h]
0x18012afc7  mov     [rsp+2490h+var_2450], eax
0x18012afcb  cmp     [rsp+2490h+var_2450], 0
0x18012afd0  jge     short loc_18012AFD7
0x18012afd2  jmp     loc_18012CCBA
0x18012afd7  mov     rcx, [rbp+arg_0]; this
0x18012afdb  call    ?MinorVerNum@GEN_PROJECT@@QEAAGXZ; GEN_PROJECT::MinorVerNum(void)
0x18012afe0  mov     [rbp+var_28], ax
0x18012afe4  mov     rcx, [rbp+arg_0]; this
0x18012afe8  call    ?MajorVerNum@GEN_PROJECT@@QEAAGXZ; GEN_PROJECT::MajorVerNum(void)
0x18012afed  mov     rcx, [rsp+2490h+var_2420]
0x18012aff2  mov     rcx, [rcx]
0x18012aff5  mov     [rsp+2490h+var_2170], rcx
0x18012affd  movzx   edx, [rbp+var_28]
0x18012b001  movzx   r8d, dx
0x18012b005  movzx   edx, ax
0x18012b008  mov     rcx, [rsp+2490h+var_2420]
0x18012b00d  mov     rax, [rsp+2490h+var_2170]
0x18012b015  call    qword ptr [rax+28h]
0x18012b018  mov     [rsp+2490h+var_2450], eax
0x18012b01c  cmp     [rsp+2490h+var_2450], 0
0x18012b021  jge     short loc_18012B028
0x18012b023  jmp     loc_18012CCA4
0x18012b028  lea     rdx, [rsp+2490h+var_2130]; retstr
0x18012b030  mov     rcx, [rbp+arg_0]; this
0x18012b034  call    ?Guid@GEN_PROJECT@@QEAA?AU_GUID@@XZ; GEN_PROJECT::Guid(void)
0x18012b039  mov     rcx, [rsp+2490h+var_2420]
0x18012b03e  mov     rcx, [rcx]
0x18012b041  mov     [rsp+2490h+var_2198], rcx
0x18012b049  mov     rdx, rax
0x18012b04c  mov     rcx, [rsp+2490h+var_2420]
0x18012b051  mov     rax, [rsp+2490h+var_2198]
0x18012b059  call    qword ptr [rax+30h]
0x18012b05c  mov     [rsp+2490h+var_2450], eax
0x18012b060  cmp     [rsp+2490h+var_2450], 0
0x18012b065  jge     short loc_18012B06C
0x18012b067  jmp     loc_18012CCA4
0x18012b06c  mov     rax, [rbp+arg_0]
0x18012b070  mov     eax, [rax+138h]
0x18012b076  shl     eax, 1Bh
0x18012b079  sar     eax, 1Fh
0x18012b07c  test    eax, eax
0x18012b07e  jz      short loc_18012B08D
0x18012b080  mov     [rsp+2490h+var_23D4], 2
0x18012b08b  jmp     short loc_18012B098
0x18012b08d  mov     [rsp+2490h+var_23D4], 0
0x18012b098  mov     rax, [rbp+arg_0]
0x18012b09c  movzx   eax, word ptr [rax+230h]
0x18012b0a3  or      eax, [rsp+2490h+var_23D4]
0x18012b0aa  mov     rcx, [rsp+2490h+var_2420]
0x18012b0af  mov     rcx, [rcx]
0x18012b0b2  mov     [rsp+2490h+var_2330], rcx
0x18012b0ba  mov     edx, eax
0x18012b0bc  mov     rcx, [rsp+2490h+var_2420]
0x18012b0c1  mov     rax, [rsp+2490h+var_2330]
0x18012b0c9  call    qword ptr [rax+58h]
0x18012b0cc  mov     [rsp+2490h+var_2450], eax
0x18012b0d0  cmp     [rsp+2490h+var_2450], 0
0x18012b0d5  jge     short loc_18012B0DC
0x18012b0d7  jmp     loc_18012CCA4
0x18012b0dc  mov     rax, [rbp+arg_0]
0x18012b0e0  mov     rax, [rax]
0x18012b0e3  mov     rcx, [rbp+arg_0]
0x18012b0e7  call    qword ptr [rax+18h]
0x18012b0ea  mov     [rsp+2490h+var_2410], eax
0x18012b0f1  mov     [rsp+2490h+var_2440], 0
0x18012b0f9  jmp     short loc_18012B105
0x18012b0fb  mov     eax, [rsp+2490h+var_2440]
0x18012b0ff  inc     eax
0x18012b101  mov     [rsp+2490h+var_2440], eax
0x18012b105  mov     eax, [rsp+2490h+var_2410]
0x18012b10c  cmp     [rsp+2490h+var_2440], eax
0x18012b110  jnb     loc_18012B20F
0x18012b116  mov     rax, [rbp+arg_0]
0x18012b11a  mov     rax, [rax]
0x18012b11d  lea     r8, [rsp+2490h+var_2448]
0x18012b122  mov     edx, [rsp+2490h+var_2440]
0x18012b126  mov     rcx, [rbp+arg_0]
0x18012b12a  call    qword ptr [rax+20h]
0x18012b12d  mov     [rsp+2490h+var_2450], eax
0x18012b131  cmp     [rsp+2490h+var_2450], 0
0x18012b136  jge     short loc_18012B13D
0x18012b138  jmp     loc_18012CCBA
0x18012b13d  mov     rax, [rsp+2490h+var_2448]
0x18012b142  mov     rax, [rax+28h]
0x18012b146  mov     [rsp+2490h+var_2318], rax
0x18012b14e  xor     r8d, r8d; int
0x18012b151  xor     edx, edx; int
0x18012b153  mov     rcx, [rsp+2490h+var_2318]; this
0x18012b15b  call    ?EnsureInDeclaredState@BASIC_TYPEROOT@@QEAAJHH@Z; BASIC_TYPEROOT::EnsureInDeclaredState(int,int)
0x18012b160  mov     [rsp+2490h+var_2450], eax
0x18012b164  cmp     [rsp+2490h+var_2450], 0
0x18012b169  jge     short loc_18012B170
0x18012b16b  jmp     loc_18012CCBA
0x18012b170  mov     rcx, [rsp+2490h+var_2448]; this
0x18012b175  call    ?GetTypeKind@BASIC_TYPEINFO@@QEAA?AW4tagTYPEKIND@@XZ; BASIC_TYPEINFO::GetTypeKind(void)
0x18012b17a  cmp     eax, 8
0x18012b17d  jnz     short loc_18012B1E9
0x18012b17f  mov     rax, [rsp+2490h+var_2448]
0x18012b184  mov     rax, [rax+28h]
0x18012b188  mov     [rsp+2490h+var_2218], rax
0x18012b190  mov     rcx, [rsp+2490h+var_2218]
0x18012b198  call    ?Access@BASIC_TYPEROOT@@QEBA?AW4ACCESS@@XZ; BASIC_TYPEROOT::Access(void)
0x18012b19d  cmp     eax, 1
0x18012b1a0  jnz     short loc_18012B1E9
0x18012b1a2  mov     rax, [rsp+2490h+var_2448]
0x18012b1a7  mov     rax, [rax+28h]
0x18012b1ab  mov     [rsp+2490h+var_2308], rax
0x18012b1b3  mov     rcx, [rsp+2490h+var_2308]; this
0x18012b1bb  call    ?Pinstmgr@BASIC_TYPEROOT@@QEAAPEAVINSTMGR@@XZ; BASIC_TYPEROOT::Pinstmgr(void)
0x18012b1c0  mov     rcx, rax; this
0x18012b1c3  call    ?ItypExe@INSTMGR@@QEAAIXZ; INSTMGR::ItypExe(void)
0x18012b1c8  mov     [rsp+2490h+var_243C], eax
0x18012b1cc  cmp     [rsp+2490h+var_243C], 0FFFFFFFFh
0x18012b1d1  jz      short loc_18012B1E9
0x18012b1d3  cmp     [rbp+var_7C], 0FFFFFFFFh
0x18012b1d7  jz      short loc_18012B1E2
  ... truncated ...
```
