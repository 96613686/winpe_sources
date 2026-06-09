# wil::details::HrToNtStatus(long)

- ea: `0x180007c78`
- end: `0x180007e34`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180007bec`
- `0x180008e04`
- `0x180008e74`
- `0x180008ec4`
- `0x180008f28`
- `0x18000a2f8`

## callees

- `0x180007c78`

## pseudocode

```c
__int64 __fastcall wil::details::HrToNtStatus(wil::details *this)
{
  if ( (int)this > -2147024662 )
  {
    if ( (int)this > -2147023746 )
    {
      switch ( (_DWORD)this )
      {
        case 0x8007050C:
          LODWORD(this) = -1073740757;
          return (unsigned int)this;
        case 0x8007054F:
          goto LABEL_53;
        case 0x800705B9:
          LODWORD(this) = -1073700733;
          return (unsigned int)this;
        case 0:
          LODWORD(this) = 0;
          return (unsigned int)this;
      }
    }
    else
    {
      switch ( (_DWORD)this )
      {
        case 0x8007047E:
          LODWORD(this) = -1073741735;
          return (unsigned int)this;
        case 0x80070216:
          LODWORD(this) = -1073741675;
          return (unsigned int)this;
        case 0x8007023E:
          LODWORD(this) = -1073741787;
          return (unsigned int)this;
        case 0x80070246:
          LODWORD(this) = -1073741471;
          return (unsigned int)this;
        case 0x80070247:
          LODWORD(this) = -1073741469;
          return (unsigned int)this;
        case 0x80070272:
          LODWORD(this) = -1073741197;
          return (unsigned int)this;
      }
    }
  }
  else
  {
    if ( (_DWORD)this == -2147024662 )
    {
      LODWORD(this) = -2147483643;
      return (unsigned int)this;
    }
    if ( (int)this > -2147024809 )
    {
      switch ( (_DWORD)this )
      {
        case 0x80070070:
          LODWORD(this) = -1073741697;
          return (unsigned int)this;
        case 0x8007007A:
          LODWORD(this) = -1073741789;
          return (unsigned int)this;
        case 0x8007007B:
          LODWORD(this) = -1073741773;
          return (unsigned int)this;
        case 0x8007007E:
          LODWORD(this) = -1073741515;
          return (unsigned int)this;
      }
    }
    else
    {
      switch ( (_DWORD)this )
      {
        case 0x80070057:
          LODWORD(this) = -1073741811;
          return (unsigned int)this;
        case 0x80004005:
          LODWORD(this) = -1073741823;
          return (unsigned int)this;
        case 0x80070001:
          LODWORD(this) = -1073741822;
          return (unsigned int)this;
        case 0x80070002:
          LODWORD(this) = -1073741772;
          return (unsigned int)this;
        case 0x80070003:
          LODWORD(this) = -1073741766;
          return (unsigned int)this;
        case 0x8007000E:
          LODWORD(this) = -1073741801;
          return (unsigned int)this;
      }
    }
  }
  if ( ((unsigned int)this & 0x10000000) != 0 )
  {
    LODWORD(this) = (unsigned int)this & 0xEFFFFFFF;
    return (unsigned int)this;
  }
  if ( ((unsigned int)this & 0x1FFF0000) == 0x70000 )
  {
    LODWORD(this) = (unsigned __int16)this;
    if ( (_WORD)this )
      LODWORD(this) = (unsigned __int16)this | 0xC0070000;
    return (unsigned int)this;
  }
  if ( ((unsigned int)this & 0x1FFF0000) != 0x90000 )
  {
LABEL_53:
    LODWORD(this) = -1073741595;
    return (unsigned int)this;
  }
  if ( (int)this > 0 )
    LODWORD(this) = (unsigned __int16)this | 0xC0090000;
  return (unsigned int)this;
}

```

## disassembly

```asm
0x180007c78  mov     eax, 800700EAh
0x180007c7d  cmp     ecx, eax
0x180007c7f  jg      loc_180007D54
0x180007c85  jz      loc_180007D4A
0x180007c8b  mov     eax, 80070057h
0x180007c90  cmp     ecx, eax
0x180007c92  jg      short loc_180007CFE
0x180007c94  jz      short loc_180007CF4
0x180007c96  cmp     ecx, 80004005h
0x180007c9c  jz      short loc_180007CEA
0x180007c9e  cmp     ecx, 80070001h
0x180007ca4  jz      short loc_180007CE0
0x180007ca6  cmp     ecx, 80070002h
0x180007cac  jz      short loc_180007CD6
0x180007cae  cmp     ecx, 80070003h
0x180007cb4  jz      short loc_180007CCC
0x180007cb6  cmp     ecx, 8007000Eh
0x180007cbc  jnz     loc_180007DD9
0x180007cc2  mov     ecx, 0C0000017h
0x180007cc7  jmp     loc_180007E31
0x180007ccc  mov     ecx, 0C000003Ah
0x180007cd1  jmp     loc_180007E31
0x180007cd6  mov     ecx, 0C0000034h
0x180007cdb  jmp     loc_180007E31
0x180007ce0  mov     ecx, 0C0000002h
0x180007ce5  jmp     loc_180007E31
0x180007cea  mov     ecx, 0C0000001h
0x180007cef  jmp     loc_180007E31
0x180007cf4  mov     ecx, 0C000000Dh
0x180007cf9  jmp     loc_180007E31
0x180007cfe  cmp     ecx, 80070070h
0x180007d04  jz      short loc_180007D40
0x180007d06  cmp     ecx, 8007007Ah
0x180007d0c  jz      short loc_180007D36
0x180007d0e  cmp     ecx, 8007007Bh
0x180007d14  jz      short loc_180007D2C
0x180007d16  cmp     ecx, 8007007Eh
0x180007d1c  jnz     loc_180007DD9
0x180007d22  mov     ecx, 0C0000135h
0x180007d27  jmp     loc_180007E31
0x180007d2c  mov     ecx, 0C0000033h
0x180007d31  jmp     loc_180007E31
0x180007d36  mov     ecx, 0C0000023h
0x180007d3b  jmp     loc_180007E31
0x180007d40  mov     ecx, 0C000007Fh
0x180007d45  jmp     loc_180007E31
0x180007d4a  mov     ecx, 80000005h
0x180007d4f  jmp     loc_180007E31
0x180007d54  mov     eax, 8007047Eh
0x180007d59  cmp     ecx, eax
0x180007d5b  jg      short loc_180007DBD
0x180007d5d  jz      short loc_180007DB6
0x180007d5f  cmp     ecx, 80070216h
0x180007d65  jz      short loc_180007DAF
0x180007d67  cmp     ecx, 8007023Eh
0x180007d6d  jz      short loc_180007DA5
0x180007d6f  cmp     ecx, 80070246h
0x180007d75  jz      short loc_180007D9B
0x180007d77  cmp     ecx, 80070247h
0x180007d7d  jz      short loc_180007D91
0x180007d7f  cmp     ecx, 80070272h
0x180007d85  jnz     short loc_180007DD9
0x180007d87  mov     ecx, 0C0000273h
0x180007d8c  jmp     loc_180007E31
0x180007d91  mov     ecx, 0C0000163h
0x180007d96  jmp     loc_180007E31
0x180007d9b  mov     ecx, 0C0000161h
0x180007da0  jmp     loc_180007E31
0x180007da5  mov     ecx, 0C0000025h
0x180007daa  jmp     loc_180007E31
0x180007daf  mov     ecx, 0C0000095h
0x180007db4  jmp     short loc_180007E31
0x180007db6  mov     ecx, 0C0000059h
0x180007dbb  jmp     short loc_180007E31
0x180007dbd  cmp     ecx, 8007050Ch
0x180007dc3  jz      short loc_180007E2C
0x180007dc5  cmp     ecx, 8007054Fh
0x180007dcb  jz      short loc_180007E25
0x180007dcd  cmp     ecx, 800705B9h
0x180007dd3  jz      short loc_180007E1E
0x180007dd5  test    ecx, ecx
0x180007dd7  jz      short loc_180007E1A
0x180007dd9  bt      ecx, 1Ch
0x180007ddd  jnb     short loc_180007DE5
0x180007ddf  btr     ecx, 1Ch
0x180007de3  jmp     short loc_180007E31
0x180007de5  mov     eax, ecx
0x180007de7  and     eax, 1FFF0000h
0x180007dec  cmp     eax, 70000h
0x180007df1  jnz     short loc_180007E04
0x180007df3  movzx   ecx, cx
0x180007df6  mov     eax, ecx
0x180007df8  or      eax, 0C0070000h
0x180007dfd  test    ecx, ecx
0x180007dff  cmovnz  ecx, eax
0x180007e02  jmp     short loc_180007E31
0x180007e04  cmp     eax, 90000h
0x180007e09  jnz     short loc_180007E25
0x180007e0b  test    ecx, ecx
0x180007e0d  jle     short loc_180007E31
0x180007e0f  movzx   ecx, cx
0x180007e12  or      ecx, 0C0090000h
0x180007e18  jmp     short loc_180007E31
0x180007e1a  xor     ecx, ecx
0x180007e1c  jmp     short loc_180007E31
0x180007e1e  mov     ecx, 0C000A083h
0x180007e23  jmp     short loc_180007E31
0x180007e25  mov     ecx, 0C00000E5h
0x180007e2a  jmp     short loc_180007E31
0x180007e2c  mov     ecx, 0C000042Bh
0x180007e31  mov     eax, ecx
0x180007e33  retn
```
