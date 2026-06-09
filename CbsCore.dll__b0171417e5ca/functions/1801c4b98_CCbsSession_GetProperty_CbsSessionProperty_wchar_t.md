# CCbsSession::GetProperty(_CbsSessionProperty,wchar_t * *)

- ea: `0x1801c4b98`
- end: `0x1801c76bc`
- name: `?GetProperty@CCbsSession@@QEAAJW4_CbsSessionProperty@@PEAPEA_W@Z`
- size: `11044`
- prototype: ``
- caller_count: `2`
- callee_count: `68`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1801dc874`
- `0x1802b5ca4`

## callees

- `0x18000f090`
- `0x180010b60`
- `0x180010cc0`
- `0x1800115a8`
- `0x180011a14`
- `0x180012034`
- `0x180012fe4`
- `0x180013250`
- `0x180013c54`
- `0x18001837c`
- `0x180019bdc`
- `0x180023ca8`
- `0x180023e74`
- `0x1800289f0`
- `0x18002a2bc`
- `0x18002a448`
- `0x18002a78c`
- `0x18002ac84`
- `0x18002de30`
- `0x18002e0d0`
- `0x18002f9a8`
- `0x1800406e4`
- `0x180044bdc`
- `0x180044c5c`
- `0x18004be14`
- `0x180051c8c`
- `0x180055b4c`
- `0x180056864`
- `0x180059a00`
- `0x18005dd58`
- `0x18005eef0`
- `0x180060d80`
- `0x1800653d8`
- `0x18008f280`
- `0x180095e34`
- `0x180098538`
- `0x180099390`
- `0x180099548`
- `0x18009cf78`
- `0x1800a0a78`
- `0x1800a6818`
- `0x1800a8678`
- `0x1800d0588`
- `0x1800e7500`
- `0x1800ea2d4`
- `0x1800eb500`
- `0x1800eb920`
- `0x1800ec920`
- `0x1800fa3ec`
- `0x18010c754`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801c6870`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801c69a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801c6b1f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801c6c24`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801c6870`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801c69a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801c6b1f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801c6c24`

## string_xrefs

- `0x1801c4f7f`: `Unserviceable`
- `0x1801c4c83`: `Failed to get task allocator.`
- `0x1801c7445`: `Failed to get path to UpdateAgent.dll`
- `0x1801c7410`: `UpdateAgent.dll`
- `0x1801c708a`: `Failed to get servicing directory`
- `0x1801c66a6`: `*.XML`
- `0x1801c712f`: `*.XML`
- `0x1801c6a5d`: `Failed directory walk on {}`
- `0x1801c7169`: `Failed directory walk on {}`
- `0x1801c6009`: `Failed to get target Windows directory`
- `0x1801c60a2`: `Failed to create servicing querier`
- `0x1801c6f27`: `Failed to create cbs identity`
- `0x1801c6bc9`: `Failed to query components of package manifest: {}`
- `0x1801c6ab8`: `Failed to create path to component: {}`
- `0x1801c4d27`: `Failed getting property.  Analysis must be completed first.`
- `0x1801c4dc8`: `Failed getting property. Session must be completed first.`
- `0x1801c5235`: `Failed to get session completion timestamp, last session state: {}`
- `0x1801c52d3`: `Failed to get session completion timestamp, last session state: {}`
- `0x1801c536d`: `Failed to get session completion timestamp, last session state: {}`
- `0x1801c53fd`: `Failed to format session completion date/time`
- `0x1801c6936`: `Failed to create path to component file: {}`

## pseudocode

```c
__int64 __fastcall CCbsSession::GetProperty(__int64 a1, int a2, _QWORD *a3)
{
  _QWORD *v3; // r12
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  __int64 InitPointer; // rax
  int TaskAllocator; // eax
  unsigned __int64 v11; // r9
  __int64 v12; // r9
  __int64 v13; // rdx
  int v14; // eax
  unsigned int v15; // eax
  const wchar_t *v16; // r8
  int v17; // eax
  const wchar_t *v18; // r8
  int v19; // eax
  __int64 v20; // rdx
  int v21; // eax
  int Property; // eax
  unsigned int v23; // edx
  const wchar_t *v24; // r8
  int v25; // eax
  const wchar_t *v26; // r8
  int IsRebootRequired; // eax
  const wchar_t *v28; // r8
  unsigned __int64 v29; // r9
  int v31; // eax
  int v32; // eax
  unsigned int v33; // edi
  const wchar_t *v34; // rax
  int v35; // eax
  __int64 v36; // r10
  const wchar_t *v37; // rax
  int v38; // eax
  __int64 v39; // r10
  const wchar_t *v40; // rax
  int SessionTimestamp; // eax
  __int64 v42; // r10
  int v43; // eax
  const wchar_t *v44; // r8
  int v45; // eax
  int v46; // eax
  int v47; // eax
  int v48; // eax
  int v49; // eax
  int v50; // eax
  int v51; // eax
  int v52; // eax
  int v53; // eax
  int v54; // eax
  int v55; // eax
  int v56; // eax
  const wchar_t *v57; // rax
  const wchar_t *v58; // r8
  int v59; // eax
  int v60; // eax
  int v61; // eax
  const wchar_t *v62; // rax
  const wchar_t *v63; // r8
  int v64; // eax
  int v65; // eax
  int v66; // eax
  const wchar_t *v67; // r8
  int v68; // eax
  int v69; // eax
  unsigned __int64 v70; // r9
  __int64 v71; // rdx
  void *p_pv; // rcx
  int v73; // eax
  void *v74; // rcx
  int TotalPackageMinimumSize; // eax
  int v76; // eax
  int v77; // eax
  const wchar_t *v78; // rax
  const wchar_t *v79; // r8
  int TimestampDifference; // eax
  int v81; // eax
  int v82; // eax
  unsigned int ImageProcessorArchitecture; // eax
  int ProcessorArchitectureString; // eax
  __int64 v85; // rdx
  unsigned __int64 v86; // r9
  int TargetWindowsDirectory; // eax
  int v88; // eax
  __int64 v89; // rdx
  int v90; // eax
  int v91; // eax
  _QWORD *v92; // rdi
  _QWORD *v93; // r14
  __int64 v94; // r15
  union _ULARGE_INTEGER v95; // rbx
  __int64 *v96; // r15
  struct CCbsIdentity **v97; // rax
  int CbsIdentity; // r14d
  const struct CCbsIdentity **v99; // rbx
  const struct CCbsIdentity **v100; // rdi
  struct ICbsIdentity *v101; // rdx
  void *v102; // rdi
  _QWORD *v103; // rdx
  char *v104; // rcx
  __int64 v105; // rax
  void *v106; // rdi
  _QWORD *v107; // rdx
  char *v108; // rcx
  __int64 v109; // rax
  void *v110; // rdi
  _QWORD *v111; // rdx
  char *v112; // rcx
  __int64 v113; // rax
  int v114; // eax
  __int64 *v115; // r14
  LPVOID v116; // rbx
  union _ULARGE_INTEGER v117; // rdi
  __int64 v118; // r8
  int v119; // esi
  wchar_t *v120; // rsi
  __int64 v121; // rcx
  int v122; // r15d
  __int64 v123; // rdi
  __int64 *v124; // r15
  __int64 *v125; // r13
  void *v126; // rbx
  _QWORD *v127; // rdx
  char *v128; // rcx
  __int64 v129; // rax
  __int64 v130; // r8
  int v131; // r12d
  __int64 v132; // rdx
  __int64 v133; // rdx
  __int64 v134; // rdx
  void *v135; // rcx
  int v136; // eax
  int v137; // eax
  unsigned int v138; // edi
  void *v139; // rbx
  _QWORD *v140; // rdx
  char *v141; // rcx
  __int64 v142; // rax
  void *v143; // rbx
  _QWORD *v144; // rdx
  char *v145; // rcx
  __int64 v146; // rax
  int ServicingDirectory; // eax
  __int64 v148; // rdx
  unsigned __int64 v149; // r9
  int v150; // eax
  __int64 v151; // rcx
  LPVOID v152; // rbx
  int v153; // eax
  __int64 v154; // rdx
  int v155; // edi
  __int64 *v156; // rdi
  __int64 *v157; // r14
  __int64 v158; // r8
  unsigned __int64 v159; // rdi
  unsigned __int64 v160; // r15
  unsigned __int64 v161; // r14
  _QWORD *v162; // rsi
  unsigned __int64 v163; // rbx
  unsigned __int64 v164; // r12
  __int64 v165; // rdx
  __int64 v166; // rcx
  int v167; // eax
  int v168; // eax
  int Win32PathOfSiblingFile; // eax
  unsigned __int64 v170; // r9
  __int64 v171; // rdx
  int v172; // eax
  __int64 v173; // rax
  int v174; // eax
  int ReofferProperty; // eax
  const wchar_t *v176; // r8
  int v177; // eax
  int IsPended; // eax
  const wchar_t *v179; // r8
  const wchar_t *v180; // r8
  int v181; // eax
  unsigned int *v182; // [rsp+20h] [rbp-E0h]
  unsigned int v183[2]; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t *v184; // [rsp+48h] [rbp-B8h] BYREF
  union _ULARGE_INTEGER v185; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v186; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t *v187; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t *v188; // [rsp+68h] [rbp-98h] BYREF
  __int64 v189; // [rsp+70h] [rbp-90h] BYREF
  __int64 v190; // [rsp+78h] [rbp-88h] BYREF
  int v191[2]; // [rsp+80h] [rbp-80h] BYREF
  char v192; // [rsp+88h] [rbp-78h]
  wchar_t *v193; // [rsp+90h] [rbp-70h] BYREF
  int v194[2]; // [rsp+98h] [rbp-68h] BYREF
  unsigned int v195[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v196; // [rsp+A8h] [rbp-58h] BYREF
  LPVOID pv; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v198; // [rsp+B8h] [rbp-48h] BYREF
  void *v199[3]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v200; // [rsp+D8h] [rbp-28h]
  __int16 v201; // [rsp+E0h] [rbp-20h]
  __int128 v202; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v203; // [rsp+F8h] [rbp-8h]
  _BYTE v204[24]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v205; // [rsp+118h] [rbp+18h]
  __int64 *v206; // [rsp+128h] [rbp+28h]
  _BYTE v207[24]; // [rsp+140h] [rbp+40h] BYREF
  unsigned __int64 v208; // [rsp+158h] [rbp+58h]
  _QWORD *v209; // [rsp+168h] [rbp+68h]
  _BYTE v210[24]; // [rsp+180h] [rbp+80h] BYREF
  __int64 v211; // [rsp+198h] [rbp+98h]
  _QWORD v212[2]; // [rsp+1C0h] [rbp+C0h] BYREF
  _WORD v213[8]; // [rsp+1D0h] [rbp+D0h] BYREF
  _BYTE v214[24]; // [rsp+1E0h] [rbp+E0h] BYREF
  __int64 v215; // [rsp+1F8h] [rbp+F8h]
  __int64 *v216; // [rsp+208h] [rbp+108h]
  wchar_t v217[32]; // [rsp+220h] [rbp+120h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  *(_QWORD *)v183 = a3;
  v3 = a3;
  v196 = 0;
  v186 = 0;
  memset_0(v217, 0, sizeof(v217));
  v6 = CCbsSession::CheckInitialized((CCbsSession *)a1);
  v7 = v6;
  if ( v6 < 0 )
  {
    v195[0] = v6;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Cannot GetSessionID on a session that has not been initialized.");
      *(_QWORD *)v183 = v195;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)v183);
    }
    v8 = 108;
LABEL_9:
    v11 = v7;
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\base\\cbs\\core\\cbssessionproperties.cpp",
      (const char *)v11,
      (int)v182);
    goto LABEL_71;
  }
  InitPointer = Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v186);
  TaskAllocator = GetTaskAllocator(InitPointer);
  v7 = TaskAllocator;
  if ( TaskAllocator < 0 )
  {
    v195[0] = TaskAllocator;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get task allocator.");
      *(_QWORD *)v183 = v195;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)v183);
    }
    v8 = 109;
    goto LABEL_9;
  }
  if ( a2 <= 13 )
  {
    if ( a2 != 13 && a2 != 8 && a2 != 9 && a2 != 10 && (unsigned int)(a2 - 11) > 1 )
    {
LABEL_32:
      if ( a2 > 8 )
      {
        switch ( a2 )
        {
          case 9:
            v55 = StringCchPrintfW(v217, 0x20u, L"%I64u", *(_QWORD *)(a1 + 1216));
            v7 = v55;
            if ( v55 >= 0 )
            {
              v56 = SczPublicAllocFromSz(&v196, v186, v217);
              v7 = v56;
              if ( v56 >= 0 )
                goto LABEL_70;
              v11 = (unsigned int)v56;
              v8 = 223;
              goto LABEL_10;
            }
            v195[0] = v55;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                (__int64)LogAdapter::g_Logger,
                0,
                3,
                (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to format non-volatile size");
              *(_QWORD *)v183 = v195;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (__int64)LogAdapter::g_Logger,
                1,
                3,
                (__int64)": {}",
                (__int64)v183);
            }
            v8 = 221;
            goto LABEL_9;
          case 10:
            v53 = StringCchPrintfW(v217, 0x20u, L"%I64u", *(_QWORD *)(a1 + 1224));
            v7 = v53;
            if ( v53 >= 0 )
            {
              v54 = SczPublicAllocFromSz(&v196, v186, v217);
              v7 = v54;
              if ( v54 >= 0 )
                goto LABEL_70;
              v11 = (unsigned int)v54;
              v8 = 233;
              goto LABEL_10;
            }
            v195[0] = v53;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                (__int64)LogAdapter::g_Logger,
                0,
                3,
                (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to format shared-with-windows size");
              *(_QWORD *)v183 = v195;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (__int64)LogAdapter::g_Logger,
                1,
                3,
                (__int64)": {}",
                (__int64)v183);
            }
            v8 = 231;
            goto LABEL_9;
          case 11:
            v51 = StringCchPrintfW(v217, 0x20u, L"%I64u", *(_QWORD *)(a1 + 1232));
            v7 = v51;
            if ( v51 >= 0 )
            {
              v52 = SczPublicAllocFromSz(&v196, v186, v217);
              v7 = v52;
              if ( v52 >= 0 )
                goto LABEL_70;
              v11 = (unsigned int)v52;
              v8 = 243;
              goto LABEL_10;
            }
            v195[0] = v51;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                (__int64)LogAdapter::g_Logger,
                0,
                3,
                (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to format according-to-explorer size");
              *(_QWORD *)v183 = v195;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (__int64)LogAdapter::g_Logger,
                1,
                3,
                (__int64)": {}",
                (__int64)v183);
            }
            v8 = 241;
            goto LABEL_9;
          case 12:
            if ( !*(_QWORD *)(a1 + 1248) )
            {
              v50 = SczPublicAllocFromSz(&v196, v186, &qword_1802EB518);
              v7 = v50;
              if ( v50 >= 0 )
                goto LABEL_70;
              v11 = (unsigned int)v50;
              v8 = 259;
              goto LABEL_10;
            }
            v48 = StringCchPrintfW(v217, 0x20u, L"%I64u");
            v7 = v48;
            if ( v48 >= 0 )
            {
              v49 = SczPublicAllocFromSz(&v196, v186, v217);
              v7 = v49;
              if ( v49 >= 0 )
                goto LABEL_70;
              v11 = (unsigned int)v49;
              v8 = 255;
              goto LABEL_10;
            }
            v195[0] = v48;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                (__int64)LogAdapter::g_Logger,
                0,
                3,
                (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to format last scavenge date/time");
              *(_QWORD *)v183 = v195;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (__int64)LogAdapter::g_Logger,
                1,
                3,
                (__int64)": {}",
                (__int64)v183);
            }
            v8 = 253;
            goto LABEL_9;
          case 13:
            v46 = StringCchPrintfW(v217, 0x20u, L"%lu", *(unsigned int *)(a1 + 1240));
            v7 = v46;
            if ( v46 >= 0 )
            {
              v47 = SczPublicAllocFromSz(&v196, v186, v217);
              v7 = v47;
              if ( v47 >= 0 )
                goto LABEL_70;
              v11 = (unsigned int)v47;
              v8 = 270;
              goto LABEL_10;
            }
            v195[0] = v46;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                (__int64)LogAdapter::g_Logger,
                0,
                3,
                (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to format superseded-package count");
              *(_QWORD *)v183 = v195;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (__int64)LogAdapter::g_Logger,
                1,
                3,
                (__int64)": {}",
                (__int64)v183);
            }
            v8 = 268;
            goto LABEL_9;
          case 14:
            v44 = L"1";
            if ( !*(_DWORD *)(a1 + 1256) )
              v44 = L"0";
            v45 = SczPublicAllocFromSz(&v196, v186, v44);
            v7 = v45;
            if ( v45 >= 0 )
              goto LABEL_70;
            v11 = (unsigned int)v45;
            v8 = 276;
            goto LABEL_10;
        }
        v185.QuadPart = 0;
        CritSecLocker::CritSecLocker((CritSecLocker *)&v202, (struct AutoCritSec *)(a1 + 584), 1);
        v33 = *(_DWORD *)(a1 + 768);
        CritSecLocker::Unlock((CritSecLocker *)&v202);
        if ( *(_DWORD *)(a1 + 1032) )
        {
          v40 = (const wchar_t *)CbsSessionStateToString(208);
          SessionTimestamp = PackageStoreGetSessionTimestamp((struct CCbsSession *)a1, v40, 1u, &v185);
          v7 = SessionTimestamp;
          if ( SessionTimestamp < 0 )
          {
            v195[0] = SessionTimestamp;
            if ( LogAdapter::g_Logger )
            {
              *(_QWORD *)v183 = CbsSessionStateToString(v33);
              LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                v42,
                0,
                3,
                (__int64)"Failed to get session completion timestamp, last session state: {}",
                (__int64)v183);
              v193 = (wchar_t *)v195;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (__int64)LogAdapter::g_Logger,
                1,
                3,
                (__int64)": {}",
                (__int64)&v193);
            }
            v29 = v7;
            v20 = 325;
            goto LABEL_68;
          }
        }
        else if ( (int)v33 < 112 )
        {
          v37 = (const wchar_t *)CbsSessionStateToString(101);
          v38 = PackageStoreGetSessionTimestamp((struct CCbsSession *)a1, v37, 1u, &v185);
          v7 = v38;
          if ( v38 < 0 )
          {
            v195[0] = v38;
            if ( LogAdapter::g_Logger )
            {
              *(_QWORD *)v183 = CbsSessionStateToString(v33);
              LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                v39,
                0,
                3,
                (__int64)"Failed to get session completion timestamp, last session state: {}",
                (__int64)v183);
              v193 = (wchar_t *)v195;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (__int64)LogAdapter::g_Logger,
                1,
                3,
                (__int64)": {}",
                (__int64)&v193);
            }
            v29 = v7;
            v20 = 313;
            goto LABEL_68;
          }
        }
        else
        {
          v34 = (const wchar_t *)CbsSessionStateToString(112);
          v35 = PackageStoreGetSessionTimestamp((struct CCbsSession *)a1, v34, 1u, &v185);
          v7 = v35;
          if ( v35 < 0 )
          {
            v195[0] = v35;
            if ( LogAdapter::g_Logger )
            {
              *(_QWORD *)v183 = CbsSessionStateToString(v33);
              LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                v36,
                0,
                3,
                (__int64)"Failed to get session completion timestamp, last session state: {}",
                (__int64)v183);
              v193 = (wchar_t *)v195;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (__int64)LogAdapter::g_Logger,
                1,
                3,
                (__int64)": {}",
                (__int64)&v193);
            }
            v29 = v7;
            v20 = 302;
            goto LABEL_68;
          }
        }
        v43 = StringCchPrintfW(v217, 0x20u, L"%I64u", v185.QuadPart);
        v7 = v43;
        if ( v43 < 0 )
        {
          v195[0] = v43;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to format session completion date/time");
            *(_QWORD *)v183 = v195;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {}",
              (__int64)v183);
          }
          v29 = v7;
          v20 = 330;
          goto LABEL_68;
        }
        v19 = SczPublicAllocFromSz(&v196, v186, v217);
        v7 = v19;
        if ( v19 < 0 )
        {
          v20 = 332;
          goto LABEL_67;
        }
      }
      else
      {
        switch ( a2 )
        {
          case 8:
            v31 = StringCchPrintfW(v217, 0x20u, L"%I64u", *(_QWORD *)(a1 + 1208));
            v7 = v31;
            if ( v31 >= 0 )
            {
              v32 = SczPublicAllocFromSz(&v196, v186, v217);
              v7 = v32;
              if ( v32 >= 0 )
                goto LABEL_70;
              v11 = (unsigned int)v32;
              v8 = 213;
              goto LABEL_10;
            }
            v195[0] = v31;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                (__int64)LogAdapter::g_Logger,
                0,
                3,
                (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to format volatile size");
              *(_QWORD *)v183 = v195;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (__int64)LogAdapter::g_Logger,
                1,
                3,
                (__int64)": {}",
                (__int64)v183);
            }
            v8 = 211;
            goto LABEL_9;
          case 1:
            CritSecLocker::CritSecLocker((CritSecLocker *)&v202, (struct AutoCritSec *)(a1 + 584), 1);
            IsRebootRequired = CCbsSession::IsRebootRequired((CCbsSession *)a1);
            v28 = L"1";
            if ( !IsRebootRequired )
              v28 = L"0";
            v19 = SczPublicAllocFromSz(&v196, v186, v28);
            v7 = v19;
            if ( v19 < 0 )
            {
              v20 = 148;
              goto LABEL_67;
            }
            break;
          case 2:
            CritSecLocker::CritSecLocker((CritSecLocker *)&v202, (struct AutoCritSec *)(a1 + 584), 1);
            v26 = &qword_1802EB518;
            if ( *(_QWORD *)(a1 + 1072) )
              v26 = *(const wchar_t **)(a1 + 1072);
            v19 = SczPublicAllocFromSz(&v196, v186, v26);
            v7 = v19;
            if ( v19 < 0 )
            {
              v20 = 155;
              goto LABEL_67;
            }
            break;
          case 3:
            v195[0] = 0;
            Property = PackageStoreGetProperty((struct CCbsSession *)a1, L"Unserviceable", v195);
            v23 = v195[0];
            v24 = L"1";
            if ( Property < 0 )
              v23 = 0;
            if ( !v23 )
              v24 = L"0";
            v25 = SczPublicAllocFromSz(&v196, v186, v24);
            v7 = v25;
            if ( v25 >= 0 )
              goto LABEL_70;
            v11 = (unsigned int)v25;
            v8 = 166;
            goto LABEL_10;
          case 4:
            v21 = SczPublicAllocFromSz(&v196, v186, L"1");
            v7 = v21;
            if ( v21 >= 0 )
              goto LABEL_70;
            v11 = (unsigned int)v21;
            v8 = 175;
            goto LABEL_10;
          case 5:
            CritSecLocker::CritSecLocker((CritSecLocker *)&v202, (struct AutoCritSec *)(a1 + 584), 1);
            v18 = &qword_1802EB518;
            if ( *(_QWORD *)(a1 + 1120) )
              v18 = *(const wchar_t **)(a1 + 1120);
            v19 = SczPublicAllocFromSz(&v196, v186, v18);
            v7 = v19;
            if ( v19 < 0 )
            {
              v20 = 182;
LABEL_67:
              v29 = (unsigned int)v19;
LABEL_68:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v20,
                (unsigned int)"onecore\\base\\cbs\\core\\cbssessionproperties.cpp",
                (const char *)v29,
                (int)v182);
              CritSecLocker::~CritSecLocker((CritSecLocker *)&v202);
              goto LABEL_71;
            }
            break;
          case 6:
            v195[0] = 0;
            v15 = CheckStoreCorruptionFlag((struct CCbsSession *)a1, 0, (int *)v195);
            LogAdapter::TraceAtLevelIfFailed<long,>(1, v15, "Unable to GetAndResetCorruptionFlag");
            v16 = L"1";
            if ( !v195[0] )
              v16 = L"0";
            v17 = SczPublicAllocFromSz(&v196, v186, v16);
            v7 = v17;
            if ( v17 >= 0 )
              goto LABEL_70;
            v11 = (unsigned int)v17;
            v8 = 194;
            goto LABEL_10;
          case 7:
            v14 = SczPublicAllocFromSz(&v196, v186, L"0");
            v7 = v14;
            if ( v14 >= 0 )
              goto LABEL_70;
            v11 = (unsigned int)v14;
            v8 = 200;
            goto LABEL_10;
          default:
            goto LABEL_210;
        }
      }
LABEL_69:
      CritSecLocker::~CritSecLocker((CritSecLocker *)&v202);
      goto LABEL_70;
    }
    goto LABEL_17;
  }
  if ( a2 == 14 )
  {
LABEL_17:
    if ( !*(_QWORD *)(a1 + 1232) )
    {
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed getting property.  Analysis must be completed first.");
        *(_QWORD *)v183 = v195;
        v195[0] = -2147023728;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {0}",
          (__int64)v183);
      }
      v12 = 1168;
      v13 = 126;
LABEL_21:
      v7 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v13,
             (unsigned int)"onecore\\base\\cbs\\core\\cbssessionproperties.cpp",
             (const char *)v12,
             (unsigned int)v182);
      goto LABEL_71;
    }
    goto LABEL_30;
  }
  if ( (a2 == 15 || a2 == 23 || (unsigned int)(a2 - 24) <= 1) && !*(_DWORD *)(a1 + 1036) )
  {
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed getting property. Session must be completed first.");
      *(_QWORD *)v183 = v195;
      v195[0] = -2147024846;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {0}",
        (__int64)v183);
    }
    v12 = 50;
    v13 = 136;
    goto LABEL_21;
  }
LABEL_30:
  if ( a2 <= 16 )
  {
    if ( a2 != 16 )
      goto LABEL_32;
LABEL_184:
    v185.QuadPart = 0;
    TotalPackageMinimumSize = CCbsSession::GetTotalPackageMinimumSize(a1, (unsigned int)a2, &v185);
    v7 = TotalPackageMinimumSize;
    if ( TotalPackageMinimumSize >= 0 )
    {
      v76 = StringCchPrintfW(v217, 0x20u, L"%llu", v185.QuadPart);
      v7 = v76;
      if ( v76 >= 0 )
      {
        v77 = SczPublicAllocFromSz(&v196, v186, v217);
        v7 = v77;
        if ( v77 >= 0 )
          goto LABEL_70;
        v11 = (unsigned int)v77;
        v8 = 348;
        goto LABEL_10;
      }
      v195[0] = v76;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to format package minimum size.");
        *(_QWORD *)v183 = v195;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v183);
      }
      v8 = 346;
    }
    else
    {
      v195[0] = TotalPackageMinimumSize;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get total package minimum size.");
        *(_QWORD *)v183 = v195;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v183);
      }
      v8 = 342;
    }
    goto LABEL_9;
  }
  if ( a2 <= 25 )
  {
    switch ( a2 )
    {
      case 25:
        v195[0] = 0;
        CbsSessionStateToString(208);
        v78 = (const wchar_t *)CbsSessionStateToString(176);
        TimestampDifference = CbsGetTimestampDifference((struct CCbsSession *)a1, v78, v79, v195);
        v7 = TimestampDifference;
        if ( TimestampDifference >= 0 )
        {
          v81 = StringCchPrintfW(v217, 0x20u, L"%lu", v195[0]);
          v7 = v81;
          if ( v81 >= 0 )
          {
            v82 = SczPublicAllocFromSz(&v196, v186, v217);
            v7 = v82;
            if ( v82 >= 0 )
              goto LABEL_70;
            v11 = (unsigned int)v82;
            v8 = 445;
            goto LABEL_10;
          }
          v195[0] = v81;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to format session post-reboot time");
            *(_QWORD *)v183 = v195;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {}",
              (__int64)v183);
          }
          v8 = 443;
        }
        else
        {
          v195[0] = TimestampDifference;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"Post-reboot time performance datapoint is invalid.");
            *(_QWORD *)v183 = v195;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {}",
              (__int64)v183);
          }
          v8 = 439;
        }
        goto LABEL_9;
      case 17:
        goto LABEL_184;
      case 19:
        v185.QuadPart = 0;
        v69 = CCbsSession::EnumerateFeaturesToRetry((CCbsSession *)a1, (wchar_t **)&v185);
        v7 = v69;
        if ( v69 >= 0 )
        {
          v73 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))SczPublicAllocFromSz)(
                  &v196,
                  v186,
                  (union _ULARGE_INTEGER)v185.QuadPart);
          v7 = v73;
          if ( v73 >= 0 )
          {
            v74 = &v185;
            goto LABEL_183;
          }
          v70 = (unsigned int)v73;
          v71 = 358;
        }
        else
        {
          v195[0] = v69;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get retry features.");
            *(_QWORD *)v183 = v195;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {}",
              (__int64)v183);
          }
          v70 = v7;
          v71 = 356;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v71,
          (unsigned int)"onecore\\base\\cbs\\core\\cbssessionproperties.cpp",
          (const char *)v70,
          (int)v182);
        p_pv = &v185;
        goto LABEL_179;
    }
    if ( a2 != 20 && a2 != 21 )
    {
      switch ( a2 )
      {
        case 22:
          v67 = L"1";
          if ( !*(_BYTE *)(a1 + 2252) )
            v67 = L"0";
          v68 = SczPublicAllocFromSz(&v196, v186, v67);
          v7 = v68;
          if ( v68 >= 0 )
            goto LABEL_70;
          v11 = (unsigned int)v68;
          v8 = 375;
          goto LABEL_10;
        case 23:
          v195[0] = 0;
          CbsSessionStateToString(160);
          v62 = (const wchar_t *)CbsSessionStateToString(144);
          v64 = CbsGetTimestampDifference((struct CCbsSession *)a1, v62, v63, v195);
          v7 = v64;
          if ( v64 >= 0 )
          {
            v65 = StringCchPrintfW(v217, 0x20u, L"%lu", v195[0]);
            v7 = v65;
            if ( v65 >= 0 )
            {
              v66 = SczPublicAllocFromSz(&v196, v186, v217);
              v7 = v66;
              if ( v66 >= 0 )
                goto LABEL_70;
              v11 = (unsigned int)v66;
              v8 = 398;
              goto LABEL_10;
            }
            v195[0] = v65;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                (__int64)LogAdapter::g_Logger,
                0,
                3,
                (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to format session shutdown time");
              *(_QWORD *)v183 = v195;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (__int64)LogAdapter::g_Logger,
                1,
                3,
                (__int64)": {}",
                (__int64)v183);
            }
            v8 = 396;
          }
          else
          {
            v195[0] = v64;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                (__int64)LogAdapter::g_Logger,
                0,
                3,
                (struct Windows::Rtl::IRtlFormattedOutputStream *)"Shutdown time performance datapoint is invalid.");
              *(_QWORD *)v183 = v195;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (__int64)LogAdapter::g_Logger,
                1,
                3,
                (__int64)": {}",
                (__int64)v183);
            }
            v8 = 392;
          }
          goto LABEL_9;
        case 24:
          v195[0] = 0;
          CbsSessionStateToString(176);
          v57 = (const wchar_t *)CbsSessionStateToString(160);
          v59 = CbsGetTimestampDifference((struct CCbsSession *)a1, v57, v58, v195);
          v7 = v59;
          if ( v59 >= 0 )
          {
            v60 = StringCchPrintfW(v217, 0x20u, L"%lu", v195[0]);
            v7 = v60;
            if ( v60 >= 0 )
            {
              v61 = SczPublicAllocFromSz(&v196, v186, v217);
              v7 = v61;
              if ( v61 >= 0 )
                goto LABEL_70;
              v11 = (unsigned int)v61;
              v8 = 421;
              goto LABEL_10;
            }
            v195[0] = v60;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                (__int64)LogAdapter::g_Logger,
                0,
                3,
                (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to format session reboot time");
              *(_QWORD *)v183 = v195;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (__int64)LogAdapter::g_Logger,
                1,
                3,
                (__int64)": {}",
                (__int64)v183);
            }
            v8 = 419;
          }
          else
          {
            v195[0] = v59;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                (__int64)LogAdapter::g_Logger,
                0,
                3,
                (struct Windows::Rtl::IRtlFormattedOutputStream *)"Reboot time performance datapoint is invalid.");
              *(_QWORD *)v183 = v195;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (__int64)LogAdapter::g_Logger,
                1,
                3,
                (__int64)": {}",
                (__int64)v183);
            }
            v8 = 415;
          }
          goto LABEL_9;
      }
      goto LABEL_210;
    }
LABEL_408:
    LOBYTE(v195[0]) = 0;
    ReofferProperty = CCbsSession::GetReofferProperty(a1, (unsigned int)a2, v195);
    v7 = ReofferProperty;
    if ( ReofferProperty >= 0 )
    {
      v176 = L"1";
      if ( !LOBYTE(v195[0]) )
        v176 = L"0";
      v177 = SczPublicAllocFromSz(&v196, v186, v176);
      v7 = v177;
      if ( v177 >= 0 )
        goto LABEL_70;
      v11 = (unsigned int)v177;
      v8 = 369;
      goto LABEL_10;
    }
    LODWORD(v196) = ReofferProperty;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get reoffer property.");
      *(_QWORD *)v191 = &v196;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)v191);
    }
    v8 = 367;
    goto LABEL_9;
  }
  switch ( a2 )
  {
    case 26:
      v180 = L"1";
      if ( (*(_DWORD *)(a1 + 2208) & 0x20000) == 0 )
        v180 = L"0";
      v181 = SczPublicAllocFromSz(&v196, v186, v180);
      v7 = v181;
      if ( v181 >= 0 )
        goto LABEL_70;
      v11 = (unsigned int)v181;
      v8 = 453;
      goto LABEL_10;
    case 27:
      CritSecLocker::CritSecLocker((CritSecLocker *)&v202, (struct AutoCritSec *)(a1 + 584), 1);
      v195[0] = 0;
      IsPended = CCbsSession::LCUInstallIsPended((CCbsSession *)a1, (int *const)v195);
      v7 = IsPended;
      if ( IsPended < 0 )
      {
        LODWORD(v196) = IsPended;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to check whether LCU is pending");
          *(_QWORD *)v191 = &v196;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)v191);
        }
        v29 = v7;
        v20 = 462;
        goto LABEL_68;
      }
      v179 = L"1";
      if ( !v195[0] )
        v179 = L"0";
      v19 = SczPublicAllocFromSz(&v196, v186, v179);
      v7 = v19;
      if ( v19 < 0 )
      {
        v20 = 464;
        goto LABEL_67;
      }
      goto LABEL_69;
    case 28:
      goto LABEL_408;
    case 29:
      v203 = 0;
      v202 = 0;
      Win32PathOfSiblingFile = Windows::COM::GetWin32PathOfSiblingFile(&_ImageBase, L"UpdateAgent.dll", &v202);
      v7 = Win32PathOfSiblingFile;
      if ( Win32PathOfSiblingFile >= 0 )
      {
        *(_QWORD *)v191 = &v202;
        v172 = Windows::StringUtil::Rtl::EnsureNullTerminated<Windows::AutoOperatorAmpersandHelper<_LUNICODE_STRING,Windows::Auto<_LUNICODE_STRING>>>(v191);
        if ( v172 < 0 )
        {
          v7 = wil::details::in1diag3::Return_NtStatus(
                 retaddr,
                 (void *)0x1DC,
                 (unsigned int)"onecore\\base\\cbs\\core\\cbssessionproperties.cpp",
                 (const char *)(unsigned int)v172,
                 (int)v182);
          goto LABEL_402;
        }
        v173 = Windows::StringUtil::c_str<Windows::Auto<_LUNICODE_STRING>>(&v202);
        v174 = SczPublicAllocFromSz(&v196, v186, v173);
        v7 = v174;
        if ( v174 >= 0 )
        {
          Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v202);
          goto LABEL_70;
        }
        v170 = (unsigned int)v174;
        v171 = 478;
      }
      else
      {
        LODWORD(v196) = Win32PathOfSiblingFile;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get path to UpdateAgent.dll");
          *(_QWORD *)v191 = &v196;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)v191);
        }
        v170 = v7;
        v171 = 474;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v171,
        (unsigned int)"onecore\\base\\cbs\\core\\cbssessionproperties.cpp",
        (const char *)v170,
        (int)v182);
LABEL_402:
      Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v202);
      goto LABEL_71;
    case 30:
      pv = 0;
      CCbsStringArray::CCbsStringArray((CCbsStringArray *)v204);
      CCbsStringArray::CCbsStringArray((CCbsStringArray *)v207);
      v184 = 0;
      ServicingDirectory = CCbsSession::GetServicingDirectory((CCbsSession *)a1, L"FodMetadata", (wchar_t **)&pv);
      v7 = ServicingDirectory;
      if ( ServicingDirectory < 0 )
      {
        LODWORD(v196) = ServicingDirectory;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get servicing directory");
          *(_QWORD *)v191 = &v196;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)v191);
        }
        v148 = 489;
LABEL_356:
        v149 = v7;
LABEL_357:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v148,
          (unsigned int)"onecore\\base\\cbs\\core\\cbssessionproperties.cpp",
          (const char *)v149,
          (int)v182);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v184);
        CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v207);
        CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v204);
        p_pv = &pv;
        goto LABEL_179;
      }
      v150 = SczAllocConcatSz(&pv, L"\\metadata\\");
      v7 = v150;
      if ( v150 < 0 )
      {
        v149 = (unsigned int)v150;
        v148 = 491;
        goto LABEL_357;
      }
      v152 = pv;
      v153 = CbsEnumFiles(v151, pv, L"*.XML", v204);
      v119 = v153;
      if ( v153 >= 0 )
      {
        if ( v205 )
        {
          v156 = v206;
          v157 = &v206[v205];
          while ( v156 != v157 )
          {
            v158 = *v156;
            v185.QuadPart = 0;
            v119 = SczAllocCombinePath2Sz(&v185, v152, v158);
            if ( v119 < 0 )
            {
              v165 = 503;
LABEL_383:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v165,
                (unsigned int)"onecore\\base\\cbs\\core\\cbssessionproperties.cpp",
                (const char *)(unsigned int)v119,
                (int)v182);
              Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v185);
LABEL_365:
              Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v184);
              CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v207);
              CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v204);
              v135 = &pv;
LABEL_366:
              Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(v135);
              v7 = v119;
              goto LABEL_71;
            }
            v119 = PathPrefix(&v185);
            if ( v119 < 0 )
            {
              v165 = 504;
              goto LABEL_383;
            }
            *(union _ULARGE_INTEGER *)v191 = v185;
            v119 = CCbsArrayBase<wchar_t *,CCbsStringArray>::Add(v207, v191);
            if ( v119 < 0 )
            {
              v165 = 505;
              goto LABEL_383;
            }
            v185.QuadPart = 0;
            Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v185);
            ++v156;
          }
          v159 = v208;
          if ( v208 > 1 )
          {
            v160 = v208 - 1;
            v161 = 0;
            v162 = v209;
            do
            {
              v163 = v161 + 1;
              v164 = v161++;
              while ( v163 < v159 )
              {
                if ( (int)StringArrayCompareCaseInsensitive(
                            (wchar_t *const *)&v162[v164],
                            (wchar_t *const *)&v162[v163]) > 0 )
                {
                  v166 = v162[v164];
                  v162[v164] = v162[v163];
                  v162[v163] = v166;
                }
                ++v163;
              }
            }
            while ( v161 < v160 );
            v3 = *(_QWORD **)v183;
          }
          v167 = CCbsStringArray::SaveAsStringList((CCbsStringArray *)v207, L";", &v184);
          v7 = v167;
          if ( v167 >= 0 )
          {
            v168 = SczPublicAllocFromSz(&v196, v186, v184);
            v7 = v168;
            if ( v168 >= 0 )
            {
              Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v184);
              CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v207);
              CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v204);
              v74 = &pv;
              goto LABEL_183;
            }
            v149 = (unsigned int)v168;
            v148 = 514;
            goto LABEL_357;
          }
          LODWORD(v196) = v167;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"Out of memory");
            *(_QWORD *)v191 = &v196;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {}",
              (__int64)v191);
          }
          v148 = 512;
          goto LABEL_356;
        }
        v119 = -2146498549;
        LODWORD(v198) = -2146498549;
        if ( LogAdapter::g_Logger )
        {
          v155 = v205 + 3;
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            v205 + 3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Target image does not have required UUP metadata");
          *(_QWORD *)v191 = &v198;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            v155,
            (__int64)": {}",
            (__int64)v191);
        }
        v154 = 497;
      }
      else
      {
        LODWORD(v196) = v153;
        if ( LogAdapter::g_Logger )
        {
          *(_QWORD *)v191 = v152;
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (__int64)"Failed directory walk on {}",
            (__int64)v191);
          *(_QWORD *)v194 = &v196;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)v194);
        }
        v154 = 495;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v154,
        (unsigned int)"onecore\\base\\cbs\\core\\cbssessionproperties.cpp",
        (const char *)(unsigned int)v119,
        (int)v182);
      goto LABEL_365;
  }
  if ( a2 != 31 )
  {
LABEL_210:
    v7 = -2147024809;
    LODWORD(v196) = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LODWORD(v198) = a2;
      LogAdapter::Logger::LogNumObjects<long>(
        (_DWORD)LogAdapter::g_Logger,
        0,
        3,
        (unsigned int)"Invalid property query on session property: {}",
        (__int64)&v198);
      *(_QWORD *)v183 = &v196;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)v183);
    }
    v8 = 681;
    goto LABEL_9;
  }
  v193 = 0;
  v184 = 0;
  v190 = 0;
  pv = 0;
  CCbsStringArray::CCbsStringArray((CCbsStringArray *)v204);
  v187 = 0;
  v189 = 0;
  CCbsStringArray::CCbsStringArray((CCbsStringArray *)v210);
  v188 = 0;
  ImageProcessorArchitecture = CCbsSession::GetImageProcessorArchitecture((CCbsSession *)a1);
  ProcessorArchitectureString = GetProcessorArchitectureString(ImageProcessorArchitecture, (const wchar_t **)&v193);
  v7 = ProcessorArchitectureString;
  if ( ProcessorArchitectureString < 0 )
  {
    LODWORD(v196) = ProcessorArchitectureString;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get processor architecture string");
      *(_QWORD *)v183 = &v196;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)v183);
    }
    v85 = 532;
LABEL_217:
    v86 = v7;
LABEL_218:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v85,
      (unsigned int)"onecore\\base\\cbs\\core\\cbssessionproperties.cpp",
      (const char *)v86,
      (int)v182);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v188);
    CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v210);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v189);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v187);
    CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v204);
    goto LABEL_219;
  }
  TargetWindowsDirectory = CCbsSession::GetTargetWindowsDirectory((CCbsSession *)a1, &v184);
  v7 = TargetWindowsDirectory;
  if ( TargetWindowsDirectory < 0 )
  {
    LODWORD(v196) = TargetWindowsDirectory;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get target Windows directory");
      *(_QWORD *)v183 = &v196;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)v183);
    }
    v85 = 536;
    goto LABEL_217;
  }
  v88 = SczAllocCombinePath2Sz(&v190, v184, L"WinSxS");
  v7 = v88;
  if ( v88 < 0 )
  {
    v86 = (unsigned int)v88;
    v85 = 538;
    goto LABEL_218;
  }
  v90 = CCbsSession::CreateServicingQuerier(a1, v89, &pv);
  v7 = v90;
  if ( v90 < 0 )
  {
    LODWORD(v196) = v90;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to create servicing querier");
      *(_QWORD *)v183 = &v196;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)v183);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x21D,
      (unsigned int)"onecore\\base\\cbs\\core\\cbssessionproperties.cpp",
      (const char *)v7,
      (int)v182);
    goto LABEL_230;
  }
  CCbsInterfaceArray<ICbsSessionObserverListener *>::CCbsInterfaceArray<ICbsSessionObserverListener *>(v207);
  v91 = PackageStoreCollectPackages(a1, 112, v207);
  v7 = v91;
  if ( v91 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x225,
      (unsigned int)"onecore\\base\\cbs\\core\\cbssessionproperties.cpp",
      (const char *)(unsigned int)v91,
      (int)v182);
    goto LABEL_234;
  }
  CCbsArrayBase<CCbsIdentity *,CCbsInterfaceArray<CCbsIdentity *>>::Sort<int (*)(CCbsIdentity * const &,CCbsIdentity * const &)>(
    v207,
    ReversedCompareCCbsIdentity);
  v92 = v209;
  v199[0] = v199;
  v199[1] = v199;
  v199[2] = 0;
  v200 = 0;
  v201 = 2048;
  v93 = &v209[v208];
  while ( v92 != v93 )
  {
    v94 = *v92 + 30LL;
    v198 = v94;
    utl::_HashTable<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::vector<CCbsIdentity *,utl::allocator<CCbsIdentity *>>>,tlx::istring_hash_ascii,tlx::istring_equal_to_ascii,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::vector<CCbsIdentity *,utl::allocator<CCbsIdentity *>>>>,0>::find<wchar_t *>(
      (__int64)v199,
      &v185,
      &v198);
    v95 = v185;
    if ( (void **)v185.QuadPart == v199 )
    {
      v213[0] = 0;
      v212[0] = v213;
      v212[1] = v213;
      if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                               v212,
                               v94) )
      {
        v7 = -2147024882;
        LODWORD(v196) = -2147024882;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Out of memory");
          *(_QWORD *)v183 = &v196;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)v183);
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x234,
          (unsigned int)"onecore\\base\\cbs\\core\\cbssessionproperties.cpp",
          (const char *)0x8007000ELL,
          (int)v182);
        utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(v212);
        while ( 1 )
        {
          v106 = v199[0];
          if ( v199[0] == v199 )
            break;
          v107 = (_QWORD *)*((_QWORD *)v199[0] + 1);
          v108 = (char *)v199[0] + 24;
          v109 = *(_QWORD *)v199[0];
          *v107 = *(_QWORD *)v199[0];
          *(_QWORD *)(v109 + 8) = v107;
          utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::vector<CCbsIdentity *,utl::allocator<CCbsIdentity *>>>::~pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::vector<CCbsIdentity *,utl::allocator<CCbsIdentity *>>>(v108);
          operator delete(v106, (const struct std::nothrow_t *)&std::nothrow);
        }
        goto LABEL_264;
      }
      utl::_HashTable<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::vector<CCbsIdentity *,utl::allocator<CCbsIdentity *>>>,tlx::istring_hash_ascii,tlx::istring_equal_to_ascii,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::vector<CCbsIdentity *,utl::allocator<CCbsIdentity *>>>>,0>::_TryEmplace<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,>(
        (__int64)v199,
        (__int64)v191,
        (__int64)v212);
      if ( !v192 )
      {
        v7 = -2147024882;
        LODWORD(v196) = -2147024882;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Out of memory");
          *(_QWORD *)v183 = &v196;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)v183);
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x237,
          (unsigned int)"onecore\\base\\cbs\\core\\cbssessionproperties.cpp",
          (const char *)0x8007000ELL,
          (int)v182);
        utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(v212);
        while ( 1 )
        {
          v102 = v199[0];
          if ( v199[0] == v199 )
            break;
          v103 = (_QWORD *)*((_QWORD *)v199[0] + 1);
          v104 = (char *)v199[0] + 24;
          v105 = *(_QWORD *)v199[0];
          *v103 = *(_QWORD *)v199[0];
          *(_QWORD *)(v105 + 8) = v103;
          utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::vector<CCbsIdentity *,utl::allocator<CCbsIdentity *>>>::~pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::vector<CCbsIdentity *,utl::allocator<CCbsIdentity *>>>(v104);
          operator delete(v102, (const struct std::nothrow_t *)&std::nothrow);
        }
        goto LABEL_264;
      }
      v95 = *(union _ULARGE_INTEGER *)v191;
      v185 = *(union _ULARGE_INTEGER *)v191;
      utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(v212);
    }
    if ( !utl::vector<CCbsIdentity *,utl::allocator<CCbsIdentity *>>::_PushBackOne<CCbsIdentity * const &>(
            (__int64 *)(v95.QuadPart + 56),
            v92) )
    {
      v7 = -2147024882;
      LODWORD(v196) = -2147024882;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Out of memory");
        *(_QWORD *)v183 = &v196;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v183);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x23B,
        (unsigned int)"onecore\\base\\cbs\\core\\cbssessionproperties.cpp",
        (const char *)0x8007000ELL,
        (int)v182);
      while ( 1 )
      {
        v110 = v199[0];
        if ( v199[0] == v199 )
          break;
        v111 = (_QWORD *)*((_QWORD *)v199[0] + 1);
        v112 = (char *)v199[0] + 24;
        v113 = *(_QWORD *)v199[0];
        *v111 = *(_QWORD *)v199[0];
        *(_QWORD *)(v113 + 8) = v111;
        utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::vector<CCbsIdentity *,utl::allocator<CCbsIdentity *>>>::~pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::vector<CCbsIdentity *,utl::allocator<CCbsIdentity *>>>(v112);
        operator delete(v110, (const struct std::nothrow_t *)&std::nothrow);
      }
LABEL_264:
      v200 = 0;
LABEL_265:
      utl::_HashTable<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,CCbsSession::PlannedParentState>,tlx::istring_hash_ascii,tlx::istring_equal_to_ascii,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,CCbsSession::PlannedParentState>>,0>::_FreeBuckets(v199);
LABEL_234:
      CCbsArrayBase<CCbsIdentity *,CCbsInterfaceArray<CCbsIdentity *>>::~CCbsArrayBase<CCbsIdentity *,CCbsInterfaceArray<CCbsIdentity *>>(v207);
LABEL_230:
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v188);
      CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v210);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v189);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v187);
      CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v204);
      if ( pv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
LABEL_219:
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v190);
      p_pv = &v184;
LABEL_179:
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(p_pv);
      goto LABEL_71;
    }
    ++v92;
  }
  v96 = (__int64 *)off_1802E1430;
  do
  {
    v185.QuadPart = 0;
    v198 = 0;
    v97 = (struct CCbsIdentity **)Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v185);
    CbsIdentity = CreateCbsIdentity(v97);
    if ( CbsIdentity < 0 )
    {
      LODWORD(v196) = CbsIdentity;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to create cbs identity");
        *(_QWORD *)v191 = &v196;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v191);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x243,
        (unsigned int)"onecore\\base\\cbs\\core\\cbssessionproperties.cpp",
        (const char *)(unsigned int)CbsIdentity,
        (int)v182);
      Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v198);
      Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v185);
      while ( 1 )
      {
        v143 = v199[0];
        if ( v199[0] == v199 )
          break;
        v144 = (_QWORD *)*((_QWORD *)v199[0] + 1);
        v145 = (char *)v199[0] + 24;
        v146 = *(_QWORD *)v199[0];
        *v144 = *(_QWORD *)v199[0];
        *(_QWORD *)(v146 + 8) = v144;
        utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::vector<CCbsIdentity *,utl::allocator<CCbsIdentity *>>>::~pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::vector<CCbsIdentity *,utl::allocator<CCbsIdentity *>>>(v145);
        operator delete(v143, (const struct std::nothrow_t *)&std::nothrow);
      }
      goto LABEL_349;
    }
    LODWORD(v182) = 0;
    CbsIdentity = (*(__int64 (__fastcall **)(union _ULARGE_INTEGER, __int64, const wchar_t *, wchar_t *))(*(_QWORD *)v185.QuadPart + 48LL))(
                    v185,
                    *v96,
                    L"31bf3856ad364e35",
                    v193);
    if ( CbsIdentity < 0 )
    {
      LODWORD(v196) = CbsIdentity;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (__int64)"Failed to parse identity: {}",
          (__int64)v96);
        *(_QWORD *)v191 = &v196;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v191);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x24C,
        (unsigned int)"onecore\\base\\cbs\\core\\cbssessionproperties.cpp",
        (const char *)(unsigned int)CbsIdentity,
        (int)v182);
      Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v198);
      Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v185);
      while ( 1 )
      {
        v139 = v199[0];
        if ( v199[0] == v199 )
          break;
        v140 = (_QWORD *)*((_QWORD *)v199[0] + 1);
        v141 = (char *)v199[0] + 24;
        v142 = *(_QWORD *)v199[0];
        *v140 = *(_QWORD *)v199[0];
        *(_QWORD *)(v142 + 8) = v140;
        utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::vector<CCbsIdentity *,utl::allocator<CCbsIdentity *>>>::~pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::vector<CCbsIdentity *,utl::allocator<CCbsIdentity *>>>(v141);
        operator delete(v139, (const struct std::nothrow_t *)&std::nothrow);
      }
LABEL_349:
      v200 = 0;
      utl::_HashTable<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,CCbsSession::PlannedParentState>,tlx::istring_hash_ascii,tlx::istring_equal_to_ascii,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,CCbsSession::PlannedParentState>>,0>::_FreeBuckets(v199);
      CCbsArrayBase<CCbsIdentity *,CCbsInterfaceArray<CCbsIdentity *>>::~CCbsArrayBase<CCbsIdentity *,CCbsInterfaceArray<CCbsIdentity *>>(v207);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v188);
      CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v210);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v189);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v187);
      CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v204);
      if ( pv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v190);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v184);
      v7 = CbsIdentity;
      goto LABEL_71;
    }
    *(_QWORD *)v195 = v185.QuadPart + 30;
    utl::_HashTable<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::vector<CCbsIdentity *,utl::allocator<CCbsIdentity *>>>,tlx::istring_hash_ascii,tlx::istring_equal_to_ascii,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::vector<CCbsIdentity *,utl::allocator<CCbsIdentity *>>>>,0>::find<wchar_t *>(
      (__int64)v199,
      v194,
      v195);
    if ( *(void ***)v194 != v199 )
    {
      v99 = *(const struct CCbsIdentity ***)(*(_QWORD *)v194 + 56LL);
      v100 = *(const struct CCbsIdentity ***)(*(_QWORD *)v194 + 64LL);
      while ( v99 != v100 )
      {
        v101 = *v99;
        v195[0] = 4096;
        CbsIdentity = PackageStoreQueryPackageAttributes(
                        (struct CCbsSession *)a1,
                        v101,
                        (enum CbsState *)v195,
                        0,
                        &v187,
                        0);
        if ( CbsIdentity < 0 )
        {
          LODWORD(v196) = CbsIdentity;
          if ( LogAdapter::g_Logger )
          {
            *(_QWORD *)v194 = GetFastCbsIdentityString(*v99);
            LogAdapter::Logger::LogNumObjects<wchar_t const *>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (__int64)"Failed to call PackageStoreQueryPackageAttributes for package: {}",
              (__int64)v194);
            *(_QWORD *)v183 = &v196;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {}",
              (__int64)v183);
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x263,
            (unsigned int)"onecore\\base\\cbs\\core\\cbssessionproperties.cpp",
            (const char *)(unsigned int)CbsIdentity,
            (int)v182);
          Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v198);
          Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v185);
          while ( 1 )
          {
            v126 = v199[0];
            if ( v199[0] == v199 )
              break;
            v127 = (_QWORD *)*((_QWORD *)v199[0] + 1);
            v128 = (char *)v199[0] + 24;
            v129 = *(_QWORD *)v199[0];
            *v127 = *(_QWORD *)v199[0];
            *(_QWORD *)(v129 + 8) = v127;
            utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::vector<CCbsIdentity *,utl::allocator<CCbsIdentity *>>>::~pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::vector<CCbsIdentity *,utl::allocator<CCbsIdentity *>>>(v128);
            operator delete(v126, (const struct std::nothrow_t *)&std::nothrow);
          }
          goto LABEL_349;
        }
        if ( v195[0] == 64 || v195[0] == 112 || v195[0] == 128 )
        {
          Windows::AutoComPtr<CCbsPublicSession>::TakeReference(&v198, *v99);
          *(_QWORD *)v195 = v187;
          v114 = CCbsArrayBase<wchar_t *,CCbsStringArray>::Add(v204, v195);
          v7 = v114;
          if ( v114 >= 0 )
          {
            v187 = 0;
            break;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x26D,
            (unsigned int)"onecore\\base\\cbs\\core\\cbssessionproperties.cpp",
            (const char *)(unsigned int)v114,
            (int)v182);
          Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v198);
          Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v185);
          utl::_HashTable<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::vector<CCbsIdentity *,utl::allocator<CCbsIdentity *>>>,tlx::istring_hash_ascii,tlx::istring_equal_to_ascii,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::vector<CCbsIdentity *,utl::allocator<CCbsIdentity *>>>>,0>::_ClearList(v199);
          goto LABEL_265;
        }
        ++v99;
      }
    }
    Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v198);
    Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v185);
    ++v96;
  }
  while ( v96 != ___LiteralObject__2U__BaseLiteralBuffer__06U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0EN__0GB__0GJ__0GO__0EP__0FD__0A_____0A__00_01_02_03_04_05_Details_RtlStringLiterals__3U_LUTF8_STRING__B );
  v115 = v206;
  v116 = pv;
  v117.QuadPart = (ULONGLONG)&v206[v205];
  *(union _ULARGE_INTEGER *)v191 = v117;
  if ( v206 != (__int64 *)v117.QuadPart )
  {
    while ( 1 )
    {
      v118 = *v115;
      pv = 0;
      LOWORD(v195[0]) = 0;
      v182 = v195;
      v119 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64, LPVOID *))(*(_QWORD *)v116 + 48LL))(
               v116,
               1,
               v118,
               &pv);
      if ( v119 < 0 )
        break;
      v120 = (wchar_t *)pv;
      v193 = (wchar_t *)((char *)pv + 8 * LOWORD(v195[0]));
      if ( pv != v193 )
      {
        while ( 2 )
        {
          CCbsStringArray::CCbsStringArray((CCbsStringArray *)v214);
          v122 = SczAllocCombinePath2Sz(&v189, v190, *(_QWORD *)v120);
          if ( v122 < 0 )
          {
            LODWORD(v196) = v122;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                (__int64)LogAdapter::g_Logger,
                0,
                3,
                (__int64)"Failed to create path to component: {}",
                (__int64)v120);
              *(_QWORD *)v191 = &v196;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (__int64)LogAdapter::g_Logger,
                1,
                3,
                (__int64)": {}",
                (__int64)v191);
            }
            v134 = 649;
            goto LABEL_316;
          }
          v123 = v189;
          v122 = CbsEnumFiles(v121, v189, L"*.XML", v214);
          if ( v122 < 0 )
          {
            LODWORD(v196) = v122;
            if ( LogAdapter::g_Logger )
            {
              *(_QWORD *)v191 = v123;
              LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                (__int64)LogAdapter::g_Logger,
                0,
                3,
                (__int64)"Failed directory walk on {}",
                (__int64)v191);
              *(_QWORD *)v194 = &v196;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (__int64)LogAdapter::g_Logger,
                1,
                3,
                (__int64)": {}",
                (__int64)v194);
            }
            v134 = 654;
LABEL_316:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v134,
              (unsigned int)"onecore\\base\\cbs\\core\\cbssessionproperties.cpp",
              (const char *)(unsigned int)v122,
              (int)v182);
            CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v214);
            if ( pv )
            {
              CoTaskMemFree(pv);
              pv = 0;
            }
            utl::_HashTable<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::vector<CCbsIdentity *,utl::allocator<CCbsIdentity *>>>,tlx::istring_hash_ascii,tlx::istring_equal_to_ascii,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::vector<CCbsIdentity *,utl::allocator<CCbsIdentity *>>>>,0>::_ClearList(v199);
            utl::_HashTable<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,CCbsSession::PlannedParentState>,tlx::istring_hash_ascii,tlx::istring_equal_to_ascii,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,CCbsSession::PlannedParentState>>,0>::_FreeBuckets(v199);
            CCbsArrayBase<CCbsIdentity *,CCbsInterfaceArray<CCbsIdentity *>>::~CCbsArrayBase<CCbsIdentity *,CCbsInterfaceArray<CCbsIdentity *>>(v207);
            Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v188);
            CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v210);
            Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v189);
            Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v187);
            CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v204);
            if ( v116 )
              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v116 + 16LL))(v116);
            Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v190);
            Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v184);
            v7 = v122;
            goto LABEL_71;
          }
          v124 = v216;
          v125 = &v216[v215];
          while ( v124 != v125 )
          {
            v130 = *v124;
            v198 = 0;
            v131 = SczAllocCombinePath2Sz(&v198, v123, v130);
            if ( v131 < 0 )
            {
              LODWORD(v196) = v131;
              if ( LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                  (__int64)LogAdapter::g_Logger,
                  0,
                  3,
                  (__int64)"Failed to create path to component file: {}",
                  (__int64)v124);
                *(_QWORD *)v191 = &v196;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  (__int64)LogAdapter::g_Logger,
                  1,
                  3,
                  (__int64)": {}",
                  (__int64)v191);
              }
              v133 = 661;
              goto LABEL_305;
            }
            *(_QWORD *)v194 = v198;
            v131 = CCbsArrayBase<wchar_t *,CCbsStringArray>::Add(v210, v194);
            if ( v131 < 0 )
            {
              v133 = 663;
LABEL_305:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v133,
                (unsigned int)"onecore\\base\\cbs\\core\\cbssessionproperties.cpp",
                (const char *)(unsigned int)v131,
                (int)v182);
              Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v198);
              CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v214);
              if ( pv )
              {
                CoTaskMemFree(pv);
                pv = 0;
              }
              utl::_HashTable<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::vector<CCbsIdentity *,utl::allocator<CCbsIdentity *>>>,tlx::istring_hash_ascii,tlx::istring_equal_to_ascii,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::vector<CCbsIdentity *,utl::allocator<CCbsIdentity *>>>>,0>::_ClearList(v199);
              utl::_HashTable<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,CCbsSession::PlannedParentState>,tlx::istring_hash_ascii,tlx::istring_equal_to_ascii,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,CCbsSession::PlannedParentState>>,0>::_FreeBuckets(v199);
              CCbsArrayBase<CCbsIdentity *,CCbsInterfaceArray<CCbsIdentity *>>::~CCbsArrayBase<CCbsIdentity *,CCbsInterfaceArray<CCbsIdentity *>>(v207);
              Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v188);
              CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v210);
              Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v189);
              Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v187);
              CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v204);
              if ( v116 )
                (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v116 + 16LL))(v116);
              Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v190);
              Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v184);
              v7 = v131;
              goto LABEL_71;
            }
            v198 = 0;
            Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v198);
            ++v124;
          }
          CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v214);
          v120 += 4;
          if ( v120 != v193 )
            continue;
          break;
        }
        v120 = (wchar_t *)pv;
        v117 = *(union _ULARGE_INTEGER *)v191;
      }
      if ( v120 )
      {
        CoTaskMemFree(v120);
        pv = 0;
      }
      if ( ++v115 == (__int64 *)v117.QuadPart )
      {
        v3 = *(_QWORD **)v183;
        goto LABEL_296;
      }
    }
    LODWORD(v196) = v119;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (__int64)"Failed to query components of package manifest: {}",
        (__int64)v115);
      *(_QWORD *)v191 = &v196;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)v191);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x280,
      (unsigned int)"onecore\\base\\cbs\\core\\cbssessionproperties.cpp",
      (const char *)(unsigned int)v119,
      (int)v182);
    if ( pv )
    {
      CoTaskMemFree(pv);
      pv = 0;
    }
    goto LABEL_325;
  }
LABEL_296:
  if ( !v211 )
  {
    v119 = -2146498549;
    LODWORD(v198) = -2146498549;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Target image does not have required UUP metadata");
      *(_QWORD *)v191 = &v198;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)v191);
    }
    v132 = 669;
LABEL_300:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v132,
      (unsigned int)"onecore\\base\\cbs\\core\\cbssessionproperties.cpp",
      (const char *)(unsigned int)v119,
      (int)v182);
LABEL_325:
    utl::_HashTable<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::vector<CCbsIdentity *,utl::allocator<CCbsIdentity *>>>,tlx::istring_hash_ascii,tlx::istring_equal_to_ascii,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::vector<CCbsIdentity *,utl::allocator<CCbsIdentity *>>>>,0>::_ClearList(v199);
    utl::_HashTable<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,CCbsSession::PlannedParentState>,tlx::istring_hash_ascii,tlx::istring_equal_to_ascii,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,CCbsSession::PlannedParentState>>,0>::_FreeBuckets(v199);
    CCbsArrayBase<CCbsIdentity *,CCbsInterfaceArray<CCbsIdentity *>>::~CCbsArrayBase<CCbsIdentity *,CCbsInterfaceArray<CCbsIdentity *>>(v207);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v188);
    CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v210);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v189);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v187);
    CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v204);
    if ( v116 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v116 + 16LL))(v116);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v190);
    v135 = &v184;
    goto LABEL_366;
  }
  CCbsArrayBase<wchar_t *,CCbsStringArray>::Sort<int (*)(wchar_t * const &,wchar_t * const &)>(v210);
  v136 = CCbsStringArray::SaveAsStringList((CCbsStringArray *)v210, L";", &v188);
  v119 = v136;
  if ( v136 < 0 )
  {
    LODWORD(v196) = v136;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Out of memory");
      *(_QWORD *)v191 = &v196;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)v191);
    }
    v132 = 674;
    goto LABEL_300;
  }
  v137 = SczPublicAllocFromSz(&v196, v186, v188);
  v138 = v137;
  if ( v137 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2A4,
      (unsigned int)"onecore\\base\\cbs\\core\\cbssessionproperties.cpp",
      (const char *)(unsigned int)v137,
      (int)v182);
    utl::_HashTable<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::vector<CCbsIdentity *,utl::allocator<CCbsIdentity *>>>,tlx::istring_hash_ascii,tlx::istring_equal_to_ascii,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::vector<CCbsIdentity *,utl::allocator<CCbsIdentity *>>>>,0>::_ClearList(v199);
    utl::_HashTable<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,CCbsSession::PlannedParentState>,tlx::istring_hash_ascii,tlx::istring_equal_to_ascii,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,CCbsSession::PlannedParentState>>,0>::_FreeBuckets(v199);
    CCbsArrayBase<CCbsIdentity *,CCbsInterfaceArray<CCbsIdentity *>>::~CCbsArrayBase<CCbsIdentity *,CCbsInterfaceArray<CCbsIdentity *>>(v207);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v188);
    CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v210);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v189);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v187);
    CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v204);
    if ( v116 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v116 + 16LL))(v116);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v190);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v184);
    v7 = v138;
    goto LABEL_71;
  }
  utl::_HashTable<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::vector<CCbsIdentity *,utl::allocator<CCbsIdentity *>>>,tlx::istring_hash_ascii,tlx::istring_equal_to_ascii,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::vector<CCbsIdentity *,utl::allocator<CCbsIdentity *>>>>,0>::_ClearList(v199);
  utl::_HashTable<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,CCbsSession::PlannedParentState>,tlx::istring_hash_ascii,tlx::istring_equal_to_ascii,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,CCbsSession::PlannedParentState>>,0>::_FreeBuckets(v199);
  CCbsArrayBase<CCbsIdentity *,CCbsInterfaceArray<CCbsIdentity *>>::~CCbsArrayBase<CCbsIdentity *,CCbsInterfaceArray<CCbsIdentity *>>(v207);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v188);
  CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v210);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v189);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v187);
  CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v204);
  if ( v116 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v116 + 16LL))(v116);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v190);
  v74 = &v184;
LABEL_183:
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(v74);
LABEL_70:
  v7 = 0;
  *v3 = v196;
LABEL_71:
  Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v186);
  return v7;
}

```

## disassembly

```asm
0x1801c4b98  mov     [rsp-8+arg_18], rbx
0x1801c4b9d  push    rbp
0x1801c4b9e  push    rsi
0x1801c4b9f  push    rdi
0x1801c4ba0  push    r12
0x1801c4ba2  push    r13
0x1801c4ba4  push    r14
0x1801c4ba6  push    r15
0x1801c4ba8  lea     rbp, [rsp-170h]
0x1801c4bb0  sub     rsp, 270h
0x1801c4bb7  mov     rax, cs:__security_cookie
0x1801c4bbe  xor     rax, rsp
0x1801c4bc1  mov     [rbp+1A0h+var_40], rax
0x1801c4bc8  xor     r13d, r13d
0x1801c4bcb  mov     qword ptr [rsp+2A0h+var_260], r8
0x1801c4bd0  mov     r12, r8
0x1801c4bd3  mov     [rbp+1A0h+var_1F8], r13
0x1801c4bd7  mov     edi, edx
0x1801c4bd9  mov     [rsp+2A0h+var_248], r13
0x1801c4bde  mov     rsi, rcx
0x1801c4be1  xor     edx, edx; Val
0x1801c4be3  lea     r8d, [r13+40h]; Size
0x1801c4be7  lea     rcx, [rbp+1A0h+var_80]; void *
0x1801c4bee  call    memset_0
0x1801c4bf3  mov     rcx, rsi; this
0x1801c4bf6  call    ?CheckInitialized@CCbsSession@@QEAAJXZ; CCbsSession::CheckInitialized(void)
0x1801c4bfb  mov     ebx, eax
0x1801c4bfd  test    eax, eax
0x1801c4bff  jns     short loc_1801C4C57
0x1801c4c01  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801c4c08  mov     [rbp+1A0h+var_200], eax
0x1801c4c0b  test    rcx, rcx
0x1801c4c0e  jz      short loc_1801C4C50
0x1801c4c10  lea     edi, [r13+3]
0x1801c4c14  xor     edx, edx
0x1801c4c16  mov     r8d, edi
0x1801c4c19  lea     r9, aCannotGetsessi; "Cannot GetSessionID on a session that h"...
0x1801c4c20  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801c4c25  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801c4c2c  lea     rax, [rbp+1A0h+var_200]
0x1801c4c30  mov     qword ptr [rsp+2A0h+var_260], rax
0x1801c4c35  lea     r9, asc_1802EE7AC; ": {}"
0x1801c4c3c  lea     rax, [rsp+2A0h+var_260]
0x1801c4c41  mov     r8d, edi
0x1801c4c44  mov     dl, 1
0x1801c4c46  mov     [rsp+2A0h+var_280], rax
0x1801c4c4b  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801c4c50  mov     edx, 6Ch ; 'l'
0x1801c4c55  jmp     short loc_1801C4CC4
0x1801c4c57  lea     rcx, [rsp+2A0h+var_248]
0x1801c4c5c  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseBcdStore@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&CloseBcdStore(void *)>>::GetInitPointer(void)
0x1801c4c61  mov     rcx, rax
0x1801c4c64  call    GetTaskAllocator
0x1801c4c69  mov     ebx, eax
0x1801c4c6b  test    eax, eax
0x1801c4c6d  jns     short loc_1801C4CDF
0x1801c4c6f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801c4c76  mov     [rbp+1A0h+var_200], eax
0x1801c4c79  test    rcx, rcx
0x1801c4c7c  jz      short loc_1801C4CBF
0x1801c4c7e  mov     edi, 3
0x1801c4c83  lea     r9, aFailedToGetTas; "Failed to get task allocator."
0x1801c4c8a  mov     r8d, edi
0x1801c4c8d  xor     edx, edx
0x1801c4c8f  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801c4c94  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801c4c9b  lea     rax, [rbp+1A0h+var_200]
0x1801c4c9f  mov     qword ptr [rsp+2A0h+var_260], rax
0x1801c4ca4  lea     r9, asc_1802EE7AC; ": {}"
0x1801c4cab  lea     rax, [rsp+2A0h+var_260]
0x1801c4cb0  mov     r8d, edi
0x1801c4cb3  mov     dl, 1
0x1801c4cb5  mov     [rsp+2A0h+var_280], rax; int
0x1801c4cba  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801c4cbf  mov     edx, 6Dh ; 'm'; void *
0x1801c4cc4  mov     r9d, ebx; char *
0x1801c4cc7  mov     rcx, [rbp+1A8h]; this
0x1801c4cce  lea     r8, aOnecoreBaseCbs_67; "onecore\\base\\cbs\\core\\cbssessionpro"...
0x1801c4cd5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801c4cda  jmp     loc_1801C5090
0x1801c4cdf  cmp     edi, 0Dh
0x1801c4ce2  jg      loc_1801C4D8F
0x1801c4ce8  jz      short loc_1801C4D09
0x1801c4cea  mov     ecx, edi
0x1801c4cec  sub     ecx, 8
0x1801c4cef  jz      short loc_1801C4D09
0x1801c4cf1  sub     ecx, 1
0x1801c4cf4  jz      short loc_1801C4D09
0x1801c4cf6  sub     ecx, 1
0x1801c4cf9  jz      short loc_1801C4D09
0x1801c4cfb  sub     ecx, 1
0x1801c4cfe  jz      short loc_1801C4D09
0x1801c4d00  cmp     ecx, 1
0x1801c4d03  jnz     loc_1801C4E29
0x1801c4d09  cmp     [rsi+4D0h], r13
0x1801c4d10  jnz     loc_1801C4E1A
0x1801c4d16  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801c4d1d  test    rcx, rcx
0x1801c4d20  jz      short loc_1801C4D6A
0x1801c4d22  mov     edi, 3
0x1801c4d27  lea     r9, aFailedGettingP_0; "Failed getting property.  Analysis must"...
0x1801c4d2e  mov     r8d, edi
0x1801c4d31  xor     edx, edx
0x1801c4d33  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801c4d38  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801c4d3f  lea     rax, [rbp+1A0h+var_200]
0x1801c4d43  mov     qword ptr [rsp+2A0h+var_260], rax
0x1801c4d48  lea     r9, a0; ": {0}"
0x1801c4d4f  lea     rax, [rsp+2A0h+var_260]
0x1801c4d54  mov     [rbp+1A0h+var_200], 80070490h
0x1801c4d5b  mov     r8d, edi
0x1801c4d5e  mov     [rsp+2A0h+var_280], rax; unsigned int
0x1801c4d63  mov     dl, 1
0x1801c4d65  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801c4d6a  mov     r9d, 490h; char *
0x1801c4d70  mov     edx, 7Eh ; '~'; void *
0x1801c4d75  mov     rcx, [rbp+1A8h]; this
0x1801c4d7c  lea     r8, aOnecoreBaseCbs_67; "onecore\\base\\cbs\\core\\cbssessionpro"...
0x1801c4d83  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1801c4d88  mov     ebx, eax
0x1801c4d8a  jmp     loc_1801C5090
0x1801c4d8f  mov     ecx, edi
0x1801c4d91  sub     ecx, 0Eh
0x1801c4d94  jz      loc_1801C4D09
0x1801c4d9a  sub     ecx, 1
0x1801c4d9d  jz      short loc_1801C4DAE
0x1801c4d9f  sub     ecx, 8
0x1801c4da2  jz      short loc_1801C4DAE
0x1801c4da4  sub     ecx, 1
0x1801c4da7  jz      short loc_1801C4DAE
0x1801c4da9  cmp     ecx, 1
0x1801c4dac  jnz     short loc_1801C4E1A
0x1801c4dae  cmp     [rsi+40Ch], r13d
0x1801c4db5  jnz     short loc_1801C4E1A
0x1801c4db7  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801c4dbe  test    rcx, rcx
0x1801c4dc1  jz      short loc_1801C4E0B
0x1801c4dc3  mov     edi, 3
0x1801c4dc8  lea     r9, aFailedGettingP_9; "Failed getting property. Session must b"...
0x1801c4dcf  mov     r8d, edi
0x1801c4dd2  xor     edx, edx
0x1801c4dd4  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801c4dd9  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801c4de0  lea     rax, [rbp+1A0h+var_200]
0x1801c4de4  mov     qword ptr [rsp+2A0h+var_260], rax
0x1801c4de9  lea     r9, a0; ": {0}"
0x1801c4df0  lea     rax, [rsp+2A0h+var_260]
0x1801c4df5  mov     [rbp+1A0h+var_200], 80070032h
0x1801c4dfc  mov     r8d, edi
0x1801c4dff  mov     [rsp+2A0h+var_280], rax
0x1801c4e04  mov     dl, 1
0x1801c4e06  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801c4e0b  mov     r9d, 32h ; '2'
0x1801c4e11  lea     edx, [r9+56h]
0x1801c4e15  jmp     loc_1801C4D75
0x1801c4e1a  cmp     edi, 10h
0x1801c4e1d  jg      loc_1801C5839
0x1801c4e23  jz      loc_1801C5BEF
0x1801c4e29  cmp     edi, 8
0x1801c4e2c  jg      loc_1801C5172
0x1801c4e32  jz      loc_1801C50C7
0x1801c4e38  mov     ecx, edi
0x1801c4e3a  sub     ecx, 1
0x1801c4e3d  jz      loc_1801C5013
0x1801c4e43  sub     ecx, 1
0x1801c4e46  jz      loc_1801C4FD0
0x1801c4e4c  sub     ecx, 1
0x1801c4e4f  jz      loc_1801C4F77
0x1801c4e55  sub     ecx, 1
0x1801c4e58  jz      loc_1801C4F4B
0x1801c4e5e  sub     ecx, 1
0x1801c4e61  jz      loc_1801C4F01
0x1801c4e67  sub     ecx, 1
0x1801c4e6a  jz      short loc_1801C4EA1
0x1801c4e6c  cmp     ecx, 1
0x1801c4e6f  jnz     loc_1801C5E72
0x1801c4e75  mov     rdx, [rsp+2A0h+var_248]
0x1801c4e7a  lea     r8, a0_1; "0"
0x1801c4e81  lea     rcx, [rbp+1A0h+var_1F8]
0x1801c4e85  call    SczPublicAllocFromSz
0x1801c4e8a  mov     ebx, eax
0x1801c4e8c  test    eax, eax
0x1801c4e8e  jns     loc_1801C5085
0x1801c4e94  mov     r9d, eax
0x1801c4e97  mov     edx, 0C8h
0x1801c4e9c  jmp     loc_1801C4CC7
0x1801c4ea1  lea     r8, [rbp+1A0h+var_200]; int *
0x1801c4ea5  mov     [rbp+1A0h+var_200], r13d
0x1801c4ea9  xor     edx, edx; int
0x1801c4eab  mov     rcx, rsi; struct CCbsSession *
0x1801c4eae  call    ?CheckStoreCorruptionFlag@@YAJPEAVCCbsSession@@HPEAH@Z; CheckStoreCorruptionFlag(CCbsSession *,int,int *)
0x1801c4eb3  lea     r8, aUnableToGetand; "Unable to GetAndResetCorruptionFlag"
0x1801c4eba  mov     edx, eax
0x1801c4ebc  mov     ecx, 1
0x1801c4ec1  call    ??$TraceAtLevelIfFailed@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelIfFailed<long,>(LogAdapter::LogLevel,long,char const * const)
0x1801c4ec6  cmp     [rbp+1A0h+var_200], r13d
0x1801c4eca  lea     rcx, a0_1; "0"
0x1801c4ed1  mov     rdx, [rsp+2A0h+var_248]
0x1801c4ed6  lea     r8, a1; "1"
0x1801c4edd  cmovz   r8, rcx
0x1801c4ee1  lea     rcx, [rbp+1A0h+var_1F8]
0x1801c4ee5  call    SczPublicAllocFromSz
0x1801c4eea  mov     ebx, eax
0x1801c4eec  test    eax, eax
0x1801c4eee  jns     loc_1801C5085
0x1801c4ef4  mov     r9d, eax
0x1801c4ef7  mov     edx, 0C2h
0x1801c4efc  jmp     loc_1801C4CC7
0x1801c4f01  lea     rdx, [rsi+248h]; struct AutoCritSec *
0x1801c4f08  mov     r8b, 1; bool
0x1801c4f0b  lea     rcx, [rbp+1A0h+var_1B8]; this
0x1801c4f0f  call    ??0CritSecLocker@@QEAA@AEAVAutoCritSec@@_N@Z; CritSecLocker::CritSecLocker(AutoCritSec &,bool)
0x1801c4f14  mov     rax, [rsi+460h]
0x1801c4f1b  lea     r8, qword_1802EB518
0x1801c4f22  mov     rdx, [rsp+2A0h+var_248]
0x1801c4f27  lea     rcx, [rbp+1A0h+var_1F8]
0x1801c4f2b  test    rax, rax
0x1801c4f2e  cmovnz  r8, rax
0x1801c4f32  call    SczPublicAllocFromSz
0x1801c4f37  mov     ebx, eax
0x1801c4f39  test    eax, eax
0x1801c4f3b  jns     loc_1801C507C
0x1801c4f41  mov     edx, 0B6h
0x1801c4f46  jmp     loc_1801C505B
0x1801c4f4b  mov     rdx, [rsp+2A0h+var_248]
0x1801c4f50  lea     r8, a1; "1"
0x1801c4f57  lea     rcx, [rbp+1A0h+var_1F8]
0x1801c4f5b  call    SczPublicAllocFromSz
0x1801c4f60  mov     ebx, eax
0x1801c4f62  test    eax, eax
0x1801c4f64  jns     loc_1801C5085
0x1801c4f6a  mov     r9d, eax
0x1801c4f6d  mov     edx, 0AFh
0x1801c4f72  jmp     loc_1801C4CC7
0x1801c4f77  lea     r8, [rbp+1A0h+var_200]; unsigned int *
0x1801c4f7b  mov     [rbp+1A0h+var_200], r13d
0x1801c4f7f  lea     rdx, aUnserviceable; "Unserviceable"
0x1801c4f86  mov     rcx, rsi; struct CCbsSession *
0x1801c4f89  call    ?PackageStoreGetProperty@@YAJPEAVCCbsSession@@PEB_WPEAK@Z; PackageStoreGetProperty(CCbsSession *,wchar_t const *,ulong *)
0x1801c4f8e  mov     edx, [rbp+1A0h+var_200]
0x1801c4f91  lea     rcx, a0_1; "0"
0x1801c4f98  test    eax, eax
0x1801c4f9a  lea     r8, a1; "1"
0x1801c4fa1  cmovs   edx, r13d
0x1801c4fa5  test    edx, edx
0x1801c4fa7  mov     rdx, [rsp+2A0h+var_248]
0x1801c4fac  cmovz   r8, rcx
0x1801c4fb0  lea     rcx, [rbp+1A0h+var_1F8]
0x1801c4fb4  call    SczPublicAllocFromSz
0x1801c4fb9  mov     ebx, eax
0x1801c4fbb  test    eax, eax
0x1801c4fbd  jns     loc_1801C5085
0x1801c4fc3  mov     r9d, eax
0x1801c4fc6  mov     edx, 0A6h
0x1801c4fcb  jmp     loc_1801C4CC7
0x1801c4fd0  lea     rdx, [rsi+248h]; struct AutoCritSec *
0x1801c4fd7  mov     r8b, 1; bool
0x1801c4fda  lea     rcx, [rbp+1A0h+var_1B8]; this
0x1801c4fde  call    ??0CritSecLocker@@QEAA@AEAVAutoCritSec@@_N@Z; CritSecLocker::CritSecLocker(AutoCritSec &,bool)
0x1801c4fe3  mov     rax, [rsi+430h]
0x1801c4fea  lea     r8, qword_1802EB518
0x1801c4ff1  mov     rdx, [rsp+2A0h+var_248]
0x1801c4ff6  lea     rcx, [rbp+1A0h+var_1F8]
0x1801c4ffa  test    rax, rax
0x1801c4ffd  cmovnz  r8, rax
0x1801c5001  call    SczPublicAllocFromSz
0x1801c5006  mov     ebx, eax
0x1801c5008  test    eax, eax
0x1801c500a  jns     short loc_1801C507C
0x1801c500c  mov     edx, 9Bh
0x1801c5011  jmp     short loc_1801C505B
0x1801c5013  lea     rdx, [rsi+248h]; struct AutoCritSec *
0x1801c501a  mov     r8b, 1; bool
0x1801c501d  lea     rcx, [rbp+1A0h+var_1B8]; this
0x1801c5021  call    ??0CritSecLocker@@QEAA@AEAVAutoCritSec@@_N@Z; CritSecLocker::CritSecLocker(AutoCritSec &,bool)
0x1801c5026  mov     rcx, rsi; this
0x1801c5029  call    ?IsRebootRequired@CCbsSession@@AEAAHXZ; CCbsSession::IsRebootRequired(void)
0x1801c502e  mov     rdx, [rsp+2A0h+var_248]
0x1801c5033  lea     rcx, a0_1; "0"
0x1801c503a  test    eax, eax
0x1801c503c  lea     r8, a1; "1"
0x1801c5043  cmovz   r8, rcx
0x1801c5047  lea     rcx, [rbp+1A0h+var_1F8]
0x1801c504b  call    SczPublicAllocFromSz
0x1801c5050  mov     ebx, eax
0x1801c5052  test    eax, eax
0x1801c5054  jns     short loc_1801C507C
0x1801c5056  mov     edx, 94h; void *
0x1801c505b  mov     r9d, eax; char *
0x1801c505e  mov     rcx, [rbp+1A8h]; this
0x1801c5065  lea     r8, aOnecoreBaseCbs_67; "onecore\\base\\cbs\\core\\cbssessionpro"...
0x1801c506c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801c5071  lea     rcx, [rbp+1A0h+var_1B8]; this
0x1801c5075  call    ??1CritSecLocker@@UEAA@XZ; CritSecLocker::~CritSecLocker(void)
0x1801c507a  jmp     short loc_1801C5090
0x1801c507c  lea     rcx, [rbp+1A0h+var_1B8]; this
0x1801c5080  call    ??1CritSecLocker@@UEAA@XZ; CritSecLocker::~CritSecLocker(void)
0x1801c5085  mov     rax, [rbp+1A0h+var_1F8]
0x1801c5089  mov     ebx, r13d
0x1801c508c  mov     [r12], rax
  ... truncated ...
```
