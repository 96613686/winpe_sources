# _guard_dispatch_icall_nop

- ea: `0x180013740`
- end: `0x180013742`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x1800015b0`
- `0x180001824`
- `0x180001c9c`
- `0x180013770`
- `0x1800137a0`

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
0x180013740  jmp     rax
```
