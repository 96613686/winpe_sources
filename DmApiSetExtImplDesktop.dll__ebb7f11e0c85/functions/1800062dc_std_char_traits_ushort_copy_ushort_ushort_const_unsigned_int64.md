# std::char_traits<ushort>::copy(ushort *,ushort const *,unsigned __int64)

- ea: `0x1800062dc`
- end: `0x1800062f9`
- name: `?copy@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z`
- size: `29`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800059a4`
- `0x180005c60`
- `0x180005d60`
- `0x180005e18`
- `0x1800060cc`
- `0x1800061f0`

## callees

- `0x1800062dc`
- `0x180009ee6`

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
0x1800062dc  sub     rsp, 28h
0x1800062e0  test    r8, r8
0x1800062e3  jz      short loc_1800062F0
0x1800062e5  add     r8, r8; Size
0x1800062e8  call    memcpy_0
0x1800062ed  mov     rcx, rax
0x1800062f0  mov     rax, rcx
0x1800062f3  add     rsp, 28h
0x1800062f7  retn
```
