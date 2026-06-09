# wil::details::HrToNtStatus(long)

- ea: `0x1400042f0`
- end: `0x1400044ac`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x1400025e0`
- `0x140002680`
- `0x1400026d0`
- `0x140002798`
- `0x1400038c8`
- `0x1400044b4`
- `0x140004c30`
- `0x140006608`
- `0x140011707`
- `0x140011772`
- `0x14001183b`
- `0x1400118a6`

## callees

- `0x1400042f0`

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
0x1400042f0  mov     eax, 800700EAh
0x1400042f5  cmp     ecx, eax
0x1400042f7  jg      loc_1400043CC
0x1400042fd  jz      loc_1400043C2
0x140004303  mov     eax, 80070057h
0x140004308  cmp     ecx, eax
0x14000430a  jg      short loc_140004376
0x14000430c  jz      short loc_14000436C
0x14000430e  cmp     ecx, 80004005h
0x140004314  jz      short loc_140004362
0x140004316  cmp     ecx, 80070001h
0x14000431c  jz      short loc_140004358
0x14000431e  cmp     ecx, 80070002h
0x140004324  jz      short loc_14000434E
0x140004326  cmp     ecx, 80070003h
0x14000432c  jz      short loc_140004344
0x14000432e  cmp     ecx, 8007000Eh
0x140004334  jnz     loc_140004451
0x14000433a  mov     ecx, 0C0000017h
0x14000433f  jmp     loc_1400044A9
0x140004344  mov     ecx, 0C000003Ah
0x140004349  jmp     loc_1400044A9
0x14000434e  mov     ecx, 0C0000034h
0x140004353  jmp     loc_1400044A9
0x140004358  mov     ecx, 0C0000002h
0x14000435d  jmp     loc_1400044A9
0x140004362  mov     ecx, 0C0000001h
0x140004367  jmp     loc_1400044A9
0x14000436c  mov     ecx, 0C000000Dh
0x140004371  jmp     loc_1400044A9
0x140004376  cmp     ecx, 80070070h
0x14000437c  jz      short loc_1400043B8
0x14000437e  cmp     ecx, 8007007Ah
0x140004384  jz      short loc_1400043AE
0x140004386  cmp     ecx, 8007007Bh
0x14000438c  jz      short loc_1400043A4
0x14000438e  cmp     ecx, 8007007Eh
0x140004394  jnz     loc_140004451
0x14000439a  mov     ecx, 0C0000135h
0x14000439f  jmp     loc_1400044A9
0x1400043a4  mov     ecx, 0C0000033h
0x1400043a9  jmp     loc_1400044A9
0x1400043ae  mov     ecx, 0C0000023h
0x1400043b3  jmp     loc_1400044A9
0x1400043b8  mov     ecx, 0C000007Fh
0x1400043bd  jmp     loc_1400044A9
0x1400043c2  mov     ecx, 80000005h
0x1400043c7  jmp     loc_1400044A9
0x1400043cc  mov     eax, 8007047Eh
0x1400043d1  cmp     ecx, eax
0x1400043d3  jg      short loc_140004435
0x1400043d5  jz      short loc_14000442E
0x1400043d7  cmp     ecx, 80070216h
0x1400043dd  jz      short loc_140004427
0x1400043df  cmp     ecx, 8007023Eh
0x1400043e5  jz      short loc_14000441D
0x1400043e7  cmp     ecx, 80070246h
0x1400043ed  jz      short loc_140004413
0x1400043ef  cmp     ecx, 80070247h
0x1400043f5  jz      short loc_140004409
0x1400043f7  cmp     ecx, 80070272h
0x1400043fd  jnz     short loc_140004451
0x1400043ff  mov     ecx, 0C0000273h
0x140004404  jmp     loc_1400044A9
0x140004409  mov     ecx, 0C0000163h
0x14000440e  jmp     loc_1400044A9
0x140004413  mov     ecx, 0C0000161h
0x140004418  jmp     loc_1400044A9
0x14000441d  mov     ecx, 0C0000025h
0x140004422  jmp     loc_1400044A9
0x140004427  mov     ecx, 0C0000095h
0x14000442c  jmp     short loc_1400044A9
0x14000442e  mov     ecx, 0C0000059h
0x140004433  jmp     short loc_1400044A9
0x140004435  cmp     ecx, 8007050Ch
0x14000443b  jz      short loc_1400044A4
0x14000443d  cmp     ecx, 8007054Fh
0x140004443  jz      short loc_14000449D
0x140004445  cmp     ecx, 800705B9h
0x14000444b  jz      short loc_140004496
0x14000444d  test    ecx, ecx
0x14000444f  jz      short loc_140004492
0x140004451  bt      ecx, 1Ch
0x140004455  jnb     short loc_14000445D
0x140004457  btr     ecx, 1Ch
0x14000445b  jmp     short loc_1400044A9
0x14000445d  mov     eax, ecx
0x14000445f  and     eax, 1FFF0000h
0x140004464  cmp     eax, 70000h
0x140004469  jnz     short loc_14000447C
0x14000446b  movzx   ecx, cx
0x14000446e  mov     eax, ecx
0x140004470  or      eax, 0C0070000h
0x140004475  test    ecx, ecx
0x140004477  cmovnz  ecx, eax
0x14000447a  jmp     short loc_1400044A9
0x14000447c  cmp     eax, 90000h
0x140004481  jnz     short loc_14000449D
0x140004483  test    ecx, ecx
0x140004485  jle     short loc_1400044A9
0x140004487  movzx   ecx, cx
0x14000448a  or      ecx, 0C0090000h
0x140004490  jmp     short loc_1400044A9
0x140004492  xor     ecx, ecx
0x140004494  jmp     short loc_1400044A9
0x140004496  mov     ecx, 0C000A083h
0x14000449b  jmp     short loc_1400044A9
0x14000449d  mov     ecx, 0C00000E5h
0x1400044a2  jmp     short loc_1400044A9
0x1400044a4  mov     ecx, 0C000042Bh
0x1400044a9  mov     eax, ecx
0x1400044ab  retn
```
