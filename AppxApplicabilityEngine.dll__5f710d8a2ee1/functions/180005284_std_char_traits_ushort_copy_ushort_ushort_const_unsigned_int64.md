# std::char_traits<ushort>::copy(ushort *,ushort const *,unsigned __int64)

- ea: `0x180005284`
- end: `0x18000528c`
- name: `?copy@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z`
- size: `8`
- prototype: ``
- caller_count: `11`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180004920`
- `0x180004c88`
- `0x180004e60`
- `0x180005000`
- `0x180005140`
- `0x180005780`
- `0x180008fc0`
- `0x180009288`
- `0x180009350`
- `0x18000951c`
- `0x18001b654`

## callees

- `0x1800132b6`

## pseudocode

```c
void *__fastcall std::char_traits<unsigned short>::copy(void *a1, const void *a2, __int64 a3)
{
  return memcpy_0(a1, a2, 2 * a3);
}

```

## disassembly

```asm
0x180005284  add     r8, r8; Size
0x180005287  jmp     memcpy_0
```
