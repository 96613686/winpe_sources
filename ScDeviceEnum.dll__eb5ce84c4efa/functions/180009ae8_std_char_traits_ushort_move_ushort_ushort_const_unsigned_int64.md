# std::char_traits<ushort>::move(ushort *,ushort const *,unsigned __int64)

- ea: `0x180009ae8`
- end: `0x180009b04`
- name: `?move@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z`
- size: `28`
- prototype: `void *__fastcall(void *, const void *, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000904c`
- `0x180009a38`
- `0x1800117d0`

## callees

- `0x180001f32`
- `0x180009ae8`

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
0x180009ae8  sub     rsp, 28h
0x180009aec  test    r8, r8
0x180009aef  jz      short loc_180009AFC
0x180009af1  add     r8, r8; Size
0x180009af4  call    memmove_0
0x180009af9  mov     rcx, rax
0x180009afc  mov     rax, rcx
0x180009aff  add     rsp, 28h
0x180009b03  retn
```
