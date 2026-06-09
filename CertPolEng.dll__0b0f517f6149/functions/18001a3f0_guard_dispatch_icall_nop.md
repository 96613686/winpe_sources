# _guard_dispatch_icall_nop

- ea: `0x18001a3f0`
- end: `0x18001a3f2`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x18000e0c0`
- `0x18000e334`
- `0x18000e558`
- `0x18001a3c0`
- `0x18001a420`

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
0x18001a3f0  jmp     rax
```
