# _guard_dispatch_icall_nop

- ea: `0x180006640`
- end: `0x180006642`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x1800010b0`
- `0x180001324`
- `0x18000175c`
- `0x180006670`
- `0x1800066a0`

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
0x180006640  jmp     rax
```
