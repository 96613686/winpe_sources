# std::char_traits<ushort>::move(ushort *,ushort const *,unsigned __int64)

- ea: `0x140008228`
- end: `0x140008245`
- name: `?move@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z`
- size: `29`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14000363c`
- `0x140008034`

## callees

- `0x140001e12`
- `0x140008228`

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
0x140008228  sub     rsp, 28h
0x14000822c  test    r8, r8
0x14000822f  jz      short loc_14000823C
0x140008231  add     r8, r8; Size
0x140008234  call    memmove_0
0x140008239  mov     rcx, rax
0x14000823c  mov     rax, rcx
0x14000823f  add     rsp, 28h
0x140008243  retn
```
