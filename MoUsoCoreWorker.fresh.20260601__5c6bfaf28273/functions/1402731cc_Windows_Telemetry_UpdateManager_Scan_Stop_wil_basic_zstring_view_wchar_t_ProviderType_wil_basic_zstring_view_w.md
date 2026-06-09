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
  volatile signed __int32 *v33; // rdi
  volatile signed __int32 *v34; // rdi
  const struct _tlgProvider_t *v35; // rax
  int v36; // r14d
  _QWORD *v37; // rax
  _QWORD *v38; // rax
  _QWORD *v39; // rax
  _QWORD *v40; // rax
  __int64 v41; // rax
  __int64 v42; // rcx
  _QWORD *v43; // rax
  int v44; // eax
  int v45; // eax
  const wchar_t *v46; // rdi
  __int128 *v47; // rax
  __int64 v48; // r8
  volatile signed __int32 *v49; // rdi
  volatile signed __int32 *v50; // rdi
  volatile signed __int32 *v51; // rdi
  char IsEnabled; // al
  int *v53; // rdx
  int v54; // ecx
  int *v55; // rbx
  const struct _tlgProvider_t *v56; // rax
  int v57; // r14d
  _QWORD *v58; // rax
  _QWORD *v59; // rax
  _QWORD *v60; // rax
  _QWORD *v61; // rax
  __int64 v62; // rax
  __int64 v63; // rcx
  _QWORD *v64; // rax
  int v65; // eax
  int v66; // eax
  const wchar_t *v67; // rdi
  volatile signed __int32 *v68; // rdi
  volatile signed __int32 *v69; // rdi
  int v70; // r14d
  const struct _tlgProvider_t *v71; // rax
  _QWORD *System; // rax
  _QWORD *v73; // rax
  __int64 v74; // rax
  const OLECHAR *v75; // r12
  __int64 v76; // rax
  const CHAR *v77; // r15
  __int64 v78; // rax
  __int64 v79; // rcx
  _QWORD *v80; // rax
  int v81; // eax
  int v82; // eax
  const wchar_t *v83; // rdi
  const OLECHAR *v84; // r13
  __int64 v85; // r8
  __int64 v86; // rax
  int v87; // eax
  __int64 v88; // rax
  int v89; // eax
  const OLECHAR *v90; // rax
  __int64 v91; // rcx
  int v92; // ecx
  __int64 v93; // rax
  __int64 v94; // r14
  volatile signed __int32 *v95; // rdi
  volatile signed __int32 *v96; // rdi
  volatile signed __int32 *v97; // rdi
  volatile signed __int32 *v98; // rdi
  int *v100; // r14
  const struct _tlgProvider_t *v101; // rax
  int v102; // ebx
  _QWORD *v103; // rax
  __int64 v104; // rax
  __int64 v105; // rcx
  _QWORD *v106; // rax
  unsigned int v107; // eax
  const struct _tlgProvider_t *v108; // rax
  int v109; // ebx
  _QWORD *v110; // rax
  __int64 v111; // rax
  __int64 v112; // rcx
  _QWORD *v113; // rax
  int v114; // eax
  int v115; // eax
  const wchar_t *v116; // rdi
  __int64 v117; // r8
  volatile signed __int32 *v118; // rdi
  volatile signed __int32 *v119; // rdi
  __int64 v120; // rax
  __int64 v121; // r8
  __int64 v122; // r12
  __int64 v123; // r15
  int v124; // eax
  int *v125; // r15
  _DWORD **v126; // r14
  const struct _tlgProvider_t *v127; // rax
  int v128; // r14d
  _QWORD *v129; // rax
  __int64 v130; // rax
  __int64 v131; // rcx
  _QWORD *v132; // rax
  int v133; // eax
  int v134; // eax
  const wchar_t *v135; // rdi
  __int128 *v136; // rax
  volatile signed __int32 *v137; // rdi
  volatile signed __int32 *v138; // rdi
  const struct _tlgProvider_t *v139; // rax
  int v140; // r14d
  _QWORD *v141; // rax
  __int64 v142; // rax
  __int64 v143; // rcx
  _QWORD *v144; // rax
  int v145; // eax
  int v146; // eax
  const wchar_t *v147; // rdi
  __int128 *v148; // rax
  _DWORD *v149; // r8
  volatile signed __int32 *v150; // rdi
  volatile signed __int32 *v151; // rdi
  char v152; // [rsp+100h] [rbp-80h] BYREF
  _BYTE v153[3]; // [rsp+101h] [rbp-7Fh] BYREF
  int v154; // [rsp+104h] [rbp-7Ch] BYREF
  __int64 v155; // [rsp+108h] [rbp-78h] BYREF
  int v156; // [rsp+110h] [rbp-70h] BYREF
  int v157; // [rsp+114h] [rbp-6Ch] BYREF
  int v158; // [rsp+118h] [rbp-68h] BYREF
  int v159; // [rsp+11Ch] [rbp-64h] BYREF
  __int64 v160; // [rsp+120h] [rbp-60h] BYREF
  __int64 v161; // [rsp+128h] [rbp-58h] BYREF
  __int64 v162; // [rsp+130h] [rbp-50h] BYREF
  __int64 v163; // [rsp+138h] [rbp-48h] BYREF
  __int64 v164; // [rsp+140h] [rbp-40h] BYREF
  __int64 v165; // [rsp+148h] [rbp-38h] BYREF
  __int64 v166; // [rsp+150h] [rbp-30h] BYREF
  __int64 v167; // [rsp+158h] [rbp-28h] BYREF
  __int64 v168; // [rsp+160h] [rbp-20h] BYREF
  __int64 v169; // [rsp+168h] [rbp-18h] BYREF
  __int64 v170; // [rsp+170h] [rbp-10h] BYREF
  __int64 v171; // [rsp+178h] [rbp-8h] BYREF
  __int64 v172; // [rsp+180h] [rbp+0h] BYREF
  __int64 v173; // [rsp+188h] [rbp+8h] BYREF
  __int64 v174; // [rsp+190h] [rbp+10h] BYREF
  __int64 v175; // [rsp+198h] [rbp+18h] BYREF
  _BYTE v176[8]; // [rsp+1A0h] [rbp+20h] BYREF
  volatile signed __int32 *v177; // [rsp+1A8h] [rbp+28h]
  _BYTE v178[8]; // [rsp+1B0h] [rbp+30h] BYREF
  volatile signed __int32 *v179; // [rsp+1B8h] [rbp+38h]
  __int64 v180; // [rsp+1C0h] [rbp+40h] BYREF
  __int64 v181; // [rsp+1C8h] [rbp+48h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+1D0h] [rbp+50h] BYREF
  __int64 v183; // [rsp+1E8h] [rbp+68h] BYREF
  _BYTE v184[8]; // [rsp+1F0h] [rbp+70h] BYREF
  volatile signed __int32 *v185; // [rsp+1F8h] [rbp+78h]
  _BYTE v186[8]; // [rsp+200h] [rbp+80h] BYREF
  volatile signed __int32 *v187; // [rsp+208h] [rbp+88h]
  _BYTE v188[32]; // [rsp+210h] [rbp+90h] BYREF
  _BYTE v189[32]; // [rsp+230h] [rbp+B0h] BYREF
  __int128 v190; // [rsp+250h] [rbp+D0h] BYREF
  __int128 v191; // [rsp+260h] [rbp+E0h]
  struct _EVENT_DATA_DESCRIPTOR v192; // [rsp+270h] [rbp+F0h] BYREF
  __int64 *v193; // [rsp+290h] [rbp+110h]
  __int64 v194; // [rsp+298h] [rbp+118h]
  int *v195; // [rsp+2A0h] [rbp+120h]
  __int64 v196; // [rsp+2A8h] [rbp+128h]
  __int64 *v197; // [rsp+2B0h] [rbp+130h]
  __int64 v198; // [rsp+2B8h] [rbp+138h]
  const OLECHAR *v199; // [rsp+2C0h] [rbp+140h]
  int v200; // [rsp+2C8h] [rbp+148h]
  int v201; // [rsp+2CCh] [rbp+14Ch]
  char *v202; // [rsp+2D0h] [rbp+150h]
  __int64 v203; // [rsp+2D8h] [rbp+158h]
  _BYTE *v204; // [rsp+2E0h] [rbp+160h]
  __int64 v205; // [rsp+2E8h] [rbp+168h]
  const wchar_t *v206; // [rsp+2F0h] [rbp+170h]
  int v207; // [rsp+2F8h] [rbp+178h]
  int v208; // [rsp+2FCh] [rbp+17Ch]
  __int64 *v209; // [rsp+300h] [rbp+180h]
  __int64 v210; // [rsp+308h] [rbp+188h]
  const OLECHAR *v211; // [rsp+310h] [rbp+190h]
  int v212; // [rsp+318h] [rbp+198h]
  int v213; // [rsp+31Ch] [rbp+19Ch]
  const CHAR *v214; // [rsp+320h] [rbp+1A0h]
  int v215; // [rsp+328h] [rbp+1A8h]
  int v216; // [rsp+32Ch] [rbp+1ACh]
  const OLECHAR *v217; // [rsp+330h] [rbp+1B0h]
  int v218; // [rsp+338h] [rbp+1B8h]
  int v219; // [rsp+33Ch] [rbp+1BCh]
  const char *v220; // [rsp+340h] [rbp+1C0h]
  __int64 v221; // [rsp+348h] [rbp+1C8h]

  v181 = (__int64)a4;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UOvNext_46833319>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_UOvNext_46833319>::GetImpl'::`2'::impl)
    || !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections>::GetImpl'::`2'::impl) )
  {
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UOvNext_46833319>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_UOvNext_46833319>::GetImpl'::`2'::impl) )
    {
      IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections>::GetImpl'::`2'::impl);
      v53 = *(int **)(a1 + 272);
      v54 = v53[18];
      if ( IsEnabled )
      {
        if ( v54 >= 0 || (v55 = v53 + 20, v54 != v53[22]) || v53 == (int *)-80LL )
        {
          v155 = 0;
          wil::ActivityBase<Windows::Telemetry::BaseCore,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
            a1,
            &v155);
          v70 = 2;
          **(_DWORD **)(a1 + 272) = 2;
          if ( v155 )
            ReleaseSRWLockExclusive((PSRWLOCK)v155);
          v71 = Windows::Telemetry::Base::Provider();
          v162 = (__int64)v71;
          if ( *(_DWORD *)v71 > 5u
            && (*((_QWORD *)v71 + 2) & 0x400000000000LL) != 0
            && (*((_QWORD *)v71 + 3) & 0x400000000000LL) == *((_QWORD *)v71 + 3) )
          {
            System = (_QWORD *)SystemInterface::Providers::GetSystem(v184);
            v73 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*System + 40LL))(*System, v186);
            v74 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v73 + 440LL))(*v73, v189);
            v75 = (const OLECHAR *)v74;
            if ( *(_QWORD *)(v74 + 24) > 7u )
              v75 = *(const OLECHAR **)v74;
            v76 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)a7 + 8LL))(a7, v188);
            v77 = (const CHAR *)v76;
            if ( *(_QWORD *)(v76 + 24) > 0xFu )
              v77 = *(const CHAR **)v76;
            v160 = a9;
            v78 = SystemInterface::Providers::GetSystem(v176);
            v79 = *(_QWORD *)v78 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v78 + 8LL) + 4LL);
            v80 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v79 + 96LL))(v79, v178);
            v81 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v80 + 8LL))(*v80);
            if ( v81 )
            {
              v82 = v81 - 1;
              if ( v82 )
              {
                if ( v82 != 1 )
                {
                  std::logic_error::logic_error((std::logic_error *)pExceptionObject, "Invalid connectivity level");
                  throw (std::logic_error *)pExceptionObject;
                }
                v83 = L"Internet";
              }
              else
              {
                v83 = L"local only";
              }
            }
            else
            {
              v83 = L"none";
            }
            v153[0] = a6;
            v152 = a5;
            v84 = (const OLECHAR *)*a2;
            LODWORD(v155) = GetCurrentThreadId();
            v85 = *(_QWORD *)(a1 + 272);
            v154 = *(_DWORD *)(v85 + 72);
            v161 = 0x1000000;
            v220 = "1507.2603.28012.0";
            v221 = 18;
            if ( v75 )
            {
              v86 = -1;
              do
                ++v86;
              while ( v75[v86] );
              v87 = 2 * v86 + 2;
            }
            else
            {
              v75 = &psz;
              v87 = 2;
            }
            v217 = v75;
            v218 = v87;
            v219 = 0;
            if ( v77 )
            {
              v88 = -1;
              do
                ++v88;
              while ( v77[v88] );
              v89 = v88 + 1;
            }
            else
            {
              v77 = &pszCabPath;
              v89 = 1;
            }
            v214 = v77;
            v215 = v89;
            v216 = 0;
            v90 = (const OLECHAR *)a8;
            if ( a8 )
            {
              v91 = -1;
              do
                ++v91;
              while ( *(_WORD *)(a8 + 2 * v91) );
              v92 = 2 * v91 + 2;
            }
            else
            {
              v90 = &psz;
              v92 = 2;
            }
            v211 = v90;
            v212 = v92;
            v213 = 0;
            v209 = &v160;
            v210 = 8;
            v93 = -1;
            do
              ++v93;
            while ( v83[v93] );
            v206 = v83;
            v207 = 2 * v93 + 2;
            v208 = 0;
            v204 = v153;
            v205 = 1;
            v202 = &v152;
            v203 = 1;
            if ( v84 )
            {
              v94 = -1;
              do
                ++v94;
              while ( v84[v94] );
              v70 = 2 * v94 + 2;
            }
            else
            {
              v84 = &psz;
            }
            v199 = v84;
            v200 = v70;
            v201 = 0;
            v197 = &v155;
            v198 = 4;
            v195 = &v154;
            v196 = 4;
            v193 = &v161;
            v194 = 8;
            tlgWriteTransfer_EventWriteTransfer(v162, (int)&byte_14049F501, v85 + 8, 0, 0xEu, &v192);
            v95 = v179;
            if ( v179 )
            {
              if ( _InterlockedExchangeAdd(v179 + 2, 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v95)(v95);
                if ( _InterlockedExchangeAdd(v95 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v95 + 8LL))(v95);
              }
            }
            v96 = v177;
            if ( v177 )
            {
              if ( _InterlockedExchangeAdd(v177 + 2, 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v96)(v96);
                if ( _InterlockedExchangeAdd(v96 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v96 + 8LL))(v96);
              }
            }
            std::string::_Tidy_deallocate(v188);
            std::wstring::~wstring(v189);
            v97 = v187;
            if ( v187 )
            {
              if ( !_InterlockedDecrement(v187 + 2) )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v97)(v97);
                if ( !_InterlockedDecrement(v97 + 3) )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v97 + 8LL))(v97);
              }
            }
            v98 = v185;
            if ( v185 )
            {
              if ( !_InterlockedDecrement(v185 + 2) )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v98)(v98);
                if ( !_InterlockedDecrement(v98 + 3) )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v98 + 8LL))(v98);
              }
            }
          }
        }
        else
        {
          wil::ActivityBase<Windows::Telemetry::BaseCore,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(a1);
          v56 = Windows::Telemetry::Base::Provider();
          v57 = (int)v56;
          if ( *(_DWORD *)v56 > 5u
            && (*((_QWORD *)v56 + 2) & 0x400000000000LL) != 0
            && (*((_QWORD *)v56 + 3) & 0x400000000000LL) == *((_QWORD *)v56 + 3) )
          {
            v160 = (__int64)"1507.2603.28012.0";
            v58 = (_QWORD *)SystemInterface::Providers::GetSystem(v184);
            v59 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v58 + 40LL))(*v58, v186);
            v60 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v59 + 440LL))(*v59, v189);
            if ( v60[3] > 7u )
              v60 = (_QWORD *)*v60;
            v161 = (__int64)v60;
            v61 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)a7 + 8LL))(a7, v188);
            if ( v61[3] > 0xFu )
              v61 = (_QWORD *)*v61;
            v162 = (__int64)v61;
            v166 = a8;
            v163 = a9;
            v62 = SystemInterface::Providers::GetSystem(v176);
            v63 = *(_QWORD *)v62 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v62 + 8LL) + 4LL);
            v64 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v63 + 96LL))(v63, v178);
            v65 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v64 + 8LL))(*v64);
            if ( v65 )
            {
              v66 = v65 - 1;
              if ( v66 )
              {
                if ( v66 != 1 )
                {
                  std::logic_error::logic_error((std::logic_error *)pExceptionObject, "Invalid connectivity level");
                  throw (std::logic_error *)pExceptionObject;
                }
                v67 = L"Internet";
              }
              else
              {
                v67 = L"local only";
              }
            }
            else
            {
              v67 = L"none";
            }
            v164 = (__int64)v67;
            v153[0] = a6;
            v152 = a5;
            v165 = *a2;
            v167 = *((_QWORD *)v55 + 15);
            v168 = *((_QWORD *)v55 + 14);
            LODWORD(v155) = v55[26];
            v169 = *((_QWORD *)v55 + 12);
            v170 = *((_QWORD *)v55 + 11);
            v154 = v55[20];
            v171 = *((_QWORD *)v55 + 9);
            v159 = v55[8];
            v172 = *((_QWORD *)v55 + 3);
            v158 = *v55;
            v173 = *((_QWORD *)v55 + 16);
            v157 = v55[16];
            v174 = *((_QWORD *)v55 + 7);
            v156 = v55[2];
            v175 = 0x1000000;
            v180 = 0x1000000;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>>(
              v57,
              (int)&dword_14049F8BC,
              *(_QWORD *)(a1 + 272) + 8,
              (__int64)&v180,
              (__int64)&v175,
              (__int64)&v156,
              (__int64)&v174,
              (__int64)&v157,
              (__int64)&v173,
              (__int64)&v158,
              (__int64)&v172,
              (__int64)&v159,
              (__int64)&v171,
              (__int64)&v154,
              (__int64)&v170,
              (__int64)&v169,
              (__int64)&v155,
              (__int64)&v168,
              (__int64)&v167,
              (__int64)&v165,
              (__int64)&v152,
              (__int64)v153,
              (__int64)&v164,
              (__int64)&v163,
              (__int64)&v166,
              (__int64)&v162,
              (__int64)&v161,
              (__int64)&v160);
            v68 = v179;
            if ( v179 )
            {
              if ( _InterlockedExchangeAdd(v179 + 2, 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v68)(v68);
                if ( _InterlockedExchangeAdd(v68 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v68 + 8LL))(v68);
              }
            }
            v69 = v177;
            if ( v177 )
            {
              if ( _InterlockedExchangeAdd(v177 + 2, 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v69)(v69);
                if ( _InterlockedExchangeAdd(v69 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v69 + 8LL))(v69);
              }
            }
            std::string::_Tidy_deallocate(v188);
            std::wstring::~wstring(v189);
            std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v186);
            std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v184);
          }
        }
        return wil::ActivityBase<Windows::WU::Telemetry::WuProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(a1);
      }
      if ( v54 >= 0 || (v100 = v53 + 20, v54 != v53[22]) || v53 == (int *)-80LL )
      {
        v155 = 0;
        wil::ActivityBase<Windows::Telemetry::BaseCore,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
          a1,
          &v155);
        **(_DWORD **)(a1 + 272) = 2;
        if ( v155 )
          ReleaseSRWLockExclusive((PSRWLOCK)v155);
        v108 = Windows::Telemetry::Base::Provider();
        v109 = (int)v108;
        if ( *(_DWORD *)v108 <= 5u
          || (*((_QWORD *)v108 + 2) & 0x400000000000LL) == 0
          || (*((_QWORD *)v108 + 3) & 0x400000000000LL) != *((_QWORD *)v108 + 3) )
        {
          return wil::ActivityBase<Windows::WU::Telemetry::WuProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(a1);
        }
        v160 = (__int64)"1507.2603.28012.0";
        v110 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)a7 + 8LL))(a7, v188);
        if ( v110[3] > 0xFu )
          v110 = (_QWORD *)*v110;
        v161 = (__int64)v110;
        v162 = a8;
        v166 = a9;
        v111 = SystemInterface::Providers::GetSystem(v176);
        v112 = *(_QWORD *)v111 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v111 + 8LL) + 4LL);
        v113 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v112 + 96LL))(v112, v178);
        v114 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v113 + 8LL))(*v113);
        if ( v114 )
        {
          v115 = v114 - 1;
          if ( v115 )
          {
            if ( v115 != 1 )
            {
              std::logic_error::logic_error((std::logic_error *)pExceptionObject, "Invalid connectivity level");
              throw (std::logic_error *)pExceptionObject;
            }
            v116 = L"Internet";
          }
          else
          {
            v116 = L"local only";
          }
        }
        else
        {
          v116 = L"none";
        }
        v163 = (__int64)v116;
        v153[0] = a6;
        v152 = a5;
        v164 = *a2;
        LODWORD(v155) = GetCurrentThreadId();
        v117 = *(_QWORD *)(a1 + 272);
        v154 = *(_DWORD *)(v117 + 72);
        v165 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v109,
          (int)&byte_14049F73F,
          v117 + 8,
          (__int64)&v165,
          (__int64)&v154,
          (__int64)&v155,
          (__int64)&v164,
          (__int64)&v152,
          (__int64)v153,
          (__int64)&v163,
          (__int64)&v166,
          (__int64)&v162,
          (__int64)&v161,
          (__int64)&v160);
        v118 = v179;
        if ( v179 )
        {
          if ( _InterlockedExchangeAdd(v179 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v118)(v118);
            if ( _InterlockedExchangeAdd(v118 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v118 + 8LL))(v118);
          }
        }
        v119 = v177;
        if ( v177 )
        {
          if ( _InterlockedExchangeAdd(v177 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v119)(v119);
            if ( _InterlockedExchangeAdd(v119 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v119 + 8LL))(v119);
          }
        }
      }
      else
      {
        wil::ActivityBase<Windows::Telemetry::BaseCore,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(a1);
        v101 = Windows::Telemetry::Base::Provider();
        v102 = (int)v101;
        if ( *(_DWORD *)v101 <= 5u
          || (*((_QWORD *)v101 + 2) & 0x400000000000LL) == 0
          || (*((_QWORD *)v101 + 3) & 0x400000000000LL) != *((_QWORD *)v101 + 3) )
        {
          return wil::ActivityBase<Windows::WU::Telemetry::WuProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(a1);
        }
        v160 = (__int64)"1507.2603.28012.0";
        v103 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)a7 + 8LL))(a7, v188);
        if ( v103[3] > 0xFu )
          v103 = (_QWORD *)*v103;
        v161 = (__int64)v103;
        v162 = a8;
        v166 = a9;
        v104 = SystemInterface::Providers::GetSystem(v176);
        v105 = *(_QWORD *)v104 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v104 + 8LL) + 4LL);
        v106 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v105 + 96LL))(v105, v178);
        v107 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v106 + 8LL))(*v106);
        v163 = SystemInterface::to_wstring(v107);
        v153[0] = a6;
        v152 = a5;
        v164 = *a2;
        v165 = *((_QWORD *)v100 + 15);
        v167 = *((_QWORD *)v100 + 14);
        LODWORD(v155) = v100[26];
        v168 = *((_QWORD *)v100 + 12);
        v169 = *((_QWORD *)v100 + 11);
        v154 = v100[20];
        v170 = *((_QWORD *)v100 + 9);
        v159 = v100[8];
        v171 = *((_QWORD *)v100 + 3);
        v158 = *v100;
        v172 = *((_QWORD *)v100 + 16);
        v157 = v100[16];
        v173 = *((_QWORD *)v100 + 7);
        v156 = v100[2];
        v174 = 0x1000000;
        v175 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v102,
          (int)&byte_14049F5B9,
          *(_QWORD *)(a1 + 272) + 8,
          (__int64)&v175,
          (__int64)&v174,
          (__int64)&v156,
          (__int64)&v173,
          (__int64)&v157,
          (__int64)&v172,
          (__int64)&v158,
          (__int64)&v171,
          (__int64)&v159,
          (__int64)&v170,
          (__int64)&v154,
          (__int64)&v169,
          (__int64)&v168,
          (__int64)&v155,
          (__int64)&v167,
          (__int64)&v165,
          (__int64)&v164,
          (__int64)&v152,
          (__int64)v153,
          (__int64)&v163,
          (__int64)&v166,
          (__int64)&v162,
          (__int64)&v161,
          (__int64)&v160);
        std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v178);
        std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v176);
      }
      std::string::_Tidy_deallocate(v188);
      return wil::ActivityBase<Windows::WU::Telemetry::WuProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(a1);
    }
    v120 = to_wstring(a3);
    v190 = 0;
    v191 = 0;
    v121 = -1;
    do
      ++v121;
    while ( *(_WORD *)(v120 + 2 * v121) );
    std::wstring::_Construct<1,wchar_t const *>(&v190, v120, v121);
    v122 = a1 + 272;
    v123 = *(_QWORD *)(a1 + 272);
    v124 = *(_DWORD *)(v123 + 72);
    if ( v124 < 0 && (v125 = (int *)(v123 + 80), v124 == v125[2]) )
    {
      v126 = (_DWORD **)(a1 + 272);
      if ( v125 )
      {
        v155 = 0;
        wil::ActivityBase<Windows::Telemetry::BaseCore,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
          a1,
          &v155);
        **(_DWORD **)v122 = 2;
        if ( v155 )
          ReleaseSRWLockExclusive((PSRWLOCK)v155);
        v127 = Windows::Telemetry::Base::Provider();
        v128 = (int)v127;
        if ( *(_DWORD *)v127 <= 5u
          || (*((_QWORD *)v127 + 2) & 0x400000000000LL) == 0
          || (*((_QWORD *)v127 + 3) & 0x400000000000LL) != *((_QWORD *)v127 + 3) )
        {
          goto LABEL_238;
        }
        v160 = (__int64)"1507.2603.28012.0";
        v129 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)a7 + 8LL))(a7, v188);
        if ( v129[3] > 0xFu )
          v129 = (_QWORD *)*v129;
        v161 = (__int64)v129;
        v162 = a8;
        v166 = a9;
        v130 = SystemInterface::Providers::GetSystem(v176);
        v131 = *(_QWORD *)v130 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v130 + 8LL) + 4LL);
        v132 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v131 + 96LL))(v131, v178);
        v133 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v132 + 8LL))(*v132);
        if ( v133 )
        {
          v134 = v133 - 1;
          if ( v134 )
          {
            if ( v134 != 1 )
            {
              std::logic_error::logic_error((std::logic_error *)pExceptionObject, "Invalid connectivity level");
              throw (std::logic_error *)pExceptionObject;
            }
            v135 = L"Internet";
          }
          else
          {
            v135 = L"local only";
          }
        }
        else
        {
          v135 = L"none";
        }
        v163 = (__int64)v135;
        v153[0] = a6;
        v152 = a5;
        v164 = *(_QWORD *)v181;
        v136 = &v190;
        if ( *((_QWORD *)&v191 + 1) > 7u )
          v136 = (__int128 *)v190;
        v165 = (__int64)v136;
        v167 = *a2;
        v168 = *((_QWORD *)v125 + 15);
        v169 = *((_QWORD *)v125 + 14);
        LODWORD(v155) = v125[26];
        v170 = *((_QWORD *)v125 + 12);
        v171 = *((_QWORD *)v125 + 11);
        v154 = v125[20];
        v172 = *((_QWORD *)v125 + 9);
        v159 = v125[8];
        v173 = *((_QWORD *)v125 + 3);
        v158 = *v125;
        v174 = *((_QWORD *)v125 + 16);
        v157 = v125[16];
        v175 = *((_QWORD *)v125 + 7);
        v156 = v125[2];
        v180 = 0x1000000;
        v183 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v128,
          (int)&unk_14049FCD0,
          *(_DWORD *)v122 + 8,
          (__int64)&v183,
          (__int64)&v180,
          (__int64)&v156,
          (__int64)&v175,
          (__int64)&v157,
          (__int64)&v174,
          (__int64)&v158,
          (__int64)&v173,
          (__int64)&v159,
          (__int64)&v172,
          (__int64)&v154,
          (__int64)&v171,
          (__int64)&v170,
          (__int64)&v155,
          (__int64)&v169,
          (__int64)&v168,
          (__int64)&v167,
          (__int64)&v165,
          (__int64)&v164,
          (__int64)&v152,
          (__int64)v153,
          (__int64)&v163,
          (__int64)&v166,
          (__int64)&v162,
          (__int64)&v161,
          (__int64)&v160);
        v137 = v179;
        if ( v179 )
        {
          if ( _InterlockedExchangeAdd(v179 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v137)(v137);
            if ( _InterlockedExchangeAdd(v137 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v137 + 8LL))(v137);
          }
        }
        v138 = v177;
        if ( v177 )
        {
          if ( _InterlockedExchangeAdd(v177 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v138)(v138);
            if ( _InterlockedExchangeAdd(v138 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v138 + 8LL))(v138);
          }
        }
        goto LABEL_237;
      }
    }
    else
    {
      v126 = (_DWORD **)(a1 + 272);
    }
    v155 = 0;
    wil::ActivityBase<Windows::Telemetry::BaseCore,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      a1,
      &v155);
    **v126 = 2;
    if ( v155 )
      ReleaseSRWLockExclusive((PSRWLOCK)v155);
    v139 = Windows::Telemetry::Base::Provider();
    v140 = (int)v139;
    if ( *(_DWORD *)v139 <= 5u
      || (*((_QWORD *)v139 + 2) & 0x400000000000LL) == 0
      || (*((_QWORD *)v139 + 3) & 0x400000000000LL) != *((_QWORD *)v139 + 3) )
    {
      goto LABEL_238;
    }
    v160 = (__int64)"1507.2603.28012.0";
    v141 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)a7 + 8LL))(a7, v188);
    if ( v141[3] > 0xFu )
      v141 = (_QWORD *)*v141;
    v161 = (__int64)v141;
    v162 = a8;
    v166 = a9;
    v142 = SystemInterface::Providers::GetSystem(v176);
    v143 = *(_QWORD *)v142 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v142 + 8LL) + 4LL);
    v144 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v143 + 96LL))(v143, v178);
    v145 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v144 + 8LL))(*v144);
    if ( v145 )
    {
      v146 = v145 - 1;
      if ( v146 )
      {
        if ( v146 != 1 )
        {
          std::logic_error::logic_error((std::logic_error *)pExceptionObject, "Invalid connectivity level");
          throw (std::logic_error *)pExceptionObject;
        }
        v147 = L"Internet";
      }
      else
      {
        v147 = L"local only";
      }
    }
    else
    {
      v147 = L"none";
    }
    v163 = (__int64)v147;
    v153[0] = a6;
    v152 = a5;
    v164 = *(_QWORD *)v181;
    v148 = &v190;
    if ( *((_QWORD *)&v191 + 1) > 7u )
      v148 = (__int128 *)v190;
    v165 = (__int64)v148;
    v167 = *a2;
    LODWORD(v155) = GetCurrentThreadId();
    v149 = *(_DWORD **)v122;
    v154 = *(_DWORD *)(*(_QWORD *)v122 + 72LL);
    v168 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v140,
      (int)&word_14049F7EE,
      (_DWORD)v149 + 8,
      (__int64)&v168,
      (__int64)&v154,
      (__int64)&v155,
      (__int64)&v167,
      (__int64)&v165,
      (__int64)&v164,
      (__int64)&v152,
      (__int64)v153,
      (__int64)&v163,
      (__int64)&v166,
      (__int64)&v162,
      (__int64)&v161,
      (__int64)&v160);
    v150 = v179;
    if ( v179 )
    {
      if ( _InterlockedExchangeAdd(v179 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v150)(v150);
        if ( _InterlockedExchangeAdd(v150 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v150 + 8LL))(v150);
      }
    }
    v151 = v177;
    if ( v177 )
    {
      if ( _InterlockedExchangeAdd(v177 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v151)(v151);
        if ( _InterlockedExchangeAdd(v151 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v151 + 8LL))(v151);
      }
    }
LABEL_237:
    std::string::_Tidy_deallocate(v188);
    goto LABEL_238;
  }
  v13 = to_wstring(a3);
  v190 = 0;
  v191 = 0;
  v14 = -1;
  do
    ++v14;
  while ( *(_WORD *)(v13 + 2 * v14) );
  std::wstring::_Construct<1,wchar_t const *>(&v190, v13, v14);
  v15 = *(_QWORD *)(a1 + 272);
  v16 = *(_DWORD *)(v15 + 72);
  if ( v16 >= 0 || (v17 = (int *)(v15 + 80), v16 != v17[2]) || !v17 )
  {
    v155 = 0;
    wil::ActivityBase<Windows::Telemetry::BaseCore,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      a1,
      &v155);
    **(_DWORD **)(a1 + 272) = 2;
    if ( v155 )
      ReleaseSRWLockExclusive((PSRWLOCK)v155);
    v35 = Windows::Telemetry::Base::Provider();
    v36 = (int)v35;
    if ( *(_DWORD *)v35 <= 5u
      || (*((_QWORD *)v35 + 2) & 0x400000000000LL) == 0
      || (*((_QWORD *)v35 + 3) & 0x400000000000LL) != *((_QWORD *)v35 + 3) )
    {
      goto LABEL_238;
    }
    v160 = (__int64)"1507.2603.28012.0";
    v37 = (_QWORD *)SystemInterface::Providers::GetSystem(v184);
    v38 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v37 + 40LL))(*v37, v186);
    v39 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v38 + 440LL))(*v38, v189);
    if ( v39[3] > 7u )
      v39 = (_QWORD *)*v39;
    v161 = (__int64)v39;
    v40 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)a7 + 8LL))(a7, v188);
    if ( v40[3] > 0xFu )
      v40 = (_QWORD *)*v40;
    v162 = (__int64)v40;
    v166 = a8;
    v163 = a9;
    v41 = SystemInterface::Providers::GetSystem(v176);
    v42 = *(_QWORD *)v41 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v41 + 8LL) + 4LL);
    v43 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v42 + 96LL))(v42, v178);
    v44 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v43 + 8LL))(*v43);
    if ( v44 )
    {
      v45 = v44 - 1;
      if ( v45 )
      {
        if ( v45 != 1 )
        {
          std::logic_error::logic_error((std::logic_error *)pExceptionObject, "Invalid connectivity level");
          throw (std::logic_error *)pExceptionObject;
        }
        v46 = L"Internet";
      }
      else
      {
        v46 = L"local only";
      }
    }
    else
    {
      v46 = L"none";
    }
    v164 = (__int64)v46;
    v153[0] = a6;
    v152 = a5;
    v165 = *a4;
    v47 = &v190;
    if ( *((_QWORD *)&v191 + 1) > 7u )
      v47 = (__int128 *)v190;
    v167 = (__int64)v47;
    v168 = *a2;
    LODWORD(v155) = GetCurrentThreadId();
    v48 = *(_QWORD *)(a1 + 272);
    v154 = *(_DWORD *)(v48 + 72);
    v169 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>>(
      v36,
      (int)&byte_14049FBF9,
      v48 + 8,
      (__int64)&v169,
      (__int64)&v154,
      (__int64)&v155,
      (__int64)&v168,
      (__int64)&v167,
      (__int64)&v165,
      (__int64)&v152,
      (__int64)v153,
      (__int64)&v164,
      (__int64)&v163,
      (__int64)&v166,
      (__int64)&v162,
      (__int64)&v161,
      (__int64)&v160);
    v49 = v179;
    if ( v179 )
    {
      if ( _InterlockedExchangeAdd(v179 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v49)(v49);
        if ( _InterlockedExchangeAdd(v49 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v49 + 8LL))(v49);
      }
    }
    v50 = v177;
    if ( v177 )
    {
      if ( _InterlockedExchangeAdd(v177 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v50)(v50);
        if ( _InterlockedExchangeAdd(v50 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v50 + 8LL))(v50);
      }
    }
    std::string::_Tidy_deallocate(v188);
    std::wstring::~wstring(v189);
    v51 = v187;
    if ( v187 )
    {
      if ( !_InterlockedDecrement(v187 + 2) )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v51)(v51);
        if ( !_InterlockedDecrement(v51 + 3) )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v51 + 8LL))(v51);
      }
    }
    v34 = v185;
    goto LABEL_66;
  }
  wil::ActivityBase<Windows::Telemetry::BaseCore,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(a1);
  v18 = Windows::Telemetry::Base::Provider();
  v19 = (int)v18;
  if ( *(_DWORD *)v18 > 5u
    && (*((_QWORD *)v18 + 2) & 0x400000000000LL) != 0
    && (*((_QWORD *)v18 + 3) & 0x400000000000LL) == *((_QWORD *)v18 + 3) )
  {
    v181 = (__int64)"1507.2603.28012.0";
    v20 = (_QWORD *)SystemInterface::Providers::GetSystem(v178);
    v21 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v20 + 40LL))(*v20, v176);
    v22 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v21 + 440LL))(*v21, v188);
    if ( v22[3] > 7u )
      v22 = (_QWORD *)*v22;
    v183 = (__int64)v22;
    v23 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)a7 + 8LL))(a7, v189);
    if ( v23[3] > 0xFu )
      v23 = (_QWORD *)*v23;
    v180 = (__int64)v23;
    v175 = a8;
    v174 = a9;
    v24 = SystemInterface::Providers::GetSystem(v186);
    v25 = *(_QWORD *)v24 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v24 + 8LL) + 4LL);
    v26 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v25 + 96LL))(v25, v184);
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
    v173 = (__int64)v29;
    v152 = a6;
    v153[0] = a5;
    v172 = *a4;
    v30 = &v190;
    if ( *((_QWORD *)&v191 + 1) > 7u )
      v30 = (__int128 *)v190;
    v171 = (__int64)v30;
    v170 = *a2;
    v169 = *((_QWORD *)v17 + 15);
    v168 = *((_QWORD *)v17 + 14);
    v156 = v17[26];
    v167 = *((_QWORD *)v17 + 12);
    v165 = *((_QWORD *)v17 + 11);
    v157 = v17[20];
    v164 = *((_QWORD *)v17 + 9);
    v158 = v17[8];
    v163 = *((_QWORD *)v17 + 3);
    v159 = *v17;
    v166 = *((_QWORD *)v17 + 16);
    v154 = v17[16];
    v162 = *((_QWORD *)v17 + 7);
    LODWORD(v155) = v17[2];
    v161 = 0x1000000;
    v160 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>>(
      v19,
      (int)&byte_14049FA4B,
      *(_QWORD *)(a1 + 272) + 8,
      (__int64)&v160,
      (__int64)&v161,
      (__int64)&v155,
      (__int64)&v162,
      (__int64)&v154,
      (__int64)&v166,
      (__int64)&v159,
      (__int64)&v163,
      (__int64)&v158,
      (__int64)&v164,
      (__int64)&v157,
      (__int64)&v165,
      (__int64)&v167,
      (__int64)&v156,
      (__int64)&v168,
      (__int64)&v169,
      (__int64)&v170,
      (__int64)&v171,
      (__int64)&v172,
      (__int64)v153,
      (__int64)&v152,
      (__int64)&v173,
      (__int64)&v174,
      (__int64)&v175,
      (__int64)&v180,
      (__int64)&v183,
      (__int64)&v181);
    v31 = v185;
    if ( v185 )
    {
      if ( _InterlockedExchangeAdd(v185 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v31)(v31);
        if ( _InterlockedExchangeAdd(v31 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v31 + 8LL))(v31);
      }
    }
    v32 = v187;
    if ( v187 )
    {
      if ( _InterlockedExchangeAdd(v187 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v32)(v32);
        if ( _InterlockedExchangeAdd(v32 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v32 + 8LL))(v32);
      }
    }
    std::string::_Tidy_deallocate(v189);
    std::wstring::~wstring(v188);
    v33 = v177;
    if ( v177 )
    {
      if ( !_InterlockedDecrement(v177 + 2) )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v33)(v33);
        if ( !_InterlockedDecrement(v33 + 3) )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v33 + 8LL))(v33);
      }
    }
    v34 = v179;
LABEL_66:
    if ( v34 && !_InterlockedDecrement(v34 + 2) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v34)(v34);
      if ( !_InterlockedDecrement(v34 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v34 + 8LL))(v34);
    }
  }
LABEL_238:
  wil::ActivityBase<Windows::WU::Telemetry::WuProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(a1);
  return std::wstring::~wstring(&v190);
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
