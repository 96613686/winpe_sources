# _configthreadlocale

- ea: `0x140001e5a`
- end: `0x140001e60`
- name: `_configthreadlocale`
- size: `6`
- prototype: `int __cdecl(int Flag)`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x140001290`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__configthreadlocale` at `0x140001e5a`

## pseudocode

```c
// attributes: thunk
int __cdecl configthreadlocale(int Flag)
{
  return _o__configthreadlocale(Flag);
}

```

## disassembly

```asm
0x140001e5a  jmp     cs:__imp__o__configthreadlocale
```
