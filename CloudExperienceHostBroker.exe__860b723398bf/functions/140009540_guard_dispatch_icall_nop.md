# _guard_dispatch_icall_nop

- ea: `0x140009540`
- end: `0x140009542`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x140001dd0`
- `0x140002068`
- `0x140009510`
- `0x140009570`

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
0x140009540  jmp     rax
```
