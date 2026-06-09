# _guard_dispatch_icall

- ea: `0x140013770`
- end: `0x140013776`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140002760`
- `0x140004910`
- `0x140004998`
- `0x140004a78`
- `0x1400102b0`
- `0x140010300`
- `0x140015010`
- `0x14001e740`

## callees

- `0x1400137a0`

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
0x140013770  jmp     cs:__guard_dispatch_icall_fptr
```
