# _guard_dispatch_icall_nop

- ea: `0x180001f00`
- end: `0x180001f02`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x1800011a0`
- `0x18000133c`
- `0x18000171c`
- `0x180001adc`
- `0x180001b18`
- `0x180001f20`

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
0x180001f00  jmp     rax
```
