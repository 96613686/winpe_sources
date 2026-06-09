# AppV::Client::Service::NotificationManagerImpl::QueueEventCall<std::_Binder<std::_Unforced,long (IAppVClientEventSink::*)(_GUID,_GUID,uint),std::_Ph<1> const &,_GUID const &,_GUID const &,uint &>>(ClientEventType,std::_Binder<std::_Unforced,long (IAppVClientEventSink::*)(_GUID,_GUID,uint),std::_Ph<1> const &,_GUID const &,_GUID const &,uint &> const &)

- ea: `0x140015294`
- end: `0x1400154fa`
- name: `??$QueueEventCall@V?$_Binder@U_Unforced@std@@P8IAppVClientEventSink@@EAAJU_GUID@@0I@ZAEBU?$_Ph@$00@2@AEBU4@AEBU4@AEAI@std@@@NotificationManagerImpl@Service@Client@AppV@@AEAAXW4ClientEventType@@AEBV?$_Binder@U_Unforced@std@@P8IAppVClientEventSink@@EAAJU_GUID@@0I@ZAEBU?$_Ph@$00@2@AEBU4@AEBU4@AEAI@std@@@Z`
- size: `614`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x140017ab0`

## callees

- `0x140004280`
- `0x1400042a4`
- `0x140006304`
- `0x1400147fc`
- `0x140015294`
- `0x1400162e0`
- `0x14006a010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1400153c9`
- `KERNEL32!GetCurrentThreadId` at `0x1400153c9`
- `KERNEL32!LeaveCriticalSection` at `0x140015496`
- `KERNEL32!LeaveCriticalSection` at `0x140015496`
- `KERNEL32!EnterCriticalSection` at `0x1400153ba`
- `KERNEL32!EnterCriticalSection` at `0x1400153ba`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AppV::Client::Service::NotificationManagerImpl::QueueEventCall<std::_Binder<std::_Unforced,long (IAppVClientEventSink::*)(_GUID,_GUID,unsigned int),std::_Ph<1> const &,_GUID const &,_GUID const &,unsigned int &>>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  char *v5; // rdi
  void *v6; // rbx
  __int64 v7; // r8
  volatile signed __int32 *v8; // rdi
  __int64 result; // rax
  char *v11; // [rsp+30h] [rbp-79h] BYREF
  __int128 v12; // [rsp+38h] [rbp-71h] BYREF
  int v13; // [rsp+48h] [rbp-61h]
  __int128 v14; // [rsp+50h] [rbp-59h]
  void **v15; // [rsp+68h] [rbp-41h]
  char v16; // [rsp+70h] [rbp-39h]
  __int64 v17; // [rsp+78h] [rbp-31h]
  __int128 v18; // [rsp+80h] [rbp-29h] BYREF
  char **v19; // [rsp+90h] [rbp-19h]
  __int64 v20; // [rsp+98h] [rbp-11h]
  _BYTE v21[8]; // [rsp+A0h] [rbp-9h] BYREF
  volatile signed __int32 *v22; // [rsp+A8h] [rbp-1h]
  char **v23; // [rsp+B0h] [rbp+7h]
  __int64 v24; // [rsp+B8h] [rbp+Fh]

  if ( (Microsoft_AppV_SharedPerformanceEnableBits & 1) != 0 )
  {
    LODWORD(v11) = 2;
    v19 = &v11;
    v20 = 4;
    McGenEventWrite_EventWriteTransfer(
      PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context,
      Service_QueueClientEventBegin,
      a3,
      2,
      &v18);
  }
  v14 = 0;
  v5 = (char *)operator new(0x38u);
  v11 = v5;
  *(_QWORD *)v5 = `AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>::CreateEventCall<std::_Binder<std::_Unforced,long (IAppVClientEventSink::*)(_GUID,_GUID,unsigned int),std::_Ph<1> const &,_GUID const &,_GUID const &,unsigned int &>>'::`2'::EventCallImpl::`vftable';
  *((_QWORD *)v5 + 1) = *(_QWORD *)a3;
  *((_DWORD *)v5 + 4) = *(_DWORD *)(a3 + 8);
  *(_OWORD *)(v5 + 20) = *(_OWORD *)(a3 + 12);
  *(_OWORD *)(v5 + 36) = *(_OWORD *)(a3 + 28);
  v5[52] = *(_BYTE *)(a3 + 44);
  v11 = v5;
  v6 = operator new(0x18u);
  *(_OWORD *)v6 = 0;
  *((_DWORD *)v6 + 2) = 1;
  *((_DWORD *)v6 + 3) = 1;
  *(_QWORD *)v6 = ___7___Ref_count_VEventCallImpl__1____CreateEventCall_V___Binder_U_Unforced_std__P8IAppVClientEventSink__EAAJU_GUID__0I_ZAEBU___Ph__00_2_AEBU4_AEBU4_AEAI_std_____Subscriber_UIAppVClientEventSink__JUEnterpriseDeliveryParameters_Host_Client_AppV___Host_Client_AppV__SAXAEBV___Binder_U_Unforced_std__P8IAppVClientEventSink__EAAJU_GUID__0I_ZAEBU___Ph__00_2_AEBU4_AEBU4_AEAI_std__AEAV__shared_ptr_VEventCall___Subscriber_UIAppVClientEventSink__JUEnterpriseDeliveryParameters_Host_Client_AppV___Host_Client_AppV___7__Z__std__6B_;
  *((_QWORD *)v6 + 2) = v5;
  *(_QWORD *)&v14 = v5;
  *((_QWORD *)&v14 + 1) = v6;
  v18 = 0;
  v19 = 0;
  v20 = 7;
  LOWORD(v18) = 0;
  v11 = 0;
  v15 = &softricity::shared::lock_holder<softricity::shared::critical_section>::`vftable';
  v17 = a1 + 16;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  if ( ++*(_DWORD *)(a1 + 56) == 1 )
    *(_DWORD *)(a1 + 60) = GetCurrentThreadId();
  v16 = 1;
  v12 = 0;
  _InterlockedIncrement((volatile signed __int32 *)v6 + 2);
  *(_QWORD *)&v12 = v5;
  *((_QWORD *)&v12 + 1) = v6;
  v13 = 2;
  std::for_each<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<IAppVClientEventSink * const,std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>>>>>>,AppV::Client::Service::NotificationManagerImpl::QueueEventByFilter>(
    (__int64)v21,
    **(__int64 ***)(a1 + 72),
    *(__int64 **)(a1 + 72),
    (__int64)&v12);
  v8 = v22;
  if ( v22 )
  {
    if ( _InterlockedExchangeAdd(v22 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v8)(v8);
      if ( _InterlockedExchangeAdd(v8 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
    }
  }
  if ( (Microsoft_AppV_SharedPerformanceEnableBits & 1) != 0 )
  {
    LODWORD(v11) = 2;
    v23 = &v11;
    v24 = 4;
    McGenEventWrite_EventWriteTransfer(
      PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context,
      Service_QueueClientEventEnd,
      v7,
      2,
      v21);
  }
  if ( (*(_DWORD *)(a1 + 56))-- == 1 )
    *(_DWORD *)(a1 + 60) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  std::wstring::~wstring(&v18);
  result = (unsigned int)_InterlockedDecrement((volatile signed __int32 *)v6 + 2);
  if ( !(_DWORD)result )
  {
    (**(void (__fastcall ***)(void *))v6)(v6);
    result = (unsigned int)_InterlockedDecrement((volatile signed __int32 *)v6 + 3);
    if ( !(_DWORD)result )
      return (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v6 + 8LL))(v6);
  }
  return result;
}

```

## disassembly

```asm
0x140015294  push    rbp
0x140015296  push    rbx
0x140015297  push    rsi
0x140015298  push    rdi
0x140015299  push    r14
0x14001529b  push    r15
0x14001529d  lea     rbp, [rsp-2Fh]
0x1400152a2  sub     rsp, 0D8h
0x1400152a9  mov     rax, cs:__security_cookie
0x1400152b0  xor     rax, rsp
0x1400152b3  mov     [rbp+57h+var_40], rax
0x1400152b7  mov     rbx, r8
0x1400152ba  mov     r14, rcx
0x1400152bd  mov     r15d, 2
0x1400152c3  test    byte ptr cs:Microsoft_AppV_SharedPerformanceEnableBits, 1
0x1400152ca  jz      short loc_1400152FF
0x1400152cc  mov     dword ptr [rbp+57h+var_D0], r15d
0x1400152d0  lea     rax, [rbp+57h+var_D0]
0x1400152d4  mov     [rbp+57h+var_70], rax
0x1400152d8  mov     [rbp+57h+var_68], 4
0x1400152e0  lea     rax, [rbp+57h+var_80]
0x1400152e4  mov     [rsp+100h+var_E0], rax
0x1400152e9  mov     r9d, r15d
0x1400152ec  lea     rdx, Service_QueueClientEventBegin
0x1400152f3  lea     rcx, PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context
0x1400152fa  call    McGenEventWrite_EventWriteTransfer
0x1400152ff  xorps   xmm0, xmm0
0x140015302  movdqu  [rbp+57h+var_B0], xmm0
0x140015307  mov     ecx, 38h ; '8'; Size
0x14001530c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140015311  mov     rdi, rax
0x140015314  mov     [rbp+57h+var_D0], rax
0x140015318  lea     rax, ??_7EventCallImpl@?1???$CreateEventCall@V?$_Binder@U_Unforced@std@@P8IAppVClientEventSink@@EAAJU_GUID@@0I@ZAEBU?$_Ph@$00@2@AEBU4@AEBU4@AEAI@std@@@?$Subscriber@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@@Host@Client@AppV@@SAXAEBV?$_Binder@U_Unforced@std@@P8IAppVClientEventSink@@EAAJU_GUID@@0I@ZAEBU?$_Ph@$00@2@AEBU4@AEBU4@AEAI@std@@AEAV?$shared_ptr@VEventCall@?$Subscriber@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@@Host@Client@AppV@@@6@@Z@6B@; const `AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>::CreateEventCall<std::_Binder<std::_Unforced,long (IAppVClientEventSink::*)(_GUID,_GUID,uint),std::_Ph<1> const &,_GUID const &,_GUID const &,uint &>>(std::_Binder<std::_Unforced,long (IAppVClientEventSink::*)(_GUID,_GUID,uint),std::_Ph<1> const &,_GUID const &,_GUID const &,uint &> const &,std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>::EventCall> &)'::`2'::EventCallImpl::`vftable'
0x14001531f  mov     [rdi], rax
0x140015322  mov     rcx, [rbx]
0x140015325  mov     [rdi+8], rcx
0x140015329  mov     ecx, [rbx+8]
0x14001532c  mov     [rdi+10h], ecx
0x14001532f  movups  xmm0, xmmword ptr [rbx+0Ch]
0x140015333  movdqu  xmmword ptr [rdi+14h], xmm0
0x140015338  movups  xmm1, xmmword ptr [rbx+1Ch]
0x14001533c  movdqu  xmmword ptr [rdi+24h], xmm1
0x140015341  mov     al, [rbx+2Ch]
0x140015344  mov     [rdi+34h], al
0x140015347  mov     [rbp+57h+var_D0], rdi
0x14001534b  mov     ecx, 18h; Size
0x140015350  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140015355  mov     rbx, rax
0x140015358  mov     [rbp+57h+var_D0], rax
0x14001535c  xorps   xmm0, xmm0
0x14001535f  movups  xmmword ptr [rax], xmm0
0x140015362  mov     dword ptr [rax+8], 1
0x140015369  mov     dword ptr [rax+0Ch], 1
0x140015370  lea     rax, ??_7?$_Ref_count@VEventCallImpl@?1???$CreateEventCall@V?$_Binder@U_Unforced@std@@P8IAppVClientEventSink@@EAAJU_GUID@@0I@ZAEBU?$_Ph@$00@2@AEBU4@AEBU4@AEAI@std@@@?$Subscriber@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@@Host@Client@AppV@@SAXAEBV?$_Binder@U_Unforced@std@@P8IAppVClientEventSink@@EAAJU_GUID@@0I@ZAEBU?$_Ph@$00@2@AEBU4@AEBU4@AEAI@std@@AEAV?$shared_ptr@VEventCall@?$Subscriber@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@@Host@Client@AppV@@@7@@Z@@std@@6B@; const std::_Ref_count<`AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>::CreateEventCall<std::_Binder<std::_Unforced,long (IAppVClientEventSink::*)(_GUID,_GUID,uint),std::_Ph<1> const &,_GUID const &,_GUID const &,uint &>>(std::_Binder<std::_Unforced,long (IAppVClientEventSink::*)(_GUID,_GUID,uint),std::_Ph<1> const &,_GUID const &,_GUID const &,uint &> const &,std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>::EventCall> &)'::`2'::EventCallImpl>::`vftable'
0x140015377  mov     [rbx], rax
0x14001537a  mov     [rbx+10h], rdi
0x14001537e  mov     qword ptr [rbp+57h+var_B0], rdi
0x140015382  mov     qword ptr [rbp+57h+var_B0+8], rbx
0x140015386  movups  [rbp+57h+var_80], xmm0
0x14001538a  mov     [rbp+57h+var_70], 0
0x140015392  mov     [rbp+57h+var_68], 7
0x14001539a  xor     eax, eax
0x14001539c  mov     word ptr [rbp+57h+var_80], ax
0x1400153a0  mov     [rbp+57h+var_D0], rax
0x1400153a4  lea     rax, ??_7?$lock_holder@Vcritical_section@shared@softricity@@@shared@softricity@@6B@; const softricity::shared::lock_holder<softricity::shared::critical_section>::`vftable'
0x1400153ab  mov     [rbp+57h+var_98], rax
0x1400153af  lea     rsi, [r14+10h]
0x1400153b3  mov     [rbp+57h+var_88], rsi
0x1400153b7  mov     rcx, rsi; lpCriticalSection
0x1400153ba  call    cs:__imp_EnterCriticalSection
0x1400153c0  inc     dword ptr [rsi+28h]
0x1400153c3  cmp     dword ptr [rsi+28h], 1
0x1400153c7  jnz     short loc_1400153D2
0x1400153c9  call    cs:__imp_GetCurrentThreadId
0x1400153cf  mov     [rsi+2Ch], eax
0x1400153d2  mov     [rbp+57h+var_90], 1
0x1400153d6  xorps   xmm0, xmm0
0x1400153d9  movdqu  [rbp+57h+var_C8], xmm0
0x1400153de  lock inc dword ptr [rbx+8]
0x1400153e2  mov     qword ptr [rbp+57h+var_C8], rdi
0x1400153e6  mov     qword ptr [rbp+57h+var_C8+8], rbx
0x1400153ea  mov     [rbp+57h+var_B8], r15d
0x1400153ee  mov     rdx, [r14+48h]
0x1400153f2  lea     r9, [rbp+57h+var_C8]
0x1400153f6  mov     r8, rdx
0x1400153f9  mov     rdx, [rdx]
0x1400153fc  lea     rcx, [rbp+57h+var_60]
0x140015400  call    ??$for_each@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAUIAppVClientEventSink@@V?$shared_ptr@V?$Subscriber@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@@Host@Client@AppV@@@std@@@std@@@std@@@std@@@std@@VQueueEventByFilter@NotificationManagerImpl@Service@Client@AppV@@@std@@YA?AVQueueEventByFilter@NotificationManagerImpl@Service@Client@AppV@@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAUIAppVClientEventSink@@V?$shared_ptr@V?$Subscriber@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@@Host@Client@AppV@@@std@@@std@@@std@@@std@@@0@0V12345@@Z; std::for_each<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<IAppVClientEventSink * const,std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>>>>>>,AppV::Client::Service::NotificationManagerImpl::QueueEventByFilter>(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<IAppVClientEventSink * const,std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>>>>>>,std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<IAppVClientEventSink * const,std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>>>>>>,AppV::Client::Service::NotificationManagerImpl::QueueEventByFilter)
0x140015405  mov     rdi, [rbp+57h+var_58]
0x140015409  or      r14d, 0FFFFFFFFh
0x14001540d  test    rdi, rdi
0x140015410  jz      short loc_140015449
0x140015412  mov     eax, r14d
0x140015415  lock xadd [rdi+8], eax
0x14001541a  add     eax, r14d
0x14001541d  jnz     short loc_140015449
0x14001541f  mov     rax, [rdi]
0x140015422  mov     rcx, rdi
0x140015425  mov     rax, [rax]
0x140015428  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001542d  mov     eax, r14d
0x140015430  lock xadd [rdi+0Ch], eax
0x140015435  add     eax, r14d
0x140015438  jnz     short loc_140015449
0x14001543a  mov     rax, [rdi]
0x14001543d  mov     rcx, rdi
0x140015440  mov     rax, [rax+8]
0x140015444  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015449  test    byte ptr cs:Microsoft_AppV_SharedPerformanceEnableBits, 1
0x140015450  jz      short loc_140015486
0x140015452  mov     dword ptr [rbp+57h+var_D0], r15d
0x140015456  lea     rax, [rbp+57h+var_D0]
0x14001545a  mov     [rbp+57h+var_50], rax
0x14001545e  mov     [rbp+57h+var_48], 4
0x140015466  lea     rax, [rbp+57h+var_60]
0x14001546a  mov     [rsp+100h+var_E0], rax
0x14001546f  mov     r9d, r15d
0x140015472  lea     rdx, Service_QueueClientEventEnd
0x140015479  lea     rcx, PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context
0x140015480  call    McGenEventWrite_EventWriteTransfer
0x140015485  nop
0x140015486  add     [rsi+28h], r14d
0x14001548a  jnz     short loc_140015493
0x14001548c  mov     dword ptr [rsi+2Ch], 0
0x140015493  mov     rcx, rsi; lpCriticalSection
0x140015496  call    cs:__imp_LeaveCriticalSection
0x14001549c  nop
0x14001549d  lea     rcx, [rbp+57h+var_80]
0x1400154a1  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400154a6  nop
0x1400154a7  mov     eax, r14d
0x1400154aa  lock xadd [rbx+8], eax
0x1400154af  add     eax, r14d
0x1400154b2  jnz     short loc_1400154DE
0x1400154b4  mov     rax, [rbx]
0x1400154b7  mov     rcx, rbx
0x1400154ba  mov     rax, [rax]
0x1400154bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400154c2  mov     eax, r14d
0x1400154c5  lock xadd [rbx+0Ch], eax
0x1400154ca  add     eax, r14d
0x1400154cd  jnz     short loc_1400154DE
0x1400154cf  mov     rax, [rbx]
0x1400154d2  mov     rcx, rbx
0x1400154d5  mov     rax, [rax+8]
0x1400154d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400154de  mov     rcx, [rbp+57h+var_40]
0x1400154e2  xor     rcx, rsp; StackCookie
0x1400154e5  call    __security_check_cookie
0x1400154ea  add     rsp, 0D8h
0x1400154f1  pop     r15
0x1400154f3  pop     r14
0x1400154f5  pop     rdi
0x1400154f6  pop     rsi
0x1400154f7  pop     rbx
0x1400154f8  pop     rbp
0x1400154f9  retn
```
