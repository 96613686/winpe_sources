# _guard_dispatch_icall_nop

- ea: `0x1400134e0`
- end: `0x1400134e2`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x140001a90`
- `0x140001c68`
- `0x140013510`
- `0x1400135a0`

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
0x1400134e0  jmp     rax
```
