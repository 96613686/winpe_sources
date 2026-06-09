# _guard_dispatch_icall

- ea: `0x14000f4d0`
- end: `0x14000f4d6`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `60`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x14000142c`
- `0x140001714`
- `0x140001904`
- `0x140001ad0`
- `0x1400026e0`
- `0x1400029fc`
- `0x140002c30`
- `0x140002d20`
- `0x140003910`
- `0x140003c48`
- `0x140003ca4`
- `0x140003e98`
- `0x140004168`
- `0x140004318`
- `0x14000452c`
- `0x1400045d0`
- `0x140004778`
- `0x140004d94`
- `0x14000523c`
- `0x140005e94`
- `0x1400060c4`
- `0x1400062f4`
- `0x140006524`
- `0x140006754`
- `0x140006984`
- `0x140006bb4`
- `0x140006de4`
- `0x140007014`
- `0x140007244`
- `0x140007474`
- `0x1400076a4`
- `0x1400078d4`
- `0x140007b04`
- `0x140007d34`
- `0x140007f64`
- `0x140008194`
- `0x1400083c4`
- `0x1400085f4`
- `0x140008824`
- `0x140008a54`
- `0x140008c84`
- `0x140008eb4`
- `0x1400090e4`
- `0x140009314`
- `0x140009544`
- `0x140009774`
- `0x1400099a4`
- `0x140009bd4`
- `0x140009e04`
- `0x14000a034`

## callees

- `0x14000f4f0`

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
0x14000f4d0  jmp     cs:__guard_dispatch_icall_fptr
```
