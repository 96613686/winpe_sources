# _o__get_wide_winmain_command_line_0

- ea: `0x140001e8a`
- end: `0x140001e90`
- name: `_o__get_wide_winmain_command_line_0`
- size: `6`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140001380`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__get_wide_winmain_command_line` at `0x140001e8a`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall o__get_wide_winmain_command_line_0(__int64 a1)
{
  return _o__get_wide_winmain_command_line(a1);
}

```

## disassembly

```asm
0x140001e8a  jmp     cs:__imp__o__get_wide_winmain_command_line
```
