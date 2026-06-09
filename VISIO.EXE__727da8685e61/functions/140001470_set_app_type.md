# _set_app_type

- ea: `0x140001470`
- end: `0x140001476`
- name: `_set_app_type`
- size: `6`
- prototype: `void __cdecl(_crt_app_type Type)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140001750`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_set_app_type` at `0x140001470`

## pseudocode

```c
// attributes: thunk
void __cdecl set_app_type(_crt_app_type Type)
{
  _set_app_type(Type);
}

```

## disassembly

```asm
0x140001470  jmp     cs:__imp__set_app_type
```
