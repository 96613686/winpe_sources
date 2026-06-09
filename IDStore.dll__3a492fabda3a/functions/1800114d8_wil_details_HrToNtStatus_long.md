# wil::details::HrToNtStatus(long)

- ea: `0x1800114d8`
- end: `0x180011694`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800154dc`
- `0x180015540`
- `0x180015588`
- `0x180016ea0`

## callees

- `0x1800114d8`

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
0x1800114d8  mov     eax, 800700EAh
0x1800114dd  cmp     ecx, eax
0x1800114df  jg      loc_1800115B4
0x1800114e5  jz      loc_1800115AA
0x1800114eb  mov     eax, 80070057h
0x1800114f0  cmp     ecx, eax
0x1800114f2  jg      short loc_18001155E
0x1800114f4  jz      short loc_180011554
0x1800114f6  cmp     ecx, 80004005h
0x1800114fc  jz      short loc_18001154A
0x1800114fe  cmp     ecx, 80070001h
0x180011504  jz      short loc_180011540
0x180011506  cmp     ecx, 80070002h
0x18001150c  jz      short loc_180011536
0x18001150e  cmp     ecx, 80070003h
0x180011514  jz      short loc_18001152C
0x180011516  cmp     ecx, 8007000Eh
0x18001151c  jnz     loc_180011639
0x180011522  mov     ecx, 0C0000017h
0x180011527  jmp     loc_180011691
0x18001152c  mov     ecx, 0C000003Ah
0x180011531  jmp     loc_180011691
0x180011536  mov     ecx, 0C0000034h
0x18001153b  jmp     loc_180011691
0x180011540  mov     ecx, 0C0000002h
0x180011545  jmp     loc_180011691
0x18001154a  mov     ecx, 0C0000001h
0x18001154f  jmp     loc_180011691
0x180011554  mov     ecx, 0C000000Dh
0x180011559  jmp     loc_180011691
0x18001155e  cmp     ecx, 80070070h
0x180011564  jz      short loc_1800115A0
0x180011566  cmp     ecx, 8007007Ah
0x18001156c  jz      short loc_180011596
0x18001156e  cmp     ecx, 8007007Bh
0x180011574  jz      short loc_18001158C
0x180011576  cmp     ecx, 8007007Eh
0x18001157c  jnz     loc_180011639
0x180011582  mov     ecx, 0C0000135h
0x180011587  jmp     loc_180011691
0x18001158c  mov     ecx, 0C0000033h
0x180011591  jmp     loc_180011691
0x180011596  mov     ecx, 0C0000023h
0x18001159b  jmp     loc_180011691
0x1800115a0  mov     ecx, 0C000007Fh
0x1800115a5  jmp     loc_180011691
0x1800115aa  mov     ecx, 80000005h
0x1800115af  jmp     loc_180011691
0x1800115b4  mov     eax, 8007047Eh
0x1800115b9  cmp     ecx, eax
0x1800115bb  jg      short loc_18001161D
0x1800115bd  jz      short loc_180011616
0x1800115bf  cmp     ecx, 80070216h
0x1800115c5  jz      short loc_18001160F
0x1800115c7  cmp     ecx, 8007023Eh
0x1800115cd  jz      short loc_180011605
0x1800115cf  cmp     ecx, 80070246h
0x1800115d5  jz      short loc_1800115FB
0x1800115d7  cmp     ecx, 80070247h
0x1800115dd  jz      short loc_1800115F1
0x1800115df  cmp     ecx, 80070272h
0x1800115e5  jnz     short loc_180011639
0x1800115e7  mov     ecx, 0C0000273h
0x1800115ec  jmp     loc_180011691
0x1800115f1  mov     ecx, 0C0000163h
0x1800115f6  jmp     loc_180011691
0x1800115fb  mov     ecx, 0C0000161h
0x180011600  jmp     loc_180011691
0x180011605  mov     ecx, 0C0000025h
0x18001160a  jmp     loc_180011691
0x18001160f  mov     ecx, 0C0000095h
0x180011614  jmp     short loc_180011691
0x180011616  mov     ecx, 0C0000059h
0x18001161b  jmp     short loc_180011691
0x18001161d  cmp     ecx, 8007050Ch
0x180011623  jz      short loc_18001168C
0x180011625  cmp     ecx, 8007054Fh
0x18001162b  jz      short loc_180011685
0x18001162d  cmp     ecx, 800705B9h
0x180011633  jz      short loc_18001167E
0x180011635  test    ecx, ecx
0x180011637  jz      short loc_18001167A
0x180011639  bt      ecx, 1Ch
0x18001163d  jnb     short loc_180011645
0x18001163f  btr     ecx, 1Ch
0x180011643  jmp     short loc_180011691
0x180011645  mov     eax, ecx
0x180011647  and     eax, 1FFF0000h
0x18001164c  cmp     eax, 70000h
0x180011651  jnz     short loc_180011664
0x180011653  movzx   ecx, cx
0x180011656  mov     eax, ecx
0x180011658  or      eax, 0C0070000h
0x18001165d  test    ecx, ecx
0x18001165f  cmovnz  ecx, eax
0x180011662  jmp     short loc_180011691
0x180011664  cmp     eax, 90000h
0x180011669  jnz     short loc_180011685
0x18001166b  test    ecx, ecx
0x18001166d  jle     short loc_180011691
0x18001166f  movzx   ecx, cx
0x180011672  or      ecx, 0C0090000h
0x180011678  jmp     short loc_180011691
0x18001167a  xor     ecx, ecx
0x18001167c  jmp     short loc_180011691
0x18001167e  mov     ecx, 0C000A083h
0x180011683  jmp     short loc_180011691
0x180011685  mov     ecx, 0C00000E5h
0x18001168a  jmp     short loc_180011691
0x18001168c  mov     ecx, 0C000042Bh
0x180011691  mov     eax, ecx
0x180011693  retn
```
