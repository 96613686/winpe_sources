# _guard_dispatch_icall

- ea: `0x1400158d0`
- end: `0x140015902`
- name: `_guard_dispatch_icall`
- size: `50`
- prototype: ``
- caller_count: `13`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140002330`
- `0x140005988`
- `0x1400059f4`
- `0x140005b08`
- `0x140005ca0`
- `0x140006130`
- `0x140009628`
- `0x14000dae4`
- `0x14000dedc`
- `0x140013330`
- `0x140014ba8`
- `0x140017010`
- `0x140023010`

## callees

- `0x1400158d0`

## pseudocode

```c
__int64 __fastcall guard_dispatch_icall()
{
  __int64 (*v0)(void); // rax

  return v0();
}

```

## disassembly

```asm
0x1400158d0  jmp     cs:__guard_dispatch_icall_fptr
0x140015900  jmp     rax
```
