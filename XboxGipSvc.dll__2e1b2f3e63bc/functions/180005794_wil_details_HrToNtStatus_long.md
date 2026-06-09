# wil::details::HrToNtStatus(long)

- ea: `0x180005794`
- end: `0x180005950`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180003dbc`
- `0x180003e64`
- `0x180003eb4`
- `0x18000505c`
- `0x1800059f0`
- `0x180006c68`
- `0x18000e160`

## callees

- `0x180005794`

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
0x180005794  mov     eax, 800700EAh
0x180005799  cmp     ecx, eax
0x18000579b  jg      loc_180005870
0x1800057a1  jz      loc_180005866
0x1800057a7  mov     eax, 80070057h
0x1800057ac  cmp     ecx, eax
0x1800057ae  jg      short loc_18000581A
0x1800057b0  jz      short loc_180005810
0x1800057b2  cmp     ecx, 80004005h
0x1800057b8  jz      short loc_180005806
0x1800057ba  cmp     ecx, 80070001h
0x1800057c0  jz      short loc_1800057FC
0x1800057c2  cmp     ecx, 80070002h
0x1800057c8  jz      short loc_1800057F2
0x1800057ca  cmp     ecx, 80070003h
0x1800057d0  jz      short loc_1800057E8
0x1800057d2  cmp     ecx, 8007000Eh
0x1800057d8  jnz     loc_1800058F5
0x1800057de  mov     ecx, 0C0000017h
0x1800057e3  jmp     loc_18000594D
0x1800057e8  mov     ecx, 0C000003Ah
0x1800057ed  jmp     loc_18000594D
0x1800057f2  mov     ecx, 0C0000034h
0x1800057f7  jmp     loc_18000594D
0x1800057fc  mov     ecx, 0C0000002h
0x180005801  jmp     loc_18000594D
0x180005806  mov     ecx, 0C0000001h
0x18000580b  jmp     loc_18000594D
0x180005810  mov     ecx, 0C000000Dh
0x180005815  jmp     loc_18000594D
0x18000581a  cmp     ecx, 80070070h
0x180005820  jz      short loc_18000585C
0x180005822  cmp     ecx, 8007007Ah
0x180005828  jz      short loc_180005852
0x18000582a  cmp     ecx, 8007007Bh
0x180005830  jz      short loc_180005848
0x180005832  cmp     ecx, 8007007Eh
0x180005838  jnz     loc_1800058F5
0x18000583e  mov     ecx, 0C0000135h
0x180005843  jmp     loc_18000594D
0x180005848  mov     ecx, 0C0000033h
0x18000584d  jmp     loc_18000594D
0x180005852  mov     ecx, 0C0000023h
0x180005857  jmp     loc_18000594D
0x18000585c  mov     ecx, 0C000007Fh
0x180005861  jmp     loc_18000594D
0x180005866  mov     ecx, 80000005h
0x18000586b  jmp     loc_18000594D
0x180005870  mov     eax, 8007047Eh
0x180005875  cmp     ecx, eax
0x180005877  jg      short loc_1800058D9
0x180005879  jz      short loc_1800058D2
0x18000587b  cmp     ecx, 80070216h
0x180005881  jz      short loc_1800058CB
0x180005883  cmp     ecx, 8007023Eh
0x180005889  jz      short loc_1800058C1
0x18000588b  cmp     ecx, 80070246h
0x180005891  jz      short loc_1800058B7
0x180005893  cmp     ecx, 80070247h
0x180005899  jz      short loc_1800058AD
0x18000589b  cmp     ecx, 80070272h
0x1800058a1  jnz     short loc_1800058F5
0x1800058a3  mov     ecx, 0C0000273h
0x1800058a8  jmp     loc_18000594D
0x1800058ad  mov     ecx, 0C0000163h
0x1800058b2  jmp     loc_18000594D
0x1800058b7  mov     ecx, 0C0000161h
0x1800058bc  jmp     loc_18000594D
0x1800058c1  mov     ecx, 0C0000025h
0x1800058c6  jmp     loc_18000594D
0x1800058cb  mov     ecx, 0C0000095h
0x1800058d0  jmp     short loc_18000594D
0x1800058d2  mov     ecx, 0C0000059h
0x1800058d7  jmp     short loc_18000594D
0x1800058d9  cmp     ecx, 8007050Ch
0x1800058df  jz      short loc_180005948
0x1800058e1  cmp     ecx, 8007054Fh
0x1800058e7  jz      short loc_180005941
0x1800058e9  cmp     ecx, 800705B9h
0x1800058ef  jz      short loc_18000593A
0x1800058f1  test    ecx, ecx
0x1800058f3  jz      short loc_180005936
0x1800058f5  bt      ecx, 1Ch
0x1800058f9  jnb     short loc_180005901
0x1800058fb  btr     ecx, 1Ch
0x1800058ff  jmp     short loc_18000594D
0x180005901  mov     eax, ecx
0x180005903  and     eax, 1FFF0000h
0x180005908  cmp     eax, 70000h
0x18000590d  jnz     short loc_180005920
0x18000590f  movzx   ecx, cx
0x180005912  mov     eax, ecx
0x180005914  or      eax, 0C0070000h
0x180005919  test    ecx, ecx
0x18000591b  cmovnz  ecx, eax
0x18000591e  jmp     short loc_18000594D
0x180005920  cmp     eax, 90000h
0x180005925  jnz     short loc_180005941
0x180005927  test    ecx, ecx
0x180005929  jle     short loc_18000594D
0x18000592b  movzx   ecx, cx
0x18000592e  or      ecx, 0C0090000h
0x180005934  jmp     short loc_18000594D
0x180005936  xor     ecx, ecx
0x180005938  jmp     short loc_18000594D
0x18000593a  mov     ecx, 0C000A083h
0x18000593f  jmp     short loc_18000594D
0x180005941  mov     ecx, 0C00000E5h
0x180005946  jmp     short loc_18000594D
0x180005948  mov     ecx, 0C000042Bh
0x18000594d  mov     eax, ecx
0x18000594f  retn
```
