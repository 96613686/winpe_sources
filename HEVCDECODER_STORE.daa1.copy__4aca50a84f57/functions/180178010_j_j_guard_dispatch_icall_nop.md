# j_j__guard_dispatch_icall_nop

- ea: `0x180178010`
- end: `0x180178015`
- name: `j_j__guard_dispatch_icall_nop`
- size: `5`
- prototype: ``
- caller_count: `17`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x1801655f8`
- `0x18016579c`
- `0x180165980`
- `0x180165ac0`
- `0x180165c28`
- `0x1801660bc`
- `0x180166100`
- `0x180166468`
- `0x1801664c4`
- `0x1801672e0`
- `0x180167300`
- `0x180167bd0`
- `0x180167dc8`
- `0x180169540`
- `0x180169774`
- `0x18016aea0`
- `0x18016b300`

## callees

- `0x180172620`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall j_j__guard_dispatch_icall_nop()
{
  __int64 (__fastcall *v0)(); // rax

  return v0();
}

```

## disassembly

```asm
0x180178010  jmp     j__guard_dispatch_icall_nop
```
