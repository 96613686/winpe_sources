# abort

- ea: `0x18001bdc6`
- end: `0x18001bdcc`
- name: `abort`
- size: `6`
- prototype: `void __cdecl __noreturn()`
- caller_count: `23`
- callee_count: `0`
- tags: ``

## callers

- `0x180002344`
- `0x1800023d8`
- `0x180002b10`
- `0x180002c90`
- `0x180003144`
- `0x180003294`
- `0x1800035d4`
- `0x1800054e0`
- `0x180009380`
- `0x180009e98`
- `0x180012450`
- `0x180013ec8`
- `0x1800144ac`
- `0x180014cb0`
- `0x180016590`
- `0x1800168f0`
- `0x180018fe0`
- `0x180019fcc`
- `0x18001a18c`
- `0x18001a314`
- `0x18001aaf0`
- `0x18001ae48`
- `0x18001d398`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18001bdc6`

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
0x18001bdc6  jmp     cs:__imp_abort
```
