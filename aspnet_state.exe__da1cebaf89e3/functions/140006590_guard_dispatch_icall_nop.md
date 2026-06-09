# _guard_dispatch_icall_nop

- ea: `0x140006590`
- end: `0x140006592`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `29`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x1400011ac`
- `0x140002bd8`
- `0x140002c50`
- `0x140002d6c`
- `0x140002dfc`
- `0x140002e88`
- `0x140002f14`
- `0x1400033ec`
- `0x140003518`
- `0x140003774`
- `0x140003bb0`
- `0x140004108`
- `0x140004240`
- `0x1400044b0`
- `0x1400044f0`
- `0x140004730`
- `0x140004850`
- `0x14000505c`
- `0x14000556c`
- `0x1400055e0`
- `0x140005720`
- `0x140005780`
- `0x1400058fc`
- `0x1400060cc`
- `0x140006110`
- `0x1400065b0`
- `0x140006680`
- `0x1400066b0`
- `0x140006710`

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
0x140006590  jmp     rax
```
