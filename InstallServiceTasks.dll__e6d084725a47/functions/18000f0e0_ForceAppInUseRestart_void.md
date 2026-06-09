# ForceAppInUseRestart(void)

- ea: `0x18000f0e0`
- end: `0x18000f2ea`
- name: `?ForceAppInUseRestart@@YAXXZ`
- size: `522`
- prototype: `void(void)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x18000b714`
- `0x18000b7b8`
- `0x18000d544`
- `0x18000f0e0`
- `0x18000f39c`
- `0x18000fcc4`
- `0x18000ff28`
- `0x1800109dc`
- `0x180010d74`
- `0x180012118`
- `0x180012f10`
- `0x180027020`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18000f285`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18000f285`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000f201`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000f201`

## string_xrefs

- `0x18000f121`: `onecoreuap\enduser\winstore\installservice\tasksdll\installservicetasks.cpp`
- `0x18000f1d3`: `onecoreuap\enduser\winstore\installservice\tasksdll\installservicetasks.cpp`
- `0x18000f2c5`: `onecoreuap\enduser\winstore\installservice\tasksdll\installservicetasks.cpp`
- `0x18000f150`: `ScheduledRetry`
- `0x18000f2a8`: `Failed calling IInstallControl::SmartRetryAsync`
- `0x18000f101`: `Starting InstallService to perform SmartRetry of InUse items due to CSP Policy trigger.`
- `0x18000f1b2`: `Calling IInstallControl::SmartRetryAsync (CSP scenario) with stableNetwork = %s, and scheduledRetry = %s, and forceAppRestart = true`

## pseudocode

```c
void ForceAppInUseRestart(void)
{
  __int64 v0; // rdx
  __int64 v1; // rcx
  char v2; // di
  __int64 v3; // rdx
  _QWORD *v4; // rax
  int TimeTriggerState; // esi
  const wchar_t *v6; // rdx
  const wchar_t *v7; // rax
  __int64 v8; // r9
  __int64 v9; // r8
  __int64 v10; // rdx
  int v11; // edi
  const char *v12; // r9
  __int64 v13; // r8
  __int64 v14; // rdx
  char v15; // al
  __int64 v16; // [rsp+50h] [rbp-18h] BYREF
  std::_Ref_count_base *v17; // [rsp+58h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  int v19; // [rsp+70h] [rbp+8h] BYREF
  __int64 v20; // [rsp+78h] [rbp+10h] BYREF

  LogSimpleMessage(
    3u,
    "onecoreuap\\enduser\\winstore\\installservice\\tasksdll\\installservicetasks.cpp",
    0x173u,
    "ForceAppInUseRestart",
    -1,
    L"Starting InstallService to perform SmartRetry of InUse items due to CSP Policy trigger.",
    0,
    0);
  try
  {
    wil::RoInitialize(&v19);
    v2 = _ProcessNetworkTriggers(v1, v0);
    v4 = InstallServiceTasks::SmartRetry(&v16, v3);
    TimeTriggerState = ScheduledTask::GetTimeTriggerState(*v4, L"ScheduledRetry");
    if ( v17 )
      std::_Ref_count_base::_Decref(v17);
    v6 = L"true";
    v7 = L"true";
    if ( TimeTriggerState != 2 )
      v7 = L"false";
    if ( !v2 )
      v6 = L"false";
    LogMessage(
      3u,
      "onecoreuap\\enduser\\winstore\\installservice\\tasksdll\\installservicetasks.cpp",
      0x17Fu,
      "ForceAppInUseRestart",
      -1,
      L"Calling IInstallControl::SmartRetryAsync (CSP scenario) with stableNetwork = %s, and scheduledRetry = %s, and forc"
       "eAppRestart = true",
      0,
      0,
      v6,
      v7);
    if ( !(unsigned int)IsDeviceXbox()
      || (InitOnceExecuteOnce(&InitOnce, InitializeInstallServiceConfiguration, 0, 0), byte_180083C66) )
    {
      wil::ActivateInstance<Windows::Internal::InstallService::Control::IInstallServiceControl>(&v20);
      LOBYTE(v13) = TimeTriggerState == 2;
      LOBYTE(v14) = v2;
      v11 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD))(*(_QWORD *)v20 + 72LL))(v20, v14, v13, 0);
      wil::com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>::~com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>(&v20);
    }
    else
    {
      wil::ActivateInstance<WindowsUpdate::Internal::IInstallControl>(&v20);
      LOBYTE(v8) = 1;
      LOBYTE(v9) = TimeTriggerState == 2;
      LOBYTE(v10) = v2;
      v11 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64))(*(_QWORD *)v20 + 224LL))(v20, v10, v9, v8);
      wil::com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>::~com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>(&v20);
    }
    v15 = v19;
    LOBYTE(v19) = 0;
    if ( v15 )
      RoUninitialize();
  }
  catch ( ... )
  {
    v19 = wil::details::in1diag3::Log_CaughtException(
            retaddr,
            (void *)0x18B,
            (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\tasksdll\\installservicetasks.cpp",
            v12);
    v11 = v19;
  }
  if ( v11 < 0 )
    LogSimpleMessage(
      1u,
      "onecoreuap\\enduser\\winstore\\installservice\\tasksdll\\installservicetasks.cpp",
      0x18Fu,
      "ForceAppInUseRestart",
      v11,
      L"Failed calling IInstallControl::SmartRetryAsync",
      0,
      0);
}

```

## disassembly

```asm
0x18000f0e0  mov     r11, rsp
0x18000f0e3  mov     [r11+18h], rsi
0x18000f0e7  mov     [r11+20h], rdi
0x18000f0eb  push    r14
0x18000f0ed  sub     rsp, 60h
0x18000f0f1  mov     qword ptr [r11-30h], 0
0x18000f0f9  mov     qword ptr [r11-38h], 0
0x18000f101  lea     rax, aStartingInstal; "Starting InstallService to perform Smar"...
0x18000f108  mov     [r11-40h], rax
0x18000f10c  mov     [rsp+68h+var_48], 0FFFFFFFFh; int
0x18000f114  lea     r9, aForceappinuser_0; "ForceAppInUseRestart"
0x18000f11b  mov     r8d, 173h; unsigned int
0x18000f121  lea     rdx, aOnecoreuapEndu_7; "onecoreuap\\enduser\\winstore\\installs"...
0x18000f128  mov     ecx, 3; unsigned int
0x18000f12d  call    ?LogSimpleMessage@@YAXIPEBDI0JPEBG01@Z; LogSimpleMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *)
0x18000f132  nop
0x18000f133  lea     rcx, [rsp+68h+arg_0]
0x18000f138  call    ?RoInitialize@wil@@YA?AV?$unique_call@P6AXXZ$1?RoUninitialize@@YAXXZ$00@1@W4RO_INIT_TYPE@@@Z; wil::RoInitialize(RO_INIT_TYPE)
0x18000f13d  nop
0x18000f13e  call    ?_ProcessNetworkTriggers@@YA_NXZ; _ProcessNetworkTriggers(void)
0x18000f143  mov     dil, al
0x18000f146  lea     rcx, [rsp+68h+var_18]
0x18000f14b  call    ?SmartRetry@InstallServiceTasks@@YA?AV?$shared_ptr@VScheduledTask@@@std@@XZ; InstallServiceTasks::SmartRetry(void)
0x18000f150  lea     rdx, aScheduledretry; "ScheduledRetry"
0x18000f157  mov     rcx, [rax]
0x18000f15a  call    ?GetTimeTriggerState@ScheduledTask@@QEAA?AW4TimeTriggerState@@PEBG@Z; ScheduledTask::GetTimeTriggerState(ushort const *)
0x18000f15f  mov     esi, eax
0x18000f161  cmp     eax, 2
0x18000f164  setz    r14b
0x18000f168  mov     rcx, [rsp+68h+var_10]; this
0x18000f16d  test    rcx, rcx
0x18000f170  jz      short loc_18000F177
0x18000f172  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000f177  lea     r8, aFalse; "false"
0x18000f17e  lea     rdx, aTrue; "true"
0x18000f185  mov     rax, rdx
0x18000f188  cmp     esi, 2
0x18000f18b  cmovnz  rax, r8
0x18000f18f  test    dil, dil
0x18000f192  cmovz   rdx, r8
0x18000f196  mov     [rsp+68h+var_20], rax
0x18000f19b  mov     [rsp+68h+var_28], rdx
0x18000f1a0  mov     [rsp+68h+var_30], 0; unsigned __int16 *
0x18000f1a9  mov     [rsp+68h+var_38], 0; char *
0x18000f1b2  lea     rax, aCallingIinstal; "Calling IInstallControl::SmartRetryAsyn"...
0x18000f1b9  mov     [rsp+68h+var_40], rax; unsigned __int16 *
0x18000f1be  mov     [rsp+68h+var_48], 0FFFFFFFFh; int
0x18000f1c6  lea     r9, aForceappinuser_0; "ForceAppInUseRestart"
0x18000f1cd  mov     r8d, 17Fh; unsigned int
0x18000f1d3  lea     rdx, aOnecoreuapEndu_7; "onecoreuap\\enduser\\winstore\\installs"...
0x18000f1da  mov     ecx, 3; unsigned int
0x18000f1df  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x18000f1e4  call    ?IsDeviceXbox@@YAHXZ; IsDeviceXbox(void)
0x18000f1e9  test    eax, eax
0x18000f1eb  jz      short loc_18000F246
0x18000f1ed  xor     r9d, r9d; Context
0x18000f1f0  xor     r8d, r8d; Parameter
0x18000f1f3  lea     rdx, InitializeInstallServiceConfiguration; InitFn
0x18000f1fa  lea     rcx, InitOnce; InitOnce
0x18000f201  call    cs:__imp_InitOnceExecuteOnce
0x18000f207  cmp     cs:byte_180083C66, 0
0x18000f20e  jnz     short loc_18000F246
0x18000f210  lea     rcx, [rsp+68h+arg_8]
0x18000f215  call    ??$ActivateInstance@UIInstallControl@Internal@WindowsUpdate@@@wil@@YA?AV?$com_ptr_t@UIInstallControl@Internal@WindowsUpdate@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::ActivateInstance<WindowsUpdate::Internal::IInstallControl>(ushort const *)
0x18000f21a  nop
0x18000f21b  mov     rcx, [rsp+68h+arg_8]
0x18000f220  mov     rax, [rcx]
0x18000f223  mov     r9b, 1
0x18000f226  mov     r8b, r14b
0x18000f229  mov     dl, dil
0x18000f22c  mov     rax, [rax+0E0h]
0x18000f233  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f238  mov     edi, eax
0x18000f23a  lea     rcx, [rsp+68h+arg_8]
0x18000f23f  call    ??1?$com_ptr_t@UITaskSchedulerEx2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>::~com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>(void)
0x18000f244  jmp     short loc_18000F278
0x18000f246  lea     rcx, [rsp+68h+arg_8]
0x18000f24b  call    ??$ActivateInstance@UIInstallServiceControl@Control@InstallService@Internal@Windows@@@wil@@YA?AV?$com_ptr_t@UIInstallServiceControl@Control@InstallService@Internal@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::ActivateInstance<Windows::Internal::InstallService::Control::IInstallServiceControl>(ushort const *)
0x18000f250  nop
0x18000f251  mov     rcx, [rsp+68h+arg_8]
0x18000f256  mov     rax, [rcx]
0x18000f259  xor     r9d, r9d
0x18000f25c  mov     r8b, r14b
0x18000f25f  mov     dl, dil
0x18000f262  mov     rax, [rax+48h]
0x18000f266  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f26b  mov     edi, eax
0x18000f26d  lea     rcx, [rsp+68h+arg_8]
0x18000f272  call    ??1?$com_ptr_t@UITaskSchedulerEx2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>::~com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>(void)
0x18000f277  nop
0x18000f278  mov     al, byte ptr [rsp+68h+arg_0]
0x18000f27c  mov     byte ptr [rsp+68h+arg_0], 0
0x18000f281  test    al, al
0x18000f283  jz      short loc_18000F28C
0x18000f285  call    cs:__imp_RoUninitialize
0x18000f28b  nop
0x18000f28c  jmp     short loc_18000F292
0x18000f28e  mov     edi, [rsp+68h+arg_0]
0x18000f292  test    edi, edi
0x18000f294  jns     short loc_18000F2D7
0x18000f296  mov     [rsp+68h+var_30], 0; unsigned __int16 *
0x18000f29f  mov     [rsp+68h+var_38], 0; char *
0x18000f2a8  lea     rax, aFailedCallingI; "Failed calling IInstallControl::SmartRe"...
0x18000f2af  mov     [rsp+68h+var_40], rax; unsigned __int16 *
0x18000f2b4  mov     [rsp+68h+var_48], edi; int
0x18000f2b8  lea     r9, aForceappinuser_0; "ForceAppInUseRestart"
0x18000f2bf  mov     r8d, 18Fh; unsigned int
0x18000f2c5  lea     rdx, aOnecoreuapEndu_7; "onecoreuap\\enduser\\winstore\\installs"...
0x18000f2cc  mov     ecx, 1; unsigned int
0x18000f2d1  call    ?LogSimpleMessage@@YAXIPEBDI0JPEBG01@Z; LogSimpleMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *)
0x18000f2d6  nop
0x18000f2d7  lea     r11, [rsp+68h+var_8]
0x18000f2dc  mov     rsi, [r11+20h]
0x18000f2e0  mov     rdi, [r11+28h]
0x18000f2e4  mov     rsp, r11
0x18000f2e7  pop     r14
0x18000f2e9  retn
```
