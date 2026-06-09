# _guard_dispatch_icall_nop

- ea: `0x1800162c0`
- end: `0x1800162c2`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180001820`
- `0x180001a94`
- `0x180001cb4`
- `0x1800162f0`
- `0x180016380`

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
0x1800162c0  jmp     rax
```
