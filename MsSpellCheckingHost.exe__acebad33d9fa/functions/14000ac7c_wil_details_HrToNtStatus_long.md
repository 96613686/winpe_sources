# wil::details::HrToNtStatus(long)

- ea: `0x14000ac7c`
- end: `0x14000ae38`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x140006f94`
- `0x140007034`
- `0x140007084`
- `0x140007144`
- `0x14000a2d8`
- `0x14000b5b4`

## callees

- `0x14000ac7c`

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
0x14000ac7c  mov     eax, 800700EAh
0x14000ac81  cmp     ecx, eax
0x14000ac83  jg      loc_14000AD58
0x14000ac89  jz      loc_14000AD4E
0x14000ac8f  mov     eax, 80070057h
0x14000ac94  cmp     ecx, eax
0x14000ac96  jg      short loc_14000AD02
0x14000ac98  jz      short loc_14000ACF8
0x14000ac9a  cmp     ecx, 80004005h
0x14000aca0  jz      short loc_14000ACEE
0x14000aca2  cmp     ecx, 80070001h
0x14000aca8  jz      short loc_14000ACE4
0x14000acaa  cmp     ecx, 80070002h
0x14000acb0  jz      short loc_14000ACDA
0x14000acb2  cmp     ecx, 80070003h
0x14000acb8  jz      short loc_14000ACD0
0x14000acba  cmp     ecx, 8007000Eh
0x14000acc0  jnz     loc_14000ADDD
0x14000acc6  mov     ecx, 0C0000017h
0x14000accb  jmp     loc_14000AE35
0x14000acd0  mov     ecx, 0C000003Ah
0x14000acd5  jmp     loc_14000AE35
0x14000acda  mov     ecx, 0C0000034h
0x14000acdf  jmp     loc_14000AE35
0x14000ace4  mov     ecx, 0C0000002h
0x14000ace9  jmp     loc_14000AE35
0x14000acee  mov     ecx, 0C0000001h
0x14000acf3  jmp     loc_14000AE35
0x14000acf8  mov     ecx, 0C000000Dh
0x14000acfd  jmp     loc_14000AE35
0x14000ad02  cmp     ecx, 80070070h
0x14000ad08  jz      short loc_14000AD44
0x14000ad0a  cmp     ecx, 8007007Ah
0x14000ad10  jz      short loc_14000AD3A
0x14000ad12  cmp     ecx, 8007007Bh
0x14000ad18  jz      short loc_14000AD30
0x14000ad1a  cmp     ecx, 8007007Eh
0x14000ad20  jnz     loc_14000ADDD
0x14000ad26  mov     ecx, 0C0000135h
0x14000ad2b  jmp     loc_14000AE35
0x14000ad30  mov     ecx, 0C0000033h
0x14000ad35  jmp     loc_14000AE35
0x14000ad3a  mov     ecx, 0C0000023h
0x14000ad3f  jmp     loc_14000AE35
0x14000ad44  mov     ecx, 0C000007Fh
0x14000ad49  jmp     loc_14000AE35
0x14000ad4e  mov     ecx, 80000005h
0x14000ad53  jmp     loc_14000AE35
0x14000ad58  mov     eax, 8007047Eh
0x14000ad5d  cmp     ecx, eax
0x14000ad5f  jg      short loc_14000ADC1
0x14000ad61  jz      short loc_14000ADBA
0x14000ad63  cmp     ecx, 80070216h
0x14000ad69  jz      short loc_14000ADB3
0x14000ad6b  cmp     ecx, 8007023Eh
0x14000ad71  jz      short loc_14000ADA9
0x14000ad73  cmp     ecx, 80070246h
0x14000ad79  jz      short loc_14000AD9F
0x14000ad7b  cmp     ecx, 80070247h
0x14000ad81  jz      short loc_14000AD95
0x14000ad83  cmp     ecx, 80070272h
0x14000ad89  jnz     short loc_14000ADDD
0x14000ad8b  mov     ecx, 0C0000273h
0x14000ad90  jmp     loc_14000AE35
0x14000ad95  mov     ecx, 0C0000163h
0x14000ad9a  jmp     loc_14000AE35
0x14000ad9f  mov     ecx, 0C0000161h
0x14000ada4  jmp     loc_14000AE35
0x14000ada9  mov     ecx, 0C0000025h
0x14000adae  jmp     loc_14000AE35
0x14000adb3  mov     ecx, 0C0000095h
0x14000adb8  jmp     short loc_14000AE35
0x14000adba  mov     ecx, 0C0000059h
0x14000adbf  jmp     short loc_14000AE35
0x14000adc1  cmp     ecx, 8007050Ch
0x14000adc7  jz      short loc_14000AE30
0x14000adc9  cmp     ecx, 8007054Fh
0x14000adcf  jz      short loc_14000AE29
0x14000add1  cmp     ecx, 800705B9h
0x14000add7  jz      short loc_14000AE22
0x14000add9  test    ecx, ecx
0x14000addb  jz      short loc_14000AE1E
0x14000addd  bt      ecx, 1Ch
0x14000ade1  jnb     short loc_14000ADE9
0x14000ade3  btr     ecx, 1Ch
0x14000ade7  jmp     short loc_14000AE35
0x14000ade9  mov     eax, ecx
0x14000adeb  and     eax, 1FFF0000h
0x14000adf0  cmp     eax, 70000h
0x14000adf5  jnz     short loc_14000AE08
0x14000adf7  movzx   ecx, cx
0x14000adfa  mov     eax, ecx
0x14000adfc  or      eax, 0C0070000h
0x14000ae01  test    ecx, ecx
0x14000ae03  cmovnz  ecx, eax
0x14000ae06  jmp     short loc_14000AE35
0x14000ae08  cmp     eax, 90000h
0x14000ae0d  jnz     short loc_14000AE29
0x14000ae0f  test    ecx, ecx
0x14000ae11  jle     short loc_14000AE35
0x14000ae13  movzx   ecx, cx
0x14000ae16  or      ecx, 0C0090000h
0x14000ae1c  jmp     short loc_14000AE35
0x14000ae1e  xor     ecx, ecx
0x14000ae20  jmp     short loc_14000AE35
0x14000ae22  mov     ecx, 0C000A083h
0x14000ae27  jmp     short loc_14000AE35
0x14000ae29  mov     ecx, 0C00000E5h
0x14000ae2e  jmp     short loc_14000AE35
0x14000ae30  mov     ecx, 0C000042Bh
0x14000ae35  mov     eax, ecx
0x14000ae37  retn
```
