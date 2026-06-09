# _o__configthreadlocale

- ea: `0x14000785e`
- end: `0x140007864`
- name: `_o__configthreadlocale`
- size: `6`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x140006cb0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__configthreadlocale` at `0x14000785e`

## pseudocode

```c
// attributes: thunk
__int64 o__configthreadlocale()
{
  return _o__configthreadlocale();
}

```

## disassembly

```asm
0x14000785e  jmp     cs:__imp__o__configthreadlocale
```
