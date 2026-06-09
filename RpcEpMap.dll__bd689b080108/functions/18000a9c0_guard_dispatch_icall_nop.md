# _guard_dispatch_icall_nop

- ea: `0x18000a9c0`
- end: `0x18000a9c2`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180005d08`
- `0x18000a9f0`
- `0x18000aa20`

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
0x18000a9c0  jmp     rax
```
