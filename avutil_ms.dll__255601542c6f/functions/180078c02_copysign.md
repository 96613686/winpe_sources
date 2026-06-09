# copysign

- ea: `0x180078c02`
- end: `0x180078c08`
- name: `copysign`
- size: `6`
- prototype: `double __cdecl(double Number, double Sign)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18002ad1c`
- `0x18002c91c`

## import_xrefs

- `api-ms-win-crt-math-l1-1-0!copysign` at `0x180078c02`

## pseudocode

```c
// attributes: thunk
double __cdecl copysign(double Number, double Sign)
{
  return __imp_copysign(Number, Sign);
}

```

## disassembly

```asm
0x180078c02  jmp     cs:__imp_copysign
```
