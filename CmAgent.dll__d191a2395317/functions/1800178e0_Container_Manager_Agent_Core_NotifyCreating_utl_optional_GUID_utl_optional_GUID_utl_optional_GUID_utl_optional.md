# Container::Manager::Agent::Core::NotifyCreating(utl::optional<_GUID>,utl::optional<_GUID>,utl::optional<_GUID>,utl::optional<ulong>,_CMA_RUNTIME_VELOCITY_MIRRORING_INFORMATION *,_CMA_HOT_PATCH_MIRRORING_INFORMATION *,bool)

- ea: `0x1800178e0`
- end: `0x180018089`
- name: `?NotifyCreating@Core@Agent@Manager@Container@@YAJV?$optional@U_GUID@@@utl@@00V?$optional@K@6@PEAU_CMA_RUNTIME_VELOCITY_MIRRORING_INFORMATION@@PEAU_CMA_HOT_PATCH_MIRRORING_INFORMATION@@_N@Z`
- size: `1961`
- prototype: `__int64 __fastcall(__int64, _BYTE *, __int64, __int64, Container::Manager::Agent::Core *, Container::Manager::Agent::Core *, char)`
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180004c80`

## callees

- `0x180002140`
- `0x180002534`
- `0x1800045e4`
- `0x180005934`
- `0x1800059f8`
- `0x1800063e8`
- `0x180007b2c`
- `0x18000892c`
- `0x180009518`
- `0x18000970c`
- `0x180009eb8`
- `0x18000a59c`
- `0x18000a768`
- `0x18000b894`
- `0x18001666c`
- `0x1800178e0`
- `0x18001bdc0`
- `0x18001fb70`
- `0x180020000`
- `0x18002463c`
- `0x18003619c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180017f7c`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180017f7c`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180017d7d`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180017d7d`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x180017cf0`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x180017cf0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017e57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017e9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017ef0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017f33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017e57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017e9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017ef0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017f33`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017e76`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017ec7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017f0f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017f52`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017e76`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017ec7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017f0f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017f52`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017c78`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017cc3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017d33`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017d49`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017dc2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017dd1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017de7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017e0a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017e68`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017eb0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017f01`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017f44`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017f97`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017c78`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017cc3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017d33`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017d49`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017dc2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017dd1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017de7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017e0a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017e68`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017eb0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017f01`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017f44`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017f97`
- `Container.Policy.Manager!GetContainerPolicyProfile` at `0x180017b03`
- `Container.Policy.Manager!GetContainerPolicyProfile` at `0x180017b03`
- `Container.Policy.Manager!SetContainerPolicyProfile` at `0x180017b23`
- `Container.Policy.Manager!SetContainerPolicyProfile` at `0x180017b23`
- `ntdll!RtlPublishWnfStateData` at `0x180017be0`
- `ntdll!RtlPublishWnfStateData` at `0x180017be0`
- `ntdll!NtSetInformationThread` at `0x180017e35`
- `ntdll!NtSetInformationThread` at `0x180017e35`
- `ntdll!NtCreateCrossVmEvent` at `0x180017c38`
- `ntdll!NtCreateCrossVmEvent` at `0x180017c38`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017aa5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017adb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017aa5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017adb`

## string_xrefs

- `0x180017a4e`: `onecore\base\gendrv\silos\csl\lib\cslregistry.cpp`
- `0x180017a84`: `onecore\base\gendrv\silos\clem\agent\core\lib\core.cpp`
- `0x180017c52`: `onecore\base\gendrv\silos\clem\agent\core\lib\core.cpp`
- `0x180017ca8`: `onecore\base\gendrv\silos\clem\agent\core\lib\core.cpp`
- `0x180017d13`: `onecore\base\gendrv\silos\clem\agent\core\lib\core.cpp`
- `0x180017da2`: `onecore\base\gendrv\silos\clem\agent\core\lib\core.cpp`
- `0x180017fbf`: `onecore\base\gendrv\silos\clem\agent\core\lib\core.cpp`

## pseudocode

```c
__int64 __fastcall Container::Manager::Agent::Core::NotifyCreating(
        __int64 a1,
        _BYTE *a2,
        __int64 a3,
        __int64 a4,
        Container::Manager::Agent::Core *a5,
        Container::Manager::Agent::Core *a6,
        char a7)
{
  LONG v7; // edi
  char v11; // bl
  int v12; // r9d
  const struct _CMA_RUNTIME_VELOCITY_MIRRORING_INFORMATION *v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r8
  __int64 v16; // r9
  int v17; // eax
  unsigned int LastError; // ebx
  unsigned __int64 v19; // r9
  __int64 v20; // rdx
  int v21; // eax
  __int64 v22; // rdx
  int ContainerPolicyProfile; // eax
  __int64 v24; // rdx
  __int64 v25; // r9
  int v26; // eax
  struct Path *v27; // rdx
  Csl *v28; // rcx
  __int64 v29; // rax
  int CrossVmEvent; // eax
  HKEY v31; // rcx
  bool v32; // cc
  int v33; // eax
  __int64 v34; // r8
  const char *v35; // r9
  const char *v36; // r9
  char *WaitableTimer; // r14
  __int64 v38; // r8
  const char *v39; // r9
  char *Thread; // rbx
  const char *v41; // r9
  unsigned int v42; // edi
  __int64 v43; // r8
  const char *v44; // r9
  HKEY v45; // r12
  HANDLE v46; // r15
  DWORD v47; // esi
  HANDLE v48; // rsi
  DWORD v49; // r15d
  __int64 v50; // r8
  const char *v51; // r9
  HANDLE v52; // r15
  DWORD v53; // esi
  HANDLE v54; // r14
  DWORD v55; // esi
  int dwCreationFlags; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE hObject; // [rsp+48h] [rbp-B8h] BYREF
  int ThreadInformation; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v61; // [rsp+58h] [rbp-A8h] BYREF
  _WORD *v62; // [rsp+60h] [rbp-A0h]
  _WORD v63[8]; // [rsp+68h] [rbp-98h] BYREF
  __int128 Buf1; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v65[42]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+238h] [rbp+138h]
  char v67; // [rsp+25Ch] [rbp+15Ch]

  v67 = BYTE4(a4);
  v7 = a4;
  hObject = 0;
  if ( *(_QWORD *)a6 )
  {
    LODWORD(hObject) = **(_DWORD **)a6;
    BYTE4(hObject) = 1;
  }
  v11 = *((_DWORD *)a6 + 2) != 0;
  wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    (__int64)v65,
    (__int64)"NotifyCreating");
  v65[0] = &CmAgentTraceProvider::NotifyCreating::`vftable';
  LOBYTE(v12) = a5 != 0;
  CmAgentTraceProvider::NotifyCreating::StartActivity(
    (unsigned int)v65,
    a1,
    (_DWORD)a2,
    v12,
    v11,
    (__int64)&hObject,
    a7);
  if ( *(_BYTE *)(a1 + 16) )
  {
    hKey = 0;
    v17 = Csl::CreateOrOpenRegistryKey(v14, L"SYSTEM\\CurrentControlSet\\Control", v15, (char *)&hKey);
    LastError = v17;
    if ( v17 < 0 )
    {
      v19 = (unsigned int)v17;
      v20 = 609;
LABEL_15:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v20,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\agent\\core\\lib\\core.cpp",
        (const char *)v19,
        dwCreationFlags);
      if ( hKey )
        RegCloseKey(hKey);
      goto LABEL_82;
    }
    if ( !*(_BYTE *)(a1 + 16) )
      __int2c();
    v61 = v63;
    v62 = v63;
    v63[0] = 0;
    v21 = Csl::GuidToString(a1, &v61);
    LastError = v21;
    if ( v21 < 0 )
    {
      v22 = 1151;
LABEL_12:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v22,
        (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslregistry.cpp",
        (const char *)(unsigned int)v21,
        dwCreationFlags);
      if ( v61 != v63 )
        operator delete(v61, (const struct std::nothrow_t *)&std::nothrow);
      v19 = LastError;
      v20 = 611;
      goto LABEL_15;
    }
    v21 = Csl::RegistryKey::SetStringValue((Csl::RegistryKey *)&hKey, L"ContainerId", v61, v62 - v61 + 1);
    LastError = v21;
    if ( v21 < 0 )
    {
      v22 = 1153;
      goto LABEL_12;
    }
    if ( v61 != v63 )
      operator delete(v61, (const struct std::nothrow_t *)&std::nothrow);
    if ( hKey )
      RegCloseKey(hKey);
  }
  if ( a2[16] )
  {
    Buf1 = 0;
    ContainerPolicyProfile = GetContainerPolicyProfile(&Buf1);
    LastError = ContainerPolicyProfile;
    if ( ContainerPolicyProfile == -2147024894 )
    {
      if ( !a2[16] )
        __int2c();
      ContainerPolicyProfile = SetContainerPolicyProfile(a2);
      LastError = ContainerPolicyProfile;
      if ( ContainerPolicyProfile < 0 )
      {
        v24 = 625;
LABEL_80:
        v25 = (unsigned int)ContainerPolicyProfile;
        goto LABEL_81;
      }
    }
    else
    {
      if ( ContainerPolicyProfile < 0 )
      {
        v24 = 629;
        goto LABEL_80;
      }
      if ( !a2[16] )
        __int2c();
      if ( memcmp_0(&Buf1, a2, 0x10u) )
      {
        LastError = -2147024809;
        v25 = 2147942487LL;
        v24 = 635;
LABEL_81:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v24,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\agent\\core\\lib\\core.cpp",
          (const char *)v25,
          dwCreationFlags);
LABEL_82:
        v65[0] = &CmAgentTraceProvider::NotifyCreating::`vftable';
        wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v65);
        wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>((__int64)v65);
        return LastError;
      }
    }
  }
  if ( a5 )
  {
    ContainerPolicyProfile = Container::Manager::Agent::Core::UpdateRuntimeFeatureConfigurations(a5, v13, v15, v16);
    LastError = ContainerPolicyProfile;
    if ( ContainerPolicyProfile < 0 )
    {
      v24 = 643;
      goto LABEL_80;
    }
  }
  if ( *((_DWORD *)a6 + 2) )
  {
    ContainerPolicyProfile = Container::Manager::Agent::Core::UpdateHotPatches(a6, v13, v15, v16);
    LastError = ContainerPolicyProfile;
    if ( ContainerPolicyProfile < 0 )
    {
      v24 = 649;
      goto LABEL_80;
    }
  }
  dword_18004B950 = 1;
  dwCreationFlags = 0;
  v26 = RtlPublishWnfStateData(WNF_CONT_CONTAINER_STATE, 0, &dword_18004B950, 4);
  LastError = v26 | 0x10000000;
  if ( v26 < 0 )
  {
    v25 = LastError;
    v24 = 657;
    goto LABEL_81;
  }
  if ( *(_BYTE *)(a3 + 16) )
  {
    hKey = 0;
    v29 = wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator&(&hKey);
    CrossVmEvent = NtCreateCrossVmEvent(v29, 2031619, 0, 0);
    if ( CrossVmEvent < 0 )
    {
      LastError = wil::details::in1diag3::Return_NtStatus(
                    retaddr,
                    (void *)0x2A2,
                    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\agent\\core\\lib\\core.cpp",
                    (const char *)(unsigned int)CrossVmEvent,
                    a3);
      v31 = hKey;
      v32 = (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL;
      goto LABEL_44;
    }
    hObject = 0;
    v33 = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(&hObject);
    LastError = v33;
    if ( v33 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2A6,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\agent\\core\\lib\\core.cpp",
        (const char *)(unsigned int)v33,
        a3);
      if ( hObject && !CloseHandle(hObject) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v34, v35);
LABEL_49:
      v31 = hKey;
      v32 = (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL;
LABEL_44:
      if ( v32 )
        CloseHandle(v31);
      goto LABEL_82;
    }
    WaitableTimer = (char *)CreateWaitableTimerExW(0, 0, 0, 0x1F0003u);
    if ( ((unsigned __int64)(WaitableTimer + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x2AD,
                    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\agent\\core\\lib\\core.cpp",
                    v36);
      if ( (unsigned __int64)(WaitableTimer - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(WaitableTimer);
      if ( hObject && !CloseHandle(hObject) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v38, v39);
      goto LABEL_49;
    }
    Thread = (char *)CreateThread(
                       0,
                       0,
                       Container::Manager::Agent::Core::_anonymous_namespace_::HeartbeatThread,
                       0,
                       4u,
                       0);
    if ( ((unsigned __int64)(Thread + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      v42 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x2B6,
              (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\agent\\core\\lib\\core.cpp",
              v41);
      if ( (unsigned __int64)(Thread - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(Thread);
      CloseHandle(WaitableTimer);
      if ( hObject && !CloseHandle(hObject) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v43, v44);
      if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(hKey);
      LastError = v42;
      goto LABEL_82;
    }
    ThreadInformation = 12;
    NtSetInformationThread(Thread, ThreadActualBasePriority, &ThreadInformation, 4u);
    v45 = hKey;
    v46 = EventHandle;
    if ( (char *)EventHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      v47 = GetLastError();
      CloseHandle(v46);
      SetLastError(v47);
    }
    EventHandle = v45;
    hKey = 0;
    v48 = qword_18004B938;
    if ( qword_18004B938 )
    {
      v49 = GetLastError();
      if ( !CloseHandle(v48) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v50, v51);
      SetLastError(v49);
    }
    qword_18004B938 = hObject;
    v52 = hTimer;
    if ( (char *)hTimer - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      v53 = GetLastError();
      CloseHandle(v52);
      SetLastError(v53);
    }
    hTimer = WaitableTimer;
    v54 = ::hObject;
    if ( (char *)::hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      v55 = GetLastError();
      CloseHandle(v54);
      SetLastError(v55);
    }
    ::hObject = Thread;
    if ( !v67 )
      __int2c();
    lPeriod = v7;
    ResumeThread(Thread);
    v28 = (Csl *)hKey;
    if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(hKey);
  }
  if ( a7 )
  {
    ContainerPolicyProfile = Csl::ExpandSystemVolume(v28, v27);
    LastError = ContainerPolicyProfile;
    if ( ContainerPolicyProfile < 0 )
    {
      v24 = 718;
      goto LABEL_80;
    }
  }
  wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
    v65,
    0);
  v65[0] = &CmAgentTraceProvider::NotifyCreating::`vftable';
  wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v65);
  wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>((__int64)v65);
  return 0;
}

```

## disassembly

```asm
0x1800178e0  mov     [rsp-8+arg_18], r9
0x1800178e5  push    rbp
0x1800178e6  push    rbx
0x1800178e7  push    rsi
0x1800178e8  push    rdi
0x1800178e9  push    r12
0x1800178eb  push    r13
0x1800178ed  push    r14
0x1800178ef  push    r15
0x1800178f1  lea     rbp, [rsp-0F8h]
0x1800178f9  sub     rsp, 1F8h
0x180017900  mov     rax, cs:__security_cookie
0x180017907  xor     rax, rsp
0x18001790a  mov     [rbp+130h+var_50], rax
0x180017911  mov     rdi, r9
0x180017914  mov     r13, r8
0x180017917  mov     rsi, rdx
0x18001791a  mov     r14, rcx
0x18001791d  mov     r15, [rbp+130h+arg_28]
0x180017924  mov     r12, [rbp+130h+arg_20]
0x18001792b  mov     [rsp+230h+hObject], 0
0x180017934  mov     rax, [r15]
0x180017937  test    rax, rax
0x18001793a  jz      short loc_180017951
0x18001793c  mov     eax, [rax]
0x18001793e  mov     dword ptr [rsp+230h+hObject], eax
0x180017942  mov     byte ptr [rsp+230h+hObject+4], 1
0x180017947  mov     rax, [rsp+230h+hObject]
0x18001794c  mov     [rsp+230h+hObject], rax
0x180017951  cmp     dword ptr [r15+8], 0
0x180017956  setnz   bl
0x180017959  lea     rdx, aNotifycreating; "NotifyCreating"
0x180017960  lea     rcx, [rbp+130h+var_1A0]
0x180017964  call    ??0?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180017969  lea     rax, ??_7NotifyCreating@CmAgentTraceProvider@@6B@; const CmAgentTraceProvider::NotifyCreating::`vftable'
0x180017970  mov     [rbp+130h+var_1A0], rax
0x180017974  test    r12, r12
0x180017977  setnz   r9b
0x18001797b  mov     al, [rbp+130h+arg_30]
0x180017981  mov     [rsp+230h+var_200], al
0x180017985  lea     rax, [rsp+230h+hObject]
0x18001798a  mov     [rsp+230h+lpThreadId], rax
0x18001798f  mov     byte ptr [rsp+230h+dwCreationFlags], bl; int
0x180017993  mov     r8, rsi
0x180017996  mov     rdx, r14
0x180017999  lea     rcx, [rbp+130h+var_1A0]
0x18001799d  call    ?StartActivity@NotifyCreating@CmAgentTraceProvider@@QEAAXAEBV?$optional@U_GUID@@@utl@@0_N1AEBV?$optional@K@4@1@Z; CmAgentTraceProvider::NotifyCreating::StartActivity(utl::optional<_GUID> const &,utl::optional<_GUID> const &,bool,bool,utl::optional<ulong> const &,bool)
0x1800179a2  nop
0x1800179a3  cmp     byte ptr [r14+10h], 0
0x1800179a8  jz      loc_180017AE9
0x1800179ae  mov     [rsp+230h+hKey], 0
0x1800179b7  lea     r9, [rsp+230h+hKey]
0x1800179bc  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Control"
0x1800179c3  call    ?CreateOrOpenRegistryKey@Csl@@YAJPEAUHKEY__@@PEBGW4RegistryKeyAccess@1@AEAVRegistryKey@1@@Z; Csl::CreateOrOpenRegistryKey(HKEY__ *,ushort const *,Csl::RegistryKeyAccess,Csl::RegistryKey &)
0x1800179c8  mov     ebx, eax
0x1800179ca  test    eax, eax
0x1800179cc  jns     short loc_1800179DB
0x1800179ce  mov     r9d, eax
0x1800179d1  mov     edx, 261h
0x1800179d6  jmp     loc_180017A84
0x1800179db  cmp     byte ptr [r14+10h], 0
0x1800179e0  jnz     short loc_1800179E4
0x1800179e2  int     2Ch; Windows NT - assertion failure
0x1800179e4  lea     rax, [rsp+230h+var_1C8]
0x1800179e9  mov     [rsp+230h+var_1D8], rax
0x1800179ee  lea     rax, [rsp+230h+var_1C8]
0x1800179f3  mov     [rsp+230h+var_1D0], rax
0x1800179f8  xor     eax, eax
0x1800179fa  mov     [rsp+230h+var_1C8], ax
0x1800179ff  lea     rdx, [rsp+230h+var_1D8]
0x180017a04  mov     rcx, r14
0x180017a07  call    ?GuidToString@Csl@@YAJAEBU_GUID@@AEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; Csl::GuidToString(_GUID const &,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x180017a0c  mov     ebx, eax
0x180017a0e  xor     r14d, r14d
0x180017a11  test    eax, eax
0x180017a13  jns     short loc_180017A1C
0x180017a15  mov     edx, 47Fh
0x180017a1a  jmp     short loc_180017A4B
0x180017a1c  mov     r8, [rsp+230h+var_1D8]; unsigned __int16 *
0x180017a21  mov     r9, [rsp+230h+var_1D0]
0x180017a26  sub     r9, r8
0x180017a29  sar     r9, 1
0x180017a2c  inc     r9d; unsigned int
0x180017a2f  lea     rdx, Value; "ContainerId"
0x180017a36  lea     rcx, [rsp+230h+hKey]; this
0x180017a3b  call    ?SetStringValue@RegistryKey@Csl@@QEAAJPEBG0K@Z; Csl::RegistryKey::SetStringValue(ushort const *,ushort const *,ulong)
0x180017a40  mov     ebx, eax
0x180017a42  test    eax, eax
0x180017a44  jns     short loc_180017AB6
0x180017a46  mov     edx, 481h; void *
0x180017a4b  mov     r9d, eax; char *
0x180017a4e  lea     r8, aOnecoreBaseGen_13; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x180017a55  mov     rcx, [rbp+138h]; this
0x180017a5c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017a61  lea     rax, [rsp+230h+var_1C8]
0x180017a66  mov     rcx, [rsp+230h+var_1D8]; void *
0x180017a6b  cmp     rcx, rax
0x180017a6e  jz      short loc_180017A7C
0x180017a70  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180017a77  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180017a7c  mov     r9d, ebx; char *
0x180017a7f  mov     edx, 263h; void *
0x180017a84  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x180017a8b  mov     rcx, [rbp+138h]; this
0x180017a92  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017a97  mov     rcx, [rsp+230h+hKey]; hKey
0x180017a9c  test    rcx, rcx
0x180017a9f  jz      loc_180017FD2
0x180017aa5  call    cs:__imp_RegCloseKey
0x180017aac  nop     dword ptr [rax+rax+00h]
0x180017ab1  jmp     loc_180017FD2
0x180017ab6  lea     rax, [rsp+230h+var_1C8]
0x180017abb  mov     rcx, [rsp+230h+var_1D8]; void *
0x180017ac0  cmp     rcx, rax
0x180017ac3  jz      short loc_180017AD1
0x180017ac5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180017acc  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180017ad1  mov     rcx, [rsp+230h+hKey]; hKey
0x180017ad6  test    rcx, rcx
0x180017ad9  jz      short loc_180017AEC
0x180017adb  call    cs:__imp_RegCloseKey
0x180017ae2  nop     dword ptr [rax+rax+00h]
0x180017ae7  jmp     short loc_180017AEC
0x180017ae9  xor     r14d, r14d
0x180017aec  cmp     [rsi+10h], r14b
0x180017af0  jz      loc_180017B7E
0x180017af6  xorps   xmm0, xmm0
0x180017af9  movups  [rsp+230h+Buf1], xmm0
0x180017afe  lea     rcx, [rsp+230h+Buf1]
0x180017b03  call    cs:__imp_GetContainerPolicyProfile
0x180017b0a  nop     dword ptr [rax+rax+00h]
0x180017b0f  mov     ebx, eax
0x180017b11  cmp     eax, 80070002h
0x180017b16  jnz     short loc_180017B3F
0x180017b18  cmp     [rsi+10h], r14b
0x180017b1c  jnz     short loc_180017B20
0x180017b1e  int     2Ch; Windows NT - assertion failure
0x180017b20  mov     rcx, rsi
0x180017b23  call    cs:__imp_SetContainerPolicyProfile
0x180017b2a  nop     dword ptr [rax+rax+00h]
0x180017b2f  mov     ebx, eax
0x180017b31  test    eax, eax
0x180017b33  jns     short loc_180017B7E
0x180017b35  mov     edx, 271h
0x180017b3a  jmp     loc_180017FBC
0x180017b3f  test    eax, eax
0x180017b41  jns     short loc_180017B4D
0x180017b43  mov     edx, 275h
0x180017b48  jmp     loc_180017FBC
0x180017b4d  cmp     [rsi+10h], r14b
0x180017b51  jnz     short loc_180017B55
0x180017b53  int     2Ch; Windows NT - assertion failure
0x180017b55  mov     r8d, 10h; Size
0x180017b5b  mov     rdx, rsi; Buf2
0x180017b5e  lea     rcx, [rsp+230h+Buf1]; Buf1
0x180017b63  call    memcmp_0
0x180017b68  test    eax, eax
0x180017b6a  jz      short loc_180017B7E
0x180017b6c  mov     ebx, 80070057h
0x180017b71  mov     r9d, ebx
0x180017b74  mov     edx, 27Bh
0x180017b79  jmp     loc_180017FBF
0x180017b7e  test    r12, r12
0x180017b81  jz      short loc_180017B9B
0x180017b83  mov     rcx, r12; this
0x180017b86  call    ?UpdateRuntimeFeatureConfigurations@Core@Agent@Manager@Container@@YAJAEBU_CMA_RUNTIME_VELOCITY_MIRRORING_INFORMATION@@@Z; Container::Manager::Agent::Core::UpdateRuntimeFeatureConfigurations(_CMA_RUNTIME_VELOCITY_MIRRORING_INFORMATION const &)
0x180017b8b  mov     ebx, eax
0x180017b8d  test    eax, eax
0x180017b8f  jns     short loc_180017B9B
0x180017b91  mov     edx, 283h
0x180017b96  jmp     loc_180017FBC
0x180017b9b  cmp     [r15+8], r14d
0x180017b9f  jz      short loc_180017BB9
0x180017ba1  mov     rcx, r15; this
0x180017ba4  call    ?UpdateHotPatches@Core@Agent@Manager@Container@@YAJAEAU_CMA_HOT_PATCH_MIRRORING_INFORMATION@@@Z; Container::Manager::Agent::Core::UpdateHotPatches(_CMA_HOT_PATCH_MIRRORING_INFORMATION &)
0x180017ba9  mov     ebx, eax
0x180017bab  test    eax, eax
0x180017bad  jns     short loc_180017BB9
0x180017baf  mov     edx, 289h
0x180017bb4  jmp     loc_180017FBC
0x180017bb9  mov     cs:dword_18004B950, 1
0x180017bc3  mov     qword ptr [rsp+230h+dwCreationFlags], r14
0x180017bc8  mov     esi, 4
0x180017bcd  mov     r9d, esi
0x180017bd0  lea     r8, dword_18004B950
0x180017bd7  xor     edx, edx
0x180017bd9  mov     rcx, cs:WNF_CONT_CONTAINER_STATE
0x180017be0  call    cs:__imp_RtlPublishWnfStateData
0x180017be7  nop     dword ptr [rax+rax+00h]
0x180017bec  mov     ebx, eax
0x180017bee  or      ebx, 10000000h
0x180017bf4  jge     short loc_180017C03
0x180017bf6  mov     r9d, ebx
0x180017bf9  mov     edx, 291h
0x180017bfe  jmp     loc_180017FBF
0x180017c03  cmp     [r13+10h], r14b
0x180017c07  jz      loc_180017FA3
0x180017c0d  mov     [rsp+230h+hKey], r14
0x180017c12  lea     rcx, [rsp+230h+hKey]
0x180017c17  call    ??I?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator&(void)
0x180017c1c  mov     [rsp+230h+lpThreadId], r14
0x180017c21  mov     qword ptr [rsp+230h+dwCreationFlags], r13; int
0x180017c26  xor     r9d, r9d
0x180017c29  xor     r8d, r8d
0x180017c2c  mov     r15d, 1F0003h
0x180017c32  mov     edx, r15d
0x180017c35  mov     rcx, rax
0x180017c38  call    cs:__imp_NtCreateCrossVmEvent
0x180017c3f  nop     dword ptr [rax+rax+00h]
0x180017c44  test    eax, eax
0x180017c46  jns     short loc_180017C89
0x180017c48  mov     rcx, [rbp+138h]; this
0x180017c4f  mov     r9d, eax; char *
0x180017c52  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x180017c59  mov     edx, 2A2h; void *
0x180017c5e  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180017c63  mov     ebx, eax
0x180017c65  mov     rcx, [rsp+230h+hKey]; hObject
0x180017c6a  lea     rdx, [rcx-1]
0x180017c6e  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180017c72  ja      loc_180017FD2
0x180017c78  call    cs:__imp_CloseHandle
0x180017c7f  nop     dword ptr [rax+rax+00h]
0x180017c84  jmp     loc_180017FD2
0x180017c89  mov     [rsp+230h+hObject], r14
0x180017c8e  lea     rcx, [rsp+230h+hObject]
0x180017c93  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180017c98  mov     ebx, eax
0x180017c9a  test    eax, eax
0x180017c9c  jns     short loc_180017CE6
0x180017c9e  mov     rcx, [rbp+138h]; this
0x180017ca5  mov     r9d, eax; char *
0x180017ca8  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x180017caf  mov     edx, 2A6h; void *
0x180017cb4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017cb9  mov     rcx, [rsp+230h+hObject]; hObject
0x180017cbe  test    rcx, rcx
0x180017cc1  jz      short loc_180017CD7
0x180017cc3  call    cs:__imp_CloseHandle
0x180017cca  nop     dword ptr [rax+rax+00h]
0x180017ccf  test    eax, eax
0x180017cd1  jz      loc_180018065
0x180017cd7  mov     rcx, [rsp+230h+hKey]
0x180017cdc  lea     rax, [rcx-1]
0x180017ce0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180017ce4  jmp     short loc_180017C72
0x180017ce6  mov     r9d, r15d; dwDesiredAccess
0x180017ce9  xor     r8d, r8d; dwFlags
0x180017cec  xor     edx, edx; lpTimerName
0x180017cee  xor     ecx, ecx; lpTimerAttributes
0x180017cf0  call    cs:__imp_CreateWaitableTimerExW
0x180017cf7  nop     dword ptr [rax+rax+00h]
0x180017cfc  mov     r14, rax
0x180017cff  lea     rcx, [rax+1]
0x180017d03  test    rcx, 0FFFFFFFFFFFFFFFEh
0x180017d0a  jnz     short loc_180017D62
0x180017d0c  mov     rcx, [rbp+138h]; this
0x180017d13  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x180017d1a  mov     edx, 2ADh; void *
0x180017d1f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180017d24  mov     ebx, eax
0x180017d26  lea     rcx, [r14-1]
0x180017d2a  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180017d2e  ja      short loc_180017D3F
0x180017d30  mov     rcx, r14; hObject
0x180017d33  call    cs:__imp_CloseHandle
0x180017d3a  nop     dword ptr [rax+rax+00h]
0x180017d3f  mov     rcx, [rsp+230h+hObject]; hObject
0x180017d44  test    rcx, rcx
0x180017d47  jz      short loc_180017CD7
0x180017d49  call    cs:__imp_CloseHandle
0x180017d50  nop     dword ptr [rax+rax+00h]
0x180017d55  test    eax, eax
0x180017d57  jz      loc_180018053
0x180017d5d  jmp     loc_180017CD7
0x180017d62  mov     [rsp+230h+lpThreadId], 0; lpThreadId
0x180017d6b  mov     [rsp+230h+dwCreationFlags], esi; int
0x180017d6f  xor     r9d, r9d; lpParameter
0x180017d72  lea     r8, Container__Manager__Agent__Core___anonymous_namespace___HeartbeatThread; lpStartAddress
0x180017d79  xor     edx, edx; dwStackSize
0x180017d7b  xor     ecx, ecx; lpThreadAttributes
0x180017d7d  call    cs:__imp_CreateThread
0x180017d84  nop     dword ptr [rax+rax+00h]
0x180017d89  mov     rbx, rax
0x180017d8c  inc     rax
0x180017d8f  test    rax, 0FFFFFFFFFFFFFFFEh
0x180017d95  jnz     loc_180017E1D
0x180017d9b  mov     rcx, [rbp+138h]; this
0x180017da2  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x180017da9  mov     edx, 2B6h; void *
0x180017dae  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180017db3  mov     edi, eax
0x180017db5  lea     rcx, [rbx-1]
0x180017db9  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180017dbd  ja      short loc_180017DCE
0x180017dbf  mov     rcx, rbx; hObject
0x180017dc2  call    cs:__imp_CloseHandle
0x180017dc9  nop     dword ptr [rax+rax+00h]
0x180017dce  mov     rcx, r14; hObject
0x180017dd1  call    cs:__imp_CloseHandle
  ... truncated ...
```
