# wil::details::HrToNtStatus(long)

- ea: `0x180004cb0`
- end: `0x180004e6c`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x180002fcc`
- `0x18000306c`
- `0x1800030bc`
- `0x18000317c`
- `0x180004288`
- `0x180004e74`
- `0x1800055f0`
- `0x18000eaf4`
- `0x18000eb5f`
- `0x18000ec28`
- `0x18000ec93`

## callees

- `0x180004cb0`

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
0x180004cb0  mov     eax, 800700EAh
0x180004cb5  cmp     ecx, eax
0x180004cb7  jg      loc_180004D8C
0x180004cbd  jz      loc_180004D82
0x180004cc3  mov     eax, 80070057h
0x180004cc8  cmp     ecx, eax
0x180004cca  jg      short loc_180004D36
0x180004ccc  jz      short loc_180004D2C
0x180004cce  cmp     ecx, 80004005h
0x180004cd4  jz      short loc_180004D22
0x180004cd6  cmp     ecx, 80070001h
0x180004cdc  jz      short loc_180004D18
0x180004cde  cmp     ecx, 80070002h
0x180004ce4  jz      short loc_180004D0E
0x180004ce6  cmp     ecx, 80070003h
0x180004cec  jz      short loc_180004D04
0x180004cee  cmp     ecx, 8007000Eh
0x180004cf4  jnz     loc_180004E11
0x180004cfa  mov     ecx, 0C0000017h
0x180004cff  jmp     loc_180004E69
0x180004d04  mov     ecx, 0C000003Ah
0x180004d09  jmp     loc_180004E69
0x180004d0e  mov     ecx, 0C0000034h
0x180004d13  jmp     loc_180004E69
0x180004d18  mov     ecx, 0C0000002h
0x180004d1d  jmp     loc_180004E69
0x180004d22  mov     ecx, 0C0000001h
0x180004d27  jmp     loc_180004E69
0x180004d2c  mov     ecx, 0C000000Dh
0x180004d31  jmp     loc_180004E69
0x180004d36  cmp     ecx, 80070070h
0x180004d3c  jz      short loc_180004D78
0x180004d3e  cmp     ecx, 8007007Ah
0x180004d44  jz      short loc_180004D6E
0x180004d46  cmp     ecx, 8007007Bh
0x180004d4c  jz      short loc_180004D64
0x180004d4e  cmp     ecx, 8007007Eh
0x180004d54  jnz     loc_180004E11
0x180004d5a  mov     ecx, 0C0000135h
0x180004d5f  jmp     loc_180004E69
0x180004d64  mov     ecx, 0C0000033h
0x180004d69  jmp     loc_180004E69
0x180004d6e  mov     ecx, 0C0000023h
0x180004d73  jmp     loc_180004E69
0x180004d78  mov     ecx, 0C000007Fh
0x180004d7d  jmp     loc_180004E69
0x180004d82  mov     ecx, 80000005h
0x180004d87  jmp     loc_180004E69
0x180004d8c  mov     eax, 8007047Eh
0x180004d91  cmp     ecx, eax
0x180004d93  jg      short loc_180004DF5
0x180004d95  jz      short loc_180004DEE
0x180004d97  cmp     ecx, 80070216h
0x180004d9d  jz      short loc_180004DE7
0x180004d9f  cmp     ecx, 8007023Eh
0x180004da5  jz      short loc_180004DDD
0x180004da7  cmp     ecx, 80070246h
0x180004dad  jz      short loc_180004DD3
0x180004daf  cmp     ecx, 80070247h
0x180004db5  jz      short loc_180004DC9
0x180004db7  cmp     ecx, 80070272h
0x180004dbd  jnz     short loc_180004E11
0x180004dbf  mov     ecx, 0C0000273h
0x180004dc4  jmp     loc_180004E69
0x180004dc9  mov     ecx, 0C0000163h
0x180004dce  jmp     loc_180004E69
0x180004dd3  mov     ecx, 0C0000161h
0x180004dd8  jmp     loc_180004E69
0x180004ddd  mov     ecx, 0C0000025h
0x180004de2  jmp     loc_180004E69
0x180004de7  mov     ecx, 0C0000095h
0x180004dec  jmp     short loc_180004E69
0x180004dee  mov     ecx, 0C0000059h
0x180004df3  jmp     short loc_180004E69
0x180004df5  cmp     ecx, 8007050Ch
0x180004dfb  jz      short loc_180004E64
0x180004dfd  cmp     ecx, 8007054Fh
0x180004e03  jz      short loc_180004E5D
0x180004e05  cmp     ecx, 800705B9h
0x180004e0b  jz      short loc_180004E56
0x180004e0d  test    ecx, ecx
0x180004e0f  jz      short loc_180004E52
0x180004e11  bt      ecx, 1Ch
0x180004e15  jnb     short loc_180004E1D
0x180004e17  btr     ecx, 1Ch
0x180004e1b  jmp     short loc_180004E69
0x180004e1d  mov     eax, ecx
0x180004e1f  and     eax, 1FFF0000h
0x180004e24  cmp     eax, 70000h
0x180004e29  jnz     short loc_180004E3C
0x180004e2b  movzx   ecx, cx
0x180004e2e  mov     eax, ecx
0x180004e30  or      eax, 0C0070000h
0x180004e35  test    ecx, ecx
0x180004e37  cmovnz  ecx, eax
0x180004e3a  jmp     short loc_180004E69
0x180004e3c  cmp     eax, 90000h
0x180004e41  jnz     short loc_180004E5D
0x180004e43  test    ecx, ecx
0x180004e45  jle     short loc_180004E69
0x180004e47  movzx   ecx, cx
0x180004e4a  or      ecx, 0C0090000h
0x180004e50  jmp     short loc_180004E69
0x180004e52  xor     ecx, ecx
0x180004e54  jmp     short loc_180004E69
0x180004e56  mov     ecx, 0C000A083h
0x180004e5b  jmp     short loc_180004E69
0x180004e5d  mov     ecx, 0C00000E5h
0x180004e62  jmp     short loc_180004E69
0x180004e64  mov     ecx, 0C000042Bh
0x180004e69  mov     eax, ecx
0x180004e6b  retn
```
