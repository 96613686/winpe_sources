# NetworkStatusMonitor::Invoke(IInspectable *)

- ea: `0x180034330`
- end: `0x180034664`
- name: `?Invoke@NetworkStatusMonitor@@UEAAJPEAUIInspectable@@@Z`
- size: `820`
- prototype: `__int64 __fastcall(PVOID Parameter, struct IInspectable *)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x18000b7a4`
- `0x180013b50`
- `0x180034330`
- `0x1800593bc`
- `0x18006a480`
- `0x18008a400`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003435f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800343f0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003435f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800343f0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003439b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180034453`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003461c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003439b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180034453`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003461c`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x1800344ad`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x1800344ee`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x1800344ad`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x1800344ee`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x1800345c2`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x1800345c2`
- `ext-ms-win-xblauth-console-l1-1-0!XblaIsConsole` at `0x18003458f`
- `ext-ms-win-xblauth-console-l1-1-0!XblaIsConsole` at `0x18003458f`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall NetworkStatusMonitor::Invoke(char *Parameter, struct IInspectable *a2)
{
  __int64 v3; // rbx
  struct _RTL_CRITICAL_SECTION *v4; // rdi
  const char *v5; // r9
  __int64 v6; // r14
  __int64 (__fastcall *v7)(__int64, __int64 *); // r14
  __int64 v8; // rcx
  int v9; // eax
  char v10; // r14
  int v11; // eax
  NetworkStatusMonitor *v12; // rcx
  int v13; // eax
  __int64 v14; // rcx
  __int64 result; // rax
  __time64_t v16; // rax
  BOOL TimerQueueTimer; // eax
  const char *v18; // r9
  __int64 v19; // rcx
  int DueTime; // [rsp+20h] [rbp-58h]
  DWORD Period[2]; // [rsp+28h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  int v23; // [rsp+80h] [rbp+8h] BYREF
  __int64 v24; // [rsp+90h] [rbp+18h] BYREF
  __int64 v25; // [rsp+98h] [rbp+20h]

  v23 = 0;
  v24 = 0;
  v3 = 0;
  v25 = 0;
  v4 = (struct _RTL_CRITICAL_SECTION *)(Parameter + 16);
  EnterCriticalSection((LPCRITICAL_SECTION)(Parameter + 16));
  try
  {
    if ( !Parameter[56] )
    {
      v6 = *((_QWORD *)Parameter + 10);
      if ( v6 )
      {
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v6 + 8LL))(*((_QWORD *)Parameter + 10));
        v3 = v6;
        v25 = v6;
      }
      if ( v4 )
        LeaveCriticalSection(v4);
      v7 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v3 + 56LL);
      v8 = v24;
      if ( v24 )
      {
        v24 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
      }
      v9 = v7(v3, &v24);
      if ( v9 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x62,
          (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\networkstatusmonitor.cpp",
          (const char *)(unsigned int)v9,
          DueTime);
      v10 = 0;
      EnterCriticalSection(v4);
      if ( !v24 )
      {
        *((_DWORD *)Parameter + 15) = 0;
        LogMessage(
          3u,
          "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\networkstatusmonitor.cpp",
          0x6Cu,
          "NetworkStatusMonitor::Invoke",
          (wchar_t *)L"Network connectivity level changed to 0x%x",
          0);
        goto LABEL_28;
      }
      v11 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v24 + 56LL))(v24, &v23);
      v12 = retaddr;
      if ( v11 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x71,
          (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\networkstatusmonitor.cpp",
          (const char *)(unsigned int)v11,
          DueTime);
      v13 = v23;
      if ( v23 >= 3 )
      {
        if ( *((_DWORD *)Parameter + 15) == v23 )
          goto LABEL_14;
        v16 = _time64(0) - *((_QWORD *)Parameter + 8);
        if ( v16 > 60 )
        {
          LogMessage(
            3u,
            "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\networkstatusmonitor.cpp",
            0x79u,
            "NetworkStatusMonitor::Invoke",
            (wchar_t *)L"Lease any offline running content after %d seconds",
            v16);
          *((_QWORD *)Parameter + 8) = _time64(0);
          v10 = 1;
        }
        Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(Parameter + 88);
        v13 = v23;
      }
      if ( *((_DWORD *)Parameter + 15) != v13 )
      {
        *((_DWORD *)Parameter + 15) = v13;
        Period[0] = v13;
        LogMessage(
          3u,
          "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\networkstatusmonitor.cpp",
          0x84u,
          "NetworkStatusMonitor::Invoke",
          (wchar_t *)L"Network connectivity level changed to 0x%x",
          *(_QWORD *)Period);
        v13 = v23;
      }
LABEL_14:
      if ( v13 >= 3 )
      {
LABEL_15:
        if ( v4 )
          LeaveCriticalSection(v4);
        if ( v10 )
          NetworkStatusMonitor::QueueLicenseRefresh(v12);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
        v14 = v24;
        if ( v24 )
        {
          v24 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
        }
        return 0;
      }
LABEL_28:
      if ( !*((_QWORD *)Parameter + 12) )
      {
        if ( (unsigned int)XblaIsConsole(v12) )
        {
          TimerQueueTimer = CreateTimerQueueTimer(
                              (PHANDLE)Parameter + 12,
                              0,
                              lambda_48949491746a0b2fe0637bd72432b555_::_lambda_invoker_cdecl_,
                              Parameter,
                              0x493E0u,
                              0,
                              8u);
          v12 = retaddr;
          if ( !TimerQueueTimer )
            wil::details::in1diag3::_Throw_GetLastError(
              retaddr,
              (void *)0x9E,
              (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\networkstatusmonitor.cpp",
              v18);
        }
      }
      goto LABEL_15;
    }
    *((_DWORD *)Parameter + 15) = 0;
    if ( v4 )
      LeaveCriticalSection(v4);
    v19 = v24;
    if ( v24 )
    {
      v24 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xA9,
                           (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\networkstatusmonitor.cpp",
                           v5);
  }
  return result;
}

```

## disassembly

```asm
0x180034330  mov     rax, rsp
0x180034333  mov     [rax+10h], rbx
0x180034337  push    rsi
0x180034338  push    rdi
0x180034339  push    r12
0x18003433b  push    r14
0x18003433d  push    r15
0x18003433f  sub     rsp, 50h
0x180034343  mov     rsi, rcx
0x180034346  xor     r12d, r12d
0x180034349  mov     [rax+8], r12d
0x18003434d  mov     [rax+18h], r12
0x180034351  mov     ebx, r12d
0x180034354  mov     [rax+20h], rbx
0x180034358  lea     rdi, [rcx+10h]
0x18003435c  mov     rcx, rdi; lpCriticalSection
0x18003435f  call    cs:__imp_EnterCriticalSection
0x180034365  cmp     [rsi+38h], r12b
0x180034369  jnz     loc_1800345E7
0x18003436f  mov     r14, [rsi+50h]
0x180034373  test    r14, r14
0x180034376  jz      short loc_180034393
0x180034378  mov     rax, [r14]
0x18003437b  mov     rcx, r14
0x18003437e  mov     rax, [rax+8]
0x180034382  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034387  nop
0x180034388  mov     rbx, r14
0x18003438b  mov     [rsp+78h+arg_18], rbx
0x180034393  test    rdi, rdi
0x180034396  jz      short loc_1800343A1
0x180034398  mov     rcx, rdi; lpCriticalSection
0x18003439b  call    cs:__imp_LeaveCriticalSection
0x1800343a1  mov     rax, [rbx]
0x1800343a4  mov     r14, [rax+38h]
0x1800343a8  mov     rcx, [rsp+78h+arg_10]
0x1800343b0  test    rcx, rcx
0x1800343b3  jz      short loc_1800343CA
0x1800343b5  mov     [rsp+78h+arg_10], r12
0x1800343bd  mov     rdx, [rcx]
0x1800343c0  mov     rax, [rdx+10h]
0x1800343c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800343c9  nop
0x1800343ca  lea     rdx, [rsp+78h+arg_10]
0x1800343d2  mov     rcx, rbx
0x1800343d5  mov     rax, r14
0x1800343d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800343dd  mov     rcx, [rsp+78h]; this
0x1800343e2  test    eax, eax
0x1800343e4  js      loc_180034624
0x1800343ea  xor     r14b, r14b
0x1800343ed  mov     rcx, rdi; lpCriticalSection
0x1800343f0  call    cs:__imp_EnterCriticalSection
0x1800343f6  mov     [rsp+78h+var_38], rdi
0x1800343fb  mov     rcx, [rsp+78h+arg_10]
0x180034403  test    rcx, rcx
0x180034406  jz      loc_180034551
0x18003440c  mov     rax, [rcx]
0x18003440f  lea     rdx, [rsp+78h+arg_0]
0x180034417  mov     rax, [rax+38h]
0x18003441b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034420  mov     rcx, [rsp+78h]; this
0x180034425  test    eax, eax
0x180034427  js      loc_180034639
0x18003442d  mov     eax, [rsp+78h+arg_0]
0x180034434  cmp     eax, 3
0x180034437  jl      loc_18003450B
0x18003443d  cmp     [rsi+3Ch], eax
0x180034440  jnz     short loc_1800344AB
0x180034442  cmp     eax, 3
0x180034445  jl      loc_180034584
0x18003444b  test    rdi, rdi
0x18003444e  jz      short loc_180034459
0x180034450  mov     rcx, rdi; lpCriticalSection
0x180034453  call    cs:__imp_LeaveCriticalSection
0x180034459  test    r14b, r14b
0x18003445c  jnz     loc_18003464E
0x180034462  mov     rax, [rbx]
0x180034465  mov     rcx, rbx
0x180034468  mov     rax, [rax+10h]
0x18003446c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034471  nop
0x180034472  mov     rcx, [rsp+78h+arg_10]
0x18003447a  test    rcx, rcx
0x18003447d  jz      short loc_180034494
0x18003447f  mov     [rsp+78h+arg_10], r12
0x180034487  mov     rax, [rcx]
0x18003448a  mov     rax, [rax+10h]
0x18003448e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034493  nop
0x180034494  xor     eax, eax
0x180034496  mov     rbx, [rsp+78h+arg_8]
0x18003449e  add     rsp, 50h
0x1800344a2  pop     r15
0x1800344a4  pop     r14
0x1800344a6  pop     r12
0x1800344a8  pop     rdi
0x1800344a9  pop     rsi
0x1800344aa  retn
0x1800344ab  xor     ecx, ecx; Time
0x1800344ad  call    cs:__imp__time64
0x1800344b3  sub     rax, [rsi+40h]
0x1800344b7  cmp     rax, 3Ch ; '<'
0x1800344bb  jle     short loc_1800344FB
0x1800344bd  mov     qword ptr [rsp+78h+Period], rax
0x1800344c2  lea     rax, aLeaseAnyOfflin; "Lease any offline running content after"...
0x1800344c9  mov     qword ptr [rsp+78h+DueTime], rax; Format
0x1800344ce  lea     r9, aNetworkstatusm; "NetworkStatusMonitor::Invoke"
0x1800344d5  mov     r8d, 79h ; 'y'; unsigned int
0x1800344db  lea     rdx, aOnecoreuapEndu_5; "onecoreuap\\enduser\\winstore\\licensem"...
0x1800344e2  mov     ecx, 3; unsigned int
0x1800344e7  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x1800344ec  xor     ecx, ecx; Time
0x1800344ee  call    cs:__imp__time64
0x1800344f4  mov     [rsi+40h], rax
0x1800344f8  mov     r14b, 1
0x1800344fb  lea     rcx, [rsi+58h]
0x1800344ff  call    ?Close@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(void)
0x180034504  mov     eax, [rsp+78h+arg_0]
0x18003450b  cmp     [rsi+3Ch], eax
0x18003450e  jz      loc_180034442
0x180034514  mov     [rsi+3Ch], eax
0x180034517  mov     [rsp+78h+Period], eax
0x18003451b  lea     rax, aNetworkConnect; "Network connectivity level changed to 0"...
0x180034522  mov     qword ptr [rsp+78h+DueTime], rax; Format
0x180034527  lea     r9, aNetworkstatusm; "NetworkStatusMonitor::Invoke"
0x18003452e  mov     r8d, 84h; unsigned int
0x180034534  lea     rdx, aOnecoreuapEndu_5; "onecoreuap\\enduser\\winstore\\licensem"...
0x18003453b  mov     ecx, 3; unsigned int
0x180034540  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x180034545  mov     eax, [rsp+78h+arg_0]
0x18003454c  jmp     loc_180034442
0x180034551  mov     [rsi+3Ch], r12d
0x180034555  mov     [rsp+78h+Period], r12d
0x18003455a  lea     rax, aNetworkConnect; "Network connectivity level changed to 0"...
0x180034561  mov     qword ptr [rsp+78h+DueTime], rax; Format
0x180034566  lea     r9, aNetworkstatusm; "NetworkStatusMonitor::Invoke"
0x18003456d  mov     r8d, 6Ch ; 'l'; unsigned int
0x180034573  lea     rdx, aOnecoreuapEndu_5; "onecoreuap\\enduser\\winstore\\licensem"...
0x18003457a  mov     ecx, 3; unsigned int
0x18003457f  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x180034584  cmp     qword ptr [rsi+60h], 0
0x180034589  jnz     loc_18003444B
0x18003458f  call    cs:__imp_XblaIsConsole
0x180034595  test    eax, eax
0x180034597  jz      loc_18003444B
0x18003459d  mov     [rsp+78h+Flags], 8; Flags
0x1800345a5  mov     [rsp+78h+Period], r12d; Period
0x1800345aa  mov     [rsp+78h+DueTime], 493E0h; DueTime
0x1800345b2  mov     r9, rsi; Parameter
0x1800345b5  lea     r8, _lambda_48949491746a0b2fe0637bd72432b555____lambda_invoker_cdecl_; Callback
0x1800345bc  xor     edx, edx; TimerQueue
0x1800345be  lea     rcx, [rsi+60h]; phNewTimer
0x1800345c2  call    cs:__imp_CreateTimerQueueTimer
0x1800345c8  mov     rcx, [rsp+78h]; this
0x1800345cd  test    eax, eax
0x1800345cf  jnz     loc_18003444B
0x1800345d5  lea     r8, aOnecoreuapEndu_5; "onecoreuap\\enduser\\winstore\\licensem"...
0x1800345dc  mov     edx, 9Eh; void *
0x1800345e1  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800345e7  mov     [rsi+3Ch], r12d
0x1800345eb  test    rdi, rdi
0x1800345ee  jnz     short loc_180034619
0x1800345f0  mov     rcx, [rsp+78h+arg_10]
0x1800345f8  test    rcx, rcx
0x1800345fb  jz      short loc_180034612
0x1800345fd  mov     [rsp+78h+arg_10], r12
0x180034605  mov     rax, [rcx]
0x180034608  mov     rax, [rax+10h]
0x18003460c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034611  nop
0x180034612  xor     eax, eax
0x180034614  jmp     loc_180034496
0x180034619  mov     rcx, rdi; lpCriticalSection
0x18003461c  call    cs:__imp_LeaveCriticalSection
0x180034622  jmp     short loc_1800345F0
0x180034624  mov     r9d, eax; char *
0x180034627  lea     r8, aOnecoreuapEndu_5; "onecoreuap\\enduser\\winstore\\licensem"...
0x18003462e  mov     edx, 62h ; 'b'; void *
0x180034633  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180034639  mov     r9d, eax; char *
0x18003463c  lea     r8, aOnecoreuapEndu_5; "onecoreuap\\enduser\\winstore\\licensem"...
0x180034643  mov     edx, 71h ; 'q'; void *
0x180034648  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003464e  call    ?QueueLicenseRefresh@NetworkStatusMonitor@@AEAAXXZ; NetworkStatusMonitor::QueueLicenseRefresh(void)
0x180034653  jmp     loc_180034462
0x180034658  mov     eax, [rsp+78h+arg_0]
0x18003465f  jmp     loc_180034496
```
