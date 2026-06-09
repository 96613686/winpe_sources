# _guard_dispatch_icall_nop

- ea: `0x140001a10`
- end: `0x140001a12`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x140001190`
- `0x140001570`
- `0x140001a20`
- `0x140001a30`
- `0x140001a9c`
- `0x140001e00`

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
0x140001a10  jmp     rax
```
