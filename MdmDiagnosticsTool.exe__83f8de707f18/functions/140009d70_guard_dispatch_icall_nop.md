# _guard_dispatch_icall_nop

- ea: `0x140009d70`
- end: `0x140009d72`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x1400018a0`
- `0x140001a88`
- `0x140009d40`
- `0x140009da0`

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
0x140009d70  jmp     rax
```
