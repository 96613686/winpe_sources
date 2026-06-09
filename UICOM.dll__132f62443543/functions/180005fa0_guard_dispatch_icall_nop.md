# _guard_dispatch_icall_nop

- ea: `0x180005fa0`
- end: `0x180005fa2`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180001220`
- `0x180001494`
- `0x180001a2c`
- `0x180005fd0`
- `0x180006060`

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
0x180005fa0  jmp     rax
```
