# terminate_0

- ea: `0x18000b5fe`
- end: `0x18000b604`
- name: `terminate_0`
- size: `6`
- prototype: `void __noreturn()`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180008a80`
- `0x180008b50`
- `0x180008bb8`
- `0x1800095ac`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!terminate` at `0x18000b5fe`

## pseudocode

```c
// attributes: thunk
void __noreturn terminate_0()
{
  terminate();
}

```

## disassembly

```asm
0x18000b5fe  jmp     cs:__imp_terminate
```
