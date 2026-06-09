# wil::details::HrToNtStatus(long)

- ea: `0x18000514c`
- end: `0x180005308`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800049dc`
- `0x180004ce8`

## callees

- `0x18000514c`

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
0x18000514c  mov     eax, 800700EAh
0x180005151  cmp     ecx, eax
0x180005153  jg      loc_180005228
0x180005159  jz      loc_18000521E
0x18000515f  mov     eax, 80070057h
0x180005164  cmp     ecx, eax
0x180005166  jg      short loc_1800051D2
0x180005168  jz      short loc_1800051C8
0x18000516a  cmp     ecx, 80004005h
0x180005170  jz      short loc_1800051BE
0x180005172  cmp     ecx, 80070001h
0x180005178  jz      short loc_1800051B4
0x18000517a  cmp     ecx, 80070002h
0x180005180  jz      short loc_1800051AA
0x180005182  cmp     ecx, 80070003h
0x180005188  jz      short loc_1800051A0
0x18000518a  cmp     ecx, 8007000Eh
0x180005190  jnz     loc_1800052AD
0x180005196  mov     ecx, 0C0000017h
0x18000519b  jmp     loc_180005305
0x1800051a0  mov     ecx, 0C000003Ah
0x1800051a5  jmp     loc_180005305
0x1800051aa  mov     ecx, 0C0000034h
0x1800051af  jmp     loc_180005305
0x1800051b4  mov     ecx, 0C0000002h
0x1800051b9  jmp     loc_180005305
0x1800051be  mov     ecx, 0C0000001h
0x1800051c3  jmp     loc_180005305
0x1800051c8  mov     ecx, 0C000000Dh
0x1800051cd  jmp     loc_180005305
0x1800051d2  cmp     ecx, 80070070h
0x1800051d8  jz      short loc_180005214
0x1800051da  cmp     ecx, 8007007Ah
0x1800051e0  jz      short loc_18000520A
0x1800051e2  cmp     ecx, 8007007Bh
0x1800051e8  jz      short loc_180005200
0x1800051ea  cmp     ecx, 8007007Eh
0x1800051f0  jnz     loc_1800052AD
0x1800051f6  mov     ecx, 0C0000135h
0x1800051fb  jmp     loc_180005305
0x180005200  mov     ecx, 0C0000033h
0x180005205  jmp     loc_180005305
0x18000520a  mov     ecx, 0C0000023h
0x18000520f  jmp     loc_180005305
0x180005214  mov     ecx, 0C000007Fh
0x180005219  jmp     loc_180005305
0x18000521e  mov     ecx, 80000005h
0x180005223  jmp     loc_180005305
0x180005228  mov     eax, 8007047Eh
0x18000522d  cmp     ecx, eax
0x18000522f  jg      short loc_180005291
0x180005231  jz      short loc_18000528A
0x180005233  cmp     ecx, 80070216h
0x180005239  jz      short loc_180005283
0x18000523b  cmp     ecx, 8007023Eh
0x180005241  jz      short loc_180005279
0x180005243  cmp     ecx, 80070246h
0x180005249  jz      short loc_18000526F
0x18000524b  cmp     ecx, 80070247h
0x180005251  jz      short loc_180005265
0x180005253  cmp     ecx, 80070272h
0x180005259  jnz     short loc_1800052AD
0x18000525b  mov     ecx, 0C0000273h
0x180005260  jmp     loc_180005305
0x180005265  mov     ecx, 0C0000163h
0x18000526a  jmp     loc_180005305
0x18000526f  mov     ecx, 0C0000161h
0x180005274  jmp     loc_180005305
0x180005279  mov     ecx, 0C0000025h
0x18000527e  jmp     loc_180005305
0x180005283  mov     ecx, 0C0000095h
0x180005288  jmp     short loc_180005305
0x18000528a  mov     ecx, 0C0000059h
0x18000528f  jmp     short loc_180005305
0x180005291  cmp     ecx, 8007050Ch
0x180005297  jz      short loc_180005300
0x180005299  cmp     ecx, 8007054Fh
0x18000529f  jz      short loc_1800052F9
0x1800052a1  cmp     ecx, 800705B9h
0x1800052a7  jz      short loc_1800052F2
0x1800052a9  test    ecx, ecx
0x1800052ab  jz      short loc_1800052EE
0x1800052ad  bt      ecx, 1Ch
0x1800052b1  jnb     short loc_1800052B9
0x1800052b3  btr     ecx, 1Ch
0x1800052b7  jmp     short loc_180005305
0x1800052b9  mov     eax, ecx
0x1800052bb  and     eax, 1FFF0000h
0x1800052c0  cmp     eax, 70000h
0x1800052c5  jnz     short loc_1800052D8
0x1800052c7  movzx   ecx, cx
0x1800052ca  mov     eax, ecx
0x1800052cc  or      eax, 0C0070000h
0x1800052d1  test    ecx, ecx
0x1800052d3  cmovnz  ecx, eax
0x1800052d6  jmp     short loc_180005305
0x1800052d8  cmp     eax, 90000h
0x1800052dd  jnz     short loc_1800052F9
0x1800052df  test    ecx, ecx
0x1800052e1  jle     short loc_180005305
0x1800052e3  movzx   ecx, cx
0x1800052e6  or      ecx, 0C0090000h
0x1800052ec  jmp     short loc_180005305
0x1800052ee  xor     ecx, ecx
0x1800052f0  jmp     short loc_180005305
0x1800052f2  mov     ecx, 0C000A083h
0x1800052f7  jmp     short loc_180005305
0x1800052f9  mov     ecx, 0C00000E5h
0x1800052fe  jmp     short loc_180005305
0x180005300  mov     ecx, 0C000042Bh
0x180005305  mov     eax, ecx
0x180005307  retn
```
