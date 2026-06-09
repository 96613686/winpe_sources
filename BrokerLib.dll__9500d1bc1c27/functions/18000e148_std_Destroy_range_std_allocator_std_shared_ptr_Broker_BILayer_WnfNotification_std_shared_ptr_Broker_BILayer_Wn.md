# std::_Destroy_range<std::allocator<std::shared_ptr<Broker::BILayer::WnfNotification>>>(std::shared_ptr<Broker::BILayer::WnfNotification> *,std::shared_ptr<Broker::BILayer::WnfNotification> * const,std::allocator<std::shared_ptr<Broker::BILayer::WnfNotification>> &)

- ea: `0x18000e148`
- end: `0x18000e17f`
- name: `??$_Destroy_range@V?$allocator@V?$shared_ptr@VWnfNotification@BILayer@Broker@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@VWnfNotification@BILayer@Broker@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@VWnfNotification@BILayer@Broker@@@std@@@0@@Z`
- size: `55`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000d2a8`
- `0x18000e360`
- `0x18001402c`
- `0x180014138`
- `0x180014dc8`

## callees

- `0x180004ae0`
- `0x18000e148`

## pseudocode

```c
void __fastcall std::_Destroy_range<std::allocator<std::shared_ptr<Broker::BILayer::WnfNotification>>>(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rbx
  std::_Ref_count_base *v4; // rcx

  if ( a1 != a2 )
  {
    v3 = a1;
    do
    {
      v4 = *(std::_Ref_count_base **)(v3 + 8);
      if ( v4 )
        std::_Ref_count_base::_Decref(v4);
      v3 += 16;
    }
    while ( v3 != a2 );
  }
}

```

## disassembly

```asm
0x18000e148  cmp     rcx, rdx
0x18000e14b  jz      short locret_18000E17E
0x18000e14d  mov     [rsp+arg_0], rbx
0x18000e152  push    rdi
0x18000e153  sub     rsp, 20h
0x18000e157  mov     rdi, rdx
0x18000e15a  mov     rbx, rcx
0x18000e15d  mov     rcx, [rbx+8]; this
0x18000e161  test    rcx, rcx
0x18000e164  jz      short loc_18000E16B
0x18000e166  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000e16b  add     rbx, 10h
0x18000e16f  cmp     rbx, rdi
0x18000e172  jnz     short loc_18000E15D
0x18000e174  mov     rbx, [rsp+28h+arg_0]
0x18000e179  add     rsp, 20h
0x18000e17d  pop     rdi
0x18000e17e  retn
```
