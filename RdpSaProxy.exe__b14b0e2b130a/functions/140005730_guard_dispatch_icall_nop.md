# _guard_dispatch_icall_nop

- ea: `0x140005730`
- end: `0x140005732`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x1400011e0`
- `0x140001478`
- `0x140005760`
- `0x140005790`

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
0x140005730  jmp     rax
```
