# WdipValidateMessagePayloadRange

- ea: `0x18000c90c`
- end: `0x18000c936`
- name: `WdipValidateMessagePayloadRange`
- size: `42`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180002510`
- `0x1800054f0`
- `0x18000b7ec`
- `0x18000c21c`
- `0x180014df0`

## callees

- `0x18000c90c`

## pseudocode

```c
__int64 __fastcall WdipValidateMessagePayloadRange(unsigned __int64 a1, unsigned int a2, unsigned __int64 a3)
{
  unsigned __int64 v3; // rcx
  unsigned __int64 v4; // rax

  if ( a1 < 0x28 )
    return 2147942487LL;
  v3 = a1 - 40;
  if ( a2 > v3 )
    return 2147942487LL;
  v4 = a3 + a2;
  if ( v4 < a3 )
    return 2147942487LL;
  else
    return v3 < v4 ? 0x80070057 : 0;
}

```

## disassembly

```asm
0x18000c90c  cmp     rcx, 28h ; '('
0x18000c910  jb      short loc_18000C930
0x18000c912  add     rcx, 0FFFFFFFFFFFFFFD8h
0x18000c916  mov     eax, edx
0x18000c918  cmp     rax, rcx
0x18000c91b  ja      short loc_18000C930
0x18000c91d  add     rax, r8
0x18000c920  cmp     rax, r8
0x18000c923  jb      short loc_18000C930
0x18000c925  cmp     rcx, rax
0x18000c928  sbb     eax, eax
0x18000c92a  and     eax, 80070057h
0x18000c92f  retn
0x18000c930  mov     eax, 80070057h
0x18000c935  retn
```
