# terminate

- ea: `0x180006cc7`
- end: `0x180006ccd`
- name: `terminate`
- size: `6`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x1800031a0`
- `0x18000328c`
- `0x1800032f8`
- `0x180003e8c`
- `0x18000438c`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!terminate` at `0x180006cc7`

## pseudocode

```c
// attributes: thunk
void __noreturn terminate()
{
  __imp_terminate();
}

```

## disassembly

```asm
0x180006cc7  jmp     cs:__imp_terminate
```
