# _invalid_parameter_noinfo

- ea: `0x140001eae`
- end: `0x140001eb4`
- name: `_invalid_parameter_noinfo`
- size: `6`
- prototype: `void __cdecl()`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x140005808`
- `0x1400065ec`
- `0x1400069e0`
- `0x140006b84`
- `0x14000715c`
- `0x140007cb0`
- `0x140008184`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo` at `0x140001eae`

## pseudocode

```c
// attributes: thunk
void __cdecl invalid_parameter_noinfo()
{
  _invalid_parameter_noinfo();
}

```

## disassembly

```asm
0x140001eae  jmp     cs:__imp__invalid_parameter_noinfo
```
