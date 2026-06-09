# _guard_dispatch_icall_nop

- ea: `0x18000f630`
- end: `0x18000f632`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180001530`
- `0x1800017a4`
- `0x180001a4c`
- `0x18000f660`
- `0x18000f6f0`

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
0x18000f630  jmp     rax
```
