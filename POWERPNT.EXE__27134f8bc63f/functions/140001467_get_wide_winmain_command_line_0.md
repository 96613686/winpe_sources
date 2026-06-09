# _get_wide_winmain_command_line_0

- ea: `0x140001467`
- end: `0x14000146d`
- name: `_get_wide_winmain_command_line_0`
- size: `6`
- prototype: `wchar_t *__cdecl()`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140001ac0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_get_wide_winmain_command_line` at `0x140001467`

## pseudocode

```c
// attributes: thunk
wchar_t *__cdecl get_wide_winmain_command_line_0()
{
  return _get_wide_winmain_command_line();
}

```

## disassembly

```asm
0x140001467  jmp     cs:__imp__get_wide_winmain_command_line
```
