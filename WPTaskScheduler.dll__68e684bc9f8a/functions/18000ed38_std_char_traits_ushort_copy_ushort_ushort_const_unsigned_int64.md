# std::char_traits<ushort>::copy(ushort *,ushort const *,unsigned __int64)

- ea: `0x18000ed38`
- end: `0x18000ed54`
- name: `?copy@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z`
- size: `28`
- prototype: `void *__fastcall(void *, const void *, __int64)`
- caller_count: `8`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000ae10`
- `0x18000af60`
- `0x18000b0cc`
- `0x18000b300`
- `0x18000b420`
- `0x18000b4f0`
- `0x18000ea98`
- `0x18000ebbc`

## callees

- `0x18000ed38`
- `0x180010276`

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
0x18000ed38  sub     rsp, 28h
0x18000ed3c  test    r8, r8
0x18000ed3f  jz      short loc_18000ED4C
0x18000ed41  add     r8, r8; Size
0x18000ed44  call    memcpy_0
0x18000ed49  mov     rcx, rax
0x18000ed4c  mov     rax, rcx
0x18000ed4f  add     rsp, 28h
0x18000ed53  retn
```
