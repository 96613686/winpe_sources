# Windows::Telemetry::UpdateManager::Scan::Stop(wil::basic_zstring_view<wchar_t>,ProviderType,wil::basic_zstring_view<wchar_t>,bool,bool,SystemInterface::Telemetry::CorrelationVector &,wchar_t const *,unsigned __int64)

- ea: `0x1402731cc`
- end: `0x140274ef2`
- name: `?Stop@Scan@UpdateManager@Telemetry@Windows@@QEAAXV?$basic_zstring_view@_W@wil@@W4ProviderType@@0_N2AEAVCorrelationVector@3SystemInterface@@PEB_W_K@Z`
- size: `7462`
- prototype: ``
- caller_count: `2`
- callee_count: `26`
- tags: `installer_update`

## callers

- `0x14028f560`
- `0x14028f620`

## callees

- `0x140001f74`
- `0x1400080d4`
- `0x1400085a0`
- `0x14000883c`
- `0x140008ccc`
- `0x140008f2c`
- `0x140009384`
- `0x1400097a0`
- `0x140021474`
- `0x140024de0`
- `0x14002a258`
- `0x14002a7d8`
- `0x14002b5f0`
- `0x14002cc08`
- `0x14002cd1c`
- `0x140043284`
- `0x140044f20`
- `0x140045404`
- `0x140045688`
- `0x14012d7d8`
- `0x1402369c4`
- `0x140268cbc`
- `0x1402731cc`
- `0x140379070`
- `0x14037b4b0`
- `0x140380b50`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140273844`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140273f5d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14027464a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140274c9d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140273844`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140273f5d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14027464a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140274c9d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1402736d1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140273e2e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140274543`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1402747f7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140274b70`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1402736d1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140273e2e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140274543`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1402747f7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140274b70`

## pseudocode

```c
// Hidden C++ exception states: #wind=43
__int64 __fastcall Windows::Telemetry::UpdateManager::Scan::Stop(
        __int64 a1,
        __int64 *a2,
        enum ProviderType a3,
        __int64 *a4,
        char a5,
        char a6,
        __int64 a7,
        __int64 a8,
        __int64 a9)
{
  __int64 v13; // rax
  __int64 v14; // r8
  __int64 v15; // r14
  int v16; // eax
  int *v17; // r14
  const struct _tlgProvider_t *v18; // rax
  int v19; // r15d
  _QWORD *v20; // rax
  _QWORD *v21; // rax
  _QWORD *v22; // rax
  _QWORD *v23; // rax
  __int64 v24; // rax
  __int64 v25; // rcx
  _QWORD *v26; // rax
  int v27; // eax
  int v28; // eax
  const wchar_t *v29; // rdi
  __int128 *v30; // rax
  volatile signed __int32 *v31; // rdi
  volatile signed __int32 *v32; // rdi
  __int64 v33; // rdx
  volatile signed __int32 *v34; // rdi
  volatile signed __int32 *v35; // rdi
  const struct _tlgProvider_t *v36; // rax
  int v37; // r14d
  _QWORD *v38; // rax
  _QWORD *v39; // rax
  _QWORD *v40; // rax
  _QWORD *v41; // rax
  __int64 v42; // rax
  __int64 v43; // rcx
  _QWORD *v44; // rax
  int v45; // eax
  int v46; // eax
  const wchar_t *v47; // rdi
  __int128 *v48; // rax
  __int64 v49; // r8
  volatile signed __int32 *v50; // rdi
  volatile signed __int32 *v51; // rdi
  __int64 v52; // rdx
  volatile signed __int32 *v53; // rdi
  char IsEnabled; // al
  int *v55; // rdx
  int v56; // ecx
  int *v57; // rbx
  const struct _tlgProvider_t *v58; // rax
  int v59; // r14d
  _QWORD *v60; // rax
  _QWORD *v61; // rax
  _QWORD *v62; // rax
  _QWORD *v63; // rax
  __int64 v64; // rax
  __int64 v65; // rcx
  _QWORD *v66; // rax
  int v67; // eax
  int v68; // eax
  const wchar_t *v69; // rdi
  volatile signed __int32 *v70; // rdi
  volatile signed __int32 *v71; // rdi
  __int64 v72; // rdx
  int v73; // r14d
  const struct _tlgProvider_t *v74; // rax
  _QWORD *System; // rax
  _QWORD *v76; // rax
  __int64 v77; // rax
  const OLECHAR *v78; // r12
  __int64 v79; // rax
  const CHAR *v80; // r15
  __int64 v81; // rax
  __int64 v82; // rcx
  _QWORD *v83; // rax
  int v84; // eax
  int v85; // eax
  const wchar_t *v86; // rdi
  const OLECHAR *v87; // r13
  __int64 v88; // r8
  __int64 v89; // rax
  int v90; // eax
  __int64 v91; // rax
  int v92; // eax
  const OLECHAR *v93; // rax
  __int64 v94; // rcx
  int v95; // ecx
  __int64 v96; // rax
  __int64 v97; // r14
  volatile signed __int32 *v98; // rdi
  volatile signed __int32 *v99; // rdi
  __int64 v100; // rdx
  volatile signed __int32 *v101; // rdi
  volatile signed __int32 *v102; // rdi
  int *v104; // r14
  const struct _tlgProvider_t *v105; // rax
  int v106; // ebx
  _QWORD *v107; // rax
  __int64 v108; // rax
  __int64 v109; // rcx
  _QWORD *v110; // rax
  unsigned int v111; // eax
  const struct _tlgProvider_t *v112; // rax
  int v113; // ebx
  _QWORD *v114; // rax
  __int64 v115; // rax
  __int64 v116; // rcx
  _QWORD *v117; // rax
  int v118; // eax
  int v119; // eax
  const wchar_t *v120; // rdi
  __int64 v121; // r8
  volatile signed __int32 *v122; // rdi
  volatile signed __int32 *v123; // rdi
  __int64 v124; // rax
  __int64 v125; // r8
  __int64 v126; // r12
  __int64 v127; // r15
  int v128; // eax
  int *v129; // r15
  _DWORD **v130; // r14
  const struct _tlgProvider_t *v131; // rax
  int v132; // r14d
  _QWORD *v133; // rax
  __int64 v134; // rax
  __int64 v135; // rcx
  _QWORD *v136; // rax
  int v137; // eax
  int v138; // eax
  const wchar_t *v139; // rdi
  __int128 *v140; // rax
  volatile signed __int32 *v141; // rdi
  volatile signed __int32 *v142; // rdi
  const struct _tlgProvider_t *v143; // rax
  int v144; // r14d
  _QWORD *v145; // rax
  __int64 v146; // rax
  __int64 v147; // rcx
  _QWORD *v148; // rax
  int v149; // eax
  int v150; // eax
  const wchar_t *v151; // rdi
  __int128 *v152; // rax
  _DWORD *v153; // r8
  volatile signed __int32 *v154; // rdi
  volatile signed __int32 *v155; // rdi
  __int64 v156; // rdx
  char v157; // [rsp+100h] [rbp-80h] BYREF
  _BYTE v158[3]; // [rsp+101h] [rbp-7Fh] BYREF
  int v159; // [rsp+104h] [rbp-7Ch] BYREF
  __int64 v160; // [rsp+108h] [rbp-78h] BYREF
  int v161; // [rsp+110h] [rbp-70h] BYREF
  int v162; // [rsp+114h] [rbp-6Ch] BYREF
  int v163; // [rsp+118h] [rbp-68h] BYREF
  int v164; // [rsp+11Ch] [rbp-64h] BYREF
  __int64 v165; // [rsp+120h] [rbp-60h] BYREF
  __int64 v166; // [rsp+128h] [rbp-58h] BYREF
  __int64 v167; // [rsp+130h] [rbp-50h] BYREF
  __int64 v168; // [rsp+138h] [rbp-48h] BYREF
  __int64 v169; // [rsp+140h] [rbp-40h] BYREF
  __int64 v170; // [rsp+148h] [rbp-38h] BYREF
  __int64 v171; // [rsp+150h] [rbp-30h] BYREF
  __int64 v172; // [rsp+158h] [rbp-28h] BYREF
  __int64 v173; // [rsp+160h] [rbp-20h] BYREF
  __int64 v174; // [rsp+168h] [rbp-18h] BYREF
  __int64 v175; // [rsp+170h] [rbp-10h] BYREF
  __int64 v176; // [rsp+178h] [rbp-8h] BYREF
  __int64 v177; // [rsp+180h] [rbp+0h] BYREF
  __int64 v178; // [rsp+188h] [rbp+8h] BYREF
  __int64 v179; // [rsp+190h] [rbp+10h] BYREF
  __int64 v180; // [rsp+198h] [rbp+18h] BYREF
  _BYTE v181[8]; // [rsp+1A0h] [rbp+20h] BYREF
  volatile signed __int32 *v182; // [rsp+1A8h] [rbp+28h]
  _BYTE v183[8]; // [rsp+1B0h] [rbp+30h] BYREF
  volatile signed __int32 *v184; // [rsp+1B8h] [rbp+38h]
  __int64 v185; // [rsp+1C0h] [rbp+40h] BYREF
  __int64 v186; // [rsp+1C8h] [rbp+48h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+1D0h] [rbp+50h] BYREF
  __int64 v188; // [rsp+1E8h] [rbp+68h] BYREF
  _BYTE v189[8]; // [rsp+1F0h] [rbp+70h] BYREF
  volatile signed __int32 *v190; // [rsp+1F8h] [rbp+78h]
  _BYTE v191[8]; // [rsp+200h] [rbp+80h] BYREF
  volatile signed __int32 *v192; // [rsp+208h] [rbp+88h]
  _BYTE v193[32]; // [rsp+210h] [rbp+90h] BYREF
  _BYTE v194[32]; // [rsp+230h] [rbp+B0h] BYREF
  __int128 v195; // [rsp+250h] [rbp+D0h] BYREF
  __int128 v196; // [rsp+260h] [rbp+E0h]
  struct _EVENT_DATA_DESCRIPTOR v197; // [rsp+270h] [rbp+F0h] BYREF
  __int64 *v198; // [rsp+290h] [rbp+110h]
  __int64 v199; // [rsp+298h] [rbp+118h]
  int *v200; // [rsp+2A0h] [rbp+120h]
  __int64 v201; // [rsp+2A8h] [rbp+128h]
  __int64 *v202; // [rsp+2B0h] [rbp+130h]
  __int64 v203; // [rsp+2B8h] [rbp+138h]
  const OLECHAR *v204; // [rsp+2C0h] [rbp+140h]
  int v205; // [rsp+2C8h] [rbp+148h]
  int v206; // [rsp+2CCh] [rbp+14Ch]
  char *v207; // [rsp+2D0h] [rbp+150h]
  __int64 v208; // [rsp+2D8h] [rbp+158h]
  _BYTE *v209; // [rsp+2E0h] [rbp+160h]
  __int64 v210; // [rsp+2E8h] [rbp+168h]
  const wchar_t *v211; // [rsp+2F0h] [rbp+170h]
  int v212; // [rsp+2F8h] [rbp+178h]
  int v213; // [rsp+2FCh] [rbp+17Ch]
  __int64 *v214; // [rsp+300h] [rbp+180h]
  __int64 v215; // [rsp+308h] [rbp+188h]
  const OLECHAR *v216; // [rsp+310h] [rbp+190h]
  int v217; // [rsp+318h] [rbp+198h]
  int v218; // [rsp+31Ch] [rbp+19Ch]
  const CHAR *v219; // [rsp+320h] [rbp+1A0h]
  int v220; // [rsp+328h] [rbp+1A8h]
  int v221; // [rsp+32Ch] [rbp+1ACh]
  const OLECHAR *v222; // [rsp+330h] [rbp+1B0h]
  int v223; // [rsp+338h] [rbp+1B8h]
  int v224; // [rsp+33Ch] [rbp+1BCh]
  const char *v225; // [rsp+340h] [rbp+1C0h]
  __int64 v226; // [rsp+348h] [rbp+1C8h]

  v186 = (__int64)a4;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UOvNext_46833319>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_UOvNext_46833319>::GetImpl'::`2'::impl)
    || !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections>::GetImpl'::`2'::impl) )
  {
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UOvNext_46833319>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_UOvNext_46833319>::GetImpl'::`2'::impl) )
    {
      IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections>::GetImpl'::`2'::impl);
      v55 = *(int **)(a1 + 272);
      v56 = v55[18];
      if ( IsEnabled )
      {
        if ( v56 >= 0 || (v57 = v55 + 20, v56 != v55[22]) || v55 == (int *)-80LL )
        {
          v160 = 0;
          wil::ActivityBase<Windows::Telemetry::BaseCore,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
            a1,
            &v160);
          v73 = 2;
          **(_DWORD **)(a1 + 272) = 2;
          if ( v160 )
            ReleaseSRWLockExclusive((PSRWLOCK)v160);
          v74 = Windows::Telemetry::Base::Provider();
          v167 = (__int64)v74;
          if ( *(_DWORD *)v74 > 5u
            && (*((_QWORD *)v74 + 2) & 0x400000000000LL) != 0
            && (*((_QWORD *)v74 + 3) & 0x400000000000LL) == *((_QWORD *)v74 + 3) )
          {
            System = (_QWORD *)SystemInterface::Providers::GetSystem(v189);
            v76 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*System + 40LL))(*System, v191);
            v77 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v76 + 440LL))(*v76, v194);
            v78 = (const OLECHAR *)v77;
            if ( *(_QWORD *)(v77 + 24) > 7u )
              v78 = *(const OLECHAR **)v77;
            v79 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)a7 + 8LL))(a7, v193);
            v80 = (const CHAR *)v79;
            if ( *(_QWORD *)(v79 + 24) > 0xFu )
              v80 = *(const CHAR **)v79;
            v165 = a9;
            v81 = SystemInterface::Providers::GetSystem(v181);
            v82 = *(_QWORD *)v81 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v81 + 8LL) + 4LL);
            v83 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v82 + 96LL))(v82, v183);
            v84 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v83 + 8LL))(*v83);
            if ( v84 )
            {
              v85 = v84 - 1;
              if ( v85 )
              {
                if ( v85 != 1 )
                {
                  std::logic_error::logic_error((std::logic_error *)pExceptionObject, "Invalid connectivity level");
                  throw (std::logic_error *)pExceptionObject;
                }
                v86 = L"Internet";
              }
              else
              {
                v86 = L"local only";
              }
            }
            else
            {
              v86 = L"none";
            }
            v158[0] = a6;
            v157 = a5;
            v87 = (const OLECHAR *)*a2;
            LODWORD(v160) = GetCurrentThreadId();
            v88 = *(_QWORD *)(a1 + 272);
            v159 = *(_DWORD *)(v88 + 72);
            v166 = 0x1000000;
            v225 = "1507.2603.28012.0";
            v226 = 18;
            if ( v78 )
            {
              v89 = -1;
              do
                ++v89;
              while ( v78[v89] );
              v90 = 2 * v89 + 2;
            }
            else
            {
              v78 = &psz;
              v90 = 2;
            }
            v222 = v78;
            v223 = v90;
            v224 = 0;
            if ( v80 )
            {
              v91 = -1;
              do
                ++v91;
              while ( v80[v91] );
              v92 = v91 + 1;
            }
            else
            {
              v80 = &pszCabPath;
              v92 = 1;
            }
            v219 = v80;
            v220 = v92;
            v221 = 0;
            v93 = (const OLECHAR *)a8;
            if ( a8 )
            {
              v94 = -1;
              do
                ++v94;
              while ( *(_WORD *)(a8 + 2 * v94) );
              v95 = 2 * v94 + 2;
            }
            else
            {
              v93 = &psz;
              v95 = 2;
            }
            v216 = v93;
            v217 = v95;
            v218 = 0;
            v214 = &v165;
            v215 = 8;
            v96 = -1;
            do
              ++v96;
            while ( v86[v96] );
            v211 = v86;
            v212 = 2 * v96 + 2;
            v213 = 0;
            v209 = v158;
            v210 = 1;
            v207 = &v157;
            v208 = 1;
            if ( v87 )
            {
              v97 = -1;
              do
                ++v97;
              while ( v87[v97] );
              v73 = 2 * v97 + 2;
            }
            else
            {
              v87 = &psz;
            }
            v204 = v87;
            v205 = v73;
            v206 = 0;
            v202 = &v160;
            v203 = 4;
            v200 = &v159;
            v201 = 4;
            v198 = &v166;
            v199 = 8;
            tlgWriteTransfer_EventWriteTransfer(v167, (int)&byte_14049F501, v88 + 8, 0, 0xEu, &v197);
            v98 = v184;
            if ( v184 )
            {
              if ( _InterlockedExchangeAdd(v184 + 2, 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v98)(v98);
                if ( _InterlockedExchangeAdd(v98 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v98 + 8LL))(v98);
              }
            }
            v99 = v182;
            if ( v182 )
            {
              if ( _InterlockedExchangeAdd(v182 + 2, 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v99)(v99);
                if ( _InterlockedExchangeAdd(v99 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v99 + 8LL))(v99);
              }
            }
            std::string::_Tidy_deallocate(v193);
            std::wstring::~wstring(v194, v100);
            v101 = v192;
            if ( v192 )
            {
              if ( !_InterlockedDecrement(v192 + 2) )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v101)(v101);
                if ( !_InterlockedDecrement(v101 + 3) )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v101 + 8LL))(v101);
              }
            }
            v102 = v190;
            if ( v190 )
            {
              if ( !_InterlockedDecrement(v190 + 2) )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v102)(v102);
                if ( !_InterlockedDecrement(v102 + 3) )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v102 + 8LL))(v102);
              }
            }
          }
        }
        else
        {
          wil::ActivityBase<Windows::Telemetry::BaseCore,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(a1);
          v58 = Windows::Telemetry::Base::Provider();
          v59 = (int)v58;
          if ( *(_DWORD *)v58 > 5u
            && (*((_QWORD *)v58 + 2) & 0x400000000000LL) != 0
            && (*((_QWORD *)v58 + 3) & 0x400000000000LL) == *((_QWORD *)v58 + 3) )
          {
            v165 = (__int64)"1507.2603.28012.0";
            v60 = (_QWORD *)SystemInterface::Providers::GetSystem(v189);
            v61 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v60 + 40LL))(*v60, v191);
            v62 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v61 + 440LL))(*v61, v194);
            if ( v62[3] > 7u )
              v62 = (_QWORD *)*v62;
            v166 = (__int64)v62;
            v63 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)a7 + 8LL))(a7, v193);
            if ( v63[3] > 0xFu )
              v63 = (_QWORD *)*v63;
            v167 = (__int64)v63;
            v171 = a8;
            v168 = a9;
            v64 = SystemInterface::Providers::GetSystem(v181);
            v65 = *(_QWORD *)v64 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v64 + 8LL) + 4LL);
            v66 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v65 + 96LL))(v65, v183);
            v67 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v66 + 8LL))(*v66);
            if ( v67 )
            {
              v68 = v67 - 1;
              if ( v68 )
              {
                if ( v68 != 1 )
                {
                  std::logic_error::logic_error((std::logic_error *)pExceptionObject, "Invalid connectivity level");
                  throw (std::logic_error *)pExceptionObject;
                }
                v69 = L"Internet";
              }
              else
              {
                v69 = L"local only";
              }
            }
            else
            {
              v69 = L"none";
            }
            v169 = (__int64)v69;
            v158[0] = a6;
            v157 = a5;
            v170 = *a2;
            v172 = *((_QWORD *)v57 + 15);
            v173 = *((_QWORD *)v57 + 14);
            LODWORD(v160) = v57[26];
            v174 = *((_QWORD *)v57 + 12);
            v175 = *((_QWORD *)v57 + 11);
            v159 = v57[20];
            v176 = *((_QWORD *)v57 + 9);
            v164 = v57[8];
            v177 = *((_QWORD *)v57 + 3);
            v163 = *v57;
            v178 = *((_QWORD *)v57 + 16);
            v162 = v57[16];
            v179 = *((_QWORD *)v57 + 7);
            v161 = v57[2];
            v180 = 0x1000000;
            v185 = 0x1000000;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>>(
              v59,
              (int)&dword_14049F8BC,
              *(_QWORD *)(a1 + 272) + 8,
              (__int64)&v185,
              (__int64)&v180,
              (__int64)&v161,
              (__int64)&v179,
              (__int64)&v162,
              (__int64)&v178,
              (__int64)&v163,
              (__int64)&v177,
              (__int64)&v164,
              (__int64)&v176,
              (__int64)&v159,
              (__int64)&v175,
              (__int64)&v174,
              (__int64)&v160,
              (__int64)&v173,
              (__int64)&v172,
              (__int64)&v170,
              (__int64)&v157,
              (__int64)v158,
              (__int64)&v169,
              (__int64)&v168,
              (__int64)&v171,
              (__int64)&v167,
              (__int64)&v166,
              (__int64)&v165);
            v70 = v184;
            if ( v184 )
            {
              if ( _InterlockedExchangeAdd(v184 + 2, 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v70)(v70);
                if ( _InterlockedExchangeAdd(v70 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v70 + 8LL))(v70);
              }
            }
            v71 = v182;
            if ( v182 )
            {
              if ( _InterlockedExchangeAdd(v182 + 2, 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v71)(v71);
                if ( _InterlockedExchangeAdd(v71 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v71 + 8LL))(v71);
              }
            }
            std::string::_Tidy_deallocate(v193);
            std::wstring::~wstring(v194, v72);
            std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v191);
            std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v189);
          }
        }
        return wil::ActivityBase<Windows::WU::Telemetry::WuProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(a1);
      }
      if ( v56 >= 0 || (v104 = v55 + 20, v56 != v55[22]) || v55 == (int *)-80LL )
      {
        v160 = 0;
        wil::ActivityBase<Windows::Telemetry::BaseCore,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
          a1,
          &v160);
        **(_DWORD **)(a1 + 272) = 2;
        if ( v160 )
          ReleaseSRWLockExclusive((PSRWLOCK)v160);
        v112 = Windows::Telemetry::Base::Provider();
        v113 = (int)v112;
        if ( *(_DWORD *)v112 <= 5u
          || (*((_QWORD *)v112 + 2) & 0x400000000000LL) == 0
          || (*((_QWORD *)v112 + 3) & 0x400000000000LL) != *((_QWORD *)v112 + 3) )
        {
          return wil::ActivityBase<Windows::WU::Telemetry::WuProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(a1);
        }
        v165 = (__int64)"1507.2603.28012.0";
        v114 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)a7 + 8LL))(a7, v193);
        if ( v114[3] > 0xFu )
          v114 = (_QWORD *)*v114;
        v166 = (__int64)v114;
        v167 = a8;
        v171 = a9;
        v115 = SystemInterface::Providers::GetSystem(v181);
        v116 = *(_QWORD *)v115 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v115 + 8LL) + 4LL);
        v117 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v116 + 96LL))(v116, v183);
        v118 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v117 + 8LL))(*v117);
        if ( v118 )
        {
          v119 = v118 - 1;
          if ( v119 )
          {
            if ( v119 != 1 )
            {
              std::logic_error::logic_error((std::logic_error *)pExceptionObject, "Invalid connectivity level");
              throw (std::logic_error *)pExceptionObject;
            }
            v120 = L"Internet";
          }
          else
          {
            v120 = L"local only";
          }
        }
        else
        {
          v120 = L"none";
        }
        v168 = (__int64)v120;
        v158[0] = a6;
        v157 = a5;
        v169 = *a2;
        LODWORD(v160) = GetCurrentThreadId();
        v121 = *(_QWORD *)(a1 + 272);
        v159 = *(_DWORD *)(v121 + 72);
        v170 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v113,
          (int)&byte_14049F73F,
          v121 + 8,
          (__int64)&v170,
          (__int64)&v159,
          (__int64)&v160,
          (__int64)&v169,
          (__int64)&v157,
          (__int64)v158,
          (__int64)&v168,
          (__int64)&v171,
          (__int64)&v167,
          (__int64)&v166,
          (__int64)&v165);
        v122 = v184;
        if ( v184 )
        {
          if ( _InterlockedExchangeAdd(v184 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v122)(v122);
            if ( _InterlockedExchangeAdd(v122 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v122 + 8LL))(v122);
          }
        }
        v123 = v182;
        if ( v182 )
        {
          if ( _InterlockedExchangeAdd(v182 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v123)(v123);
            if ( _InterlockedExchangeAdd(v123 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v123 + 8LL))(v123);
          }
        }
      }
      else
      {
        wil::ActivityBase<Windows::Telemetry::BaseCore,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(a1);
        v105 = Windows::Telemetry::Base::Provider();
        v106 = (int)v105;
        if ( *(_DWORD *)v105 <= 5u
          || (*((_QWORD *)v105 + 2) & 0x400000000000LL) == 0
          || (*((_QWORD *)v105 + 3) & 0x400000000000LL) != *((_QWORD *)v105 + 3) )
        {
          return wil::ActivityBase<Windows::WU::Telemetry::WuProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(a1);
        }
        v165 = (__int64)"1507.2603.28012.0";
        v107 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)a7 + 8LL))(a7, v193);
        if ( v107[3] > 0xFu )
          v107 = (_QWORD *)*v107;
        v166 = (__int64)v107;
        v167 = a8;
        v171 = a9;
        v108 = SystemInterface::Providers::GetSystem(v181);
        v109 = *(_QWORD *)v108 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v108 + 8LL) + 4LL);
        v110 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v109 + 96LL))(v109, v183);
        v111 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v110 + 8LL))(*v110);
        v168 = SystemInterface::to_wstring(v111);
        v158[0] = a6;
        v157 = a5;
        v169 = *a2;
        v170 = *((_QWORD *)v104 + 15);
        v172 = *((_QWORD *)v104 + 14);
        LODWORD(v160) = v104[26];
        v173 = *((_QWORD *)v104 + 12);
        v174 = *((_QWORD *)v104 + 11);
        v159 = v104[20];
        v175 = *((_QWORD *)v104 + 9);
        v164 = v104[8];
        v176 = *((_QWORD *)v104 + 3);
        v163 = *v104;
        v177 = *((_QWORD *)v104 + 16);
        v162 = v104[16];
        v178 = *((_QWORD *)v104 + 7);
        v161 = v104[2];
        v179 = 0x1000000;
        v180 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v106,
          (int)&byte_14049F5B9,
          *(_QWORD *)(a1 + 272) + 8,
          (__int64)&v180,
          (__int64)&v179,
          (__int64)&v161,
          (__int64)&v178,
          (__int64)&v162,
          (__int64)&v177,
          (__int64)&v163,
          (__int64)&v176,
          (__int64)&v164,
          (__int64)&v175,
          (__int64)&v159,
          (__int64)&v174,
          (__int64)&v173,
          (__int64)&v160,
          (__int64)&v172,
          (__int64)&v170,
          (__int64)&v169,
          (__int64)&v157,
          (__int64)v158,
          (__int64)&v168,
          (__int64)&v171,
          (__int64)&v167,
          (__int64)&v166,
          (__int64)&v165);
        std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v183);
        std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v181);
      }
      std::string::_Tidy_deallocate(v193);
      return wil::ActivityBase<Windows::WU::Telemetry::WuProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(a1);
    }
    v124 = to_wstring(a3);
    v195 = 0;
    v196 = 0;
    v125 = -1;
    do
      ++v125;
    while ( *(_WORD *)(v124 + 2 * v125) );
    std::wstring::_Construct<1,wchar_t const *>(&v195, v124, v125);
    v126 = a1 + 272;
    v127 = *(_QWORD *)(a1 + 272);
    v128 = *(_DWORD *)(v127 + 72);
    if ( v128 < 0 && (v129 = (int *)(v127 + 80), v128 == v129[2]) )
    {
      v130 = (_DWORD **)(a1 + 272);
      if ( v129 )
      {
        v160 = 0;
        wil::ActivityBase<Windows::Telemetry::BaseCore,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
          a1,
          &v160);
        **(_DWORD **)v126 = 2;
        if ( v160 )
          ReleaseSRWLockExclusive((PSRWLOCK)v160);
        v131 = Windows::Telemetry::Base::Provider();
        v132 = (int)v131;
        if ( *(_DWORD *)v131 <= 5u
          || (*((_QWORD *)v131 + 2) & 0x400000000000LL) == 0
          || (*((_QWORD *)v131 + 3) & 0x400000000000LL) != *((_QWORD *)v131 + 3) )
        {
          goto LABEL_238;
        }
        v165 = (__int64)"1507.2603.28012.0";
        v133 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)a7 + 8LL))(a7, v193);
        if ( v133[3] > 0xFu )
          v133 = (_QWORD *)*v133;
        v166 = (__int64)v133;
        v167 = a8;
        v171 = a9;
        v134 = SystemInterface::Providers::GetSystem(v181);
        v135 = *(_QWORD *)v134 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v134 + 8LL) + 4LL);
        v136 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v135 + 96LL))(v135, v183);
        v137 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v136 + 8LL))(*v136);
        if ( v137 )
        {
          v138 = v137 - 1;
          if ( v138 )
          {
            if ( v138 != 1 )
            {
              std::logic_error::logic_error((std::logic_error *)pExceptionObject, "Invalid connectivity level");
              throw (std::logic_error *)pExceptionObject;
            }
            v139 = L"Internet";
          }
          else
          {
            v139 = L"local only";
          }
        }
        else
        {
          v139 = L"none";
        }
        v168 = (__int64)v139;
        v158[0] = a6;
        v157 = a5;
        v169 = *(_QWORD *)v186;
        v140 = &v195;
        if ( *((_QWORD *)&v196 + 1) > 7u )
          v140 = (__int128 *)v195;
        v170 = (__int64)v140;
        v172 = *a2;
        v173 = *((_QWORD *)v129 + 15);
        v174 = *((_QWORD *)v129 + 14);
        LODWORD(v160) = v129[26];
        v175 = *((_QWORD *)v129 + 12);
        v176 = *((_QWORD *)v129 + 11);
        v159 = v129[20];
        v177 = *((_QWORD *)v129 + 9);
        v164 = v129[8];
        v178 = *((_QWORD *)v129 + 3);
        v163 = *v129;
        v179 = *((_QWORD *)v129 + 16);
        v162 = v129[16];
        v180 = *((_QWORD *)v129 + 7);
        v161 = v129[2];
        v185 = 0x1000000;
        v188 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v132,
          (int)&unk_14049FCD0,
          *(_DWORD *)v126 + 8,
          (__int64)&v188,
          (__int64)&v185,
          (__int64)&v161,
          (__int64)&v180,
          (__int64)&v162,
          (__int64)&v179,
          (__int64)&v163,
          (__int64)&v178,
          (__int64)&v164,
          (__int64)&v177,
          (__int64)&v159,
          (__int64)&v176,
          (__int64)&v175,
          (__int64)&v160,
          (__int64)&v174,
          (__int64)&v173,
          (__int64)&v172,
          (__int64)&v170,
          (__int64)&v169,
          (__int64)&v157,
          (__int64)v158,
          (__int64)&v168,
          (__int64)&v171,
          (__int64)&v167,
          (__int64)&v166,
          (__int64)&v165);
        v141 = v184;
        if ( v184 )
        {
          if ( _InterlockedExchangeAdd(v184 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v141)(v141);
            if ( _InterlockedExchangeAdd(v141 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v141 + 8LL))(v141);
          }
        }
        v142 = v182;
        if ( v182 )
        {
          if ( _InterlockedExchangeAdd(v182 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v142)(v142);
            if ( _InterlockedExchangeAdd(v142 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v142 + 8LL))(v142);
          }
        }
        goto LABEL_237;
      }
    }
    else
    {
      v130 = (_DWORD **)(a1 + 272);
    }
    v160 = 0;
    wil::ActivityBase<Windows::Telemetry::BaseCore,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      a1,
      &v160);
    **v130 = 2;
    if ( v160 )
      ReleaseSRWLockExclusive((PSRWLOCK)v160);
    v143 = Windows::Telemetry::Base::Provider();
    v144 = (int)v143;
    if ( *(_DWORD *)v143 <= 5u
      || (*((_QWORD *)v143 + 2) & 0x400000000000LL) == 0
      || (*((_QWORD *)v143 + 3) & 0x400000000000LL) != *((_QWORD *)v143 + 3) )
    {
      goto LABEL_238;
    }
    v165 = (__int64)"1507.2603.28012.0";
    v145 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)a7 + 8LL))(a7, v193);
    if ( v145[3] > 0xFu )
      v145 = (_QWORD *)*v145;
    v166 = (__int64)v145;
    v167 = a8;
    v171 = a9;
    v146 = SystemInterface::Providers::GetSystem(v181);
    v147 = *(_QWORD *)v146 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v146 + 8LL) + 4LL);
    v148 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v147 + 96LL))(v147, v183);
    v149 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v148 + 8LL))(*v148);
    if ( v149 )
    {
      v150 = v149 - 1;
      if ( v150 )
      {
        if ( v150 != 1 )
        {
          std::logic_error::logic_error((std::logic_error *)pExceptionObject, "Invalid connectivity level");
          throw (std::logic_error *)pExceptionObject;
        }
        v151 = L"Internet";
      }
      else
      {
        v151 = L"local only";
      }
    }
    else
    {
      v151 = L"none";
    }
    v168 = (__int64)v151;
    v158[0] = a6;
    v157 = a5;
    v169 = *(_QWORD *)v186;
    v152 = &v195;
    if ( *((_QWORD *)&v196 + 1) > 7u )
      v152 = (__int128 *)v195;
    v170 = (__int64)v152;
    v172 = *a2;
    LODWORD(v160) = GetCurrentThreadId();
    v153 = *(_DWORD **)v126;
    v159 = *(_DWORD *)(*(_QWORD *)v126 + 72LL);
    v173 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v144,
      (int)&word_14049F7EE,
      (_DWORD)v153 + 8,
      (__int64)&v173,
      (__int64)&v159,
      (__int64)&v160,
      (__int64)&v172,
      (__int64)&v170,
      (__int64)&v169,
      (__int64)&v157,
      (__int64)v158,
      (__int64)&v168,
      (__int64)&v171,
      (__int64)&v167,
      (__int64)&v166,
      (__int64)&v165);
    v154 = v184;
    if ( v184 )
    {
      if ( _InterlockedExchangeAdd(v184 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v154)(v154);
        if ( _InterlockedExchangeAdd(v154 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v154 + 8LL))(v154);
      }
    }
    v155 = v182;
    if ( v182 )
    {
      if ( _InterlockedExchangeAdd(v182 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v155)(v155);
        if ( _InterlockedExchangeAdd(v155 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v155 + 8LL))(v155);
      }
    }
LABEL_237:
    std::string::_Tidy_deallocate(v193);
    goto LABEL_238;
  }
  v13 = to_wstring(a3);
  v195 = 0;
  v196 = 0;
  v14 = -1;
  do
    ++v14;
  while ( *(_WORD *)(v13 + 2 * v14) );
  std::wstring::_Construct<1,wchar_t const *>(&v195, v13, v14);
  v15 = *(_QWORD *)(a1 + 272);
  v16 = *(_DWORD *)(v15 + 72);
  if ( v16 >= 0 || (v17 = (int *)(v15 + 80), v16 != v17[2]) || !v17 )
  {
    v160 = 0;
    wil::ActivityBase<Windows::Telemetry::BaseCore,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      a1,
      &v160);
    **(_DWORD **)(a1 + 272) = 2;
    if ( v160 )
      ReleaseSRWLockExclusive((PSRWLOCK)v160);
    v36 = Windows::Telemetry::Base::Provider();
    v37 = (int)v36;
    if ( *(_DWORD *)v36 <= 5u
      || (*((_QWORD *)v36 + 2) & 0x400000000000LL) == 0
      || (*((_QWORD *)v36 + 3) & 0x400000000000LL) != *((_QWORD *)v36 + 3) )
    {
      goto LABEL_238;
    }
    v165 = (__int64)"1507.2603.28012.0";
    v38 = (_QWORD *)SystemInterface::Providers::GetSystem(v189);
    v39 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v38 + 40LL))(*v38, v191);
    v40 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v39 + 440LL))(*v39, v194);
    if ( v40[3] > 7u )
      v40 = (_QWORD *)*v40;
    v166 = (__int64)v40;
    v41 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)a7 + 8LL))(a7, v193);
    if ( v41[3] > 0xFu )
      v41 = (_QWORD *)*v41;
    v167 = (__int64)v41;
    v171 = a8;
    v168 = a9;
    v42 = SystemInterface::Providers::GetSystem(v181);
    v43 = *(_QWORD *)v42 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v42 + 8LL) + 4LL);
    v44 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v43 + 96LL))(v43, v183);
    v45 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v44 + 8LL))(*v44);
    if ( v45 )
    {
      v46 = v45 - 1;
      if ( v46 )
      {
        if ( v46 != 1 )
        {
          std::logic_error::logic_error((std::logic_error *)pExceptionObject, "Invalid connectivity level");
          throw (std::logic_error *)pExceptionObject;
        }
        v47 = L"Internet";
      }
      else
      {
        v47 = L"local only";
      }
    }
    else
    {
      v47 = L"none";
    }
    v169 = (__int64)v47;
    v158[0] = a6;
    v157 = a5;
    v170 = *a4;
    v48 = &v195;
    if ( *((_QWORD *)&v196 + 1) > 7u )
      v48 = (__int128 *)v195;
    v172 = (__int64)v48;
    v173 = *a2;
    LODWORD(v160) = GetCurrentThreadId();
    v49 = *(_QWORD *)(a1 + 272);
    v159 = *(_DWORD *)(v49 + 72);
    v174 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>>(
      v37,
      (int)&byte_14049FBF9,
      v49 + 8,
      (__int64)&v174,
      (__int64)&v159,
      (__int64)&v160,
      (__int64)&v173,
      (__int64)&v172,
      (__int64)&v170,
      (__int64)&v157,
      (__int64)v158,
      (__int64)&v169,
      (__int64)&v168,
      (__int64)&v171,
      (__int64)&v167,
      (__int64)&v166,
      (__int64)&v165);
    v50 = v184;
    if ( v184 )
    {
      if ( _InterlockedExchangeAdd(v184 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v50)(v50);
        if ( _InterlockedExchangeAdd(v50 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v50 + 8LL))(v50);
      }
    }
    v51 = v182;
    if ( v182 )
    {
      if ( _InterlockedExchangeAdd(v182 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v51)(v51);
        if ( _InterlockedExchangeAdd(v51 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v51 + 8LL))(v51);
      }
    }
    std::string::_Tidy_deallocate(v193);
    std::wstring::~wstring(v194, v52);
    v53 = v192;
    if ( v192 )
    {
      if ( !_InterlockedDecrement(v192 + 2) )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v53)(v53);
        if ( !_InterlockedDecrement(v53 + 3) )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v53 + 8LL))(v53);
      }
    }
    v35 = v190;
    goto LABEL_66;
  }
  wil::ActivityBase<Windows::Telemetry::BaseCore,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(a1);
  v18 = Windows::Telemetry::Base::Provider();
  v19 = (int)v18;
  if ( *(_DWORD *)v18 > 5u
    && (*((_QWORD *)v18 + 2) & 0x400000000000LL) != 0
    && (*((_QWORD *)v18 + 3) & 0x400000000000LL) == *((_QWORD *)v18 + 3) )
  {
    v186 = (__int64)"1507.2603.28012.0";
    v20 = (_QWORD *)SystemInterface::Providers::GetSystem(v183);
    v21 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v20 + 40LL))(*v20, v181);
    v22 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v21 + 440LL))(*v21, v193);
    if ( v22[3] > 7u )
      v22 = (_QWORD *)*v22;
    v188 = (__int64)v22;
    v23 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)a7 + 8LL))(a7, v194);
    if ( v23[3] > 0xFu )
      v23 = (_QWORD *)*v23;
    v185 = (__int64)v23;
    v180 = a8;
    v179 = a9;
    v24 = SystemInterface::Providers::GetSystem(v191);
    v25 = *(_QWORD *)v24 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v24 + 8LL) + 4LL);
    v26 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v25 + 96LL))(v25, v189);
    v27 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v26 + 8LL))(*v26);
    if ( v27 )
    {
      v28 = v27 - 1;
      if ( v28 )
      {
        if ( v28 != 1 )
        {
          std::logic_error::logic_error((std::logic_error *)pExceptionObject, "Invalid connectivity level");
          throw (std::logic_error *)pExceptionObject;
        }
        v29 = L"Internet";
      }
      else
      {
        v29 = L"local only";
      }
    }
    else
    {
      v29 = L"none";
    }
    v178 = (__int64)v29;
    v157 = a6;
    v158[0] = a5;
    v177 = *a4;
    v30 = &v195;
    if ( *((_QWORD *)&v196 + 1) > 7u )
      v30 = (__int128 *)v195;
    v176 = (__int64)v30;
    v175 = *a2;
    v174 = *((_QWORD *)v17 + 15);
    v173 = *((_QWORD *)v17 + 14);
    v161 = v17[26];
    v172 = *((_QWORD *)v17 + 12);
    v170 = *((_QWORD *)v17 + 11);
    v162 = v17[20];
    v169 = *((_QWORD *)v17 + 9);
    v163 = v17[8];
    v168 = *((_QWORD *)v17 + 3);
    v164 = *v17;
    v171 = *((_QWORD *)v17 + 16);
    v159 = v17[16];
    v167 = *((_QWORD *)v17 + 7);
    LODWORD(v160) = v17[2];
    v166 = 0x1000000;
    v165 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>>(
      v19,
      (int)&byte_14049FA4B,
      *(_QWORD *)(a1 + 272) + 8,
      (__int64)&v165,
      (__int64)&v166,
      (__int64)&v160,
      (__int64)&v167,
      (__int64)&v159,
      (__int64)&v171,
      (__int64)&v164,
      (__int64)&v168,
      (__int64)&v163,
      (__int64)&v169,
      (__int64)&v162,
      (__int64)&v170,
      (__int64)&v172,
      (__int64)&v161,
      (__int64)&v173,
      (__int64)&v174,
      (__int64)&v175,
      (__int64)&v176,
      (__int64)&v177,
      (__int64)v158,
      (__int64)&v157,
      (__int64)&v178,
      (__int64)&v179,
      (__int64)&v180,
      (__int64)&v185,
      (__int64)&v188,
      (__int64)&v186);
    v31 = v190;
    if ( v190 )
    {
      if ( _InterlockedExchangeAdd(v190 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v31)(v31);
        if ( _InterlockedExchangeAdd(v31 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v31 + 8LL))(v31);
      }
    }
    v32 = v192;
    if ( v192 )
    {
      if ( _InterlockedExchangeAdd(v192 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v32)(v32);
        if ( _InterlockedExchangeAdd(v32 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v32 + 8LL))(v32);
      }
    }
    std::string::_Tidy_deallocate(v194);
    std::wstring::~wstring(v193, v33);
    v34 = v182;
    if ( v182 )
    {
      if ( !_InterlockedDecrement(v182 + 2) )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v34)(v34);
        if ( !_InterlockedDecrement(v34 + 3) )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v34 + 8LL))(v34);
      }
    }
    v35 = v184;
LABEL_66:
    if ( v35 && !_InterlockedDecrement(v35 + 2) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v35)(v35);
      if ( !_InterlockedDecrement(v35 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v35 + 8LL))(v35);
    }
  }
LABEL_238:
  wil::ActivityBase<Windows::WU::Telemetry::WuProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(a1);
  return std::wstring::~wstring(&v195, v156);
}

```

## disassembly

```asm
0x1402731cc  mov     [rsp-8+arg_8], rbx
0x1402731d1  push    rbp
0x1402731d2  push    rsi
0x1402731d3  push    rdi
0x1402731d4  push    r12
0x1402731d6  push    r13
0x1402731d8  push    r14
0x1402731da  push    r15
0x1402731dc  lea     rbp, [rsp-1E0h]
0x1402731e4  sub     rsp, 360h
0x1402731eb  mov     rax, cs:__security_cookie
0x1402731f2  xor     rax, rsp
0x1402731f5  mov     [rbp+210h+var_40], rax
0x1402731fc  mov     r12, r9
0x1402731ff  mov     [rbp+210h+var_1C8], r9
0x140273203  mov     ebx, r8d
0x140273206  mov     r13, rdx
0x140273209  mov     rsi, rcx
0x14027320c  mov     rdi, [rbp+210h+arg_30]
0x140273213  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_UOvNext_46833319@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_UOvNext_46833319@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UOvNext_46833319> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_UOvNext_46833319>::GetImpl(void)'::`2'::impl
0x14027321a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_UOvNext_46833319@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UOvNext_46833319>::__private_IsEnabled(void)
0x14027321f  xor     r15d, r15d
0x140273222  test    al, al
0x140273224  jz      loc_140273A1A
0x14027322a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections> `wil::Feature<__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections>::GetImpl(void)'::`2'::impl
0x140273231  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections>::__private_IsEnabled(void)
0x140273236  test    al, al
0x140273238  jz      loc_140273A1A
0x14027323e  mov     ecx, ebx; enum ProviderType
0x140273240  call    ?to_wstring@@YA@W4ProviderType@@@Z; to_wstring(ProviderType)
0x140273245  xorps   xmm0, xmm0
0x140273248  movups  [rbp+210h+var_140], xmm0
0x14027324f  xorps   xmm1, xmm1
0x140273252  movdqu  [rbp+210h+var_130], xmm1
0x14027325a  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14027325e  mov     r8, rbx
0x140273261  inc     r8
0x140273264  cmp     [rax+r8*2], r15w
0x140273269  jnz     short loc_140273261
0x14027326b  mov     rdx, rax
0x14027326e  lea     rcx, [rbp+210h+var_140]
0x140273275  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14027327a  nop
0x14027327b  mov     r14, [rsi+110h]
0x140273282  mov     eax, [r14+48h]
0x140273286  test    eax, eax
0x140273288  jns     loc_1402736AB
0x14027328e  add     r14, 50h ; 'P'
0x140273292  cmp     eax, [r14+8]
0x140273296  jnz     loc_1402736AB
0x14027329c  test    r14, r14
0x14027329f  jz      loc_1402736AB
0x1402732a5  mov     rcx, rsi
0x1402732a8  call    ?zInternalStop@?$ActivityBase@VBaseCore@Telemetry@Windows@@$00$0IAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Telemetry::BaseCore,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1402732ad  call    ?Provider@Base@Telemetry@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Telemetry::Base::Provider(void)
0x1402732b2  mov     r15, rax
0x1402732b5  cmp     dword ptr [rax], 5
0x1402732b8  jbe     loc_140273A0C
0x1402732be  mov     rdx, 400000000000h
0x1402732c8  test    [rax+10h], rdx
0x1402732cc  jz      loc_140273A0C
0x1402732d2  mov     rcx, [rax+18h]
0x1402732d6  and     rcx, rdx
0x1402732d9  cmp     rcx, [rax+18h]
0x1402732dd  jnz     loc_140273A0C
0x1402732e3  lea     rax, a15072603280120; "1507.2603.28012.0"
0x1402732ea  mov     [rbp+210h+var_1C8], rax
0x1402732ee  lea     rcx, [rbp+210h+var_1E0]
0x1402732f2  call    ?GetSystem@Providers@SystemInterface@@YA?AV?$shared_ptr@VSystem@Providers@SystemInterface@@@std@@XZ; SystemInterface::Providers::GetSystem(void)
0x1402732f7  nop
0x1402732f8  mov     rcx, [rax]
0x1402732fb  mov     rax, [rcx]
0x1402732fe  lea     rdx, [rbp+210h+var_1F0]
0x140273302  mov     rax, [rax+28h]
0x140273306  call    _guard_dispatch_icall
0x14027330b  nop
0x14027330c  mov     rcx, [rax]
0x14027330f  mov     rax, [rcx]
0x140273312  lea     rdx, [rbp+210h+var_180]
0x140273319  mov     rax, [rax+1B8h]
0x140273320  call    _guard_dispatch_icall
0x140273325  nop
0x140273326  cmp     qword ptr [rax+18h], 7
0x14027332b  jbe     short loc_140273330
0x14027332d  mov     rax, [rax]
0x140273330  mov     [rbp+210h+var_1A8], rax
0x140273334  mov     rax, [rdi]
0x140273337  lea     rdx, [rbp+210h+var_160]
0x14027333e  mov     rcx, rdi
0x140273341  mov     rax, [rax+8]
0x140273345  call    _guard_dispatch_icall
0x14027334a  nop
0x14027334b  cmp     qword ptr [rax+18h], 0Fh
0x140273350  jbe     short loc_140273355
0x140273352  mov     rax, [rax]
0x140273355  mov     [rbp+210h+var_1D0], rax
0x140273359  mov     rax, [rbp+210h+arg_38]
0x140273360  mov     [rbp+210h+var_1F8], rax
0x140273364  mov     rax, [rbp+210h+arg_40]
0x14027336b  mov     [rbp+210h+var_200], rax
0x14027336f  lea     rcx, [rbp+210h+var_190]
0x140273376  call    ?GetSystem@Providers@SystemInterface@@YA?AV?$shared_ptr@VSystem@Providers@SystemInterface@@@std@@XZ; SystemInterface::Providers::GetSystem(void)
0x14027337b  nop
0x14027337c  mov     rdx, [rax]
0x14027337f  mov     rax, [rdx+8]
0x140273383  movsxd  rcx, dword ptr [rax+4]
0x140273387  add     rdx, 8
0x14027338b  add     rcx, rdx
0x14027338e  mov     rax, [rcx]
0x140273391  lea     rdx, [rbp+210h+var_1A0]
0x140273395  mov     rax, [rax+60h]
0x140273399  call    _guard_dispatch_icall
0x14027339e  nop
0x14027339f  mov     rcx, [rax]
0x1402733a2  mov     rax, [rcx]
0x1402733a5  mov     rax, [rax+8]
0x1402733a9  call    _guard_dispatch_icall
0x1402733ae  test    eax, eax
0x1402733b0  jz      short loc_1402733D2
0x1402733b2  sub     eax, 1
0x1402733b5  jz      short loc_1402733C9
0x1402733b7  cmp     eax, 1
0x1402733ba  jnz     loc_140274E2C
0x1402733c0  lea     rdi, aInternet; "Internet"
0x1402733c7  jmp     short loc_1402733D9
0x1402733c9  lea     rdi, aLocalOnly; "local only"
0x1402733d0  jmp     short loc_1402733D9
0x1402733d2  lea     rdi, aNone; "none"
0x1402733d9  mov     [rbp+210h+var_208], rdi
0x1402733dd  mov     al, [rbp+210h+arg_28]
0x1402733e3  mov     byte ptr [rbp+210h+var_290], al
0x1402733e6  mov     al, [rbp+210h+arg_20]
0x1402733ec  mov     byte ptr [rbp+210h+var_290+1], al
0x1402733ef  mov     rax, [r12]
0x1402733f3  mov     [rbp+210h+var_210], rax
0x1402733f7  lea     rax, [rbp+210h+var_140]
0x1402733fe  cmp     qword ptr [rbp+210h+var_130+8], 7
0x140273406  cmova   rax, qword ptr [rbp+210h+var_140]
0x14027340e  mov     [rbp+210h+var_218], rax
0x140273412  mov     rax, [r13+0]
0x140273416  mov     [rbp+210h+var_220], rax
0x14027341a  mov     rax, [r14+78h]
0x14027341e  mov     [rbp+210h+var_228], rax
0x140273422  mov     rax, [r14+70h]
0x140273426  mov     [rbp+210h+var_230], rax
0x14027342a  mov     eax, [r14+68h]
0x14027342e  mov     dword ptr [rbp+210h+var_280], eax
0x140273431  mov     rax, [r14+60h]
0x140273435  mov     [rbp+210h+var_238], rax
0x140273439  mov     rax, [r14+58h]
0x14027343d  mov     [rbp+210h+var_248], rax
0x140273441  mov     eax, [r14+50h]
0x140273445  mov     dword ptr [rbp+210h+var_280+4], eax
0x140273448  mov     rax, [r14+48h]
0x14027344c  mov     [rbp+210h+var_250], rax
0x140273450  mov     eax, [r14+20h]
0x140273454  mov     dword ptr [rbp+210h+var_278], eax
0x140273457  mov     rax, [r14+18h]
0x14027345b  mov     [rbp+210h+var_258], rax
0x14027345f  mov     eax, [r14]
0x140273462  mov     dword ptr [rbp+210h+var_278+4], eax
0x140273465  mov     rax, [r14+80h]
0x14027346c  mov     [rbp+210h+var_240], rax
0x140273470  mov     eax, [r14+40h]
0x140273474  mov     dword ptr [rbp+210h+var_290+4], eax
0x140273477  mov     rax, [r14+38h]
0x14027347b  mov     [rbp+210h+var_260], rax
0x14027347f  mov     eax, [r14+8]
0x140273483  mov     dword ptr [rbp+210h+var_288], eax
0x140273486  mov     eax, 1000000h
0x14027348b  mov     [rbp+210h+var_268], rax
0x14027348f  mov     [rbp+210h+var_270], rax
0x140273493  mov     r8, [rsi+110h]
0x14027349a  add     r8, 8; int
0x14027349e  lea     rax, [rbp+210h+var_1C8]
0x1402734a2  mov     [rsp+390h+var_2A0], rax; __int64
0x1402734aa  lea     rax, [rbp+210h+var_1A8]
0x1402734ae  mov     [rsp+390h+var_2A8], rax; __int64
0x1402734b6  lea     rax, [rbp+210h+var_1D0]
0x1402734ba  mov     [rsp+390h+var_2B0], rax; __int64
0x1402734c2  lea     rax, [rbp+210h+var_1F8]
0x1402734c6  mov     [rsp+390h+var_2B8], rax; __int64
0x1402734ce  lea     rax, [rbp+210h+var_200]
0x1402734d2  mov     [rsp+390h+var_2C0], rax; __int64
0x1402734da  lea     rax, [rbp+210h+var_208]
0x1402734de  mov     [rsp+390h+var_2C8], rax; __int64
0x1402734e6  lea     rax, [rbp+210h+var_290]
0x1402734ea  mov     [rsp+390h+var_2D0], rax; __int64
0x1402734f2  lea     rax, [rbp+210h+var_290+1]
0x1402734f6  mov     [rsp+390h+var_2D8], rax; __int64
0x1402734fe  lea     rax, [rbp+210h+var_210]
0x140273502  mov     [rsp+390h+var_2E0], rax; __int64
0x14027350a  lea     rax, [rbp+210h+var_218]
0x14027350e  mov     [rsp+390h+var_2E8], rax; __int64
0x140273516  lea     rax, [rbp+210h+var_220]
0x14027351a  mov     [rsp+390h+var_2F0], rax; __int64
0x140273522  lea     rax, [rbp+210h+var_228]
0x140273526  mov     [rsp+390h+var_2F8], rax; __int64
0x14027352e  lea     rax, [rbp+210h+var_230]
0x140273532  mov     [rsp+390h+var_300], rax; __int64
0x14027353a  lea     rax, [rbp+210h+var_280]
0x14027353e  mov     [rsp+390h+var_308], rax; __int64
0x140273546  lea     rax, [rbp+210h+var_238]
0x14027354a  mov     [rsp+390h+var_310], rax; __int64
0x140273552  lea     rax, [rbp+210h+var_248]
0x140273556  mov     [rsp+390h+var_318], rax; __int64
0x14027355b  lea     rax, [rbp+210h+var_280+4]
0x14027355f  mov     [rsp+390h+var_320], rax; __int64
0x140273564  lea     rax, [rbp+210h+var_250]
0x140273568  mov     [rsp+390h+var_328], rax; __int64
0x14027356d  lea     rax, [rbp+210h+var_278]
0x140273571  mov     [rsp+390h+var_330], rax; __int64
0x140273576  lea     rax, [rbp+210h+var_258]
0x14027357a  mov     [rsp+390h+var_338], rax; __int64
0x14027357f  lea     rax, [rbp+210h+var_278+4]
0x140273583  mov     [rsp+390h+var_340], rax; __int64
0x140273588  lea     rax, [rbp+210h+var_240]
0x14027358c  mov     [rsp+390h+var_348], rax; __int64
0x140273591  lea     rax, [rbp+210h+var_290+4]
0x140273595  mov     [rsp+390h+var_350], rax; __int64
0x14027359a  lea     rax, [rbp+210h+var_260]
0x14027359e  mov     [rsp+390h+var_358], rax; __int64
0x1402735a3  lea     rax, [rbp+210h+var_288]
0x1402735a7  mov     [rsp+390h+var_360], rax; __int64
0x1402735ac  lea     rax, [rbp+210h+var_268]
0x1402735b0  mov     [rsp+390h+var_368], rax; __int64
0x1402735b5  lea     rax, [rbp+210h+var_270]
0x1402735b9  mov     qword ptr [rsp+390h+var_370], rax; __int64
0x1402735be  lea     rdx, byte_14049FA4B; int
0x1402735c5  mov     rcx, r15; int
0x1402735c8  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@U4@U4@U4@U?$_tlgWrapperByVal@$00@@U5@U4@U1@U4@U3@U4@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456666AEBU?$_tlgWrapperByVal@$00@@7636565@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<char> const &)
0x1402735cd  nop
0x1402735ce  mov     rdi, [rbp+210h+var_198]
0x1402735d2  test    rdi, rdi
0x1402735d5  jz      short loc_14027360B
0x1402735d7  mov     eax, ebx
0x1402735d9  lock xadd [rdi+8], eax
0x1402735de  add     eax, ebx
0x1402735e0  jnz     short loc_14027360B
0x1402735e2  mov     rax, [rdi]
0x1402735e5  mov     rcx, rdi
0x1402735e8  mov     rax, [rax]
0x1402735eb  call    _guard_dispatch_icall
0x1402735f0  mov     eax, ebx
0x1402735f2  lock xadd [rdi+0Ch], eax
0x1402735f7  add     eax, ebx
0x1402735f9  jnz     short loc_14027360B
0x1402735fb  mov     rax, [rdi]
0x1402735fe  mov     rcx, rdi
0x140273601  mov     rax, [rax+8]
0x140273605  call    _guard_dispatch_icall
0x14027360a  nop
0x14027360b  mov     rdi, [rbp+210h+var_188]
0x140273612  test    rdi, rdi
0x140273615  jz      short loc_14027364B
0x140273617  mov     eax, ebx
0x140273619  lock xadd [rdi+8], eax
0x14027361e  add     eax, ebx
0x140273620  jnz     short loc_14027364B
0x140273622  mov     rax, [rdi]
0x140273625  mov     rcx, rdi
0x140273628  mov     rax, [rax]
0x14027362b  call    _guard_dispatch_icall
0x140273630  mov     eax, ebx
0x140273632  lock xadd [rdi+0Ch], eax
0x140273637  add     eax, ebx
0x140273639  jnz     short loc_14027364B
0x14027363b  mov     rax, [rdi]
0x14027363e  mov     rcx, rdi
0x140273641  mov     rax, [rax+8]
0x140273645  call    _guard_dispatch_icall
0x14027364a  nop
0x14027364b  lea     rcx, [rbp+210h+var_160]
0x140273652  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x140273657  nop
0x140273658  lea     rcx, [rbp+210h+var_180]
0x14027365f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140273664  nop
0x140273665  mov     rdi, [rbp+210h+var_1E8]
0x140273669  test    rdi, rdi
0x14027366c  jz      short loc_1402736A2
0x14027366e  mov     eax, ebx
0x140273670  lock xadd [rdi+8], eax
0x140273675  add     eax, ebx
0x140273677  jnz     short loc_1402736A2
0x140273679  mov     rax, [rdi]
0x14027367c  mov     rcx, rdi
0x14027367f  mov     rax, [rax]
0x140273682  call    _guard_dispatch_icall
0x140273687  mov     eax, ebx
0x140273689  lock xadd [rdi+0Ch], eax
0x14027368e  add     eax, ebx
0x140273690  jnz     short loc_1402736A2
0x140273692  mov     rax, [rdi]
0x140273695  mov     rcx, rdi
0x140273698  mov     rax, [rax+8]
0x14027369c  call    _guard_dispatch_icall
0x1402736a1  nop
0x1402736a2  mov     rdi, [rbp+210h+var_1D8]
0x1402736a6  jmp     loc_1402739D4
  ... truncated ...
```
