# EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager::AutoPilotAsyncAction::LaunchWorker(void)

- ea: `0x1800d5a08`
- end: `0x1800d5c47`
- name: `?LaunchWorker@AutoPilotAsyncAction@AutoPilotManager@AutoPilot@Service@EnterpriseDeviceManagement@@QEAAJXZ`
- size: `575`
- prototype: `__int64 __fastcall(EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager::AutoPilotAsyncAction *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800d78c4`

## callees

- `0x180067e34`
- `0x180067e54`
- `0x180087ec4`
- `0x1800a19c4`
- `0x1800d56b0`
- `0x1800d5a08`
- `0x180179f94`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800d5ade`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800d5ade`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d5ab6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d5b3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d5b90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d5be3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d5c1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d5ab6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d5b3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d5b90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d5be3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d5c1b`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800d5a67`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800d5a67`

## string_xrefs

- `0x1800d5a30`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\autopilotmanager.cpp`
- `0x1800d5a8b`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\autopilotmanager.cpp`
- `0x1800d5afd`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\autopilotmanager.cpp`

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
  signed int v10; // eax
  int v11; // edx
  unsigned int v12; // r8d
  signed int v13; // eax
  int v14; // edx
  unsigned int v15; // r8d
  signed int v16; // eax
  int v17; // edx
  unsigned int v18; // r8d
  signed int v19; // eax
  int v20; // edx
  unsigned int v21; // r8d
  DWORD dwCreationFlags; // [rsp+20h] [rbp-28h]
  DWORD dwCreationFlagsa; // [rsp+20h] [rbp-28h]
  void **v24; // [rsp+30h] [rbp-18h] BYREF
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
  v24 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
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
    v24 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
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
      v24 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
      if ( !Thread
        || (unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(&v24) )
      {
        return LastError;
      }
      v10 = GetLastError();
      if ( v10 > 0 )
        v10 = (unsigned __int16)v10 | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v10, v11, v12);
    }
    if ( LastError == -1 )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(v8, (void *)0x12C, (unsigned int)v9, v7);
      v24 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
      if ( !Thread
        || (unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(&v24) )
      {
        return LastError;
      }
      v13 = GetLastError();
      if ( v13 > 0 )
        v13 = (unsigned __int16)v13 | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v13, v14, v15);
    }
    LastError = -2147418113;
    wil::details::in1diag3::Return_Hr(v8, (void *)0x12D, (unsigned int)v9, (const char *)0x8000FFFFLL, dwCreationFlagsa);
    v24 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
    if ( Thread
      && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(&v24) )
    {
      v16 = GetLastError();
      if ( v16 > 0 )
        v16 = (unsigned __int16)v16 | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v16, v17, v18);
      __debugbreak();
    }
    return LastError;
  }
  v24 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
  if ( Thread
    && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(&v24) )
  {
    v19 = GetLastError();
    if ( v19 > 0 )
      v19 = (unsigned __int16)v19 | 0x80070000;
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v19, v20, v21);
    __debugbreak();
  }
  return 0;
}

```

## disassembly

```asm
0x1800d5a08  push    rbp
0x1800d5a0a  push    rbx
0x1800d5a0b  push    rsi
0x1800d5a0c  push    rdi
0x1800d5a0d  mov     rbp, rsp
0x1800d5a10  sub     rsp, 48h
0x1800d5a14  mov     rsi, rcx
0x1800d5a17  lea     rdi, [rcx+20h]
0x1800d5a1b  mov     rcx, rdi
0x1800d5a1e  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800d5a23  mov     ebx, eax
0x1800d5a25  test    eax, eax
0x1800d5a27  jns     short loc_1800D5A48
0x1800d5a29  mov     rcx, [rbp+20h]; this
0x1800d5a2d  mov     r9d, eax; char *
0x1800d5a30  lea     r8, aOnecoreuapAdmi_111; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800d5a37  mov     edx, 11Eh; void *
0x1800d5a3c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d5a41  mov     eax, ebx
0x1800d5a43  jmp     loc_1800D5C3D
0x1800d5a48  mov     [rsp+48h+lpThreadId], 0; lpThreadId
0x1800d5a51  mov     [rsp+48h+dwCreationFlags], 0; int
0x1800d5a59  mov     r9, rsi; lpParameter
0x1800d5a5c  lea     r8, ?AsyncThreadProc@AutoPilotAsyncAction@AutoPilotManager@AutoPilot@Service@EnterpriseDeviceManagement@@CAKPEAX@Z; lpStartAddress
0x1800d5a63  xor     edx, edx; dwStackSize
0x1800d5a65  xor     ecx, ecx; lpThreadAttributes
0x1800d5a67  call    cs:__imp_CreateThread
0x1800d5a6e  nop     dword ptr [rax+rax+00h]
0x1800d5a73  lea     rsi, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x1800d5a7a  mov     [rbp+var_18], rsi
0x1800d5a7e  mov     [rbp+var_10], rax
0x1800d5a82  test    rax, rax
0x1800d5a85  jnz     short loc_1800D5AD6
0x1800d5a87  mov     rcx, [rbp+20h]; this
0x1800d5a8b  lea     r8, aOnecoreuapAdmi_111; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800d5a92  mov     edx, 123h; void *
0x1800d5a97  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800d5a9c  mov     ebx, eax
0x1800d5a9e  mov     [rbp+var_18], rsi
0x1800d5aa2  cmp     [rbp+var_10], 0
0x1800d5aa7  jz      short loc_1800D5A41
0x1800d5aa9  lea     rcx, [rbp+var_18]
0x1800d5aad  call    ?InternalClose@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(void)
0x1800d5ab2  test    al, al
0x1800d5ab4  jnz     short loc_1800D5A41
0x1800d5ab6  call    cs:__imp_GetLastError
0x1800d5abd  nop     dword ptr [rax+rax+00h]
0x1800d5ac2  test    eax, eax
0x1800d5ac4  jle     short loc_1800D5ACE
0x1800d5ac6  movzx   eax, ax
0x1800d5ac9  or      eax, 80070000h
0x1800d5ace  mov     ecx, eax; this
0x1800d5ad0  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1800d5ad5  nop
0x1800d5ad6  mov     edx, 0EA60h; dwMilliseconds
0x1800d5adb  mov     rcx, [rdi]; hHandle
0x1800d5ade  call    cs:__imp_WaitForSingleObject
0x1800d5ae5  nop     dword ptr [rax+rax+00h]
0x1800d5aea  mov     ebx, eax
0x1800d5aec  test    eax, eax
0x1800d5aee  jz      loc_1800D5C03
0x1800d5af4  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "false", "Unexpected wait result in LaunchWorker")
0x1800d5af9  mov     rcx, [rbp+20h]; this
0x1800d5afd  lea     r8, aOnecoreuapAdmi_111; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800d5b04  cmp     ebx, 102h
0x1800d5b0a  jnz     short loc_1800D5B5F
0x1800d5b0c  mov     ebx, 800705B4h
0x1800d5b11  mov     r9d, ebx; char *
0x1800d5b14  mov     edx, 12Bh; void *
0x1800d5b19  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d5b1e  nop
0x1800d5b1f  mov     [rbp+var_18], rsi
0x1800d5b23  cmp     [rbp+var_10], 0
0x1800d5b28  jz      loc_1800D5A41
0x1800d5b2e  lea     rcx, [rbp+var_18]
0x1800d5b32  call    ?InternalClose@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(void)
0x1800d5b37  test    al, al
0x1800d5b39  jnz     loc_1800D5A41
0x1800d5b3f  call    cs:__imp_GetLastError
0x1800d5b46  nop     dword ptr [rax+rax+00h]
0x1800d5b4b  test    eax, eax
0x1800d5b4d  jle     short loc_1800D5B57
0x1800d5b4f  movzx   eax, ax
0x1800d5b52  or      eax, 80070000h
0x1800d5b57  mov     ecx, eax; this
0x1800d5b59  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1800d5b5e  nop
0x1800d5b5f  cmp     ebx, 0FFFFFFFFh
0x1800d5b62  jnz     short loc_1800D5BB0
0x1800d5b64  mov     edx, 12Ch; void *
0x1800d5b69  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800d5b6e  mov     ebx, eax
0x1800d5b70  mov     [rbp+var_18], rsi
0x1800d5b74  cmp     [rbp+var_10], 0
0x1800d5b79  jz      loc_1800D5A41
0x1800d5b7f  lea     rcx, [rbp+var_18]
0x1800d5b83  call    ?InternalClose@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(void)
0x1800d5b88  test    al, al
0x1800d5b8a  jnz     loc_1800D5A41
0x1800d5b90  call    cs:__imp_GetLastError
0x1800d5b97  nop     dword ptr [rax+rax+00h]
0x1800d5b9c  test    eax, eax
0x1800d5b9e  jle     short loc_1800D5BA8
0x1800d5ba0  movzx   eax, ax
0x1800d5ba3  or      eax, 80070000h
0x1800d5ba8  mov     ecx, eax; this
0x1800d5baa  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1800d5baf  nop
0x1800d5bb0  mov     ebx, 8000FFFFh
0x1800d5bb5  mov     r9d, ebx; char *
0x1800d5bb8  mov     edx, 12Dh; void *
0x1800d5bbd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d5bc2  nop
0x1800d5bc3  mov     [rbp+var_18], rsi
0x1800d5bc7  cmp     [rbp+var_10], 0
0x1800d5bcc  jz      loc_1800D5A41
0x1800d5bd2  lea     rcx, [rbp+var_18]
0x1800d5bd6  call    ?InternalClose@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(void)
0x1800d5bdb  test    al, al
0x1800d5bdd  jnz     loc_1800D5A41
0x1800d5be3  call    cs:__imp_GetLastError
0x1800d5bea  nop     dword ptr [rax+rax+00h]
0x1800d5bef  test    eax, eax
0x1800d5bf1  jle     short loc_1800D5BFB
0x1800d5bf3  movzx   eax, ax
0x1800d5bf6  or      eax, 80070000h
0x1800d5bfb  mov     ecx, eax; this
0x1800d5bfd  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1800d5c02  int     3; Trap to Debugger
0x1800d5c03  mov     [rbp+var_18], rsi
0x1800d5c07  cmp     [rbp+var_10], 0
0x1800d5c0c  jz      short loc_1800D5C3B
0x1800d5c0e  lea     rcx, [rbp+var_18]
0x1800d5c12  call    ?InternalClose@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(void)
0x1800d5c17  test    al, al
0x1800d5c19  jnz     short loc_1800D5C3B
0x1800d5c1b  call    cs:__imp_GetLastError
0x1800d5c22  nop     dword ptr [rax+rax+00h]
0x1800d5c27  test    eax, eax
0x1800d5c29  jle     short loc_1800D5C33
0x1800d5c2b  movzx   eax, ax
0x1800d5c2e  or      eax, 80070000h
0x1800d5c33  mov     ecx, eax; this
0x1800d5c35  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1800d5c3a  int     3; Trap to Debugger
0x1800d5c3b  xor     eax, eax
0x1800d5c3d  add     rsp, 48h
0x1800d5c41  pop     rdi
0x1800d5c42  pop     rsi
0x1800d5c43  pop     rbx
0x1800d5c44  pop     rbp
0x1800d5c45  retn
```
