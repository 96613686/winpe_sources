# _guard_dispatch_icall_nop

- ea: `0x1800094b0`
- end: `0x1800094b2`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180001540`
- `0x1800017b4`
- `0x180001adc`
- `0x180009480`
- `0x1800094e0`

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
0x1800094b0  jmp     rax
```
