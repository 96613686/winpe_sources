# memcmp

- ea: `0x18006cc58`
- end: `0x18006cc5e`
- name: `memcmp`
- size: `6`
- prototype: `int __cdecl(const void *Buf1, const void *Buf2, size_t Size)`
- caller_count: `31`
- callee_count: `0`
- tags: ``

## callers

- `0x18000be4c`
- `0x180013a70`
- `0x180014a74`
- `0x180017350`
- `0x18001777c`
- `0x1800190d0`
- `0x1800192c0`
- `0x18001a880`
- `0x18001c5c8`
- `0x1800208a8`
- `0x180025850`
- `0x18002a640`
- `0x18002a7cc`
- `0x18002ac90`
- `0x18002bcb0`
- `0x18002eabc`
- `0x180038b8c`
- `0x180038ebc`
- `0x18003a024`
- `0x18003a3b0`
- `0x18003e260`
- `0x18003e63c`
- `0x18003e9c0`
- `0x18003fc2c`
- `0x180040760`
- `0x180052544`
- `0x180052b10`
- `0x180058ed0`
- `0x18005bb10`
- `0x18005fc08`
- `0x1800606e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memcmp` at `0x18006cc58`

## pseudocode

```c
// attributes: thunk
int __cdecl memcmp(const void *Buf1, const void *Buf2, size_t Size)
{
  return __imp_memcmp(Buf1, Buf2, Size);
}

```

## disassembly

```asm
0x18006cc58  jmp     cs:__imp_memcmp
```
