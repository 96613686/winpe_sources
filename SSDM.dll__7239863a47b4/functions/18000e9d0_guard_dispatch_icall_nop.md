# _guard_dispatch_icall_nop

- ea: `0x18000e9d0`
- end: `0x18000e9d2`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180002040`
- `0x1800022b4`
- `0x1800026b0`
- `0x18000ea00`
- `0x18000ea30`

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
0x18000e9d0  jmp     rax
```
