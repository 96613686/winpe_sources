# _guard_dispatch_icall_nop

- ea: `0x14000e230`
- end: `0x14000e232`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x140002200`
- `0x140002498`
- `0x14000e200`
- `0x14000e260`

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
0x14000e230  jmp     rax
```
