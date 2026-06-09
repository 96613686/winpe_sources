# TimeBrokerOnResumeFromSleepCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x180011280`
- end: `0x1800112cf`
- name: `?TimeBrokerOnResumeFromSleepCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `79`
- prototype: `void __fastcall(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WORK *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180001ba4`
- `0x180005b30`
- `0x180011280`

## pseudocode

```c
void __fastcall TimeBrokerOnResumeFromSleepCallback(struct _TP_CALLBACK_INSTANCE *a1, void *a2, struct _TP_WORK *a3)
{
  std::_Ref_count_base *v3; // rbx

  v3 = *(&Broker::TimeBroker::Instance + 1);
  if ( *(&Broker::TimeBroker::Instance + 1) )
  {
    _InterlockedIncrement((volatile signed __int32 *)*(&Broker::TimeBroker::Instance + 1) + 2);
    v3 = *(&Broker::TimeBroker::Instance + 1);
  }
  if ( Broker::TimeBroker::Instance )
    Broker::TimeBroker::OnResumeFromSleep(Broker::TimeBroker::Instance);
  if ( v3 )
    std::_Ref_count_base::_Decref(v3);
}

```

## disassembly

```asm
0x180011280  push    rbx
0x180011282  sub     rsp, 30h
0x180011286  mov     rbx, qword ptr cs:?Instance@TimeBroker@Broker@@0V?$shared_ptr@VTimeBroker@Broker@@@std@@A+8; std::shared_ptr<Broker::TimeBroker> Broker::TimeBroker::Instance
0x18001128d  test    rbx, rbx
0x180011290  jz      short loc_18001129D
0x180011292  lock inc dword ptr [rbx+8]
0x180011296  mov     rbx, qword ptr cs:?Instance@TimeBroker@Broker@@0V?$shared_ptr@VTimeBroker@Broker@@@std@@A+8; std::shared_ptr<Broker::TimeBroker> Broker::TimeBroker::Instance
0x18001129d  mov     rcx, qword ptr cs:?Instance@TimeBroker@Broker@@0V?$shared_ptr@VTimeBroker@Broker@@@std@@A; this
0x1800112a4  mov     [rsp+38h+var_18], rcx
0x1800112a9  mov     [rsp+38h+var_10], rbx
0x1800112ae  test    rcx, rcx
0x1800112b1  jnz     short loc_1800112C6
0x1800112b3  test    rbx, rbx
0x1800112b6  jz      short loc_1800112C0
0x1800112b8  mov     rcx, rbx; this
0x1800112bb  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800112c0  add     rsp, 30h
0x1800112c4  pop     rbx
0x1800112c5  retn
0x1800112c6  call    ?OnResumeFromSleep@TimeBroker@Broker@@QEAAXXZ; Broker::TimeBroker::OnResumeFromSleep(void)
0x1800112cb  nop
0x1800112cc  jmp     short loc_1800112B3
```
