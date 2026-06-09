# EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager::AutoPilotAsyncAction::LaunchWorker(void)

- ea: `0x1800d3408`
- end: `0x1800d3653`
- name: `?LaunchWorker@AutoPilotAsyncAction@AutoPilotManager@AutoPilot@Service@EnterpriseDeviceManagement@@QEAAJXZ`
- size: `587`
- prototype: `__int64 __fastcall(EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager::AutoPilotAsyncAction *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800d52a4`

## callees

- `0x180067a34`
- `0x180067a54`
- `0x1800a0434`
- `0x1800d30f0`
- `0x1800d3408`
- `0x1801759bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800d34dd`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800d34dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d34b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d3538`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d358e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d35e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d3623`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d34b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d3538`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d358e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d35e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d3623`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800d34ce`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800d3556`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800d35ac`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800d3604`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800d3641`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800d34ce`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800d3556`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800d35ac`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800d3604`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800d3641`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800d3467`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800d3467`

## string_xrefs

- `0x1800d3430`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\autopilotmanager.cpp`
- `0x1800d3485`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\autopilotmanager.cpp`
- `0x1800d34f6`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\autopilotmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager::AutoPilotAsyncAction::LaunchWorker(
        EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager::AutoPilotAsyncAction *this)
{
  HANDLE *v2; // rdi
  int event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  DWORD LastError; // ebx
  const char *v6; // r9
  const char *v7; // r9
  wil::details::in1diag3 *v8; // rcx
  const char *v9; // r8
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  DWORD dwCreationFlags; // [rsp+20h] [rbp-28h]
  DWORD dwCreationFlagsa; // [rsp+20h] [rbp-28h]
  void **v16; // [rsp+30h] [rbp-18h] BYREF
  HANDLE Thread; // [rsp+38h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+20h]

  v2 = (HANDLE *)((char *)this + 32);
  event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((char *)this + 32);
  LastError = event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x11E,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\lib\\autopilotmanager.cpp",
      (const char *)(unsigned int)event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
      dwCreationFlags);
    return LastError;
  }
  v16 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
  Thread = CreateThread(
             0,
             0,
             (LPTHREAD_START_ROUTINE)EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager::AutoPilotAsyncAction::AsyncThreadProc,
             this,
             0,
             0);
  if ( !Thread )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x123,
                  (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\lib\\autopilotmanager.cpp",
                  v6);
    v16 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
    return LastError;
  }
  LastError = WaitForSingleObject(*v2, 0xEA60u);
  if ( LastError )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
    v8 = retaddr;
    v9 = "onecoreuap\\admin\\moderndeployment\\autopilot\\service\\lib\\autopilotmanager.cpp";
    if ( LastError == 258 )
    {
      LastError = -2147023436;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x12B,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\lib\\autopilotmanager.cpp",
        (const char *)0x800705B4LL,
        dwCreationFlagsa);
      v16 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
      if ( !Thread
        || (unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(&v16) )
      {
        return LastError;
      }
      v10 = GetLastError();
      if ( v10 > 0 )
        v10 = (unsigned __int16)v10 | 0x80070000;
      RaiseException(v10, 1u, 0, 0);
    }
    if ( LastError == -1 )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(v8, (void *)0x12C, (unsigned int)v9, v7);
      v16 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
      if ( !Thread
        || (unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(&v16) )
      {
        return LastError;
      }
      v11 = GetLastError();
      if ( v11 > 0 )
        v11 = (unsigned __int16)v11 | 0x80070000;
      RaiseException(v11, 1u, 0, 0);
    }
    LastError = -2147418113;
    wil::details::in1diag3::Return_Hr(v8, (void *)0x12D, (unsigned int)v9, (const char *)0x8000FFFFLL, dwCreationFlagsa);
    v16 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
    if ( Thread
      && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(&v16) )
    {
      v12 = GetLastError();
      if ( v12 > 0 )
        v12 = (unsigned __int16)v12 | 0x80070000;
      RaiseException(v12, 1u, 0, 0);
      __debugbreak();
    }
    return LastError;
  }
  v16 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
  if ( Thread
    && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(&v16) )
  {
    v13 = GetLastError();
    if ( v13 > 0 )
      v13 = (unsigned __int16)v13 | 0x80070000;
    RaiseException(v13, 1u, 0, 0);
    __debugbreak();
  }
  return 0;
}

```

## disassembly

```asm
0x1800d3408  push    rbp
0x1800d340a  push    rbx
0x1800d340b  push    rsi
0x1800d340c  push    rdi
0x1800d340d  mov     rbp, rsp
0x1800d3410  sub     rsp, 48h
0x1800d3414  mov     rsi, rcx
0x1800d3417  lea     rdi, [rcx+20h]
0x1800d341b  mov     rcx, rdi
0x1800d341e  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800d3423  mov     ebx, eax
0x1800d3425  test    eax, eax
0x1800d3427  jns     short loc_1800D3448
0x1800d3429  mov     rcx, [rbp+20h]; this
0x1800d342d  mov     r9d, eax; char *
0x1800d3430  lea     r8, aOnecoreuapAdmi_111; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800d3437  mov     edx, 11Eh; void *
0x1800d343c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d3441  mov     eax, ebx
0x1800d3443  jmp     loc_1800D364A
0x1800d3448  mov     [rsp+48h+lpThreadId], 0; lpThreadId
0x1800d3451  mov     [rsp+48h+dwCreationFlags], 0; int
0x1800d3459  mov     r9, rsi; lpParameter
0x1800d345c  lea     r8, ?AsyncThreadProc@AutoPilotAsyncAction@AutoPilotManager@AutoPilot@Service@EnterpriseDeviceManagement@@CAKPEAX@Z; lpStartAddress
0x1800d3463  xor     edx, edx; dwStackSize
0x1800d3465  xor     ecx, ecx; lpThreadAttributes
0x1800d3467  call    cs:__imp_CreateThread
0x1800d346d  lea     rsi, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x1800d3474  mov     [rbp+var_18], rsi
0x1800d3478  mov     [rbp+var_10], rax
0x1800d347c  test    rax, rax
0x1800d347f  jnz     short loc_1800D34D5
0x1800d3481  mov     rcx, [rbp+20h]; this
0x1800d3485  lea     r8, aOnecoreuapAdmi_111; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800d348c  mov     edx, 123h; void *
0x1800d3491  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800d3496  mov     ebx, eax
0x1800d3498  mov     [rbp+var_18], rsi
0x1800d349c  cmp     [rbp+var_10], 0
0x1800d34a1  jz      short loc_1800D3441
0x1800d34a3  lea     rcx, [rbp+var_18]
0x1800d34a7  call    ?InternalClose@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(void)
0x1800d34ac  test    al, al
0x1800d34ae  jnz     short loc_1800D3441
0x1800d34b0  call    cs:__imp_GetLastError
0x1800d34b6  test    eax, eax
0x1800d34b8  jle     short loc_1800D34C2
0x1800d34ba  movzx   eax, ax
0x1800d34bd  or      eax, 80070000h
0x1800d34c2  xor     r9d, r9d; lpArguments
0x1800d34c5  xor     r8d, r8d; nNumberOfArguments
0x1800d34c8  lea     edx, [r9+1]; dwExceptionFlags
0x1800d34cc  mov     ecx, eax; dwExceptionCode
0x1800d34ce  call    cs:__imp_RaiseException
0x1800d34d4  nop
0x1800d34d5  mov     edx, 0EA60h; dwMilliseconds
0x1800d34da  mov     rcx, [rdi]; hHandle
0x1800d34dd  call    cs:__imp_WaitForSingleObject
0x1800d34e3  mov     ebx, eax
0x1800d34e5  test    eax, eax
0x1800d34e7  jz      loc_1800D360B
0x1800d34ed  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800d34f2  mov     rcx, [rbp+20h]; this
0x1800d34f6  lea     r8, aOnecoreuapAdmi_111; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800d34fd  cmp     ebx, 102h
0x1800d3503  jnz     short loc_1800D355D
0x1800d3505  mov     ebx, 800705B4h
0x1800d350a  mov     r9d, ebx; char *
0x1800d350d  mov     edx, 12Bh; void *
0x1800d3512  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d3517  nop
0x1800d3518  mov     [rbp+var_18], rsi
0x1800d351c  cmp     [rbp+var_10], 0
0x1800d3521  jz      loc_1800D3441
0x1800d3527  lea     rcx, [rbp+var_18]
0x1800d352b  call    ?InternalClose@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(void)
0x1800d3530  test    al, al
0x1800d3532  jnz     loc_1800D3441
0x1800d3538  call    cs:__imp_GetLastError
0x1800d353e  test    eax, eax
0x1800d3540  jle     short loc_1800D354A
0x1800d3542  movzx   eax, ax
0x1800d3545  or      eax, 80070000h
0x1800d354a  xor     r9d, r9d; lpArguments
0x1800d354d  xor     r8d, r8d; nNumberOfArguments
0x1800d3550  lea     edx, [r9+1]; dwExceptionFlags
0x1800d3554  mov     ecx, eax; dwExceptionCode
0x1800d3556  call    cs:__imp_RaiseException
0x1800d355c  nop
0x1800d355d  cmp     ebx, 0FFFFFFFFh
0x1800d3560  jnz     short loc_1800D35B3
0x1800d3562  mov     edx, 12Ch; void *
0x1800d3567  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800d356c  mov     ebx, eax
0x1800d356e  mov     [rbp+var_18], rsi
0x1800d3572  cmp     [rbp+var_10], 0
0x1800d3577  jz      loc_1800D3441
0x1800d357d  lea     rcx, [rbp+var_18]
0x1800d3581  call    ?InternalClose@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(void)
0x1800d3586  test    al, al
0x1800d3588  jnz     loc_1800D3441
0x1800d358e  call    cs:__imp_GetLastError
0x1800d3594  test    eax, eax
0x1800d3596  jle     short loc_1800D35A0
0x1800d3598  movzx   eax, ax
0x1800d359b  or      eax, 80070000h
0x1800d35a0  xor     r9d, r9d; lpArguments
0x1800d35a3  xor     r8d, r8d; nNumberOfArguments
0x1800d35a6  lea     edx, [r9+1]; dwExceptionFlags
0x1800d35aa  mov     ecx, eax; dwExceptionCode
0x1800d35ac  call    cs:__imp_RaiseException
0x1800d35b2  nop
0x1800d35b3  mov     ebx, 8000FFFFh
0x1800d35b8  mov     r9d, ebx; char *
0x1800d35bb  mov     edx, 12Dh; void *
0x1800d35c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d35c5  nop
0x1800d35c6  mov     [rbp+var_18], rsi
0x1800d35ca  cmp     [rbp+var_10], 0
0x1800d35cf  jz      loc_1800D3441
0x1800d35d5  lea     rcx, [rbp+var_18]
0x1800d35d9  call    ?InternalClose@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(void)
0x1800d35de  test    al, al
0x1800d35e0  jnz     loc_1800D3441
0x1800d35e6  call    cs:__imp_GetLastError
0x1800d35ec  test    eax, eax
0x1800d35ee  jle     short loc_1800D35F8
0x1800d35f0  movzx   eax, ax
0x1800d35f3  or      eax, 80070000h
0x1800d35f8  xor     r9d, r9d; lpArguments
0x1800d35fb  xor     r8d, r8d; nNumberOfArguments
0x1800d35fe  lea     edx, [r9+1]; dwExceptionFlags
0x1800d3602  mov     ecx, eax; dwExceptionCode
0x1800d3604  call    cs:__imp_RaiseException
0x1800d360a  int     3; Trap to Debugger
0x1800d360b  mov     [rbp+var_18], rsi
0x1800d360f  cmp     [rbp+var_10], 0
0x1800d3614  jz      short loc_1800D3648
0x1800d3616  lea     rcx, [rbp+var_18]
0x1800d361a  call    ?InternalClose@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(void)
0x1800d361f  test    al, al
0x1800d3621  jnz     short loc_1800D3648
0x1800d3623  call    cs:__imp_GetLastError
0x1800d3629  test    eax, eax
0x1800d362b  jle     short loc_1800D3635
0x1800d362d  movzx   eax, ax
0x1800d3630  or      eax, 80070000h
0x1800d3635  xor     r9d, r9d; lpArguments
0x1800d3638  xor     r8d, r8d; nNumberOfArguments
0x1800d363b  lea     edx, [r9+1]; dwExceptionFlags
0x1800d363f  mov     ecx, eax; dwExceptionCode
0x1800d3641  call    cs:__imp_RaiseException
0x1800d3647  int     3; Trap to Debugger
0x1800d3648  xor     eax, eax
0x1800d364a  add     rsp, 48h
0x1800d364e  pop     rdi
0x1800d364f  pop     rsi
0x1800d3650  pop     rbx
0x1800d3651  pop     rbp
0x1800d3652  retn
```
