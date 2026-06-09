# _guard_dispatch_icall_nop

- ea: `0x1400044a0`
- end: `0x1400044a2`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x140001168`
- `0x1400044d0`
- `0x140004500`

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
0x1400044a0  jmp     rax
```
