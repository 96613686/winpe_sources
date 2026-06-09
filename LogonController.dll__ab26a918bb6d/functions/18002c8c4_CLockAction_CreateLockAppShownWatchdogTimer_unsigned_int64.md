# CLockAction::_CreateLockAppShownWatchdogTimer(unsigned __int64)

- ea: `0x18002c8c4`
- end: `0x18002cc78`
- name: `?_CreateLockAppShownWatchdogTimer@CLockAction@@AEAAJ_K@Z`
- size: `948`
- prototype: `__int64 __fastcall(PVOID pv, unsigned __int64)`
- caller_count: `2`
- callee_count: `20`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800211f8`
- `0x18002be30`

## callees

- `0x18000bac8`
- `0x18000cc18`
- `0x18000e72c`
- `0x18001c56c`
- `0x18001c860`
- `0x18001d850`
- `0x18001db70`
- `0x18001f3a0`
- `0x18002c8c4`
- `0x18002cc80`
- `0x180039bb0`
- `0x1800489f4`
- `0x18004f560`
- `0x18005b3e4`
- `0x18005d4e8`
- `0x18005f980`
- `0x18006c000`
- `0x18006cad0`
- `0x18009b790`
- `0x18009d010`

## import_xrefs

- `KERNEL32!CreateThreadpoolTimer` at `0x18002c9e4`
- `KERNEL32!CreateThreadpoolTimer` at `0x18002ca6c`
- `KERNEL32!CreateThreadpoolTimer` at `0x18002c9e4`
- `KERNEL32!CreateThreadpoolTimer` at `0x18002ca6c`
- `KERNEL32!SetThreadpoolTimer` at `0x18002cb95`
- `KERNEL32!SetThreadpoolTimer` at `0x18002cc17`
- `KERNEL32!SetThreadpoolTimer` at `0x18002cb95`
- `KERNEL32!SetThreadpoolTimer` at `0x18002cc17`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18002ca44`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18002caa4`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18002cb74`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18002cc31`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18002ca44`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18002caa4`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18002cb74`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18002cc31`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18002c9d1`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18002cad2`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18002c9d1`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18002cad2`
- `KERNEL32!SetLastError` at `0x18002ca0b`
- `KERNEL32!SetLastError` at `0x18002ca0b`
- `KERNEL32!GetLastError` at `0x18002c9f9`
- `KERNEL32!GetLastError` at `0x18002c9f9`

## string_xrefs

- `0x18002c916`: `CLockAction__CreateLockAppShownWatchdogTimer_Activity`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CLockAction::_CreateLockAppShownWatchdogTimer(char *pv)
{
  const char *v2; // r9
  PTP_TIMER ThreadpoolTimer; // r14
  struct _TP_TIMER *v4; // r15
  DWORD LastError; // ebx
  unsigned int v6; // ebx
  PTP_TIMER v7; // rax
  const char *v8; // r9
  __int64 v9; // rcx
  __int64 v10; // r8
  struct wil::details::wnf_subscription_state_base *v11; // rdx
  __int64 v12; // rcx
  struct _GUID Buf1; // [rsp+20h] [rbp-E0h] BYREF
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp-D0h] BYREF
  void **v16; // [rsp+40h] [rbp-C0h] BYREF
  int v17; // [rsp+48h] [rbp-B8h] BYREF
  char v18; // [rsp+4Ch] [rbp-B4h]
  int v19; // [rsp+70h] [rbp-90h] BYREF
  const char *v20; // [rsp+78h] [rbp-88h]
  __int64 v21; // [rsp+80h] [rbp-80h]
  char v22; // [rsp+88h] [rbp-78h]
  int v23; // [rsp+90h] [rbp-70h]
  _BYTE v24[152]; // [rsp+98h] [rbp-68h] BYREF
  __int128 v25; // [rsp+130h] [rbp+30h]
  int v26; // [rsp+140h] [rbp+40h]
  __int64 v27; // [rsp+148h] [rbp+48h]
  int *v28; // [rsp+150h] [rbp+50h]
  __int64 v29; // [rsp+158h] [rbp+58h]
  _BYTE v30[48]; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v31[8]; // [rsp+190h] [rbp+90h] BYREF
  _QWORD v32[13]; // [rsp+198h] [rbp+98h] BYREF
  _QWORD *v33; // [rsp+200h] [rbp+100h]
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+158h]

  v16 = &wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::`vftable';
  v17 = 0;
  v18 = 0;
  v22 = 0;
  v19 = 0;
  v20 = "CLockAction__CreateLockAppShownWatchdogTimer_Activity";
  v21 = 0;
  v23 = 0;
  v25 = 0;
  memset_0(v24, 0, sizeof(v24));
  v26 = 1;
  v27 = 0;
  v28 = &v17;
  v29 = 0;
  wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(
    (wil::details::ThreadFailureCallbackHolder *)v30,
    (struct wil::details::IFailureCallback *)&v16,
    (struct wil::CallContextInfo *)&v19,
    0);
  v16 = &LogonControllerTelemetry::CLockAction__CreateLockAppShownWatchdogTimer_Activity::`vftable';
  Buf1 = *GetFirstRunTelemetryCorrelationId(&Buf1);
  if ( memcmp_0(&Buf1, &GUID_NULL, 0x10u) )
    wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivityId(
      &v16,
      &Buf1);
  LogonControllerTelemetry::CLockAction__CreateLockAppShownWatchdogTimer_Activity::StartActivity((LogonControllerTelemetry::CLockAction__CreateLockAppShownWatchdogTimer_Activity *)&v16);
  AcquireSRWLockExclusive((PSRWLOCK)pv + 59);
  ThreadpoolTimer = CreateThreadpoolTimer(CLockAction::_s_LockAppShownWatchdogTimerExpired, pv, 0);
  v4 = (struct _TP_TIMER *)*((_QWORD *)pv + 60);
  if ( v4 )
  {
    LastError = GetLastError();
    wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(v4);
    SetLastError(LastError);
  }
  *((_QWORD *)pv + 60) = ThreadpoolTimer;
  if ( !ThreadpoolTimer )
  {
    v6 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0x39E,
           (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lockhost\\lockaction.cpp",
           v2);
    if ( pv != (char *)-472LL )
      ReleaseSRWLockExclusive((PSRWLOCK)pv + 59);
LABEL_33:
    v16 = &LogonControllerTelemetry::CLockAction__CreateLockAppShownWatchdogTimer_Activity::`vftable';
    wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v16);
    wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(&v16);
    return v6;
  }
  if ( !pv[565]
    || (v7 = CreateThreadpoolTimer(CLockAction::_s_UnlockIfLockAppDidntShowWatchdogTimerExpired, pv, 0),
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          pv + 488,
          v7),
        *((_QWORD *)pv + 61)) )
  {
    *((_WORD *)pv + 248) = 0;
    *((_DWORD *)pv + 78) = 0;
    AcquireSRWLockExclusive((PSRWLOCK)pv + 64);
    if ( !*((_QWORD *)pv + 63) )
    {
      v32[0] = off_1800A1658;
      v32[1] = pv;
      v33 = v32;
      *(_QWORD *)&Buf1.Data1 = 0;
      if ( (int)wil::details::make_wnf_subscription_state<unsigned int>(v9, v31, v10, &Buf1) < 0 )
        *(_QWORD *)&Buf1.Data1 = 0;
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>>::operator=(
        pv + 504,
        &Buf1);
      if ( *(_QWORD *)&Buf1.Data1 )
        wil::details::delete_wnf_subscription_state(*(wil::details **)&Buf1.Data1, v11);
      if ( v33 )
        (*(void (__fastcall **)(_QWORD *))(*v33 + 24LL))(v33);
    }
    if ( pv != (char *)-512LL )
      ReleaseSRWLockExclusive((PSRWLOCK)pv + 64);
    pftDueTime = (struct _FILETIME)-50000000LL;
    SetThreadpoolTimer(*((PTP_TIMER *)pv + 60), &pftDueTime, 0, 0);
    if ( pv[565] )
    {
      v12 = qword_1800D3F10;
      if ( !qword_1800D3F10 )
      {
        Buf1.Data1 = 0;
        if ( SHRegGetDWORD(
               HKEY_LOCAL_MACHINE,
               L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI\\TestHooks",
               L"UnlockIfLockAppDidntShowWatchdogDuration",
               &Buf1.Data1) >= 0
          && Buf1.Data1 )
        {
          v12 = 10000LL * Buf1.Data1;
        }
        else
        {
          v12 = 180000000;
        }
        qword_1800D3F10 = v12;
      }
      *((_WORD *)pv + 249) = 0;
      pftDueTime = (struct _FILETIME)-v12;
      SetThreadpoolTimer(*((PTP_TIMER *)pv + 61), &pftDueTime, 0, 0);
    }
    wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v16, 0);
    if ( pv != (char *)-472LL )
      ReleaseSRWLockExclusive((PSRWLOCK)pv + 59);
    v6 = 0;
    goto LABEL_33;
  }
  v6 = wil::details::in1diag3::Return_GetLastError(
         retaddr,
         (void *)0x3A3,
         (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lockhost\\lockaction.cpp",
         v8);
  if ( pv != (char *)-472LL )
    ReleaseSRWLockExclusive((PSRWLOCK)pv + 59);
  LogonControllerTelemetry::CLockAction__CreateLockAppShownWatchdogTimer_Activity::~CLockAction__CreateLockAppShownWatchdogTimer_Activity((LogonControllerTelemetry::CLockAction__CreateLockAppShownWatchdogTimer_Activity *)&v16);
  return v6;
}

```

## disassembly

```asm
0x18002c8c4  push    rbp
0x18002c8c6  push    rbx
0x18002c8c7  push    rsi
0x18002c8c8  push    rdi
0x18002c8c9  push    r12
0x18002c8cb  push    r13
0x18002c8cd  push    r14
0x18002c8cf  push    r15
0x18002c8d1  lea     rbp, [rsp-118h]
0x18002c8d9  sub     rsp, 218h
0x18002c8e0  mov     rax, cs:__security_cookie
0x18002c8e7  xor     rax, rsp
0x18002c8ea  mov     [rbp+150h+var_48], rax
0x18002c8f1  mov     rdi, rcx
0x18002c8f4  lea     rax, ??_7?$ActivityBase@VLogonControllerLogger@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@6B@; const wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::`vftable'
0x18002c8fb  mov     [rsp+250h+var_210], rax
0x18002c900  xor     r12d, r12d
0x18002c903  mov     [rsp+250h+var_208], r12d
0x18002c908  mov     [rsp+250h+var_204], r12b
0x18002c90d  mov     [rbp+150h+var_1C8], r12b
0x18002c911  mov     [rsp+250h+var_1E0], r12d
0x18002c916  lea     rax, aClockactionCre_2; "CLockAction__CreateLockAppShownWatchdog"...
0x18002c91d  mov     [rsp+250h+var_1D8], rax
0x18002c922  mov     [rbp+150h+var_1D0], r12
0x18002c926  mov     [rbp+150h+var_1C0], r12d
0x18002c92a  xorps   xmm0, xmm0
0x18002c92d  movdqa  [rbp+150h+var_120], xmm0
0x18002c932  xor     edx, edx; Val
0x18002c934  mov     r8d, 98h; Size
0x18002c93a  lea     rcx, [rbp+150h+var_1B8]; void *
0x18002c93e  call    memset_0
0x18002c943  nop
0x18002c944  mov     [rbp+150h+var_110], 1
0x18002c94b  xor     eax, eax
0x18002c94d  mov     [rbp+150h+var_108], rax
0x18002c951  lea     rax, [rsp+250h+var_208]
0x18002c956  mov     [rbp+150h+var_100], rax
0x18002c95a  mov     [rbp+150h+var_F8], r12
0x18002c95e  xor     r9d, r9d; bool
0x18002c961  lea     r8, [rsp+250h+var_1E0]; struct wil::CallContextInfo *
0x18002c966  lea     rdx, [rsp+250h+var_210]; struct wil::details::IFailureCallback *
0x18002c96b  lea     rcx, [rbp+150h+var_F0]; this
0x18002c96f  call    ??0ThreadFailureCallbackHolder@details@wil@@QEAA@PEAUIFailureCallback@12@PEAUCallContextInfo@2@_N@Z; wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(wil::details::IFailureCallback *,wil::CallContextInfo *,bool)
0x18002c974  nop
0x18002c975  lea     r13, ??_7CLockAction__CreateLockAppShownWatchdogTimer_Activity@LogonControllerTelemetry@@6B@; const LogonControllerTelemetry::CLockAction__CreateLockAppShownWatchdogTimer_Activity::`vftable'
0x18002c97c  mov     [rsp+250h+var_210], r13
0x18002c981  lea     rcx, [rsp+250h+Buf1]; retstr
0x18002c986  call    ?GetFirstRunTelemetryCorrelationId@@YA?AU_GUID@@XZ; GetFirstRunTelemetryCorrelationId(void)
0x18002c98b  movups  xmm0, xmmword ptr [rax]
0x18002c98e  movdqu  [rsp+250h+Buf1], xmm0
0x18002c994  lea     r8d, [r12+10h]; Size
0x18002c999  lea     rdx, GUID_NULL; Buf2
0x18002c9a0  lea     rcx, [rsp+250h+Buf1]; Buf1
0x18002c9a5  call    memcmp_0
0x18002c9aa  test    eax, eax
0x18002c9ac  jz      short loc_18002C9BD
0x18002c9ae  lea     rdx, [rsp+250h+Buf1]
0x18002c9b3  lea     rcx, [rsp+250h+var_210]
0x18002c9b8  call    ?SetRelatedActivityId@?$ActivityBase@VLogonControllerLogger@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXAEBU_GUID@@@Z; wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivityId(_GUID const &)
0x18002c9bd  lea     rcx, [rsp+250h+var_210]; this
0x18002c9c2  call    ?StartActivity@CLockAction__CreateLockAppShownWatchdogTimer_Activity@LogonControllerTelemetry@@QEAAXXZ; LogonControllerTelemetry::CLockAction__CreateLockAppShownWatchdogTimer_Activity::StartActivity(void)
0x18002c9c7  lea     rsi, [rdi+1D8h]
0x18002c9ce  mov     rcx, rsi; SRWLock
0x18002c9d1  call    cs:__imp_AcquireSRWLockExclusive
0x18002c9d7  xor     r8d, r8d; pcbe
0x18002c9da  mov     rdx, rdi; pv
0x18002c9dd  lea     rcx, ?_s_LockAppShownWatchdogTimerExpired@CLockAction@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18002c9e4  call    cs:__imp_CreateThreadpoolTimer
0x18002c9ea  mov     r14, rax
0x18002c9ed  mov     r15, [rdi+1E0h]
0x18002c9f4  test    r15, r15
0x18002c9f7  jz      short loc_18002CA12
0x18002c9f9  call    cs:__imp_GetLastError
0x18002c9ff  mov     ebx, eax
0x18002ca01  mov     rcx, r15; pti
0x18002ca04  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x18002ca09  mov     ecx, ebx; dwErrCode
0x18002ca0b  call    cs:__imp_SetLastError
0x18002ca11  nop
0x18002ca12  mov     [rdi+1E0h], r14
0x18002ca19  test    r14, r14
0x18002ca1c  jnz     short loc_18002CA4F
0x18002ca1e  mov     rcx, [rbp+158h]; this
0x18002ca25  lea     r8, aPcshellShellAu_15; "pcshell\\shell\\auth\\authux\\controlle"...
0x18002ca2c  mov     edx, 39Eh; void *
0x18002ca31  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002ca36  mov     ebx, eax
0x18002ca38  test    rsi, rsi
0x18002ca3b  jz      loc_18002CC3A
0x18002ca41  mov     rcx, rsi; SRWLock
0x18002ca44  call    cs:__imp_ReleaseSRWLockExclusive
0x18002ca4a  jmp     loc_18002CC3A
0x18002ca4f  cmp     [rdi+235h], r12b
0x18002ca56  jz      short loc_18002CAB9
0x18002ca58  lea     rbx, [rdi+1E8h]
0x18002ca5f  xor     r8d, r8d; pcbe
0x18002ca62  mov     rdx, rdi; pv
0x18002ca65  lea     rcx, ?_s_UnlockIfLockAppDidntShowWatchdogTimerExpired@CLockAction@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18002ca6c  call    cs:__imp_CreateThreadpoolTimer
0x18002ca72  mov     rdx, rax
0x18002ca75  mov     rcx, rbx
0x18002ca78  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18002ca7d  cmp     [rbx], r12
0x18002ca80  jnz     short loc_18002CAB9
0x18002ca82  mov     rcx, [rbp+158h]; this
0x18002ca89  lea     r8, aPcshellShellAu_15; "pcshell\\shell\\auth\\authux\\controlle"...
0x18002ca90  mov     edx, 3A3h; void *
0x18002ca95  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002ca9a  mov     ebx, eax
0x18002ca9c  test    rsi, rsi
0x18002ca9f  jz      short loc_18002CAAA
0x18002caa1  mov     rcx, rsi; SRWLock
0x18002caa4  call    cs:__imp_ReleaseSRWLockExclusive
0x18002caaa  lea     rcx, [rsp+250h+var_210]; this
0x18002caaf  call    ??1CLockAction__CreateLockAppShownWatchdogTimer_Activity@LogonControllerTelemetry@@QEAA@XZ; LogonControllerTelemetry::CLockAction__CreateLockAppShownWatchdogTimer_Activity::~CLockAction__CreateLockAppShownWatchdogTimer_Activity(void)
0x18002cab4  jmp     loc_18002CC53
0x18002cab9  mov     [rdi+1F0h], r12w
0x18002cac1  mov     [rdi+138h], r12d
0x18002cac8  lea     rbx, [rdi+200h]
0x18002cacf  mov     rcx, rbx; SRWLock
0x18002cad2  call    cs:__imp_AcquireSRWLockExclusive
0x18002cad8  lea     r14, [rdi+1F8h]
0x18002cadf  cmp     [r14], r12
0x18002cae2  jnz     loc_18002CB6C
0x18002cae8  lea     rax, off_1800A1658
0x18002caef  mov     [rbp+150h+var_B8], rax
0x18002caf6  mov     [rbp+150h+var_B0], rdi
0x18002cafd  lea     rax, [rbp+150h+var_B8]
0x18002cb04  mov     [rbp+150h+var_50], rax
0x18002cb0b  mov     qword ptr [rsp+250h+Buf1], r12
0x18002cb10  lea     r9, [rsp+250h+Buf1]
0x18002cb15  lea     rdx, [rbp+150h+var_C0]
0x18002cb1c  call    ??$make_wnf_subscription_state@I@details@wil@@YAJAEBU_WNF_STATE_NAME@@$$QEAV?$function@$$A6AXAEBI@Z@wistd@@KPEAPEAU?$wnf_subscription_state@I@01@@Z; wil::details::make_wnf_subscription_state<uint>(_WNF_STATE_NAME const &,wistd::function<void (uint const &)> &&,ulong,wil::details::wnf_subscription_state<uint> * *)
0x18002cb21  test    eax, eax
0x18002cb23  js      short loc_18002CB31
0x18002cb25  mov     rax, qword ptr [rsp+250h+Buf1]
0x18002cb2a  mov     qword ptr [rsp+250h+Buf1], rax
0x18002cb2f  jmp     short loc_18002CB36
0x18002cb31  mov     qword ptr [rsp+250h+Buf1], r12
0x18002cb36  lea     rdx, [rsp+250h+Buf1]
0x18002cb3b  mov     rcx, r14
0x18002cb3e  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>> &&)
0x18002cb43  nop
0x18002cb44  mov     rcx, qword ptr [rsp+250h+Buf1]; this
0x18002cb49  test    rcx, rcx
0x18002cb4c  jz      short loc_18002CB54
0x18002cb4e  call    ?delete_wnf_subscription_state@details@wil@@YAXPEAUwnf_subscription_state_base@12@@Z; wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *)
0x18002cb53  nop
0x18002cb54  mov     rcx, [rbp+150h+var_50]
0x18002cb5b  test    rcx, rcx
0x18002cb5e  jz      short loc_18002CB6C
0x18002cb60  mov     rax, [rcx]
0x18002cb63  mov     rax, [rax+18h]
0x18002cb67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cb6c  test    rbx, rbx
0x18002cb6f  jz      short loc_18002CB7A
0x18002cb71  mov     rcx, rbx; SRWLock
0x18002cb74  call    cs:__imp_ReleaseSRWLockExclusive
0x18002cb7a  mov     qword ptr [rsp+250h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x18002cb83  xor     r9d, r9d; msWindowLength
0x18002cb86  xor     r8d, r8d; msPeriod
0x18002cb89  lea     rdx, [rsp+250h+pftDueTime]; pftDueTime
0x18002cb8e  mov     rcx, [rdi+1E0h]; pti
0x18002cb95  call    cs:__imp_SetThreadpoolTimer
0x18002cb9b  cmp     [rdi+235h], r12b
0x18002cba2  jz      short loc_18002CC1D
0x18002cba4  mov     rcx, cs:qword_1800D3F10
0x18002cbab  test    rcx, rcx
0x18002cbae  jnz     short loc_18002CBF5
0x18002cbb0  mov     dword ptr [rsp+250h+Buf1], r12d
0x18002cbb5  lea     r9, [rsp+250h+Buf1]; unsigned int *
0x18002cbba  lea     r8, aUnlockiflockap; "UnlockIfLockAppDidntShowWatchdogDuratio"...
0x18002cbc1  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18002cbc8  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x18002cbcf  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18002cbd4  test    eax, eax
0x18002cbd6  js      short loc_18002CBE9
0x18002cbd8  mov     eax, dword ptr [rsp+250h+Buf1]
0x18002cbdc  test    eax, eax
0x18002cbde  jz      short loc_18002CBE9
0x18002cbe0  imul    rcx, rax, 2710h
0x18002cbe7  jmp     short loc_18002CBEE
0x18002cbe9  mov     ecx, 0ABA9500h
0x18002cbee  mov     cs:qword_1800D3F10, rcx
0x18002cbf5  mov     [rdi+1F2h], r12w
0x18002cbfd  neg     rcx
0x18002cc00  mov     qword ptr [rsp+250h+pftDueTime.dwLowDateTime], rcx
0x18002cc05  xor     r9d, r9d; msWindowLength
0x18002cc08  xor     r8d, r8d; msPeriod
0x18002cc0b  lea     rdx, [rsp+250h+pftDueTime]; pftDueTime
0x18002cc10  mov     rcx, [rdi+1E8h]; pti
0x18002cc17  call    cs:__imp_SetThreadpoolTimer
0x18002cc1d  xor     edx, edx
0x18002cc1f  lea     rcx, [rsp+250h+var_210]
0x18002cc24  call    ?Stop@?$ActivityBase@VLogonControllerLogger@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18002cc29  test    rsi, rsi
0x18002cc2c  jz      short loc_18002CC37
0x18002cc2e  mov     rcx, rsi; SRWLock
0x18002cc31  call    cs:__imp_ReleaseSRWLockExclusive
0x18002cc37  mov     ebx, r12d
0x18002cc3a  mov     [rsp+250h+var_210], r13
0x18002cc3f  lea     rcx, [rsp+250h+var_210]
0x18002cc44  call    ?Destroy@?$ActivityBase@VLogonControllerLogger@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18002cc49  lea     rcx, [rsp+250h+var_210]
0x18002cc4e  call    ??1?$ActivityBase@VLogonControllerLogger@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18002cc53  mov     eax, ebx
0x18002cc55  mov     rcx, [rbp+150h+var_48]
0x18002cc5c  xor     rcx, rsp; StackCookie
0x18002cc5f  call    __security_check_cookie
0x18002cc64  add     rsp, 218h
0x18002cc6b  pop     r15
0x18002cc6d  pop     r14
0x18002cc6f  pop     r13
0x18002cc71  pop     r12
0x18002cc73  pop     rdi
0x18002cc74  pop     rsi
0x18002cc75  pop     rbx
0x18002cc76  pop     rbp
0x18002cc77  retn
```
