# int `Concurrency::details::UMSThreadScheduler::VirtualProcessorActiveNotification(bool,long)'::`1'::dtor$0

- ea: `0x18002fd70`
- end: `0x18002fd7c`
- name: `?dtor$0@?0??VirtualProcessorActiveNotification@UMSThreadScheduler@details@Concurrency@@MEAAX_NJ@Z@4HA`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180004c90`

## pseudocode

```c
__int64 __fastcall `Concurrency::details::UMSThreadScheduler::VirtualProcessorActiveNotification'::`1'::dtor$0(
        __int64 a1,
        __int64 a2)
{
  return sub_180004C90(*(_QWORD *)(a2 + 136));
}

```

## disassembly

```asm
0x18002fd70  mov     rcx, [rdx+88h]
0x18002fd77  jmp     sub_180004C90
```
