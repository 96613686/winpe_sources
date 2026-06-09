# _guard_dispatch_icall_nop

- ea: `0x180009600`
- end: `0x180009602`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180001a30`
- `0x180001ca4`
- `0x180009630`
- `0x180009660`

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
0x180009600  jmp     rax
```
