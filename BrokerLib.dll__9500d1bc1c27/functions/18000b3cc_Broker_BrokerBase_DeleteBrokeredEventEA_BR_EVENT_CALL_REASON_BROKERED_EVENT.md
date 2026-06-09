# Broker::BrokerBase::DeleteBrokeredEventEA(_BR_EVENT_CALL_REASON,_BROKERED_EVENT *)

- ea: `0x18000b3cc`
- end: `0x18000b4fe`
- name: `?DeleteBrokeredEventEA@BrokerBase@Broker@@QEAAXW4_BR_EVENT_CALL_REASON@@PEAU_BROKERED_EVENT@@@Z`
- size: `306`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18000b2b0`

## callees

- `0x180004ae0`
- `0x180005a80`
- `0x180005b50`
- `0x18000b3cc`
- `0x18000eb40`
- `0x18000ed50`
- `0x18000fc28`
- `0x1800126e0`
- `0x180015af0`
- `0x1800183bc`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Broker::BrokerBase::DeleteBrokeredEventEA(struct _RTL_SRWLOCK *a1, unsigned int a2, __int64 a3)
{
  __int64 v3; // rdi
  __int64 v6; // r9
  __int64 v7; // r8
  __int64 v8; // r9
  std::_Ref_count_base *v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  __int128 *v13; // [rsp+30h] [rbp-58h] BYREF
  __int64 v14; // [rsp+38h] [rbp-50h] BYREF
  std::_Ref_count_base *v15; // [rsp+40h] [rbp-48h]
  _BYTE v16[16]; // [rsp+48h] [rbp-40h] BYREF
  __int128 v17; // [rsp+58h] [rbp-30h] BYREF

  v3 = a3;
  v13 = (__int128 *)a3;
  v17 = 0;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    WPP_SF__guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids, a1[1].Ptr);
  v17 = BLP_TRACELOGGING_INVALID_GUID;
  Broker::ScopedWriteLock::ScopedWriteLock((Broker::ScopedWriteLock *)v16, a1, 1);
  try
  {
    Broker::BrokeredEventTable::Find(&a1[26], &v14, &v13);
    v17 = *(_OWORD *)*(_QWORD *)(v14 + 16);
    Broker::BrokerBase::DestroyEvent((__int64)a1, a2, &v14, v6);
    v9 = v15;
    if ( v15 )
      std::_Ref_count_base::_Decref(v15);
  }
  catch ( Broker::NotFound )
  {
    v9 = (std::_Ref_count_base *)WPP_GLOBAL_Control;
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids);
    v3 = (__int64)v13;
  }
  if ( (unsigned int)dword_180028000 > 4 && (unsigned __int8)tlgKeywordOn(v9, 1, v7, v8) )
  {
    v13 = &v17;
    v14 = v3;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>>(
      v10,
      byte_1800220BE,
      v11,
      v12,
      (__int64)&v14,
      (__int64 *)&v13);
  }
  Broker::ScopedWriteLock::~ScopedWriteLock((Broker::ScopedWriteLock *)v16);
}

```

## disassembly

```asm
0x18000b3cc  push    rbx
0x18000b3ce  push    rsi
0x18000b3cf  push    rdi
0x18000b3d0  sub     rsp, 70h
0x18000b3d4  mov     rax, cs:__security_cookie
0x18000b3db  xor     rax, rsp
0x18000b3de  mov     [rsp+88h+var_20], rax
0x18000b3e3  mov     rdi, r8
0x18000b3e6  mov     esi, edx
0x18000b3e8  mov     rbx, rcx
0x18000b3eb  mov     [rsp+88h+var_58], r8
0x18000b3f0  xorps   xmm0, xmm0
0x18000b3f3  movups  [rsp+88h+var_30], xmm0
0x18000b3f8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b3ff  test    dword ptr [rcx+1Ch], 800h
0x18000b406  jz      short loc_18000B427
0x18000b408  cmp     byte ptr [rcx+19h], 5
0x18000b40c  jb      short loc_18000B427
0x18000b40e  mov     edx, 1Dh
0x18000b413  mov     r9, [rbx+8]
0x18000b417  lea     r8, WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids
0x18000b41e  mov     rcx, [rcx+10h]
0x18000b422  call    WPP_SF__guid_
0x18000b427  movups  xmm0, cs:BLP_TRACELOGGING_INVALID_GUID
0x18000b42e  movdqu  [rsp+88h+var_30], xmm0
0x18000b434  mov     r8b, 1; bool
0x18000b437  mov     rdx, rbx; struct _RTL_SRWLOCK *
0x18000b43a  lea     rcx, [rsp+88h+var_40]; this
0x18000b43f  call    ??0ScopedWriteLock@Broker@@QEAA@AEAU_RTL_SRWLOCK@@_N@Z; Broker::ScopedWriteLock::ScopedWriteLock(_RTL_SRWLOCK &,bool)
0x18000b444  nop
0x18000b445  lea     rcx, [rbx+0D0h]
0x18000b44c  lea     r8, [rsp+88h+var_58]
0x18000b451  lea     rdx, [rsp+88h+var_50]
0x18000b456  call    ?Find@BrokeredEventTable@Broker@@QEAA?AV?$shared_ptr@VBrokerEvent@Broker@@@std@@AEBQEAU_BROKERED_EVENT@@@Z; Broker::BrokeredEventTable::Find(_BROKERED_EVENT * const &)
0x18000b45b  nop
0x18000b45c  mov     rax, [rsp+88h+var_50]
0x18000b461  mov     r8, [rax+10h]
0x18000b465  movups  xmm0, xmmword ptr [r8]
0x18000b469  movdqu  [rsp+88h+var_30], xmm0
0x18000b46f  lea     r8, [rsp+88h+var_50]
0x18000b474  mov     edx, esi
0x18000b476  mov     rcx, rbx
0x18000b479  call    ?DestroyEvent@BrokerBase@Broker@@AEAAXW4_BR_EVENT_CALL_REASON@@AEAV?$shared_ptr@VBrokerEvent@Broker@@@std@@@Z; Broker::BrokerBase::DestroyEvent(_BR_EVENT_CALL_REASON,std::shared_ptr<Broker::BrokerEvent> &)
0x18000b47e  nop
0x18000b47f  mov     rcx, [rsp+88h+var_48]; this
0x18000b484  test    rcx, rcx
0x18000b487  jz      short loc_18000B48F
0x18000b489  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000b48e  nop
0x18000b48f  jmp     short loc_18000B496
0x18000b491  mov     rdi, [rsp+88h+var_58]
0x18000b496  mov     eax, cs:dword_180028000
0x18000b49c  cmp     eax, 4
0x18000b49f  jbe     short loc_18000B4DF
0x18000b4a1  mov     edx, 1
0x18000b4a6  call    _tlgKeywordOn
0x18000b4ab  test    al, al
0x18000b4ad  jz      short loc_18000B4DF
0x18000b4af  lea     rax, [rsp+88h+var_30]
0x18000b4b4  mov     [rsp+88h+var_58], rax
0x18000b4b9  mov     [rsp+88h+var_50], rdi
0x18000b4be  lea     rax, [rsp+88h+var_58]
0x18000b4c3  mov     [rsp+88h+var_60], rax
0x18000b4c8  lea     rax, [rsp+88h+var_50]
0x18000b4cd  mov     [rsp+88h+var_68], rax
0x18000b4d2  lea     rdx, byte_1800220BE
0x18000b4d9  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByRef<16> const &)
0x18000b4de  nop
0x18000b4df  lea     rcx, [rsp+88h+var_40]; this
0x18000b4e4  call    ??1ScopedWriteLock@Broker@@QEAA@XZ; Broker::ScopedWriteLock::~ScopedWriteLock(void)
0x18000b4e9  mov     rcx, [rsp+88h+var_20]
0x18000b4ee  xor     rcx, rsp; StackCookie
0x18000b4f1  call    __security_check_cookie
0x18000b4f6  add     rsp, 70h
0x18000b4fa  pop     rdi
0x18000b4fb  pop     rsi
0x18000b4fc  pop     rbx
0x18000b4fd  retn
```
