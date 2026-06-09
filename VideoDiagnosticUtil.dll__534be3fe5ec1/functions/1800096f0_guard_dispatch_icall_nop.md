# _guard_dispatch_icall_nop

- ea: `0x1800096f0`
- end: `0x1800096f2`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180001230`
- `0x1800014a4`
- `0x1800016c4`
- `0x180009720`
- `0x1800097b0`

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
0x1800096f0  jmp     rax
```
