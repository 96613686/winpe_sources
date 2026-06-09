# int `Concurrency::task_completion_event<std::pair<uchar,Concurrency::details::_CancellationTokenState *>>::set(std::pair<uchar,Concurrency::details::_CancellationTokenState *>)'::`1'::dtor$0

- ea: `0x18002f35f`
- end: `0x18002f36b`
- name: `?dtor$0@?0??set@?$task_completion_event@U?$pair@EPEAV_CancellationTokenState@details@Concurrency@@@std@@@Concurrency@@QEBA_NU?$pair@EPEAV_CancellationTokenState@details@Concurrency@@@std@@@Z@4HA`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003ef0`

## pseudocode

```c
__int64 __fastcall `Concurrency::task_completion_event<std::pair<unsigned char,Concurrency::details::_CancellationTokenState *>>::set'::`1'::dtor$0(
        __int64 a1,
        __int64 a2)
{
  return sub_180003EF0((_QWORD *)(a2 + 96));
}

```

## disassembly

```asm
0x18002f35f  lea     rcx, [rdx+60h]
0x18002f366  jmp     sub_180003EF0
```
