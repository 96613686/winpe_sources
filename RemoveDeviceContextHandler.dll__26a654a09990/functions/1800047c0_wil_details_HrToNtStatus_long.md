# wil::details::HrToNtStatus(long)

- ea: `0x1800047c0`
- end: `0x18000497c`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180002bd4`
- `0x180002c74`
- `0x180002cc4`
- `0x180002d7c`
- `0x180003288`
- `0x180003db8`

## callees

- `0x1800047c0`

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
0x1800047c0  mov     eax, 800700EAh
0x1800047c5  cmp     ecx, eax
0x1800047c7  jg      loc_18000489C
0x1800047cd  jz      loc_180004892
0x1800047d3  mov     eax, 80070057h
0x1800047d8  cmp     ecx, eax
0x1800047da  jg      short loc_180004846
0x1800047dc  jz      short loc_18000483C
0x1800047de  cmp     ecx, 80004005h
0x1800047e4  jz      short loc_180004832
0x1800047e6  cmp     ecx, 80070001h
0x1800047ec  jz      short loc_180004828
0x1800047ee  cmp     ecx, 80070002h
0x1800047f4  jz      short loc_18000481E
0x1800047f6  cmp     ecx, 80070003h
0x1800047fc  jz      short loc_180004814
0x1800047fe  cmp     ecx, 8007000Eh
0x180004804  jnz     loc_180004921
0x18000480a  mov     ecx, 0C0000017h
0x18000480f  jmp     loc_180004979
0x180004814  mov     ecx, 0C000003Ah
0x180004819  jmp     loc_180004979
0x18000481e  mov     ecx, 0C0000034h
0x180004823  jmp     loc_180004979
0x180004828  mov     ecx, 0C0000002h
0x18000482d  jmp     loc_180004979
0x180004832  mov     ecx, 0C0000001h
0x180004837  jmp     loc_180004979
0x18000483c  mov     ecx, 0C000000Dh
0x180004841  jmp     loc_180004979
0x180004846  cmp     ecx, 80070070h
0x18000484c  jz      short loc_180004888
0x18000484e  cmp     ecx, 8007007Ah
0x180004854  jz      short loc_18000487E
0x180004856  cmp     ecx, 8007007Bh
0x18000485c  jz      short loc_180004874
0x18000485e  cmp     ecx, 8007007Eh
0x180004864  jnz     loc_180004921
0x18000486a  mov     ecx, 0C0000135h
0x18000486f  jmp     loc_180004979
0x180004874  mov     ecx, 0C0000033h
0x180004879  jmp     loc_180004979
0x18000487e  mov     ecx, 0C0000023h
0x180004883  jmp     loc_180004979
0x180004888  mov     ecx, 0C000007Fh
0x18000488d  jmp     loc_180004979
0x180004892  mov     ecx, 80000005h
0x180004897  jmp     loc_180004979
0x18000489c  mov     eax, 8007047Eh
0x1800048a1  cmp     ecx, eax
0x1800048a3  jg      short loc_180004905
0x1800048a5  jz      short loc_1800048FE
0x1800048a7  cmp     ecx, 80070216h
0x1800048ad  jz      short loc_1800048F7
0x1800048af  cmp     ecx, 8007023Eh
0x1800048b5  jz      short loc_1800048ED
0x1800048b7  cmp     ecx, 80070246h
0x1800048bd  jz      short loc_1800048E3
0x1800048bf  cmp     ecx, 80070247h
0x1800048c5  jz      short loc_1800048D9
0x1800048c7  cmp     ecx, 80070272h
0x1800048cd  jnz     short loc_180004921
0x1800048cf  mov     ecx, 0C0000273h
0x1800048d4  jmp     loc_180004979
0x1800048d9  mov     ecx, 0C0000163h
0x1800048de  jmp     loc_180004979
0x1800048e3  mov     ecx, 0C0000161h
0x1800048e8  jmp     loc_180004979
0x1800048ed  mov     ecx, 0C0000025h
0x1800048f2  jmp     loc_180004979
0x1800048f7  mov     ecx, 0C0000095h
0x1800048fc  jmp     short loc_180004979
0x1800048fe  mov     ecx, 0C0000059h
0x180004903  jmp     short loc_180004979
0x180004905  cmp     ecx, 8007050Ch
0x18000490b  jz      short loc_180004974
0x18000490d  cmp     ecx, 8007054Fh
0x180004913  jz      short loc_18000496D
0x180004915  cmp     ecx, 800705B9h
0x18000491b  jz      short loc_180004966
0x18000491d  test    ecx, ecx
0x18000491f  jz      short loc_180004962
0x180004921  bt      ecx, 1Ch
0x180004925  jnb     short loc_18000492D
0x180004927  btr     ecx, 1Ch
0x18000492b  jmp     short loc_180004979
0x18000492d  mov     eax, ecx
0x18000492f  and     eax, 1FFF0000h
0x180004934  cmp     eax, 70000h
0x180004939  jnz     short loc_18000494C
0x18000493b  movzx   ecx, cx
0x18000493e  mov     eax, ecx
0x180004940  or      eax, 0C0070000h
0x180004945  test    ecx, ecx
0x180004947  cmovnz  ecx, eax
0x18000494a  jmp     short loc_180004979
0x18000494c  cmp     eax, 90000h
0x180004951  jnz     short loc_18000496D
0x180004953  test    ecx, ecx
0x180004955  jle     short loc_180004979
0x180004957  movzx   ecx, cx
0x18000495a  or      ecx, 0C0090000h
0x180004960  jmp     short loc_180004979
0x180004962  xor     ecx, ecx
0x180004964  jmp     short loc_180004979
0x180004966  mov     ecx, 0C000A083h
0x18000496b  jmp     short loc_180004979
0x18000496d  mov     ecx, 0C00000E5h
0x180004972  jmp     short loc_180004979
0x180004974  mov     ecx, 0C000042Bh
0x180004979  mov     eax, ecx
0x18000497b  retn
```
