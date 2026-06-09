# _guard_dispatch_icall_nop

- ea: `0x140006bd0`
- end: `0x140006bd2`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x1400012c0`
- `0x140001580`
- `0x140006c00`
- `0x140006c90`

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
0x140006bd0  jmp     rax
```
