# _guard_dispatch_icall_nop

- ea: `0x1400043d0`
- end: `0x1400043d2`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x140001ad8`
- `0x140001d9c`
- `0x1400043a0`
- `0x140004400`

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
0x1400043d0  jmp     rax
```
