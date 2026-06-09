# av_compare_mod

- ea: `0x180043d60`
- end: `0x180043d7e`
- name: `av_compare_mod`
- size: `30`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
unsigned __int64 __fastcall av_compare_mod(__int64 a1, __int64 a2, unsigned __int64 a3)
{
  unsigned __int64 v3; // rcx
  unsigned __int64 result; // rax

  v3 = (a3 - 1) & (a1 - a2);
  result = v3 - a3;
  if ( v3 <= a3 >> 1 )
    return v3;
  return result;
}

```

## disassembly

```asm
0x180043d60  sub     rcx, rdx
0x180043d63  lea     rax, [r8-1]
0x180043d67  and     rcx, rax
0x180043d6a  mov     rdx, r8
0x180043d6d  mov     rax, rcx
0x180043d70  shr     rdx, 1
0x180043d73  sub     rax, r8
0x180043d76  cmp     rcx, rdx
0x180043d79  cmovbe  rax, rcx
0x180043d7d  retn
```
