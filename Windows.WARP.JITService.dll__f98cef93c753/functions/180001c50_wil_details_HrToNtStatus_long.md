# wil::details::HrToNtStatus(long)

- ea: `0x180001c50`
- end: `0x180001e0f`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `447`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1800017d0`
- `0x180002920`
- `0x180006c04`
- `0x180006cb8`
- `0x180006f38`
- `0x180006f88`

## callees

- `0x180001c50`

## pseudocode

```c
__int64 __fastcall wil::details::HrToNtStatus(wil::details *this)
{
  unsigned int v1; // ecx
  int v2; // eax
  unsigned int v3; // eax

  if ( (int)this > -2147024662 )
  {
    if ( (int)this > -2147023746 )
    {
      switch ( (_DWORD)this )
      {
        case 0x8007050C:
          return (unsigned int)-1073740757;
        case 0x8007054F:
          return (unsigned int)-1073741595;
        case 0x800705B9:
          return (unsigned int)-1073700733;
        case 0:
          return 0;
      }
    }
    else
    {
      switch ( (_DWORD)this )
      {
        case 0x8007047E:
          return (unsigned int)-1073741735;
        case 0x80070216:
          return (unsigned int)-1073741675;
        case 0x8007023E:
          return (unsigned int)-1073741787;
        case 0x80070246:
          return (unsigned int)-1073741471;
        case 0x80070247:
          return (unsigned int)-1073741469;
        case 0x80070272:
          return (unsigned int)-1073741197;
      }
    }
  }
  else
  {
    if ( (_DWORD)this == -2147024662 )
      return (unsigned int)-2147483643;
    if ( (int)this > -2147024809 )
    {
      switch ( (_DWORD)this )
      {
        case 0x80070070:
          return (unsigned int)-1073741697;
        case 0x8007007A:
          return (unsigned int)-1073741789;
        case 0x8007007B:
          return (unsigned int)-1073741773;
        case 0x8007007E:
          return (unsigned int)-1073741515;
      }
    }
    else
    {
      switch ( (_DWORD)this )
      {
        case 0x80070057:
          return (unsigned int)-1073741811;
        case 0x80004005:
          return (unsigned int)-1073741823;
        case 0x80070001:
          return (unsigned int)-1073741822;
        case 0x80070002:
          return (unsigned int)-1073741772;
        case 0x80070003:
          return (unsigned int)-1073741766;
        case 0x8007000E:
          return (unsigned int)-1073741801;
      }
    }
  }
  if ( ((unsigned int)this & 0x10000000) != 0 )
    return (unsigned int)this & 0xEFFFFFFF;
  if ( ((unsigned int)this & 0x1FFF0000) == 0x70000 )
  {
    v2 = (unsigned __int16)this;
    v1 = (unsigned __int16)this | 0xC0070000;
    if ( !v2 )
      return 0;
    return v1;
  }
  if ( ((unsigned int)this & 0x1FFF0000) != 0x90000 )
    return (unsigned int)-1073741595;
  v3 = (unsigned __int16)this | 0xC0090000;
  if ( (int)this <= 0 )
    return (unsigned int)this;
  return v3;
}

```

## disassembly

```asm
0x180001c50  mov     eax, 800700EAh
0x180001c55  cmp     ecx, eax
0x180001c57  jg      loc_180001D2C
0x180001c5d  jz      loc_180001D22
0x180001c63  mov     eax, 80070057h
0x180001c68  cmp     ecx, eax
0x180001c6a  jg      short loc_180001CD6
0x180001c6c  jz      short loc_180001CCC
0x180001c6e  cmp     ecx, 80004005h
0x180001c74  jz      short loc_180001CC2
0x180001c76  cmp     ecx, 80070001h
0x180001c7c  jz      short loc_180001CB8
0x180001c7e  cmp     ecx, 80070002h
0x180001c84  jz      short loc_180001CAE
0x180001c86  cmp     ecx, 80070003h
0x180001c8c  jz      short loc_180001CA4
0x180001c8e  cmp     ecx, 8007000Eh
0x180001c94  jnz     loc_180001DB1
0x180001c9a  mov     ecx, 0C0000017h
0x180001c9f  jmp     loc_180001E0C
0x180001ca4  mov     ecx, 0C000003Ah
0x180001ca9  jmp     loc_180001E0C
0x180001cae  mov     ecx, 0C0000034h
0x180001cb3  jmp     loc_180001E0C
0x180001cb8  mov     ecx, 0C0000002h
0x180001cbd  jmp     loc_180001E0C
0x180001cc2  mov     ecx, 0C0000001h
0x180001cc7  jmp     loc_180001E0C
0x180001ccc  mov     ecx, 0C000000Dh
0x180001cd1  jmp     loc_180001E0C
0x180001cd6  cmp     ecx, 80070070h
0x180001cdc  jz      short loc_180001D18
0x180001cde  cmp     ecx, 8007007Ah
0x180001ce4  jz      short loc_180001D0E
0x180001ce6  cmp     ecx, 8007007Bh
0x180001cec  jz      short loc_180001D04
0x180001cee  cmp     ecx, 8007007Eh
0x180001cf4  jnz     loc_180001DB1
0x180001cfa  mov     ecx, 0C0000135h
0x180001cff  jmp     loc_180001E0C
0x180001d04  mov     ecx, 0C0000033h
0x180001d09  jmp     loc_180001E0C
0x180001d0e  mov     ecx, 0C0000023h
0x180001d13  jmp     loc_180001E0C
0x180001d18  mov     ecx, 0C000007Fh
0x180001d1d  jmp     loc_180001E0C
0x180001d22  mov     ecx, 80000005h
0x180001d27  jmp     loc_180001E0C
0x180001d2c  mov     eax, 8007047Eh
0x180001d31  cmp     ecx, eax
0x180001d33  jg      short loc_180001D95
0x180001d35  jz      short loc_180001D8E
0x180001d37  cmp     ecx, 80070216h
0x180001d3d  jz      short loc_180001D87
0x180001d3f  cmp     ecx, 8007023Eh
0x180001d45  jz      short loc_180001D7D
0x180001d47  cmp     ecx, 80070246h
0x180001d4d  jz      short loc_180001D73
0x180001d4f  cmp     ecx, 80070247h
0x180001d55  jz      short loc_180001D69
0x180001d57  cmp     ecx, 80070272h
0x180001d5d  jnz     short loc_180001DB1
0x180001d5f  mov     ecx, 0C0000273h
0x180001d64  jmp     loc_180001E0C
0x180001d69  mov     ecx, 0C0000163h
0x180001d6e  jmp     loc_180001E0C
0x180001d73  mov     ecx, 0C0000161h
0x180001d78  jmp     loc_180001E0C
0x180001d7d  mov     ecx, 0C0000025h
0x180001d82  jmp     loc_180001E0C
0x180001d87  mov     ecx, 0C0000095h
0x180001d8c  jmp     short loc_180001E0C
0x180001d8e  mov     ecx, 0C0000059h
0x180001d93  jmp     short loc_180001E0C
0x180001d95  cmp     ecx, 8007050Ch
0x180001d9b  jz      short loc_180001E07
0x180001d9d  cmp     ecx, 8007054Fh
0x180001da3  jz      short loc_180001E00
0x180001da5  cmp     ecx, 800705B9h
0x180001dab  jz      short loc_180001DF9
0x180001dad  test    ecx, ecx
0x180001daf  jz      short loc_180001DF5
0x180001db1  bt      ecx, 1Ch
0x180001db5  jnb     short loc_180001DBD
0x180001db7  btr     ecx, 1Ch
0x180001dbb  jmp     short loc_180001E0C
0x180001dbd  mov     eax, ecx
0x180001dbf  and     eax, 1FFF0000h
0x180001dc4  cmp     eax, 70000h
0x180001dc9  jnz     short loc_180001DDD
0x180001dcb  movzx   eax, cx
0x180001dce  mov     ecx, eax
0x180001dd0  or      ecx, 0C0070000h
0x180001dd6  test    eax, eax
0x180001dd8  cmovz   ecx, eax
0x180001ddb  jmp     short loc_180001E0C
0x180001ddd  cmp     eax, 90000h
0x180001de2  jnz     short loc_180001E00
0x180001de4  movzx   eax, cx
0x180001de7  or      eax, 0C0090000h
0x180001dec  test    ecx, ecx
0x180001dee  cmovle  eax, ecx
0x180001df1  mov     ecx, eax
0x180001df3  jmp     short loc_180001E0C
0x180001df5  xor     ecx, ecx
0x180001df7  jmp     short loc_180001E0C
0x180001df9  mov     ecx, 0C000A083h
0x180001dfe  jmp     short loc_180001E0C
0x180001e00  mov     ecx, 0C00000E5h
0x180001e05  jmp     short loc_180001E0C
0x180001e07  mov     ecx, 0C000042Bh
0x180001e0c  mov     eax, ecx
0x180001e0e  retn
```
