# MapErrorCodes(long)

- ea: `0x18000e39c`
- end: `0x18000e3b9`
- name: `?MapErrorCodes@@YAJJ@Z`
- size: `29`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x18000eb30`
- `0x180015b30`
- `0x180015d10`
- `0x180016060`
- `0x180016400`
- `0x180016718`
- `0x180017ec0`
- `0x180018040`

## callees

- `0x18000e39c`

## pseudocode

```c
__int64 __fastcall MapErrorCodes(unsigned int a1)
{
  __int64 result; // rax

  if ( a1 == -805306355 )
    return 2147942487LL;
  result = 2147942405LL;
  if ( a1 != -805306334 )
    return a1;
  return result;
}

```

## disassembly

```asm
0x18000e39c  cmp     ecx, 0D000000Dh
0x18000e3a2  jz      short loc_18000E3B3
0x18000e3a4  cmp     ecx, 0D0000022h
0x18000e3aa  mov     eax, 80070005h
0x18000e3af  cmovnz  eax, ecx
0x18000e3b2  retn
0x18000e3b3  mov     eax, 80070057h
0x18000e3b8  retn
```
