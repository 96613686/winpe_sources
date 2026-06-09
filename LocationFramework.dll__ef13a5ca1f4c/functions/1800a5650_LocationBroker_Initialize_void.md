# LocationBroker::Initialize(void)

- ea: `0x1800a5650`
- end: `0x1800a5884`
- name: `?Initialize@LocationBroker@@UEAAJXZ`
- size: `564`
- prototype: `__int64 __fastcall(LocationBroker *__hidden this)`
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000c974`
- `0x180012194`
- `0x1800123c0`
- `0x180021450`
- `0x1800234ec`
- `0x1800244ac`
- `0x1800261a4`
- `0x180028434`
- `0x18003b360`
- `0x18003b92c`
- `0x18008fbe0`
- `0x180094610`
- `0x1800a5650`
- `0x1800a588c`
- `0x1800a594c`
- `0x1800a98c0`

## import_xrefs

- `BrokerLib!BrInitializeBrokerInstance2` at `0x1800a5720`
- `BrokerLib!BrInitializeBrokerInstance2` at `0x1800a5720`
- `BrokerLib!BrCreateBrokerInstance2` at `0x1800a56c6`
- `BrokerLib!BrCreateBrokerInstance2` at `0x1800a56c6`

## string_xrefs

- `0x1800a56eb`: `onecoreuap\drivers\mobilepc\location\product\core\systemintegration\locationbroker.cpp`
- `0x1800a5745`: `onecoreuap\drivers\mobilepc\location\product\core\systemintegration\locationbroker.cpp`
- `0x1800a5732`: `BrInitializeBrokerInstance2(m_pBrokerInstance.get(), nullptr, nullptr)`
- `0x1800a56e4`: `LocationBroker::Initialize`
- `0x1800a573e`: `LocationBroker::Initialize`
- `0x1800a56d8`: `BrCreateBrokerInstance2( &BrokerCallbackTable, &c_locationBrokerGuid2, BrokerEventTypeCount, &BrokerLimits, &m_pBrokerInstance)`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall LocationBroker::Initialize(LocationBroker *this)
{
  int BrokerInstance2; // eax
  unsigned int v3; // ebx
  int v5; // eax
  __int64 v6; // rax
  wil::details *v7; // [rsp+28h] [rbp-71h]
  unsigned int v8; // [rsp+30h] [rbp-69h]
  LocationBroker *v9; // [rsp+40h] [rbp-59h] BYREF
  void ***v10; // [rsp+48h] [rbp-51h] BYREF
  std::_Ref_count_base *v11; // [rsp+50h] [rbp-49h]
  _BYTE v12[16]; // [rsp+58h] [rbp-41h] BYREF
  std::_Ref_count_base *v13[2]; // [rsp+68h] [rbp-31h] BYREF
  void **v14; // [rsp+78h] [rbp-21h] BYREF
  __int128 v15; // [rsp+80h] [rbp-19h]
  char v16; // [rsp+90h] [rbp-9h]
  char v17; // [rsp+91h] [rbp-8h]
  char v18; // [rsp+92h] [rbp-7h]
  char v19; // [rsp+93h] [rbp-6h]
  __int64 v20; // [rsp+98h] [rbp-1h]
  void ***v21; // [rsp+B0h] [rbp+17h]
  LocationBroker *v22; // [rsp+B8h] [rbp+1Fh]
  __int64 v23; // [rsp+C0h] [rbp+27h]
  __int128 v24; // [rsp+C8h] [rbp+2Fh] BYREF
  char v25; // [rsp+D8h] [rbp+3Fh]
  char v26; // [rsp+D9h] [rbp+40h]
  char v27; // [rsp+DAh] [rbp+41h]
  char v28; // [rsp+DBh] [rbp+42h]
  __int64 v29; // [rsp+E0h] [rbp+47h]
  wil::details::in1diag5 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v23 = 1;
  v22 = this;
  ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(
    v12,
    (char *)this + 24);
  wil::details::unique_storage<wil::details::resource_policy<_BROKER *,unsigned long (*)(_BROKER *),&unsigned long BrDeleteBrokerInstance(_BROKER *),wistd::integral_constant<unsigned __int64,0>,_BROKER *,_BROKER *,0,std::nullptr_t>>::reset(
    (char *)this + 240,
    0);
  BrokerInstance2 = BrCreateBrokerInstance2(
                      &LocationBroker::BrokerCallbackTable,
                      &c_locationBrokerGuid2,
                      1,
                      &qword_1801A64B0,
                      (char *)this + 240);
  if ( BrokerInstance2 )
  {
    LODWORD(v7) = BrokerInstance2;
    v3 = wil::details::in1diag5::Return_Win32(
           retaddr,
           (void *)0x25,
           (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\systemintegration\\locationbroker.cpp",
           "LocationBroker::Initialize",
           "BrCreateBrokerInstance2( &BrokerCallbackTable, &c_locationBrokerGuid2, BrokerEventTypeCount, &BrokerLimits, &"
           "m_pBrokerInstance)",
           v7,
           v8);
    ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(v12);
    LocationBroker::Uninitialize(this);
    return v3;
  }
  v5 = BrInitializeBrokerInstance2(*((_QWORD *)this + 30), 0, 0);
  if ( v5 )
  {
    LODWORD(v7) = v5;
    v3 = wil::details::in1diag5::Return_Win32(
           retaddr,
           (void *)0x27,
           (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\systemintegration\\locationbroker.cpp",
           "LocationBroker::Initialize",
           "BrInitializeBrokerInstance2(m_pBrokerInstance.get(), nullptr, nullptr)",
           v7,
           v8);
    ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(v12);
    LocationBroker::Uninitialize(this);
    return v3;
  }
  *(_OWORD *)v13 = 0;
  v6 = std::enable_shared_from_this<LocationSignalManager>::shared_from_this((char *)this + 8, &v10);
  std::weak_ptr<SignalValue<bool>::SignalState>::weak_ptr<SignalValue<bool>::SignalState>(v13, v6);
  if ( v11 )
    std::_Ref_count_base::_Decref(v11);
  v9 = this;
  v10 = (void ***)LocationBroker::SignalTrigger;
  LODWORD(v11) = 0;
  HIDWORD(v11) = HIDWORD(v13[1]);
  std::bind<void (LocationBroker::*)(_BROKERED_EVENT *,_GUID const *,unsigned long,unsigned char *),LocationBroker *,std::_Ph<1> const &,std::_Ph<2> const &,std::_Ph<3> const &,std::_Ph<4> const &>(
    &v24,
    &v10,
    &v9);
  v14 = &std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,void (LocationBroker::*)(_BROKERED_EVENT *,_GUID const *,unsigned long,unsigned char *),LocationBroker *,std::_Ph<1> const &,std::_Ph<2> const &,std::_Ph<3> const &,std::_Ph<4> const &>,void,_BROKERED_EVENT *,_GUID const *,unsigned long,unsigned char *>::`vftable';
  v15 = v24;
  v16 = v25;
  v17 = v26;
  v18 = v27;
  v19 = v28;
  v20 = v29;
  v21 = &v14;
  v10 = &v14;
  v9 = 0;
  wil::EnterCriticalSection(&v9, (char *)this + 136);
  std::function<void (_BROKERED_EVENT *,_GUID const *,unsigned long,unsigned char *)>::operator=(
    (char *)this + 72,
    &v14);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(&v9);
  std::_Func_class<void,enum CLocationActivityDetector::ActivityType,bool>::_Tidy(&v14);
  if ( v13[1] )
    std::_Ref_count_base::_Decwref(v13[1]);
  ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(v12);
  return 0;
}

```

## disassembly

```asm
0x1800a5650  mov     [rsp-8+arg_8], rbx
0x1800a5655  mov     [rsp-8+arg_10], rdi
0x1800a565a  push    rbp
0x1800a565b  lea     rbp, [rsp-57h]
0x1800a5660  sub     rsp, 0F0h
0x1800a5667  mov     rax, cs:__security_cookie
0x1800a566e  xor     rax, rsp
0x1800a5671  mov     [rbp+57h+var_8], rax
0x1800a5675  mov     rdi, rcx
0x1800a5678  xorps   xmm0, xmm0
0x1800a567b  movups  [rbp+57h+var_38], xmm0
0x1800a567f  mov     qword ptr [rbp+57h+var_38], rcx
0x1800a5683  mov     byte ptr [rbp+57h+var_38+8], 1
0x1800a5687  lea     rdx, [rcx+18h]
0x1800a568b  lea     rcx, [rbp+57h+var_98]
0x1800a568f  call    ??0?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@AEAVCComAutoCriticalSection@1@_N@Z; ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(ATL::CComAutoCriticalSection &,bool)
0x1800a5694  nop
0x1800a5695  lea     rbx, [rdi+0F0h]
0x1800a569c  xor     edx, edx
0x1800a569e  mov     rcx, rbx
0x1800a56a1  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_BROKER@@P6AKPEAU1@@Z$1?BrDeleteBrokerInstance@@YAK0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_BROKER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_BROKER *,ulong (*)(_BROKER *),&BrDeleteBrokerInstance(_BROKER *),wistd::integral_constant<unsigned __int64,0>,_BROKER *,_BROKER *,0,std::nullptr_t>>::reset(_BROKER *)
0x1800a56a6  mov     [rsp+0F0h+var_D0], rbx
0x1800a56ab  lea     r9, qword_1801A64B0
0x1800a56b2  mov     r8d, 1
0x1800a56b8  lea     rdx, ?c_locationBrokerGuid2@@3U_GUID@@B; _GUID const c_locationBrokerGuid2
0x1800a56bf  lea     rcx, ?BrokerCallbackTable@LocationBroker@@0U_BROKER_CALLBACK_TABLE_V2@@A; _BROKER_CALLBACK_TABLE_V2 LocationBroker::BrokerCallbackTable
0x1800a56c6  call    cs:__imp_BrCreateBrokerInstance2
0x1800a56cc  test    eax, eax
0x1800a56ce  jz      short loc_1800A5718
0x1800a56d0  mov     rcx, [rbp+5Fh]; this
0x1800a56d4  mov     dword ptr [rsp+0F0h+var_C8], eax; wil::details *
0x1800a56d8  lea     rax, aBrcreatebroker_0; "BrCreateBrokerInstance2( &BrokerCallbac"...
0x1800a56df  mov     [rsp+0F0h+var_D0], rax; char *
0x1800a56e4  lea     r9, aLocationbroker; "LocationBroker::Initialize"
0x1800a56eb  lea     r8, aOnecoreuapDriv_76; "onecoreuap\\drivers\\mobilepc\\location"...
0x1800a56f2  mov     edx, 25h ; '%'; void *
0x1800a56f7  call    ?Return_Win32@in1diag5@details@wil@@YAJPEAXIPEBD11K@Z; wil::details::in1diag5::Return_Win32(void *,uint,char const *,char const *,char const *,ulong)
0x1800a56fc  mov     ebx, eax
0x1800a56fe  lea     rcx, [rbp+57h+var_98]
0x1800a5702  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x1800a5707  nop
0x1800a5708  mov     rcx, rdi; this
0x1800a570b  call    ?Uninitialize@LocationBroker@@AEAAXXZ; LocationBroker::Uninitialize(void)
0x1800a5710  nop
0x1800a5711  mov     eax, ebx
0x1800a5713  jmp     loc_1800A5863
0x1800a5718  xor     r8d, r8d
0x1800a571b  xor     edx, edx
0x1800a571d  mov     rcx, [rbx]
0x1800a5720  call    cs:__imp_BrInitializeBrokerInstance2
0x1800a5726  test    eax, eax
0x1800a5728  jz      short loc_1800A576D
0x1800a572a  mov     rcx, [rbp+5Fh]; this
0x1800a572e  mov     dword ptr [rsp+0F0h+var_C8], eax; wil::details *
0x1800a5732  lea     rax, aBrinitializebr_1; "BrInitializeBrokerInstance2(m_pBrokerIn"...
0x1800a5739  mov     [rsp+0F0h+var_D0], rax; char *
0x1800a573e  lea     r9, aLocationbroker; "LocationBroker::Initialize"
0x1800a5745  lea     r8, aOnecoreuapDriv_76; "onecoreuap\\drivers\\mobilepc\\location"...
0x1800a574c  mov     edx, 27h ; '''; void *
0x1800a5751  call    ?Return_Win32@in1diag5@details@wil@@YAJPEAXIPEBD11K@Z; wil::details::in1diag5::Return_Win32(void *,uint,char const *,char const *,char const *,ulong)
0x1800a5756  mov     ebx, eax
0x1800a5758  lea     rcx, [rbp+57h+var_98]
0x1800a575c  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x1800a5761  nop
0x1800a5762  mov     rcx, rdi; this
0x1800a5765  call    ?Uninitialize@LocationBroker@@AEAAXXZ; LocationBroker::Uninitialize(void)
0x1800a576a  nop
0x1800a576b  jmp     short loc_1800A5711
0x1800a576d  xorps   xmm0, xmm0
0x1800a5770  movups  xmmword ptr [rbp+57h+var_88], xmm0
0x1800a5774  lea     rcx, [rdi+8]
0x1800a5778  lea     rdx, [rbp+57h+var_A8]
0x1800a577c  call    ?shared_from_this@?$enable_shared_from_this@VLocationSignalManager@@@std@@QEAA?AV?$shared_ptr@VLocationSignalManager@@@2@XZ; std::enable_shared_from_this<LocationSignalManager>::shared_from_this(void)
0x1800a5781  mov     rdx, rax
0x1800a5784  lea     rcx, [rbp+57h+var_88]
0x1800a5788  call    ??0?$weak_ptr@USignalState@?$SignalValue@_N@@@std@@QEAA@AEBV01@@Z; std::weak_ptr<SignalValue<bool>::SignalState>::weak_ptr<SignalValue<bool>::SignalState>(std::weak_ptr<SignalValue<bool>::SignalState> const &)
0x1800a578d  nop
0x1800a578e  mov     rcx, [rbp+57h+var_A0]; this
0x1800a5792  test    rcx, rcx
0x1800a5795  jz      short loc_1800A579C
0x1800a5797  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800a579c  mov     [rbp+57h+var_B0], rdi
0x1800a57a0  lea     rax, ?SignalTrigger@LocationBroker@@AEAAXPEAU_BROKERED_EVENT@@PEBU_GUID@@KPEAE@Z; LocationBroker::SignalTrigger(_BROKERED_EVENT *,_GUID const *,ulong,uchar *)
0x1800a57a7  mov     [rbp+57h+var_A8], rax
0x1800a57ab  mov     dword ptr [rbp+57h+var_A0], 0
0x1800a57b2  mov     eax, dword ptr [rbp+57h+var_88+0Ch]
0x1800a57b5  mov     dword ptr [rbp+57h+var_A0+4], eax
0x1800a57b8  lea     r8, [rbp+57h+var_B0]
0x1800a57bc  lea     rdx, [rbp+57h+var_A8]
0x1800a57c0  lea     rcx, [rbp+57h+var_28]
0x1800a57c4  call    ??$bind@P8LocationBroker@@EAAXPEAU_BROKERED_EVENT@@PEBU_GUID@@KPEAE@ZPEAV1@AEBU?$_Ph@$00@std@@AEBU?$_Ph@$01@5@AEBU?$_Ph@$02@5@AEBU?$_Ph@$03@5@@std@@YA?AV?$_Binder@U_Unforced@std@@P8LocationBroker@@EAAXPEAU_BROKERED_EVENT@@PEBU_GUID@@KPEAE@ZPEAV3@AEBU?$_Ph@$00@2@AEBU?$_Ph@$01@2@AEBU?$_Ph@$02@2@AEBU?$_Ph@$03@2@@0@$$QEAP8LocationBroker@@EAAXPEAU_BROKERED_EVENT@@PEBU_GUID@@KPEAE@Z$$QEAPEAV2@AEBU?$_Ph@$00@0@AEBU?$_Ph@$01@0@AEBU?$_Ph@$02@0@AEBU?$_Ph@$03@0@@Z; std::bind<void (LocationBroker::*)(_BROKERED_EVENT *,_GUID const *,ulong,uchar *),LocationBroker *,std::_Ph<1> const &,std::_Ph<2> const &,std::_Ph<3> const &,std::_Ph<4> const &>(void (LocationBroker::*&&)(_BROKERED_EVENT *,_GUID const *,ulong,uchar *),LocationBroker * &&,std::_Ph<1> const &,std::_Ph<2> const &,std::_Ph<3> const &,std::_Ph<4> const &)
0x1800a57c9  lea     rax, ??_7?$_Func_impl_no_alloc@V?$_Binder@U_Unforced@std@@P8LocationBroker@@EAAXPEAU_BROKERED_EVENT@@PEBU_GUID@@KPEAE@ZPEAV3@AEBU?$_Ph@$00@2@AEBU?$_Ph@$01@2@AEBU?$_Ph@$02@2@AEBU?$_Ph@$03@2@@std@@XPEAU_BROKERED_EVENT@@PEBU_GUID@@KPEAE@std@@6B@; const std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,void (LocationBroker::*)(_BROKERED_EVENT *,_GUID const *,ulong,uchar *),LocationBroker *,std::_Ph<1> const &,std::_Ph<2> const &,std::_Ph<3> const &,std::_Ph<4> const &>,void,_BROKERED_EVENT *,_GUID const *,ulong,uchar *>::`vftable'
0x1800a57d0  mov     [rbp+57h+var_78], rax
0x1800a57d4  movups  xmm0, [rbp+57h+var_28]
0x1800a57d8  movdqu  [rbp+57h+var_70], xmm0
0x1800a57dd  mov     al, [rbp+57h+var_18]
0x1800a57e0  mov     [rbp+57h+var_60], al
0x1800a57e3  mov     al, [rbp+57h+var_17]
0x1800a57e6  mov     [rbp+57h+var_5F], al
0x1800a57e9  mov     al, [rbp+57h+var_16]
0x1800a57ec  mov     [rbp+57h+var_5E], al
0x1800a57ef  mov     al, [rbp+57h+var_15]
0x1800a57f2  mov     [rbp+57h+var_5D], al
0x1800a57f5  mov     rax, [rbp+57h+var_10]
0x1800a57f9  mov     [rbp+57h+var_58], rax
0x1800a57fd  lea     rax, [rbp+57h+var_78]
0x1800a5801  mov     [rbp+57h+var_40], rax
0x1800a5805  lea     rax, [rbp+57h+var_78]
0x1800a5809  mov     [rbp+57h+var_A8], rax
0x1800a580d  mov     [rbp+57h+var_B0], 0
0x1800a5815  lea     rdx, [rdi+88h]
0x1800a581c  lea     rcx, [rbp+57h+var_B0]
0x1800a5820  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x1800a5825  nop
0x1800a5826  lea     rcx, [rdi+48h]
0x1800a582a  lea     rdx, [rbp+57h+var_78]
0x1800a582e  call    ??4?$function@$$A6AXPEAU_BROKERED_EVENT@@PEBU_GUID@@KPEAE@Z@std@@QEAAAEAV01@AEBV01@@Z; std::function<void (_BROKERED_EVENT *,_GUID const *,ulong,uchar *)>::operator=(std::function<void (_BROKERED_EVENT *,_GUID const *,ulong,uchar *)> const &)
0x1800a5833  nop
0x1800a5834  lea     rcx, [rbp+57h+var_B0]
0x1800a5838  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x1800a583d  nop
0x1800a583e  lea     rcx, [rbp+57h+var_78]
0x1800a5842  call    ?_Tidy@?$_Func_class@XW4ActivityType@CLocationActivityDetector@@_N@std@@IEAAXXZ; std::_Func_class<void,CLocationActivityDetector::ActivityType,bool>::_Tidy(void)
0x1800a5847  nop
0x1800a5848  mov     rcx, [rbp+57h+var_88+8]; this
0x1800a584c  test    rcx, rcx
0x1800a584f  jz      short loc_1800A5857
0x1800a5851  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x1800a5856  nop
0x1800a5857  lea     rcx, [rbp+57h+var_98]
0x1800a585b  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x1800a5860  nop
0x1800a5861  xor     eax, eax
0x1800a5863  mov     rcx, [rbp+57h+var_8]
0x1800a5867  xor     rcx, rsp; StackCookie
0x1800a586a  call    __security_check_cookie
0x1800a586f  lea     r11, [rsp+0F0h+var_s0]
0x1800a5877  mov     rbx, [r11+18h]
0x1800a587b  mov     rdi, [r11+20h]
0x1800a587f  mov     rsp, r11
0x1800a5882  pop     rbp
0x1800a5883  retn
```
