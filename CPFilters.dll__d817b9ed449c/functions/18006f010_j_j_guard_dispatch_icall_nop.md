# j_j__guard_dispatch_icall_nop

- ea: `0x18006f010`
- end: `0x18006f015`
- name: `j_j__guard_dispatch_icall_nop`
- size: `5`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180001f98`
- `0x180002124`
- `0x1800022e0`
- `0x180002350`
- `0x180002488`
- `0x180002a34`
- `0x180002a7c`
- `0x180002ae0`
- `0x180002be8`
- `0x180002c2c`

## callees

- `0x18006cca0`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall j_j__guard_dispatch_icall_nop()
{
  __int64 (*v0)(void); // rax

  return v0();
}

```

## disassembly

```asm
0x18006f010  jmp     j__guard_dispatch_icall_nop
```
