# _guard_dispatch_icall_nop

- ea: `0x140001540`
- end: `0x140001542`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `12`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x140001180`
- `0x140001550`
- `0x140001650`
- `0x14000194c`
- `0x140001ac0`
- `0x140001c40`
- `0x140001e10`
- `0x140002090`
- `0x140002710`
- `0x140002970`
- `0x140002c10`
- `0x140002d90`

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
0x140001540  jmp     rax
```
