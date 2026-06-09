# _guard_dispatch_icall_nop

- ea: `0x1800043b0`
- end: `0x1800043b2`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `14`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180001050`
- `0x18000120c`
- `0x1800016f4`
- `0x180001ba0`
- `0x1800022a0`
- `0x18000291c`
- `0x1800032e0`
- `0x18000347c`
- `0x1800037b0`
- `0x1800037f4`
- `0x180003b30`
- `0x180003f44`
- `0x180003f80`
- `0x1800043d0`

## pseudocode

```c
__int64 __fastcall guard_dispatch_icall_nop()
{
  __int64 (*v0)(void); // rax

  return v0();
}

```

## disassembly

```asm
0x1800043b0  jmp     rax
```
