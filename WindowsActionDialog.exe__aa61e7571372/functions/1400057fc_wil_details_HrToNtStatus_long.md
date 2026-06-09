# wil::details::HrToNtStatus(long)

- ea: `0x1400057fc`
- end: `0x1400059b8`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x1400020a8`
- `0x1400022a8`
- `0x140002364`
- `0x1400023c0`
- `0x14000249c`
- `0x140004418`
- `0x1400059e8`
- `0x140006260`
- `0x1400095ef`
- `0x14000965a`
- `0x140009723`
- `0x14000978e`

## callees

- `0x1400057fc`

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
0x1400057fc  mov     eax, 800700EAh
0x140005801  cmp     ecx, eax
0x140005803  jg      loc_1400058D8
0x140005809  jz      loc_1400058CE
0x14000580f  mov     eax, 80070057h
0x140005814  cmp     ecx, eax
0x140005816  jg      short loc_140005882
0x140005818  jz      short loc_140005878
0x14000581a  cmp     ecx, 80004005h
0x140005820  jz      short loc_14000586E
0x140005822  cmp     ecx, 80070001h
0x140005828  jz      short loc_140005864
0x14000582a  cmp     ecx, 80070002h
0x140005830  jz      short loc_14000585A
0x140005832  cmp     ecx, 80070003h
0x140005838  jz      short loc_140005850
0x14000583a  cmp     ecx, 8007000Eh
0x140005840  jnz     loc_14000595D
0x140005846  mov     ecx, 0C0000017h
0x14000584b  jmp     loc_1400059B5
0x140005850  mov     ecx, 0C000003Ah
0x140005855  jmp     loc_1400059B5
0x14000585a  mov     ecx, 0C0000034h
0x14000585f  jmp     loc_1400059B5
0x140005864  mov     ecx, 0C0000002h
0x140005869  jmp     loc_1400059B5
0x14000586e  mov     ecx, 0C0000001h
0x140005873  jmp     loc_1400059B5
0x140005878  mov     ecx, 0C000000Dh
0x14000587d  jmp     loc_1400059B5
0x140005882  cmp     ecx, 80070070h
0x140005888  jz      short loc_1400058C4
0x14000588a  cmp     ecx, 8007007Ah
0x140005890  jz      short loc_1400058BA
0x140005892  cmp     ecx, 8007007Bh
0x140005898  jz      short loc_1400058B0
0x14000589a  cmp     ecx, 8007007Eh
0x1400058a0  jnz     loc_14000595D
0x1400058a6  mov     ecx, 0C0000135h
0x1400058ab  jmp     loc_1400059B5
0x1400058b0  mov     ecx, 0C0000033h
0x1400058b5  jmp     loc_1400059B5
0x1400058ba  mov     ecx, 0C0000023h
0x1400058bf  jmp     loc_1400059B5
0x1400058c4  mov     ecx, 0C000007Fh
0x1400058c9  jmp     loc_1400059B5
0x1400058ce  mov     ecx, 80000005h
0x1400058d3  jmp     loc_1400059B5
0x1400058d8  mov     eax, 8007047Eh
0x1400058dd  cmp     ecx, eax
0x1400058df  jg      short loc_140005941
0x1400058e1  jz      short loc_14000593A
0x1400058e3  cmp     ecx, 80070216h
0x1400058e9  jz      short loc_140005933
0x1400058eb  cmp     ecx, 8007023Eh
0x1400058f1  jz      short loc_140005929
0x1400058f3  cmp     ecx, 80070246h
0x1400058f9  jz      short loc_14000591F
0x1400058fb  cmp     ecx, 80070247h
0x140005901  jz      short loc_140005915
0x140005903  cmp     ecx, 80070272h
0x140005909  jnz     short loc_14000595D
0x14000590b  mov     ecx, 0C0000273h
0x140005910  jmp     loc_1400059B5
0x140005915  mov     ecx, 0C0000163h
0x14000591a  jmp     loc_1400059B5
0x14000591f  mov     ecx, 0C0000161h
0x140005924  jmp     loc_1400059B5
0x140005929  mov     ecx, 0C0000025h
0x14000592e  jmp     loc_1400059B5
0x140005933  mov     ecx, 0C0000095h
0x140005938  jmp     short loc_1400059B5
0x14000593a  mov     ecx, 0C0000059h
0x14000593f  jmp     short loc_1400059B5
0x140005941  cmp     ecx, 8007050Ch
0x140005947  jz      short loc_1400059B0
0x140005949  cmp     ecx, 8007054Fh
0x14000594f  jz      short loc_1400059A9
0x140005951  cmp     ecx, 800705B9h
0x140005957  jz      short loc_1400059A2
0x140005959  test    ecx, ecx
0x14000595b  jz      short loc_14000599E
0x14000595d  bt      ecx, 1Ch
0x140005961  jnb     short loc_140005969
0x140005963  btr     ecx, 1Ch
0x140005967  jmp     short loc_1400059B5
0x140005969  mov     eax, ecx
0x14000596b  and     eax, 1FFF0000h
0x140005970  cmp     eax, 70000h
0x140005975  jnz     short loc_140005988
0x140005977  movzx   ecx, cx
0x14000597a  mov     eax, ecx
0x14000597c  or      eax, 0C0070000h
0x140005981  test    ecx, ecx
0x140005983  cmovnz  ecx, eax
0x140005986  jmp     short loc_1400059B5
0x140005988  cmp     eax, 90000h
0x14000598d  jnz     short loc_1400059A9
0x14000598f  test    ecx, ecx
0x140005991  jle     short loc_1400059B5
0x140005993  movzx   ecx, cx
0x140005996  or      ecx, 0C0090000h
0x14000599c  jmp     short loc_1400059B5
0x14000599e  xor     ecx, ecx
0x1400059a0  jmp     short loc_1400059B5
0x1400059a2  mov     ecx, 0C000A083h
0x1400059a7  jmp     short loc_1400059B5
0x1400059a9  mov     ecx, 0C00000E5h
0x1400059ae  jmp     short loc_1400059B5
0x1400059b0  mov     ecx, 0C000042Bh
0x1400059b5  mov     eax, ecx
0x1400059b7  retn
```
