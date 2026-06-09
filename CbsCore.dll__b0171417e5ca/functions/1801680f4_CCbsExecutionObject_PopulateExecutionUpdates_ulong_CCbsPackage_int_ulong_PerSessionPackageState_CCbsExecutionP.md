# CCbsExecutionObject::PopulateExecutionUpdates(ulong,CCbsPackage *,int,ulong,PerSessionPackageState *,CCbsExecutionPackage *,int,int,CbsState,CbsState,CCbsPointerArray<PackageToAdd *> *)

- ea: `0x1801680f4`
- end: `0x180169d0a`
- name: `?PopulateExecutionUpdates@CCbsExecutionObject@@AEAAJKPEAVCCbsPackage@@HKPEAUPerSessionPackageState@@PEAVCCbsExecutionPackage@@HHW4CbsState@@3PEAV?$CCbsPointerArray@PEAUPackageToAdd@@@@@Z`
- size: `7190`
- prototype: ``
- caller_count: `1`
- callee_count: `60`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18016be2c`

## callees

- `0x18000c70c`
- `0x18000d910`
- `0x180010b60`
- `0x180010cc0`
- `0x1800115a8`
- `0x180012ae4`
- `0x180012fe4`
- `0x1800138b8`
- `0x180015420`
- `0x18001e1a0`
- `0x18001f90c`
- `0x18002293c`
- `0x18002341c`
- `0x180023444`
- `0x180025008`
- `0x180042130`
- `0x1800466f8`
- `0x18004c2f4`
- `0x18004d564`
- `0x1800649d4`
- `0x180065f04`
- `0x180092590`
- `0x180093a70`
- `0x180093c4c`
- `0x180098538`
- `0x180099390`
- `0x180099548`
- `0x18009cf78`
- `0x1800a06ec`
- `0x1800a0898`
- `0x1800a5fe0`
- `0x1800ad504`
- `0x1800bd450`
- `0x1800bd544`
- `0x1800c0054`
- `0x1800eb4c0`
- `0x1800eb920`
- `0x180143f5c`
- `0x18015fa6c`
- `0x18015fc38`
- `0x18015ff68`
- `0x1801608c0`
- `0x180160afc`
- `0x1801633f4`
- `0x180166580`
- `0x1801666b8`
- `0x180166930`
- `0x180166ae0`
- `0x180167078`
- `0x1801677b4`

## string_xrefs

- `0x180168433`: `Appl: Force package: {}, update: {}, applicable state: {}, for MFL`
- `0x180169b02`: `Failed to get start state for update: {}`
- `0x18016849d`: `Plan: Sub-Execution, use current state as update start state`
- `0x180168628`: `Plan: Skip superseded on demand update, adjust its target state to Resolved: {}`
- `0x180169c81`: `Failed to get per session update state`
- `0x1801691f1`: `Failed to get applicable state for update.`
- `0x180169bc6`: `Failed to get applicable state for update.`
- `0x180168254`: `Plan: Force package:{}, update: {} into absent state since package state is absent`
- `0x180169250`: `Failed to set selection on update: {} for Package: {}`
- `0x18016833c`: `Appl: Force package: {}, update: {}, selected: {}, RemovePayload: {} by request of Client`
- `0x180168ded`: `Plan: Will attempt to restore Package: {}, Update: {}`
- `0x180168ca4`: `Plan: Skip update: {} that points to package {} since it is semi-isolated and target state is not absent.`
- `0x1801689b4`: `Exec: Planning an absent detached OC capability during a transmog operation, skipping capability planning for: {}`
- `0x18016895a`: `Exec: NetFx3 OC and package already added to the execution, skip`
- `0x1801686df`: `Plan: Merged into existing execution update for Package: {}, Update: {}, targeted: {}, merged: {}`
- `0x180169340`: `Failed to merge execution for package:{}, update:{}`
- `0x1801699ba`: `Failed to add execution component to execution package.`
- `0x180169098`: `Failed to add execution component to parent execution update.`
- `0x180169895`: `Failed to add execution component to parent execution update.`
- `0x1801688e0`: `Plan: Skip update: {} that points to package {} since it is isolated`
- `0x1801694be`: `Failed to resolve detached OC capability on installation of detached OC: {}`
- `0x180168aa0`: `Exec: Planning an absent detached update and it is not applicable, skipping capability planning for: {}`
- `0x18016944b`: `Failed to resolve detached OC capability on uninstallation or evaluation of installed detached OC: {}`

## pseudocode

```c
__int64 __fastcall CCbsExecutionObject::PopulateExecutionUpdates(
        __int64 a1,
        __int64 a2,
        CCbsPackage *a3,
        int a4,
        int a5,
        struct PerSessionPackageState *a6,
        CCbsExecutionPackage *a7,
        int a8,
        int a9,
        int a10,
        unsigned int a11,
        __int64 a12)
{
  __int64 v12; // r14
  struct PerSessionPackageState *v13; // rdx
  CCbsPackage *v14; // r13
  __int64 v15; // rax
  struct CCbsUpdate **v16; // rcx
  const wchar_t *v17; // rsi
  struct CCbsUpdate *v18; // r15
  CCbsSession *v19; // rcx
  int SessionUpdateState; // ebx
  int v21; // edi
  const wchar_t *v22; // rax
  bool v23; // zf
  PackageToAdd *v24; // rax
  struct PerSessionUpdateState *v25; // r12
  const wchar_t *v26; // rdx
  const struct SessionAction *DeferredOCAction; // rax
  __int64 v28; // rdx
  unsigned int Selection; // ebx
  __int64 v30; // r8
  int v31; // edx
  int v32; // r8d
  unsigned int v33; // r10d
  PackageToAdd *v34; // rcx
  CapabilityToChange *v35; // rcx
  __int64 v36; // rax
  int v37; // edx
  const wchar_t *v38; // rax
  const wchar_t *v39; // rax
  int v40; // r12d
  __int64 v41; // rcx
  unsigned int v42; // ebx
  __int64 v43; // rax
  int v44; // edx
  int v45; // r8d
  int v46; // r9d
  const wchar_t *v47; // rax
  const wchar_t *v48; // rax
  __int64 v49; // rcx
  const wchar_t *v50; // rax
  unsigned int v51; // edi
  CCbsExecutionUpdate *v52; // rbx
  __int64 v53; // rax
  int v54; // edx
  int v55; // r8d
  const wchar_t *v56; // rax
  const wchar_t *v57; // rax
  CCbsExecutionUpdate *v58; // rax
  int CurrentState; // edi
  int v60; // edi
  unsigned int *v61; // rcx
  __int64 v62; // rax
  __int64 v63; // r14
  int v64; // ecx
  const wchar_t *v65; // rax
  PackageToAdd *v66; // r13
  struct CCbsIdentity **v67; // rax
  unsigned int v68; // r14d
  wchar_t *v69; // rax
  const wchar_t *v70; // rax
  int v71; // ecx
  int v72; // ecx
  int v73; // ecx
  const wchar_t *v74; // rcx
  wchar_t *FastCbsIdentityString; // rax
  struct LogAdapter::Logger *v76; // rcx
  wchar_t **v77; // rax
  const char *v78; // r9
  CCbsUpdate *v79; // rcx
  wchar_t *v80; // rax
  char v81; // dl
  CCbsUpdate *v82; // rcx
  int v83; // r8d
  int v84; // r9d
  wchar_t *v85; // rax
  CCbsUpdate *v86; // rcx
  int v87; // r9d
  int v88; // r9d
  wchar_t *v89; // rax
  CCbsCapabilityManager *v90; // rdi
  struct CCbsCapability **InitPointer; // rax
  __int64 v92; // r8
  _QWORD *v93; // r14
  __int64 v94; // r9
  bool v95; // cc
  const wchar_t *v96; // r8
  const wchar_t *v97; // rdx
  __int64 v98; // r9
  struct PerSessionUpdateState *v99; // rcx
  CCbsCapability ***v100; // rdi
  CCbsCapability ***v101; // r12
  CCbsCapability **v102; // r14
  wchar_t *v103; // rax
  const wchar_t *v104; // rax
  CCbsPackage *v105; // r8
  __int64 v106; // r9
  struct LogAdapter::Logger *v107; // r10
  __int64 v108; // r13
  __int64 v109; // rdi
  __int64 v110; // r14
  CapabilityToChange *v111; // rax
  const wchar_t *v112; // rax
  CapabilityToChange *v113; // rdi
  const wchar_t *v114; // rdx
  int v115; // eax
  int RoomAt; // r14d
  __int64 v117; // r12
  int v118; // eax
  PackageToAdd *v119; // rdi
  int v120; // eax
  int v121; // eax
  __int64 v122; // rdx
  unsigned int v123; // edx
  const wchar_t *v124; // rdx
  __int64 v125; // r13
  __int64 v126; // r12
  CCbsExecutionComponent *v127; // rdi
  struct ICbsExecutionItem *v128; // rdx
  int v129; // eax
  __int64 v130; // rdx
  struct ICbsExecutionItem *v131; // rdx
  char *v132; // rcx
  char *v133; // rcx
  __int64 v134; // rdx
  const wchar_t *v135; // rax
  const wchar_t *v136; // rax
  __int64 v137; // rdx
  __int64 v138; // rdx
  unsigned int v139; // edx
  __int64 v140; // rdx
  void (*v141)(void); // rax
  void (*v142)(void); // rax
  char *v143; // rcx
  char *v144; // rcx
  char *v145; // rcx
  char *v147; // rcx
  int v148; // [rsp+20h] [rbp-E0h]
  bool v149; // [rsp+70h] [rbp-90h] BYREF
  int v150[2]; // [rsp+78h] [rbp-88h] BYREF
  int v151; // [rsp+80h] [rbp-80h] BYREF
  int v152; // [rsp+84h] [rbp-7Ch]
  int v153[2]; // [rsp+88h] [rbp-78h] BYREF
  struct CCbsIdentity *v154; // [rsp+90h] [rbp-70h] BYREF
  int v155; // [rsp+98h] [rbp-68h] BYREF
  struct CCbsCapability *v156; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v157; // [rsp+A8h] [rbp-58h] BYREF
  PackageToAdd *v158; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v159; // [rsp+B8h] [rbp-48h]
  CCbsPackage *v160; // [rsp+C0h] [rbp-40h]
  struct PerSessionUpdateState *v161; // [rsp+C8h] [rbp-38h] BYREF
  CapabilityToChange *v162; // [rsp+D0h] [rbp-30h] BYREF
  unsigned int *v163; // [rsp+D8h] [rbp-28h] BYREF
  int v164[2]; // [rsp+E0h] [rbp-20h] BYREF
  int v165[2]; // [rsp+E8h] [rbp-18h] BYREF
  int v166[2]; // [rsp+F0h] [rbp-10h] BYREF
  struct CCbsUpdate **v167; // [rsp+F8h] [rbp-8h]
  CCbsExecutionPackage *v168; // [rsp+100h] [rbp+0h]
  const wchar_t *v169; // [rsp+108h] [rbp+8h] BYREF
  __int64 v170; // [rsp+110h] [rbp+10h] BYREF
  const wchar_t *v171; // [rsp+118h] [rbp+18h] BYREF
  const wchar_t *v172; // [rsp+120h] [rbp+20h] BYREF
  __int64 v173; // [rsp+128h] [rbp+28h] BYREF
  __int64 v174; // [rsp+130h] [rbp+30h] BYREF
  __int64 v175; // [rsp+138h] [rbp+38h] BYREF
  __int64 v176; // [rsp+140h] [rbp+40h] BYREF
  __int64 v177; // [rsp+148h] [rbp+48h] BYREF
  __int64 v178; // [rsp+150h] [rbp+50h] BYREF
  const wchar_t *v179; // [rsp+158h] [rbp+58h] BYREF
  int v180[2]; // [rsp+160h] [rbp+60h] BYREF
  __int64 v181; // [rsp+168h] [rbp+68h] BYREF
  __int64 v182; // [rsp+170h] [rbp+70h] BYREF
  const wchar_t *v183; // [rsp+178h] [rbp+78h] BYREF
  const wchar_t *v184; // [rsp+180h] [rbp+80h] BYREF
  const wchar_t *v185; // [rsp+188h] [rbp+88h] BYREF
  wchar_t *v186; // [rsp+190h] [rbp+90h] BYREF
  wchar_t *v187; // [rsp+198h] [rbp+98h] BYREF
  wchar_t *v188; // [rsp+1A0h] [rbp+A0h] BYREF
  wchar_t *v189; // [rsp+1A8h] [rbp+A8h] BYREF
  wchar_t *v190; // [rsp+1B0h] [rbp+B0h] BYREF
  const wchar_t *v191; // [rsp+1B8h] [rbp+B8h] BYREF
  wchar_t *v192; // [rsp+1C0h] [rbp+C0h] BYREF
  wchar_t *v193; // [rsp+1C8h] [rbp+C8h] BYREF
  unsigned int v194; // [rsp+1D0h] [rbp+D0h] BYREF
  unsigned int UpdateOptions; // [rsp+1D4h] [rbp+D4h] BYREF
  CCbsExecutionComponent *v196; // [rsp+1D8h] [rbp+D8h] BYREF
  unsigned int v197; // [rsp+1E0h] [rbp+E0h] BYREF
  int v198; // [rsp+1E4h] [rbp+E4h] BYREF
  int v199; // [rsp+1E8h] [rbp+E8h] BYREF
  int v200; // [rsp+1ECh] [rbp+ECh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+238h] [rbp+138h]

  v12 = a1;
  v13 = a6;
  v14 = a3;
  v168 = a7;
  v194 = a11;
  *(_QWORD *)v164 = a12;
  v15 = *((_QWORD *)a3 + 92);
  v159 = a1;
  v16 = (struct CCbsUpdate **)*((_QWORD *)a3 + 94);
  v199 = a4;
  v160 = a3;
  *(_QWORD *)v150 = a6;
  v167 = v16;
  *(_QWORD *)v153 = &v16[v15];
  if ( v16 == *(struct CCbsUpdate ***)v153 )
    return 0;
  v17 = &qword_1802EB518;
  while ( 1 )
  {
    v18 = *v16;
    v19 = *(CCbsSession **)(v12 + 64);
    v155 = 4096;
    v151 = 4096;
    v197 = -1;
    LODWORD(v196) = 0;
    v149 = 0;
    v161 = 0;
    SessionUpdateState = CCbsSession::GetSessionUpdateState(v19, v18, v13, 1, &v161);
    if ( SessionUpdateState < 0 )
    {
      v200 = SessionUpdateState;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get per session update state");
        *(_QWORD *)v166 = &v200;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v166);
      }
      v134 = 171;
      goto LABEL_335;
    }
    SessionUpdateState = CCbsUpdate::GetCurrentState(v18, *(struct CCbsSession **)(v12 + 64), (enum CbsState *)&v155);
    if ( SessionUpdateState < 0 )
    {
      v200 = SessionUpdateState;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get current state.");
        *(_QWORD *)v166 = &v200;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v166);
      }
      v134 = 174;
      goto LABEL_335;
    }
    if ( !a10 )
    {
      v21 = 0;
      v22 = &qword_1802EB518;
      if ( *((_QWORD *)v18 + 4) )
        v22 = (const wchar_t *)*((_QWORD *)v18 + 4);
      v23 = *((_QWORD *)v14 + 15) == 0;
      v157 = (__int64)v22;
      v24 = (PackageToAdd *)&qword_1802EB518;
      if ( !v23 )
        v24 = (PackageToAdd *)*((_QWORD *)v14 + 15);
      v158 = v24;
      if ( LogAdapter::g_Logger )
        LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
          (__int64)LogAdapter::g_Logger,
          1,
          1,
          (__int64)"Plan: Force package:{}, update: {} into absent state since package state is absent",
          (__int64)&v158,
          (__int64)&v157);
      goto LABEL_37;
    }
    v25 = v161;
    SessionUpdateState = CCbsUpdate::GetApplicableSelectableState(
                           v18,
                           *(struct CCbsSession **)(v12 + 64),
                           v161,
                           (enum CbsState *)&v151,
                           &v149);
    if ( SessionUpdateState < 0 )
    {
      v194 = SessionUpdateState;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get applicable state for update.");
        *(_QWORD *)v150 = &v194;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v150);
      }
      v134 = 192;
      goto LABEL_335;
    }
    if ( (unsigned int)CCbsUpdate::IsSelectable(v18) )
    {
      v21 = v151;
      if ( v151 <= 32 )
        goto LABEL_28;
      v26 = &qword_1802EB518;
      if ( *((_QWORD *)v18 + 4) )
        v26 = (const wchar_t *)*((_QWORD *)v18 + 4);
      DeferredOCAction = CCbsSession::GetDeferredOCAction(*(CCbsSession **)(v12 + 64), v26);
      if ( !DeferredOCAction || *(_DWORD *)DeferredOCAction != 3 )
        goto LABEL_28;
      Selection = SessionAction::GetSelection(DeferredOCAction, v28, DeferredOCAction);
      UpdateOptions = SessionAction::GetUpdateOptions(v30);
      v157 = CbsSelectionToString(Selection);
      v34 = (PackageToAdd *)&qword_1802EB518;
      if ( *((_QWORD *)v18 + 4) )
        v34 = (PackageToAdd *)*((_QWORD *)v18 + 4);
      v23 = *((_QWORD *)v14 + 15) == 0;
      v158 = v34;
      v35 = (CapabilityToChange *)&qword_1802EB518;
      if ( !v23 )
        v35 = (CapabilityToChange *)*((_QWORD *)v14 + 15);
      v162 = v35;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t const *,wchar_t const *,unsigned long>(
          (_DWORD)LogAdapter::g_Logger,
          v31,
          v32,
          (unsigned int)"Appl: Force package: {}, update: {}, selected: {}, RemovePayload: {} by request of Client",
          (__int64)&v162,
          (__int64)&v158,
          (__int64)&v157,
          (__int64)&UpdateOptions);
        v33 = UpdateOptions;
      }
      v148 = 0;
      SessionUpdateState = CCbsUpdate::SetInstallState(v18, v33, *(_QWORD *)(v12 + 64), Selection);
      if ( SessionUpdateState < 0 )
      {
        v194 = SessionUpdateState;
        if ( LogAdapter::g_Logger )
        {
          v135 = &qword_1802EB518;
          if ( *((_QWORD *)v14 + 15) )
            v135 = (const wchar_t *)*((_QWORD *)v14 + 15);
          v23 = *((_QWORD *)v18 + 4) == 0;
          *(_QWORD *)v150 = v135;
          if ( !v23 )
            v17 = (const wchar_t *)*((_QWORD *)v18 + 4);
          *(_QWORD *)v153 = v17;
          LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (__int64)"Failed to set selection on update: {} for Package: {}",
            (__int64)v153,
            (__int64)v150);
          v163 = &v194;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)&v163);
        }
        v134 = 213;
        goto LABEL_335;
      }
      SessionUpdateState = CCbsUpdate::GetApplicableSelectableState(
                             v18,
                             *(struct CCbsSession **)(v12 + 64),
                             v25,
                             (enum CbsState *)&v151,
                             &v149);
      if ( SessionUpdateState < 0 )
      {
        v194 = SessionUpdateState;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get applicable state for update.");
          *(_QWORD *)v150 = &v194;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)v150);
        }
        v134 = 222;
        goto LABEL_335;
      }
    }
    v21 = v151;
LABEL_28:
    if ( v21 != 112 && (a5 & 0x20000) != 0 && *(_BYTE *)(*(_QWORD *)(v12 + 64) + 1744LL) )
    {
      v21 = 112;
      v36 = CbsStateToString(112);
      v23 = *((_QWORD *)v18 + 4) == 0;
      v170 = v36;
      v38 = &qword_1802EB518;
      if ( !v23 )
        v38 = (const wchar_t *)*((_QWORD *)v18 + 4);
      v23 = *((_QWORD *)v14 + 15) == 0;
      v171 = v38;
      v39 = &qword_1802EB518;
      if ( !v23 )
        v39 = (const wchar_t *)*((_QWORD *)v14 + 15);
      v172 = v39;
      if ( LogAdapter::g_Logger )
      {
        LOBYTE(v37) = 1;
        LogAdapter::Logger::LogNumObjects<wchar_t const *,AutoScz,wchar_t *>(
          (_DWORD)LogAdapter::g_Logger,
          v37,
          1,
          (unsigned int)"Appl: Force package: {}, update: {}, applicable state: {}, for MFL",
          (__int64)&v172,
          (__int64)&v171,
          (__int64)&v170);
      }
    }
LABEL_37:
    SessionUpdateState = CCbsUpdate::GetUserSelectionWithAdjustment(
                           v18,
                           *(struct CCbsSession **)(v12 + 64),
                           1,
                           (enum UpdateSelection *)&v197,
                           (int *)&v196);
    if ( SessionUpdateState < 0 )
    {
      v194 = SessionUpdateState;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get user selection state");
        *(_QWORD *)v150 = &v194;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v150);
      }
      v134 = 245;
      goto LABEL_335;
    }
    v40 = v21;
    UpdateOptions = 4096;
    if ( a10 < v21 )
      v40 = a10;
    v23 = *(_BYTE *)(v12 + 888) == 0;
    v152 = v40;
    if ( v23 )
    {
      SessionUpdateState = CCbsUpdate::GetStartState(v18, *(_QWORD *)(v12 + 64), (unsigned int)v40, &UpdateOptions);
      if ( SessionUpdateState < 0 )
      {
        v194 = SessionUpdateState;
        if ( LogAdapter::g_Logger )
        {
          if ( *((_QWORD *)v18 + 4) )
            v17 = (const wchar_t *)*((_QWORD *)v18 + 4);
          *(_QWORD *)v150 = v17;
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (__int64)"Failed to get start state for update: {}",
            (__int64)v150);
          *(_QWORD *)v153 = &v194;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)v153);
        }
        v134 = 307;
        goto LABEL_335;
      }
      v41 = UpdateOptions;
    }
    else
    {
      LogAdapter::TraceAtLevel<>(1, "Plan: Sub-Execution, use current state as update start state");
      v41 = (unsigned int)v155;
    }
    v151 = EquivalentStateIfInvalid(v41, (unsigned int)v40);
    v42 = v151;
    if ( v40 == 4096 )
    {
      CurrentState = -2146498560;
      v194 = -2146498560;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"target state cannot be default");
        *(_QWORD *)v150 = &v194;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v150);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x139,
        (unsigned int)"onecore\\base\\cbs\\core\\cbsexecutionobjectstateplanning.cpp",
        (const char *)0x800F0800LL,
        v148);
      return (unsigned int)CurrentState;
    }
    v157 = CbsSelectionToString(v197);
    v173 = CbsStateToString(v194);
    v174 = CbsStateToString((unsigned int)v40);
    v175 = CbsStateToString((unsigned int)v21);
    v176 = CbsStateToString(v42);
    v177 = CbsStateToString(4096);
    v43 = CbsStateToString((unsigned int)v155);
    v23 = *((_QWORD *)v18 + 4) == 0;
    v178 = v43;
    v47 = &qword_1802EB518;
    if ( !v23 )
      v47 = (const wchar_t *)*((_QWORD *)v18 + 4);
    v23 = *((_QWORD *)v14 + 15) == 0;
    v179 = v47;
    v48 = &qword_1802EB518;
    if ( !v23 )
      v48 = (const wchar_t *)*((_QWORD *)v14 + 15);
    *(_QWORD *)v180 = v48;
    if ( LogAdapter::g_Logger )
      LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *>(
        (_DWORD)LogAdapter::g_Logger,
        v44,
        v45,
        v46,
        (__int64)v180,
        (__int64)&v179,
        (__int64)&v178,
        (__int64)&v177,
        (__int64)&v176,
        (__int64)&v175,
        (__int64)&v174,
        (__int64)&v173,
        (__int64)&v157);
    v49 = *(_QWORD *)(v12 + 24);
    if ( v49 )
    {
      SessionUpdateState = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, bool))(*(_QWORD *)v49 + 40LL))(
                             v49,
                             32,
                             (unsigned int)(a9 != 0) - 2,
                             a9 == 0);
      if ( SessionUpdateState < 0 )
      {
        v194 = SessionUpdateState;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Plan: User cancelled the operation.");
          *(_QWORD *)v150 = &v194;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)v150);
        }
        v134 = 336;
        goto LABEL_335;
      }
    }
    if ( v155 == 32 && v40 == 80 )
    {
      v50 = &qword_1802EB518;
      if ( *((_QWORD *)v18 + 4) )
        v50 = (const wchar_t *)*((_QWORD *)v18 + 4);
      v157 = (__int64)v50;
      LogAdapter::TraceAtLevel<wchar_t const *>(
        1,
        "Plan: Skip superseded on demand update, adjust its target state to Resolved: {}",
        &v157);
      v40 = 32;
      v152 = 32;
    }
    if ( a8 )
    {
      UpdateOptions = 4096;
      SessionUpdateState = CCbsExecutionPackage::MergeExecutionUpdate(v168, v18, (unsigned int)v40, &UpdateOptions);
      if ( SessionUpdateState < 0 )
      {
        v194 = SessionUpdateState;
        if ( LogAdapter::g_Logger )
        {
          v136 = &qword_1802EB518;
          if ( *((_QWORD *)v18 + 4) )
            v136 = (const wchar_t *)*((_QWORD *)v18 + 4);
          v23 = *((_QWORD *)v14 + 15) == 0;
          *(_QWORD *)v150 = v136;
          if ( !v23 )
            v17 = (const wchar_t *)*((_QWORD *)v14 + 15);
          *(_QWORD *)v153 = v17;
          LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (__int64)"Failed to merge execution for package:{}, update:{}",
            (__int64)v153,
            (__int64)v150);
          v163 = &v194;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)&v163);
        }
        v134 = 360;
LABEL_335:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v134,
          (unsigned int)"onecore\\base\\cbs\\core\\cbsexecutionobjectstateplanning.cpp",
          (const char *)(unsigned int)SessionUpdateState,
          v148);
        return (unsigned int)SessionUpdateState;
      }
      v51 = UpdateOptions;
      v52 = 0;
      if ( v40 != UpdateOptions )
      {
        v181 = CbsStateToString(UpdateOptions);
        v53 = CbsStateToString((unsigned int)v40);
        v23 = *((_QWORD *)v18 + 4) == 0;
        v182 = v53;
        v56 = &qword_1802EB518;
        if ( !v23 )
          v56 = (const wchar_t *)*((_QWORD *)v18 + 4);
        v23 = *((_QWORD *)v14 + 15) == 0;
        v183 = v56;
        v57 = &qword_1802EB518;
        if ( !v23 )
          v57 = (const wchar_t *)*((_QWORD *)v14 + 15);
        v184 = v57;
        if ( LogAdapter::g_Logger )
          LogAdapter::Logger::LogNumObjects<wchar_t *,wchar_t *,wchar_t const *,wchar_t const *>(
            (_DWORD)LogAdapter::g_Logger,
            v54,
            v55,
            (unsigned int)"Plan: Merged into existing execution update for Package: {}, Update: {}, targeted: {}, merged: {}",
            (__int64)&v184,
            (__int64)&v183,
            (__int64)&v182,
            (__int64)&v181);
      }
      v40 = v51;
      v152 = v51;
    }
    else
    {
      v58 = (CCbsExecutionUpdate *)operator new(0xA0u);
      if ( !v58 || (v52 = CCbsExecutionUpdate::CCbsExecutionUpdate(v58)) == 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x178,
          (unsigned int)"onecore\\base\\cbs\\core\\cbsexecutionobjectstateplanning.cpp",
          (const char *)0x8007000ELL,
          v148);
        return 2147942414LL;
      }
      v148 = (int)v18;
      CCbsExecutionUpdate::Initialize(v52, *(_QWORD *)(v12 + 64), v168, v14);
      CurrentState = CCbsExecutionPackage::AddExecutionUpdate(v168, v52);
      if ( CurrentState < 0 )
      {
        UpdateOptions = CurrentState;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to add execution component to execution package.");
          *(_QWORD *)v165 = &UpdateOptions;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)v165);
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x184,
          (unsigned int)"onecore\\base\\cbs\\core\\cbsexecutionobjectstateplanning.cpp",
          (const char *)(unsigned int)CurrentState,
          v148);
        goto LABEL_310;
      }
    }
    v60 = v151;
    if ( v199 && v40 > 64 )
    {
      if ( v151 <= 64 )
        v40 = 64;
      v152 = v40;
    }
    *((_DWORD *)v161 + 3) = v40;
    v61 = (unsigned int *)*((_QWORD *)v18 + 28);
    v62 = *((_QWORD *)v18 + 26);
    v157 = (__int64)v61;
    v163 = &v61[2 * v62];
    if ( v61 != v163 )
      break;
LABEL_221:
    if ( v52 )
    {
      v133 = (char *)v52 + *(int *)(*((_QWORD *)v52 + 1) + 4LL) + 8;
      (*(void (__fastcall **)(char *))(*(_QWORD *)v133 + 16LL))(v133);
    }
    v16 = v167 + 1;
    v167 = v16;
    if ( v16 == *(struct CCbsUpdate ***)v153 )
      return 0;
    v13 = *(struct PerSessionPackageState **)v150;
  }
  while ( 1 )
  {
    v63 = *(_QWORD *)v61;
    v64 = *(_DWORD *)(*(_QWORD *)v61 + 24LL);
    if ( v64 == 5 && (a5 & 0x4000) != 0 )
      break;
    v71 = v64 - 1;
    if ( !v71 )
    {
      if ( a8 )
        goto LABEL_219;
      v196 = 0;
      if ( Windows::AutoComPtr<CCbsExecutionComponent>::AllocateWithNew<CCbsExecutionComponent,>(&v196) )
      {
        v127 = v196;
        CCbsExecutionComponent::Initialize(
          v196,
          *(struct CCbsSession **)(v159 + 64),
          v14,
          v18,
          *(struct CCbsComponentDeployment **)(v63 + 40));
        if ( v127 )
          v131 = (CCbsExecutionComponent *)((char *)v127 + *(int *)(*((_QWORD *)v127 + 1) + 4LL) + 8);
        else
          v131 = 0;
        RoomAt = CCbsExecutionUpdate::AddExecutionItem(v52, v131);
        if ( RoomAt < 0 )
        {
          v197 = RoomAt;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to add execution component to parent execution update.");
            *(_QWORD *)v164 = &v197;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {}",
              (__int64)v164);
          }
          v130 = 449;
          goto LABEL_297;
        }
LABEL_217:
        if ( v127 )
        {
          v132 = (char *)v127 + *(int *)(*((_QWORD *)v127 + 1) + 4LL) + 8;
          (*(void (__fastcall **)(char *))(*(_QWORD *)v132 + 16LL))(v132);
        }
        goto LABEL_219;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1BB,
        (unsigned int)"onecore\\base\\cbs\\core\\cbsexecutionobjectstateplanning.cpp",
        (const char *)0x8007000ELL,
        v148);
      if ( v196 )
      {
        v147 = (char *)v196 + *(int *)(*((_QWORD *)v196 + 1) + 4LL) + 8;
        (*(void (__fastcall **)(char *))(*(_QWORD *)v147 + 16LL))(v147);
      }
      if ( v52 )
      {
        v141 = *(void (**)(void))(*(_QWORD *)((char *)v52 + *(int *)(*((_QWORD *)v52 + 1) + 4LL) + 8) + 16LL);
        goto LABEL_306;
      }
      return 2147942414LL;
    }
    v72 = v71 - 1;
    if ( !v72 )
    {
      if ( a8 )
        goto LABEL_219;
      v196 = 0;
      if ( Windows::AutoComPtr<CCbsExecutionComponent>::AllocateWithNew<CCbsExecutionComponent,>(&v196) )
      {
        v127 = v196;
        CCbsExecutionComponent::Initialize(
          v196,
          *(struct CCbsSession **)(v159 + 64),
          v14,
          v18,
          *(struct CCbsDriverDeployment **)(v63 + 40));
        if ( v127 )
          v128 = (CCbsExecutionComponent *)((char *)v127 + *(int *)(*((_QWORD *)v127 + 1) + 4LL) + 8);
        else
          v128 = 0;
        v129 = CCbsExecutionUpdate::AddExecutionItem(v52, v128);
        RoomAt = v129;
        if ( v129 < 0 )
        {
          v199 = v129;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to add execution component to parent execution update.");
            *(_QWORD *)v153 = &v199;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {}",
              (__int64)v153);
          }
          v130 = 464;
LABEL_297:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v130,
            (unsigned int)"onecore\\base\\cbs\\core\\cbsexecutionobjectstateplanning.cpp",
            (const char *)(unsigned int)RoomAt,
            v148);
          if ( v127 )
          {
            v144 = (char *)v127 + *(int *)(*((_QWORD *)v127 + 1) + 4LL) + 8;
            (*(void (__fastcall **)(char *))(*(_QWORD *)v144 + 16LL))(v144);
          }
          goto LABEL_299;
        }
        goto LABEL_217;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1CA,
        (unsigned int)"onecore\\base\\cbs\\core\\cbsexecutionobjectstateplanning.cpp",
        (const char *)0x8007000ELL,
        v148);
      if ( v196 )
      {
        v143 = (char *)v196 + *(int *)(*((_QWORD *)v196 + 1) + 4LL) + 8;
        (*(void (__fastcall **)(char *))(*(_QWORD *)v143 + 16LL))(v143);
      }
LABEL_277:
      if ( !v52 )
        return 2147942414LL;
      v141 = *(void (**)(void))(*(_QWORD *)((char *)v52 + *(int *)(*((_QWORD *)v52 + 1) + 4LL) + 8) + 16LL);
LABEL_306:
      v141();
      return 2147942414LL;
    }
    v73 = v72 - 1;
    if ( !v73 )
      goto LABEL_82;
    if ( v73 != 2 )
    {
      CurrentState = -2146498560;
      LODWORD(v196) = -2146498560;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Unknown Deployment Type.");
        *(_QWORD *)v150 = &v196;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v150);
      }
      v138 = 825;
LABEL_289:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v138,
        (unsigned int)"onecore\\base\\cbs\\core\\cbsexecutionobjectstateplanning.cpp",
        (const char *)(unsigned int)CurrentState,
        v148);
LABEL_290:
      if ( !v52 )
        return (unsigned int)CurrentState;
LABEL_310:
      v142 = *(void (**)(void))(*(_QWORD *)((char *)v52 + *(int *)(*((_QWORD *)v52 + 1) + 4LL) + 8) + 16LL);
LABEL_311:
      v142();
      return (unsigned int)CurrentState;
    }
    if ( v60 != v40 )
    {
      v74 = &qword_1802EB518;
      if ( *((_QWORD *)v18 + 4) )
        v74 = (const wchar_t *)*((_QWORD *)v18 + 4);
      if ( !(unsigned __int8)StringsAreEqual(v74, L"NetFx3", 1)
        || (*(_DWORD *)(*(_QWORD *)(v159 + 64) + 2208LL) & 0x2000) == 0 )
      {
        v156 = 0;
        if ( (v60 <= 0 || v155 <= 0) && (*(_DWORD *)(*(_QWORD *)(v159 + 64) + 2208LL) & 0x100000) != 0 )
        {
          FastCbsIdentityString = GetFastCbsIdentityString(*((const struct CCbsIdentity **)v14 + 14));
          v76 = LogAdapter::g_Logger;
          v186 = FastCbsIdentityString;
          if ( LogAdapter::g_Logger )
          {
            v77 = &v186;
            v78 = "Exec: Planning an absent detached OC capability during a transmog operation, skipping capability planning for: {}";
            goto LABEL_122;
          }
LABEL_147:
          Windows::AutoComPtr<CCbsDriverDeployment>::Close(&v156);
          goto LABEL_219;
        }
        if ( CCbsUpdate::AllowAbsentIfCapabilityAbsent(v18) && v149 && v60 < 64 )
        {
          v80 = GetFastCbsIdentityString(*((const struct CCbsIdentity **)v14 + 14));
          v76 = LogAdapter::g_Logger;
          v187 = v80;
          if ( !LogAdapter::g_Logger )
            goto LABEL_147;
          v77 = &v187;
          v78 = "Exec: Planning an absent detached OC using default feature state, skipping capability planning for: {}";
LABEL_122:
          LogAdapter::Logger::LogNumObjects<wchar_t const *>((__int64)v76, 1, 1, (__int64)v78, (__int64)v77);
          goto LABEL_147;
        }
        if ( CCbsUpdate::AllowAbsentIfCapabilityAbsent(v79) && !v81 && v197 == v83 && v60 < v84 )
        {
          v85 = GetFastCbsIdentityString(*((const struct CCbsIdentity **)v14 + 14));
          v76 = LogAdapter::g_Logger;
          v193 = v85;
          if ( !LogAdapter::g_Logger )
            goto LABEL_147;
          v77 = &v193;
          v78 = "Exec: Planning an absent detached OC and user selection is off, skipping capability planning for: {}";
          goto LABEL_122;
        }
        if ( CCbsUpdate::AllowAbsentIfCapabilityAbsent(v82)
          && v60 < v87
          && !(unsigned int)CCbsUpdate::IsSelectable(v86)
          && v40 == v88 )
        {
          v89 = GetFastCbsIdentityString(*((const struct CCbsIdentity **)v14 + 14));
          v76 = LogAdapter::g_Logger;
          v188 = v89;
          if ( !LogAdapter::g_Logger )
            goto LABEL_147;
          v77 = &v188;
          v78 = "Exec: Planning an absent detached update and it is not applicable, skipping capability planning for: {}";
          goto LABEL_122;
        }
        v90 = vpCapabilityManager;
        InitPointer = (struct CCbsCapability **)Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v156);
        v92 = *(_QWORD *)(v63 + 40);
        v93 = (_QWORD *)v159;
        CurrentState = CCbsCapabilityManager::ResolveCapability(
                         v90,
                         *(struct CCbsSession **)(v159 + 64),
                         *(const struct CCbsIdentity **)(v92 + 24),
                         InitPointer);
        if ( CurrentState < 0 )
        {
          if ( v40 > 64 )
          {
            v194 = CurrentState;
            if ( LogAdapter::g_Logger )
            {
              if ( *((_QWORD *)v18 + 4) )
                v17 = (const wchar_t *)*((_QWORD *)v18 + 4);
              *(_QWORD *)v150 = v17;
              LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                (__int64)LogAdapter::g_Logger,
                0,
                3,
                (__int64)"Failed to resolve detached OC capability on installation of detached OC: {}",
                (__int64)v150);
              *(_QWORD *)v153 = &v194;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (__int64)LogAdapter::g_Logger,
                1,
                3,
                (__int64)": {}",
                (__int64)v153);
            }
            v137 = 729;
            goto LABEL_260;
          }
          if ( v151 > 64 )
          {
            v194 = CurrentState;
            if ( LogAdapter::g_Logger )
            {
              if ( *((_QWORD *)v18 + 4) )
                v17 = (const wchar_t *)*((_QWORD *)v18 + 4);
              *(_QWORD *)v150 = v17;
              LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                (__int64)LogAdapter::g_Logger,
                0,
                3,
                (__int64)"Failed to resolve detached OC capability on uninstallation or evaluation of installed detached OC: {}",
                (__int64)v150);
              *(_QWORD *)v153 = &v194;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (__int64)LogAdapter::g_Logger,
                1,
                3,
                (__int64)": {}",
                (__int64)v153);
            }
            v137 = 737;
            goto LABEL_260;
          }
          if ( !CCbsUpdate::AllowAbsentIfCapabilityAbsent(v18) )
          {
            v194 = CurrentState;
            if ( LogAdapter::g_Logger )
            {
              if ( *((_QWORD *)v18 + 4) != v94 )
                v17 = (const wchar_t *)*((_QWORD *)v18 + 4);
              *(_QWORD *)v150 = v17;
              LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                (__int64)LogAdapter::g_Logger,
                0,
                3,
                (__int64)"Failed to resolve detached OC capability and absent default state is not allowed: {}",
                (__int64)v150);
              *(_QWORD *)v153 = &v194;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (__int64)LogAdapter::g_Logger,
                1,
                3,
                (__int64)": {}",
                (__int64)v153);
            }
            v137 = 751;
LABEL_260:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v137,
              (unsigned int)"onecore\\base\\cbs\\core\\cbsexecutionobjectstateplanning.cpp",
              (const char *)(unsigned int)CurrentState,
              v148);
            Windows::AutoComPtr<CCbsDriverDeployment>::Close(&v156);
            goto LABEL_290;
          }
          LogAdapter::TraceAtLevel<>(
            (unsigned int)(v94 + 1),
            "Staging an OC with a missing FoD, allowing absent as the capability is absent");
          goto LABEL_147;
        }
        v95 = v40 < 64;
        if ( v40 <= 64 )
        {
LABEL_136:
          if ( v95 )
          {
            v40 = 0;
            v152 = 0;
            v189 = GetFastCbsIdentityString(*((const struct CCbsIdentity **)v156 + 17));
            LogAdapter::TraceAtLevel<wchar_t const *>(
              1,
              "Forcing Capability: {} targetState from Resolved to Absent because it is a detached OC",
              &v189);
          }
        }
        else if ( v151 < v40 )
        {
          v96 = &qword_1802EB518;
          v97 = &qword_1802EB518;
          if ( *((_QWORD *)v18 + 4) )
            v96 = (const wchar_t *)*((_QWORD *)v18 + 4);
          v148 = 0;
          if ( *((_QWORD *)v14 + 15) )
            v97 = (const wchar_t *)*((_QWORD *)v14 + 15);
          CurrentState = CCbsSession::AddAction(v93[8], v97, v96, 11);
          if ( CurrentState < 0 )
          {
            v194 = CurrentState;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                (__int64)LogAdapter::g_Logger,
                0,
                3,
                (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to add action.");
              *(_QWORD *)v150 = &v194;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (__int64)LogAdapter::g_Logger,
                1,
                3,
                (__int64)": {}",
                (__int64)v150);
            }
            v137 = 763;
            goto LABEL_260;
          }
          v95 = v40 < 64;
          goto LABEL_136;
        }
        LOBYTE(v98) = CCbsUpdate::AllowAbsentIfCapabilityAbsent(v18);
        CurrentState = CCbsExecutionObject::PlanCapability(v93, v156, (unsigned int)v40, v98);
        if ( CurrentState < 0 )
        {
          v194 = CurrentState;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to plan capability");
            *(_QWORD *)v150 = &v194;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {}",
              (__int64)v150);
          }
          v137 = 782;
          goto LABEL_260;
        }
        v99 = v161;
        if ( (*((_BYTE *)v161 + 24) & 1) != 0 )
        {
          v100 = (CCbsCapability ***)v93[71];
          v101 = &v100[v93[69]];
          if ( v100 == v101 )
          {
LABEL_145:
            v40 = v152;
            if ( v151 >= 64 )
            {
              *((_DWORD *)v99 + 3) = v151;
              *((_DWORD *)v99 + 6) &= ~1u;
            }
          }
          else
          {
            while ( 1 )
            {
              v102 = *v100;
              if ( (*(_BYTE *)*v100 & 2) != 0 && CCbsCapability::IsSameCapability(v102[1], v156) )
                break;
              if ( ++v100 == v101 )
              {
                v99 = v161;
                goto LABEL_145;
              }
            }
            v40 = v152;
            if ( *((int *)v102 + 8) >= 64 )
              *((_DWORD *)v161 + 6) &= ~1u;
          }
        }
        goto LABEL_147;
      }
      LogAdapter::TraceAtLevel<>(1, "Exec: NetFx3 OC and package already added to the execution, skip");
    }
LABEL_219:
    v60 = v151;
    v61 = (unsigned int *)(v157 + 8);
    v157 = (__int64)v61;
    if ( v61 == v163 )
    {
      v12 = v159;
      goto LABEL_221;
    }
  }
  v65 = &qword_1802EB518;
  if ( *((_QWORD *)v14 + 15) )
    v65 = (const wchar_t *)*((_QWORD *)v14 + 15);
  v185 = v65;
  LogAdapter::TraceAtLevel<wchar_t const *>(1, "Planning child capability of LCU as a package: {}", &v185);
LABEL_82:
  v66 = *(PackageToAdd **)(v63 + 40);
  v158 = v66;
  v198 = 4096;
  CurrentState = CCbsPackageDeployment::GetCurrentState(
                   v66,
                   *(struct CCbsSession **)(v159 + 64),
                   v18,
                   (enum CbsState *)&v198);
  if ( CurrentState < 0 )
  {
    LODWORD(v196) = CurrentState;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get current package state.");
      *(_QWORD *)v150 = &v196;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)v150);
    }
    v138 = 481;
    goto LABEL_289;
  }
  if ( v198 == 4096 )
  {
    CurrentState = -2146498560;
    v194 = -2146498560;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Package state cannot be CbsStateDefault");
      *(_QWORD *)v150 = &v194;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)v150);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E3,
      (unsigned int)"onecore\\base\\cbs\\core\\cbsexecutionobjectstateplanning.cpp",
      (const char *)0x800F0800LL,
      v148);
    if ( v52 )
    {
      v142 = *(void (**)(void))(*(_QWORD *)((char *)v52 + *(int *)(*((_QWORD *)v52 + 1) + 4LL) + 8) + 16LL);
      goto LABEL_311;
    }
    return (unsigned int)CurrentState;
  }
  LODWORD(v196) = 0;
  v154 = 0;
  UpdateOptions = 0;
  v67 = (struct CCbsIdentity **)Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v154);
  CCbsPackageDeployment::GetData(v66, v67, (enum PACKAGE_INTEGRATION_TYPE::PACKAGE_INTEGRATION *)&UpdateOptions);
  v68 = UpdateOptions;
  if ( UpdateOptions != 1 )
  {
    if ( UpdateOptions != 4 || !*((_DWORD *)v160 + 224) || !v40 )
      goto LABEL_159;
    v103 = GetFastCbsIdentityString(v154);
    v23 = *((_QWORD *)v18 + 4) == 0;
    v192 = v103;
    v104 = &qword_1802EB518;
    if ( !v23 )
      v104 = (const wchar_t *)*((_QWORD *)v18 + 4);
    v169 = v104;
    if ( LogAdapter::g_Logger )
      LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
        (__int64)LogAdapter::g_Logger,
        1,
        1,
        (__int64)"Plan: Skip update: {} that points to package {} since it is semi-isolated and target state is not absent.",
        (__int64)&v169,
        (__int64)&v192);
LABEL_157:
    if ( (a5 & 0x20) != 0 )
    {
      LODWORD(v196) = 1;
      goto LABEL_159;
    }
LABEL_201:
    Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v154);
    v14 = v160;
    goto LABEL_219;
  }
  if ( *((_DWORD *)v160 + 224) )
  {
    v69 = GetFastCbsIdentityString(v154);
    v23 = *((_QWORD *)v18 + 4) == 0;
    v190 = v69;
    v70 = &qword_1802EB518;
    if ( !v23 )
      v70 = (const wchar_t *)*((_QWORD *)v18 + 4);
    v191 = v70;
    if ( LogAdapter::g_Logger )
      LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
        (__int64)LogAdapter::g_Logger,
        1,
        1,
        (__int64)"Plan: Skip update: {} that points to package {} since it is isolated",
        (__int64)&v191,
        (__int64)&v190);
    goto LABEL_157;
  }
LABEL_159:
  if ( *(_BYTE *)(*(_QWORD *)(v159 + 64) + 1744LL)
    || !(unsigned int)CCbsUpdate::IsSelectable(v18)
    || (unsigned int)CCbsUpdate::GetDeploymentType() == 5
    || v149
    || CCbsPackage::IsFODorLPPackage(v160)
    || (v198 & 0xFFFFFFDF) != 0
    || v198 >= v40
    || v40 < 64 )
  {
LABEL_186:
    v158 = 0;
    Windows::AutoNewPtr<PackageToAdd>::Allocate<>(&v158);
    v119 = v158;
    if ( !v158 )
    {
      v140 = 591;
LABEL_276:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v140,
        (unsigned int)"onecore\\base\\cbs\\core\\cbsexecutionobjectstateplanning.cpp",
        (const char *)0x8007000ELL,
        v148);
      Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v154);
      goto LABEL_277;
    }
    Windows::AutoComPtr<IServicingCache>::operator=(v158, &v154);
    *((_DWORD *)v119 + 13) |= a5;
    if ( v199 )
      *((_DWORD *)v119 + 13) |= 0x40u;
    *((_DWORD *)v119 + 2) = v40;
    Windows::AutoComPtr<CCbsPackageDeployment>::operator=((char *)v119 + 16, v66);
    v120 = (int)v196;
    *((_DWORD *)v119 + 8) = v68;
    *((_DWORD *)v119 + 9) = v120;
    *((_DWORD *)v119 + 10) = a9;
    if ( v68 == 1 )
    {
      v121 = (*(__int64 (__fastcall **)(struct CCbsIdentity *, __int64))(*(_QWORD *)v154 + 72LL))(
               v154,
               (__int64)v119 + 24);
      RoomAt = v121;
      if ( v121 < 0 )
      {
        v194 = v121;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get identity string");
          *(_QWORD *)v150 = &v194;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)v150);
        }
        v122 = 619;
        goto LABEL_194;
      }
    }
    else
    {
      v124 = &qword_1802EB518;
      if ( *((_QWORD *)v160 + 15) )
        v124 = (const wchar_t *)*((_QWORD *)v160 + 15);
      RoomAt = SczAllocFromSz((char *)v119 + 24, v124);
      if ( RoomAt < 0 )
      {
        v122 = 627;
        goto LABEL_194;
      }
    }
    v125 = *(_QWORD *)v164;
    v126 = *(_QWORD *)(*(_QWORD *)v164 + 24LL);
    RoomAt = CCbsArrayBase<SessionAction *,CCbsPointerArray<SessionAction *>>::MakeRoomAt(*(_QWORD *)v164, v126);
    if ( RoomAt >= 0 )
    {
      *(_QWORD *)(*(_QWORD *)(v125 + 40) + 8 * v126) = v119;
      v40 = v152;
      goto LABEL_201;
    }
    v122 = 630;
LABEL_194:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v122,
      (unsigned int)"onecore\\base\\cbs\\core\\cbsexecutionobjectstateplanning.cpp",
      (const char *)(unsigned int)RoomAt,
      v148);
    if ( v119 )
      PackageToAdd::`scalar deleting destructor'(v119, v123);
    goto LABEL_274;
  }
  v108 = v106 + 528;
  v109 = *(_QWORD *)(v106 + 568);
  v110 = v109 + 8LL * *(_QWORD *)(v106 + 552);
  if ( v109 != v110 )
  {
    do
    {
      if ( (**(_BYTE **)v109 & 4) != 0 )
      {
        if ( (unsigned int)CCbsIdentity::IsFastEqual(
                             *(CCbsIdentity **)(*(_QWORD *)v109 + 16LL),
                             *((struct CCbsIdentity **)v105 + 14)) )
          goto LABEL_185;
        v105 = v160;
      }
      v109 += 8;
    }
    while ( v109 != v110 );
    v107 = LogAdapter::g_Logger;
  }
  v111 = (CapabilityToChange *)&qword_1802EB518;
  if ( *((_QWORD *)v18 + 4) )
    v111 = (CapabilityToChange *)*((_QWORD *)v18 + 4);
  v23 = *((_QWORD *)v105 + 15) == 0;
  v162 = v111;
  v112 = &qword_1802EB518;
  if ( !v23 )
    v112 = (const wchar_t *)*((_QWORD *)v105 + 15);
  *(_QWORD *)v165 = v112;
  if ( v107 )
    LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
      (__int64)v107,
      1,
      1,
      (__int64)"Plan: Will attempt to restore Package: {}, Update: {}",
      (__int64)v165,
      (__int64)&v162);
  v162 = 0;
  Windows::AutoNewPtr<CapabilityToChange>::Allocate<>(&v162);
  v113 = v162;
  if ( !v162 )
  {
    v140 = 571;
    goto LABEL_276;
  }
  *(_DWORD *)v162 |= 4u;
  Windows::AutoComPtr<CCbsPublicSession>::TakeReference((char *)v113 + 16, *((_QWORD *)v160 + 14));
  v114 = &qword_1802EB518;
  if ( *((_QWORD *)v18 + 4) )
    v114 = (const wchar_t *)*((_QWORD *)v18 + 4);
  v115 = SczAllocFromSz((char *)v113 + 24, v114);
  RoomAt = v115;
  if ( v115 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x241,
      (unsigned int)"onecore\\base\\cbs\\core\\cbsexecutionobjectstateplanning.cpp",
      (const char *)(unsigned int)v115,
      v148);
    goto LABEL_273;
  }
  *((_DWORD *)v113 + 9) = v151;
  *((_DWORD *)v113 + 8) = v40;
  *((_BYTE *)v113 + 168) = 1;
  v117 = *(_QWORD *)(v108 + 24);
  v118 = CCbsArrayBase<SessionAction *,CCbsPointerArray<SessionAction *>>::MakeRoomAt(v108, v117);
  RoomAt = v118;
  if ( v118 >= 0 )
  {
    *(_QWORD *)(*(_QWORD *)(v108 + 40) + 8 * v117) = v113;
    v40 = v152;
LABEL_185:
    v66 = v158;
    v68 = UpdateOptions;
    goto LABEL_186;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x247,
    (unsigned int)"onecore\\base\\cbs\\core\\cbsexecutionobjectstateplanning.cpp",
    (const char *)(unsigned int)v118,
    v148);
  if ( v113 )
LABEL_273:
    CapabilityToChange::`scalar deleting destructor'(v113, v139);
LABEL_274:
  Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v154);
LABEL_299:
  if ( v52 )
  {
    v145 = (char *)v52 + *(int *)(*((_QWORD *)v52 + 1) + 4LL) + 8;
    (*(void (__fastcall **)(char *))(*(_QWORD *)v145 + 16LL))(v145);
  }
  return (unsigned int)RoomAt;
}

```

## disassembly

```asm
0x1801680f4  mov     [rsp-8+arg_8], rbx
0x1801680f9  push    rbp
0x1801680fa  push    rsi
0x1801680fb  push    rdi
0x1801680fc  push    r12
0x1801680fe  push    r13
0x180168100  push    r14
0x180168102  push    r15
0x180168104  lea     rbp, [rsp-100h]
0x18016810c  sub     rsp, 200h
0x180168113  mov     rax, cs:__security_cookie
0x18016811a  xor     rax, rsp
0x18016811d  mov     [rbp+130h+var_40], rax
0x180168124  mov     rax, [rbp+130h+arg_30]
0x18016812b  mov     r14, rcx
0x18016812e  mov     rdx, [rbp+130h+arg_28]
0x180168135  mov     r13, r8
0x180168138  mov     [rbp+130h+var_130], rax
0x18016813c  mov     eax, [rbp+130h+arg_50]
0x180168142  mov     [rbp+130h+var_60], eax
0x180168148  mov     rax, [rbp+130h+arg_58]
0x18016814f  mov     qword ptr [rbp+130h+var_150], rax
0x180168153  mov     rax, [r8+2E0h]
0x18016815a  mov     [rbp+130h+var_178], rcx
0x18016815e  mov     rcx, [r8+2F0h]
0x180168165  mov     [rbp+130h+var_48], r9d
0x18016816c  mov     [rbp+130h+var_170], r8
0x180168170  mov     qword ptr [rsp+230h+var_1B8], rdx
0x180168175  lea     rax, [rcx+rax*8]
0x180168179  mov     [rbp+130h+var_138], rcx
0x18016817d  mov     qword ptr [rbp+130h+var_1A8], rax
0x180168181  cmp     rcx, rax
0x180168184  jz      loc_180169CDD
0x18016818a  lea     rsi, qword_1802EB518
0x180168191  mov     r15, [rcx]
0x180168194  lea     rax, [rbp+130h+var_168]
0x180168198  mov     rcx, [r14+40h]; this
0x18016819c  mov     r8, rdx; struct PerSessionPackageState *
0x18016819f  mov     rdx, r15; struct CCbsUpdate *
0x1801681a2  mov     [rbp+130h+var_198], 1000h
0x1801681a9  mov     r9d, 1; int
0x1801681af  mov     [rbp+130h+var_1B0], 1000h
0x1801681b6  mov     [rbp+130h+var_50], 0FFFFFFFFh
0x1801681c0  mov     dword ptr [rbp+130h+var_58], 0
0x1801681ca  mov     [rsp+230h+var_1C0], 0
0x1801681cf  mov     [rbp+130h+var_168], 0
0x1801681d7  mov     [rsp+230h+var_210], rax; struct PerSessionUpdateState **
0x1801681dc  call    ?GetSessionUpdateState@CCbsSession@@QEAAJPEAVCCbsUpdate@@PEAUPerSessionPackageState@@HPEAPEAUPerSessionUpdateState@@@Z; CCbsSession::GetSessionUpdateState(CCbsUpdate *,PerSessionPackageState *,int,PerSessionUpdateState * *)
0x1801681e1  mov     ebx, eax
0x1801681e3  test    eax, eax
0x1801681e5  js      loc_180169C6A
0x1801681eb  mov     rdx, [r14+40h]; struct CCbsSession *
0x1801681ef  lea     r8, [rbp+130h+var_198]; enum CbsState *
0x1801681f3  mov     rcx, r15; this
0x1801681f6  call    ?GetCurrentState@CCbsUpdate@@QEAAJPEAVCCbsSession@@PEAW4CbsState@@@Z; CCbsUpdate::GetCurrentState(CCbsSession *,CbsState *)
0x1801681fb  mov     ebx, eax
0x1801681fd  test    eax, eax
0x1801681ff  js      loc_180169C0F
0x180168205  cmp     [rbp+130h+arg_48], 0
0x18016820c  jnz     short loc_18016826A
0x18016820e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180168215  xor     edi, edi
0x180168217  cmp     [r15+20h], rdi
0x18016821b  mov     rax, rsi
0x18016821e  cmovnz  rax, [r15+20h]
0x180168223  cmp     [r13+78h], rdi
0x180168227  mov     [rbp+130h+var_188], rax
0x18016822b  mov     rax, rsi
0x18016822e  cmovnz  rax, [r13+78h]
0x180168233  mov     [rbp+130h+var_180], rax
0x180168237  test    rcx, rcx
0x18016823a  jz      loc_180168448
0x180168240  lea     rax, [rbp+130h+var_188]
0x180168244  mov     [rsp+230h+var_208], rax
0x180168249  lea     r8d, [rdi+1]
0x18016824d  lea     rax, [rbp+130h+var_180]
0x180168251  mov     dl, r8b
0x180168254  lea     r9, aPlanForcePacka; "Plan: Force package:{}, update: {} into"...
0x18016825b  mov     [rsp+230h+var_210], rax
0x180168260  call    ??$LogNumObjects@PEB_WPEA_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_WAEBQEA_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &,wchar_t * const &)
0x180168265  jmp     loc_180168448
0x18016826a  mov     r12, [rbp+130h+var_168]
0x18016826e  lea     rax, [rsp+230h+var_1C0]
0x180168273  mov     rdx, [r14+40h]; struct CCbsSession *
0x180168277  lea     r9, [rbp+130h+var_1B0]; enum CbsState *
0x18016827b  mov     r8, r12; struct PerSessionUpdateState *
0x18016827e  mov     [rsp+230h+var_210], rax; bool *
0x180168283  mov     rcx, r15; this
0x180168286  call    ?GetApplicableSelectableState@CCbsUpdate@@QEAAJPEAVCCbsSession@@PEAUPerSessionUpdateState@@PEAW4CbsState@@PEA_N@Z; CCbsUpdate::GetApplicableSelectableState(CCbsSession *,PerSessionUpdateState *,CbsState *,bool *)
0x18016828b  mov     ebx, eax
0x18016828d  test    eax, eax
0x18016828f  js      loc_180169BAF
0x180168295  mov     rcx, r15; this
0x180168298  call    ?IsSelectable@CCbsUpdate@@QEBAHXZ; CCbsUpdate::IsSelectable(void)
0x18016829d  test    eax, eax
0x18016829f  jz      loc_1801683B1
0x1801682a5  mov     edi, [rbp+130h+var_1B0]
0x1801682a8  cmp     edi, 20h ; ' '
0x1801682ab  jle     loc_1801683B4
0x1801682b1  cmp     qword ptr [r15+20h], 0
0x1801682b6  mov     rdx, rsi
0x1801682b9  mov     rcx, [r14+40h]; this
0x1801682bd  cmovnz  rdx, [r15+20h]; wchar_t *
0x1801682c2  call    ?GetDeferredOCAction@CCbsSession@@QEBAQEBUSessionAction@@QEB_W@Z; CCbsSession::GetDeferredOCAction(wchar_t const * const)
0x1801682c7  mov     r8, rax
0x1801682ca  test    rax, rax
0x1801682cd  jz      loc_1801683B4
0x1801682d3  cmp     dword ptr [rax], 3
0x1801682d6  jnz     loc_1801683B4
0x1801682dc  mov     rcx, rax
0x1801682df  call    ?GetSelection@SessionAction@@QEBA?AW4UpdateSelection@@XZ; SessionAction::GetSelection(void)
0x1801682e4  mov     rcx, r8
0x1801682e7  mov     ebx, eax
0x1801682e9  call    ?GetUpdateOptions@SessionAction@@QEBA?AW4_CbsUpdateOption@@XZ; SessionAction::GetUpdateOptions(void)
0x1801682ee  mov     ecx, ebx
0x1801682f0  mov     [rbp+130h+var_5C], eax
0x1801682f6  mov     r10d, eax
0x1801682f9  call    ?CbsSelectionToString@@YAPEB_WW4UpdateSelection@@@Z; CbsSelectionToString(UpdateSelection)
0x1801682fe  xor     edi, edi
0x180168300  mov     [rbp+130h+var_188], rax
0x180168304  cmp     [r15+20h], rdi
0x180168308  mov     rcx, rsi
0x18016830b  cmovnz  rcx, [r15+20h]
0x180168310  cmp     [r13+78h], rdi
0x180168314  mov     [rbp+130h+var_180], rcx
0x180168318  mov     rcx, rsi
0x18016831b  cmovnz  rcx, [r13+78h]
0x180168320  mov     [rbp+130h+var_160], rcx
0x180168324  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18016832b  test    rcx, rcx
0x18016832e  jz      short loc_18016836A
0x180168330  lea     rax, [rbp+130h+var_5C]
0x180168337  mov     [rsp+230h+var_1F8], rax
0x18016833c  lea     r9, aApplForcePacka; "Appl: Force package: {}, update: {}, se"...
0x180168343  lea     rax, [rbp+130h+var_188]
0x180168347  mov     [rsp+230h+var_200], rax
0x18016834c  lea     rax, [rbp+130h+var_180]
0x180168350  mov     [rsp+230h+var_208], rax
0x180168355  lea     rax, [rbp+130h+var_160]
0x180168359  mov     [rsp+230h+var_210], rax
0x18016835e  call    ??$LogNumObjects@PEB_WPEB_WPEB_WK@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W33AEBK@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t const *,wchar_t const *,ulong>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &,wchar_t const * const &,wchar_t const * const &,ulong const &)
0x180168363  mov     r10d, [rbp+130h+var_5C]
0x18016836a  mov     r8, [r14+40h]
0x18016836e  mov     r9d, ebx
0x180168371  mov     edx, r10d
0x180168374  mov     dword ptr [rsp+230h+var_210], edi
0x180168378  mov     rcx, r15
0x18016837b  call    ?SetInstallState@CCbsUpdate@@QEAAJKPEAVCCbsSession@@W4UpdateSelection@@H@Z; CCbsUpdate::SetInstallState(ulong,CCbsSession *,UpdateSelection,int)
0x180168380  mov     ebx, eax
0x180168382  test    eax, eax
0x180168384  js      loc_18016923A
0x18016838a  mov     rdx, [r14+40h]; struct CCbsSession *
0x18016838e  lea     rax, [rsp+230h+var_1C0]
0x180168393  lea     r9, [rbp+130h+var_1B0]; enum CbsState *
0x180168397  mov     [rsp+230h+var_210], rax; bool *
0x18016839c  mov     r8, r12; struct PerSessionUpdateState *
0x18016839f  mov     rcx, r15; this
0x1801683a2  call    ?GetApplicableSelectableState@CCbsUpdate@@QEAAJPEAVCCbsSession@@PEAUPerSessionUpdateState@@PEAW4CbsState@@PEA_N@Z; CCbsUpdate::GetApplicableSelectableState(CCbsSession *,PerSessionUpdateState *,CbsState *,bool *)
0x1801683a7  mov     ebx, eax
0x1801683a9  test    eax, eax
0x1801683ab  js      loc_1801691DA
0x1801683b1  mov     edi, [rbp+130h+var_1B0]
0x1801683b4  mov     r12d, 70h ; 'p'
0x1801683ba  cmp     edi, r12d
0x1801683bd  jz      loc_180168448
0x1801683c3  test    [rbp+130h+arg_20], 20000h
0x1801683cd  jz      short loc_180168448
0x1801683cf  mov     rax, [r14+40h]
0x1801683d3  cmp     byte ptr [rax+6D0h], 0
0x1801683da  jz      short loc_180168448
0x1801683dc  mov     ecx, r12d
0x1801683df  mov     edi, r12d
0x1801683e2  call    ?CbsStateToString@@YAPEB_WW4CbsState@@@Z; CbsStateToString(CbsState)
0x1801683e7  cmp     qword ptr [r15+20h], 0
0x1801683ec  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801683f3  mov     [rbp+130h+var_120], rax
0x1801683f7  mov     rax, rsi
0x1801683fa  cmovnz  rax, [r15+20h]
0x1801683ff  cmp     qword ptr [r13+78h], 0
0x180168404  mov     [rbp+130h+var_118], rax
0x180168408  mov     rax, rsi
0x18016840b  cmovnz  rax, [r13+78h]
0x180168410  mov     [rbp+130h+var_110], rax
0x180168414  test    rcx, rcx
0x180168417  jz      short loc_180168448
0x180168419  lea     rax, [rbp+130h+var_120]
0x18016841d  mov     [rsp+230h+var_200], rax
0x180168422  lea     r8d, [r12-6Fh]
0x180168427  lea     rax, [rbp+130h+var_118]
0x18016842b  mov     dl, r8b
0x18016842e  mov     [rsp+230h+var_208], rax
0x180168433  lea     r9, aApplForcePacka_0; "Appl: Force package: {}, update: {}, ap"...
0x18016843a  lea     rax, [rbp+130h+var_110]
0x18016843e  mov     [rsp+230h+var_210], rax
0x180168443  call    ??$LogNumObjects@PEB_WVAutoScz@@PEA_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_WAEBVAutoScz@@AEBQEA_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *,AutoScz,wchar_t *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &,AutoScz const &,wchar_t * const &)
0x180168448  mov     rdx, [r14+40h]; struct CCbsSession *
0x18016844c  lea     rax, [rbp+130h+var_58]
0x180168453  lea     r9, [rbp+130h+var_50]; enum UpdateSelection *
0x18016845a  mov     [rsp+230h+var_210], rax; int *
0x18016845f  mov     r8b, 1; bool
0x180168462  mov     rcx, r15; this
0x180168465  call    ?GetUserSelectionWithAdjustment@CCbsUpdate@@QEAAJPEAVCCbsSession@@_NPEAW4UpdateSelection@@PEAH@Z; CCbsUpdate::GetUserSelectionWithAdjustment(CCbsSession *,bool,UpdateSelection *,int *)
0x18016846a  mov     ebx, eax
0x18016846c  test    eax, eax
0x18016846e  js      loc_180169B4E
0x180168474  cmp     [rbp+130h+arg_48], edi
0x18016847a  mov     r12d, edi
0x18016847d  mov     [rbp+130h+var_5C], 1000h
0x180168487  cmovl   r12d, [rbp+130h+arg_48]
0x18016848f  cmp     byte ptr [r14+378h], 0
0x180168497  mov     [rbp+130h+var_1AC], r12d
0x18016849b  jz      short loc_1801684B3
0x18016849d  lea     rdx, aPlanSubExecuti_0; "Plan: Sub-Execution, use current state "...
0x1801684a4  mov     ecx, 1
0x1801684a9  call    ??$TraceAtLevel@$$V@LogAdapter@@YAXW4LogLevel@0@QEBD@Z; LogAdapter::TraceAtLevel<>(LogAdapter::LogLevel,char const * const)
0x1801684ae  mov     ecx, [rbp+130h+var_198]
0x1801684b1  jmp     short loc_1801684D9
0x1801684b3  mov     rdx, [r14+40h]
0x1801684b7  lea     r9, [rbp+130h+var_5C]
0x1801684be  mov     r8d, r12d
0x1801684c1  mov     rcx, r15
0x1801684c4  call    ?GetStartState@CCbsUpdate@@QEAAJPEAVCCbsSession@@W4CbsState@@PEAW43@@Z; CCbsUpdate::GetStartState(CCbsSession *,CbsState,CbsState *)
0x1801684c9  mov     ebx, eax
0x1801684cb  test    eax, eax
0x1801684cd  js      loc_180169AD7
0x1801684d3  mov     ecx, [rbp+130h+var_5C]
0x1801684d9  mov     edx, r12d
0x1801684dc  call    ?EquivalentStateIfInvalid@@YA?AW4CbsState@@W41@0@Z; EquivalentStateIfInvalid(CbsState,CbsState)
0x1801684e1  mov     [rbp+130h+var_1B0], eax
0x1801684e4  mov     ebx, eax
0x1801684e6  cmp     r12d, 1000h
0x1801684ed  jz      loc_180169A5A
0x1801684f3  mov     ecx, [rbp+130h+var_50]
0x1801684f9  call    ?CbsSelectionToString@@YAPEB_WW4UpdateSelection@@@Z; CbsSelectionToString(UpdateSelection)
0x1801684fe  mov     ecx, [rbp+130h+var_60]
0x180168504  mov     [rbp+130h+var_188], rax
0x180168508  call    ?CbsStateToString@@YAPEB_WW4CbsState@@@Z; CbsStateToString(CbsState)
0x18016850d  mov     ecx, r12d
0x180168510  mov     [rbp+130h+var_108], rax
0x180168514  call    ?CbsStateToString@@YAPEB_WW4CbsState@@@Z; CbsStateToString(CbsState)
0x180168519  mov     ecx, edi
0x18016851b  mov     [rbp+130h+var_100], rax
0x18016851f  call    ?CbsStateToString@@YAPEB_WW4CbsState@@@Z; CbsStateToString(CbsState)
0x180168524  mov     ecx, ebx
0x180168526  mov     [rbp+130h+var_F8], rax
0x18016852a  call    ?CbsStateToString@@YAPEB_WW4CbsState@@@Z; CbsStateToString(CbsState)
0x18016852f  mov     ecx, 1000h
0x180168534  mov     [rbp+130h+var_F0], rax
0x180168538  call    ?CbsStateToString@@YAPEB_WW4CbsState@@@Z; CbsStateToString(CbsState)
0x18016853d  mov     ecx, [rbp+130h+var_198]
0x180168540  mov     [rbp+130h+var_E8], rax
0x180168544  call    ?CbsStateToString@@YAPEB_WW4CbsState@@@Z; CbsStateToString(CbsState)
0x180168549  cmp     qword ptr [r15+20h], 0
0x18016854e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180168555  mov     [rbp+130h+var_E0], rax
0x180168559  mov     rax, rsi
0x18016855c  cmovnz  rax, [r15+20h]
0x180168561  cmp     qword ptr [r13+78h], 0
0x180168566  mov     [rbp+130h+var_D8], rax
0x18016856a  mov     rax, rsi
0x18016856d  cmovnz  rax, [r13+78h]
0x180168572  mov     qword ptr [rbp+130h+var_D0], rax
0x180168576  test    rcx, rcx
0x180168579  jz      short loc_1801685D1
0x18016857b  lea     rax, [rbp+130h+var_188]
0x18016857f  mov     [rsp+230h+var_1D0], rax
0x180168584  lea     rax, [rbp+130h+var_108]
0x180168588  mov     [rsp+230h+var_1D8], rax
0x18016858d  lea     rax, [rbp+130h+var_100]
0x180168591  mov     [rsp+230h+var_1E0], rax
0x180168596  lea     rax, [rbp+130h+var_F8]
0x18016859a  mov     [rsp+230h+var_1E8], rax
0x18016859f  lea     rax, [rbp+130h+var_F0]
0x1801685a3  mov     [rsp+230h+var_1F0], rax
0x1801685a8  lea     rax, [rbp+130h+var_E8]
0x1801685ac  mov     [rsp+230h+var_1F8], rax
0x1801685b1  lea     rax, [rbp+130h+var_E0]
0x1801685b5  mov     [rsp+230h+var_200], rax
0x1801685ba  lea     rax, [rbp+130h+var_D8]
0x1801685be  mov     [rsp+230h+var_208], rax
0x1801685c3  lea     rax, [rbp+130h+var_D0]
0x1801685c7  mov     [rsp+230h+var_210], rax; int
0x1801685cc  call    ??$LogNumObjects@PEB_WPEB_WPEB_WPEB_WPEB_WPEB_WPEB_WPEB_WPEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W33333333@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &,wchar_t const * const &,wchar_t const * const &,wchar_t const * const &,wchar_t const * const &,wchar_t const * const &,wchar_t const * const &,wchar_t const * const &,wchar_t const * const &)
0x1801685d1  mov     rcx, [r14+18h]
0x1801685d5  test    rcx, rcx
0x1801685d8  jz      short loc_180168610
0x1801685da  mov     eax, [rbp+130h+arg_40]
0x1801685e0  xor     r9d, r9d
0x1801685e3  mov     r10, [rcx]
0x1801685e6  test    eax, eax
0x1801685e8  mov     edx, 20h ; ' '
0x1801685ed  setz    r9b
0x1801685f1  neg     eax
0x1801685f3  mov     rax, [r10+28h]
0x1801685f7  sbb     r8d, r8d
0x1801685fa  neg     r8d
0x1801685fd  add     r8d, 0FFFFFFFEh
0x180168601  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180168606  mov     ebx, eax
0x180168608  test    eax, eax
  ... truncated ...
```
