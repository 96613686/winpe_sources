# std::char_traits<ushort>::copy(ushort *,ushort const *,unsigned __int64)

- ea: `0x14000679c`
- end: `0x1400067b8`
- name: `?copy@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z`
- size: `28`
- prototype: `void *__fastcall(void *, const void *, __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140006230`
- `0x140006480`
- `0x140006538`
- `0x140006604`
- `0x140011c90`
- `0x140011d80`

## callees

- `0x14000679c`
- `0x14001a892`

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
0x14000679c  sub     rsp, 28h
0x1400067a0  test    r8, r8
0x1400067a3  jz      short loc_1400067B0
0x1400067a5  add     r8, r8; Size
0x1400067a8  call    memcpy_0
0x1400067ad  mov     rcx, rax
0x1400067b0  mov     rax, rcx
0x1400067b3  add     rsp, 28h
0x1400067b7  retn
```
