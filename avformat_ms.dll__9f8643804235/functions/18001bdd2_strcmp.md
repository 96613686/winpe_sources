# strcmp

- ea: `0x18001bdd2`
- end: `0x18001bdd8`
- name: `strcmp`
- size: `6`
- prototype: `int __cdecl(const char *Str1, const char *Str2)`
- caller_count: `23`
- callee_count: `0`
- tags: ``

## callers

- `0x180001c10`
- `0x1800023d8`
- `0x180003294`
- `0x1800035d4`
- `0x1800039f0`
- `0x180003c8c`
- `0x1800062e0`
- `0x180006390`
- `0x180007900`
- `0x180008068`
- `0x180008910`
- `0x18000b288`
- `0x18000d148`
- `0x18000fa10`
- `0x18000fe00`
- `0x180010cb8`
- `0x180010da0`
- `0x180010e4c`
- `0x1800110fc`
- `0x180011cac`
- `0x180019190`
- `0x180019200`
- `0x180019780`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!strcmp` at `0x18001bdd2`

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
0x18001bdd2  jmp     cs:__imp_strcmp
```
