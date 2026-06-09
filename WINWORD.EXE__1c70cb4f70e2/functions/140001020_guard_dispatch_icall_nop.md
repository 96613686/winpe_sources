# _guard_dispatch_icall_nop

- ea: `0x140001020`
- end: `0x140001022`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `17`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x140001030`
- `0x1400011a0`
- `0x1400018dc`
- `0x140001fc0`
- `0x14000202c`
- `0x140002404`
- `0x140002440`
- `0x140002810`
- `0x1400028fc`
- `0x140002c84`
- `0x140002d30`
- `0x140004244`
- `0x1400044b0`
- `0x1400045d0`
- `0x140004870`
- `0x140004890`
- `0x1400048b0`

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
0x140001020  jmp     rax
```
