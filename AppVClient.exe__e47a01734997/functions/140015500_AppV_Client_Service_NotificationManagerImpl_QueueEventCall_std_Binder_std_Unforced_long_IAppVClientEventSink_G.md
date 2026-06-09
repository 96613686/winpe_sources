# AppV::Client::Service::NotificationManagerImpl::QueueEventCall<std::_Binder<std::_Unforced,long (IAppVClientEventSink::*)(_GUID,_GUID,ulong),std::_Ph<1> const &,_GUID const &,_GUID const &,ulong &>>(ClientEventType,std::_Binder<std::_Unforced,long (IAppVClientEventSink::*)(_GUID,_GUID,ulong),std::_Ph<1> const &,_GUID const &,_GUID const &,ulong &> const &)

- ea: `0x140015500`
- end: `0x140015847`
- name: `??$QueueEventCall@V?$_Binder@U_Unforced@std@@P8IAppVClientEventSink@@EAAJU_GUID@@0K@ZAEBU?$_Ph@$00@2@AEBU4@AEBU4@AEAK@std@@@NotificationManagerImpl@Service@Client@AppV@@AEAAXW4ClientEventType@@AEBV?$_Binder@U_Unforced@std@@P8IAppVClientEventSink@@EAAJU_GUID@@0K@ZAEBU?$_Ph@$00@2@AEBU4@AEBU4@AEAK@std@@@Z`
- size: `839`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `2`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400179c0`
- `0x1400186e0`

## callees

- `0x140004280`
- `0x1400042a4`
- `0x140006304`
- `0x1400147fc`
- `0x140015500`
- `0x1400162e0`
- `0x1400163f4`
- `0x1400165b4`
- `0x1400173c4`
- `0x14006a010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14001564a`
- `KERNEL32!CloseHandle` at `0x140015670`
- `KERNEL32!CloseHandle` at `0x1400157e3`
- `KERNEL32!CloseHandle` at `0x14001564a`
- `KERNEL32!CloseHandle` at `0x140015670`
- `KERNEL32!CloseHandle` at `0x1400157e3`
- `KERNEL32!GetCurrentThreadId` at `0x1400156a5`
- `KERNEL32!GetCurrentThreadId` at `0x1400156a5`
- `KERNEL32!LeaveCriticalSection` at `0x1400157d4`
- `KERNEL32!LeaveCriticalSection` at `0x1400157d4`
- `KERNEL32!EnterCriticalSection` at `0x140015695`
- `KERNEL32!EnterCriticalSection` at `0x140015695`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall AppV::Client::Service::NotificationManagerImpl::QueueEventCall<std::_Binder<std::_Unforced,long (IAppVClientEventSink::*)(_GUID,_GUID,unsigned long),std::_Ph<1> const &,_GUID const &,_GUID const &,unsigned long &>>(
        __int64 a1,
        int a2,
        __int64 a3)
{
  _QWORD *v6; // r15
  void *v7; // rdi
  HANDLE v8; // rbx
  __int64 v9; // r8
  volatile signed __int32 *v10; // r15
  __int64 result; // rax
  __int128 *v13; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE hObject; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v15; // [rsp+40h] [rbp-C0h] BYREF
  int v16; // [rsp+50h] [rbp-B0h]
  __int128 v17; // [rsp+58h] [rbp-A8h]
  void **v18; // [rsp+68h] [rbp-98h]
  char v19; // [rsp+70h] [rbp-90h]
  __int64 v20; // [rsp+78h] [rbp-88h]
  _BYTE v21[8]; // [rsp+80h] [rbp-80h] BYREF
  volatile signed __int32 *v22; // [rsp+88h] [rbp-78h]
  _BYTE v23[40]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v24; // [rsp+B8h] [rbp-48h] BYREF
  __int128 **v25; // [rsp+C8h] [rbp-38h]
  __int64 v26; // [rsp+D0h] [rbp-30h]
  __int128 v27; // [rsp+D8h] [rbp-28h] BYREF
  _QWORD v28[4]; // [rsp+E8h] [rbp-18h] BYREF
  int v29; // [rsp+108h] [rbp+8h]

  if ( (Microsoft_AppV_SharedPerformanceEnableBits & 1) != 0 )
  {
    LODWORD(v13) = a2;
    v25 = &v13;
    v26 = 4;
    McGenEventWrite_EventWriteTransfer(
      PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context,
      Service_QueueClientEventBegin,
      a3,
      2,
      &v24);
  }
  v17 = 0;
  v6 = operator new(0x38u);
  hObject = v6;
  *v6 = `AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>::CreateEventCall<std::_Binder<std::_Unforced,long (IAppVClientEventSink::*)(_GUID,_GUID,unsigned long),std::_Ph<1> const &,_GUID const &,_GUID const &,unsigned long &>>'::`2'::EventCallImpl::`vftable';
  v6[1] = *(_QWORD *)a3;
  *((_DWORD *)v6 + 4) = *(_DWORD *)(a3 + 8);
  *(_OWORD *)((char *)v6 + 20) = *(_OWORD *)(a3 + 12);
  *(_OWORD *)((char *)v6 + 36) = *(_OWORD *)(a3 + 28);
  *((_BYTE *)v6 + 52) = *(_BYTE *)(a3 + 44);
  hObject = v6;
  v7 = operator new(0x18u);
  *(_OWORD *)v7 = 0;
  *((_DWORD *)v7 + 2) = 1;
  *((_DWORD *)v7 + 3) = 1;
  *(_QWORD *)v7 = ___7___Ref_count_VEventCallImpl__1____CreateEventCall_V___Binder_U_Unforced_std__P8IAppVClientEventSink__EAAJU_GUID__0K_ZAEBU___Ph__00_2_AEBU4_AEBU4_AEAK_std_____Subscriber_UIAppVClientEventSink__JUEnterpriseDeliveryParameters_Host_Client_AppV___Host_Client_AppV__SAXAEBV___Binder_U_Unforced_std__P8IAppVClientEventSink__EAAJU_GUID__0K_ZAEBU___Ph__00_2_AEBU4_AEBU4_AEAK_std__AEAV__shared_ptr_VEventCall___Subscriber_UIAppVClientEventSink__JUEnterpriseDeliveryParameters_Host_Client_AppV___Host_Client_AppV___7__Z__std__6B_;
  *((_QWORD *)v7 + 2) = v6;
  *(_QWORD *)&v17 = v6;
  *((_QWORD *)&v17 + 1) = v7;
  v24 = 0;
  v25 = 0;
  v26 = 7;
  LOWORD(v24) = 0;
  v8 = 0;
  hObject = 0;
  LODWORD(v13) = a2 & 0xFFFF0000;
  if ( (a2 & 0xFFFF0000) != 0 )
  {
    if ( (AppV::Client::Service::NotificationManagerImpl::GetSessionIdentity(&v24, &hObject) & 0x8000000000LL) == 0 )
    {
      if ( hObject )
        CloseHandle(hObject);
      goto LABEL_25;
    }
    v8 = hObject;
    if ( hObject )
    {
      CloseHandle(hObject);
      v8 = 0;
      hObject = 0;
    }
  }
  v18 = &softricity::shared::lock_holder<softricity::shared::critical_section>::`vftable';
  v20 = a1 + 16;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  if ( ++*(_DWORD *)(a1 + 56) == 1 )
    *(_DWORD *)(a1 + 60) = GetCurrentThreadId();
  v19 = 1;
  if ( (_DWORD)v13 )
  {
    v13 = &v27;
    v27 = 0;
    _InterlockedIncrement((volatile signed __int32 *)v7 + 2);
    *(_QWORD *)&v27 = v6;
    *((_QWORD *)&v27 + 1) = v7;
    std::wstring::wstring(v28, &v24);
    v29 = a2;
    std::for_each<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<IAppVClientEventSink * const,std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>>>>>>,AppV::Client::Service::NotificationManagerImpl::QueueEventBySessionAndFilter>(
      (__int64)v21,
      **(__int64 ***)(a1 + 72),
      *(__int64 **)(a1 + 72),
      (__int64)&v27);
    std::wstring::~wstring(v23);
    v10 = v22;
  }
  else
  {
    v15 = 0;
    _InterlockedIncrement((volatile signed __int32 *)v7 + 2);
    *(_QWORD *)&v15 = v6;
    *((_QWORD *)&v15 + 1) = v7;
    v16 = a2;
    std::for_each<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<IAppVClientEventSink * const,std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>>>>>>,AppV::Client::Service::NotificationManagerImpl::QueueEventByFilter>(
      (__int64)&v27,
      **(__int64 ***)(a1 + 72),
      *(__int64 **)(a1 + 72),
      (__int64)&v15);
    v10 = (volatile signed __int32 *)*((_QWORD *)&v27 + 1);
  }
  if ( v10 )
  {
    if ( _InterlockedExchangeAdd(v10 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
      if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
    }
  }
  if ( (Microsoft_AppV_SharedPerformanceEnableBits & 1) != 0 )
  {
    LODWORD(v13) = a2;
    v28[0] = &v13;
    v28[1] = 4;
    McGenEventWrite_EventWriteTransfer(
      PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context,
      Service_QueueClientEventEnd,
      v9,
      2,
      &v27);
  }
  if ( (*(_DWORD *)(a1 + 56))-- == 1 )
    *(_DWORD *)(a1 + 60) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  if ( v8 )
    CloseHandle(v8);
LABEL_25:
  std::wstring::~wstring(&v24);
  result = (unsigned int)_InterlockedDecrement((volatile signed __int32 *)v7 + 2);
  if ( !(_DWORD)result )
  {
    (**(void (__fastcall ***)(void *))v7)(v7);
    result = (unsigned int)_InterlockedDecrement((volatile signed __int32 *)v7 + 3);
    if ( !(_DWORD)result )
      return (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v7 + 8LL))(v7);
  }
  return result;
}

```

## disassembly

```asm
0x140015500  push    rbp
0x140015502  push    rbx
0x140015503  push    rsi
0x140015504  push    rdi
0x140015505  push    r12
0x140015507  push    r13
0x140015509  push    r14
0x14001550b  push    r15
0x14001550d  lea     rbp, [rsp-28h]
0x140015512  sub     rsp, 128h
0x140015519  mov     rax, cs:__security_cookie
0x140015520  xor     rax, rsp
0x140015523  mov     [rbp+60h+var_50], rax
0x140015527  mov     rbx, r8
0x14001552a  mov     r12d, edx
0x14001552d  mov     r13, rcx
0x140015530  mov     esi, 1
0x140015535  test    byte ptr cs:Microsoft_AppV_SharedPerformanceEnableBits, sil
0x14001553c  jz      short loc_140015573
0x14001553e  mov     dword ptr [rsp+160h+var_130], edx
0x140015542  lea     rax, [rsp+160h+var_130]
0x140015547  mov     [rbp+60h+var_98], rax
0x14001554b  mov     [rbp+60h+var_90], 4
0x140015553  lea     rax, [rbp+60h+var_A8]
0x140015557  mov     [rsp+160h+var_140], rax
0x14001555c  lea     r9d, [rsi+1]
0x140015560  lea     rdx, Service_QueueClientEventBegin
0x140015567  lea     rcx, PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context
0x14001556e  call    McGenEventWrite_EventWriteTransfer
0x140015573  xorps   xmm0, xmm0
0x140015576  movdqu  [rsp+160h+var_108], xmm0
0x14001557c  mov     ecx, 38h ; '8'; Size
0x140015581  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140015586  mov     r15, rax
0x140015589  mov     [rsp+160h+hObject], rax
0x14001558e  lea     rax, ??_7EventCallImpl@?1???$CreateEventCall@V?$_Binder@U_Unforced@std@@P8IAppVClientEventSink@@EAAJU_GUID@@0K@ZAEBU?$_Ph@$00@2@AEBU4@AEBU4@AEAK@std@@@?$Subscriber@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@@Host@Client@AppV@@SAXAEBV?$_Binder@U_Unforced@std@@P8IAppVClientEventSink@@EAAJU_GUID@@0K@ZAEBU?$_Ph@$00@2@AEBU4@AEBU4@AEAK@std@@AEAV?$shared_ptr@VEventCall@?$Subscriber@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@@Host@Client@AppV@@@6@@Z@6B@; const `AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>::CreateEventCall<std::_Binder<std::_Unforced,long (IAppVClientEventSink::*)(_GUID,_GUID,ulong),std::_Ph<1> const &,_GUID const &,_GUID const &,ulong &>>(std::_Binder<std::_Unforced,long (IAppVClientEventSink::*)(_GUID,_GUID,ulong),std::_Ph<1> const &,_GUID const &,_GUID const &,ulong &> const &,std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>::EventCall> &)'::`2'::EventCallImpl::`vftable'
0x140015595  mov     [r15], rax
0x140015598  mov     rcx, [rbx]
0x14001559b  mov     [r15+8], rcx
0x14001559f  mov     ecx, [rbx+8]
0x1400155a2  mov     [r15+10h], ecx
0x1400155a6  movups  xmm0, xmmword ptr [rbx+0Ch]
0x1400155aa  movdqu  xmmword ptr [r15+14h], xmm0
0x1400155b0  movups  xmm1, xmmword ptr [rbx+1Ch]
0x1400155b4  movdqu  xmmword ptr [r15+24h], xmm1
0x1400155ba  mov     al, [rbx+2Ch]
0x1400155bd  mov     [r15+34h], al
0x1400155c1  mov     [rsp+160h+hObject], r15
0x1400155c6  mov     ecx, 18h; Size
0x1400155cb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400155d0  mov     rdi, rax
0x1400155d3  mov     [rsp+160h+hObject], rax
0x1400155d8  xorps   xmm0, xmm0
0x1400155db  movups  xmmword ptr [rax], xmm0
0x1400155de  mov     [rax+8], esi
0x1400155e1  mov     [rax+0Ch], esi
0x1400155e4  lea     rax, ??_7?$_Ref_count@VEventCallImpl@?1???$CreateEventCall@V?$_Binder@U_Unforced@std@@P8IAppVClientEventSink@@EAAJU_GUID@@0K@ZAEBU?$_Ph@$00@2@AEBU4@AEBU4@AEAK@std@@@?$Subscriber@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@@Host@Client@AppV@@SAXAEBV?$_Binder@U_Unforced@std@@P8IAppVClientEventSink@@EAAJU_GUID@@0K@ZAEBU?$_Ph@$00@2@AEBU4@AEBU4@AEAK@std@@AEAV?$shared_ptr@VEventCall@?$Subscriber@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@@Host@Client@AppV@@@7@@Z@@std@@6B@; const std::_Ref_count<`AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>::CreateEventCall<std::_Binder<std::_Unforced,long (IAppVClientEventSink::*)(_GUID,_GUID,ulong),std::_Ph<1> const &,_GUID const &,_GUID const &,ulong &>>(std::_Binder<std::_Unforced,long (IAppVClientEventSink::*)(_GUID,_GUID,ulong),std::_Ph<1> const &,_GUID const &,_GUID const &,ulong &> const &,std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>::EventCall> &)'::`2'::EventCallImpl>::`vftable'
0x1400155eb  mov     [rdi], rax
0x1400155ee  mov     [rdi+10h], r15
0x1400155f2  mov     qword ptr [rsp+160h+var_108], r15
0x1400155f7  mov     qword ptr [rsp+160h+var_108+8], rdi
0x1400155fc  movups  [rbp+60h+var_A8], xmm0
0x140015600  mov     [rbp+60h+var_98], 0
0x140015608  mov     [rbp+60h+var_90], 7
0x140015610  xor     eax, eax
0x140015612  mov     word ptr [rbp+60h+var_A8], ax
0x140015616  xor     ebx, ebx
0x140015618  mov     [rsp+160h+hObject], rbx
0x14001561d  mov     eax, r12d
0x140015620  and     eax, 0FFFF0000h
0x140015625  mov     dword ptr [rsp+160h+var_130], eax
0x140015629  jz      short loc_14001567D
0x14001562b  lea     rdx, [rsp+160h+hObject]
0x140015630  lea     rcx, [rbp+60h+var_A8]
0x140015634  call    ?GetSessionIdentity@NotificationManagerImpl@Service@Client@AppV@@CA_KAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVCHandle@ATL@@@Z; AppV::Client::Service::NotificationManagerImpl::GetSessionIdentity(std::wstring &,ATL::CHandle &)
0x140015639  bt      rax, 27h ; '''
0x14001563e  jb      short loc_140015663
0x140015640  mov     rcx, [rsp+160h+hObject]; hObject
0x140015645  test    rcx, rcx
0x140015648  jz      short loc_140015651
0x14001564a  call    cs:__imp_CloseHandle
0x140015650  nop
0x140015651  lea     rcx, [rbp+60h+var_A8]
0x140015655  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001565a  nop
0x14001565b  or      esi, 0FFFFFFFFh
0x14001565e  jmp     loc_1400157F4
0x140015663  mov     rbx, [rsp+160h+hObject]
0x140015668  test    rbx, rbx
0x14001566b  jz      short loc_14001567D
0x14001566d  mov     rcx, rbx; hObject
0x140015670  call    cs:__imp_CloseHandle
0x140015676  xor     ebx, ebx
0x140015678  mov     [rsp+160h+hObject], rbx
0x14001567d  lea     rax, ??_7?$lock_holder@Vcritical_section@shared@softricity@@@shared@softricity@@6B@; const softricity::shared::lock_holder<softricity::shared::critical_section>::`vftable'
0x140015684  mov     [rsp+160h+var_F8], rax
0x140015689  lea     r14, [r13+10h]
0x14001568d  mov     [rsp+160h+var_E8], r14
0x140015692  mov     rcx, r14; lpCriticalSection
0x140015695  call    cs:__imp_EnterCriticalSection
0x14001569b  add     [r14+28h], esi
0x14001569f  cmp     [r14+28h], esi
0x1400156a3  jnz     short loc_1400156AF
0x1400156a5  call    cs:__imp_GetCurrentThreadId
0x1400156ab  mov     [r14+2Ch], eax
0x1400156af  mov     [rsp+160h+var_F0], sil
0x1400156b4  or      esi, 0FFFFFFFFh
0x1400156b7  xorps   xmm0, xmm0
0x1400156ba  cmp     dword ptr [rsp+160h+var_130], 0
0x1400156bf  jnz     short loc_1400156F8
0x1400156c1  movdqu  [rsp+160h+var_120], xmm0
0x1400156c7  lock inc dword ptr [rdi+8]
0x1400156cb  mov     qword ptr [rsp+160h+var_120], r15
0x1400156d0  mov     qword ptr [rsp+160h+var_120+8], rdi
0x1400156d5  mov     [rsp+160h+var_110], r12d
0x1400156da  mov     rdx, [r13+48h]
0x1400156de  lea     r9, [rsp+160h+var_120]
0x1400156e3  mov     r8, rdx
0x1400156e6  mov     rdx, [rdx]
0x1400156e9  lea     rcx, [rbp+60h+var_88]
0x1400156ed  call    ??$for_each@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAUIAppVClientEventSink@@V?$shared_ptr@V?$Subscriber@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@@Host@Client@AppV@@@std@@@std@@@std@@@std@@@std@@VQueueEventByFilter@NotificationManagerImpl@Service@Client@AppV@@@std@@YA?AVQueueEventByFilter@NotificationManagerImpl@Service@Client@AppV@@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAUIAppVClientEventSink@@V?$shared_ptr@V?$Subscriber@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@@Host@Client@AppV@@@std@@@std@@@std@@@std@@@0@0V12345@@Z; std::for_each<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<IAppVClientEventSink * const,std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>>>>>>,AppV::Client::Service::NotificationManagerImpl::QueueEventByFilter>(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<IAppVClientEventSink * const,std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>>>>>>,std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<IAppVClientEventSink * const,std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>>>>>>,AppV::Client::Service::NotificationManagerImpl::QueueEventByFilter)
0x1400156f2  mov     r15, qword ptr [rbp+60h+var_88+8]
0x1400156f6  jmp     short loc_140015747
0x1400156f8  lea     rax, [rbp+60h+var_88]
0x1400156fc  mov     [rsp+160h+var_130], rax
0x140015701  movdqu  [rbp+60h+var_88], xmm0
0x140015706  lock inc dword ptr [rdi+8]
0x14001570a  mov     qword ptr [rbp+60h+var_88], r15
0x14001570e  mov     qword ptr [rbp+60h+var_88+8], rdi
0x140015712  lea     rdx, [rbp+60h+var_A8]
0x140015716  lea     rcx, [rbp+60h+var_78]
0x14001571a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14001571f  mov     [rbp+60h+var_58], r12d
0x140015723  mov     rdx, [r13+48h]
0x140015727  lea     r9, [rbp+60h+var_88]
0x14001572b  mov     r8, rdx
0x14001572e  mov     rdx, [rdx]
0x140015731  lea     rcx, [rbp+60h+var_E0]
0x140015735  call    ??$for_each@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAUIAppVClientEventSink@@V?$shared_ptr@V?$Subscriber@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@@Host@Client@AppV@@@std@@@std@@@std@@@std@@@std@@VQueueEventBySessionAndFilter@NotificationManagerImpl@Service@Client@AppV@@@std@@YA?AVQueueEventBySessionAndFilter@NotificationManagerImpl@Service@Client@AppV@@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAUIAppVClientEventSink@@V?$shared_ptr@V?$Subscriber@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@@Host@Client@AppV@@@std@@@std@@@std@@@std@@@0@0V12345@@Z; std::for_each<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<IAppVClientEventSink * const,std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>>>>>>,AppV::Client::Service::NotificationManagerImpl::QueueEventBySessionAndFilter>(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<IAppVClientEventSink * const,std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>>>>>>,std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<IAppVClientEventSink * const,std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>>>>>>,AppV::Client::Service::NotificationManagerImpl::QueueEventBySessionAndFilter)
0x14001573a  lea     rcx, [rbp+60h+var_D0]
0x14001573e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140015743  mov     r15, [rbp+60h+var_D8]
0x140015747  test    r15, r15
0x14001574a  jz      short loc_140015781
0x14001574c  mov     eax, esi
0x14001574e  lock xadd [r15+8], eax
0x140015754  add     eax, esi
0x140015756  jnz     short loc_140015781
0x140015758  mov     rax, [r15]
0x14001575b  mov     rcx, r15
0x14001575e  mov     rax, [rax]
0x140015761  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015766  mov     eax, esi
0x140015768  lock xadd [r15+0Ch], eax
0x14001576e  add     eax, esi
0x140015770  jnz     short loc_140015781
0x140015772  mov     rax, [r15]
0x140015775  mov     rcx, r15
0x140015778  mov     rax, [rax+8]
0x14001577c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015781  test    byte ptr cs:Microsoft_AppV_SharedPerformanceEnableBits, 1
0x140015788  jz      short loc_1400157C3
0x14001578a  mov     dword ptr [rsp+160h+var_130], r12d
0x14001578f  lea     rax, [rsp+160h+var_130]
0x140015794  mov     [rbp+60h+var_78], rax
0x140015798  mov     [rbp+60h+var_70], 4
0x1400157a0  lea     rax, [rbp+60h+var_88]
0x1400157a4  mov     [rsp+160h+var_140], rax
0x1400157a9  mov     r9d, 2
0x1400157af  lea     rdx, Service_QueueClientEventEnd
0x1400157b6  lea     rcx, PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context
0x1400157bd  call    McGenEventWrite_EventWriteTransfer
0x1400157c2  nop
0x1400157c3  add     [r14+28h], esi
0x1400157c7  jnz     short loc_1400157D1
0x1400157c9  mov     dword ptr [r14+2Ch], 0
0x1400157d1  mov     rcx, r14; lpCriticalSection
0x1400157d4  call    cs:__imp_LeaveCriticalSection
0x1400157da  nop
0x1400157db  test    rbx, rbx
0x1400157de  jz      short loc_1400157EA
0x1400157e0  mov     rcx, rbx; hObject
0x1400157e3  call    cs:__imp_CloseHandle
0x1400157e9  nop
0x1400157ea  lea     rcx, [rbp+60h+var_A8]
0x1400157ee  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400157f3  nop
0x1400157f4  mov     eax, esi
0x1400157f6  lock xadd [rdi+8], eax
0x1400157fb  add     eax, esi
0x1400157fd  jnz     short loc_140015827
0x1400157ff  mov     rax, [rdi]
0x140015802  mov     rcx, rdi
0x140015805  mov     rax, [rax]
0x140015808  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001580d  mov     eax, esi
0x14001580f  lock xadd [rdi+0Ch], eax
0x140015814  add     eax, esi
0x140015816  jnz     short loc_140015827
0x140015818  mov     rax, [rdi]
0x14001581b  mov     rcx, rdi
0x14001581e  mov     rax, [rax+8]
0x140015822  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015827  mov     rcx, [rbp+60h+var_50]
0x14001582b  xor     rcx, rsp; StackCookie
0x14001582e  call    __security_check_cookie
0x140015833  add     rsp, 128h
0x14001583a  pop     r15
0x14001583c  pop     r14
0x14001583e  pop     r13
0x140015840  pop     r12
0x140015842  pop     rdi
0x140015843  pop     rsi
0x140015844  pop     rbx
0x140015845  pop     rbp
0x140015846  retn
```
