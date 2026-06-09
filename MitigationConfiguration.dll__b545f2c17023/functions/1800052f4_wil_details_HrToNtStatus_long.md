# wil::details::HrToNtStatus(long)

- ea: `0x1800052f4`
- end: `0x1800054b0`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180002b88`
- `0x180002c30`
- `0x180002c80`
- `0x180002d38`
- `0x1800048c8`
- `0x1800054e0`

## callees

- `0x1800052f4`

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
0x1800052f4  mov     eax, 800700EAh
0x1800052f9  cmp     ecx, eax
0x1800052fb  jg      loc_1800053D0
0x180005301  jz      loc_1800053C6
0x180005307  mov     eax, 80070057h
0x18000530c  cmp     ecx, eax
0x18000530e  jg      short loc_18000537A
0x180005310  jz      short loc_180005370
0x180005312  cmp     ecx, 80004005h
0x180005318  jz      short loc_180005366
0x18000531a  cmp     ecx, 80070001h
0x180005320  jz      short loc_18000535C
0x180005322  cmp     ecx, 80070002h
0x180005328  jz      short loc_180005352
0x18000532a  cmp     ecx, 80070003h
0x180005330  jz      short loc_180005348
0x180005332  cmp     ecx, 8007000Eh
0x180005338  jnz     loc_180005455
0x18000533e  mov     ecx, 0C0000017h
0x180005343  jmp     loc_1800054AD
0x180005348  mov     ecx, 0C000003Ah
0x18000534d  jmp     loc_1800054AD
0x180005352  mov     ecx, 0C0000034h
0x180005357  jmp     loc_1800054AD
0x18000535c  mov     ecx, 0C0000002h
0x180005361  jmp     loc_1800054AD
0x180005366  mov     ecx, 0C0000001h
0x18000536b  jmp     loc_1800054AD
0x180005370  mov     ecx, 0C000000Dh
0x180005375  jmp     loc_1800054AD
0x18000537a  cmp     ecx, 80070070h
0x180005380  jz      short loc_1800053BC
0x180005382  cmp     ecx, 8007007Ah
0x180005388  jz      short loc_1800053B2
0x18000538a  cmp     ecx, 8007007Bh
0x180005390  jz      short loc_1800053A8
0x180005392  cmp     ecx, 8007007Eh
0x180005398  jnz     loc_180005455
0x18000539e  mov     ecx, 0C0000135h
0x1800053a3  jmp     loc_1800054AD
0x1800053a8  mov     ecx, 0C0000033h
0x1800053ad  jmp     loc_1800054AD
0x1800053b2  mov     ecx, 0C0000023h
0x1800053b7  jmp     loc_1800054AD
0x1800053bc  mov     ecx, 0C000007Fh
0x1800053c1  jmp     loc_1800054AD
0x1800053c6  mov     ecx, 80000005h
0x1800053cb  jmp     loc_1800054AD
0x1800053d0  mov     eax, 8007047Eh
0x1800053d5  cmp     ecx, eax
0x1800053d7  jg      short loc_180005439
0x1800053d9  jz      short loc_180005432
0x1800053db  cmp     ecx, 80070216h
0x1800053e1  jz      short loc_18000542B
0x1800053e3  cmp     ecx, 8007023Eh
0x1800053e9  jz      short loc_180005421
0x1800053eb  cmp     ecx, 80070246h
0x1800053f1  jz      short loc_180005417
0x1800053f3  cmp     ecx, 80070247h
0x1800053f9  jz      short loc_18000540D
0x1800053fb  cmp     ecx, 80070272h
0x180005401  jnz     short loc_180005455
0x180005403  mov     ecx, 0C0000273h
0x180005408  jmp     loc_1800054AD
0x18000540d  mov     ecx, 0C0000163h
0x180005412  jmp     loc_1800054AD
0x180005417  mov     ecx, 0C0000161h
0x18000541c  jmp     loc_1800054AD
0x180005421  mov     ecx, 0C0000025h
0x180005426  jmp     loc_1800054AD
0x18000542b  mov     ecx, 0C0000095h
0x180005430  jmp     short loc_1800054AD
0x180005432  mov     ecx, 0C0000059h
0x180005437  jmp     short loc_1800054AD
0x180005439  cmp     ecx, 8007050Ch
0x18000543f  jz      short loc_1800054A8
0x180005441  cmp     ecx, 8007054Fh
0x180005447  jz      short loc_1800054A1
0x180005449  cmp     ecx, 800705B9h
0x18000544f  jz      short loc_18000549A
0x180005451  test    ecx, ecx
0x180005453  jz      short loc_180005496
0x180005455  bt      ecx, 1Ch
0x180005459  jnb     short loc_180005461
0x18000545b  btr     ecx, 1Ch
0x18000545f  jmp     short loc_1800054AD
0x180005461  mov     eax, ecx
0x180005463  and     eax, 1FFF0000h
0x180005468  cmp     eax, 70000h
0x18000546d  jnz     short loc_180005480
0x18000546f  movzx   ecx, cx
0x180005472  mov     eax, ecx
0x180005474  or      eax, 0C0070000h
0x180005479  test    ecx, ecx
0x18000547b  cmovnz  ecx, eax
0x18000547e  jmp     short loc_1800054AD
0x180005480  cmp     eax, 90000h
0x180005485  jnz     short loc_1800054A1
0x180005487  test    ecx, ecx
0x180005489  jle     short loc_1800054AD
0x18000548b  movzx   ecx, cx
0x18000548e  or      ecx, 0C0090000h
0x180005494  jmp     short loc_1800054AD
0x180005496  xor     ecx, ecx
0x180005498  jmp     short loc_1800054AD
0x18000549a  mov     ecx, 0C000A083h
0x18000549f  jmp     short loc_1800054AD
0x1800054a1  mov     ecx, 0C00000E5h
0x1800054a6  jmp     short loc_1800054AD
0x1800054a8  mov     ecx, 0C000042Bh
0x1800054ad  mov     eax, ecx
0x1800054af  retn
```
