# CSmartRetryTaskHandler::Worker(void)

- ea: `0x180010230`
- end: `0x1800104a8`
- name: `?Worker@CSmartRetryTaskHandler@@EEAAJXZ`
- size: `632`
- prototype: `__int64 __fastcall(CSmartRetryTaskHandler *__hidden this)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x18000b714`
- `0x18000b7b8`
- `0x18000d544`
- `0x18000f39c`
- `0x18000ff28`
- `0x180010230`
- `0x1800109dc`
- `0x180010d74`
- `0x180012118`
- `0x180012f10`
- `0x18001f340`
- `0x180027020`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001037b`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001037b`

## string_xrefs

- `0x18001027c`: `onecoreuap\enduser\winstore\installservice\tasksdll\installservicetasks.cpp`
- `0x18001034f`: `onecoreuap\enduser\winstore\installservice\tasksdll\installservicetasks.cpp`
- `0x180010481`: `onecoreuap\enduser\winstore\installservice\tasksdll\installservicetasks.cpp`
- `0x1800102b3`: `ScheduledRetry`
- `0x18001025c`: `Starting InstallService to perform SmartRetry of blocked queued items.`
- `0x18001026f`: `CSmartRetryTaskHandler::Worker`
- `0x180010342`: `CSmartRetryTaskHandler::Worker`
- `0x18001047a`: `CSmartRetryTaskHandler::Worker`
- `0x180010331`: `Calling IInstallControl::SmartRetryAsync with stableNetwork = %s, and scheduledRetry = %s`
- `0x18001042b`: `Succesfully called IInstallControl::SmartRetryAsync`
- `0x180010457`: `Task was triggered, but system/trigger state didn't result in call to SmartRetry - not completely unexpected.`
- `0x180010448`: `Failed calling IInstallControl::SmartRetryAsync`

## pseudocode

```c
__int64 __fastcall CSmartRetryTaskHandler::Worker(CSmartRetryTaskHandler *this)
{
  int v2; // esi
  int v3; // r15d
  unsigned int v4; // r14d
  bool v5; // bl
  _QWORD *v6; // rax
  int TimeTriggerState; // r12d
  std::_Ref_count_base *v8; // rcx
  const char *v9; // r9
  const wchar_t *v10; // rcx
  const wchar_t *v11; // rax
  __int64 v12; // r8
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // rdx
  unsigned int v16; // r8d
  const unsigned __int16 *v17; // rax
  _BYTE v19[8]; // [rsp+50h] [rbp-38h] BYREF
  std::_Ref_count_base *v20; // [rsp+58h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  __int64 v22; // [rsp+98h] [rbp+10h] BYREF

  v2 = -2147483638;
  v3 = -1;
  v4 = 3;
  LogSimpleMessage(
    3u,
    "onecoreuap\\enduser\\winstore\\installservice\\tasksdll\\installservicetasks.cpp",
    0x129u,
    "CSmartRetryTaskHandler::Worker",
    -1,
    L"Starting InstallService to perform SmartRetry of blocked queued items.",
    0,
    0);
  if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 9, 1, 1) == 1 )
    goto LABEL_21;
  try
  {
    v5 = _ProcessNetworkTriggers();
    v6 = (_QWORD *)InstallServiceTasks::SmartRetry(v19);
    TimeTriggerState = ScheduledTask::GetTimeTriggerState(*v6, L"ScheduledRetry");
    v8 = v20;
    if ( v20 )
      std::_Ref_count_base::_Decref(v20);
    if ( v5 || TimeTriggerState == 2 || InstallServiceTaskHelpers::IsNonTimerSmartRetryTriggerEnabled(v8) )
    {
      v10 = L"true";
      v11 = L"true";
      if ( TimeTriggerState != 2 )
        v11 = L"false";
      if ( !v5 )
        v10 = L"false";
      LogMessage(
        3u,
        "onecoreuap\\enduser\\winstore\\installservice\\tasksdll\\installservicetasks.cpp",
        0x135u,
        "CSmartRetryTaskHandler::Worker",
        -1,
        L"Calling IInstallControl::SmartRetryAsync with stableNetwork = %s, and scheduledRetry = %s",
        0,
        0,
        v10,
        v11);
      if ( !(unsigned int)IsDeviceXbox()
        || (InitOnceExecuteOnce(&InitOnce, InitializeInstallServiceConfiguration, 0, 0), byte_180083C66) )
      {
        wil::ActivateInstance<Windows::Internal::InstallService::Control::IInstallServiceControl>(&v22);
        LOBYTE(v14) = TimeTriggerState == 2;
        LOBYTE(v15) = v5;
        v2 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD))(*(_QWORD *)v22 + 72LL))(v22, v15, v14, 0);
        wil::com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>::~com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>(&v22);
      }
      else
      {
        wil::ActivateInstance<WindowsUpdate::Internal::IInstallControl>(&v22);
        LOBYTE(v12) = TimeTriggerState == 2;
        LOBYTE(v13) = v5;
        v2 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD))(*(_QWORD *)v22 + 224LL))(v22, v13, v12, 0);
        wil::com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>::~com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>(&v22);
      }
    }
  }
  catch ( ... )
  {
    v3 = -1;
    v4 = 3;
    v2 = wil::details::in1diag3::Log_CaughtException(
           retaddr,
           (void *)0x142,
           (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\tasksdll\\installservicetasks.cpp",
           v9);
  }
  if ( v2 < 0 )
  {
    if ( v2 != -2147483638 )
    {
      v4 = 1;
      v16 = 334;
      v3 = v2;
      v17 = L"Failed calling IInstallControl::SmartRetryAsync";
      goto LABEL_22;
    }
LABEL_21:
    v16 = 330;
    v17 = L"Task was triggered, but system/trigger state didn't result in call to SmartRetry - not completely unexpected.";
    goto LABEL_22;
  }
  v16 = 326;
  v17 = L"Succesfully called IInstallControl::SmartRetryAsync";
LABEL_22:
  LogSimpleMessage(
    v4,
    "onecoreuap\\enduser\\winstore\\installservice\\tasksdll\\installservicetasks.cpp",
    v16,
    "CSmartRetryTaskHandler::Worker",
    v3,
    v17,
    0,
    0);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180010230  mov     r11, rsp
0x180010233  mov     [r11+18h], rbx
0x180010237  push    rsi
0x180010238  push    r12
0x18001023a  push    r13
0x18001023c  push    r14
0x18001023e  push    r15
0x180010240  sub     rsp, 60h
0x180010244  mov     rbx, rcx
0x180010247  mov     esi, 8000000Ah
0x18001024c  mov     qword ptr [r11-50h], 0
0x180010254  mov     qword ptr [r11-58h], 0
0x18001025c  lea     rax, aStartingInstal_0; "Starting InstallService to perform Smar"...
0x180010263  mov     [r11-60h], rax
0x180010267  or      r15d, 0FFFFFFFFh
0x18001026b  mov     [r11-68h], r15d
0x18001026f  lea     r9, aCsmartretrytas; "CSmartRetryTaskHandler::Worker"
0x180010276  mov     r8d, 129h; unsigned int
0x18001027c  lea     rdx, aOnecoreuapEndu_7; "onecoreuap\\enduser\\winstore\\installs"...
0x180010283  lea     r14d, [r15+4]
0x180010287  mov     ecx, r14d; unsigned int
0x18001028a  call    ?LogSimpleMessage@@YAXIPEBDI0JPEBG01@Z; LogSimpleMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *)
0x18001028f  lea     r13d, [r15+2]
0x180010293  mov     eax, r13d
0x180010296  lock cmpxchg [rbx+24h], r13d
0x18001029c  jz      loc_180010451
0x1800102a2  call    ?_ProcessNetworkTriggers@@YA_NXZ; _ProcessNetworkTriggers(void)
0x1800102a7  mov     bl, al
0x1800102a9  lea     rcx, [rsp+88h+var_38]
0x1800102ae  call    ?SmartRetry@InstallServiceTasks@@YA?AV?$shared_ptr@VScheduledTask@@@std@@XZ; InstallServiceTasks::SmartRetry(void)
0x1800102b3  lea     rdx, aScheduledretry; "ScheduledRetry"
0x1800102ba  mov     rcx, [rax]
0x1800102bd  call    ?GetTimeTriggerState@ScheduledTask@@QEAA?AW4TimeTriggerState@@PEBG@Z; ScheduledTask::GetTimeTriggerState(ushort const *)
0x1800102c2  mov     r12d, eax
0x1800102c5  cmp     eax, 2
0x1800102c8  setz    byte ptr [rsp+88h+arg_0]
0x1800102d0  mov     rcx, [rsp+88h+var_30]; this
0x1800102d5  test    rcx, rcx
0x1800102d8  jz      short loc_1800102DF
0x1800102da  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800102df  test    bl, bl
0x1800102e1  jnz     short loc_1800102F6
0x1800102e3  cmp     r12d, 2
0x1800102e7  jz      short loc_1800102F6
0x1800102e9  call    ?IsNonTimerSmartRetryTriggerEnabled@InstallServiceTaskHelpers@@YA_NXZ; InstallServiceTaskHelpers::IsNonTimerSmartRetryTriggerEnabled(void)
0x1800102ee  test    al, al
0x1800102f0  jz      loc_18001040C
0x1800102f6  lea     rdx, aFalse; "false"
0x1800102fd  lea     rcx, aTrue; "true"
0x180010304  mov     rax, rcx
0x180010307  cmp     r12d, 2
0x18001030b  cmovnz  rax, rdx
0x18001030f  test    bl, bl
0x180010311  cmovz   rcx, rdx
0x180010315  mov     [rsp+88h+var_40], rax
0x18001031a  mov     [rsp+88h+var_48], rcx
0x18001031f  mov     [rsp+88h+var_50], 0; unsigned __int16 *
0x180010328  mov     [rsp+88h+var_58], 0; char *
0x180010331  lea     rax, aCallingIinstal_0; "Calling IInstallControl::SmartRetryAsyn"...
0x180010338  mov     [rsp+88h+var_60], rax; unsigned __int16 *
0x18001033d  mov     [rsp+88h+var_68], r15d; int
0x180010342  lea     r9, aCsmartretrytas; "CSmartRetryTaskHandler::Worker"
0x180010349  mov     r8d, 135h; unsigned int
0x18001034f  lea     rdx, aOnecoreuapEndu_7; "onecoreuap\\enduser\\winstore\\installs"...
0x180010356  mov     ecx, r14d; unsigned int
0x180010359  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x18001035e  call    ?IsDeviceXbox@@YAHXZ; IsDeviceXbox(void)
0x180010363  test    eax, eax
0x180010365  jz      short loc_1800103CD
0x180010367  xor     r9d, r9d; Context
0x18001036a  xor     r8d, r8d; Parameter
0x18001036d  lea     rdx, InitializeInstallServiceConfiguration; InitFn
0x180010374  lea     rcx, InitOnce; InitOnce
0x18001037b  call    cs:__imp_InitOnceExecuteOnce
0x180010381  cmp     cs:byte_180083C66, 0
0x180010388  jnz     short loc_1800103CD
0x18001038a  lea     rcx, [rsp+88h+arg_8]
0x180010392  call    ??$ActivateInstance@UIInstallControl@Internal@WindowsUpdate@@@wil@@YA?AV?$com_ptr_t@UIInstallControl@Internal@WindowsUpdate@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::ActivateInstance<WindowsUpdate::Internal::IInstallControl>(ushort const *)
0x180010397  nop
0x180010398  mov     rcx, [rsp+88h+arg_8]
0x1800103a0  mov     rax, [rcx]
0x1800103a3  xor     r9d, r9d
0x1800103a6  mov     r8b, byte ptr [rsp+88h+arg_0]
0x1800103ae  mov     dl, bl
0x1800103b0  mov     rax, [rax+0E0h]
0x1800103b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800103bc  mov     esi, eax
0x1800103be  lea     rcx, [rsp+88h+arg_8]
0x1800103c6  call    ??1?$com_ptr_t@UITaskSchedulerEx2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>::~com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>(void)
0x1800103cb  jmp     short loc_18001040C
0x1800103cd  lea     rcx, [rsp+88h+arg_8]
0x1800103d5  call    ??$ActivateInstance@UIInstallServiceControl@Control@InstallService@Internal@Windows@@@wil@@YA?AV?$com_ptr_t@UIInstallServiceControl@Control@InstallService@Internal@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::ActivateInstance<Windows::Internal::InstallService::Control::IInstallServiceControl>(ushort const *)
0x1800103da  nop
0x1800103db  mov     rcx, [rsp+88h+arg_8]
0x1800103e3  mov     rax, [rcx]
0x1800103e6  xor     r9d, r9d
0x1800103e9  mov     r8b, byte ptr [rsp+88h+arg_0]
0x1800103f1  mov     dl, bl
0x1800103f3  mov     rax, [rax+48h]
0x1800103f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800103fc  mov     esi, eax
0x1800103fe  lea     rcx, [rsp+88h+arg_8]
0x180010406  call    ??1?$com_ptr_t@UITaskSchedulerEx2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>::~com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>(void)
0x18001040b  nop
0x18001040c  jmp     short loc_180010421
0x18001040e  or      r15d, 0FFFFFFFFh
0x180010412  lea     r14d, [r15+4]
0x180010416  lea     r13d, [r15+2]
0x18001041a  mov     esi, [rsp+88h+arg_0]
0x180010421  test    esi, esi
0x180010423  js      short loc_180010434
0x180010425  mov     r8d, 146h
0x18001042b  lea     rax, aSuccesfullyCal; "Succesfully called IInstallControl::Sma"...
0x180010432  jmp     short loc_18001045E
0x180010434  cmp     esi, 8000000Ah
0x18001043a  jz      short loc_180010451
0x18001043c  mov     r14d, r13d
0x18001043f  mov     r8d, 14Eh
0x180010445  mov     r15d, esi
0x180010448  lea     rax, aFailedCallingI; "Failed calling IInstallControl::SmartRe"...
0x18001044f  jmp     short loc_18001045E
0x180010451  mov     r8d, 14Ah; unsigned int
0x180010457  lea     rax, aTaskWasTrigger; "Task was triggered, but system/trigger "...
0x18001045e  mov     [rsp+88h+var_50], 0; unsigned __int16 *
0x180010467  mov     [rsp+88h+var_58], 0; char *
0x180010470  mov     [rsp+88h+var_60], rax; unsigned __int16 *
0x180010475  mov     [rsp+88h+var_68], r15d; int
0x18001047a  lea     r9, aCsmartretrytas; "CSmartRetryTaskHandler::Worker"
0x180010481  lea     rdx, aOnecoreuapEndu_7; "onecoreuap\\enduser\\winstore\\installs"...
0x180010488  mov     ecx, r14d; unsigned int
0x18001048b  call    ?LogSimpleMessage@@YAXIPEBDI0JPEBG01@Z; LogSimpleMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *)
0x180010490  mov     eax, esi
0x180010492  mov     rbx, [rsp+88h+arg_10]
0x18001049a  add     rsp, 60h
0x18001049e  pop     r15
0x1800104a0  pop     r14
0x1800104a2  pop     r13
0x1800104a4  pop     r12
0x1800104a6  pop     rsi
0x1800104a7  retn
```
