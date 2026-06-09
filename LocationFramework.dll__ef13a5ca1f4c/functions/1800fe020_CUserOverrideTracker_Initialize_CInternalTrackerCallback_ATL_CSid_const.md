# CUserOverrideTracker::Initialize(CInternalTrackerCallback *,ATL::CSid const &)

- ea: `0x1800fe020`
- end: `0x1800fe198`
- name: `?Initialize@CUserOverrideTracker@@QEAAJPEAVCInternalTrackerCallback@@AEBVCSid@ATL@@@Z`
- size: `376`
- prototype: `__int64 __fastcall(CUserOverrideTracker *__hidden this, struct CInternalTrackerCallback *, const struct ATL::CSid *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800fdebc`

## callees

- `0x1800234ec`
- `0x1800292ac`
- `0x180048a04`
- `0x18008c30c`
- `0x1800c2120`
- `0x1800fe020`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800fe043`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800fe098`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800fe0ed`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800fe043`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800fe098`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800fe0ed`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CUserOverrideTracker::Initialize(
        CUserOverrideTracker *this,
        struct CInternalTrackerCallback *a2,
        const struct ATL::CSid *a3)
{
  _QWORD *v6; // rbx
  HANDLE EventW; // rax
  HANDLE v8; // rax
  HANDLE v9; // rax
  int v10; // ebx
  const char *v12; // [rsp+28h] [rbp-70h]
  _QWORD v13[13]; // [rsp+30h] [rbp-68h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+98h] [rbp+0h]

  v6 = (_QWORD *)((char *)this + 384);
  EventW = CreateEventW(0, 0, 0, 0);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    v6,
    EventW);
  if ( !*v6 )
    wil::details::in1diag5::_Throw_GetLastError(
      retaddr,
      (void *)0xC,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\geofence\\geofencetracker\\useroverridetracker.cpp",
      "CUserOverrideTracker::Initialize",
      "m_workerExitEvent",
      v12);
  v8 = CreateEventW(0, 0, 0, 0);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    (char *)this + 392,
    v8);
  if ( !*((_QWORD *)this + 49) )
    wil::details::in1diag5::_Throw_GetLastError(
      retaddr,
      (void *)0xF,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\geofence\\geofencetracker\\useroverridetracker.cpp",
      "CUserOverrideTracker::Initialize",
      "m_trackingChangeEvent",
      v12);
  v9 = CreateEventW(0, 0, 0, 0);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    (char *)this + 400,
    v9);
  if ( !*((_QWORD *)this + 50) )
    wil::details::in1diag5::_Throw_GetLastError(
      retaddr,
      (void *)0x12,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\geofence\\geofencetracker\\useroverridetracker.cpp",
      "CUserOverrideTracker::Initialize",
      "m_sessionNotification",
      v12);
  v13[0] = &std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,long (CUserOverrideTracker::*)(void),CUserOverrideTracker *>,long,>::`vftable';
  v13[1] = CUserOverrideTracker::BackgroundWorkerThread;
  v13[2] = this;
  v13[7] = v13;
  v10 = CLocationWorker_Impl<0>::Initialize((char *)this + 200, v13);
  std::_Func_class<void,enum CLocationActivityDetector::ActivityType,bool>::_Tidy(v13);
  if ( v10 < 0 )
    return (unsigned int)v10;
  *((_QWORD *)this + 9) = a2;
  ATL::CSid::operator=((char *)this + 80, a3);
  return 0;
}

```

## disassembly

```asm
0x1800fe020  push    rbx
0x1800fe022  push    rbp
0x1800fe023  push    rsi
0x1800fe024  push    rdi
0x1800fe025  sub     rsp, 78h
0x1800fe029  mov     rsi, r8
0x1800fe02c  mov     rbp, rdx
0x1800fe02f  mov     rdi, rcx
0x1800fe032  lea     rbx, [rcx+180h]
0x1800fe039  xor     r9d, r9d; lpName
0x1800fe03c  xor     r8d, r8d; bInitialState
0x1800fe03f  xor     edx, edx; bManualReset
0x1800fe041  xor     ecx, ecx; lpEventAttributes
0x1800fe043  call    cs:__imp_CreateEventW
0x1800fe049  mov     rdx, rax
0x1800fe04c  mov     rcx, rbx
0x1800fe04f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800fe054  mov     rcx, [rsp+98h]; this
0x1800fe05c  cmp     qword ptr [rbx], 0
0x1800fe060  jnz     short loc_1800FE087
0x1800fe062  lea     rax, aMWorkerexiteve; "m_workerExitEvent"
0x1800fe069  mov     [rsp+98h+var_78], rax; char *
0x1800fe06e  lea     r9, aCuseroverridet_2; "CUserOverrideTracker::Initialize"
0x1800fe075  lea     r8, aOnecoreuapDriv_11; "onecoreuap\\drivers\\mobilepc\\location"...
0x1800fe07c  mov     edx, 0Ch; void *
0x1800fe081  call    ?_Throw_GetLastError@in1diag5@details@wil@@YAXPEAXIPEBD11@Z; wil::details::in1diag5::_Throw_GetLastError(void *,uint,char const *,char const *,char const *)
0x1800fe087  lea     rbx, [rdi+188h]
0x1800fe08e  xor     r9d, r9d; lpName
0x1800fe091  xor     r8d, r8d; bInitialState
0x1800fe094  xor     edx, edx; bManualReset
0x1800fe096  xor     ecx, ecx; lpEventAttributes
0x1800fe098  call    cs:__imp_CreateEventW
0x1800fe09e  mov     rdx, rax
0x1800fe0a1  mov     rcx, rbx
0x1800fe0a4  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800fe0a9  mov     rcx, [rsp+98h]; this
0x1800fe0b1  cmp     qword ptr [rbx], 0
0x1800fe0b5  jnz     short loc_1800FE0DC
0x1800fe0b7  lea     rax, aMTrackingchang; "m_trackingChangeEvent"
0x1800fe0be  mov     [rsp+98h+var_78], rax; char *
0x1800fe0c3  lea     r9, aCuseroverridet_2; "CUserOverrideTracker::Initialize"
0x1800fe0ca  lea     r8, aOnecoreuapDriv_11; "onecoreuap\\drivers\\mobilepc\\location"...
0x1800fe0d1  mov     edx, 0Fh; void *
0x1800fe0d6  call    ?_Throw_GetLastError@in1diag5@details@wil@@YAXPEAXIPEBD11@Z; wil::details::in1diag5::_Throw_GetLastError(void *,uint,char const *,char const *,char const *)
0x1800fe0dc  lea     rbx, [rdi+190h]
0x1800fe0e3  xor     r9d, r9d; lpName
0x1800fe0e6  xor     r8d, r8d; bInitialState
0x1800fe0e9  xor     edx, edx; bManualReset
0x1800fe0eb  xor     ecx, ecx; lpEventAttributes
0x1800fe0ed  call    cs:__imp_CreateEventW
0x1800fe0f3  mov     rdx, rax
0x1800fe0f6  mov     rcx, rbx
0x1800fe0f9  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800fe0fe  mov     rcx, [rsp+98h]; this
0x1800fe106  cmp     qword ptr [rbx], 0
0x1800fe10a  jnz     short loc_1800FE131
0x1800fe10c  lea     rax, aMSessionnotifi; "m_sessionNotification"
0x1800fe113  mov     [rsp+98h+var_78], rax; char *
0x1800fe118  lea     r9, aCuseroverridet_2; "CUserOverrideTracker::Initialize"
0x1800fe11f  lea     r8, aOnecoreuapDriv_11; "onecoreuap\\drivers\\mobilepc\\location"...
0x1800fe126  mov     edx, 12h; void *
0x1800fe12b  call    ?_Throw_GetLastError@in1diag5@details@wil@@YAXPEAXIPEBD11@Z; wil::details::in1diag5::_Throw_GetLastError(void *,uint,char const *,char const *,char const *)
0x1800fe131  lea     rax, ??_7?$_Func_impl_no_alloc@V?$_Binder@U_Unforced@std@@P8CUserOverrideTracker@@EAAJXZPEAV3@@std@@J$$V@std@@6B@; const std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,long (CUserOverrideTracker::*)(void),CUserOverrideTracker *>,long,>::`vftable'
0x1800fe138  mov     [rsp+98h+var_68], rax
0x1800fe13d  lea     rax, ?BackgroundWorkerThread@CUserOverrideTracker@@AEAAJXZ; CUserOverrideTracker::BackgroundWorkerThread(void)
0x1800fe144  mov     [rsp+98h+var_60], rax
0x1800fe149  mov     [rsp+98h+var_58], rdi
0x1800fe14e  lea     rax, [rsp+98h+var_68]
0x1800fe153  mov     [rsp+98h+var_30], rax
0x1800fe158  lea     rcx, [rdi+0C8h]
0x1800fe15f  lea     rdx, [rsp+98h+var_68]
0x1800fe164  call    ?Initialize@?$CLocationWorker_Impl@$0A@@@QEAAJAEBV?$function@$$A6AJXZ@std@@@Z; CLocationWorker_Impl<0>::Initialize(std::function<long (void)> const &)
0x1800fe169  mov     ebx, eax
0x1800fe16b  lea     rcx, [rsp+98h+var_68]
0x1800fe170  call    ?_Tidy@?$_Func_class@XW4ActivityType@CLocationActivityDetector@@_N@std@@IEAAXXZ; std::_Func_class<void,CLocationActivityDetector::ActivityType,bool>::_Tidy(void)
0x1800fe175  test    ebx, ebx
0x1800fe177  jns     short loc_1800FE17D
0x1800fe179  mov     eax, ebx
0x1800fe17b  jmp     short loc_1800FE18F
0x1800fe17d  mov     [rdi+48h], rbp
0x1800fe181  lea     rcx, [rdi+50h]
0x1800fe185  mov     rdx, rsi
0x1800fe188  call    ??4CSid@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSid::operator=(ATL::CSid const &)
0x1800fe18d  xor     eax, eax
0x1800fe18f  add     rsp, 78h
0x1800fe193  pop     rdi
0x1800fe194  pop     rsi
0x1800fe195  pop     rbp
0x1800fe196  pop     rbx
0x1800fe197  retn
```
