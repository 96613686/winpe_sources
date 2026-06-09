# _guard_dispatch_icall_nop

- ea: `0x180003520`
- end: `0x180003522`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180001050`
- `0x1800012c4`
- `0x180003550`

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
0x180003520  jmp     rax
```
