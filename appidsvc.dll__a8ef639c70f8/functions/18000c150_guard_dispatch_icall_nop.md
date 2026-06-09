# _guard_dispatch_icall_nop

- ea: `0x18000c150`
- end: `0x18000c152`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x1800013d0`
- `0x180001644`
- `0x1800018dc`
- `0x18000c120`
- `0x18000c180`

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
0x18000c150  jmp     rax
```
