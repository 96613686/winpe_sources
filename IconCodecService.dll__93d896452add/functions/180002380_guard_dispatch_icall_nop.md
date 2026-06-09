# _guard_dispatch_icall_nop

- ea: `0x180002380`
- end: `0x180002382`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180001930`
- `0x180001ba4`
- `0x1800023b0`
- `0x1800023e0`

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
0x180002380  jmp     rax
```
