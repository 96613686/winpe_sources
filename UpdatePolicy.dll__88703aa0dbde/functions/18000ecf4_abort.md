# abort

- ea: `0x18000ecf4`
- end: `0x18000ecfa`
- name: `abort`
- size: `6`
- prototype: `void __cdecl __noreturn()`
- caller_count: `19`
- callee_count: `0`
- tags: ``

## callers

- `0x18000de80`
- `0x1800101a4`
- `0x1800108cc`
- `0x180011058`
- `0x1800112b0`
- `0x180011410`
- `0x180011608`
- `0x180011804`
- `0x1800118cc`
- `0x180011b5c`
- `0x18001205c`
- `0x18001259c`
- `0x180012804`
- `0x180012d80`
- `0x180012fb4`
- `0x1800136f0`
- `0x180013ba0`
- `0x180013d30`
- `0x1800140ec`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18000ecf4`

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
0x18000ecf4  jmp     cs:__imp_abort
```
