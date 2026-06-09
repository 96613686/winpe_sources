# Broker::TimeBroker::DestroyEvent(std::shared_ptr<Broker::TimeEvent>)

- ea: `0x18000874c`
- end: `0x1800087c8`
- name: `?DestroyEvent@TimeBroker@Broker@@AEAAXV?$shared_ptr@VTimeEvent@Broker@@@std@@@Z`
- size: `124`
- prototype: `void __fastcall(Broker::TimeBroker *this, Broker::TimeEvent **)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000fe70`
- `0x18001bd50`

## callees

- `0x180005b30`
- `0x1800074c0`
- `0x18000874c`
- `0x1800087d0`
- `0x180009670`

## pseudocode

```c
void __fastcall Broker::TimeBroker::DestroyEvent(Broker::TimeBroker *this, Broker::TimeEvent **a2)
{
  Broker::TimeEvent *v4; // rax
  std::_Ref_count_base *v5; // rcx

  Broker::TimeEvent::OnDelete(*a2);
  Broker::TimeEvent::OnDisable(*a2);
  v4 = a2[1];
  if ( v4 )
    _InterlockedIncrement((volatile signed __int32 *)v4 + 2);
  Broker::TimeBroker::RemoveFromTimerWheel(this);
  v5 = a2[1];
  if ( v5 )
    std::_Ref_count_base::_Decref(v5);
}

```

## disassembly

```asm
0x18000874c  mov     [rsp+arg_0], rbx
0x180008751  mov     [rsp+arg_8], rdx
0x180008756  push    rdi
0x180008757  sub     rsp, 40h
0x18000875b  mov     rbx, rdx
0x18000875e  mov     rdi, rcx
0x180008761  xorps   xmm0, xmm0
0x180008764  movdqu  [rsp+48h+var_18], xmm0
0x18000876a  mov     rcx, [rdx]; this
0x18000876d  call    ?OnDelete@TimeEvent@Broker@@QEAAXXZ; Broker::TimeEvent::OnDelete(void)
0x180008772  mov     rcx, [rbx]; this
0x180008775  call    ?OnDisable@TimeEvent@Broker@@QEAAXXZ; Broker::TimeEvent::OnDisable(void)
0x18000877a  xorps   xmm0, xmm0
0x18000877d  movdqu  [rsp+48h+var_28], xmm0
0x180008783  mov     rax, [rbx+8]
0x180008787  test    rax, rax
0x18000878a  jz      short loc_180008790
0x18000878c  lock inc dword ptr [rax+8]
0x180008790  mov     rax, [rbx]
0x180008793  mov     qword ptr [rsp+48h+var_28], rax
0x180008798  mov     rax, [rbx+8]
0x18000879c  mov     qword ptr [rsp+48h+var_28+8], rax
0x1800087a1  lea     rdx, [rsp+48h+var_28]
0x1800087a6  mov     rcx, rdi; this
0x1800087a9  call    ?RemoveFromTimerWheel@TimeBroker@Broker@@AEAAXV?$shared_ptr@VTimeEvent@Broker@@@std@@@Z; Broker::TimeBroker::RemoveFromTimerWheel(std::shared_ptr<Broker::TimeEvent>)
0x1800087ae  nop
0x1800087af  mov     rcx, [rbx+8]; this
0x1800087b3  test    rcx, rcx
0x1800087b6  jz      short loc_1800087BD
0x1800087b8  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800087bd  mov     rbx, [rsp+48h+arg_0]
0x1800087c2  add     rsp, 40h
0x1800087c6  pop     rdi
0x1800087c7  retn
```
