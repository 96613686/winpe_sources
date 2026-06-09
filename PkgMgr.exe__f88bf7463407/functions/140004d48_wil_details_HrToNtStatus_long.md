# wil::details::HrToNtStatus(long)

- ea: `0x140004d48`
- end: `0x140004f04`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x14000338c`
- `0x140003404`
- `0x140003480`
- `0x1400034d0`
- `0x1400043b8`
- `0x140004f0c`
- `0x140008d84`

## callees

- `0x140004d48`

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
0x140004d48  mov     eax, 800700EAh
0x140004d4d  cmp     ecx, eax
0x140004d4f  jg      loc_140004E24
0x140004d55  jz      loc_140004E1A
0x140004d5b  mov     eax, 80070057h
0x140004d60  cmp     ecx, eax
0x140004d62  jg      short loc_140004DCE
0x140004d64  jz      short loc_140004DC4
0x140004d66  cmp     ecx, 80004005h
0x140004d6c  jz      short loc_140004DBA
0x140004d6e  cmp     ecx, 80070001h
0x140004d74  jz      short loc_140004DB0
0x140004d76  cmp     ecx, 80070002h
0x140004d7c  jz      short loc_140004DA6
0x140004d7e  cmp     ecx, 80070003h
0x140004d84  jz      short loc_140004D9C
0x140004d86  cmp     ecx, 8007000Eh
0x140004d8c  jnz     loc_140004EA9
0x140004d92  mov     ecx, 0C0000017h
0x140004d97  jmp     loc_140004F01
0x140004d9c  mov     ecx, 0C000003Ah
0x140004da1  jmp     loc_140004F01
0x140004da6  mov     ecx, 0C0000034h
0x140004dab  jmp     loc_140004F01
0x140004db0  mov     ecx, 0C0000002h
0x140004db5  jmp     loc_140004F01
0x140004dba  mov     ecx, 0C0000001h
0x140004dbf  jmp     loc_140004F01
0x140004dc4  mov     ecx, 0C000000Dh
0x140004dc9  jmp     loc_140004F01
0x140004dce  cmp     ecx, 80070070h
0x140004dd4  jz      short loc_140004E10
0x140004dd6  cmp     ecx, 8007007Ah
0x140004ddc  jz      short loc_140004E06
0x140004dde  cmp     ecx, 8007007Bh
0x140004de4  jz      short loc_140004DFC
0x140004de6  cmp     ecx, 8007007Eh
0x140004dec  jnz     loc_140004EA9
0x140004df2  mov     ecx, 0C0000135h
0x140004df7  jmp     loc_140004F01
0x140004dfc  mov     ecx, 0C0000033h
0x140004e01  jmp     loc_140004F01
0x140004e06  mov     ecx, 0C0000023h
0x140004e0b  jmp     loc_140004F01
0x140004e10  mov     ecx, 0C000007Fh
0x140004e15  jmp     loc_140004F01
0x140004e1a  mov     ecx, 80000005h
0x140004e1f  jmp     loc_140004F01
0x140004e24  mov     eax, 8007047Eh
0x140004e29  cmp     ecx, eax
0x140004e2b  jg      short loc_140004E8D
0x140004e2d  jz      short loc_140004E86
0x140004e2f  cmp     ecx, 80070216h
0x140004e35  jz      short loc_140004E7F
0x140004e37  cmp     ecx, 8007023Eh
0x140004e3d  jz      short loc_140004E75
0x140004e3f  cmp     ecx, 80070246h
0x140004e45  jz      short loc_140004E6B
0x140004e47  cmp     ecx, 80070247h
0x140004e4d  jz      short loc_140004E61
0x140004e4f  cmp     ecx, 80070272h
0x140004e55  jnz     short loc_140004EA9
0x140004e57  mov     ecx, 0C0000273h
0x140004e5c  jmp     loc_140004F01
0x140004e61  mov     ecx, 0C0000163h
0x140004e66  jmp     loc_140004F01
0x140004e6b  mov     ecx, 0C0000161h
0x140004e70  jmp     loc_140004F01
0x140004e75  mov     ecx, 0C0000025h
0x140004e7a  jmp     loc_140004F01
0x140004e7f  mov     ecx, 0C0000095h
0x140004e84  jmp     short loc_140004F01
0x140004e86  mov     ecx, 0C0000059h
0x140004e8b  jmp     short loc_140004F01
0x140004e8d  cmp     ecx, 8007050Ch
0x140004e93  jz      short loc_140004EFC
0x140004e95  cmp     ecx, 8007054Fh
0x140004e9b  jz      short loc_140004EF5
0x140004e9d  cmp     ecx, 800705B9h
0x140004ea3  jz      short loc_140004EEE
0x140004ea5  test    ecx, ecx
0x140004ea7  jz      short loc_140004EEA
0x140004ea9  bt      ecx, 1Ch
0x140004ead  jnb     short loc_140004EB5
0x140004eaf  btr     ecx, 1Ch
0x140004eb3  jmp     short loc_140004F01
0x140004eb5  mov     eax, ecx
0x140004eb7  and     eax, 1FFF0000h
0x140004ebc  cmp     eax, 70000h
0x140004ec1  jnz     short loc_140004ED4
0x140004ec3  movzx   ecx, cx
0x140004ec6  mov     eax, ecx
0x140004ec8  or      eax, 0C0070000h
0x140004ecd  test    ecx, ecx
0x140004ecf  cmovnz  ecx, eax
0x140004ed2  jmp     short loc_140004F01
0x140004ed4  cmp     eax, 90000h
0x140004ed9  jnz     short loc_140004EF5
0x140004edb  test    ecx, ecx
0x140004edd  jle     short loc_140004F01
0x140004edf  movzx   ecx, cx
0x140004ee2  or      ecx, 0C0090000h
0x140004ee8  jmp     short loc_140004F01
0x140004eea  xor     ecx, ecx
0x140004eec  jmp     short loc_140004F01
0x140004eee  mov     ecx, 0C000A083h
0x140004ef3  jmp     short loc_140004F01
0x140004ef5  mov     ecx, 0C00000E5h
0x140004efa  jmp     short loc_140004F01
0x140004efc  mov     ecx, 0C000042Bh
0x140004f01  mov     eax, ecx
0x140004f03  retn
```
