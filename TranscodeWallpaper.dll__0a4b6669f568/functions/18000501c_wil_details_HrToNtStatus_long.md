# wil::details::HrToNtStatus(long)

- ea: `0x18000501c`
- end: `0x1800051d8`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x180002efc`
- `0x1800030c8`
- `0x180003178`
- `0x1800031d0`
- `0x180003298`
- `0x1800045e8`
- `0x1800051e0`
- `0x1800058e0`
- `0x18000dfd0`
- `0x18000e03b`
- `0x18000e104`
- `0x18000e16f`

## callees

- `0x18000501c`

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
0x18000501c  mov     eax, 800700EAh
0x180005021  cmp     ecx, eax
0x180005023  jg      loc_1800050F8
0x180005029  jz      loc_1800050EE
0x18000502f  mov     eax, 80070057h
0x180005034  cmp     ecx, eax
0x180005036  jg      short loc_1800050A2
0x180005038  jz      short loc_180005098
0x18000503a  cmp     ecx, 80004005h
0x180005040  jz      short loc_18000508E
0x180005042  cmp     ecx, 80070001h
0x180005048  jz      short loc_180005084
0x18000504a  cmp     ecx, 80070002h
0x180005050  jz      short loc_18000507A
0x180005052  cmp     ecx, 80070003h
0x180005058  jz      short loc_180005070
0x18000505a  cmp     ecx, 8007000Eh
0x180005060  jnz     loc_18000517D
0x180005066  mov     ecx, 0C0000017h
0x18000506b  jmp     loc_1800051D5
0x180005070  mov     ecx, 0C000003Ah
0x180005075  jmp     loc_1800051D5
0x18000507a  mov     ecx, 0C0000034h
0x18000507f  jmp     loc_1800051D5
0x180005084  mov     ecx, 0C0000002h
0x180005089  jmp     loc_1800051D5
0x18000508e  mov     ecx, 0C0000001h
0x180005093  jmp     loc_1800051D5
0x180005098  mov     ecx, 0C000000Dh
0x18000509d  jmp     loc_1800051D5
0x1800050a2  cmp     ecx, 80070070h
0x1800050a8  jz      short loc_1800050E4
0x1800050aa  cmp     ecx, 8007007Ah
0x1800050b0  jz      short loc_1800050DA
0x1800050b2  cmp     ecx, 8007007Bh
0x1800050b8  jz      short loc_1800050D0
0x1800050ba  cmp     ecx, 8007007Eh
0x1800050c0  jnz     loc_18000517D
0x1800050c6  mov     ecx, 0C0000135h
0x1800050cb  jmp     loc_1800051D5
0x1800050d0  mov     ecx, 0C0000033h
0x1800050d5  jmp     loc_1800051D5
0x1800050da  mov     ecx, 0C0000023h
0x1800050df  jmp     loc_1800051D5
0x1800050e4  mov     ecx, 0C000007Fh
0x1800050e9  jmp     loc_1800051D5
0x1800050ee  mov     ecx, 80000005h
0x1800050f3  jmp     loc_1800051D5
0x1800050f8  mov     eax, 8007047Eh
0x1800050fd  cmp     ecx, eax
0x1800050ff  jg      short loc_180005161
0x180005101  jz      short loc_18000515A
0x180005103  cmp     ecx, 80070216h
0x180005109  jz      short loc_180005153
0x18000510b  cmp     ecx, 8007023Eh
0x180005111  jz      short loc_180005149
0x180005113  cmp     ecx, 80070246h
0x180005119  jz      short loc_18000513F
0x18000511b  cmp     ecx, 80070247h
0x180005121  jz      short loc_180005135
0x180005123  cmp     ecx, 80070272h
0x180005129  jnz     short loc_18000517D
0x18000512b  mov     ecx, 0C0000273h
0x180005130  jmp     loc_1800051D5
0x180005135  mov     ecx, 0C0000163h
0x18000513a  jmp     loc_1800051D5
0x18000513f  mov     ecx, 0C0000161h
0x180005144  jmp     loc_1800051D5
0x180005149  mov     ecx, 0C0000025h
0x18000514e  jmp     loc_1800051D5
0x180005153  mov     ecx, 0C0000095h
0x180005158  jmp     short loc_1800051D5
0x18000515a  mov     ecx, 0C0000059h
0x18000515f  jmp     short loc_1800051D5
0x180005161  cmp     ecx, 8007050Ch
0x180005167  jz      short loc_1800051D0
0x180005169  cmp     ecx, 8007054Fh
0x18000516f  jz      short loc_1800051C9
0x180005171  cmp     ecx, 800705B9h
0x180005177  jz      short loc_1800051C2
0x180005179  test    ecx, ecx
0x18000517b  jz      short loc_1800051BE
0x18000517d  bt      ecx, 1Ch
0x180005181  jnb     short loc_180005189
0x180005183  btr     ecx, 1Ch
0x180005187  jmp     short loc_1800051D5
0x180005189  mov     eax, ecx
0x18000518b  and     eax, 1FFF0000h
0x180005190  cmp     eax, 70000h
0x180005195  jnz     short loc_1800051A8
0x180005197  movzx   ecx, cx
0x18000519a  mov     eax, ecx
0x18000519c  or      eax, 0C0070000h
0x1800051a1  test    ecx, ecx
0x1800051a3  cmovnz  ecx, eax
0x1800051a6  jmp     short loc_1800051D5
0x1800051a8  cmp     eax, 90000h
0x1800051ad  jnz     short loc_1800051C9
0x1800051af  test    ecx, ecx
0x1800051b1  jle     short loc_1800051D5
0x1800051b3  movzx   ecx, cx
0x1800051b6  or      ecx, 0C0090000h
0x1800051bc  jmp     short loc_1800051D5
0x1800051be  xor     ecx, ecx
0x1800051c0  jmp     short loc_1800051D5
0x1800051c2  mov     ecx, 0C000A083h
0x1800051c7  jmp     short loc_1800051D5
0x1800051c9  mov     ecx, 0C00000E5h
0x1800051ce  jmp     short loc_1800051D5
0x1800051d0  mov     ecx, 0C000042Bh
0x1800051d5  mov     eax, ecx
0x1800051d7  retn
```
