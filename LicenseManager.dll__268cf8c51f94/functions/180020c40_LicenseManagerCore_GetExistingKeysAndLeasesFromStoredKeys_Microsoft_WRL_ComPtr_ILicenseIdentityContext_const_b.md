# LicenseManagerCore::GetExistingKeysAndLeasesFromStoredKeys(Microsoft::WRL::ComPtr<ILicenseIdentityContext> const &,bool,ComArray<ComInterfaceTraits<IStoredKeyDocument>> &,ComArray<ComInterfaceTraits<IStoredLeaseDocument>> &)

- ea: `0x180020c40`
- end: `0x1800226c3`
- name: `?GetExistingKeysAndLeasesFromStoredKeys@LicenseManagerCore@@AEAAXAEBV?$ComPtr@UILicenseIdentityContext@@@WRL@Microsoft@@_NAEAV?$ComArray@U?$ComInterfaceTraits@UIStoredKeyDocument@@@@@@AEAV?$ComArray@U?$ComInterfaceTraits@UIStoredLeaseDocument@@@@@@@Z`
- size: `6787`
- prototype: ``
- caller_count: `4`
- callee_count: `32`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180020340`
- `0x1800226d0`
- `0x180022940`
- `0x18005a670`

## callees

- `0x180013b50`
- `0x180019c58`
- `0x18001a6f4`
- `0x18001a81c`
- `0x18001f268`
- `0x18001ff9c`
- `0x180020bc4`
- `0x180020c40`
- `0x18003ad9c`
- `0x18003b18c`
- `0x180040a68`
- `0x180044728`
- `0x180054a54`
- `0x1800593bc`
- `0x180066168`
- `0x18006ce2c`
- `0x18006ea5c`
- `0x18006eba8`
- `0x18006ec98`
- `0x18006ed2c`
- `0x180075e60`
- `0x180076300`
- `0x18007633c`
- `0x180076360`
- `0x1800767e0`
- `0x180076a00`
- `0x180076e64`
- `0x18008251f`
- `0x18008a400`
- `0x1800946f0`
- `0x18009500c`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800210ee`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800210ee`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020cf2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020cf2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800219b0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800219b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022608`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022608`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180020f51`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180020f51`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002160b`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002160b`
- `ext-ms-win-core-licensemanager-l1-1-0!CompareContentId` at `0x180020f2c`
- `ext-ms-win-core-licensemanager-l1-1-0!CompareContentId` at `0x180020f2c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021960`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021960`

## pseudocode

```c
// Hidden C++ exception states: #wind=67
__int64 __fastcall LicenseManagerCore::GetExistingKeysAndLeasesFromStoredKeys(
        __int64 a1,
        _QWORD *a2,
        char a3,
        __int64 a4,
        __int64 a5)
{
  _QWORD *v5; // rdi
  struct _RTL_CRITICAL_SECTION *v6; // rbx
  __int64 v7; // rax
  __int64 v8; // r13
  __int64 *v9; // rcx
  __int64 v10; // rax
  _lambda_608eb4e91e30957692f8e971acddbc70_ *v11; // rsi
  void *v12; // r12
  unsigned __int64 v13; // rbx
  size_t v14; // rbx
  unsigned __int64 v15; // r15
  size_t v16; // rcx
  void *v17; // rax
  WCHAR *v18; // rdi
  size_t v19; // rbx
  __int64 i; // rbx
  unsigned int v21; // r12d
  __int64 v22; // r15
  const WCHAR *v23; // rdi
  char v24; // al
  unsigned __int64 v25; // rcx
  bool v26; // zf
  const WCHAR *v27; // rax
  int v28; // eax
  const struct std::nothrow_t *v29; // rdx
  WCHAR *v30; // rcx
  __int64 *v31; // rdi
  __int64 (__fastcall ***v32)(_QWORD *, GUID *, _lambda_608eb4e91e30957692f8e971acddbc70_ **); // rbx
  unsigned int v33; // r12d
  _QWORD *v34; // rax
  _QWORD *v35; // rsi
  void *v36; // rcx
  _QWORD *v37; // r15
  const char *v38; // r9
  HANDLE EventW; // r15
  HANDLE v40; // rcx
  unsigned int v41; // r12d
  __int64 (__fastcall *v42)(_QWORD *, GUID *, _lambda_608eb4e91e30957692f8e971acddbc70_ **); // rbx
  _lambda_608eb4e91e30957692f8e971acddbc70_ *v43; // rcx
  int v44; // eax
  __int64 (__fastcall *v45)(_lambda_608eb4e91e30957692f8e971acddbc70_ *, GUID *, _QWORD **); // rbx
  _QWORD *v46; // rcx
  int v47; // eax
  struct _RTL_CRITICAL_SECTION *v48; // rbx
  _lambda_608eb4e91e30957692f8e971acddbc70_ *v49; // r12
  _lambda_608eb4e91e30957692f8e971acddbc70_ *v50; // r15
  _lambda_608eb4e91e30957692f8e971acddbc70_ *v51; // rbx
  __int64 *v52; // r15
  signed __int64 v53; // rdx
  unsigned __int64 v54; // rcx
  unsigned __int64 v55; // r8
  unsigned __int64 v56; // rdx
  signed __int64 v57; // rbx
  size_t v58; // rdx
  _lambda_608eb4e91e30957692f8e971acddbc70_ *v59; // r13
  void *v60; // rax
  _lambda_608eb4e91e30957692f8e971acddbc70_ **v61; // r9
  _lambda_608eb4e91e30957692f8e971acddbc70_ *v62; // r12
  _lambda_608eb4e91e30957692f8e971acddbc70_ *v63; // rcx
  _lambda_608eb4e91e30957692f8e971acddbc70_ *v64; // rbx
  _QWORD *v65; // r8
  _QWORD *v66; // r8
  _lambda_608eb4e91e30957692f8e971acddbc70_ *v67; // rcx
  _QWORD *v68; // r8
  __int64 v69; // rcx
  __int64 v70; // rcx
  const struct std::nothrow_t *v71; // rdx
  __int64 v72; // rax
  __int64 v73; // rcx
  _QWORD *v74; // rcx
  __int64 v75; // r12
  _lambda_608eb4e91e30957692f8e971acddbc70_ *v76; // rbx
  __int64 *v77; // rbx
  signed __int64 v78; // rdx
  unsigned __int64 v79; // rcx
  unsigned __int64 v80; // r8
  unsigned __int64 v81; // r13
  signed __int64 v82; // rdi
  size_t v83; // r13
  _lambda_608eb4e91e30957692f8e971acddbc70_ *v84; // r15
  void *v85; // rax
  _QWORD *v86; // r10
  _lambda_608eb4e91e30957692f8e971acddbc70_ *v87; // rdi
  _lambda_608eb4e91e30957692f8e971acddbc70_ *v88; // rcx
  _lambda_608eb4e91e30957692f8e971acddbc70_ *v89; // rbx
  _QWORD *v90; // r8
  _lambda_608eb4e91e30957692f8e971acddbc70_ *v91; // r8
  _lambda_608eb4e91e30957692f8e971acddbc70_ *v92; // rdx
  _QWORD *v93; // r9
  __int64 v94; // rcx
  __int64 v95; // rcx
  const struct std::nothrow_t *v96; // rdx
  _lambda_608eb4e91e30957692f8e971acddbc70_ *v97; // r15
  int v98; // edi
  _QWORD *v99; // rbx
  _QWORD *v100; // rax
  __int64 v101; // rsi
  __int64 v102; // rcx
  _QWORD *v103; // rax
  _QWORD *v104; // rsi
  wil *v105; // rcx
  _QWORD *v106; // rax
  _QWORD *v107; // r8
  __int64 v108; // r10
  _QWORD *v109; // rdi
  __int64 v110; // rdx
  unsigned __int64 v111; // rcx
  unsigned __int64 v112; // r8
  __int64 v113; // r15
  __int64 v114; // r13
  unsigned __int64 v115; // r12
  size_t v116; // rcx
  _QWORD *v117; // rsi
  void *v118; // rax
  __int64 v119; // r15
  _QWORD *v120; // r8
  _QWORD *v121; // rdx
  _QWORD *v122; // rcx
  unsigned __int64 v123; // r9
  char *v124; // rdx
  _QWORD *j; // rcx
  __int64 v126; // rdi
  __int64 v127; // rcx
  __int64 v128; // r15
  __int64 v129; // rdx
  unsigned __int64 v130; // rcx
  unsigned __int64 v131; // r8
  __int64 v132; // r12
  unsigned __int64 v133; // rsi
  size_t v134; // rcx
  char *v135; // rdi
  void *v136; // rax
  __int64 v137; // r12
  __int64 v138; // rcx
  __int64 v139; // rdx
  char *v140; // r8
  __int64 v141; // rcx
  _QWORD *v142; // r10
  __int64 v143; // rdi
  __int64 v144; // rdx
  unsigned __int64 v145; // rcx
  unsigned __int64 v146; // r8
  __int64 v147; // r15
  __int64 v148; // r12
  unsigned __int64 v149; // r13
  size_t v150; // r13
  char *v151; // rsi
  void *v152; // rax
  __int64 v153; // r15
  __int64 v154; // rdx
  char *v155; // r8
  __int64 v156; // rcx
  __int64 v157; // rcx
  char *v158; // rdi
  char *v159; // r15
  unsigned int v160; // esi
  struct _RTL_CRITICAL_SECTION *v161; // rdi
  unsigned int v162; // r13d
  __int64 v163; // rdi
  __int64 *v164; // rax
  __int64 v165; // r12
  __int64 v166; // rdx
  unsigned __int64 v167; // rcx
  unsigned __int64 v168; // r8
  unsigned __int64 v169; // rsi
  __int64 v170; // r15
  size_t v171; // rcx
  _QWORD *v172; // r10
  void *v173; // rax
  __int64 *v174; // r9
  __int64 v175; // rdx
  _QWORD *v176; // r8
  __int64 v177; // rcx
  __int64 v178; // r9
  __int64 v179; // r10
  __int64 v180; // r11
  unsigned __int64 v181; // rbx
  unsigned int v182; // edi
  __int64 v183; // r8
  LPCWCH k; // rsi
  __int64 v185; // rdx
  __int64 v186; // rcx
  unsigned __int64 v187; // rbx
  unsigned int v188; // r8d
  struct _RTL_CRITICAL_SECTION *v189; // r9
  __int64 v190; // rdx
  struct _RTL_CRITICAL_SECTION_DEBUG *v191; // rcx
  const WCHAR **v192; // rdx
  int v193; // ecx
  const WCHAR *v194; // rax
  struct _RTL_CRITICAL_SECTION **v195; // rdx
  unsigned int v196; // ecx
  struct _RTL_CRITICAL_SECTION *v197; // rax
  signed int LastError; // eax
  int v200; // edx
  unsigned int v201; // r8d
  int bIgnoreCase; // [rsp+20h] [rbp-1B8h]
  __int64 v203; // [rsp+28h] [rbp-1B0h]
  int v204; // [rsp+30h] [rbp-1A8h] BYREF
  char v205; // [rsp+34h] [rbp-1A4h]
  _lambda_608eb4e91e30957692f8e971acddbc70_ *v206[2]; // [rsp+38h] [rbp-1A0h]
  _lambda_608eb4e91e30957692f8e971acddbc70_ *v207; // [rsp+48h] [rbp-190h]
  __int64 v208; // [rsp+50h] [rbp-188h]
  _QWORD *v209; // [rsp+58h] [rbp-180h] BYREF
  struct _RTL_CRITICAL_SECTION *v210; // [rsp+60h] [rbp-178h] BYREF
  unsigned int v211; // [rsp+68h] [rbp-170h]
  _QWORD *v212; // [rsp+70h] [rbp-168h]
  _lambda_608eb4e91e30957692f8e971acddbc70_ *v213; // [rsp+78h] [rbp-160h] BYREF
  __int128 v214; // [rsp+80h] [rbp-158h] BYREF
  char *v215; // [rsp+90h] [rbp-148h]
  __int128 v216; // [rsp+98h] [rbp-140h] BYREF
  __int64 v217; // [rsp+A8h] [rbp-130h]
  unsigned __int64 v218; // [rsp+B0h] [rbp-128h]
  _QWORD *v219; // [rsp+B8h] [rbp-120h]
  void *Src; // [rsp+C0h] [rbp-118h] BYREF
  __int64 v221; // [rsp+C8h] [rbp-110h] BYREF
  _lambda_608eb4e91e30957692f8e971acddbc70_ *v222; // [rsp+D0h] [rbp-108h] BYREF
  _lambda_608eb4e91e30957692f8e971acddbc70_ *v223; // [rsp+D8h] [rbp-100h] BYREF
  _QWORD *v224; // [rsp+E0h] [rbp-F8h]
  _QWORD *v225; // [rsp+E8h] [rbp-F0h]
  struct _RTL_CRITICAL_SECTION *v226; // [rsp+F0h] [rbp-E8h] BYREF
  __int64 v227; // [rsp+F8h] [rbp-E0h]
  __int64 v228; // [rsp+100h] [rbp-D8h] BYREF
  _lambda_608eb4e91e30957692f8e971acddbc70_ *v229; // [rsp+108h] [rbp-D0h]
  _QWORD *v230; // [rsp+110h] [rbp-C8h]
  _QWORD *v231; // [rsp+118h] [rbp-C0h]
  __int64 v232; // [rsp+120h] [rbp-B8h] BYREF
  struct _RTL_CRITICAL_SECTION *v233; // [rsp+128h] [rbp-B0h]
  __int64 v234; // [rsp+130h] [rbp-A8h]
  __int64 v235; // [rsp+138h] [rbp-A0h]
  __int64 *v236; // [rsp+140h] [rbp-98h]
  _BYTE pExceptionObject[24]; // [rsp+148h] [rbp-90h] BYREF
  LPCWCH lpString2[2]; // [rsp+160h] [rbp-78h] BYREF
  int cchCount2[2]; // [rsp+170h] [rbp-68h]
  unsigned __int64 v240; // [rsp+178h] [rbp-60h]
  int *v241; // [rsp+180h] [rbp-58h]
  __int64 v242; // [rsp+188h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+0h]

  v205 = a3;
  v219 = a2;
  v5 = (_QWORD *)a1;
  v212 = (_QWORD *)a1;
  v230 = (_QWORD *)a1;
  v231 = a2;
  v235 = a4;
  v234 = a5;
  LODWORD(v224) = 0;
  LODWORD(v208) = 0;
  v214 = 0;
  v215 = 0;
  v216 = 0;
  v217 = 0;
  *(_OWORD *)v206 = 0;
  v207 = 0;
  v6 = (struct _RTL_CRITICAL_SECTION *)(a1 + 64);
  v229 = (_lambda_608eb4e91e30957692f8e971acddbc70_ *)(a1 + 64);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 64));
  v233 = v6;
  v210 = 0;
  v211 = 0;
  (*(void (__fastcall **)(_QWORD *, struct _RTL_CRITICAL_SECTION **))(v5[4] + 24LL))(v5 + 4, &v210);
  v7 = 0;
  v204 = 0;
  if ( v211 )
  {
    while ( 1 )
    {
      Src = 0;
      v8 = 8 * v7;
      v9 = (__int64 *)*((_QWORD *)&v210->DebugInfo + v7);
      v10 = *v9;
      Src = 0;
      (*(void (__fastcall **)(__int64 *, void **))(v10 + 104))(v9, &Src);
      v11 = 0;
      v226 = 0;
      v12 = Src;
      *(_OWORD *)lpString2 = 0;
      *(_QWORD *)cchCount2 = 0;
      v240 = 0;
      v13 = -1;
      do
        ++v13;
      while ( *((_WORD *)Src + v13) );
      if ( v13 > 0x7FFFFFFFFFFFFFFELL )
        std::_Xlen_string();
      if ( v13 > 7 )
        break;
      *(_QWORD *)cchCount2 = v13;
      v240 = 7;
      v14 = 2 * v13;
      memcpy_0(lpString2, Src, v14);
      *(_WORD *)((char *)lpString2 + v14) = 0;
LABEL_20:
      for ( i = v5[17]; i != v5[18]; i += 48 )
      {
        v21 = cchCount2[0];
        v22 = *(_QWORD *)(i + 16);
        v23 = lpString2[0];
        if ( v240 <= 7 )
          v23 = (const WCHAR *)lpString2;
        v24 = IsCompareContentIdPresent();
        v25 = *(_QWORD *)(i + 24);
        v26 = v24 == 0;
        v27 = (const WCHAR *)i;
        if ( v26 )
        {
          if ( v25 > 7 )
            v27 = *(const WCHAR **)i;
          v28 = CompareStringOrdinal(v27, v22, v23, v21, 1) - 2;
        }
        else
        {
          if ( v25 > 7 )
            v27 = *(const WCHAR **)i;
          v28 = CompareContentId(v27, (unsigned int)v22, v23, v21);
        }
        v5 = v212;
        if ( !v28 )
          goto LABEL_34;
      }
      i = v5[18];
LABEL_34:
      if ( v240 > 7 )
      {
        v29 = (const struct std::nothrow_t *)(2 * v240 + 2);
        v30 = (WCHAR *)lpString2[0];
        if ( (unsigned __int64)v29 >= 0x1000 )
        {
          if ( (unsigned __int64)lpString2[0] - *((_QWORD *)lpString2[0] - 1) - 8 > 0x1F )
            goto LABEL_191;
          v29 = (const struct std::nothrow_t *)(2 * v240 + 41);
          v30 = (WCHAR *)*((_QWORD *)lpString2[0] - 1);
        }
        operator delete(v30, v29);
      }
      *(_QWORD *)cchCount2 = 0;
      v240 = 7;
      LOWORD(lpString2[0]) = 0;
      if ( i != v5[18] )
      {
        v31 = *(__int64 **)(i + 40);
        v236 = v31;
        if ( v31 )
          (*(void (__fastcall **)(__int64 *))(*v31 + 8))(v31);
        v209 = 0;
        v213 = 0;
        v32 = 0;
        v218 = 0;
        v33 = (unsigned int)v224 | 5;
        LODWORD(v208) = (unsigned int)v224 | 5;
        v34 = operator new(0x40u, (const struct std::nothrow_t *)std::nothrow);
        v35 = v34;
        v36 = v34;
        v225 = v34;
        v224 = v34;
        v37 = 0;
        if ( v34 )
        {
          lpString2[0] = (LPCWCH)v34;
          *v34 = &IRootsCallback::`vftable';
          v34[1] = &IKeyLicenseCallbackWaiter::`vftable';
          *((_DWORD *)v34 + 5) = 1;
          *v34 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IKeyLicenseCallback,IKeyLicenseCallbackWaiter>::`vftable'{for `IKeyLicenseCallback'};
          v34[1] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IKeyLicenseCallback,IKeyLicenseCallbackWaiter>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IKeyLicenseCallbackWaiter>'};
          if ( Microsoft::WRL::Details::ModuleBase::module_ )
            (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                                 + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
          *v35 = &LicenseCallback::`vftable'{for `IKeyLicenseCallback'};
          v35[1] = &LicenseCallback::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IKeyLicenseCallbackWaiter>'};
          v35[4] = 0;
          v35[3] = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
          *((_DWORD *)v35 + 10) = -2147418113;
          v35[6] = 0;
          v35[7] = 0;
          EventW = CreateEventW(0, 0, 0, 0);
          v40 = (HANDLE)v35[4];
          if ( EventW != v40 )
          {
            if ( v40 && !(*(unsigned __int8 (__fastcall **)(_QWORD *))v35[3])(v35 + 3) )
            {
              LastError = GetLastError();
              if ( LastError > 0 )
                LastError = (unsigned __int16)LastError | 0x80070000;
              Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v200, v201);
              __debugbreak();
            }
            v35[4] = EventW;
          }
          if ( !v35[4] )
            wil::details::in1diag3::_Throw_GetLastError(
              retaddr,
              (void *)0xA5,
              (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\managercore.cpp",
              v38);
          v32 = (__int64 (__fastcall ***)(_QWORD *, GUID *, _lambda_608eb4e91e30957692f8e971acddbc70_ **))v35;
          v218 = (unsigned __int64)v35;
          v36 = 0;
          v37 = v35;
        }
        if ( v36 )
          operator delete(v36);
        v41 = v33 & 0xFFFFFFF9 | 2;
        LODWORD(v208) = v41;
        if ( !v37 )
        {
          std::bad_alloc::bad_alloc((std::bad_alloc *)pExceptionObject);
          throw (std::bad_alloc *)pExceptionObject;
        }
        v42 = **v32;
        v43 = v213;
        if ( v213 )
        {
          v213 = 0;
          (*(void (__fastcall **)(_lambda_608eb4e91e30957692f8e971acddbc70_ *, _QWORD))(*(_QWORD *)v43 + 16LL))(
            v43,
            *(_QWORD *)v43);
        }
        v44 = v42(v37, &GUID_85f3fad7_61e8_4612_9f09_2d1af999aa40, &v213);
        if ( v44 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x25,
            (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\manager.cpp",
            (const char *)(unsigned int)v44,
            bIgnoreCase);
        LODWORD(v208) = v41 & 0xFFFFFFFD;
        (*(void (__fastcall **)(_QWORD *))(*v37 + 16LL))(v37);
        v11 = v213;
        v226 = (struct _RTL_CRITICAL_SECTION *)v213;
        LODWORD(v224) = v41 & 0xFFFFFFFC;
        v45 = **(__int64 (__fastcall ***)(_lambda_608eb4e91e30957692f8e971acddbc70_ *, GUID *, _QWORD **))v213;
        v46 = v209;
        if ( v209 )
        {
          v209 = 0;
          (*(void (__fastcall **)(_QWORD *, _QWORD))(*v46 + 16LL))(v46, *v46);
        }
        v47 = v45(v11, &GUID_31b9a58b_7f4e_48b0_b70f_0aaccefa8ab6, &v209);
        if ( v47 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x5FA,
            (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\managercore.cpp",
            (const char *)(unsigned int)v47,
            bIgnoreCase);
        (*(void (__fastcall **)(__int64 *, _QWORD *, _QWORD **))(*v31 + 48))(v31, v219, &v209);
        v48 = v210;
        v222 = v11;
        (*(void (__fastcall **)(_lambda_608eb4e91e30957692f8e971acddbc70_ *))(*(_QWORD *)v11 + 8LL))(v11);
        v49 = *(_lambda_608eb4e91e30957692f8e971acddbc70_ **)((char *)&v48->DebugInfo + v8);
        v223 = v49;
        if ( v49 )
          (*(void (__fastcall **)(_lambda_608eb4e91e30957692f8e971acddbc70_ *))(*(_QWORD *)v49 + 8LL))(v49);
        v50 = v206[1];
        if ( v206[1] != v207 )
        {
          *(_QWORD *)v206[1] = 0;
          if ( v50 == (_lambda_608eb4e91e30957692f8e971acddbc70_ *)&v222 )
          {
            v51 = v222;
          }
          else
          {
            *(_QWORD *)v50 = v11;
            v51 = 0;
          }
          v52 = (__int64 *)((char *)v50 + 8);
          *v52 = 0;
          if ( v52 != (__int64 *)&v223 )
          {
            *v52 = (__int64)v49;
            v49 = 0;
          }
          v206[1] = (_lambda_608eb4e91e30957692f8e971acddbc70_ *)((char *)v206[1] + 16);
LABEL_120:
          if ( v49 )
          {
            v223 = 0;
            (*(void (__fastcall **)(_lambda_608eb4e91e30957692f8e971acddbc70_ *))(*(_QWORD *)v49 + 16LL))(v49);
          }
          if ( v51 )
          {
            v222 = 0;
            (*(void (__fastcall **)(_lambda_608eb4e91e30957692f8e971acddbc70_ *))(*(_QWORD *)v51 + 16LL))(v51);
          }
          if ( v205 )
          {
            v72 = *v31;
            v221 = 0;
            (*(void (__fastcall **)(__int64 *, __int64 *))(v72 + 136))(v31, &v221);
            v73 = v221;
            if ( v221 )
            {
              v221 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v73 + 16LL))(v73);
            }
            Sleep(0);
          }
          v74 = v209;
          if ( v209 )
          {
            v209 = 0;
            (*(void (__fastcall **)(_QWORD *))(*v74 + 16LL))(v74);
          }
          if ( v31 )
            (*(void (__fastcall **)(__int64 *))(*v31 + 16))(v31);
          goto LABEL_185;
        }
        v53 = (v206[1] - v206[0]) >> 4;
        if ( v53 == 0xFFFFFFFFFFFFFFFLL )
          std::vector<LicenseProxyService::UserRootThreadParam>::_Xlength();
        v54 = (v207 - v206[0]) >> 4;
        v55 = v54 >> 1;
        if ( v54 > 0xFFFFFFFFFFFFFFFLL - (v54 >> 1) )
          goto LABEL_369;
        v56 = v53 + 1;
        v218 = v56;
        if ( v55 + v54 >= v56 )
          v56 = v55 + v54;
        if ( v56 > 0xFFFFFFFFFFFFFFFLL )
LABEL_369:
          std::_Throw_bad_array_new_length();
        v57 = v206[1] - v206[0];
        v58 = 16 * v56;
        v225 = (_QWORD *)v58;
        if ( v58 )
        {
          if ( v58 < 0x1000 )
          {
            v59 = (_lambda_608eb4e91e30957692f8e971acddbc70_ *)operator new(v58);
          }
          else
          {
            if ( v58 + 39 < v58 )
              goto LABEL_369;
            v60 = operator new(v58 + 39);
            if ( !v60 )
LABEL_192:
              __fastfail(5u);
            v59 = (_lambda_608eb4e91e30957692f8e971acddbc70_ *)(((unsigned __int64)v60 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
            *((_QWORD *)v59 - 1) = v60;
          }
        }
        else
        {
          v59 = 0;
        }
        v61 = (_lambda_608eb4e91e30957692f8e971acddbc70_ **)((char *)v59 + (v57 & 0xFFFFFFFFFFFFFFF0uLL));
        *v61 = 0;
        if ( v61 != &v222 )
        {
          *v61 = v11;
          v222 = 0;
        }
        v61[1] = 0;
        if ( v61 + 1 != &v223 )
        {
          v61[1] = v49;
          v223 = 0;
        }
        v62 = v206[1];
        v63 = v59;
        v64 = v206[0];
        if ( v50 == v206[1] )
        {
          if ( v206[0] != v206[1] )
          {
            do
            {
              *(_QWORD *)v63 = 0;
              if ( v63 != v64 )
              {
                *(_QWORD *)v63 = *(_QWORD *)v64;
                *(_QWORD *)v64 = 0;
              }
              v65 = (_QWORD *)((char *)v64 + 8);
              *((_QWORD *)v63 + 1) = 0;
              if ( (char *)v63 + 8 != (char *)v64 + 8 )
              {
                *((_QWORD *)v63 + 1) = *v65;
                *v65 = 0;
              }
              v63 = (_lambda_608eb4e91e30957692f8e971acddbc70_ *)((char *)v63 + 16);
              v64 = (_lambda_608eb4e91e30957692f8e971acddbc70_ *)((char *)v64 + 16);
            }
            while ( v64 != v62 );
            goto LABEL_106;
          }
        }
        else
        {
          if ( v206[0] != v50 )
          {
            do
            {
              *(_QWORD *)v63 = 0;
              if ( v63 != v64 )
              {
                *(_QWORD *)v63 = *(_QWORD *)v64;
                *(_QWORD *)v64 = 0;
              }
              v66 = (_QWORD *)((char *)v64 + 8);
              *((_QWORD *)v63 + 1) = 0;
              if ( (char *)v63 + 8 != (char *)v64 + 8 )
              {
                *((_QWORD *)v63 + 1) = *v66;
                *v66 = 0;
              }
              v63 = (_lambda_608eb4e91e30957692f8e971acddbc70_ *)((char *)v63 + 16);
              v64 = (_lambda_608eb4e91e30957692f8e971acddbc70_ *)((char *)v64 + 16);
            }
            while ( v64 != v50 );
            v62 = v206[1];
            v64 = v206[0];
          }
          v67 = (_lambda_608eb4e91e30957692f8e971acddbc70_ *)(v61 + 2);
          if ( v50 != v62 )
          {
            do
            {
              *(_QWORD *)v67 = 0;
              if ( v67 != v50 )
              {
                *(_QWORD *)v67 = *(_QWORD *)v50;
                *(_QWORD *)v50 = 0;
              }
              v68 = (_QWORD *)((char *)v50 + 8);
              *((_QWORD *)v67 + 1) = 0;
              if ( (char *)v67 + 8 != (char *)v50 + 8 )
              {
                *((_QWORD *)v67 + 1) = *v68;
                *v68 = 0;
              }
              v67 = (_lambda_608eb4e91e30957692f8e971acddbc70_ *)((char *)v67 + 16);
              v50 = (_lambda_608eb4e91e30957692f8e971acddbc70_ *)((char *)v50 + 16);
            }
            while ( v50 != v62 );
LABEL_106:
            v64 = v206[0];
            v62 = v206[1];
          }
        }
        if ( v64 )
        {
          if ( v64 != v62 )
          {
            do
            {
              v69 = *((_QWORD *)v64 + 1);
              if ( v69 )
              {
                *((_QWORD *)v64 + 1) = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v69 + 16LL))(v69);
              }
              v70 = *(_QWORD *)v64;
              if ( *(_QWORD *)v64 )
              {
                *(_QWORD *)v64 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v70 + 16LL))(v70);
              }
              v64 = (_lambda_608eb4e91e30957692f8e971acddbc70_ *)((char *)v64 + 16);
            }
            while ( v64 != v62 );
            v64 = v206[0];
          }
          v71 = (const struct std::nothrow_t *)((v207 - v64) & 0xFFFFFFFFFFFFFFF0uLL);
          if ( (unsigned __int64)v71 >= 0x1000 )
          {
            if ( (unsigned __int64)v64 - *((_QWORD *)v64 - 1) - 8 > 0x1F )
              goto LABEL_192;
            v71 = (const struct std::nothrow_t *)((char *)v71 + 39);
            v64 = (_lambda_608eb4e91e30957692f8e971acddbc70_ *)*((_QWORD *)v64 - 1);
          }
          operator delete(v64, v71);
        }
        v206[0] = v59;
        v206[1] = (_lambda_608eb4e91e30957692f8e971acddbc70_ *)((char *)v59 + 16 * v218);
        v207 = (_lambda_608eb4e91e30957692f8e971acddbc70_ *)((char *)v225 + (_QWORD)v59);
        v49 = v223;
        v51 = v222;
        goto LABEL_120;
      }
      v227 = 0;
      v75 = *(__int64 *)((char *)&v210->DebugInfo + v8);
      v228 = v75;
      if ( v75 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v75 + 8LL))(v75);
      v76 = v206[1];
      if ( v206[1] == v207 )
      {
        v78 = (v206[1] - v206[0]) >> 4;
        if ( v78 == 0xFFFFFFFFFFFFFFFLL )
          std::vector<LicenseProxyService::UserRootThreadParam>::_Xlength();
        v79 = (v207 - v206[0]) >> 4;
        v80 = v79 >> 1;
        if ( v79 > 0xFFFFFFFFFFFFFFFLL - (v79 >> 1) )
          goto LABEL_374;
        v218 = v78 + 1;
        v81 = v78 + 1;
        if ( v80 + v79 >= v78 + 1 )
          v81 = v80 + v79;
        if ( v81 > 0xFFFFFFFFFFFFFFFLL )
LABEL_374:
          std::_Throw_bad_array_new_length();
        v82 = v206[1] - v206[0];
        v83 = 16 * v81;
        if ( v83 )
        {
          if ( v83 < 0x1000 )
          {
            v84 = (_lambda_608eb4e91e30957692f8e971acddbc70_ *)operator new(v83);
          }
          else
          {
            if ( v83 + 39 < v83 )
              goto LABEL_374;
            v85 = operator new(v83 + 39);
            if ( !v85 )
LABEL_193:
              __fastfail(5u);
            v84 = (_lambda_608eb4e91e30957692f8e971acddbc70_ *)(((unsigned __int64)v85 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
            *((_QWORD *)v84 - 1) = v85;
          }
        }
        else
        {
          v84 = 0;
        }
        v86 = (_QWORD *)((char *)v84 + (v82 & 0xFFFFFFFFFFFFFFF0uLL));
        *v86 = 0;
        v227 = 0;
        v86[1] = 0;
        if ( v86 + 1 != &v228 )
        {
          v86[1] = v75;
          v75 = 0;
          v228 = 0;
        }
        v87 = v206[1];
        if ( v76 == v206[1] )
        {
          v88 = v84;
          v89 = v206[0];
          if ( v206[0] != v206[1] )
          {
            do
            {
              *(_QWORD *)v88 = 0;
              if ( v88 != v89 )
              {
                *(_QWORD *)v88 = *(_QWORD *)v89;
                *(_QWORD *)v89 = 0;
              }
              v90 = (_QWORD *)((char *)v89 + 8);
              *((_QWORD *)v88 + 1) = 0;
              if ( (char *)v88 + 8 != (char *)v89 + 8 )
              {
                *((_QWORD *)v88 + 1) = *v90;
                *v90 = 0;
              }
              v88 = (_lambda_608eb4e91e30957692f8e971acddbc70_ *)((char *)v88 + 16);
              v89 = (_lambda_608eb4e91e30957692f8e971acddbc70_ *)((char *)v89 + 16);
            }
            while ( v89 != v87 );
            goto LABEL_169;
          }
        }
        else
        {
          v91 = v84;
          v92 = v206[0];
          if ( v206[0] != v76 )
          {
            do
            {
              *(_QWORD *)v91 = 0;
              if ( v91 != v92 )
              {
                *(_QWORD *)v91 = *(_QWORD *)v92;
                *(_QWORD *)v92 = 0;
              }
              v93 = (_QWORD *)((char *)v92 + 8);
              *((_QWORD *)v91 + 1) = 0;
              if ( (char *)v91 + 8 != (char *)v92 + 8 )
              {
                *((_QWORD *)v91 + 1) = *v93;
                *v93 = 0;
              }
              v91 = (_lambda_608eb4e91e30957692f8e971acddbc70_ *)((char *)v91 + 16);
              v92 = (_lambda_608eb4e91e30957692f8e971acddbc70_ *)((char *)v92 + 16);
            }
            while ( v92 != v76 );
            v87 = v206[1];
          }
          std::_Uninitialized_move<std::pair<Microsoft::WRL::ComPtr<IKeyLicenseCallbackWaiter>,Microsoft::WRL::ComPtr<IStoredKeyDocument>> *,std::allocator<std::pair<Microsoft::WRL::ComPtr<IKeyLicenseCallbackWaiter>,Microsoft::WRL::ComPtr<IStoredKeyDocument>>>>(
            v76,
            v87,
            v86 + 2);
LABEL_169:
          v89 = v206[0];
          v87 = v206[1];
        }
        if ( v89 )
        {
          if ( v89 != v87 )
          {
            do
            {
              v94 = *((_QWORD *)v89 + 1);
              if ( v94 )
              {
                *((_QWORD *)v89 + 1) = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
              }
              v95 = *(_QWORD *)v89;
              if ( *(_QWORD *)v89 )
              {
                *(_QWORD *)v89 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
              }
              v89 = (_lambda_608eb4e91e30957692f8e971acddbc70_ *)((char *)v89 + 16);
            }
            while ( v89 != v87 );
            v89 = v206[0];
          }
          v96 = (const struct std::nothrow_t *)((v207 - v89) & 0xFFFFFFFFFFFFFFF0uLL);
          if ( (unsigned __int64)v96 >= 0x1000 )
          {
            if ( (unsigned __int64)v89 - *((_QWORD *)v89 - 1) - 8 > 0x1F )
              goto LABEL_193;
            v96 = (const struct std::nothrow_t *)((char *)v96 + 39);
            v89 = (_lambda_608eb4e91e30957692f8e971acddbc70_ *)*((_QWORD *)v89 - 1);
          }
          operator delete(v89, v96);
        }
        v206[0] = v84;
        v206[1] = (_lambda_608eb4e91e30957692f8e971acddbc70_ *)((char *)v84 + 16 * v218);
        v207 = (_lambda_608eb4e91e30957692f8e971acddbc70_ *)((char *)v84 + v83);
        goto LABEL_183;
      }
      *(_QWORD *)v206[1] = 0;
      v227 = 0;
      v77 = (__int64 *)((char *)v76 + 8);
      *v77 = 0;
      if ( v77 != &v228 )
      {
        *v77 = v75;
        v75 = 0;
      }
      v206[1] = (_lambda_608eb4e91e30957692f8e971acddbc70_ *)((char *)v206[1] + 16);
LABEL_183:
      if ( v75 )
      {
        v228 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v75 + 16LL))(v75);
      }
LABEL_185:
      if ( v11 )
        (*(void (__fastcall **)(_lambda_608eb4e91e30957692f8e971acddbc70_ *))(*(_QWORD *)v11 + 16LL))(v11);
      if ( Src )
        CoTaskMemFree(Src);
      v7 = (unsigned int)(v204 + 1);
      v204 = v7;
      if ( (unsigned int)v7 >= v211 )
      {
        v6 = (struct _RTL_CRITICAL_SECTION *)v229;
        goto LABEL_195;
      }
      v5 = v212;
    }
    v15 = v13 | 7;
    if ( (v13 | 7) <= 0x7FFFFFFFFFFFFFFELL )
    {
      if ( v15 < 0xA )
        v15 = 10;
      if ( v15 + 1 > 0x7FFFFFFFFFFFFFFFLL )
LABEL_376:
        std::_Throw_bad_array_new_length();
      v16 = 2 * (v15 + 1);
      if ( !v16 )
      {
        v18 = 0;
LABEL_19:
        lpString2[0] = v18;
        *(_QWORD *)cchCount2 = v13;
        v240 = v15;
        v19 = v13;
        memcpy_0(v18, v12, v19 * 2);
        v18[v19] = 0;
        v5 = v212;
        goto LABEL_20;
      }
    }
    else
    {
      v15 = 0x7FFFFFFFFFFFFFFELL;
      v16 = -2;
    }
    if ( v16 < 0x1000 )
    {
      v18 = (WCHAR *)operator new(v16);
    }
    else
    {
      if ( v16 + 39 < v16 )
        goto LABEL_376;
      v17 = operator new(v16 + 39);
      if ( !v17 )
LABEL_191:
        __fastfail(5u);
      v18 = (WCHAR *)(((unsigned __int64)v17 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
      *((_QWORD *)v18 - 1) = v17;
    }
    goto LABEL_19;
  }
LABEL_195:
  ComArray<ComInterfaceTraits<IStoredLicenseDocument>>::_free(&v210);
  if ( v6 )
    LeaveCriticalSection(v6);
  v97 = v206[0];
  v229 = v206[1];
  while ( 1 )
  {
    v213 = v97;
    if ( v97 == v229 )
      break;
    v98 = 0;
    v208 = 0;
    v209 = 0;
    v99 = *(_QWORD **)v97;
    v225 = v99;
    if ( v99 )
    {
      (*(void (__fastcall **)(_QWORD *))(*v99 + 8LL))(v99);
      try
      {
        (*(void (**)(void))(*v99 + 24LL))();
        v100 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD *, __int64 *))(*v99 + 32LL))(v99, &v221);
        v101 = *v100;
        if ( *v100 )
        {
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v101 + 8LL))(*v100);
          v208 = v101;
        }
        v102 = v221;
        if ( v221 )
        {
          v221 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v102 + 16LL))(v102);
        }
        v103 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD *, void **))(*v99 + 40LL))(v99, &Src);
        v104 = (_QWORD *)*v103;
        if ( *v103 )
        {
          (*(void (__fastcall **)(_QWORD))(*v104 + 8LL))(*v103);
          v209 = v104;
        }
        v105 = (wil *)Src;
        if ( Src )
        {
          Src = 0;
          (*(void (__fastcall **)(wil *))(*(_QWORD *)v105 + 16LL))(v105);
        }
      }
      catch ( ... )
      {
        v204 = wil::ResultFromCaughtException(v105);
        v98 = v204;
        if ( (v204 & 0xF000) == 0x8000 && (v204 & 0x1FFF0000) == 0x3F0000 && v204 < 0 )
        {
          LODWORD(v203) = v204;
          LogMessage(
            2u,
            "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\managercore.cpp",
            0x626u,
            "LicenseManagerCore::GetExistingKeysAndLeasesFromStoredKeys",
            (wchar_t *)L"Running key is invalid. (0x%08x)",
            v203);
          v99 = v225;
          v106 = v230;
          v212 = v230;
          v107 = v231;
          v219 = v231;
          goto LABEL_281;
        }
        v97 = v213;
        v99 = v225;
        v212 = v230;
        v219 = v231;
      }
    }
    v108 = v208;
    if ( !v208 )
    {
      if ( v98 < 0 )
      {
        if ( (unsigned int)dword_1800F11D0 > 5
          && (qword_1800F11E0 & 0x400000000000LL) != 0
          && (qword_1800F11E8 & 0x400000000000LL) == qword_1800F11E8 )
        {
          v204 = v98;
          v241 = &v204;
          v242 = 4;
          tlgWriteTransfer_EtwEventWriteTransfer(
            (unsigned int)&dword_1800F11D0,
            (unsigned int)&dword_1800D77C4,
            0,
            0,
            3,
            (__int64)lpString2);
        }
        LODWORD(v203) = v98;
        LogMessage(
          1u,
          "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\managercore.cpp",
          0x636u,
          "LicenseManagerCore::GetExistingKeysAndLeasesFromStoredKeys",
          (wchar_t *)L"Running key is invalid. (0x%08x)",
          v203);
      }
      v126 = *((_QWORD *)v97 + 1);
      if ( v126 )
      {
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v126 + 8LL))(*((_QWORD *)v97 + 1));
        v208 = v126;
      }
      if ( *((_QWORD *)&v216 + 1) != v217 )
      {
        v127 = *((_QWORD *)v97 + 1);
        **((_QWORD **)&v216 + 1) = v127;
        if ( v127 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v127 + 8LL))(v127);
        *((_QWORD *)&v216 + 1) += 8LL;
        goto LABEL_280;
      }
      v128 = *((_QWORD *)&v216 + 1);
      v129 = (__int64)(*((_QWORD *)&v216 + 1) - v216) >> 3;
      if ( v129 == 0x1FFFFFFFFFFFFFFFLL )
LABEL_378:
        std::vector<LicenseProxyService::UserRootThreadParam>::_Xlength();
      v130 = (v217 - (__int64)v216) >> 3;
      v131 = v130 >> 1;
      if ( v130 > 0x1FFFFFFFFFFFFFFFLL - (v130 >> 1) )
        goto LABEL_382;
      v132 = *((_QWORD *)&v216 + 1) - v216;
      v114 = v129 + 1;
      v133 = v129 + 1;
      if ( v130 + v131 >= v129 + 1 )
        v133 = v130 + v131;
      if ( v133 > 0x1FFFFFFFFFFFFFFFLL )
LABEL_382:
        std::_Throw_bad_array_new_length();
      v134 = 8 * v133;
      if ( 8 * v133 )
      {
        if ( v134 < 0x1000 )
        {
          v135 = (char *)operator new(v134);
        }
        else
        {
          if ( v134 + 39 < v134 )
            goto LABEL_382;
          v136 = operator new(v134 + 39);
          if ( !v136 )
            goto LABEL_296;
          v135 = (char *)(((unsigned __int64)v136 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
          *((_QWORD *)v135 - 1) = v136;
        }
      }
      else
      {
        v135 = 0;
      }
      v137 = v132 >> 3;
      v138 = *((_QWORD *)v213 + 1);
      *(_QWORD *)&v135[8 * v137] = v138;
      if ( v138 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v138 + 8LL))(v138);
      v139 = *((_QWORD *)&v216 + 1);
      v140 = v135;
      v141 = v216;
      if ( v128 != *((_QWORD *)&v216 + 1) )
      {
        std::_Uninitialized_move<Microsoft::WRL::ComPtr<IStoredKeyDocument> *,std::allocator<Microsoft::WRL::ComPtr<IStoredKeyDocument>>>(
          v216,
          v128,
          v135);
        v140 = &v135[8 * v137 + 8];
        v139 = *((_QWORD *)&v216 + 1);
        v141 = v128;
      }
      std::_Uninitialized_move<Microsoft::WRL::ComPtr<IStoredKeyDocument> *,std::allocator<Microsoft::WRL::ComPtr<IStoredKeyDocument>>>(
        v141,
        v139,
        v140);
      v123 = v133;
      v124 = v135;
      goto LABEL_279;
    }
    if ( *((_QWORD *)&v216 + 1) != v217 )
    {
      **((_QWORD **)&v216 + 1) = v208;
      if ( v108 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v108 + 8LL))(v108);
      *((_QWORD *)&v216 + 1) += 8LL;
      goto LABEL_280;
    }
    v109 = (_QWORD *)*((_QWORD *)&v216 + 1);
    v110 = (__int64)(*((_QWORD *)&v216 + 1) - v216) >> 3;
    if ( v110 == 0x1FFFFFFFFFFFFFFFLL )
      goto LABEL_378;
    v111 = (v217 - (__int64)v216) >> 3;
    v112 = v111 >> 1;
    if ( v111 > 0x1FFFFFFFFFFFFFFFLL - (v111 >> 1) )
      goto LABEL_382;
    v113 = *((_QWORD *)&v216 + 1) - v216;
    v114 = v110 + 1;
    v115 = v110 + 1;
    if ( v112 + v111 >= v110 + 1 )
      v115 = v112 + v111;
    if ( v115 > 0x1FFFFFFFFFFFFFFFLL )
      goto LABEL_382;
    v116 = 8 * v115;
    if ( 8 * v115 )
    {
      if ( v116 < 0x1000 )
      {
        v117 = operator new(v116);
      }
      else
      {
        if ( v116 + 39 < v116 )
          goto LABEL_382;
        v118 = operator new(v116 + 39);
        if ( !v118 )
          goto LABEL_296;
        v117 = (_QWORD *)(((unsigned __int64)v118 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
        *(v117 - 1) = v118;
      }
      v108 = v208;
    }
    else
    {
      v117 = 0;
    }
    v119 = v113 >> 3;
    v117[v119] = v108;
    if ( v108 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v108 + 8LL))(v108);
    v120 = (_QWORD *)*((_QWORD *)&v216 + 1);
    v121 = v117;
    v122 = (_QWORD *)v216;
    if ( v109 == *((_QWORD **)&v216 + 1) )
    {
      if ( (_QWORD)v216 != *((_QWORD *)&v216 + 1) )
      {
        do
        {
          *v121 = 0;
          if ( v121 != v122 )
          {
            *v121 = *v122;
            *v122 = 0;
          }
          ++v121;
          ++v122;
        }
        while ( v122 != v120 );
        v123 = v115;
        v124 = (char *)v117;
        goto LABEL_279;
      }
    }
    else
    {
      if ( (_QWORD *)v216 != v109 )
      {
        do
        {
          *v121 = 0;
          if ( v121 != v122 )
          {
            *v121 = *v122;
            *v122 = 0;
          }
          ++v121;
          ++v122;
        }
        while ( v122 != v109 );
        v120 = (_QWORD *)*((_QWORD *)&v216 + 1);
      }
      for ( j = &v117[v119 + 1]; v109 != v120; ++v109 )
      {
        *j = 0;
        if ( j != v109 )
        {
          *j = *v109;
          *v109 = 0;
        }
        ++j;
      }
    }
    v123 = v115;
    v124 = (char *)v117;
LABEL_279:
    std::vector<Microsoft::WRL::ComPtr<IStoredKeyDocument>>::_Change_array(&v216, v124, v114, v123);
LABEL_280:
    v107 = v219;
    v106 = v212;
LABEL_281:
    v142 = v209;
    if ( v209 )
    {
      v143 = *((_QWORD *)&v214 + 1);
      if ( *((char **)&v214 + 1) == v215 )
      {
        v144 = (__int64)(*((_QWORD *)&v214 + 1) - v214) >> 3;
        if ( v144 == 0x1FFFFFFFFFFFFFFFLL )
          std::vector<LicenseProxyService::UserRootThreadParam>::_Xlength();
        v145 = (__int64)&v215[-v214] >> 3;
        v146 = v145 >> 1;
        if ( v145 > 0x1FFFFFFFFFFFFFFFLL - (v145 >> 1) )
          goto LABEL_382;
        v147 = *((_QWORD *)&v214 + 1) - v214;
        v148 = v144 + 1;
        v149 = v144 + 1;
        if ( v146 + v145 >= v144 + 1 )
          v149 = v146 + v145;
        if ( v149 > 0x1FFFFFFFFFFFFFFFLL )
          goto LABEL_382;
        v150 = 8 * v149;
        if ( v150 )
        {
          if ( v150 < 0x1000 )
          {
            v151 = (char *)operator new(v150);
          }
          else
          {
            if ( v150 + 39 < v150 )
              goto LABEL_382;
            v152 = operator new(v150 + 39);
            if ( !v152 )
LABEL_296:
              __fastfail(5u);
            v151 = (char *)(((unsigned __int64)v152 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
            *((_QWORD *)v151 - 1) = v152;
          }
          v142 = v209;
        }
        else
        {
          v151 = 0;
        }
        v153 = v147 >> 3;
        *(_QWORD *)&v151[8 * v153] = v142;
        if ( v142 )
          (*(void (__fastcall **)(_QWORD *))(*v142 + 8LL))(v142);
        v154 = *((_QWORD *)&v214 + 1);
        v155 = v151;
        v156 = v214;
        if ( v143 != *((_QWORD *)&v214 + 1) )
        {
          std::_Uninitialized_move<Microsoft::WRL::ComPtr<IStoredKeyDocument> *,std::allocator<Microsoft::WRL::ComPtr<IStoredKeyDocument>>>(
            v214,
            v143,
            v151);
          v155 = &v151[8 * v153 + 8];
          v154 = *((_QWORD *)&v214 + 1);
          v156 = v143;
        }
        std::_Uninitialized_move<Microsoft::WRL::ComPtr<IStoredKeyDocument> *,std::allocator<Microsoft::WRL::ComPtr<IStoredKeyDocument>>>(
          v156,
          v154,
          v155);
        v158 = (char *)v214;
        if ( (_QWORD)v214 )
        {
          v159 = (char *)*((_QWORD *)&v214 + 1);
          if ( (_QWORD)v214 != *((_QWORD *)&v214 + 1) )
          {
            do
            {
              v157 = *(_QWORD *)v158;
              if ( *(_QWORD *)v158 )
              {
                *(_QWORD *)v158 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v157 + 16LL))(v157);
              }
              v158 += 8;
            }
            while ( v158 != v159 );
            v158 = (char *)v214;
          }
          std::allocator<Microsoft::WRL::ComPtr<IStoredLeaseDocument>>::deallocate(v157, v158, (v215 - v158) >> 3);
        }
        *(_QWORD *)&v214 = v151;
        *((_QWORD *)&v214 + 1) = &v151[8 * v148];
        v215 = &v151[v150];
      }
      else
      {
        **((_QWORD **)&v214 + 1) = v209;
        if ( v142 )
          (*(void (__fastcall **)(_QWORD *))(*v142 + 8LL))(v142);
        *((_QWORD *)&v214 + 1) += 8LL;
      }
    }
    else if ( v208 )
    {
      v204 = 0;
      v226 = 0;
      v210 = 0;
      v211 = 0;
      if ( (*(int (__fastcall **)(_QWORD, __int64, _QWORD, int *, struct _RTL_CRITICAL_SECTION **))(*(_QWORD *)v106[23]
                                                                                                  + 88LL))(
             v106[23],
             v208,
             *v107,
             &v204,
             &v226) >= 0 )
      {
        v160 = v204;
        LODWORD(v224) = v204;
        v161 = v226;
        v233 = v226;
        ComArray<ComInterfaceTraits<IStoredLeaseDocument>>::_free(&v210);
        v210 = v161;
        v211 = v160;
        v162 = 0;
        if ( v160 )
        {
          while ( 1 )
          {
            v163 = *((_QWORD *)&v161->DebugInfo + v162);
            v232 = v163;
            if ( v163 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v163 + 8LL))(v163);
            v164 = (__int64 *)*((_QWORD *)&v214 + 1);
            if ( *((char **)&v214 + 1) == v215 )
            {
              v165 = *((_QWORD *)&v214 + 1);
              v166 = (__int64)(*((_QWORD *)&v214 + 1) - v214) >> 3;
              if ( v166 == 0x1FFFFFFFFFFFFFFFLL )
                std::vector<LicenseProxyService::UserRootThreadParam>::_Xlength();
              v167 = (__int64)&v215[-v214] >> 3;
              v168 = v167 >> 1;
              if ( v167 > 0x1FFFFFFFFFFFFFFFLL - (v167 >> 1) )
                goto LABEL_380;
              v218 = v166 + 1;
              v169 = v166 + 1;
              if ( v168 + v167 >= v166 + 1 )
                v169 = v168 + v167;
              if ( v169 > 0x1FFFFFFFFFFFFFFFLL )
LABEL_380:
                std::_Throw_bad_array_new_length();
              v170 = *((_QWORD *)&v214 + 1) - v214;
              v171 = 8 * v169;
              if ( 8 * v169 )
              {
                if ( v171 < 0x1000 )
                {
                  v172 = operator new(v171);
                }
                else
                {
                  if ( v171 + 39 < v171 )
                    goto LABEL_380;
                  v173 = operator new(v171 + 39);
                  if ( !v173 )
                    __fastfail(5u);
                  v172 = (_QWORD *)(((unsigned __int64)v173 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
                  *(v172 - 1) = v173;
                }
              }
              else
              {
                v172 = 0;
              }
              v174 = &v172[v170 >> 3];
              *v174 = 0;
              if ( v174 != &v232 )
              {
                *v174 = v163;
                v163 = 0;
              }
              v175 = *((_QWORD *)&v214 + 1);
              v176 = v172;
              v177 = v214;
              if ( v165 != *((_QWORD *)&v214 + 1) )
              {
                std::_Uninitialized_move<Microsoft::WRL::ComPtr<IStoredKeyDocument> *,std::allocator<Microsoft::WRL::ComPtr<IStoredKeyDocument>>>(
                  v214,
                  v165,
                  v172);
                v176 = (_QWORD *)(v178 + 8);
                v175 = *((_QWORD *)&v214 + 1);
                v177 = v165;
              }
              std::_Uninitialized_move<Microsoft::WRL::ComPtr<IStoredKeyDocument> *,std::allocator<Microsoft::WRL::ComPtr<IStoredKeyDocument>>>(
                v177,
                v175,
                v176);
              std::vector<Microsoft::WRL::ComPtr<IStoredLeaseDocument>>::_Change_array(&v214, v179, v180, v169);
              v160 = (unsigned int)v224;
            }
            else
            {
              **((_QWORD **)&v214 + 1) = 0;
              if ( v164 != &v232 )
              {
                *v164 = v163;
                v163 = 0;
              }
              *((_QWORD *)&v214 + 1) += 8LL;
            }
            if ( v163 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v163 + 16LL))(v163);
            if ( ++v162 >= v160 )
              break;
            v161 = v233;
          }
        }
      }
      ComArray<ComInterfaceTraits<IStoredLeaseDocument>>::_free(&v210);
    }
    if ( v99 )
      (*(void (__fastcall **)(_QWORD *))(*v99 + 16LL))(v99);
    if ( v209 )
      (*(void (__fastcall **)(_QWORD *))(*v209 + 16LL))(v209);
    if ( v208 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v208 + 16LL))(v208);
    v97 = (_lambda_608eb4e91e30957692f8e971acddbc70_ *)((char *)v213 + 16);
  }
  v181 = (__int64)(*((_QWORD *)&v214 + 1) - v214) >> 3;
  v182 = -1;
  if ( v181 > 0xFFFFFFFF )
    LODWORD(v181) = -1;
  ComArray<ComInterfaceTraits<IStoredLeaseDocument>>::ComArray<ComInterfaceTraits<IStoredLeaseDocument>>(
    lpString2,
    (unsigned int)v181);
  v183 = 0;
  for ( k = lpString2[0]; (unsigned int)v183 < (unsigned int)v181; v183 = (unsigned int)(v183 + 1) )
  {
    v185 = 8LL * (unsigned int)v183;
    v186 = *(_QWORD *)(v214 + v185);
    *(_QWORD *)(v214 + v185) = 0;
    *(_QWORD *)&k[(unsigned __int64)v185 / 2] = v186;
  }
  v187 = (__int64)(*((_QWORD *)&v216 + 1) - v216) >> 3;
  if ( v187 <= 0xFFFFFFFF )
  {
    ComArray<ComInterfaceTraits<IStoredKeyDocument>>::ComArray<ComInterfaceTraits<IStoredKeyDocument>>(
      &v210,
      (unsigned int)v187,
      v183);
    v188 = 0;
    v182 = v187;
    if ( (_DWORD)v187 )
      goto LABEL_358;
    v189 = v210;
  }
  else
  {
    ComArray<ComInterfaceTraits<IStoredKeyDocument>>::ComArray<ComInterfaceTraits<IStoredKeyDocument>>(
      &v210,
      0xFFFFFFFFLL,
      v183);
    v188 = 0;
LABEL_358:
    v189 = v210;
    do
    {
      v190 = 8LL * v188;
      v191 = *(struct _RTL_CRITICAL_SECTION_DEBUG **)(v216 + v190);
      *(_QWORD *)(v216 + v190) = 0;
      *(PRTL_CRITICAL_SECTION_DEBUG *)((char *)&v189->DebugInfo + v190) = v191;
      ++v188;
    }
    while ( v188 < v182 );
  }
  v192 = (const WCHAR **)v234;
  v193 = *(_DWORD *)(v234 + 8);
  *(_DWORD *)(v234 + 8) = lpString2[1];
  LODWORD(lpString2[1]) = v193;
  v194 = *v192;
  *v192 = k;
  lpString2[0] = v194;
  v195 = (struct _RTL_CRITICAL_SECTION **)v235;
  v196 = *(_DWORD *)(v235 + 8);
  *(_DWORD *)(v235 + 8) = v211;
  v211 = v196;
  v197 = *v195;
  *v195 = v189;
  v210 = v197;
  ComArray<ComInterfaceTraits<IStoredLicenseDocument>>::_free(&v210);
  ComArray<ComInterfaceTraits<IStoredLeaseDocument>>::_free(lpString2);
  if ( v206[0] )
  {
    std::_Destroy_range<std::allocator<std::pair<Microsoft::WRL::ComPtr<IKeyLicenseCallbackWaiter>,Microsoft::WRL::ComPtr<IStoredKeyDocument>>>>(v206[0]);
    std::_Deallocate<16>(v206[0], (v207 - v206[0]) & 0xFFFFFFFFFFFFFFF0uLL);
    *(_OWORD *)v206 = 0;
    v207 = 0;
  }
  std::vector<Microsoft::WRL::ComPtr<IStoredKeyDocument>>::_Tidy(&v216);
  return std::vector<Microsoft::WRL::ComPtr<IStoredLeaseDocument>>::~vector<Microsoft::WRL::ComPtr<IStoredLeaseDocument>>(&v214);
}

```

## disassembly

```asm
0x180020c40  push    rbx
0x180020c42  push    rsi
0x180020c43  push    rdi
0x180020c44  push    r12
0x180020c46  push    r13
0x180020c48  push    r14
0x180020c4a  push    r15
0x180020c4c  sub     rsp, 1A0h
0x180020c53  mov     rax, cs:__security_cookie
0x180020c5a  xor     rax, rsp
0x180020c5d  mov     [rsp+1D8h+var_48], rax
0x180020c65  mov     [rsp+1D8h+var_1A4], r8b
0x180020c6a  mov     [rsp+1D8h+var_120], rdx
0x180020c72  mov     rdi, rcx
0x180020c75  mov     [rsp+1D8h+var_168], rcx
0x180020c7a  mov     [rsp+1D8h+var_C8], rcx
0x180020c82  mov     [rsp+1D8h+var_C0], rdx
0x180020c8a  mov     [rsp+1D8h+var_A0], r9
0x180020c92  mov     rax, [rsp+1D8h+arg_20]
0x180020c9a  mov     [rsp+1D8h+var_A8], rax
0x180020ca2  xor     r14d, r14d
0x180020ca5  mov     eax, r14d
0x180020ca8  mov     dword ptr [rsp+1D8h+var_F8], eax
0x180020caf  mov     dword ptr [rsp+1D8h+var_188], eax
0x180020cb3  xorps   xmm0, xmm0
0x180020cb6  movdqu  [rsp+1D8h+var_158], xmm0
0x180020cbf  mov     [rsp+1D8h+var_148], r14
0x180020cc7  movdqu  [rsp+1D8h+var_140], xmm0
0x180020cd0  mov     [rsp+1D8h+var_130], r14
0x180020cd8  movdqu  xmmword ptr [rsp+1D8h+var_1A0], xmm0
0x180020cde  mov     [rsp+1D8h+var_190], r14
0x180020ce3  lea     rbx, [rcx+40h]
0x180020ce7  mov     [rsp+1D8h+var_D0], rbx
0x180020cef  mov     rcx, rbx; lpCriticalSection
0x180020cf2  call    cs:__imp_EnterCriticalSection
0x180020cf8  mov     [rsp+1D8h+var_B0], rbx
0x180020d00  mov     [rsp+1D8h+var_178], r14
0x180020d05  mov     [rsp+1D8h+var_170], r14d
0x180020d0a  lea     rcx, [rdi+20h]
0x180020d0e  mov     rax, [rcx]
0x180020d11  lea     rdx, [rsp+1D8h+var_178]
0x180020d16  mov     rax, [rax+18h]
0x180020d1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020d1f  mov     eax, r14d
0x180020d22  mov     [rsp+1D8h+var_1A8], eax
0x180020d26  cmp     [rsp+1D8h+var_170], r14d
0x180020d2b  jbe     loc_18002199D
0x180020d31  nop     dword ptr [rax+00h]
0x180020d35  nop     word ptr [rax+rax+00000000h]
0x180020d40  mov     [rsp+1D8h+Src], r14
0x180020d48  lea     r13, ds:0[rax*8]
0x180020d50  mov     rax, [rsp+1D8h+var_178]
0x180020d55  mov     rcx, [rax+r13]
0x180020d59  mov     rax, [rcx]
0x180020d5c  mov     [rsp+1D8h+Src], r14
0x180020d64  lea     rdx, [rsp+1D8h+Src]
0x180020d6c  mov     rax, [rax+68h]
0x180020d70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020d75  mov     rsi, r14
0x180020d78  mov     [rsp+1D8h+var_E8], r14
0x180020d80  mov     r12, [rsp+1D8h+Src]
0x180020d88  xorps   xmm0, xmm0
0x180020d8b  movups  xmmword ptr [rsp+1D8h+lpString2], xmm0
0x180020d93  mov     qword ptr [rsp+1D8h+cchCount2], r14
0x180020d9b  mov     [rsp+1D8h+var_60], r14
0x180020da3  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180020daa  nop     word ptr [rax+rax+00h]
0x180020db0  inc     rbx
0x180020db3  cmp     word ptr [r12+rbx*2], 0
0x180020db9  jnz     short loc_180020DB0
0x180020dbb  mov     rax, 7FFFFFFFFFFFFFFEh
0x180020dc5  cmp     rbx, rax
0x180020dc8  ja      loc_18002269F
0x180020dce  cmp     rbx, 7
0x180020dd2  ja      short loc_180020E0C
0x180020dd4  mov     qword ptr [rsp+1D8h+cchCount2], rbx
0x180020ddc  mov     [rsp+1D8h+var_60], 7
0x180020de8  add     rbx, rbx
0x180020deb  mov     r8, rbx; Size
0x180020dee  mov     rdx, r12; Src
0x180020df1  lea     rcx, [rsp+1D8h+lpString2]; void *
0x180020df9  call    memcpy_0
0x180020dfe  mov     word ptr [rsp+rbx+1D8h+lpString2], r14w
0x180020e07  jmp     loc_180020EC0
0x180020e0c  mov     r15, rbx
0x180020e0f  or      r15, 7
0x180020e13  cmp     r15, rax
0x180020e16  jbe     short loc_180020E57
0x180020e18  mov     r15, rax
0x180020e1b  mov     rcx, 0FFFFFFFFFFFFFFFEh; Size
0x180020e22  cmp     rcx, 1000h
0x180020e29  jb      short loc_180020E85
0x180020e2b  lea     rax, [rcx+27h]
0x180020e2f  cmp     rax, rcx
0x180020e32  jbe     loc_180022699
0x180020e38  mov     rcx, rax; Size
0x180020e3b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180020e40  test    rax, rax
0x180020e43  jz      loc_180021980
0x180020e49  lea     rdi, [rax+27h]
0x180020e4d  and     rdi, 0FFFFFFFFFFFFFFE0h
0x180020e51  mov     [rdi-8], rax
0x180020e55  jmp     short loc_180020E8D
0x180020e57  cmp     r15, 0Ah
0x180020e5b  mov     eax, 0Ah
0x180020e60  cmovb   r15, rax
0x180020e64  lea     rcx, [r15+1]
0x180020e68  mov     rax, 7FFFFFFFFFFFFFFFh
0x180020e72  cmp     rcx, rax
0x180020e75  ja      loc_180022699
0x180020e7b  add     rcx, rcx
0x180020e7e  jnz     short loc_180020E22
0x180020e80  mov     rdi, r14
0x180020e83  jmp     short loc_180020E8D
0x180020e85  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180020e8a  mov     rdi, rax
0x180020e8d  mov     [rsp+1D8h+lpString2], rdi
0x180020e95  mov     qword ptr [rsp+1D8h+cchCount2], rbx
0x180020e9d  mov     [rsp+1D8h+var_60], r15
0x180020ea5  add     rbx, rbx
0x180020ea8  mov     r8, rbx; Size
0x180020eab  mov     rdx, r12; Src
0x180020eae  mov     rcx, rdi; void *
0x180020eb1  call    memcpy_0
0x180020eb6  mov     [rbx+rdi], r14w
0x180020ebb  mov     rdi, [rsp+1D8h+var_168]
0x180020ec0  mov     rbx, [rdi+88h]
0x180020ec7  nop     word ptr [rax+rax+00000000h]
0x180020ed0  mov     rax, [rdi+90h]
0x180020ed7  cmp     rbx, rax
0x180020eda  jz      loc_180020F6C
0x180020ee0  mov     r12, qword ptr [rsp+1D8h+cchCount2]
0x180020ee8  mov     r15, [rbx+10h]
0x180020eec  cmp     [rsp+1D8h+var_60], 7
0x180020ef5  mov     rdi, [rsp+1D8h+lpString2]
0x180020efd  ja      short loc_180020F07
0x180020eff  lea     rdi, [rsp+1D8h+lpString2]
0x180020f07  call    IsCompareContentIdPresent
0x180020f0c  mov     rcx, [rbx+18h]
0x180020f10  test    al, al
0x180020f12  mov     rax, rbx
0x180020f15  jz      short loc_180020F34
0x180020f17  cmp     rcx, 7
0x180020f1b  jbe     short loc_180020F20
0x180020f1d  mov     rax, [rbx]
0x180020f20  mov     r9d, r12d
0x180020f23  mov     edx, r15d
0x180020f26  mov     r8, rdi
0x180020f29  mov     rcx, rax
0x180020f2c  call    cs:__imp_CompareContentId
0x180020f32  jmp     short loc_180020F5A
0x180020f34  cmp     rcx, 7
0x180020f38  jbe     short loc_180020F3D
0x180020f3a  mov     rax, [rbx]
0x180020f3d  mov     r9d, r12d; cchCount2
0x180020f40  mov     edx, r15d; cchCount1
0x180020f43  mov     [rsp+1D8h+bIgnoreCase], 1; bIgnoreCase
0x180020f4b  mov     r8, rdi; lpString2
0x180020f4e  mov     rcx, rax; lpString1
0x180020f51  call    cs:__imp_CompareStringOrdinal
0x180020f57  sub     eax, 2
0x180020f5a  mov     rdi, [rsp+1D8h+var_168]
0x180020f5f  test    eax, eax
0x180020f61  jz      short loc_180020F6F
0x180020f63  add     rbx, 30h ; '0'
0x180020f67  jmp     loc_180020ED0
0x180020f6c  mov     rbx, rax
0x180020f6f  mov     rdx, [rsp+1D8h+var_60]
0x180020f77  cmp     rdx, 7
0x180020f7b  jbe     short loc_180020FB7
0x180020f7d  lea     rdx, ds:2[rdx*2]
0x180020f85  mov     rcx, [rsp+1D8h+lpString2]
0x180020f8d  cmp     rdx, 1000h
0x180020f94  jb      short loc_180020FB2
0x180020f96  mov     rax, [rcx-8]
0x180020f9a  sub     rcx, rax
0x180020f9d  sub     rcx, 8
0x180020fa1  cmp     rcx, 1Fh
0x180020fa5  ja      loc_180021980
0x180020fab  add     rdx, 27h ; '''; struct std::nothrow_t *
0x180020faf  mov     rcx, rax; void *
0x180020fb2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180020fb7  mov     qword ptr [rsp+1D8h+cchCount2], r14
0x180020fbf  mov     [rsp+1D8h+var_60], 7
0x180020fcb  mov     word ptr [rsp+1D8h+lpString2], r14w
0x180020fd4  cmp     rbx, [rdi+90h]
0x180020fdb  jz      loc_180021648
0x180020fe1  mov     rdi, [rbx+28h]
0x180020fe5  mov     [rsp+1D8h+var_98], rdi
0x180020fed  test    rdi, rdi
0x180020ff0  jz      short loc_180021002
0x180020ff2  mov     rax, [rdi]
0x180020ff5  mov     rcx, rdi
0x180020ff8  mov     rax, [rax+8]
0x180020ffc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021001  nop
0x180021002  mov     [rsp+1D8h+var_180], r14
0x180021007  mov     [rsp+1D8h+var_160], r14
0x18002100c  mov     r12d, dword ptr [rsp+1D8h+var_F8]
0x180021014  or      r12d, 1
0x180021018  mov     rbx, r14
0x18002101b  mov     [rsp+1D8h+var_128], rbx
0x180021023  or      r12d, 4
0x180021027  mov     dword ptr [rsp+1D8h+var_188], r12d
0x18002102c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180021033  mov     ecx, 40h ; '@'; unsigned __int64
0x180021038  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002103d  mov     rsi, rax
0x180021040  mov     rcx, rax
0x180021043  mov     [rsp+1D8h+var_F0], rax
0x18002104b  mov     [rsp+1D8h+var_F8], rax
0x180021053  mov     r15, r14
0x180021056  test    rax, rax
0x180021059  jz      loc_180021145
0x18002105f  mov     [rsp+1D8h+lpString2], rax
0x180021067  lea     rax, ??_7IRootsCallback@@6B@; const IRootsCallback::`vftable'
0x18002106e  mov     [rcx], rax
0x180021071  lea     rax, ??_7IKeyLicenseCallbackWaiter@@6B@; const IKeyLicenseCallbackWaiter::`vftable'
0x180021078  mov     [rcx+8], rax
0x18002107c  mov     dword ptr [rcx+14h], 1
0x180021083  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIKeyLicenseCallback@@UIKeyLicenseCallbackWaiter@@@WRL@Microsoft@@6BIKeyLicenseCallback@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IKeyLicenseCallback,IKeyLicenseCallbackWaiter>::`vftable'{for `IKeyLicenseCallback'}
0x18002108a  mov     [rcx], rax
0x18002108d  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIKeyLicenseCallback@@UIKeyLicenseCallbackWaiter@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIKeyLicenseCallbackWaiter@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IKeyLicenseCallback,IKeyLicenseCallbackWaiter>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IKeyLicenseCallbackWaiter>'}
0x180021094  mov     [rcx+8], rax
0x180021098  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18002109f  test    rcx, rcx
0x1800210a2  jz      short loc_1800210B1
0x1800210a4  mov     rax, [rcx]
0x1800210a7  mov     rax, [rax+8]
0x1800210ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800210b0  nop
0x1800210b1  lea     rax, ??_7LicenseCallback@@6BIKeyLicenseCallback@@@; const LicenseCallback::`vftable'{for `IKeyLicenseCallback'}
0x1800210b8  mov     [rsi], rax
0x1800210bb  lea     rax, ??_7LicenseCallback@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIKeyLicenseCallbackWaiter@@@Details@WRL@Microsoft@@@; const LicenseCallback::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IKeyLicenseCallbackWaiter>'}
0x1800210c2  mov     [rsi+8], rax
0x1800210c6  mov     [rsi+20h], r14
0x1800210ca  lea     rax, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x1800210d1  mov     [rsi+18h], rax
0x1800210d5  mov     dword ptr [rsi+28h], 8000FFFFh
0x1800210dc  mov     [rsi+30h], r14
0x1800210e0  mov     [rsi+38h], r14
0x1800210e4  xor     r9d, r9d; lpName
0x1800210e7  xor     r8d, r8d; bInitialState
0x1800210ea  xor     edx, edx; bManualReset
0x1800210ec  xor     ecx, ecx; lpEventAttributes
0x1800210ee  call    cs:__imp_CreateEventW
0x1800210f4  mov     r15, rax
0x1800210f7  mov     rcx, [rsi+20h]
0x1800210fb  cmp     rax, rcx
0x1800210fe  jz      short loc_180021121
0x180021100  test    rcx, rcx
0x180021103  jz      short loc_18002111D
0x180021105  mov     rcx, [rsi+18h]
0x180021109  mov     rax, [rcx]
0x18002110c  lea     rcx, [rsi+18h]
0x180021110  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021115  test    al, al
0x180021117  jz      loc_180022608
0x18002111d  mov     [rsi+20h], r15
0x180021121  mov     rcx, [rsp+1D8h]; this
0x180021129  cmp     qword ptr [rsi+20h], 0
0x18002112e  jz      loc_180022623
0x180021134  mov     rbx, rsi
0x180021137  mov     [rsp+1D8h+var_128], rbx
0x18002113f  mov     rcx, r14; Block
0x180021142  mov     r15, rsi
0x180021145  test    rcx, rcx
0x180021148  jz      short loc_18002114F
0x18002114a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002114f  and     r12d, 0FFFFFFFBh
0x180021153  or      r12d, 2
0x180021157  mov     dword ptr [rsp+1D8h+var_188], r12d
0x18002115c  test    r15, r15
0x18002115f  jz      loc_18002266B
0x180021165  mov     rax, [rbx]
0x180021168  mov     rbx, [rax]
0x18002116b  mov     rcx, [rsp+1D8h+var_160]
0x180021170  test    rcx, rcx
0x180021173  jz      short loc_180021187
0x180021175  mov     [rsp+1D8h+var_160], r14
0x18002117a  mov     rdx, [rcx]
0x18002117d  mov     rax, [rdx+10h]
0x180021181  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021186  nop
0x180021187  lea     r8, [rsp+1D8h+var_160]
0x18002118c  lea     rdx, _GUID_85f3fad7_61e8_4612_9f09_2d1af999aa40
0x180021193  mov     rcx, r15
0x180021196  mov     rax, rbx
0x180021199  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002119e  nop
0x18002119f  mov     rcx, [rsp+1D8h]; this
0x1800211a7  test    eax, eax
0x1800211a9  js      loc_180022656
0x1800211af  and     r12d, 0FFFFFFFDh
0x1800211b3  mov     dword ptr [rsp+1D8h+var_188], r12d
0x1800211b8  mov     rax, [r15]
0x1800211bb  mov     rcx, r15
0x1800211be  mov     rax, [rax+10h]
0x1800211c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800211c7  nop
  ... truncated ...
```
