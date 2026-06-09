# std::char_traits<ushort>::copy(ushort *,ushort const *,unsigned __int64)

- ea: `0x18000670c`
- end: `0x180006729`
- name: `?copy@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z`
- size: `29`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180005fb4`
- `0x1800062ac`
- `0x180006530`
- `0x180006620`
- `0x180009d64`
- `0x180009e48`
- `0x180014ba4`

## callees

- `0x18000670c`
- `0x18001f3c2`

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
0x18000670c  sub     rsp, 28h
0x180006710  test    r8, r8
0x180006713  jz      short loc_180006720
0x180006715  add     r8, r8; Size
0x180006718  call    memcpy_0
0x18000671d  mov     rcx, rax
0x180006720  mov     rax, rcx
0x180006723  add     rsp, 28h
0x180006727  retn
```
