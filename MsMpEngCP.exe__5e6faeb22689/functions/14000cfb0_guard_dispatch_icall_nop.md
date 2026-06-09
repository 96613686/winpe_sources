# _guard_dispatch_icall_nop

- ea: `0x14000cfb0`
- end: `0x14000cfb2`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `16`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x140001000`
- `0x14000119c`
- `0x140001914`
- `0x140001950`
- `0x140002030`
- `0x140002588`
- `0x1400025d0`
- `0x140002618`
- `0x140002660`
- `0x1400026b4`
- `0x140002718`
- `0x140002e0c`
- `0x140003a20`
- `0x1400044e8`
- `0x14000cfd0`
- `0x14000cff0`

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
0x14000cfb0  jmp     rax
```
