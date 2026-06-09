# _guard_dispatch_icall_nop

- ea: `0x140064a70`
- end: `0x140064a72`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `21`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x14000a448`
- `0x14000a698`
- `0x140012060`
- `0x140012254`
- `0x1400122a0`
- `0x140012510`
- `0x140012688`
- `0x1400127d8`
- `0x140012ab8`
- `0x140012b70`
- `0x140013280`
- `0x140013560`
- `0x14001383c`
- `0x140013b14`
- `0x140013de4`
- `0x1400140bc`
- `0x140014394`
- `0x14001467c`
- `0x140014958`
- `0x140014c34`
- `0x140064aa0`

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
0x140064a70  jmp     rax
```
