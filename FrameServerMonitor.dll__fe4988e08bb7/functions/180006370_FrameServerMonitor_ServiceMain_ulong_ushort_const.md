# FrameServerMonitor::ServiceMain(ulong,ushort * * const)

- ea: `0x180006370`
- end: `0x1800066f9`
- name: `?ServiceMain@FrameServerMonitor@@UEAAXKQEAPEAG@Z`
- size: `905`
- prototype: `void __fastcall(FrameServerMonitor *__hidden this, unsigned int, unsigned __int16 **const)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180005b70`

## callees

- `0x1800060e8`
- `0x1800060f8`
- `0x180006370`
- `0x180006a14`
- `0x180006a98`
- `0x180006ae8`
- `0x180006b84`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800064f7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800064f7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006598`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000667a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800066bb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006598`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000667a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800066bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006418`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000646d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006555`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006418`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000646d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006555`
- `api-ms-win-core-processthreads-l1-1-0!SetPriorityClass` at `0x180006405`
- `api-ms-win-core-processthreads-l1-1-0!SetPriorityClass` at `0x180006405`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18000645a`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18000645a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000644c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800064aa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000644c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800064aa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800063f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800064bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800063f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800064bb`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x1800064b3`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x1800064b3`
- `api-ms-win-core-processthreads-l1-1-0!GetPriorityClass` at `0x1800064c4`
- `api-ms-win-core-processthreads-l1-1-0!GetPriorityClass` at `0x1800064c4`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180006546`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180006546`

## pseudocode

```c
void __fastcall FrameServerMonitor::ServiceMain(FrameServerMonitor *this, unsigned int a2, unsigned __int16 **const a3)
{
  __int64 v6; // rcx
  __int64 i; // rbx
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  HANDLE CurrentThread; // rax
  signed int v11; // eax
  HANDLE v12; // rax
  int ThreadPriority; // ebx
  HANDLE v14; // rax
  DWORD PriorityClass; // eax
  int event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // ebx
  __int64 v17; // rdx
  SERVICE_STATUS_HANDLE v18; // rax
  signed int v19; // eax
  __int64 v20; // rdx

  if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 0x10u )
  {
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), 10, WPP_bdd9d25d8e093ac443a3686148e14a5a_Traceguids, v6, a2);
    for ( i = 0; (unsigned int)i < a2; i = (unsigned int)(i + 1) )
    {
      if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 8u )
        WPP_SF_qDS(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          11,
          (unsigned int)WPP_bdd9d25d8e093ac443a3686148e14a5a_Traceguids,
          (_DWORD)this,
          i,
          (__int64)a3[i]);
    }
  }
  CurrentProcess = GetCurrentProcess();
  if ( !SetPriorityClass(CurrentProcess, 0x80u) && _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      12,
      WPP_bdd9d25d8e093ac443a3686148e14a5a_Traceguids,
      this,
      LastError);
  }
  CurrentThread = GetCurrentThread();
  if ( !SetThreadPriority(CurrentThread, 2) && _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() )
  {
    v11 = GetLastError();
    if ( v11 > 0 )
      v11 = (unsigned __int16)v11 | 0x80070000;
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), 13, WPP_bdd9d25d8e093ac443a3686148e14a5a_Traceguids, this, v11);
  }
  if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 8u )
  {
    v12 = GetCurrentThread();
    ThreadPriority = GetThreadPriority(v12);
    v14 = GetCurrentProcess();
    PriorityClass = GetPriorityClass(v14);
    WPP_SF_qDD(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      14,
      WPP_bdd9d25d8e093ac443a3686148e14a5a_Traceguids,
      this,
      PriorityClass,
      ThreadPriority);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  *(_OWORD *)((char *)this + 88) = 0;
  *(_OWORD *)((char *)this + 100) = 0;
  event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((__int64)this + 64);
  if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
  {
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v17 = 15;
LABEL_40:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v17,
        WPP_bdd9d25d8e093ac443a3686148e14a5a_Traceguids,
        this,
        event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z);
      goto LABEL_41;
    }
    goto LABEL_41;
  }
  *((_DWORD *)this + 22) = 32;
  v18 = RegisterServiceCtrlHandlerExW(L"FrameServerMonitor", FrameServerMonitor::SvcHandler, this);
  *((_QWORD *)this + 10) = v18;
  if ( v18 )
  {
    event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = (*(__int64 (__fastcall **)(FrameServerMonitor *, __int64, _QWORD, __int64))(*(_QWORD *)this + 24LL))(this, 2, 0, 5000);
    if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
    {
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v17 = 17;
        goto LABEL_40;
      }
LABEL_41:
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
LABEL_42:
      (*(void (__fastcall **)(FrameServerMonitor *))(*(_QWORD *)this + 48LL))(this);
      (*(void (__fastcall **)(FrameServerMonitor *, __int64, _QWORD))(*(_QWORD *)this + 24LL))(
        this,
        1,
        (unsigned int)event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z);
      if ( !_MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() )
        return;
      v20 = 21;
      goto LABEL_47;
    }
    event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = (*(__int64 (__fastcall **)(FrameServerMonitor *, _QWORD, unsigned __int16 **const))(*(_QWORD *)this + 40LL))(this, a2, a3);
    if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
    {
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v17 = 18;
        goto LABEL_40;
      }
      goto LABEL_41;
    }
    event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = (*(__int64 (__fastcall **)(FrameServerMonitor *, __int64, _QWORD))(*(_QWORD *)this + 24LL))(this, 4, 0);
    if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
    {
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v17 = 19;
        goto LABEL_40;
      }
      goto LABEL_41;
    }
    event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = (*(__int64 (__fastcall **)(FrameServerMonitor *))(*(_QWORD *)this + 32LL))(this);
    if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
    {
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v17 = 20;
        goto LABEL_40;
      }
      goto LABEL_41;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  }
  else
  {
    v19 = GetLastError();
    event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = v19;
    if ( v19 > 0 )
      event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = (unsigned __int16)v19 | 0x80070000;
    if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        16,
        WPP_bdd9d25d8e093ac443a3686148e14a5a_Traceguids,
        this,
        event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z);
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
    if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
      goto LABEL_42;
  }
  if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() < 8u )
    return;
  v20 = 22;
LABEL_47:
  WPP_SF_qD(
    *((_QWORD *)WPP_GLOBAL_Control + 27),
    v20,
    WPP_bdd9d25d8e093ac443a3686148e14a5a_Traceguids,
    this,
    event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z);
}

```

## disassembly

```asm
0x180006370  push    rbx
0x180006372  push    rbp
0x180006373  push    rsi
0x180006374  push    rdi
0x180006375  push    r14
0x180006377  push    r15
0x180006379  sub     rsp, 38h
0x18000637d  mov     r14, r8
0x180006380  mov     ebp, edx
0x180006382  mov     rdi, rcx
0x180006385  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x18000638a  lea     r15, WPP_bdd9d25d8e093ac443a3686148e14a5a_Traceguids
0x180006391  cmp     al, 10h
0x180006393  jb      short loc_1800063F7
0x180006395  mov     r9, rcx
0x180006398  mov     [rsp+68h+var_48], ebp
0x18000639c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800063a3  mov     edx, 0Ah
0x1800063a8  mov     r8, r15
0x1800063ab  mov     rcx, [rcx+0D8h]
0x1800063b2  call    WPP_SF_qD
0x1800063b7  xor     ebx, ebx
0x1800063b9  test    ebp, ebp
0x1800063bb  jz      short loc_1800063F7
0x1800063bd  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x1800063c2  cmp     al, 8
0x1800063c4  jb      short loc_1800063F1
0x1800063c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800063cd  mov     edx, 0Bh
0x1800063d2  mov     rax, [r14+rbx*8]
0x1800063d6  mov     r9, rdi
0x1800063d9  mov     [rsp+68h+var_40], rax
0x1800063de  mov     r8, r15
0x1800063e1  mov     [rsp+68h+var_48], ebx
0x1800063e5  mov     rcx, [rcx+0D8h]
0x1800063ec  call    WPP_SF_qDS
0x1800063f1  inc     ebx
0x1800063f3  cmp     ebx, ebp
0x1800063f5  jb      short loc_1800063BD
0x1800063f7  call    cs:__imp_GetCurrentProcess
0x1800063fd  mov     rcx, rax; hProcess
0x180006400  mov     edx, 80h; dwPriorityClass
0x180006405  call    cs:__imp_SetPriorityClass
0x18000640b  test    eax, eax
0x18000640d  jnz     short loc_18000644C
0x18000640f  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180006414  cmp     al, 1
0x180006416  jb      short loc_18000644C
0x180006418  call    cs:__imp_GetLastError
0x18000641e  test    eax, eax
0x180006420  jle     short loc_18000642A
0x180006422  movzx   eax, ax
0x180006425  or      eax, 80070000h
0x18000642a  mov     rcx, cs:WPP_GLOBAL_Control
0x180006431  mov     edx, 0Ch
0x180006436  mov     r9, rdi
0x180006439  mov     [rsp+68h+var_48], eax
0x18000643d  mov     r8, r15
0x180006440  mov     rcx, [rcx+0D8h]
0x180006447  call    WPP_SF_qD
0x18000644c  call    cs:__imp_GetCurrentThread
0x180006452  mov     rcx, rax; hThread
0x180006455  mov     edx, 2; nPriority
0x18000645a  call    cs:__imp_SetThreadPriority
0x180006460  test    eax, eax
0x180006462  jnz     short loc_1800064A1
0x180006464  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180006469  cmp     al, 1
0x18000646b  jb      short loc_1800064A1
0x18000646d  call    cs:__imp_GetLastError
0x180006473  test    eax, eax
0x180006475  jle     short loc_18000647F
0x180006477  movzx   eax, ax
0x18000647a  or      eax, 80070000h
0x18000647f  mov     rcx, cs:WPP_GLOBAL_Control
0x180006486  mov     edx, 0Dh
0x18000648b  mov     r9, rdi
0x18000648e  mov     [rsp+68h+var_48], eax
0x180006492  mov     r8, r15
0x180006495  mov     rcx, [rcx+0D8h]
0x18000649c  call    WPP_SF_qD
0x1800064a1  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x1800064a6  cmp     al, 8
0x1800064a8  jb      short loc_1800064F0
0x1800064aa  call    cs:__imp_GetCurrentThread
0x1800064b0  mov     rcx, rax; hThread
0x1800064b3  call    cs:__imp_GetThreadPriority
0x1800064b9  mov     ebx, eax
0x1800064bb  call    cs:__imp_GetCurrentProcess
0x1800064c1  mov     rcx, rax; hProcess
0x1800064c4  call    cs:__imp_GetPriorityClass
0x1800064ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800064d1  mov     edx, 0Eh
0x1800064d6  mov     dword ptr [rsp+68h+var_40], ebx
0x1800064da  mov     r9, rdi
0x1800064dd  mov     r8, r15
0x1800064e0  mov     [rsp+68h+var_48], eax
0x1800064e4  mov     rcx, [rcx+0D8h]
0x1800064eb  call    WPP_SF_qDD
0x1800064f0  lea     rsi, [rdi+8]
0x1800064f4  mov     rcx, rsi; lpCriticalSection
0x1800064f7  call    cs:__imp_EnterCriticalSection
0x1800064fd  xorps   xmm0, xmm0
0x180006500  lea     rcx, [rdi+40h]
0x180006504  movups  xmmword ptr [rdi+58h], xmm0
0x180006508  movups  xmmword ptr [rdi+64h], xmm0
0x18000650c  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180006511  mov     ebx, eax
0x180006513  test    eax, eax
0x180006515  jns     short loc_18000652E
0x180006517  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18000651c  cmp     al, 1
0x18000651e  jb      loc_180006677
0x180006524  mov     edx, 0Fh
0x180006529  jmp     loc_18000665D
0x18000652e  mov     r8, rdi; lpContext
0x180006531  mov     dword ptr [rdi+58h], 20h ; ' '
0x180006538  lea     rdx, ?SvcHandler@FrameServerMonitor@@KAKKKPEAX0@Z; lpHandlerProc
0x18000653f  lea     rcx, ServiceName; "FrameServerMonitor"
0x180006546  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x18000654c  mov     [rdi+50h], rax
0x180006550  test    rax, rax
0x180006553  jnz     short loc_1800065AB
0x180006555  call    cs:__imp_GetLastError
0x18000655b  mov     ebx, eax
0x18000655d  test    eax, eax
0x18000655f  jle     short loc_18000656A
0x180006561  movzx   ebx, ax
0x180006564  or      ebx, 80070000h
0x18000656a  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x18000656f  cmp     al, 1
0x180006571  jb      short loc_180006595
0x180006573  mov     rcx, cs:WPP_GLOBAL_Control
0x18000657a  mov     edx, 10h
0x18000657f  mov     r9, rdi
0x180006582  mov     [rsp+68h+var_48], ebx
0x180006586  mov     r8, r15
0x180006589  mov     rcx, [rcx+0D8h]
0x180006590  call    WPP_SF_qD
0x180006595  mov     rcx, rsi; lpCriticalSection
0x180006598  call    cs:__imp_LeaveCriticalSection
0x18000659e  test    ebx, ebx
0x1800065a0  jns     loc_1800066C1
0x1800065a6  jmp     loc_180006680
0x1800065ab  mov     rax, [rdi]
0x1800065ae  xor     r8d, r8d
0x1800065b1  mov     r9d, 1388h
0x1800065b7  mov     rcx, rdi
0x1800065ba  mov     rax, [rax+18h]
0x1800065be  lea     edx, [r8+2]
0x1800065c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065c7  mov     ebx, eax
0x1800065c9  test    eax, eax
0x1800065cb  jns     short loc_1800065E1
0x1800065cd  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800065d2  cmp     al, 1
0x1800065d4  jb      loc_180006677
0x1800065da  mov     edx, 11h
0x1800065df  jmp     short loc_18000665D
0x1800065e1  mov     rax, [rdi]
0x1800065e4  mov     r8, r14
0x1800065e7  mov     edx, ebp
0x1800065e9  mov     rcx, rdi
0x1800065ec  mov     rax, [rax+28h]
0x1800065f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065f5  mov     ebx, eax
0x1800065f7  test    eax, eax
0x1800065f9  jns     short loc_18000660B
0x1800065fb  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180006600  cmp     al, 1
0x180006602  jb      short loc_180006677
0x180006604  mov     edx, 12h
0x180006609  jmp     short loc_18000665D
0x18000660b  mov     rax, [rdi]
0x18000660e  xor     r9d, r9d
0x180006611  xor     r8d, r8d
0x180006614  mov     rcx, rdi
0x180006617  mov     rax, [rax+18h]
0x18000661b  lea     edx, [r9+4]
0x18000661f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006624  mov     ebx, eax
0x180006626  test    eax, eax
0x180006628  jns     short loc_18000663A
0x18000662a  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18000662f  cmp     al, 1
0x180006631  jb      short loc_180006677
0x180006633  mov     edx, 13h
0x180006638  jmp     short loc_18000665D
0x18000663a  mov     rax, [rdi]
0x18000663d  mov     rcx, rdi
0x180006640  mov     rax, [rax+20h]
0x180006644  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006649  mov     ebx, eax
0x18000664b  test    eax, eax
0x18000664d  jns     short loc_1800066B8
0x18000664f  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180006654  cmp     al, 1
0x180006656  jb      short loc_180006677
0x180006658  mov     edx, 14h
0x18000665d  mov     rcx, cs:WPP_GLOBAL_Control
0x180006664  mov     r9, rdi
0x180006667  mov     r8, r15
0x18000666a  mov     [rsp+68h+var_48], ebx
0x18000666e  mov     rcx, [rcx+10h]
0x180006672  call    WPP_SF_qD
0x180006677  mov     rcx, rsi; lpCriticalSection
0x18000667a  call    cs:__imp_LeaveCriticalSection
0x180006680  mov     rax, [rdi]
0x180006683  mov     rcx, rdi
0x180006686  mov     rax, [rax+30h]
0x18000668a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000668f  mov     rax, [rdi]
0x180006692  xor     r9d, r9d
0x180006695  mov     r8d, ebx
0x180006698  mov     rcx, rdi
0x18000669b  mov     rax, [rax+18h]
0x18000669f  lea     edx, [r9+1]
0x1800066a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066a8  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x1800066ad  cmp     al, 1
0x1800066af  jb      short loc_1800066EC
0x1800066b1  mov     edx, 15h
0x1800066b6  jmp     short loc_1800066CF
0x1800066b8  mov     rcx, rsi; lpCriticalSection
0x1800066bb  call    cs:__imp_LeaveCriticalSection
0x1800066c1  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x1800066c6  cmp     al, 8
0x1800066c8  jb      short loc_1800066EC
0x1800066ca  mov     edx, 16h
0x1800066cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800066d6  mov     r9, rdi
0x1800066d9  mov     r8, r15
0x1800066dc  mov     [rsp+68h+var_48], ebx
0x1800066e0  mov     rcx, [rcx+0D8h]
0x1800066e7  call    WPP_SF_qD
0x1800066ec  add     rsp, 38h
0x1800066f0  pop     r15
0x1800066f2  pop     r14
0x1800066f4  pop     rdi
0x1800066f5  pop     rsi
0x1800066f6  pop     rbp
0x1800066f7  pop     rbx
0x1800066f8  retn
```
