# wil::details::HrToNtStatus(long)

- ea: `0x1800055c4`
- end: `0x180005780`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180002af4`
- `0x180002b6c`
- `0x180002be4`
- `0x180002c34`
- `0x180002c98`
- `0x180005940`

## callees

- `0x1800055c4`

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
0x1800055c4  mov     eax, 800700EAh
0x1800055c9  cmp     ecx, eax
0x1800055cb  jg      loc_1800056A0
0x1800055d1  jz      loc_180005696
0x1800055d7  mov     eax, 80070057h
0x1800055dc  cmp     ecx, eax
0x1800055de  jg      short loc_18000564A
0x1800055e0  jz      short loc_180005640
0x1800055e2  cmp     ecx, 80004005h
0x1800055e8  jz      short loc_180005636
0x1800055ea  cmp     ecx, 80070001h
0x1800055f0  jz      short loc_18000562C
0x1800055f2  cmp     ecx, 80070002h
0x1800055f8  jz      short loc_180005622
0x1800055fa  cmp     ecx, 80070003h
0x180005600  jz      short loc_180005618
0x180005602  cmp     ecx, 8007000Eh
0x180005608  jnz     loc_180005725
0x18000560e  mov     ecx, 0C0000017h
0x180005613  jmp     loc_18000577D
0x180005618  mov     ecx, 0C000003Ah
0x18000561d  jmp     loc_18000577D
0x180005622  mov     ecx, 0C0000034h
0x180005627  jmp     loc_18000577D
0x18000562c  mov     ecx, 0C0000002h
0x180005631  jmp     loc_18000577D
0x180005636  mov     ecx, 0C0000001h
0x18000563b  jmp     loc_18000577D
0x180005640  mov     ecx, 0C000000Dh
0x180005645  jmp     loc_18000577D
0x18000564a  cmp     ecx, 80070070h
0x180005650  jz      short loc_18000568C
0x180005652  cmp     ecx, 8007007Ah
0x180005658  jz      short loc_180005682
0x18000565a  cmp     ecx, 8007007Bh
0x180005660  jz      short loc_180005678
0x180005662  cmp     ecx, 8007007Eh
0x180005668  jnz     loc_180005725
0x18000566e  mov     ecx, 0C0000135h
0x180005673  jmp     loc_18000577D
0x180005678  mov     ecx, 0C0000033h
0x18000567d  jmp     loc_18000577D
0x180005682  mov     ecx, 0C0000023h
0x180005687  jmp     loc_18000577D
0x18000568c  mov     ecx, 0C000007Fh
0x180005691  jmp     loc_18000577D
0x180005696  mov     ecx, 80000005h
0x18000569b  jmp     loc_18000577D
0x1800056a0  mov     eax, 8007047Eh
0x1800056a5  cmp     ecx, eax
0x1800056a7  jg      short loc_180005709
0x1800056a9  jz      short loc_180005702
0x1800056ab  cmp     ecx, 80070216h
0x1800056b1  jz      short loc_1800056FB
0x1800056b3  cmp     ecx, 8007023Eh
0x1800056b9  jz      short loc_1800056F1
0x1800056bb  cmp     ecx, 80070246h
0x1800056c1  jz      short loc_1800056E7
0x1800056c3  cmp     ecx, 80070247h
0x1800056c9  jz      short loc_1800056DD
0x1800056cb  cmp     ecx, 80070272h
0x1800056d1  jnz     short loc_180005725
0x1800056d3  mov     ecx, 0C0000273h
0x1800056d8  jmp     loc_18000577D
0x1800056dd  mov     ecx, 0C0000163h
0x1800056e2  jmp     loc_18000577D
0x1800056e7  mov     ecx, 0C0000161h
0x1800056ec  jmp     loc_18000577D
0x1800056f1  mov     ecx, 0C0000025h
0x1800056f6  jmp     loc_18000577D
0x1800056fb  mov     ecx, 0C0000095h
0x180005700  jmp     short loc_18000577D
0x180005702  mov     ecx, 0C0000059h
0x180005707  jmp     short loc_18000577D
0x180005709  cmp     ecx, 8007050Ch
0x18000570f  jz      short loc_180005778
0x180005711  cmp     ecx, 8007054Fh
0x180005717  jz      short loc_180005771
0x180005719  cmp     ecx, 800705B9h
0x18000571f  jz      short loc_18000576A
0x180005721  test    ecx, ecx
0x180005723  jz      short loc_180005766
0x180005725  bt      ecx, 1Ch
0x180005729  jnb     short loc_180005731
0x18000572b  btr     ecx, 1Ch
0x18000572f  jmp     short loc_18000577D
0x180005731  mov     eax, ecx
0x180005733  and     eax, 1FFF0000h
0x180005738  cmp     eax, 70000h
0x18000573d  jnz     short loc_180005750
0x18000573f  movzx   ecx, cx
0x180005742  mov     eax, ecx
0x180005744  or      eax, 0C0070000h
0x180005749  test    ecx, ecx
0x18000574b  cmovnz  ecx, eax
0x18000574e  jmp     short loc_18000577D
0x180005750  cmp     eax, 90000h
0x180005755  jnz     short loc_180005771
0x180005757  test    ecx, ecx
0x180005759  jle     short loc_18000577D
0x18000575b  movzx   ecx, cx
0x18000575e  or      ecx, 0C0090000h
0x180005764  jmp     short loc_18000577D
0x180005766  xor     ecx, ecx
0x180005768  jmp     short loc_18000577D
0x18000576a  mov     ecx, 0C000A083h
0x18000576f  jmp     short loc_18000577D
0x180005771  mov     ecx, 0C00000E5h
0x180005776  jmp     short loc_18000577D
0x180005778  mov     ecx, 0C000042Bh
0x18000577d  mov     eax, ecx
0x18000577f  retn
```
