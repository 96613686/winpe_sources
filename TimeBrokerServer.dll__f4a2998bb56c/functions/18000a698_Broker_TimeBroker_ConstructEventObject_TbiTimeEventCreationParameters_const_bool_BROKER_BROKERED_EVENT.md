# Broker::TimeBroker::ConstructEventObject(_TbiTimeEventCreationParameters const &,bool,_BROKER *,_BROKERED_EVENT *)

- ea: `0x18000a698`
- end: `0x18000a984`
- name: `?ConstructEventObject@TimeBroker@Broker@@AEAA?AV?$unique_ptr@VTimeEvent@Broker@@U?$default_delete@VTimeEvent@Broker@@@std@@@std@@AEBU_TbiTimeEventCreationParameters@@_NPEAU_BROKER@@PEAU_BROKERED_EVENT@@@Z`
- size: `748`
- prototype: `Broker::TimeEvent **__fastcall(__int64, Broker::TimeEvent **, __int64, __int64, struct _BROKER *, struct _BROKERED_EVENT *)`
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x18000ef50`

## callees

- `0x180004488`
- `0x18000461c`
- `0x180004b70`
- `0x18000a698`
- `0x18000a990`
- `0x18000a9e4`
- `0x18000cb24`
- `0x180011858`
- `0x180012df4`
- `0x180014c90`
- `0x1800169bc`
- `0x1800179fc`
- `0x18001811c`
- `0x180018320`
- `0x180018b0c`

## pseudocode

```c
Broker::TimeEvent **__fastcall Broker::TimeBroker::ConstructEventObject(
        __int64 a1,
        Broker::TimeEvent **a2,
        __int64 a3,
        __int64 a4,
        struct _BROKER *a5,
        struct _BROKERED_EVENT *a6)
{
  __int64 v9; // r8
  __int64 v10; // rdx
  Broker::TimeEvent *v11; // rdx
  Broker::TimeEvent *v12; // rax
  int v13; // r8d
  int v14; // r8d
  __int128 v16; // [rsp+68h] [rbp+7h] BYREF
  __int64 v17; // [rsp+78h] [rbp+17h] BYREF
  __int64 v18; // [rsp+80h] [rbp+1Fh]
  Broker::TimeEvent *v19; // [rsp+C8h] [rbp+67h] BYREF

  *a2 = 0;
  std::vector<_GUID>::vector<_GUID>(&v17);
  v10 = v17;
  if ( v18 == v17 )
    v10 = v18;
  else
    v18 = v17;
  std::vector<unsigned char>::_Insert_counted_range<unsigned char *>(
    &v17,
    v10,
    *(_QWORD *)(v9 + 64),
    *(unsigned int *)(v9 + 56));
  if ( *(_DWORD *)a3 )
  {
    switch ( *(_DWORD *)a3 )
    {
      case 1:
        v19 = (Broker::TimeEvent *)operator new(0x130u);
        v12 = (Broker::TimeEvent *)Broker::CalendarTimeEvent::CalendarTimeEvent(
                                     (_DWORD)v19,
                                     (int)a3 + 8,
                                     *(_DWORD *)(a3 + 24),
                                     *(_DWORD *)(a3 + 28),
                                     *(_DWORD *)(a3 + 32),
                                     a3 + 40,
                                     (__int64)&v17);
        break;
      case 2:
        v19 = (Broker::TimeEvent *)operator new(0x138u);
        v12 = (Broker::TimeEvent *)Broker::ConvenientTimeEvent::ConvenientTimeEvent(
                                     v19,
                                     *(_DWORD *)(a3 + 32),
                                     (__int64)&v17);
        break;
      case 3:
        v19 = (Broker::TimeEvent *)operator new(0x120u);
        v12 = (Broker::TimeEvent *)Broker::KeepAliveEvent::KeepAliveEvent(
                                     v19,
                                     *(_DWORD *)(a3 + 16),
                                     *(_DWORD *)(a3 + 20) != 0,
                                     *(_BYTE *)(a1 + 184),
                                     a3 + 24,
                                     (__int64)&v17);
        break;
      case 4:
        v19 = (Broker::TimeEvent *)operator new(0x158u);
        v16 = *(_OWORD *)(a3 + 72);
        LOBYTE(v13) = *(_DWORD *)(a3 + 88) != 0;
        v12 = (Broker::TimeEvent *)Broker::CAlarmTimeEvent::CAlarmTimeEvent(
                                     (_DWORD)v19,
                                     (int)a3 + 8,
                                     v13,
                                     *(_DWORD *)(a3 + 24),
                                     (__int64)&v16,
                                     *(_DWORD *)(a3 + 28),
                                     a3 + 40,
                                     *(_DWORD *)(a3 + 32) != 0,
                                     (__int64)&v17);
        break;
      case 5:
        v19 = (Broker::TimeEvent *)operator new(0x140u);
        v12 = (Broker::TimeEvent *)Broker::CKeepAliveEvent::CKeepAliveEvent(
                                     (_DWORD)v19,
                                     (int)a3 + 8,
                                     *(_DWORD *)(a3 + 24),
                                     *(_DWORD *)(a3 + 28),
                                     a3 + 40,
                                     *(_DWORD *)(a3 + 32) != 0,
                                     *(_BYTE *)(a1 + 184),
                                     (__int64)&v17);
        break;
      default:
        goto LABEL_18;
    }
  }
  else
  {
    v19 = (Broker::TimeEvent *)operator new(0x140u);
    v16 = *(_OWORD *)(a3 + 72);
    LOBYTE(v14) = *(_DWORD *)(a3 + 88) != 0;
    v12 = (Broker::TimeEvent *)Broker::AlarmTimeEvent::AlarmTimeEvent(
                                 (_DWORD)v19,
                                 (int)a3 + 8,
                                 v14,
                                 *(_DWORD *)(a3 + 24),
                                 (__int64)&v16,
                                 *(_DWORD *)(a3 + 28),
                                 *(_DWORD *)(a3 + 32),
                                 a3 + 40,
                                 (__int64)&v17);
  }
  v19 = v12;
  std::unique_ptr<Broker::TimeEvent>::operator=<std::default_delete<Broker::TimeEvent>,0>(a2, &v19);
  v11 = v19;
  if ( v19 )
    std::default_delete<Broker::TimeEvent>::operator()();
LABEL_18:
  StringCbCopyW((unsigned __int16 *)*a2 + 47, (unsigned __int64)v11, (const unsigned __int16 *)(a3 + 116));
  if ( a5 && a6 )
    Broker::TimeEvent::SetEventBrokerContext(*a2, a5, a6);
  std::vector<unsigned char>::_Tidy(&v17);
  return a2;
}

```

## disassembly

```asm
0x18000a698  mov     rax, rsp
0x18000a69b  mov     [rax+8], rbx
0x18000a69f  mov     [rax+20h], rsi
0x18000a6a3  mov     [rax+10h], rdx
0x18000a6a7  push    rbp
0x18000a6a8  push    rdi
0x18000a6a9  push    r14
0x18000a6ab  lea     rbp, [rax-4Fh]
0x18000a6af  sub     rsp, 90h
0x18000a6b6  mov     r14b, r9b
0x18000a6b9  mov     rbx, r8
0x18000a6bc  mov     rdi, rdx
0x18000a6bf  mov     rsi, rcx
0x18000a6c2  mov     [rbp+47h+var_50], 0
0x18000a6c9  mov     qword ptr [rdx], 0
0x18000a6d0  mov     [rbp+47h+var_50], 1
0x18000a6d7  lea     rcx, [rbp+47h+var_30]
0x18000a6db  call    ??0?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID>::vector<_GUID>(void)
0x18000a6e0  nop
0x18000a6e1  mov     rdx, [rbp+47h+var_30]
0x18000a6e5  cmp     [rbp+47h+var_28], rdx
0x18000a6e9  jz      short loc_18000A6F1
0x18000a6eb  mov     [rbp+47h+var_28], rdx
0x18000a6ef  jmp     short loc_18000A6F5
0x18000a6f1  mov     rdx, [rbp+47h+var_28]
0x18000a6f5  mov     r9d, [r8+38h]
0x18000a6f9  mov     r8, [r8+40h]
0x18000a6fd  lea     rcx, [rbp+47h+var_30]
0x18000a701  call    ??$_Insert_counted_range@PEAE@?$vector@EV?$allocator@E@std@@@std@@AEAAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@1@PEAE_K@Z; std::vector<uchar>::_Insert_counted_range<uchar *>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,uchar *,unsigned __int64)
0x18000a706  mov     ecx, [rbx]
0x18000a708  test    ecx, ecx
0x18000a70a  jz      loc_18000A8BA
0x18000a710  sub     ecx, 1
0x18000a713  jz      loc_18000A87C
0x18000a719  sub     ecx, 1
0x18000a71c  jz      loc_18000A844
0x18000a722  sub     ecx, 1
0x18000a725  jz      loc_18000A7EF
0x18000a72b  sub     ecx, 1
0x18000a72e  jz      short loc_18000A78A
0x18000a730  cmp     ecx, 1
0x18000a733  jnz     loc_18000A934
0x18000a739  mov     ecx, 140h; Size
0x18000a73e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a743  mov     [rbp+47h+arg_10], rax
0x18000a747  cmp     dword ptr [rbx+20h], 0
0x18000a74b  setnz   r8b
0x18000a74f  lea     r9, [rbx+28h]
0x18000a753  lea     rdx, [rbx+8]
0x18000a757  lea     rcx, [rbp+47h+var_30]
0x18000a75b  mov     [rsp+0A0h+var_68], rcx
0x18000a760  mov     cl, [rsi+0B8h]
0x18000a766  mov     [rsp+0A0h+var_70], cl
0x18000a76a  mov     [rsp+0A0h+var_78], r8b
0x18000a76f  mov     qword ptr [rsp+0A0h+var_80], r9
0x18000a774  mov     r9d, [rbx+1Ch]
0x18000a778  mov     r8d, [rbx+18h]
0x18000a77c  mov     rcx, rax
0x18000a77f  call    ??0CKeepAliveEvent@Broker@@QEAA@AEBU_SYSTEMTIME@@KKPEBU_TbiTimeEventModsParameters@@_N2AEBV?$vector@EV?$allocator@E@std@@@std@@@Z; Broker::CKeepAliveEvent::CKeepAliveEvent(_SYSTEMTIME const &,ulong,ulong,_TbiTimeEventModsParameters const *,bool,bool,std::vector<uchar> const &)
0x18000a784  nop
0x18000a785  jmp     loc_18000A916
0x18000a78a  mov     ecx, 158h; Size
0x18000a78f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a794  mov     r10, rax
0x18000a797  mov     [rbp+47h+arg_10], rax
0x18000a79b  movups  xmm0, xmmword ptr [rbx+48h]
0x18000a79f  movdqu  [rbp+47h+var_40], xmm0
0x18000a7a4  cmp     dword ptr [rbx+20h], 0
0x18000a7a8  setnz   cl
0x18000a7ab  lea     r9, [rbx+28h]
0x18000a7af  cmp     dword ptr [rbx+58h], 0
0x18000a7b3  setnz   r8b
0x18000a7b7  lea     rdx, [rbx+8]
0x18000a7bb  lea     rax, [rbp+47h+var_30]
0x18000a7bf  mov     [rsp+0A0h+var_60], rax
0x18000a7c4  mov     byte ptr [rsp+0A0h+var_68], cl
0x18000a7c8  mov     qword ptr [rsp+0A0h+var_70], r9
0x18000a7cd  mov     eax, [rbx+1Ch]
0x18000a7d0  mov     dword ptr [rsp+0A0h+var_78], eax
0x18000a7d4  lea     rax, [rbp+47h+var_40]
0x18000a7d8  mov     qword ptr [rsp+0A0h+var_80], rax
0x18000a7dd  mov     r9d, [rbx+18h]
0x18000a7e1  mov     rcx, r10
0x18000a7e4  call    ??0CAlarmTimeEvent@Broker@@QEAA@AEBU_SYSTEMTIME@@_NKU_TB_IRREGULAR_SCHEDULE@@KPEBU_TbiTimeEventModsParameters@@1AEBV?$vector@EV?$allocator@E@std@@@std@@@Z; Broker::CAlarmTimeEvent::CAlarmTimeEvent(_SYSTEMTIME const &,bool,ulong,_TB_IRREGULAR_SCHEDULE,ulong,_TbiTimeEventModsParameters const *,bool,std::vector<uchar> const &)
0x18000a7e9  nop
0x18000a7ea  jmp     loc_18000A916
0x18000a7ef  mov     ecx, 120h; Size
0x18000a7f4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a7f9  mov     [rbp+47h+arg_10], rax
0x18000a7fd  lea     rcx, [rbx+18h]
0x18000a801  cmp     dword ptr [rbx+14h], 0
0x18000a805  setnz   dl
0x18000a808  lea     r8, [rbp+47h+var_30]
0x18000a80c  mov     [rsp+0A0h+var_60], r8; __int64
0x18000a811  mov     [rsp+0A0h+var_68], rcx; __int64
0x18000a816  mov     cl, [rsi+0B8h]
0x18000a81c  mov     [rsp+0A0h+var_70], cl; char
0x18000a820  mov     [rsp+0A0h+var_78], dl; char
0x18000a824  mov     ecx, [rbx+10h]
0x18000a827  mov     [rsp+0A0h+var_80], ecx; int
0x18000a82b  mov     r9d, [rbx+0Ch]
0x18000a82f  mov     r8d, [rbx+8]
0x18000a833  mov     dl, r14b
0x18000a836  mov     rcx, rax; this
0x18000a839  call    ??0KeepAliveEvent@Broker@@QEAA@_NKKK00PEBU_TbiTimeEventModsParameters@@AEBV?$vector@EV?$allocator@E@std@@@std@@@Z; Broker::KeepAliveEvent::KeepAliveEvent(bool,ulong,ulong,ulong,bool,bool,_TbiTimeEventModsParameters const *,std::vector<uchar> const &)
0x18000a83e  nop
0x18000a83f  jmp     loc_18000A916
0x18000a844  mov     ecx, 138h; Size
0x18000a849  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a84e  mov     [rbp+47h+arg_10], rax
0x18000a852  lea     rdx, [rbx+8]
0x18000a856  lea     rcx, [rbp+47h+var_30]
0x18000a85a  mov     qword ptr [rsp+0A0h+var_78], rcx; __int64
0x18000a85f  mov     ecx, [rbx+20h]
0x18000a862  mov     [rsp+0A0h+var_80], ecx; int
0x18000a866  mov     r9d, [rbx+1Ch]
0x18000a86a  mov     r8d, [rbx+18h]
0x18000a86e  mov     rcx, rax; this
0x18000a871  call    ??0ConvenientTimeEvent@Broker@@QEAA@AEBU_SYSTEMTIME@@KKKAEBV?$vector@EV?$allocator@E@std@@@std@@@Z; Broker::ConvenientTimeEvent::ConvenientTimeEvent(_SYSTEMTIME const &,ulong,ulong,ulong,std::vector<uchar> const &)
0x18000a876  nop
0x18000a877  jmp     loc_18000A916
0x18000a87c  mov     ecx, 130h; Size
0x18000a881  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a886  mov     [rbp+47h+arg_10], rax
0x18000a88a  lea     rcx, [rbx+28h]
0x18000a88e  lea     rdx, [rbx+8]
0x18000a892  lea     r8, [rbp+47h+var_30]
0x18000a896  mov     qword ptr [rsp+0A0h+var_70], r8
0x18000a89b  mov     qword ptr [rsp+0A0h+var_78], rcx
0x18000a8a0  mov     ecx, [rbx+20h]
0x18000a8a3  mov     [rsp+0A0h+var_80], ecx
0x18000a8a7  mov     r9d, [rbx+1Ch]
0x18000a8ab  mov     r8d, [rbx+18h]
0x18000a8af  mov     rcx, rax
0x18000a8b2  call    ??0CalendarTimeEvent@Broker@@QEAA@AEBU_SYSTEMTIME@@KKKPEBU_TbiTimeEventModsParameters@@AEBV?$vector@EV?$allocator@E@std@@@std@@@Z; Broker::CalendarTimeEvent::CalendarTimeEvent(_SYSTEMTIME const &,ulong,ulong,ulong,_TbiTimeEventModsParameters const *,std::vector<uchar> const &)
0x18000a8b7  nop
0x18000a8b8  jmp     short loc_18000A916
0x18000a8ba  mov     ecx, 140h; Size
0x18000a8bf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a8c4  mov     r10, rax
0x18000a8c7  mov     [rbp+47h+arg_10], rax
0x18000a8cb  movups  xmm0, xmmword ptr [rbx+48h]
0x18000a8cf  movdqu  [rbp+47h+var_40], xmm0
0x18000a8d4  lea     rcx, [rbx+28h]
0x18000a8d8  cmp     dword ptr [rbx+58h], 0
0x18000a8dc  setnz   r8b
0x18000a8e0  lea     rdx, [rbx+8]
0x18000a8e4  lea     rax, [rbp+47h+var_30]
0x18000a8e8  mov     [rsp+0A0h+var_60], rax
0x18000a8ed  mov     [rsp+0A0h+var_68], rcx
0x18000a8f2  mov     ecx, [rbx+20h]
0x18000a8f5  mov     dword ptr [rsp+0A0h+var_70], ecx
0x18000a8f9  mov     eax, [rbx+1Ch]
0x18000a8fc  mov     dword ptr [rsp+0A0h+var_78], eax
0x18000a900  lea     rax, [rbp+47h+var_40]
0x18000a904  mov     qword ptr [rsp+0A0h+var_80], rax
0x18000a909  mov     r9d, [rbx+18h]
0x18000a90d  mov     rcx, r10
0x18000a910  call    ??0AlarmTimeEvent@Broker@@QEAA@AEBU_SYSTEMTIME@@_NKU_TB_IRREGULAR_SCHEDULE@@KKPEBU_TbiTimeEventModsParameters@@AEBV?$vector@EV?$allocator@E@std@@@std@@@Z; Broker::AlarmTimeEvent::AlarmTimeEvent(_SYSTEMTIME const &,bool,ulong,_TB_IRREGULAR_SCHEDULE,ulong,ulong,_TbiTimeEventModsParameters const *,std::vector<uchar> const &)
0x18000a915  nop
0x18000a916  mov     [rbp+47h+arg_10], rax
0x18000a91a  lea     rdx, [rbp+47h+arg_10]
0x18000a91e  mov     rcx, rdi
0x18000a921  call    ??$?4U?$default_delete@VTimeEvent@Broker@@@std@@$0A@@?$unique_ptr@VTimeEvent@Broker@@U?$default_delete@VTimeEvent@Broker@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<Broker::TimeEvent>::operator=<std::default_delete<Broker::TimeEvent>,0>(std::unique_ptr<Broker::TimeEvent> &&)
0x18000a926  mov     rdx, [rbp+47h+arg_10]
0x18000a92a  test    rdx, rdx
0x18000a92d  jz      short loc_18000A934
0x18000a92f  call    ??R?$default_delete@VTimeEvent@Broker@@@std@@QEBAXPEAVTimeEvent@Broker@@@Z; std::default_delete<Broker::TimeEvent>::operator()(Broker::TimeEvent *)
0x18000a934  lea     r8, [rbx+74h]; unsigned __int16 *
0x18000a938  mov     rcx, [rdi]
0x18000a93b  add     rcx, 5Eh ; '^'; unsigned __int16 *
0x18000a93f  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18000a944  mov     rdx, [rbp+47h+arg_20]; struct _BROKER *
0x18000a948  test    rdx, rdx
0x18000a94b  jz      short loc_18000A95F
0x18000a94d  mov     r8, [rbp+47h+arg_28]; struct _BROKERED_EVENT *
0x18000a951  test    r8, r8
0x18000a954  jz      short loc_18000A95F
0x18000a956  mov     rcx, [rdi]; this
0x18000a959  call    ?SetEventBrokerContext@TimeEvent@Broker@@QEAAXPEAU_BROKER@@PEAU_BROKERED_EVENT@@@Z; Broker::TimeEvent::SetEventBrokerContext(_BROKER *,_BROKERED_EVENT *)
0x18000a95e  nop
0x18000a95f  lea     rcx, [rbp+47h+var_30]
0x18000a963  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18000a968  mov     rax, rdi
0x18000a96b  lea     r11, [rsp+0A0h+var_10]
0x18000a973  mov     rbx, [r11+20h]
0x18000a977  mov     rsi, [r11+38h]
0x18000a97b  mov     rsp, r11
0x18000a97e  pop     r14
0x18000a980  pop     rdi
0x18000a981  pop     rbp
0x18000a982  retn
```
