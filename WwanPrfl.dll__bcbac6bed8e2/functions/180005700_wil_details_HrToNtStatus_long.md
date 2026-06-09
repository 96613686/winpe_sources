# wil::details::HrToNtStatus(long)

- ea: `0x180005700`
- end: `0x1800058bc`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180002688`
- `0x180002728`
- `0x180002778`
- `0x180002838`
- `0x180004b18`
- `0x1800059ac`

## callees

- `0x180005700`

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
0x180005700  mov     eax, 800700EAh
0x180005705  cmp     ecx, eax
0x180005707  jg      loc_1800057DC
0x18000570d  jz      loc_1800057D2
0x180005713  mov     eax, 80070057h
0x180005718  cmp     ecx, eax
0x18000571a  jg      short loc_180005786
0x18000571c  jz      short loc_18000577C
0x18000571e  cmp     ecx, 80004005h
0x180005724  jz      short loc_180005772
0x180005726  cmp     ecx, 80070001h
0x18000572c  jz      short loc_180005768
0x18000572e  cmp     ecx, 80070002h
0x180005734  jz      short loc_18000575E
0x180005736  cmp     ecx, 80070003h
0x18000573c  jz      short loc_180005754
0x18000573e  cmp     ecx, 8007000Eh
0x180005744  jnz     loc_180005861
0x18000574a  mov     ecx, 0C0000017h
0x18000574f  jmp     loc_1800058B9
0x180005754  mov     ecx, 0C000003Ah
0x180005759  jmp     loc_1800058B9
0x18000575e  mov     ecx, 0C0000034h
0x180005763  jmp     loc_1800058B9
0x180005768  mov     ecx, 0C0000002h
0x18000576d  jmp     loc_1800058B9
0x180005772  mov     ecx, 0C0000001h
0x180005777  jmp     loc_1800058B9
0x18000577c  mov     ecx, 0C000000Dh
0x180005781  jmp     loc_1800058B9
0x180005786  cmp     ecx, 80070070h
0x18000578c  jz      short loc_1800057C8
0x18000578e  cmp     ecx, 8007007Ah
0x180005794  jz      short loc_1800057BE
0x180005796  cmp     ecx, 8007007Bh
0x18000579c  jz      short loc_1800057B4
0x18000579e  cmp     ecx, 8007007Eh
0x1800057a4  jnz     loc_180005861
0x1800057aa  mov     ecx, 0C0000135h
0x1800057af  jmp     loc_1800058B9
0x1800057b4  mov     ecx, 0C0000033h
0x1800057b9  jmp     loc_1800058B9
0x1800057be  mov     ecx, 0C0000023h
0x1800057c3  jmp     loc_1800058B9
0x1800057c8  mov     ecx, 0C000007Fh
0x1800057cd  jmp     loc_1800058B9
0x1800057d2  mov     ecx, 80000005h
0x1800057d7  jmp     loc_1800058B9
0x1800057dc  mov     eax, 8007047Eh
0x1800057e1  cmp     ecx, eax
0x1800057e3  jg      short loc_180005845
0x1800057e5  jz      short loc_18000583E
0x1800057e7  cmp     ecx, 80070216h
0x1800057ed  jz      short loc_180005837
0x1800057ef  cmp     ecx, 8007023Eh
0x1800057f5  jz      short loc_18000582D
0x1800057f7  cmp     ecx, 80070246h
0x1800057fd  jz      short loc_180005823
0x1800057ff  cmp     ecx, 80070247h
0x180005805  jz      short loc_180005819
0x180005807  cmp     ecx, 80070272h
0x18000580d  jnz     short loc_180005861
0x18000580f  mov     ecx, 0C0000273h
0x180005814  jmp     loc_1800058B9
0x180005819  mov     ecx, 0C0000163h
0x18000581e  jmp     loc_1800058B9
0x180005823  mov     ecx, 0C0000161h
0x180005828  jmp     loc_1800058B9
0x18000582d  mov     ecx, 0C0000025h
0x180005832  jmp     loc_1800058B9
0x180005837  mov     ecx, 0C0000095h
0x18000583c  jmp     short loc_1800058B9
0x18000583e  mov     ecx, 0C0000059h
0x180005843  jmp     short loc_1800058B9
0x180005845  cmp     ecx, 8007050Ch
0x18000584b  jz      short loc_1800058B4
0x18000584d  cmp     ecx, 8007054Fh
0x180005853  jz      short loc_1800058AD
0x180005855  cmp     ecx, 800705B9h
0x18000585b  jz      short loc_1800058A6
0x18000585d  test    ecx, ecx
0x18000585f  jz      short loc_1800058A2
0x180005861  bt      ecx, 1Ch
0x180005865  jnb     short loc_18000586D
0x180005867  btr     ecx, 1Ch
0x18000586b  jmp     short loc_1800058B9
0x18000586d  mov     eax, ecx
0x18000586f  and     eax, 1FFF0000h
0x180005874  cmp     eax, 70000h
0x180005879  jnz     short loc_18000588C
0x18000587b  movzx   ecx, cx
0x18000587e  mov     eax, ecx
0x180005880  or      eax, 0C0070000h
0x180005885  test    ecx, ecx
0x180005887  cmovnz  ecx, eax
0x18000588a  jmp     short loc_1800058B9
0x18000588c  cmp     eax, 90000h
0x180005891  jnz     short loc_1800058AD
0x180005893  test    ecx, ecx
0x180005895  jle     short loc_1800058B9
0x180005897  movzx   ecx, cx
0x18000589a  or      ecx, 0C0090000h
0x1800058a0  jmp     short loc_1800058B9
0x1800058a2  xor     ecx, ecx
0x1800058a4  jmp     short loc_1800058B9
0x1800058a6  mov     ecx, 0C000A083h
0x1800058ab  jmp     short loc_1800058B9
0x1800058ad  mov     ecx, 0C00000E5h
0x1800058b2  jmp     short loc_1800058B9
0x1800058b4  mov     ecx, 0C000042Bh
0x1800058b9  mov     eax, ecx
0x1800058bb  retn
```
