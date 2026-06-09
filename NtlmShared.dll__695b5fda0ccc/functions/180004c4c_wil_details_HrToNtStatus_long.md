# wil::details::HrToNtStatus(long)

- ea: `0x180004c4c`
- end: `0x180004e08`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1800021e4`
- `0x180002284`
- `0x1800022d4`
- `0x180002394`
- `0x180004228`
- `0x180004ef8`

## callees

- `0x180004c4c`

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
0x180004c4c  mov     eax, 800700EAh
0x180004c51  cmp     ecx, eax
0x180004c53  jg      loc_180004D28
0x180004c59  jz      loc_180004D1E
0x180004c5f  mov     eax, 80070057h
0x180004c64  cmp     ecx, eax
0x180004c66  jg      short loc_180004CD2
0x180004c68  jz      short loc_180004CC8
0x180004c6a  cmp     ecx, 80004005h
0x180004c70  jz      short loc_180004CBE
0x180004c72  cmp     ecx, 80070001h
0x180004c78  jz      short loc_180004CB4
0x180004c7a  cmp     ecx, 80070002h
0x180004c80  jz      short loc_180004CAA
0x180004c82  cmp     ecx, 80070003h
0x180004c88  jz      short loc_180004CA0
0x180004c8a  cmp     ecx, 8007000Eh
0x180004c90  jnz     loc_180004DAD
0x180004c96  mov     ecx, 0C0000017h
0x180004c9b  jmp     loc_180004E05
0x180004ca0  mov     ecx, 0C000003Ah
0x180004ca5  jmp     loc_180004E05
0x180004caa  mov     ecx, 0C0000034h
0x180004caf  jmp     loc_180004E05
0x180004cb4  mov     ecx, 0C0000002h
0x180004cb9  jmp     loc_180004E05
0x180004cbe  mov     ecx, 0C0000001h
0x180004cc3  jmp     loc_180004E05
0x180004cc8  mov     ecx, 0C000000Dh
0x180004ccd  jmp     loc_180004E05
0x180004cd2  cmp     ecx, 80070070h
0x180004cd8  jz      short loc_180004D14
0x180004cda  cmp     ecx, 8007007Ah
0x180004ce0  jz      short loc_180004D0A
0x180004ce2  cmp     ecx, 8007007Bh
0x180004ce8  jz      short loc_180004D00
0x180004cea  cmp     ecx, 8007007Eh
0x180004cf0  jnz     loc_180004DAD
0x180004cf6  mov     ecx, 0C0000135h
0x180004cfb  jmp     loc_180004E05
0x180004d00  mov     ecx, 0C0000033h
0x180004d05  jmp     loc_180004E05
0x180004d0a  mov     ecx, 0C0000023h
0x180004d0f  jmp     loc_180004E05
0x180004d14  mov     ecx, 0C000007Fh
0x180004d19  jmp     loc_180004E05
0x180004d1e  mov     ecx, 80000005h
0x180004d23  jmp     loc_180004E05
0x180004d28  mov     eax, 8007047Eh
0x180004d2d  cmp     ecx, eax
0x180004d2f  jg      short loc_180004D91
0x180004d31  jz      short loc_180004D8A
0x180004d33  cmp     ecx, 80070216h
0x180004d39  jz      short loc_180004D83
0x180004d3b  cmp     ecx, 8007023Eh
0x180004d41  jz      short loc_180004D79
0x180004d43  cmp     ecx, 80070246h
0x180004d49  jz      short loc_180004D6F
0x180004d4b  cmp     ecx, 80070247h
0x180004d51  jz      short loc_180004D65
0x180004d53  cmp     ecx, 80070272h
0x180004d59  jnz     short loc_180004DAD
0x180004d5b  mov     ecx, 0C0000273h
0x180004d60  jmp     loc_180004E05
0x180004d65  mov     ecx, 0C0000163h
0x180004d6a  jmp     loc_180004E05
0x180004d6f  mov     ecx, 0C0000161h
0x180004d74  jmp     loc_180004E05
0x180004d79  mov     ecx, 0C0000025h
0x180004d7e  jmp     loc_180004E05
0x180004d83  mov     ecx, 0C0000095h
0x180004d88  jmp     short loc_180004E05
0x180004d8a  mov     ecx, 0C0000059h
0x180004d8f  jmp     short loc_180004E05
0x180004d91  cmp     ecx, 8007050Ch
0x180004d97  jz      short loc_180004E00
0x180004d99  cmp     ecx, 8007054Fh
0x180004d9f  jz      short loc_180004DF9
0x180004da1  cmp     ecx, 800705B9h
0x180004da7  jz      short loc_180004DF2
0x180004da9  test    ecx, ecx
0x180004dab  jz      short loc_180004DEE
0x180004dad  bt      ecx, 1Ch
0x180004db1  jnb     short loc_180004DB9
0x180004db3  btr     ecx, 1Ch
0x180004db7  jmp     short loc_180004E05
0x180004db9  mov     eax, ecx
0x180004dbb  and     eax, 1FFF0000h
0x180004dc0  cmp     eax, 70000h
0x180004dc5  jnz     short loc_180004DD8
0x180004dc7  movzx   ecx, cx
0x180004dca  mov     eax, ecx
0x180004dcc  or      eax, 0C0070000h
0x180004dd1  test    ecx, ecx
0x180004dd3  cmovnz  ecx, eax
0x180004dd6  jmp     short loc_180004E05
0x180004dd8  cmp     eax, 90000h
0x180004ddd  jnz     short loc_180004DF9
0x180004ddf  test    ecx, ecx
0x180004de1  jle     short loc_180004E05
0x180004de3  movzx   ecx, cx
0x180004de6  or      ecx, 0C0090000h
0x180004dec  jmp     short loc_180004E05
0x180004dee  xor     ecx, ecx
0x180004df0  jmp     short loc_180004E05
0x180004df2  mov     ecx, 0C000A083h
0x180004df7  jmp     short loc_180004E05
0x180004df9  mov     ecx, 0C00000E5h
0x180004dfe  jmp     short loc_180004E05
0x180004e00  mov     ecx, 0C000042Bh
0x180004e05  mov     eax, ecx
0x180004e07  retn
```
