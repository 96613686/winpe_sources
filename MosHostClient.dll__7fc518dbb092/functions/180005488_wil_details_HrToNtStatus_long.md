# wil::details::HrToNtStatus(long)

- ea: `0x180005488`
- end: `0x180005644`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x18000341c`
- `0x1800034c4`
- `0x180003514`
- `0x1800035cc`
- `0x1800049b8`
- `0x18000568c`

## callees

- `0x180005488`

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
0x180005488  mov     eax, 800700EAh
0x18000548d  cmp     ecx, eax
0x18000548f  jg      loc_180005564
0x180005495  jz      loc_18000555A
0x18000549b  mov     eax, 80070057h
0x1800054a0  cmp     ecx, eax
0x1800054a2  jg      short loc_18000550E
0x1800054a4  jz      short loc_180005504
0x1800054a6  cmp     ecx, 80004005h
0x1800054ac  jz      short loc_1800054FA
0x1800054ae  cmp     ecx, 80070001h
0x1800054b4  jz      short loc_1800054F0
0x1800054b6  cmp     ecx, 80070002h
0x1800054bc  jz      short loc_1800054E6
0x1800054be  cmp     ecx, 80070003h
0x1800054c4  jz      short loc_1800054DC
0x1800054c6  cmp     ecx, 8007000Eh
0x1800054cc  jnz     loc_1800055E9
0x1800054d2  mov     ecx, 0C0000017h
0x1800054d7  jmp     loc_180005641
0x1800054dc  mov     ecx, 0C000003Ah
0x1800054e1  jmp     loc_180005641
0x1800054e6  mov     ecx, 0C0000034h
0x1800054eb  jmp     loc_180005641
0x1800054f0  mov     ecx, 0C0000002h
0x1800054f5  jmp     loc_180005641
0x1800054fa  mov     ecx, 0C0000001h
0x1800054ff  jmp     loc_180005641
0x180005504  mov     ecx, 0C000000Dh
0x180005509  jmp     loc_180005641
0x18000550e  cmp     ecx, 80070070h
0x180005514  jz      short loc_180005550
0x180005516  cmp     ecx, 8007007Ah
0x18000551c  jz      short loc_180005546
0x18000551e  cmp     ecx, 8007007Bh
0x180005524  jz      short loc_18000553C
0x180005526  cmp     ecx, 8007007Eh
0x18000552c  jnz     loc_1800055E9
0x180005532  mov     ecx, 0C0000135h
0x180005537  jmp     loc_180005641
0x18000553c  mov     ecx, 0C0000033h
0x180005541  jmp     loc_180005641
0x180005546  mov     ecx, 0C0000023h
0x18000554b  jmp     loc_180005641
0x180005550  mov     ecx, 0C000007Fh
0x180005555  jmp     loc_180005641
0x18000555a  mov     ecx, 80000005h
0x18000555f  jmp     loc_180005641
0x180005564  mov     eax, 8007047Eh
0x180005569  cmp     ecx, eax
0x18000556b  jg      short loc_1800055CD
0x18000556d  jz      short loc_1800055C6
0x18000556f  cmp     ecx, 80070216h
0x180005575  jz      short loc_1800055BF
0x180005577  cmp     ecx, 8007023Eh
0x18000557d  jz      short loc_1800055B5
0x18000557f  cmp     ecx, 80070246h
0x180005585  jz      short loc_1800055AB
0x180005587  cmp     ecx, 80070247h
0x18000558d  jz      short loc_1800055A1
0x18000558f  cmp     ecx, 80070272h
0x180005595  jnz     short loc_1800055E9
0x180005597  mov     ecx, 0C0000273h
0x18000559c  jmp     loc_180005641
0x1800055a1  mov     ecx, 0C0000163h
0x1800055a6  jmp     loc_180005641
0x1800055ab  mov     ecx, 0C0000161h
0x1800055b0  jmp     loc_180005641
0x1800055b5  mov     ecx, 0C0000025h
0x1800055ba  jmp     loc_180005641
0x1800055bf  mov     ecx, 0C0000095h
0x1800055c4  jmp     short loc_180005641
0x1800055c6  mov     ecx, 0C0000059h
0x1800055cb  jmp     short loc_180005641
0x1800055cd  cmp     ecx, 8007050Ch
0x1800055d3  jz      short loc_18000563C
0x1800055d5  cmp     ecx, 8007054Fh
0x1800055db  jz      short loc_180005635
0x1800055dd  cmp     ecx, 800705B9h
0x1800055e3  jz      short loc_18000562E
0x1800055e5  test    ecx, ecx
0x1800055e7  jz      short loc_18000562A
0x1800055e9  bt      ecx, 1Ch
0x1800055ed  jnb     short loc_1800055F5
0x1800055ef  btr     ecx, 1Ch
0x1800055f3  jmp     short loc_180005641
0x1800055f5  mov     eax, ecx
0x1800055f7  and     eax, 1FFF0000h
0x1800055fc  cmp     eax, 70000h
0x180005601  jnz     short loc_180005614
0x180005603  movzx   ecx, cx
0x180005606  mov     eax, ecx
0x180005608  or      eax, 0C0070000h
0x18000560d  test    ecx, ecx
0x18000560f  cmovnz  ecx, eax
0x180005612  jmp     short loc_180005641
0x180005614  cmp     eax, 90000h
0x180005619  jnz     short loc_180005635
0x18000561b  test    ecx, ecx
0x18000561d  jle     short loc_180005641
0x18000561f  movzx   ecx, cx
0x180005622  or      ecx, 0C0090000h
0x180005628  jmp     short loc_180005641
0x18000562a  xor     ecx, ecx
0x18000562c  jmp     short loc_180005641
0x18000562e  mov     ecx, 0C000A083h
0x180005633  jmp     short loc_180005641
0x180005635  mov     ecx, 0C00000E5h
0x18000563a  jmp     short loc_180005641
0x18000563c  mov     ecx, 0C000042Bh
0x180005641  mov     eax, ecx
0x180005643  retn
```
