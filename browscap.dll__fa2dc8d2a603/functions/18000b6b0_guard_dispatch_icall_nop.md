# _guard_dispatch_icall_nop

- ea: `0x18000b6b0`
- end: `0x18000b6b2`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180001260`
- `0x1800014d4`
- `0x180001b94`
- `0x18000b680`
- `0x18000b6e0`

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
0x18000b6b0  jmp     rax
```
