# _o__get_wide_winmain_command_line_0

- ea: `0x1400025c2`
- end: `0x1400025c8`
- name: `_o__get_wide_winmain_command_line_0`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140001b20`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__get_wide_winmain_command_line` at `0x1400025c2`

## pseudocode

```c
// attributes: thunk
__int64 o__get_wide_winmain_command_line_0()
{
  return _o__get_wide_winmain_command_line();
}

```

## disassembly

```asm
0x1400025c2  jmp     cs:__imp__o__get_wide_winmain_command_line
```
