# _guard_dispatch_icall_nop

- ea: `0x140009740`
- end: `0x140009742`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x140001870`
- `0x140001a58`
- `0x140009710`
- `0x140009770`

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
0x140009740  jmp     rax
```
