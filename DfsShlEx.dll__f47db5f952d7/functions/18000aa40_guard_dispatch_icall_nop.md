# _guard_dispatch_icall_nop

- ea: `0x18000aa40`
- end: `0x18000aa42`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180001b10`
- `0x180001d84`
- `0x18000234c`
- `0x18000aa10`
- `0x18000aa70`

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
0x18000aa40  jmp     rax
```
