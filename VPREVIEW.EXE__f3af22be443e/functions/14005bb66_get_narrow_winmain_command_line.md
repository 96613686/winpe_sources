# _get_narrow_winmain_command_line

- ea: `0x14005bb66`
- end: `0x14005bb6c`
- name: `_get_narrow_winmain_command_line`
- size: `6`
- prototype: `char *__cdecl()`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x14005a6fc`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_get_narrow_winmain_command_line` at `0x14005bb66`

## pseudocode

```c
// attributes: thunk
char *__cdecl get_narrow_winmain_command_line()
{
  return _get_narrow_winmain_command_line();
}

```

## disassembly

```asm
0x14005bb66  jmp     cs:__imp__get_narrow_winmain_command_line
```
