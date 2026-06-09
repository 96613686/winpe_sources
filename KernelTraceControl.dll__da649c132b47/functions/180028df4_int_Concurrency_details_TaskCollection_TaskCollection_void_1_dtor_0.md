# int `Concurrency::details::_TaskCollection::~_TaskCollection(void)'::`1'::dtor$0

- ea: `0x180028df4`
- end: `0x180028e04`
- name: `?dtor$0@?0???1_TaskCollection@details@Concurrency@@QEAA@XZ@4HA`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180017ab8`

## pseudocode

```c
void __fastcall `Concurrency::details::_TaskCollection::~_TaskCollection'::`1'::dtor$0(__int64 a1, __int64 a2)
{
  Microsoft::Windows::Performance::CTraceEventInfoDelocalizer::~CTraceEventInfoDelocalizer((Microsoft::Windows::Performance::CTraceEventInfoDelocalizer *)(*(_QWORD *)(a2 + 80) + 96LL));
}

```

## disassembly

```asm
0x180028df4  mov     rcx, [rdx+50h]
0x180028dfb  add     rcx, 60h ; '`'; this
0x180028dff  jmp     ??1CTraceEventInfoDelocalizer@Performance@Windows@Microsoft@@QEAA@XZ
```
