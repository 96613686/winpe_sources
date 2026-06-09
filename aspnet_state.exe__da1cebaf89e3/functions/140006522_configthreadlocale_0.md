# _configthreadlocale_0

- ea: `0x140006522`
- end: `0x140006528`
- name: `_configthreadlocale_0`
- size: `6`
- prototype: `int __cdecl(int Flag)`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x140005810`

## import_xrefs

- `ucrtbase_clr0400!_configthreadlocale` at `0x140006522`

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
0x140006522  jmp     cs:__imp__configthreadlocale
```
