# _Broker::TimeBroker::SignalEvent_::_1_::catch$9

- ea: `0x18001bd50`
- end: `0x18001bdb5`
- name: `_Broker::TimeBroker::SignalEvent_::_1_::catch$9`
- size: `101`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18000874c`
- `0x18000b990`
- `0x180013882`
- `0x180016190`
- `0x18001bd50`

## pseudocode

```c
__int64 __fastcall Broker::TimeBroker::SignalEvent_::_1_::catch_9(
        __int64 a1,
        __int64 a2,
        int a3,
        void (*a4)(void *, unsigned int, unsigned int))
{
  Broker::TimeEvent **v5; // rdx

  if ( *(_DWORD *)(a2 + 136) == -1073741275 )
  {
    v5 = (Broker::TimeEvent **)std::shared_ptr<Broker::TimeEvent>::shared_ptr<Broker::TimeEvent>(
                                 (_QWORD *)(a2 + 88),
                                 *(_QWORD **)(a2 + 80));
    Broker::TimeBroker::DestroyEvent(*(Broker::TimeBroker **)(a2 + 72), v5);
  }
  else
  {
    Broker::TimeBroker::SubmitLowMemoryWorker(*(Broker::TimeBroker **)(a2 + 72), a2, a3, a4);
  }
  *(_QWORD *)(a2 + 104) = &std::exception::`vftable';
  o___std_exception_destroy_0(a2 + 112);
  return 0;
}

```

## disassembly

```asm
0x18001bd50  mov     [rsp+arg_8], rdx
0x18001bd55  push    rbp
0x18001bd56  sub     rsp, 30h
0x18001bd5a  mov     rbp, rdx
0x18001bd5d  cmp     dword ptr [rbp+88h], 0C0000225h
0x18001bd67  jnz     short loc_18001BD85
0x18001bd69  mov     rdx, [rbp+50h]
0x18001bd6d  lea     rcx, [rbp+58h]
0x18001bd71  call    ??0?$shared_ptr@VTimeEvent@Broker@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Broker::TimeEvent>::shared_ptr<Broker::TimeEvent>(std::shared_ptr<Broker::TimeEvent> const &)
0x18001bd76  mov     rdx, rax
0x18001bd79  mov     rcx, [rbp+48h]; this
0x18001bd7d  call    ?DestroyEvent@TimeBroker@Broker@@AEAAXV?$shared_ptr@VTimeEvent@Broker@@@std@@@Z; Broker::TimeBroker::DestroyEvent(std::shared_ptr<Broker::TimeEvent>)
0x18001bd82  nop
0x18001bd83  jmp     short loc_18001BD8F
0x18001bd85  mov     rcx, [rbp+48h]; this
0x18001bd89  call    ?SubmitLowMemoryWorker@TimeBroker@Broker@@AEAAXXZ; Broker::TimeBroker::SubmitLowMemoryWorker(void)
0x18001bd8e  nop
0x18001bd8f  lea     rax, ??_7exception@std@@6B@; const std::exception::`vftable'
0x18001bd96  mov     [rbp+68h], rax
0x18001bd9a  lea     rcx, [rbp+70h]
0x18001bd9e  call    _o___std_exception_destroy_0
0x18001bda3  nop
0x18001bda4  mov     rax, 0
0x18001bdae  add     rsp, 30h
0x18001bdb2  pop     rbp
0x18001bdb3  retn
```
