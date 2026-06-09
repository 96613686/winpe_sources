# _guard_dispatch_icall_nop

- ea: `0x18001bd30`
- end: `0x18001bd32`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x1800088a0`
- `0x180008b14`
- `0x1800091dc`
- `0x18001bd60`
- `0x18001bdf0`

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
0x18001bd30  jmp     rax
```
