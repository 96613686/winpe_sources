# _guard_dispatch_icall_nop

- ea: `0x180015450`
- end: `0x180015452`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180014738`
- `0x18001482c`
- `0x180014bd0`
- `0x180014c80`
- `0x180015430`
- `0x180015470`

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
0x180015450  jmp     rax
```
