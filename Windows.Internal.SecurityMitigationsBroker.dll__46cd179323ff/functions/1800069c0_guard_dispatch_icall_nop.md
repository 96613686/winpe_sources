# _guard_dispatch_icall_nop

- ea: `0x1800069c0`
- end: `0x1800069c2`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x1800013e0`
- `0x180001654`
- `0x180001868`
- `0x1800069f0`
- `0x180006a80`

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
0x1800069c0  jmp     rax
```
