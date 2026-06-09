# wil::details::HrToNtStatus(long)

- ea: `0x180013bac`
- end: `0x180013d68`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180011350`
- `0x1800113f0`
- `0x180011440`
- `0x180011500`
- `0x180013188`
- `0x180013e58`

## callees

- `0x180013bac`

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
0x180013bac  mov     eax, 800700EAh
0x180013bb1  cmp     ecx, eax
0x180013bb3  jg      loc_180013C88
0x180013bb9  jz      loc_180013C7E
0x180013bbf  mov     eax, 80070057h
0x180013bc4  cmp     ecx, eax
0x180013bc6  jg      short loc_180013C32
0x180013bc8  jz      short loc_180013C28
0x180013bca  cmp     ecx, 80004005h
0x180013bd0  jz      short loc_180013C1E
0x180013bd2  cmp     ecx, 80070001h
0x180013bd8  jz      short loc_180013C14
0x180013bda  cmp     ecx, 80070002h
0x180013be0  jz      short loc_180013C0A
0x180013be2  cmp     ecx, 80070003h
0x180013be8  jz      short loc_180013C00
0x180013bea  cmp     ecx, 8007000Eh
0x180013bf0  jnz     loc_180013D0D
0x180013bf6  mov     ecx, 0C0000017h
0x180013bfb  jmp     loc_180013D65
0x180013c00  mov     ecx, 0C000003Ah
0x180013c05  jmp     loc_180013D65
0x180013c0a  mov     ecx, 0C0000034h
0x180013c0f  jmp     loc_180013D65
0x180013c14  mov     ecx, 0C0000002h
0x180013c19  jmp     loc_180013D65
0x180013c1e  mov     ecx, 0C0000001h
0x180013c23  jmp     loc_180013D65
0x180013c28  mov     ecx, 0C000000Dh
0x180013c2d  jmp     loc_180013D65
0x180013c32  cmp     ecx, 80070070h
0x180013c38  jz      short loc_180013C74
0x180013c3a  cmp     ecx, 8007007Ah
0x180013c40  jz      short loc_180013C6A
0x180013c42  cmp     ecx, 8007007Bh
0x180013c48  jz      short loc_180013C60
0x180013c4a  cmp     ecx, 8007007Eh
0x180013c50  jnz     loc_180013D0D
0x180013c56  mov     ecx, 0C0000135h
0x180013c5b  jmp     loc_180013D65
0x180013c60  mov     ecx, 0C0000033h
0x180013c65  jmp     loc_180013D65
0x180013c6a  mov     ecx, 0C0000023h
0x180013c6f  jmp     loc_180013D65
0x180013c74  mov     ecx, 0C000007Fh
0x180013c79  jmp     loc_180013D65
0x180013c7e  mov     ecx, 80000005h
0x180013c83  jmp     loc_180013D65
0x180013c88  mov     eax, 8007047Eh
0x180013c8d  cmp     ecx, eax
0x180013c8f  jg      short loc_180013CF1
0x180013c91  jz      short loc_180013CEA
0x180013c93  cmp     ecx, 80070216h
0x180013c99  jz      short loc_180013CE3
0x180013c9b  cmp     ecx, 8007023Eh
0x180013ca1  jz      short loc_180013CD9
0x180013ca3  cmp     ecx, 80070246h
0x180013ca9  jz      short loc_180013CCF
0x180013cab  cmp     ecx, 80070247h
0x180013cb1  jz      short loc_180013CC5
0x180013cb3  cmp     ecx, 80070272h
0x180013cb9  jnz     short loc_180013D0D
0x180013cbb  mov     ecx, 0C0000273h
0x180013cc0  jmp     loc_180013D65
0x180013cc5  mov     ecx, 0C0000163h
0x180013cca  jmp     loc_180013D65
0x180013ccf  mov     ecx, 0C0000161h
0x180013cd4  jmp     loc_180013D65
0x180013cd9  mov     ecx, 0C0000025h
0x180013cde  jmp     loc_180013D65
0x180013ce3  mov     ecx, 0C0000095h
0x180013ce8  jmp     short loc_180013D65
0x180013cea  mov     ecx, 0C0000059h
0x180013cef  jmp     short loc_180013D65
0x180013cf1  cmp     ecx, 8007050Ch
0x180013cf7  jz      short loc_180013D60
0x180013cf9  cmp     ecx, 8007054Fh
0x180013cff  jz      short loc_180013D59
0x180013d01  cmp     ecx, 800705B9h
0x180013d07  jz      short loc_180013D52
0x180013d09  test    ecx, ecx
0x180013d0b  jz      short loc_180013D4E
0x180013d0d  bt      ecx, 1Ch
0x180013d11  jnb     short loc_180013D19
0x180013d13  btr     ecx, 1Ch
0x180013d17  jmp     short loc_180013D65
0x180013d19  mov     eax, ecx
0x180013d1b  and     eax, 1FFF0000h
0x180013d20  cmp     eax, 70000h
0x180013d25  jnz     short loc_180013D38
0x180013d27  movzx   ecx, cx
0x180013d2a  mov     eax, ecx
0x180013d2c  or      eax, 0C0070000h
0x180013d31  test    ecx, ecx
0x180013d33  cmovnz  ecx, eax
0x180013d36  jmp     short loc_180013D65
0x180013d38  cmp     eax, 90000h
0x180013d3d  jnz     short loc_180013D59
0x180013d3f  test    ecx, ecx
0x180013d41  jle     short loc_180013D65
0x180013d43  movzx   ecx, cx
0x180013d46  or      ecx, 0C0090000h
0x180013d4c  jmp     short loc_180013D65
0x180013d4e  xor     ecx, ecx
0x180013d50  jmp     short loc_180013D65
0x180013d52  mov     ecx, 0C000A083h
0x180013d57  jmp     short loc_180013D65
0x180013d59  mov     ecx, 0C00000E5h
0x180013d5e  jmp     short loc_180013D65
0x180013d60  mov     ecx, 0C000042Bh
0x180013d65  mov     eax, ecx
0x180013d67  retn
```
