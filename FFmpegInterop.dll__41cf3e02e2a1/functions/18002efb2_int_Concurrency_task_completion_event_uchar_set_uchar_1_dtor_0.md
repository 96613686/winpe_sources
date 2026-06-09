# int `Concurrency::task_completion_event<uchar>::set(uchar)'::`1'::dtor$0

- ea: `0x18002efb2`
- end: `0x18002efbe`
- name: `?dtor$0@?0??set@?$task_completion_event@E@Concurrency@@QEBA_NE@Z@4HA`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002f94`

## pseudocode

```c
__int64 __fastcall `Concurrency::task_completion_event<unsigned char>::set'::`1'::dtor$0(__int64 a1, __int64 a2)
{
  return sub_180002F94(a2 + 72);
}

```

## disassembly

```asm
0x18002efb2  lea     rcx, [rdx+48h]
0x18002efb9  jmp     sub_180002F94
```
