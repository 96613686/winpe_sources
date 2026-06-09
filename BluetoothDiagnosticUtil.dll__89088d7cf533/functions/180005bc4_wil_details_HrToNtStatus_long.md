# wil::details::HrToNtStatus(long)

- ea: `0x180005bc4`
- end: `0x180005d80`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x180001df8`
- `0x180001fd0`
- `0x180002088`
- `0x1800020e8`
- `0x180002208`
- `0x180005134`
- `0x180005ee8`
- `0x180007090`
- `0x18000a3aa`
- `0x18000a415`
- `0x18000a4de`
- `0x18000a549`

## callees

- `0x180005bc4`

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
0x180005bc4  mov     eax, 800700EAh
0x180005bc9  cmp     ecx, eax
0x180005bcb  jg      loc_180005CA0
0x180005bd1  jz      loc_180005C96
0x180005bd7  mov     eax, 80070057h
0x180005bdc  cmp     ecx, eax
0x180005bde  jg      short loc_180005C4A
0x180005be0  jz      short loc_180005C40
0x180005be2  cmp     ecx, 80004005h
0x180005be8  jz      short loc_180005C36
0x180005bea  cmp     ecx, 80070001h
0x180005bf0  jz      short loc_180005C2C
0x180005bf2  cmp     ecx, 80070002h
0x180005bf8  jz      short loc_180005C22
0x180005bfa  cmp     ecx, 80070003h
0x180005c00  jz      short loc_180005C18
0x180005c02  cmp     ecx, 8007000Eh
0x180005c08  jnz     loc_180005D25
0x180005c0e  mov     ecx, 0C0000017h
0x180005c13  jmp     loc_180005D7D
0x180005c18  mov     ecx, 0C000003Ah
0x180005c1d  jmp     loc_180005D7D
0x180005c22  mov     ecx, 0C0000034h
0x180005c27  jmp     loc_180005D7D
0x180005c2c  mov     ecx, 0C0000002h
0x180005c31  jmp     loc_180005D7D
0x180005c36  mov     ecx, 0C0000001h
0x180005c3b  jmp     loc_180005D7D
0x180005c40  mov     ecx, 0C000000Dh
0x180005c45  jmp     loc_180005D7D
0x180005c4a  cmp     ecx, 80070070h
0x180005c50  jz      short loc_180005C8C
0x180005c52  cmp     ecx, 8007007Ah
0x180005c58  jz      short loc_180005C82
0x180005c5a  cmp     ecx, 8007007Bh
0x180005c60  jz      short loc_180005C78
0x180005c62  cmp     ecx, 8007007Eh
0x180005c68  jnz     loc_180005D25
0x180005c6e  mov     ecx, 0C0000135h
0x180005c73  jmp     loc_180005D7D
0x180005c78  mov     ecx, 0C0000033h
0x180005c7d  jmp     loc_180005D7D
0x180005c82  mov     ecx, 0C0000023h
0x180005c87  jmp     loc_180005D7D
0x180005c8c  mov     ecx, 0C000007Fh
0x180005c91  jmp     loc_180005D7D
0x180005c96  mov     ecx, 80000005h
0x180005c9b  jmp     loc_180005D7D
0x180005ca0  mov     eax, 8007047Eh
0x180005ca5  cmp     ecx, eax
0x180005ca7  jg      short loc_180005D09
0x180005ca9  jz      short loc_180005D02
0x180005cab  cmp     ecx, 80070216h
0x180005cb1  jz      short loc_180005CFB
0x180005cb3  cmp     ecx, 8007023Eh
0x180005cb9  jz      short loc_180005CF1
0x180005cbb  cmp     ecx, 80070246h
0x180005cc1  jz      short loc_180005CE7
0x180005cc3  cmp     ecx, 80070247h
0x180005cc9  jz      short loc_180005CDD
0x180005ccb  cmp     ecx, 80070272h
0x180005cd1  jnz     short loc_180005D25
0x180005cd3  mov     ecx, 0C0000273h
0x180005cd8  jmp     loc_180005D7D
0x180005cdd  mov     ecx, 0C0000163h
0x180005ce2  jmp     loc_180005D7D
0x180005ce7  mov     ecx, 0C0000161h
0x180005cec  jmp     loc_180005D7D
0x180005cf1  mov     ecx, 0C0000025h
0x180005cf6  jmp     loc_180005D7D
0x180005cfb  mov     ecx, 0C0000095h
0x180005d00  jmp     short loc_180005D7D
0x180005d02  mov     ecx, 0C0000059h
0x180005d07  jmp     short loc_180005D7D
0x180005d09  cmp     ecx, 8007050Ch
0x180005d0f  jz      short loc_180005D78
0x180005d11  cmp     ecx, 8007054Fh
0x180005d17  jz      short loc_180005D71
0x180005d19  cmp     ecx, 800705B9h
0x180005d1f  jz      short loc_180005D6A
0x180005d21  test    ecx, ecx
0x180005d23  jz      short loc_180005D66
0x180005d25  bt      ecx, 1Ch
0x180005d29  jnb     short loc_180005D31
0x180005d2b  btr     ecx, 1Ch
0x180005d2f  jmp     short loc_180005D7D
0x180005d31  mov     eax, ecx
0x180005d33  and     eax, 1FFF0000h
0x180005d38  cmp     eax, 70000h
0x180005d3d  jnz     short loc_180005D50
0x180005d3f  movzx   ecx, cx
0x180005d42  mov     eax, ecx
0x180005d44  or      eax, 0C0070000h
0x180005d49  test    ecx, ecx
0x180005d4b  cmovnz  ecx, eax
0x180005d4e  jmp     short loc_180005D7D
0x180005d50  cmp     eax, 90000h
0x180005d55  jnz     short loc_180005D71
0x180005d57  test    ecx, ecx
0x180005d59  jle     short loc_180005D7D
0x180005d5b  movzx   ecx, cx
0x180005d5e  or      ecx, 0C0090000h
0x180005d64  jmp     short loc_180005D7D
0x180005d66  xor     ecx, ecx
0x180005d68  jmp     short loc_180005D7D
0x180005d6a  mov     ecx, 0C000A083h
0x180005d6f  jmp     short loc_180005D7D
0x180005d71  mov     ecx, 0C00000E5h
0x180005d76  jmp     short loc_180005D7D
0x180005d78  mov     ecx, 0C000042Bh
0x180005d7d  mov     eax, ecx
0x180005d7f  retn
```
