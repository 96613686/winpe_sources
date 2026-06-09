# wil::details::HrToNtStatus(long)

- ea: `0x140005cd0`
- end: `0x140005e8c`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `13`
- callee_count: `1`
- tags: ``

## callers

- `0x140003a2c`
- `0x140003b20`
- `0x140003ba0`
- `0x140003c24`
- `0x140003c7c`
- `0x1400041d8`
- `0x1400051f8`
- `0x140005f80`
- `0x1400067a0`
- `0x140018905`
- `0x140018950`
- `0x140018a13`
- `0x140018a5e`

## callees

- `0x140005cd0`

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
0x140005cd0  mov     eax, 800700EAh
0x140005cd5  cmp     ecx, eax
0x140005cd7  jg      loc_140005DAC
0x140005cdd  jz      loc_140005DA2
0x140005ce3  mov     eax, 80070057h
0x140005ce8  cmp     ecx, eax
0x140005cea  jg      short loc_140005D56
0x140005cec  jz      short loc_140005D4C
0x140005cee  cmp     ecx, 80004005h
0x140005cf4  jz      short loc_140005D42
0x140005cf6  cmp     ecx, 80070001h
0x140005cfc  jz      short loc_140005D38
0x140005cfe  cmp     ecx, 80070002h
0x140005d04  jz      short loc_140005D2E
0x140005d06  cmp     ecx, 80070003h
0x140005d0c  jz      short loc_140005D24
0x140005d0e  cmp     ecx, 8007000Eh
0x140005d14  jnz     loc_140005E31
0x140005d1a  mov     ecx, 0C0000017h
0x140005d1f  jmp     loc_140005E89
0x140005d24  mov     ecx, 0C000003Ah
0x140005d29  jmp     loc_140005E89
0x140005d2e  mov     ecx, 0C0000034h
0x140005d33  jmp     loc_140005E89
0x140005d38  mov     ecx, 0C0000002h
0x140005d3d  jmp     loc_140005E89
0x140005d42  mov     ecx, 0C0000001h
0x140005d47  jmp     loc_140005E89
0x140005d4c  mov     ecx, 0C000000Dh
0x140005d51  jmp     loc_140005E89
0x140005d56  cmp     ecx, 80070070h
0x140005d5c  jz      short loc_140005D98
0x140005d5e  cmp     ecx, 8007007Ah
0x140005d64  jz      short loc_140005D8E
0x140005d66  cmp     ecx, 8007007Bh
0x140005d6c  jz      short loc_140005D84
0x140005d6e  cmp     ecx, 8007007Eh
0x140005d74  jnz     loc_140005E31
0x140005d7a  mov     ecx, 0C0000135h
0x140005d7f  jmp     loc_140005E89
0x140005d84  mov     ecx, 0C0000033h
0x140005d89  jmp     loc_140005E89
0x140005d8e  mov     ecx, 0C0000023h
0x140005d93  jmp     loc_140005E89
0x140005d98  mov     ecx, 0C000007Fh
0x140005d9d  jmp     loc_140005E89
0x140005da2  mov     ecx, 80000005h
0x140005da7  jmp     loc_140005E89
0x140005dac  mov     eax, 8007047Eh
0x140005db1  cmp     ecx, eax
0x140005db3  jg      short loc_140005E15
0x140005db5  jz      short loc_140005E0E
0x140005db7  cmp     ecx, 80070216h
0x140005dbd  jz      short loc_140005E07
0x140005dbf  cmp     ecx, 8007023Eh
0x140005dc5  jz      short loc_140005DFD
0x140005dc7  cmp     ecx, 80070246h
0x140005dcd  jz      short loc_140005DF3
0x140005dcf  cmp     ecx, 80070247h
0x140005dd5  jz      short loc_140005DE9
0x140005dd7  cmp     ecx, 80070272h
0x140005ddd  jnz     short loc_140005E31
0x140005ddf  mov     ecx, 0C0000273h
0x140005de4  jmp     loc_140005E89
0x140005de9  mov     ecx, 0C0000163h
0x140005dee  jmp     loc_140005E89
0x140005df3  mov     ecx, 0C0000161h
0x140005df8  jmp     loc_140005E89
0x140005dfd  mov     ecx, 0C0000025h
0x140005e02  jmp     loc_140005E89
0x140005e07  mov     ecx, 0C0000095h
0x140005e0c  jmp     short loc_140005E89
0x140005e0e  mov     ecx, 0C0000059h
0x140005e13  jmp     short loc_140005E89
0x140005e15  cmp     ecx, 8007050Ch
0x140005e1b  jz      short loc_140005E84
0x140005e1d  cmp     ecx, 8007054Fh
0x140005e23  jz      short loc_140005E7D
0x140005e25  cmp     ecx, 800705B9h
0x140005e2b  jz      short loc_140005E76
0x140005e2d  test    ecx, ecx
0x140005e2f  jz      short loc_140005E72
0x140005e31  bt      ecx, 1Ch
0x140005e35  jnb     short loc_140005E3D
0x140005e37  btr     ecx, 1Ch
0x140005e3b  jmp     short loc_140005E89
0x140005e3d  mov     eax, ecx
0x140005e3f  and     eax, 1FFF0000h
0x140005e44  cmp     eax, 70000h
0x140005e49  jnz     short loc_140005E5C
0x140005e4b  movzx   ecx, cx
0x140005e4e  mov     eax, ecx
0x140005e50  or      eax, 0C0070000h
0x140005e55  test    ecx, ecx
0x140005e57  cmovnz  ecx, eax
0x140005e5a  jmp     short loc_140005E89
0x140005e5c  cmp     eax, 90000h
0x140005e61  jnz     short loc_140005E7D
0x140005e63  test    ecx, ecx
0x140005e65  jle     short loc_140005E89
0x140005e67  movzx   ecx, cx
0x140005e6a  or      ecx, 0C0090000h
0x140005e70  jmp     short loc_140005E89
0x140005e72  xor     ecx, ecx
0x140005e74  jmp     short loc_140005E89
0x140005e76  mov     ecx, 0C000A083h
0x140005e7b  jmp     short loc_140005E89
0x140005e7d  mov     ecx, 0C00000E5h
0x140005e82  jmp     short loc_140005E89
0x140005e84  mov     ecx, 0C000042Bh
0x140005e89  mov     eax, ecx
0x140005e8b  retn
```
