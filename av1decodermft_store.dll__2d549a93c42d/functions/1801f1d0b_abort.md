# abort

- ea: `0x1801f1d0b`
- end: `0x1801f1d11`
- name: `abort`
- size: `6`
- prototype: `void __cdecl __noreturn()`
- caller_count: `19`
- callee_count: `0`
- tags: ``

## callers

- `0x18017f954`
- `0x18018007c`
- `0x180180370`
- `0x1801808a8`
- `0x180180b00`
- `0x180180c60`
- `0x180180e58`
- `0x180181054`
- `0x18018111c`
- `0x1801813ac`
- `0x1801818ac`
- `0x180181dec`
- `0x180182054`
- `0x1801825d0`
- `0x180182804`
- `0x180182f40`
- `0x1801833f0`
- `0x180183580`
- `0x18018393c`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x1801f1d0b`

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
0x1801f1d0b  jmp     cs:__imp_abort
```
