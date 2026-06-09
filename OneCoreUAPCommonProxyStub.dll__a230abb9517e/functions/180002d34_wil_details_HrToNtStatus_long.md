# wil::details::HrToNtStatus(long)

- ea: `0x180002d34`
- end: `0x180002ef0`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `13`
- callee_count: `1`
- tags: ``

## callers

- `0x18000380c`
- `0x180006074`
- `0x180006168`
- `0x1800061e8`
- `0x180006260`
- `0x1800062e8`
- `0x180006348`
- `0x180008470`
- `0x180008ff0`
- `0x18000b4ff`
- `0x18000b54a`
- `0x18000b60d`
- `0x18000b658`

## callees

- `0x180002d34`

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
        case 0x8007054F:
          goto LABEL_53;
        case 0x8007050C:
          LODWORD(this) = -1073740757;
          return (unsigned int)this;
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
0x180002d34  mov     eax, 800700EAh
0x180002d39  cmp     ecx, eax
0x180002d3b  jg      loc_180002E10
0x180002d41  jz      loc_180002E06
0x180002d47  mov     eax, 80070057h
0x180002d4c  cmp     ecx, eax
0x180002d4e  jg      short loc_180002DBA
0x180002d50  jz      short loc_180002DB0
0x180002d52  cmp     ecx, 80004005h
0x180002d58  jz      short loc_180002DA6
0x180002d5a  cmp     ecx, 80070001h
0x180002d60  jz      short loc_180002D9C
0x180002d62  cmp     ecx, 80070002h
0x180002d68  jz      short loc_180002D92
0x180002d6a  cmp     ecx, 80070003h
0x180002d70  jz      short loc_180002D88
0x180002d72  cmp     ecx, 8007000Eh
0x180002d78  jnz     loc_180002E95
0x180002d7e  mov     ecx, 0C0000017h
0x180002d83  jmp     loc_180002EED
0x180002d88  mov     ecx, 0C000003Ah
0x180002d8d  jmp     loc_180002EED
0x180002d92  mov     ecx, 0C0000034h
0x180002d97  jmp     loc_180002EED
0x180002d9c  mov     ecx, 0C0000002h
0x180002da1  jmp     loc_180002EED
0x180002da6  mov     ecx, 0C0000001h
0x180002dab  jmp     loc_180002EED
0x180002db0  mov     ecx, 0C000000Dh
0x180002db5  jmp     loc_180002EED
0x180002dba  cmp     ecx, 80070070h
0x180002dc0  jz      short loc_180002DFC
0x180002dc2  cmp     ecx, 8007007Ah
0x180002dc8  jz      short loc_180002DF2
0x180002dca  cmp     ecx, 8007007Bh
0x180002dd0  jz      short loc_180002DE8
0x180002dd2  cmp     ecx, 8007007Eh
0x180002dd8  jnz     loc_180002E95
0x180002dde  mov     ecx, 0C0000135h
0x180002de3  jmp     loc_180002EED
0x180002de8  mov     ecx, 0C0000033h
0x180002ded  jmp     loc_180002EED
0x180002df2  mov     ecx, 0C0000023h
0x180002df7  jmp     loc_180002EED
0x180002dfc  mov     ecx, 0C000007Fh
0x180002e01  jmp     loc_180002EED
0x180002e06  mov     ecx, 80000005h
0x180002e0b  jmp     loc_180002EED
0x180002e10  mov     eax, 8007047Eh
0x180002e15  cmp     ecx, eax
0x180002e17  jg      short loc_180002E79
0x180002e19  jz      short loc_180002E72
0x180002e1b  cmp     ecx, 80070216h
0x180002e21  jz      short loc_180002E6B
0x180002e23  cmp     ecx, 8007023Eh
0x180002e29  jz      short loc_180002E61
0x180002e2b  cmp     ecx, 80070246h
0x180002e31  jz      short loc_180002E57
0x180002e33  cmp     ecx, 80070247h
0x180002e39  jz      short loc_180002E4D
0x180002e3b  cmp     ecx, 80070272h
0x180002e41  jnz     short loc_180002E95
0x180002e43  mov     ecx, 0C0000273h
0x180002e48  jmp     loc_180002EED
0x180002e4d  mov     ecx, 0C0000163h
0x180002e52  jmp     loc_180002EED
0x180002e57  mov     ecx, 0C0000161h
0x180002e5c  jmp     loc_180002EED
0x180002e61  mov     ecx, 0C0000025h
0x180002e66  jmp     loc_180002EED
0x180002e6b  mov     ecx, 0C0000095h
0x180002e70  jmp     short loc_180002EED
0x180002e72  mov     ecx, 0C0000059h
0x180002e77  jmp     short loc_180002EED
0x180002e79  cmp     ecx, 8007054Fh
0x180002e7f  jz      short loc_180002EE1
0x180002e81  cmp     ecx, 8007050Ch
0x180002e87  jz      short loc_180002EE8
0x180002e89  cmp     ecx, 800705B9h
0x180002e8f  jz      short loc_180002EDA
0x180002e91  test    ecx, ecx
0x180002e93  jz      short loc_180002ED6
0x180002e95  bt      ecx, 1Ch
0x180002e99  jnb     short loc_180002EA1
0x180002e9b  btr     ecx, 1Ch
0x180002e9f  jmp     short loc_180002EED
0x180002ea1  mov     eax, ecx
0x180002ea3  and     eax, 1FFF0000h
0x180002ea8  cmp     eax, 70000h
0x180002ead  jnz     short loc_180002EC0
0x180002eaf  movzx   ecx, cx
0x180002eb2  mov     eax, ecx
0x180002eb4  or      eax, 0C0070000h
0x180002eb9  test    ecx, ecx
0x180002ebb  cmovnz  ecx, eax
0x180002ebe  jmp     short loc_180002EED
0x180002ec0  cmp     eax, 90000h
0x180002ec5  jnz     short loc_180002EE1
0x180002ec7  test    ecx, ecx
0x180002ec9  jle     short loc_180002EED
0x180002ecb  movzx   ecx, cx
0x180002ece  or      ecx, 0C0090000h
0x180002ed4  jmp     short loc_180002EED
0x180002ed6  xor     ecx, ecx
0x180002ed8  jmp     short loc_180002EED
0x180002eda  mov     ecx, 0C000A083h
0x180002edf  jmp     short loc_180002EED
0x180002ee1  mov     ecx, 0C00000E5h
0x180002ee6  jmp     short loc_180002EED
0x180002ee8  mov     ecx, 0C000042Bh
0x180002eed  mov     eax, ecx
0x180002eef  retn
```
