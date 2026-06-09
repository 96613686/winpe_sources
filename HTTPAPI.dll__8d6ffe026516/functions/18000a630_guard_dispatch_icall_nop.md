# _guard_dispatch_icall_nop

- ea: `0x18000a630`
- end: `0x18000a632`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x1800044b4`
- `0x18000a660`
- `0x18000a690`

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
0x18000a630  jmp     rax
```
