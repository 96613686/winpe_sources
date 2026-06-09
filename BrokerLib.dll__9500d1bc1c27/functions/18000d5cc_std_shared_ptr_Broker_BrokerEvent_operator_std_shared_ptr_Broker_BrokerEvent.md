# std::shared_ptr<Broker::BrokerEvent>::operator=(std::shared_ptr<Broker::BrokerEvent> &&)

- ea: `0x18000d5cc`
- end: `0x18000d609`
- name: `??4?$shared_ptr@VBrokerEvent@Broker@@@std@@QEAAAEAV01@$$QEAV01@@Z`
- size: `61`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000d2a8`
- `0x18000f42c`
- `0x180017a9c`
- `0x180018004`
- `0x1800187b8`

## callees

- `0x180004ae0`
- `0x18000d5cc`

## pseudocode

```c
_QWORD *__fastcall std::shared_ptr<Broker::BrokerEvent>::operator=(_QWORD *a1, __int64 *a2)
{
  __int64 v2; // rax
  __int64 v4; // r8
  std::_Ref_count_base *v5; // rcx

  v2 = *a2;
  v4 = a2[1];
  *a2 = 0;
  a2[1] = 0;
  *a1 = v2;
  v5 = (std::_Ref_count_base *)a1[1];
  a1[1] = v4;
  if ( v5 )
    std::_Ref_count_base::_Decref(v5);
  return a1;
}

```

## disassembly

```asm
0x18000d5cc  push    rbx
0x18000d5ce  sub     rsp, 20h
0x18000d5d2  mov     rax, [rdx]
0x18000d5d5  mov     rbx, rcx
0x18000d5d8  mov     r8, [rdx+8]
0x18000d5dc  mov     qword ptr [rdx], 0
0x18000d5e3  mov     qword ptr [rdx+8], 0
0x18000d5eb  mov     [rcx], rax
0x18000d5ee  mov     rcx, [rcx+8]; this
0x18000d5f2  mov     [rbx+8], r8
0x18000d5f6  test    rcx, rcx
0x18000d5f9  jz      short loc_18000D600
0x18000d5fb  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000d600  mov     rax, rbx
0x18000d603  add     rsp, 20h
0x18000d607  pop     rbx
0x18000d608  retn
```
