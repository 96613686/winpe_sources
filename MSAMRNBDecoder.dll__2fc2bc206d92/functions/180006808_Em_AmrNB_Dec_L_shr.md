# Em_AmrNB_Dec_L_shr

- ea: `0x180006808`
- end: `0x18000683b`
- name: `Em_AmrNB_Dec_L_shr`
- size: `51`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800067ac`
- `0x180006844`
- `0x180006eb4`
- `0x180007138`

## callees

- `0x1800067ac`
- `0x180006808`

## pseudocode

```c
__int64 __fastcall Em_AmrNB_Dec_L_shr(__int64 a1, __int16 a2)
{
  __int16 v3; // dx

  if ( a2 >= 0 )
  {
    if ( a2 < 31 )
      return (unsigned int)((int)a1 >> a2);
    else
      return (unsigned int)((int)a1 >> 31);
  }
  else
  {
    v3 = -32;
    if ( a2 >= -32 )
      v3 = a2;
    return Em_AmrNB_Dec_L_shl(a1, -v3);
  }
}

```

## disassembly

```asm
0x180006808  movzx   r8d, dx
0x18000680c  mov     eax, ecx
0x18000680e  test    dx, dx
0x180006811  jns     short loc_180006829
0x180006813  mov     edx, 0FFFFFFE0h
0x180006818  cmp     r8w, dx
0x18000681c  cmovge  dx, r8w
0x180006821  neg     dx
0x180006824  jmp     Em_AmrNB_Dec_L_shl
0x180006829  cmp     r8w, 1Fh
0x18000682e  jl      short loc_180006835
0x180006830  sar     eax, 1Fh
0x180006833  jmp     short locret_18000683A
0x180006835  mov     cl, r8b
0x180006838  sar     eax, cl
0x18000683a  retn
```
