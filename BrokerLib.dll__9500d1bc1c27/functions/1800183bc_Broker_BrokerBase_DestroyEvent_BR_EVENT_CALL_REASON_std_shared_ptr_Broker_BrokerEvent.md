# Broker::BrokerBase::DestroyEvent(_BR_EVENT_CALL_REASON,std::shared_ptr<Broker::BrokerEvent> &)

- ea: `0x1800183bc`
- end: `0x180018493`
- name: `?DestroyEvent@BrokerBase@Broker@@AEAAXW4_BR_EVENT_CALL_REASON@@AEAV?$shared_ptr@VBrokerEvent@Broker@@@std@@@Z`
- size: `215`
- prototype: ``
- caller_count: `5`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800012cc`
- `0x18000b3cc`
- `0x18000f42c`
- `0x18001854c`
- `0x1800187b8`

## callees

- `0x180001ff8`
- `0x180004500`
- `0x180004840`
- `0x18000ed78`
- `0x1800114d8`
- `0x1800126e0`
- `0x180012710`
- `0x1800149f8`
- `0x1800165da`
- `0x1800183bc`
- `0x180019454`

## pseudocode

```c
void __fastcall Broker::BrokerBase::DestroyEvent(__int64 a1, unsigned int a2, _QWORD *a3, __int64 a4)
{
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 v9; // rcx
  _QWORD *v10; // rax
  _QWORD pExceptionObject[5]; // [rsp+30h] [rbp-28h] BYREF
  int v12; // [rsp+70h] [rbp+18h] BYREF
  __int64 v13; // [rsp+78h] [rbp+20h] BYREF

  if ( (unsigned int)dword_180028000 > 4 && (unsigned __int8)tlgKeywordOn(a1, 4, a3, a4) )
  {
    v9 = *(_QWORD *)v7;
    v12 = *(_DWORD *)(*(_QWORD *)v7 + 28LL);
    v13 = *(_QWORD *)(v9 + 16);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
      v9,
      byte_180021FBE,
      v7,
      v8,
      &v13,
      (__int64)&v12);
  }
  Broker::BrokerBase::OnEventDisable(a1, a2, a3);
  if ( (unsigned int)Broker::BrokerEvent::GetState(*a3) )
  {
    Broker::NotFound::NotFound((Broker::NotFound *)pExceptionObject);
    throw (Broker::NotFound *)pExceptionObject;
  }
  v10 = std::shared_ptr<Broker::BrokerBase>::shared_ptr<Broker::BrokerBase>(pExceptionObject, a3);
  Broker::BrokeredEventTable::Remove(a1 + 208, v10);
  Broker::BrokerBase::OnEventDestroy(a1, a2, a3);
  Broker::BrokerEvent::EventCleanup((Broker::BrokerEvent *)*a3);
}

```

## disassembly

```asm
0x1800183bc  mov     [rsp+arg_0], rbx
0x1800183c1  mov     [rsp+arg_8], rsi
0x1800183c6  push    rdi
0x1800183c7  sub     rsp, 50h
0x1800183cb  mov     eax, cs:dword_180028000
0x1800183d1  mov     esi, edx
0x1800183d3  mov     edx, 4
0x1800183d8  mov     rbx, r8
0x1800183db  mov     rdi, rcx
0x1800183de  cmp     eax, edx
0x1800183e0  jbe     short loc_18001841E
0x1800183e2  call    _tlgKeywordOn
0x1800183e7  test    al, al
0x1800183e9  jz      short loc_18001841E
0x1800183eb  mov     rcx, [r8]
0x1800183ee  lea     rdx, byte_180021FBE
0x1800183f5  mov     eax, [rcx+1Ch]
0x1800183f8  mov     [rsp+58h+arg_10], eax
0x1800183fc  mov     rax, [rcx+10h]
0x180018400  mov     [rsp+58h+arg_18], rax
0x180018405  lea     rax, [rsp+58h+arg_10]
0x18001840a  mov     [rsp+58h+var_30], rax
0x18001840f  lea     rax, [rsp+58h+arg_18]
0x180018414  mov     [rsp+58h+var_38], rax
0x180018419  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x18001841e  mov     r8, rbx
0x180018421  mov     edx, esi
0x180018423  mov     rcx, rdi
0x180018426  call    ?OnEventDisable@BrokerBase@Broker@@AEAAXW4_BR_EVENT_CALL_REASON@@AEBV?$shared_ptr@VBrokerEvent@Broker@@@std@@@Z; Broker::BrokerBase::OnEventDisable(_BR_EVENT_CALL_REASON,std::shared_ptr<Broker::BrokerEvent> const &)
0x18001842b  mov     rcx, [rbx]
0x18001842e  call    ?GetState@BrokerEvent@Broker@@QEBA?AW4_BROKERED_EVENT_STATE@@XZ; Broker::BrokerEvent::GetState(void)
0x180018433  test    eax, eax
0x180018435  jnz     short loc_180018477
0x180018437  mov     rdx, rbx
0x18001843a  lea     rcx, [rsp+58h+pExceptionObject]
0x18001843f  call    ??0?$shared_ptr@VBrokerBase@Broker@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Broker::BrokerBase>::shared_ptr<Broker::BrokerBase>(std::shared_ptr<Broker::BrokerBase> const &)
0x180018444  mov     rdx, rax
0x180018447  lea     rcx, [rdi+0D0h]
0x18001844e  call    ?Remove@BrokeredEventTable@Broker@@QEAAXV?$shared_ptr@VBrokerEvent@Broker@@@std@@@Z; Broker::BrokeredEventTable::Remove(std::shared_ptr<Broker::BrokerEvent>)
0x180018453  mov     r8, rbx
0x180018456  mov     edx, esi
0x180018458  mov     rcx, rdi
0x18001845b  call    ?OnEventDestroy@BrokerBase@Broker@@AEAAXW4_BR_EVENT_CALL_REASON@@AEBV?$shared_ptr@VBrokerEvent@Broker@@@std@@@Z; Broker::BrokerBase::OnEventDestroy(_BR_EVENT_CALL_REASON,std::shared_ptr<Broker::BrokerEvent> const &)
0x180018460  mov     rcx, [rbx]; this
0x180018463  mov     rbx, [rsp+58h+arg_0]
0x180018468  mov     rsi, [rsp+58h+arg_8]
0x18001846d  add     rsp, 50h
0x180018471  pop     rdi
0x180018472  jmp     ?EventCleanup@BrokerEvent@Broker@@QEAAXXZ; Broker::BrokerEvent::EventCleanup(void)
0x180018477  lea     rcx, [rsp+58h+pExceptionObject]; this
0x18001847c  call    ??0NotFound@Broker@@QEAA@XZ; Broker::NotFound::NotFound(void)
0x180018481  lea     rdx, _TI3?AUNotFound@Broker@@; pThrowInfo
0x180018488  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18001848d  call    _CxxThrowException_0
```
