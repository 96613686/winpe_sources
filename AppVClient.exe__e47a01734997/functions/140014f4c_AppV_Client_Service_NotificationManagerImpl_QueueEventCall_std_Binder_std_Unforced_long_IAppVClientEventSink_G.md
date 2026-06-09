# AppV::Client::Service::NotificationManagerImpl::QueueEventCall<std::_Binder<std::_Unforced,long (IAppVClientEventSink::*)(_GUID,_GUID),std::_Ph<1> const &,_GUID const &,_GUID const &>>(ClientEventType,std::_Binder<std::_Unforced,long (IAppVClientEventSink::*)(_GUID,_GUID),std::_Ph<1> const &,_GUID const &,_GUID const &> const &)

- ea: `0x140014f4c`
- end: `0x14001528d`
- name: `??$QueueEventCall@V?$_Binder@U_Unforced@std@@P8IAppVClientEventSink@@EAAJU_GUID@@0@ZAEBU?$_Ph@$00@2@AEBU4@AEBU4@@std@@@NotificationManagerImpl@Service@Client@AppV@@AEAAXW4ClientEventType@@AEBV?$_Binder@U_Unforced@std@@P8IAppVClientEventSink@@EAAJU_GUID@@0@ZAEBU?$_Ph@$00@2@AEBU4@AEBU4@@std@@@Z`
- size: `833`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `2`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x140017a60`
- `0x140018640`

## callees

- `0x140004280`
- `0x1400042a4`
- `0x140006304`
- `0x1400147fc`
- `0x140014f4c`
- `0x1400162e0`
- `0x1400163f4`
- `0x1400165b4`
- `0x1400173c4`
- `0x14006a010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140015090`
- `KERNEL32!CloseHandle` at `0x1400150b6`
- `KERNEL32!CloseHandle` at `0x140015229`
- `KERNEL32!CloseHandle` at `0x140015090`
- `KERNEL32!CloseHandle` at `0x1400150b6`
- `KERNEL32!CloseHandle` at `0x140015229`
- `KERNEL32!GetCurrentThreadId` at `0x1400150eb`
- `KERNEL32!GetCurrentThreadId` at `0x1400150eb`
- `KERNEL32!LeaveCriticalSection` at `0x14001521a`
- `KERNEL32!LeaveCriticalSection` at `0x14001521a`
- `KERNEL32!EnterCriticalSection` at `0x1400150db`
- `KERNEL32!EnterCriticalSection` at `0x1400150db`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall AppV::Client::Service::NotificationManagerImpl::QueueEventCall<std::_Binder<std::_Unforced,long (IAppVClientEventSink::*)(_GUID,_GUID),std::_Ph<1> const &,_GUID const &,_GUID const &>>(
        __int64 a1,
        int a2,
        __int64 a3)
{
  _QWORD *v6; // r13
  void *v7; // rdi
  HANDLE v8; // rbx
  __int64 v9; // r14
  __int64 v10; // r8
  volatile signed __int32 *v11; // r15
  __int64 result; // rax
  __int128 *v14; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE hObject; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v16; // [rsp+40h] [rbp-C0h] BYREF
  int v17; // [rsp+50h] [rbp-B0h]
  __int128 v18; // [rsp+58h] [rbp-A8h]
  void **v19; // [rsp+68h] [rbp-98h]
  char v20; // [rsp+70h] [rbp-90h]
  __int64 v21; // [rsp+78h] [rbp-88h]
  _BYTE v22[8]; // [rsp+80h] [rbp-80h] BYREF
  volatile signed __int32 *v23; // [rsp+88h] [rbp-78h]
  _BYTE v24[40]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v25; // [rsp+B8h] [rbp-48h] BYREF
  __int128 **v26; // [rsp+C8h] [rbp-38h]
  __int64 v27; // [rsp+D0h] [rbp-30h]
  __int128 v28; // [rsp+D8h] [rbp-28h] BYREF
  _QWORD v29[4]; // [rsp+E8h] [rbp-18h] BYREF
  int v30; // [rsp+108h] [rbp+8h]

  if ( (Microsoft_AppV_SharedPerformanceEnableBits & 1) != 0 )
  {
    LODWORD(v14) = a2;
    v26 = &v14;
    v27 = 4;
    McGenEventWrite_EventWriteTransfer(
      PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context,
      Service_QueueClientEventBegin,
      a3,
      2,
      &v25);
  }
  v18 = 0;
  v6 = operator new(0x38u);
  hObject = v6;
  *v6 = `AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>::CreateEventCall<std::_Binder<std::_Unforced,long (IAppVClientEventSink::*)(_GUID,_GUID),std::_Ph<1> const &,_GUID const &,_GUID const &>>'::`2'::EventCallImpl::`vftable';
  v6[1] = *(_QWORD *)a3;
  *((_OWORD *)v6 + 1) = *(_OWORD *)(a3 + 8);
  *((_OWORD *)v6 + 2) = *(_OWORD *)(a3 + 24);
  *((_BYTE *)v6 + 48) = *(_BYTE *)(a3 + 40);
  hObject = v6;
  v7 = operator new(0x18u);
  *(_OWORD *)v7 = 0;
  *((_DWORD *)v7 + 2) = 1;
  *((_DWORD *)v7 + 3) = 1;
  *(_QWORD *)v7 = ___7___Ref_count_VEventCallImpl__1____CreateEventCall_V___Binder_U_Unforced_std__P8IAppVClientEventSink__EAAJU_GUID__0_ZAEBU___Ph__00_2_AEBU4_AEBU4__std_____Subscriber_UIAppVClientEventSink__JUEnterpriseDeliveryParameters_Host_Client_AppV___Host_Client_AppV__SAXAEBV___Binder_U_Unforced_std__P8IAppVClientEventSink__EAAJU_GUID__0_ZAEBU___Ph__00_2_AEBU4_AEBU4__std__AEAV__shared_ptr_VEventCall___Subscriber_UIAppVClientEventSink__JUEnterpriseDeliveryParameters_Host_Client_AppV___Host_Client_AppV___7__Z__std__6B_;
  *((_QWORD *)v7 + 2) = v6;
  *(_QWORD *)&v18 = v6;
  *((_QWORD *)&v18 + 1) = v7;
  v25 = 0;
  v26 = 0;
  v27 = 7;
  LOWORD(v25) = 0;
  v8 = 0;
  hObject = 0;
  LODWORD(v14) = a2 & 0xFFFF0000;
  if ( (a2 & 0xFFFF0000) != 0 )
  {
    if ( (AppV::Client::Service::NotificationManagerImpl::GetSessionIdentity(&v25, &hObject) & 0x8000000000LL) == 0 )
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
  v19 = &softricity::shared::lock_holder<softricity::shared::critical_section>::`vftable';
  v9 = a1 + 16;
  v21 = a1 + 16;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  if ( ++*(_DWORD *)(a1 + 56) == 1 )
    *(_DWORD *)(a1 + 60) = GetCurrentThreadId();
  v20 = 1;
  if ( (_DWORD)v14 )
  {
    v14 = &v28;
    v28 = 0;
    _InterlockedIncrement((volatile signed __int32 *)v7 + 2);
    *(_QWORD *)&v28 = v6;
    *((_QWORD *)&v28 + 1) = v7;
    std::wstring::wstring(v29, &v25);
    v30 = a2;
    std::for_each<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<IAppVClientEventSink * const,std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>>>>>>,AppV::Client::Service::NotificationManagerImpl::QueueEventBySessionAndFilter>(
      (__int64)v22,
      **(__int64 ***)(a1 + 72),
      *(__int64 **)(a1 + 72),
      (__int64)&v28);
    std::wstring::~wstring(v24);
    v11 = v23;
  }
  else
  {
    v16 = 0;
    _InterlockedIncrement((volatile signed __int32 *)v7 + 2);
    *(_QWORD *)&v16 = v6;
    *((_QWORD *)&v16 + 1) = v7;
    v17 = a2;
    std::for_each<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<IAppVClientEventSink * const,std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>>>>>>,AppV::Client::Service::NotificationManagerImpl::QueueEventByFilter>(
      (__int64)&v28,
      **(__int64 ***)(a1 + 72),
      *(__int64 **)(a1 + 72),
      (__int64)&v16);
    v11 = (volatile signed __int32 *)*((_QWORD *)&v28 + 1);
  }
  if ( v11 )
  {
    if ( _InterlockedExchangeAdd(v11 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
      if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
    }
  }
  if ( (Microsoft_AppV_SharedPerformanceEnableBits & 1) != 0 )
  {
    LODWORD(v14) = a2;
    v29[0] = &v14;
    v29[1] = 4;
    McGenEventWrite_EventWriteTransfer(
      PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context,
      Service_QueueClientEventEnd,
      v10,
      2,
      &v28);
  }
  if ( (*(_DWORD *)(v9 + 40))-- == 1 )
    *(_DWORD *)(v9 + 44) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)v9);
  if ( v8 )
    CloseHandle(v8);
LABEL_25:
  std::wstring::~wstring(&v25);
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
0x140014f4c  push    rbp
0x140014f4e  push    rbx
0x140014f4f  push    rsi
0x140014f50  push    rdi
0x140014f51  push    r12
0x140014f53  push    r13
0x140014f55  push    r14
0x140014f57  push    r15
0x140014f59  lea     rbp, [rsp-28h]
0x140014f5e  sub     rsp, 128h
0x140014f65  mov     rax, cs:__security_cookie
0x140014f6c  xor     rax, rsp
0x140014f6f  mov     [rbp+60h+var_50], rax
0x140014f73  mov     rbx, r8
0x140014f76  mov     r12d, edx
0x140014f79  mov     r15, rcx
0x140014f7c  mov     esi, 1
0x140014f81  test    byte ptr cs:Microsoft_AppV_SharedPerformanceEnableBits, sil
0x140014f88  jz      short loc_140014FBF
0x140014f8a  mov     dword ptr [rsp+160h+var_130], edx
0x140014f8e  lea     rax, [rsp+160h+var_130]
0x140014f93  mov     [rbp+60h+var_98], rax
0x140014f97  mov     [rbp+60h+var_90], 4
0x140014f9f  lea     rax, [rbp+60h+var_A8]
0x140014fa3  mov     [rsp+160h+var_140], rax
0x140014fa8  lea     r9d, [rsi+1]
0x140014fac  lea     rdx, Service_QueueClientEventBegin
0x140014fb3  lea     rcx, PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context
0x140014fba  call    McGenEventWrite_EventWriteTransfer
0x140014fbf  xorps   xmm0, xmm0
0x140014fc2  movdqu  [rsp+160h+var_108], xmm0
0x140014fc8  mov     ecx, 38h ; '8'; Size
0x140014fcd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140014fd2  mov     r13, rax
0x140014fd5  mov     [rsp+160h+hObject], rax
0x140014fda  lea     rax, ??_7EventCallImpl@?1???$CreateEventCall@V?$_Binder@U_Unforced@std@@P8IAppVClientEventSink@@EAAJU_GUID@@0@ZAEBU?$_Ph@$00@2@AEBU4@AEBU4@@std@@@?$Subscriber@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@@Host@Client@AppV@@SAXAEBV?$_Binder@U_Unforced@std@@P8IAppVClientEventSink@@EAAJU_GUID@@0@ZAEBU?$_Ph@$00@2@AEBU4@AEBU4@@std@@AEAV?$shared_ptr@VEventCall@?$Subscriber@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@@Host@Client@AppV@@@6@@Z@6B@; const `AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>::CreateEventCall<std::_Binder<std::_Unforced,long (IAppVClientEventSink::*)(_GUID,_GUID),std::_Ph<1> const &,_GUID const &,_GUID const &>>(std::_Binder<std::_Unforced,long (IAppVClientEventSink::*)(_GUID,_GUID),std::_Ph<1> const &,_GUID const &,_GUID const &> const &,std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>::EventCall> &)'::`2'::EventCallImpl::`vftable'
0x140014fe1  mov     [r13+0], rax
0x140014fe5  mov     rcx, [rbx]
0x140014fe8  mov     [r13+8], rcx
0x140014fec  movups  xmm0, xmmword ptr [rbx+8]
0x140014ff0  movdqu  xmmword ptr [r13+10h], xmm0
0x140014ff6  movups  xmm1, xmmword ptr [rbx+18h]
0x140014ffa  movdqu  xmmword ptr [r13+20h], xmm1
0x140015000  mov     cl, [rbx+28h]
0x140015003  mov     [r13+30h], cl
0x140015007  mov     [rsp+160h+hObject], r13
0x14001500c  mov     ecx, 18h; Size
0x140015011  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140015016  mov     rdi, rax
0x140015019  mov     [rsp+160h+hObject], rax
0x14001501e  xorps   xmm0, xmm0
0x140015021  movups  xmmword ptr [rax], xmm0
0x140015024  mov     [rax+8], esi
0x140015027  mov     [rax+0Ch], esi
0x14001502a  lea     rax, ??_7?$_Ref_count@VEventCallImpl@?1???$CreateEventCall@V?$_Binder@U_Unforced@std@@P8IAppVClientEventSink@@EAAJU_GUID@@0@ZAEBU?$_Ph@$00@2@AEBU4@AEBU4@@std@@@?$Subscriber@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@@Host@Client@AppV@@SAXAEBV?$_Binder@U_Unforced@std@@P8IAppVClientEventSink@@EAAJU_GUID@@0@ZAEBU?$_Ph@$00@2@AEBU4@AEBU4@@std@@AEAV?$shared_ptr@VEventCall@?$Subscriber@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@@Host@Client@AppV@@@7@@Z@@std@@6B@; const std::_Ref_count<`AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>::CreateEventCall<std::_Binder<std::_Unforced,long (IAppVClientEventSink::*)(_GUID,_GUID),std::_Ph<1> const &,_GUID const &,_GUID const &>>(std::_Binder<std::_Unforced,long (IAppVClientEventSink::*)(_GUID,_GUID),std::_Ph<1> const &,_GUID const &,_GUID const &> const &,std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>::EventCall> &)'::`2'::EventCallImpl>::`vftable'
0x140015031  mov     [rdi], rax
0x140015034  mov     [rdi+10h], r13
0x140015038  mov     qword ptr [rsp+160h+var_108], r13
0x14001503d  mov     qword ptr [rsp+160h+var_108+8], rdi
0x140015042  movups  [rbp+60h+var_A8], xmm0
0x140015046  mov     [rbp+60h+var_98], 0
0x14001504e  mov     [rbp+60h+var_90], 7
0x140015056  xor     eax, eax
0x140015058  mov     word ptr [rbp+60h+var_A8], ax
0x14001505c  xor     ebx, ebx
0x14001505e  mov     [rsp+160h+hObject], rbx
0x140015063  mov     eax, r12d
0x140015066  and     eax, 0FFFF0000h
0x14001506b  mov     dword ptr [rsp+160h+var_130], eax
0x14001506f  jz      short loc_1400150C3
0x140015071  lea     rdx, [rsp+160h+hObject]
0x140015076  lea     rcx, [rbp+60h+var_A8]
0x14001507a  call    ?GetSessionIdentity@NotificationManagerImpl@Service@Client@AppV@@CA_KAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVCHandle@ATL@@@Z; AppV::Client::Service::NotificationManagerImpl::GetSessionIdentity(std::wstring &,ATL::CHandle &)
0x14001507f  bt      rax, 27h ; '''
0x140015084  jb      short loc_1400150A9
0x140015086  mov     rcx, [rsp+160h+hObject]; hObject
0x14001508b  test    rcx, rcx
0x14001508e  jz      short loc_140015097
0x140015090  call    cs:__imp_CloseHandle
0x140015096  nop
0x140015097  lea     rcx, [rbp+60h+var_A8]
0x14001509b  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400150a0  nop
0x1400150a1  or      esi, 0FFFFFFFFh
0x1400150a4  jmp     loc_14001523A
0x1400150a9  mov     rbx, [rsp+160h+hObject]
0x1400150ae  test    rbx, rbx
0x1400150b1  jz      short loc_1400150C3
0x1400150b3  mov     rcx, rbx; hObject
0x1400150b6  call    cs:__imp_CloseHandle
0x1400150bc  xor     ebx, ebx
0x1400150be  mov     [rsp+160h+hObject], rbx
0x1400150c3  lea     rax, ??_7?$lock_holder@Vcritical_section@shared@softricity@@@shared@softricity@@6B@; const softricity::shared::lock_holder<softricity::shared::critical_section>::`vftable'
0x1400150ca  mov     [rsp+160h+var_F8], rax
0x1400150cf  lea     r14, [r15+10h]
0x1400150d3  mov     [rsp+160h+var_E8], r14
0x1400150d8  mov     rcx, r14; lpCriticalSection
0x1400150db  call    cs:__imp_EnterCriticalSection
0x1400150e1  add     [r14+28h], esi
0x1400150e5  cmp     [r14+28h], esi
0x1400150e9  jnz     short loc_1400150F5
0x1400150eb  call    cs:__imp_GetCurrentThreadId
0x1400150f1  mov     [r14+2Ch], eax
0x1400150f5  mov     [rsp+160h+var_F0], sil
0x1400150fa  or      esi, 0FFFFFFFFh
0x1400150fd  xorps   xmm0, xmm0
0x140015100  cmp     dword ptr [rsp+160h+var_130], 0
0x140015105  jnz     short loc_14001513E
0x140015107  movdqu  [rsp+160h+var_120], xmm0
0x14001510d  lock inc dword ptr [rdi+8]
0x140015111  mov     qword ptr [rsp+160h+var_120], r13
0x140015116  mov     qword ptr [rsp+160h+var_120+8], rdi
0x14001511b  mov     [rsp+160h+var_110], r12d
0x140015120  mov     rdx, [r15+48h]
0x140015124  lea     r9, [rsp+160h+var_120]
0x140015129  mov     r8, rdx
0x14001512c  mov     rdx, [rdx]
0x14001512f  lea     rcx, [rbp+60h+var_88]
0x140015133  call    ??$for_each@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAUIAppVClientEventSink@@V?$shared_ptr@V?$Subscriber@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@@Host@Client@AppV@@@std@@@std@@@std@@@std@@@std@@VQueueEventByFilter@NotificationManagerImpl@Service@Client@AppV@@@std@@YA?AVQueueEventByFilter@NotificationManagerImpl@Service@Client@AppV@@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAUIAppVClientEventSink@@V?$shared_ptr@V?$Subscriber@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@@Host@Client@AppV@@@std@@@std@@@std@@@std@@@0@0V12345@@Z; std::for_each<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<IAppVClientEventSink * const,std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>>>>>>,AppV::Client::Service::NotificationManagerImpl::QueueEventByFilter>(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<IAppVClientEventSink * const,std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>>>>>>,std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<IAppVClientEventSink * const,std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>>>>>>,AppV::Client::Service::NotificationManagerImpl::QueueEventByFilter)
0x140015138  mov     r15, qword ptr [rbp+60h+var_88+8]
0x14001513c  jmp     short loc_14001518D
0x14001513e  lea     rax, [rbp+60h+var_88]
0x140015142  mov     [rsp+160h+var_130], rax
0x140015147  movdqu  [rbp+60h+var_88], xmm0
0x14001514c  lock inc dword ptr [rdi+8]
0x140015150  mov     qword ptr [rbp+60h+var_88], r13
0x140015154  mov     qword ptr [rbp+60h+var_88+8], rdi
0x140015158  lea     rdx, [rbp+60h+var_A8]
0x14001515c  lea     rcx, [rbp+60h+var_78]
0x140015160  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140015165  mov     [rbp+60h+var_58], r12d
0x140015169  mov     rdx, [r15+48h]
0x14001516d  lea     r9, [rbp+60h+var_88]
0x140015171  mov     r8, rdx
0x140015174  mov     rdx, [rdx]
0x140015177  lea     rcx, [rbp+60h+var_E0]
0x14001517b  call    ??$for_each@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAUIAppVClientEventSink@@V?$shared_ptr@V?$Subscriber@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@@Host@Client@AppV@@@std@@@std@@@std@@@std@@@std@@VQueueEventBySessionAndFilter@NotificationManagerImpl@Service@Client@AppV@@@std@@YA?AVQueueEventBySessionAndFilter@NotificationManagerImpl@Service@Client@AppV@@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAUIAppVClientEventSink@@V?$shared_ptr@V?$Subscriber@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@@Host@Client@AppV@@@std@@@std@@@std@@@std@@@0@0V12345@@Z; std::for_each<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<IAppVClientEventSink * const,std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>>>>>>,AppV::Client::Service::NotificationManagerImpl::QueueEventBySessionAndFilter>(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<IAppVClientEventSink * const,std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>>>>>>,std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<IAppVClientEventSink * const,std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>>>>>>,AppV::Client::Service::NotificationManagerImpl::QueueEventBySessionAndFilter)
0x140015180  lea     rcx, [rbp+60h+var_D0]
0x140015184  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140015189  mov     r15, [rbp+60h+var_D8]
0x14001518d  test    r15, r15
0x140015190  jz      short loc_1400151C7
0x140015192  mov     eax, esi
0x140015194  lock xadd [r15+8], eax
0x14001519a  add     eax, esi
0x14001519c  jnz     short loc_1400151C7
0x14001519e  mov     rax, [r15]
0x1400151a1  mov     rcx, r15
0x1400151a4  mov     rax, [rax]
0x1400151a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400151ac  mov     eax, esi
0x1400151ae  lock xadd [r15+0Ch], eax
0x1400151b4  add     eax, esi
0x1400151b6  jnz     short loc_1400151C7
0x1400151b8  mov     rax, [r15]
0x1400151bb  mov     rcx, r15
0x1400151be  mov     rax, [rax+8]
0x1400151c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400151c7  test    byte ptr cs:Microsoft_AppV_SharedPerformanceEnableBits, 1
0x1400151ce  jz      short loc_140015209
0x1400151d0  mov     dword ptr [rsp+160h+var_130], r12d
0x1400151d5  lea     rax, [rsp+160h+var_130]
0x1400151da  mov     [rbp+60h+var_78], rax
0x1400151de  mov     [rbp+60h+var_70], 4
0x1400151e6  lea     rax, [rbp+60h+var_88]
0x1400151ea  mov     [rsp+160h+var_140], rax
0x1400151ef  mov     r9d, 2
0x1400151f5  lea     rdx, Service_QueueClientEventEnd
0x1400151fc  lea     rcx, PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context
0x140015203  call    McGenEventWrite_EventWriteTransfer
0x140015208  nop
0x140015209  add     [r14+28h], esi
0x14001520d  jnz     short loc_140015217
0x14001520f  mov     dword ptr [r14+2Ch], 0
0x140015217  mov     rcx, r14; lpCriticalSection
0x14001521a  call    cs:__imp_LeaveCriticalSection
0x140015220  nop
0x140015221  test    rbx, rbx
0x140015224  jz      short loc_140015230
0x140015226  mov     rcx, rbx; hObject
0x140015229  call    cs:__imp_CloseHandle
0x14001522f  nop
0x140015230  lea     rcx, [rbp+60h+var_A8]
0x140015234  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140015239  nop
0x14001523a  mov     eax, esi
0x14001523c  lock xadd [rdi+8], eax
0x140015241  add     eax, esi
0x140015243  jnz     short loc_14001526D
0x140015245  mov     rax, [rdi]
0x140015248  mov     rcx, rdi
0x14001524b  mov     rax, [rax]
0x14001524e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015253  mov     eax, esi
0x140015255  lock xadd [rdi+0Ch], eax
0x14001525a  add     eax, esi
0x14001525c  jnz     short loc_14001526D
0x14001525e  mov     rax, [rdi]
0x140015261  mov     rcx, rdi
0x140015264  mov     rax, [rax+8]
0x140015268  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001526d  mov     rcx, [rbp+60h+var_50]
0x140015271  xor     rcx, rsp; StackCookie
0x140015274  call    __security_check_cookie
0x140015279  add     rsp, 128h
0x140015280  pop     r15
0x140015282  pop     r14
0x140015284  pop     r13
0x140015286  pop     r12
0x140015288  pop     rdi
0x140015289  pop     rsi
0x14001528a  pop     rbx
0x14001528b  pop     rbp
0x14001528c  retn
```
