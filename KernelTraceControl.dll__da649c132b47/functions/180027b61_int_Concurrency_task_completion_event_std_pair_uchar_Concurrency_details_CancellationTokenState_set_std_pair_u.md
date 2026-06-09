# int `Concurrency::task_completion_event<std::pair<uchar,Concurrency::details::_CancellationTokenState *>>::set(std::pair<uchar,Concurrency::details::_CancellationTokenState *>)'::`1'::dtor$1

- ea: `0x180027b61`
- end: `0x180027b6d`
- name: `?dtor$1@?0??set@?$task_completion_event@U?$pair@EPEAV_CancellationTokenState@details@Concurrency@@@std@@@Concurrency@@QEBA_NU?$pair@EPEAV_CancellationTokenState@details@Concurrency@@@std@@@Z@4HA`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003764`

## pseudocode

```c
void __fastcall `Concurrency::task_completion_event<std::pair<unsigned char,Concurrency::details::_CancellationTokenState *>>::set'::`1'::dtor$1(
        __int64 a1,
        __int64 a2)
{
  Microsoft::Windows::Performance::CEtwTraceHandleGroup::~CEtwTraceHandleGroup((Microsoft::Windows::Performance::CEtwTraceHandleGroup *)(a2 + 104));
}

```

## disassembly

```asm
0x180027b61  lea     rcx, [rdx+68h]; this
0x180027b68  jmp     ??1CEtwTraceHandleGroup@Performance@Windows@Microsoft@@QEAA@XZ
```
