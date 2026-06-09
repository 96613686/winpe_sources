# j__guard_dispatch_icall_nop

- ea: `0x14000cff0`
- end: `0x14000cff6`
- name: `j__guard_dispatch_icall_nop`
- size: `6`
- prototype: ``
- caller_count: `16`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140004590`
- `0x140004e64`
- `0x140004e9c`
- `0x140004f10`
- `0x1400050e4`
- `0x1400055dc`
- `0x140005958`
- `0x14000648c`
- `0x1400095a0`
- `0x1400095fc`
- `0x1400096f4`
- `0x1400097e8`
- `0x140009a38`
- `0x140009ab8`
- `0x140009b00`
- `0x140009c94`

## callees

- `0x14000cfb0`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall j__guard_dispatch_icall_nop()
{
  __int64 (__fastcall *v0)(); // rax

  return v0();
}

```

## disassembly

```asm
0x14000cff0  jmp     cs:__guard_dispatch_icall_fptr
```
