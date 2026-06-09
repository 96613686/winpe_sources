# std::locale::_Getgloballocale(void)

- ea: `0x18000258c`
- end: `0x180002594`
- name: `?_Getgloballocale@locale@std@@CAPEAV_Locimp@12@XZ`
- size: `8`
- prototype: `struct std::locale::_Locimp *(void)`
- caller_count: `39`
- callee_count: `0`
- tags: ``

## callers

- `0x180002c3c`
- `0x180002d80`
- `0x180002ec4`
- `0x180003008`
- `0x18000314c`
- `0x1800095bc`
- `0x180009700`
- `0x180009844`
- `0x180009988`
- `0x180009acc`
- `0x180009c10`
- `0x180009d54`
- `0x180009e98`
- `0x180009fdc`
- `0x18000a120`
- `0x18000a264`
- `0x18000a3a8`
- `0x18000a4ec`
- `0x18000a630`
- `0x18000a774`
- `0x18000a8b8`
- `0x18000a9fc`
- `0x18000ab40`
- `0x18000ac84`
- `0x18000adc8`
- `0x18000af0c`
- `0x18000b050`
- `0x18000b194`
- `0x18000b2d8`
- `0x18000b41c`
- `0x18000b560`
- `0x18001cc84`
- `0x18001cdc8`
- `0x18001cf0c`
- `0x18001d050`
- `0x18001d194`
- `0x18001d2d8`
- `0x18001d41c`
- `0x18001d560`

## pseudocode

```c
struct std::locale::_Locimp *std::locale::_Getgloballocale(void)
{
  return (struct std::locale::_Locimp *)qword_1800465A8;
}

```

## disassembly

```asm
0x18000258c  mov     rax, cs:qword_1800465A8
0x180002593  retn
```
