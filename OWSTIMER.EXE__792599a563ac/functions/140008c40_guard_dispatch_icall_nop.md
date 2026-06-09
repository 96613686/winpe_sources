# _guard_dispatch_icall_nop

- ea: `0x140008c40`
- end: `0x140008c42`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `12`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x1400023f4`
- `0x1400025ec`
- `0x1400029b4`
- `0x140002e18`
- `0x140003094`
- `0x140003350`
- `0x140003c78`
- `0x140005428`
- `0x140005c6c`
- `0x140006668`
- `0x140006b54`
- `0x140009552`

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
0x140008c40  jmp     rax
```
