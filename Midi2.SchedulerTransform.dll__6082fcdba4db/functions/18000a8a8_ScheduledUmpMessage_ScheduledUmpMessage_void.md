# ScheduledUmpMessage::~ScheduledUmpMessage(void)

- ea: `0x18000a8a8`
- end: `0x18000a8b1`
- name: `??1ScheduledUmpMessage@@QEAA@XZ`
- size: `9`
- prototype: `void __fastcall(ScheduledUmpMessage *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18000cf01`
- `0x18000d089`

## callees

- `0x18000a83c`

## pseudocode

```c
void __fastcall ScheduledUmpMessage::~ScheduledUmpMessage(ScheduledUmpMessage *this)
{
  std::vector<unsigned char>::~vector<unsigned char>((char *)this + 16);
}

```

## disassembly

```asm
0x18000a8a8  add     rcx, 10h
0x18000a8ac  jmp     ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
```
