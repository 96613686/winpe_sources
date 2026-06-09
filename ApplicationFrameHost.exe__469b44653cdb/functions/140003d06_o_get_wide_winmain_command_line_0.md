# _o__get_wide_winmain_command_line_0

- ea: `0x140003d06`
- end: `0x140003d0c`
- name: `_o__get_wide_winmain_command_line_0`
- size: `6`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140003000`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__get_wide_winmain_command_line` at `0x140003d06`

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
0x140003d06  jmp     cs:__imp__o__get_wide_winmain_command_line
```
