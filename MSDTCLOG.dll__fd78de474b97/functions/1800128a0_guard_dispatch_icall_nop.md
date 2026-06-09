# _guard_dispatch_icall_nop

- ea: `0x1800128a0`
- end: `0x1800128a2`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x1800013f0`
- `0x180001664`
- `0x180001f44`
- `0x180012870`
- `0x1800128d0`

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
0x1800128a0  jmp     rax
```
