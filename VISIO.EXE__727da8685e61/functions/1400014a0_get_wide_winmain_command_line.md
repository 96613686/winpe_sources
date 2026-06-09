# _get_wide_winmain_command_line

- ea: `0x1400014a0`
- end: `0x1400014a6`
- name: `_get_wide_winmain_command_line`
- size: `6`
- prototype: `wchar_t *__cdecl()`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140001570`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_get_wide_winmain_command_line` at `0x1400014a0`

## pseudocode

```c
// attributes: thunk
wchar_t *__cdecl get_wide_winmain_command_line()
{
  return _get_wide_winmain_command_line();
}

```

## disassembly

```asm
0x1400014a0  jmp     cs:__imp__get_wide_winmain_command_line
```
