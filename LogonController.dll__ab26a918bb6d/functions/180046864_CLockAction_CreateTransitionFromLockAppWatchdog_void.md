# CLockAction::_CreateTransitionFromLockAppWatchdog(void)

- ea: `0x180046864`
- end: `0x180046aa9`
- name: `?_CreateTransitionFromLockAppWatchdog@CLockAction@@AEAAJXZ`
- size: `581`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x18008d4b0`

## callees

- `0x18001c56c`
- `0x18001c860`
- `0x18001d850`
- `0x18001db70`
- `0x18001f3a0`
- `0x180046864`
- `0x180046ab0`
- `0x18005b3e4`
- `0x18005d4e8`
- `0x18005f980`
- `0x18006c000`
- `0x18006cad0`
- `0x18009b790`

## import_xrefs

- `KERNEL32!CreateThreadpoolTimer` at `0x1800469a6`
- `KERNEL32!CreateThreadpoolTimer` at `0x1800469a6`
- `KERNEL32!SetThreadpoolTimer` at `0x180046a43`
- `KERNEL32!SetThreadpoolTimer` at `0x180046a43`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180046a02`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180046a5d`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180046a02`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180046a5d`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180046993`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180046993`
- `KERNEL32!SetLastError` at `0x1800469cd`
- `KERNEL32!SetLastError` at `0x1800469cd`
- `KERNEL32!GetLastError` at `0x1800469bb`
- `KERNEL32!GetLastError` at `0x1800469bb`

## string_xrefs

- `0x1800468da`: `CLockAction__CreateTransitionFromLockAppWatchdog_Activity`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CLockAction::_CreateTransitionFromLockAppWatchdog(PVOID pv)
{
  const char *v2; // r9
  struct _TP_TIMER *ThreadpoolTimer; // r14
  struct _TP_TIMER *v4; // r15
  DWORD LastError; // ebx
  unsigned int v6; // ebx
  struct _FILETIME pftDueTime; // [rsp+20h] [rbp-E0h] BYREF
  struct _GUID Buf1; // [rsp+28h] [rbp-D8h] BYREF
  void **v10; // [rsp+40h] [rbp-C0h] BYREF
  int v11; // [rsp+48h] [rbp-B8h] BYREF
  char v12; // [rsp+4Ch] [rbp-B4h]
  int v13; // [rsp+70h] [rbp-90h] BYREF
  const char *v14; // [rsp+78h] [rbp-88h]
  __int64 v15; // [rsp+80h] [rbp-80h]
  char v16; // [rsp+88h] [rbp-78h]
  int v17; // [rsp+90h] [rbp-70h]
  _BYTE v18[152]; // [rsp+98h] [rbp-68h] BYREF
  __int128 v19; // [rsp+130h] [rbp+30h]
  int v20; // [rsp+140h] [rbp+40h]
  __int64 v21; // [rsp+148h] [rbp+48h]
  int *v22; // [rsp+150h] [rbp+50h]
  __int64 v23; // [rsp+158h] [rbp+58h]
  _BYTE v24[48]; // [rsp+160h] [rbp+60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+C8h]

  if ( !*((_BYTE *)pv + 564) || _InterlockedCompareExchange16((volatile signed __int16 *)pv + 281, 1, 0) )
    return 0;
  v10 = &wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::`vftable';
  v11 = 0;
  v12 = 0;
  v16 = 0;
  v13 = 0;
  v14 = "CLockAction__CreateTransitionFromLockAppWatchdog_Activity";
  v15 = 0;
  v17 = 0;
  v19 = 0;
  memset_0(v18, 0, sizeof(v18));
  v20 = 1;
  v21 = 0;
  v22 = &v11;
  v23 = 0;
  wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(
    (wil::details::ThreadFailureCallbackHolder *)v24,
    (struct wil::details::IFailureCallback *)&v10,
    (struct wil::CallContextInfo *)&v13,
    0);
  v10 = &LogonControllerTelemetry::CLockAction__CreateTransitionFromLockAppWatchdog_Activity::`vftable';
  Buf1 = *GetFirstRunTelemetryCorrelationId(&Buf1);
  if ( memcmp_0(&Buf1, &GUID_NULL, 0x10u) )
    wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivityId(
      &v10,
      &Buf1);
  LogonControllerTelemetry::CLockAction__CreateTransitionFromLockAppWatchdog_Activity::StartActivity((LogonControllerTelemetry::CLockAction__CreateTransitionFromLockAppWatchdog_Activity *)&v10);
  AcquireSRWLockExclusive((PSRWLOCK)pv + 66);
  ThreadpoolTimer = CreateThreadpoolTimer(CLockAction::_s_TransitionFromLockAppWatchdogTimerExpired, pv, 0);
  v4 = (struct _TP_TIMER *)*((_QWORD *)pv + 67);
  if ( v4 )
  {
    LastError = GetLastError();
    wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(v4);
    SetLastError(LastError);
  }
  *((_QWORD *)pv + 67) = ThreadpoolTimer;
  if ( ThreadpoolTimer )
  {
    *((_BYTE *)pv + 544) = 0;
    pftDueTime = (struct _FILETIME)-50000000LL;
    SetThreadpoolTimer(ThreadpoolTimer, &pftDueTime, 0, 0);
    wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v10, 0);
    if ( pv != (PVOID)-528LL )
      ReleaseSRWLockExclusive((PSRWLOCK)pv + 66);
    v10 = &LogonControllerTelemetry::CLockAction__CreateTransitionFromLockAppWatchdog_Activity::`vftable';
    wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v10);
    wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(&v10);
    return 0;
  }
  v6 = wil::details::in1diag3::Return_GetLastError(
         retaddr,
         (void *)0x4DF,
         (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lockhost\\lockaction.cpp",
         v2);
  if ( pv != (PVOID)-528LL )
    ReleaseSRWLockExclusive((PSRWLOCK)pv + 66);
  v10 = &LogonControllerTelemetry::CLockAction__CreateTransitionFromLockAppWatchdog_Activity::`vftable';
  wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v10);
  wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(&v10);
  return v6;
}

```

## disassembly

```asm
0x180046864  mov     [rsp-8+arg_8], rbx
0x180046869  mov     [rsp-8+arg_10], rsi
0x18004686e  push    rbp
0x18004686f  push    rdi
0x180046870  push    r13
0x180046872  push    r14
0x180046874  push    r15
0x180046876  lea     rbp, [rsp-0A0h]
0x18004687e  sub     rsp, 1A0h
0x180046885  mov     rax, cs:__security_cookie
0x18004688c  xor     rax, rsp
0x18004688f  mov     [rbp+0C0h+var_30], rax
0x180046896  mov     rdi, rcx
0x180046899  cmp     byte ptr [rcx+234h], 0
0x1800468a0  jz      loc_180046A7C
0x1800468a6  xor     eax, eax
0x1800468a8  lea     ebx, [rax+1]
0x1800468ab  lock cmpxchg [rcx+232h], bx
0x1800468b4  xor     ecx, ecx
0x1800468b6  cmp     cx, ax
0x1800468b9  jnz     loc_180046A7C
0x1800468bf  lea     rax, ??_7?$ActivityBase@VLogonControllerLogger@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@6B@; const wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::`vftable'
0x1800468c6  mov     [rsp+1C0h+var_180], rax
0x1800468cb  mov     [rsp+1C0h+var_178], ecx
0x1800468cf  mov     [rsp+1C0h+var_174], cl
0x1800468d3  mov     [rbp+0C0h+var_138], cl
0x1800468d6  mov     [rsp+1C0h+var_150], ecx
0x1800468da  lea     rax, aClockactionCre; "CLockAction__CreateTransitionFromLockAp"...
0x1800468e1  mov     [rsp+1C0h+var_148], rax
0x1800468e6  mov     [rbp+0C0h+var_140], rcx
0x1800468ea  mov     [rbp+0C0h+var_130], ecx
0x1800468ed  xorps   xmm0, xmm0
0x1800468f0  movdqa  [rbp+0C0h+var_90], xmm0
0x1800468f5  xor     edx, edx; Val
0x1800468f7  mov     r8d, 98h; Size
0x1800468fd  lea     rcx, [rbp+0C0h+var_128]; void *
0x180046901  call    memset_0
0x180046906  nop
0x180046907  mov     [rbp+0C0h+var_80], ebx
0x18004690a  xor     eax, eax
0x18004690c  mov     [rbp+0C0h+var_78], rax
0x180046910  lea     rax, [rsp+1C0h+var_178]
0x180046915  mov     [rbp+0C0h+var_70], rax
0x180046919  mov     [rbp+0C0h+var_68], 0
0x180046921  xor     r9d, r9d; bool
0x180046924  lea     r8, [rsp+1C0h+var_150]; struct wil::CallContextInfo *
0x180046929  lea     rdx, [rsp+1C0h+var_180]; struct wil::details::IFailureCallback *
0x18004692e  lea     rcx, [rbp+0C0h+var_60]; this
0x180046932  call    ??0ThreadFailureCallbackHolder@details@wil@@QEAA@PEAUIFailureCallback@12@PEAUCallContextInfo@2@_N@Z; wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(wil::details::IFailureCallback *,wil::CallContextInfo *,bool)
0x180046937  nop
0x180046938  lea     r13, ??_7CLockAction__CreateTransitionFromLockAppWatchdog_Activity@LogonControllerTelemetry@@6B@; const LogonControllerTelemetry::CLockAction__CreateTransitionFromLockAppWatchdog_Activity::`vftable'
0x18004693f  mov     [rsp+1C0h+var_180], r13
0x180046944  lea     rcx, [rsp+1C0h+Buf1]; retstr
0x180046949  call    ?GetFirstRunTelemetryCorrelationId@@YA?AU_GUID@@XZ; GetFirstRunTelemetryCorrelationId(void)
0x18004694e  movups  xmm0, xmmword ptr [rax]
0x180046951  movdqu  xmmword ptr [rsp+1C0h+Buf1.Data1], xmm0
0x180046957  lea     r8d, [rbx+0Fh]; Size
0x18004695b  lea     rdx, GUID_NULL; Buf2
0x180046962  lea     rcx, [rsp+1C0h+Buf1]; Buf1
0x180046967  call    memcmp_0
0x18004696c  test    eax, eax
0x18004696e  jz      short loc_18004697F
0x180046970  lea     rdx, [rsp+1C0h+Buf1]
0x180046975  lea     rcx, [rsp+1C0h+var_180]
0x18004697a  call    ?SetRelatedActivityId@?$ActivityBase@VLogonControllerLogger@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXAEBU_GUID@@@Z; wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivityId(_GUID const &)
0x18004697f  lea     rcx, [rsp+1C0h+var_180]; this
0x180046984  call    ?StartActivity@CLockAction__CreateTransitionFromLockAppWatchdog_Activity@LogonControllerTelemetry@@QEAAXXZ; LogonControllerTelemetry::CLockAction__CreateTransitionFromLockAppWatchdog_Activity::StartActivity(void)
0x180046989  lea     rsi, [rdi+210h]
0x180046990  mov     rcx, rsi; SRWLock
0x180046993  call    cs:__imp_AcquireSRWLockExclusive
0x180046999  xor     r8d, r8d; pcbe
0x18004699c  mov     rdx, rdi; pv
0x18004699f  lea     rcx, ?_s_TransitionFromLockAppWatchdogTimerExpired@CLockAction@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800469a6  call    cs:__imp_CreateThreadpoolTimer
0x1800469ac  mov     r14, rax
0x1800469af  mov     r15, [rdi+218h]
0x1800469b6  test    r15, r15
0x1800469b9  jz      short loc_1800469D4
0x1800469bb  call    cs:__imp_GetLastError
0x1800469c1  mov     ebx, eax
0x1800469c3  mov     rcx, r15; pti
0x1800469c6  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x1800469cb  mov     ecx, ebx; dwErrCode
0x1800469cd  call    cs:__imp_SetLastError
0x1800469d3  nop
0x1800469d4  mov     [rdi+218h], r14
0x1800469db  test    r14, r14
0x1800469de  jnz     short loc_180046A25
0x1800469e0  mov     rcx, [rbp+0C8h]; this
0x1800469e7  lea     r8, aPcshellShellAu_15; "pcshell\\shell\\auth\\authux\\controlle"...
0x1800469ee  mov     edx, 4DFh; void *
0x1800469f3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800469f8  mov     ebx, eax
0x1800469fa  test    rsi, rsi
0x1800469fd  jz      short loc_180046A08
0x1800469ff  mov     rcx, rsi; SRWLock
0x180046a02  call    cs:__imp_ReleaseSRWLockExclusive
0x180046a08  mov     [rsp+1C0h+var_180], r13
0x180046a0d  lea     rcx, [rsp+1C0h+var_180]
0x180046a12  call    ?Destroy@?$ActivityBase@VLogonControllerLogger@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180046a17  lea     rcx, [rsp+1C0h+var_180]
0x180046a1c  call    ??1?$ActivityBase@VLogonControllerLogger@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180046a21  mov     eax, ebx
0x180046a23  jmp     short loc_180046A7E
0x180046a25  mov     byte ptr [rdi+220h], 0
0x180046a2c  mov     qword ptr [rsp+1C0h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x180046a35  xor     r9d, r9d; msWindowLength
0x180046a38  xor     r8d, r8d; msPeriod
0x180046a3b  lea     rdx, [rsp+1C0h+pftDueTime]; pftDueTime
0x180046a40  mov     rcx, r14; pti
0x180046a43  call    cs:__imp_SetThreadpoolTimer
0x180046a49  xor     edx, edx
0x180046a4b  lea     rcx, [rsp+1C0h+var_180]
0x180046a50  call    ?Stop@?$ActivityBase@VLogonControllerLogger@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180046a55  test    rsi, rsi
0x180046a58  jz      short loc_180046A63
0x180046a5a  mov     rcx, rsi; SRWLock
0x180046a5d  call    cs:__imp_ReleaseSRWLockExclusive
0x180046a63  mov     [rsp+1C0h+var_180], r13
0x180046a68  lea     rcx, [rsp+1C0h+var_180]
0x180046a6d  call    ?Destroy@?$ActivityBase@VLogonControllerLogger@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180046a72  lea     rcx, [rsp+1C0h+var_180]
0x180046a77  call    ??1?$ActivityBase@VLogonControllerLogger@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180046a7c  xor     eax, eax
0x180046a7e  mov     rcx, [rbp+0C0h+var_30]
0x180046a85  xor     rcx, rsp; StackCookie
0x180046a88  call    __security_check_cookie
0x180046a8d  lea     r11, [rsp+1C0h+var_20]
0x180046a95  mov     rbx, [r11+38h]
0x180046a99  mov     rsi, [r11+40h]
0x180046a9d  mov     rsp, r11
0x180046aa0  pop     r15
0x180046aa2  pop     r14
0x180046aa4  pop     r13
0x180046aa6  pop     rdi
0x180046aa7  pop     rbp
0x180046aa8  retn
```
