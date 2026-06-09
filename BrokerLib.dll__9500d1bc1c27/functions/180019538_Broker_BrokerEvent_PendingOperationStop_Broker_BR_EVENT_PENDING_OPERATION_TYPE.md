# Broker::BrokerEvent::PendingOperationStop(Broker::_BR_EVENT_PENDING_OPERATION_TYPE)

- ea: `0x180019538`
- end: `0x1800195ae`
- name: `?PendingOperationStop@BrokerEvent@Broker@@QEAAXW4_BR_EVENT_PENDING_OPERATION_TYPE@2@@Z`
- size: `118`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180001ff8`
- `0x180012710`

## callees

- `0x18000f888`
- `0x1800126e0`
- `0x180019538`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x1800195a7`

## pseudocode

```c
void __fastcall Broker::BrokerEvent::PendingOperationStop(__int64 a1, unsigned int a2, __int64 a3, __int64 a4)
{
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // r9
  int v8; // [rsp+50h] [rbp+8h] BYREF
  int v9; // [rsp+60h] [rbp+18h] BYREF
  __int64 v10; // [rsp+68h] [rbp+20h] BYREF

  if ( (unsigned int)dword_180028000 > 4 && (unsigned __int8)tlgKeywordOn(a1, 4, a2, a4) )
  {
    v9 = *(_DWORD *)(a1 + 28);
    v10 = *(_QWORD *)(a1 + 16);
    v8 = v6;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v5,
      byte_180022211,
      v6,
      v7,
      &v10,
      (__int64)&v9,
      (__int64)&v8);
  }
  *(_DWORD *)(a1 + 24) &= ~1u;
  WakeByAddressAll((PVOID)(a1 + 24));
}

```

## disassembly

```asm
0x180019538  push    rbx
0x18001953a  sub     rsp, 40h
0x18001953e  mov     eax, cs:dword_180028000
0x180019544  mov     r8d, edx
0x180019547  mov     edx, 4
0x18001954c  mov     rbx, rcx
0x18001954f  cmp     eax, edx
0x180019551  jbe     short loc_18001959B
0x180019553  call    _tlgKeywordOn
0x180019558  test    al, al
0x18001955a  jz      short loc_18001959B
0x18001955c  mov     eax, [rbx+1Ch]
0x18001955f  lea     rdx, byte_180022211
0x180019566  mov     [rsp+48h+arg_10], eax
0x18001956a  mov     rax, [rbx+10h]
0x18001956e  mov     [rsp+48h+arg_18], rax
0x180019573  lea     rax, [rsp+48h+arg_0]
0x180019578  mov     [rsp+48h+var_18], rax
0x18001957d  lea     rax, [rsp+48h+arg_10]
0x180019582  mov     [rsp+48h+var_20], rax
0x180019587  lea     rax, [rsp+48h+arg_18]
0x18001958c  mov     [rsp+48h+var_28], rax
0x180019591  mov     [rsp+48h+arg_0], r8d
0x180019596  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001959b  lea     rcx, [rbx+18h]
0x18001959f  and     dword ptr [rcx], 0FFFFFFFEh
0x1800195a2  add     rsp, 40h
0x1800195a6  pop     rbx
0x1800195a7  jmp     cs:__imp_WakeByAddressAll
```
