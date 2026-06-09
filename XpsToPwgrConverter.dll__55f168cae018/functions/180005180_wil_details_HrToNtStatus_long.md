# wil::details::HrToNtStatus(long)

- ea: `0x180005180`
- end: `0x18000533c`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x180002504`
- `0x1800025b4`
- `0x180002614`
- `0x1800026dc`
- `0x180004758`
- `0x180005344`
- `0x180006c30`
- `0x18000a6dc`
- `0x18000f7d5`
- `0x18000f840`
- `0x18000f909`
- `0x18000f974`

## callees

- `0x180005180`

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
0x180005180  mov     eax, 800700EAh
0x180005185  cmp     ecx, eax
0x180005187  jg      loc_18000525C
0x18000518d  jz      loc_180005252
0x180005193  mov     eax, 80070057h
0x180005198  cmp     ecx, eax
0x18000519a  jg      short loc_180005206
0x18000519c  jz      short loc_1800051FC
0x18000519e  cmp     ecx, 80004005h
0x1800051a4  jz      short loc_1800051F2
0x1800051a6  cmp     ecx, 80070001h
0x1800051ac  jz      short loc_1800051E8
0x1800051ae  cmp     ecx, 80070002h
0x1800051b4  jz      short loc_1800051DE
0x1800051b6  cmp     ecx, 80070003h
0x1800051bc  jz      short loc_1800051D4
0x1800051be  cmp     ecx, 8007000Eh
0x1800051c4  jnz     loc_1800052E1
0x1800051ca  mov     ecx, 0C0000017h
0x1800051cf  jmp     loc_180005339
0x1800051d4  mov     ecx, 0C000003Ah
0x1800051d9  jmp     loc_180005339
0x1800051de  mov     ecx, 0C0000034h
0x1800051e3  jmp     loc_180005339
0x1800051e8  mov     ecx, 0C0000002h
0x1800051ed  jmp     loc_180005339
0x1800051f2  mov     ecx, 0C0000001h
0x1800051f7  jmp     loc_180005339
0x1800051fc  mov     ecx, 0C000000Dh
0x180005201  jmp     loc_180005339
0x180005206  cmp     ecx, 80070070h
0x18000520c  jz      short loc_180005248
0x18000520e  cmp     ecx, 8007007Ah
0x180005214  jz      short loc_18000523E
0x180005216  cmp     ecx, 8007007Bh
0x18000521c  jz      short loc_180005234
0x18000521e  cmp     ecx, 8007007Eh
0x180005224  jnz     loc_1800052E1
0x18000522a  mov     ecx, 0C0000135h
0x18000522f  jmp     loc_180005339
0x180005234  mov     ecx, 0C0000033h
0x180005239  jmp     loc_180005339
0x18000523e  mov     ecx, 0C0000023h
0x180005243  jmp     loc_180005339
0x180005248  mov     ecx, 0C000007Fh
0x18000524d  jmp     loc_180005339
0x180005252  mov     ecx, 80000005h
0x180005257  jmp     loc_180005339
0x18000525c  mov     eax, 8007047Eh
0x180005261  cmp     ecx, eax
0x180005263  jg      short loc_1800052C5
0x180005265  jz      short loc_1800052BE
0x180005267  cmp     ecx, 80070216h
0x18000526d  jz      short loc_1800052B7
0x18000526f  cmp     ecx, 8007023Eh
0x180005275  jz      short loc_1800052AD
0x180005277  cmp     ecx, 80070246h
0x18000527d  jz      short loc_1800052A3
0x18000527f  cmp     ecx, 80070247h
0x180005285  jz      short loc_180005299
0x180005287  cmp     ecx, 80070272h
0x18000528d  jnz     short loc_1800052E1
0x18000528f  mov     ecx, 0C0000273h
0x180005294  jmp     loc_180005339
0x180005299  mov     ecx, 0C0000163h
0x18000529e  jmp     loc_180005339
0x1800052a3  mov     ecx, 0C0000161h
0x1800052a8  jmp     loc_180005339
0x1800052ad  mov     ecx, 0C0000025h
0x1800052b2  jmp     loc_180005339
0x1800052b7  mov     ecx, 0C0000095h
0x1800052bc  jmp     short loc_180005339
0x1800052be  mov     ecx, 0C0000059h
0x1800052c3  jmp     short loc_180005339
0x1800052c5  cmp     ecx, 8007050Ch
0x1800052cb  jz      short loc_180005334
0x1800052cd  cmp     ecx, 8007054Fh
0x1800052d3  jz      short loc_18000532D
0x1800052d5  cmp     ecx, 800705B9h
0x1800052db  jz      short loc_180005326
0x1800052dd  test    ecx, ecx
0x1800052df  jz      short loc_180005322
0x1800052e1  bt      ecx, 1Ch
0x1800052e5  jnb     short loc_1800052ED
0x1800052e7  btr     ecx, 1Ch
0x1800052eb  jmp     short loc_180005339
0x1800052ed  mov     eax, ecx
0x1800052ef  and     eax, 1FFF0000h
0x1800052f4  cmp     eax, 70000h
0x1800052f9  jnz     short loc_18000530C
0x1800052fb  movzx   ecx, cx
0x1800052fe  mov     eax, ecx
0x180005300  or      eax, 0C0070000h
0x180005305  test    ecx, ecx
0x180005307  cmovnz  ecx, eax
0x18000530a  jmp     short loc_180005339
0x18000530c  cmp     eax, 90000h
0x180005311  jnz     short loc_18000532D
0x180005313  test    ecx, ecx
0x180005315  jle     short loc_180005339
0x180005317  movzx   ecx, cx
0x18000531a  or      ecx, 0C0090000h
0x180005320  jmp     short loc_180005339
0x180005322  xor     ecx, ecx
0x180005324  jmp     short loc_180005339
0x180005326  mov     ecx, 0C000A083h
0x18000532b  jmp     short loc_180005339
0x18000532d  mov     ecx, 0C00000E5h
0x180005332  jmp     short loc_180005339
0x180005334  mov     ecx, 0C000042Bh
0x180005339  mov     eax, ecx
0x18000533b  retn
```
