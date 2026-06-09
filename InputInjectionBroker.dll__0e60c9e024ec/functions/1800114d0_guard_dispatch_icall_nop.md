# _guard_dispatch_icall_nop

- ea: `0x1800114d0`
- end: `0x1800114d2`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180001890`
- `0x180001b04`
- `0x180001d28`
- `0x1800114a0`
- `0x180011500`

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
0x1800114d0  jmp     rax
```
