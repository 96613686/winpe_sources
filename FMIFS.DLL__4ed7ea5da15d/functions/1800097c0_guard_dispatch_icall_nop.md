# _guard_dispatch_icall_nop

- ea: `0x1800097c0`
- end: `0x1800097c2`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180003f50`
- `0x1800041c4`
- `0x1800097f0`
- `0x180009820`

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
0x1800097c0  jmp     rax
```
