# _guard_dispatch_icall_nop

- ea: `0x180009f70`
- end: `0x180009f72`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180001200`
- `0x180001474`
- `0x180001888`
- `0x180009fa0`
- `0x180009fd0`

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
0x180009f70  jmp     rax
```
