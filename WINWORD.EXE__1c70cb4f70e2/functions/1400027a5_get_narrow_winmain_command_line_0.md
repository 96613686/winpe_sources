# _get_narrow_winmain_command_line_0

- ea: `0x1400027a5`
- end: `0x1400027ab`
- name: `_get_narrow_winmain_command_line_0`
- size: `6`
- prototype: `char *__cdecl()`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1400018dc`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_get_narrow_winmain_command_line` at `0x1400027a5`

## pseudocode

```c
// attributes: thunk
char *__cdecl get_narrow_winmain_command_line_0()
{
  return _get_narrow_winmain_command_line();
}

```

## disassembly

```asm
0x1400027a5  jmp     cs:__imp__get_narrow_winmain_command_line
```
