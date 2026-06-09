# _guard_dispatch_icall_nop

- ea: `0x180007cd0`
- end: `0x180007cd2`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180001af0`
- `0x180001d64`
- `0x180001f84`
- `0x180007d00`
- `0x180007d90`

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
0x180007cd0  jmp     rax
```
