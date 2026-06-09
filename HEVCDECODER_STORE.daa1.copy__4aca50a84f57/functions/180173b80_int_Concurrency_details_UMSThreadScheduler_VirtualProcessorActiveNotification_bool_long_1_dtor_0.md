# int `Concurrency::details::UMSThreadScheduler::VirtualProcessorActiveNotification(bool,long)'::`1'::dtor$0

- ea: `0x180173b80`
- end: `0x180173b8c`
- name: `?dtor$0@?0??VirtualProcessorActiveNotification@UMSThreadScheduler@details@Concurrency@@MEAAX_NJ@Z@4HA`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18002b270`
- `0x180173b80`

## pseudocode

```c
void __fastcall `Concurrency::details::UMSThreadScheduler::VirtualProcessorActiveNotification'::`1'::dtor$0(
        __int64 a1,
        __int64 a2)
{
  _QWORD *v2; // rcx

  v2 = *(_QWORD **)(a2 + 136);
  *v2 = off_1801795C8;
  sub_18002B270((__int64)v2, a2);
}

```

## disassembly

```asm
0x180173b80  mov     rcx, [rdx+88h]
0x180173b87  jmp     loc_1800104D0
0x1800104d0  lea     rax, off_1801795C8
0x1800104d7  mov     [rcx], rax
0x1800104da  jmp     sub_18002B270
```
