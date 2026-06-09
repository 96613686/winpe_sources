# _guard_dispatch_icall_nop

- ea: `0x14000aea0`
- end: `0x14000aea2`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x140001310`
- `0x140001800`
- `0x14000aed0`
- `0x14000af60`

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
0x14000aea0  jmp     rax
```
