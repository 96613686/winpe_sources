# int `Concurrency::task_completion_event<uchar>::set(uchar)'::`1'::dtor$1

- ea: `0x18002efbe`
- end: `0x18002efca`
- name: `?dtor$1@?0??set@?$task_completion_event@E@Concurrency@@QEBA_NE@Z@4HA`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003ef0`

## pseudocode

```c
__int64 __fastcall `Concurrency::task_completion_event<unsigned char>::set'::`1'::dtor$1(__int64 a1, __int64 a2)
{
  return sub_180003EF0((_QWORD *)(a2 + 96));
}

```

## disassembly

```asm
0x18002efbe  lea     rcx, [rdx+60h]
0x18002efc5  jmp     sub_180003EF0
```
