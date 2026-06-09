# strlen

- ea: `0x180078c1a`
- end: `0x180078c20`
- name: `strlen`
- size: `6`
- prototype: `size_t __cdecl(const char *Str)`
- caller_count: `25`
- callee_count: `0`
- tags: ``

## callers

- `0x18002cf40`
- `0x18002d2b0`
- `0x18002d4b0`
- `0x18002d610`
- `0x18002d7c0`
- `0x18002d830`
- `0x18002d8b0`
- `0x18002d960`
- `0x18002e940`
- `0x180036210`
- `0x180037300`
- `0x180038958`
- `0x1800426b0`
- `0x180044f00`
- `0x1800465b0`
- `0x1800481c8`
- `0x180048e90`
- `0x180049074`
- `0x180049a10`
- `0x18004a380`
- `0x18004a4b4`
- `0x18004b170`
- `0x18004be48`
- `0x18004c800`
- `0x180077650`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!strlen` at `0x180078c1a`

## pseudocode

```c
// attributes: thunk
size_t __cdecl strlen(const char *Str)
{
  return __imp_strlen(Str);
}

```

## disassembly

```asm
0x180078c1a  jmp     cs:__imp_strlen
```
