# DeviceServicesBrokerTerminate

- ea: `0x180021874`
- end: `0x1800218ad`
- name: `DeviceServicesBrokerTerminate`
- size: `57`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001a830`
- `0x18001db70`
- `0x180021840`

## callees

- `0x1800076a0`
- `0x180021874`

## pseudocode

```c
__int64 DeviceServicesBrokerTerminate()
{
  std::_Ref_count_base *v0; // rcx

  Broker::DsBroker::Instance = 0;
  v0 = qword_180036F20;
  qword_180036F20 = 0;
  if ( v0 )
    std::_Ref_count_base::_Decref(v0);
  return 0;
}

```

## disassembly

```asm
0x180021874  sub     rsp, 58h
0x180021878  xor     eax, eax
0x18002187a  mov     [rsp+58h+arg_0], eax
0x18002187e  mov     cs:?Instance@DsBroker@Broker@@0V?$shared_ptr@VDsBroker@Broker@@@std@@A, rax; std::shared_ptr<Broker::DsBroker> Broker::DsBroker::Instance
0x180021885  mov     rcx, cs:qword_180036F20; this
0x18002188c  mov     cs:qword_180036F20, rax
0x180021893  test    rcx, rcx
0x180021896  jz      short loc_18002189E
0x180021898  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002189d  nop
0x18002189e  jmp     short loc_1800218A4
0x1800218a0  jmp     short loc_1800218A4
0x1800218a2  jmp     short $+2
0x1800218a4  mov     eax, [rsp+58h+arg_0]
0x1800218a8  add     rsp, 58h
0x1800218ac  retn
```
