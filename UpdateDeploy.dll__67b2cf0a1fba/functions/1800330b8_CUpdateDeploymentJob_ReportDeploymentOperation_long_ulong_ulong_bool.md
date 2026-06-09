# CUpdateDeploymentJob::ReportDeploymentOperation(long,ulong,ulong,bool)

- ea: `0x1800330b8`
- end: `0x1800357a3`
- name: `?ReportDeploymentOperation@CUpdateDeploymentJob@@AEAAXJKK_N@Z`
- size: `9963`
- prototype: `void __fastcall(CUpdateDeploymentJob *__hidden this, int, unsigned int, unsigned int, bool)`
- caller_count: `5`
- callee_count: `57`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180029fac`
- `0x18002a280`
- `0x18002a674`
- `0x18002a868`
- `0x18002aa98`

## callees

- `0x180003180`
- `0x180007b6c`
- `0x180008ab8`
- `0x180008f5c`
- `0x1800091cc`
- `0x18000c30c`
- `0x18000cd48`
- `0x18000dce4`
- `0x18000dd60`
- `0x1800110fc`
- `0x180011b44`
- `0x180011bf0`
- `0x180012358`
- `0x180012694`
- `0x180013ee0`
- `0x18001422c`
- `0x180018ac8`
- `0x180018e40`
- `0x18001d408`
- `0x180020958`
- `0x180020a40`
- `0x180020b5c`
- `0x180020bfc`
- `0x180020c50`
- `0x180020e40`
- `0x180020fe8`
- `0x1800217c8`
- `0x180021b90`
- `0x1800223e0`
- `0x180022478`
- `0x18002250c`
- `0x1800225a4`
- `0x180022790`
- `0x180024fd8`
- `0x1800283c8`
- `0x18002be38`
- `0x1800330b8`
- `0x1800357ac`
- `0x18003597c`
- `0x1800359e0`
- `0x18003672c`
- `0x180037200`
- `0x180037d28`
- `0x1800475f4`
- `0x18004763c`
- `0x1800476fc`
- `0x1800482f0`
- `0x18004e830`
- `0x18004e9e4`
- `0x18004ea88`

## import_xrefs

- `RPCRT4!UuidFromStringW` at `0x1800341f0`
- `RPCRT4!UuidFromStringW` at `0x180034264`
- `RPCRT4!UuidFromStringW` at `0x180034fa3`
- `RPCRT4!UuidFromStringW` at `0x1800341f0`
- `RPCRT4!UuidFromStringW` at `0x180034264`
- `RPCRT4!UuidFromStringW` at `0x180034fa3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800343ef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800343ef`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180033882`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180033882`
- `OLEAUT32!__imp_SysAllocString` at `0x180033cd1`
- `OLEAUT32!__imp_SysAllocString` at `0x180034e32`
- `OLEAUT32!__imp_SysAllocString` at `0x180033cd1`
- `OLEAUT32!__imp_SysAllocString` at `0x180034e32`
- `OLEAUT32!__imp_SysFreeString` at `0x18003568d`
- `OLEAUT32!__imp_SysFreeString` at `0x18003568d`
- `OLEAUT32!__imp_SysStringLen` at `0x180033b07`
- `OLEAUT32!__imp_SysStringLen` at `0x180033b38`
- `OLEAUT32!__imp_SysStringLen` at `0x180033b07`
- `OLEAUT32!__imp_SysStringLen` at `0x180033b38`
- `OLEAUT32!__imp_SysStringByteLen` at `0x1800355ab`
- `OLEAUT32!__imp_SysStringByteLen` at `0x1800355ef`
- `OLEAUT32!__imp_SysStringByteLen` at `0x1800355ab`
- `OLEAUT32!__imp_SysStringByteLen` at `0x1800355ef`

## string_xrefs

- `0x18003385c`: `http://schemas.microsoft.com/msus/2016/01/UpdateHandlers/OSInstaller`
- `0x1800348bc`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\DPReportingData.cpp`
- `0x180035302`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\DPReportingData.cpp`
- `0x180033da0`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\UpdateDeploymentJob.cpp`
- `0x180034ebd`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\UpdateDeploymentJob.cpp`
- `0x1800356c7`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\UpdateDeploymentJob.cpp`
- `0x1800339e9`: `IDP Child Update`
- `0x1800347a9`: `Deployment job Id %ws : Deployment provider reports pending update`
- `0x1800340f8`: `Fail to get update metadata for deployment reporting events.`
- `0x1800349ec`: `Deployment job Id %ws : UDP reports a child update deployment`
- `0x1800348ec`: `Deployment job Id %ws : UDP queues a child update for post-reboot reporting`
- `0x180035578`: `Deployment job Id %ws : Failed to write deployment status cookie bstr`
- `0x180035529`: `Deployment job Id %ws : Failed to serialize pending update group`
- `0x18003565d`: `Deployment job Id %ws : Failed to copy and attach deployment status cookie bstr to update : %ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=25
void __fastcall CUpdateDeploymentJob::ReportDeploymentOperation(
        struct _GUID *this,
        int a2,
        int a3,
        unsigned int a4,
        bool a5)
{
  int v6; // esi
  _QWORD *v8; // r15
  unsigned int v9; // r13d
  const wchar_t *v10; // r14
  __int64 v11; // rbx
  TraceLoggingCorrelationVector *v12; // rcx
  volatile signed __int64 *v13; // rcx
  __int64 v14; // rdi
  void (__fastcall *v15)(__int64, void **); // rsi
  __int64 v16; // r8
  BOOL v17; // ecx
  int v18; // ecx
  int v19; // r12d
  _BOOL8 v20; // rcx
  unsigned int v21; // esi
  __int16 v22; // ax
  CUpdateDeploymentJob *v23; // r13
  int v24; // ecx
  wchar_t **v25; // rax
  wchar_t **v26; // rdi
  bool v27; // zf
  int v28; // eax
  bool IsPauseQualityUpdateEnabled; // al
  bool IsPauseFeatureUpdateEnabled; // al
  int v31; // eax
  unsigned int v32; // eax
  __int64 v33; // rdx
  const wchar_t *v34; // r10
  int v35; // r10d
  wchar_t **v36; // rax
  wchar_t **v37; // rcx
  unsigned int v38; // edx
  int v39; // eax
  unsigned int v40; // eax
  __int64 v41; // r14
  BOOL v42; // edi
  const WCHAR *v43; // r8
  BOOL v44; // eax
  int v45; // eax
  unsigned int v46; // eax
  BSTR v47; // rdi
  unsigned int i; // esi
  int v49; // ecx
  unsigned __int64 v50; // rcx
  LPVOID v51; // rax
  struct tagUpdateDeploymentReportingData *v52; // rcx
  unsigned int v53; // r12d
  _WORD *v54; // rax
  BSTR v55; // rax
  int v56; // ecx
  struct tagUpdateDeploymentReportingData *v57; // rax
  int v58; // eax
  __int64 v59; // xmm0_8
  int v60; // ecx
  struct tagUpdateDeploymentReportingData *v61; // rax
  int v62; // eax
  int v63; // r9d
  int v64; // r12d
  bool updated; // al
  unsigned int v66; // edx
  unsigned int v67; // ecx
  int v68; // eax
  char v69; // r8
  unsigned int v70; // ecx
  unsigned int v71; // edx
  const wchar_t *v72; // rcx
  int v73; // r10d
  struct tagUpdateDeploymentReportingData *v74; // rax
  _DWORD *v75; // rdx
  unsigned int v76; // edx
  struct tagUpdateDeploymentReportingData *v77; // rax
  wchar_t **v78; // rdx
  unsigned __int16 *v79; // rcx
  void *v80; // rax
  __int64 v81; // rcx
  void *v82; // rax
  struct tagUpdateDeploymentReportingData *v83; // rax
  __int64 v84; // rcx
  int v85; // ecx
  __int64 RegKeyPath; // rax
  __int64 v87; // rcx
  int v88; // esi
  struct tagUpdateDeploymentReportingData *v89; // rax
  wchar_t **v90; // rcx
  unsigned int v91; // r12d
  HKEY v92; // rdx
  void *v93; // r10
  struct tagUpdateDeploymentReportingData *v94; // rdx
  int v95; // eax
  int v96; // esi
  int v97; // ecx
  struct tagUpdateDeploymentReportingData *v98; // rdx
  __int64 v99; // rdi
  BOOL v100; // r8d
  unsigned int v101; // ecx
  unsigned int v102; // ecx
  int v103; // eax
  char v104; // r8
  unsigned int v105; // ecx
  unsigned int v106; // edx
  int v107; // r14d
  unsigned int j; // esi
  unsigned int v109; // esi
  const wchar_t *v110; // rcx
  unsigned __int64 v111; // rcx
  wchar_t *v112; // rax
  wchar_t **v113; // rax
  unsigned int v114; // r14d
  __int64 v115; // r13
  const OLECHAR *v116; // rcx
  BSTR v117; // rax
  int v118; // eax
  wchar_t *v119; // xmm0_8
  int v120; // ecx
  wchar_t **v121; // rax
  unsigned int v122; // r14d
  wchar_t **v123; // rdx
  unsigned __int16 *v124; // rcx
  wchar_t *v125; // rax
  wchar_t *v126; // rcx
  wchar_t *v127; // rax
  wchar_t *v128; // rcx
  wchar_t **v129; // rdx
  struct tagUpdateDeploymentReportingData *v130; // rdx
  _QWORD *v131; // rax
  void *v132; // r9
  int v133; // r8d
  __int64 v134; // rcx
  wchar_t **v135; // rdx
  int v136; // eax
  unsigned int v137; // r8d
  OLECHAR *v138; // rdi
  UINT v139; // r14d
  void *v140; // rcx
  int v141; // eax
  PCNZWCH lpString2; // [rsp+20h] [rbp-E0h]
  WCHAR *lpString2a; // [rsp+20h] [rbp-E0h]
  int lpString2b; // [rsp+20h] [rbp-E0h]
  const wchar_t *cchCount2; // [rsp+28h] [rbp-D8h]
  int cchCount2a; // [rsp+28h] [rbp-D8h]
  wchar_t *v147; // [rsp+30h] [rbp-D0h]
  __int64 v148; // [rsp+38h] [rbp-C8h]
  bool v149[4]; // [rsp+70h] [rbp-90h] BYREF
  int v150; // [rsp+74h] [rbp-8Ch]
  int v151; // [rsp+78h] [rbp-88h]
  int v152; // [rsp+7Ch] [rbp-84h]
  int v153; // [rsp+80h] [rbp-80h]
  int v154; // [rsp+84h] [rbp-7Ch]
  int v155; // [rsp+88h] [rbp-78h] BYREF
  int v156; // [rsp+8Ch] [rbp-74h] BYREF
  int v157; // [rsp+90h] [rbp-70h] BYREF
  BSTR bstr; // [rsp+98h] [rbp-68h] BYREF
  int v159; // [rsp+A0h] [rbp-60h]
  int v160; // [rsp+A4h] [rbp-5Ch]
  int v161; // [rsp+A8h] [rbp-58h]
  CUpdateDeploymentJob *v162; // [rsp+B0h] [rbp-50h]
  __int64 v163; // [rsp+B8h] [rbp-48h] BYREF
  unsigned int v164; // [rsp+C0h] [rbp-40h]
  struct tagUpdateDeploymentReportingData **v165; // [rsp+C8h] [rbp-38h]
  char v166; // [rsp+D0h] [rbp-30h]
  _QWORD *v167; // [rsp+D8h] [rbp-28h]
  void **v168; // [rsp+E0h] [rbp-20h]
  char v169; // [rsp+E8h] [rbp-18h]
  wchar_t v170[40]; // [rsp+F0h] [rbp-10h] BYREF
  wchar_t ***v171; // [rsp+140h] [rbp+40h]
  struct tagUpdateDeploymentReportingData **v172; // [rsp+148h] [rbp+48h]
  char v173; // [rsp+150h] [rbp+50h]
  wchar_t v174[56]; // [rsp+160h] [rbp+60h] BYREF
  wchar_t **v175; // [rsp+1D0h] [rbp+D0h] BYREF
  struct tagUpdateDeploymentReportingData *v176; // [rsp+1D8h] [rbp+D8h] BYREF
  void *v177; // [rsp+1E0h] [rbp+E0h] BYREF
  HKEY hKey; // [rsp+1E8h] [rbp+E8h] BYREF
  struct tagUpdateDeploymentReportingData *v179; // [rsp+1F0h] [rbp+F0h] BYREF
  void *lpMem; // [rsp+1F8h] [rbp+F8h] BYREF
  void *p_hKey; // [rsp+200h] [rbp+100h] BYREF
  void *v182; // [rsp+208h] [rbp+108h]
  int v183; // [rsp+210h] [rbp+110h]
  int v184; // [rsp+214h] [rbp+114h]
  void *v185; // [rsp+218h] [rbp+118h]
  void *v186[8]; // [rsp+220h] [rbp+120h] BYREF
  _BYTE v187[96]; // [rsp+260h] [rbp+160h] BYREF
  wchar_t Buffer; // [rsp+2C0h] [rbp+1C0h] BYREF
  __int128 v189; // [rsp+2C2h] [rbp+1C2h]
  __int128 v190; // [rsp+2D2h] [rbp+1D2h]
  int v191; // [rsp+2E2h] [rbp+1E2h]
  __int16 v192; // [rsp+2E6h] [rbp+1E6h]
  __int128 v193; // [rsp+2F0h] [rbp+1F0h] BYREF
  __int128 v194; // [rsp+300h] [rbp+200h]
  __int128 v195; // [rsp+310h] [rbp+210h]
  __int128 v196; // [rsp+320h] [rbp+220h]
  __int128 v197; // [rsp+330h] [rbp+230h]
  __int128 v198; // [rsp+340h] [rbp+240h]
  __int128 v199; // [rsp+350h] [rbp+250h]
  __int128 v200; // [rsp+360h] [rbp+260h]
  char v201; // [rsp+370h] [rbp+270h]
  __int128 v202; // [rsp+380h] [rbp+280h] BYREF
  __int128 v203; // [rsp+390h] [rbp+290h]
  __int128 v204; // [rsp+3A0h] [rbp+2A0h]
  __int128 v205; // [rsp+3B0h] [rbp+2B0h]
  __int128 v206; // [rsp+3C0h] [rbp+2C0h]
  __int128 v207; // [rsp+3D0h] [rbp+2D0h]
  __int128 v208; // [rsp+3E0h] [rbp+2E0h]
  __int128 v209; // [rsp+3F0h] [rbp+2F0h]
  char v210; // [rsp+400h] [rbp+300h]
  wil::details::in1diag3 *retaddr; // [rsp+468h] [rbp+368h]

  v164 = a4;
  v6 = a2;
  v152 = a2;
  v162 = (CUpdateDeploymentJob *)this;
  if ( a4 >= this[43].Data1 )
    return;
  _mm_lfence();
  v153 = 0;
  v8 = *(_QWORD **)(*(_QWORD *)this[43].Data4 + 8LL * a4);
  v167 = v8;
  v9 = *((_DWORD *)v8 + 14);
  Buffer = 0;
  v189 = 0;
  v190 = 0;
  v191 = 0;
  v192 = 0;
  v10 = (const wchar_t *)v8[55];
  v160 = *((_DWORD *)v8 + 60);
  v151 = v8[67] & 0x200;
  memset(v186, 0, sizeof(v186));
  v186[0] = &CSusArrayList<tagDeploymentReportingUpdateEvent,CSusArrayListItemOpDeploymentReportingUpdateEvent>::`vftable';
  v186[1] = 0;
  v186[2] = 0;
  v186[3] = &CSusArrayList<tagDeploymentReportingUpdateEvent,CSusArrayListItemOpDeploymentReportingUpdateEvent>::`vftable';
  memset(&v186[4], 0, 28);
  v11 = 0;
  v163 = 0;
  v175 = 0;
  v179 = 0;
  v157 = 0;
  v161 = 0;
  v159 = 0;
  v154 = 0;
  lpMem = 0;
  v171 = &v175;
  v172 = &v179;
  v173 = 1;
  v12 = (TraceLoggingCorrelationVector *)v8[73];
  LOBYTE(v193) = 0;
  if ( v12 )
    TraceLoggingCorrelationVector::Increment(v12, (char *)&v193);
  v13 = (volatile signed __int64 *)v8[74];
  if ( v13 )
    TraceLoggingCorrelationVector::ToStringImpl(
      (TraceLoggingCorrelationVector *)v13,
      _InterlockedExchangeAdd64(v13 + 17, 0),
      (char *)&v202);
  else
    LOBYTE(v202) = 0;
  if ( (int)WuSmartPtr::XPtrBase<tagDeployableUpdateData,WuSmartPtr::Policies::STPolicy<tagDeployableUpdateData>>::ReleaseAndAlloc(&v175) >= 0 )
  {
    memset(v175, 0, 0x288u);
    DPCopyString(L"1.0.0.6", v175);
    *((_DWORD *)v175 + 101) = 1;
    if ( (v8[67] & 0x20) != 0 )
    {
      v14 = *(_QWORD *)&this[44].Data1;
      v15 = *(void (__fastcall **)(__int64, void **))(*(_QWORD *)v14 + 128LL);
      if ( lpMem )
      {
        SusFree(lpMem);
        lpMem = 0;
      }
      v15(v14, &lpMem);
      v6 = v152;
    }
    v16 = 0;
    if ( !a5 )
      *((_DWORD *)v8 + 140) = 1;
    *((_DWORD *)v175 + 25) = a3;
    v17 = (v8[67] & 0xC0) != 0;
    *((_DWORD *)v175 + 38) = v17;
    if ( !v17 || (v18 = 1, v6 >= 0) )
      v18 = 0;
    *((_DWORD *)v175 + 39) = v18;
    v19 = v151;
    v20 = v151 != 0;
    *((_DWORD *)v175 + 98) = v20;
    if ( !a5 )
    {
      if ( v6 >= 0 )
      {
        v21 = 0;
        LOBYTE(v16) = *((_DWORD *)v8 + 26) != 0;
        LOWORD(v150) = CUpdateDeploymentJob::GetDeploymentSuccessEventID(v20, *((unsigned int *)v8 + 14), v16);
        v36 = v175;
        v37 = v175 + 25;
        if ( v175 != (wchar_t **)-200LL && !*(_DWORD *)v37 )
        {
          *(_DWORD *)v37 = 2 - (v35 != 0);
          v36 = v175;
        }
        v38 = *((_DWORD *)v36 + 91) | 0x80;
        if ( *((_DWORD *)v36 + 50) != 1 )
          v38 = *((_DWORD *)v36 + 91) & 0xFFFFFF7F;
        *((_DWORD *)v36 + 91) = v38;
        DPAppendString((unsigned int *)v175 + 51, (wchar_t ***)v175 + 26, v10);
        if ( (v8[67] & 0x20) == 0 )
          goto LABEL_29;
        v23 = v162;
        if ( *((_DWORD *)v8 + 14) == 1 )
          *((_DWORD *)v175 + 100) = *((unsigned __int8 *)v8 + 153);
      }
      else
      {
        v33 = v9;
        v23 = v162;
        LOWORD(v150) = CUpdateDeploymentJob::GetDeploymentFailureEventID(v162, v33, (unsigned int)v6);
        *((_DWORD *)v175 + 77) = *((unsigned __int8 *)v8 + 152);
        StringCchPrintfExW(&Buffer, 0x14u, 0, 0, 0x100u, v34, v6);
        DPAppendString((unsigned int *)v175 + 51, (wchar_t ***)v175 + 26, &Buffer);
        DPAppendString((unsigned int *)v175 + 51, (wchar_t ***)v175 + 26, v10);
        v21 = 0;
      }
LABEL_30:
      v24 = *((_DWORD *)v8 + 54);
      v25 = v175;
      *(_OWORD *)((char *)v175 + 236) = *(_OWORD *)(v8 + 25);
      *((_DWORD *)v25 + 63) = v24;
      v26 = v175;
      if ( v175 )
      {
        *((_DWORD *)v26 + 16) = GetEnterprisePolicy_IsWUfBDeferralActive();
        if ( !GetEnterprisePolicy_IsWUfBDeferralActive() || (v27 = !IsPolicyDrivenServiceEnabled(), v28 = 1, v27) )
          v28 = 0;
        *((_DWORD *)v26 + 17) = v28;
        v149[0] = 0;
        IsPauseQualityUpdateEnabled = GetEnterprisePolicy_IsPauseQualityUpdateEnabled(v149);
        if ( v149[0] )
          *((_BYTE *)v26 + 88) = IsPauseQualityUpdateEnabled;
        IsPauseFeatureUpdateEnabled = GetEnterprisePolicy_IsPauseFeatureUpdateEnabled(v149);
        if ( v149[0] )
          *((_BYTE *)v26 + 89) = IsPauseFeatureUpdateEnabled;
      }
      PopulateSystemProps((struct tagUpdateDeploymentReportingData *)v175);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_ModernStandby>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_ModernStandby>::GetImpl'::`2'::impl) )
      {
        v31 = *((_DWORD *)v175 + 91);
        if ( (*((_DWORD *)v23 + 198) & 0x800) != 0 )
          v32 = v31 | 0x800;
        else
          v32 = v31 & 0xFFFFF7FF;
        *((_DWORD *)v175 + 91) = v32;
      }
      v177 = 0;
      p_hKey = &v177;
      LOBYTE(v182) = 1;
      if ( (int)WuSmartPtr::XPtrBase<tagDeployableUpdateData,WuSmartPtr::Policies::STPolicy<tagDeployableUpdateData>>::ReleaseAndAlloc(&v177) >= 0 )
      {
        switch ( *((_DWORD *)v8 + 14) )
        {
          case 1:
            v39 = 1;
            break;
          case 2:
            v39 = 2;
            break;
          case 4:
            v39 = 4;
            break;
          default:
            v39 = *((_DWORD *)v8 + 14) == 8 ? 8 : 0;
            break;
        }
        v21 = 0;
        if ( (*(int (__fastcall **)(_QWORD, __int64, _QWORD, __int64, int, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, _QWORD, void *, _DWORD))(**((_QWORD **)v23 + 89) + 24LL))(
               *((_QWORD *)v23 + 89),
               2,
               *((unsigned int *)v23 + 200),
               2048,
               v39,
               v8[6],
               v8[2],
               *((_DWORD *)v8 + 6),
               v8[8],
               0,
               0,
               v177,
               0) >= 0 )
        {
          DPPopulateProductRelatedData(
            (const struct tagDSUpdateMetadata *)((char *)v177 + 8),
            (struct tagUpdateDeploymentReportingData *)v175);
          *((_DWORD *)v175 + 137) = *((_DWORD *)v177 + 11);
          *((_DWORD *)v175 + 138) = *((_DWORD *)v177 + 12);
          *((_DWORD *)v175 + 148) = *((_DWORD *)v177 + 48);
        }
      }
      DPFreeDeployableUpdateData(v177);
      if ( v177 )
        operator delete(v177, (const struct std::nothrow_t *)0x288);
      *((_OWORD *)v175 + 32) = *(_OWORD *)(v8 + 63);
      DuplicateOptionalString<wchar_t *,wchar_t *>((void *)v8[71]);
      if ( v160 )
      {
        *((_DWORD *)v175 + 69) = 7;
        v40 = 0;
        v156 = 0;
        if ( !*((_DWORD *)v8 + 136) )
          goto LABEL_278;
        while ( 1 )
        {
          LODWORD(hKey) = 0;
          v176 = 0;
          *(_DWORD *)v149 = 0;
          v155 = -1;
          v41 = *(_QWORD *)(v8[69] + 8LL * v40);
          if ( !*(_DWORD *)(v41 + 100) && *(_DWORD *)(v41 + 92) != -2145124299 )
            v21 = 1;
          v42 = 0;
          if ( a5 )
            v42 = CUpdateDeploymentJob::GetProcessedUpdateResult(
                    v23,
                    *(const wchar_t **)(v41 + 16),
                    (int *)&hKey,
                    (unsigned int *)v149) < 0;
          v44 = ((v165 = &v176,
                  v166 = 1,
                  v43 = *(const WCHAR **)(v41 + 80),
                  v43 == L"http://schemas.microsoft.com/msus/2016/01/UpdateHandlers/OSInstaller")
              || v43
              && CompareStringW(
                   0x7Fu,
                   1u,
                   v43,
                   -1,
                   L"http://schemas.microsoft.com/msus/2016/01/UpdateHandlers/OSInstaller",
                   -1) == 2)
             && *(_DWORD *)(v41 + 104);
          v154 |= v44;
          if ( v21 )
          {
            v21 = 0;
          }
          else
          {
            v21 = 0;
            if ( !v42 )
              goto LABEL_82;
          }
          WuSmartPtr::XPtrBase<tagDeployableUpdateData,WuSmartPtr::Policies::STPolicy<tagDeployableUpdateData>>::ReleaseAndAlloc(&v176);
          if ( v176 )
            break;
          v166 = 0;
          FreeObject(0);
LABEL_83:
          if ( v176 )
            operator delete(v176, (const struct std::nothrow_t *)0x288);
LABEL_200:
          v40 = v156 + 1;
          v156 = v40;
          if ( v40 >= *((_DWORD *)v8 + 136) )
            goto LABEL_278;
        }
        memset(v176, 0, 0x288u);
        *(_WORD *)v149 = v150;
        *((_DWORD *)v176 + 101) = 1;
        *((_OWORD *)v176 + 32) = *(_OWORD *)(v8 + 63);
        DuplicateOptionalString<wchar_t *,wchar_t *>((void *)v8[71]);
        PopulateSystemProps(v176);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_ModernStandby>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_ModernStandby>::GetImpl'::`2'::impl) )
        {
          v45 = *((_DWORD *)v176 + 91);
          if ( (*((_DWORD *)v23 + 198) & 0x800) != 0 )
            v46 = v45 | 0x800;
          else
            v46 = v45 & 0xFFFFF7FF;
          *((_DWORD *)v176 + 91) = v46;
        }
        v47 = 0;
        bstr = 0;
        if ( v19 )
        {
          if ( (int)CUpdateDeploymentJob::GetUpdateTitle(
                      v23,
                      *(const wchar_t **)(v41 + 16),
                      *(_DWORD *)(v41 + 24),
                      *(const wchar_t **)(v41 + 48),
                      *(const wchar_t **)(v41 + 64),
                      &bstr) < 0 )
          {
            if ( bstr )
            {
              SusFree(bstr);
              bstr = 0;
            }
            if ( (int)DuplicateString<wchar_t const *,wchar_t *>(L"IDP Child Update", &bstr) < 0 )
            {
              if ( bstr )
                SusFree(bstr);
              FreeObject(v176);
              if ( v176 )
                operator delete(v176, (const struct std::nothrow_t *)0x288);
              goto LABEL_278;
            }
          }
          v47 = bstr;
        }
        if ( *(_DWORD *)(v41 + 272) )
        {
          do
            DPAppendString(
              (unsigned int *)v176 + 40,
              (wchar_t ***)v176 + 21,
              *(const wchar_t **)(*(_QWORD *)(v41 + 264) + 8LL * v21++));
          while ( v21 < *(_DWORD *)(v41 + 272) );
        }
        for ( i = 0; i < *(_DWORD *)(v41 + 376); ++i )
          DPAppendString(
            (unsigned int *)v175 + 44,
            (wchar_t ***)v175 + 23,
            *(const wchar_t **)(*(_QWORD *)(v41 + 368) + 8LL * i));
        CUHHandlerManager::HandlerUriToId(
          (CUpdateDeploymentJob *)((char *)v23 + 48),
          *(const wchar_t **)(v41 + 80),
          (enum tagUHUpdateHandler *)&v155);
        v49 = v155;
        *((_DWORD *)v176 + 69) = v155;
        if ( v49 == 8 )
          *((_DWORD *)v175 + 96) = 1;
        *((_OWORD *)v176 + 7) = *(_OWORD *)(v41 + 312);
        DPCopyString(*(const wchar_t **)(v41 + 328), (wchar_t **)v176 + 18);
        DPCopyString(*(const wchar_t **)(v41 + 336), (wchar_t **)v176 + 13);
        v21 = 0;
        if ( !SysStringLen(v175[18]) )
          DPCopyString(*(const wchar_t **)(v41 + 328), v175 + 18);
        if ( !SysStringLen(v175[13]) )
          DPCopyString(*(const wchar_t **)(v41 + 336), v175 + 13);
        *((_DWORD *)v176 + 98) = *(_DWORD *)(v41 + 304) != 0;
        *((_DWORD *)v176 + 78) = *(_DWORD *)(v41 + 240);
        DPCopyString(*(const wchar_t **)(v41 + 232), (wchar_t **)v176 + 40);
        DPCopyString(*(const wchar_t **)(v41 + 224), (wchar_t **)v176 + 41);
        DPCopyString(*(const wchar_t **)(v41 + 216), (wchar_t **)v176 + 42);
        if ( *(_QWORD *)(v41 + 280) && *(_DWORD *)(v41 + 288) )
        {
          do
            DPAppendBSTR(
              (unsigned int *)v176 + 54,
              (wchar_t ***)v176 + 28,
              *(wchar_t **)(*(_QWORD *)(v41 + 280) + 8LL * v21++));
          while ( v21 < *(_DWORD *)(v41 + 288) );
          v21 = 0;
        }
        v50 = *(unsigned int *)(v41 + 256);
        *((_DWORD *)v176 + 120) = v50;
        v51 = SafeSusAllocArray(v50, 8u);
        *((_QWORD *)v176 + 61) = v51;
        *((_QWORD *)v176 + 62) = SafeSusAllocArray(*((unsigned int *)v176 + 120), 4u);
        v52 = v176;
        if ( !*((_QWORD *)v176 + 61) || !*((_QWORD *)v176 + 62) )
        {
          if ( v47 )
          {
            SusFree(v47);
            v52 = v176;
          }
          v166 = 0;
          FreeObject(v52);
          goto LABEL_83;
        }
        v53 = 0;
        if ( *(_DWORD *)(v41 + 256) )
        {
          do
          {
            hKey = *(HKEY *)(v41 + 248);
            v54 = (_WORD *)*((_QWORD *)hKey + 2 * v53 + 1);
            if ( v54 && *v54 )
            {
              v55 = SysAllocString(*((const OLECHAR **)hKey + 2 * v53 + 1));
              *(_QWORD *)(*((_QWORD *)v176 + 61) + 8LL * v53) = v55;
              v52 = v176;
            }
            *(_DWORD *)(struct HKEY__ *)(*((_QWORD *)v52 + 62) + 4LL * v53) = *((_DWORD *)hKey + 4 * v53);
            ++v53;
            v52 = v176;
          }
          while ( v53 < *(_DWORD *)(v41 + 256) );
          v8 = v167;
          v23 = v162;
          v21 = 0;
        }
        *((_DWORD *)v52 + 38) = (*(_BYTE *)(v41 + 308) & 0xC0) != 0;
        *((_DWORD *)v176 + 39) = 0;
        v56 = *((_DWORD *)v8 + 54);
        v57 = v176;
        *((_OWORD *)v176 + 16) = *(_OWORD *)(v8 + 25);
        *((_DWORD *)v57 + 68) = v56;
        if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModelCacheGeneration>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_ModelCacheGeneration>::GetImpl'::`2'::impl) )
        {
          v58 = DuplicateOptionalString<wchar_t *,wchar_t *>(*(void **)(v41 + 384));
          if ( v58 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x130D,
              (int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentJob.cpp",
              (const char *)(unsigned int)v58);
          v59 = *(_QWORD *)(v41 + 408);
          v60 = *(_DWORD *)(v41 + 416);
          v61 = v176;
          *(_OWORD *)((char *)v176 + 616) = *(_OWORD *)(v41 + 392);
          *((_QWORD *)v61 + 79) = v59;
          *((_DWORD *)v61 + 160) = v60;
        }
        v177 = 0;
        v168 = &v177;
        v169 = 1;
        if ( (int)WuSmartPtr::XPtrBase<tagDeployableUpdateData,WuSmartPtr::Policies::STPolicy<tagDeployableUpdateData>>::ReleaseAndAlloc(&v177) < 0 )
        {
          cchCount2 = L"Fail to get update metadata for deployment reporting events.";
          LODWORD(lpString2) = v153;
          WUTrace(0, 0, 0x1000000, 3);
        }
        else
        {
          switch ( *(_DWORD *)(v41 + 56) )
          {
            case 1:
              v62 = 1;
              break;
            case 2:
              v62 = 2;
              break;
            case 4:
              v62 = 4;
              break;
            case 8:
              v62 = 8;
              break;
            default:
              v62 = 0;
              break;
          }
          LODWORD(v148) = *(_DWORD *)(v41 + 24);
          LODWORD(lpString2) = v62;
          v21 = 0;
          if ( (*(int (__fastcall **)(_QWORD, __int64, _QWORD, __int64, PCNZWCH, _QWORD, _QWORD, __int64, _QWORD, _QWORD, _QWORD, void *, _DWORD))(**((_QWORD **)v23 + 89) + 24LL))(
                 *((_QWORD *)v23 + 89),
                 2,
                 *((unsigned int *)v23 + 200),
                 3116,
                 lpString2,
                 *(_QWORD *)(v41 + 48),
                 *(_QWORD *)(v41 + 16),
                 v148,
                 *(_QWORD *)(v41 + 64),
                 0,
                 0,
                 v177,
                 0) >= 0 )
          {
            hKey = 0;
            if ( (int)CUHHandlerManager::GetHandler(
                        (CUpdateDeploymentJob *)((char *)v23 + 48),
                        *(const wchar_t **)(v41 + 80),
                        1,
                        v63,
                        &GUID_3da6d224_c341_52ac_f168_5457166f1bba,
                        (void **)&hKey) >= 0 )
            {
              v64 = (*(__int64 (__fastcall **)(HKEY, char *, _QWORD, _QWORD, struct tagUpdateDeploymentReportingData *))(*(_QWORD *)hKey + 24LL))(
                      hKey,
                      (char *)v177 + 8,
                      *(_QWORD *)(v41 + 64),
                      *(_QWORD *)(v41 + 136),
                      v176);
              if ( v64 < 0 )
              {
                v148 = *(_QWORD *)(v41 + 80);
                v147 = Trace::GuidToString::GuidToString(v170, (const struct _GUID *)v23 + 1);
                cchCount2 = L"Deployment job Id %ws : Failed to query deployment custom reporting data from handler = %ws.";
                LODWORD(lpString2) = v64;
                WUTrace(0, 0, 0x1000000, 5);
                v21 = 0;
              }
            }
            if ( !a5 )
              *((_DWORD *)v176 + 99) = *(_DWORD *)(v41 + 352);
            *((_DWORD *)v176 + 74) = *(_DWORD *)(v41 + 348);
            *((_DWORD *)v176 + 71) = *((_DWORD *)v177 + 47);
            DPPopulateProductRelatedData((const struct tagDSUpdateMetadata *)((char *)v177 + 8), v176);
            updated = DidUpdateUseSystemVolume(*(PCNZWCH *)(v41 + 144));
            *((_DWORD *)v176 + 70) = updated;
            *((_DWORD *)v176 + 137) = *((_DWORD *)v177 + 11);
            *((_DWORD *)v176 + 138) = *((_DWORD *)v177 + 12);
            *((_DWORD *)v176 + 148) = *((_DWORD *)v177 + 48);
            v66 = *((_DWORD *)v176 + 91) | 1;
            if ( !*((_DWORD *)v176 + 70) )
              v66 = *((_DWORD *)v176 + 91) & 0xFFFFFFFE;
            *((_DWORD *)v176 + 91) = v66;
            v67 = *((_DWORD *)v176 + 91) | 0x10;
            if ( !*(_DWORD *)(v41 + 300) )
              v67 = *((_DWORD *)v176 + 91) & 0xFFFFFFEF;
            *((_DWORD *)v176 + 91) = v67;
            v68 = *((_DWORD *)v23 + 207);
            if ( v68 == 1 || (v69 = 0, (unsigned int)(v68 - 2) <= 1) )
              v69 = 1;
            v70 = *((_DWORD *)v176 + 91) | 0x20;
            if ( !v69 )
              v70 = *((_DWORD *)v176 + 91) & 0xFFFFFFDF;
            *((_DWORD *)v176 + 91) = v70;
            v71 = *((_DWORD *)v176 + 91) | 0x40;
            if ( !*((_DWORD *)v176 + 74) )
              v71 = *((_DWORD *)v176 + 91) & 0xFFFFFFBF;
            *((_DWORD *)v176 + 91) = v71;
            if ( hKey )
              (*(void (__fastcall **)(HKEY))(*(_QWORD *)hKey + 16LL))(hKey);
          }
        }
        v72 = *(const wchar_t **)(v41 + 200);
        if ( v72 )
          DPCopyString(v72, (wchar_t **)v176 + 24);
        if ( !a5 )
        {
          if ( *(int *)(v41 + 92) < 0 )
          {
            *((_DWORD *)v176 + 77) = *(unsigned __int8 *)(v41 + 152);
            *((_DWORD *)v176 + 39) = *((_DWORD *)v176 + 38);
            *((_DWORD *)v176 + 25) = *(_DWORD *)(v41 + 96);
            if ( v152 == *(_DWORD *)(v41 + 92) )
            {
              v89 = v176;
              if ( *((_DWORD *)v176 + 40) )
              {
                do
                {
                  DPAppendBSTR(
                    (unsigned int *)v175 + 40,
                    (wchar_t ***)v175 + 21,
                    *(wchar_t **)(*((_QWORD *)v89 + 21) + 8LL * v21++));
                  v89 = v176;
                }
                while ( v21 < *((_DWORD *)v176 + 40) );
              }
              *((_DWORD *)v175 + 78) = *((_DWORD *)v89 + 78);
              DPCopyBSTR(*((wchar_t **)v176 + 40), v175 + 40);
              DPCopyBSTR(*((wchar_t **)v176 + 41), v175 + 41);
              DPCopyBSTR(*((wchar_t **)v176 + 42), v175 + 42);
              *((_DWORD *)v175 + 120) = *((_DWORD *)v176 + 120);
              v175[61] = (wchar_t *)SafeSusAllocArray(*((unsigned int *)v176 + 120), 8u);
              v175[62] = (wchar_t *)SafeSusAllocArray(*((unsigned int *)v176 + 120), 4u);
              v90 = v175;
              v21 = 0;
              if ( !v175[61] || !v175[62] )
              {
                v169 = 0;
                DPFreeDeployableUpdateData(v177);
                if ( v177 )
                {
                  operator delete(v177, (const struct std::nothrow_t *)0x288);
                  v177 = 0;
                }
                if ( v47 )
                  SusFree(v47);
                v166 = 0;
                FreeObject(v176);
                if ( v176 )
                  operator delete(v176, (const struct std::nothrow_t *)0x288);
                v19 = v151;
                goto LABEL_200;
              }
              v91 = 0;
              v77 = v176;
              if ( *((_DWORD *)v176 + 120) )
              {
                while ( 1 )
                {
                  DPCopyBSTR(*(wchar_t **)(*((_QWORD *)v77 + 61) + 8LL * v91), (wchar_t **)&v90[61][4 * v91]);
                  *(_DWORD *)&v175[62][2 * v91] = *(_DWORD *)(*((_QWORD *)v176 + 62) + 4LL * v91);
                  ++v91;
                  v77 = v176;
                  if ( v91 >= *((_DWORD *)v176 + 120) )
                    break;
                  v90 = v175;
                }
              }
LABEL_169:
              UuidFromStringW(*(RPC_WSTR *)(v41 + 16), (UUID *)((char *)v77 + 236));
              *((_DWORD *)v176 + 63) = *(_DWORD *)(v41 + 24);
              DPAppendString((unsigned int *)v176 + 6, (wchar_t ***)v176 + 4, *((const wchar_t **)v23 + 85));
              PopulateFirstProcessNameIfAvailable(v176, v78);
              *((_DWORD *)v176 + 10) = *(__int16 *)v149;
              *((_DWORD *)v176 + 11) = 101;
              v79 = *(unsigned __int16 **)(v41 + 48);
              if ( v79 && *v79 )
                UuidFromStringW(v79, (UUID *)((char *)v176 + 8));
              DPCopyString(*(const wchar_t **)(v41 + 72), (wchar_t **)v176 + 44);
              v80 = operator new[](0x81u, (const struct std::nothrow_t *)&std::nothrow);
              *((_QWORD *)v176 + 54) = v80;
              v81 = *((_QWORD *)v176 + 54);
              if ( v81 )
              {
                *(_OWORD *)v81 = v193;
                *(_OWORD *)(v81 + 16) = v194;
                *(_OWORD *)(v81 + 32) = v195;
                *(_OWORD *)(v81 + 48) = v196;
                *(_OWORD *)(v81 + 64) = v197;
                *(_OWORD *)(v81 + 80) = v198;
                *(_OWORD *)(v81 + 96) = v199;
                *(_OWORD *)(v81 + 112) = v200;
                *(_BYTE *)(v81 + 128) = v201;
              }
              v82 = operator new[](0x81u, (const struct std::nothrow_t *)&std::nothrow);
              *((_QWORD *)v176 + 55) = v82;
              v83 = v176;
              v84 = *((_QWORD *)v176 + 55);
              if ( v84 )
              {
                *(_OWORD *)v84 = v202;
                *(_OWORD *)(v84 + 16) = v203;
                *(_OWORD *)(v84 + 32) = v204;
                *(_OWORD *)(v84 + 48) = v205;
                *(_OWORD *)(v84 + 64) = v206;
                *(_OWORD *)(v84 + 80) = v207;
                *(_OWORD *)(v84 + 96) = v208;
                *(_OWORD *)(v84 + 112) = v209;
                *(_BYTE *)(v84 + 128) = v210;
                v83 = v176;
              }
              if ( a5 )
              {
                v97 = v152;
                *((_DWORD *)v83 + 24) = v152;
              }
              else
              {
                v85 = *(_DWORD *)(v41 + 92);
                if ( v85 >= 0 && *(_QWORD *)(v41 + 184) )
                {
                  hKey = 0;
                  RegKeyPath = GetRegKeyPath(13);
                  RegCreateKeyHelperPrivate(
                    v87,
                    RegKeyPath,
                    L"DontExpirePolledEvents",
                    &hKey,
                    (_DWORD)lpString2,
                    cchCount2,
                    v147,
                    v148);
                  if ( hKey )
                    RegCloseKey(hKey);
                  v155 = -1;
                  CUHHandlerManager::HandlerUriToId(
                    (CUpdateDeploymentJob *)((char *)v23 + 48),
                    *(const wchar_t **)(v41 + 80),
                    (enum tagUHUpdateHandler *)&v155);
                  v88 = v155;
                  if ( v155 == 8 || v155 == 12 )
                    v161 = 1;
                  if ( *(_DWORD *)(v41 + 304) || v155 == 8 || v155 == 12 )
                  {
                    hKey = 0;
                    p_hKey = &hKey;
                    LOBYTE(v182) = 1;
                    if ( (int)WuSmartPtr::XPtrBase<tagDeployableUpdateData,WuSmartPtr::Policies::STPolicy<tagDeployableUpdateData>>::ReleaseAndAlloc(&hKey) >= 0 )
                    {
                      memset(hKey, 0, 0x288u);
                      CloneUpdateDeploymentReportingData(v176, (struct tagUpdateDeploymentReportingData *)hKey);
                      *((_DWORD *)hKey + 10) = 201;
                      *((_DWORD *)hKey + 11) = 101;
                      *((_DWORD *)hKey + 24) = 2359301;
                      v92 = hKey;
                      hKey = 0;
                      v153 = CDeploymentReportingUpdateGroup::AddEvent((__int64)v186, (__int64)v92);
                      if ( v153 < 0 )
                      {
                        v147 = Trace::GuidToString::GuidToString(v170, (const struct _GUID *)v23 + 1);
                        WUTrace(0, 0, 0x1000000, 5);
                      }
                    }
                    LOBYTE(v182) = 0;
                    FreeObject((struct tagUpdateDeploymentReportingData *)hKey);
                    if ( hKey )
                      operator delete(hKey, (const struct std::nothrow_t *)0x288);
                  }
                  if ( v11
                    || (WuSmartPtr::XPtrBase<CDeploymentReportingUpdateGroup,WuSmartPtr::Policies::STPolicy<CDeploymentReportingUpdateGroup>>::ReleaseAndAlloc(&v163),
                        (v11 = v163) != 0) )
                  {
                    *((_DWORD *)v176 + 24) = 2367509;
                    v19 = v151;
                    if ( v151 )
                      DPAppendString((unsigned int *)v176 + 51, (wchar_t ***)v176 + 26, v47);
                    v93 = *(void **)(v41 + 184);
                    if ( *(_DWORD *)(v41 + 208) )
                      v88 = -1;
                    v94 = v176;
                    v176 = 0;
                    v95 = CDeploymentReportingUpdateGroup::AddEventInternal(v11, v94, v88, v93, lpMem, v19 != 0 ? 4 : 2);
                    v96 = v95;
                    v153 = v95;
                    if ( v95 >= 0 )
                    {
                      v96 = 0;
                      v153 = 0;
                    }
                    else
                    {
                      wil::details::in1diag3::Return_Hr(
                        retaddr,
                        (void *)0x5DF,
                        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\DPReportingData.cpp",
                        (const char *)(unsigned int)v95,
                        (int)lpString2);
                    }
                    if ( v96 < 0 )
                    {
                      v147 = Trace::GuidToString::GuidToString(v170, (const struct _GUID *)v23 + 1);
                      WUTrace(0, 0, 0x1000000, 5);
                    }
                    v157 = 1;
                  }
                  else
                  {
                    v19 = v151;
                  }
LABEL_231:
                  v21 = 0;
                  v169 = 0;
                  DPFreeDeployableUpdateData(v177);
                  if ( v177 )
                  {
                    operator delete(v177, (const struct std::nothrow_t *)0x288);
                    v177 = 0;
                  }
                  if ( v47 )
                    SusFree(v47);
LABEL_82:
                  v166 = 0;
                  FreeObject(v176);
                  goto LABEL_83;
                }
                *((_DWORD *)v83 + 24) = v85;
                v97 = v152;
              }
              v19 = v151;
              if ( v151 )
              {
                if ( *(int *)(v41 + 92) < 0 )
                {
                  LODWORD(v147) = v97;
                  StringCchPrintfExW(&Buffer, 0x14u, 0, 0, 0x100u, L"%#lx", v147);
                  DPAppendString((unsigned int *)v176 + 51, (wchar_t ***)v176 + 26, &Buffer);
                }
                DPAppendString((unsigned int *)v176 + 51, (wchar_t ***)v176 + 26, v47);
              }
              v98 = v176;
              v176 = 0;
              v153 = CDeploymentReportingUpdateGroup::AddEvent((__int64)v186, (__int64)v98);
              if ( v153 < 0 )
              {
                v147 = Trace::GuidToString::GuidToString(v170, (const struct _GUID *)v23 + 1);
                WUTrace(0, 0, 0x1000000, 5);
              }
              goto LABEL_231;
            }
          }
          else
          {
            *(_WORD *)v149 = CUpdateDeploymentJob::GetDeploymentSuccessEventID(
                               v72,
                               *(unsigned int *)(v41 + 56),
                               *(_DWORD *)(v41 + 104) != 0);
            v74 = v176;
            v75 = (_DWORD *)((char *)v176 + 200);
            if ( v176 != (struct tagUpdateDeploymentReportingData *)-200LL && !*v75 )
            {
              *v75 = 2 - (v73 != 0);
              v74 = v176;
            }
            v76 = *((_DWORD *)v74 + 91) | 0x80;
            if ( *((_DWORD *)v74 + 50) != 1 )
              v76 = *((_DWORD *)v74 + 91) & 0xFFFFFF7F;
            *((_DWORD *)v74 + 91) = v76;
            if ( (v8[67] & 0x20) != 0 && *((_DWORD *)v8 + 14) == 1 )
              *((_DWORD *)v176 + 100) = *(unsigned __int8 *)(v41 + 153);
          }
        }
        v77 = v176;
        goto LABEL_169;
      }
      v99 = *(_QWORD *)v8[69];
      *((_DWORD *)v175 + 74) = *(_DWORD *)(v99 + 348);
      v100 = DidUpdateUseSystemVolume(*(PCNZWCH *)(v99 + 144));
      *((_DWORD *)v175 + 70) = v100;
      v101 = *((_DWORD *)v175 + 91) | 1;
      if ( !v100 )
        v101 = *((_DWORD *)v175 + 91) & 0xFFFFFFFE;
      *((_DWORD *)v175 + 91) = v101;
      v102 = *((_DWORD *)v175 + 91) | 0x10;
      if ( !*(_DWORD *)(v99 + 300) )
        v102 = *((_DWORD *)v175 + 91) & 0xFFFFFFEF;
      *((_DWORD *)v175 + 91) = v102;
      v103 = *((_DWORD *)v23 + 207);
      if ( v103 == 1 || (v104 = 0, (unsigned int)(v103 - 2) <= 1) )
        v104 = 1;
      v105 = *((_DWORD *)v175 + 91) | 0x20;
      if ( !v104 )
        v105 = *((_DWORD *)v175 + 91) & 0xFFFFFFDF;
      *((_DWORD *)v175 + 91) = v105;
      v106 = *((_DWORD *)v175 + 91) | 0x40;
      if ( !*((_DWORD *)v175 + 74) )
        v106 = *((_DWORD *)v175 + 91) & 0xFFFFFFBF;
      *((_DWORD *)v175 + 91) = v106;
      v156 = -1;
      CUHHandlerManager::HandlerUriToId(
        (CUpdateDeploymentJob *)((char *)v23 + 48),
        *(const wchar_t **)(v99 + 80),
        (enum tagUHUpdateHandler *)&v156);
      v107 = v156;
      if ( v156 != 12 || (v27 = *(_DWORD *)(v99 + 104) == 0, v154 = 1, v27) )
        v154 = 0;
      if ( *(_DWORD *)(v99 + 272) )
      {
        do
          DPAppendString(
            (unsigned int *)v175 + 40,
            (wchar_t ***)v175 + 21,
            *(const wchar_t **)(*(_QWORD *)(v99 + 264) + 8LL * v21++));
        while ( v21 < *(_DWORD *)(v99 + 272) );
      }
      for ( j = 0; j < *(_DWORD *)(v99 + 376); ++j )
        DPAppendString(
          (unsigned int *)v175 + 44,
          (wchar_t ***)v175 + 23,
          *(const wchar_t **)(*(_QWORD *)(v99 + 368) + 8LL * j));
      v109 = 0;
      *((_DWORD *)v175 + 96) = v107 == 8;
      *((_DWORD *)v175 + 69) = v107;
      *((_OWORD *)v175 + 7) = *(_OWORD *)(v99 + 312);
      DPCopyString(*(const wchar_t **)(v99 + 328), v175 + 18);
      DPCopyString(*(const wchar_t **)(v99 + 336), v175 + 13);
      *((_DWORD *)v175 + 78) = *(_DWORD *)(v99 + 240);
      DPCopyString(*(const wchar_t **)(v99 + 232), v175 + 40);
      DPCopyString(*(const wchar_t **)(v99 + 224), v175 + 41);
      DPCopyString(*(const wchar_t **)(v99 + 216), v175 + 42);
      v110 = *(const wchar_t **)(v99 + 200);
      if ( v110 )
        DPCopyString(v110, v175 + 24);
      *((_DWORD *)v175 + 38) = (*(_BYTE *)(v99 + 308) & 0xC0) != 0;
      if ( *(_QWORD *)(v99 + 280) && *(_DWORD *)(v99 + 288) )
      {
        do
          DPAppendBSTR(
            (unsigned int *)v175 + 54,
            (wchar_t ***)v175 + 28,
            *(wchar_t **)(*(_QWORD *)(v99 + 280) + 8LL * v109++));
        while ( v109 < *(_DWORD *)(v99 + 288) );
      }
      v111 = *(unsigned int *)(v99 + 256);
      *((_DWORD *)v175 + 120) = v111;
      v112 = (wchar_t *)SafeSusAllocArray(v111, 8u);
      v175[61] = v112;
      v175[62] = (wchar_t *)SafeSusAllocArray(*((unsigned int *)v175 + 120), 4u);
      v113 = v175;
      if ( v175[61] )
      {
        if ( v175[62] )
        {
          v114 = 0;
          if ( *(_DWORD *)(v99 + 256) )
          {
            do
            {
              v115 = *(_QWORD *)(v99 + 248);
              v116 = *(const OLECHAR **)(v115 + 16LL * v114 + 8);
              if ( v116 && *v116 )
              {
                v117 = SysAllocString(v116);
                *(_QWORD *)&v175[61][4 * v114] = v117;
                v113 = v175;
              }
              *(_DWORD *)&v113[62][2 * v114] = *(_DWORD *)(v115 + 16LL * v114);
              ++v114;
              v113 = v175;
            }
            while ( v114 < *(_DWORD *)(v99 + 256) );
            v23 = v162;
            v19 = v151;
          }
        }
      }
      *((_DWORD *)v113 + 25) = *(_DWORD *)(v99 + 96);
      if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModelCacheGeneration>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_ModelCacheGeneration>::GetImpl'::`2'::impl) )
      {
        v118 = DuplicateOptionalString<wchar_t *,wchar_t *>(*(void **)(v99 + 384));
        if ( v118 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x1500,
            (int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentJob.cpp",
            (const char *)(unsigned int)v118);
        v119 = *(wchar_t **)(v99 + 408);
        v120 = *(_DWORD *)(v99 + 416);
        v121 = v175;
        *(_OWORD *)(v175 + 77) = *(_OWORD *)(v99 + 392);
        v121[79] = v119;
        *((_DWORD *)v121 + 160) = v120;
      }
LABEL_278:
      v122 = v152;
      if ( a5 || v152 < 0 )
      {
        v159 = 0;
      }
      else if ( v160 )
      {
        v159 = v157;
      }
      else if ( *(_QWORD *)(*(_QWORD *)v8[69] + 184LL) )
      {
        v159 = 1;
      }
      DPAppendString((unsigned int *)v175 + 6, (wchar_t ***)v175 + 4, *((const wchar_t **)v23 + 85));
      PopulateFirstProcessNameIfAvailable((struct tagUpdateDeploymentReportingData *)v175, v123);
      *((_DWORD *)v175 + 10) = (__int16)v150;
      *((_DWORD *)v175 + 11) = 101;
      v124 = (unsigned __int16 *)v8[6];
      if ( v124 && *v124 )
        UuidFromStringW(v124, (UUID *)(v175 + 1));
      v125 = (wchar_t *)operator new[](0x81u, (const struct std::nothrow_t *)&std::nothrow);
      v175[54] = v125;
      v126 = v175[54];
      if ( v126 )
      {
        *(_OWORD *)v126 = v193;
        *((_OWORD *)v126 + 1) = v194;
        *((_OWORD *)v126 + 2) = v195;
        *((_OWORD *)v126 + 3) = v196;
        *((_OWORD *)v126 + 4) = v197;
        *((_OWORD *)v126 + 5) = v198;
        *((_OWORD *)v126 + 6) = v199;
        *((_OWORD *)v126 + 7) = v200;
        *((_BYTE *)v126 + 128) = v201;
      }
      v127 = (wchar_t *)operator new[](0x81u, (const struct std::nothrow_t *)&std::nothrow);
      v175[55] = v127;
      v128 = v175[55];
      if ( v128 )
      {
        *(_OWORD *)v128 = v202;
        *((_OWORD *)v128 + 1) = v203;
        *((_OWORD *)v128 + 2) = v204;
        *((_OWORD *)v128 + 3) = v205;
        *((_OWORD *)v128 + 4) = v206;
        *((_OWORD *)v128 + 5) = v207;
        *((_OWORD *)v128 + 6) = v208;
        *((_OWORD *)v128 + 7) = v209;
        *((_BYTE *)v128 + 128) = v210;
      }
      if ( !v159 )
      {
        *((_DWORD *)v175 + 24) = v122;
        *((_DWORD *)v175 + 39) &= v122 >> 31;
        v129 = v175;
        v175 = 0;
        CDeploymentReportingUpdateGroup::AddEvent((__int64)v186, (__int64)v129);
LABEL_310:
        v184 = 0;
        v182 = v186[1];
        p_hKey = (void *)HIDWORD(v186[2]);
        v186[1] = 0;
        v186[2] = 0;
        v185 = v186[4];
        v183 = HIDWORD(v186[5]);
        v186[4] = 0;
        v186[5] = 0;
        if ( (*(int (__fastcall **)(_QWORD, _QWORD, void **))(**((_QWORD **)v23 + 91) + 48LL))(
               *((_QWORD *)v23 + 91),
               0,
               &p_hKey) < 0 )
        {
          Trace::GuidToString::GuidToString(v170, (const struct _GUID *)v23 + 1);
          WUTrace(0, 0, 0x1000000, 3);
        }
        CDeploymentReportingUpdateGroup::AttachEvents(v186, (struct tagDeploymentReportingUpdateGroup *)&p_hKey);
        if ( v11 )
        {
          HIDWORD(p_hKey) = 0;
          v184 = 0;
          v182 = *(void **)(v11 + 8);
          LODWORD(p_hKey) = *(_DWORD *)(v11 + 20);
          *(_QWORD *)(v11 + 8) = 0;
          *(_QWORD *)(v11 + 16) = 0;
          v185 = *(void **)(v11 + 32);
          v183 = *(_DWORD *)(v11 + 44);
          *(_QWORD *)(v11 + 32) = 0;
          *(_QWORD *)(v11 + 40) = 0;
          if ( (*(int (__fastcall **)(_QWORD, __int64, void **))(**((_QWORD **)v23 + 91) + 48LL))(
                 *((_QWORD *)v23 + 91),
                 1,
                 &p_hKey) < 0 )
          {
            Trace::GuidToString::GuidToString(v170, (const struct _GUID *)v23 + 1);
            WUTrace(0, 0, 0x1000000, 3);
          }
          CDeploymentReportingUpdateGroup::AttachEvents(
            (void **)v11,
            (struct tagDeploymentReportingUpdateGroup *)&p_hKey);
          memset(v187, 0, sizeof(v187));
          CSerializationHelper::CSerializationHelper((CSerializationHelper *)v187);
          v138 = 0;
          bstr = 0;
          if ( (int)CSerializationHelper::InitSerializeToStringWithHeader((CSerializationHelper *)v187) >= 0
            && (int)CDeploymentReportingUpdateGroup::Serialize(
                      (CDeploymentReportingUpdateGroup *)v11,
                      (struct CSerializationHelper *)v187) >= 0 )
          {
            if ( (int)CSerializationHelper::WriteToBSTRWithHeader((CSerializationHelper *)v187, &bstr) >= 0 )
            {
              v138 = bstr;
              SysStringByteLen(bstr);
              Trace::GuidToString::GuidToString(v170, (const struct _GUID *)v23 + 1);
              WUTrace(0, 0, 0x1000000, 4);
              v139 = SysStringByteLen(v138);
              if ( v139 )
              {
                v140 = (void *)v8[23];
                if ( v140 )
                {
                  SusFree(v140);
                  v8[23] = 0;
                }
                if ( (int)DPCopyBufferWithAlloc(
                            v139,
                            (const unsigned __int8 *)v138,
                            (unsigned int *)v8 + 44,
                            (unsigned __int8 **)v8 + 23) < 0 )
                {
                  Trace::UpdateIdToString::UpdateIdToString(v174, (const struct tagDSGlobalUpdateId *)(v8 + 25));
                  Trace::GuidToString::GuidToString(v170, (const struct _GUID *)v23 + 1);
                  WUTrace(0, 0, 0x1000000, 3);
                }
              }
            }
            else
            {
              Trace::GuidToString::GuidToString(v170, (const struct _GUID *)v23 + 1);
              WUTrace(0, 0, 0x1000000, 3);
              v138 = bstr;
            }
          }
          else
          {
            Trace::GuidToString::GuidToString(v170, (const struct _GUID *)v23 + 1);
            WUTrace(0, 0, 0x1000000, 3);
          }
          if ( v138 )
            SysFreeString(v138);
          CSerializationHelper::~CSerializationHelper((CSerializationHelper *)v187);
        }
        if ( !a5 )
        {
          v141 = CUpdateDeploymentJob::LogHistory(v23, v152, v137, v164);
          if ( v141 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x15F2,
              (int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentJob.cpp",
              (const char *)(unsigned int)v141);
        }
        goto LABEL_331;
      }
      if ( (v161 || v154)
        && (int)WuSmartPtr::XPtrBase<tagDeployableUpdateData,WuSmartPtr::Policies::STPolicy<tagDeployableUpdateData>>::ReleaseAndAlloc(&v179) >= 0 )
      {
        memset(v179, 0, 0x288u);
        CloneUpdateDeploymentReportingData((const struct tagUpdateDeploymentReportingData *)v175, v179);
        *((_DWORD *)v179 + 10) = 201;
        *((_DWORD *)v179 + 11) = 101;
        *((_DWORD *)v179 + 24) = 2359301;
        v130 = v179;
        v179 = 0;
        if ( (int)CDeploymentReportingUpdateGroup::AddEvent((__int64)v186, (__int64)v130) < 0 )
        {
          Trace::GuidToString::GuidToString(v170, (const struct _GUID *)v23 + 1);
          WUTrace(0, 0, 0x1000000, 5);
        }
      }
      if ( !v11 )
      {
        v131 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
        v11 = (__int64)v131;
        v167 = v131;
        if ( !v131 )
        {
          v11 = 0;
          v163 = 0;
          goto LABEL_310;
        }
        *v131 = &CSusArrayList<tagDeploymentReportingUpdateEvent,CSusArrayListItemOpDeploymentReportingUpdateEvent>::`vftable';
        v131[1] = 0;
        v131[2] = 0;
        v131[3] = &CSusArrayList<tagDeploymentReportingUpdateEvent,CSusArrayListItemOpDeploymentReportingUpdateEvent>::`vftable';
        v131[4] = 0;
        v131[5] = 0;
        *((_DWORD *)v131 + 12) = 0;
        *(_QWORD *)((char *)v131 + 52) = 0;
        v163 = (__int64)v131;
      }
      *((_DWORD *)v175 + 24) = 2367509;
      *((_DWORD *)v175 + 39) = 0;
      if ( v160 )
      {
        cchCount2a = v19 != 0 ? 5 : 1;
        lpString2a = 0;
        v132 = 0;
        v133 = 7;
      }
      else
      {
        v157 = -1;
        CUHHandlerManager::HandlerUriToId(
          (CUpdateDeploymentJob *)((char *)v23 + 48),
          *(const wchar_t **)(*(_QWORD *)v8[69] + 80LL),
          (enum tagUHUpdateHandler *)&v157);
        v134 = *(_QWORD *)v8[69];
        v132 = *(void **)(v134 + 184);
        v133 = v157;
        if ( *(_DWORD *)(v134 + 208) )
          v133 = -1;
        cchCount2a = 3;
        lpString2a = (WCHAR *)lpMem;
      }
      v135 = v175;
      v175 = 0;
      v136 = CDeploymentReportingUpdateGroup::AddEventInternal(v11, v135, v133, v132, lpString2a, cchCount2a);
      if ( v136 < 0 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5DF,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\DPReportingData.cpp",
          (const char *)(unsigned int)v136,
          lpString2b);
      goto LABEL_310;
    }
    v21 = 0;
    LOWORD(v150) = 0;
    if ( *((_DWORD *)v8 + 14) == 1 )
    {
      v22 = 181;
    }
    else if ( *((_DWORD *)v8 + 14) == 2 )
    {
      v22 = 226;
    }
    else
    {
      if ( *((_DWORD *)v8 + 14) != 4 )
      {
        if ( *((_DWORD *)v8 + 14) == 8 )
          v150 = 521;
        goto LABEL_28;
      }
      v22 = 546;
    }
    LOWORD(v150) = v22;
LABEL_28:
    DPAppendString((unsigned int *)v175 + 51, (wchar_t ***)v175 + 26, v10);
LABEL_29:
    v23 = v162;
    goto LABEL_30;
  }
  Trace::GuidToString::GuidToString(v170, this + 1);
  WUTrace(0, 0, 0x1000000, 3);
LABEL_331:
  FreeObject((struct tagUpdateDeploymentReportingData *)v175);
  FreeObject(v179);
  if ( lpMem )
  {
    SusFree(lpMem);
    lpMem = 0;
  }
  if ( v179 )
  {
    operator delete(v179, (const struct std::nothrow_t *)0x288);
    v179 = 0;
  }
  if ( v175 )
  {
    operator delete(v175, (const struct std::nothrow_t *)0x288);
    v175 = 0;
  }
  if ( v11 )
  {
    CSusArrayList<tagDeploymentReportingUpdateEvent,CSusArrayListItemOpDeploymentReportingUpdateEvent>::~CSusArrayList<tagDeploymentReportingUpdateEvent,CSusArrayListItemOpDeploymentReportingUpdateEvent>((_QWORD *)(v11 + 24));
    CSusArrayList<tagDeploymentReportingUpdateEvent,CSusArrayListItemOpDeploymentReportingUpdateEvent>::~CSusArrayList<tagDeploymentReportingUpdateEvent,CSusArrayListItemOpDeploymentReportingUpdateEvent>((_QWORD *)v11);
    operator delete((void *)v11, (const struct std::nothrow_t *)0x40);
  }
  CSusArrayList<tagDeploymentReportingUpdateEvent,CSusArrayListItemOpDeploymentReportingUpdateEvent>::~CSusArrayList<tagDeploymentReportingUpdateEvent,CSusArrayListItemOpDeploymentReportingUpdateEvent>(&v186[3]);
  CSusArrayList<tagDeploymentReportingUpdateEvent,CSusArrayListItemOpDeploymentReportingUpdateEvent>::~CSusArrayList<tagDeploymentReportingUpdateEvent,CSusArrayListItemOpDeploymentReportingUpdateEvent>(v186);
}

```

## disassembly

```asm
0x1800330b8  push    rbp
0x1800330ba  push    rbx
0x1800330bb  push    rsi
0x1800330bc  push    rdi
0x1800330bd  push    r12
0x1800330bf  push    r13
0x1800330c1  push    r14
0x1800330c3  push    r15
0x1800330c5  lea     rbp, [rsp-328h]
0x1800330cd  sub     rsp, 428h
0x1800330d4  mov     rax, cs:__security_cookie
0x1800330db  xor     rax, rsp
0x1800330de  mov     [rbp+360h+var_50], rax
0x1800330e5  mov     eax, r9d
0x1800330e8  mov     [rbp+360h+var_3A0], eax
0x1800330eb  mov     r12d, r8d
0x1800330ee  mov     esi, edx
0x1800330f0  mov     [rsp+460h+var_3E4], edx
0x1800330f4  mov     rdi, rcx
0x1800330f7  mov     [rbp+360h+var_3B0], rcx
0x1800330fb  cmp     r9d, [rcx+2B0h]
0x180033102  jnb     loc_180035780
0x180033108  lfence
0x18003310b  xor     edx, edx; Val
0x18003310d  mov     [rbp+360h+var_3E0], edx
0x180033110  mov     ecx, eax
0x180033112  mov     rax, [rdi+2B8h]
0x180033119  mov     r15, [rax+rcx*8]
0x18003311d  mov     [rbp+360h+var_388], r15
0x180033121  mov     r13d, [r15+38h]
0x180033125  mov     [rbp+360h+Buffer], dx
0x18003312c  xorps   xmm0, xmm0
0x18003312f  xor     eax, eax
0x180033131  movups  [rbp+360h+var_19E], xmm0
0x180033138  movups  [rbp+360h+var_18E], xmm0
0x18003313f  mov     [rbp+360h+var_17E], eax
0x180033145  mov     [rbp+360h+var_17A], ax
0x18003314c  mov     r14, [r15+1B8h]
0x180033153  mov     eax, [r15+0F0h]
0x18003315a  mov     [rbp+360h+var_3BC], eax
0x18003315d  mov     eax, [r15+218h]
0x180033164  and     eax, 200h
0x180033169  mov     [rsp+460h+var_3E8], eax
0x18003316d  lea     r8d, [rdx+40h]; Size
0x180033171  lea     rcx, [rbp+360h+var_240]; void *
0x180033178  call    memset
0x18003317d  lea     rax, ??_7?$CSusArrayList@UtagDeploymentReportingUpdateEvent@@VCSusArrayListItemOpDeploymentReportingUpdateEvent@@@@6B@; const CSusArrayList<tagDeploymentReportingUpdateEvent,CSusArrayListItemOpDeploymentReportingUpdateEvent>::`vftable'
0x180033184  mov     [rbp+360h+var_240], rax
0x18003318b  xor     edx, edx
0x18003318d  mov     [rbp+360h+var_238], rdx
0x180033194  mov     [rbp+360h+var_230], rdx
0x18003319b  mov     [rbp+360h+var_228], rax
0x1800331a2  mov     [rbp+360h+var_220], rdx
0x1800331a9  mov     [rbp+360h+var_218], rdx
0x1800331b0  mov     [rbp+360h+var_210], edx
0x1800331b6  xor     eax, eax
0x1800331b8  mov     [rbp+360h+var_20C], rax
0x1800331bf  mov     ebx, edx
0x1800331c1  mov     [rbp+360h+var_3A8], rdx
0x1800331c5  mov     [rbp+360h+var_290], rdx
0x1800331cc  mov     [rbp+360h+var_270], rdx
0x1800331d3  mov     [rbp+360h+var_3D0], edx
0x1800331d6  mov     [rbp+360h+var_3B8], edx
0x1800331d9  mov     [rbp+360h+var_3C0], edx
0x1800331dc  mov     [rbp+360h+var_3DC], edx
0x1800331df  mov     [rbp+360h+lpMem], rdx
0x1800331e6  lea     rax, [rbp+360h+var_290]
0x1800331ed  mov     [rbp+360h+var_320], rax
0x1800331f1  lea     rax, [rbp+360h+var_270]
0x1800331f8  mov     [rbp+360h+var_318], rax
0x1800331fc  mov     [rbp+360h+var_310], 1
0x180033200  mov     rcx, [r15+248h]; this
0x180033207  mov     byte ptr [rbp+360h+var_170], dl
0x18003320d  test    rcx, rcx
0x180033210  jz      short loc_180033220
0x180033212  lea     rdx, [rbp+360h+var_170]; char *
0x180033219  call    ?Increment@TraceLoggingCorrelationVector@@QEAA_NPEAD@Z; TraceLoggingCorrelationVector::Increment(char *)
0x18003321e  xor     edx, edx
0x180033220  mov     rcx, [r15+250h]; this
0x180033227  test    rcx, rcx
0x18003322a  jnz     short loc_180033234
0x18003322c  mov     byte ptr [rbp+360h+var_E0], dl
0x180033232  jmp     short loc_180033249
0x180033234  lock xadd [rcx+88h], rdx; unsigned __int64
0x18003323d  lea     r8, [rbp+360h+var_E0]; char *
0x180033244  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x180033249  lea     rcx, [rbp+360h+var_290]
0x180033250  call    ?ReleaseAndAlloc@?$XPtrBase@UtagDeployableUpdateData@@U?$STPolicy@UtagDeployableUpdateData@@@Policies@WuSmartPtr@@@WuSmartPtr@@QEAAJXZ; WuSmartPtr::XPtrBase<tagDeployableUpdateData,WuSmartPtr::Policies::STPolicy<tagDeployableUpdateData>>::ReleaseAndAlloc(void)
0x180033255  test    eax, eax
0x180033257  jns     short loc_180033297
0x180033259  lea     rdx, [rdi+10h]; struct _GUID *
0x18003325d  lea     rcx, [rbp+360h+var_370]; this
0x180033261  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x180033266  mov     [rsp+460h+var_430], rax
0x18003326b  lea     rax, aDeploymentJobI_15; "Deployment job Id %ws : ReportDeploymen"...
0x180033272  mov     qword ptr [rsp+460h+cchCount2], rax
0x180033277  xor     r14d, r14d
0x18003327a  mov     [rsp+460h+lpString2], r14
0x18003327f  xor     edx, edx
0x180033281  xor     ecx, ecx
0x180033283  lea     r9d, [r14+3]
0x180033287  mov     r8d, 1000000h
0x18003328d  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180033292  jmp     loc_1800356D9
0x180033297  xor     edx, edx; Val
0x180033299  mov     r8d, 288h; Size
0x18003329f  mov     rcx, [rbp+360h+var_290]; void *
0x1800332a6  call    memset
0x1800332ab  mov     rdx, [rbp+360h+var_290]; wchar_t **
0x1800332b2  lea     rcx, a1006; "1.0.0.6"
0x1800332b9  call    ?DPCopyString@@YAJPEB_WPEAPEA_W@Z; DPCopyString(wchar_t const *,wchar_t * *)
0x1800332be  mov     rax, [rbp+360h+var_290]
0x1800332c5  mov     dword ptr [rax+194h], 1
0x1800332cf  test    byte ptr [r15+218h], 20h
0x1800332d7  jz      short loc_18003331A
0x1800332d9  mov     rdi, [rdi+2C0h]
0x1800332e0  mov     rax, [rdi]
0x1800332e3  mov     rsi, [rax+80h]
0x1800332ea  mov     rcx, [rbp+360h+lpMem]; lpMem
0x1800332f1  test    rcx, rcx
0x1800332f4  jz      short loc_180033304
0x1800332f6  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x1800332fb  xor     eax, eax
0x1800332fd  mov     [rbp+360h+lpMem], rax
0x180033304  lea     rdx, [rbp+360h+lpMem]
0x18003330b  mov     rcx, rdi
0x18003330e  mov     rax, rsi
0x180033311  call    _guard_dispatch_icall
0x180033316  mov     esi, [rsp+460h+var_3E4]
0x18003331a  mov     dl, [rbp+360h+arg_20]
0x180033320  xor     r8d, r8d
0x180033323  test    dl, dl
0x180033325  jnz     short loc_180033332
0x180033327  mov     dword ptr [r15+230h], 1
0x180033332  mov     rax, [rbp+360h+var_290]
0x180033339  mov     [rax+64h], r12d
0x18003333d  test    byte ptr [r15+218h], 0C0h
0x180033345  mov     ecx, r8d
0x180033348  setnz   cl
0x18003334b  mov     rax, [rbp+360h+var_290]
0x180033352  mov     [rax+98h], ecx
0x180033358  test    ecx, ecx
0x18003335a  jz      short loc_180033365
0x18003335c  test    esi, esi
0x18003335e  mov     ecx, 1
0x180033363  js      short loc_180033368
0x180033365  mov     ecx, r8d
0x180033368  mov     rax, [rbp+360h+var_290]
0x18003336f  mov     [rax+9Ch], ecx
0x180033375  mov     ecx, r8d
0x180033378  mov     r12d, [rsp+460h+var_3E8]
0x18003337d  test    r12d, r12d
0x180033380  setnz   cl
0x180033383  mov     rax, [rbp+360h+var_290]
0x18003338a  mov     [rax+188h], ecx
0x180033390  lea     r10, aLx; "%#lx"
0x180033397  test    dl, dl
0x180033399  jz      loc_1800334CC
0x18003339f  xor     esi, esi
0x1800333a1  mov     word ptr [rsp+460h+var_3EC], si
0x1800333a6  mov     ecx, [r15+38h]
0x1800333aa  sub     ecx, 1
0x1800333ad  jz      short loc_1800333D6
0x1800333af  sub     ecx, 1
0x1800333b2  jz      short loc_1800333CF
0x1800333b4  sub     ecx, 2
0x1800333b7  jz      short loc_1800333C8
0x1800333b9  cmp     ecx, 4
0x1800333bc  jnz     short loc_1800333E0
0x1800333be  mov     [rsp+460h+var_3EC], 209h
0x1800333c6  jmp     short loc_1800333E0
0x1800333c8  mov     eax, 222h
0x1800333cd  jmp     short loc_1800333DB
0x1800333cf  mov     eax, 0E2h
0x1800333d4  jmp     short loc_1800333DB
0x1800333d6  mov     eax, 0B5h
0x1800333db  mov     word ptr [rsp+460h+var_3EC], ax
0x1800333e0  mov     rcx, [rbp+360h+var_290]
0x1800333e7  lea     rdx, [rcx+0D0h]; wchar_t ***
0x1800333ee  add     rcx, 0CCh; unsigned int *
0x1800333f5  mov     r8, r14; wchar_t *
0x1800333f8  call    ?DPAppendString@@YAJAEAKPEAPEAPEA_WPEB_W@Z; DPAppendString(ulong &,wchar_t * * *,wchar_t const *)
0x1800333fd  mov     r13, [rbp+360h+var_3B0]
0x180033401  movups  xmm0, xmmword ptr [r15+0C8h]
0x180033409  mov     ecx, [r15+0D8h]
0x180033410  mov     rax, [rbp+360h+var_290]
0x180033417  movups  xmmword ptr [rax+0ECh], xmm0
0x18003341e  mov     [rax+0FCh], ecx
0x180033424  mov     rdi, [rbp+360h+var_290]
0x18003342b  test    rdi, rdi
0x18003342e  jz      short loc_180033484
0x180033430  call    ?GetEnterprisePolicy_IsWUfBDeferralActive@@YA_NXZ; GetEnterprisePolicy_IsWUfBDeferralActive(void)
0x180033435  movzx   eax, al
0x180033438  mov     [rdi+40h], eax
0x18003343b  call    ?GetEnterprisePolicy_IsWUfBDeferralActive@@YA_NXZ; GetEnterprisePolicy_IsWUfBDeferralActive(void)
0x180033440  test    al, al
0x180033442  jz      short loc_180033452
0x180033444  call    ?IsPolicyDrivenServiceEnabled@@YA_NXZ; IsPolicyDrivenServiceEnabled(void)
0x180033449  test    al, al
0x18003344b  mov     eax, 1
0x180033450  jnz     short loc_180033454
0x180033452  mov     eax, esi
0x180033454  mov     [rdi+44h], eax
0x180033457  mov     [rsp+460h+var_3F0], sil
0x18003345c  lea     rcx, [rsp+460h+var_3F0]; bool *
0x180033461  call    ?GetEnterprisePolicy_IsPauseQualityUpdateEnabled@@YA_NAEA_N@Z; GetEnterprisePolicy_IsPauseQualityUpdateEnabled(bool &)
0x180033466  cmp     [rsp+460h+var_3F0], sil
0x18003346b  jz      short loc_180033470
0x18003346d  mov     [rdi+58h], al
0x180033470  lea     rcx, [rsp+460h+var_3F0]; bool *
0x180033475  call    ?GetEnterprisePolicy_IsPauseFeatureUpdateEnabled@@YA_NAEA_N@Z; GetEnterprisePolicy_IsPauseFeatureUpdateEnabled(bool &)
0x18003347a  cmp     [rsp+460h+var_3F0], sil
0x18003347f  jz      short loc_180033484
0x180033481  mov     [rdi+59h], al
0x180033484  mov     rcx, [rbp+360h+var_290]; struct tagUpdateDeploymentReportingData *
0x18003348b  call    ?PopulateSystemProps@@YAXPEAUtagUpdateDeploymentReportingData@@@Z; PopulateSystemProps(tagUpdateDeploymentReportingData *)
0x180033490  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_ModernStandby@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_ModernStandby@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_ModernStandby> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_ModernStandby>::GetImpl(void)'::`2'::impl
0x180033497  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_ModernStandby@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_ModernStandby>::__private_IsEnabled(void)
0x18003349c  mov     r14d, 800h
0x1800334a2  test    al, al
0x1800334a4  jz      loc_18003362D
0x1800334aa  mov     rcx, [rbp+360h+var_290]
0x1800334b1  mov     eax, [rcx+16Ch]
0x1800334b7  test    [r13+318h], r14d
0x1800334be  jz      loc_180033623
0x1800334c4  or      eax, r14d
0x1800334c7  jmp     loc_180033627
0x1800334cc  test    esi, esi
0x1800334ce  jns     loc_18003356C
0x1800334d4  mov     r8d, esi
0x1800334d7  mov     edx, r13d
0x1800334da  mov     r13, [rbp+360h+var_3B0]
0x1800334de  mov     rcx, r13
0x1800334e1  call    ?GetDeploymentFailureEventID@CUpdateDeploymentJob@@AEAAFW4tagDeploymentOperation@@J@Z; CUpdateDeploymentJob::GetDeploymentFailureEventID(tagDeploymentOperation,long)
0x1800334e6  mov     word ptr [rsp+460h+var_3EC], ax
0x1800334eb  movzx   ecx, byte ptr [r15+98h]
0x1800334f3  mov     rax, [rbp+360h+var_290]
0x1800334fa  mov     [rax+134h], ecx
0x180033500  mov     dword ptr [rsp+460h+var_430], esi
0x180033504  mov     qword ptr [rsp+460h+cchCount2], r10; wchar_t *
0x180033509  mov     dword ptr [rsp+460h+lpString2], 100h; unsigned int
0x180033511  xor     r9d, r9d; unsigned __int64 *
0x180033514  xor     r8d, r8d; wchar_t **
0x180033517  lea     edx, [r9+14h]; unsigned __int64
0x18003351b  lea     rcx, [rbp+360h+Buffer]; Buffer
0x180033522  call    ?StringCchPrintfExW@@YAJPEA_W_KPEAPEA_WPEA_KKPEB_WZZ; StringCchPrintfExW(wchar_t *,unsigned __int64,wchar_t * *,unsigned __int64 *,ulong,wchar_t const *,...)
0x180033527  mov     rcx, [rbp+360h+var_290]
0x18003352e  lea     rdx, [rcx+0D0h]; wchar_t ***
0x180033535  add     rcx, 0CCh; unsigned int *
0x18003353c  lea     r8, [rbp+360h+Buffer]; wchar_t *
0x180033543  call    ?DPAppendString@@YAJAEAKPEAPEAPEA_WPEB_W@Z; DPAppendString(ulong &,wchar_t * * *,wchar_t const *)
0x180033548  mov     rcx, [rbp+360h+var_290]
0x18003354f  lea     rdx, [rcx+0D0h]; wchar_t ***
0x180033556  add     rcx, 0CCh; unsigned int *
0x18003355d  mov     r8, r14; wchar_t *
0x180033560  call    ?DPAppendString@@YAJAEAKPEAPEAPEA_WPEB_W@Z; DPAppendString(ulong &,wchar_t * * *,wchar_t const *)
0x180033565  xor     esi, esi
0x180033567  jmp     loc_180033401
0x18003356c  mov     r10d, [r15+68h]
0x180033570  xor     esi, esi
0x180033572  test    r10d, r10d
0x180033575  setnz   r8b
0x180033579  mov     edx, [r15+38h]
0x18003357d  call    ?GetDeploymentSuccessEventID@CUpdateDeploymentJob@@AEAAFW4tagDeploymentOperation@@H@Z; CUpdateDeploymentJob::GetDeploymentSuccessEventID(tagDeploymentOperation,int)
0x180033582  mov     word ptr [rsp+460h+var_3EC], ax
0x180033587  mov     rax, [rbp+360h+var_290]
0x18003358e  lea     rcx, [rax+0C8h]
0x180033595  test    rcx, rcx
0x180033598  jz      short loc_1800335AF
0x18003359a  cmp     [rcx], esi
0x18003359c  jnz     short loc_1800335AF
0x18003359e  neg     r10d
0x1800335a1  sbb     eax, eax
0x1800335a3  add     eax, 2
0x1800335a6  mov     [rcx], eax
0x1800335a8  mov     rax, [rbp+360h+var_290]
0x1800335af  mov     edx, [rax+16Ch]
0x1800335b5  mov     ecx, edx
0x1800335b7  btr     ecx, 7
0x1800335bb  bts     edx, 7
0x1800335bf  cmp     dword ptr [rax+0C8h], 1
0x1800335c6  cmovnz  edx, ecx
0x1800335c9  mov     [rax+16Ch], edx
0x1800335cf  mov     rcx, [rbp+360h+var_290]
0x1800335d6  lea     rdx, [rcx+0D0h]; wchar_t ***
0x1800335dd  add     rcx, 0CCh; unsigned int *
0x1800335e4  mov     r8, r14; wchar_t *
0x1800335e7  call    ?DPAppendString@@YAJAEAKPEAPEAPEA_WPEB_W@Z; DPAppendString(ulong &,wchar_t * * *,wchar_t const *)
0x1800335ec  test    byte ptr [r15+218h], 20h
0x1800335f4  jz      loc_1800333FD
0x1800335fa  mov     r13, [rbp+360h+var_3B0]
0x1800335fe  cmp     dword ptr [r15+38h], 1
0x180033603  jnz     loc_180033401
0x180033609  movzx   ecx, byte ptr [r15+99h]
0x180033611  mov     rax, [rbp+360h+var_290]
0x180033618  mov     [rax+190h], ecx
0x18003361e  jmp     loc_180033401
0x180033623  btr     eax, 0Bh
0x180033627  mov     [rcx+16Ch], eax
0x18003362d  mov     [rbp+360h+var_280], rsi
  ... truncated ...
```
