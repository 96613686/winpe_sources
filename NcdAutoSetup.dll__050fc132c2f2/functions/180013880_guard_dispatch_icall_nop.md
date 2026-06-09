# _guard_dispatch_icall_nop

- ea: `0x180013880`
- end: `0x180013882`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180001910`
- `0x180001b84`
- `0x180001da4`
- `0x1800138b0`
- `0x180013940`

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
0x180013880  jmp     rax
```
