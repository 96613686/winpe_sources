# _configthreadlocale

- ea: `0x18002c980`
- end: `0x18002c986`
- name: `_configthreadlocale`
- size: `6`
- prototype: `int __cdecl(int Flag)`
- caller_count: `2`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x18000e7d8`
- `0x18000e8d4`

## import_xrefs

- `api-ms-win-crt-locale-l1-1-0!_configthreadlocale` at `0x18002c980`

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
0x18002c980  jmp     cs:__imp__configthreadlocale
```
