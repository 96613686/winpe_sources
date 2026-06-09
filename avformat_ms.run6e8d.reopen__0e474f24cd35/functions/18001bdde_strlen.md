# strlen

- ea: `0x18001bdde`
- end: `0x18001bde4`
- name: `strlen`
- size: `6`
- prototype: `size_t __cdecl(const char *Str)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x1800039f0`
- `0x180004450`
- `0x1800044d0`
- `0x180010290`
- `0x180011008`
- `0x1800188e4`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!strlen` at `0x18001bdde`

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
0x18001bdde  jmp     cs:__imp_strlen
```
