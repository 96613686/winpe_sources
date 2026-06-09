# _guard_dispatch_icall_nop

- ea: `0x180006140`
- end: `0x180006142`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180004970`
- `0x180004be4`
- `0x180006170`

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
0x180006140  jmp     rax
```
