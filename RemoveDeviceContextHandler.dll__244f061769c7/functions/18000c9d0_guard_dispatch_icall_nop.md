# _guard_dispatch_icall_nop

- ea: `0x18000c9d0`
- end: `0x18000c9d2`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180001c90`
- `0x180001f04`
- `0x180002118`
- `0x18000ca00`
- `0x18000ca90`

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
0x18000c9d0  jmp     rax
```
