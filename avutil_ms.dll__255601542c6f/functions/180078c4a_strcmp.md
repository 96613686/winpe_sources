# strcmp

- ea: `0x180078c4a`
- end: `0x180078c50`
- name: `strcmp`
- size: `6`
- prototype: `int __cdecl(const char *Str1, const char *Str2)`
- caller_count: `22`
- callee_count: `0`
- tags: ``

## callers

- `0x180031b40`
- `0x180032620`
- `0x180032bc0`
- `0x180036210`
- `0x18003f170`
- `0x1800426b0`
- `0x180045780`
- `0x1800465b0`
- `0x180048524`
- `0x180048658`
- `0x1800493b0`
- `0x18004a4b4`
- `0x18004a680`
- `0x18004a7b8`
- `0x18004a834`
- `0x18004b040`
- `0x18004b960`
- `0x18004ba50`
- `0x18004c4b0`
- `0x18004c800`
- `0x18004cf54`
- `0x18004f5c0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!strcmp` at `0x180078c4a`

## pseudocode

```c
// attributes: thunk
int __cdecl strcmp(const char *Str1, const char *Str2)
{
  return __imp_strcmp(Str1, Str2);
}

```

## disassembly

```asm
0x180078c4a  jmp     cs:__imp_strcmp
```
