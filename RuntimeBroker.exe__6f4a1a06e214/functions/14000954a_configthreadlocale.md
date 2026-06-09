# _configthreadlocale

- ea: `0x14000954a`
- end: `0x140009550`
- name: `_configthreadlocale`
- size: `6`
- prototype: `int __cdecl(int Flag)`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x1400089e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__configthreadlocale` at `0x14000954a`

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
0x14000954a  jmp     cs:__imp__o__configthreadlocale
```
