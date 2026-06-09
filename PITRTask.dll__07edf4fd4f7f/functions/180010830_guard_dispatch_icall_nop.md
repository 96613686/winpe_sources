# _guard_dispatch_icall_nop

- ea: `0x180010830`
- end: `0x180010832`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180001780`
- `0x1800019f4`
- `0x180001c28`
- `0x180010800`
- `0x180010860`

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
0x180010830  jmp     rax
```
