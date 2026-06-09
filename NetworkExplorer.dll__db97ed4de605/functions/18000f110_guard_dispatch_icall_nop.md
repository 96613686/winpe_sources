# _guard_dispatch_icall_nop

- ea: `0x18000f110`
- end: `0x18000f112`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180007490`
- `0x180007704`
- `0x180007994`
- `0x18000f0e0`
- `0x18000f140`

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
0x18000f110  jmp     rax
```
