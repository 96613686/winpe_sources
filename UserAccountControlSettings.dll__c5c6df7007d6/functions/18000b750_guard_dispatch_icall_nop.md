# _guard_dispatch_icall_nop

- ea: `0x18000b750`
- end: `0x18000b752`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180001a90`
- `0x180001d04`
- `0x180002108`
- `0x18000b780`
- `0x18000b810`

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
0x18000b750  jmp     rax
```
