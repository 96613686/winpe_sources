# CCbsExecutionComponent::Execute(IServicingCommitter *,ICSITransaction *,CCbsExecutionCommunication *,ExecutionItemAction)

- ea: `0x180046754`
- end: `0x180048110`
- name: `?Execute@CCbsExecutionComponent@@UEAAJPEAVIServicingCommitter@@PEAUICSITransaction@@PEAVCCbsExecutionCommunication@@W4ExecutionItemAction@@@Z`
- size: `6588`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180167760`

## callees

- `0x180010cc0`
- `0x180010f54`
- `0x1800110d0`
- `0x180012fe4`
- `0x180028e24`
- `0x180046754`
- `0x180048118`
- `0x18004854c`
- `0x18006822c`
- `0x180093a70`
- `0x180098538`
- `0x180099390`
- `0x180099548`
- `0x18009cf78`
- `0x1800a4b58`
- `0x1800a8678`
- `0x1800bc75c`
- `0x1800eb920`
- `0x18012b54c`
- `0x1801461a4`
- `0x1801c3524`
- `0x1802d5010`

## string_xrefs

- `0x18004691e`: `onecore\base\cbs\core\cbsexecutioncomponent.cpp`
- `0x180047fd2`: `onecore\base\cbs\core\cbsexecutioncomponent.cpp`
- `0x180046859`: `Item action for Component Executions should never be ExecutionItemActionDefault because it doesn't do anything`
- `0x1800478f4`: `Failed adding unproject component operation`
- `0x180047c11`: `Failed adding unproject component operation`
- `0x1800475c8`: `Exec: Unprojecting/Unmarking Package: {}, Update: {}, UninstallDeployment/UnstageDeployment: {}`
- `0x180047018`: `Failed to begin deployment uninstallation for Update: {}`
- `0x180047656`: `Failed to begin deployment uninstallation for Update: {}`
- `0x180047a21`: `Failed to begin deployment uninstallation for Update: {}`
- `0x1800470c5`: `ComponentAnalyzerUninstallDeployment: Failed on update: {}`
- `0x1800473e7`: `ComponentAnalyzerUninstallDeployment: Failed on update: {}`
- `0x18004785b`: `ComponentAnalyzerUninstallDeployment: Failed on update: {}`
- `0x180047b78`: `ComponentAnalyzerUninstallDeployment: Failed on update: {}`
- `0x18004752d`: `Failed adding uninstall component operation`
- `0x180047cac`: `Exec: Installing Package: {}, Update: {}, InstallDeployment: {}`
- `0x180046e61`: `Exec: Unmarking Package: {}, Update: {}, UnstageDeployment: {}`
- `0x180047290`: `Failed to unpin deployment after uninstall for Update '{}'`
- `0x180046a80`: `Failed to unpin deployment for Update '{}'`
- `0x180046c52`: `Failed to unpin deployment for Update '{}'`
- `0x180046cff`: `Failed to MarkDeploymentUntaged while staging Update: {}`
- `0x180046ed9`: `Failed to MarkDeploymentUntaged while staging Update: {}`
- `0x1800471e3`: `Failed to MarkDeploymentUntaged while staging Update: {}`
- `0x180047704`: `Failed to MarkDeploymentUntaged while staging Update: {}`
- `0x1800468db`: `Could not acquire an ICSITransaction2 from ICSITransaction, mismatched wcp.dll and cbscore.dll?`
- `0x180046be2`: `Exec: Unstaging Package: {}, Update: {}, UnstageDeployment/UnpinDeployment: {}`
- `0x180046f8a`: `Exec: Unprojecting Package: {}, Update: {}, UninstallDeployment: {}`
- `0x18004798f`: `Exec: Unprojecting Package: {}, Update: {}, UninstallDeployment: {}`
- `0x18004733a`: `Failed to install manifest for Update: {}`
- `0x1800477ae`: `Failed to install manifest for Update: {}`
- `0x180047acb`: `Failed to install manifest for Update: {}`
- `0x180047ed0`: `Failed to install manifest for Update: {}`
- `0x180046b31`: `ComponentAnalyzerUnPinDeployment: Failed on update: {}`
- `0x180046db0`: `ComponentAnalyzerUnPinDeployment: Failed on update: {}`
- `0x180047494`: `ComponentAnalyzerUnPinDeployment: Failed on update: {}`
- `0x180046a1c`: `Exec: Unpinning Package: {}, Update: {}, UnpinDeployment: {}`
- `0x18004716f`: `Exec: Unpinning Package: {}, Update: {}, UnpinDeployment: {}`
- `0x180047e26`: `Failed to begin deployment installation for Update: {}`
- `0x180047f82`: `ComponentAnalyzerInstallDeployment: Failed on update: {}`
- `0x180047d15`: `Failed to get stored catalog path for package: {}`
- `0x180047df7`: `Unable to verify manifest against catalog, mark store as corrupt.`
- `0x18004806b`: `Failed adding install component operation`

## pseudocode

```c
__int64 __fastcall CCbsExecutionComponent::Execute(
        __int64 a1,
        __int64 a2,
        __int64 (__fastcall ***a3)(_QWORD, GUID *, __int64),
        __int64 a4,
        int a5)
{
  unsigned int v8; // ebx
  __int64 v9; // rdx
  __int64 (__fastcall *v10)(_QWORD, GUID *, __int64); // rbx
  __int64 InitPointer; // rax
  int v12; // eax
  struct IDefinitionIdentity **v13; // rax
  int v14; // edx
  const wchar_t *v15; // rsi
  __int64 v16; // rax
  wchar_t *v17; // rcx
  __int64 v18; // rax
  const wchar_t *v19; // rcx
  int v20; // eax
  __int64 v21; // rax
  int v22; // eax
  __int64 v23; // rax
  int v24; // edx
  const wchar_t *v25; // rsi
  __int64 v26; // rax
  const wchar_t *v27; // rcx
  __int64 v28; // rax
  wchar_t *v29; // rcx
  int v30; // eax
  __int64 v31; // rax
  int v32; // eax
  __int64 v33; // rax
  int v34; // eax
  __int64 v35; // rax
  int v36; // edx
  const wchar_t *v37; // rsi
  __int64 v38; // rax
  const wchar_t *v39; // rcx
  __int64 v40; // rax
  wchar_t *v41; // rcx
  int v42; // eax
  __int64 v43; // rax
  int v44; // edx
  const wchar_t *v45; // rsi
  __int64 v46; // rax
  const wchar_t *v47; // rcx
  __int64 v48; // rax
  wchar_t *v49; // rcx
  int v50; // ecx
  int v51; // eax
  __int64 v52; // rax
  int v53; // eax
  __int64 v54; // rax
  int v55; // edx
  const wchar_t *v56; // rcx
  __int64 v57; // rax
  __int64 v58; // rax
  wchar_t *v59; // rcx
  int v60; // eax
  __int64 v61; // rax
  int v62; // eax
  __int64 v63; // rax
  __int64 v64; // rdx
  const wchar_t *v65; // r9
  const wchar_t *v66; // r8
  __int64 v67; // rax
  int v68; // eax
  __int64 v69; // rax
  int v70; // eax
  __int64 v71; // rax
  int v72; // eax
  __int64 v73; // rax
  int v74; // eax
  int v75; // edx
  const wchar_t *v76; // rsi
  __int64 v77; // rax
  const wchar_t *v78; // rcx
  __int64 v79; // rax
  wchar_t *v80; // rcx
  int v81; // ecx
  int v82; // eax
  __int64 v83; // rax
  int v84; // eax
  __int64 v85; // rax
  __int64 v86; // rcx
  const wchar_t *v87; // r9
  const wchar_t *v88; // r8
  __int64 v89; // rax
  int v90; // eax
  __int64 v91; // rax
  int v92; // eax
  __int64 v93; // rax
  int v94; // eax
  int v95; // edx
  const wchar_t *v96; // rsi
  __int64 v97; // rax
  const wchar_t *v98; // rcx
  __int64 v99; // rax
  wchar_t *v100; // rcx
  int v101; // ecx
  int v102; // eax
  __int64 v103; // rax
  __int64 v104; // rcx
  const wchar_t *v105; // r9
  const wchar_t *v106; // r8
  __int64 v107; // rax
  int v108; // eax
  __int64 v109; // rax
  int v110; // eax
  __int64 v111; // rax
  int v112; // eax
  int v113; // edx
  const wchar_t *v114; // rsi
  __int64 v115; // rax
  const wchar_t *v116; // rcx
  __int64 v117; // rax
  const wchar_t *v118; // rcx
  struct CCbsSession *v119; // rdx
  int v120; // eax
  int StoredCatalogPath; // eax
  __int64 v122; // rdx
  CCbsSession *v123; // rcx
  int v124; // eax
  __int64 v125; // rax
  __int64 v126; // rcx
  const wchar_t *v127; // r9
  const wchar_t *v128; // r8
  __int64 v129; // rax
  int v130; // eax
  __int64 v131; // rax
  int v132; // eax
  __int64 v133; // rdx
  int v134; // eax
  int v136; // [rsp+20h] [rbp-81h]
  int v137; // [rsp+20h] [rbp-81h]
  char v138[8]; // [rsp+60h] [rbp-41h] BYREF
  int v139[2]; // [rsp+68h] [rbp-39h] BYREF
  int v140[2]; // [rsp+70h] [rbp-31h] BYREF
  struct IDefinitionIdentity *v141; // [rsp+78h] [rbp-29h] BYREF
  wchar_t **v142; // [rsp+80h] [rbp-21h] BYREF
  _QWORD v143[2]; // [rsp+88h] [rbp-19h] BYREF
  char v144; // [rsp+98h] [rbp-9h]
  wchar_t *v145; // [rsp+A0h] [rbp-1h] BYREF
  __int64 v146; // [rsp+A8h] [rbp+7h] BYREF
  int v147; // [rsp+B0h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+57h]

  v143[1] = &vComponentAnalyzerLock;
  v141 = 0;
  v143[0] = &PackageTrackerLocker::`vftable';
  v146 = 0;
  v147 = 0;
  v145 = 0;
  v144 = 0;
  MonitoredCritSecLocker::Lock((MonitoredCritSecLocker *)v143);
  v138[0] = 1;
  if ( vpfnTiLockProcess )
    vpfnTiLockProcess(0);
  if ( !a3 )
  {
    v8 = -2147024809;
    LODWORD(v145) = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No transaction specified");
      *(_QWORD *)v140 = &v145;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)v140);
    }
    v9 = 263;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\base\\cbs\\core\\cbsexecutioncomponent.cpp",
      (const char *)v8,
      v136);
    AutoCsiStoreLock::~AutoCsiStoreLock((AutoCsiStoreLock *)v138);
    MonitoredCritSecLocker::~MonitoredCritSecLocker((MonitoredCritSecLocker *)v143);
    if ( v146 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v146 + 16LL))(v146);
      v146 = 0;
    }
LABEL_271:
    Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v141);
    return v8;
  }
  if ( !a5 )
  {
    v8 = -2147024809;
    LODWORD(v145) = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Item action for Component Executions should never be Execution"
                                                          "ItemActionDefault because it doesn't do anything");
      *(_QWORD *)v140 = &v145;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)v140);
    }
    v9 = 265;
    goto LABEL_15;
  }
  v10 = **a3;
  InitPointer = Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v146);
  v12 = v10(a3, &GUID_0e695bd1_628c_40a1_88cf_925083986d16, InitPointer);
  v8 = v12;
  if ( v12 < 0 )
  {
    LODWORD(v145) = v12;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Could not acquire an ICSITransaction2 from ICSITransaction, mi"
                                                          "smatched wcp.dll and cbscore.dll?");
      *(_QWORD *)v140 = &v145;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)v140);
    }
    v9 = 269;
    goto LABEL_15;
  }
  v13 = (struct IDefinitionIdentity **)Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v141);
  CCbsExecutionComponent::GetIdentity((CCbsExecutionComponent *)(a1 - 72), v13);
  if ( a5 != 3 )
  {
    switch ( a5 )
    {
      case 4:
        *(_QWORD *)v139 = GetFastIdentityString(v141);
        v96 = &qword_1802EB518;
        v97 = *(_QWORD *)(a1 - 40);
        v98 = &qword_1802EB518;
        if ( *(_QWORD *)(v97 + 32) )
          v98 = *(const wchar_t **)(v97 + 32);
        v99 = *(_QWORD *)(a1 - 48);
        *(_QWORD *)v140 = v98;
        v100 = (wchar_t *)&qword_1802EB518;
        if ( *(_QWORD *)(v99 + 120) )
          v100 = *(wchar_t **)(v99 + 120);
        v145 = v100;
        if ( LogAdapter::g_Logger )
        {
          LOBYTE(v95) = 1;
          LogAdapter::Logger::LogNumObjects<wchar_t const *,AutoScz,wchar_t *>(
            (_DWORD)LogAdapter::g_Logger,
            v95,
            1,
            (unsigned int)"Exec: Unprojecting Package: {}, Update: {}, UninstallDeployment: {}",
            (__int64)&v145,
            (__int64)v140,
            (__int64)v139);
        }
        v101 = *(_DWORD *)(*(_QWORD *)(a1 - 32) + 692LL);
        if ( (v101 & 0x80000) != 0 || (v101 & 0x400) != 0 )
        {
          v104 = *(_QWORD *)(a1 - 48);
          v105 = &qword_1802EB518;
          v106 = &qword_1802EB518;
          v107 = *(_QWORD *)(a1 - 40);
          if ( *(_QWORD *)(v107 + 32) )
            v105 = *(const wchar_t **)(v107 + 32);
          if ( *(_QWORD *)(v104 + 120) )
            v106 = *(const wchar_t **)(v104 + 120);
          v108 = (*(__int64 (__fastcall **)(__int64, struct IDefinitionIdentity *, const wchar_t *, const wchar_t *))(*(_QWORD *)a2 + 64LL))(
                   a2,
                   v141,
                   v106,
                   v105);
          v8 = v108;
          if ( v108 < 0 )
          {
            LODWORD(v145) = v108;
            if ( LogAdapter::g_Logger )
            {
              v109 = *(_QWORD *)(a1 - 40);
              if ( *(_QWORD *)(v109 + 32) )
                v96 = *(const wchar_t **)(v109 + 32);
              *(_QWORD *)v139 = v96;
              LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                (__int64)LogAdapter::g_Logger,
                0,
                3,
                (__int64)"Failed to install manifest for Update: {}",
                (__int64)v139);
              *(_QWORD *)v140 = &v145;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (__int64)LogAdapter::g_Logger,
                1,
                3,
                (__int64)": {}",
                (__int64)v140);
            }
            v9 = 322;
            goto LABEL_15;
          }
        }
        else
        {
          v136 = 0;
          v102 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64), _QWORD, struct IDefinitionIdentity *, _QWORD))(*a3)[5])(
                   a3,
                   0,
                   v141,
                   0);
          v8 = v102;
          if ( v102 < 0 )
          {
            LODWORD(v145) = v102;
            if ( LogAdapter::g_Logger )
            {
              v103 = *(_QWORD *)(a1 - 40);
              if ( *(_QWORD *)(v103 + 32) )
                v96 = *(const wchar_t **)(v103 + 32);
              *(_QWORD *)v139 = v96;
              LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                (__int64)LogAdapter::g_Logger,
                0,
                3,
                (__int64)"Failed to begin deployment uninstallation for Update: {}",
                (__int64)v139);
              *(_QWORD *)v140 = &v145;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (__int64)LogAdapter::g_Logger,
                1,
                3,
                (__int64)": {}",
                (__int64)v140);
            }
            v9 = 328;
            goto LABEL_15;
          }
        }
        v110 = ComponentAnalyzerChangeDeployment(
                 *(struct CCbsSession **)(a1 - 32),
                 *(_QWORD *)(a1 - 40) + 376LL,
                 4,
                 *(_QWORD *)(a1 - 16) != 0);
        v8 = v110;
        if ( v110 < 0 )
        {
          LODWORD(v145) = v110;
          if ( LogAdapter::g_Logger )
          {
            v111 = *(_QWORD *)(a1 - 40);
            if ( *(_QWORD *)(v111 + 32) )
              v96 = *(const wchar_t **)(v111 + 32);
            *(_QWORD *)v139 = v96;
            LogAdapter::Logger::LogNumObjects<wchar_t const *>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (__int64)"ComponentAnalyzerUninstallDeployment: Failed on update: {}",
              (__int64)v139);
            *(_QWORD *)v140 = &v145;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {}",
              (__int64)v140);
          }
          v9 = 334;
          goto LABEL_15;
        }
        if ( *(_QWORD *)(a1 - 16) )
        {
          v136 = 1;
          v112 = DoqAddDriverOperation(*(_QWORD *)(a1 - 32), *(_QWORD *)(a1 - 48), *(_QWORD *)(a1 - 40));
          v8 = v112;
          if ( v112 < 0 )
          {
            LODWORD(v145) = v112;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                (__int64)LogAdapter::g_Logger,
                0,
                3,
                (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed adding unproject component operation");
              *(_QWORD *)v139 = &v145;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (__int64)LogAdapter::g_Logger,
                1,
                3,
                (__int64)": {}",
                (__int64)v139);
            }
            v9 = 340;
            goto LABEL_15;
          }
        }
        break;
      case 5:
        *(_QWORD *)v139 = GetFastIdentityString(v141);
        v76 = &qword_1802EB518;
        v77 = *(_QWORD *)(a1 - 40);
        v78 = &qword_1802EB518;
        if ( *(_QWORD *)(v77 + 32) )
          v78 = *(const wchar_t **)(v77 + 32);
        v79 = *(_QWORD *)(a1 - 48);
        *(_QWORD *)v140 = v78;
        v80 = (wchar_t *)&qword_1802EB518;
        if ( *(_QWORD *)(v79 + 120) )
          v80 = *(wchar_t **)(v79 + 120);
        v145 = v80;
        if ( LogAdapter::g_Logger )
        {
          LOBYTE(v75) = 1;
          LogAdapter::Logger::LogNumObjects<wchar_t const *,AutoScz,wchar_t *>(
            (_DWORD)LogAdapter::g_Logger,
            v75,
            1,
            (unsigned int)"Exec: Unprojecting/Unmarking Package: {}, Update: {}, UninstallDeployment/UnstageDeployment: {}",
            (__int64)&v145,
            (__int64)v140,
            (__int64)v139);
        }
        v81 = *(_DWORD *)(*(_QWORD *)(a1 - 32) + 692LL);
        if ( (v81 & 0x80000) != 0 || (v81 & 0x400) != 0 )
        {
          v86 = *(_QWORD *)(a1 - 48);
          v87 = &qword_1802EB518;
          v88 = &qword_1802EB518;
          v89 = *(_QWORD *)(a1 - 40);
          if ( *(_QWORD *)(v89 + 32) )
            v87 = *(const wchar_t **)(v89 + 32);
          if ( *(_QWORD *)(v86 + 120) )
            v88 = *(const wchar_t **)(v86 + 120);
          v90 = (*(__int64 (__fastcall **)(__int64, struct IDefinitionIdentity *, const wchar_t *, const wchar_t *))(*(_QWORD *)a2 + 64LL))(
                  a2,
                  v141,
                  v88,
                  v87);
          v8 = v90;
          if ( v90 < 0 )
          {
            LODWORD(v145) = v90;
            if ( LogAdapter::g_Logger )
            {
              v91 = *(_QWORD *)(a1 - 40);
              if ( *(_QWORD *)(v91 + 32) )
                v76 = *(const wchar_t **)(v91 + 32);
              *(_QWORD *)v139 = v76;
              LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                (__int64)LogAdapter::g_Logger,
                0,
                3,
                (__int64)"Failed to install manifest for Update: {}",
                (__int64)v139);
              *(_QWORD *)v140 = &v145;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (__int64)LogAdapter::g_Logger,
                1,
                3,
                (__int64)": {}",
                (__int64)v140);
            }
            v9 = 352;
            goto LABEL_15;
          }
        }
        else
        {
          v136 = 0;
          v82 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64), _QWORD, struct IDefinitionIdentity *, _QWORD))(*a3)[5])(
                  a3,
                  0,
                  v141,
                  0);
          v8 = v82;
          if ( v82 < 0 )
          {
            LODWORD(v145) = v82;
            if ( LogAdapter::g_Logger )
            {
              v83 = *(_QWORD *)(a1 - 40);
              if ( *(_QWORD *)(v83 + 32) )
                v76 = *(const wchar_t **)(v83 + 32);
              *(_QWORD *)v139 = v76;
              LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                (__int64)LogAdapter::g_Logger,
                0,
                3,
                (__int64)"Failed to begin deployment uninstallation for Update: {}",
                (__int64)v139);
              *(_QWORD *)v140 = &v145;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (__int64)LogAdapter::g_Logger,
                1,
                3,
                (__int64)": {}",
                (__int64)v140);
            }
            v9 = 358;
            goto LABEL_15;
          }
          v136 = 0;
          v84 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct IDefinitionIdentity *, _QWORD))(*(_QWORD *)v146 + 72LL))(
                  v146,
                  0,
                  v141,
                  0);
          v8 = v84;
          if ( v84 < 0 )
          {
            LODWORD(v145) = v84;
            if ( LogAdapter::g_Logger )
            {
              v85 = *(_QWORD *)(a1 - 40);
              if ( *(_QWORD *)(v85 + 32) )
                v76 = *(const wchar_t **)(v85 + 32);
              *(_QWORD *)v139 = v76;
              LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                (__int64)LogAdapter::g_Logger,
                0,
                3,
                (__int64)"Failed to MarkDeploymentUntaged while staging Update: {}",
                (__int64)v139);
              *(_QWORD *)v140 = &v145;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (__int64)LogAdapter::g_Logger,
                1,
                3,
                (__int64)": {}",
                (__int64)v140);
            }
            v9 = 362;
            goto LABEL_15;
          }
        }
        v92 = ComponentAnalyzerChangeDeployment(
                *(struct CCbsSession **)(a1 - 32),
                *(_QWORD *)(a1 - 40) + 376LL,
                4,
                *(_QWORD *)(a1 - 16) != 0);
        v8 = v92;
        if ( v92 < 0 )
        {
          LODWORD(v145) = v92;
          if ( LogAdapter::g_Logger )
          {
            v93 = *(_QWORD *)(a1 - 40);
            if ( *(_QWORD *)(v93 + 32) )
              v76 = *(const wchar_t **)(v93 + 32);
            *(_QWORD *)v139 = v76;
            LogAdapter::Logger::LogNumObjects<wchar_t const *>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (__int64)"ComponentAnalyzerUninstallDeployment: Failed on update: {}",
              (__int64)v139);
            *(_QWORD *)v140 = &v145;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {}",
              (__int64)v140);
          }
          v9 = 368;
          goto LABEL_15;
        }
        if ( *(_QWORD *)(a1 - 16) )
        {
          v136 = 1;
          v94 = DoqAddDriverOperation(*(_QWORD *)(a1 - 32), *(_QWORD *)(a1 - 48), *(_QWORD *)(a1 - 40));
          v8 = v94;
          if ( v94 < 0 )
          {
            LODWORD(v145) = v94;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                (__int64)LogAdapter::g_Logger,
                0,
                3,
                (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed adding unproject component operation");
              *(_QWORD *)v139 = &v145;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (__int64)LogAdapter::g_Logger,
                1,
                3,
                (__int64)": {}",
                (__int64)v139);
            }
            v9 = 374;
            goto LABEL_15;
          }
        }
        break;
      case 6:
        *(_QWORD *)v139 = GetFastIdentityString(v141);
        v45 = &qword_1802EB518;
        v46 = *(_QWORD *)(a1 - 40);
        v47 = &qword_1802EB518;
        if ( *(_QWORD *)(v46 + 32) )
          v47 = *(const wchar_t **)(v46 + 32);
        v48 = *(_QWORD *)(a1 - 48);
        *(_QWORD *)v140 = v47;
        v49 = (wchar_t *)&qword_1802EB518;
        if ( *(_QWORD *)(v48 + 120) )
          v49 = *(wchar_t **)(v48 + 120);
        v145 = v49;
        if ( LogAdapter::g_Logger )
        {
          LOBYTE(v44) = 1;
          LogAdapter::Logger::LogNumObjects<wchar_t const *,AutoScz,wchar_t *>(
            (_DWORD)LogAdapter::g_Logger,
            v44,
            1,
            (unsigned int)"Exec: Unprojecting Package: {}, Update: {}, UninstallDeployment: {}",
            (__int64)&v145,
            (__int64)v140,
            (__int64)v139);
        }
        v50 = *(_DWORD *)(*(_QWORD *)(a1 - 32) + 692LL);
        if ( (v50 & 0x80000) != 0 || (v50 & 0x400) != 0 )
        {
          v64 = *(_QWORD *)(a1 - 48);
          v65 = &qword_1802EB518;
          v66 = &qword_1802EB518;
          v67 = *(_QWORD *)(a1 - 40);
          if ( *(_QWORD *)(v67 + 32) )
            v65 = *(const wchar_t **)(v67 + 32);
          if ( *(_QWORD *)(v64 + 120) )
            v66 = *(const wchar_t **)(v64 + 120);
          v68 = (*(__int64 (__fastcall **)(__int64, struct IDefinitionIdentity *, const wchar_t *, const wchar_t *))(*(_QWORD *)a2 + 64LL))(
                  a2,
                  v141,
                  v66,
                  v65);
          v8 = v68;
          if ( v68 < 0 )
          {
            LODWORD(v145) = v68;
            if ( LogAdapter::g_Logger )
            {
              v69 = *(_QWORD *)(a1 - 40);
              if ( *(_QWORD *)(v69 + 32) )
                v45 = *(const wchar_t **)(v69 + 32);
              *(_QWORD *)v139 = v45;
              LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                (__int64)LogAdapter::g_Logger,
                0,
                3,
                (__int64)"Failed to install manifest for Update: {}",
                (__int64)v139);
              *(_QWORD *)v140 = &v145;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (__int64)LogAdapter::g_Logger,
                1,
                3,
                (__int64)": {}",
                (__int64)v140);
            }
            v9 = 395;
            goto LABEL_15;
          }
          v70 = ComponentAnalyzerChangeDeployment(
                  *(struct CCbsSession **)(a1 - 32),
                  *(_QWORD *)(a1 - 40) + 376LL,
                  4,
                  *(_QWORD *)(a1 - 16) != 0);
          v8 = v70;
          if ( v70 < 0 )
          {
            LODWORD(v145) = v70;
            if ( LogAdapter::g_Logger )
            {
              v71 = *(_QWORD *)(a1 - 40);
              if ( *(_QWORD *)(v71 + 32) )
                v45 = *(const wchar_t **)(v71 + 32);
              *(_QWORD *)v139 = v45;
              LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                (__int64)LogAdapter::g_Logger,
                0,
                3,
                (__int64)"ComponentAnalyzerUninstallDeployment: Failed on update: {}",
                (__int64)v139);
              *(_QWORD *)v140 = &v145;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (__int64)LogAdapter::g_Logger,
                1,
                3,
                (__int64)": {}",
                (__int64)v140);
            }
            v9 = 400;
            goto LABEL_15;
          }
        }
        else
        {
          v136 = 0;
          v51 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64), _QWORD, struct IDefinitionIdentity *, _QWORD))(*a3)[5])(
                  a3,
                  0,
                  v141,
                  0);
          v8 = v51;
          if ( v51 < 0 )
          {
            LODWORD(v145) = v51;
            if ( LogAdapter::g_Logger )
            {
              v52 = *(_QWORD *)(a1 - 40);
              if ( *(_QWORD *)(v52 + 32) )
                v45 = *(const wchar_t **)(v52 + 32);
              *(_QWORD *)v139 = v45;
              LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                (__int64)LogAdapter::g_Logger,
                0,
                3,
                (__int64)"Failed to begin deployment uninstallation for Update: {}",
                (__int64)v139);
              *(_QWORD *)v140 = &v145;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (__int64)LogAdapter::g_Logger,
                1,
                3,
                (__int64)": {}",
                (__int64)v140);
            }
            v9 = 406;
            goto LABEL_15;
          }
          v53 = ComponentAnalyzerChangeDeployment(
                  *(struct CCbsSession **)(a1 - 32),
                  *(_QWORD *)(a1 - 40) + 376LL,
                  4,
                  *(_QWORD *)(a1 - 16) != 0);
          v8 = v53;
          if ( v53 < 0 )
          {
            LODWORD(v145) = v53;
            if ( LogAdapter::g_Logger )
            {
              v54 = *(_QWORD *)(a1 - 40);
              if ( *(_QWORD *)(v54 + 32) )
                v45 = *(const wchar_t **)(v54 + 32);
              *(_QWORD *)v139 = v45;
              LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                (__int64)LogAdapter::g_Logger,
                0,
                3,
                (__int64)"ComponentAnalyzerUninstallDeployment: Failed on update: {}",
                (__int64)v139);
              *(_QWORD *)v140 = &v145;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (__int64)LogAdapter::g_Logger,
                1,
                3,
                (__int64)": {}",
                (__int64)v140);
            }
            v9 = 411;
            goto LABEL_15;
          }
          *(_QWORD *)v139 = GetFastIdentityString(v141);
          v56 = &qword_1802EB518;
          v57 = *(_QWORD *)(a1 - 40);
          if ( *(_QWORD *)(v57 + 32) )
            v56 = *(const wchar_t **)(v57 + 32);
          v58 = *(_QWORD *)(a1 - 48);
          *(_QWORD *)v140 = v56;
          v59 = (wchar_t *)&qword_1802EB518;
          if ( *(_QWORD *)(v58 + 120) )
            v59 = *(wchar_t **)(v58 + 120);
          v145 = v59;
          if ( LogAdapter::g_Logger )
          {
            LOBYTE(v55) = 1;
            LogAdapter::Logger::LogNumObjects<wchar_t const *,AutoScz,wchar_t *>(
              (_DWORD)LogAdapter::g_Logger,
              v55,
              1,
              (unsigned int)"Exec: Unpinning Package: {}, Update: {}, UnpinDeployment: {}",
              (__int64)&v145,
              (__int64)v140,
              (__int64)v139);
          }
          v136 = 0;
          v60 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct IDefinitionIdentity *, _QWORD))(*(_QWORD *)v146 + 72LL))(
                  v146,
                  0,
                  v141,
                  0);
          v8 = v60;
          if ( v60 < 0 )
          {
            LODWORD(v145) = v60;
            if ( LogAdapter::g_Logger )
            {
              v61 = *(_QWORD *)(a1 - 40);
              if ( *(_QWORD *)(v61 + 32) )
                v45 = *(const wchar_t **)(v61 + 32);
              *(_QWORD *)v139 = v45;
              LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                (__int64)LogAdapter::g_Logger,
                0,
                3,
                (__int64)"Failed to MarkDeploymentUntaged while staging Update: {}",
                (__int64)v139);
              *(_QWORD *)v140 = &v145;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (__int64)LogAdapter::g_Logger,
                1,
                3,
                (__int64)": {}",
                (__int64)v140);
            }
            v9 = 418;
            goto LABEL_15;
          }
          v136 = 0;
          v62 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64), _QWORD, struct IDefinitionIdentity *, _QWORD))(*a3)[6])(
                  a3,
                  0,
                  v141,
                  0);
          v8 = v62;
          if ( v62 < 0 )
          {
            LODWORD(v145) = v62;
            if ( LogAdapter::g_Logger )
            {
              v63 = *(_QWORD *)(a1 - 40);
              if ( *(_QWORD *)(v63 + 32) )
                v45 = *(const wchar_t **)(v63 + 32);
              *(_QWORD *)v139 = v45;
              LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                (__int64)LogAdapter::g_Logger,
                0,
                3,
                (__int64)"Failed to unpin deployment after uninstall for Update '{}'",
                (__int64)v139);
              *(_QWORD *)v140 = &v145;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (__int64)LogAdapter::g_Logger,
                1,
                3,
                (__int64)": {}",
                (__int64)v140);
            }
            v9 = 422;
            goto LABEL_15;
          }
        }
        v72 = ComponentAnalyzerChangeDeployment(
                *(struct CCbsSession **)(a1 - 32),
                *(_QWORD *)(a1 - 40) + 376LL,
                2,
                *(_QWORD *)(a1 - 16) != 0);
        v8 = v72;
        if ( v72 < 0 )
        {
          LODWORD(v145) = v72;
          if ( LogAdapter::g_Logger )
          {
            v73 = *(_QWORD *)(a1 - 40);
            if ( *(_QWORD *)(v73 + 32) )
              v45 = *(const wchar_t **)(v73 + 32);
            *(_QWORD *)v139 = v45;
            LogAdapter::Logger::LogNumObjects<wchar_t const *>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (__int64)"ComponentAnalyzerUnPinDeployment: Failed on update: {}",
              (__int64)v139);
            *(_QWORD *)v140 = &v145;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {}",
              (__int64)v140);
          }
          v9 = 428;
          goto LABEL_15;
        }
        if ( *(_QWORD *)(a1 - 16) )
        {
          v136 = 1;
          v74 = DoqAddDriverOperation(*(_QWORD *)(a1 - 32), *(_QWORD *)(a1 - 48), *(_QWORD *)(a1 - 40));
          v8 = v74;
          if ( v74 < 0 )
          {
            LODWORD(v145) = v74;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                (__int64)LogAdapter::g_Logger,
                0,
                3,
                (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed adding uninstall component operation");
              *(_QWORD *)v139 = &v145;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (__int64)LogAdapter::g_Logger,
                1,
                3,
                (__int64)": {}",
                (__int64)v139);
            }
            v9 = 434;
            goto LABEL_15;
          }
        }
        break;
      case 7:
        *(_QWORD *)v139 = GetFastIdentityString(v141);
        v37 = &qword_1802EB518;
        v38 = *(_QWORD *)(a1 - 40);
        v39 = &qword_1802EB518;
        if ( *(_QWORD *)(v38 + 32) )
          v39 = *(const wchar_t **)(v38 + 32);
        v40 = *(_QWORD *)(a1 - 48);
        *(_QWORD *)v140 = v39;
        v41 = (wchar_t *)&qword_1802EB518;
        if ( *(_QWORD *)(v40 + 120) )
          v41 = *(wchar_t **)(v40 + 120);
        v145 = v41;
        if ( LogAdapter::g_Logger )
        {
          LOBYTE(v36) = 1;
          LogAdapter::Logger::LogNumObjects<wchar_t const *,AutoScz,wchar_t *>(
            (_DWORD)LogAdapter::g_Logger,
            v36,
            1,
            (unsigned int)"Exec: Unmarking Package: {}, Update: {}, UnstageDeployment: {}",
            (__int64)&v145,
            (__int64)v140,
            (__int64)v139);
        }
        v136 = 0;
        v42 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct IDefinitionIdentity *, _QWORD))(*(_QWORD *)v146 + 72LL))(
                v146,
                0,
                v141,
                0);
        v8 = v42;
        if ( v42 < 0 )
        {
          LODWORD(v145) = v42;
          if ( LogAdapter::g_Logger )
          {
            v43 = *(_QWORD *)(a1 - 40);
            if ( *(_QWORD *)(v43 + 32) )
              v37 = *(const wchar_t **)(v43 + 32);
            *(_QWORD *)v139 = v37;
            LogAdapter::Logger::LogNumObjects<wchar_t const *>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (__int64)"Failed to MarkDeploymentUntaged while staging Update: {}",
              (__int64)v139);
            *(_QWORD *)v140 = &v145;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {}",
              (__int64)v140);
          }
          v9 = 384;
          goto LABEL_15;
        }
        break;
      case 8:
        *(_QWORD *)v139 = GetFastIdentityString(v141);
        v25 = &qword_1802EB518;
        v26 = *(_QWORD *)(a1 - 40);
        v27 = &qword_1802EB518;
        if ( *(_QWORD *)(v26 + 32) )
          v27 = *(const wchar_t **)(v26 + 32);
        v28 = *(_QWORD *)(a1 - 48);
        *(_QWORD *)v140 = v27;
        v29 = (wchar_t *)&qword_1802EB518;
        if ( *(_QWORD *)(v28 + 120) )
          v29 = *(wchar_t **)(v28 + 120);
        v145 = v29;
        if ( LogAdapter::g_Logger )
        {
          LOBYTE(v24) = 1;
          LogAdapter::Logger::LogNumObjects<wchar_t const *,AutoScz,wchar_t *>(
            (_DWORD)LogAdapter::g_Logger,
            v24,
            1,
            (unsigned int)"Exec: Unstaging Package: {}, Update: {}, UnstageDeployment/UnpinDeployment: {}",
            (__int64)&v145,
            (__int64)v140,
            (__int64)v139);
        }
        v136 = 0;
        v30 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64), _QWORD, struct IDefinitionIdentity *, _QWORD))(*a3)[6])(
                a3,
                0,
                v141,
                0);
        v8 = v30;
        if ( v30 < 0 )
        {
          LODWORD(v145) = v30;
          if ( LogAdapter::g_Logger )
          {
            v31 = *(_QWORD *)(a1 - 40);
            if ( *(_QWORD *)(v31 + 32) )
              v25 = *(const wchar_t **)(v31 + 32);
            *(_QWORD *)v139 = v25;
            LogAdapter::Logger::LogNumObjects<wchar_t const *>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (__int64)"Failed to unpin deployment for Update '{}'",
              (__int64)v139);
            *(_QWORD *)v140 = &v145;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {}",
              (__int64)v140);
          }
          v9 = 288;
          goto LABEL_15;
        }
        v136 = 0;
        v32 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct IDefinitionIdentity *, _QWORD))(*(_QWORD *)v146 + 72LL))(
                v146,
                0,
                v141,
                0);
        v8 = v32;
        if ( v32 < 0 )
        {
          LODWORD(v145) = v32;
          if ( LogAdapter::g_Logger )
          {
            v33 = *(_QWORD *)(a1 - 40);
            if ( *(_QWORD *)(v33 + 32) )
              v25 = *(const wchar_t **)(v33 + 32);
            *(_QWORD *)v139 = v25;
            LogAdapter::Logger::LogNumObjects<wchar_t const *>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (__int64)"Failed to MarkDeploymentUntaged while staging Update: {}",
              (__int64)v139);
            *(_QWORD *)v140 = &v145;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {}",
              (__int64)v140);
          }
          v9 = 292;
          goto LABEL_15;
        }
        v34 = ComponentAnalyzerChangeDeployment(
                *(struct CCbsSession **)(a1 - 32),
                *(_QWORD *)(a1 - 40) + 376LL,
                2,
                *(_QWORD *)(a1 - 16) != 0);
        v8 = v34;
        if ( v34 < 0 )
        {
          LODWORD(v145) = v34;
          if ( LogAdapter::g_Logger )
          {
            v35 = *(_QWORD *)(a1 - 40);
            if ( *(_QWORD *)(v35 + 32) )
              v25 = *(const wchar_t **)(v35 + 32);
            *(_QWORD *)v139 = v25;
            LogAdapter::Logger::LogNumObjects<wchar_t const *>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (__int64)"ComponentAnalyzerUnPinDeployment: Failed on update: {}",
              (__int64)v139);
            *(_QWORD *)v140 = &v145;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {}",
              (__int64)v140);
          }
          v9 = 297;
          goto LABEL_15;
        }
        break;
      case 9:
        *(_QWORD *)v140 = GetFastIdentityString(v141);
        v15 = &qword_1802EB518;
        v16 = *(_QWORD *)(a1 - 40);
        v17 = (wchar_t *)&qword_1802EB518;
        if ( *(_QWORD *)(v16 + 32) )
          v17 = *(wchar_t **)(v16 + 32);
        v18 = *(_QWORD *)(a1 - 48);
        v145 = v17;
        v19 = &qword_1802EB518;
        if ( *(_QWORD *)(v18 + 120) )
          v19 = *(const wchar_t **)(v18 + 120);
        *(_QWORD *)v139 = v19;
        if ( LogAdapter::g_Logger )
        {
          LOBYTE(v14) = 1;
          LogAdapter::Logger::LogNumObjects<wchar_t const *,AutoScz,wchar_t *>(
            (_DWORD)LogAdapter::g_Logger,
            v14,
            1,
            (unsigned int)"Exec: Unpinning Package: {}, Update: {}, UnpinDeployment: {}",
            (__int64)v139,
            (__int64)&v145,
            (__int64)v140);
        }
        v136 = 0;
        v20 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64), _QWORD, struct IDefinitionIdentity *, _QWORD))(*a3)[6])(
                a3,
                0,
                v141,
                0);
        v8 = v20;
        if ( v20 < 0 )
        {
          LODWORD(v145) = v20;
          if ( LogAdapter::g_Logger )
          {
            v21 = *(_QWORD *)(a1 - 40);
            if ( *(_QWORD *)(v21 + 32) )
              v15 = *(const wchar_t **)(v21 + 32);
            *(_QWORD *)v139 = v15;
            LogAdapter::Logger::LogNumObjects<wchar_t const *>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (__int64)"Failed to unpin deployment for Update '{}'",
              (__int64)v139);
            *(_QWORD *)v140 = &v145;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {}",
              (__int64)v140);
          }
          v9 = 306;
          goto LABEL_15;
        }
        v22 = ComponentAnalyzerChangeDeployment(
                *(struct CCbsSession **)(a1 - 32),
                *(_QWORD *)(a1 - 40) + 376LL,
                2,
                *(_QWORD *)(a1 - 16) != 0);
        v8 = v22;
        if ( v22 < 0 )
        {
          LODWORD(v145) = v22;
          if ( LogAdapter::g_Logger )
          {
            v23 = *(_QWORD *)(a1 - 40);
            if ( *(_QWORD *)(v23 + 32) )
              v15 = *(const wchar_t **)(v23 + 32);
            *(_QWORD *)v139 = v15;
            LogAdapter::Logger::LogNumObjects<wchar_t const *>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (__int64)"ComponentAnalyzerUnPinDeployment: Failed on update: {}",
              (__int64)v139);
            *(_QWORD *)v140 = &v145;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {}",
              (__int64)v140);
          }
          v9 = 311;
          goto LABEL_15;
        }
        break;
    }
LABEL_268:
    AutoCsiStoreLock::~AutoCsiStoreLock((AutoCsiStoreLock *)v138);
    MonitoredCritSecLocker::~MonitoredCritSecLocker((MonitoredCritSecLocker *)v143);
    if ( v146 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v146 + 16LL))(v146);
      v146 = 0;
    }
    v8 = 0;
    goto LABEL_271;
  }
  *(_QWORD *)v139 = GetFastIdentityString(v141);
  v114 = &qword_1802EB518;
  v115 = *(_QWORD *)(a1 - 40);
  v116 = &qword_1802EB518;
  if ( *(_QWORD *)(v115 + 32) )
    v116 = *(const wchar_t **)(v115 + 32);
  v117 = *(_QWORD *)(a1 - 48);
  *(_QWORD *)v140 = v116;
  v118 = &qword_1802EB518;
  if ( *(_QWORD *)(v117 + 120) )
    v118 = *(const wchar_t **)(v117 + 120);
  v142 = (wchar_t **)v118;
  if ( LogAdapter::g_Logger )
  {
    LOBYTE(v113) = 1;
    LogAdapter::Logger::LogNumObjects<wchar_t const *,AutoScz,wchar_t *>(
      (_DWORD)LogAdapter::g_Logger,
      v113,
      1,
      (unsigned int)"Exec: Installing Package: {}, Update: {}, InstallDeployment: {}",
      (__int64)&v142,
      (__int64)v140,
      (__int64)v139);
  }
  v119 = *(struct CCbsSession **)(a1 - 32);
  v120 = *((_DWORD *)v119 + 173);
  if ( (v120 & 0x80000) != 0 || (v120 & 0x400) != 0 )
  {
    v126 = *(_QWORD *)(a1 - 48);
    v127 = &qword_1802EB518;
    v128 = &qword_1802EB518;
    v129 = *(_QWORD *)(a1 - 40);
    if ( *(_QWORD *)(v129 + 32) )
      v127 = *(const wchar_t **)(v129 + 32);
    if ( *(_QWORD *)(v126 + 120) )
      v128 = *(const wchar_t **)(v126 + 120);
    v130 = (*(__int64 (__fastcall **)(__int64, struct IDefinitionIdentity *, const wchar_t *, const wchar_t *))(*(_QWORD *)a2 + 56LL))(
             a2,
             v141,
             v128,
             v127);
    v8 = v130;
    if ( v130 < 0 )
    {
      LODWORD(v145) = v130;
      if ( LogAdapter::g_Logger )
      {
        v131 = *(_QWORD *)(a1 - 40);
        if ( *(_QWORD *)(v131 + 32) )
          v114 = *(const wchar_t **)(v131 + 32);
        v142 = (wchar_t **)v114;
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (__int64)"Failed to install manifest for Update: {}",
          (__int64)&v142);
        *(_QWORD *)v139 = &v145;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v139);
      }
      v9 = 449;
      goto LABEL_15;
    }
  }
  else
  {
    StoredCatalogPath = CCbsPackage::GetStoredCatalogPath(*(CCbsPackage **)(*(_QWORD *)(a1 - 40) + 24LL), v119, &v145);
    v8 = StoredCatalogPath;
    if ( StoredCatalogPath < 0 )
    {
      LODWORD(v145) = StoredCatalogPath;
      if ( LogAdapter::g_Logger )
      {
        v122 = *(_QWORD *)(*(_QWORD *)(a1 - 40) + 24LL);
        if ( *(_QWORD *)(v122 + 120) )
          v114 = *(const wchar_t **)(v122 + 120);
        v142 = (wchar_t **)v114;
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (__int64)"Failed to get stored catalog path for package: {}",
          (__int64)&v142);
        *(_QWORD *)v139 = &v145;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v139);
      }
      v9 = 455;
      goto LABEL_15;
    }
    v136 = 0;
    v8 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64), _QWORD, struct IDefinitionIdentity *, _QWORD))(*a3)[3])(
           a3,
           0,
           v141,
           0);
    if ( (v8 & 0x80000000) != 0 )
    {
      if ( !(unsigned int)CCbsSession::IsOffline(*(CCbsSession **)(a1 - 32)) )
      {
        v124 = VerifyCatalogAndManifest(v123, v145);
        if ( v124 < 0 )
        {
          LogAdapter::TraceAtLevelIfFailed<long,>(
            1,
            (unsigned int)v124,
            "Unable to verify manifest against catalog, mark store as corrupt.");
          CCbsSession::MarkPackageStoreCorrupt(*(CCbsSession **)(a1 - 32));
        }
      }
      LODWORD(v145) = v8;
      if ( LogAdapter::g_Logger )
      {
        v125 = *(_QWORD *)(a1 - 40);
        if ( *(_QWORD *)(v125 + 32) )
          v114 = *(const wchar_t **)(v125 + 32);
        v142 = (wchar_t **)v114;
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (__int64)"Failed to begin deployment installation for Update: {}",
          (__int64)&v142);
        *(_QWORD *)v139 = &v145;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v139);
      }
      v9 = 486;
      goto LABEL_15;
    }
  }
  v132 = ComponentAnalyzerChangeDeployment(
           *(struct CCbsSession **)(a1 - 32),
           *(_QWORD *)(a1 - 40) + 376LL,
           3,
           *(_QWORD *)(a1 - 16) != 0);
  v8 = v132;
  if ( v132 >= 0 )
  {
    if ( *(_QWORD *)(a1 - 16) )
    {
      v136 = 0;
      v134 = DoqAddDriverOperation(*(_QWORD *)(a1 - 32), *(_QWORD *)(a1 - 48), *(_QWORD *)(a1 - 40));
      v8 = v134;
      if ( v134 < 0 )
      {
        LODWORD(v145) = v134;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed adding install component operation");
          v142 = &v145;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)&v142);
        }
        v9 = 499;
        goto LABEL_15;
      }
    }
    goto LABEL_268;
  }
  LODWORD(v145) = v132;
  if ( LogAdapter::g_Logger )
  {
    v133 = *(_QWORD *)(a1 - 40);
    if ( *(_QWORD *)(v133 + 32) )
      v114 = *(const wchar_t **)(v133 + 32);
    v142 = (wchar_t **)v114;
    LogAdapter::Logger::LogNumObjects<wchar_t const *>(
      (__int64)LogAdapter::g_Logger,
      0,
      3,
      (__int64)"ComponentAnalyzerInstallDeployment: Failed on update: {}",
      (__int64)&v142);
    *(_QWORD *)v139 = &v145;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (__int64)LogAdapter::g_Logger,
      1,
      3,
      (__int64)": {}",
      (__int64)v139);
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1ED,
    (unsigned int)"onecore\\base\\cbs\\core\\cbsexecutioncomponent.cpp",
    (const char *)v8,
    v137);
  if ( vpfnTiUnlockProcess )
    vpfnTiUnlockProcess();
  MonitoredCritSecLocker::~MonitoredCritSecLocker((MonitoredCritSecLocker *)v143);
  if ( v146 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v146 + 16LL))(v146);
    v146 = 0;
  }
  if ( v141 )
    (*(void (__fastcall **)(struct IDefinitionIdentity *))(*(_QWORD *)v141 + 16LL))(v141);
  return v8;
}

```

## disassembly

```asm
0x180046754  mov     [rsp-8+arg_18], rbx
0x180046759  push    rbp
0x18004675a  push    rsi
0x18004675b  push    rdi
0x18004675c  push    r12
0x18004675e  push    r13
0x180046760  push    r14
0x180046762  push    r15
0x180046764  lea     rbp, [rsp-1Fh]
0x180046769  sub     rsp, 0C0h
0x180046770  mov     rax, cs:__security_cookie
0x180046777  xor     rax, rsp
0x18004677a  mov     [rbp+4Fh+var_38], rax
0x18004677e  xor     r13d, r13d
0x180046781  lea     rax, ?vComponentAnalyzerLock@@3UMonitoredCritSec@@A; MonitoredCritSec vComponentAnalyzerLock
0x180046788  mov     [rbp+4Fh+var_60], rax
0x18004678c  mov     rdi, rcx
0x18004678f  lea     rax, ??_7PackageTrackerLocker@@6B@; const PackageTrackerLocker::`vftable'
0x180046796  mov     [rbp+4Fh+var_78], r13
0x18004679a  lea     rcx, [rbp+4Fh+var_68]; this
0x18004679e  mov     [rbp+4Fh+var_68], rax
0x1800467a2  mov     r15, r8
0x1800467a5  mov     [rbp+4Fh+var_48], r13
0x1800467a9  mov     r12, rdx
0x1800467ac  mov     [rbp+4Fh+var_40], r13d
0x1800467b0  mov     [rbp+4Fh+var_50], r13
0x1800467b4  mov     [rbp+4Fh+var_58], r13b
0x1800467b8  call    ?Lock@MonitoredCritSecLocker@@UEAAXXZ; MonitoredCritSecLocker::Lock(void)
0x1800467bd  mov     rax, cs:?vpfnTiLockProcess@@3P6AHH@ZEA; int (*vpfnTiLockProcess)(int)
0x1800467c4  mov     [rbp+4Fh+var_90], 1
0x1800467c8  test    rax, rax
0x1800467cb  jz      short loc_1800467D4
0x1800467cd  xor     ecx, ecx
0x1800467cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800467d4  test    r15, r15
0x1800467d7  jnz     short loc_180046835
0x1800467d9  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800467e0  mov     ebx, 80070057h
0x1800467e5  mov     dword ptr [rbp+4Fh+var_50], ebx
0x1800467e8  test    rcx, rcx
0x1800467eb  jz      short loc_18004682B
0x1800467ed  lea     r14d, [r15+3]
0x1800467f1  xor     edx, edx
0x1800467f3  mov     r8d, r14d
0x1800467f6  lea     r9, aNoTransactionS_0; "No transaction specified"
0x1800467fd  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180046802  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180046809  lea     rax, [rbp+4Fh+var_50]
0x18004680d  mov     qword ptr [rbp+4Fh+var_80], rax
0x180046811  lea     r9, asc_1802EE7AC; ": {}"
0x180046818  lea     rax, [rbp+4Fh+var_80]
0x18004681c  mov     r8d, r14d
0x18004681f  mov     dl, 1
0x180046821  mov     qword ptr [rsp+0F0h+var_D0], rax
0x180046826  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18004682b  mov     edx, 107h
0x180046830  jmp     loc_18004691A
0x180046835  mov     esi, [rbp+4Fh+arg_20]
0x180046838  test    esi, esi
0x18004683a  jnz     short loc_180046898
0x18004683c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180046843  mov     ebx, 80070057h
0x180046848  mov     dword ptr [rbp+4Fh+var_50], ebx
0x18004684b  test    rcx, rcx
0x18004684e  jz      short loc_18004688E
0x180046850  lea     r14d, [rsi+3]
0x180046854  xor     edx, edx
0x180046856  mov     r8d, r14d
0x180046859  lea     r9, aItemActionForC; "Item action for Component Executions sh"...
0x180046860  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180046865  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004686c  lea     rax, [rbp+4Fh+var_50]
0x180046870  mov     qword ptr [rbp+4Fh+var_80], rax
0x180046874  lea     r9, asc_1802EE7AC; ": {}"
0x18004687b  lea     rax, [rbp+4Fh+var_80]
0x18004687f  mov     r8d, r14d
0x180046882  mov     dl, 1
0x180046884  mov     qword ptr [rsp+0F0h+var_D0], rax
0x180046889  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18004688e  mov     edx, 109h
0x180046893  jmp     loc_18004691A
0x180046898  mov     rax, [r15]
0x18004689b  lea     rcx, [rbp+4Fh+var_48]
0x18004689f  mov     rbx, [rax]
0x1800468a2  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseBcdStore@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&CloseBcdStore(void *)>>::GetInitPointer(void)
0x1800468a7  mov     r8, rax
0x1800468aa  lea     rdx, _GUID_0e695bd1_628c_40a1_88cf_925083986d16
0x1800468b1  mov     rax, rbx
0x1800468b4  mov     rcx, r15
0x1800468b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800468bc  mov     ebx, eax
0x1800468be  test    eax, eax
0x1800468c0  jns     loc_180046961
0x1800468c6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800468cd  mov     dword ptr [rbp+4Fh+var_50], eax
0x1800468d0  test    rcx, rcx
0x1800468d3  jz      short loc_180046915
0x1800468d5  mov     r14d, 3
0x1800468db  lea     r9, aCouldNotAcquir; "Could not acquire an ICSITransaction2 f"...
0x1800468e2  mov     r8d, r14d
0x1800468e5  xor     edx, edx
0x1800468e7  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800468ec  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800468f3  lea     rax, [rbp+4Fh+var_50]
0x1800468f7  mov     qword ptr [rbp+4Fh+var_80], rax
0x1800468fb  lea     r9, asc_1802EE7AC; ": {}"
0x180046902  lea     rax, [rbp+4Fh+var_80]
0x180046906  mov     r8d, r14d
0x180046909  mov     dl, 1
0x18004690b  mov     qword ptr [rsp+0F0h+var_D0], rax; int
0x180046910  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180046915  mov     edx, 10Dh; void *
0x18004691a  mov     rcx, [rbp+57h]; this
0x18004691e  lea     r8, aOnecoreBaseCbs_139; "onecore\\base\\cbs\\core\\cbsexecutionc"...
0x180046925  mov     r9d, ebx; char *
0x180046928  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004692d  lea     rcx, [rbp+4Fh+var_90]; this
0x180046931  call    ??1AutoCsiStoreLock@@QEAA@XZ; AutoCsiStoreLock::~AutoCsiStoreLock(void)
0x180046936  lea     rcx, [rbp+4Fh+var_68]; this
0x18004693a  call    ??1MonitoredCritSecLocker@@UEAA@XZ; MonitoredCritSecLocker::~MonitoredCritSecLocker(void)
0x18004693f  mov     rcx, [rbp+4Fh+var_48]
0x180046943  test    rcx, rcx
0x180046946  jz      loc_1800480DD
0x18004694c  mov     rax, [rcx]
0x18004694f  mov     rax, [rax+10h]
0x180046953  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046958  mov     [rbp+4Fh+var_48], r13
0x18004695c  jmp     loc_1800480DD
0x180046961  lea     rcx, [rbp+4Fh+var_78]
0x180046965  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseBcdStore@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&CloseBcdStore(void *)>>::GetInitPointer(void)
0x18004696a  lea     rcx, [rdi-48h]; this
0x18004696e  mov     rdx, rax; struct IDefinitionIdentity **
0x180046971  call    ?GetIdentity@CCbsExecutionComponent@@QEAAXPEAPEAUIDefinitionIdentity@@@Z; CCbsExecutionComponent::GetIdentity(IDefinitionIdentity * *)
0x180046976  mov     r14d, 3
0x18004697c  sub     esi, r14d
0x18004697f  jz      loc_180047C55
0x180046985  sub     esi, 1
0x180046988  jz      loc_180047938
0x18004698e  sub     esi, 1
0x180046991  jz      loc_180047571
0x180046997  sub     esi, 1
0x18004699a  jz      loc_180046F33
0x1800469a0  sub     esi, 1
0x1800469a3  jz      loc_180046E0A
0x1800469a9  sub     esi, 1
0x1800469ac  jz      loc_180046B8B
0x1800469b2  cmp     esi, 1
0x1800469b5  jnz     loc_1800480AF
0x1800469bb  mov     rcx, [rbp+4Fh+var_78]; struct IDefinitionIdentity *
0x1800469bf  call    ?GetFastIdentityString@@YAPEA_WPEAUIDefinitionIdentity@@@Z; GetFastIdentityString(IDefinitionIdentity *)
0x1800469c4  mov     qword ptr [rbp+4Fh+var_80], rax
0x1800469c8  lea     rsi, qword_1802EB518
0x1800469cf  mov     rax, [rdi-28h]
0x1800469d3  mov     rcx, rsi
0x1800469d6  cmp     [rax+20h], r13
0x1800469da  cmovnz  rcx, [rax+20h]
0x1800469df  mov     rax, [rdi-30h]
0x1800469e3  mov     [rbp+4Fh+var_50], rcx
0x1800469e7  mov     rcx, rsi
0x1800469ea  cmp     [rax+78h], r13
0x1800469ee  cmovnz  rcx, [rax+78h]
0x1800469f3  mov     qword ptr [rbp+4Fh+var_88], rcx
0x1800469f7  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800469fe  test    rcx, rcx
0x180046a01  jz      short loc_180046A31
0x180046a03  lea     rax, [rbp+4Fh+var_80]
0x180046a07  mov     [rsp+0F0h+var_C0], rax
0x180046a0c  lea     r8d, [r14-2]
0x180046a10  lea     rax, [rbp+4Fh+var_50]
0x180046a14  mov     dl, r8b
0x180046a17  mov     [rsp+0F0h+var_C8], rax
0x180046a1c  lea     r9, aExecUnpinningP; "Exec: Unpinning Package: {}, Update: {}"...
0x180046a23  lea     rax, [rbp+4Fh+var_88]
0x180046a27  mov     qword ptr [rsp+0F0h+var_D0], rax
0x180046a2c  call    ??$LogNumObjects@PEB_WVAutoScz@@PEA_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_WAEBVAutoScz@@AEBQEA_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *,AutoScz,wchar_t *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &,AutoScz const &,wchar_t * const &)
0x180046a31  mov     rcx, [rdi-28h]
0x180046a35  lea     rdx, [rbp+4Fh+var_40]
0x180046a39  mov     rax, [r15]
0x180046a3c  xor     r9d, r9d
0x180046a3f  mov     r8, [rbp+4Fh+var_78]
0x180046a43  mov     [rsp+0F0h+var_C0], rdx
0x180046a48  xor     edx, edx
0x180046a4a  mov     rcx, [rcx+1C8h]
0x180046a51  mov     rax, [rax+30h]
0x180046a55  mov     [rsp+0F0h+var_C8], rcx
0x180046a5a  mov     rcx, r15
0x180046a5d  mov     qword ptr [rsp+0F0h+var_D0], r13
0x180046a62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046a67  mov     ebx, eax
0x180046a69  test    eax, eax
0x180046a6b  jns     short loc_180046ADA
0x180046a6d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180046a74  mov     dword ptr [rbp+4Fh+var_50], eax
0x180046a77  test    rcx, rcx
0x180046a7a  jz      short loc_180046AD0
0x180046a7c  mov     rax, [rdi-28h]
0x180046a80  lea     r9, aFailedToUnpinD; "Failed to unpin deployment for Update '"...
0x180046a87  mov     r8d, r14d
0x180046a8a  cmp     [rax+20h], r13
0x180046a8e  cmovnz  rsi, [rax+20h]
0x180046a93  lea     rax, [rbp+4Fh+var_88]
0x180046a97  xor     edx, edx
0x180046a99  mov     qword ptr [rsp+0F0h+var_D0], rax
0x180046a9e  mov     qword ptr [rbp+4Fh+var_88], rsi
0x180046aa2  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x180046aa7  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180046aae  lea     rax, [rbp+4Fh+var_50]
0x180046ab2  mov     qword ptr [rbp+4Fh+var_80], rax
0x180046ab6  lea     r9, asc_1802EE7AC; ": {}"
0x180046abd  lea     rax, [rbp+4Fh+var_80]
0x180046ac1  mov     r8d, r14d
0x180046ac4  mov     dl, 1
0x180046ac6  mov     qword ptr [rsp+0F0h+var_D0], rax
0x180046acb  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180046ad0  mov     edx, 132h
0x180046ad5  jmp     loc_18004691A
0x180046ada  mov     rdx, [rdi-28h]
0x180046ade  mov     eax, r13d
0x180046ae1  cmp     [rdi-10h], r13
0x180046ae5  mov     r9, [rbp+4Fh+var_78]
0x180046ae9  setnz   al
0x180046aec  lea     rcx, [rdx+178h]
0x180046af3  mov     dword ptr [rsp+0F0h+var_C0], eax
0x180046af7  mov     rdx, [rdx+1C8h]
0x180046afe  mov     dword ptr [rsp+0F0h+var_C8], 2
0x180046b06  mov     qword ptr [rsp+0F0h+var_D0], rcx
0x180046b0b  mov     rcx, [rdi-20h]
0x180046b0f  call    ComponentAnalyzerChangeDeployment
0x180046b14  mov     ebx, eax
0x180046b16  test    eax, eax
0x180046b18  jns     loc_1800480AF
0x180046b1e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180046b25  mov     dword ptr [rbp+4Fh+var_50], eax
0x180046b28  test    rcx, rcx
0x180046b2b  jz      short loc_180046B81
0x180046b2d  mov     rax, [rdi-28h]
0x180046b31  lea     r9, aComponentanaly; "ComponentAnalyzerUnPinDeployment: Faile"...
0x180046b38  mov     r8d, r14d
0x180046b3b  cmp     [rax+20h], r13
0x180046b3f  cmovnz  rsi, [rax+20h]
0x180046b44  lea     rax, [rbp+4Fh+var_88]
0x180046b48  xor     edx, edx
0x180046b4a  mov     qword ptr [rsp+0F0h+var_D0], rax
0x180046b4f  mov     qword ptr [rbp+4Fh+var_88], rsi
0x180046b53  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x180046b58  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180046b5f  lea     rax, [rbp+4Fh+var_50]
0x180046b63  mov     qword ptr [rbp+4Fh+var_80], rax
0x180046b67  lea     r9, asc_1802EE7AC; ": {}"
0x180046b6e  lea     rax, [rbp+4Fh+var_80]
0x180046b72  mov     r8d, r14d
0x180046b75  mov     dl, 1
0x180046b77  mov     qword ptr [rsp+0F0h+var_D0], rax
0x180046b7c  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180046b81  mov     edx, 137h
0x180046b86  jmp     loc_18004691A
0x180046b8b  mov     rcx, [rbp+4Fh+var_78]; struct IDefinitionIdentity *
0x180046b8f  call    ?GetFastIdentityString@@YAPEA_WPEAUIDefinitionIdentity@@@Z; GetFastIdentityString(IDefinitionIdentity *)
0x180046b94  mov     qword ptr [rbp+4Fh+var_88], rax
0x180046b98  lea     rsi, qword_1802EB518
0x180046b9f  mov     rax, [rdi-28h]
0x180046ba3  mov     rcx, rsi
0x180046ba6  cmp     [rax+20h], r13
0x180046baa  cmovnz  rcx, [rax+20h]
0x180046baf  mov     rax, [rdi-30h]
0x180046bb3  mov     qword ptr [rbp+4Fh+var_80], rcx
0x180046bb7  mov     rcx, rsi
0x180046bba  cmp     [rax+78h], r13
0x180046bbe  cmovnz  rcx, [rax+78h]
0x180046bc3  mov     [rbp+4Fh+var_50], rcx
0x180046bc7  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180046bce  test    rcx, rcx
0x180046bd1  jz      short loc_180046C03
0x180046bd3  lea     rax, [rbp+4Fh+var_88]
0x180046bd7  mov     r8d, 1
0x180046bdd  mov     [rsp+0F0h+var_C0], rax
0x180046be2  lea     r9, aExecUnstagingP; "Exec: Unstaging Package: {}, Update: {}"...
0x180046be9  lea     rax, [rbp+4Fh+var_80]
0x180046bed  mov     dl, r8b
0x180046bf0  mov     [rsp+0F0h+var_C8], rax
0x180046bf5  lea     rax, [rbp+4Fh+var_50]
0x180046bf9  mov     qword ptr [rsp+0F0h+var_D0], rax
0x180046bfe  call    ??$LogNumObjects@PEB_WVAutoScz@@PEA_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_WAEBVAutoScz@@AEBQEA_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *,AutoScz,wchar_t *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &,AutoScz const &,wchar_t * const &)
0x180046c03  mov     rcx, [rdi-28h]
0x180046c07  lea     rdx, [rbp+4Fh+var_40]
0x180046c0b  mov     rax, [r15]
0x180046c0e  xor     r9d, r9d
0x180046c11  mov     r8, [rbp+4Fh+var_78]
0x180046c15  mov     [rsp+0F0h+var_C0], rdx
0x180046c1a  xor     edx, edx
0x180046c1c  mov     rcx, [rcx+1C8h]
0x180046c23  mov     rax, [rax+30h]
0x180046c27  mov     [rsp+0F0h+var_C8], rcx
0x180046c2c  mov     rcx, r15
0x180046c2f  mov     qword ptr [rsp+0F0h+var_D0], r13
0x180046c34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046c39  mov     ebx, eax
0x180046c3b  test    eax, eax
0x180046c3d  jns     short loc_180046CAC
0x180046c3f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
  ... truncated ...
```
