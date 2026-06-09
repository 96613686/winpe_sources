# PackageUtil::CreateDeploymentTask(void)

- ea: `0x1800a0de4`
- end: `0x1800a14ba`
- name: `?CreateDeploymentTask@PackageUtil@@SAJXZ`
- size: `1750`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180054bd8`

## callees

- `0x18000782c`
- `0x180047228`
- `0x1800a0da4`
- `0x1800a0de4`
- `0x1800a214c`
- `0x1800cd010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800a0e18`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800a0e18`
- `OLEAUT32!__imp_VariantInit` at `0x1800a0e71`
- `OLEAUT32!__imp_VariantInit` at `0x1800a0e71`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800a0e87`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800a0e87`

## string_xrefs

- `0x1800a0e2b`: `onecore\ds\security\devicecredential\service\packageutil\packageutil.cpp`
- `0x1800a0eed`: `onecore\ds\security\devicecredential\service\packageutil\packageutil.cpp`
- `0x1800a0f42`: `onecore\ds\security\devicecredential\service\packageutil\packageutil.cpp`
- `0x1800a0fa0`: `onecore\ds\security\devicecredential\service\packageutil\packageutil.cpp`
- `0x1800a101b`: `onecore\ds\security\devicecredential\service\packageutil\packageutil.cpp`
- `0x1800a108e`: `onecore\ds\security\devicecredential\service\packageutil\packageutil.cpp`
- `0x1800a10e6`: `onecore\ds\security\devicecredential\service\packageutil\packageutil.cpp`
- `0x1800a1186`: `onecore\ds\security\devicecredential\service\packageutil\packageutil.cpp`
- `0x1800a1217`: `onecore\ds\security\devicecredential\service\packageutil\packageutil.cpp`
- `0x1800a1252`: `onecore\ds\security\devicecredential\service\packageutil\packageutil.cpp`
- `0x1800a136b`: `onecore\ds\security\devicecredential\service\packageutil\packageutil.cpp`
- `0x1800a1228`: `<Task xmlns="http://schemas.microsoft.com/windows/2004/02/mit/task">  <RegistrationInfo>    <Version>1.0</Version>    <SecurityDescriptor>D:P(A;;FA;;;BA)(A;;FA;;;SY)(A;;FRFX;;;IU)</SecurityDescriptor>  </RegistrationInfo>  <Triggers>    <SessionStateChangeTrigger>      <Enabled>true</Enabled>      <StateChange>SessionUnlock</StateChange>      <UserId>CDFAccount</UserId>    </SessionStateChangeTrigger>    <LogonTrigger>      <Enabled>true</Enabled>      <UserId>CDFAccount</UserId>    </LogonTrigg`
- `0x1800a1160`: `BackgroundTaskDeployment`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 PackageUtil::CreateDeploymentTask(void)
{
  HRESULT v0; // eax
  unsigned int v1; // ebx
  LPVOID v2; // rcx
  int v4; // eax
  LPVOID v5; // rcx
  LPVOID v6; // rcx
  void (*v7)(void); // rax
  int v8; // eax
  __int64 v9; // rcx
  LPVOID v10; // rcx
  __int64 v11; // rbx
  __int64 v12; // rcx
  int v13; // eax
  int v14; // edi
  int v15; // eax
  __int64 v16; // rcx
  __int64 v17; // rcx
  LPVOID v18; // rcx
  __int64 v19; // rbx
  __int64 v20; // rcx
  __int64 v21; // rcx
  int v22; // eax
  __int64 v23; // rcx
  __int64 v24; // rcx
  LPVOID v25; // rcx
  int v26; // eax
  __int64 v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rcx
  LPVOID v30; // rcx
  __int64 v31; // rcx
  __int64 v32; // rcx
  __int64 v33; // rcx
  LPVOID v34; // rcx
  int ppv; // [rsp+20h] [rbp-E0h]
  LPVOID *ppva; // [rsp+20h] [rbp-E0h]
  __int64 v37; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v38; // [rsp+58h] [rbp-A8h]
  __int64 v39; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v40; // [rsp+68h] [rbp-98h] BYREF
  VARIANTARG pvarg; // [rsp+70h] [rbp-90h] BYREF
  VARIANTARG v42; // [rsp+90h] [rbp-70h] BYREF
  VARIANTARG v43; // [rsp+B0h] [rbp-50h] BYREF
  VARIANTARG v44; // [rsp+D0h] [rbp-30h] BYREF
  VARIANTARG v45[2]; // [rsp+F0h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+38h]
  LPVOID v47; // [rsp+140h] [rbp+40h] BYREF
  __int64 v48; // [rsp+148h] [rbp+48h] BYREF
  __int64 v49; // [rsp+150h] [rbp+50h] BYREF
  __int64 v50; // [rsp+158h] [rbp+58h] BYREF

  v47 = 0;
  v0 = CoCreateInstance(
         &GUID_0f87369f_a4e5_4cfc_bd3e_73e6154572dd,
         0,
         1u,
         &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85,
         &v47);
  v1 = v0;
  if ( v0 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x237,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\packageutil\\packageutil.cpp",
      (const char *)(unsigned int)v0,
      ppv);
    v2 = v47;
    if ( v47 )
    {
      v47 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v2 + 16LL))(v2);
    }
    return v1;
  }
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  VariantChangeType(&pvarg, &pvarg, 0, 0);
  v45[0] = pvarg;
  v43 = pvarg;
  v44 = pvarg;
  v42 = pvarg;
  ppva = (LPVOID *)v45;
  v4 = (*(__int64 (__fastcall **)(LPVOID, VARIANTARG *, VARIANTARG *, VARIANTARG *))(*(_QWORD *)v47 + 80LL))(
         v47,
         &v42,
         &v44,
         &v43);
  v1 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x243,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\packageutil\\packageutil.cpp",
      (const char *)(unsigned int)v4,
      (int)v45);
    v5 = v47;
    if ( v47 )
    {
      v47 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v5 + 16LL))(v5);
    }
    return v1;
  }
  wil::make_bstr_nothrow(&v50, L"\\");
  if ( !v50 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x246,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\packageutil\\packageutil.cpp",
      (const char *)0x8007000ELL,
      (int)v45);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v50);
LABEL_11:
    v6 = v47;
    if ( !v47 )
      return 2147942414LL;
    v47 = 0;
    v7 = *(void (**)(void))(*(_QWORD *)v6 + 16LL);
LABEL_49:
    v7();
    return 2147942414LL;
  }
  v48 = 0;
  v8 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)v47 + 56LL))(v47, v50, &v48);
  v1 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x24A,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\packageutil\\packageutil.cpp",
      (const char *)(unsigned int)v8,
      (int)v45);
    v9 = v48;
    if ( v48 )
    {
      v48 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v50);
    v10 = v47;
    if ( v47 )
    {
      v47 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v10 + 16LL))(v10);
    }
    return v1;
  }
  wil::make_bstr_nothrow(&v37, L"\\Microsoft\\Windows\\Secondary Authentication Factor");
  v11 = v37;
  if ( !v37 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x24D,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\packageutil\\packageutil.cpp",
      (const char *)0x8007000ELL,
      (int)v45);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v37);
    v12 = v48;
    if ( v48 )
    {
      v48 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    }
LABEL_22:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v50);
    goto LABEL_11;
  }
  v49 = 0;
  v13 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v48 + 72LL))(v48, v37, &v49);
  v14 = v13;
  if ( v13 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x252,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\packageutil\\packageutil.cpp",
      (const char *)(unsigned int)v13,
      (int)v45);
  if ( v14 < 0 )
  {
    v42 = pvarg;
    v15 = (*(__int64 (__fastcall **)(__int64, __int64, VARIANTARG *, __int64 *))(*(_QWORD *)v48 + 88LL))(
            v48,
            v11,
            &v42,
            &v49);
    v1 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x257,
        (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\packageutil\\packageutil.cpp",
        (const char *)(unsigned int)v15,
        (int)ppva);
      v16 = v49;
      if ( v49 )
      {
        v49 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
      }
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v37);
      v17 = v48;
      if ( v48 )
      {
        v48 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      }
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v50);
      v18 = v47;
      if ( v47 )
      {
        v47 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v18 + 16LL))(v18);
      }
      return v1;
    }
  }
  wil::make_bstr_nothrow(&v39, L"BackgroundTaskDeployment");
  v19 = v39;
  if ( !v39 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x25B,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\packageutil\\packageutil.cpp",
      (const char *)0x8007000ELL,
      (int)ppva);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v39);
    v20 = v49;
    if ( v49 )
    {
      v49 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v37);
    v21 = v48;
    if ( v48 )
    {
      v48 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    }
    goto LABEL_22;
  }
  v22 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v49 + 120LL))(v49, v39, 0);
  if ( v22 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x25E,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\packageutil\\packageutil.cpp",
      (const char *)(unsigned int)v22,
      (int)ppva);
  wil::make_bstr_nothrow(
    &v40,
    L"<Task xmlns=\"http://schemas.microsoft.com/windows/2004/02/mit/task\">  <RegistrationInfo>    <Version>1.0</Version>"
     "    <SecurityDescriptor>D:P(A;;FA;;;BA)(A;;FA;;;SY)(A;;FRFX;;;IU)</SecurityDescriptor>  </RegistrationInfo>  <Trigg"
     "ers>    <SessionStateChangeTrigger>      <Enabled>true</Enabled>      <StateChange>SessionUnlock</StateChange>     "
     " <UserId>CDFAccount</UserId>    </SessionStateChangeTrigger>    <LogonTrigger>      <Enabled>true</Enabled>      <U"
     "serId>CDFAccount</UserId>    </LogonTrigger>  </Triggers>  <Principals>    <Principal id=\"CDFAccountContext\">    "
     "  <GroupId>S-1-5-32-545</GroupId>      <RunLevel>HighestAvailable</RunLevel>    </Principal>  </Principals>  <Setti"
     "ngs>    <MultipleInstancesPolicy>Parallel</MultipleInstancesPolicy>    <DisallowStartIfOnBatteries>false</DisallowS"
     "tartIfOnBatteries>    <StopIfGoingOnBatteries>false</StopIfGoingOnBatteries>    <AllowHardTerminate>true</AllowHard"
     "Terminate>    <StartWhenAvailable>true</StartWhenAvailable>    <RunOnlyIfNetworkAvailable>false</RunOnlyIfNetworkAv"
     "ailable>    <IdleSettings>      <StopOnIdleEnd>true</StopOnIdleEnd>      <RestartOnIdle>false</RestartOnIdle>    </"
     "IdleSettings>    <AllowStartOnDemand>true</AllowStartOnDemand>    <Enabled>true</Enabled>    <Hidden>true</Hidden> "
     "   <RunOnlyIfIdle>false</RunOnlyIfIdle>    <DisallowStartOnRemoteAppSession>true</DisallowStartOnRemoteAppSession> "
     "   <UseUnifiedSchedulingEngine>true</UseUnifiedSchedulingEngine>    <WakeToRun>false</WakeToRun>    <ExecutionTimeL"
     "imit>PT0S</ExecutionTimeLimit>    <Priority>7</Priority>  </Settings>  <Actions Context=\"CDFAccountContext\">    <"
     "Exec>      <Command>%windir%\\System32\\DeviceCredentialDeployment.exe</Command>    </Exec>  </Actions></Task>");
  if ( !v40 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x261,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\packageutil\\packageutil.cpp",
      (const char *)0x8007000ELL,
      (int)ppva);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v40);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v39);
    v23 = v49;
    if ( v49 )
    {
      v49 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v37);
    v24 = v48;
    if ( v48 )
    {
      v48 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v50);
    v25 = v47;
    if ( !v47 )
      return 2147942414LL;
    v47 = 0;
    v7 = *(void (**)(void))(*(_QWORD *)v25 + 16LL);
    goto LABEL_49;
  }
  v38 = 0;
  v42 = pvarg;
  v44 = pvarg;
  v43 = pvarg;
  v26 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64))(*(_QWORD *)v49 + 128LL))(v49, v19, v40, 6);
  v1 = v26;
  if ( v26 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x26B,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\packageutil\\packageutil.cpp",
      (const char *)(unsigned int)v26,
      (int)&v43);
    v27 = v38;
    if ( v38 )
    {
      v38 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v40);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v39);
    v28 = v49;
    if ( v49 )
    {
      v49 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v37);
    v29 = v48;
    if ( v48 )
    {
      v48 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v50);
    v30 = v47;
    if ( v47 )
    {
      v47 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v30 + 16LL))(v30);
    }
    return v1;
  }
  v31 = v38;
  if ( v38 )
  {
    v38 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v40);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v39);
  v32 = v49;
  if ( v49 )
  {
    v49 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v37);
  v33 = v48;
  if ( v48 )
  {
    v48 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v50);
  v34 = v47;
  if ( v47 )
  {
    v47 = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v34 + 16LL))(v34);
  }
  return 0;
}

```

## disassembly

```asm
0x1800a0de4  push    rbp
0x1800a0de6  push    rbx
0x1800a0de7  push    rsi
0x1800a0de8  push    rdi
0x1800a0de9  lea     rbp, [rsp-18h]
0x1800a0dee  sub     rsp, 118h
0x1800a0df5  xor     esi, esi
0x1800a0df7  mov     [rbp+30h+arg_0], rsi
0x1800a0dfb  lea     rax, [rbp+30h+arg_0]
0x1800a0dff  mov     [rsp+130h+ppv], rax; int
0x1800a0e04  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x1800a0e0b  xor     edx, edx; pUnkOuter
0x1800a0e0d  lea     r8d, [rsi+1]; dwClsContext
0x1800a0e11  lea     rcx, _GUID_0f87369f_a4e5_4cfc_bd3e_73e6154572dd; rclsid
0x1800a0e18  call    cs:__imp_CoCreateInstance
0x1800a0e1e  mov     ebx, eax
0x1800a0e20  test    eax, eax
0x1800a0e22  jns     short loc_1800A0E5E
0x1800a0e24  mov     rcx, [rbp+38h]; this
0x1800a0e28  mov     r9d, eax; char *
0x1800a0e2b  lea     r8, aOnecoreDsSecur_35; "onecore\\ds\\security\\devicecredential"...
0x1800a0e32  mov     edx, 237h; void *
0x1800a0e37  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a0e3c  nop
0x1800a0e3d  mov     rcx, [rbp+30h+arg_0]
0x1800a0e41  test    rcx, rcx
0x1800a0e44  jz      short loc_1800A0E57
0x1800a0e46  mov     [rbp+30h+arg_0], rsi
0x1800a0e4a  mov     rax, [rcx]
0x1800a0e4d  mov     rax, [rax+10h]
0x1800a0e51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a0e56  nop
0x1800a0e57  mov     eax, ebx
0x1800a0e59  jmp     loc_1800A14AE
0x1800a0e5e  xorps   xmm0, xmm0
0x1800a0e61  xor     eax, eax
0x1800a0e63  movups  xmmword ptr [rsp+130h+pvarg], xmm0
0x1800a0e68  mov     qword ptr [rbp+30h+pvarg+10h], rax
0x1800a0e6c  lea     rcx, [rsp+130h+pvarg]; pvarg
0x1800a0e71  call    cs:__imp_VariantInit
0x1800a0e77  xor     r9d, r9d; vt
0x1800a0e7a  xor     r8d, r8d; wFlags
0x1800a0e7d  lea     rdx, [rsp+130h+pvarg]; pvarSrc
0x1800a0e82  lea     rcx, [rsp+130h+pvarg]; pvargDest
0x1800a0e87  call    cs:__imp_VariantChangeType
0x1800a0e8d  mov     rcx, [rbp+30h+arg_0]
0x1800a0e91  movups  xmm1, xmmword ptr [rsp+130h+pvarg]
0x1800a0e96  movsd   xmm0, qword ptr [rbp+30h+pvarg+10h]
0x1800a0e9b  movaps  xmmword ptr [rbp+30h+var_40], xmm1
0x1800a0e9f  movsd   [rbp+30h+var_30], xmm0
0x1800a0ea4  movaps  xmmword ptr [rbp+30h+var_80], xmm1
0x1800a0ea8  movsd   [rbp+30h+var_70], xmm0
0x1800a0ead  movaps  [rbp+30h+var_60], xmm1
0x1800a0eb1  movsd   [rbp+30h+var_50], xmm0
0x1800a0eb6  movaps  [rbp+30h+var_A0], xmm1
0x1800a0eba  movsd   [rbp+30h+var_90], xmm0
0x1800a0ebf  mov     rax, [rcx]
0x1800a0ec2  lea     rdx, [rbp+30h+var_40]
0x1800a0ec6  mov     [rsp+130h+ppv], rdx; int
0x1800a0ecb  lea     r9, [rbp+30h+var_80]
0x1800a0ecf  lea     r8, [rbp+30h+var_60]
0x1800a0ed3  lea     rdx, [rbp+30h+var_A0]
0x1800a0ed7  mov     rax, [rax+50h]
0x1800a0edb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a0ee0  mov     ebx, eax
0x1800a0ee2  test    eax, eax
0x1800a0ee4  jns     short loc_1800A0F1E
0x1800a0ee6  mov     rcx, [rbp+38h]; this
0x1800a0eea  mov     r9d, eax; char *
0x1800a0eed  lea     r8, aOnecoreDsSecur_35; "onecore\\ds\\security\\devicecredential"...
0x1800a0ef4  mov     edx, 243h; void *
0x1800a0ef9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a0efe  nop
0x1800a0eff  mov     rcx, [rbp+30h+arg_0]
0x1800a0f03  test    rcx, rcx
0x1800a0f06  jz      short loc_1800A0F19
0x1800a0f08  mov     [rbp+30h+arg_0], rsi
0x1800a0f0c  mov     rax, [rcx]
0x1800a0f0f  mov     rax, [rax+10h]
0x1800a0f13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a0f18  nop
0x1800a0f19  jmp     loc_1800A0E57
0x1800a0f1e  lea     rdx, asc_1800DB4FC; "\\"
0x1800a0f25  lea     rcx, [rbp+30h+arg_18]
0x1800a0f29  call    ?make_bstr_nothrow@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr_nothrow(ushort const *)
0x1800a0f2e  nop
0x1800a0f2f  mov     rdx, [rbp+30h+arg_18]
0x1800a0f33  test    rdx, rdx
0x1800a0f36  jnz     short loc_1800A0F7B
0x1800a0f38  mov     rcx, [rbp+38h]; this
0x1800a0f3c  mov     r9d, 8007000Eh; char *
0x1800a0f42  lea     r8, aOnecoreDsSecur_35; "onecore\\ds\\security\\devicecredential"...
0x1800a0f49  mov     edx, 246h; void *
0x1800a0f4e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a0f53  nop
0x1800a0f54  lea     rcx, [rbp+30h+arg_18]
0x1800a0f58  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800a0f5d  nop
0x1800a0f5e  mov     rcx, [rbp+30h+arg_0]
0x1800a0f62  test    rcx, rcx
0x1800a0f65  jz      loc_1800A12DD
0x1800a0f6b  mov     [rbp+30h+arg_0], rsi
0x1800a0f6f  mov     rax, [rcx]
0x1800a0f72  mov     rax, [rax+10h]
0x1800a0f76  jmp     loc_1800A12D7
0x1800a0f7b  mov     [rbp+30h+arg_8], rsi
0x1800a0f7f  mov     rcx, [rbp+30h+arg_0]
0x1800a0f83  mov     rax, [rcx]
0x1800a0f86  lea     r8, [rbp+30h+arg_8]
0x1800a0f8a  mov     rax, [rax+38h]
0x1800a0f8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a0f93  mov     ebx, eax
0x1800a0f95  test    eax, eax
0x1800a0f97  jns     short loc_1800A0FF5
0x1800a0f99  mov     rcx, [rbp+38h]; this
0x1800a0f9d  mov     r9d, eax; char *
0x1800a0fa0  lea     r8, aOnecoreDsSecur_35; "onecore\\ds\\security\\devicecredential"...
0x1800a0fa7  mov     edx, 24Ah; void *
0x1800a0fac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a0fb1  nop
0x1800a0fb2  mov     rcx, [rbp+30h+arg_8]
0x1800a0fb6  test    rcx, rcx
0x1800a0fb9  jz      short loc_1800A0FCC
0x1800a0fbb  mov     [rbp+30h+arg_8], rsi
0x1800a0fbf  mov     rax, [rcx]
0x1800a0fc2  mov     rax, [rax+10h]
0x1800a0fc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a0fcb  nop
0x1800a0fcc  lea     rcx, [rbp+30h+arg_18]
0x1800a0fd0  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800a0fd5  nop
0x1800a0fd6  mov     rcx, [rbp+30h+arg_0]
0x1800a0fda  test    rcx, rcx
0x1800a0fdd  jz      short loc_1800A0FF0
0x1800a0fdf  mov     [rbp+30h+arg_0], rsi
0x1800a0fe3  mov     rax, [rcx]
0x1800a0fe6  mov     rax, [rax+10h]
0x1800a0fea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a0fef  nop
0x1800a0ff0  jmp     loc_1800A0E57
0x1800a0ff5  lea     rdx, aMicrosoftWindo; "\\Microsoft\\Windows\\Secondary Authent"...
0x1800a0ffc  lea     rcx, [rsp+130h+var_E0]
0x1800a1001  call    ?make_bstr_nothrow@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr_nothrow(ushort const *)
0x1800a1006  nop
0x1800a1007  mov     rbx, [rsp+130h+var_E0]
0x1800a100c  test    rbx, rbx
0x1800a100f  jnz     short loc_1800A1061
0x1800a1011  mov     rcx, [rbp+38h]; this
0x1800a1015  mov     r9d, 8007000Eh; char *
0x1800a101b  lea     r8, aOnecoreDsSecur_35; "onecore\\ds\\security\\devicecredential"...
0x1800a1022  mov     edx, 24Dh; void *
0x1800a1027  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a102c  nop
0x1800a102d  lea     rcx, [rsp+130h+var_E0]
0x1800a1032  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800a1037  nop
0x1800a1038  mov     rcx, [rbp+30h+arg_8]
0x1800a103c  test    rcx, rcx
0x1800a103f  jz      short loc_1800A1052
0x1800a1041  mov     [rbp+30h+arg_8], rsi
0x1800a1045  mov     rax, [rcx]
0x1800a1048  mov     rax, [rax+10h]
0x1800a104c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1051  nop
0x1800a1052  lea     rcx, [rbp+30h+arg_18]
0x1800a1056  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800a105b  nop
0x1800a105c  jmp     loc_1800A0F5E
0x1800a1061  mov     [rbp+30h+arg_10], rsi
0x1800a1065  mov     rcx, [rbp+30h+arg_8]
0x1800a1069  mov     rax, [rcx]
0x1800a106c  lea     r8, [rbp+30h+arg_10]
0x1800a1070  mov     rdx, rbx
0x1800a1073  mov     rax, [rax+48h]
0x1800a1077  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a107c  mov     edi, eax
0x1800a107e  mov     rcx, [rbp+38h]; this
0x1800a1082  mov     edx, eax
0x1800a1084  shr     edx, 1Fh
0x1800a1087  test    dl, dl
0x1800a1089  jz      short loc_1800A109F
0x1800a108b  mov     r9d, eax; char *
0x1800a108e  lea     r8, aOnecoreDsSecur_35; "onecore\\ds\\security\\devicecredential"...
0x1800a1095  mov     edx, 252h; void *
0x1800a109a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800a109f  test    edi, edi
0x1800a10a1  jns     loc_1800A1160
0x1800a10a7  mov     rcx, [rbp+30h+arg_8]
0x1800a10ab  movups  xmm0, xmmword ptr [rsp+130h+pvarg]
0x1800a10b0  movaps  [rbp+30h+var_A0], xmm0
0x1800a10b4  movsd   xmm1, qword ptr [rbp+30h+pvarg+10h]
0x1800a10b9  movsd   [rbp+30h+var_90], xmm1
0x1800a10be  mov     rax, [rcx]
0x1800a10c1  lea     r9, [rbp+30h+arg_10]
0x1800a10c5  lea     r8, [rbp+30h+var_A0]
0x1800a10c9  mov     rdx, rbx
0x1800a10cc  mov     rax, [rax+58h]
0x1800a10d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a10d5  mov     ebx, eax
0x1800a10d7  test    eax, eax
0x1800a10d9  jns     loc_1800A1160
0x1800a10df  mov     rcx, [rbp+38h]; this
0x1800a10e3  mov     r9d, eax; char *
0x1800a10e6  lea     r8, aOnecoreDsSecur_35; "onecore\\ds\\security\\devicecredential"...
0x1800a10ed  mov     edx, 257h; void *
0x1800a10f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a10f7  nop
0x1800a10f8  mov     rcx, [rbp+30h+arg_10]
0x1800a10fc  test    rcx, rcx
0x1800a10ff  jz      short loc_1800A1112
0x1800a1101  mov     [rbp+30h+arg_10], rsi
0x1800a1105  mov     rax, [rcx]
0x1800a1108  mov     rax, [rax+10h]
0x1800a110c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1111  nop
0x1800a1112  lea     rcx, [rsp+130h+var_E0]
0x1800a1117  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800a111c  nop
0x1800a111d  mov     rcx, [rbp+30h+arg_8]
0x1800a1121  test    rcx, rcx
0x1800a1124  jz      short loc_1800A1137
0x1800a1126  mov     [rbp+30h+arg_8], rsi
0x1800a112a  mov     rax, [rcx]
0x1800a112d  mov     rax, [rax+10h]
0x1800a1131  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1136  nop
0x1800a1137  lea     rcx, [rbp+30h+arg_18]
0x1800a113b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800a1140  nop
0x1800a1141  mov     rcx, [rbp+30h+arg_0]
0x1800a1145  test    rcx, rcx
0x1800a1148  jz      short loc_1800A115B
0x1800a114a  mov     [rbp+30h+arg_0], rsi
0x1800a114e  mov     rax, [rcx]
0x1800a1151  mov     rax, [rax+10h]
0x1800a1155  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a115a  nop
0x1800a115b  jmp     loc_1800A0E57
0x1800a1160  lea     rdx, aBackgroundtask; "BackgroundTaskDeployment"
0x1800a1167  lea     rcx, [rsp+130h+var_D0]
0x1800a116c  call    ?make_bstr_nothrow@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr_nothrow(ushort const *)
0x1800a1171  nop
0x1800a1172  mov     rbx, [rsp+130h+var_D0]
0x1800a1177  test    rbx, rbx
0x1800a117a  jnz     short loc_1800A11F1
0x1800a117c  mov     rcx, [rbp+38h]; this
0x1800a1180  mov     r9d, 8007000Eh; char *
0x1800a1186  lea     r8, aOnecoreDsSecur_35; "onecore\\ds\\security\\devicecredential"...
0x1800a118d  mov     edx, 25Bh; void *
0x1800a1192  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a1197  nop
0x1800a1198  lea     rcx, [rsp+130h+var_D0]
0x1800a119d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800a11a2  nop
0x1800a11a3  mov     rcx, [rbp+30h+arg_10]
0x1800a11a7  test    rcx, rcx
0x1800a11aa  jz      short loc_1800A11BD
0x1800a11ac  mov     [rbp+30h+arg_10], rsi
0x1800a11b0  mov     rax, [rcx]
0x1800a11b3  mov     rax, [rax+10h]
0x1800a11b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a11bc  nop
0x1800a11bd  lea     rcx, [rsp+130h+var_E0]
0x1800a11c2  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800a11c7  nop
0x1800a11c8  mov     rcx, [rbp+30h+arg_8]
0x1800a11cc  test    rcx, rcx
0x1800a11cf  jz      short loc_1800A11E2
0x1800a11d1  mov     [rbp+30h+arg_8], rsi
0x1800a11d5  mov     rax, [rcx]
0x1800a11d8  mov     rax, [rax+10h]
0x1800a11dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a11e1  nop
0x1800a11e2  lea     rcx, [rbp+30h+arg_18]
0x1800a11e6  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800a11eb  nop
0x1800a11ec  jmp     loc_1800A0F5E
0x1800a11f1  mov     rcx, [rbp+30h+arg_10]
0x1800a11f5  mov     rax, [rcx]
0x1800a11f8  xor     r8d, r8d
0x1800a11fb  mov     rdx, rbx
0x1800a11fe  mov     rax, [rax+78h]
0x1800a1202  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1207  mov     rcx, [rbp+38h]; this
0x1800a120b  mov     edx, eax
0x1800a120d  shr     edx, 1Fh
0x1800a1210  test    dl, dl
0x1800a1212  jz      short loc_1800A1228
0x1800a1214  mov     r9d, eax; char *
0x1800a1217  lea     r8, aOnecoreDsSecur_35; "onecore\\ds\\security\\devicecredential"...
0x1800a121e  mov     edx, 25Eh; void *
0x1800a1223  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800a1228  lea     rdx, aTaskXmlnsHttpS; "<Task xmlns=\"http://schemas.microsoft."...
0x1800a122f  lea     rcx, [rsp+130h+var_C8]
0x1800a1234  call    ?make_bstr_nothrow@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr_nothrow(ushort const *)
0x1800a1239  nop
0x1800a123a  mov     r8, [rsp+130h+var_C8]
0x1800a123f  test    r8, r8
0x1800a1242  jnz     loc_1800A12E7
0x1800a1248  mov     rcx, [rbp+38h]; this
  ... truncated ...
```
