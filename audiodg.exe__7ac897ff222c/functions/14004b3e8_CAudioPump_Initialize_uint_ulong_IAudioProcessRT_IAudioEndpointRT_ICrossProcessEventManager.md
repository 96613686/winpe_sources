# CAudioPump::Initialize(uint,ulong,IAudioProcessRT *,IAudioEndpointRT *,ICrossProcessEventManager *)

- ea: `0x14004b3e8`
- end: `0x14004baa6`
- name: `?Initialize@CAudioPump@@IEAAJIKPEAUIAudioProcessRT@@PEAUIAudioEndpointRT@@PEAUICrossProcessEventManager@@@Z`
- size: `1726`
- prototype: `__int64 __usercall@<rax>(CAudioPump *__hidden this@<rcx>, unsigned int@<edx>, unsigned int@<r8d>, struct IAudioProcessRT *@<r9>, struct IAudioEndpointRT *, struct ICrossProcessEventManager *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140070cfc`

## callees

- `0x140008124`
- `0x140009aa4`
- `0x14000a378`
- `0x14000a39c`
- `0x14000c33c`
- `0x140011ad4`
- `0x140011e00`
- `0x140016ba8`
- `0x140031a68`
- `0x140036864`
- `0x14004b3e8`
- `0x14004c130`
- `0x140070fa0`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14004b459`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14004b4c1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14004b73c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14004ba83`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14004b459`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14004b4c1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14004b73c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14004ba83`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x14004ba06`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x14004ba06`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14004b420`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14004b6df`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14004b420`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14004b6df`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14004b7f1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14004b895`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14004b7f1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14004b895`
- `ntdll!NtSetTimerResolution` at `0x14004b714`
- `ntdll!NtSetTimerResolution` at `0x14004b714`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CAudioPump::Initialize(
        CAudioPump *this,
        unsigned int a2,
        unsigned int a3,
        struct IAudioProcessRT *a4,
        struct IAudioEndpointRT *a5,
        struct ICrossProcessEventManager *a6)
{
  struct _RTL_CRITICAL_SECTION *v9; // rbx
  int event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // edi
  __int64 v12; // rdx
  struct IAudioEndpointRT *v13; // r12
  int v14; // eax
  int v15; // eax
  __int64 v16; // rax
  __int64 v17; // rdx
  signed __int32 v18; // eax
  const char *v19; // r9
  __int64 (__fastcall *v20)(CAudioPump *); // rax
  int v21; // eax
  struct ICrossProcessEventManager *v22; // r12
  __int64 (__fastcall *v23)(struct ICrossProcessEventManager *, char *); // rsi
  __int64 (__fastcall *v24)(struct ICrossProcessEventManager *, char *); // rsi
  HANDLE WaitableTimer; // rax
  const char *v26; // r9
  int pdwType; // [rsp+28h] [rbp-59h]
  __int64 *v28; // [rsp+48h] [rbp-39h] BYREF
  __int64 v29; // [rsp+50h] [rbp-31h] BYREF
  int *v30; // [rsp+58h] [rbp-29h] BYREF
  int v31; // [rsp+60h] [rbp-21h] BYREF
  DWORD pcbData; // [rsp+64h] [rbp-1Dh] BYREF
  DWORD v33; // [rsp+68h] [rbp-19h] BYREF
  int v34; // [rsp+6Ch] [rbp-15h] BYREF
  ULONG ActualResolution; // [rsp+70h] [rbp-11h] BYREF
  int v36; // [rsp+74h] [rbp-Dh]
  int **v37; // [rsp+78h] [rbp-9h] BYREF
  __int64 v38; // [rsp+80h] [rbp-1h] BYREF
  char v39; // [rsp+88h] [rbp+7h]
  struct _RTL_CRITICAL_SECTION *v40; // [rsp+90h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+D0h] [rbp+4Fh]
  unsigned int pvData; // [rsp+D8h] [rbp+57h] BYREF
  unsigned int v43; // [rsp+E8h] [rbp+67h]
  struct IAudioProcessRT *v44; // [rsp+F0h] [rbp+6Fh]

  v44 = a4;
  v43 = a3;
  v9 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 128);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 128));
  v40 = v9;
  if ( *((_BYTE *)this + 72) )
  {
    event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = -2005139440;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x68,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\audiopump.cpp",
      (const char *)0x887C0010LL,
      pdwType);
LABEL_3:
    if ( v9 )
      LeaveCriticalSection(v9);
    return (unsigned int)event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  }
  if ( (a2 & 0xFFFFFFF0) != 0 )
  {
    v12 = 107;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\audiopump.cpp",
      (const char *)0x80070057LL,
      pdwType);
    if ( v9 )
      LeaveCriticalSection(v9);
    return 2147942487LL;
  }
  if ( !a3 )
  {
    v12 = 108;
    goto LABEL_15;
  }
  if ( (a2 & 1) != 0 )
  {
    if ( (a2 & 2) != 0 )
    {
      v12 = 114;
      goto LABEL_15;
    }
  }
  else if ( (a2 & 2) == 0 )
  {
    v12 = (a2 & 1) + 112;
    goto LABEL_15;
  }
  *((_WORD *)this + 37) = 0;
  *((_QWORD *)this + 45) = 0;
  *((_QWORD *)this + 46) = 0;
  *((_WORD *)this + 2340) = 0;
  v28 = 0;
  v13 = a5;
  v14 = ((__int64 (__fastcall *)(struct IAudioEndpointRT *, GUID *, __int64 **))a5->lpVtbl->QueryInterface)(
          a5,
          &GUID_30a99515_1527_4451_af9f_00c5f0234daf,
          &v28);
  event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x82,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\audiopump.cpp",
      (const char *)(unsigned int)v14,
      pdwType);
LABEL_20:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v28);
    goto LABEL_3;
  }
  v29 = 0;
  v15 = ((__int64 (__fastcall *)(struct IAudioEndpointRT *, GUID *, __int64 *))v13->lpVtbl->QueryInterface)(
          v13,
          &GUID_d4952f5a_a0b2_4cc4_8b82_9358488dd8ac,
          &v29);
  event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x86,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\audiopump.cpp",
      (const char *)(unsigned int)v15,
      pdwType);
LABEL_23:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v29);
    goto LABEL_20;
  }
  v30 = 0;
  v16 = *v28;
  v37 = &v30;
  v38 = 0;
  v39 = 1;
  event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v16 + 24))(v28, &v38);
  wil::details::out_param_t<wistd::unique_ptr<APO_REG_PROPERTIES,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<APO_REG_PROPERTIES,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>((__int64)&v37);
  if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
  {
    v17 = 138;
LABEL_26:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\audiopump.cpp",
      (const char *)(unsigned int)event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
      pdwType);
LABEL_27:
    wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
      (void **)&v30,
      0);
    goto LABEL_23;
  }
  event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = (*(__int64 (__fastcall **)(__int64 *, char *))(*v28 + 40))(v28, (char *)this + 224);
  if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
  {
    v17 = 141;
    goto LABEL_26;
  }
  event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((__int64)this + 264, 0);
  if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
  {
    v17 = 144;
    goto LABEL_26;
  }
  event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((__int64)this + 280, 1);
  if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
  {
    v17 = 147;
    goto LABEL_26;
  }
  v31 = 0;
  v36 = a2 & 4;
  if ( (a2 & 4) != 0 && (a2 & 2) != 0 )
  {
    v31 = 1;
  }
  else
  {
    event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v29 + 40LL))(v29, &v31);
    if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
    {
      v17 = 159;
      goto LABEL_26;
    }
    if ( !v31 )
    {
      EnterCriticalSection(&CAudioPump::s_AudioPumpTimerResolutionCountLock);
      v18 = _InterlockedIncrement(&CAudioPump::s_AudioPumpTimerResolutionCount);
      *((_BYTE *)this + 73) = 1;
      if ( v18 == 1 )
      {
        ActualResolution = 0;
        if ( NtSetTimerResolution(0x2710u, 1u, &ActualResolution) < 0 )
          wil::details::in1diag3::_Log_GetLastError(
            retaddr,
            (void *)0xB9,
            (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\audiopump.cpp",
            v19);
      }
      LeaveCriticalSection(&CAudioPump::s_AudioPumpTimerResolutionCountLock);
      goto LABEL_48;
    }
  }
  event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((__int64)this + 312, 0);
  if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
  {
    v17 = 166;
    goto LABEL_26;
  }
  event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*v28 + 56))(v28, *((_QWORD *)this + 39));
  if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
  {
    v17 = 167;
    goto LABEL_26;
  }
LABEL_48:
  v20 = CAudioPump::InputPumpWorkRoutine;
  if ( (a2 & 1) == 0 )
    v20 = CAudioPump::OutputPumpWorkRoutine;
  *((_QWORD *)this + 27) = v20;
  *((_QWORD *)this + 13) = v43;
  wil::com_ptr_t<ISubmix,wil::err_returncode_policy>::operator=((char *)this + 80, v44);
  *((float *)this + 28) = (float)v30[2] / (float)*((unsigned __int16 *)v30 + 6);
  wil::com_ptr_t<ISubmix,wil::err_returncode_policy>::operator=((char *)this + 208, v13);
  pvData = 0;
  pcbData = 4;
  v33 = 0;
  if ( !RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Audio\\Parameters",
          L"AudioDGCPUPercentMax",
          0x10u,
          &v33,
          &pvData,
          &pcbData) )
  {
    v21 = pvData;
    if ( pvData >= 0xA )
    {
      if ( pvData <= 0x5A )
      {
LABEL_56:
        *((_QWORD *)this + 44) = (unsigned int)(int)(float)((float)(int)(*((_QWORD *)this + 13) * v21) / 100.0);
        goto LABEL_57;
      }
      v21 = 90;
    }
    else
    {
      v21 = 10;
    }
    pvData = v21;
    goto LABEL_56;
  }
LABEL_57:
  if ( !*((_QWORD *)this + 44) )
    *((_QWORD *)this + 44) = (unsigned int)(int)(float)((float)(int)*((_QWORD *)this + 13) * 0.40000001);
  pcbData = 4;
  if ( !RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Audio\\Parameters",
          L"DeadlineDurationThreshold",
          0x10u,
          &v33,
          &pvData,
          &pcbData) )
    *((_QWORD *)this + 55) = 10000 * pvData;
  v34 = 0;
  event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v29 + 32LL))(v29, &v34);
  if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
  {
    v17 = 253;
    goto LABEL_26;
  }
  if ( v36 && ((a2 & 1) != 0 && *((_QWORD *)this + 39) && v34 == 1 || (a2 & 2) != 0) )
  {
    v22 = a6;
    v23 = *(__int64 (__fastcall **)(struct ICrossProcessEventManager *, char *))(*(_QWORD *)a6 + 32LL);
    wil::com_ptr_t<Windows::Foundation::Collections::IVector<Windows::Media::Devices::AudioDeviceModule *>,wil::err_returncode_policy>::reset((char *)this + 408);
    event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = v23(v22, (char *)this + 408);
    if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
    {
      v17 = 264;
      goto LABEL_26;
    }
    *((_BYTE *)this + 4680) = 1;
    *((_DWORD *)this + 1189) = 1;
    if ( (a2 & 2) != 0 )
    {
      event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((__int64)this + 416, 0);
      if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
      {
        v17 = 277;
        goto LABEL_26;
      }
      event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((__int64)this + 432, 0);
      if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
      {
        v17 = 281;
        goto LABEL_26;
      }
      v24 = *(__int64 (__fastcall **)(struct ICrossProcessEventManager *, char *))(*(_QWORD *)v22 + 32LL);
      wil::com_ptr_t<Windows::Foundation::Collections::IVector<Windows::Media::Devices::AudioDeviceModule *>,wil::err_returncode_policy>::reset((char *)this + 424);
      event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = v24(v22, (char *)this + 424);
      if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
      {
        v17 = 285;
        goto LABEL_26;
      }
      event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((__int64)this + 288, 0);
      if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
      {
        v17 = 289;
        goto LABEL_26;
      }
    }
  }
  if ( CAudioPump::IsTimerRequired(this, a2) )
  {
    WaitableTimer = CreateWaitableTimerExW(0, 0, 0, 0x1F0003u);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      (char *)this + 296,
      WaitableTimer);
    if ( ((*((_QWORD *)this + 37) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0x12A, (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\audiopump.cpp", v26);
      goto LABEL_27;
    }
  }
  if ( CAudioPump::IsOffload(this) )
    _InterlockedExchange((volatile __int32 *)this + 84, 0);
  *((_BYTE *)this + 72) = 1;
  wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
    (void **)&v30,
    0);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v29);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v28);
  if ( v9 )
    LeaveCriticalSection(v9);
  return 0;
}

```

## disassembly

```asm
0x14004b3e8  mov     rax, rsp
0x14004b3eb  mov     [rax+10h], rbx
0x14004b3ef  mov     [rax+20h], r9
0x14004b3f3  mov     [rax+18h], r8d
0x14004b3f7  push    rbp
0x14004b3f8  push    rsi
0x14004b3f9  push    rdi
0x14004b3fa  push    r12
0x14004b3fc  push    r13
0x14004b3fe  push    r14
0x14004b400  push    r15
0x14004b402  lea     rbp, [rax-4Fh]
0x14004b406  sub     rsp, 90h
0x14004b40d  mov     edi, r8d
0x14004b410  mov     r13d, edx
0x14004b413  mov     r14, rcx
0x14004b416  lea     rbx, [rcx+80h]
0x14004b41d  mov     rcx, rbx; lpCriticalSection
0x14004b420  call    cs:__imp_EnterCriticalSection
0x14004b426  mov     [rbp+47h+var_38], rbx
0x14004b42a  xor     r12d, r12d
0x14004b42d  cmp     [r14+48h], r12b
0x14004b431  jz      short loc_14004B466
0x14004b433  mov     rcx, [rbp+4Fh]; this
0x14004b437  mov     edi, 887C0010h
0x14004b43c  mov     r9d, edi; char *
0x14004b43f  lea     r8, aAvcoreAudiocor_16; "avcore\\audiocore\\server\\audiodg\\exe"...
0x14004b446  lea     edx, [r12+68h]; void *
0x14004b44b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004b450  nop
0x14004b451  test    rbx, rbx
0x14004b454  jz      short loc_14004B45F
0x14004b456  mov     rcx, rbx; lpCriticalSection
0x14004b459  call    cs:__imp_LeaveCriticalSection
0x14004b45f  mov     eax, edi
0x14004b461  jmp     loc_14004BA8B
0x14004b466  test    r13d, 0FFFFFFF0h
0x14004b46d  jz      short loc_14004B476
0x14004b46f  mov     edx, 6Bh ; 'k'
0x14004b474  jmp     short loc_14004B4A2
0x14004b476  test    edi, edi
0x14004b478  jnz     short loc_14004B47F
0x14004b47a  lea     edx, [rdi+6Ch]
0x14004b47d  jmp     short loc_14004B4A2
0x14004b47f  mov     esi, r13d
0x14004b482  mov     r15d, r13d
0x14004b485  and     r15d, 2
0x14004b489  and     esi, 1
0x14004b48c  jnz     short loc_14004B498
0x14004b48e  test    r15d, r15d
0x14004b491  jnz     short loc_14004B4D1
0x14004b493  lea     edx, [rsi+70h]
0x14004b496  jmp     short loc_14004B4A2
0x14004b498  test    r15d, r15d
0x14004b49b  jz      short loc_14004B4D1
0x14004b49d  mov     edx, 72h ; 'r'; void *
0x14004b4a2  mov     r9d, 80070057h; char *
0x14004b4a8  lea     r8, aAvcoreAudiocor_16; "avcore\\audiocore\\server\\audiodg\\exe"...
0x14004b4af  mov     rcx, [rbp+4Fh]; this
0x14004b4b3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004b4b8  nop
0x14004b4b9  test    rbx, rbx
0x14004b4bc  jz      short loc_14004B4C7
0x14004b4be  mov     rcx, rbx; lpCriticalSection
0x14004b4c1  call    cs:__imp_LeaveCriticalSection
0x14004b4c7  mov     eax, 80070057h
0x14004b4cc  jmp     loc_14004BA8B
0x14004b4d1  mov     [r14+4Ah], r12w
0x14004b4d6  mov     [r14+168h], r12
0x14004b4dd  mov     [r14+170h], r12
0x14004b4e4  mov     [r14+1248h], r12w
0x14004b4ec  mov     [rbp+47h+var_80], r12
0x14004b4f0  mov     r12, [rbp+47h+arg_20]
0x14004b4f4  mov     rax, [r12]
0x14004b4f8  lea     r8, [rbp+47h+var_80]
0x14004b4fc  lea     rdx, _GUID_30a99515_1527_4451_af9f_00c5f0234daf
0x14004b503  mov     rcx, r12
0x14004b506  mov     rax, [rax]
0x14004b509  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004b50e  mov     edi, eax
0x14004b510  test    eax, eax
0x14004b512  jns     short loc_14004B53B
0x14004b514  mov     rcx, [rbp+4Fh]; this
0x14004b518  mov     r9d, eax; char *
0x14004b51b  lea     r8, aAvcoreAudiocor_16; "avcore\\audiocore\\server\\audiodg\\exe"...
0x14004b522  mov     edx, 82h; void *
0x14004b527  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004b52c  nop
0x14004b52d  lea     rcx, [rbp+47h+var_80]
0x14004b531  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14004b536  jmp     loc_14004B451
0x14004b53b  mov     [rbp+47h+var_78], 0
0x14004b543  mov     rax, [r12]
0x14004b547  lea     r8, [rbp+47h+var_78]
0x14004b54b  lea     rdx, _GUID_d4952f5a_a0b2_4cc4_8b82_9358488dd8ac
0x14004b552  mov     rcx, r12
0x14004b555  mov     rax, [rax]
0x14004b558  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004b55d  mov     edi, eax
0x14004b55f  test    eax, eax
0x14004b561  jns     short loc_14004B587
0x14004b563  mov     rcx, [rbp+4Fh]; this
0x14004b567  mov     r9d, eax; char *
0x14004b56a  lea     r8, aAvcoreAudiocor_16; "avcore\\audiocore\\server\\audiodg\\exe"...
0x14004b571  mov     edx, 86h; void *
0x14004b576  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004b57b  nop
0x14004b57c  lea     rcx, [rbp+47h+var_78]
0x14004b580  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14004b585  jmp     short loc_14004B52D
0x14004b587  mov     [rbp+47h+var_70], 0
0x14004b58f  mov     rcx, [rbp+47h+var_80]
0x14004b593  mov     rax, [rcx]
0x14004b596  lea     rdx, [rbp+47h+var_70]
0x14004b59a  mov     [rbp+47h+var_50], rdx
0x14004b59e  mov     [rbp+47h+var_48], 0
0x14004b5a6  mov     [rbp+47h+var_40], 1
0x14004b5aa  lea     rdx, [rbp+47h+var_48]
0x14004b5ae  mov     rax, [rax+18h]
0x14004b5b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004b5b7  mov     edi, eax
0x14004b5b9  lea     rcx, [rbp+47h+var_50]
0x14004b5bd  call    ??1?$out_param_t@V?$unique_ptr@UAPO_REG_PROPERTIES@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<APO_REG_PROPERTIES,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<APO_REG_PROPERTIES,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x14004b5c2  test    edi, edi
0x14004b5c4  jns     short loc_14004B5EC
0x14004b5c6  mov     edx, 8Ah; void *
0x14004b5cb  mov     rcx, [rbp+4Fh]; this
0x14004b5cf  mov     r9d, edi; char *
0x14004b5d2  lea     r8, aAvcoreAudiocor_16; "avcore\\audiocore\\server\\audiodg\\exe"...
0x14004b5d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004b5de  nop
0x14004b5df  xor     edx, edx
0x14004b5e1  lea     rcx, [rbp+47h+var_70]
0x14004b5e5  call    ?reset@?$unique_ptr@UtWAVEFORMATEX@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAUtWAVEFORMATEX@@@Z; wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(tWAVEFORMATEX *)
0x14004b5ea  jmp     short loc_14004B57C
0x14004b5ec  mov     rcx, [rbp+47h+var_80]
0x14004b5f0  mov     rax, [rcx]
0x14004b5f3  lea     rdx, [r14+0E0h]
0x14004b5fa  mov     rax, [rax+28h]
0x14004b5fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004b603  mov     edi, eax
0x14004b605  test    eax, eax
0x14004b607  jns     short loc_14004B610
0x14004b609  mov     edx, 8Dh
0x14004b60e  jmp     short loc_14004B5CB
0x14004b610  lea     rcx, [r14+108h]
0x14004b617  xor     edx, edx
0x14004b619  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x14004b61e  mov     edi, eax
0x14004b620  test    eax, eax
0x14004b622  jns     short loc_14004B62B
0x14004b624  mov     edx, 90h
0x14004b629  jmp     short loc_14004B5CB
0x14004b62b  lea     rcx, [r14+118h]
0x14004b632  mov     edx, 1
0x14004b637  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x14004b63c  mov     edi, eax
0x14004b63e  test    eax, eax
0x14004b640  jns     short loc_14004B649
0x14004b642  mov     edx, 93h
0x14004b647  jmp     short loc_14004B5CB
0x14004b649  mov     [rbp+47h+var_68], 0
0x14004b650  mov     eax, r13d
0x14004b653  and     eax, 4
0x14004b656  mov     [rbp+47h+var_54], eax
0x14004b659  jz      short loc_14004B669
0x14004b65b  test    r15d, r15d
0x14004b65e  jz      short loc_14004B669
0x14004b660  mov     [rbp+47h+var_68], 1
0x14004b667  jmp     short loc_14004B693
0x14004b669  mov     rcx, [rbp+47h+var_78]
0x14004b66d  mov     rax, [rcx]
0x14004b670  lea     rdx, [rbp+47h+var_68]
0x14004b674  mov     rax, [rax+28h]
0x14004b678  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004b67d  mov     edi, eax
0x14004b67f  test    eax, eax
0x14004b681  jns     short loc_14004B68D
0x14004b683  mov     edx, 9Fh
0x14004b688  jmp     loc_14004B5CB
0x14004b68d  cmp     [rbp+47h+var_68], 0
0x14004b691  jz      short loc_14004B6D8
0x14004b693  lea     rcx, [r14+138h]
0x14004b69a  xor     edx, edx
0x14004b69c  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x14004b6a1  mov     edi, eax
0x14004b6a3  test    eax, eax
0x14004b6a5  jns     short loc_14004B6B1
0x14004b6a7  mov     edx, 0A6h
0x14004b6ac  jmp     loc_14004B5CB
0x14004b6b1  mov     rcx, [rbp+47h+var_80]
0x14004b6b5  mov     rax, [rcx]
0x14004b6b8  mov     rdx, [r14+138h]
0x14004b6bf  mov     rax, [rax+38h]
0x14004b6c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004b6c8  mov     edi, eax
0x14004b6ca  test    eax, eax
0x14004b6cc  jns     short loc_14004B742
0x14004b6ce  mov     edx, 0A7h
0x14004b6d3  jmp     loc_14004B5CB
0x14004b6d8  lea     rcx, ?s_AudioPumpTimerResolutionCountLock@CAudioPump@@1Vcritical_section@wil@@A; lpCriticalSection
0x14004b6df  call    cs:__imp_EnterCriticalSection
0x14004b6e5  mov     eax, 1
0x14004b6ea  lock xadd cs:?s_AudioPumpTimerResolutionCount@CAudioPump@@1JA, eax; long CAudioPump::s_AudioPumpTimerResolutionCount
0x14004b6f2  inc     eax
0x14004b6f4  mov     byte ptr [r14+49h], 1
0x14004b6f9  cmp     eax, 1
0x14004b6fc  jnz     short loc_14004B735
0x14004b6fe  mov     [rbp+47h+ActualResolution], 0
0x14004b705  mov     rdi, [rbp+4Fh]
0x14004b709  lea     r8, [rbp+47h+ActualResolution]; ActualResolution
0x14004b70d  mov     dl, al; SetOrUnset
0x14004b70f  mov     ecx, 2710h; RequestedResolution
0x14004b714  call    cs:__imp_NtSetTimerResolution
0x14004b71a  shr     eax, 1Fh
0x14004b71d  test    al, al
0x14004b71f  jz      short loc_14004B735
0x14004b721  lea     r8, aAvcoreAudiocor_16; "avcore\\audiocore\\server\\audiodg\\exe"...
0x14004b728  mov     edx, 0B9h; void *
0x14004b72d  mov     rcx, rdi; this
0x14004b730  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x14004b735  lea     rcx, ?s_AudioPumpTimerResolutionCountLock@CAudioPump@@1Vcritical_section@wil@@A; lpCriticalSection
0x14004b73c  call    cs:__imp_LeaveCriticalSection
0x14004b742  lea     rax, ?InputPumpWorkRoutine@CAudioPump@@CAKPEAX@Z; CAudioPump::InputPumpWorkRoutine(void *)
0x14004b749  lea     rcx, ?OutputPumpWorkRoutine@CAudioPump@@CAKPEAX@Z; CAudioPump::OutputPumpWorkRoutine(void *)
0x14004b750  test    esi, esi
0x14004b752  cmovz   rax, rcx
0x14004b756  mov     [r14+0D8h], rax
0x14004b75d  mov     eax, [rbp+47h+arg_10]
0x14004b760  mov     [r14+68h], rax
0x14004b764  lea     rcx, [r14+50h]
0x14004b768  mov     rdx, [rbp+47h+arg_18]
0x14004b76c  call    ??4?$com_ptr_t@UISubmix@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@PEAUISubmix@@@Z; wil::com_ptr_t<ISubmix,wil::err_returncode_policy>::operator=(ISubmix *)
0x14004b771  mov     rax, [rbp+47h+var_70]
0x14004b775  mov     ecx, [rax+8]
0x14004b778  xorps   xmm1, xmm1
0x14004b77b  cvtsi2ss xmm1, rcx
0x14004b780  movzx   ecx, word ptr [rax+0Ch]
0x14004b784  movd    xmm0, ecx
0x14004b788  cvtdq2ps xmm0, xmm0
0x14004b78b  divss   xmm1, xmm0
0x14004b78f  movss   dword ptr [r14+70h], xmm1
0x14004b795  lea     rcx, [r14+0D0h]
0x14004b79c  mov     rdx, r12
0x14004b79f  call    ??4?$com_ptr_t@UISubmix@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@PEAUISubmix@@@Z; wil::com_ptr_t<ISubmix,wil::err_returncode_policy>::operator=(ISubmix *)
0x14004b7a4  mov     [rbp+47h+arg_0], 0
0x14004b7ab  mov     edi, 4
0x14004b7b0  mov     [rbp+47h+pcbData], edi
0x14004b7b3  mov     [rbp+47h+var_60], 0
0x14004b7ba  lea     rax, [rbp+47h+pcbData]
0x14004b7be  mov     [rsp+30h], rax; pcbData
0x14004b7c3  lea     rax, [rbp+47h+arg_0]
0x14004b7c7  mov     [rsp+0C0h+pvData], rax; pvData
0x14004b7cc  lea     rax, [rbp+47h+var_60]
0x14004b7d0  mov     [rsp+0C0h+pdwType], rax; pdwType
0x14004b7d5  lea     r12d, [rdi+0Ch]
0x14004b7d9  mov     r9d, r12d; dwFlags
0x14004b7dc  lea     r8, aAudiodgcpuperc; "AudioDGCPUPercentMax"
0x14004b7e3  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x14004b7ea  mov     rcx, 0FFFFFFFF80000002h; hkey
0x14004b7f1  call    cs:__imp_RegGetValueW
0x14004b7f7  test    eax, eax
0x14004b7f9  jnz     short loc_14004B838
0x14004b7fb  mov     eax, [rbp+47h+arg_0]
0x14004b7fe  cmp     eax, 0Ah
0x14004b801  jnb     short loc_14004B80A
0x14004b803  mov     eax, 0Ah
0x14004b808  jmp     short loc_14004B814
0x14004b80a  cmp     eax, 5Ah ; 'Z'
0x14004b80d  jbe     short loc_14004B817
0x14004b80f  mov     eax, 5Ah ; 'Z'
0x14004b814  mov     [rbp+47h+arg_0], eax
0x14004b817  imul    rax, [r14+68h]
0x14004b81c  xorps   xmm0, xmm0
0x14004b81f  cvtsi2ss xmm0, rax
0x14004b824  divss   xmm0, cs:__real@42c80000
0x14004b82c  cvttss2si rax, xmm0
0x14004b831  mov     [r14+160h], rax
0x14004b838  cmp     qword ptr [r14+160h], 0
0x14004b840  jnz     short loc_14004B85F
0x14004b842  xorps   xmm0, xmm0
0x14004b845  cvtsi2ss xmm0, qword ptr [r14+68h]
0x14004b84b  mulss   xmm0, cs:__real@3ecccccd
0x14004b853  cvttss2si rax, xmm0
0x14004b858  mov     [r14+160h], rax
0x14004b85f  mov     [rbp+47h+pcbData], edi
0x14004b862  lea     rax, [rbp+47h+pcbData]
0x14004b866  mov     [rsp+30h], rax; pcbData
0x14004b86b  lea     rax, [rbp+47h+arg_0]
0x14004b86f  mov     [rsp+0C0h+pvData], rax; pvData
0x14004b874  lea     rax, [rbp+47h+var_60]
0x14004b878  mov     [rsp+0C0h+pdwType], rax; pdwType
0x14004b87d  mov     r9d, r12d; dwFlags
0x14004b880  lea     r8, aDeadlinedurati; "DeadlineDurationThreshold"
0x14004b887  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x14004b88e  mov     rcx, 0FFFFFFFF80000002h; hkey
0x14004b895  call    cs:__imp_RegGetValueW
0x14004b89b  test    eax, eax
0x14004b89d  jnz     short loc_14004B8AD
0x14004b89f  imul    ecx, [rbp+47h+arg_0], 2710h
  ... truncated ...
```
