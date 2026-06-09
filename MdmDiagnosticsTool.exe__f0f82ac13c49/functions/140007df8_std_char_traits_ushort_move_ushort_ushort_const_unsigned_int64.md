# std::char_traits<ushort>::move(ushort *,ushort const *,unsigned __int64)

- ea: `0x140007df8`
- end: `0x140007e14`
- name: `?move@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z`
- size: `28`
- prototype: `void *__fastcall(void *, const void *, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400035ac`
- `0x140007c00`

## callees

- `0x140001de2`
- `0x140007df8`

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
0x140007df8  sub     rsp, 28h
0x140007dfc  test    r8, r8
0x140007dff  jz      short loc_140007E0C
0x140007e01  add     r8, r8; Size
0x140007e04  call    memmove_0
0x140007e09  mov     rcx, rax
0x140007e0c  mov     rax, rcx
0x140007e0f  add     rsp, 28h
0x140007e13  retn
```
