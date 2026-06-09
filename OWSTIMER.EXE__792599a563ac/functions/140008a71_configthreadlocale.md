# _configthreadlocale

- ea: `0x140008a71`
- end: `0x140008a77`
- name: `_configthreadlocale`
- size: `6`
- prototype: `int __cdecl(int Flag)`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x140007de0`

## import_xrefs

- `api-ms-win-crt-locale-l1-1-0!_configthreadlocale` at `0x140008a71`

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
0x140008a71  jmp     cs:__imp__configthreadlocale
```
