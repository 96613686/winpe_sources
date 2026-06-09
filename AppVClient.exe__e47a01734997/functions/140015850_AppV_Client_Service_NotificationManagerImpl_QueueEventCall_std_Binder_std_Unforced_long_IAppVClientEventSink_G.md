# AppV::Client::Service::NotificationManagerImpl::QueueEventCall<std::_Binder<std::_Unforced,long (IAppVClientEventSink::*)(_GUID,_GUID,unsigned __int64),std::_Ph<1> const &,_GUID const &,_GUID const &,unsigned __int64 &>>(ClientEventType,std::_Binder<std::_Unforced,long (IAppVClientEventSink::*)(_GUID,_GUID,unsigned __int64),std::_Ph<1> const &,_GUID const &,_GUID const &,unsigned __int64 &> const &)

- ea: `0x140015850`
- end: `0x140015b98`
- name: `??$QueueEventCall@V?$_Binder@U_Unforced@std@@P8IAppVClientEventSink@@EAAJU_GUID@@0_K@ZAEBU?$_Ph@$00@2@AEBU4@AEBU4@AEA_K@std@@@NotificationManagerImpl@Service@Client@AppV@@AEAAXW4ClientEventType@@AEBV?$_Binder@U_Unforced@std@@P8IAppVClientEventSink@@EAAJU_GUID@@0_K@ZAEBU?$_Ph@$00@2@AEBU4@AEBU4@AEA_K@std@@@Z`
- size: `840`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `3`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x140017a10`
- `0x1400181a0`
- `0x140018690`

## callees

- `0x140004280`
- `0x1400042a4`
- `0x140006304`
- `0x1400147fc`
- `0x140015850`
- `0x1400162e0`
- `0x1400163f4`
- `0x1400165b4`
- `0x1400173c4`
- `0x14006a010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14001599b`
- `KERNEL32!CloseHandle` at `0x1400159c1`
- `KERNEL32!CloseHandle` at `0x140015b34`
- `KERNEL32!CloseHandle` at `0x14001599b`
- `KERNEL32!CloseHandle` at `0x1400159c1`
- `KERNEL32!CloseHandle` at `0x140015b34`
- `KERNEL32!GetCurrentThreadId` at `0x1400159f6`
- `KERNEL32!GetCurrentThreadId` at `0x1400159f6`
- `KERNEL32!LeaveCriticalSection` at `0x140015b25`
- `KERNEL32!LeaveCriticalSection` at `0x140015b25`
- `KERNEL32!EnterCriticalSection` at `0x1400159e6`
- `KERNEL32!EnterCriticalSection` at `0x1400159e6`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall AppV::Client::Service::NotificationManagerImpl::QueueEventCall<std::_Binder<std::_Unforced,long (IAppVClientEventSink::*)(_GUID,_GUID,unsigned __int64),std::_Ph<1> const &,_GUID const &,_GUID const &,unsigned __int64 &>>(
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
  v6 = operator new(0x40u);
  hObject = v6;
  *v6 = `AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>::CreateEventCall<std::_Binder<std::_Unforced,long (IAppVClientEventSink::*)(_GUID,_GUID,unsigned __int64),std::_Ph<1> const &,_GUID const &,_GUID const &,unsigned __int64 &>>'::`2'::EventCallImpl::`vftable';
  v6[1] = *(_QWORD *)a3;
  v6[2] = *(_QWORD *)(a3 + 8);
  *(_OWORD *)(v6 + 3) = *(_OWORD *)(a3 + 16);
  *(_OWORD *)(v6 + 5) = *(_OWORD *)(a3 + 32);
  *((_BYTE *)v6 + 56) = *(_BYTE *)(a3 + 48);
  hObject = v6;
  v7 = operator new(0x18u);
  *(_OWORD *)v7 = 0;
  *((_DWORD *)v7 + 2) = 1;
  *((_DWORD *)v7 + 3) = 1;
  *(_QWORD *)v7 = ___7___Ref_count_VEventCallImpl__1____CreateEventCall_V___Binder_U_Unforced_std__P8IAppVClientEventSink__EAAJU_GUID__0_K_ZAEBU___Ph__00_2_AEBU4_AEBU4_AEA_K_std_____Subscriber_UIAppVClientEventSink__JUEnterpriseDeliveryParameters_Host_Client_AppV___Host_Client_AppV__SAXAEBV___Binder_U_Unforced_std__P8IAppVClientEventSink__EAAJU_GUID__0_K_ZAEBU___Ph__00_2_AEBU4_AEBU4_AEA_K_std__AEAV__shared_ptr_VEventCall___Subscriber_UIAppVClientEventSink__JUEnterpriseDeliveryParameters_Host_Client_AppV___Host_Client_AppV___7__Z__std__6B_;
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
0x140015850  push    rbp
0x140015852  push    rbx
0x140015853  push    rsi
0x140015854  push    rdi
0x140015855  push    r12
0x140015857  push    r13
0x140015859  push    r14
0x14001585b  push    r15
0x14001585d  lea     rbp, [rsp-28h]
0x140015862  sub     rsp, 128h
0x140015869  mov     rax, cs:__security_cookie
0x140015870  xor     rax, rsp
0x140015873  mov     [rbp+60h+var_50], rax
0x140015877  mov     rbx, r8
0x14001587a  mov     r12d, edx
0x14001587d  mov     r13, rcx
0x140015880  mov     esi, 1
0x140015885  test    byte ptr cs:Microsoft_AppV_SharedPerformanceEnableBits, sil
0x14001588c  jz      short loc_1400158C3
0x14001588e  mov     dword ptr [rsp+160h+var_130], edx
0x140015892  lea     rax, [rsp+160h+var_130]
0x140015897  mov     [rbp+60h+var_98], rax
0x14001589b  mov     [rbp+60h+var_90], 4
0x1400158a3  lea     rax, [rbp+60h+var_A8]
0x1400158a7  mov     [rsp+160h+var_140], rax
0x1400158ac  lea     r9d, [rsi+1]
0x1400158b0  lea     rdx, Service_QueueClientEventBegin
0x1400158b7  lea     rcx, PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context
0x1400158be  call    McGenEventWrite_EventWriteTransfer
0x1400158c3  xorps   xmm0, xmm0
0x1400158c6  movdqu  [rsp+160h+var_108], xmm0
0x1400158cc  mov     ecx, 40h ; '@'; Size
0x1400158d1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400158d6  mov     r15, rax
0x1400158d9  mov     [rsp+160h+hObject], rax
0x1400158de  lea     rax, ??_7EventCallImpl@?1???$CreateEventCall@V?$_Binder@U_Unforced@std@@P8IAppVClientEventSink@@EAAJU_GUID@@0_K@ZAEBU?$_Ph@$00@2@AEBU4@AEBU4@AEA_K@std@@@?$Subscriber@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@@Host@Client@AppV@@SAXAEBV?$_Binder@U_Unforced@std@@P8IAppVClientEventSink@@EAAJU_GUID@@0_K@ZAEBU?$_Ph@$00@2@AEBU4@AEBU4@AEA_K@std@@AEAV?$shared_ptr@VEventCall@?$Subscriber@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@@Host@Client@AppV@@@6@@Z@6B@; const `AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>::CreateEventCall<std::_Binder<std::_Unforced,long (IAppVClientEventSink::*)(_GUID,_GUID,unsigned __int64),std::_Ph<1> const &,_GUID const &,_GUID const &,unsigned __int64 &>>(std::_Binder<std::_Unforced,long (IAppVClientEventSink::*)(_GUID,_GUID,unsigned __int64),std::_Ph<1> const &,_GUID const &,_GUID const &,unsigned __int64 &> const &,std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>::EventCall> &)'::`2'::EventCallImpl::`vftable'
0x1400158e5  mov     [r15], rax
0x1400158e8  mov     rcx, [rbx]
0x1400158eb  mov     [r15+8], rcx
0x1400158ef  mov     rcx, [rbx+8]
0x1400158f3  mov     [r15+10h], rcx
0x1400158f7  movups  xmm0, xmmword ptr [rbx+10h]
0x1400158fb  movdqu  xmmword ptr [r15+18h], xmm0
0x140015901  movups  xmm1, xmmword ptr [rbx+20h]
0x140015905  movdqu  xmmword ptr [r15+28h], xmm1
0x14001590b  mov     al, [rbx+30h]
0x14001590e  mov     [r15+38h], al
0x140015912  mov     [rsp+160h+hObject], r15
0x140015917  mov     ecx, 18h; Size
0x14001591c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140015921  mov     rdi, rax
0x140015924  mov     [rsp+160h+hObject], rax
0x140015929  xorps   xmm0, xmm0
0x14001592c  movups  xmmword ptr [rax], xmm0
0x14001592f  mov     [rax+8], esi
0x140015932  mov     [rax+0Ch], esi
0x140015935  lea     rax, ??_7?$_Ref_count@VEventCallImpl@?1???$CreateEventCall@V?$_Binder@U_Unforced@std@@P8IAppVClientEventSink@@EAAJU_GUID@@0_K@ZAEBU?$_Ph@$00@2@AEBU4@AEBU4@AEA_K@std@@@?$Subscriber@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@@Host@Client@AppV@@SAXAEBV?$_Binder@U_Unforced@std@@P8IAppVClientEventSink@@EAAJU_GUID@@0_K@ZAEBU?$_Ph@$00@2@AEBU4@AEBU4@AEA_K@std@@AEAV?$shared_ptr@VEventCall@?$Subscriber@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@@Host@Client@AppV@@@7@@Z@@std@@6B@; const std::_Ref_count<`AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>::CreateEventCall<std::_Binder<std::_Unforced,long (IAppVClientEventSink::*)(_GUID,_GUID,unsigned __int64),std::_Ph<1> const &,_GUID const &,_GUID const &,unsigned __int64 &>>(std::_Binder<std::_Unforced,long (IAppVClientEventSink::*)(_GUID,_GUID,unsigned __int64),std::_Ph<1> const &,_GUID const &,_GUID const &,unsigned __int64 &> const &,std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>::EventCall> &)'::`2'::EventCallImpl>::`vftable'
0x14001593c  mov     [rdi], rax
0x14001593f  mov     [rdi+10h], r15
0x140015943  mov     qword ptr [rsp+160h+var_108], r15
0x140015948  mov     qword ptr [rsp+160h+var_108+8], rdi
0x14001594d  movups  [rbp+60h+var_A8], xmm0
0x140015951  mov     [rbp+60h+var_98], 0
0x140015959  mov     [rbp+60h+var_90], 7
0x140015961  xor     eax, eax
0x140015963  mov     word ptr [rbp+60h+var_A8], ax
0x140015967  xor     ebx, ebx
0x140015969  mov     [rsp+160h+hObject], rbx
0x14001596e  mov     eax, r12d
0x140015971  and     eax, 0FFFF0000h
0x140015976  mov     dword ptr [rsp+160h+var_130], eax
0x14001597a  jz      short loc_1400159CE
0x14001597c  lea     rdx, [rsp+160h+hObject]
0x140015981  lea     rcx, [rbp+60h+var_A8]
0x140015985  call    ?GetSessionIdentity@NotificationManagerImpl@Service@Client@AppV@@CA_KAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVCHandle@ATL@@@Z; AppV::Client::Service::NotificationManagerImpl::GetSessionIdentity(std::wstring &,ATL::CHandle &)
0x14001598a  bt      rax, 27h ; '''
0x14001598f  jb      short loc_1400159B4
0x140015991  mov     rcx, [rsp+160h+hObject]; hObject
0x140015996  test    rcx, rcx
0x140015999  jz      short loc_1400159A2
0x14001599b  call    cs:__imp_CloseHandle
0x1400159a1  nop
0x1400159a2  lea     rcx, [rbp+60h+var_A8]
0x1400159a6  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400159ab  nop
0x1400159ac  or      esi, 0FFFFFFFFh
0x1400159af  jmp     loc_140015B45
0x1400159b4  mov     rbx, [rsp+160h+hObject]
0x1400159b9  test    rbx, rbx
0x1400159bc  jz      short loc_1400159CE
0x1400159be  mov     rcx, rbx; hObject
0x1400159c1  call    cs:__imp_CloseHandle
0x1400159c7  xor     ebx, ebx
0x1400159c9  mov     [rsp+160h+hObject], rbx
0x1400159ce  lea     rax, ??_7?$lock_holder@Vcritical_section@shared@softricity@@@shared@softricity@@6B@; const softricity::shared::lock_holder<softricity::shared::critical_section>::`vftable'
0x1400159d5  mov     [rsp+160h+var_F8], rax
0x1400159da  lea     r14, [r13+10h]
0x1400159de  mov     [rsp+160h+var_E8], r14
0x1400159e3  mov     rcx, r14; lpCriticalSection
0x1400159e6  call    cs:__imp_EnterCriticalSection
0x1400159ec  add     [r14+28h], esi
0x1400159f0  cmp     [r14+28h], esi
0x1400159f4  jnz     short loc_140015A00
0x1400159f6  call    cs:__imp_GetCurrentThreadId
0x1400159fc  mov     [r14+2Ch], eax
0x140015a00  mov     [rsp+160h+var_F0], sil
0x140015a05  or      esi, 0FFFFFFFFh
0x140015a08  xorps   xmm0, xmm0
0x140015a0b  cmp     dword ptr [rsp+160h+var_130], 0
0x140015a10  jnz     short loc_140015A49
0x140015a12  movdqu  [rsp+160h+var_120], xmm0
0x140015a18  lock inc dword ptr [rdi+8]
0x140015a1c  mov     qword ptr [rsp+160h+var_120], r15
0x140015a21  mov     qword ptr [rsp+160h+var_120+8], rdi
0x140015a26  mov     [rsp+160h+var_110], r12d
0x140015a2b  mov     rdx, [r13+48h]
0x140015a2f  lea     r9, [rsp+160h+var_120]
0x140015a34  mov     r8, rdx
0x140015a37  mov     rdx, [rdx]
0x140015a3a  lea     rcx, [rbp+60h+var_88]
0x140015a3e  call    ??$for_each@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAUIAppVClientEventSink@@V?$shared_ptr@V?$Subscriber@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@@Host@Client@AppV@@@std@@@std@@@std@@@std@@@std@@VQueueEventByFilter@NotificationManagerImpl@Service@Client@AppV@@@std@@YA?AVQueueEventByFilter@NotificationManagerImpl@Service@Client@AppV@@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAUIAppVClientEventSink@@V?$shared_ptr@V?$Subscriber@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@@Host@Client@AppV@@@std@@@std@@@std@@@std@@@0@0V12345@@Z; std::for_each<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<IAppVClientEventSink * const,std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>>>>>>,AppV::Client::Service::NotificationManagerImpl::QueueEventByFilter>(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<IAppVClientEventSink * const,std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>>>>>>,std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<IAppVClientEventSink * const,std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>>>>>>,AppV::Client::Service::NotificationManagerImpl::QueueEventByFilter)
0x140015a43  mov     r15, qword ptr [rbp+60h+var_88+8]
0x140015a47  jmp     short loc_140015A98
0x140015a49  lea     rax, [rbp+60h+var_88]
0x140015a4d  mov     [rsp+160h+var_130], rax
0x140015a52  movdqu  [rbp+60h+var_88], xmm0
0x140015a57  lock inc dword ptr [rdi+8]
0x140015a5b  mov     qword ptr [rbp+60h+var_88], r15
0x140015a5f  mov     qword ptr [rbp+60h+var_88+8], rdi
0x140015a63  lea     rdx, [rbp+60h+var_A8]
0x140015a67  lea     rcx, [rbp+60h+var_78]
0x140015a6b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140015a70  mov     [rbp+60h+var_58], r12d
0x140015a74  mov     rdx, [r13+48h]
0x140015a78  lea     r9, [rbp+60h+var_88]
0x140015a7c  mov     r8, rdx
0x140015a7f  mov     rdx, [rdx]
0x140015a82  lea     rcx, [rbp+60h+var_E0]
0x140015a86  call    ??$for_each@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAUIAppVClientEventSink@@V?$shared_ptr@V?$Subscriber@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@@Host@Client@AppV@@@std@@@std@@@std@@@std@@@std@@VQueueEventBySessionAndFilter@NotificationManagerImpl@Service@Client@AppV@@@std@@YA?AVQueueEventBySessionAndFilter@NotificationManagerImpl@Service@Client@AppV@@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAUIAppVClientEventSink@@V?$shared_ptr@V?$Subscriber@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@@Host@Client@AppV@@@std@@@std@@@std@@@std@@@0@0V12345@@Z; std::for_each<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<IAppVClientEventSink * const,std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>>>>>>,AppV::Client::Service::NotificationManagerImpl::QueueEventBySessionAndFilter>(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<IAppVClientEventSink * const,std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>>>>>>,std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<IAppVClientEventSink * const,std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>>>>>>,AppV::Client::Service::NotificationManagerImpl::QueueEventBySessionAndFilter)
0x140015a8b  lea     rcx, [rbp+60h+var_D0]
0x140015a8f  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140015a94  mov     r15, [rbp+60h+var_D8]
0x140015a98  test    r15, r15
0x140015a9b  jz      short loc_140015AD2
0x140015a9d  mov     eax, esi
0x140015a9f  lock xadd [r15+8], eax
0x140015aa5  add     eax, esi
0x140015aa7  jnz     short loc_140015AD2
0x140015aa9  mov     rax, [r15]
0x140015aac  mov     rcx, r15
0x140015aaf  mov     rax, [rax]
0x140015ab2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015ab7  mov     eax, esi
0x140015ab9  lock xadd [r15+0Ch], eax
0x140015abf  add     eax, esi
0x140015ac1  jnz     short loc_140015AD2
0x140015ac3  mov     rax, [r15]
0x140015ac6  mov     rcx, r15
0x140015ac9  mov     rax, [rax+8]
0x140015acd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015ad2  test    byte ptr cs:Microsoft_AppV_SharedPerformanceEnableBits, 1
0x140015ad9  jz      short loc_140015B14
0x140015adb  mov     dword ptr [rsp+160h+var_130], r12d
0x140015ae0  lea     rax, [rsp+160h+var_130]
0x140015ae5  mov     [rbp+60h+var_78], rax
0x140015ae9  mov     [rbp+60h+var_70], 4
0x140015af1  lea     rax, [rbp+60h+var_88]
0x140015af5  mov     [rsp+160h+var_140], rax
0x140015afa  mov     r9d, 2
0x140015b00  lea     rdx, Service_QueueClientEventEnd
0x140015b07  lea     rcx, PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context
0x140015b0e  call    McGenEventWrite_EventWriteTransfer
0x140015b13  nop
0x140015b14  add     [r14+28h], esi
0x140015b18  jnz     short loc_140015B22
0x140015b1a  mov     dword ptr [r14+2Ch], 0
0x140015b22  mov     rcx, r14; lpCriticalSection
0x140015b25  call    cs:__imp_LeaveCriticalSection
0x140015b2b  nop
0x140015b2c  test    rbx, rbx
0x140015b2f  jz      short loc_140015B3B
0x140015b31  mov     rcx, rbx; hObject
0x140015b34  call    cs:__imp_CloseHandle
0x140015b3a  nop
0x140015b3b  lea     rcx, [rbp+60h+var_A8]
0x140015b3f  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140015b44  nop
0x140015b45  mov     eax, esi
0x140015b47  lock xadd [rdi+8], eax
0x140015b4c  add     eax, esi
0x140015b4e  jnz     short loc_140015B78
0x140015b50  mov     rax, [rdi]
0x140015b53  mov     rcx, rdi
0x140015b56  mov     rax, [rax]
0x140015b59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015b5e  mov     eax, esi
0x140015b60  lock xadd [rdi+0Ch], eax
0x140015b65  add     eax, esi
0x140015b67  jnz     short loc_140015B78
0x140015b69  mov     rax, [rdi]
0x140015b6c  mov     rcx, rdi
0x140015b6f  mov     rax, [rax+8]
0x140015b73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015b78  mov     rcx, [rbp+60h+var_50]
0x140015b7c  xor     rcx, rsp; StackCookie
0x140015b7f  call    __security_check_cookie
0x140015b84  add     rsp, 128h
0x140015b8b  pop     r15
0x140015b8d  pop     r14
0x140015b8f  pop     r13
0x140015b91  pop     r12
0x140015b93  pop     rdi
0x140015b94  pop     rsi
0x140015b95  pop     rbx
0x140015b96  pop     rbp
0x140015b97  retn
```
