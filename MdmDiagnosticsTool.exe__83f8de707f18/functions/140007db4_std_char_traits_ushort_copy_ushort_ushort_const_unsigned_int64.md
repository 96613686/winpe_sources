# std::char_traits<ushort>::copy(ushort *,ushort const *,unsigned __int64)

- ea: `0x140007db4`
- end: `0x140007dd1`
- name: `?copy@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z`
- size: `29`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x14000727c`
- `0x140007610`
- `0x1400078b0`
- `0x1400079a0`
- `0x140007bfc`
- `0x140007cc8`

## callees

- `0x140001e06`
- `0x140007db4`

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
0x140007db4  sub     rsp, 28h
0x140007db8  test    r8, r8
0x140007dbb  jz      short loc_140007DC8
0x140007dbd  add     r8, r8; Size
0x140007dc0  call    memcpy_0
0x140007dc5  mov     rcx, rax
0x140007dc8  mov     rax, rcx
0x140007dcb  add     rsp, 28h
0x140007dcf  retn
```
