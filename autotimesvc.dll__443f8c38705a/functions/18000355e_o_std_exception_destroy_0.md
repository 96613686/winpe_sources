# _o___std_exception_destroy_0

- ea: `0x18000355e`
- end: `0x180003564`
- name: `_o___std_exception_destroy_0`
- size: `6`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180004ca0`
- `0x180005688`
- `0x1800058b4`
- `0x180005a0c`
- `0x180005c30`
- `0x180005c80`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_destroy` at `0x18000355e`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall o___std_exception_destroy_0(__int64 a1)
{
  return __std_exception_destroy(a1);
}

```

## disassembly

```asm
0x18000355e  jmp     cs:__imp___std_exception_destroy
```
