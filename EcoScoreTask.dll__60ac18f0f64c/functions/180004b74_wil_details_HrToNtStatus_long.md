# wil::details::HrToNtStatus(long)

- ea: `0x180004b74`
- end: `0x180004d30`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180002704`
- `0x1800027ac`
- `0x1800027fc`
- `0x1800028b4`
- `0x180004168`
- `0x180004e10`

## callees

- `0x180004b74`

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
0x180004b74  mov     eax, 800700EAh
0x180004b79  cmp     ecx, eax
0x180004b7b  jg      loc_180004C50
0x180004b81  jz      loc_180004C46
0x180004b87  mov     eax, 80070057h
0x180004b8c  cmp     ecx, eax
0x180004b8e  jg      short loc_180004BFA
0x180004b90  jz      short loc_180004BF0
0x180004b92  cmp     ecx, 80004005h
0x180004b98  jz      short loc_180004BE6
0x180004b9a  cmp     ecx, 80070001h
0x180004ba0  jz      short loc_180004BDC
0x180004ba2  cmp     ecx, 80070002h
0x180004ba8  jz      short loc_180004BD2
0x180004baa  cmp     ecx, 80070003h
0x180004bb0  jz      short loc_180004BC8
0x180004bb2  cmp     ecx, 8007000Eh
0x180004bb8  jnz     loc_180004CD5
0x180004bbe  mov     ecx, 0C0000017h
0x180004bc3  jmp     loc_180004D2D
0x180004bc8  mov     ecx, 0C000003Ah
0x180004bcd  jmp     loc_180004D2D
0x180004bd2  mov     ecx, 0C0000034h
0x180004bd7  jmp     loc_180004D2D
0x180004bdc  mov     ecx, 0C0000002h
0x180004be1  jmp     loc_180004D2D
0x180004be6  mov     ecx, 0C0000001h
0x180004beb  jmp     loc_180004D2D
0x180004bf0  mov     ecx, 0C000000Dh
0x180004bf5  jmp     loc_180004D2D
0x180004bfa  cmp     ecx, 80070070h
0x180004c00  jz      short loc_180004C3C
0x180004c02  cmp     ecx, 8007007Ah
0x180004c08  jz      short loc_180004C32
0x180004c0a  cmp     ecx, 8007007Bh
0x180004c10  jz      short loc_180004C28
0x180004c12  cmp     ecx, 8007007Eh
0x180004c18  jnz     loc_180004CD5
0x180004c1e  mov     ecx, 0C0000135h
0x180004c23  jmp     loc_180004D2D
0x180004c28  mov     ecx, 0C0000033h
0x180004c2d  jmp     loc_180004D2D
0x180004c32  mov     ecx, 0C0000023h
0x180004c37  jmp     loc_180004D2D
0x180004c3c  mov     ecx, 0C000007Fh
0x180004c41  jmp     loc_180004D2D
0x180004c46  mov     ecx, 80000005h
0x180004c4b  jmp     loc_180004D2D
0x180004c50  mov     eax, 8007047Eh
0x180004c55  cmp     ecx, eax
0x180004c57  jg      short loc_180004CB9
0x180004c59  jz      short loc_180004CB2
0x180004c5b  cmp     ecx, 80070216h
0x180004c61  jz      short loc_180004CAB
0x180004c63  cmp     ecx, 8007023Eh
0x180004c69  jz      short loc_180004CA1
0x180004c6b  cmp     ecx, 80070246h
0x180004c71  jz      short loc_180004C97
0x180004c73  cmp     ecx, 80070247h
0x180004c79  jz      short loc_180004C8D
0x180004c7b  cmp     ecx, 80070272h
0x180004c81  jnz     short loc_180004CD5
0x180004c83  mov     ecx, 0C0000273h
0x180004c88  jmp     loc_180004D2D
0x180004c8d  mov     ecx, 0C0000163h
0x180004c92  jmp     loc_180004D2D
0x180004c97  mov     ecx, 0C0000161h
0x180004c9c  jmp     loc_180004D2D
0x180004ca1  mov     ecx, 0C0000025h
0x180004ca6  jmp     loc_180004D2D
0x180004cab  mov     ecx, 0C0000095h
0x180004cb0  jmp     short loc_180004D2D
0x180004cb2  mov     ecx, 0C0000059h
0x180004cb7  jmp     short loc_180004D2D
0x180004cb9  cmp     ecx, 8007050Ch
0x180004cbf  jz      short loc_180004D28
0x180004cc1  cmp     ecx, 8007054Fh
0x180004cc7  jz      short loc_180004D21
0x180004cc9  cmp     ecx, 800705B9h
0x180004ccf  jz      short loc_180004D1A
0x180004cd1  test    ecx, ecx
0x180004cd3  jz      short loc_180004D16
0x180004cd5  bt      ecx, 1Ch
0x180004cd9  jnb     short loc_180004CE1
0x180004cdb  btr     ecx, 1Ch
0x180004cdf  jmp     short loc_180004D2D
0x180004ce1  mov     eax, ecx
0x180004ce3  and     eax, 1FFF0000h
0x180004ce8  cmp     eax, 70000h
0x180004ced  jnz     short loc_180004D00
0x180004cef  movzx   ecx, cx
0x180004cf2  mov     eax, ecx
0x180004cf4  or      eax, 0C0070000h
0x180004cf9  test    ecx, ecx
0x180004cfb  cmovnz  ecx, eax
0x180004cfe  jmp     short loc_180004D2D
0x180004d00  cmp     eax, 90000h
0x180004d05  jnz     short loc_180004D21
0x180004d07  test    ecx, ecx
0x180004d09  jle     short loc_180004D2D
0x180004d0b  movzx   ecx, cx
0x180004d0e  or      ecx, 0C0090000h
0x180004d14  jmp     short loc_180004D2D
0x180004d16  xor     ecx, ecx
0x180004d18  jmp     short loc_180004D2D
0x180004d1a  mov     ecx, 0C000A083h
0x180004d1f  jmp     short loc_180004D2D
0x180004d21  mov     ecx, 0C00000E5h
0x180004d26  jmp     short loc_180004D2D
0x180004d28  mov     ecx, 0C000042Bh
0x180004d2d  mov     eax, ecx
0x180004d2f  retn
```
