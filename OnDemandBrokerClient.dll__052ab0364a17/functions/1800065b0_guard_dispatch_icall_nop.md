# _guard_dispatch_icall_nop

- ea: `0x1800065b0`
- end: `0x1800065b2`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180004410`
- `0x180004684`
- `0x1800065e0`
- `0x180006610`

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
0x1800065b0  jmp     rax
```
