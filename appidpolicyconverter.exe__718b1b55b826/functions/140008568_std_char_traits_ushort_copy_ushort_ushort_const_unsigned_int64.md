# std::char_traits<ushort>::copy(ushort *,ushort const *,unsigned __int64)

- ea: `0x140008568`
- end: `0x140008584`
- name: `?copy@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z`
- size: `28`
- prototype: `void *__fastcall(void *, const void *, __int64)`
- caller_count: `7`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140008188`
- `0x140008368`
- `0x1400083c8`
- `0x1400084c0`
- `0x14000b4f8`
- `0x14000b5c4`
- `0x14000b7a0`

## callees

- `0x140008568`
- `0x140013ab7`

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
0x140008568  sub     rsp, 28h
0x14000856c  test    r8, r8
0x14000856f  jz      short loc_14000857C
0x140008571  add     r8, r8; Size
0x140008574  call    memcpy_0
0x140008579  mov     rcx, rax
0x14000857c  mov     rax, rcx
0x14000857f  add     rsp, 28h
0x140008583  retn
```
