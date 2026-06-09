# std::char_traits<ushort>::move(ushort *,ushort const *,unsigned __int64)

- ea: `0x14000865c`
- end: `0x140008678`
- name: `?move@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z`
- size: `28`
- prototype: `void *__fastcall(void *, const void *, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140008120`
- `0x14000858c`
- `0x14000b7a0`
- `0x14000c628`

## callees

- `0x14000865c`
- `0x140013ac3`

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
0x14000865c  sub     rsp, 28h
0x140008660  test    r8, r8
0x140008663  jz      short loc_140008670
0x140008665  add     r8, r8; Size
0x140008668  call    memmove_0
0x14000866d  mov     rcx, rax
0x140008670  mov     rax, rcx
0x140008673  add     rsp, 28h
0x140008677  retn
```
