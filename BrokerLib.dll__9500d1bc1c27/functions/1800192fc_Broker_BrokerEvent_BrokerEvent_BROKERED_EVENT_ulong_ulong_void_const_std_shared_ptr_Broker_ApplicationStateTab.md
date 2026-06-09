# Broker::BrokerEvent::BrokerEvent(_BROKERED_EVENT *,ulong,ulong,void * const,std::shared_ptr<Broker::ApplicationStateTable::State>,uchar,_WNF_STATE_NAME *,Broker::BrokerBase *)

- ea: `0x1800192fc`
- end: `0x18001944d`
- name: `??0BrokerEvent@Broker@@QEAA@PEAU_BROKERED_EVENT@@KKQEAXV?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@EPEAU_WNF_STATE_NAME@@PEAVBrokerBase@1@@Z`
- size: `337`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800171e4`

## callees

- `0x180004500`
- `0x180004ae0`
- `0x18000bc2c`
- `0x18000ed78`
- `0x18001184c`
- `0x1800119f4`
- `0x1800126e0`
- `0x1800165da`
- `0x1800192fc`

## import_xrefs

- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180019429`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180019429`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Broker::BrokerEvent::BrokerEvent(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        unsigned int a4,
        __int64 a5,
        Broker::ApplicationStateTable::State **a6,
        char a7,
        _QWORD *a8,
        __int64 a9)
{
  Broker::ApplicationStateTable::State **v13; // rdi
  __int64 v14; // rcx
  __int64 v15; // r8
  __int64 v16; // r9
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  void *v20; // r9
  NTSTATUS TemporaryStateName; // eax
  std::_Ref_count_base *v22; // rcx
  ULONG v24; // eax
  _BYTE pExceptionObject[48]; // [rsp+30h] [rbp-48h] BYREF
  unsigned int v26; // [rsp+90h] [rbp+18h] BYREF

  *(_QWORD *)a1 = &Broker::BrokerEvent::`vftable';
  *(_QWORD *)(a1 + 8) = a9;
  *(_QWORD *)(a1 + 16) = a2;
  *(_DWORD *)(a1 + 28) = a3;
  *(_DWORD *)(a1 + 32) = a4;
  *(_QWORD *)(a1 + 40) = a5;
  v13 = a6;
  std::shared_ptr<Broker::BrokerBase>::shared_ptr<Broker::BrokerBase>((_QWORD *)(a1 + 48), a6);
  if ( (unsigned int)dword_180028000 > 4 && (unsigned __int8)tlgKeywordOn(v14, 4, v15, v16) )
  {
    v26 = *(_DWORD *)(a1 + 28);
    a9 = *(_QWORD *)(a1 + 16);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
      v17,
      byte_1800222F3,
      v18,
      v19,
      &a9,
      (__int64)&v26);
  }
  Broker::ApplicationStateTable::State::OnEventCreation(*v13, a3, a4);
  *(_QWORD *)(a1 + 64) = 0;
  *(_DWORD *)(a1 + 24) = 0;
  *(_QWORD *)(a1 + 72) = 0;
  if ( a8 )
    *(_QWORD *)(a1 + 72) = *a8;
  if ( a7 )
  {
    TemporaryStateName = Broker::CreateTemporaryStateName(
                           (Broker *)(a1 + 64),
                           (struct _WNF_STATE_NAME *)4,
                           *(void **)(a2 + 32),
                           v20);
    if ( TemporaryStateName < 0 )
    {
      v24 = RtlNtStatusToDosErrorNoTeb(TemporaryStateName);
      Broker::Win32Error::Win32Error((Broker::Win32Error *)pExceptionObject, v24);
      throw (Broker::Win32Error *)pExceptionObject;
    }
  }
  v22 = v13[1];
  if ( v22 )
    std::_Ref_count_base::_Decref(v22);
  return a1;
}

```

## disassembly

```asm
0x1800192fc  mov     r11, rsp
0x1800192ff  mov     [r11+10h], rbx
0x180019303  mov     [r11+20h], rbp
0x180019307  mov     [r11+8], rcx
0x18001930b  push    rsi
0x18001930c  push    rdi
0x18001930d  push    r14
0x18001930f  sub     rsp, 60h
0x180019313  mov     ebp, r9d
0x180019316  mov     r14d, r8d
0x180019319  mov     rsi, rdx
0x18001931c  mov     rbx, rcx
0x18001931f  lea     rax, ??_7BrokerEvent@Broker@@6B@; const Broker::BrokerEvent::`vftable'
0x180019326  mov     [rcx], rax
0x180019329  mov     rax, [rsp+78h+arg_40]
0x180019331  mov     [rcx+8], rax
0x180019335  mov     [rcx+10h], rdx
0x180019339  mov     [rcx+1Ch], r8d
0x18001933d  mov     [rcx+20h], r9d
0x180019341  mov     rax, [rsp+78h+arg_20]
0x180019349  mov     [rcx+28h], rax
0x18001934d  add     rcx, 30h ; '0'
0x180019351  mov     rdi, [r11+30h]
0x180019355  mov     rdx, rdi
0x180019358  call    ??0?$shared_ptr@VBrokerBase@Broker@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Broker::BrokerBase>::shared_ptr<Broker::BrokerBase>(std::shared_ptr<Broker::BrokerBase> const &)
0x18001935d  nop
0x18001935e  mov     eax, cs:dword_180028000
0x180019364  cmp     eax, 4
0x180019367  jbe     short loc_1800193B3
0x180019369  mov     edx, 4
0x18001936e  call    _tlgKeywordOn
0x180019373  test    al, al
0x180019375  jz      short loc_1800193B3
0x180019377  mov     eax, [rbx+1Ch]
0x18001937a  mov     [rsp+78h+arg_10], eax
0x180019381  mov     rax, [rbx+10h]
0x180019385  mov     [rsp+78h+arg_40], rax
0x18001938d  lea     rax, [rsp+78h+arg_10]
0x180019395  mov     qword ptr [rsp+78h+var_50], rax; unsigned int
0x18001939a  lea     rax, [rsp+78h+arg_40]
0x1800193a2  mov     [rsp+78h+var_58], rax; void *
0x1800193a7  lea     rdx, byte_1800222F3
0x1800193ae  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x1800193b3  mov     r8d, ebp; unsigned int
0x1800193b6  mov     edx, r14d; unsigned int
0x1800193b9  mov     rcx, [rdi]; this
0x1800193bc  call    ?OnEventCreation@State@ApplicationStateTable@Broker@@QEAAXKK@Z; Broker::ApplicationStateTable::State::OnEventCreation(ulong,ulong)
0x1800193c1  lea     rcx, [rbx+40h]; this
0x1800193c5  xor     eax, eax
0x1800193c7  mov     [rcx], rax
0x1800193ca  mov     [rbx+18h], eax
0x1800193cd  mov     [rbx+48h], rax
0x1800193d1  mov     rax, [rsp+78h+arg_38]
0x1800193d9  test    rax, rax
0x1800193dc  jz      short loc_1800193E5
0x1800193de  mov     rax, [rax]
0x1800193e1  mov     [rbx+48h], rax
0x1800193e5  cmp     [rsp+78h+arg_30], 0
0x1800193ed  jz      short loc_180019401
0x1800193ef  mov     r8, [rsi+20h]; unsigned int
0x1800193f3  mov     edx, 4; struct _WNF_STATE_NAME *
0x1800193f8  call    ?CreateTemporaryStateName@Broker@@YAJPEAU_WNF_STATE_NAME@@IPEAX1K@Z; Broker::CreateTemporaryStateName(_WNF_STATE_NAME *,uint,void *,void *,ulong)
0x1800193fd  test    eax, eax
0x1800193ff  js      short loc_180019427
0x180019401  mov     rcx, [rdi+8]; this
0x180019405  test    rcx, rcx
0x180019408  jz      short loc_18001940F
0x18001940a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001940f  mov     rax, rbx
0x180019412  lea     r11, [rsp+78h+var_18]
0x180019417  mov     rbx, [r11+28h]
0x18001941b  mov     rbp, [r11+38h]
0x18001941f  mov     rsp, r11
0x180019422  pop     r14
0x180019424  pop     rdi
0x180019425  pop     rsi
0x180019426  retn
0x180019427  mov     ecx, eax; Status
0x180019429  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18001942f  mov     edx, eax; unsigned int
0x180019431  lea     rcx, [rsp+78h+pExceptionObject]; this
0x180019436  call    ??0Win32Error@Broker@@QEAA@K@Z; Broker::Win32Error::Win32Error(ulong)
0x18001943b  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x180019442  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x180019447  call    _CxxThrowException_0
```
