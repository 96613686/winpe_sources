# abort

- ea: `0x18016afda`
- end: `0x18016afe0`
- name: `abort`
- size: `6`
- prototype: `void __cdecl __noreturn()`
- caller_count: `21`
- callee_count: `0`
- tags: ``

## callers

- `0x18005a310`
- `0x18015051c`
- `0x1801668c4`
- `0x180166fec`
- `0x1801672e0`
- `0x180167818`
- `0x180167a70`
- `0x180167bd0`
- `0x180167dc8`
- `0x180167fc4`
- `0x18016808c`
- `0x18016831c`
- `0x18016881c`
- `0x180168d5c`
- `0x180168fc4`
- `0x180169540`
- `0x180169774`
- `0x180169eb0`
- `0x18016a360`
- `0x18016a4f0`
- `0x18016a8ac`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18016afda`

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
0x18016afda  jmp     cs:__imp_abort
```
