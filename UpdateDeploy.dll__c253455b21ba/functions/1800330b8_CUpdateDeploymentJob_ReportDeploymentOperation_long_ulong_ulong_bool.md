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
  _QWORD *v11; // rbx
  TraceLoggingCorrelationVector *v12; // rcx
  volatile signed __int64 *v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rdi
  void (__fastcall *v16)(__int64, void **); // rsi
  __int64 v17; // r8
  BOOL v18; // ecx
  int v19; // ecx
  int v20; // r12d
  _BOOL8 v21; // rcx
  unsigned int v22; // esi
  __int16 v23; // ax
  CUpdateDeploymentJob *v24; // r13
  int v25; // ecx
  wchar_t **v26; // rax
  wchar_t **v27; // rdi
  bool v28; // zf
  int v29; // eax
  bool IsPauseQualityUpdateEnabled; // al
  bool IsPauseFeatureUpdateEnabled; // al
  int v32; // eax
  unsigned int v33; // eax
  __int64 v34; // rdx
  const wchar_t *v35; // r10
  int v36; // r10d
  wchar_t **v37; // rax
  wchar_t **v38; // rcx
  unsigned int v39; // edx
  int v40; // eax
  unsigned int v41; // eax
  __int64 v42; // r14
  BOOL v43; // edi
  const WCHAR *v44; // r8
  BOOL v45; // eax
  int v46; // eax
  unsigned int v47; // eax
  BSTR v48; // rdi
  unsigned int i; // esi
  int v50; // ecx
  unsigned __int64 v51; // rcx
  void *v52; // rax
  struct tagUpdateDeploymentReportingData *v53; // rcx
  unsigned int v54; // r12d
  _WORD *v55; // rax
  BSTR v56; // rax
  int v57; // ecx
  struct tagUpdateDeploymentReportingData *v58; // rax
  int v59; // eax
  __int64 v60; // xmm0_8
  int v61; // ecx
  struct tagUpdateDeploymentReportingData *v62; // rax
  int v63; // eax
  int v64; // r9d
  int v65; // r12d
  bool updated; // al
  unsigned int v67; // edx
  unsigned int v68; // ecx
  int v69; // eax
  char v70; // r8
  unsigned int v71; // ecx
  unsigned int v72; // edx
  const wchar_t *v73; // rcx
  int v74; // r10d
  struct tagUpdateDeploymentReportingData *v75; // rax
  _DWORD *v76; // rdx
  unsigned int v77; // edx
  struct tagUpdateDeploymentReportingData *v78; // rax
  wchar_t **v79; // rdx
  unsigned __int16 *v80; // rcx
  void *v81; // rax
  __int64 v82; // rcx
  void *v83; // rax
  struct tagUpdateDeploymentReportingData *v84; // rax
  __int64 v85; // rcx
  int v86; // ecx
  __int64 RegKeyPath; // rax
  __int64 v88; // rcx
  unsigned int v89; // esi
  int v90; // r12d
  struct tagUpdateDeploymentReportingData *v91; // rax
  wchar_t **v92; // rcx
  unsigned int v93; // r12d
  HKEY v94; // rdx
  int v95; // r12d
  __int64 v96; // r10
  struct tagUpdateDeploymentReportingData *v97; // rdx
  int v98; // eax
  int v99; // esi
  struct tagUpdateDeploymentReportingData *v100; // rdx
  int v101; // esi
  __int64 v102; // rdi
  BOOL v103; // r8d
  unsigned int v104; // ecx
  unsigned int v105; // ecx
  int v106; // eax
  char v107; // r8
  unsigned int v108; // ecx
  unsigned int v109; // edx
  int v110; // r14d
  unsigned int j; // esi
  unsigned int v112; // esi
  const wchar_t *v113; // rcx
  unsigned __int64 v114; // rcx
  wchar_t *v115; // rax
  wchar_t **v116; // rax
  unsigned int v117; // r14d
  __int64 v118; // r13
  const OLECHAR *v119; // rcx
  BSTR v120; // rax
  int v121; // eax
  wchar_t *v122; // xmm0_8
  int v123; // ecx
  wchar_t **v124; // rax
  unsigned int v125; // r14d
  wchar_t **v126; // rdx
  unsigned __int16 *v127; // rcx
  wchar_t *v128; // rax
  wchar_t *v129; // rcx
  wchar_t *v130; // rax
  wchar_t *v131; // rcx
  wchar_t **v132; // rdx
  __int64 v133; // r8
  int v134; // r14d
  struct tagUpdateDeploymentReportingData *v135; // rdx
  int v136; // r14d
  _QWORD *v137; // rax
  __int64 v138; // r9
  __int64 v139; // r8
  __int64 v140; // rcx
  wchar_t **v141; // rdx
  int v142; // eax
  int v143; // edi
  unsigned int v144; // r8d
  int v145; // edi
  __int64 v146; // rax
  OLECHAR *v147; // rdi
  unsigned int v148; // edx
  unsigned int v149; // r8d
  int inited; // esi
  const wchar_t *v151; // rax
  int v152; // edi
  UINT v153; // r14d
  void *v154; // rcx
  int v155; // r14d
  int v156; // eax
  PCNZWCH lpString2; // [rsp+20h] [rbp-E0h]
  __int64 v158; // [rsp+30h] [rbp-D0h]
  bool v159[4]; // [rsp+70h] [rbp-90h] BYREF
  int v160; // [rsp+74h] [rbp-8Ch]
  int v161; // [rsp+78h] [rbp-88h]
  int v162; // [rsp+7Ch] [rbp-84h]
  int v163; // [rsp+80h] [rbp-80h]
  int v164; // [rsp+84h] [rbp-7Ch]
  int v165; // [rsp+88h] [rbp-78h] BYREF
  int v166; // [rsp+8Ch] [rbp-74h] BYREF
  unsigned int v167; // [rsp+90h] [rbp-70h] BYREF
  BSTR bstr; // [rsp+98h] [rbp-68h] BYREF
  int v169; // [rsp+A0h] [rbp-60h]
  int v170; // [rsp+A4h] [rbp-5Ch]
  int v171; // [rsp+A8h] [rbp-58h]
  CUpdateDeploymentJob *v172; // [rsp+B0h] [rbp-50h]
  _QWORD *v173; // [rsp+B8h] [rbp-48h] BYREF
  unsigned int v174; // [rsp+C0h] [rbp-40h]
  struct tagUpdateDeploymentReportingData **v175; // [rsp+C8h] [rbp-38h]
  char v176; // [rsp+D0h] [rbp-30h]
  _QWORD *v177; // [rsp+D8h] [rbp-28h]
  void **v178; // [rsp+E0h] [rbp-20h]
  char v179; // [rsp+E8h] [rbp-18h]
  _BYTE v180[80]; // [rsp+F0h] [rbp-10h] BYREF
  wchar_t ***v181; // [rsp+140h] [rbp+40h]
  struct tagUpdateDeploymentReportingData **v182; // [rsp+148h] [rbp+48h]
  char v183; // [rsp+150h] [rbp+50h]
  char v184[112]; // [rsp+160h] [rbp+60h] BYREF
  wchar_t **v185; // [rsp+1D0h] [rbp+D0h] BYREF
  struct tagUpdateDeploymentReportingData *v186; // [rsp+1D8h] [rbp+D8h] BYREF
  void *v187; // [rsp+1E0h] [rbp+E0h] BYREF
  HKEY hKey; // [rsp+1E8h] [rbp+E8h] BYREF
  struct tagUpdateDeploymentReportingData *v189; // [rsp+1F0h] [rbp+F0h] BYREF
  void *lpMem; // [rsp+1F8h] [rbp+F8h] BYREF
  void *p_hKey; // [rsp+200h] [rbp+100h] BYREF
  __int64 v192; // [rsp+208h] [rbp+108h]
  int v193; // [rsp+210h] [rbp+110h]
  int v194; // [rsp+214h] [rbp+114h]
  __int64 v195; // [rsp+218h] [rbp+118h]
  _QWORD v196[8]; // [rsp+220h] [rbp+120h] BYREF
  _BYTE v197[96]; // [rsp+260h] [rbp+160h] BYREF
  wchar_t Buffer; // [rsp+2C0h] [rbp+1C0h] BYREF
  __int128 v199; // [rsp+2C2h] [rbp+1C2h]
  __int128 v200; // [rsp+2D2h] [rbp+1D2h]
  int v201; // [rsp+2E2h] [rbp+1E2h]
  __int16 v202; // [rsp+2E6h] [rbp+1E6h]
  __int128 v203; // [rsp+2F0h] [rbp+1F0h] BYREF
  __int128 v204; // [rsp+300h] [rbp+200h]
  __int128 v205; // [rsp+310h] [rbp+210h]
  __int128 v206; // [rsp+320h] [rbp+220h]
  __int128 v207; // [rsp+330h] [rbp+230h]
  __int128 v208; // [rsp+340h] [rbp+240h]
  __int128 v209; // [rsp+350h] [rbp+250h]
  __int128 v210; // [rsp+360h] [rbp+260h]
  char v211; // [rsp+370h] [rbp+270h]
  __int128 v212; // [rsp+380h] [rbp+280h] BYREF
  __int128 v213; // [rsp+390h] [rbp+290h]
  __int128 v214; // [rsp+3A0h] [rbp+2A0h]
  __int128 v215; // [rsp+3B0h] [rbp+2B0h]
  __int128 v216; // [rsp+3C0h] [rbp+2C0h]
  __int128 v217; // [rsp+3D0h] [rbp+2D0h]
  __int128 v218; // [rsp+3E0h] [rbp+2E0h]
  __int128 v219; // [rsp+3F0h] [rbp+2F0h]
  char v220; // [rsp+400h] [rbp+300h]
  wil::details::in1diag3 *retaddr; // [rsp+468h] [rbp+368h]

  v174 = a4;
  v6 = a2;
  v162 = a2;
  v172 = (CUpdateDeploymentJob *)this;
  if ( a4 >= this[43].Data1 )
    return;
  _mm_lfence();
  v163 = 0;
  v8 = *(_QWORD **)(*(_QWORD *)this[43].Data4 + 8LL * a4);
  v177 = v8;
  v9 = *((_DWORD *)v8 + 14);
  Buffer = 0;
  v199 = 0;
  v200 = 0;
  v201 = 0;
  v202 = 0;
  v10 = (const wchar_t *)v8[55];
  v170 = *((_DWORD *)v8 + 60);
  v161 = v8[67] & 0x200;
  memset(v196, 0, sizeof(v196));
  v196[0] = &CSusArrayList<tagDeploymentReportingUpdateEvent,CSusArrayListItemOpDeploymentReportingUpdateEvent>::`vftable';
  v196[1] = 0;
  v196[2] = 0;
  v196[3] = &CSusArrayList<tagDeploymentReportingUpdateEvent,CSusArrayListItemOpDeploymentReportingUpdateEvent>::`vftable';
  memset(&v196[4], 0, 28);
  v11 = 0;
  v173 = 0;
  v185 = 0;
  v189 = 0;
  v167 = 0;
  v171 = 0;
  v169 = 0;
  v164 = 0;
  lpMem = 0;
  v181 = &v185;
  v182 = &v189;
  v183 = 1;
  v12 = (TraceLoggingCorrelationVector *)v8[73];
  LOBYTE(v203) = 0;
  if ( v12 )
    TraceLoggingCorrelationVector::Increment(v12, (char *)&v203);
  v13 = (volatile signed __int64 *)v8[74];
  if ( v13 )
    TraceLoggingCorrelationVector::ToStringImpl(
      (TraceLoggingCorrelationVector *)v13,
      _InterlockedExchangeAdd64(v13 + 17, 0),
      (char *)&v212);
  else
    LOBYTE(v212) = 0;
  if ( (int)WuSmartPtr::XPtrBase<tagDeployableUpdateData,WuSmartPtr::Policies::STPolicy<tagDeployableUpdateData>>::ReleaseAndAlloc(&v185) >= 0 )
  {
    memset(v185, 0, 0x288u);
    DPCopyString(L"1.0.0.6", v185);
    *((_DWORD *)v185 + 101) = 1;
    if ( (v8[67] & 0x20) != 0 )
    {
      v15 = *(_QWORD *)&this[44].Data1;
      v16 = *(void (__fastcall **)(__int64, void **))(*(_QWORD *)v15 + 128LL);
      if ( lpMem )
      {
        SusFree(lpMem);
        lpMem = 0;
      }
      v16(v15, &lpMem);
      v6 = v162;
    }
    v17 = 0;
    if ( !a5 )
      *((_DWORD *)v8 + 140) = 1;
    *((_DWORD *)v185 + 25) = a3;
    v18 = (v8[67] & 0xC0) != 0;
    *((_DWORD *)v185 + 38) = v18;
    if ( !v18 || (v19 = 1, v6 >= 0) )
      v19 = 0;
    *((_DWORD *)v185 + 39) = v19;
    v20 = v161;
    v21 = v161 != 0;
    *((_DWORD *)v185 + 98) = v21;
    if ( !a5 )
    {
      if ( v6 >= 0 )
      {
        v22 = 0;
        LOBYTE(v17) = *((_DWORD *)v8 + 26) != 0;
        LOWORD(v160) = CUpdateDeploymentJob::GetDeploymentSuccessEventID(v21, *((unsigned int *)v8 + 14), v17);
        v37 = v185;
        v38 = v185 + 25;
        if ( v185 != (wchar_t **)-200LL && !*(_DWORD *)v38 )
        {
          *(_DWORD *)v38 = 2 - (v36 != 0);
          v37 = v185;
        }
        v39 = *((_DWORD *)v37 + 91) | 0x80;
        if ( *((_DWORD *)v37 + 50) != 1 )
          v39 = *((_DWORD *)v37 + 91) & 0xFFFFFF7F;
        *((_DWORD *)v37 + 91) = v39;
        DPAppendString((unsigned int *)v185 + 51, (wchar_t ***)v185 + 26, v10);
        if ( (v8[67] & 0x20) == 0 )
          goto LABEL_29;
        v24 = v172;
        if ( *((_DWORD *)v8 + 14) == 1 )
          *((_DWORD *)v185 + 100) = *((unsigned __int8 *)v8 + 153);
      }
      else
      {
        v34 = v9;
        v24 = v172;
        LOWORD(v160) = CUpdateDeploymentJob::GetDeploymentFailureEventID(v172, v34, (unsigned int)v6);
        *((_DWORD *)v185 + 77) = *((unsigned __int8 *)v8 + 152);
        StringCchPrintfExW(&Buffer, 0x14u, 0, 0, 0x100u, v35);
        DPAppendString((unsigned int *)v185 + 51, (wchar_t ***)v185 + 26, &Buffer);
        DPAppendString((unsigned int *)v185 + 51, (wchar_t ***)v185 + 26, v10);
        v22 = 0;
      }
LABEL_30:
      v25 = *((_DWORD *)v8 + 54);
      v26 = v185;
      *(_OWORD *)((char *)v185 + 236) = *(_OWORD *)(v8 + 25);
      *((_DWORD *)v26 + 63) = v25;
      v27 = v185;
      if ( v185 )
      {
        *((_DWORD *)v27 + 16) = GetEnterprisePolicy_IsWUfBDeferralActive();
        if ( !GetEnterprisePolicy_IsWUfBDeferralActive() || (v28 = !IsPolicyDrivenServiceEnabled(), v29 = 1, v28) )
          v29 = 0;
        *((_DWORD *)v27 + 17) = v29;
        v159[0] = 0;
        IsPauseQualityUpdateEnabled = GetEnterprisePolicy_IsPauseQualityUpdateEnabled(v159);
        if ( v159[0] )
          *((_BYTE *)v27 + 88) = IsPauseQualityUpdateEnabled;
        IsPauseFeatureUpdateEnabled = GetEnterprisePolicy_IsPauseFeatureUpdateEnabled(v159);
        if ( v159[0] )
          *((_BYTE *)v27 + 89) = IsPauseFeatureUpdateEnabled;
      }
      PopulateSystemProps((struct tagUpdateDeploymentReportingData *)v185);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_ModernStandby>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_ModernStandby>::GetImpl'::`2'::impl) )
      {
        v32 = *((_DWORD *)v185 + 91);
        if ( (*((_DWORD *)v24 + 198) & 0x800) != 0 )
          v33 = v32 | 0x800;
        else
          v33 = v32 & 0xFFFFF7FF;
        *((_DWORD *)v185 + 91) = v33;
      }
      v187 = 0;
      p_hKey = &v187;
      LOBYTE(v192) = 1;
      if ( (int)WuSmartPtr::XPtrBase<tagDeployableUpdateData,WuSmartPtr::Policies::STPolicy<tagDeployableUpdateData>>::ReleaseAndAlloc(&v187) >= 0 )
      {
        switch ( *((_DWORD *)v8 + 14) )
        {
          case 1:
            v40 = 1;
            break;
          case 2:
            v40 = 2;
            break;
          case 4:
            v40 = 4;
            break;
          default:
            v40 = *((_DWORD *)v8 + 14) == 8 ? 8 : 0;
            break;
        }
        LODWORD(lpString2) = v40;
        v22 = 0;
        if ( (*(int (__fastcall **)(_QWORD, __int64, _QWORD, __int64))(**((_QWORD **)v24 + 89) + 24LL))(
               *((_QWORD *)v24 + 89),
               2,
               *((unsigned int *)v24 + 200),
               2048) >= 0 )
        {
          DPPopulateProductRelatedData(
            (const struct tagDSUpdateMetadata *)((char *)v187 + 8),
            (struct tagUpdateDeploymentReportingData *)v185);
          *((_DWORD *)v185 + 137) = *((_DWORD *)v187 + 11);
          *((_DWORD *)v185 + 138) = *((_DWORD *)v187 + 12);
          *((_DWORD *)v185 + 148) = *((_DWORD *)v187 + 48);
        }
      }
      DPFreeDeployableUpdateData(v187);
      if ( v187 )
        operator delete(v187, (const struct std::nothrow_t *)0x288);
      *((_OWORD *)v185 + 32) = *(_OWORD *)(v8 + 63);
      DuplicateOptionalString<wchar_t *,wchar_t *>(v8[71], v185 + 66);
      if ( v170 )
      {
        *((_DWORD *)v185 + 69) = 7;
        v41 = 0;
        v166 = 0;
        if ( !*((_DWORD *)v8 + 136) )
          goto LABEL_279;
        while ( 1 )
        {
          LODWORD(hKey) = 0;
          v186 = 0;
          *(_DWORD *)v159 = 0;
          v165 = -1;
          v42 = *(_QWORD *)(v8[69] + 8LL * v41);
          if ( !*(_DWORD *)(v42 + 100) && *(_DWORD *)(v42 + 92) != -2145124299 )
            v22 = 1;
          v43 = 0;
          if ( a5 )
            v43 = CUpdateDeploymentJob::GetProcessedUpdateResult(
                    v24,
                    *(const wchar_t **)(v42 + 16),
                    (int *)&hKey,
                    (unsigned int *)v159) < 0;
          v45 = ((v175 = &v186,
                  v176 = 1,
                  v44 = *(const WCHAR **)(v42 + 80),
                  v44 == L"http://schemas.microsoft.com/msus/2016/01/UpdateHandlers/OSInstaller")
              || v44
              && CompareStringW(
                   0x7Fu,
                   1u,
                   v44,
                   -1,
                   L"http://schemas.microsoft.com/msus/2016/01/UpdateHandlers/OSInstaller",
                   -1) == 2)
             && *(_DWORD *)(v42 + 104);
          v164 |= v45;
          if ( v22 )
          {
            v22 = 0;
          }
          else
          {
            v22 = 0;
            if ( !v43 )
              goto LABEL_82;
          }
          WuSmartPtr::XPtrBase<tagDeployableUpdateData,WuSmartPtr::Policies::STPolicy<tagDeployableUpdateData>>::ReleaseAndAlloc(&v186);
          if ( v186 )
            break;
          v176 = 0;
          FreeObject(0);
LABEL_83:
          if ( v186 )
            operator delete(v186, (const struct std::nothrow_t *)0x288);
LABEL_200:
          v41 = v166 + 1;
          v166 = v41;
          if ( v41 >= *((_DWORD *)v8 + 136) )
            goto LABEL_279;
        }
        memset(v186, 0, 0x288u);
        *(_WORD *)v159 = v160;
        *((_DWORD *)v186 + 101) = 1;
        *((_OWORD *)v186 + 32) = *(_OWORD *)(v8 + 63);
        DuplicateOptionalString<wchar_t *,wchar_t *>(v8[71], (char *)v186 + 528);
        PopulateSystemProps(v186);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_ModernStandby>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_ModernStandby>::GetImpl'::`2'::impl) )
        {
          v46 = *((_DWORD *)v186 + 91);
          if ( (*((_DWORD *)v24 + 198) & 0x800) != 0 )
            v47 = v46 | 0x800;
          else
            v47 = v46 & 0xFFFFF7FF;
          *((_DWORD *)v186 + 91) = v47;
        }
        v48 = 0;
        bstr = 0;
        if ( v20 )
        {
          if ( (int)CUpdateDeploymentJob::GetUpdateTitle(
                      v24,
                      *(const wchar_t **)(v42 + 16),
                      *(_DWORD *)(v42 + 24),
                      *(const wchar_t **)(v42 + 48),
                      *(const wchar_t **)(v42 + 64),
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
              FreeObject(v186);
              if ( v186 )
                operator delete(v186, (const struct std::nothrow_t *)0x288);
              goto LABEL_279;
            }
          }
          v48 = bstr;
        }
        if ( *(_DWORD *)(v42 + 272) )
        {
          do
            DPAppendString(
              (unsigned int *)v186 + 40,
              (wchar_t ***)v186 + 21,
              *(const wchar_t **)(*(_QWORD *)(v42 + 264) + 8LL * v22++));
          while ( v22 < *(_DWORD *)(v42 + 272) );
        }
        for ( i = 0; i < *(_DWORD *)(v42 + 376); ++i )
          DPAppendString(
            (unsigned int *)v185 + 44,
            (wchar_t ***)v185 + 23,
            *(const wchar_t **)(*(_QWORD *)(v42 + 368) + 8LL * i));
        CUHHandlerManager::HandlerUriToId(
          (CUpdateDeploymentJob *)((char *)v24 + 48),
          *(const wchar_t **)(v42 + 80),
          (enum tagUHUpdateHandler *)&v165);
        v50 = v165;
        *((_DWORD *)v186 + 69) = v165;
        if ( v50 == 8 )
          *((_DWORD *)v185 + 96) = 1;
        *((_OWORD *)v186 + 7) = *(_OWORD *)(v42 + 312);
        DPCopyString(*(const wchar_t **)(v42 + 328), (wchar_t **)v186 + 18);
        DPCopyString(*(const wchar_t **)(v42 + 336), (wchar_t **)v186 + 13);
        v22 = 0;
        if ( !SysStringLen(v185[18]) )
          DPCopyString(*(const wchar_t **)(v42 + 328), v185 + 18);
        if ( !SysStringLen(v185[13]) )
          DPCopyString(*(const wchar_t **)(v42 + 336), v185 + 13);
        *((_DWORD *)v186 + 98) = *(_DWORD *)(v42 + 304) != 0;
        *((_DWORD *)v186 + 78) = *(_DWORD *)(v42 + 240);
        DPCopyString(*(const wchar_t **)(v42 + 232), (wchar_t **)v186 + 40);
        DPCopyString(*(const wchar_t **)(v42 + 224), (wchar_t **)v186 + 41);
        DPCopyString(*(const wchar_t **)(v42 + 216), (wchar_t **)v186 + 42);
        if ( *(_QWORD *)(v42 + 280) && *(_DWORD *)(v42 + 288) )
        {
          do
            DPAppendBSTR(
              (unsigned int *)v186 + 54,
              (wchar_t ***)v186 + 28,
              *(wchar_t **)(*(_QWORD *)(v42 + 280) + 8LL * v22++));
          while ( v22 < *(_DWORD *)(v42 + 288) );
          v22 = 0;
        }
        v51 = *(unsigned int *)(v42 + 256);
        *((_DWORD *)v186 + 120) = v51;
        v52 = SafeSusAllocArray(v51, 8u);
        *((_QWORD *)v186 + 61) = v52;
        *((_QWORD *)v186 + 62) = SafeSusAllocArray(*((unsigned int *)v186 + 120), 4u);
        v53 = v186;
        if ( !*((_QWORD *)v186 + 61) || !*((_QWORD *)v186 + 62) )
        {
          if ( v48 )
          {
            SusFree(v48);
            v53 = v186;
          }
          v176 = 0;
          FreeObject(v53);
          goto LABEL_83;
        }
        v54 = 0;
        if ( *(_DWORD *)(v42 + 256) )
        {
          do
          {
            hKey = *(HKEY *)(v42 + 248);
            v55 = (_WORD *)*((_QWORD *)hKey + 2 * v54 + 1);
            if ( v55 && *v55 )
            {
              v56 = SysAllocString(*((const OLECHAR **)hKey + 2 * v54 + 1));
              *(_QWORD *)(*((_QWORD *)v186 + 61) + 8LL * v54) = v56;
              v53 = v186;
            }
            *(_DWORD *)(struct HKEY__ *)(*((_QWORD *)v53 + 62) + 4LL * v54) = *((_DWORD *)hKey + 4 * v54);
            ++v54;
            v53 = v186;
          }
          while ( v54 < *(_DWORD *)(v42 + 256) );
          v8 = v177;
          v24 = v172;
          v22 = 0;
        }
        *((_DWORD *)v53 + 38) = (*(_BYTE *)(v42 + 308) & 0xC0) != 0;
        *((_DWORD *)v186 + 39) = 0;
        v57 = *((_DWORD *)v8 + 54);
        v58 = v186;
        *((_OWORD *)v186 + 16) = *(_OWORD *)(v8 + 25);
        *((_DWORD *)v58 + 68) = v57;
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModelCacheGeneration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ModelCacheGeneration>::GetImpl'::`2'::impl) )
        {
          v59 = DuplicateOptionalString<wchar_t *,wchar_t *>(*(_QWORD *)(v42 + 384), (char *)v186 + 608);
          if ( v59 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x130D,
              (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentJob.cpp",
              (const char *)(unsigned int)v59,
              (int)lpString2);
          v60 = *(_QWORD *)(v42 + 408);
          v61 = *(_DWORD *)(v42 + 416);
          v62 = v186;
          *(_OWORD *)((char *)v186 + 616) = *(_OWORD *)(v42 + 392);
          *((_QWORD *)v62 + 79) = v60;
          *((_DWORD *)v62 + 160) = v61;
        }
        v187 = 0;
        v178 = &v187;
        v179 = 1;
        if ( (int)WuSmartPtr::XPtrBase<tagDeployableUpdateData,WuSmartPtr::Policies::STPolicy<tagDeployableUpdateData>>::ReleaseAndAlloc(&v187) < 0 )
        {
          LODWORD(lpString2) = v163;
          WUTrace(0, 0, 0x1000000, 3, lpString2, L"Fail to get update metadata for deployment reporting events.");
        }
        else
        {
          switch ( *(_DWORD *)(v42 + 56) )
          {
            case 1:
              v63 = 1;
              break;
            case 2:
              v63 = 2;
              break;
            case 4:
              v63 = 4;
              break;
            case 8:
              v63 = 8;
              break;
            default:
              v63 = 0;
              break;
          }
          LODWORD(lpString2) = v63;
          v22 = 0;
          if ( (*(int (__fastcall **)(_QWORD, __int64, _QWORD, __int64))(**((_QWORD **)v24 + 89) + 24LL))(
                 *((_QWORD *)v24 + 89),
                 2,
                 *((unsigned int *)v24 + 200),
                 3116) >= 0 )
          {
            hKey = 0;
            if ( (int)CUHHandlerManager::GetHandler(
                        (CUpdateDeploymentJob *)((char *)v24 + 48),
                        *(const wchar_t **)(v42 + 80),
                        1,
                        v64,
                        &GUID_3da6d224_c341_52ac_f168_5457166f1bba,
                        (void **)&hKey) >= 0 )
            {
              lpString2 = (PCNZWCH)v186;
              v65 = (*(__int64 (__fastcall **)(HKEY, char *, _QWORD, _QWORD))(*(_QWORD *)hKey + 24LL))(
                      hKey,
                      (char *)v187 + 8,
                      *(_QWORD *)(v42 + 64),
                      *(_QWORD *)(v42 + 136));
              if ( v65 < 0 )
              {
                Trace::GuidToString::GuidToString((Trace::GuidToString *)v180, (const struct _GUID *)v24 + 1);
                LODWORD(lpString2) = v65;
                WUTrace(
                  0,
                  0,
                  0x1000000,
                  5,
                  lpString2,
                  L"Deployment job Id %ws : Failed to query deployment custom reporting data from handler = %ws.");
                v22 = 0;
              }
            }
            if ( !a5 )
              *((_DWORD *)v186 + 99) = *(_DWORD *)(v42 + 352);
            *((_DWORD *)v186 + 74) = *(_DWORD *)(v42 + 348);
            *((_DWORD *)v186 + 71) = *((_DWORD *)v187 + 47);
            DPPopulateProductRelatedData((const struct tagDSUpdateMetadata *)((char *)v187 + 8), v186);
            updated = DidUpdateUseSystemVolume(*(PCNZWCH *)(v42 + 144));
            *((_DWORD *)v186 + 70) = updated;
            *((_DWORD *)v186 + 137) = *((_DWORD *)v187 + 11);
            *((_DWORD *)v186 + 138) = *((_DWORD *)v187 + 12);
            *((_DWORD *)v186 + 148) = *((_DWORD *)v187 + 48);
            v67 = *((_DWORD *)v186 + 91) | 1;
            if ( !*((_DWORD *)v186 + 70) )
              v67 = *((_DWORD *)v186 + 91) & 0xFFFFFFFE;
            *((_DWORD *)v186 + 91) = v67;
            v68 = *((_DWORD *)v186 + 91) | 0x10;
            if ( !*(_DWORD *)(v42 + 300) )
              v68 = *((_DWORD *)v186 + 91) & 0xFFFFFFEF;
            *((_DWORD *)v186 + 91) = v68;
            v69 = *((_DWORD *)v24 + 207);
            if ( v69 == 1 || (v70 = 0, (unsigned int)(v69 - 2) <= 1) )
              v70 = 1;
            v71 = *((_DWORD *)v186 + 91) | 0x20;
            if ( !v70 )
              v71 = *((_DWORD *)v186 + 91) & 0xFFFFFFDF;
            *((_DWORD *)v186 + 91) = v71;
            v72 = *((_DWORD *)v186 + 91) | 0x40;
            if ( !*((_DWORD *)v186 + 74) )
              v72 = *((_DWORD *)v186 + 91) & 0xFFFFFFBF;
            *((_DWORD *)v186 + 91) = v72;
            if ( hKey )
              (*(void (__fastcall **)(HKEY))(*(_QWORD *)hKey + 16LL))(hKey);
          }
        }
        v73 = *(const wchar_t **)(v42 + 200);
        if ( v73 )
          DPCopyString(v73, (wchar_t **)v186 + 24);
        if ( !a5 )
        {
          if ( *(int *)(v42 + 92) < 0 )
          {
            *((_DWORD *)v186 + 77) = *(unsigned __int8 *)(v42 + 152);
            *((_DWORD *)v186 + 39) = *((_DWORD *)v186 + 38);
            *((_DWORD *)v186 + 25) = *(_DWORD *)(v42 + 96);
            if ( v162 == *(_DWORD *)(v42 + 92) )
            {
              v91 = v186;
              if ( *((_DWORD *)v186 + 40) )
              {
                do
                {
                  DPAppendBSTR(
                    (unsigned int *)v185 + 40,
                    (wchar_t ***)v185 + 21,
                    *(wchar_t **)(*((_QWORD *)v91 + 21) + 8LL * v22++));
                  v91 = v186;
                }
                while ( v22 < *((_DWORD *)v186 + 40) );
              }
              *((_DWORD *)v185 + 78) = *((_DWORD *)v91 + 78);
              DPCopyBSTR(*((wchar_t **)v186 + 40), v185 + 40);
              DPCopyBSTR(*((wchar_t **)v186 + 41), v185 + 41);
              DPCopyBSTR(*((wchar_t **)v186 + 42), v185 + 42);
              *((_DWORD *)v185 + 120) = *((_DWORD *)v186 + 120);
              v185[61] = (wchar_t *)SafeSusAllocArray(*((unsigned int *)v186 + 120), 8u);
              v185[62] = (wchar_t *)SafeSusAllocArray(*((unsigned int *)v186 + 120), 4u);
              v92 = v185;
              v22 = 0;
              if ( !v185[61] || !v185[62] )
              {
                v179 = 0;
                DPFreeDeployableUpdateData(v187);
                if ( v187 )
                {
                  operator delete(v187, (const struct std::nothrow_t *)0x288);
                  v187 = 0;
                }
                if ( v48 )
                  SusFree(v48);
                v176 = 0;
                FreeObject(v186);
                if ( v186 )
                  operator delete(v186, (const struct std::nothrow_t *)0x288);
                v20 = v161;
                goto LABEL_200;
              }
              v93 = 0;
              v78 = v186;
              if ( *((_DWORD *)v186 + 120) )
              {
                while ( 1 )
                {
                  DPCopyBSTR(*(wchar_t **)(*((_QWORD *)v78 + 61) + 8LL * v93), (wchar_t **)&v92[61][4 * v93]);
                  *(_DWORD *)&v185[62][2 * v93] = *(_DWORD *)(*((_QWORD *)v186 + 62) + 4LL * v93);
                  ++v93;
                  v78 = v186;
                  if ( v93 >= *((_DWORD *)v186 + 120) )
                    break;
                  v92 = v185;
                }
              }
LABEL_169:
              UuidFromStringW(*(RPC_WSTR *)(v42 + 16), (UUID *)((char *)v78 + 236));
              *((_DWORD *)v186 + 63) = *(_DWORD *)(v42 + 24);
              DPAppendString((unsigned int *)v186 + 6, (wchar_t ***)v186 + 4, *((const wchar_t **)v24 + 85));
              PopulateFirstProcessNameIfAvailable(v186, v79);
              *((_DWORD *)v186 + 10) = *(__int16 *)v159;
              *((_DWORD *)v186 + 11) = 101;
              v80 = *(unsigned __int16 **)(v42 + 48);
              if ( v80 && *v80 )
                UuidFromStringW(v80, (UUID *)((char *)v186 + 8));
              DPCopyString(*(const wchar_t **)(v42 + 72), (wchar_t **)v186 + 44);
              v81 = operator new[](0x81u, (const struct std::nothrow_t *)&std::nothrow);
              *((_QWORD *)v186 + 54) = v81;
              v82 = *((_QWORD *)v186 + 54);
              if ( v82 )
              {
                *(_OWORD *)v82 = v203;
                *(_OWORD *)(v82 + 16) = v204;
                *(_OWORD *)(v82 + 32) = v205;
                *(_OWORD *)(v82 + 48) = v206;
                *(_OWORD *)(v82 + 64) = v207;
                *(_OWORD *)(v82 + 80) = v208;
                *(_OWORD *)(v82 + 96) = v209;
                *(_OWORD *)(v82 + 112) = v210;
                *(_BYTE *)(v82 + 128) = v211;
              }
              v83 = operator new[](0x81u, (const struct std::nothrow_t *)&std::nothrow);
              *((_QWORD *)v186 + 55) = v83;
              v84 = v186;
              v85 = *((_QWORD *)v186 + 55);
              if ( v85 )
              {
                *(_OWORD *)v85 = v212;
                *(_OWORD *)(v85 + 16) = v213;
                *(_OWORD *)(v85 + 32) = v214;
                *(_OWORD *)(v85 + 48) = v215;
                *(_OWORD *)(v85 + 64) = v216;
                *(_OWORD *)(v85 + 80) = v217;
                *(_OWORD *)(v85 + 96) = v218;
                *(_OWORD *)(v85 + 112) = v219;
                *(_BYTE *)(v85 + 128) = v220;
                v84 = v186;
              }
              if ( a5 )
              {
                *((_DWORD *)v84 + 24) = v162;
              }
              else
              {
                v86 = *(_DWORD *)(v42 + 92);
                if ( v86 >= 0 && *(_QWORD *)(v42 + 184) )
                {
                  hKey = 0;
                  RegKeyPath = GetRegKeyPath(13);
                  RegCreateKeyHelperPrivate(v88, RegKeyPath, L"DontExpirePolledEvents", &hKey);
                  if ( hKey )
                    RegCloseKey(hKey);
                  v165 = -1;
                  CUHHandlerManager::HandlerUriToId(
                    (CUpdateDeploymentJob *)((char *)v24 + 48),
                    *(const wchar_t **)(v42 + 80),
                    (enum tagUHUpdateHandler *)&v165);
                  v89 = v165;
                  if ( v165 == 8 || v165 == 12 )
                  {
                    v90 = 1;
                    v171 = 1;
                  }
                  else
                  {
                    v90 = v171;
                  }
                  if ( *(_DWORD *)(v42 + 304) || v165 == 8 || v165 == 12 )
                  {
                    hKey = 0;
                    p_hKey = &hKey;
                    LOBYTE(v192) = 1;
                    if ( (int)WuSmartPtr::XPtrBase<tagDeployableUpdateData,WuSmartPtr::Policies::STPolicy<tagDeployableUpdateData>>::ReleaseAndAlloc(&hKey) >= 0 )
                    {
                      memset(hKey, 0, 0x288u);
                      CloneUpdateDeploymentReportingData(v186, (struct tagUpdateDeploymentReportingData *)hKey);
                      *((_DWORD *)hKey + 10) = 201;
                      *((_DWORD *)hKey + 11) = 101;
                      *((_DWORD *)hKey + 24) = 2359301;
                      v94 = hKey;
                      hKey = 0;
                      v95 = CDeploymentReportingUpdateGroup::AddEvent(v196, v94, 3 - (unsigned int)(v90 != 0));
                      v163 = v95;
                      if ( v95 < 0 )
                      {
                        Trace::GuidToString::GuidToString((Trace::GuidToString *)v180, (const struct _GUID *)v24 + 1);
                        LODWORD(lpString2) = v95;
                        WUTrace(
                          0,
                          0,
                          0x1000000,
                          5,
                          lpString2,
                          L"Deployment job Id %ws : Deployment provider reports pending update");
                      }
                    }
                    LOBYTE(v192) = 0;
                    FreeObject((struct tagUpdateDeploymentReportingData *)hKey);
                    if ( hKey )
                      operator delete(hKey, (const struct std::nothrow_t *)0x288);
                  }
                  if ( v11
                    || (WuSmartPtr::XPtrBase<CDeploymentReportingUpdateGroup,WuSmartPtr::Policies::STPolicy<CDeploymentReportingUpdateGroup>>::ReleaseAndAlloc(&v173),
                        (v11 = v173) != 0) )
                  {
                    *((_DWORD *)v186 + 24) = 2367509;
                    v20 = v161;
                    if ( v161 )
                      DPAppendString((unsigned int *)v186 + 51, (wchar_t ***)v186 + 26, v48);
                    v96 = *(_QWORD *)(v42 + 184);
                    if ( *(_DWORD *)(v42 + 208) )
                      v89 = -1;
                    v97 = v186;
                    v186 = 0;
                    lpString2 = (PCNZWCH)lpMem;
                    v98 = CDeploymentReportingUpdateGroup::AddEventInternal(v11, v97, v89, v96);
                    v99 = v98;
                    v163 = v98;
                    if ( v98 >= 0 )
                    {
                      v99 = 0;
                      v163 = 0;
                    }
                    else
                    {
                      wil::details::in1diag3::Return_Hr(
                        retaddr,
                        (void *)0x5DF,
                        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\DPReportingData.cpp",
                        (const char *)(unsigned int)v98,
                        (int)lpString2);
                    }
                    if ( v99 < 0 )
                    {
                      Trace::GuidToString::GuidToString((Trace::GuidToString *)v180, (const struct _GUID *)v24 + 1);
                      LODWORD(lpString2) = v99;
                      WUTrace(
                        0,
                        0,
                        0x1000000,
                        5,
                        lpString2,
                        L"Deployment job Id %ws : UDP queues a child update for post-reboot reporting");
                    }
                    v167 = 1;
                  }
                  else
                  {
                    v20 = v161;
                  }
LABEL_232:
                  v22 = 0;
                  v179 = 0;
                  DPFreeDeployableUpdateData(v187);
                  if ( v187 )
                  {
                    operator delete(v187, (const struct std::nothrow_t *)0x288);
                    v187 = 0;
                  }
                  if ( v48 )
                    SusFree(v48);
LABEL_82:
                  v176 = 0;
                  FreeObject(v186);
                  goto LABEL_83;
                }
                *((_DWORD *)v84 + 24) = v86;
              }
              v20 = v161;
              if ( v161 )
              {
                if ( *(int *)(v42 + 92) < 0 )
                {
                  StringCchPrintfExW(&Buffer, 0x14u, 0, 0, 0x100u, L"%#lx");
                  DPAppendString((unsigned int *)v186 + 51, (wchar_t ***)v186 + 26, &Buffer);
                }
                DPAppendString((unsigned int *)v186 + 51, (wchar_t ***)v186 + 26, v48);
              }
              v100 = v186;
              v186 = 0;
              v101 = CDeploymentReportingUpdateGroup::AddEvent(v196, v100, v20 != 0 ? 4 : 2);
              v163 = v101;
              if ( v101 < 0 )
              {
                Trace::GuidToString::GuidToString((Trace::GuidToString *)v180, (const struct _GUID *)v24 + 1);
                LODWORD(lpString2) = v101;
                WUTrace(0, 0, 0x1000000, 5, lpString2, L"Deployment job Id %ws : UDP reports a child update deployment");
              }
              goto LABEL_232;
            }
          }
          else
          {
            *(_WORD *)v159 = CUpdateDeploymentJob::GetDeploymentSuccessEventID(
                               v73,
                               *(unsigned int *)(v42 + 56),
                               *(_DWORD *)(v42 + 104) != 0);
            v75 = v186;
            v76 = (_DWORD *)((char *)v186 + 200);
            if ( v186 != (struct tagUpdateDeploymentReportingData *)-200LL && !*v76 )
            {
              *v76 = 2 - (v74 != 0);
              v75 = v186;
            }
            v77 = *((_DWORD *)v75 + 91) | 0x80;
            if ( *((_DWORD *)v75 + 50) != 1 )
              v77 = *((_DWORD *)v75 + 91) & 0xFFFFFF7F;
            *((_DWORD *)v75 + 91) = v77;
            if ( (v8[67] & 0x20) != 0 && *((_DWORD *)v8 + 14) == 1 )
              *((_DWORD *)v186 + 100) = *(unsigned __int8 *)(v42 + 153);
          }
        }
        v78 = v186;
        goto LABEL_169;
      }
      v102 = *(_QWORD *)v8[69];
      *((_DWORD *)v185 + 74) = *(_DWORD *)(v102 + 348);
      v103 = DidUpdateUseSystemVolume(*(PCNZWCH *)(v102 + 144));
      *((_DWORD *)v185 + 70) = v103;
      v104 = *((_DWORD *)v185 + 91) | 1;
      if ( !v103 )
        v104 = *((_DWORD *)v185 + 91) & 0xFFFFFFFE;
      *((_DWORD *)v185 + 91) = v104;
      v105 = *((_DWORD *)v185 + 91) | 0x10;
      if ( !*(_DWORD *)(v102 + 300) )
        v105 = *((_DWORD *)v185 + 91) & 0xFFFFFFEF;
      *((_DWORD *)v185 + 91) = v105;
      v106 = *((_DWORD *)v24 + 207);
      if ( v106 == 1 || (v107 = 0, (unsigned int)(v106 - 2) <= 1) )
        v107 = 1;
      v108 = *((_DWORD *)v185 + 91) | 0x20;
      if ( !v107 )
        v108 = *((_DWORD *)v185 + 91) & 0xFFFFFFDF;
      *((_DWORD *)v185 + 91) = v108;
      v109 = *((_DWORD *)v185 + 91) | 0x40;
      if ( !*((_DWORD *)v185 + 74) )
        v109 = *((_DWORD *)v185 + 91) & 0xFFFFFFBF;
      *((_DWORD *)v185 + 91) = v109;
      v166 = -1;
      CUHHandlerManager::HandlerUriToId(
        (CUpdateDeploymentJob *)((char *)v24 + 48),
        *(const wchar_t **)(v102 + 80),
        (enum tagUHUpdateHandler *)&v166);
      v110 = v166;
      if ( v166 != 12 || (v28 = *(_DWORD *)(v102 + 104) == 0, v164 = 1, v28) )
        v164 = 0;
      if ( *(_DWORD *)(v102 + 272) )
      {
        do
          DPAppendString(
            (unsigned int *)v185 + 40,
            (wchar_t ***)v185 + 21,
            *(const wchar_t **)(*(_QWORD *)(v102 + 264) + 8LL * v22++));
        while ( v22 < *(_DWORD *)(v102 + 272) );
      }
      for ( j = 0; j < *(_DWORD *)(v102 + 376); ++j )
        DPAppendString(
          (unsigned int *)v185 + 44,
          (wchar_t ***)v185 + 23,
          *(const wchar_t **)(*(_QWORD *)(v102 + 368) + 8LL * j));
      v112 = 0;
      *((_DWORD *)v185 + 96) = v110 == 8;
      *((_DWORD *)v185 + 69) = v110;
      *((_OWORD *)v185 + 7) = *(_OWORD *)(v102 + 312);
      DPCopyString(*(const wchar_t **)(v102 + 328), v185 + 18);
      DPCopyString(*(const wchar_t **)(v102 + 336), v185 + 13);
      *((_DWORD *)v185 + 78) = *(_DWORD *)(v102 + 240);
      DPCopyString(*(const wchar_t **)(v102 + 232), v185 + 40);
      DPCopyString(*(const wchar_t **)(v102 + 224), v185 + 41);
      DPCopyString(*(const wchar_t **)(v102 + 216), v185 + 42);
      v113 = *(const wchar_t **)(v102 + 200);
      if ( v113 )
        DPCopyString(v113, v185 + 24);
      *((_DWORD *)v185 + 38) = (*(_BYTE *)(v102 + 308) & 0xC0) != 0;
      if ( *(_QWORD *)(v102 + 280) && *(_DWORD *)(v102 + 288) )
      {
        do
          DPAppendBSTR(
            (unsigned int *)v185 + 54,
            (wchar_t ***)v185 + 28,
            *(wchar_t **)(*(_QWORD *)(v102 + 280) + 8LL * v112++));
        while ( v112 < *(_DWORD *)(v102 + 288) );
      }
      v114 = *(unsigned int *)(v102 + 256);
      *((_DWORD *)v185 + 120) = v114;
      v115 = (wchar_t *)SafeSusAllocArray(v114, 8u);
      v185[61] = v115;
      v185[62] = (wchar_t *)SafeSusAllocArray(*((unsigned int *)v185 + 120), 4u);
      v116 = v185;
      if ( v185[61] )
      {
        if ( v185[62] )
        {
          v117 = 0;
          if ( *(_DWORD *)(v102 + 256) )
          {
            do
            {
              v118 = *(_QWORD *)(v102 + 248);
              v119 = *(const OLECHAR **)(v118 + 16LL * v117 + 8);
              if ( v119 && *v119 )
              {
                v120 = SysAllocString(v119);
                *(_QWORD *)&v185[61][4 * v117] = v120;
                v116 = v185;
              }
              *(_DWORD *)&v116[62][2 * v117] = *(_DWORD *)(v118 + 16LL * v117);
              ++v117;
              v116 = v185;
            }
            while ( v117 < *(_DWORD *)(v102 + 256) );
            v24 = v172;
            v20 = v161;
          }
        }
      }
      *((_DWORD *)v116 + 25) = *(_DWORD *)(v102 + 96);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModelCacheGeneration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ModelCacheGeneration>::GetImpl'::`2'::impl) )
      {
        v121 = DuplicateOptionalString<wchar_t *,wchar_t *>(*(_QWORD *)(v102 + 384), v185 + 76);
        if ( v121 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x1500,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentJob.cpp",
            (const char *)(unsigned int)v121,
            (int)lpString2);
        v122 = *(wchar_t **)(v102 + 408);
        v123 = *(_DWORD *)(v102 + 416);
        v124 = v185;
        *(_OWORD *)(v185 + 77) = *(_OWORD *)(v102 + 392);
        v124[79] = v122;
        *((_DWORD *)v124 + 160) = v123;
      }
LABEL_279:
      v125 = v162;
      if ( a5 || v162 < 0 )
      {
        v169 = 0;
      }
      else if ( v170 )
      {
        v169 = v167;
      }
      else if ( *(_QWORD *)(*(_QWORD *)v8[69] + 184LL) )
      {
        v169 = 1;
      }
      DPAppendString((unsigned int *)v185 + 6, (wchar_t ***)v185 + 4, *((const wchar_t **)v24 + 85));
      PopulateFirstProcessNameIfAvailable((struct tagUpdateDeploymentReportingData *)v185, v126);
      *((_DWORD *)v185 + 10) = (__int16)v160;
      *((_DWORD *)v185 + 11) = 101;
      v127 = (unsigned __int16 *)v8[6];
      if ( v127 && *v127 )
        UuidFromStringW(v127, (UUID *)(v185 + 1));
      v128 = (wchar_t *)operator new[](0x81u, (const struct std::nothrow_t *)&std::nothrow);
      v185[54] = v128;
      v129 = v185[54];
      if ( v129 )
      {
        *(_OWORD *)v129 = v203;
        *((_OWORD *)v129 + 1) = v204;
        *((_OWORD *)v129 + 2) = v205;
        *((_OWORD *)v129 + 3) = v206;
        *((_OWORD *)v129 + 4) = v207;
        *((_OWORD *)v129 + 5) = v208;
        *((_OWORD *)v129 + 6) = v209;
        *((_OWORD *)v129 + 7) = v210;
        *((_BYTE *)v129 + 128) = v211;
      }
      v130 = (wchar_t *)operator new[](0x81u, (const struct std::nothrow_t *)&std::nothrow);
      v185[55] = v130;
      v131 = v185[55];
      if ( v131 )
      {
        *(_OWORD *)v131 = v212;
        *((_OWORD *)v131 + 1) = v213;
        *((_OWORD *)v131 + 2) = v214;
        *((_OWORD *)v131 + 3) = v215;
        *((_OWORD *)v131 + 4) = v216;
        *((_OWORD *)v131 + 5) = v217;
        *((_OWORD *)v131 + 6) = v218;
        *((_OWORD *)v131 + 7) = v219;
        *((_BYTE *)v131 + 128) = v220;
      }
      if ( v169 )
      {
        v134 = v171;
        if ( (v171 || v164)
          && (int)WuSmartPtr::XPtrBase<tagDeployableUpdateData,WuSmartPtr::Policies::STPolicy<tagDeployableUpdateData>>::ReleaseAndAlloc(&v189) >= 0 )
        {
          memset(v189, 0, 0x288u);
          CloneUpdateDeploymentReportingData((const struct tagUpdateDeploymentReportingData *)v185, v189);
          *((_DWORD *)v189 + 10) = 201;
          *((_DWORD *)v189 + 11) = 101;
          *((_DWORD *)v189 + 24) = 2359301;
          v135 = v189;
          v189 = 0;
          v136 = CDeploymentReportingUpdateGroup::AddEvent(v196, v135, v134 != 0 ? 1 : 3);
          if ( v136 < 0 )
          {
            Trace::GuidToString::GuidToString((Trace::GuidToString *)v180, (const struct _GUID *)v24 + 1);
            LODWORD(lpString2) = v136;
            WUTrace(0, 0, 0x1000000, 5, lpString2, L"Deployment job Id %ws : UDP reports pending CBS bundle");
          }
        }
        if ( !v11 )
        {
          v137 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
          v11 = v137;
          v177 = v137;
          if ( !v137 )
          {
            v11 = 0;
            v173 = 0;
            goto LABEL_313;
          }
          *v137 = &CSusArrayList<tagDeploymentReportingUpdateEvent,CSusArrayListItemOpDeploymentReportingUpdateEvent>::`vftable';
          v137[1] = 0;
          v137[2] = 0;
          v137[3] = &CSusArrayList<tagDeploymentReportingUpdateEvent,CSusArrayListItemOpDeploymentReportingUpdateEvent>::`vftable';
          v137[4] = 0;
          v137[5] = 0;
          *((_DWORD *)v137 + 12) = 0;
          *(_QWORD *)((char *)v137 + 52) = 0;
          v173 = v137;
        }
        *((_DWORD *)v185 + 24) = 2367509;
        *((_DWORD *)v185 + 39) = 0;
        if ( v170 )
        {
          lpString2 = 0;
          v138 = 0;
          v139 = 7;
        }
        else
        {
          v167 = -1;
          CUHHandlerManager::HandlerUriToId(
            (CUpdateDeploymentJob *)((char *)v24 + 48),
            *(const wchar_t **)(*(_QWORD *)v8[69] + 80LL),
            (enum tagUHUpdateHandler *)&v167);
          v140 = *(_QWORD *)v8[69];
          v138 = *(_QWORD *)(v140 + 184);
          v139 = v167;
          if ( *(_DWORD *)(v140 + 208) )
            v139 = 0xFFFFFFFFLL;
          lpString2 = (PCNZWCH)lpMem;
        }
        v141 = v185;
        v185 = 0;
        v142 = CDeploymentReportingUpdateGroup::AddEventInternal(v11, v141, v139, v138);
        if ( v142 < 0 )
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x5DF,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\DPReportingData.cpp",
            (const char *)(unsigned int)v142,
            (int)lpString2);
      }
      else
      {
        *((_DWORD *)v185 + 24) = v125;
        *((_DWORD *)v185 + 39) &= v125 >> 31;
        v132 = v185;
        v185 = 0;
        v133 = 3;
        if ( v170 )
          v133 = v20 != 0 ? 5 : 1;
        CDeploymentReportingUpdateGroup::AddEvent(v196, v132, v133);
      }
LABEL_313:
      v194 = 0;
      v192 = v196[1];
      p_hKey = (void *)HIDWORD(v196[2]);
      v196[1] = 0;
      v196[2] = 0;
      v195 = v196[4];
      v193 = HIDWORD(v196[5]);
      v196[4] = 0;
      v196[5] = 0;
      v143 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, void **))(**((_QWORD **)v24 + 91) + 48LL))(
               *((_QWORD *)v24 + 91),
               0,
               &p_hKey);
      if ( v143 < 0 )
      {
        Trace::GuidToString::GuidToString((Trace::GuidToString *)v180, (const struct _GUID *)v24 + 1);
        LODWORD(lpString2) = v143;
        WUTrace(0, 0, 0x1000000, 3, lpString2, L"Deployment job Id %ws : UDP reporting fail to report event");
      }
      CDeploymentReportingUpdateGroup::AttachEvents(
        (CDeploymentReportingUpdateGroup *)v196,
        (struct tagDeploymentReportingUpdateGroup *)&p_hKey);
      if ( !v11 )
        goto LABEL_333;
      HIDWORD(p_hKey) = 0;
      v194 = 0;
      v192 = v11[1];
      LODWORD(p_hKey) = *((_DWORD *)v11 + 5);
      v11[1] = 0;
      v11[2] = 0;
      v195 = v11[4];
      v193 = *((_DWORD *)v11 + 11);
      v11[4] = 0;
      v11[5] = 0;
      v145 = (*(__int64 (__fastcall **)(_QWORD, __int64, void **))(**((_QWORD **)v24 + 91) + 48LL))(
               *((_QWORD *)v24 + 91),
               1,
               &p_hKey);
      if ( v145 < 0 )
      {
        v146 = Trace::GuidToString::GuidToString((Trace::GuidToString *)v180, (const struct _GUID *)v24 + 1);
        LODWORD(lpString2) = v145;
        WUTrace(
          0,
          0,
          0x1000000,
          3,
          lpString2,
          L"Deployment job Id %ws : UDP reporting fail to report pending event group",
          v146);
      }
      CDeploymentReportingUpdateGroup::AttachEvents(
        (CDeploymentReportingUpdateGroup *)v11,
        (struct tagDeploymentReportingUpdateGroup *)&p_hKey);
      memset(v197, 0, sizeof(v197));
      CSerializationHelper::CSerializationHelper((CSerializationHelper *)v197);
      v147 = 0;
      bstr = 0;
      inited = CSerializationHelper::InitSerializeToStringWithHeader((CSerializationHelper *)v197, v148, v149);
      if ( inited >= 0 )
      {
        inited = CDeploymentReportingUpdateGroup::Serialize(
                   (CDeploymentReportingUpdateGroup *)v11,
                   (struct CSerializationHelper *)v197);
        if ( inited >= 0 )
        {
          v152 = CSerializationHelper::WriteToBSTRWithHeader((CSerializationHelper *)v197, &bstr);
          if ( v152 >= 0 )
          {
            v147 = bstr;
            SysStringByteLen(bstr);
            Trace::GuidToString::GuidToString((Trace::GuidToString *)v180, (const struct _GUID *)v24 + 1);
            WUTrace(
              0,
              0,
              0x1000000,
              4,
              0,
              L"Deployment job Id %ws : Successfully serialized deployment status cookie bstr, length = %lu bytes");
            v153 = SysStringByteLen(v147);
            if ( v153 )
            {
              v154 = (void *)v8[23];
              if ( v154 )
              {
                SusFree(v154);
                v8[23] = 0;
              }
              v155 = DPCopyBufferWithAlloc(
                       v153,
                       (const unsigned __int8 *)v147,
                       (unsigned int *)v8 + 44,
                       (unsigned __int8 **)v8 + 23);
              if ( v155 < 0 )
              {
                Trace::UpdateIdToString::UpdateIdToString(
                  (Trace::UpdateIdToString *)v184,
                  (const struct tagDSGlobalUpdateId *)(v8 + 25));
                Trace::GuidToString::GuidToString((Trace::GuidToString *)v180, (const struct _GUID *)v24 + 1);
                LODWORD(lpString2) = v155;
                WUTrace(
                  0,
                  0,
                  0x1000000,
                  3,
                  lpString2,
                  L"Deployment job Id %ws : Failed to copy and attach deployment status cookie bstr to update : %ws");
              }
            }
          }
          else
          {
            Trace::GuidToString::GuidToString((Trace::GuidToString *)v180, (const struct _GUID *)v24 + 1);
            LODWORD(lpString2) = v152;
            WUTrace(
              0,
              0,
              0x1000000,
              3,
              lpString2,
              L"Deployment job Id %ws : Failed to write deployment status cookie bstr");
            v147 = bstr;
          }
          goto LABEL_330;
        }
        v158 = Trace::GuidToString::GuidToString((Trace::GuidToString *)v180, (const struct _GUID *)v24 + 1);
        v151 = L"Deployment job Id %ws : Failed to serialize pending update group";
      }
      else
      {
        v158 = Trace::GuidToString::GuidToString((Trace::GuidToString *)v180, (const struct _GUID *)v24 + 1);
        v151 = L"Deployment job Id %ws : Failed to initialize serializer";
      }
      LODWORD(lpString2) = inited;
      WUTrace(0, 0, 0x1000000, 3, lpString2, v151, v158);
LABEL_330:
      if ( v147 )
        SysFreeString(v147);
      CSerializationHelper::~CSerializationHelper((CSerializationHelper *)v197);
LABEL_333:
      if ( !a5 )
      {
        v156 = CUpdateDeploymentJob::LogHistory(v24, v162, v144, v174);
        if ( v156 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x15F2,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentJob.cpp",
            (const char *)(unsigned int)v156,
            (int)lpString2);
      }
      goto LABEL_336;
    }
    v22 = 0;
    LOWORD(v160) = 0;
    if ( *((_DWORD *)v8 + 14) == 1 )
    {
      v23 = 181;
    }
    else if ( *((_DWORD *)v8 + 14) == 2 )
    {
      v23 = 226;
    }
    else
    {
      if ( *((_DWORD *)v8 + 14) != 4 )
      {
        if ( *((_DWORD *)v8 + 14) == 8 )
          v160 = 521;
        goto LABEL_28;
      }
      v23 = 546;
    }
    LOWORD(v160) = v23;
LABEL_28:
    DPAppendString((unsigned int *)v185 + 51, (wchar_t ***)v185 + 26, v10);
LABEL_29:
    v24 = v172;
    goto LABEL_30;
  }
  v14 = Trace::GuidToString::GuidToString((Trace::GuidToString *)v180, this + 1);
  WUTrace(0, 0, 0x1000000, 3, 0, L"Deployment job Id %ws : ReportDeploymentOperation out of memory", v14);
LABEL_336:
  FreeObject((struct tagUpdateDeploymentReportingData *)v185);
  FreeObject(v189);
  if ( lpMem )
  {
    SusFree(lpMem);
    lpMem = 0;
  }
  if ( v189 )
  {
    operator delete(v189, (const struct std::nothrow_t *)0x288);
    v189 = 0;
  }
  if ( v185 )
  {
    operator delete(v185, (const struct std::nothrow_t *)0x288);
    v185 = 0;
  }
  if ( v11 )
  {
    CSusArrayList<tagDeploymentReportingUpdateEvent,CSusArrayListItemOpDeploymentReportingUpdateEvent>::~CSusArrayList<tagDeploymentReportingUpdateEvent,CSusArrayListItemOpDeploymentReportingUpdateEvent>(v11 + 3);
    CSusArrayList<tagDeploymentReportingUpdateEvent,CSusArrayListItemOpDeploymentReportingUpdateEvent>::~CSusArrayList<tagDeploymentReportingUpdateEvent,CSusArrayListItemOpDeploymentReportingUpdateEvent>(v11);
    operator delete(v11, (const struct std::nothrow_t *)0x40);
  }
  CSusArrayList<tagDeploymentReportingUpdateEvent,CSusArrayListItemOpDeploymentReportingUpdateEvent>::~CSusArrayList<tagDeploymentReportingUpdateEvent,CSusArrayListItemOpDeploymentReportingUpdateEvent>(&v196[3]);
  CSusArrayList<tagDeploymentReportingUpdateEvent,CSusArrayListItemOpDeploymentReportingUpdateEvent>::~CSusArrayList<tagDeploymentReportingUpdateEvent,CSusArrayListItemOpDeploymentReportingUpdateEvent>(v196);
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
