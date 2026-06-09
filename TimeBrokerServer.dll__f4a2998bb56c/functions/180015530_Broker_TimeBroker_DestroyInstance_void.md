# Broker::TimeBroker::DestroyInstance(void)

- ea: `0x180015530`
- end: `0x180015619`
- name: `?DestroyInstance@TimeBroker@Broker@@SAXXZ`
- size: `233`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180013b40`

## callees

- `0x180003840`
- `0x180005b30`
- `0x180015530`

## import_xrefs

- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x180015586`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x180015586`
- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x1800155f0`
- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x1800155f0`
- `BrokerLib!BrDeleteBrokerInstance` at `0x1800155a6`
- `BrokerLib!BrDeleteBrokerInstance` at `0x1800155a6`

## pseudocode

```c
void Broker::TimeBroker::DestroyInstance(void)
{
  Broker::TimeBroker *v0; // rdi
  PVOID *v1; // rbx
  void *v2; // rcx
  std::_Ref_count_base *v3; // rcx
  TRACEHANDLE v4; // rcx

  v0 = Broker::TimeBroker::Instance;
  v1 = (PVOID *)WPP_GLOBAL_Control;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids);
    v1 = (PVOID *)WPP_GLOBAL_Control;
  }
  v2 = (void *)*((_QWORD *)v0 + 22);
  if ( v2 )
  {
    PowerSettingUnregisterNotification(v2);
    v1 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( *((_QWORD *)Broker::TimeBroker::Instance + 24) )
  {
    BrDeleteBrokerInstance();
    v1 = (PVOID *)WPP_GLOBAL_Control;
  }
  v3 = *(&Broker::TimeBroker::Instance + 1);
  *(_OWORD *)&Broker::TimeBroker::Instance = 0u;
  if ( v3 )
  {
    std::_Ref_count_base::_Decref(v3);
    v1 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v1 != &WPP_GLOBAL_Control )
  {
    while ( v1 )
    {
      v4 = (TRACEHANDLE)v1[1];
      if ( v4 )
      {
        UnregisterTraceGuids(v4);
        v1[1] = 0;
      }
      v1 = (PVOID *)*v1;
    }
    WPP_GLOBAL_Control = &WPP_GLOBAL_Control;
  }
}

```

## disassembly

```asm
0x180015530  mov     [rsp+arg_0], rbx
0x180015535  mov     [rsp+arg_8], rsi
0x18001553a  push    rdi
0x18001553b  sub     rsp, 20h
0x18001553f  mov     rdi, qword ptr cs:?Instance@TimeBroker@Broker@@0V?$shared_ptr@VTimeBroker@Broker@@@std@@A; std::shared_ptr<Broker::TimeBroker> Broker::TimeBroker::Instance
0x180015546  mov     rbx, cs:WPP_GLOBAL_Control
0x18001554d  test    dword ptr [rbx+1Ch], 100h
0x180015554  jz      short loc_180015578
0x180015556  cmp     byte ptr [rbx+19h], 4
0x18001555a  jb      short loc_180015578
0x18001555c  mov     rcx, [rbx+10h]
0x180015560  lea     r8, WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids
0x180015567  mov     edx, 16h
0x18001556c  call    WPP_SF_
0x180015571  mov     rbx, cs:WPP_GLOBAL_Control
0x180015578  mov     rcx, [rdi+0B0h]; RegistrationHandle
0x18001557f  xor     edi, edi
0x180015581  test    rcx, rcx
0x180015584  jz      short loc_180015593
0x180015586  call    cs:__imp_PowerSettingUnregisterNotification
0x18001558c  mov     rbx, cs:WPP_GLOBAL_Control
0x180015593  mov     rax, qword ptr cs:?Instance@TimeBroker@Broker@@0V?$shared_ptr@VTimeBroker@Broker@@@std@@A; std::shared_ptr<Broker::TimeBroker> Broker::TimeBroker::Instance
0x18001559a  mov     rcx, [rax+0C0h]
0x1800155a1  test    rcx, rcx
0x1800155a4  jz      short loc_1800155B3
0x1800155a6  call    cs:__imp_BrDeleteBrokerInstance
0x1800155ac  mov     rbx, cs:WPP_GLOBAL_Control
0x1800155b3  mov     rcx, qword ptr cs:?Instance@TimeBroker@Broker@@0V?$shared_ptr@VTimeBroker@Broker@@@std@@A+8; this
0x1800155ba  mov     qword ptr cs:?Instance@TimeBroker@Broker@@0V?$shared_ptr@VTimeBroker@Broker@@@std@@A, rdi; std::shared_ptr<Broker::TimeBroker> Broker::TimeBroker::Instance
0x1800155c1  mov     qword ptr cs:?Instance@TimeBroker@Broker@@0V?$shared_ptr@VTimeBroker@Broker@@@std@@A+8, rdi; std::shared_ptr<Broker::TimeBroker> Broker::TimeBroker::Instance
0x1800155c8  test    rcx, rcx
0x1800155cb  jz      short loc_1800155D9
0x1800155cd  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800155d2  mov     rbx, cs:WPP_GLOBAL_Control
0x1800155d9  lea     rsi, WPP_GLOBAL_Control
0x1800155e0  cmp     rbx, rsi
0x1800155e3  jz      short loc_180015609
0x1800155e5  jmp     short loc_1800155FD
0x1800155e7  mov     rcx, [rbx+8]; RegistrationHandle
0x1800155eb  test    rcx, rcx
0x1800155ee  jz      short loc_1800155FA
0x1800155f0  call    cs:__imp_UnregisterTraceGuids
0x1800155f6  mov     [rbx+8], rdi
0x1800155fa  mov     rbx, [rbx]
0x1800155fd  test    rbx, rbx
0x180015600  jnz     short loc_1800155E7
0x180015602  mov     cs:WPP_GLOBAL_Control, rsi
0x180015609  mov     rbx, [rsp+28h+arg_0]
0x18001560e  mov     rsi, [rsp+28h+arg_8]
0x180015613  add     rsp, 20h
0x180015617  pop     rdi
0x180015618  retn
```
