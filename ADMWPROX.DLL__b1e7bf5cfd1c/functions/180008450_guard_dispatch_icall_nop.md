# _guard_dispatch_icall_nop

- ea: `0x180008450`
- end: `0x180008452`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x1800011b0`
- `0x180001424`
- `0x180001844`
- `0x180008480`
- `0x180008510`

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
0x180008450  jmp     rax
```
