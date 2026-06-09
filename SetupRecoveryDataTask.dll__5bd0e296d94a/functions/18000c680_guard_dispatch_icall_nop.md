# _guard_dispatch_icall_nop

- ea: `0x18000c680`
- end: `0x18000c682`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x1800016d0`
- `0x180001944`
- `0x180001b78`
- `0x18000c650`
- `0x18000c6b0`

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
0x18000c680  jmp     rax
```
