# _guard_dispatch_icall_nop

- ea: `0x14000df40`
- end: `0x14000df42`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x1400017e0`
- `0x140001a78`
- `0x14000df10`
- `0x14000df70`

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
0x14000df40  jmp     rax
```
