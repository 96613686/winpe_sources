# abort

- ea: `0x180017baf`
- end: `0x180017bb5`
- name: `abort`
- size: `6`
- prototype: `void __cdecl __noreturn()`
- caller_count: `11`
- callee_count: `0`
- tags: ``

## callers

- `0x18001a354`
- `0x18001a620`
- `0x18001aad8`
- `0x18001ad30`
- `0x18001af28`
- `0x18001b0c4`
- `0x18001b610`
- `0x18001bb78`
- `0x18001c040`
- `0x18001c4d4`
- `0x18001c7e0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180017baf`

## pseudocode

```c
// attributes: thunk
void __cdecl __noreturn abort()
{
  __imp_abort();
}

```

## disassembly

```asm
0x180017baf  jmp     cs:__imp_abort
```
