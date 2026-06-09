# _configthreadlocale

- ea: `0x1400014e0`
- end: `0x1400014e6`
- name: `_configthreadlocale`
- size: `6`
- prototype: `int __cdecl(int Flag)`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x140001750`

## import_xrefs

- `api-ms-win-crt-locale-l1-1-0!_configthreadlocale` at `0x1400014e0`

## pseudocode

```c
// attributes: thunk
int __cdecl configthreadlocale(int Flag)
{
  return _configthreadlocale(Flag);
}

```

## disassembly

```asm
0x1400014e0  jmp     cs:__imp__configthreadlocale
```
