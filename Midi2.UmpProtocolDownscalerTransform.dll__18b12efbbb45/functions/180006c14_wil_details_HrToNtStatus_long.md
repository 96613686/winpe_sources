# wil::details::HrToNtStatus(long)

- ea: `0x180006c14`
- end: `0x180006dd0`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180003cb8`
- `0x180003d60`
- `0x180003db0`
- `0x180003e68`
- `0x1800061d8`
- `0x180006f40`

## callees

- `0x180006c14`

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
0x180006c14  mov     eax, 800700EAh
0x180006c19  cmp     ecx, eax
0x180006c1b  jg      loc_180006CF0
0x180006c21  jz      loc_180006CE6
0x180006c27  mov     eax, 80070057h
0x180006c2c  cmp     ecx, eax
0x180006c2e  jg      short loc_180006C9A
0x180006c30  jz      short loc_180006C90
0x180006c32  cmp     ecx, 80004005h
0x180006c38  jz      short loc_180006C86
0x180006c3a  cmp     ecx, 80070001h
0x180006c40  jz      short loc_180006C7C
0x180006c42  cmp     ecx, 80070002h
0x180006c48  jz      short loc_180006C72
0x180006c4a  cmp     ecx, 80070003h
0x180006c50  jz      short loc_180006C68
0x180006c52  cmp     ecx, 8007000Eh
0x180006c58  jnz     loc_180006D75
0x180006c5e  mov     ecx, 0C0000017h
0x180006c63  jmp     loc_180006DCD
0x180006c68  mov     ecx, 0C000003Ah
0x180006c6d  jmp     loc_180006DCD
0x180006c72  mov     ecx, 0C0000034h
0x180006c77  jmp     loc_180006DCD
0x180006c7c  mov     ecx, 0C0000002h
0x180006c81  jmp     loc_180006DCD
0x180006c86  mov     ecx, 0C0000001h
0x180006c8b  jmp     loc_180006DCD
0x180006c90  mov     ecx, 0C000000Dh
0x180006c95  jmp     loc_180006DCD
0x180006c9a  cmp     ecx, 80070070h
0x180006ca0  jz      short loc_180006CDC
0x180006ca2  cmp     ecx, 8007007Ah
0x180006ca8  jz      short loc_180006CD2
0x180006caa  cmp     ecx, 8007007Bh
0x180006cb0  jz      short loc_180006CC8
0x180006cb2  cmp     ecx, 8007007Eh
0x180006cb8  jnz     loc_180006D75
0x180006cbe  mov     ecx, 0C0000135h
0x180006cc3  jmp     loc_180006DCD
0x180006cc8  mov     ecx, 0C0000033h
0x180006ccd  jmp     loc_180006DCD
0x180006cd2  mov     ecx, 0C0000023h
0x180006cd7  jmp     loc_180006DCD
0x180006cdc  mov     ecx, 0C000007Fh
0x180006ce1  jmp     loc_180006DCD
0x180006ce6  mov     ecx, 80000005h
0x180006ceb  jmp     loc_180006DCD
0x180006cf0  mov     eax, 8007047Eh
0x180006cf5  cmp     ecx, eax
0x180006cf7  jg      short loc_180006D59
0x180006cf9  jz      short loc_180006D52
0x180006cfb  cmp     ecx, 80070216h
0x180006d01  jz      short loc_180006D4B
0x180006d03  cmp     ecx, 8007023Eh
0x180006d09  jz      short loc_180006D41
0x180006d0b  cmp     ecx, 80070246h
0x180006d11  jz      short loc_180006D37
0x180006d13  cmp     ecx, 80070247h
0x180006d19  jz      short loc_180006D2D
0x180006d1b  cmp     ecx, 80070272h
0x180006d21  jnz     short loc_180006D75
0x180006d23  mov     ecx, 0C0000273h
0x180006d28  jmp     loc_180006DCD
0x180006d2d  mov     ecx, 0C0000163h
0x180006d32  jmp     loc_180006DCD
0x180006d37  mov     ecx, 0C0000161h
0x180006d3c  jmp     loc_180006DCD
0x180006d41  mov     ecx, 0C0000025h
0x180006d46  jmp     loc_180006DCD
0x180006d4b  mov     ecx, 0C0000095h
0x180006d50  jmp     short loc_180006DCD
0x180006d52  mov     ecx, 0C0000059h
0x180006d57  jmp     short loc_180006DCD
0x180006d59  cmp     ecx, 8007050Ch
0x180006d5f  jz      short loc_180006DC8
0x180006d61  cmp     ecx, 8007054Fh
0x180006d67  jz      short loc_180006DC1
0x180006d69  cmp     ecx, 800705B9h
0x180006d6f  jz      short loc_180006DBA
0x180006d71  test    ecx, ecx
0x180006d73  jz      short loc_180006DB6
0x180006d75  bt      ecx, 1Ch
0x180006d79  jnb     short loc_180006D81
0x180006d7b  btr     ecx, 1Ch
0x180006d7f  jmp     short loc_180006DCD
0x180006d81  mov     eax, ecx
0x180006d83  and     eax, 1FFF0000h
0x180006d88  cmp     eax, 70000h
0x180006d8d  jnz     short loc_180006DA0
0x180006d8f  movzx   ecx, cx
0x180006d92  mov     eax, ecx
0x180006d94  or      eax, 0C0070000h
0x180006d99  test    ecx, ecx
0x180006d9b  cmovnz  ecx, eax
0x180006d9e  jmp     short loc_180006DCD
0x180006da0  cmp     eax, 90000h
0x180006da5  jnz     short loc_180006DC1
0x180006da7  test    ecx, ecx
0x180006da9  jle     short loc_180006DCD
0x180006dab  movzx   ecx, cx
0x180006dae  or      ecx, 0C0090000h
0x180006db4  jmp     short loc_180006DCD
0x180006db6  xor     ecx, ecx
0x180006db8  jmp     short loc_180006DCD
0x180006dba  mov     ecx, 0C000A083h
0x180006dbf  jmp     short loc_180006DCD
0x180006dc1  mov     ecx, 0C00000E5h
0x180006dc6  jmp     short loc_180006DCD
0x180006dc8  mov     ecx, 0C000042Bh
0x180006dcd  mov     eax, ecx
0x180006dcf  retn
```
