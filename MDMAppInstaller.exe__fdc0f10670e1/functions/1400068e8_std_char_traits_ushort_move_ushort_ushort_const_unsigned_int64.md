# std::char_traits<ushort>::move(ushort *,ushort const *,unsigned __int64)

- ea: `0x1400068e8`
- end: `0x140006904`
- name: `?move@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z`
- size: `28`
- prototype: `void *__fastcall(void *, const void *, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140006818`
- `0x140011604`

## callees

- `0x1400068e8`
- `0x14001a89e`

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
0x1400068e8  sub     rsp, 28h
0x1400068ec  test    r8, r8
0x1400068ef  jz      short loc_1400068FC
0x1400068f1  add     r8, r8; Size
0x1400068f4  call    memmove_0
0x1400068f9  mov     rcx, rax
0x1400068fc  mov     rax, rcx
0x1400068ff  add     rsp, 28h
0x140006903  retn
```
