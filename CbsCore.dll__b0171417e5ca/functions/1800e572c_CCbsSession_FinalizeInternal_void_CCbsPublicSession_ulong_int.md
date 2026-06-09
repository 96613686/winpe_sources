# CCbsSession::FinalizeInternal(void *,CCbsPublicSession *,ulong,int *)

- ea: `0x1800e572c`
- end: `0x1800e74f7`
- name: `?FinalizeInternal@CCbsSession@@AEAAJPEAXPEAVCCbsPublicSession@@KPEAH@Z`
- size: `7627`
- prototype: `__int64 __usercall@<rax>(CCbsSession *__hidden this@<rcx>, void *@<rdx>, struct CCbsPublicSession *@<r8>, unsigned int@<r9d>, int *)`
- caller_count: `1`
- callee_count: `65`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1801d99f8`

## callees

- `0x18000f090`
- `0x180010b60`
- `0x180010cc0`
- `0x180012fe4`
- `0x180013018`
- `0x1800132a4`
- `0x1800138b8`
- `0x180013c54`
- `0x1800194bc`
- `0x180023e74`
- `0x18002573c`
- `0x1800289f0`
- `0x180028e24`
- `0x18002a78c`
- `0x18002ac84`
- `0x18002f9a8`
- `0x180048fc0`
- `0x1800532d4`
- `0x18005e64c`
- `0x180098538`
- `0x180099390`
- `0x180099548`
- `0x18009cf78`
- `0x1800a8678`
- `0x1800ad504`
- `0x1800aea00`
- `0x1800b693c`
- `0x1800b7698`
- `0x1800b8e68`
- `0x1800b980c`
- `0x1800bce9c`
- `0x1800be2e0`
- `0x1800be684`
- `0x1800c03f0`
- `0x1800c12b4`
- `0x1800d5720`
- `0x1800d9578`
- `0x1800e572c`
- `0x1800e7500`
- `0x1800e9f30`
- `0x1800eb920`
- `0x1800f19ec`
- `0x1800f5dcc`
- `0x1800fdf60`
- `0x180150750`
- `0x1801507a8`
- `0x1801507f4`
- `0x180150840`
- `0x180150888`
- `0x18016e1f0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800e5ade`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800e5ade`

## string_xrefs

- `0x1800e6b40`: `PostRebootInstallSandbox`
- `0x1800e7366`: `Failed to create private session store.`
- `0x1800e74e1`: `Session complete notification failed.`
- `0x1800e6abe`: `Failed to decompress OC content.`
- `0x1800e5ad7`: `UpdateAgentLCU`
- `0x1800e60d7`: `Executing pending online actions cannot be done in the same call as package installs.`
- `0x1800e5f4d`: `Failed preparing for servicing during pre-shutdown`
- `0x1800e5f99`: `Failed preparing for servicing during pre-shutdown`
- `0x1800e5888`: `No write operations are allowed on a container`
- `0x1800e5917`: `No write operations are allowed on a read only session`
- `0x1800e59fd`: `Cannot finalize a session that has both UseLocalSourceOnly and UseWindowsUpdate set.`
- `0x1800e5a68`: `Cannot finalize a session that has both CbsSessionOptionNoPend and CbsSessionOptionDelayExecutionIfPendRequired set.`
- `0x1800e58e7`: `Read only operations session, exit.`
- `0x1800e6d11`: `Client specifies manual store corruption detect or repair.`
- `0x1800e6cbf`: `Session: {} failed to perform store corruption detect and repair operation.`
- `0x1800e6dd1`: `Session: {} failed to perform store corruption detect and repair operation.`
- `0x1800e6a21`: `Call to decompress the OC content along with setting the store flag to not compress it again.`
- `0x1800e6bff`: `Client specifies auto store corruption detect or repair.`
- `0x1800e6b63`: `Failed to set the sandbox property for post reboot installation.`
- `0x1800e6fbf`: `B2B: OSUninstall: Adding package to reservicing: {}`
- `0x1800e71d3`: `B2B: OSUninstall: Adding package to reservicing: {}`
- `0x1800e704a`: `B2B: OSUninstall: Failed to collect packages from package store`

## pseudocode

```c
__int64 __fastcall CCbsSession::FinalizeInternal(
        CCbsSession *this,
        void *a2,
        struct CCbsPublicSession *a3,
        int a4,
        int *a5)
{
  unsigned int v5; // r12d
  const char *v8; // rdx
  int v9; // eax
  int v10; // edi
  __int64 v11; // rdx
  void *v12; // r14
  int v13; // r13d
  int v14; // eax
  int v15; // eax
  __int64 v16; // rcx
  int v17; // eax
  unsigned int v18; // ecx
  int v19; // eax
  bool v20; // zf
  int v21; // ebx
  int v22; // eax
  int IsAdministrator; // eax
  unsigned int active; // ebx
  int v25; // eax
  int v26; // eax
  int v27; // eax
  int v28; // eax
  int v29; // eax
  int v30; // ecx
  int v31; // eax
  int v32; // eax
  unsigned int v33; // ebx
  int v34; // eax
  int v35; // eax
  unsigned int v36; // r14d
  __int64 v37; // rdx
  int v38; // eax
  int v39; // eax
  unsigned int v40; // eax
  int v41; // eax
  int v42; // eax
  int v43; // eax
  int v44; // eax
  int v45; // eax
  int v46; // eax
  int v47; // eax
  int v48; // eax
  int v49; // eax
  int v50; // eax
  int v51; // eax
  int v52; // eax
  unsigned int v53; // esi
  int v55; // eax
  int v56; // eax
  int v57; // eax
  int v58; // eax
  int v59; // r9d
  __int64 v60; // r8
  unsigned int v61; // ecx
  struct CCbsIdentity **InitPointer; // rax
  struct CCbsPackage **v63; // rax
  struct ICbsUIHandler *v64; // r9
  int v65; // eax
  __int64 v66; // rdx
  int v67; // eax
  struct ICbsIdentity **v68; // r12
  struct ICbsIdentity **v69; // rax
  struct ICbsIdentity *v70; // r13
  struct CCbsPackage **v71; // rax
  struct ICbsUIHandler *v72; // r9
  unsigned int v73; // r14d
  int v74; // eax
  int v75; // eax
  __int64 v76; // rcx
  void *v77; // r12
  int SessionSandbox; // eax
  __int64 *v79; // rcx
  __int64 *v80; // r9
  __int64 v81; // rax
  __int64 *v82; // rdx
  __int64 *v83; // r8
  __int64 v84; // rax
  int v85; // r8d
  int v86; // eax
  unsigned int v87; // eax
  int v88; // [rsp+20h] [rbp-E0h]
  int v89[2]; // [rsp+50h] [rbp-B0h] BYREF
  int v90[2]; // [rsp+58h] [rbp-A8h] BYREF
  struct CCbsPublicSession *v91; // [rsp+60h] [rbp-A0h] BYREF
  __int64 *v92; // [rsp+68h] [rbp-98h] BYREF
  int v93[2]; // [rsp+70h] [rbp-90h] BYREF
  void *v94; // [rsp+78h] [rbp-88h]
  int v95[2]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v96[24]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v97; // [rsp+A0h] [rbp-60h] BYREF
  int v98; // [rsp+A8h] [rbp-58h]
  __int128 v99; // [rsp+B0h] [rbp-50h]
  __int64 v100; // [rsp+C0h] [rbp-40h]
  bool v101[8]; // [rsp+C8h] [rbp-38h] BYREF
  CCbsSession *v102; // [rsp+D0h] [rbp-30h]
  int v103; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v104; // [rsp+E0h] [rbp-20h] BYREF
  struct CCbsIdentity *v105; // [rsp+E8h] [rbp-18h] BYREF
  CCbsPackage *v106; // [rsp+F0h] [rbp-10h] BYREF
  int v107; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE v108[24]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v109; // [rsp+118h] [rbp+18h]
  struct ICbsIdentity **v110; // [rsp+128h] [rbp+28h]
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  v5 = 0;
  v94 = a2;
  v91 = a3;
  *a5 = 0;
  CritSecLocker::CritSecLocker((CritSecLocker *)v96, (CCbsSession *)((char *)this + 584), 1);
  v101[0] = 1;
  v102 = this;
  if ( !a4 && !*((_DWORD *)this + 173) && !*((_DWORD *)this + 403) && *((_DWORD *)this + 369) )
  {
    v8 = "Lazy store initialization and no action to do, exit.";
LABEL_21:
    LogAdapter::TraceAtLevel<>(1, v8);
LABEL_22:
    v10 = v5;
    goto LABEL_213;
  }
  v9 = CCbsSession::CheckInitialized(this);
  v10 = v9;
  if ( v9 < 0 )
  {
    LODWORD(v104) = v9;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Cannot finalize a session that has not been initialized.");
      v91 = (struct CCbsPublicSession *)&v104;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&v91);
    }
    v11 = 195;
    goto LABEL_10;
  }
  v12 = (void *)*((_QWORD *)this + 141);
  v13 = CCbsSession::InspectSessionTask(this);
  if ( !v13 && *((_DWORD *)this + 172) && CCbsSession::IsImageReadOnly(this) )
  {
    v10 = -2146498493;
    LODWORD(v104) = -2146498493;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        v13 + 3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No write operations are allowed on a container");
      v91 = (struct CCbsPublicSession *)&v104;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        v13 + 3,
        (__int64)": {}",
        (__int64)&v91);
    }
    v11 = 212;
    goto LABEL_10;
  }
  *((_DWORD *)this + 172) |= a4;
  if ( *((_BYTE *)this + 1040) )
  {
    if ( !v13 && !*((_DWORD *)this + 172) )
    {
      v8 = "Read only operations session, exit.";
      goto LABEL_21;
    }
    v10 = -2146498493;
    LODWORD(v104) = -2146498493;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No write operations are allowed on a read only session");
      v91 = (struct CCbsPublicSession *)&v104;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&v91);
    }
    v11 = 226;
    goto LABEL_10;
  }
  v14 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 306) + 88LL))(*((_QWORD *)this + 306), 0);
  v10 = v14;
  if ( v14 < 0 )
  {
    LODWORD(v106) = v14;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to validate store version");
      v91 = (struct CCbsPublicSession *)&v106;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&v91);
    }
    v11 = 235;
    goto LABEL_10;
  }
  v15 = *((_DWORD *)this + 172);
  if ( (v15 & 0x20000) != 0 && (v15 & 0x40000) != 0 )
  {
    v10 = -2147024809;
    LODWORD(v104) = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Cannot finalize a session that has both UseLocalSourceOnly and"
                                                          " UseWindowsUpdate set.");
      v91 = (struct CCbsPublicSession *)&v104;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&v91);
    }
    v11 = 243;
    goto LABEL_10;
  }
  if ( (v15 & 0x10000) != 0 && (v15 & 0x2000000) != 0 )
  {
    v10 = -2147024809;
    LODWORD(v104) = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Cannot finalize a session that has both CbsSessionOptionNoPend"
                                                          " and CbsSessionOptionDelayExecutionIfPendRequired set.");
      v91 = (struct CCbsPublicSession *)&v104;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&v91);
    }
    v11 = 248;
    goto LABEL_10;
  }
  if ( (*((_BYTE *)this + 2208) & 0x10) != 0
    && ((unsigned int)CCbsSession::IsClientWindowsUpdate(this)
     || (v16 = *((_QWORD *)this + 81)) != 0 && !(unsigned int)_o__wcsicmp(v16, L"UpdateAgentLCU")) )
  {
    if ( *((_BYTE *)this + 2320) )
    {
      LODWORD(v104) = 0;
      v17 = (*(__int64 (__fastcall **)(struct IServicingWOSCSettings *, const wchar_t *, __int64 *))(*(_QWORD *)vOneSettings + 48LL))(
              vOneSettings,
              L"ENABLEPRIORITY",
              &v104);
      if ( !IsExpectedOneSettingsError_HRESULT(v17) )
        LogAdapter::TraceAtLevelIfFailed<long,>(1, v18, "Unable to get the OneSettings value for ENABLEPRIORITY.");
      switch ( (_DWORD)v104 )
      {
        case 1:
          LogAdapter::TraceAtLevel<>(1, "Setting Normal priority based on onesettings");
          *((_DWORD *)this + 173) &= 0xCFFFFFFF;
          break;
        case 2:
          LogAdapter::TraceAtLevel<>(1, "Setting UserAway priority based on onesettings");
          *((_DWORD *)this + 173) &= ~0x10000000u;
          *((_DWORD *)this + 173) |= 0x20000000u;
          break;
        case 3:
          LogAdapter::TraceAtLevel<>(1, "Setting UserPresent priority based on onesettings");
          *((_DWORD *)this + 173) &= ~0x20000000u;
          *((_DWORD *)this + 173) |= 0x10000000u;
          break;
      }
    }
  }
  v19 = *((_DWORD *)this + 173);
  if ( (v19 & 0x10000000) != 0 )
  {
    CCbsSession::SetUserPresentPriority(this);
  }
  else if ( (v19 & 0x20000000) != 0 )
  {
    CCbsSession::SetUserAwayPriority(this);
  }
  else if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Update_EcoQos>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Update_EcoQos>::GetImpl'::`2'::impl)
         && (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Update_EcoQos>::__private_GetVariant(`wil::Feature<__WilFeatureTraits_Feature_Update_EcoQos>::GetImpl'::`2'::impl) == 1 )
  {
    CCbsSession::SetNormalPriorityEcoQos(this);
  }
  v20 = (*((_DWORD *)this + 172) & 0x200) == 0;
  v103 = *((_DWORD *)this + 172) & 0x200;
  LOBYTE(v5) = !v20;
  v21 = a4 & 0x80000;
  v107 = v5;
  v20 = *((_DWORD *)this + 190) == 0;
  *((_DWORD *)this + 316) = v21 != 0;
  if ( !v20 && !v21 )
  {
    v10 = -2146498494;
    LODWORD(v105) = -2146498494;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Cannot finalize a session that has been finalized.");
      v91 = (struct CCbsPublicSession *)&v105;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&v91);
    }
    v11 = 309;
    goto LABEL_10;
  }
  *((_DWORD *)this + 270) = 1;
  v22 = CCbsSession::FinalizeOCs(this);
  v10 = v22;
  if ( v22 < 0 )
  {
    LODWORD(v105) = v22;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to finalize OCs");
      v92 = (__int64 *)&v105;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&v92);
    }
    v11 = 319;
    goto LABEL_10;
  }
  v20 = *((_DWORD *)this + 403) == 0;
  *((_DWORD *)this + 190) = 1;
  if ( !v20 )
  {
    IsAdministrator = EnsureCallerIsAdministrator(v12, 0);
    v10 = IsAdministrator;
    if ( IsAdministrator < 0 )
    {
      LODWORD(v105) = IsAdministrator;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to ensure caller is an administrator.");
        v92 = (__int64 *)&v105;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)&v92);
      }
      v11 = 331;
      goto LABEL_10;
    }
    if ( *((_DWORD *)this + 403) == 1 )
    {
      v26 = CCbsSession::ExportRepository(this, a5);
    }
    else if ( *((_DWORD *)this + 403) == 3 )
    {
      v26 = CCbsSession::PerformPrepareServicingOperation(this, v5, v91);
    }
    else
    {
      if ( *((_DWORD *)this + 403) != 4 )
      {
        if ( *((_DWORD *)this + 403) == 10 )
        {
          active = CCbsSessionManager::RegisterActiveSession((CCbsSessionManager *)qword_1803B11E8, this, 0);
          v25 = CCbsSession::OfflineFinalizeInstallation(this);
        }
        else
        {
          if ( *((_DWORD *)this + 403) != 11 )
            goto LABEL_90;
          active = CCbsSessionManager::RegisterActiveSession((CCbsSessionManager *)qword_1803B11E8, this, 0);
          v25 = CCbsSession::OfflineRollbackInstallation(this);
        }
        v10 = v25;
        CCbsSessionManager::UnregisterActiveSession((CCbsSessionManager *)qword_1803B11E8, active);
LABEL_86:
        if ( v10 < 0 )
        {
          LODWORD(v104) = v10;
          if ( LogAdapter::g_Logger )
          {
            LODWORD(v106) = *((_DWORD *)this + 403);
            LogAdapter::Logger::LogNumObjects<unsigned long>(
              (_DWORD)LogAdapter::g_Logger,
              0,
              3,
              (unsigned int)"Failed to perform client operation: {}",
              (__int64)&v106);
            v92 = &v104;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {}",
              (__int64)&v92);
          }
          v11 = 362;
          goto LABEL_10;
        }
LABEL_90:
        v10 = 0;
        goto LABEL_213;
      }
      v26 = CCbsSession::PerformLateAcquisitionOperation(this, v94, v5, v91, a5);
    }
    v10 = v26;
    goto LABEL_86;
  }
  v5 = 0;
  v10 = 0;
  if ( (*((_DWORD *)this + 172) & 0x200000) != 0 )
  {
    v27 = EnsureCallerIsAdministrator(v12, 0);
    v10 = v27;
    if ( v27 < 0 )
    {
      LODWORD(v105) = v27;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to ensure caller is an administrator.");
        v92 = (__int64 *)&v105;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)&v92);
      }
      v11 = 372;
      goto LABEL_10;
    }
    v28 = AnticipatePreshutdownNeeded();
    v10 = v28;
    if ( v28 < 0 )
    {
      if ( v13 )
      {
        LODWORD(v104) = v28;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed preparing for servicing during pre-shutdown");
          *(_QWORD *)v90 = &v104;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)v90);
        }
        v11 = 379;
      }
      else
      {
        LODWORD(v106) = v28;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed preparing for servicing during pre-shutdown");
          *(_QWORD *)v95 = &v106;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)v95);
        }
        v11 = 377;
      }
      goto LABEL_10;
    }
  }
  if ( (*((_BYTE *)this + 692) & 1) != 0 )
  {
    *(_QWORD *)v89 = *((_QWORD *)this + 81);
    if ( LogAdapter::g_Logger )
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (__int64)LogAdapter::g_Logger,
        1,
        1,
        (__int64)"ExecPA: Client: {} requested postponing of online actions until explicitly requested",
        (__int64)v89);
    v29 = PackageStoreSetProperty(this, L"PostponeOnlineActions", 1u);
    v5 = v29;
    if ( v29 < 0 )
    {
      v107 = v29;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"ExecPA: Failed postponing online actions");
        *(_QWORD *)v89 = &v107;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v89);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x186,
        (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationexecution.cpp",
        (const char *)v5,
        v88);
      goto LABEL_22;
    }
    v5 = 0;
  }
  v30 = *((_DWORD *)this + 173);
  if ( (v30 & 2) != 0 )
  {
    if ( v13 )
    {
      v10 = -2146498554;
      v103 = -2146498554;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Executing pending online actions cannot be done in the same "
                                                            "call as package installs.");
        *(_QWORD *)v89 = &v103;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v89);
      }
      v11 = 397;
    }
    else
    {
      v91 = (struct CCbsPublicSession *)*((_QWORD *)this + 81);
      if ( LogAdapter::g_Logger )
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (__int64)LogAdapter::g_Logger,
          1,
          1,
          (__int64)"ExecPA: Executing postponed online actions per request by client: {}",
          (__int64)&v91);
      v31 = EnsureCallerIsAdministrator(v12, 0);
      v10 = v31;
      if ( v31 >= 0 )
      {
        v32 = PackageStoreSetProperty(this, L"PostponeOnlineActions", 2u);
        v10 = v32;
        if ( v32 >= 0 )
        {
          v33 = CCbsSessionManager::RegisterActiveSession((CCbsSessionManager *)qword_1803B11E8, this, 0);
          CritSecLocker::Unlock((CritSecLocker *)v96);
          v10 = CbsCoreStartupProcessingEx(1);
          CCbsSessionManager::UnregisterActiveSession((CCbsSessionManager *)qword_1803B11E8, v33);
          if ( v10 == -2147021886 )
          {
            LogAdapter::TraceAtLevel<>(1, "ExecPA: Online actions required a reboot");
            *a5 = 1;
          }
          else if ( v10 < 0 )
          {
            v103 = v10;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                (__int64)LogAdapter::g_Logger,
                0,
                3,
                (struct Windows::Rtl::IRtlFormattedOutputStream *)"ExecPA: Failed executing online actions");
              *(_QWORD *)v89 = &v103;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (__int64)LogAdapter::g_Logger,
                1,
                3,
                (__int64)": {}",
                (__int64)v89);
            }
            v11 = 427;
            goto LABEL_10;
          }
          *((_DWORD *)this + 192) = 208;
          goto LABEL_22;
        }
        v103 = v32;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"ExecPA: Failed clearing postpone flag for online actions");
          *(_QWORD *)v89 = &v103;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)v89);
        }
        v11 = 406;
      }
      else
      {
        v103 = v31;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to ensure caller is an administrator.");
          *(_QWORD *)v89 = &v103;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)v89);
        }
        v11 = 402;
      }
    }
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationexecution.cpp",
      (const char *)(unsigned int)v10,
      v88);
    goto LABEL_213;
  }
  if ( v13 )
  {
    v59 = 7044;
    if ( *((_QWORD *)this + 122) )
    {
      v60 = **((_QWORD **)this + 124);
      if ( *(_QWORD *)(v60 + 24) )
      {
        v61 = *(_DWORD *)(*(_QWORD *)(**(_QWORD **)(v60 + 40) + 24LL) + 632LL);
        if ( v61 <= 0xC && _bittest(&v59, v61) && (unsigned int)CCbsSession::IsClientWindowsUpdate(this) )
          *((_DWORD *)this + 172) |= 0x100u;
      }
    }
    if ( (*((_BYTE *)this + 692) & 4) != 0 )
    {
      v105 = 0;
      InitPointer = (struct CCbsIdentity **)Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v105);
      if ( CCbsSession::IsAnLCUInstalled(this, InitPointer) && v105 )
      {
        v104 = 0;
        v63 = (struct CCbsPackage **)Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v104);
        v65 = CCbsSession::ResolvePackage(this, 0, *((void **)this + 141), v64, v105, 1, v63, 0);
        v36 = v65;
        if ( v65 < 0 )
        {
          v103 = v65;
          if ( LogAdapter::g_Logger )
          {
            *(_QWORD *)v89 = GetFastCbsIdentityString(v105);
            LogAdapter::Logger::LogNumObjects<wchar_t const *>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (__int64)"Failed to resolve the LCU package: {}",
              (__int64)v89);
            *(_QWORD *)v90 = &v103;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {}",
              (__int64)v90);
          }
          v66 = 638;
          goto LABEL_243;
        }
        *(_QWORD *)v89 = GetFastCbsIdentityString(v105);
        if ( LogAdapter::g_Logger )
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            (__int64)LogAdapter::g_Logger,
            1,
            1,
            (__int64)"B2B: OSUninstall: Adding package to reservicing: {}",
            (__int64)v89);
        *(_QWORD *)v89 = v104;
        v36 = CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>::Add((char *)this + 2144, v89);
        if ( (v36 & 0x80000000) != 0 )
        {
          v66 = 641;
LABEL_243:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v66,
            (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationexecution.cpp",
            (const char *)v36,
            v88);
          Windows::AutoComPtr<CCbsDriverDeployment>::Close(&v104);
LABEL_244:
          Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v105);
          goto LABEL_141;
        }
        *((_DWORD *)this + 173) |= 0x40000000u;
        Windows::AutoComPtr<CCbsDriverDeployment>::Close(&v104);
      }
      CCbsInterfaceArray<ICbsSessionObserverListener *>::CCbsInterfaceArray<ICbsSessionObserverListener *>(v108);
      v67 = PackageStoreCollectPackages(this, 496, v108);
      v36 = v67;
      if ( v67 < 0 )
      {
        v103 = v67;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"B2B: OSUninstall: Failed to collect packages from package store");
          *(_QWORD *)v89 = &v103;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)v89);
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x293,
          (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationexecution.cpp",
          (const char *)v36,
          v88);
LABEL_254:
        CCbsArrayBase<CCbsIdentity *,CCbsInterfaceArray<CCbsIdentity *>>::~CCbsArrayBase<CCbsIdentity *,CCbsInterfaceArray<CCbsIdentity *>>(v108);
        goto LABEL_244;
      }
      v68 = v110;
      v69 = &v110[v109];
      *(_QWORD *)v93 = v69;
      while ( v68 != v69 )
      {
        v70 = *v68;
        v106 = 0;
        v71 = (struct CCbsPackage **)Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v106);
        v10 = CCbsSession::ResolvePackage(this, 0, 0, v72, v70, 1, v71, 0);
        *(_QWORD *)v89 = GetFastCbsIdentityString(v70);
        if ( v10 >= 0 )
        {
          v73 = *((_DWORD *)v106 + 158);
          if ( CCbsPackage::IsLCUPackage(v106) && *((_DWORD *)v106 + 176) != 112
            || !*((_DWORD *)v106 + 225)
            && *((_DWORD *)v106 + 159) != 2
            && v73 <= 0xC
            && (v74 = 7044, _bittest(&v74, v73)) )
          {
            *(_QWORD *)v95 = GetFastCbsIdentityString(v70);
            if ( LogAdapter::g_Logger )
              LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                (__int64)LogAdapter::g_Logger,
                1,
                1,
                (__int64)"B2B: OSUninstall: Adding package to reservicing: {}",
                (__int64)v95);
            v92 = (__int64 *)v106;
            v75 = CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>::Add((char *)this + 2144, &v92);
            v36 = v75;
            if ( v75 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x2BE,
                (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationexecution.cpp",
                (const char *)(unsigned int)v75,
                v88);
              Windows::AutoComPtr<CCbsDriverDeployment>::Close(&v106);
              goto LABEL_254;
            }
            *((_DWORD *)this + 173) |= 0x40000000u;
          }
        }
        else
        {
          LogAdapter::TraceAtLevelHr<long,wchar_t const *>(1, (unsigned int)v10, "Unable to resolve package: {}", v89);
          *(_QWORD *)v90 = GetFastCbsIdentityString(v70);
          if ( LogAdapter::g_Logger )
            LogAdapter::Logger::LogNumObjects<wchar_t const *>(
              (__int64)LogAdapter::g_Logger,
              1,
              1,
              (__int64)"Unable to resolve package: {}, moving on",
              (__int64)v90);
          v10 = 0;
        }
        Windows::AutoComPtr<CCbsDriverDeployment>::Close(&v106);
        v69 = *(struct ICbsIdentity ***)v93;
        ++v68;
      }
      CCbsArrayBase<CCbsIdentity *,CCbsInterfaceArray<CCbsIdentity *>>::~CCbsArrayBase<CCbsIdentity *,CCbsInterfaceArray<CCbsIdentity *>>(v108);
      Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v105);
    }
    if ( (*((_DWORD *)this + 172) & 0x100) != 0 )
      *((_DWORD *)this + 264) = 1;
    if ( !(unsigned int)CCbsSession::IsOffline(this) )
    {
      v97 = 0;
      v98 = 0;
      v100 = 0;
      v99 = 0;
      if ( (int)CCbsSession::GetStoreObject(v76, 0, 1, 0, &v97) >= 0 )
      {
        CCbsStoreObject::SetValue((CCbsStoreObject *)&v97, L"DoqTime", 0);
        CCbsStoreObject::SetValue((CCbsStoreObject *)&v97, L"DoqCount", 0);
        CCbsStoreObject::SetValue((CCbsStoreObject *)&v97, L"PoqTime", 0);
        CCbsStoreObject::SetValue((CCbsStoreObject *)&v97, L"PoqCount", 0);
        CCbsStoreObject::SetValue((CCbsStoreObject *)&v97, L"RptTime", 0);
        CCbsStoreObject::SetValue((CCbsStoreObject *)&v97, L"RptCount", 0);
      }
      CCbsStoreObject::~CCbsStoreObject((CCbsStoreObject *)&v97);
    }
    v77 = v94;
    SessionSandbox = CCbsSession::CreateSessionSandbox(this, v94, 0, 0);
    v36 = SessionSandbox;
    if ( SessionSandbox < 0 )
    {
      v103 = SessionSandbox;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to create private session store.");
        *(_QWORD *)v93 = &v103;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v93);
      }
      v37 = 740;
      goto LABEL_140;
    }
    CritSecLocker::Unlock((CritSecLocker *)v96);
    if ( *((_DWORD *)this + 316) )
    {
      CCbsSession::SetRetryFlag(this);
      v79 = (__int64 *)*((_QWORD *)this + 102);
      v80 = &v79[*((_QWORD *)this + 100)];
      while ( v79 != v80 )
      {
        v81 = *v79;
        *(_DWORD *)(v81 + 56) = 4096;
        v82 = *(__int64 **)(v81 + 104);
        v83 = &v82[*(_QWORD *)(v81 + 88)];
        while ( v82 != v83 )
        {
          v84 = *v82++;
          *(_DWORD *)(v84 + 12) = 4096;
        }
        ++v79;
      }
    }
    v85 = *((_DWORD *)this + 316);
    v101[0] = v103 == 0;
    v86 = CCbsSession::PerformSessionTasksOperation(this, v77, v85, 0, v107, 0, v91, a5, 0);
    v36 = v86;
    if ( v86 < 0 )
    {
      v103 = v86;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to perform operation. ");
        *(_QWORD *)v93 = &v103;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v93);
      }
      v37 = 778;
      goto LABEL_140;
    }
    if ( *((_DWORD *)this + 316) && !*a5 )
    {
      v87 = CCbsSession::ChangeState(this, 208, (unsigned int)v10);
      LogAdapter::TraceAtLevelIfFailed<long,>(1, v87, "Session complete notification failed.");
    }
    goto LABEL_208;
  }
  v34 = *((_DWORD *)this + 172);
  if ( (v34 & 0x400) != 0 )
  {
    LogAdapter::TraceAtLevel<>(1, "No call is made on InitiateChanges, Scavenge only.");
    v35 = EnsureCallerIsAdministrator(v12, 0);
    v36 = v35;
    if ( v35 < 0 )
    {
      v103 = v35;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to ensure caller is an administrator.");
        *(_QWORD *)v89 = &v103;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v89);
      }
      v37 = 443;
LABEL_140:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v37,
        (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationexecution.cpp",
        (const char *)v36,
        v88);
LABEL_141:
      v10 = v36;
      goto LABEL_213;
    }
    CritSecLocker::Unlock((CritSecLocker *)v96);
    v38 = CCbsSession::PerformMaintenanceTaskOperation(this, 0, vhIdleProcessingPaused, 0, 0, 4u, a5, 0, 0);
    v36 = v38;
    if ( v38 < 0 )
    {
      v103 = v38;
      if ( LogAdapter::g_Logger )
      {
        *(_QWORD *)v89 = *((_QWORD *)this + 80);
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (__int64)"Session: {} failed to perform synchronous scavenge operation",
          (__int64)v89);
        *(_QWORD *)v90 = &v103;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v90);
      }
      v37 = 460;
      goto LABEL_140;
    }
    goto LABEL_206;
  }
  if ( (v34 & 0x400000) != 0 )
  {
    LogAdapter::TraceAtLevel<>(1, "No call is made on InitiateChanges, Synchronous Cleanup only.");
    v39 = EnsureCallerIsAdministrator(v12, 0);
    v36 = v39;
    if ( v39 < 0 )
    {
      v103 = v39;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to ensure caller is an administrator.");
        *(_QWORD *)v89 = &v103;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v89);
      }
      v37 = 476;
      goto LABEL_140;
    }
    CritSecLocker::Unlock((CritSecLocker *)v96);
    v40 = 1;
    if ( (*((_DWORD *)this + 173) & 0x800000) != 0 )
    {
      LogAdapter::TraceAtLevel<>(1, "Testing mode, simulating automatic cleanup");
      v40 = 3;
    }
    v41 = CCbsSession::PerformMaintenanceTaskOperation(this, 0, vhIdleProcessingPaused, 0, 0, v40, a5, 0, 0);
    v36 = v41;
    if ( v41 < 0 )
    {
      v103 = v41;
      if ( LogAdapter::g_Logger )
      {
        *(_QWORD *)v89 = *((_QWORD *)this + 80);
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (__int64)"Session: {} failed to perform Synchronous Cleanup operation",
          (__int64)v89);
        *(_QWORD *)v90 = &v103;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v90);
      }
      v37 = 498;
      goto LABEL_140;
    }
    goto LABEL_206;
  }
  if ( (v34 & 0x100000) != 0 )
  {
    LogAdapter::TraceAtLevel<>(1, "Client specifies reporting stack internal information");
    v42 = EnsureCallerIsAdministrator(v12, 0);
    v36 = v42;
    if ( v42 < 0 )
    {
      v103 = v42;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to ensure caller is an administrator.");
        *(_QWORD *)v89 = &v103;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v89);
      }
      v37 = 509;
      goto LABEL_140;
    }
    CritSecLocker::Unlock((CritSecLocker *)v96);
    v43 = CCbsSession::PerformInternalReportingOperation(this, v91, a5);
    v36 = v43;
    if ( v43 < 0 )
    {
      v103 = v43;
      if ( LogAdapter::g_Logger )
      {
        *(_QWORD *)v89 = *((_QWORD *)this + 80);
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (__int64)"Session: {} failed to perform internal reporting operation",
          (__int64)v89);
        *(_QWORD *)v90 = &v103;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v90);
      }
      v37 = 519;
      goto LABEL_140;
    }
LABEL_206:
    *((_DWORD *)this + 192) = 208;
    goto LABEL_208;
  }
  if ( v34 >= 0 )
  {
    if ( (v34 & 0x800) != 0 )
    {
      LogAdapter::TraceAtLevel<>(1, "Client specified cancelling all pended transactions.");
      v46 = EnsureCallerIsAdministrator(v12, 0);
      v36 = v46;
      if ( v46 < 0 )
      {
        v103 = v46;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to ensure caller is an administrator.");
          *(_QWORD *)v89 = &v103;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)v89);
        }
        v37 = 542;
        goto LABEL_140;
      }
      CritSecLocker::Unlock((CritSecLocker *)v96);
      v47 = CCbsSession::PerformCancelTransactionsInternal(this, a5, 0);
      v36 = v47;
      if ( v47 < 0 )
      {
        v103 = v47;
        if ( LogAdapter::g_Logger )
        {
          *(_QWORD *)v89 = *((_QWORD *)this + 80);
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (__int64)"Session: {} failed to perform cancelling all pending transactions.",
            (__int64)v89);
          *(_QWORD *)v90 = &v103;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)v90);
        }
        v37 = 552;
        goto LABEL_140;
      }
    }
    else if ( (v30 & 0x800) != 0 || (v30 & 0x1000) != 0 )
    {
      LogAdapter::TraceAtLevel<>(1, "Client specifies manual store corruption detect or repair.");
      v57 = EnsureCallerIsAdministrator(v12, 0);
      v36 = v57;
      if ( v57 < 0 )
      {
        v103 = v57;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to ensure caller is an administrator.");
          *(_QWORD *)v89 = &v103;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)v89);
        }
        v37 = 559;
        goto LABEL_140;
      }
      CritSecLocker::Unlock((CritSecLocker *)v96);
      v58 = CCbsSession::PerformStoreCorruptionDetectAndRepairOperation(this, v94, 1, a5);
      v36 = v58;
      if ( v58 < 0 )
      {
        v103 = v58;
        if ( LogAdapter::g_Logger )
        {
          *(_QWORD *)v89 = *((_QWORD *)this + 80);
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (__int64)"Session: {} failed to perform store corruption detect and repair operation.",
            (__int64)v89);
          *(_QWORD *)v90 = &v103;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)v90);
        }
        v37 = 569;
        goto LABEL_140;
      }
    }
    else
    {
      if ( (v34 & 0xC000) == 0 )
      {
        if ( (v34 & 0x8000000) != 0 )
        {
          LogAdapter::TraceAtLevel<>(1, "No call is made on InitiateChanges, Synchronous analysis only.");
          v48 = EnsureCallerIsAdministrator(v12, 0);
          v36 = v48;
          if ( v48 < 0 )
          {
            v103 = v48;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                (__int64)LogAdapter::g_Logger,
                0,
                3,
                (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to ensure caller is an administrator.");
              *(_QWORD *)v89 = &v103;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (__int64)LogAdapter::g_Logger,
                1,
                3,
                (__int64)": {}",
                (__int64)v89);
            }
            v37 = 591;
            goto LABEL_140;
          }
          CritSecLocker::Unlock((CritSecLocker *)v96);
          v49 = CCbsSession::PerformStoreAnalysisOperation(this, a5);
          v36 = v49;
          if ( v49 < 0 )
          {
            v103 = v49;
            if ( LogAdapter::g_Logger )
            {
              *(_QWORD *)v89 = *((_QWORD *)this + 80);
              LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                (__int64)LogAdapter::g_Logger,
                0,
                3,
                (__int64)"Session: {} failed to perform store analysis operation",
                (__int64)v89);
              *(_QWORD *)v90 = &v103;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (__int64)LogAdapter::g_Logger,
                1,
                3,
                (__int64)": {}",
                (__int64)v90);
            }
            v37 = 597;
            goto LABEL_140;
          }
        }
        else
        {
          if ( (v30 & 0x40) == 0 )
          {
            *a5 = CCbsSession::IsRebootRequired(this);
            *((_DWORD *)this + 192) = 208;
            goto LABEL_208;
          }
          LogAdapter::TraceAtLevel<>(
            1,
            "Call to decompress the OC content along with setting the store flag to not compress it again.");
          v50 = EnsureCallerIsAdministrator(v12, 0);
          v36 = v50;
          if ( v50 < 0 )
          {
            v103 = v50;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                (__int64)LogAdapter::g_Logger,
                0,
                3,
                (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to ensure caller is an administrator.");
              *(_QWORD *)v89 = &v103;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (__int64)LogAdapter::g_Logger,
                1,
                3,
                (__int64)": {}",
                (__int64)v89);
            }
            v37 = 607;
            goto LABEL_140;
          }
          CritSecLocker::Unlock((CritSecLocker *)v96);
          v51 = CCbsSession::DecompressOCContent(this);
          v36 = v51;
          if ( v51 < 0 )
          {
            v103 = v51;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                (__int64)LogAdapter::g_Logger,
                0,
                3,
                (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to decompress OC content.");
              *(_QWORD *)v89 = &v103;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (__int64)LogAdapter::g_Logger,
                1,
                3,
                (__int64)": {}",
                (__int64)v89);
            }
            v37 = 611;
            goto LABEL_140;
          }
        }
        goto LABEL_206;
      }
      LogAdapter::TraceAtLevel<>(1, "Client specifies auto store corruption detect or repair.");
      v55 = EnsureCallerIsAdministrator(v12, 0);
      v36 = v55;
      if ( v55 < 0 )
      {
        v103 = v55;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to ensure caller is an administrator.");
          *(_QWORD *)v89 = &v103;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)v89);
        }
        v37 = 575;
        goto LABEL_140;
      }
      CritSecLocker::Unlock((CritSecLocker *)v96);
      v56 = CCbsSession::PerformStoreCorruptionDetectAndRepairOperation(this, v94, 0, a5);
      v36 = v56;
      if ( v56 < 0 )
      {
        v103 = v56;
        if ( LogAdapter::g_Logger )
        {
          *(_QWORD *)v89 = *((_QWORD *)this + 80);
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (__int64)"Session: {} failed to perform store corruption detect and repair operation.",
            (__int64)v89);
          *(_QWORD *)v90 = &v103;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)v90);
        }
        v37 = 585;
        goto LABEL_140;
      }
    }
  }
  else
  {
    LogAdapter::TraceAtLevel<>(1, "Client specified cancelling only smart pended transactions.");
    v44 = EnsureCallerIsAdministrator(v12, 0);
    v36 = v44;
    if ( v44 < 0 )
    {
      v103 = v44;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to ensure caller is an administrator.");
        *(_QWORD *)v89 = &v103;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v89);
      }
      v37 = 529;
      goto LABEL_140;
    }
    v45 = CCbsSession::PerformCancelTransactionsInternal(this, a5, 1);
    v36 = v45;
    if ( v45 < 0 )
    {
      v103 = v45;
      if ( LogAdapter::g_Logger )
      {
        *(_QWORD *)v89 = *((_QWORD *)this + 80);
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (__int64)"Session: {} failed to perform cancelling all pending transactions.",
          (__int64)v89);
        *(_QWORD *)v90 = &v103;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v90);
      }
      v37 = 533;
      goto LABEL_140;
    }
    *a5 |= PackageStoreIsPendingRequired(this, 0, 0);
  }
LABEL_208:
  if ( *((_BYTE *)this + 2273) )
  {
    v52 = PackageStoreSetStringProperty(0, L"PostRebootInstallSandbox", *((const wchar_t **)this + 285));
    v53 = v52;
    if ( v52 < 0 )
    {
      v103 = v52;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to set the sandbox property for post reboot installation.");
        *(_QWORD *)v93 = &v103;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v93);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x31A,
        (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationexecution.cpp",
        (const char *)v53,
        v88);
      v10 = v53;
    }
  }
LABEL_213:
  Windows::Detail::OnBlockExitImpl__CCbsSession::FinalizeInternal_::_2_::_lambda_1___::_OnBlockExitImpl__CCbsSession::FinalizeInternal_::_2_::_lambda_1___(v101);
  CritSecLocker::~CritSecLocker((CritSecLocker *)v96);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800e572c  mov     [rsp-8+arg_18], rbx
0x1800e5731  push    rbp
0x1800e5732  push    rsi
0x1800e5733  push    rdi
0x1800e5734  push    r12
0x1800e5736  push    r13
0x1800e5738  push    r14
0x1800e573a  push    r15
0x1800e573c  lea     rbp, [rsp-50h]
0x1800e5741  sub     rsp, 150h
0x1800e5748  mov     rax, cs:__security_cookie
0x1800e574f  xor     rax, rsp
0x1800e5752  mov     [rbp+80h+var_40], rax
0x1800e5756  mov     r15, [rbp+80h+arg_20]
0x1800e575d  xor     r12d, r12d
0x1800e5760  mov     [rsp+180h+var_108], rdx
0x1800e5765  mov     rsi, rcx
0x1800e5768  mov     [rsp+180h+var_120], r8
0x1800e576d  lea     rdx, [rcx+248h]; struct AutoCritSec *
0x1800e5774  lea     rcx, [rbp+80h+var_F8]; this
0x1800e5778  mov     ebx, r9d
0x1800e577b  lea     r14d, [r12+1]
0x1800e5780  mov     [r15], r12d
0x1800e5783  mov     r8b, r14b; bool
0x1800e5786  call    ??0CritSecLocker@@QEAA@AEAVAutoCritSec@@_N@Z; CritSecLocker::CritSecLocker(AutoCritSec &,bool)
0x1800e578b  mov     [rbp+80h+var_B8], r14b
0x1800e578f  mov     [rbp+80h+var_B0], rsi
0x1800e5793  test    ebx, ebx
0x1800e5795  jnz     short loc_1800E57C1
0x1800e5797  cmp     [rsi+2B4h], r12d
0x1800e579e  jnz     short loc_1800E57C1
0x1800e57a0  cmp     [rsi+64Ch], r12d
0x1800e57a7  jnz     short loc_1800E57C1
0x1800e57a9  cmp     [rsi+5C4h], r12d
0x1800e57b0  jz      short loc_1800E57C1
0x1800e57b2  lea     rdx, aLazyStoreIniti; "Lazy store initialization and no action"...
0x1800e57b9  mov     ecx, r14d
0x1800e57bc  jmp     loc_1800E58F1
0x1800e57c1  mov     rcx, rsi; this
0x1800e57c4  call    ?CheckInitialized@CCbsSession@@QEAAJXZ; CCbsSession::CheckInitialized(void)
0x1800e57c9  mov     edi, eax
0x1800e57cb  test    eax, eax
0x1800e57cd  jns     short loc_1800E5840
0x1800e57cf  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800e57d6  mov     dword ptr [rbp+80h+var_A0], eax
0x1800e57d9  test    rcx, rcx
0x1800e57dc  jz      short loc_1800E5820
0x1800e57de  mov     ebx, 3
0x1800e57e3  lea     r9, aCannotFinalize_1; "Cannot finalize a session that has not "...
0x1800e57ea  mov     r8d, ebx
0x1800e57ed  xor     edx, edx
0x1800e57ef  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800e57f4  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800e57fb  lea     rax, [rbp+80h+var_A0]
0x1800e57ff  mov     [rsp+180h+var_120], rax
0x1800e5804  lea     r9, asc_1802EE7AC; ": {}"
0x1800e580b  lea     rax, [rsp+180h+var_120]
0x1800e5810  mov     r8d, ebx
0x1800e5813  mov     dl, r14b
0x1800e5816  mov     [rsp+180h+var_160], rax; int
0x1800e581b  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800e5820  mov     edx, 0C3h; void *
0x1800e5825  mov     rcx, [rbp+88h]; this
0x1800e582c  lea     r8, aOnecoreBaseCbs_110; "onecore\\base\\cbs\\core\\cbssessionope"...
0x1800e5833  mov     r9d, edi; char *
0x1800e5836  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e583b  jmp     loc_1800E6BBD
0x1800e5840  mov     r14, [rsi+468h]
0x1800e5847  mov     rcx, rsi; this
0x1800e584a  call    ?InspectSessionTask@CCbsSession@@AEAAHXZ; CCbsSession::InspectSessionTask(void)
0x1800e584f  mov     r13d, eax
0x1800e5852  test    eax, eax
0x1800e5854  jnz     short loc_1800E58C9
0x1800e5856  cmp     [rsi+2B0h], r12d
0x1800e585d  jz      short loc_1800E58C9
0x1800e585f  mov     rcx, rsi; this
0x1800e5862  call    ?IsImageReadOnly@CCbsSession@@QEAA_NXZ; CCbsSession::IsImageReadOnly(void)
0x1800e5867  test    al, al
0x1800e5869  jz      short loc_1800E58C9
0x1800e586b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800e5872  mov     edi, 800F0843h
0x1800e5877  mov     dword ptr [rbp+80h+var_A0], edi
0x1800e587a  test    rcx, rcx
0x1800e587d  jz      short loc_1800E58BF
0x1800e587f  lea     ebx, [r13+3]
0x1800e5883  xor     edx, edx
0x1800e5885  mov     r8d, ebx
0x1800e5888  lea     r9, aNoWriteOperati_0; "No write operations are allowed on a co"...
0x1800e588f  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800e5894  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800e589b  lea     rax, [rbp+80h+var_A0]
0x1800e589f  mov     [rsp+180h+var_120], rax
0x1800e58a4  lea     r9, asc_1802EE7AC; ": {}"
0x1800e58ab  lea     rax, [rsp+180h+var_120]
0x1800e58b0  mov     r8d, ebx
0x1800e58b3  mov     dl, 1
0x1800e58b5  mov     [rsp+180h+var_160], rax
0x1800e58ba  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800e58bf  mov     edx, 0D4h
0x1800e58c4  jmp     loc_1800E5825
0x1800e58c9  or      [rsi+2B0h], ebx
0x1800e58cf  mov     eax, [rsi+2B0h]
0x1800e58d5  cmp     [rsi+410h], r12b
0x1800e58dc  jz      short loc_1800E595D
0x1800e58de  test    r13d, r13d
0x1800e58e1  jnz     short loc_1800E58FE
0x1800e58e3  test    eax, eax
0x1800e58e5  jnz     short loc_1800E58FE
0x1800e58e7  lea     rdx, aReadOnlyOperat; "Read only operations session, exit."
0x1800e58ee  lea     ecx, [rax+1]
0x1800e58f1  call    ??$TraceAtLevel@$$V@LogAdapter@@YAXW4LogLevel@0@QEBD@Z; LogAdapter::TraceAtLevel<>(LogAdapter::LogLevel,char const * const)
0x1800e58f6  mov     edi, r12d
0x1800e58f9  jmp     loc_1800E6BBD
0x1800e58fe  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800e5905  mov     edi, 800F0843h
0x1800e590a  mov     dword ptr [rbp+80h+var_A0], edi
0x1800e590d  test    rcx, rcx
0x1800e5910  jz      short loc_1800E5953
0x1800e5912  mov     ebx, 3
0x1800e5917  lea     r9, aNoWriteOperati; "No write operations are allowed on a re"...
0x1800e591e  mov     r8d, ebx
0x1800e5921  xor     edx, edx
0x1800e5923  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800e5928  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800e592f  lea     rax, [rbp+80h+var_A0]
0x1800e5933  mov     [rsp+180h+var_120], rax
0x1800e5938  lea     r9, asc_1802EE7AC; ": {}"
0x1800e593f  lea     rax, [rsp+180h+var_120]
0x1800e5944  mov     r8d, ebx
0x1800e5947  mov     dl, 1
0x1800e5949  mov     [rsp+180h+var_160], rax
0x1800e594e  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800e5953  mov     edx, 0E2h
0x1800e5958  jmp     loc_1800E5825
0x1800e595d  mov     rcx, [rsi+990h]
0x1800e5964  xor     edx, edx
0x1800e5966  mov     rax, [rcx]
0x1800e5969  mov     rax, [rax+58h]
0x1800e596d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5972  mov     edi, eax
0x1800e5974  test    eax, eax
0x1800e5976  jns     short loc_1800E59D2
0x1800e5978  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800e597f  mov     dword ptr [rbp+80h+var_90], eax
0x1800e5982  test    rcx, rcx
0x1800e5985  jz      short loc_1800E59C8
0x1800e5987  mov     ebx, 3
0x1800e598c  lea     r9, aFailedToValida_3; "Failed to validate store version"
0x1800e5993  mov     r8d, ebx
0x1800e5996  xor     edx, edx
0x1800e5998  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800e599d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800e59a4  lea     rax, [rbp+80h+var_90]
0x1800e59a8  mov     [rsp+180h+var_120], rax
0x1800e59ad  lea     r9, asc_1802EE7AC; ": {}"
0x1800e59b4  lea     rax, [rsp+180h+var_120]
0x1800e59b9  mov     r8d, ebx
0x1800e59bc  mov     dl, 1
0x1800e59be  mov     [rsp+180h+var_160], rax
0x1800e59c3  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800e59c8  mov     edx, 0EBh
0x1800e59cd  jmp     loc_1800E5825
0x1800e59d2  mov     eax, [rsi+2B0h]
0x1800e59d8  bt      eax, 11h
0x1800e59dc  jnb     short loc_1800E5A43
0x1800e59de  bt      eax, 12h
0x1800e59e2  jnb     short loc_1800E5A43
0x1800e59e4  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800e59eb  mov     edi, 80070057h
0x1800e59f0  mov     dword ptr [rbp+80h+var_A0], edi
0x1800e59f3  test    rcx, rcx
0x1800e59f6  jz      short loc_1800E5A39
0x1800e59f8  mov     ebx, 3
0x1800e59fd  lea     r9, aCannotFinalize_2; "Cannot finalize a session that has both"...
0x1800e5a04  mov     r8d, ebx
0x1800e5a07  xor     edx, edx
0x1800e5a09  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800e5a0e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800e5a15  lea     rax, [rbp+80h+var_A0]
0x1800e5a19  mov     [rsp+180h+var_120], rax
0x1800e5a1e  lea     r9, asc_1802EE7AC; ": {}"
0x1800e5a25  lea     rax, [rsp+180h+var_120]
0x1800e5a2a  mov     r8d, ebx
0x1800e5a2d  mov     dl, 1
0x1800e5a2f  mov     [rsp+180h+var_160], rax
0x1800e5a34  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800e5a39  mov     edx, 0F3h
0x1800e5a3e  jmp     loc_1800E5825
0x1800e5a43  bt      eax, 10h
0x1800e5a47  jnb     short loc_1800E5AAE
0x1800e5a49  bt      eax, 19h
0x1800e5a4d  jnb     short loc_1800E5AAE
0x1800e5a4f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800e5a56  mov     edi, 80070057h
0x1800e5a5b  mov     dword ptr [rbp+80h+var_A0], edi
0x1800e5a5e  test    rcx, rcx
0x1800e5a61  jz      short loc_1800E5AA4
0x1800e5a63  mov     ebx, 3
0x1800e5a68  lea     r9, aCannotFinalize_0; "Cannot finalize a session that has both"...
0x1800e5a6f  mov     r8d, ebx
0x1800e5a72  xor     edx, edx
0x1800e5a74  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800e5a79  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800e5a80  lea     rax, [rbp+80h+var_A0]
0x1800e5a84  mov     [rsp+180h+var_120], rax
0x1800e5a89  lea     r9, asc_1802EE7AC; ": {}"
0x1800e5a90  lea     rax, [rsp+180h+var_120]
0x1800e5a95  mov     r8d, ebx
0x1800e5a98  mov     dl, 1
0x1800e5a9a  mov     [rsp+180h+var_160], rax
0x1800e5a9f  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800e5aa4  mov     edx, 0F8h
0x1800e5aa9  jmp     loc_1800E5825
0x1800e5aae  test    byte ptr [rsi+8A0h], 10h
0x1800e5ab5  jz      loc_1800E5BAB
0x1800e5abb  mov     rcx, rsi; this
0x1800e5abe  call    ?IsClientWindowsUpdate@CCbsSession@@QEBAHXZ; CCbsSession::IsClientWindowsUpdate(void)
0x1800e5ac3  test    eax, eax
0x1800e5ac5  jnz     short loc_1800E5AF2
0x1800e5ac7  mov     rcx, [rsi+288h]
0x1800e5ace  test    rcx, rcx
0x1800e5ad1  jz      loc_1800E5BAB
0x1800e5ad7  lea     rdx, aUpdateagentlcu; "UpdateAgentLCU"
0x1800e5ade  call    cs:__imp__o__wcsicmp
0x1800e5ae5  nop     dword ptr [rax+rax+00h]
0x1800e5aea  test    eax, eax
0x1800e5aec  jnz     loc_1800E5BAB
0x1800e5af2  cmp     [rsi+910h], r12b
0x1800e5af9  jz      loc_1800E5BAB
0x1800e5aff  mov     rcx, cs:?vOneSettings@@3PEAVIServicingWOSCSettings@@EA; IServicingWOSCSettings * vOneSettings
0x1800e5b06  lea     r8, [rbp+80h+var_A0]
0x1800e5b0a  lea     rdx, aEnablepriority; "ENABLEPRIORITY"
0x1800e5b11  mov     dword ptr [rbp+80h+var_A0], r12d
0x1800e5b15  mov     rax, [rcx]
0x1800e5b18  mov     rax, [rax+30h]
0x1800e5b1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5b21  mov     ecx, eax; int
0x1800e5b23  call    ?IsExpectedOneSettingsError_HRESULT@@YA_NJ@Z; IsExpectedOneSettingsError_HRESULT(long)
0x1800e5b28  mov     edi, 1
0x1800e5b2d  test    al, al
0x1800e5b2f  jnz     short loc_1800E5B41
0x1800e5b31  mov     edx, ecx
0x1800e5b33  lea     r8, aUnableToGetThe_5; "Unable to get the OneSettings value for"...
0x1800e5b3a  mov     ecx, edi
0x1800e5b3c  call    ??$TraceAtLevelIfFailed@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelIfFailed<long,>(LogAdapter::LogLevel,long,char const * const)
0x1800e5b41  mov     ecx, dword ptr [rbp+80h+var_A0]
0x1800e5b44  sub     ecx, 1
0x1800e5b47  jz      short loc_1800E5B93
0x1800e5b49  sub     ecx, 1
0x1800e5b4c  jz      short loc_1800E5B73
0x1800e5b4e  cmp     ecx, 1
0x1800e5b51  jnz     short loc_1800E5BAB
0x1800e5b53  lea     rdx, aSettingUserpre; "Setting UserPresent priority based on o"...
0x1800e5b5a  mov     ecx, edi
0x1800e5b5c  call    ??$TraceAtLevel@$$V@LogAdapter@@YAXW4LogLevel@0@QEBD@Z; LogAdapter::TraceAtLevel<>(LogAdapter::LogLevel,char const * const)
0x1800e5b61  btr     dword ptr [rsi+2B4h], 1Dh
0x1800e5b69  bts     dword ptr [rsi+2B4h], 1Ch
0x1800e5b71  jmp     short loc_1800E5BAB
0x1800e5b73  lea     rdx, aSettingUserawa; "Setting UserAway priority based on ones"...
0x1800e5b7a  mov     ecx, edi
0x1800e5b7c  call    ??$TraceAtLevel@$$V@LogAdapter@@YAXW4LogLevel@0@QEBD@Z; LogAdapter::TraceAtLevel<>(LogAdapter::LogLevel,char const * const)
0x1800e5b81  btr     dword ptr [rsi+2B4h], 1Ch
0x1800e5b89  bts     dword ptr [rsi+2B4h], 1Dh
0x1800e5b91  jmp     short loc_1800E5BAB
0x1800e5b93  lea     rdx, aSettingNormalP; "Setting Normal priority based on oneset"...
0x1800e5b9a  mov     ecx, edi
0x1800e5b9c  call    ??$TraceAtLevel@$$V@LogAdapter@@YAXW4LogLevel@0@QEBD@Z; LogAdapter::TraceAtLevel<>(LogAdapter::LogLevel,char const * const)
0x1800e5ba1  and     dword ptr [rsi+2B4h], 0CFFFFFFFh
0x1800e5bab  mov     eax, [rsi+2B4h]
0x1800e5bb1  bt      eax, 1Ch
0x1800e5bb5  jnb     short loc_1800E5BC1
0x1800e5bb7  mov     rcx, rsi; this
0x1800e5bba  call    ?SetUserPresentPriority@CCbsSession@@QEAAXXZ; CCbsSession::SetUserPresentPriority(void)
0x1800e5bbf  jmp     short loc_1800E5BF9
0x1800e5bc1  bt      eax, 1Dh
0x1800e5bc5  jnb     short loc_1800E5BD1
0x1800e5bc7  mov     rcx, rsi; this
0x1800e5bca  call    ?SetUserAwayPriority@CCbsSession@@QEAAXXZ; CCbsSession::SetUserAwayPriority(void)
0x1800e5bcf  jmp     short loc_1800E5BF9
0x1800e5bd1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Update_EcoQos@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Update_EcoQos@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Update_EcoQos> `wil::Feature<__WilFeatureTraits_Feature_Update_EcoQos>::GetImpl(void)'::`2'::impl
0x1800e5bd8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Update_EcoQos@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Update_EcoQos>::__private_IsEnabled(void)
0x1800e5bdd  test    al, al
0x1800e5bdf  jz      short loc_1800E5BF9
0x1800e5be1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Update_EcoQos@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Update_EcoQos@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Update_EcoQos> `wil::Feature<__WilFeatureTraits_Feature_Update_EcoQos>::GetImpl(void)'::`2'::impl
0x1800e5be8  call    ?__private_GetVariant@?$FeatureImpl@U__WilFeatureTraits_Feature_Update_EcoQos@@@details@wil@@QEAA?AW4Variant_Update_EcoQos@@W4VariantReportingKind@3@_N@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Update_EcoQos>::__private_GetVariant(wil::VariantReportingKind,bool)
0x1800e5bed  cmp     al, 1
0x1800e5bef  jnz     short loc_1800E5BF9
0x1800e5bf1  mov     rcx, rsi; this
0x1800e5bf4  call    ?SetNormalPriorityEcoQos@CCbsSession@@QEAAXXZ; CCbsSession::SetNormalPriorityEcoQos(void)
0x1800e5bf9  mov     eax, [rsi+2B0h]
0x1800e5bff  and     eax, 200h
0x1800e5c04  mov     [rbp+80h+var_A8], eax
0x1800e5c07  mov     eax, 0
0x1800e5c0c  setnz   r12b
0x1800e5c10  and     ebx, 80000h
0x1800e5c16  mov     [rbp+80h+var_88], r12d
0x1800e5c1a  setnz   al
0x1800e5c1d  cmp     dword ptr [rsi+2F8h], 0
0x1800e5c24  mov     [rsi+4F0h], eax
0x1800e5c2a  jz      short loc_1800E5C8F
  ... truncated ...
```
