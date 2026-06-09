# Broker::TimeBroker::ExpireTimers(Broker::TimerWheel &,Broker::TimeBroker::_TB_TIMER_EXPIRY_REASON)

- ea: `0x18001579c`
- end: `0x18001598e`
- name: `?ExpireTimers@TimeBroker@Broker@@AEAAXAEAVTimerWheel@2@W4_TB_TIMER_EXPIRY_REASON@12@@Z`
- size: `498`
- prototype: `void __fastcall(Broker::TimeBroker *, __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180001c14`

## callees

- `0x18000106c`
- `0x180005b30`
- `0x180006070`
- `0x180008370`
- `0x18000b990`
- `0x18000bba0`
- `0x18000bc90`
- `0x18000bd70`
- `0x18000ee60`
- `0x18000fe70`
- `0x18001579c`
- `0x180018684`

## pseudocode

```c
void __fastcall Broker::TimeBroker::ExpireTimers(Broker::TimeBroker *a1, __int64 a2)
{
  __int64 v4; // rsi
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 *FirstDueEvent; // rax
  __int64 *NextDueEvent; // rax
  std::_Ref_count_base *i; // rcx
  std::_Ref_count_base *v11; // rbx
  _QWORD *v12; // rax
  __int64 v13; // r8
  __int64 *v14; // rax
  __int64 *v15; // rax
  __int64 v16; // rcx
  std::_Ref_count_base *v17[2]; // [rsp+30h] [rbp-40h] BYREF
  __int64 v18; // [rsp+40h] [rbp-30h] BYREF
  std::_Ref_count_base *v19; // [rsp+48h] [rbp-28h]
  __int64 v20; // [rsp+50h] [rbp-20h] BYREF
  _BYTE v21[8]; // [rsp+60h] [rbp-10h] BYREF
  std::_Ref_count_base *v22; // [rsp+68h] [rbp-8h]
  int v23; // [rsp+90h] [rbp+20h] BYREF
  __int64 v24; // [rsp+A8h] [rbp+38h] BYREF

  *(_OWORD *)v17 = 0;
  v4 = *((_QWORD *)a1 + 25);
  if ( (unsigned int)dword_180026058 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180026058, 10) )
  {
    v23 = v6;
    v24 = v4;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      v5,
      (__int64)qword_1800207F8,
      v6,
      v7,
      (__int64)&v24,
      (__int64)&v23);
  }
  FirstDueEvent = (__int64 *)Broker::TimerWheel::GetFirstDueEvent(a2, &v18);
  std::shared_ptr<Broker::TimeEvent>::operator=(v17, FirstDueEvent);
  if ( v19 )
    std::_Ref_count_base::_Decref(v19);
  if ( v17[0] )
    Broker::TimeEvent::LogState(v17[0], 0);
  NextDueEvent = (__int64 *)Broker::TimerWheel::GetNextDueEvent(a2, &v18, v4);
  std::shared_ptr<Broker::TimeEvent>::operator=(v17, NextDueEvent);
  for ( i = v19; ; i = v22 )
  {
    if ( i )
      std::_Ref_count_base::_Decref(i);
    v11 = v17[0];
    if ( !v17[0] )
      break;
    Broker::TimeEvent::LogState(v17[0], 1);
    *((_QWORD *)v11 + 28) = 0;
    if ( *((_QWORD *)v11 + 29) )
    {
      v12 = std::shared_ptr<Broker::TimeEvent>::shared_ptr<Broker::TimeEvent>(&v18, v17);
      Broker::TimerWheel::Remove(v13, v12);
      *((_QWORD *)v11 + 29) = 0;
    }
    std::shared_ptr<Broker::TimeEvent>::shared_ptr<Broker::TimeEvent>(&v20, v17);
    Broker::TimeBroker::SignalEvent(a1);
    Broker::TimeEvent::LogState(v11, 2);
    v14 = (__int64 *)Broker::TimerWheel::GetNextDueEvent(a2, v21, v4);
    std::shared_ptr<Broker::TimeEvent>::operator=(v17, v14);
  }
  v15 = (__int64 *)Broker::TimerWheel::GetFirstDueEvent(a2, v21);
  std::shared_ptr<Broker::TimeEvent>::operator=(v17, v15);
  if ( v22 )
    std::_Ref_count_base::_Decref(v22);
  if ( v17[0] )
    Broker::TimeEvent::LogState(v17[0], 0);
  if ( (unsigned int)dword_180026058 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180026058, 10) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v16,
      (__int64)word_180020662);
  if ( v17[1] )
    std::_Ref_count_base::_Decref(v17[1]);
}

```

## disassembly

```asm
0x18001579c  mov     [rsp-18h+arg_8], rbx
0x1800157a1  mov     [rsp-18h+arg_10], rsi
0x1800157a6  push    rbp
0x1800157a7  push    rdi
0x1800157a8  push    r14
0x1800157aa  mov     rbp, rsp
0x1800157ad  sub     rsp, 70h
0x1800157b1  mov     rdi, rdx
0x1800157b4  mov     r14, rcx
0x1800157b7  xorps   xmm0, xmm0
0x1800157ba  movdqu  xmmword ptr [rbp+var_40], xmm0
0x1800157bf  mov     rsi, [rcx+0C8h]
0x1800157c6  mov     eax, cs:dword_180026058
0x1800157cc  cmp     eax, 5
0x1800157cf  jbe     short loc_18001580C
0x1800157d1  mov     edx, 0Ah
0x1800157d6  lea     rcx, dword_180026058
0x1800157dd  call    _tlgKeywordOn
0x1800157e2  test    al, al
0x1800157e4  jz      short loc_18001580C
0x1800157e6  mov     [rbp+arg_0], r8d
0x1800157ea  mov     [rbp+arg_18], rsi
0x1800157ee  lea     rax, [rbp+arg_0]
0x1800157f2  mov     [rsp+70h+var_48], rax
0x1800157f7  lea     rax, [rbp+arg_18]
0x1800157fb  mov     [rsp+70h+var_50], rax
0x180015800  lea     rdx, qword_1800207F8
0x180015807  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x18001580c  lea     rdx, [rbp+var_30]
0x180015810  mov     rcx, rdi
0x180015813  call    ?GetFirstDueEvent@TimerWheel@Broker@@QEAA?AV?$shared_ptr@VTimeEvent@Broker@@@std@@XZ; Broker::TimerWheel::GetFirstDueEvent(void)
0x180015818  mov     rdx, rax
0x18001581b  lea     rcx, [rbp+var_40]
0x18001581f  call    ??4?$shared_ptr@VTimeEvent@Broker@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Broker::TimeEvent>::operator=(std::shared_ptr<Broker::TimeEvent> &&)
0x180015824  mov     rcx, [rbp+var_28]; this
0x180015828  test    rcx, rcx
0x18001582b  jz      short loc_180015832
0x18001582d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180015832  mov     rcx, [rbp+var_40]
0x180015836  test    rcx, rcx
0x180015839  jz      short loc_180015842
0x18001583b  xor     edx, edx
0x18001583d  call    ?LogState@TimeEvent@Broker@@QEAAXW4_TB_EVENT_LOG_STATE_REASON@2@@Z; Broker::TimeEvent::LogState(Broker::_TB_EVENT_LOG_STATE_REASON)
0x180015842  mov     r8, rsi
0x180015845  lea     rdx, [rbp+var_30]
0x180015849  mov     rcx, rdi
0x18001584c  call    ?GetNextDueEvent@TimerWheel@Broker@@QEAA?AV?$shared_ptr@VTimeEvent@Broker@@@std@@_J@Z; Broker::TimerWheel::GetNextDueEvent(__int64)
0x180015851  mov     rdx, rax
0x180015854  lea     rcx, [rbp+var_40]
0x180015858  call    ??4?$shared_ptr@VTimeEvent@Broker@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Broker::TimeEvent>::operator=(std::shared_ptr<Broker::TimeEvent> &&)
0x18001585d  mov     rcx, [rbp+var_28]; this
0x180015861  test    rcx, rcx
0x180015864  jz      short loc_18001586B
0x180015866  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001586b  mov     rbx, [rbp+var_40]
0x18001586f  test    rbx, rbx
0x180015872  jz      loc_180015908
0x180015878  mov     edx, 1
0x18001587d  mov     rcx, rbx
0x180015880  call    ?LogState@TimeEvent@Broker@@QEAAXW4_TB_EVENT_LOG_STATE_REASON@2@@Z; Broker::TimeEvent::LogState(Broker::_TB_EVENT_LOG_STATE_REASON)
0x180015885  mov     qword ptr [rbx+0E0h], 0
0x180015890  mov     r8, [rbx+0E8h]
0x180015897  test    r8, r8
0x18001589a  jz      short loc_1800158BF
0x18001589c  lea     rdx, [rbp+var_40]
0x1800158a0  lea     rcx, [rbp+var_30]
0x1800158a4  call    ??0?$shared_ptr@VTimeEvent@Broker@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Broker::TimeEvent>::shared_ptr<Broker::TimeEvent>(std::shared_ptr<Broker::TimeEvent> const &)
0x1800158a9  mov     rdx, rax
0x1800158ac  mov     rcx, r8
0x1800158af  call    ?Remove@TimerWheel@Broker@@QEAAXV?$shared_ptr@VTimeEvent@Broker@@@std@@@Z; Broker::TimerWheel::Remove(std::shared_ptr<Broker::TimeEvent>)
0x1800158b4  mov     qword ptr [rbx+0E8h], 0
0x1800158bf  lea     rdx, [rbp+var_40]
0x1800158c3  lea     rcx, [rbp+var_20]
0x1800158c7  call    ??0?$shared_ptr@VTimeEvent@Broker@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Broker::TimeEvent>::shared_ptr<Broker::TimeEvent>(std::shared_ptr<Broker::TimeEvent> const &)
0x1800158cc  mov     rdx, rax
0x1800158cf  mov     rcx, r14; this
0x1800158d2  call    ?SignalEvent@TimeBroker@Broker@@AEAAXV?$shared_ptr@VTimeEvent@Broker@@@std@@@Z; Broker::TimeBroker::SignalEvent(std::shared_ptr<Broker::TimeEvent>)
0x1800158d7  mov     edx, 2
0x1800158dc  mov     rcx, rbx
0x1800158df  call    ?LogState@TimeEvent@Broker@@QEAAXW4_TB_EVENT_LOG_STATE_REASON@2@@Z; Broker::TimeEvent::LogState(Broker::_TB_EVENT_LOG_STATE_REASON)
0x1800158e4  mov     r8, rsi
0x1800158e7  lea     rdx, [rbp+var_10]
0x1800158eb  mov     rcx, rdi
0x1800158ee  call    ?GetNextDueEvent@TimerWheel@Broker@@QEAA?AV?$shared_ptr@VTimeEvent@Broker@@@std@@_J@Z; Broker::TimerWheel::GetNextDueEvent(__int64)
0x1800158f3  mov     rdx, rax
0x1800158f6  lea     rcx, [rbp+var_40]
0x1800158fa  call    ??4?$shared_ptr@VTimeEvent@Broker@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Broker::TimeEvent>::operator=(std::shared_ptr<Broker::TimeEvent> &&)
0x1800158ff  mov     rcx, [rbp+var_8]
0x180015903  jmp     loc_180015861
0x180015908  lea     rdx, [rbp+var_10]
0x18001590c  mov     rcx, rdi
0x18001590f  call    ?GetFirstDueEvent@TimerWheel@Broker@@QEAA?AV?$shared_ptr@VTimeEvent@Broker@@@std@@XZ; Broker::TimerWheel::GetFirstDueEvent(void)
0x180015914  mov     rdx, rax
0x180015917  lea     rcx, [rbp+var_40]
0x18001591b  call    ??4?$shared_ptr@VTimeEvent@Broker@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Broker::TimeEvent>::operator=(std::shared_ptr<Broker::TimeEvent> &&)
0x180015920  mov     rcx, [rbp+var_8]; this
0x180015924  test    rcx, rcx
0x180015927  jz      short loc_18001592E
0x180015929  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001592e  mov     rcx, [rbp+var_40]
0x180015932  test    rcx, rcx
0x180015935  jz      short loc_18001593E
0x180015937  xor     edx, edx
0x180015939  call    ?LogState@TimeEvent@Broker@@QEAAXW4_TB_EVENT_LOG_STATE_REASON@2@@Z; Broker::TimeEvent::LogState(Broker::_TB_EVENT_LOG_STATE_REASON)
0x18001593e  mov     eax, cs:dword_180026058
0x180015944  cmp     eax, 5
0x180015947  jbe     short loc_18001596B
0x180015949  mov     edx, 0Ah
0x18001594e  lea     rcx, dword_180026058
0x180015955  call    _tlgKeywordOn
0x18001595a  test    al, al
0x18001595c  jz      short loc_18001596B
0x18001595e  lea     rdx, word_180020662
0x180015965  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18001596a  nop
0x18001596b  mov     rcx, [rbp+var_40+8]; this
0x18001596f  test    rcx, rcx
0x180015972  jz      short loc_180015979
0x180015974  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180015979  lea     r11, [rsp+70h+var_s0]
0x18001597e  mov     rbx, [r11+28h]
0x180015982  mov     rsi, [r11+30h]
0x180015986  mov     rsp, r11
0x180015989  pop     r14
0x18001598b  pop     rdi
0x18001598c  pop     rbp
0x18001598d  retn
```
