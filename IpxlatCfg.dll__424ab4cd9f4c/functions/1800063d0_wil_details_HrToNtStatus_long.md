# wil::details::HrToNtStatus(long)

- ea: `0x1800063d0`
- end: `0x18000658c`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x180003574`
- `0x180003614`
- `0x180003664`
- `0x180003724`
- `0x1800059a8`
- `0x18000667c`
- `0x180008230`
- `0x1800180d4`
- `0x18001813f`
- `0x180018208`
- `0x180018273`

## callees

- `0x1800063d0`

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
0x1800063d0  mov     eax, 800700EAh
0x1800063d5  cmp     ecx, eax
0x1800063d7  jg      loc_1800064AC
0x1800063dd  jz      loc_1800064A2
0x1800063e3  mov     eax, 80070057h
0x1800063e8  cmp     ecx, eax
0x1800063ea  jg      short loc_180006456
0x1800063ec  jz      short loc_18000644C
0x1800063ee  cmp     ecx, 80004005h
0x1800063f4  jz      short loc_180006442
0x1800063f6  cmp     ecx, 80070001h
0x1800063fc  jz      short loc_180006438
0x1800063fe  cmp     ecx, 80070002h
0x180006404  jz      short loc_18000642E
0x180006406  cmp     ecx, 80070003h
0x18000640c  jz      short loc_180006424
0x18000640e  cmp     ecx, 8007000Eh
0x180006414  jnz     loc_180006531
0x18000641a  mov     ecx, 0C0000017h
0x18000641f  jmp     loc_180006589
0x180006424  mov     ecx, 0C000003Ah
0x180006429  jmp     loc_180006589
0x18000642e  mov     ecx, 0C0000034h
0x180006433  jmp     loc_180006589
0x180006438  mov     ecx, 0C0000002h
0x18000643d  jmp     loc_180006589
0x180006442  mov     ecx, 0C0000001h
0x180006447  jmp     loc_180006589
0x18000644c  mov     ecx, 0C000000Dh
0x180006451  jmp     loc_180006589
0x180006456  cmp     ecx, 80070070h
0x18000645c  jz      short loc_180006498
0x18000645e  cmp     ecx, 8007007Ah
0x180006464  jz      short loc_18000648E
0x180006466  cmp     ecx, 8007007Bh
0x18000646c  jz      short loc_180006484
0x18000646e  cmp     ecx, 8007007Eh
0x180006474  jnz     loc_180006531
0x18000647a  mov     ecx, 0C0000135h
0x18000647f  jmp     loc_180006589
0x180006484  mov     ecx, 0C0000033h
0x180006489  jmp     loc_180006589
0x18000648e  mov     ecx, 0C0000023h
0x180006493  jmp     loc_180006589
0x180006498  mov     ecx, 0C000007Fh
0x18000649d  jmp     loc_180006589
0x1800064a2  mov     ecx, 80000005h
0x1800064a7  jmp     loc_180006589
0x1800064ac  mov     eax, 8007047Eh
0x1800064b1  cmp     ecx, eax
0x1800064b3  jg      short loc_180006515
0x1800064b5  jz      short loc_18000650E
0x1800064b7  cmp     ecx, 80070216h
0x1800064bd  jz      short loc_180006507
0x1800064bf  cmp     ecx, 8007023Eh
0x1800064c5  jz      short loc_1800064FD
0x1800064c7  cmp     ecx, 80070246h
0x1800064cd  jz      short loc_1800064F3
0x1800064cf  cmp     ecx, 80070247h
0x1800064d5  jz      short loc_1800064E9
0x1800064d7  cmp     ecx, 80070272h
0x1800064dd  jnz     short loc_180006531
0x1800064df  mov     ecx, 0C0000273h
0x1800064e4  jmp     loc_180006589
0x1800064e9  mov     ecx, 0C0000163h
0x1800064ee  jmp     loc_180006589
0x1800064f3  mov     ecx, 0C0000161h
0x1800064f8  jmp     loc_180006589
0x1800064fd  mov     ecx, 0C0000025h
0x180006502  jmp     loc_180006589
0x180006507  mov     ecx, 0C0000095h
0x18000650c  jmp     short loc_180006589
0x18000650e  mov     ecx, 0C0000059h
0x180006513  jmp     short loc_180006589
0x180006515  cmp     ecx, 8007050Ch
0x18000651b  jz      short loc_180006584
0x18000651d  cmp     ecx, 8007054Fh
0x180006523  jz      short loc_18000657D
0x180006525  cmp     ecx, 800705B9h
0x18000652b  jz      short loc_180006576
0x18000652d  test    ecx, ecx
0x18000652f  jz      short loc_180006572
0x180006531  bt      ecx, 1Ch
0x180006535  jnb     short loc_18000653D
0x180006537  btr     ecx, 1Ch
0x18000653b  jmp     short loc_180006589
0x18000653d  mov     eax, ecx
0x18000653f  and     eax, 1FFF0000h
0x180006544  cmp     eax, 70000h
0x180006549  jnz     short loc_18000655C
0x18000654b  movzx   ecx, cx
0x18000654e  mov     eax, ecx
0x180006550  or      eax, 0C0070000h
0x180006555  test    ecx, ecx
0x180006557  cmovnz  ecx, eax
0x18000655a  jmp     short loc_180006589
0x18000655c  cmp     eax, 90000h
0x180006561  jnz     short loc_18000657D
0x180006563  test    ecx, ecx
0x180006565  jle     short loc_180006589
0x180006567  movzx   ecx, cx
0x18000656a  or      ecx, 0C0090000h
0x180006570  jmp     short loc_180006589
0x180006572  xor     ecx, ecx
0x180006574  jmp     short loc_180006589
0x180006576  mov     ecx, 0C000A083h
0x18000657b  jmp     short loc_180006589
0x18000657d  mov     ecx, 0C00000E5h
0x180006582  jmp     short loc_180006589
0x180006584  mov     ecx, 0C000042Bh
0x180006589  mov     eax, ecx
0x18000658b  retn
```
