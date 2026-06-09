# _guard_dispatch_icall_nop

- ea: `0x180005bb0`
- end: `0x180005bb2`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180002a10`
- `0x180002c84`
- `0x180005be0`
- `0x180005c10`

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
0x180005bb0  jmp     rax
```
