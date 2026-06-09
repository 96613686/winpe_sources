# _guard_dispatch_icall_nop

- ea: `0x180011a60`
- end: `0x180011a62`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180008330`
- `0x1800085a4`
- `0x1800087c8`
- `0x180011a30`
- `0x180011a90`

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
0x180011a60  jmp     rax
```
