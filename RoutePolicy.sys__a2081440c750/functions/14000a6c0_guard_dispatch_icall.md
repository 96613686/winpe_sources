# _guard_dispatch_icall

- ea: `0x14000a6c0`
- end: `0x14000a6c6`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `22`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140002d00`
- `0x140003340`
- `0x140003dac`
- `0x140003f18`
- `0x140004e54`
- `0x140005034`
- `0x140005874`
- `0x14000646c`
- `0x140006570`
- `0x140007110`
- `0x140007280`
- `0x140007da0`
- `0x140008c5c`
- `0x140008d94`
- `0x140008f10`
- `0x140008f44`
- `0x1400090d0`
- `0x14000b010`
- `0x1400170c0`
- `0x140017140`
- `0x140017ca4`
- `0x14001903c`

## callees

- `0x14000a6f0`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall guard_dispatch_icall()
{
  __int64 (__fastcall *v0)(); // rax

  return v0();
}

```

## disassembly

```asm
0x14000a6c0  jmp     cs:__guard_dispatch_icall_fptr
```
