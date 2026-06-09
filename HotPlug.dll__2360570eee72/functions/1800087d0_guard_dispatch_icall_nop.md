# _guard_dispatch_icall_nop

- ea: `0x1800087d0`
- end: `0x1800087d2`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180001a00`
- `0x180001c74`
- `0x1800020dc`
- `0x1800087a0`
- `0x180008800`

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
0x1800087d0  jmp     rax
```
