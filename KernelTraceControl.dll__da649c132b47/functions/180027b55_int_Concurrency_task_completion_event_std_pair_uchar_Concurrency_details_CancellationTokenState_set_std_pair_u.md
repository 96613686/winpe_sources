# int `Concurrency::task_completion_event<std::pair<uchar,Concurrency::details::_CancellationTokenState *>>::set(std::pair<uchar,Concurrency::details::_CancellationTokenState *>)'::`1'::dtor$0

- ea: `0x180027b55`
- end: `0x180027b61`
- name: `?dtor$0@?0??set@?$task_completion_event@U?$pair@EPEAV_CancellationTokenState@details@Concurrency@@@std@@@Concurrency@@QEBA_NU?$pair@EPEAV_CancellationTokenState@details@Concurrency@@@std@@@Z@4HA`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001d00`

## pseudocode

```c
void __fastcall `Concurrency::task_completion_event<std::pair<unsigned char,Concurrency::details::_CancellationTokenState *>>::set'::`1'::dtor$0(
        __int64 a1,
        __int64 a2)
{
  ATL::CHeapPtr<_TRACE_EVENT_INFO,ATL::CCRTAllocator>::~CHeapPtr<_TRACE_EVENT_INFO,ATL::CCRTAllocator>((void *)(a2 + 80));
}

```

## disassembly

```asm
0x180027b55  lea     rcx, [rdx+50h]; void *
0x180027b5c  jmp     ??1?$CHeapPtr@U_TRACE_EVENT_INFO@@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ
```
