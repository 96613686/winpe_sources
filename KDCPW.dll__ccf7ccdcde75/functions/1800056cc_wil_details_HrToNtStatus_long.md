# wil::details::HrToNtStatus(long)

- ea: `0x1800056cc`
- end: `0x180005888`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180002964`
- `0x180002a04`
- `0x180002a54`
- `0x180002b14`
- `0x180004b38`
- `0x180005bec`

## callees

- `0x1800056cc`

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
0x1800056cc  mov     eax, 800700EAh
0x1800056d1  cmp     ecx, eax
0x1800056d3  jg      loc_1800057A8
0x1800056d9  jz      loc_18000579E
0x1800056df  mov     eax, 80070057h
0x1800056e4  cmp     ecx, eax
0x1800056e6  jg      short loc_180005752
0x1800056e8  jz      short loc_180005748
0x1800056ea  cmp     ecx, 80004005h
0x1800056f0  jz      short loc_18000573E
0x1800056f2  cmp     ecx, 80070001h
0x1800056f8  jz      short loc_180005734
0x1800056fa  cmp     ecx, 80070002h
0x180005700  jz      short loc_18000572A
0x180005702  cmp     ecx, 80070003h
0x180005708  jz      short loc_180005720
0x18000570a  cmp     ecx, 8007000Eh
0x180005710  jnz     loc_18000582D
0x180005716  mov     ecx, 0C0000017h
0x18000571b  jmp     loc_180005885
0x180005720  mov     ecx, 0C000003Ah
0x180005725  jmp     loc_180005885
0x18000572a  mov     ecx, 0C0000034h
0x18000572f  jmp     loc_180005885
0x180005734  mov     ecx, 0C0000002h
0x180005739  jmp     loc_180005885
0x18000573e  mov     ecx, 0C0000001h
0x180005743  jmp     loc_180005885
0x180005748  mov     ecx, 0C000000Dh
0x18000574d  jmp     loc_180005885
0x180005752  cmp     ecx, 80070070h
0x180005758  jz      short loc_180005794
0x18000575a  cmp     ecx, 8007007Ah
0x180005760  jz      short loc_18000578A
0x180005762  cmp     ecx, 8007007Bh
0x180005768  jz      short loc_180005780
0x18000576a  cmp     ecx, 8007007Eh
0x180005770  jnz     loc_18000582D
0x180005776  mov     ecx, 0C0000135h
0x18000577b  jmp     loc_180005885
0x180005780  mov     ecx, 0C0000033h
0x180005785  jmp     loc_180005885
0x18000578a  mov     ecx, 0C0000023h
0x18000578f  jmp     loc_180005885
0x180005794  mov     ecx, 0C000007Fh
0x180005799  jmp     loc_180005885
0x18000579e  mov     ecx, 80000005h
0x1800057a3  jmp     loc_180005885
0x1800057a8  mov     eax, 8007047Eh
0x1800057ad  cmp     ecx, eax
0x1800057af  jg      short loc_180005811
0x1800057b1  jz      short loc_18000580A
0x1800057b3  cmp     ecx, 80070216h
0x1800057b9  jz      short loc_180005803
0x1800057bb  cmp     ecx, 8007023Eh
0x1800057c1  jz      short loc_1800057F9
0x1800057c3  cmp     ecx, 80070246h
0x1800057c9  jz      short loc_1800057EF
0x1800057cb  cmp     ecx, 80070247h
0x1800057d1  jz      short loc_1800057E5
0x1800057d3  cmp     ecx, 80070272h
0x1800057d9  jnz     short loc_18000582D
0x1800057db  mov     ecx, 0C0000273h
0x1800057e0  jmp     loc_180005885
0x1800057e5  mov     ecx, 0C0000163h
0x1800057ea  jmp     loc_180005885
0x1800057ef  mov     ecx, 0C0000161h
0x1800057f4  jmp     loc_180005885
0x1800057f9  mov     ecx, 0C0000025h
0x1800057fe  jmp     loc_180005885
0x180005803  mov     ecx, 0C0000095h
0x180005808  jmp     short loc_180005885
0x18000580a  mov     ecx, 0C0000059h
0x18000580f  jmp     short loc_180005885
0x180005811  cmp     ecx, 8007050Ch
0x180005817  jz      short loc_180005880
0x180005819  cmp     ecx, 8007054Fh
0x18000581f  jz      short loc_180005879
0x180005821  cmp     ecx, 800705B9h
0x180005827  jz      short loc_180005872
0x180005829  test    ecx, ecx
0x18000582b  jz      short loc_18000586E
0x18000582d  bt      ecx, 1Ch
0x180005831  jnb     short loc_180005839
0x180005833  btr     ecx, 1Ch
0x180005837  jmp     short loc_180005885
0x180005839  mov     eax, ecx
0x18000583b  and     eax, 1FFF0000h
0x180005840  cmp     eax, 70000h
0x180005845  jnz     short loc_180005858
0x180005847  movzx   ecx, cx
0x18000584a  mov     eax, ecx
0x18000584c  or      eax, 0C0070000h
0x180005851  test    ecx, ecx
0x180005853  cmovnz  ecx, eax
0x180005856  jmp     short loc_180005885
0x180005858  cmp     eax, 90000h
0x18000585d  jnz     short loc_180005879
0x18000585f  test    ecx, ecx
0x180005861  jle     short loc_180005885
0x180005863  movzx   ecx, cx
0x180005866  or      ecx, 0C0090000h
0x18000586c  jmp     short loc_180005885
0x18000586e  xor     ecx, ecx
0x180005870  jmp     short loc_180005885
0x180005872  mov     ecx, 0C000A083h
0x180005877  jmp     short loc_180005885
0x180005879  mov     ecx, 0C00000E5h
0x18000587e  jmp     short loc_180005885
0x180005880  mov     ecx, 0C000042Bh
0x180005885  mov     eax, ecx
0x180005887  retn
```
