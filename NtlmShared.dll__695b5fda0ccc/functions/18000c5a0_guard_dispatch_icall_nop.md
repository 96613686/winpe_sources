# _guard_dispatch_icall_nop

- ea: `0x18000c5a0`
- end: `0x18000c5a2`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180001364`
- `0x1800015a8`
- `0x18000c5d0`
- `0x18000c660`

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
0x18000c5a0  jmp     rax
```
