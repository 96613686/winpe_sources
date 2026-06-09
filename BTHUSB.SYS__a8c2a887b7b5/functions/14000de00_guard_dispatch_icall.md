# _guard_dispatch_icall

- ea: `0x14000de00`
- end: `0x14000de06`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `104`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x14000175c`
- `0x1400017d4`
- `0x14000187c`
- `0x140001924`
- `0x140001c74`
- `0x140001cb4`
- `0x140001da0`
- `0x140001f44`
- `0x1400021a0`
- `0x1400021f0`
- `0x140002234`
- `0x1400024e0`
- `0x140002564`
- `0x140002b3c`
- `0x140002c24`
- `0x140002d0c`
- `0x140002dcc`
- `0x140002ec0`
- `0x140002fb4`
- `0x140005560`
- `0x1400057ac`
- `0x1400058bc`
- `0x140005c8c`
- `0x14000638c`
- `0x1400064c4`
- `0x140006580`
- `0x140006638`
- `0x140006700`
- `0x1400067e8`
- `0x1400068e8`
- `0x1400069ac`
- `0x140006abc`
- `0x140006bdc`
- `0x140006cb8`
- `0x140006db0`
- `0x140006e80`
- `0x140006f3c`
- `0x14000700c`
- `0x1400070fc`
- `0x140007218`
- `0x140007410`
- `0x1400077c4`
- `0x140007b10`
- `0x1400081b0`
- `0x140008918`
- `0x1400089f8`
- `0x140008b20`
- `0x140008c4c`
- `0x140009000`
- `0x1400090d8`

## callees

- `0x14000de30`

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
0x14000de00  jmp     cs:__guard_dispatch_icall_fptr
```
