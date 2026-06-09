# _guard_dispatch_icall_nop

- ea: `0x180010ff0`
- end: `0x180010ff2`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180001970`
- `0x180001be4`
- `0x180001e30`
- `0x180010fc0`
- `0x180011020`

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
0x180010ff0  jmp     rax
```
