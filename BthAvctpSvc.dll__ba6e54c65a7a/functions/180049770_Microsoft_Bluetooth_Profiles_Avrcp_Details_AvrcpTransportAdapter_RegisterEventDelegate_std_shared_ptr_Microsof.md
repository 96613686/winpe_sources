# Microsoft::Bluetooth::Profiles::Avrcp::Details::AvrcpTransportAdapter::RegisterEventDelegate(std::shared_ptr<Microsoft::Bluetooth::Profiles::Avrcp::AvrcpTransport::EventDelegate>)

- ea: `0x180049770`
- end: `0x1800499b6`
- name: `?RegisterEventDelegate@AvrcpTransportAdapter@Details@Avrcp@Profiles@Bluetooth@Microsoft@@UEAA?AV?$unique_ptr@VEventRegistration@EventNotifier@Foundation@Bluetooth@Microsoft@@U?$default_delete@VEventRegistration@EventNotifier@Foundation@Bluetooth@Microsoft@@@std@@@std@@V?$shared_ptr@VEventDelegate@AvrcpTransport@Avrcp@Profiles@Bluetooth@Microsoft@@@8@@Z`
- size: `582`
- prototype: `__int64 __fastcall(Microsoft::Bluetooth::Profiles::Avrcp::Details::AvrcpTransportAdapter *this)`
- caller_count: `0`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001dd0`
- `0x1800021dc`
- `0x180004060`
- `0x18000b69c`
- `0x18000de78`
- `0x18000deb0`
- `0x18000e0c0`
- `0x180010b78`
- `0x1800120e8`
- `0x180012168`
- `0x180019c68`
- `0x180046bd4`
- `0x180049518`
- `0x180049770`
- `0x1800499bc`
- `0x18004aea4`
- `0x18005f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004982e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004982e`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
struct _GUID *__fastcall Microsoft::Bluetooth::Profiles::Avrcp::Details::AvrcpTransportAdapter::RegisterEventDelegate(
        Microsoft::Bluetooth::Profiles::Avrcp::Details::AvrcpTransportAdapter *this,
        struct _GUID *a2,
        __int64 *a3)
{
  bool v6; // dl
  __int64 v7; // rax
  __int64 v8; // r10
  __int64 v9; // rax
  __int64 v10; // rcx
  std::_Ref_count_base *v11; // rcx
  __int64 v12; // rax
  _QWORD *v13; // rbx
  void *v14; // rax
  std::_Ref_count_base *v15; // rcx
  int v17; // [rsp+20h] [rbp-59h]
  int v18; // [rsp+28h] [rbp-51h]
  int v19; // [rsp+30h] [rbp-49h]
  int v20; // [rsp+38h] [rbp-41h]
  _QWORD v21[2]; // [rsp+60h] [rbp-19h] BYREF
  GUID v22; // [rsp+70h] [rbp-9h] BYREF
  struct _GUID *v23; // [rsp+80h] [rbp+7h] BYREF
  __int64 v24[2]; // [rsp+90h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v23 = a2;
  v21[0] = a3;
  *(struct _GUID *)v24 = *Microsoft::Bluetooth::Foundation::GuidFactory::GetNextId(&v22, a2);
  v6 = WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  if ( v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v7 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 48);
    WPP_RECORDER_AND_TRACE_SF_iS_guid_q(
      *(_QWORD *)(v8 + 16),
      v17,
      v18,
      v19,
      v20,
      *((_QWORD *)this + 10),
      v7,
      (__int64)v24,
      (char)this);
  }
  AcquireSRWLockExclusive((PSRWLOCK)this + 3);
  v23 = (struct _GUID *)((char *)this + 24);
  if ( *(_QWORD *)std::weak_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestServer<Microsoft::Bluetooth::Foundation::ThreadProcessorWorkResult>>::lock(
                    (char *)this + 168,
                    &v22) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x28,
      (unsigned int)"onecore\\drivers\\bluetooth\\legacy\\avrcptransportadapter\\lib\\avrcptransportadapter.cpp",
      (const char *)0x8000FFFFLL,
      v17);
  if ( *(_QWORD *)v22.Data4 )
    std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)v22.Data4);
  v9 = a3[1];
  if ( v9 )
  {
    v10 = *a3;
    _InterlockedIncrement((volatile signed __int32 *)(v9 + 12));
  }
  else
  {
    v10 = 0;
    v9 = 0;
  }
  *((_QWORD *)this + 21) = v10;
  v11 = (std::_Ref_count_base *)*((_QWORD *)this + 22);
  *((_QWORD *)this + 22) = v9;
  if ( v11 )
    std::_Ref_count_base::_Decwref(v11);
  v12 = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64, void *, __int64, _QWORD))(**((_QWORD **)this + 11) + 32LL))(
          *((_QWORD *)this + 11),
          &v22,
          4276228,
          &Microsoft::Bluetooth::Profiles::Avrcp::Details::AvrcpTransportAdapter::c_eventQueueConfig,
          2,
          0);
  std::shared_ptr<Microsoft::Bluetooth::Foundation::AsyncDeviceInterfaceWatcher>::operator=((char *)this + 104, v12);
  if ( *(_QWORD *)v22.Data4 )
    std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)v22.Data4);
  *(_OWORD *)((char *)this + 184) = *(_OWORD *)v24;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v23);
  Microsoft::Bluetooth::Profiles::Avrcp::Details::AvrcpTransportAdapter::StartEventRead((RTL_SRWLOCK *)this);
  Microsoft::Bluetooth::Profiles::Avrcp::Details::AvrcpTransportAdapter::ReadCurrentChannelState(this, ChannelTypeOther);
  Microsoft::Bluetooth::Profiles::Avrcp::Details::AvrcpTransportAdapter::ReadCurrentChannelState(this, ChannelTypeNone);
  v13 = (_QWORD *)std::enable_shared_from_this<Microsoft::Bluetooth::Foundation::Details::AsyncDeviceInterfaceWatcherImpl>::shared_from_this(
                    (char *)this + 8,
                    &v22);
  v14 = operator new(0x48u);
  v21[0] = v14;
  v21[0] = *v13;
  v21[1] = v13[1];
  *v13 = 0;
  v13[1] = 0;
  *(_QWORD *)&a2->Data1 = Microsoft::Bluetooth::Foundation::EventNotifier::EventRegistration::EventRegistration(
                            v14,
                            1,
                            v24,
                            v21);
  if ( *(_QWORD *)v22.Data4 )
    std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)v22.Data4);
  v15 = (std::_Ref_count_base *)a3[1];
  if ( v15 )
    std::_Ref_count_base::_Decref(v15);
  return a2;
}

```

## disassembly

```asm
0x180049770  push    rbp
0x180049772  push    rbx
0x180049773  push    rsi
0x180049774  push    rdi
0x180049775  push    r14
0x180049777  lea     rbp, [rsp-37h]
0x18004977c  sub     rsp, 0B0h
0x180049783  mov     rax, cs:__security_cookie
0x18004978a  xor     rax, rsp
0x18004978d  mov     [rbp+57h+var_30], rax
0x180049791  mov     rsi, r8
0x180049794  mov     r14, rdx
0x180049797  mov     rdi, rcx
0x18004979a  mov     [rbp+57h+var_50], rdx
0x18004979e  mov     [rbp+57h+var_70], r8
0x1800497a2  lea     rcx, [rbp+57h+var_60]; this
0x1800497a6  call    ?GetNextId@GuidFactory@Foundation@Bluetooth@Microsoft@@YA?AU_GUID@@XZ; Microsoft::Bluetooth::Foundation::GuidFactory::GetNextId(void)
0x1800497ab  movups  xmm0, xmmword ptr [rax]
0x1800497ae  movdqu  xmmword ptr [rbp+57h+var_40], xmm0
0x1800497b3  lea     rax, WPP_GLOBAL_Control
0x1800497ba  mov     r10, cs:WPP_GLOBAL_Control
0x1800497c1  cmp     r10, rax
0x1800497c4  jz      short loc_1800497D8
0x1800497c6  test    byte ptr [r10+1Ch], 1
0x1800497cb  jz      short loc_1800497D8
0x1800497cd  cmp     byte ptr [r10+19h], 4
0x1800497d2  jb      short loc_1800497D8
0x1800497d4  mov     dl, 1
0x1800497d6  jmp     short loc_1800497DA
0x1800497d8  xor     dl, dl
0x1800497da  lea     rax, WPP_RECORDER_INITIALIZED
0x1800497e1  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1800497e8  setnz   r8b
0x1800497ec  test    dl, dl
0x1800497ee  jnz     short loc_1800497F5
0x1800497f0  test    r8b, r8b
0x1800497f3  jz      short loc_180049827
0x1800497f5  lea     rcx, [rdi+30h]
0x1800497f9  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800497fe  mov     qword ptr [rsp+0D0h+var_78], rdi; char
0x180049803  lea     rcx, [rbp+57h+var_40]
0x180049807  mov     [rsp+0D0h+var_80], rcx; __int64
0x18004980c  mov     [rsp+0D0h+var_88], rax; __int64
0x180049811  mov     rax, [rdi+50h]
0x180049815  mov     qword ptr [rsp+0D0h+var_90], rax; char
0x18004981a  mov     r9, [r10+28h]
0x18004981e  mov     rcx, [r10+10h]; LoggerHandle
0x180049822  call    WPP_RECORDER_AND_TRACE_SF_iS_guid_q
0x180049827  lea     rbx, [rdi+18h]
0x18004982b  mov     rcx, rbx; SRWLock
0x18004982e  call    cs:__imp_AcquireSRWLockExclusive
0x180049834  mov     [rbp+57h+var_50], rbx
0x180049838  lea     rbx, [rdi+0A8h]
0x18004983f  lea     rdx, [rbp+57h+var_60]
0x180049843  mov     rcx, rbx
0x180049846  call    ?lock@?$weak_ptr@V?$AsyncRequestServer@UThreadProcessorWorkResult@Foundation@Bluetooth@Microsoft@@@Foundation@Bluetooth@Microsoft@@@std@@QEBA?AV?$shared_ptr@V?$AsyncRequestServer@UThreadProcessorWorkResult@Foundation@Bluetooth@Microsoft@@@Foundation@Bluetooth@Microsoft@@@2@XZ; std::weak_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestServer<Microsoft::Bluetooth::Foundation::ThreadProcessorWorkResult>>::lock(void)
0x18004984b  nop
0x18004984c  mov     rcx, [rbp+5Fh]; this
0x180049850  cmp     qword ptr [rax], 0
0x180049854  jz      short loc_18004986E
0x180049856  mov     r9d, 8000FFFFh; char *
0x18004985c  lea     r8, aOnecoreDrivers_22; "onecore\\drivers\\bluetooth\\legacy\\av"...
0x180049863  mov     edx, 28h ; '('; void *
0x180049868  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004986e  mov     rcx, [rbp+57h+var_58]; this
0x180049872  test    rcx, rcx
0x180049875  jz      short loc_18004987C
0x180049877  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18004987c  mov     rax, [rsi+8]
0x180049880  test    rax, rax
0x180049883  jz      short loc_18004988E
0x180049885  mov     rcx, [rsi]
0x180049888  lock inc dword ptr [rax+0Ch]
0x18004988c  jmp     short loc_180049892
0x18004988e  xor     ecx, ecx
0x180049890  xor     eax, eax
0x180049892  mov     [rbx], rcx
0x180049895  mov     rcx, [rbx+8]; this
0x180049899  mov     [rbx+8], rax
0x18004989d  test    rcx, rcx
0x1800498a0  jz      short loc_1800498A7
0x1800498a2  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x1800498a7  mov     rcx, [rdi+58h]
0x1800498ab  mov     rax, [rcx]
0x1800498ae  mov     [rsp+0D0h+var_A8], 0
0x1800498b7  mov     [rsp+0D0h+var_B0], 2
0x1800498c0  lea     r9, ?c_eventQueueConfig@AvrcpTransportAdapter@Details@Avrcp@Profiles@Bluetooth@Microsoft@@0UBLUETOOTH_AVRCP_TRANSPORT_EVENT_QUEUE_CONFIG@@B; BLUETOOTH_AVRCP_TRANSPORT_EVENT_QUEUE_CONFIG const Microsoft::Bluetooth::Profiles::Avrcp::Details::AvrcpTransportAdapter::c_eventQueueConfig
0x1800498c7  mov     r8d, 414004h
0x1800498cd  lea     rdx, [rbp+57h+var_60]
0x1800498d1  mov     rax, [rax+20h]
0x1800498d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800498da  lea     rcx, [rdi+68h]
0x1800498de  mov     rdx, rax
0x1800498e1  call    ??4?$shared_ptr@VAsyncDeviceInterfaceWatcher@Foundation@Bluetooth@Microsoft@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Microsoft::Bluetooth::Foundation::AsyncDeviceInterfaceWatcher>::operator=(std::shared_ptr<Microsoft::Bluetooth::Foundation::AsyncDeviceInterfaceWatcher> &&)
0x1800498e6  mov     rcx, [rbp+57h+var_58]; this
0x1800498ea  test    rcx, rcx
0x1800498ed  jz      short loc_1800498F4
0x1800498ef  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800498f4  movups  xmm0, xmmword ptr [rbp+57h+var_40]
0x1800498f8  movdqu  xmmword ptr [rdi+0B8h], xmm0
0x180049900  lea     rcx, [rbp+57h+var_50]
0x180049904  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180049909  mov     rcx, rdi; this
0x18004990c  call    ?StartEventRead@AvrcpTransportAdapter@Details@Avrcp@Profiles@Bluetooth@Microsoft@@AEAAXXZ; Microsoft::Bluetooth::Profiles::Avrcp::Details::AvrcpTransportAdapter::StartEventRead(void)
0x180049911  mov     edx, 1; enum ChannelType
0x180049916  mov     rcx, rdi; this
0x180049919  call    ?ReadCurrentChannelState@AvrcpTransportAdapter@Details@Avrcp@Profiles@Bluetooth@Microsoft@@AEAAXW4ChannelType@AvrcpTransport@3456@@Z; Microsoft::Bluetooth::Profiles::Avrcp::Details::AvrcpTransportAdapter::ReadCurrentChannelState(Microsoft::Bluetooth::Profiles::Avrcp::AvrcpTransport::ChannelType)
0x18004991e  xor     edx, edx; enum ChannelType
0x180049920  mov     rcx, rdi; this
0x180049923  call    ?ReadCurrentChannelState@AvrcpTransportAdapter@Details@Avrcp@Profiles@Bluetooth@Microsoft@@AEAAXW4ChannelType@AvrcpTransport@3456@@Z; Microsoft::Bluetooth::Profiles::Avrcp::Details::AvrcpTransportAdapter::ReadCurrentChannelState(Microsoft::Bluetooth::Profiles::Avrcp::AvrcpTransport::ChannelType)
0x180049928  lea     rcx, [rdi+8]
0x18004992c  lea     rdx, [rbp+57h+var_60]
0x180049930  call    ?shared_from_this@?$enable_shared_from_this@VAsyncDeviceInterfaceWatcherImpl@Details@Foundation@Bluetooth@Microsoft@@@std@@QEAA?AV?$shared_ptr@VAsyncDeviceInterfaceWatcherImpl@Details@Foundation@Bluetooth@Microsoft@@@2@XZ; std::enable_shared_from_this<Microsoft::Bluetooth::Foundation::Details::AsyncDeviceInterfaceWatcherImpl>::shared_from_this(void)
0x180049935  mov     rbx, rax
0x180049938  mov     ecx, 48h ; 'H'; Size
0x18004993d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180049942  mov     [rbp+57h+var_70], rax
0x180049946  mov     rcx, [rbx]
0x180049949  mov     [rbp+57h+var_70], rcx
0x18004994d  mov     rcx, [rbx+8]
0x180049951  mov     [rbp+57h+var_68], rcx
0x180049955  mov     qword ptr [rbx], 0
0x18004995c  mov     qword ptr [rbx+8], 0
0x180049964  lea     r9, [rbp+57h+var_70]
0x180049968  lea     r8, [rbp+57h+var_40]
0x18004996c  mov     edx, 1
0x180049971  mov     rcx, rax
0x180049974  call    ??0EventRegistration@EventNotifier@Foundation@Bluetooth@Microsoft@@QEAA@IAEBU_GUID@@V?$shared_ptr@VEventNotifier@Foundation@Bluetooth@Microsoft@@@std@@@Z; Microsoft::Bluetooth::Foundation::EventNotifier::EventRegistration::EventRegistration(uint,_GUID const &,std::shared_ptr<Microsoft::Bluetooth::Foundation::EventNotifier>)
0x180049979  mov     [r14], rax
0x18004997c  mov     rcx, [rbp+57h+var_58]; this
0x180049980  test    rcx, rcx
0x180049983  jz      short loc_18004998B
0x180049985  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18004998a  nop
0x18004998b  mov     rcx, [rsi+8]; this
0x18004998f  test    rcx, rcx
0x180049992  jz      short loc_180049999
0x180049994  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180049999  mov     rax, r14
0x18004999c  mov     rcx, [rbp+57h+var_30]
0x1800499a0  xor     rcx, rsp; StackCookie
0x1800499a3  call    __security_check_cookie
0x1800499a8  add     rsp, 0B0h
0x1800499af  pop     r14
0x1800499b1  pop     rdi
0x1800499b2  pop     rsi
0x1800499b3  pop     rbx
0x1800499b4  pop     rbp
0x1800499b5  retn
```
