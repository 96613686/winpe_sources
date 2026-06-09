# _get_narrow_winmain_command_line

- ea: `0x140008a3b`
- end: `0x140008a41`
- name: `_get_narrow_winmain_command_line`
- size: `6`
- prototype: `char *__cdecl()`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140007ecc`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_get_narrow_winmain_command_line` at `0x140008a3b`

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
0x140008a3b  jmp     cs:__imp__get_narrow_winmain_command_line
```
