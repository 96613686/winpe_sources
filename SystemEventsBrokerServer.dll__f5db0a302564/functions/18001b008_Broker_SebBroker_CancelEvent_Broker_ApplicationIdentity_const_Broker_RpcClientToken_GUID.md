# Broker::SebBroker::CancelEvent(Broker::ApplicationIdentity const &,Broker::RpcClientToken *,_GUID &)

- ea: `0x18001b008`
- end: `0x18001b1eb`
- name: `?CancelEvent@SebBroker@Broker@@QEAAXAEBUApplicationIdentity@2@PEAVRpcClientToken@2@AEAU_GUID@@@Z`
- size: `483`
- prototype: `void __fastcall(struct _BROKER **this, const struct Broker::ApplicationIdentity *, struct Broker::RpcClientToken *, struct _GUID *)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x18001aee0`

## callees

- `0x18000142c`
- `0x180001b50`
- `0x180001b78`
- `0x180001dc0`
- `0x180001e40`
- `0x1800076a0`
- `0x18000e770`
- `0x180011574`
- `0x180017ca4`
- `0x18001ab0c`
- `0x18001b008`
- `0x18001d9ac`

## import_xrefs

- `BrokerLib!BrGetBrokeredEventInfo2` at `0x18001b0b3`
- `BrokerLib!BrGetBrokeredEventInfo2` at `0x18001b0b3`
- `BrokerLib!BrSendActivatorControl` at `0x18001b13f`
- `BrokerLib!BrSendActivatorControl` at `0x18001b13f`
- `BrokerLib!BrFindBrokeredEvent` at `0x18001b080`
- `BrokerLib!BrFindBrokeredEvent` at `0x18001b080`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Broker::SebBroker::CancelEvent(
        struct _BROKER **this,
        const struct Broker::ApplicationIdentity *a2,
        struct Broker::RpcClientToken *a3,
        struct _GUID *a4)
{
  int BrokeredEvent; // ebx
  __int64 v9; // r8
  std::_Ref_count_base *v10; // rbx
  Broker::ApplicationIdentity *v11; // rax
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v15; // [rsp+40h] [rbp-89h] BYREF
  _QWORD *v16; // [rsp+48h] [rbp-81h] BYREF
  __int128 v17; // [rsp+50h] [rbp-79h] BYREF
  std::_Ref_count_base *v18[2]; // [rsp+60h] [rbp-69h] BYREF
  _BYTE v19[16]; // [rsp+70h] [rbp-59h] BYREF
  _BYTE pExceptionObject[40]; // [rsp+80h] [rbp-49h] BYREF
  _BYTE v21[120]; // [rsp+A8h] [rbp-21h] BYREF
  int v22; // [rsp+130h] [rbp+67h] BYREF
  int v23; // [rsp+148h] [rbp+7Fh] BYREF

  v15 = 0;
  v16 = 0;
  *(_OWORD *)v18 = 0;
  Broker::BrokerLock::BrokerLock((Broker::BrokerLock *)v19, this[17], 1);
  v17 = (__int128)*a4;
  BrokeredEvent = BrFindBrokeredEvent(this[17], &v17, 0, 0, &v15);
  if ( BrokeredEvent )
  {
    v9 = 10;
    goto LABEL_14;
  }
  BrokeredEvent = BrGetBrokeredEventInfo2(this[17], v15, 0, 0, &v16);
  if ( BrokeredEvent )
  {
    v9 = 20;
    goto LABEL_14;
  }
  std::shared_ptr<std::map<unsigned long,std::shared_ptr<Broker::_SessionInfo>>>::operator=(v18, v16);
  v10 = v18[0];
  if ( !(unsigned __int8)Broker::SebEvent::IsSyncEvent(*((unsigned int *)v18[0] + 24)) )
  {
    BrokeredEvent = 87;
    v9 = 30;
    goto LABEL_14;
  }
  v11 = Broker::ApplicationIdentity::ApplicationIdentity((Broker::ApplicationIdentity *)v21, a2);
  if ( !Broker::SebEvent::CheckSignalPermissions((__int64)v10, (__int64)v11, a3) )
  {
    BrokeredEvent = 5;
    v9 = 40;
    goto LABEL_14;
  }
  v22 = 0;
  BrokeredEvent = BrSendActivatorControl(*(_QWORD *)(*((_QWORD *)v10 + 24) + 136LL), *((_QWORD *)v10 + 28), &v22);
  if ( BrokeredEvent )
  {
    v9 = 50;
LABEL_14:
    if ( (unsigned int)dword_180035050 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_180035050, 0, v9) )
      {
        v22 = v13;
        v23 = BrokeredEvent;
        *(_QWORD *)&v17 = a4;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v12,
          (__int64)byte_18002DDE9,
          v13,
          v14,
          &v17,
          (__int64)&v23,
          (__int64)&v22);
      }
    }
    Broker::Win32Error::Win32Error((Broker::Win32Error *)pExceptionObject, BrokeredEvent);
    throw (Broker::Win32Error *)pExceptionObject;
  }
  Broker::BrokerLock::~BrokerLock((Broker::BrokerLock *)v19);
  if ( v18[1] )
    std::_Ref_count_base::_Decref(v18[1]);
}

```

## disassembly

```asm
0x18001b008  mov     [rsp-8+arg_8], rbx
0x18001b00d  push    rbp
0x18001b00e  push    rsi
0x18001b00f  push    rdi
0x18001b010  push    r14
0x18001b012  push    r15
0x18001b014  lea     rbp, [rsp-37h]
0x18001b019  sub     rsp, 100h
0x18001b020  mov     rsi, r9
0x18001b023  mov     r14, r8
0x18001b026  mov     r15, rdx
0x18001b029  mov     rdi, rcx
0x18001b02c  mov     [rsp+120h+var_E0], 0
0x18001b035  mov     [rsp+120h+var_D8], 0
0x18001b03e  xorps   xmm0, xmm0
0x18001b041  movdqu  xmmword ptr [rbp+57h+var_C0], xmm0
0x18001b046  mov     r8d, 1; int
0x18001b04c  mov     rdx, [rcx+88h]; struct _BROKER *
0x18001b053  lea     rcx, [rbp+57h+var_B0]; this
0x18001b057  call    ??0BrokerLock@Broker@@QEAA@PEAU_BROKER@@HH@Z; Broker::BrokerLock::BrokerLock(_BROKER *,int,int)
0x18001b05c  nop
0x18001b05d  movups  xmm0, xmmword ptr [rsi]
0x18001b060  movdqu  [rbp+57h+var_D0], xmm0
0x18001b065  lea     rax, [rsp+120h+var_E0]
0x18001b06a  mov     [rsp+120h+var_100], rax
0x18001b06f  xor     r9d, r9d
0x18001b072  xor     r8d, r8d
0x18001b075  lea     rdx, [rbp+57h+var_D0]
0x18001b079  mov     rcx, [rdi+88h]
0x18001b080  call    cs:__imp_BrFindBrokeredEvent
0x18001b086  mov     ebx, eax
0x18001b088  test    eax, eax
0x18001b08a  jz      short loc_18001B097
0x18001b08c  mov     r8d, 0Ah
0x18001b092  jmp     loc_18001B180
0x18001b097  lea     rax, [rsp+120h+var_D8]
0x18001b09c  mov     [rsp+120h+var_100], rax
0x18001b0a1  xor     r9d, r9d
0x18001b0a4  xor     r8d, r8d
0x18001b0a7  mov     rdx, [rsp+120h+var_E0]
0x18001b0ac  mov     rcx, [rdi+88h]
0x18001b0b3  call    cs:__imp_BrGetBrokeredEventInfo2
0x18001b0b9  mov     ebx, eax
0x18001b0bb  test    eax, eax
0x18001b0bd  jz      short loc_18001B0CA
0x18001b0bf  mov     r8d, 14h
0x18001b0c5  jmp     loc_18001B180
0x18001b0ca  mov     rdx, [rsp+120h+var_D8]
0x18001b0cf  lea     rcx, [rbp+57h+var_C0]
0x18001b0d3  call    ??4?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>::operator=(std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>> const &)
0x18001b0d8  mov     rbx, [rbp+57h+var_C0]
0x18001b0dc  mov     ecx, [rbx+60h]
0x18001b0df  call    ?IsSyncEvent@SebEvent@Broker@@SA_NW4_SebiEventType@@@Z; Broker::SebEvent::IsSyncEvent(_SebiEventType)
0x18001b0e4  test    al, al
0x18001b0e6  jnz     short loc_18001B0F6
0x18001b0e8  mov     ebx, 57h ; 'W'
0x18001b0ed  lea     r8d, [rbx-39h]
0x18001b0f1  jmp     loc_18001B180
0x18001b0f6  mov     rdx, r15; struct Broker::ApplicationIdentity *
0x18001b0f9  lea     rcx, [rbp+57h+var_78]; this
0x18001b0fd  call    ??0ApplicationIdentity@Broker@@QEAA@AEBU01@@Z; Broker::ApplicationIdentity::ApplicationIdentity(Broker::ApplicationIdentity const &)
0x18001b102  mov     r8, r14
0x18001b105  mov     rdx, rax
0x18001b108  mov     rcx, rbx
0x18001b10b  call    ?CheckSignalPermissions@SebEvent@Broker@@QEAA_NUApplicationIdentity@2@PEAVRpcClientToken@2@@Z; Broker::SebEvent::CheckSignalPermissions(Broker::ApplicationIdentity,Broker::RpcClientToken *)
0x18001b110  test    al, al
0x18001b112  jnz     short loc_18001B11F
0x18001b114  mov     ebx, 5
0x18001b119  lea     r8d, [rbx+23h]
0x18001b11d  jmp     short loc_18001B180
0x18001b11f  mov     [rbp+57h+arg_0], 0
0x18001b126  mov     rcx, [rbx+0C0h]
0x18001b12d  lea     r8, [rbp+57h+arg_0]
0x18001b131  mov     rdx, [rbx+0E0h]
0x18001b138  mov     rcx, [rcx+88h]
0x18001b13f  call    cs:__imp_BrSendActivatorControl
0x18001b145  mov     ebx, eax
0x18001b147  test    eax, eax
0x18001b149  jnz     short loc_18001B17A
0x18001b14b  lea     rcx, [rbp+57h+var_B0]; this
0x18001b14f  call    ??1BrokerLock@Broker@@QEAA@XZ; Broker::BrokerLock::~BrokerLock(void)
0x18001b154  nop
0x18001b155  mov     rcx, [rbp+57h+var_C0+8]; this
0x18001b159  test    rcx, rcx
0x18001b15c  jz      short loc_18001B163
0x18001b15e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001b163  mov     rbx, [rsp+120h+arg_8]
0x18001b16b  add     rsp, 100h
0x18001b172  pop     r15
0x18001b174  pop     r14
0x18001b176  pop     rdi
0x18001b177  pop     rsi
0x18001b178  pop     rbp
0x18001b179  retn
0x18001b17a  mov     r8d, 32h ; '2'
0x18001b180  mov     eax, cs:dword_180035050
0x18001b186  cmp     eax, 5
0x18001b189  jbe     short loc_18001B1CF
0x18001b18b  xor     edx, edx
0x18001b18d  lea     rcx, dword_180035050
0x18001b194  call    _tlgKeywordOn
0x18001b199  test    al, al
0x18001b19b  jz      short loc_18001B1CF
0x18001b19d  mov     [rbp+57h+arg_0], r8d
0x18001b1a1  mov     [rbp+57h+arg_18], ebx
0x18001b1a4  mov     qword ptr [rbp+57h+var_D0], rsi
0x18001b1a8  lea     rax, [rbp+57h+arg_0]
0x18001b1ac  mov     [rsp+120h+var_F0], rax
0x18001b1b1  lea     rax, [rbp+57h+arg_18]
0x18001b1b5  mov     [rsp+120h+var_F8], rax
0x18001b1ba  lea     rax, [rbp+57h+var_D0]
0x18001b1be  mov     [rsp+120h+var_100], rax
0x18001b1c3  lea     rdx, byte_18002DDE9
0x18001b1ca  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001b1cf  mov     edx, ebx; unsigned int
0x18001b1d1  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18001b1d5  call    ??0Win32Error@Broker@@QEAA@K@Z; Broker::Win32Error::Win32Error(ulong)
0x18001b1da  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x18001b1e1  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18001b1e5  call    _CxxThrowException_0
```
