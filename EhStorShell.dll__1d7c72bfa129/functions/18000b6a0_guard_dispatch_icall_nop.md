# _guard_dispatch_icall_nop

- ea: `0x18000b6a0`
- end: `0x18000b6a2`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180006c20`
- `0x180006e94`
- `0x1800074c4`
- `0x18000b670`
- `0x18000b6d0`

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
0x18000b6a0  jmp     rax
```
