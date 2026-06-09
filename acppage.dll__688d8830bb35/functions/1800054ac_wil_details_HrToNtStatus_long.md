# wil::details::HrToNtStatus(long)

- ea: `0x1800054ac`
- end: `0x180005668`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180002744`
- `0x1800027e4`
- `0x180002834`
- `0x1800028f4`
- `0x1800049f8`
- `0x180005794`

## callees

- `0x1800054ac`

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
0x1800054ac  mov     eax, 800700EAh
0x1800054b1  cmp     ecx, eax
0x1800054b3  jg      loc_180005588
0x1800054b9  jz      loc_18000557E
0x1800054bf  mov     eax, 80070057h
0x1800054c4  cmp     ecx, eax
0x1800054c6  jg      short loc_180005532
0x1800054c8  jz      short loc_180005528
0x1800054ca  cmp     ecx, 80004005h
0x1800054d0  jz      short loc_18000551E
0x1800054d2  cmp     ecx, 80070001h
0x1800054d8  jz      short loc_180005514
0x1800054da  cmp     ecx, 80070002h
0x1800054e0  jz      short loc_18000550A
0x1800054e2  cmp     ecx, 80070003h
0x1800054e8  jz      short loc_180005500
0x1800054ea  cmp     ecx, 8007000Eh
0x1800054f0  jnz     loc_18000560D
0x1800054f6  mov     ecx, 0C0000017h
0x1800054fb  jmp     loc_180005665
0x180005500  mov     ecx, 0C000003Ah
0x180005505  jmp     loc_180005665
0x18000550a  mov     ecx, 0C0000034h
0x18000550f  jmp     loc_180005665
0x180005514  mov     ecx, 0C0000002h
0x180005519  jmp     loc_180005665
0x18000551e  mov     ecx, 0C0000001h
0x180005523  jmp     loc_180005665
0x180005528  mov     ecx, 0C000000Dh
0x18000552d  jmp     loc_180005665
0x180005532  cmp     ecx, 80070070h
0x180005538  jz      short loc_180005574
0x18000553a  cmp     ecx, 8007007Ah
0x180005540  jz      short loc_18000556A
0x180005542  cmp     ecx, 8007007Bh
0x180005548  jz      short loc_180005560
0x18000554a  cmp     ecx, 8007007Eh
0x180005550  jnz     loc_18000560D
0x180005556  mov     ecx, 0C0000135h
0x18000555b  jmp     loc_180005665
0x180005560  mov     ecx, 0C0000033h
0x180005565  jmp     loc_180005665
0x18000556a  mov     ecx, 0C0000023h
0x18000556f  jmp     loc_180005665
0x180005574  mov     ecx, 0C000007Fh
0x180005579  jmp     loc_180005665
0x18000557e  mov     ecx, 80000005h
0x180005583  jmp     loc_180005665
0x180005588  mov     eax, 8007047Eh
0x18000558d  cmp     ecx, eax
0x18000558f  jg      short loc_1800055F1
0x180005591  jz      short loc_1800055EA
0x180005593  cmp     ecx, 80070216h
0x180005599  jz      short loc_1800055E3
0x18000559b  cmp     ecx, 8007023Eh
0x1800055a1  jz      short loc_1800055D9
0x1800055a3  cmp     ecx, 80070246h
0x1800055a9  jz      short loc_1800055CF
0x1800055ab  cmp     ecx, 80070247h
0x1800055b1  jz      short loc_1800055C5
0x1800055b3  cmp     ecx, 80070272h
0x1800055b9  jnz     short loc_18000560D
0x1800055bb  mov     ecx, 0C0000273h
0x1800055c0  jmp     loc_180005665
0x1800055c5  mov     ecx, 0C0000163h
0x1800055ca  jmp     loc_180005665
0x1800055cf  mov     ecx, 0C0000161h
0x1800055d4  jmp     loc_180005665
0x1800055d9  mov     ecx, 0C0000025h
0x1800055de  jmp     loc_180005665
0x1800055e3  mov     ecx, 0C0000095h
0x1800055e8  jmp     short loc_180005665
0x1800055ea  mov     ecx, 0C0000059h
0x1800055ef  jmp     short loc_180005665
0x1800055f1  cmp     ecx, 8007050Ch
0x1800055f7  jz      short loc_180005660
0x1800055f9  cmp     ecx, 8007054Fh
0x1800055ff  jz      short loc_180005659
0x180005601  cmp     ecx, 800705B9h
0x180005607  jz      short loc_180005652
0x180005609  test    ecx, ecx
0x18000560b  jz      short loc_18000564E
0x18000560d  bt      ecx, 1Ch
0x180005611  jnb     short loc_180005619
0x180005613  btr     ecx, 1Ch
0x180005617  jmp     short loc_180005665
0x180005619  mov     eax, ecx
0x18000561b  and     eax, 1FFF0000h
0x180005620  cmp     eax, 70000h
0x180005625  jnz     short loc_180005638
0x180005627  movzx   ecx, cx
0x18000562a  mov     eax, ecx
0x18000562c  or      eax, 0C0070000h
0x180005631  test    ecx, ecx
0x180005633  cmovnz  ecx, eax
0x180005636  jmp     short loc_180005665
0x180005638  cmp     eax, 90000h
0x18000563d  jnz     short loc_180005659
0x18000563f  test    ecx, ecx
0x180005641  jle     short loc_180005665
0x180005643  movzx   ecx, cx
0x180005646  or      ecx, 0C0090000h
0x18000564c  jmp     short loc_180005665
0x18000564e  xor     ecx, ecx
0x180005650  jmp     short loc_180005665
0x180005652  mov     ecx, 0C000A083h
0x180005657  jmp     short loc_180005665
0x180005659  mov     ecx, 0C00000E5h
0x18000565e  jmp     short loc_180005665
0x180005660  mov     ecx, 0C000042Bh
0x180005665  mov     eax, ecx
0x180005667  retn
```
