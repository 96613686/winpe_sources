# WorkerTaskResuming::RunTask(void)

- ea: `0x140183200`
- end: `0x14018354a`
- name: `?RunTask@WorkerTaskResuming@@UEAAXXZ`
- size: `842`
- prototype: `void __fastcall(WorkerTaskResuming *__hidden this)`
- caller_count: `0`
- callee_count: `16`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x14002ecd0`
- `0x140032f40`
- `0x140042240`
- `0x1400549dc`
- `0x14005dbd0`
- `0x140078c98`
- `0x1400941dc`
- `0x1400dbe4c`
- `0x1400df13c`
- `0x1400eb528`
- `0x1400f6660`
- `0x14012f68c`
- `0x140132940`
- `0x140170f7c`
- `0x140183200`
- `0x1402c2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1401833ea`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1401833ea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140183429`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140183429`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14018331e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14018331e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140183405`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140183405`
- `vmprox!GetVmErrInfo` at `0x140183500`
- `vmprox!GetVmErrInfo` at `0x140183500`
- `vid!VidSuspendClear` at `0x1401832d8`
- `vid!VidSuspendClear` at `0x1401832d8`

## string_xrefs

- `0x1401832f6`: `onecore\vm\worker\wpcore\workertaskresuming.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall WorkerTaskResuming::RunTask(WorkerTaskResuming *this)
{
  VirtualMachine *v2; // rcx
  signed int started; // ebx
  __int64 v4; // rcx
  int v5; // edi
  int v6; // ebx
  unsigned int v7; // r14d
  __int64 v8; // rcx
  __int64 v9; // rax
  signed int LastError; // eax
  int v11; // eax
  __int64 v12; // rcx
  __int64 v13; // rbx
  __int64 v14; // rcx
  __int64 VmErrInfo; // rax
  int v16; // [rsp+20h] [rbp-48h]
  struct IUnknown *v17; // [rsp+30h] [rbp-38h] BYREF
  __int64 v18; // [rsp+38h] [rbp-30h] BYREF
  __int64 VmName; // [rsp+40h] [rbp-28h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+48h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+30h]

  v17 = 0;
  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)this + 2) + 1040LL) + 608LL))(*(_QWORD *)(*((_QWORD *)this + 2) + 1040LL));
  if ( *((_DWORD *)this + 100) == 19 )
  {
    v2 = (VirtualMachine *)*((_QWORD *)this + 2);
    if ( *((_DWORD *)v2 + 586) == 4 )
    {
      started = VirtualMachine::ValidateRecovery(v2);
      if ( started < 0 )
        goto LABEL_14;
    }
  }
  v4 = *((_QWORD *)this + 2);
  v5 = *(_DWORD *)(v4 + 2344);
  v6 = 5;
  if ( v5 != 4 )
    v6 = 0;
  v7 = v6 | 0x100;
  if ( !(*(unsigned __int8 (__fastcall **)(_QWORD))(**(_QWORD **)(v4 + 1040) + 504LL))(*(_QWORD *)(v4 + 1040)) )
    v7 = v6;
  v8 = *((_QWORD *)this + 2);
  if ( *(_DWORD *)(v8 + 2620) )
  {
    v9 = (**(__int64 (__fastcall ***)(__int64))(*(_QWORD *)(v8 + 1024) + 24LL))(*(_QWORD *)(v8 + 1024) + 24LL);
    if ( !(unsigned int)VidSuspendClear(v9) )
    {
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x7C,
        (unsigned int)"onecore\\vm\\worker\\wpcore\\workertaskresuming.cpp",
        (const char *)0x8000FFFFLL,
        v16);
      if ( (unsigned int)VmlIsDebugTraceEnabled(0) )
        VmlDebugTraceEx(0, &off_1402D9CB8);
      LastError = GetLastError();
      started = LastError;
      if ( LastError > 0 )
        started = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_14;
    }
    *(_DWORD *)(*((_QWORD *)this + 2) + 2620LL) = 0;
    v8 = *((_QWORD *)this + 2);
  }
  if ( v5 == 4 )
    VirtualMotherboard::NotifyVmResumedFromCriticalError(*(VirtualMotherboard **)(v8 + 984));
  started = VirtualMachine::StartVm(*((_QWORD *)this + 2), v7, 5 - (unsigned int)(v5 != 4));
  if ( started >= 0 )
  {
    v13 = *((_QWORD *)this + 2);
    EnterCriticalSection((LPCRITICAL_SECTION)(v13 + 2456));
    SetThreadpoolTimer(*(PTP_TIMER *)(v13 + 2496), 0, 0, 0);
    *(_QWORD *)(v13 + 2504) = 0;
    *(_DWORD *)(v13 + 2512) = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)(v13 + 2456));
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)this + 2) + 1064LL) + 72LL))(*(_QWORD *)(*((_QWORD *)this + 2) + 1064LL));
    VirtualMachine::SetState(*((_QWORD *)this + 2), 2, *((unsigned int *)this + 100));
    started = 0;
    v11 = *((_DWORD *)this + 100);
    goto LABEL_15;
  }
LABEL_14:
  v11 = *((_DWORD *)this + 100);
  if ( started >= 0 )
  {
LABEL_15:
    EventDescriptor = (EVENT_DESCRIPTOR)MSVM_RESUME_SUCCESS;
    if ( v11 == 20 )
      EventDescriptor = (EVENT_DESCRIPTOR)MSVM_RESUME_CRITICAL_SUCCESS;
    v12 = *((_QWORD *)this + 2);
    v18 = v12 + 1152;
    VmName = (__int64)VirtualMachine::GetVmName((VirtualMachine *)(v12 + 16));
    VmEventWrite<unsigned short const *,unsigned short const *>(&EventDescriptor, 1u, (__int64)&v18);
    goto LABEL_26;
  }
  EventDescriptor = (EVENT_DESCRIPTOR)MSVMB_WP_RESUME_ERROR;
  if ( v11 == 20 )
    EventDescriptor = (EVENT_DESCRIPTOR)MSVMB_WP_RESUME_CRITICAL_ERROR;
  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)this + 2) + 1040LL) + 600LL))(*(_QWORD *)(*((_QWORD *)this + 2) + 1040LL));
  VirtualMachine::SetState(
    *((_QWORD *)this + 2),
    4 - (unsigned int)(*(_DWORD *)(*((_QWORD *)this + 2) + 2344LL) != 4),
    21);
  v14 = *((_QWORD *)this + 2);
  VmName = v14 + 1152;
  v18 = (__int64)VirtualMachine::GetVmName((VirtualMachine *)(v14 + 16));
  VmEventWriteAndReport<unsigned short const *,unsigned short const *>(
    &EventDescriptor,
    0xDu,
    (__int64)&v18,
    (__int64)&VmName);
LABEL_26:
  VmErrInfo = GetVmErrInfo();
  Vml::VmComPtr<IVmSimpleTask>::Attach<IVmSimpleTask>(&v17, VmErrInfo);
  WorkerAsyncTaskBase::SetStatusComplete(this, started, v17);
  Vml::VmComPtr<IVmMetricValueSink>::~VmComPtr<IVmMetricValueSink>(&v17);
}

```

## disassembly

```asm
0x140183200  push    rbp
0x140183202  push    rbx
0x140183203  push    rsi
0x140183204  push    rdi
0x140183205  push    r14
0x140183207  push    r15
0x140183209  mov     rbp, rsp
0x14018320c  sub     rsp, 68h
0x140183210  mov     rax, cs:__security_cookie
0x140183217  xor     rax, rsp
0x14018321a  mov     [rbp+var_10], rax
0x14018321e  mov     rsi, rcx
0x140183221  mov     [rbp+var_38], 0
0x140183229  mov     rax, [rcx+10h]
0x14018322d  mov     rcx, [rax+410h]
0x140183234  mov     rax, [rcx]
0x140183237  mov     rax, [rax+260h]
0x14018323e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140183243  cmp     dword ptr [rsi+190h], 13h
0x14018324a  jnz     short loc_140183268
0x14018324c  mov     rcx, [rsi+10h]; this
0x140183250  cmp     dword ptr [rcx+928h], 4
0x140183257  jnz     short loc_140183268
0x140183259  call    ?ValidateRecovery@VirtualMachine@@QEAAJXZ; VirtualMachine::ValidateRecovery(void)
0x14018325e  mov     ebx, eax
0x140183260  test    eax, eax
0x140183262  js      loc_140183339
0x140183268  mov     rcx, [rsi+10h]
0x14018326c  mov     edi, [rcx+928h]
0x140183272  lea     eax, [rdi-4]
0x140183275  neg     eax
0x140183277  sbb     r15d, r15d
0x14018327a  mov     ebx, 5
0x14018327f  add     r15d, ebx
0x140183282  xor     eax, eax
0x140183284  cmp     edi, 4
0x140183287  cmovnz  ebx, eax
0x14018328a  mov     rcx, [rcx+410h]
0x140183291  mov     rax, [rcx]
0x140183294  mov     rax, [rax+1F8h]
0x14018329b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401832a0  mov     r14d, ebx
0x1401832a3  bts     r14d, 8
0x1401832a8  test    al, al
0x1401832aa  cmovz   r14d, ebx
0x1401832ae  mov     rcx, [rsi+10h]
0x1401832b2  cmp     dword ptr [rcx+0A3Ch], 0
0x1401832b9  jz      loc_1401833B2
0x1401832bf  mov     rcx, [rcx+400h]
0x1401832c6  add     rcx, 18h
0x1401832ca  mov     rax, [rcx]
0x1401832cd  mov     rax, [rax]
0x1401832d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401832d5  mov     rcx, rax
0x1401832d8  call    cs:__imp_VidSuspendClear
0x1401832df  nop     dword ptr [rax+rax+00h]
0x1401832e4  test    eax, eax
0x1401832e6  jnz     loc_1401833A0
0x1401832ec  mov     rcx, [rbp+30h]; this
0x1401832f0  mov     r9d, 8000FFFFh; char *
0x1401832f6  lea     r8, aOnecoreVmWorke_38; "onecore\\vm\\worker\\wpcore\\workertask"...
0x1401832fd  lea     edx, [rax+7Ch]; void *
0x140183300  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x140183305  xor     ecx, ecx
0x140183307  call    VmlIsDebugTraceEnabled
0x14018330c  test    eax, eax
0x14018330e  jz      short loc_14018331E
0x140183310  lea     rdx, off_1402D9CB8; "Unexpected error.\n"
0x140183317  xor     ecx, ecx
0x140183319  call    VmlDebugTraceEx
0x14018331e  call    cs:__imp_GetLastError
0x140183325  nop     dword ptr [rax+rax+00h]
0x14018332a  mov     ebx, eax
0x14018332c  test    eax, eax
0x14018332e  jle     short loc_140183339
0x140183330  movzx   ebx, ax
0x140183333  or      ebx, 80070000h
0x140183339  mov     eax, [rsi+190h]
0x14018333f  test    ebx, ebx
0x140183341  js      loc_14018346E
0x140183347  movups  xmm0, cs:MSVM_RESUME_SUCCESS
0x14018334e  movdqu  xmmword ptr [rbp+EventDescriptor.Id], xmm0
0x140183353  cmp     eax, 14h
0x140183356  jnz     short loc_140183364
0x140183358  movups  xmm0, cs:MSVM_RESUME_CRITICAL_SUCCESS
0x14018335f  movdqu  xmmword ptr [rbp+EventDescriptor.Id], xmm0
0x140183364  mov     rcx, [rsi+10h]
0x140183368  lea     rax, [rcx+480h]
0x14018336f  mov     [rbp+var_30], rax
0x140183373  add     rcx, 10h; this
0x140183377  call    ?GetVmName@VirtualMachine@@UEBAPEBGXZ; VirtualMachine::GetVmName(void)
0x14018337c  mov     [rbp+var_28], rax
0x140183380  lea     rax, [rbp+var_30]
0x140183384  mov     [rsp+68h+var_48], rax; __int64
0x140183389  lea     r9, [rbp+var_28]
0x14018338d  mov     edx, 1; unsigned int
0x140183392  lea     rcx, [rbp+EventDescriptor]; EventDescriptor
0x140183396  call    ??$VmEventWrite@PEBGPEBG@@YAXPEBU_EVENT_DESCRIPTOR@@IAEBU_GUID@@$$QEAPEBG2@Z; VmEventWrite<ushort const *,ushort const *>(_EVENT_DESCRIPTOR const *,uint,_GUID const &,ushort const * &&,ushort const * &&)
0x14018339b  jmp     loc_140183500
0x1401833a0  mov     rax, [rsi+10h]
0x1401833a4  mov     dword ptr [rax+0A3Ch], 0
0x1401833ae  mov     rcx, [rsi+10h]
0x1401833b2  cmp     edi, 4
0x1401833b5  jnz     short loc_1401833C3
0x1401833b7  mov     rcx, [rcx+3D8h]; this
0x1401833be  call    ?NotifyVmResumedFromCriticalError@VirtualMotherboard@@QEAAJXZ; VirtualMotherboard::NotifyVmResumedFromCriticalError(void)
0x1401833c3  mov     r8d, r15d
0x1401833c6  mov     edx, r14d
0x1401833c9  mov     rcx, [rsi+10h]
0x1401833cd  call    ?StartVm@VirtualMachine@@QEAAJIW4__MIDL___MIDL_itf_vmbservices_0000_0011_0002@@@Z; VirtualMachine::StartVm(uint,__MIDL___MIDL_itf_vmbservices_0000_0011_0002)
0x1401833d2  mov     ebx, eax
0x1401833d4  test    eax, eax
0x1401833d6  js      loc_140183339
0x1401833dc  mov     rbx, [rsi+10h]
0x1401833e0  lea     rdi, [rbx+998h]
0x1401833e7  mov     rcx, rdi; lpCriticalSection
0x1401833ea  call    cs:__imp_EnterCriticalSection
0x1401833f1  nop     dword ptr [rax+rax+00h]
0x1401833f6  xor     r9d, r9d; msWindowLength
0x1401833f9  xor     r8d, r8d; msPeriod
0x1401833fc  xor     edx, edx; pftDueTime
0x1401833fe  mov     rcx, [rbx+9C0h]; pti
0x140183405  call    cs:__imp_SetThreadpoolTimer
0x14018340c  nop     dword ptr [rax+rax+00h]
0x140183411  mov     qword ptr [rbx+9C8h], 0
0x14018341c  mov     dword ptr [rbx+9D0h], 0
0x140183426  mov     rcx, rdi; lpCriticalSection
0x140183429  call    cs:__imp_LeaveCriticalSection
0x140183430  nop     dword ptr [rax+rax+00h]
0x140183435  mov     rax, [rsi+10h]
0x140183439  mov     rcx, [rax+428h]
0x140183440  mov     rax, [rcx]
0x140183443  mov     rax, [rax+48h]
0x140183447  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14018344c  mov     r8d, [rsi+190h]
0x140183453  mov     edx, 2
0x140183458  mov     rcx, [rsi+10h]
0x14018345c  call    ?SetState@VirtualMachine@@QEAAHW4_VM_STATE@@W4_VM_STATE_REASON_CODE@@@Z; VirtualMachine::SetState(_VM_STATE,_VM_STATE_REASON_CODE)
0x140183461  xor     ebx, ebx
0x140183463  mov     eax, [rsi+190h]
0x140183469  jmp     loc_140183347
0x14018346e  movups  xmm0, cs:MSVMB_WP_RESUME_ERROR
0x140183475  movdqu  xmmword ptr [rbp+EventDescriptor.Id], xmm0
0x14018347a  cmp     eax, 14h
0x14018347d  jnz     short loc_14018348B
0x14018347f  movups  xmm0, cs:MSVMB_WP_RESUME_CRITICAL_ERROR
0x140183486  movdqu  xmmword ptr [rbp+EventDescriptor.Id], xmm0
0x14018348b  mov     rax, [rsi+10h]
0x14018348f  mov     rcx, [rax+410h]
0x140183496  mov     rax, [rcx]
0x140183499  mov     rax, [rax+258h]
0x1401834a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401834a5  mov     rcx, [rsi+10h]
0x1401834a9  mov     eax, [rcx+928h]
0x1401834af  sub     eax, 4
0x1401834b2  neg     eax
0x1401834b4  sbb     edx, edx
0x1401834b6  add     edx, 4
0x1401834b9  mov     r8d, 15h
0x1401834bf  call    ?SetState@VirtualMachine@@QEAAHW4_VM_STATE@@W4_VM_STATE_REASON_CODE@@@Z; VirtualMachine::SetState(_VM_STATE,_VM_STATE_REASON_CODE)
0x1401834c4  mov     rcx, [rsi+10h]
0x1401834c8  lea     rax, [rcx+480h]
0x1401834cf  mov     [rbp+var_28], rax
0x1401834d3  add     rcx, 10h; this
0x1401834d7  call    ?GetVmName@VirtualMachine@@UEBAPEBGXZ; VirtualMachine::GetVmName(void)
0x1401834dc  mov     [rbp+var_30], rax
0x1401834e0  lea     rax, [rbp+var_28]
0x1401834e4  mov     [rsp+68h+var_40], rax; __int64
0x1401834e9  lea     rax, [rbp+var_30]
0x1401834ed  mov     [rsp+68h+var_48], rax; __int64
0x1401834f2  mov     edx, 0Dh; unsigned int
0x1401834f7  lea     rcx, [rbp+EventDescriptor]; struct _EVENT_DESCRIPTOR *
0x1401834fb  call    ??$VmEventWriteAndReport@PEBGPEBG@@YAXPEBU_EVENT_DESCRIPTOR@@IAEBU_GUID@@PEBG$$QEAPEBG3@Z; VmEventWriteAndReport<ushort const *,ushort const *>(_EVENT_DESCRIPTOR const *,uint,_GUID const &,ushort const *,ushort const * &&,ushort const * &&)
0x140183500  call    cs:__imp_GetVmErrInfo
0x140183507  nop     dword ptr [rax+rax+00h]
0x14018350c  mov     rdx, rax
0x14018350f  lea     rcx, [rbp+var_38]
0x140183513  call    ??$Attach@UIVmSimpleTask@@@?$VmComPtr@UIVmSimpleTask@@@Vml@@QEAAXPEAUIVmSimpleTask@@@Z; Vml::VmComPtr<IVmSimpleTask>::Attach<IVmSimpleTask>(IVmSimpleTask *)
0x140183518  mov     r8, [rbp+var_38]; struct IUnknown *
0x14018351c  mov     edx, ebx; int
0x14018351e  mov     rcx, rsi; this
0x140183521  call    ?SetStatusComplete@WorkerAsyncTaskBase@@MEAAXJPEAUIUnknown@@@Z; WorkerAsyncTaskBase::SetStatusComplete(long,IUnknown *)
0x140183526  nop
0x140183527  lea     rcx, [rbp+var_38]; void *
0x14018352b  call    ??1?$VmComPtr@UIVmMetricValueSink@@@Vml@@QEAA@XZ; Vml::VmComPtr<IVmMetricValueSink>::~VmComPtr<IVmMetricValueSink>(void)
0x140183530  mov     rcx, [rbp+var_10]
0x140183534  xor     rcx, rsp; StackCookie
0x140183537  call    __security_check_cookie
0x14018353c  add     rsp, 68h
0x140183540  pop     r15
0x140183542  pop     r14
0x140183544  pop     rdi
0x140183545  pop     rsi
0x140183546  pop     rbx
0x140183547  pop     rbp
0x140183548  retn
```
