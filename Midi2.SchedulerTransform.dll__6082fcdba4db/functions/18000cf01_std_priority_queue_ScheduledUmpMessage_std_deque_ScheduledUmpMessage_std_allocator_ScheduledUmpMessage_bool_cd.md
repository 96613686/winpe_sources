# _std::priority_queue_ScheduledUmpMessage_std::deque_ScheduledUmpMessage_std::allocator_ScheduledUmpMessage____bool_(__cdecl_)(ScheduledUmpMessage_&_ScheduledUmpMessage_&)_::emplace___int64_&_std::atomic_unsigned_int__&_unsigned_int_&_unsigned_char____::_1_::dtor$1

- ea: `0x18000cf01`
- end: `0x18000cf0d`
- name: `_std::priority_queue_ScheduledUmpMessage_std::deque_ScheduledUmpMessage_std::allocator_ScheduledUmpMessage____bool_(__cdecl_)(ScheduledUmpMessage_&_ScheduledUmpMessage_&)_::emplace___int64_&_std::atomic_unsigned_int__&_unsigned_int_&_unsigned_char____::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000a8a8`

## pseudocode

```c
void __fastcall std::priority_queue_ScheduledUmpMessage_std::deque_ScheduledUmpMessage_std::allocator_ScheduledUmpMessage____bool____cdecl___ScheduledUmpMessage___ScheduledUmpMessage____::emplace___int64___std::atomic_unsigned_int____unsigned_int___unsigned_char____::_1_::dtor_1(
        __int64 a1,
        __int64 a2)
{
  ScheduledUmpMessage::~ScheduledUmpMessage((ScheduledUmpMessage *)(a2 + 64));
}

```

## disassembly

```asm
0x18000cf01  lea     rcx, [rdx+40h]; this
0x18000cf08  jmp     ??1ScheduledUmpMessage@@QEAA@XZ; ScheduledUmpMessage::~ScheduledUmpMessage(void)
```
