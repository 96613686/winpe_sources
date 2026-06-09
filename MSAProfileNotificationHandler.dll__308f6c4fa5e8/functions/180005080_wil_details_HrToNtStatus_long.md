# wil::details::HrToNtStatus(long)

- ea: `0x180005080`
- end: `0x18000523c`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1800031b4`
- `0x180003254`
- `0x1800032a4`
- `0x18000335c`
- `0x180004658`
- `0x18000525c`

## callees

- `0x180005080`

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
0x180005080  mov     eax, 800700EAh
0x180005085  cmp     ecx, eax
0x180005087  jg      loc_18000515C
0x18000508d  jz      loc_180005152
0x180005093  mov     eax, 80070057h
0x180005098  cmp     ecx, eax
0x18000509a  jg      short loc_180005106
0x18000509c  jz      short loc_1800050FC
0x18000509e  cmp     ecx, 80004005h
0x1800050a4  jz      short loc_1800050F2
0x1800050a6  cmp     ecx, 80070001h
0x1800050ac  jz      short loc_1800050E8
0x1800050ae  cmp     ecx, 80070002h
0x1800050b4  jz      short loc_1800050DE
0x1800050b6  cmp     ecx, 80070003h
0x1800050bc  jz      short loc_1800050D4
0x1800050be  cmp     ecx, 8007000Eh
0x1800050c4  jnz     loc_1800051E1
0x1800050ca  mov     ecx, 0C0000017h
0x1800050cf  jmp     loc_180005239
0x1800050d4  mov     ecx, 0C000003Ah
0x1800050d9  jmp     loc_180005239
0x1800050de  mov     ecx, 0C0000034h
0x1800050e3  jmp     loc_180005239
0x1800050e8  mov     ecx, 0C0000002h
0x1800050ed  jmp     loc_180005239
0x1800050f2  mov     ecx, 0C0000001h
0x1800050f7  jmp     loc_180005239
0x1800050fc  mov     ecx, 0C000000Dh
0x180005101  jmp     loc_180005239
0x180005106  cmp     ecx, 80070070h
0x18000510c  jz      short loc_180005148
0x18000510e  cmp     ecx, 8007007Ah
0x180005114  jz      short loc_18000513E
0x180005116  cmp     ecx, 8007007Bh
0x18000511c  jz      short loc_180005134
0x18000511e  cmp     ecx, 8007007Eh
0x180005124  jnz     loc_1800051E1
0x18000512a  mov     ecx, 0C0000135h
0x18000512f  jmp     loc_180005239
0x180005134  mov     ecx, 0C0000033h
0x180005139  jmp     loc_180005239
0x18000513e  mov     ecx, 0C0000023h
0x180005143  jmp     loc_180005239
0x180005148  mov     ecx, 0C000007Fh
0x18000514d  jmp     loc_180005239
0x180005152  mov     ecx, 80000005h
0x180005157  jmp     loc_180005239
0x18000515c  mov     eax, 8007047Eh
0x180005161  cmp     ecx, eax
0x180005163  jg      short loc_1800051C5
0x180005165  jz      short loc_1800051BE
0x180005167  cmp     ecx, 80070216h
0x18000516d  jz      short loc_1800051B7
0x18000516f  cmp     ecx, 8007023Eh
0x180005175  jz      short loc_1800051AD
0x180005177  cmp     ecx, 80070246h
0x18000517d  jz      short loc_1800051A3
0x18000517f  cmp     ecx, 80070247h
0x180005185  jz      short loc_180005199
0x180005187  cmp     ecx, 80070272h
0x18000518d  jnz     short loc_1800051E1
0x18000518f  mov     ecx, 0C0000273h
0x180005194  jmp     loc_180005239
0x180005199  mov     ecx, 0C0000163h
0x18000519e  jmp     loc_180005239
0x1800051a3  mov     ecx, 0C0000161h
0x1800051a8  jmp     loc_180005239
0x1800051ad  mov     ecx, 0C0000025h
0x1800051b2  jmp     loc_180005239
0x1800051b7  mov     ecx, 0C0000095h
0x1800051bc  jmp     short loc_180005239
0x1800051be  mov     ecx, 0C0000059h
0x1800051c3  jmp     short loc_180005239
0x1800051c5  cmp     ecx, 8007050Ch
0x1800051cb  jz      short loc_180005234
0x1800051cd  cmp     ecx, 8007054Fh
0x1800051d3  jz      short loc_18000522D
0x1800051d5  cmp     ecx, 800705B9h
0x1800051db  jz      short loc_180005226
0x1800051dd  test    ecx, ecx
0x1800051df  jz      short loc_180005222
0x1800051e1  bt      ecx, 1Ch
0x1800051e5  jnb     short loc_1800051ED
0x1800051e7  btr     ecx, 1Ch
0x1800051eb  jmp     short loc_180005239
0x1800051ed  mov     eax, ecx
0x1800051ef  and     eax, 1FFF0000h
0x1800051f4  cmp     eax, 70000h
0x1800051f9  jnz     short loc_18000520C
0x1800051fb  movzx   ecx, cx
0x1800051fe  mov     eax, ecx
0x180005200  or      eax, 0C0070000h
0x180005205  test    ecx, ecx
0x180005207  cmovnz  ecx, eax
0x18000520a  jmp     short loc_180005239
0x18000520c  cmp     eax, 90000h
0x180005211  jnz     short loc_18000522D
0x180005213  test    ecx, ecx
0x180005215  jle     short loc_180005239
0x180005217  movzx   ecx, cx
0x18000521a  or      ecx, 0C0090000h
0x180005220  jmp     short loc_180005239
0x180005222  xor     ecx, ecx
0x180005224  jmp     short loc_180005239
0x180005226  mov     ecx, 0C000A083h
0x18000522b  jmp     short loc_180005239
0x18000522d  mov     ecx, 0C00000E5h
0x180005232  jmp     short loc_180005239
0x180005234  mov     ecx, 0C000042Bh
0x180005239  mov     eax, ecx
0x18000523b  retn
```
