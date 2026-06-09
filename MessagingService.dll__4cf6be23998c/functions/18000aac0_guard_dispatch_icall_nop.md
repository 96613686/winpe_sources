# _guard_dispatch_icall_nop

- ea: `0x18000aac0`
- end: `0x18000aac2`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x1800020d0`
- `0x180002344`
- `0x180002598`
- `0x18000aa90`
- `0x18000aaf0`

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
0x18000aac0  jmp     rax
```
