# Em_AmrNB_Dec_mult

- ea: `0x18000694c`
- end: `0x180006983`
- name: `Em_AmrNB_Dec_mult`
- size: `55`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180004afc`
- `0x180004dd0`
- `0x1800051e0`
- `0x180006ce8`
- `0x180006eb4`
- `0x180007138`

## callees

- `0x18000694c`

## pseudocode

```c
__int64 __fastcall Em_AmrNB_Dec_mult(__int16 a1, __int16 a2)
{
  __int64 result; // rax
  int v3; // r8d
  signed int v4; // ecx

  result = 0x7FFF;
  v3 = (a2 * a1) >> 15;
  v4 = v3 | 0xFFFF0000;
  if ( (v3 & 0x10000) == 0 )
    v4 = v3;
  if ( v4 <= 0x7FFF )
  {
    result = 4294934528LL;
    if ( v4 >= -32768 )
      return (unsigned __int16)v4;
  }
  return result;
}

```

## disassembly

```asm
0x18000694c  movsx   r8d, cx
0x180006950  movsx   eax, dx
0x180006953  imul    r8d, eax
0x180006957  mov     eax, 7FFFh
0x18000695c  sar     r8d, 0Fh
0x180006960  mov     ecx, r8d
0x180006963  or      ecx, 0FFFF0000h
0x180006969  bt      r8d, 10h
0x18000696e  cmovnb  ecx, r8d
0x180006972  cmp     ecx, eax
0x180006974  jg      short locret_180006982
0x180006976  mov     eax, 0FFFF8000h
0x18000697b  cmp     ecx, eax
0x18000697d  jl      short locret_180006982
0x18000697f  movzx   eax, cx
0x180006982  retn
```
