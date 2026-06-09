# std::char_traits<ushort>::move(ushort *,ushort const *,unsigned __int64)

- ea: `0x180006a80`
- end: `0x180006a9d`
- name: `?move@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z`
- size: `29`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800068f0`
- `0x180009bec`
- `0x180014ba4`

## callees

- `0x180006a80`
- `0x18001f3ce`

## pseudocode

```c
void *__fastcall std::char_traits<unsigned short>::move(void *a1, const void *a2, __int64 a3)
{
  if ( a3 )
    return memmove_0(a1, a2, 2 * a3);
  return a1;
}

```

## disassembly

```asm
0x180006a80  sub     rsp, 28h
0x180006a84  test    r8, r8
0x180006a87  jz      short loc_180006A94
0x180006a89  add     r8, r8; Size
0x180006a8c  call    memmove_0
0x180006a91  mov     rcx, rax
0x180006a94  mov     rax, rcx
0x180006a97  add     rsp, 28h
0x180006a9b  retn
```
