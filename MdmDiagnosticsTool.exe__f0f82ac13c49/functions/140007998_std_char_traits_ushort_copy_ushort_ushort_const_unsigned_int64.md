# std::char_traits<ushort>::copy(ushort *,ushort const *,unsigned __int64)

- ea: `0x140007998`
- end: `0x1400079b4`
- name: `?copy@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z`
- size: `28`
- prototype: `void *__fastcall(void *, const void *, __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140006e80`
- `0x140007204`
- `0x14000749c`
- `0x14000758c`
- `0x1400077e4`
- `0x1400078b0`

## callees

- `0x140001dd6`
- `0x140007998`

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
0x140007998  sub     rsp, 28h
0x14000799c  test    r8, r8
0x14000799f  jz      short loc_1400079AC
0x1400079a1  add     r8, r8; Size
0x1400079a4  call    memcpy_0
0x1400079a9  mov     rcx, rax
0x1400079ac  mov     rax, rcx
0x1400079af  add     rsp, 28h
0x1400079b3  retn
```
