# _configthreadlocale

- ea: `0x14005bb9c`
- end: `0x14005bba2`
- name: `_configthreadlocale`
- size: `6`
- prototype: `int __cdecl(int Flag)`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x14005a610`

## import_xrefs

- `api-ms-win-crt-locale-l1-1-0!_configthreadlocale` at `0x14005bb9c`

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
0x14005bb9c  jmp     cs:__imp__configthreadlocale
```
