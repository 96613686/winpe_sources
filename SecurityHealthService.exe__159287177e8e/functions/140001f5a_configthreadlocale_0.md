# _configthreadlocale_0

- ea: `0x140001f5a`
- end: `0x140001f60`
- name: `_configthreadlocale_0`
- size: `6`
- prototype: `int __cdecl(int Flag)`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x140001320`

## import_xrefs

- `api-ms-win-crt-locale-l1-1-0!_configthreadlocale` at `0x140001f5a`

## pseudocode

```c
// attributes: thunk
int __cdecl configthreadlocale_0(int Flag)
{
  return _configthreadlocale(Flag);
}

```

## disassembly

```asm
0x140001f5a  jmp     cs:__imp__configthreadlocale
```
