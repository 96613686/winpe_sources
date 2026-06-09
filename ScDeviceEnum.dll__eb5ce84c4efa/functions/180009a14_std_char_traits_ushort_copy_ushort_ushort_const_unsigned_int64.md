# std::char_traits<ushort>::copy(ushort *,ushort const *,unsigned __int64)

- ea: `0x180009a14`
- end: `0x180009a30`
- name: `?copy@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z`
- size: `28`
- prototype: `void *__fastcall(void *, const void *, __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180009164`
- `0x180009840`
- `0x1800098a4`
- `0x180009970`
- `0x180011728`
- `0x1800117d0`

## callees

- `0x180001f26`
- `0x180009a14`

## pseudocode

```c
void *__fastcall std::char_traits<unsigned short>::copy(void *a1, const void *a2, __int64 a3)
{
  if ( a3 )
    return memcpy_0(a1, a2, 2 * a3);
  return a1;
}

```

## disassembly

```asm
0x180009a14  sub     rsp, 28h
0x180009a18  test    r8, r8
0x180009a1b  jz      short loc_180009A28
0x180009a1d  add     r8, r8; Size
0x180009a20  call    memcpy_0
0x180009a25  mov     rcx, rax
0x180009a28  mov     rax, rcx
0x180009a2b  add     rsp, 28h
0x180009a2f  retn
```
